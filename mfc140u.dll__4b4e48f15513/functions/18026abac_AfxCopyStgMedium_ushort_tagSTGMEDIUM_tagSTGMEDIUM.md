# _AfxCopyStgMedium(ushort,tagSTGMEDIUM *,tagSTGMEDIUM *)

- ea: `0x18026abac`
- end: `0x18026b0c7`
- name: `?_AfxCopyStgMedium@@YAHGPEAUtagSTGMEDIUM@@0@Z`
- size: `1307`
- prototype: `int __fastcall(unsigned __int16 cfFormat, tagSTGMEDIUM *lpDest, tagSTGMEDIUM *lpSource)`
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x18025db70`
- `0x18025de30`
- `0x18025eb90`
- `0x18025ecb0`

## callees

- `0x180003230`
- `0x1800033dc`
- `0x180003450`
- `0x18000ddc0`
- `0x18000df50`
- `0x180231d70`
- `0x18026aaa0`
- `0x18026abac`
- `0x1802bbce0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x18026ac97`
- `KERNEL32!GlobalLock` at `0x18026ac97`
- `KERNEL32!GlobalUnlock` at `0x18026acb8`
- `KERNEL32!GlobalUnlock` at `0x18026acce`
- `KERNEL32!GlobalUnlock` at `0x18026acb8`
- `KERNEL32!GlobalUnlock` at `0x18026acce`
- `KERNEL32!GlobalFree` at `0x18026acc1`
- `KERNEL32!GlobalFree` at `0x18026acc1`
- `KERNEL32!CopyFileW` at `0x18026b004`
- `KERNEL32!CopyFileW` at `0x18026b004`
- `VCRUNTIME140!memmove` at `0x18026af7d`
- `VCRUNTIME140!memmove` at `0x18026af7d`
- `VCRUNTIME140!memset` at `0x18026afac`
- `VCRUNTIME140!memset` at `0x18026b0a9`
- `VCRUNTIME140!memset` at `0x18026afac`
- `VCRUNTIME140!memset` at `0x18026b0a9`
- `VCRUNTIME140!memcpy` at `0x18026ad8e`
- `VCRUNTIME140!memcpy` at `0x18026afa2`
- `VCRUNTIME140!memcpy` at `0x18026ad8e`
- `VCRUNTIME140!memcpy` at `0x18026afa2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18026afbe`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18026b0bb`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18026afbe`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18026b0bb`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026af5d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026afb2`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026b0af`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026af5d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026afb2`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026b0af`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026ad41`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026aef6`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026ad41`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026aef6`
- `GDI32!CopyMetaFileW` at `0x18026aca6`
- `GDI32!CopyMetaFileW` at `0x18026aca6`
- `ole32!CoTaskMemAlloc` at `0x18026ad5a`
- `ole32!CoTaskMemAlloc` at `0x18026ad5a`
- `ole32!OleDuplicateData` at `0x18026ac6d`
- `ole32!OleDuplicateData` at `0x18026ac6d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _AfxCopyStgMedium(CLIPFORMAT cfFormat, tagSTGMEDIUM *lpDest, tagSTGMEDIUM *lpSource)
{
  __int64 v5; // rdx
  HBITMAP__ *v6; // rax
  HBITMAP__ *v7; // rax
  HBITMAP__ *v8; // rsi
  HMETAFILE *v9; // rbx
  HMETAFILE v10; // rax
  HBITMAP__ *v12; // rcx
  HBITMAP__ *v13; // rcx
  HBITMAP__ *hBitmap; // rcx
  size_t v15; // rbx
  HBITMAP__ *v16; // rax
  HBITMAP__ *v17; // rdx
  HBITMAP__ *v18; // r13
  wchar_t *m_pszData; // rbx
  HINSTANCE__ *StringResourceHandle; // rax
  int v21; // r14d
  unsigned __int64 v22; // r12
  unsigned __int64 v23; // r15
  wchar_t *v24; // rdx
  size_t v25; // r8
  unsigned int v26; // edi
  wchar_t *v27; // rdx
  HBITMAP__ *v28; // rax
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strDest; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v30; // [rsp+38h] [rbp-51h]
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strSource; // [rsp+40h] [rbp-49h] BYREF
  tagSTATSTG stat; // [rsp+50h] [rbp-39h] BYREF

  v5 = cfFormat;
  if ( !lpDest->tymed )
  {
    if ( lpSource->tymed != 1 )
    {
      switch ( lpSource->tymed )
      {
        case 2u:
          lpDest->tymed = 2;
          hBitmap = lpSource->hBitmap;
          if ( hBitmap )
          {
            v15 = 2LL * ((unsigned int)wcslen((const wchar_t *)hBitmap) + 1);
            if ( v15 > 0xFFFFFFFF )
              v16 = 0;
            else
              v16 = (HBITMAP__ *)CoTaskMemAlloc((unsigned int)v15);
            lpDest->hBitmap = v16;
            if ( !v16 )
              return 0;
            v17 = lpSource->hBitmap;
            if ( !v15 )
              return 1;
            if ( v17 )
            {
              memcpy(v16, v17, v15);
              return 1;
            }
            memset(v16, 0, v15);
            *_errno() = 22;
            _invalid_parameter_noinfo();
          }
          AfxThrowInvalidArgException();
        case 4u:
          v13 = lpSource->hBitmap;
          lpDest->hBitmap = v13;
          (*(void (__fastcall **)(HBITMAP__ *, __int64))(*(_QWORD *)v13 + 8LL))(v13, v5);
          lpDest->tymed = 4;
          return 1;
        case 8u:
          v12 = lpSource->hBitmap;
          lpDest->hBitmap = v12;
          (*(void (__fastcall **)(HBITMAP__ *, __int64))(*(_QWORD *)v12 + 8LL))(v12, v5);
          lpDest->tymed = 8;
          return 1;
        case 0x10u:
          lpDest->tymed = 16;
          goto LABEL_10;
        case 0x20u:
          v7 = (HBITMAP__ *)_AfxCopyGlobalMemory(0, lpSource->hBitmap);
          v8 = v7;
          if ( !v7 )
            return 0;
          v9 = (HMETAFILE *)GlobalLock(v7);
          v10 = CopyMetaFileW(v9[2], 0);
          v9[2] = v10;
          if ( !v10 )
          {
            GlobalUnlock(v8);
            GlobalFree(v8);
            return 0;
          }
          GlobalUnlock(v8);
          lpDest->hBitmap = v8;
          lpDest->tymed = 32;
          return 1;
      }
      if ( lpSource->tymed != 64 )
        return 0;
    }
    lpDest->tymed = lpSource->tymed;
LABEL_10:
    lpDest->hBitmap = 0;
  }
  if ( lpSource->tymed == 1 )
  {
    v28 = (HBITMAP__ *)_AfxCopyGlobalMemory(lpDest->hBitmap, lpSource->hBitmap);
    if ( !v28 )
      return 0;
    lpDest->hBitmap = v28;
    return 1;
  }
  if ( lpSource->tymed != 2 )
  {
    if ( lpSource->tymed == 4 )
    {
      if ( (*(unsigned int (__fastcall **)(HBITMAP__ *, tagSTATSTG *, __int64))(*(_QWORD *)lpSource->hBitmap + 96LL))(
             lpSource->hBitmap,
             &stat,
             1) )
      {
        return 0;
      }
      strDest.m_pszData = 0;
      (*(void (__fastcall **)(HBITMAP__ *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)lpDest->hBitmap + 40LL))(
        lpDest->hBitmap,
        0,
        0,
        0);
      (*(void (__fastcall **)(HBITMAP__ *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)lpSource->hBitmap + 40LL))(
        lpSource->hBitmap,
        0,
        0,
        0);
      if ( (*(unsigned int (__fastcall **)(HBITMAP__ *, HBITMAP__ *, _ULARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)lpSource->hBitmap + 56LL))(
             lpSource->hBitmap,
             lpDest->hBitmap,
             stat.cbSize,
             0,
             0) )
      {
        return 0;
      }
      (*(void (__fastcall **)(HBITMAP__ *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)lpDest->hBitmap + 40LL))(
        lpDest->hBitmap,
        0,
        0,
        0);
      (*(void (__fastcall **)(HBITMAP__ *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)lpSource->hBitmap + 40LL))(
        lpSource->hBitmap,
        0,
        0,
        0);
    }
    else
    {
      if ( lpSource->tymed != 8 )
      {
        if ( (lpSource->tymed == 16 || lpSource->tymed == 64) && !lpDest->hBitmap )
        {
          v6 = (HBITMAP__ *)OleDuplicateData(lpSource->hBitmap, cfFormat, 0);
          lpDest->hBitmap = v6;
          if ( v6 )
            return 1;
        }
        return 0;
      }
      if ( (*(unsigned int (__fastcall **)(HBITMAP__ *, _QWORD, _QWORD, _QWORD, HBITMAP__ *))(*(_QWORD *)lpSource->hBitmap
                                                                                            + 56LL))(
             lpSource->hBitmap,
             0,
             0,
             0,
             lpDest->hBitmap) )
      {
        return 0;
      }
    }
    return 1;
  }
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &strSource,
    lpSource->lpszFileName);
  v18 = lpDest->hBitmap;
  m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
  strDest.m_pszData = m_pszData;
  if ( !v18 )
    goto LABEL_63;
  if ( (unsigned __int64)v18 >= 0x10000 )
  {
    v21 = wcslen((const wchar_t *)v18);
    if ( v21 )
    {
      v30 = *((_DWORD *)m_pszData - 4);
      v22 = ((char *)v18 - (char *)m_pszData) >> 1;
      if ( v21 < 0 )
        goto LABEL_73;
      if ( ((1 - *((_DWORD *)m_pszData - 2)) | (*((_DWORD *)m_pszData - 3) - v21)) < 0 )
      {
        ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(&strDest, v21);
        m_pszData = strDest.m_pszData;
      }
      v23 = 2LL * v21;
      if ( v22 > v30 )
      {
        v25 = 2LL * *((int *)m_pszData - 3);
        if ( !v23 )
          goto LABEL_61;
        if ( v25 >= v23 )
        {
          memcpy(m_pszData, v18, 2LL * v21);
          goto LABEL_61;
        }
        memset(m_pszData, 0, v25);
      }
      else
      {
        v24 = &m_pszData[v22];
        if ( !v23 )
          goto LABEL_61;
        if ( !v24 )
        {
          *_errno() = 22;
LABEL_60:
          _invalid_parameter_noinfo();
LABEL_61:
          if ( v21 <= *((_DWORD *)m_pszData - 3) )
          {
            *((_DWORD *)m_pszData - 4) = v21;
            m_pszData[v23 / 2] = 0;
            goto LABEL_65;
          }
LABEL_73:
          ATL::AtlThrowImpl(-2147024809);
        }
        if ( 2LL * *((int *)m_pszData - 3) >= v23 )
        {
          memmove(m_pszData, v24, 2LL * v21);
          goto LABEL_61;
        }
      }
      *_errno() = 34;
      goto LABEL_60;
    }
LABEL_63:
    ATL::CSimpleStringT<wchar_t,1>::Empty(&strDest);
    goto LABEL_64;
  }
  StringResourceHandle = AfxFindStringResourceHandle((unsigned __int16)v18);
  if ( StringResourceHandle )
  {
    ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(
      &strDest,
      StringResourceHandle,
      (unsigned __int16)v18);
LABEL_64:
    m_pszData = strDest.m_pszData;
  }
LABEL_65:
  v26 = CopyFileW(
          (LPCWSTR)((unsigned __int64)strSource.m_pszData & -(__int64)(lpSource->hBitmap != 0)),
          (LPCWSTR)((unsigned __int64)m_pszData & ((unsigned __int128)-(__int128)(unsigned __int64)lpDest->hBitmap >> 64)),
          0);
  if ( _InterlockedDecrement((volatile signed __int32 *)m_pszData - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)m_pszData - 3) + 8LL))(*((_QWORD *)m_pszData - 3));
  v27 = strSource.m_pszData - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)strSource.m_pszData - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 8LL))(*(_QWORD *)v27);
  return v26;
}

```

## disassembly

```asm
0x18026abac  mov     [rsp-8+arg_18], rbx
0x18026abb1  push    rbp
0x18026abb2  push    rsi
0x18026abb3  push    rdi
0x18026abb4  push    r12
0x18026abb6  push    r13
0x18026abb8  push    r14
0x18026abba  push    r15
0x18026abbc  lea     rbp, [rsp-27h]
0x18026abc1  sub     rsp, 0B0h
0x18026abc8  mov     rax, cs:__security_cookie
0x18026abcf  xor     rax, rsp
0x18026abd2  mov     [rbp+57h+var_40], rax
0x18026abd6  mov     rsi, lpSource
0x18026abd9  mov     rdi, lpDest
0x18026abdc  movzx   edx, cfFormat; cfFormat
0x18026abdf  mov     r15d, 1
0x18026abe5  xor     r12d, r12d
0x18026abe8  cmp     [rdi], r12d
0x18026abeb  jnz     short loc_18026AC2F
0x18026abed  mov     ecx, [lpSource]
0x18026abf0  mov     eax, ecx
0x18026abf2  sub     eax, r15d
0x18026abf5  jz      short loc_18026AC29
0x18026abf7  sub     eax, r15d
0x18026abfa  jz      loc_18026AD2E
0x18026ac00  sub     eax, 2
0x18026ac03  jz      loc_18026AD0E
0x18026ac09  sub     eax, 4
0x18026ac0c  jz      loc_18026ACEE
0x18026ac12  sub     eax, 8
0x18026ac15  jz      loc_18026ACE3
0x18026ac1b  sub     eax, 10h
0x18026ac1e  jz      short loc_18026AC81
0x18026ac20  cmp     eax, 20h ; ' '
0x18026ac23  jnz     loc_18026ACC7
0x18026ac29  mov     [rdi], ecx
0x18026ac2b  mov     [rdi+8], r12
0x18026ac2f  mov     ecx, [lpSource]
0x18026ac32  sub     ecx, r15d
0x18026ac35  jz      loc_18026B05A
0x18026ac3b  sub     ecx, r15d
0x18026ac3e  jz      loc_18026AE85
0x18026ac44  sub     ecx, 2
0x18026ac47  jz      loc_18026ADC8
0x18026ac4d  sub     ecx, 4
0x18026ac50  jz      loc_18026AD99
0x18026ac56  sub     ecx, 8
0x18026ac59  jz      short loc_18026AC60
0x18026ac5b  cmp     ecx, 30h ; '0'
0x18026ac5e  jnz     short loc_18026ACC7
0x18026ac60  cmp     [rdi+8], r12
0x18026ac64  jnz     short loc_18026ACC7
0x18026ac66  xor     r8d, r8d; uiFlags
0x18026ac69  mov     rcx, [rsi+8]; hSrc
0x18026ac6d  call    cs:__imp_OleDuplicateData
0x18026ac73  mov     [rdi+8], rax
0x18026ac77  test    rax, rax
0x18026ac7a  jz      short loc_18026ACC7
0x18026ac7c  jmp     loc_18026B074
0x18026ac81  mov     lpDest, [lpSource+8]; hSource
0x18026ac85  xor     ecx, ecx; hDest
0x18026ac87  call    ?_AfxCopyGlobalMemory@@YAPEAXPEAX0@Z; _AfxCopyGlobalMemory(void *,void *)
0x18026ac8c  mov     rsi, rax
0x18026ac8f  test    rax, rax
0x18026ac92  jz      short loc_18026ACC7
0x18026ac94  mov     rcx, rax; hMem
0x18026ac97  call    cs:__imp_GlobalLock
0x18026ac9d  mov     rbx, rax
0x18026aca0  xor     edx, edx; LPCWSTR
0x18026aca2  mov     rcx, [rax+10h]; HMETAFILE
0x18026aca6  call    cs:__imp_CopyMetaFileW
0x18026acac  mov     [rbx+10h], rax
0x18026acb0  mov     rcx, rsi; hMem
0x18026acb3  test    rax, rax
0x18026acb6  jnz     short loc_18026ACCE
0x18026acb8  call    cs:__imp_GlobalUnlock
0x18026acbe  mov     rcx, rsi; hMem
0x18026acc1  call    cs:__imp_GlobalFree
0x18026acc7  xor     eax, eax
0x18026acc9  jmp     loc_18026B077
0x18026acce  call    cs:__imp_GlobalUnlock
0x18026acd4  mov     [rdi+8], rsi
0x18026acd8  mov     dword ptr [rdi], 20h ; ' '
0x18026acde  jmp     loc_18026B074
0x18026ace3  mov     dword ptr [rdi], 10h
0x18026ace9  jmp     loc_18026AC2B
0x18026acee  mov     rcx, [lpSource+8]
0x18026acf2  mov     [rdi+8], rcx
0x18026acf6  mov     rax, [rcx]
0x18026acf9  mov     rax, [rax+8]
0x18026acfd  call    cs:__guard_dispatch_icall_fptr
0x18026ad03  mov     dword ptr [rdi], 8
0x18026ad09  jmp     loc_18026B074
0x18026ad0e  mov     rcx, [lpSource+8]
0x18026ad12  mov     [rdi+8], rcx
0x18026ad16  mov     rax, [rcx]
0x18026ad19  mov     rax, [rax+8]
0x18026ad1d  call    cs:__guard_dispatch_icall_fptr
0x18026ad23  mov     dword ptr [rdi], 4
0x18026ad29  jmp     loc_18026B074
0x18026ad2e  mov     dword ptr [rdi], 2
0x18026ad34  mov     rcx, [lpSource+8]; String
0x18026ad38  test    rcx, rcx
0x18026ad3b  jz      loc_18026B0C1
0x18026ad41  call    cs:__imp_wcslen
0x18026ad47  lea     ebx, [r15+rax]
0x18026ad4b  add     rbx, rbx
0x18026ad4e  mov     eax, 0FFFFFFFFh
0x18026ad53  cmp     rbx, rax
0x18026ad56  ja      short loc_18026AD62
0x18026ad58  mov     ecx, ebx; cb
0x18026ad5a  call    cs:__imp_CoTaskMemAlloc
0x18026ad60  jmp     short loc_18026AD65
0x18026ad62  mov     rax, r12
0x18026ad65  mov     [rdi+8], rax
0x18026ad69  test    rax, rax
0x18026ad6c  jz      loc_18026ACC7
0x18026ad72  mov     lpDest, [rsi+8]; Val
0x18026ad76  test    rbx, rbx
0x18026ad79  jz      loc_18026B074
0x18026ad7f  mov     lpSource, rbx; Size
0x18026ad82  mov     rcx, rax; void *
0x18026ad85  test    lpDest, lpDest
0x18026ad88  jz      loc_18026B0A9
0x18026ad8e  call    cs:__imp_memcpy
0x18026ad94  jmp     loc_18026B074
0x18026ad99  mov     rcx, [lpSource+8]
0x18026ad9d  mov     rax, [rcx]
0x18026ada0  mov     lpDest, [rdi+8]
0x18026ada4  mov     [rsp+0E0h+var_C0], lpDest
0x18026ada9  xor     r9d, r9d
0x18026adac  xor     r8d, r8d
0x18026adaf  xor     edx, edx
0x18026adb1  mov     rax, [rax+38h]
0x18026adb5  call    cs:__guard_dispatch_icall_fptr
0x18026adbb  test    eax, eax
0x18026adbd  jnz     loc_18026ACC7
0x18026adc3  jmp     loc_18026B074
0x18026adc8  mov     rcx, [lpSource+8]
0x18026adcc  mov     rax, [rcx]
0x18026adcf  mov     r8d, r15d
0x18026add2  lea     lpDest, [rbp+57h+stat]
0x18026add6  mov     rax, [rax+60h]
0x18026adda  call    cs:__guard_dispatch_icall_fptr
0x18026ade0  test    eax, eax
0x18026ade2  jnz     loc_18026ACC7
0x18026ade8  mov     [rbp+57h+strDest.m_pszData], r12
0x18026adec  mov     rcx, [rdi+8]
0x18026adf0  mov     rax, [rcx]
0x18026adf3  xor     r9d, r9d
0x18026adf6  xor     r8d, r8d
0x18026adf9  mov     rbx, r12
0x18026adfc  mov     lpDest, rbx
0x18026adff  mov     rax, [rax+28h]
0x18026ae03  call    cs:__guard_dispatch_icall_fptr
0x18026ae09  mov     rcx, [rsi+8]
0x18026ae0d  mov     rax, [rcx]
0x18026ae10  xor     r9d, r9d
0x18026ae13  xor     r8d, r8d
0x18026ae16  mov     lpDest, rbx
0x18026ae19  mov     rax, [rax+28h]
0x18026ae1d  call    cs:__guard_dispatch_icall_fptr
0x18026ae23  mov     rcx, [rsi+8]
0x18026ae27  mov     rax, [rcx]
0x18026ae2a  mov     [rsp+0E0h+var_C0], r12
0x18026ae2f  xor     r9d, r9d
0x18026ae32  mov     lpSource, qword ptr [rbp+57h+stat.cbSize]
0x18026ae36  mov     lpDest, [rdi+8]
0x18026ae3a  mov     rax, [rax+38h]
0x18026ae3e  call    cs:__guard_dispatch_icall_fptr
0x18026ae44  test    eax, eax
0x18026ae46  jnz     loc_18026ACC7
0x18026ae4c  mov     rcx, [rdi+8]
0x18026ae50  mov     rax, [rcx]
0x18026ae53  xor     r9d, r9d
0x18026ae56  xor     r8d, r8d
0x18026ae59  mov     lpDest, rbx
0x18026ae5c  mov     rax, [rax+28h]
0x18026ae60  call    cs:__guard_dispatch_icall_fptr
0x18026ae66  mov     rcx, [rsi+8]
0x18026ae6a  mov     rax, [rcx]
0x18026ae6d  xor     r9d, r9d
0x18026ae70  xor     r8d, r8d
0x18026ae73  mov     lpDest, rbx
0x18026ae76  mov     rax, [rax+28h]
0x18026ae7a  call    cs:__guard_dispatch_icall_fptr
0x18026ae80  jmp     loc_18026B074
0x18026ae85  mov     lpDest, [lpSource+8]; pszSrc
0x18026ae89  lea     rcx, [rbp+57h+strSource]; this
0x18026ae8d  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x18026ae92  nop
0x18026ae93  mov     r13, [rdi+8]
0x18026ae97  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x18026ae9e  lea     rcx, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x18026aea5  mov     rax, [rax+18h]
0x18026aea9  call    cs:__guard_dispatch_icall_fptr
0x18026aeaf  lea     rbx, [rax+18h]
0x18026aeb3  mov     [rbp+57h+strDest.m_pszData], rbx
0x18026aeb7  test    r13, r13
0x18026aeba  jz      loc_18026AFD9
0x18026aec0  cmp     r13, 10000h
0x18026aec7  jnb     short loc_18026AEF3
0x18026aec9  movzx   r14d, r13w
0x18026aecd  mov     ecx, r14d; nID
0x18026aed0  call    ?AfxFindStringResourceHandle@@YAPEAUHINSTANCE__@@I@Z; AfxFindStringResourceHandle(uint)
0x18026aed5  nop
0x18026aed6  test    rax, rax
0x18026aed9  jz      loc_18026AFE6
0x18026aedf  mov     r8d, r14d; nID
0x18026aee2  mov     lpDest, rax; hInstance
0x18026aee5  lea     rcx, [rbp+57h+strDest]; this
0x18026aee9  call    ?LoadStringW@?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(HINSTANCE__ *,uint)
0x18026aeee  jmp     loc_18026AFE2
0x18026aef3  mov     rcx, r13; String
0x18026aef6  call    cs:__imp_wcslen
0x18026aefc  mov     r14, rax
0x18026aeff  test    eax, eax
0x18026af01  jz      loc_18026AFD9
0x18026af07  mov     eax, [rbx-10h]
0x18026af0a  mov     [rbp+57h+var_A8], eax
0x18026af0d  mov     r12, r13
0x18026af10  sub     r12, rbx
0x18026af13  sar     r12, 1
0x18026af16  test    r14d, r14d
0x18026af19  js      loc_18026B09E
0x18026af1f  sub     r15d, [rbx-8]
0x18026af23  mov     eax, [rbx-0Ch]
0x18026af26  sub     eax, r14d
0x18026af29  or      eax, r15d
0x18026af2c  jge     short loc_18026AF3E
0x18026af2e  mov     edx, r14d; nLength
0x18026af31  lea     rcx, [rbp+57h+strDest]; this
0x18026af35  call    ?PrepareWrite2@?$CSimpleStringT@_W$00@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(int)
0x18026af3a  mov     rbx, [rbp+57h+strDest.m_pszData]
0x18026af3e  movsxd  r15, r14d
0x18026af41  add     r15, r15
0x18026af44  mov     eax, [rbp+57h+var_A8]
0x18026af47  cmp     r12, rax
0x18026af4a  ja      short loc_18026AF85
0x18026af4c  lea     lpDest, [rbx+r12*2]; Src
0x18026af50  xor     r12d, r12d
0x18026af53  test    r15, r15
0x18026af56  jz      short loc_18026AFC4
0x18026af58  test    lpDest, lpDest
0x18026af5b  jnz     short loc_18026AF6B
0x18026af5d  call    cs:__imp__errno
0x18026af63  mov     dword ptr [rax], 16h
0x18026af69  jmp     short loc_18026AFBE
0x18026af6b  movsxd  rax, dword ptr [rbx-0Ch]
0x18026af6f  add     rax, rax
0x18026af72  cmp     rax, r15
0x18026af75  jb      short loc_18026AFB2
0x18026af77  mov     lpSource, r15; Size
0x18026af7a  mov     rcx, rbx; void *
0x18026af7d  call    cs:__imp_memmove
0x18026af83  jmp     short loc_18026AFC4
0x18026af85  movsxd  lpSource, dword ptr [rbx-0Ch]
0x18026af89  add     lpSource, lpSource; Size
0x18026af8c  xor     r12d, r12d
0x18026af8f  test    r15, r15
0x18026af92  jz      short loc_18026AFC4
0x18026af94  mov     rcx, rbx; void *
0x18026af97  cmp     lpSource, r15
0x18026af9a  jb      short loc_18026AFAA
0x18026af9c  mov     lpSource, r15; Size
0x18026af9f  mov     lpDest, r13; Src
0x18026afa2  call    cs:__imp_memcpy
0x18026afa8  jmp     short loc_18026AFC4
0x18026afaa  xor     edx, edx; Val
0x18026afac  call    cs:__imp_memset
0x18026afb2  call    cs:__imp__errno
0x18026afb8  mov     dword ptr [rax], 22h ; '"'
0x18026afbe  call    cs:__imp__invalid_parameter_noinfo
0x18026afc4  cmp     r14d, [rbx-0Ch]
0x18026afc8  jg      loc_18026B09E
0x18026afce  mov     [rbx-10h], r14d
0x18026afd2  mov     [r15+rbx], r12w
0x18026afd7  jmp     short loc_18026AFE6
0x18026afd9  lea     rcx, [rbp+57h+strDest]; this
0x18026afdd  call    ?Empty@?$CSimpleStringT@_W$00@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,1>::Empty(void)
0x18026afe2  mov     rbx, [rbp+57h+strDest.m_pszData]
0x18026afe6  mov     rax, [rdi+8]
0x18026afea  neg     rax
0x18026afed  sbb     lpDest, lpDest
0x18026aff0  and     lpDest, rbx; lpNewFileName
0x18026aff3  mov     rax, [rsi+8]
0x18026aff7  neg     rax
0x18026affa  sbb     rcx, rcx
0x18026affd  and     rcx, [rbp+57h+strSource.m_pszData]; lpExistingFileName
0x18026b001  xor     r8d, r8d; bFailIfExists
0x18026b004  call    cs:__imp_CopyFileW
0x18026b00a  mov     edi, eax
0x18026b00c  lea     lpDest, [rbx-18h]
0x18026b010  or      ebx, 0FFFFFFFFh
0x18026b013  mov     ecx, ebx
0x18026b015  lock xadd [lpDest+10h], ecx
0x18026b01a  add     ecx, ebx
0x18026b01c  test    ecx, ecx
0x18026b01e  jg      short loc_18026B031
  ... truncated ...
```
