# RdsDWMDirectUpdateProcessor::ProcessCompositionSurface(RdpDWMDirectWindowContext *,_DWMIndirectCompositionSurfaceMetadata *)

- ea: `0x18000fcdc`
- end: `0x18000fe5f`
- name: `?ProcessCompositionSurface@RdsDWMDirectUpdateProcessor@@IEAAJPEAVRdpDWMDirectWindowContext@@PEAU_DWMIndirectCompositionSurfaceMetadata@@@Z`
- size: `387`
- prototype: `int(RdsDWMDirectUpdateProcessor *__hidden this, struct RdpDWMDirectWindowContext *, struct _DWMIndirectCompositionSurfaceMetadata *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180010a30`

## callees

- `0x180001724`
- `0x1800022b0`
- `0x18000d4b4`
- `0x18000fcdc`

## string_xrefs

- `0x18000fd30`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x18000fe01`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x18000fd0c`: `No target window for composition surface`
- `0x18000fd25`: `ProcessCompositionSurface`
- `0x18000fdf6`: `ProcessCompositionSurface`
- `0x18000fd92`: `RdsDWMDirectUpdateProcessor::ProcessCompositionSurface surface handle=0x%p`
- `0x18000fddd`: `Failed to create composition surface`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectUpdateProcessor::ProcessCompositionSurface(
        __int64 this,
        struct RdpDWMDirectWindowContext *a2,
        void **a3,
        __int64 a4)
{
  int CompositionSurface; // ebx
  __int16 *v7; // rdx
  const unsigned __int16 **v8; // rax
  const unsigned __int16 **v10; // [rsp+40h] [rbp-30h]
  const char *v11; // [rsp+50h] [rbp-20h] BYREF
  const char *v12; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v13[2]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v14; // [rsp+90h] [rbp+20h] BYREF
  __int64 v15; // [rsp+98h] [rbp+28h] BYREF
  const char *v16; // [rsp+A8h] [rbp+38h] BYREF

  v14 = this;
  if ( a2 )
  {
    if ( (unsigned int)dword_180044008 > 5 )
    {
      v14 = (__int64)*a3;
      v15 = *((_QWORD *)a2 + 8);
      v16 = "RdsDWMDirectUpdateProcessor::ProcessCompositionSurface surface handle=0x%p";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        this,
        (__int64)byte_18003AA83,
        (__int64)a3,
        a4,
        (const unsigned __int16 **)&v16,
        (__int64)&v15,
        (__int64)&v14);
    }
    CompositionSurface = RdpDWMDirectWindowContext::CreateCompositionSurface(a2, *a3);
    if ( CompositionSurface < 0 )
    {
      this = (unsigned int)dword_180044008;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v14) = 1030;
        v16 = "Failed to create composition surface";
        v7 = &word_18003AA36;
        v13[0] = "ProcessCompositionSurface";
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
    CompositionSurface = -2147418113;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v14) = 1016;
      v16 = "No target window for composition surface";
      v7 = word_18003AAC2;
      v11 = "ProcessCompositionSurface";
      v12 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v13[0] = "Error condition failed";
      v10 = (const unsigned __int16 **)&v11;
      v8 = (const unsigned __int16 **)v13;
LABEL_9:
      LODWORD(v15) = CompositionSurface;
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
  return (unsigned int)CompositionSurface;
}

```

## disassembly

```asm
0x18000fcdc  mov     r11, rsp
0x18000fcdf  mov     [r11+8], rcx
0x18000fce3  push    rbp
0x18000fce4  push    rbx
0x18000fce5  push    rdi
0x18000fce6  mov     rbp, rsp
0x18000fce9  sub     rsp, 70h
0x18000fced  mov     eax, cs:dword_180044008
0x18000fcf3  mov     rdi, r8
0x18000fcf6  mov     rbx, rdx
0x18000fcf9  test    rdx, rdx
0x18000fcfc  jnz     short loc_18000FD77
0x18000fcfe  mov     ebx, 8000FFFFh
0x18000fd03  cmp     eax, 2
0x18000fd06  jbe     loc_18000FE55
0x18000fd0c  lea     rax, aNoTargetWindow; "No target window for composition surfac"...
0x18000fd13  mov     dword ptr [rbp+arg_0], 3F8h
0x18000fd1a  mov     [rbp+arg_18], rax
0x18000fd1e  lea     rdx, word_18003AAC2
0x18000fd25  lea     rax, aProcesscomposi_0; "ProcessCompositionSurface"
0x18000fd2c  mov     [rbp+var_20], rax
0x18000fd30  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000fd37  mov     [rbp+var_18], rax
0x18000fd3b  lea     rax, aErrorCondition; "Error condition failed"
0x18000fd42  mov     [rbp+var_10], rax
0x18000fd46  lea     rax, [rbp+arg_18]
0x18000fd4a  mov     [r11-40h], rax
0x18000fd4e  lea     rax, [rbp+var_20]
0x18000fd52  mov     [r11-48h], rax
0x18000fd56  lea     rax, [rbp+arg_0]
0x18000fd5a  mov     [r11-50h], rax
0x18000fd5e  lea     rax, [rbp+var_18]
0x18000fd62  mov     [r11-58h], rax
0x18000fd66  lea     rax, [rbp+arg_8]
0x18000fd6a  mov     [r11-60h], rax
0x18000fd6e  lea     rax, [rbp+var_10]
0x18000fd72  jmp     loc_18000FE48
0x18000fd77  cmp     eax, 5
0x18000fd7a  jbe     short loc_18000FDBD
0x18000fd7c  mov     rax, [r8]
0x18000fd7f  mov     [rbp+arg_0], rax
0x18000fd83  mov     rax, [rdx+40h]
0x18000fd87  lea     rdx, byte_18003AA83
0x18000fd8e  mov     [rbp+arg_8], rax
0x18000fd92  lea     rax, aRdsdwmdirectup_5; "RdsDWMDirectUpdateProcessor::ProcessCom"...
0x18000fd99  mov     [rbp+arg_18], rax
0x18000fd9d  lea     rax, [rbp+arg_0]
0x18000fda1  mov     [rsp+70h+var_40], rax
0x18000fda6  lea     rax, [rbp+arg_8]
0x18000fdaa  mov     [rsp+70h+var_48], rax
0x18000fdaf  lea     rax, [rbp+arg_18]
0x18000fdb3  mov     [rsp+70h+var_50], rax
0x18000fdb8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18000fdbd  mov     rdx, [rdi]; void *
0x18000fdc0  mov     rcx, rbx; this
0x18000fdc3  call    ?CreateCompositionSurface@RdpDWMDirectWindowContext@@QEAAJPEAX@Z; RdpDWMDirectWindowContext::CreateCompositionSurface(void *)
0x18000fdc8  mov     ebx, eax
0x18000fdca  test    eax, eax
0x18000fdcc  jns     loc_18000FE55
0x18000fdd2  mov     ecx, cs:dword_180044008
0x18000fdd8  cmp     ecx, 2
0x18000fddb  jbe     short loc_18000FE55
0x18000fddd  lea     rax, aFailedToCreate_5; "Failed to create composition surface"
0x18000fde4  mov     dword ptr [rbp+arg_0], 406h
0x18000fdeb  mov     [rbp+arg_18], rax
0x18000fdef  lea     rdx, word_18003AA36
0x18000fdf6  lea     rax, aProcesscomposi_0; "ProcessCompositionSurface"
0x18000fdfd  mov     [rbp+var_10], rax
0x18000fe01  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000fe08  mov     [rbp+var_18], rax
0x18000fe0c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18000fe13  mov     [rbp+var_20], rax
0x18000fe17  lea     rax, [rbp+arg_18]
0x18000fe1b  mov     [rsp+70h+var_28], rax
0x18000fe20  lea     rax, [rbp+var_10]
0x18000fe24  mov     [rsp+70h+var_30], rax
0x18000fe29  lea     rax, [rbp+arg_0]
0x18000fe2d  mov     [rsp+70h+var_38], rax
0x18000fe32  lea     rax, [rbp+var_18]
0x18000fe36  mov     [rsp+70h+var_40], rax
0x18000fe3b  lea     rax, [rbp+arg_8]
0x18000fe3f  mov     [rsp+70h+var_48], rax
0x18000fe44  lea     rax, [rbp+var_20]
0x18000fe48  mov     [rsp+70h+var_50], rax
0x18000fe4d  mov     dword ptr [rbp+arg_8], ebx
0x18000fe50  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000fe55  mov     eax, ebx
0x18000fe57  add     rsp, 70h
0x18000fe5b  pop     rdi
0x18000fe5c  pop     rbx
0x18000fe5d  pop     rbp
0x18000fe5e  retn
```
