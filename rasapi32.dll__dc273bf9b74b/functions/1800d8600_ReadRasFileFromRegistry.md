# ReadRasFileFromRegistry

- ea: `0x1800d8600`
- end: `0x1800d8717`
- name: `ReadRasFileFromRegistry`
- size: `279`
- prototype: `__int64 __fastcall(int, int, int, int, LPCSTR lpSubKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800d8720`

## callees

- `0x18000b0f4`
- `0x1800d34e4`
- `0x1800d8600`
- `0x1800da068`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d866b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d866b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d86d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d86d5`
- `rtutils!TracePrintfExA` at `0x1800d8696`
- `rtutils!TracePrintfExA` at `0x1800d86b4`
- `rtutils!TracePrintfExA` at `0x1800d86f5`
- `rtutils!TracePrintfExA` at `0x1800d8696`
- `rtutils!TracePrintfExA` at `0x1800d86b4`
- `rtutils!TracePrintfExA` at `0x1800d86f5`

## string_xrefs

- `0x1800d868c`: `ReadRasFile: key registry %S does not exist`
- `0x1800d86e9`: `ReadEntryListFromRegistry returned %d`
- `0x1800d86a8`: `Couldn't open the registry key`

## pseudocode

```c
__int64 __fastcall ReadRasFileFromRegistry(const WCHAR *a1, const WCHAR *a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax
  unsigned int v7; // eax
  unsigned int EntryListFromRegistry; // ebx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h]

  phkResult = 0;
  hKey = 0;
  result = RegistryPathConverter(a1);
  if ( !(_DWORD)result )
  {
    v7 = RegOpenKeyExA(hKey, 0, 0, 0x20219u, &phkResult);
    EntryListFromRegistry = v7;
    if ( v7 )
    {
      if ( v7 == 2 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "ReadRasFile: key registry %S does not exist", 0);
        return 0;
      }
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Couldn't open the registry key", v7);
    }
    else
    {
      EntryListFromRegistry = ReadEntryListFromRegistry(a4, 0, a2, phkResult);
      RegCloseKey(phkResult);
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "ReadEntryListFromRegistry returned %d", EntryListFromRegistry);
      Free0(0);
    }
    return EntryListFromRegistry;
  }
  if ( (_DWORD)result == 235 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1800d8600  mov     rax, rsp
0x1800d8603  mov     [rax+8], rbx
0x1800d8607  mov     [rax+10h], rbp
0x1800d860b  push    rsi
0x1800d860c  sub     rsp, 40h
0x1800d8610  mov     rsi, r9
0x1800d8613  mov     qword ptr [rax-18h], 0
0x1800d861b  mov     rbp, rdx
0x1800d861e  mov     qword ptr [rax-10h], 0
0x1800d8626  mov     rdx, rsi
0x1800d8629  mov     qword ptr [rax+28h], 0
0x1800d8631  lea     r9, [rax+28h]
0x1800d8635  lea     r8, [rax-10h]
0x1800d8639  call    RegistryPathConverter
0x1800d863e  test    eax, eax
0x1800d8640  jz      short loc_1800D864E
0x1800d8642  cmp     eax, 0EBh
0x1800d8647  jz      short loc_1800D869C
0x1800d8649  jmp     loc_1800D8707
0x1800d864e  mov     rdx, [rsp+48h+lpSubKey]; lpSubKey
0x1800d8653  lea     rax, [rsp+48h+var_18]
0x1800d8658  mov     rcx, [rsp+48h+hKey]; hKey
0x1800d865d  mov     r9d, 20219h; samDesired
0x1800d8663  xor     r8d, r8d; ulOptions
0x1800d8666  mov     [rsp+48h+phkResult], rax; phkResult
0x1800d866b  call    cs:__imp_RegOpenKeyExA
0x1800d8671  mov     ebx, eax
0x1800d8673  test    eax, eax
0x1800d8675  jz      short loc_1800D86BC
0x1800d8677  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d867d  cmp     eax, 2
0x1800d8680  jnz     short loc_1800D86A0
0x1800d8682  cmp     ecx, 0FFFFFFFFh
0x1800d8685  jz      short loc_1800D869C
0x1800d8687  mov     r9, [rsp+48h+lpSubKey]
0x1800d868c  lea     r8, aReadrasfileKey; "ReadRasFile: key registry %S does not e"...
0x1800d8693  lea     edx, [rax+0Ah]; dwFlags
0x1800d8696  call    cs:__imp_TracePrintfExA
0x1800d869c  xor     eax, eax
0x1800d869e  jmp     short loc_1800D8707
0x1800d86a0  cmp     ecx, 0FFFFFFFFh
0x1800d86a3  jz      short loc_1800D8705
0x1800d86a5  mov     r9d, ebx
0x1800d86a8  lea     r8, aCouldnTOpenThe; "Couldn't open the registry key"
0x1800d86af  mov     edx, 0Ch; dwFlags
0x1800d86b4  call    cs:__imp_TracePrintfExA
0x1800d86ba  jmp     short loc_1800D8705
0x1800d86bc  mov     r9, [rsp+48h+var_18]
0x1800d86c1  mov     r8, rbp
0x1800d86c4  xor     edx, edx
0x1800d86c6  mov     rcx, rsi
0x1800d86c9  call    ReadEntryListFromRegistry
0x1800d86ce  mov     rcx, [rsp+48h+var_18]; hKey
0x1800d86d3  mov     ebx, eax
0x1800d86d5  call    cs:__imp_RegCloseKey
0x1800d86db  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d86e1  cmp     ecx, 0FFFFFFFFh
0x1800d86e4  jz      short loc_1800D86FB
0x1800d86e6  mov     r9d, ebx
0x1800d86e9  lea     r8, aReadentrylistf; "ReadEntryListFromRegistry returned %d"
0x1800d86f0  mov     edx, 0Ch; dwFlags
0x1800d86f5  call    cs:__imp_TracePrintfExA
0x1800d86fb  mov     rcx, [rsp+48h+lpSubKey]
0x1800d8700  call    Free0
0x1800d8705  mov     eax, ebx
0x1800d8707  mov     rbx, [rsp+48h+arg_0]
0x1800d870c  mov     rbp, [rsp+48h+arg_8]
0x1800d8711  add     rsp, 40h
0x1800d8715  pop     rsi
0x1800d8716  retn
```
