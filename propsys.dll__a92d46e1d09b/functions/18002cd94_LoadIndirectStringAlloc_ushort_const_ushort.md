# LoadIndirectStringAlloc(ushort const *,ushort * *)

- ea: `0x18002cd94`
- end: `0x18002cfc9`
- name: `?LoadIndirectStringAlloc@@YAJPEBGPEAPEAG@Z`
- size: `565`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `7`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002ae2c`
- `0x18002bbf0`
- `0x18002c3fc`
- `0x18002d8f0`
- `0x180056c80`
- `0x180064370`
- `0x18008372c`

## callees

- `0x18002cd94`
- `0x18002cfd0`
- `0x18002d044`
- `0x18006ed20`
- `0x18006fb98`
- `0x180083ae8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002ce24`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002ce24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ce0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ce0e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18002cdef`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18002cdef`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x18002cdf9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x18002cdf9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18002cddf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18002cddf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18002cf91`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18002cf91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002cebf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002cebf`

## string_xrefs

- `0x18002cdcd`: `@propsys.dll,-`

## pseudocode

```c
__int64 __fastcall LoadIndirectStringAlloc(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  const WCHAR *v2; // rdi
  PWSTR v4; // rax
  int v5; // eax
  UINT v6; // esi
  HINSTANCE v7; // rbx
  bool v8; // zf
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rdi
  unsigned int DllString; // ebx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rdx
  WCHAR *v15; // rcx
  unsigned __int64 v16; // r8
  __int64 v17; // r10
  unsigned __int16 *v18; // rcx
  __int64 v19; // r9
  __int64 v20; // rdi
  bool v21; // cf
  unsigned int v22; // r8d
  WCHAR Buffer[512]; // [rsp+30h] [rbp-648h] BYREF
  unsigned __int16 v24[272]; // [rsp+430h] [rbp-248h] BYREF

  v2 = &Src;
  *a2 = 0;
  if ( a1 )
    v2 = a1;
  if ( StrCmpNICW(v2, L"@propsys.dll,-", 14)
    || (v4 = StrChrW(v2, 0x2Cu), v5 = StrToIntW(v4 + 1), v6 = -v5, !v5)
    || (v7 = g_hModMUIResources, SetLastError(0), !LoadStringW(v7, v6, Buffer, 512)) && (int)ResultFromLastError() < 0 )
  {
    v8 = *v2 == 64;
    Buffer[0] = 0;
    if ( v8 )
    {
      SHExpandEnvironmentStringsW(v2 + 1, v24, 267);
      DllString = _LoadDllString(v24, Buffer, v22);
      if ( (DllString & 0x80000000) != 0 )
        return DllString;
    }
    else if ( Buffer != v2 )
    {
      StringCchCopyW(Buffer, 0x200u, v2);
    }
  }
  v9 = -1;
  do
    ++v9;
  while ( Buffer[v9] );
  v10 = v9 + 1;
  *a2 = 0;
  if ( v9 + 1 < v9 || !is_mul_ok(v10, 2u) )
    return (unsigned int)-2147024362;
  v13 = (unsigned __int16 *)CoTaskMemAlloc(2 * v10);
  *a2 = v13;
  v14 = v13;
  DllString = v13 == 0 ? 0x8007000E : 0;
  if ( !v13 )
    return DllString;
  if ( v10 > 0x7FFFFFFF )
  {
LABEL_32:
    *v13 = 0;
    return DllString;
  }
  if ( v9 >= 0x7FFFFFFF )
  {
    if ( v9 == -1 )
      return DllString;
    goto LABEL_32;
  }
  v15 = Buffer;
  v16 = v9 + 1;
  v17 = 0;
  do
  {
    if ( !v9 )
      break;
    if ( !*v15 )
      break;
    *v13++ = *v15++;
    --v9;
    ++v17;
    --v16;
  }
  while ( v16 );
  v18 = v13 - 1;
  v19 = v17 - 1;
  if ( v16 )
  {
    v18 = v13;
    v19 = v17;
  }
  *v18 = 0;
  if ( v16 )
  {
    v21 = v10 == v19;
    v20 = v10 - v19;
    if ( !v21 && v20 != 1 && (unsigned __int64)(2 * v20) > 2 )
      memset_0(&v14[v19 + 1], 0, 2 * v20 - 2);
  }
  return DllString;
}

```

## disassembly

```asm
0x18002cd94  mov     [rsp+arg_10], rbx
0x18002cd99  mov     [rsp+arg_18], rbp
0x18002cd9e  push    rsi
0x18002cd9f  push    rdi
0x18002cda0  push    r14
0x18002cda2  sub     rsp, 660h
0x18002cda9  mov     rax, cs:__security_cookie
0x18002cdb0  xor     rax, rsp
0x18002cdb3  mov     [rsp+678h+var_28], rax
0x18002cdbb  xor     ebp, ebp
0x18002cdbd  lea     rdi, Src
0x18002cdc4  test    rcx, rcx
0x18002cdc7  mov     [rdx], rbp
0x18002cdca  mov     r14, rdx
0x18002cdcd  lea     rdx, aPropsysDll_1; "@propsys.dll,-"
0x18002cdd4  cmovnz  rdi, rcx
0x18002cdd8  mov     rcx, rdi; pszStr1
0x18002cddb  lea     r8d, [rbp+0Eh]; nChar
0x18002cddf  call    cs:__imp_StrCmpNICW
0x18002cde5  test    eax, eax
0x18002cde7  jnz     short loc_18002CE37
0x18002cde9  lea     edx, [rbp+2Ch]; wMatch
0x18002cdec  mov     rcx, rdi; pszStart
0x18002cdef  call    cs:__imp_StrChrW
0x18002cdf5  lea     rcx, [rax+2]; pszSrc
0x18002cdf9  call    cs:__imp_StrToIntW
0x18002cdff  mov     esi, eax
0x18002ce01  neg     esi
0x18002ce03  jz      short loc_18002CE37
0x18002ce05  mov     rbx, cs:?g_hModMUIResources@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hModMUIResources
0x18002ce0c  xor     ecx, ecx; dwErrCode
0x18002ce0e  call    cs:__imp_SetLastError
0x18002ce14  mov     r9d, 200h; cchBufferMax
0x18002ce1a  lea     r8, [rsp+678h+Buffer]; lpBuffer
0x18002ce1f  mov     edx, esi; uID
0x18002ce21  mov     rcx, rbx; hInstance
0x18002ce24  call    cs:__imp_LoadStringW
0x18002ce2a  test    eax, eax
0x18002ce2c  jnz     short loc_18002CE62
0x18002ce2e  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002ce33  test    eax, eax
0x18002ce35  jns     short loc_18002CE62
0x18002ce37  cmp     word ptr [rdi], 40h ; '@'
0x18002ce3b  mov     [rsp+678h+Buffer], bp
0x18002ce40  jz      loc_18002CF7F
0x18002ce46  lea     rax, [rsp+678h+Buffer]
0x18002ce4b  cmp     rax, rdi
0x18002ce4e  jz      short loc_18002CE62
0x18002ce50  mov     r8, rdi; unsigned __int16 *
0x18002ce53  lea     rcx, [rsp+678h+Buffer]; unsigned __int16 *
0x18002ce58  mov     edx, 200h; unsigned __int64
0x18002ce5d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ce62  lea     rax, [rsp+678h+Buffer]
0x18002ce67  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002ce6b  inc     rsi
0x18002ce6e  cmp     [rax+rsi*2], bp
0x18002ce72  jnz     short loc_18002CE6B
0x18002ce74  lea     rdi, [rsi+1]
0x18002ce78  mov     [r14], rbp
0x18002ce7b  cmp     rdi, rsi
0x18002ce7e  jnb     short loc_18002CEAF
0x18002ce80  mov     ebx, 80070216h
0x18002ce85  mov     eax, ebx
0x18002ce87  mov     rcx, [rsp+678h+var_28]
0x18002ce8f  xor     rcx, rsp; StackCookie
0x18002ce92  call    __security_check_cookie
0x18002ce97  lea     r11, [rsp+678h+var_18]
0x18002ce9f  mov     rbx, [r11+30h]
0x18002cea3  mov     rbp, [r11+38h]
0x18002cea7  mov     rsp, r11
0x18002ceaa  pop     r14
0x18002ceac  pop     rdi
0x18002cead  pop     rsi
0x18002ceae  retn
0x18002ceaf  mov     eax, 2
0x18002ceb4  mul     rdi
0x18002ceb7  test    rdx, rdx
0x18002ceba  jnz     short loc_18002CE80
0x18002cebc  mov     rcx, rax; cb
0x18002cebf  call    cs:__imp_CoTaskMemAlloc
0x18002cec5  mov     rcx, rax
0x18002cec8  mov     [r14], rax
0x18002cecb  neg     rcx
0x18002cece  mov     rdx, rax
0x18002ced1  sbb     ebx, ebx
0x18002ced3  not     ebx
0x18002ced5  and     ebx, 8007000Eh
0x18002cedb  test    rax, rax
0x18002cede  jz      short loc_18002CE85
0x18002cee0  mov     eax, 7FFFFFFFh
0x18002cee5  cmp     rdi, rax
0x18002cee8  ja      loc_18002CFC1
0x18002ceee  cmp     rsi, rax
0x18002cef1  jnb     loc_18002CFB8
0x18002cef7  test    rdi, rdi
0x18002cefa  jz      short loc_18002CE85
0x18002cefc  lea     rcx, [rsp+678h+Buffer]
0x18002cf01  mov     r8, rdi
0x18002cf04  mov     rax, rdx
0x18002cf07  mov     r10, rbp
0x18002cf0a  test    rsi, rsi
0x18002cf0d  jz      short loc_18002CF31
0x18002cf0f  movzx   r9d, word ptr [rcx]
0x18002cf13  test    r9w, r9w
0x18002cf17  jz      short loc_18002CF31
0x18002cf19  mov     [rax], r9w
0x18002cf1d  add     rcx, 2
0x18002cf21  add     rax, 2
0x18002cf25  dec     rsi
0x18002cf28  inc     r10
0x18002cf2b  sub     r8, 1
0x18002cf2f  jnz     short loc_18002CF0A
0x18002cf31  test    r8, r8
0x18002cf34  lea     rcx, [rax-2]
0x18002cf38  lea     r9, [r10-1]
0x18002cf3c  cmovnz  rcx, rax
0x18002cf40  cmovnz  r9, r10
0x18002cf44  mov     [rcx], bp
0x18002cf47  jz      loc_18002CE85
0x18002cf4d  sub     rdi, r9
0x18002cf50  cmp     rdi, 1
0x18002cf54  jbe     loc_18002CE85
0x18002cf5a  lea     r8, [rdi+rdi]
0x18002cf5e  cmp     r8, 2
0x18002cf62  jbe     loc_18002CE85
0x18002cf68  inc     r9
0x18002cf6b  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18002cf6f  lea     rcx, [rdx+r9*2]; void *
0x18002cf73  xor     edx, edx; Val
0x18002cf75  call    memset_0
0x18002cf7a  jmp     loc_18002CE85
0x18002cf7f  lea     rcx, [rdi+2]
0x18002cf83  mov     r8d, 10Bh
0x18002cf89  lea     rdx, [rsp+678h+var_248]
0x18002cf91  call    cs:__imp_SHExpandEnvironmentStringsW
0x18002cf97  lea     rdx, [rsp+678h+Buffer]; lpBuffer
0x18002cf9c  lea     rcx, [rsp+678h+var_248]; unsigned __int16 *
0x18002cfa4  call    ?_LoadDllString@@YAJPEBGPEAGI@Z; _LoadDllString(ushort const *,ushort *,uint)
0x18002cfa9  mov     ebx, eax
0x18002cfab  test    eax, eax
0x18002cfad  jns     loc_18002CE62
0x18002cfb3  jmp     loc_18002CE85
0x18002cfb8  test    rdi, rdi
0x18002cfbb  jz      loc_18002CE85
0x18002cfc1  mov     [rdx], bp
0x18002cfc4  jmp     loc_18002CE85
```
