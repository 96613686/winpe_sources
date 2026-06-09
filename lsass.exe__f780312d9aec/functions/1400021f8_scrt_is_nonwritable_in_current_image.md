# __scrt_is_nonwritable_in_current_image

- ea: `0x1400021f8`
- end: `0x140002290`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001f00`

## callees

- `0x1400021f8`

## pseudocode

```c
bool __fastcall _scrt_is_nonwritable_in_current_image(__int64 a1)
{
  _DWORD *v2; // rcx
  unsigned __int64 v3; // r8
  _DWORD *v4; // rdx
  _DWORD *v5; // r9
  unsigned __int64 v6; // rcx

  if ( _ImageBase != 23117 )
    return 0;
  v2 = (_DWORD *)((char *)&_ImageBase + (int)off_14000003C);
  if ( *v2 != 17744 || *(__int16 *)((char *)&word_140000018 + (int)off_14000003C) != 523 )
    return 0;
  v3 = a1 - (_QWORD)&_ImageBase;
  v4 = (_DWORD *)((char *)v2 + *(unsigned __int16 *)((char *)&word_140000014 + (int)off_14000003C) + 24);
  v5 = &v4[10 * *(unsigned __int16 *)((char *)&word_140000006 + (int)off_14000003C)];
  while ( v4 != v5 )
  {
    v6 = (unsigned int)v4[3];
    if ( v3 >= v6 && v3 < (unsigned int)(v6 + v4[2]) )
      return v4 && v4[9] >= 0;
    v4 += 10;
  }
  v4 = 0;
  return v4 && v4[9] >= 0;
}

```

## disassembly

```asm
0x1400021f8  sub     rsp, 18h
0x1400021fc  mov     r8, rcx
0x1400021ff  mov     eax, 5A4Dh
0x140002204  cmp     cs:__ImageBase, ax
0x14000220b  jnz     short loc_140002285
0x14000220d  movsxd  rcx, cs:off_14000003C
0x140002214  lea     rdx, __ImageBase
0x14000221b  add     rcx, rdx
0x14000221e  cmp     dword ptr [rcx], 4550h
0x140002224  jnz     short loc_140002285
0x140002226  mov     eax, 20Bh
0x14000222b  cmp     [rcx+18h], ax
0x14000222f  jnz     short loc_140002285
0x140002231  sub     r8, rdx
0x140002234  movzx   edx, word ptr [rcx+14h]
0x140002238  add     rdx, 18h
0x14000223c  add     rdx, rcx
0x14000223f  movzx   eax, word ptr [rcx+6]
0x140002243  lea     rcx, [rax+rax*4]
0x140002247  lea     r9, [rdx+rcx*8]
0x14000224b  mov     [rsp+18h+var_18], rdx
0x14000224f  cmp     rdx, r9
0x140002252  jz      short loc_14000226C
0x140002254  mov     ecx, [rdx+0Ch]
0x140002257  cmp     r8, rcx
0x14000225a  jb      short loc_140002266
0x14000225c  mov     eax, [rdx+8]
0x14000225f  add     eax, ecx
0x140002261  cmp     r8, rax
0x140002264  jb      short loc_14000226E
0x140002266  add     rdx, 28h ; '('
0x14000226a  jmp     short loc_14000224B
0x14000226c  xor     edx, edx
0x14000226e  test    rdx, rdx
0x140002271  jnz     short loc_140002277
0x140002273  xor     al, al
0x140002275  jmp     short loc_14000228B
0x140002277  cmp     dword ptr [rdx+24h], 0
0x14000227b  jge     short loc_140002281
0x14000227d  xor     al, al
0x14000227f  jmp     short loc_14000228B
0x140002281  mov     al, 1
0x140002283  jmp     short loc_14000228B
0x140002285  xor     al, al
0x140002287  jmp     short loc_14000228B
0x140002289  xor     al, al
0x14000228b  add     rsp, 18h
0x14000228f  retn
0x140005330  push    rbp
0x140005332  mov     rbp, rdx
0x140005335  mov     rax, [rcx]
0x140005338  xor     ecx, ecx
0x14000533a  cmp     dword ptr [rax], 0C0000005h
0x140005340  setz    cl
0x140005343  mov     eax, ecx
0x140005345  pop     rbp
0x140005346  retn
```
