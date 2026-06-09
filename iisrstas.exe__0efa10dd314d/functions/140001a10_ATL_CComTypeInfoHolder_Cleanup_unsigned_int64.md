# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x140001a10`
- end: `0x140001a89`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `121`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001008`
- `0x140001888`
- `0x140001a10`
- `0x140006010`

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
0x140001a10  test    rcx, rcx
0x140001a13  jz      short locret_140001A88
0x140001a15  push    rbx
0x140001a16  push    rsi
0x140001a17  push    rdi
0x140001a18  push    r14
0x140001a1a  sub     rsp, 28h
0x140001a1e  mov     rbx, rcx
0x140001a21  mov     rcx, [rcx+18h]
0x140001a25  test    rcx, rcx
0x140001a28  jz      short loc_140001A36
0x140001a2a  mov     rax, [rcx]
0x140001a2d  mov     rax, [rax+10h]
0x140001a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001a36  mov     rax, [rbx+28h]
0x140001a3a  mov     qword ptr [rbx+18h], 0
0x140001a42  test    rax, rax
0x140001a45  jz      short loc_140001A77
0x140001a47  lea     r14, [rax-8]
0x140001a4b  mov     rsi, [r14]
0x140001a4e  mov     rdi, rsi
0x140001a51  shl     rdi, 4
0x140001a55  add     rdi, rax
0x140001a58  test    rsi, rsi
0x140001a5b  jz      short loc_140001A6F
0x140001a5d  sub     rdi, 10h
0x140001a61  mov     rcx, rdi; this
0x140001a64  call    ??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)
0x140001a69  sub     rsi, 1
0x140001a6d  jnz     short loc_140001A5D
0x140001a6f  mov     rcx, r14; void *
0x140001a72  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140001a77  mov     qword ptr [rbx+28h], 0
0x140001a7f  add     rsp, 28h
0x140001a83  pop     r14
0x140001a85  pop     rdi
0x140001a86  pop     rsi
0x140001a87  pop     rbx
0x140001a88  retn
```
