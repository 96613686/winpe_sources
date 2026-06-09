# ORCreateNewHiveInternal

- ea: `0x14002307c`
- end: `0x14002332e`
- name: `ORCreateNewHiveInternal`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140022fe0`

## callees

- `0x1400020b0`
- `0x1400029c6`
- `0x1400029d2`
- `0x140002b2c`
- `0x14002307c`
- `0x140026bbc`
- `0x14002909c`
- `0x14002e8cc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140023140`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140023140`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x14002323d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x14002323d`

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
0x14002307c  push    rbx
0x14002307e  push    rbp
0x14002307f  push    rsi
0x140023080  push    rdi
0x140023081  push    r12
0x140023083  push    r13
0x140023085  push    r14
0x140023087  push    r15
0x140023089  sub     rsp, 48h
0x14002308d  mov     rax, cs:__security_cookie
0x140023094  xor     rax, rsp
0x140023097  mov     [rsp+88h+var_58], rax
0x14002309c  xor     ebp, ebp
0x14002309e  mov     ebx, edx
0x1400230a0  mov     edi, 2000h
0x1400230a5  mov     qword ptr [rsp+88h+SystemTimeAsFileTime.dwLowDateTime], rbp
0x1400230aa  mov     ecx, edi; Size
0x1400230ac  mov     [r8], rbp
0x1400230af  mov     r15, r8
0x1400230b2  lea     edx, [rbp+10h]; Alignment
0x1400230b5  call    _o__aligned_malloc_0
0x1400230ba  mov     rsi, rax
0x1400230bd  test    rax, rax
0x1400230c0  jnz     short loc_1400230CA
0x1400230c2  lea     ebp, [rax+8]
0x1400230c5  jmp     loc_14002330D
0x1400230ca  mov     r8, rdi; Size
0x1400230cd  xor     edx, edx; Val
0x1400230cf  mov     rcx, rsi; void *
0x1400230d2  call    memset_0
0x1400230d7  mov     ecx, 1
0x1400230dc  mov     dword ptr [rsi], 66676572h
0x1400230e2  and     ebx, ecx
0x1400230e4  mov     [rsi+4], ecx
0x1400230e7  mov     [rsi+8], ecx
0x1400230ea  mov     [rsi+14h], ecx
0x1400230ed  lea     eax, [rbx+5]
0x1400230f0  mov     [rsi+18h], eax
0x1400230f3  mov     [rsi+20h], ecx
0x1400230f6  mov     [rsi+2Ch], ecx
0x1400230f9  jz      short loc_140023105
0x1400230fb  mov     dword ptr [rsi+90h], 2
0x140023105  lea     rbx, [rsi+1000h]
0x14002310c  mov     edi, 1000h
0x140023111  mov     r8d, edi; Size
0x140023114  mov     rcx, rbx; void *
0x140023117  xor     edx, edx; Val
0x140023119  call    memset_0
0x14002311e  mov     [rbx+8], edi
0x140023121  lea     r14, [rbx+20h]
0x140023125  mov     dword ptr [rbx], 6E696268h
0x14002312b  lea     rcx, [rsp+88h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140023130  mov     edi, 20h ; ' '
0x140023135  mov     [rsi+24h], edi
0x140023138  mov     dword ptr [r14+4], 6B6Eh
0x140023140  call    cs:__imp_GetSystemTimeAsFileTime
0x140023147  nop     dword ptr [rax+rax+00h]
0x14002314c  mov     eax, [rsp+88h+SystemTimeAsFileTime.dwLowDateTime]
0x140023150  lea     r9, asc_1400358B8; "\b\n"
0x140023157  mov     [r14+8], eax
0x14002315b  lea     rcx, [rsp+88h+Src]
0x140023160  mov     eax, [rsp+88h+SystemTimeAsFileTime.dwHighDateTime]
0x140023164  mov     r8, rsi
0x140023167  mov     [r14+18h], rbp
0x14002316b  mov     [r14+0Ch], eax
0x14002316f  or      eax, 0FFFFFFFFh
0x140023172  mov     [r14+20h], eax
0x140023176  mov     [r14+24h], eax
0x14002317a  mov     [r14+4Ch], ebp
0x14002317e  mov     [r14+10h], bpl
0x140023182  mov     [r14+28h], ebp
0x140023186  mov     [r14+3Ch], rbp
0x14002318a  mov     [r14+38h], bp
0x14002318f  mov     [r14+44h], ebp
0x140023193  lea     ebp, [rdi-18h]
0x140023196  mov     edx, ebp
0x140023198  mov     [r14+14h], eax
0x14002319c  mov     [r14+2Ch], eax
0x1400231a0  mov     [r14+30h], eax
0x1400231a4  mov     [r14+34h], eax
0x1400231a8  call    ORCompressCopyName
0x1400231ad  movzx   ebx, ax
0x1400231b0  lea     rcx, [r14+50h]; void *
0x1400231b4  mov     r8d, ebx; Size
0x1400231b7  lea     rdx, [rsp+88h+Src]; Src
0x1400231bc  call    memcpy_0
0x1400231c1  movzx   ecx, word ptr [r14+6]
0x1400231c6  mov     edx, 0FFDFh
0x1400231cb  movzx   eax, cx
0x1400231ce  or      cx, di
0x1400231d1  and     ax, dx
0x1400231d4  cmp     bx, bp
0x1400231d7  cmovnb  cx, ax
0x1400231db  mov     [r14+6], cx
0x1400231e0  mov     [r14+4Ch], bx
0x1400231e5  mov     ecx, [rsi+14h]
0x1400231e8  mov     edx, [rsi+18h]
0x1400231eb  shl     ecx, 0Ch
0x1400231ee  add     ecx, 0FFFFF000h
0x1400231f4  add     edx, ecx
0x1400231f6  mov     ecx, 0FFFFFFF8h
0x1400231fb  cmp     edx, 2
0x1400231fe  sbb     r12d, r12d
0x140023201  and     r12d, ebp
0x140023204  add     r12d, 57h ; 'W'
0x140023208  add     r12d, ebx
0x14002320b  cmp     edx, 2
0x14002320e  sbb     eax, eax
0x140023210  and     eax, ecx
0x140023212  add     eax, ecx
0x140023214  and     r12d, eax
0x140023217  mov     eax, r12d
0x14002321a  neg     eax
0x14002321c  mov     [r14], eax
0x14002321f  mov     ecx, [rsi+24h]
0x140023222  add     ecx, r12d
0x140023225  mov     [r14+30h], ecx
0x140023229  call    ORGetRelativeSecurityDescriptor
0x14002322e  mov     r13, rax
0x140023231  test    rax, rax
0x140023234  jz      loc_140023305
0x14002323a  mov     rcx, rax; pSecurityDescriptor
0x14002323d  call    cs:__imp_GetSecurityDescriptorLength
0x140023244  nop     dword ptr [rax+rax+00h]
0x140023249  lea     rcx, [r12+18h]
0x14002324e  mov     word ptr [r14+r12+4], 6B73h
0x140023256  add     rcx, r14; void *
0x140023259  mov     r8d, eax; Size
0x14002325c  mov     rdx, r13; Src
0x14002325f  mov     ebx, eax
0x140023261  mov     dword ptr [r14+r12+10h], 1
0x14002326a  call    memcpy_0
0x14002326f  mov     [r14+r12+14h], ebx
0x140023274  mov     ecx, [rsi+24h]
0x140023277  add     ecx, r12d
0x14002327a  mov     [r14+r12+0Ch], ecx
0x14002327f  mov     [r14+r12+8], ecx
0x140023284  mov     ecx, [rsi+14h]
0x140023287  mov     edx, [rsi+18h]
0x14002328a  shl     ecx, 0Ch
0x14002328d  add     ecx, 0FFFFF000h
0x140023293  add     edx, ecx
0x140023295  cmp     edx, 2
0x140023298  sbb     ecx, ecx
0x14002329a  and     ecx, ebp
0x14002329c  add     ecx, 1Fh
0x14002329f  add     ecx, ebx
0x1400232a1  cmp     edx, 2
0x1400232a4  mov     edx, 0FFFFFFF8h
0x1400232a9  sbb     eax, eax
0x1400232ab  and     eax, edx
0x1400232ad  add     eax, edx
0x1400232af  lea     edx, [rdi-1Fh]
0x1400232b2  and     ecx, eax
0x1400232b4  mov     eax, ecx
0x1400232b6  neg     eax
0x1400232b8  mov     [r14+r12], eax
0x1400232bc  mov     eax, 0FE0h
0x1400232c1  sub     eax, ecx
0x1400232c3  add     rcx, r14
0x1400232c6  sub     eax, r12d
0x1400232c9  mov     [rcx+r12], eax
0x1400232cd  xor     eax, eax
0x1400232cf  xor     ecx, ecx
0x1400232d1  mov     dword ptr [rsi+28h], 1000h
0x1400232d8  xor     eax, [rsi+rcx*4]
0x1400232db  add     rcx, rdx
0x1400232de  cmp     rcx, 7Fh
0x1400232e2  jnz     short loc_1400232D8
0x1400232e4  cmp     eax, 0FFFFFFFFh
0x1400232e7  jnz     short loc_1400232F0
0x1400232e9  mov     eax, 0FFFFFFFEh
0x1400232ee  jmp     short loc_1400232F5
0x1400232f0  test    eax, eax
0x1400232f2  cmovz   eax, edx
0x1400232f5  mov     [rsi+1FCh], eax
0x1400232fb  xor     ebp, ebp
0x1400232fd  mov     [r15], rsi
0x140023300  mov     rcx, r13
0x140023303  jmp     short loc_140023308
0x140023305  mov     rcx, rsi; Block
0x140023308  call    _aligned_free
0x14002330d  mov     eax, ebp
0x14002330f  mov     rcx, [rsp+88h+var_58]
0x140023314  xor     rcx, rsp; StackCookie
0x140023317  call    __security_check_cookie
0x14002331c  add     rsp, 48h
0x140023320  pop     r15
0x140023322  pop     r14
0x140023324  pop     r13
0x140023326  pop     r12
0x140023328  pop     rdi
0x140023329  pop     rsi
0x14002332a  pop     rbp
0x14002332b  pop     rbx
0x14002332c  retn
```
