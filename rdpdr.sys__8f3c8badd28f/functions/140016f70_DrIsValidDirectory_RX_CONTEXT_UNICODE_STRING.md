# DrIsValidDirectory(_RX_CONTEXT *,_UNICODE_STRING *)

- ea: `0x140016f70`
- end: `0x140016faa`
- name: `?DrIsValidDirectory@@YAJPEAU_RX_CONTEXT@@PEAU_UNICODE_STRING@@@Z`
- size: `58`
- prototype: `__int64 __fastcall(struct _RX_CONTEXT *, struct _UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000324c`
- `0x140016f70`

## pseudocode

```c
__int64 __fastcall DrIsValidDirectory(struct _RX_CONTEXT *a1, struct _UNICODE_STRING *a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140016f70  sub     rsp, 28h
0x140016f74  mov     rcx, cs:WPP_GLOBAL_Control
0x140016f7b  lea     rax, WPP_GLOBAL_Control
0x140016f82  cmp     rcx, rax
0x140016f85  jz      short loc_140016FA2
0x140016f87  cmp     byte ptr [rcx+29h], 4
0x140016f8b  jb      short loc_140016FA2
0x140016f8d  mov     rcx, [rcx+18h]
0x140016f91  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x140016f98  mov     edx, 3Fh ; '?'
0x140016f9d  call    WPP_SF_
0x140016fa2  xor     eax, eax
0x140016fa4  add     rsp, 28h
0x140016fa8  retn
```
