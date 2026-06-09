# CGlassTerminal::staticCreateGlassSession(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180075760`
- end: `0x180075eb2`
- name: `?staticCreateGlassSession@CGlassTerminal@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `1874`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001b90`
- `0x18000c684`
- `0x18000f320`
- `0x18001eb00`
- `0x18002701c`
- `0x18002772c`
- `0x18002be88`
- `0x18002ec64`
- `0x180048aa0`
- `0x180075760`
- `0x180075eb8`
- `0x18008faa8`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800758da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800758da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075912`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075912`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800758be`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180075d4d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800758be`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180075d4d`

## string_xrefs

- `0x1800757b4`: `staticCreateGlassSession`
- `0x1800757c6`: `No glass terminal created in this environment`
- `0x180075936`: `Attempting to reuse the pre-created glass session ...`
- `0x18007598f`: `Successfully obtained the pre-created glass session`
- `0x180075bc3`: `Temp. glass session reconnect failed`
- `0x180075c00`: `Trying to see if we should switch to a cache session`
- `0x180075c3f`: `SwitchToCacheSession finished`
- `0x180075c7b`: `Successfully switched to cache session, return.`
- `0x180075c96`: `We're not supposed to (or we gave up) trying to switch to cache session.`
- `0x180075cca`: `Creating new glass replacement session`
- `0x180075e08`: `Created new glass replacement session successfully`

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
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      v43 = "staticCreateGlassSession";
      v40 = -2147024891;
      v44 = "No glass terminal created in this environment";
      v41 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v3,
        (unsigned int)&dword_1800CB64C,
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
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      v40 = InstanceOfGlassTerminalNew;
      v41 = "staticGetInstanceOfGlassTerminal failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_1800DF020,
        (unsigned int)byte_1800CB621,
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
    if ( (unsigned int)dword_1800DF020 > 5 )
    {
      v41 = "Trying to see if we should switch to a cache session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v10,
        (unsigned int)word_1800CB48A,
        v11,
        v12,
        (__int64)&v41);
    }
    v28 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v6 + 56LL))(v6);
    v29 = v28;
    v15 = dword_1800DF020;
    if ( (unsigned int)dword_1800DF020 > 5 )
    {
      v40 = v28;
      v41 = "SwitchToCacheSession finished";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_1800DF020,
        (unsigned int)byte_1800CB463,
        v16,
        v17,
        (__int64)&v41,
        (__int64)&v40);
    }
    if ( !v29 )
    {
      if ( (unsigned int)dword_1800DF020 <= 4 )
        goto LABEL_67;
      v30 = "Successfully switched to cache session, return.";
      v31 = byte_1800CB441;
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
    if ( (unsigned int)dword_1800DF020 > 4 )
    {
      v40 = v29;
      v41 = "We're not supposed to (or we gave up) trying to switch to cache session.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v15,
        (unsigned int)word_1800CB41A,
        v16,
        v17,
        (__int64)&v41,
        (__int64)&v40);
    }
LABEL_50:
    if ( (unsigned int)dword_1800DF020 > 4 )
    {
      v41 = "Creating new glass replacement session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v15,
        (unsigned int)&dword_1800CB3F4,
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
        if ( (unsigned int)dword_1800DF020 > 2 )
        {
          v40 = v33;
          v41 = "GetInstanceOfSession failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            dword_1800DF020,
            (unsigned int)byte_1800CB3C9,
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
        if ( (unsigned int)dword_1800DF020 > 4 )
        {
          LODWORD(v43) = v37;
          v41 = (const char *)v40;
          v44 = "Created new glass replacement session successfully";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            dword_1800DF020,
            (unsigned int)byte_1800CB33D,
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
        if ( (unsigned int)dword_1800DF020 > 2 )
        {
          v40 = v36;
          v41 = "ptrSession->Start() failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            dword_1800DF020,
            (unsigned int)&unk_1800CB378,
            v16,
            v17,
            (__int64)&v41,
            (__int64)&v40);
        }
        wil::com_ptr_t<ITSSession,wil::err_returncode_policy>::reset(&v42);
      }
    }
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_67;
    v30 = "System is in shutdown, no glass creation";
    v31 = byte_1800CB3A3;
    goto LABEL_66;
  }
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    v41 = "Attempting to reuse the pre-created glass session ...";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v10,
      (unsigned int)byte_1800CB5FB,
      v11,
      v12,
      (__int64)&v41);
  }
  v14 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 232LL);
  wil::com_ptr_t<ITSSession,wil::err_returncode_policy>::reset(&v42);
  if ( v14(v13, &v42) < 0 )
    goto LABEL_50;
  v43 = 0;
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    v41 = "Successfully obtained the pre-created glass session";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v15,
      (unsigned int)byte_1800CB5D5,
      v16,
      v17,
      (__int64)&v41);
  }
  v19 = (**(__int64 (__fastcall ***)(__int64, __int64 *, const char **))v42)(v42, qword_1800B7C08, &v43);
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
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      v40 = v19;
      v41 = (const char *)v52;
      v44 = "WaitForSessionState failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_1800CB596,
        v23,
        v24,
        (__int64)&v44,
        (__int64)&v41,
        (__int64)&v40);
    }
    v25 = (*(__int64 (__fastcall **)(const char *, __int64))(*(_QWORD *)v43 + 576LL))(v43, 4);
    if ( v25 < 0 )
    {
      v18 = dword_1800DF020;
      if ( (unsigned int)dword_1800DF020 > 2 )
      {
        v40 = v25;
        v41 = (const char *)v52;
        v44 = "LogoffEx failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          dword_1800DF020,
          (unsigned int)byte_1800CB553,
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
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      v26 = "DisconnectEx() failed";
      v27 = (char *)&unk_1800CB528;
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
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      v26 = "ReconnectEx() failed";
      v27 = &byte_1800CB4D7;
      goto LABEL_37;
    }
LABEL_38:
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      v40 = v19;
      v41 = "Temp. glass session reconnect failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v18,
        (unsigned int)&dword_1800CB4AC,
        v20,
        v21,
        (__int64)&v41,
        (__int64)&v40);
    }
    SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v43);
    goto LABEL_50;
  }
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    v41 = "ReconnectEx() succeed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v18,
      (unsigned int)word_1800CB502,
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
0x180075760  mov     [rsp-8+arg_0], rbx
0x180075765  mov     [rsp-8+arg_8], rsi
0x18007576a  push    rbp
0x18007576b  push    rdi
0x18007576c  push    r14
0x18007576e  lea     rbp, [rsp-47h]
0x180075773  sub     rsp, 0A0h
0x18007577a  xor     r14d, r14d
0x18007577d  mov     [rbp+57h+var_20], r14
0x180075781  mov     [rbp+57h+var_60], r14
0x180075785  mov     [rbp+57h+var_40], r14
0x180075789  mov     [rbp+57h+var_28], r14
0x18007578d  mov     [rbp+57h+var_44], r14d
0x180075791  mov     [rbp+57h+arg_18], 0FFFFFFFFh
0x180075798  mov     [rbp+57h+var_30], r14
0x18007579c  call    ?AllowGlassTerminal@@YAHXZ; AllowGlassTerminal(void)
0x1800757a1  test    eax, eax
0x1800757a3  jnz     short loc_180075811
0x1800757a5  mov     eax, cs:dword_1800DF020
0x1800757ab  cmp     eax, 3
0x1800757ae  jbe     loc_180075E68
0x1800757b4  lea     rax, aStaticcreategl; "staticCreateGlassSession"
0x1800757bb  mov     [rbp+57h+var_58], rax
0x1800757bf  mov     [rbp+57h+var_70], 80070005h
0x1800757c6  lea     rax, aNoGlassTermina; "No glass terminal created in this envir"...
0x1800757cd  mov     [rbp+57h+var_50], rax
0x1800757d1  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800757d8  mov     [rbp+57h+var_68], rax
0x1800757dc  lea     rax, [rbp+57h+var_58]
0x1800757e0  mov     [rsp+0B0h+var_78], rax
0x1800757e5  lea     rax, [rbp+57h+var_70]
0x1800757e9  mov     [rsp+0B0h+var_80], rax
0x1800757ee  lea     rax, [rbp+57h+var_50]
0x1800757f2  mov     [rsp+0B0h+var_88], rax
0x1800757f7  lea     rax, [rbp+57h+var_68]
0x1800757fb  mov     [rsp+0B0h+var_90], rax
0x180075800  lea     rdx, dword_1800CB64C
0x180075807  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18007580c  jmp     loc_180075E68
0x180075811  lea     rcx, [rbp+57h+var_20]; struct ISessionManagerInternal **
0x180075815  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18007581a  mov     [rbp+57h+var_48], r14d
0x18007581e  mov     rbx, [rbp+57h+var_20]
0x180075822  mov     rax, [rbx]
0x180075825  lea     rdx, [rbp+57h+var_48]
0x180075829  mov     rcx, rbx
0x18007582c  mov     rax, [rax+58h]
0x180075830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075835  test    eax, eax
0x180075837  js      short loc_180075849
0x180075839  cmp     [rbp+57h+var_48], r14d
0x18007583d  jz      short loc_180075849
0x18007583f  call    ?DoSessionLoggedOff@@YAJXZ; DoSessionLoggedOff(void)
0x180075844  jmp     loc_180075E68
0x180075849  mov     [rbp+57h+var_38], r14d
0x18007584d  mov     rax, [rbx]
0x180075850  lea     r8, [rbp+57h+var_38]
0x180075854  lea     rdx, [rbp+57h+var_44]
0x180075858  mov     rcx, rbx
0x18007585b  mov     rax, [rax+0C0h]
0x180075862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075867  test    eax, eax
0x180075869  js      short loc_180075875
0x18007586b  cmp     [rbp+57h+var_44], 1
0x18007586f  jz      loc_180075E68
0x180075875  lea     rcx, [rbp+57h+var_40]; struct ITerminal **
0x180075879  call    ?staticGetInstanceOfGlassTerminalNew@CGlassTerminal@@SAJPEAPEAUITerminal@@@Z; CGlassTerminal::staticGetInstanceOfGlassTerminalNew(ITerminal * *)
0x18007587e  test    eax, eax
0x180075880  jns     short loc_1800758CC
0x180075882  mov     ecx, cs:dword_1800DF020
0x180075888  cmp     ecx, 2
0x18007588b  jbe     short loc_1800758B9
0x18007588d  mov     [rbp+57h+var_70], eax
0x180075890  lea     rax, aStaticgetinsta; "staticGetInstanceOfGlassTerminal failed"
0x180075897  mov     [rbp+57h+var_68], rax
0x18007589b  lea     rax, [rbp+57h+var_70]
0x18007589f  mov     [rsp+0B0h+var_88], rax
0x1800758a4  lea     rax, [rbp+57h+var_68]
0x1800758a8  mov     [rsp+0B0h+var_90], rax
0x1800758ad  lea     rdx, byte_1800CB621
0x1800758b4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800758b9  mov     ecx, 1388h; dwMilliseconds
0x1800758be  call    cs:__imp_Sleep
0x1800758c5  nop     dword ptr [rax+rax+00h]
0x1800758ca  jmp     short loc_180075875
0x1800758cc  lea     rdi, ?g_staticTempGlassCSLock@CTempGlassTerminal@@0VCCSLockEx@@A; CCSLockEx CTempGlassTerminal::g_staticTempGlassCSLock
0x1800758d3  mov     [rbp+57h+var_68], rdi
0x1800758d7  mov     rcx, rdi; lpCriticalSection
0x1800758da  call    cs:__imp_EnterCriticalSection
0x1800758e1  nop     dword ptr [rax+rax+00h]
0x1800758e6  nop
0x1800758e7  lea     rcx, [rbp+57h+var_30]
0x1800758eb  call    ??4?$SmartPtr@VITempGlassTerminal@@@@QEAAAEAV0@PEAVITempGlassTerminal@@@Z; SmartPtr<ITempGlassTerminal>::operator=(ITempGlassTerminal *)
0x1800758f0  mov     rcx, cs:?g_staticTempGlassTerminal@CTempGlassTerminal@@0PEAVITempGlassTerminal@@EA; ITempGlassTerminal * CTempGlassTerminal::g_staticTempGlassTerminal
0x1800758f7  test    rcx, rcx
0x1800758fa  jz      short loc_18007590F
0x1800758fc  mov     rax, [rcx]
0x1800758ff  mov     rax, [rax+10h]
0x180075903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075908  mov     cs:?g_staticTempGlassTerminal@CTempGlassTerminal@@0PEAVITempGlassTerminal@@EA, r14; ITempGlassTerminal * CTempGlassTerminal::g_staticTempGlassTerminal
0x18007590f  mov     rcx, rdi; lpCriticalSection
0x180075912  call    cs:__imp_LeaveCriticalSection
0x180075919  nop     dword ptr [rax+rax+00h]
0x18007591e  mov     rdi, [rbp+57h+var_30]
0x180075922  mov     eax, cs:dword_1800DF020
0x180075928  test    rdi, rdi
0x18007592b  jz      loc_180075BFB
0x180075931  cmp     eax, 4
0x180075934  jbe     short loc_180075956
0x180075936  lea     rax, aAttemptingToRe; "Attempting to reuse the pre-created gla"...
0x18007593d  mov     [rbp+57h+var_68], rax
0x180075941  lea     rax, [rbp+57h+var_68]
0x180075945  mov     [rsp+0B0h+var_90], rax
0x18007594a  lea     rdx, byte_1800CB5FB
0x180075951  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180075956  mov     rax, [rdi]
0x180075959  mov     rsi, [rax+0E8h]
0x180075960  lea     rcx, [rbp+57h+var_60]
0x180075964  call    ?reset@?$com_ptr_t@UITSSession@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<ITSSession,wil::err_returncode_policy>::reset(void)
0x180075969  lea     rdx, [rbp+57h+var_60]
0x18007596d  mov     rcx, rdi
0x180075970  mov     rax, rsi
0x180075973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075978  test    eax, eax
0x18007597a  js      loc_180075CBF
0x180075980  mov     [rbp+57h+var_58], r14
0x180075984  mov     eax, cs:dword_1800DF020
0x18007598a  cmp     eax, 4
0x18007598d  jbe     short loc_1800759AF
0x18007598f  lea     rax, aSuccessfullyOb; "Successfully obtained the pre-created g"...
0x180075996  mov     [rbp+57h+var_68], rax
0x18007599a  lea     rax, [rbp+57h+var_68]
0x18007599e  mov     [rsp+0B0h+var_90], rax
0x1800759a3  lea     rdx, byte_1800CB5D5
0x1800759aa  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800759af  mov     rcx, [rbp+57h+var_60]
0x1800759b3  mov     rax, [rcx]
0x1800759b6  lea     r8, [rbp+57h+var_58]
0x1800759ba  lea     rdx, qword_1800B7C08
0x1800759c1  mov     rax, [rax]
0x1800759c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800759c9  mov     edi, eax
0x1800759cb  test    eax, eax
0x1800759cd  js      loc_180075BB5
0x1800759d3  mov     rcx, [rbp+57h+var_60]
0x1800759d7  mov     rax, [rcx]
0x1800759da  lea     rdx, [rbp+57h+arg_18]
0x1800759de  mov     rax, [rax+50h]
0x1800759e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800759e7  mov     rax, [rbx]
0x1800759ea  lea     rdx, [rbp+57h+var_28]
0x1800759ee  mov     rcx, rbx
0x1800759f1  mov     rax, [rax+20h]
0x1800759f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800759fa  mov     rcx, [rbp+57h+var_28]
0x1800759fe  mov     rax, [rcx]
0x180075a01  mov     r9d, 1D4C0h
0x180075a07  mov     r8d, [rbp+57h+arg_18]
0x180075a0b  mov     edx, 2
0x180075a10  mov     rax, [rax+20h]
0x180075a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075a19  mov     edi, eax
0x180075a1b  test    eax, eax
0x180075a1d  jns     loc_180075ADC
0x180075a23  mov     eax, cs:dword_1800DF020
0x180075a29  cmp     eax, 2
0x180075a2c  jbe     short loc_180075A6B
0x180075a2e  mov     [rbp+57h+var_70], edi
0x180075a31  movsxd  rax, [rbp+57h+arg_18]
0x180075a35  mov     [rbp+57h+var_68], rax
0x180075a39  lea     rax, aWaitforsession_2; "WaitForSessionState failed"
0x180075a40  mov     [rbp+57h+var_50], rax
0x180075a44  lea     rax, [rbp+57h+var_70]
0x180075a48  mov     [rsp+0B0h+var_80], rax
0x180075a4d  lea     rax, [rbp+57h+var_68]
0x180075a51  mov     [rsp+0B0h+var_88], rax
0x180075a56  lea     rax, [rbp+57h+var_50]
0x180075a5a  mov     [rsp+0B0h+var_90], rax
0x180075a5f  lea     rdx, word_1800CB596
0x180075a66  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180075a6b  mov     rcx, [rbp+57h+var_58]
0x180075a6f  mov     rax, [rcx]
0x180075a72  mov     edx, 4
0x180075a77  mov     rax, [rax+240h]
0x180075a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075a83  test    eax, eax
0x180075a85  jns     loc_180075BB5
0x180075a8b  mov     ecx, cs:dword_1800DF020
0x180075a91  cmp     ecx, 2
0x180075a94  jbe     loc_180075BB5
0x180075a9a  mov     [rbp+57h+var_70], eax
0x180075a9d  movsxd  rax, [rbp+57h+arg_18]
0x180075aa1  mov     [rbp+57h+var_68], rax
0x180075aa5  lea     rax, aLogoffexFailed_0; "LogoffEx failed"
0x180075aac  mov     [rbp+57h+var_50], rax
0x180075ab0  lea     rax, [rbp+57h+var_70]
0x180075ab4  mov     [rsp+0B0h+var_80], rax
0x180075ab9  lea     rax, [rbp+57h+var_68]
0x180075abd  mov     [rsp+0B0h+var_88], rax
0x180075ac2  lea     rax, [rbp+57h+var_50]
0x180075ac6  mov     [rsp+0B0h+var_90], rax
0x180075acb  lea     rdx, byte_1800CB553
0x180075ad2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180075ad7  jmp     loc_180075BB5
0x180075adc  mov     rcx, [rbp+57h+var_58]
0x180075ae0  mov     rax, [rcx]
0x180075ae3  xor     r9d, r9d
0x180075ae6  lea     edx, [r9+0Bh]
0x180075aea  mov     r8d, 20Ch
0x180075af0  mov     rax, [rax+210h]
0x180075af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075afc  mov     edi, eax
0x180075afe  test    eax, eax
0x180075b00  jns     short loc_180075B21
0x180075b02  mov     eax, cs:dword_1800DF020
0x180075b08  cmp     eax, 2
0x180075b0b  jbe     loc_180075BB5
0x180075b11  lea     rax, aDisconnectexFa; "DisconnectEx() failed"
0x180075b18  lea     rdx, unk_1800CB528
0x180075b1f  jmp     short loc_180075B97
0x180075b21  mov     rcx, [rbp+57h+var_58]
0x180075b25  mov     rax, [rcx]
0x180075b28  mov     r9d, 1
0x180075b2e  mov     r8d, 20Dh
0x180075b34  mov     rdx, [rbp+57h+var_40]
0x180075b38  mov     rax, [rax+218h]
0x180075b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075b44  mov     edi, eax
0x180075b46  test    eax, eax
0x180075b48  mov     eax, cs:dword_1800DF020
0x180075b4e  js      short loc_180075B84
0x180075b50  cmp     eax, 4
0x180075b53  jbe     short loc_180075B76
0x180075b55  lea     rax, aReconnectexSuc; "ReconnectEx() succeed"
0x180075b5c  mov     [rbp+57h+var_68], rax
0x180075b60  lea     rax, [rbp+57h+var_68]
0x180075b64  mov     [rsp+0B0h+var_90], rax
0x180075b69  lea     rdx, word_1800CB502
0x180075b70  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180075b75  nop
0x180075b76  lea     rcx, [rbp+57h+var_58]
0x180075b7a  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180075b7f  jmp     loc_180075E68
0x180075b84  cmp     eax, 2
0x180075b87  jbe     short loc_180075BB5
0x180075b89  lea     rax, aReconnectexFai; "ReconnectEx() failed"
0x180075b90  lea     rdx, byte_1800CB4D7
0x180075b97  mov     [rbp+57h+var_68], rax
0x180075b9b  lea     rax, [rbp+57h+var_70]
0x180075b9f  mov     [rsp+0B0h+var_88], rax
0x180075ba4  lea     rax, [rbp+57h+var_68]
0x180075ba8  mov     [rsp+0B0h+var_90], rax
0x180075bad  mov     [rbp+57h+var_70], edi
0x180075bb0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180075bb5  mov     eax, cs:dword_1800DF020
0x180075bbb  cmp     eax, 2
0x180075bbe  jbe     short loc_180075BED
0x180075bc0  mov     [rbp+57h+var_70], edi
0x180075bc3  lea     rax, aTempGlassSessi; "Temp. glass session reconnect failed"
0x180075bca  mov     [rbp+57h+var_68], rax
0x180075bce  lea     rax, [rbp+57h+var_70]
0x180075bd2  mov     [rsp+0B0h+var_88], rax
0x180075bd7  lea     rax, [rbp+57h+var_68]
0x180075bdb  mov     [rsp+0B0h+var_90], rax
0x180075be0  lea     rdx, dword_1800CB4AC
0x180075be7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180075bec  nop
0x180075bed  lea     rcx, [rbp+57h+var_58]
0x180075bf1  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180075bf6  jmp     loc_180075CBF
0x180075bfb  cmp     eax, 5
0x180075bfe  jbe     short loc_180075C20
0x180075c00  lea     rax, aTryingToSeeIfW; "Trying to see if we should switch to a "...
0x180075c07  mov     [rbp+57h+var_68], rax
0x180075c0b  lea     rax, [rbp+57h+var_68]
0x180075c0f  mov     [rsp+0B0h+var_90], rax
0x180075c14  lea     rdx, word_1800CB48A
0x180075c1b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180075c20  mov     rax, [rbx]
0x180075c23  mov     rcx, rbx
0x180075c26  mov     rax, [rax+38h]
0x180075c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075c2f  mov     edi, eax
0x180075c31  mov     ecx, cs:dword_1800DF020
0x180075c37  cmp     ecx, 5
0x180075c3a  jbe     short loc_180075C68
0x180075c3c  mov     [rbp+57h+var_70], eax
0x180075c3f  lea     rax, aSwitchtocaches_0; "SwitchToCacheSession finished"
0x180075c46  mov     [rbp+57h+var_68], rax
0x180075c4a  lea     rax, [rbp+57h+var_70]
0x180075c4e  mov     [rsp+0B0h+var_88], rax
0x180075c53  lea     rax, [rbp+57h+var_68]
0x180075c57  mov     [rsp+0B0h+var_90], rax
0x180075c5c  lea     rdx, byte_1800CB463
0x180075c63  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180075c68  mov     eax, cs:dword_1800DF020
0x180075c6e  test    edi, edi
0x180075c70  jnz     short loc_180075C8E
0x180075c72  cmp     eax, 4
0x180075c75  jbe     loc_180075E68
  ... truncated ...
```
