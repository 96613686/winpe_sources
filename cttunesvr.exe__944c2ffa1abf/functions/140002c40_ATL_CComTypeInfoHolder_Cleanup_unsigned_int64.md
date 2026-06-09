# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x140002c40`
- end: `0x140002cb9`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `121`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400011ec`
- `0x140001f58`
- `0x140002c40`
- `0x140007010`

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
0x140002c40  test    rcx, rcx
0x140002c43  jz      short locret_140002CB8
0x140002c45  push    rbx
0x140002c46  push    rsi
0x140002c47  push    rdi
0x140002c48  push    r14
0x140002c4a  sub     rsp, 28h
0x140002c4e  mov     rbx, rcx
0x140002c51  mov     rcx, [rcx+18h]
0x140002c55  test    rcx, rcx
0x140002c58  jz      short loc_140002C66
0x140002c5a  mov     rax, [rcx]
0x140002c5d  mov     rax, [rax+10h]
0x140002c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c66  mov     rax, [rbx+28h]
0x140002c6a  mov     qword ptr [rbx+18h], 0
0x140002c72  test    rax, rax
0x140002c75  jz      short loc_140002CA7
0x140002c77  lea     r14, [rax-8]
0x140002c7b  mov     rsi, [r14]
0x140002c7e  mov     rdi, rsi
0x140002c81  shl     rdi, 4
0x140002c85  add     rdi, rax
0x140002c88  test    rsi, rsi
0x140002c8b  jz      short loc_140002C9F
0x140002c8d  sub     rdi, 10h
0x140002c91  mov     rcx, rdi; this
0x140002c94  call    ??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)
0x140002c99  sub     rsi, 1
0x140002c9d  jnz     short loc_140002C8D
0x140002c9f  mov     rcx, r14; Block
0x140002ca2  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140002ca7  mov     qword ptr [rbx+28h], 0
0x140002caf  add     rsp, 28h
0x140002cb3  pop     r14
0x140002cb5  pop     rdi
0x140002cb6  pop     rsi
0x140002cb7  pop     rbx
0x140002cb8  retn
```
