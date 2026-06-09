# DynArrayGetCount2

- ea: `0x14000e838`
- end: `0x14000e873`
- name: `DynArrayGetCount2`
- size: `59`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000caa8`
- `0x14000cd48`
- `0x14000cf88`
- `0x14000d8b4`

## callees

- `0x14000e838`
- `0x14000ec3c`

## pseudocode

```c
__int64 __fastcall DynArrayGetCount2(__int64 a1, unsigned int a2)
{
  __int64 Item; // rax
  _DWORD *v3; // rax

  Item = _DynArrayGetItem(qword_140014218, a2, 0);
  if ( Item && *(_DWORD *)(Item + 4) == 0x80000 && (v3 = *(_DWORD **)(Item + 16)) != 0 && *v3 == 9 )
    return (unsigned int)v3[1];
  else
    return 0;
}

```

## disassembly

```asm
0x14000e838  sub     rsp, 28h
0x14000e83c  mov     rcx, cs:qword_140014218
0x14000e843  xor     r8d, r8d
0x14000e846  call    __DynArrayGetItem
0x14000e84b  test    rax, rax
0x14000e84e  jz      short loc_14000E86C
0x14000e850  cmp     dword ptr [rax+4], 80000h
0x14000e857  jnz     short loc_14000E86C
0x14000e859  mov     rax, [rax+10h]
0x14000e85d  test    rax, rax
0x14000e860  jz      short loc_14000E86C
0x14000e862  cmp     dword ptr [rax], 9
0x14000e865  jnz     short loc_14000E86C
0x14000e867  mov     eax, [rax+4]
0x14000e86a  jmp     short loc_14000E86E
0x14000e86c  xor     eax, eax
0x14000e86e  add     rsp, 28h
0x14000e872  retn
```
