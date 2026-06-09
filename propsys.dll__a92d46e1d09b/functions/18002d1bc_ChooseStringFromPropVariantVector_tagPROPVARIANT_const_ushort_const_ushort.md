# ChooseStringFromPropVariantVector(tagPROPVARIANT const &,ushort const *,ushort * *)

- ea: `0x18002d1bc`
- end: `0x18002d365`
- name: `?ChooseStringFromPropVariantVector@@YAJAEBUtagPROPVARIANT@@PEBGPEAPEAG@Z`
- size: `425`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002d810`

## callees

- `0x18002d070`
- `0x18002d1bc`
- `0x18002d370`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002d32c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002d32c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCSpnW` at `0x18002d2dc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCSpnW` at `0x18002d2dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d284`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d295`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d284`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d295`

## string_xrefs

- `0x18002d216`: `music;picture;document;movie;recordedtv;video;email;contact;calendar;task;folder`

## pseudocode

```c
__int64 __fastcall ChooseStringFromPropVariantVector(
        const PROPVARIANT *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  HRESULT v4; // ebx
  __int64 v5; // rcx
  const wchar_t *v6; // r8
  __int64 v7; // rdx
  WCHAR *v8; // rax
  PWSTR *v9; // rsi
  WCHAR *v10; // rcx
  unsigned __int64 v11; // rbp
  unsigned __int64 i; // rdi
  int v14; // ebp
  WCHAR *v15; // r14
  ULONG v16; // edi
  WCHAR *v17; // r12
  int v18; // ecx
  bool v19; // zf
  int v20; // ecx
  __int64 v21; // rdx
  __int64 v22; // rcx
  ULONG pcElem; // [rsp+20h] [rbp-268h] BYREF
  PWSTR *pprgsz; // [rsp+28h] [rbp-260h] BYREF
  WCHAR pszStr[264]; // [rsp+30h] [rbp-258h] BYREF

  *a3 = 0;
  pcElem = 0;
  pprgsz = 0;
  v4 = PropVariantToStringVectorAlloc(a1, &pprgsz, &pcElem);
  if ( v4 < 0 )
  {
    if ( v4 == -2147024809 )
      return (unsigned int)-2147319765;
  }
  else
  {
    v5 = 2147483646;
    v6 = L"music;picture;document;movie;recordedtv;video;email;contact;calendar;task;folder";
    v7 = 260;
    v8 = pszStr;
    do
    {
      if ( !v5 )
        break;
      if ( !*v6 )
        break;
      *v8++ = *v6++;
      --v5;
      --v7;
    }
    while ( v7 );
    v9 = pprgsz;
    v10 = v8 - 1;
    if ( v7 )
      v10 = v8;
    *v10 = 0;
    v4 = v7 == 0 ? 0x8007007A : 0;
    if ( v7 )
    {
      v14 = 1;
      v15 = pszStr;
      while ( 2 )
      {
        v16 = 0;
        v17 = &v15[StrCSpnW(v15, L";")];
        v18 = 0;
        v19 = *v17 == 0;
        *v17 = 0;
        if ( !v19 )
          v18 = v14;
        v14 = v18;
        while ( v16 < pcElem )
        {
          if ( !StrCmpICW(v9[v16], v15) )
          {
            v4 = _AllocString<CTCoAllocPolicy>(v22, v21, v9[v16], a3);
            v20 = 1;
            goto LABEL_19;
          }
          ++v16;
        }
        v15 = v17 + 1;
        v20 = 0;
        if ( v14 )
          continue;
        break;
      }
LABEL_19:
      if ( !v20 )
        v4 = -2147319765;
    }
    v11 = pcElem;
    for ( i = 0; i < v11; CoTaskMemFree(v9[i++]) )
      ;
    CoTaskMemFree(v9);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002d1bc  mov     [rsp+arg_8], rbx
0x18002d1c1  push    rbp
0x18002d1c2  push    rsi
0x18002d1c3  push    rdi
0x18002d1c4  push    r12
0x18002d1c6  push    r13
0x18002d1c8  push    r14
0x18002d1ca  push    r15
0x18002d1cc  sub     rsp, 250h
0x18002d1d3  mov     rax, cs:__security_cookie
0x18002d1da  xor     rax, rsp
0x18002d1dd  mov     [rsp+288h+var_48], rax
0x18002d1e5  xor     r15d, r15d
0x18002d1e8  lea     rdx, [rsp+288h+pprgsz]; pprgsz
0x18002d1ed  mov     [r8], r15
0x18002d1f0  mov     r13, r8
0x18002d1f3  lea     r8, [rsp+288h+pcElem]; pcElem
0x18002d1f8  mov     [rsp+288h+pcElem], r15d
0x18002d1fd  mov     [rsp+288h+pprgsz], r15
0x18002d202  call    PropVariantToStringVectorAlloc
0x18002d207  mov     ebx, eax
0x18002d209  test    eax, eax
0x18002d20b  js      loc_18002D352
0x18002d211  mov     ecx, 7FFFFFFEh
0x18002d216  lea     r8, aMusicPictureDo; "music;picture;document;movie;recordedtv"...
0x18002d21d  mov     edx, 104h
0x18002d222  lea     rax, [rsp+288h+pszStr]
0x18002d227  test    rcx, rcx
0x18002d22a  jz      short loc_18002D24B
0x18002d22c  movzx   r9d, word ptr [r8]
0x18002d230  test    r9w, r9w
0x18002d234  jz      short loc_18002D24B
0x18002d236  mov     [rax], r9w
0x18002d23a  add     r8, 2
0x18002d23e  add     rax, 2
0x18002d242  dec     rcx
0x18002d245  sub     rdx, 1
0x18002d249  jnz     short loc_18002D227
0x18002d24b  mov     rsi, [rsp+288h+pprgsz]
0x18002d250  lea     rcx, [rax-2]
0x18002d254  test    rdx, rdx
0x18002d257  cmovnz  rcx, rax
0x18002d25b  mov     rax, rdx
0x18002d25e  neg     rax
0x18002d261  sbb     ebx, ebx
0x18002d263  not     ebx
0x18002d265  mov     [rcx], r15w
0x18002d269  and     ebx, 8007007Ah
0x18002d26f  test    rdx, rdx
0x18002d272  jnz     short loc_18002D2C8
0x18002d274  mov     ebp, [rsp+288h+pcElem]
0x18002d278  mov     rdi, r15
0x18002d27b  test    rbp, rbp
0x18002d27e  jz      short loc_18002D292
0x18002d280  mov     rcx, [rsi+rdi*8]; pv
0x18002d284  call    cs:__imp_CoTaskMemFree
0x18002d28a  inc     rdi
0x18002d28d  cmp     rdi, rbp
0x18002d290  jb      short loc_18002D280
0x18002d292  mov     rcx, rsi; pv
0x18002d295  call    cs:__imp_CoTaskMemFree
0x18002d29b  mov     eax, ebx
0x18002d29d  mov     rcx, [rsp+288h+var_48]
0x18002d2a5  xor     rcx, rsp; StackCookie
0x18002d2a8  call    __security_check_cookie
0x18002d2ad  mov     rbx, [rsp+288h+arg_8]
0x18002d2b5  add     rsp, 250h
0x18002d2bc  pop     r15
0x18002d2be  pop     r14
0x18002d2c0  pop     r13
0x18002d2c2  pop     r12
0x18002d2c4  pop     rdi
0x18002d2c5  pop     rsi
0x18002d2c6  pop     rbp
0x18002d2c7  retn
0x18002d2c8  mov     ebp, 1
0x18002d2cd  lea     r14, [rsp+288h+pszStr]
0x18002d2d2  lea     rdx, pszSet; ";"
0x18002d2d9  mov     rcx, r14; pszStr
0x18002d2dc  call    cs:__imp_StrCSpnW
0x18002d2e2  movsxd  rcx, eax
0x18002d2e5  mov     edi, r15d
0x18002d2e8  lea     r12, [r14+rcx*2]
0x18002d2ec  mov     ecx, r15d
0x18002d2ef  cmp     r15w, [r12]
0x18002d2f4  mov     [r12], r15w
0x18002d2f9  cmovnz  ecx, ebp
0x18002d2fc  mov     ebp, ecx
0x18002d2fe  cmp     edi, [rsp+288h+pcElem]
0x18002d302  jb      short loc_18002D322
0x18002d304  xor     r15d, r15d
0x18002d307  lea     r14, [r12+2]
0x18002d30c  mov     ecx, r15d
0x18002d30f  test    ebp, ebp
0x18002d311  jnz     short loc_18002D2D2
0x18002d313  test    ecx, ecx
0x18002d315  mov     eax, 8002802Bh
0x18002d31a  cmovz   ebx, eax
0x18002d31d  jmp     loc_18002D274
0x18002d322  mov     r15d, edi
0x18002d325  mov     rdx, r14; pszStr2
0x18002d328  mov     rcx, [rsi+r15*8]; pszStr1
0x18002d32c  call    cs:__imp_StrCmpICW
0x18002d332  test    eax, eax
0x18002d334  jz      short loc_18002D33A
0x18002d336  inc     edi
0x18002d338  jmp     short loc_18002D2FE
0x18002d33a  mov     r8, [rsi+r15*8]
0x18002d33e  mov     r9, r13
0x18002d341  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18002d346  mov     ebx, eax
0x18002d348  mov     ecx, 1
0x18002d34d  xor     r15d, r15d
0x18002d350  jmp     short loc_18002D313
0x18002d352  cmp     ebx, 80070057h
0x18002d358  mov     eax, 8002802Bh
0x18002d35d  cmovz   ebx, eax
0x18002d360  jmp     loc_18002D29B
```
