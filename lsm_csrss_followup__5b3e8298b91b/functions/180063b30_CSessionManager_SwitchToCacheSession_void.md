# CSessionManager::SwitchToCacheSession(void)

- ea: `0x180063b30`
- end: `0x180064135`
- name: `?SwitchToCacheSession@CSessionManager@@EEAAJXZ`
- size: `1541`
- prototype: `__int64 __fastcall(CSessionManager *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x180001ac0`
- `0x180008f64`
- `0x180024ce0`
- `0x180025070`
- `0x180025890`
- `0x180029110`
- `0x1800298d4`
- `0x180063b30`
- `0x180071d60`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180063caf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180063dc2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800640a6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180063caf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180063dc2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800640a6`

## string_xrefs

- `0x180063b58`: `SwitchToCacheSession was called, but it's not supported`
- `0x180063b87`: `Switching to cache session started`
- `0x180063cee`: `Checking state of cache session`
- `0x1800640c3`: `Throwing away cache session`
- `0x180063d82`: `Checking state of cache session in a loop`
- `0x180063df2`: `Cache session is bad, giving up.`
- `0x180063fa2`: `Going alternate reconnect path (no specialdiscon/specialrecon)`
- `0x180063fee`: `Disconnect failed on cache session (might be ok still)`
- `0x180064053`: `Finished Switch to Cache session (Alternate Reconnect)`
- `0x180063e57`: `Disconnecting cache session`
- `0x180063ead`: `DisconnectEx() failed on cache session. Returning S_FALSE`
- `0x180063ec5`: `About to Reconnect to cache session`
- `0x180063f2f`: `Finished Switching to Cache session (Reconnect)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSessionManager::SwitchToCacheSession(CSessionManager *this, __int64 a2, int a3, int a4)
{
  __int64 v6; // rcx
  unsigned int v7; // edi
  int InstanceOfGlassTerminalNew; // ecx
  int v9; // r8d
  int v10; // r9d
  int v11; // ebx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  int v18; // eax
  int v19; // ecx
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  const char *v23; // rax
  char *v24; // rdx
  struct ITerminal *v25; // rbx
  int v26; // esi
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  struct ITerminal *v30; // rbx
  int v31; // esi
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  const char *v38; // [rsp+40h] [rbp-9h] BYREF
  __int64 v39; // [rsp+48h] [rbp-1h] BYREF
  __int64 v40; // [rsp+50h] [rbp+7h] BYREF
  struct ITerminal *v41; // [rsp+58h] [rbp+Fh] BYREF
  struct ITSEventDispatcher *v42; // [rsp+60h] [rbp+17h] BYREF
  const char *v43; // [rsp+68h] [rbp+1Fh] BYREF
  _QWORD v44[6]; // [rsp+70h] [rbp+27h] BYREF
  const char *v45; // [rsp+B0h] [rbp+67h] BYREF
  int v46; // [rsp+B8h] [rbp+6Fh] BYREF
  const char *v47; // [rsp+C0h] [rbp+77h] BYREF
  const char *v48; // [rsp+C8h] [rbp+7Fh] BYREF

  if ( *((_DWORD *)this + 424) )
  {
    if ( (unsigned int)dword_1800DA020 > 4 )
    {
      v47 = "Switching to cache session started";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)this,
        (unsigned int)&byte_1800C2797,
        a3,
        a4,
        (__int64)&v47);
    }
    v44[0] = 0;
    v39 = 0;
    v6 = *((_QWORD *)this + 215);
    if ( v6 )
    {
      v42 = 0;
      v46 = 0;
      v41 = 0;
      v40 = 0;
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 80LL))(v6, &v46);
      CSessionManager::GetInstanceOfEventDispatcher(this, &v42);
      (***((void (__fastcall ****)(_QWORD, __int64 *, __int64 *))this + 215))(
        *((_QWORD *)this + 215),
        qword_1800ACB20,
        &v39);
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 104LL))(v39, &v40);
      while ( 1 )
      {
        InstanceOfGlassTerminalNew = CGlassTerminal::staticGetInstanceOfGlassTerminalNew(&v41);
        if ( InstanceOfGlassTerminalNew >= 0 )
          break;
        if ( (unsigned int)dword_1800DA020 > 2 )
        {
          LODWORD(v47) = InstanceOfGlassTerminalNew;
          v48 = "staticGetInstanceOfGlassTerminal failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            InstanceOfGlassTerminalNew,
            (unsigned int)&word_1800C274E,
            v9,
            v10,
            (__int64)&v48,
            (__int64)&v47);
        }
        Sleep(0x1388u);
      }
      v11 = 60;
      LODWORD(v45) = 0;
      (*(void (__fastcall **)(__int64, const char **))(*(_QWORD *)v39 + 88LL))(v39, &v45);
      if ( (unsigned int)dword_1800DA020 > 4 )
      {
        LODWORD(v47) = (_DWORD)v45;
        LODWORD(v48) = v46;
        v38 = "Checking state of cache session";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v12,
          (unsigned int)byte_1800C270D,
          v13,
          v14,
          (__int64)&v38,
          (__int64)&v48,
          (__int64)&v47);
      }
      v7 = 1;
      do
      {
        if ( (*(int (__fastcall **)(__int64, const char **))(*(_QWORD *)v39 + 88LL))(v39, &v45) < 0
          || (v17 = (int)v45, (((_DWORD)v45 - 6) & 0xFFFFFFFA) == 0) && (_DWORD)v45 != 7 )
        {
          Sleep(0x3E8u);
          if ( (unsigned int)dword_1800DA020 > 5 )
          {
            LODWORD(v47) = (_DWORD)v45;
            LODWORD(v48) = v46;
            v43 = "Throwing away cache session";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v35,
              (unsigned int)&dword_1800C26CC,
              v36,
              v37,
              (__int64)&v43,
              (__int64)&v48,
              (__int64)&v47);
          }
          goto LABEL_56;
        }
        --v11;
        if ( (unsigned int)v45 <= 0xD )
        {
          v18 = 12340;
          if ( _bittest(&v18, (unsigned int)v45) )
            break;
        }
        if ( (unsigned int)dword_1800DA020 > 4 )
        {
          LODWORD(v47) = v11;
          LODWORD(v48) = (_DWORD)v45;
          LODWORD(v38) = v46;
          v43 = "Checking state of cache session in a loop";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v45,
            (unsigned int)&byte_1800C267F,
            v15,
            v16,
            (__int64)&v43,
            (__int64)&v38,
            (__int64)&v48,
            (__int64)&v47);
        }
        Sleep(0x1F4u);
      }
      while ( v11 > 0 );
      if ( !v11 )
      {
        if ( (unsigned int)dword_1800DA020 > 4 )
        {
          LODWORD(v47) = 0;
          LODWORD(v48) = (_DWORD)v45;
          LODWORD(v38) = v46;
          v43 = "Cache session is bad, giving up.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v17,
            (unsigned int)word_1800C2632,
            v15,
            v16,
            (__int64)&v43,
            (__int64)&v38,
            (__int64)&v48,
            (__int64)&v47);
        }
        goto LABEL_56;
      }
      v19 = v40;
      if ( v40 && (unsigned int)IsCacheTerminal() )
      {
        if ( (unsigned int)dword_1800DA020 > 5 )
        {
          v47 = "Disconnecting cache session";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v19,
            (unsigned int)qword_1800C25A0,
            v15,
            v16,
            (__int64)&v47);
        }
        v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v39 + 528LL))(v39, 0, 524, 0);
        if ( v20 < 0 )
        {
          if ( (unsigned int)dword_1800DA020 <= 2 )
            goto LABEL_56;
          LODWORD(v47) = v20;
          v23 = "DisconnectEx() failed on cache session. Returning S_FALSE";
          v24 = byte_1800C2579;
LABEL_44:
          v48 = v23;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v20,
            (_DWORD)v24,
            v21,
            v22,
            (__int64)&v48,
            (__int64)&v47);
          goto LABEL_56;
        }
        if ( (unsigned int)dword_1800DA020 > 4 )
        {
          v47 = "About to Reconnect to cache session";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v20,
            (unsigned int)&byte_1800C2557,
            v21,
            v22,
            (__int64)&v47);
        }
        v25 = v41;
        v26 = (*(__int64 (__fastcall **)(__int64, struct ITerminal *, __int64, __int64))(*(_QWORD *)v39 + 536LL))(
                v39,
                v41,
                525,
                1);
        (*(void (__fastcall **)(struct ITerminal *))(*(_QWORD *)v25 + 8LL))(v25);
        if ( v26 < 0 )
        {
          if ( (unsigned int)dword_1800DA020 <= 2 )
            goto LABEL_56;
          LODWORD(v47) = v26;
          v23 = "Tried to reconnect and failed";
          v24 = byte_1800C2509;
          goto LABEL_44;
        }
        if ( (unsigned int)dword_1800DA020 > 4 )
        {
          LODWORD(v47) = v26;
          v48 = "Finished Switching to Cache session (Reconnect)";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)qword_1800C2530,
            v21,
            v22,
            (__int64)&v48,
            (__int64)&v47);
        }
LABEL_53:
        SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v40);
        SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v41);
        SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v42);
        v7 = 0;
        goto LABEL_57;
      }
      if ( (unsigned int)dword_1800DA020 > 4 )
      {
        v47 = "Going alternate reconnect path (no specialdiscon/specialrecon)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v19,
          (unsigned int)qword_1800C2610,
          v15,
          v16,
          (__int64)&v47);
      }
      if ( v40 )
      {
        v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v39 + 56LL))(v39, 0, 0);
        if ( (unsigned int)dword_1800DA020 > 5 )
        {
          LODWORD(v47) = v27;
          v48 = "Disconnect failed on cache session (might be ok still)";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v27,
            (unsigned int)byte_1800C25E9,
            v28,
            v29,
            (__int64)&v48,
            (__int64)&v47);
        }
      }
      v30 = v41;
      v31 = (*(__int64 (__fastcall **)(__int64, struct ITerminal *, __int64, __int64))(*(_QWORD *)v39 + 48LL))(
              v39,
              v41,
              1,
              1);
      (*(void (__fastcall **)(struct ITerminal *))(*(_QWORD *)v30 + 8LL))(v30);
      if ( (unsigned int)dword_1800DA020 > 4 )
      {
        LODWORD(v47) = v31;
        v48 = "Finished Switch to Cache session (Alternate Reconnect)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v32,
          (unsigned int)word_1800C25C2,
          v33,
          v34,
          (__int64)&v48,
          (__int64)&v47);
      }
      if ( v31 >= 0 )
        goto LABEL_53;
LABEL_56:
      SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v40);
      SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v41);
      SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v42);
    }
    else
    {
      if ( (unsigned int)dword_1800DA020 > 4 )
      {
        v47 = "Can't switch, there is no session";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          0,
          (unsigned int)byte_1800C2775,
          a3,
          a4,
          (__int64)&v47);
      }
      v7 = 1;
    }
LABEL_57:
    SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v39);
    SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(v44);
    return v7;
  }
  else
  {
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      v45 = "SwitchToCacheSession was called, but it's not supported";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)this,
        (unsigned int)byte_1800C27B9,
        a3,
        a4,
        (__int64)&v45);
    }
    return 50;
  }
}

```

## disassembly

```asm
0x180063b30  push    rbp
0x180063b32  push    rbx
0x180063b33  push    rsi
0x180063b34  push    rdi
0x180063b35  lea     rbp, [rsp-3Fh]
0x180063b3a  sub     rsp, 88h
0x180063b41  mov     rbx, rcx
0x180063b44  cmp     dword ptr [rcx+6A0h], 0
0x180063b4b  mov     eax, cs:dword_1800DA020
0x180063b51  jnz     short loc_180063B82
0x180063b53  cmp     eax, 2
0x180063b56  jbe     short loc_180063B78
0x180063b58  lea     rax, aSwitchtocaches; "SwitchToCacheSession was called, but it"...
0x180063b5f  mov     [rbp+57h+arg_0], rax
0x180063b63  lea     rax, [rbp+57h+arg_0]
0x180063b67  mov     [rsp+0A0h+var_80], rax
0x180063b6c  lea     rdx, byte_1800C27B9
0x180063b73  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180063b78  mov     eax, 32h ; '2'
0x180063b7d  jmp     loc_180064129
0x180063b82  cmp     eax, 4
0x180063b85  jbe     short loc_180063BA7
0x180063b87  lea     rax, aSwitchingToCac; "Switching to cache session started"
0x180063b8e  mov     [rbp+57h+arg_10], rax
0x180063b92  lea     rax, [rbp+57h+arg_10]
0x180063b96  mov     [rsp+0A0h+var_80], rax
0x180063b9b  lea     rdx, byte_1800C2797
0x180063ba2  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180063ba7  mov     [rbp+57h+var_30], 0
0x180063baf  mov     [rbp+57h+var_58], 0
0x180063bb7  mov     rcx, [rbx+6B8h]
0x180063bbe  test    rcx, rcx
0x180063bc1  jnz     short loc_180063BF8
0x180063bc3  mov     eax, cs:dword_1800DA020
0x180063bc9  cmp     eax, 4
0x180063bcc  jbe     short loc_180063BEE
0x180063bce  lea     rax, aCanTSwitchTher; "Can't switch, there is no session"
0x180063bd5  mov     [rbp+57h+arg_10], rax
0x180063bd9  lea     rax, [rbp+57h+arg_10]
0x180063bdd  mov     [rsp+0A0h+var_80], rax
0x180063be2  lea     rdx, byte_1800C2775
0x180063be9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180063bee  mov     edi, 1
0x180063bf3  jmp     loc_180064114
0x180063bf8  mov     [rbp+57h+var_40], 0
0x180063c00  mov     [rbp+57h+arg_8], 0
0x180063c07  mov     [rbp+57h+var_48], 0
0x180063c0f  mov     [rbp+57h+var_50], 0
0x180063c17  mov     rax, [rcx]
0x180063c1a  lea     rdx, [rbp+57h+arg_8]
0x180063c1e  mov     rax, [rax+50h]
0x180063c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063c27  lea     rdx, [rbp+57h+var_40]; struct ITSEventDispatcher **
0x180063c2b  mov     rcx, rbx; this
0x180063c2e  call    ?GetInstanceOfEventDispatcher@CSessionManager@@UEAAJPEAPEAUITSEventDispatcher@@@Z; CSessionManager::GetInstanceOfEventDispatcher(ITSEventDispatcher * *)
0x180063c33  mov     rcx, [rbx+6B8h]
0x180063c3a  mov     rax, [rcx]
0x180063c3d  lea     r8, [rbp+57h+var_58]
0x180063c41  lea     rdx, qword_1800ACB20
0x180063c48  mov     rax, [rax]
0x180063c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063c50  mov     rcx, [rbp+57h+var_58]
0x180063c54  mov     rax, [rcx]
0x180063c57  lea     rdx, [rbp+57h+var_50]
0x180063c5b  mov     rax, [rax+68h]
0x180063c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063c64  lea     rcx, [rbp+57h+var_48]; struct ITerminal **
0x180063c68  call    ?staticGetInstanceOfGlassTerminalNew@CGlassTerminal@@SAJPEAPEAUITerminal@@@Z; CGlassTerminal::staticGetInstanceOfGlassTerminalNew(ITerminal * *)
0x180063c6d  mov     ecx, eax
0x180063c6f  test    eax, eax
0x180063c71  jns     short loc_180063CB7
0x180063c73  mov     eax, cs:dword_1800DA020
0x180063c79  cmp     eax, 2
0x180063c7c  jbe     short loc_180063CAA
0x180063c7e  mov     dword ptr [rbp+57h+arg_10], ecx
0x180063c81  lea     rax, aStaticgetinsta; "staticGetInstanceOfGlassTerminal failed"
0x180063c88  mov     [rbp+57h+arg_18], rax
0x180063c8c  lea     rax, [rbp+57h+arg_10]
0x180063c90  mov     [rsp+0A0h+var_78], rax
0x180063c95  lea     rax, [rbp+57h+arg_18]
0x180063c99  mov     [rsp+0A0h+var_80], rax
0x180063c9e  lea     rdx, word_1800C274E
0x180063ca5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180063caa  mov     ecx, 1388h; dwMilliseconds
0x180063caf  call    cs:__imp_Sleep
0x180063cb5  jmp     short loc_180063C64
0x180063cb7  mov     ebx, 3Ch ; '<'
0x180063cbc  mov     dword ptr [rbp+57h+arg_0], 0
0x180063cc3  mov     rcx, [rbp+57h+var_58]
0x180063cc7  mov     rax, [rcx]
0x180063cca  lea     rdx, [rbp+57h+arg_0]
0x180063cce  mov     rax, [rax+58h]
0x180063cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063cd7  mov     eax, cs:dword_1800DA020
0x180063cdd  cmp     eax, 4
0x180063ce0  jbe     short loc_180063D20
0x180063ce2  mov     eax, dword ptr [rbp+57h+arg_0]
0x180063ce5  mov     dword ptr [rbp+57h+arg_10], eax
0x180063ce8  mov     eax, [rbp+57h+arg_8]
0x180063ceb  mov     dword ptr [rbp+57h+arg_18], eax
0x180063cee  lea     rax, aCheckingStateO_0; "Checking state of cache session"
0x180063cf5  mov     [rbp+57h+var_60], rax
0x180063cf9  lea     rax, [rbp+57h+arg_10]
0x180063cfd  mov     [rsp+0A0h+var_70], rax
0x180063d02  lea     rax, [rbp+57h+arg_18]
0x180063d06  mov     [rsp+0A0h+var_78], rax
0x180063d0b  lea     rax, [rbp+57h+var_60]
0x180063d0f  mov     [rsp+0A0h+var_80], rax
0x180063d14  lea     rdx, byte_1800C270D
0x180063d1b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180063d20  mov     edi, 1
0x180063d25  mov     rcx, [rbp+57h+var_58]
0x180063d29  mov     rax, [rcx]
0x180063d2c  lea     rdx, [rbp+57h+arg_0]
0x180063d30  mov     rax, [rax+58h]
0x180063d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063d39  test    eax, eax
0x180063d3b  js      loc_1800640A1
0x180063d41  mov     ecx, dword ptr [rbp+57h+arg_0]
0x180063d44  lea     eax, [rcx-6]
0x180063d47  test    eax, 0FFFFFFFAh
0x180063d4c  jnz     short loc_180063D57
0x180063d4e  cmp     ecx, 7
0x180063d51  jnz     loc_1800640A1
0x180063d57  sub     ebx, edi
0x180063d59  cmp     ecx, 0Dh
0x180063d5c  ja      short loc_180063D68
0x180063d5e  mov     eax, 3034h
0x180063d63  bt      eax, ecx
0x180063d66  jb      short loc_180063DD0
0x180063d68  mov     eax, cs:dword_1800DA020
0x180063d6e  cmp     eax, 4
0x180063d71  jbe     short loc_180063DBD
0x180063d73  mov     dword ptr [rbp+57h+arg_10], ebx
0x180063d76  mov     eax, dword ptr [rbp+57h+arg_0]
0x180063d79  mov     dword ptr [rbp+57h+arg_18], eax
0x180063d7c  mov     eax, [rbp+57h+arg_8]
0x180063d7f  mov     dword ptr [rbp+57h+var_60], eax
0x180063d82  lea     rax, aCheckingStateO; "Checking state of cache session in a lo"...
0x180063d89  mov     [rbp+57h+var_38], rax
0x180063d8d  lea     rax, [rbp+57h+arg_10]
0x180063d91  mov     [rsp+0A0h+var_68], rax
0x180063d96  lea     rax, [rbp+57h+arg_18]
0x180063d9a  mov     [rsp+0A0h+var_70], rax
0x180063d9f  lea     rax, [rbp+57h+var_60]
0x180063da3  mov     [rsp+0A0h+var_78], rax
0x180063da8  lea     rax, [rbp+57h+var_38]
0x180063dac  mov     [rsp+0A0h+var_80], rax
0x180063db1  lea     rdx, byte_1800C267F
0x180063db8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180063dbd  mov     ecx, 1F4h; dwMilliseconds
0x180063dc2  call    cs:__imp_Sleep
0x180063dc8  test    ebx, ebx
0x180063dca  jg      loc_180063D25
0x180063dd0  test    ebx, ebx
0x180063dd2  jnz     short loc_180063E32
0x180063dd4  mov     eax, cs:dword_1800DA020
0x180063dda  cmp     eax, 4
0x180063ddd  jbe     loc_1800640F6
0x180063de3  mov     dword ptr [rbp+57h+arg_10], ebx
0x180063de6  mov     eax, dword ptr [rbp+57h+arg_0]
0x180063de9  mov     dword ptr [rbp+57h+arg_18], eax
0x180063dec  mov     eax, [rbp+57h+arg_8]
0x180063def  mov     dword ptr [rbp+57h+var_60], eax
0x180063df2  lea     rax, aCacheSessionIs; "Cache session is bad, giving up."
0x180063df9  mov     [rbp+57h+var_38], rax
0x180063dfd  lea     rax, [rbp+57h+arg_10]
0x180063e01  mov     [rsp+0A0h+var_68], rax
0x180063e06  lea     rax, [rbp+57h+arg_18]
0x180063e0a  mov     [rsp+0A0h+var_70], rax
0x180063e0f  lea     rax, [rbp+57h+var_60]
0x180063e13  mov     [rsp+0A0h+var_78], rax
0x180063e18  lea     rax, [rbp+57h+var_38]
0x180063e1c  mov     [rsp+0A0h+var_80], rax
0x180063e21  lea     rdx, word_1800C2632
0x180063e28  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180063e2d  jmp     loc_1800640F6
0x180063e32  mov     rcx, [rbp+57h+var_50]
0x180063e36  test    rcx, rcx
0x180063e39  jz      loc_180063F97
0x180063e3f  call    IsCacheTerminal
0x180063e44  test    eax, eax
0x180063e46  jz      loc_180063F97
0x180063e4c  mov     eax, cs:dword_1800DA020
0x180063e52  cmp     eax, 5
0x180063e55  jbe     short loc_180063E77
0x180063e57  lea     rax, aDisconnectingC; "Disconnecting cache session"
0x180063e5e  mov     [rbp+57h+arg_10], rax
0x180063e62  lea     rax, [rbp+57h+arg_10]
0x180063e66  mov     [rsp+0A0h+var_80], rax
0x180063e6b  lea     rdx, qword_1800C25A0
0x180063e72  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180063e77  mov     rcx, [rbp+57h+var_58]
0x180063e7b  mov     rax, [rcx]
0x180063e7e  xor     r9d, r9d
0x180063e81  xor     edx, edx
0x180063e83  mov     r8d, 20Ch
0x180063e89  mov     rax, [rax+210h]
0x180063e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063e95  mov     ecx, eax
0x180063e97  test    eax, eax
0x180063e99  mov     eax, cs:dword_1800DA020
0x180063e9f  jns     short loc_180063EC0
0x180063ea1  cmp     eax, 2
0x180063ea4  jbe     loc_1800640F6
0x180063eaa  mov     dword ptr [rbp+57h+arg_10], ecx
0x180063ead  lea     rax, aDisconnectexFa_0; "DisconnectEx() failed on cache session."...
0x180063eb4  lea     rdx, byte_1800C2579
0x180063ebb  jmp     loc_180063F77
0x180063ec0  cmp     eax, 4
0x180063ec3  jbe     short loc_180063EE5
0x180063ec5  lea     rax, aAboutToReconne; "About to Reconnect to cache session"
0x180063ecc  mov     [rbp+57h+arg_10], rax
0x180063ed0  lea     rax, [rbp+57h+arg_10]
0x180063ed4  mov     [rsp+0A0h+var_80], rax
0x180063ed9  lea     rdx, byte_1800C2557
0x180063ee0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180063ee5  mov     rcx, [rbp+57h+var_58]
0x180063ee9  mov     rax, [rcx]
0x180063eec  mov     r9d, edi
0x180063eef  mov     r8d, 20Dh
0x180063ef5  mov     rbx, [rbp+57h+var_48]
0x180063ef9  mov     rdx, rbx
0x180063efc  mov     rax, [rax+218h]
0x180063f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f08  mov     esi, eax
0x180063f0a  mov     rax, [rbx]
0x180063f0d  mov     rcx, rbx
0x180063f10  mov     rax, [rax+8]
0x180063f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f19  mov     eax, cs:dword_1800DA020
0x180063f1f  test    esi, esi
0x180063f21  js      short loc_180063F5D
0x180063f23  cmp     eax, 4
0x180063f26  jbe     loc_180064080
0x180063f2c  mov     dword ptr [rbp+57h+arg_10], esi
0x180063f2f  lea     rax, aFinishedSwitch_0; "Finished Switching to Cache session (Re"...
0x180063f36  mov     [rbp+57h+arg_18], rax
0x180063f3a  lea     rax, [rbp+57h+arg_10]
0x180063f3e  mov     [rsp+0A0h+var_78], rax
0x180063f43  lea     rax, [rbp+57h+arg_18]
0x180063f47  mov     [rsp+0A0h+var_80], rax
0x180063f4c  lea     rdx, qword_1800C2530
0x180063f53  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180063f58  jmp     loc_180064080
0x180063f5d  cmp     eax, 2
0x180063f60  jbe     loc_1800640F6
0x180063f66  mov     dword ptr [rbp+57h+arg_10], esi
0x180063f69  lea     rax, aTriedToReconne; "Tried to reconnect and failed"
0x180063f70  lea     rdx, byte_1800C2509
0x180063f77  mov     [rbp+57h+arg_18], rax
0x180063f7b  lea     rax, [rbp+57h+arg_10]
0x180063f7f  mov     [rsp+0A0h+var_78], rax
0x180063f84  lea     rax, [rbp+57h+arg_18]
0x180063f88  mov     [rsp+0A0h+var_80], rax
0x180063f8d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180063f92  jmp     loc_1800640F6
0x180063f97  mov     eax, cs:dword_1800DA020
0x180063f9d  cmp     eax, 4
0x180063fa0  jbe     short loc_180063FC2
0x180063fa2  lea     rax, aGoingAlternate; "Going alternate reconnect path (no spec"...
0x180063fa9  mov     [rbp+57h+arg_10], rax
0x180063fad  lea     rax, [rbp+57h+arg_10]
0x180063fb1  mov     [rsp+0A0h+var_80], rax
0x180063fb6  lea     rdx, qword_1800C2610
0x180063fbd  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180063fc2  cmp     [rbp+57h+var_50], 0
0x180063fc7  jz      short loc_180064017
0x180063fc9  mov     rcx, [rbp+57h+var_58]
0x180063fcd  mov     rax, [rcx]
0x180063fd0  xor     r8d, r8d
0x180063fd3  xor     edx, edx
0x180063fd5  mov     rax, [rax+38h]
0x180063fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063fde  mov     ecx, eax
0x180063fe0  mov     eax, cs:dword_1800DA020
0x180063fe6  cmp     eax, 5
0x180063fe9  jbe     short loc_180064017
0x180063feb  mov     dword ptr [rbp+57h+arg_10], ecx
0x180063fee  lea     rax, aDisconnectFail; "Disconnect failed on cache session (mig"...
0x180063ff5  mov     [rbp+57h+arg_18], rax
0x180063ff9  lea     rax, [rbp+57h+arg_10]
0x180063ffd  mov     [rsp+0A0h+var_78], rax
0x180064002  lea     rax, [rbp+57h+arg_18]
0x180064006  mov     [rsp+0A0h+var_80], rax
0x18006400b  lea     rdx, byte_1800C25E9
0x180064012  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180064017  mov     rcx, [rbp+57h+var_58]
0x18006401b  mov     rax, [rcx]
0x18006401e  mov     r9d, edi
0x180064021  mov     r8d, edi
0x180064024  mov     rbx, [rbp+57h+var_48]
0x180064028  mov     rdx, rbx
0x18006402b  mov     rax, [rax+30h]
0x18006402f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064034  mov     esi, eax
0x180064036  mov     rax, [rbx]
0x180064039  mov     rcx, rbx
0x18006403c  mov     rax, [rax+8]
0x180064040  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
