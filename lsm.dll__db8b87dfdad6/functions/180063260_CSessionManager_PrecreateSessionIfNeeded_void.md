# CSessionManager::PrecreateSessionIfNeeded(void)

- ea: `0x180063260`
- end: `0x1800635b5`
- name: `?PrecreateSessionIfNeeded@CSessionManager@@EEAAJXZ`
- size: `853`
- prototype: `__int64 __fastcall(CSessionManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180061940`

## callees

- `0x180001b80`
- `0x180008f64`
- `0x18001fd70`
- `0x180025070`
- `0x180027030`
- `0x18004b86c`
- `0x180062320`
- `0x180063260`
- `0x18007af10`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800632e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800633df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800632e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800633df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063374`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063374`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006358c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006358c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800632d8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800633d5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800632d8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800633d5`

## string_xrefs

- `0x18006329c`: `Precreatesession if needed was called!`
- `0x1800632d1`: `%SYSTEMROOT%\System32\WinLogon.exe -CachedTerminalSession`
- `0x1800633ce`: `%SYSTEMROOT%\System32\WinLogon.exe -CachedTerminalSession`
- `0x180063317`: `PrecreateSessionIfNeeded`
- `0x1800633aa`: `PrecreateSessionIfNeeded`
- `0x1800634c6`: `PrecreateSessionIfNeeded`
- `0x18006351a`: `PrecreateSessionIfNeeded`
- `0x18006354e`: `Precreatesession if needed completed successfully`
- `0x180063569`: `We're supposed to create a new cache session, but the pointer is taken!`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSessionManager::PrecreateSessionIfNeeded(CSessionManager *this, __int64 a2, __int64 a3, __int64 a4)
{
  signed int InstanceOfSessionInternal; // ebx
  HLOCAL v6; // rsi
  DWORD v7; // eax
  __int64 v8; // rdi
  signed int LastError; // eax
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  char *v13; // rdx
  const char *v14; // rax
  signed int v15; // eax
  DWORD v16; // eax
  signed int v17; // eax
  unsigned __int16 *v18; // rax
  const char *v19; // rdx
  struct ITSSession *v20; // rdi
  const char *v21; // rax
  unsigned __int8 *v22; // rdx
  __int64 v24; // [rsp+40h] [rbp-18h] BYREF
  __int64 v25; // [rsp+48h] [rbp-10h] BYREF
  const char *v26; // [rsp+90h] [rbp+38h] BYREF
  struct ITSSession *v27; // [rsp+98h] [rbp+40h] BYREF
  const unsigned __int16 *v28; // [rsp+A0h] [rbp+48h] BYREF
  const char *v29; // [rsp+A8h] [rbp+50h] BYREF

  InstanceOfSessionInternal = 0;
  v25 = 0;
  v24 = 0;
  if ( *((_DWORD *)this + 424) )
  {
    v6 = 0;
    if ( (unsigned int)dword_1800DA020 > 4 )
    {
      v26 = "Precreatesession if needed was called!";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)this,
        (unsigned __int8 *)&byte_1800C24E7,
        a3,
        a4,
        (const unsigned __int16 **)&v26);
    }
    if ( *((_QWORD *)this + 215) )
    {
      if ( (unsigned int)dword_1800DA020 <= 2 )
        goto LABEL_44;
      v21 = "We're supposed to create a new cache session, but the pointer is taken!";
      v22 = (unsigned __int8 *)qword_1800C2308;
    }
    else
    {
      v7 = ExpandEnvironmentStringsW(L"%SYSTEMROOT%\\System32\\WinLogon.exe -CachedTerminalSession", 0, 0);
      v8 = v7;
      if ( !v7 )
      {
        LastError = GetLastError();
        InstanceOfSessionInternal = LastError;
        if ( LastError > 0 )
          InstanceOfSessionInternal = (unsigned __int16)LastError | 0x80070000;
        if ( InstanceOfSessionInternal < 0 )
        {
          if ( (unsigned int)dword_1800DA020 <= 3 )
          {
LABEL_44:
            LocalFree(v6);
            goto LABEL_45;
          }
          v13 = byte_1800C24AB;
          goto LABEL_12;
        }
      }
      v6 = LocalAlloc(0x40u, 2 * v8);
      if ( !v6 )
      {
        v15 = GetLastError();
        InstanceOfSessionInternal = v15;
        if ( v15 > 0 )
          InstanceOfSessionInternal = (unsigned __int16)v15 | 0x80070000;
        if ( InstanceOfSessionInternal < 0 )
        {
          if ( (unsigned int)dword_1800DA020 <= 3 )
            goto LABEL_44;
          v27 = (struct ITSSession *)"PrecreateSessionIfNeeded";
          v14 = "LocalAlloc";
          v13 = &byte_1800C246F;
          goto LABEL_13;
        }
      }
      v16 = ExpandEnvironmentStringsW(L"%SYSTEMROOT%\\System32\\WinLogon.exe -CachedTerminalSession", (LPWSTR)v6, v8);
      if ( v16 )
      {
        if ( v16 > (unsigned int)v8 )
        {
          InstanceOfSessionInternal = -2147024774;
          if ( (unsigned int)dword_1800DA020 <= 3 )
            goto LABEL_44;
          v13 = &byte_1800C23F7;
LABEL_12:
          v27 = (struct ITSSession *)"PrecreateSessionIfNeeded";
          v14 = "ExpandEnvironmentStrings";
LABEL_13:
          v28 = (const unsigned __int16 *)v14;
          v29 = "Warning HResult failed";
          LODWORD(v26) = InstanceOfSessionInternal;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v10,
            (int)v13,
            v11,
            v12,
            (const unsigned __int16 **)&v29,
            &v28,
            (__int64)&v26,
            (const unsigned __int16 **)&v27);
          goto LABEL_44;
        }
      }
      else
      {
        v17 = GetLastError();
        InstanceOfSessionInternal = v17;
        if ( v17 > 0 )
          InstanceOfSessionInternal = (unsigned __int16)v17 | 0x80070000;
        if ( InstanceOfSessionInternal < 0 )
        {
          if ( (unsigned int)dword_1800DA020 <= 3 )
            goto LABEL_44;
          v13 = byte_1800C2433;
          goto LABEL_12;
        }
      }
      if ( (unsigned int)dword_1800DA020 > 4 )
      {
        v26 = (const char *)v6;
        v27 = (struct ITSSession *)"Precreating session";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v10,
          (unsigned __int8 *)&dword_1800C23C4,
          v11,
          v12,
          (const unsigned __int16 **)&v27,
          (__int64 **)&v26);
      }
      v27 = 0;
      v18 = (unsigned __int16 *)operator new(0x640u, (const struct std::nothrow_t *)&std::nothrow);
      v28 = v18;
      if ( v18 )
        v18 = (unsigned __int16 *)CCacheTerminal::CCacheTerminal((CCacheTerminal *)v18, v19, (int *)&v26);
      InstanceOfSessionInternal = CSessionManager::GetInstanceOfSessionInternal(this, &v27, (struct ITerminal *)v18, -1);
      if ( InstanceOfSessionInternal < 0 )
      {
        if ( (unsigned int)dword_1800DA020 <= 3 )
          goto LABEL_44;
        v27 = (struct ITSSession *)"PrecreateSessionIfNeeded";
        v14 = "GetInstanceOfSession";
        v13 = (char *)qword_1800C2388;
        goto LABEL_13;
      }
      v20 = v27;
      InstanceOfSessionInternal = (*(__int64 (__fastcall **)(struct ITSSession *, __int64, HLOCAL, _QWORD, _QWORD))(*(_QWORD *)v27 + 32LL))(
                                    v27,
                                    0xFFFFFFFFLL,
                                    v6,
                                    0,
                                    0);
      if ( InstanceOfSessionInternal < 0 )
      {
        if ( (unsigned int)dword_1800DA020 <= 3 )
          goto LABEL_44;
        v27 = (struct ITSSession *)"PrecreateSessionIfNeeded";
        v14 = "Start";
        v13 = (char *)&dword_1800C234C;
        goto LABEL_13;
      }
      SmartPtr<ITSSession>::operator=((__int64 *)this + 215, (__int64)v20);
      if ( (unsigned int)dword_1800DA020 <= 4 )
        goto LABEL_44;
      v21 = "Precreatesession if needed completed successfully";
      v22 = (unsigned __int8 *)word_1800C232A;
    }
    v26 = v21;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)this,
      v22,
      a3,
      a4,
      (const unsigned __int16 **)&v26);
    goto LABEL_44;
  }
  InstanceOfSessionInternal = -2147024637;
LABEL_45:
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v24);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v25);
  return (unsigned int)InstanceOfSessionInternal;
}

```

## disassembly

```asm
0x180063260  push    rbp
0x180063262  push    rbx
0x180063263  push    rsi
0x180063264  push    rdi
0x180063265  push    r14
0x180063267  push    r15
0x180063269  mov     rbp, rsp
0x18006326c  sub     rsp, 58h
0x180063270  mov     r14, rcx
0x180063273  xor     ebx, ebx
0x180063275  mov     [rbp+var_10], rbx
0x180063279  mov     [rbp+var_18], rbx
0x18006327d  cmp     [rcx+6A0h], ebx
0x180063283  jnz     short loc_18006328F
0x180063285  mov     ebx, 80070103h
0x18006328a  jmp     loc_180063593
0x18006328f  xor     esi, esi
0x180063291  mov     eax, cs:dword_1800DA020
0x180063297  cmp     eax, 4
0x18006329a  jbe     short loc_1800632BC
0x18006329c  lea     rax, aPrecreatesessi_1; "Precreatesession if needed was called!"
0x1800632a3  mov     [rbp+arg_0], rax
0x1800632a7  lea     rax, [rbp+arg_0]
0x1800632ab  mov     [rsp+58h+var_38], rax
0x1800632b0  lea     rdx, byte_1800C24E7
0x1800632b7  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800632bc  lea     r15, [r14+6B8h]
0x1800632c3  cmp     [r15], rsi
0x1800632c6  jnz     loc_18006355E
0x1800632cc  xor     r8d, r8d; nSize
0x1800632cf  xor     edx, edx; lpDst
0x1800632d1  lea     rcx, aSystemrootSyst_1; "%SYSTEMROOT%\\System32\\WinLogon.exe -C"...
0x1800632d8  call    cs:__imp_ExpandEnvironmentStringsW
0x1800632de  mov     edi, eax
0x1800632e0  test    eax, eax
0x1800632e2  jnz     loc_180063369
0x1800632e8  call    cs:__imp_GetLastError
0x1800632ee  mov     ebx, eax
0x1800632f0  test    eax, eax
0x1800632f2  jle     short loc_1800632FD
0x1800632f4  movzx   ebx, ax
0x1800632f7  or      ebx, 80070000h
0x1800632fd  test    ebx, ebx
0x1800632ff  jns     short loc_180063369
0x180063301  mov     eax, cs:dword_1800DA020
0x180063307  cmp     eax, 3
0x18006330a  jbe     loc_180063589
0x180063310  lea     rdx, byte_1800C24AB
0x180063317  lea     rax, aPrecreatesessi_2; "PrecreateSessionIfNeeded"
0x18006331e  mov     [rbp+arg_8], rax
0x180063322  lea     rax, aExpandenvironm_0; "ExpandEnvironmentStrings"
0x180063329  mov     [rbp+arg_10], rax
0x18006332d  lea     rax, aWarningHresult; "Warning HResult failed"
0x180063334  mov     [rbp+arg_18], rax
0x180063338  lea     rax, [rbp+arg_8]
0x18006333c  mov     [rsp+58h+var_20], rax
0x180063341  lea     rax, [rbp+arg_0]
0x180063345  mov     [rsp+58h+var_28], rax
0x18006334a  lea     rax, [rbp+arg_10]
0x18006334e  mov     [rsp+58h+var_30], rax
0x180063353  lea     rax, [rbp+arg_18]
0x180063357  mov     [rsp+58h+var_38], rax
0x18006335c  mov     dword ptr [rbp+arg_0], ebx
0x18006335f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180063364  jmp     loc_180063589
0x180063369  mov     rdx, rdi
0x18006336c  add     rdx, rdx; uBytes
0x18006336f  mov     ecx, 40h ; '@'; uFlags
0x180063374  call    cs:__imp_LocalAlloc
0x18006337a  mov     rsi, rax
0x18006337d  test    rax, rax
0x180063380  jnz     short loc_1800633C8
0x180063382  call    cs:__imp_GetLastError
0x180063388  mov     ebx, eax
0x18006338a  test    eax, eax
0x18006338c  jle     short loc_180063397
0x18006338e  movzx   ebx, ax
0x180063391  or      ebx, 80070000h
0x180063397  test    ebx, ebx
0x180063399  jns     short loc_1800633C8
0x18006339b  mov     eax, cs:dword_1800DA020
0x1800633a1  cmp     eax, 3
0x1800633a4  jbe     loc_180063589
0x1800633aa  lea     rax, aPrecreatesessi_2; "PrecreateSessionIfNeeded"
0x1800633b1  mov     [rbp+arg_8], rax
0x1800633b5  lea     rax, aLocalalloc; "LocalAlloc"
0x1800633bc  lea     rdx, byte_1800C246F
0x1800633c3  jmp     loc_180063329
0x1800633c8  mov     r8d, edi; nSize
0x1800633cb  mov     rdx, rsi; lpDst
0x1800633ce  lea     rcx, aSystemrootSyst_1; "%SYSTEMROOT%\\System32\\WinLogon.exe -C"...
0x1800633d5  call    cs:__imp_ExpandEnvironmentStringsW
0x1800633db  test    eax, eax
0x1800633dd  jnz     short loc_180063413
0x1800633df  call    cs:__imp_GetLastError
0x1800633e5  mov     ebx, eax
0x1800633e7  test    eax, eax
0x1800633e9  jle     short loc_1800633F4
0x1800633eb  movzx   ebx, ax
0x1800633ee  or      ebx, 80070000h
0x1800633f4  test    ebx, ebx
0x1800633f6  jns     short loc_180063437
0x1800633f8  mov     eax, cs:dword_1800DA020
0x1800633fe  cmp     eax, 3
0x180063401  jbe     loc_180063589
0x180063407  lea     rdx, byte_1800C2433
0x18006340e  jmp     loc_180063317
0x180063413  cmp     eax, edi
0x180063415  jbe     short loc_180063437
0x180063417  mov     ebx, 8007007Ah
0x18006341c  mov     eax, cs:dword_1800DA020
0x180063422  cmp     eax, 3
0x180063425  jbe     loc_180063589
0x18006342b  lea     rdx, byte_1800C23F7
0x180063432  jmp     loc_180063317
0x180063437  mov     eax, cs:dword_1800DA020
0x18006343d  cmp     eax, 4
0x180063440  jbe     short loc_18006346F
0x180063442  mov     [rbp+arg_0], rsi
0x180063446  lea     rax, aPrecreatingSes; "Precreating session"
0x18006344d  mov     [rbp+arg_8], rax
0x180063451  lea     rax, [rbp+arg_0]
0x180063455  mov     [rsp+58h+var_30], rax
0x18006345a  lea     rax, [rbp+arg_8]
0x18006345e  mov     [rsp+58h+var_38], rax
0x180063463  lea     rdx, dword_1800C23C4
0x18006346a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18006346f  mov     [rbp+arg_8], 0
0x180063477  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006347e  mov     ecx, 640h; unsigned __int64
0x180063483  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180063488  mov     [rbp+arg_10], rax
0x18006348c  test    rax, rax
0x18006348f  jz      short loc_18006349E
0x180063491  lea     r8, [rbp+arg_0]; int *
0x180063495  mov     rcx, rax; this
0x180063498  call    ??0CCacheTerminal@@QEAA@PEAGPEAJ@Z; CCacheTerminal::CCacheTerminal(ushort *,long *)
0x18006349d  nop
0x18006349e  or      r9d, 0FFFFFFFFh; int
0x1800634a2  mov     r8, rax; struct ITerminal *
0x1800634a5  lea     rdx, [rbp+arg_8]; struct ITSSession **
0x1800634a9  mov     rcx, r14; this
0x1800634ac  call    ?GetInstanceOfSessionInternal@CSessionManager@@EEAAJPEAPEAUITSSession@@PEAUITerminal@@J@Z; CSessionManager::GetInstanceOfSessionInternal(ITSSession * *,ITerminal *,long)
0x1800634b1  mov     ebx, eax
0x1800634b3  test    eax, eax
0x1800634b5  jns     short loc_1800634E4
0x1800634b7  mov     eax, cs:dword_1800DA020
0x1800634bd  cmp     eax, 3
0x1800634c0  jbe     loc_180063589
0x1800634c6  lea     rax, aPrecreatesessi_2; "PrecreateSessionIfNeeded"
0x1800634cd  mov     [rbp+arg_8], rax
0x1800634d1  lea     rax, aGetinstanceofs_10; "GetInstanceOfSession"
0x1800634d8  lea     rdx, qword_1800C2388
0x1800634df  jmp     loc_180063329
0x1800634e4  mov     rdi, [rbp+arg_8]
0x1800634e8  mov     rax, [rdi]
0x1800634eb  mov     [rsp+58h+var_38], 0
0x1800634f4  xor     r9d, r9d
0x1800634f7  mov     r8, rsi
0x1800634fa  or      edx, 0FFFFFFFFh
0x1800634fd  mov     rcx, rdi
0x180063500  mov     rax, [rax+20h]
0x180063504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063509  mov     ebx, eax
0x18006350b  test    eax, eax
0x18006350d  jns     short loc_180063538
0x18006350f  mov     eax, cs:dword_1800DA020
0x180063515  cmp     eax, 3
0x180063518  jbe     short loc_180063589
0x18006351a  lea     rax, aPrecreatesessi_2; "PrecreateSessionIfNeeded"
0x180063521  mov     [rbp+arg_8], rax
0x180063525  lea     rax, aStart; "Start"
0x18006352c  lea     rdx, dword_1800C234C
0x180063533  jmp     loc_180063329
0x180063538  mov     rdx, rdi
0x18006353b  mov     rcx, r15
0x18006353e  call    ??4?$SmartPtr@UITSSession@@@@QEAAAEAV0@PEAUITSSession@@@Z; SmartPtr<ITSSession>::operator=(ITSSession *)
0x180063543  mov     eax, cs:dword_1800DA020
0x180063549  cmp     eax, 4
0x18006354c  jbe     short loc_180063589
0x18006354e  lea     rax, aPrecreatesessi_0; "Precreatesession if needed completed su"...
0x180063555  lea     rdx, word_1800C232A
0x18006355c  jmp     short loc_180063577
0x18006355e  mov     eax, cs:dword_1800DA020
0x180063564  cmp     eax, 2
0x180063567  jbe     short loc_180063589
0x180063569  lea     rax, aWeReSupposedTo; "We're supposed to create a new cache se"...
0x180063570  lea     rdx, qword_1800C2308
0x180063577  mov     [rbp+arg_0], rax
0x18006357b  lea     rax, [rbp+arg_0]
0x18006357f  mov     [rsp+58h+var_38], rax
0x180063584  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180063589  mov     rcx, rsi; hMem
0x18006358c  call    cs:__imp_LocalFree
0x180063592  nop
0x180063593  lea     rcx, [rbp+var_18]
0x180063597  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18006359c  nop
0x18006359d  lea     rcx, [rbp+var_10]
0x1800635a1  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800635a6  mov     eax, ebx
0x1800635a8  add     rsp, 58h
0x1800635ac  pop     r15
0x1800635ae  pop     r14
0x1800635b0  pop     rdi
0x1800635b1  pop     rsi
0x1800635b2  pop     rbx
0x1800635b3  pop     rbp
0x1800635b4  retn
```
