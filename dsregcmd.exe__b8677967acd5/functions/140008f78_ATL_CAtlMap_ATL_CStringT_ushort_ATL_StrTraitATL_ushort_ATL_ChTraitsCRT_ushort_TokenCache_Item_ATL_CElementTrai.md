# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::RemoveAll(void)

- ea: `0x140008f78`
- end: `0x14000902b`
- name: `?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VItem@TokenCache@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VItem@TokenCache@@@2@@ATL@@QEAAXXZ`
- size: `179`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1400075c0`
- `0x140007b74`
- `0x140009518`

## callees

- `0x140001820`
- `0x14000878c`
- `0x140008c34`
- `0x140008db4`
- `0x140008f78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140009006`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140009006`

## pseudocode

```c
void __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<TokenCache::Item>>::RemoveAll(
        __int64 a1)
{
  __int64 i; // rbx
  _QWORD *v3; // rsi
  _QWORD *v4; // rdx
  unsigned int v5; // eax
  _QWORD *v6; // rcx
  _QWORD *v7; // rbx

  ++*(_DWORD *)(a1 + 48);
  if ( *(_QWORD *)a1 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 16); i = (unsigned int)(i + 1) )
    {
      v3 = *(_QWORD **)(*(_QWORD *)a1 + 8 * i);
      while ( v3 )
      {
        v4 = v3;
        v3 = (_QWORD *)v3[4];
        ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<TokenCache::Item>>::FreeNode(
          a1,
          v4);
      }
    }
  }
  operator delete(*(void **)a1);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  if ( !*(_DWORD *)(a1 + 48) )
  {
    v5 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::PickSize(a1);
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::InitHashTable(
      (void **)a1,
      v5,
      0);
  }
  *(_QWORD *)(a1 + 64) = 0;
  v6 = *(_QWORD **)(a1 + 56);
  if ( v6 )
  {
    do
    {
      v7 = (_QWORD *)*v6;
      free(v6);
      v6 = v7;
    }
    while ( v7 );
    *(_QWORD *)(a1 + 56) = 0;
  }
  --*(_DWORD *)(a1 + 48);
}

```

## disassembly

```asm
0x140008f78  mov     [rsp+arg_0], rbx
0x140008f7d  mov     [rsp+arg_8], rsi
0x140008f82  push    rdi
0x140008f83  sub     rsp, 20h
0x140008f87  mov     rdi, rcx
0x140008f8a  inc     dword ptr [rcx+30h]
0x140008f8d  cmp     qword ptr [rcx], 0
0x140008f91  jz      short loc_140008FBE
0x140008f93  xor     ebx, ebx
0x140008f95  cmp     [rcx+10h], ebx
0x140008f98  jbe     short loc_140008FBE
0x140008f9a  mov     rax, [rdi]
0x140008f9d  mov     rsi, [rax+rbx*8]
0x140008fa1  jmp     short loc_140008FB2
0x140008fa3  mov     rdx, rsi
0x140008fa6  mov     rsi, [rsi+20h]
0x140008faa  mov     rcx, rdi
0x140008fad  call    ?FreeNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VItem@TokenCache@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VItem@TokenCache@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::FreeNode(ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::CNode *)
0x140008fb2  test    rsi, rsi
0x140008fb5  jnz     short loc_140008FA3
0x140008fb7  inc     ebx
0x140008fb9  cmp     ebx, [rdi+10h]
0x140008fbc  jb      short loc_140008F9A
0x140008fbe  mov     rcx, [rdi]; Block
0x140008fc1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140008fc6  mov     qword ptr [rdi], 0
0x140008fcd  mov     qword ptr [rdi+8], 0
0x140008fd5  cmp     dword ptr [rdi+30h], 0
0x140008fd9  jnz     short loc_140008FF2
0x140008fdb  xor     edx, edx
0x140008fdd  mov     rcx, rdi
0x140008fe0  call    ?PickSize@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@AEBAI_K@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::PickSize(unsigned __int64)
0x140008fe5  mov     edx, eax
0x140008fe7  xor     r8d, r8d
0x140008fea  mov     rcx, rdi
0x140008fed  call    ?InitHashTable@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::InitHashTable(uint,bool)
0x140008ff2  mov     qword ptr [rdi+40h], 0
0x140008ffa  mov     rcx, [rdi+38h]; Block
0x140008ffe  test    rcx, rcx
0x140009001  jz      short loc_140009018
0x140009003  mov     rbx, [rcx]
0x140009006  call    cs:__imp_free
0x14000900c  mov     rcx, rbx
0x14000900f  test    rbx, rbx
0x140009012  jnz     short loc_140009003
0x140009014  mov     [rdi+38h], rbx
0x140009018  dec     dword ptr [rdi+30h]
0x14000901b  mov     rbx, [rsp+28h+arg_0]
0x140009020  mov     rsi, [rsp+28h+arg_8]
0x140009025  add     rsp, 20h
0x140009029  pop     rdi
0x14000902a  retn
```
