# Mso::OfficeWebServiceApi::XmlHelper::~XmlHelper(void)

- ea: `0x1800931f0`
- end: `0x180093245`
- name: `??1XmlHelper@OfficeWebServiceApi@Mso@@UEAA@XZ`
- size: `85`
- prototype: `void __fastcall(Mso::OfficeWebServiceApi::XmlHelper *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180093250`

## callees

- `0x1800931f0`

## import_xrefs

- `webservices!WsFreeError` at `0x18009321b`
- `webservices!WsFreeError` at `0x18009321b`
- `webservices!WsFreeReader` at `0x18009320c`
- `webservices!WsFreeReader` at `0x18009320c`
- `webservices!WsFreeHeap` at `0x18009322a`
- `webservices!WsFreeHeap` at `0x18009322a`
- `webservices!WsFreeWriter` at `0x180093239`
- `webservices!WsFreeWriter` at `0x180093239`

## pseudocode

```c
void __fastcall Mso::OfficeWebServiceApi::XmlHelper::~XmlHelper(Mso::OfficeWebServiceApi::XmlHelper *this)
{
  WS_XML_READER *v2; // rcx
  WS_ERROR *v3; // rcx
  WS_HEAP *v4; // rcx
  WS_XML_WRITER *v5; // rcx

  *(_QWORD *)this = &Mso::OfficeWebServiceApi::XmlHelper::`vftable';
  v2 = (WS_XML_READER *)*((_QWORD *)this + 4);
  if ( v2 )
    WsFreeReader(v2);
  v3 = (WS_ERROR *)*((_QWORD *)this + 3);
  if ( v3 )
    WsFreeError(v3);
  v4 = (WS_HEAP *)*((_QWORD *)this + 2);
  if ( v4 )
    WsFreeHeap(v4);
  v5 = (WS_XML_WRITER *)*((_QWORD *)this + 5);
  if ( v5 )
    WsFreeWriter(v5);
}

```

## disassembly

```asm
0x1800931f0  push    rbx
0x1800931f2  sub     rsp, 20h
0x1800931f6  lea     rax, ??_7XmlHelper@OfficeWebServiceApi@Mso@@6B@; const Mso::OfficeWebServiceApi::XmlHelper::`vftable'
0x1800931fd  mov     rbx, rcx
0x180093200  mov     [rcx], rax
0x180093203  mov     rcx, [rcx+20h]; reader
0x180093207  test    rcx, rcx
0x18009320a  jz      short loc_180093212
0x18009320c  call    cs:__imp_WsFreeReader
0x180093212  mov     rcx, [rbx+18h]; error
0x180093216  test    rcx, rcx
0x180093219  jz      short loc_180093221
0x18009321b  call    cs:__imp_WsFreeError
0x180093221  mov     rcx, [rbx+10h]; heap
0x180093225  test    rcx, rcx
0x180093228  jz      short loc_180093230
0x18009322a  call    cs:__imp_WsFreeHeap
0x180093230  mov     rcx, [rbx+28h]; writer
0x180093234  test    rcx, rcx
0x180093237  jz      short loc_18009323F
0x180093239  call    cs:__imp_WsFreeWriter
0x18009323f  add     rsp, 20h
0x180093243  pop     rbx
0x180093244  retn
```
