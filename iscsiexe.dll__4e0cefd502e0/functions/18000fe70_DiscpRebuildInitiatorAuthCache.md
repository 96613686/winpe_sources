# DiscpRebuildInitiatorAuthCache

- ea: `0x18000fe70`
- end: `0x18000ff81`
- name: `DiscpRebuildInitiatorAuthCache`
- size: `273`
- prototype: `__int64 __fastcall(__int64, _WORD *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f5b0`

## callees

- `0x18000fb28`
- `0x18000fe70`
- `0x18001048c`

## pseudocode

```c
__int64 __fastcall DiscpRebuildInitiatorAuthCache(__int64 a1, _WORD *a2, __int64 a3, unsigned int a4)
{
  unsigned int v7; // ebx
  unsigned int v8; // ebp
  __int64 v9; // rdi
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rcx
  int v13; // r11d
  int v14; // r15d
  __int64 v15; // r9
  unsigned int v16; // r10d
  unsigned int v17; // r8d
  int v19; // [rsp+40h] [rbp-48h]
  __int64 v20; // [rsp+50h] [rbp-38h] BYREF
  __int64 v21; // [rsp+58h] [rbp-30h] BYREF
  unsigned int v22; // [rsp+90h] [rbp+8h] BYREF

  v22 = 0;
  v21 = 0;
  v20 = 0;
  v7 = DiscpParseCacheName(a2, &v21, &v22, &v20);
  if ( !v7 )
  {
    v8 = 0;
    while ( a4 >= 0x28 )
    {
      v9 = a3 + v8;
      if ( *(_DWORD *)v9 > a4 )
        return (unsigned int)-268500938;
      v10 = *(unsigned int *)(v9 + 24);
      v11 = -1;
      v12 = *(unsigned int *)(v9 + 32);
      v13 = *(_DWORD *)(v9 + 20);
      v14 = *(_DWORD *)(v9 + 28);
      v15 = (unsigned int)(v10 + v13);
      v16 = v12 + v14;
      if ( (unsigned int)v15 >= (unsigned int)v10 )
        v11 = v10 + v13;
      v17 = -1;
      if ( v16 >= (unsigned int)v12 )
        v17 = v12 + v14;
      if ( v11 > *(_DWORD *)v9
        || v17 > *(_DWORD *)v9
        || (unsigned int)v15 < (unsigned int)v10
        || v16 < (unsigned int)v12 )
      {
        return (unsigned int)-268500938;
      }
      LOBYTE(v15) = *(_BYTE *)(v9 + 16);
      LOBYTE(v19) = 0;
      DiscpSetPresharedKey(a1, v22, *(_QWORD *)(v9 + 8), v15, v13, v9 + v10, v14, v9 + v12, v19);
      v8 += *(_DWORD *)v9;
      a4 -= *(_DWORD *)v9;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000fe70  mov     r11, rsp
0x18000fe73  mov     [r11+10h], rbx
0x18000fe77  mov     [r11+18h], rbp
0x18000fe7b  push    rsi
0x18000fe7c  push    rdi
0x18000fe7d  push    r12
0x18000fe7f  push    r14
0x18000fe81  push    r15
0x18000fe83  sub     rsp, 60h
0x18000fe87  mov     rax, rdx
0x18000fe8a  mov     dword ptr [r11+8], 0
0x18000fe92  mov     esi, r9d
0x18000fe95  mov     qword ptr [r11-30h], 0
0x18000fe9d  mov     r14, r8
0x18000fea0  mov     qword ptr [r11-38h], 0
0x18000fea8  mov     r12, rcx
0x18000feab  lea     r9, [r11-38h]
0x18000feaf  mov     rcx, rax
0x18000feb2  lea     r8, [r11+8]
0x18000feb6  lea     rdx, [r11-30h]
0x18000feba  call    DiscpParseCacheName
0x18000febf  mov     ebx, eax
0x18000fec1  test    eax, eax
0x18000fec3  jnz     loc_18000FF66
0x18000fec9  xor     ebp, ebp
0x18000fecb  jmp     loc_18000FF56
0x18000fed0  mov     edi, ebp
0x18000fed2  add     rdi, r14
0x18000fed5  cmp     [rdi], esi
0x18000fed7  ja      loc_18000FF61
0x18000fedd  mov     edx, [rdi+18h]
0x18000fee0  or      eax, 0FFFFFFFFh
0x18000fee3  mov     ecx, [rdi+20h]
0x18000fee6  mov     r11d, [rdi+14h]
0x18000feea  mov     r15d, [rdi+1Ch]
0x18000feee  lea     r9d, [rdx+r11]
0x18000fef2  cmp     r9d, edx
0x18000fef5  lea     r10d, [rcx+r15]
0x18000fef9  cmovnb  eax, r9d
0x18000fefd  or      r8d, 0FFFFFFFFh
0x18000ff01  cmp     r10d, ecx
0x18000ff04  cmovnb  r8d, r10d
0x18000ff08  cmp     eax, [rdi]
0x18000ff0a  ja      short loc_18000FF61
0x18000ff0c  cmp     r8d, [rdi]
0x18000ff0f  ja      short loc_18000FF61
0x18000ff11  cmp     r9d, edx
0x18000ff14  jb      short loc_18000FF61
0x18000ff16  cmp     r10d, ecx
0x18000ff19  jb      short loc_18000FF61
0x18000ff1b  mov     r9b, [rdi+10h]
0x18000ff1f  lea     rax, [rdi+rcx]
0x18000ff23  mov     r8, [rdi+8]
0x18000ff27  lea     rcx, [rdi+rdx]
0x18000ff2b  mov     edx, [rsp+88h+arg_0]
0x18000ff32  mov     byte ptr [rsp+88h+var_48], bl
0x18000ff36  mov     [rsp+88h+var_50], rax
0x18000ff3b  mov     [rsp+88h+var_58], r15d
0x18000ff40  mov     [rsp+88h+var_60], rcx
0x18000ff45  mov     rcx, r12
0x18000ff48  mov     [rsp+88h+var_68], r11d
0x18000ff4d  call    DiscpSetPresharedKey
0x18000ff52  add     ebp, [rdi]
0x18000ff54  sub     esi, [rdi]
0x18000ff56  cmp     esi, 28h ; '('
0x18000ff59  jnb     loc_18000FED0
0x18000ff5f  jmp     short loc_18000FF66
0x18000ff61  mov     ebx, 0EFFF0036h
0x18000ff66  lea     r11, [rsp+88h+var_28]
0x18000ff6b  mov     eax, ebx
0x18000ff6d  mov     rbx, [r11+38h]
0x18000ff71  mov     rbp, [r11+40h]
0x18000ff75  mov     rsp, r11
0x18000ff78  pop     r15
0x18000ff7a  pop     r14
0x18000ff7c  pop     r12
0x18000ff7e  pop     rdi
0x18000ff7f  pop     rsi
0x18000ff80  retn
```
