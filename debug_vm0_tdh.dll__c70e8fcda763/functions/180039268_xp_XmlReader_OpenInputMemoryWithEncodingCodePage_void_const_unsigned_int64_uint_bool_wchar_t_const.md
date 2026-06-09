# xp::XmlReader::OpenInputMemoryWithEncodingCodePage(void const *,unsigned __int64,uint,bool,wchar_t const *)

- ea: `0x180039268`
- end: `0x180039321`
- name: `?OpenInputMemoryWithEncodingCodePage@XmlReader@xp@@QEAAJPEBX_KI_NPEB_W@Z`
- size: `185`
- prototype: `int(xp::XmlReader *__hidden this, const void *, unsigned __int64, unsigned int, bool, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180039184`

## callees

- `0x18003538c`
- `0x180039268`
- `0x18004c010`

## import_xrefs

- `XmlLite!CreateXmlReaderInputWithEncodingCodePage` at `0x1800392cd`
- `XmlLite!CreateXmlReaderInputWithEncodingCodePage` at `0x1800392cd`

## pseudocode

```c
__int64 __fastcall xp::XmlReader::OpenInputMemoryWithEncodingCodePage(
        xp::XmlReader *this,
        const void *a2,
        unsigned __int64 a3,
        __int64 a4,
        bool a5,
        IXmlReaderInput *ppInput)
{
  HRESULT MemoryStream; // edi
  IUnknown *v8; // rbx
  IUnknown *pInputStream; // [rsp+30h] [rbp-18h] BYREF

  pInputStream = 0;
  MemoryStream = xp::XmlReader::CreateMemoryStream(a2, a3, (struct IStream **)&pInputStream);
  if ( MemoryStream >= 0 )
  {
    ppInput = 0;
    v8 = pInputStream;
    MemoryStream = CreateXmlReaderInputWithEncodingCodePage(pInputStream, 0, 0x4E4u, 0, 0, &ppInput);
    ((void (__fastcall *)(IUnknown *))v8->lpVtbl->Release)(v8);
    if ( MemoryStream >= 0 )
    {
      MemoryStream = (*(__int64 (__fastcall **)(xp::XmlReader *, IXmlReaderInput *))(*(_QWORD *)this + 24LL))(
                       this,
                       ppInput);
      ((void (__fastcall *)(IXmlReaderInput *))ppInput->lpVtbl->Release)(ppInput);
    }
  }
  return (unsigned int)MemoryStream;
}

```

## disassembly

```asm
0x180039268  mov     r11, rsp
0x18003926b  mov     [r11+8], rbx
0x18003926f  mov     [r11+10h], rsi
0x180039273  push    rdi
0x180039274  sub     rsp, 40h
0x180039278  mov     rax, r8
0x18003927b  mov     r9, rdx
0x18003927e  mov     rsi, rcx
0x180039281  mov     qword ptr [r11-18h], 0
0x180039289  lea     r8, [r11-18h]; struct IStream **
0x18003928d  mov     rdx, rax; unsigned __int64
0x180039290  mov     rcx, r9; void *
0x180039293  call    ?CreateMemoryStream@XmlReader@xp@@SAJPEBX_KPEAPEAUIStream@@@Z; xp::XmlReader::CreateMemoryStream(void const *,unsigned __int64,IStream * *)
0x180039298  mov     edi, eax
0x18003929a  test    eax, eax
0x18003929c  js      short loc_18003930F
0x18003929e  mov     [rsp+48h+arg_28], 0
0x1800392a7  lea     rax, [rsp+48h+arg_28]
0x1800392ac  mov     [rsp+48h+ppInput], rax; ppInput
0x1800392b1  mov     [rsp+48h+pwszBaseUri], 0; pwszBaseUri
0x1800392ba  xor     r9d, r9d; fEncodingHint
0x1800392bd  xor     edx, edx; pMalloc
0x1800392bf  mov     r8d, 4E4h; nEncodingCodePage
0x1800392c5  mov     rbx, [rsp+48h+pInputStream]
0x1800392ca  mov     rcx, rbx; pInputStream
0x1800392cd  call    cs:__imp_CreateXmlReaderInputWithEncodingCodePage
0x1800392d3  mov     edi, eax
0x1800392d5  mov     rax, [rbx]
0x1800392d8  mov     rcx, rbx
0x1800392db  mov     rax, [rax+10h]
0x1800392df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392e4  test    edi, edi
0x1800392e6  js      short loc_18003930F
0x1800392e8  mov     rax, [rsi]
0x1800392eb  mov     rdx, [rsp+48h+arg_28]
0x1800392f0  mov     rcx, rsi
0x1800392f3  mov     rax, [rax+18h]
0x1800392f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392fc  mov     edi, eax
0x1800392fe  mov     rcx, [rsp+48h+arg_28]
0x180039303  mov     rax, [rcx]
0x180039306  mov     rax, [rax+10h]
0x18003930a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003930f  mov     eax, edi
0x180039311  mov     rbx, [rsp+48h+arg_0]
0x180039316  mov     rsi, [rsp+48h+arg_8]
0x18003931b  add     rsp, 40h
0x18003931f  pop     rdi
0x180039320  retn
```
