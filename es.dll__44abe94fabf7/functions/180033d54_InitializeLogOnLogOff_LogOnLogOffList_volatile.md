# InitializeLogOnLogOff(LogOnLogOffList volatile * *)

- ea: `0x180033d54`
- end: `0x180033e25`
- name: `?InitializeLogOnLogOff@@YAJPEAPECULogOnLogOffList@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(volatile struct LogOnLogOffList **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033a9c`

## callees

- `0x180033a74`
- `0x180033d54`
- `0x180034090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180033db9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180033db9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180033dd7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180033dd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033de4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033de4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033d75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033d75`

## pseudocode

```c
__int64 __fastcall InitializeLogOnLogOff(volatile struct LogOnLogOffList **a1)
{
  LogOnLogOffList *v1; // rax
  unsigned int v2; // ebx
  _QWORD *v4; // rax
  signed __int64 v5; // rdi
  volatile struct LogOnLogOffList *v6; // rax
  signed int LastError; // eax

  v1 = g_pLogOnLogOff;
  v2 = 0;
  if ( g_pLogOnLogOff )
  {
    *a1 = g_pLogOnLogOff;
    _InterlockedIncrement((volatile signed __int32 *)v1 + 20);
    return v2;
  }
  v4 = CoTaskMemAlloc(0x58u);
  v5 = (signed __int64)v4;
  if ( !v4 )
    return (unsigned int)-2147024882;
  *v4 = 0;
  v4[1] = 17;
  v4[2] = 0;
  v4[4] = v4 + 3;
  v4[3] = v4 + 3;
  Map<unsigned short const *,unsigned short const *,LogOnLogOffList::HashCaseInsentitiveWSTR,LogOnLogOffList::CNonFailFastingAllocator>::allocAssocIfNecessary((__int64)v4);
  *(_DWORD *)(v5 + 80) = 1;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v5 + 40), 0x3E8u) )
  {
    v6 = (volatile struct LogOnLogOffList *)_InterlockedCompareExchange64(
                                              (volatile signed __int64 *)&g_pLogOnLogOff,
                                              v5,
                                              0);
    *a1 = v6;
    if ( !v6 )
    {
      *a1 = (volatile struct LogOnLogOffList *)v5;
      return v2;
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)(v5 + 40));
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( (v2 & 0x80000000) != 0 )
      goto LABEL_11;
  }
  if ( *a1 != (volatile struct LogOnLogOffList *)v5 )
LABEL_11:
    LogOnLogOffList::`scalar deleting destructor'((LogOnLogOffList *)v5);
  return v2;
}

```

## disassembly

```asm
0x180033d54  push    rbx
0x180033d56  push    rbp
0x180033d57  push    rsi
0x180033d58  push    rdi
0x180033d59  sub     rsp, 28h
0x180033d5d  mov     rax, cs:?g_pLogOnLogOff@@3PECULogOnLogOffList@@EC; LogOnLogOffList volatile * volatile g_pLogOnLogOff
0x180033d64  xor     ebx, ebx
0x180033d66  mov     rsi, rcx
0x180033d69  test    rax, rax
0x180033d6c  jnz     loc_180033E13
0x180033d72  lea     ecx, [rbx+58h]; cb
0x180033d75  call    cs:__imp_CoTaskMemAlloc
0x180033d7b  mov     rdi, rax
0x180033d7e  test    rax, rax
0x180033d81  jz      loc_180033E0C
0x180033d87  lea     rcx, [rax+18h]
0x180033d8b  mov     [rax], rbx
0x180033d8e  mov     qword ptr [rax+8], 11h
0x180033d96  mov     [rax+10h], rbx
0x180033d9a  mov     [rcx+8], rcx
0x180033d9e  mov     [rcx], rcx
0x180033da1  mov     rcx, rax
0x180033da4  call    ?allocAssocIfNecessary@?$Map@PEBGPEBGVHashCaseInsentitiveWSTR@LogOnLogOffList@@VCNonFailFastingAllocator@2@@@AEAAJXZ; Map<ushort const *,ushort const *,LogOnLogOffList::HashCaseInsentitiveWSTR,LogOnLogOffList::CNonFailFastingAllocator>::allocAssocIfNecessary(void)
0x180033da9  mov     edx, 3E8h; dwSpinCount
0x180033dae  mov     dword ptr [rdi+50h], 1
0x180033db5  lea     rcx, [rdi+28h]; lpCriticalSection
0x180033db9  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180033dbf  test    eax, eax
0x180033dc1  jz      short loc_180033DE4
0x180033dc3  xor     eax, eax
0x180033dc5  lock cmpxchg cs:?g_pLogOnLogOff@@3PECULogOnLogOffList@@EC, rdi; LogOnLogOffList volatile * volatile g_pLogOnLogOff
0x180033dce  mov     [rsi], rax
0x180033dd1  jz      short loc_180033DDF
0x180033dd3  lea     rcx, [rdi+28h]; lpCriticalSection
0x180033dd7  call    cs:__imp_DeleteCriticalSection
0x180033ddd  jmp     short loc_180033DFD
0x180033ddf  mov     [rsi], rdi
0x180033de2  jmp     short loc_180033E1A
0x180033de4  call    cs:__imp_GetLastError
0x180033dea  mov     ebx, eax
0x180033dec  test    eax, eax
0x180033dee  jle     short loc_180033DF9
0x180033df0  movzx   ebx, ax
0x180033df3  or      ebx, 80070000h
0x180033df9  test    ebx, ebx
0x180033dfb  js      short loc_180033E02
0x180033dfd  cmp     [rsi], rdi
0x180033e00  jz      short loc_180033E1A
0x180033e02  mov     rcx, rdi; this
0x180033e05  call    ??_GLogOnLogOffList@@QEAAPEAXI@Z; LogOnLogOffList::`scalar deleting destructor'(uint)
0x180033e0a  jmp     short loc_180033E1A
0x180033e0c  mov     ebx, 8007000Eh
0x180033e11  jmp     short loc_180033E1A
0x180033e13  mov     [rcx], rax
0x180033e16  lock inc dword ptr [rax+50h]
0x180033e1a  mov     eax, ebx
0x180033e1c  add     rsp, 28h
0x180033e20  pop     rdi
0x180033e21  pop     rsi
0x180033e22  pop     rbp
0x180033e23  pop     rbx
0x180033e24  retn
```
