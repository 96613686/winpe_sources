# CloudExperienceHostAPI::OobeRegionManagerStaticsCore::GetLocaleNameFromDisplayLanguage(HSTRING__ * *)

- ea: `0x18004b1e8`
- end: `0x18004b2c4`
- name: `?GetLocaleNameFromDisplayLanguage@OobeRegionManagerStaticsCore@CloudExperienceHostAPI@@CAJPEAPEAUHSTRING__@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(HSTRING *string)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004a8ac`

## callees

- `0x180002b60`
- `0x1800036e4`
- `0x1800076b4`
- `0x1800076d4`
- `0x18004b1e8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b275`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b275`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x18004b21c`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x18004b21c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18004b234`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18004b234`

## string_xrefs

- `0x18004b248`: `shellcommon\shell\oobe\core\components\winrt\ooberegioncore.cpp`
- `0x18004b289`: `shellcommon\shell\oobe\core\components\winrt\ooberegioncore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeRegionManagerStaticsCore::GetLocaleNameFromDisplayLanguage(
        HSTRING *string)
{
  LANGID ThreadUILanguage; // ax
  const char *v3; // r9
  __int64 v5; // rdx
  HRESULT v6; // eax
  unsigned int v7; // ebx
  WCHAR LCData[88]; // [rsp+20h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  memset_0(LCData, 0, 0xAAu);
  ThreadUILanguage = GetThreadUILanguage();
  if ( !GetLocaleInfoW(ThreadUILanguage, 0x5Cu, LCData, 85) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xCF,
             (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\ooberegioncore.cpp",
             v3);
  v5 = -1;
  do
    ++v5;
  while ( LCData[v5] );
  v6 = WindowsCreateString(LCData, v5, string);
  v7 = v6;
  if ( v6 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD0,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\ooberegioncore.cpp",
    (const char *)(unsigned int)v6,
    *(int *)LCData);
  return v7;
}

```

## disassembly

```asm
0x18004b1e8  mov     [rsp+arg_8], rbx
0x18004b1ed  push    rdi
0x18004b1ee  sub     rsp, 0E0h
0x18004b1f5  mov     rax, cs:__security_cookie
0x18004b1fc  xor     rax, rsp
0x18004b1ff  mov     [rsp+0E8h+var_18], rax
0x18004b207  mov     rbx, rcx
0x18004b20a  xor     edx, edx; Val
0x18004b20c  lea     rcx, [rsp+0E8h+LCData]; void *
0x18004b211  mov     r8d, 0AAh; Size
0x18004b217  call    memset_0
0x18004b21c  call    cs:__imp_GetThreadUILanguage
0x18004b222  mov     r9d, 55h ; 'U'; cchData
0x18004b228  movzx   ecx, ax; Locale
0x18004b22b  lea     r8, [rsp+0E8h+LCData]; lpLCData
0x18004b230  lea     edx, [r9+7]; LCType
0x18004b234  call    cs:__imp_GetLocaleInfoW
0x18004b23a  xor     edi, edi
0x18004b23c  test    eax, eax
0x18004b23e  jnz     short loc_18004B25B
0x18004b240  mov     rcx, [rsp+0E8h]; this
0x18004b248  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004b24f  mov     edx, 0CFh; void *
0x18004b254  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004b259  jmp     short loc_18004B2A3
0x18004b25b  lea     rax, [rsp+0E8h+LCData]
0x18004b260  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004b264  inc     rdx; length
0x18004b267  cmp     [rax+rdx*2], di
0x18004b26b  jnz     short loc_18004B264
0x18004b26d  mov     r8, rbx; string
0x18004b270  lea     rcx, [rsp+0E8h+LCData]; sourceString
0x18004b275  call    cs:__imp_WindowsCreateString
0x18004b27b  mov     ebx, eax
0x18004b27d  test    eax, eax
0x18004b27f  jns     short loc_18004B2A1
0x18004b281  mov     rcx, [rsp+0E8h]; this
0x18004b289  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004b290  mov     r9d, eax; char *
0x18004b293  mov     edx, 0D0h; void *
0x18004b298  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b29d  mov     eax, ebx
0x18004b29f  jmp     short loc_18004B2A3
0x18004b2a1  xor     eax, eax
0x18004b2a3  mov     rcx, [rsp+0E8h+var_18]
0x18004b2ab  xor     rcx, rsp; StackCookie
0x18004b2ae  call    __security_check_cookie
0x18004b2b3  mov     rbx, [rsp+0E8h+arg_8]
0x18004b2bb  add     rsp, 0E0h
0x18004b2c2  pop     rdi
0x18004b2c3  retn
```
