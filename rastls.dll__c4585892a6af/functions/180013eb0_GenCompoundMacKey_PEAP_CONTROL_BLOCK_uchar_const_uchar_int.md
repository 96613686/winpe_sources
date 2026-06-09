# GenCompoundMacKey(_PEAP_CONTROL_BLOCK *,uchar * const,uchar *,int)

- ea: `0x180013eb0`
- end: `0x1800144ff`
- name: `?GenCompoundMacKey@@YAKPEAU_PEAP_CONTROL_BLOCK@@QEAEPEAEH@Z`
- size: `1615`
- prototype: `unsigned int __fastcall(struct _PEAP_CONTROL_BLOCK *, unsigned __int8 *const, unsigned __int8 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800602c4`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180013eb0`
- `0x180014510`
- `0x180014770`
- `0x180038270`
- `0x180038e4c`
- `0x180038e64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001417e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001417e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014165`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014220`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001428b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014165`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014220`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001428b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014334`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014355`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800143de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014418`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014334`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014355`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800143de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014418`
- `eapputil!EapConvertWireToHostFormat32` at `0x180013f6e`
- `eapputil!EapConvertWireToHostFormat32` at `0x180014042`
- `eapputil!EapConvertWireToHostFormat32` at `0x180013f6e`
- `eapputil!EapConvertWireToHostFormat32` at `0x180014042`

## string_xrefs

- `0x180013eda`: `Inner Methods Compound Keys`

## pseudocode

```c
__int64 __fastcall GenCompoundMacKey(struct _PEAP_CONTROL_BLOCK *a1, unsigned __int8 *const a2, unsigned __int8 *a3)
{
  __int64 v4; // rbx
  int v5; // r12d
  int v6; // r13d
  char v7; // di
  int *v8; // r15
  char v9; // si
  int v10; // eax
  char v11; // cl
  int *v12; // rdi
  const void *v13; // r15
  int v14; // eax
  char v15; // r14
  const void *v16; // r13
  unsigned int v17; // r12d
  unsigned int v18; // esi
  _BYTE *v19; // r15
  char v20; // dl
  struct _EAPTLS_CONTROL_BLOCK *v21; // rcx
  DWORD LastError; // ebx
  __int64 v23; // rdx
  unsigned int v24; // edi
  unsigned int v25; // ecx
  char *v26; // rax
  char *v27; // r12
  __int64 v28; // r9
  unsigned int v29; // r14d
  unsigned __int16 v30; // si
  __int128 v31; // xmm1
  HLOCAL v32; // r15
  unsigned __int16 v33; // r13
  unsigned __int16 v34; // bx
  ULONG v35; // r12d
  _BYTE *v36; // rax
  _BYTE *v37; // rdi
  unsigned __int64 v38; // rax
  __int64 v39; // r9
  int v40; // ebx
  unsigned __int8 *v41; // rdi
  __int128 v42; // xmm0
  int v43; // eax
  unsigned int v44; // eax
  char v46; // [rsp+30h] [rbp-D0h]
  char *hMem; // [rsp+38h] [rbp-C8h]
  HLOCAL hMema; // [rsp+38h] [rbp-C8h]
  HLOCAL hMemb; // [rsp+38h] [rbp-C8h]
  unsigned __int16 v51; // [rsp+48h] [rbp-B8h]
  char Src[32]; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v54[2]; // [rsp+78h] [rbp-88h] BYREF
  UCHAR pbSecret[16]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v56; // [rsp+A8h] [rbp-58h]
  _BYTE v57[28]; // [rsp+B8h] [rbp-48h]
  unsigned __int8 v58[40]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v59; // [rsp+100h] [rbp+0h]
  int v60; // [rsp+110h] [rbp+10h]

  strcpy(Src, "Inner Methods Compound Keys");
  v4 = -1;
  do
    ++v4;
  while ( Src[v4] );
  v5 = 0;
  v6 = 0;
  v7 = ((*((_DWORD *)a1 + 1) & 1) != 0) + 16;
  v8 = *(int **)(*((_QWORD *)a1 + 352) + 536LL);
  v9 = ((*((_DWORD *)a1 + 1) & 1) == 0) + 16;
  v10 = *v8;
  if ( !*v8 )
    goto LABEL_78;
  do
  {
    if ( v10 == 26 && v8[1] == 56 )
    {
      hMem = (char *)*((_QWORD *)v8 + 1);
      if ( (unsigned int)EapConvertWireToHostFormat32(hMem) == 311 )
      {
        v11 = hMem[4];
        if ( v7 == v11 )
        {
          v6 = 1;
          *(_OWORD *)pbSecret = *(_OWORD *)(hMem + 9);
          v56 = *(_OWORD *)(hMem + 25);
          if ( v5 == 1 )
            break;
        }
        else if ( v9 == v11 )
        {
          v5 = 1;
          *(_OWORD *)v57 = *(_OWORD *)(hMem + 9);
          *(_OWORD *)&v57[12] = *(_OWORD *)(hMem + 21);
          if ( v6 == 1 )
            goto LABEL_14;
        }
      }
    }
    v10 = v8[4];
    v8 += 4;
  }
  while ( v10 );
  if ( !v5 )
  {
LABEL_78:
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
    return 627;
  }
LABEL_14:
  if ( !v6 )
    goto LABEL_78;
  if ( !*((_DWORD *)a1 + 660) )
  {
    v12 = (int *)*((_QWORD *)a1 + 348);
    if ( v12 )
    {
      v13 = 0;
      v14 = *v12;
      v15 = *((_BYTE *)a1 + 4) & 1 | 0x10;
      hMema = 0;
      v16 = 0;
      v17 = 0;
      v18 = 0;
      if ( !*v12 )
        goto LABEL_34;
      while ( 1 )
      {
        if ( v14 == 26 )
        {
          v19 = (_BYTE *)*((_QWORD *)v12 + 1);
          if ( (unsigned int)EapConvertWireToHostFormat32(v19) == 311 )
          {
            v20 = v19[4];
            if ( (unsigned __int8)(v20 - 16) <= 1u )
            {
              if ( v20 != v15 )
              {
                v17 = (unsigned __int8)v19[8];
                hMema = v19 + 9;
                v13 = v19 + 9;
                goto LABEL_24;
              }
              v18 = (unsigned __int8)v19[8];
              v16 = v19 + 9;
            }
          }
          v13 = hMema;
        }
LABEL_24:
        v14 = v12[4];
        v12 += 4;
        if ( !v14 )
        {
          if ( v18 != v17 && (!v18 || !v17) )
          {
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
              v21 = WPP_GLOBAL_Control;
            }
            LastError = 13;
            if ( v21 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              return LastError;
            v23 = 88;
            goto LABEL_45;
          }
          v24 = 32;
          if ( v18 <= 0x20 )
LABEL_34:
            v24 = v18;
          memcpy_0(v54, v16, v24);
          if ( v24 != 32 )
          {
            v25 = v17;
            if ( 32 - v24 < v17 )
              v25 = 32 - v24;
            if ( v25 )
              memcpy_0((char *)v54 + v18, v13, v25);
          }
          if ( v18 + v17 < 0x20 )
            memset_0((char *)v54 + v17 + v18, 0, 32 - v18 - v17);
          v26 = (char *)LocalAlloc(0x40u, (unsigned __int16)v4 + 32LL);
          hMemb = v26;
          v27 = v26;
          if ( v26 )
          {
            memcpy_0(v26, Src, (unsigned __int16)v4);
            v29 = 0;
            v30 = 0;
            v31 = v54[1];
            v32 = 0;
            v33 = 0;
            *(_OWORD *)&v27[(unsigned __int16)v4] = v54[0];
            *(_OWORD *)&v27[(unsigned __int16)v4 + 16] = v31;
            v34 = v4 + 32;
            v51 = v34;
            v46 = 0;
            while ( 1 )
            {
              if ( v30 >= 0x3Cu )
                goto LABEL_65;
              v35 = v33 + 3 + v34;
              v36 = LocalAlloc(0x40u, v35);
              v37 = v36;
              if ( !v36 )
              {
                v29 = 14;
                v21 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
LABEL_65:
                  v21 = WPP_GLOBAL_Control;
                }
                if ( v33 && v32 )
                {
                  LocalFree(v32);
                  v21 = WPP_GLOBAL_Control;
                }
                goto LABEL_69;
              }
              ++v46;
              memcpy_0(v36, v32, v33);
              memcpy_0(&v37[v33], hMemb, v34);
              v38 = v34 + (unsigned __int64)v33;
              *(_WORD *)&v37[v38] = 60;
              v37[v38] = v46;
              if ( v33 )
              {
                memset_0(v32, 0, v33);
              }
              else
              {
                v32 = LocalAlloc(0x40u, 0x14u);
                if ( !v32 )
                {
                  LastError = 14;
                  v29 = 14;
                  LocalFree(v37);
                  v21 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
                    v21 = WPP_GLOBAL_Control;
                    goto LABEL_70;
                  }
LABEL_69:
                  LastError = v29;
                  if ( !v29 )
                  {
                    v41 = v58;
                    LocalFree(hMemb);
                    v42 = v59;
                    v43 = v60;
                    goto LABEL_74;
                  }
LABEL_70:
                  if ( v21 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                    return LastError;
                  v23 = 87;
                  v28 = v29;
LABEL_46:
                  WPP_SF_d(*((_QWORD *)v21 + 2), v23, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids, v28);
                  return LastError;
                }
                v33 = 20;
              }
              v29 = HmacSha1(v37, v35, (PUCHAR)v32, v39, pbSecret, 0x28u);
              if ( v29 )
              {
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    76,
                    WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids,
                    v29);
              }
              else
              {
                v40 = 60 - v30;
                if ( v40 > 20 )
                  LOWORD(v40) = 20;
                memcpy_0(&v58[v30], v32, (unsigned __int16)v40);
                v30 += v40;
              }
              LocalFree(v37);
              v34 = v51;
            }
          }
          LastError = GetLastError();
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            return LastError;
          v23 = 86;
LABEL_45:
          v28 = LastError;
          goto LABEL_46;
        }
      }
    }
  }
  v42 = *(_OWORD *)&v57[8];
  v43 = *(_DWORD *)&v57[24];
  v41 = pbSecret;
  LastError = 0;
LABEL_74:
  *(_OWORD *)a2 = v42;
  *((_DWORD *)a2 + 4) = v43;
  if ( a3 )
  {
    strcpy((char *)v54, "Session Key Generating Function");
    v44 = PRFPlus(v41, (unsigned __int16)a2, (unsigned __int8 *)v54, 0x20u, a3, 0x80u);
    LastError = v44;
    if ( v44 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v23 = 89;
        v28 = v44;
        goto LABEL_46;
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180013eb0  mov     [rsp-8+arg_18], rbx
0x180013eb5  push    rbp
0x180013eb6  push    rsi
0x180013eb7  push    rdi
0x180013eb8  push    r12
0x180013eba  push    r13
0x180013ebc  push    r14
0x180013ebe  push    r15
0x180013ec0  lea     rbp, [rsp-20h]
0x180013ec5  sub     rsp, 120h
0x180013ecc  mov     rax, cs:__security_cookie
0x180013ed3  xor     rax, rsp
0x180013ed6  mov     [rbp+50h+var_38], rax
0x180013eda  movups  xmm0, xmmword ptr cs:aInnerMethodsCo; "Inner Methods Compound Keys"
0x180013ee1  mov     [rsp+150h+var_100], r8
0x180013ee6  mov     r14, rcx
0x180013ee9  movups  xmm1, xmmword ptr cs:aInnerMethodsCo+0Ch; "s Compound Keys"
0x180013ef0  mov     [rsp+150h+var_110], rdx
0x180013ef5  lea     rax, [rsp+150h+Src]
0x180013efa  movups  xmmword ptr [rsp+150h+Src], xmm0
0x180013eff  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180013f06  movups  xmmword ptr [rsp+150h+Src+0Ch], xmm1
0x180013f0b  nop     dword ptr [rax+rax+00h]
0x180013f10  inc     rbx
0x180013f13  cmp     byte ptr [rax+rbx], 0
0x180013f17  jnz     short loc_180013F10
0x180013f19  test    dword ptr [rcx+4], 1
0x180013f20  mov     r12d, 0
0x180013f26  mov     rax, [rcx+0B00h]
0x180013f2d  mov     r13d, r12d
0x180013f30  setnz   dil
0x180013f34  add     dil, 10h
0x180013f38  test    dword ptr [rcx+4], 1
0x180013f3f  mov     r15, [rax+218h]
0x180013f46  setz    sil
0x180013f4a  add     sil, 10h
0x180013f4e  mov     eax, [r15]
0x180013f51  test    eax, eax
0x180013f53  jz      loc_1800144A8
0x180013f59  cmp     eax, 1Ah
0x180013f5c  jnz     short loc_180013FCC
0x180013f5e  cmp     dword ptr [r15+4], 38h ; '8'
0x180013f63  jnz     short loc_180013FCC
0x180013f65  mov     rcx, [r15+8]
0x180013f69  mov     [rsp+150h+hMem], rcx
0x180013f6e  call    cs:__imp_EapConvertWireToHostFormat32
0x180013f75  nop     dword ptr [rax+rax+00h]
0x180013f7a  cmp     eax, 137h
0x180013f7f  jnz     short loc_180013FCC
0x180013f81  mov     rax, [rsp+150h+hMem]
0x180013f86  movzx   ecx, byte ptr [rax+4]
0x180013f8a  cmp     dil, cl
0x180013f8d  jnz     short loc_180013FAC
0x180013f8f  movups  xmm0, xmmword ptr [rax+9]
0x180013f93  mov     r13d, 1
0x180013f99  movups  xmmword ptr [rbp+50h+var_B8], xmm0
0x180013f9d  movups  xmm1, xmmword ptr [rax+19h]
0x180013fa1  movups  [rbp+50h+var_A8], xmm1
0x180013fa5  cmp     r12d, r13d
0x180013fa8  jnz     short loc_180013FCC
0x180013faa  jmp     short loc_180013FD8
0x180013fac  cmp     sil, cl
0x180013faf  jnz     short loc_180013FCC
0x180013fb1  movups  xmm0, xmmword ptr [rax+9]
0x180013fb5  mov     r12d, 1
0x180013fbb  movups  [rbp+50h+var_98], xmm0
0x180013fbf  movups  xmm1, xmmword ptr [rax+15h]
0x180013fc3  movups  [rbp+50h+var_98+0Ch], xmm1
0x180013fc7  cmp     r13d, r12d
0x180013fca  jz      short loc_180013FE1
0x180013fcc  mov     eax, [r15+10h]
0x180013fd0  add     r15, 10h
0x180013fd4  test    eax, eax
0x180013fd6  jnz     short loc_180013F59
0x180013fd8  test    r12d, r12d
0x180013fdb  jz      loc_1800144A8
0x180013fe1  test    r13d, r13d
0x180013fe4  jz      loc_1800144A8
0x180013fea  cmp     dword ptr [r14+0A50h], 0
0x180013ff2  lea     rsi, WPP_GLOBAL_Control
0x180013ff9  jnz     loc_18001442D
0x180013fff  mov     rdi, [r14+0AE0h]
0x180014006  test    rdi, rdi
0x180014009  jz      loc_18001442D
0x18001400f  movzx   r14d, byte ptr [r14+4]
0x180014014  xor     r15d, r15d
0x180014017  mov     eax, [rdi]
0x180014019  and     r14b, 1
0x18001401d  or      r14b, 10h
0x180014021  mov     [rsp+150h+hMem], r15
0x180014026  xor     r13d, r13d
0x180014029  xor     r12d, r12d
0x18001402c  xor     esi, esi
0x18001402e  test    eax, eax
0x180014030  jz      loc_1800140F0
0x180014036  cmp     eax, 1Ah
0x180014039  jnz     short loc_180014079
0x18001403b  mov     r15, [rdi+8]
0x18001403f  mov     rcx, r15
0x180014042  call    cs:__imp_EapConvertWireToHostFormat32
0x180014049  nop     dword ptr [rax+rax+00h]
0x18001404e  cmp     eax, 137h
0x180014053  jnz     short loc_180014074
0x180014055  movzx   edx, byte ptr [r15+4]
0x18001405a  lea     eax, [rdx-10h]
0x18001405d  cmp     al, 1
0x18001405f  ja      short loc_180014074
0x180014061  movzx   ecx, byte ptr [r15+8]
0x180014066  lea     rax, [r15+9]
0x18001406a  cmp     dl, r14b
0x18001406d  jnz     short loc_1800140D9
0x18001406f  mov     esi, ecx
0x180014071  mov     r13, rax
0x180014074  mov     r15, [rsp+150h+hMem]
0x180014079  mov     eax, [rdi+10h]
0x18001407c  add     rdi, 10h
0x180014080  test    eax, eax
0x180014082  jnz     short loc_180014036
0x180014084  cmp     esi, r12d
0x180014087  jz      short loc_1800140E6
0x180014089  test    esi, esi
0x18001408b  jz      short loc_180014092
0x18001408d  test    r12d, r12d
0x180014090  jnz     short loc_1800140E6
0x180014092  mov     rcx, cs:WPP_GLOBAL_Control
0x180014099  lea     rdi, WPP_GLOBAL_Control
0x1800140a0  cmp     rcx, rdi
0x1800140a3  jz      short loc_1800140C1
0x1800140a5  mov     rcx, [rcx+10h]
0x1800140a9  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x1800140b0  mov     edx, 5Bh ; '['
0x1800140b5  call    WPP_SF_
0x1800140ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140c1  mov     ebx, 0Dh
0x1800140c6  cmp     rcx, rdi
0x1800140c9  jz      loc_1800144D5
0x1800140cf  mov     edx, 58h ; 'X'
0x1800140d4  jmp     loc_1800141A8
0x1800140d9  mov     r12d, ecx
0x1800140dc  mov     [rsp+150h+hMem], rax
0x1800140e1  mov     r15, rax
0x1800140e4  jmp     short loc_180014079
0x1800140e6  mov     edi, 20h ; ' '
0x1800140eb  cmp     esi, 20h ; ' '
0x1800140ee  ja      short loc_1800140F2
0x1800140f0  mov     edi, esi
0x1800140f2  mov     r8d, edi; Size
0x1800140f5  lea     rcx, [rsp+150h+var_D8]; void *
0x1800140fa  mov     rdx, r13; Src
0x1800140fd  call    memcpy_0
0x180014102  mov     eax, 20h ; ' '
0x180014107  sub     eax, edi
0x180014109  jz      short loc_18001412D
0x18001410b  cmp     eax, r12d
0x18001410e  mov     ecx, r12d
0x180014111  cmovb   ecx, eax
0x180014114  test    ecx, ecx
0x180014116  jz      short loc_18001412D
0x180014118  mov     r8d, ecx; Size
0x18001411b  mov     rdx, r15; Src
0x18001411e  mov     eax, esi
0x180014120  lea     rcx, [rsp+150h+var_D8]
0x180014125  add     rcx, rax; void *
0x180014128  call    memcpy_0
0x18001412d  lea     eax, [rsi+r12]
0x180014131  cmp     eax, 20h ; ' '
0x180014134  jnb     short loc_180014159
0x180014136  mov     edx, esi
0x180014138  lea     rcx, [rsp+150h+var_D8]
0x18001413d  mov     eax, r12d
0x180014140  mov     r8d, 20h ; ' '
0x180014146  add     rcx, rax
0x180014149  sub     r8d, esi
0x18001414c  add     rcx, rdx; void *
0x18001414f  sub     r8d, r12d; Size
0x180014152  xor     edx, edx; Val
0x180014154  call    memset_0
0x180014159  movzx   ebx, bx
0x18001415c  mov     ecx, 40h ; '@'; uFlags
0x180014161  lea     rdx, [rbx+20h]; uBytes
0x180014165  call    cs:__imp_LocalAlloc
0x18001416c  nop     dword ptr [rax+rax+00h]
0x180014171  mov     [rsp+150h+hMem], rax
0x180014176  mov     r12, rax
0x180014179  test    rax, rax
0x18001417c  jnz     short loc_1800141C0
0x18001417e  call    cs:__imp_GetLastError
0x180014185  nop     dword ptr [rax+rax+00h]
0x18001418a  mov     ebx, eax
0x18001418c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014193  lea     rax, WPP_GLOBAL_Control
0x18001419a  cmp     rcx, rax
0x18001419d  jz      loc_1800144D5
0x1800141a3  mov     edx, 56h ; 'V'
0x1800141a8  mov     r9d, ebx
0x1800141ab  mov     rcx, [rcx+10h]
0x1800141af  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x1800141b6  call    WPP_SF_d
0x1800141bb  jmp     loc_1800144D5
0x1800141c0  mov     r8, rbx; Size
0x1800141c3  lea     rdx, [rsp+150h+Src]; Src
0x1800141c8  mov     rcx, r12; void *
0x1800141cb  call    memcpy_0
0x1800141d0  movups  xmm0, xmmword ptr [rsp+150h+var_D8]
0x1800141d5  xor     r14d, r14d
0x1800141d8  xor     esi, esi
0x1800141da  movups  xmm1, xmmword ptr [rbp+50h+var_D8+10h]
0x1800141de  xor     r15d, r15d
0x1800141e1  xor     r13d, r13d
0x1800141e4  movups  xmmword ptr [rbx+r12], xmm0
0x1800141e9  movups  xmmword ptr [rbx+r12+10h], xmm1
0x1800141ef  add     bx, 20h ; ' '
0x1800141f3  xor     cl, cl
0x1800141f5  mov     [rsp+150h+var_108], rbx
0x1800141fa  mov     [rsp+150h+var_120], cl
0x1800141fe  xchg    ax, ax
0x180014200  cmp     si, 3Ch ; '<'
0x180014204  jnb     loc_1800143C2
0x18001420a  movzx   ecx, r13w
0x18001420e  add     ecx, 3
0x180014211  movzx   r12d, bx
0x180014215  add     r12d, ecx
0x180014218  mov     ecx, 40h ; '@'; uFlags
0x18001421d  mov     edx, r12d; uBytes
0x180014220  call    cs:__imp_LocalAlloc
0x180014227  nop     dword ptr [rax+rax+00h]
0x18001422c  mov     rdi, rax
0x18001422f  test    rax, rax
0x180014232  jz      loc_180014392
0x180014238  inc     [rsp+150h+var_120]
0x18001423c  mov     rdx, r15; Src
0x18001423f  movzx   r14d, r13w
0x180014243  mov     rcx, rax; void *
0x180014246  mov     r8d, r14d; Size
0x180014249  call    memcpy_0
0x18001424e  mov     rdx, [rsp+150h+hMem]; Src
0x180014253  lea     rcx, [r14+rdi]; void *
0x180014257  movzx   ebx, bx
0x18001425a  mov     r8d, ebx; Size
0x18001425d  call    memcpy_0
0x180014262  movzx   ecx, [rsp+150h+var_120]
0x180014267  lea     rax, [rbx+r14]
0x18001426b  mov     ebx, 3Ch ; '<'
0x180014270  mov     [rax+rdi], bx
0x180014274  mov     [rax+rdi], cl
0x180014277  test    r13w, r13w
0x18001427b  jnz     short loc_1800142A9
0x18001427d  mov     r14d, 14h
0x180014283  mov     ecx, 40h ; '@'; uFlags
0x180014288  mov     edx, r14d; uBytes
0x18001428b  call    cs:__imp_LocalAlloc
0x180014292  nop     dword ptr [rax+rax+00h]
0x180014297  mov     r15, rax
0x18001429a  test    rax, rax
0x18001429d  jz      loc_18001434A
0x1800142a3  movzx   r13d, r14w
0x1800142a7  jmp     short loc_1800142B6
0x1800142a9  mov     r8, r14; Size
0x1800142ac  xor     edx, edx; Val
0x1800142ae  mov     rcx, r15; void *
0x1800142b1  call    memset_0
0x1800142b6  lea     rax, [rbp+50h+var_B8]
0x1800142ba  mov     [rsp+150h+var_128], 28h ; '('; unsigned int
0x1800142c2  mov     r8, r15; pbOutput
0x1800142c5  mov     [rsp+150h+pbSecret], rax; pbSecret
0x1800142ca  mov     edx, r12d; cbInput
0x1800142cd  mov     rcx, rdi; pbInput
0x1800142d0  call    ?HmacSha1@@YAKPEAEK0K0K@Z; HmacSha1(uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x1800142d5  mov     r14d, eax
0x1800142d8  test    eax, eax
0x1800142da  jz      short loc_180014309
0x1800142dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142e3  lea     rax, WPP_GLOBAL_Control
0x1800142ea  cmp     rcx, rax
0x1800142ed  jz      short loc_180014331
0x1800142ef  mov     rcx, [rcx+10h]
0x1800142f3  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x1800142fa  mov     edx, 4Ch ; 'L'
0x1800142ff  mov     r9d, r14d
0x180014302  call    WPP_SF_d
0x180014307  jmp     short loc_180014331
0x180014309  movzx   eax, si
0x18001430c  sub     ebx, eax
0x18001430e  cmp     ebx, 14h
0x180014311  jle     short loc_180014318
0x180014313  mov     ebx, 14h
0x180014318  movzx   eax, si
0x18001431b  lea     rcx, [rbp+50h+var_78]
0x18001431f  add     rcx, rax; void *
0x180014322  movzx   r8d, bx; Size
0x180014326  mov     rdx, r15; Src
0x180014329  call    memcpy_0
0x18001432e  add     si, bx
0x180014331  mov     rcx, rdi; hMem
0x180014334  call    cs:__imp_LocalFree
0x18001433b  nop     dword ptr [rax+rax+00h]
0x180014340  mov     rbx, [rsp+150h+var_108]
0x180014345  jmp     loc_180014200
0x18001434a  mov     ebx, 0Eh
0x18001434f  mov     rcx, rdi; hMem
  ... truncated ...
```
