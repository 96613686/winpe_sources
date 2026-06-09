# VIDMM_GLOBAL::UpdateAllocationProperty(VIDMM_PAGING_QUEUE *,VIDMM_MULTI_ALLOC *,VIDMM_UPDATEALLOCPROPERTY const *,unsigned __int64 *)

- ea: `0x1401232c8`
- end: `0x14012372c`
- name: `?UpdateAllocationProperty@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_QUEUE@@PEAUVIDMM_MULTI_ALLOC@@PEBUVIDMM_UPDATEALLOCPROPERTY@@PEA_K@Z`
- size: `1124`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_PAGING_QUEUE *@<rdx>, struct VIDMM_MULTI_ALLOC *@<r8>, const struct VIDMM_UPDATEALLOCPROPERTY *@<r9>, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14003fb00`

## callees

- `0x1400045ec`
- `0x140058ac0`
- `0x1400baf4c`
- `0x1400bb59c`
- `0x1400bd658`
- `0x1400e2504`
- `0x14010aef8`
- `0x14010b314`
- `0x1401232c8`

## import_xrefs

- `watchdog!WdLogSingleEntry0` at `0x14012348e`
- `watchdog!WdLogSingleEntry0` at `0x1401234f2`
- `watchdog!WdLogSingleEntry0` at `0x140123527`
- `watchdog!WdLogSingleEntry0` at `0x140123669`
- `watchdog!WdLogSingleEntry0` at `0x1401236e5`
- `watchdog!WdLogSingleEntry0` at `0x14012348e`
- `watchdog!WdLogSingleEntry0` at `0x1401234f2`
- `watchdog!WdLogSingleEntry0` at `0x140123527`
- `watchdog!WdLogSingleEntry0` at `0x140123669`
- `watchdog!WdLogSingleEntry0` at `0x1401236e5`
- `watchdog!WdLogSingleEntry1` at `0x14012338a`
- `watchdog!WdLogSingleEntry1` at `0x1401233e0`
- `watchdog!WdLogSingleEntry1` at `0x14012342a`
- `watchdog!WdLogSingleEntry1` at `0x140123570`
- `watchdog!WdLogSingleEntry1` at `0x1401235d1`
- `watchdog!WdLogSingleEntry1` at `0x140123633`
- `watchdog!WdLogSingleEntry1` at `0x1401236a5`
- `watchdog!WdLogSingleEntry1` at `0x14012338a`
- `watchdog!WdLogSingleEntry1` at `0x1401233e0`
- `watchdog!WdLogSingleEntry1` at `0x14012342a`
- `watchdog!WdLogSingleEntry1` at `0x140123570`
- `watchdog!WdLogSingleEntry1` at `0x1401235d1`
- `watchdog!WdLogSingleEntry1` at `0x140123633`
- `watchdog!WdLogSingleEntry1` at `0x1401236a5`

## string_xrefs

- `0x140123644`: `May not remove AccessedPhysically on allocations that have AccessedPhysically enabled, returning 0x%I64x`
- `0x1401236b6`: `SetUnmoveable is not supported, returning 0x%I64x`

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
      WdLogGlobalForLineNumber = 6318;
LABEL_4:
      DxgkLogInternalTriageEvent(v20, 0x40000, v21, (_DWORD)v22, -1073741811, 0, 0, 0);
      return 3221225485LL;
    }
    if ( (v9 & *((_DWORD *)v16 + 20)) == 0 )
    {
      WdLogSingleEntry1(1, -1073741811);
      v22 = L"Specified supported segment set may only contain driver segments, returning 0x%I64x";
      WdLogGlobalForLineNumber = 6330;
      goto LABEL_4;
    }
    if ( (*(_DWORD *)(*((_QWORD *)a3 + 2) + 72LL) & 0x200000) == 0 && (*((_DWORD *)a3 + 7) & 8) != 0 && (~v17 & v9) != 0 )
    {
      WdLogSingleEntry1(1, -1073741811);
      v22 = L"Specified supported segment set may not add segments to shareable alloc, returning 0x%I64x";
      WdLogGlobalForLineNumber = 6343;
      goto LABEL_4;
    }
    v24 = (struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 *)v13[48];
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
      WdLogGlobalForLineNumber = 6352;
      DxgkLogInternalTriageEvent(
        v26,
        0x40000,
        v27,
        (unsigned int)L"VidMmVerifySupportedSegmentSetAndAdjustFlags failed.\n",
        6352,
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
      WdLogGlobalForLineNumber = 6361;
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
      WdLogGlobalForLineNumber = 6372;
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
      WdLogGlobalForLineNumber = 6384;
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
      WdLogGlobalForLineNumber = 6394;
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
  if ( (v10 & 1) != 0 && (*(_DWORD *)v13[48] & 0x8000) != 0 )
  {
    if ( (v34 & 1) == 0 )
    {
      WdLogSingleEntry1(1, -1073741811);
      WdLogGlobalForLineNumber = 6406;
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
    WdLogGlobalForLineNumber = 6413;
  }
  if ( (v10 & 8) != 0 )
  {
    if ( (*(_DWORD *)(*((_QWORD *)this + 3) + 444LL) & 0x200) == 0 )
    {
      WdLogSingleEntry1(1, -1073741811);
      WdLogGlobalForLineNumber = 6423;
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
      WdLogGlobalForLineNumber = 6430;
    }
  }
  return VIDMM_GLOBAL::QueueDeferredCommand(this, a2, (struct _VIDMM_DEFERRED_COMMAND *)v41, 0, a5);
}

```

## disassembly

```asm
0x1401232c8  mov     [rsp-8+arg_8], rdx
0x1401232cd  mov     [rsp-8+arg_0], rcx
0x1401232d2  push    rbp
0x1401232d3  push    rbx
0x1401232d4  push    rsi
0x1401232d5  push    rdi
0x1401232d6  push    r12
0x1401232d8  push    r13
0x1401232da  push    r14
0x1401232dc  push    r15
0x1401232de  lea     rbp, [rsp-17h]
0x1401232e3  sub     rsp, 0C8h
0x1401232ea  xor     edx, edx; Val
0x1401232ec  mov     r12, r8
0x1401232ef  mov     rdi, rcx
0x1401232f2  mov     rbx, r9
0x1401232f5  lea     rcx, [rbp+4Fh+var_A0]; void *
0x1401232f9  lea     r8d, [rdx+58h]; Size
0x1401232fd  call    memset
0x140123302  mov     eax, [rbx+8]
0x140123305  lea     r8, [rbp+4Fh+var_B0]; struct VIDMM_SEGMENT_PREFERENCES *
0x140123309  mov     edx, [rbx+4]; struct _D3DDDI_SEGMENTPREFERENCE
0x14012330c  mov     esi, [rbx]
0x14012330e  mov     r14d, [rbx+0Ch]
0x140123312  mov     ecx, [r12+20h]
0x140123317  mov     [rbp+4Fh+arg_18], eax
0x14012331a  mov     [rbp+4Fh+var_74], eax
0x14012331d  mov     rax, [r12]
0x140123321  shr     rcx, 2
0x140123325  and     ecx, 3Fh
0x140123328  mov     [rbp+4Fh+var_A0], 0D6h
0x14012332f  mov     [rbp+4Fh+var_90], r12
0x140123333  mov     r13, [rax]
0x140123336  mov     rax, [rdi+8E80h]
0x14012333d  mov     [rbp+4Fh+var_7C], esi
0x140123340  mov     [rbp+4Fh+var_78], edx
0x140123343  mov     r9, [r13+0]
0x140123347  mov     r15, [rax+rcx*8]
0x14012334b  mov     rcx, rdi; struct VIDMM_GLOBAL *
0x14012334e  mov     [rbp+4Fh+var_70], r14d
0x140123352  mov     [rbp+4Fh+var_B0], 0
0x14012335a  mov     r10, [r9+30h]
0x14012335e  mov     ebx, [r9+28h]
0x140123362  mov     [rbp+4Fh+var_A8], r10
0x140123366  call    ?VidMmConvertSegmentPreferences@@YAXPEBVVIDMM_GLOBAL@@U_D3DDDI_SEGMENTPREFERENCE@@PEAUVIDMM_SEGMENT_PREFERENCES@@@Z; VidMmConvertSegmentPreferences(VIDMM_GLOBAL const *,_D3DDDI_SEGMENTPREFERENCE,VIDMM_SEGMENT_PREFERENCES *)
0x14012336b  mov     edi, 1
0x140123370  test    r14b, 2
0x140123374  jz      loc_14012350E
0x14012337a  test    esi, esi
0x14012337c  jnz     short loc_1401233CE
0x14012337e  mov     rbx, 0FFFFFFFFC000000Dh
0x140123385  mov     ecx, edi
0x140123387  mov     rdx, rbx
0x14012338a  call    cs:__imp_WdLogSingleEntry1
0x140123391  nop     dword ptr [rax+rax+00h]
0x140123396  lea     r9, aSupportedsegme; "SupportedSegmentSet may not be empty, r"...
0x14012339d  mov     cs:WdLogGlobalForLineNumber, 18AEh
0x1401233a7  xor     eax, eax
0x1401233a9  mov     [rsp+100h+var_C8], rax
0x1401233ae  mov     [rsp+100h+var_D0], rax
0x1401233b3  mov     qword ptr [rsp+100h+var_D8], rax
0x1401233b8  mov     edx, 40000h
0x1401233bd  mov     [rsp+100h+var_E0], rbx
0x1401233c2  call    DxgkLogInternalTriageEvent
0x1401233c7  mov     eax, ebx
0x1401233c9  jmp     loc_140123717
0x1401233ce  test    [r15+50h], esi
0x1401233d2  jnz     short loc_1401233FF
0x1401233d4  mov     rbx, 0FFFFFFFFC000000Dh
0x1401233db  mov     ecx, edi
0x1401233dd  mov     rdx, rbx
0x1401233e0  call    cs:__imp_WdLogSingleEntry1
0x1401233e7  nop     dword ptr [rax+rax+00h]
0x1401233ec  lea     r9, aSpecifiedSuppo; "Specified supported segment set may onl"...
0x1401233f3  mov     cs:WdLogGlobalForLineNumber, 18BAh
0x1401233fd  jmp     short loc_1401233A7
0x1401233ff  mov     rax, [r12+10h]
0x140123404  test    dword ptr [rax+48h], 200000h
0x14012340b  jnz     short loc_14012344C
0x14012340d  mov     eax, [r12+1Ch]
0x140123412  test    al, 8
0x140123414  jz      short loc_14012344C
0x140123416  mov     eax, ebx
0x140123418  not     eax
0x14012341a  test    esi, eax
0x14012341c  jz      short loc_14012344C
0x14012341e  mov     rbx, 0FFFFFFFFC000000Dh
0x140123425  mov     ecx, edi
0x140123427  mov     rdx, rbx
0x14012342a  call    cs:__imp_WdLogSingleEntry1
0x140123431  nop     dword ptr [rax+rax+00h]
0x140123436  lea     r9, aSpecifiedSuppo_0; "Specified supported segment set may not"...
0x14012343d  mov     cs:WdLogGlobalForLineNumber, 18C7h
0x140123447  jmp     loc_1401233A7
0x14012344c  mov     eax, [r13+18h]
0x140123450  lea     rcx, [rbp+4Fh+arg_10]
0x140123454  mov     r8, [r13+180h]; struct _DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 *
0x14012345b  xor     r12d, r12d
0x14012345e  mov     [rsp+100h+var_D0], rcx; struct _VIDMM_VERIFY_SUPPORTED_SEGMENT *
0x140123463  mov     edx, esi; unsigned int
0x140123465  shr     eax, 17h
0x140123468  mov     rcx, r15; struct VIDMM_PHYSICAL_ADAPTER *
0x14012346b  and     al, dil
0x14012346e  mov     [rbp+4Fh+arg_10], r12d
0x140123472  mov     [rsp+100h+var_D8], al; bool
0x140123476  mov     rax, [r9+18h]
0x14012347a  mov     r9, [r9+10h]; unsigned __int64
0x14012347e  mov     [rsp+100h+var_E0], rax; unsigned __int64
0x140123483  call    ?VidMmVerifySupportedSegmentSetAndAdjustFlags@@YA_NPEBUVIDMM_PHYSICAL_ADAPTER@@IPEAU_DXGK_ALLOCATIONINFOFLAGS_WDDM2_0@@_K2_NPEAU_VIDMM_VERIFY_SUPPORTED_SEGMENT@@@Z; VidMmVerifySupportedSegmentSetAndAdjustFlags(VIDMM_PHYSICAL_ADAPTER const *,uint,_DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 *,unsigned __int64,unsigned __int64,bool,_VIDMM_VERIFY_SUPPORTED_SEGMENT *)
0x140123488  test    al, al
0x14012348a  jnz     short loc_1401234D6
0x14012348c  mov     ecx, edi
0x14012348e  call    cs:__imp_WdLogSingleEntry0
0x140123495  nop     dword ptr [rax+rax+00h]
0x14012349a  mov     [rsp+100h+var_C8], r12
0x14012349f  lea     r9, aVidmmverifysup_0; "VidMmVerifySupportedSegmentSetAndAdjust"...
0x1401234a6  mov     eax, 18D0h
0x1401234ab  mov     [rsp+100h+var_D0], r12
0x1401234b0  mov     qword ptr [rsp+100h+var_D8], r12
0x1401234b5  mov     edx, 40000h
0x1401234ba  mov     cs:WdLogGlobalForLineNumber, eax
0x1401234c0  mov     [rsp+100h+var_E0], rax
0x1401234c5  call    DxgkLogInternalTriageEvent
0x1401234ca  mov     rax, 0FFFFFFFFC000000Dh
0x1401234d1  jmp     loc_140123717
0x1401234d6  mov     eax, [rbp+4Fh+arg_10]
0x1401234d9  mov     cl, al
0x1401234db  shr     eax, 1
0x1401234dd  and     cl, dil
0x1401234e0  and     al, dil
0x1401234e3  mov     [rbp+4Fh+var_6C], cl
0x1401234e6  mov     [rbp+4Fh+var_6B], al
0x1401234e9  cmp     esi, ebx
0x1401234eb  jnz     short loc_140123508
0x1401234ed  mov     ecx, 3
0x1401234f2  call    cs:__imp_WdLogSingleEntry0
0x1401234f9  nop     dword ptr [rax+rax+00h]
0x1401234fe  mov     cs:WdLogGlobalForLineNumber, 18D9h
0x140123508  mov     r10, [rbp+4Fh+var_A8]
0x14012350c  jmp     short loc_140123513
0x14012350e  mov     esi, ebx
0x140123510  xor     r12d, r12d
0x140123513  test    r14b, 4
0x140123517  jz      short loc_14012353F
0x140123519  mov     rbx, [rbp+4Fh+var_B0]
0x14012351d  cmp     rbx, r10
0x140123520  jnz     short loc_140123542
0x140123522  mov     ecx, 3
0x140123527  call    cs:__imp_WdLogSingleEntry0
0x14012352e  nop     dword ptr [rax+rax+00h]
0x140123533  mov     cs:WdLogGlobalForLineNumber, 18E4h
0x14012353d  jmp     short loc_140123542
0x14012353f  mov     rbx, r10
0x140123542  test    r14b, 2
0x140123546  jnz     short loc_140123552
0x140123548  test    r14b, 4
0x14012354c  jz      loc_14012360B
0x140123552  mov     r8d, esi
0x140123555  mov     rdx, rbx
0x140123558  mov     rcx, r15
0x14012355b  call    ?VidMmValidatePreferredSegment@@YA_NPEBUVIDMM_PHYSICAL_ADAPTER@@UVIDMM_SEGMENT_PREFERENCES@@I@Z; VidMmValidatePreferredSegment(VIDMM_PHYSICAL_ADAPTER const *,VIDMM_SEGMENT_PREFERENCES,uint)
0x140123560  test    al, al
0x140123562  jnz     short loc_1401235A1
0x140123564  mov     rbx, 0FFFFFFFFC000000Dh
0x14012356b  mov     ecx, edi
0x14012356d  mov     rdx, rbx
0x140123570  call    cs:__imp_WdLogSingleEntry1
0x140123577  nop     dword ptr [rax+rax+00h]
0x14012357c  mov     [rsp+100h+var_C8], r12
0x140123581  lea     r9, aCurrentPreferr; "Current preferred segment is invalid. I"...
0x140123588  mov     [rsp+100h+var_D0], r12
0x14012358d  mov     qword ptr [rsp+100h+var_D8], r12
0x140123592  mov     cs:WdLogGlobalForLineNumber, 18F0h
0x14012359c  jmp     loc_1401233B8
0x1401235a1  lea     r8, [rbp+4Fh+arg_10]
0x1401235a5  mov     rdx, rbx
0x1401235a8  mov     rcx, r15
0x1401235ab  call    ?VidMmGetMostPreferredSegment@@YAPEAUVIDMM_SEGMENT_BASE@@PEAUVIDMM_PHYSICAL_ADAPTER@@UVIDMM_SEGMENT_PREFERENCES@@PEA_N@Z; VidMmGetMostPreferredSegment(VIDMM_PHYSICAL_ADAPTER *,VIDMM_SEGMENT_PREFERENCES,bool *)
0x1401235b0  lea     r9, [rbp+4Fh+var_80]; struct _VIDMM_VERIFY_BUDGET_GROUPS *
0x1401235b4  mov     r8, rax; struct VIDMM_SEGMENT_BASE *
0x1401235b7  mov     edx, esi; unsigned int
0x1401235b9  mov     rcx, r15; struct VIDMM_PHYSICAL_ADAPTER *
0x1401235bc  call    ?VidMmVerifyBudgetGroups@@YA_NPEBUVIDMM_PHYSICAL_ADAPTER@@IPEBUVIDMM_SEGMENT_BASE@@PEAU_VIDMM_VERIFY_BUDGET_GROUPS@@@Z; VidMmVerifyBudgetGroups(VIDMM_PHYSICAL_ADAPTER const *,uint,VIDMM_SEGMENT_BASE const *,_VIDMM_VERIFY_BUDGET_GROUPS *)
0x1401235c1  test    al, al
0x1401235c3  jnz     short loc_140123602
0x1401235c5  mov     rbx, 0FFFFFFFFC000000Dh
0x1401235cc  mov     ecx, edi
0x1401235ce  mov     rdx, rbx
0x1401235d1  call    cs:__imp_WdLogSingleEntry1
0x1401235d8  nop     dword ptr [rax+rax+00h]
0x1401235dd  mov     [rsp+100h+var_C8], r12
0x1401235e2  lea     r9, aFailedToVerify; "Failed to VerifyBudgetGroups, returning"...
0x1401235e9  mov     [rsp+100h+var_D0], r12
0x1401235ee  mov     qword ptr [rsp+100h+var_D8], r12
0x1401235f3  mov     cs:WdLogGlobalForLineNumber, 18FAh
0x1401235fd  jmp     loc_1401233B8
0x140123602  mov     r14d, [rbp+4Fh+var_70]
0x140123606  mov     edx, [rbp+4Fh+var_74]
0x140123609  jmp     short loc_14012360E
0x14012360b  mov     edx, [rbp+4Fh+arg_18]
0x14012360e  test    dil, r14b
0x140123611  jz      short loc_14012367F
0x140123613  mov     rax, [r13+180h]
0x14012361a  test    dword ptr [rax], 8000h
0x140123620  jz      short loc_14012367F
0x140123622  test    dil, dl
0x140123625  jnz     short loc_140123664
0x140123627  mov     rbx, 0FFFFFFFFC000000Dh
0x14012362e  mov     ecx, edi
0x140123630  mov     rdx, rbx
0x140123633  call    cs:__imp_WdLogSingleEntry1
0x14012363a  nop     dword ptr [rax+rax+00h]
0x14012363f  mov     [rsp+100h+var_C8], r12
0x140123644  lea     r9, aMayNotRemoveAc; "May not remove AccessedPhysically on al"...
0x14012364b  mov     [rsp+100h+var_D0], r12
0x140123650  mov     qword ptr [rsp+100h+var_D8], r12
0x140123655  mov     cs:WdLogGlobalForLineNumber, 1906h
0x14012365f  jmp     loc_1401233B8
0x140123664  mov     ecx, 3
0x140123669  call    cs:__imp_WdLogSingleEntry0
0x140123670  nop     dword ptr [rax+rax+00h]
0x140123675  mov     cs:WdLogGlobalForLineNumber, 190Dh
0x14012367f  mov     rbx, [rbp+4Fh+arg_0]
0x140123683  test    r14b, 8
0x140123687  jz      short loc_1401236FB
0x140123689  mov     rax, [rbx+18h]
0x14012368d  test    dword ptr [rax+1BCh], 200h
0x140123697  jnz     short loc_1401236D6
0x140123699  mov     rbx, 0FFFFFFFFC000000Dh
0x1401236a0  mov     ecx, edi
0x1401236a2  mov     rdx, rbx
0x1401236a5  call    cs:__imp_WdLogSingleEntry1
0x1401236ac  nop     dword ptr [rax+rax+00h]
0x1401236b1  mov     [rsp+100h+var_C8], r12
0x1401236b6  lea     r9, aSetunmoveableI; "SetUnmoveable is not supported, returni"...
0x1401236bd  mov     [rsp+100h+var_D0], r12
0x1401236c2  mov     qword ptr [rsp+100h+var_D8], r12
0x1401236c7  mov     cs:WdLogGlobalForLineNumber, 1917h
0x1401236d1  jmp     loc_1401233B8
0x1401236d6  test    dword ptr [r13+1Ch], 800h
0x1401236de  jz      short loc_1401236FB
0x1401236e0  mov     ecx, 3
0x1401236e5  call    cs:__imp_WdLogSingleEntry0
0x1401236ec  nop     dword ptr [rax+rax+00h]
0x1401236f1  mov     cs:WdLogGlobalForLineNumber, 191Eh
0x1401236fb  mov     rax, [rbp+4Fh+arg_20]
0x1401236ff  lea     r8, [rbp+4Fh+var_A0]; struct _VIDMM_DEFERRED_COMMAND *
0x140123703  mov     rdx, [rbp+4Fh+arg_8]; struct VIDMM_PAGING_QUEUE *
0x140123707  xor     r9d, r9d; bool
0x14012370a  mov     rcx, rbx; this
0x14012370d  mov     [rsp+100h+var_E0], rax; unsigned __int64 *
0x140123712  call    ?QueueDeferredCommand@VIDMM_GLOBAL@@QEAAJAEAUVIDMM_PAGING_QUEUE@@PEAU_VIDMM_DEFERRED_COMMAND@@_NPEA_K@Z; VIDMM_GLOBAL::QueueDeferredCommand(VIDMM_PAGING_QUEUE &,_VIDMM_DEFERRED_COMMAND *,bool,unsigned __int64 *)
0x140123717  add     rsp, 0C8h
0x14012371e  pop     r15
0x140123720  pop     r14
0x140123722  pop     r13
0x140123724  pop     r12
0x140123726  pop     rdi
0x140123727  pop     rsi
0x140123728  pop     rbx
0x140123729  pop     rbp
0x14012372a  retn
```
