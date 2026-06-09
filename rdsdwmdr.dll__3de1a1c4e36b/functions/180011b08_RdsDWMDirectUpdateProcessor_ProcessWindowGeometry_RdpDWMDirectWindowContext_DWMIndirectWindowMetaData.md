# RdsDWMDirectUpdateProcessor::ProcessWindowGeometry(RdpDWMDirectWindowContext *,_DWMIndirectWindowMetaData *)

- ea: `0x180011b08`
- end: `0x180011c7e`
- name: `?ProcessWindowGeometry@RdsDWMDirectUpdateProcessor@@IEAAJPEAVRdpDWMDirectWindowContext@@PEAU_DWMIndirectWindowMetaData@@@Z`
- size: `374`
- prototype: `int(RdsDWMDirectUpdateProcessor *__hidden this, struct RdpDWMDirectWindowContext *, struct _DWMIndirectWindowMetaData *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180010a30`

## callees

- `0x180001724`
- `0x180001bfc`
- `0x18000ef18`
- `0x180011b08`

## string_xrefs

- `0x180011b5c`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180011c20`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180011b38`: `No target window for window geometry update.`
- `0x180011bb7`: `RdsDWMDirectUpdateProcessor::ProcessWindowGeometry.`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectUpdateProcessor::ProcessWindowGeometry(
        __int64 this,
        struct RdpDWMDirectWindowContext *a2,
        struct _DWMIndirectWindowMetaData *a3,
        __int64 a4)
{
  int v6; // ebx
  char *v7; // rdx
  const unsigned __int16 **v8; // rax
  const unsigned __int16 **v10; // [rsp+40h] [rbp-30h]
  const char *v11; // [rsp+50h] [rbp-20h] BYREF
  const char *v12; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v13[2]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v14; // [rsp+90h] [rbp+20h] BYREF
  const char *v15; // [rsp+98h] [rbp+28h] BYREF
  const char *v16; // [rsp+A8h] [rbp+38h] BYREF

  v14 = this;
  if ( a2 )
  {
    if ( (unsigned int)dword_180044008 > 5 )
    {
      v14 = *((_QWORD *)a2 + 8);
      v15 = "RdsDWMDirectUpdateProcessor::ProcessWindowGeometry.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        this,
        (__int64)qword_18003ADF8,
        (__int64)a3,
        a4,
        (const unsigned __int16 **)&v15,
        (__int64)&v14);
    }
    v6 = RdpDWMDirectWindowContext::Resize(a2, *(_DWORD *)a3, *((_DWORD *)a3 + 1));
    if ( v6 < 0 )
    {
      this = (unsigned int)dword_180044008;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v14) = 855;
        v16 = "Failed to resize the rendering context";
        v7 = byte_18003ADAB;
        v13[0] = "ProcessWindowGeometry";
        v12 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v11 = "Error HResult failed";
        v10 = (const unsigned __int16 **)v13;
        v8 = (const unsigned __int16 **)&v11;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v6 = -2147418113;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v14) = 847;
      v16 = "No target window for window geometry update.";
      v7 = byte_18003AE23;
      v11 = "ProcessWindowGeometry";
      v12 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v13[0] = "Error condition failed";
      v10 = (const unsigned __int16 **)&v11;
      v8 = (const unsigned __int16 **)v13;
LABEL_9:
      LODWORD(v15) = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        this,
        (__int64)v7,
        (__int64)a3,
        a4,
        v8,
        (__int64)&v15,
        (const unsigned __int16 **)&v12,
        (__int64)&v14,
        v10,
        (const unsigned __int16 **)&v16);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180011b08  mov     r11, rsp
0x180011b0b  mov     [r11+8], rcx
0x180011b0f  push    rbp
0x180011b10  push    rbx
0x180011b11  push    rdi
0x180011b12  mov     rbp, rsp
0x180011b15  sub     rsp, 70h
0x180011b19  mov     eax, cs:dword_180044008
0x180011b1f  mov     rdi, r8
0x180011b22  mov     rbx, rdx
0x180011b25  test    rdx, rdx
0x180011b28  jnz     short loc_180011BA3
0x180011b2a  mov     ebx, 8000FFFFh
0x180011b2f  cmp     eax, 2
0x180011b32  jbe     loc_180011C74
0x180011b38  lea     rax, aNoTargetWindow_6; "No target window for window geometry up"...
0x180011b3f  mov     dword ptr [rbp+arg_0], 34Fh
0x180011b46  mov     [rbp+arg_18], rax
0x180011b4a  lea     rdx, byte_18003AE23
0x180011b51  lea     rax, aProcesswindowg; "ProcessWindowGeometry"
0x180011b58  mov     [rbp+var_20], rax
0x180011b5c  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180011b63  mov     [rbp+var_18], rax
0x180011b67  lea     rax, aErrorCondition; "Error condition failed"
0x180011b6e  mov     [rbp+var_10], rax
0x180011b72  lea     rax, [rbp+arg_18]
0x180011b76  mov     [r11-40h], rax
0x180011b7a  lea     rax, [rbp+var_20]
0x180011b7e  mov     [r11-48h], rax
0x180011b82  lea     rax, [rbp+arg_0]
0x180011b86  mov     [r11-50h], rax
0x180011b8a  lea     rax, [rbp+var_18]
0x180011b8e  mov     [r11-58h], rax
0x180011b92  lea     rax, [rbp+arg_8]
0x180011b96  mov     [r11-60h], rax
0x180011b9a  lea     rax, [rbp+var_10]
0x180011b9e  jmp     loc_180011C67
0x180011ba3  cmp     eax, 5
0x180011ba6  jbe     short loc_180011BD9
0x180011ba8  mov     rax, [rdx+40h]
0x180011bac  lea     rdx, qword_18003ADF8
0x180011bb3  mov     [rbp+arg_0], rax
0x180011bb7  lea     rax, aRdsdwmdirectup_0; "RdsDWMDirectUpdateProcessor::ProcessWin"...
0x180011bbe  mov     [rbp+arg_8], rax
0x180011bc2  lea     rax, [rbp+arg_0]
0x180011bc6  mov     [rsp+70h+var_48], rax
0x180011bcb  lea     rax, [rbp+arg_8]
0x180011bcf  mov     [rsp+70h+var_50], rax
0x180011bd4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180011bd9  mov     r8d, [rdi+4]; unsigned int
0x180011bdd  mov     rcx, rbx; this
0x180011be0  mov     edx, [rdi]; unsigned int
0x180011be2  call    ?Resize@RdpDWMDirectWindowContext@@QEAAJII@Z; RdpDWMDirectWindowContext::Resize(uint,uint)
0x180011be7  mov     ebx, eax
0x180011be9  test    eax, eax
0x180011beb  jns     loc_180011C74
0x180011bf1  mov     ecx, cs:dword_180044008
0x180011bf7  cmp     ecx, 2
0x180011bfa  jbe     short loc_180011C74
0x180011bfc  lea     rax, aFailedToResize; "Failed to resize the rendering context"
0x180011c03  mov     dword ptr [rbp+arg_0], 357h
0x180011c0a  mov     [rbp+arg_18], rax
0x180011c0e  lea     rdx, byte_18003ADAB
0x180011c15  lea     rax, aProcesswindowg; "ProcessWindowGeometry"
0x180011c1c  mov     [rbp+var_10], rax
0x180011c20  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180011c27  mov     [rbp+var_18], rax
0x180011c2b  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180011c32  mov     [rbp+var_20], rax
0x180011c36  lea     rax, [rbp+arg_18]
0x180011c3a  mov     [rsp+70h+var_28], rax
0x180011c3f  lea     rax, [rbp+var_10]
0x180011c43  mov     [rsp+70h+var_30], rax
0x180011c48  lea     rax, [rbp+arg_0]
0x180011c4c  mov     [rsp+70h+var_38], rax
0x180011c51  lea     rax, [rbp+var_18]
0x180011c55  mov     [rsp+70h+var_40], rax
0x180011c5a  lea     rax, [rbp+arg_8]
0x180011c5e  mov     [rsp+70h+var_48], rax
0x180011c63  lea     rax, [rbp+var_20]
0x180011c67  mov     [rsp+70h+var_50], rax
0x180011c6c  mov     dword ptr [rbp+arg_8], ebx
0x180011c6f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180011c74  mov     eax, ebx
0x180011c76  add     rsp, 70h
0x180011c7a  pop     rdi
0x180011c7b  pop     rbx
0x180011c7c  pop     rbp
0x180011c7d  retn
```
