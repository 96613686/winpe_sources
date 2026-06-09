# CreatePhysicalAdapterSegments

- ea: `0x1400cf3ac`
- end: `0x1400cf9dd`
- name: `CreatePhysicalAdapterSegments`
- size: `1585`
- prototype: `__int64 __fastcall(struct VIDMM_PHYSICAL_ADAPTER_LEGACY *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400cff90`

## callees

- `0x140004268`
- `0x14002ed58`
- `0x14003e238`
- `0x140058f50`
- `0x140059380`
- `0x1400cf3ac`
- `0x1400cffa8`
- `0x1400d13d8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400cf64c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cf734`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cf785`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cf8ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cf9ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cf64c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cf734`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cf785`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cf8ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cf9ab`
- `ntoskrnl!ExAllocatePool2` at `0x1400cf54c`
- `ntoskrnl!ExAllocatePool2` at `0x1400cf54c`
- `watchdog!WdLogSingleEntry3` at `0x1400cf847`
- `watchdog!WdLogSingleEntry3` at `0x1400cf847`
- `watchdog!WdLogSingleEntry2` at `0x1400cf4e3`
- `watchdog!WdLogSingleEntry2` at `0x1400cf6e1`
- `watchdog!WdLogSingleEntry2` at `0x1400cf4e3`
- `watchdog!WdLogSingleEntry2` at `0x1400cf6e1`
- `watchdog!WdLogSingleEntry0` at `0x1400cf48b`
- `watchdog!WdLogSingleEntry0` at `0x1400cf48b`
- `watchdog!WdLogSingleEntry1` at `0x1400cf463`
- `watchdog!WdLogSingleEntry1` at `0x1400cf59d`
- `watchdog!WdLogSingleEntry1` at `0x1400cf5fd`
- `watchdog!WdLogSingleEntry1` at `0x1400cf899`
- `watchdog!WdLogSingleEntry1` at `0x1400cf463`
- `watchdog!WdLogSingleEntry1` at `0x1400cf59d`
- `watchdog!WdLogSingleEntry1` at `0x1400cf5fd`
- `watchdog!WdLogSingleEntry1` at `0x1400cf899`

## string_xrefs

- `0x1400cf60e`: `Failed to query segment descriptors: NtStatus=0x%08X`

## pseudocode

```c
__int64 __fastcall CreatePhysicalAdapterSegments(struct VIDMM_PHYSICAL_ADAPTER_LEGACY *a1)
{
  __int64 v1; // r13
  int v3; // eax
  unsigned int v4; // edi
  __int64 result; // rax
  int v6; // ecx
  int v7; // r8d
  int v8; // ecx
  int v9; // r8d
  __int64 v10; // rsi
  unsigned int v11; // edi
  PVOID Pool2; // r14
  int v13; // ecx
  int v14; // r8d
  int v15; // eax
  __int64 v16; // r15
  int v17; // ecx
  int v18; // r8d
  bool v19; // zf
  __int64 v20; // rax
  __int64 v21; // rax
  int v22; // ecx
  int v23; // r8d
  unsigned int v24; // r12d
  int v25; // esi
  __int64 v26; // r9
  unsigned int i; // ecx
  int v28; // edx
  __int64 v29; // r8
  int v30; // eax
  int v31; // eax
  unsigned int v32; // r8d
  int v33; // ecx
  __int64 v34; // rdx
  int v35; // r8d
  int v36; // ecx
  int v37; // r8d
  __int64 v38; // r9
  __int64 v39; // rdx
  int v40; // r8d
  int v41; // ecx
  int v42; // ecx
  int v43; // [rsp+50h] [rbp-B0h] BYREF
  int v44; // [rsp+54h] [rbp-ACh]
  __int64 v45; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v46; // [rsp+60h] [rbp-A0h]
  __int128 v47; // [rsp+68h] [rbp-98h]
  __int64 v48; // [rsp+78h] [rbp-88h]
  __int64 v49; // [rsp+80h] [rbp-80h]
  struct _DXGKARG_QUERYADAPTERINFO v50; // [rsp+88h] [rbp-78h] BYREF
  PVOID P; // [rsp+C0h] [rbp-40h]
  _BYTE v52[416]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v53; // [rsp+268h] [rbp+168h]

  v1 = *((_QWORD *)a1 + 7);
  v44 = *((unsigned __int16 *)a1 + 36);
  v49 = *(_QWORD *)(*(_QWORD *)(v1 + 24) + 3120LL);
  v50.pInputData = &v43;
  v50.pOutputData = &v45;
  *(_QWORD *)&v50.Type = 11;
  *(_QWORD *)&v50.InputDataSize = 4;
  *(_QWORD *)&v50.Flags.0 = 0;
  HIDWORD(v50.hKmdProcessHandle) = 0;
  v45 = 0;
  v47 = 0;
  v48 = 0;
  v43 = v44;
  v46 = 0;
  v50.OutputDataSize = 40;
  v3 = DXGADAPTER::DdiQueryAdapterInfo(*(DXGADAPTER **)(v1 + 24), &v50);
  v4 = v3;
  if ( v3 < 0 )
  {
    WdLogSingleEntry1(3, v3);
    result = v4;
    WdLogGlobalForLineNumber = 665;
    return result;
  }
  if ( !(_DWORD)v45 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 673;
    DxgkLogInternalTriageEvent(
      v6,
      0x40000,
      v7,
      (unsigned int)L"DXGKQAITYPE_QUERYSEGMENT4: Driver must provide at least one segment",
      673,
      0,
      0,
      0);
    return 3221225473LL;
  }
  if ( (unsigned int)v45 > 0x20 )
  {
    WdLogSingleEntry2(1, (unsigned int)v45, 32);
    WdLogGlobalForLineNumber = 681;
    DxgkLogInternalTriageEvent(
      v8,
      0x40000,
      v9,
      (unsigned int)L"DXGKQAITYPE_QUERYSEGMENT4: Too many segments specified (%u). Maximum allowed is %u",
      (unsigned int)v45,
      32,
      0,
      0);
    return 3221225473LL;
  }
  v10 = (unsigned __int16)v45;
  P = 0;
  v11 = (unsigned __int16)v45;
  v53 = 0;
  if ( (unsigned __int16)v45 <= 4u )
  {
    P = v52;
    memset(v52, 0, 104LL * (unsigned __int16)v45);
    Pool2 = P;
  }
  else
  {
    if ( 0xFFFFFFFFFFFFFFFFuLL / (unsigned __int16)v45 < 0x68 )
    {
LABEL_14:
      _InterlockedAdd(&dword_1400876D8, 1u);
      WdLogSingleEntry1(6, v10);
      WdLogGlobalForLineNumber = 694;
      DxgkLogInternalTriageEvent(
        v13,
        262145,
        v14,
        (unsigned int)L"Failed to allocate memory for segment description array. NbSegment=%d",
        v10,
        0,
        0,
        0);
LABEL_27:
      if ( P != v52 )
      {
        if ( P )
          ExFreePoolWithTag(P, 0);
      }
      return 3221225495LL;
    }
    Pool2 = (PVOID)ExAllocatePool2(256, 104LL * (unsigned __int16)v45, 1265072196);
    P = Pool2;
  }
  v53 = v11;
  if ( !Pool2 )
    goto LABEL_14;
  v46 = Pool2;
  v48 = 104;
  v15 = DXGADAPTER::DdiQueryAdapterInfo(*(DXGADAPTER **)(v1 + 24), &v50);
  v16 = v15;
  if ( v15 < 0 )
  {
    WdLogSingleEntry1(1, v15);
    WdLogGlobalForLineNumber = 706;
    DxgkLogInternalTriageEvent(
      v17,
      0x40000,
      v18,
      (unsigned int)L"Failed to query segment descriptors: NtStatus=0x%08X",
      v16,
      0,
      0,
      0);
    if ( P != v52 && P )
      ExFreePoolWithTag(P, 0);
    return (unsigned int)v16;
  }
  if ( !ValidateSegmentDescriptors_0(v1, (__int64)Pool2, v11, v47) )
    goto LABEL_60;
  v19 = (*((_BYTE *)a1 + 1348) & 0x48) == 0;
  *((_DWORD *)a1 + 233) = v11;
  if ( !v19 )
    LOWORD(v10) = v10 + 1;
  v20 = 8LL * (unsigned __int16)v10;
  if ( !is_mul_ok((unsigned __int16)v10, 8u) )
    v20 = -1;
  v21 = operator new[](v20, 925919574, 64);
  *((_QWORD *)a1 + 332) = v21;
  if ( !v21 )
  {
    _InterlockedAdd(&dword_140087718, 1u);
    WdLogSingleEntry2(6, v1, *((unsigned __int16 *)a1 + 36));
    WdLogGlobalForLineNumber = 743;
    DxgkLogInternalTriageEvent(
      v22,
      262145,
      v23,
      (unsigned int)L"Failed to allocate segment array. VidMmGlobal=0x%I64x, PhysicalAdapterIndex=%u",
      v1,
      *((unsigned __int16 *)a1 + 36),
      0,
      0);
    goto LABEL_27;
  }
  v24 = (unsigned __int16)v10;
  *((_DWORD *)a1 + 232) = (unsigned __int16)v10;
  v25 = InitializePhysicalAdapterSegments_0(a1);
  if ( v25 < 0 )
  {
    if ( P != v52 && P )
      ExFreePoolWithTag(P, 0);
    return (unsigned int)v25;
  }
  if ( v24 )
  {
    v26 = *((_QWORD *)a1 + 332);
    for ( i = 0; i < v24; ++i )
    {
      v28 = 1 << i;
      v29 = *(_QWORD *)(v26 + 8LL * i);
      v30 = *(_DWORD *)(v29 + 64);
      if ( (v30 & 1) != 0 )
      {
        *((_DWORD *)a1 + 23) |= v28;
      }
      else if ( (v30 & 0x1000) != 0 )
      {
        *((_DWORD *)a1 + 22) |= v28;
      }
      else
      {
        *((_DWORD *)a1 + 21) |= v28;
      }
      v31 = *(_DWORD *)(v29 + 64);
      if ( (v31 & 0x80000) != 0 )
      {
        *((_DWORD *)a1 + 29) |= v28;
      }
      else if ( (v31 & 0x100000) != 0 )
      {
        *((_DWORD *)a1 + 30) |= v28;
      }
      else
      {
        *((_DWORD *)a1 + 31) |= v28;
      }
      if ( (*(_DWORD *)(v29 + 64) & 0x10) != 0 )
        *((_DWORD *)a1 + 25) |= v28;
      if ( (*(_DWORD *)(v29 + 64) & 4) != 0 )
      {
        *((_DWORD *)a1 + 26) |= v28;
        *((_DWORD *)a1 + 27) |= v28;
      }
      if ( (*(_DWORD *)(v29 + 64) & 0x6000) != 0 )
      {
        *((_DWORD *)a1 + 26) |= v28;
        *((_DWORD *)a1 + 28) |= v28;
      }
    }
  }
  v32 = *((_DWORD *)a1 + 23);
  v33 = *((_DWORD *)a1 + 21);
  v34 = v33 | *((_DWORD *)a1 + 22) | v32;
  *((_DWORD *)a1 + 24) = *((_DWORD *)a1 + 22) | v32;
  *((_DWORD *)a1 + 19) = v34;
  *((_DWORD *)a1 + 20) = v32 | v33;
  if ( !*((_DWORD *)a1 + 29) )
  {
    WdLogSingleEntry3(1, v34, *((unsigned int *)a1 + 30), *((unsigned int *)a1 + 31));
    WdLogGlobalForLineNumber = 831;
    DxgkLogInternalTriageEvent(
      *((_DWORD *)a1 + 30),
      0x40000,
      v35,
      (unsigned int)L"Adapter segments must contain at least one local segment. SegmentSet: %u, NonLocalSegmentSet: %u, No"
                     "nBudgetSegmentSet: %u",
      *((unsigned int *)a1 + 19),
      *((unsigned int *)a1 + 30),
      *((unsigned int *)a1 + 31),
      0);
    goto LABEL_60;
  }
  if ( (_DWORD)v47 && !_bittest((const int *)&v32, (unsigned __int8)(v47 - 1)) )
  {
    WdLogSingleEntry1(1, (unsigned int)v47);
    WdLogGlobalForLineNumber = 845;
    DxgkLogInternalTriageEvent(
      v36,
      0x40000,
      v37,
      (unsigned int)L"PagingBufferSegmentId (%u) must be an aperture segment",
      (unsigned int)v47,
      0,
      0,
      0);
LABEL_60:
    if ( P != v52 && P )
      ExFreePoolWithTag(P, 0);
    return 3221225485LL;
  }
  v38 = v49;
  v39 = 352LL * (unsigned __int16)v44;
  *(_BYTE *)(*((unsigned __int16 *)a1 + 36) + v1 + 68) = v47;
  *(_DWORD *)(v1 + 4LL * *((unsigned __int16 *)a1 + 36) + 388) = DWORD2(v47);
  *(_DWORD *)(v1 + 4LL * *((unsigned __int16 *)a1 + 36) + 132) = DWORD1(v47);
  v40 = *((_DWORD *)a1 + 23);
  *((_QWORD *)a1 + 318) = *((_QWORD *)a1 + 332);
  v41 = *(_DWORD *)(v39 + v38 + 344);
  *((_DWORD *)a1 + 32) = v41;
  if ( (v41 & v40) != 0 )
  {
    _bittestandset(&v41, *((unsigned __int16 *)a1 + 468));
    *((_DWORD *)a1 + 32) = v41;
  }
  v42 = *(_DWORD *)(v39 + v38 + 348);
  *((_DWORD *)a1 + 33) = v42;
  if ( (v42 & v40) != 0 )
  {
    _bittestandset(&v42, *((unsigned __int16 *)a1 + 468));
    *((_DWORD *)a1 + 33) = v42;
  }
  if ( P != v52 && P )
    ExFreePoolWithTag(P, 0);
  return 0;
}

```

## disassembly

```asm
0x1400cf3ac  push    rbp
0x1400cf3ae  push    rbx
0x1400cf3af  push    rsi
0x1400cf3b0  push    rdi
0x1400cf3b1  push    r12
0x1400cf3b3  push    r13
0x1400cf3b5  push    r14
0x1400cf3b7  push    r15
0x1400cf3b9  lea     rbp, [rsp-188h]
0x1400cf3c1  sub     rsp, 288h
0x1400cf3c8  mov     rax, cs:__security_cookie
0x1400cf3cf  xor     rax, rsp
0x1400cf3d2  mov     [rbp+1C0h+var_50], rax
0x1400cf3d9  mov     r13, [rcx+38h]
0x1400cf3dd  lea     rdx, [rbp+1C0h+var_238]; struct _DXGKARG_QUERYADAPTERINFO *
0x1400cf3e1  xor     r12d, r12d
0x1400cf3e4  mov     rbx, rcx
0x1400cf3e7  movzx   ecx, word ptr [rcx+48h]
0x1400cf3eb  xorps   xmm0, xmm0
0x1400cf3ee  mov     [rsp+2C0h+var_26C], ecx
0x1400cf3f2  mov     rax, [r13+18h]
0x1400cf3f6  mov     rax, [rax+0C30h]
0x1400cf3fd  mov     [rbp+1C0h+var_240], rax
0x1400cf401  lea     rax, [rsp+2C0h+var_270]
0x1400cf406  mov     [rbp+1C0h+var_238.pInputData], rax
0x1400cf40a  lea     rax, [rsp+2C0h+var_268]
0x1400cf40f  mov     [rbp+1C0h+var_238.pOutputData], rax
0x1400cf413  mov     qword ptr [rbp+1C0h+var_238.Type], 0Bh
0x1400cf41b  mov     qword ptr [rbp+1C0h+var_238.InputDataSize], 4
0x1400cf423  mov     qword ptr [rbp+1C0h+var_238.Flags], r12
0x1400cf427  mov     dword ptr [rbp+1C0h+var_238.hKmdProcessHandle+4], r12d
0x1400cf42b  mov     [rsp+2C0h+var_268], r12
0x1400cf430  movdqu  [rsp+2C0h+var_258], xmm0
0x1400cf436  mov     [rsp+2C0h+var_248], r12
0x1400cf43b  mov     [rsp+2C0h+var_270], ecx
0x1400cf43f  mov     [rsp+2C0h+var_260], r12
0x1400cf444  mov     [rbp+1C0h+var_238.OutputDataSize], 28h ; '('
0x1400cf44b  mov     rcx, [r13+18h]; this
0x1400cf44f  call    ?DdiQueryAdapterInfo@DXGADAPTER@@QEAAJPEAU_DXGKARG_QUERYADAPTERINFO@@@Z; DXGADAPTER::DdiQueryAdapterInfo(_DXGKARG_QUERYADAPTERINFO *)
0x1400cf454  movsxd  rdi, eax
0x1400cf457  test    eax, eax
0x1400cf459  jns     short loc_1400CF480
0x1400cf45b  mov     rdx, rdi
0x1400cf45e  lea     ecx, [r12+3]
0x1400cf463  call    cs:__imp_WdLogSingleEntry1
0x1400cf46a  nop     dword ptr [rax+rax+00h]
0x1400cf46f  mov     eax, edi
0x1400cf471  mov     cs:WdLogGlobalForLineNumber, 299h
0x1400cf47b  jmp     loc_1400CF9B9
0x1400cf480  mov     eax, dword ptr [rsp+2C0h+var_268]
0x1400cf484  test    eax, eax
0x1400cf486  jnz     short loc_1400CF4D1
0x1400cf488  lea     ecx, [rax+1]
0x1400cf48b  call    cs:__imp_WdLogSingleEntry0
0x1400cf492  nop     dword ptr [rax+rax+00h]
0x1400cf497  mov     [rsp+2C0h+var_288], r12
0x1400cf49c  lea     r9, aDxgkqaitypeQue_0; "DXGKQAITYPE_QUERYSEGMENT4: Driver must "...
0x1400cf4a3  mov     eax, 2A1h
0x1400cf4a8  mov     [rsp+2C0h+var_290], r12
0x1400cf4ad  mov     cs:WdLogGlobalForLineNumber, eax
0x1400cf4b3  mov     [rsp+2C0h+var_298], r12
0x1400cf4b8  mov     edx, 40000h
0x1400cf4bd  mov     [rsp+2C0h+var_2A0], rax
0x1400cf4c2  call    DxgkLogInternalTriageEvent
0x1400cf4c7  mov     eax, 0C0000001h
0x1400cf4cc  jmp     loc_1400CF9B9
0x1400cf4d1  mov     esi, 20h ; ' '
0x1400cf4d6  cmp     eax, esi
0x1400cf4d8  jbe     short loc_1400CF515
0x1400cf4da  mov     rdx, rax
0x1400cf4dd  lea     ecx, [rsi-1Fh]
0x1400cf4e0  mov     r8d, esi
0x1400cf4e3  call    cs:__imp_WdLogSingleEntry2
0x1400cf4ea  nop     dword ptr [rax+rax+00h]
0x1400cf4ef  mov     eax, dword ptr [rsp+2C0h+var_268]
0x1400cf4f3  lea     r9, aDxgkqaitypeQue; "DXGKQAITYPE_QUERYSEGMENT4: Too many seg"...
0x1400cf4fa  mov     [rsp+2C0h+var_288], r12
0x1400cf4ff  mov     [rsp+2C0h+var_290], r12
0x1400cf504  mov     [rsp+2C0h+var_298], rsi
0x1400cf509  mov     cs:WdLogGlobalForLineNumber, 2A9h
0x1400cf513  jmp     short loc_1400CF4B8
0x1400cf515  movzx   esi, word ptr [rsp+2C0h+var_268]
0x1400cf51a  mov     [rbp+1C0h+P], r12
0x1400cf51e  mov     edi, esi
0x1400cf520  mov     [rbp+1C0h+var_58], r12d
0x1400cf527  cmp     esi, 4
0x1400cf52a  jbe     short loc_1400CF561
0x1400cf52c  xor     edx, edx
0x1400cf52e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400cf532  div     rdi
0x1400cf535  mov     ecx, esi
0x1400cf537  cmp     rax, 68h ; 'h'
0x1400cf53b  jb      short loc_1400CF58B
0x1400cf53d  imul    rdx, rcx, 68h ; 'h'
0x1400cf541  mov     ecx, 100h
0x1400cf546  mov     r8d, 4B677844h
0x1400cf54c  call    cs:__imp_ExAllocatePool2
0x1400cf553  nop     dword ptr [rax+rax+00h]
0x1400cf558  mov     r14, rax
0x1400cf55b  mov     [rbp+1C0h+P], rax
0x1400cf55f  jmp     short loc_1400CF580
0x1400cf561  lea     r14, [rbp+1C0h+var_1F8]
0x1400cf565  mov     [rbp+1C0h+P], r14
0x1400cf569  test    edi, edi
0x1400cf56b  jz      short loc_1400CF580
0x1400cf56d  imul    r8, rdi, 68h ; 'h'; Size
0x1400cf571  xor     edx, edx; Val
0x1400cf573  lea     rcx, [rbp+1C0h+var_1F8]; void *
0x1400cf577  call    memset
0x1400cf57c  mov     r14, [rbp+1C0h+P]
0x1400cf580  mov     [rbp+1C0h+var_58], edi
0x1400cf586  test    r14, r14
0x1400cf589  jnz     short loc_1400CF5D3
0x1400cf58b  mov     edi, 1
0x1400cf590  lock add cs:dword_1400876D8, edi
0x1400cf597  mov     rdx, rsi
0x1400cf59a  lea     ecx, [rdi+5]
0x1400cf59d  call    cs:__imp_WdLogSingleEntry1
0x1400cf5a4  nop     dword ptr [rax+rax+00h]
0x1400cf5a9  mov     [rsp+2C0h+var_288], r12
0x1400cf5ae  lea     r9, aFailedToAlloca_56; "Failed to allocate memory for segment d"...
0x1400cf5b5  mov     [rsp+2C0h+var_290], r12
0x1400cf5ba  mov     [rsp+2C0h+var_298], r12
0x1400cf5bf  mov     [rsp+2C0h+var_2A0], rsi
0x1400cf5c4  mov     cs:WdLogGlobalForLineNumber, 2B6h
0x1400cf5ce  jmp     loc_1400CF716
0x1400cf5d3  mov     [rsp+2C0h+var_260], r14
0x1400cf5d8  lea     rdx, [rbp+1C0h+var_238]; struct _DXGKARG_QUERYADAPTERINFO *
0x1400cf5dc  mov     [rsp+2C0h+var_248], 68h ; 'h'
0x1400cf5e5  mov     rcx, [r13+18h]; this
0x1400cf5e9  call    ?DdiQueryAdapterInfo@DXGADAPTER@@QEAAJPEAU_DXGKARG_QUERYADAPTERINFO@@@Z; DXGADAPTER::DdiQueryAdapterInfo(_DXGKARG_QUERYADAPTERINFO *)
0x1400cf5ee  movsxd  r15, eax
0x1400cf5f1  test    eax, eax
0x1400cf5f3  jns     short loc_1400CF660
0x1400cf5f5  mov     rdx, r15
0x1400cf5f8  mov     ecx, 1
0x1400cf5fd  call    cs:__imp_WdLogSingleEntry1
0x1400cf604  nop     dword ptr [rax+rax+00h]
0x1400cf609  mov     [rsp+2C0h+var_288], r12
0x1400cf60e  lea     r9, aFailedToQueryS; "Failed to query segment descriptors: Nt"...
0x1400cf615  mov     [rsp+2C0h+var_290], r12
0x1400cf61a  mov     edx, 40000h
0x1400cf61f  mov     [rsp+2C0h+var_298], r12
0x1400cf624  mov     [rsp+2C0h+var_2A0], r15
0x1400cf629  mov     cs:WdLogGlobalForLineNumber, 2C2h
0x1400cf633  call    DxgkLogInternalTriageEvent
0x1400cf638  mov     rcx, [rbp+1C0h+P]; P
0x1400cf63c  lea     rax, [rbp+1C0h+var_1F8]
0x1400cf640  cmp     rcx, rax
0x1400cf643  jz      short loc_1400CF658
0x1400cf645  test    rcx, rcx
0x1400cf648  jz      short loc_1400CF658
0x1400cf64a  xor     edx, edx; Tag
0x1400cf64c  call    cs:__imp_ExFreePoolWithTag
0x1400cf653  nop     dword ptr [rax+rax+00h]
0x1400cf658  mov     eax, r15d
0x1400cf65b  jmp     loc_1400CF9B9
0x1400cf660  mov     r9d, dword ptr [rsp+2C0h+var_258]
0x1400cf665  mov     r8d, edi
0x1400cf668  mov     rdx, r14
0x1400cf66b  mov     rcx, r13
0x1400cf66e  call    ValidateSegmentDescriptors_0
0x1400cf673  test    al, al
0x1400cf675  jz      loc_1400CF8D8
0x1400cf67b  test    byte ptr [rbx+544h], 48h
0x1400cf682  mov     r15d, 0FFFFh
0x1400cf688  mov     [rbx+3A4h], edi
0x1400cf68e  mov     edi, 1
0x1400cf693  jz      short loc_1400CF69C
0x1400cf695  movzx   r15d, si
0x1400cf699  add     si, di
0x1400cf69c  movzx   ecx, si
0x1400cf69f  mov     eax, 8
0x1400cf6a4  mul     rcx
0x1400cf6a7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400cf6ae  mov     edx, 37306956h
0x1400cf6b3  cmovb   rax, rcx
0x1400cf6b7  lea     r8d, [rcx+41h]
0x1400cf6bb  mov     rcx, rax
0x1400cf6be  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400cf6c3  mov     [rbx+0A60h], rax
0x1400cf6ca  test    rax, rax
0x1400cf6cd  jnz     short loc_1400CF74A
0x1400cf6cf  lock add cs:dword_140087718, edi
0x1400cf6d6  movzx   r8d, word ptr [rbx+48h]
0x1400cf6db  lea     ecx, [rax+6]
0x1400cf6de  mov     rdx, r13
0x1400cf6e1  call    cs:__imp_WdLogSingleEntry2
0x1400cf6e8  nop     dword ptr [rax+rax+00h]
0x1400cf6ed  mov     [rsp+2C0h+var_288], r12
0x1400cf6f2  lea     r9, aFailedToAlloca_0; "Failed to allocate segment array. VidMm"...
0x1400cf6f9  mov     [rsp+2C0h+var_290], r12
0x1400cf6fe  mov     cs:WdLogGlobalForLineNumber, 2E7h
0x1400cf708  movzx   eax, word ptr [rbx+48h]
0x1400cf70c  mov     [rsp+2C0h+var_298], rax
0x1400cf711  mov     [rsp+2C0h+var_2A0], r13
0x1400cf716  mov     edx, 40001h
0x1400cf71b  call    DxgkLogInternalTriageEvent
0x1400cf720  mov     rcx, [rbp+1C0h+P]; P
0x1400cf724  lea     rax, [rbp+1C0h+var_1F8]
0x1400cf728  cmp     rcx, rax
0x1400cf72b  jz      short loc_1400CF740
0x1400cf72d  test    rcx, rcx
0x1400cf730  jz      short loc_1400CF740
0x1400cf732  xor     edx, edx; Tag
0x1400cf734  call    cs:__imp_ExFreePoolWithTag
0x1400cf73b  nop     dword ptr [rax+rax+00h]
0x1400cf740  mov     eax, 0C0000017h
0x1400cf745  jmp     loc_1400CF9B9
0x1400cf74a  movzx   r12d, si
0x1400cf74e  movzx   r9d, r15w
0x1400cf752  movzx   r8d, si
0x1400cf756  mov     [rbx+3A0h], r12d
0x1400cf75d  mov     rdx, r14
0x1400cf760  mov     rcx, rbx; struct VIDMM_PHYSICAL_ADAPTER_LEGACY *
0x1400cf763  call    InitializePhysicalAdapterSegments_0
0x1400cf768  xor     r14d, r14d
0x1400cf76b  mov     esi, eax
0x1400cf76d  test    eax, eax
0x1400cf76f  jns     short loc_1400CF798
0x1400cf771  mov     rcx, [rbp+1C0h+P]; P
0x1400cf775  lea     rax, [rbp+1C0h+var_1F8]
0x1400cf779  cmp     rcx, rax
0x1400cf77c  jz      short loc_1400CF791
0x1400cf77e  test    rcx, rcx
0x1400cf781  jz      short loc_1400CF791
0x1400cf783  xor     edx, edx; Tag
0x1400cf785  call    cs:__imp_ExFreePoolWithTag
0x1400cf78c  nop     dword ptr [rax+rax+00h]
0x1400cf791  mov     eax, esi
0x1400cf793  jmp     loc_1400CF9B9
0x1400cf798  test    r12d, r12d
0x1400cf79b  jz      short loc_1400CF81A
0x1400cf79d  mov     r9, [rbx+0A60h]
0x1400cf7a4  mov     ecx, r14d
0x1400cf7a7  mov     eax, ecx
0x1400cf7a9  mov     edx, edi
0x1400cf7ab  shl     edx, cl
0x1400cf7ad  mov     r8, [r9+rax*8]
0x1400cf7b1  mov     eax, [r8+40h]
0x1400cf7b5  test    dil, al
0x1400cf7b8  jz      short loc_1400CF7BF
0x1400cf7ba  or      [rbx+5Ch], edx
0x1400cf7bd  jmp     short loc_1400CF7CD
0x1400cf7bf  bt      eax, 0Ch
0x1400cf7c3  jnb     short loc_1400CF7CA
0x1400cf7c5  or      [rbx+58h], edx
0x1400cf7c8  jmp     short loc_1400CF7CD
0x1400cf7ca  or      [rbx+54h], edx
0x1400cf7cd  mov     eax, [r8+40h]
0x1400cf7d1  bt      eax, 13h
0x1400cf7d5  jnb     short loc_1400CF7DC
0x1400cf7d7  or      [rbx+74h], edx
0x1400cf7da  jmp     short loc_1400CF7EA
0x1400cf7dc  bt      eax, 14h
0x1400cf7e0  jnb     short loc_1400CF7E7
0x1400cf7e2  or      [rbx+78h], edx
0x1400cf7e5  jmp     short loc_1400CF7EA
0x1400cf7e7  or      [rbx+7Ch], edx
0x1400cf7ea  mov     eax, [r8+40h]
0x1400cf7ee  test    al, 10h
0x1400cf7f0  jz      short loc_1400CF7F5
0x1400cf7f2  or      [rbx+64h], edx
0x1400cf7f5  mov     eax, [r8+40h]
0x1400cf7f9  test    al, 4
0x1400cf7fb  jz      short loc_1400CF803
0x1400cf7fd  or      [rbx+68h], edx
0x1400cf800  or      [rbx+6Ch], edx
0x1400cf803  test    dword ptr [r8+40h], 6000h
0x1400cf80b  jz      short loc_1400CF813
0x1400cf80d  or      [rbx+68h], edx
0x1400cf810  or      [rbx+70h], edx
0x1400cf813  add     ecx, edi
0x1400cf815  cmp     ecx, r12d
0x1400cf818  jb      short loc_1400CF7A7
0x1400cf81a  mov     r8d, [rbx+5Ch]
0x1400cf81e  mov     eax, r8d
0x1400cf821  or      eax, [rbx+58h]
0x1400cf824  mov     ecx, [rbx+54h]
0x1400cf827  mov     edx, eax
0x1400cf829  or      edx, ecx
0x1400cf82b  mov     [rbx+60h], eax
0x1400cf82e  or      ecx, r8d
0x1400cf831  mov     [rbx+4Ch], edx
0x1400cf834  mov     [rbx+50h], ecx
0x1400cf837  cmp     [rbx+74h], r14d
0x1400cf83b  jnz     short loc_1400CF883
0x1400cf83d  mov     r9d, [rbx+7Ch]
0x1400cf841  mov     ecx, edi
0x1400cf843  mov     r8d, [rbx+78h]
0x1400cf847  call    cs:__imp_WdLogSingleEntry3
0x1400cf84e  nop     dword ptr [rax+rax+00h]
0x1400cf853  mov     cs:WdLogGlobalForLineNumber, 33Fh
0x1400cf85d  lea     r9, aAdapterSegment; "Adapter segments must contain at least "...
0x1400cf864  mov     eax, [rbx+7Ch]
0x1400cf867  mov     ecx, [rbx+78h]
0x1400cf86a  mov     edx, [rbx+4Ch]
0x1400cf86d  mov     [rsp+2C0h+var_288], r14
0x1400cf872  mov     [rsp+2C0h+var_290], rax
0x1400cf877  mov     [rsp+2C0h+var_298], rcx
  ... truncated ...
```
