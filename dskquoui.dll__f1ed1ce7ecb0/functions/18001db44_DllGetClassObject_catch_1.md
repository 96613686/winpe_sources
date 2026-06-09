# DllGetClassObject$catch$1

- ea: `0x18001db44`
- end: `0x18001db7a`
- name: `DllGetClassObject$catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001db44`

## pseudocode

```c
__int64 __fastcall DllGetClassObject_catch_1(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rax

  v2 = *(_QWORD **)(a2 + 96);
  if ( *v2 )
    *v2 = 0;
  *(_DWORD *)(a2 + 96) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x18001db44  mov     [rsp+arg_8], rdx
0x18001db49  push    rbp
0x18001db4a  sub     rsp, 20h
0x18001db4e  mov     rbp, rdx
0x18001db51  mov     rax, [rbp+60h]
0x18001db55  cmp     qword ptr [rax], 0
0x18001db59  jz      short loc_18001DB62
0x18001db5b  mov     qword ptr [rax], 0
0x18001db62  mov     dword ptr [rbp+60h], 8007000Eh
0x18001db69  mov     rax, 0
0x18001db73  add     rsp, 20h
0x18001db77  pop     rbp
0x18001db78  retn
```
