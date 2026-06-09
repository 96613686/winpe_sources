# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x18000f230`
- end: `0x18000f29d`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `109`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800017f8`
- `0x18000f230`
- `0x180019010`

## import_xrefs

- `msvcrt!free` at `0x18000f283`
- `msvcrt!free` at `0x18000f283`

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
      free(v4);
    }
    *(_QWORD *)(a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x18000f230  test    rcx, rcx
0x18000f233  jz      short locret_18000F29C
0x18000f235  mov     [rsp+arg_0], rbx
0x18000f23a  push    rdi
0x18000f23b  sub     rsp, 20h
0x18000f23f  mov     rdi, rcx
0x18000f242  mov     rcx, [rcx+18h]
0x18000f246  test    rcx, rcx
0x18000f249  jz      short loc_18000F257
0x18000f24b  mov     rax, [rcx]
0x18000f24e  mov     rax, [rax+10h]
0x18000f252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f257  mov     qword ptr [rdi+18h], 0
0x18000f25f  mov     rcx, [rdi+28h]; void *
0x18000f263  test    rcx, rcx
0x18000f266  jz      short loc_18000F28A
0x18000f268  lea     rbx, [rcx-8]
0x18000f26c  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x18000f273  mov     r8, [rbx]; unsigned __int64
0x18000f276  mov     edx, 10h; unsigned __int64
0x18000f27b  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000f280  mov     rcx, rbx; Block
0x18000f283  call    cs:__imp_free
0x18000f289  nop
0x18000f28a  mov     qword ptr [rdi+28h], 0
0x18000f292  mov     rbx, [rsp+28h+arg_0]
0x18000f297  add     rsp, 20h
0x18000f29b  pop     rdi
0x18000f29c  retn
```
