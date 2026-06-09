# EapTlsCMakeMessage(_EAPTLS_CONTROL_BLOCK *,_EAPTLS_PACKET *,_EAPTLS_PACKET *,ulong,_PPP_EAP_OUTPUT *,_PPP_EAP_INPUT *)

- ea: `0x18004f508`
- end: `0x18004feae`
- name: `?EapTlsCMakeMessage@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_EAPTLS_PACKET@@1KPEAU_PPP_EAP_OUTPUT@@PEAU_PPP_EAP_INPUT@@@Z`
- size: `2470`
- prototype: `unsigned int __fastcall(struct _EAPTLS_CONTROL_BLOCK *, struct _EAPTLS_PACKET *, struct _EAPTLS_PACKET *, unsigned int, struct _PPP_EAP_OUTPUT *, struct _PPP_EAP_INPUT *)`
- caller_count: `2`
- callee_count: `23`
- tags: ``

## callers

- `0x180008b28`
- `0x1800164a0`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18001c680`
- `0x18001e410`
- `0x18001f670`
- `0x18001f78c`
- `0x1800234e0`
- `0x180031048`
- `0x18004acb8`
- `0x18004c85c`
- `0x18004f508`
- `0x180050d30`
- `0x180051318`
- `0x1800533ec`
- `0x1800537e0`
- `0x180053a98`
- `0x180056908`
- `0x180058558`
- `0x180058708`
- `0x180058894`
- `0x18005a90c`
- `0x18005aa7c`
- `0x180064cb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f830`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f830`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18004f812`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18004f812`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f85e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f85e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f78a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f78a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f867`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f953`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fe3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f867`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f953`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fe3d`
- `eapputil!EapConvertWireToHostFormat16` at `0x18004fd37`
- `eapputil!EapConvertWireToHostFormat16` at `0x18004fd37`

## pseudocode

```c
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
              &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
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
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 306, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
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
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 307, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v17);
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
            WPP_SF_d(*((_QWORD *)v21 + 2), v22, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v20);
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
        WPP_SF_(*((_QWORD *)v18 + 2), v19, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
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
          Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)SaveCertCredsThread, v23, 0, 0);
          if ( Thread )
          {
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 313, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
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
                &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
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
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 311, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
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
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 316, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
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
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 317, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
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
            &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
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
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 319, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
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
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        320,
        &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
        v8->Id,
        *((unsigned __int8 *)a1 + 721));
    }
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v35 = "success";
      if ( v8->Code != 3 )
        v35 = "failure";
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 321, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v35);
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 326, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
    }
  }
  return ReplyMessage;
}

```

## disassembly

```asm
0x18004f508  mov     [rsp+arg_8], rbx
0x18004f50d  mov     [rsp+arg_10], r8
0x18004f512  push    rbp
0x18004f513  push    rsi
0x18004f514  push    rdi
0x18004f515  push    r12
0x18004f517  push    r13
0x18004f519  push    r14
0x18004f51b  push    r15
0x18004f51d  sub     rsp, 30h
0x18004f521  mov     r13d, r9d
0x18004f524  mov     [rsp+68h+arg_0], 0
0x18004f52c  mov     r15, r8
0x18004f52f  mov     r14, rdx
0x18004f532  mov     rbx, rcx
0x18004f535  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f53c  lea     rax, WPP_GLOBAL_Control
0x18004f543  cmp     rcx, rax
0x18004f546  jz      short loc_18004F55B
0x18004f548  mov     eax, [rbx+4]
0x18004f54b  mov     r9d, [rbx]
0x18004f54e  mov     rcx, [rcx+10h]
0x18004f552  mov     [rsp+68h+dwCreationFlags], eax
0x18004f556  call    WPP_SF_dL
0x18004f55b  mov     rsi, [rsp+68h+arg_20]
0x18004f563  lea     r8, [rsp+68h+arg_0]; int *
0x18004f568  mov     rbp, [rsp+68h+arg_28]
0x18004f570  mov     r9, rsi; struct _PPP_EAP_OUTPUT *
0x18004f573  mov     rdx, rbp; struct _PPP_EAP_INPUT *
0x18004f576  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x18004f579  call    ?IsPinRetry@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_PPP_EAP_INPUT@@PEAHPEAU_PPP_EAP_OUTPUT@@@Z; IsPinRetry(_EAPTLS_CONTROL_BLOCK *,_PPP_EAP_INPUT *,int *,_PPP_EAP_OUTPUT *)
0x18004f57e  mov     r12d, [rsp+68h+arg_0]
0x18004f583  mov     edi, eax
0x18004f585  mov     [rsp+68h+arg_0], r12d
0x18004f58a  test    eax, eax
0x18004f58c  jz      short loc_18004F5A7
0x18004f58e  test    rbp, rbp
0x18004f591  jz      short loc_18004F59D
0x18004f593  cmp     dword ptr [rbp+44h], 0
0x18004f597  jnz     loc_18004FE2D
0x18004f59d  xor     edi, edi
0x18004f59f  mov     [rsi+4], edi
0x18004f5a2  jmp     loc_18004FE2D
0x18004f5a7  cmp     r12d, 1
0x18004f5ab  jnz     short loc_18004F5BC
0x18004f5ad  mov     rcx, [rbx+2F8h]; Src
0x18004f5b4  call    ?CopyEapPacket@@YAPEAU_PPP_EAP_PACKET@@PEAU1@@Z; CopyEapPacket(_PPP_EAP_PACKET *)
0x18004f5b9  mov     r14, rax
0x18004f5bc  test    r14, r14
0x18004f5bf  jz      loc_18004F8D5
0x18004f5c5  cmp     byte ptr [r14], 1
0x18004f5c9  jnz     loc_18004F8AC
0x18004f5cf  mov     al, [r14+1]
0x18004f5d3  cmp     [rbx+2D1h], al
0x18004f5d9  jnz     short loc_18004F63C
0x18004f5db  cmp     dword ptr [rbx], 0
0x18004f5de  jz      short loc_18004F63C
0x18004f5e0  mov     r8, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x18004f5e3  mov     byte ptr [rbx+2D0h], 2
0x18004f5ea  mov     edx, r13d; unsigned int
0x18004f5ed  mov     rcx, r15; struct _EAPTLS_PACKET *
0x18004f5f0  call    ?BuildPacket@@YAKPEAU_EAPTLS_PACKET@@KPEAU_EAPTLS_CONTROL_BLOCK@@@Z; BuildPacket(_EAPTLS_PACKET *,ulong,_EAPTLS_CONTROL_BLOCK *)
0x18004f5f5  mov     edi, eax
0x18004f5f7  test    eax, eax
0x18004f5f9  jz      short loc_18004F602
0x18004f5fb  xor     ebp, ebp
0x18004f5fd  jmp     loc_18004FE2A
0x18004f602  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f609  lea     rax, WPP_GLOBAL_Control
0x18004f610  cmp     rcx, rax
0x18004f613  jz      short loc_18004F632
0x18004f615  movzx   r9d, byte ptr [rbx+2D1h]
0x18004f61d  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f624  mov     rcx, [rcx+10h]
0x18004f628  mov     edx, 131h
0x18004f62d  call    WPP_SF_d
0x18004f632  mov     ebp, 4
0x18004f637  jmp     loc_18004FE2A
0x18004f63c  test    byte ptr [r14+5], 20h
0x18004f641  jnz     short loc_18004F680
0x18004f643  cmp     dword ptr [rbx], 0
0x18004f646  jnz     loc_18004F8AC
0x18004f64c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f653  lea     rbp, WPP_GLOBAL_Control
0x18004f65a  cmp     rcx, rbp
0x18004f65d  jz      short loc_18004F674
0x18004f65f  mov     rcx, [rcx+10h]
0x18004f663  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f66a  mov     edx, 132h
0x18004f66f  call    WPP_SF_
0x18004f674  mov     dword ptr [rsi+4], 0
0x18004f67b  jmp     loc_18004FE34
0x18004f680  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x18004f683  call    ?EapTlsReset@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@@Z; EapTlsReset(_EAPTLS_CONTROL_BLOCK *)
0x18004f688  mov     edi, eax
0x18004f68a  test    eax, eax
0x18004f68c  jz      loc_18004F76F
0x18004f692  and     eax, 1FFF0000h
0x18004f697  cmp     eax, 100000h
0x18004f69c  jnz     short loc_18004F6CB
0x18004f69e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f6a5  lea     rbp, WPP_GLOBAL_Control
0x18004f6ac  cmp     rcx, rbp
0x18004f6af  jz      short loc_18004F71D
0x18004f6b1  mov     rcx, [rcx+10h]
0x18004f6b5  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f6bc  mov     edx, 133h
0x18004f6c1  mov     r9d, edi
0x18004f6c4  call    WPP_SF_d
0x18004f6c9  jmp     short loc_18004F71D
0x18004f6cb  cmp     edi, 34Fh
0x18004f6d1  jnz     short loc_18004F6ED
0x18004f6d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f6da  lea     rbp, WPP_GLOBAL_Control
0x18004f6e1  cmp     rcx, rbp
0x18004f6e4  jz      short loc_18004F71D
0x18004f6e6  mov     edx, 134h
0x18004f6eb  jmp     short loc_18004F70D
0x18004f6ed  cmp     edi, 365h
0x18004f6f3  jnz     short loc_18004F763
0x18004f6f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f6fc  lea     rbp, WPP_GLOBAL_Control
0x18004f703  cmp     rcx, rbp
0x18004f706  jz      short loc_18004F71D
0x18004f708  mov     edx, 135h
0x18004f70d  mov     rcx, [rcx+10h]
0x18004f711  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f718  call    WPP_SF_
0x18004f71d  mov     r9, rsi; struct _PPP_EAP_OUTPUT *
0x18004f720  mov     r8d, edi; unsigned int
0x18004f723  mov     rdx, r14; struct _EAPTLS_PACKET *
0x18004f726  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x18004f729  call    ?FillPinRetryContextUiData@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_EAPTLS_PACKET@@KPEAU_PPP_EAP_OUTPUT@@@Z; FillPinRetryContextUiData(_EAPTLS_CONTROL_BLOCK *,_EAPTLS_PACKET *,ulong,_PPP_EAP_OUTPUT *)
0x18004f72e  mov     edi, eax
0x18004f730  test    eax, eax
0x18004f732  jz      short loc_18004F761
0x18004f734  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f73b  cmp     rcx, rbp
0x18004f73e  jz      loc_18004FE34
0x18004f744  mov     edx, 136h
0x18004f749  mov     rcx, [rcx+10h]
0x18004f74d  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f754  mov     r9d, eax
0x18004f757  call    WPP_SF_d
0x18004f75c  jmp     loc_18004FE34
0x18004f761  xor     edi, edi
0x18004f763  mov     dword ptr [rsi+4], 0
0x18004f76a  jmp     loc_18004FE2D
0x18004f76f  mov     eax, [rbx+4]
0x18004f772  and     eax, 44000h
0x18004f777  cmp     eax, 40000h
0x18004f77c  jnz     loc_18004F8AC
0x18004f782  mov     edx, 28h ; '('; uBytes
0x18004f787  lea     ecx, [rdx+18h]; uFlags
0x18004f78a  call    cs:__imp_LocalAlloc
0x18004f790  mov     r15, rax
0x18004f793  test    rax, rax
0x18004f796  jnz     short loc_18004F7C9
0x18004f798  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f79f  lea     rax, WPP_GLOBAL_Control
0x18004f7a6  cmp     rcx, rax
0x18004f7a9  jz      loc_18004F8A4
0x18004f7af  mov     rcx, [rcx+10h]
0x18004f7b3  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f7ba  mov     edx, 137h
0x18004f7bf  call    WPP_SF_
0x18004f7c4  jmp     loc_18004F8A4
0x18004f7c9  mov     rax, [rbx+8]
0x18004f7cd  lea     r8, ?SaveCertCredsThread@@YAKPEAX@Z; lpStartAddress
0x18004f7d4  mov     [r15], rax
0x18004f7d7  mov     r9, r15; lpParameter
0x18004f7da  mov     rax, [rbx+238h]
0x18004f7e1  xor     edx, edx; dwStackSize
0x18004f7e3  mov     [r15+8], rax
0x18004f7e7  xor     ecx, ecx; lpThreadAttributes
0x18004f7e9  mov     rax, [rbx+220h]
0x18004f7f0  mov     [r15+10h], rax
0x18004f7f4  movups  xmm0, xmmword ptr [rbx+30Ch]
0x18004f7fb  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x18004f804  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18004f80c  movdqu  xmmword ptr [r15+18h], xmm0
0x18004f812  call    cs:__imp_CreateThread
0x18004f818  mov     r12, rax
0x18004f81b  test    rax, rax
0x18004f81e  jnz     short loc_18004F86F
0x18004f820  lea     rax, WPP_GLOBAL_Control
0x18004f827  cmp     cs:WPP_GLOBAL_Control, rax
0x18004f82e  jz      short loc_18004F855
0x18004f830  call    cs:__imp_GetLastError
0x18004f836  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f83d  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f844  mov     edx, 138h
0x18004f849  mov     r9d, eax
0x18004f84c  mov     rcx, [rcx+10h]
0x18004f850  call    WPP_SF_d
0x18004f855  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x18004f859  jz      short loc_18004F864
0x18004f85b  mov     rcx, [r15]; hObject
0x18004f85e  call    cs:__imp_CloseHandle
0x18004f864  mov     rcx, r15; hMem
0x18004f867  call    cs:__imp_LocalFree
0x18004f86d  jmp     short loc_18004F89F
0x18004f86f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f876  lea     rax, WPP_GLOBAL_Control
0x18004f87d  cmp     rcx, rax
0x18004f880  jz      short loc_18004F897
0x18004f882  mov     rcx, [rcx+10h]
0x18004f886  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f88d  mov     edx, 139h
0x18004f892  call    WPP_SF_
0x18004f897  mov     rdx, r12; void *
0x18004f89a  call    ?SetThreadHandle@CWorkerThreadState@@QEAAXPEAX@Z; CWorkerThreadState::SetThreadHandle(void *)
0x18004f89f  mov     r12d, [rsp+68h+arg_0]
0x18004f8a4  mov     r15, [rsp+68h+arg_10]
0x18004f8ac  mov     eax, [rbx+2CCh]
0x18004f8b2  mov     [rbx+2C8h], eax
0x18004f8b8  cmp     eax, [rbx+2C0h]
0x18004f8be  jnz     short loc_18004F8D5
0x18004f8c0  mov     dword ptr [rbx+2C0h], 0
0x18004f8ca  mov     qword ptr [rbx+2C8h], 0
0x18004f8d5  mov     ecx, [rbx]
0x18004f8d7  test    ecx, ecx
0x18004f8d9  jz      loc_18004FCD2
0x18004f8df  sub     ecx, 2
0x18004f8e2  jz      loc_18004FCD2
0x18004f8e8  sub     ecx, 1
0x18004f8eb  jz      loc_18004FCD2
0x18004f8f1  sub     ecx, 1
0x18004f8f4  jz      loc_18004FA89
0x18004f8fa  cmp     ecx, 3
0x18004f8fd  jz      short loc_18004F934
0x18004f8ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f906  lea     rbp, WPP_GLOBAL_Control
0x18004f90d  cmp     rcx, rbp
0x18004f910  jz      short loc_18004F92A
0x18004f912  mov     r9d, [rbx]
0x18004f915  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f91c  mov     rcx, [rcx+10h]
0x18004f920  mov     edx, 145h
0x18004f925  call    WPP_SF_d
0x18004f92a  mov     edi, 2D2h
0x18004f92f  jmp     loc_18004FC8B
0x18004f934  test    rbp, rbp
0x18004f937  jz      loc_18004FA7D
0x18004f93d  cmp     dword ptr [rbp+44h], 0
0x18004f941  jz      loc_18004FA7D
0x18004f947  mov     rcx, [rbx+2E8h]; hMem
0x18004f94e  test    rcx, rcx
0x18004f951  jz      short loc_18004F964
0x18004f953  call    cs:__imp_LocalFree
0x18004f959  mov     qword ptr [rbx+2E8h], 0
0x18004f964  cmp     dword ptr [rbp+50h], 1
0x18004f968  jnz     short loc_18004F9A3
0x18004f96a  mov     rax, [rbp+48h]
0x18004f96e  cmp     byte ptr [rax], 7
0x18004f971  jz      short loc_18004F9A3
0x18004f973  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f97a  lea     rax, WPP_GLOBAL_Control
0x18004f981  cmp     rcx, rax
0x18004f984  jz      short loc_18004F99B
0x18004f986  mov     rcx, [rcx+10h]
0x18004f98a  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f991  mov     edx, 13Dh
0x18004f996  call    WPP_SF_
0x18004f99b  or      dword ptr [rbx+4], 8
0x18004f99f  xor     edi, edi
0x18004f9a1  jmp     short loc_18004FA0E
0x18004f9a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f9aa  lea     rax, WPP_GLOBAL_Control
0x18004f9b1  cmp     rcx, rax
0x18004f9b4  jz      short loc_18004F9CB
0x18004f9b6  mov     rcx, [rcx+10h]
0x18004f9ba  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f9c1  mov     edx, 13Ch
0x18004f9c6  call    WPP_SF_
0x18004f9cb  and     dword ptr [rbx+4], 0FFFFFFE7h
0x18004f9cf  lea     rcx, [rsp+68h+arg_0]; unsigned int *
0x18004f9d4  mov     r9d, 30Ah
0x18004f9da  mov     dword ptr [rbx+2B0h], 0
0x18004f9e4  mov     edx, 1; int
0x18004f9e9  mov     [rsp+68h+arg_0], r9d
0x18004f9ee  mov     dword ptr [rbx+2A8h], 0
0x18004f9f8  call    ?AlertFromError@@YAKPEAKH@Z; AlertFromError(ulong *,int)
0x18004f9fd  xor     r8d, r8d; int
0x18004fa00  mov     edx, eax; unsigned int
0x18004fa02  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x18004fa05  call    ?MakeAlert@@YAXPEAU_EAPTLS_CONTROL_BLOCK@@KHK@Z; MakeAlert(_EAPTLS_CONTROL_BLOCK *,ulong,int,ulong)
0x18004fa0a  mov     edi, [rsp+68h+arg_0]
0x18004fa0e  mov     ebp, 4
0x18004fa13  mov     [rbx], ebp
0x18004fa15  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fa1c  lea     rax, WPP_GLOBAL_Control
0x18004fa23  cmp     rcx, rax
0x18004fa26  jz      short loc_18004FA41
0x18004fa28  mov     r9, cs:off_18007E300; "RecdFinished"
0x18004fa2f  mov     edx, 13Eh
0x18004fa34  mov     rcx, [rcx+10h]
0x18004fa38  mov     [rsp+68h+dwCreationFlags], edi
0x18004fa3c  call    WPP_SF_sD
0x18004fa41  mov     al, [rbx+2F0h]
  ... truncated ...
```
