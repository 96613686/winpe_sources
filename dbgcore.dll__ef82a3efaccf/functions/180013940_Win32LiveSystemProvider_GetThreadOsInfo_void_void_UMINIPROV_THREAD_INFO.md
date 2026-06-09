# Win32LiveSystemProvider::GetThreadOsInfo(void *,void *,_UMINIPROV_THREAD_INFO *)

- ea: `0x180013940`
- end: `0x1800139bd`
- name: `?GetThreadOsInfo@Win32LiveSystemProvider@@UEAAJPEAX0PEAU_UMINIPROV_THREAD_INFO@@@Z`
- size: `125`
- prototype: `int(Win32LiveSystemProvider *__hidden this, void *, void *, struct _UMINIPROV_THREAD_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180024f60`

## callees

- `0x180013940`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001396b`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001396b`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x18001395b`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x18001395b`

## pseudocode

```c
__int64 __fastcall Win32LiveSystemProvider::GetThreadOsInfo(
        Win32LiveSystemProvider *this,
        void *a2,
        void *a3,
        struct _UMINIPROV_THREAD_INFO *a4)
{
  DWORD PriorityClass; // eax
  int ThreadPriority; // eax
  void (__fastcall *v9)(void *, char *, char *, char *, char *); // rax

  PriorityClass = GetPriorityClass(a2);
  if ( PriorityClass )
    *((_DWORD *)a4 + 1) = PriorityClass;
  ThreadPriority = GetThreadPriority(a3);
  if ( ThreadPriority != 0x7FFFFFFF )
    *((_DWORD *)a4 + 2) = ThreadPriority;
  v9 = (void (__fastcall *)(void *, char *, char *, char *, char *))*((_QWORD *)this + 47);
  if ( !v9 )
    return 2147500033LL;
  v9(a3, (char *)a4 + 16, (char *)a4 + 24, (char *)a4 + 32, (char *)a4 + 40);
  return 0;
}

```

## disassembly

```asm
0x180013940  mov     [rsp+arg_0], rbx
0x180013945  mov     [rsp+arg_8], rsi
0x18001394a  push    rdi
0x18001394b  sub     rsp, 30h
0x18001394f  mov     rsi, rcx
0x180013952  mov     rbx, r9
0x180013955  mov     rcx, rdx; hProcess
0x180013958  mov     rdi, r8
0x18001395b  call    cs:__imp_GetPriorityClass
0x180013961  test    eax, eax
0x180013963  jz      short loc_180013968
0x180013965  mov     [rbx+4], eax
0x180013968  mov     rcx, rdi; hThread
0x18001396b  call    cs:__imp_GetThreadPriority
0x180013971  cmp     eax, 7FFFFFFFh
0x180013976  jz      short loc_18001397B
0x180013978  mov     [rbx+8], eax
0x18001397b  mov     rax, [rsi+178h]
0x180013982  test    rax, rax
0x180013985  jnz     short loc_18001398E
0x180013987  mov     eax, 80004001h
0x18001398c  jmp     short loc_1800139AD
0x18001398e  lea     rcx, [rbx+28h]
0x180013992  mov     [rsp+38h+var_18], rcx
0x180013997  lea     r9, [rbx+20h]
0x18001399b  mov     rcx, rdi
0x18001399e  lea     r8, [rbx+18h]
0x1800139a2  lea     rdx, [rbx+10h]
0x1800139a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139ab  xor     eax, eax
0x1800139ad  mov     rbx, [rsp+38h+arg_0]
0x1800139b2  mov     rsi, [rsp+38h+arg_8]
0x1800139b7  add     rsp, 30h
0x1800139bb  pop     rdi
0x1800139bc  retn
```
