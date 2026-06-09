# CreatePhysicalAdapterSegments

- ea: `0x1400c9520`
- end: `0x1400c9b51`
- name: `CreatePhysicalAdapterSegments`
- size: `1585`
- prototype: `__int64 __fastcall(struct VIDMM_PHYSICAL_ADAPTER_LEGACY *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400ca100`

## callees

- `0x1400045ec`
- `0x140031178`
- `0x14003f8b8`
- `0x140058680`
- `0x140058ac0`
- `0x1400c9520`
- `0x1400ca118`
- `0x1400cb4c8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400c97c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c98a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c98f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9a60`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9b1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c97c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c98a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c98f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9a60`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9b1f`
- `ntoskrnl!ExAllocatePool2` at `0x1400c96c0`
- `ntoskrnl!ExAllocatePool2` at `0x1400c96c0`
- `watchdog!WdLogSingleEntry3` at `0x1400c99bb`
- `watchdog!WdLogSingleEntry3` at `0x1400c99bb`
- `watchdog!WdLogSingleEntry2` at `0x1400c9657`
- `watchdog!WdLogSingleEntry2` at `0x1400c9855`
- `watchdog!WdLogSingleEntry2` at `0x1400c9657`
- `watchdog!WdLogSingleEntry2` at `0x1400c9855`
- `watchdog!WdLogSingleEntry0` at `0x1400c95ff`
- `watchdog!WdLogSingleEntry0` at `0x1400c95ff`
- `watchdog!WdLogSingleEntry1` at `0x1400c95d7`
- `watchdog!WdLogSingleEntry1` at `0x1400c9711`
- `watchdog!WdLogSingleEntry1` at `0x1400c9771`
- `watchdog!WdLogSingleEntry1` at `0x1400c9a0d`
- `watchdog!WdLogSingleEntry1` at `0x1400c95d7`
- `watchdog!WdLogSingleEntry1` at `0x1400c9711`
- `watchdog!WdLogSingleEntry1` at `0x1400c9771`
- `watchdog!WdLogSingleEntry1` at `0x1400c9a0d`

## string_xrefs

- `0x1400c9782`: `Failed to query segment descriptors: NtStatus=0x%08X`

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
  v49 = *(_QWORD *)(*(_QWORD *)(v1 + 24) + 3104LL);
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
      _InterlockedAdd(&dword_1400866F8, 1u);
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
  v19 = (*((_BYTE *)a1 + 1084) & 0x48) == 0;
  *((_DWORD *)a1 + 167) = v11;
  if ( !v19 )
    LOWORD(v10) = v10 + 1;
  v20 = 8LL * (unsigned __int16)v10;
  if ( !is_mul_ok((unsigned __int16)v10, 8u) )
    v20 = -1;
  v21 = operator new[](v20, 925919574, 64);
  *((_QWORD *)a1 + 299) = v21;
  if ( !v21 )
  {
    _InterlockedAdd(&dword_140086738, 1u);
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
  *((_DWORD *)a1 + 166) = (unsigned __int16)v10;
  v25 = InitializePhysicalAdapterSegments_0(a1);
  if ( v25 < 0 )
  {
    if ( P != v52 && P )
      ExFreePoolWithTag(P, 0);
    return (unsigned int)v25;
  }
  if ( v24 )
  {
    v26 = *((_QWORD *)a1 + 299);
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
  *((_QWORD *)a1 + 285) = *((_QWORD *)a1 + 299);
  v41 = *(_DWORD *)(v39 + v38 + 344);
  *((_DWORD *)a1 + 32) = v41;
  if ( (v41 & v40) != 0 )
  {
    _bittestandset(&v41, *((unsigned __int16 *)a1 + 336));
    *((_DWORD *)a1 + 32) = v41;
  }
  v42 = *(_DWORD *)(v39 + v38 + 348);
  *((_DWORD *)a1 + 33) = v42;
  if ( (v42 & v40) != 0 )
  {
    _bittestandset(&v42, *((unsigned __int16 *)a1 + 336));
    *((_DWORD *)a1 + 33) = v42;
  }
  if ( P != v52 && P )
    ExFreePoolWithTag(P, 0);
  return 0;
}

```

## disassembly

```asm
0x1400c9520  push    rbp
0x1400c9522  push    rbx
0x1400c9523  push    rsi
0x1400c9524  push    rdi
0x1400c9525  push    r12
0x1400c9527  push    r13
0x1400c9529  push    r14
0x1400c952b  push    r15
0x1400c952d  lea     rbp, [rsp-188h]
0x1400c9535  sub     rsp, 288h
0x1400c953c  mov     rax, cs:__security_cookie
0x1400c9543  xor     rax, rsp
0x1400c9546  mov     [rbp+1C0h+var_50], rax
0x1400c954d  mov     r13, [rcx+38h]
0x1400c9551  lea     rdx, [rbp+1C0h+var_238]; struct _DXGKARG_QUERYADAPTERINFO *
0x1400c9555  xor     r12d, r12d
0x1400c9558  mov     rbx, rcx
0x1400c955b  movzx   ecx, word ptr [rcx+48h]
0x1400c955f  xorps   xmm0, xmm0
0x1400c9562  mov     [rsp+2C0h+var_26C], ecx
0x1400c9566  mov     rax, [r13+18h]
0x1400c956a  mov     rax, [rax+0C20h]
0x1400c9571  mov     [rbp+1C0h+var_240], rax
0x1400c9575  lea     rax, [rsp+2C0h+var_270]
0x1400c957a  mov     [rbp+1C0h+var_238.pInputData], rax
0x1400c957e  lea     rax, [rsp+2C0h+var_268]
0x1400c9583  mov     [rbp+1C0h+var_238.pOutputData], rax
0x1400c9587  mov     qword ptr [rbp+1C0h+var_238.Type], 0Bh
0x1400c958f  mov     qword ptr [rbp+1C0h+var_238.InputDataSize], 4
0x1400c9597  mov     qword ptr [rbp+1C0h+var_238.Flags], r12
0x1400c959b  mov     dword ptr [rbp+1C0h+var_238.hKmdProcessHandle+4], r12d
0x1400c959f  mov     [rsp+2C0h+var_268], r12
0x1400c95a4  movdqu  [rsp+2C0h+var_258], xmm0
0x1400c95aa  mov     [rsp+2C0h+var_248], r12
0x1400c95af  mov     [rsp+2C0h+var_270], ecx
0x1400c95b3  mov     [rsp+2C0h+var_260], r12
0x1400c95b8  mov     [rbp+1C0h+var_238.OutputDataSize], 28h ; '('
0x1400c95bf  mov     rcx, [r13+18h]; this
0x1400c95c3  call    ?DdiQueryAdapterInfo@DXGADAPTER@@QEAAJPEAU_DXGKARG_QUERYADAPTERINFO@@@Z; DXGADAPTER::DdiQueryAdapterInfo(_DXGKARG_QUERYADAPTERINFO *)
0x1400c95c8  movsxd  rdi, eax
0x1400c95cb  test    eax, eax
0x1400c95cd  jns     short loc_1400C95F4
0x1400c95cf  mov     rdx, rdi
0x1400c95d2  lea     ecx, [r12+3]
0x1400c95d7  call    cs:__imp_WdLogSingleEntry1
0x1400c95de  nop     dword ptr [rax+rax+00h]
0x1400c95e3  mov     eax, edi
0x1400c95e5  mov     cs:WdLogGlobalForLineNumber, 299h
0x1400c95ef  jmp     loc_1400C9B2D
0x1400c95f4  mov     eax, dword ptr [rsp+2C0h+var_268]
0x1400c95f8  test    eax, eax
0x1400c95fa  jnz     short loc_1400C9645
0x1400c95fc  lea     ecx, [rax+1]
0x1400c95ff  call    cs:__imp_WdLogSingleEntry0
0x1400c9606  nop     dword ptr [rax+rax+00h]
0x1400c960b  mov     [rsp+2C0h+var_288], r12
0x1400c9610  lea     r9, aDxgkqaitypeQue_0; "DXGKQAITYPE_QUERYSEGMENT4: Driver must "...
0x1400c9617  mov     eax, 2A1h
0x1400c961c  mov     [rsp+2C0h+var_290], r12
0x1400c9621  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c9627  mov     [rsp+2C0h+var_298], r12
0x1400c962c  mov     edx, 40000h
0x1400c9631  mov     [rsp+2C0h+var_2A0], rax
0x1400c9636  call    DxgkLogInternalTriageEvent
0x1400c963b  mov     eax, 0C0000001h
0x1400c9640  jmp     loc_1400C9B2D
0x1400c9645  mov     esi, 20h ; ' '
0x1400c964a  cmp     eax, esi
0x1400c964c  jbe     short loc_1400C9689
0x1400c964e  mov     rdx, rax
0x1400c9651  lea     ecx, [rsi-1Fh]
0x1400c9654  mov     r8d, esi
0x1400c9657  call    cs:__imp_WdLogSingleEntry2
0x1400c965e  nop     dword ptr [rax+rax+00h]
0x1400c9663  mov     eax, dword ptr [rsp+2C0h+var_268]
0x1400c9667  lea     r9, aDxgkqaitypeQue; "DXGKQAITYPE_QUERYSEGMENT4: Too many seg"...
0x1400c966e  mov     [rsp+2C0h+var_288], r12
0x1400c9673  mov     [rsp+2C0h+var_290], r12
0x1400c9678  mov     [rsp+2C0h+var_298], rsi
0x1400c967d  mov     cs:WdLogGlobalForLineNumber, 2A9h
0x1400c9687  jmp     short loc_1400C962C
0x1400c9689  movzx   esi, word ptr [rsp+2C0h+var_268]
0x1400c968e  mov     [rbp+1C0h+P], r12
0x1400c9692  mov     edi, esi
0x1400c9694  mov     [rbp+1C0h+var_58], r12d
0x1400c969b  cmp     esi, 4
0x1400c969e  jbe     short loc_1400C96D5
0x1400c96a0  xor     edx, edx
0x1400c96a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400c96a6  div     rdi
0x1400c96a9  mov     ecx, esi
0x1400c96ab  cmp     rax, 68h ; 'h'
0x1400c96af  jb      short loc_1400C96FF
0x1400c96b1  imul    rdx, rcx, 68h ; 'h'
0x1400c96b5  mov     ecx, 100h
0x1400c96ba  mov     r8d, 4B677844h
0x1400c96c0  call    cs:__imp_ExAllocatePool2
0x1400c96c7  nop     dword ptr [rax+rax+00h]
0x1400c96cc  mov     r14, rax
0x1400c96cf  mov     [rbp+1C0h+P], rax
0x1400c96d3  jmp     short loc_1400C96F4
0x1400c96d5  lea     r14, [rbp+1C0h+var_1F8]
0x1400c96d9  mov     [rbp+1C0h+P], r14
0x1400c96dd  test    edi, edi
0x1400c96df  jz      short loc_1400C96F4
0x1400c96e1  imul    r8, rdi, 68h ; 'h'; Size
0x1400c96e5  xor     edx, edx; Val
0x1400c96e7  lea     rcx, [rbp+1C0h+var_1F8]; void *
0x1400c96eb  call    memset
0x1400c96f0  mov     r14, [rbp+1C0h+P]
0x1400c96f4  mov     [rbp+1C0h+var_58], edi
0x1400c96fa  test    r14, r14
0x1400c96fd  jnz     short loc_1400C9747
0x1400c96ff  mov     edi, 1
0x1400c9704  lock add cs:dword_1400866F8, edi
0x1400c970b  mov     rdx, rsi
0x1400c970e  lea     ecx, [rdi+5]
0x1400c9711  call    cs:__imp_WdLogSingleEntry1
0x1400c9718  nop     dword ptr [rax+rax+00h]
0x1400c971d  mov     [rsp+2C0h+var_288], r12
0x1400c9722  lea     r9, aFailedToAlloca_52; "Failed to allocate memory for segment d"...
0x1400c9729  mov     [rsp+2C0h+var_290], r12
0x1400c972e  mov     [rsp+2C0h+var_298], r12
0x1400c9733  mov     [rsp+2C0h+var_2A0], rsi
0x1400c9738  mov     cs:WdLogGlobalForLineNumber, 2B6h
0x1400c9742  jmp     loc_1400C988A
0x1400c9747  mov     [rsp+2C0h+var_260], r14
0x1400c974c  lea     rdx, [rbp+1C0h+var_238]; struct _DXGKARG_QUERYADAPTERINFO *
0x1400c9750  mov     [rsp+2C0h+var_248], 68h ; 'h'
0x1400c9759  mov     rcx, [r13+18h]; this
0x1400c975d  call    ?DdiQueryAdapterInfo@DXGADAPTER@@QEAAJPEAU_DXGKARG_QUERYADAPTERINFO@@@Z; DXGADAPTER::DdiQueryAdapterInfo(_DXGKARG_QUERYADAPTERINFO *)
0x1400c9762  movsxd  r15, eax
0x1400c9765  test    eax, eax
0x1400c9767  jns     short loc_1400C97D4
0x1400c9769  mov     rdx, r15
0x1400c976c  mov     ecx, 1
0x1400c9771  call    cs:__imp_WdLogSingleEntry1
0x1400c9778  nop     dword ptr [rax+rax+00h]
0x1400c977d  mov     [rsp+2C0h+var_288], r12
0x1400c9782  lea     r9, aFailedToQueryS; "Failed to query segment descriptors: Nt"...
0x1400c9789  mov     [rsp+2C0h+var_290], r12
0x1400c978e  mov     edx, 40000h
0x1400c9793  mov     [rsp+2C0h+var_298], r12
0x1400c9798  mov     [rsp+2C0h+var_2A0], r15
0x1400c979d  mov     cs:WdLogGlobalForLineNumber, 2C2h
0x1400c97a7  call    DxgkLogInternalTriageEvent
0x1400c97ac  mov     rcx, [rbp+1C0h+P]; P
0x1400c97b0  lea     rax, [rbp+1C0h+var_1F8]
0x1400c97b4  cmp     rcx, rax
0x1400c97b7  jz      short loc_1400C97CC
0x1400c97b9  test    rcx, rcx
0x1400c97bc  jz      short loc_1400C97CC
0x1400c97be  xor     edx, edx; Tag
0x1400c97c0  call    cs:__imp_ExFreePoolWithTag
0x1400c97c7  nop     dword ptr [rax+rax+00h]
0x1400c97cc  mov     eax, r15d
0x1400c97cf  jmp     loc_1400C9B2D
0x1400c97d4  mov     r9d, dword ptr [rsp+2C0h+var_258]
0x1400c97d9  mov     r8d, edi
0x1400c97dc  mov     rdx, r14
0x1400c97df  mov     rcx, r13
0x1400c97e2  call    ValidateSegmentDescriptors_0
0x1400c97e7  test    al, al
0x1400c97e9  jz      loc_1400C9A4C
0x1400c97ef  test    byte ptr [rbx+43Ch], 48h
0x1400c97f6  mov     r15d, 0FFFFh
0x1400c97fc  mov     [rbx+29Ch], edi
0x1400c9802  mov     edi, 1
0x1400c9807  jz      short loc_1400C9810
0x1400c9809  movzx   r15d, si
0x1400c980d  add     si, di
0x1400c9810  movzx   ecx, si
0x1400c9813  mov     eax, 8
0x1400c9818  mul     rcx
0x1400c981b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400c9822  mov     edx, 37306956h
0x1400c9827  cmovb   rax, rcx
0x1400c982b  lea     r8d, [rcx+41h]
0x1400c982f  mov     rcx, rax
0x1400c9832  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400c9837  mov     [rbx+958h], rax
0x1400c983e  test    rax, rax
0x1400c9841  jnz     short loc_1400C98BE
0x1400c9843  lock add cs:dword_140086738, edi
0x1400c984a  movzx   r8d, word ptr [rbx+48h]
0x1400c984f  lea     ecx, [rax+6]
0x1400c9852  mov     rdx, r13
0x1400c9855  call    cs:__imp_WdLogSingleEntry2
0x1400c985c  nop     dword ptr [rax+rax+00h]
0x1400c9861  mov     [rsp+2C0h+var_288], r12
0x1400c9866  lea     r9, aFailedToAlloca_0; "Failed to allocate segment array. VidMm"...
0x1400c986d  mov     [rsp+2C0h+var_290], r12
0x1400c9872  mov     cs:WdLogGlobalForLineNumber, 2E7h
0x1400c987c  movzx   eax, word ptr [rbx+48h]
0x1400c9880  mov     [rsp+2C0h+var_298], rax
0x1400c9885  mov     [rsp+2C0h+var_2A0], r13
0x1400c988a  mov     edx, 40001h
0x1400c988f  call    DxgkLogInternalTriageEvent
0x1400c9894  mov     rcx, [rbp+1C0h+P]; P
0x1400c9898  lea     rax, [rbp+1C0h+var_1F8]
0x1400c989c  cmp     rcx, rax
0x1400c989f  jz      short loc_1400C98B4
0x1400c98a1  test    rcx, rcx
0x1400c98a4  jz      short loc_1400C98B4
0x1400c98a6  xor     edx, edx; Tag
0x1400c98a8  call    cs:__imp_ExFreePoolWithTag
0x1400c98af  nop     dword ptr [rax+rax+00h]
0x1400c98b4  mov     eax, 0C0000017h
0x1400c98b9  jmp     loc_1400C9B2D
0x1400c98be  movzx   r12d, si
0x1400c98c2  movzx   r9d, r15w
0x1400c98c6  movzx   r8d, si
0x1400c98ca  mov     [rbx+298h], r12d
0x1400c98d1  mov     rdx, r14
0x1400c98d4  mov     rcx, rbx; struct VIDMM_PHYSICAL_ADAPTER_LEGACY *
0x1400c98d7  call    InitializePhysicalAdapterSegments_0
0x1400c98dc  xor     r14d, r14d
0x1400c98df  mov     esi, eax
0x1400c98e1  test    eax, eax
0x1400c98e3  jns     short loc_1400C990C
0x1400c98e5  mov     rcx, [rbp+1C0h+P]; P
0x1400c98e9  lea     rax, [rbp+1C0h+var_1F8]
0x1400c98ed  cmp     rcx, rax
0x1400c98f0  jz      short loc_1400C9905
0x1400c98f2  test    rcx, rcx
0x1400c98f5  jz      short loc_1400C9905
0x1400c98f7  xor     edx, edx; Tag
0x1400c98f9  call    cs:__imp_ExFreePoolWithTag
0x1400c9900  nop     dword ptr [rax+rax+00h]
0x1400c9905  mov     eax, esi
0x1400c9907  jmp     loc_1400C9B2D
0x1400c990c  test    r12d, r12d
0x1400c990f  jz      short loc_1400C998E
0x1400c9911  mov     r9, [rbx+958h]
0x1400c9918  mov     ecx, r14d
0x1400c991b  mov     eax, ecx
0x1400c991d  mov     edx, edi
0x1400c991f  shl     edx, cl
0x1400c9921  mov     r8, [r9+rax*8]
0x1400c9925  mov     eax, [r8+40h]
0x1400c9929  test    dil, al
0x1400c992c  jz      short loc_1400C9933
0x1400c992e  or      [rbx+5Ch], edx
0x1400c9931  jmp     short loc_1400C9941
0x1400c9933  bt      eax, 0Ch
0x1400c9937  jnb     short loc_1400C993E
0x1400c9939  or      [rbx+58h], edx
0x1400c993c  jmp     short loc_1400C9941
0x1400c993e  or      [rbx+54h], edx
0x1400c9941  mov     eax, [r8+40h]
0x1400c9945  bt      eax, 13h
0x1400c9949  jnb     short loc_1400C9950
0x1400c994b  or      [rbx+74h], edx
0x1400c994e  jmp     short loc_1400C995E
0x1400c9950  bt      eax, 14h
0x1400c9954  jnb     short loc_1400C995B
0x1400c9956  or      [rbx+78h], edx
0x1400c9959  jmp     short loc_1400C995E
0x1400c995b  or      [rbx+7Ch], edx
0x1400c995e  mov     eax, [r8+40h]
0x1400c9962  test    al, 10h
0x1400c9964  jz      short loc_1400C9969
0x1400c9966  or      [rbx+64h], edx
0x1400c9969  mov     eax, [r8+40h]
0x1400c996d  test    al, 4
0x1400c996f  jz      short loc_1400C9977
0x1400c9971  or      [rbx+68h], edx
0x1400c9974  or      [rbx+6Ch], edx
0x1400c9977  test    dword ptr [r8+40h], 6000h
0x1400c997f  jz      short loc_1400C9987
0x1400c9981  or      [rbx+68h], edx
0x1400c9984  or      [rbx+70h], edx
0x1400c9987  add     ecx, edi
0x1400c9989  cmp     ecx, r12d
0x1400c998c  jb      short loc_1400C991B
0x1400c998e  mov     r8d, [rbx+5Ch]
0x1400c9992  mov     eax, r8d
0x1400c9995  or      eax, [rbx+58h]
0x1400c9998  mov     ecx, [rbx+54h]
0x1400c999b  mov     edx, eax
0x1400c999d  or      edx, ecx
0x1400c999f  mov     [rbx+60h], eax
0x1400c99a2  or      ecx, r8d
0x1400c99a5  mov     [rbx+4Ch], edx
0x1400c99a8  mov     [rbx+50h], ecx
0x1400c99ab  cmp     [rbx+74h], r14d
0x1400c99af  jnz     short loc_1400C99F7
0x1400c99b1  mov     r9d, [rbx+7Ch]
0x1400c99b5  mov     ecx, edi
0x1400c99b7  mov     r8d, [rbx+78h]
0x1400c99bb  call    cs:__imp_WdLogSingleEntry3
0x1400c99c2  nop     dword ptr [rax+rax+00h]
0x1400c99c7  mov     cs:WdLogGlobalForLineNumber, 33Fh
0x1400c99d1  lea     r9, aAdapterSegment; "Adapter segments must contain at least "...
0x1400c99d8  mov     eax, [rbx+7Ch]
0x1400c99db  mov     ecx, [rbx+78h]
0x1400c99de  mov     edx, [rbx+4Ch]
0x1400c99e1  mov     [rsp+2C0h+var_288], r14
0x1400c99e6  mov     [rsp+2C0h+var_290], rax
0x1400c99eb  mov     [rsp+2C0h+var_298], rcx
  ... truncated ...
```
