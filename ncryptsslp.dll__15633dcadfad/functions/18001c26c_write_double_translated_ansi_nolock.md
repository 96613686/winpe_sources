# write_double_translated_ansi_nolock

- ea: `0x18001c26c`
- end: `0x18001c75b`
- name: `write_double_translated_ansi_nolock`
- size: `1263`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18001cc4c`

## callees

- `0x180018020`
- `0x1800186e0`
- `0x18001b1d8`
- `0x18001b568`
- `0x18001c26c`
- `0x180024ef0`
- `0x180024fb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c729`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x18001c2f2`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x18001c2f2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001c5ec`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001c63a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001c5ec`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001c63a`

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
0x18001c26c  mov     rax, rsp
0x18001c26f  push    rbp
0x18001c270  push    rsi
0x18001c271  push    rdi
0x18001c272  push    r12
0x18001c274  push    r13
0x18001c276  push    r14
0x18001c278  push    r15
0x18001c27a  lea     rbp, [rax-57h]
0x18001c27e  sub     rsp, 0E0h
0x18001c285  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x18001c28d  mov     [rax+8], rbx
0x18001c291  mov     rax, cs:__security_cookie
0x18001c298  xor     rax, rsp
0x18001c29b  mov     [rbp+4Fh+var_38], rax
0x18001c29f  mov     rdi, r8
0x18001c2a2  mov     [rbp+4Fh+var_60], r8
0x18001c2a6  movsxd  r14, edx
0x18001c2a9  mov     rbx, rcx
0x18001c2ac  mov     [rbp+4Fh+var_98], rcx
0x18001c2b0  mov     rax, [rbp+4Fh+arg_20]
0x18001c2b4  mov     [rbp+4Fh+var_B8], rax
0x18001c2b8  mov     r13, r14
0x18001c2bb  mov     r12, r14
0x18001c2be  sar     r12, 6
0x18001c2c2  lea     rcx, __ImageBase
0x18001c2c9  mov     eax, r14d
0x18001c2cc  and     eax, 3Fh
0x18001c2cf  lea     rsi, [rax+rax*8]
0x18001c2d3  mov     [rbp+4Fh+var_90], rsi
0x18001c2d7  mov     rax, rva __pioinfo[rcx+r12*8]
0x18001c2df  mov     rax, [rax+rsi*8+28h]
0x18001c2e4  mov     [rbp+4Fh+hFile], rax
0x18001c2e8  mov     r15d, r9d
0x18001c2eb  add     r15, r8
0x18001c2ee  mov     [rbp+4Fh+var_C0], r15
0x18001c2f2  call    cs:__imp_GetConsoleOutputCP
0x18001c2f8  mov     [rbp+4Fh+var_A4], eax
0x18001c2fb  xor     r10d, r10d
0x18001c2fe  mov     r11, [rbp+4Fh+var_B8]
0x18001c302  cmp     [r11+28h], r10b
0x18001c306  jnz     short loc_18001C317
0x18001c308  mov     rcx, r11; this
0x18001c30b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18001c310  mov     r11, [rbp+4Fh+var_B8]
0x18001c314  xor     r10d, r10d
0x18001c317  xor     eax, eax
0x18001c319  mov     [rbx], rax
0x18001c31c  mov     [rbx+8], eax
0x18001c31f  mov     [rbp+4Fh+var_88], rdi
0x18001c323  cmp     rdi, r15
0x18001c326  jnb     loc_18001C731
0x18001c32c  mov     rax, [r11+18h]
0x18001c330  mov     ecx, [rax+0Ch]
0x18001c333  mov     [rbp+4Fh+var_A0], ecx
0x18001c336  mov     rdx, r14
0x18001c339  sar     rdx, 6
0x18001c33d  mov     [rbp+4Fh+var_88], rdx
0x18001c341  mov     r8d, r10d
0x18001c344  mov     al, [rdi]
0x18001c346  mov     byte ptr [rsp+110h+var_D0], al
0x18001c34a  mov     [rbp+4Fh+var_CC], r10d
0x18001c34e  cmp     ecx, 0FDE9h
0x18001c354  jnz     loc_18001C4ED
0x18001c35a  mov     esi, r10d
0x18001c35d  mov     rax, r13
0x18001c360  and     eax, 3Fh
0x18001c363  lea     r14, [rax+rax*8]
0x18001c367  shl     r14, 3
0x18001c36b  lea     r8, __ImageBase
0x18001c372  mov     eax, esi
0x18001c374  add     rax, rva __pioinfo[r8+rdx*8]
0x18001c37c  cmp     [rax+r14+3Eh], r10b
0x18001c381  jz      short loc_18001C38A
0x18001c383  inc     esi
0x18001c385  cmp     esi, 5
0x18001c388  jl      short loc_18001C372
0x18001c38a  test    esi, esi
0x18001c38c  jz      loc_18001C483
0x18001c392  mov     rax, rva __pioinfo[r8+r12*8]
0x18001c39a  movzx   ecx, byte ptr [rax+r14+3Eh]
0x18001c3a0  movsx   eax, byte ptr [rcx+r8+379A0h]
0x18001c3a9  inc     eax
0x18001c3ab  mov     dword ptr [rbp+4Fh+var_B0], eax
0x18001c3ae  mov     r15d, eax
0x18001c3b1  sub     r15d, esi
0x18001c3b4  mov     r10, [rbp+4Fh+var_C0]
0x18001c3b8  sub     r10, rdi
0x18001c3bb  movsxd  r8, r15d; Size
0x18001c3be  xor     eax, eax
0x18001c3c0  mov     r9d, eax
0x18001c3c3  cmp     r8, r10
0x18001c3c6  jg      loc_18001C67C
0x18001c3cc  lea     r10, __ImageBase
0x18001c3d3  mov     r10, rva __pioinfo[r10+rdx*8]
0x18001c3db  mov     edx, r9d
0x18001c3de  lea     rax, [r10+r14]
0x18001c3e2  mov     cl, [rax+rdx+3Eh]
0x18001c3e6  mov     [rbp+rdx+4Fh+var_50], cl
0x18001c3ea  inc     r9d
0x18001c3ed  cmp     r9d, esi
0x18001c3f0  jl      short loc_18001C3DB
0x18001c3f2  xor     r9d, r9d
0x18001c3f5  test    r15d, r15d
0x18001c3f8  jle     short loc_18001C412
0x18001c3fa  mov     eax, esi
0x18001c3fc  lea     rcx, [rbp+4Fh+var_50]
0x18001c400  add     rcx, rax; void *
0x18001c403  mov     rdx, rdi; Src
0x18001c406  call    memmove
0x18001c40b  xor     r9d, r9d
0x18001c40e  mov     r11, [rbp+4Fh+var_B8]
0x18001c412  mov     edx, r9d
0x18001c415  lea     rbx, __ImageBase
0x18001c41c  movsxd  rcx, edx
0x18001c41f  add     rcx, r14
0x18001c422  mov     rax, rva __pioinfo[rbx+r12*8]
0x18001c42a  mov     [rcx+rax+3Eh], r9b
0x18001c42f  inc     edx
0x18001c431  cmp     edx, esi
0x18001c433  jl      short loc_18001C41C
0x18001c435  mov     rbx, [rbp+4Fh+var_98]
0x18001c439  mov     [rbp+4Fh+var_80], r9
0x18001c43d  lea     rax, [rbp+4Fh+var_50]
0x18001c441  mov     qword ptr [rbp+4Fh+var_78], rax
0x18001c445  mov     eax, r9d
0x18001c448  cmp     dword ptr [rbp+4Fh+var_B0], 4
0x18001c44c  setz    al
0x18001c44f  inc     eax
0x18001c451  mov     r14d, eax
0x18001c454  mov     r8d, eax; char **
0x18001c457  mov     [rsp+110h+lpOverlapped], r11; struct _Mbstatet *
0x18001c45c  lea     r9, [rbp+4Fh+var_80]; unsigned __int64
0x18001c460  lea     rdx, [rbp+4Fh+var_78]; wchar_t *
0x18001c464  lea     rcx, [rbp+4Fh+var_CC]; this
0x18001c468  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18001c46d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c471  jz      loc_18001C731
0x18001c477  lea     eax, [r15-1]
0x18001c47b  movsxd  rcx, eax
0x18001c47e  add     rdi, rcx
0x18001c481  jmp     short loc_18001C4E4
0x18001c483  movzx   eax, byte ptr [rdi]
0x18001c486  movsx   r15, byte ptr [rax+r8+379A0h]
0x18001c48f  lea     ecx, [r15+1]
0x18001c493  mov     r9, [rbp+4Fh+var_C0]
0x18001c497  sub     r9, rdi
0x18001c49a  movsxd  rax, ecx
0x18001c49d  cmp     rax, r9
0x18001c4a0  jg      loc_18001C6BA
0x18001c4a6  mov     [rbp+4Fh+var_B0], r10
0x18001c4aa  mov     qword ptr [rbp+4Fh+var_70], rdi
0x18001c4ae  mov     eax, r10d
0x18001c4b1  cmp     ecx, 4
0x18001c4b4  setz    al
0x18001c4b7  inc     eax
0x18001c4b9  mov     esi, eax
0x18001c4bb  mov     r8d, eax; char **
0x18001c4be  mov     [rsp+110h+lpOverlapped], r11; struct _Mbstatet *
0x18001c4c3  lea     r9, [rbp+4Fh+var_B0]; unsigned __int64
0x18001c4c7  lea     rdx, [rbp+4Fh+var_70]; wchar_t *
0x18001c4cb  lea     rcx, [rbp+4Fh+var_CC]; this
0x18001c4cf  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18001c4d4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c4d8  jz      loc_18001C731
0x18001c4de  add     rdi, r15
0x18001c4e1  mov     r14d, esi
0x18001c4e4  mov     r15, [rbp+4Fh+var_C0]
0x18001c4e8  jmp     loc_18001C595
0x18001c4ed  mov     r14d, 1
0x18001c4f3  lea     rax, __ImageBase
0x18001c4fa  mov     rdx, rva __pioinfo[rax+r12*8]
0x18001c502  test    byte ptr [rdx+rsi*8+3Dh], 4
0x18001c507  jz      short loc_18001C538
0x18001c509  mov     rax, r13
0x18001c50c  and     eax, 3Fh
0x18001c50f  lea     rax, [rax+rax*8]
0x18001c513  mov     cl, [rdx+rax*8+3Eh]
0x18001c517  mov     [rbp+4Fh+var_48], cl
0x18001c51a  mov     al, [rdi]
0x18001c51c  mov     [rbp+4Fh+var_47], al
0x18001c51f  mov     eax, r13d
0x18001c522  and     eax, 3Fh
0x18001c525  lea     rcx, [rax+rax*8]
0x18001c529  and     byte ptr [rdx+rcx*8+3Dh], 0FBh
0x18001c52e  lea     r8d, [r14+1]
0x18001c532  lea     rdx, [rbp+4Fh+var_48]
0x18001c536  jmp     short loc_18001C580
0x18001c538  movzx   r9d, byte ptr [rdi]
0x18001c53c  mov     rax, [r11+18h]
0x18001c540  mov     rcx, [rax]
0x18001c543  cmp     [rcx+r9*2], r10w
0x18001c548  jge     short loc_18001C57A
0x18001c54a  lea     rsi, [rdi+1]
0x18001c54e  cmp     rsi, r15
0x18001c551  jnb     loc_18001C6F4
0x18001c557  mov     r9, r11; __crt_cached_ptd_host *
0x18001c55a  mov     r8d, 2; char *
0x18001c560  mov     rdx, rdi; wchar_t *
0x18001c563  lea     rcx, [rbp+4Fh+var_CC]; this
0x18001c567  call    _mbtowc_internal
0x18001c56c  cmp     eax, 0FFFFFFFFh
0x18001c56f  jz      loc_18001C731
0x18001c575  mov     rdi, rsi
0x18001c578  jmp     short loc_18001C595
0x18001c57a  mov     r8, r14; char *
0x18001c57d  mov     rdx, rdi; wchar_t *
0x18001c580  mov     r9, r11; __crt_cached_ptd_host *
0x18001c583  lea     rcx, [rbp+4Fh+var_CC]; this
0x18001c587  call    _mbtowc_internal
0x18001c58c  cmp     eax, 0FFFFFFFFh
0x18001c58f  jz      loc_18001C731
0x18001c595  inc     rdi
0x18001c598  xor     eax, eax
0x18001c59a  mov     qword ptr [rsp+110h+var_D8], rax
0x18001c59f  mov     [rsp+110h+var_E0], rax
0x18001c5a4  mov     dword ptr [rsp+110h+var_E8], 5
0x18001c5ac  lea     rax, [rbp+4Fh+Buffer]
0x18001c5b0  mov     [rsp+110h+lpOverlapped], rax
0x18001c5b5  mov     r9d, r14d
0x18001c5b8  lea     r8, [rbp+4Fh+var_CC]
0x18001c5bc  xor     edx, edx
0x18001c5be  mov     ecx, [rbp+4Fh+var_A4]
0x18001c5c1  call    __acrt_WideCharToMultiByte
0x18001c5c6  mov     esi, eax
0x18001c5c8  xor     eax, eax
0x18001c5ca  test    esi, esi
0x18001c5cc  jz      loc_18001C731
0x18001c5d2  mov     [rbp+4Fh+NumberOfBytesWritten], eax
0x18001c5d5  mov     [rsp+110h+lpOverlapped], rax; lpOverlapped
0x18001c5da  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001c5de  mov     r8d, esi; nNumberOfBytesToWrite
0x18001c5e1  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x18001c5e5  mov     r14, [rbp+4Fh+hFile]
0x18001c5e9  mov     rcx, r14; hFile
0x18001c5ec  call    cs:__imp_WriteFile
0x18001c5f2  xor     r10d, r10d
0x18001c5f5  test    eax, eax
0x18001c5f7  jz      loc_18001C729
0x18001c5fd  mov     r8d, [rbx+8]
0x18001c601  sub     r8d, dword ptr [rbp+4Fh+var_60]
0x18001c605  add     r8d, edi
0x18001c608  mov     [rbx+4], r8d
0x18001c60c  cmp     [rbp+4Fh+NumberOfBytesWritten], esi
0x18001c60f  jb      loc_18001C731
0x18001c615  cmp     byte ptr [rsp+110h+var_D0], 0Ah
0x18001c61a  jnz     short loc_18001C65F
0x18001c61c  lea     eax, [r10+0Dh]
0x18001c620  mov     [rsp+110h+var_D0], ax
0x18001c625  mov     [rsp+110h+lpOverlapped], r10; lpOverlapped
0x18001c62a  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001c62e  lea     r8d, [r10+1]; nNumberOfBytesToWrite
0x18001c632  lea     rdx, [rsp+110h+var_D0]; lpBuffer
0x18001c637  mov     rcx, r14; hFile
0x18001c63a  call    cs:__imp_WriteFile
0x18001c640  xor     r10d, r10d
0x18001c643  test    eax, eax
0x18001c645  jz      loc_18001C729
0x18001c64b  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x18001c64f  jb      loc_18001C731
0x18001c655  inc     dword ptr [rbx+8]
0x18001c658  inc     dword ptr [rbx+4]
0x18001c65b  mov     r8d, [rbx+4]
0x18001c65f  cmp     rdi, r15
0x18001c662  jnb     loc_18001C731
0x18001c668  mov     r11, [rbp+4Fh+var_B8]
0x18001c66c  mov     rsi, [rbp+4Fh+var_90]
0x18001c670  mov     rdx, [rbp+4Fh+var_88]
0x18001c674  mov     ecx, [rbp+4Fh+var_A0]
0x18001c677  jmp     loc_18001C344
0x18001c67c  test    r10, r10
0x18001c67f  jle     short loc_18001C6B4
0x18001c681  lea     rbx, __ImageBase
0x18001c688  movsxd  r8, r9d
0x18001c68b  lea     eax, [r9+rsi]
0x18001c68f  movsxd  rdx, eax
0x18001c692  add     rdx, r14
0x18001c695  mov     rcx, rva __pioinfo[rbx+r12*8]
0x18001c69d  mov     al, [r8+rdi]
0x18001c6a1  mov     [rdx+rcx+3Eh], al
0x18001c6a5  inc     r9d
0x18001c6a8  movsxd  rax, r9d
0x18001c6ab  cmp     rax, r10
0x18001c6ae  jl      short loc_18001C688
0x18001c6b0  mov     rbx, [rbp+4Fh+var_98]
0x18001c6b4  add     [rbx+4], r10d
0x18001c6b8  jmp     short loc_18001C731
0x18001c6ba  mov     r8d, r10d
0x18001c6bd  test    r9, r9
0x18001c6c0  jle     short loc_18001C6EE
0x18001c6c2  lea     rbx, __ImageBase
0x18001c6c9  movsxd  rdx, r8d
0x18001c6cc  mov     rcx, rva __pioinfo[rbx+r12*8]
0x18001c6d4  add     rcx, rdx
0x18001c6d7  mov     al, [rdx+rdi]
0x18001c6da  mov     [rcx+r14+3Eh], al
0x18001c6df  inc     r8d
0x18001c6e2  movsxd  rax, r8d
0x18001c6e5  cmp     rax, r9
0x18001c6e8  jl      short loc_18001C6C9
  ... truncated ...
```
