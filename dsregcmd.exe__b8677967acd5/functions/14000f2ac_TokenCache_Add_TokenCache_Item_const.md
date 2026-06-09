# TokenCache::Add(TokenCache::Item const &)

- ea: `0x14000f2ac`
- end: `0x14000f377`
- name: `?Add@TokenCache@@QEAAXAEBVItem@1@@Z`
- size: `203`
- prototype: `void __fastcall(TokenCache *__hidden this, const struct TokenCache::Item *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400090ec`
- `0x140009518`

## callees

- `0x140005c58`
- `0x140007bf8`
- `0x140008c34`
- `0x14000f2ac`
- `0x14000f6b0`
- `0x14000f77c`
- `0x140030010`

## pseudocode

```c
void __fastcall TokenCache::Add(TokenCache *this, const struct TokenCache::Item *a2)
{
  __int64 v4; // rsi
  char *v5; // rbx
  __int64 Node; // rax
  __int64 v7; // r8
  __int64 v8; // rbx
  unsigned int v9; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v10; // [rsp+60h] [rbp+18h] BYREF
  __int64 v11; // [rsp+68h] [rbp+20h] BYREF

  if ( (**(unsigned __int8 (__fastcall ***)(TokenCache *, const struct TokenCache::Item *, _QWORD))this)(this, a2, 0) )
  {
    v4 = *(_QWORD *)a2;
    v5 = (char *)this + 8;
    v10 = 0;
    v9 = 0;
    v11 = 0;
    Node = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<TokenCache::Item>>::GetNode(
             (_DWORD)v5,
             v4,
             (unsigned int)&v10,
             (unsigned int)&v9,
             (__int64)&v11);
    if ( !Node )
    {
      if ( !*(_QWORD *)v5 )
      {
        LOBYTE(v7) = 1;
        if ( !(unsigned __int8)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::InitHashTable(
                                 v5,
                                 *((unsigned int *)v5 + 4),
                                 v7) )
          ATL::AtlThrowImpl(0x8007000E);
      }
      Node = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<TokenCache::Item>>::NewNode(
               v5,
               v4,
               v10,
               v9);
    }
    v8 = Node + 8;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (_QWORD *)(Node + 8),
      a2);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (_QWORD *)(v8 + 8),
      (_QWORD *)a2 + 1);
    *(_QWORD *)(v8 + 16) = *((_QWORD *)a2 + 2);
  }
}

```

## disassembly

```asm
0x14000f2ac  push    rbx
0x14000f2ae  push    rsi
0x14000f2af  push    rdi
0x14000f2b0  sub     rsp, 30h
0x14000f2b4  mov     rax, [rcx]
0x14000f2b7  xor     r8d, r8d
0x14000f2ba  mov     rdi, rdx
0x14000f2bd  mov     rbx, rcx
0x14000f2c0  mov     rax, [rax]
0x14000f2c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f2c8  test    al, al
0x14000f2ca  jz      loc_14000F364
0x14000f2d0  mov     rsi, [rdi]
0x14000f2d3  lea     rax, [rsp+48h+arg_18]
0x14000f2d8  add     rbx, 8
0x14000f2dc  mov     [rsp+48h+arg_10], 0
0x14000f2e4  mov     rdx, rsi
0x14000f2e7  mov     [rsp+48h+arg_0], 0
0x14000f2ef  mov     rcx, rbx
0x14000f2f2  mov     [rsp+48h+arg_18], 0
0x14000f2fb  lea     r9, [rsp+48h+arg_0]
0x14000f300  mov     [rsp+48h+var_28], rax
0x14000f305  lea     r8, [rsp+48h+arg_10]
0x14000f30a  call    ?GetNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VItem@TokenCache@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VItem@TokenCache@@@2@@ATL@@AEBAPEAVCNode@12@PEBGAEAI1AEAPEAV312@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::GetNode(ushort const *,uint &,uint &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::CNode * &)
0x14000f30f  test    rax, rax
0x14000f312  jnz     short loc_14000F340
0x14000f314  cmp     [rbx], rax
0x14000f317  jnz     short loc_14000F32B
0x14000f319  mov     edx, [rbx+10h]
0x14000f31c  mov     r8b, 1
0x14000f31f  mov     rcx, rbx
0x14000f322  call    ?InitHashTable@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::InitHashTable(uint,bool)
0x14000f327  test    al, al
0x14000f329  jz      short loc_14000F36C
0x14000f32b  mov     r9d, [rsp+48h+arg_0]
0x14000f330  mov     rdx, rsi
0x14000f333  mov     r8d, [rsp+48h+arg_10]
0x14000f338  mov     rcx, rbx
0x14000f33b  call    ?NewNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VItem@TokenCache@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VItem@TokenCache@@@2@@ATL@@AEAAPEAVCNode@12@PEBGII@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::NewNode(ushort const *,uint,uint)
0x14000f340  lea     rbx, [rax+8]
0x14000f344  mov     rdx, rdi
0x14000f347  mov     rcx, rbx
0x14000f34a  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000f34f  lea     rdx, [rdi+8]
0x14000f353  lea     rcx, [rbx+8]
0x14000f357  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000f35c  mov     rax, [rdi+10h]
0x14000f360  mov     [rbx+10h], rax
0x14000f364  add     rsp, 30h
0x14000f368  pop     rdi
0x14000f369  pop     rsi
0x14000f36a  pop     rbx
0x14000f36b  retn
0x14000f36c  mov     ecx, 8007000Eh; unsigned int
0x14000f371  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
