# RegUtils::SetRegDword(ushort const *,ushort const *,ulong)

- ea: `0x18000c440`
- end: `0x18000c4a0`
- name: `?SetRegDword@RegUtils@@SAJPEBG0K@Z`
- size: `96`
- prototype: `int __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a6a4`

## callees

- `0x18000c440`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c491`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c491`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000c46e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000c46e`

## pseudocode

```c
int __fastcall RegUtils::SetRegDword(LPCWSTR lpSubKey, const unsigned __int16 *a2, int a3)
{
  int v3; // eax
  int v5; // [rsp+50h] [rbp+18h] BYREF

  v5 = a3;
  v3 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, lpSubKey, L"CurrentOperation", 4u, &v5, 4u);
  if ( !v3 )
    return 0;
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  return ZTraceReportOriginationNoThis(v3, "RegUtils::SetRegDword", 286);
}

```

## disassembly

```asm
0x18000c440  mov     r11, rsp
0x18000c443  mov     [r11+18h], r8d
0x18000c447  sub     rsp, 38h
0x18000c44b  mov     r9d, 4; dwType
0x18000c451  lea     rax, [r11+18h]
0x18000c455  mov     rdx, rcx; lpSubKey
0x18000c458  mov     [r11-10h], r9d
0x18000c45c  lea     r8, ValueName; "CurrentOperation"
0x18000c463  mov     [r11-18h], rax
0x18000c467  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c46e  call    cs:__imp_RegSetKeyValueW
0x18000c474  test    eax, eax
0x18000c476  jz      short loc_18000C499
0x18000c478  jle     short loc_18000C482
0x18000c47a  movzx   eax, ax
0x18000c47d  or      eax, 80070000h
0x18000c482  mov     r8d, 11Eh
0x18000c488  lea     rdx, aRegutilsSetreg; "RegUtils::SetRegDword"
0x18000c48f  mov     ecx, eax
0x18000c491  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000c497  jmp     short loc_18000C49B
0x18000c499  xor     eax, eax
0x18000c49b  add     rsp, 38h
0x18000c49f  retn
```
