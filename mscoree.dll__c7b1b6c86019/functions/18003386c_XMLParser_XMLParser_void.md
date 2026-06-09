# XMLParser::~XMLParser(void)

- ea: `0x18003386c`
- end: `0x180033953`
- name: `??1XMLParser@@UEAA@XZ`
- size: `231`
- prototype: `void __fastcall(XMLParser *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180033990`

## callees

- `0x180003840`
- `0x180005538`
- `0x18003386c`
- `0x180034330`
- `0x1800354a8`
- `0x180039310`
- `0x180039418`

## pseudocode

```c
void __fastcall XMLParser::~XMLParser(XMLParser *this)
{
  void *v1; // rbx
  int v3; // ebp
  __int64 v4; // r15
  __int64 v5; // r14
  void *v6; // rcx
  void *v7; // rcx

  v1 = (void *)*((_QWORD *)this + 25);
  *(_QWORD *)this = &XMLParser::`vftable';
  ClrEnterCriticalSection(v1);
  XMLParser::Reset(this);
  v3 = *((_DWORD *)this + 33);
  while ( --v3 >= 0 )
  {
    v4 = *((_QWORD *)this + 15);
    v5 = *((_DWORD *)this + 28) * v3;
    v6 = *(void **)(v5 + v4 + 48);
    if ( v6 )
    {
      operator delete(v6);
      *(_QWORD *)(v5 + v4 + 48) = 0;
      *(_DWORD *)(v5 + v4 + 56) = 0;
    }
    *(_QWORD *)(v5 + v4 + 32) = 0;
  }
  operator delete(*((void **)this + 26));
  operator delete(*((void **)this + 27));
  operator delete(*((void **)this + 21));
  ClrLeaveCriticalSection(v1);
  v7 = (void *)*((_QWORD *)this + 25);
  if ( v7 )
    ClrDeleteCriticalSection(v7);
  _release((struct IUnknown **)this + 24);
  operator delete(*((void **)this + 15));
  operator delete(*((void **)this + 10));
  *(_QWORD *)this = &_unknown<IXMLParser,&_GUID const IID_IXMLParser>::`vftable';
}

```

## disassembly

```asm
0x18003386c  push    rbx
0x18003386e  push    rbp
0x18003386f  push    rsi
0x180033870  push    rdi
0x180033871  push    r14
0x180033873  push    r15
0x180033875  sub     rsp, 28h
0x180033879  mov     rbx, [rcx+0C8h]
0x180033880  lea     rax, ??_7XMLParser@@6B@; const XMLParser::`vftable'
0x180033887  mov     [rcx], rax
0x18003388a  mov     rdi, rcx
0x18003388d  mov     rcx, rbx; void *
0x180033890  call    ?ClrEnterCriticalSection@@YAXPEAX@Z; ClrEnterCriticalSection(void *)
0x180033895  mov     rcx, rdi; this
0x180033898  call    ?Reset@XMLParser@@UEAAJXZ; XMLParser::Reset(void)
0x18003389d  mov     ebp, [rdi+84h]
0x1800338a3  jmp     short loc_1800338DC
0x1800338a5  mov     r15, [rdi+78h]
0x1800338a9  mov     eax, ebp
0x1800338ab  imul    eax, [rdi+70h]
0x1800338af  movsxd  r14, eax
0x1800338b2  mov     rcx, [r14+r15+30h]; void *
0x1800338b7  test    rcx, rcx
0x1800338ba  jz      short loc_1800338D3
0x1800338bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800338c1  mov     qword ptr [r14+r15+30h], 0
0x1800338ca  mov     dword ptr [r14+r15+38h], 0
0x1800338d3  mov     qword ptr [r14+r15+20h], 0
0x1800338dc  sub     ebp, 1
0x1800338df  jns     short loc_1800338A5
0x1800338e1  mov     rcx, [rdi+0D0h]; void *
0x1800338e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800338ed  mov     rcx, [rdi+0D8h]; void *
0x1800338f4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800338f9  mov     rcx, [rdi+0A8h]; void *
0x180033900  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180033905  mov     rcx, rbx; void *
0x180033908  call    ?ClrLeaveCriticalSection@@YAXPEAX@Z; ClrLeaveCriticalSection(void *)
0x18003390d  mov     rcx, [rdi+0C8h]; void *
0x180033914  test    rcx, rcx
0x180033917  jz      short loc_18003391E
0x180033919  call    ?ClrDeleteCriticalSection@@YAJPEAX@Z; ClrDeleteCriticalSection(void *)
0x18003391e  lea     rcx, [rdi+0C0h]; struct IUnknown **
0x180033925  call    ?_release@@YAXPEAPEAUIUnknown@@@Z; _release(IUnknown * *)
0x18003392a  mov     rcx, [rdi+78h]; void *
0x18003392e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180033933  mov     rcx, [rdi+50h]; void *
0x180033937  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003393c  lea     rax, ??_7?$_unknown@UIXMLParser@@$1?IID_IXMLParser@@3U_GUID@@B@@6B@; const _unknown<IXMLParser,&_GUID const IID_IXMLParser>::`vftable'
0x180033943  mov     [rdi], rax
0x180033946  add     rsp, 28h
0x18003394a  pop     r15
0x18003394c  pop     r14
0x18003394e  pop     rdi
0x18003394f  pop     rsi
0x180033950  pop     rbp
0x180033951  pop     rbx
0x180033952  retn
```
