# CEnumJobs::Next(ulong,ushort * * *,ulong *)

- ea: `0x180005270`
- end: `0x180005bab`
- name: `?Next@CEnumJobs@@UEAAJKPEAPEAPEAGPEAK@Z`
- size: `2363`
- prototype: `__int64 __fastcall(CEnumJobs *__hidden this, unsigned int, unsigned __int16 ***, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001840`
- `0x180005270`
- `0x180009ef8`
- `0x180009f38`
- `0x18001aa82`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000548b`
- `msvcrt!wcsrchr` at `0x18000552e`
- `msvcrt!wcsrchr` at `0x18000587d`
- `msvcrt!wcsrchr` at `0x18000595e`
- `msvcrt!wcsrchr` at `0x18000548b`
- `msvcrt!wcsrchr` at `0x18000552e`
- `msvcrt!wcsrchr` at `0x18000587d`
- `msvcrt!wcsrchr` at `0x18000595e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b38`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000551a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000594a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000551a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000594a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000546d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000585f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000546d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000585f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180005577`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180005993`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180005577`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180005993`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800054a0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005543`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005896`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005973`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800054a0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005543`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005896`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005973`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800055f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005920`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800059f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800055f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005920`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800059f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800055a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800055d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800059cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005a16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800055a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800055d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800059cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005a16`

## pseudocode

```c
__int64 __fastcall CEnumJobs::Next(CEnumJobs *this, unsigned int a2, LPVOID *a3, unsigned int *a4)
{
  unsigned int v7; // esi
  unsigned __int16 *v8; // r12
  unsigned int v9; // r13d
  _WORD *v10; // rdx
  __int64 v11; // rcx
  _WORD *v12; // r8
  __int64 v13; // r9
  _WORD *v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rbx
  WCHAR *v17; // rdx
  WCHAR *v18; // r8
  __int64 v19; // rcx
  __int64 v20; // r9
  WCHAR *v21; // rcx
  WCHAR *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // r9
  const wchar_t *v25; // r8
  bool v26; // zf
  __int64 v27; // rdx
  __int64 v28; // rcx
  WCHAR *v29; // r9
  WCHAR *v30; // rcx
  HANDLE FirstFileW; // rax
  wchar_t *v32; // rax
  __int64 v33; // rax
  unsigned __int64 v34; // rbx
  unsigned __int16 *v35; // rax
  __int64 result; // rax
  wchar_t *v37; // rax
  signed int LastError; // eax
  unsigned __int16 **v39; // rax
  __int64 v40; // rax
  _QWORD *v41; // rbx
  unsigned __int64 v42; // rdi
  _WORD *v43; // rcx
  _WORD *v44; // r8
  __int64 v45; // rcx
  unsigned __int16 *v46; // rdx
  _WORD *v47; // rcx
  unsigned int v48; // eax
  int v49; // r13d
  unsigned int v50; // r15d
  __int64 v51; // r14
  signed int v52; // edi
  _WORD *v53; // rcx
  __int64 v54; // rdx
  _WORD *v55; // r8
  __int64 v56; // r9
  _WORD *v57; // rcx
  _QWORD *v58; // rcx
  __int64 v59; // rbx
  WCHAR *v60; // rdx
  WCHAR *v61; // r8
  __int64 v62; // rcx
  __int64 v63; // r9
  WCHAR *v64; // rcx
  __int64 v65; // rcx
  WCHAR *v66; // rax
  __int64 v67; // rdx
  const wchar_t *v68; // r9
  __int64 v69; // rax
  __int64 v70; // rcx
  WCHAR *v71; // rdx
  WCHAR *v72; // rcx
  HANDLE v73; // rax
  wchar_t *v74; // rax
  __int64 v75; // rax
  unsigned __int64 v76; // rbx
  bool v77; // sf
  int v78; // edi
  LPVOID *i; // rbx
  wchar_t *v80; // rax
  signed int v81; // eax
  unsigned __int16 **v82; // rbx
  unsigned __int16 **v83; // rax
  __int64 v84; // rdi
  __int64 v85; // rbx
  unsigned __int64 v86; // rbx
  unsigned __int16 *v87; // r8
  __int64 v88; // rcx
  unsigned __int16 *v89; // rdx
  unsigned __int16 *v90; // rcx
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp+190h] BYREF

  if ( !a2 || a2 > 1 && !a4 || !a3 )
    return 2147942487LL;
  v7 = 0;
  *a3 = 0;
  if ( *((_DWORD *)this + 149) )
  {
    if ( a4 )
      *a4 = 0;
    return 1;
  }
  else
  {
    v8 = 0;
    v9 = 0;
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    while ( 1 )
    {
      if ( *((_QWORD *)this + 1) != -1 )
        goto LABEL_42;
      v10 = (_WORD *)*((_QWORD *)this + 2);
      if ( !v10 )
      {
        v9 = 1;
        *((_DWORD *)this + 149) = 1;
        goto LABEL_39;
      }
      v11 = 2147483646;
      v12 = (_WORD *)((char *)this + 32);
      v13 = 261;
      do
      {
        if ( !v11 )
          break;
        if ( !*v10 )
          break;
        *v12++ = *v10++;
        --v11;
        --v13;
      }
      while ( v13 );
      v14 = v12 - 1;
      if ( v13 )
        v14 = v12;
      *v14 = 0;
      v15 = (_QWORD *)*((_QWORD *)this + 2);
      v16 = v15[66];
      operator delete(v15);
      *((_QWORD *)this + 2) = v16;
      memset_0(FileName, 0, 0x20Au);
      v17 = (WCHAR *)*((_QWORD *)this + 3);
      v18 = FileName;
      v19 = 2147483646;
      v20 = 261;
      do
      {
        if ( !v19 )
          break;
        if ( !*v17 )
          break;
        *v18++ = *v17++;
        --v19;
        --v20;
      }
      while ( v20 );
      v21 = v18 - 1;
      v22 = FileName;
      if ( v20 )
        v21 = v18;
      *v21 = 0;
      v23 = 261;
      do
      {
        if ( !*v22 )
          break;
        ++v22;
        --v23;
      }
      while ( v23 );
      v24 = 261 - v23;
      if ( v23 )
      {
        v25 = L"\\*";
        v27 = v23;
        v26 = v24 == 261;
        v28 = 2147483646;
        v29 = &FileName[v24];
        if ( !v26 )
        {
          do
          {
            if ( !v28 )
              break;
            if ( !*v25 )
              break;
            *v29++ = *v25++;
            --v28;
            --v27;
          }
          while ( v27 );
        }
        v30 = v29 - 1;
        if ( v27 )
          v30 = v29;
        *v30 = 0;
      }
      FirstFileW = FindFirstFileW(FileName, &FindFileData);
      *((_QWORD *)this + 1) = FirstFileW;
      if ( FirstFileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError == 2 )
          goto LABEL_147;
        if ( LastError > 0 )
LABEL_51:
          v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_52:
        if ( !v9 )
        {
          v7 = 0;
          goto LABEL_54;
        }
LABEL_39:
        if ( a4 )
          *a4 = 0;
        *a3 = 0;
        return v9;
      }
      v32 = wcsrchr(FindFileData.cFileName, 0x2Eu);
      if ( v32 )
      {
        if ( !lstrcmpiW(v32, (LPCWSTR)this + 277) )
          break;
      }
LABEL_42:
      while ( FindNextFileW(*((HANDLE *)this + 1), &FindFileData) )
      {
        v37 = wcsrchr(FindFileData.cFileName, 0x2Eu);
        if ( v37 && !lstrcmpiW(v37, (LPCWSTR)this + 277) )
          goto LABEL_34;
      }
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError != 18 )
      {
        if ( LastError > 0 )
          goto LABEL_51;
        goto LABEL_52;
      }
      FindClose(*((HANDLE *)this + 1));
      *((_QWORD *)this + 1) = -1;
    }
LABEL_34:
    if ( !v9 )
    {
      v33 = -1;
      do
        ++v33;
      while ( FindFileData.cFileName[v33] );
      v34 = (int)v33 + 1LL;
      v35 = (unsigned __int16 *)operator new(saturated_mul(v34, 2u));
      v8 = v35;
      if ( !v35 )
      {
        v9 = -2147024882;
        goto LABEL_39;
      }
      *v35 = 0;
      StringCchCopyW(v35, v34, FindFileData.cFileName);
    }
LABEL_147:
    ++*((_DWORD *)this + 147);
LABEL_54:
    v39 = (unsigned __int16 **)CoTaskMemAlloc(8u);
    *a3 = v39;
    if ( !v39 )
    {
      if ( a4 )
        *a4 = 0;
      goto LABEL_61;
    }
    v40 = -1;
    do
      v26 = v8[++v40] == 0;
    while ( !v26 );
    v41 = *a3;
    v42 = v40 + 1;
    *v41 = CoTaskMemAlloc(2 * (v40 + 1));
    v43 = *(_WORD **)*a3;
    if ( !v43 )
    {
      if ( a4 )
        *a4 = 0;
      CoTaskMemFree(*a3);
      *a3 = 0;
LABEL_61:
      operator delete(v8);
      return 2147942414LL;
    }
    *v43 = 0;
    if ( v42 )
    {
      v44 = *(_WORD **)*a3;
      if ( v42 > 0x7FFFFFFF )
      {
        *v44 = 0;
      }
      else
      {
        v45 = 2147483646;
        v46 = v8;
        do
        {
          if ( !v45 )
            break;
          if ( !*v46 )
            break;
          *v44++ = *v46++;
          --v45;
          --v42;
        }
        while ( v42 );
        v47 = v44 - 1;
        if ( v42 )
          v47 = v44;
        *v47 = 0;
      }
    }
    operator delete(v8);
    v48 = a2;
    if ( a2 == 1 )
    {
      if ( a4 )
        *a4 = 1;
      return 0;
    }
    else
    {
      v49 = 1;
      v50 = 1;
      while ( 1 )
      {
        v51 = v50++;
        if ( v50 > v48 )
          break;
        v52 = 0;
        memset_0(&FindFileData, 0, sizeof(FindFileData));
        while ( 1 )
        {
          if ( *((_QWORD *)this + 1) != -1 )
            goto LABEL_116;
          v53 = (_WORD *)*((_QWORD *)this + 2);
          if ( !v53 )
          {
            *((_DWORD *)this + 149) = 1;
LABEL_112:
            v7 = v49;
            v77 = v49 < 0;
LABEL_113:
            if ( !v77 )
              goto LABEL_77;
LABEL_114:
            v78 = 0;
            for ( i = (LPVOID *)*a3; v78 < (int)v51; ++v78 )
              CoTaskMemFree(i[v78]);
            CoTaskMemFree(i);
            operator delete(v8);
            *a4 = 0;
            result = v7;
            *a3 = 0;
            return result;
          }
          v54 = 2147483646;
          v55 = (_WORD *)((char *)this + 32);
          v56 = 261;
          do
          {
            if ( !v54 )
              break;
            if ( !*v53 )
              break;
            *v55++ = *v53++;
            --v54;
            --v56;
          }
          while ( v56 );
          v57 = v55 - 1;
          if ( v56 )
            v57 = v55;
          *v57 = 0;
          v58 = (_QWORD *)*((_QWORD *)this + 2);
          v59 = v58[66];
          operator delete(v58);
          *((_QWORD *)this + 2) = v59;
          memset_0(FileName, 0, 0x20Au);
          v60 = (WCHAR *)*((_QWORD *)this + 3);
          v61 = FileName;
          v62 = 2147483646;
          v63 = 261;
          do
          {
            if ( !v62 )
              break;
            if ( !*v60 )
              break;
            *v61++ = *v60++;
            --v62;
            --v63;
          }
          while ( v63 );
          v64 = v61 - 1;
          if ( v63 )
            v64 = v61;
          *v64 = 0;
          v65 = 261;
          v66 = FileName;
          do
          {
            if ( !*v66 )
              break;
            ++v66;
            --v65;
          }
          while ( v65 );
          v67 = 261 - v65;
          if ( v65 )
          {
            v68 = L"\\*";
            v69 = v65;
            v26 = v67 == 261;
            v70 = 2147483646;
            v71 = &FileName[v67];
            if ( !v26 )
            {
              do
              {
                if ( !v70 )
                  break;
                if ( !*v68 )
                  break;
                *v71++ = *v68++;
                --v70;
                --v69;
              }
              while ( v69 );
            }
            v72 = v71 - 1;
            if ( v69 )
              v72 = v71;
            *v72 = 0;
          }
          v73 = FindFirstFileW(FileName, &FindFileData);
          *((_QWORD *)this + 1) = v73;
          if ( v73 == (HANDLE)-1LL )
            break;
          v74 = wcsrchr(FindFileData.cFileName, 0x2Eu);
          if ( v74 && !lstrcmpiW(v74, (LPCWSTR)this + 277) )
          {
LABEL_107:
            if ( !v52 )
            {
              v75 = -1;
              do
                ++v75;
              while ( FindFileData.cFileName[v75] );
              v76 = (int)v75 + 1LL;
              v8 = (unsigned __int16 *)operator new(saturated_mul(v76, 2u));
              if ( !v8 )
              {
                v49 = -2147024882;
                goto LABEL_112;
              }
              *v8 = 0;
              StringCchCopyW(v8, v76, FindFileData.cFileName);
            }
LABEL_157:
            ++*((_DWORD *)this + 147);
            v7 = 0;
            goto LABEL_125;
          }
LABEL_116:
          while ( FindNextFileW(*((HANDLE *)this + 1), &FindFileData) )
          {
            v80 = wcsrchr(FindFileData.cFileName, 0x2Eu);
            if ( v80 && !lstrcmpiW(v80, (LPCWSTR)this + 277) )
              goto LABEL_107;
          }
          v81 = GetLastError();
          v52 = v81;
          if ( v81 != 18 )
          {
            if ( v81 > 0 )
              goto LABEL_123;
            goto LABEL_124;
          }
          FindClose(*((HANDLE *)this + 1));
          *((_QWORD *)this + 1) = -1;
        }
        v81 = GetLastError();
        v52 = v81;
        if ( v81 == 2 )
          goto LABEL_157;
        if ( v81 > 0 )
LABEL_123:
          v52 = (unsigned __int16)v81 | 0x80070000;
LABEL_124:
        v7 = v52;
        v77 = v52 < 0;
        if ( v52 )
          goto LABEL_113;
LABEL_125:
        v82 = (unsigned __int16 **)*a3;
        v83 = (unsigned __int16 **)CoTaskMemAlloc(8LL * v50);
        *a3 = v83;
        if ( !v83 )
        {
          *a3 = v82;
LABEL_161:
          v7 = -2147024882;
          goto LABEL_114;
        }
        v84 = 8 * v51;
        memcpy_0(v83, v82, 8 * v51);
        CoTaskMemFree(v82);
        v85 = -1;
        do
          ++v85;
        while ( v8[v85] );
        v86 = v85 + 1;
        *(_QWORD *)((char *)*a3 + v84) = CoTaskMemAlloc(2 * v86);
        v87 = *(unsigned __int16 **)((char *)*a3 + v84);
        if ( !v87 )
          goto LABEL_161;
        if ( v86 )
        {
          if ( v86 > 0x7FFFFFFF )
          {
            *v87 = 0;
          }
          else
          {
            v88 = 2147483646;
            v89 = v8;
            do
            {
              if ( !v88 )
                break;
              if ( !*v89 )
                break;
              *v87++ = *v89++;
              --v88;
              --v86;
            }
            while ( v86 );
            v90 = v87 - 1;
            if ( v86 )
              v90 = v87;
            *v90 = 0;
          }
        }
        operator delete(v8);
        v48 = a2;
        v8 = 0;
      }
LABEL_77:
      *a4 = v51;
      return v7;
    }
  }
}

```

## disassembly

```asm
0x180005270  push    rbp
0x180005272  push    rdi
0x180005273  push    r14
0x180005275  push    r15
0x180005277  lea     rbp, [rsp-3C8h]
0x18000527f  sub     rsp, 4C8h
0x180005286  mov     rax, cs:__security_cookie
0x18000528d  xor     rax, rsp
0x180005290  mov     [rbp+3E0h+var_40], rax
0x180005297  mov     [rsp+4E0h+var_4B0], r9
0x18000529c  mov     r15, r9
0x18000529f  mov     [rsp+4E0h+var_4B8], r8
0x1800052a4  mov     r14, r8
0x1800052a7  mov     [rsp+4E0h+var_4C0], edx
0x1800052ab  mov     eax, edx
0x1800052ad  mov     [rsp+4E0h+var_4A8], rcx
0x1800052b2  mov     rdi, rcx
0x1800052b5  test    edx, edx
0x1800052b7  jz      loc_18000555B
0x1800052bd  cmp     eax, 1
0x1800052c0  ja      loc_180005552
0x1800052c6  test    r14, r14
0x1800052c9  jz      loc_18000555B
0x1800052cf  mov     [rsp+4E0h+var_20], rsi
0x1800052d7  xor     esi, esi
0x1800052d9  mov     [r8], rsi
0x1800052dc  mov     [rsp+4E0h+var_30], r13
0x1800052e4  cmp     [rcx+254h], esi
0x1800052ea  jnz     loc_18000564F
0x1800052f0  mov     [rsp+4E0h+arg_8], rbx
0x1800052f8  lea     rcx, [rsp+4E0h+FindFileData]; void *
0x1800052fd  mov     [rsp+4E0h+var_28], r12
0x180005305  xor     edx, edx; Val
0x180005307  mov     r8d, 250h; Size
0x18000530d  mov     r12d, esi
0x180005310  mov     r13d, esi
0x180005313  call    memset_0
0x180005318  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000531f  cmp     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x180005324  jnz     loc_180005511
0x18000532a  mov     rdx, [rdi+10h]
0x18000532e  test    rdx, rdx
0x180005331  jz      loc_180005AC9
0x180005337  mov     ecx, 7FFFFFFEh
0x18000533c  lea     r8, [rdi+20h]
0x180005340  mov     r9d, 105h
0x180005346  test    rcx, rcx
0x180005349  jz      short loc_180005368
0x18000534b  movzx   eax, word ptr [rdx]
0x18000534e  test    ax, ax
0x180005351  jz      short loc_180005368
0x180005353  mov     [r8], ax
0x180005357  add     rdx, 2
0x18000535b  add     r8, 2
0x18000535f  dec     rcx
0x180005362  sub     r9, 1
0x180005366  jnz     short loc_180005346
0x180005368  test    r9, r9
0x18000536b  lea     rcx, [r8-2]
0x18000536f  cmovnz  rcx, r8
0x180005373  mov     [rcx], si
0x180005376  mov     rcx, [rdi+10h]; Block
0x18000537a  mov     rbx, [rcx+210h]
0x180005381  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005386  xor     edx, edx; Val
0x180005388  mov     [rdi+10h], rbx
0x18000538c  mov     r8d, 20Ah; Size
0x180005392  lea     rcx, [rbp+3E0h+FileName]; void *
0x180005399  call    memset_0
0x18000539e  mov     rdx, [rdi+18h]
0x1800053a2  lea     r8, [rbp+3E0h+FileName]
0x1800053a9  mov     ecx, 7FFFFFFEh
0x1800053ae  mov     r9d, 105h
0x1800053b4  test    rcx, rcx
0x1800053b7  jz      short loc_1800053D6
0x1800053b9  movzx   eax, word ptr [rdx]
0x1800053bc  test    ax, ax
0x1800053bf  jz      short loc_1800053D6
0x1800053c1  mov     [r8], ax
0x1800053c5  add     rdx, 2
0x1800053c9  add     r8, 2
0x1800053cd  dec     rcx
0x1800053d0  sub     r9, 1
0x1800053d4  jnz     short loc_1800053B4
0x1800053d6  test    r9, r9
0x1800053d9  lea     rcx, [r8-2]
0x1800053dd  lea     rax, [rbp+3E0h+FileName]
0x1800053e4  cmovnz  rcx, r8
0x1800053e8  mov     [rcx], si
0x1800053eb  mov     ecx, 105h
0x1800053f0  cmp     [rax], si
0x1800053f3  jz      short loc_1800053FF
0x1800053f5  add     rax, 2
0x1800053f9  sub     rcx, 1
0x1800053fd  jnz     short loc_1800053F0
0x1800053ff  mov     r9d, 105h
0x180005405  sub     r9, rcx
0x180005408  test    rcx, rcx
0x18000540b  cmovz   r9, rsi
0x18000540f  jz      short loc_180005461
0x180005411  mov     edx, 105h
0x180005416  lea     r8, asc_18001D984; "\\*"
0x18000541d  sub     rdx, r9
0x180005420  mov     ecx, 7FFFFFFEh
0x180005425  lea     r9, [rbp+r9*2+3E0h+FileName]
0x18000542d  jz      short loc_180005453
0x18000542f  nop
0x180005430  test    rcx, rcx
0x180005433  jz      short loc_180005453
0x180005435  movzx   eax, word ptr [r8]
0x180005439  test    ax, ax
0x18000543c  jz      short loc_180005453
0x18000543e  mov     [r9], ax
0x180005442  add     r8, 2
0x180005446  add     r9, 2
0x18000544a  dec     rcx
0x18000544d  sub     rdx, 1
0x180005451  jnz     short loc_180005430
0x180005453  test    rdx, rdx
0x180005456  lea     rcx, [r9-2]
0x18000545a  cmovnz  rcx, r9
0x18000545e  mov     [rcx], si
0x180005461  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x180005466  lea     rcx, [rbp+3E0h+FileName]; lpFileName
0x18000546d  call    cs:__imp_FindFirstFileW
0x180005473  mov     [rdi+8], rax
0x180005477  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000547b  jz      loc_180005AB9
0x180005481  mov     edx, 2Eh ; '.'; Ch
0x180005486  lea     rcx, [rsp+4E0h+FindFileData.cFileName]; Str
0x18000548b  call    cs:__imp_wcsrchr
0x180005491  test    rax, rax
0x180005494  jz      short loc_18000550A
0x180005496  lea     rdx, [rdi+22Ah]; lpString2
0x18000549d  mov     rcx, rax; lpString1
0x1800054a0  call    cs:__imp_lstrcmpiW
0x1800054a6  test    eax, eax
0x1800054a8  jnz     short loc_18000550A
0x1800054aa  test    r13d, r13d
0x1800054ad  jnz     loc_180005AEE
0x1800054b3  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800054ba  lea     rcx, [rsp+4E0h+FindFileData.cFileName]
0x1800054bf  mov     rax, r8
0x1800054c2  inc     rax
0x1800054c5  cmp     [rcx+rax*2], si
0x1800054c9  jnz     short loc_1800054C2
0x1800054cb  movsxd  rbx, eax
0x1800054ce  mov     eax, 2
0x1800054d3  inc     rbx
0x1800054d6  mul     rbx
0x1800054d9  cmovb   rax, r8
0x1800054dd  mov     rcx, rax; Size
0x1800054e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800054e5  mov     r12, rax
0x1800054e8  test    rax, rax
0x1800054eb  jnz     loc_180005ADB
0x1800054f1  mov     r13d, 8007000Eh
0x1800054f7  test    r15, r15
0x1800054fa  jz      short loc_1800054FF
0x1800054fc  mov     [r15], esi
0x1800054ff  mov     [r14], rsi
0x180005502  mov     eax, r13d
0x180005505  jmp     loc_180005612
0x18000550a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180005511  mov     rcx, [rdi+8]; hFindFile
0x180005515  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x18000551a  call    cs:__imp_FindNextFileW
0x180005520  test    eax, eax
0x180005522  jz      short loc_180005565
0x180005524  mov     edx, 2Eh ; '.'; Ch
0x180005529  lea     rcx, [rsp+4E0h+FindFileData.cFileName]; Str
0x18000552e  call    cs:__imp_wcsrchr
0x180005534  test    rax, rax
0x180005537  jz      short loc_180005511
0x180005539  lea     rdx, [rdi+22Ah]; lpString2
0x180005540  mov     rcx, rax; lpString1
0x180005543  call    cs:__imp_lstrcmpiW
0x180005549  test    eax, eax
0x18000554b  jnz     short loc_180005511
0x18000554d  jmp     loc_1800054AA
0x180005552  test    r15, r15
0x180005555  jnz     loc_1800052C6
0x18000555b  mov     eax, 80070057h
0x180005560  jmp     loc_180005632
0x180005565  call    cs:__imp_GetLastError
0x18000556b  mov     r13d, eax
0x18000556e  cmp     eax, 12h
0x180005571  jnz     short loc_180005586
0x180005573  mov     rcx, [rdi+8]; hFindFile
0x180005577  call    cs:__imp_FindClose
0x18000557d  mov     [rdi+8], rbx
0x180005581  jmp     loc_18000531F
0x180005586  test    eax, eax
0x180005588  jle     short loc_180005595
0x18000558a  movzx   r13d, ax
0x18000558e  or      r13d, 80070000h
0x180005595  test    r13d, r13d
0x180005598  jnz     loc_1800054F7
0x18000559e  mov     esi, r13d
0x1800055a1  mov     ecx, 8; cb
0x1800055a6  call    cs:__imp_CoTaskMemAlloc
0x1800055ac  mov     [r14], rax
0x1800055af  test    rax, rax
0x1800055b2  jz      loc_180005AF9
0x1800055b8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800055bf  nop
0x1800055c0  cmp     word ptr [r12+rax*2+2], 0
0x1800055c7  lea     rax, [rax+1]
0x1800055cb  jnz     short loc_1800055C0
0x1800055cd  mov     rbx, [r14]
0x1800055d0  lea     rdi, [rax+1]
0x1800055d4  lea     rcx, [rdi+rdi]; cb
0x1800055d8  call    cs:__imp_CoTaskMemAlloc
0x1800055de  mov     [rbx], rax
0x1800055e1  mov     rax, [r14]
0x1800055e4  mov     rcx, [rax]
0x1800055e7  test    rcx, rcx
0x1800055ea  jnz     short loc_18000565F
0x1800055ec  test    r15, r15
0x1800055ef  jnz     loc_180005B0E
0x1800055f5  mov     rcx, [r14]; pv
0x1800055f8  call    cs:__imp_CoTaskMemFree
0x1800055fe  mov     qword ptr [r14], 0
0x180005605  mov     rcx, r12; Block
0x180005608  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000560d  mov     eax, 8007000Eh
0x180005612  mov     r12, [rsp+4E0h+var_28]
0x18000561a  mov     rbx, [rsp+4E0h+arg_8]
0x180005622  mov     r13, [rsp+4E0h+var_30]
0x18000562a  mov     rsi, [rsp+4E0h+var_20]
0x180005632  mov     rcx, [rbp+3E0h+var_40]
0x180005639  xor     rcx, rsp; StackCookie
0x18000563c  call    __security_check_cookie
0x180005641  add     rsp, 4C8h
0x180005648  pop     r15
0x18000564a  pop     r14
0x18000564c  pop     rdi
0x18000564d  pop     rbp
0x18000564e  retn
0x18000564f  test    r15, r15
0x180005652  jnz     loc_180005AB1
0x180005658  mov     eax, 1
0x18000565d  jmp     short loc_180005622
0x18000565f  xor     eax, eax
0x180005661  mov     [rcx], ax
0x180005664  test    rdi, rdi
0x180005667  jz      short loc_1800056B6
0x180005669  mov     rax, [r14]
0x18000566c  mov     r8, [rax]
0x18000566f  cmp     rdi, 7FFFFFFFh
0x180005676  ja      loc_180005B1A
0x18000567c  mov     ecx, 7FFFFFFEh
0x180005681  mov     rdx, r12
0x180005684  test    rcx, rcx
0x180005687  jz      short loc_1800056A6
0x180005689  movzx   eax, word ptr [rdx]
0x18000568c  test    ax, ax
0x18000568f  jz      short loc_1800056A6
0x180005691  mov     [r8], ax
0x180005695  add     rdx, 2
0x180005699  add     r8, 2
0x18000569d  dec     rcx
0x1800056a0  sub     rdi, 1
0x1800056a4  jnz     short loc_180005684
0x1800056a6  test    rdi, rdi
0x1800056a9  lea     rcx, [r8-2]
0x1800056ad  cmovnz  rcx, r8
0x1800056b1  xor     eax, eax
0x1800056b3  mov     [rcx], ax
0x1800056b6  mov     rcx, r12; Block
0x1800056b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800056be  mov     eax, [rsp+4E0h+var_4C0]
0x1800056c2  cmp     eax, 1
0x1800056c5  jz      loc_180005B25
0x1800056cb  mov     r13d, 1
0x1800056d1  mov     r15d, r13d
0x1800056d4  mov     r14d, r15d
0x1800056d7  inc     r15d
0x1800056da  cmp     r15d, eax
0x1800056dd  jbe     short loc_1800056EE
0x1800056df  mov     rax, [rsp+4E0h+var_4B0]
0x1800056e4  mov     [rax], r14d
0x1800056e7  mov     eax, esi
0x1800056e9  jmp     loc_180005612
0x1800056ee  xor     edi, edi
0x1800056f0  lea     rcx, [rsp+4E0h+FindFileData]; void *
0x1800056f5  xor     edx, edx; Val
0x1800056f7  mov     r8d, 250h; Size
0x1800056fd  call    memset_0
0x180005702  mov     rsi, [rsp+4E0h+var_4A8]
0x180005707  cmp     qword ptr [rsi+8], 0FFFFFFFFFFFFFFFFh
0x18000570c  jnz     loc_180005941
0x180005712  mov     rcx, [rsi+10h]
0x180005716  test    rcx, rcx
0x180005719  jz      loc_180005B79
0x18000571f  mov     edx, 7FFFFFFEh
0x180005724  lea     r8, [rsi+20h]
0x180005728  mov     r9d, 105h
0x18000572e  xchg    ax, ax
0x180005730  test    rdx, rdx
  ... truncated ...
```
