# UxpSslCommonSendData

- ea: `0x14004d740`
- end: `0x14004e0f5`
- name: `UxpSslCommonSendData`
- size: `2485`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1400a405c`

## callees

- `0x14000a350`
- `0x14004ba70`
- `0x14004bd90`
- `0x14004d130`
- `0x14004d2d0`
- `0x14004d740`
- `0x14004ebe0`
- `0x14013aed0`
- `0x14013b124`
- `0x140155b78`
- `0x1401678f0`
- `0x140167940`
- `0x1401c3f58`
- `0x1401d58d4`
- `0x1401d5988`
- `0x1401d5a48`
- `0x1401d5b20`
- `0x1401d9e44`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14004dc94`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14004dc94`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004db04`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004db04`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d816`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d816`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004d80a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004d80a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004d7bd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004d7bd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004d7a8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004d7a8`

## pseudocode

```c
__int64 __fastcall UxpSslCommonSendData(
        __int64 a1,
        int a2,
        __int64 a3,
        struct _MDL *a4,
        int a5,
        unsigned __int64 a6,
        __int64 (__fastcall *a7)(PVOID P),
        _QWORD *a8,
        __int64 a9)
{
  unsigned int v10; // ebx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  unsigned int v15; // edi
  unsigned __int64 v17; // rdi
  _QWORD *v18; // r13
  _QWORD *v19; // r12
  unsigned __int64 v20; // r15
  unsigned int v21; // r9d
  char *SendBuffer; // rax
  unsigned int v23; // ecx
  unsigned int v24; // r10d
  int v25; // r14d
  __int64 v26; // rdi
  unsigned int v27; // r9d
  unsigned int v28; // r12d
  __int64 v29; // rcx
  PMDL v30; // r10
  char *v31; // r9
  int v32; // r8d
  ULONG v33; // r14d
  char *MappedSystemVa; // rax
  ULONG v35; // r12d
  int v36; // eax
  _QWORD *v37; // r14
  __int64 v38; // r15
  int v39; // ecx
  _QWORD *v40; // rdi
  __int64 v41; // r8
  _QWORD *v42; // r12
  __int64 v43; // r9
  char v44; // di
  char v45; // bl
  __int64 v46; // rax
  __int64 v47; // rcx
  _QWORD *v48; // rdx
  _QWORD *v49; // rax
  __int64 SendRequestTracker; // rax
  __int64 v51; // [rsp+38h] [rbp-B1h]
  __int64 v52; // [rsp+48h] [rbp-A1h]
  char v53; // [rsp+60h] [rbp-89h]
  unsigned int v54; // [rsp+64h] [rbp-85h]
  int v55; // [rsp+68h] [rbp-81h]
  unsigned int v56; // [rsp+6Ch] [rbp-7Dh]
  unsigned int v57; // [rsp+70h] [rbp-79h]
  int v58; // [rsp+74h] [rbp-75h]
  int v59; // [rsp+78h] [rbp-71h] BYREF
  unsigned int v60; // [rsp+80h] [rbp-69h] BYREF
  unsigned int v61; // [rsp+84h] [rbp-65h]
  _QWORD *v62; // [rsp+88h] [rbp-61h] BYREF
  PMDL MemoryDescriptorList; // [rsp+90h] [rbp-59h] BYREF
  unsigned int Size; // [rsp+98h] [rbp-51h]
  unsigned int Size_4; // [rsp+9Ch] [rbp-4Dh]
  char *v66; // [rsp+A0h] [rbp-49h]
  PMDL Next; // [rsp+A8h] [rbp-41h]
  __int64 v68; // [rsp+B0h] [rbp-39h]
  _QWORD *v69; // [rsp+B8h] [rbp-31h] BYREF
  PVOID P; // [rsp+C0h] [rbp-29h]
  _QWORD *v71; // [rsp+C8h] [rbp-21h]
  __int128 v72; // [rsp+D0h] [rbp-19h] BYREF
  __int128 v73; // [rsp+E0h] [rbp-9h]
  char v74; // [rsp+138h] [rbp+4Fh]
  unsigned int v75; // [rsp+140h] [rbp+57h]

  v75 = a3;
  v74 = a2;
  v10 = (unsigned __int8)a2;
  v12 = (unsigned __int8)a2;
  v61 = (unsigned __int8)a2;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
  {
    WPP_SF_qlLqLPqqq((unsigned __int8)a2, 27, a3, a1, (unsigned __int8)a2, a3, a4, a5, a6, a7, a8, a9);
    a3 = v75;
    v12 = v10;
  }
  v53 = 0;
  if ( !(_BYTE)v10 )
  {
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qlLqLPqqq(v12, 49, a3, a1, v12, a3, a4, a5, a6, a7, a8, a9);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a1 + 208, 0);
    v13 = *(_DWORD *)(a1 + 220);
    if ( v13 == 4 || v13 != 5 && (*(_DWORD *)(a1 + 1296) & 2) != 0 )
    {
      if ( (*(_DWORD *)(a1 + 1184) & 2) != 0 || (v14 = *(_DWORD *)(a1 + 1296), (v14 & 3) != 0) )
      {
        SendRequestTracker = UxpSslAllocateSendRequestTracker(0, v75, (_DWORD)a4, a5, a6, (__int64)a7, (__int64)a8, a9);
        if ( SendRequestTracker )
        {
          v48 = *(_QWORD **)(a1 + 1312);
          if ( *v48 != a1 + 1304 )
            __fastfail(3u);
          v49 = (_QWORD *)(SendRequestTracker + 24);
          v15 = 259;
          *v49 = a1 + 1304;
          v49[1] = v48;
          *v48 = v49;
          *(_QWORD *)(a1 + 1312) = v49;
        }
        else
        {
          v15 = -1073741670;
        }
      }
      else
      {
        v15 = 0;
        *(_DWORD *)(a1 + 1296) = v14 | 1;
      }
    }
    else
    {
      v15 = -1073741436;
    }
    ExReleasePushLockExclusiveEx(a1 + 208, 0);
    KeLeaveCriticalRegion();
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_d(1041, 50, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, v15);
    if ( (v15 & 0x80000000) != 0 )
    {
      v15 = UlInvokeCompletionRoutine(v15, 0, a7, a8);
      goto LABEL_14;
    }
    if ( v15 == 259 )
      goto LABEL_14;
    a3 = v75;
    v12 = v61;
    v53 = 1;
  }
  v59 = a5;
  MemoryDescriptorList = a4;
  v69 = 0;
  v62 = 0;
  v17 = a6;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qlLqLPqqq(v12, 29, a3, a1, v12, a3, a4, a5, a6, a7, a8, a9);
  v71 = 0;
  v18 = 0;
  v19 = 0;
  v20 = (a6 >> 15) + ((a6 & 0x7FFF) != 0);
  if ( v20 )
  {
    do
    {
      v60 = 0;
      v21 = v17;
      if ( v17 > 0x8000 )
        v21 = 0x8000;
      v54 = v21;
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      {
        LODWORD(v51) = 0;
        WPP_SF_qqqLlq(v12, (_WORD)a2, a3, a1, (char)&MemoryDescriptorList, (char)&v59, v21, v51, &v62);
        v21 = v54;
      }
      a3 = *(unsigned int *)(a1 + 456);
      v19 = 0;
      v62 = 0;
      if ( (unsigned int)a3 >= 0x10000 || (v12 = *(unsigned int *)(a1 + 460), (unsigned int)v12 >= 0x10000) )
      {
        v25 = -1073741811;
        v54 = v21;
      }
      else
      {
        Size = *(_DWORD *)(a1 + 464);
        a2 = v21 % Size;
        v12 = v21 + (v21 / Size + (v21 % Size != 0)) * (a3 + v12);
        v55 = v21 / Size + (v21 % Size != 0);
        if ( (unsigned int)v12 == v12 )
        {
          SendBuffer = UxSslAllocateSendBuffer((unsigned int)v12);
          P = SendBuffer;
          if ( SendBuffer )
          {
            v24 = v54;
            v25 = 0;
            v26 = *((_QWORD *)SendBuffer + 8);
            v27 = *((_DWORD *)SendBuffer + 15);
            LODWORD(a3) = v55;
            while ( 1 )
            {
              v56 = v27;
              v68 = v26;
              v57 = v24;
              if ( !(_DWORD)a3 )
              {
                v19 = P;
                LODWORD(v12) = v54;
                *((_DWORD *)P + 14) = v26 - *((_DWORD *)P + 16);
                v17 = a6;
                v62 = v19;
                goto LABEL_31;
              }
              v28 = v24;
              if ( v24 > Size )
                v28 = Size;
              v61 = v28;
              if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
              {
                LODWORD(v52) = 0;
                WPP_SF_qqLqqLlq(v23, a2, a3, a1, v26, v27, (char)&MemoryDescriptorList, (char)&v59, v28, v52, &v60);
                LODWORD(a3) = v55;
                v27 = v56;
                v24 = v57;
              }
              v29 = *(unsigned int *)(a1 + 456);
              Size_4 = v29 + v28 + *(_DWORD *)(a1 + 460);
              if ( Size_4 > v27 )
              {
                v25 = -1073741789;
              }
              else
              {
                v30 = MemoryDescriptorList;
                v31 = (char *)(v26 + v29);
                v32 = v59;
                v33 = v28;
                Next = MemoryDescriptorList;
                v58 = v59;
                while ( 1 )
                {
                  v66 = v31;
                  if ( !v33 )
                  {
                    v26 = v68;
                    v59 = v32;
                    MemoryDescriptorList = v30;
                    v36 = UxpSslSealMessage(a1, v68, Size_4, 0, (__int64)&v60);
                    LODWORD(a3) = v55;
                    v25 = v36;
                    v27 = v56;
                    v24 = v57;
                    v28 = v61;
                    goto LABEL_57;
                  }
                  if ( (v30->MdlFlags & 5) != 0 )
                  {
                    MappedSystemVa = (char *)v30->MappedSystemVa;
                  }
                  else
                  {
                    MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v30, 0, MmCached, 0, 0, 0x40000000u);
                    v30 = Next;
                    v32 = v58;
                    v31 = v66;
                  }
                  if ( !MappedSystemVa )
                    break;
                  v35 = v30->ByteCount - v32;
                  if ( v35 <= v33 )
                  {
                    Next = v30->Next;
                    v58 = 0;
                  }
                  else
                  {
                    v35 = v33;
                    v58 = v33 + v32;
                  }
                  memmove(v31, &MappedSystemVa[v32], v35);
                  v30 = Next;
                  v31 = &v66[v35];
                  v32 = v58;
                  v33 -= v35;
                }
                LODWORD(a3) = v55;
                v25 = -1073741670;
                v26 = v68;
                v28 = v61;
                v27 = v56;
                v24 = v57;
              }
LABEL_57:
              if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
              {
                WPP_SF_Dd(1041, 36, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, v60, v25);
                LODWORD(a3) = v55;
                v27 = v56;
                v24 = v57;
              }
              if ( v25 < 0 )
                break;
              v23 = v60;
              if ( v60 > v27 )
              {
                v25 = -1073741675;
                break;
              }
              v26 += v60;
              v27 -= v60;
              v24 -= v28;
              LODWORD(a3) = a3 - 1;
              v55 = a3;
            }
            UxSslFreeSendBufferList(P);
            v19 = v62;
            v17 = a6;
          }
          else
          {
            LODWORD(v12) = v54;
            v25 = -1073741670;
            v19 = v62;
          }
        }
        else
        {
          v25 = -1073741675;
        }
      }
LABEL_31:
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      {
        WPP_SF_qD(1041, 34, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, v19, v25);
        v19 = v62;
      }
      if ( v25 < 0 )
        goto LABEL_62;
      if ( v18 )
      {
        LODWORD(v12) = (_DWORD)v71;
        v71[3] = v19;
        v19 = v62;
      }
      else
      {
        v18 = v19;
      }
      v17 -= v54;
      v71 = v19;
      a6 = v17;
    }
    while ( --v20 );
  }
  v44 = v74;
  if ( !v74 || !*(_BYTE *)(*(_QWORD *)(a1 + 1696) + 8162LL) )
  {
LABEL_63:
    v72 = 0;
    v73 = 0;
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qlLqqqq(1, (_WORD)a2, a3, a1, v74, v75, (char)v18, (char)a7, a8, a9);
    v37 = 0;
    v38 = 0;
    if ( v18 )
    {
      v18[4] = a1;
      v39 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 20));
      if ( UxDebugCheckRefcount && v39 <= -1 )
        UlBugCheckEx(3u, a1 + 20, 0x2Bu, v39);
      v40 = v18;
      v18[5] = a7;
      a7 = UxSslRestartSendRawData;
      v18[6] = a8;
      a8 = v18;
      do
      {
        v41 = v40[8];
        v42 = v40 + 9;
        v43 = *((unsigned int *)v40 + 14);
        v40[9] = 0;
        *((_WORD *)v40 + 41) = 0;
        *((_DWORD *)v40 + 28) = v43;
        v40[13] = v41 & 0xFFFFFFFFFFFFF000uLL;
        *((_WORD *)v40 + 40) = 8 * (((v43 + (unsigned __int64)(v41 & 0xFFF) + 4095) >> 12) + 6);
        *((_DWORD *)v40 + 29) = v41 & 0xFFF;
        MmBuildMdlForNonPagedPool((PMDL)(v40 + 9));
        v38 += *((unsigned int *)v40 + 14);
        if ( v37 )
          *v37 = v42;
        v40 = (_QWORD *)v40[3];
        v37 = v42;
      }
      while ( v40 );
      v44 = v74;
      v37 = v18 + 9;
    }
    LODWORD(v72) = 0;
    LODWORD(v73) = 0;
    v45 = byte_1401A3780;
    *((_QWORD *)&v72 + 1) = v37;
    *((_QWORD *)&v73 + 1) = v38;
    if ( SBYTE2(xmmword_1401A2CA0) < 0 )
      WPP_SF_d(1047, 10, WPP_b6616b8acc683c557a6f97eb9025b7cb_Traceguids, (unsigned __int8)byte_1401A3780);
    if ( v45 )
      UxPktMonTraceSslSend(a1);
    v46 = *(_QWORD *)(a1 + 56);
    v47 = *(_QWORD *)(a1 + 48);
    if ( v44 )
      (*(void (__fastcall **)(__int64, _QWORD, __int128 *, __int64 (__fastcall *)(PVOID), _QWORD *, __int64))(v46 + 88))(
        v47,
        v75,
        &v72,
        a7,
        a8,
        a9);
    else
      (*(void (__fastcall **)(__int64, _QWORD, __int128 *, __int64 (__fastcall *)(PVOID), _QWORD *, __int64))(v46 + 96))(
        v47,
        v75,
        &v72,
        a7,
        a8,
        a9);
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1041, 19, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids);
    v15 = 259;
    goto LABEL_81;
  }
  v25 = UxpSslGenerateCloseNotify(a1, &v69);
  if ( v25 >= 0 )
  {
    if ( v18 )
      v19[3] = v69;
    else
      v18 = v69;
    goto LABEL_63;
  }
LABEL_62:
  UxSslFreeSendBufferList(v18);
  v15 = UlInvokeCompletionRoutine((unsigned int)v25, 0, a7, a8);
LABEL_81:
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1041, 30, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, v15);
  if ( v53 )
    UxSslPostsendCheck(a1);
LABEL_14:
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1041, 28, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x14004d740  mov     [rsp-8+arg_10], r8d
0x14004d745  mov     [rsp-8+arg_8], dl
0x14004d749  push    rbp
0x14004d74a  push    rbx
0x14004d74b  push    rsi
0x14004d74c  push    rdi
0x14004d74d  push    r12
0x14004d74f  push    r13
0x14004d751  push    r15
0x14004d753  lea     rbp, [rsp-7]
0x14004d758  sub     rsp, 0F0h
0x14004d75f  mov     r15, r9
0x14004d762  movzx   ebx, dl
0x14004d765  mov     rsi, rcx
0x14004d768  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004d76f  mov     ecx, ebx
0x14004d771  mov     r12d, [rbp+37h+arg_20]
0x14004d775  mov     r13, [rbp+37h+arg_38]
0x14004d779  mov     rdi, [rbp+37h+arg_28]
0x14004d77d  mov     [rbp+37h+var_9C], ebx
0x14004d780  jnz     loc_14004DE22
0x14004d786  mov     [rsp+120h+arg_0], r14
0x14004d78e  mov     [rsp+120h+var_C0], 0
0x14004d793  test    bl, bl
0x14004d795  jnz     loc_14004D86D
0x14004d79b  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004d7a2  jnz     loc_14004DE6C
0x14004d7a8  call    cs:__imp_KeEnterCriticalRegion
0x14004d7af  nop     dword ptr [rax+rax+00h]
0x14004d7b4  xor     edx, edx
0x14004d7b6  lea     rcx, [rsi+0D0h]
0x14004d7bd  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14004d7c4  nop     dword ptr [rax+rax+00h]
0x14004d7c9  mov     eax, [rsi+0DCh]
0x14004d7cf  xor     ebx, ebx
0x14004d7d1  cmp     eax, 4
0x14004d7d4  jnz     loc_14004D9EC
0x14004d7da  mov     eax, [rsi+4A0h]
0x14004d7e0  test    al, 2
0x14004d7e2  jnz     loc_14004DEC3
0x14004d7e8  mov     eax, [rsi+510h]
0x14004d7ee  test    al, 3
0x14004d7f0  jnz     loc_14004DEC3
0x14004d7f6  or      eax, 1
0x14004d7f9  mov     edi, ebx
0x14004d7fb  mov     [rsi+510h], eax
0x14004d801  xor     edx, edx
0x14004d803  lea     rcx, [rsi+0D0h]
0x14004d80a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14004d811  nop     dword ptr [rax+rax+00h]
0x14004d816  call    cs:__imp_KeLeaveCriticalRegion
0x14004d81d  nop     dword ptr [rax+rax+00h]
0x14004d822  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004d829  jnz     loc_14004DA10
0x14004d82f  test    edi, edi
0x14004d831  js      loc_14004DF05
0x14004d837  cmp     edi, 103h
0x14004d83d  jnz     loc_14004D9FF
0x14004d843  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004d84a  jnz     loc_14004E0D7
0x14004d850  mov     r14, [rsp+120h+arg_0]
0x14004d858  mov     eax, edi
0x14004d85a  add     rsp, 0F0h
0x14004d861  pop     r15
0x14004d863  pop     r13
0x14004d865  pop     r12
0x14004d867  pop     rdi
0x14004d868  pop     rsi
0x14004d869  pop     rbx
0x14004d86a  pop     rbp
0x14004d86b  retn
0x14004d86d  xor     ebx, ebx
0x14004d86f  mov     [rbp+37h+var_A8], r12d
0x14004d873  mov     [rbp+37h+MemoryDescriptorList], r15
0x14004d877  mov     [rbp+37h+var_68], rbx
0x14004d87b  mov     [rbp+37h+var_98], rbx
0x14004d87f  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004d886  mov     rdi, [rbp+37h+arg_28]
0x14004d88a  jnz     loc_14004DF1C
0x14004d890  test    rdi, 7FFFh
0x14004d897  mov     [rbp+37h+var_58], rbx
0x14004d89b  mov     r15, rbx
0x14004d89e  mov     rax, rdi
0x14004d8a1  setnbe  r15b
0x14004d8a5  mov     r13, rbx
0x14004d8a8  shr     rax, 0Fh
0x14004d8ac  mov     r12, rbx
0x14004d8af  add     r15, rax
0x14004d8b2  jz      loc_14017680C
0x14004d8b8  mov     eax, 8000h
0x14004d8bd  nop     dword ptr [rax]
0x14004d8c0  cmp     rdi, rax
0x14004d8c3  mov     [rbp+37h+var_A0], ebx
0x14004d8c6  mov     r9d, edi
0x14004d8c9  cmova   r9d, eax
0x14004d8cd  mov     [rsp+120h+var_BC], r9d
0x14004d8d2  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004d8d9  jnz     loc_14004DF60
0x14004d8df  mov     r8d, [rsi+1C8h]
0x14004d8e6  mov     r12, rbx
0x14004d8e9  mov     [rbp+37h+var_98], rbx
0x14004d8ed  cmp     r8d, 10000h
0x14004d8f4  jnb     loc_14004DD77
0x14004d8fa  mov     ecx, [rsi+1CCh]
0x14004d900  cmp     ecx, 10000h
0x14004d906  jnb     loc_14004DD77
0x14004d90c  mov     r10d, [rsi+1D0h]
0x14004d913  xor     edx, edx
0x14004d915  mov     eax, r9d
0x14004d918  mov     dword ptr [rbp+37h+Size], r10d
0x14004d91c  div     r10d
0x14004d91f  mov     r10d, ebx
0x14004d922  test    edx, edx
0x14004d924  setnz   r10b
0x14004d928  add     rcx, r8
0x14004d92b  add     r10d, eax
0x14004d92e  mov     eax, r10d
0x14004d931  imul    rcx, rax
0x14004d935  mov     eax, r9d
0x14004d938  add     rcx, rax
0x14004d93b  mov     [rsp+120h+var_B8], r10d
0x14004d940  mov     eax, ecx
0x14004d942  cmp     rax, rcx
0x14004d945  jnz     loc_14004DD87
0x14004d94b  mov     ecx, eax; Length
0x14004d94d  call    UxSslAllocateSendBuffer
0x14004d952  mov     [rbp+37h+P], rax
0x14004d956  test    rax, rax
0x14004d959  jz      loc_14004DF96
0x14004d95f  mov     r10d, [rsp+120h+var_BC]
0x14004d964  mov     r14d, ebx
0x14004d967  mov     rdi, [rax+40h]
0x14004d96b  mov     r9d, [rax+3Ch]
0x14004d96f  mov     r8d, [rsp+120h+var_B8]
0x14004d974  mov     [rbp+37h+var_B4], r9d
0x14004d978  mov     [rbp+37h+var_70], rdi
0x14004d97c  mov     [rbp+37h+var_B0], r10d
0x14004d980  test    r8d, r8d
0x14004d983  jnz     loc_14004DA2E
0x14004d989  mov     r12, [rbp+37h+P]
0x14004d98d  mov     ecx, [rsp+120h+var_BC]
0x14004d991  mov     [rsp+120h+var_BC], ecx
0x14004d995  sub     edi, [r12+40h]
0x14004d99a  mov     [r12+38h], edi
0x14004d99f  mov     rdi, [rbp+37h+arg_28]
0x14004d9a3  mov     [rbp+37h+var_98], r12
0x14004d9a7  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004d9ae  jnz     loc_14004DB94
0x14004d9b4  test    r14d, r14d
0x14004d9b7  js      loc_14004DBBB
0x14004d9bd  mov     eax, [rsp+120h+var_BC]
0x14004d9c1  test    r13, r13
0x14004d9c4  jnz     loc_14004E075
0x14004d9ca  mov     r13, r12
0x14004d9cd  sub     rdi, rax
0x14004d9d0  mov     [rbp+37h+var_58], r12
0x14004d9d4  mov     [rbp+37h+arg_28], rdi
0x14004d9d8  mov     eax, 8000h
0x14004d9dd  sub     r15, 1
0x14004d9e1  jnz     loc_14004D8C0
0x14004d9e7  jmp     loc_14017680C
0x14004d9ec  cmp     eax, 5
0x14004d9ef  jnz     loc_14004DEB0
0x14004d9f5  mov     edi, 0C0000184h
0x14004d9fa  jmp     loc_14004D801
0x14004d9ff  mov     r8d, [rbp+37h+arg_10]
0x14004da03  mov     ecx, [rbp+37h+var_9C]
0x14004da06  mov     [rsp+120h+var_C0], 1
0x14004da0b  jmp     loc_14004D86F
0x14004da10  mov     edx, 32h ; '2'
0x14004da15  lea     r8, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids
0x14004da1c  mov     ecx, 411h
0x14004da21  mov     r9d, edi
0x14004da24  call    WPP_SF_d
0x14004da29  jmp     loc_14004D82F
0x14004da2e  cmp     r10d, dword ptr [rbp+37h+Size]
0x14004da32  mov     r12d, r10d
0x14004da35  cmova   r12d, dword ptr [rbp+37h+Size]
0x14004da3a  mov     [rbp+37h+var_9C], r12d
0x14004da3e  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004da45  jnz     loc_14004DFAD
0x14004da4b  mov     eax, [rsi+1CCh]
0x14004da51  mov     ecx, [rsi+1C8h]
0x14004da57  add     eax, r12d
0x14004da5a  add     eax, ecx
0x14004da5c  mov     dword ptr [rbp+37h+Size+4], eax
0x14004da5f  cmp     eax, r9d
0x14004da62  ja      loc_14004E015
0x14004da68  mov     r10, [rbp+37h+MemoryDescriptorList]
0x14004da6c  lea     r9, [rdi+rcx]
0x14004da70  mov     r8d, [rbp+37h+var_A8]
0x14004da74  mov     r14d, r12d
0x14004da77  mov     [rbp+37h+var_78], r10
0x14004da7b  mov     [rbp+37h+var_AC], r8d
0x14004da7f  mov     [rbp+37h+var_80], r9
0x14004da83  test    r14d, r14d
0x14004da86  jz      loc_14004DB21
0x14004da8c  test    byte ptr [r10+0Ah], 5
0x14004da91  jz      short loc_14004DAEA
0x14004da93  mov     rax, [r10+18h]
0x14004da97  test    rax, rax
0x14004da9a  jz      loc_14004DFF5
0x14004daa0  mov     r12d, [r10+28h]
0x14004daa4  mov     edx, r8d
0x14004daa7  sub     r12d, r8d
0x14004daaa  add     rdx, rax; Src
0x14004daad  cmp     r12d, r14d
0x14004dab0  jbe     short loc_14004DADE
0x14004dab2  add     r8d, r14d
0x14004dab5  mov     r12d, r14d
0x14004dab8  mov     [rbp+37h+var_AC], r8d
0x14004dabc  mov     r8d, r12d; Size
0x14004dabf  mov     rcx, r9; void *
0x14004dac2  mov     edi, r12d
0x14004dac5  call    memmove
0x14004daca  mov     r9, [rbp+37h+var_80]
0x14004dace  mov     r10, [rbp+37h+var_78]
0x14004dad2  add     r9, rdi
0x14004dad5  mov     r8d, [rbp+37h+var_AC]
0x14004dad9  sub     r14d, r12d
0x14004dadc  jmp     short loc_14004DA7F
0x14004dade  mov     r10, [r10]
0x14004dae1  mov     [rbp+37h+var_78], r10
0x14004dae5  mov     [rbp+37h+var_AC], ebx
0x14004dae8  jmp     short loc_14004DABC
0x14004daea  mov     [rsp+120h+Priority], 40000000h; Priority
0x14004daf2  xor     r9d, r9d; RequestedAddress
0x14004daf5  xor     edx, edx; AccessMode
0x14004daf7  mov     [rsp+120h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x14004dafb  mov     r8d, 1; CacheType
0x14004db01  mov     rcx, r10; MemoryDescriptorList
0x14004db04  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004db0b  nop     dword ptr [rax+rax+00h]
0x14004db10  mov     r10, [rbp+37h+var_78]
0x14004db14  mov     r8d, [rbp+37h+var_AC]
0x14004db18  mov     r9, [rbp+37h+var_80]
0x14004db1c  jmp     loc_14004DA97
0x14004db21  mov     rdi, [rbp+37h+var_70]
0x14004db25  lea     rax, [rbp+37h+var_A0]
0x14004db29  mov     [rbp+37h+var_A8], r8d
0x14004db2d  mov     rdx, rdi
0x14004db30  mov     r8d, dword ptr [rbp+37h+Size+4]
0x14004db34  xor     r9d, r9d
0x14004db37  mov     rcx, rsi
0x14004db3a  mov     [rbp+37h+MemoryDescriptorList], r10
0x14004db3e  mov     qword ptr [rsp+120h+BugCheckOnFailure], rax
0x14004db43  call    UxpSslSealMessage
0x14004db48  mov     r8d, [rsp+120h+var_B8]
0x14004db4d  mov     r14d, eax
0x14004db50  mov     r9d, [rbp+37h+var_B4]
0x14004db54  mov     r10d, [rbp+37h+var_B0]
0x14004db58  mov     r12d, [rbp+37h+var_9C]
0x14004db5c  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004db63  jnz     loc_14004E020
0x14004db69  test    r14d, r14d
0x14004db6c  js      loc_14004E057
0x14004db72  mov     ecx, [rbp+37h+var_A0]
0x14004db75  cmp     ecx, r9d
0x14004db78  ja      loc_14004E051
0x14004db7e  add     rdi, rcx
0x14004db81  sub     r9d, ecx
0x14004db84  sub     r10d, r12d
0x14004db87  dec     r8d
0x14004db8a  mov     [rsp+120h+var_B8], r8d
0x14004db8f  jmp     loc_14004D974
0x14004db94  mov     edx, 22h ; '"'
0x14004db99  mov     [rsp+120h+BugCheckOnFailure], r14d
0x14004db9e  mov     ecx, 411h
0x14004dba3  lea     r8, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids
0x14004dbaa  mov     r9, r12
0x14004dbad  call    WPP_SF_qD
0x14004dbb2  mov     r12, [rbp+37h+var_98]
0x14004dbb6  jmp     loc_14004D9B4
0x14004dbbb  mov     rcx, r13; P
0x14004dbbe  call    UxSslFreeSendBufferList
0x14004dbc3  mov     r9, [rbp+37h+arg_38]
0x14004dbc7  xor     edx, edx
0x14004dbc9  mov     r8, [rbp+37h+arg_30]
0x14004dbcd  mov     ecx, r14d
0x14004dbd0  call    UlInvokeCompletionRoutine
0x14004dbd5  mov     edi, eax
0x14004dbd7  jmp     loc_14004DD35
0x14004dbdc  xorps   xmm0, xmm0
0x14004dbdf  movups  [rbp+37h+var_50], xmm0
0x14004dbe3  movups  [rbp+37h+var_40], xmm0
0x14004dbe7  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004dbee  mov     r12, [rbp+37h+arg_38]
0x14004dbf2  jnz     loc_14004E086
0x14004dbf8  mov     r14, rbx
0x14004dbfb  mov     r15, rbx
0x14004dbfe  test    r13, r13
0x14004dc01  jz      loc_14004DCC3
0x14004dc07  mov     [r13+20h], rsi
0x14004dc0b  lea     rdx, [rsi+14h]; BugCheckParameter2
0x14004dc0f  lock xadd [rdx], ecx
0x14004dc13  inc     ecx
0x14004dc15  cmp     cs:UxDebugCheckRefcount, 0
0x14004dc1c  jnz     loc_14004DD5A
0x14004dc22  mov     rax, [rbp+37h+arg_30]
0x14004dc26  mov     rdi, r13
  ... truncated ...
```
