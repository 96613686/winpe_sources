# CCliModalLoop::HandleWakeForMsg(void)

- ea: `0x18009ccd8`
- end: `0x18009d280`
- name: `?HandleWakeForMsg@CCliModalLoop@@AEAAXXZ`
- size: `1448`
- prototype: `void __fastcall(CCliModalLoop *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18009c804`

## callees

- `0x1800880f8`
- `0x18008db2c`
- `0x18009ccd8`
- `0x18009d79c`
- `0x18009d8f0`
- `0x18009dacc`
- `0x18009de18`
- `0x18009df84`
- `0x18010dfe8`
- `0x1801457c0`
- `0x18014d5f4`
- `0x180187ea8`
- `0x1801b1314`
- `0x1801b6ec0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x18009ce84`
- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x18009ce84`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DispatchMessageW` at `0x18009ceea`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DispatchMessageW` at `0x18009cf66`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DispatchMessageW` at `0x18009ceea`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DispatchMessageW` at `0x18009cf66`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PeekMessageW` at `0x18009ce75`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PeekMessageW` at `0x18009ce75`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetQueueStatus` at `0x18009cd20`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetQueueStatus` at `0x18009cd20`
- `ext-ms-win-ntuser-private-l1-1-0!IsThreadMessageQueueAttached` at `0x18009cdf1`
- `ext-ms-win-ntuser-private-l1-1-0!IsThreadMessageQueueAttached` at `0x18009cdf1`

## string_xrefs

- `0x18009cfa9`: `onecore\com\combase\dcomrem\callctrl.cxx`
- `0x18009d083`: `onecore\com\combase\dcomrem\callctrl.cxx`
- `0x18009d12e`: `onecore\com\combase\dcomrem\callctrl.cxx`
- `0x18009d1d6`: `onecore\com\combase\dcomrem\callctrl.cxx`
- `0x18009d20d`: `onecore\com\combase\dcomrem\callctrl.cxx`
- `0x180249c45`: `onecore\com\combase\dcomrem\callctrl.cxx`
- `0x180249cd5`: `onecore\com\combase\dcomrem\callctrl.cxx`

## pseudocode

```c
void __fastcall CCliModalLoop::HandleWakeForMsg(CCliModalLoop *this)
{
  DWORD QueueStatus; // esi
  unsigned __int64 LowPart; // rcx
  _DWORD *ReservedForOle; // r14
  DWORD v5; // r13d
  __int16 v6; // si
  unsigned int dwTIDCallee; // edx
  __int64 v8; // rcx
  int j; // eax
  void (__fastcall *v10)(const _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, _EVENT_FILTER_DESCRIPTOR *, void *); // rdx
  void (__fastcall *v11)(const _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, _EVENT_FILTER_DESCRIPTOR *, void *); // rdx
  void (__fastcall *v12)(const _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, _EVENT_FILTER_DESCRIPTOR *, void *); // rdx
  _MCGEN_TRACE_CONTEXT *v13; // rcx
  int i; // eax
  void (__fastcall *v15)(const _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, _EVENT_FILTER_DESCRIPTOR *, void *); // rdx
  int k; // eax
  void (__fastcall *v17)(const _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, _EVENT_FILTER_DESCRIPTOR *, void *); // rdx
  _MCGEN_TRACE_CONTEXT *v18; // rcx
  _MCGEN_TRACE_CONTEXT *v19; // rcx
  _MCGEN_TRACE_CONTEXT *v20; // rcx
  const _EVENT_DESCRIPTOR *v21; // rdx
  _MCGEN_TRACE_CONTEXT *v22; // rcx
  unsigned int v23; // r8d
  void (__fastcall *v24)(const _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, _EVENT_FILTER_DESCRIPTOR *, void *); // rdx
  const _EVENT_DESCRIPTOR *v25; // rdx
  _MCGEN_TRACE_CONTEXT *v26; // rcx
  unsigned int v27; // r8d
  tagMSG msg; // [rsp+30h] [rbp-58h] BYREF

  memset(&msg, 0, sizeof(msg));
  ++this->_handleWakeForMsgCount;
  CCliModalLoop::RevertToNormalPointerInputMode(this);
  if ( this->_dwMsgQInputFlag == 64 )
  {
    PeekMessageW(&msg, 0, 0, 0, 0);
    goto LABEL_18;
  }
  QueueStatus = GetQueueStatus(0x5CFFu);
  LowPart = this->_dwMsgQInputFlag & 0x1CFF;
  if ( (_DWORD)LowPart == 7423 && CCliModalLoop::FindMessage(this, QueueStatus) )
    CCliModalLoop::HandlePendingMessage(this);
  if ( (this->_dwWaitFlags & 0x10) == 0 )
  {
    ReservedForOle = NtCurrentTeb()->ReservedForOle;
    v5 = HIWORD(QueueStatus);
    if ( (QueueStatus & 0x200000) != 0 )
    {
      LowPart = NtCurrentPeb()->AppCompatFlags.LowPart;
      if ( (LowPart & 0x100000) == 0 && CCliModalLoop::MyPeekMessage(this, &msg, 0, 0xFu, 0xFu, 3u) )
        DispatchMessageW(&msg);
      ReservedForOle[5] |= 0x80000u;
    }
    if ( (QueueStatus & 0x1C070000) != 0 )
    {
      ReservedForOle[5] |= 0x80000u;
      this->_dwFlags |= 0x10u;
      ++this->_handleWakeForMsgWithInputCount;
    }
    v6 = QueueStatus & 0x4000;
    if ( v6 && gfEnableTracing && IsWppLevelEnabled(INFO) )
      ComTraceMessageT<>(
        "onecore\\com\\combase\\dcomrem\\callctrl.cxx",
        "CCliModalLoop::HandleWakeForMsg",
        2325,
        INFO,
        L"Saw QS_TRANSFER in modal loop");
    if ( v6 || (this->_dwFlags & 2) != 0 )
    {
LABEL_31:
      this->_dwFlags |= 2u;
      if ( (v5 & 1) != 0 )
      {
        this->_dwFlags |= 8u;
        for ( i = CCliModalLoop::MyPeekMessage(this, &msg, 0, 0x100u, 0x109u, 3u);
              i;
              i = CCliModalLoop::MyPeekMessage(this, &msg, 0, 0x100u, 0x109u, 3u) )
        {
          if ( (this->_dwFlags & 0x20) == 0 )
          {
            if ( gfEnableTracing && IsWppLevelEnabled(INFO) )
              ComTraceMessageT<>(
                "onecore\\com\\combase\\dcomrem\\callctrl.cxx",
                "CCliModalLoop::HandleWakeForMsg",
                2364,
                INFO,
                L"Dropped keyboard message in STA");
            McGenEventRegister_EtwEventRegister(
              &S_olemsg_COM,
              v15,
              &S_olemsg_COM_Context,
              &S_olemsg_COM_Context.RegistrationHandle);
            if ( (Microsoft_Windows_COMRuntimeEnableBits[0] & 4) != 0 )
              McTemplateU0q_EtwEventWriteTransfer(v18, &DropKeyboardMessage, 0);
            this->_dwFlags |= 0x20u;
          }
        }
      }
      if ( (v5 & 6) != 0 )
      {
        this->_dwFlags |= 8u;
        for ( j = CCliModalLoop::MyPeekMessage(this, &msg, 0, 0x200u, 0x20Eu, 3u);
              j;
              j = CCliModalLoop::MyPeekMessage(this, &msg, 0, 0x200u, 0x20Eu, 3u) )
        {
          if ( (this->_dwFlags & 0x40) == 0 )
          {
            if ( gfEnableTracing && IsWppLevelEnabled(INFO) )
              ComTraceMessageT<>(
                "onecore\\com\\combase\\dcomrem\\callctrl.cxx",
                "CCliModalLoop::HandleWakeForMsg",
                2383,
                INFO,
                L"Dropped mouse message in STA");
            McGenEventRegister_EtwEventRegister(
              &S_olemsg_COM,
              v10,
              &S_olemsg_COM_Context,
              &S_olemsg_COM_Context.RegistrationHandle);
            if ( (Microsoft_Windows_COMRuntimeEnableBits[0] & 4) != 0 )
              McTemplateU0q_EtwEventWriteTransfer(v13, &DropMouseMessage, 0);
            this->_dwFlags |= 0x40u;
          }
        }
        while ( CCliModalLoop::MyPeekMessage(this, &msg, 0, 0xA0u, 0xADu, 3u) )
        {
          if ( (this->_dwFlags & 0x40) == 0 )
          {
            if ( gfEnableTracing && IsWppLevelEnabled(INFO) )
              ComTraceMessageT<>(
                "onecore\\com\\combase\\dcomrem\\callctrl.cxx",
                "CCliModalLoop::HandleWakeForMsg",
                2397,
                INFO,
                L"Dropped mouse message in STA");
            McGenEventRegister_EtwEventRegister(
              &S_olemsg_COM,
              v11,
              &S_olemsg_COM_Context,
              &S_olemsg_COM_Context.RegistrationHandle);
            if ( (Microsoft_Windows_COMRuntimeEnableBits[0] & 4) != 0 )
              McTemplateU0q_EtwEventWriteTransfer(v19, &DropMouseMessage, 0);
            this->_dwFlags |= 0x40u;
          }
        }
        while ( CCliModalLoop::MyPeekMessage(this, &msg, 0, 0x23u, 0x23u, 3u) )
        {
          if ( SLOBYTE(this->_dwFlags) >= 0 )
          {
            if ( gfEnableTracing && IsWppLevelEnabled(INFO) )
              ComTraceMessageT<>(
                "onecore\\com\\combase\\dcomrem\\callctrl.cxx",
                "CCliModalLoop::HandleWakeForMsg",
                2411,
                INFO,
                L"Dropped WM_QUEUESYNC in STA");
            McGenEventRegister_EtwEventRegister(
              &S_olemsg_COM,
              v12,
              &S_olemsg_COM_Context,
              &S_olemsg_COM_Context.RegistrationHandle);
            if ( (Microsoft_Windows_COMRuntimeEnableBits[0] & 4) != 0 )
              McTemplateU0q_EtwEventWriteTransfer(v20, &DropQueueSyncMessage, 0);
            this->_dwFlags |= 0x80u;
          }
        }
      }
      if ( (g_GLBOPT_RoFlags & 1) != 0
        && !CCliModalLoop::IsAttachedQueuePointerMessageReorderingAllowed((CCliModalLoop *)LowPart)
        && (v5 & 0x1000) != 0 )
      {
        this->_dwFlags |= 8u;
        for ( k = CCliModalLoop::MyPeekMessage(this, &msg, 0, 0x245u, 0x257u, 3u);
              k;
              k = CCliModalLoop::MyPeekMessage(this, &msg, 0, 0x245u, 0x257u, 3u) )
        {
          if ( gfEnableTracing && IsWppLevelEnabled(INFO) )
            ComTraceMessageT<unsigned int>(
              "onecore\\com\\combase\\dcomrem\\callctrl.cxx",
              "CCliModalLoop::HandleWakeForMsg",
              2437,
              INFO,
              L"Dropped pointer message %x in STA",
              msg.message);
          McGenEventRegister_EtwEventRegister(
            &S_olemsg_COM,
            v17,
            &S_olemsg_COM_Context,
            &S_olemsg_COM_Context.RegistrationHandle);
          if ( (Microsoft_Windows_COMRuntimeEnableBits[0] & 4) != 0 )
            McTemplateU0qq_EtwEventWriteTransfer(v22, v21, v23, msg.message);
        }
        while ( CCliModalLoop::MyPeekMessage(this, &msg, 0, 0x241u, 0x244u, 3u) )
        {
          if ( gfEnableTracing && IsWppLevelEnabled(INFO) )
            ComTraceMessageT<unsigned int>(
              "onecore\\com\\combase\\dcomrem\\callctrl.cxx",
              "CCliModalLoop::HandleWakeForMsg",
              2447,
              INFO,
              L"Dropped pointer message %x in STA",
              msg.message);
          McGenEventRegister_EtwEventRegister(
            &S_olemsg_COM,
            v24,
            &S_olemsg_COM_Context,
            &S_olemsg_COM_Context.RegistrationHandle);
          if ( (Microsoft_Windows_COMRuntimeEnableBits[0] & 4) != 0 )
            McTemplateU0qq_EtwEventWriteTransfer(v26, v25, v27, msg.message);
        }
      }
      if ( (QueueStatus & 0x200000) != 0 && CCliModalLoop::MyPeekMessage(this, &msg, 0, 0xFu, 0xFu, 3u) )
        DispatchMessageW(&msg);
      goto LABEL_18;
    }
    LowPart = 0;
    if ( this->_fAttachedQueueInputMessageRemovalAllowed )
    {
      if ( this->_fCoWaitCalled )
      {
        v8 = 0;
      }
      else
      {
        dwTIDCallee = this->_dwTIDCallee;
        if ( dwTIDCallee - 1 > 0xFFFFFFFD )
          goto LABEL_17;
        v8 = dwTIDCallee;
      }
      LowPart = (unsigned int)IsThreadMessageQueueAttached(v8);
    }
LABEL_17:
    if ( !(_DWORD)LowPart )
      goto LABEL_18;
    goto LABEL_31;
  }
LABEL_18:
  if ( !gEnableOldModalLoop )
  {
    if ( CCliModalLoop::MyPeekMessage(this, &msg, 0, 0, 0, 0) )
    {
      this->_fUseOldModalLoop = 1;
      ++this->_handleWakeForMsgDidntClearQueueCount;
    }
    else if ( this->_fUseOldModalLoop )
    {
      this->_fUseOldModalLoop = 0;
    }
  }
  CCliModalLoop::SetPointerInputModeAsAppropriateForQueueAttachmentConditions(this);
}

```

## disassembly

```asm
0x18009ccd8  mov     rax, rsp
0x18009ccdb  mov     [rax+10h], rbx
0x18009ccdf  mov     [rax+18h], rsi
0x18009cce3  mov     [rax+8], this
0x18009cce7  push    rdi
0x18009cce8  push    r12
0x18009ccea  push    r13
0x18009ccec  push    r14
0x18009ccee  push    r15
0x18009ccf0  sub     rsp, 60h
0x18009ccf4  mov     rbx, this
0x18009ccf7  xorps   xmm0, xmm0
0x18009ccfa  movups  xmmword ptr [rax-58h], xmm0
0x18009ccfe  movups  xmmword ptr [rax-48h], xmm0
0x18009cd02  movups  xmmword ptr [rax-38h], xmm0
0x18009cd06  inc     dword ptr [this+0A0h]
0x18009cd0c  call    ?RevertToNormalPointerInputMode@CCliModalLoop@@AEAAXXZ; CCliModalLoop::RevertToNormalPointerInputMode(void)
0x18009cd11  cmp     dword ptr [rbx+3Ch], 40h ; '@'
0x18009cd15  jz      loc_18009CE62
0x18009cd1b  mov     ecx, 5CFFh; flags
0x18009cd20  call    cs:__imp_GetQueueStatus
0x18009cd26  mov     esi, eax
0x18009cd28  mov     ecx, [rbx+3Ch]
0x18009cd2b  mov     eax, 1CFFh
0x18009cd30  and     ecx, eax
0x18009cd32  cmp     ecx, eax
0x18009cd34  jnz     loc_18009CE99
0x18009cd3a  mov     edx, esi; dwStatus
0x18009cd3c  mov     this, rbx; this
0x18009cd3f  call    ?FindMessage@CCliModalLoop@@AEAAHK@Z; CCliModalLoop::FindMessage(ulong)
0x18009cd44  xor     edi, edi
0x18009cd46  test    eax, eax
0x18009cd48  jz      short loc_18009CD52
0x18009cd4a  mov     this, rbx; this
0x18009cd4d  call    ?HandlePendingMessage@CCliModalLoop@@AEAAXXZ; CCliModalLoop::HandlePendingMessage(void)
0x18009cd52  test    byte ptr [rbx+54h], 10h
0x18009cd56  jnz     loc_18009CE01
0x18009cd5c  mov     rax, gs:30h
0x18009cd65  mov     r14, [rax+1758h]
0x18009cd6c  mov     r13d, esi
0x18009cd6f  shr     r13d, 10h
0x18009cd73  movzx   eax, r13w
0x18009cd77  and     ax, 20h
0x18009cd7b  mov     word ptr [rsp+88h+arg_0], ax
0x18009cd83  mov     r12d, 3
0x18009cd89  jnz     loc_18009CEA7
0x18009cd8f  mov     eax, 1C07h
0x18009cd94  test    ax, r13w
0x18009cd98  jz      short loc_18009CDAA
0x18009cd9a  bts     dword ptr [r14+14h], 13h
0x18009cda0  or      dword ptr [rbx+50h], 10h
0x18009cda4  inc     dword ptr [rbx+0A4h]
0x18009cdaa  mov     eax, 4000h
0x18009cdaf  and     si, ax
0x18009cdb2  mov     r14d, 2
0x18009cdb8  jnz     loc_18009CF71
0x18009cdbe  test    si, si
0x18009cdc1  jnz     loc_18009CEFB
0x18009cdc7  test    [rbx+50h], r14b
0x18009cdcb  jnz     loc_18009CEFB
0x18009cdd1  mov     ecx, edi
0x18009cdd3  cmp     [rbx+6Ch], edi
0x18009cdd6  jz      short loc_18009CDF9
0x18009cdd8  cmp     [rbx+80h], edi
0x18009cdde  jnz     loc_18009CEA0
0x18009cde4  mov     edx, [rbx+38h]
0x18009cde7  lea     eax, [rdx-1]
0x18009cdea  cmp     eax, 0FFFFFFFDh
0x18009cded  ja      short loc_18009CDF9
0x18009cdef  mov     ecx, edx
0x18009cdf1  call    cs:__imp_IsThreadMessageQueueAttached
0x18009cdf7  mov     ecx, eax
0x18009cdf9  test    ecx, ecx
0x18009cdfb  jnz     loc_18009CEFB
0x18009ce01  cmp     cs:?gEnableOldModalLoop@@3HA, edi; int gEnableOldModalLoop
0x18009ce07  jnz     short loc_18009CE36
0x18009ce09  mov     [rsp+88h+wFlag], di; wFlag
0x18009ce0e  mov     [rsp+88h+max], edi; max
0x18009ce12  xor     r9d, r9d; min
0x18009ce15  xor     r8d, r8d; hwnd
0x18009ce18  lea     rdx, [rsp+88h+msg]; pMsg
0x18009ce1d  mov     this, rbx; this
0x18009ce20  call    ?MyPeekMessage@CCliModalLoop@@QEAAHPEAUtagMSG@@PEAUHWND__@@IIG@Z; CCliModalLoop::MyPeekMessage(tagMSG *,HWND__ *,uint,uint,ushort)
0x18009ce25  test    eax, eax
0x18009ce27  jz      short loc_18009CE58
0x18009ce29  mov     dword ptr [rbx+68h], 1
0x18009ce30  inc     dword ptr [rbx+0A8h]
0x18009ce36  mov     this, rbx; this
0x18009ce39  call    ?SetPointerInputModeAsAppropriateForQueueAttachmentConditions@CCliModalLoop@@AEAAXXZ; CCliModalLoop::SetPointerInputModeAsAppropriateForQueueAttachmentConditions(void)
0x18009ce3e  lea     r11, [rsp+88h+var_28]
0x18009ce43  mov     rbx, [r11+38h]
0x18009ce47  mov     rsi, [r11+40h]
0x18009ce4b  mov     rsp, r11
0x18009ce4e  pop     r15
0x18009ce50  pop     r14
0x18009ce52  pop     r13
0x18009ce54  pop     r12
0x18009ce56  pop     rdi
0x18009ce57  retn
0x18009ce58  cmp     [rbx+68h], edi
0x18009ce5b  jz      short loc_18009CE36
0x18009ce5d  mov     [rbx+68h], edi
0x18009ce60  jmp     short loc_18009CE36
0x18009ce62  xor     edi, edi
0x18009ce64  mov     [rsp+88h+max], edi; wRemoveMsg
0x18009ce68  xor     r9d, r9d; wMsgFilterMax
0x18009ce6b  xor     r8d, r8d; wMsgFilterMin
0x18009ce6e  xor     edx, edx; hWnd
0x18009ce70  lea     this, [rsp+88h+msg]; lpMsg
0x18009ce75  call    cs:__imp_PeekMessageW
0x18009ce7b  jmp     short loc_18009CE01
0x18009ce7d  cmp     eax, 0C00000FDh
0x18009ce82  jnz     short loc_18009CE8A
0x18009ce84  call    cs:__imp__o__resetstkoflw
0x18009ce8a  xor     edi, edi
0x18009ce8c  mov     rbx, [rsp+88h+arg_0]
0x18009ce94  jmp     loc_18009CE01
0x18009ce99  xor     edi, edi
0x18009ce9b  jmp     loc_18009CD52
0x18009cea0  xor     ecx, ecx
0x18009cea2  jmp     loc_18009CDF1
0x18009cea7  mov     rax, gs:60h
0x18009ceb0  mov     ecx, [rax+2C8h]
0x18009ceb6  bt      this, 14h
0x18009cebb  jb      short loc_18009CEF0
0x18009cebd  mov     [rsp+88h+wFlag], r12w; wFlag
0x18009cec3  mov     [rsp+88h+max], 0Fh; max
0x18009cecb  mov     r9d, 0Fh; min
0x18009ced1  xor     r8d, r8d; hwnd
0x18009ced4  lea     rdx, [rsp+88h+msg]; pMsg
0x18009ced9  mov     this, rbx; this
0x18009cedc  call    ?MyPeekMessage@CCliModalLoop@@QEAAHPEAUtagMSG@@PEAUHWND__@@IIG@Z; CCliModalLoop::MyPeekMessage(tagMSG *,HWND__ *,uint,uint,ushort)
0x18009cee1  test    eax, eax
0x18009cee3  jz      short loc_18009CEF0
0x18009cee5  lea     this, [rsp+88h+msg]; lpMsg
0x18009ceea  call    cs:__imp_DispatchMessageW
0x18009cef0  bts     dword ptr [r14+14h], 13h
0x18009cef6  jmp     loc_18009CD8F
0x18009cefb  or      [rbx+50h], r14d
0x18009ceff  test    r13b, 1
0x18009cf03  jnz     loc_18009D140
0x18009cf09  lea     r15, S_olemsg_COM_Context
0x18009cf10  test    r13b, 6
0x18009cf14  jnz     loc_18009CFBA
0x18009cf1a  test    byte ptr cs:?g_GLBOPT_RoFlags@@3KA, 1; ulong g_GLBOPT_RoFlags
0x18009cf21  jnz     loc_18009D232
0x18009cf27  cmp     word ptr [rsp+88h+arg_0], di
0x18009cf2f  jz      loc_18009CE01
0x18009cf35  mov     [rsp+88h+wFlag], r12w; wFlag
0x18009cf3b  mov     [rsp+88h+max], 0Fh; max
0x18009cf43  mov     r9d, 0Fh; min
0x18009cf49  xor     r8d, r8d; hwnd
0x18009cf4c  lea     rdx, [rsp+88h+msg]; pMsg
0x18009cf51  mov     this, rbx; this
0x18009cf54  call    ?MyPeekMessage@CCliModalLoop@@QEAAHPEAUtagMSG@@PEAUHWND__@@IIG@Z; CCliModalLoop::MyPeekMessage(tagMSG *,HWND__ *,uint,uint,ushort)
0x18009cf59  test    eax, eax
0x18009cf5b  jz      loc_18009CE01
0x18009cf61  lea     this, [rsp+88h+msg]; lpMsg
0x18009cf66  call    cs:__imp_DispatchMessageW
0x18009cf6c  jmp     loc_18009CE01
0x18009cf71  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18009cf77  jz      loc_18009CDBE
0x18009cf7d  mov     ecx, r14d; level
0x18009cf80  call    IsWppLevelEnabled
0x18009cf85  test    al, al
0x18009cf87  jz      loc_18009CDBE
0x18009cf8d  lea     rax, aSawQsTransferI; "Saw QS_TRANSFER in modal loop"
0x18009cf94  mov     qword ptr [rsp+88h+max], rax; format
0x18009cf99  mov     r9d, r14d; level
0x18009cf9c  mov     r8d, 915h; line
0x18009cfa2  lea     rdx, aCclimodalloopH; "CCliModalLoop::HandleWakeForMsg"
0x18009cfa9  lea     this, aOnecoreComComb_7; "onecore\\com\\combase\\dcomrem\\callctr"...
0x18009cfb0  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x18009cfb5  jmp     loc_18009CDBE
0x18009cfba  or      dword ptr [rbx+50h], 8
0x18009cfbe  mov     [rsp+88h+wFlag], r12w; wFlag
0x18009cfc4  mov     [rsp+88h+max], 20Eh; max
0x18009cfcc  mov     r9d, 200h; min
0x18009cfd2  xor     r8d, r8d; hwnd
0x18009cfd5  lea     rdx, [rsp+88h+msg]; pMsg
0x18009cfda  mov     this, rbx; this
0x18009cfdd  call    ?MyPeekMessage@CCliModalLoop@@QEAAHPEAUtagMSG@@PEAUHWND__@@IIG@Z; CCliModalLoop::MyPeekMessage(tagMSG *,HWND__ *,uint,uint,ushort)
0x18009cfe2  lea     rsi, aDroppedMouseMe; "Dropped mouse message in STA"
0x18009cfe9  test    eax, eax
0x18009cfeb  jnz     loc_18009D095
0x18009cff1  mov     [rsp+88h+wFlag], r12w; wFlag
0x18009cff7  mov     [rsp+88h+max], 0ADh; max
0x18009cfff  mov     r9d, 0A0h; min
0x18009d005  xor     r8d, r8d; hwnd
0x18009d008  lea     rdx, [rsp+88h+msg]; pMsg
0x18009d00d  mov     this, rbx; this
0x18009d010  call    ?MyPeekMessage@CCliModalLoop@@QEAAHPEAUtagMSG@@PEAUHWND__@@IIG@Z; CCliModalLoop::MyPeekMessage(tagMSG *,HWND__ *,uint,uint,ushort)
0x18009d015  test    eax, eax
0x18009d017  jnz     loc_18009D0F3
0x18009d01d  lea     esi, [rax+23h]
0x18009d020  mov     [rsp+88h+wFlag], r12w; wFlag
0x18009d026  mov     [rsp+88h+max], esi; max
0x18009d02a  mov     r9d, esi; min
0x18009d02d  xor     r8d, r8d; hwnd
0x18009d030  lea     rdx, [rsp+88h+msg]; pMsg
0x18009d035  mov     this, rbx; this
0x18009d038  call    ?MyPeekMessage@CCliModalLoop@@QEAAHPEAUtagMSG@@PEAUHWND__@@IIG@Z; CCliModalLoop::MyPeekMessage(tagMSG *,HWND__ *,uint,uint,ushort)
0x18009d03d  test    eax, eax
0x18009d03f  jz      loc_18009CF1A
0x18009d045  test    byte ptr [rbx+50h], 80h
0x18009d049  jnz     short loc_18009D020
0x18009d04b  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18009d051  jz      loc_180249BD8
0x18009d057  mov     ecx, r14d; level
0x18009d05a  call    IsWppLevelEnabled
0x18009d05f  test    al, al
0x18009d061  jz      loc_180249BD8
0x18009d067  lea     rax, aDroppedWmQueue_0; "Dropped WM_QUEUESYNC in STA"
0x18009d06e  mov     qword ptr [rsp+88h+max], rax; format
0x18009d073  mov     r9d, r14d; level
0x18009d076  mov     r8d, 96Bh; line
0x18009d07c  lea     rdx, aCclimodalloopH; "CCliModalLoop::HandleWakeForMsg"
0x18009d083  lea     this, aOnecoreComComb_7; "onecore\\com\\combase\\dcomrem\\callctr"...
0x18009d08a  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x18009d08f  nop
0x18009d090  jmp     loc_180249BD8
0x18009d095  test    byte ptr [rbx+50h], 40h
0x18009d099  jnz     short loc_18009D0CA
0x18009d09b  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18009d0a1  jnz     loc_18009D1E8
0x18009d0a7  mov     r9, r15; ProviderId
0x18009d0aa  mov     r8, r15; RegHandle
0x18009d0ad  lea     this, S_olemsg_COM; ProviderId
0x18009d0b4  call    McGenEventRegister_EtwEventRegister
0x18009d0b9  test    byte ptr cs:Microsoft_Windows_COMRuntimeEnableBits, 4
0x18009d0c0  jnz     loc_18009D21E
0x18009d0c6  or      dword ptr [rbx+50h], 40h
0x18009d0ca  mov     [rsp+88h+wFlag], r12w; wFlag
0x18009d0d0  mov     [rsp+88h+max], 20Eh; max
0x18009d0d8  mov     r9d, 200h; min
0x18009d0de  xor     r8d, r8d; hwnd
0x18009d0e1  lea     rdx, [rsp+88h+msg]; pMsg
0x18009d0e6  mov     this, rbx; this
0x18009d0e9  call    ?MyPeekMessage@CCliModalLoop@@QEAAHPEAUtagMSG@@PEAUHWND__@@IIG@Z; CCliModalLoop::MyPeekMessage(tagMSG *,HWND__ *,uint,uint,ushort)
0x18009d0ee  jmp     loc_18009CFE9
0x18009d0f3  test    byte ptr [rbx+50h], 40h
0x18009d0f7  jnz     loc_18009CFF1
0x18009d0fd  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18009d103  jz      loc_180249BA5
0x18009d109  mov     ecx, r14d; level
0x18009d10c  call    IsWppLevelEnabled
0x18009d111  test    al, al
0x18009d113  jz      loc_180249BA5
0x18009d119  mov     qword ptr [rsp+88h+max], rsi; format
0x18009d11e  mov     r9d, r14d; level
0x18009d121  mov     r8d, 95Dh; line
0x18009d127  lea     rdx, aCclimodalloopH; "CCliModalLoop::HandleWakeForMsg"
0x18009d12e  lea     this, aOnecoreComComb_7; "onecore\\com\\combase\\dcomrem\\callctr"...
0x18009d135  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x18009d13a  nop
0x18009d13b  jmp     loc_180249BA5
0x18009d140  or      dword ptr [rbx+50h], 8
0x18009d144  mov     [rsp+88h+wFlag], r12w; wFlag
0x18009d14a  mov     esi, 109h
0x18009d14f  mov     [rsp+88h+max], esi; max
0x18009d153  lea     r9d, [rsi-9]; min
0x18009d157  xor     r8d, r8d; hwnd
0x18009d15a  lea     rdx, [rsp+88h+msg]; pMsg
0x18009d15f  mov     this, rbx; this
0x18009d162  call    ?MyPeekMessage@CCliModalLoop@@QEAAHPEAUtagMSG@@PEAUHWND__@@IIG@Z; CCliModalLoop::MyPeekMessage(tagMSG *,HWND__ *,uint,uint,ushort)
0x18009d167  lea     r15, S_olemsg_COM_Context
0x18009d16e  test    eax, eax
0x18009d170  jz      loc_18009CF10
0x18009d176  test    byte ptr [rbx+50h], 20h
0x18009d17a  jz      short loc_18009D19E
0x18009d17c  mov     [rsp+88h+wFlag], r12w; wFlag
0x18009d182  mov     [rsp+88h+max], esi; max
0x18009d186  mov     r9d, 100h; min
0x18009d18c  xor     r8d, r8d; hwnd
0x18009d18f  lea     rdx, [rsp+88h+msg]; pMsg
0x18009d194  mov     this, rbx; this
0x18009d197  call    ?MyPeekMessage@CCliModalLoop@@QEAAHPEAUtagMSG@@PEAUHWND__@@IIG@Z; CCliModalLoop::MyPeekMessage(tagMSG *,HWND__ *,uint,uint,ushort)
0x18009d19c  jmp     short loc_18009D16E
0x18009d19e  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18009d1a4  jz      loc_180249B72
0x18009d1aa  mov     ecx, r14d; level
0x18009d1ad  call    IsWppLevelEnabled
0x18009d1b2  test    al, al
0x18009d1b4  jz      loc_180249B72
0x18009d1ba  lea     rax, aDroppedKeyboar; "Dropped keyboard message in STA"
0x18009d1c1  mov     qword ptr [rsp+88h+max], rax; format
0x18009d1c6  mov     r9d, r14d; level
0x18009d1c9  mov     r8d, 93Ch; line
0x18009d1cf  lea     rdx, aCclimodalloopH; "CCliModalLoop::HandleWakeForMsg"
0x18009d1d6  lea     this, aOnecoreComComb_7; "onecore\\com\\combase\\dcomrem\\callctr"...
0x18009d1dd  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x18009d1e2  nop
0x18009d1e3  jmp     loc_180249B72
0x18009d1e8  mov     ecx, r14d; level
0x18009d1eb  call    IsWppLevelEnabled
0x18009d1f0  test    al, al
0x18009d1f2  jz      loc_18009D0A7
0x18009d1f8  mov     qword ptr [rsp+88h+max], rsi; format
0x18009d1fd  mov     r9d, r14d; level
0x18009d200  mov     r8d, 94Fh; line
  ... truncated ...
```
