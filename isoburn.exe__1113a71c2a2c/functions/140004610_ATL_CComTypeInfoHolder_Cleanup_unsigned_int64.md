# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x140004610`
- end: `0x140004694`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `132`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001fc4`
- `0x140002c28`
- `0x140004610`
- `0x140010010`

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
0x140004610  test    rcx, rcx
0x140004613  jz      short locret_140004693
0x140004615  push    rbx
0x140004616  push    rsi
0x140004617  push    rdi
0x140004618  push    r14
0x14000461a  sub     rsp, 28h
0x14000461e  mov     rbx, rcx
0x140004621  mov     rcx, [rcx+18h]
0x140004625  test    rcx, rcx
0x140004628  jz      short loc_140004636
0x14000462a  mov     rax, [rcx]
0x14000462d  mov     rax, [rax+10h]
0x140004631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004636  mov     rax, [rbx+28h]
0x14000463a  mov     qword ptr [rbx+18h], 0
0x140004642  test    rax, rax
0x140004645  jz      short loc_140004682
0x140004647  lea     r14, [rax-8]
0x14000464b  mov     rsi, [r14]
0x14000464e  mov     rdi, rsi
0x140004651  shl     rdi, 4
0x140004655  add     rdi, rax
0x140004658  test    rsi, rsi
0x14000465b  jz      short loc_14000466F
0x14000465d  sub     rdi, 10h
0x140004661  mov     rcx, rdi; this
0x140004664  call    ??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)
0x140004669  sub     rsi, 1
0x14000466d  jnz     short loc_14000465D
0x14000466f  mov     rdx, [r14]
0x140004672  mov     rcx, r14; Block
0x140004675  shl     rdx, 4
0x140004679  add     rdx, 8
0x14000467d  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x140004682  mov     qword ptr [rbx+28h], 0
0x14000468a  add     rsp, 28h
0x14000468e  pop     r14
0x140004690  pop     rdi
0x140004691  pop     rsi
0x140004692  pop     rbx
0x140004693  retn
```
