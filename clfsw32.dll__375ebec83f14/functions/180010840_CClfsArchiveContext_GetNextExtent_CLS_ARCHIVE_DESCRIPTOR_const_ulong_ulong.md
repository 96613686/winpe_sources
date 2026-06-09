# CClfsArchiveContext::GetNextExtent(_CLS_ARCHIVE_DESCRIPTOR * const,ulong,ulong &)

- ea: `0x180010840`
- end: `0x180010917`
- name: `?GetNextExtent@CClfsArchiveContext@@QEAAKQEAU_CLS_ARCHIVE_DESCRIPTOR@@KAEAK@Z`
- size: `215`
- prototype: `unsigned int(CClfsArchiveContext *__hidden this, struct _CLS_ARCHIVE_DESCRIPTOR *const, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000bbb0`

## callees

- `0x180010840`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800108f4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800159a1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800108f4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800159a1`
- `ntdll!RtlEnterCriticalSection` at `0x18001086e`
- `ntdll!RtlEnterCriticalSection` at `0x18001086e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108bc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800108ac`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800108ac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800108d8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800108d8`

## pseudocode

```c
__int64 __fastcall CClfsArchiveContext::GetNextExtent(
        CClfsArchiveContext *this,
        struct _CLS_ARCHIVE_DESCRIPTOR *const a2,
        int a3,
        unsigned int *a4)
{
  DWORD LastError; // ebx
  int InBuffer; // [rsp+70h] [rbp+18h] BYREF

  InBuffer = a3;
  LastError = 0;
  *a4 = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 24));
  if ( !DeviceIoControl(
          *((HANDLE *)this + 1),
          0x80076846,
          &InBuffer,
          4u,
          a2,
          592 * InBuffer,
          a4,
          (LPOVERLAPPED)this + 2) )
  {
    LastError = GetLastError();
    if ( LastError == 997 )
    {
      LastError = WaitForSingleObject(*((HANDLE *)this + 11), 0xFFFFFFFF);
      if ( LastError )
        LastError = 1359;
    }
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 24));
  return LastError;
}

```

## disassembly

```asm
0x180010840  mov     rax, rsp
0x180010843  mov     [rax+10h], rbx
0x180010847  mov     [rax+20h], rsi
0x18001084b  mov     [rax+18h], r8d
0x18001084f  mov     [rax+8], rcx
0x180010853  push    rdi
0x180010854  push    r14
0x180010856  push    r15
0x180010858  sub     rsp, 40h
0x18001085c  mov     r14, r9
0x18001085f  mov     r15, rdx
0x180010862  mov     rdi, rcx
0x180010865  xor     ebx, ebx
0x180010867  mov     [r9], ebx
0x18001086a  add     rcx, 18h; CriticalSection
0x18001086e  call    cs:__imp_RtlEnterCriticalSection
0x180010875  nop     dword ptr [rax+rax+00h]
0x18001087a  nop
0x18001087b  lea     rax, [rdi+40h]
0x18001087f  imul    edx, [rsp+58h+InBuffer], 250h
0x180010887  mov     [rsp+58h+lpOverlapped], rax; lpOverlapped
0x18001088c  mov     [rsp+58h+lpBytesReturned], r14; lpBytesReturned
0x180010891  mov     [rsp+58h+nOutBufferSize], edx; nOutBufferSize
0x180010895  mov     [rsp+58h+lpOutBuffer], r15; lpOutBuffer
0x18001089a  lea     r9d, [rbx+4]; nInBufferSize
0x18001089e  lea     r8, [rsp+58h+InBuffer]; lpInBuffer
0x1800108a3  mov     edx, 80076846h; dwIoControlCode
0x1800108a8  mov     rcx, [rdi+8]; hDevice
0x1800108ac  call    cs:__imp_DeviceIoControl
0x1800108b3  nop     dword ptr [rax+rax+00h]
0x1800108b8  test    eax, eax
0x1800108ba  jnz     short loc_1800108F0
0x1800108bc  call    cs:__imp_GetLastError
0x1800108c3  nop     dword ptr [rax+rax+00h]
0x1800108c8  mov     ebx, eax
0x1800108ca  cmp     eax, 3E5h
0x1800108cf  jnz     short loc_1800108F0
0x1800108d1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800108d4  mov     rcx, [rdi+58h]; hHandle
0x1800108d8  call    cs:__imp_WaitForSingleObject
0x1800108df  nop     dword ptr [rax+rax+00h]
0x1800108e4  mov     ebx, eax
0x1800108e6  mov     eax, 54Fh
0x1800108eb  test    ebx, ebx
0x1800108ed  cmovnz  ebx, eax
0x1800108f0  lea     rcx, [rdi+18h]; CriticalSection
0x1800108f4  call    cs:__imp_RtlLeaveCriticalSection
0x1800108fb  nop     dword ptr [rax+rax+00h]
0x180010900  mov     eax, ebx
0x180010902  mov     rbx, [rsp+58h+arg_8]
0x180010907  mov     rsi, [rsp+58h+arg_18]
0x18001090c  add     rsp, 40h
0x180010910  pop     r15
0x180010912  pop     r14
0x180010914  pop     rdi
0x180010915  retn
0x180015990  push    rbp
0x180015992  sub     rsp, 40h
0x180015996  mov     rbp, rdx
0x180015999  mov     rcx, [rbp+60h]
0x18001599d  add     rcx, 18h; CriticalSection
0x1800159a1  call    cs:__imp_RtlLeaveCriticalSection
0x1800159a8  nop     dword ptr [rax+rax+00h]
0x1800159ad  nop
0x1800159ae  add     rsp, 40h
0x1800159b2  pop     rbp
0x1800159b3  retn
```
