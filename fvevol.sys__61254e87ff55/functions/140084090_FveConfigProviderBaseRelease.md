# FveConfigProviderBaseRelease

- ea: `0x140084090`
- end: `0x140084191`
- name: `FveConfigProviderBaseRelease`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140022cd0`
- `0x140023040`
- `0x140084090`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14008415f`
- `ntoskrnl!ExDeleteResourceLite` at `0x14008415f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400840fc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400840fc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400840c8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400840c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084147`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084147`

## pseudocode

```c
__int64 __fastcall FveConfigProviderBaseRelease(__int64 a1, char *a2)
{
  __int64 v2; // rdi
  void (__fastcall *v5)(__int64, char *); // rbp
  unsigned __int32 v6; // esi
  _QWORD *v7; // rcx
  void **v8; // rax
  void *v9; // rcx

  v2 = *((_QWORD *)a2 + 2);
  v5 = *(void (__fastcall **)(__int64, char *))(v2 + 208);
  v6 = _InterlockedDecrement((volatile signed __int32 *)a2 + 9);
  if ( !v6 )
  {
    if ( *(char **)a2 != a2 )
    {
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v2 + 8), 1u);
      v7 = *(_QWORD **)a2;
      if ( *(char **)(*(_QWORD *)a2 + 8LL) != a2 || (v8 = (void **)*((_QWORD *)a2 + 1), *v8 != a2) )
        __fastfail(3u);
      *v8 = v7;
      v7[1] = v8;
      --*(_DWORD *)(v2 + 16);
      ExReleaseResourceLite(*(PERESOURCE *)(v2 + 8));
    }
    if ( v5 && (char *)v5 != (char *)&FveConfigProviderBaseRelease )
      v5(a1, a2);
    v9 = (void *)*((_QWORD *)a2 + 6);
    if ( v9 )
    {
      memset(v9, 0, *(unsigned int *)(v2 + 136));
      ExFreePoolWithTag(*((PVOID *)a2 + 6), 0x30455646u);
      *((_QWORD *)a2 + 6) = 0;
    }
    ExDeleteResourceLite((PERESOURCE)(a2 + 56));
    memset(a2, 0, *(unsigned int *)(v2 + 128));
  }
  return v6;
}

```

## disassembly

```asm
0x140084090  push    rbx
0x140084092  push    rbp
0x140084093  push    rsi
0x140084094  push    rdi
0x140084095  push    r14
0x140084097  sub     rsp, 20h
0x14008409b  mov     rdi, [rdx+10h]
0x14008409f  mov     rbx, rdx
0x1400840a2  mov     r14, rcx
0x1400840a5  or      esi, 0FFFFFFFFh
0x1400840a8  mov     rbp, [rdi+0D0h]
0x1400840af  lock xadd [rdx+24h], esi
0x1400840b4  sub     esi, 1
0x1400840b7  jnz     loc_14008417C
0x1400840bd  cmp     [rdx], rdx
0x1400840c0  jz      short loc_140084108
0x1400840c2  mov     rcx, [rdi+8]; Resource
0x1400840c6  mov     dl, 1; Wait
0x1400840c8  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400840cf  nop     dword ptr [rax+rax+00h]
0x1400840d4  mov     rcx, [rbx]
0x1400840d7  cmp     [rcx+8], rbx
0x1400840db  jnz     loc_14008418A
0x1400840e1  mov     rax, [rbx+8]
0x1400840e5  cmp     [rax], rbx
0x1400840e8  jnz     loc_14008418A
0x1400840ee  mov     [rax], rcx
0x1400840f1  mov     [rcx+8], rax
0x1400840f5  dec     dword ptr [rdi+10h]
0x1400840f8  mov     rcx, [rdi+8]; Resource
0x1400840fc  call    cs:__imp_ExReleaseResourceLite
0x140084103  nop     dword ptr [rax+rax+00h]
0x140084108  test    rbp, rbp
0x14008410b  jz      short loc_140084127
0x14008410d  lea     rax, FveConfigProviderBaseRelease
0x140084114  cmp     rbp, rax
0x140084117  jz      short loc_140084127
0x140084119  mov     rdx, rbx
0x14008411c  mov     rcx, r14
0x14008411f  mov     rax, rbp
0x140084122  call    _guard_dispatch_icall
0x140084127  mov     rcx, [rbx+30h]; void *
0x14008412b  test    rcx, rcx
0x14008412e  jz      short loc_14008415B
0x140084130  mov     r8d, [rdi+88h]; Size
0x140084137  xor     edx, edx; Val
0x140084139  call    memset
0x14008413e  mov     rcx, [rbx+30h]; P
0x140084142  mov     edx, 30455646h; Tag
0x140084147  call    cs:__imp_ExFreePoolWithTag
0x14008414e  nop     dword ptr [rax+rax+00h]
0x140084153  mov     qword ptr [rbx+30h], 0
0x14008415b  lea     rcx, [rbx+38h]; Resource
0x14008415f  call    cs:__imp_ExDeleteResourceLite
0x140084166  nop     dword ptr [rax+rax+00h]
0x14008416b  mov     r8d, [rdi+80h]; Size
0x140084172  xor     edx, edx; Val
0x140084174  mov     rcx, rbx; void *
0x140084177  call    memset
0x14008417c  mov     eax, esi
0x14008417e  add     rsp, 20h
0x140084182  pop     r14
0x140084184  pop     rdi
0x140084185  pop     rsi
0x140084186  pop     rbp
0x140084187  pop     rbx
0x140084188  retn
0x14008418a  mov     ecx, 3
0x14008418f  int     29h; Win8: RtlFailFast(ecx)
```
