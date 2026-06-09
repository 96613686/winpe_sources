# CUMRDPSecurityStreamCallback::AuthorizeClient(void *)

- ea: `0x180046180`
- end: `0x1800463a4`
- name: `?AuthorizeClient@CUMRDPSecurityStreamCallback@@UEAAJPEAX@Z`
- size: `548`
- prototype: `__int64 __fastcall(CUMRDPSecurityStreamCallback *this, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x1800457f0`
- `0x180046180`
- `0x18004d58c`
- `0x18004d6a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800462f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800462f2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180046265`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180046265`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800461c6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800461c6`

## string_xrefs

- `0x1800461fb`: `this->AccessCheck failed!`
- `0x18004631a`: `ImpersonateLoggedOnUser failed!`

## pseudocode

```c
__int64 __fastcall CUMRDPSecurityStreamCallback::AuthorizeClient(CUMRDPSecurityStreamCallback *this, void *a2)
{
  CUMRDPSecurityStreamCallback *v2; // rbx
  signed int v4; // ebx
  int v5; // r8d
  int v6; // r9d
  signed int LastError; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  signed int v11; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  const char *v16; // [rsp+50h] [rbp-20h] BYREF
  const char *v17; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v18[2]; // [rsp+60h] [rbp-10h] BYREF
  int v19; // [rsp+90h] [rbp+20h] BYREF
  signed int v20; // [rsp+A0h] [rbp+30h] BYREF
  const char *v21; // [rsp+A8h] [rbp+38h] BYREF

  v2 = (CUMRDPSecurityStreamCallback *)((char *)this - 48);
  if ( *((_QWORD *)this + 3) )
  {
    if ( a2 )
    {
      CUMRDPSecurityStreamCallback::LogUserInfo((CUMRDPSecurityStreamCallback *)((char *)this - 48), a2);
      CUMRDPSecurityStreamCallback::LogSecurityDescriptor(v2);
      if ( ImpersonateLoggedOnUser(a2) )
      {
        v4 = CUMRDPSecurityStreamCallback::AccessCheck(v2);
        if ( v4 < 0 && (unsigned int)dword_1801B76C8 > 2 )
        {
          v16 = "AuthorizeClient";
          v21 = "this->AccessCheck failed!";
          v19 = 7705;
          v18[0] = "Error HResult failed";
          v17 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
          v20 = v4;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            dword_1801B76C8,
            (unsigned int)byte_180191F25,
            v5,
            v6,
            (__int64)v18,
            (__int64)&v20,
            (__int64)&v17,
            (__int64)&v19,
            (__int64)&v16,
            (__int64)&v21);
        }
        if ( !RevertToSelf() )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            v21 = "AuthorizeClient";
            v17 = "RevertToSelf failed!";
            v19 = 7720;
            v18[0] = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
            v20 = v4;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v8,
              (unsigned int)byte_180191E8B,
              v9,
              v10,
              (__int64)&v17,
              (__int64)&v20,
              (__int64)v18,
              (__int64)&v19,
              (__int64)&v21);
          }
        }
      }
      else
      {
        v11 = GetLastError();
        v4 = v11;
        if ( v11 > 0 )
          v4 = (unsigned __int16)v11 | 0x80070000;
        if ( v4 < 0 && (unsigned int)dword_1801B76C8 > 2 )
        {
          v19 = 7710;
          v21 = "ImpersonateLoggedOnUser failed!";
          v18[0] = "AuthorizeClient";
          v16 = "Error HResult failed";
          v17 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
          v20 = v4;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v12,
            (unsigned int)&dword_180191ED4,
            v13,
            v14,
            (__int64)&v16,
            (__int64)&v20,
            (__int64)&v17,
            (__int64)&v19,
            (__int64)v18,
            (__int64)&v21);
        }
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    return 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180046180  mov     [rsp-18h+arg_8], rbx
0x180046185  push    rbp
0x180046186  push    rsi
0x180046187  push    rdi
0x180046188  mov     rbp, rsp
0x18004618b  sub     rsp, 70h
0x18004618f  lea     rbx, [rcx-30h]
0x180046193  mov     rdi, rdx
0x180046196  cmp     qword ptr [rbx+48h], 0
0x18004619b  jnz     short loc_1800461A4
0x18004619d  xor     ebx, ebx
0x18004619f  jmp     loc_180046392
0x1800461a4  test    rdi, rdi
0x1800461a7  jnz     short loc_1800461B3
0x1800461a9  mov     ebx, 80070057h
0x1800461ae  jmp     loc_180046392
0x1800461b3  mov     rcx, rbx; this
0x1800461b6  call    ?LogUserInfo@CUMRDPSecurityStreamCallback@@AEBAXPEAX@Z; CUMRDPSecurityStreamCallback::LogUserInfo(void *)
0x1800461bb  mov     rcx, rbx; this
0x1800461be  call    ?LogSecurityDescriptor@CUMRDPSecurityStreamCallback@@AEBAXXZ; CUMRDPSecurityStreamCallback::LogSecurityDescriptor(void)
0x1800461c3  mov     rcx, rdi; hToken
0x1800461c6  call    cs:__imp_ImpersonateLoggedOnUser
0x1800461cc  test    eax, eax
0x1800461ce  jz      loc_1800462F2
0x1800461d4  mov     rcx, rbx; this
0x1800461d7  call    ?AccessCheck@CUMRDPSecurityStreamCallback@@AEAAJXZ; CUMRDPSecurityStreamCallback::AccessCheck(void)
0x1800461dc  lea     rdi, aAuthorizeclien; "AuthorizeClient"
0x1800461e3  mov     ebx, eax
0x1800461e5  lea     rsi, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x1800461ec  test    eax, eax
0x1800461ee  jns     short loc_180046265
0x1800461f0  mov     ecx, cs:dword_1801B76C8
0x1800461f6  cmp     ecx, 2
0x1800461f9  jbe     short loc_180046265
0x1800461fb  lea     rax, aThisAccesschec; "this->AccessCheck failed!"
0x180046202  mov     [rbp+var_20], rdi
0x180046206  mov     [rbp+arg_18], rax
0x18004620a  lea     rdx, byte_180191F25
0x180046211  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180046218  mov     [rbp+arg_0], 1E19h
0x18004621f  mov     [rbp+var_10], rax
0x180046223  lea     rax, [rbp+arg_18]
0x180046227  mov     [rsp+70h+var_28], rax
0x18004622c  lea     rax, [rbp+var_20]
0x180046230  mov     [rsp+70h+var_30], rax
0x180046235  lea     rax, [rbp+arg_0]
0x180046239  mov     [rsp+70h+var_38], rax
0x18004623e  lea     rax, [rbp+var_18]
0x180046242  mov     [rsp+70h+var_40], rax
0x180046247  lea     rax, [rbp+arg_10]
0x18004624b  mov     [rsp+70h+var_48], rax
0x180046250  lea     rax, [rbp+var_10]
0x180046254  mov     [rsp+70h+var_50], rax
0x180046259  mov     [rbp+var_18], rsi
0x18004625d  mov     [rbp+arg_10], ebx
0x180046260  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180046265  call    cs:__imp_RevertToSelf
0x18004626b  test    eax, eax
0x18004626d  jnz     loc_180046392
0x180046273  call    cs:__imp_GetLastError
0x180046279  mov     ebx, eax
0x18004627b  test    eax, eax
0x18004627d  jle     short loc_180046288
0x18004627f  movzx   ebx, ax
0x180046282  or      ebx, 80070000h
0x180046288  mov     eax, cs:dword_1801B76C8
0x18004628e  cmp     eax, 2
0x180046291  jbe     loc_180046392
0x180046297  lea     rax, aReverttoselfFa; "RevertToSelf failed!"
0x18004629e  mov     [rbp+arg_18], rdi
0x1800462a2  mov     [rbp+var_18], rax
0x1800462a6  lea     rdx, byte_180191E8B
0x1800462ad  lea     rax, [rbp+arg_18]
0x1800462b1  mov     [rbp+arg_0], 1E28h
0x1800462b8  mov     [rsp+70h+var_30], rax
0x1800462bd  lea     rax, [rbp+arg_0]
0x1800462c1  mov     [rsp+70h+var_38], rax
0x1800462c6  lea     rax, [rbp+var_10]
0x1800462ca  mov     [rsp+70h+var_40], rax
0x1800462cf  lea     rax, [rbp+arg_10]
0x1800462d3  mov     [rsp+70h+var_48], rax
0x1800462d8  lea     rax, [rbp+var_18]
0x1800462dc  mov     [rsp+70h+var_50], rax
0x1800462e1  mov     [rbp+var_10], rsi
0x1800462e5  mov     [rbp+arg_10], ebx
0x1800462e8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800462ed  jmp     loc_180046392
0x1800462f2  call    cs:__imp_GetLastError
0x1800462f8  mov     ebx, eax
0x1800462fa  test    eax, eax
0x1800462fc  jle     short loc_180046307
0x1800462fe  movzx   ebx, ax
0x180046301  or      ebx, 80070000h
0x180046307  test    ebx, ebx
0x180046309  jns     loc_180046392
0x18004630f  mov     eax, cs:dword_1801B76C8
0x180046315  cmp     eax, 2
0x180046318  jbe     short loc_180046392
0x18004631a  lea     rax, aImpersonatelog; "ImpersonateLoggedOnUser failed!"
0x180046321  mov     [rbp+arg_0], 1E1Eh
0x180046328  mov     [rbp+arg_18], rax
0x18004632c  lea     rdi, aAuthorizeclien; "AuthorizeClient"
0x180046333  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18004633a  mov     [rbp+var_10], rdi
0x18004633e  mov     [rbp+var_20], rax
0x180046342  lea     rsi, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180046349  lea     rax, [rbp+arg_18]
0x18004634d  mov     [rbp+var_18], rsi
0x180046351  mov     [rsp+70h+var_28], rax
0x180046356  lea     rdx, dword_180191ED4
0x18004635d  lea     rax, [rbp+var_10]
0x180046361  mov     [rbp+arg_10], ebx
0x180046364  mov     [rsp+70h+var_30], rax
0x180046369  lea     rax, [rbp+arg_0]
0x18004636d  mov     [rsp+70h+var_38], rax
0x180046372  lea     rax, [rbp+var_18]
0x180046376  mov     [rsp+70h+var_40], rax
0x18004637b  lea     rax, [rbp+arg_10]
0x18004637f  mov     [rsp+70h+var_48], rax
0x180046384  lea     rax, [rbp+var_20]
0x180046388  mov     [rsp+70h+var_50], rax
0x18004638d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180046392  mov     eax, ebx
0x180046394  mov     rbx, [rsp+70h+arg_8]
0x18004639c  add     rsp, 70h
0x1800463a0  pop     rdi
0x1800463a1  pop     rsi
0x1800463a2  pop     rbp
0x1800463a3  retn
```
