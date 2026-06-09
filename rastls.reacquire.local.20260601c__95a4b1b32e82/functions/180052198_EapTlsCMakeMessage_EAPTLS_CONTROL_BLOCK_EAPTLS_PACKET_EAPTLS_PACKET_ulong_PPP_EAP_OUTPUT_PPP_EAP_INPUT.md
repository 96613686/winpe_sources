# EapTlsCMakeMessage(_EAPTLS_CONTROL_BLOCK *,_EAPTLS_PACKET *,_EAPTLS_PACKET *,ulong,_PPP_EAP_OUTPUT *,_PPP_EAP_INPUT *)

- ea: `0x180052198`
- end: `0x180052b6f`
- name: `?EapTlsCMakeMessage@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_EAPTLS_PACKET@@1KPEAU_PPP_EAP_OUTPUT@@PEAU_PPP_EAP_INPUT@@@Z`
- size: `2519`
- prototype: `__int64 __fastcall(struct _EAPTLS_CONTROL_BLOCK *, struct _PPP_EAP_PACKET *, struct _EAPTLS_PACKET *, unsigned int, struct _PPP_EAP_OUTPUT *, struct _PPP_EAP_INPUT *)`
- caller_count: `2`
- callee_count: `23`
- tags: ``

## callers

- `0x180009418`
- `0x180017ad0`

## callees

- `0x180005010`
- `0x180007d00`
- `0x18001e0c0`
- `0x180020140`
- `0x1800213e0`
- `0x180021504`
- `0x180025ff0`
- `0x180032e7c`
- `0x18004d58c`
- `0x18004f23c`
- `0x180052198`
- `0x180053ac8`
- `0x180054094`
- `0x180056290`
- `0x1800566ac`
- `0x18005697c`
- `0x180059a50`
- `0x18005b790`
- `0x18005b944`
- `0x18005bad0`
- `0x18005dd00`
- `0x18005de90`
- `0x180068830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524cc`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800524a8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800524a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052500`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052500`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005241a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005241a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005250f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052601`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052af7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005250f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052601`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052af7`
- `eapputil!EapConvertWireToHostFormat16` at `0x1800529eb`
- `eapputil!EapConvertWireToHostFormat16` at `0x1800529eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EapTlsCMakeMessage(
        struct _EAPTLS_CONTROL_BLOCK *a1,
        struct _PPP_EAP_PACKET *a2,
        struct _EAPTLS_PACKET *a3,
        unsigned int a4,
        struct _PPP_EAP_OUTPUT *a5,
        struct _PPP_EAP_INPUT *a6)
{
  struct _EAPTLS_PACKET *v7; // r15
  struct _PPP_EAP_PACKET *v8; // r14
  struct _PPP_EAP_OUTPUT *v10; // rsi
  struct _PPP_EAP_INPUT *v11; // rbp
  unsigned int v12; // eax
  int v13; // r8d
  unsigned int v14; // r12d
  unsigned int ReplyMessage; // edi
  int v16; // ebp
  unsigned int v17; // eax
  struct _EAPTLS_CONTROL_BLOCK *v18; // rcx
  __int64 v19; // rdx
  unsigned int v20; // eax
  struct _EAPTLS_CONTROL_BLOCK *v21; // rcx
  __int64 v22; // rdx
  char *v23; // rax
  HANDLE *v24; // r15
  HANDLE Thread; // r12
  DWORD LastError; // eax
  CWorkerThreadState *v27; // rcx
  int v28; // eax
  void *v29; // rcx
  unsigned int v30; // edi
  unsigned int v31; // eax
  unsigned int v32; // r9d
  int v33; // eax
  int Code; // r9d
  const char *v35; // r9
  int v36; // eax
  __int64 v37; // rcx
  int v38; // eax
  unsigned int v40; // [rsp+70h] [rbp+8h] BYREF
  struct _EAPTLS_PACKET *v41; // [rsp+80h] [rbp+18h]

  v41 = a3;
  v40 = 0;
  v7 = a3;
  v8 = a2;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_dL(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *(unsigned int *)a1, *((_DWORD *)a1 + 1));
  v10 = a5;
  v11 = a6;
  v12 = IsPinRetry(a1, a6, (int *)&v40, a5);
  v14 = v40;
  ReplyMessage = v12;
  if ( v12 )
  {
    if ( !v11 || !v11->fDataReceivedFromInteractiveUI )
    {
      ReplyMessage = 0;
      v10->Action = EAPACTION_NoAction;
    }
    goto LABEL_140;
  }
  if ( v40 == 1 )
    v8 = CopyEapPacket(*((struct _PPP_EAP_PACKET **)a1 + 95));
  if ( v8 )
  {
    if ( v8->Code == 1 )
    {
      if ( *((_BYTE *)a1 + 721) == v8->Id && *(_DWORD *)a1 )
      {
        *((_BYTE *)a1 + 720) = 2;
        ReplyMessage = BuildPacket(v7, a4, a1);
        if ( ReplyMessage )
        {
          v16 = 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              305,
              &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
              *((unsigned __int8 *)a1 + 721));
          v16 = 4;
        }
LABEL_139:
        v10->Action = v16;
        goto LABEL_140;
      }
      if ( (v8[1].Code & 0x20) == 0 )
      {
        if ( !*(_DWORD *)a1 )
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 306, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
          goto LABEL_22;
        }
        goto LABEL_55;
      }
      v17 = EapTlsReset(a1);
      ReplyMessage = v17;
      if ( v17 )
      {
        if ( (v17 & 0x1FFF0000) == 0x100000 )
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 307, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v17);
          goto LABEL_34;
        }
        if ( v17 == 847 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
LABEL_34:
            v20 = FillPinRetryContextUiData(a1, (struct _EAPTLS_PACKET *)v8, ReplyMessage, v10);
            ReplyMessage = v20;
            if ( !v20 )
            {
              ReplyMessage = 0;
              goto LABEL_39;
            }
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              goto LABEL_140;
            v22 = 310;
LABEL_37:
            WPP_SF_d(*((_QWORD *)v21 + 2), v22, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v20);
            goto LABEL_140;
          }
          v19 = 308;
        }
        else
        {
          if ( v17 != 869 )
            goto LABEL_39;
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_34;
          v19 = 309;
        }
        WPP_SF_(*((_QWORD *)v18 + 2), v19, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
        goto LABEL_34;
      }
      if ( (*((_DWORD *)a1 + 1) & 0x44000) == 0x40000 )
      {
        v23 = (char *)LocalAlloc(0x40u, 0x28u);
        v24 = (HANDLE *)v23;
        if ( v23 )
        {
          *(_QWORD *)v23 = *((_QWORD *)a1 + 1);
          *((_QWORD *)v23 + 1) = *((_QWORD *)a1 + 71);
          *((_QWORD *)v23 + 2) = *((_QWORD *)a1 + 68);
          *(_OWORD *)(v23 + 24) = *(_OWORD *)((char *)a1 + 780);
          Thread = CreateThread(0, 0, SaveCertCredsThread, v23, 0, 0);
          if ( Thread )
          {
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 313, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
            CWorkerThreadState::SetThreadHandle(v27, Thread);
          }
          else
          {
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            {
              LastError = GetLastError();
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                312,
                &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
                LastError);
            }
            if ( *v24 != (HANDLE)-1LL )
              CloseHandle(*v24);
            LocalFree(v24);
          }
          v14 = v40;
        }
        else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 311, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
        }
        v7 = v41;
      }
    }
LABEL_55:
    v28 = *((_DWORD *)a1 + 179);
    *((_DWORD *)a1 + 178) = v28;
    if ( v28 == *((_DWORD *)a1 + 176) )
    {
      *((_DWORD *)a1 + 176) = 0;
      *((_QWORD *)a1 + 89) = 0;
    }
  }
  if ( *(_DWORD *)a1 && *(_DWORD *)a1 != 2 && *(_DWORD *)a1 != 3 )
  {
    if ( *(_DWORD *)a1 != 4 )
    {
      if ( *(_DWORD *)a1 == 7 )
      {
        if ( v11 && v11->fDataReceivedFromInteractiveUI )
        {
          v29 = (void *)*((_QWORD *)a1 + 93);
          if ( v29 )
          {
            LocalFree(v29);
            *((_QWORD *)a1 + 93) = 0;
          }
          if ( v11->dwSizeOfDataFromInteractiveUI != 1 || *v11->pDataFromInteractiveUI == 7 )
          {
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 316, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
            *((_DWORD *)a1 + 1) &= 0xFFFFFFE7;
            *((_DWORD *)a1 + 172) = 0;
            v40 = 778;
            *((_DWORD *)a1 + 170) = 0;
            v31 = AlertFromError(&v40, 1);
            MakeAlert(a1, v31, 0, v32);
            v30 = v40;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 317, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
            *((_DWORD *)a1 + 1) |= 8u;
            v30 = 0;
          }
          *(_DWORD *)a1 = 4;
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 318, v13, (unsigned int)"RecdFinished", v30);
          *((_BYTE *)a1 + 721) = *((_BYTE *)a1 + 752);
          *((_DWORD *)a1 + 181) = v30;
          *((_BYTE *)a1 + 720) = 2;
          ReplyMessage = BuildPacket(v7, a4, a1);
          v33 = 0;
          if ( !ReplyMessage )
            v33 = 4;
          goto LABEL_118;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            325,
            &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
            *(unsigned int *)a1);
        ReplyMessage = 722;
      }
LABEL_117:
      v33 = 0;
LABEL_118:
      v10->Action = v33;
      goto LABEL_140;
    }
    if ( !v8 )
    {
      if ( v11 && v11->fSuccessPacketReceived )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 319, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
        v40 = 0;
        IsTLSSessionReconnect(a1, (int *)&v40);
        goto LABEL_114;
      }
LABEL_39:
      v10->Action = EAPACTION_NoAction;
      goto LABEL_140;
    }
    Code = v8->Code;
    if ( Code == 1 || v8->Code == 2 || (unsigned int)v8->Code - 3 > 1 )
    {
      if ( (*((_DWORD *)a1 + 1) & 0x4000) == 0 )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            324,
            (unsigned int)&g_szEapTlsState,
            Code,
            (__int64)(&g_szEapTlsState)[*(int *)a1]);
        goto LABEL_22;
      }
      if ( (_BYTE)Code != 1 )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            323,
            (unsigned int)&g_szEapTlsState,
            Code,
            (__int64)(&g_szEapTlsState)[*(int *)a1]);
        goto LABEL_117;
      }
LABEL_114:
      RespondToResult(a1, v10);
      goto LABEL_140;
    }
    if ( v8->Id != *((_BYTE *)a1 + 721) )
    {
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
LABEL_99:
        if ( (*((_DWORD *)a1 + 1) & 0x10000) == 0 && v8->Code == 4 && !*((_DWORD *)a1 + 181) )
          *((_DWORD *)a1 + 181) = -2143158011;
        if ( (*((_DWORD *)a1 + 1) & 0x4000) != 0 || (v20 = RasEapExportPeerId(a1), (ReplyMessage = v20) == 0) )
        {
          if ( !*((_DWORD *)a1 + 192) )
          {
            if ( v8->Code == 3 )
            {
              WriteTlsTraceLoggingEvent(a1, 3u, 1);
              WriteTlsAuthSuccessEvent(a1);
            }
            else
            {
              WriteTlsTraceLoggingEvent(a1, v8->Code, 0);
              WriteTlsAuthFailEvent(a1, *((_DWORD *)a1 + 181));
            }
          }
          goto LABEL_114;
        }
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_140;
        v22 = 322;
        goto LABEL_37;
      }
      WPP_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        320,
        &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
        v8->Id,
        *((unsigned __int8 *)a1 + 721));
    }
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v35 = "success";
      if ( v8->Code != 3 )
        v35 = "failure";
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 321, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v35);
    }
    goto LABEL_99;
  }
  if ( !v8 )
    goto LABEL_39;
  if ( v8->Code != 1 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        315,
        (unsigned int)&g_szEapTlsState,
        v8->Code,
        (__int64)(&g_szEapTlsState)[*(int *)a1]);
    v10->Action = EAPACTION_NoAction;
    ReplyMessage = 722;
    goto LABEL_140;
  }
  if ( !*((_DWORD *)a1 + 176) )
  {
LABEL_132:
    ReplyMessage = MakeReplyMessage(a1, (struct _EAPTLS_PACKET *)v8);
    if ( !ReplyMessage )
    {
      if ( *(_DWORD *)a1 == 7 )
      {
        v10->Action = EAPACTION_NoAction;
        v10->fInvokeInteractiveUI = 1;
        v10->dwSizeOfUIContextData = *(_DWORD *)(*((_QWORD *)a1 + 93) + 4LL);
        v10->pUIContextData = (PBYTE)*((_QWORD *)a1 + 93);
        *((_BYTE *)a1 + 752) = v8->Id;
        goto LABEL_140;
      }
      *((_BYTE *)a1 + 721) = v8->Id;
      *((_BYTE *)a1 + 720) = 2;
      ReplyMessage = BuildPacket(v7, a4, a1);
      v16 = 4;
      if ( ReplyMessage )
        v16 = 0;
      goto LABEL_139;
    }
    if ( *((_DWORD *)a1 + 181) )
    {
      *((_DWORD *)a1 + 1) &= ~8u;
      v10->Action = EAPACTION_Done;
      v10->dwAuthResultCode = *((_DWORD *)a1 + 181);
      goto LABEL_140;
    }
LABEL_22:
    v10->Action = EAPACTION_NoAction;
    goto LABEL_140;
  }
  if ( (unsigned __int16)EapConvertWireToHostFormat16(v8->Length) != 6 )
  {
    *((_DWORD *)a1 + 176) = 0;
    *((_QWORD *)a1 + 89) = 0;
    goto LABEL_132;
  }
  *((_BYTE *)a1 + 721) = v8->Id;
  *((_BYTE *)a1 + 720) = 2;
  ReplyMessage = BuildPacket(v7, a4, a1);
  v36 = 0;
  if ( !ReplyMessage )
    v36 = 4;
  v10->Action = v36;
LABEL_140:
  if ( v14 == 1 )
    LocalFree(v8);
  v37 = *((_QWORD *)a1 + 68);
  v38 = *(_DWORD *)(v37 + 8);
  if ( (v38 & 0x100) != 0 )
  {
    if ( v10->fSaveConnectionData )
    {
      *(_DWORD *)(v37 + 8) = v38 & 0xFFFFFFFE;
      *(_DWORD *)(*((_QWORD *)a1 + 68) + 8LL) &= ~0x10u;
      *(_DWORD *)(*((_QWORD *)a1 + 68) + 8LL) &= ~0x100u;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 326, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
    }
  }
  return ReplyMessage;
}

```

## disassembly

```asm
0x180052198  mov     [rsp+arg_8], rbx
0x18005219d  mov     [rsp+arg_10], r8
0x1800521a2  push    rbp
0x1800521a3  push    rsi
0x1800521a4  push    rdi
0x1800521a5  push    r12
0x1800521a7  push    r13
0x1800521a9  push    r14
0x1800521ab  push    r15
0x1800521ad  sub     rsp, 30h
0x1800521b1  mov     r13d, r9d
0x1800521b4  mov     [rsp+68h+arg_0], 0
0x1800521bc  mov     r15, r8
0x1800521bf  mov     r14, rdx
0x1800521c2  mov     rbx, rcx
0x1800521c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800521cc  lea     rax, WPP_GLOBAL_Control
0x1800521d3  cmp     rcx, rax
0x1800521d6  jz      short loc_1800521EB
0x1800521d8  mov     eax, [rbx+4]
0x1800521db  mov     r9d, [rbx]
0x1800521de  mov     rcx, [rcx+10h]
0x1800521e2  mov     [rsp+68h+dwCreationFlags], eax
0x1800521e6  call    WPP_SF_dL
0x1800521eb  mov     rsi, [rsp+68h+arg_20]
0x1800521f3  lea     r8, [rsp+68h+arg_0]; int *
0x1800521f8  mov     rbp, [rsp+68h+arg_28]
0x180052200  mov     r9, rsi; struct _PPP_EAP_OUTPUT *
0x180052203  mov     rdx, rbp; struct _PPP_EAP_INPUT *
0x180052206  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x180052209  call    ?IsPinRetry@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_PPP_EAP_INPUT@@PEAHPEAU_PPP_EAP_OUTPUT@@@Z; IsPinRetry(_EAPTLS_CONTROL_BLOCK *,_PPP_EAP_INPUT *,int *,_PPP_EAP_OUTPUT *)
0x18005220e  mov     r12d, [rsp+68h+arg_0]
0x180052213  mov     edi, eax
0x180052215  mov     [rsp+68h+arg_0], r12d
0x18005221a  test    eax, eax
0x18005221c  jz      short loc_180052237
0x18005221e  test    rbp, rbp
0x180052221  jz      short loc_18005222D
0x180052223  cmp     dword ptr [rbp+44h], 0
0x180052227  jnz     loc_180052AE7
0x18005222d  xor     edi, edi
0x18005222f  mov     [rsi+4], edi
0x180052232  jmp     loc_180052AE7
0x180052237  cmp     r12d, 1
0x18005223b  jnz     short loc_18005224C
0x18005223d  mov     rcx, [rbx+2F8h]; Src
0x180052244  call    ?CopyEapPacket@@YAPEAU_PPP_EAP_PACKET@@PEAU1@@Z; CopyEapPacket(_PPP_EAP_PACKET *)
0x180052249  mov     r14, rax
0x18005224c  test    r14, r14
0x18005224f  jz      loc_180052583
0x180052255  cmp     byte ptr [r14], 1
0x180052259  jnz     loc_18005255A
0x18005225f  mov     al, [r14+1]
0x180052263  cmp     [rbx+2D1h], al
0x180052269  jnz     short loc_1800522CC
0x18005226b  cmp     dword ptr [rbx], 0
0x18005226e  jz      short loc_1800522CC
0x180052270  mov     r8, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x180052273  mov     byte ptr [rbx+2D0h], 2
0x18005227a  mov     edx, r13d; unsigned int
0x18005227d  mov     rcx, r15; struct _EAPTLS_PACKET *
0x180052280  call    ?BuildPacket@@YAKPEAU_EAPTLS_PACKET@@KPEAU_EAPTLS_CONTROL_BLOCK@@@Z; BuildPacket(_EAPTLS_PACKET *,ulong,_EAPTLS_CONTROL_BLOCK *)
0x180052285  mov     edi, eax
0x180052287  test    eax, eax
0x180052289  jz      short loc_180052292
0x18005228b  xor     ebp, ebp
0x18005228d  jmp     loc_180052AE4
0x180052292  mov     rcx, cs:WPP_GLOBAL_Control
0x180052299  lea     rax, WPP_GLOBAL_Control
0x1800522a0  cmp     rcx, rax
0x1800522a3  jz      short loc_1800522C2
0x1800522a5  movzx   r9d, byte ptr [rbx+2D1h]
0x1800522ad  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x1800522b4  mov     rcx, [rcx+10h]
0x1800522b8  mov     edx, 131h
0x1800522bd  call    WPP_SF_d
0x1800522c2  mov     ebp, 4
0x1800522c7  jmp     loc_180052AE4
0x1800522cc  test    byte ptr [r14+5], 20h
0x1800522d1  jnz     short loc_180052310
0x1800522d3  cmp     dword ptr [rbx], 0
0x1800522d6  jnz     loc_18005255A
0x1800522dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800522e3  lea     rbp, WPP_GLOBAL_Control
0x1800522ea  cmp     rcx, rbp
0x1800522ed  jz      short loc_180052304
0x1800522ef  mov     rcx, [rcx+10h]
0x1800522f3  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x1800522fa  mov     edx, 132h
0x1800522ff  call    WPP_SF_
0x180052304  mov     dword ptr [rsi+4], 0
0x18005230b  jmp     loc_180052AEE
0x180052310  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x180052313  call    ?EapTlsReset@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@@Z; EapTlsReset(_EAPTLS_CONTROL_BLOCK *)
0x180052318  mov     edi, eax
0x18005231a  test    eax, eax
0x18005231c  jz      loc_1800523FF
0x180052322  and     eax, 1FFF0000h
0x180052327  cmp     eax, 100000h
0x18005232c  jnz     short loc_18005235B
0x18005232e  mov     rcx, cs:WPP_GLOBAL_Control
0x180052335  lea     rbp, WPP_GLOBAL_Control
0x18005233c  cmp     rcx, rbp
0x18005233f  jz      short loc_1800523AD
0x180052341  mov     rcx, [rcx+10h]
0x180052345  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005234c  mov     edx, 133h
0x180052351  mov     r9d, edi
0x180052354  call    WPP_SF_d
0x180052359  jmp     short loc_1800523AD
0x18005235b  cmp     edi, 34Fh
0x180052361  jnz     short loc_18005237D
0x180052363  mov     rcx, cs:WPP_GLOBAL_Control
0x18005236a  lea     rbp, WPP_GLOBAL_Control
0x180052371  cmp     rcx, rbp
0x180052374  jz      short loc_1800523AD
0x180052376  mov     edx, 134h
0x18005237b  jmp     short loc_18005239D
0x18005237d  cmp     edi, 365h
0x180052383  jnz     short loc_1800523F3
0x180052385  mov     rcx, cs:WPP_GLOBAL_Control
0x18005238c  lea     rbp, WPP_GLOBAL_Control
0x180052393  cmp     rcx, rbp
0x180052396  jz      short loc_1800523AD
0x180052398  mov     edx, 135h
0x18005239d  mov     rcx, [rcx+10h]
0x1800523a1  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x1800523a8  call    WPP_SF_
0x1800523ad  mov     r9, rsi; struct _PPP_EAP_OUTPUT *
0x1800523b0  mov     r8d, edi; unsigned int
0x1800523b3  mov     rdx, r14; struct _EAPTLS_PACKET *
0x1800523b6  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x1800523b9  call    ?FillPinRetryContextUiData@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_EAPTLS_PACKET@@KPEAU_PPP_EAP_OUTPUT@@@Z; FillPinRetryContextUiData(_EAPTLS_CONTROL_BLOCK *,_EAPTLS_PACKET *,ulong,_PPP_EAP_OUTPUT *)
0x1800523be  mov     edi, eax
0x1800523c0  test    eax, eax
0x1800523c2  jz      short loc_1800523F1
0x1800523c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800523cb  cmp     rcx, rbp
0x1800523ce  jz      loc_180052AEE
0x1800523d4  mov     edx, 136h
0x1800523d9  mov     rcx, [rcx+10h]
0x1800523dd  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x1800523e4  mov     r9d, eax
0x1800523e7  call    WPP_SF_d
0x1800523ec  jmp     loc_180052AEE
0x1800523f1  xor     edi, edi
0x1800523f3  mov     dword ptr [rsi+4], 0
0x1800523fa  jmp     loc_180052AE7
0x1800523ff  mov     eax, [rbx+4]
0x180052402  and     eax, 44000h
0x180052407  cmp     eax, 40000h
0x18005240c  jnz     loc_18005255A
0x180052412  mov     edx, 28h ; '('; uBytes
0x180052417  lea     ecx, [rdx+18h]; uFlags
0x18005241a  call    cs:__imp_LocalAlloc
0x180052421  nop     dword ptr [rax+rax+00h]
0x180052426  mov     r15, rax
0x180052429  test    rax, rax
0x18005242c  jnz     short loc_18005245F
0x18005242e  mov     rcx, cs:WPP_GLOBAL_Control
0x180052435  lea     rax, WPP_GLOBAL_Control
0x18005243c  cmp     rcx, rax
0x18005243f  jz      loc_180052552
0x180052445  mov     rcx, [rcx+10h]
0x180052449  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180052450  mov     edx, 137h
0x180052455  call    WPP_SF_
0x18005245a  jmp     loc_180052552
0x18005245f  mov     rax, [rbx+8]
0x180052463  lea     r8, ?SaveCertCredsThread@@YAKPEAX@Z; lpStartAddress
0x18005246a  mov     [r15], rax
0x18005246d  mov     r9, r15; lpParameter
0x180052470  mov     rax, [rbx+238h]
0x180052477  xor     edx, edx; dwStackSize
0x180052479  mov     [r15+8], rax
0x18005247d  xor     ecx, ecx; lpThreadAttributes
0x18005247f  mov     rax, [rbx+220h]
0x180052486  mov     [r15+10h], rax
0x18005248a  movups  xmm0, xmmword ptr [rbx+30Ch]
0x180052491  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x18005249a  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x1800524a2  movdqu  xmmword ptr [r15+18h], xmm0
0x1800524a8  call    cs:__imp_CreateThread
0x1800524af  nop     dword ptr [rax+rax+00h]
0x1800524b4  mov     r12, rax
0x1800524b7  test    rax, rax
0x1800524ba  jnz     short loc_18005251D
0x1800524bc  lea     rax, WPP_GLOBAL_Control
0x1800524c3  cmp     cs:WPP_GLOBAL_Control, rax
0x1800524ca  jz      short loc_1800524F7
0x1800524cc  call    cs:__imp_GetLastError
0x1800524d3  nop     dword ptr [rax+rax+00h]
0x1800524d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800524df  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x1800524e6  mov     edx, 138h
0x1800524eb  mov     r9d, eax
0x1800524ee  mov     rcx, [rcx+10h]
0x1800524f2  call    WPP_SF_d
0x1800524f7  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x1800524fb  jz      short loc_18005250C
0x1800524fd  mov     rcx, [r15]; hObject
0x180052500  call    cs:__imp_CloseHandle
0x180052507  nop     dword ptr [rax+rax+00h]
0x18005250c  mov     rcx, r15; hMem
0x18005250f  call    cs:__imp_LocalFree
0x180052516  nop     dword ptr [rax+rax+00h]
0x18005251b  jmp     short loc_18005254D
0x18005251d  mov     rcx, cs:WPP_GLOBAL_Control
0x180052524  lea     rax, WPP_GLOBAL_Control
0x18005252b  cmp     rcx, rax
0x18005252e  jz      short loc_180052545
0x180052530  mov     rcx, [rcx+10h]
0x180052534  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005253b  mov     edx, 139h
0x180052540  call    WPP_SF_
0x180052545  mov     rdx, r12; void *
0x180052548  call    ?SetThreadHandle@CWorkerThreadState@@QEAAXPEAX@Z; CWorkerThreadState::SetThreadHandle(void *)
0x18005254d  mov     r12d, [rsp+68h+arg_0]
0x180052552  mov     r15, [rsp+68h+arg_10]
0x18005255a  mov     eax, [rbx+2CCh]
0x180052560  mov     [rbx+2C8h], eax
0x180052566  cmp     eax, [rbx+2C0h]
0x18005256c  jnz     short loc_180052583
0x18005256e  mov     dword ptr [rbx+2C0h], 0
0x180052578  mov     qword ptr [rbx+2C8h], 0
0x180052583  mov     ecx, [rbx]
0x180052585  test    ecx, ecx
0x180052587  jz      loc_180052986
0x18005258d  sub     ecx, 2
0x180052590  jz      loc_180052986
0x180052596  sub     ecx, 1
0x180052599  jz      loc_180052986
0x18005259f  sub     ecx, 1
0x1800525a2  jz      loc_18005273D
0x1800525a8  cmp     ecx, 3
0x1800525ab  jz      short loc_1800525E2
0x1800525ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800525b4  lea     rbp, WPP_GLOBAL_Control
0x1800525bb  cmp     rcx, rbp
0x1800525be  jz      short loc_1800525D8
0x1800525c0  mov     r9d, [rbx]
0x1800525c3  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x1800525ca  mov     rcx, [rcx+10h]
0x1800525ce  mov     edx, 145h
0x1800525d3  call    WPP_SF_d
0x1800525d8  mov     edi, 2D2h
0x1800525dd  jmp     loc_18005293F
0x1800525e2  test    rbp, rbp
0x1800525e5  jz      loc_180052731
0x1800525eb  cmp     dword ptr [rbp+44h], 0
0x1800525ef  jz      loc_180052731
0x1800525f5  mov     rcx, [rbx+2E8h]; hMem
0x1800525fc  test    rcx, rcx
0x1800525ff  jz      short loc_180052618
0x180052601  call    cs:__imp_LocalFree
0x180052608  nop     dword ptr [rax+rax+00h]
0x18005260d  mov     qword ptr [rbx+2E8h], 0
0x180052618  cmp     dword ptr [rbp+50h], 1
0x18005261c  jnz     short loc_180052657
0x18005261e  mov     rax, [rbp+48h]
0x180052622  cmp     byte ptr [rax], 7
0x180052625  jz      short loc_180052657
0x180052627  mov     rcx, cs:WPP_GLOBAL_Control
0x18005262e  lea     rax, WPP_GLOBAL_Control
0x180052635  cmp     rcx, rax
0x180052638  jz      short loc_18005264F
0x18005263a  mov     rcx, [rcx+10h]
0x18005263e  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180052645  mov     edx, 13Dh
0x18005264a  call    WPP_SF_
0x18005264f  or      dword ptr [rbx+4], 8
0x180052653  xor     edi, edi
0x180052655  jmp     short loc_1800526C2
0x180052657  mov     rcx, cs:WPP_GLOBAL_Control
0x18005265e  lea     rax, WPP_GLOBAL_Control
0x180052665  cmp     rcx, rax
0x180052668  jz      short loc_18005267F
0x18005266a  mov     rcx, [rcx+10h]
0x18005266e  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180052675  mov     edx, 13Ch
0x18005267a  call    WPP_SF_
0x18005267f  and     dword ptr [rbx+4], 0FFFFFFE7h
0x180052683  lea     rcx, [rsp+68h+arg_0]; unsigned int *
0x180052688  mov     r9d, 30Ah
0x18005268e  mov     dword ptr [rbx+2B0h], 0
0x180052698  mov     edx, 1; int
0x18005269d  mov     [rsp+68h+arg_0], r9d
0x1800526a2  mov     dword ptr [rbx+2A8h], 0
0x1800526ac  call    ?AlertFromError@@YAKPEAKH@Z; AlertFromError(ulong *,int)
0x1800526b1  xor     r8d, r8d; int
0x1800526b4  mov     edx, eax; unsigned int
0x1800526b6  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x1800526b9  call    ?MakeAlert@@YAXPEAU_EAPTLS_CONTROL_BLOCK@@KHK@Z; MakeAlert(_EAPTLS_CONTROL_BLOCK *,ulong,int,ulong)
0x1800526be  mov     edi, [rsp+68h+arg_0]
0x1800526c2  mov     ebp, 4
0x1800526c7  mov     [rbx], ebp
0x1800526c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800526d0  lea     rax, WPP_GLOBAL_Control
0x1800526d7  cmp     rcx, rax
0x1800526da  jz      short loc_1800526F5
  ... truncated ...
```
