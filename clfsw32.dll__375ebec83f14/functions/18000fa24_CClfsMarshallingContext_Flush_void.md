# CClfsMarshallingContext::Flush(void)

- ea: `0x18000fa24`
- end: `0x18000fcd5`
- name: `?Flush@CClfsMarshallingContext@@AEAAKXZ`
- size: `689`
- prototype: `unsigned int __fastcall(CClfsMarshallingContext *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000e534`
- `0x1800136a0`

## callees

- `0x18000e750`
- `0x18000fa24`
- `0x18001031c`
- `0x180011330`
- `0x1800130a0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000fcc2`
- `ntdll!RtlLeaveCriticalSection` at `0x180015859`
- `ntdll!RtlLeaveCriticalSection` at `0x18000fcc2`
- `ntdll!RtlLeaveCriticalSection` at `0x180015859`
- `ntdll!RtlEnterCriticalSection` at `0x18000fa8a`
- `ntdll!RtlEnterCriticalSection` at `0x18000fa8a`
- `ntdll!RtlNtStatusToDosError` at `0x18000fbee`
- `ntdll!RtlNtStatusToDosError` at `0x18000fbee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fc0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fc0f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000fb7c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000fb7c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000fbcb`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000fbcb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000fbaa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000fbaa`

## pseudocode

```c
__int64 __fastcall CClfsMarshallingContext::Flush(CClfsMarshallingContext *this)
{
  DWORD LastError; // esi
  unsigned int IocbNaked; // ebx
  struct _RTL_CRITICAL_SECTION *v5; // r12
  char v6; // r14
  struct CLogIocb *v7; // r13
  void *v8; // r15
  unsigned __int64 EventA; // rax
  void *v10; // rcx
  CLFS_LSN InBuffer; // [rsp+48h] [rbp-60h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-58h] BYREF
  DWORD BytesReturned; // [rsp+B8h] [rbp+10h] BYREF
  CLFS_LSN OutBuffer; // [rsp+C0h] [rbp+18h] BYREF
  HANDLE hDevice; // [rsp+C8h] [rbp+20h] BYREF

  InBuffer = CLFS_LSN_NULL;
  OutBuffer = CLFS_LSN_INVALID;
  LastError = 0;
  hDevice = 0;
  IocbNaked = 0;
  BytesReturned = 0;
  if ( !*((_DWORD *)this + 31) )
    return 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 328);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 328));
  v6 = 1;
  if ( !(unsigned int)CFlushQ::IsEmpty((CClfsMarshallingContext *)((char *)this + 232)) )
  {
    InBuffer = *(CLFS_LSN *)((char *)this + 200);
    IocbNaked = CClfsMarshallingContext::AllocateIocbNaked(this, (struct CLogIocb **)&hDevice);
    if ( !IocbNaked )
    {
      v7 = (struct CLogIocb *)hDevice;
      v8 = (void *)*((_QWORD *)hDevice + 7);
      hDevice = (HANDLE)*((_QWORD *)this + 6);
      memset(&Overlapped, 0, sizeof(Overlapped));
      BytesReturned = 0;
      OutBuffer = CLFS_LSN_INVALID;
      if ( v8 )
      {
        Overlapped.hEvent = v8;
        EventA = (unsigned __int64)v8;
      }
      else
      {
        EventA = (unsigned __int64)CreateEventA(0, 0, 0, 0);
        Overlapped.hEvent = (HANDLE)EventA;
        if ( !EventA )
        {
          IocbNaked = 8;
          goto LABEL_18;
        }
      }
      Overlapped.hEvent = (HANDLE)(EventA | 1);
      if ( !DeviceIoControl(hDevice, 0x8007282C, &InBuffer, 8u, &OutBuffer, 8u, &BytesReturned, &Overlapped) )
        LastError = GetLastError();
      if ( LastError == 997 )
      {
        if ( WaitForSingleObject(Overlapped.hEvent, 0xFFFFFFFF) )
          LastError = 1117;
        else
          LastError = RtlNtStatusToDosError(Overlapped.Internal);
      }
      v10 = (void *)((unsigned __int64)Overlapped.hEvent & 0xFFFFFFFFFFFFFFFEuLL);
      Overlapped.hEvent = (HANDLE)((unsigned __int64)Overlapped.hEvent & ~1uLL);
      if ( !v8 )
        CloseHandle(v10);
      Overlapped.hEvent = 0;
      IocbNaked = LastError;
LABEL_18:
      CClfsMarshallingContext::FreeIocbNaked(this, v7);
      hDevice = 0;
      if ( IocbNaked )
        goto LABEL_26;
      if ( this == (CClfsMarshallingContext *)-208LL )
      {
        v6 = 0;
      }
      else if ( *((_QWORD *)this + 26) >= OutBuffer.ullOffset )
      {
LABEL_25:
        CClfsMarshallingContext::ReleaseFlushElements(this, &OutBuffer);
        goto LABEL_26;
      }
      if ( v6 )
        *((CLFS_LSN *)this + 26) = OutBuffer;
      goto LABEL_25;
    }
  }
LABEL_26:
  if ( IocbNaked == 6640 || IocbNaked == 6643 )
  {
    hDevice = (HANDLE)CLFS_LSN_INVALID.ullOffset;
    CClfsMarshallingContext::ReleaseFlushElements(this, (union _CLS_LSN *)&hDevice);
  }
  RtlLeaveCriticalSection(v5);
  return IocbNaked;
}

```

## disassembly

```asm
0x18000fa24  mov     r11, rsp
0x18000fa27  mov     [r11+8], rcx
0x18000fa2b  push    rbx
0x18000fa2c  push    rsi
0x18000fa2d  push    rdi
0x18000fa2e  push    r12
0x18000fa30  push    r13
0x18000fa32  push    r14
0x18000fa34  push    r15
0x18000fa36  sub     rsp, 70h
0x18000fa3a  mov     rdi, rcx
0x18000fa3d  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x18000fa44  mov     [r11-60h], rax
0x18000fa48  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000fa4f  mov     [r11+18h], rax
0x18000fa53  xor     esi, esi
0x18000fa55  mov     [r11+20h], rsi
0x18000fa59  mov     ebx, esi
0x18000fa5b  mov     [rsp+0A8h+var_64], ebx
0x18000fa5f  mov     [r11+10h], esi
0x18000fa63  mov     [rsp+0A8h+var_68], sil
0x18000fa68  cmp     [rcx+7Ch], esi
0x18000fa6b  jnz     short loc_18000FA80
0x18000fa6d  xor     eax, eax
0x18000fa6f  add     rsp, 70h
0x18000fa73  pop     r15
0x18000fa75  pop     r14
0x18000fa77  pop     r13
0x18000fa79  pop     r12
0x18000fa7b  pop     rdi
0x18000fa7c  pop     rsi
0x18000fa7d  pop     rbx
0x18000fa7e  retn
0x18000fa80  lea     r12, [rcx+148h]
0x18000fa87  mov     rcx, r12; CriticalSection
0x18000fa8a  call    cs:__imp_RtlEnterCriticalSection
0x18000fa91  nop     dword ptr [rax+rax+00h]
0x18000fa96  mov     r14d, 1
0x18000fa9c  mov     [rsp+0A8h+var_68], r14b
0x18000faa1  lea     rcx, [rdi+0E8h]; this
0x18000faa8  call    ?IsEmpty@CFlushQ@@QEAAHXZ; CFlushQ::IsEmpty(void)
0x18000faad  test    eax, eax
0x18000faaf  jnz     loc_18000FC90
0x18000fab5  mov     rax, [rdi+0C8h]
0x18000fabc  mov     [rsp+0A8h+InBuffer], rax
0x18000fac1  lea     rdx, [rsp+0A8h+hDevice]; struct CLogIocb **
0x18000fac9  mov     rcx, rdi; this
0x18000facc  call    ?AllocateIocbNaked@CClfsMarshallingContext@@AEAAKPEAPEAVCLogIocb@@@Z; CClfsMarshallingContext::AllocateIocbNaked(CLogIocb * *)
0x18000fad1  mov     ebx, eax
0x18000fad3  mov     [rsp+0A8h+var_64], eax
0x18000fad7  test    eax, eax
0x18000fad9  jnz     loc_18000FC90
0x18000fadf  mov     r13, [rsp+0A8h+hDevice]
0x18000fae7  mov     r15, [r13+38h]
0x18000faeb  mov     rax, [rdi+30h]
0x18000faef  mov     [rsp+0A8h+hDevice], rax
0x18000faf7  mov     [rsp+0A8h+Overlapped.Internal], rsi
0x18000fafc  mov     [rsp+0A8h+Overlapped.InternalHigh], rsi
0x18000fb01  mov     qword ptr [rsp+0A8h+Overlapped.10h], rsi
0x18000fb06  mov     [rsp+0A8h+Overlapped.hEvent], rsi
0x18000fb0b  mov     [rsp+0A8h+BytesReturned], ebx
0x18000fb12  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000fb19  mov     [rsp+0A8h+OutBuffer], rax
0x18000fb21  test    r15, r15
0x18000fb24  jz      loc_18000FBC1
0x18000fb2a  mov     [rsp+0A8h+Overlapped.hEvent], r15
0x18000fb2f  mov     rax, r15
0x18000fb32  or      rax, r14
0x18000fb35  mov     [rsp+0A8h+Overlapped.hEvent], rax
0x18000fb3a  lea     rax, [rsp+0A8h+Overlapped]
0x18000fb3f  mov     [rsp+0A8h+lpOverlapped], rax; lpOverlapped
0x18000fb44  lea     rax, [rsp+0A8h+BytesReturned]
0x18000fb4c  mov     [rsp+0A8h+lpBytesReturned], rax; lpBytesReturned
0x18000fb51  mov     ebx, 8
0x18000fb56  mov     [rsp+0A8h+nOutBufferSize], ebx; nOutBufferSize
0x18000fb5a  lea     rax, [rsp+0A8h+OutBuffer]
0x18000fb62  mov     [rsp+0A8h+lpOutBuffer], rax; lpOutBuffer
0x18000fb67  mov     r9d, ebx; nInBufferSize
0x18000fb6a  lea     r8, [rsp+0A8h+InBuffer]; lpInBuffer
0x18000fb6f  mov     edx, 8007282Ch; dwIoControlCode
0x18000fb74  mov     rcx, [rsp+0A8h+hDevice]; hDevice
0x18000fb7c  call    cs:__imp_DeviceIoControl
0x18000fb83  nop     dword ptr [rax+rax+00h]
0x18000fb88  test    eax, eax
0x18000fb8a  jnz     short loc_18000FB9A
0x18000fb8c  call    cs:__imp_GetLastError
0x18000fb93  nop     dword ptr [rax+rax+00h]
0x18000fb98  mov     esi, eax
0x18000fb9a  cmp     esi, 3E5h
0x18000fba0  jnz     short loc_18000FBFC
0x18000fba2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000fba5  mov     rcx, [rsp+0A8h+Overlapped.hEvent]; hHandle
0x18000fbaa  call    cs:__imp_WaitForSingleObject
0x18000fbb1  nop     dword ptr [rax+rax+00h]
0x18000fbb6  test    eax, eax
0x18000fbb8  jz      short loc_18000FBEA
0x18000fbba  mov     esi, 45Dh
0x18000fbbf  jmp     short loc_18000FBFC
0x18000fbc1  xor     r9d, r9d; lpName
0x18000fbc4  xor     r8d, r8d; bInitialState
0x18000fbc7  xor     edx, edx; bManualReset
0x18000fbc9  xor     ecx, ecx; lpEventAttributes
0x18000fbcb  call    cs:__imp_CreateEventA
0x18000fbd2  nop     dword ptr [rax+rax+00h]
0x18000fbd7  mov     [rsp+0A8h+Overlapped.hEvent], rax
0x18000fbdc  test    rax, rax
0x18000fbdf  jnz     loc_18000FB32
0x18000fbe5  lea     ebx, [rax+8]
0x18000fbe8  jmp     short loc_18000FC26
0x18000fbea  mov     ecx, dword ptr [rsp+0A8h+Overlapped.Internal]; Status
0x18000fbee  call    cs:__imp_RtlNtStatusToDosError
0x18000fbf5  nop     dword ptr [rax+rax+00h]
0x18000fbfa  mov     esi, eax
0x18000fbfc  mov     rcx, [rsp+0A8h+Overlapped.hEvent]
0x18000fc01  and     rcx, 0FFFFFFFFFFFFFFFEh; hObject
0x18000fc05  mov     [rsp+0A8h+Overlapped.hEvent], rcx
0x18000fc0a  test    r15, r15
0x18000fc0d  jnz     short loc_18000FC1B
0x18000fc0f  call    cs:__imp_CloseHandle
0x18000fc16  nop     dword ptr [rax+rax+00h]
0x18000fc1b  mov     [rsp+0A8h+Overlapped.hEvent], 0
0x18000fc24  mov     ebx, esi
0x18000fc26  mov     [rsp+0A8h+var_64], ebx
0x18000fc2a  mov     rdx, r13; struct CLogIocb *
0x18000fc2d  mov     rcx, rdi; this
0x18000fc30  call    ?FreeIocbNaked@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z; CClfsMarshallingContext::FreeIocbNaked(CLogIocb *)
0x18000fc35  mov     [rsp+0A8h+hDevice], 0
0x18000fc41  test    ebx, ebx
0x18000fc43  jnz     short loc_18000FC90
0x18000fc45  lea     rcx, [rdi+0D0h]
0x18000fc4c  test    rcx, rcx
0x18000fc4f  jz      short loc_18000FC6C
0x18000fc51  mov     eax, [rcx+4]
0x18000fc54  cmp     eax, dword ptr [rsp+0A8h+OutBuffer+4]
0x18000fc5b  ja      short loc_18000FC7F
0x18000fc5d  jnz     short loc_18000FC6F
0x18000fc5f  mov     eax, dword ptr [rsp+0A8h+OutBuffer]
0x18000fc66  cmp     [rcx], eax
0x18000fc68  jnb     short loc_18000FC7F
0x18000fc6a  jmp     short loc_18000FC6F
0x18000fc6c  xor     r14b, r14b
0x18000fc6f  test    r14b, r14b
0x18000fc72  jz      short loc_18000FC7F
0x18000fc74  mov     rax, [rsp+0A8h+OutBuffer]
0x18000fc7c  mov     [rcx], rax
0x18000fc7f  lea     rdx, [rsp+0A8h+OutBuffer]; union _CLS_LSN *
0x18000fc87  mov     rcx, rdi; this
0x18000fc8a  call    ?ReleaseFlushElements@CClfsMarshallingContext@@AEAAXAEAT_CLS_LSN@@@Z; CClfsMarshallingContext::ReleaseFlushElements(_CLS_LSN &)
0x18000fc8f  nop
0x18000fc90  cmp     ebx, 19F0h
0x18000fc96  jz      short loc_18000FCA0
0x18000fc98  cmp     ebx, 19F3h
0x18000fc9e  jnz     short loc_18000FCBF
0x18000fca0  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000fca7  mov     [rsp+0A8h+hDevice], rax
0x18000fcaf  lea     rdx, [rsp+0A8h+hDevice]; union _CLS_LSN *
0x18000fcb7  mov     rcx, rdi; this
0x18000fcba  call    ?ReleaseFlushElements@CClfsMarshallingContext@@AEAAXAEAT_CLS_LSN@@@Z; CClfsMarshallingContext::ReleaseFlushElements(_CLS_LSN &)
0x18000fcbf  mov     rcx, r12; CriticalSection
0x18000fcc2  call    cs:__imp_RtlLeaveCriticalSection
0x18000fcc9  nop     dword ptr [rax+rax+00h]
0x18000fcce  mov     eax, ebx
0x18000fcd0  jmp     loc_18000FA6F
0x180015808  push    rbp
0x18001580a  sub     rsp, 40h
0x18001580e  mov     rbp, rdx
0x180015811  cmp     dword ptr [rbp+44h], 19F0h
0x180015818  jz      short loc_180015823
0x18001581a  cmp     dword ptr [rbp+44h], 19F3h
0x180015821  jnz     short loc_180015845
0x180015823  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18001582a  mov     [rbp+0C8h], rax
0x180015831  lea     rdx, [rbp+0C8h]; union _CLS_LSN *
0x180015838  mov     rcx, [rbp+0B0h]; this
0x18001583f  call    ?ReleaseFlushElements@CClfsMarshallingContext@@AEAAXAEAT_CLS_LSN@@@Z; CClfsMarshallingContext::ReleaseFlushElements(_CLS_LSN &)
0x180015844  nop
0x180015845  cmp     byte ptr [rbp+40h], 0
0x180015849  jz      short loc_180015869
0x18001584b  mov     rcx, [rbp+0B0h]
0x180015852  add     rcx, 148h; CriticalSection
0x180015859  call    cs:__imp_RtlLeaveCriticalSection
0x180015860  nop     dword ptr [rax+rax+00h]
0x180015865  mov     byte ptr [rbp+40h], 0
0x180015869  add     rsp, 40h
0x18001586d  pop     rbp
0x18001586e  retn
```
