# TrySend

- ea: `0x18004b1d0`
- end: `0x18004b888`
- name: `TrySend`
- size: `1720`
- prototype: `__int64 __usercall@<rax>(PVOID CompletionContext@<rcx>, __int64)`
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18003c7cc`
- `0x1800411a8`
- `0x180046c34`

## callees

- `0x180008250`
- `0x180022bd2`
- `0x180023b04`
- `0x180024dd4`
- `0x180038944`
- `0x18003aefc`
- `0x18003ff84`
- `0x1800462b0`
- `0x1800479e4`
- `0x180047be4`
- `0x180049af0`
- `0x18004b1d0`
- `0x18004f7cc`
- `0x180050074`
- `0x180050c40`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b329`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b393`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b45d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b4f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b58c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b5fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b65e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b77e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b329`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b393`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b45d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b4f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b58c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b5fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b65e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b77e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b315`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b37f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b4a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b5c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b62a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b718`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b315`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b37f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b4a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b5c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b62a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b718`

## pseudocode

```c
__int64 __fastcall TrySend(char *CompletionContext, __int64 a2, char a3, _DWORD *a4, int *a5)
{
  unsigned int v7; // r11d
  unsigned int v8; // r12d
  char v9; // cl
  __int64 v10; // rdx
  __int64 v11; // r13
  __int64 v12; // r14
  char v13; // r15
  unsigned int v14; // r9d
  unsigned int v15; // edx
  __int64 v16; // r8
  __int64 v17; // rax
  unsigned int v18; // r8d
  int v19; // eax
  unsigned int v20; // edx
  unsigned int v21; // r8d
  unsigned int v22; // r9d
  _QWORD *v23; // r10
  int v24; // edx
  __int64 RdmaData; // rax
  __int64 v27; // rbx
  __int64 v28; // rdx
  int v29; // eax
  __int64 WsaBuf; // r14
  __int64 v31; // rdx
  __int64 v32; // r8
  _DWORD *v33; // rax
  char **v34; // rdx
  char *v35; // rax
  __int64 v36; // rax
  char *v37; // r14
  char **v38; // rcx
  char *v39; // rax
  char **v40; // rcx
  char **v41; // rcx
  int *v42; // r15
  unsigned int Msg; // eax
  unsigned int v44; // r14d
  char *v45; // rax
  char *v46; // rcx
  char **v47; // rdx
  int v48; // ebx
  int *v49; // r14
  int v50; // eax
  __int64 v51; // rax
  int v52; // eax
  int v53; // r12d
  BOOL v54; // [rsp+30h] [rbp-51h]
  unsigned int v55; // [rsp+34h] [rbp-4Dh] BYREF
  __int64 v56; // [rsp+38h] [rbp-49h]
  _BYTE v57[4]; // [rsp+40h] [rbp-41h] BYREF
  int v58; // [rsp+44h] [rbp-3Dh]
  char v59; // [rsp+58h] [rbp-29h]
  int v60; // [rsp+E0h] [rbp+5Fh] BYREF
  __int64 v61; // [rsp+E8h] [rbp+67h] BYREF
  char v62; // [rsp+F0h] [rbp+6Fh]
  _DWORD *v63; // [rsp+F8h] [rbp+77h]

  v63 = a4;
  v62 = a3;
  LODWORD(v61) = 0;
  v55 = 0;
  v58 = 0;
  memset_0(v57, 0, 0x44u);
  v7 = *(_DWORD *)(a2 + 84);
  v8 = *(_DWORD *)(a2 + 80) - v7;
  v9 = *(_BYTE *)(a2 + 128);
  v10 = *(_QWORD *)(a2 + 8);
  v11 = *(_QWORD *)CompletionContext;
  v12 = *(_QWORD *)(a2 + 136);
  v56 = v10;
  if ( !v9 || (v13 = 1, *(_BYTE *)(a2 + 129)) )
    v13 = 0;
  LOBYTE(v60) = v13;
  if ( v12 || (*(_BYTE *)(v11 + 68) & 0x40) != 0 || v9 )
  {
    if ( !*((_DWORD *)CompletionContext + 8) || (v54 = 1, !v10) )
      v54 = 0;
    if ( v12 )
      goto LABEL_28;
  }
  else
  {
    v54 = *(_BYTE *)(a2 + 129) == 0;
  }
  if ( (CompletionContext[801] & 8) != 0 )
  {
    v14 = *(_DWORD *)(a2 + 56);
    v15 = 0;
    if ( !v14 )
      goto LABEL_19;
    v16 = *(_QWORD *)(a2 + 48);
    do
    {
      v17 = 16LL * v15;
      if ( *(_DWORD *)(v17 + v16) > v7 )
        break;
      v7 -= *(_DWORD *)(v17 + v16);
      ++v15;
    }
    while ( v15 < v14 );
    if ( v15 < v14 )
      v18 = *(_DWORD *)(v16 + 16LL * v15) - v7;
    else
LABEL_19:
      v18 = 0;
    v19 = UseRdma(v18);
    while ( v20 < v22 && !v19 )
    {
      v19 = UseRdma(*(unsigned int *)(*v23 + 16LL * v20));
      v20 = v24 + 1;
    }
    if ( *(_DWORD *)(a2 + 40) >= 0x3F0u && v21 <= 0x3F0 && (*(_BYTE *)(a2 + 92) & 4) == 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      *(_DWORD *)(a2 + 92) &= ~2u;
      LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
LABEL_28:
      v19 = 0;
    }
  }
  else
  {
    v19 = UseRdma(v8);
  }
  if ( (*(_BYTE *)(a2 + 92) & 2) == 0 && !v19
    || (*(_BYTE *)(a2 + 92) & 0x21) != 0
    || *((_DWORD *)CompletionContext + 117) == 3
    || v12
    || v13 )
  {
LABEL_89:
    v48 = 997;
    if ( v8 )
    {
      v51 = *((_QWORD *)CompletionContext + 64);
      if ( v51 )
      {
        *(_DWORD *)(v51 + 28) = 0;
        *(_DWORD *)(*((_QWORD *)CompletionContext + 64) + 24LL) = 0;
      }
      v59 = 0;
      v52 = SendUsingSmallMsg(CompletionContext, a2, 0, (__int64)v57, &v61);
      v49 = a5;
      *a5 = v52;
      if ( v52 && v52 != 997 )
        return 0xFFFFFFFFLL;
      v50 = v61;
    }
    else
    {
      v49 = a5;
      v50 = 0;
      LODWORD(v61) = 0;
      *a5 = 0;
    }
    v53 = v8 - v50;
    if ( v54 && v53 <= 0 && (*(_BYTE *)(a2 + 92) & 8) == 0 && v62 )
    {
      CompleteOverlappedIO(
        *(_QWORD *)(*(_QWORD *)CompletionContext + 8LL),
        v56,
        *(void **)(a2 + 64),
        *(void **)(a2 + 72),
        0,
        *(_DWORD *)(a2 + 80));
      v50 = v61;
    }
    if ( *v49 )
    {
      if ( *v49 != 997 )
        goto LABEL_106;
      if ( !(_BYTE)v60 )
        return (unsigned int)-(v48 != 0);
      v48 = 10035;
    }
    else if ( v53 <= 0 || (_BYTE)v60 )
    {
      if ( !v63 )
      {
        v48 = 0;
        return (unsigned int)-(v48 != 0);
      }
      *v63 = v50;
LABEL_106:
      v48 = *v49;
      return (unsigned int)-(v48 != 0);
    }
    *v49 = v48;
    return (unsigned int)-(v48 != 0);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  if ( *(_DWORD *)(a2 + 36) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    *a5 = 997;
    return 0xFFFFFFFFLL;
  }
  RdmaData = GetRdmaData(CompletionContext);
  v27 = RdmaData;
  if ( !RdmaData )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      v28 = 146;
LABEL_46:
      WPP_SF_qq(1025, v28, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, *(_QWORD *)(v11 + 8), CompletionContext);
      goto LABEL_88;
    }
    goto LABEL_88;
  }
  v29 = PopLargeRecvFCInfo(CompletionContext, &v55, *(_QWORD *)(RdmaData + 96));
  if ( v29 == 1 )
  {
    WsaBuf = GetWsaBufExArray(CompletionContext, *(unsigned int *)(a2 + 56));
    if ( !WsaBuf )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
      {
        v28 = 147;
        goto LABEL_46;
      }
LABEL_88:
      LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      goto LABEL_89;
    }
    if ( (((unsigned __int8)CompletionContext[801] >> 3) & ((*(_BYTE *)(a2 + 92) & 0x84) == 0x84)) == 0 )
      goto LABEL_52;
    v60 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(*((_QWORD *)CompletionContext + 2) + 328LL))(
      *((_QWORD *)CompletionContext + 13),
      *(_QWORD *)(*(_QWORD *)(a2 + 120) + 96LL),
      *(unsigned int *)(*((_QWORD *)CompletionContext + 2) + 20LL),
      &v60);
    if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)CompletionContext + 1), 0xFFFFFFFF) == 1 )
      SockDestroySocket(*((_QWORD *)CompletionContext + 1), v31, v32);
    EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    v33 = *(_DWORD **)(a2 + 120);
    *v33 = 1145324612;
    v34 = (char **)*((_QWORD *)CompletionContext + 97);
    if ( *v34 == CompletionContext + 768 )
    {
      v35 = (char *)(v33 + 10);
      *((_QWORD *)v35 + 1) = v34;
      *(_QWORD *)v35 = CompletionContext + 768;
      *v34 = v35;
      *((_QWORD *)CompletionContext + 97) = v35;
      *(_DWORD *)(a2 + 92) &= ~0x80u;
      *(_QWORD *)(a2 + 120) = 0;
LABEL_52:
      LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      *(_QWORD *)(v27 + 56) = CompletionContext;
      *(_QWORD *)(v27 + 64) = a2;
      *(_QWORD *)(a2 + 120) = v27;
      v36 = *((_QWORD *)CompletionContext + 64);
      if ( v36 )
      {
        *(_DWORD *)(v36 + 28) = 0;
        *(_DWORD *)(*((_QWORD *)CompletionContext + 64) + 24LL) = 0;
      }
      return StartRdmaWrite(v27, v55, WsaBuf, a5);
    }
LABEL_86:
    __fastfail(3u);
  }
  if ( v29 != 4 )
  {
    *(_DWORD *)(a2 + 92) &= 0xFFFFFFF9;
    v45 = (char *)(v27 + 40);
    v46 = CompletionContext + 768;
    if ( (CompletionContext[801] & 8) == 0 )
      *(_QWORD *)(a2 + 120) = 0;
    *(_DWORD *)v27 = 1145324612;
    v47 = (char **)*((_QWORD *)CompletionContext + 97);
    if ( *v47 == v46 )
    {
      *(_QWORD *)v45 = v46;
      *(_QWORD *)(v27 + 48) = v47;
      *v47 = v45;
      *((_QWORD *)CompletionContext + 97) = v45;
      goto LABEL_88;
    }
    goto LABEL_86;
  }
  v37 = CompletionContext + 768;
  if ( (CompletionContext[801] & 8) == 0 )
  {
    *(_DWORD *)v27 = 1145324612;
    v38 = (char **)*((_QWORD *)CompletionContext + 97);
    if ( *v38 != v37 )
      goto LABEL_86;
    v39 = (char *)(v27 + 40);
    v27 = 0;
    *(_QWORD *)v39 = v37;
    *((_QWORD *)v39 + 1) = v38;
    *v38 = v39;
    *((_QWORD *)CompletionContext + 97) = v39;
  }
  *(_DWORD *)(a2 + 92) |= 2u;
  LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  if ( (*(_BYTE *)(a2 + 92) & 4) != 0 )
  {
LABEL_63:
    if ( (CompletionContext[801] & 8) != 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      *(_DWORD *)v27 = 1145324612;
      v40 = (char **)*((_QWORD *)v37 + 1);
      if ( *v40 != v37 )
        goto LABEL_86;
      *(_QWORD *)(v27 + 40) = v37;
      *(_QWORD *)(v27 + 48) = v40;
      *v40 = (char *)(v27 + 40);
      *((_QWORD *)v37 + 1) = v27 + 40;
    }
    else
    {
      if ( !(unsigned __int8)InitializeStuckSendTracker((__int64)CompletionContext) )
        goto LABEL_89;
      EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      *(_DWORD *)(*((_QWORD *)CompletionContext + 64) + 24LL) = 1;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    *a5 = 997;
    return 0xFFFFFFFFLL;
  }
  if ( (CompletionContext[801] & 8) == 0 && *((_DWORD *)CompletionContext + 117) >= 2u )
  {
    v37 = CompletionContext + 768;
    goto LABEL_63;
  }
  if ( !(unsigned __int8)AllocateStuckSendTracker(CompletionContext) )
  {
    if ( v27 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      *(_DWORD *)v27 = 1145324612;
      v41 = (char **)*((_QWORD *)CompletionContext + 97);
      if ( *v41 != v37 )
        goto LABEL_86;
      *(_QWORD *)(v27 + 48) = v41;
      *(_QWORD *)(v27 + 40) = v37;
      *v41 = (char *)(v27 + 40);
      *((_QWORD *)CompletionContext + 97) = v27 + 40;
      LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    }
    *a5 = 10055;
    return 0xFFFFFFFFLL;
  }
  v42 = a5;
  Msg = SendLargeSendFirstMsg(CompletionContext);
  v44 = Msg;
  if ( Msg && (Msg != -1 || *v42 != 997) )
    return 0xFFFFFFFFLL;
  InitializeStuckSendTracker((__int64)CompletionContext);
  *(_DWORD *)(*((_QWORD *)CompletionContext + 64) + 36LL) = 1;
  if ( (*(_BYTE *)(a2 + 92) & 8) == 0 || *(_DWORD *)(a2 + 84) < *(_DWORD *)(a2 + 80) )
  {
    *v42 = 997;
    return 0xFFFFFFFFLL;
  }
  if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
    WPP_SF_dd(1036, 148, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v44, *v42);
  return v44;
}

```

## disassembly

```asm
0x18004b1d0  mov     [rsp-8+arg_18], r9
0x18004b1d5  mov     [rsp-8+arg_10], r8b
0x18004b1da  push    rbp
0x18004b1db  push    rbx
0x18004b1dc  push    rsi
0x18004b1dd  push    rdi
0x18004b1de  push    r12
0x18004b1e0  push    r13
0x18004b1e2  push    r14
0x18004b1e4  push    r15
0x18004b1e6  lea     rbp, [rsp-17h]
0x18004b1eb  sub     rsp, 98h
0x18004b1f2  xor     ebx, ebx
0x18004b1f4  mov     rsi, rdx
0x18004b1f7  mov     rdi, rcx
0x18004b1fa  mov     dword ptr [rbp+4Fh+arg_8], ebx
0x18004b1fd  xor     eax, eax
0x18004b1ff  mov     [rbp+4Fh+var_9C], ebx
0x18004b202  xor     edx, edx; Val
0x18004b204  mov     [rbp+4Fh+var_8C], eax
0x18004b207  lea     r8d, [rbx+44h]; Size
0x18004b20b  lea     rcx, [rbp+4Fh+var_90]; void *
0x18004b20f  call    memset_0
0x18004b214  mov     r12d, [rsi+50h]
0x18004b218  lea     rax, [rsi+81h]
0x18004b21f  mov     r11d, [rsi+54h]
0x18004b223  sub     r12d, r11d
0x18004b226  mov     cl, [rsi+80h]
0x18004b22c  mov     rdx, [rsi+8]
0x18004b230  mov     r13, [rdi]
0x18004b233  mov     r14, [rsi+88h]
0x18004b23a  mov     [rbp+4Fh+var_98], rdx
0x18004b23e  test    cl, cl
0x18004b240  jz      short loc_18004B249
0x18004b242  mov     r15b, 1
0x18004b245  cmp     [rax], bl
0x18004b247  jz      short loc_18004B24C
0x18004b249  mov     r15b, bl
0x18004b24c  mov     byte ptr [rbp+4Fh+arg_0], r15b
0x18004b250  test    r14, r14
0x18004b253  jnz     short loc_18004B26C
0x18004b255  test    byte ptr [r13+44h], 40h
0x18004b25a  jnz     short loc_18004B26C
0x18004b25c  test    cl, cl
0x18004b25e  jnz     short loc_18004B26C
0x18004b260  cmp     [rax], bl
0x18004b262  mov     ecx, ebx
0x18004b264  setz    cl
0x18004b267  mov     [rbp+4Fh+var_A0], ecx
0x18004b26a  jmp     short loc_18004B289
0x18004b26c  cmp     [rdi+20h], ebx
0x18004b26f  jz      short loc_18004B27D
0x18004b271  mov     [rbp+4Fh+var_A0], 1
0x18004b278  test    rdx, rdx
0x18004b27b  jnz     short loc_18004B280
0x18004b27d  mov     [rbp+4Fh+var_A0], ebx
0x18004b280  test    r14, r14
0x18004b283  jnz     loc_18004B335
0x18004b289  test    byte ptr [rdi+321h], 8
0x18004b290  jz      loc_18004B339
0x18004b296  mov     r9d, [rsi+38h]
0x18004b29a  lea     r10, [rsi+30h]
0x18004b29e  mov     edx, ebx
0x18004b2a0  test    r9d, r9d
0x18004b2a3  jz      short loc_18004B2D2
0x18004b2a5  mov     r8, [r10]
0x18004b2a8  mov     eax, edx
0x18004b2aa  shl     rax, 4
0x18004b2ae  cmp     [rax+r8], r11d
0x18004b2b2  ja      short loc_18004B2BF
0x18004b2b4  sub     r11d, [rax+r8]
0x18004b2b8  inc     edx
0x18004b2ba  cmp     edx, r9d
0x18004b2bd  jb      short loc_18004B2A8
0x18004b2bf  cmp     edx, r9d
0x18004b2c2  jnb     short loc_18004B2D2
0x18004b2c4  mov     eax, edx
0x18004b2c6  add     rax, rax
0x18004b2c9  mov     r8d, [r8+rax*8]
0x18004b2cd  sub     r8d, r11d
0x18004b2d0  jmp     short loc_18004B2D5
0x18004b2d2  mov     r8d, ebx
0x18004b2d5  inc     edx
0x18004b2d7  mov     ecx, r8d
0x18004b2da  call    UseRdma
0x18004b2df  jmp     short loc_18004B2F7
0x18004b2e1  test    eax, eax
0x18004b2e3  jnz     short loc_18004B2FC
0x18004b2e5  mov     rcx, [r10]
0x18004b2e8  mov     eax, edx
0x18004b2ea  add     rax, rax
0x18004b2ed  mov     ecx, [rcx+rax*8]
0x18004b2f0  call    UseRdma
0x18004b2f5  inc     edx
0x18004b2f7  cmp     edx, r9d
0x18004b2fa  jb      short loc_18004B2E1
0x18004b2fc  mov     ecx, 3F0h
0x18004b301  cmp     [rsi+28h], ecx
0x18004b304  jb      short loc_18004B341
0x18004b306  cmp     r8d, ecx
0x18004b309  ja      short loc_18004B341
0x18004b30b  test    byte ptr [rsi+5Ch], 4
0x18004b30f  jnz     short loc_18004B341
0x18004b311  lea     rcx, [rdi+30h]; lpCriticalSection
0x18004b315  call    cs:__imp_EnterCriticalSection
0x18004b31c  nop     dword ptr [rax+rax+00h]
0x18004b321  and     dword ptr [rsi+5Ch], 0FFFFFFFDh
0x18004b325  lea     rcx, [rdi+30h]; lpCriticalSection
0x18004b329  call    cs:__imp_LeaveCriticalSection
0x18004b330  nop     dword ptr [rax+rax+00h]
0x18004b335  mov     eax, ebx
0x18004b337  jmp     short loc_18004B341
0x18004b339  mov     ecx, r12d
0x18004b33c  call    UseRdma
0x18004b341  test    byte ptr [rsi+5Ch], 2
0x18004b345  jnz     short loc_18004B34F
0x18004b347  test    eax, eax
0x18004b349  jz      loc_18004B78A
0x18004b34f  test    byte ptr [rsi+5Ch], 21h
0x18004b353  jnz     loc_18004B78A
0x18004b359  cmp     dword ptr [rdi+1D4h], 3
0x18004b360  jz      loc_18004B78A
0x18004b366  test    r14, r14
0x18004b369  jnz     loc_18004B78A
0x18004b36f  test    r15b, r15b
0x18004b372  jnz     loc_18004B78A
0x18004b378  lea     r15, [rdi+30h]
0x18004b37c  mov     rcx, r15; lpCriticalSection
0x18004b37f  call    cs:__imp_EnterCriticalSection
0x18004b386  nop     dword ptr [rax+rax+00h]
0x18004b38b  cmp     [rsi+24h], ebx
0x18004b38e  jz      short loc_18004B3B1
0x18004b390  mov     rcx, r15; lpCriticalSection
0x18004b393  call    cs:__imp_LeaveCriticalSection
0x18004b39a  nop     dword ptr [rax+rax+00h]
0x18004b39f  mov     rcx, [rbp+4Fh+arg_20]
0x18004b3a3  mov     dword ptr [rcx], 3E5h
0x18004b3a9  or      eax, 0FFFFFFFFh
0x18004b3ac  jmp     loc_18004B859
0x18004b3b1  mov     rcx, rdi
0x18004b3b4  call    GetRdmaData
0x18004b3b9  mov     rbx, rax
0x18004b3bc  test    rax, rax
0x18004b3bf  jnz     short loc_18004B3D5
0x18004b3c1  test    byte ptr cs:xmmword_180063D60, 2
0x18004b3c8  jz      loc_18004B77B
0x18004b3ce  mov     edx, 92h
0x18004b3d3  jmp     short loc_18004B413
0x18004b3d5  mov     r8, [rax+60h]
0x18004b3d9  lea     rdx, [rbp+4Fh+var_9C]
0x18004b3dd  mov     rcx, rdi
0x18004b3e0  call    PopLargeRecvFCInfo
0x18004b3e5  cmp     eax, 1
0x18004b3e8  jnz     loc_18004B545
0x18004b3ee  mov     edx, [rsi+38h]
0x18004b3f1  mov     rcx, rdi
0x18004b3f4  call    GetWsaBufExArray
0x18004b3f9  mov     r14, rax
0x18004b3fc  test    rax, rax
0x18004b3ff  jnz     short loc_18004B432
0x18004b401  test    byte ptr cs:xmmword_180063D60, 2
0x18004b408  jz      loc_18004B77B
0x18004b40e  mov     edx, 93h
0x18004b413  mov     r9, [r13+8]
0x18004b417  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004b41e  mov     ecx, 401h
0x18004b423  mov     [rsp+0D0h+var_B0], rdi
0x18004b428  call    WPP_SF_qq
0x18004b42d  jmp     loc_18004B77B
0x18004b432  mov     eax, [rsi+5Ch]
0x18004b435  and     eax, 84h
0x18004b43a  cmp     al, 84h
0x18004b43c  mov     al, [rdi+321h]
0x18004b442  setz    cl
0x18004b445  shr     al, 3
0x18004b448  and     cl, al
0x18004b44a  test    cl, 1
0x18004b44d  jz      loc_18004B4F2
0x18004b453  mov     rcx, r15; lpCriticalSection
0x18004b456  mov     [rbp+4Fh+arg_0], 0
0x18004b45d  call    cs:__imp_LeaveCriticalSection
0x18004b464  nop     dword ptr [rax+rax+00h]
0x18004b469  mov     r8, [rdi+10h]
0x18004b46d  lea     r9, [rbp+4Fh+arg_0]
0x18004b471  mov     rdx, [rsi+78h]
0x18004b475  mov     rcx, [rdi+68h]
0x18004b479  mov     rax, [r8+148h]
0x18004b480  mov     r8d, [r8+14h]
0x18004b484  mov     rdx, [rdx+60h]
0x18004b488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b48d  mov     rax, [rdi+8]
0x18004b491  or      ecx, 0FFFFFFFFh
0x18004b494  lock xadd [rax], ecx
0x18004b498  cmp     ecx, 1
0x18004b49b  jnz     short loc_18004B4A6
0x18004b49d  mov     rcx, [rdi+8]
0x18004b4a1  call    SockDestroySocket
0x18004b4a6  mov     rcx, r15; lpCriticalSection
0x18004b4a9  call    cs:__imp_EnterCriticalSection
0x18004b4b0  nop     dword ptr [rax+rax+00h]
0x18004b4b5  mov     rax, [rsi+78h]
0x18004b4b9  lea     rcx, [rdi+300h]
0x18004b4c0  mov     dword ptr [rax], 44444444h
0x18004b4c6  mov     rdx, [rcx+8]
0x18004b4ca  cmp     [rdx], rcx
0x18004b4cd  jnz     loc_18004B766
0x18004b4d3  add     rax, 28h ; '('
0x18004b4d7  mov     [rax+8], rdx
0x18004b4db  mov     [rax], rcx
0x18004b4de  mov     [rdx], rax
0x18004b4e1  mov     [rcx+8], rax
0x18004b4e5  btr     dword ptr [rsi+5Ch], 7
0x18004b4ea  mov     qword ptr [rsi+78h], 0
0x18004b4f2  mov     rcx, r15; lpCriticalSection
0x18004b4f5  call    cs:__imp_LeaveCriticalSection
0x18004b4fc  nop     dword ptr [rax+rax+00h]
0x18004b501  mov     [rbx+38h], rdi
0x18004b505  mov     [rbx+40h], rsi
0x18004b509  mov     [rsi+78h], rbx
0x18004b50d  mov     rax, [rdi+200h]
0x18004b514  test    rax, rax
0x18004b517  jz      short loc_18004B52E
0x18004b519  mov     dword ptr [rax+1Ch], 0
0x18004b520  mov     rax, [rdi+200h]
0x18004b527  mov     dword ptr [rax+18h], 0
0x18004b52e  mov     r9, [rbp+4Fh+arg_20]
0x18004b532  mov     r8, r14
0x18004b535  mov     edx, [rbp+4Fh+var_9C]
0x18004b538  mov     rcx, rbx
0x18004b53b  call    StartRdmaWrite
0x18004b540  jmp     loc_18004B859
0x18004b545  cmp     eax, 4
0x18004b548  jnz     loc_18004B737
0x18004b54e  test    byte ptr [rdi+321h], 8
0x18004b555  lea     r14, [rdi+300h]
0x18004b55c  jnz     short loc_18004B585
0x18004b55e  mov     dword ptr [rbx], 44444444h
0x18004b564  mov     rcx, [r14+8]
0x18004b568  cmp     [rcx], r14
0x18004b56b  jnz     loc_18004B766
0x18004b571  lea     rax, [rbx+28h]
0x18004b575  xor     ebx, ebx
0x18004b577  mov     [rax], r14
0x18004b57a  mov     [rax+8], rcx
0x18004b57e  mov     [rcx], rax
0x18004b581  mov     [r14+8], rax
0x18004b585  or      dword ptr [rsi+5Ch], 2
0x18004b589  mov     rcx, r15; lpCriticalSection
0x18004b58c  call    cs:__imp_LeaveCriticalSection
0x18004b593  nop     dword ptr [rax+rax+00h]
0x18004b598  test    byte ptr [rsi+5Ch], 4
0x18004b59c  jnz     short loc_18004B5B7
0x18004b59e  test    byte ptr [rdi+321h], 8
0x18004b5a5  jnz     short loc_18004B616
0x18004b5a7  cmp     dword ptr [rdi+1D4h], 2
0x18004b5ae  jb      short loc_18004B616
0x18004b5b0  lea     r14, [rdi+300h]
0x18004b5b7  test    byte ptr [rdi+321h], 8
0x18004b5be  jz      loc_18004B709
0x18004b5c4  mov     rcx, r15; lpCriticalSection
0x18004b5c7  call    cs:__imp_EnterCriticalSection
0x18004b5ce  nop     dword ptr [rax+rax+00h]
0x18004b5d3  mov     dword ptr [rbx], 44444444h
0x18004b5d9  mov     rcx, [r14+8]
0x18004b5dd  cmp     [rcx], r14
0x18004b5e0  jnz     loc_18004B766
0x18004b5e6  lea     rax, [rbx+28h]
0x18004b5ea  mov     [rax], r14
0x18004b5ed  mov     [rax+8], rcx
0x18004b5f1  mov     [rcx], rax
0x18004b5f4  mov     [r14+8], rax
0x18004b5f8  mov     rcx, r15; lpCriticalSection
0x18004b5fb  call    cs:__imp_LeaveCriticalSection
0x18004b602  nop     dword ptr [rax+rax+00h]
0x18004b607  mov     rax, [rbp+4Fh+arg_20]
0x18004b60b  mov     dword ptr [rax], 3E5h
0x18004b611  jmp     loc_18004B3A9
0x18004b616  mov     rcx, rdi
0x18004b619  call    AllocateStuckSendTracker
0x18004b61e  test    al, al
0x18004b620  jnz     short loc_18004B679
0x18004b622  test    rbx, rbx
0x18004b625  jz      short loc_18004B66A
0x18004b627  mov     rcx, r15; lpCriticalSection
0x18004b62a  call    cs:__imp_EnterCriticalSection
0x18004b631  nop     dword ptr [rax+rax+00h]
0x18004b636  mov     dword ptr [rbx], 44444444h
0x18004b63c  mov     rcx, [r14+8]
0x18004b640  cmp     [rcx], r14
0x18004b643  jnz     loc_18004B766
0x18004b649  lea     rax, [rbx+28h]
0x18004b64d  mov     [rax+8], rcx
0x18004b651  mov     [rax], r14
0x18004b654  mov     [rcx], rax
0x18004b657  mov     rcx, r15; lpCriticalSection
0x18004b65a  mov     [r14+8], rax
0x18004b65e  call    cs:__imp_LeaveCriticalSection
0x18004b665  nop     dword ptr [rax+rax+00h]
0x18004b66a  mov     rax, [rbp+4Fh+arg_20]
0x18004b66e  mov     dword ptr [rax], 2747h
  ... truncated ...
```
