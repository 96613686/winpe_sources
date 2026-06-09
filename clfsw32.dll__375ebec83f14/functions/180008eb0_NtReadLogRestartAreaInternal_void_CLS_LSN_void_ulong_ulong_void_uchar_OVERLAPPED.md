# NtReadLogRestartAreaInternal(void *,_CLS_LSN *,void *,ulong,ulong *,void *,uchar,_OVERLAPPED *)

- ea: `0x180008eb0`
- end: `0x180009087`
- name: `?NtReadLogRestartAreaInternal@@YAKPEAXPEAT_CLS_LSN@@0KPEAK0EPEAU_OVERLAPPED@@@Z`
- size: `471`
- prototype: `unsigned int(void *, union _CLS_LSN *, void *, unsigned int, unsigned int *, void *, unsigned __int8, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012e18`

## callees

- `0x180008eb0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180008ffe`
- `ntdll!RtlNtStatusToDosError` at `0x180008ffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009024`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009024`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008fa6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008fa6`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008f54`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008f54`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008fe5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008fe5`

## pseudocode

```c
__int64 __fastcall NtReadLogRestartAreaInternal(
        void *a1,
        union _CLS_LSN *a2,
        char *a3,
        unsigned int a4,
        unsigned int *lpBytesReturned,
        unsigned __int64 a6,
        unsigned __int8 a7,
        struct _OVERLAPPED *a8)
{
  DWORD LastError; // esi
  __int64 nOutBufferSize; // r14
  __int64 result; // rax
  struct _OVERLAPPED *lpOverlapped; // rbx
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-48h] BYREF
  HANDLE hDevice; // [rsp+90h] [rbp+8h]

  hDevice = a1;
  LastError = 0;
  nOutBufferSize = a4;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( !a2 || !lpBytesReturned )
    return 87;
  if ( a4 && (!a3 || a4 < 0x28) )
    return 1784;
  if ( a6 )
  {
    lpOverlapped = &Overlapped;
    Overlapped.hEvent = (HANDLE)(a6 | 1);
  }
  else if ( a8 )
  {
    lpOverlapped = a8;
  }
  else
  {
    result = (__int64)CreateEventA(0, 0, 0, 0);
    if ( !result )
      return result;
    a1 = hDevice;
    lpOverlapped = &Overlapped;
    Overlapped.hEvent = (HANDLE)(result | 1);
  }
  if ( !DeviceIoControl(a1, 0x80076822, a2, 8u, a3, nOutBufferSize, lpBytesReturned, lpOverlapped) )
    LastError = GetLastError();
  if ( a6 || !a8 )
  {
    if ( LastError == 997 )
    {
      if ( WaitForSingleObject(lpOverlapped->hEvent, 0xFFFFFFFF) )
        LastError = 1117;
      else
        LastError = RtlNtStatusToDosError(lpOverlapped->Internal);
    }
    lpOverlapped->hEvent = (HANDLE)((unsigned __int64)lpOverlapped->hEvent & ~1uLL);
    if ( !a6 && !a8 )
      CloseHandle(lpOverlapped->hEvent);
    lpOverlapped->hEvent = 0;
  }
  if ( LastError )
    return LastError;
  *a2 = *(union _CLS_LSN *)&a3[nOutBufferSize - 32];
  if ( !a8 || !a7 || a8->hEvent && ((__int64)a8->hEvent & 1) != 0 )
    return LastError;
  else
    return 997;
}

```

## disassembly

```asm
0x180008eb0  mov     rax, rsp
0x180008eb3  mov     [rax+10h], rbx
0x180008eb7  mov     [rax+18h], rsi
0x180008ebb  mov     [rax+8], rcx
0x180008ebf  push    rdi
0x180008ec0  push    r12
0x180008ec2  push    r13
0x180008ec4  push    r14
0x180008ec6  push    r15
0x180008ec8  sub     rsp, 60h
0x180008ecc  xor     esi, esi
0x180008ece  mov     r14d, r9d
0x180008ed1  mov     [rax-48h], rsi
0x180008ed5  mov     r12, r8
0x180008ed8  mov     [rax-40h], rsi
0x180008edc  mov     r13, rdx
0x180008edf  mov     [rax-38h], rsi
0x180008ee3  mov     [rax-30h], rsi
0x180008ee7  test    rdx, rdx
0x180008eea  jz      loc_180009067
0x180008ef0  mov     r15, [rsp+88h+arg_20]
0x180008ef8  test    r15, r15
0x180008efb  jz      loc_180009067
0x180008f01  test    r9d, r9d
0x180008f04  jz      short loc_180008F1B
0x180008f06  test    r8, r8
0x180008f09  jz      short loc_180008F11
0x180008f0b  cmp     r14d, 28h ; '('
0x180008f0f  jnb     short loc_180008F1B
0x180008f11  mov     eax, 6F8h
0x180008f16  jmp     loc_18000906C
0x180008f1b  mov     rdi, [rsp+88h+arg_38]
0x180008f23  cmp     [rsp+88h+arg_28], rsi
0x180008f2b  jz      short loc_180008F45
0x180008f2d  mov     rax, [rsp+88h+arg_28]
0x180008f35  lea     rbx, [rsp+88h+Overlapped]
0x180008f3a  or      rax, 1
0x180008f3e  mov     [rsp+88h+Overlapped.hEvent], rax
0x180008f43  jmp     short loc_180008F84
0x180008f45  test    rdi, rdi
0x180008f48  jnz     short loc_180008F81
0x180008f4a  xor     r9d, r9d; lpName
0x180008f4d  xor     r8d, r8d; bInitialState
0x180008f50  xor     edx, edx; bManualReset
0x180008f52  xor     ecx, ecx; lpEventAttributes
0x180008f54  call    cs:__imp_CreateEventA
0x180008f5b  nop     dword ptr [rax+rax+00h]
0x180008f60  test    rax, rax
0x180008f63  jz      loc_18000906C
0x180008f69  mov     rcx, [rsp+88h+hDevice]; hDevice
0x180008f71  lea     rbx, [rsp+88h+Overlapped]
0x180008f76  or      rax, 1
0x180008f7a  mov     [rsp+88h+Overlapped.hEvent], rax
0x180008f7f  jmp     short loc_180008F84
0x180008f81  mov     rbx, rdi
0x180008f84  mov     [rsp+88h+lpOverlapped], rbx; lpOverlapped
0x180008f89  mov     r9d, 8; nInBufferSize
0x180008f8f  mov     [rsp+88h+lpBytesReturned], r15; lpBytesReturned
0x180008f94  mov     r8, r13; lpInBuffer
0x180008f97  mov     [rsp+88h+nOutBufferSize], r14d; nOutBufferSize
0x180008f9c  mov     edx, 80076822h; dwIoControlCode
0x180008fa1  mov     [rsp+88h+lpOutBuffer], r12; lpOutBuffer
0x180008fa6  call    cs:__imp_DeviceIoControl
0x180008fad  nop     dword ptr [rax+rax+00h]
0x180008fb2  xor     r15d, r15d
0x180008fb5  test    eax, eax
0x180008fb7  jnz     short loc_180008FC7
0x180008fb9  call    cs:__imp_GetLastError
0x180008fc0  nop     dword ptr [rax+rax+00h]
0x180008fc5  mov     esi, eax
0x180008fc7  cmp     [rsp+88h+arg_28], r15
0x180008fcf  jnz     short loc_180008FD6
0x180008fd1  test    rdi, rdi
0x180008fd4  jnz     short loc_180009034
0x180008fd6  cmp     esi, 3E5h
0x180008fdc  jnz     short loc_18000900C
0x180008fde  mov     rcx, [rbx+18h]; hHandle
0x180008fe2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008fe5  call    cs:__imp_WaitForSingleObject
0x180008fec  nop     dword ptr [rax+rax+00h]
0x180008ff1  test    eax, eax
0x180008ff3  jz      short loc_180008FFC
0x180008ff5  mov     esi, 45Dh
0x180008ffa  jmp     short loc_18000900C
0x180008ffc  mov     ecx, [rbx]; Status
0x180008ffe  call    cs:__imp_RtlNtStatusToDosError
0x180009005  nop     dword ptr [rax+rax+00h]
0x18000900a  mov     esi, eax
0x18000900c  and     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFEh
0x180009011  cmp     [rsp+88h+arg_28], r15
0x180009019  jnz     short loc_180009030
0x18000901b  test    rdi, rdi
0x18000901e  jnz     short loc_180009030
0x180009020  mov     rcx, [rbx+18h]; hObject
0x180009024  call    cs:__imp_CloseHandle
0x18000902b  nop     dword ptr [rax+rax+00h]
0x180009030  mov     [rbx+18h], r15
0x180009034  test    esi, esi
0x180009036  jnz     short loc_180009063
0x180009038  mov     rcx, [r14+r12-20h]
0x18000903d  mov     [r13+0], rcx
0x180009041  test    rdi, rdi
0x180009044  jz      short loc_180009063
0x180009046  cmp     [rsp+88h+arg_30], r15b
0x18000904e  jz      short loc_180009063
0x180009050  cmp     [rdi+18h], r15
0x180009054  jz      short loc_18000905C
0x180009056  test    byte ptr [rdi+18h], 1
0x18000905a  jnz     short loc_180009063
0x18000905c  mov     eax, 3E5h
0x180009061  jmp     short loc_18000906C
0x180009063  mov     eax, esi
0x180009065  jmp     short loc_18000906C
0x180009067  mov     eax, 57h ; 'W'
0x18000906c  lea     r11, [rsp+88h+var_28]
0x180009071  mov     rbx, [r11+38h]
0x180009075  mov     rsi, [r11+40h]
0x180009079  mov     rsp, r11
0x18000907c  pop     r15
0x18000907e  pop     r14
0x180009080  pop     r13
0x180009082  pop     r12
0x180009084  pop     rdi
0x180009085  retn
```
