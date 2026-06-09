# CClassMoniker::GetDisplayName(IBindCtx *,IMoniker *,ushort * *)

- ea: `0x18004ddc0`
- end: `0x18004df9a`
- name: `?GetDisplayName@CClassMoniker@@UEAAJPEAUIBindCtx@@PEAUIMoniker@@PEAPEAG@Z`
- size: `474`
- prototype: `HRESULT __fastcall(CClassMoniker *this, IBindCtx *pbc, IMoniker *pmkToLeft, wchar_t **lplpszDisplayName)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800077fc`
- `0x18000fc2c`
- `0x18001a630`
- `0x180046460`
- `0x18004c254`
- `0x18004ddc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004deaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004deaa`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18004de44`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18004de44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004df49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004df5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004df49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004df5d`

## pseudocode

```c
__int64 __fastcall CClassMoniker::GetDisplayName(
        CClassMoniker *this,
        IBindCtx *pbc,
        IMoniker *pmkToLeft,
        wchar_t **lplpszDisplayName)
{
  wchar_t *v5; // rdi
  const wchar_t *pExtra; // rbp
  int v7; // eax
  __int64 v8; // r8
  HRESULT v9; // ebx
  __int64 v10; // r8
  int v11; // eax
  int v12; // r8d
  int v13; // r8d
  int v14; // eax
  int v15; // r8d
  __int64 v16; // r8
  unsigned __int64 v17; // rsi
  wchar_t *v18; // rax
  wchar_t *pszPrefix; // [rsp+20h] [rbp-98h] BYREF
  wchar_t szClassID[40]; // [rsp+30h] [rbp-88h] BYREF

  pszPrefix = 0;
  v5 = 0;
  if ( !lplpszDisplayName )
    return 2147942487LL;
  *lplpszDisplayName = 0;
  if ( !pbc )
    return 2147942487LL;
  pExtra = (const wchar_t *)this->_pExtra;
  v7 = safe_lstrlenW(pExtra);
  if ( 2LL * v7 > (unsigned __int64)*(unsigned int *)(v8 + 44) )
    return 2147942487LL;
  wStringFromUUID((const _GUID *)(v8 + 28), szClassID);
  v9 = ProgIDFromCLSID(&CLSID_ClassMoniker, &pszPrefix);
  if ( v9 >= 0 )
  {
    v10 = -1;
    do
      ++v10;
    while ( szClassID[v10] );
    v11 = safe_lstrlenW(pszPrefix);
    v13 = v11 + 1 + v12;
    if ( pExtra )
    {
      v14 = safe_lstrlenW(pExtra);
      v13 = v14 + v15;
    }
    v16 = (unsigned int)(v13 + 2);
    if ( (unsigned int)v16 <= 0x7FFFFFFF )
    {
      v17 = (unsigned int)v16;
      v18 = (wchar_t *)CoTaskMemAlloc(2 * v16);
      v5 = v18;
      if ( v18 )
      {
        v9 = StringCchCopyW(v18, (unsigned int)v17, pszPrefix);
        if ( v9 >= 0 )
        {
          v9 = StringCchCatW(v5, (unsigned int)v17, L":");
          if ( v9 >= 0 )
          {
            v9 = StringCchCatW(v5, (unsigned int)v17, szClassID);
            if ( v9 >= 0 )
            {
              if ( !pExtra || (v9 = StringCchCatW(v5, (unsigned int)v17, pExtra), v9 >= 0) )
              {
                v9 = StringCchCatW(v5, v17, L":");
                if ( v9 >= 0 )
                {
                  *lplpszDisplayName = v5;
                  v9 = 0;
                  v5 = 0;
                }
              }
            }
          }
        }
      }
      else
      {
        v9 = -2147024882;
      }
    }
    else
    {
      v9 = -2147024809;
    }
  }
  if ( pszPrefix )
    CoTaskMemFree(pszPrefix);
  if ( v5 )
    CoTaskMemFree(v5);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004ddc0  mov     [rsp+arg_8], rbx
0x18004ddc5  push    rbp
0x18004ddc6  push    rsi
0x18004ddc7  push    rdi
0x18004ddc8  push    r14
0x18004ddca  push    r15
0x18004ddcc  sub     rsp, 90h
0x18004ddd3  mov     rax, cs:__security_cookie
0x18004ddda  xor     rax, rsp
0x18004dddd  mov     [rsp+0B8h+var_38], rax
0x18004dde5  xor     r15d, r15d
0x18004dde8  mov     r14, lplpszDisplayName
0x18004ddeb  mov     [rsp+0B8h+pszPrefix], r15
0x18004ddf0  mov     pmkToLeft, this
0x18004ddf3  mov     edi, r15d
0x18004ddf6  test    lplpszDisplayName, lplpszDisplayName
0x18004ddf9  jz      loc_18004DF6D
0x18004ddff  mov     [lplpszDisplayName], r15
0x18004de02  test    pbc, pbc
0x18004de05  jz      loc_18004DF6D
0x18004de0b  mov     rbp, [this+30h]
0x18004de0f  mov     this, rbp; string
0x18004de12  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004de17  movsxd  this, eax
0x18004de1a  mov     eax, [pmkToLeft+2Ch]
0x18004de1e  add     this, this
0x18004de21  cmp     this, rax
0x18004de24  ja      loc_18004DF6D
0x18004de2a  lea     this, [pmkToLeft+1Ch]; rguid
0x18004de2e  lea     pbc, [rsp+0B8h+szClassID]; lpsz
0x18004de33  call    ?wStringFromUUID@@YAJAEBU_GUID@@PEAG@Z; wStringFromUUID(_GUID const &,ushort *)
0x18004de38  lea     pbc, [rsp+0B8h+pszPrefix]; lplpszProgID
0x18004de3d  lea     this, CLSID_ClassMoniker; clsid
0x18004de44  call    cs:__imp_ProgIDFromCLSID
0x18004de4b  nop     dword ptr [rax+rax+00h]
0x18004de50  mov     ebx, eax
0x18004de52  test    eax, eax
0x18004de54  js      $Cleanup_0
0x18004de5a  lea     rax, [rsp+0B8h+szClassID]
0x18004de5f  or      pmkToLeft, 0FFFFFFFFFFFFFFFFh
0x18004de63  inc     pmkToLeft
0x18004de66  cmp     [rax+pmkToLeft*2], r15w
0x18004de6b  jnz     short loc_18004DE63
0x18004de6d  mov     this, [rsp+0B8h+pszPrefix]; string
0x18004de72  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004de77  inc     eax
0x18004de79  add     r8d, eax
0x18004de7c  test    rbp, rbp
0x18004de7f  jz      short loc_18004DE8C
0x18004de81  mov     this, rbp; string
0x18004de84  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004de89  add     r8d, eax
0x18004de8c  add     r8d, 2
0x18004de90  cmp     r8d, 7FFFFFFFh
0x18004de97  jbe     short loc_18004DEA3
0x18004de99  mov     ebx, 80070057h
0x18004de9e  jmp     $Cleanup_0
0x18004dea3  lea     this, [pmkToLeft+pmkToLeft]; cb
0x18004dea7  mov     esi, r8d
0x18004deaa  call    cs:__imp_CoTaskMemAlloc
0x18004deb1  nop     dword ptr [rax+rax+00h]
0x18004deb6  mov     rdi, rax
0x18004deb9  test    rax, rax
0x18004debc  jz      short loc_18004DF3A
0x18004debe  mov     pmkToLeft, [rsp+0B8h+pszPrefix]; pszSrc
0x18004dec3  mov     edx, esi; cchDest
0x18004dec5  mov     this, rax; pszDest
0x18004dec8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004decd  mov     ebx, eax
0x18004decf  test    eax, eax
0x18004ded1  js      short $Cleanup_0
0x18004ded3  lea     pmkToLeft, asc_1800EACD4; ":"
0x18004deda  mov     edx, esi; cchDest
0x18004dedc  mov     this, rdi; pszDest
0x18004dedf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004dee4  mov     ebx, eax
0x18004dee6  test    eax, eax
0x18004dee8  js      short $Cleanup_0
0x18004deea  lea     pmkToLeft, [rsp+0B8h+szClassID]; pszSrc
0x18004deef  mov     edx, esi; cchDest
0x18004def1  mov     this, rdi; pszDest
0x18004def4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004def9  mov     ebx, eax
0x18004defb  test    eax, eax
0x18004defd  js      short $Cleanup_0
0x18004deff  test    rbp, rbp
0x18004df02  jz      short loc_18004DF17
0x18004df04  mov     pmkToLeft, rbp; pszSrc
0x18004df07  mov     edx, esi; cchDest
0x18004df09  mov     this, rdi; pszDest
0x18004df0c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004df11  mov     ebx, eax
0x18004df13  test    eax, eax
0x18004df15  js      short $Cleanup_0
0x18004df17  lea     pmkToLeft, asc_1800EACD4; ":"
0x18004df1e  mov     pbc, rsi; cchDest
0x18004df21  mov     this, rdi; pszDest
0x18004df24  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004df29  mov     ebx, eax
0x18004df2b  test    eax, eax
0x18004df2d  js      short $Cleanup_0
0x18004df2f  mov     [r14], rdi
0x18004df32  mov     ebx, r15d
0x18004df35  mov     rdi, r15
0x18004df38  jmp     short $Cleanup_0
0x18004df3a  mov     ebx, 8007000Eh
0x18004df3f  mov     this, [rsp+0B8h+pszPrefix]; pv
0x18004df44  test    this, this
0x18004df47  jz      short loc_18004DF55
0x18004df49  call    cs:__imp_CoTaskMemFree
0x18004df50  nop     dword ptr [rax+rax+00h]
0x18004df55  test    rdi, rdi
0x18004df58  jz      short loc_18004DF69
0x18004df5a  mov     this, rdi; pv
0x18004df5d  call    cs:__imp_CoTaskMemFree
0x18004df64  nop     dword ptr [rax+rax+00h]
0x18004df69  mov     eax, ebx
0x18004df6b  jmp     short loc_18004DF72
0x18004df6d  mov     eax, 80070057h
0x18004df72  mov     this, [rsp+0B8h+var_38]
0x18004df7a  xor     this, rsp; StackCookie
0x18004df7d  call    __security_check_cookie
0x18004df82  mov     rbx, [rsp+0B8h+arg_8]
0x18004df8a  add     rsp, 90h
0x18004df91  pop     r15
0x18004df93  pop     r14
0x18004df95  pop     rdi
0x18004df96  pop     rsi
0x18004df97  pop     rbp
0x18004df98  retn
```
