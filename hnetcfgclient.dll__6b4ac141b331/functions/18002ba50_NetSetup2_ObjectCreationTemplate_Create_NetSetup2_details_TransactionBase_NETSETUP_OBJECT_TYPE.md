# NetSetup2::ObjectCreationTemplate::Create(NetSetup2::details::TransactionBase &,_NETSETUP_OBJECT_TYPE)

- ea: `0x18002ba50`
- end: `0x18002bb46`
- name: `?Create@ObjectCreationTemplate@NetSetup2@@QEAA?AU_GUID@@AEAVTransactionBase@details@2@W4_NETSETUP_OBJECT_TYPE@@@Z`
- size: `246`
- prototype: `_OWORD *__fastcall(__int64 *, _OWORD *, _QWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180026510`

## callees

- `0x1800216c0`
- `0x180026c18`
- `0x18002ba50`
- `0x18002c374`
- `0x18002c758`

## import_xrefs

- `NetSetupApi!NetSetupCreateObject` at `0x18002bb0a`
- `NetSetupApi!NetSetupCreateObject` at `0x18002bb0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_OWORD *__fastcall NetSetup2::ObjectCreationTemplate::Create(__int64 *a1, _OWORD *a2, _QWORD *a3, unsigned int a4)
{
  unsigned __int64 v8; // r8
  __int64 v9; // rcx
  __int64 i; // r9
  __int64 v11; // r8
  int Object; // eax
  __int128 v14; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v14 = 0;
  v15 = 0;
  std::vector<_NETSETUPPROPERTY>::resize(&v14, 0xAAAAAAAAAAAAAAABuLL * ((a1[1] - *a1) >> 4));
  v8 = 0;
  v9 = *a1;
  for ( i = v14; v8 < 0xAAAAAAAAAAAAAAABuLL * ((a1[1] - *a1) >> 4); v9 = *a1 )
  {
    NetSetup2::Property::Store((NetSetup2::Property *)(48 * v8 + v9), (struct _NETSETUPPROPERTY *)(48 * v8 + i));
    v8 = v11 + 1;
  }
  *a2 = 0;
  Object = NetSetupCreateObject(*a3, a4, 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)&v14 + 1) - i) >> 4));
  if ( Object < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x445,
      (unsigned int)"onecore\\internal\\net\\inc\\NetSetupCxx.cpp",
      (const char *)(unsigned int)Object,
      (int)a2);
  std::vector<_NETSETUPPROPERTY>::_Tidy((__int64)&v14);
  return a2;
}

```

## disassembly

```asm
0x18002ba50  push    rbx
0x18002ba52  push    rbp
0x18002ba53  push    rsi
0x18002ba54  push    rdi
0x18002ba55  push    r14
0x18002ba57  sub     rsp, 50h
0x18002ba5b  mov     esi, r9d
0x18002ba5e  mov     r14, r8
0x18002ba61  mov     rbx, rdx
0x18002ba64  mov     rdi, rcx
0x18002ba67  xorps   xmm0, xmm0
0x18002ba6a  movdqu  [rsp+78h+var_48], xmm0
0x18002ba70  mov     [rsp+78h+var_38], 0
0x18002ba79  mov     rdx, [rcx+8]
0x18002ba7d  sub     rdx, [rcx]
0x18002ba80  sar     rdx, 4
0x18002ba84  mov     rbp, 0AAAAAAAAAAAAAAABh
0x18002ba8e  imul    rdx, rbp
0x18002ba92  lea     rcx, [rsp+78h+var_48]
0x18002ba97  call    ?resize@?$vector@U_NETSETUPPROPERTY@@V?$allocator@U_NETSETUPPROPERTY@@@std@@@std@@QEAAX_K@Z; std::vector<_NETSETUPPROPERTY>::resize(unsigned __int64)
0x18002ba9c  nop
0x18002ba9d  xor     r8d, r8d
0x18002baa0  mov     rcx, [rdi]
0x18002baa3  mov     rax, [rdi+8]
0x18002baa7  sub     rax, rcx
0x18002baaa  sar     rax, 4
0x18002baae  imul    rax, rbp
0x18002bab2  mov     r9, qword ptr [rsp+78h+var_48]
0x18002bab7  test    rax, rax
0x18002baba  jz      short loc_18002BAEA
0x18002babc  lea     rax, [r8+r8*2]
0x18002bac0  shl     rax, 4
0x18002bac4  lea     rdx, [rax+r9]; struct _NETSETUPPROPERTY *
0x18002bac8  add     rcx, rax; this
0x18002bacb  call    ?Store@Property@NetSetup2@@QEBAXAEAU_NETSETUPPROPERTY@@@Z; NetSetup2::Property::Store(_NETSETUPPROPERTY &)
0x18002bad0  inc     r8
0x18002bad3  mov     rcx, [rdi]
0x18002bad6  mov     rax, [rdi+8]
0x18002bada  sub     rax, rcx
0x18002badd  sar     rax, 4
0x18002bae1  imul    rax, rbp
0x18002bae5  cmp     r8, rax
0x18002bae8  jb      short loc_18002BABC
0x18002baea  xorps   xmm0, xmm0
0x18002baed  movups  xmmword ptr [rbx], xmm0
0x18002baf0  mov     r8, qword ptr [rsp+78h+var_48+8]
0x18002baf5  sub     r8, r9
0x18002baf8  sar     r8, 4
0x18002bafc  imul    r8, rbp
0x18002bb00  mov     qword ptr [rsp+78h+var_58], rbx; int
0x18002bb05  mov     edx, esi
0x18002bb07  mov     rcx, [r14]
0x18002bb0a  call    cs:__imp_NetSetupCreateObject
0x18002bb10  test    eax, eax
0x18002bb12  jns     short loc_18002BB2E
0x18002bb14  mov     rcx, [rsp+78h]; this
0x18002bb19  mov     r9d, eax; char *
0x18002bb1c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\net\\inc\\NetSetupCx"...
0x18002bb23  mov     edx, 445h; void *
0x18002bb28  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002bb2e  lea     rcx, [rsp+78h+var_48]
0x18002bb33  call    ?_Tidy@?$vector@U_NETSETUPPROPERTY@@V?$allocator@U_NETSETUPPROPERTY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPERTY>::_Tidy(void)
0x18002bb38  mov     rax, rbx
0x18002bb3b  add     rsp, 50h
0x18002bb3f  pop     r14
0x18002bb41  pop     rdi
0x18002bb42  pop     rsi
0x18002bb43  pop     rbp
0x18002bb44  pop     rbx
0x18002bb45  retn
```
