# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmersiveColorFight>::GetCurrentFeatureEnabledState(int *)

- ea: `0x140015fc8`
- end: `0x140016087`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ImmersiveColorFight@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `191`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140014f60`

## callees

- `0x140015fc8`
- `0x140017d24`
- `0x140017f7c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmersiveColorFight>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  unsigned int v9; // r8d
  int v10; // edi
  char v11; // si
  char IsEnabled; // al
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x34217D1, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v8 = 0;
    if ( v6 == 2 )
      v8 = 64;
  }
  else
  {
    v8 = 64;
  }
  v9 = v8 | v7;
  v10 = 1;
  *(_DWORD *)a2 = v9;
  if ( (v9 & 0x400) != 0 && v9 >= 0x800 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    IsEnabled = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_12;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl);
  if ( v11 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_12:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v10 = 0;
  result = a2;
  *(_DWORD *)a2 = v10 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x140015fc8  push    rbx
0x140015fca  push    rbp
0x140015fcb  push    rsi
0x140015fcc  push    rdi
0x140015fcd  sub     rsp, 28h
0x140015fd1  mov     ecx, 34217D1h; this
0x140015fd6  mov     rbx, rdx
0x140015fd9  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x140015fde  mov     edx, eax
0x140015fe0  mov     qword ptr [rbx], 0
0x140015fe7  and     edx, 0FFFFFF3Fh
0x140015fed  mov     ecx, eax
0x140015fef  and     eax, 80h
0x140015ff4  mov     r8d, edx
0x140015ff7  and     r8d, 3
0x140015ffb  mov     ebp, 40h ; '@'
0x140016000  shl     r8d, 2
0x140016004  and     ecx, ebp
0x140016006  or      r8d, ecx
0x140016009  shl     r8d, 2
0x14001600d  or      r8d, eax
0x140016010  shl     r8d, 3
0x140016014  test    edx, edx
0x140016016  jnz     short loc_14001601C
0x140016018  mov     eax, ebp
0x14001601a  jmp     short loc_140016024
0x14001601c  xor     eax, eax
0x14001601e  cmp     edx, 2
0x140016021  cmovz   eax, ebp
0x140016024  or      r8d, eax
0x140016027  mov     edi, 1
0x14001602c  mov     [rbx], r8d
0x14001602f  bt      r8d, 0Ah
0x140016034  jnb     short loc_140016044
0x140016036  cmp     r8d, 800h
0x14001603d  jb      short loc_140016044
0x14001603f  mov     sil, dil
0x140016042  jmp     short loc_14001604E
0x140016044  xor     sil, sil
0x140016047  xor     al, al
0x140016049  test    bpl, r8b
0x14001604c  jz      short loc_140016067
0x14001604e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x140016055  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x14001605a  test    sil, sil
0x14001605d  jz      short loc_140016067
0x14001605f  test    al, al
0x140016061  jnz     short loc_140016067
0x140016063  btr     dword ptr [rbx], 0Ah
0x140016067  mov     ecx, [rbx]
0x140016069  test    bpl, cl
0x14001606c  jz      short loc_140016072
0x14001606e  test    al, al
0x140016070  jnz     short loc_140016074
0x140016072  xor     edi, edi
0x140016074  and     ecx, 0FFFFFFFEh
0x140016077  mov     rax, rbx
0x14001607a  or      ecx, edi
0x14001607c  mov     [rbx], ecx
0x14001607e  add     rsp, 28h
0x140016082  pop     rdi
0x140016083  pop     rsi
0x140016084  pop     rbp
0x140016085  pop     rbx
0x140016086  retn
```
