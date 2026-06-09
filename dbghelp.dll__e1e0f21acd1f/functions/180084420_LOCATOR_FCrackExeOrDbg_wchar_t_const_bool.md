# LOCATOR::FCrackExeOrDbg(wchar_t const *,bool)

- ea: `0x180084420`
- end: `0x180085128`
- name: `?FCrackExeOrDbg@LOCATOR@@QEAA_NPEB_W_N@Z`
- size: `3336`
- prototype: `bool __fastcall(LOCATOR *__hidden this, const wchar_t *, bool)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x1800478a0`
- `0x1800479f0`
- `0x180047b60`

## callees

- `0x180084420`
- `0x180085e80`
- `0x180087230`
- `0x180087400`
- `0x180087970`
- `0x180087f00`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180084d7d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180084d7d`
- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x180084589`
- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x180084589`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180084b86`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180084d69`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180084b86`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180084d69`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18008468d`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800850ea`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18008468d`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800850ea`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180084613`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18008471a`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180084904`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180084a71`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180084bde`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180084f26`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180084613`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18008471a`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180084904`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180084a71`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180084bde`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180084f26`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800845f3`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800846f7`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800848e4`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180084a51`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180084bbe`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180084f05`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800845f3`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800846f7`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800848e4`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180084a51`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180084bbe`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180084f05`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800845be`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18008504e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800850be`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800845be`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18008504e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800850be`

## pseudocode

```c
char __fastcall LOCATOR::FCrackExeOrDbg(LOCATOR *this, wchar_t *a2, char a3)
{
  __int64 (__fastcall *v3)(_QWORD, __int64); // rax
  _QWORD *v4; // rsi
  unsigned int v5; // r14d
  __int64 v8; // rax
  char result; // al
  __int64 (__fastcall *v10)(_QWORD, __int64); // rax
  __int64 (__fastcall *v11)(_QWORD, __int64); // rax
  struct _iobuf *v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 (__fastcall *v15)(_QWORD, __int64); // rax
  __int64 v16; // rax
  FILE *v17; // rax
  _WORD *v18; // rcx
  bool v19; // al
  int (__fastcall *v20)(_QWORD, _QWORD, __int64, __int16 *); // rax
  bool v21; // al
  int (__fastcall *v22)(_QWORD, _QWORD, __int64, int *); // rax
  unsigned int v23; // edx
  unsigned int v24; // ecx
  unsigned int v25; // r12d
  int v26; // r13d
  char v27; // r11
  unsigned int v28; // r13d
  unsigned int v29; // esi
  __int64 v30; // rcx
  unsigned int v31; // eax
  unsigned int v32; // r10d
  __int64 v33; // r15
  bool v34; // al
  int (__fastcall *v35)(_QWORD, _QWORD, __int64, _BYTE *); // rax
  int v36; // r11d
  char v37; // al
  bool v38; // al
  __int64 (__fastcall *v39)(_QWORD, _QWORD, __int64, _BYTE *); // rax
  int v40; // eax
  __int64 (__fastcall *v41)(_QWORD, _QWORD, __int64, _BYTE *); // rax
  unsigned __int64 v42; // r14
  unsigned __int64 v43; // r15
  __m128i v44; // xmm2
  __m128i v45; // xmm1
  unsigned int v46; // r8d
  unsigned int v47; // r9d
  unsigned __int64 v48; // r12
  __int64 v49; // rsi
  unsigned int i; // r14d
  _QWORD *v51; // r15
  bool v52; // al
  __int64 (__fastcall *v53)(_QWORD, _QWORD, __int64, __m128i *); // rax
  int v54; // eax
  __int64 (__fastcall *v55)(_QWORD, _QWORD, __int64, __m128i *); // rax
  __int64 (__fastcall *v56)(_QWORD, _QWORD); // rax
  void (__fastcall *v57)(_QWORD, __int64, __m128i *); // rax
  const wchar_t *v58; // rcx
  __m128i v59; // xmm2
  char v60; // si
  bool v61; // al
  __int64 (__fastcall *v62)(_QWORD, _QWORD, __int64, unsigned int *); // rax
  int v63; // eax
  __int64 (__fastcall *v64)(_QWORD, unsigned __int64, __int64, unsigned int *); // rax
  bool v65; // zf
  __m128i v66; // xmm1
  unsigned int v67; // r9d
  wchar_t *v68; // rax
  _WORD *v69; // rcx
  _WORD *v70; // rcx
  wchar_t *v71; // r8
  wchar_t *v72; // rax
  unsigned int DirCount; // [rsp+20h] [rbp-E0h]
  unsigned int Filename; // [rsp+28h] [rbp-D8h]
  unsigned int v76; // [rsp+54h] [rbp-ACh]
  unsigned int v77; // [rsp+54h] [rbp-ACh]
  int v78; // [rsp+58h] [rbp-A8h]
  unsigned int v79; // [rsp+58h] [rbp-A8h]
  unsigned int v80; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v81; // [rsp+60h] [rbp-A0h]
  unsigned int v82[2]; // [rsp+68h] [rbp-98h]
  _QWORD *v83; // [rsp+70h] [rbp-90h]
  unsigned int v84; // [rsp+78h] [rbp-88h]
  __m128i v85; // [rsp+80h] [rbp-80h]
  __m128i v86; // [rsp+90h] [rbp-70h]
  wchar_t *FullPath; // [rsp+A0h] [rbp-60h]
  __m128i v88; // [rsp+A8h] [rbp-58h]
  unsigned int v89[8]; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v90; // [rsp+E8h] [rbp-18h]
  __m128i v91; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v92; // [rsp+108h] [rbp+8h]
  unsigned int v93; // [rsp+110h] [rbp+10h]
  _BYTE v94[12]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v95; // [rsp+12Ch] [rbp+2Ch]
  unsigned __int64 v96; // [rsp+130h] [rbp+30h]
  int v97; // [rsp+160h] [rbp+60h]
  int v98; // [rsp+164h] [rbp+64h]
  __int16 Buffer; // [rsp+170h] [rbp+70h] BYREF
  int v100; // [rsp+178h] [rbp+78h]
  int Offset; // [rsp+1ACh] [rbp+ACh]
  int v102; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v103; // [rsp+1B6h] [rbp+B6h]
  int v104; // [rsp+1B8h] [rbp+B8h]
  unsigned __int16 v105; // [rsp+1C4h] [rbp+C4h]
  __int16 v106; // [rsp+1C6h] [rbp+C6h]
  __int16 v107; // [rsp+1C8h] [rbp+C8h]
  int v108; // [rsp+200h] [rbp+100h]
  __int64 v109; // [rsp+224h] [rbp+124h]
  __int64 v110; // [rsp+234h] [rbp+134h]
  unsigned int v111; // [rsp+258h] [rbp+158h]
  unsigned int v112; // [rsp+25Ch] [rbp+15Ch]
  unsigned int v113; // [rsp+268h] [rbp+168h]
  unsigned int v114; // [rsp+26Ch] [rbp+16Ch]
  unsigned int v115; // [rsp+298h] [rbp+198h]
  int v116; // [rsp+29Ch] [rbp+19Ch]
  unsigned int v117; // [rsp+2A8h] [rbp+1A8h]
  int v118; // [rsp+2ACh] [rbp+1ACh]
  wchar_t v119[256]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wchar_t v120[256]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v3 = (__int64 (__fastcall *)(_QWORD, __int64))*((_QWORD *)this + 258);
  v4 = (_QWORD *)((char *)this + 2056);
  v5 = 0;
  FullPath = a2;
  v83 = (_QWORD *)((char *)this + 2056);
  if ( v3 )
  {
    v8 = v3(*v4, 11);
    *((_QWORD *)this + 269) = v8;
    if ( v8 )
    {
      *((_BYTE *)this + 3352) = 1;
      return 1;
    }
    v83 = v4;
  }
  else
  {
    *((_QWORD *)this + 269) = 0;
  }
  v10 = (__int64 (__fastcall *)(_QWORD, __int64))*((_QWORD *)this + 258);
  if ( v10 )
  {
    v13 = v10(*v4, 10);
    *((_QWORD *)this + 270) = v13;
    if ( v13 && LOCATOR::FReadMiscDebugData(this) )
    {
      *((_BYTE *)this + 3312) = 1;
      return LOCATOR::FSaveFileNames(this, a2);
    }
  }
  else
  {
    *((_QWORD *)this + 270) = 0;
  }
  v11 = (__int64 (__fastcall *)(_QWORD, __int64))*((_QWORD *)this + 258);
  v12 = 0;
  if ( v11 )
  {
    v14 = v11(*v4, 4);
    *((_QWORD *)this + 267) = v14;
    if ( v14 )
      goto LABEL_24;
  }
  else
  {
    *((_QWORD *)this + 267) = 0;
  }
  v15 = (__int64 (__fastcall *)(_QWORD, __int64))*((_QWORD *)this + 258);
  if ( v15 )
  {
    v16 = v15(*v4, 5);
    *((_QWORD *)this + 268) = v16;
    if ( !v16 )
      goto LABEL_17;
LABEL_24:
    v20 = (int (__fastcall *)(_QWORD, _QWORD, __int64, __int16 *))*((_QWORD *)this + 267);
    if ( !v20 )
    {
      v20 = (int (__fastcall *)(_QWORD, _QWORD, __int64, __int16 *))*((_QWORD *)this + 268);
      if ( !v20 )
        goto LABEL_175;
    }
    v19 = v20(*v4, 0, 64, &Buffer) >= 0;
    goto LABEL_27;
  }
  *((_QWORD *)this + 268) = 0;
LABEL_17:
  v17 = _wfsopen(a2, L"rb", 32);
  v12 = v17;
  if ( !v17 )
  {
    *(_DWORD *)this = 4;
    v18 = (_WORD *)((char *)this + 4);
    if ( a2 )
    {
      _o_wcsncpy_s(v18, 1024, a2, -1);
      if ( (unsigned __int16)(*((_WORD *)this + 1024) + 10240) <= 0x3FFu )
        *((_WORD *)this + 1024) = 0;
    }
    else
    {
      *v18 = 0;
    }
    return 0;
  }
  if ( fseek(v17, 0, 0) )
    goto LABEL_175;
  v19 = fread(&Buffer, 1u, 0x40u, v12) == 64;
LABEL_27:
  if ( !v19 )
    goto LABEL_175;
  if ( v12 && Buffer == 18756 )
  {
    fclose(v12);
    *((_DWORD *)this + 830) = v100;
    result = LOCATOR::FLocateDbgValidate(this, a2);
    if ( result || *(_DWORD *)this != 11 )
      return result;
    goto LABEL_175;
  }
  if ( Buffer != 23117 )
    goto LABEL_175;
  if ( !LOCATOR::FSaveFileNames(this, a2) )
    goto LABEL_180;
  if ( Offset <= 0 )
    goto LABEL_175;
  if ( v12 )
  {
    if ( fseek(v12, Offset, 0) )
      goto LABEL_175;
    v21 = fread(&v102, 1u, 0x108u, v12) == 264;
  }
  else
  {
    v22 = (int (__fastcall *)(_QWORD, _QWORD, __int64, int *))*((_QWORD *)this + 267);
    if ( !v22 )
    {
      v22 = (int (__fastcall *)(_QWORD, _QWORD, __int64, int *))*((_QWORD *)this + 268);
      if ( !v22 )
        goto LABEL_175;
    }
    v21 = v22(*v4, (unsigned int)Offset, 264, &v102) >= 0;
  }
  if ( !v21 || v102 != 17744 )
    goto LABEL_175;
  v23 = 0;
  v81 = 0;
  v24 = 0;
  v80 = 0;
  v25 = 0;
  v26 = 0;
  if ( v107 == 267 )
  {
    *((_DWORD *)this + 829) = v108;
    if ( (unsigned int)v109 >= 6 )
    {
      v23 = v111;
      v24 = v112;
      v81 = v111;
      v80 = v112;
    }
    v27 = a3;
    if ( a3 && (unsigned int)v109 >= 0xE )
    {
      v25 = v115;
      v26 = v116;
    }
  }
  else
  {
    if ( v107 != 523 )
      goto LABEL_175;
    *((_DWORD *)this + 829) = v108;
    if ( (unsigned int)v110 >= 6 )
    {
      v23 = v113;
      v24 = v114;
      v81 = v113;
      v80 = v114;
    }
    v27 = a3;
    if ( a3 && (unsigned int)v110 >= 0xE )
    {
      v25 = v117;
      v26 = v118;
    }
  }
  if ( !v23 || !v24 )
  {
    *(_DWORD *)this = 19;
    v70 = (_WORD *)((char *)this + 4);
    if ( !a2 )
    {
      *v70 = 0;
      goto LABEL_180;
    }
    v71 = a2;
LABEL_178:
    _o_wcsncpy_s(v70, 1024, v71, -1);
    if ( (unsigned __int16)(*((_WORD *)this + 1024) + 10240) <= 0x3FFu )
      *((_WORD *)this + 1024) = 0;
    goto LABEL_180;
  }
  if ( v27 && (!v25 || !v26) )
  {
LABEL_175:
    v72 = FullPath;
    v70 = (_WORD *)((char *)this + 4);
    *(_DWORD *)this = 17;
    if ( !v72 )
    {
      *v70 = 0;
LABEL_180:
      if ( v12 )
        fclose(v12);
      return 0;
    }
    v71 = v72;
    goto LABEL_178;
  }
  if ( *((_QWORD *)this + 267) || !*((_QWORD *)this + 268) )
  {
    v29 = v105 + 24 + Offset;
    v78 = 0;
    v30 = v103;
    v31 = 0;
    *(_QWORD *)v82 = v103;
    v32 = 0;
    v76 = 0;
    v33 = 0;
    v84 = 0;
    if ( v103 )
    {
      while ( 1 )
      {
        if ( v12 )
        {
          if ( fseek(v12, v29, 0) )
            break;
          v34 = fread(v94, 1u, 0x28u, v12) == 40;
        }
        else
        {
          v35 = (int (__fastcall *)(_QWORD, _QWORD, __int64, _BYTE *))*((_QWORD *)this + 267);
          if ( !v35 )
          {
            v35 = (int (__fastcall *)(_QWORD, _QWORD, __int64, _BYTE *))*((_QWORD *)this + 268);
            if ( !v35 )
              goto LABEL_87;
          }
          v34 = v35(*v83, v29, 40, v94) >= 0;
        }
        if ( !v34 )
          break;
        if ( v95 > v81 || (unsigned int)v96 + v95 < v81 + v80 )
        {
          v36 = v78;
          v32 = v76;
        }
        else
        {
          v36 = HIDWORD(v96);
          v78 = HIDWORD(v96);
          v32 = v95;
          v76 = v95;
        }
        v37 = a3;
        if ( a3 )
        {
          if ( v95 <= v25 )
          {
            v37 = a3;
            if ( (unsigned int)v96 + v95 >= v25 + v26 )
            {
              v5 = HIDWORD(v96);
              v84 = v95;
            }
          }
        }
        if ( v36 && (!v37 || v5) )
          goto LABEL_86;
        v30 = *(_QWORD *)v82;
        if ( (unsigned __int64)++v33 >= *(_QWORD *)v82 )
          goto LABEL_87;
        v29 += 40;
      }
      v32 = v76;
LABEL_86:
      v30 = *(_QWORD *)v82;
LABEL_87:
      v31 = v84;
      v23 = v81;
      v27 = a3;
    }
    if ( v33 == v30 )
      goto LABEL_175;
    v28 = v23 + v78 - v32;
    if ( !v27 )
      goto LABEL_105;
    v4 = v83;
    v5 = v25 + v5 - v31;
  }
  else
  {
    v28 = 0;
  }
  if ( v27 )
  {
    if ( v12 )
    {
      if ( fseek(v12, v5, 0) )
        goto LABEL_175;
      v38 = fread(v94, 1u, 0x48u, v12) == 72;
    }
    else
    {
      v39 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _BYTE *))*((_QWORD *)this + 267);
      if ( v39 )
      {
        v40 = v39(*v4, v5, 72, v94);
      }
      else
      {
        v41 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _BYTE *))*((_QWORD *)this + 268);
        if ( !v41 || !v25 )
          goto LABEL_175;
        v40 = v41(*v4, v25, 72, v94);
      }
      v38 = v40 >= 0;
    }
    if ( !v38 || !v97 || !v98 )
      goto LABEL_175;
    v27 = a3;
  }
LABEL_105:
  v42 = 0;
  v43 = 0;
  v90 = 0;
  v77 = 0;
  v96 = 0;
  v44 = 0;
  v45 = 0;
  v86 = 0;
  v46 = 0;
  v79 = 0;
  *(_QWORD *)v82 = 0;
  v47 = 0;
  *(_QWORD *)v89 = 0;
  v48 = v80 / 0x1CuLL;
  v85 = 0;
  v88 = 0;
  if ( v27 )
  {
    _wsplitpath_s(FullPath, 0, 0, 0, 0, v120, 0x100u, 0, 0);
    v27 = a3;
    v45 = 0;
    v44 = 0;
    v47 = 0;
    v46 = 0;
  }
  v49 = 0;
  if ( v48 )
  {
    for ( i = v81; ; i += 28 )
    {
      if ( v12 )
      {
        if ( fseek(v12, v28, 0) )
          goto LABEL_175;
        v51 = v83;
        v52 = fread(&v91, 1u, 0x1Cu, v12) == 28;
      }
      else
      {
        v53 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, __m128i *))*((_QWORD *)this + 267);
        if ( v53 )
        {
          v51 = v83;
          v54 = v53(*v83, v28, 28, &v91);
        }
        else
        {
          v55 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, __m128i *))*((_QWORD *)this + 268);
          if ( !v55 || !i )
            goto LABEL_175;
          v51 = v83;
          v54 = v55(*v83, i, 28, &v91);
        }
        v52 = v54 >= 0;
      }
      if ( !v52 )
        goto LABEL_175;
      if ( *((_QWORD *)this + 267) || !*((_QWORD *)this + 268) )
        v28 += 28;
      if ( !*((_BYTE *)this + 2072) )
      {
        v56 = (__int64 (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)this + 258);
        *((_BYTE *)this + 2072) = 1;
        if ( v56 )
          v56 = (__int64 (__fastcall *)(_QWORD, _QWORD))v56(*v51, 0);
        *((_QWORD *)this + 260) = v56;
      }
      v57 = (void (__fastcall *)(_QWORD, __int64, __m128i *))*((_QWORD *)this + 260);
      if ( v57 )
        v57(*v51, 1, &v91);
      switch ( v91.m128i_i32[3] )
      {
        case 2:
          v27 = a3;
          if ( !a3 )
          {
            v44 = v91;
            v46 = v93;
            v86 = v91;
            v77 = v93;
            v90 = v92;
            goto LABEL_136;
          }
          *(_QWORD *)((char *)this + 3356) = v92;
          *((_DWORD *)this + 841) = v93;
          *((_WORD *)this + 1684) = v91.m128i_i16[5];
          *((_BYTE *)this + 3352) = 1;
          *((_QWORD *)this + 283) = v12;
          if ( !LOCATOR::FReadDebugDirInfo(this) || !*((_BYTE *)this + 3370) || !*((_DWORD *)this + 848) )
            goto LABEL_135;
          v58 = (const wchar_t *)*((_QWORD *)this + 425);
          if ( v58 )
          {
            _wsplitpath_s(v58, 0, 0, 0, 0, v119, 0x100u, 0, 0);
            if ( !(unsigned int)_o__wcsicmp(v120, v119) )
              return 1;
LABEL_135:
            v27 = a3;
            v46 = v77;
            v44 = v86;
LABEL_136:
            v45 = v85;
            v47 = v79;
            break;
          }
          v45 = v85;
          v47 = v79;
          v27 = a3;
          v46 = v77;
          v44 = v86;
          break;
        case 4:
          v88 = v91;
          *(_QWORD *)v82 = v93;
          *(_QWORD *)v89 = v92;
          goto LABEL_135;
        case 0x11:
          v45 = v91;
          v47 = v93;
          v27 = a3;
          v46 = v77;
          v44 = v86;
          v79 = v93;
          v85 = v91;
          v96 = v92;
          break;
        default:
          goto LABEL_135;
      }
      if ( ++v49 >= v48 )
      {
        v42 = v90;
        v43 = v96;
        break;
      }
    }
  }
  v59 = _mm_srli_si128(v44, 8);
  *((_QWORD *)this + 283) = v12;
  if ( v59.m128i_i32[1] )
  {
    *((_DWORD *)this + 839) = v42;
    v60 = 1;
    *((_WORD *)this + 1684) = v59.m128i_i16[1];
    *((_BYTE *)this + 3352) = 1;
    *((_DWORD *)this + 840) = HIDWORD(v42);
    *((_DWORD *)this + 841) = v46;
  }
  else
  {
    v60 = 0;
    if ( v27 )
      goto LABEL_175;
  }
  if ( _mm_srli_si128(v45, 8).m128i_u32[1] )
  {
    *((_BYTE *)this + 3352) = 1;
    *((_BYTE *)this + 3408) = 1;
    *(_QWORD *)((char *)this + 3412) = v43;
    *((_DWORD *)this + 855) = v47;
    if ( (unsigned int)v43 > 8 )
    {
      if ( v12 )
      {
        if ( fseek(v12, v47, 0) )
          goto LABEL_175;
        v61 = fread(&v80, 1u, 4u, v12) == 4;
      }
      else
      {
        v62 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, unsigned int *))*((_QWORD *)this + 267);
        if ( v62 )
        {
          v63 = v62(*((_QWORD *)this + 257), v47, 4, &v80);
        }
        else
        {
          v64 = (__int64 (__fastcall *)(_QWORD, unsigned __int64, __int64, unsigned int *))*((_QWORD *)this + 268);
          if ( !v64 || !HIDWORD(v43) )
            goto LABEL_175;
          v63 = v64(*((_QWORD *)this + 257), HIDWORD(v43), 4, &v80);
        }
        v61 = v63 >= 0;
      }
      if ( v61 )
      {
        v60 = 1;
        if ( v80 == 1111773261 )
          goto LABEL_163;
      }
    }
    goto LABEL_175;
  }
LABEL_163:
  v65 = (v106 & 0x200) == 0;
  *((_BYTE *)this + 3312) = (v106 & 0x200) != 0;
  if ( !v65 )
  {
    v66 = v88;
    if ( _mm_cvtsi128_si32(_mm_srli_si128(v88, 12)) )
    {
      v67 = v82[0];
      *((_DWORD *)this + 830) = v104;
      Filename = v89[0];
      DirCount = v89[1];
      *((_DWORD *)this + 831) = _mm_cvtsi128_si32(_mm_srli_si128(v66, 4));
      LOCATOR::ReadMiscPath(this, 0, v12, v67, DirCount, Filename);
      return 1;
    }
  }
  if ( !v60 )
  {
    v68 = FullPath;
    v69 = (_WORD *)((char *)this + 4);
    *(_DWORD *)this = 19;
    if ( !v68 )
    {
      *v69 = 0;
      return 0;
    }
    _o_wcsncpy_s(v69, 1024, v68, -1);
    if ( (unsigned __int16)(*((_WORD *)this + 1024) + 10240) <= 0x3FFu )
      *((_WORD *)this + 1024) = 0;
  }
  return v60;
}

```

## disassembly

```asm
0x180084420  push    rbp
0x180084422  push    rbx
0x180084423  push    rsi
0x180084424  push    r14
0x180084426  push    r15
0x180084428  lea     rbp, [rsp-5E0h]
0x180084430  sub     rsp, 6E0h
0x180084437  mov     rax, cs:__security_cookie
0x18008443e  xor     rax, rsp
0x180084441  mov     [rbp+600h+var_40], rax
0x180084448  mov     rax, [rcx+810h]
0x18008444f  lea     rsi, [rcx+808h]
0x180084456  xor     r14d, r14d
0x180084459  mov     [rsp+700h+var_6B0], r8b
0x18008445e  mov     [rbp+600h+FullPath], rdx
0x180084462  mov     r15, rdx
0x180084465  mov     [rsp+700h+var_690], rsi
0x18008446a  mov     rbx, rcx
0x18008446d  test    rax, rax
0x180084470  jnz     short loc_18008447B
0x180084472  mov     [rcx+868h], r14
0x180084479  jmp     short loc_1800844A8
0x18008447b  mov     rcx, [rsi]
0x18008447e  mov     edx, 0Bh
0x180084483  call    cs:__guard_dispatch_icall_fptr
0x180084489  mov     [rbx+868h], rax
0x180084490  test    rax, rax
0x180084493  jz      short loc_1800844A3
0x180084495  mov     byte ptr [rbx+0D18h], 1
0x18008449c  mov     al, 1
0x18008449e  jmp     loc_18008510A
0x1800844a3  mov     [rsp+700h+var_690], rsi
0x1800844a8  mov     rax, [rbx+810h]
0x1800844af  test    rax, rax
0x1800844b2  jnz     short loc_1800844EB
0x1800844b4  mov     [rbx+870h], r14
0x1800844bb  mov     rax, [rbx+810h]
0x1800844c2  mov     [rsp+700h+arg_10], rdi
0x1800844ca  mov     rdi, r14
0x1800844cd  mov     [rsp+700h+var_28], r12
0x1800844d5  mov     [rsp+700h+var_30], r13
0x1800844dd  test    rax, rax
0x1800844e0  jnz     short loc_180084528
0x1800844e2  mov     [rbx+858h], r14
0x1800844e9  jmp     short loc_180084546
0x1800844eb  mov     rcx, [rsi]
0x1800844ee  mov     edx, 0Ah
0x1800844f3  call    cs:__guard_dispatch_icall_fptr
0x1800844f9  mov     [rbx+870h], rax
0x180084500  test    rax, rax
0x180084503  jz      short loc_1800844BB
0x180084505  mov     rcx, rbx; this
0x180084508  call    ?FReadMiscDebugData@LOCATOR@@AEAA_NXZ; LOCATOR::FReadMiscDebugData(void)
0x18008450d  test    al, al
0x18008450f  jz      short loc_1800844BB
0x180084511  mov     rdx, r15; wchar_t *
0x180084514  mov     byte ptr [rbx+0CF0h], 1
0x18008451b  mov     rcx, rbx; this
0x18008451e  call    ?FSaveFileNames@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FSaveFileNames(wchar_t const *)
0x180084523  jmp     loc_18008510A
0x180084528  mov     rcx, [rsi]
0x18008452b  mov     edx, 4
0x180084530  call    cs:__guard_dispatch_icall_fptr
0x180084536  mov     [rbx+858h], rax
0x18008453d  test    rax, rax
0x180084540  jnz     loc_180084622
0x180084546  mov     rax, [rbx+810h]
0x18008454d  test    rax, rax
0x180084550  jnz     short loc_18008455B
0x180084552  mov     [rbx+860h], r14
0x180084559  jmp     short loc_180084579
0x18008455b  mov     rcx, [rsi]
0x18008455e  mov     edx, 5
0x180084563  call    cs:__guard_dispatch_icall_fptr
0x180084569  mov     [rbx+860h], rax
0x180084570  test    rax, rax
0x180084573  jnz     loc_180084622
0x180084579  mov     r8d, 20h ; ' '; ShFlag
0x18008457f  lea     rdx, aRb; "rb"
0x180084586  mov     rcx, r15; FileName
0x180084589  call    cs:__imp__wfsopen
0x18008458f  mov     rdi, rax
0x180084592  test    rax, rax
0x180084595  jnz     short loc_1800845EB
0x180084597  mov     dword ptr [rbx], 4
0x18008459d  lea     rcx, [rbx+4]
0x1800845a1  test    r15, r15
0x1800845a4  jnz     short loc_1800845AF
0x1800845a6  mov     [rcx], r14w
0x1800845aa  jmp     loc_1800850F0
0x1800845af  mov     r9, 0FFFFFFFFFFFFFFFFh
0x1800845b6  mov     r8, r15
0x1800845b9  mov     edx, 400h
0x1800845be  call    cs:__imp__o_wcsncpy_s
0x1800845c4  mov     eax, 2800h
0x1800845c9  mov     ecx, 3FFh
0x1800845ce  add     ax, [rbx+800h]
0x1800845d5  cmp     ax, cx
0x1800845d8  ja      loc_1800850F0
0x1800845de  mov     [rbx+800h], r14w
0x1800845e6  jmp     loc_1800850F0
0x1800845eb  xor     r8d, r8d; Origin
0x1800845ee  xor     edx, edx; Offset
0x1800845f0  mov     rcx, rdi; Stream
0x1800845f3  call    cs:__imp_fseek
0x1800845f9  test    eax, eax
0x1800845fb  jnz     loc_180085096
0x180084601  mov     r9, rdi; Stream
0x180084604  lea     rcx, [rbp+600h+Buffer]; Buffer
0x180084608  mov     edx, 1; ElementSize
0x18008460d  mov     r8d, 40h ; '@'; ElementCount
0x180084613  call    cs:__imp_fread
0x180084619  cmp     rax, 40h ; '@'
0x18008461d  setz    al
0x180084620  jmp     short loc_18008466F
0x180084622  mov     rax, [rbx+858h]
0x180084629  test    rax, rax
0x18008462c  jz      short loc_180084645
0x18008462e  mov     rcx, [rsi]
0x180084631  lea     r9, [rbp+600h+Buffer]
0x180084635  xor     edx, edx
0x180084637  mov     r8d, 40h ; '@'
0x18008463d  call    cs:__guard_dispatch_icall_fptr
0x180084643  jmp     short loc_18008466A
0x180084645  mov     rax, [rbx+860h]
0x18008464c  test    rax, rax
0x18008464f  jz      loc_180085096
0x180084655  mov     rcx, [rsi]
0x180084658  lea     r9, [rbp+600h+Buffer]
0x18008465c  xor     edx, edx
0x18008465e  mov     r8d, 40h ; '@'
0x180084664  call    cs:__guard_dispatch_icall_fptr
0x18008466a  shr     eax, 1Fh
0x18008466d  xor     al, 1
0x18008466f  test    al, al
0x180084671  jz      loc_180085096
0x180084677  movzx   eax, [rbp+600h+Buffer]
0x18008467b  test    rdi, rdi
0x18008467e  jz      short loc_1800846BD
0x180084680  mov     ecx, 4944h
0x180084685  cmp     ax, cx
0x180084688  jnz     short loc_1800846BD
0x18008468a  mov     rcx, rdi; Stream
0x18008468d  call    cs:__imp_fclose
0x180084693  mov     eax, [rbp+600h+var_588]
0x180084696  mov     rdx, r15; wchar_t *
0x180084699  mov     rcx, rbx; this
0x18008469c  mov     [rbx+0CF8h], eax
0x1800846a2  call    ?FLocateDbgValidate@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocateDbgValidate(wchar_t const *)
0x1800846a7  test    al, al
0x1800846a9  jnz     loc_1800850F2
0x1800846af  cmp     dword ptr [rbx], 0Bh
0x1800846b2  jz      loc_180085096
0x1800846b8  jmp     loc_1800850F2
0x1800846bd  mov     ecx, 5A4Dh
0x1800846c2  cmp     ax, cx
0x1800846c5  jnz     loc_180085096
0x1800846cb  mov     rdx, r15; wchar_t *
0x1800846ce  mov     rcx, rbx; this
0x1800846d1  call    ?FSaveFileNames@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FSaveFileNames(wchar_t const *)
0x1800846d6  test    al, al
0x1800846d8  jz      loc_1800850E2
0x1800846de  mov     edx, [rbp+600h+Offset]; Offset
0x1800846e4  test    edx, edx
0x1800846e6  jle     loc_180085096
0x1800846ec  test    rdi, rdi
0x1800846ef  jz      short loc_18008472B
0x1800846f1  xor     r8d, r8d; Origin
0x1800846f4  mov     rcx, rdi; Stream
0x1800846f7  call    cs:__imp_fseek
0x1800846fd  test    eax, eax
0x1800846ff  jnz     loc_180085096
0x180084705  mov     r9, rdi; Stream
0x180084708  lea     rcx, [rbp+600h+var_550]; Buffer
0x18008470f  mov     edx, 1; ElementSize
0x180084714  mov     r8d, 108h; ElementCount
0x18008471a  call    cs:__imp_fread
0x180084720  cmp     rax, 108h
0x180084726  setz    al
0x180084729  jmp     short loc_18008477A
0x18008472b  mov     rax, [rbx+858h]
0x180084732  test    rax, rax
0x180084735  jz      short loc_18008474F
0x180084737  mov     rcx, [rsi]
0x18008473a  lea     r9, [rbp+600h+var_550]
0x180084741  mov     r8d, 108h
0x180084747  call    cs:__guard_dispatch_icall_fptr
0x18008474d  jmp     short loc_180084775
0x18008474f  mov     rax, [rbx+860h]
0x180084756  test    rax, rax
0x180084759  jz      loc_180085096
0x18008475f  mov     rcx, [rsi]
0x180084762  lea     r9, [rbp+600h+var_550]
0x180084769  mov     r8d, 108h
0x18008476f  call    cs:__guard_dispatch_icall_fptr
0x180084775  shr     eax, 1Fh
0x180084778  xor     al, 1
0x18008477a  test    al, al
0x18008477c  jz      loc_180085096
0x180084782  cmp     [rbp+600h+var_550], 4550h
0x18008478c  jnz     loc_180085096
0x180084792  movzx   eax, [rbp+600h+var_538]
0x180084799  mov     edx, r14d
0x18008479c  mov     [rsp+700h+var_6A0], edx
0x1800847a0  mov     ecx, r14d
0x1800847a3  mov     [rsp+700h+var_6A4], ecx
0x1800847a7  mov     r12d, r14d
0x1800847aa  mov     r13d, r14d
0x1800847ad  cmp     eax, 10Bh
0x1800847b2  jz      short loc_18008480B
0x1800847b4  cmp     eax, 20Bh
0x1800847b9  jnz     loc_180085096
0x1800847bf  mov     eax, [rbp+600h+var_500]
0x1800847c5  mov     [rbx+0CF4h], eax
0x1800847cb  mov     rax, [rbp+600h+var_4CC]
0x1800847d2  cmp     eax, 6
0x1800847d5  jb      short loc_1800847EB
0x1800847d7  mov     edx, [rbp+600h+var_498]
0x1800847dd  mov     ecx, [rbp+600h+var_494]
0x1800847e3  mov     [rsp+700h+var_6A0], edx
0x1800847e7  mov     [rsp+700h+var_6A4], ecx
0x1800847eb  movzx   r11d, [rsp+700h+var_6B0]
0x1800847f1  test    r11b, r11b
0x1800847f4  jz      short loc_180084855
0x1800847f6  cmp     eax, 0Eh
0x1800847f9  jb      short loc_180084855
0x1800847fb  mov     r12d, [rbp+600h+var_458]
0x180084802  mov     r13d, [rbp+600h+var_454]
0x180084809  jmp     short loc_180084855
0x18008480b  mov     eax, [rbp+600h+var_500]
0x180084811  mov     [rbx+0CF4h], eax
0x180084817  mov     rax, [rbp+600h+var_4DC]
0x18008481e  cmp     eax, 6
0x180084821  jb      short loc_180084837
0x180084823  mov     edx, [rbp+600h+var_4A8]
0x180084829  mov     ecx, [rbp+600h+var_4A4]
0x18008482f  mov     [rsp+700h+var_6A0], edx
0x180084833  mov     [rsp+700h+var_6A4], ecx
0x180084837  movzx   r11d, [rsp+700h+var_6B0]
0x18008483d  test    r11b, r11b
0x180084840  jz      short loc_180084855
0x180084842  cmp     eax, 0Eh
0x180084845  jb      short loc_180084855
0x180084847  mov     r12d, [rbp+600h+var_468]
0x18008484e  mov     r13d, [rbp+600h+var_464]
0x180084855  test    edx, edx
0x180084857  jz      loc_180085079
0x18008485d  test    ecx, ecx
0x18008485f  jz      loc_180085079
0x180084865  test    r11b, r11b
0x180084868  jz      short loc_18008487C
0x18008486a  test    r12d, r12d
0x18008486d  jz      loc_180085096
0x180084873  test    r13d, r13d
0x180084876  jz      loc_180085096
0x18008487c  cmp     [rbx+858h], r14
0x180084883  jnz     short loc_180084896
0x180084885  cmp     [rbx+860h], r14
0x18008488c  jz      short loc_180084896
0x18008488e  xor     r13d, r13d
0x180084891  jmp     loc_180084A3A
0x180084896  movzx   ecx, [rbp+600h+var_53C]
0x18008489d  xor     r8d, r8d
0x1800848a0  mov     esi, [rbp+600h+Offset]
0x1800848a6  add     ecx, 18h
0x1800848a9  add     esi, ecx
0x1800848ab  mov     [rsp+700h+var_6A8], r14d
0x1800848b0  movzx   ecx, [rbp+600h+var_54A]
0x1800848b7  mov     eax, r8d
0x1800848ba  mov     qword ptr [rsp+700h+var_698], rcx
0x1800848bf  mov     r10d, r14d
0x1800848c2  mov     [rsp+700h+var_6AC], r14d
0x1800848c7  mov     r15d, r8d
0x1800848ca  mov     [rsp+700h+var_688], eax
0x1800848ce  test    rcx, rcx
0x1800848d1  jz      loc_180084A12
0x1800848d7  test    rdi, rdi
0x1800848da  jz      short loc_180084913
0x1800848dc  xor     r8d, r8d; Origin
0x1800848df  mov     edx, esi; Offset
0x1800848e1  mov     rcx, rdi; Stream
0x1800848e4  call    cs:__imp_fseek
0x1800848ea  test    eax, eax
0x1800848ec  jnz     loc_1800849FA
0x1800848f2  mov     r9, rdi; Stream
0x1800848f5  lea     rcx, [rbp+600h+var_5E0]; Buffer
0x1800848f9  mov     edx, 1; ElementSize
0x1800848fe  mov     r8d, 28h ; '('; ElementCount
0x180084904  call    cs:__imp_fread
0x18008490a  cmp     rax, 28h ; '('
0x18008490e  setz    al
0x180084911  jmp     short loc_18008496A
0x180084913  mov     rax, [rbx+858h]
0x18008491a  test    rax, rax
0x18008491d  jz      short loc_18008493B
0x18008491f  mov     rcx, [rsp+700h+var_690]
0x180084924  lea     r9, [rbp+600h+var_5E0]
0x180084928  mov     edx, esi
0x18008492a  mov     r8d, 28h ; '('
0x180084930  mov     rcx, [rcx]
  ... truncated ...
```
