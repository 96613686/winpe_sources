# RdsDWMDirectUpdateProcessor::ProcessWindowDirtyRegion(RdpDWMDirectWindowContext *,_DWMIndirectDirtyMetadata *)

- ea: `0x18001196c`
- end: `0x180011aff`
- name: `?ProcessWindowDirtyRegion@RdsDWMDirectUpdateProcessor@@IEAAJPEAVRdpDWMDirectWindowContext@@PEAU_DWMIndirectDirtyMetadata@@@Z`
- size: `403`
- prototype: `int(RdsDWMDirectUpdateProcessor *__hidden this, struct RdpDWMDirectWindowContext *, struct _DWMIndirectDirtyMetadata *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x180010a30`

## callees

- `0x180001724`
- `0x180001bfc`
- `0x18000cf04`
- `0x18001196c`

## string_xrefs

- `0x1800119c3`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180011a99`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x18001199f`: `No target window for dirty update.`
- `0x180011a1e`: `RdsDWMDirectUpdateProcessor::ProcessWindowDirtyRegion`
- `0x180011a75`: `Failed to copy the dirty region`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectUpdateProcessor::ProcessWindowDirtyRegion(
        __int64 this,
        struct RdpDWMDirectWindowContext *a2,
        struct _DWMIndirectDirtyMetadata *a3,
        __int64 a4)
{
  RdsDWMDirectUpdateProcessor *v6; // rsi
  int v7; // ebx
  char *v8; // rdx
  const char **v9; // rax
  HDC v10; // r8
  const char **v12; // [rsp+30h] [rbp-40h]
  const char **v13; // [rsp+40h] [rbp-30h]
  const char **v14; // [rsp+48h] [rbp-28h]
  const char *v15; // [rsp+50h] [rbp-20h] BYREF
  const char *v16; // [rsp+58h] [rbp-18h] BYREF
  const char *v17; // [rsp+60h] [rbp-10h] BYREF
  const char *v18; // [rsp+68h] [rbp-8h] BYREF
  __int64 v19; // [rsp+98h] [rbp+28h] BYREF
  const char *v20; // [rsp+A8h] [rbp+38h] BYREF

  v6 = (RdsDWMDirectUpdateProcessor *)this;
  if ( a2 )
  {
    if ( (unsigned int)dword_180044008 > 5 )
    {
      v19 = *((_QWORD *)a2 + 8);
      v20 = "RdsDWMDirectUpdateProcessor::ProcessWindowDirtyRegion";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        this,
        (__int64)&dword_18003AB5C,
        (__int64)a3,
        a4,
        (const unsigned __int16 **)&v20,
        (__int64)&v19);
    }
    v10 = (HDC)*((_QWORD *)a3 + 1);
    if ( !v10 )
    {
      v10 = (HDC)*((_QWORD *)v6 + 8);
      *((_QWORD *)a3 + 1) = v10;
    }
    v7 = RdpDWMDirectWindowContext::CopyDirtyRegion(a2, *(HRGN *)a3, v10, (struct tagPOINT *)a3 + 2);
    if ( v7 < 0 )
    {
      this = (unsigned int)dword_180044008;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v19) = 988;
        v18 = "Failed to copy the dirty region";
        v8 = &byte_18003AB0F;
        v17 = "ProcessWindowDirtyRegion";
        v16 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v15 = "Error HResult failed";
        v14 = &v18;
        v13 = &v17;
        v12 = &v16;
        v9 = &v15;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v7 = -2147418113;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v19) = 967;
      v15 = "No target window for dirty update.";
      v8 = &byte_18003AB87;
      v16 = "ProcessWindowDirtyRegion";
      v17 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v18 = "Error condition failed";
      v14 = &v15;
      v13 = &v16;
      v12 = &v17;
      v9 = &v18;
LABEL_11:
      LODWORD(v20) = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        this,
        (__int64)v8,
        (__int64)a3,
        a4,
        (const unsigned __int16 **)v9,
        (__int64)&v20,
        (const unsigned __int16 **)v12,
        (__int64)&v19,
        (const unsigned __int16 **)v13,
        (const unsigned __int16 **)v14);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001196c  mov     r11, rsp
0x18001196f  mov     [r11+8], rbx
0x180011973  push    rbp
0x180011974  push    rsi
0x180011975  push    rdi
0x180011976  mov     rbp, rsp
0x180011979  sub     rsp, 70h
0x18001197d  mov     eax, cs:dword_180044008
0x180011983  mov     rbx, r8
0x180011986  mov     rdi, rdx
0x180011989  mov     rsi, rcx
0x18001198c  test    rdx, rdx
0x18001198f  jnz     short loc_180011A0A
0x180011991  mov     ebx, 8000FFFFh
0x180011996  cmp     eax, 2
0x180011999  jbe     loc_180011AED
0x18001199f  lea     rax, aNoTargetWindow_4; "No target window for dirty update."
0x1800119a6  mov     dword ptr [rbp+arg_8], 3C7h
0x1800119ad  mov     [rbp+var_20], rax
0x1800119b1  lea     rdx, byte_18003AB87
0x1800119b8  lea     rax, aProcesswindowd; "ProcessWindowDirtyRegion"
0x1800119bf  mov     [rbp+var_18], rax
0x1800119c3  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x1800119ca  mov     [rbp+var_10], rax
0x1800119ce  lea     rax, aErrorCondition; "Error condition failed"
0x1800119d5  mov     [rbp+var_8], rax
0x1800119d9  lea     rax, [rbp+var_20]
0x1800119dd  mov     [r11-40h], rax
0x1800119e1  lea     rax, [rbp+var_18]
0x1800119e5  mov     [r11-48h], rax
0x1800119e9  lea     rax, [rbp+arg_8]
0x1800119ed  mov     [r11-50h], rax
0x1800119f1  lea     rax, [rbp+var_10]
0x1800119f5  mov     [r11-58h], rax
0x1800119f9  lea     rax, [rbp+arg_18]
0x1800119fd  mov     [r11-60h], rax
0x180011a01  lea     rax, [rbp+var_8]
0x180011a05  jmp     loc_180011AE0
0x180011a0a  cmp     eax, 5
0x180011a0d  jbe     short loc_180011A40
0x180011a0f  mov     rax, [rdx+40h]
0x180011a13  lea     rdx, dword_18003AB5C
0x180011a1a  mov     [rbp+arg_8], rax
0x180011a1e  lea     rax, aRdsdwmdirectup; "RdsDWMDirectUpdateProcessor::ProcessWin"...
0x180011a25  mov     [rbp+arg_18], rax
0x180011a29  lea     rax, [rbp+arg_8]
0x180011a2d  mov     [rsp+70h+var_48], rax
0x180011a32  lea     rax, [rbp+arg_18]
0x180011a36  mov     [rsp+70h+var_50], rax
0x180011a3b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180011a40  mov     r8, [rbx+8]
0x180011a44  test    r8, r8
0x180011a47  jnz     short loc_180011A51
0x180011a49  mov     r8, [rsi+40h]; HDC
0x180011a4d  mov     [rbx+8], r8
0x180011a51  mov     rdx, [rbx]; HRGN
0x180011a54  lea     r9, [rbx+10h]; struct tagPOINT *
0x180011a58  mov     rcx, rdi; this
0x180011a5b  call    ?CopyDirtyRegion@RdpDWMDirectWindowContext@@QEAAJPEAUHRGN__@@PEAUHDC__@@PEAUtagPOINT@@@Z; RdpDWMDirectWindowContext::CopyDirtyRegion(HRGN__ *,HDC__ *,tagPOINT *)
0x180011a60  mov     ebx, eax
0x180011a62  test    eax, eax
0x180011a64  jns     loc_180011AED
0x180011a6a  mov     ecx, cs:dword_180044008
0x180011a70  cmp     ecx, 2
0x180011a73  jbe     short loc_180011AED
0x180011a75  lea     rax, aFailedToCopyTh_0; "Failed to copy the dirty region"
0x180011a7c  mov     dword ptr [rbp+arg_8], 3DCh
0x180011a83  mov     [rbp+var_8], rax
0x180011a87  lea     rdx, byte_18003AB0F
0x180011a8e  lea     rax, aProcesswindowd; "ProcessWindowDirtyRegion"
0x180011a95  mov     [rbp+var_10], rax
0x180011a99  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180011aa0  mov     [rbp+var_18], rax
0x180011aa4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180011aab  mov     [rbp+var_20], rax
0x180011aaf  lea     rax, [rbp+var_8]
0x180011ab3  mov     [rsp+70h+var_28], rax
0x180011ab8  lea     rax, [rbp+var_10]
0x180011abc  mov     [rsp+70h+var_30], rax
0x180011ac1  lea     rax, [rbp+arg_8]
0x180011ac5  mov     [rsp+70h+var_38], rax
0x180011aca  lea     rax, [rbp+var_18]
0x180011ace  mov     [rsp+70h+var_40], rax
0x180011ad3  lea     rax, [rbp+arg_18]
0x180011ad7  mov     [rsp+70h+var_48], rax
0x180011adc  lea     rax, [rbp+var_20]
0x180011ae0  mov     [rsp+70h+var_50], rax
0x180011ae5  mov     dword ptr [rbp+arg_18], ebx
0x180011ae8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180011aed  mov     eax, ebx
0x180011aef  mov     rbx, [rsp+70h+arg_0]
0x180011af7  add     rsp, 70h
0x180011afb  pop     rdi
0x180011afc  pop     rsi
0x180011afd  pop     rbp
0x180011afe  retn
```
