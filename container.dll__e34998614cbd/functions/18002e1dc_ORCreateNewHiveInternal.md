# ORCreateNewHiveInternal

- ea: `0x18002e1dc`
- end: `0x18002e48e`
- name: `ORCreateNewHiveInternal`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e14c`

## callees

- `0x180002ad0`
- `0x180003542`
- `0x18000354e`
- `0x180003614`
- `0x18000362c`
- `0x18002e1dc`
- `0x18002f708`
- `0x18002ff60`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18002e39d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18002e39d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002e2a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002e2a0`

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
0x18002e1dc  push    rbx
0x18002e1de  push    rbp
0x18002e1df  push    rsi
0x18002e1e0  push    rdi
0x18002e1e1  push    r12
0x18002e1e3  push    r13
0x18002e1e5  push    r14
0x18002e1e7  push    r15
0x18002e1e9  sub     rsp, 48h
0x18002e1ed  mov     rax, cs:__security_cookie
0x18002e1f4  xor     rax, rsp
0x18002e1f7  mov     [rsp+88h+var_58], rax
0x18002e1fc  xor     ebp, ebp
0x18002e1fe  mov     ebx, edx
0x18002e200  mov     edi, 2000h
0x18002e205  mov     qword ptr [rsp+88h+SystemTimeAsFileTime.dwLowDateTime], rbp
0x18002e20a  mov     ecx, edi; Size
0x18002e20c  mov     [r8], rbp
0x18002e20f  mov     r15, r8
0x18002e212  lea     edx, [rbp+10h]; Alignment
0x18002e215  call    _o__aligned_malloc_0
0x18002e21a  mov     rsi, rax
0x18002e21d  test    rax, rax
0x18002e220  jnz     short loc_18002E22A
0x18002e222  lea     ebp, [rax+8]
0x18002e225  jmp     loc_18002E46D
0x18002e22a  mov     r8, rdi; Size
0x18002e22d  xor     edx, edx; Val
0x18002e22f  mov     rcx, rsi; void *
0x18002e232  call    memset_0
0x18002e237  mov     ecx, 1
0x18002e23c  mov     dword ptr [rsi], 66676572h
0x18002e242  and     ebx, ecx
0x18002e244  mov     [rsi+4], ecx
0x18002e247  mov     [rsi+8], ecx
0x18002e24a  mov     [rsi+14h], ecx
0x18002e24d  lea     eax, [rbx+5]
0x18002e250  mov     [rsi+18h], eax
0x18002e253  mov     [rsi+20h], ecx
0x18002e256  mov     [rsi+2Ch], ecx
0x18002e259  jz      short loc_18002E265
0x18002e25b  mov     dword ptr [rsi+90h], 2
0x18002e265  lea     rbx, [rsi+1000h]
0x18002e26c  mov     edi, 1000h
0x18002e271  mov     r8d, edi; Size
0x18002e274  mov     rcx, rbx; void *
0x18002e277  xor     edx, edx; Val
0x18002e279  call    memset_0
0x18002e27e  mov     [rbx+8], edi
0x18002e281  lea     r14, [rbx+20h]
0x18002e285  mov     dword ptr [rbx], 6E696268h
0x18002e28b  lea     rcx, [rsp+88h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002e290  mov     edi, 20h ; ' '
0x18002e295  mov     [rsi+24h], edi
0x18002e298  mov     dword ptr [r14+4], 6B6Eh
0x18002e2a0  call    cs:__imp_GetSystemTimeAsFileTime
0x18002e2a7  nop     dword ptr [rax+rax+00h]
0x18002e2ac  mov     eax, [rsp+88h+SystemTimeAsFileTime.dwLowDateTime]
0x18002e2b0  lea     r9, asc_180036CE8; "\b\n"
0x18002e2b7  mov     [r14+8], eax
0x18002e2bb  lea     rcx, [rsp+88h+Src]
0x18002e2c0  mov     eax, [rsp+88h+SystemTimeAsFileTime.dwHighDateTime]
0x18002e2c4  mov     r8, rsi
0x18002e2c7  mov     [r14+18h], rbp
0x18002e2cb  mov     [r14+0Ch], eax
0x18002e2cf  or      eax, 0FFFFFFFFh
0x18002e2d2  mov     [r14+20h], eax
0x18002e2d6  mov     [r14+24h], eax
0x18002e2da  mov     [r14+4Ch], ebp
0x18002e2de  mov     [r14+10h], bpl
0x18002e2e2  mov     [r14+28h], ebp
0x18002e2e6  mov     [r14+3Ch], rbp
0x18002e2ea  mov     [r14+38h], bp
0x18002e2ef  mov     [r14+44h], ebp
0x18002e2f3  lea     ebp, [rdi-18h]
0x18002e2f6  mov     edx, ebp
0x18002e2f8  mov     [r14+14h], eax
0x18002e2fc  mov     [r14+2Ch], eax
0x18002e300  mov     [r14+30h], eax
0x18002e304  mov     [r14+34h], eax
0x18002e308  call    ORCompressCopyName
0x18002e30d  movzx   ebx, ax
0x18002e310  lea     rcx, [r14+50h]; void *
0x18002e314  mov     r8d, ebx; Size
0x18002e317  lea     rdx, [rsp+88h+Src]; Src
0x18002e31c  call    memcpy_0
0x18002e321  movzx   ecx, word ptr [r14+6]
0x18002e326  mov     edx, 0FFDFh
0x18002e32b  movzx   eax, cx
0x18002e32e  or      cx, di
0x18002e331  and     ax, dx
0x18002e334  cmp     bx, bp
0x18002e337  cmovnb  cx, ax
0x18002e33b  mov     [r14+6], cx
0x18002e340  mov     [r14+4Ch], bx
0x18002e345  mov     ecx, [rsi+14h]
0x18002e348  mov     edx, [rsi+18h]
0x18002e34b  shl     ecx, 0Ch
0x18002e34e  add     ecx, 0FFFFF000h
0x18002e354  add     edx, ecx
0x18002e356  mov     ecx, 0FFFFFFF8h
0x18002e35b  cmp     edx, 2
0x18002e35e  sbb     r12d, r12d
0x18002e361  and     r12d, ebp
0x18002e364  add     r12d, 57h ; 'W'
0x18002e368  add     r12d, ebx
0x18002e36b  cmp     edx, 2
0x18002e36e  sbb     eax, eax
0x18002e370  and     eax, ecx
0x18002e372  add     eax, ecx
0x18002e374  and     r12d, eax
0x18002e377  mov     eax, r12d
0x18002e37a  neg     eax
0x18002e37c  mov     [r14], eax
0x18002e37f  mov     ecx, [rsi+24h]
0x18002e382  add     ecx, r12d
0x18002e385  mov     [r14+30h], ecx
0x18002e389  call    ORGetRelativeSecurityDescriptor
0x18002e38e  mov     r13, rax
0x18002e391  test    rax, rax
0x18002e394  jz      loc_18002E465
0x18002e39a  mov     rcx, rax; pSecurityDescriptor
0x18002e39d  call    cs:__imp_GetSecurityDescriptorLength
0x18002e3a4  nop     dword ptr [rax+rax+00h]
0x18002e3a9  lea     rcx, [r12+18h]
0x18002e3ae  mov     word ptr [r14+r12+4], 6B73h
0x18002e3b6  add     rcx, r14; void *
0x18002e3b9  mov     r8d, eax; Size
0x18002e3bc  mov     rdx, r13; Src
0x18002e3bf  mov     ebx, eax
0x18002e3c1  mov     dword ptr [r14+r12+10h], 1
0x18002e3ca  call    memcpy_0
0x18002e3cf  mov     [r14+r12+14h], ebx
0x18002e3d4  mov     ecx, [rsi+24h]
0x18002e3d7  add     ecx, r12d
0x18002e3da  mov     [r14+r12+0Ch], ecx
0x18002e3df  mov     [r14+r12+8], ecx
0x18002e3e4  mov     ecx, [rsi+14h]
0x18002e3e7  mov     edx, [rsi+18h]
0x18002e3ea  shl     ecx, 0Ch
0x18002e3ed  add     ecx, 0FFFFF000h
0x18002e3f3  add     edx, ecx
0x18002e3f5  cmp     edx, 2
0x18002e3f8  sbb     ecx, ecx
0x18002e3fa  and     ecx, ebp
0x18002e3fc  add     ecx, 1Fh
0x18002e3ff  add     ecx, ebx
0x18002e401  cmp     edx, 2
0x18002e404  mov     edx, 0FFFFFFF8h
0x18002e409  sbb     eax, eax
0x18002e40b  and     eax, edx
0x18002e40d  add     eax, edx
0x18002e40f  lea     edx, [rdi-1Fh]
0x18002e412  and     ecx, eax
0x18002e414  mov     eax, ecx
0x18002e416  neg     eax
0x18002e418  mov     [r14+r12], eax
0x18002e41c  mov     eax, 0FE0h
0x18002e421  sub     eax, ecx
0x18002e423  add     rcx, r14
0x18002e426  sub     eax, r12d
0x18002e429  mov     [rcx+r12], eax
0x18002e42d  xor     eax, eax
0x18002e42f  xor     ecx, ecx
0x18002e431  mov     dword ptr [rsi+28h], 1000h
0x18002e438  xor     eax, [rsi+rcx*4]
0x18002e43b  add     rcx, rdx
0x18002e43e  cmp     rcx, 7Fh
0x18002e442  jnz     short loc_18002E438
0x18002e444  cmp     eax, 0FFFFFFFFh
0x18002e447  jnz     short loc_18002E450
0x18002e449  mov     eax, 0FFFFFFFEh
0x18002e44e  jmp     short loc_18002E455
0x18002e450  test    eax, eax
0x18002e452  cmovz   eax, edx
0x18002e455  mov     [rsi+1FCh], eax
0x18002e45b  xor     ebp, ebp
0x18002e45d  mov     [r15], rsi
0x18002e460  mov     rcx, r13
0x18002e463  jmp     short loc_18002E468
0x18002e465  mov     rcx, rsi; Block
0x18002e468  call    _aligned_free
0x18002e46d  mov     eax, ebp
0x18002e46f  mov     rcx, [rsp+88h+var_58]
0x18002e474  xor     rcx, rsp; StackCookie
0x18002e477  call    __security_check_cookie
0x18002e47c  add     rsp, 48h
0x18002e480  pop     r15
0x18002e482  pop     r14
0x18002e484  pop     r13
0x18002e486  pop     r12
0x18002e488  pop     rdi
0x18002e489  pop     rsi
0x18002e48a  pop     rbp
0x18002e48b  pop     rbx
0x18002e48c  retn
```
