# write_double_translated_ansi_nolock

- ea: `0x18000f1ac`
- end: `0x18000f69b`
- name: `write_double_translated_ansi_nolock`
- size: `1263`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18000fb8c`

## callees

- `0x180005ac0`
- `0x180008434`
- `0x180008870`
- `0x18000cf5c`
- `0x18000f1ac`
- `0x1800115f0`
- `0x18008e3b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000f669`
- `KERNEL32!GetLastError` at `0x18000f669`
- `KERNEL32!WriteFile` at `0x18000f52c`
- `KERNEL32!WriteFile` at `0x18000f57a`
- `KERNEL32!WriteFile` at `0x18000f52c`
- `KERNEL32!WriteFile` at `0x18000f57a`
- `KERNEL32!GetConsoleOutputCP` at `0x18000f232`
- `KERNEL32!GetConsoleOutputCP` at `0x18000f232`

## pseudocode

```c
__int64 __fastcall write_double_translated_ansi_nolock(__int64 a1, int a2, _BYTE *a3, int a4, __int64 a5)
{
  _BYTE *v5; // rdi
  __int64 v6; // r14
  __int64 v7; // rbx
  char v8; // r13
  __int64 v9; // r12
  __int64 v10; // rsi
  unsigned __int64 v11; // r15
  struct _Mbstatet *v12; // r11
  int v13; // ecx
  __int64 v14; // rdx
  int v15; // r8d
  int v16; // esi
  __int64 v17; // r14
  int v18; // r15d
  __int64 v19; // r10
  signed __int64 v20; // r8
  unsigned int v21; // r9d
  __int64 v22; // r10
  int v23; // edx
  unsigned int v24; // r14d
  __int64 v25; // r15
  __int64 v26; // r9
  unsigned int v27; // esi
  __int64 v28; // rdx
  __int64 v29; // r8
  wchar_t *v30; // rdx
  __int64 v31; // r9
  DWORD v32; // esi
  HANDLE v33; // r14
  int v34; // r8d
  struct __crt_cached_ptd_host *v36; // [rsp+30h] [rbp-99h]
  __int16 v37[2]; // [rsp+48h] [rbp-81h] BYREF
  int v38; // [rsp+4Ch] [rbp-7Dh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-79h] BYREF
  unsigned __int64 v40; // [rsp+58h] [rbp-71h]
  struct _Mbstatet *v41; // [rsp+60h] [rbp-69h]
  unsigned __int64 v42; // [rsp+68h] [rbp-61h] BYREF
  UINT ConsoleOutputCP; // [rsp+74h] [rbp-55h]
  int v44; // [rsp+78h] [rbp-51h]
  __int64 v45; // [rsp+80h] [rbp-49h]
  __int64 v46; // [rsp+88h] [rbp-41h]
  __int64 v47; // [rsp+90h] [rbp-39h]
  unsigned __int64 v48; // [rsp+98h] [rbp-31h] BYREF
  wchar_t v49[4]; // [rsp+A0h] [rbp-29h] BYREF
  wchar_t v50[4]; // [rsp+A8h] [rbp-21h] BYREF
  HANDLE hFile; // [rsp+B0h] [rbp-19h]
  _BYTE *v52; // [rsp+B8h] [rbp-11h]
  __int64 v53; // [rsp+C0h] [rbp-9h]
  _BYTE v54[8]; // [rsp+C8h] [rbp-1h] BYREF
  _BYTE v55[8]; // [rsp+D0h] [rbp+7h] BYREF
  char Buffer[8]; // [rsp+D8h] [rbp+Fh] BYREF

  v53 = -2;
  v5 = a3;
  v52 = a3;
  v6 = a2;
  v7 = a1;
  v45 = a1;
  v41 = (struct _Mbstatet *)a5;
  v8 = a2;
  v9 = (__int64)a2 >> 6;
  v10 = 9LL * (a2 & 0x3F);
  v46 = v10;
  hFile = *(HANDLE *)(_pioinfo[v9] + 72LL * (a2 & 0x3F) + 40);
  v11 = (unsigned __int64)&a3[a4];
  v40 = v11;
  ConsoleOutputCP = GetConsoleOutputCP();
  v12 = (struct _Mbstatet *)a5;
  if ( !*(_BYTE *)(a5 + 40) )
  {
    __crt_cached_ptd_host::update_locale_slow((__crt_cached_ptd_host *)v41);
    v12 = v41;
  }
  *(_QWORD *)v7 = 0;
  *(_DWORD *)(v7 + 8) = 0;
  v47 = (__int64)v5;
  if ( (unsigned __int64)v5 < v11 )
  {
    v13 = *(_DWORD *)(*(_QWORD *)&v12[3] + 12LL);
    v44 = v13;
    v14 = v6 >> 6;
    v47 = v6 >> 6;
    v15 = 0;
    while ( 1 )
    {
      LOBYTE(v37[0]) = *v5;
      v38 = 0;
      if ( v13 == 65001 )
      {
        v16 = 0;
        v17 = 72LL * (v8 & 0x3F);
        do
        {
          if ( !*(_BYTE *)(_pioinfo[v14] + (unsigned int)v16 + v17 + 62) )
            break;
          ++v16;
        }
        while ( v16 < 5 );
        if ( v16 )
        {
          LODWORD(v42) = *((char *)lookuptrailbytes + *(unsigned __int8 *)(_pioinfo[v9] + v17 + 62)) + 1;
          v18 = v42 - v16;
          v19 = v40 - (_QWORD)v5;
          v20 = (int)v42 - v16;
          v21 = 0;
          if ( v20 > (__int64)(v40 - (_QWORD)v5) )
          {
            if ( v19 > 0 )
            {
              do
              {
                *(_BYTE *)(v17 + (int)(v21 + v16) + _pioinfo[v9] + 62) = v5[v21];
                ++v21;
              }
              while ( (int)v21 < v19 );
              v7 = v45;
            }
            *(_DWORD *)(v7 + 4) += v19;
            return v7;
          }
          v22 = _pioinfo[v14];
          do
          {
            v54[v21] = *(_BYTE *)(v22 + v17 + v21 + 62);
            ++v21;
          }
          while ( (int)v21 < v16 );
          if ( v18 > 0 )
          {
            memmove(&v54[v16], v5, v20);
            v12 = v41;
          }
          v23 = 0;
          do
            *(_BYTE *)(v17 + v23++ + _pioinfo[v9] + 62) = 0;
          while ( v23 < v16 );
          v7 = v45;
          v48 = 0;
          *(_QWORD *)v49 = v54;
          v24 = ((_DWORD)v42 == 4) + 1;
          if ( __crt_mbstring::__mbsrtowcs_utf8(
                 (__crt_mbstring *)&v38,
                 v49,
                 (const char **)v24,
                 (unsigned __int64)&v48,
                 v12,
                 v36) == -1 )
            return v7;
          v5 += v18 - 1;
        }
        else
        {
          v25 = *((char *)lookuptrailbytes + (unsigned __int8)*v5);
          v26 = v40 - (_QWORD)v5;
          if ( (int)v25 + 1 > (__int64)(v40 - (_QWORD)v5) )
          {
            v34 = 0;
            if ( v26 > 0 )
            {
              do
              {
                *(_BYTE *)(v34 + _pioinfo[v9] + v17 + 62) = v5[v34];
                ++v34;
              }
              while ( v34 < v26 );
              v7 = v45;
            }
            *(_DWORD *)(v7 + 4) += v26;
            return v7;
          }
          v42 = 0;
          *(_QWORD *)v50 = v5;
          v27 = ((_DWORD)v25 == 3) + 1;
          if ( __crt_mbstring::__mbsrtowcs_utf8(
                 (__crt_mbstring *)&v38,
                 v50,
                 (const char **)v27,
                 (unsigned __int64)&v42,
                 v12,
                 v36) == -1 )
            return v7;
          v5 += v25;
          v24 = v27;
        }
        v11 = v40;
      }
      else
      {
        v24 = 1;
        v28 = _pioinfo[v9];
        if ( (*(_BYTE *)(v28 + 8 * v10 + 61) & 4) != 0 )
        {
          v55[0] = *(_BYTE *)(v28 + 72LL * (v8 & 0x3F) + 62);
          v55[1] = *v5;
          *(_BYTE *)(v28 + 72LL * (v8 & 0x3F) + 61) &= ~4u;
          v29 = 2;
          v30 = (wchar_t *)v55;
          goto LABEL_30;
        }
        v31 = (unsigned __int8)*v5;
        if ( *(__int16 *)(**(_QWORD **)&v12[3] + 2 * v31) >= 0 )
        {
          v29 = 1;
          v30 = (wchar_t *)v5;
LABEL_30:
          if ( (unsigned int)mbtowc_internal((__crt_mbstring *)&v38, v30, (char *)v29, (__crt_cached_ptd_host *)v12) == -1 )
            return v7;
          goto LABEL_31;
        }
        if ( (unsigned __int64)(v5 + 1) >= v11 )
        {
          *(_BYTE *)(v28 + 72LL * (v8 & 0x3F) + 62) = v31;
          *(_BYTE *)(_pioinfo[v9] + 8 * v46 + 61) |= 4u;
          *(_DWORD *)(v7 + 4) = v15 + 1;
          return v7;
        }
        if ( (unsigned int)mbtowc_internal(
                             (__crt_mbstring *)&v38,
                             (wchar_t *)v5,
                             (char *)2,
                             (__crt_cached_ptd_host *)v12) == -1 )
          return v7;
        ++v5;
      }
LABEL_31:
      ++v5;
      v32 = _acrt_WideCharToMultiByte(ConsoleOutputCP, 0, (unsigned int)&v38, v24, (unsigned int)Buffer, 5, 0, 0);
      if ( !v32 )
        return v7;
      NumberOfBytesWritten = 0;
      v33 = hFile;
      if ( !WriteFile(hFile, Buffer, v32, &NumberOfBytesWritten, 0) )
      {
LABEL_49:
        *(_DWORD *)v7 = GetLastError();
        return v7;
      }
      v15 = (_DWORD)v5 + *(_DWORD *)(v7 + 8) - (_DWORD)v52;
      *(_DWORD *)(v7 + 4) = v15;
      if ( NumberOfBytesWritten < v32 )
        return v7;
      if ( LOBYTE(v37[0]) == 10 )
      {
        v37[0] = 13;
        if ( !WriteFile(v33, v37, 1u, &NumberOfBytesWritten, 0) )
          goto LABEL_49;
        if ( !NumberOfBytesWritten )
          return v7;
        ++*(_DWORD *)(v7 + 8);
        v15 = ++*(_DWORD *)(v7 + 4);
      }
      if ( (unsigned __int64)v5 >= v11 )
        return v7;
      v12 = v41;
      v10 = v46;
      v14 = v47;
      v13 = v44;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000f1ac  mov     rax, rsp
0x18000f1af  push    rbp
0x18000f1b0  push    rsi
0x18000f1b1  push    rdi
0x18000f1b2  push    r12
0x18000f1b4  push    r13
0x18000f1b6  push    r14
0x18000f1b8  push    r15
0x18000f1ba  lea     rbp, [rax-57h]
0x18000f1be  sub     rsp, 0E0h
0x18000f1c5  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x18000f1cd  mov     [rax+8], rbx
0x18000f1d1  mov     rax, cs:__security_cookie
0x18000f1d8  xor     rax, rsp
0x18000f1db  mov     [rbp+4Fh+var_38], rax
0x18000f1df  mov     rdi, r8
0x18000f1e2  mov     [rbp+4Fh+var_60], r8
0x18000f1e6  movsxd  r14, edx
0x18000f1e9  mov     rbx, rcx
0x18000f1ec  mov     [rbp+4Fh+var_98], rcx
0x18000f1f0  mov     rax, [rbp+4Fh+arg_20]
0x18000f1f4  mov     [rbp+4Fh+var_B8], rax
0x18000f1f8  mov     r13, r14
0x18000f1fb  mov     r12, r14
0x18000f1fe  sar     r12, 6
0x18000f202  lea     rcx, cs:180000000h
0x18000f209  mov     eax, r14d
0x18000f20c  and     eax, 3Fh
0x18000f20f  lea     rsi, [rax+rax*8]
0x18000f213  mov     [rbp+4Fh+var_90], rsi
0x18000f217  mov     rax, rva __pioinfo[rcx+r12*8]
0x18000f21f  mov     rax, [rax+rsi*8+28h]
0x18000f224  mov     [rbp+4Fh+hFile], rax
0x18000f228  mov     r15d, r9d
0x18000f22b  add     r15, r8
0x18000f22e  mov     [rbp+4Fh+var_C0], r15
0x18000f232  call    cs:__imp_GetConsoleOutputCP
0x18000f238  mov     [rbp+4Fh+var_A4], eax
0x18000f23b  xor     r10d, r10d
0x18000f23e  mov     r11, [rbp+4Fh+var_B8]
0x18000f242  cmp     [r11+28h], r10b
0x18000f246  jnz     short loc_18000F257
0x18000f248  mov     rcx, r11; this
0x18000f24b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18000f250  mov     r11, [rbp+4Fh+var_B8]
0x18000f254  xor     r10d, r10d
0x18000f257  xor     eax, eax
0x18000f259  mov     [rbx], rax
0x18000f25c  mov     [rbx+8], eax
0x18000f25f  mov     [rbp+4Fh+var_88], rdi
0x18000f263  cmp     rdi, r15
0x18000f266  jnb     loc_18000F671
0x18000f26c  mov     rax, [r11+18h]
0x18000f270  mov     ecx, [rax+0Ch]
0x18000f273  mov     [rbp+4Fh+var_A0], ecx
0x18000f276  mov     rdx, r14
0x18000f279  sar     rdx, 6
0x18000f27d  mov     [rbp+4Fh+var_88], rdx
0x18000f281  mov     r8d, r10d
0x18000f284  mov     al, [rdi]
0x18000f286  mov     byte ptr [rsp+110h+var_D0], al
0x18000f28a  mov     [rbp+4Fh+var_CC], r10d
0x18000f28e  cmp     ecx, 0FDE9h
0x18000f294  jnz     loc_18000F42D
0x18000f29a  mov     esi, r10d
0x18000f29d  mov     rax, r13
0x18000f2a0  and     eax, 3Fh
0x18000f2a3  lea     r14, [rax+rax*8]
0x18000f2a7  shl     r14, 3
0x18000f2ab  lea     r8, cs:180000000h
0x18000f2b2  mov     eax, esi
0x18000f2b4  add     rax, rva __pioinfo[r8+rdx*8]
0x18000f2bc  cmp     [rax+r14+3Eh], r10b
0x18000f2c1  jz      short loc_18000F2CA
0x18000f2c3  inc     esi
0x18000f2c5  cmp     esi, 5
0x18000f2c8  jl      short loc_18000F2B2
0x18000f2ca  test    esi, esi
0x18000f2cc  jz      loc_18000F3C3
0x18000f2d2  mov     rax, rva __pioinfo[r8+r12*8]
0x18000f2da  movzx   ecx, byte ptr [rax+r14+3Eh]
0x18000f2e0  movsx   eax, byte ptr [rcx+r8+0A4B10h]
0x18000f2e9  inc     eax
0x18000f2eb  mov     dword ptr [rbp+4Fh+var_B0], eax
0x18000f2ee  mov     r15d, eax
0x18000f2f1  sub     r15d, esi
0x18000f2f4  mov     r10, [rbp+4Fh+var_C0]
0x18000f2f8  sub     r10, rdi
0x18000f2fb  movsxd  r8, r15d; Size
0x18000f2fe  xor     eax, eax
0x18000f300  mov     r9d, eax
0x18000f303  cmp     r8, r10
0x18000f306  jg      loc_18000F5BC
0x18000f30c  lea     r10, cs:180000000h
0x18000f313  mov     r10, rva __pioinfo[r10+rdx*8]
0x18000f31b  mov     edx, r9d
0x18000f31e  lea     rax, [r10+r14]
0x18000f322  mov     cl, [rax+rdx+3Eh]
0x18000f326  mov     [rbp+rdx+4Fh+var_50], cl
0x18000f32a  inc     r9d
0x18000f32d  cmp     r9d, esi
0x18000f330  jl      short loc_18000F31B
0x18000f332  xor     r9d, r9d
0x18000f335  test    r15d, r15d
0x18000f338  jle     short loc_18000F352
0x18000f33a  mov     eax, esi
0x18000f33c  lea     rcx, [rbp+4Fh+var_50]
0x18000f340  add     rcx, rax; void *
0x18000f343  mov     rdx, rdi; Src
0x18000f346  call    memmove
0x18000f34b  xor     r9d, r9d
0x18000f34e  mov     r11, [rbp+4Fh+var_B8]
0x18000f352  mov     edx, r9d
0x18000f355  lea     rbx, cs:180000000h
0x18000f35c  movsxd  rcx, edx
0x18000f35f  add     rcx, r14
0x18000f362  mov     rax, rva __pioinfo[rbx+r12*8]
0x18000f36a  mov     [rcx+rax+3Eh], r9b
0x18000f36f  inc     edx
0x18000f371  cmp     edx, esi
0x18000f373  jl      short loc_18000F35C
0x18000f375  mov     rbx, [rbp+4Fh+var_98]
0x18000f379  mov     [rbp+4Fh+var_80], r9
0x18000f37d  lea     rax, [rbp+4Fh+var_50]
0x18000f381  mov     qword ptr [rbp+4Fh+var_78], rax
0x18000f385  mov     eax, r9d
0x18000f388  cmp     dword ptr [rbp+4Fh+var_B0], 4
0x18000f38c  setz    al
0x18000f38f  inc     eax
0x18000f391  mov     r14d, eax
0x18000f394  mov     r8d, eax; char **
0x18000f397  mov     [rsp+110h+lpOverlapped], r11; struct _Mbstatet *
0x18000f39c  lea     r9, [rbp+4Fh+var_80]; unsigned __int64
0x18000f3a0  lea     rdx, [rbp+4Fh+var_78]; wchar_t *
0x18000f3a4  lea     rcx, [rbp+4Fh+var_CC]; this
0x18000f3a8  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18000f3ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f3b1  jz      loc_18000F671
0x18000f3b7  lea     eax, [r15-1]
0x18000f3bb  movsxd  rcx, eax
0x18000f3be  add     rdi, rcx
0x18000f3c1  jmp     short loc_18000F424
0x18000f3c3  movzx   eax, byte ptr [rdi]
0x18000f3c6  movsx   r15, byte ptr [rax+r8+0A4B10h]
0x18000f3cf  lea     ecx, [r15+1]
0x18000f3d3  mov     r9, [rbp+4Fh+var_C0]
0x18000f3d7  sub     r9, rdi
0x18000f3da  movsxd  rax, ecx
0x18000f3dd  cmp     rax, r9
0x18000f3e0  jg      loc_18000F5FA
0x18000f3e6  mov     [rbp+4Fh+var_B0], r10
0x18000f3ea  mov     qword ptr [rbp+4Fh+var_70], rdi
0x18000f3ee  mov     eax, r10d
0x18000f3f1  cmp     ecx, 4
0x18000f3f4  setz    al
0x18000f3f7  inc     eax
0x18000f3f9  mov     esi, eax
0x18000f3fb  mov     r8d, eax; char **
0x18000f3fe  mov     [rsp+110h+lpOverlapped], r11; struct _Mbstatet *
0x18000f403  lea     r9, [rbp+4Fh+var_B0]; unsigned __int64
0x18000f407  lea     rdx, [rbp+4Fh+var_70]; wchar_t *
0x18000f40b  lea     rcx, [rbp+4Fh+var_CC]; this
0x18000f40f  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18000f414  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f418  jz      loc_18000F671
0x18000f41e  add     rdi, r15
0x18000f421  mov     r14d, esi
0x18000f424  mov     r15, [rbp+4Fh+var_C0]
0x18000f428  jmp     loc_18000F4D5
0x18000f42d  mov     r14d, 1
0x18000f433  lea     rax, cs:180000000h
0x18000f43a  mov     rdx, rva __pioinfo[rax+r12*8]
0x18000f442  test    byte ptr [rdx+rsi*8+3Dh], 4
0x18000f447  jz      short loc_18000F478
0x18000f449  mov     rax, r13
0x18000f44c  and     eax, 3Fh
0x18000f44f  lea     rax, [rax+rax*8]
0x18000f453  mov     cl, [rdx+rax*8+3Eh]
0x18000f457  mov     [rbp+4Fh+var_48], cl
0x18000f45a  mov     al, [rdi]
0x18000f45c  mov     [rbp+4Fh+var_47], al
0x18000f45f  mov     eax, r13d
0x18000f462  and     eax, 3Fh
0x18000f465  lea     rcx, [rax+rax*8]
0x18000f469  and     byte ptr [rdx+rcx*8+3Dh], 0FBh
0x18000f46e  lea     r8d, [r14+1]
0x18000f472  lea     rdx, [rbp+4Fh+var_48]
0x18000f476  jmp     short loc_18000F4C0
0x18000f478  movzx   r9d, byte ptr [rdi]
0x18000f47c  mov     rax, [r11+18h]
0x18000f480  mov     rcx, [rax]
0x18000f483  cmp     [rcx+r9*2], r10w
0x18000f488  jge     short loc_18000F4BA
0x18000f48a  lea     rsi, [rdi+1]
0x18000f48e  cmp     rsi, r15
0x18000f491  jnb     loc_18000F634
0x18000f497  mov     r9, r11; __crt_cached_ptd_host *
0x18000f49a  mov     r8d, 2; char *
0x18000f4a0  mov     rdx, rdi; wchar_t *
0x18000f4a3  lea     rcx, [rbp+4Fh+var_CC]; this
0x18000f4a7  call    _mbtowc_internal
0x18000f4ac  cmp     eax, 0FFFFFFFFh
0x18000f4af  jz      loc_18000F671
0x18000f4b5  mov     rdi, rsi
0x18000f4b8  jmp     short loc_18000F4D5
0x18000f4ba  mov     r8, r14; char *
0x18000f4bd  mov     rdx, rdi; wchar_t *
0x18000f4c0  mov     r9, r11; __crt_cached_ptd_host *
0x18000f4c3  lea     rcx, [rbp+4Fh+var_CC]; this
0x18000f4c7  call    _mbtowc_internal
0x18000f4cc  cmp     eax, 0FFFFFFFFh
0x18000f4cf  jz      loc_18000F671
0x18000f4d5  inc     rdi
0x18000f4d8  xor     eax, eax
0x18000f4da  mov     qword ptr [rsp+110h+var_D8], rax
0x18000f4df  mov     [rsp+110h+var_E0], rax
0x18000f4e4  mov     dword ptr [rsp+110h+var_E8], 5
0x18000f4ec  lea     rax, [rbp+4Fh+Buffer]
0x18000f4f0  mov     [rsp+110h+lpOverlapped], rax
0x18000f4f5  mov     r9d, r14d
0x18000f4f8  lea     r8, [rbp+4Fh+var_CC]
0x18000f4fc  xor     edx, edx
0x18000f4fe  mov     ecx, [rbp+4Fh+var_A4]
0x18000f501  call    __acrt_WideCharToMultiByte
0x18000f506  mov     esi, eax
0x18000f508  xor     eax, eax
0x18000f50a  test    esi, esi
0x18000f50c  jz      loc_18000F671
0x18000f512  mov     [rbp+4Fh+NumberOfBytesWritten], eax
0x18000f515  mov     [rsp+110h+lpOverlapped], rax; lpOverlapped
0x18000f51a  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000f51e  mov     r8d, esi; nNumberOfBytesToWrite
0x18000f521  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x18000f525  mov     r14, [rbp+4Fh+hFile]
0x18000f529  mov     rcx, r14; hFile
0x18000f52c  call    cs:__imp_WriteFile
0x18000f532  xor     r10d, r10d
0x18000f535  test    eax, eax
0x18000f537  jz      loc_18000F669
0x18000f53d  mov     r8d, [rbx+8]
0x18000f541  sub     r8d, dword ptr [rbp+4Fh+var_60]
0x18000f545  add     r8d, edi
0x18000f548  mov     [rbx+4], r8d
0x18000f54c  cmp     [rbp+4Fh+NumberOfBytesWritten], esi
0x18000f54f  jb      loc_18000F671
0x18000f555  cmp     byte ptr [rsp+110h+var_D0], 0Ah
0x18000f55a  jnz     short loc_18000F59F
0x18000f55c  lea     eax, [r10+0Dh]
0x18000f560  mov     [rsp+110h+var_D0], ax
0x18000f565  mov     [rsp+110h+lpOverlapped], r10; lpOverlapped
0x18000f56a  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000f56e  lea     r8d, [r10+1]; nNumberOfBytesToWrite
0x18000f572  lea     rdx, [rsp+110h+var_D0]; lpBuffer
0x18000f577  mov     rcx, r14; hFile
0x18000f57a  call    cs:__imp_WriteFile
0x18000f580  xor     r10d, r10d
0x18000f583  test    eax, eax
0x18000f585  jz      loc_18000F669
0x18000f58b  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x18000f58f  jb      loc_18000F671
0x18000f595  inc     dword ptr [rbx+8]
0x18000f598  inc     dword ptr [rbx+4]
0x18000f59b  mov     r8d, [rbx+4]
0x18000f59f  cmp     rdi, r15
0x18000f5a2  jnb     loc_18000F671
0x18000f5a8  mov     r11, [rbp+4Fh+var_B8]
0x18000f5ac  mov     rsi, [rbp+4Fh+var_90]
0x18000f5b0  mov     rdx, [rbp+4Fh+var_88]
0x18000f5b4  mov     ecx, [rbp+4Fh+var_A0]
0x18000f5b7  jmp     loc_18000F284
0x18000f5bc  test    r10, r10
0x18000f5bf  jle     short loc_18000F5F4
0x18000f5c1  lea     rbx, cs:180000000h
0x18000f5c8  movsxd  r8, r9d
0x18000f5cb  lea     eax, [r9+rsi]
0x18000f5cf  movsxd  rdx, eax
0x18000f5d2  add     rdx, r14
0x18000f5d5  mov     rcx, rva __pioinfo[rbx+r12*8]
0x18000f5dd  mov     al, [r8+rdi]
0x18000f5e1  mov     [rdx+rcx+3Eh], al
0x18000f5e5  inc     r9d
0x18000f5e8  movsxd  rax, r9d
0x18000f5eb  cmp     rax, r10
0x18000f5ee  jl      short loc_18000F5C8
0x18000f5f0  mov     rbx, [rbp+4Fh+var_98]
0x18000f5f4  add     [rbx+4], r10d
0x18000f5f8  jmp     short loc_18000F671
0x18000f5fa  mov     r8d, r10d
0x18000f5fd  test    r9, r9
0x18000f600  jle     short loc_18000F62E
0x18000f602  lea     rbx, cs:180000000h
0x18000f609  movsxd  rdx, r8d
0x18000f60c  mov     rcx, rva __pioinfo[rbx+r12*8]
0x18000f614  add     rcx, rdx
0x18000f617  mov     al, [rdx+rdi]
0x18000f61a  mov     [rcx+r14+3Eh], al
0x18000f61f  inc     r8d
0x18000f622  movsxd  rax, r8d
0x18000f625  cmp     rax, r9
0x18000f628  jl      short loc_18000F609
  ... truncated ...
```
