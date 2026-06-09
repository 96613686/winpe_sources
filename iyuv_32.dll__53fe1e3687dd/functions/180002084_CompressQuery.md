# CompressQuery

- ea: `0x180002084`
- end: `0x1800021ab`
- name: `CompressQuery`
- size: `295`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001dd0`
- `0x180001fe0`
- `0x180002710`

## callees

- `0x180002084`

## pseudocode

```c
__int64 __fastcall CompressQuery(__int64 a1, __int64 a2)
{
  int v3; // eax
  unsigned int v4; // edi
  unsigned int v5; // ebx
  unsigned int v7; // r10d
  int v8; // ecx
  unsigned int v9; // r10d
  char v10; // dl
  int v11; // r8d
  int v12; // eax
  unsigned int v13; // r10d
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  unsigned int v17; // r10d
  int v18; // r9d
  int v19; // edx

  if ( !a1 )
    return 4294967294LL;
  v3 = *(_DWORD *)(a1 + 8);
  if ( v3 > 2048 )
    return 4294967294LL;
  if ( *(int *)(a1 + 4) > 2048 )
    return 4294967294LL;
  if ( v3 < 16 )
    return 4294967294LL;
  if ( *(int *)(a1 + 4) < 16 )
    return 4294967294LL;
  if ( *(_DWORD *)(a1 + 16) )
    return 4294967294LL;
  v4 = (((v3 >> 31) & 3) + v3) & 0xFFFFFFFC;
  if ( !v4 )
    return 4294967294LL;
  v5 = (((*(int *)(a1 + 4) >> 31) & 3) + *(_DWORD *)(a1 + 4)) & 0xFFFFFFFC;
  if ( !v5 || *(_WORD *)(a1 + 12) != 1 || *(_WORD *)(a1 + 14) < 8u )
    return 4294967294LL;
  if ( !a2 )
    return 0;
  v7 = *(_DWORD *)(a2 + 16);
  v8 = (unsigned __int8)v7;
  v9 = v7 >> 8;
  v10 = v9;
  v11 = v8 - 32;
  v12 = (unsigned __int8)v9;
  if ( (unsigned __int8)(v8 - 97) > 0x19u )
    v11 = v8;
  v13 = v9 >> 8;
  v14 = v12 - 32;
  if ( (unsigned __int8)(v10 - 97) > 0x19u )
    v14 = v12;
  v15 = (v14 << 8) + v11;
  v16 = (unsigned __int8)v13 - 32;
  if ( (unsigned __int8)(v13 - 97) > 0x19u )
    v16 = (unsigned __int8)v13;
  v17 = v13 >> 8;
  v18 = v15 + (v16 << 16);
  v19 = (unsigned __int8)v17 - 32;
  if ( (unsigned __int8)(v17 - 97) > 0x19u )
    v19 = (unsigned __int8)v17;
  if ( v18 + (v19 << 24) == 1448433993
    && *(_WORD *)(a2 + 14) == 24
    && v5 == *(_DWORD *)(a2 + 4)
    && v4 == *(_DWORD *)(a2 + 8) )
  {
    return 0;
  }
  else
  {
    return 4294967294LL;
  }
}

```

## disassembly

```asm
0x180002084  mov     [rsp+arg_0], rbx
0x180002089  mov     [rsp+arg_8], rdi
0x18000208e  mov     r11, rdx
0x180002091  test    rcx, rcx
0x180002094  jz      loc_18000219B
0x18000209a  mov     eax, [rcx+8]
0x18000209d  mov     edx, 800h
0x1800020a2  cmp     eax, edx
0x1800020a4  jg      loc_18000219B
0x1800020aa  cmp     [rcx+4], edx
0x1800020ad  jg      loc_18000219B
0x1800020b3  cmp     eax, 10h
0x1800020b6  jl      loc_18000219B
0x1800020bc  cmp     dword ptr [rcx+4], 10h
0x1800020c0  jl      loc_18000219B
0x1800020c6  cmp     dword ptr [rcx+10h], 0
0x1800020ca  jnz     loc_18000219B
0x1800020d0  cdq
0x1800020d1  and     edx, 3
0x1800020d4  lea     edi, [rdx+rax]
0x1800020d7  and     edi, 0FFFFFFFCh
0x1800020da  jz      loc_18000219B
0x1800020e0  mov     eax, [rcx+4]
0x1800020e3  cdq
0x1800020e4  and     edx, 3
0x1800020e7  lea     ebx, [rdx+rax]
0x1800020ea  and     ebx, 0FFFFFFFCh
0x1800020ed  jz      loc_18000219B
0x1800020f3  cmp     word ptr [rcx+0Ch], 1
0x1800020f8  jnz     loc_18000219B
0x1800020fe  cmp     word ptr [rcx+0Eh], 8
0x180002103  jb      loc_18000219B
0x180002109  test    r11, r11
0x18000210c  jnz     short loc_180002115
0x18000210e  xor     eax, eax
0x180002110  jmp     loc_1800021A0
0x180002115  mov     r10d, [r11+10h]
0x180002119  movzx   ecx, r10b
0x18000211d  shr     r10d, 8
0x180002121  movzx   edx, r10b
0x180002125  lea     eax, [rcx-61h]
0x180002128  cmp     al, 19h
0x18000212a  lea     r8d, [rcx-20h]
0x18000212e  mov     eax, edx
0x180002130  cmova   r8d, ecx
0x180002134  sub     dl, 61h ; 'a'
0x180002137  shr     r10d, 8
0x18000213b  cmp     dl, 19h
0x18000213e  movzx   edx, r10b
0x180002142  lea     ecx, [rax-20h]
0x180002145  cmova   ecx, eax
0x180002148  shl     ecx, 8
0x18000214b  lea     eax, [rdx-61h]
0x18000214e  add     r8d, ecx
0x180002151  lea     r9d, [rdx-20h]
0x180002155  cmp     al, 19h
0x180002157  cmova   r9d, edx
0x18000215b  shr     r10d, 8
0x18000215f  movzx   ecx, r10b
0x180002163  shl     r9d, 10h
0x180002167  add     r9d, r8d
0x18000216a  lea     eax, [rcx-61h]
0x18000216d  cmp     al, 19h
0x18000216f  lea     edx, [rcx-20h]
0x180002172  cmova   edx, ecx
0x180002175  shl     edx, 18h
0x180002178  add     edx, r9d
0x18000217b  cmp     edx, 56555949h
0x180002181  jnz     short loc_18000219B
0x180002183  cmp     word ptr [r11+0Eh], 18h
0x180002189  jnz     short loc_18000219B
0x18000218b  cmp     ebx, [r11+4]
0x18000218f  jnz     short loc_18000219B
0x180002191  cmp     edi, [r11+8]
0x180002195  jz      loc_18000210E
0x18000219b  mov     eax, 0FFFFFFFEh
0x1800021a0  mov     rbx, [rsp+arg_0]
0x1800021a5  mov     rdi, [rsp+arg_8]
0x1800021aa  retn
```
