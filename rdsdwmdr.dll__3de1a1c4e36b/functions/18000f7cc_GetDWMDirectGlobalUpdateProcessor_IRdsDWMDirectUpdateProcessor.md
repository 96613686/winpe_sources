# GetDWMDirectGlobalUpdateProcessor(IRdsDWMDirectUpdateProcessor * *)

- ea: `0x18000f7cc`
- end: `0x18000f8a8`
- name: `?GetDWMDirectGlobalUpdateProcessor@@YAJPEAPEAUIRdsDWMDirectUpdateProcessor@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(struct IRdsDWMDirectUpdateProcessor **)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180004cbc`

## callees

- `0x1800010f8`
- `0x18000160c`
- `0x18000f7cc`
- `0x18000fb78`

## string_xrefs

- `0x18000f84c`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x18000f833`: `GetDWMDirectGlobalUpdateProcessor`
- `0x18000f85a`: `The update processor failed initialization.`

## pseudocode

```c
__int64 __fastcall GetDWMDirectGlobalUpdateProcessor(struct IRdsDWMDirectUpdateProcessor **a1)
{
  __int64 v2; // rcx
  int v3; // ebx
  __int64 v4; // r8
  __int64 v5; // r9
  const char *v7; // [rsp+50h] [rbp-10h] BYREF
  const char *v8; // [rsp+80h] [rbp+20h] BYREF
  int v9; // [rsp+88h] [rbp+28h] BYREF
  const char *v10; // [rsp+90h] [rbp+30h] BYREF
  const char *v11; // [rsp+98h] [rbp+38h] BYREF

  if ( a1 )
  {
    v3 = RdsDWMDirectUpdateProcessor::Initialize((RdsDWMDirectUpdateProcessor *)a1);
    if ( v3 < 0 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v8) = 1589;
        v10 = "GetDWMDirectGlobalUpdateProcessor";
        v9 = v3;
        v11 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v7 = "The update processor failed initialization.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v2,
          (__int64)byte_180039ACD,
          v4,
          v5,
          (const unsigned __int16 **)&v7,
          (__int64)&v9,
          (const unsigned __int16 **)&v11,
          (__int64)&v8,
          (const unsigned __int16 **)&v10);
      }
    }
    else
    {
      if ( (unsigned int)dword_180044008 > 4 )
      {
        v8 = "Returning a global HiDef processor instance.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v2,
          (__int64)word_180039B12,
          v4,
          v5,
          (const unsigned __int16 **)&v8);
      }
      _InterlockedIncrement(&dword_1800440E4);
      v3 = 0;
      *a1 = (struct IRdsDWMDirectUpdateProcessor *)g_Processor;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000f7cc  push    rbp
0x18000f7ce  push    rbx
0x18000f7cf  push    rdi
0x18000f7d0  mov     rbp, rsp
0x18000f7d3  sub     rsp, 60h
0x18000f7d7  mov     rdi, rcx
0x18000f7da  test    rcx, rcx
0x18000f7dd  jz      loc_18000F899
0x18000f7e3  call    ?Initialize@RdsDWMDirectUpdateProcessor@@IEAAJXZ; RdsDWMDirectUpdateProcessor::Initialize(void)
0x18000f7e8  mov     ebx, eax
0x18000f7ea  test    eax, eax
0x18000f7ec  mov     eax, cs:dword_180044008
0x18000f7f2  js      short loc_18000F82E
0x18000f7f4  cmp     eax, 4
0x18000f7f7  jbe     short loc_18000F819
0x18000f7f9  lea     rax, aReturningAGlob; "Returning a global HiDef processor inst"...
0x18000f800  mov     [rbp+arg_0], rax
0x18000f804  lea     rdx, word_180039B12
0x18000f80b  lea     rax, [rbp+arg_0]
0x18000f80f  mov     [rsp+60h+var_40], rax
0x18000f814  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000f819  lock inc cs:dword_1800440E4
0x18000f820  lea     rax, ?g_Processor@@3VRdsDWMDirectUpdateProcessor@@A; RdsDWMDirectUpdateProcessor g_Processor
0x18000f827  xor     ebx, ebx
0x18000f829  mov     [rdi], rax
0x18000f82c  jmp     short loc_18000F89E
0x18000f82e  cmp     eax, 2
0x18000f831  jbe     short loc_18000F89E
0x18000f833  lea     rax, aGetdwmdirectgl; "GetDWMDirectGlobalUpdateProcessor"
0x18000f83a  mov     dword ptr [rbp+arg_0], 635h
0x18000f841  mov     [rbp+arg_10], rax
0x18000f845  lea     rdx, byte_180039ACD
0x18000f84c  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000f853  mov     [rbp+arg_8], ebx
0x18000f856  mov     [rbp+arg_18], rax
0x18000f85a  lea     rax, aTheUpdateProce; "The update processor failed initializat"...
0x18000f861  mov     [rbp+var_10], rax
0x18000f865  lea     rax, [rbp+arg_10]
0x18000f869  mov     [rsp+60h+var_20], rax
0x18000f86e  lea     rax, [rbp+arg_0]
0x18000f872  mov     [rsp+60h+var_28], rax
0x18000f877  lea     rax, [rbp+arg_18]
0x18000f87b  mov     [rsp+60h+var_30], rax
0x18000f880  lea     rax, [rbp+arg_8]
0x18000f884  mov     [rsp+60h+var_38], rax
0x18000f889  lea     rax, [rbp+var_10]
0x18000f88d  mov     [rsp+60h+var_40], rax
0x18000f892  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000f897  jmp     short loc_18000F89E
0x18000f899  mov     ebx, 80004003h
0x18000f89e  mov     eax, ebx
0x18000f8a0  add     rsp, 60h
0x18000f8a4  pop     rdi
0x18000f8a5  pop     rbx
0x18000f8a6  pop     rbp
0x18000f8a7  retn
```
