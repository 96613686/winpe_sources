# CClfsArchiveContext::ReadMetadata(ulong,ulong,uchar *,ulong &)

- ea: `0x180012410`
- end: `0x1800124e7`
- name: `?ReadMetadata@CClfsArchiveContext@@QEAAKKKPEAEAEAK@Z`
- size: `215`
- prototype: `unsigned int(CClfsArchiveContext *__hidden this, unsigned int, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000c3c0`

## callees

- `0x180012410`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800124c3`
- `ntdll!RtlLeaveCriticalSection` at `0x180015a9e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800124c3`
- `ntdll!RtlLeaveCriticalSection` at `0x180015a9e`
- `ntdll!RtlEnterCriticalSection` at `0x180012444`
- `ntdll!RtlEnterCriticalSection` at `0x180012444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001248b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001248b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001247b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001247b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800124a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800124a7`

## pseudocode

```c
__int64 __fastcall CClfsArchiveContext::ReadMetadata(
        CClfsArchiveContext *this,
        int a2,
        DWORD a3,
        unsigned __int8 *a4,
        LPDWORD a5)
{
  DWORD LastError; // ebx
  DWORD *lpBytesReturned; // r14
  int InBuffer; // [rsp+78h] [rbp+10h] BYREF

  InBuffer = a2;
  LastError = 0;
  lpBytesReturned = a5;
  *a5 = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 24));
  if ( !DeviceIoControl(
          *((HANDLE *)this + 1),
          0x80076856,
          &InBuffer,
          4u,
          a4,
          a3,
          lpBytesReturned,
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
0x180012410  mov     [rsp+arg_10], rbx
0x180012415  mov     [rsp+InBuffer], edx
0x180012419  mov     [rsp+arg_0], rcx
0x18001241e  push    rsi
0x18001241f  push    rdi
0x180012420  push    r12
0x180012422  push    r14
0x180012424  push    r15
0x180012426  sub     rsp, 40h
0x18001242a  mov     r15, r9
0x18001242d  mov     r12d, r8d
0x180012430  mov     rdi, rcx
0x180012433  xor     ebx, ebx
0x180012435  mov     r14, [rsp+68h+arg_20]
0x18001243d  mov     [r14], ebx
0x180012440  add     rcx, 18h; CriticalSection
0x180012444  call    cs:__imp_RtlEnterCriticalSection
0x18001244b  nop     dword ptr [rax+rax+00h]
0x180012450  nop
0x180012451  lea     rax, [rdi+40h]
0x180012455  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18001245a  mov     [rsp+68h+lpBytesReturned], r14; lpBytesReturned
0x18001245f  mov     [rsp+68h+nOutBufferSize], r12d; nOutBufferSize
0x180012464  mov     [rsp+68h+lpOutBuffer], r15; lpOutBuffer
0x180012469  lea     r9d, [rbx+4]; nInBufferSize
0x18001246d  lea     r8, [rsp+68h+InBuffer]; lpInBuffer
0x180012472  mov     edx, 80076856h; dwIoControlCode
0x180012477  mov     rcx, [rdi+8]; hDevice
0x18001247b  call    cs:__imp_DeviceIoControl
0x180012482  nop     dword ptr [rax+rax+00h]
0x180012487  test    eax, eax
0x180012489  jnz     short loc_1800124BF
0x18001248b  call    cs:__imp_GetLastError
0x180012492  nop     dword ptr [rax+rax+00h]
0x180012497  mov     ebx, eax
0x180012499  cmp     eax, 3E5h
0x18001249e  jnz     short loc_1800124BF
0x1800124a0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800124a3  mov     rcx, [rdi+58h]; hHandle
0x1800124a7  call    cs:__imp_WaitForSingleObject
0x1800124ae  nop     dword ptr [rax+rax+00h]
0x1800124b3  mov     ebx, eax
0x1800124b5  mov     eax, 54Fh
0x1800124ba  test    ebx, ebx
0x1800124bc  cmovnz  ebx, eax
0x1800124bf  lea     rcx, [rdi+18h]; CriticalSection
0x1800124c3  call    cs:__imp_RtlLeaveCriticalSection
0x1800124ca  nop     dword ptr [rax+rax+00h]
0x1800124cf  mov     eax, ebx
0x1800124d1  mov     rbx, [rsp+68h+arg_10]
0x1800124d9  add     rsp, 40h
0x1800124dd  pop     r15
0x1800124df  pop     r14
0x1800124e1  pop     r12
0x1800124e3  pop     rdi
0x1800124e4  pop     rsi
0x1800124e5  retn
0x180015a8d  push    rbp
0x180015a8f  sub     rsp, 40h
0x180015a93  mov     rbp, rdx
0x180015a96  mov     rcx, [rbp+70h]
0x180015a9a  add     rcx, 18h; CriticalSection
0x180015a9e  call    cs:__imp_RtlLeaveCriticalSection
0x180015aa5  nop     dword ptr [rax+rax+00h]
0x180015aaa  nop
0x180015aab  add     rsp, 40h
0x180015aaf  pop     rbp
0x180015ab0  retn
```
