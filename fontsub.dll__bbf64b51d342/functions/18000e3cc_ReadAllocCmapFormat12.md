# ReadAllocCmapFormat12

- ea: `0x18000e3cc`
- end: `0x18000e4c2`
- name: `ReadAllocCmapFormat12`
- size: `246`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a688`
- `0x18000e9e8`
- `0x1800143f0`

## callees

- `0x18000e3cc`
- `0x180011538`
- `0x180011574`
- `0x18001a3bc`

## pseudocode

```c
__int64 __fastcall ReadAllocCmapFormat12(__int64 a1, unsigned int a2, __int64 a3, __int64 *a4)
{
  __int64 result; // rax
  unsigned int v9; // edi
  __int64 v10; // rax
  unsigned int v11; // ebx
  unsigned int i; // esi
  unsigned __int16 v13; // bp
  unsigned __int16 v14; // [rsp+68h] [rbp+10h] BYREF

  *a4 = 0;
  v14 = 0;
  result = ReadGeneric(a1, a3, 0x10u, (unsigned __int8 *)&CMAP_FORMAT12_CONTROL, a2, &v14);
  if ( !(_WORD)result )
  {
    v9 = *(_DWORD *)(a3 + 12);
    if ( v9 <= 0x15555555 && (v10 = Mem_Alloc(12 * v9), (*a4 = v10) != 0) )
    {
      v11 = a2 + v14;
      for ( i = 0; i < v9; ++i )
      {
        v13 = ReadGeneric(a1, *a4 + 12LL * i, 0xCu, (unsigned __int8 *)&FORMAT12_GROUPS_CONTROL, v11, &v14);
        if ( v13 )
        {
          Mem_Free(*a4);
          result = v13;
          *a4 = 0;
          return result;
        }
        v11 += v14;
      }
      return 0;
    }
    else
    {
      return 1005;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e3cc  mov     r11, rsp
0x18000e3cf  mov     [r11+8], rbx
0x18000e3d3  mov     [r11+18h], rbp
0x18000e3d7  push    rsi
0x18000e3d8  push    rdi
0x18000e3d9  push    r12
0x18000e3db  push    r14
0x18000e3dd  push    r15
0x18000e3df  sub     rsp, 30h
0x18000e3e3  xor     r12d, r12d
0x18000e3e6  lea     rax, [r11+10h]
0x18000e3ea  mov     rdi, r8
0x18000e3ed  mov     [r11-30h], rax
0x18000e3f1  mov     r14, r9
0x18000e3f4  mov     [r9], r12
0x18000e3f7  mov     esi, edx
0x18000e3f9  mov     [rsp+58h+var_38], edx
0x18000e3fd  lea     r8d, [r12+10h]
0x18000e402  mov     [r11+10h], r12w
0x18000e407  lea     r9, CMAP_FORMAT12_CONTROL
0x18000e40e  mov     rdx, rdi
0x18000e411  mov     r15, rcx
0x18000e414  call    ReadGeneric
0x18000e419  test    ax, ax
0x18000e41c  jnz     loc_18000E4AB
0x18000e422  mov     edi, [rdi+0Ch]
0x18000e425  cmp     edi, 15555555h
0x18000e42b  ja      short loc_18000E4A6
0x18000e42d  lea     ecx, [rdi+rdi*2]
0x18000e430  shl     ecx, 2; Size
0x18000e433  call    Mem_Alloc
0x18000e438  mov     [r14], rax
0x18000e43b  test    rax, rax
0x18000e43e  jz      short loc_18000E4A6
0x18000e440  movzx   ebx, [rsp+58h+arg_8]
0x18000e445  add     ebx, esi
0x18000e447  mov     esi, r12d
0x18000e44a  cmp     esi, edi
0x18000e44c  jnb     short loc_18000E4A1
0x18000e44e  mov     eax, esi
0x18000e450  lea     r9, FORMAT12_GROUPS_CONTROL
0x18000e457  mov     r8d, 0Ch
0x18000e45d  lea     rcx, [rax+rax*2]
0x18000e461  mov     rax, [r14]
0x18000e464  lea     rdx, [rax+rcx*4]
0x18000e468  mov     rcx, r15
0x18000e46b  lea     rax, [rsp+58h+arg_8]
0x18000e470  mov     [rsp+58h+var_30], rax
0x18000e475  mov     [rsp+58h+var_38], ebx
0x18000e479  call    ReadGeneric
0x18000e47e  movzx   ebp, ax
0x18000e481  test    ax, ax
0x18000e484  jnz     short loc_18000E491
0x18000e486  movzx   eax, [rsp+58h+arg_8]
0x18000e48b  add     ebx, eax
0x18000e48d  inc     esi
0x18000e48f  jmp     short loc_18000E44A
0x18000e491  mov     rcx, [r14]
0x18000e494  call    Mem_Free
0x18000e499  movzx   eax, bp
0x18000e49c  mov     [r14], r12
0x18000e49f  jmp     short loc_18000E4AB
0x18000e4a1  mov     eax, r12d
0x18000e4a4  jmp     short loc_18000E4AB
0x18000e4a6  mov     eax, 3EDh
0x18000e4ab  mov     rbx, [rsp+58h+arg_0]
0x18000e4b0  mov     rbp, [rsp+58h+arg_10]
0x18000e4b5  add     rsp, 30h
0x18000e4b9  pop     r15
0x18000e4bb  pop     r14
0x18000e4bd  pop     r12
0x18000e4bf  pop     rdi
0x18000e4c0  pop     rsi
0x18000e4c1  retn
```
