# FveConfigSubscriberBaseRelease

- ea: `0x140084890`
- end: `0x14008496e`
- name: `FveConfigSubscriberBaseRelease`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140022cd0`
- `0x140023040`
- `0x140084890`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14008493c`
- `ntoskrnl!ObfDereferenceObject` at `0x14008493c`
- `ntoskrnl!ExDeleteResourceLite` at `0x140084927`
- `ntoskrnl!ExDeleteResourceLite` at `0x140084927`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400848f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400848f8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400848c8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400848c8`

## pseudocode

```c
__int64 __fastcall FveConfigSubscriberBaseRelease(__int64 a1, char *a2)
{
  __int64 v2; // rdi
  void (__fastcall *v5)(__int64, char *); // rbp
  unsigned __int32 v6; // esi
  _QWORD *v7; // rcx
  void **v8; // rax
  void *v9; // rcx

  v2 = *((_QWORD *)a2 + 2);
  v5 = *(void (__fastcall **)(__int64, char *))(v2 + 160);
  v6 = _InterlockedDecrement((volatile signed __int32 *)a2 + 11);
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
      --*(_DWORD *)(v2 + 20);
      ExReleaseResourceLite(*(PERESOURCE *)(v2 + 8));
    }
    if ( v5 && (char *)v5 != (char *)&FveConfigSubscriberBaseRelease )
      v5(a1, a2);
    ExDeleteResourceLite((PERESOURCE)(a2 + 64));
    v9 = (void *)*((_QWORD *)a2 + 3);
    if ( v9 )
      ObfDereferenceObject(v9);
    memset(a2, 0, *(unsigned int *)(v2 + 132));
  }
  return v6;
}

```

## disassembly

```asm
0x140084890  push    rbx
0x140084892  push    rbp
0x140084893  push    rsi
0x140084894  push    rdi
0x140084895  push    r14
0x140084897  sub     rsp, 20h
0x14008489b  mov     rdi, [rdx+10h]
0x14008489f  mov     rbx, rdx
0x1400848a2  mov     r14, rcx
0x1400848a5  or      esi, 0FFFFFFFFh
0x1400848a8  mov     rbp, [rdi+0A0h]
0x1400848af  lock xadd [rdx+2Ch], esi
0x1400848b4  sub     esi, 1
0x1400848b7  jnz     loc_140084959
0x1400848bd  cmp     [rdx], rdx
0x1400848c0  jz      short loc_140084904
0x1400848c2  mov     rcx, [rdi+8]; Resource
0x1400848c6  mov     dl, 1; Wait
0x1400848c8  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400848cf  nop     dword ptr [rax+rax+00h]
0x1400848d4  mov     rcx, [rbx]
0x1400848d7  cmp     [rcx+8], rbx
0x1400848db  jnz     loc_140084967
0x1400848e1  mov     rax, [rbx+8]
0x1400848e5  cmp     [rax], rbx
0x1400848e8  jnz     short loc_140084967
0x1400848ea  mov     [rax], rcx
0x1400848ed  mov     [rcx+8], rax
0x1400848f1  dec     dword ptr [rdi+14h]
0x1400848f4  mov     rcx, [rdi+8]; Resource
0x1400848f8  call    cs:__imp_ExReleaseResourceLite
0x1400848ff  nop     dword ptr [rax+rax+00h]
0x140084904  test    rbp, rbp
0x140084907  jz      short loc_140084923
0x140084909  lea     rax, FveConfigSubscriberBaseRelease
0x140084910  cmp     rbp, rax
0x140084913  jz      short loc_140084923
0x140084915  mov     rdx, rbx
0x140084918  mov     rcx, r14
0x14008491b  mov     rax, rbp
0x14008491e  call    _guard_dispatch_icall
0x140084923  lea     rcx, [rbx+40h]; Resource
0x140084927  call    cs:__imp_ExDeleteResourceLite
0x14008492e  nop     dword ptr [rax+rax+00h]
0x140084933  mov     rcx, [rbx+18h]; Object
0x140084937  test    rcx, rcx
0x14008493a  jz      short loc_140084948
0x14008493c  call    cs:__imp_ObfDereferenceObject
0x140084943  nop     dword ptr [rax+rax+00h]
0x140084948  mov     r8d, [rdi+84h]; Size
0x14008494f  xor     edx, edx; Val
0x140084951  mov     rcx, rbx; void *
0x140084954  call    memset
0x140084959  mov     eax, esi
0x14008495b  add     rsp, 20h
0x14008495f  pop     r14
0x140084961  pop     rdi
0x140084962  pop     rsi
0x140084963  pop     rbp
0x140084964  pop     rbx
0x140084965  retn
0x140084967  mov     ecx, 3
0x14008496c  int     29h; Win8: RtlFailFast(ecx)
```
