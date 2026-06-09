# CMSMQRuleHandler::CMSMQRuleHandler(void)

- ea: `0x1800051e0`
- end: `0x180005289`
- name: `??0CMSMQRuleHandler@@QEAA@XZ`
- size: `169`
- prototype: `CMSMQRuleHandler *__fastcall(CMSMQRuleHandler *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dffc`
- `0x18000e2a0`

## callees

- `0x180005740`
- `0x1800157c8`

## import_xrefs

- `ATL!__imp_AtlComPtrAssign` at `0x180005250`
- `ATL!__imp_AtlComPtrAssign` at `0x180005250`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CMSMQRuleHandler *__fastcall CMSMQRuleHandler::CMSMQRuleHandler(CMSMQRuleHandler *this)
{
  *((_DWORD *)this + 4) = 0;
  *(_OWORD *)((char *)this + 24) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_BYTE *)this + 64) = 0;
  *((_QWORD *)this + 9) = 0;
  CStringTokens::CStringTokens((CMSMQRuleHandler *)((char *)this + 80));
  CStringTokens::CStringTokens((CMSMQRuleHandler *)((char *)this + 112));
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  AtlComPtrAssign((char *)this + 72, 0);
  _bstr_t::operator=((char *)this + 152, &psz);
  _bstr_t::operator=((char *)this + 160, &psz);
  *((_WORD *)this + 86) = 0;
  return this;
}

```

## disassembly

```asm
0x1800051e0  mov     [rsp+arg_0], rcx
0x1800051e5  push    rbx
0x1800051e6  push    rbp
0x1800051e7  push    rsi
0x1800051e8  push    rdi
0x1800051e9  sub     rsp, 28h
0x1800051ed  mov     rbp, rcx
0x1800051f0  mov     dword ptr [rcx+10h], 0
0x1800051f7  xorps   xmm0, xmm0
0x1800051fa  xor     eax, eax
0x1800051fc  movups  xmmword ptr [rcx+18h], xmm0
0x180005200  movups  xmmword ptr [rcx+28h], xmm0
0x180005204  mov     [rcx+38h], rax
0x180005208  mov     [rcx+40h], al
0x18000520b  mov     [rcx+48h], rax
0x18000520f  add     rcx, 50h ; 'P'; this
0x180005213  call    ??0CStringTokens@@QEAA@XZ; CStringTokens::CStringTokens(void)
0x180005218  nop
0x180005219  lea     rcx, [rbp+70h]; this
0x18000521d  call    ??0CStringTokens@@QEAA@XZ; CStringTokens::CStringTokens(void)
0x180005222  nop
0x180005223  mov     qword ptr [rbp+90h], 0
0x18000522e  lea     rdi, [rbp+98h]
0x180005235  mov     qword ptr [rdi], 0
0x18000523c  lea     rbx, [rbp+0A0h]
0x180005243  mov     qword ptr [rbx], 0
0x18000524a  xor     edx, edx
0x18000524c  lea     rcx, [rbp+48h]
0x180005250  call    cs:__imp_AtlComPtrAssign
0x180005256  lea     rdx, psz
0x18000525d  mov     rcx, rdi
0x180005260  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x180005265  lea     rdx, psz
0x18000526c  mov     rcx, rbx
0x18000526f  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x180005274  mov     word ptr [rbp+0ACh], 0
0x18000527d  mov     rax, rbp
0x180005280  add     rsp, 28h
0x180005284  pop     rdi
0x180005285  pop     rsi
0x180005286  pop     rbp
0x180005287  pop     rbx
0x180005288  retn
```
