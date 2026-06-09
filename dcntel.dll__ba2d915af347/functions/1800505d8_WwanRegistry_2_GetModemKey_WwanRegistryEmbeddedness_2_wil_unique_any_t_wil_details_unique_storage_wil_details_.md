# WwanRegistry_2::GetModemKey(WwanRegistryEmbeddedness_2,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)

- ea: `0x1800505d8`
- end: `0x18005075f`
- name: `?GetModemKey@WwanRegistry_2@@CA_NW4WwanRegistryEmbeddedness_2@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `391`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18004f950`
- `0x18004fc70`
- `0x180050770`
- `0x1800509dc`
- `0x180050f50`
- `0x180050fe0`

## callees

- `0x180008dc0`
- `0x18004f8b0`
- `0x1800505d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050657`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050644`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180050700`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180050700`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005064f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050718`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050755`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005064f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050718`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050755`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800506be`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800506be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050678`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050678`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall WwanRegistry_2::GetModemKey(int a1, HKEY *a2)
{
  DWORD v4; // r14d
  DWORD i; // edx
  HKEY v6; // rdi
  DWORD LastError; // ebx
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  int pvData; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD pcbData[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  cchName = 260;
  if ( (unsigned __int8)WwanRegistry_2::GetBaseKey(&hKey) )
  {
    v4 = 0;
    for ( i = 0; !RegEnumKeyExW(hKey, i, SubKey, &cchName, 0, 0, 0, 0); i = v4 )
    {
      v6 = *a2;
      if ( *a2 )
      {
        LastError = GetLastError();
        RegCloseKey(v6);
        SetLastError(LastError);
      }
      *a2 = 0;
      if ( RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, a2) )
        break;
      pvData = 0;
      pcbData[0] = 4;
      if ( RegGetValueW(*a2, 0, L"Embeddedness", 0x18u, 0, &pvData, pcbData) )
        break;
      if ( pvData == a1 )
      {
        if ( hKey )
          RegCloseKey(hKey);
        return 1;
      }
      ++v4;
      cchName = 260;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800505d8  mov     [rsp-8+arg_0], rbx
0x1800505dd  mov     [rsp-8+arg_10], rsi
0x1800505e2  push    rbp
0x1800505e3  push    rdi
0x1800505e4  push    r12
0x1800505e6  push    r14
0x1800505e8  push    r15
0x1800505ea  lea     rbp, [rsp-180h]
0x1800505f2  sub     rsp, 280h
0x1800505f9  mov     rax, cs:__security_cookie
0x180050600  xor     rax, rsp
0x180050603  mov     [rbp+1A0h+var_30], rax
0x18005060a  mov     rsi, rdx
0x18005060d  mov     r15d, ecx
0x180050610  xor     r12d, r12d
0x180050613  mov     [rsp+2A0h+hKey], r12
0x180050618  mov     [rsp+2A0h+cchName], 104h
0x180050620  lea     rcx, [rsp+2A0h+hKey]; phkResult
0x180050625  call    ?GetBaseKey@WwanRegistry_2@@CA_NAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; WwanRegistry_2::GetBaseKey(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x18005062a  test    al, al
0x18005062c  jz      loc_18005070E
0x180050632  mov     r14d, r12d
0x180050635  xor     edx, edx
0x180050637  jmp     loc_1800506DD
0x18005063c  mov     rdi, [rsi]
0x18005063f  test    rdi, rdi
0x180050642  jz      short loc_18005065D
0x180050644  call    cs:__imp_GetLastError
0x18005064a  mov     ebx, eax
0x18005064c  mov     rcx, rdi; hKey
0x18005064f  call    cs:__imp_RegCloseKey
0x180050655  mov     ecx, ebx; dwErrCode
0x180050657  call    cs:__imp_SetLastError
0x18005065d  mov     [rsi], r12
0x180050660  mov     [rsp+2A0h+phkResult], rsi; phkResult
0x180050665  mov     r9d, 20019h; samDesired
0x18005066b  xor     r8d, r8d; ulOptions
0x18005066e  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x180050673  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180050678  call    cs:__imp_RegOpenKeyExW
0x18005067e  test    eax, eax
0x180050680  jnz     loc_18005070E
0x180050686  mov     [rsp+2A0h+var_254], r12d
0x18005068b  mov     [rsp+2A0h+var_250], 4
0x180050693  lea     rax, [rsp+2A0h+var_250]
0x180050698  mov     [rsp+2A0h+pcbData], rax; pcbData
0x18005069d  lea     rax, [rsp+2A0h+var_254]
0x1800506a2  mov     [rsp+2A0h+pvData], rax; pvData
0x1800506a7  mov     [rsp+2A0h+phkResult], r12; pdwType
0x1800506ac  mov     r9d, 18h; dwFlags
0x1800506b2  lea     r8, aEmbeddedness; "Embeddedness"
0x1800506b9  xor     edx, edx; lpSubKey
0x1800506bb  mov     rcx, [rsi]; hkey
0x1800506be  call    cs:__imp_RegGetValueW
0x1800506c4  test    eax, eax
0x1800506c6  jnz     short loc_18005070E
0x1800506c8  cmp     [rsp+2A0h+var_254], r15d
0x1800506cd  jz      short loc_18005074B
0x1800506cf  inc     r14d
0x1800506d2  mov     [rsp+2A0h+cchName], 104h
0x1800506da  mov     edx, r14d; dwIndex
0x1800506dd  mov     [rsp+2A0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800506e2  mov     [rsp+2A0h+pcbData], r12; lpcchClass
0x1800506e7  mov     [rsp+2A0h+pvData], r12; lpClass
0x1800506ec  mov     [rsp+2A0h+phkResult], r12; lpReserved
0x1800506f1  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x1800506f6  lea     r8, [rsp+2A0h+SubKey]; lpName
0x1800506fb  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180050700  call    cs:__imp_RegEnumKeyExW
0x180050706  test    eax, eax
0x180050708  jz      loc_18005063C
0x18005070e  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180050713  test    rcx, rcx
0x180050716  jz      short loc_18005071E
0x180050718  call    cs:__imp_RegCloseKey
0x18005071e  xor     al, al
0x180050720  mov     rcx, [rbp+1A0h+var_30]
0x180050727  xor     rcx, rsp; StackCookie
0x18005072a  call    __security_check_cookie
0x18005072f  lea     r11, [rsp+2A0h+var_20]
0x180050737  mov     rbx, [r11+30h]
0x18005073b  mov     rsi, [r11+40h]
0x18005073f  mov     rsp, r11
0x180050742  pop     r15
0x180050744  pop     r14
0x180050746  pop     r12
0x180050748  pop     rdi
0x180050749  pop     rbp
0x18005074a  retn
0x18005074b  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180050750  test    rcx, rcx
0x180050753  jz      short loc_18005075B
0x180050755  call    cs:__imp_RegCloseKey
0x18005075b  mov     al, 1
0x18005075d  jmp     short loc_180050720
```
