# write_double_translated_ansi_nolock(int,char const * const,uint)

- ea: `0x1815fcbd`
- end: `0x18160069`
- name: `?write_double_translated_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z`
- size: `940`
- prototype: `DWORD *__cdecl(DWORD *, int, _BYTE *Src, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x1816052a`

## callees

- `0x18127b28`
- `0x1813c250`
- `0x18141a7e`
- `0x1814dffc`
- `0x181515c4`
- `0x181580a5`
- `0x1815ae56`
- `0x1815fcbd`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18160037`
- `KERNEL32!GetLastError` at `0x18160037`
- `KERNEL32!WriteFile` at `0x1815ff4f`
- `KERNEL32!WriteFile` at `0x1815ff8f`
- `KERNEL32!WriteFile` at `0x1815ff4f`
- `KERNEL32!WriteFile` at `0x1815ff8f`
- `KERNEL32!GetConsoleOutputCP` at `0x1815fd05`
- `KERNEL32!GetConsoleOutputCP` at `0x1815fd05`

## pseudocode

```c
DWORD *__cdecl write_double_translated_ansi_nolock(DWORD *a1, int a2, _BYTE *Src, int a4)
{
  int v4; // eax
  _BYTE *v5; // edi
  int v6; // ebx
  _BYTE *v7; // esi
  int v8; // ecx
  size_t v9; // eax
  int v10; // eax
  int v11; // edx
  int v12; // edx
  int v13; // esi
  size_t v14; // ecx
  int v15; // ecx
  int v16; // edi
  int v17; // esi
  size_t v18; // esi
  signed int v19; // ecx
  char v20; // dl
  int v21; // eax
  DWORD v22; // eax
  int v23; // esi
  char v24; // al
  char *v25; // ecx
  _BYTE *v26; // esi
  bool v27; // zf
  int v28; // esi
  int v29; // edx
  int v30; // ecx
  DWORD *result; // eax
  struct _Mbstatet *v32; // [esp+0h] [ebp-98h]
  unsigned int v33[2]; // [esp+Ch] [ebp-8Ch] BYREF
  unsigned int v34[2]; // [esp+14h] [ebp-84h] BYREF
  int v35; // [esp+1Ch] [ebp-7Ch]
  UINT CodePage; // [esp+20h] [ebp-78h]
  wchar_t v37[2]; // [esp+24h] [ebp-74h] BYREF
  size_t v38; // [esp+28h] [ebp-70h]
  HANDLE hFile; // [esp+2Ch] [ebp-6Ch]
  _BYTE *v40; // [esp+30h] [ebp-68h]
  _BYTE *v41; // [esp+34h] [ebp-64h]
  DWORD NumberOfBytesWritten; // [esp+38h] [ebp-60h] BYREF
  unsigned int v43; // [esp+3Ch] [ebp-5Ch]
  DWORD LastError; // [esp+40h] [ebp-58h]
  _BYTE *v45; // [esp+44h] [ebp-54h]
  DWORD v46; // [esp+48h] [ebp-50h]
  int v47; // [esp+4Ch] [ebp-4Ch]
  wchar_t DstCh[2]; // [esp+50h] [ebp-48h] BYREF
  _DWORD v49[3]; // [esp+54h] [ebp-44h] BYREF
  char v50; // [esp+60h] [ebp-38h]
  wchar_t v51[2]; // [esp+64h] [ebp-34h] BYREF
  __int16 v52; // [esp+68h] [ebp-30h] BYREF
  size_t Size; // [esp+6Ch] [ebp-2Ch]
  int v54; // [esp+70h] [ebp-28h]
  int cchWideChar; // [esp+74h] [ebp-24h]
  unsigned __int8 v56; // [esp+7Bh] [ebp-1Dh]
  CHAR Buffer[8]; // [esp+7Ch] [ebp-1Ch] BYREF
  char v58[8]; // [esp+84h] [ebp-14h] BYREF
  _BYTE v59[8]; // [esp+8Ch] [ebp-Ch] BYREF

  v4 = (int)*(&lpCriticalSection + (a2 >> 6));
  v5 = Src;
  v40 = Src;
  v47 = a2 >> 6;
  hFile = *(HANDLE *)(56 * (a2 & 0x3F) + v4 + 24);
  v54 = 56 * (a2 & 0x3F);
  v43 = (unsigned int)&Src[a4];
  v6 = 0;
  CodePage = GetConsoleOutputCP();
  _LocaleUpdate::_LocaleUpdate((_LocaleUpdate *)v49, 0);
  v7 = 0;
  LastError = 0;
  v45 = 0;
  v46 = 0;
  v8 = *(_DWORD *)(v49[1] + 8);
  v35 = v8;
  v41 = Src;
  if ( Src >= &Src[a4] )
    goto LABEL_49;
  while ( 1 )
  {
    HIBYTE(v52) = *v5;
    *(_DWORD *)DstCh = 0;
    cchWideChar = 1;
    v9 = (size_t)*(&lpCriticalSection + v47);
    Size = v9;
    if ( v8 == 65001 )
    {
      v10 = 0;
      v38 = v54 + Size + 46;
      do
      {
        if ( !*(_BYTE *)(v54 + Size + 46 + v10) )
          break;
        ++v10;
      }
      while ( v10 < 5 );
      v11 = v43 - (_DWORD)v5;
      cchWideChar = v10;
      if ( v10 <= 0 )
      {
        v19 = byte_181E8960[(unsigned __int8)*v5] + 1;
        Size = v19;
        if ( v19 <= v11 )
        {
          v33[0] = 0;
          v33[1] = 0;
          *(_DWORD *)v51 = v5;
          cchWideChar = (v19 == 4) + 1;
          if ( __crt_mbstring::__mbsrtowcs_utf8(
                 (__crt_mbstring *)DstCh,
                 v51,
                 (const char **)cchWideChar,
                 (unsigned int)v33,
                 v32) == -1 )
            goto LABEL_49;
          v18 = Size;
LABEL_19:
          v5 = &v5[v18 - 1];
          goto LABEL_28;
        }
        if ( v11 <= 0 )
          goto LABEL_41;
        v28 = v54;
        do
        {
          *((_BYTE *)&(*(&lpCriticalSection + v47))[1].SpinCount + v28 + v6 + 2) = v5[v6];
          ++v6;
        }
        while ( v6 < v11 );
      }
      else
      {
        *(_DWORD *)v51 = byte_181E8960[*(unsigned __int8 *)(v54 + Size + 46)] + 1;
        Size = *(_DWORD *)v51 - cchWideChar;
        if ( *(_DWORD *)v51 - cchWideChar <= v11 )
        {
          v12 = cchWideChar;
          v13 = 0;
          v14 = v38;
          do
          {
            v59[v13] = *(_BYTE *)(v14 + v13);
            ++v13;
          }
          while ( v13 < v12 );
          v15 = v54;
          if ( (int)Size > 0 )
          {
            memmove(&v59[v12], v5, Size);
            v15 = v54;
            v12 = cchWideChar;
          }
          v16 = v47;
          v17 = 0;
          do
            *((_BYTE *)&(*(&lpCriticalSection + v16))[1].SpinCount + v15 + v17++ + 2) = 0;
          while ( v17 < v12 );
          v5 = v41;
          v18 = Size;
          *(_DWORD *)v37 = v59;
          v34[0] = 0;
          v34[1] = 0;
          cchWideChar = (*(_DWORD *)v51 == 4) + 1;
          if ( __crt_mbstring::__mbsrtowcs_utf8(
                 (__crt_mbstring *)DstCh,
                 v37,
                 (const char **)cchWideChar,
                 (unsigned int)v34,
                 v32) == -1 )
            goto LABEL_49;
          goto LABEL_19;
        }
        if ( v11 <= 0 )
          goto LABEL_41;
        v23 = v54;
        do
        {
          v24 = v5[v6];
          v25 = (char *)*(&lpCriticalSection + v47) + v23 + v6++;
          v25[cchWideChar + 46] = v24;
          v23 = v54;
        }
        while ( v6 < v11 );
      }
      v7 = v45;
LABEL_41:
      v26 = &v7[v11];
LABEL_42:
      v27 = v50 == 0;
      v45 = v26;
      goto LABEL_50;
    }
    v20 = *(_BYTE *)(v54 + v9 + 45);
    if ( (v20 & 4) != 0 )
    {
      v58[0] = *(_BYTE *)(v54 + v9 + 46);
      v58[1] = *v5;
      *(_BYTE *)(v54 + Size + 45) = v20 & 0xFB;
      v21 = mbtowc(DstCh, v58, 2u);
      goto LABEL_27;
    }
    v56 = *v5;
    if ( (__pctype_func()[v56] & 0x8000u) == 0 )
    {
      v21 = mbtowc(DstCh, v5, 1u);
LABEL_27:
      if ( v21 == -1 )
        goto LABEL_49;
      goto LABEL_28;
    }
    *(_DWORD *)v51 = v5 + 1;
    if ( (unsigned int)(v5 + 1) >= v43 )
    {
      v29 = v47;
      v30 = v54;
      *((_BYTE *)&(*(&lpCriticalSection + v47))[1].SpinCount + v54 + 2) = v56;
      *((_BYTE *)&(*(&lpCriticalSection + v29))[1].SpinCount + v30 + 1) |= 4u;
      v26 = v7 + 1;
      goto LABEL_42;
    }
    if ( mbtowc(DstCh, v5, 2u) == -1 )
      goto LABEL_49;
    v5 = *(_BYTE **)v51;
LABEL_28:
    v41 = ++v5;
    v22 = __acrt_WideCharToMultiByte(CodePage, 0, DstCh, cchWideChar, Buffer, 5, 0, 0);
    *(_DWORD *)v51 = v22;
    if ( !v22 )
      goto LABEL_49;
    if ( !WriteFile(hFile, Buffer, v22, &NumberOfBytesWritten, 0) )
      break;
    v7 = &v5[v46 - (_DWORD)v40];
    v45 = v7;
    if ( NumberOfBytesWritten < *(_DWORD *)v51 )
      goto LABEL_49;
    if ( HIBYTE(v52) == 10 )
    {
      v52 = 13;
      if ( !WriteFile(hFile, &v52, 1u, &NumberOfBytesWritten, 0) )
        break;
      if ( !NumberOfBytesWritten )
        goto LABEL_49;
      ++v46;
      v45 = ++v7;
    }
    if ( (unsigned int)v5 >= v43 )
      goto LABEL_49;
    v8 = v35;
  }
  LastError = GetLastError();
LABEL_49:
  v27 = v50 == 0;
LABEL_50:
  if ( !v27 )
    *(_DWORD *)(v49[0] + 848) &= ~2u;
  result = a1;
  *a1 = LastError;
  a1[1] = (DWORD)v45;
  a1[2] = v46;
  return result;
}

```

## disassembly

```asm
0x1815fcbd  mov     edi, edi
0x1815fcbf  push    ebp
0x1815fcc0  mov     ebp, esp
0x1815fcc2  sub     esp, 8Ch
0x1815fcc8  mov     eax, ___security_cookie
0x1815fccd  xor     eax, ebp
0x1815fccf  mov     [ebp+var_4], eax
0x1815fcd2  mov     eax, [ebp+arg_4]
0x1815fcd5  mov     edx, eax
0x1815fcd7  and     eax, 3Fh
0x1815fcda  sar     edx, 6
0x1815fcdd  imul    ecx, eax, 38h ; '8'
0x1815fce0  push    ebx
0x1815fce1  push    esi
0x1815fce2  mov     eax, lpCriticalSection[edx*4]
0x1815fce9  push    edi; struct _Mbstatet *
0x1815fcea  mov     edi, [ebp+Src]
0x1815fced  mov     [ebp+var_68], edi
0x1815fcf0  mov     [ebp+var_4C], edx
0x1815fcf3  mov     eax, [ecx+eax+18h]
0x1815fcf7  mov     [ebp+hFile], eax
0x1815fcfa  mov     eax, [ebp+arg_C]
0x1815fcfd  add     eax, edi
0x1815fcff  mov     [ebp+var_28], ecx
0x1815fd02  mov     [ebp+var_5C], eax
0x1815fd05  call    ds:GetConsoleOutputCP
0x1815fd0b  xor     ebx, ebx
0x1815fd0d  mov     [ebp+CodePage], eax
0x1815fd10  push    ebx; struct __crt_locale_pointers *
0x1815fd11  lea     ecx, [ebp+var_44]; this
0x1815fd14  call    ??0_LocaleUpdate@@QAE@QAU__crt_locale_pointers@@@Z
0x1815fd19  mov     ecx, [ebp+var_40]
0x1815fd1c  mov     eax, edi
0x1815fd1e  mov     esi, ebx
0x1815fd20  mov     [ebp+var_58], ebx
0x1815fd23  mov     [ebp+var_54], esi
0x1815fd26  mov     [ebp+var_50], ebx
0x1815fd29  mov     ecx, [ecx+8]
0x1815fd2c  mov     [ebp+var_7C], ecx
0x1815fd2f  mov     [ebp+var_64], edi
0x1815fd32  cmp     eax, [ebp+var_5C]
0x1815fd35  jnb     loc_18160040
0x1815fd3b  mov     al, [edi]
0x1815fd3d  cmp     ecx, 0FDE9h
0x1815fd43  mov     ecx, [ebp+var_28]
0x1815fd46  mov     [ebp+var_2F], al
0x1815fd49  mov     eax, [ebp+var_4C]
0x1815fd4c  mov     dword ptr [ebp+DstCh], ebx
0x1815fd4f  mov     [ebp+cchWideChar], 1
0x1815fd56  mov     eax, lpCriticalSection[eax*4]
0x1815fd5d  mov     [ebp+Size], eax
0x1815fd60  jnz     loc_1815FE99
0x1815fd66  mov     edx, [ebp+Size]
0x1815fd69  mov     eax, ebx
0x1815fd6b  add     edx, 2Eh ; '.'
0x1815fd6e  add     edx, ecx
0x1815fd70  mov     [ebp+var_70], edx
0x1815fd73  cmp     [edx+eax], bl
0x1815fd76  jz      short loc_1815FD7E
0x1815fd78  inc     eax
0x1815fd79  cmp     eax, 5
0x1815fd7c  jl      short loc_1815FD73
0x1815fd7e  mov     edx, [ebp+var_5C]
0x1815fd81  sub     edx, edi
0x1815fd83  mov     [ebp+cchWideChar], eax
0x1815fd86  test    eax, eax
0x1815fd88  jle     loc_1815FE3F
0x1815fd8e  mov     eax, [ebp+Size]
0x1815fd91  movzx   eax, byte ptr [ecx+eax+2Eh]
0x1815fd96  movsx   eax, byte_181E8960[eax]
0x1815fd9d  inc     eax
0x1815fd9e  mov     dword ptr [ebp+var_34], eax
0x1815fda1  sub     eax, [ebp+cchWideChar]
0x1815fda4  mov     [ebp+Size], eax
0x1815fda7  cmp     eax, edx
0x1815fda9  jg      loc_1815FFBF
0x1815fdaf  mov     edx, [ebp+cchWideChar]
0x1815fdb2  mov     esi, ebx
0x1815fdb4  mov     ecx, [ebp+var_70]
0x1815fdb7  mov     al, [ecx+esi]
0x1815fdba  mov     [ebp+esi+var_C], al
0x1815fdbe  inc     esi
0x1815fdbf  cmp     esi, edx
0x1815fdc1  jl      short loc_1815FDB7
0x1815fdc3  mov     esi, [ebp+Size]
0x1815fdc6  mov     ecx, [ebp+var_28]
0x1815fdc9  test    esi, esi
0x1815fdcb  jle     short loc_1815FDE3
0x1815fdcd  push    esi; Size
0x1815fdce  lea     eax, [ebp+var_C]
0x1815fdd1  add     eax, edx
0x1815fdd3  push    edi; Src
0x1815fdd4  push    eax; void *
0x1815fdd5  call    _memmove
0x1815fdda  mov     ecx, [ebp+var_28]
0x1815fddd  add     esp, 0Ch
0x1815fde0  mov     edx, [ebp+cchWideChar]
0x1815fde3  mov     edi, [ebp+var_4C]
0x1815fde6  mov     esi, ebx
0x1815fde8  mov     eax, lpCriticalSection[edi*4]
0x1815fdef  add     eax, ecx
0x1815fdf1  mov     [eax+esi+2Eh], bl
0x1815fdf5  inc     esi
0x1815fdf6  cmp     esi, edx
0x1815fdf8  jl      short loc_1815FDE8
0x1815fdfa  mov     edi, [ebp+var_64]
0x1815fdfd  lea     eax, [ebp+var_C]
0x1815fe00  mov     esi, [ebp+Size]
0x1815fe03  lea     ecx, [ebp+var_84]
0x1815fe09  mov     dword ptr [ebp+var_74], eax
0x1815fe0c  xor     eax, eax
0x1815fe0e  cmp     dword ptr [ebp+var_34], 4
0x1815fe12  push    ecx; unsigned int
0x1815fe13  setz    al
0x1815fe16  mov     [ebp+var_84], ebx
0x1815fe1c  inc     eax
0x1815fe1d  mov     [ebp+var_80], ebx
0x1815fe20  push    eax; char **
0x1815fe21  mov     [ebp+cchWideChar], eax
0x1815fe24  lea     eax, [ebp+var_74]
0x1815fe27  push    eax; wchar_t *
0x1815fe28  lea     eax, [ebp+DstCh]
0x1815fe2b  push    eax; this
0x1815fe2c  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YAIPA_WPAPBDIPAU_Mbstatet@@@Z
0x1815fe31  add     esp, 10h
0x1815fe34  cmp     eax, 0FFFFFFFFh
0x1815fe37  jz      loc_18160040
0x1815fe3d  jmp     short loc_1815FE94
0x1815fe3f  movzx   eax, byte ptr [edi]
0x1815fe42  movsx   ecx, byte_181E8960[eax]
0x1815fe49  inc     ecx
0x1815fe4a  mov     [ebp+Size], ecx
0x1815fe4d  cmp     ecx, edx
0x1815fe4f  jg      loc_1815FFF3
0x1815fe55  xor     eax, eax
0x1815fe57  mov     [ebp+var_8C], ebx
0x1815fe5d  cmp     ecx, 4
0x1815fe60  mov     [ebp+var_88], ebx
0x1815fe66  lea     ecx, [ebp+var_8C]
0x1815fe6c  mov     dword ptr [ebp+var_34], edi
0x1815fe6f  setz    al
0x1815fe72  inc     eax
0x1815fe73  push    ecx; unsigned int
0x1815fe74  push    eax; char **
0x1815fe75  mov     [ebp+cchWideChar], eax
0x1815fe78  lea     eax, [ebp+var_34]
0x1815fe7b  push    eax; wchar_t *
0x1815fe7c  lea     eax, [ebp+DstCh]
0x1815fe7f  push    eax; this
0x1815fe80  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YAIPA_WPAPBDIPAU_Mbstatet@@@Z
0x1815fe85  add     esp, 10h
0x1815fe88  cmp     eax, 0FFFFFFFFh
0x1815fe8b  jz      loc_18160040
0x1815fe91  mov     esi, [ebp+Size]
0x1815fe94  dec     edi
0x1815fe95  add     edi, esi
0x1815fe97  jmp     short loc_1815FF18
0x1815fe99  mov     dl, [ecx+eax+2Dh]
0x1815fe9d  test    dl, 4
0x1815fea0  jz      short loc_1815FEC0
0x1815fea2  mov     al, [ecx+eax+2Eh]
0x1815fea6  and     dl, 0FBh
0x1815fea9  mov     [ebp+var_14], al
0x1815feac  mov     al, [edi]
0x1815feae  mov     [ebp+var_13], al
0x1815feb1  mov     eax, [ebp+Size]
0x1815feb4  push    2
0x1815feb6  mov     [ecx+eax+2Dh], dl
0x1815feba  lea     eax, [ebp+var_14]
0x1815febd  push    eax
0x1815febe  jmp     short loc_1815FF03
0x1815fec0  mov     al, [edi]
0x1815fec2  mov     [ebp+var_1D], al
0x1815fec5  call    ___pctype_func
0x1815feca  movzx   ecx, [ebp+var_1D]
0x1815fece  cmp     [eax+ecx*2], bx
0x1815fed2  jge     short loc_1815FF00
0x1815fed4  lea     eax, [edi+1]
0x1815fed7  mov     dword ptr [ebp+var_34], eax
0x1815feda  cmp     eax, [ebp+var_5C]
0x1815fedd  jnb     loc_18160014
0x1815fee3  push    2; SrcSizeInBytes
0x1815fee5  lea     eax, [ebp+DstCh]
0x1815fee8  push    edi; SrcCh
0x1815fee9  push    eax; DstCh
0x1815feea  call    _mbtowc
0x1815feef  add     esp, 0Ch
0x1815fef2  cmp     eax, 0FFFFFFFFh
0x1815fef5  jz      loc_18160040
0x1815fefb  mov     edi, dword ptr [ebp+var_34]
0x1815fefe  jmp     short loc_1815FF18
0x1815ff00  push    1; SrcSizeInBytes
0x1815ff02  push    edi; SrcCh
0x1815ff03  lea     eax, [ebp+DstCh]
0x1815ff06  push    eax; DstCh
0x1815ff07  call    _mbtowc
0x1815ff0c  add     esp, 0Ch
0x1815ff0f  cmp     eax, 0FFFFFFFFh
0x1815ff12  jz      loc_18160040
0x1815ff18  push    ebx; int
0x1815ff19  push    ebx; int
0x1815ff1a  push    5; cbMultiByte
0x1815ff1c  lea     eax, [ebp+Buffer]
0x1815ff1f  inc     edi
0x1815ff20  push    eax; lpMultiByteStr
0x1815ff21  push    [ebp+cchWideChar]; cchWideChar
0x1815ff24  lea     eax, [ebp+DstCh]
0x1815ff27  mov     [ebp+var_64], edi
0x1815ff2a  push    eax; lpWideCharStr
0x1815ff2b  push    ebx; int
0x1815ff2c  push    [ebp+CodePage]; CodePage
0x1815ff2f  call    ___acrt_WideCharToMultiByte
0x1815ff34  add     esp, 20h
0x1815ff37  mov     dword ptr [ebp+var_34], eax
0x1815ff3a  test    eax, eax
0x1815ff3c  jz      loc_18160040
0x1815ff42  push    ebx; lpOverlapped
0x1815ff43  lea     ecx, [ebp+NumberOfBytesWritten]
0x1815ff46  push    ecx; lpNumberOfBytesWritten
0x1815ff47  push    eax; nNumberOfBytesToWrite
0x1815ff48  lea     eax, [ebp+Buffer]
0x1815ff4b  push    eax; lpBuffer
0x1815ff4c  push    [ebp+hFile]; hFile
0x1815ff4f  call    ds:WriteFile
0x1815ff55  test    eax, eax
0x1815ff57  jz      loc_18160037
0x1815ff5d  mov     esi, [ebp+var_50]
0x1815ff60  sub     esi, [ebp+var_68]
0x1815ff63  mov     eax, dword ptr [ebp+var_34]
0x1815ff66  add     esi, edi
0x1815ff68  mov     [ebp+var_54], esi
0x1815ff6b  cmp     [ebp+NumberOfBytesWritten], eax
0x1815ff6e  jb      loc_18160040
0x1815ff74  cmp     [ebp+var_2F], 0Ah
0x1815ff78  jnz     short loc_1815FFAE
0x1815ff7a  push    0Dh
0x1815ff7c  pop     eax
0x1815ff7d  push    ebx; lpOverlapped
0x1815ff7e  mov     [ebp-30h], ax
0x1815ff82  lea     eax, [ebp+NumberOfBytesWritten]
0x1815ff85  push    eax; lpNumberOfBytesWritten
0x1815ff86  push    1; nNumberOfBytesToWrite
0x1815ff88  lea     eax, [ebp+var_30]
0x1815ff8b  push    eax; lpBuffer
0x1815ff8c  push    [ebp+hFile]; hFile
0x1815ff8f  call    ds:WriteFile
0x1815ff95  test    eax, eax
0x1815ff97  jz      loc_18160037
0x1815ff9d  cmp     [ebp+NumberOfBytesWritten], 1
0x1815ffa1  jb      loc_18160040
0x1815ffa7  inc     [ebp+var_50]
0x1815ffaa  inc     esi
0x1815ffab  mov     [ebp+var_54], esi
0x1815ffae  cmp     edi, [ebp+var_5C]
0x1815ffb1  jnb     loc_18160040
0x1815ffb7  mov     ecx, [ebp+var_7C]
0x1815ffba  jmp     loc_1815FD3B
0x1815ffbf  test    edx, edx
0x1815ffc1  jle     short loc_1815FFE8
0x1815ffc3  mov     esi, ecx
0x1815ffc5  mov     eax, [ebp+var_4C]
0x1815ffc8  mov     ecx, lpCriticalSection[eax*4]
0x1815ffcf  mov     al, [ebx+edi]
0x1815ffd2  add     ecx, esi
0x1815ffd4  mov     esi, [ebp+cchWideChar]
0x1815ffd7  add     ecx, ebx
0x1815ffd9  inc     ebx
0x1815ffda  mov     [ecx+esi+2Eh], al
0x1815ffde  mov     esi, [ebp+var_28]
0x1815ffe1  cmp     ebx, edx
0x1815ffe3  jl      short loc_1815FFC5
0x1815ffe5  mov     esi, [ebp+var_54]
0x1815ffe8  add     esi, edx
0x1815ffea  cmp     [ebp+var_38], 0
0x1815ffee  mov     [ebp+var_54], esi
0x1815fff1  jmp     short loc_18160043
0x1815fff3  test    edx, edx
0x1815fff5  jle     short loc_1815FFE8
0x1815fff7  mov     esi, [ebp+var_28]
0x1815fffa  mov     eax, [ebp+var_4C]
0x1815fffd  mov     ecx, lpCriticalSection[eax*4]
0x18160004  mov     al, [ebx+edi]
0x18160007  add     ecx, esi
0x18160009  mov     [ecx+ebx+2Eh], al
0x1816000d  inc     ebx
0x1816000e  cmp     ebx, edx
0x18160010  jl      short loc_1815FFFA
0x18160012  jmp     short loc_1815FFE5
0x18160014  mov     edx, [ebp+var_4C]
0x18160017  mov     ecx, [ebp+var_28]
0x1816001a  mov     bl, [ebp+var_1D]
0x1816001d  mov     eax, lpCriticalSection[edx*4]
0x18160024  mov     [ecx+eax+2Eh], bl
0x18160028  mov     eax, lpCriticalSection[edx*4]
0x1816002f  or      byte ptr [ecx+eax+2Dh], 4
0x18160034  inc     esi
0x18160035  jmp     short loc_1815FFEA
0x18160037  call    ds:GetLastError
0x1816003d  mov     [ebp+var_58], eax
0x18160040  cmp     [ebp+var_38], bl
  ... truncated ...
```
