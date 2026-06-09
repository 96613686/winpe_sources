# NfsUpCallPasswdGroupContextCreate

- ea: `0x140010be4`
- end: `0x140010c92`
- name: `NfsUpCallPasswdGroupContextCreate`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000664c`

## callees

- `0x140010be4`
- `0x140010c98`
- `0x140011614`
- `0x140011968`
- `0x14001830e`

## import_xrefs

- `KERNEL32!InitializeSRWLock` at `0x140010c23`
- `KERNEL32!InitializeSRWLock` at `0x140010c23`
- `KERNEL32!GetLastError` at `0x140010c60`
- `KERNEL32!GetLastError` at `0x140010c60`
- `KERNEL32!CreateThread` at `0x140010c50`
- `KERNEL32!CreateThread` at `0x140010c50`
- `ntdll!RtlAllocateHeap` at `0x140010c04`
- `ntdll!RtlAllocateHeap` at `0x140010c04`

## pseudocode

```c
__int64 NfsUpCallPasswdGroupContextCreate()
{
  DWORD LastError; // edi
  RTL_SRWLOCK *Heap; // rax
  RTL_SRWLOCK *v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // rcx

  LastError = 0;
  Heap = (RTL_SRWLOCK *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x48u);
  v2 = Heap;
  if ( Heap
    && (memset_0(Heap, 0, 0x48u),
        InitializeSRWLock(v2),
        NfsUpCallpPasswdGroupRefreshPasswdIfNeeded(v3, (__int64)v2),
        NfsUpCallpPasswdGroupRefreshGroupIfNeeded(v4, (__int64)v2),
        v2[6].Ptr = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)NfsUpCallpPasswdGroupWatchEtcDir, v2, 0, 0),
        v2 == (RTL_SRWLOCK *)-1LL)
    && (LastError = GetLastError()) != 0 )
  {
    NfsUpCallPasswdGroupContextDestroy(-1);
  }
  else
  {
    v2[5].Ptr = 0;
    g_PasswdGroupContext = v2;
  }
  return LastError;
}

```

## disassembly

```asm
0x140010be4  mov     [rsp+arg_0], rbx
0x140010be9  push    rdi
0x140010bea  sub     rsp, 30h
0x140010bee  mov     rcx, gs:60h
0x140010bf7  xor     edi, edi
0x140010bf9  mov     rcx, [rcx+30h]; HeapHandle
0x140010bfd  lea     edx, [rdi+8]; Flags
0x140010c00  lea     r8d, [rdi+48h]; Size
0x140010c04  call    cs:__imp_RtlAllocateHeap
0x140010c0a  mov     rbx, rax
0x140010c0d  test    rax, rax
0x140010c10  jz      short loc_140010C76
0x140010c12  xor     edx, edx; Val
0x140010c14  lea     r8d, [rdi+48h]; Size
0x140010c18  mov     rcx, rax; void *
0x140010c1b  call    memset_0
0x140010c20  mov     rcx, rbx; SRWLock
0x140010c23  call    cs:__imp_InitializeSRWLock
0x140010c29  mov     rdx, rbx
0x140010c2c  call    NfsUpCallpPasswdGroupRefreshPasswdIfNeeded
0x140010c31  mov     rdx, rbx
0x140010c34  call    NfsUpCallpPasswdGroupRefreshGroupIfNeeded
0x140010c39  mov     r9, rbx; lpParameter
0x140010c3c  mov     [rsp+38h+lpThreadId], rdi; lpThreadId
0x140010c41  lea     r8, NfsUpCallpPasswdGroupWatchEtcDir; lpStartAddress
0x140010c48  mov     [rsp+38h+dwCreationFlags], edi; dwCreationFlags
0x140010c4c  xor     edx, edx; dwStackSize
0x140010c4e  xor     ecx, ecx; lpThreadAttributes
0x140010c50  call    cs:__imp_CreateThread
0x140010c56  mov     [rbx+30h], rax
0x140010c5a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140010c5e  jnz     short loc_140010C76
0x140010c60  call    cs:__imp_GetLastError
0x140010c66  mov     edi, eax
0x140010c68  test    eax, eax
0x140010c6a  jz      short loc_140010C76
0x140010c6c  or      rcx, rbx
0x140010c6f  call    NfsUpCallPasswdGroupContextDestroy
0x140010c74  jmp     short loc_140010C85
0x140010c76  mov     qword ptr [rbx+28h], 0
0x140010c7e  mov     cs:g_PasswdGroupContext, rbx
0x140010c85  mov     rbx, [rsp+38h+arg_0]
0x140010c8a  mov     eax, edi
0x140010c8c  add     rsp, 30h
0x140010c90  pop     rdi
0x140010c91  retn
```
