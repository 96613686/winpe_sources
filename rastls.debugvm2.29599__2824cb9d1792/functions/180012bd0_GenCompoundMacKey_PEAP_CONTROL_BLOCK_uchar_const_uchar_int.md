# GenCompoundMacKey(_PEAP_CONTROL_BLOCK *,uchar * const,uchar *,int)

- ea: `0x180012bd0`
- end: `0x1800131e0`
- name: `?GenCompoundMacKey@@YAKPEAU_PEAP_CONTROL_BLOCK@@QEAEPEAEH@Z`
- size: `1552`
- prototype: `unsigned int __fastcall(struct _PEAP_CONTROL_BLOCK *, unsigned __int8 *const, unsigned __int8 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18005cc50`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180012bd0`
- `0x1800131f0`
- `0x180013430`
- `0x180035680`
- `0x18003623c`
- `0x180036254`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e8c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012e79`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012f26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012f8b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012e79`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012f26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012f8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001302e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013049`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800130cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013100`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001302e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013049`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800130cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013100`
- `eapputil!EapConvertWireToHostFormat32` at `0x180012c8e`
- `eapputil!EapConvertWireToHostFormat32` at `0x180012d5c`
- `eapputil!EapConvertWireToHostFormat32` at `0x180012c8e`
- `eapputil!EapConvertWireToHostFormat32` at `0x180012d5c`

## string_xrefs

- `0x180012bfa`: `Inner Methods Compound Keys`

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
0x180012bd0  mov     [rsp-8+arg_18], rbx
0x180012bd5  push    rbp
0x180012bd6  push    rsi
0x180012bd7  push    rdi
0x180012bd8  push    r12
0x180012bda  push    r13
0x180012bdc  push    r14
0x180012bde  push    r15
0x180012be0  lea     rbp, [rsp-20h]
0x180012be5  sub     rsp, 120h
0x180012bec  mov     rax, cs:__security_cookie
0x180012bf3  xor     rax, rsp
0x180012bf6  mov     [rbp+50h+var_38], rax
0x180012bfa  movups  xmm0, xmmword ptr cs:aInnerMethodsCo; "Inner Methods Compound Keys"
0x180012c01  mov     [rsp+150h+var_100], r8
0x180012c06  mov     r14, rcx
0x180012c09  movups  xmm1, xmmword ptr cs:aInnerMethodsCo+0Ch; "s Compound Keys"
0x180012c10  mov     [rsp+150h+var_110], rdx
0x180012c15  lea     rax, [rsp+150h+Src]
0x180012c1a  movups  xmmword ptr [rsp+150h+Src], xmm0
0x180012c1f  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180012c26  movups  xmmword ptr [rsp+150h+Src+0Ch], xmm1
0x180012c2b  nop     dword ptr [rax+rax+00h]
0x180012c30  inc     rbx
0x180012c33  cmp     byte ptr [rax+rbx], 0
0x180012c37  jnz     short loc_180012C30
0x180012c39  test    dword ptr [rcx+4], 1
0x180012c40  mov     r12d, 0
0x180012c46  mov     rax, [rcx+0B00h]
0x180012c4d  mov     r13d, r12d
0x180012c50  setnz   dil
0x180012c54  add     dil, 10h
0x180012c58  test    dword ptr [rcx+4], 1
0x180012c5f  mov     r15, [rax+218h]
0x180012c66  setz    sil
0x180012c6a  add     sil, 10h
0x180012c6e  mov     eax, [r15]
0x180012c71  test    eax, eax
0x180012c73  jz      loc_18001318A
0x180012c79  cmp     eax, 1Ah
0x180012c7c  jnz     short loc_180012CE6
0x180012c7e  cmp     dword ptr [r15+4], 38h ; '8'
0x180012c83  jnz     short loc_180012CE6
0x180012c85  mov     rcx, [r15+8]
0x180012c89  mov     [rsp+150h+hMem], rcx
0x180012c8e  call    cs:__imp_EapConvertWireToHostFormat32
0x180012c94  cmp     eax, 137h
0x180012c99  jnz     short loc_180012CE6
0x180012c9b  mov     rax, [rsp+150h+hMem]
0x180012ca0  movzx   ecx, byte ptr [rax+4]
0x180012ca4  cmp     dil, cl
0x180012ca7  jnz     short loc_180012CC6
0x180012ca9  movups  xmm0, xmmword ptr [rax+9]
0x180012cad  mov     r13d, 1
0x180012cb3  movups  xmmword ptr [rbp+50h+var_B8], xmm0
0x180012cb7  movups  xmm1, xmmword ptr [rax+19h]
0x180012cbb  movups  [rbp+50h+var_A8], xmm1
0x180012cbf  cmp     r12d, r13d
0x180012cc2  jnz     short loc_180012CE6
0x180012cc4  jmp     short loc_180012CF2
0x180012cc6  cmp     sil, cl
0x180012cc9  jnz     short loc_180012CE6
0x180012ccb  movups  xmm0, xmmword ptr [rax+9]
0x180012ccf  mov     r12d, 1
0x180012cd5  movups  [rbp+50h+var_98], xmm0
0x180012cd9  movups  xmm1, xmmword ptr [rax+15h]
0x180012cdd  movups  [rbp+50h+var_98+0Ch], xmm1
0x180012ce1  cmp     r13d, r12d
0x180012ce4  jz      short loc_180012CFB
0x180012ce6  mov     eax, [r15+10h]
0x180012cea  add     r15, 10h
0x180012cee  test    eax, eax
0x180012cf0  jnz     short loc_180012C79
0x180012cf2  test    r12d, r12d
0x180012cf5  jz      loc_18001318A
0x180012cfb  test    r13d, r13d
0x180012cfe  jz      loc_18001318A
0x180012d04  cmp     dword ptr [r14+0A50h], 0
0x180012d0c  lea     rsi, WPP_GLOBAL_Control
0x180012d13  jnz     loc_18001310F
0x180012d19  mov     rdi, [r14+0AE0h]
0x180012d20  test    rdi, rdi
0x180012d23  jz      loc_18001310F
0x180012d29  movzx   r14d, byte ptr [r14+4]
0x180012d2e  xor     r15d, r15d
0x180012d31  mov     eax, [rdi]
0x180012d33  and     r14b, 1
0x180012d37  or      r14b, 10h
0x180012d3b  mov     [rsp+150h+hMem], r15
0x180012d40  xor     r13d, r13d
0x180012d43  xor     r12d, r12d
0x180012d46  xor     esi, esi
0x180012d48  test    eax, eax
0x180012d4a  jz      loc_180012E04
0x180012d50  cmp     eax, 1Ah
0x180012d53  jnz     short loc_180012D8D
0x180012d55  mov     r15, [rdi+8]
0x180012d59  mov     rcx, r15
0x180012d5c  call    cs:__imp_EapConvertWireToHostFormat32
0x180012d62  cmp     eax, 137h
0x180012d67  jnz     short loc_180012D88
0x180012d69  movzx   edx, byte ptr [r15+4]
0x180012d6e  lea     eax, [rdx-10h]
0x180012d71  cmp     al, 1
0x180012d73  ja      short loc_180012D88
0x180012d75  movzx   ecx, byte ptr [r15+8]
0x180012d7a  lea     rax, [r15+9]
0x180012d7e  cmp     dl, r14b
0x180012d81  jnz     short loc_180012DED
0x180012d83  mov     esi, ecx
0x180012d85  mov     r13, rax
0x180012d88  mov     r15, [rsp+150h+hMem]
0x180012d8d  mov     eax, [rdi+10h]
0x180012d90  add     rdi, 10h
0x180012d94  test    eax, eax
0x180012d96  jnz     short loc_180012D50
0x180012d98  cmp     esi, r12d
0x180012d9b  jz      short loc_180012DFA
0x180012d9d  test    esi, esi
0x180012d9f  jz      short loc_180012DA6
0x180012da1  test    r12d, r12d
0x180012da4  jnz     short loc_180012DFA
0x180012da6  mov     rcx, cs:WPP_GLOBAL_Control
0x180012dad  lea     rdi, WPP_GLOBAL_Control
0x180012db4  cmp     rcx, rdi
0x180012db7  jz      short loc_180012DD5
0x180012db9  mov     rcx, [rcx+10h]
0x180012dbd  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x180012dc4  mov     edx, 5Bh ; '['
0x180012dc9  call    WPP_SF_
0x180012dce  mov     rcx, cs:WPP_GLOBAL_Control
0x180012dd5  mov     ebx, 0Dh
0x180012dda  cmp     rcx, rdi
0x180012ddd  jz      loc_1800131B7
0x180012de3  mov     edx, 58h ; 'X'
0x180012de8  jmp     loc_180012EB0
0x180012ded  mov     r12d, ecx
0x180012df0  mov     [rsp+150h+hMem], rax
0x180012df5  mov     r15, rax
0x180012df8  jmp     short loc_180012D8D
0x180012dfa  mov     edi, 20h ; ' '
0x180012dff  cmp     esi, 20h ; ' '
0x180012e02  ja      short loc_180012E06
0x180012e04  mov     edi, esi
0x180012e06  mov     r8d, edi; Size
0x180012e09  lea     rcx, [rsp+150h+var_D8]; void *
0x180012e0e  mov     rdx, r13; Src
0x180012e11  call    memcpy_0
0x180012e16  mov     eax, 20h ; ' '
0x180012e1b  sub     eax, edi
0x180012e1d  jz      short loc_180012E41
0x180012e1f  cmp     eax, r12d
0x180012e22  mov     ecx, r12d
0x180012e25  cmovb   ecx, eax
0x180012e28  test    ecx, ecx
0x180012e2a  jz      short loc_180012E41
0x180012e2c  mov     r8d, ecx; Size
0x180012e2f  mov     rdx, r15; Src
0x180012e32  mov     eax, esi
0x180012e34  lea     rcx, [rsp+150h+var_D8]
0x180012e39  add     rcx, rax; void *
0x180012e3c  call    memcpy_0
0x180012e41  lea     eax, [rsi+r12]
0x180012e45  cmp     eax, 20h ; ' '
0x180012e48  jnb     short loc_180012E6D
0x180012e4a  mov     edx, esi
0x180012e4c  lea     rcx, [rsp+150h+var_D8]
0x180012e51  mov     eax, r12d
0x180012e54  mov     r8d, 20h ; ' '
0x180012e5a  add     rcx, rax
0x180012e5d  sub     r8d, esi
0x180012e60  add     rcx, rdx; void *
0x180012e63  sub     r8d, r12d; Size
0x180012e66  xor     edx, edx; Val
0x180012e68  call    memset_0
0x180012e6d  movzx   ebx, bx
0x180012e70  mov     ecx, 40h ; '@'; uFlags
0x180012e75  lea     rdx, [rbx+20h]; uBytes
0x180012e79  call    cs:__imp_LocalAlloc
0x180012e7f  mov     [rsp+150h+hMem], rax
0x180012e84  mov     r12, rax
0x180012e87  test    rax, rax
0x180012e8a  jnz     short loc_180012EC8
0x180012e8c  call    cs:__imp_GetLastError
0x180012e92  mov     ebx, eax
0x180012e94  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e9b  lea     rax, WPP_GLOBAL_Control
0x180012ea2  cmp     rcx, rax
0x180012ea5  jz      loc_1800131B7
0x180012eab  mov     edx, 56h ; 'V'
0x180012eb0  mov     r9d, ebx
0x180012eb3  mov     rcx, [rcx+10h]
0x180012eb7  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x180012ebe  call    WPP_SF_d
0x180012ec3  jmp     loc_1800131B7
0x180012ec8  mov     r8, rbx; Size
0x180012ecb  lea     rdx, [rsp+150h+Src]; Src
0x180012ed0  mov     rcx, r12; void *
0x180012ed3  call    memcpy_0
0x180012ed8  movups  xmm0, xmmword ptr [rsp+150h+var_D8]
0x180012edd  xor     r14d, r14d
0x180012ee0  xor     esi, esi
0x180012ee2  movups  xmm1, xmmword ptr [rbp+50h+var_D8+10h]
0x180012ee6  xor     r15d, r15d
0x180012ee9  xor     r13d, r13d
0x180012eec  movups  xmmword ptr [rbx+r12], xmm0
0x180012ef1  movups  xmmword ptr [rbx+r12+10h], xmm1
0x180012ef7  add     bx, 20h ; ' '
0x180012efb  xor     cl, cl
0x180012efd  mov     [rsp+150h+var_108], rbx
0x180012f02  mov     [rsp+150h+var_120], cl
0x180012f06  cmp     si, 3Ch ; '<'
0x180012f0a  jnb     loc_1800130B0
0x180012f10  movzx   ecx, r13w
0x180012f14  add     ecx, 3
0x180012f17  movzx   r12d, bx
0x180012f1b  add     r12d, ecx
0x180012f1e  mov     ecx, 40h ; '@'; uFlags
0x180012f23  mov     edx, r12d; uBytes
0x180012f26  call    cs:__imp_LocalAlloc
0x180012f2c  mov     rdi, rax
0x180012f2f  test    rax, rax
0x180012f32  jz      loc_180013080
0x180012f38  inc     [rsp+150h+var_120]
0x180012f3c  mov     rdx, r15; Src
0x180012f3f  movzx   r14d, r13w
0x180012f43  mov     rcx, rax; void *
0x180012f46  mov     r8d, r14d; Size
0x180012f49  call    memcpy_0
0x180012f4e  mov     rdx, [rsp+150h+hMem]; Src
0x180012f53  lea     rcx, [r14+rdi]; void *
0x180012f57  movzx   ebx, bx
0x180012f5a  mov     r8d, ebx; Size
0x180012f5d  call    memcpy_0
0x180012f62  movzx   ecx, [rsp+150h+var_120]
0x180012f67  lea     rax, [rbx+r14]
0x180012f6b  mov     ebx, 3Ch ; '<'
0x180012f70  mov     [rax+rdi], bx
0x180012f74  mov     [rax+rdi], cl
0x180012f77  test    r13w, r13w
0x180012f7b  jnz     short loc_180012FA3
0x180012f7d  mov     r14d, 14h
0x180012f83  mov     ecx, 40h ; '@'; uFlags
0x180012f88  mov     edx, r14d; uBytes
0x180012f8b  call    cs:__imp_LocalAlloc
0x180012f91  mov     r15, rax
0x180012f94  test    rax, rax
0x180012f97  jz      loc_18001303E
0x180012f9d  movzx   r13d, r14w
0x180012fa1  jmp     short loc_180012FB0
0x180012fa3  mov     r8, r14; Size
0x180012fa6  xor     edx, edx; Val
0x180012fa8  mov     rcx, r15; void *
0x180012fab  call    memset_0
0x180012fb0  lea     rax, [rbp+50h+var_B8]
0x180012fb4  mov     [rsp+150h+var_128], 28h ; '('; unsigned int
0x180012fbc  mov     r8, r15; pbOutput
0x180012fbf  mov     [rsp+150h+pbSecret], rax; pbSecret
0x180012fc4  mov     edx, r12d; cbInput
0x180012fc7  mov     rcx, rdi; pbInput
0x180012fca  call    ?HmacSha1@@YAKPEAEK0K0K@Z; HmacSha1(uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x180012fcf  mov     r14d, eax
0x180012fd2  test    eax, eax
0x180012fd4  jz      short loc_180013003
0x180012fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fdd  lea     rax, WPP_GLOBAL_Control
0x180012fe4  cmp     rcx, rax
0x180012fe7  jz      short loc_18001302B
0x180012fe9  mov     rcx, [rcx+10h]
0x180012fed  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x180012ff4  mov     edx, 4Ch ; 'L'
0x180012ff9  mov     r9d, r14d
0x180012ffc  call    WPP_SF_d
0x180013001  jmp     short loc_18001302B
0x180013003  movzx   eax, si
0x180013006  sub     ebx, eax
0x180013008  cmp     ebx, 14h
0x18001300b  jle     short loc_180013012
0x18001300d  mov     ebx, 14h
0x180013012  movzx   eax, si
0x180013015  lea     rcx, [rbp+50h+var_78]
0x180013019  add     rcx, rax; void *
0x18001301c  movzx   r8d, bx; Size
0x180013020  mov     rdx, r15; Src
0x180013023  call    memcpy_0
0x180013028  add     si, bx
0x18001302b  mov     rcx, rdi; hMem
0x18001302e  call    cs:__imp_LocalFree
0x180013034  mov     rbx, [rsp+150h+var_108]
0x180013039  jmp     loc_180012F06
0x18001303e  mov     ebx, 0Eh
0x180013043  mov     rcx, rdi; hMem
0x180013046  mov     r14d, ebx
0x180013049  call    cs:__imp_LocalFree
0x18001304f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013056  lea     rsi, WPP_GLOBAL_Control
0x18001305d  cmp     rcx, rsi
0x180013060  jz      short loc_1800130D9
0x180013062  mov     rcx, [rcx+10h]
0x180013066  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
  ... truncated ...
```
