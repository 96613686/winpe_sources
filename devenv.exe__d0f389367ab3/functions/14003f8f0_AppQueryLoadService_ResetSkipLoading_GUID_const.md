# AppQueryLoadService::ResetSkipLoading(_GUID const &)

- ea: `0x14003f8f0`
- end: `0x14003f9c5`
- name: `?ResetSkipLoading@AppQueryLoadService@@UEAAJAEBU_GUID@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(AppQueryLoadService *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x140001020`
- `0x140004a0c`
- `0x140004f28`
- `0x14003f8f0`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x14003f977`
- `ADVAPI32!RegDeleteValueW` at `0x14003f977`
- `ADVAPI32!RegCloseKey` at `0x14003f9a5`
- `ADVAPI32!RegCloseKey` at `0x14003f9a5`
- `OLEAUT32!__imp_SysFreeString` at `0x14003f997`
- `OLEAUT32!__imp_SysFreeString` at `0x14003f997`

## pseudocode

```c
__int64 __fastcall AppQueryLoadService::ResetSkipLoading(AppQueryLoadService *this, const struct _GUID *a2)
{
  const unsigned __int16 *v2; // rcx
  HKEY v4; // rbx
  int v5; // eax
  unsigned int v6; // esi
  LSTATUS v7; // eax
  BSTR bstrString; // [rsp+20h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+28h] [rbp-20h] BYREF

  v2 = (const unsigned __int16 *)**((_QWORD **)this + 8);
  if ( !v2 )
    return 2147549183LL;
  v4 = 0;
  bstrString = 0;
  hKey = 0;
  util_GetPackageRegKey(v2, a2, &bstrString);
  if ( bstrString && (v5 = CVsRegKeyW::Open(&hKey, HKEY_CURRENT_USER, bstrString, 0x2001Fu), v4 = hKey, v5 >= 0) )
  {
    if ( hKey )
    {
      v7 = RegDeleteValueW(hKey, L"SkipLoading");
      v6 = (unsigned __int16)v7 | 0x80070000;
      if ( v7 <= 0 )
        v6 = v7;
    }
    else
    {
      v6 = -2147418113;
    }
  }
  else
  {
    v6 = -2147467259;
  }
  SysFreeString(bstrString);
  if ( v4 )
    RegCloseKey(v4);
  return v6;
}

```

## disassembly

```asm
0x14003f8f0  mov     [rsp+arg_10], rbx
0x14003f8f5  push    rsi
0x14003f8f6  sub     rsp, 40h
0x14003f8fa  mov     rax, cs:__security_cookie
0x14003f901  xor     rax, rsp
0x14003f904  mov     [rsp+48h+var_18], rax
0x14003f909  mov     rax, [rcx+40h]
0x14003f90d  mov     rcx, [rax]; unsigned __int16 *
0x14003f910  test    rcx, rcx
0x14003f913  jnz     short loc_14003F91F
0x14003f915  mov     eax, 8000FFFFh
0x14003f91a  jmp     loc_14003F9AD
0x14003f91f  xor     ebx, ebx
0x14003f921  lea     r8, [rsp+48h+bstrString]; unsigned __int16 **
0x14003f926  and     [rsp+48h+bstrString], rbx
0x14003f92b  mov     [rsp+48h+hKey], rbx
0x14003f930  call    ?util_GetPackageRegKey@@YAJPEBGAEBU_GUID@@PEAPEAG@Z; util_GetPackageRegKey(ushort const *,_GUID const &,ushort * *)
0x14003f935  cmp     [rsp+48h+bstrString], rbx
0x14003f93a  jz      short loc_14003F98D
0x14003f93c  mov     r8, [rsp+48h+bstrString]; unsigned __int16 *
0x14003f941  lea     rcx, [rsp+48h+hKey]; this
0x14003f946  mov     r9d, 2001Fh; unsigned int
0x14003f94c  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x14003f953  call    ?Open@CVsRegKeyW@@QEAAJPEAUHKEY__@@PEBGK@Z; CVsRegKeyW::Open(HKEY__ *,ushort const *,ulong)
0x14003f958  mov     rbx, [rsp+48h+hKey]
0x14003f95d  test    eax, eax
0x14003f95f  js      short loc_14003F98D
0x14003f961  test    rbx, rbx
0x14003f964  jnz     short loc_14003F96D
0x14003f966  mov     esi, 8000FFFFh
0x14003f96b  jmp     short loc_14003F992
0x14003f96d  lea     rdx, aSkiploading; "SkipLoading"
0x14003f974  mov     rcx, rbx; hKey
0x14003f977  call    cs:__imp_RegDeleteValueW
0x14003f97d  movzx   esi, ax
0x14003f980  or      esi, 80070000h
0x14003f986  test    eax, eax
0x14003f988  cmovle  esi, eax
0x14003f98b  jmp     short loc_14003F992
0x14003f98d  mov     esi, 80004005h
0x14003f992  mov     rcx, [rsp+48h+bstrString]; bstrString
0x14003f997  call    cs:__imp_SysFreeString
0x14003f99d  test    rbx, rbx
0x14003f9a0  jz      short loc_14003F9AB
0x14003f9a2  mov     rcx, rbx; hKey
0x14003f9a5  call    cs:__imp_RegCloseKey
0x14003f9ab  mov     eax, esi
0x14003f9ad  mov     rcx, [rsp+48h+var_18]
0x14003f9b2  xor     rcx, rsp; StackCookie
0x14003f9b5  call    __security_check_cookie
0x14003f9ba  mov     rbx, [rsp+48h+arg_10]
0x14003f9bf  add     rsp, 40h
0x14003f9c3  pop     rsi
0x14003f9c4  retn
```
