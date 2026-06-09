# __delayLoadHelper2

- ea: `0x18000e720`
- end: `0x18000e913`
- name: `__delayLoadHelper2`
- size: `499`
- prototype: `FARPROC __fastcall(unsigned int *, FARPROC *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000210d`

## callees

- `0x180001fd6`
- `0x1800020fb`
- `0x180002107`
- `0x18000e720`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000e8d5`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000e8d5`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18000e873`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18000e873`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000e8f9`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000e82f`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000e8f9`

## string_xrefs

- `0x18000e77b`: `api-ms-win-core-delayload-l1-1-1.dll`
- `0x18000e78f`: `KERNEL32.DLL`
- `0x18000e801`: `ResolveDelayLoadsFromDll`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(unsigned int *a1, FARPROC *a2)
{
  __int64 v2; // rbp
  __int64 v3; // r15
  __int64 v5; // r12
  HMODULE v7; // rbx
  __int64 ModuleHandleW_0; // rdi
  const CHAR *v9; // rsi
  __int64 v10; // rdx
  const CHAR *v11; // rdi
  FARPROC result; // rax
  HMODULE Library; // rax
  signed __int64 v14; // rbp
  struct DelayLoadInfo v15[2]; // [rsp+40h] [rbp-98h] BYREF
  volatile signed __int64 *v16; // [rsp+E0h] [rbp+8h]

  v2 = a1[1];
  v3 = a1[3];
  v5 = a1[4];
  v16 = (volatile signed __int64 *)((char *)&_ImageBase + a1[2]);
  v7 = (HMODULE)*v16;
  if ( DloadKernel32 != 1 )
  {
    if ( DloadKernel32 )
      return (FARPROC)((__int64 (__fastcall *)(__int16 *, unsigned int *, __int64, __int64 (__fastcall *)(_QWORD, _QWORD), FARPROC *, _DWORD))DloadResolveDelayLoadedAPI)(
                        &_ImageBase,
                        a1,
                        _pfnDefaultDliFailureHook2,
                        DelayLoadFailureHook,
                        a2,
                        0);
    ModuleHandleW_0 = (__int64)GetModuleHandleW_0(L"api-ms-win-core-delayload-l1-1-1.dll");
    if ( (ModuleHandleW_0 || (ModuleHandleW_0 = (__int64)GetModuleHandleW_0(L"KERNEL32.DLL")) != 0)
      && (DloadResolveDelayLoadedAPI = (__int64)GetProcAddress_0((HMODULE)ModuleHandleW_0, "ResolveDelayLoadedAPI")) != 0 )
    {
      DloadResolveDelayLoadsFromDll = (__int64)GetProcAddress_0((HMODULE)ModuleHandleW_0, "ResolveDelayLoadsFromDll");
      if ( !DloadResolveDelayLoadsFromDll )
        ModuleHandleW_0 = 1;
      DloadKernel32 = ModuleHandleW_0;
      if ( ModuleHandleW_0 != 1 )
        return (FARPROC)((__int64 (__fastcall *)(__int16 *, unsigned int *, __int64, __int64 (__fastcall *)(_QWORD, _QWORD), FARPROC *, _DWORD))DloadResolveDelayLoadedAPI)(
                          &_ImageBase,
                          a1,
                          _pfnDefaultDliFailureHook2,
                          DelayLoadFailureHook,
                          a2,
                          0);
    }
    else
    {
      DloadKernel32 = 1;
    }
  }
  v9 = (char *)&_ImageBase + v2;
  v10 = v5 + 8LL * (unsigned int)(((char *)a2 - v3 - (char *)&_ImageBase) >> 3);
  if ( *(__int64 *)((char *)&_ImageBase + v10) < 0 )
    v11 = (const CHAR *)*(unsigned __int16 *)((char *)&_ImageBase + v10);
  else
    v11 = (char *)&word_180000002 + *(unsigned int *)((char *)&_ImageBase + v10);
  if ( !v7 )
  {
    Library = LoadLibraryExA((LPCSTR)&_ImageBase + v2, 0, 0);
    v7 = Library;
    if ( !Library )
      return (FARPROC)DelayLoadFailureHook(v9, v11);
    v14 = _InterlockedCompareExchange64(v16, (signed __int64)Library, 0);
    if ( v14 )
    {
      FreeLibrary(Library);
      v7 = (HMODULE)v14;
    }
    else
    {
      memset_0(v15, 0, 0x48u);
      v15[0].cb = 72;
      v15[0].szDll = v9;
      v15[0].hmodCur = v7;
      if ( _pfnDliNotifyHook2 )
        _pfnDliNotifyHook2(5u, v15);
    }
  }
  result = GetProcAddress_0(v7, v11);
  if ( result )
  {
    *a2 = result;
    return result;
  }
  return (FARPROC)DelayLoadFailureHook(v9, v11);
}

```

## disassembly

```asm
0x18000e720  push    rbx
0x18000e722  push    rbp
0x18000e723  push    rsi
0x18000e724  push    rdi
0x18000e725  push    r12
0x18000e727  push    r13
0x18000e729  push    r14
0x18000e72b  push    r15
0x18000e72d  sub     rsp, 98h
0x18000e734  mov     eax, [rcx+8]
0x18000e737  lea     r13, __ImageBase
0x18000e73e  mov     ebp, [rcx+4]
0x18000e741  add     rax, r13
0x18000e744  mov     r15d, [rcx+0Ch]
0x18000e748  mov     r14, rdx
0x18000e74b  mov     r12d, [rcx+10h]
0x18000e74f  mov     rsi, rcx
0x18000e752  mov     [rsp+0D8h+arg_0], rax
0x18000e75a  mov     rax, [rsp+0D8h+arg_0]
0x18000e762  mov     rbx, [rax]
0x18000e765  mov     rax, cs:DloadKernel32
0x18000e76c  cmp     rax, 1
0x18000e770  jz      short loc_18000E7AF
0x18000e772  test    rax, rax
0x18000e775  jnz     loc_18000E82F
0x18000e77b  lea     rcx, aApiMsWinCoreDe_1; "api-ms-win-core-delayload-l1-1-1.dll"
0x18000e782  call    GetModuleHandleW_0
0x18000e787  mov     rdi, rax
0x18000e78a  test    rax, rax
0x18000e78d  jnz     short loc_18000E7E6
0x18000e78f  lea     rcx, aKernel32Dll_0; "KERNEL32.DLL"
0x18000e796  call    GetModuleHandleW_0
0x18000e79b  mov     rdi, rax
0x18000e79e  test    rax, rax
0x18000e7a1  jnz     short loc_18000E7E6
0x18000e7a3  mov     eax, 1
0x18000e7a8  mov     cs:DloadKernel32, rax
0x18000e7af  mov     rcx, r14
0x18000e7b2  mov     rsi, rbp
0x18000e7b5  sub     rcx, r15
0x18000e7b8  add     rsi, r13
0x18000e7bb  sub     rcx, r13
0x18000e7be  sar     rcx, 3
0x18000e7c2  mov     ecx, ecx
0x18000e7c4  lea     rdx, [r12+rcx*8]
0x18000e7c8  cmp     qword ptr [rdx+r13], 0
0x18000e7cd  jl      loc_18000E861
0x18000e7d3  mov     edi, [rdx+r13]
0x18000e7d7  lea     rax, word_180000002
0x18000e7de  add     rdi, rax
0x18000e7e1  jmp     loc_18000E866
0x18000e7e6  lea     rdx, aResolvedelaylo; "ResolveDelayLoadedAPI"
0x18000e7ed  mov     rcx, rdi; hModule
0x18000e7f0  call    GetProcAddress_0
0x18000e7f5  mov     cs:DloadResolveDelayLoadedAPI, rax
0x18000e7fc  test    rax, rax
0x18000e7ff  jz      short loc_18000E7A3
0x18000e801  lea     rdx, aResolvedelaylo_0; "ResolveDelayLoadsFromDll"
0x18000e808  mov     rcx, rdi; hModule
0x18000e80b  call    GetProcAddress_0
0x18000e810  test    rax, rax
0x18000e813  mov     cs:DloadResolveDelayLoadsFromDll, rax
0x18000e81a  mov     eax, 1
0x18000e81f  cmovz   rdi, rax
0x18000e823  mov     cs:DloadKernel32, rdi
0x18000e82a  cmp     rdi, rax
0x18000e82d  jz      short loc_18000E7AF
0x18000e82f  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000e836  mov     rdx, rsi
0x18000e839  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000e840  mov     rcx, r13
0x18000e843  mov     rax, cs:DloadResolveDelayLoadedAPI
0x18000e84a  mov     [rsp+0D8h+var_B0], 0
0x18000e852  mov     [rsp+0D8h+var_B8], r14
0x18000e857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e85c  jmp     loc_18000E8FF
0x18000e861  movzx   edi, word ptr [rdx+r13]
0x18000e866  test    rbx, rbx
0x18000e869  jnz     short loc_18000E8DE
0x18000e86b  xor     r8d, r8d; dwFlags
0x18000e86e  xor     edx, edx; hFile
0x18000e870  mov     rcx, rsi; lpLibFileName
0x18000e873  call    cs:__imp_LoadLibraryExA
0x18000e879  mov     rbx, rax
0x18000e87c  test    rax, rax
0x18000e87f  jz      short loc_18000E8F3
0x18000e881  mov     rcx, [rsp+0D8h+arg_0]
0x18000e889  xor     eax, eax
0x18000e88b  lock cmpxchg [rcx], rbx
0x18000e890  mov     rbp, rax
0x18000e893  jnz     short loc_18000E8D2
0x18000e895  mov     ebp, 48h ; 'H'
0x18000e89a  lea     rcx, [rsp+0D8h+var_98]; void *
0x18000e89f  mov     r8d, ebp; Size
0x18000e8a2  xor     edx, edx; Val
0x18000e8a4  call    memset_0
0x18000e8a9  mov     rax, cs:__pfnDliNotifyHook2
0x18000e8b0  mov     [rsp+0D8h+var_98], ebp
0x18000e8b4  mov     [rsp+0D8h+var_80], rsi
0x18000e8b9  mov     [rsp+0D8h+var_68], rbx
0x18000e8be  test    rax, rax
0x18000e8c1  jz      short loc_18000E8DE
0x18000e8c3  lea     rdx, [rsp+0D8h+var_98]
0x18000e8c8  lea     ecx, [rbp-43h]
0x18000e8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8d0  jmp     short loc_18000E8DE
0x18000e8d2  mov     rcx, rbx; hLibModule
0x18000e8d5  call    cs:__imp_FreeLibrary
0x18000e8db  mov     rbx, rbp
0x18000e8de  mov     rdx, rdi; lpProcName
0x18000e8e1  mov     rcx, rbx; hModule
0x18000e8e4  call    GetProcAddress_0
0x18000e8e9  test    rax, rax
0x18000e8ec  jz      short loc_18000E8F3
0x18000e8ee  mov     [r14], rax
0x18000e8f1  jmp     short loc_18000E8FF
0x18000e8f3  mov     rdx, rdi
0x18000e8f6  mov     rcx, rsi
0x18000e8f9  call    cs:__imp_DelayLoadFailureHook
0x18000e8ff  add     rsp, 98h
0x18000e906  pop     r15
0x18000e908  pop     r14
0x18000e90a  pop     r13
0x18000e90c  pop     r12
0x18000e90e  pop     rdi
0x18000e90f  pop     rsi
0x18000e910  pop     rbp
0x18000e911  pop     rbx
0x18000e912  retn
```
