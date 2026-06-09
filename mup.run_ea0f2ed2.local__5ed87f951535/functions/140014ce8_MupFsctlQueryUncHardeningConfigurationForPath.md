# MupFsctlQueryUncHardeningConfigurationForPath

- ea: `0x140014ce8`
- end: `0x140014ddf`
- name: `MupFsctlQueryUncHardeningConfigurationForPath`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140019cc0`

## callees

- `0x140014ce8`
- `0x140018520`
- `0x140018930`

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
        v11 = MupiCreatePrefixEntryForPathFromConfiguration(v5, (__int64)&v14, &v15);
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
0x140014ce8  mov     [rsp+arg_8], rbx
0x140014ced  push    rdi
0x140014cee  sub     rsp, 30h
0x140014cf2  mov     rax, [rcx+0B8h]
0x140014cf9  xor     edx, edx
0x140014cfb  xorps   xmm0, xmm0
0x140014cfe  mov     [rsp+38h+arg_0], rdx
0x140014d03  mov     rdi, rcx
0x140014d06  movups  [rsp+38h+var_18], xmm0
0x140014d0b  cmp     dword ptr [rax+8], 8
0x140014d0f  jnb     short loc_140014D1B
0x140014d11  mov     ebx, 0C000000Dh
0x140014d16  jmp     loc_140014DD1
0x140014d1b  mov     ecx, [rax+10h]
0x140014d1e  mov     ebx, 4
0x140014d23  cmp     ecx, ebx
0x140014d25  jb      short loc_140014D11
0x140014d27  mov     r9, [rdi+18h]
0x140014d2b  mov     eax, [r9]
0x140014d2e  cmp     eax, 0Ah
0x140014d31  jb      short loc_140014D11
0x140014d33  cmp     eax, ecx
0x140014d35  ja      short loc_140014D11
0x140014d37  mov     r11d, [r9+4]
0x140014d3b  movzx   r8d, word ptr [r9+8]
0x140014d40  lea     r10, [r8+r11]
0x140014d44  cmp     r10, r11
0x140014d47  jb      short loc_140014DBF
0x140014d49  mov     eax, 0FFFFFFFFh
0x140014d4e  cmp     r10, rax
0x140014d51  ja      short loc_140014DBF
0x140014d53  cmp     r10, rcx
0x140014d56  ja      short loc_140014DBF
0x140014d58  lea     rax, [r11+r9]
0x140014d5c  test    al, 1
0x140014d5e  jnz     short loc_140014DBF
0x140014d60  mov     qword ptr [rsp+38h+var_18+8], rax
0x140014d65  mov     word ptr [rsp+38h+var_18+2], r8w
0x140014d6b  mov     word ptr [rsp+38h+var_18], r8w
0x140014d71  cmp     r8w, bx
0x140014d75  jbe     short loc_140014D11
0x140014d77  cmp     word ptr [rax], 5Ch ; '\'
0x140014d7b  jnz     short loc_140014D11
0x140014d7d  cmp     word ptr [rax+2], 5Ch ; '\'
0x140014d82  jnz     short loc_140014D11
0x140014d84  lea     r8, [rsp+38h+arg_0]
0x140014d89  lea     rdx, [rsp+38h+var_18]
0x140014d8e  call    MupiCreatePrefixEntryForPathFromConfiguration
0x140014d93  mov     rdx, [rsp+38h+arg_0]
0x140014d98  mov     ebx, eax
0x140014d9a  test    eax, eax
0x140014d9c  js      short loc_140014DC4
0x140014d9e  mov     rcx, [rdi+18h]
0x140014da2  xor     eax, eax
0x140014da4  xor     ebx, ebx
0x140014da6  mov     [rcx], rax
0x140014da9  mov     dword ptr [rcx], 8
0x140014daf  mov     eax, [rdx+58h]
0x140014db2  mov     [rcx+4], eax
0x140014db5  mov     qword ptr [rdi+38h], 8
0x140014dbd  jmp     short loc_140014DC4
0x140014dbf  mov     ebx, 0C000000Dh
0x140014dc4  test    rdx, rdx
0x140014dc7  jz      short loc_140014DD1
0x140014dc9  mov     rcx, rdx
0x140014dcc  call    MupiDereferenceUncHardeningPrefixEntry
0x140014dd1  mov     eax, ebx
0x140014dd3  mov     rbx, [rsp+38h+arg_8]
0x140014dd8  add     rsp, 30h
0x140014ddc  pop     rdi
0x140014ddd  retn
```
