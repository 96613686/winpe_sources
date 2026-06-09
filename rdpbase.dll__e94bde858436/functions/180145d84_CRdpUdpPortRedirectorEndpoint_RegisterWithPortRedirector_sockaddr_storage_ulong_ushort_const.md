# CRdpUdpPortRedirectorEndpoint::RegisterWithPortRedirector(sockaddr_storage &,ulong,ushort const *)

- ea: `0x180145d84`
- end: `0x180146024`
- name: `?RegisterWithPortRedirector@CRdpUdpPortRedirectorEndpoint@@IEAAJAEAUsockaddr_storage@@KPEBG@Z`
- size: `672`
- prototype: `__int64 __fastcall(CRdpUdpPortRedirectorEndpoint *__hidden this, struct sockaddr_storage *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1801454b0`

## callees

- `0x180001aa0`
- `0x180002550`
- `0x180145d84`
- `0x180146214`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180145edc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180145edc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180146001`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180146001`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180145dd2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180145dd2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180145df4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180145df4`

## string_xrefs

- `0x180145e1c`: `Failed to loadLibrary for UDP port redirector.`
- `0x180145dc3`: `RdpCdvPortRedirect.dll`
- `0x180145de3`: `RdpCdvPortRedirect.dll`
- `0x180145ea4`: `RdpCdvPortRedirect.dll has been already loaded`
- `0x180145e9d`: `RdpCdvPortRedirect.dll loaded`

## pseudocode

```c
__int64 __fastcall CRdpUdpPortRedirectorEndpoint::RegisterWithPortRedirector(
        CRdpUdpPortRedirectorEndpoint *this,
        struct sockaddr_storage *a2,
        int a3,
        const unsigned __int16 *a4)
{
  HMODULE *v4; // rdi
  _QWORD *v5; // r14
  int v10; // r9d
  BOOL ModuleHandle; // r15d
  HMODULE LibraryW; // rax
  int v13; // r8d
  int v14; // ebx
  const char *v15; // rax
  FARPROC ProcAddress; // rax
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  __int16 *v20; // rdx
  const char *v21; // rax
  int v23; // [rsp+50h] [rbp-19h] BYREF
  __int64 v24; // [rsp+58h] [rbp-11h] BYREF
  const char *v25; // [rsp+60h] [rbp-9h] BYREF
  const char *v26; // [rsp+68h] [rbp-1h] BYREF
  const char *v27; // [rsp+70h] [rbp+7h] BYREF
  _QWORD v28[9]; // [rsp+78h] [rbp+Fh] BYREF
  const char *v29; // [rsp+D0h] [rbp+67h] BYREF

  v4 = (HMODULE *)((char *)this + 688);
  v24 = 0;
  v5 = (_QWORD *)((char *)this + 696);
  *((_QWORD *)this + 87) = 0;
  ModuleHandle = GetModuleHandleExW(0, L"RdpCdvPortRedirect.dll", (HMODULE *)this + 86);
  if ( !ModuleHandle )
  {
    if ( !a4 )
      a4 = L"RdpCdvPortRedirect.dll";
    LibraryW = LoadLibraryW(a4);
    *v4 = LibraryW;
    if ( !LibraryW )
    {
      v14 = -2147418113;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v29) = 426;
        v25 = "Failed to loadLibrary for UDP port redirector.";
        v23 = -2147418113;
        v26 = "RegisterWithPortRedirector";
        v27 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpportredirectorendpoint.cpp";
        v28[0] = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          -2147418113,
          (unsigned int)&byte_1801D5A5F,
          v13,
          v10,
          (__int64)v28,
          (__int64)&v23,
          (__int64)&v27,
          (__int64)&v29,
          (__int64)&v26,
          (__int64)&v25);
      }
      goto LABEL_18;
    }
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v15 = "RdpCdvPortRedirect.dll has been already loaded";
    if ( !ModuleHandle )
      v15 = "RdpCdvPortRedirect.dll loaded";
    v29 = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&CallbackContext,
      (unsigned int)byte_1801D5C0D,
      0,
      v10,
      (__int64)&v29);
  }
  ProcAddress = GetProcAddress(*v4, "RegisterUdpPortListener");
  if ( !ProcAddress )
  {
    v19 = -2147418113;
    v14 = -2147418113;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_18;
    LODWORD(v29) = 432;
    v28[0] = "Failed to get address of RegisterUdpPortListener.";
    v20 = word_1801D5E52;
    v23 = -2147418113;
    v27 = "RegisterWithPortRedirector";
    v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpportredirectorendpoint.cpp";
    v21 = "Error condition failed";
    goto LABEL_17;
  }
  LODWORD(v24) = 8;
  HIDWORD(v24) = a3;
  v14 = ((__int64 (__fastcall *)(__int64, CRdpUdpPortRedirectorEndpoint *, __int64 *, struct sockaddr_storage *, _QWORD *))ProcAddress)(
          1,
          this,
          &v24,
          a2,
          v5);
  if ( v14 >= 0 )
    return (unsigned int)v14;
  v19 = (int)CallbackContext;
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v29) = 438;
    v28[0] = "RegisterUdpPortListener call failed";
    v20 = (__int16 *)byte_1801D5C4B;
    v23 = v14;
    v27 = "RegisterWithPortRedirector";
    v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpportredirectorendpoint.cpp";
    v21 = "Error HResult failed";
LABEL_17:
    v25 = v21;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v19,
      (_DWORD)v20,
      v17,
      v18,
      (__int64)&v25,
      (__int64)&v23,
      (__int64)&v26,
      (__int64)&v29,
      (__int64)&v27,
      (__int64)v28);
  }
LABEL_18:
  if ( *v5 )
  {
    CRdpUdpPortRedirectorEndpoint::UnregisterFromPortRedirector(this);
  }
  else if ( *v4 )
  {
    FreeLibrary(*v4);
    *v4 = 0;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180145d84  push    rbp
0x180145d86  push    rbx
0x180145d87  push    rsi
0x180145d88  push    rdi
0x180145d89  push    r12
0x180145d8b  push    r13
0x180145d8d  push    r14
0x180145d8f  push    r15
0x180145d91  lea     rbp, [rsp-1Fh]
0x180145d96  sub     rsp, 88h
0x180145d9d  lea     rdi, [rcx+2B0h]
0x180145da4  mov     [rbp+57h+var_68], 0
0x180145dac  lea     r14, [rcx+2B8h]
0x180145db3  mov     r12d, r8d
0x180145db6  mov     r13, rdx
0x180145db9  mov     qword ptr [r14], 0
0x180145dc0  mov     rsi, rcx
0x180145dc3  lea     rdx, aRdpcdvportredi_0; "RdpCdvPortRedirect.dll"
0x180145dca  mov     r8, rdi; phModule
0x180145dcd  xor     ecx, ecx; dwFlags
0x180145dcf  mov     rbx, r9
0x180145dd2  call    cs:__imp_GetModuleHandleExW
0x180145dd8  mov     r15d, eax
0x180145ddb  test    eax, eax
0x180145ddd  jnz     loc_180145E8F
0x180145de3  lea     rax, aRdpcdvportredi_0; "RdpCdvPortRedirect.dll"
0x180145dea  test    rbx, rbx
0x180145ded  cmovz   rbx, rax
0x180145df1  mov     rcx, rbx; lpLibFileName
0x180145df4  call    cs:__imp_LoadLibraryW
0x180145dfa  mov     [rdi], rax
0x180145dfd  test    rax, rax
0x180145e00  jnz     loc_180145E8F
0x180145e06  mov     eax, cs:CallbackContext
0x180145e0c  mov     ecx, 8000FFFFh
0x180145e11  mov     ebx, ecx
0x180145e13  cmp     eax, 2
0x180145e16  jbe     loc_180145FE9
0x180145e1c  lea     rax, aFailedToLoadli; "Failed to loadLibrary for UDP port redi"...
0x180145e23  mov     dword ptr [rbp+57h+arg_0], 1AAh
0x180145e2a  mov     [rbp+57h+var_60], rax
0x180145e2e  lea     rdx, byte_1801D5A5F
0x180145e35  lea     rax, aRegisterwithpo; "RegisterWithPortRedirector"
0x180145e3c  mov     [rbp+57h+var_70], ecx
0x180145e3f  mov     [rbp+57h+var_58], rax
0x180145e43  lea     rax, aOnecoreTermsrv_69; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180145e4a  mov     [rbp+57h+var_50], rax
0x180145e4e  lea     rax, aErrorCondition; "Error condition failed"
0x180145e55  mov     [rbp+57h+var_48], rax
0x180145e59  lea     rax, [rbp+57h+var_60]
0x180145e5d  mov     [rsp+0C0h+var_78], rax
0x180145e62  lea     rax, [rbp+57h+var_58]
0x180145e66  mov     [rsp+0C0h+var_80], rax
0x180145e6b  lea     rax, [rbp+57h+arg_0]
0x180145e6f  mov     [rsp+0C0h+var_88], rax
0x180145e74  lea     rax, [rbp+57h+var_50]
0x180145e78  mov     [rsp+0C0h+var_90], rax
0x180145e7d  lea     rax, [rbp+57h+var_70]
0x180145e81  mov     [rsp+0C0h+var_98], rax
0x180145e86  lea     rax, [rbp+57h+var_48]
0x180145e8a  jmp     loc_180145FDF
0x180145e8f  mov     eax, cs:CallbackContext
0x180145e95  cmp     eax, 4
0x180145e98  jbe     short loc_180145ED2
0x180145e9a  test    r15d, r15d
0x180145e9d  lea     rcx, aRdpcdvportredi_1; "RdpCdvPortRedirect.dll loaded"
0x180145ea4  lea     rax, aRdpcdvportredi_2; "RdpCdvPortRedirect.dll has been already"...
0x180145eab  cmovz   rax, rcx
0x180145eaf  lea     rdx, byte_1801D5C0D
0x180145eb6  mov     [rbp+57h+arg_0], rax
0x180145eba  lea     rcx, CallbackContext
0x180145ec1  lea     rax, [rbp+57h+arg_0]
0x180145ec5  xor     r8d, r8d
0x180145ec8  mov     [rsp+0C0h+var_A0], rax
0x180145ecd  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180145ed2  mov     rcx, [rdi]; hModule
0x180145ed5  lea     rdx, aRegisterudppor; "RegisterUdpPortListener"
0x180145edc  call    cs:__imp_GetProcAddress
0x180145ee2  test    rax, rax
0x180145ee5  jnz     short loc_180145F38
0x180145ee7  mov     eax, cs:CallbackContext
0x180145eed  mov     ecx, 8000FFFFh
0x180145ef2  mov     ebx, ecx
0x180145ef4  cmp     eax, 2
0x180145ef7  jbe     loc_180145FE9
0x180145efd  lea     rax, aFailedToGetAdd_0; "Failed to get address of RegisterUdpPor"...
0x180145f04  mov     dword ptr [rbp+57h+arg_0], 1B0h
0x180145f0b  mov     [rbp+57h+var_48], rax
0x180145f0f  lea     rdx, word_1801D5E52
0x180145f16  lea     rax, aRegisterwithpo; "RegisterWithPortRedirector"
0x180145f1d  mov     [rbp+57h+var_70], ecx
0x180145f20  mov     [rbp+57h+var_50], rax
0x180145f24  lea     rax, aOnecoreTermsrv_69; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180145f2b  mov     [rbp+57h+var_58], rax
0x180145f2f  lea     rax, aErrorCondition; "Error condition failed"
0x180145f36  jmp     short loc_180145FAA
0x180145f38  mov     r9, r13
0x180145f3b  mov     dword ptr [rbp+57h+var_68], 8
0x180145f42  lea     r8, [rbp+57h+var_68]
0x180145f46  mov     dword ptr [rbp+57h+var_68+4], r12d
0x180145f4a  mov     rdx, rsi
0x180145f4d  mov     [rsp+0C0h+var_A0], r14
0x180145f52  mov     ecx, 1
0x180145f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145f5c  mov     ebx, eax
0x180145f5e  test    eax, eax
0x180145f60  jns     loc_18014600E
0x180145f66  mov     ecx, cs:CallbackContext
0x180145f6c  cmp     ecx, 2
0x180145f6f  jbe     short loc_180145FE9
0x180145f71  lea     rax, aRegisterudppor_0; "RegisterUdpPortListener call failed"
0x180145f78  mov     dword ptr [rbp+57h+arg_0], 1B6h
0x180145f7f  mov     [rbp+57h+var_48], rax
0x180145f83  lea     rdx, byte_1801D5C4B
0x180145f8a  lea     rax, aRegisterwithpo; "RegisterWithPortRedirector"
0x180145f91  mov     [rbp+57h+var_70], ebx
0x180145f94  mov     [rbp+57h+var_50], rax
0x180145f98  lea     rax, aOnecoreTermsrv_69; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180145f9f  mov     [rbp+57h+var_58], rax
0x180145fa3  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180145faa  mov     [rbp+57h+var_60], rax
0x180145fae  lea     rax, [rbp+57h+var_48]
0x180145fb2  mov     [rsp+0C0h+var_78], rax
0x180145fb7  lea     rax, [rbp+57h+var_50]
0x180145fbb  mov     [rsp+0C0h+var_80], rax
0x180145fc0  lea     rax, [rbp+57h+arg_0]
0x180145fc4  mov     [rsp+0C0h+var_88], rax
0x180145fc9  lea     rax, [rbp+57h+var_58]
0x180145fcd  mov     [rsp+0C0h+var_90], rax
0x180145fd2  lea     rax, [rbp+57h+var_70]
0x180145fd6  mov     [rsp+0C0h+var_98], rax
0x180145fdb  lea     rax, [rbp+57h+var_60]
0x180145fdf  mov     [rsp+0C0h+var_A0], rax
0x180145fe4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180145fe9  cmp     qword ptr [r14], 0
0x180145fed  jz      short loc_180145FF9
0x180145fef  mov     rcx, rsi; this
0x180145ff2  call    ?UnregisterFromPortRedirector@CRdpUdpPortRedirectorEndpoint@@IEAAXXZ; CRdpUdpPortRedirectorEndpoint::UnregisterFromPortRedirector(void)
0x180145ff7  jmp     short loc_18014600E
0x180145ff9  mov     rcx, [rdi]; hLibModule
0x180145ffc  test    rcx, rcx
0x180145fff  jz      short loc_18014600E
0x180146001  call    cs:__imp_FreeLibrary
0x180146007  mov     qword ptr [rdi], 0
0x18014600e  mov     eax, ebx
0x180146010  add     rsp, 88h
0x180146017  pop     r15
0x180146019  pop     r14
0x18014601b  pop     r13
0x18014601d  pop     r12
0x18014601f  pop     rdi
0x180146020  pop     rsi
0x180146021  pop     rbx
0x180146022  pop     rbp
0x180146023  retn
```
