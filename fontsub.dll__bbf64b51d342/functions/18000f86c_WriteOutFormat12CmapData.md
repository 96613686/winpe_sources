# WriteOutFormat12CmapData

- ea: `0x18000f86c`
- end: `0x18000f921`
- name: `WriteOutFormat12CmapData`
- size: `181`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a688`
- `0x1800118bc`

## callees

- `0x18000f86c`
- `0x18001a808`

## pseudocode

```c
__int16 __fastcall WriteOutFormat12CmapData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        _DWORD *a6)
{
  __int16 result; // ax
  unsigned int v10; // edi
  unsigned int v11; // ebx
  _WORD v12[36]; // [rsp+30h] [rbp-48h] BYREF

  v12[0] = 0;
  result = WriteGeneric(a1, a2, 0x10u, (unsigned __int8 *)&CMAP_FORMAT12_CONTROL, a5, v12);
  if ( !result )
  {
    v10 = 0;
    v11 = a5 + v12[0];
    while ( v10 < a4 )
    {
      result = WriteGeneric(a1, a3 + 12LL * v10, 0xCu, (unsigned __int8 *)&FORMAT12_GROUPS_CONTROL, v11, v12);
      if ( result )
        return result;
      v11 += v12[0];
      ++v10;
    }
    *a6 = v11 - a5;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000f86c  push    rbx
0x18000f86e  push    rbp
0x18000f86f  push    rsi
0x18000f870  push    rdi
0x18000f871  push    r12
0x18000f873  push    r14
0x18000f875  push    r15
0x18000f877  sub     rsp, 40h
0x18000f87b  mov     esi, [rsp+78h+arg_20]
0x18000f882  lea     rax, [rsp+78h+var_48]
0x18000f887  xor     r12d, r12d
0x18000f88a  mov     [rsp+78h+var_50], rax
0x18000f88f  mov     ebp, r9d
0x18000f892  mov     [rsp+78h+var_48], r12w
0x18000f898  mov     r15, r8
0x18000f89b  mov     [rsp+78h+var_58], esi
0x18000f89f  lea     r9, CMAP_FORMAT12_CONTROL
0x18000f8a6  mov     r14, rcx
0x18000f8a9  lea     r8d, [r12+10h]
0x18000f8ae  call    WriteGeneric
0x18000f8b3  test    ax, ax
0x18000f8b6  jnz     short loc_18000F912
0x18000f8b8  movzx   ebx, [rsp+78h+var_48]
0x18000f8bd  mov     edi, r12d
0x18000f8c0  add     ebx, esi
0x18000f8c2  cmp     edi, ebp
0x18000f8c4  jnb     short loc_18000F903
0x18000f8c6  mov     eax, edi
0x18000f8c8  lea     r9, FORMAT12_GROUPS_CONTROL
0x18000f8cf  mov     r8d, 0Ch
0x18000f8d5  lea     rcx, [rax+rax*2]
0x18000f8d9  lea     rax, [rsp+78h+var_48]
0x18000f8de  lea     rdx, [r15+rcx*4]
0x18000f8e2  mov     [rsp+78h+var_50], rax
0x18000f8e7  mov     rcx, r14
0x18000f8ea  mov     [rsp+78h+var_58], ebx
0x18000f8ee  call    WriteGeneric
0x18000f8f3  test    ax, ax
0x18000f8f6  jnz     short loc_18000F912
0x18000f8f8  movzx   eax, [rsp+78h+var_48]
0x18000f8fd  add     ebx, eax
0x18000f8ff  inc     edi
0x18000f901  jmp     short loc_18000F8C2
0x18000f903  mov     rax, [rsp+78h+arg_28]
0x18000f90b  sub     ebx, esi
0x18000f90d  mov     [rax], ebx
0x18000f90f  mov     eax, r12d
0x18000f912  add     rsp, 40h
0x18000f916  pop     r15
0x18000f918  pop     r14
0x18000f91a  pop     r12
0x18000f91c  pop     rdi
0x18000f91d  pop     rsi
0x18000f91e  pop     rbp
0x18000f91f  pop     rbx
0x18000f920  retn
```
