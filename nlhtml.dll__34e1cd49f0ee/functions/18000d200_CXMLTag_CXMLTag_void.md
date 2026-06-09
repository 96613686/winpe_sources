# CXMLTag::~CXMLTag(void)

- ea: `0x18000d200`
- end: `0x18000d23a`
- name: `??1CXMLTag@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(CXMLTag *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e900`

## callees

- `0x18000aef4`
- `0x18000cc6c`
- `0x18000d240`

## pseudocode

```c
void __fastcall CXMLTag::~CXMLTag(CXMLTag *this)
{
  TLMString<32,32,1024>::~TLMString<32,32,1024>((char *)this + 1432);
  TLMString<192,64,32767>::~TLMString<192,64,32767>((char *)this + 1016);
  TLMString<32,32,1024>::~TLMString<32,32,1024>((char *)this + 920);
  CPropertyTag::~CPropertyTag(this);
}

```

## disassembly

```asm
0x18000d200  push    rbx
0x18000d202  sub     rsp, 20h
0x18000d206  mov     rbx, rcx
0x18000d209  add     rcx, 598h
0x18000d210  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x18000d215  lea     rcx, [rbx+3F8h]
0x18000d21c  call    ??1?$TLMString@$0MA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<192,64,32767>::~TLMString<192,64,32767>(void)
0x18000d221  lea     rcx, [rbx+398h]
0x18000d228  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x18000d22d  mov     rcx, rbx; this
0x18000d230  add     rsp, 20h
0x18000d234  pop     rbx
0x18000d235  jmp     ??1CPropertyTag@@UEAA@XZ; CPropertyTag::~CPropertyTag(void)
```
