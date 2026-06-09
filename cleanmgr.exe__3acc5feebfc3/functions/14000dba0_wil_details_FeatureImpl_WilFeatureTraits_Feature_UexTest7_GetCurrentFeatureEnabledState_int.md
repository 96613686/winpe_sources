# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000dba0`
- end: `0x14000dc83`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `227`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d304`

## callees

- `0x140009c64`
- `0x14000dba0`
- `0x14000e6f8`
- `0x14000ec20`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // si
  char v13; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419DD, 3u, a3, a4);
  *a2 = 0;
  v6 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (FeatureEnabledState & 0xFFFFFF3F) == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_16;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetImpl'::`2'::impl);
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_16:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x14000dba0  push    rbx
0x14000dba2  push    rbp
0x14000dba3  push    rsi
0x14000dba4  push    rdi
0x14000dba5  sub     rsp, 28h
0x14000dba9  mov     rbx, rdx
0x14000dbac  mov     ecx, 38419DDh; this
0x14000dbb1  mov     edx, 3; unsigned int
0x14000dbb6  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14000dbbb  mov     edx, eax
0x14000dbbd  mov     qword ptr [rbx], 0
0x14000dbc4  and     edx, 0FFFFFF3Fh
0x14000dbca  mov     ecx, eax
0x14000dbcc  and     eax, 80h
0x14000dbd1  mov     r8d, edx
0x14000dbd4  and     r8d, 3
0x14000dbd8  mov     ebp, 40h ; '@'
0x14000dbdd  shl     r8d, 2
0x14000dbe1  and     ecx, ebp
0x14000dbe3  or      r8d, ecx
0x14000dbe6  shl     r8d, 2
0x14000dbea  or      r8d, eax
0x14000dbed  shl     r8d, 3
0x14000dbf1  test    edx, edx
0x14000dbf3  jnz     short loc_14000DBFB
0x14000dbf5  mov     ecx, ebp
0x14000dbf7  mov     edx, ebp
0x14000dbf9  jmp     short loc_14000DC05
0x14000dbfb  xor     ecx, ecx
0x14000dbfd  cmp     edx, 2
0x14000dc00  cmovz   ecx, ebp
0x14000dc03  mov     edx, ecx
0x14000dc05  mov     eax, r8d
0x14000dc08  mov     edi, 1
0x14000dc0d  or      eax, edx
0x14000dc0f  or      r8d, ecx
0x14000dc12  mov     [rbx], eax
0x14000dc14  bt      r8d, 0Ah
0x14000dc19  jnb     short loc_14000DC29
0x14000dc1b  cmp     r8d, 800h
0x14000dc22  jb      short loc_14000DC29
0x14000dc24  mov     sil, dil
0x14000dc27  jmp     short loc_14000DC33
0x14000dc29  xor     sil, sil
0x14000dc2c  xor     cl, cl
0x14000dc2e  test    bpl, r8b
0x14000dc31  jz      short loc_14000DC63
0x14000dc33  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x14000dc3a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x14000dc3f  test    al, al
0x14000dc41  jz      short loc_14000DC54
0x14000dc43  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetImpl(void)'::`2'::impl
0x14000dc4a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14000dc4f  mov     cl, dil
0x14000dc52  jmp     short loc_14000DC56
0x14000dc54  xor     cl, cl
0x14000dc56  test    sil, sil
0x14000dc59  jz      short loc_14000DC63
0x14000dc5b  test    cl, cl
0x14000dc5d  jnz     short loc_14000DC63
0x14000dc5f  btr     dword ptr [rbx], 0Ah
0x14000dc63  mov     eax, [rbx]
0x14000dc65  test    bpl, al
0x14000dc68  jz      short loc_14000DC6E
0x14000dc6a  test    cl, cl
0x14000dc6c  jnz     short loc_14000DC70
0x14000dc6e  xor     edi, edi
0x14000dc70  and     eax, 0FFFFFFFEh
0x14000dc73  or      eax, edi
0x14000dc75  mov     [rbx], eax
0x14000dc77  mov     rax, rbx
0x14000dc7a  add     rsp, 28h
0x14000dc7e  pop     rdi
0x14000dc7f  pop     rsi
0x14000dc80  pop     rbp
0x14000dc81  pop     rbx
0x14000dc82  retn
```
