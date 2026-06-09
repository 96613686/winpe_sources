# _WSManPluginShutdown_::_1_::catch$0

- ea: `0x180009c3d`
- end: `0x180009c89`
- name: `_WSManPluginShutdown_::_1_::catch$0`
- size: `76`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x180009c3d`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009c70`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009c70`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009c5f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009c5f`

## pseudocode

```c
__int64 __fastcall WSManPluginShutdown_::_1_::catch_0(__int64 a1, __int64 a2)
{
  void **v2; // rbx

  v2 = *(void ***)(a2 + 32);
  if ( v2 )
  {
    if ( v2[1] )
    {
      operator delete[](v2[1]);
      v2[1] = 0;
    }
    operator delete(v2);
  }
  return 0;
}

```

## disassembly

```asm
0x180009c3d  mov     [rsp+arg_8], rdx
0x180009c42  push    rbx
0x180009c43  push    rbp
0x180009c44  sub     rsp, 28h
0x180009c48  mov     rbp, rdx
0x180009c4b  mov     rbx, [rbp+20h]
0x180009c4f  test    rbx, rbx
0x180009c52  jz      short loc_180009C77
0x180009c54  cmp     qword ptr [rbx+8], 0
0x180009c59  jz      short loc_180009C6D
0x180009c5b  mov     rcx, [rbx+8]
0x180009c5f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009c65  mov     qword ptr [rbx+8], 0
0x180009c6d  mov     rcx, rbx
0x180009c70  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009c76  nop
0x180009c77  mov     rax, 0
0x180009c81  add     rsp, 28h
0x180009c85  pop     rbp
0x180009c86  pop     rbx
0x180009c87  retn
```
