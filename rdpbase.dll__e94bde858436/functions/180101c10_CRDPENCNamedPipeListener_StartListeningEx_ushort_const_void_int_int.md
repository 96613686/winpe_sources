# CRDPENCNamedPipeListener::StartListeningEx(ushort const *,void *,int,int)

- ea: `0x180101c10`
- end: `0x180101f10`
- name: `?StartListeningEx@CRDPENCNamedPipeListener@@UEAAJPEBGPEAXHH@Z`
- size: `768`
- prototype: `__int64 __fastcall(CRDPENCNamedPipeListener *__hidden this, const unsigned __int16 *, PSID pSourceSid, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180001aa0`
- `0x180005090`
- `0x18006f3dc`
- `0x180101c10`
- `0x180101f18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101dd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101dd2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180101c5d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180101d15`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180101c5d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180101d15`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180101dc4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180101dc4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180101d05`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180101d05`

## string_xrefs

- `0x180101c85`: `SIDs array allocation failed`
- `0x180101d44`: `Failed to allocate memory to copy SID`
- `0x180101df2`: `Failed to copy SID`

## pseudocode

```c
__int64 __fastcall CRDPENCNamedPipeListener::StartListeningEx(
        CRDPENCNamedPipeListener *this,
        const unsigned __int16 *a2,
        PSID pSourceSid,
        int a4,
        int a5)
{
  _QWORD *v5; // r14
  PSID **v7; // rdi
  PSID *v11; // rax
  int v12; // r8d
  int v13; // r9d
  unsigned int v14; // ebx
  char *v15; // rdx
  const char **v16; // rax
  SIZE_T LengthSid; // r15
  PSID *v18; // rdx
  signed int LastError; // eax
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int started; // eax
  int v24; // r8d
  int v25; // r9d
  const char **v27; // [rsp+30h] [rbp-40h]
  const char **v28; // [rsp+40h] [rbp-30h]
  const char **v29; // [rsp+48h] [rbp-28h]
  const char *v30; // [rsp+50h] [rbp-20h] BYREF
  const char *v31; // [rsp+58h] [rbp-18h] BYREF
  const char *v32; // [rsp+60h] [rbp-10h] BYREF
  const char *v33; // [rsp+68h] [rbp-8h] BYREF
  int v34; // [rsp+B0h] [rbp+40h] BYREF
  const char *v35; // [rsp+C0h] [rbp+50h] BYREF

  v5 = (_QWORD *)((char *)this + 680);
  v7 = (PSID **)((char *)this + 672);
  DeleteSidsArray((char *)this + 672, (char *)this + 680);
  if ( !pSourceSid )
    goto LABEL_16;
  v11 = (PSID *)LocalAlloc(0x40u, 8u);
  *v7 = v11;
  if ( !v11 )
  {
    v14 = -2147024882;
    if ( (unsigned int)CallbackContext <= 2 )
    {
LABEL_19:
      DeleteSidsArray(v7, v5);
      return v14;
    }
    v34 = 356;
    v30 = "SIDs array allocation failed";
    v15 = byte_1801C6329;
    v31 = "StartListeningEx";
    v32 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
    v33 = "Error condition failed";
    v29 = &v30;
    v28 = &v31;
    v27 = &v32;
    v16 = &v33;
LABEL_5:
    LODWORD(v35) = -2147024882;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      -2147024882,
      (_DWORD)v15,
      v12,
      v13,
      (__int64)v16,
      (__int64)&v35,
      (__int64)v27,
      (__int64)&v34,
      (__int64)v28,
      (__int64)v29);
    goto LABEL_19;
  }
  LengthSid = GetLengthSid(pSourceSid);
  **v7 = LocalAlloc(0x40u, LengthSid);
  v18 = *v7;
  if ( !**v7 )
  {
    v14 = -2147024882;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_19;
    v34 = 360;
    v33 = "Failed to allocate memory to copy SID";
    v15 = &byte_1801C62D7;
    v32 = "StartListeningEx";
    v31 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
    v30 = "Error condition failed";
    v29 = &v33;
    v28 = &v32;
    v27 = &v31;
    v16 = &v30;
    goto LABEL_5;
  }
  *v5 = 1;
  if ( CopySid(LengthSid, *v18, pSourceSid) )
  {
LABEL_16:
    started = CRDPENCNamedPipeListener::StartListeningInternal(this, a2, a4, a5);
    v14 = started;
    if ( started < 0 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        v34 = started;
        v35 = "StartListeningEx";
        v33 = "StartListeningInternal failed";
        v32 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)&byte_1801C6297,
          v24,
          v25,
          (__int64)&v32,
          (__int64)&v33,
          (__int64)&v34,
          (__int64)&v35);
      }
      goto LABEL_19;
    }
  }
  else
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v34 = 364;
      v33 = "Failed to copy SID";
      LODWORD(v35) = v14;
      v32 = "StartListeningEx";
      v31 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
      v30 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v20,
        (unsigned int)byte_1801C6245,
        v21,
        v22,
        (__int64)&v30,
        (__int64)&v35,
        (__int64)&v31,
        (__int64)&v34,
        (__int64)&v32,
        (__int64)&v33);
    }
    if ( (v14 & 0x80000000) != 0 )
      goto LABEL_19;
  }
  return v14;
}

```

## disassembly

```asm
0x180101c10  mov     [rsp-38h+arg_8], rbx
0x180101c15  push    rbp
0x180101c16  push    rsi
0x180101c17  push    rdi
0x180101c18  push    r12
0x180101c1a  push    r13
0x180101c1c  push    r14
0x180101c1e  push    r15
0x180101c20  mov     rbp, rsp
0x180101c23  sub     rsp, 70h
0x180101c27  lea     r14, [rcx+2A8h]
0x180101c2e  mov     r13, rdx
0x180101c31  lea     rdi, [rcx+2A0h]
0x180101c38  mov     rbx, rcx
0x180101c3b  mov     rdx, r14
0x180101c3e  mov     rcx, rdi
0x180101c41  mov     r12d, r9d
0x180101c44  mov     rsi, r8
0x180101c47  call    DeleteSidsArray
0x180101c4c  test    rsi, rsi
0x180101c4f  jz      loc_180101E74
0x180101c55  mov     edx, 8; uBytes
0x180101c5a  lea     ecx, [rdx+38h]; uFlags
0x180101c5d  call    cs:__imp_LocalAlloc
0x180101c63  mov     [rdi], rax
0x180101c66  test    rax, rax
0x180101c69  jnz     loc_180101D02
0x180101c6f  mov     eax, cs:CallbackContext
0x180101c75  mov     ecx, 8007000Eh
0x180101c7a  mov     ebx, ecx
0x180101c7c  cmp     eax, 2
0x180101c7f  jbe     loc_180101EEB
0x180101c85  lea     rax, aSidsArrayAlloc; "SIDs array allocation failed"
0x180101c8c  mov     [rbp+arg_0], 164h
0x180101c93  mov     [rbp+var_20], rax
0x180101c97  lea     rdx, byte_1801C6329
0x180101c9e  lea     rax, aStartlistening_0; "StartListeningEx"
0x180101ca5  mov     [rbp+var_18], rax
0x180101ca9  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180101cb0  mov     [rbp+var_10], rax
0x180101cb4  lea     rax, aErrorCondition; "Error condition failed"
0x180101cbb  mov     [rbp+var_8], rax
0x180101cbf  lea     rax, [rbp+var_20]
0x180101cc3  mov     [rsp+70h+var_28], rax
0x180101cc8  lea     rax, [rbp+var_18]
0x180101ccc  mov     [rsp+70h+var_30], rax
0x180101cd1  lea     rax, [rbp+arg_0]
0x180101cd5  mov     [rsp+70h+var_38], rax
0x180101cda  lea     rax, [rbp+var_10]
0x180101cde  mov     [rsp+70h+var_40], rax
0x180101ce3  lea     rax, [rbp+arg_10]
0x180101ce7  mov     [rsp+70h+var_48], rax
0x180101cec  lea     rax, [rbp+var_8]
0x180101cf0  mov     [rsp+70h+var_50], rax
0x180101cf5  mov     dword ptr [rbp+arg_10], ecx
0x180101cf8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180101cfd  jmp     loc_180101EEB
0x180101d02  mov     rcx, rsi; pSid
0x180101d05  call    cs:__imp_GetLengthSid
0x180101d0b  mov     edx, eax; uBytes
0x180101d0d  mov     ecx, 40h ; '@'; uFlags
0x180101d12  mov     r15d, eax
0x180101d15  call    cs:__imp_LocalAlloc
0x180101d1b  mov     rcx, [rdi]
0x180101d1e  mov     [rcx], rax
0x180101d21  mov     rdx, [rdi]
0x180101d24  cmp     qword ptr [rdx], 0
0x180101d28  jnz     loc_180101DB4
0x180101d2e  mov     eax, cs:CallbackContext
0x180101d34  mov     ecx, 8007000Eh
0x180101d39  mov     ebx, ecx
0x180101d3b  cmp     eax, 2
0x180101d3e  jbe     loc_180101EEB
0x180101d44  lea     rax, aFailedToAlloca_18; "Failed to allocate memory to copy SID"
0x180101d4b  mov     [rbp+arg_0], 168h
0x180101d52  mov     [rbp+var_8], rax
0x180101d56  lea     rdx, byte_1801C62D7
0x180101d5d  lea     rax, aStartlistening_0; "StartListeningEx"
0x180101d64  mov     [rbp+var_10], rax
0x180101d68  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180101d6f  mov     [rbp+var_18], rax
0x180101d73  lea     rax, aErrorCondition; "Error condition failed"
0x180101d7a  mov     [rbp+var_20], rax
0x180101d7e  lea     rax, [rbp+var_8]
0x180101d82  mov     [rsp+70h+var_28], rax
0x180101d87  lea     rax, [rbp+var_10]
0x180101d8b  mov     [rsp+70h+var_30], rax
0x180101d90  lea     rax, [rbp+arg_0]
0x180101d94  mov     [rsp+70h+var_38], rax
0x180101d99  lea     rax, [rbp+var_18]
0x180101d9d  mov     [rsp+70h+var_40], rax
0x180101da2  lea     rax, [rbp+arg_10]
0x180101da6  mov     [rsp+70h+var_48], rax
0x180101dab  lea     rax, [rbp+var_20]
0x180101daf  jmp     loc_180101CF0
0x180101db4  mov     qword ptr [r14], 1
0x180101dbb  mov     r8, rsi; pSourceSid
0x180101dbe  mov     rdx, [rdx]; pDestinationSid
0x180101dc1  mov     ecx, r15d; nDestinationSidLength
0x180101dc4  call    cs:__imp_CopySid
0x180101dca  test    eax, eax
0x180101dcc  jnz     loc_180101E74
0x180101dd2  call    cs:__imp_GetLastError
0x180101dd8  mov     ebx, eax
0x180101dda  test    eax, eax
0x180101ddc  jle     short loc_180101DE7
0x180101dde  movzx   ebx, ax
0x180101de1  or      ebx, 80070000h
0x180101de7  mov     eax, cs:CallbackContext
0x180101ded  cmp     eax, 2
0x180101df0  jbe     short loc_180101E6A
0x180101df2  lea     rax, aFailedToCopySi; "Failed to copy SID"
0x180101df9  mov     [rbp+arg_0], 16Ch
0x180101e00  mov     [rbp+var_8], rax
0x180101e04  lea     rdx, byte_1801C6245
0x180101e0b  lea     rax, aStartlistening_0; "StartListeningEx"
0x180101e12  mov     dword ptr [rbp+arg_10], ebx
0x180101e15  mov     [rbp+var_10], rax
0x180101e19  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180101e20  mov     [rbp+var_18], rax
0x180101e24  lea     rax, aErrorCondition; "Error condition failed"
0x180101e2b  mov     [rbp+var_20], rax
0x180101e2f  lea     rax, [rbp+var_8]
0x180101e33  mov     [rsp+70h+var_28], rax
0x180101e38  lea     rax, [rbp+var_10]
0x180101e3c  mov     [rsp+70h+var_30], rax
0x180101e41  lea     rax, [rbp+arg_0]
0x180101e45  mov     [rsp+70h+var_38], rax
0x180101e4a  lea     rax, [rbp+var_18]
0x180101e4e  mov     [rsp+70h+var_40], rax
0x180101e53  lea     rax, [rbp+arg_10]
0x180101e57  mov     [rsp+70h+var_48], rax
0x180101e5c  lea     rax, [rbp+var_20]
0x180101e60  mov     [rsp+70h+var_50], rax
0x180101e65  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180101e6a  test    ebx, ebx
0x180101e6c  jns     loc_180101EF6
0x180101e72  jmp     short loc_180101EEB
0x180101e74  mov     r9d, [rbp+arg_20]; int
0x180101e78  mov     r8d, r12d; int
0x180101e7b  mov     rdx, r13; unsigned __int16 *
0x180101e7e  mov     rcx, rbx; this
0x180101e81  call    ?StartListeningInternal@CRDPENCNamedPipeListener@@IEAAJPEBGHH@Z; CRDPENCNamedPipeListener::StartListeningInternal(ushort const *,int,int)
0x180101e86  mov     ebx, eax
0x180101e88  test    eax, eax
0x180101e8a  jns     short loc_180101EF6
0x180101e8c  mov     ecx, cs:CallbackContext
0x180101e92  cmp     ecx, 3
0x180101e95  jbe     short loc_180101EEB
0x180101e97  lea     rax, aStartlistening_0; "StartListeningEx"
0x180101e9e  mov     [rbp+arg_0], ebx
0x180101ea1  mov     [rbp+arg_10], rax
0x180101ea5  lea     rdx, byte_1801C6297
0x180101eac  lea     rax, aStartlistening; "StartListeningInternal failed"
0x180101eb3  mov     [rbp+var_8], rax
0x180101eb7  lea     rax, aWarningHresult; "Warning HResult failed"
0x180101ebe  mov     [rbp+var_10], rax
0x180101ec2  lea     rax, [rbp+arg_10]
0x180101ec6  mov     [rsp+70h+var_38], rax
0x180101ecb  lea     rax, [rbp+arg_0]
0x180101ecf  mov     [rsp+70h+var_40], rax
0x180101ed4  lea     rax, [rbp+var_8]
0x180101ed8  mov     [rsp+70h+var_48], rax
0x180101edd  lea     rax, [rbp+var_10]
0x180101ee1  mov     [rsp+70h+var_50], rax
0x180101ee6  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180101eeb  mov     rdx, r14
0x180101eee  mov     rcx, rdi
0x180101ef1  call    DeleteSidsArray
0x180101ef6  mov     eax, ebx
0x180101ef8  mov     rbx, [rsp+70h+arg_8]
0x180101f00  add     rsp, 70h
0x180101f04  pop     r15
0x180101f06  pop     r14
0x180101f08  pop     r13
0x180101f0a  pop     r12
0x180101f0c  pop     rdi
0x180101f0d  pop     rsi
0x180101f0e  pop     rbp
0x180101f0f  retn
```
