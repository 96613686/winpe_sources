# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x1800118c0`
- end: `0x18001192d`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `109`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002044`
- `0x1800118c0`
- `0x180021010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180011913`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180011913`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::Cleanup(__int64 a1)
{
  __int64 v2; // rcx
  char *v3; // rcx
  char *v4; // rbx

  if ( a1 )
  {
    v2 = *(_QWORD *)(a1 + 24);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *(_QWORD *)(a1 + 24) = 0;
    v3 = *(char **)(a1 + 40);
    if ( v3 )
    {
      v4 = v3 - 8;
      `eh vector destructor iterator'(v3, 0x10u, *((_QWORD *)v3 - 1), (void (*)(void *))ATL::CComBSTR::~CComBSTR);
      operator delete[](v4);
    }
    *(_QWORD *)(a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x1800118c0  test    rcx, rcx
0x1800118c3  jz      short locret_18001192C
0x1800118c5  mov     [rsp+arg_0], rbx
0x1800118ca  push    rdi
0x1800118cb  sub     rsp, 20h
0x1800118cf  mov     rdi, rcx
0x1800118d2  mov     rcx, [rcx+18h]
0x1800118d6  test    rcx, rcx
0x1800118d9  jz      short loc_1800118E7
0x1800118db  mov     rax, [rcx]
0x1800118de  mov     rax, [rax+10h]
0x1800118e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118e7  mov     qword ptr [rdi+18h], 0
0x1800118ef  mov     rcx, [rdi+28h]; void *
0x1800118f3  test    rcx, rcx
0x1800118f6  jz      short loc_18001191A
0x1800118f8  lea     rbx, [rcx-8]
0x1800118fc  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180011903  mov     r8, [rbx]; unsigned __int64
0x180011906  mov     edx, 10h; unsigned __int64
0x18001190b  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180011910  mov     rcx, rbx
0x180011913  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180011919  nop
0x18001191a  mov     qword ptr [rdi+28h], 0
0x180011922  mov     rbx, [rsp+28h+arg_0]
0x180011927  add     rsp, 20h
0x18001192b  pop     rdi
0x18001192c  retn
```
