# CreateProfileDescription

- ea: `0x18004ee44`
- end: `0x18004f3e7`
- name: `CreateProfileDescription`
- size: `1443`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *, CHAR **, WCHAR *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18004fc60`

## callees

- `0x1800230bc`
- `0x18002e5f0`
- `0x18002ea84`
- `0x18004ee44`
- `0x18004f3f0`
- `0x180057d94`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004ef23`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004f189`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004ef23`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004f189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ef2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f0bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f2ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ef2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f0bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f2ac`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004f0fa`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004f148`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004f0fa`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004f148`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004f0b2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004f2a2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004f0b2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004f2a2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f10c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f10c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f2f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f308`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f31d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f2f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f308`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f31d`

## pseudocode

```c
__int64 __fastcall CreateProfileDescription(__int64 a1, __int64 a2, unsigned int *a3, CHAR **a4, WCHAR *a5, _QWORD *a6)
{
  void *v9; // r13
  void *v10; // r12
  void *v11; // rdi
  signed int PreferredPropertiesLanguages; // ebx
  signed int LastError; // eax
  HLOCAL *v14; // r15
  LPWSTR v15; // rsi
  int LocalizedPropertyValue; // eax
  const OLECHAR *v17; // rsi
  const OLECHAR *v18; // rcx
  const OLECHAR *v19; // rax
  const OLECHAR *v20; // rax
  signed int v21; // eax
  int v22; // eax
  int v23; // ebx
  CHAR *v24; // rax
  signed int v25; // eax
  int v26; // eax
  void *v27; // r14
  const OLECHAR *v28; // rcx
  const OLECHAR *v29; // rax
  signed int v30; // eax
  DWORD nSize; // [rsp+28h] [rbp-D8h]
  DWORD nSizea; // [rsp+28h] [rbp-D8h]
  DWORD nSizeb; // [rsp+28h] [rbp-D8h]
  DWORD nSizec; // [rsp+28h] [rbp-D8h]
  DWORD nSized; // [rsp+28h] [rbp-D8h]
  void *v37; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR v38; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v39; // [rsp+50h] [rbp-B0h] BYREF
  CHAR **v40; // [rsp+58h] [rbp-A8h]
  __int64 v41; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h] BYREF
  void *v44; // [rsp+78h] [rbp-88h] BYREF
  void *v45; // [rsp+80h] [rbp-80h] BYREF
  void *v46; // [rsp+88h] [rbp-78h] BYREF
  WCHAR lpBuffer[4]; // [rsp+90h] [rbp-70h] BYREF
  void *Block; // [rsp+98h] [rbp-68h] BYREF
  void *v49; // [rsp+A0h] [rbp-60h] BYREF
  void *v50; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD *v51; // [rsp+B0h] [rbp-50h]
  va_list Arguments[3]; // [rsp+B8h] [rbp-48h] BYREF
  va_list v53[4]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Buffer[512]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Source[512]; // [rsp+4F0h] [rbp+3F0h] BYREF

  *a4 = 0;
  v40 = a4;
  v38 = a5;
  v9 = 0;
  v51 = a6;
  v10 = 0;
  *(_QWORD *)a5 = 0;
  v11 = 0;
  *a6 = 0;
  *(_QWORD *)lpBuffer = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  Block = 0;
  v45 = 0;
  v49 = 0;
  v50 = 0;
  v44 = 0;
  v37 = 0;
  v46 = 0;
  LODWORD(v39) = 0;
  if ( !a1 || !a2 || !a3 )
  {
    PreferredPropertiesLanguages = -2147024809;
    v14 = (HLOCAL *)a4;
    v15 = a5;
    goto LABEL_50;
  }
  PreferredPropertiesLanguages = ProfileProperties::GetPreferredPropertiesLanguages((ProfileProperties *)&v46, &v39, a3);
  if ( PreferredPropertiesLanguages < 0 )
    goto LABEL_8;
  if ( !LoadStringW(ghInstMscms, 0x97u, Buffer, 512) )
  {
    LastError = GetLastError();
    PreferredPropertiesLanguages = LastError;
    if ( LastError > 0 )
      PreferredPropertiesLanguages = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_8;
  }
  PreferredPropertiesLanguages = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 360LL))(a1, &v41);
  if ( PreferredPropertiesLanguages < 0 )
  {
LABEL_8:
    v11 = v46;
    goto LABEL_9;
  }
  v11 = v46;
  PreferredPropertiesLanguages = ProfileProperties::GetLocalizedPropertyValue(v41, 1, 0, v46, (_DWORD)v39, 1, &Block);
  if ( PreferredPropertiesLanguages < 0 )
    goto LABEL_9;
  PreferredPropertiesLanguages = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 360LL))(a2, &v42);
  if ( PreferredPropertiesLanguages < 0 )
    goto LABEL_9;
  LOBYTE(nSize) = 1;
  PreferredPropertiesLanguages = ProfileProperties::GetLocalizedPropertyValue(v42, 2, 0, v11, (_DWORD)v39, nSize, &v45);
  if ( PreferredPropertiesLanguages < 0
    || (PreferredPropertiesLanguages = (*(__int64 (__fastcall **)(unsigned int *, __int64 *))(*(_QWORD *)a3 + 360LL))(
                                         a3,
                                         &v43),
        PreferredPropertiesLanguages < 0) )
  {
    v9 = v45;
    goto LABEL_9;
  }
  LOBYTE(nSizea) = 1;
  LocalizedPropertyValue = ProfileProperties::GetLocalizedPropertyValue(v43, 3, 0, v11, (_DWORD)v39, nSizea, &v49);
  v9 = v45;
  PreferredPropertiesLanguages = LocalizedPropertyValue;
  if ( LocalizedPropertyValue < 0 )
  {
LABEL_9:
    v14 = (HLOCAL *)v40;
    goto LABEL_10;
  }
  v17 = &word_1800884E0;
  v18 = &word_1800884E0;
  if ( Block )
    v18 = (const OLECHAR *)Block;
  Arguments[0] = (va_list)v18;
  v19 = &word_1800884E0;
  if ( v45 )
    v19 = (const OLECHAR *)v45;
  Arguments[1] = (va_list)v19;
  v20 = &word_1800884E0;
  if ( v49 )
    v20 = (const OLECHAR *)v49;
  Arguments[2] = (va_list)v20;
  if ( !FormatMessageW(0x2500u, Buffer, 0, 0, lpBuffer, 0, Arguments)
    || (v22 = WideCharToMultiByte(0, 0, *(LPCWCH *)lpBuffer, -1, 0, 0, 0, 0), (v23 = v22) == 0) )
  {
    v21 = GetLastError();
    PreferredPropertiesLanguages = v21;
    if ( v21 > 0 )
      PreferredPropertiesLanguages = (unsigned __int16)v21 | 0x80070000;
    goto LABEL_9;
  }
  v24 = (CHAR *)LocalAlloc(0, v22);
  v14 = (HLOCAL *)v40;
  *v40 = v24;
  if ( !v24 )
  {
    PreferredPropertiesLanguages = -2147024882;
    goto LABEL_10;
  }
  if ( !WideCharToMultiByte(0, 0, *(LPCWCH *)lpBuffer, -1, v24, v23, 0, 0)
    || !LoadStringW(ghInstMscms, 0x96u, Source, 512) )
  {
    v25 = GetLastError();
    PreferredPropertiesLanguages = v25;
    if ( v25 > 0 )
      PreferredPropertiesLanguages = (unsigned __int16)v25 | 0x80070000;
    goto LABEL_10;
  }
  PreferredPropertiesLanguages = DetermineResourceLanguage(v51);
  if ( PreferredPropertiesLanguages < 0
    || (LOBYTE(nSizeb) = 0,
        PreferredPropertiesLanguages = ProfileProperties::GetLocalizedPropertyValue(
                                         v41,
                                         1,
                                         0,
                                         v11,
                                         (_DWORD)v39,
                                         nSizeb,
                                         &v50),
        PreferredPropertiesLanguages < 0) )
  {
LABEL_10:
    v15 = v38;
LABEL_50:
    v27 = v37;
    goto LABEL_51;
  }
  LOBYTE(nSizec) = 0;
  PreferredPropertiesLanguages = ProfileProperties::GetLocalizedPropertyValue(v42, 2, 0, v11, (_DWORD)v39, nSizec, &v44);
  if ( PreferredPropertiesLanguages < 0 )
  {
    v10 = v44;
    goto LABEL_10;
  }
  LOBYTE(nSized) = 0;
  v26 = ProfileProperties::GetLocalizedPropertyValue(v43, 3, 0, v11, (_DWORD)v39, nSized, &v37);
  v10 = v44;
  PreferredPropertiesLanguages = v26;
  v27 = v37;
  if ( v26 < 0 )
  {
    v15 = v38;
  }
  else
  {
    v28 = &word_1800884E0;
    if ( v50 )
      v28 = (const OLECHAR *)v50;
    v29 = &word_1800884E0;
    v53[0] = (va_list)v28;
    if ( v44 )
      v29 = (const OLECHAR *)v44;
    v53[1] = (va_list)v29;
    if ( v37 )
      v17 = (const OLECHAR *)v37;
    v53[2] = (va_list)v17;
    v15 = v38;
    if ( !FormatMessageW(0x2500u, Source, 0, 0, v38, 0, v53) )
    {
      v30 = GetLastError();
      PreferredPropertiesLanguages = v30;
      if ( v30 > 0 )
        PreferredPropertiesLanguages = (unsigned __int16)v30 | 0x80070000;
    }
  }
LABEL_51:
  if ( *(_QWORD *)lpBuffer )
    LocalFree(*(HLOCAL *)lpBuffer);
  if ( PreferredPropertiesLanguages < 0 )
  {
    if ( *v14 )
    {
      LocalFree(*v14);
      *v14 = 0;
    }
    if ( *(_QWORD *)v15 )
    {
      LocalFree(*(HLOCAL *)v15);
      *(_QWORD *)v15 = 0;
    }
  }
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
  }
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    v42 = 0;
  }
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  operator delete(Block);
  operator delete(v9);
  operator delete(v49);
  operator delete(v50);
  operator delete(v10);
  operator delete(v27);
  operator delete(v11);
  return (unsigned int)PreferredPropertiesLanguages;
}

```

## disassembly

```asm
0x18004ee44  push    rbp
0x18004ee46  push    rbx
0x18004ee47  push    rsi
0x18004ee48  push    rdi
0x18004ee49  push    r12
0x18004ee4b  push    r13
0x18004ee4d  push    r14
0x18004ee4f  push    r15
0x18004ee51  lea     rbp, [rsp-808h]
0x18004ee59  sub     rsp, 908h
0x18004ee60  mov     rax, cs:__security_cookie
0x18004ee67  xor     rax, rsp
0x18004ee6a  mov     [rbp+840h+var_50], rax
0x18004ee71  mov     rax, [rbp+840h+arg_28]
0x18004ee78  xor     ebx, ebx
0x18004ee7a  mov     r14, rcx
0x18004ee7d  mov     [r9], rbx
0x18004ee80  mov     rcx, [rbp+840h+arg_20]
0x18004ee87  mov     r15, r8
0x18004ee8a  mov     [rsp+940h+var_8E8], r9
0x18004ee8f  mov     rsi, rdx
0x18004ee92  mov     [rsp+940h+var_8F8], rcx
0x18004ee97  mov     r13d, ebx
0x18004ee9a  mov     [rbp+840h+var_890], rax
0x18004ee9e  mov     r12d, ebx
0x18004eea1  mov     [rcx], rbx
0x18004eea4  mov     edi, ebx
0x18004eea6  mov     [rax], rbx
0x18004eea9  mov     qword ptr [rbp+840h+var_8B0], rbx
0x18004eead  mov     [rsp+940h+var_8E0], rbx
0x18004eeb2  mov     [rsp+940h+var_8D8], rbx
0x18004eeb7  mov     [rsp+940h+var_8D0], rbx
0x18004eebc  mov     [rbp+840h+Block], rbx
0x18004eec0  mov     [rbp+840h+var_8C0], rbx
0x18004eec4  mov     [rbp+840h+var_8A0], rbx
0x18004eec8  mov     [rbp+840h+var_898], rbx
0x18004eecc  mov     [rsp+940h+var_8C8], rbx
0x18004eed1  mov     [rsp+940h+var_900], rbx
0x18004eed6  mov     [rbp+840h+var_8B8], rbx
0x18004eeda  mov     dword ptr [rsp+940h+var_8F0], ebx
0x18004eede  test    r14, r14
0x18004eee1  jz      loc_18004F2DD
0x18004eee7  test    rdx, rdx
0x18004eeea  jz      loc_18004F2DD
0x18004eef0  test    r8, r8
0x18004eef3  jz      loc_18004F2DD
0x18004eef9  lea     rdx, [rsp+940h+var_8F0]; unsigned __int16 **
0x18004eefe  lea     rcx, [rbp+840h+var_8B8]; this
0x18004ef02  call    ?GetPreferredPropertiesLanguages@ProfileProperties@@YAJPEAPEAGPEAK@Z; ProfileProperties::GetPreferredPropertiesLanguages(ushort * *,ulong *)
0x18004ef07  mov     ebx, eax
0x18004ef09  test    eax, eax
0x18004ef0b  js      short loc_18004EF42
0x18004ef0d  mov     rcx, cs:ghInstMscms; hInstance
0x18004ef14  lea     r8, [rbp+840h+Buffer]; lpBuffer
0x18004ef18  mov     r9d, 200h; cchBufferMax
0x18004ef1e  mov     edx, 97h; uID
0x18004ef23  call    cs:__imp_LoadStringW
0x18004ef29  test    eax, eax
0x18004ef2b  jnz     short loc_18004EF55
0x18004ef2d  call    cs:__imp_GetLastError
0x18004ef33  mov     ebx, eax
0x18004ef35  test    eax, eax
0x18004ef37  jle     short loc_18004EF42
0x18004ef39  movzx   ebx, ax
0x18004ef3c  or      ebx, 80070000h
0x18004ef42  mov     rdi, [rbp+840h+var_8B8]
0x18004ef46  mov     r15, [rsp+940h+var_8E8]
0x18004ef4b  mov     rsi, [rsp+940h+var_8F8]
0x18004ef50  jmp     loc_18004F2E8
0x18004ef55  mov     rax, [r14]
0x18004ef58  lea     rdx, [rsp+940h+var_8E0]
0x18004ef5d  mov     rcx, r14
0x18004ef60  mov     rax, [rax+168h]
0x18004ef67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef6c  xor     r14d, r14d
0x18004ef6f  mov     ebx, eax
0x18004ef71  test    eax, eax
0x18004ef73  js      short loc_18004EF42
0x18004ef75  mov     rdi, [rbp+840h+var_8B8]
0x18004ef79  lea     rax, [rbp+840h+Block]
0x18004ef7d  mov     rcx, [rsp+940h+var_8E0]
0x18004ef82  lea     edx, [r14+1]
0x18004ef86  mov     [rsp+940h+Arguments], rax
0x18004ef8b  mov     r9, rdi
0x18004ef8e  mov     eax, dword ptr [rsp+940h+var_8F0]
0x18004ef92  xor     r8d, r8d
0x18004ef95  mov     byte ptr [rsp+940h+nSize], 1
0x18004ef9a  mov     dword ptr [rsp+940h+lpBuffer], eax
0x18004ef9e  call    ?GetLocalizedPropertyValue@ProfileProperties@@YAJPEAUIXMLDOMElement@@W4COLORPROFILETYPE@@W4Enum@WcsProperty@@PEBGK_NPEAPEAG@Z; ProfileProperties::GetLocalizedPropertyValue(IXMLDOMElement *,COLORPROFILETYPE,WcsProperty::Enum,ushort const *,ulong,bool,ushort * *)
0x18004efa3  mov     ebx, eax
0x18004efa5  test    eax, eax
0x18004efa7  js      short loc_18004EF46
0x18004efa9  mov     rax, [rsi]
0x18004efac  lea     rdx, [rsp+940h+var_8D8]
0x18004efb1  mov     rcx, rsi
0x18004efb4  mov     rax, [rax+168h]
0x18004efbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004efc0  mov     ebx, eax
0x18004efc2  test    eax, eax
0x18004efc4  js      short loc_18004EF46
0x18004efc6  mov     rcx, [rsp+940h+var_8D8]
0x18004efcb  lea     rax, [rbp+840h+var_8C0]
0x18004efcf  mov     [rsp+940h+Arguments], rax
0x18004efd4  lea     edx, [r14+2]
0x18004efd8  mov     eax, dword ptr [rsp+940h+var_8F0]
0x18004efdc  mov     r9, rdi
0x18004efdf  mov     byte ptr [rsp+940h+nSize], 1
0x18004efe4  xor     r8d, r8d
0x18004efe7  mov     dword ptr [rsp+940h+lpBuffer], eax
0x18004efeb  call    ?GetLocalizedPropertyValue@ProfileProperties@@YAJPEAUIXMLDOMElement@@W4COLORPROFILETYPE@@W4Enum@WcsProperty@@PEBGK_NPEAPEAG@Z; ProfileProperties::GetLocalizedPropertyValue(IXMLDOMElement *,COLORPROFILETYPE,WcsProperty::Enum,ushort const *,ulong,bool,ushort * *)
0x18004eff0  mov     ebx, eax
0x18004eff2  test    eax, eax
0x18004eff4  js      loc_18004F2D4
0x18004effa  mov     rax, [r15]
0x18004effd  lea     rdx, [rsp+940h+var_8D0]
0x18004f002  mov     rcx, r15
0x18004f005  mov     rax, [rax+168h]
0x18004f00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f011  mov     ebx, eax
0x18004f013  test    eax, eax
0x18004f015  js      loc_18004F2D4
0x18004f01b  mov     rcx, [rsp+940h+var_8D0]
0x18004f020  lea     rax, [rbp+840h+var_8A0]
0x18004f024  mov     [rsp+940h+Arguments], rax
0x18004f029  lea     edx, [r14+3]
0x18004f02d  mov     eax, dword ptr [rsp+940h+var_8F0]
0x18004f031  mov     r9, rdi
0x18004f034  mov     byte ptr [rsp+940h+nSize], 1
0x18004f039  xor     r8d, r8d
0x18004f03c  mov     dword ptr [rsp+940h+lpBuffer], eax
0x18004f040  call    ?GetLocalizedPropertyValue@ProfileProperties@@YAJPEAUIXMLDOMElement@@W4COLORPROFILETYPE@@W4Enum@WcsProperty@@PEBGK_NPEAPEAG@Z; ProfileProperties::GetLocalizedPropertyValue(IXMLDOMElement *,COLORPROFILETYPE,WcsProperty::Enum,ushort const *,ulong,bool,ushort * *)
0x18004f045  mov     r13, [rbp+840h+var_8C0]
0x18004f049  mov     ebx, eax
0x18004f04b  test    eax, eax
0x18004f04d  js      loc_18004EF46
0x18004f053  mov     rax, [rbp+840h+Block]
0x18004f057  lea     rsi, word_1800884E0
0x18004f05e  test    rax, rax
0x18004f061  lea     rdx, [rbp+840h+Buffer]; lpSource
0x18004f065  mov     rcx, rsi
0x18004f068  cmovnz  rcx, rax
0x18004f06c  test    r13, r13
0x18004f06f  mov     [rbp+840h+var_888], rcx
0x18004f073  mov     rax, rsi
0x18004f076  mov     rcx, [rbp+840h+var_8A0]
0x18004f07a  cmovnz  rax, r13
0x18004f07e  mov     [rbp+840h+var_880], rax
0x18004f082  test    rcx, rcx
0x18004f085  mov     rax, rsi
0x18004f088  cmovnz  rax, rcx
0x18004f08c  xor     r9d, r9d; dwLanguageId
0x18004f08f  mov     [rbp+840h+var_878], rax
0x18004f093  xor     r8d, r8d; dwMessageId
0x18004f096  lea     rax, [rbp+840h+var_888]
0x18004f09a  mov     ecx, 2500h; dwFlags
0x18004f09f  mov     [rsp+940h+Arguments], rax; Arguments
0x18004f0a4  lea     rax, [rbp+840h+var_8B0]
0x18004f0a8  mov     [rsp+940h+nSize], r14d; nSize
0x18004f0ad  mov     [rsp+940h+lpBuffer], rax; lpBuffer
0x18004f0b2  call    cs:__imp_FormatMessageW
0x18004f0b8  test    eax, eax
0x18004f0ba  jnz     short loc_18004F0DA
0x18004f0bc  call    cs:__imp_GetLastError
0x18004f0c2  mov     ebx, eax
0x18004f0c4  test    eax, eax
0x18004f0c6  jle     loc_18004EF46
0x18004f0cc  movzx   ebx, ax
0x18004f0cf  or      ebx, 80070000h
0x18004f0d5  jmp     loc_18004EF46
0x18004f0da  mov     r8, qword ptr [rbp+840h+var_8B0]; lpWideCharStr
0x18004f0de  or      r9d, 0FFFFFFFFh; cchWideChar
0x18004f0e2  mov     [rsp+940h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18004f0e7  xor     edx, edx; dwFlags
0x18004f0e9  mov     [rsp+940h+Arguments], r14; lpDefaultChar
0x18004f0ee  xor     ecx, ecx; CodePage
0x18004f0f0  mov     [rsp+940h+nSize], r14d; cbMultiByte
0x18004f0f5  mov     [rsp+940h+lpBuffer], r14; lpMultiByteStr
0x18004f0fa  call    cs:__imp_WideCharToMultiByte
0x18004f100  movsxd  rbx, eax
0x18004f103  test    eax, eax
0x18004f105  jz      short loc_18004F0BC
0x18004f107  mov     rdx, rbx; uBytes
0x18004f10a  xor     ecx, ecx; uFlags
0x18004f10c  call    cs:__imp_LocalAlloc
0x18004f112  mov     r15, [rsp+940h+var_8E8]
0x18004f117  mov     [r15], rax
0x18004f11a  test    rax, rax
0x18004f11d  jnz     short loc_18004F129
0x18004f11f  mov     ebx, 8007000Eh
0x18004f124  jmp     loc_18004EF4B
0x18004f129  mov     r8, qword ptr [rbp+840h+var_8B0]; lpWideCharStr
0x18004f12d  or      r9d, 0FFFFFFFFh; cchWideChar
0x18004f131  mov     [rsp+940h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18004f136  xor     edx, edx; dwFlags
0x18004f138  mov     [rsp+940h+Arguments], r14; lpDefaultChar
0x18004f13d  xor     ecx, ecx; CodePage
0x18004f13f  mov     [rsp+940h+nSize], ebx; cbMultiByte
0x18004f143  mov     [rsp+940h+lpBuffer], rax; lpMultiByteStr
0x18004f148  call    cs:__imp_WideCharToMultiByte
0x18004f14e  test    eax, eax
0x18004f150  jnz     short loc_18004F170
0x18004f152  call    cs:__imp_GetLastError
0x18004f158  mov     ebx, eax
0x18004f15a  test    eax, eax
0x18004f15c  jle     loc_18004EF4B
0x18004f162  movzx   ebx, ax
0x18004f165  or      ebx, 80070000h
0x18004f16b  jmp     loc_18004EF4B
0x18004f170  mov     rcx, cs:ghInstMscms; hInstance
0x18004f177  lea     r8, [rbp+840h+Source]; lpBuffer
0x18004f17e  mov     r9d, 200h; cchBufferMax
0x18004f184  mov     edx, 96h; uID
0x18004f189  call    cs:__imp_LoadStringW
0x18004f18f  test    eax, eax
0x18004f191  jz      short loc_18004F152
0x18004f193  mov     rcx, [rbp+840h+var_890]
0x18004f197  call    DetermineResourceLanguage
0x18004f19c  mov     ebx, eax
0x18004f19e  test    eax, eax
0x18004f1a0  js      loc_18004EF4B
0x18004f1a6  mov     rcx, [rsp+940h+var_8E0]
0x18004f1ab  lea     rax, [rbp+840h+var_898]
0x18004f1af  mov     [rsp+940h+Arguments], rax
0x18004f1b4  xor     r8d, r8d
0x18004f1b7  mov     eax, dword ptr [rsp+940h+var_8F0]
0x18004f1bb  mov     r9, rdi
0x18004f1be  mov     byte ptr [rsp+940h+nSize], r14b
0x18004f1c3  mov     dword ptr [rsp+940h+lpBuffer], eax
0x18004f1c7  lea     edx, [r8+1]
0x18004f1cb  call    ?GetLocalizedPropertyValue@ProfileProperties@@YAJPEAUIXMLDOMElement@@W4COLORPROFILETYPE@@W4Enum@WcsProperty@@PEBGK_NPEAPEAG@Z; ProfileProperties::GetLocalizedPropertyValue(IXMLDOMElement *,COLORPROFILETYPE,WcsProperty::Enum,ushort const *,ulong,bool,ushort * *)
0x18004f1d0  mov     ebx, eax
0x18004f1d2  test    eax, eax
0x18004f1d4  js      loc_18004EF4B
0x18004f1da  mov     rcx, [rsp+940h+var_8D8]
0x18004f1df  lea     rax, [rsp+940h+var_8C8]
0x18004f1e4  mov     [rsp+940h+Arguments], rax
0x18004f1e9  xor     r8d, r8d
0x18004f1ec  mov     eax, dword ptr [rsp+940h+var_8F0]
0x18004f1f0  mov     r9, rdi
0x18004f1f3  mov     byte ptr [rsp+940h+nSize], r14b
0x18004f1f8  mov     dword ptr [rsp+940h+lpBuffer], eax
0x18004f1fc  lea     edx, [r8+2]
0x18004f200  call    ?GetLocalizedPropertyValue@ProfileProperties@@YAJPEAUIXMLDOMElement@@W4COLORPROFILETYPE@@W4Enum@WcsProperty@@PEBGK_NPEAPEAG@Z; ProfileProperties::GetLocalizedPropertyValue(IXMLDOMElement *,COLORPROFILETYPE,WcsProperty::Enum,ushort const *,ulong,bool,ushort * *)
0x18004f205  mov     ebx, eax
0x18004f207  test    eax, eax
0x18004f209  js      loc_18004F2CA
0x18004f20f  mov     rcx, [rsp+940h+var_8D0]
0x18004f214  lea     rax, [rsp+940h+var_900]
0x18004f219  mov     [rsp+940h+Arguments], rax
0x18004f21e  xor     r8d, r8d
0x18004f221  mov     eax, dword ptr [rsp+940h+var_8F0]
0x18004f225  mov     r9, rdi
0x18004f228  mov     byte ptr [rsp+940h+nSize], r14b
0x18004f22d  mov     dword ptr [rsp+940h+lpBuffer], eax
0x18004f231  lea     edx, [r8+3]
0x18004f235  call    ?GetLocalizedPropertyValue@ProfileProperties@@YAJPEAUIXMLDOMElement@@W4COLORPROFILETYPE@@W4Enum@WcsProperty@@PEBGK_NPEAPEAG@Z; ProfileProperties::GetLocalizedPropertyValue(IXMLDOMElement *,COLORPROFILETYPE,WcsProperty::Enum,ushort const *,ulong,bool,ushort * *)
0x18004f23a  mov     r12, [rsp+940h+var_8C8]
0x18004f23f  mov     ebx, eax
0x18004f241  mov     r14, [rsp+940h+var_900]
0x18004f246  test    eax, eax
0x18004f248  js      short loc_18004F2C3
0x18004f24a  mov     rax, [rbp+840h+var_898]
0x18004f24e  lea     rdx, [rbp+840h+Source]; lpSource
0x18004f255  test    rax, rax
0x18004f258  mov     rcx, rsi
0x18004f25b  cmovnz  rcx, rax
0x18004f25f  mov     rax, rsi
0x18004f262  test    r12, r12
0x18004f265  mov     [rbp+840h+var_870], rcx
0x18004f269  mov     ecx, 2500h; dwFlags
0x18004f26e  cmovnz  rax, r12
0x18004f272  test    r14, r14
0x18004f275  mov     [rbp+840h+var_868], rax
0x18004f279  lea     rax, [rbp+840h+var_870]
0x18004f27d  cmovnz  rsi, r14
0x18004f281  mov     [rsp+940h+Arguments], rax; Arguments
0x18004f286  mov     [rbp+840h+var_860], rsi
0x18004f28a  xor     r9d, r9d; dwLanguageId
0x18004f28d  mov     rsi, [rsp+940h+var_8F8]
0x18004f292  xor     r8d, r8d; dwMessageId
0x18004f295  mov     [rsp+940h+nSize], 0; nSize
0x18004f29d  mov     [rsp+940h+lpBuffer], rsi; lpBuffer
0x18004f2a2  call    cs:__imp_FormatMessageW
0x18004f2a8  test    eax, eax
0x18004f2aa  jnz     short loc_18004F2ED
0x18004f2ac  call    cs:__imp_GetLastError
0x18004f2b2  mov     ebx, eax
0x18004f2b4  test    eax, eax
0x18004f2b6  jle     short loc_18004F2ED
0x18004f2b8  movzx   ebx, ax
0x18004f2bb  or      ebx, 80070000h
0x18004f2c1  jmp     short loc_18004F2ED
0x18004f2c3  mov     rsi, [rsp+940h+var_8F8]
0x18004f2c8  jmp     short loc_18004F2ED
0x18004f2ca  mov     r12, [rsp+940h+var_8C8]
0x18004f2cf  jmp     loc_18004EF4B
0x18004f2d4  mov     r13, [rbp+840h+var_8C0]
0x18004f2d8  jmp     loc_18004EF46
0x18004f2dd  mov     ebx, 80070057h
0x18004f2e2  mov     r15, r9
  ... truncated ...
```
