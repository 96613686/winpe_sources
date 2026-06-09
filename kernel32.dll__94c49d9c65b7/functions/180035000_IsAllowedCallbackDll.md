# IsAllowedCallbackDll

- ea: `0x180035000`
- end: `0x180035152`
- name: `IsAllowedCallbackDll`
- size: `338`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180034360`

## callees

- `0x180035000`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003502a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003504c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003506e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180035090`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800350b2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800350d4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800350f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180035110`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003512e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003502a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003504c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003506e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180035090`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800350b2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800350d4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800350f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180035110`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003512e`

## string_xrefs

- `0x180035040`: `setbcdlocale.dll`
- `0x1800350a6`: `MUILanguageCleanup.dll`
- `0x180035084`: `tsf3gip.dll`
- `0x180035062`: `muifontsetup.dll`
- `0x180035012`: `LanguageOverlayUtil.dll`
- `0x1800350c8`: `NetSetupApi.dll`
- `0x1800350e6`: `TimeDateMUICallback.dll`
- `0x180035122`: `samlib.dll`
- `0x180035104`: `UserLanguageProfileCallback.dll`

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
0x180035000  mov     [rsp+arg_0], rbx
0x180035005  mov     [rsp+arg_8], rsi
0x18003500a  push    rdi
0x18003500b  sub     rsp, 30h
0x18003500f  or      edi, 0FFFFFFFFh
0x180035012  lea     r8, aLanguageoverla; "LanguageOverlayUtil.dll"
0x180035019  mov     esi, 1
0x18003501e  mov     r9d, edi; cchCount2
0x180035021  mov     edx, edi; cchCount1
0x180035023  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x180035027  mov     rbx, rcx
0x18003502a  call    cs:__imp_CompareStringOrdinal
0x180035030  cmp     eax, 2
0x180035033  jz      loc_18003514E
0x180035039  mov     r9d, edi; cchCount2
0x18003503c  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x180035040  lea     r8, aSetbcdlocaleDl; "setbcdlocale.dll"
0x180035047  mov     edx, edi; cchCount1
0x180035049  mov     rcx, rbx; lpString1
0x18003504c  call    cs:__imp_CompareStringOrdinal
0x180035052  cmp     eax, 2
0x180035055  jz      loc_18003514E
0x18003505b  mov     r9d, edi; cchCount2
0x18003505e  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x180035062  lea     r8, aMuifontsetupDl; "muifontsetup.dll"
0x180035069  mov     edx, edi; cchCount1
0x18003506b  mov     rcx, rbx; lpString1
0x18003506e  call    cs:__imp_CompareStringOrdinal
0x180035074  cmp     eax, 2
0x180035077  jz      loc_18003514E
0x18003507d  mov     r9d, edi; cchCount2
0x180035080  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x180035084  lea     r8, aTsf3gipDll; "tsf3gip.dll"
0x18003508b  mov     edx, edi; cchCount1
0x18003508d  mov     rcx, rbx; lpString1
0x180035090  call    cs:__imp_CompareStringOrdinal
0x180035096  cmp     eax, 2
0x180035099  jz      loc_18003514E
0x18003509f  mov     r9d, edi; cchCount2
0x1800350a2  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x1800350a6  lea     r8, aMuilanguagecle; "MUILanguageCleanup.dll"
0x1800350ad  mov     edx, edi; cchCount1
0x1800350af  mov     rcx, rbx; lpString1
0x1800350b2  call    cs:__imp_CompareStringOrdinal
0x1800350b8  cmp     eax, 2
0x1800350bb  jz      loc_18003514E
0x1800350c1  mov     r9d, edi; cchCount2
0x1800350c4  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x1800350c8  lea     r8, aNetsetupapiDll; "NetSetupApi.dll"
0x1800350cf  mov     edx, edi; cchCount1
0x1800350d1  mov     rcx, rbx; lpString1
0x1800350d4  call    cs:__imp_CompareStringOrdinal
0x1800350da  cmp     eax, 2
0x1800350dd  jz      short loc_18003514E
0x1800350df  mov     r9d, edi; cchCount2
0x1800350e2  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x1800350e6  lea     r8, aTimedatemuical; "TimeDateMUICallback.dll"
0x1800350ed  mov     edx, edi; cchCount1
0x1800350ef  mov     rcx, rbx; lpString1
0x1800350f2  call    cs:__imp_CompareStringOrdinal
0x1800350f8  cmp     eax, 2
0x1800350fb  jz      short loc_18003514E
0x1800350fd  mov     r9d, edi; cchCount2
0x180035100  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x180035104  lea     r8, aUserlanguagepr; "UserLanguageProfileCallback.dll"
0x18003510b  mov     edx, edi; cchCount1
0x18003510d  mov     rcx, rbx; lpString1
0x180035110  call    cs:__imp_CompareStringOrdinal
0x180035116  cmp     eax, 2
0x180035119  jz      short loc_18003514E
0x18003511b  mov     r9d, edi; cchCount2
0x18003511e  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x180035122  lea     r8, aSamlibDll; "samlib.dll"
0x180035129  mov     edx, edi; cchCount1
0x18003512b  mov     rcx, rbx; lpString1
0x18003512e  call    cs:__imp_CompareStringOrdinal
0x180035134  xor     ecx, ecx
0x180035136  cmp     eax, 2
0x180035139  setz    cl
0x18003513c  mov     eax, ecx
0x18003513e  mov     rbx, [rsp+38h+arg_0]
0x180035143  mov     rsi, [rsp+38h+arg_8]
0x180035148  add     rsp, 30h
0x18003514c  pop     rdi
0x18003514d  retn
0x18003514e  mov     eax, esi
0x180035150  jmp     short loc_18003513E
```
