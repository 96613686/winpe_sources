# VerifyAppAllowed

- ea: `0x180076d08`
- end: `0x180076f51`
- name: `VerifyAppAllowed`
- size: `585`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021bd0`

## callees

- `0x18000e420`
- `0x180032110`
- `0x180076158`
- `0x180076354`
- `0x180076910`
- `0x1800769f4`
- `0x180076c3c`
- `0x180076d08`

## import_xrefs

- `RDPBASE!TRC_TraceBufferW` at `0x180076da6`
- `RDPBASE!TRC_TraceBufferW` at `0x180076e5a`
- `RDPBASE!TRC_TraceBufferW` at `0x180076da6`
- `RDPBASE!TRC_TraceBufferW` at `0x180076e5a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180076ee4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180076ee4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathQuoteSpacesW` at `0x180076f20`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathQuoteSpacesW` at `0x180076f20`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x180076ef3`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x180076ef3`

## string_xrefs

- `0x180076d7b`: `StringCchCopy CmdLine hr[0x%x]`
- `0x180076e2d`: `ExpandAppPath hr[0x%x]`

## pseudocode

```c
__int64 __fastcall VerifyAppAllowed(
        __int64 a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        LPCWSTR pszPath,
        unsigned __int64 a6,
        unsigned __int16 *a7,
        char a8,
        int *a9,
        int *a10)
{
  int *v10; // rsi
  int v11; // r15d
  int v13; // ebp
  unsigned __int16 *v14; // r14
  int v15; // eax
  unsigned int v16; // r11d
  int v17; // ebx
  WCHAR *v18; // rdi
  int v19; // eax
  int v20; // eax
  int *v22; // [rsp+38h] [rbp-40h]
  int v23; // [rsp+80h] [rbp+8h] BYREF
  int v24; // [rsp+84h] [rbp+Ch]
  unsigned __int16 *v25; // [rsp+88h] [rbp+10h]

  v25 = a2;
  v24 = HIDWORD(a1);
  v10 = a9;
  v11 = 0;
  v13 = a8 & 1;
  v23 = 0;
  *a9 = 0;
  if ( !a3 || v13 )
  {
    v14 = a7;
    StringCchCopyW(a7, (unsigned int)a6, &WindowName);
  }
  else
  {
    v14 = a7;
    v15 = StringCchCopyW(a7, (unsigned int)a6, a3);
    v17 = v15;
    if ( v15 < 0 )
    {
      TRC_TraceBufferW(
        3,
        4096,
        810,
        L"VerifyAppAllowed",
        L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
        0,
        L"StringCchCopy CmdLine hr[0x%x]",
        v15);
      goto LABEL_26;
    }
    v13 = 0;
  }
  v18 = (WCHAR *)pszPath;
  v19 = ExpandAppPath(&v23, v25, a4, (unsigned __int16 *)pszPath, v16, v14, a8 & 8, &v23, v10);
  v17 = v19;
  if ( v19 < 0 )
  {
    LODWORD(v22) = v19;
    TRC_TraceBufferW(
      3,
      4096,
      827,
      L"VerifyAppAllowed",
      L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
      0,
      L"ExpandAppPath hr[0x%x]",
      v22);
    v11 = v23;
    goto LABEL_26;
  }
  v11 = v23;
  if ( (a8 & 2) != 0 || (unsigned int)IsAllowListDisabled() )
  {
    *v10 = 1;
  }
  else if ( !v11 )
  {
    if ( v13 )
    {
      v20 = VerifyDocAllowed(v18, v10);
    }
    else
    {
      v17 = VerifyRealAppAllowedFromLRPC(v18, v14, 1, v10);
      if ( v17 >= 0 )
        goto LABEL_18;
      v20 = VerifyRealAppAllowedFromRegistry(v18, v14, 1, v10);
    }
    v17 = v20;
    if ( v20 < 0 )
      goto LABEL_26;
  }
LABEL_18:
  if ( (a8 & 4) == 0 )
    goto LABEL_24;
  if ( !PathIsUNCW(v18) && !UrlIsW(v18, URLIS_URL) )
    v17 = ExpandDriveRedirection(a4, v18);
  if ( v17 >= 0 )
  {
LABEL_24:
    if ( a4 >= 0x104 && *v18 != 34 )
      PathQuoteSpacesW(v18);
  }
LABEL_26:
  if ( a10 )
    *a10 = v11;
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180076d08  mov     rax, rsp
0x180076d0b  mov     [rax+18h], rbx
0x180076d0f  mov     [rax+20h], rbp
0x180076d13  mov     [rax+10h], rdx
0x180076d17  mov     [rax+8], rcx
0x180076d1b  push    rsi
0x180076d1c  push    rdi
0x180076d1d  push    r13
0x180076d1f  push    r14
0x180076d21  push    r15
0x180076d23  sub     rsp, 50h
0x180076d27  mov     rsi, [rsp+78h+arg_40]
0x180076d2f  xor     r15d, r15d
0x180076d32  mov     ebp, dword ptr [rsp+78h+arg_38]
0x180076d39  mov     r13d, r9d
0x180076d3c  and     ebp, 1
0x180076d3f  mov     [rax+8], r15d
0x180076d43  mov     [rsi], r15d
0x180076d46  test    r8, r8
0x180076d49  jz      short loc_180076DB5
0x180076d4b  test    ebp, ebp
0x180076d4d  jnz     short loc_180076DB5
0x180076d4f  mov     r11d, dword ptr [rsp+78h+arg_28]
0x180076d57  mov     r14, [rsp+78h+arg_30]
0x180076d5f  mov     edx, r11d; unsigned __int64
0x180076d62  mov     rcx, r14; unsigned __int16 *
0x180076d65  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180076d6a  mov     ebx, eax
0x180076d6c  test    eax, eax
0x180076d6e  jns     short loc_180076DB1
0x180076d70  mov     dword ptr [rsp+78h+var_40], eax
0x180076d74  lea     r9, aVerifyappallow; "VerifyAppAllowed"
0x180076d7b  lea     rax, aStringcchcopyC; "StringCchCopy CmdLine hr[0x%x]"
0x180076d82  mov     edx, 1000h
0x180076d87  mov     qword ptr [rsp+78h+var_48], rax
0x180076d8c  lea     ecx, [rbp+3]
0x180076d8f  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rap\\allow\\lib\\t"...
0x180076d96  mov     [rsp+78h+var_50], r15
0x180076d9b  mov     r8d, 32Ah
0x180076da1  mov     qword ptr [rsp+78h+var_58], rax
0x180076da6  call    cs:__imp_TRC_TraceBufferW
0x180076dac  jmp     loc_180076F26
0x180076db1  xor     ebp, ebp
0x180076db3  jmp     short loc_180076DD7
0x180076db5  mov     r11d, dword ptr [rsp+78h+arg_28]
0x180076dbd  lea     r8, WindowName; unsigned __int16 *
0x180076dc4  mov     r14, [rsp+78h+arg_30]
0x180076dcc  mov     edx, r11d; unsigned __int64
0x180076dcf  mov     rcx, r14; unsigned __int16 *
0x180076dd2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180076dd7  mov     eax, dword ptr [rsp+78h+arg_38]
0x180076dde  lea     rcx, [rsp+78h+arg_0]; void *
0x180076de6  mov     rdi, [rsp+78h+pszPath]
0x180076dee  and     eax, 8
0x180076df1  mov     rdx, [rsp+78h+arg_8]; unsigned __int16 *
0x180076df9  mov     r9, rdi; unsigned __int16 *
0x180076dfc  mov     [rsp+78h+var_38], rsi; int *
0x180076e01  mov     r8d, r13d; unsigned int
0x180076e04  mov     [rsp+78h+var_40], rcx; int *
0x180076e09  mov     [rsp+78h+var_48], eax; int
0x180076e0d  mov     [rsp+78h+var_50], r14; unsigned __int16 *
0x180076e12  mov     [rsp+78h+var_58], r11d; unsigned int
0x180076e17  call    ?ExpandAppPath@@YAJPEAXPEBGKPEAGK2HPEAH3@Z; ExpandAppPath(void *,ushort const *,ulong,ushort *,ulong,ushort *,int,int *,int *)
0x180076e1c  mov     ebx, eax
0x180076e1e  test    eax, eax
0x180076e20  jns     short loc_180076E6D
0x180076e22  mov     dword ptr [rsp+78h+var_40], eax
0x180076e26  lea     r9, aVerifyappallow; "VerifyAppAllowed"
0x180076e2d  lea     rax, aExpandapppathH; "ExpandAppPath hr[0x%x]"
0x180076e34  mov     edx, 1000h
0x180076e39  mov     qword ptr [rsp+78h+var_48], rax
0x180076e3e  mov     ecx, 3
0x180076e43  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rap\\allow\\lib\\t"...
0x180076e4a  mov     [rsp+78h+var_50], r15
0x180076e4f  mov     r8d, 33Bh
0x180076e55  mov     qword ptr [rsp+78h+var_58], rax
0x180076e5a  call    cs:__imp_TRC_TraceBufferW
0x180076e60  mov     r15d, [rsp+78h+arg_0]
0x180076e68  jmp     loc_180076F26
0x180076e6d  test    [rsp+78h+arg_38], 2
0x180076e75  mov     r15d, [rsp+78h+arg_0]
0x180076e7d  jnz     short loc_180076E88
0x180076e7f  call    ?IsAllowListDisabled@@YAHXZ; IsAllowListDisabled(void)
0x180076e84  test    eax, eax
0x180076e86  jz      short loc_180076E90
0x180076e88  mov     dword ptr [rsi], 1
0x180076e8e  jmp     short loc_180076ED7
0x180076e90  test    r15d, r15d
0x180076e93  jnz     short loc_180076ED7
0x180076e95  mov     rcx, rdi; unsigned __int16 *
0x180076e98  test    ebp, ebp
0x180076e9a  jz      short loc_180076EA6
0x180076e9c  mov     rdx, rsi; int *
0x180076e9f  call    ?VerifyDocAllowed@@YAJPEBGPEAH@Z; VerifyDocAllowed(ushort const *,int *)
0x180076ea4  jmp     short loc_180076ED1
0x180076ea6  mov     r9, rsi; int *
0x180076ea9  mov     r8d, 1; int
0x180076eaf  mov     rdx, r14; unsigned __int16 *
0x180076eb2  call    ?VerifyRealAppAllowedFromLRPC@@YAJPEBG0HPEAH@Z; VerifyRealAppAllowedFromLRPC(ushort const *,ushort const *,int,int *)
0x180076eb7  mov     ebx, eax
0x180076eb9  test    eax, eax
0x180076ebb  jns     short loc_180076ED7
0x180076ebd  mov     r9, rsi; int *
0x180076ec0  mov     r8d, 1; int
0x180076ec6  mov     rdx, r14; unsigned __int16 *
0x180076ec9  mov     rcx, rdi; lpString2
0x180076ecc  call    ?VerifyRealAppAllowedFromRegistry@@YAJPEBG0HPEAH@Z; VerifyRealAppAllowedFromRegistry(ushort const *,ushort const *,int,int *)
0x180076ed1  mov     ebx, eax
0x180076ed3  test    eax, eax
0x180076ed5  js      short loc_180076F26
0x180076ed7  test    [rsp+78h+arg_38], 4
0x180076edf  jz      short loc_180076F0E
0x180076ee1  mov     rcx, rdi; pszPath
0x180076ee4  call    cs:__imp_PathIsUNCW
0x180076eea  test    eax, eax
0x180076eec  jnz     short loc_180076F0A
0x180076eee  xor     edx, edx; UrlIs
0x180076ef0  mov     rcx, rdi; pszUrl
0x180076ef3  call    cs:__imp_UrlIsW
0x180076ef9  test    eax, eax
0x180076efb  jnz     short loc_180076F0A
0x180076efd  mov     rdx, rdi; unsigned __int16 *
0x180076f00  mov     ecx, r13d; unsigned int
0x180076f03  call    ?ExpandDriveRedirection@@YAJKPEAG@Z; ExpandDriveRedirection(ulong,ushort *)
0x180076f08  mov     ebx, eax
0x180076f0a  test    ebx, ebx
0x180076f0c  js      short loc_180076F26
0x180076f0e  cmp     r13d, 104h
0x180076f15  jb      short loc_180076F26
0x180076f17  cmp     word ptr [rdi], 22h ; '"'
0x180076f1b  jz      short loc_180076F26
0x180076f1d  mov     rcx, rdi; lpsz
0x180076f20  call    cs:__imp_PathQuoteSpacesW
0x180076f26  mov     rax, [rsp+78h+arg_48]
0x180076f2e  test    rax, rax
0x180076f31  jz      short loc_180076F36
0x180076f33  mov     [rax], r15d
0x180076f36  lea     r11, [rsp+78h+var_28]
0x180076f3b  mov     eax, ebx
0x180076f3d  mov     rbx, [r11+40h]
0x180076f41  mov     rbp, [r11+48h]
0x180076f45  mov     rsp, r11
0x180076f48  pop     r15
0x180076f4a  pop     r14
0x180076f4c  pop     r13
0x180076f4e  pop     rdi
0x180076f4f  pop     rsi
0x180076f50  retn
```
