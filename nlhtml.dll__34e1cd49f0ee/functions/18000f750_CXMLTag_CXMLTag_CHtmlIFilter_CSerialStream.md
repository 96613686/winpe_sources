# CXMLTag::CXMLTag(CHtmlIFilter &,CSerialStream &)

- ea: `0x18000f750`
- end: `0x18000f7fd`
- name: `??0CXMLTag@@QEAA@AEAVCHtmlIFilter@@AEAVCSerialStream@@@Z`
- size: `173`
- prototype: `CXMLTag *__fastcall(CXMLTag *__hidden this, struct CHtmlIFilter *, struct CSerialStream *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ed78`

## callees

- `0x18000f574`

## pseudocode

```c
CXMLTag *__fastcall CXMLTag::CXMLTag(CXMLTag *this, struct CHtmlIFilter *a2, struct CSerialStream *a3)
{
  CXMLTag *result; // rax

  CPropertyTag::CPropertyTag(this, a2, a3);
  *((_WORD *)this + 452) = 0;
  *(_QWORD *)this = &CXMLTag::`vftable';
  *(_QWORD *)((char *)this + 908) = 0;
  *((_QWORD *)this + 116) = (char *)this + 944;
  *((_QWORD *)this + 117) = 33;
  *((_WORD *)this + 472) = 0;
  *((_QWORD *)this + 115) = &TLMString<32,32,1024>::`vftable';
  *((_QWORD *)this + 128) = (char *)this + 1040;
  *((_QWORD *)this + 129) = 193;
  *((_WORD *)this + 520) = 0;
  *((_QWORD *)this + 127) = &TLMString<192,64,32767>::`vftable';
  result = this;
  *((_QWORD *)this + 180) = (char *)this + 1456;
  *((_QWORD *)this + 181) = 33;
  *((_WORD *)this + 728) = 0;
  *((_QWORD *)this + 179) = &TLMString<32,32,1024>::`vftable';
  return result;
}

```

## disassembly

```asm
0x18000f750  push    rbx
0x18000f752  sub     rsp, 20h
0x18000f756  mov     rbx, rcx
0x18000f759  call    ??0CPropertyTag@@QEAA@AEAVCHtmlIFilter@@AEAVCSerialStream@@@Z; CPropertyTag::CPropertyTag(CHtmlIFilter &,CSerialStream &)
0x18000f75e  xor     r9d, r9d
0x18000f761  lea     rcx, [rbx+3B0h]
0x18000f768  mov     [rbx+388h], r9w
0x18000f770  lea     rax, ??_7CXMLTag@@6B@; const CXMLTag::`vftable'
0x18000f777  mov     [rbx], rax
0x18000f77a  lea     r8, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x18000f781  mov     [rbx+38Ch], r9
0x18000f788  lea     rax, ??_7?$TLMString@$0MA@$0EA@$0HPPP@@@6B@; const TLMString<192,64,32767>::`vftable'
0x18000f78f  mov     [rbx+3A0h], rcx
0x18000f796  mov     qword ptr [rbx+3A8h], 21h ; '!'
0x18000f7a1  mov     [rcx], r9w
0x18000f7a5  lea     rcx, [rbx+410h]
0x18000f7ac  mov     [rbx+398h], r8
0x18000f7b3  mov     [rbx+400h], rcx
0x18000f7ba  mov     qword ptr [rbx+408h], 0C1h
0x18000f7c5  mov     [rcx], r9w
0x18000f7c9  lea     rcx, [rbx+5B0h]
0x18000f7d0  mov     [rbx+3F8h], rax
0x18000f7d7  mov     rax, rbx
0x18000f7da  mov     [rbx+5A0h], rcx
0x18000f7e1  mov     qword ptr [rbx+5A8h], 21h ; '!'
0x18000f7ec  mov     [rcx], r9w
0x18000f7f0  mov     [rbx+598h], r8
0x18000f7f7  add     rsp, 20h
0x18000f7fb  pop     rbx
0x18000f7fc  retn
```
