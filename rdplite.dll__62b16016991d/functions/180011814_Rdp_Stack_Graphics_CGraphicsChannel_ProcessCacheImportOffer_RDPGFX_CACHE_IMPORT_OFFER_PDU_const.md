# Rdp::Stack::Graphics::CGraphicsChannel::ProcessCacheImportOffer(_RDPGFX_CACHE_IMPORT_OFFER_PDU const *)

- ea: `0x180011814`
- end: `0x18001189d`
- name: `?ProcessCacheImportOffer@CGraphicsChannel@Graphics@Stack@Rdp@@AEAAXPEBU_RDPGFX_CACHE_IMPORT_OFFER_PDU@@@Z`
- size: `137`
- prototype: `void __fastcall(Rdp::Stack::Graphics::CGraphicsChannel *this, const struct _RDPGFX_CACHE_IMPORT_OFFER_PDU *, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010a30`

## callees

- `0x180001ecc`
- `0x180011814`

## string_xrefs

- `0x180011833`: `ProcessCacheImportOffer`
- `0x18001183e`: `Rdp::Stack::Graphics::CGraphicsChannel::ProcessCacheImportOffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Rdp::Stack::Graphics::CGraphicsChannel::ProcessCacheImportOffer(
        Rdp::Stack::Graphics::CGraphicsChannel *this,
        const struct _RDPGFX_CACHE_IMPORT_OFFER_PDU *a2,
        int a3,
        int a4)
{
  const char *v4; // [rsp+50h] [rbp-18h] BYREF
  const char *v5; // [rsp+58h] [rbp-10h] BYREF
  Rdp::Stack::Graphics::CGraphicsChannel *v6; // [rsp+70h] [rbp+8h] BYREF
  int v7; // [rsp+80h] [rbp+18h] BYREF
  const char *v8; // [rsp+88h] [rbp+20h] BYREF

  v6 = this;
  if ( (unsigned int)dword_18003C058 > 4 )
  {
    LOWORD(v6) = *((_WORD *)a2 + 4);
    v8 = "ProcessCacheImportOffer";
    v4 = "Rdp::Stack::Graphics::CGraphicsChannel::ProcessCacheImportOffer";
    v7 = 1134;
    v5 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)word_18003502A,
      a3,
      a4,
      (__int64)&v5,
      (__int64)&v7,
      (__int64)&v4,
      (__int64)&v8,
      (__int64)&v6);
  }
}

```

## disassembly

```asm
0x180011814  mov     r11, rsp
0x180011817  mov     [r11+8], rcx
0x18001181b  sub     rsp, 68h
0x18001181f  mov     eax, cs:dword_18003C058
0x180011825  cmp     eax, 4
0x180011828  jbe     short loc_180011898
0x18001182a  movzx   eax, word ptr [rdx+8]
0x18001182e  mov     word ptr [rsp+68h+arg_0], ax
0x180011833  lea     rax, aProcesscacheim; "ProcessCacheImportOffer"
0x18001183a  mov     [r11+20h], rax
0x18001183e  lea     rax, aRdpStackGraphi_4; "Rdp::Stack::Graphics::CGraphicsChannel:"...
0x180011845  mov     [r11-18h], rax
0x180011849  mov     dword ptr [r11+18h], 46Eh
0x180011851  lea     rax, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180011858  mov     [r11-10h], rax
0x18001185c  lea     rax, [r11+8]
0x180011860  mov     [r11-28h], rax
0x180011864  lea     rax, [r11+20h]
0x180011868  mov     [r11-30h], rax
0x18001186c  lea     rax, [r11-18h]
0x180011870  mov     [r11-38h], rax
0x180011874  lea     rax, [r11+18h]
0x180011878  mov     [r11-40h], rax
0x18001187c  lea     rax, [r11-10h]
0x180011880  mov     [r11-48h], rax
0x180011884  lea     rdx, word_18003502A
0x18001188b  lea     rcx, dword_18003C058
0x180011892  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &)
0x180011897  nop
0x180011898  add     rsp, 68h
0x18001189c  retn
```
