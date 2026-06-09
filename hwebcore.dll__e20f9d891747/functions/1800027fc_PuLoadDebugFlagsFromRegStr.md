# PuLoadDebugFlagsFromRegStr

- ea: `0x1800027fc`
- end: `0x18000289d`
- name: `PuLoadDebugFlagsFromRegStr`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180001948`

## callees

- `0x1800027fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180002878`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180002878`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000288e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000288e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180002838`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180002838`

## string_xrefs

- `0x180002828`: `System\CurrentControlSet\Services\W3SVC\Parameters\HWEBCORE`

## pseudocode

```c
__int64 __fastcall PuLoadDebugFlagsFromRegStr(__int64 a1, DWORD a2)
{
  unsigned int v2; // ebx
  __int64 Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  Type = a2;
  Data = a1;
  hKey = 0;
  v2 = 0;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\HWEBCORE",
          0,
          0x20019u,
          &hKey) )
  {
    LODWORD(Data) = 0;
    cbData = 4;
    Type = 0;
    if ( hKey && !RegQueryValueExA(hKey, "DebugFlags", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      v2 = Data;
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x1800027fc  mov     [rsp-10h+Type], edx
0x180002800  mov     [rsp-10h+Data], rcx
0x180002805  push    rbp
0x180002806  push    rbx
0x180002807  mov     rbp, rsp
0x18000280a  sub     rsp, 38h
0x18000280e  lea     rax, [rbp+hKey]
0x180002812  mov     [rbp+hKey], 0
0x18000281a  mov     r9d, 20019h; samDesired
0x180002820  mov     [rsp+38h+phkResult], rax; phkResult
0x180002825  xor     r8d, r8d; ulOptions
0x180002828  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\W3"...
0x18000282f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002836  xor     ebx, ebx
0x180002838  call    cs:__imp_RegOpenKeyExA
0x18000283e  test    eax, eax
0x180002840  jnz     short loc_180002894
0x180002842  mov     rcx, [rbp+hKey]; hKey
0x180002846  mov     dword ptr [rbp+Data], ebx
0x180002849  mov     [rbp+cbData], 4
0x180002850  mov     [rbp+Type], ebx
0x180002853  test    rcx, rcx
0x180002856  jz      short loc_18000288A
0x180002858  lea     rax, [rbp+cbData]
0x18000285c  xor     r8d, r8d; lpReserved
0x18000285f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180002864  lea     r9, [rbp+Type]; lpType
0x180002868  lea     rax, [rbp+Data]
0x18000286c  lea     rdx, ValueName; "DebugFlags"
0x180002873  mov     [rsp+38h+phkResult], rax; lpData
0x180002878  call    cs:__imp_RegQueryValueExA
0x18000287e  test    eax, eax
0x180002880  jnz     short loc_18000288A
0x180002882  cmp     [rbp+Type], 4
0x180002886  cmovz   ebx, dword ptr [rbp+Data]
0x18000288a  mov     rcx, [rbp+hKey]; hKey
0x18000288e  call    cs:__imp_RegCloseKey
0x180002894  mov     eax, ebx
0x180002896  add     rsp, 38h
0x18000289a  pop     rbx
0x18000289b  pop     rbp
0x18000289c  retn
```
