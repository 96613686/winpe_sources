# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180010778`
- end: `0x18001085b`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800101f4`

## callees

- `0x180010778`
- `0x180011a10`
- `0x180012298`
- `0x1800123b8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CAD, 3u, a3, a4);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetImpl'::`2'::impl);
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
0x180010778  push    rbx
0x18001077a  push    rbp
0x18001077b  push    rsi
0x18001077c  push    rdi
0x18001077d  sub     rsp, 28h
0x180010781  mov     rbx, rdx
0x180010784  mov     ecx, 3667CADh; this
0x180010789  mov     edx, 3; unsigned int
0x18001078e  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180010793  mov     edx, eax
0x180010795  mov     qword ptr [rbx], 0
0x18001079c  and     edx, 0FFFFFF3Fh
0x1800107a2  mov     ecx, eax
0x1800107a4  and     eax, 80h
0x1800107a9  mov     r8d, edx
0x1800107ac  and     r8d, 3
0x1800107b0  mov     ebp, 40h ; '@'
0x1800107b5  shl     r8d, 2
0x1800107b9  and     ecx, ebp
0x1800107bb  or      r8d, ecx
0x1800107be  shl     r8d, 2
0x1800107c2  or      r8d, eax
0x1800107c5  shl     r8d, 3
0x1800107c9  test    edx, edx
0x1800107cb  jnz     short loc_1800107D3
0x1800107cd  mov     ecx, ebp
0x1800107cf  mov     edx, ebp
0x1800107d1  jmp     short loc_1800107DD
0x1800107d3  xor     ecx, ecx
0x1800107d5  cmp     edx, 2
0x1800107d8  cmovz   ecx, ebp
0x1800107db  mov     edx, ecx
0x1800107dd  mov     eax, r8d
0x1800107e0  mov     edi, 1
0x1800107e5  or      eax, edx
0x1800107e7  or      r8d, ecx
0x1800107ea  mov     [rbx], eax
0x1800107ec  bt      r8d, 0Ah
0x1800107f1  jnb     short loc_180010801
0x1800107f3  cmp     r8d, 800h
0x1800107fa  jb      short loc_180010801
0x1800107fc  mov     sil, dil
0x1800107ff  jmp     short loc_18001080B
0x180010801  xor     sil, sil
0x180010804  xor     cl, cl
0x180010806  test    bpl, r8b
0x180010809  jz      short loc_18001083B
0x18001080b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x180010812  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x180010817  test    al, al
0x180010819  jz      short loc_18001082C
0x18001081b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetImpl(void)'::`2'::impl
0x180010822  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180010827  mov     cl, dil
0x18001082a  jmp     short loc_18001082E
0x18001082c  xor     cl, cl
0x18001082e  test    sil, sil
0x180010831  jz      short loc_18001083B
0x180010833  test    cl, cl
0x180010835  jnz     short loc_18001083B
0x180010837  btr     dword ptr [rbx], 0Ah
0x18001083b  mov     eax, [rbx]
0x18001083d  test    bpl, al
0x180010840  jz      short loc_180010846
0x180010842  test    cl, cl
0x180010844  jnz     short loc_180010848
0x180010846  xor     edi, edi
0x180010848  and     eax, 0FFFFFFFEh
0x18001084b  or      eax, edi
0x18001084d  mov     [rbx], eax
0x18001084f  mov     rax, rbx
0x180010852  add     rsp, 28h
0x180010856  pop     rdi
0x180010857  pop     rsi
0x180010858  pop     rbp
0x180010859  pop     rbx
0x18001085a  retn
```
