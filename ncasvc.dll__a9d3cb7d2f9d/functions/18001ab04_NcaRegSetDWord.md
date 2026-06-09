# NcaRegSetDWord

- ea: `0x18001ab04`
- end: `0x18001abcb`
- name: `NcaRegSetDWord`
- size: `199`
- prototype: `__int64 __fastcall(HKEY hKey, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180014188`

## callees

- `0x1800033bc`
- `0x1800037b0`
- `0x180016e30`
- `0x1800199b4`
- `0x18001ab04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ab75`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ab75`

## string_xrefs

- `0x18001ab2b`: `DirectAccessPreferLocal`
- `0x18001ab8f`: `NcaRegSetDWord`
- `0x18001abaa`: `NcaRegSetDWord`
- `0x18001ab88`: `RegSetValueExW`

## pseudocode

```c
__int64 __fastcall NcaRegSetDWord(HKEY hKey, __int64 a2, __int64 a3, int a4)
{
  int v5; // ebx
  unsigned int v6; // eax
  int Data; // [rsp+58h] [rbp+20h] BYREF

  Data = a4;
  v5 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_149084e4aca63d179354f111bb13106e_Traceguids,
      0,
      (__int64)L"DirectAccessPreferLocal");
  v6 = RegSetValueExW(hKey, L"DirectAccessPreferLocal", 0, 4u, (const BYTE *)&Data, 4u);
  if ( v6 )
    v5 = NcaReportErrorAsWinError("NcaRegSetDWord", "RegSetValueExW", v6);
  NcaRegCloseKey(0);
  if ( v5 < 0 )
    return (unsigned int)NcaReportReturnError("NcaRegSetDWord", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001ab04  mov     r11, rsp
0x18001ab07  mov     [r11+8], rbx
0x18001ab0b  mov     [r11+10h], rsi
0x18001ab0f  mov     [r11+20h], r9d
0x18001ab13  push    rdi
0x18001ab14  sub     rsp, 30h
0x18001ab18  mov     rdi, rcx
0x18001ab1b  xor     ebx, ebx
0x18001ab1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab24  lea     rax, WPP_GLOBAL_Control
0x18001ab2b  lea     rsi, ValueName; "DirectAccessPreferLocal"
0x18001ab32  cmp     rcx, rax
0x18001ab35  jz      short loc_18001AB57
0x18001ab37  test    byte ptr [rcx+1Ch], 8
0x18001ab3b  jz      short loc_18001AB57
0x18001ab3d  mov     rcx, [rcx+10h]
0x18001ab41  lea     edx, [rbx+11h]
0x18001ab44  xor     r9d, r9d
0x18001ab47  mov     [r11-18h], rsi
0x18001ab4b  lea     r8, WPP_149084e4aca63d179354f111bb13106e_Traceguids
0x18001ab52  call    WPP_SF_SS
0x18001ab57  mov     r9d, 4; dwType
0x18001ab5d  lea     rax, [rsp+38h+Data]
0x18001ab62  mov     [rsp+38h+cbData], r9d; cbData
0x18001ab67  xor     r8d, r8d; Reserved
0x18001ab6a  mov     rdx, rsi; lpValueName
0x18001ab6d  mov     [rsp+38h+lpData], rax; lpData
0x18001ab72  mov     rcx, rdi; hKey
0x18001ab75  call    cs:__imp_RegSetValueExW
0x18001ab7c  nop     dword ptr [rax+rax+00h]
0x18001ab81  test    eax, eax
0x18001ab83  jz      short loc_18001AB9D
0x18001ab85  mov     r8d, eax
0x18001ab88  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x18001ab8f  lea     rcx, aNcaregsetdword; "NcaRegSetDWord"
0x18001ab96  call    NcaReportErrorAsWinError
0x18001ab9b  mov     ebx, eax
0x18001ab9d  xor     ecx, ecx
0x18001ab9f  call    NcaRegCloseKey
0x18001aba4  test    ebx, ebx
0x18001aba6  jns     short loc_18001ABB8
0x18001aba8  mov     edx, ebx
0x18001abaa  lea     rcx, aNcaregsetdword; "NcaRegSetDWord"
0x18001abb1  call    NcaReportReturnError
0x18001abb6  mov     ebx, eax
0x18001abb8  mov     rsi, [rsp+38h+arg_8]
0x18001abbd  mov     eax, ebx
0x18001abbf  mov     rbx, [rsp+38h+arg_0]
0x18001abc4  add     rsp, 30h
0x18001abc8  pop     rdi
0x18001abc9  retn
```
