# PsmpFindOrCreateUserContext

- ea: `0x18000b3d8`
- end: `0x18000b4cf`
- name: `PsmpFindOrCreateUserContext`
- size: `247`
- prototype: `__int64 __fastcall(__int64, unsigned int, void *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800043d8`
- `0x18000abf0`
- `0x18000cb7c`

## callees

- `0x18000b3d8`
- `0x18000d010`
- `0x180014e68`
- `0x18002e17c`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000b42f`
- `ntdll!RtlLengthSid` at `0x18000b42f`
- `ntdll!RtlInitializeSRWLock` at `0x18000b49b`
- `ntdll!RtlInitializeSRWLock` at `0x18000b49b`
- `ntdll!RtlAllocateHeap` at `0x18000b44e`
- `ntdll!RtlAllocateHeap` at `0x18000b44e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b3f4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b3f4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b414`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b414`

## pseudocode

```c
__int64 __fastcall PsmpFindOrCreateUserContext(__int64 a1, unsigned int a2, void *a3)
{
  __int64 UserContext; // rbx
  ULONG v8; // r13d
  _DWORD *Heap; // rax
  _QWORD *v10; // rdi
  _DWORD *v11; // rbx
  _QWORD *v12; // rdx

  RtlAcquireSRWLockExclusive(a1 + 8);
  UserContext = PsmpFindUserContext(a1, a2, a3);
  if ( !UserContext )
  {
    v8 = RtlLengthSid(a3);
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v8 + 3144LL);
    v10 = Heap;
    if ( Heap )
    {
      v11 = Heap + 786;
      Heap[1] = a2;
      *Heap = 1;
      memcpy_0(Heap + 786, a3, v8);
      v10[5] = v11;
      v10[7] = a1;
      PsmpInitializeHashTable(v10 + 8);
      v10[4] = v10 + 3;
      v10[3] = v10 + 3;
      RtlInitializeSRWLock(v10 + 6);
      v12 = *(_QWORD **)(a1 + 32);
      if ( *v12 != a1 + 24 )
        __fastfail(3u);
      UserContext = (__int64)v10;
      v10[1] = a1 + 24;
      v10[2] = v12;
      *v12 = v10 + 1;
      *(_QWORD *)(a1 + 32) = v10 + 1;
    }
  }
  RtlReleaseSRWLockExclusive(a1 + 8);
  return UserContext;
}

```

## disassembly

```asm
0x18000b3d8  push    rbx
0x18000b3da  push    rbp
0x18000b3db  push    rsi
0x18000b3dc  push    rdi
0x18000b3dd  push    r13
0x18000b3df  push    r14
0x18000b3e1  push    r15
0x18000b3e3  sub     rsp, 20h
0x18000b3e7  mov     rbp, rcx
0x18000b3ea  mov     r14, r8
0x18000b3ed  add     rcx, 8
0x18000b3f1  mov     r15d, edx
0x18000b3f4  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000b3fa  mov     r8, r14
0x18000b3fd  mov     edx, r15d
0x18000b400  mov     rcx, rbp
0x18000b403  call    PsmpFindUserContext
0x18000b408  mov     rbx, rax
0x18000b40b  test    rax, rax
0x18000b40e  jz      short loc_18000B42C
0x18000b410  lea     rcx, [rbp+8]
0x18000b414  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000b41a  mov     rax, rbx
0x18000b41d  add     rsp, 20h
0x18000b421  pop     r15
0x18000b423  pop     r14
0x18000b425  pop     r13
0x18000b427  pop     rdi
0x18000b428  pop     rsi
0x18000b429  pop     rbp
0x18000b42a  pop     rbx
0x18000b42b  retn
0x18000b42c  mov     rcx, r14; Sid
0x18000b42f  call    cs:__imp_RtlLengthSid
0x18000b435  mov     rcx, gs:60h
0x18000b43e  xor     edx, edx; Flags
0x18000b440  mov     r13d, eax
0x18000b443  mov     rcx, [rcx+30h]; HeapHandle
0x18000b447  lea     r8, [r13+0C48h]; Size
0x18000b44e  call    cs:__imp_RtlAllocateHeap
0x18000b454  mov     rdi, rax
0x18000b457  test    rax, rax
0x18000b45a  jz      short loc_18000B410
0x18000b45c  lea     rbx, [rax+0C48h]
0x18000b463  mov     [rax+4], r15d
0x18000b467  mov     rcx, rbx; void *
0x18000b46a  mov     dword ptr [rax], 1
0x18000b470  mov     r8d, r13d; Size
0x18000b473  mov     rdx, r14; Src
0x18000b476  call    memcpy_0
0x18000b47b  lea     rcx, [rdi+40h]
0x18000b47f  mov     [rdi+28h], rbx
0x18000b483  mov     [rdi+38h], rbp
0x18000b487  call    PsmpInitializeHashTable
0x18000b48c  lea     rax, [rdi+18h]
0x18000b490  lea     rcx, [rdi+30h]
0x18000b494  mov     [rax+8], rax
0x18000b498  mov     [rax], rax
0x18000b49b  call    cs:__imp_RtlInitializeSRWLock
0x18000b4a1  lea     rcx, [rbp+18h]
0x18000b4a5  mov     rdx, [rcx+8]
0x18000b4a9  cmp     [rdx], rcx
0x18000b4ac  jnz     short loc_18000B4C8
0x18000b4ae  lea     rax, [rdi+8]
0x18000b4b2  mov     rbx, rdi
0x18000b4b5  mov     [rax], rcx
0x18000b4b8  mov     [rax+8], rdx
0x18000b4bc  mov     [rdx], rax
0x18000b4bf  mov     [rcx+8], rax
0x18000b4c3  jmp     loc_18000B410
0x18000b4c8  mov     ecx, 3
0x18000b4cd  int     29h; Win8: RtlFailFast(ecx)
```
