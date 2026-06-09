# TelemetryProvider::WriteStatus(long)

- ea: `0x1800c07ec`
- end: `0x1800c093c`
- name: `?WriteStatus@TelemetryProvider@@AEAAXJ@Z`
- size: `336`
- prototype: `void __fastcall(TelemetryProvider *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180022e5c`

## callees

- `0x1800152d0`
- `0x1800c07ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c0844`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c089b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c0902`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c0844`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c089b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c0902`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c080e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c080e`

## string_xrefs

- `0x1800c0852`: `RegSetValueExW failed: %ls [%#x]`
- `0x1800c08a9`: `RegSetValueExW failed: %ls [%#x]`
- `0x1800c0910`: `RegSetValueExW failed: %ls [%#x]`
- `0x1800c085c`: `TelemetryProvider::WriteStatus`
- `0x1800c08b3`: `TelemetryProvider::WriteStatus`
- `0x1800c091a`: `TelemetryProvider::WriteStatus`

## pseudocode

```c
void __fastcall TelemetryProvider::WriteStatus(const wchar_t **this, int a2)
{
  HKEY v3; // rcx
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  struct _FILETIME Data; // [rsp+40h] [rbp+8h] BYREF
  int lpData; // [rsp+48h] [rbp+10h] BYREF
  struct _FILETIME v9; // [rsp+50h] [rbp+18h] BYREF

  lpData = a2;
  v9 = 0;
  Data = 0;
  GetSystemTimeAsFileTime(&v9);
  v3 = (HKEY)this[5];
  Data = v9;
  v4 = RegSetValueExW(v3, L"LastRunTime", 0, 0xBu, (const BYTE *)&Data, 8u);
  if ( v4 )
    AslLogCallPrintf(1, "TelemetryProvider::WriteStatus", 437, "RegSetValueExW failed: %ls [%#x]", *this, v4);
  v5 = RegSetValueExW((HKEY)this[5], L"Result", 0, 4u, (const BYTE *)&lpData, 4u);
  if ( v5 )
    AslLogCallPrintf(1, "TelemetryProvider::WriteStatus", 446, "RegSetValueExW failed: %ls [%#x]", *this, v5);
  if ( *((_BYTE *)this + 49) && !lpData )
  {
    v6 = RegSetValueExW((HKEY)this[5], L"LastFullSync", 0, 0xBu, (const BYTE *)&Data, 8u);
    if ( v6 )
      AslLogCallPrintf(1, "TelemetryProvider::WriteStatus", 457, "RegSetValueExW failed: %ls [%#x]", *this, v6);
  }
}

```

## disassembly

```asm
0x1800c07ec  mov     rax, rsp
0x1800c07ef  mov     [rax+10h], edx
0x1800c07f2  push    rbx
0x1800c07f3  sub     rsp, 30h
0x1800c07f7  mov     rbx, rcx
0x1800c07fa  mov     qword ptr [rax+18h], 0
0x1800c0802  lea     rcx, [rax+18h]; lpSystemTimeAsFileTime
0x1800c0806  mov     qword ptr [rax+8], 0
0x1800c080e  call    cs:__imp_GetSystemTimeAsFileTime
0x1800c0814  mov     rax, [rsp+38h+arg_10]
0x1800c0819  lea     rdx, aLastruntime; "LastRunTime"
0x1800c0820  mov     rcx, [rbx+28h]; hKey
0x1800c0824  mov     r9d, 0Bh; dwType
0x1800c082a  mov     [rsp+38h+Data], rax
0x1800c082f  xor     r8d, r8d; Reserved
0x1800c0832  lea     rax, [rsp+38h+Data]
0x1800c0837  mov     [rsp+38h+cbData], 8; cbData
0x1800c083f  mov     [rsp+38h+lpData], rax; lpData
0x1800c0844  call    cs:__imp_RegSetValueExW
0x1800c084a  test    eax, eax
0x1800c084c  jz      short loc_1800C0878
0x1800c084e  mov     [rsp+38h+cbData], eax
0x1800c0852  lea     r9, aRegsetvalueexw; "RegSetValueExW failed: %ls [%#x]"
0x1800c0859  mov     rax, [rbx]
0x1800c085c  lea     rdx, aTelemetryprovi_15; "TelemetryProvider::WriteStatus"
0x1800c0863  mov     r8d, 1B5h
0x1800c0869  mov     [rsp+38h+lpData], rax
0x1800c086e  mov     ecx, 1
0x1800c0873  call    AslLogCallPrintf
0x1800c0878  mov     rcx, [rbx+28h]; hKey
0x1800c087c  lea     rax, [rsp+38h+arg_8]
0x1800c0881  mov     r9d, 4; dwType
0x1800c0887  lea     rdx, aResult; "Result"
0x1800c088e  mov     [rsp+38h+cbData], r9d; cbData
0x1800c0893  xor     r8d, r8d; Reserved
0x1800c0896  mov     [rsp+38h+lpData], rax; lpData
0x1800c089b  call    cs:__imp_RegSetValueExW
0x1800c08a1  test    eax, eax
0x1800c08a3  jz      short loc_1800C08CF
0x1800c08a5  mov     [rsp+38h+cbData], eax
0x1800c08a9  lea     r9, aRegsetvalueexw; "RegSetValueExW failed: %ls [%#x]"
0x1800c08b0  mov     rax, [rbx]
0x1800c08b3  lea     rdx, aTelemetryprovi_15; "TelemetryProvider::WriteStatus"
0x1800c08ba  mov     r8d, 1BEh
0x1800c08c0  mov     [rsp+38h+lpData], rax
0x1800c08c5  mov     ecx, 1
0x1800c08ca  call    AslLogCallPrintf
0x1800c08cf  cmp     byte ptr [rbx+31h], 0
0x1800c08d3  jz      short loc_1800C0936
0x1800c08d5  cmp     [rsp+38h+arg_8], 0
0x1800c08da  jnz     short loc_1800C0936
0x1800c08dc  mov     rcx, [rbx+28h]; hKey
0x1800c08e0  lea     rax, [rsp+38h+Data]
0x1800c08e5  mov     [rsp+38h+cbData], 8; cbData
0x1800c08ed  lea     rdx, aLastfullsync_0; "LastFullSync"
0x1800c08f4  mov     r9d, 0Bh; dwType
0x1800c08fa  mov     [rsp+38h+lpData], rax; lpData
0x1800c08ff  xor     r8d, r8d; Reserved
0x1800c0902  call    cs:__imp_RegSetValueExW
0x1800c0908  test    eax, eax
0x1800c090a  jz      short loc_1800C0936
0x1800c090c  mov     [rsp+38h+cbData], eax
0x1800c0910  lea     r9, aRegsetvalueexw; "RegSetValueExW failed: %ls [%#x]"
0x1800c0917  mov     rax, [rbx]
0x1800c091a  lea     rdx, aTelemetryprovi_15; "TelemetryProvider::WriteStatus"
0x1800c0921  mov     r8d, 1C9h
0x1800c0927  mov     [rsp+38h+lpData], rax
0x1800c092c  mov     ecx, 1
0x1800c0931  call    AslLogCallPrintf
0x1800c0936  add     rsp, 30h
0x1800c093a  pop     rbx
0x1800c093b  retn
```
