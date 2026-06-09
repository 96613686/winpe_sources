# CBrowserFrame::FrameMessagePump(void)

- ea: `0x180045fa0`
- end: `0x180046721`
- name: `?FrameMessagePump@CBrowserFrame@@QEAAXXZ`
- size: `1921`
- prototype: `void __fastcall(CBrowserFrame *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801f0498`

## callees

- `0x180005030`
- `0x180045fa0`
- `0x180046728`
- `0x18005ada0`
- `0x180074e98`
- `0x18008f1bc`
- `0x1801cb220`
- `0x1801e1650`
- `0x180208d48`
- `0x18024a830`
- `0x1802627e0`
- `0x1802a4d80`
- `0x1803b6028`
- `0x1805267f8`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180046523`
- `KERNEL32!GetTickCount64` at `0x180046523`
- `KERNEL32!GetCurrentThreadId` at `0x180046074`
- `KERNEL32!GetCurrentThreadId` at `0x180046631`
- `KERNEL32!GetCurrentThreadId` at `0x1800466b2`
- `KERNEL32!GetCurrentThreadId` at `0x180046074`
- `KERNEL32!GetCurrentThreadId` at `0x180046631`
- `KERNEL32!GetCurrentThreadId` at `0x1800466b2`
- `USER32!IsWindow` at `0x1800461a3`
- `USER32!IsWindow` at `0x1800461a3`
- `USER32!TranslateMessage` at `0x180046241`
- `USER32!TranslateMessage` at `0x180046294`
- `USER32!TranslateMessage` at `0x180046241`
- `USER32!TranslateMessage` at `0x180046294`
- `USER32!DispatchMessageW` at `0x180046251`
- `USER32!DispatchMessageW` at `0x1800462a4`
- `USER32!DispatchMessageW` at `0x180046251`
- `USER32!DispatchMessageW` at `0x1800462a4`
- `USER32!WaitMessage` at `0x180046710`
- `USER32!WaitMessage` at `0x180046710`
- `USER32!PeekMessageW` at `0x180046356`
- `USER32!PeekMessageW` at `0x180046356`
- `USER32!GetMessageExtraInfo` at `0x18004642f`
- `USER32!GetMessageExtraInfo` at `0x18004642f`
- `USER32!IsWindowEnabled` at `0x180046323`
- `USER32!IsWindowEnabled` at `0x180046323`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800466cf`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800466cf`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800461b3`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800461b3`
- `IEUI!WaitMessageEx` at `0x180046114`
- `IEUI!WaitMessageEx` at `0x180046114`
- `IEUI!PeekMessageExW` at `0x180046060`
- `IEUI!PeekMessageExW` at `0x180046060`
- `msIso!__imp_?LCIEChangeComponentSharedFlagBit@@YAJK_NK@Z` at `0x180046512`
- `msIso!__imp_?LCIEChangeComponentSharedFlagBit@@YAJK_NK@Z` at `0x180046512`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180046211`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180046227`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180046211`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180046227`
- `msIso!__imp_?IsoDispatchMessageToArtifacts@@YAJPEAUtagMSG@@@Z` at `0x180046277`
- `msIso!__imp_?IsoDispatchMessageToArtifacts@@YAJPEAUtagMSG@@@Z` at `0x180046277`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1800460cf`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1800460cf`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1800460b0`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1800460b0`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x18004666e`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x18004666e`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x18004667f`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x18004667f`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x1800460f3`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x180046262`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x18004661c`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x180046698`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x1800460f3`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x180046262`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x18004661c`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x180046698`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180045fe3`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180045ff2`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180045fe3`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180045ff2`

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
      && *ProcessGetRefCountAddress() < dword_1806A20F4
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
    dword_1806A20F4 = *ProcessGetRefCountAddress();
    if ( *((_DWORD *)this + 66) )
      WaitMessageEx();
    else
      WaitMessage();
  }
}

```

## disassembly

```asm
0x180045fa0  mov     [rsp-8+arg_18], rdi
0x180045fa5  push    rbp
0x180045fa6  push    r14
0x180045fa8  push    r15
0x180045faa  lea     rbp, [rsp-47h]
0x180045faf  sub     rsp, 0D0h
0x180045fb6  mov     rax, cs:__security_cookie
0x180045fbd  xor     rax, rsp
0x180045fc0  mov     [rbp+57h+var_30], rax
0x180045fc4  cmp     dword ptr [rcx+218h], 0
0x180045fcb  mov     rdi, rcx
0x180045fce  movaps  [rsp+0E0h+var_20], xmm6
0x180045fd6  jnz     loc_180046367
0x180045fdc  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x180045fe3  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180045fea  nop     dword ptr [rax+rax+00h]
0x180045fef  movups  xmmword ptr [rax], xmm6
0x180045ff2  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180045ff9  nop     dword ptr [rax+rax+00h]
0x180045ffe  movaps  xmm6, [rsp+0E0h+var_20]
0x180046006  xor     r14d, r14d
0x180046009  mov     [rsp+0E0h+arg_8], rbx
0x180046011  mov     r15d, 0FF515780h
0x180046017  mov     [rsp+0E0h+arg_10], rsi
0x18004601f  mov     byte ptr [rax+10h], 0
0x180046023  nop     dword ptr [rax+00h]
0x180046027  nop     word ptr [rax+rax+00000000h]
0x180046030  xorps   xmm0, xmm0
0x180046033  mov     [rsp+0E0h+wRemoveMsg], 1; wRemoveMsg
0x18004603b  xor     r9d, r9d; wMsgFilterMax
0x18004603e  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180046042  xor     r8d, r8d; wMsgFilterMin
0x180046045  xor     edx, edx; hWnd
0x180046047  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18004604b  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18004604f  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x180046053  cmp     [rdi+108h], r14d
0x18004605a  jz      loc_180046356
0x180046060  call    cs:__imp_PeekMessageExW
0x180046067  nop     dword ptr [rax+rax+00h]
0x18004606c  test    eax, eax
0x18004606e  jnz     loc_180046125
0x180046074  call    cs:__imp_GetCurrentThreadId
0x18004607b  nop     dword ptr [rax+rax+00h]
0x180046080  cmp     eax, cs:g_tidParking
0x180046086  jz      loc_180046262
0x18004608c  lea     rax, [rdi+0F4h]
0x180046093  cmp     [rax], r14d
0x180046096  jz      loc_1800462B5
0x18004609c  cmp     [rdi+208h], r14d
0x1800460a3  jnz     loc_18004661C
0x1800460a9  mov     ebx, r14d
0x1800460ac  mov     [rbp+57h+var_A8], r14
0x1800460b0  call    cs:__imp_?IsoGetAuthorityManager@@YAKXZ; IsoGetAuthorityManager(void)
0x1800460b7  nop     dword ptr [rax+rax+00h]
0x1800460bc  xor     r9d, r9d
0x1800460bf  xor     r8d, r8d
0x1800460c2  mov     ecx, eax
0x1800460c4  xor     edx, edx
0x1800460c6  lea     rax, [rbp+57h+var_A8]
0x1800460ca  mov     qword ptr [rsp+0E0h+wRemoveMsg], rax
0x1800460cf  call    cs:__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z; IsoGetTrustSplitComponent(ulong,ulong,_IsoComponent * *,ulong *,_IsoUntrustedComponent * *)
0x1800460d6  nop     dword ptr [rax+rax+00h]
0x1800460db  test    eax, eax
0x1800460dd  js      short loc_1800460E6
0x1800460df  mov     rax, [rbp+57h+var_A8]
0x1800460e3  mov     ebx, [rax+6Ch]
0x1800460e6  cmp     cs:?g_cProcessIESessions@@3KA, r14d; ulong g_cProcessIESessions
0x1800460ed  jz      loc_180046690
0x1800460f3  call    cs:__imp_?ProcessGetRefCountAddress@@YAPEAJXZ; ProcessGetRefCountAddress(void)
0x1800460fa  nop     dword ptr [rax+rax+00h]
0x1800460ff  mov     ecx, [rax]
0x180046101  mov     cs:dword_1806A20F4, ecx
0x180046107  cmp     [rdi+108h], r14d
0x18004610e  jz      loc_180046710
0x180046114  call    cs:__imp_WaitMessageEx
0x18004611b  nop     dword ptr [rax+rax+00h]
0x180046120  jmp     loc_180046030
0x180046125  mov     ecx, [rbp+57h+Msg.message]
0x180046128  cmp     ecx, 85BEh
0x18004612e  jz      loc_180046385
0x180046134  cmp     ecx, 85BFh
0x18004613a  jz      loc_1800463D1
0x180046140  cmp     ecx, 85C0h
0x180046146  jz      loc_1800463E0
0x18004614c  cmp     ecx, 85C1h
0x180046152  jz      loc_1800463EF
0x180046158  xor     sil, sil
0x18004615b  lea     eax, [rcx-200h]
0x180046161  cmp     eax, 0Eh
0x180046164  jbe     loc_1800463FE
0x18004616a  cmp     ecx, 100h
0x180046170  jz      loc_18004638F
0x180046176  lea     eax, [rcx-201h]
0x18004617c  cmp     eax, 2
0x18004617f  jbe     loc_1800462E7
0x180046185  cmp     ecx, 16h
0x180046188  jz      loc_180046504
0x18004618e  cmp     ecx, 483h
0x180046194  jz      loc_1800462B5
0x18004619a  mov     rcx, [rdi+8]; hWnd
0x18004619e  test    rcx, rcx
0x1800461a1  jz      short loc_18004620C
0x1800461a3  call    cs:__imp_IsWindow
0x1800461aa  nop     dword ptr [rax+rax+00h]
0x1800461af  test    eax, eax
0x1800461b1  jz      short loc_18004620C
0x1800461b3  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1800461ba  nop     dword ptr [rax+rax+00h]
0x1800461bf  test    al, al
0x1800461c1  jz      loc_180046551
0x1800461c7  mov     ecx, [rbp+57h+Msg.message]
0x1800461ca  lea     eax, [rcx-200h]
0x1800461d0  cmp     eax, 0Eh
0x1800461d3  jbe     loc_180046523
0x1800461d9  lea     eax, [rcx-100h]
0x1800461df  cmp     eax, 9
0x1800461e2  jbe     loc_180046523
0x1800461e8  cmp     ecx, 10h
0x1800461eb  jz      loc_180046312
0x1800461f1  cmp     ecx, 46Ah
0x1800461f7  jz      loc_180046312
0x1800461fd  lea     eax, [rcx-100h]
0x180046203  cmp     eax, 9
0x180046206  jbe     loc_18004657D
0x18004620c  mov     ecx, 2
0x180046211  call    cs:__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z; IsoGetWindowsMessageNumber(_IsoMsgWmNumbers)
0x180046218  nop     dword ptr [rax+rax+00h]
0x18004621d  cmp     [rbp+57h+Msg.message], eax
0x180046220  jz      short loc_180046273
0x180046222  mov     ecx, 3
0x180046227  call    cs:__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z; IsoGetWindowsMessageNumber(_IsoMsgWmNumbers)
0x18004622e  nop     dword ptr [rax+rax+00h]
0x180046233  cmp     [rbp+57h+Msg.message], eax
0x180046236  jz      short loc_180046273
0x180046238  test    sil, sil
0x18004623b  jnz     short loc_18004624D
0x18004623d  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180046241  call    cs:__imp_TranslateMessage
0x180046248  nop     dword ptr [rax+rax+00h]
0x18004624d  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180046251  call    cs:__imp_DispatchMessageW
0x180046258  nop     dword ptr [rax+rax+00h]
0x18004625d  jmp     loc_180046030
0x180046262  call    cs:__imp_?ProcessGetRefCountAddress@@YAPEAJXZ; ProcessGetRefCountAddress(void)
0x180046269  nop     dword ptr [rax+rax+00h]
0x18004626e  jmp     loc_180046093
0x180046273  lea     rcx, [rbp+57h+Msg]
0x180046277  call    cs:__imp_?IsoDispatchMessageToArtifacts@@YAJPEAUtagMSG@@@Z; IsoDispatchMessageToArtifacts(tagMSG *)
0x18004627e  nop     dword ptr [rax+rax+00h]
0x180046283  test    eax, eax
0x180046285  jz      loc_180046030
0x18004628b  test    sil, sil
0x18004628e  jnz     short loc_1800462A0
0x180046290  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180046294  call    cs:__imp_TranslateMessage
0x18004629b  nop     dword ptr [rax+rax+00h]
0x1800462a0  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800462a4  call    cs:__imp_DispatchMessageW
0x1800462ab  nop     dword ptr [rax+rax+00h]
0x1800462b0  jmp     loc_180046030
0x1800462b5  mov     rsi, [rsp+0E0h+arg_10]
0x1800462bd  mov     rbx, [rsp+0E0h+arg_8]
0x1800462c5  mov     rcx, [rbp+57h+var_30]
0x1800462c9  xor     rcx, rsp; StackCookie
0x1800462cc  call    __security_check_cookie
0x1800462d1  mov     rdi, [rsp+0E0h+arg_18]
0x1800462d9  add     rsp, 0D0h
0x1800462e0  pop     r15
0x1800462e2  pop     r14
0x1800462e4  pop     rbp
0x1800462e5  retn
0x1800462e7  test    byte ptr cs:Microsoft_IEFRAMEEnableBits, 1
0x1800462ee  jz      loc_18004618E
0x1800462f4  mov     r8d, ecx
0x1800462f7  lea     rdx, LEFTBUTTONACTION_INFO
0x1800462fe  lea     rcx, BERP_IEFRAME2_Context
0x180046305  call    McTemplateU0q_EventWriteTransfer
0x18004630a  mov     ecx, [rbp+57h+Msg.message]
0x18004630d  jmp     loc_18004618E
0x180046312  mov     rax, [rdi+8]
0x180046316  cmp     rax, [rbp+57h+Msg.hwnd]
0x18004631a  jnz     loc_1800461FD
0x180046320  mov     rcx, rax; hWnd
0x180046323  call    cs:__imp_IsWindowEnabled
0x18004632a  nop     dword ptr [rax+rax+00h]
0x18004632f  test    eax, eax
0x180046331  jz      loc_180046575
0x180046337  cmp     [rbp+57h+Msg.message], 46Ah
0x18004633e  jz      loc_180046559
0x180046344  mov     edx, 1; int
0x180046349  mov     rcx, rdi; this
0x18004634c  call    ?_OnClose@CBrowserFrame@@IEAAXH@Z; CBrowserFrame::_OnClose(int)
0x180046351  jmp     loc_180046030
0x180046356  call    cs:__imp_PeekMessageW
0x18004635d  nop     dword ptr [rax+rax+00h]
0x180046362  jmp     loc_18004606C
0x180046367  mov     rcx, [rcx+118h]
0x18004636e  test    rcx, rcx
0x180046371  jz      loc_180045FDC
0x180046377  add     rcx, 8; this
0x18004637b  call    ?CloseAllTabs@CTabWindowManager@@UEAAJXZ; CTabWindowManager::CloseAllTabs(void)
0x180046380  jmp     loc_180045FDC
0x180046385  mov     [rbp+57h+Msg.message], 100h
0x18004638c  mov     sil, 1
0x18004638f  mov     rax, [rbp+57h+Msg.wParam]
0x180046393  cmp     rax, 0Dh
0x180046397  jnz     loc_180046452
0x18004639d  test    byte ptr cs:Microsoft_IEFRAMEEnableBits, 1
0x1800463a4  jz      loc_18004619A
0x1800463aa  lea     rax, [rbp+57h+var_70]
0x1800463ae  mov     r9d, 1
0x1800463b4  lea     rdx, BROWSERTHREADPROC_RETURN_INFO
0x1800463bb  mov     qword ptr [rsp+0E0h+wRemoveMsg], rax
0x1800463c0  lea     rcx, BERP_IEFRAME2_Context
0x1800463c7  call    McGenEventWrite_EventWriteTransfer
0x1800463cc  jmp     loc_18004630A
0x1800463d1  mov     [rbp+57h+Msg.message], 101h
0x1800463d8  mov     sil, 1
0x1800463db  jmp     loc_18004619A
0x1800463e0  mov     [rbp+57h+Msg.message], 104h
0x1800463e7  mov     sil, 1
0x1800463ea  jmp     loc_18004619A
0x1800463ef  mov     [rbp+57h+Msg.message], 105h
0x1800463f6  mov     sil, 1
0x1800463f9  jmp     loc_18004619A
0x1800463fe  lea     rcx, [rbp+57h+var_B0]; struct tagINPUT_MESSAGE_SOURCE *
0x180046402  mov     [rdi+3D1h], sil
0x180046409  mov     qword ptr [rbp+57h+var_B0.deviceType], r14
0x18004640d  call    ?IE_GetCurrentInputMessageSource@@YAHPEAUtagINPUT_MESSAGE_SOURCE@@@Z; IE_GetCurrentInputMessageSource(tagINPUT_MESSAGE_SOURCE *)
0x180046412  test    eax, eax
0x180046414  jz      short loc_18004642F
0x180046416  cmp     [rbp+57h+var_B0.deviceType], 4
0x18004641a  mov     ecx, [rbp+57h+Msg.message]
0x18004641d  jnz     loc_18004616A
0x180046423  mov     byte ptr [rdi+3D1h], 1
0x18004642a  jmp     loc_18004616A
0x18004642f  call    cs:__imp_GetMessageExtraInfo
0x180046436  nop     dword ptr [rax+rax+00h]
0x18004643b  mov     ecx, [rbp+57h+Msg.message]
0x18004643e  and     rax, r15
0x180046441  cmp     rax, r15
0x180046444  setz    al
0x180046447  mov     [rdi+3D1h], al
0x18004644d  jmp     loc_18004616A
0x180046452  cmp     rax, 8
0x180046456  jnz     short loc_18004648C
0x180046458  test    byte ptr cs:Microsoft_IEFRAMEEnableBits, 1
0x18004645f  jz      loc_18004619A
0x180046465  lea     rax, [rbp+57h+var_60]
0x180046469  mov     r9d, 1
0x18004646f  lea     rdx, BACKNAVIAGATION_REQUESTED_INFO
0x180046476  mov     qword ptr [rsp+0E0h+wRemoveMsg], rax
0x18004647b  lea     rcx, BERP_IEFRAME2_Context
0x180046482  call    McGenEventWrite_EventWriteTransfer
0x180046487  jmp     loc_18004630A
0x18004648c  cmp     rax, 22h ; '"'
0x180046490  jnz     short loc_1800464C6
0x180046492  test    byte ptr cs:Microsoft_IEFRAMEEnableBits, 1
0x180046499  jz      loc_18004619A
0x18004649f  lea     rax, [rbp+57h+var_50]
0x1800464a3  mov     r9d, 1
0x1800464a9  lea     rdx, BROWSERTHREADPROC_NEXT_INFO
0x1800464b0  mov     qword ptr [rsp+0E0h+wRemoveMsg], rax
0x1800464b5  lea     rcx, BERP_IEFRAME2_Context
0x1800464bc  call    McGenEventWrite_EventWriteTransfer
0x1800464c1  jmp     loc_18004630A
0x1800464c6  cmp     rax, 21h ; '!'
0x1800464ca  jnz     loc_18004619A
0x1800464d0  test    byte ptr cs:Microsoft_IEFRAMEEnableBits, 1
0x1800464d7  jz      loc_18004619A
0x1800464dd  lea     rax, [rbp+57h+var_40]
0x1800464e1  mov     r9d, 1
0x1800464e7  lea     rdx, BROWSERTHREADPROC_PRIOR_INFO
0x1800464ee  mov     qword ptr [rsp+0E0h+wRemoveMsg], rax
0x1800464f3  lea     rcx, BERP_IEFRAME2_Context
0x1800464fa  call    McGenEventWrite_EventWriteTransfer
0x1800464ff  jmp     loc_18004630A
0x180046504  mov     ecx, [rdi+2ACh]
0x18004650a  mov     r8d, 4
0x180046510  mov     dl, 1
0x180046512  call    cs:__imp_?LCIEChangeComponentSharedFlagBit@@YAJK_NK@Z; LCIEChangeComponentSharedFlagBit(ulong,bool,ulong)
0x180046519  nop     dword ptr [rax+rax+00h]
0x18004651e  jmp     loc_18004630A
0x180046523  call    cs:__imp_GetTickCount64
0x18004652a  nop     dword ptr [rax+rax+00h]
0x18004652f  mov     rcx, [rdi+4D8h]
0x180046536  add     rcx, 3E8h
0x18004653d  cmp     rcx, rax
0x180046540  jnb     short loc_180046551
0x180046542  mov     rcx, rdi; this
0x180046545  mov     [rdi+4D8h], rax
0x18004654c  call    ?DualEngineOnInputAttempted@CBrowserFrame@@QEAAXXZ; CBrowserFrame::DualEngineOnInputAttempted(void)
0x180046551  mov     ecx, [rbp+57h+Msg.message]
0x180046554  jmp     loc_1800461E8
0x180046559  mov     rax, [rdi+118h]
0x180046560  test    rax, rax
0x180046563  jz      loc_180046344
0x180046569  mov     byte ptr [rax+198h], 1
0x180046570  jmp     loc_180046344
  ... truncated ...
```
