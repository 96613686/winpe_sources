# OobeRegionElevatedManager::GetLocaleNameFromDisplayLanguage(HSTRING__ * *)

- ea: `0x18005c4a8`
- end: `0x18005c572`
- name: `?GetLocaleNameFromDisplayLanguage@OobeRegionElevatedManager@@CAJPEAPEAUHSTRING__@@@Z`
- size: `202`
- prototype: `__int64 __fastcall(HSTRING *string)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005bdf0`

## callees

- `0x180003470`
- `0x180008524`
- `0x180008544`
- `0x18005c4a8`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x18005c4ca`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x18005c4ca`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18005c4e2`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18005c4e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005c523`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005c523`

## string_xrefs

- `0x18005c4f6`: `shell\oobe\machine\plugins\adapters\com\ooberegion.cpp`
- `0x18005c537`: `shell\oobe\machine\plugins\adapters\com\ooberegion.cpp`

## pseudocode

```c
__int64 __fastcall OobeRegionElevatedManager::GetLocaleNameFromDisplayLanguage(HSTRING *string)
{
  LANGID ThreadUILanguage; // ax
  const char *v3; // r9
  __int64 v5; // rdx
  HRESULT v6; // eax
  unsigned int v7; // ebx
  WCHAR LCData[88]; // [rsp+20h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  ThreadUILanguage = GetThreadUILanguage();
  if ( !GetLocaleInfoW(ThreadUILanguage, 0x5Cu, LCData, 85) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x86,
             (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\ooberegion.cpp",
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
    (void *)0x87,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\ooberegion.cpp",
    (const char *)(unsigned int)v6,
    *(int *)LCData);
  return v7;
}

```

## disassembly

```asm
0x18005c4a8  mov     [rsp+arg_8], rbx
0x18005c4ad  push    rdi
0x18005c4ae  sub     rsp, 0E0h
0x18005c4b5  mov     rax, cs:__security_cookie
0x18005c4bc  xor     rax, rsp
0x18005c4bf  mov     [rsp+0E8h+var_18], rax
0x18005c4c7  mov     rbx, rcx
0x18005c4ca  call    cs:__imp_GetThreadUILanguage
0x18005c4d0  mov     r9d, 55h ; 'U'; cchData
0x18005c4d6  movzx   ecx, ax; Locale
0x18005c4d9  lea     r8, [rsp+0E8h+LCData]; lpLCData
0x18005c4de  lea     edx, [r9+7]; LCType
0x18005c4e2  call    cs:__imp_GetLocaleInfoW
0x18005c4e8  xor     edi, edi
0x18005c4ea  test    eax, eax
0x18005c4ec  jnz     short loc_18005C509
0x18005c4ee  mov     rcx, [rsp+0E8h]; this
0x18005c4f6  lea     r8, aShellOobeMachi_45; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005c4fd  mov     edx, 86h; void *
0x18005c502  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c507  jmp     short loc_18005C551
0x18005c509  lea     rax, [rsp+0E8h+LCData]
0x18005c50e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005c512  inc     rdx; length
0x18005c515  cmp     [rax+rdx*2], di
0x18005c519  jnz     short loc_18005C512
0x18005c51b  mov     r8, rbx; string
0x18005c51e  lea     rcx, [rsp+0E8h+LCData]; sourceString
0x18005c523  call    cs:__imp_WindowsCreateString
0x18005c529  mov     ebx, eax
0x18005c52b  test    eax, eax
0x18005c52d  jns     short loc_18005C54F
0x18005c52f  mov     rcx, [rsp+0E8h]; this
0x18005c537  lea     r8, aShellOobeMachi_45; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005c53e  mov     r9d, eax; char *
0x18005c541  mov     edx, 87h; void *
0x18005c546  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c54b  mov     eax, ebx
0x18005c54d  jmp     short loc_18005C551
0x18005c54f  xor     eax, eax
0x18005c551  mov     rcx, [rsp+0E8h+var_18]
0x18005c559  xor     rcx, rsp; StackCookie
0x18005c55c  call    __security_check_cookie
0x18005c561  mov     rbx, [rsp+0E8h+arg_8]
0x18005c569  add     rsp, 0E0h
0x18005c570  pop     rdi
0x18005c571  retn
```
