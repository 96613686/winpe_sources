# CObjectIdentityInterrogator::_GetIdentityFromCLSID(_GUID const &,ushort * *)

- ea: `0x180085a5c`
- end: `0x180085ca5`
- name: `?_GetIdentityFromCLSID@CObjectIdentityInterrogator@@IEAAJAEBU_GUID@@PEAPEAG@Z`
- size: `585`
- prototype: `int(CObjectIdentityInterrogator *__hidden this, const struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180085940`

## callees

- `0x180033148`
- `0x18006ed20`
- `0x18006fb98`
- `0x1800858d4`
- `0x180085a5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180085b32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180085b32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085c51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085c51`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180085aa6`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180085aa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085c76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085c76`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180085c25`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180085c25`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x180085b73`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x180085b73`

## string_xrefs

- `0x180085aca`: `CLSID\`

## pseudocode

```c
__int64 __fastcall CObjectIdentityInterrogator::_GetIdentityFromCLSID(
        CObjectIdentityInterrogator *this,
        const struct _GUID *a2,
        unsigned __int16 **a3)
{
  HRESULT v5; // ebx
  CObjectIdentityInterrogator *v6; // rcx
  unsigned int v7; // esi
  CObjectIdentityInterrogator *v8; // rcx
  LPOLESTR v9; // rcx
  LPCWSTR pszSubKey[5]; // [rsp+40h] [rbp-C0h]
  LPOLESTR lpsz; // [rsp+68h] [rbp-98h] BYREF
  HKEY hkey; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SubKey[7]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v16[514]; // [rsp+8Eh] [rbp-72h] BYREF
  unsigned __int16 pvData[264]; // [rsp+290h] [rbp+190h] BYREF

  *a3 = 0;
  lpsz = 0;
  v5 = StringFromCLSID(a2, &lpsz);
  if ( v5 >= 0 )
  {
    if ( (*((_BYTE *)this + 8) & 4) != 0 )
    {
      wcscpy(SubKey, L"CLSID\\");
      memset_0(v16, 0, 0x1FAu);
      v5 = StringCchCatW(SubKey, 0x104u, lpsz);
      if ( v5 >= 0 )
      {
        hkey = 0;
        if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hkey) )
        {
          pvData[0] = 0;
          pcbData = 520;
          if ( SHQueryValueExW(hkey, 0, 0, 0, pvData, &pcbData) || !pvData[0] )
            v5 = -2147467259;
          else
            v5 = CObjectIdentityInterrogator::_FormatGuidIdentity(v6, lpsz, pvData, a3);
          if ( v5 < 0 )
          {
            v7 = 0;
            pszSubKey[0] = L"VersionIndependentProgID";
            pszSubKey[1] = L"ProgID";
            pszSubKey[2] = L"AppID";
            pszSubKey[3] = L"InprocServer32";
            pszSubKey[4] = L"LocalServer32 ";
            do
            {
              if ( v5 >= 0 )
                break;
              pcbData = 520;
              if ( !SHRegGetValueW(hkey, pszSubKey[v7], 0, 0, 0, pvData, &pcbData) )
                v5 = CObjectIdentityInterrogator::_FormatGuidIdentity(v8, lpsz, pvData, a3);
              ++v7;
            }
            while ( v7 < 5 );
          }
          RegCloseKey(hkey);
        }
      }
    }
    if ( *a3 )
    {
      v9 = lpsz;
    }
    else
    {
      v9 = 0;
      *a3 = lpsz;
      v5 = 0;
      lpsz = 0;
    }
    CoTaskMemFree(v9);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180085a5c  mov     [rsp-8+arg_0], rbx
0x180085a61  mov     [rsp-8+arg_18], rsi
0x180085a66  push    rbp
0x180085a67  push    rdi
0x180085a68  push    r14
0x180085a6a  lea     rbp, [rsp-3B0h]
0x180085a72  sub     rsp, 4B0h
0x180085a79  mov     rax, cs:__security_cookie
0x180085a80  xor     rax, rsp
0x180085a83  mov     [rbp+3C0h+var_20], rax
0x180085a8a  mov     rax, rdx
0x180085a8d  mov     rsi, rcx
0x180085a90  xor     r14d, r14d
0x180085a93  lea     rdx, [rsp+4C0h+lpsz]; lplpsz
0x180085a98  mov     rcx, rax; rclsid
0x180085a9b  mov     [r8], r14
0x180085a9e  mov     rdi, r8
0x180085aa1  mov     [rsp+4C0h+lpsz], r14
0x180085aa6  call    cs:__imp_StringFromCLSID
0x180085aac  mov     ebx, eax
0x180085aae  test    eax, eax
0x180085ab0  js      loc_180085C7C
0x180085ab6  test    byte ptr [rsi+8], 4
0x180085aba  jz      loc_180085C57
0x180085ac0  mov     eax, dword ptr cs:aClsid_0+8; "D\\"
0x180085ac6  lea     rcx, [rbp+3C0h+var_432]; void *
0x180085aca  movsd   xmm0, qword ptr cs:aClsid_0; "CLSID\\"
0x180085ad2  xor     edx, edx; Val
0x180085ad4  mov     [rbp+3C0h+var_438], eax
0x180085ad7  mov     r8d, 1FAh; Size
0x180085add  movzx   eax, word ptr cs:aClsid_0+0Ch; ""
0x180085ae4  mov     [rbp+3C0h+var_434], ax
0x180085ae8  movsd   qword ptr [rbp+3C0h+SubKey], xmm0
0x180085aed  call    memset_0
0x180085af2  mov     r8, [rsp+4C0h+lpsz]; unsigned __int16 *
0x180085af7  lea     rcx, [rbp+3C0h+SubKey]; unsigned __int16 *
0x180085afb  mov     edx, 104h; unsigned __int64
0x180085b00  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180085b05  mov     ebx, eax
0x180085b07  test    eax, eax
0x180085b09  js      loc_180085C57
0x180085b0f  lea     rax, [rsp+4C0h+hkey]
0x180085b14  mov     [rsp+4C0h+hkey], r14
0x180085b19  mov     r9d, 20019h; samDesired
0x180085b1f  mov     [rsp+4C0h+phkResult], rax; phkResult
0x180085b24  xor     r8d, r8d; ulOptions
0x180085b27  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x180085b2b  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180085b32  call    cs:__imp_RegOpenKeyExW
0x180085b38  test    eax, eax
0x180085b3a  jnz     loc_180085C57
0x180085b40  mov     rcx, [rsp+4C0h+hkey]; hkey
0x180085b45  lea     rax, [rsp+4C0h+var_448]
0x180085b4a  mov     [rsp+4C0h+pcbData], rax; pcbData
0x180085b4f  xor     r9d, r9d; pdwType
0x180085b52  lea     rax, [rbp+3C0h+pvData]
0x180085b59  mov     [rbp+3C0h+pvData], r14w
0x180085b61  xor     r8d, r8d; pdwReserved
0x180085b64  mov     [rsp+4C0h+phkResult], rax; pvData
0x180085b69  xor     edx, edx; pszValue
0x180085b6b  mov     [rsp+4C0h+var_448], 208h
0x180085b73  call    cs:__imp_SHQueryValueExW
0x180085b79  test    eax, eax
0x180085b7b  jnz     short loc_180085B9F
0x180085b7d  cmp     [rbp+3C0h+pvData], r14w
0x180085b85  jz      short loc_180085B9F
0x180085b87  mov     rdx, [rsp+4C0h+lpsz]; unsigned __int16 *
0x180085b8c  lea     r8, [rbp+3C0h+pvData]; unsigned __int16 *
0x180085b93  mov     r9, rdi; unsigned __int16 **
0x180085b96  call    ?_FormatGuidIdentity@CObjectIdentityInterrogator@@IEAAJPEBGPEAGPEAPEAG@Z; CObjectIdentityInterrogator::_FormatGuidIdentity(ushort const *,ushort *,ushort * *)
0x180085b9b  mov     ebx, eax
0x180085b9d  jmp     short loc_180085BA4
0x180085b9f  mov     ebx, 80004005h
0x180085ba4  test    ebx, ebx
0x180085ba6  jns     loc_180085C4C
0x180085bac  lea     rax, aVersionindepen; "VersionIndependentProgID"
0x180085bb3  mov     esi, r14d
0x180085bb6  mov     [rsp+4C0h+pszSubKey], rax
0x180085bbb  lea     rax, aProgid; "ProgID"
0x180085bc2  mov     [rsp+4C0h+var_478], rax
0x180085bc7  lea     rax, aAppid; "AppID"
0x180085bce  mov     [rsp+4C0h+var_470], rax
0x180085bd3  lea     rax, aInprocserver32; "InprocServer32"
0x180085bda  mov     [rsp+4C0h+var_468], rax
0x180085bdf  lea     rax, aLocalserver32; "LocalServer32 "
0x180085be6  mov     [rsp+4C0h+var_460], rax
0x180085beb  test    ebx, ebx
0x180085bed  jns     short loc_180085C4C
0x180085bef  mov     rcx, [rsp+4C0h+hkey]; hkey
0x180085bf4  lea     rax, [rsp+4C0h+var_448]
0x180085bf9  mov     [rsp+4C0h+var_490], rax; pcbData
0x180085bfe  xor     r9d, r9d; srrfFlags
0x180085c01  lea     rax, [rbp+3C0h+pvData]
0x180085c08  movsxd  rdx, esi
0x180085c0b  mov     [rsp+4C0h+pcbData], rax; pvData
0x180085c10  xor     r8d, r8d; pszValue
0x180085c13  mov     [rsp+4C0h+phkResult], r14; pdwType
0x180085c18  mov     [rsp+4C0h+var_448], 208h
0x180085c20  mov     rdx, [rsp+rdx*8+4C0h+pszSubKey]; pszSubKey
0x180085c25  call    cs:__imp_SHRegGetValueW
0x180085c2b  test    eax, eax
0x180085c2d  jnz     short loc_180085C45
0x180085c2f  mov     rdx, [rsp+4C0h+lpsz]; unsigned __int16 *
0x180085c34  lea     r8, [rbp+3C0h+pvData]; unsigned __int16 *
0x180085c3b  mov     r9, rdi; unsigned __int16 **
0x180085c3e  call    ?_FormatGuidIdentity@CObjectIdentityInterrogator@@IEAAJPEBGPEAGPEAPEAG@Z; CObjectIdentityInterrogator::_FormatGuidIdentity(ushort const *,ushort *,ushort * *)
0x180085c43  mov     ebx, eax
0x180085c45  inc     esi
0x180085c47  cmp     esi, 5
0x180085c4a  jb      short loc_180085BEB
0x180085c4c  mov     rcx, [rsp+4C0h+hkey]; hKey
0x180085c51  call    cs:__imp_RegCloseKey
0x180085c57  cmp     [rdi], r14
0x180085c5a  jnz     short loc_180085C71
0x180085c5c  mov     rax, [rsp+4C0h+lpsz]
0x180085c61  mov     rcx, r14
0x180085c64  mov     [rdi], rax
0x180085c67  mov     ebx, r14d
0x180085c6a  mov     [rsp+4C0h+lpsz], rcx
0x180085c6f  jmp     short loc_180085C76
0x180085c71  mov     rcx, [rsp+4C0h+lpsz]; pv
0x180085c76  call    cs:__imp_CoTaskMemFree
0x180085c7c  mov     eax, ebx
0x180085c7e  mov     rcx, [rbp+3C0h+var_20]
0x180085c85  xor     rcx, rsp; StackCookie
0x180085c88  call    __security_check_cookie
0x180085c8d  lea     r11, [rsp+4C0h+var_10]
0x180085c95  mov     rbx, [r11+20h]
0x180085c99  mov     rsi, [r11+38h]
0x180085c9d  mov     rsp, r11
0x180085ca0  pop     r14
0x180085ca2  pop     rdi
0x180085ca3  pop     rbp
0x180085ca4  retn
```
