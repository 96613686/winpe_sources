# NetClassInstaller$catch$0

- ea: `0x180012618`
- end: `0x18001263d`
- name: `NetClassInstaller$catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
__int64 __fastcall NetClassInstaller_catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 104) = 8;
  return 0;
}

```

## disassembly

```asm
0x180012618  mov     [rsp+arg_8], rdx
0x18001261d  push    rbp
0x18001261e  sub     rsp, 20h
0x180012622  mov     rbp, rdx
0x180012625  mov     dword ptr [rbp+68h], 8
0x18001262c  mov     rax, 0
0x180012636  add     rsp, 20h
0x18001263a  pop     rbp
0x18001263b  retn
```
