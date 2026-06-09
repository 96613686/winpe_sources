# write_double_translated_ansi_nolock

- ea: `0x180125510`
- end: `0x1801259a3`
- name: `write_double_translated_ansi_nolock`
- size: `1171`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180125ef4`

## callees

- `0x18010cb40`
- `0x1801181d0`
- `0x180125510`
- `0x18012db70`
- `0x18012e064`
- `0x1801354b4`
- `0x18023a6d0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18012586c`
- `KERNEL32!WriteFile` at `0x1801258b2`
- `KERNEL32!WriteFile` at `0x18012586c`
- `KERNEL32!WriteFile` at `0x1801258b2`
- `KERNEL32!GetLastError` at `0x180125971`
- `KERNEL32!GetLastError` at `0x180125971`
- `KERNEL32!GetConsoleOutputCP` at `0x18012558f`
- `KERNEL32!GetConsoleOutputCP` at `0x18012558f`

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
0x180125510  mov     rax, rsp
0x180125513  push    rbp
0x180125514  push    rsi
0x180125515  push    rdi
0x180125516  push    r12
0x180125518  push    r13
0x18012551a  push    r14
0x18012551c  push    r15
0x18012551e  lea     rbp, [rax-57h]
0x180125522  sub     rsp, 0D0h
0x180125529  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x180125531  mov     [rax+8], rbx
0x180125535  mov     rax, cs:__security_cookie
0x18012553c  xor     rax, rsp
0x18012553f  mov     [rbp+4Fh+var_38], rax
0x180125543  mov     rsi, r8
0x180125546  mov     [rbp+4Fh+var_90], r8
0x18012554a  movsxd  r14, edx
0x18012554d  mov     rbx, rcx
0x180125550  mov     rax, [rbp+4Fh+arg_20]
0x180125554  mov     [rbp+4Fh+var_A8], rax
0x180125558  mov     rax, r14
0x18012555b  mov     r13, r14
0x18012555e  sar     r13, 6
0x180125562  mov     [rbp+4Fh+var_88], r13
0x180125566  lea     rcx, __ImageBase
0x18012556d  and     eax, 3Fh
0x180125570  lea     r15, [rax+rax*8]
0x180125574  mov     rax, rva __pioinfo[rcx+r13*8]
0x18012557c  mov     rax, [rax+r15*8+28h]
0x180125581  mov     [rbp+4Fh+hFile], rax
0x180125585  mov     r12d, r9d
0x180125588  add     r12, r8
0x18012558b  mov     [rbp+4Fh+var_B0], r12
0x18012558f  call    cs:__imp_GetConsoleOutputCP
0x180125595  mov     [rbp+4Fh+var_98], eax
0x180125598  xor     edi, edi
0x18012559a  mov     r10, [rbp+4Fh+var_A8]
0x18012559e  cmp     [r10+28h], dil
0x1801255a2  jnz     short loc_1801255B0
0x1801255a4  mov     rcx, r10; this
0x1801255a7  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1801255ac  mov     r10, [rbp+4Fh+var_A8]
0x1801255b0  mov     rcx, [r10+18h]
0x1801255b4  mov     ecx, [rcx+0Ch]
0x1801255b7  mov     [rbp+4Fh+var_94], ecx
0x1801255ba  xor     eax, eax
0x1801255bc  mov     [rbx], rax
0x1801255bf  mov     [rbx+8], eax
0x1801255c2  cmp     [rbp+4Fh+var_90], r12
0x1801255c6  jnb     loc_180125979
0x1801255cc  mov     r11, r14
0x1801255cf  sar     r11, 6
0x1801255d3  mov     [rbp+4Fh+var_60], r11
0x1801255d7  mov     edx, edi
0x1801255d9  mov     al, [rsi]
0x1801255db  mov     byte ptr [rbp+4Fh+var_C0], al
0x1801255de  mov     [rbp+4Fh+var_BC], edi
0x1801255e1  mov     r12d, 1
0x1801255e7  cmp     ecx, 0FDE9h
0x1801255ed  jnz     loc_180125780
0x1801255f3  mov     edx, edi
0x1801255f5  mov     r14, rdi
0x1801255f8  lea     r12, __ImageBase
0x1801255ff  lea     rcx, ds:3Eh[r15*8]
0x180125607  add     rcx, rva __pioinfo[r12+r11*8]
0x18012560f  cmp     [rcx], dil
0x180125612  jz      short loc_180125622
0x180125614  inc     edx
0x180125616  inc     r14
0x180125619  inc     rcx
0x18012561c  cmp     r14, 5
0x180125620  jl      short loc_18012560F
0x180125622  test    r14, r14
0x180125625  jle     loc_180125716
0x18012562b  mov     rax, rva __pioinfo[r12+r13*8]
0x180125633  movzx   ecx, byte ptr [rax+r15*8+3Eh]
0x180125639  movsx   r12d, byte ptr [rcx+r12+302560h]
0x180125642  inc     r12d
0x180125645  mov     eax, r12d
0x180125648  sub     eax, edx
0x18012564a  mov     dword ptr [rbp+4Fh+var_A0], eax
0x18012564d  mov     r8, [rbp+4Fh+var_B0]
0x180125651  sub     r8, rsi
0x180125654  movsxd  r9, eax
0x180125657  cmp     r9, r8
0x18012565a  jg      loc_1801258ED
0x180125660  mov     rcx, rdi
0x180125663  lea     r8, __ImageBase
0x18012566a  lea     rdx, ds:3Eh[r15*8]
0x180125672  add     rdx, rva __pioinfo[r8+r11*8]
0x18012567a  mov     al, [rdx]
0x18012567c  mov     [rbp+rcx+4Fh+var_50], al
0x180125680  inc     rcx
0x180125683  inc     rdx
0x180125686  cmp     rcx, r14
0x180125689  jl      short loc_18012567A
0x18012568b  test    r9, r9
0x18012568e  jle     short loc_1801256AD
0x180125690  lea     rcx, [rbp+4Fh+var_50]
0x180125694  add     rcx, r14; void *
0x180125697  mov     r8, r9; Size
0x18012569a  mov     rdx, rsi; Src
0x18012569d  call    memmove
0x1801256a2  mov     r10, [rbp+4Fh+var_A8]
0x1801256a6  lea     r8, __ImageBase
0x1801256ad  mov     rdx, rdi
0x1801256b0  lea     rcx, [rdx+r15*8]
0x1801256b4  mov     rax, rva __pioinfo[r8+r13*8]
0x1801256bc  mov     [rcx+rax+3Eh], dil
0x1801256c1  inc     rdx
0x1801256c4  cmp     rdx, r14
0x1801256c7  jl      short loc_1801256B0
0x1801256c9  mov     [rbp+4Fh+var_80], rdi
0x1801256cd  lea     rax, [rbp+4Fh+var_50]
0x1801256d1  mov     qword ptr [rbp+4Fh+var_78], rax
0x1801256d5  mov     eax, edi
0x1801256d7  cmp     r12d, 4
0x1801256db  setz    al
0x1801256de  inc     eax
0x1801256e0  mov     r12d, eax
0x1801256e3  mov     r8d, eax; char **
0x1801256e6  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x1801256eb  lea     r9, [rbp+4Fh+var_80]; unsigned __int64
0x1801256ef  lea     rdx, [rbp+4Fh+var_78]; wchar_t *
0x1801256f3  lea     rcx, [rbp+4Fh+var_BC]; this
0x1801256f7  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x1801256fc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180125700  jz      loc_180125979
0x180125706  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x180125709  dec     eax
0x18012570b  movsxd  rcx, eax
0x18012570e  add     rsi, rcx
0x180125711  jmp     loc_180125818
0x180125716  movzx   eax, byte ptr [rsi]
0x180125719  movsx   r13, byte ptr [rax+r12+302560h]
0x180125722  lea     ecx, [r13+1]
0x180125726  mov     r9, [rbp+4Fh+var_B0]
0x18012572a  sub     r9, rsi
0x18012572d  movsxd  rax, ecx
0x180125730  cmp     rax, r9
0x180125733  jg      loc_180125923
0x180125739  mov     [rbp+4Fh+var_A0], rdi
0x18012573d  mov     qword ptr [rbp+4Fh+var_70], rsi
0x180125741  mov     eax, edi
0x180125743  cmp     ecx, 4
0x180125746  setz    al
0x180125749  inc     eax
0x18012574b  mov     r14d, eax
0x18012574e  mov     r8d, eax; char **
0x180125751  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x180125756  lea     r9, [rbp+4Fh+var_A0]; unsigned __int64
0x18012575a  lea     rdx, [rbp+4Fh+var_70]; wchar_t *
0x18012575e  lea     rcx, [rbp+4Fh+var_BC]; this
0x180125762  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180125767  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18012576b  jz      loc_180125979
0x180125771  add     rsi, r13
0x180125774  mov     r12d, r14d
0x180125777  mov     r13, [rbp+4Fh+var_88]
0x18012577b  jmp     loc_180125818
0x180125780  lea     r11, __ImageBase
0x180125787  mov     r8, rva __pioinfo[r11+r13*8]
0x18012578f  mov     cl, [r8+r15*8+3Dh]
0x180125794  test    cl, 4
0x180125797  jz      short loc_1801257BA
0x180125799  mov     al, [r8+r15*8+3Eh]
0x18012579e  mov     [rbp+4Fh+var_48], al
0x1801257a1  mov     al, [rsi]
0x1801257a3  mov     [rbp+4Fh+var_47], al
0x1801257a6  and     cl, 0FBh
0x1801257a9  mov     [r8+r15*8+3Dh], cl
0x1801257ae  mov     r8d, 2
0x1801257b4  lea     rdx, [rbp+4Fh+var_48]
0x1801257b8  jmp     short loc_180125803
0x1801257ba  movzx   r9d, byte ptr [rsi]
0x1801257be  mov     rax, [r10+18h]
0x1801257c2  mov     rcx, [rax]
0x1801257c5  cmp     [rcx+r9*2], di
0x1801257ca  jge     short loc_1801257FD
0x1801257cc  lea     r14, [rsi+1]
0x1801257d0  cmp     r14, [rbp+4Fh+var_B0]
0x1801257d4  jnb     loc_180125956
0x1801257da  mov     r9, r10; __crt_cached_ptd_host *
0x1801257dd  mov     r8d, 2; char *
0x1801257e3  mov     rdx, rsi; wchar_t *
0x1801257e6  lea     rcx, [rbp+4Fh+var_BC]; this
0x1801257ea  call    _mbtowc_internal
0x1801257ef  cmp     eax, 0FFFFFFFFh
0x1801257f2  jz      loc_180125979
0x1801257f8  mov     rsi, r14
0x1801257fb  jmp     short loc_180125818
0x1801257fd  mov     r8, r12; char *
0x180125800  mov     rdx, rsi; wchar_t *
0x180125803  mov     r9, r10; __crt_cached_ptd_host *
0x180125806  lea     rcx, [rbp+4Fh+var_BC]; this
0x18012580a  call    _mbtowc_internal
0x18012580f  cmp     eax, 0FFFFFFFFh
0x180125812  jz      loc_180125979
0x180125818  inc     rsi
0x18012581b  mov     [rsp+38h], rdi
0x180125820  mov     [rsp+100h+var_D0], rdi
0x180125825  mov     dword ptr [rsp+100h+var_D8], 5
0x18012582d  lea     rax, [rbp+4Fh+Buffer]
0x180125831  mov     [rsp+100h+lpOverlapped], rax
0x180125836  mov     r9d, r12d
0x180125839  lea     r8, [rbp+4Fh+var_BC]
0x18012583d  xor     edx, edx
0x18012583f  mov     ecx, [rbp+4Fh+var_98]
0x180125842  call    __acrt_WideCharToMultiByte
0x180125847  mov     r14d, eax
0x18012584a  test    eax, eax
0x18012584c  jz      loc_180125979
0x180125852  mov     [rbp+4Fh+NumberOfBytesWritten], edi
0x180125855  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x18012585a  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18012585e  mov     r8d, eax; nNumberOfBytesToWrite
0x180125861  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x180125865  mov     r12, [rbp+4Fh+hFile]
0x180125869  mov     rcx, r12; hFile
0x18012586c  call    cs:__imp_WriteFile
0x180125872  test    eax, eax
0x180125874  jz      loc_180125971
0x18012587a  mov     edx, [rbx+8]
0x18012587d  sub     edx, dword ptr [rbp+4Fh+var_90]
0x180125880  add     edx, esi
0x180125882  mov     [rbx+4], edx
0x180125885  cmp     [rbp+4Fh+NumberOfBytesWritten], r14d
0x180125889  jb      loc_180125979
0x18012588f  cmp     byte ptr [rbp+4Fh+var_C0], 0Ah
0x180125893  jnz     short loc_1801258D3
0x180125895  mov     eax, 0Dh
0x18012589a  mov     [rbp+4Fh+var_C0], ax
0x18012589e  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x1801258a3  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801258a7  lea     r8d, [rax-0Ch]; nNumberOfBytesToWrite
0x1801258ab  lea     rdx, [rbp+4Fh+var_C0]; lpBuffer
0x1801258af  mov     rcx, r12; hFile
0x1801258b2  call    cs:__imp_WriteFile
0x1801258b8  test    eax, eax
0x1801258ba  jz      loc_180125971
0x1801258c0  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x1801258c4  jb      loc_180125979
0x1801258ca  inc     dword ptr [rbx+8]
0x1801258cd  inc     dword ptr [rbx+4]
0x1801258d0  mov     edx, [rbx+4]
0x1801258d3  cmp     rsi, [rbp+4Fh+var_B0]
0x1801258d7  jnb     loc_180125979
0x1801258dd  mov     r10, [rbp+4Fh+var_A8]
0x1801258e1  mov     r11, [rbp+4Fh+var_60]
0x1801258e5  mov     ecx, [rbp+4Fh+var_94]
0x1801258e8  jmp     loc_1801255D9
0x1801258ed  test    r8, r8
0x1801258f0  jle     short loc_18012591D
0x1801258f2  sub     rsi, r14
0x1801258f5  lea     r9, __ImageBase
0x1801258fc  lea     rdx, [r14+r15*8]
0x180125900  mov     rcx, rva __pioinfo[r9+r13*8]
0x180125908  mov     al, [rsi+r14]
0x18012590c  mov     [rdx+rcx+3Eh], al
0x180125910  inc     edi
0x180125912  inc     r14
0x180125915  movsxd  rax, edi
0x180125918  cmp     rax, r8
0x18012591b  jl      short loc_1801258FC
0x18012591d  add     [rbx+4], r8d
0x180125921  jmp     short loc_180125979
0x180125923  test    r9, r9
0x180125926  jle     short loc_180125950
0x180125928  mov     r8, rdi
0x18012592b  mov     r10, [rbp+4Fh+var_88]
0x18012592f  lea     rdx, [r8+r15*8]
0x180125933  mov     rcx, rva __pioinfo[r12+r10*8]
0x18012593b  mov     al, [r8+rsi]
0x18012593f  mov     [rdx+rcx+3Eh], al
0x180125943  inc     edi
0x180125945  inc     r8
0x180125948  movsxd  rax, edi
0x18012594b  cmp     rax, r9
0x18012594e  jl      short loc_18012592F
0x180125950  add     [rbx+4], r9d
0x180125954  jmp     short loc_180125979
0x180125956  mov     [r8+r15*8+3Eh], r9b
0x18012595b  mov     rax, rva __pioinfo[r11+r13*8]
0x180125963  or      byte ptr [rax+r15*8+3Dh], 4
0x180125969  lea     eax, [rdx+1]
0x18012596c  mov     [rbx+4], eax
0x18012596f  jmp     short loc_180125979
0x180125971  call    cs:__imp_GetLastError
0x180125977  mov     [rbx], eax
0x180125979  mov     rax, rbx
0x18012597c  mov     rcx, [rbp+4Fh+var_38]
0x180125980  xor     rcx, rsp; StackCookie
0x180125983  call    __security_check_cookie
0x180125988  mov     rbx, [rsp+100h+arg_0]
0x180125990  add     rsp, 0D0h
0x180125997  pop     r15
0x180125999  pop     r14
0x18012599b  pop     r13
0x18012599d  pop     r12
  ... truncated ...
```
