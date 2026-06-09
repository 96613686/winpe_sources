# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x180015790`
- end: `0x180015809`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `121`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001150`
- `0x1800020cc`
- `0x180015790`
- `0x180019010`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::Cleanup(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  void *v4; // r14
  __int64 v5; // rsi
  ATL::CComTypeInfoHolder::stringdispid *i; // rdi

  if ( a1 )
  {
    v2 = *(_QWORD *)(a1 + 24);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    v3 = *(_QWORD *)(a1 + 40);
    *(_QWORD *)(a1 + 24) = 0;
    if ( v3 )
    {
      v4 = (void *)(v3 - 8);
      v5 = *(_QWORD *)(v3 - 8);
      for ( i = (ATL::CComTypeInfoHolder::stringdispid *)(v3 + 16 * v5); v5; --v5 )
      {
        i = (ATL::CComTypeInfoHolder::stringdispid *)((char *)i - 16);
        ATL::CComTypeInfoHolder::stringdispid::~stringdispid(i);
      }
      operator delete[](v4);
    }
    *(_QWORD *)(a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x180015790  test    rcx, rcx
0x180015793  jz      short locret_180015808
0x180015795  push    rbx
0x180015796  push    rsi
0x180015797  push    rdi
0x180015798  push    r14
0x18001579a  sub     rsp, 28h
0x18001579e  mov     rbx, rcx
0x1800157a1  mov     rcx, [rcx+18h]
0x1800157a5  test    rcx, rcx
0x1800157a8  jz      short loc_1800157B6
0x1800157aa  mov     rax, [rcx]
0x1800157ad  mov     rax, [rax+10h]
0x1800157b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157b6  mov     rax, [rbx+28h]
0x1800157ba  mov     qword ptr [rbx+18h], 0
0x1800157c2  test    rax, rax
0x1800157c5  jz      short loc_1800157F7
0x1800157c7  lea     r14, [rax-8]
0x1800157cb  mov     rsi, [r14]
0x1800157ce  mov     rdi, rsi
0x1800157d1  shl     rdi, 4
0x1800157d5  add     rdi, rax
0x1800157d8  test    rsi, rsi
0x1800157db  jz      short loc_1800157EF
0x1800157dd  sub     rdi, 10h
0x1800157e1  mov     rcx, rdi; this
0x1800157e4  call    ??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)
0x1800157e9  sub     rsi, 1
0x1800157ed  jnz     short loc_1800157DD
0x1800157ef  mov     rcx, r14; Block
0x1800157f2  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800157f7  mov     qword ptr [rbx+28h], 0
0x1800157ff  add     rsp, 28h
0x180015803  pop     r14
0x180015805  pop     rdi
0x180015806  pop     rsi
0x180015807  pop     rbx
0x180015808  retn
```
