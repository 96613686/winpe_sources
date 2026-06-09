# IkeInitMMInitiatorPhase1

- ea: `0x180043fb0`
- end: `0x180044593`
- name: `IkeInitMMInitiatorPhase1`
- size: `1507`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800400a0`

## callees

- `0x180002a40`
- `0x180006e60`
- `0x180008388`
- `0x1800283d0`
- `0x180040d70`
- `0x180043fb0`
- `0x18004890c`
- `0x180050850`
- `0x18005bce4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004404c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044091`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800441eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044261`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800442a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044445`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004448d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004404c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044091`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800441eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044261`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800442a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044445`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004448d`
- `ntdll!EtwEventWriteTransfer` at `0x18004416b`
- `ntdll!EtwEventWriteTransfer` at `0x180044382`
- `ntdll!EtwEventWriteTransfer` at `0x18004455e`
- `ntdll!EtwEventWriteTransfer` at `0x18004416b`
- `ntdll!EtwEventWriteTransfer` at `0x180044382`
- `ntdll!EtwEventWriteTransfer` at `0x18004455e`

## pseudocode

```c
__int64 __fastcall IkeInitMMInitiatorPhase1(__int64 a1, __int64 a2, unsigned int *a3, LPCRITICAL_SECTION *a4)
{
  LPCRITICAL_SECTION *v4; // r14
  __int64 v6; // rbx
  __int64 v8; // rsi
  LPCRITICAL_SECTION v9; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v12; // rcx
  DWORD v13; // ecx
  char *v14; // rax
  const WCHAR *v15; // rdx
  __int64 v16; // rax
  bool v17; // zf
  int v18; // eax
  __int64 CanProcessAcquire; // rdi
  __int64 LockSemaphore_low; // rcx
  _QWORD *v21; // rdi
  __int64 *v22; // rax
  __int64 v23; // r14
  unsigned int v24; // ebx
  __int64 v25; // rdi
  __int64 TlsPeerAddr; // rax
  LPCRITICAL_SECTION v27; // rax
  DWORD v28; // ecx
  LPCRITICAL_SECTION **v29; // rax
  LPCRITICAL_SECTION *v30; // rcx
  DWORD v31; // ecx
  char *v32; // rax
  const WCHAR *v33; // rdx
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // r8
  LPCRITICAL_SECTION v37; // rbx
  _DWORD *v38; // rax
  LPCRITICAL_SECTION v39; // rax
  DWORD v40; // ecx
  LPCRITICAL_SECTION **v41; // rax
  LPCRITICAL_SECTION *v42; // rcx
  DWORD v43; // ecx
  char *v44; // rax
  const WCHAR *v45; // rdx
  int v46; // esi
  __int64 v48; // [rsp+28h] [rbp-A1h]
  LPCRITICAL_SECTION v49; // [rsp+40h] [rbp-89h] BYREF
  __int64 v50; // [rsp+48h] [rbp-81h]
  unsigned int v51; // [rsp+50h] [rbp-79h] BYREF
  __int64 v52; // [rsp+58h] [rbp-71h] BYREF
  LPCRITICAL_SECTION *v53; // [rsp+60h] [rbp-69h] BYREF
  int v54; // [rsp+68h] [rbp-61h] BYREF
  int v55; // [rsp+6Ch] [rbp-5Dh]
  __int64 v56; // [rsp+70h] [rbp-59h]
  char *v57; // [rsp+80h] [rbp-49h] BYREF
  int v58; // [rsp+88h] [rbp-41h]
  int v59; // [rsp+8Ch] [rbp-3Dh]
  int *v60; // [rsp+90h] [rbp-39h]
  int v61; // [rsp+98h] [rbp-31h]
  int v62; // [rsp+9Ch] [rbp-2Dh]
  LPCRITICAL_SECTION **v63; // [rsp+A0h] [rbp-29h]
  __int64 v64; // [rsp+A8h] [rbp-21h]
  const WCHAR *v65; // [rsp+B0h] [rbp-19h]
  int v66; // [rsp+B8h] [rbp-11h]
  int v67; // [rsp+BCh] [rbp-Dh]
  unsigned int *v68; // [rsp+C0h] [rbp-9h]
  __int64 v69; // [rsp+C8h] [rbp-1h]

  v53 = a4;
  v50 = a2;
  v4 = a4;
  v49 = 0;
  v6 = a2;
  v8 = -1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v9 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v9 = gIkeExtGlobals;
LABEL_9:
    v12 = 0;
    goto LABEL_10;
  }
  v12 = *Value;
  v9 = gIkeExtGlobals;
LABEL_10:
  v52 = v12;
  v63 = (LPCRITICAL_SECTION **)&v52;
  v64 = 8;
  if ( !v9 )
    goto LABEL_18;
  v13 = (DWORD)v9[86].LockSemaphore;
  if ( v13 == -1 )
    goto LABEL_18;
  v14 = (char *)TlsGetValue(v13);
  v15 = (const WCHAR *)(v14 + 8);
  if ( !v14 )
    v15 = 0;
  if ( v15 )
  {
    v16 = -1;
    do
      v17 = v15[++v16] == 0;
    while ( !v17 );
    v18 = 2 * v16 + 2;
  }
  else
  {
LABEL_18:
    v15 = &LocaleName;
    v18 = 2;
  }
  v66 = v18;
  v65 = v15;
  v68 = (unsigned int *)"IkeInitMMInitiatorPhase1";
  v55 = 5;
  v57 = off_180173280;
  v67 = 0;
  v69 = 25;
  v54 = 184549376;
  v56 = 1;
  v58 = *(unsigned __int16 *)off_180173280;
  v60 = &dword_180166EA4;
  v59 = 2;
  v61 = 45;
  v62 = 1;
  v51 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EtwEventWriteTransfer(qword_180173298, &v54, 0, 0, 5, &v57);
LABEL_20:
  CanProcessAcquire = IkeCanProcessAcquire(a1);
  if ( CanProcessAcquire )
    goto LABEL_55;
  CanProcessAcquire = DoesActivePeerStateExist((int)a1 + 16, *(_DWORD *)(a1 + 372), 0, 0, 0, (__int64)a3, 0);
  if ( CanProcessAcquire )
    goto LABEL_55;
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    if ( gIkeExtGlobals
      && (LockSemaphore_low = LODWORD(gIkeExtGlobals[86].LockSemaphore), (_DWORD)LockSemaphore_low != -1)
      && (v22 = (__int64 *)TlsGetValue(LockSemaphore_low), v21 = WPP_GLOBAL_Control, v22) )
    {
      v23 = *v22;
    }
    else
    {
      LODWORD(v23) = 0;
    }
    v24 = *a3;
    v25 = v21[2];
    TlsPeerAddr = IkeGetTlsPeerAddr(LockSemaphore_low);
    LODWORD(v48) = v24;
    WPP_SF_iSL(v25, 12, (unsigned int)WPP_142eefe8c0a8324bd0f22eb85fef74f7_Traceguids, v23, TlsPeerAddr, v48);
    v6 = v50;
    v4 = v53;
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v27 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v28 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v28 != -1 )
      {
        v29 = (LPCRITICAL_SECTION **)TlsGetValue(v28);
        if ( v29 )
        {
          v30 = *v29;
          v27 = gIkeExtGlobals;
LABEL_38:
          v53 = v30;
          v63 = &v53;
          v64 = 8;
          if ( !v27 )
            goto LABEL_46;
          v31 = (DWORD)v27[86].LockSemaphore;
          if ( v31 == -1 )
            goto LABEL_46;
          v32 = (char *)TlsGetValue(v31);
          v33 = (const WCHAR *)(v32 + 8);
          if ( !v32 )
            v33 = 0;
          if ( v33 )
          {
            v34 = -1;
            do
              v17 = v33[++v34] == 0;
            while ( !v17 );
            v35 = 2 * v34 + 2;
          }
          else
          {
LABEL_46:
            v33 = &LocaleName;
            v35 = 2;
          }
          v66 = v35;
          v51 = *a3;
          v65 = v33;
          v68 = &v51;
          v55 = 4;
          v57 = off_180173280;
          v67 = 0;
          v69 = 4;
          v54 = 184549376;
          v56 = 0;
          v58 = *(unsigned __int16 *)off_180173280;
          v60 = &dword_18016236C;
          v59 = 2;
          v61 = 67;
          v62 = 1;
          LODWORD(v52) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v54, 0, 0, 5, &v57);
          goto LABEL_48;
        }
        v27 = gIkeExtGlobals;
      }
    }
    v30 = 0;
    goto LABEL_38;
  }
LABEL_48:
  CanProcessAcquire = IkeCreateMMSA(*(_DWORD *)(a1 + 372), a1 + 16, &v49);
  if ( !CanProcessAcquire )
  {
    v36 = v6;
    v37 = v49;
    CanProcessAcquire = IkeInitializeMMSAInitiator(v49, a1, v36);
    if ( !CanProcessAcquire )
    {
      if ( LODWORD(v37[14].LockSemaphore) == 2 )
      {
        v38 = v37[27].LockSemaphore;
        if ( *(_DWORD *)(a1 + 312) == 1 )
          v38[141] = 2;
        else
          v38[141] = 1;
      }
      *v4 = v37;
    }
  }
LABEL_55:
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    return IkeReturnError(CanProcessAcquire, "IkeInitMMInitiatorPhase1");
  v39 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_63;
  v40 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v40 == -1 )
    goto LABEL_63;
  v41 = (LPCRITICAL_SECTION **)TlsGetValue(v40);
  if ( !v41 )
  {
    v39 = gIkeExtGlobals;
LABEL_63:
    v42 = 0;
    goto LABEL_64;
  }
  v42 = *v41;
  v39 = gIkeExtGlobals;
LABEL_64:
  v53 = v42;
  v63 = &v53;
  v64 = 8;
  if ( !v39 )
    goto LABEL_71;
  v43 = (DWORD)v39[86].LockSemaphore;
  if ( v43 == -1 )
    goto LABEL_71;
  v44 = (char *)TlsGetValue(v43);
  v45 = (const WCHAR *)(v44 + 8);
  if ( !v44 )
    v45 = 0;
  if ( v45 )
  {
    do
      v17 = v45[++v8] == 0;
    while ( !v17 );
    v46 = 2 * v8 + 2;
  }
  else
  {
LABEL_71:
    v45 = &LocaleName;
    v46 = 2;
  }
  v65 = v45;
  v68 = (unsigned int *)"IkeInitMMInitiatorPhase1";
  v55 = 5;
  v57 = off_180173280;
  v66 = v46;
  v67 = 0;
  v69 = 25;
  v54 = 184549376;
  v56 = 1;
  v58 = *(unsigned __int16 *)off_180173280;
  v60 = (int *)byte_180166E6B;
  v59 = 2;
  v61 = 45;
  v62 = 1;
  LODWORD(v52) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EtwEventWriteTransfer(qword_180173298, &v54, 0, 0, 5, &v57);
  return IkeReturnError(CanProcessAcquire, "IkeInitMMInitiatorPhase1");
}

```

## disassembly

```asm
0x180043fb0  push    rbp
0x180043fb2  push    rbx
0x180043fb3  push    rsi
0x180043fb4  push    rdi
0x180043fb5  push    r12
0x180043fb7  push    r13
0x180043fb9  push    r14
0x180043fbb  push    r15
0x180043fbd  lea     rbp, [rsp-1Fh]
0x180043fc2  sub     rsp, 0E8h
0x180043fc9  mov     rax, cs:__security_cookie
0x180043fd0  xor     rax, rsp
0x180043fd3  mov     [rbp+57h+var_50], rax
0x180043fd7  mov     eax, cs:dword_180173278
0x180043fdd  lea     r12, _TraceLoggingMetadataEnd
0x180043fe4  xor     edi, edi
0x180043fe6  mov     [rbp+57h+var_C0], r9
0x180043fea  mov     [rsp+120h+var_D8], rdx
0x180043fef  mov     r14, r9
0x180043ff2  mov     [rsp+120h+var_E0], rdi
0x180043ff7  mov     r13, r8
0x180043ffa  mov     rbx, rdx
0x180043ffd  mov     r15, rcx
0x180044000  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180044007  cmp     eax, 5
0x18004400a  jbe     loc_180044171
0x180044010  mov     rcx, cs:qword_180173290
0x180044017  mov     rax, cs:qword_180173288
0x18004401e  test    al, 1
0x180044020  jz      loc_180044171
0x180044026  mov     rax, rcx
0x180044029  and     eax, 1
0x18004402c  cmp     rax, rcx
0x18004402f  jnz     loc_180044171
0x180044035  mov     rax, cs:gIkeExtGlobals
0x18004403c  test    rax, rax
0x18004403f  jz      short loc_18004406A
0x180044041  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180044047  cmp     ecx, 0FFFFFFFFh
0x18004404a  jz      short loc_18004406A
0x18004404c  call    cs:__imp_TlsGetValue
0x180044052  test    rax, rax
0x180044055  jz      short loc_180044063
0x180044057  mov     rcx, [rax]
0x18004405a  mov     rax, cs:gIkeExtGlobals
0x180044061  jmp     short loc_18004406D
0x180044063  mov     rax, cs:gIkeExtGlobals
0x18004406a  mov     rcx, rdi
0x18004406d  mov     [rbp+57h+var_C8], rcx
0x180044071  lea     rcx, [rbp+57h+var_C8]
0x180044075  mov     [rbp+57h+var_80], rcx
0x180044079  mov     [rbp+57h+var_78], 8
0x180044081  test    rax, rax
0x180044084  jz      short loc_1800440C4
0x180044086  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18004408c  cmp     ecx, 0FFFFFFFFh
0x18004408f  jz      short loc_1800440C4
0x180044091  call    cs:__imp_TlsGetValue
0x180044097  test    rax, rax
0x18004409a  lea     rdx, [rax+8]
0x18004409e  cmovz   rdx, rdi
0x1800440a2  test    rdx, rdx
0x1800440a5  jz      short loc_1800440C4
0x1800440a7  mov     rax, rsi
0x1800440aa  nop     word ptr [rax+rax+00h]
0x1800440b0  cmp     [rdx+rax*2+2], di
0x1800440b5  lea     rax, [rax+1]
0x1800440b9  jnz     short loc_1800440B0
0x1800440bb  lea     eax, ds:2[rax*2]
0x1800440c2  jmp     short loc_1800440D0
0x1800440c4  lea     rdx, LocaleName
0x1800440cb  mov     eax, 2
0x1800440d0  mov     [rbp+57h+var_68], eax
0x1800440d3  lea     rcx, _TraceLoggingMetadata
0x1800440da  mov     [rbp+57h+var_70], rdx
0x1800440de  lea     rax, aIkeinitmminiti; "IkeInitMMInitiatorPhase1"
0x1800440e5  mov     [rbp+57h+var_60], rax
0x1800440e9  lea     rdx, [rbp+57h+var_B8]
0x1800440ed  movzx   eax, cs:word_180166E9A
0x1800440f4  xor     r9d, r9d
0x1800440f7  mov     [rbp+57h+var_B4], eax
0x1800440fa  xor     r8d, r8d
0x1800440fd  mov     rax, cs:off_180173280
0x180044104  mov     [rbp+57h+var_A0], rax
0x180044108  mov     [rbp+57h+var_64], edi
0x18004410b  mov     [rbp+57h+var_58], 19h
0x180044113  mov     [rbp+57h+var_B8], 0B000000h
0x18004411a  mov     [rbp+57h+var_B0], 1
0x180044122  movzx   eax, word ptr [rax]
0x180044125  mov     [rbp+57h+var_98], eax
0x180044128  lea     rax, dword_180166EA4
0x18004412f  mov     [rbp+57h+var_90], rax
0x180044133  mov     rax, r12
0x180044136  sub     eax, ecx
0x180044138  mov     [rbp+57h+var_94], 2
0x18004413f  mov     [rbp+57h+var_88], 2Dh ; '-'
0x180044146  mov     [rbp+57h+var_84], 1
0x18004414d  mov     [rbp+57h+var_D0], eax
0x180044150  mov     eax, [rbp+57h+var_D0]
0x180044153  mov     rcx, cs:qword_180173298
0x18004415a  lea     rax, [rbp+57h+var_A0]
0x18004415e  mov     [rsp+120h+var_F8], rax
0x180044163  mov     dword ptr [rsp+120h+var_100], 5
0x18004416b  call    cs:__imp_EtwEventWriteTransfer
0x180044171  mov     rcx, r15
0x180044174  call    IkeCanProcessAcquire
0x180044179  mov     rdi, rax
0x18004417c  test    rax, rax
0x18004417f  jnz     loc_1800443FA
0x180044185  mov     edx, [r15+174h]
0x18004418c  lea     rcx, [r15+10h]
0x180044190  mov     [rsp+120h+var_F0], rax
0x180044195  xor     r9d, r9d
0x180044198  mov     [rsp+120h+var_F8], r13
0x18004419d  xor     r8d, r8d
0x1800441a0  mov     dword ptr [rsp+120h+var_100], eax
0x1800441a4  call    DoesActivePeerStateExist
0x1800441a9  mov     rdi, rax
0x1800441ac  test    rax, rax
0x1800441af  jnz     loc_1800443F3
0x1800441b5  mov     rdi, cs:WPP_GLOBAL_Control
0x1800441bc  lea     rax, WPP_GLOBAL_Control
0x1800441c3  cmp     rdi, rax
0x1800441c6  jz      short loc_18004423B
0x1800441c8  cmp     byte ptr [rdi+19h], 4
0x1800441cc  jb      short loc_18004423B
0x1800441ce  test    byte ptr [rdi+1Ch], 10h
0x1800441d2  jz      short loc_18004423B
0x1800441d4  mov     rax, cs:gIkeExtGlobals
0x1800441db  test    rax, rax
0x1800441de  jz      short loc_180044202
0x1800441e0  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800441e6  cmp     ecx, 0FFFFFFFFh
0x1800441e9  jz      short loc_180044202
0x1800441eb  call    cs:__imp_TlsGetValue
0x1800441f1  mov     rdi, cs:WPP_GLOBAL_Control
0x1800441f8  test    rax, rax
0x1800441fb  jz      short loc_180044202
0x1800441fd  mov     r14, [rax]
0x180044200  jmp     short loc_180044205
0x180044202  xor     r14d, r14d
0x180044205  mov     ebx, [r13+0]
0x180044209  mov     rdi, [rdi+10h]
0x18004420d  call    IkeGetTlsPeerAddr
0x180044212  mov     edx, 0Ch
0x180044217  mov     dword ptr [rsp+120h+var_F8], ebx
0x18004421b  mov     r9, r14
0x18004421e  mov     [rsp+120h+var_100], rax
0x180044223  lea     r8, WPP_142eefe8c0a8324bd0f22eb85fef74f7_Traceguids
0x18004422a  mov     rcx, rdi
0x18004422d  call    WPP_SF_iSL
0x180044232  mov     rbx, [rsp+120h+var_D8]
0x180044237  mov     r14, [rbp+57h+var_C0]
0x18004423b  mov     eax, cs:dword_180173278
0x180044241  cmp     eax, 4
0x180044244  jbe     loc_180044388
0x18004424a  mov     rax, cs:gIkeExtGlobals
0x180044251  test    rax, rax
0x180044254  jz      short loc_180044281
0x180044256  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18004425c  cmp     ecx, 0FFFFFFFFh
0x18004425f  jz      short loc_180044281
0x180044261  call    cs:__imp_TlsGetValue
0x180044267  test    rax, rax
0x18004426a  jz      short loc_18004427A
0x18004426c  mov     rcx, [rax]
0x18004426f  xor     edi, edi
0x180044271  mov     rax, cs:gIkeExtGlobals
0x180044278  jmp     short loc_180044285
0x18004427a  mov     rax, cs:gIkeExtGlobals
0x180044281  xor     edi, edi
0x180044283  mov     ecx, edi
0x180044285  mov     [rbp+57h+var_C0], rcx
0x180044289  lea     rcx, [rbp+57h+var_C0]
0x18004428d  mov     [rbp+57h+var_80], rcx
0x180044291  mov     [rbp+57h+var_78], 8
0x180044299  test    rax, rax
0x18004429c  jz      short loc_1800442D7
0x18004429e  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800442a4  cmp     ecx, 0FFFFFFFFh
0x1800442a7  jz      short loc_1800442D7
0x1800442a9  call    cs:__imp_TlsGetValue
0x1800442af  test    rax, rax
0x1800442b2  lea     rdx, [rax+8]
0x1800442b6  cmovz   rdx, rdi
0x1800442ba  test    rdx, rdx
0x1800442bd  jz      short loc_1800442D7
0x1800442bf  mov     rax, rsi
0x1800442c2  cmp     word ptr [rdx+rax*2+2], 0
0x1800442c8  lea     rax, [rax+1]
0x1800442cc  jnz     short loc_1800442C2
0x1800442ce  lea     eax, ds:2[rax*2]
0x1800442d5  jmp     short loc_1800442E3
0x1800442d7  lea     rdx, LocaleName
0x1800442de  mov     eax, 2
0x1800442e3  mov     [rbp+57h+var_68], eax
0x1800442e6  lea     rcx, _TraceLoggingMetadata
0x1800442ed  mov     eax, [r13+0]
0x1800442f1  xor     r9d, r9d
0x1800442f4  mov     [rbp+57h+var_D0], eax
0x1800442f7  xor     r8d, r8d
0x1800442fa  mov     [rbp+57h+var_70], rdx
0x1800442fe  lea     rax, [rbp+57h+var_D0]
0x180044302  mov     [rbp+57h+var_60], rax
0x180044306  lea     rdx, [rbp+57h+var_B8]
0x18004430a  movzx   eax, cs:word_180162362
0x180044311  mov     [rbp+57h+var_B4], eax
0x180044314  mov     rax, cs:off_180173280
0x18004431b  mov     [rbp+57h+var_A0], rax
0x18004431f  mov     [rbp+57h+var_64], edi
0x180044322  mov     [rbp+57h+var_58], 4
0x18004432a  mov     [rbp+57h+var_B8], 0B000000h
0x180044331  mov     [rbp+57h+var_B0], rdi
0x180044335  movzx   eax, word ptr [rax]
0x180044338  mov     [rbp+57h+var_98], eax
0x18004433b  lea     rax, dword_18016236C
0x180044342  mov     [rbp+57h+var_90], rax
0x180044346  lea     rax, _TraceLoggingMetadataEnd
0x18004434d  sub     eax, ecx
0x18004434f  mov     [rbp+57h+var_94], 2
0x180044356  mov     [rbp+57h+var_88], 43h ; 'C'
0x18004435d  mov     [rbp+57h+var_84], 1
0x180044364  mov     dword ptr [rbp+57h+var_C8], eax
0x180044367  mov     eax, dword ptr [rbp+57h+var_C8]
0x18004436a  mov     rcx, cs:qword_180173298
0x180044371  lea     rax, [rbp+57h+var_A0]
0x180044375  mov     [rsp+120h+var_F8], rax
0x18004437a  mov     dword ptr [rsp+120h+var_100], 5
0x180044382  call    cs:__imp_EtwEventWriteTransfer
0x180044388  mov     ecx, [r15+174h]
0x18004438f  lea     r8, [rsp+120h+var_E0]
0x180044394  lea     rdx, [r15+10h]
0x180044398  call    IkeCreateMMSA
0x18004439d  mov     rdi, rax
0x1800443a0  test    rax, rax
0x1800443a3  jnz     short loc_1800443F3
0x1800443a5  mov     r8, rbx
0x1800443a8  mov     rdx, r15
0x1800443ab  mov     rbx, [rsp+120h+var_E0]
0x1800443b0  mov     rcx, rbx
0x1800443b3  call    IkeInitializeMMSAInitiator
0x1800443b8  mov     rdi, rax
0x1800443bb  test    rax, rax
0x1800443be  jnz     short loc_1800443F3
0x1800443c0  cmp     dword ptr [rbx+248h], 2
0x1800443c7  jnz     short loc_1800443F0
0x1800443c9  cmp     dword ptr [r15+138h], 1
0x1800443d1  mov     rax, [rbx+450h]
0x1800443d8  jnz     short loc_1800443E6
0x1800443da  mov     dword ptr [rax+234h], 2
0x1800443e4  jmp     short loc_1800443F0
0x1800443e6  mov     dword ptr [rax+234h], 1
0x1800443f0  mov     [r14], rbx
0x1800443f3  lea     r12, _TraceLoggingMetadataEnd
0x1800443fa  mov     eax, cs:dword_180173278
0x180044400  cmp     eax, 5
0x180044403  jbe     loc_180044564
0x180044409  mov     rcx, cs:qword_180173290
0x180044410  mov     rax, cs:qword_180173288
0x180044417  test    al, 1
0x180044419  jz      loc_180044564
0x18004441f  mov     rax, rcx
0x180044422  and     eax, 1
0x180044425  cmp     rax, rcx
0x180044428  jnz     loc_180044564
0x18004442e  mov     rax, cs:gIkeExtGlobals
0x180044435  test    rax, rax
0x180044438  jz      short loc_180044465
0x18004443a  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180044440  cmp     ecx, 0FFFFFFFFh
0x180044443  jz      short loc_180044465
0x180044445  call    cs:__imp_TlsGetValue
0x18004444b  test    rax, rax
0x18004444e  jz      short loc_18004445E
0x180044450  mov     rcx, [rax]
0x180044453  xor     ebx, ebx
0x180044455  mov     rax, cs:gIkeExtGlobals
0x18004445c  jmp     short loc_180044469
0x18004445e  mov     rax, cs:gIkeExtGlobals
0x180044465  xor     ebx, ebx
0x180044467  mov     ecx, ebx
0x180044469  mov     [rbp+57h+var_C0], rcx
0x18004446d  lea     rcx, [rbp+57h+var_C0]
0x180044471  mov     [rbp+57h+var_80], rcx
0x180044475  mov     [rbp+57h+var_78], 8
0x18004447d  test    rax, rax
0x180044480  jz      short loc_1800444B8
0x180044482  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180044488  cmp     ecx, 0FFFFFFFFh
0x18004448b  jz      short loc_1800444B8
0x18004448d  call    cs:__imp_TlsGetValue
0x180044493  test    rax, rax
0x180044496  lea     rdx, [rax+8]
0x18004449a  cmovz   rdx, rbx
0x18004449e  test    rdx, rdx
0x1800444a1  jz      short loc_1800444B8
0x1800444a3  cmp     word ptr [rdx+rsi*2+2], 0
0x1800444a9  lea     rsi, [rsi+1]
0x1800444ad  jnz     short loc_1800444A3
0x1800444af  lea     esi, ds:2[rsi*2]
  ... truncated ...
```
