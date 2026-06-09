# CGlassTerminal::staticCreateGlassSession(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180071620`
- end: `0x180071d59`
- name: `?staticCreateGlassSession@CGlassTerminal@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `1849`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001b80`
- `0x180008f64`
- `0x180014ff0`
- `0x18001eab0`
- `0x180025070`
- `0x180025890`
- `0x180029edc`
- `0x18002ce58`
- `0x180045fa4`
- `0x180071620`
- `0x180071d60`
- `0x18008ad08`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180071794`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180071794`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800717c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800717c6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007177e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180071bfb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007177e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180071bfb`

## string_xrefs

- `0x180071674`: `staticCreateGlassSession`
- `0x180071686`: `No glass terminal created in this environment`
- `0x1800717e4`: `Attempting to reuse the pre-created glass session ...`
- `0x18007183d`: `Successfully obtained the pre-created glass session`
- `0x180071a71`: `Temp. glass session reconnect failed`
- `0x180071aae`: `Trying to see if we should switch to a cache session`
- `0x180071aed`: `SwitchToCacheSession finished`
- `0x180071b29`: `Successfully switched to cache session, return.`
- `0x180071b44`: `We're not supposed to (or we gave up) trying to switch to cache session.`
- `0x180071b78`: `Creating new glass replacement session`
- `0x180071cb0`: `Created new glass replacement session successfully`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CGlassTerminal::staticCreateGlassSession(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  struct ISessionManagerInternal *v6; // rbx
  int InstanceOfGlassTerminalNew; // eax
  int v8; // r8d
  int v9; // r9d
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, __int64 *); // rsi
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v18; // ecx
  int v19; // edi
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // eax
  const char *v26; // rax
  char *v27; // rdx
  int v28; // eax
  int v29; // edi
  const char *v30; // rax
  char *v31; // rdx
  __int64 (__fastcall *v32)(struct ISessionManagerInternal *, __int64 *, struct ITerminal *); // rdi
  int v33; // eax
  int v34; // r8d
  int v35; // r9d
  int v36; // eax
  int v37; // eax
  int v38; // r8d
  int v39; // r9d
  int v40; // [rsp+40h] [rbp-19h] BYREF
  const char *v41; // [rsp+48h] [rbp-11h] BYREF
  __int64 v42; // [rsp+50h] [rbp-9h] BYREF
  const char *v43; // [rsp+58h] [rbp-1h] BYREF
  const char *v44; // [rsp+60h] [rbp+7h] BYREF
  int v45; // [rsp+68h] [rbp+Fh] BYREF
  int v46; // [rsp+6Ch] [rbp+13h] BYREF
  struct ITerminal *v47; // [rsp+70h] [rbp+17h] BYREF
  int v48; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v49; // [rsp+80h] [rbp+27h] BYREF
  __int64 v50; // [rsp+88h] [rbp+2Fh] BYREF
  struct ISessionManagerInternal *v51[2]; // [rsp+90h] [rbp+37h] BYREF
  int v52; // [rsp+D8h] [rbp+7Fh] BYREF

  v51[0] = 0;
  v42 = 0;
  v47 = 0;
  v50 = 0;
  v46 = 0;
  v52 = -1;
  v49 = 0;
  if ( !(unsigned int)AllowGlassTerminal() )
  {
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      v43 = "staticCreateGlassSession";
      v40 = -2147024891;
      v44 = "No glass terminal created in this environment";
      v41 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v3,
        (unsigned int)&dword_1800C64C4,
        v4,
        v5,
        (__int64)&v41,
        (__int64)&v44,
        (__int64)&v40,
        (__int64)&v43);
    }
    goto LABEL_67;
  }
  ISessionManagerInternal::GetInstanceOfSessionManagerInternal(v51);
  v45 = 0;
  v6 = v51[0];
  if ( (*(int (__fastcall **)(struct ISessionManagerInternal *, int *))(*(_QWORD *)v51[0] + 88LL))(v51[0], &v45) >= 0
    && v45 )
  {
    DoSessionLoggedOff();
    goto LABEL_67;
  }
  v48 = 0;
  if ( (*(int (__fastcall **)(struct ISessionManagerInternal *, int *, int *))(*(_QWORD *)v6 + 192LL))(v6, &v46, &v48) >= 0
    && v46 == 1 )
  {
    goto LABEL_67;
  }
  while ( 1 )
  {
    InstanceOfGlassTerminalNew = CGlassTerminal::staticGetInstanceOfGlassTerminalNew(&v47);
    if ( InstanceOfGlassTerminalNew >= 0 )
      break;
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      v40 = InstanceOfGlassTerminalNew;
      v41 = "staticGetInstanceOfGlassTerminal failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_1800DA020,
        (unsigned int)byte_1800C6499,
        v8,
        v9,
        (__int64)&v41,
        (__int64)&v40);
    }
    Sleep(0x1388u);
  }
  v41 = (const char *)&CTempGlassTerminal::g_staticTempGlassCSLock;
  EnterCriticalSection((LPCRITICAL_SECTION)&CTempGlassTerminal::g_staticTempGlassCSLock);
  SmartPtr<ITempGlassTerminal>::operator=(&v49);
  if ( *(_QWORD *)&CTempGlassTerminal::g_staticTempGlassTerminal )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&CTempGlassTerminal::g_staticTempGlassTerminal + 16LL))(*(_QWORD *)&CTempGlassTerminal::g_staticTempGlassTerminal);
    *(_QWORD *)&CTempGlassTerminal::g_staticTempGlassTerminal = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)&CTempGlassTerminal::g_staticTempGlassCSLock);
  v13 = v49;
  if ( !v49 )
  {
    if ( (unsigned int)dword_1800DA020 > 5 )
    {
      v41 = "Trying to see if we should switch to a cache session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v10,
        (unsigned int)word_1800C6302,
        v11,
        v12,
        (__int64)&v41);
    }
    v28 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v6 + 56LL))(v6);
    v29 = v28;
    v15 = dword_1800DA020;
    if ( (unsigned int)dword_1800DA020 > 5 )
    {
      v40 = v28;
      v41 = "SwitchToCacheSession finished";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_1800DA020,
        (unsigned int)byte_1800C62DB,
        v16,
        v17,
        (__int64)&v41,
        (__int64)&v40);
    }
    if ( !v29 )
    {
      if ( (unsigned int)dword_1800DA020 <= 4 )
        goto LABEL_67;
      v30 = "Successfully switched to cache session, return.";
      v31 = byte_1800C62B9;
LABEL_66:
      v41 = v30;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v15,
        (_DWORD)v31,
        v16,
        v17,
        (__int64)&v41);
      goto LABEL_67;
    }
    if ( (unsigned int)dword_1800DA020 > 4 )
    {
      v40 = v29;
      v41 = "We're not supposed to (or we gave up) trying to switch to cache session.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v15,
        (unsigned int)word_1800C6292,
        v16,
        v17,
        (__int64)&v41,
        (__int64)&v40);
    }
LABEL_50:
    if ( (unsigned int)dword_1800DA020 > 4 )
    {
      v41 = "Creating new glass replacement session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v15,
        (unsigned int)&dword_1800C626C,
        v16,
        v17,
        (__int64)&v41);
    }
    while ( 1 )
    {
      while ( 1 )
      {
        v32 = *(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *, struct ITerminal *))(*(_QWORD *)v6 + 40LL);
        wil::com_ptr_t<ITSSession,wil::err_returncode_policy>::reset(&v42);
        v33 = v32(v6, &v42, v47);
        if ( v33 >= 0 )
          break;
        if ( (unsigned int)dword_1800DA020 > 2 )
        {
          v40 = v33;
          v41 = "GetInstanceOfSession failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            dword_1800DA020,
            (unsigned int)byte_1800C6241,
            v34,
            v35,
            (__int64)&v41,
            (__int64)&v40);
        }
        Sleep(0x1388u);
      }
      v36 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v42 + 32LL))(
              v42,
              0xFFFFFFFFLL,
              0,
              0,
              0);
      if ( v36 == -805305602 )
        break;
      if ( v36 >= 0 )
      {
        v40 = -1;
        v37 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 80LL))(v42, &v40);
        if ( (unsigned int)dword_1800DA020 > 4 )
        {
          LODWORD(v43) = v37;
          v41 = (const char *)v40;
          v44 = "Created new glass replacement session successfully";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            dword_1800DA020,
            (unsigned int)byte_1800C61B5,
            v38,
            v39,
            (__int64)&v44,
            (__int64)&v41,
            (__int64)&v43);
        }
        goto LABEL_67;
      }
      if ( v42 )
      {
        if ( (unsigned int)dword_1800DA020 > 2 )
        {
          v40 = v36;
          v41 = "ptrSession->Start() failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            dword_1800DA020,
            (unsigned int)&unk_1800C61F0,
            v16,
            v17,
            (__int64)&v41,
            (__int64)&v40);
        }
        wil::com_ptr_t<ITSSession,wil::err_returncode_policy>::reset(&v42);
      }
    }
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_67;
    v30 = "System is in shutdown, no glass creation";
    v31 = byte_1800C621B;
    goto LABEL_66;
  }
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    v41 = "Attempting to reuse the pre-created glass session ...";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v10,
      (unsigned int)byte_1800C6473,
      v11,
      v12,
      (__int64)&v41);
  }
  v14 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 232LL);
  wil::com_ptr_t<ITSSession,wil::err_returncode_policy>::reset(&v42);
  if ( v14(v13, &v42) < 0 )
    goto LABEL_50;
  v43 = 0;
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    v41 = "Successfully obtained the pre-created glass session";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v15,
      (unsigned int)byte_1800C644D,
      v16,
      v17,
      (__int64)&v41);
  }
  v19 = (**(__int64 (__fastcall ***)(__int64, __int64 *, const char **))v42)(v42, qword_1800B2A78, &v43);
  if ( v19 < 0 )
    goto LABEL_38;
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 80LL))(v42, &v52);
  (*(void (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v6 + 32LL))(v6, &v50);
  v19 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v50 + 32LL))(
          v50,
          2,
          (unsigned int)v52,
          120000);
  if ( v19 < 0 )
  {
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      v40 = v19;
      v41 = (const char *)v52;
      v44 = "WaitForSessionState failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_1800C640E,
        v23,
        v24,
        (__int64)&v44,
        (__int64)&v41,
        (__int64)&v40);
    }
    v25 = (*(__int64 (__fastcall **)(const char *, __int64))(*(_QWORD *)v43 + 576LL))(v43, 4);
    if ( v25 < 0 )
    {
      v18 = dword_1800DA020;
      if ( (unsigned int)dword_1800DA020 > 2 )
      {
        v40 = v25;
        v41 = (const char *)v52;
        v44 = "LogoffEx failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          dword_1800DA020,
          (unsigned int)byte_1800C63CB,
          v20,
          v21,
          (__int64)&v44,
          (__int64)&v41,
          (__int64)&v40);
      }
    }
    goto LABEL_38;
  }
  v19 = (*(__int64 (__fastcall **)(const char *, __int64, __int64))(*(_QWORD *)v43 + 528LL))(v43, 11, 524);
  if ( v19 < 0 )
  {
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      v26 = "DisconnectEx() failed";
      v27 = (char *)&unk_1800C63A0;
LABEL_37:
      v41 = v26;
      v40 = v19;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v18,
        (_DWORD)v27,
        v20,
        v21,
        (__int64)&v41,
        (__int64)&v40);
      goto LABEL_38;
    }
    goto LABEL_38;
  }
  v19 = (*(__int64 (__fastcall **)(const char *, struct ITerminal *, __int64, __int64))(*(_QWORD *)v43 + 536LL))(
          v43,
          v47,
          525,
          1);
  if ( v19 < 0 )
  {
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      v26 = "ReconnectEx() failed";
      v27 = &byte_1800C634F;
      goto LABEL_37;
    }
LABEL_38:
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      v40 = v19;
      v41 = "Temp. glass session reconnect failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v18,
        (unsigned int)&dword_1800C6324,
        v20,
        v21,
        (__int64)&v41,
        (__int64)&v40);
    }
    SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v43);
    goto LABEL_50;
  }
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    v41 = "ReconnectEx() succeed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v18,
      (unsigned int)word_1800C637A,
      v20,
      v21,
      (__int64)&v41);
  }
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v43);
LABEL_67:
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v49);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v50);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v47);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v42);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(v51);
}

```

## disassembly

```asm
0x180071620  mov     [rsp-8+arg_0], rbx
0x180071625  mov     [rsp-8+arg_8], rsi
0x18007162a  push    rbp
0x18007162b  push    rdi
0x18007162c  push    r14
0x18007162e  lea     rbp, [rsp-47h]
0x180071633  sub     rsp, 0A0h
0x18007163a  xor     r14d, r14d
0x18007163d  mov     [rbp+57h+var_20], r14
0x180071641  mov     [rbp+57h+var_60], r14
0x180071645  mov     [rbp+57h+var_40], r14
0x180071649  mov     [rbp+57h+var_28], r14
0x18007164d  mov     [rbp+57h+var_44], r14d
0x180071651  mov     [rbp+57h+arg_18], 0FFFFFFFFh
0x180071658  mov     [rbp+57h+var_30], r14
0x18007165c  call    ?AllowGlassTerminal@@YAHXZ; AllowGlassTerminal(void)
0x180071661  test    eax, eax
0x180071663  jnz     short loc_1800716D1
0x180071665  mov     eax, cs:dword_1800DA020
0x18007166b  cmp     eax, 3
0x18007166e  jbe     loc_180071D10
0x180071674  lea     rax, aStaticcreategl; "staticCreateGlassSession"
0x18007167b  mov     [rbp+57h+var_58], rax
0x18007167f  mov     [rbp+57h+var_70], 80070005h
0x180071686  lea     rax, aNoGlassTermina; "No glass terminal created in this envir"...
0x18007168d  mov     [rbp+57h+var_50], rax
0x180071691  lea     rax, aWarningHresult; "Warning HResult failed"
0x180071698  mov     [rbp+57h+var_68], rax
0x18007169c  lea     rax, [rbp+57h+var_58]
0x1800716a0  mov     [rsp+0B0h+var_78], rax
0x1800716a5  lea     rax, [rbp+57h+var_70]
0x1800716a9  mov     [rsp+0B0h+var_80], rax
0x1800716ae  lea     rax, [rbp+57h+var_50]
0x1800716b2  mov     [rsp+0B0h+var_88], rax
0x1800716b7  lea     rax, [rbp+57h+var_68]
0x1800716bb  mov     [rsp+0B0h+var_90], rax
0x1800716c0  lea     rdx, dword_1800C64C4
0x1800716c7  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800716cc  jmp     loc_180071D10
0x1800716d1  lea     rcx, [rbp+57h+var_20]; struct ISessionManagerInternal **
0x1800716d5  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x1800716da  mov     [rbp+57h+var_48], r14d
0x1800716de  mov     rbx, [rbp+57h+var_20]
0x1800716e2  mov     rax, [rbx]
0x1800716e5  lea     rdx, [rbp+57h+var_48]
0x1800716e9  mov     rcx, rbx
0x1800716ec  mov     rax, [rax+58h]
0x1800716f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800716f5  test    eax, eax
0x1800716f7  js      short loc_180071709
0x1800716f9  cmp     [rbp+57h+var_48], r14d
0x1800716fd  jz      short loc_180071709
0x1800716ff  call    ?DoSessionLoggedOff@@YAJXZ; DoSessionLoggedOff(void)
0x180071704  jmp     loc_180071D10
0x180071709  mov     [rbp+57h+var_38], r14d
0x18007170d  mov     rax, [rbx]
0x180071710  lea     r8, [rbp+57h+var_38]
0x180071714  lea     rdx, [rbp+57h+var_44]
0x180071718  mov     rcx, rbx
0x18007171b  mov     rax, [rax+0C0h]
0x180071722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071727  test    eax, eax
0x180071729  js      short loc_180071735
0x18007172b  cmp     [rbp+57h+var_44], 1
0x18007172f  jz      loc_180071D10
0x180071735  lea     rcx, [rbp+57h+var_40]; struct ITerminal **
0x180071739  call    ?staticGetInstanceOfGlassTerminalNew@CGlassTerminal@@SAJPEAPEAUITerminal@@@Z; CGlassTerminal::staticGetInstanceOfGlassTerminalNew(ITerminal * *)
0x18007173e  test    eax, eax
0x180071740  jns     short loc_180071786
0x180071742  mov     ecx, cs:dword_1800DA020
0x180071748  cmp     ecx, 2
0x18007174b  jbe     short loc_180071779
0x18007174d  mov     [rbp+57h+var_70], eax
0x180071750  lea     rax, aStaticgetinsta; "staticGetInstanceOfGlassTerminal failed"
0x180071757  mov     [rbp+57h+var_68], rax
0x18007175b  lea     rax, [rbp+57h+var_70]
0x18007175f  mov     [rsp+0B0h+var_88], rax
0x180071764  lea     rax, [rbp+57h+var_68]
0x180071768  mov     [rsp+0B0h+var_90], rax
0x18007176d  lea     rdx, byte_1800C6499
0x180071774  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180071779  mov     ecx, 1388h; dwMilliseconds
0x18007177e  call    cs:__imp_Sleep
0x180071784  jmp     short loc_180071735
0x180071786  lea     rdi, ?g_staticTempGlassCSLock@CTempGlassTerminal@@0VCCSLockEx@@A; CCSLockEx CTempGlassTerminal::g_staticTempGlassCSLock
0x18007178d  mov     [rbp+57h+var_68], rdi
0x180071791  mov     rcx, rdi; lpCriticalSection
0x180071794  call    cs:__imp_EnterCriticalSection
0x18007179a  nop
0x18007179b  lea     rcx, [rbp+57h+var_30]
0x18007179f  call    ??4?$SmartPtr@VITempGlassTerminal@@@@QEAAAEAV0@PEAVITempGlassTerminal@@@Z; SmartPtr<ITempGlassTerminal>::operator=(ITempGlassTerminal *)
0x1800717a4  mov     rcx, cs:?g_staticTempGlassTerminal@CTempGlassTerminal@@0PEAVITempGlassTerminal@@EA; ITempGlassTerminal * CTempGlassTerminal::g_staticTempGlassTerminal
0x1800717ab  test    rcx, rcx
0x1800717ae  jz      short loc_1800717C3
0x1800717b0  mov     rax, [rcx]
0x1800717b3  mov     rax, [rax+10h]
0x1800717b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800717bc  mov     cs:?g_staticTempGlassTerminal@CTempGlassTerminal@@0PEAVITempGlassTerminal@@EA, r14; ITempGlassTerminal * CTempGlassTerminal::g_staticTempGlassTerminal
0x1800717c3  mov     rcx, rdi; lpCriticalSection
0x1800717c6  call    cs:__imp_LeaveCriticalSection
0x1800717cc  mov     rdi, [rbp+57h+var_30]
0x1800717d0  mov     eax, cs:dword_1800DA020
0x1800717d6  test    rdi, rdi
0x1800717d9  jz      loc_180071AA9
0x1800717df  cmp     eax, 4
0x1800717e2  jbe     short loc_180071804
0x1800717e4  lea     rax, aAttemptingToRe; "Attempting to reuse the pre-created gla"...
0x1800717eb  mov     [rbp+57h+var_68], rax
0x1800717ef  lea     rax, [rbp+57h+var_68]
0x1800717f3  mov     [rsp+0B0h+var_90], rax
0x1800717f8  lea     rdx, byte_1800C6473
0x1800717ff  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180071804  mov     rax, [rdi]
0x180071807  mov     rsi, [rax+0E8h]
0x18007180e  lea     rcx, [rbp+57h+var_60]
0x180071812  call    ?reset@?$com_ptr_t@UITSSession@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<ITSSession,wil::err_returncode_policy>::reset(void)
0x180071817  lea     rdx, [rbp+57h+var_60]
0x18007181b  mov     rcx, rdi
0x18007181e  mov     rax, rsi
0x180071821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071826  test    eax, eax
0x180071828  js      loc_180071B6D
0x18007182e  mov     [rbp+57h+var_58], r14
0x180071832  mov     eax, cs:dword_1800DA020
0x180071838  cmp     eax, 4
0x18007183b  jbe     short loc_18007185D
0x18007183d  lea     rax, aSuccessfullyOb; "Successfully obtained the pre-created g"...
0x180071844  mov     [rbp+57h+var_68], rax
0x180071848  lea     rax, [rbp+57h+var_68]
0x18007184c  mov     [rsp+0B0h+var_90], rax
0x180071851  lea     rdx, byte_1800C644D
0x180071858  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007185d  mov     rcx, [rbp+57h+var_60]
0x180071861  mov     rax, [rcx]
0x180071864  lea     r8, [rbp+57h+var_58]
0x180071868  lea     rdx, qword_1800B2A78
0x18007186f  mov     rax, [rax]
0x180071872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071877  mov     edi, eax
0x180071879  test    eax, eax
0x18007187b  js      loc_180071A63
0x180071881  mov     rcx, [rbp+57h+var_60]
0x180071885  mov     rax, [rcx]
0x180071888  lea     rdx, [rbp+57h+arg_18]
0x18007188c  mov     rax, [rax+50h]
0x180071890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071895  mov     rax, [rbx]
0x180071898  lea     rdx, [rbp+57h+var_28]
0x18007189c  mov     rcx, rbx
0x18007189f  mov     rax, [rax+20h]
0x1800718a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800718a8  mov     rcx, [rbp+57h+var_28]
0x1800718ac  mov     rax, [rcx]
0x1800718af  mov     r9d, 1D4C0h
0x1800718b5  mov     r8d, [rbp+57h+arg_18]
0x1800718b9  mov     edx, 2
0x1800718be  mov     rax, [rax+20h]
0x1800718c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800718c7  mov     edi, eax
0x1800718c9  test    eax, eax
0x1800718cb  jns     loc_18007198A
0x1800718d1  mov     eax, cs:dword_1800DA020
0x1800718d7  cmp     eax, 2
0x1800718da  jbe     short loc_180071919
0x1800718dc  mov     [rbp+57h+var_70], edi
0x1800718df  movsxd  rax, [rbp+57h+arg_18]
0x1800718e3  mov     [rbp+57h+var_68], rax
0x1800718e7  lea     rax, aWaitforsession_2; "WaitForSessionState failed"
0x1800718ee  mov     [rbp+57h+var_50], rax
0x1800718f2  lea     rax, [rbp+57h+var_70]
0x1800718f6  mov     [rsp+0B0h+var_80], rax
0x1800718fb  lea     rax, [rbp+57h+var_68]
0x1800718ff  mov     [rsp+0B0h+var_88], rax
0x180071904  lea     rax, [rbp+57h+var_50]
0x180071908  mov     [rsp+0B0h+var_90], rax
0x18007190d  lea     rdx, word_1800C640E
0x180071914  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180071919  mov     rcx, [rbp+57h+var_58]
0x18007191d  mov     rax, [rcx]
0x180071920  mov     edx, 4
0x180071925  mov     rax, [rax+240h]
0x18007192c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071931  test    eax, eax
0x180071933  jns     loc_180071A63
0x180071939  mov     ecx, cs:dword_1800DA020
0x18007193f  cmp     ecx, 2
0x180071942  jbe     loc_180071A63
0x180071948  mov     [rbp+57h+var_70], eax
0x18007194b  movsxd  rax, [rbp+57h+arg_18]
0x18007194f  mov     [rbp+57h+var_68], rax
0x180071953  lea     rax, aLogoffexFailed_0; "LogoffEx failed"
0x18007195a  mov     [rbp+57h+var_50], rax
0x18007195e  lea     rax, [rbp+57h+var_70]
0x180071962  mov     [rsp+0B0h+var_80], rax
0x180071967  lea     rax, [rbp+57h+var_68]
0x18007196b  mov     [rsp+0B0h+var_88], rax
0x180071970  lea     rax, [rbp+57h+var_50]
0x180071974  mov     [rsp+0B0h+var_90], rax
0x180071979  lea     rdx, byte_1800C63CB
0x180071980  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180071985  jmp     loc_180071A63
0x18007198a  mov     rcx, [rbp+57h+var_58]
0x18007198e  mov     rax, [rcx]
0x180071991  xor     r9d, r9d
0x180071994  lea     edx, [r9+0Bh]
0x180071998  mov     r8d, 20Ch
0x18007199e  mov     rax, [rax+210h]
0x1800719a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800719aa  mov     edi, eax
0x1800719ac  test    eax, eax
0x1800719ae  jns     short loc_1800719CF
0x1800719b0  mov     eax, cs:dword_1800DA020
0x1800719b6  cmp     eax, 2
0x1800719b9  jbe     loc_180071A63
0x1800719bf  lea     rax, aDisconnectexFa; "DisconnectEx() failed"
0x1800719c6  lea     rdx, unk_1800C63A0
0x1800719cd  jmp     short loc_180071A45
0x1800719cf  mov     rcx, [rbp+57h+var_58]
0x1800719d3  mov     rax, [rcx]
0x1800719d6  mov     r9d, 1
0x1800719dc  mov     r8d, 20Dh
0x1800719e2  mov     rdx, [rbp+57h+var_40]
0x1800719e6  mov     rax, [rax+218h]
0x1800719ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800719f2  mov     edi, eax
0x1800719f4  test    eax, eax
0x1800719f6  mov     eax, cs:dword_1800DA020
0x1800719fc  js      short loc_180071A32
0x1800719fe  cmp     eax, 4
0x180071a01  jbe     short loc_180071A24
0x180071a03  lea     rax, aReconnectexSuc; "ReconnectEx() succeed"
0x180071a0a  mov     [rbp+57h+var_68], rax
0x180071a0e  lea     rax, [rbp+57h+var_68]
0x180071a12  mov     [rsp+0B0h+var_90], rax
0x180071a17  lea     rdx, word_1800C637A
0x180071a1e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180071a23  nop
0x180071a24  lea     rcx, [rbp+57h+var_58]
0x180071a28  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180071a2d  jmp     loc_180071D10
0x180071a32  cmp     eax, 2
0x180071a35  jbe     short loc_180071A63
0x180071a37  lea     rax, aReconnectexFai; "ReconnectEx() failed"
0x180071a3e  lea     rdx, byte_1800C634F
0x180071a45  mov     [rbp+57h+var_68], rax
0x180071a49  lea     rax, [rbp+57h+var_70]
0x180071a4d  mov     [rsp+0B0h+var_88], rax
0x180071a52  lea     rax, [rbp+57h+var_68]
0x180071a56  mov     [rsp+0B0h+var_90], rax
0x180071a5b  mov     [rbp+57h+var_70], edi
0x180071a5e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180071a63  mov     eax, cs:dword_1800DA020
0x180071a69  cmp     eax, 2
0x180071a6c  jbe     short loc_180071A9B
0x180071a6e  mov     [rbp+57h+var_70], edi
0x180071a71  lea     rax, aTempGlassSessi; "Temp. glass session reconnect failed"
0x180071a78  mov     [rbp+57h+var_68], rax
0x180071a7c  lea     rax, [rbp+57h+var_70]
0x180071a80  mov     [rsp+0B0h+var_88], rax
0x180071a85  lea     rax, [rbp+57h+var_68]
0x180071a89  mov     [rsp+0B0h+var_90], rax
0x180071a8e  lea     rdx, dword_1800C6324
0x180071a95  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180071a9a  nop
0x180071a9b  lea     rcx, [rbp+57h+var_58]
0x180071a9f  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180071aa4  jmp     loc_180071B6D
0x180071aa9  cmp     eax, 5
0x180071aac  jbe     short loc_180071ACE
0x180071aae  lea     rax, aTryingToSeeIfW; "Trying to see if we should switch to a "...
0x180071ab5  mov     [rbp+57h+var_68], rax
0x180071ab9  lea     rax, [rbp+57h+var_68]
0x180071abd  mov     [rsp+0B0h+var_90], rax
0x180071ac2  lea     rdx, word_1800C6302
0x180071ac9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180071ace  mov     rax, [rbx]
0x180071ad1  mov     rcx, rbx
0x180071ad4  mov     rax, [rax+38h]
0x180071ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071add  mov     edi, eax
0x180071adf  mov     ecx, cs:dword_1800DA020
0x180071ae5  cmp     ecx, 5
0x180071ae8  jbe     short loc_180071B16
0x180071aea  mov     [rbp+57h+var_70], eax
0x180071aed  lea     rax, aSwitchtocaches_0; "SwitchToCacheSession finished"
0x180071af4  mov     [rbp+57h+var_68], rax
0x180071af8  lea     rax, [rbp+57h+var_70]
0x180071afc  mov     [rsp+0B0h+var_88], rax
0x180071b01  lea     rax, [rbp+57h+var_68]
0x180071b05  mov     [rsp+0B0h+var_90], rax
0x180071b0a  lea     rdx, byte_1800C62DB
0x180071b11  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180071b16  mov     eax, cs:dword_1800DA020
0x180071b1c  test    edi, edi
0x180071b1e  jnz     short loc_180071B3C
0x180071b20  cmp     eax, 4
0x180071b23  jbe     loc_180071D10
0x180071b29  lea     rax, aSuccessfullySw; "Successfully switched to cache session,"...
0x180071b30  lea     rdx, byte_1800C62B9
0x180071b37  jmp     loc_180071CFD
  ... truncated ...
```
