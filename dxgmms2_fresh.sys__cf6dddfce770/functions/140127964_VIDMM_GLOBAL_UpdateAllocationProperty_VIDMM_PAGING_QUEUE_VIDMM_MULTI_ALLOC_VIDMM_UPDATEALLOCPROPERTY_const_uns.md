# VIDMM_GLOBAL::UpdateAllocationProperty(VIDMM_PAGING_QUEUE *,VIDMM_MULTI_ALLOC *,VIDMM_UPDATEALLOCPROPERTY const *,unsigned __int64 *)

- ea: `0x140127964`
- end: `0x140127dc8`
- name: `?UpdateAllocationProperty@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_QUEUE@@PEAUVIDMM_MULTI_ALLOC@@PEBUVIDMM_UPDATEALLOCPROPERTY@@PEA_K@Z`
- size: `1124`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_PAGING_QUEUE *@<rdx>, struct VIDMM_MULTI_ALLOC *@<r8>, const struct VIDMM_UPDATEALLOCPROPERTY *@<r9>, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14003e480`

## callees

- `0x140004268`
- `0x140059380`
- `0x1400be9ec`
- `0x1400bf03c`
- `0x1400c1108`
- `0x1400ea904`
- `0x14010ea78`
- `0x14010ee94`
- `0x140127964`

## import_xrefs

- `watchdog!WdLogSingleEntry0` at `0x140127b2a`
- `watchdog!WdLogSingleEntry0` at `0x140127b8e`
- `watchdog!WdLogSingleEntry0` at `0x140127bc3`
- `watchdog!WdLogSingleEntry0` at `0x140127d05`
- `watchdog!WdLogSingleEntry0` at `0x140127d81`
- `watchdog!WdLogSingleEntry0` at `0x140127b2a`
- `watchdog!WdLogSingleEntry0` at `0x140127b8e`
- `watchdog!WdLogSingleEntry0` at `0x140127bc3`
- `watchdog!WdLogSingleEntry0` at `0x140127d05`
- `watchdog!WdLogSingleEntry0` at `0x140127d81`
- `watchdog!WdLogSingleEntry1` at `0x140127a26`
- `watchdog!WdLogSingleEntry1` at `0x140127a7c`
- `watchdog!WdLogSingleEntry1` at `0x140127ac6`
- `watchdog!WdLogSingleEntry1` at `0x140127c0c`
- `watchdog!WdLogSingleEntry1` at `0x140127c6d`
- `watchdog!WdLogSingleEntry1` at `0x140127ccf`
- `watchdog!WdLogSingleEntry1` at `0x140127d41`
- `watchdog!WdLogSingleEntry1` at `0x140127a26`
- `watchdog!WdLogSingleEntry1` at `0x140127a7c`
- `watchdog!WdLogSingleEntry1` at `0x140127ac6`
- `watchdog!WdLogSingleEntry1` at `0x140127c0c`
- `watchdog!WdLogSingleEntry1` at `0x140127c6d`
- `watchdog!WdLogSingleEntry1` at `0x140127ccf`
- `watchdog!WdLogSingleEntry1` at `0x140127d41`

## string_xrefs

- `0x140127ce0`: `May not remove AccessedPhysically on allocations that have AccessedPhysically enabled, returning 0x%I64x`
- `0x140127d52`: `SetUnmoveable is not supported, returning 0x%I64x`

## pseudocode

```c
__int64 __fastcall VIDMM_GLOBAL::UpdateAllocationProperty(
        VIDMM_GLOBAL *this,
        struct VIDMM_PAGING_QUEUE *a2,
        struct VIDMM_MULTI_ALLOC *a3,
        const struct VIDMM_UPDATEALLOCPROPERTY *a4,
        unsigned __int64 *a5)
{
  struct _D3DDDI_SEGMENTPREFERENCE v8; // edx
  unsigned int v9; // esi
  int v10; // r14d
  int v11; // ecx
  __int64 **v12; // rax
  __int64 *v13; // r13
  __int64 v14; // rax
  __int64 v15; // r9
  const struct VIDMM_PHYSICAL_ADAPTER *v16; // r15
  unsigned int v17; // ebx
  __int64 v18; // r9
  __int64 v19; // r10
  int v20; // ecx
  int v21; // r8d
  const wchar_t *v22; // r9
  struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 *v24; // r8
  bool v25; // al
  int v26; // ecx
  int v27; // r8d
  __int64 v28; // rbx
  int v29; // ecx
  int v30; // r8d
  const struct VIDMM_SEGMENT_BASE *MostPreferredSegment; // rax
  int v32; // ecx
  int v33; // r8d
  char v34; // dl
  int v35; // ecx
  int v36; // r8d
  int v37; // ecx
  int v38; // r8d
  __int64 v39; // [rsp+50h] [rbp-61h] BYREF
  __int64 v40; // [rsp+58h] [rbp-59h]
  _QWORD v41[20]; // [rsp+60h] [rbp-51h] BYREF
  int v44; // [rsp+120h] [rbp+6Fh] BYREF
  unsigned int v45; // [rsp+128h] [rbp+77h]

  memset(v41, 0, 0x58u);
  v8.0 = (struct _D3DDDI_SEGMENTPREFERENCE::$F972DAF4C5B61B4C701096F96A6C826A::$59FADADC9B5649AD99C3978E94186D1F)*((_DWORD *)a4 + 1);
  v9 = *(_DWORD *)a4;
  v10 = *((_DWORD *)a4 + 3);
  v11 = *((_DWORD *)a3 + 8);
  v45 = *((_DWORD *)a4 + 2);
  v12 = *(__int64 ***)a3;
  LODWORD(v41[0]) = 214;
  v41[2] = a3;
  v13 = *v12;
  v14 = *((_QWORD *)this + 4560);
  HIDWORD(v41[4]) = v9;
  v41[5] = __PAIR64__(v45, v8.Value);
  v15 = *v13;
  v16 = *(const struct VIDMM_PHYSICAL_ADAPTER **)(v14 + 8LL * ((unsigned __int8)v11 >> 2));
  LODWORD(v41[6]) = v10;
  v39 = 0;
  v17 = *(_DWORD *)(v15 + 40);
  v40 = *(_QWORD *)(v15 + 48);
  VidMmConvertSegmentPreferences(this, v8, (struct VIDMM_SEGMENT_PREFERENCES *)&v39);
  if ( (v10 & 2) != 0 )
  {
    if ( !v9 )
    {
      WdLogSingleEntry1(1, -1073741811);
      v22 = L"SupportedSegmentSet may not be empty, returning 0x%I64x";
      WdLogGlobalForLineNumber = 6459;
LABEL_4:
      DxgkLogInternalTriageEvent(v20, 0x40000, v21, (_DWORD)v22, -1073741811, 0, 0, 0);
      return 3221225485LL;
    }
    if ( (v9 & *((_DWORD *)v16 + 20)) == 0 )
    {
      WdLogSingleEntry1(1, -1073741811);
      v22 = L"Specified supported segment set may only contain driver segments, returning 0x%I64x";
      WdLogGlobalForLineNumber = 6471;
      goto LABEL_4;
    }
    if ( (*(_DWORD *)(*((_QWORD *)a3 + 2) + 72LL) & 0x200000) == 0 && (*((_DWORD *)a3 + 7) & 8) != 0 && (~v17 & v9) != 0 )
    {
      WdLogSingleEntry1(1, -1073741811);
      v22 = L"Specified supported segment set may not add segments to shareable alloc, returning 0x%I64x";
      WdLogGlobalForLineNumber = 6484;
      goto LABEL_4;
    }
    v24 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 *)v13[49];
    v25 = (v13[3] & 0x800000) != 0;
    v44 = 0;
    if ( !VidMmVerifySupportedSegmentSetAndAdjustFlags(
            v16,
            v9,
            v24,
            *(_QWORD *)(v18 + 16),
            *(_QWORD *)(v18 + 24),
            v25,
            (struct _VIDMM_VERIFY_SUPPORTED_SEGMENT *)&v44) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 6493;
      DxgkLogInternalTriageEvent(
        v26,
        0x40000,
        v27,
        (unsigned int)L"VidMmVerifySupportedSegmentSetAndAdjustFlags failed.\n",
        6493,
        0,
        0,
        0);
      return -1073741811;
    }
    BYTE4(v41[6]) = v44 & 1;
    BYTE5(v41[6]) = (v44 & 2) != 0;
    if ( v9 == v17 )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 6502;
    }
    v19 = v40;
  }
  else
  {
    v9 = v17;
  }
  if ( (v10 & 4) != 0 )
  {
    v28 = v39;
    if ( v39 == v19 )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 6513;
    }
  }
  else
  {
    v28 = v19;
  }
  if ( (v10 & 2) != 0 || (v10 & 4) != 0 )
  {
    if ( !(unsigned __int8)VidMmValidatePreferredSegment(v16, v28, v9) )
    {
      WdLogSingleEntry1(1, -1073741811);
      WdLogGlobalForLineNumber = 6525;
      DxgkLogInternalTriageEvent(
        v29,
        0x40000,
        v30,
        (unsigned int)L"Current preferred segment is invalid. It must be a subset of the supported segment set, returning 0x%I64x",
        -1073741811,
        0,
        0,
        0);
      return 3221225485LL;
    }
    MostPreferredSegment = (const struct VIDMM_SEGMENT_BASE *)VidMmGetMostPreferredSegment(v16, v28, &v44);
    if ( !VidMmVerifyBudgetGroups(v16, v9, MostPreferredSegment, (struct _VIDMM_VERIFY_BUDGET_GROUPS *)&v41[4]) )
    {
      WdLogSingleEntry1(1, -1073741811);
      WdLogGlobalForLineNumber = 6535;
      DxgkLogInternalTriageEvent(
        v32,
        0x40000,
        v33,
        (unsigned int)L"Failed to VerifyBudgetGroups, returning 0x%I64x",
        -1073741811,
        0,
        0,
        0);
      return 3221225485LL;
    }
    LOBYTE(v10) = v41[6];
    v34 = BYTE4(v41[5]);
  }
  else
  {
    v34 = v45;
  }
  if ( (v10 & 1) != 0 && (*(_DWORD *)v13[49] & 0x8000) != 0 )
  {
    if ( (v34 & 1) == 0 )
    {
      WdLogSingleEntry1(1, -1073741811);
      WdLogGlobalForLineNumber = 6547;
      DxgkLogInternalTriageEvent(
        v35,
        0x40000,
        v36,
        (unsigned int)L"May not remove AccessedPhysically on allocations that have AccessedPhysically enabled, returning 0x%I64x",
        -1073741811,
        0,
        0,
        0);
      return 3221225485LL;
    }
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 6554;
  }
  if ( (v10 & 8) != 0 )
  {
    if ( (*(_DWORD *)(*((_QWORD *)this + 3) + 444LL) & 0x200) == 0 )
    {
      WdLogSingleEntry1(1, -1073741811);
      WdLogGlobalForLineNumber = 6564;
      DxgkLogInternalTriageEvent(
        v37,
        0x40000,
        v38,
        (unsigned int)L"SetUnmoveable is not supported, returning 0x%I64x",
        -1073741811,
        0,
        0,
        0);
      return 3221225485LL;
    }
    if ( (*((_DWORD *)v13 + 7) & 0x800) != 0 )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 6571;
    }
  }
  return VIDMM_GLOBAL::QueueDeferredCommand(this, a2, (struct _VIDMM_DEFERRED_COMMAND *)v41, 0, a5);
}

```

## disassembly

```asm
0x140127964  mov     [rsp-8+arg_8], rdx
0x140127969  mov     [rsp-8+arg_0], rcx
0x14012796e  push    rbp
0x14012796f  push    rbx
0x140127970  push    rsi
0x140127971  push    rdi
0x140127972  push    r12
0x140127974  push    r13
0x140127976  push    r14
0x140127978  push    r15
0x14012797a  lea     rbp, [rsp-17h]
0x14012797f  sub     rsp, 0C8h
0x140127986  xor     edx, edx; Val
0x140127988  mov     r12, r8
0x14012798b  mov     rdi, rcx
0x14012798e  mov     rbx, r9
0x140127991  lea     rcx, [rbp+4Fh+var_A0]; void *
0x140127995  lea     r8d, [rdx+58h]; Size
0x140127999  call    memset
0x14012799e  mov     eax, [rbx+8]
0x1401279a1  lea     r8, [rbp+4Fh+var_B0]; struct VIDMM_SEGMENT_PREFERENCES *
0x1401279a5  mov     edx, [rbx+4]; struct _D3DDDI_SEGMENTPREFERENCE
0x1401279a8  mov     esi, [rbx]
0x1401279aa  mov     r14d, [rbx+0Ch]
0x1401279ae  mov     ecx, [r12+20h]
0x1401279b3  mov     [rbp+4Fh+arg_18], eax
0x1401279b6  mov     [rbp+4Fh+var_74], eax
0x1401279b9  mov     rax, [r12]
0x1401279bd  shr     rcx, 2
0x1401279c1  and     ecx, 3Fh
0x1401279c4  mov     [rbp+4Fh+var_A0], 0D6h
0x1401279cb  mov     [rbp+4Fh+var_90], r12
0x1401279cf  mov     r13, [rax]
0x1401279d2  mov     rax, [rdi+8E80h]
0x1401279d9  mov     [rbp+4Fh+var_7C], esi
0x1401279dc  mov     [rbp+4Fh+var_78], edx
0x1401279df  mov     r9, [r13+0]
0x1401279e3  mov     r15, [rax+rcx*8]
0x1401279e7  mov     rcx, rdi; struct VIDMM_GLOBAL *
0x1401279ea  mov     [rbp+4Fh+var_70], r14d
0x1401279ee  mov     [rbp+4Fh+var_B0], 0
0x1401279f6  mov     r10, [r9+30h]
0x1401279fa  mov     ebx, [r9+28h]
0x1401279fe  mov     [rbp+4Fh+var_A8], r10
0x140127a02  call    ?VidMmConvertSegmentPreferences@@YAXPEBVVIDMM_GLOBAL@@U_D3DDDI_SEGMENTPREFERENCE@@PEAUVIDMM_SEGMENT_PREFERENCES@@@Z; VidMmConvertSegmentPreferences(VIDMM_GLOBAL const *,_D3DDDI_SEGMENTPREFERENCE,VIDMM_SEGMENT_PREFERENCES *)
0x140127a07  mov     edi, 1
0x140127a0c  test    r14b, 2
0x140127a10  jz      loc_140127BAA
0x140127a16  test    esi, esi
0x140127a18  jnz     short loc_140127A6A
0x140127a1a  mov     rbx, 0FFFFFFFFC000000Dh
0x140127a21  mov     ecx, edi
0x140127a23  mov     rdx, rbx
0x140127a26  call    cs:__imp_WdLogSingleEntry1
0x140127a2d  nop     dword ptr [rax+rax+00h]
0x140127a32  lea     r9, aSupportedsegme; "SupportedSegmentSet may not be empty, r"...
0x140127a39  mov     cs:WdLogGlobalForLineNumber, 193Bh
0x140127a43  xor     eax, eax
0x140127a45  mov     [rsp+100h+var_C8], rax
0x140127a4a  mov     [rsp+100h+var_D0], rax
0x140127a4f  mov     qword ptr [rsp+100h+var_D8], rax
0x140127a54  mov     edx, 40000h
0x140127a59  mov     [rsp+100h+var_E0], rbx
0x140127a5e  call    DxgkLogInternalTriageEvent
0x140127a63  mov     eax, ebx
0x140127a65  jmp     loc_140127DB3
0x140127a6a  test    [r15+50h], esi
0x140127a6e  jnz     short loc_140127A9B
0x140127a70  mov     rbx, 0FFFFFFFFC000000Dh
0x140127a77  mov     ecx, edi
0x140127a79  mov     rdx, rbx
0x140127a7c  call    cs:__imp_WdLogSingleEntry1
0x140127a83  nop     dword ptr [rax+rax+00h]
0x140127a88  lea     r9, aSpecifiedSuppo; "Specified supported segment set may onl"...
0x140127a8f  mov     cs:WdLogGlobalForLineNumber, 1947h
0x140127a99  jmp     short loc_140127A43
0x140127a9b  mov     rax, [r12+10h]
0x140127aa0  test    dword ptr [rax+48h], 200000h
0x140127aa7  jnz     short loc_140127AE8
0x140127aa9  mov     eax, [r12+1Ch]
0x140127aae  test    al, 8
0x140127ab0  jz      short loc_140127AE8
0x140127ab2  mov     eax, ebx
0x140127ab4  not     eax
0x140127ab6  test    esi, eax
0x140127ab8  jz      short loc_140127AE8
0x140127aba  mov     rbx, 0FFFFFFFFC000000Dh
0x140127ac1  mov     ecx, edi
0x140127ac3  mov     rdx, rbx
0x140127ac6  call    cs:__imp_WdLogSingleEntry1
0x140127acd  nop     dword ptr [rax+rax+00h]
0x140127ad2  lea     r9, aSpecifiedSuppo_0; "Specified supported segment set may not"...
0x140127ad9  mov     cs:WdLogGlobalForLineNumber, 1954h
0x140127ae3  jmp     loc_140127A43
0x140127ae8  mov     eax, [r13+18h]
0x140127aec  lea     rcx, [rbp+4Fh+arg_10]
0x140127af0  mov     r8, [r13+188h]; struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 *
0x140127af7  xor     r12d, r12d
0x140127afa  mov     [rsp+100h+var_D0], rcx; struct _VIDMM_VERIFY_SUPPORTED_SEGMENT *
0x140127aff  mov     edx, esi; unsigned int
0x140127b01  shr     eax, 17h
0x140127b04  mov     rcx, r15; struct VIDMM_PHYSICAL_ADAPTER *
0x140127b07  and     al, dil
0x140127b0a  mov     [rbp+4Fh+arg_10], r12d
0x140127b0e  mov     [rsp+100h+var_D8], al; bool
0x140127b12  mov     rax, [r9+18h]
0x140127b16  mov     r9, [r9+10h]; unsigned __int64
0x140127b1a  mov     [rsp+100h+var_E0], rax; unsigned __int64
0x140127b1f  call    ?VidMmVerifySupportedSegmentSetAndAdjustFlags@@YA_NPEBUVIDMM_PHYSICAL_ADAPTER@@IPEAU_DXGK_ALLOCATIONINFOFLAGS_WDDM2_0@@_K2_NPEAU_VIDMM_VERIFY_SUPPORTED_SEGMENT@@@Z; VidMmVerifySupportedSegmentSetAndAdjustFlags(VIDMM_PHYSICAL_ADAPTER const *,uint,_DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 *,unsigned __int64,unsigned __int64,bool,_VIDMM_VERIFY_SUPPORTED_SEGMENT *)
0x140127b24  test    al, al
0x140127b26  jnz     short loc_140127B72
0x140127b28  mov     ecx, edi
0x140127b2a  call    cs:__imp_WdLogSingleEntry0
0x140127b31  nop     dword ptr [rax+rax+00h]
0x140127b36  mov     [rsp+100h+var_C8], r12
0x140127b3b  lea     r9, aVidmmverifysup_0; "VidMmVerifySupportedSegmentSetAndAdjust"...
0x140127b42  mov     eax, 195Dh
0x140127b47  mov     [rsp+100h+var_D0], r12
0x140127b4c  mov     qword ptr [rsp+100h+var_D8], r12
0x140127b51  mov     edx, 40000h
0x140127b56  mov     cs:WdLogGlobalForLineNumber, eax
0x140127b5c  mov     [rsp+100h+var_E0], rax
0x140127b61  call    DxgkLogInternalTriageEvent
0x140127b66  mov     rax, 0FFFFFFFFC000000Dh
0x140127b6d  jmp     loc_140127DB3
0x140127b72  mov     eax, [rbp+4Fh+arg_10]
0x140127b75  mov     cl, al
0x140127b77  shr     eax, 1
0x140127b79  and     cl, dil
0x140127b7c  and     al, dil
0x140127b7f  mov     [rbp+4Fh+var_6C], cl
0x140127b82  mov     [rbp+4Fh+var_6B], al
0x140127b85  cmp     esi, ebx
0x140127b87  jnz     short loc_140127BA4
0x140127b89  mov     ecx, 3
0x140127b8e  call    cs:__imp_WdLogSingleEntry0
0x140127b95  nop     dword ptr [rax+rax+00h]
0x140127b9a  mov     cs:WdLogGlobalForLineNumber, 1966h
0x140127ba4  mov     r10, [rbp+4Fh+var_A8]
0x140127ba8  jmp     short loc_140127BAF
0x140127baa  mov     esi, ebx
0x140127bac  xor     r12d, r12d
0x140127baf  test    r14b, 4
0x140127bb3  jz      short loc_140127BDB
0x140127bb5  mov     rbx, [rbp+4Fh+var_B0]
0x140127bb9  cmp     rbx, r10
0x140127bbc  jnz     short loc_140127BDE
0x140127bbe  mov     ecx, 3
0x140127bc3  call    cs:__imp_WdLogSingleEntry0
0x140127bca  nop     dword ptr [rax+rax+00h]
0x140127bcf  mov     cs:WdLogGlobalForLineNumber, 1971h
0x140127bd9  jmp     short loc_140127BDE
0x140127bdb  mov     rbx, r10
0x140127bde  test    r14b, 2
0x140127be2  jnz     short loc_140127BEE
0x140127be4  test    r14b, 4
0x140127be8  jz      loc_140127CA7
0x140127bee  mov     r8d, esi
0x140127bf1  mov     rdx, rbx
0x140127bf4  mov     rcx, r15
0x140127bf7  call    ?VidMmValidatePreferredSegment@@YA_NPEBUVIDMM_PHYSICAL_ADAPTER@@UVIDMM_SEGMENT_PREFERENCES@@I@Z; VidMmValidatePreferredSegment(VIDMM_PHYSICAL_ADAPTER const *,VIDMM_SEGMENT_PREFERENCES,uint)
0x140127bfc  test    al, al
0x140127bfe  jnz     short loc_140127C3D
0x140127c00  mov     rbx, 0FFFFFFFFC000000Dh
0x140127c07  mov     ecx, edi
0x140127c09  mov     rdx, rbx
0x140127c0c  call    cs:__imp_WdLogSingleEntry1
0x140127c13  nop     dword ptr [rax+rax+00h]
0x140127c18  mov     [rsp+100h+var_C8], r12
0x140127c1d  lea     r9, aCurrentPreferr; "Current preferred segment is invalid. I"...
0x140127c24  mov     [rsp+100h+var_D0], r12
0x140127c29  mov     qword ptr [rsp+100h+var_D8], r12
0x140127c2e  mov     cs:WdLogGlobalForLineNumber, 197Dh
0x140127c38  jmp     loc_140127A54
0x140127c3d  lea     r8, [rbp+4Fh+arg_10]
0x140127c41  mov     rdx, rbx
0x140127c44  mov     rcx, r15
0x140127c47  call    ?VidMmGetMostPreferredSegment@@YAPEAUVIDMM_SEGMENT_BASE@@PEAUVIDMM_PHYSICAL_ADAPTER@@UVIDMM_SEGMENT_PREFERENCES@@PEA_N@Z; VidMmGetMostPreferredSegment(VIDMM_PHYSICAL_ADAPTER *,VIDMM_SEGMENT_PREFERENCES,bool *)
0x140127c4c  lea     r9, [rbp+4Fh+var_80]; struct _VIDMM_VERIFY_BUDGET_GROUPS *
0x140127c50  mov     r8, rax; struct VIDMM_SEGMENT_BASE *
0x140127c53  mov     edx, esi; unsigned int
0x140127c55  mov     rcx, r15; struct VIDMM_PHYSICAL_ADAPTER *
0x140127c58  call    ?VidMmVerifyBudgetGroups@@YA_NPEBUVIDMM_PHYSICAL_ADAPTER@@IPEBUVIDMM_SEGMENT_BASE@@PEAU_VIDMM_VERIFY_BUDGET_GROUPS@@@Z; VidMmVerifyBudgetGroups(VIDMM_PHYSICAL_ADAPTER const *,uint,VIDMM_SEGMENT_BASE const *,_VIDMM_VERIFY_BUDGET_GROUPS *)
0x140127c5d  test    al, al
0x140127c5f  jnz     short loc_140127C9E
0x140127c61  mov     rbx, 0FFFFFFFFC000000Dh
0x140127c68  mov     ecx, edi
0x140127c6a  mov     rdx, rbx
0x140127c6d  call    cs:__imp_WdLogSingleEntry1
0x140127c74  nop     dword ptr [rax+rax+00h]
0x140127c79  mov     [rsp+100h+var_C8], r12
0x140127c7e  lea     r9, aFailedToVerify; "Failed to VerifyBudgetGroups, returning"...
0x140127c85  mov     [rsp+100h+var_D0], r12
0x140127c8a  mov     qword ptr [rsp+100h+var_D8], r12
0x140127c8f  mov     cs:WdLogGlobalForLineNumber, 1987h
0x140127c99  jmp     loc_140127A54
0x140127c9e  mov     r14d, [rbp+4Fh+var_70]
0x140127ca2  mov     edx, [rbp+4Fh+var_74]
0x140127ca5  jmp     short loc_140127CAA
0x140127ca7  mov     edx, [rbp+4Fh+arg_18]
0x140127caa  test    dil, r14b
0x140127cad  jz      short loc_140127D1B
0x140127caf  mov     rax, [r13+188h]
0x140127cb6  test    dword ptr [rax], 8000h
0x140127cbc  jz      short loc_140127D1B
0x140127cbe  test    dil, dl
0x140127cc1  jnz     short loc_140127D00
0x140127cc3  mov     rbx, 0FFFFFFFFC000000Dh
0x140127cca  mov     ecx, edi
0x140127ccc  mov     rdx, rbx
0x140127ccf  call    cs:__imp_WdLogSingleEntry1
0x140127cd6  nop     dword ptr [rax+rax+00h]
0x140127cdb  mov     [rsp+100h+var_C8], r12
0x140127ce0  lea     r9, aMayNotRemoveAc; "May not remove AccessedPhysically on al"...
0x140127ce7  mov     [rsp+100h+var_D0], r12
0x140127cec  mov     qword ptr [rsp+100h+var_D8], r12
0x140127cf1  mov     cs:WdLogGlobalForLineNumber, 1993h
0x140127cfb  jmp     loc_140127A54
0x140127d00  mov     ecx, 3
0x140127d05  call    cs:__imp_WdLogSingleEntry0
0x140127d0c  nop     dword ptr [rax+rax+00h]
0x140127d11  mov     cs:WdLogGlobalForLineNumber, 199Ah
0x140127d1b  mov     rbx, [rbp+4Fh+arg_0]
0x140127d1f  test    r14b, 8
0x140127d23  jz      short loc_140127D97
0x140127d25  mov     rax, [rbx+18h]
0x140127d29  test    dword ptr [rax+1BCh], 200h
0x140127d33  jnz     short loc_140127D72
0x140127d35  mov     rbx, 0FFFFFFFFC000000Dh
0x140127d3c  mov     ecx, edi
0x140127d3e  mov     rdx, rbx
0x140127d41  call    cs:__imp_WdLogSingleEntry1
0x140127d48  nop     dword ptr [rax+rax+00h]
0x140127d4d  mov     [rsp+100h+var_C8], r12
0x140127d52  lea     r9, aSetunmoveableI; "SetUnmoveable is not supported, returni"...
0x140127d59  mov     [rsp+100h+var_D0], r12
0x140127d5e  mov     qword ptr [rsp+100h+var_D8], r12
0x140127d63  mov     cs:WdLogGlobalForLineNumber, 19A4h
0x140127d6d  jmp     loc_140127A54
0x140127d72  test    dword ptr [r13+1Ch], 800h
0x140127d7a  jz      short loc_140127D97
0x140127d7c  mov     ecx, 3
0x140127d81  call    cs:__imp_WdLogSingleEntry0
0x140127d88  nop     dword ptr [rax+rax+00h]
0x140127d8d  mov     cs:WdLogGlobalForLineNumber, 19ABh
0x140127d97  mov     rax, [rbp+4Fh+arg_20]
0x140127d9b  lea     r8, [rbp+4Fh+var_A0]; struct _VIDMM_DEFERRED_COMMAND *
0x140127d9f  mov     rdx, [rbp+4Fh+arg_8]; struct VIDMM_PAGING_QUEUE *
0x140127da3  xor     r9d, r9d; bool
0x140127da6  mov     rcx, rbx; this
0x140127da9  mov     [rsp+100h+var_E0], rax; unsigned __int64 *
0x140127dae  call    ?QueueDeferredCommand@VIDMM_GLOBAL@@QEAAJAEAUVIDMM_PAGING_QUEUE@@PEAU_VIDMM_DEFERRED_COMMAND@@_NPEA_K@Z; VIDMM_GLOBAL::QueueDeferredCommand(VIDMM_PAGING_QUEUE &,_VIDMM_DEFERRED_COMMAND *,bool,unsigned __int64 *)
0x140127db3  add     rsp, 0C8h
0x140127dba  pop     r15
0x140127dbc  pop     r14
0x140127dbe  pop     r13
0x140127dc0  pop     r12
0x140127dc2  pop     rdi
0x140127dc3  pop     rsi
0x140127dc4  pop     rbx
0x140127dc5  pop     rbp
0x140127dc6  retn
```
