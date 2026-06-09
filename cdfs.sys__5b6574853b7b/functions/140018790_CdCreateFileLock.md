# CdCreateFileLock

- ea: `0x140018790`
- end: `0x1400188b5`
- name: `CdCreateFileLock`
- size: `293`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400156c0`
- `0x140015850`
- `0x140015a50`
- `0x140015bf0`
- `0x140015db0`

## callees

- `0x140001114`
- `0x140018790`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1400187d4`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400187d4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001881b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140018862`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001881b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140018862`
- `ntoskrnl!FsRtlAllocateFileLock` at `0x140018832`
- `ntoskrnl!FsRtlAllocateFileLock` at `0x140018832`

## pseudocode

```c
char __fastcall CdCreateFileLock(__int64 a1, __int64 a2, char a3)
{
  struct _KTHREAD *CurrentThread; // rdi
  __int64 v4; // rsi
  bool v8; // zf
  int v9; // ecx
  struct _FAST_MUTEX *v10; // rcx
  char v12; // di
  PFILE_LOCK FileLock; // rax
  PFILE_LOCK v14; // rbp
  struct _FAST_MUTEX *v15; // rcx

  CurrentThread = KeGetCurrentThread();
  v4 = a2 + 200;
  if ( CurrentThread != *(struct _KTHREAD **)(a2 + 184) )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)v4 + 136LL));
    *(_QWORD *)(a2 + 184) = CurrentThread;
  }
  v8 = *(_QWORD *)(a2 + 472) == 0;
  v9 = *(_DWORD *)(a2 + 192);
  *(_DWORD *)(a2 + 192) = v9 + 1;
  if ( v8 )
  {
    v12 = 1;
    FileLock = FsRtlAllocateFileLock(0, 0);
    v8 = (*(_DWORD *)(a2 + 192))-- == 1;
    v14 = FileLock;
    *(_QWORD *)(a2 + 472) = FileLock;
    if ( v8 )
    {
      v15 = (struct _FAST_MUTEX *)(*(_QWORD *)v4 + 136LL);
      *(_QWORD *)(a2 + 184) = 0;
      ExReleaseFastMutex(v15);
    }
    if ( !v14 )
    {
      if ( a3 )
        CdRaiseStatusEx(a1, 3221225626LL, 0, 1638400, 1562);
      return 0;
    }
    return v12;
  }
  else
  {
    *(_DWORD *)(a2 + 192) = v9;
    if ( !v9 )
    {
      v10 = (struct _FAST_MUTEX *)(*(_QWORD *)v4 + 136LL);
      *(_QWORD *)(a2 + 184) = 0;
      ExReleaseFastMutex(v10);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x140018790  mov     [rsp+arg_0], rbx
0x140018795  mov     [rsp+arg_10], rbp
0x14001879a  push    rsi
0x14001879b  push    rdi
0x14001879c  push    r13
0x14001879e  push    r14
0x1400187a0  push    r15
0x1400187a2  sub     rsp, 30h
0x1400187a6  mov     rdi, gs:188h
0x1400187af  lea     rsi, [rdx+0C8h]
0x1400187b6  mov     r14b, r8b
0x1400187b9  mov     rbx, rdx
0x1400187bc  mov     r15, rcx
0x1400187bf  mov     r13d, 88h
0x1400187c5  cmp     rdi, [rdx+0B8h]
0x1400187cc  jz      short loc_1400187E7
0x1400187ce  mov     rcx, [rsi]
0x1400187d1  add     rcx, r13; FastMutex
0x1400187d4  call    cs:__imp_ExAcquireFastMutex
0x1400187db  nop     dword ptr [rax+rax+00h]
0x1400187e0  mov     [rbx+0B8h], rdi
0x1400187e7  cmp     qword ptr [rbx+1D8h], 0
0x1400187ef  mov     ecx, [rbx+0C0h]
0x1400187f5  lea     eax, [rcx+1]
0x1400187f8  mov     [rbx+0C0h], eax
0x1400187fe  jz      short loc_14001882B
0x140018800  mov     [rbx+0C0h], ecx
0x140018806  test    ecx, ecx
0x140018808  jnz     short loc_140018827
0x14001880a  mov     rcx, [rsi]
0x14001880d  add     rcx, r13; FastMutex
0x140018810  mov     qword ptr [rbx+0B8h], 0
0x14001881b  call    cs:__imp_ExReleaseFastMutex
0x140018822  nop     dword ptr [rax+rax+00h]
0x140018827  mov     al, 1
0x140018829  jmp     short loc_14001887E
0x14001882b  xor     edx, edx; UnlockRoutine
0x14001882d  xor     ecx, ecx; CompleteLockIrpRoutine
0x14001882f  mov     dil, 1
0x140018832  call    cs:__imp_FsRtlAllocateFileLock
0x140018839  nop     dword ptr [rax+rax+00h]
0x14001883e  add     dword ptr [rbx+0C0h], 0FFFFFFFFh
0x140018845  mov     rbp, rax
0x140018848  mov     [rbx+1D8h], rax
0x14001884f  jnz     short loc_14001886E
0x140018851  mov     rcx, [rsi]
0x140018854  add     rcx, r13; FastMutex
0x140018857  mov     qword ptr [rbx+0B8h], 0
0x140018862  call    cs:__imp_ExReleaseFastMutex
0x140018869  nop     dword ptr [rax+rax+00h]
0x14001886e  test    rbp, rbp
0x140018871  jnz     short loc_14001887B
0x140018873  test    r14b, r14b
0x140018876  jnz     short loc_140018896
0x140018878  xor     dil, dil
0x14001887b  mov     al, dil
0x14001887e  mov     rbx, [rsp+58h+arg_0]
0x140018883  mov     rbp, [rsp+58h+arg_10]
0x140018888  add     rsp, 30h
0x14001888c  pop     r15
0x14001888e  pop     r14
0x140018890  pop     r13
0x140018892  pop     rdi
0x140018893  pop     rsi
0x140018894  retn
0x140018896  mov     r9d, 190000h
0x14001889c  mov     [rsp+58h+var_38], 61Ah
0x1400188a4  xor     r8d, r8d
0x1400188a7  mov     edx, 0C000009Ah
0x1400188ac  mov     rcx, r15
0x1400188af  call    CdRaiseStatusEx
```
