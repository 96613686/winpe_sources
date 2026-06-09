# QuicCryptoTlsReadClientHello

- ea: `0x140020d30`
- end: `0x140020e92`
- name: `QuicCryptoTlsReadClientHello`
- size: `354`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140020c50`

## callees

- `0x140020d30`
- `0x140020e98`
- `0x14003ec10`

## string_xrefs

- `0x14003e4bd`: `Parse error. ReadTlsClientHello #1`
- `0x14003e451`: `Parse error. ReadTlsClientHello #2`
- `0x14003e4ab`: `Parse error. ReadTlsClientHello #3`
- `0x14003e463`: `Parse error. ReadTlsClientHello #4`
- `0x14003e499`: `Parse error. ReadTlsClientHello #5`
- `0x14003e487`: `Parse error. ReadTlsClientHello #6`
- `0x14003e475`: `Parse error. ReadTlsClientHello #7`

## pseudocode

```c
__int64 __fastcall QuicCryptoTlsReadClientHello(__int64 a1, unsigned __int8 *a2, unsigned int a3)
{
  __int64 v3; // rbx
  unsigned int v4; // r8d
  unsigned int v5; // r8d
  unsigned __int8 *v6; // rdx
  __int64 v7; // r10
  unsigned __int8 *v8; // r11
  unsigned int v9; // r8d
  unsigned __int16 v10; // dx
  unsigned int v11; // r8d
  unsigned __int8 *v12; // r11
  __int64 v13; // r9
  unsigned int v14; // r8d
  const char *v16; // r9

  v3 = a1;
  if ( a3 < 2 || (unsigned __int16)(a2[1] + (*a2 << 8)) < 0x301u )
  {
    if ( (byte_14005C48B & 4) != 0 )
    {
      v16 = "Parse error. ReadTlsClientHello #1";
      goto LABEL_31;
    }
    return 3221225485LL;
  }
  v4 = a3 - 2;
  if ( v4 < 0x20 )
  {
    if ( (byte_14005C48B & 4) == 0 )
      return 3221225485LL;
    v16 = "Parse error. ReadTlsClientHello #2";
LABEL_31:
    McTemplateU0ps_EtwWriteTransfer(a1, QuicConnError, v3, v16);
    return 3221225485LL;
  }
  v5 = v4 - 32;
  v6 = a2 + 34;
  if ( !v5 || (v7 = *v6, (unsigned __int8)v7 > 0x20u) || (a1 = v7 + 1, v5 < (unsigned __int64)(v7 + 1)) )
  {
    if ( (byte_14005C48B & 4) != 0 )
    {
      v16 = "Parse error. ReadTlsClientHello #3";
      goto LABEL_31;
    }
    return 3221225485LL;
  }
  a1 = *v6;
  v8 = &v6[a1 + 1];
  v9 = -1 - v7 + v5;
  if ( v9 < 2 )
  {
    if ( (byte_14005C48B & 4) == 0 )
      return 3221225485LL;
    v16 = "Parse error. ReadTlsClientHello #4";
    goto LABEL_31;
  }
  v10 = v8[1] + (*v8 << 8);
  a1 = v10;
  if ( (v8[1] & 1) != 0 || v9 < (unsigned int)v10 + 2 )
  {
    if ( (byte_14005C48B & 4) != 0 )
    {
      v16 = "Parse error. ReadTlsClientHello #5";
      goto LABEL_31;
    }
  }
  else
  {
    v11 = -2 - v10 + v9;
    v12 = &v8[v10];
    if ( v11 && (v13 = v12[2], (_BYTE)v13) && (a1 = v13 + 1, v11 >= (unsigned __int64)(v13 + 1)) )
    {
      v14 = -1 - v13 + v11;
      if ( v14 < 2 )
        return 0;
      if ( v14 >= (unsigned int)(unsigned __int16)(v12[v13 + 4] + (v12[v13 + 3] << 8)) + 2 )
        return QuicCryptoTlsReadExtensions(v3);
      if ( (byte_14005C48B & 4) != 0 )
      {
        v16 = "Parse error. ReadTlsClientHello #7";
        goto LABEL_31;
      }
    }
    else if ( (byte_14005C48B & 4) != 0 )
    {
      v16 = "Parse error. ReadTlsClientHello #6";
      goto LABEL_31;
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140020d30  mov     [rsp+arg_0], rbx
0x140020d35  mov     [rsp+arg_8], rsi
0x140020d3a  push    rdi
0x140020d3b  sub     rsp, 20h
0x140020d3f  mov     rdi, r9
0x140020d42  mov     rbx, rcx
0x140020d45  cmp     r8d, 2
0x140020d49  jb      loc_14003E4B4
0x140020d4f  movzx   eax, byte ptr [rdx+1]
0x140020d53  mov     esi, 100h
0x140020d58  movzx   r11d, byte ptr [rdx]
0x140020d5c  imul    r11d, esi
0x140020d60  add     r11w, ax
0x140020d64  mov     eax, 301h
0x140020d69  cmp     r11w, ax
0x140020d6d  jb      loc_14003E4B4
0x140020d73  mov     r9d, 0FFFFFFFEh
0x140020d79  add     r8d, r9d
0x140020d7c  cmp     r8d, 20h ; ' '
0x140020d80  jb      loc_14003E444
0x140020d86  add     r8d, 0FFFFFFE0h
0x140020d8a  add     rdx, 22h ; '"'
0x140020d8e  cmp     r8d, 1
0x140020d92  jb      loc_14003E4A2
0x140020d98  movzx   r10d, byte ptr [rdx]
0x140020d9c  cmp     r10b, 20h ; ' '
0x140020da0  ja      loc_14003E4A2
0x140020da6  lea     rcx, [r10+1]
0x140020daa  mov     eax, r8d
0x140020dad  mov     r11d, r10d
0x140020db0  cmp     rax, rcx
0x140020db3  jb      loc_14003E4A2
0x140020db9  mov     ecx, r10d
0x140020dbc  inc     r11
0x140020dbf  or      r10d, 0FFFFFFFFh
0x140020dc3  add     r11, rdx
0x140020dc6  mov     eax, r10d
0x140020dc9  sub     eax, ecx
0x140020dcb  add     r8d, eax
0x140020dce  cmp     r8d, 2
0x140020dd2  jb      loc_14003E45A
0x140020dd8  movzx   edx, byte ptr [r11]
0x140020ddc  movzx   eax, byte ptr [r11+1]
0x140020de1  imul    edx, esi
0x140020de4  add     dx, ax
0x140020de7  movzx   ecx, dx
0x140020dea  test    cl, 1
0x140020ded  jnz     loc_14003E490
0x140020df3  lea     eax, [rcx+2]
0x140020df6  cmp     r8d, eax
0x140020df9  jb      loc_14003E490
0x140020dff  sub     r9d, ecx
0x140020e02  movzx   eax, dx
0x140020e05  add     r8d, r9d
0x140020e08  add     r11, rax
0x140020e0b  cmp     r8d, 1
0x140020e0f  jb      loc_14003E47E
0x140020e15  movzx   r9d, byte ptr [r11+2]
0x140020e1a  cmp     r9b, 1
0x140020e1e  jb      loc_14003E47E
0x140020e24  lea     rcx, [r9+1]
0x140020e28  mov     eax, r8d
0x140020e2b  mov     edx, r9d
0x140020e2e  cmp     rax, rcx
0x140020e31  jb      loc_14003E47E
0x140020e37  sub     r10d, r9d
0x140020e3a  add     r8d, r10d
0x140020e3d  cmp     r8d, 2
0x140020e41  jb      short loc_140020E8E
0x140020e43  movzx   eax, byte ptr [r11+r9+4]
0x140020e49  movzx   r10d, byte ptr [r11+r9+3]
0x140020e4f  imul    r10d, esi
0x140020e53  add     r10w, ax
0x140020e57  movzx   eax, r10w
0x140020e5b  add     eax, 2
0x140020e5e  cmp     r8d, eax
0x140020e61  jb      loc_14003E46C
0x140020e67  add     r11, 5
0x140020e6b  mov     r9, rdi
0x140020e6e  add     rdx, r11
0x140020e71  movzx   r8d, r10w
0x140020e75  mov     rcx, rbx; int
0x140020e78  call    QuicCryptoTlsReadExtensions
0x140020e7d  mov     rbx, [rsp+28h+arg_0]
0x140020e82  mov     rsi, [rsp+28h+arg_8]
0x140020e87  add     rsp, 20h
0x140020e8b  pop     rdi
0x140020e8c  retn
0x140020e8e  xor     eax, eax
0x140020e90  jmp     short loc_140020E7D
0x14003e444  test    cs:byte_14005C48B, 4
0x14003e44b  jz      loc_14003E4D3
0x14003e451  lea     r9, aParseErrorRead_13; "Parse error. ReadTlsClientHello #2"
0x14003e458  jmp     short loc_14003E4C4
0x14003e45a  test    cs:byte_14005C48B, 4
0x14003e461  jz      short loc_14003E4D3
0x14003e463  lea     r9, aParseErrorRead_8; "Parse error. ReadTlsClientHello #4"
0x14003e46a  jmp     short loc_14003E4C4
0x14003e46c  test    cs:byte_14005C48B, 4
0x14003e473  jz      short loc_14003E4D3
0x14003e475  lea     r9, aParseErrorRead_4; "Parse error. ReadTlsClientHello #7"
0x14003e47c  jmp     short loc_14003E4C4
0x14003e47e  test    cs:byte_14005C48B, 4
0x14003e485  jz      short loc_14003E4D3
0x14003e487  lea     r9, aParseErrorRead; "Parse error. ReadTlsClientHello #6"
0x14003e48e  jmp     short loc_14003E4C4
0x14003e490  test    cs:byte_14005C48B, 4
0x14003e497  jz      short loc_14003E4D3
0x14003e499  lea     r9, aParseErrorRead_12; "Parse error. ReadTlsClientHello #5"
0x14003e4a0  jmp     short loc_14003E4C4
0x14003e4a2  test    cs:byte_14005C48B, 4
0x14003e4a9  jz      short loc_14003E4D3
0x14003e4ab  lea     r9, aParseErrorRead_10; "Parse error. ReadTlsClientHello #3"
0x14003e4b2  jmp     short loc_14003E4C4
0x14003e4b4  test    cs:byte_14005C48B, 4
0x14003e4bb  jz      short loc_14003E4D3
0x14003e4bd  lea     r9, aParseErrorRead_9; "Parse error. ReadTlsClientHello #1"
0x14003e4c4  mov     r8, rbx
0x14003e4c7  lea     rdx, QuicConnError
0x14003e4ce  call    McTemplateU0ps_EtwWriteTransfer
0x14003e4d3  mov     eax, 0C000000Dh
0x14003e4d8  jmp     loc_140020E7D
```
