# MupFsctlQueryUncHardeningConfigurationForPath

- ea: `0x140014d38`
- end: `0x140014e2f`
- name: `MupFsctlQueryUncHardeningConfigurationForPath`
- size: `247`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140019d10`

## callees

- `0x140014d38`
- `0x140018570`
- `0x140018980`

## pseudocode

```c
__int64 __fastcall MupFsctlQueryUncHardeningConfigurationForPath(_QWORD *a1)
{
  __int64 v1; // rax
  __int64 v2; // rdx
  unsigned int v4; // ebx
  unsigned __int64 v5; // rcx
  __int64 v6; // r9
  unsigned __int64 v7; // r11
  __int64 v8; // r8
  unsigned __int64 v9; // r10
  _WORD *v10; // rax
  int v11; // eax
  __int64 v12; // rcx
  __int128 v14; // [rsp+20h] [rbp-18h] BYREF
  __int64 v15; // [rsp+40h] [rbp+8h] BYREF

  v1 = a1[23];
  v2 = 0;
  v15 = 0;
  v14 = 0;
  if ( *(_DWORD *)(v1 + 8) < 8u )
    return (unsigned int)-1073741811;
  v5 = *(unsigned int *)(v1 + 16);
  if ( (unsigned int)v5 < 4 )
    return (unsigned int)-1073741811;
  v6 = a1[3];
  if ( *(_DWORD *)v6 < 0xAu || *(_DWORD *)v6 > (unsigned int)v5 )
    return (unsigned int)-1073741811;
  v7 = *(unsigned int *)(v6 + 4);
  v8 = *(unsigned __int16 *)(v6 + 8);
  v9 = v8 + v7;
  if ( v8 + v7 >= v7 && v9 <= 0xFFFFFFFF && v9 <= v5 )
  {
    v10 = (_WORD *)(v7 + v6);
    if ( (((_BYTE)v7 + (_BYTE)v6) & 1) == 0 )
    {
      *((_QWORD *)&v14 + 1) = v7 + v6;
      WORD1(v14) = v8;
      LOWORD(v14) = v8;
      if ( (unsigned __int16)v8 > 4u && *v10 == 92 && v10[1] == 92 )
      {
        v11 = MupiCreatePrefixEntryForPathFromConfiguration(v5, &v14, &v15);
        v2 = v15;
        v4 = v11;
        if ( v11 >= 0 )
        {
          v12 = a1[3];
          v4 = 0;
          *(_QWORD *)v12 = 0;
          *(_DWORD *)v12 = 8;
          *(_DWORD *)(v12 + 4) = *(_DWORD *)(v2 + 88);
          a1[7] = 8;
        }
        goto LABEL_16;
      }
      return (unsigned int)-1073741811;
    }
  }
  v4 = -1073741811;
LABEL_16:
  if ( v2 )
    MupiDereferenceUncHardeningPrefixEntry(v2);
  return v4;
}

```

## disassembly

```asm
0x140014d38  mov     [rsp+arg_8], rbx
0x140014d3d  push    rdi
0x140014d3e  sub     rsp, 30h
0x140014d42  mov     rax, [rcx+0B8h]
0x140014d49  xor     edx, edx
0x140014d4b  xorps   xmm0, xmm0
0x140014d4e  mov     [rsp+38h+arg_0], rdx
0x140014d53  mov     rdi, rcx
0x140014d56  movups  [rsp+38h+var_18], xmm0
0x140014d5b  cmp     dword ptr [rax+8], 8
0x140014d5f  jnb     short loc_140014D6B
0x140014d61  mov     ebx, 0C000000Dh
0x140014d66  jmp     loc_140014E21
0x140014d6b  mov     ecx, [rax+10h]
0x140014d6e  mov     ebx, 4
0x140014d73  cmp     ecx, ebx
0x140014d75  jb      short loc_140014D61
0x140014d77  mov     r9, [rdi+18h]
0x140014d7b  mov     eax, [r9]
0x140014d7e  cmp     eax, 0Ah
0x140014d81  jb      short loc_140014D61
0x140014d83  cmp     eax, ecx
0x140014d85  ja      short loc_140014D61
0x140014d87  mov     r11d, [r9+4]
0x140014d8b  movzx   r8d, word ptr [r9+8]
0x140014d90  lea     r10, [r8+r11]
0x140014d94  cmp     r10, r11
0x140014d97  jb      short loc_140014E0F
0x140014d99  mov     eax, 0FFFFFFFFh
0x140014d9e  cmp     r10, rax
0x140014da1  ja      short loc_140014E0F
0x140014da3  cmp     r10, rcx
0x140014da6  ja      short loc_140014E0F
0x140014da8  lea     rax, [r11+r9]
0x140014dac  test    al, 1
0x140014dae  jnz     short loc_140014E0F
0x140014db0  mov     qword ptr [rsp+38h+var_18+8], rax
0x140014db5  mov     word ptr [rsp+38h+var_18+2], r8w
0x140014dbb  mov     word ptr [rsp+38h+var_18], r8w
0x140014dc1  cmp     r8w, bx
0x140014dc5  jbe     short loc_140014D61
0x140014dc7  cmp     word ptr [rax], 5Ch ; '\'
0x140014dcb  jnz     short loc_140014D61
0x140014dcd  cmp     word ptr [rax+2], 5Ch ; '\'
0x140014dd2  jnz     short loc_140014D61
0x140014dd4  lea     r8, [rsp+38h+arg_0]
0x140014dd9  lea     rdx, [rsp+38h+var_18]
0x140014dde  call    MupiCreatePrefixEntryForPathFromConfiguration
0x140014de3  mov     rdx, [rsp+38h+arg_0]
0x140014de8  mov     ebx, eax
0x140014dea  test    eax, eax
0x140014dec  js      short loc_140014E14
0x140014dee  mov     rcx, [rdi+18h]
0x140014df2  xor     eax, eax
0x140014df4  xor     ebx, ebx
0x140014df6  mov     [rcx], rax
0x140014df9  mov     dword ptr [rcx], 8
0x140014dff  mov     eax, [rdx+58h]
0x140014e02  mov     [rcx+4], eax
0x140014e05  mov     qword ptr [rdi+38h], 8
0x140014e0d  jmp     short loc_140014E14
0x140014e0f  mov     ebx, 0C000000Dh
0x140014e14  test    rdx, rdx
0x140014e17  jz      short loc_140014E21
0x140014e19  mov     rcx, rdx
0x140014e1c  call    MupiDereferenceUncHardeningPrefixEntry
0x140014e21  mov     eax, ebx
0x140014e23  mov     rbx, [rsp+38h+arg_8]
0x140014e28  add     rsp, 30h
0x140014e2c  pop     rdi
0x140014e2d  retn
```
