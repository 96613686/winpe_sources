# DrSetFileInfoAtCleanUp(_RX_CONTEXT *)

- ea: `0x140017380`
- end: `0x1400173ba`
- name: `?DrSetFileInfoAtCleanUp@@YAJPEAU_RX_CONTEXT@@@Z`
- size: `58`
- prototype: `__int64 __fastcall(struct _RX_CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x14000324c`
- `0x140017380`

## pseudocode

```c
__int64 __fastcall DrSetFileInfoAtCleanUp(struct _RX_CONTEXT *a1)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140017380  sub     rsp, 28h
0x140017384  mov     rcx, cs:WPP_GLOBAL_Control
0x14001738b  lea     rax, WPP_GLOBAL_Control
0x140017392  cmp     rcx, rax
0x140017395  jz      short loc_1400173B2
0x140017397  cmp     byte ptr [rcx+29h], 4
0x14001739b  jb      short loc_1400173B2
0x14001739d  mov     rcx, [rcx+18h]
0x1400173a1  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x1400173a8  mov     edx, 3Ch ; '<'
0x1400173ad  call    WPP_SF_
0x1400173b2  xor     eax, eax
0x1400173b4  add     rsp, 28h
0x1400173b8  retn
```
