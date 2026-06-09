# CBrowserFrame::FrameMessagePump(void)

- ea: `0x180044050`
- end: `0x180044712`
- name: `?FrameMessagePump@CBrowserFrame@@QEAAXXZ`
- size: `1730`
- prototype: `void __fastcall(CBrowserFrame *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801d7bbc`

## callees

- `0x18000b9e0`
- `0x180044050`
- `0x180044718`
- `0x180057560`
- `0x18006f940`
- `0x180087978`
- `0x1801b5820`
- `0x1801c9dcc`
- `0x1801ef2bc`
- `0x18022dbfc`
- `0x1802446e4`
- `0x1802830b0`
- `0x180385404`
- `0x1804e8008`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18004454a`
- `KERNEL32!GetTickCount64` at `0x18004454a`
- `KERNEL32!GetCurrentThreadId` at `0x18004410e`
- `KERNEL32!GetCurrentThreadId` at `0x18004464c`
- `KERNEL32!GetCurrentThreadId` at `0x1800446b5`
- `KERNEL32!GetCurrentThreadId` at `0x18004410e`
- `KERNEL32!GetCurrentThreadId` at `0x18004464c`
- `KERNEL32!GetCurrentThreadId` at `0x1800446b5`
- `USER32!IsWindow` at `0x18004421f`
- `USER32!IsWindow` at `0x18004421f`
- `USER32!TranslateMessage` at `0x1800442a5`
- `USER32!TranslateMessage` at `0x1800442e0`
- `USER32!TranslateMessage` at `0x1800442a5`
- `USER32!TranslateMessage` at `0x1800442e0`
- `USER32!DispatchMessageW` at `0x1800442af`
- `USER32!DispatchMessageW` at `0x1800442ea`
- `USER32!DispatchMessageW` at `0x1800442af`
- `USER32!DispatchMessageW` at `0x1800442ea`
- `USER32!WaitMessage` at `0x180044707`
- `USER32!WaitMessage` at `0x180044707`
- `USER32!PeekMessageW` at `0x18004438f`
- `USER32!PeekMessageW` at `0x18004438f`
- `USER32!GetMessageExtraInfo` at `0x180044462`
- `USER32!GetMessageExtraInfo` at `0x180044462`
- `USER32!IsWindowEnabled` at `0x180044362`
- `USER32!IsWindowEnabled` at `0x180044362`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800446cc`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800446cc`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180044229`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180044229`
- `IEUI!WaitMessageEx` at `0x180044196`
- `IEUI!WaitMessageEx` at `0x180044196`
- `IEUI!PeekMessageExW` at `0x180044100`
- `IEUI!PeekMessageExW` at `0x180044100`
- `msIso!__imp_?LCIEChangeComponentSharedFlagBit@@YAJK_NK@Z` at `0x18004453f`
- `msIso!__imp_?LCIEChangeComponentSharedFlagBit@@YAJK_NK@Z` at `0x18004453f`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180044281`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180044291`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180044281`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180044291`
- `msIso!__imp_?IsoDispatchMessageToArtifacts@@YAJPEAUtagMSG@@@Z` at `0x1800442c9`
- `msIso!__imp_?IsoDispatchMessageToArtifacts@@YAJPEAUtagMSG@@@Z` at `0x1800442c9`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x18004415d`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x18004415d`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x180044144`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x180044144`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x180044683`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x180044683`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x18004468e`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x18004468e`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x18004417b`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x1800442ba`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x18004463d`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x1800446a1`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x18004417b`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x1800442ba`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x18004463d`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x1800446a1`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180044093`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18004409c`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180044093`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18004409c`

## pseudocode

```c
void __fastcall CBrowserFrame::FrameMessagePump(CBrowserFrame *this)
{
  __int64 v3; // r8
  int *v4; // rax
  int v5; // ebx
  unsigned int AuthorityManager; // eax
  UINT message; // ecx
  char v8; // si
  HWND v9; // rcx
  UINT v10; // ecx
  __int64 v11; // rcx
  int MessageExtraInfo; // eax
  ULONGLONG TickCount64; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  tagINPUT_MESSAGE_SOURCE v16; // rbx
  tagINPUT_MESSAGE_SOURCE v17; // [rsp+30h] [rbp-59h] BYREF
  struct _IsoUntrustedComponent *v18; // [rsp+38h] [rbp-51h] BYREF
  MSG Msg; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v20[16]; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v21[16]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v22[16]; // [rsp+90h] [rbp+7h] BYREF
  _BYTE v23[16]; // [rsp+A0h] [rbp+17h] BYREF

  if ( *((_DWORD *)this + 134) )
  {
    v11 = *((_QWORD *)this + 35);
    if ( v11 )
      CTabWindowManager::CloseAllTabs((CTabWindowManager *)(v11 + 8));
  }
  *(GUID *)GlobalThreadState() = GUID_NULL;
  *((_BYTE *)GlobalThreadState() + 16) = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      memset(&Msg, 0, sizeof(Msg));
      if ( !(*((_DWORD *)this + 66) ? PeekMessageExW(&Msg, 0, 0, 0, 1) : PeekMessageW(&Msg, 0, 0, 0, 1u)) )
        break;
      message = Msg.message;
      switch ( Msg.message )
      {
        case 0x85BEu:
          Msg.message = 256;
          v8 = 1;
LABEL_54:
          switch ( Msg.wParam )
          {
            case 0xDuLL:
              if ( (Microsoft_IEFRAMEEnableBits & 1) == 0 )
                goto LABEL_24;
              McGenEventWrite_EventWriteTransfer(BERP_IEFRAME2_Context, BROWSERTHREADPROC_RETURN_INFO, v3, 1, v20);
              break;
            case 8uLL:
              if ( (Microsoft_IEFRAMEEnableBits & 1) == 0 )
                goto LABEL_24;
              McGenEventWrite_EventWriteTransfer(BERP_IEFRAME2_Context, BACKNAVIAGATION_REQUESTED_INFO, v3, 1, v21);
              break;
            case 0x22uLL:
              if ( (Microsoft_IEFRAMEEnableBits & 1) == 0 )
                goto LABEL_24;
              McGenEventWrite_EventWriteTransfer(BERP_IEFRAME2_Context, BROWSERTHREADPROC_NEXT_INFO, v3, 1, v22);
              break;
            default:
              if ( Msg.wParam != 33 || (Microsoft_IEFRAMEEnableBits & 1) == 0 )
                goto LABEL_24;
              McGenEventWrite_EventWriteTransfer(BERP_IEFRAME2_Context, BROWSERTHREADPROC_PRIOR_INFO, v3, 1, v23);
              break;
          }
          goto LABEL_45;
        case 0x85BFu:
          Msg.message = 257;
          v8 = 1;
          goto LABEL_24;
        case 0x85C0u:
          Msg.message = 260;
          v8 = 1;
          goto LABEL_24;
        case 0x85C1u:
          Msg.message = 261;
          v8 = 1;
          goto LABEL_24;
      }
      v8 = 0;
      if ( Msg.message - 512 <= 0xE )
      {
        *((_BYTE *)this + 977) = 0;
        v17 = 0;
        if ( (unsigned int)IE_GetCurrentInputMessageSource(&v17) )
        {
          message = Msg.message;
          if ( v17.deviceType == IMDT_TOUCH )
            *((_BYTE *)this + 977) = 1;
        }
        else
        {
          MessageExtraInfo = GetMessageExtraInfo();
          message = Msg.message;
          *((_BYTE *)this + 977) = (MessageExtraInfo & 0xFF515780) == 4283520896LL;
        }
      }
      if ( message == 256 )
        goto LABEL_54;
      if ( message - 513 <= 2 )
      {
        if ( (Microsoft_IEFRAMEEnableBits & 1) == 0 )
          goto LABEL_23;
        McTemplateU0q_EventWriteTransfer(BERP_IEFRAME2_Context, LEFTBUTTONACTION_INFO, message);
      }
      else
      {
        if ( message != 22 )
          goto LABEL_23;
        LCIEChangeComponentSharedFlagBit(*((_DWORD *)this + 171), 1, 4u);
      }
LABEL_45:
      message = Msg.message;
LABEL_23:
      if ( message == 1155 )
        return;
LABEL_24:
      v9 = (HWND)*((_QWORD *)this + 1);
      if ( !v9 || !IsWindow(v9) )
        goto LABEL_32;
      if ( !IsDualEngineProcess() )
        goto LABEL_76;
      v10 = Msg.message;
      if ( Msg.message - 512 <= 0xE || Msg.message - 256 <= 9 )
      {
        TickCount64 = GetTickCount64();
        if ( *((_QWORD *)this + 155) + 1000LL < TickCount64 )
        {
          *((_QWORD *)this + 155) = TickCount64;
          CBrowserFrame::DualEngineOnInputAttempted(this);
        }
LABEL_76:
        v10 = Msg.message;
      }
      if ( (v10 == 16 || v10 == 1130) && (HWND)*((_QWORD *)this + 1) == Msg.hwnd )
      {
        if ( !IsWindowEnabled(*((HWND *)this + 1)) )
        {
          v10 = Msg.message;
          goto LABEL_31;
        }
        if ( Msg.message == 1130 )
        {
          v14 = *((_QWORD *)this + 35);
          if ( v14 )
            *(_BYTE *)(v14 + 408) = 1;
        }
        CBrowserFrame::_OnClose(this, 1);
      }
      else
      {
LABEL_31:
        if ( v10 - 256 > 9 )
          goto LABEL_32;
        if ( v10 == 260 )
        {
          v15 = *((_QWORD *)this + 35);
          v17 = 0;
          if ( v15 )
          {
            if ( (int)CTabWindowManager::GetActiveTab((CTabWindowManager *)(v15 + 8), (struct ITabWindow2 **)&v17) >= 0 )
            {
              v16 = v17;
              v18 = 0;
              if ( (*(int (__fastcall **)(tagINPUT_MESSAGE_SOURCE, struct _IsoUntrustedComponent **))(**(_QWORD **)&v17 + 208LL))(
                     v17,
                     &v18) >= 0
                && !v18 )
              {
                (*(void (__fastcall **)(tagINPUT_MESSAGE_SOURCE, __int64, _QWORD))(**(_QWORD **)&v16 + 128LL))(
                  v16,
                  1,
                  0);
              }
            }
          }
          ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v17);
        }
        if ( v8
          || (*(unsigned int (__fastcall **)(char *, MSG *))(*((_QWORD *)this + 2) + 40LL))((char *)this + 16, &Msg) )
        {
LABEL_32:
          if ( Msg.message != (unsigned int)IsoGetWindowsMessageNumber(2)
            && Msg.message != (unsigned int)IsoGetWindowsMessageNumber(3) )
          {
            if ( !v8 )
              TranslateMessage(&Msg);
            goto LABEL_36;
          }
          if ( IsoDispatchMessageToArtifacts(&Msg) )
          {
            if ( !v8 )
              TranslateMessage(&Msg);
LABEL_36:
            DispatchMessageW(&Msg);
          }
        }
      }
    }
    v4 = GetCurrentThreadId() == g_tidParking ? ProcessGetRefCountAddress() : (int *)((char *)this + 244);
    if ( !*v4 )
      break;
    if ( *((_DWORD *)this + 130)
      && *ProcessGetRefCountAddress() == 1
      && GetCurrentThreadId() == g_tidParking
      && !*((_DWORD *)this + 172) )
    {
      PostWSNotifyCleanupMsg();
      CDownloadManager::PostDLMNotifyFrameExitMsg();
      *((_DWORD *)this + 172) = 1;
      IsoReferenceDefaultScope(0, 0);
      IsoReleaseDefaultScope(1u);
    }
    v5 = 0;
    v18 = 0;
    AuthorityManager = IsoGetAuthorityManager();
    if ( (int)IsoGetTrustSplitComponent(AuthorityManager, 0, 0, 0, &v18) >= 0 )
      v5 = *((_DWORD *)v18 + 27);
    if ( !g_cProcessIESessions
      && !v5
      && *ProcessGetRefCountAddress() < dword_18065E0F4
      && GetCurrentThreadId() == g_tidParking )
    {
      if ( (unsigned __int8)IEConfiguration_GetBool(268435483) )
      {
        v17.deviceType = IMDT_UNAVAILABLE;
        GetBOOL((__int64 *)SettingStore::IEVALUE_LCIE_FrameShutdownDelay[0], &v17);
        if ( v17.deviceType == IMDT_UNAVAILABLE )
        {
          LCIEDisableFrameMergability();
          CBrowserFrame::s_PurgeStalledShutdownProcesses();
        }
      }
    }
    dword_18065E0F4 = *ProcessGetRefCountAddress();
    if ( *((_DWORD *)this + 66) )
      WaitMessageEx();
    else
      WaitMessage();
  }
}

```

## disassembly

```asm
0x180044050  mov     [rsp-8+arg_18], rdi
0x180044055  push    rbp
0x180044056  push    r14
0x180044058  push    r15
0x18004405a  lea     rbp, [rsp-47h]
0x18004405f  sub     rsp, 0D0h
0x180044066  mov     rax, cs:__security_cookie
0x18004406d  xor     rax, rsp
0x180044070  mov     [rbp+57h+var_30], rax
0x180044074  cmp     dword ptr [rcx+218h], 0
0x18004407b  mov     rdi, rcx
0x18004407e  movaps  [rsp+0E0h+var_20], xmm6
0x180044086  jnz     loc_18004439A
0x18004408c  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x180044093  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180044099  movups  xmmword ptr [rax], xmm6
0x18004409c  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800440a2  movaps  xmm6, [rsp+0E0h+var_20]
0x1800440aa  xor     r14d, r14d
0x1800440ad  mov     [rsp+0E0h+arg_8], rbx
0x1800440b5  mov     r15d, 0FF515780h
0x1800440bb  mov     [rsp+0E0h+arg_10], rsi
0x1800440c3  mov     byte ptr [rax+10h], 0
0x1800440c7  nop     word ptr [rax+rax+00000000h]
0x1800440d0  xorps   xmm0, xmm0
0x1800440d3  mov     [rsp+0E0h+wRemoveMsg], 1; wRemoveMsg
0x1800440db  xor     r9d, r9d; wMsgFilterMax
0x1800440de  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800440e2  xor     r8d, r8d; wMsgFilterMin
0x1800440e5  xor     edx, edx; hWnd
0x1800440e7  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x1800440eb  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x1800440ef  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x1800440f3  cmp     [rdi+108h], r14d
0x1800440fa  jz      loc_18004438F
0x180044100  call    cs:__imp_PeekMessageExW
0x180044106  test    eax, eax
0x180044108  jnz     loc_1800441A1
0x18004410e  call    cs:__imp_GetCurrentThreadId
0x180044114  cmp     eax, cs:g_tidParking
0x18004411a  jz      loc_1800442BA
0x180044120  lea     rax, [rdi+0F4h]
0x180044127  cmp     [rax], r14d
0x18004412a  jz      loc_1800442F5
0x180044130  cmp     [rdi+208h], r14d
0x180044137  jnz     loc_18004463D
0x18004413d  mov     ebx, r14d
0x180044140  mov     [rbp+57h+var_A8], r14
0x180044144  call    cs:__imp_?IsoGetAuthorityManager@@YAKXZ; IsoGetAuthorityManager(void)
0x18004414a  xor     r9d, r9d
0x18004414d  xor     r8d, r8d
0x180044150  mov     ecx, eax
0x180044152  xor     edx, edx
0x180044154  lea     rax, [rbp+57h+var_A8]
0x180044158  mov     qword ptr [rsp+0E0h+wRemoveMsg], rax
0x18004415d  call    cs:__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z; IsoGetTrustSplitComponent(ulong,ulong,_IsoComponent * *,ulong *,_IsoUntrustedComponent * *)
0x180044163  test    eax, eax
0x180044165  js      short loc_18004416E
0x180044167  mov     rax, [rbp+57h+var_A8]
0x18004416b  mov     ebx, [rax+6Ch]
0x18004416e  cmp     cs:?g_cProcessIESessions@@3KA, r14d; ulong g_cProcessIESessions
0x180044175  jz      loc_180044699
0x18004417b  call    cs:__imp_?ProcessGetRefCountAddress@@YAPEAJXZ; ProcessGetRefCountAddress(void)
0x180044181  mov     ecx, [rax]
0x180044183  mov     cs:dword_18065E0F4, ecx
0x180044189  cmp     [rdi+108h], r14d
0x180044190  jz      loc_180044707
0x180044196  call    cs:__imp_WaitMessageEx
0x18004419c  jmp     loc_1800440D0
0x1800441a1  mov     ecx, [rbp+57h+Msg.message]
0x1800441a4  cmp     ecx, 85BEh
0x1800441aa  jz      loc_1800443B8
0x1800441b0  cmp     ecx, 85BFh
0x1800441b6  jz      loc_180044404
0x1800441bc  cmp     ecx, 85C0h
0x1800441c2  jz      loc_180044413
0x1800441c8  cmp     ecx, 85C1h
0x1800441ce  jz      loc_180044422
0x1800441d4  xor     sil, sil
0x1800441d7  lea     eax, [rcx-200h]
0x1800441dd  cmp     eax, 0Eh
0x1800441e0  jbe     loc_180044431
0x1800441e6  cmp     ecx, 100h
0x1800441ec  jz      loc_1800443C2
0x1800441f2  lea     eax, [rcx-201h]
0x1800441f8  cmp     eax, 2
0x1800441fb  jbe     loc_180044326
0x180044201  cmp     ecx, 16h
0x180044204  jz      loc_180044531
0x18004420a  cmp     ecx, 483h
0x180044210  jz      loc_1800442F5
0x180044216  mov     rcx, [rdi+8]; hWnd
0x18004421a  test    rcx, rcx
0x18004421d  jz      short loc_18004427C
0x18004421f  call    cs:__imp_IsWindow
0x180044225  test    eax, eax
0x180044227  jz      short loc_18004427C
0x180044229  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18004422f  test    al, al
0x180044231  jz      loc_180044572
0x180044237  mov     ecx, [rbp+57h+Msg.message]
0x18004423a  lea     eax, [rcx-200h]
0x180044240  cmp     eax, 0Eh
0x180044243  jbe     loc_18004454A
0x180044249  lea     eax, [rcx-100h]
0x18004424f  cmp     eax, 9
0x180044252  jbe     loc_18004454A
0x180044258  cmp     ecx, 10h
0x18004425b  jz      loc_180044351
0x180044261  cmp     ecx, 46Ah
0x180044267  jz      loc_180044351
0x18004426d  lea     eax, [rcx-100h]
0x180044273  cmp     eax, 9
0x180044276  jbe     loc_18004459E
0x18004427c  mov     ecx, 2
0x180044281  call    cs:__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z; IsoGetWindowsMessageNumber(_IsoMsgWmNumbers)
0x180044287  cmp     [rbp+57h+Msg.message], eax
0x18004428a  jz      short loc_1800442C5
0x18004428c  mov     ecx, 3
0x180044291  call    cs:__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z; IsoGetWindowsMessageNumber(_IsoMsgWmNumbers)
0x180044297  cmp     [rbp+57h+Msg.message], eax
0x18004429a  jz      short loc_1800442C5
0x18004429c  test    sil, sil
0x18004429f  jnz     short loc_1800442AB
0x1800442a1  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800442a5  call    cs:__imp_TranslateMessage
0x1800442ab  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800442af  call    cs:__imp_DispatchMessageW
0x1800442b5  jmp     loc_1800440D0
0x1800442ba  call    cs:__imp_?ProcessGetRefCountAddress@@YAPEAJXZ; ProcessGetRefCountAddress(void)
0x1800442c0  jmp     loc_180044127
0x1800442c5  lea     rcx, [rbp+57h+Msg]
0x1800442c9  call    cs:__imp_?IsoDispatchMessageToArtifacts@@YAJPEAUtagMSG@@@Z; IsoDispatchMessageToArtifacts(tagMSG *)
0x1800442cf  test    eax, eax
0x1800442d1  jz      loc_1800440D0
0x1800442d7  test    sil, sil
0x1800442da  jnz     short loc_1800442E6
0x1800442dc  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800442e0  call    cs:__imp_TranslateMessage
0x1800442e6  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800442ea  call    cs:__imp_DispatchMessageW
0x1800442f0  jmp     loc_1800440D0
0x1800442f5  mov     rsi, [rsp+0E0h+arg_10]
0x1800442fd  mov     rbx, [rsp+0E0h+arg_8]
0x180044305  mov     rcx, [rbp+57h+var_30]
0x180044309  xor     rcx, rsp; StackCookie
0x18004430c  call    __security_check_cookie
0x180044311  mov     rdi, [rsp+0E0h+arg_18]
0x180044319  add     rsp, 0D0h
0x180044320  pop     r15
0x180044322  pop     r14
0x180044324  pop     rbp
0x180044325  retn
0x180044326  test    byte ptr cs:Microsoft_IEFRAMEEnableBits, 1
0x18004432d  jz      loc_18004420A
0x180044333  mov     r8d, ecx
0x180044336  lea     rdx, LEFTBUTTONACTION_INFO
0x18004433d  lea     rcx, BERP_IEFRAME2_Context
0x180044344  call    McTemplateU0q_EventWriteTransfer
0x180044349  mov     ecx, [rbp+57h+Msg.message]
0x18004434c  jmp     loc_18004420A
0x180044351  mov     rax, [rdi+8]
0x180044355  cmp     rax, [rbp+57h+Msg.hwnd]
0x180044359  jnz     loc_18004426D
0x18004435f  mov     rcx, rax; hWnd
0x180044362  call    cs:__imp_IsWindowEnabled
0x180044368  test    eax, eax
0x18004436a  jz      loc_180044596
0x180044370  cmp     [rbp+57h+Msg.message], 46Ah
0x180044377  jz      loc_18004457A
0x18004437d  mov     edx, 1; int
0x180044382  mov     rcx, rdi; this
0x180044385  call    ?_OnClose@CBrowserFrame@@IEAAXH@Z; CBrowserFrame::_OnClose(int)
0x18004438a  jmp     loc_1800440D0
0x18004438f  call    cs:__imp_PeekMessageW
0x180044395  jmp     loc_180044106
0x18004439a  mov     rcx, [rcx+118h]
0x1800443a1  test    rcx, rcx
0x1800443a4  jz      loc_18004408C
0x1800443aa  add     rcx, 8; this
0x1800443ae  call    ?CloseAllTabs@CTabWindowManager@@UEAAJXZ; CTabWindowManager::CloseAllTabs(void)
0x1800443b3  jmp     loc_18004408C
0x1800443b8  mov     [rbp+57h+Msg.message], 100h
0x1800443bf  mov     sil, 1
0x1800443c2  mov     rax, [rbp+57h+Msg.wParam]
0x1800443c6  cmp     rax, 0Dh
0x1800443ca  jnz     loc_18004447F
0x1800443d0  test    byte ptr cs:Microsoft_IEFRAMEEnableBits, 1
0x1800443d7  jz      loc_180044216
0x1800443dd  lea     rax, [rbp+57h+var_70]
0x1800443e1  mov     r9d, 1
0x1800443e7  lea     rdx, BROWSERTHREADPROC_RETURN_INFO
0x1800443ee  mov     qword ptr [rsp+0E0h+wRemoveMsg], rax
0x1800443f3  lea     rcx, BERP_IEFRAME2_Context
0x1800443fa  call    McGenEventWrite_EventWriteTransfer
0x1800443ff  jmp     loc_180044349
0x180044404  mov     [rbp+57h+Msg.message], 101h
0x18004440b  mov     sil, 1
0x18004440e  jmp     loc_180044216
0x180044413  mov     [rbp+57h+Msg.message], 104h
0x18004441a  mov     sil, 1
0x18004441d  jmp     loc_180044216
0x180044422  mov     [rbp+57h+Msg.message], 105h
0x180044429  mov     sil, 1
0x18004442c  jmp     loc_180044216
0x180044431  lea     rcx, [rbp+57h+var_B0]; struct tagINPUT_MESSAGE_SOURCE *
0x180044435  mov     [rdi+3D1h], sil
0x18004443c  mov     qword ptr [rbp+57h+var_B0.deviceType], r14
0x180044440  call    ?IE_GetCurrentInputMessageSource@@YAHPEAUtagINPUT_MESSAGE_SOURCE@@@Z; IE_GetCurrentInputMessageSource(tagINPUT_MESSAGE_SOURCE *)
0x180044445  test    eax, eax
0x180044447  jz      short loc_180044462
0x180044449  cmp     [rbp+57h+var_B0.deviceType], 4
0x18004444d  mov     ecx, [rbp+57h+Msg.message]
0x180044450  jnz     loc_1800441E6
0x180044456  mov     byte ptr [rdi+3D1h], 1
0x18004445d  jmp     loc_1800441E6
0x180044462  call    cs:__imp_GetMessageExtraInfo
0x180044468  mov     ecx, [rbp+57h+Msg.message]
0x18004446b  and     rax, r15
0x18004446e  cmp     rax, r15
0x180044471  setz    al
0x180044474  mov     [rdi+3D1h], al
0x18004447a  jmp     loc_1800441E6
0x18004447f  cmp     rax, 8
0x180044483  jnz     short loc_1800444B9
0x180044485  test    byte ptr cs:Microsoft_IEFRAMEEnableBits, 1
0x18004448c  jz      loc_180044216
0x180044492  lea     rax, [rbp+57h+var_60]
0x180044496  mov     r9d, 1
0x18004449c  lea     rdx, BACKNAVIAGATION_REQUESTED_INFO
0x1800444a3  mov     qword ptr [rsp+0E0h+wRemoveMsg], rax
0x1800444a8  lea     rcx, BERP_IEFRAME2_Context
0x1800444af  call    McGenEventWrite_EventWriteTransfer
0x1800444b4  jmp     loc_180044349
0x1800444b9  cmp     rax, 22h ; '"'
0x1800444bd  jnz     short loc_1800444F3
0x1800444bf  test    byte ptr cs:Microsoft_IEFRAMEEnableBits, 1
0x1800444c6  jz      loc_180044216
0x1800444cc  lea     rax, [rbp+57h+var_50]
0x1800444d0  mov     r9d, 1
0x1800444d6  lea     rdx, BROWSERTHREADPROC_NEXT_INFO
0x1800444dd  mov     qword ptr [rsp+0E0h+wRemoveMsg], rax
0x1800444e2  lea     rcx, BERP_IEFRAME2_Context
0x1800444e9  call    McGenEventWrite_EventWriteTransfer
0x1800444ee  jmp     loc_180044349
0x1800444f3  cmp     rax, 21h ; '!'
0x1800444f7  jnz     loc_180044216
0x1800444fd  test    byte ptr cs:Microsoft_IEFRAMEEnableBits, 1
0x180044504  jz      loc_180044216
0x18004450a  lea     rax, [rbp+57h+var_40]
0x18004450e  mov     r9d, 1
0x180044514  lea     rdx, BROWSERTHREADPROC_PRIOR_INFO
0x18004451b  mov     qword ptr [rsp+0E0h+wRemoveMsg], rax
0x180044520  lea     rcx, BERP_IEFRAME2_Context
0x180044527  call    McGenEventWrite_EventWriteTransfer
0x18004452c  jmp     loc_180044349
0x180044531  mov     ecx, [rdi+2ACh]
0x180044537  mov     r8d, 4
0x18004453d  mov     dl, 1
0x18004453f  call    cs:__imp_?LCIEChangeComponentSharedFlagBit@@YAJK_NK@Z; LCIEChangeComponentSharedFlagBit(ulong,bool,ulong)
0x180044545  jmp     loc_180044349
0x18004454a  call    cs:__imp_GetTickCount64
0x180044550  mov     rcx, [rdi+4D8h]
0x180044557  add     rcx, 3E8h
0x18004455e  cmp     rcx, rax
0x180044561  jnb     short loc_180044572
0x180044563  mov     rcx, rdi; this
0x180044566  mov     [rdi+4D8h], rax
0x18004456d  call    ?DualEngineOnInputAttempted@CBrowserFrame@@QEAAXXZ; CBrowserFrame::DualEngineOnInputAttempted(void)
0x180044572  mov     ecx, [rbp+57h+Msg.message]
0x180044575  jmp     loc_180044258
0x18004457a  mov     rax, [rdi+118h]
0x180044581  test    rax, rax
0x180044584  jz      loc_18004437D
0x18004458a  mov     byte ptr [rax+198h], 1
0x180044591  jmp     loc_18004437D
0x180044596  mov     ecx, [rbp+57h+Msg.message]
0x180044599  jmp     loc_18004426D
0x18004459e  cmp     ecx, 104h
0x1800445a4  jnz     short loc_180044612
0x1800445a6  mov     rcx, [rdi+118h]
0x1800445ad  mov     qword ptr [rbp+57h+var_B0.deviceType], r14
0x1800445b1  test    rcx, rcx
0x1800445b4  jz      short loc_180044609
0x1800445b6  add     rcx, 8; this
0x1800445ba  lea     rdx, [rbp+57h+var_B0]; struct ITabWindow2 **
0x1800445be  call    ?GetActiveTab@CTabWindowManager@@UEAAJPEAPEAUITabWindow2@@@Z; CTabWindowManager::GetActiveTab(ITabWindow2 * *)
0x1800445c3  test    eax, eax
0x1800445c5  js      short loc_180044609
0x1800445c7  mov     rbx, qword ptr [rbp+57h+var_B0.deviceType]
0x1800445cb  lea     rdx, [rbp+57h+var_A8]
0x1800445cf  mov     [rbp+57h+var_A8], r14
0x1800445d3  mov     rcx, rbx
0x1800445d6  mov     rax, [rbx]
0x1800445d9  mov     rax, [rax+0D0h]
0x1800445e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445e5  test    eax, eax
0x1800445e7  js      short loc_180044609
0x1800445e9  cmp     [rbp+57h+var_A8], r14
0x1800445ed  jnz     short loc_180044609
  ... truncated ...
```
