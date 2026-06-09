# CClfsMarshallingContext::FlushToLsn(_CLS_LSN const &,_CLS_LSN &,_OVERLAPPED *)

- ea: `0x18000fcdc`
- end: `0x1800101bf`
- name: `?FlushToLsn@CClfsMarshallingContext@@QEAAKAEBT_CLS_LSN@@AEAT2@PEAU_OVERLAPPED@@@Z`
- size: `1251`
- prototype: `unsigned int __fastcall(CClfsMarshallingContext *__hidden this, const union _CLS_LSN *, union _CLS_LSN *, struct _OVERLAPPED *)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000b630`
- `0x18000b6c0`
- `0x180011854`

## callees

- `0x18000e750`
- `0x18000efa0`
- `0x18000fcdc`
- `0x18001031c`
- `0x1800130a0`
- `0x180013f04`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180010199`
- `ntdll!RtlLeaveCriticalSection` at `0x1800101ac`
- `ntdll!RtlLeaveCriticalSection` at `0x1800158de`
- `ntdll!RtlLeaveCriticalSection` at `0x180015902`
- `ntdll!RtlLeaveCriticalSection` at `0x180010199`
- `ntdll!RtlLeaveCriticalSection` at `0x1800101ac`
- `ntdll!RtlLeaveCriticalSection` at `0x1800158de`
- `ntdll!RtlLeaveCriticalSection` at `0x180015902`
- `ntdll!RtlEnterCriticalSection` at `0x18000fd9d`
- `ntdll!RtlEnterCriticalSection` at `0x1800100f5`
- `ntdll!RtlEnterCriticalSection` at `0x18000fd9d`
- `ntdll!RtlEnterCriticalSection` at `0x1800100f5`
- `ntdll!RtlNtStatusToDosError` at `0x18001005b`
- `ntdll!RtlNtStatusToDosError` at `0x18001005b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010005`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010083`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010083`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000fff5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000fff5`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000ff93`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000ff93`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001003b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001003b`

## pseudocode

```c
__int64 __fastcall CClfsMarshallingContext::FlushToLsn(
        CClfsMarshallingContext *this,
        const union _CLS_LSN *a2,
        union _CLS_LSN *a3,
        struct _OVERLAPPED *a4)
{
  CLFS_RECORD_INDEX v8; // eax
  char v10; // r12
  union _CLS_LSN v11; // rcx
  char v12; // al
  char v13; // al
  CLFS_LSN v14; // rax
  unsigned int IocbNaked; // ebx
  char v16; // dl
  __int64 v17; // rdx
  HANDLE v18; // rcx
  struct _OVERLAPPED *lpOverlapped; // r14
  DWORD LastError; // esi
  unsigned __int64 EventA; // rax
  char v22; // si
  CLFS_LSN InBuffer; // [rsp+50h] [rbp-78h] BYREF
  union _CLS_LSN v24; // [rsp+58h] [rbp-70h] BYREF
  DWORD BytesReturned; // [rsp+60h] [rbp-68h] BYREF
  union _CLS_LSN v26; // [rsp+68h] [rbp-60h] BYREF
  __int64 v27; // [rsp+70h] [rbp-58h]
  HANDLE hDevice; // [rsp+78h] [rbp-50h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+80h] [rbp-48h] BYREF

  InBuffer = CLFS_LSN_NULL;
  hDevice = (HANDLE)CLFS_LSN_INVALID.ullOffset;
  v26 = CLFS_LSN_INVALID;
  v24.ullOffset = 0;
  BytesReturned = 0;
  if ( a2 && CLFS_LSN_INVALID.ullOffset == a2->ullOffset )
    return 87;
  v8 = -1;
  if ( a2 )
    v8 = a2->offset.idxRecord & 0xFFFFFE00;
  if ( v8 % *((_DWORD *)this + 34) )
    return 87;
  v27 = 0;
  if ( !*((_DWORD *)this + 31) )
    return 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 288));
  v10 = 1;
  InBuffer = *a2;
  v11 = CLFS_LSN_NULL;
  if ( CLFS_LSN_NULL.ullOffset == InBuffer.ullOffset )
    goto LABEL_15;
  if ( this == (CClfsMarshallingContext *)-200LL )
  {
    v12 = 0;
  }
  else
  {
    if ( a2->ullOffset <= *((_QWORD *)this + 25) )
      goto LABEL_16;
    v12 = 1;
  }
  if ( v12 )
LABEL_15:
    InBuffer = *(CLFS_LSN *)((char *)this + 200);
LABEL_16:
  if ( this == (CClfsMarshallingContext *)-200LL )
  {
    v13 = 0;
  }
  else
  {
    if ( InBuffer.ullOffset >= *((_QWORD *)this + 25) )
      goto LABEL_24;
    v13 = 1;
  }
  if ( v13 )
  {
    CFlushQ::UpperBound((CClfsMarshallingContext *)((char *)this + 232), &InBuffer, (union _CLS_LSN *)&hDevice, &v26);
    v14 = CLFS_LSN_INVALID;
    if ( CLFS_LSN_INVALID.ullOffset != v26.ullOffset )
      InBuffer = v26;
    v11 = CLFS_LSN_NULL;
    goto LABEL_27;
  }
LABEL_24:
  if ( *((_QWORD *)this + 20) )
  {
    IocbNaked = CClfsMarshallingContext::AppendWriteBlockToFlushQueue(this, 0, 2u, a4);
    v14 = CLFS_LSN_INVALID;
    goto LABEL_78;
  }
  v14 = CLFS_LSN_INVALID;
LABEL_27:
  if ( this == (CClfsMarshallingContext *)-200LL )
  {
    v16 = 0;
  }
  else
  {
    if ( InBuffer.ullOffset <= *((_QWORD *)this + 25) )
      goto LABEL_32;
    v16 = 1;
  }
  if ( !v16 )
  {
LABEL_32:
    if ( v11.ullOffset != a2->ullOffset )
      goto LABEL_34;
  }
  InBuffer = v11;
LABEL_34:
  if ( !a4 )
  {
    IocbNaked = CClfsMarshallingContext::AllocateIocbNaked(this, (struct CLogIocb **)&v24);
    v14 = CLFS_LSN_INVALID;
    if ( !IocbNaked )
    {
      v17 = *(_QWORD *)(v24.ullOffset + 56);
      v27 = v17;
      goto LABEL_38;
    }
LABEL_78:
    v22 = 0;
    goto LABEL_79;
  }
  v17 = v27;
LABEL_38:
  v26.offset.idxRecord = *((_DWORD *)this + 39) & 0x20;
  v18 = (HANDLE)*((_QWORD *)this + 6);
  hDevice = v18;
  memset(&Overlapped, 0, sizeof(Overlapped));
  lpOverlapped = a4;
  LastError = 0;
  if ( a3 )
  {
    BytesReturned = 0;
    *a3 = v14;
    if ( v17 )
    {
      lpOverlapped = &Overlapped;
      Overlapped.hEvent = (HANDLE)(v17 | 1);
    }
    else if ( !a4 )
    {
      lpOverlapped = &Overlapped;
      EventA = (unsigned __int64)CreateEventA(0, 0, 0, 0);
      Overlapped.hEvent = (HANDLE)EventA;
      if ( !EventA )
      {
        IocbNaked = 8;
LABEL_44:
        v14 = CLFS_LSN_INVALID;
        goto LABEL_67;
      }
      Overlapped.hEvent = (HANDLE)(EventA | 1);
      v18 = hDevice;
    }
    if ( !DeviceIoControl(v18, 0x8007282C, &InBuffer, 8u, a3, 8u, &BytesReturned, lpOverlapped) )
      LastError = GetLastError();
    if ( v27 || !a4 )
    {
      IocbNaked = 997;
      if ( LastError == 997 )
      {
        if ( WaitForSingleObject(lpOverlapped->hEvent, 0xFFFFFFFF) )
          LastError = 1117;
        else
          LastError = RtlNtStatusToDosError(lpOverlapped->Internal);
      }
      lpOverlapped->hEvent = (HANDLE)((unsigned __int64)lpOverlapped->hEvent & ~1uLL);
      if ( !v27 && !a4 )
        CloseHandle(lpOverlapped->hEvent);
      lpOverlapped->hEvent = 0;
    }
    else
    {
      IocbNaked = 997;
    }
    if ( LastError || !a4 || v26.offset.idxRecord || a4->hEvent && ((__int64)a4->hEvent & 1) != 0 )
      IocbNaked = LastError;
    goto LABEL_44;
  }
  IocbNaked = 87;
LABEL_67:
  if ( !a4 )
  {
    CClfsMarshallingContext::FreeIocbNaked(this, (struct CLogIocb *)v24.ullOffset);
    v24.ullOffset = 0;
    v14 = CLFS_LSN_INVALID;
  }
  if ( IocbNaked )
    goto LABEL_78;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 328));
  v22 = 1;
  if ( this == (CClfsMarshallingContext *)-208LL || !a3 )
  {
    v10 = 0;
    goto LABEL_75;
  }
  if ( *((_QWORD *)this + 26) < a3->ullOffset )
  {
LABEL_75:
    if ( v10 )
      *((union _CLS_LSN *)this + 26) = *a3;
  }
  CClfsMarshallingContext::ReleaseFlushElements(this, a3);
  v14 = CLFS_LSN_INVALID;
LABEL_79:
  if ( IocbNaked )
  {
    if ( IocbNaked == 6640 || IocbNaked == 6643 )
    {
      v24 = v14;
      CClfsMarshallingContext::ReleaseFlushElements(this, &v24);
    }
  }
  else
  {
    *a3 = *(union _CLS_LSN *)((char *)this + 208);
  }
  if ( v22 )
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 328));
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 288));
  return IocbNaked;
}

```

## disassembly

```asm
0x18000fcdc  mov     r11, rsp
0x18000fcdf  mov     [r11+10h], rbx
0x18000fce3  mov     [r11+20h], rsi
0x18000fce7  mov     [r11+18h], r8
0x18000fceb  mov     [r11+8], rcx
0x18000fcef  push    rdi
0x18000fcf0  push    r12
0x18000fcf2  push    r13
0x18000fcf4  push    r14
0x18000fcf6  push    r15
0x18000fcf8  sub     rsp, 0A0h
0x18000fcff  mov     r15, r9
0x18000fd02  mov     r13, r8
0x18000fd05  mov     r14, rdx
0x18000fd08  mov     rdi, rcx
0x18000fd0b  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x18000fd12  mov     [r11-78h], rax
0x18000fd16  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000fd1d  mov     [r11-50h], rax
0x18000fd21  mov     [r11-60h], rax
0x18000fd25  xor     r8d, r8d
0x18000fd28  mov     [r11-70h], r8
0x18000fd2c  mov     [r11-68h], r8d
0x18000fd30  test    rdx, rdx
0x18000fd33  jz      short loc_18000FD3A
0x18000fd35  cmp     rax, [rdx]
0x18000fd38  jz      short loc_18000FD55
0x18000fd3a  or      eax, 0FFFFFFFFh
0x18000fd3d  test    r14, r14
0x18000fd40  jz      short loc_18000FD49
0x18000fd42  mov     eax, [rdx]
0x18000fd44  and     eax, 0FFFFFE00h
0x18000fd49  xor     edx, edx
0x18000fd4b  div     dword ptr [rcx+88h]
0x18000fd51  test    edx, edx
0x18000fd53  jz      short loc_18000FD78
0x18000fd55  mov     eax, 57h ; 'W'
0x18000fd5a  lea     r11, [rsp+0C8h+var_28]
0x18000fd62  mov     rbx, [r11+38h]
0x18000fd66  mov     rsi, [r11+48h]
0x18000fd6a  mov     rsp, r11
0x18000fd6d  pop     r15
0x18000fd6f  pop     r14
0x18000fd71  pop     r13
0x18000fd73  pop     r12
0x18000fd75  pop     rdi
0x18000fd76  retn
0x18000fd78  mov     [rsp+0C8h+var_58], r8
0x18000fd7d  mov     [rsp+0C8h+var_80], r8d
0x18000fd82  mov     [rsp+0C8h+var_87], r8b
0x18000fd87  mov     [rsp+0C8h+var_88], r8b
0x18000fd8c  cmp     [rcx+7Ch], r8d
0x18000fd90  jnz     short loc_18000FD96
0x18000fd92  xor     eax, eax
0x18000fd94  jmp     short loc_18000FD5A
0x18000fd96  add     rcx, 120h; CriticalSection
0x18000fd9d  call    cs:__imp_RtlEnterCriticalSection
0x18000fda4  nop     dword ptr [rax+rax+00h]
0x18000fda9  mov     r12d, 1
0x18000fdaf  mov     [rsp+0C8h+var_87], r12b
0x18000fdb4  mov     rax, [r14]
0x18000fdb7  mov     [rsp+0C8h+InBuffer], rax
0x18000fdbc  mov     rcx, qword ptr cs:CLFS_LSN_NULL
0x18000fdc3  lea     rbx, [rdi+0C8h]
0x18000fdca  cmp     rcx, rax
0x18000fdcd  jz      short loc_18000FDF1
0x18000fdcf  test    rbx, rbx
0x18000fdd2  jz      short loc_18000FDEB
0x18000fdd4  mov     eax, [r14+4]
0x18000fdd8  cmp     eax, [rbx+4]
0x18000fddb  jb      short loc_18000FDF9
0x18000fddd  jnz     short loc_18000FDE6
0x18000fddf  mov     eax, [rbx]
0x18000fde1  cmp     [r14], eax
0x18000fde4  jbe     short loc_18000FDF9
0x18000fde6  mov     al, r12b
0x18000fde9  jmp     short loc_18000FDED
0x18000fdeb  xor     al, al
0x18000fded  test    al, al
0x18000fdef  jz      short loc_18000FDF9
0x18000fdf1  mov     rax, [rbx]
0x18000fdf4  mov     [rsp+0C8h+InBuffer], rax
0x18000fdf9  test    rbx, rbx
0x18000fdfc  jz      short loc_18000FE1A
0x18000fdfe  mov     rax, [rsp+0C8h+InBuffer]
0x18000fe03  mov     rdx, rax
0x18000fe06  shr     rdx, 20h
0x18000fe0a  cmp     edx, [rbx+4]
0x18000fe0d  ja      short loc_18000FE5A
0x18000fe0f  jnz     short loc_18000FE15
0x18000fe11  cmp     eax, [rbx]
0x18000fe13  jnb     short loc_18000FE5A
0x18000fe15  mov     al, r12b
0x18000fe18  jmp     short loc_18000FE1C
0x18000fe1a  xor     al, al
0x18000fe1c  test    al, al
0x18000fe1e  jz      short loc_18000FE5A
0x18000fe20  lea     rcx, [rdi+0E8h]; this
0x18000fe27  lea     r9, [rsp+0C8h+var_60]; union _CLS_LSN *
0x18000fe2c  lea     r8, [rsp+0C8h+hDevice]; union _CLS_LSN *
0x18000fe31  lea     rdx, [rsp+0C8h+InBuffer]; union _CLS_LSN *
0x18000fe36  call    ?UpperBound@CFlushQ@@QEAAKAEBT_CLS_LSN@@AEAT2@1@Z; CFlushQ::UpperBound(_CLS_LSN const &,_CLS_LSN &,_CLS_LSN &)
0x18000fe3b  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000fe42  mov     rcx, qword ptr [rsp+0C8h+var_60]
0x18000fe47  cmp     rax, rcx
0x18000fe4a  jz      short loc_18000FE51
0x18000fe4c  mov     [rsp+0C8h+InBuffer], rcx
0x18000fe51  mov     rcx, qword ptr cs:CLFS_LSN_NULL
0x18000fe58  jmp     short loc_18000FE8E
0x18000fe5a  cmp     qword ptr [rdi+0A0h], 0
0x18000fe62  jz      short loc_18000FE87
0x18000fe64  mov     r9, r15; struct _OVERLAPPED *
0x18000fe67  xor     edx, edx; unsigned __int8
0x18000fe69  lea     r8d, [rdx+2]; unsigned int
0x18000fe6d  mov     rcx, rdi; this
0x18000fe70  call    ?AppendWriteBlockToFlushQueue@CClfsMarshallingContext@@AEAAKEKPEAU_OVERLAPPED@@@Z; CClfsMarshallingContext::AppendWriteBlockToFlushQueue(uchar,ulong,_OVERLAPPED *)
0x18000fe75  mov     ebx, eax
0x18000fe77  mov     [rsp+0C8h+var_80], eax
0x18000fe7b  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000fe82  jmp     loc_180010155
0x18000fe87  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000fe8e  test    rbx, rbx
0x18000fe91  jz      short loc_18000FEAB
0x18000fe93  mov     edx, dword ptr [rsp+0C8h+InBuffer+4]
0x18000fe97  cmp     edx, [rbx+4]
0x18000fe9a  jb      short loc_18000FEB1
0x18000fe9c  jnz     short loc_18000FEA6
0x18000fe9e  mov     edx, [rbx]
0x18000fea0  cmp     dword ptr [rsp+0C8h+InBuffer], edx
0x18000fea4  jbe     short loc_18000FEB1
0x18000fea6  mov     dl, r12b
0x18000fea9  jmp     short loc_18000FEAD
0x18000feab  xor     dl, dl
0x18000fead  test    dl, dl
0x18000feaf  jnz     short loc_18000FEB6
0x18000feb1  cmp     rcx, [r14]
0x18000feb4  jnz     short loc_18000FEBB
0x18000feb6  mov     [rsp+0C8h+InBuffer], rcx
0x18000febb  test    r15, r15
0x18000febe  jnz     short loc_18000FEF2
0x18000fec0  lea     rdx, [rsp+0C8h+var_70]; struct CLogIocb **
0x18000fec5  mov     rcx, rdi; this
0x18000fec8  call    ?AllocateIocbNaked@CClfsMarshallingContext@@AEAAKPEAPEAVCLogIocb@@@Z; CClfsMarshallingContext::AllocateIocbNaked(CLogIocb * *)
0x18000fecd  mov     ebx, eax
0x18000fecf  mov     [rsp+0C8h+var_80], eax
0x18000fed3  test    eax, eax
0x18000fed5  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000fedc  jnz     loc_180010155
0x18000fee2  mov     rdx, qword ptr [rsp+0C8h+var_70]
0x18000fee7  mov     rdx, [rdx+38h]
0x18000feeb  mov     [rsp+0C8h+var_58], rdx
0x18000fef0  jmp     short loc_18000FEF7
0x18000fef2  mov     rdx, [rsp+0C8h+var_58]
0x18000fef7  mov     ecx, [rdi+9Ch]
0x18000fefd  and     ecx, 20h
0x18000ff00  mov     dword ptr [rsp+0C8h+var_60], ecx
0x18000ff04  mov     rcx, [rdi+30h]
0x18000ff08  mov     [rsp+0C8h+hDevice], rcx
0x18000ff0d  mov     [rsp+0C8h+Overlapped.Internal], 0
0x18000ff19  mov     [rsp+0C8h+Overlapped.InternalHigh], 0
0x18000ff25  mov     qword ptr [rsp+0C8h+Overlapped.10h], 0
0x18000ff31  mov     [rsp+0C8h+Overlapped.hEvent], 0
0x18000ff3d  mov     r14, r15
0x18000ff40  xor     esi, esi
0x18000ff42  mov     [rsp+0C8h+var_84], esi
0x18000ff46  test    r13, r13
0x18000ff49  jz      loc_1800100C3
0x18000ff4f  mov     [rsp+0C8h+BytesReturned], esi
0x18000ff53  mov     [r13+0], rax
0x18000ff57  test    rdx, rdx
0x18000ff5a  jz      short loc_18000FF7C
0x18000ff5c  mov     [rsp+0C8h+Overlapped.hEvent], rdx
0x18000ff64  lea     r14, [rsp+0C8h+Overlapped]
0x18000ff6c  mov     rax, rdx
0x18000ff6f  or      rax, r12
0x18000ff72  mov     [rsp+0C8h+Overlapped.hEvent], rax
0x18000ff7a  jmp     short loc_18000FFCB
0x18000ff7c  test    r15, r15
0x18000ff7f  jnz     short loc_18000FFCB
0x18000ff81  lea     r14, [rsp+0C8h+Overlapped]
0x18000ff89  xor     r9d, r9d; lpName
0x18000ff8c  xor     r8d, r8d; bInitialState
0x18000ff8f  xor     edx, edx; bManualReset
0x18000ff91  xor     ecx, ecx; lpEventAttributes
0x18000ff93  call    cs:__imp_CreateEventA
0x18000ff9a  nop     dword ptr [rax+rax+00h]
0x18000ff9f  mov     [rsp+0C8h+Overlapped.hEvent], rax
0x18000ffa7  test    rax, rax
0x18000ffaa  jnz     short loc_18000FFBB
0x18000ffac  lea     ebx, [rax+8]
0x18000ffaf  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000ffb6  jmp     loc_1800100C8
0x18000ffbb  or      rax, r12
0x18000ffbe  mov     [rsp+0C8h+Overlapped.hEvent], rax
0x18000ffc6  mov     rcx, [rsp+0C8h+hDevice]; hDevice
0x18000ffcb  mov     [rsp+0C8h+lpOverlapped], r14; lpOverlapped
0x18000ffd0  lea     rax, [rsp+0C8h+BytesReturned]
0x18000ffd5  mov     [rsp+0C8h+lpBytesReturned], rax; lpBytesReturned
0x18000ffda  mov     ebx, 8
0x18000ffdf  mov     [rsp+0C8h+nOutBufferSize], ebx; nOutBufferSize
0x18000ffe3  mov     [rsp+0C8h+lpOutBuffer], r13; lpOutBuffer
0x18000ffe8  mov     r9d, ebx; nInBufferSize
0x18000ffeb  lea     r8, [rsp+0C8h+InBuffer]; lpInBuffer
0x18000fff0  mov     edx, 8007282Ch; dwIoControlCode
0x18000fff5  call    cs:__imp_DeviceIoControl
0x18000fffc  nop     dword ptr [rax+rax+00h]
0x180010001  test    eax, eax
0x180010003  jnz     short loc_180010017
0x180010005  call    cs:__imp_GetLastError
0x18001000c  nop     dword ptr [rax+rax+00h]
0x180010011  mov     esi, eax
0x180010013  mov     [rsp+0C8h+var_84], eax
0x180010017  cmp     [rsp+0C8h+var_58], 0
0x18001001d  jnz     short loc_18001002B
0x18001001f  test    r15, r15
0x180010022  jz      short loc_18001002B
0x180010024  mov     ebx, 3E5h
0x180010029  jmp     short loc_180010097
0x18001002b  mov     ebx, 3E5h
0x180010030  cmp     esi, ebx
0x180010032  jnz     short loc_18001006D
0x180010034  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180010037  mov     rcx, [r14+18h]; hHandle
0x18001003b  call    cs:__imp_WaitForSingleObject
0x180010042  nop     dword ptr [rax+rax+00h]
0x180010047  mov     [rsp+0C8h+var_84], eax
0x18001004b  test    eax, eax
0x18001004d  jz      short loc_180010058
0x18001004f  lea     esi, [rbx+78h]
0x180010052  mov     [rsp+0C8h+var_84], esi
0x180010056  jmp     short loc_18001006D
0x180010058  mov     ecx, [r14]; Status
0x18001005b  call    cs:__imp_RtlNtStatusToDosError
0x180010062  nop     dword ptr [rax+rax+00h]
0x180010067  mov     esi, eax
0x180010069  mov     [rsp+0C8h+var_84], eax
0x18001006d  and     qword ptr [r14+18h], 0FFFFFFFFFFFFFFFEh
0x180010072  mov     rcx, [r14+18h]; hObject
0x180010076  cmp     [rsp+0C8h+var_58], 0
0x18001007c  jnz     short loc_18001008F
0x18001007e  test    r15, r15
0x180010081  jnz     short loc_18001008F
0x180010083  call    cs:__imp_CloseHandle
0x18001008a  nop     dword ptr [rax+rax+00h]
0x18001008f  mov     qword ptr [r14+18h], 0
0x180010097  test    esi, esi
0x180010099  jnz     short loc_1800100BC
0x18001009b  test    r15, r15
0x18001009e  jz      short loc_1800100BC
0x1800100a0  cmp     dword ptr [rsp+0C8h+var_60], esi
0x1800100a4  jnz     short loc_1800100BC
0x1800100a6  cmp     qword ptr [r15+18h], 0
0x1800100ab  jz      short loc_1800100B3
0x1800100ad  test    [r15+18h], r12b
0x1800100b1  jnz     short loc_1800100BC
0x1800100b3  mov     [rsp+0C8h+var_84], ebx
0x1800100b7  jmp     loc_18000FFAF
0x1800100bc  mov     ebx, esi
0x1800100be  jmp     loc_18000FFAF
0x1800100c3  mov     ebx, 57h ; 'W'
0x1800100c8  mov     [rsp+0C8h+var_80], ebx
0x1800100cc  test    r15, r15
0x1800100cf  jnz     short loc_1800100EA
0x1800100d1  mov     rdx, qword ptr [rsp+0C8h+var_70]; struct CLogIocb *
0x1800100d6  mov     rcx, rdi; this
0x1800100d9  call    ?FreeIocbNaked@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z; CClfsMarshallingContext::FreeIocbNaked(CLogIocb *)
0x1800100de  mov     qword ptr [rsp+0C8h+var_70], r15
0x1800100e3  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1800100ea  test    ebx, ebx
0x1800100ec  jnz     short loc_180010155
0x1800100ee  lea     rcx, [rdi+148h]; CriticalSection
0x1800100f5  call    cs:__imp_RtlEnterCriticalSection
0x1800100fc  nop     dword ptr [rax+rax+00h]
0x180010101  mov     sil, r12b
0x180010104  mov     [rsp+0C8h+var_88], r12b
0x180010109  lea     rcx, [rdi+0D0h]
0x180010110  xor     r8d, r8d
0x180010113  test    rcx, rcx
0x180010116  jz      short loc_180010132
0x180010118  test    r13, r13
0x18001011b  jz      short loc_180010132
0x18001011d  mov     eax, [rcx+4]
0x180010120  cmp     eax, [r13+4]
0x180010124  ja      short loc_180010141
0x180010126  jnz     short loc_180010135
0x180010128  mov     eax, [r13+0]
0x18001012c  cmp     [rcx], eax
0x18001012e  jnb     short loc_180010141
0x180010130  jmp     short loc_180010135
0x180010132  mov     r12b, r8b
0x180010135  test    r12b, r12b
0x180010138  jz      short loc_180010141
0x18001013a  mov     rax, [r13+0]
0x18001013e  mov     [rcx], rax
0x180010141  mov     rdx, r13; union _CLS_LSN *
0x180010144  mov     rcx, rdi; this
0x180010147  call    ?ReleaseFlushElements@CClfsMarshallingContext@@AEAAXAEAT_CLS_LSN@@@Z; CClfsMarshallingContext::ReleaseFlushElements(_CLS_LSN &)
0x18001014c  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180010153  jmp     short loc_18001015A
0x180010155  mov     sil, [rsp+0C8h+var_88]
  ... truncated ...
```
