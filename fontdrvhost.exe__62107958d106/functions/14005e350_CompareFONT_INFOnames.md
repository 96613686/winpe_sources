# CompareFONT_INFOnames

- ea: `0x14005e350`
- end: `0x14005e471`
- name: `CompareFONT_INFOnames`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14005e350`
- `0x140076ede`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005e3bd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005e3bd`

## pseudocode

```c
__int64 __fastcall CompareFONT_INFOnames(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  char v3; // r15
  unsigned __int16 v4; // di
  unsigned __int16 v5; // si
  unsigned __int8 v6; // al
  unsigned __int8 v7; // r9
  _WORD *v8; // r14
  _WORD *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // eax

  v2 = 1;
  v3 = 0;
  v4 = *(_WORD *)(a1 + 1058);
  v5 = *(_WORD *)(a2 + 1058);
  if ( ((unsigned __int8)v4 & (unsigned __int8)v5 & 0xC) != 0 )
  {
    v6 = *(_BYTE *)(a1 + 1109);
    if ( (v6 & 4) != 0 || (v7 = *(_BYTE *)(a2 + 1109), (v7 & 4) != 0) )
    {
      v3 = 1;
      v4 = *(_WORD *)(a1 + 1058) & 3;
      v5 &= 3u;
      v7 = *(_BYTE *)(a2 + 1109);
    }
    v8 = (_WORD *)(a1 + 392);
    if ( (v6 & 1) != 0 && *v8 == 64 )
      v8 = (_WORD *)(a1 + 394);
    v9 = (_WORD *)(a2 + 392);
    if ( (v7 & 1) != 0 && *v9 == 64 )
      v9 = (_WORD *)(a2 + 394);
    if ( (v7 & v6 & 2) == 0
      || (v10 = *(_QWORD *)(a1 + 384)) == 0
      || (v11 = *(_QWORD *)(a2 + 384)) == 0
      || (v12 = memcmp_0((const void *)(v10 + 916), (const void *)(v11 + 916), 0x48u), (v2 = v12) == 0) )
    {
      LODWORD(v2) = _o__wcsicmp(v8, v9, v2);
      if ( !(_DWORD)v2 && v3 )
        LODWORD(v2) = v4 - v5;
    }
  }
  return (unsigned int)-(int)v2;
}

```

## disassembly

```asm
0x14005e350  push    rbx
0x14005e352  push    rsi
0x14005e353  push    rdi
0x14005e354  push    r14
0x14005e356  push    r15
0x14005e358  sub     rsp, 30h
0x14005e35c  mov     r8d, 1
0x14005e362  xor     r15b, r15b
0x14005e365  movzx   edi, word ptr [rcx+422h]
0x14005e36c  movzx   esi, word ptr [rdx+422h]
0x14005e373  mov     al, sil
0x14005e376  and     al, dil
0x14005e379  test    al, 0Ch
0x14005e37b  jz      loc_14005E45F
0x14005e381  mov     al, [rcx+455h]
0x14005e387  test    al, 4
0x14005e389  jnz     short loc_14005E3EC
0x14005e38b  mov     r9b, [rdx+455h]
0x14005e392  test    r9b, 4
0x14005e396  jnz     short loc_14005E3EC
0x14005e398  lea     r14, [rcx+188h]
0x14005e39f  test    r8b, al
0x14005e3a2  jnz     short loc_14005E400
0x14005e3a4  lea     rbx, [rdx+188h]
0x14005e3ab  test    r8b, r9b
0x14005e3ae  jnz     short loc_14005E410
0x14005e3b0  and     al, r9b
0x14005e3b3  test    al, 2
0x14005e3b5  jnz     short loc_14005E41F
0x14005e3b7  mov     rdx, rbx
0x14005e3ba  mov     rcx, r14
0x14005e3bd  call    cs:__imp__o__wcsicmp
0x14005e3c3  mov     r8d, eax
0x14005e3c6  mov     [rsp+58h+var_38], eax
0x14005e3ca  test    eax, eax
0x14005e3cc  jnz     loc_14005E45F
0x14005e3d2  test    r15b, r15b
0x14005e3d5  jz      loc_14005E45F
0x14005e3db  movzx   eax, si
0x14005e3de  movzx   r8d, di
0x14005e3e2  sub     r8d, eax
0x14005e3e5  mov     [rsp+58h+var_38], r8d
0x14005e3ea  jmp     short loc_14005E45F
0x14005e3ec  mov     r15b, r8b
0x14005e3ef  and     di, 3
0x14005e3f3  and     si, 3
0x14005e3f7  mov     r9b, [rdx+455h]
0x14005e3fe  jmp     short loc_14005E398
0x14005e400  cmp     word ptr [r14], 40h ; '@'
0x14005e405  jnz     short loc_14005E3A4
0x14005e407  lea     r14, [rcx+18Ah]
0x14005e40e  jmp     short loc_14005E3A4
0x14005e410  cmp     word ptr [rbx], 40h ; '@'
0x14005e414  jnz     short loc_14005E3B0
0x14005e416  lea     rbx, [rdx+18Ah]
0x14005e41d  jmp     short loc_14005E3B0
0x14005e41f  mov     rcx, [rcx+180h]
0x14005e426  test    rcx, rcx
0x14005e429  jz      short loc_14005E3B7
0x14005e42b  mov     rdx, [rdx+180h]
0x14005e432  test    rdx, rdx
0x14005e435  jz      short loc_14005E3B7
0x14005e437  add     rdx, 394h; Buf2
0x14005e43e  add     rcx, 394h; Buf1
0x14005e445  mov     r8d, 48h ; 'H'; Size
0x14005e44b  call    memcmp_0
0x14005e450  mov     r8d, eax
0x14005e453  mov     [rsp+58h+var_38], eax
0x14005e457  test    eax, eax
0x14005e459  jz      loc_14005E3B7
0x14005e45f  neg     r8d
0x14005e462  mov     eax, r8d
0x14005e465  add     rsp, 30h
0x14005e469  pop     r15
0x14005e46b  pop     r14
0x14005e46d  pop     rdi
0x14005e46e  pop     rsi
0x14005e46f  pop     rbx
0x14005e470  retn
0x140097573  push    rbp
0x140097575  sub     rsp, 20h
0x140097579  mov     rbp, rdx
0x14009757c  add     rsp, 20h
0x140097580  pop     rbp
0x140097581  retn
```
