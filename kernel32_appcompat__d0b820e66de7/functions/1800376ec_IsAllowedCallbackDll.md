# IsAllowedCallbackDll

- ea: `0x1800376ec`
- end: `0x180037879`
- name: `IsAllowedCallbackDll`
- size: `397`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180036944`

## callees

- `0x1800376ec`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180037716`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003773e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180037766`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003778e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800377b6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800377de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180037806`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003782a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003784e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180037716`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003773e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180037766`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003778e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800377b6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800377de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180037806`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003782a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003784e`

## string_xrefs

- `0x180037732`: `setbcdlocale.dll`
- `0x1800377aa`: `MUILanguageCleanup.dll`
- `0x180037782`: `tsf3gip.dll`
- `0x18003775a`: `muifontsetup.dll`
- `0x1800376fe`: `LanguageOverlayUtil.dll`
- `0x1800377d2`: `NetSetupApi.dll`
- `0x1800377fa`: `TimeDateMUICallback.dll`
- `0x180037842`: `samlib.dll`
- `0x18003781e`: `UserLanguageProfileCallback.dll`

## pseudocode

```c
_BOOL8 __fastcall IsAllowedCallbackDll(LPCWCH lpString1)
{
  return CompareStringOrdinal(lpString1, -1, L"LanguageOverlayUtil.dll", -1, 1) == 2
      || CompareStringOrdinal(lpString1, -1, L"setbcdlocale.dll", -1, 1) == 2
      || CompareStringOrdinal(lpString1, -1, L"muifontsetup.dll", -1, 1) == 2
      || CompareStringOrdinal(lpString1, -1, L"tsf3gip.dll", -1, 1) == 2
      || CompareStringOrdinal(lpString1, -1, L"MUILanguageCleanup.dll", -1, 1) == 2
      || CompareStringOrdinal(lpString1, -1, L"NetSetupApi.dll", -1, 1) == 2
      || CompareStringOrdinal(lpString1, -1, L"TimeDateMUICallback.dll", -1, 1) == 2
      || CompareStringOrdinal(lpString1, -1, L"UserLanguageProfileCallback.dll", -1, 1) == 2
      || CompareStringOrdinal(lpString1, -1, L"samlib.dll", -1, 1) == 2;
}

```

## disassembly

```asm
0x1800376ec  mov     [rsp+arg_0], rbx
0x1800376f1  mov     [rsp+arg_8], rsi
0x1800376f6  push    rdi
0x1800376f7  sub     rsp, 30h
0x1800376fb  or      edi, 0FFFFFFFFh
0x1800376fe  lea     r8, aLanguageoverla; "LanguageOverlayUtil.dll"
0x180037705  mov     esi, 1
0x18003770a  mov     r9d, edi; cchCount2
0x18003770d  mov     edx, edi; cchCount1
0x18003770f  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x180037713  mov     rbx, rcx
0x180037716  call    cs:__imp_CompareStringOrdinal
0x18003771d  nop     dword ptr [rax+rax+00h]
0x180037722  cmp     eax, 2
0x180037725  jz      loc_180037875
0x18003772b  mov     r9d, edi; cchCount2
0x18003772e  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x180037732  lea     r8, aSetbcdlocaleDl; "setbcdlocale.dll"
0x180037739  mov     edx, edi; cchCount1
0x18003773b  mov     rcx, rbx; lpString1
0x18003773e  call    cs:__imp_CompareStringOrdinal
0x180037745  nop     dword ptr [rax+rax+00h]
0x18003774a  cmp     eax, 2
0x18003774d  jz      loc_180037875
0x180037753  mov     r9d, edi; cchCount2
0x180037756  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x18003775a  lea     r8, aMuifontsetupDl; "muifontsetup.dll"
0x180037761  mov     edx, edi; cchCount1
0x180037763  mov     rcx, rbx; lpString1
0x180037766  call    cs:__imp_CompareStringOrdinal
0x18003776d  nop     dword ptr [rax+rax+00h]
0x180037772  cmp     eax, 2
0x180037775  jz      loc_180037875
0x18003777b  mov     r9d, edi; cchCount2
0x18003777e  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x180037782  lea     r8, aTsf3gipDll; "tsf3gip.dll"
0x180037789  mov     edx, edi; cchCount1
0x18003778b  mov     rcx, rbx; lpString1
0x18003778e  call    cs:__imp_CompareStringOrdinal
0x180037795  nop     dword ptr [rax+rax+00h]
0x18003779a  cmp     eax, 2
0x18003779d  jz      loc_180037875
0x1800377a3  mov     r9d, edi; cchCount2
0x1800377a6  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x1800377aa  lea     r8, aMuilanguagecle; "MUILanguageCleanup.dll"
0x1800377b1  mov     edx, edi; cchCount1
0x1800377b3  mov     rcx, rbx; lpString1
0x1800377b6  call    cs:__imp_CompareStringOrdinal
0x1800377bd  nop     dword ptr [rax+rax+00h]
0x1800377c2  cmp     eax, 2
0x1800377c5  jz      loc_180037875
0x1800377cb  mov     r9d, edi; cchCount2
0x1800377ce  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x1800377d2  lea     r8, aNetsetupapiDll; "NetSetupApi.dll"
0x1800377d9  mov     edx, edi; cchCount1
0x1800377db  mov     rcx, rbx; lpString1
0x1800377de  call    cs:__imp_CompareStringOrdinal
0x1800377e5  nop     dword ptr [rax+rax+00h]
0x1800377ea  cmp     eax, 2
0x1800377ed  jz      loc_180037875
0x1800377f3  mov     r9d, edi; cchCount2
0x1800377f6  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x1800377fa  lea     r8, aTimedatemuical; "TimeDateMUICallback.dll"
0x180037801  mov     edx, edi; cchCount1
0x180037803  mov     rcx, rbx; lpString1
0x180037806  call    cs:__imp_CompareStringOrdinal
0x18003780d  nop     dword ptr [rax+rax+00h]
0x180037812  cmp     eax, 2
0x180037815  jz      short loc_180037875
0x180037817  mov     r9d, edi; cchCount2
0x18003781a  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x18003781e  lea     r8, aUserlanguagepr; "UserLanguageProfileCallback.dll"
0x180037825  mov     edx, edi; cchCount1
0x180037827  mov     rcx, rbx; lpString1
0x18003782a  call    cs:__imp_CompareStringOrdinal
0x180037831  nop     dword ptr [rax+rax+00h]
0x180037836  cmp     eax, 2
0x180037839  jz      short loc_180037875
0x18003783b  mov     r9d, edi; cchCount2
0x18003783e  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x180037842  lea     r8, aSamlibDll; "samlib.dll"
0x180037849  mov     edx, edi; cchCount1
0x18003784b  mov     rcx, rbx; lpString1
0x18003784e  call    cs:__imp_CompareStringOrdinal
0x180037855  nop     dword ptr [rax+rax+00h]
0x18003785a  xor     ecx, ecx
0x18003785c  cmp     eax, 2
0x18003785f  setz    cl
0x180037862  mov     eax, ecx
0x180037864  mov     rbx, [rsp+38h+arg_0]
0x180037869  mov     rsi, [rsp+38h+arg_8]
0x18003786e  add     rsp, 30h
0x180037872  pop     rdi
0x180037873  retn
0x180037875  mov     eax, esi
0x180037877  jmp     short loc_180037864
```
