# tson::input_archive::search(void)

- ea: `0x180018360`
- end: `0x180018469`
- name: `?search@input_archive@tson@@AEAA_NXZ`
- size: `265`
- prototype: `char __fastcall(tson::input_archive *this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180006610`
- `0x180016ba4`
- `0x180016cc4`
- `0x180016dec`
- `0x180018ea8`

## callees

- `0x18000391c`
- `0x180018360`

## pseudocode

```c
char __fastcall tson::input_archive::search(tson::input_archive *this)
{
  const char *v1; // r10
  char *v2; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned __int8 *v6; // rax
  unsigned __int8 v7; // r8
  int v8; // r8d
  _BYTE *v9; // r9
  _BYTE *v10; // r8
  int *v11; // rbx
  unsigned __int64 v13; // rax

  v1 = (const char *)*((_QWORD *)this + 2);
  v2 = (char *)this + 32;
  *((_QWORD *)this + 2) = 0;
  *((_BYTE *)this + 25) = 0;
  v4 = *((_QWORD *)this + 17);
  if ( v4 )
    v2 = &v2[4 * v4 - 4];
  else
    *v2 = 1;
  if ( *((_DWORD *)v2 + 1) == 1 )
    return 1;
  v5 = *(_QWORD *)this;
  v6 = *(unsigned __int8 **)(*(_QWORD *)this + 8LL);
  if ( (unsigned __int64)v6 >= *(_QWORD *)(*(_QWORD *)this + 16LL) )
    v7 = 0;
  else
    v7 = *v6;
  v8 = v7 - 6;
  if ( v8 )
  {
    if ( (unsigned int)(v8 - 1) >= 2 )
    {
      if ( !v1 )
      {
        v1 = "-";
        *((_BYTE *)this + 24) = 1;
      }
      v9 = *(_BYTE **)(v5 + 8);
      v10 = &v9[*((unsigned __int8 *)this + 24) + 2];
      if ( (unsigned __int64)v10 > *(_QWORD *)(v5 + 16) )
      {
        *(_BYTE *)(v5 + 24) = 1;
      }
      else
      {
        *(_QWORD *)(v5 + 8) = v10;
        if ( v9 )
        {
          v11 = (int *)((char *)this + 8);
          if ( *v9 != 5 && *v11 >= 0 )
            *v11 = -2147023267;
          if ( (v9[1] != *((_BYTE *)this + 24) || memcmp_0(v1, v9 + 2, *((unsigned __int8 *)this + 24))) && *v11 >= 0 )
            *v11 = -2147023092;
        }
      }
      return 1;
    }
    *((_BYTE *)this + 25) = 1;
  }
  v13 = *(_QWORD *)(v5 + 8);
  if ( v13 >= *(_QWORD *)(v5 + 16) )
    *(_BYTE *)(v5 + 24) = 1;
  else
    *(_QWORD *)(v5 + 8) = v13 + 1;
  return 0;
}

```

## disassembly

```asm
0x180018360  push    rbx
0x180018362  sub     rsp, 20h
0x180018366  mov     r10, [rcx+10h]
0x18001836a  lea     rax, [rcx+20h]
0x18001836e  mov     qword ptr [rcx+10h], 0
0x180018376  mov     rdx, rcx
0x180018379  mov     byte ptr [rcx+19h], 0
0x18001837d  mov     rcx, [rax+68h]
0x180018381  test    rcx, rcx
0x180018384  jz      short loc_180018390
0x180018386  lea     rax, [rax+rcx*4]
0x18001838a  add     rax, 0FFFFFFFFFFFFFFFCh
0x18001838e  jmp     short loc_180018393
0x180018390  mov     byte ptr [rax], 1
0x180018393  cmp     dword ptr [rax+4], 1
0x180018397  jz      loc_18001843C
0x18001839d  mov     rcx, [rdx]
0x1800183a0  mov     rax, [rcx+8]
0x1800183a4  cmp     rax, [rcx+10h]
0x1800183a8  jnb     short loc_1800183AF
0x1800183aa  mov     r8b, [rax]
0x1800183ad  jmp     short loc_1800183B2
0x1800183af  xor     r8b, r8b
0x1800183b2  movzx   r8d, r8b
0x1800183b6  sub     r8d, 6
0x1800183ba  jz      loc_18001844E
0x1800183c0  sub     r8d, 1
0x1800183c4  jz      loc_18001844A
0x1800183ca  cmp     r8d, 1
0x1800183ce  jz      short loc_18001844A
0x1800183d0  test    r10, r10
0x1800183d3  jnz     short loc_1800183E0
0x1800183d5  lea     r10, asc_18002563C; "-"
0x1800183dc  mov     byte ptr [rdx+18h], 1
0x1800183e0  movzx   r8d, byte ptr [rdx+18h]
0x1800183e5  mov     r9, [rcx+8]
0x1800183e9  add     r8, 2
0x1800183ed  add     r8, r9
0x1800183f0  cmp     r8, [rcx+10h]
0x1800183f4  ja      short loc_180018444
0x1800183f6  mov     [rcx+8], r8
0x1800183fa  test    r9, r9
0x1800183fd  jz      short loc_18001843C
0x1800183ff  cmp     byte ptr [r9], 5
0x180018403  lea     rbx, [rdx+8]
0x180018407  jz      short loc_180018414
0x180018409  cmp     dword ptr [rbx], 0
0x18001840c  jl      short loc_180018414
0x18001840e  mov     dword ptr [rbx], 8007065Dh
0x180018414  movzx   eax, byte ptr [rdx+18h]
0x180018418  cmp     [r9+1], al
0x18001841c  jnz     short loc_180018431
0x18001841e  mov     r8d, eax; Size
0x180018421  lea     rdx, [r9+2]; Buf2
0x180018425  mov     rcx, r10; Buf1
0x180018428  call    memcmp_0
0x18001842d  test    eax, eax
0x18001842f  jz      short loc_18001843C
0x180018431  cmp     dword ptr [rbx], 0
0x180018434  jl      short loc_18001843C
0x180018436  mov     dword ptr [rbx], 8007070Ch
0x18001843c  mov     al, 1
0x18001843e  add     rsp, 20h
0x180018442  pop     rbx
0x180018443  retn
0x180018444  mov     byte ptr [rcx+18h], 1
0x180018448  jmp     short loc_18001843C
0x18001844a  mov     byte ptr [rdx+19h], 1
0x18001844e  mov     rax, [rcx+8]
0x180018452  cmp     rax, [rcx+10h]
0x180018456  jnb     short loc_180018461
0x180018458  inc     rax
0x18001845b  mov     [rcx+8], rax
0x18001845f  jmp     short loc_180018465
0x180018461  mov     byte ptr [rcx+18h], 1
0x180018465  xor     al, al
0x180018467  jmp     short loc_18001843E
```
