# write_double_translated_ansi_nolock

- ea: `0x18035bad8`
- end: `0x18035bf6b`
- name: `write_double_translated_ansi_nolock`
- size: `1171`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18035c424`

## callees

- `0x18032f0b0`
- `0x180343580`
- `0x180357810`
- `0x180357d10`
- `0x180359e98`
- `0x18035bad8`
- `0x180375cc0`

## import_xrefs

- `KERNEL32!GetConsoleOutputCP` at `0x18035bb57`
- `KERNEL32!GetConsoleOutputCP` at `0x18035bb57`
- `KERNEL32!GetLastError` at `0x18035bf39`
- `KERNEL32!GetLastError` at `0x18035bf39`
- `KERNEL32!WriteFile` at `0x18035be34`
- `KERNEL32!WriteFile` at `0x18035be7a`
- `KERNEL32!WriteFile` at `0x18035be34`
- `KERNEL32!WriteFile` at `0x18035be7a`

## pseudocode

```c
__int64 __fastcall write_double_translated_ansi_nolock(__int64 a1, int a2, _BYTE *a3, int a4, __int64 a5)
{
  _BYTE *v5; // rsi
  __int64 v6; // r14
  __int64 v8; // r13
  __int64 v9; // r15
  unsigned __int64 v10; // r12
  int v11; // edi
  struct _Mbstatet *v12; // r10
  int v13; // ecx
  __int64 v14; // r11
  int v15; // edx
  unsigned int v16; // r12d
  int v17; // edx
  __int64 v18; // r14
  _BYTE *v19; // rcx
  int v20; // r12d
  __int64 v21; // r8
  signed __int64 v22; // r9
  __int64 v23; // rcx
  _BYTE *v24; // rdx
  __int64 i; // rdx
  __int64 v26; // r13
  __int64 v27; // r9
  unsigned int v28; // r14d
  __int64 v29; // r8
  char v30; // cl
  __int64 v31; // r8
  wchar_t *v32; // rdx
  __int64 v33; // r9
  DWORD v34; // eax
  DWORD v35; // r14d
  HANDLE v36; // r12
  _BYTE *v37; // rsi
  __int64 v38; // r8
  __int64 v39; // r10
  struct __crt_cached_ptd_host *v41; // [rsp+30h] [rbp-89h]
  __int16 v42[2]; // [rsp+48h] [rbp-71h] BYREF
  int v43; // [rsp+4Ch] [rbp-6Dh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int64 v45; // [rsp+58h] [rbp-61h]
  struct _Mbstatet *v46; // [rsp+60h] [rbp-59h]
  unsigned __int64 v47; // [rsp+68h] [rbp-51h] BYREF
  UINT ConsoleOutputCP; // [rsp+70h] [rbp-49h]
  int v49; // [rsp+74h] [rbp-45h]
  _BYTE *v50; // [rsp+78h] [rbp-41h]
  __int64 v51; // [rsp+80h] [rbp-39h]
  unsigned __int64 v52; // [rsp+88h] [rbp-31h] BYREF
  wchar_t v53[4]; // [rsp+90h] [rbp-29h] BYREF
  wchar_t v54[4]; // [rsp+98h] [rbp-21h] BYREF
  HANDLE hFile; // [rsp+A0h] [rbp-19h]
  __int64 v56; // [rsp+A8h] [rbp-11h]
  __int64 v57; // [rsp+B0h] [rbp-9h]
  _BYTE v58[8]; // [rsp+B8h] [rbp-1h] BYREF
  _BYTE v59[8]; // [rsp+C0h] [rbp+7h] BYREF
  char Buffer[8]; // [rsp+C8h] [rbp+Fh] BYREF

  v57 = -2;
  v5 = a3;
  v50 = a3;
  v6 = a2;
  v46 = (struct _Mbstatet *)a5;
  v8 = (__int64)a2 >> 6;
  v51 = v8;
  v9 = 9LL * (a2 & 0x3F);
  hFile = *(HANDLE *)(_pioinfo[v8] + 72LL * (a2 & 0x3F) + 40);
  v10 = (unsigned __int64)&a3[a4];
  v45 = v10;
  ConsoleOutputCP = GetConsoleOutputCP();
  v11 = 0;
  v12 = (struct _Mbstatet *)a5;
  if ( !*(_BYTE *)(a5 + 40) )
  {
    __crt_cached_ptd_host::update_locale_slow((__crt_cached_ptd_host *)v46);
    v12 = v46;
  }
  v13 = *(_DWORD *)(*(_QWORD *)&v12[3] + 12LL);
  v49 = v13;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)v50 < v10 )
  {
    v14 = v6 >> 6;
    v56 = v6 >> 6;
    v15 = 0;
    while ( 1 )
    {
      LOBYTE(v42[0]) = *v5;
      v43 = 0;
      v16 = 1;
      if ( v13 == 65001 )
      {
        v17 = 0;
        v18 = 0;
        v19 = (_BYTE *)(_pioinfo[v14] + 8 * v9 + 62);
        do
        {
          if ( !*v19 )
            break;
          ++v17;
          ++v18;
          ++v19;
        }
        while ( v18 < 5 );
        if ( v18 <= 0 )
        {
          v26 = *((char *)lookuptrailbytes + (unsigned __int8)*v5);
          v27 = v45 - (_QWORD)v5;
          if ( (int)v26 + 1 > (__int64)(v45 - (_QWORD)v5) )
          {
            if ( v27 > 0 )
            {
              v38 = 0;
              v39 = v51;
              do
              {
                *(_BYTE *)(v38 + 8 * v9 + _pioinfo[v39] + 62) = v5[v38];
                ++v11;
                ++v38;
              }
              while ( v11 < v27 );
            }
            *(_DWORD *)(a1 + 4) += v27;
            return a1;
          }
          v47 = 0;
          *(_QWORD *)v54 = v5;
          v28 = ((_DWORD)v26 == 3) + 1;
          if ( __crt_mbstring::__mbsrtowcs_utf8(
                 (__crt_mbstring *)&v43,
                 v54,
                 (const char **)v28,
                 (unsigned __int64)&v47,
                 v12,
                 v41) == -1 )
            return a1;
          v5 += v26;
          v16 = v28;
          v8 = v51;
        }
        else
        {
          v20 = *((char *)lookuptrailbytes + *(unsigned __int8 *)(_pioinfo[v8] + 8 * v9 + 62)) + 1;
          LODWORD(v47) = v20 - v17;
          v21 = v45 - (_QWORD)v5;
          v22 = v20 - v17;
          if ( v22 > (__int64)(v45 - (_QWORD)v5) )
          {
            if ( v21 > 0 )
            {
              v37 = &v5[-v18];
              do
              {
                *(_BYTE *)(v18 + 8 * v9 + _pioinfo[v8] + 62) = v37[v18];
                ++v11;
                ++v18;
              }
              while ( v11 < v21 );
            }
            *(_DWORD *)(a1 + 4) += v21;
            return a1;
          }
          v23 = 0;
          v24 = (_BYTE *)(_pioinfo[v14] + 8 * v9 + 62);
          do
            v58[v23++] = *v24++;
          while ( v23 < v18 );
          if ( v22 > 0 )
          {
            memmove(&v58[v18], v5, v22);
            v12 = v46;
          }
          for ( i = 0; i < v18; ++i )
            *(_BYTE *)(i + 8 * v9 + _pioinfo[v8] + 62) = 0;
          v52 = 0;
          *(_QWORD *)v53 = v58;
          v16 = (v20 == 4) + 1;
          if ( __crt_mbstring::__mbsrtowcs_utf8(
                 (__crt_mbstring *)&v43,
                 v53,
                 (const char **)v16,
                 (unsigned __int64)&v52,
                 v12,
                 v41) == -1 )
            return a1;
          v5 += (int)v47 - 1;
        }
      }
      else
      {
        v29 = _pioinfo[v8];
        v30 = *(_BYTE *)(v29 + 8 * v9 + 61);
        if ( (v30 & 4) != 0 )
        {
          v59[0] = *(_BYTE *)(v29 + 8 * v9 + 62);
          v59[1] = *v5;
          *(_BYTE *)(v29 + 8 * v9 + 61) = v30 & 0xFB;
          v31 = 2;
          v32 = (wchar_t *)v59;
          goto LABEL_29;
        }
        v33 = (unsigned __int8)*v5;
        if ( *(__int16 *)(**(_QWORD **)&v12[3] + 2 * v33) >= 0 )
        {
          v31 = 1;
          v32 = (wchar_t *)v5;
LABEL_29:
          if ( (unsigned int)mbtowc_internal((__crt_mbstring *)&v43, v32, (char *)v31, (__crt_cached_ptd_host *)v12) == -1 )
            return a1;
          goto LABEL_30;
        }
        if ( (unsigned __int64)(v5 + 1) >= v45 )
        {
          *(_BYTE *)(v29 + 8 * v9 + 62) = v33;
          *(_BYTE *)(_pioinfo[v8] + 8 * v9 + 61) |= 4u;
          *(_DWORD *)(a1 + 4) = v15 + 1;
          return a1;
        }
        if ( (unsigned int)mbtowc_internal(
                             (__crt_mbstring *)&v43,
                             (wchar_t *)v5,
                             (char *)2,
                             (__crt_cached_ptd_host *)v12) == -1 )
          return a1;
        ++v5;
      }
LABEL_30:
      ++v5;
      v34 = _acrt_WideCharToMultiByte(ConsoleOutputCP, 0, (unsigned int)&v43, v16, (unsigned int)Buffer, 5, 0, 0);
      v35 = v34;
      if ( !v34 )
        return a1;
      NumberOfBytesWritten = 0;
      v36 = hFile;
      if ( !WriteFile(hFile, Buffer, v34, &NumberOfBytesWritten, 0) )
      {
LABEL_48:
        *(_DWORD *)a1 = GetLastError();
        return a1;
      }
      v15 = (_DWORD)v5 + *(_DWORD *)(a1 + 8) - (_DWORD)v50;
      *(_DWORD *)(a1 + 4) = v15;
      if ( NumberOfBytesWritten < v35 )
        return a1;
      if ( LOBYTE(v42[0]) == 10 )
      {
        v42[0] = 13;
        if ( !WriteFile(v36, v42, 1u, &NumberOfBytesWritten, 0) )
          goto LABEL_48;
        if ( !NumberOfBytesWritten )
          return a1;
        ++*(_DWORD *)(a1 + 8);
        v15 = ++*(_DWORD *)(a1 + 4);
      }
      if ( (unsigned __int64)v5 >= v45 )
        return a1;
      v12 = v46;
      v14 = v56;
      v13 = v49;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18035bad8  mov     rax, rsp
0x18035badb  push    rbp
0x18035badc  push    rsi
0x18035badd  push    rdi
0x18035bade  push    r12
0x18035bae0  push    r13
0x18035bae2  push    r14
0x18035bae4  push    r15
0x18035bae6  lea     rbp, [rax-57h]
0x18035baea  sub     rsp, 0D0h
0x18035baf1  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x18035baf9  mov     [rax+8], rbx
0x18035bafd  mov     rax, cs:__security_cookie
0x18035bb04  xor     rax, rsp
0x18035bb07  mov     [rbp+4Fh+var_38], rax
0x18035bb0b  mov     rsi, r8
0x18035bb0e  mov     [rbp+4Fh+var_90], r8
0x18035bb12  movsxd  r14, edx
0x18035bb15  mov     rbx, rcx
0x18035bb18  mov     rax, [rbp+4Fh+arg_20]
0x18035bb1c  mov     [rbp+4Fh+var_A8], rax
0x18035bb20  mov     rax, r14
0x18035bb23  mov     r13, r14
0x18035bb26  sar     r13, 6
0x18035bb2a  mov     [rbp+4Fh+var_88], r13
0x18035bb2e  lea     rcx, __ImageBase
0x18035bb35  and     eax, 3Fh
0x18035bb38  lea     r15, [rax+rax*8]
0x18035bb3c  mov     rax, rva __pioinfo[rcx+r13*8]
0x18035bb44  mov     rax, [rax+r15*8+28h]
0x18035bb49  mov     [rbp+4Fh+hFile], rax
0x18035bb4d  mov     r12d, r9d
0x18035bb50  add     r12, r8
0x18035bb53  mov     [rbp+4Fh+var_B0], r12
0x18035bb57  call    cs:__imp_GetConsoleOutputCP
0x18035bb5d  mov     [rbp+4Fh+var_98], eax
0x18035bb60  xor     edi, edi
0x18035bb62  mov     r10, [rbp+4Fh+var_A8]
0x18035bb66  cmp     [r10+28h], dil
0x18035bb6a  jnz     short loc_18035BB78
0x18035bb6c  mov     rcx, r10; this
0x18035bb6f  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18035bb74  mov     r10, [rbp+4Fh+var_A8]
0x18035bb78  mov     rcx, [r10+18h]
0x18035bb7c  mov     ecx, [rcx+0Ch]
0x18035bb7f  mov     [rbp+4Fh+var_94], ecx
0x18035bb82  xor     eax, eax
0x18035bb84  mov     [rbx], rax
0x18035bb87  mov     [rbx+8], eax
0x18035bb8a  cmp     [rbp+4Fh+var_90], r12
0x18035bb8e  jnb     loc_18035BF41
0x18035bb94  mov     r11, r14
0x18035bb97  sar     r11, 6
0x18035bb9b  mov     [rbp+4Fh+var_60], r11
0x18035bb9f  mov     edx, edi
0x18035bba1  mov     al, [rsi]
0x18035bba3  mov     byte ptr [rbp+4Fh+var_C0], al
0x18035bba6  mov     [rbp+4Fh+var_BC], edi
0x18035bba9  mov     r12d, 1
0x18035bbaf  cmp     ecx, 0FDE9h
0x18035bbb5  jnz     loc_18035BD48
0x18035bbbb  mov     edx, edi
0x18035bbbd  mov     r14, rdi
0x18035bbc0  lea     r12, __ImageBase
0x18035bbc7  lea     rcx, ds:3Eh[r15*8]
0x18035bbcf  add     rcx, rva __pioinfo[r12+r11*8]
0x18035bbd7  cmp     [rcx], dil
0x18035bbda  jz      short loc_18035BBEA
0x18035bbdc  inc     edx
0x18035bbde  inc     r14
0x18035bbe1  inc     rcx
0x18035bbe4  cmp     r14, 5
0x18035bbe8  jl      short loc_18035BBD7
0x18035bbea  test    r14, r14
0x18035bbed  jle     loc_18035BCDE
0x18035bbf3  mov     rax, rva __pioinfo[r12+r13*8]
0x18035bbfb  movzx   ecx, byte ptr [rax+r15*8+3Eh]
0x18035bc01  movsx   r12d, byte ptr [rcx+r12+500BC0h]
0x18035bc0a  inc     r12d
0x18035bc0d  mov     eax, r12d
0x18035bc10  sub     eax, edx
0x18035bc12  mov     dword ptr [rbp+4Fh+var_A0], eax
0x18035bc15  mov     r8, [rbp+4Fh+var_B0]
0x18035bc19  sub     r8, rsi
0x18035bc1c  movsxd  r9, eax
0x18035bc1f  cmp     r9, r8
0x18035bc22  jg      loc_18035BEB5
0x18035bc28  mov     rcx, rdi
0x18035bc2b  lea     r8, __ImageBase
0x18035bc32  lea     rdx, ds:3Eh[r15*8]
0x18035bc3a  add     rdx, rva __pioinfo[r8+r11*8]
0x18035bc42  mov     al, [rdx]
0x18035bc44  mov     [rbp+rcx+4Fh+var_50], al
0x18035bc48  inc     rcx
0x18035bc4b  inc     rdx
0x18035bc4e  cmp     rcx, r14
0x18035bc51  jl      short loc_18035BC42
0x18035bc53  test    r9, r9
0x18035bc56  jle     short loc_18035BC75
0x18035bc58  lea     rcx, [rbp+4Fh+var_50]
0x18035bc5c  add     rcx, r14; void *
0x18035bc5f  mov     r8, r9; Size
0x18035bc62  mov     rdx, rsi; Src
0x18035bc65  call    memmove
0x18035bc6a  mov     r10, [rbp+4Fh+var_A8]
0x18035bc6e  lea     r8, __ImageBase
0x18035bc75  mov     rdx, rdi
0x18035bc78  lea     rcx, [rdx+r15*8]
0x18035bc7c  mov     rax, rva __pioinfo[r8+r13*8]
0x18035bc84  mov     [rcx+rax+3Eh], dil
0x18035bc89  inc     rdx
0x18035bc8c  cmp     rdx, r14
0x18035bc8f  jl      short loc_18035BC78
0x18035bc91  mov     [rbp+4Fh+var_80], rdi
0x18035bc95  lea     rax, [rbp+4Fh+var_50]
0x18035bc99  mov     qword ptr [rbp+4Fh+var_78], rax
0x18035bc9d  mov     eax, edi
0x18035bc9f  cmp     r12d, 4
0x18035bca3  setz    al
0x18035bca6  inc     eax
0x18035bca8  mov     r12d, eax
0x18035bcab  mov     r8d, eax; char **
0x18035bcae  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x18035bcb3  lea     r9, [rbp+4Fh+var_80]; unsigned __int64
0x18035bcb7  lea     rdx, [rbp+4Fh+var_78]; wchar_t *
0x18035bcbb  lea     rcx, [rbp+4Fh+var_BC]; this
0x18035bcbf  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18035bcc4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18035bcc8  jz      loc_18035BF41
0x18035bcce  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x18035bcd1  dec     eax
0x18035bcd3  movsxd  rcx, eax
0x18035bcd6  add     rsi, rcx
0x18035bcd9  jmp     loc_18035BDE0
0x18035bcde  movzx   eax, byte ptr [rsi]
0x18035bce1  movsx   r13, byte ptr [rax+r12+500BC0h]
0x18035bcea  lea     ecx, [r13+1]
0x18035bcee  mov     r9, [rbp+4Fh+var_B0]
0x18035bcf2  sub     r9, rsi
0x18035bcf5  movsxd  rax, ecx
0x18035bcf8  cmp     rax, r9
0x18035bcfb  jg      loc_18035BEEB
0x18035bd01  mov     [rbp+4Fh+var_A0], rdi
0x18035bd05  mov     qword ptr [rbp+4Fh+var_70], rsi
0x18035bd09  mov     eax, edi
0x18035bd0b  cmp     ecx, 4
0x18035bd0e  setz    al
0x18035bd11  inc     eax
0x18035bd13  mov     r14d, eax
0x18035bd16  mov     r8d, eax; char **
0x18035bd19  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x18035bd1e  lea     r9, [rbp+4Fh+var_A0]; unsigned __int64
0x18035bd22  lea     rdx, [rbp+4Fh+var_70]; wchar_t *
0x18035bd26  lea     rcx, [rbp+4Fh+var_BC]; this
0x18035bd2a  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18035bd2f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18035bd33  jz      loc_18035BF41
0x18035bd39  add     rsi, r13
0x18035bd3c  mov     r12d, r14d
0x18035bd3f  mov     r13, [rbp+4Fh+var_88]
0x18035bd43  jmp     loc_18035BDE0
0x18035bd48  lea     r11, __ImageBase
0x18035bd4f  mov     r8, rva __pioinfo[r11+r13*8]
0x18035bd57  mov     cl, [r8+r15*8+3Dh]
0x18035bd5c  test    cl, 4
0x18035bd5f  jz      short loc_18035BD82
0x18035bd61  mov     al, [r8+r15*8+3Eh]
0x18035bd66  mov     [rbp+4Fh+var_48], al
0x18035bd69  mov     al, [rsi]
0x18035bd6b  mov     [rbp+4Fh+var_47], al
0x18035bd6e  and     cl, 0FBh
0x18035bd71  mov     [r8+r15*8+3Dh], cl
0x18035bd76  mov     r8d, 2
0x18035bd7c  lea     rdx, [rbp+4Fh+var_48]
0x18035bd80  jmp     short loc_18035BDCB
0x18035bd82  movzx   r9d, byte ptr [rsi]
0x18035bd86  mov     rax, [r10+18h]
0x18035bd8a  mov     rcx, [rax]
0x18035bd8d  cmp     [rcx+r9*2], di
0x18035bd92  jge     short loc_18035BDC5
0x18035bd94  lea     r14, [rsi+1]
0x18035bd98  cmp     r14, [rbp+4Fh+var_B0]
0x18035bd9c  jnb     loc_18035BF1E
0x18035bda2  mov     r9, r10; __crt_cached_ptd_host *
0x18035bda5  mov     r8d, 2; char *
0x18035bdab  mov     rdx, rsi; wchar_t *
0x18035bdae  lea     rcx, [rbp+4Fh+var_BC]; this
0x18035bdb2  call    _mbtowc_internal
0x18035bdb7  cmp     eax, 0FFFFFFFFh
0x18035bdba  jz      loc_18035BF41
0x18035bdc0  mov     rsi, r14
0x18035bdc3  jmp     short loc_18035BDE0
0x18035bdc5  mov     r8, r12; char *
0x18035bdc8  mov     rdx, rsi; wchar_t *
0x18035bdcb  mov     r9, r10; __crt_cached_ptd_host *
0x18035bdce  lea     rcx, [rbp+4Fh+var_BC]; this
0x18035bdd2  call    _mbtowc_internal
0x18035bdd7  cmp     eax, 0FFFFFFFFh
0x18035bdda  jz      loc_18035BF41
0x18035bde0  inc     rsi
0x18035bde3  mov     [rsp+38h], rdi
0x18035bde8  mov     [rsp+100h+var_D0], rdi
0x18035bded  mov     dword ptr [rsp+100h+var_D8], 5
0x18035bdf5  lea     rax, [rbp+4Fh+Buffer]
0x18035bdf9  mov     [rsp+100h+lpOverlapped], rax
0x18035bdfe  mov     r9d, r12d
0x18035be01  lea     r8, [rbp+4Fh+var_BC]
0x18035be05  xor     edx, edx
0x18035be07  mov     ecx, [rbp+4Fh+var_98]
0x18035be0a  call    __acrt_WideCharToMultiByte
0x18035be0f  mov     r14d, eax
0x18035be12  test    eax, eax
0x18035be14  jz      loc_18035BF41
0x18035be1a  mov     [rbp+4Fh+NumberOfBytesWritten], edi
0x18035be1d  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x18035be22  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18035be26  mov     r8d, eax; nNumberOfBytesToWrite
0x18035be29  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x18035be2d  mov     r12, [rbp+4Fh+hFile]
0x18035be31  mov     rcx, r12; hFile
0x18035be34  call    cs:__imp_WriteFile
0x18035be3a  test    eax, eax
0x18035be3c  jz      loc_18035BF39
0x18035be42  mov     edx, [rbx+8]
0x18035be45  sub     edx, dword ptr [rbp+4Fh+var_90]
0x18035be48  add     edx, esi
0x18035be4a  mov     [rbx+4], edx
0x18035be4d  cmp     [rbp+4Fh+NumberOfBytesWritten], r14d
0x18035be51  jb      loc_18035BF41
0x18035be57  cmp     byte ptr [rbp+4Fh+var_C0], 0Ah
0x18035be5b  jnz     short loc_18035BE9B
0x18035be5d  mov     eax, 0Dh
0x18035be62  mov     [rbp+4Fh+var_C0], ax
0x18035be66  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x18035be6b  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18035be6f  lea     r8d, [rax-0Ch]; nNumberOfBytesToWrite
0x18035be73  lea     rdx, [rbp+4Fh+var_C0]; lpBuffer
0x18035be77  mov     rcx, r12; hFile
0x18035be7a  call    cs:__imp_WriteFile
0x18035be80  test    eax, eax
0x18035be82  jz      loc_18035BF39
0x18035be88  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x18035be8c  jb      loc_18035BF41
0x18035be92  inc     dword ptr [rbx+8]
0x18035be95  inc     dword ptr [rbx+4]
0x18035be98  mov     edx, [rbx+4]
0x18035be9b  cmp     rsi, [rbp+4Fh+var_B0]
0x18035be9f  jnb     loc_18035BF41
0x18035bea5  mov     r10, [rbp+4Fh+var_A8]
0x18035bea9  mov     r11, [rbp+4Fh+var_60]
0x18035bead  mov     ecx, [rbp+4Fh+var_94]
0x18035beb0  jmp     loc_18035BBA1
0x18035beb5  test    r8, r8
0x18035beb8  jle     short loc_18035BEE5
0x18035beba  sub     rsi, r14
0x18035bebd  lea     r9, __ImageBase
0x18035bec4  lea     rdx, [r14+r15*8]
0x18035bec8  mov     rcx, rva __pioinfo[r9+r13*8]
0x18035bed0  mov     al, [rsi+r14]
0x18035bed4  mov     [rdx+rcx+3Eh], al
0x18035bed8  inc     edi
0x18035beda  inc     r14
0x18035bedd  movsxd  rax, edi
0x18035bee0  cmp     rax, r8
0x18035bee3  jl      short loc_18035BEC4
0x18035bee5  add     [rbx+4], r8d
0x18035bee9  jmp     short loc_18035BF41
0x18035beeb  test    r9, r9
0x18035beee  jle     short loc_18035BF18
0x18035bef0  mov     r8, rdi
0x18035bef3  mov     r10, [rbp+4Fh+var_88]
0x18035bef7  lea     rdx, [r8+r15*8]
0x18035befb  mov     rcx, rva __pioinfo[r12+r10*8]
0x18035bf03  mov     al, [r8+rsi]
0x18035bf07  mov     [rdx+rcx+3Eh], al
0x18035bf0b  inc     edi
0x18035bf0d  inc     r8
0x18035bf10  movsxd  rax, edi
0x18035bf13  cmp     rax, r9
0x18035bf16  jl      short loc_18035BEF7
0x18035bf18  add     [rbx+4], r9d
0x18035bf1c  jmp     short loc_18035BF41
0x18035bf1e  mov     [r8+r15*8+3Eh], r9b
0x18035bf23  mov     rax, rva __pioinfo[r11+r13*8]
0x18035bf2b  or      byte ptr [rax+r15*8+3Dh], 4
0x18035bf31  lea     eax, [rdx+1]
0x18035bf34  mov     [rbx+4], eax
0x18035bf37  jmp     short loc_18035BF41
0x18035bf39  call    cs:__imp_GetLastError
0x18035bf3f  mov     [rbx], eax
0x18035bf41  mov     rax, rbx
0x18035bf44  mov     rcx, [rbp+4Fh+var_38]
0x18035bf48  xor     rcx, rsp; StackCookie
0x18035bf4b  call    __security_check_cookie
0x18035bf50  mov     rbx, [rsp+100h+arg_0]
0x18035bf58  add     rsp, 0D0h
0x18035bf5f  pop     r15
0x18035bf61  pop     r14
0x18035bf63  pop     r13
0x18035bf65  pop     r12
  ... truncated ...
```
