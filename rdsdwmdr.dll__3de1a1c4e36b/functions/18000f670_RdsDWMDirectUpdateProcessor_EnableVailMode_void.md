# RdsDWMDirectUpdateProcessor::EnableVailMode(void)

- ea: `0x18000f670`
- end: `0x18000f795`
- name: `?EnableVailMode@RdsDWMDirectUpdateProcessor@@IEAAJXZ`
- size: `293`
- prototype: `__int64 __fastcall(RdsDWMDirectUpdateProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180010a30`

## callees

- `0x1800010f8`
- `0x18000160c`
- `0x18000f52c`
- `0x18000f670`
- `0x180019ccc`
- `0x180019d58`

## import_xrefs

- `GDI32!D3DKMTVailConnect` at `0x18000f67e`
- `GDI32!D3DKMTVailConnect` at `0x18000f67e`

## string_xrefs

- `0x18000f6c5`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectUpdateProcessor::EnableVailMode(RdsDWMDirectUpdateProcessor *this)
{
  int v2; // eax
  unsigned __int16 *v3; // r8
  __int64 v4; // r9
  int v5; // ebx
  int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  const char *v10; // [rsp+50h] [rbp-10h] BYREF
  const char *v11; // [rsp+58h] [rbp-8h] BYREF
  const char *v12; // [rsp+88h] [rbp+28h] BYREF
  int v13; // [rsp+90h] [rbp+30h] BYREF
  const char *v14; // [rsp+98h] [rbp+38h] BYREF

  v2 = D3DKMTVailConnect();
  v5 = v2;
  if ( (int)(v2 + 0x80000000) < 0 || v2 == -1073740528 )
  {
    v6 = 0;
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v12 = "VAIL mode connected";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        0x80000000LL,
        (__int64)byte_180039B33,
        (__int64)v3,
        v4,
        (const unsigned __int16 **)&v12);
    }
    RDSDWMDirectTraceLogging::LogVAILModeState(
      (RdsDWMDirectUpdateProcessor *)((char *)this + 92),
      (struct _GUID *)&stru_180032700,
      v3);
    *((_DWORD *)this + 42) = 1;
    if ( *((_DWORD *)this + 44) )
      RdsDWMDirectUpdateProcessor::EnableVailMMCSS(this, 1, v7, v8);
  }
  else
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v12) = 1519;
      v14 = "EnableVailMode";
      v10 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v13 = v2 | 0x10000000;
      v11 = "D3DKMTVailConnect failed! Error: %!STATUS!";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0x80000000LL,
        (__int64)&dword_180039B54,
        (__int64)v3,
        v4,
        (const unsigned __int16 **)&v11,
        (__int64)&v13,
        (const unsigned __int16 **)&v10,
        (__int64)&v12,
        (const unsigned __int16 **)&v14);
    }
    v6 = v5 | 0x10000000;
    if ( v6 < 0 )
      RDSDWMDirectTraceLogging::LogVAILModeError(
        (RdsDWMDirectUpdateProcessor *)((char *)this + 92),
        (struct _GUID *)&stru_180032700,
        (unsigned __int16 *)(unsigned int)v6,
        v4);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000f670  push    rbp
0x18000f672  push    rbx
0x18000f673  push    rdi
0x18000f674  mov     rbp, rsp
0x18000f677  sub     rsp, 60h
0x18000f67b  mov     rdi, rcx
0x18000f67e  call    cs:__imp_D3DKMTVailConnect
0x18000f684  mov     ecx, 80000000h
0x18000f689  mov     ebx, eax
0x18000f68b  add     eax, ecx
0x18000f68d  test    ecx, eax
0x18000f68f  jnz     loc_18000F733
0x18000f695  cmp     ebx, 0C0000510h
0x18000f69b  jz      loc_18000F733
0x18000f6a1  mov     eax, cs:dword_180044008
0x18000f6a7  cmp     eax, 2
0x18000f6aa  jbe     short loc_18000F716
0x18000f6ac  lea     rax, aEnablevailmode; "EnableVailMode"
0x18000f6b3  mov     dword ptr [rbp+arg_8], 5EFh
0x18000f6ba  mov     [rbp+arg_18], rax
0x18000f6be  lea     rdx, dword_180039B54
0x18000f6c5  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000f6cc  mov     [rbp+var_10], rax
0x18000f6d0  mov     eax, ebx
0x18000f6d2  bts     eax, 1Ch
0x18000f6d6  mov     [rbp+arg_10], eax
0x18000f6d9  lea     rax, aD3dkmtvailconn; "D3DKMTVailConnect failed! Error: %!STAT"...
0x18000f6e0  mov     [rbp+var_8], rax
0x18000f6e4  lea     rax, [rbp+arg_18]
0x18000f6e8  mov     [rsp+60h+var_20], rax
0x18000f6ed  lea     rax, [rbp+arg_8]
0x18000f6f1  mov     [rsp+60h+var_28], rax
0x18000f6f6  lea     rax, [rbp+var_10]
0x18000f6fa  mov     [rsp+60h+var_30], rax
0x18000f6ff  lea     rax, [rbp+arg_10]
0x18000f703  mov     [rsp+60h+var_38], rax
0x18000f708  lea     rax, [rbp+var_8]
0x18000f70c  mov     [rsp+60h+var_40], rax
0x18000f711  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000f716  or      ebx, 10000000h
0x18000f71c  jge     short loc_18000F78B
0x18000f71e  lea     rcx, [rdi+5Ch]; this
0x18000f722  mov     r8d, ebx; unsigned __int16 *
0x18000f725  lea     rdx, stru_180032700; struct _GUID *
0x18000f72c  call    ?LogVAILModeError@RDSDWMDirectTraceLogging@@YAXPEAU_GUID@@PEAGJ@Z; RDSDWMDirectTraceLogging::LogVAILModeError(_GUID *,ushort *,long)
0x18000f731  jmp     short loc_18000F78B
0x18000f733  mov     eax, cs:dword_180044008
0x18000f739  xor     ebx, ebx
0x18000f73b  cmp     eax, 4
0x18000f73e  jbe     short loc_18000F760
0x18000f740  lea     rax, aVailModeConnec; "VAIL mode connected"
0x18000f747  mov     [rbp+arg_8], rax
0x18000f74b  lea     rdx, byte_180039B33
0x18000f752  lea     rax, [rbp+arg_8]
0x18000f756  mov     [rsp+60h+var_40], rax
0x18000f75b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000f760  lea     rcx, [rdi+5Ch]; this
0x18000f764  lea     rdx, stru_180032700; struct _GUID *
0x18000f76b  call    ?LogVAILModeState@RDSDWMDirectTraceLogging@@YAXPEAU_GUID@@PEAG@Z; RDSDWMDirectTraceLogging::LogVAILModeState(_GUID *,ushort *)
0x18000f770  mov     edx, 1; int
0x18000f775  mov     [rdi+0A8h], edx
0x18000f77b  cmp     [rdi+0B0h], ebx
0x18000f781  jz      short loc_18000F78B
0x18000f783  mov     rcx, rdi; this
0x18000f786  call    ?EnableVailMMCSS@RdsDWMDirectUpdateProcessor@@IEAAJH@Z; RdsDWMDirectUpdateProcessor::EnableVailMMCSS(int)
0x18000f78b  mov     eax, ebx
0x18000f78d  add     rsp, 60h
0x18000f791  pop     rdi
0x18000f792  pop     rbx
0x18000f793  pop     rbp
0x18000f794  retn
```
