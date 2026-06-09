# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x180012c80`
- end: `0x180012ced`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `109`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001b24`
- `0x180012c80`
- `0x18001c010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180012cd3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180012cd3`

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
0x180012c80  test    rcx, rcx
0x180012c83  jz      short locret_180012CEC
0x180012c85  mov     [rsp+arg_0], rbx
0x180012c8a  push    rdi
0x180012c8b  sub     rsp, 20h
0x180012c8f  mov     rdi, rcx
0x180012c92  mov     rcx, [rcx+18h]
0x180012c96  test    rcx, rcx
0x180012c99  jz      short loc_180012CA7
0x180012c9b  mov     rax, [rcx]
0x180012c9e  mov     rax, [rax+10h]
0x180012ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ca7  mov     qword ptr [rdi+18h], 0
0x180012caf  mov     rcx, [rdi+28h]; void *
0x180012cb3  test    rcx, rcx
0x180012cb6  jz      short loc_180012CDA
0x180012cb8  lea     rbx, [rcx-8]
0x180012cbc  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180012cc3  mov     r8, [rbx]; unsigned __int64
0x180012cc6  mov     edx, 10h; unsigned __int64
0x180012ccb  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180012cd0  mov     rcx, rbx
0x180012cd3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180012cd9  nop
0x180012cda  mov     qword ptr [rdi+28h], 0
0x180012ce2  mov     rbx, [rsp+28h+arg_0]
0x180012ce7  add     rsp, 20h
0x180012ceb  pop     rdi
0x180012cec  retn
```
