# mwGetLevel

- ea: `0x180001df8`
- end: `0x180001f9b`
- name: `mwGetLevel`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001860`

## callees

- `0x180001df8`

## pseudocode

```c
__int64 __fastcall mwGetLevel(__int64 a1, __int16 *a2, int a3)
{
  _WORD *v3; // rax
  __int16 v4; // r10
  int v5; // r9d
  int v6; // r10d
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  __int16 v11; // r11
  int v12; // r9d
  int v13; // ebx
  int v14; // ecx
  int v15; // eax
  unsigned __int8 *v16; // rdx
  int v17; // ecx
  int v18; // eax
  int v19; // edi
  int v20; // eax
  __int16 *v21; // rdx
  int v22; // edi
  int v23; // eax

  v3 = *(_WORD **)(a1 + 168);
  if ( *v3 == 1 )
  {
    if ( v3[1] == 1 )
    {
      v4 = v3[7];
      v5 = 0;
      if ( v4 == 8 )
      {
        for ( ; a3; a2 = (__int16 *)((char *)a2 + 1) )
        {
          v6 = *(unsigned __int8 *)a2;
          --a3;
          v7 = v6 - 128;
          if ( (unsigned __int8)v6 <= 0x80u )
            v7 = 128 - v6;
          if ( v7 > v5 )
          {
            v5 = 128 - v6;
            if ( (unsigned __int8)v6 > 0x80u )
              v5 = v6 - 128;
          }
        }
        return (unsigned int)v5;
      }
      if ( v4 == 16 )
      {
        for ( ; a3; a3 -= 2 )
        {
          v8 = *a2;
          v9 = v8;
          if ( *a2 <= 0 )
            v9 = -v8;
          if ( v9 > v5 )
          {
            v5 = -v8;
            if ( *a2 > 0 )
              v5 = *a2;
          }
          ++a2;
        }
        return (unsigned int)v5;
      }
      return 0;
    }
    if ( v3[1] == 2 )
    {
      v11 = v3[7];
      v12 = 0;
      v13 = 0;
      if ( v11 == 8 )
      {
        for ( ; a3; a3 -= 2 )
        {
          v14 = *(unsigned __int8 *)a2;
          v15 = v14 - 128;
          if ( (unsigned __int8)v14 <= 0x80u )
            v15 = 128 - v14;
          if ( v15 > v12 )
          {
            v12 = 128 - v14;
            if ( (unsigned __int8)v14 > 0x80u )
              v12 = v14 - 128;
          }
          v16 = (unsigned __int8 *)a2 + 1;
          v17 = *v16;
          v18 = v17 - 128;
          if ( (unsigned __int8)v17 <= 0x80u )
            v18 = 128 - v17;
          if ( v18 > v13 )
          {
            v13 = 128 - v17;
            if ( (unsigned __int8)v17 > 0x80u )
              v13 = v17 - 128;
          }
          a2 = (__int16 *)(v16 + 1);
        }
        return (unsigned __int16)v12 | ((unsigned __int16)v13 << 16);
      }
      if ( v11 == 16 )
      {
        for ( ; a3; a3 -= 4 )
        {
          v19 = *a2;
          v20 = v19;
          if ( *a2 <= 0 )
            v20 = -v19;
          if ( v20 > v12 )
          {
            v12 = -v19;
            if ( *a2 > 0 )
              v12 = *a2;
          }
          v21 = a2 + 1;
          v22 = *v21;
          v23 = v22;
          if ( *v21 <= 0 )
            v23 = -v22;
          if ( v23 > v13 )
          {
            v13 = -v22;
            if ( *v21 > 0 )
              v13 = *v21;
          }
          a2 = v21 + 1;
        }
        return (unsigned __int16)v12 | ((unsigned __int16)v13 << 16);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001df8  push    rbx
0x180001dfa  push    rbp
0x180001dfb  push    rsi
0x180001dfc  push    rdi
0x180001dfd  mov     rax, [rcx+0A8h]
0x180001e04  mov     ebp, 1
0x180001e09  cmp     [rax], bp
0x180001e0c  jnz     loc_180001F94
0x180001e12  cmp     [rax+2], bp
0x180001e16  jnz     loc_180001EAF
0x180001e1c  movzx   r10d, word ptr [rax+0Eh]
0x180001e21  xor     ecx, ecx
0x180001e23  mov     r9d, ecx
0x180001e26  cmp     r10w, 8
0x180001e2b  jnz     short loc_180001E68
0x180001e2d  test    r8d, r8d
0x180001e30  jz      short loc_180001EA7
0x180001e32  lea     r11d, [rbp+7Fh]
0x180001e36  movzx   r10d, byte ptr [rdx]
0x180001e3a  sub     r8d, ebp
0x180001e3d  mov     ebx, r11d
0x180001e40  sub     ebx, r10d
0x180001e43  cmp     r10b, r11b
0x180001e46  lea     edi, [r10-80h]
0x180001e4a  mov     eax, edi
0x180001e4c  cmovbe  eax, ebx
0x180001e4f  cmp     eax, r9d
0x180001e52  jle     short loc_180001E5E
0x180001e54  cmp     r10b, r11b
0x180001e57  mov     r9d, ebx
0x180001e5a  cmova   r9d, edi
0x180001e5e  add     rdx, rbp
0x180001e61  test    r8d, r8d
0x180001e64  jnz     short loc_180001E36
0x180001e66  jmp     short loc_180001EA7
0x180001e68  cmp     r10w, 10h
0x180001e6d  jnz     loc_180001F94
0x180001e73  test    r8d, r8d
0x180001e76  jz      short loc_180001EA7
0x180001e78  mov     r10d, 2
0x180001e7e  movsx   ebx, word ptr [rdx]
0x180001e81  mov     r11d, ebx
0x180001e84  mov     eax, ebx
0x180001e86  neg     r11d
0x180001e89  cmp     [rdx], cx
0x180001e8c  cmovle  eax, r11d
0x180001e90  cmp     eax, r9d
0x180001e93  jle     short loc_180001E9F
0x180001e95  cmp     [rdx], cx
0x180001e98  mov     r9d, r11d
0x180001e9b  cmovg   r9d, ebx
0x180001e9f  add     rdx, r10
0x180001ea2  sub     r8d, r10d
0x180001ea5  jnz     short loc_180001E7E
0x180001ea7  mov     eax, r9d
0x180001eaa  jmp     loc_180001F96
0x180001eaf  mov     r10d, 2
0x180001eb5  cmp     [rax+2], r10w
0x180001eba  jnz     loc_180001F94
0x180001ec0  movzx   r11d, word ptr [rax+0Eh]
0x180001ec5  xor     ecx, ecx
0x180001ec7  mov     r9d, ecx
0x180001eca  mov     ebx, ecx
0x180001ecc  cmp     r11w, 8
0x180001ed1  jnz     short loc_180001F2E
0x180001ed3  test    r8d, r8d
0x180001ed6  jz      loc_180001F86
0x180001edc  lea     r11d, [r10+7Eh]
0x180001ee0  movzx   ecx, byte ptr [rdx]
0x180001ee3  mov     edi, r11d
0x180001ee6  sub     edi, ecx
0x180001ee8  cmp     cl, r11b
0x180001eeb  lea     esi, [rcx-80h]
0x180001eee  mov     eax, esi
0x180001ef0  cmovbe  eax, edi
0x180001ef3  cmp     eax, r9d
0x180001ef6  jle     short loc_180001F02
0x180001ef8  cmp     cl, r11b
0x180001efb  mov     r9d, edi
0x180001efe  cmova   r9d, esi
0x180001f02  add     rdx, rbp
0x180001f05  mov     edi, r11d
0x180001f08  movzx   ecx, byte ptr [rdx]
0x180001f0b  sub     edi, ecx
0x180001f0d  cmp     cl, r11b
0x180001f10  lea     esi, [rcx-80h]
0x180001f13  mov     eax, esi
0x180001f15  cmovbe  eax, edi
0x180001f18  cmp     eax, ebx
0x180001f1a  jle     short loc_180001F24
0x180001f1c  cmp     cl, r11b
0x180001f1f  mov     ebx, edi
0x180001f21  cmova   ebx, esi
0x180001f24  add     rdx, rbp
0x180001f27  sub     r8d, r10d
0x180001f2a  jnz     short loc_180001EE0
0x180001f2c  jmp     short loc_180001F86
0x180001f2e  cmp     r11w, 10h
0x180001f33  jnz     short loc_180001F94
0x180001f35  test    r8d, r8d
0x180001f38  jz      short loc_180001F86
0x180001f3a  movsx   edi, word ptr [rdx]
0x180001f3d  mov     r11d, edi
0x180001f40  mov     eax, edi
0x180001f42  neg     r11d
0x180001f45  cmp     [rdx], cx
0x180001f48  cmovle  eax, r11d
0x180001f4c  cmp     eax, r9d
0x180001f4f  jle     short loc_180001F5B
0x180001f51  cmp     [rdx], cx
0x180001f54  mov     r9d, r11d
0x180001f57  cmovg   r9d, edi
0x180001f5b  add     rdx, r10
0x180001f5e  movsx   edi, word ptr [rdx]
0x180001f61  mov     r11d, edi
0x180001f64  mov     eax, edi
0x180001f66  neg     r11d
0x180001f69  cmp     [rdx], cx
0x180001f6c  cmovle  eax, r11d
0x180001f70  cmp     eax, ebx
0x180001f72  jle     short loc_180001F7D
0x180001f74  cmp     [rdx], cx
0x180001f77  mov     ebx, r11d
0x180001f7a  cmovg   ebx, edi
0x180001f7d  add     rdx, r10
0x180001f80  sub     r8d, 4
0x180001f84  jnz     short loc_180001F3A
0x180001f86  movzx   eax, bx
0x180001f89  shl     eax, 10h
0x180001f8c  movzx   ecx, r9w
0x180001f90  or      eax, ecx
0x180001f92  jmp     short loc_180001F96
0x180001f94  xor     eax, eax
0x180001f96  pop     rdi
0x180001f97  pop     rsi
0x180001f98  pop     rbp
0x180001f99  pop     rbx
0x180001f9a  retn
```
