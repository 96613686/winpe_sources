# MRxDAVSetFileInformation

- ea: `0x140022a80`
- end: `0x14002338c`
- name: `MRxDAVSetFileInformation`
- size: `2316`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, installer_update`

## callees

- `0x140001680`
- `0x140001c30`
- `0x140002138`
- `0x1400024b0`
- `0x140002ac4`
- `0x140003378`
- `0x140003a84`
- `0x140005a4c`
- `0x140006900`
- `0x14001c740`
- `0x14002000c`
- `0x140022a80`
- `0x1400252f8`
- `0x140025808`
- `0x140025b9c`
- `0x140025d00`
- `0x1400269d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140022afa`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022b7c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022c49`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022cf5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022d45`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022d96`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022dfb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022e5b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022eff`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023034`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400231b6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023230`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400232b7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022afa`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022b7c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022c49`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022cf5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022d45`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022d96`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022dfb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022e5b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022eff`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023034`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400231b6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023230`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400232b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022fe0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022fe0`

## string_xrefs

- `0x140022eb4`: `MRxDAVSetFileInformation`
- `0x140023260`: `MRxDAVSetFileInformation`

## pseudocode

```c
__int64 __fastcall MRxDAVSetFileInformation(__int64 a1)
{
  _QWORD *v1; // rdx
  __int64 v2; // r15
  __int64 v3; // r13
  __int64 v4; // rdi
  int v5; // esi
  __int64 v6; // r12
  __int64 v7; // r14
  _UNKNOWN **v8; // r8
  __int64 v9; // r9
  __int64 v10; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v12; // rbx
  HANDLE v13; // rax
  unsigned int v14; // esi
  __int64 v15; // rbx
  HANDLE v16; // rax
  __int64 v17; // rbx
  HANDLE v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rdi
  unsigned int v21; // eax
  __int64 v22; // rbx
  __int64 v23; // rdi
  unsigned int v24; // eax
  __int64 v25; // rbx
  unsigned int v26; // eax
  __int64 v27; // rdi
  __int64 v28; // rbx
  unsigned int v29; // eax
  int v30; // edx
  int v31; // r8d
  __int64 v32; // rbx
  HANDLE v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rbx
  int v37; // esi
  __int64 v38; // rbx
  HANDLE v39; // rax
  _QWORD *v40; // rsi
  _DWORD *v41; // rbx
  int v42; // esi
  __int64 v43; // rbx
  HANDLE v44; // rax
  int v45; // ebx
  int v46; // edi
  int v47; // esi
  int v48; // r14d
  __int64 v49; // r15
  HANDLE v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // rbx
  HANDLE v54; // rax
  __int128 v56; // [rsp+40h] [rbp-38h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-28h] BYREF
  __int128 v58; // [rsp+60h] [rbp-18h] BYREF
  _QWORD *v60; // [rsp+C8h] [rbp+50h]
  char v61; // [rsp+C8h] [rbp+50h]
  int v62; // [rsp+D0h] [rbp+58h]
  __int64 v63; // [rsp+D8h] [rbp+60h]

  v1 = *(_QWORD **)(a1 + 72);
  v2 = a1;
  v60 = v1;
  v3 = v1[4];
  if ( v3 )
    v3 = *(_QWORD *)(v3 + 136);
  v4 = *(_QWORD *)(a1 + 56);
  v5 = *(_DWORD *)(a1 + 448);
  v6 = *(_QWORD *)(a1 + 456);
  v56 = 0;
  v63 = v4;
  v7 = *(_QWORD *)(v1[5] + 40LL);
  v8 = &WPP_GLOBAL_Control;
  v9 = 0x4000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_qD(v10, 34, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, CurrentThreadId, v5);
    v1 = v60;
    v8 = &WPP_GLOBAL_Control;
    v9 = 0x4000;
  }
  switch ( v5 )
  {
    case 4:
      if ( !*(_DWORD *)(v7 + 96) )
        return (unsigned int)-1073741790;
      v37 = *(_DWORD *)(v6 + 32);
      if ( v37 && DisableEFS && !*(_DWORD *)(v3 + 2228) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v38 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v39 = PsGetCurrentThreadId();
          WPP_SF_qD(v38, 41, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v39, v37);
        }
        *(_DWORD *)(v6 + 32) &= ~0x4000u;
      }
      if ( *(_QWORD *)(v6 + 16) == -1 )
        *(_QWORD *)(v6 + 16) = 0;
      v40 = (_QWORD *)(v6 + 8);
      if ( *(_QWORD *)(v6 + 8) == -1 )
        *v40 = 0;
      if ( *(_QWORD *)v6 == -1 )
        *(_QWORD *)v6 = 0;
      v41 = (_DWORD *)(v6 + 24);
      if ( *(_QWORD *)(v6 + 24) )
      {
        if ( !(unsigned int)DavIsValidDate(v6 + 24, v1, v8, v9) )
          return (unsigned int)-1073741811;
        if ( *(_DWORD *)(v4 + 224) != *v41 || *(_DWORD *)(v4 + 228) != *(_DWORD *)(v6 + 28) )
        {
          *(_DWORD *)(v4 + 224) = *v41;
          *(_DWORD *)(v4 + 228) = *(_DWORD *)(v6 + 28);
        }
      }
      if ( *(_QWORD *)v6 )
      {
        if ( !(unsigned int)DavIsValidDate(v6, v1, v8, v9) )
          return (unsigned int)-1073741811;
        if ( *(_DWORD *)(v4 + 200) != *(_DWORD *)v6 || *(_DWORD *)(v4 + 204) != *(_DWORD *)(v6 + 4) )
          *(_BYTE *)(v3 + 60) = 1;
      }
      if ( *v40 )
      {
        if ( !(unsigned int)DavIsValidDate(v6 + 8, v1, v8, v9) )
          return (unsigned int)-1073741811;
        if ( *(_DWORD *)(v4 + 208) != *(_DWORD *)v40 || *(_DWORD *)(v4 + 212) != *(_DWORD *)(v6 + 12) )
          *(_BYTE *)(v3 + 61) = 1;
      }
      if ( *(_QWORD *)(v6 + 16) )
      {
        if ( !(unsigned int)DavIsValidDate(v6 + 16, v1, v8, v9) )
          return (unsigned int)-1073741811;
        if ( *(_DWORD *)(v4 + 216) != *(_DWORD *)(v6 + 16) || *(_DWORD *)(v4 + 220) != *(_DWORD *)(v6 + 20) )
        {
          *(_BYTE *)(v3 + 62) = 1;
          *(_DWORD *)(v3 + 28) = 1;
        }
      }
      v42 = *(_DWORD *)(v6 + 32);
      v61 = 0;
      if ( v42 )
      {
        v62 = *(_DWORD *)(v4 + 232);
        if ( v62 != v42 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
          {
            v43 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v44 = PsGetCurrentThreadId();
            WPP_SF_qLd(v43, 42, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v44, v62, v42);
          }
          if ( (*(_DWORD *)(v4 + 232) & 0x10) != 0 )
            *(_DWORD *)(v6 + 32) |= 0x10u;
          *(_BYTE *)(v3 + 63) = 1;
          v61 = 1;
        }
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v45 = *(unsigned __int8 *)(v3 + 63);
        v46 = *(unsigned __int8 *)(v3 + 62);
        v47 = *(unsigned __int8 *)(v3 + 61);
        v48 = *(unsigned __int8 *)(v3 + 60);
        v49 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v50 = PsGetCurrentThreadId();
        WPP_SF_qdddd(v49, v51, v52, v50, v48, v47, v46, v45, v56, *((_QWORD *)&v56 + 1));
        v4 = v63;
        v2 = a1;
      }
      v14 = UMRxAsyncEngOuterWrapper(
              v2,
              (_DWORD)v1,
              (_DWORD)v8,
              12,
              (__int64)MRxDAVSetFileInformationContinuation,
              (__int64)"MRxDAVSetFileInformation");
      if ( v14 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v53 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v54 = PsGetCurrentThreadId();
          WPP_SF_qD(v53, 44, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v54, v14);
        }
      }
      else
      {
        if ( *(_BYTE *)(v3 + 60) )
        {
          *(_DWORD *)(v4 + 200) = *(_DWORD *)v6;
          *(_DWORD *)(v4 + 204) = *(_DWORD *)(v6 + 4);
        }
        if ( *(_BYTE *)(v3 + 61) )
        {
          *(_DWORD *)(v4 + 208) = *(_DWORD *)(v6 + 8);
          *(_DWORD *)(v4 + 212) = *(_DWORD *)(v6 + 12);
        }
        if ( *(_BYTE *)(v3 + 62) )
        {
          *(_DWORD *)(v4 + 216) = *(_DWORD *)(v6 + 16);
          *(_DWORD *)(v4 + 220) = *(_DWORD *)(v6 + 20);
        }
        if ( v61 )
          *(_DWORD *)(v4 + 232) = *(_DWORD *)(v6 + 32) ^ (*(_DWORD *)(v4 + 232) ^ *(_DWORD *)(v6 + 32)) & 0x4000;
        MRxDAVUpdateBasicFileInfoCache(v2, *(unsigned int *)(v4 + 232), v4 + 216);
      }
      *(_WORD *)(v3 + 61) = 0;
      *(_BYTE *)(v3 + 63) = 0;
      *(_BYTE *)(v3 + 60) = 0;
      break;
    case 10:
      WORD1(v56) = *(_WORD *)(v6 + 16);
      LOWORD(v56) = WORD1(v56);
      *((_QWORD *)&v56 + 1) = v6 + 20;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v25 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v26 = (unsigned int)PsGetCurrentThreadId();
        WPP_SF_qZ(v25, 37, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v26, (__int64)&v56);
      }
      if ( *(_DWORD *)(v6 + 16) <= 0x208u )
      {
        memmove((void *)(v3 + 144), (const void *)(v6 + 20), *(unsigned int *)(v6 + 16));
        *(_DWORD *)(v3 + 664) = *(_DWORD *)(v6 + 16);
        v14 = UMRxAsyncEngOuterWrapper(
                v2,
                v30,
                v31,
                8,
                (__int64)MRxDAVReNameContinuation,
                (__int64)"MRxDAVSetFileInformation");
        if ( v14 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v32 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v33 = PsGetCurrentThreadId();
            WPP_SF_qD(v32, 39, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v33, v14);
          }
        }
        else
        {
          *(_DWORD *)(v3 + 64) = 1;
          v34 = *(_QWORD *)(v2 + 56);
          if ( *(_BYTE *)(v2 + 32) )
            v35 = *(_QWORD *)(v34 + 120);
          else
            v35 = *(_QWORD *)(v2 + 648);
          MRxDAVCacheFileNotFoundWithName(v34 + 360, v35);
          MRxDAVInvalidateFileNotFoundCacheForRename(v2);
          MRxDAVInvalidateFileInfoCache(v2);
          if ( (*(_DWORD *)(v4 + 232) & 0x4010) == 0x4010 )
          {
            v36 = *(_QWORD *)(v2 + 456);
            *(_OWORD *)P = 0;
            v58 = 0;
            MRxDAVRemoveEncryptedDirectoryKey((PUNICODE_STRING)(v3 + 40));
            *((_QWORD *)&v58 + 1) = v36 + 20;
            LOWORD(v58) = *(_WORD *)(v36 + 16);
            v14 = MRxDAVGetFullDirectoryPath(v2, (const void **)&v58, (__int64)P);
            if ( !v14 )
            {
              if ( P[1] )
              {
                v14 = MRxDAVCreateEncryptedDirectoryKey((PUNICODE_STRING)P);
                ExFreePoolWithTag(P[1], 0);
              }
            }
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v27 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v28 = v60[10];
          v29 = (unsigned int)PsGetCurrentThreadId();
          WPP_SF_qZ(v27, 38, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v29, v28);
        }
        return (unsigned int)-1073741562;
      }
      break;
    case 13:
      if ( *(_BYTE *)v6 && (*(_DWORD *)(v4 + 232) & 1) != 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v19 = v1[10];
          v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v21 = (unsigned int)PsGetCurrentThreadId();
          WPP_SF_qZ(v20, 35, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v21, v19);
        }
        return (unsigned int)-1073741535;
      }
      else
      {
        v14 = 0;
        if ( *(_BYTE *)v6
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v22 = v1[10];
          v23 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v24 = (unsigned int)PsGetCurrentThreadId();
          WPP_SF_qZ(v23, 36, (unsigned int)WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v24, v22);
        }
        *(_DWORD *)(v3 + 12) = *(_BYTE *)v6 == 1;
      }
      break;
    case 19:
      if ( *(_DWORD *)v3 )
        return (unsigned int)-1073741811;
      v14 = DavXxxInformation(6, *(_QWORD *)(v1[6] + 24LL), 19, *(unsigned int *)(v2 + 472), *(_QWORD *)(v2 + 456));
      if ( v14 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v18 = PsGetCurrentThreadId();
          WPP_SF_qD(v17, 45, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v18, 19);
        }
      }
      else if ( !*(_DWORD *)(v3 + 16) )
      {
        _InterlockedExchange((volatile __int32 *)(v3 + 16), 1);
        *(_DWORD *)(v3 + 28) = 0;
      }
      break;
    case 20:
      if ( *(_DWORD *)v3 )
        return (unsigned int)-1073741811;
      v14 = DavXxxInformation(6, *(_QWORD *)(v1[6] + 24LL), 20, *(unsigned int *)(v2 + 472), *(_QWORD *)(v2 + 456));
      if ( v14 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v16 = PsGetCurrentThreadId();
          WPP_SF_qD(v15, 40, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v16, 20);
        }
      }
      else
      {
        *(_QWORD *)(v4 + 32) = **(_QWORD **)(v2 + 456);
        if ( !*(_DWORD *)(v3 + 16) )
        {
          _InterlockedExchange((volatile __int32 *)(v3 + 16), 1);
          *(_DWORD *)(v3 + 28) = 0;
        }
        MRxDAVUpdateFileInfoCacheFileSize(v2, v4 + 32);
      }
      break;
    default:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v13 = PsGetCurrentThreadId();
        WPP_SF_qD(v12, 46, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v13, v5);
      }
      return (unsigned int)-1073741822;
  }
  return v14;
}

```

## disassembly

```asm
0x140022a80  mov     [rsp-40h+arg_0], rcx
0x140022a85  push    rbp
0x140022a86  push    rbx
0x140022a87  push    rsi
0x140022a88  push    rdi
0x140022a89  push    r12
0x140022a8b  push    r13
0x140022a8d  push    r14
0x140022a8f  push    r15
0x140022a91  mov     rbp, rsp
0x140022a94  sub     rsp, 78h
0x140022a98  mov     rdx, [rcx+48h]
0x140022a9c  mov     r15, rcx
0x140022a9f  mov     [rbp+arg_8], rdx
0x140022aa3  mov     r13, [rdx+20h]
0x140022aa7  test    r13, r13
0x140022aaa  jz      short loc_140022AB3
0x140022aac  mov     r13, [r13+88h]
0x140022ab3  mov     rdi, [rcx+38h]
0x140022ab7  xorps   xmm0, xmm0
0x140022aba  mov     esi, [rcx+1C0h]
0x140022ac0  mov     r12, [rcx+1C8h]
0x140022ac7  movups  [rbp+var_38], xmm0
0x140022acb  mov     rax, [rdx+28h]
0x140022acf  mov     [rbp+arg_18], rdi
0x140022ad3  mov     r14, [rax+28h]
0x140022ad7  mov     rbx, cs:WPP_GLOBAL_Control
0x140022ade  lea     r8, WPP_GLOBAL_Control
0x140022ae5  mov     r9d, 4000h
0x140022aeb  cmp     rbx, r8
0x140022aee  jz      short loc_140022B32
0x140022af0  test    [rbx+2Ch], r9d
0x140022af4  jz      short loc_140022B32
0x140022af6  mov     rbx, [rbx+18h]
0x140022afa  call    cs:__imp_PsGetCurrentThreadId
0x140022b01  nop     dword ptr [rax+rax+00h]
0x140022b06  mov     edx, 22h ; '"'
0x140022b0b  mov     dword ptr [rsp+78h+var_58], esi
0x140022b0f  mov     r9, rax
0x140022b12  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140022b19  mov     rcx, rbx
0x140022b1c  call    WPP_SF_qD
0x140022b21  mov     rdx, [rbp+arg_8]
0x140022b25  lea     r8, WPP_GLOBAL_Control
0x140022b2c  mov     r9d, 4000h
0x140022b32  mov     ecx, esi
0x140022b34  sub     ecx, 4
0x140022b37  jz      loc_140022FF1
0x140022b3d  mov     r10d, 6
0x140022b43  sub     ecx, r10d
0x140022b46  jz      loc_140022DCE
0x140022b4c  sub     ecx, 3
0x140022b4f  jz      loc_140022D0F
0x140022b55  sub     ecx, r10d
0x140022b58  jz      loc_140022C76
0x140022b5e  cmp     ecx, 1
0x140022b61  jz      short loc_140022BAD
0x140022b63  mov     rbx, cs:WPP_GLOBAL_Control
0x140022b6a  cmp     rbx, r8
0x140022b6d  jz      short loc_140022BA3
0x140022b6f  test    dword ptr [rbx+2Ch], 2000h
0x140022b76  jz      short loc_140022BA3
0x140022b78  mov     rbx, [rbx+18h]
0x140022b7c  call    cs:__imp_PsGetCurrentThreadId
0x140022b83  nop     dword ptr [rax+rax+00h]
0x140022b88  mov     edx, 2Eh ; '.'
0x140022b8d  mov     dword ptr [rsp+78h+var_58], esi
0x140022b91  mov     r9, rax
0x140022b94  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140022b9b  mov     rcx, rbx
0x140022b9e  call    WPP_SF_qD
0x140022ba3  mov     esi, 0C0000002h
0x140022ba8  jmp     loc_140023378
0x140022bad  cmp     dword ptr [r13+0], 0
0x140022bb2  jz      short loc_140022BBE
0x140022bb4  mov     esi, 0C000000Dh
0x140022bb9  jmp     loc_140023378
0x140022bbe  mov     rdx, [rdx+30h]
0x140022bc2  mov     r14d, 14h
0x140022bc8  mov     rax, [r15+1C8h]
0x140022bcf  mov     r8d, r14d
0x140022bd2  mov     r9d, [r15+1D8h]
0x140022bd9  mov     ecx, r10d
0x140022bdc  mov     [rsp+78h+var_58], rax
0x140022be1  mov     rdx, [rdx+18h]
0x140022be5  call    DavXxxInformation
0x140022bea  mov     esi, eax
0x140022bec  test    eax, eax
0x140022bee  jnz     short loc_140022C21
0x140022bf0  mov     rcx, [r15+1C8h]
0x140022bf7  mov     rdx, [rcx]
0x140022bfa  mov     [rdi+20h], rdx
0x140022bfe  cmp     [r13+10h], eax
0x140022c02  jnz     short loc_140022C10
0x140022c04  lea     r14d, [rax+1]
0x140022c08  xchg    r14d, [r13+10h]
0x140022c0c  mov     [r13+1Ch], eax
0x140022c10  lea     rdx, [rdi+20h]
0x140022c14  mov     rcx, r15
0x140022c17  call    MRxDAVUpdateFileInfoCacheFileSize
0x140022c1c  jmp     loc_140023378
0x140022c21  mov     rbx, cs:WPP_GLOBAL_Control
0x140022c28  lea     rax, WPP_GLOBAL_Control
0x140022c2f  cmp     rbx, rax
0x140022c32  jz      loc_140023378
0x140022c38  test    dword ptr [rbx+2Ch], 2000h
0x140022c3f  jz      loc_140023378
0x140022c45  mov     rbx, [rbx+18h]
0x140022c49  call    cs:__imp_PsGetCurrentThreadId
0x140022c50  nop     dword ptr [rax+rax+00h]
0x140022c55  mov     edx, 28h ; '('
0x140022c5a  mov     dword ptr [rsp+78h+var_58], r14d
0x140022c5f  mov     r9, rax
0x140022c62  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140022c69  mov     rcx, rbx
0x140022c6c  call    WPP_SF_qD
0x140022c71  jmp     loc_140023378
0x140022c76  cmp     dword ptr [r13+0], 0
0x140022c7b  jnz     loc_140022BB4
0x140022c81  mov     rdx, [rdx+30h]
0x140022c85  mov     edi, 13h
0x140022c8a  mov     rax, [r15+1C8h]
0x140022c91  mov     r8d, edi
0x140022c94  mov     r9d, [r15+1D8h]
0x140022c9b  mov     ecx, r10d
0x140022c9e  mov     [rsp+78h+var_58], rax
0x140022ca3  mov     rdx, [rdx+18h]
0x140022ca7  call    DavXxxInformation
0x140022cac  mov     esi, eax
0x140022cae  test    eax, eax
0x140022cb0  jnz     short loc_140022CCD
0x140022cb2  cmp     [r13+10h], eax
0x140022cb6  jnz     loc_140023378
0x140022cbc  lea     r14d, [rdi-12h]
0x140022cc0  xchg    r14d, [r13+10h]
0x140022cc4  mov     [r13+1Ch], eax
0x140022cc8  jmp     loc_140023378
0x140022ccd  mov     rbx, cs:WPP_GLOBAL_Control
0x140022cd4  lea     rax, WPP_GLOBAL_Control
0x140022cdb  cmp     rbx, rax
0x140022cde  jz      loc_140023378
0x140022ce4  test    dword ptr [rbx+2Ch], 2000h
0x140022ceb  jz      loc_140023378
0x140022cf1  mov     rbx, [rbx+18h]
0x140022cf5  call    cs:__imp_PsGetCurrentThreadId
0x140022cfc  nop     dword ptr [rax+rax+00h]
0x140022d01  mov     edx, 2Dh ; '-'
0x140022d06  mov     dword ptr [rsp+78h+var_58], edi
0x140022d0a  jmp     loc_140022C5F
0x140022d0f  mov     cl, [r12]
0x140022d13  mov     r14d, 1
0x140022d19  test    cl, cl
0x140022d1b  jz      short loc_140022D76
0x140022d1d  mov     eax, [rdi+0E8h]
0x140022d23  test    r14b, al
0x140022d26  jz      short loc_140022D76
0x140022d28  mov     rdi, cs:WPP_GLOBAL_Control
0x140022d2f  cmp     rdi, r8
0x140022d32  jz      short loc_140022D6C
0x140022d34  test    dword ptr [rdi+2Ch], 2000h
0x140022d3b  jz      short loc_140022D6C
0x140022d3d  mov     rbx, [rdx+50h]
0x140022d41  mov     rdi, [rdi+18h]
0x140022d45  call    cs:__imp_PsGetCurrentThreadId
0x140022d4c  nop     dword ptr [rax+rax+00h]
0x140022d51  lea     edx, [r14+22h]
0x140022d55  mov     [rsp+78h+var_58], rbx
0x140022d5a  mov     r9, rax
0x140022d5d  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140022d64  mov     rcx, rdi
0x140022d67  call    WPP_SF_qZ
0x140022d6c  mov     esi, 0C0000121h
0x140022d71  jmp     loc_140023378
0x140022d76  xor     esi, esi
0x140022d78  test    cl, cl
0x140022d7a  jz      short loc_140022DBC
0x140022d7c  mov     rdi, cs:WPP_GLOBAL_Control
0x140022d83  cmp     rdi, r8
0x140022d86  jz      short loc_140022DBC
0x140022d88  test    [rdi+2Ch], r9d
0x140022d8c  jz      short loc_140022DBC
0x140022d8e  mov     rbx, [rdx+50h]
0x140022d92  mov     rdi, [rdi+18h]
0x140022d96  call    cs:__imp_PsGetCurrentThreadId
0x140022d9d  nop     dword ptr [rax+rax+00h]
0x140022da2  lea     edx, [rsi+24h]
0x140022da5  mov     [rsp+78h+var_58], rbx
0x140022daa  mov     r9, rax
0x140022dad  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140022db4  mov     rcx, rdi
0x140022db7  call    WPP_SF_qZ
0x140022dbc  xor     eax, eax
0x140022dbe  cmp     [r12], r14b
0x140022dc2  setz    al
0x140022dc5  mov     [r13+0Ch], eax
0x140022dc9  jmp     loc_140023378
0x140022dce  movzx   eax, word ptr [r12+10h]
0x140022dd4  lea     rsi, [r12+14h]
0x140022dd9  mov     word ptr [rbp+var_38+2], ax
0x140022ddd  mov     word ptr [rbp+var_38], ax
0x140022de1  mov     qword ptr [rbp+var_38+8], rsi
0x140022de5  mov     rbx, cs:WPP_GLOBAL_Control
0x140022dec  cmp     rbx, r8
0x140022def  jz      short loc_140022E2E
0x140022df1  test    [rbx+2Ch], r9d
0x140022df5  jz      short loc_140022E2E
0x140022df7  mov     rbx, [rbx+18h]
0x140022dfb  call    cs:__imp_PsGetCurrentThreadId
0x140022e02  nop     dword ptr [rax+rax+00h]
0x140022e07  mov     edx, 25h ; '%'
0x140022e0c  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140022e13  mov     r9, rax
0x140022e16  mov     rcx, rbx
0x140022e19  lea     rax, [rbp+var_38]
0x140022e1d  mov     [rsp+78h+var_58], rax
0x140022e22  call    WPP_SF_qZ
0x140022e27  lea     r8, WPP_GLOBAL_Control
0x140022e2e  mov     eax, [r12+10h]
0x140022e33  cmp     eax, 208h
0x140022e38  jbe     short loc_140022E8D
0x140022e3a  mov     rdi, cs:WPP_GLOBAL_Control
0x140022e41  cmp     rdi, r8
0x140022e44  jz      short loc_140022E83
0x140022e46  test    dword ptr [rdi+2Ch], 2000h
0x140022e4d  jz      short loc_140022E83
0x140022e4f  mov     rbx, [rbp+arg_8]
0x140022e53  mov     rdi, [rdi+18h]
0x140022e57  mov     rbx, [rbx+50h]
0x140022e5b  call    cs:__imp_PsGetCurrentThreadId
0x140022e62  nop     dword ptr [rax+rax+00h]
0x140022e67  mov     edx, 26h ; '&'
0x140022e6c  mov     [rsp+78h+var_58], rbx
0x140022e71  mov     r9, rax
0x140022e74  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140022e7b  mov     rcx, rdi
0x140022e7e  call    WPP_SF_qZ
0x140022e83  mov     esi, 0C0000106h
0x140022e88  jmp     loc_140023378
0x140022e8d  mov     r8, rax; Size
0x140022e90  lea     rcx, [r13+90h]; void *
0x140022e97  mov     rdx, rsi; Src
0x140022e9a  call    memmove
0x140022e9f  mov     eax, [r12+10h]
0x140022ea4  mov     r9d, 8
0x140022eaa  mov     [r13+298h], eax
0x140022eb1  mov     rcx, r15
0x140022eb4  lea     rax, aMrxdavsetfilei; "MRxDAVSetFileInformation"
0x140022ebb  mov     [rsp+78h+var_50], rax
0x140022ec0  lea     rax, MRxDAVReNameContinuation
0x140022ec7  mov     [rsp+78h+var_58], rax
0x140022ecc  call    UMRxAsyncEngOuterWrapper
0x140022ed1  mov     esi, eax
0x140022ed3  test    eax, eax
0x140022ed5  jz      short loc_140022F2B
0x140022ed7  mov     rbx, cs:WPP_GLOBAL_Control
0x140022ede  lea     rax, WPP_GLOBAL_Control
0x140022ee5  cmp     rbx, rax
0x140022ee8  jz      loc_140023378
0x140022eee  test    dword ptr [rbx+2Ch], 2000h
0x140022ef5  jz      loc_140023378
0x140022efb  mov     rbx, [rbx+18h]
0x140022eff  call    cs:__imp_PsGetCurrentThreadId
0x140022f06  nop     dword ptr [rax+rax+00h]
0x140022f0b  mov     edx, 27h ; '''
0x140022f10  mov     dword ptr [rsp+78h+var_58], esi
0x140022f14  mov     r9, rax
0x140022f17  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140022f1e  mov     rcx, rbx
0x140022f21  call    WPP_SF_qD
0x140022f26  jmp     loc_140023378
0x140022f2b  mov     dword ptr [r13+40h], 1
0x140022f33  cmp     byte ptr [r15+20h], 0
0x140022f38  mov     rcx, [r15+38h]
0x140022f3c  jnz     short loc_140022F47
0x140022f3e  mov     rdx, [r15+288h]
0x140022f45  jmp     short loc_140022F4B
0x140022f47  mov     rdx, [rcx+78h]
0x140022f4b  add     rcx, 168h
0x140022f52  call    MRxDAVCacheFileNotFoundWithName
0x140022f57  mov     rcx, r15
0x140022f5a  call    MRxDAVInvalidateFileNotFoundCacheForRename
0x140022f5f  mov     rcx, r15
0x140022f62  call    MRxDAVInvalidateFileInfoCache
0x140022f67  mov     eax, [rdi+0E8h]
0x140022f6d  mov     ecx, 4010h
0x140022f72  and     eax, ecx
0x140022f74  cmp     eax, ecx
0x140022f76  jnz     loc_140023378
0x140022f7c  mov     rbx, [r15+1C8h]
0x140022f83  lea     rcx, [r13+28h]; ValueName
0x140022f87  xorps   xmm0, xmm0
0x140022f8a  xorps   xmm1, xmm1
0x140022f8d  movups  xmmword ptr [rbp+P], xmm0
0x140022f91  movups  [rbp+var_18], xmm1
0x140022f95  call    MRxDAVRemoveEncryptedDirectoryKey
0x140022f9a  lea     rax, [rbx+14h]
0x140022f9e  mov     rcx, r15
0x140022fa1  mov     qword ptr [rbp+var_18+8], rax
0x140022fa5  lea     r8, [rbp+P]
0x140022fa9  movzx   eax, word ptr [rbx+10h]
  ... truncated ...
```
