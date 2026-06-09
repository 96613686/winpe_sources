# AcquireRequestResources

- ea: `0x1400eb300`
- end: `0x1400ebbf2`
- name: `AcquireRequestResources`
- size: `2290`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `authz_impersonation`

## callers

- `0x1400bc494`
- `0x1400d8aa8`
- `0x1400ebc00`

## callees

- `0x140003620`
- `0x140009cb4`
- `0x14000a210`
- `0x14000b998`
- `0x1400cebf8`
- `0x1400cec8c`
- `0x1400d0af0`
- `0x1400d0b64`
- `0x1400d37c0`
- `0x1400d66b0`
- `0x1400d8e60`
- `0x1400dad50`
- `0x1400db0d0`
- `0x1400dbb20`
- `0x1400dbd50`
- `0x1400dbdd0`
- `0x1400e1b8c`
- `0x1400e228c`
- `0x1400e65a0`
- `0x1400eb300`

## import_xrefs

- `ntoskrnl!MmMdlPageContentsState` at `0x1400eb6b2`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400eb6b2`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400eb564`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400eb564`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400ebb23`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400ebb23`
- `ntoskrnl!MmAreMdlPagesCached` at `0x1400eb5d3`
- `ntoskrnl!MmAreMdlPagesCached` at `0x1400eb5d3`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400ebb85`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400ebb85`
- `ntoskrnl!KeBugCheckEx` at `0x1400eb372`
- `ntoskrnl!KeBugCheckEx` at `0x1400eb372`

## pseudocode

```c
__int64 __fastcall AcquireRequestResources(
        _QWORD *a1,
        __int64 a2,
        char a3,
        unsigned __int64 a4,
        unsigned int a5,
        char a6)
{
  __int64 v6; // r13
  unsigned __int64 v7; // rbp
  char v8; // r12
  __int64 v11; // rdi
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  char v15; // r15
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  char IsIrpWithEfsOffload; // al
  __int64 v20; // r8
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  unsigned int v25; // r14d
  unsigned int v26; // r9d
  unsigned int v27; // ecx
  unsigned int v28; // esi
  int v29; // r9d
  unsigned int v30; // ecx
  int v31; // r8d
  unsigned int v32; // ecx
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // r8
  unsigned __int64 v36; // rcx
  __int64 v37; // rbp
  __int64 v38; // r12
  __int64 v39; // r13
  __int64 v40; // rbp
  unsigned int v41; // ecx
  unsigned int v42; // r8d
  bool v43; // zf
  _DWORD *v44; // r15
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // rax
  __int64 v50; // rax
  unsigned int v51; // eax
  __int64 result; // rax
  unsigned __int64 v53; // rsi
  int v54; // eax
  unsigned __int64 v55; // rcx
  unsigned __int64 v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // rax
  __int64 v59; // rax
  unsigned __int64 v60; // r8
  __int64 v61; // rax
  unsigned __int64 v62; // rcx
  int v63; // eax
  __int64 v64; // rdx
  __int64 v65; // rdx
  PVOID v66; // rax
  __m128i si128; // xmm0
  __int64 v68; // [rsp+40h] [rbp-68h]
  __int64 v69; // [rsp+48h] [rbp-60h]
  __int64 v70; // [rsp+50h] [rbp-58h]
  unsigned __int64 v71; // [rsp+58h] [rbp-50h]
  unsigned int v72; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v73; // [rsp+B8h] [rbp+10h]
  char v74; // [rsp+C0h] [rbp+18h]
  unsigned __int64 v75; // [rsp+C8h] [rbp+20h]

  v75 = a4;
  v74 = a3;
  v73 = a2;
  v6 = a1[1];
  v7 = a4;
  v68 = v6;
  v8 = a3;
  v11 = AcquireControl((ULONG_PTR)a1);
  if ( !v11 )
    return 0;
  IsEnabledDeviceUsageNoInline = Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline();
  v15 = a6;
  if ( IsEnabledDeviceUsageNoInline )
  {
    *(_BYTE *)(v11 + 277) = a6;
  }
  else if ( a6 )
  {
    KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  }
  v16 = *((_DWORD *)a1 + 202);
  v71 = 0;
  if ( (v16 & 0x17F) != 0 && (v16 & 0x40) == 0 )
  {
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v14, v13)
      && (*((_BYTE *)a1 + 4419) & 8) != 0
      || (v17 = a1[122], *(_WORD *)(v17 + 10) == 1) )
    {
      v18 = 0;
    }
    else
    {
      v18 = *(unsigned int *)(v17 + 28);
      if ( !(_DWORD)v18 )
        v18 = 1;
    }
    v71 = v18 * *((unsigned int *)a1 + 327);
  }
  IsIrpWithEfsOffload = FveIsIrpWithEfsOffload(a2, v11 + 280, v11 + 288);
  *(_BYTE *)(v11 + 276) = IsIrpWithEfsOffload;
  if ( IsIrpWithEfsOffload )
  {
    v21 = *((_DWORD *)a1 + 586);
    if ( v8 )
    {
      if ( v21 == 1 )
      {
        _InterlockedIncrement64((volatile signed __int64 *)(a1[294] + 272LL));
      }
      else
      {
        v22 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
        ++*(_QWORD *)(v22 + a1[294] + 272);
      }
    }
    else if ( v21 == 1 )
    {
      _InterlockedIncrement64((volatile signed __int64 *)(a1[294] + 280LL));
    }
    else
    {
      v23 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
      ++*(_QWORD *)(v23 + a1[294] + 280);
    }
  }
  v24 = *(unsigned int *)(v6 + 884);
  v25 = a5;
  if ( v8 )
  {
    v26 = *((_DWORD *)a1 + v24 + 398);
    *(_DWORD *)(v11 + 96) = v26;
    v27 = *((_DWORD *)a1 + *(unsigned int *)(v6 + 884) + 398);
    v28 = (v27 + v25 - 1) / v27;
  }
  else
  {
    v29 = *((_DWORD *)a1 + v24 + 401);
    v30 = 6 * v29;
    v31 = 4 * v29;
    v28 = (2 * v29 < a5) + 1;
    do
    {
      if ( a5 <= v30 )
        break;
      ++v28;
      v31 += 2 * *((_DWORD *)a1 + v24 + 401);
      v30 += v31;
    }
    while ( v28 < 0x20 );
    v26 = 33 * v29;
    v20 = a5 / v28;
    if ( a5 / v28 < v26 )
    {
      v32 = *((_DWORD *)a1 + 327);
      if ( ((v32 - 1) & v32) != 0 || !v32 )
      {
        v26 = a5 / v28;
        if ( (unsigned int)v20 % v32 )
          v26 = v32 + v20 - (unsigned int)v20 % v32;
      }
      else
      {
        v26 = ~(v32 - 1) & (v20 + v32 - 1);
      }
    }
    if ( v26 < 0x100000 && v28 > 1 && (((v26 - 1) & v26) != 0 || !v26) )
    {
      v26 = 1 << (RtlFindMostSignificantBit(v26) + 1);
      v28 = v25 / v26;
      if ( v25 % v26 )
        ++v28;
    }
    *(_DWORD *)(v11 + 96) = v26;
  }
  LOBYTE(v20) = v8;
  FvePerfReportIoSplitSize(a1, v26, v20);
  if ( !v7 && v25 > *((_DWORD *)a1 + 327) )
    ++v28;
  if ( v28 )
  {
    if ( v28 > 0x20 )
      v28 = 32;
  }
  else
  {
    v28 = 1;
  }
  v33 = MmAreMdlPagesCached(*(_QWORD *)(v73 + 8));
  v36 = *(unsigned __int8 *)(v11 + 92);
  *(_BYTE *)(v11 + 272) = v33 != 0;
  if ( (unsigned int)v36 < v28 )
  {
    v69 = 0;
    v70 = 0;
    while ( 1 )
    {
      LOBYTE(v34) = 1;
      v37 = 192LL * (unsigned __int8)v36;
      v72 = *(_DWORD *)(v11 + 96);
      *(_QWORD *)(v11 + v37 + 328) = v11;
      v38 = AcquireSubWorkItem(a1, v34);
      if ( !v38 )
        goto LABEL_75;
      v39 = AcquireSubIrp(a1, a1 + 199, *(unsigned int *)(v6 + 884), &v72);
      if ( !v39 )
        goto LABEL_80;
      v40 = v11 + v37 + 312;
      if ( v74
        || *((_DWORD *)a1 + *(unsigned int *)(v68 + 884) + 425)
        || !*(_BYTE *)(v11 + 272)
        || !(unsigned int)MmMdlPageContentsState(*(_QWORD *)(v73 + 8), 2)
        && ((v41 = *((_DWORD *)a1 + 327), v42 = *(_DWORD *)(*(_QWORD *)(v73 + 8) + 44LL), ((v41 - 1) & v41) != 0)
         || !v41
          ? (v43 = v42 % v41 == 0)
          : (v43 = ((v41 - 1) & v42) == 0),
            !v43)
        || v15 )
      {
        v44 = (_DWORD *)(v40 + 124);
        v45 = AcquireShadowBuffer(a1, v72, v40 + 124);
        *(_QWORD *)(v40 + 96) = v45;
        if ( !v45 )
        {
          ReleaseSubIrp(a1, v39);
LABEL_80:
          ReleaseSubWorkItem(a1, v38);
          goto LABEL_74;
        }
      }
      else
      {
        v44 = (_DWORD *)(v40 + 124);
        *(_DWORD *)(v40 + 124) = v72;
        *(_QWORD *)(v40 + 96) = 0;
      }
      if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline() )
      {
        if ( a6 )
        {
          v69 = FveHwAccelAcquireDescriptor(a1, v46, v47, v48);
          v49 = FveHwAccelAcquireWorkRequest(a1);
          v70 = v49;
          if ( !v69 || !v49 )
          {
            ReleaseSubIrp(a1, v39);
            ReleaseSubWorkItem(a1, v38);
            ReleaseShadowBuffer(a1, *(_QWORD *)(v40 + 96) & 0xFFFFFFFFFFFFFFFCuLL, *(_DWORD *)(v40 + 96) & 3);
            FveHwAccelReleaseDescriptor(a1, v69);
            FveHwAccelReleaseWorkRequest(a1, v70);
LABEL_74:
            v6 = v68;
LABEL_75:
            v8 = v74;
            v7 = v75;
            break;
          }
        }
      }
      FveSetSubrequestState(a1[1], v40, 1);
      *(_DWORD *)(v40 + 120) = *v44;
      *(_QWORD *)(v40 + 32) = v38;
      FveWorkItemInitialize(a1[1], *a1, *((unsigned int *)a1 + 331), v38, 2, ControlAddRef, ControlDeRef, v11);
      *(_QWORD *)(*(_QWORD *)(v40 + 32) + 24LL) = v40;
      *(_QWORD *)(v40 + 40) = v39;
      *(_QWORD *)(v40 + 48) = 0;
      *(_QWORD *)(v40 + 56) = 0;
      *(_QWORD *)(v40 + 64) = 0;
      *(_QWORD *)(v40 + 72) = 0;
      *(_QWORD *)(v40 + 80) = 0;
      *(_QWORD *)(v40 + 112) = 0;
      *(_QWORD *)(v40 + 104) = 0;
      if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline() )
      {
        v36 = v69;
        v50 = v70;
        v69 = 0;
        v70 = 0;
      }
      else
      {
        v50 = 0;
        v36 = 0;
      }
      v6 = v68;
      *(_QWORD *)(v40 + 160) = v36;
      *(_QWORD *)(v40 + 168) = v50;
      LOBYTE(v36) = ++*(_BYTE *)(v11 + 92);
      if ( (unsigned __int8)v36 >= v28 )
      {
        v7 = v75;
        v8 = v74;
        break;
      }
      v15 = a6;
    }
  }
  v51 = *(unsigned __int8 *)(v11 + 92);
  if ( !(_BYTE)v51 )
  {
    ReleaseControl(a1, v11, v35, 1);
    return 0;
  }
  if ( !a1[594] && (unsigned __int8)v51 > 1u )
  {
    if ( v8 )
    {
      if ( *((_DWORD *)a1 + *(unsigned int *)(v6 + 884) + 416) )
      {
LABEL_90:
        v53 = v7 + v25;
        if ( v7 >= v71 || v53 <= v71 )
        {
          if ( !a1[122] )
            goto LABEL_119;
          if ( (v54 = *((_DWORD *)a1 + 202), (v54 & 0x17F) == 0)
            || (v54 & 0x40) != 0
            || ((v55 = a1[132], v7 >= v55 + *((unsigned int *)a1 + 266)) || v53 <= v55)
            && ((v56 = a1[135], v7 >= v56 + *((unsigned int *)a1 + 272)) || v53 <= v56)
            && ((v36 = a1[138], v7 >= v36 + *((unsigned int *)a1 + 278)) || v53 <= v36) )
          {
            if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v36, v34) )
            {
              if ( (*((_BYTE *)a1 + 4419) & 8) != 0 || (v59 = a1[122], *(_WORD *)(v59 + 10) == 1) )
              {
                v58 = 0;
              }
              else
              {
                v58 = *(unsigned int *)(v59 + 28);
                if ( !(_DWORD)v58 )
                  v58 = 1;
              }
              v57 = a1[122];
            }
            else
            {
              v57 = a1[122];
              if ( *(_WORD *)(v57 + 10) == 1 )
              {
                v58 = 0;
              }
              else
              {
                v58 = *(unsigned int *)(v57 + 28);
                if ( !(_DWORD)v58 )
                  v58 = 1;
              }
            }
            v60 = *(_QWORD *)(v57 + 56);
            if ( v7 >= v60 + v58 * *((unsigned int *)a1 + 327) || v53 <= v60 )
            {
              if ( !v57
                || *(_WORD *)(v57 + 12) != 2
                || (v61 = *(unsigned int *)(v57 + 24), !(_DWORD)v61)
                || (v62 = *(_QWORD *)(v57 + 16), v7 >= v62 + v61)
                || v53 <= v62 )
              {
LABEL_119:
                v63 = *((_DWORD *)a1 + 586);
                if ( v8 )
                {
                  if ( v63 == 1 )
                  {
                    _InterlockedIncrement((volatile signed __int32 *)(a1[294] + 132LL));
                  }
                  else
                  {
                    v64 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
                    ++*(_DWORD *)(v64 + a1[294] + 132);
                  }
                }
                else if ( v63 == 1 )
                {
                  _InterlockedIncrement((volatile signed __int32 *)(a1[294] + 144LL));
                }
                else
                {
                  v65 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
                  ++*(_DWORD *)(v65 + a1[294] + 144);
                }
                v66 = ExAllocateFromNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a1[1] + 352LL));
                *(_QWORD *)(v11 + 184) = v66;
                if ( v66 )
                {
                  FveWorkItemInitialize(
                    a1[1],
                    *a1,
                    *((unsigned int *)a1 + 331),
                    v66,
                    1,
                    ControlAddRef,
                    ControlDeRef,
                    v11);
                  KeInitializeSemaphore((PRKSEMAPHORE)(v11 + 200), 0, 0x7FFFFFFF);
                }
                else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                       && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                {
                  WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_4db624899e243eeb5b055379b0b9ae22_Traceguids, a1);
                }
              }
            }
          }
        }
      }
    }
    else
    {
      v36 = *(unsigned int *)(v6 + 884);
      if ( *((_DWORD *)a1 + v36 + 407) && (v51 < v28 || *(_DWORD *)(v11 + 96) < *((_DWORD *)a1 + v36 + 410)) )
        goto LABEL_90;
    }
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  result = v11;
  *(_WORD *)(v11 + 264) = 0;
  *(__m128i *)(v11 + 232) = si128;
  *(__m128i *)(v11 + 248) = si128;
  return result;
}

```

## disassembly

```asm
0x1400eb300  mov     [rsp+arg_18], r9
0x1400eb305  mov     [rsp+arg_10], r8b
0x1400eb30a  mov     [rsp+arg_8], rdx
0x1400eb30f  push    rbx
0x1400eb310  push    rbp
0x1400eb311  push    rsi
0x1400eb312  push    rdi
0x1400eb313  push    r12
0x1400eb315  push    r13
0x1400eb317  push    r14
0x1400eb319  push    r15
0x1400eb31b  sub     rsp, 68h
0x1400eb31f  mov     r13, [rcx+8]
0x1400eb323  mov     rbp, r9
0x1400eb326  mov     [rsp+0A8h+var_68], r13
0x1400eb32b  mov     r12b, r8b
0x1400eb32e  mov     r14, rdx
0x1400eb331  mov     rbx, rcx
0x1400eb334  call    AcquireControl
0x1400eb339  mov     rdi, rax
0x1400eb33c  test    rax, rax
0x1400eb33f  jz      loc_1400EB8D2
0x1400eb345  call    Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline
0x1400eb34a  mov     r15b, [rsp+0A8h+arg_28]
0x1400eb352  test    eax, eax
0x1400eb354  jnz     short loc_1400EB37F
0x1400eb356  test    r15b, r15b
0x1400eb359  jz      short loc_1400EB386
0x1400eb35b  xor     r9d, r9d; BugCheckParameter3
0x1400eb35e  mov     [rsp+0A8h+BugCheckParameter4], 0; BugCheckParameter4
0x1400eb367  xor     r8d, r8d; BugCheckParameter2
0x1400eb36a  lea     edx, [rax+0Ch]; BugCheckParameter1
0x1400eb36d  mov     ecx, 120h; BugCheckCode
0x1400eb372  call    cs:__imp_KeBugCheckEx
0x1400eb37f  mov     [rdi+115h], r15b
0x1400eb386  mov     eax, [rbx+328h]
0x1400eb38c  mov     esi, 1
0x1400eb391  mov     [rsp+0A8h+var_50], 0
0x1400eb39a  test    eax, 17Fh
0x1400eb39f  jz      short loc_1400EB3E4
0x1400eb3a1  test    al, 40h
0x1400eb3a3  jnz     short loc_1400EB3E4
0x1400eb3a5  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400eb3aa  test    eax, eax
0x1400eb3ac  jz      short loc_1400EB3B7
0x1400eb3ae  test    byte ptr [rbx+1143h], 8
0x1400eb3b5  jnz     short loc_1400EB3C4
0x1400eb3b7  mov     rax, [rbx+3D0h]
0x1400eb3be  cmp     [rax+0Ah], si
0x1400eb3c2  jnz     short loc_1400EB3C8
0x1400eb3c4  xor     eax, eax
0x1400eb3c6  jmp     short loc_1400EB3D0
0x1400eb3c8  mov     eax, [rax+1Ch]
0x1400eb3cb  test    eax, eax
0x1400eb3cd  cmovz   eax, esi
0x1400eb3d0  mov     esi, [rbx+51Ch]
0x1400eb3d6  imul    rsi, rax
0x1400eb3da  mov     [rsp+0A8h+var_50], rsi
0x1400eb3df  mov     esi, 1
0x1400eb3e4  lea     r8, [rdi+120h]
0x1400eb3eb  mov     rcx, r14
0x1400eb3ee  lea     rdx, [rdi+118h]
0x1400eb3f5  call    FveIsIrpWithEfsOffload
0x1400eb3fa  mov     [rdi+114h], al
0x1400eb400  test    al, al
0x1400eb402  jz      short loc_1400EB47B
0x1400eb404  mov     eax, [rbx+928h]
0x1400eb40a  test    r12b, r12b
0x1400eb40d  jz      short loc_1400EB446
0x1400eb40f  cmp     eax, esi
0x1400eb411  jnz     short loc_1400EB424
0x1400eb413  mov     rax, [rbx+930h]
0x1400eb41a  lock inc qword ptr [rax+110h]
0x1400eb422  jmp     short loc_1400EB47B
0x1400eb424  mov     eax, gs:1A4h
0x1400eb42c  mov     ecx, eax
0x1400eb42e  mov     rax, [rbx+930h]
0x1400eb435  imul    rdx, rcx, 128h
0x1400eb43c  add     [rdx+rax+110h], rsi
0x1400eb444  jmp     short loc_1400EB47B
0x1400eb446  cmp     eax, esi
0x1400eb448  jnz     short loc_1400EB45B
0x1400eb44a  mov     rax, [rbx+930h]
0x1400eb451  lock inc qword ptr [rax+118h]
0x1400eb459  jmp     short loc_1400EB47B
0x1400eb45b  mov     eax, gs:1A4h
0x1400eb463  mov     ecx, eax
0x1400eb465  mov     rax, [rbx+930h]
0x1400eb46c  imul    rdx, rcx, 128h
0x1400eb473  add     [rdx+rax+118h], rsi
0x1400eb47b  mov     edx, [r13+374h]
0x1400eb482  mov     r14d, [rsp+0A8h+arg_20]
0x1400eb48a  test    r12b, r12b
0x1400eb48d  jz      short loc_1400EB4BA
0x1400eb48f  mov     r9d, [rbx+rdx*4+638h]
0x1400eb497  xor     edx, edx
0x1400eb499  mov     [rdi+60h], r9d
0x1400eb49d  mov     eax, [r13+374h]
0x1400eb4a4  mov     ecx, [rbx+rax*4+638h]
0x1400eb4ab  lea     eax, [r14-1]
0x1400eb4af  add     eax, ecx
0x1400eb4b1  div     ecx
0x1400eb4b3  mov     esi, eax
0x1400eb4b5  jmp     loc_1400EB594
0x1400eb4ba  mov     r9d, [rbx+rdx*4+644h]
0x1400eb4c2  mov     r10d, 1
0x1400eb4c8  lea     ecx, [r9+r9*2]
0x1400eb4cc  add     ecx, ecx
0x1400eb4ce  lea     eax, [r9+r9]
0x1400eb4d2  cmp     eax, r14d
0x1400eb4d5  lea     r8d, ds:0[r9*4]
0x1400eb4dd  sbb     esi, esi
0x1400eb4df  neg     esi
0x1400eb4e1  add     esi, r10d
0x1400eb4e4  cmp     r14d, ecx
0x1400eb4e7  jbe     short loc_1400EB4FF
0x1400eb4e9  mov     eax, [rbx+rdx*4+644h]
0x1400eb4f0  add     esi, r10d
0x1400eb4f3  lea     r8d, [r8+rax*2]
0x1400eb4f7  add     ecx, r8d
0x1400eb4fa  cmp     esi, 20h ; ' '
0x1400eb4fd  jb      short loc_1400EB4E4
0x1400eb4ff  xor     edx, edx
0x1400eb501  imul    r9d, 21h ; '!'
0x1400eb505  mov     eax, r14d
0x1400eb508  div     esi
0x1400eb50a  mov     r8d, eax
0x1400eb50d  cmp     eax, r9d
0x1400eb510  jnb     short loc_1400EB545
0x1400eb512  mov     ecx, [rbx+51Ch]
0x1400eb518  lea     eax, [rcx-1]
0x1400eb51b  test    ecx, eax
0x1400eb51d  jnz     short loc_1400EB531
0x1400eb51f  test    ecx, ecx
0x1400eb521  jz      short loc_1400EB531
0x1400eb523  lea     r9d, [rcx-1]
0x1400eb527  not     eax
0x1400eb529  add     r9d, r8d
0x1400eb52c  and     r9d, eax
0x1400eb52f  jmp     short loc_1400EB545
0x1400eb531  xor     edx, edx
0x1400eb533  mov     eax, r8d
0x1400eb536  div     ecx
0x1400eb538  mov     r9d, r8d
0x1400eb53b  test    edx, edx
0x1400eb53d  jz      short loc_1400EB545
0x1400eb53f  sub     r9d, edx
0x1400eb542  add     r9d, ecx
0x1400eb545  cmp     r9d, 100000h
0x1400eb54c  jnb     short loc_1400EB590
0x1400eb54e  cmp     esi, r10d
0x1400eb551  jbe     short loc_1400EB590
0x1400eb553  lea     eax, [r9-1]
0x1400eb557  test    r9d, eax
0x1400eb55a  jnz     short loc_1400EB561
0x1400eb55c  test    r9d, r9d
0x1400eb55f  jnz     short loc_1400EB590
0x1400eb561  mov     ecx, r9d; Set
0x1400eb564  call    cs:__imp_RtlFindMostSignificantBit
0x1400eb56b  nop     dword ptr [rax+rax+00h]
0x1400eb570  mov     r10d, 1
0x1400eb576  xor     edx, edx
0x1400eb578  mov     r9d, r10d
0x1400eb57b  lea     ecx, [r10+rax]
0x1400eb57f  mov     eax, r14d
0x1400eb582  shl     r9d, cl
0x1400eb585  div     r9d
0x1400eb588  mov     esi, eax
0x1400eb58a  test    edx, edx
0x1400eb58c  jz      short loc_1400EB590
0x1400eb58e  inc     esi
0x1400eb590  mov     [rdi+60h], r9d
0x1400eb594  mov     r8b, r12b
0x1400eb597  mov     edx, r9d
0x1400eb59a  mov     rcx, rbx
0x1400eb59d  call    FvePerfReportIoSplitSize
0x1400eb5a2  test    rbp, rbp
0x1400eb5a5  jnz     short loc_1400EB5B2
0x1400eb5a7  cmp     r14d, [rbx+51Ch]
0x1400eb5ae  jbe     short loc_1400EB5B2
0x1400eb5b0  inc     esi
0x1400eb5b2  test    esi, esi
0x1400eb5b4  jnz     short loc_1400EB5BD
0x1400eb5b6  mov     esi, 1
0x1400eb5bb  jmp     short loc_1400EB5C7
0x1400eb5bd  mov     eax, 20h ; ' '
0x1400eb5c2  cmp     esi, eax
0x1400eb5c4  cmova   esi, eax
0x1400eb5c7  mov     rcx, [rsp+0A8h+arg_8]
0x1400eb5cf  mov     rcx, [rcx+8]
0x1400eb5d3  call    cs:__imp_MmAreMdlPagesCached
0x1400eb5da  nop     dword ptr [rax+rax+00h]
0x1400eb5df  movzx   ecx, byte ptr [rdi+5Ch]
0x1400eb5e3  mov     r9d, 1
0x1400eb5e9  test    eax, eax
0x1400eb5eb  setnz   al
0x1400eb5ee  mov     [rdi+110h], al
0x1400eb5f4  cmp     ecx, esi
0x1400eb5f6  jnb     loc_1400EB8BC
0x1400eb5fc  mov     [rsp+0A8h+var_60], 0
0x1400eb605  mov     [rsp+0A8h+var_58], 0
0x1400eb60e  movzx   eax, cl
0x1400eb611  mov     dl, r9b
0x1400eb614  mov     rcx, rbx
0x1400eb617  lea     rbp, [rax+rax*2]
0x1400eb61b  mov     eax, [rdi+60h]
0x1400eb61e  shl     rbp, 6
0x1400eb622  mov     [rsp+0A8h+arg_0], eax
0x1400eb629  mov     [rdi+rbp+148h], rdi
0x1400eb631  call    AcquireSubWorkItem
0x1400eb636  mov     r12, rax
0x1400eb639  test    rax, rax
0x1400eb63c  jz      loc_1400EB8A6
0x1400eb642  mov     r8d, [r13+374h]
0x1400eb649  lea     rdx, [rbx+638h]
0x1400eb650  lea     r9, [rsp+0A8h+arg_0]
0x1400eb658  mov     rcx, rbx
0x1400eb65b  call    AcquireSubIrp
0x1400eb660  xor     edx, edx
0x1400eb662  mov     r13, rax
0x1400eb665  test    rax, rax
0x1400eb668  jz      loc_1400EB8F1
0x1400eb66e  add     rbp, 138h
0x1400eb675  add     rbp, rdi
0x1400eb678  cmp     [rsp+0A8h+arg_10], dl
0x1400eb67f  jnz     loc_1400EB710
0x1400eb685  mov     rax, [rsp+0A8h+var_68]
0x1400eb68a  mov     ecx, [rax+374h]
0x1400eb690  cmp     [rbx+rcx*4+6A4h], edx
0x1400eb697  jnz     short loc_1400EB710
0x1400eb699  cmp     [rdi+110h], dl
0x1400eb69f  jz      short loc_1400EB710
0x1400eb6a1  mov     rax, [rsp+0A8h+arg_8]
0x1400eb6a9  mov     edx, 2
0x1400eb6ae  mov     rcx, [rax+8]
0x1400eb6b2  call    cs:__imp_MmMdlPageContentsState
0x1400eb6b9  nop     dword ptr [rax+rax+00h]
0x1400eb6be  test    eax, eax
0x1400eb6c0  jnz     short loc_1400EB6F3
0x1400eb6c2  mov     ecx, [rbx+51Ch]
0x1400eb6c8  mov     rax, [rsp+0A8h+arg_8]
0x1400eb6d0  mov     rax, [rax+8]
0x1400eb6d4  mov     r8d, [rax+2Ch]
0x1400eb6d8  lea     eax, [rcx-1]
0x1400eb6db  test    ecx, eax
0x1400eb6dd  jnz     short loc_1400EB6E8
0x1400eb6df  test    ecx, ecx
0x1400eb6e1  jz      short loc_1400EB6E8
0x1400eb6e3  test    r8d, eax
0x1400eb6e6  jmp     short loc_1400EB6F1
0x1400eb6e8  xor     edx, edx
0x1400eb6ea  mov     eax, r8d
0x1400eb6ed  div     ecx
0x1400eb6ef  test    edx, edx
0x1400eb6f1  jnz     short loc_1400EB710
0x1400eb6f3  test    r15b, r15b
0x1400eb6f6  jnz     short loc_1400EB710
0x1400eb6f8  mov     eax, [rsp+0A8h+arg_0]
0x1400eb6ff  lea     r15, [rbp+7Ch]
0x1400eb703  mov     [r15], eax
0x1400eb706  mov     qword ptr [rbp+60h], 0
0x1400eb70e  jmp     short loc_1400EB733
0x1400eb710  mov     edx, [rsp+0A8h+arg_0]
0x1400eb717  lea     r15, [rbp+7Ch]
0x1400eb71b  mov     r8, r15
0x1400eb71e  mov     rcx, rbx
0x1400eb721  call    AcquireShadowBuffer
0x1400eb726  mov     [rbp+60h], rax
0x1400eb72a  test    rax, rax
0x1400eb72d  jz      loc_1400EB8E6
0x1400eb733  call    Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline
0x1400eb738  test    eax, eax
0x1400eb73a  jz      short loc_1400EB775
0x1400eb73c  cmp     [rsp+0A8h+arg_28], 0
0x1400eb744  jz      short loc_1400EB775
0x1400eb746  mov     rcx, rbx
0x1400eb749  call    FveHwAccelAcquireDescriptor
0x1400eb74e  mov     rcx, rbx
0x1400eb751  mov     [rsp+0A8h+var_60], rax
0x1400eb756  call    FveHwAccelAcquireWorkRequest
0x1400eb75b  cmp     [rsp+0A8h+var_60], 0
0x1400eb761  mov     [rsp+0A8h+var_58], rax
0x1400eb766  jz      loc_1400EB859
0x1400eb76c  test    rax, rax
0x1400eb76f  jz      loc_1400EB859
0x1400eb775  mov     rcx, [rbx+8]
0x1400eb779  mov     r8d, 1
0x1400eb77f  mov     rdx, rbp
0x1400eb782  mov     byte ptr [rsp+0A8h+BugCheckParameter4], 0
0x1400eb787  call    FveSetSubrequestState
0x1400eb78c  mov     ecx, [r15]
0x1400eb78f  lea     rax, ControlDeRef
0x1400eb796  mov     [rbp+78h], ecx
0x1400eb799  mov     r9, r12
0x1400eb79c  mov     [rbp+20h], r12
0x1400eb7a0  mov     r8d, [rbx+52Ch]
0x1400eb7a7  mov     rdx, [rbx]
0x1400eb7aa  mov     rcx, [rbx+8]
0x1400eb7ae  mov     [rsp+0A8h+var_70], rdi
0x1400eb7b3  mov     [rsp+0A8h+var_78], rax
  ... truncated ...
```
