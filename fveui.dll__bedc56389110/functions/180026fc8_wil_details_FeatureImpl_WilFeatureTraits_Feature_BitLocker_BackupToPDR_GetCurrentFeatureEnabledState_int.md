# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_BackupToPDR>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180026fc8`
- end: `0x1800270af`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_BackupToPDR@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `231`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002611c`

## callees

- `0x18002331c`
- `0x180026fc8`
- `0x18002907c`
- `0x1800290b8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_BackupToPDR>::GetCurrentFeatureEnabledState(
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
  bool v13; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x355BBCC, 3u, a3, a4);
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
      goto LABEL_17;
  }
  v13 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DirectCloudSync>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DirectCloudSync>::GetImpl'::`2'::impl)
     && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CDSFlatBuffers>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CDSFlatBuffers>::GetImpl'::`2'::impl);
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_17:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180026fc8  push    rbx
0x180026fca  push    rbp
0x180026fcb  push    rsi
0x180026fcc  push    rdi
0x180026fcd  sub     rsp, 28h
0x180026fd1  mov     rbx, rdx
0x180026fd4  mov     ecx, 355BBCCh; this
0x180026fd9  mov     edx, 3; unsigned int
0x180026fde  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180026fe3  mov     edx, eax
0x180026fe5  mov     qword ptr [rbx], 0
0x180026fec  and     edx, 0FFFFFF3Fh
0x180026ff2  mov     ecx, eax
0x180026ff4  and     eax, 80h
0x180026ff9  mov     r8d, edx
0x180026ffc  and     r8d, 3
0x180027000  mov     ebp, 40h ; '@'
0x180027005  shl     r8d, 2
0x180027009  and     ecx, ebp
0x18002700b  or      r8d, ecx
0x18002700e  shl     r8d, 2
0x180027012  or      r8d, eax
0x180027015  shl     r8d, 3
0x180027019  test    edx, edx
0x18002701b  jnz     short loc_180027023
0x18002701d  mov     ecx, ebp
0x18002701f  mov     edx, ebp
0x180027021  jmp     short loc_18002702D
0x180027023  xor     ecx, ecx
0x180027025  cmp     edx, 2
0x180027028  cmovz   ecx, ebp
0x18002702b  mov     edx, ecx
0x18002702d  mov     eax, r8d
0x180027030  mov     edi, 1
0x180027035  or      eax, edx
0x180027037  or      r8d, ecx
0x18002703a  mov     [rbx], eax
0x18002703c  bt      r8d, 0Ah
0x180027041  jnb     short loc_180027051
0x180027043  cmp     r8d, 800h
0x18002704a  jb      short loc_180027051
0x18002704c  mov     sil, dil
0x18002704f  jmp     short loc_18002705B
0x180027051  xor     sil, sil
0x180027054  xor     cl, cl
0x180027056  test    bpl, r8b
0x180027059  jz      short loc_18002708F
0x18002705b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DirectCloudSync@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DirectCloudSync@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DirectCloudSync> `wil::Feature<__WilFeatureTraits_Feature_DirectCloudSync>::GetImpl(void)'::`2'::impl
0x180027062  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DirectCloudSync@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DirectCloudSync>::__private_IsEnabled(wil::ReportingKind)
0x180027067  test    al, al
0x180027069  jz      short loc_180027080
0x18002706b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CDSFlatBuffers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CDSFlatBuffers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CDSFlatBuffers> `wil::Feature<__WilFeatureTraits_Feature_CDSFlatBuffers>::GetImpl(void)'::`2'::impl
0x180027072  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CDSFlatBuffers@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CDSFlatBuffers>::__private_IsEnabled(wil::ReportingKind)
0x180027077  test    al, al
0x180027079  jz      short loc_180027080
0x18002707b  mov     cl, dil
0x18002707e  jmp     short loc_180027082
0x180027080  xor     cl, cl
0x180027082  test    sil, sil
0x180027085  jz      short loc_18002708F
0x180027087  test    cl, cl
0x180027089  jnz     short loc_18002708F
0x18002708b  btr     dword ptr [rbx], 0Ah
0x18002708f  mov     eax, [rbx]
0x180027091  test    bpl, al
0x180027094  jz      short loc_18002709A
0x180027096  test    cl, cl
0x180027098  jnz     short loc_18002709C
0x18002709a  xor     edi, edi
0x18002709c  and     eax, 0FFFFFFFEh
0x18002709f  or      eax, edi
0x1800270a1  mov     [rbx], eax
0x1800270a3  mov     rax, rbx
0x1800270a6  add     rsp, 28h
0x1800270aa  pop     rdi
0x1800270ab  pop     rsi
0x1800270ac  pop     rbp
0x1800270ad  pop     rbx
0x1800270ae  retn
```
