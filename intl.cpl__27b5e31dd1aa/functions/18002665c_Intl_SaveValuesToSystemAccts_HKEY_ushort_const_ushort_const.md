# Intl_SaveValuesToSystemAccts(HKEY__ *,ushort const *,ushort const *)

- ea: `0x18002665c`
- end: `0x180026734`
- name: `?Intl_SaveValuesToSystemAccts@@YAXPEAUHKEY__@@PEBG1@Z`
- size: `216`
- prototype: `void(HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180026234`

## callees

- `0x180024da4`
- `0x180024fdc`
- `0x180025078`
- `0x18002665c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800266a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800266a1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800266e6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800266e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026719`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026723`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026719`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026723`

## pseudocode

```c
void __fastcall Intl_SaveValuesToSystemAccts(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  HKEY phkResult; // [rsp+50h] [rbp-10h] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp+18h] BYREF
  int v6; // [rsp+7Ch] [rbp+1Ch]
  HKEY hKey; // [rsp+88h] [rbp+28h] BYREF

  v6 = HIDWORD(a2);
  phkResult = 0;
  hKey = 0;
  dwDisposition = 0;
  if ( !RegOpenKeyExW(a1, L"Control Panel\\International", 0, 0xF003Fu, &phkResult) )
  {
    if ( !RegCreateKeyExW(HKEY_USERS, a3, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition) )
    {
      if ( dwDisposition != 1 )
      {
        Intl_DeleteRegKeyValues(hKey);
        Intl_DeleteRegSubKeys(hKey);
      }
      Intl_CreateRegTree(phkResult, hKey);
      RegCloseKey(hKey);
    }
    RegCloseKey(phkResult);
  }
}

```

## disassembly

```asm
0x18002665c  mov     [rsp-8+arg_0], rbx
0x180026661  mov     qword ptr [rsp-8+dwDisposition], rdx
0x180026666  push    rbp
0x180026667  mov     rbp, rsp
0x18002666a  sub     rsp, 60h
0x18002666e  mov     rbx, r8
0x180026671  mov     [rbp+var_10], 0
0x180026679  lea     rax, [rbp+var_10]
0x18002667d  mov     [rbp+hKey], 0
0x180026685  xor     r8d, r8d; ulOptions
0x180026688  mov     [rsp+60h+phkResult], rax; phkResult
0x18002668d  mov     r9d, 0F003Fh; samDesired
0x180026693  mov     [rbp+dwDisposition], 0
0x18002669a  lea     rdx, ?c_szCPanelIntl@@3QBGB; "Control Panel\\International"
0x1800266a1  call    cs:__imp_RegOpenKeyExW
0x1800266a7  test    eax, eax
0x1800266a9  jnz     short loc_180026729
0x1800266ab  lea     rax, [rbp+dwDisposition]
0x1800266af  xor     r9d, r9d; lpClass
0x1800266b2  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x1800266b7  xor     r8d, r8d; Reserved
0x1800266ba  lea     rax, [rbp+hKey]
0x1800266be  mov     rdx, rbx; lpSubKey
0x1800266c1  mov     [rsp+60h+var_28], rax; phkResult
0x1800266c6  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800266cd  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800266d6  mov     [rsp+60h+samDesired], 20006h; samDesired
0x1800266de  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x1800266e6  call    cs:__imp_RegCreateKeyExW
0x1800266ec  test    eax, eax
0x1800266ee  jnz     short loc_18002671F
0x1800266f0  cmp     [rbp+dwDisposition], 1
0x1800266f4  jz      short loc_180026708
0x1800266f6  mov     rcx, [rbp+hKey]; hKey
0x1800266fa  call    ?Intl_DeleteRegKeyValues@@YAXPEAUHKEY__@@@Z; Intl_DeleteRegKeyValues(HKEY__ *)
0x1800266ff  mov     rcx, [rbp+hKey]; hKey
0x180026703  call    ?Intl_DeleteRegSubKeys@@YAXPEAUHKEY__@@@Z; Intl_DeleteRegSubKeys(HKEY__ *)
0x180026708  mov     rdx, [rbp+hKey]; HKEY
0x18002670c  mov     rcx, [rbp+var_10]; HKEY
0x180026710  call    ?Intl_CreateRegTree@@YAKPEAUHKEY__@@0@Z; Intl_CreateRegTree(HKEY__ *,HKEY__ *)
0x180026715  mov     rcx, [rbp+hKey]; hKey
0x180026719  call    cs:__imp_RegCloseKey
0x18002671f  mov     rcx, [rbp+var_10]; hKey
0x180026723  call    cs:__imp_RegCloseKey
0x180026729  mov     rbx, [rsp+60h+arg_0]
0x18002672e  add     rsp, 60h
0x180026732  pop     rbp
0x180026733  retn
```
