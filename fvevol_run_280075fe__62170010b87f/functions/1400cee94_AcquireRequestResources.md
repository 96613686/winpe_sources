# AcquireRequestResources

- ea: `0x1400cee94`
- end: `0x1400cf62e`
- name: `AcquireRequestResources`
- size: `1946`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x1400d45c8`
- `0x1400e8a30`

## callees

- `0x140003610`
- `0x140009bf4`
- `0x14000a150`
- `0x1400ced90`
- `0x1400cee94`
- `0x1400cf640`
- `0x1400cf770`
- `0x1400cf868`
- `0x1400cf970`
- `0x1400cfa10`
- `0x1400cfb90`
- `0x1400cfca0`
- `0x1400d0570`
- `0x1400d4980`

## import_xrefs

- `ntoskrnl!MmMdlPageContentsState` at `0x1400cf1d7`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400cf1d7`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400cf0b9`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400cf0b9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400cf55f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400cf55f`
- `ntoskrnl!MmAreMdlPagesCached` at `0x1400cf120`
- `ntoskrnl!MmAreMdlPagesCached` at `0x1400cf120`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400cf5c1`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400cf5c1`

## pseudocode

```c
__int64 __fastcall AcquireRequestResources(_QWORD *a1, __int64 a2, char a3, unsigned __int64 a4, unsigned int a5)
{
  __int64 v5; // r14
  __int64 v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rax
  char IsIrpWithEfsOffload; // al
  __int64 v14; // r8
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  unsigned int v19; // r12d
  unsigned int v20; // r9d
  unsigned int v21; // ecx
  unsigned int v22; // esi
  int v23; // r9d
  unsigned int v24; // ecx
  int v25; // r8d
  unsigned int v26; // ecx
  __int64 v27; // rdx
  unsigned __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rbp
  __int64 v31; // r15
  __int64 v32; // r13
  __int64 v33; // r14
  unsigned int v34; // ecx
  unsigned int v35; // r8d
  bool v36; // zf
  _DWORD *v37; // r14
  __int64 v38; // rax
  unsigned int v39; // eax
  __int64 result; // rax
  char v41; // r13
  unsigned __int64 v42; // rbp
  unsigned __int64 v43; // rsi
  unsigned __int64 v44; // rcx
  unsigned __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rax
  unsigned __int64 v49; // r8
  __int64 v50; // rax
  unsigned __int64 v51; // rcx
  int v52; // eax
  __int64 v53; // rdx
  __int64 v54; // rdx
  PVOID v55; // rax
  __m128i si128; // xmm0
  __int64 v57; // [rsp+40h] [rbp-58h]
  unsigned __int64 v58; // [rsp+48h] [rbp-50h]
  unsigned int v59; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v60; // [rsp+A8h] [rbp+10h]
  char v61; // [rsp+B0h] [rbp+18h]
  unsigned __int64 v62; // [rsp+B8h] [rbp+20h]

  v62 = a4;
  v61 = a3;
  v60 = a2;
  v5 = a1[1];
  v57 = v5;
  v10 = AcquireControl((ULONG_PTR)a1);
  if ( !v10 )
    return 0;
  v58 = 0;
  if ( (a1[101] & 0x17F) != 0 && (a1[101] & 0x40) == 0 )
  {
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(*((unsigned int *)a1 + 202))
      && (*((_BYTE *)a1 + 4403) & 8) != 0
      || (v11 = a1[122], *(_WORD *)(v11 + 10) == 1) )
    {
      v12 = 0;
    }
    else
    {
      v12 = *(unsigned int *)(v11 + 28);
      if ( !(_DWORD)v12 )
        v12 = 1;
    }
    v58 = v12 * *((unsigned int *)a1 + 327);
  }
  IsIrpWithEfsOffload = FveIsIrpWithEfsOffload(a2, v10 + 280, v10 + 288);
  *(_BYTE *)(v10 + 276) = IsIrpWithEfsOffload;
  if ( IsIrpWithEfsOffload )
  {
    v15 = *((_DWORD *)a1 + 582);
    if ( a3 )
    {
      if ( v15 == 1 )
      {
        _InterlockedIncrement64((volatile signed __int64 *)(a1[292] + 272LL));
      }
      else
      {
        v16 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
        ++*(_QWORD *)(v16 + a1[292] + 272);
      }
    }
    else if ( v15 == 1 )
    {
      _InterlockedIncrement64((volatile signed __int64 *)(a1[292] + 280LL));
    }
    else
    {
      v17 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
      ++*(_QWORD *)(v17 + a1[292] + 280);
    }
  }
  v18 = *(unsigned int *)(v5 + 884);
  v19 = a5;
  if ( a3 )
  {
    v20 = *((_DWORD *)a1 + v18 + 398);
    *(_DWORD *)(v10 + 96) = v20;
    v21 = *((_DWORD *)a1 + *(unsigned int *)(v5 + 884) + 398);
    v22 = (v21 + v19 - 1) / v21;
  }
  else
  {
    v23 = *((_DWORD *)a1 + v18 + 401);
    v24 = 6 * v23;
    v25 = 4 * v23;
    v22 = (2 * v23 < a5) + 1;
    do
    {
      if ( a5 <= v24 )
        break;
      v25 += 2 * v23;
      ++v22;
      v24 += v25;
    }
    while ( v22 < 0x20 );
    v20 = 33 * v23;
    v14 = a5 / v22;
    if ( a5 / v22 < v20 )
    {
      v26 = *((_DWORD *)a1 + 327);
      if ( ((v26 - 1) & v26) != 0 || !v26 )
      {
        v20 = a5 / v22;
        if ( (unsigned int)v14 % v26 )
          v20 = v26 + v14 - (unsigned int)v14 % v26;
      }
      else
      {
        v20 = ~(v26 - 1) & (v14 + v26 - 1);
      }
    }
    if ( v20 < 0x100000 && v22 > 1 && (((v20 - 1) & v20) != 0 || !v20) )
    {
      v20 = 1 << (RtlFindMostSignificantBit(v20) + 1);
      v22 = v19 / v20;
      if ( v19 % v20 )
        ++v22;
    }
    *(_DWORD *)(v10 + 96) = v20;
  }
  LOBYTE(v14) = a3;
  FvePerfReportIoSplitSize(a1, v20, v14);
  if ( !a4 && v19 > *((_DWORD *)a1 + 327) )
    ++v22;
  if ( v22 )
  {
    if ( v22 > 0x20 )
      v22 = 32;
  }
  else
  {
    v22 = 1;
  }
  *(_BYTE *)(v10 + 272) = (unsigned int)MmAreMdlPagesCached(*(_QWORD *)(a2 + 8)) != 0;
  while ( 1 )
  {
    v29 = *(unsigned __int8 *)(v10 + 92);
    if ( (unsigned int)v29 >= v22 )
      break;
    LOBYTE(v27) = 1;
    v59 = *(_DWORD *)(v10 + 96);
    v30 = v10 + 176 * v29 + 296;
    *(_QWORD *)(v30 + 16) = v10;
    v31 = AcquireSubWorkItem(a1, v27);
    if ( !v31 )
      break;
    v32 = AcquireSubIrp(a1, a1 + 199, *(unsigned int *)(v5 + 884), &v59);
    if ( !v32 )
    {
      ReleaseSubWorkItem(a1, v31);
      break;
    }
    if ( !v61
      && !*((_DWORD *)a1 + *(unsigned int *)(v5 + 884) + 425)
      && *(_BYTE *)(v10 + 272)
      && ((v33 = v60, (unsigned int)MmMdlPageContentsState(*(_QWORD *)(v60 + 8), 2))
       || ((v34 = *((_DWORD *)a1 + 327), v35 = *(_DWORD *)(*(_QWORD *)(v33 + 8) + 44LL), ((v34 - 1) & v34) != 0) || !v34
         ? (v36 = v35 % v34 == 0)
         : (v36 = ((v34 - 1) & v35) == 0),
           v36)) )
    {
      v37 = (_DWORD *)(v30 + 124);
      *(_DWORD *)(v30 + 124) = v59;
      *(_QWORD *)(v30 + 96) = 0;
    }
    else
    {
      v37 = (_DWORD *)(v30 + 124);
      v38 = AcquireShadowBuffer(a1, v59, v30 + 124);
      *(_QWORD *)(v30 + 96) = v38;
      if ( !v38 )
      {
        ReleaseSubIrp(a1, v32);
        ReleaseSubWorkItem(a1, v31);
        v5 = v57;
        break;
      }
    }
    FveSetSubrequestState(a1[1], v30, 1);
    *(_DWORD *)(v30 + 120) = *v37;
    *(_QWORD *)(v30 + 32) = v31;
    FveWorkItemInitialize(a1[1], *a1, *((unsigned int *)a1 + 331), v31, 2, ControlAddRef, ControlDeRef, v10);
    v5 = v57;
    *(_QWORD *)(*(_QWORD *)(v30 + 32) + 24LL) = v30;
    *(_QWORD *)(v30 + 40) = v32;
    *(_QWORD *)(v30 + 48) = 0;
    *(_QWORD *)(v30 + 56) = 0;
    *(_QWORD *)(v30 + 64) = 0;
    *(_QWORD *)(v30 + 72) = 0;
    *(_QWORD *)(v30 + 80) = 0;
    *(_QWORD *)(v30 + 112) = 0;
    *(_QWORD *)(v30 + 104) = 0;
    ++*(_BYTE *)(v10 + 92);
  }
  v39 = *(unsigned __int8 *)(v10 + 92);
  if ( !(_BYTE)v39 )
  {
    ReleaseControl((__int64)a1, (unsigned int *)v10);
    return 0;
  }
  if ( !a1[592] && (unsigned __int8)v39 > 1u )
  {
    v41 = v61;
    if ( v61 )
    {
      if ( !*((_DWORD *)a1 + *(unsigned int *)(v5 + 884) + 416) )
        goto LABEL_113;
    }
    else
    {
      v28 = *(unsigned int *)(v5 + 884);
      if ( !*((_DWORD *)a1 + v28 + 407) || v39 >= v22 && *(_DWORD *)(v10 + 96) >= *((_DWORD *)a1 + v28 + 410) )
        goto LABEL_113;
    }
    v42 = v62;
    v43 = v62 + v19;
    if ( v62 >= v58 || v43 <= v58 )
    {
      if ( !a1[122] )
        goto LABEL_100;
      LOBYTE(v28) = (a1[101] & 0x17F) != 0;
      if ( ((unsigned __int8)v28 & ((a1[101] & 0x40) == 0)) == 0
        || ((v44 = a1[132], v62 >= v44 + *((unsigned int *)a1 + 266)) || v43 <= v44)
        && ((v45 = a1[135], v62 >= v45 + *((unsigned int *)a1 + 272)) || v43 <= v45)
        && ((v28 = a1[138], v62 >= v28 + *((unsigned int *)a1 + 278)) || v43 <= v28) )
      {
        if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v28) )
        {
          if ( (*((_BYTE *)a1 + 4403) & 8) != 0 || (v48 = a1[122], *(_WORD *)(v48 + 10) == 1) )
          {
            v47 = 0;
          }
          else
          {
            v47 = *(unsigned int *)(v48 + 28);
            if ( !(_DWORD)v47 )
              v47 = 1;
          }
          v46 = a1[122];
        }
        else
        {
          v46 = a1[122];
          if ( *(_WORD *)(v46 + 10) == 1 )
          {
            v47 = 0;
          }
          else
          {
            v47 = *(unsigned int *)(v46 + 28);
            if ( !(_DWORD)v47 )
              v47 = 1;
          }
        }
        v49 = *(_QWORD *)(v46 + 56);
        if ( v42 >= v49 + v47 * *((unsigned int *)a1 + 327) || v43 <= v49 )
        {
          if ( !v46
            || *(_WORD *)(v46 + 12) != 2
            || (v50 = *(unsigned int *)(v46 + 24), !(_DWORD)v50)
            || (v51 = *(_QWORD *)(v46 + 16), v42 >= v51 + v50)
            || v43 <= v51 )
          {
LABEL_100:
            v52 = *((_DWORD *)a1 + 582);
            if ( v41 )
            {
              if ( v52 == 1 )
              {
                _InterlockedIncrement((volatile signed __int32 *)(a1[292] + 132LL));
              }
              else
              {
                v53 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
                ++*(_DWORD *)(v53 + a1[292] + 132);
              }
            }
            else if ( v52 == 1 )
            {
              _InterlockedIncrement((volatile signed __int32 *)(a1[292] + 144LL));
            }
            else
            {
              v54 = 296LL * HIDWORD(KeGetPcr()[1].LockArray);
              ++*(_DWORD *)(v54 + a1[292] + 144);
            }
            v55 = ExAllocateFromNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a1[1] + 352LL));
            *(_QWORD *)(v10 + 184) = v55;
            if ( v55 )
            {
              FveWorkItemInitialize(a1[1], *a1, *((unsigned int *)a1 + 331), v55, 1, ControlAddRef, ControlDeRef, v10);
              KeInitializeSemaphore((PRKSEMAPHORE)(v10 + 200), 0, 0x7FFFFFFF);
            }
            else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_967c1297b27d3b8fbf952ae9e74b6717_Traceguids, a1);
            }
          }
        }
      }
    }
  }
LABEL_113:
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  result = v10;
  *(_WORD *)(v10 + 264) = 0;
  *(__m128i *)(v10 + 232) = si128;
  *(__m128i *)(v10 + 248) = si128;
  return result;
}

```

## disassembly

```asm
0x1400cee94  mov     [rsp+arg_18], r9
0x1400cee99  mov     [rsp+arg_10], r8b
0x1400cee9e  mov     [rsp+arg_8], rdx
0x1400ceea3  push    rbx
0x1400ceea4  push    rbp
0x1400ceea5  push    rsi
0x1400ceea6  push    rdi
0x1400ceea7  push    r12
0x1400ceea9  push    r13
0x1400ceeab  push    r14
0x1400ceead  push    r15
0x1400ceeaf  sub     rsp, 58h
0x1400ceeb3  mov     r14, [rcx+8]
0x1400ceeb7  mov     rbp, r9
0x1400ceeba  mov     [rsp+98h+var_58], r14
0x1400ceebf  mov     r13b, r8b
0x1400ceec2  mov     r15, rdx
0x1400ceec5  mov     rbx, rcx
0x1400ceec8  call    AcquireControl
0x1400ceecd  mov     rdi, rax
0x1400ceed0  test    rax, rax
0x1400ceed3  jz      loc_1400CF31D
0x1400ceed9  mov     ecx, [rbx+328h]
0x1400ceedf  mov     esi, 1
0x1400ceee4  test    ecx, 17Fh
0x1400ceeea  mov     [rsp+98h+var_50], 0
0x1400ceef3  setnz   dl
0x1400ceef6  test    cl, 40h
0x1400ceef9  setz    al
0x1400ceefc  test    al, dl
0x1400ceefe  jz      short loc_1400CEF3F
0x1400cef00  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400cef05  test    eax, eax
0x1400cef07  jz      short loc_1400CEF12
0x1400cef09  test    byte ptr [rbx+1133h], 8
0x1400cef10  jnz     short loc_1400CEF1F
0x1400cef12  mov     rax, [rbx+3D0h]
0x1400cef19  cmp     [rax+0Ah], si
0x1400cef1d  jnz     short loc_1400CEF23
0x1400cef1f  xor     eax, eax
0x1400cef21  jmp     short loc_1400CEF2B
0x1400cef23  mov     eax, [rax+1Ch]
0x1400cef26  test    eax, eax
0x1400cef28  cmovz   eax, esi
0x1400cef2b  mov     esi, [rbx+51Ch]
0x1400cef31  imul    rsi, rax
0x1400cef35  mov     [rsp+98h+var_50], rsi
0x1400cef3a  mov     esi, 1
0x1400cef3f  lea     r8, [rdi+120h]
0x1400cef46  mov     rcx, r15
0x1400cef49  lea     rdx, [rdi+118h]
0x1400cef50  call    FveIsIrpWithEfsOffload
0x1400cef55  mov     [rdi+114h], al
0x1400cef5b  test    al, al
0x1400cef5d  jz      short loc_1400CEFD6
0x1400cef5f  mov     eax, [rbx+918h]
0x1400cef65  test    r13b, r13b
0x1400cef68  jz      short loc_1400CEFA1
0x1400cef6a  cmp     eax, esi
0x1400cef6c  jnz     short loc_1400CEF7F
0x1400cef6e  mov     rax, [rbx+920h]
0x1400cef75  lock inc qword ptr [rax+110h]
0x1400cef7d  jmp     short loc_1400CEFD6
0x1400cef7f  mov     eax, gs:1A4h
0x1400cef87  mov     ecx, eax
0x1400cef89  mov     rax, [rbx+920h]
0x1400cef90  imul    rdx, rcx, 128h
0x1400cef97  add     [rdx+rax+110h], rsi
0x1400cef9f  jmp     short loc_1400CEFD6
0x1400cefa1  cmp     eax, esi
0x1400cefa3  jnz     short loc_1400CEFB6
0x1400cefa5  mov     rax, [rbx+920h]
0x1400cefac  lock inc qword ptr [rax+118h]
0x1400cefb4  jmp     short loc_1400CEFD6
0x1400cefb6  mov     eax, gs:1A4h
0x1400cefbe  mov     ecx, eax
0x1400cefc0  mov     rax, [rbx+920h]
0x1400cefc7  imul    rdx, rcx, 128h
0x1400cefce  add     [rdx+rax+118h], rsi
0x1400cefd6  mov     edx, [r14+374h]
0x1400cefdd  mov     r12d, [rsp+98h+arg_20]
0x1400cefe5  test    r13b, r13b
0x1400cefe8  jz      short loc_1400CF016
0x1400cefea  mov     r9d, [rbx+rdx*4+638h]
0x1400ceff2  xor     edx, edx
0x1400ceff4  mov     [rdi+60h], r9d
0x1400ceff8  mov     eax, [r14+374h]
0x1400cefff  mov     ecx, [rbx+rax*4+638h]
0x1400cf006  lea     eax, [r12-1]
0x1400cf00b  add     eax, ecx
0x1400cf00d  div     ecx
0x1400cf00f  mov     esi, eax
0x1400cf011  jmp     loc_1400CF0E9
0x1400cf016  mov     r9d, [rbx+rdx*4+644h]
0x1400cf01e  mov     r10d, 1
0x1400cf024  lea     ecx, [r9+r9*2]
0x1400cf028  add     ecx, ecx
0x1400cf02a  lea     eax, [r9+r9]
0x1400cf02e  cmp     eax, r12d
0x1400cf031  lea     r8d, ds:0[r9*4]
0x1400cf039  sbb     esi, esi
0x1400cf03b  neg     esi
0x1400cf03d  add     esi, r10d
0x1400cf040  cmp     r12d, ecx
0x1400cf043  jbe     short loc_1400CF054
0x1400cf045  lea     r8d, [r8+r9*2]
0x1400cf049  add     esi, r10d
0x1400cf04c  add     ecx, r8d
0x1400cf04f  cmp     esi, 20h ; ' '
0x1400cf052  jb      short loc_1400CF040
0x1400cf054  xor     edx, edx
0x1400cf056  imul    r9d, 21h ; '!'
0x1400cf05a  mov     eax, r12d
0x1400cf05d  div     esi
0x1400cf05f  mov     r8d, eax
0x1400cf062  cmp     eax, r9d
0x1400cf065  jnb     short loc_1400CF09A
0x1400cf067  mov     ecx, [rbx+51Ch]
0x1400cf06d  lea     eax, [rcx-1]
0x1400cf070  test    ecx, eax
0x1400cf072  jnz     short loc_1400CF086
0x1400cf074  test    ecx, ecx
0x1400cf076  jz      short loc_1400CF086
0x1400cf078  lea     r9d, [rcx-1]
0x1400cf07c  not     eax
0x1400cf07e  add     r9d, r8d
0x1400cf081  and     r9d, eax
0x1400cf084  jmp     short loc_1400CF09A
0x1400cf086  xor     edx, edx
0x1400cf088  mov     eax, r8d
0x1400cf08b  div     ecx
0x1400cf08d  mov     r9d, r8d
0x1400cf090  test    edx, edx
0x1400cf092  jz      short loc_1400CF09A
0x1400cf094  sub     r9d, edx
0x1400cf097  add     r9d, ecx
0x1400cf09a  cmp     r9d, 100000h
0x1400cf0a1  jnb     short loc_1400CF0E5
0x1400cf0a3  cmp     esi, r10d
0x1400cf0a6  jbe     short loc_1400CF0E5
0x1400cf0a8  lea     eax, [r9-1]
0x1400cf0ac  test    r9d, eax
0x1400cf0af  jnz     short loc_1400CF0B6
0x1400cf0b1  test    r9d, r9d
0x1400cf0b4  jnz     short loc_1400CF0E5
0x1400cf0b6  mov     ecx, r9d; Set
0x1400cf0b9  call    cs:__imp_RtlFindMostSignificantBit
0x1400cf0c0  nop     dword ptr [rax+rax+00h]
0x1400cf0c5  mov     r10d, 1
0x1400cf0cb  xor     edx, edx
0x1400cf0cd  mov     r9d, r10d
0x1400cf0d0  lea     ecx, [r10+rax]
0x1400cf0d4  mov     eax, r12d
0x1400cf0d7  shl     r9d, cl
0x1400cf0da  div     r9d
0x1400cf0dd  mov     esi, eax
0x1400cf0df  test    edx, edx
0x1400cf0e1  jz      short loc_1400CF0E5
0x1400cf0e3  inc     esi
0x1400cf0e5  mov     [rdi+60h], r9d
0x1400cf0e9  mov     r8b, r13b
0x1400cf0ec  mov     edx, r9d
0x1400cf0ef  mov     rcx, rbx
0x1400cf0f2  call    FvePerfReportIoSplitSize
0x1400cf0f7  test    rbp, rbp
0x1400cf0fa  jnz     short loc_1400CF107
0x1400cf0fc  cmp     r12d, [rbx+51Ch]
0x1400cf103  jbe     short loc_1400CF107
0x1400cf105  inc     esi
0x1400cf107  test    esi, esi
0x1400cf109  jnz     short loc_1400CF112
0x1400cf10b  mov     esi, 1
0x1400cf110  jmp     short loc_1400CF11C
0x1400cf112  mov     eax, 20h ; ' '
0x1400cf117  cmp     esi, eax
0x1400cf119  cmova   esi, eax
0x1400cf11c  mov     rcx, [r15+8]
0x1400cf120  call    cs:__imp_MmAreMdlPagesCached
0x1400cf127  nop     dword ptr [rax+rax+00h]
0x1400cf12c  xor     r15d, r15d
0x1400cf12f  test    eax, eax
0x1400cf131  setnz   al
0x1400cf134  mov     [rdi+110h], al
0x1400cf13a  movzx   eax, byte ptr [rdi+5Ch]
0x1400cf13e  cmp     eax, esi
0x1400cf140  jnb     loc_1400CF30A
0x1400cf146  imul    rbp, rax, 0B0h
0x1400cf14d  mov     eax, [rdi+60h]
0x1400cf150  mov     dl, 1
0x1400cf152  add     rbp, 128h
0x1400cf159  mov     [rsp+98h+arg_0], eax
0x1400cf160  add     rbp, rdi
0x1400cf163  mov     rcx, rbx
0x1400cf166  mov     [rbp+10h], rdi
0x1400cf16a  call    AcquireSubWorkItem
0x1400cf16f  mov     r15, rax
0x1400cf172  test    rax, rax
0x1400cf175  jz      loc_1400CF307
0x1400cf17b  mov     r8d, [r14+374h]
0x1400cf182  lea     rdx, [rbx+638h]
0x1400cf189  lea     r9, [rsp+98h+arg_0]
0x1400cf191  mov     rcx, rbx
0x1400cf194  call    AcquireSubIrp
0x1400cf199  mov     r13, rax
0x1400cf19c  xor     eax, eax
0x1400cf19e  test    r13, r13
0x1400cf1a1  jz      loc_1400CF2FC
0x1400cf1a7  cmp     [rsp+98h+arg_10], al
0x1400cf1ae  jnz     short loc_1400CF228
0x1400cf1b0  mov     ecx, [r14+374h]
0x1400cf1b7  cmp     [rbx+rcx*4+6A4h], eax
0x1400cf1be  jnz     short loc_1400CF228
0x1400cf1c0  cmp     [rdi+110h], al
0x1400cf1c6  jz      short loc_1400CF228
0x1400cf1c8  mov     r14, [rsp+98h+arg_8]
0x1400cf1d0  lea     edx, [rax+2]
0x1400cf1d3  mov     rcx, [r14+8]
0x1400cf1d7  call    cs:__imp_MmMdlPageContentsState
0x1400cf1de  nop     dword ptr [rax+rax+00h]
0x1400cf1e3  test    eax, eax
0x1400cf1e5  jnz     short loc_1400CF210
0x1400cf1e7  mov     rax, [r14+8]
0x1400cf1eb  mov     ecx, [rbx+51Ch]
0x1400cf1f1  mov     r8d, [rax+2Ch]
0x1400cf1f5  lea     eax, [rcx-1]
0x1400cf1f8  test    ecx, eax
0x1400cf1fa  jnz     short loc_1400CF205
0x1400cf1fc  test    ecx, ecx
0x1400cf1fe  jz      short loc_1400CF205
0x1400cf200  test    r8d, eax
0x1400cf203  jmp     short loc_1400CF20E
0x1400cf205  xor     edx, edx
0x1400cf207  mov     eax, r8d
0x1400cf20a  div     ecx
0x1400cf20c  test    edx, edx
0x1400cf20e  jnz     short loc_1400CF228
0x1400cf210  mov     eax, [rsp+98h+arg_0]
0x1400cf217  lea     r14, [rbp+7Ch]
0x1400cf21b  mov     [r14], eax
0x1400cf21e  mov     qword ptr [rbp+60h], 0
0x1400cf226  jmp     short loc_1400CF24B
0x1400cf228  mov     edx, [rsp+98h+arg_0]
0x1400cf22f  lea     r14, [rbp+7Ch]
0x1400cf233  mov     r8, r14
0x1400cf236  mov     rcx, rbx
0x1400cf239  call    AcquireShadowBuffer
0x1400cf23e  mov     [rbp+60h], rax
0x1400cf242  test    rax, rax
0x1400cf245  jz      loc_1400CF2DF
0x1400cf24b  mov     rcx, [rbx+8]
0x1400cf24f  mov     r8d, 1
0x1400cf255  mov     rdx, rbp
0x1400cf258  mov     byte ptr [rsp+98h+var_78], 0
0x1400cf25d  call    FveSetSubrequestState
0x1400cf262  mov     eax, [r14]
0x1400cf265  mov     r9, r15
0x1400cf268  mov     [rbp+78h], eax
0x1400cf26b  lea     rax, ControlDeRef
0x1400cf272  mov     [rbp+20h], r15
0x1400cf276  mov     r8d, [rbx+52Ch]
0x1400cf27d  mov     rdx, [rbx]
0x1400cf280  mov     rcx, [rbx+8]
0x1400cf284  mov     [rsp+98h+var_60], rdi
0x1400cf289  mov     [rsp+98h+var_68], rax
0x1400cf28e  lea     rax, ControlAddRef
0x1400cf295  mov     [rsp+98h+var_70], rax
0x1400cf29a  mov     [rsp+98h+var_78], 2
0x1400cf2a2  call    FveWorkItemInitialize
0x1400cf2a7  mov     rax, [rbp+20h]
0x1400cf2ab  xor     r15d, r15d
0x1400cf2ae  mov     r14, [rsp+98h+var_58]
0x1400cf2b3  mov     [rax+18h], rbp
0x1400cf2b7  mov     [rbp+28h], r13
0x1400cf2bb  mov     [rbp+30h], r15
0x1400cf2bf  mov     [rbp+38h], r15
0x1400cf2c3  mov     [rbp+40h], r15
0x1400cf2c7  mov     [rbp+48h], r15
0x1400cf2cb  mov     [rbp+50h], r15
0x1400cf2cf  mov     [rbp+70h], r15
0x1400cf2d3  mov     [rbp+68h], r15
0x1400cf2d7  inc     byte ptr [rdi+5Ch]
0x1400cf2da  jmp     loc_1400CF13A
0x1400cf2df  mov     rdx, r13
0x1400cf2e2  mov     rcx, rbx
0x1400cf2e5  call    ReleaseSubIrp
0x1400cf2ea  mov     rdx, r15
0x1400cf2ed  mov     rcx, rbx
0x1400cf2f0  call    ReleaseSubWorkItem
0x1400cf2f5  mov     r14, [rsp+98h+var_58]
0x1400cf2fa  jmp     short loc_1400CF307
0x1400cf2fc  mov     rdx, r15
0x1400cf2ff  mov     rcx, rbx
0x1400cf302  call    ReleaseSubWorkItem
0x1400cf307  xor     r15d, r15d
0x1400cf30a  movzx   eax, byte ptr [rdi+5Ch]
0x1400cf30e  test    al, al
0x1400cf310  jnz     short loc_1400CF331
0x1400cf312  mov     rdx, rdi
0x1400cf315  mov     rcx, rbx
0x1400cf318  call    ReleaseControl
  ... truncated ...
```
