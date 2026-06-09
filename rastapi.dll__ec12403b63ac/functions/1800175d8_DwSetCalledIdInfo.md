# DwSetCalledIdInfo

- ea: `0x1800175d8`
- end: `0x180017738`
- name: `DwSetCalledIdInfo`
- size: `352`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180014ad0`

## callees

- `0x180016b30`
- `0x1800175d8`
- `0x18002927e`
- `0x1800292b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001765f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001765f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800176e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800176e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800176b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800176b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800176fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001770b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800176fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001770b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180017655`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180017655`

## pseudocode

```c
__int64 __fastcall DwSetCalledIdInfo(__int64 a1, __int64 a2)
{
  int v2; // esi
  DWORD LastError; // ebx
  unsigned __int8 *v5; // rcx
  HKEY v6; // rcx
  HKEY hKey; // [rsp+30h] [rbp-228h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-220h] BYREF
  WCHAR WideCharStr[256]; // [rsp+40h] [rbp-218h] BYREF

  v2 = *(_DWORD *)(a2 + 96);
  hKey = 0;
  phkResult = 0;
  memset_0(WideCharStr, 0, sizeof(WideCharStr));
  if ( !MultiByteToWideChar(0, 0, (LPCCH)(a2 + 133), -1, WideCharStr, 256) )
  {
    LastError = GetLastError();
    goto LABEL_12;
  }
  v5 = (unsigned __int8 *)WideCharStr;
  if ( (_WORD)v2 )
    v5 = (unsigned __int8 *)(a2 + 100);
  LastError = lrGetRegKeyFromGuid(v5, &hKey, 0, (unsigned __int16)v2 == 0);
  if ( !LastError )
  {
    v6 = hKey;
    if ( !(_WORD)v2 )
    {
      LastError = RegOpenKeyExW(hKey, L"Clients\\Ras", 0, 0xF003Fu, &phkResult);
      if ( LastError )
        goto LABEL_10;
      v6 = phkResult;
    }
    LastError = RegSetValueExW(
                  v6,
                  L"CalledIDInformation",
                  0,
                  7u,
                  (const BYTE *)(*(_QWORD *)(a2 + 40) + 4LL),
                  **(_DWORD **)(a2 + 40));
  }
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_12:
  if ( phkResult )
    RegCloseKey(phkResult);
  return LastError;
}

```

## disassembly

```asm
0x1800175d8  mov     [rsp+arg_0], rbx
0x1800175dd  mov     [rsp+arg_10], rbp
0x1800175e2  push    rsi
0x1800175e3  sub     rsp, 250h
0x1800175ea  mov     rax, cs:__security_cookie
0x1800175f1  xor     rax, rsp
0x1800175f4  mov     [rsp+258h+var_18], rax
0x1800175fc  mov     esi, [rdx+60h]
0x1800175ff  lea     rcx, [rsp+258h+WideCharStr]; void *
0x180017604  mov     rbp, rdx
0x180017607  mov     [rsp+258h+hKey], 0
0x180017610  and     esi, 0FFFFh
0x180017616  mov     [rsp+258h+phkResult], 0
0x18001761f  mov     ebx, 0
0x180017624  mov     r8d, 200h; Size
0x18001762a  setz    bl
0x18001762d  xor     edx, edx; Val
0x18001762f  call    memset_0
0x180017634  lea     rax, [rsp+258h+WideCharStr]
0x180017639  mov     [rsp+258h+cchWideChar], 100h; cchWideChar
0x180017641  lea     r8, [rbp+85h]; lpMultiByteStr
0x180017648  mov     [rsp+258h+lpWideCharStr], rax; lpWideCharStr
0x18001764d  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180017651  xor     edx, edx; dwFlags
0x180017653  xor     ecx, ecx; CodePage
0x180017655  call    cs:__imp_MultiByteToWideChar
0x18001765b  test    eax, eax
0x18001765d  jnz     short loc_18001766C
0x18001765f  call    cs:__imp_GetLastError
0x180017665  mov     ebx, eax
0x180017667  jmp     loc_180017701
0x18001766c  lea     rcx, [rsp+258h+WideCharStr]
0x180017671  test    esi, esi
0x180017673  jz      short loc_180017679
0x180017675  lea     rcx, [rbp+64h]; unsigned __int8 *
0x180017679  mov     r9d, ebx; int
0x18001767c  lea     rdx, [rsp+258h+hKey]; HKEY *
0x180017681  xor     r8d, r8d; unsigned int *
0x180017684  call    ?lrGetRegKeyFromGuid@@YAJPEAEPEAPEAUHKEY__@@PEAKH@Z; lrGetRegKeyFromGuid(uchar *,HKEY__ * *,ulong *,int)
0x180017689  mov     ebx, eax
0x18001768b  test    eax, eax
0x18001768d  jnz     short loc_1800176EE
0x18001768f  mov     rcx, [rsp+258h+hKey]; hKey
0x180017694  test    esi, esi
0x180017696  jnz     short loc_1800176C3
0x180017698  lea     rax, [rsp+258h+phkResult]
0x18001769d  mov     r9d, 0F003Fh; samDesired
0x1800176a3  xor     r8d, r8d; ulOptions
0x1800176a6  mov     [rsp+258h+lpWideCharStr], rax; phkResult
0x1800176ab  lea     rdx, aClientsRas; "Clients\\Ras"
0x1800176b2  call    cs:__imp_RegOpenKeyExW
0x1800176b8  mov     ebx, eax
0x1800176ba  test    eax, eax
0x1800176bc  jnz     short loc_1800176EE
0x1800176be  mov     rcx, [rsp+258h+phkResult]; hKey
0x1800176c3  mov     rax, [rbp+28h]
0x1800176c7  mov     r9d, 7; dwType
0x1800176cd  xor     r8d, r8d; Reserved
0x1800176d0  lea     rdx, [rax+4]
0x1800176d4  mov     eax, [rax]
0x1800176d6  mov     [rsp+258h+cchWideChar], eax; cbData
0x1800176da  mov     [rsp+258h+lpWideCharStr], rdx; lpData
0x1800176df  lea     rdx, aCalledidinform; "CalledIDInformation"
0x1800176e6  call    cs:__imp_RegSetValueExW
0x1800176ec  mov     ebx, eax
0x1800176ee  cmp     [rsp+258h+hKey], 0
0x1800176f4  jz      short loc_180017701
0x1800176f6  mov     rcx, [rsp+258h+hKey]; hKey
0x1800176fb  call    cs:__imp_RegCloseKey
0x180017701  mov     rcx, [rsp+258h+phkResult]; hKey
0x180017706  test    rcx, rcx
0x180017709  jz      short loc_180017711
0x18001770b  call    cs:__imp_RegCloseKey
0x180017711  mov     eax, ebx
0x180017713  mov     rcx, [rsp+258h+var_18]
0x18001771b  xor     rcx, rsp; StackCookie
0x18001771e  call    __security_check_cookie
0x180017723  lea     r11, [rsp+258h+var_8]
0x18001772b  mov     rbx, [r11+10h]
0x18001772f  mov     rbp, [r11+20h]
0x180017733  mov     rsp, r11
0x180017736  pop     rsi
0x180017737  retn
```
