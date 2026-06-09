# FveConfigProviderBaseRelease

- ea: `0x140081ff0`
- end: `0x1400820f1`
- name: `FveConfigProviderBaseRelease`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400219a0`
- `0x140021d00`
- `0x140081ff0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400820bf`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400820bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008205c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008205c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140082028`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140082028`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400820a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400820a7`

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
0x140081ff0  push    rbx
0x140081ff2  push    rbp
0x140081ff3  push    rsi
0x140081ff4  push    rdi
0x140081ff5  push    r14
0x140081ff7  sub     rsp, 20h
0x140081ffb  mov     rdi, [rdx+10h]
0x140081fff  mov     rbx, rdx
0x140082002  mov     r14, rcx
0x140082005  or      esi, 0FFFFFFFFh
0x140082008  mov     rbp, [rdi+0D0h]
0x14008200f  lock xadd [rdx+24h], esi
0x140082014  sub     esi, 1
0x140082017  jnz     loc_1400820DC
0x14008201d  cmp     [rdx], rdx
0x140082020  jz      short loc_140082068
0x140082022  mov     rcx, [rdi+8]; Resource
0x140082026  mov     dl, 1; Wait
0x140082028  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14008202f  nop     dword ptr [rax+rax+00h]
0x140082034  mov     rcx, [rbx]
0x140082037  cmp     [rcx+8], rbx
0x14008203b  jnz     loc_1400820EA
0x140082041  mov     rax, [rbx+8]
0x140082045  cmp     [rax], rbx
0x140082048  jnz     loc_1400820EA
0x14008204e  mov     [rax], rcx
0x140082051  mov     [rcx+8], rax
0x140082055  dec     dword ptr [rdi+10h]
0x140082058  mov     rcx, [rdi+8]; Resource
0x14008205c  call    cs:__imp_ExReleaseResourceLite
0x140082063  nop     dword ptr [rax+rax+00h]
0x140082068  test    rbp, rbp
0x14008206b  jz      short loc_140082087
0x14008206d  lea     rax, FveConfigProviderBaseRelease
0x140082074  cmp     rbp, rax
0x140082077  jz      short loc_140082087
0x140082079  mov     rdx, rbx
0x14008207c  mov     rcx, r14
0x14008207f  mov     rax, rbp
0x140082082  call    _guard_dispatch_icall
0x140082087  mov     rcx, [rbx+30h]; void *
0x14008208b  test    rcx, rcx
0x14008208e  jz      short loc_1400820BB
0x140082090  mov     r8d, [rdi+88h]; Size
0x140082097  xor     edx, edx; Val
0x140082099  call    memset
0x14008209e  mov     rcx, [rbx+30h]; P
0x1400820a2  mov     edx, 30455646h; Tag
0x1400820a7  call    cs:__imp_ExFreePoolWithTag
0x1400820ae  nop     dword ptr [rax+rax+00h]
0x1400820b3  mov     qword ptr [rbx+30h], 0
0x1400820bb  lea     rcx, [rbx+38h]; Resource
0x1400820bf  call    cs:__imp_ExDeleteResourceLite
0x1400820c6  nop     dword ptr [rax+rax+00h]
0x1400820cb  mov     r8d, [rdi+80h]; Size
0x1400820d2  xor     edx, edx; Val
0x1400820d4  mov     rcx, rbx; void *
0x1400820d7  call    memset
0x1400820dc  mov     eax, esi
0x1400820de  add     rsp, 20h
0x1400820e2  pop     r14
0x1400820e4  pop     rdi
0x1400820e5  pop     rsi
0x1400820e6  pop     rbp
0x1400820e7  pop     rbx
0x1400820e8  retn
0x1400820ea  mov     ecx, 3
0x1400820ef  int     29h; Win8: RtlFailFast(ecx)
```
