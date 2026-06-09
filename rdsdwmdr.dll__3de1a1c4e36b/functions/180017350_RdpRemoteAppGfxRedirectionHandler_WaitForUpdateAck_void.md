# RdpRemoteAppGfxRedirectionHandler::WaitForUpdateAck(void)

- ea: `0x180017350`
- end: `0x1800174c2`
- name: `?WaitForUpdateAck@RdpRemoteAppGfxRedirectionHandler@@IEAAJXZ`
- size: `370`
- prototype: `__int64 __fastcall(RdpRemoteAppGfxRedirectionHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800154f0`

## callees

- `0x1800010f8`
- `0x18000160c`
- `0x180017350`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173d3`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800173ac`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800173ac`

## string_xrefs

- `0x180017361`: `WaitForUpdateAck`
- `0x180017471`: `Graphics update ack is not received because session got disconnected`
- `0x180017444`: `Graphics update timed out`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::WaitForUpdateAck(
        HANDLE *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  DWORD v4; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  signed int LastError; // eax
  char *v9; // rdx
  const char *v10; // rax
  const char *v12; // [rsp+50h] [rbp-28h] BYREF
  HANDLE Handles[4]; // [rsp+58h] [rbp-20h] BYREF
  const char *v14; // [rsp+90h] [rbp+18h] BYREF
  int v15; // [rsp+98h] [rbp+20h] BYREF
  const char *v16; // [rsp+A0h] [rbp+28h] BYREF
  const char *v17; // [rsp+A8h] [rbp+30h] BYREF

  Handles[0] = this[20];
  Handles[1] = this[19];
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v14 = "WaitForUpdateAck";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)this,
      (__int64)byte_18003C3FB,
      a3,
      a4,
      (const unsigned __int16 **)&v14);
  }
  v4 = WaitForMultipleObjects(2u, Handles, 0, 0x3A98u);
  switch ( v4 )
  {
    case 0u:
      if ( (unsigned int)dword_180044008 <= 2 )
        return 0;
      LODWORD(v14) = 1184;
      v17 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v9 = byte_18003C3A1;
      v10 = "Graphics update ack is not received because session got disconnected";
      goto LABEL_15;
    case 1u:
      return 0;
    case 0x102u:
      if ( (unsigned int)dword_180044008 <= 2 )
        return 0;
      LODWORD(v14) = 1193;
      v17 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v9 = &byte_18003C347;
      v10 = "Graphics update timed out";
LABEL_15:
      v15 = 0;
      goto LABEL_16;
    case 0xFFFFFFFF:
      LastError = GetLastError();
      v5 = (unsigned int)LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v14) = 1199;
        v17 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
        v9 = byte_18003C2ED;
        v10 = "WaitForMultipleObjects";
        v15 = v5;
LABEL_16:
        v12 = v10;
        v16 = "WaitForUpdateAck";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v5,
          (__int64)v9,
          v6,
          v7,
          (const unsigned __int16 **)&v12,
          (__int64)&v15,
          (const unsigned __int16 **)&v17,
          (__int64)&v14,
          (const unsigned __int16 **)&v16);
      }
      break;
  }
  return 0;
}

```

## disassembly

```asm
0x180017350  push    rbp
0x180017352  push    rdi
0x180017353  mov     rbp, rsp
0x180017356  sub     rsp, 78h
0x18001735a  mov     rax, [rcx+0A0h]
0x180017361  lea     rdi, aWaitforupdatea_0; "WaitForUpdateAck"
0x180017368  mov     [rbp+Handles], rax
0x18001736c  mov     rax, [rcx+98h]
0x180017373  mov     [rbp+var_18], rax
0x180017377  mov     eax, cs:dword_180044008
0x18001737d  cmp     eax, 5
0x180017380  jbe     short loc_18001739B
0x180017382  lea     rax, [rbp+arg_0]
0x180017386  mov     [rbp+arg_0], rdi
0x18001738a  lea     rdx, byte_18003C3FB
0x180017391  mov     [rsp+78h+var_58], rax
0x180017396  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18001739b  xor     r8d, r8d; bWaitAll
0x18001739e  lea     rdx, [rbp+Handles]; lpHandles
0x1800173a2  mov     r9d, 3A98h; dwMilliseconds
0x1800173a8  lea     ecx, [r8+2]; nCount
0x1800173ac  call    cs:__imp_WaitForMultipleObjects
0x1800173b2  test    eax, eax
0x1800173b4  jz      loc_18001744D
0x1800173ba  cmp     eax, 1
0x1800173bd  jz      loc_1800174B9
0x1800173c3  cmp     eax, 102h
0x1800173c8  jz      short loc_18001741C
0x1800173ca  cmp     eax, 0FFFFFFFFh
0x1800173cd  jnz     loc_1800174B9
0x1800173d3  call    cs:__imp_GetLastError
0x1800173d9  mov     ecx, eax
0x1800173db  test    eax, eax
0x1800173dd  jle     short loc_1800173E8
0x1800173df  movzx   ecx, ax
0x1800173e2  or      ecx, 80070000h
0x1800173e8  mov     eax, cs:dword_180044008
0x1800173ee  cmp     eax, 2
0x1800173f1  jbe     loc_1800174B9
0x1800173f7  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x1800173fe  mov     dword ptr [rbp+arg_0], 4AFh
0x180017405  mov     [rbp+arg_18], rax
0x180017409  lea     rdx, byte_18003C2ED
0x180017410  lea     rax, aWaitformultipl; "WaitForMultipleObjects"
0x180017417  mov     [rbp+arg_8], ecx
0x18001741a  jmp     short loc_18001747F
0x18001741c  mov     eax, cs:dword_180044008
0x180017422  cmp     eax, 2
0x180017425  jbe     loc_1800174B9
0x18001742b  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180017432  mov     dword ptr [rbp+arg_0], 4A9h
0x180017439  mov     [rbp+arg_18], rax
0x18001743d  lea     rdx, byte_18003C347
0x180017444  lea     rax, aGraphicsUpdate_0; "Graphics update timed out"
0x18001744b  jmp     short loc_180017478
0x18001744d  mov     eax, cs:dword_180044008
0x180017453  cmp     eax, 2
0x180017456  jbe     short loc_1800174B9
0x180017458  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x18001745f  mov     dword ptr [rbp+arg_0], 4A0h
0x180017466  mov     [rbp+arg_18], rax
0x18001746a  lea     rdx, byte_18003C3A1
0x180017471  lea     rax, aGraphicsUpdate; "Graphics update ack is not received bec"...
0x180017478  mov     [rbp+arg_8], 0
0x18001747f  mov     [rbp+var_28], rax
0x180017483  lea     rax, [rbp+arg_10]
0x180017487  mov     [rsp+78h+var_38], rax
0x18001748c  lea     rax, [rbp+arg_0]
0x180017490  mov     [rsp+78h+var_40], rax
0x180017495  lea     rax, [rbp+arg_18]
0x180017499  mov     [rsp+78h+var_48], rax
0x18001749e  lea     rax, [rbp+arg_8]
0x1800174a2  mov     [rsp+78h+var_50], rax
0x1800174a7  lea     rax, [rbp+var_28]
0x1800174ab  mov     [rsp+78h+var_58], rax
0x1800174b0  mov     [rbp+arg_10], rdi
0x1800174b4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800174b9  xor     eax, eax
0x1800174bb  add     rsp, 78h
0x1800174bf  pop     rdi
0x1800174c0  pop     rbp
0x1800174c1  retn
```
