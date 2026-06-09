# WSTSealMessage

- ea: `0x14002a4d8`
- end: `0x14002ae08`
- name: `WSTSealMessage`
- size: `2352`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140029690`

## callees

- `0x140007008`
- `0x140010160`
- `0x140010240`
- `0x1400102c0`
- `0x1400261e0`
- `0x140029f74`
- `0x14002a2e4`
- `0x14002a4d8`
- `0x14002c874`
- `0x14002ddb8`

## string_xrefs

- `0x14002a667`: `onecore\ds\security\protocols\pku2u\message.cxx`
- `0x14002a63e`: `Can't have readonly & readonly_w_checksum\n`

## pseudocode

```c
__int64 __fastcall WSTSealMessage(__int64 a1, int a2, __int64 a3, char a4)
{
  __int64 v4; // r13
  int v9; // ebx
  int v10; // eax
  int v11; // ecx
  __int64 v12; // r11
  unsigned int v13; // r10d
  unsigned int v14; // r12d
  unsigned int i; // r9d
  _DWORD *v16; // rdx
  int v17; // r8d
  int v18; // eax
  int v19; // r14d
  _BYTE *v20; // rdi
  unsigned __int64 v21; // rcx
  int v22; // eax
  int v23; // ecx
  unsigned __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // r15
  unsigned __int64 v27; // rdx
  size_t v28; // rsi
  unsigned int v29; // r15d
  unsigned int v30; // r14d
  unsigned int j; // eax
  __int64 v32; // r11
  __int64 v33; // rdx
  int v34; // r9d
  unsigned int v35; // r10d
  int v36; // r15d
  unsigned int v37; // ebx
  char v38; // dl
  int v39; // ecx
  int v40; // r8d
  int v41; // ecx
  __int64 v42; // rcx
  unsigned int v43; // ebx
  unsigned int v44; // r8d
  const void *v45; // rdx
  int v46; // ecx
  char v47; // cl
  int v48; // edx
  int v49; // r8d
  int v50; // ecx
  unsigned __int64 v51; // rdx
  unsigned __int64 v52; // rcx
  char v53; // al
  bool v54; // zf
  int v55; // eax
  unsigned __int64 v56; // rdx
  unsigned __int64 v57; // rcx
  __int64 v59; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v60; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v61; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v62; // [rsp+68h] [rbp-98h] BYREF
  __int64 v63; // [rsp+70h] [rbp-90h] BYREF
  int v64; // [rsp+78h] [rbp-88h]
  __int64 v65; // [rsp+80h] [rbp-80h] BYREF
  __int64 v66; // [rsp+88h] [rbp-78h] BYREF
  void *v67; // [rsp+90h] [rbp-70h] BYREF
  __int64 v68; // [rsp+98h] [rbp-68h]
  size_t Size; // [rsp+A0h] [rbp-60h]
  _BYTE Src[96]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v71; // [rsp+110h] [rbp+10h] BYREF
  int v72; // [rsp+118h] [rbp+18h]

  v68 = a3;
  v4 = 0;
  v61 = 0;
  v59 = 0;
  v63 = 0;
  v65 = 0;
  v62 = 0;
  v60 = 0;
  v66 = 0;
  v67 = 0;
  v64 = a2;
  v9 = WSTGetChecksumAndEncryptionType(a1, 1, a2, (unsigned int)&v62, (__int64)&v60);
  if ( v9 < 0 )
    return (unsigned int)v9;
  v10 = CDLocateCSystem(v60, &v59);
  v9 = v10;
  if ( v10 < 0 )
  {
    if ( !KsecInfoLevel )
      return (unsigned int)v9;
    KsecDebugOut(1, "Failed to load %d crypt system: %#x\n", v11, v10);
    goto LABEL_129;
  }
  v60 = *(_DWORD *)(v59 + 4);
  if ( v60 > 0x20 )
    return (unsigned int)-1073741637;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  for ( i = 0; i < *(_DWORD *)(a3 + 4); ++i )
  {
    v16 = (_DWORD *)(*(_QWORD *)(a3 + 8) + 16LL * i);
    v17 = v16[1];
    v18 = v17 & 0x10000000;
    if ( v17 < 0 && v18 )
    {
      v9 = -2146893048;
      if ( KsecInfoLevel )
        KsecDebugOut(1, "Can't have readonly & readonly_w_checksum\n");
      goto LABEL_129;
    }
    if ( (v17 & 0xFFFFFFF) == 2 )
    {
      v12 = *(_QWORD *)(a3 + 8) + 16LL * i;
    }
    else if ( v17 >= 0 )
    {
      if ( (v17 & 0xFFFFFFF) == 9 )
      {
        *v16 = 0;
      }
      else
      {
        v13 += *v16;
        if ( a2 != -2147483647 && !v18 )
          v14 += *v16;
      }
    }
  }
  if ( v12 )
  {
    v19 = 0;
    if ( a2 != -2147483647 )
    {
      if ( v14 < v13 || !v14 )
        v19 = 16;
      if ( (*(_DWORD *)(a1 + 108) & 0x10) == 0 )
      {
        if ( KsecInfoLevel )
          KsecDebugOut(1, "Trying to seal without asking for confidentiality\n");
LABEL_33:
        v9 = -2146893054;
        goto LABEL_129;
      }
    }
    v9 = WSTMakeSignatureToken(a1, a2, v12, i, 1, a4, v19, (__int64)&v67, (__int64)&v66);
    if ( v9 < 0 )
      goto LABEL_129;
    v20 = v67;
    if ( a2 == -2147483647
      || ((*(_BYTE *)v67 |= 2u,
           *(_OWORD *)&v20[256 * (unsigned __int64)(unsigned __int8)v20[2] + 14 + (unsigned __int8)v20[3]] = *(_OWORD *)(v20 - 2),
           (*v20 & 2) == 0)
        ? (v21 = 0)
        : (v21 = (unsigned __int8)v20[3] + ((unsigned __int64)(unsigned __int8)v20[2] << 8)),
          (unsigned __int8)CDGenerateRandomBits(&v20[((*v20 & 2) != 0 ? 42LL : 26LL) + v21], 16)) )
    {
      v22 = CDLocateCheckSum(v62, &v61);
      v9 = v22;
      if ( v22 >= 0 )
      {
        v4 = v61;
        v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(v61 + 48))(
               *(_QWORD *)(a1 + 80),
               *(unsigned int *)(a1 + 72),
               (*(_DWORD *)(a1 + 104) & 2) != 0 ? 24 : 22,
               &v63);
        if ( v9 < 0 )
          goto LABEL_129;
        if ( a2 != -2147483647 )
        {
          v24 = (*v20 & 2) != 0 ? (unsigned __int8)v20[3] + ((unsigned __int64)(unsigned __int8)v20[2] << 8) : 0LL;
          v25 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(v4 + 24))(
                  v63,
                  16,
                  &v20[v24 + ((*v20 & 2) != 0 ? 42LL : 26LL)]);
          v26 = v59;
          v9 = v25;
          if ( v25 < 0 )
            goto LABEL_130;
          v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(v59 + 40))(
                 *(_QWORD *)(a1 + 80),
                 *(unsigned int *)(a1 + 72),
                 (*(_DWORD *)(a1 + 104) & 2) != 0 ? 24 : 22,
                 &v65);
          if ( v9 < 0 )
            goto LABEL_130;
          v14 += v19 + 16;
          v27 = (*v20 & 2) != 0 ? (unsigned __int8)v20[3] + ((unsigned __int64)(unsigned __int8)v20[2] << 8) : 0LL;
          v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(v26 + 96))(
                 v65,
                 v14,
                 16,
                 &v20[v27 + ((*v20 & 2) != 0 ? 42LL : 26LL)]);
          if ( v9 < 0 )
            goto LABEL_130;
        }
        v28 = 0;
        v29 = 0;
        v30 = 0;
        v67 = 0;
        v66 = 0;
        for ( j = 0; ; j = v62 + 1 )
        {
          v62 = j;
          if ( j >= *(_DWORD *)(v68 + 4) )
            break;
          v32 = *(_QWORD *)(v68 + 8);
          v33 = j;
          v61 = j;
          v34 = *(_DWORD *)(v32 + 16LL * j + 4);
          if ( (v34 & 0xFFFFFFF) != 2 && v34 >= 0 )
          {
            v35 = *(_DWORD *)(v32 + 16LL * j);
            if ( v35 )
            {
              if ( (v34 & 0x10000000) == 0 )
              {
                v36 = *(_DWORD *)(v32 + 16LL * j);
                v37 = v60;
                if ( (_DWORD)v28 )
                {
                  v66 = *(_QWORD *)(v32 + 16LL * j + 8) + v60 - (unsigned int)v28;
                  v37 = v60;
                  v36 = v28 + v35 - v60;
                }
                else
                {
                  v66 = *(_QWORD *)(v32 + 16LL * j + 8);
                }
                v30 = v36 & -v37;
                v29 = v36 - v30;
                v38 = *v20 & 2;
                if ( v38 )
                  v39 = (unsigned __int8)v20[3] + ((unsigned __int8)v20[2] << 8);
                else
                  v39 = 0;
                v40 = v38 != 0 ? 0x10 : 0;
                if ( v40 + v39 != v37 || v29 )
                {
                  v33 = v61;
                }
                else
                {
                  if ( v38 )
                    v41 = (unsigned __int8)v20[3] + ((unsigned __int8)v20[2] << 8);
                  else
                    v41 = 0;
                  v33 = v61;
                  if ( v14 == v41 + v40 + v30 )
                  {
                    v30 -= v37;
                    v29 = v37;
                  }
                }
              }
              if ( v34 != 9 )
              {
                v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(v4 + 24))(
                       v63,
                       v35,
                       *(_QWORD *)(v32 + 16 * v33 + 8));
                if ( v9 < 0 )
                  goto LABEL_129;
                if ( v64 != -2147483647 )
                {
                  v42 = *(_QWORD *)(v68 + 8);
                  if ( (*(_DWORD *)(v42 + 16 * v61 + 4) & 0x10000000) == 0 )
                  {
                    if ( (_DWORD)v28 )
                    {
                      v43 = v60;
                      v44 = *(_DWORD *)(v42 + 16 * v61);
                      if ( v60 - (unsigned int)v28 > v44 )
                      {
                        if ( KsecInfoLevel )
                          KsecDebugOut(
                            1,
                            "Insufficient buffer size %d -- unsupported fragmentation across multiple buffers\n",
                            v44);
                        goto LABEL_33;
                      }
                      v45 = *(const void **)(v42 + 16 * v61 + 8);
                      Size = v60 - (unsigned int)v28;
                      memmove(&Src[v28], v45, Size);
                      v14 -= v43;
                      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _BYTE *))(v59 + 96))(v65, v14, v43, Src);
                      if ( v9 < 0 )
                        goto LABEL_129;
                      memmove(v67, Src, v28);
                      memmove(*(void **)(*(_QWORD *)(v68 + 8) + 16 * v61 + 8), &Src[v28], Size);
                    }
                    if ( v30 )
                    {
                      v14 -= v30;
                      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(v59 + 96))(v65, v14, v30, v66);
                      if ( v9 < 0 )
                        goto LABEL_129;
                    }
                    memmove(Src, (const void *)(v66 + v30), v29);
                    v28 = v29;
                    v67 = (void *)(*(unsigned int *)(*(_QWORD *)(v68 + 8) + 16 * v61)
                                 + *(_QWORD *)(*(_QWORD *)(v68 + 8) + 16 * v61 + 8)
                                 - v29);
                  }
                }
              }
            }
          }
        }
        if ( v64 == -2147483647 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(v4 + 24))(v63, 16, v20 - 2);
          if ( v9 < 0 )
            goto LABEL_129;
        }
        else
        {
          if ( (*v20 & 2) != 0 )
            v46 = (unsigned __int8)v20[3] + ((unsigned __int8)v20[2] << 8);
          else
            v46 = 0;
          v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(v4 + 24))(
                 v63,
                 v46 + ((*v20 & 2) != 0 ? 0x10 : 0),
                 v20 + 14);
          if ( v9 < 0 )
            goto LABEL_129;
          v47 = *v20 & 2;
          if ( v47 )
            v48 = (unsigned __int8)v20[3] + ((unsigned __int8)v20[2] << 8);
          else
            v48 = 0;
          v49 = v47 != 0 ? 0x10 : 0;
          if ( (unsigned int)(v28 + v49 + v48) > 0x60 )
          {
            if ( KsecInfoLevel )
            {
              if ( v47 )
                v50 = (unsigned __int8)v20[3] + ((unsigned __int8)v20[2] << 8);
              else
                v50 = 0;
              KsecDebugOut(1, "ExtraCount %d\n", v50 + v49);
            }
            v9 = -1073741637;
            goto LABEL_129;
          }
          if ( v47 )
            v51 = (unsigned __int8)v20[3] + ((unsigned __int64)(unsigned __int8)v20[2] << 8);
          else
            v51 = 0;
          memmove(&Src[v28], v20 + 14, v51 + (v47 != 0 ? 0x10 : 0));
          v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _BYTE *))(v59 + 96))(v65, 0, v14, Src);
          if ( v9 < 0 )
            goto LABEL_129;
          memmove(v67, Src, v28);
          if ( (*v20 & 2) != 0 )
            v52 = (unsigned __int8)v20[3] + ((unsigned __int64)(unsigned __int8)v20[2] << 8);
          else
            v52 = 0;
          memmove(v20 + 14, &Src[v28], v52 + ((*v20 & 2) != 0 ? 0x10 : 0));
          LODWORD(v28) = 0;
        }
        v53 = 28;
        v20[4] = 0;
        v54 = v64 == -2147483647;
        if ( v64 == -2147483647 )
          v53 = 12;
        v20[5] = v53;
        if ( v54 )
        {
          *((_WORD *)v20 + 1) = 3072;
        }
        else if ( (_DWORD)v28 )
        {
          if ( KsecInfoLevel )
            KsecDebugOut(1, "Non-aligned buffer size to SealMessage: %d extra bytes\n", v28);
          v9 = -2146893048;
          goto LABEL_129;
        }
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(v4 + 32))(v63, &v71);
        if ( v9 >= 0 )
        {
          v55 = (*(__int64 (__fastcall **)(__int64 *))(v4 + 40))(&v63);
          v63 = 0;
          v9 = v55;
          if ( v55 >= 0 )
          {
            if ( (*v20 & 2) != 0 )
              v56 = (unsigned __int8)v20[3] + ((unsigned __int64)(unsigned __int8)v20[2] << 8);
            else
              v56 = 0;
            v57 = v56 + ((*v20 & 2) != 0 ? 0x10 : 0);
            *(_QWORD *)&v20[v57 + 14] = v71;
            *(_DWORD *)&v20[v57 + 22] = v72;
          }
        }
      }
      else
      {
        if ( KsecInfoLevel )
          KsecDebugOut(1, "Failed to load %d checksum: %#x\n", v23, v22);
        v4 = v61;
      }
    }
    else
    {
      v9 = -1073741670;
      if ( KsecInfoLevel )
        KsecDebugOut(1, "%!FUNC! WSTRandomFill failed: %!STATUS!\n", 3221225626LL);
    }
  }
  else
  {
    if ( KsecInfoLevel )
      KsecDebugOut(
        1,
        "No signature buffer found. %s, line %d\n",
        "onecore\\ds\\security\\protocols\\pku2u\\message.cxx",
        1133);
    v9 = -1073741811;
  }
LABEL_129:
  v26 = v59;
LABEL_130:
  if ( v65 && v26 )
    (*(void (__fastcall **)(__int64 *))(v26 + 64))(&v65);
  if ( v63 && v4 )
    (*(void (__fastcall **)(__int64 *))(v4 + 40))(&v63);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14002a4d8  push    rbp
0x14002a4da  push    rbx
0x14002a4db  push    rsi
0x14002a4dc  push    rdi
0x14002a4dd  push    r12
0x14002a4df  push    r13
0x14002a4e1  push    r14
0x14002a4e3  push    r15
0x14002a4e5  lea     rbp, [rsp-68h]
0x14002a4ea  sub     rsp, 168h
0x14002a4f1  mov     rax, cs:__security_cookie
0x14002a4f8  xor     rax, rsp
0x14002a4fb  mov     [rbp+0A0h+var_50], rax
0x14002a4ff  xor     eax, eax
0x14002a501  mov     [rbp+0A0h+var_108], r8
0x14002a505  mov     r13d, eax
0x14002a508  mov     [rsp+1A0h+var_140], rax
0x14002a50d  mov     [rsp+1A0h+var_150], rax
0x14002a512  mov     r14, r8
0x14002a515  mov     [rsp+1A0h+var_130], rax
0x14002a51a  mov     r8d, edx
0x14002a51d  mov     [rbp+0A0h+var_120], rax
0x14002a521  mov     r15d, edx
0x14002a524  mov     [rsp+1A0h+var_138], eax
0x14002a528  lea     r12d, [r13+1]
0x14002a52c  mov     [rsp+1A0h+var_148], eax
0x14002a530  mov     rsi, rcx
0x14002a533  mov     [rbp+0A0h+var_118], rax
0x14002a537  mov     [rbp+0A0h+var_110], rax
0x14002a53b  lea     rax, [rsp+1A0h+var_148]
0x14002a540  mov     edi, r9d
0x14002a543  lea     r9, [rsp+1A0h+var_138]
0x14002a548  mov     [rsp+1A0h+var_128], edx
0x14002a54c  mov     edx, r12d
0x14002a54f  mov     [rsp+1A0h+var_180], rax
0x14002a554  call    WSTGetChecksumAndEncryptionType
0x14002a559  mov     ebx, eax
0x14002a55b  test    eax, eax
0x14002a55d  js      loc_14002ADE5
0x14002a563  mov     ecx, [rsp+1A0h+var_148]
0x14002a567  lea     rdx, [rsp+1A0h+var_150]
0x14002a56c  call    CDLocateCSystem
0x14002a571  mov     ebx, eax
0x14002a573  test    eax, eax
0x14002a575  jns     short loc_14002A59E
0x14002a577  cmp     cs:KsecInfoLevel, r13d
0x14002a57e  jz      loc_14002ADE5
0x14002a584  mov     r8d, ecx
0x14002a587  lea     rdx, aFailedToLoadDC_0; "Failed to load %d crypt system: %#x\n"
0x14002a58e  mov     ecx, r12d
0x14002a591  mov     r9d, eax
0x14002a594  call    KsecDebugOut
0x14002a599  jmp     loc_14002ADAC
0x14002a59e  mov     rcx, [rsp+1A0h+var_150]
0x14002a5a3  mov     eax, [rcx+4]
0x14002a5a6  mov     [rsp+1A0h+var_148], eax
0x14002a5aa  cmp     eax, 20h ; ' '
0x14002a5ad  jbe     short loc_14002A5B9
0x14002a5af  mov     ebx, 0C00000BBh
0x14002a5b4  jmp     loc_14002ADE5
0x14002a5b9  xor     ebx, ebx
0x14002a5bb  mov     r11d, ebx
0x14002a5be  mov     r10d, ebx
0x14002a5c1  mov     r12d, ebx
0x14002a5c4  mov     r9d, ebx
0x14002a5c7  cmp     r9d, [r14+4]
0x14002a5cb  jnb     loc_14002A654
0x14002a5d1  mov     edx, r9d
0x14002a5d4  shl     rdx, 4
0x14002a5d8  add     rdx, [r14+8]
0x14002a5dc  mov     r8d, [rdx+4]
0x14002a5e0  mov     eax, r8d
0x14002a5e3  and     eax, 10000000h
0x14002a5e8  test    r8d, r8d
0x14002a5eb  jns     short loc_14002A5F1
0x14002a5ed  test    eax, eax
0x14002a5ef  jnz     short loc_14002A62C
0x14002a5f1  mov     ecx, r8d
0x14002a5f4  and     ecx, 0FFFFFFFh
0x14002a5fa  cmp     ecx, 2
0x14002a5fd  jnz     short loc_14002A604
0x14002a5ff  mov     r11, rdx
0x14002a602  jmp     short loc_14002A627
0x14002a604  test    r8d, r8d
0x14002a607  js      short loc_14002A627
0x14002a609  cmp     ecx, 9
0x14002a60c  jnz     short loc_14002A612
0x14002a60e  mov     [rdx], ebx
0x14002a610  jmp     short loc_14002A627
0x14002a612  mov     ecx, [rdx]
0x14002a614  add     r10d, ecx
0x14002a617  cmp     r15d, 80000001h
0x14002a61e  jz      short loc_14002A627
0x14002a620  test    eax, eax
0x14002a622  jnz     short loc_14002A627
0x14002a624  add     r12d, ecx
0x14002a627  inc     r9d
0x14002a62a  jmp     short loc_14002A5C7
0x14002a62c  cmp     cs:KsecInfoLevel, r13d
0x14002a633  mov     ebx, 80090308h
0x14002a638  jz      loc_14002ADAC
0x14002a63e  lea     rdx, aCanTHaveReadon; "Can't have readonly & readonly_w_checks"...
0x14002a645  mov     ecx, 1
0x14002a64a  call    KsecDebugOut
0x14002a64f  jmp     loc_14002ADAC
0x14002a654  test    r11, r11
0x14002a657  jnz     short loc_14002A688
0x14002a659  cmp     cs:KsecInfoLevel, ebx
0x14002a65f  jz      short loc_14002A67E
0x14002a661  mov     r9d, 46Dh
0x14002a667  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\protocols\\pku2u"...
0x14002a66e  lea     rdx, aNoSignatureBuf; "No signature buffer found. %s, line %d"...
0x14002a675  lea     ecx, [r11+1]
0x14002a679  call    KsecDebugOut
0x14002a67e  mov     ebx, 0C000000Dh
0x14002a683  jmp     loc_14002ADAC
0x14002a688  mov     r14d, ebx
0x14002a68b  cmp     r15d, 80000001h
0x14002a692  jz      short loc_14002A6CE
0x14002a694  cmp     r12d, r10d
0x14002a697  jb      short loc_14002A69E
0x14002a699  test    r12d, r12d
0x14002a69c  jnz     short loc_14002A6A4
0x14002a69e  mov     r14d, 10h
0x14002a6a4  mov     eax, [rsi+6Ch]
0x14002a6a7  test    al, 10h
0x14002a6a9  jnz     short loc_14002A6CE
0x14002a6ab  cmp     cs:KsecInfoLevel, ebx
0x14002a6b1  jz      short loc_14002A6C4
0x14002a6b3  lea     rdx, aTryingToSealWi; "Trying to seal without asking for confi"...
0x14002a6ba  mov     ecx, 1
0x14002a6bf  call    KsecDebugOut
0x14002a6c4  mov     ebx, 80090302h
0x14002a6c9  jmp     loc_14002ADAC
0x14002a6ce  lea     rcx, [rbp+0A0h+var_118]
0x14002a6d2  mov     r8, r11
0x14002a6d5  mov     [rsp+1A0h+var_160], rcx
0x14002a6da  mov     edx, r15d
0x14002a6dd  lea     rcx, [rbp+0A0h+var_110]
0x14002a6e1  mov     [rsp+1A0h+var_168], rcx
0x14002a6e6  mov     rcx, rsi
0x14002a6e9  mov     [rsp+1A0h+var_170], r14d
0x14002a6ee  mov     [rsp+1A0h+var_178], rdi
0x14002a6f3  mov     byte ptr [rsp+1A0h+var_180], 1
0x14002a6f8  call    WSTMakeSignatureToken
0x14002a6fd  mov     ebx, eax
0x14002a6ff  test    eax, eax
0x14002a701  js      loc_14002ADAC
0x14002a707  mov     rdi, [rbp+0A0h+var_110]
0x14002a70b  cmp     r15d, 80000001h
0x14002a712  jz      loc_14002A799
0x14002a718  or      byte ptr [rdi], 2
0x14002a71b  movzx   eax, byte ptr [rdi+2]
0x14002a71f  movzx   ecx, byte ptr [rdi+3]
0x14002a723  movups  xmm0, xmmword ptr [rdi-2]
0x14002a727  shl     rax, 8
0x14002a72b  add     rax, rdi
0x14002a72e  movdqu  xmmword ptr [rcx+rax+0Eh], xmm0
0x14002a734  mov     dl, [rdi]
0x14002a736  and     dl, 2
0x14002a739  jz      short loc_14002A74C
0x14002a73b  movzx   ecx, byte ptr [rdi+2]
0x14002a73f  movzx   eax, byte ptr [rdi+3]
0x14002a743  shl     rcx, 8
0x14002a747  add     rcx, rax
0x14002a74a  jmp     short loc_14002A74E
0x14002a74c  xor     ecx, ecx
0x14002a74e  neg     dl
0x14002a750  mov     edx, 10h
0x14002a755  sbb     rax, rax
0x14002a758  and     eax, 10h
0x14002a75b  add     rax, 1Ah
0x14002a75f  add     rcx, rax
0x14002a762  add     rcx, rdi
0x14002a765  call    CDGenerateRandomBits
0x14002a76a  test    al, al
0x14002a76c  jnz     short loc_14002A799
0x14002a76e  cmp     cs:KsecInfoLevel, r13d
0x14002a775  mov     ebx, 0C000009Ah
0x14002a77a  jz      loc_14002ADAC
0x14002a780  mov     r8d, ebx
0x14002a783  lea     rdx, aFuncWstrandomf; "%!FUNC! WSTRandomFill failed: %!STATUS!"...
0x14002a78a  mov     ecx, 1
0x14002a78f  call    KsecDebugOut
0x14002a794  jmp     loc_14002ADAC
0x14002a799  mov     ecx, [rsp+1A0h+var_138]
0x14002a79d  lea     rdx, [rsp+1A0h+var_140]
0x14002a7a2  call    CDLocateCheckSum
0x14002a7a7  mov     ebx, eax
0x14002a7a9  test    eax, eax
0x14002a7ab  jns     short loc_14002A7D7
0x14002a7ad  cmp     cs:KsecInfoLevel, r13d
0x14002a7b4  jz      short loc_14002A7CD
0x14002a7b6  mov     r8d, ecx
0x14002a7b9  lea     rdx, aFailedToLoadDC; "Failed to load %d checksum: %#x\n"
0x14002a7c0  mov     ecx, 1
0x14002a7c5  mov     r9d, eax
0x14002a7c8  call    KsecDebugOut
0x14002a7cd  mov     r13, [rsp+1A0h+var_140]
0x14002a7d2  jmp     loc_14002ADAC
0x14002a7d7  mov     eax, [rsi+68h]
0x14002a7da  lea     r9, [rsp+1A0h+var_130]
0x14002a7df  mov     r13, [rsp+1A0h+var_140]
0x14002a7e4  and     al, 2
0x14002a7e6  mov     edx, [rsi+48h]
0x14002a7e9  neg     al
0x14002a7eb  mov     rcx, [rsi+50h]
0x14002a7ef  sbb     r8d, r8d
0x14002a7f2  mov     rax, [r13+30h]
0x14002a7f6  and     r8d, 2
0x14002a7fa  add     r8d, 16h
0x14002a7fe  call    _guard_dispatch_icall
0x14002a803  mov     ebx, eax
0x14002a805  test    eax, eax
0x14002a807  js      loc_14002ADAC
0x14002a80d  cmp     r15d, 80000001h
0x14002a814  jz      loc_14002A8F1
0x14002a81a  mov     cl, [rdi]
0x14002a81c  mov     r9, [r13+18h]
0x14002a820  and     cl, 2
0x14002a823  jz      short loc_14002A836
0x14002a825  movzx   edx, byte ptr [rdi+2]
0x14002a829  movzx   eax, byte ptr [rdi+3]
0x14002a82d  shl     rdx, 8
0x14002a831  add     rdx, rax
0x14002a834  jmp     short loc_14002A838
0x14002a836  xor     edx, edx
0x14002a838  neg     cl
0x14002a83a  mov     rax, r9
0x14002a83d  sbb     rcx, rcx
0x14002a840  and     ecx, 10h
0x14002a843  lea     r8, [rcx+1Ah]
0x14002a847  mov     rcx, [rsp+1A0h+var_130]
0x14002a84c  add     r8, rdx
0x14002a84f  mov     edx, 10h
0x14002a854  add     r8, rdi
0x14002a857  call    _guard_dispatch_icall
0x14002a85c  mov     r15, [rsp+1A0h+var_150]
0x14002a861  mov     ebx, eax
0x14002a863  test    eax, eax
0x14002a865  js      loc_14002ADB1
0x14002a86b  mov     eax, [rsi+68h]
0x14002a86e  lea     r9, [rbp+0A0h+var_120]
0x14002a872  mov     edx, [rsi+48h]
0x14002a875  and     al, 2
0x14002a877  mov     rcx, [rsi+50h]
0x14002a87b  neg     al
0x14002a87d  mov     rax, [r15+28h]
0x14002a881  sbb     r8d, r8d
0x14002a884  and     r8d, 2
0x14002a888  add     r8d, 16h
0x14002a88c  call    _guard_dispatch_icall
0x14002a891  mov     ebx, eax
0x14002a893  test    eax, eax
0x14002a895  js      loc_14002ADB1
0x14002a89b  mov     cl, [rdi]
0x14002a89d  add     r12d, 10h
0x14002a8a1  mov     r10, [r15+60h]
0x14002a8a5  add     r12d, r14d
0x14002a8a8  and     cl, 2
0x14002a8ab  jz      short loc_14002A8BE
0x14002a8ad  movzx   edx, byte ptr [rdi+2]
0x14002a8b1  movzx   eax, byte ptr [rdi+3]
0x14002a8b5  shl     rdx, 8
0x14002a8b9  add     rdx, rax
0x14002a8bc  jmp     short loc_14002A8C0
0x14002a8be  xor     edx, edx
0x14002a8c0  neg     cl
0x14002a8c2  mov     r8d, 10h
0x14002a8c8  mov     rax, r10
0x14002a8cb  sbb     rcx, rcx
0x14002a8ce  and     ecx, 10h
0x14002a8d1  lea     r9, [rcx+1Ah]
0x14002a8d5  mov     rcx, [rbp+0A0h+var_120]
0x14002a8d9  add     r9, rdx
0x14002a8dc  mov     edx, r12d
0x14002a8df  add     r9, rdi
0x14002a8e2  call    _guard_dispatch_icall
0x14002a8e7  mov     ebx, eax
0x14002a8e9  test    eax, eax
0x14002a8eb  js      loc_14002ADB1
0x14002a8f1  xor     esi, esi
0x14002a8f3  xor     r15d, r15d
0x14002a8f6  xor     r14d, r14d
0x14002a8f9  mov     [rbp+0A0h+var_110], rsi
0x14002a8fd  mov     [rbp+0A0h+var_118], rsi
0x14002a901  xor     eax, eax
0x14002a903  mov     rcx, [rbp+0A0h+var_108]
0x14002a907  mov     [rsp+1A0h+var_138], eax
0x14002a90b  cmp     eax, [rcx+4]
0x14002a90e  jnb     loc_14002AB78
0x14002a914  mov     r11, [rcx+8]
0x14002a918  mov     ecx, eax
0x14002a91a  mov     edx, eax
0x14002a91c  add     rcx, rcx
0x14002a91f  mov     [rsp+1A0h+var_140], rdx
0x14002a924  mov     r9d, [r11+rcx*8+4]
0x14002a929  mov     eax, r9d
0x14002a92c  and     eax, 0FFFFFFFh
0x14002a931  cmp     eax, 2
  ... truncated ...
```
