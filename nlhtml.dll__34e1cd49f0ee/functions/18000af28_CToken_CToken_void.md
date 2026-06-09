# CToken::~CToken(void)

- ea: `0x18000af28`
- end: `0x18000af58`
- name: `??1CToken@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(CToken *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180023410`
- `0x180023450`
- `0x180023470`
- `0x18002369f`

## callees

- `0x18000aab0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CToken::~CToken(CToken *this)
{
  _QWORD *v1; // rbx

  v1 = (_QWORD *)((char *)this + 16);
  *((_QWORD *)this + 2) = &TLMString<32,32,1024>::`vftable';
  CLMString::DeleteBuf((CToken *)((char *)this + 16), (wchar_t *)this + 20);
  *v1 = &CLMString::`vftable';
}

```

## disassembly

```asm
0x18000af28  push    rbx
0x18000af2a  sub     rsp, 20h
0x18000af2e  lea     rbx, [rcx+10h]
0x18000af32  lea     rax, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x18000af39  mov     [rbx], rax
0x18000af3c  lea     rdx, [rbx+18h]; wchar_t *
0x18000af40  mov     rcx, rbx; this
0x18000af43  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x18000af48  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x18000af4f  mov     [rbx], rax
0x18000af52  add     rsp, 20h
0x18000af56  pop     rbx
0x18000af57  retn
```
