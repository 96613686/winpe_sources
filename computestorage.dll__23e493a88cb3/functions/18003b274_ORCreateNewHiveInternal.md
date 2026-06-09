# ORCreateNewHiveInternal

- ea: `0x18003b274`
- end: `0x18003b526`
- name: `ORCreateNewHiveInternal`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003b1d8`

## callees

- `0x180002690`
- `0x180003166`
- `0x180003172`
- `0x1800032b8`
- `0x180003bb5`
- `0x180038a10`
- `0x18003b274`
- `0x18003c864`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18003b435`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18003b435`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003b338`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003b338`

## pseudocode

```c
__int64 __fastcall ORCreateNewHiveInternal(__int64 a1, char a2, _QWORD *a3)
{
  _DWORD *v5; // rax
  _DWORD *v6; // rsi
  unsigned int v7; // ebp
  int v8; // ebx
  _DWORD *v9; // r14
  DWORD dwHighDateTime; // eax
  unsigned __int16 v11; // ax
  int v12; // ebx
  __int16 v13; // ax
  __int16 v14; // cx
  __int16 v15; // ax
  unsigned int v16; // edx
  __int64 v17; // r12
  void *v18; // rax
  const void *v19; // r13
  DWORD SecurityDescriptorLength; // eax
  DWORD v21; // ebx
  int v22; // ecx
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  void *v26; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-68h] BYREF
  char Src[8]; // [rsp+28h] [rbp-60h] BYREF

  SystemTimeAsFileTime = 0;
  *a3 = 0;
  v5 = o__aligned_malloc_0(0x2000u, 0x10u);
  v6 = v5;
  if ( v5 )
  {
    memset_0(v5, 0, 0x2000u);
    *v6 = 1718052210;
    v8 = a2 & 1;
    v6[1] = 1;
    v6[2] = 1;
    v6[5] = 1;
    v6[6] = v8 + 5;
    v6[8] = 1;
    v6[11] = 1;
    if ( v8 )
      v6[36] = 2;
    memset_0(v6 + 1024, 0, 0x1000u);
    v6[1026] = 4096;
    v9 = v6 + 1032;
    v6[1024] = 1852400232;
    v6[9] = 32;
    v6[1033] = 27502;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v6[1034] = SystemTimeAsFileTime.dwLowDateTime;
    dwHighDateTime = SystemTimeAsFileTime.dwHighDateTime;
    *((_QWORD *)v6 + 519) = 0;
    v6[1035] = dwHighDateTime;
    v6[1040] = -1;
    v6[1041] = -1;
    v6[1051] = 0;
    *((_BYTE *)v6 + 4144) = 0;
    v6[1042] = 0;
    *(_QWORD *)(v6 + 1047) = 0;
    *((_WORD *)v6 + 2092) = 0;
    v6[1049] = 0;
    v7 = 8;
    v6[1037] = -1;
    v6[1043] = -1;
    v6[1044] = -1;
    v6[1045] = -1;
    v11 = ORCompressCopyName(Src, 8, v6, L"\b\n");
    v12 = v11;
    memcpy_0(v6 + 1052, Src, v11);
    v13 = *((_WORD *)v6 + 2067);
    v14 = v13 | 0x20;
    v15 = v13 & 0xFFDF;
    if ( (unsigned __int16)v12 >= 8u )
      v14 = v15;
    *((_WORD *)v6 + 2067) = v14;
    *((_WORD *)v6 + 2102) = v12;
    v16 = (v6[5] << 12) - 4096 + v6[6];
    v17 = (v16 < 2 ? -16 : -8) & (v12 + (v16 < 2 ? 95 : 87));
    *v9 = -((v16 < 2 ? -16 : -8) & (v12 + (v16 < 2 ? 95 : 87)));
    v6[1044] = v17 + v6[9];
    v18 = ORGetRelativeSecurityDescriptor();
    v19 = v18;
    if ( v18 )
    {
      SecurityDescriptorLength = GetSecurityDescriptorLength(v18);
      *(_WORD *)((char *)v9 + v17 + 4) = 27507;
      v21 = SecurityDescriptorLength;
      *(_DWORD *)((char *)v9 + v17 + 16) = 1;
      memcpy_0((char *)v9 + v17 + 24, v19, SecurityDescriptorLength);
      *(_DWORD *)((char *)v9 + v17 + 20) = v21;
      v22 = v17 + v6[9];
      *(_DWORD *)((char *)v9 + v17 + 12) = v22;
      *(_DWORD *)((char *)v9 + v17 + 8) = v22;
      v23 = ((unsigned int)((v6[5] << 12) - 4096 + v6[6]) < 2 ? -16 : -8)
          & (v21 + ((unsigned int)((v6[5] << 12) - 4096 + v6[6]) < 2 ? 39 : 31));
      *(_DWORD *)((char *)v9 + v17) = -(((unsigned int)((v6[5] << 12) - 4096 + v6[6]) < 2 ? -16 : -8)
                                      & (v21 + ((unsigned int)((v6[5] << 12) - 4096 + v6[6]) < 2 ? 39 : 31)));
      *(_DWORD *)((char *)v9 + v23 + v17) = 4064 - v23 - v17;
      v24 = 0;
      v25 = 0;
      v6[10] = 4096;
      do
        v24 ^= v6[v25++];
      while ( v25 != 127 );
      if ( v24 == -1 )
      {
        v24 = -2;
      }
      else if ( !v24 )
      {
        v24 = 1;
      }
      v6[127] = v24;
      v7 = 0;
      *a3 = v6;
      v26 = (void *)v19;
    }
    else
    {
      v26 = v6;
    }
    aligned_free(v26);
  }
  else
  {
    return 8;
  }
  return v7;
}

```

## disassembly

```asm
0x18003b274  push    rbx
0x18003b276  push    rbp
0x18003b277  push    rsi
0x18003b278  push    rdi
0x18003b279  push    r12
0x18003b27b  push    r13
0x18003b27d  push    r14
0x18003b27f  push    r15
0x18003b281  sub     rsp, 48h
0x18003b285  mov     rax, cs:__security_cookie
0x18003b28c  xor     rax, rsp
0x18003b28f  mov     [rsp+88h+var_58], rax
0x18003b294  xor     ebp, ebp
0x18003b296  mov     ebx, edx
0x18003b298  mov     edi, 2000h
0x18003b29d  mov     qword ptr [rsp+88h+SystemTimeAsFileTime.dwLowDateTime], rbp
0x18003b2a2  mov     ecx, edi; Size
0x18003b2a4  mov     [r8], rbp
0x18003b2a7  mov     r15, r8
0x18003b2aa  lea     edx, [rbp+10h]; Alignment
0x18003b2ad  call    _o__aligned_malloc_0
0x18003b2b2  mov     rsi, rax
0x18003b2b5  test    rax, rax
0x18003b2b8  jnz     short loc_18003B2C2
0x18003b2ba  lea     ebp, [rax+8]
0x18003b2bd  jmp     loc_18003B505
0x18003b2c2  mov     r8, rdi; Size
0x18003b2c5  xor     edx, edx; Val
0x18003b2c7  mov     rcx, rsi; void *
0x18003b2ca  call    memset_0
0x18003b2cf  mov     ecx, 1
0x18003b2d4  mov     dword ptr [rsi], 66676572h
0x18003b2da  and     ebx, ecx
0x18003b2dc  mov     [rsi+4], ecx
0x18003b2df  mov     [rsi+8], ecx
0x18003b2e2  mov     [rsi+14h], ecx
0x18003b2e5  lea     eax, [rbx+5]
0x18003b2e8  mov     [rsi+18h], eax
0x18003b2eb  mov     [rsi+20h], ecx
0x18003b2ee  mov     [rsi+2Ch], ecx
0x18003b2f1  jz      short loc_18003B2FD
0x18003b2f3  mov     dword ptr [rsi+90h], 2
0x18003b2fd  lea     rbx, [rsi+1000h]
0x18003b304  mov     edi, 1000h
0x18003b309  mov     r8d, edi; Size
0x18003b30c  mov     rcx, rbx; void *
0x18003b30f  xor     edx, edx; Val
0x18003b311  call    memset_0
0x18003b316  mov     [rbx+8], edi
0x18003b319  lea     r14, [rbx+20h]
0x18003b31d  mov     dword ptr [rbx], 6E696268h
0x18003b323  lea     rcx, [rsp+88h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003b328  mov     edi, 20h ; ' '
0x18003b32d  mov     [rsi+24h], edi
0x18003b330  mov     dword ptr [r14+4], 6B6Eh
0x18003b338  call    cs:__imp_GetSystemTimeAsFileTime
0x18003b33f  nop     dword ptr [rax+rax+00h]
0x18003b344  mov     eax, [rsp+88h+SystemTimeAsFileTime.dwLowDateTime]
0x18003b348  lea     r9, asc_18004AE70; "\b\n"
0x18003b34f  mov     [r14+8], eax
0x18003b353  lea     rcx, [rsp+88h+Src]
0x18003b358  mov     eax, [rsp+88h+SystemTimeAsFileTime.dwHighDateTime]
0x18003b35c  mov     r8, rsi
0x18003b35f  mov     [r14+18h], rbp
0x18003b363  mov     [r14+0Ch], eax
0x18003b367  or      eax, 0FFFFFFFFh
0x18003b36a  mov     [r14+20h], eax
0x18003b36e  mov     [r14+24h], eax
0x18003b372  mov     [r14+4Ch], ebp
0x18003b376  mov     [r14+10h], bpl
0x18003b37a  mov     [r14+28h], ebp
0x18003b37e  mov     [r14+3Ch], rbp
0x18003b382  mov     [r14+38h], bp
0x18003b387  mov     [r14+44h], ebp
0x18003b38b  lea     ebp, [rdi-18h]
0x18003b38e  mov     edx, ebp
0x18003b390  mov     [r14+14h], eax
0x18003b394  mov     [r14+2Ch], eax
0x18003b398  mov     [r14+30h], eax
0x18003b39c  mov     [r14+34h], eax
0x18003b3a0  call    ORCompressCopyName
0x18003b3a5  movzx   ebx, ax
0x18003b3a8  lea     rcx, [r14+50h]; void *
0x18003b3ac  mov     r8d, ebx; Size
0x18003b3af  lea     rdx, [rsp+88h+Src]; Src
0x18003b3b4  call    memcpy_0
0x18003b3b9  movzx   ecx, word ptr [r14+6]
0x18003b3be  mov     edx, 0FFDFh
0x18003b3c3  movzx   eax, cx
0x18003b3c6  or      cx, di
0x18003b3c9  and     ax, dx
0x18003b3cc  cmp     bx, bp
0x18003b3cf  cmovnb  cx, ax
0x18003b3d3  mov     [r14+6], cx
0x18003b3d8  mov     [r14+4Ch], bx
0x18003b3dd  mov     ecx, [rsi+14h]
0x18003b3e0  mov     edx, [rsi+18h]
0x18003b3e3  shl     ecx, 0Ch
0x18003b3e6  add     ecx, 0FFFFF000h
0x18003b3ec  add     edx, ecx
0x18003b3ee  mov     ecx, 0FFFFFFF8h
0x18003b3f3  cmp     edx, 2
0x18003b3f6  sbb     r12d, r12d
0x18003b3f9  and     r12d, ebp
0x18003b3fc  add     r12d, 57h ; 'W'
0x18003b400  add     r12d, ebx
0x18003b403  cmp     edx, 2
0x18003b406  sbb     eax, eax
0x18003b408  and     eax, ecx
0x18003b40a  add     eax, ecx
0x18003b40c  and     r12d, eax
0x18003b40f  mov     eax, r12d
0x18003b412  neg     eax
0x18003b414  mov     [r14], eax
0x18003b417  mov     ecx, [rsi+24h]
0x18003b41a  add     ecx, r12d
0x18003b41d  mov     [r14+30h], ecx
0x18003b421  call    ORGetRelativeSecurityDescriptor
0x18003b426  mov     r13, rax
0x18003b429  test    rax, rax
0x18003b42c  jz      loc_18003B4FD
0x18003b432  mov     rcx, rax; pSecurityDescriptor
0x18003b435  call    cs:__imp_GetSecurityDescriptorLength
0x18003b43c  nop     dword ptr [rax+rax+00h]
0x18003b441  lea     rcx, [r12+18h]
0x18003b446  mov     word ptr [r14+r12+4], 6B73h
0x18003b44e  add     rcx, r14; void *
0x18003b451  mov     r8d, eax; Size
0x18003b454  mov     rdx, r13; Src
0x18003b457  mov     ebx, eax
0x18003b459  mov     dword ptr [r14+r12+10h], 1
0x18003b462  call    memcpy_0
0x18003b467  mov     [r14+r12+14h], ebx
0x18003b46c  mov     ecx, [rsi+24h]
0x18003b46f  add     ecx, r12d
0x18003b472  mov     [r14+r12+0Ch], ecx
0x18003b477  mov     [r14+r12+8], ecx
0x18003b47c  mov     ecx, [rsi+14h]
0x18003b47f  mov     edx, [rsi+18h]
0x18003b482  shl     ecx, 0Ch
0x18003b485  add     ecx, 0FFFFF000h
0x18003b48b  add     edx, ecx
0x18003b48d  cmp     edx, 2
0x18003b490  sbb     ecx, ecx
0x18003b492  and     ecx, ebp
0x18003b494  add     ecx, 1Fh
0x18003b497  add     ecx, ebx
0x18003b499  cmp     edx, 2
0x18003b49c  mov     edx, 0FFFFFFF8h
0x18003b4a1  sbb     eax, eax
0x18003b4a3  and     eax, edx
0x18003b4a5  add     eax, edx
0x18003b4a7  lea     edx, [rdi-1Fh]
0x18003b4aa  and     ecx, eax
0x18003b4ac  mov     eax, ecx
0x18003b4ae  neg     eax
0x18003b4b0  mov     [r14+r12], eax
0x18003b4b4  mov     eax, 0FE0h
0x18003b4b9  sub     eax, ecx
0x18003b4bb  add     rcx, r14
0x18003b4be  sub     eax, r12d
0x18003b4c1  mov     [rcx+r12], eax
0x18003b4c5  xor     eax, eax
0x18003b4c7  xor     ecx, ecx
0x18003b4c9  mov     dword ptr [rsi+28h], 1000h
0x18003b4d0  xor     eax, [rsi+rcx*4]
0x18003b4d3  add     rcx, rdx
0x18003b4d6  cmp     rcx, 7Fh
0x18003b4da  jnz     short loc_18003B4D0
0x18003b4dc  cmp     eax, 0FFFFFFFFh
0x18003b4df  jnz     short loc_18003B4E8
0x18003b4e1  mov     eax, 0FFFFFFFEh
0x18003b4e6  jmp     short loc_18003B4ED
0x18003b4e8  test    eax, eax
0x18003b4ea  cmovz   eax, edx
0x18003b4ed  mov     [rsi+1FCh], eax
0x18003b4f3  xor     ebp, ebp
0x18003b4f5  mov     [r15], rsi
0x18003b4f8  mov     rcx, r13
0x18003b4fb  jmp     short loc_18003B500
0x18003b4fd  mov     rcx, rsi; Block
0x18003b500  call    _aligned_free
0x18003b505  mov     eax, ebp
0x18003b507  mov     rcx, [rsp+88h+var_58]
0x18003b50c  xor     rcx, rsp; StackCookie
0x18003b50f  call    __security_check_cookie
0x18003b514  add     rsp, 48h
0x18003b518  pop     r15
0x18003b51a  pop     r14
0x18003b51c  pop     r13
0x18003b51e  pop     r12
0x18003b520  pop     rdi
0x18003b521  pop     rsi
0x18003b522  pop     rbp
0x18003b523  pop     rbx
0x18003b524  retn
```
