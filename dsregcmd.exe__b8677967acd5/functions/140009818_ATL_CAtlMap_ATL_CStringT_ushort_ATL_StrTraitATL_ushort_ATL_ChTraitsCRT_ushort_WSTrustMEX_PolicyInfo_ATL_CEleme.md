# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::UpdateRehashThresholds(void)

- ea: `0x140009818`
- end: `0x14000988f`
- name: `?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@AEAAXXZ`
- size: `119`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x140007180`
- `0x140008c34`
- `0x140008e50`
- `0x140019e24`
- `0x14001a28c`
- `0x14001b8d4`

## callees

- `0x140009818`

## pseudocode

```c
unsigned __int64 __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::UpdateRehashThresholds(
        __int64 a1)
{
  unsigned __int64 v1; // rdx
  float v2; // xmm0_4
  float v3; // xmm1_4
  float v4; // xmm0_4
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rdx
  unsigned __int64 result; // rax

  v1 = 0;
  v2 = (float)*(int *)(a1 + 16);
  v3 = v2 * *(float *)(a1 + 28);
  if ( v3 >= 9.223372e18 )
  {
    v3 = v3 - 9.223372e18;
    if ( v3 < 9.223372e18 )
      v1 = 0x8000000000000000uLL;
  }
  v4 = v2 * *(float *)(a1 + 24);
  v5 = v1 + (unsigned int)(int)v3;
  v6 = 0;
  *(_QWORD *)(a1 + 32) = v5;
  if ( v4 >= 9.223372e18 )
  {
    v4 = v4 - 9.223372e18;
    if ( v4 < 9.223372e18 )
      v6 = 0x8000000000000000uLL;
  }
  result = v6 + (unsigned int)(int)v4;
  *(_QWORD *)(a1 + 40) = result;
  if ( result < 0x11 )
    *(_QWORD *)(a1 + 40) = 0;
  return result;
}

```

## disassembly

```asm
0x140009818  mov     eax, [rcx+10h]
0x14000981b  xorps   xmm0, xmm0
0x14000981e  movss   xmm2, cs:__real@5f000000
0x140009826  xor     edx, edx
0x140009828  mov     r8, 8000000000000000h
0x140009832  cvtsi2ss xmm0, rax
0x140009837  movaps  xmm1, xmm0
0x14000983a  mulss   xmm1, dword ptr [rcx+1Ch]
0x14000983f  comiss  xmm1, xmm2
0x140009842  jb      short loc_140009850
0x140009844  subss   xmm1, xmm2
0x140009848  comiss  xmm1, xmm2
0x14000984b  jnb     short loc_140009850
0x14000984d  mov     rdx, r8
0x140009850  mulss   xmm0, dword ptr [rcx+18h]
0x140009855  cvttss2si rax, xmm1
0x14000985a  add     rax, rdx
0x14000985d  xor     edx, edx
0x14000985f  comiss  xmm0, xmm2
0x140009862  mov     [rcx+20h], rax
0x140009866  jb      short loc_140009874
0x140009868  subss   xmm0, xmm2
0x14000986c  comiss  xmm0, xmm2
0x14000986f  jnb     short loc_140009874
0x140009871  mov     rdx, r8
0x140009874  cvttss2si rax, xmm0
0x140009879  add     rax, rdx
0x14000987c  mov     [rcx+28h], rax
0x140009880  cmp     rax, 11h
0x140009884  jnb     short locret_14000988E
0x140009886  mov     qword ptr [rcx+28h], 0
0x14000988e  retn
```
