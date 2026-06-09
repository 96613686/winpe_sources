# _WSManPluginStartup_::_1_::catch$1

- ea: `0x180009d6a`
- end: `0x180009dc2`
- name: `_WSManPluginStartup_::_1_::catch$1`
- size: `88`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x180009d6a`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009da9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009da9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009d98`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009d98`

## pseudocode

```c
__int64 __fastcall WSManPluginStartup_::_1_::catch_1(__int64 a1, __int64 a2)
{
  void **v2; // rbx

  *(_DWORD *)(a2 + 88) = 1101;
  v2 = *(void ***)(a2 + 40);
  if ( v2 )
  {
    *(_DWORD *)(a2 + 88) = *(_DWORD *)v2;
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
0x180009d6a  mov     [rsp+arg_8], rdx
0x180009d6f  push    rbx
0x180009d70  push    rbp
0x180009d71  sub     rsp, 28h
0x180009d75  mov     rbp, rdx
0x180009d78  mov     dword ptr [rbp+58h], 44Dh
0x180009d7f  mov     rbx, [rbp+28h]
0x180009d83  test    rbx, rbx
0x180009d86  jz      short loc_180009DB0
0x180009d88  mov     eax, [rbx]
0x180009d8a  mov     [rbp+58h], eax
0x180009d8d  cmp     qword ptr [rbx+8], 0
0x180009d92  jz      short loc_180009DA6
0x180009d94  mov     rcx, [rbx+8]
0x180009d98  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009d9e  mov     qword ptr [rbx+8], 0
0x180009da6  mov     rcx, rbx
0x180009da9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009daf  nop
0x180009db0  mov     rax, 0
0x180009dba  add     rsp, 28h
0x180009dbe  pop     rbp
0x180009dbf  pop     rbx
0x180009dc0  retn
```
