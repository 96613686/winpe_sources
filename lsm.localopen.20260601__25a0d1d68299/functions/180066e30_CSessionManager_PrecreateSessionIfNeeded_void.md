# CSessionManager::PrecreateSessionIfNeeded(void)

- ea: `0x180066e30`
- end: `0x1800671b0`
- name: `?PrecreateSessionIfNeeded@CSessionManager@@EEAAJXZ`
- size: `896`
- prototype: `__int64 __fastcall(CSessionManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180065480`

## callees

- `0x180001b90`
- `0x18000c684`
- `0x180022200`
- `0x18002701c`
- `0x1800291f4`
- `0x18004ec5c`
- `0x180065e90`
- `0x180066e30`
- `0x18007f73c`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066ebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066ebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066fcd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180066f50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180066f50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067180`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067180`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180066ea8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180066fbd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180066ea8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180066fbd`

## string_xrefs

- `0x180066e6c`: `Precreatesession if needed was called!`
- `0x180066ea1`: `%SYSTEMROOT%\System32\WinLogon.exe -CachedTerminalSession`
- `0x180066fb6`: `%SYSTEMROOT%\System32\WinLogon.exe -CachedTerminalSession`
- `0x180066ef3`: `PrecreateSessionIfNeeded`
- `0x180066f92`: `PrecreateSessionIfNeeded`
- `0x1800670ba`: `PrecreateSessionIfNeeded`
- `0x18006710e`: `PrecreateSessionIfNeeded`
- `0x180067142`: `Precreatesession if needed completed successfully`
- `0x18006715d`: `We're supposed to create a new cache session, but the pointer is taken!`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSessionManager::PrecreateSessionIfNeeded(CSessionManager *this, __int64 a2, int a3, int a4)
{
  signed int InstanceOfSessionInternal; // ebx
  HLOCAL v6; // rsi
  DWORD v7; // eax
  __int64 v8; // rdi
  signed int LastError; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  char *v13; // rdx
  const char *v14; // rax
  signed int v15; // eax
  DWORD v16; // eax
  signed int v17; // eax
  CCacheTerminal *v18; // rax
  unsigned __int16 *v19; // rdx
  struct ITSSession *v20; // rdi
  const char *v21; // rax
  __int16 *v22; // rdx
  __int64 v24; // [rsp+40h] [rbp-18h] BYREF
  __int64 v25; // [rsp+48h] [rbp-10h] BYREF
  const char *v26; // [rsp+90h] [rbp+38h] BYREF
  struct ITSSession *v27; // [rsp+98h] [rbp+40h] BYREF
  void *v28; // [rsp+A0h] [rbp+48h] BYREF
  const char *v29; // [rsp+A8h] [rbp+50h] BYREF

  InstanceOfSessionInternal = 0;
  v25 = 0;
  v24 = 0;
  if ( *((_DWORD *)this + 424) )
  {
    v6 = 0;
    if ( (unsigned int)dword_1800DF020 > 4 )
    {
      v26 = "Precreatesession if needed was called!";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)this,
        (unsigned int)&byte_1800C766F,
        a3,
        a4,
        (__int64)&v26);
    }
    if ( *((_QWORD *)this + 215) )
    {
      if ( (unsigned int)dword_1800DF020 <= 2 )
        goto LABEL_44;
      v21 = "We're supposed to create a new cache session, but the pointer is taken!";
      v22 = (__int16 *)qword_1800C7490;
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
          if ( (unsigned int)dword_1800DF020 <= 3 )
          {
LABEL_44:
            LocalFree(v6);
            goto LABEL_45;
          }
          v13 = byte_1800C7633;
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
          if ( (unsigned int)dword_1800DF020 <= 3 )
            goto LABEL_44;
          v27 = (struct ITSSession *)"PrecreateSessionIfNeeded";
          v14 = "LocalAlloc";
          v13 = &byte_1800C75F7;
          goto LABEL_13;
        }
      }
      v16 = ExpandEnvironmentStringsW(L"%SYSTEMROOT%\\System32\\WinLogon.exe -CachedTerminalSession", (LPWSTR)v6, v8);
      if ( v16 )
      {
        if ( v16 > (unsigned int)v8 )
        {
          InstanceOfSessionInternal = -2147024774;
          if ( (unsigned int)dword_1800DF020 <= 3 )
            goto LABEL_44;
          v13 = &byte_1800C757F;
LABEL_12:
          v27 = (struct ITSSession *)"PrecreateSessionIfNeeded";
          v14 = "ExpandEnvironmentStrings";
LABEL_13:
          v28 = (void *)v14;
          v29 = "Warning HResult failed";
          LODWORD(v26) = InstanceOfSessionInternal;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v10,
            (_DWORD)v13,
            v11,
            v12,
            (__int64)&v29,
            (__int64)&v28,
            (__int64)&v26,
            (__int64)&v27);
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
          if ( (unsigned int)dword_1800DF020 <= 3 )
            goto LABEL_44;
          v13 = byte_1800C75BB;
          goto LABEL_12;
        }
      }
      if ( (unsigned int)dword_1800DF020 > 4 )
      {
        v26 = (const char *)v6;
        v27 = (struct ITSSession *)"Precreating session";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v10,
          (unsigned int)&dword_1800C754C,
          v11,
          v12,
          (__int64)&v27,
          (__int64)&v26);
      }
      v27 = 0;
      v18 = (CCacheTerminal *)operator new(0x640u, (const struct std::nothrow_t *)&std::nothrow);
      v28 = v18;
      if ( v18 )
        v18 = CCacheTerminal::CCacheTerminal(v18, v19, (int *)&v26);
      InstanceOfSessionInternal = CSessionManager::GetInstanceOfSessionInternal(this, &v27, v18, -1);
      if ( InstanceOfSessionInternal < 0 )
      {
        if ( (unsigned int)dword_1800DF020 <= 3 )
          goto LABEL_44;
        v27 = (struct ITSSession *)"PrecreateSessionIfNeeded";
        v14 = "GetInstanceOfSession";
        v13 = (char *)qword_1800C7510;
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
        if ( (unsigned int)dword_1800DF020 <= 3 )
          goto LABEL_44;
        v27 = (struct ITSSession *)"PrecreateSessionIfNeeded";
        v14 = "Start";
        v13 = (char *)&dword_1800C74D4;
        goto LABEL_13;
      }
      SmartPtr<ITSSession>::operator=((char *)this + 1720, v20);
      if ( (unsigned int)dword_1800DF020 <= 4 )
        goto LABEL_44;
      v21 = "Precreatesession if needed completed successfully";
      v22 = word_1800C74B2;
    }
    v26 = v21;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)this,
      (_DWORD)v22,
      a3,
      a4,
      (__int64)&v26);
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
0x180066e30  push    rbp
0x180066e32  push    rbx
0x180066e33  push    rsi
0x180066e34  push    rdi
0x180066e35  push    r14
0x180066e37  push    r15
0x180066e39  mov     rbp, rsp
0x180066e3c  sub     rsp, 58h
0x180066e40  mov     r14, rcx
0x180066e43  xor     ebx, ebx
0x180066e45  mov     [rbp+var_10], rbx
0x180066e49  mov     [rbp+var_18], rbx
0x180066e4d  cmp     [rcx+6A0h], ebx
0x180066e53  jnz     short loc_180066E5F
0x180066e55  mov     ebx, 80070103h
0x180066e5a  jmp     loc_18006718D
0x180066e5f  xor     esi, esi
0x180066e61  mov     eax, cs:dword_1800DF020
0x180066e67  cmp     eax, 4
0x180066e6a  jbe     short loc_180066E8C
0x180066e6c  lea     rax, aPrecreatesessi_1; "Precreatesession if needed was called!"
0x180066e73  mov     [rbp+arg_0], rax
0x180066e77  lea     rax, [rbp+arg_0]
0x180066e7b  mov     [rsp+58h+var_38], rax
0x180066e80  lea     rdx, byte_1800C766F
0x180066e87  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180066e8c  lea     r15, [r14+6B8h]
0x180066e93  cmp     [r15], rsi
0x180066e96  jnz     loc_180067152
0x180066e9c  xor     r8d, r8d; nSize
0x180066e9f  xor     edx, edx; lpDst
0x180066ea1  lea     rcx, aSystemrootSyst_1; "%SYSTEMROOT%\\System32\\WinLogon.exe -C"...
0x180066ea8  call    cs:__imp_ExpandEnvironmentStringsW
0x180066eaf  nop     dword ptr [rax+rax+00h]
0x180066eb4  mov     edi, eax
0x180066eb6  test    eax, eax
0x180066eb8  jnz     loc_180066F45
0x180066ebe  call    cs:__imp_GetLastError
0x180066ec5  nop     dword ptr [rax+rax+00h]
0x180066eca  mov     ebx, eax
0x180066ecc  test    eax, eax
0x180066ece  jle     short loc_180066ED9
0x180066ed0  movzx   ebx, ax
0x180066ed3  or      ebx, 80070000h
0x180066ed9  test    ebx, ebx
0x180066edb  jns     short loc_180066F45
0x180066edd  mov     eax, cs:dword_1800DF020
0x180066ee3  cmp     eax, 3
0x180066ee6  jbe     loc_18006717D
0x180066eec  lea     rdx, byte_1800C7633
0x180066ef3  lea     rax, aPrecreatesessi_2; "PrecreateSessionIfNeeded"
0x180066efa  mov     [rbp+arg_8], rax
0x180066efe  lea     rax, aExpandenvironm_0; "ExpandEnvironmentStrings"
0x180066f05  mov     [rbp+arg_10], rax
0x180066f09  lea     rax, aWarningHresult; "Warning HResult failed"
0x180066f10  mov     [rbp+arg_18], rax
0x180066f14  lea     rax, [rbp+arg_8]
0x180066f18  mov     [rsp+58h+var_20], rax
0x180066f1d  lea     rax, [rbp+arg_0]
0x180066f21  mov     [rsp+58h+var_28], rax
0x180066f26  lea     rax, [rbp+arg_10]
0x180066f2a  mov     [rsp+58h+var_30], rax
0x180066f2f  lea     rax, [rbp+arg_18]
0x180066f33  mov     [rsp+58h+var_38], rax
0x180066f38  mov     dword ptr [rbp+arg_0], ebx
0x180066f3b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180066f40  jmp     loc_18006717D
0x180066f45  mov     rdx, rdi
0x180066f48  add     rdx, rdx; uBytes
0x180066f4b  mov     ecx, 40h ; '@'; uFlags
0x180066f50  call    cs:__imp_LocalAlloc
0x180066f57  nop     dword ptr [rax+rax+00h]
0x180066f5c  mov     rsi, rax
0x180066f5f  test    rax, rax
0x180066f62  jnz     short loc_180066FB0
0x180066f64  call    cs:__imp_GetLastError
0x180066f6b  nop     dword ptr [rax+rax+00h]
0x180066f70  mov     ebx, eax
0x180066f72  test    eax, eax
0x180066f74  jle     short loc_180066F7F
0x180066f76  movzx   ebx, ax
0x180066f79  or      ebx, 80070000h
0x180066f7f  test    ebx, ebx
0x180066f81  jns     short loc_180066FB0
0x180066f83  mov     eax, cs:dword_1800DF020
0x180066f89  cmp     eax, 3
0x180066f8c  jbe     loc_18006717D
0x180066f92  lea     rax, aPrecreatesessi_2; "PrecreateSessionIfNeeded"
0x180066f99  mov     [rbp+arg_8], rax
0x180066f9d  lea     rax, aLocalalloc; "LocalAlloc"
0x180066fa4  lea     rdx, byte_1800C75F7
0x180066fab  jmp     loc_180066F05
0x180066fb0  mov     r8d, edi; nSize
0x180066fb3  mov     rdx, rsi; lpDst
0x180066fb6  lea     rcx, aSystemrootSyst_1; "%SYSTEMROOT%\\System32\\WinLogon.exe -C"...
0x180066fbd  call    cs:__imp_ExpandEnvironmentStringsW
0x180066fc4  nop     dword ptr [rax+rax+00h]
0x180066fc9  test    eax, eax
0x180066fcb  jnz     short loc_180067007
0x180066fcd  call    cs:__imp_GetLastError
0x180066fd4  nop     dword ptr [rax+rax+00h]
0x180066fd9  mov     ebx, eax
0x180066fdb  test    eax, eax
0x180066fdd  jle     short loc_180066FE8
0x180066fdf  movzx   ebx, ax
0x180066fe2  or      ebx, 80070000h
0x180066fe8  test    ebx, ebx
0x180066fea  jns     short loc_18006702B
0x180066fec  mov     eax, cs:dword_1800DF020
0x180066ff2  cmp     eax, 3
0x180066ff5  jbe     loc_18006717D
0x180066ffb  lea     rdx, byte_1800C75BB
0x180067002  jmp     loc_180066EF3
0x180067007  cmp     eax, edi
0x180067009  jbe     short loc_18006702B
0x18006700b  mov     ebx, 8007007Ah
0x180067010  mov     eax, cs:dword_1800DF020
0x180067016  cmp     eax, 3
0x180067019  jbe     loc_18006717D
0x18006701f  lea     rdx, byte_1800C757F
0x180067026  jmp     loc_180066EF3
0x18006702b  mov     eax, cs:dword_1800DF020
0x180067031  cmp     eax, 4
0x180067034  jbe     short loc_180067063
0x180067036  mov     [rbp+arg_0], rsi
0x18006703a  lea     rax, aPrecreatingSes; "Precreating session"
0x180067041  mov     [rbp+arg_8], rax
0x180067045  lea     rax, [rbp+arg_0]
0x180067049  mov     [rsp+58h+var_30], rax
0x18006704e  lea     rax, [rbp+arg_8]
0x180067052  mov     [rsp+58h+var_38], rax
0x180067057  lea     rdx, dword_1800C754C
0x18006705e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180067063  mov     [rbp+arg_8], 0
0x18006706b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180067072  mov     ecx, 640h; unsigned __int64
0x180067077  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006707c  mov     [rbp+arg_10], rax
0x180067080  test    rax, rax
0x180067083  jz      short loc_180067092
0x180067085  lea     r8, [rbp+arg_0]; int *
0x180067089  mov     rcx, rax; this
0x18006708c  call    ??0CCacheTerminal@@QEAA@PEAGPEAJ@Z; CCacheTerminal::CCacheTerminal(ushort *,long *)
0x180067091  nop
0x180067092  or      r9d, 0FFFFFFFFh; int
0x180067096  mov     r8, rax; struct ITerminal *
0x180067099  lea     rdx, [rbp+arg_8]; struct ITSSession **
0x18006709d  mov     rcx, r14; this
0x1800670a0  call    ?GetInstanceOfSessionInternal@CSessionManager@@EEAAJPEAPEAUITSSession@@PEAUITerminal@@J@Z; CSessionManager::GetInstanceOfSessionInternal(ITSSession * *,ITerminal *,long)
0x1800670a5  mov     ebx, eax
0x1800670a7  test    eax, eax
0x1800670a9  jns     short loc_1800670D8
0x1800670ab  mov     eax, cs:dword_1800DF020
0x1800670b1  cmp     eax, 3
0x1800670b4  jbe     loc_18006717D
0x1800670ba  lea     rax, aPrecreatesessi_2; "PrecreateSessionIfNeeded"
0x1800670c1  mov     [rbp+arg_8], rax
0x1800670c5  lea     rax, aGetinstanceofs_10; "GetInstanceOfSession"
0x1800670cc  lea     rdx, qword_1800C7510
0x1800670d3  jmp     loc_180066F05
0x1800670d8  mov     rdi, [rbp+arg_8]
0x1800670dc  mov     rax, [rdi]
0x1800670df  mov     [rsp+58h+var_38], 0
0x1800670e8  xor     r9d, r9d
0x1800670eb  mov     r8, rsi
0x1800670ee  or      edx, 0FFFFFFFFh
0x1800670f1  mov     rcx, rdi
0x1800670f4  mov     rax, [rax+20h]
0x1800670f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670fd  mov     ebx, eax
0x1800670ff  test    eax, eax
0x180067101  jns     short loc_18006712C
0x180067103  mov     eax, cs:dword_1800DF020
0x180067109  cmp     eax, 3
0x18006710c  jbe     short loc_18006717D
0x18006710e  lea     rax, aPrecreatesessi_2; "PrecreateSessionIfNeeded"
0x180067115  mov     [rbp+arg_8], rax
0x180067119  lea     rax, aStart; "Start"
0x180067120  lea     rdx, dword_1800C74D4
0x180067127  jmp     loc_180066F05
0x18006712c  mov     rdx, rdi
0x18006712f  mov     rcx, r15
0x180067132  call    ??4?$SmartPtr@UITSSession@@@@QEAAAEAV0@PEAUITSSession@@@Z; SmartPtr<ITSSession>::operator=(ITSSession *)
0x180067137  mov     eax, cs:dword_1800DF020
0x18006713d  cmp     eax, 4
0x180067140  jbe     short loc_18006717D
0x180067142  lea     rax, aPrecreatesessi_0; "Precreatesession if needed completed su"...
0x180067149  lea     rdx, word_1800C74B2
0x180067150  jmp     short loc_18006716B
0x180067152  mov     eax, cs:dword_1800DF020
0x180067158  cmp     eax, 2
0x18006715b  jbe     short loc_18006717D
0x18006715d  lea     rax, aWeReSupposedTo; "We're supposed to create a new cache se"...
0x180067164  lea     rdx, qword_1800C7490
0x18006716b  mov     [rbp+arg_0], rax
0x18006716f  lea     rax, [rbp+arg_0]
0x180067173  mov     [rsp+58h+var_38], rax
0x180067178  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006717d  mov     rcx, rsi; hMem
0x180067180  call    cs:__imp_LocalFree
0x180067187  nop     dword ptr [rax+rax+00h]
0x18006718c  nop
0x18006718d  lea     rcx, [rbp+var_18]
0x180067191  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180067196  nop
0x180067197  lea     rcx, [rbp+var_10]
0x18006719b  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800671a0  mov     eax, ebx
0x1800671a2  add     rsp, 58h
0x1800671a6  pop     r15
0x1800671a8  pop     r14
0x1800671aa  pop     rdi
0x1800671ab  pop     rsi
0x1800671ac  pop     rbx
0x1800671ad  pop     rbp
0x1800671ae  retn
```
