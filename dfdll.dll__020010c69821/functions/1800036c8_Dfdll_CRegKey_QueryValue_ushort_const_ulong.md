# Dfdll::CRegKey::QueryValue(ushort const *,ulong &)

- ea: `0x1800036c8`
- end: `0x18000379e`
- name: `?QueryValue@CRegKey@Dfdll@@QEAAJPEBGAEAK@Z`
- size: `214`
- prototype: `__int64 __fastcall(Dfdll::CRegKey *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180003168`

## callees

- `0x1800036c8`
- `0x180003b58`
- `0x180012b30`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Dfdll::CRegKey::QueryValue(HKEY *this, const unsigned __int16 *a2, unsigned int *a3)
{
  const struct std::nothrow_t *v3; // rdx
  int Value; // edi
  void **v6; // [rsp+30h] [rbp-20h] BYREF
  void *v7; // [rsp+38h] [rbp-18h]
  int v8; // [rsp+40h] [rbp-10h]
  __int64 v9; // [rsp+88h] [rbp+38h] BYREF

  LODWORD(v9) = 0;
  v7 = 0;
  v8 = 0;
  v6 = &Dfdll::CBuffer<unsigned char>::`vftable';
  Value = Dfdll::CSystem::RegQueryValueExW(this[1], a2, 0, (Dfdll::CBufferBase *)&v6, (__int64)&v9);
  if ( Value >= 0 )
  {
    Value = -2147024883;
    v6 = &Dfdll::CBuffer<unsigned char>::`vftable';
    if ( v7 )
      operator delete(v7, v3);
  }
  else
  {
    v6 = &Dfdll::CBuffer<unsigned char>::`vftable';
    if ( v7 )
      operator delete(v7, v3);
  }
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x1800036c8  mov     [rsp-18h+arg_8], rbx
0x1800036cd  push    rbp
0x1800036ce  push    rdi
0x1800036cf  push    r14
0x1800036d1  mov     rbp, rsp
0x1800036d4  sub     rsp, 50h
0x1800036d8  mov     rbx, r8
0x1800036db  and     dword ptr [rbp+arg_18], 0
0x1800036df  and     [rbp+arg_0], 0
0x1800036e3  and     [rbp+var_18], 0
0x1800036e8  and     [rbp+var_10], 0
0x1800036ec  lea     r14, ??_7?$CBuffer@E@Dfdll@@6B@; const Dfdll::CBuffer<uchar>::`vftable'
0x1800036f3  mov     [rbp+var_20], r14
0x1800036f7  lea     rax, [rbp+arg_18]
0x1800036fb  mov     [rsp+50h+var_28], rax; __int64
0x180003700  lea     rax, [rbp+var_20]
0x180003704  mov     [rsp+50h+var_30], rax; Dfdll::CBufferBase *
0x180003709  lea     r9, [rbp+arg_0]
0x18000370d  xor     r8d, r8d; lpReserved
0x180003710  mov     rcx, [rcx+8]; hKey
0x180003714  call    ?RegQueryValueExW@CSystem@Dfdll@@SAJPEAUHKEY__@@PEBGPEAK2AEAV?$CBuffer@E@2@AEAJ@Z; Dfdll::CSystem::RegQueryValueExW(HKEY__ *,ushort const *,ulong *,ulong *,Dfdll::CBuffer<uchar> &,long &)
0x180003719  mov     edi, eax
0x18000371b  test    eax, eax
0x18000371d  jns     short loc_180003734
0x18000371f  mov     [rbp+var_20], r14
0x180003723  mov     rcx, [rbp+var_18]; void *
0x180003727  test    rcx, rcx
0x18000372a  jz      short loc_180003732
0x18000372c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003731  nop
0x180003732  jmp     short loc_18000378E
0x180003734  mov     eax, 4
0x180003739  cmp     [rbp+arg_0], eax
0x18000373c  jz      short loc_180003758
0x18000373e  mov     edi, 8007000Dh
0x180003743  mov     [rbp+var_20], r14
0x180003747  mov     rcx, [rbp+var_18]; void *
0x18000374b  test    rcx, rcx
0x18000374e  jz      short loc_180003756
0x180003750  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003755  nop
0x180003756  jmp     short loc_18000378E
0x180003758  and     dword ptr [rbx], 0
0x18000375b  cmp     [rbp+var_10], eax
0x18000375e  cmovb   eax, [rbp+var_10]
0x180003762  sub     eax, 1
0x180003765  movsxd  rdx, eax
0x180003768  mov     rcx, [rbp+var_18]; void *
0x18000376c  js      short loc_18000377D
0x18000376e  shl     dword ptr [rbx], 8
0x180003771  movzx   eax, byte ptr [rdx+rcx]
0x180003775  or      [rbx], eax
0x180003777  sub     rdx, 1; struct std::nothrow_t *
0x18000377b  jns     short loc_18000376E
0x18000377d  xor     edi, edi
0x18000377f  mov     [rbp+var_20], r14
0x180003783  test    rcx, rcx
0x180003786  jz      short loc_18000378E
0x180003788  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000378d  nop
0x18000378e  mov     eax, edi
0x180003790  mov     rbx, [rsp+50h+arg_8]
0x180003795  add     rsp, 50h
0x180003799  pop     r14
0x18000379b  pop     rdi
0x18000379c  pop     rbp
0x18000379d  retn
```
