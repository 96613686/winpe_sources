# CSessionManager::SwitchToCacheSession(void)

- ea: `0x180067750`
- end: `0x180067d68`
- name: `?SwitchToCacheSession@CSessionManager@@EEAAJXZ`
- size: `1560`
- prototype: `__int64 __fastcall(CSessionManager *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x180001ad0`
- `0x18000c684`
- `0x180026c8c`
- `0x18002701c`
- `0x18002772c`
- `0x18002b300`
- `0x18002bc84`
- `0x180067750`
- `0x180075eb8`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800678cf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800679e8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180067cd2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800678cf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800679e8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180067cd2`

## string_xrefs

- `0x180067778`: `SwitchToCacheSession was called, but it's not supported`
- `0x1800677a7`: `Switching to cache session started`
- `0x180067914`: `Checking state of cache session`
- `0x180067cf5`: `Throwing away cache session`
- `0x1800679a8`: `Checking state of cache session in a loop`
- `0x180067a1e`: `Cache session is bad, giving up.`
- `0x180067bce`: `Going alternate reconnect path (no specialdiscon/specialrecon)`
- `0x180067c1a`: `Disconnect failed on cache session (might be ok still)`
- `0x180067c7f`: `Finished Switch to Cache session (Alternate Reconnect)`
- `0x180067a83`: `Disconnecting cache session`
- `0x180067ad9`: `DisconnectEx() failed on cache session. Returning S_FALSE`
- `0x180067af1`: `About to Reconnect to cache session`
- `0x180067b5b`: `Finished Switching to Cache session (Reconnect)`

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
    if ( (unsigned int)dword_1800DF020 > 4 )
    {
      v47 = "Switching to cache session started";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)this,
        (unsigned int)&byte_1800C791F,
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
        qword_1800B1CB0,
        &v39);
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 104LL))(v39, &v40);
      while ( 1 )
      {
        InstanceOfGlassTerminalNew = CGlassTerminal::staticGetInstanceOfGlassTerminalNew(&v41);
        if ( InstanceOfGlassTerminalNew >= 0 )
          break;
        if ( (unsigned int)dword_1800DF020 > 2 )
        {
          LODWORD(v47) = InstanceOfGlassTerminalNew;
          v48 = "staticGetInstanceOfGlassTerminal failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            InstanceOfGlassTerminalNew,
            (unsigned int)&word_1800C78D6,
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
      if ( (unsigned int)dword_1800DF020 > 4 )
      {
        LODWORD(v47) = (_DWORD)v45;
        LODWORD(v48) = v46;
        v38 = "Checking state of cache session";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v12,
          (unsigned int)byte_1800C7895,
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
          if ( (unsigned int)dword_1800DF020 > 5 )
          {
            LODWORD(v47) = (_DWORD)v45;
            LODWORD(v48) = v46;
            v43 = "Throwing away cache session";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v35,
              (unsigned int)&dword_1800C7854,
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
        if ( (unsigned int)dword_1800DF020 > 4 )
        {
          LODWORD(v47) = v11;
          LODWORD(v48) = (_DWORD)v45;
          LODWORD(v38) = v46;
          v43 = "Checking state of cache session in a loop";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v45,
            (unsigned int)&byte_1800C7807,
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
        if ( (unsigned int)dword_1800DF020 > 4 )
        {
          LODWORD(v47) = 0;
          LODWORD(v48) = (_DWORD)v45;
          LODWORD(v38) = v46;
          v43 = "Cache session is bad, giving up.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v17,
            (unsigned int)word_1800C77BA,
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
        if ( (unsigned int)dword_1800DF020 > 5 )
        {
          v47 = "Disconnecting cache session";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v19,
            (unsigned int)qword_1800C7728,
            v15,
            v16,
            (__int64)&v47);
        }
        v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v39 + 528LL))(v39, 0, 524, 0);
        if ( v20 < 0 )
        {
          if ( (unsigned int)dword_1800DF020 <= 2 )
            goto LABEL_56;
          LODWORD(v47) = v20;
          v23 = "DisconnectEx() failed on cache session. Returning S_FALSE";
          v24 = byte_1800C7701;
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
        if ( (unsigned int)dword_1800DF020 > 4 )
        {
          v47 = "About to Reconnect to cache session";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v20,
            (unsigned int)&byte_1800C76DF,
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
          if ( (unsigned int)dword_1800DF020 <= 2 )
            goto LABEL_56;
          LODWORD(v47) = v26;
          v23 = "Tried to reconnect and failed";
          v24 = byte_1800C7691;
          goto LABEL_44;
        }
        if ( (unsigned int)dword_1800DF020 > 4 )
        {
          LODWORD(v47) = v26;
          v48 = "Finished Switching to Cache session (Reconnect)";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)qword_1800C76B8,
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
      if ( (unsigned int)dword_1800DF020 > 4 )
      {
        v47 = "Going alternate reconnect path (no specialdiscon/specialrecon)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v19,
          (unsigned int)qword_1800C7798,
          v15,
          v16,
          (__int64)&v47);
      }
      if ( v40 )
      {
        v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v39 + 56LL))(v39, 0, 0);
        if ( (unsigned int)dword_1800DF020 > 5 )
        {
          LODWORD(v47) = v27;
          v48 = "Disconnect failed on cache session (might be ok still)";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v27,
            (unsigned int)byte_1800C7771,
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
      if ( (unsigned int)dword_1800DF020 > 4 )
      {
        LODWORD(v47) = v31;
        v48 = "Finished Switch to Cache session (Alternate Reconnect)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v32,
          (unsigned int)word_1800C774A,
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
      if ( (unsigned int)dword_1800DF020 > 4 )
      {
        v47 = "Can't switch, there is no session";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          0,
          (unsigned int)byte_1800C78FD,
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
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      v45 = "SwitchToCacheSession was called, but it's not supported";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)this,
        (unsigned int)byte_1800C7941,
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
0x180067750  push    rbp
0x180067752  push    rbx
0x180067753  push    rsi
0x180067754  push    rdi
0x180067755  lea     rbp, [rsp-3Fh]
0x18006775a  sub     rsp, 88h
0x180067761  mov     rbx, rcx
0x180067764  cmp     dword ptr [rcx+6A0h], 0
0x18006776b  mov     eax, cs:dword_1800DF020
0x180067771  jnz     short loc_1800677A2
0x180067773  cmp     eax, 2
0x180067776  jbe     short loc_180067798
0x180067778  lea     rax, aSwitchtocaches; "SwitchToCacheSession was called, but it"...
0x18006777f  mov     [rbp+57h+arg_0], rax
0x180067783  lea     rax, [rbp+57h+arg_0]
0x180067787  mov     [rsp+0A0h+var_80], rax
0x18006778c  lea     rdx, byte_1800C7941
0x180067793  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180067798  mov     eax, 32h ; '2'
0x18006779d  jmp     loc_180067D5B
0x1800677a2  cmp     eax, 4
0x1800677a5  jbe     short loc_1800677C7
0x1800677a7  lea     rax, aSwitchingToCac; "Switching to cache session started"
0x1800677ae  mov     [rbp+57h+arg_10], rax
0x1800677b2  lea     rax, [rbp+57h+arg_10]
0x1800677b6  mov     [rsp+0A0h+var_80], rax
0x1800677bb  lea     rdx, byte_1800C791F
0x1800677c2  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800677c7  mov     [rbp+57h+var_30], 0
0x1800677cf  mov     [rbp+57h+var_58], 0
0x1800677d7  mov     rcx, [rbx+6B8h]
0x1800677de  test    rcx, rcx
0x1800677e1  jnz     short loc_180067818
0x1800677e3  mov     eax, cs:dword_1800DF020
0x1800677e9  cmp     eax, 4
0x1800677ec  jbe     short loc_18006780E
0x1800677ee  lea     rax, aCanTSwitchTher; "Can't switch, there is no session"
0x1800677f5  mov     [rbp+57h+arg_10], rax
0x1800677f9  lea     rax, [rbp+57h+arg_10]
0x1800677fd  mov     [rsp+0A0h+var_80], rax
0x180067802  lea     rdx, byte_1800C78FD
0x180067809  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006780e  mov     edi, 1
0x180067813  jmp     loc_180067D46
0x180067818  mov     [rbp+57h+var_40], 0
0x180067820  mov     [rbp+57h+arg_8], 0
0x180067827  mov     [rbp+57h+var_48], 0
0x18006782f  mov     [rbp+57h+var_50], 0
0x180067837  mov     rax, [rcx]
0x18006783a  lea     rdx, [rbp+57h+arg_8]
0x18006783e  mov     rax, [rax+50h]
0x180067842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067847  lea     rdx, [rbp+57h+var_40]; struct ITSEventDispatcher **
0x18006784b  mov     rcx, rbx; this
0x18006784e  call    ?GetInstanceOfEventDispatcher@CSessionManager@@UEAAJPEAPEAUITSEventDispatcher@@@Z; CSessionManager::GetInstanceOfEventDispatcher(ITSEventDispatcher * *)
0x180067853  mov     rcx, [rbx+6B8h]
0x18006785a  mov     rax, [rcx]
0x18006785d  lea     r8, [rbp+57h+var_58]
0x180067861  lea     rdx, qword_1800B1CB0
0x180067868  mov     rax, [rax]
0x18006786b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067870  mov     rcx, [rbp+57h+var_58]
0x180067874  mov     rax, [rcx]
0x180067877  lea     rdx, [rbp+57h+var_50]
0x18006787b  mov     rax, [rax+68h]
0x18006787f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067884  lea     rcx, [rbp+57h+var_48]; struct ITerminal **
0x180067888  call    ?staticGetInstanceOfGlassTerminalNew@CGlassTerminal@@SAJPEAPEAUITerminal@@@Z; CGlassTerminal::staticGetInstanceOfGlassTerminalNew(ITerminal * *)
0x18006788d  mov     ecx, eax
0x18006788f  test    eax, eax
0x180067891  jns     short loc_1800678DD
0x180067893  mov     eax, cs:dword_1800DF020
0x180067899  cmp     eax, 2
0x18006789c  jbe     short loc_1800678CA
0x18006789e  mov     dword ptr [rbp+57h+arg_10], ecx
0x1800678a1  lea     rax, aStaticgetinsta; "staticGetInstanceOfGlassTerminal failed"
0x1800678a8  mov     [rbp+57h+arg_18], rax
0x1800678ac  lea     rax, [rbp+57h+arg_10]
0x1800678b0  mov     [rsp+0A0h+var_78], rax
0x1800678b5  lea     rax, [rbp+57h+arg_18]
0x1800678b9  mov     [rsp+0A0h+var_80], rax
0x1800678be  lea     rdx, word_1800C78D6
0x1800678c5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800678ca  mov     ecx, 1388h; dwMilliseconds
0x1800678cf  call    cs:__imp_Sleep
0x1800678d6  nop     dword ptr [rax+rax+00h]
0x1800678db  jmp     short loc_180067884
0x1800678dd  mov     ebx, 3Ch ; '<'
0x1800678e2  mov     dword ptr [rbp+57h+arg_0], 0
0x1800678e9  mov     rcx, [rbp+57h+var_58]
0x1800678ed  mov     rax, [rcx]
0x1800678f0  lea     rdx, [rbp+57h+arg_0]
0x1800678f4  mov     rax, [rax+58h]
0x1800678f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800678fd  mov     eax, cs:dword_1800DF020
0x180067903  cmp     eax, 4
0x180067906  jbe     short loc_180067946
0x180067908  mov     eax, dword ptr [rbp+57h+arg_0]
0x18006790b  mov     dword ptr [rbp+57h+arg_10], eax
0x18006790e  mov     eax, [rbp+57h+arg_8]
0x180067911  mov     dword ptr [rbp+57h+arg_18], eax
0x180067914  lea     rax, aCheckingStateO_0; "Checking state of cache session"
0x18006791b  mov     [rbp+57h+var_60], rax
0x18006791f  lea     rax, [rbp+57h+arg_10]
0x180067923  mov     [rsp+0A0h+var_70], rax
0x180067928  lea     rax, [rbp+57h+arg_18]
0x18006792c  mov     [rsp+0A0h+var_78], rax
0x180067931  lea     rax, [rbp+57h+var_60]
0x180067935  mov     [rsp+0A0h+var_80], rax
0x18006793a  lea     rdx, byte_1800C7895
0x180067941  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180067946  mov     edi, 1
0x18006794b  mov     rcx, [rbp+57h+var_58]
0x18006794f  mov     rax, [rcx]
0x180067952  lea     rdx, [rbp+57h+arg_0]
0x180067956  mov     rax, [rax+58h]
0x18006795a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006795f  test    eax, eax
0x180067961  js      loc_180067CCD
0x180067967  mov     ecx, dword ptr [rbp+57h+arg_0]
0x18006796a  lea     eax, [rcx-6]
0x18006796d  test    eax, 0FFFFFFFAh
0x180067972  jnz     short loc_18006797D
0x180067974  cmp     ecx, 7
0x180067977  jnz     loc_180067CCD
0x18006797d  sub     ebx, edi
0x18006797f  cmp     ecx, 0Dh
0x180067982  ja      short loc_18006798E
0x180067984  mov     eax, 3034h
0x180067989  bt      eax, ecx
0x18006798c  jb      short loc_1800679FC
0x18006798e  mov     eax, cs:dword_1800DF020
0x180067994  cmp     eax, 4
0x180067997  jbe     short loc_1800679E3
0x180067999  mov     dword ptr [rbp+57h+arg_10], ebx
0x18006799c  mov     eax, dword ptr [rbp+57h+arg_0]
0x18006799f  mov     dword ptr [rbp+57h+arg_18], eax
0x1800679a2  mov     eax, [rbp+57h+arg_8]
0x1800679a5  mov     dword ptr [rbp+57h+var_60], eax
0x1800679a8  lea     rax, aCheckingStateO; "Checking state of cache session in a lo"...
0x1800679af  mov     [rbp+57h+var_38], rax
0x1800679b3  lea     rax, [rbp+57h+arg_10]
0x1800679b7  mov     [rsp+0A0h+var_68], rax
0x1800679bc  lea     rax, [rbp+57h+arg_18]
0x1800679c0  mov     [rsp+0A0h+var_70], rax
0x1800679c5  lea     rax, [rbp+57h+var_60]
0x1800679c9  mov     [rsp+0A0h+var_78], rax
0x1800679ce  lea     rax, [rbp+57h+var_38]
0x1800679d2  mov     [rsp+0A0h+var_80], rax
0x1800679d7  lea     rdx, byte_1800C7807
0x1800679de  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800679e3  mov     ecx, 1F4h; dwMilliseconds
0x1800679e8  call    cs:__imp_Sleep
0x1800679ef  nop     dword ptr [rax+rax+00h]
0x1800679f4  test    ebx, ebx
0x1800679f6  jg      loc_18006794B
0x1800679fc  test    ebx, ebx
0x1800679fe  jnz     short loc_180067A5E
0x180067a00  mov     eax, cs:dword_1800DF020
0x180067a06  cmp     eax, 4
0x180067a09  jbe     loc_180067D28
0x180067a0f  mov     dword ptr [rbp+57h+arg_10], ebx
0x180067a12  mov     eax, dword ptr [rbp+57h+arg_0]
0x180067a15  mov     dword ptr [rbp+57h+arg_18], eax
0x180067a18  mov     eax, [rbp+57h+arg_8]
0x180067a1b  mov     dword ptr [rbp+57h+var_60], eax
0x180067a1e  lea     rax, aCacheSessionIs; "Cache session is bad, giving up."
0x180067a25  mov     [rbp+57h+var_38], rax
0x180067a29  lea     rax, [rbp+57h+arg_10]
0x180067a2d  mov     [rsp+0A0h+var_68], rax
0x180067a32  lea     rax, [rbp+57h+arg_18]
0x180067a36  mov     [rsp+0A0h+var_70], rax
0x180067a3b  lea     rax, [rbp+57h+var_60]
0x180067a3f  mov     [rsp+0A0h+var_78], rax
0x180067a44  lea     rax, [rbp+57h+var_38]
0x180067a48  mov     [rsp+0A0h+var_80], rax
0x180067a4d  lea     rdx, word_1800C77BA
0x180067a54  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180067a59  jmp     loc_180067D28
0x180067a5e  mov     rcx, [rbp+57h+var_50]
0x180067a62  test    rcx, rcx
0x180067a65  jz      loc_180067BC3
0x180067a6b  call    IsCacheTerminal
0x180067a70  test    eax, eax
0x180067a72  jz      loc_180067BC3
0x180067a78  mov     eax, cs:dword_1800DF020
0x180067a7e  cmp     eax, 5
0x180067a81  jbe     short loc_180067AA3
0x180067a83  lea     rax, aDisconnectingC; "Disconnecting cache session"
0x180067a8a  mov     [rbp+57h+arg_10], rax
0x180067a8e  lea     rax, [rbp+57h+arg_10]
0x180067a92  mov     [rsp+0A0h+var_80], rax
0x180067a97  lea     rdx, qword_1800C7728
0x180067a9e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180067aa3  mov     rcx, [rbp+57h+var_58]
0x180067aa7  mov     rax, [rcx]
0x180067aaa  xor     r9d, r9d
0x180067aad  xor     edx, edx
0x180067aaf  mov     r8d, 20Ch
0x180067ab5  mov     rax, [rax+210h]
0x180067abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ac1  mov     ecx, eax
0x180067ac3  test    eax, eax
0x180067ac5  mov     eax, cs:dword_1800DF020
0x180067acb  jns     short loc_180067AEC
0x180067acd  cmp     eax, 2
0x180067ad0  jbe     loc_180067D28
0x180067ad6  mov     dword ptr [rbp+57h+arg_10], ecx
0x180067ad9  lea     rax, aDisconnectexFa_0; "DisconnectEx() failed on cache session."...
0x180067ae0  lea     rdx, byte_1800C7701
0x180067ae7  jmp     loc_180067BA3
0x180067aec  cmp     eax, 4
0x180067aef  jbe     short loc_180067B11
0x180067af1  lea     rax, aAboutToReconne; "About to Reconnect to cache session"
0x180067af8  mov     [rbp+57h+arg_10], rax
0x180067afc  lea     rax, [rbp+57h+arg_10]
0x180067b00  mov     [rsp+0A0h+var_80], rax
0x180067b05  lea     rdx, byte_1800C76DF
0x180067b0c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180067b11  mov     rcx, [rbp+57h+var_58]
0x180067b15  mov     rax, [rcx]
0x180067b18  mov     r9d, edi
0x180067b1b  mov     r8d, 20Dh
0x180067b21  mov     rbx, [rbp+57h+var_48]
0x180067b25  mov     rdx, rbx
0x180067b28  mov     rax, [rax+218h]
0x180067b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b34  mov     esi, eax
0x180067b36  mov     rax, [rbx]
0x180067b39  mov     rcx, rbx
0x180067b3c  mov     rax, [rax+8]
0x180067b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b45  mov     eax, cs:dword_1800DF020
0x180067b4b  test    esi, esi
0x180067b4d  js      short loc_180067B89
0x180067b4f  cmp     eax, 4
0x180067b52  jbe     loc_180067CAC
0x180067b58  mov     dword ptr [rbp+57h+arg_10], esi
0x180067b5b  lea     rax, aFinishedSwitch_0; "Finished Switching to Cache session (Re"...
0x180067b62  mov     [rbp+57h+arg_18], rax
0x180067b66  lea     rax, [rbp+57h+arg_10]
0x180067b6a  mov     [rsp+0A0h+var_78], rax
0x180067b6f  lea     rax, [rbp+57h+arg_18]
0x180067b73  mov     [rsp+0A0h+var_80], rax
0x180067b78  lea     rdx, qword_1800C76B8
0x180067b7f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180067b84  jmp     loc_180067CAC
0x180067b89  cmp     eax, 2
0x180067b8c  jbe     loc_180067D28
0x180067b92  mov     dword ptr [rbp+57h+arg_10], esi
0x180067b95  lea     rax, aTriedToReconne; "Tried to reconnect and failed"
0x180067b9c  lea     rdx, byte_1800C7691
0x180067ba3  mov     [rbp+57h+arg_18], rax
0x180067ba7  lea     rax, [rbp+57h+arg_10]
0x180067bab  mov     [rsp+0A0h+var_78], rax
0x180067bb0  lea     rax, [rbp+57h+arg_18]
0x180067bb4  mov     [rsp+0A0h+var_80], rax
0x180067bb9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180067bbe  jmp     loc_180067D28
0x180067bc3  mov     eax, cs:dword_1800DF020
0x180067bc9  cmp     eax, 4
0x180067bcc  jbe     short loc_180067BEE
0x180067bce  lea     rax, aGoingAlternate; "Going alternate reconnect path (no spec"...
0x180067bd5  mov     [rbp+57h+arg_10], rax
0x180067bd9  lea     rax, [rbp+57h+arg_10]
0x180067bdd  mov     [rsp+0A0h+var_80], rax
0x180067be2  lea     rdx, qword_1800C7798
0x180067be9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180067bee  cmp     [rbp+57h+var_50], 0
0x180067bf3  jz      short loc_180067C43
0x180067bf5  mov     rcx, [rbp+57h+var_58]
0x180067bf9  mov     rax, [rcx]
0x180067bfc  xor     r8d, r8d
0x180067bff  xor     edx, edx
0x180067c01  mov     rax, [rax+38h]
0x180067c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067c0a  mov     ecx, eax
0x180067c0c  mov     eax, cs:dword_1800DF020
0x180067c12  cmp     eax, 5
0x180067c15  jbe     short loc_180067C43
0x180067c17  mov     dword ptr [rbp+57h+arg_10], ecx
0x180067c1a  lea     rax, aDisconnectFail; "Disconnect failed on cache session (mig"...
0x180067c21  mov     [rbp+57h+arg_18], rax
0x180067c25  lea     rax, [rbp+57h+arg_10]
0x180067c29  mov     [rsp+0A0h+var_78], rax
0x180067c2e  lea     rax, [rbp+57h+arg_18]
0x180067c32  mov     [rsp+0A0h+var_80], rax
0x180067c37  lea     rdx, byte_1800C7771
0x180067c3e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180067c43  mov     rcx, [rbp+57h+var_58]
0x180067c47  mov     rax, [rcx]
0x180067c4a  mov     r9d, edi
0x180067c4d  mov     r8d, edi
0x180067c50  mov     rbx, [rbp+57h+var_48]
0x180067c54  mov     rdx, rbx
0x180067c57  mov     rax, [rax+30h]
0x180067c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067c60  mov     esi, eax
0x180067c62  mov     rax, [rbx]
0x180067c65  mov     rcx, rbx
  ... truncated ...
```
