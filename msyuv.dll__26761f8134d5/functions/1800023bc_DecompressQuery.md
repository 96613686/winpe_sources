# DecompressQuery

- ea: `0x1800023bc`
- end: `0x18000250b`
- name: `DecompressQuery`
- size: `335`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001cc0`
- `0x1800021c8`
- `0x180002b54`

## callees

- `0x1800023bc`
- `0x180002604`

## pseudocode

```c
__int64 __fastcall DecompressQuery(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // edx
  unsigned int v7; // r9d
  int v8; // ecx
  int v9; // eax
  int v11; // r8d
  int v12; // ecx
  __int16 v13; // cx
  int v14; // eax
  int v15; // eax

  if ( a2 )
  {
    if ( (unsigned int)ValidateBitmapInfoHeader(a2) )
    {
      if ( *(_WORD *)(a2 + 14) == 16 )
      {
        v6 = *(_DWORD *)(a2 + 16);
        if ( v6 == 1498831189 || v6 == 844715353 || v6 == 1431918169 )
        {
          v7 = *(_DWORD *)(a2 + 4);
          if ( v7 > 0x4E20 )
            return 4294967289LL;
          v8 = *(_DWORD *)(a2 + 8);
          if ( !v8 )
            return 4294967289LL;
          v9 = -v8;
          if ( v8 > 0 )
            v9 = *(_DWORD *)(a2 + 8);
          if ( v9 > 20000 )
            return 4294967289LL;
          if ( !a3 )
            return 0;
          if ( *(_DWORD *)(a3 + 4) > 0x4E20u )
            return 4294967289LL;
          v11 = *(_DWORD *)(a3 + 8);
          if ( !v11 )
            return 4294967289LL;
          v12 = -v11;
          if ( v11 > 0 )
            v12 = *(_DWORD *)(a3 + 8);
          if ( v12 > 20000 )
            return 4294967289LL;
          if ( *(_DWORD *)(a3 + 4) == v7 && v12 == v9 )
          {
            v13 = *(_WORD *)(a3 + 14);
            if ( ((v13 - 8) & 0xFFE7) == 0 )
            {
              v14 = *(_DWORD *)(a3 + 16);
              if ( !v14 )
                goto LABEL_33;
              if ( v14 == 3 )
              {
                if ( ((v13 - 8) & 0xFFF7) == 0
                  && *(_DWORD *)(a3 + 40) == 63488
                  && *(_DWORD *)(a3 + 44) == 2016
                  && *(_DWORD *)(a3 + 48) == 31 )
                {
                  v15 = 1;
LABEL_34:
                  *(_DWORD *)(a1 + 16) = v15;
                  return 0;
                }
                return 4294967294LL;
              }
              if ( (v14 == 1498831189 || v14 == 844715353 || v14 == 1431918169) && v6 == v14 )
              {
LABEL_33:
                v15 = 0;
                goto LABEL_34;
              }
            }
          }
        }
      }
    }
  }
  return 4294967294LL;
}

```

## disassembly

```asm
0x1800023bc  mov     [rsp+arg_0], rbx
0x1800023c1  mov     [rsp+arg_8], rsi
0x1800023c6  push    rdi
0x1800023c7  sub     rsp, 20h
0x1800023cb  mov     rbx, r8
0x1800023ce  mov     rdi, rdx
0x1800023d1  mov     rsi, rcx
0x1800023d4  test    rdx, rdx
0x1800023d7  jz      loc_1800024F6
0x1800023dd  mov     rcx, rdx
0x1800023e0  call    ValidateBitmapInfoHeader
0x1800023e5  test    eax, eax
0x1800023e7  jz      loc_1800024F6
0x1800023ed  cmp     word ptr [rdi+0Eh], 10h
0x1800023f2  jnz     loc_1800024F6
0x1800023f8  mov     edx, [rdi+10h]
0x1800023fb  mov     r11d, 55595659h
0x180002401  cmp     edx, 59565955h
0x180002407  jz      short loc_18000241A
0x180002409  cmp     edx, 32595559h
0x18000240f  jz      short loc_18000241A
0x180002411  cmp     edx, r11d
0x180002414  jnz     loc_1800024F6
0x18000241a  mov     r9d, [rdi+4]
0x18000241e  mov     r10d, 4E20h
0x180002424  cmp     r9d, r10d
0x180002427  ja      loc_1800024EF
0x18000242d  mov     ecx, [rdi+8]
0x180002430  test    ecx, ecx
0x180002432  jz      loc_1800024EF
0x180002438  mov     eax, ecx
0x18000243a  neg     eax
0x18000243c  cmovs   eax, ecx
0x18000243f  cmp     eax, r10d
0x180002442  jg      loc_1800024EF
0x180002448  test    rbx, rbx
0x18000244b  jnz     short loc_180002454
0x18000244d  xor     eax, eax
0x18000244f  jmp     loc_1800024FB
0x180002454  cmp     [rbx+4], r10d
0x180002458  ja      loc_1800024EF
0x18000245e  mov     r8d, [rbx+8]
0x180002462  test    r8d, r8d
0x180002465  jz      loc_1800024EF
0x18000246b  mov     ecx, r8d
0x18000246e  neg     ecx
0x180002470  cmovs   ecx, r8d
0x180002474  cmp     ecx, r10d
0x180002477  jg      short loc_1800024EF
0x180002479  cmp     [rbx+4], r9d
0x18000247d  jnz     short loc_1800024F6
0x18000247f  cmp     ecx, eax
0x180002481  jnz     short loc_1800024F6
0x180002483  movzx   ecx, word ptr [rbx+0Eh]
0x180002487  mov     r8d, 0FFE7h
0x18000248d  lea     eax, [rcx-8]
0x180002490  test    r8w, ax
0x180002494  jnz     short loc_1800024F6
0x180002496  mov     eax, [rbx+10h]
0x180002499  test    eax, eax
0x18000249b  jz      short loc_1800024E5
0x18000249d  cmp     eax, 3
0x1800024a0  jnz     short loc_1800024CE
0x1800024a2  sub     cx, 8
0x1800024a6  lea     eax, [r8+10h]
0x1800024aa  test    ax, cx
0x1800024ad  jnz     short loc_1800024F6
0x1800024af  cmp     dword ptr [rbx+28h], 0F800h
0x1800024b6  jnz     short loc_1800024F6
0x1800024b8  cmp     dword ptr [rbx+2Ch], 7E0h
0x1800024bf  jnz     short loc_1800024F6
0x1800024c1  cmp     dword ptr [rbx+30h], 1Fh
0x1800024c5  jnz     short loc_1800024F6
0x1800024c7  mov     eax, 1
0x1800024cc  jmp     short loc_1800024E7
0x1800024ce  cmp     eax, 59565955h
0x1800024d3  jz      short loc_1800024E1
0x1800024d5  cmp     eax, 32595559h
0x1800024da  jz      short loc_1800024E1
0x1800024dc  cmp     eax, r11d
0x1800024df  jnz     short loc_1800024F6
0x1800024e1  cmp     edx, eax
0x1800024e3  jnz     short loc_1800024F6
0x1800024e5  xor     eax, eax
0x1800024e7  mov     [rsi+10h], eax
0x1800024ea  jmp     loc_18000244D
0x1800024ef  mov     eax, 0FFFFFFF9h
0x1800024f4  jmp     short loc_1800024FB
0x1800024f6  mov     eax, 0FFFFFFFEh
0x1800024fb  mov     rbx, [rsp+28h+arg_0]
0x180002500  mov     rsi, [rsp+28h+arg_8]
0x180002505  add     rsp, 20h
0x180002509  pop     rdi
0x18000250a  retn
```
