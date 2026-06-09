# Mso::OfficeWebServiceApi::XmlHelper::XmlHelper(void)

- ea: `0x18009313c`
- end: `0x1800931ed`
- name: `??0XmlHelper@OfficeWebServiceApi@Mso@@QEAA@XZ`
- size: `177`
- prototype: `__int64 __fastcall(Mso::OfficeWebServiceApi::XmlHelper *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18008062c`

## callees

- `0x18009313c`

## import_xrefs

- `webservices!WsCreateError` at `0x18009318c`
- `webservices!WsCreateError` at `0x18009318c`
- `webservices!WsCreateHeap` at `0x1800931b6`
- `webservices!WsCreateHeap` at `0x1800931b6`
- `webservices!WsFreeError` at `0x1800931c6`
- `webservices!WsFreeError` at `0x1800931c6`

## pseudocode

```c
Mso::OfficeWebServiceApi::XmlHelper *__fastcall Mso::OfficeWebServiceApi::XmlHelper::XmlHelper(
        Mso::OfficeWebServiceApi::XmlHelper *this)
{
  WS_ERROR **v1; // rbx
  WS_HEAP **heap; // rsi

  *((_DWORD *)this + 2) = 1;
  v1 = (WS_ERROR **)((char *)this + 24);
  heap = (WS_HEAP **)((char *)this + 16);
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *(_QWORD *)this = &Mso::OfficeWebServiceApi::XmlHelper::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  if ( WsCreateError(0, 0, (WS_ERROR **)this + 3) < 0 )
    goto LABEL_4;
  _mm_lfence();
  if ( WsCreateHeap(0x500000u, 0x200u, 0, 0, heap, *v1) < 0 )
  {
    _mm_lfence();
    WsFreeError(*v1);
    *heap = 0;
LABEL_4:
    *v1 = 0;
  }
  return this;
}

```

## disassembly

```asm
0x18009313c  mov     [rsp+arg_0], rbx
0x180093141  mov     [rsp+arg_8], rsi
0x180093146  push    rdi
0x180093147  sub     rsp, 30h
0x18009314b  mov     dword ptr [rcx+8], 1
0x180093152  lea     rbx, [rcx+18h]
0x180093156  lea     rsi, [rcx+10h]
0x18009315a  mov     qword ptr [rcx+20h], 0
0x180093162  lea     rax, ??_7XmlHelper@OfficeWebServiceApi@Mso@@6B@; const Mso::OfficeWebServiceApi::XmlHelper::`vftable'
0x180093169  mov     qword ptr [rcx+28h], 0
0x180093171  mov     [rcx], rax
0x180093174  mov     rdi, rcx
0x180093177  xor     ecx, ecx; properties
0x180093179  mov     qword ptr [rsi], 0
0x180093180  mov     r8, rbx; error
0x180093183  mov     qword ptr [rbx], 0
0x18009318a  xor     edx, edx; propertyCount
0x18009318c  call    cs:__imp_WsCreateError
0x180093192  test    eax, eax
0x180093194  js      short loc_1800931D3
0x180093196  lfence
0x180093199  mov     rax, [rbx]
0x18009319c  xor     r9d, r9d; propertyCount
0x18009319f  mov     [rsp+38h+error], rax; error
0x1800931a4  xor     r8d, r8d; properties
0x1800931a7  mov     edx, 200h; trimSize
0x1800931ac  mov     [rsp+38h+heap], rsi; heap
0x1800931b1  mov     ecx, 500000h; maxSize
0x1800931b6  call    cs:__imp_WsCreateHeap
0x1800931bc  test    eax, eax
0x1800931be  jns     short loc_1800931DA
0x1800931c0  lfence
0x1800931c3  mov     rcx, [rbx]; error
0x1800931c6  call    cs:__imp_WsFreeError
0x1800931cc  mov     qword ptr [rsi], 0
0x1800931d3  mov     qword ptr [rbx], 0
0x1800931da  mov     rbx, [rsp+38h+arg_0]
0x1800931df  mov     rax, rdi
0x1800931e2  mov     rsi, [rsp+38h+arg_8]
0x1800931e7  add     rsp, 30h
0x1800931eb  pop     rdi
0x1800931ec  retn
```
