# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::FreeNode(ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::CNode *)

- ea: `0x14000878c`
- end: `0x14000886a`
- name: `?FreeNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VItem@TokenCache@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VItem@TokenCache@@@2@@ATL@@AEAAXPEAVCNode@12@@Z`
- size: `222`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140008f78`
- `0x14000f8f4`

## callees

- `0x14000579c`
- `0x140005c58`
- `0x14000878c`
- `0x140008db4`
- `0x140008e50`
- `0x140030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140008842`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140008842`

## pseudocode

```c
void __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<TokenCache::Item>>::FreeNode(
        __int64 a1,
        _QWORD *a2)
{
  volatile signed __int32 *v4; // rdx
  volatile signed __int32 *v5; // rdx
  unsigned int v6; // eax
  _QWORD *v7; // rcx
  _QWORD *v8; // rbx

  if ( !a2 )
    ATL::AtlThrowImpl(0x80004005);
  CSecureString::~CSecureString((CSecureString *)(a2 + 2));
  v4 = (volatile signed __int32 *)(a2[1] - 24LL);
  if ( _InterlockedExchangeAdd(v4 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4);
  v5 = (volatile signed __int32 *)(*a2 - 24LL);
  if ( _InterlockedExchangeAdd(v5 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
  a2[4] = *(_QWORD *)(a1 + 64);
  *(_QWORD *)(a1 + 64) = a2;
  if ( --*(_QWORD *)(a1 + 8) < *(_QWORD *)(a1 + 40) && !*(_DWORD *)(a1 + 48) )
  {
    v6 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::PickSize(a1);
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::Rehash(
      a1,
      v6);
  }
  if ( !*(_QWORD *)(a1 + 8) )
  {
    *(_QWORD *)(a1 + 64) = 0;
    v7 = *(_QWORD **)(a1 + 56);
    if ( v7 )
    {
      do
      {
        v8 = (_QWORD *)*v7;
        free(v7);
        v7 = v8;
      }
      while ( v8 );
      *(_QWORD *)(a1 + 56) = 0;
    }
  }
}

```

## disassembly

```asm
0x14000878c  mov     [rsp+arg_0], rbx
0x140008791  push    rdi
0x140008792  sub     rsp, 20h
0x140008796  mov     rbx, rdx
0x140008799  mov     rdi, rcx
0x14000879c  test    rdx, rdx
0x14000879f  jz      loc_14000885F
0x1400087a5  lea     rcx, [rdx+10h]; this
0x1400087a9  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x1400087ae  mov     rdx, [rbx+8]
0x1400087b2  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400087b6  or      eax, 0FFFFFFFFh
0x1400087b9  lock xadd [rdx+10h], eax
0x1400087be  sub     eax, 1
0x1400087c1  jg      short loc_1400087D2
0x1400087c3  mov     rcx, [rdx]
0x1400087c6  mov     rax, [rcx]
0x1400087c9  mov     rax, [rax+8]
0x1400087cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400087d2  mov     rdx, [rbx]
0x1400087d5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400087d9  or      eax, 0FFFFFFFFh
0x1400087dc  lock xadd [rdx+10h], eax
0x1400087e1  sub     eax, 1
0x1400087e4  jg      short loc_1400087F5
0x1400087e6  mov     rcx, [rdx]
0x1400087e9  mov     rax, [rcx]
0x1400087ec  mov     rax, [rax+8]
0x1400087f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400087f5  mov     rax, [rdi+40h]
0x1400087f9  mov     [rbx+20h], rax
0x1400087fd  mov     [rdi+40h], rbx
0x140008801  dec     qword ptr [rdi+8]
0x140008805  mov     rdx, [rdi+8]
0x140008809  cmp     rdx, [rdi+28h]
0x14000880d  jnb     short loc_140008827
0x14000880f  cmp     dword ptr [rdi+30h], 0
0x140008813  jnz     short loc_140008827
0x140008815  mov     rcx, rdi
0x140008818  call    ?PickSize@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@AEBAI_K@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::PickSize(unsigned __int64)
0x14000881d  mov     edx, eax
0x14000881f  mov     rcx, rdi
0x140008822  call    ?Rehash@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@QEAAXI@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::Rehash(uint)
0x140008827  cmp     qword ptr [rdi+8], 0
0x14000882c  jnz     short loc_140008854
0x14000882e  mov     qword ptr [rdi+40h], 0
0x140008836  mov     rcx, [rdi+38h]; Block
0x14000883a  test    rcx, rcx
0x14000883d  jz      short loc_140008854
0x14000883f  mov     rbx, [rcx]
0x140008842  call    cs:__imp_free
0x140008848  mov     rcx, rbx
0x14000884b  test    rbx, rbx
0x14000884e  jnz     short loc_14000883F
0x140008850  mov     [rdi+38h], rbx
0x140008854  mov     rbx, [rsp+28h+arg_0]
0x140008859  add     rsp, 20h
0x14000885d  pop     rdi
0x14000885e  retn
0x14000885f  mov     ecx, 80004005h; unsigned int
0x140008864  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
