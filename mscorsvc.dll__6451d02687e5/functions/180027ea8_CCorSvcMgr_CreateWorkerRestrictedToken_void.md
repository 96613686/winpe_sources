# CCorSvcMgr::CreateWorkerRestrictedToken(void)

- ea: `0x180027ea8`
- end: `0x1800280bc`
- name: `?CreateWorkerRestrictedToken@CCorSvcMgr@@CAPEAXXZ`
- size: `532`
- prototype: `__int64 __fastcall(__int64, struct NGENService::ServiceWorkerPrivileges *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, service_task`

## callers

- `0x180008680`

## callees

- `0x18001b800`
- `0x180027ea8`
- `0x1800280bc`
- `0x1800304ec`
- `0x1800351e8`
- `0x18003dc50`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180027fc9`
- `KERNEL32!LoadLibraryExW` at `0x180027fc9`
- `KERNEL32!GetProcAddress` at `0x180027fde`
- `KERNEL32!GetProcAddress` at `0x180027fde`
- `KERNEL32!HeapFree` at `0x180027efd`
- `KERNEL32!HeapFree` at `0x180028090`
- `KERNEL32!HeapFree` at `0x180027efd`
- `KERNEL32!HeapFree` at `0x180028090`
- `KERNEL32!GetProcessHeap` at `0x180027ee8`
- `KERNEL32!GetProcessHeap` at `0x18002807b`
- `KERNEL32!GetProcessHeap` at `0x180027ee8`
- `KERNEL32!GetProcessHeap` at `0x18002807b`

## string_xrefs

- `0x180027fc2`: `advapi32.dll`
- `0x180027fd4`: `LookupPrivilegeValueW`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CCorSvcMgr::CreateWorkerRestrictedToken(__int64 a1, struct NGENService::ServiceWorkerPrivileges *a2)
{
  __int64 v2; // r15
  void *v3; // rbx
  HANDLE ProcessHeap; // rax
  char *v6; // rbx
  unsigned int v7; // ebp
  _WORD *i; // rax
  __int64 v9; // rcx
  struct _TOKEN_PRIVILEGES *v10; // rsi
  char *v11; // r12
  unsigned int j; // r14d
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  __int64 v15; // rax
  void *WorkerRestrictedToken; // rdi
  HANDLE v17; // rax
  LPVOID lpMem; // [rsp+70h] [rbp+8h] BYREF
  LUID_AND_ATTRIBUTES *v19; // [rsp+78h] [rbp+10h]

  v2 = 0;
  lpMem = 0;
  if ( (int)NGENService::GetServiceWorkerPrivileges((NGENService *)&lpMem, a2) < 0 )
  {
    v3 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v3);
      lpMem = 0;
    }
    return -1;
  }
  v6 = (char *)lpMem;
  if ( !lpMem )
    return -1;
  v7 = 0;
  for ( i = lpMem; *i; i += v9 + 1 )
  {
    ++v7;
    v9 = -1;
    do
      ++v9;
    while ( i[v9] );
  }
  v10 = (struct _TOKEN_PRIVILEGES *)operator new(12LL * v7 + 4);
  v10->PrivilegeCount = 0;
  v11 = v6;
  for ( j = 0; j < v7; ++v2 )
  {
    v19 = &v10->Privileges[j];
    ProcAddress = (FARPROC)qword_18006FF88;
    if ( !qword_18006FF88
      && (bLookupPrivilegeValueProbed
       || ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
         ? (ProcAddress = (FARPROC)qword_18006FF88)
         : (FARPROC)(ProcAddress = GetProcAddress(Library, "LookupPrivilegeValueW"),
                     qword_18006FF88 = (__int64)ProcAddress),
           bLookupPrivilegeValueProbed = 1,
           !ProcAddress))
      || !((unsigned int (__fastcall *)(_QWORD, char *, LUID_AND_ATTRIBUTES *))ProcAddress)(0, v11, v19) )
    {
      ThrowLastError();
    }
    v10->Privileges[v2].Attributes = 0;
    ++v10->PrivilegeCount;
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)&v11[2 * v15] );
    v11 += 2 * v15 + 2;
    ++j;
  }
  WorkerRestrictedToken = CCorSvcMgr::CreateWorkerRestrictedToken(v10);
  if ( v10 )
    operator delete(v10);
  v17 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
  if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
  {
    v17 = GetProcessHeap();
    `ClrFreeInProcessHeap'::`2'::ProcessHeap = v17;
  }
  HeapFree(v17, 0, v6);
  lpMem = 0;
  return (__int64)WorkerRestrictedToken;
}

```

## disassembly

```asm
0x180027ea8  mov     [rsp+arg_10], rbx
0x180027ead  push    rbp
0x180027eae  push    rsi
0x180027eaf  push    rdi
0x180027eb0  push    r12
0x180027eb2  push    r13
0x180027eb4  push    r14
0x180027eb6  push    r15
0x180027eb8  sub     rsp, 30h
0x180027ebc  xor     r15d, r15d
0x180027ebf  mov     [rsp+68h+lpMem], r15
0x180027ec4  lea     rcx, [rsp+68h+lpMem]; this
0x180027ec9  call    ?GetServiceWorkerPrivileges@NGENService@@YAJPEAUServiceWorkerPrivileges@1@@Z; NGENService::GetServiceWorkerPrivileges(NGENService::ServiceWorkerPrivileges *)
0x180027ece  test    eax, eax
0x180027ed0  jns     short loc_180027F11
0x180027ed2  mov     rbx, [rsp+68h+lpMem]
0x180027ed7  test    rbx, rbx
0x180027eda  jz      short loc_180027F08
0x180027edc  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180027ee3  test    rax, rax
0x180027ee6  jnz     short loc_180027EF5
0x180027ee8  call    cs:__imp_GetProcessHeap
0x180027eee  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180027ef5  mov     r8, rbx; lpMem
0x180027ef8  xor     edx, edx; dwFlags
0x180027efa  mov     rcx, rax; hHeap
0x180027efd  call    cs:__imp_HeapFree
0x180027f03  mov     [rsp+68h+lpMem], r15
0x180027f08  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027f0c  jmp     loc_18002809E
0x180027f11  mov     rbx, [rsp+68h+lpMem]
0x180027f16  test    rbx, rbx
0x180027f19  jnz     short loc_180027F1D
0x180027f1b  jmp     short loc_180027F08
0x180027f1d  mov     ebp, r15d
0x180027f20  mov     rax, rbx
0x180027f23  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180027f27  lea     r14d, [rdi+2]
0x180027f2b  cmp     [rbx], r15w
0x180027f2f  jz      short loc_180027F4F
0x180027f31  add     ebp, r14d
0x180027f34  mov     rcx, rdi
0x180027f37  inc     rcx
0x180027f3a  cmp     [rax+rcx*2], r15w
0x180027f3f  jnz     short loc_180027F37
0x180027f41  lea     rax, [rax+rcx*2]
0x180027f45  add     rax, 2
0x180027f49  cmp     [rax], r15w
0x180027f4d  jnz     short loc_180027F31
0x180027f4f  mov     eax, ebp
0x180027f51  lea     rcx, [rax+rax*2]
0x180027f55  lea     rcx, ds:4[rcx*4]; dwBytes
0x180027f5d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027f62  mov     rsi, rax
0x180027f65  mov     [rsp+68h+var_48], rax
0x180027f6a  mov     [rsp+68h+var_40], r15d
0x180027f6f  mov     r13d, r15d
0x180027f72  test    rax, rax
0x180027f75  cmovnz  r13d, r14d
0x180027f79  mov     [rsp+68h+var_40], r13d
0x180027f7e  mov     [rax], r15d
0x180027f81  mov     r12, rbx
0x180027f84  mov     r14d, r15d
0x180027f87  test    ebp, ebp
0x180027f89  jz      loc_18002804D
0x180027f8f  xor     edx, edx
0x180027f91  mov     eax, r14d
0x180027f94  lea     rax, [rax+rax*2]
0x180027f98  lea     rax, [rax+1]
0x180027f9c  lea     rax, [rsi+rax*4]
0x180027fa0  mov     [rsp+68h+arg_8], rax
0x180027fa5  mov     rax, cs:qword_18006FF88
0x180027fac  test    rax, rax
0x180027faf  jnz     short loc_180028004
0x180027fb1  cmp     cs:?bLookupPrivilegeValueProbed@@3_NA, dl; bool bLookupPrivilegeValueProbed
0x180027fb7  jnz     loc_1800280B6
0x180027fbd  xor     r8d, r8d; dwFlags
0x180027fc0  xor     edx, edx; hFile
0x180027fc2  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x180027fc9  call    cs:__imp_LoadLibraryExW
0x180027fcf  test    rax, rax
0x180027fd2  jz      short loc_180027FED
0x180027fd4  lea     rdx, aLookupprivileg; "LookupPrivilegeValueW"
0x180027fdb  mov     rcx, rax; hModule
0x180027fde  call    cs:__imp_GetProcAddress
0x180027fe4  mov     cs:qword_18006FF88, rax
0x180027feb  jmp     short loc_180027FF4
0x180027fed  mov     rax, cs:qword_18006FF88
0x180027ff4  mov     cs:?bLookupPrivilegeValueProbed@@3_NA, 1; bool bLookupPrivilegeValueProbed
0x180027ffb  test    rax, rax
0x180027ffe  jz      loc_1800280B6
0x180028004  mov     r8, [rsp+68h+arg_8]
0x180028009  mov     rdx, r12
0x18002800c  xor     ecx, ecx
0x18002800e  call    cs:__guard_dispatch_icall_fptr
0x180028014  xor     edx, edx
0x180028016  test    eax, eax
0x180028018  jz      loc_1800280B6
0x18002801e  mov     [r15+rsi+0Ch], edx
0x180028023  inc     dword ptr [rsi]
0x180028025  mov     rax, rdi
0x180028028  inc     rax
0x18002802b  cmp     [r12+rax*2], dx
0x180028030  jnz     short loc_180028028
0x180028032  lea     r12, [r12+rax*2]
0x180028036  add     r12, 2
0x18002803a  inc     r14d
0x18002803d  add     r15, 0Ch
0x180028041  cmp     r14d, ebp
0x180028044  jb      loc_180027F91
0x18002804a  xor     r15d, r15d
0x18002804d  mov     rcx, rsi; struct _TOKEN_PRIVILEGES *
0x180028050  call    ?CreateWorkerRestrictedToken@CCorSvcMgr@@CAPEAXPEAU_TOKEN_PRIVILEGES@@@Z; CCorSvcMgr::CreateWorkerRestrictedToken(_TOKEN_PRIVILEGES *)
0x180028055  mov     rdi, rax
0x180028058  test    r13d, r13d
0x18002805b  jz      short loc_18002806F
0x18002805d  mov     edx, 10h; unsigned __int64
0x180028062  mov     rcx, rsi; void *
0x180028065  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002806a  mov     [rsp+68h+var_40], r15d
0x18002806f  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180028076  test    rax, rax
0x180028079  jnz     short loc_180028088
0x18002807b  call    cs:__imp_GetProcessHeap
0x180028081  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180028088  mov     r8, rbx; lpMem
0x18002808b  xor     edx, edx; dwFlags
0x18002808d  mov     rcx, rax; hHeap
0x180028090  call    cs:__imp_HeapFree
0x180028096  mov     [rsp+68h+lpMem], r15
0x18002809b  mov     rax, rdi
0x18002809e  mov     rbx, [rsp+68h+arg_10]
0x1800280a6  add     rsp, 30h
0x1800280aa  pop     r15
0x1800280ac  pop     r14
0x1800280ae  pop     r13
0x1800280b0  pop     r12
0x1800280b2  pop     rdi
0x1800280b3  pop     rsi
0x1800280b4  pop     rbp
0x1800280b5  retn
0x1800280b6  call    ?ThrowLastError@@YAXXZ; ThrowLastError(void)
```
