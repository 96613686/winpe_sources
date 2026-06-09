# CW32System::GetSurrogateFontName(ushort *,ulong)

- ea: `0x18000a260`
- end: `0x18000a315`
- name: `?GetSurrogateFontName@CW32System@@CA_NPEAGK@Z`
- size: `181`
- prototype: `bool __fastcall(LPBYTE lpData, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009848`

## callees

- `0x18000a260`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a29c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a29c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a2f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a2f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a2db`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a2db`

## pseudocode

```c
bool __fastcall CW32System::GetSurrogateFontName(LPBYTE lpData, DWORD a2)
{
  bool v3; // bl
  DWORD Type; // [rsp+48h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  Type = a2;
  hKey = 0;
  v3 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\LanguagePack\\SurrogateFallback",
          0,
          1u,
          &hKey) )
  {
    Type = 0;
    cbData = 64;
    if ( !RegQueryValueExW(hKey, L"Plane2", 0, &Type, lpData, &cbData) )
      v3 = Type == 1;
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x18000a260  mov     rax, rsp
0x18000a263  mov     [rax+8], rbx
0x18000a267  mov     [rax+10h], edx
0x18000a26a  push    rdi
0x18000a26b  sub     rsp, 30h
0x18000a26f  mov     qword ptr [rax+20h], 0
0x18000a277  lea     rax, [rax+20h]
0x18000a27b  mov     rdi, rcx
0x18000a27e  mov     [rsp+38h+phkResult], rax; phkResult
0x18000a283  mov     r9d, 1; samDesired
0x18000a289  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000a290  xor     r8d, r8d; ulOptions
0x18000a293  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a29a  xor     bl, bl
0x18000a29c  call    cs:__imp_RegOpenKeyExW
0x18000a2a3  nop     dword ptr [rax+rax+00h]
0x18000a2a8  test    eax, eax
0x18000a2aa  jnz     short loc_18000A2FC
0x18000a2ac  mov     rcx, [rsp+38h+hKey]; hKey
0x18000a2b1  lea     r9, [rsp+38h+Type]; lpType
0x18000a2b6  mov     [rsp+38h+Type], eax
0x18000a2ba  lea     rdx, ValueName; "Plane2"
0x18000a2c1  lea     rax, [rsp+38h+cbData]
0x18000a2c6  mov     [rsp+38h+cbData], 40h ; '@'
0x18000a2ce  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000a2d3  xor     r8d, r8d; lpReserved
0x18000a2d6  mov     [rsp+38h+phkResult], rdi; lpData
0x18000a2db  call    cs:__imp_RegQueryValueExW
0x18000a2e2  nop     dword ptr [rax+rax+00h]
0x18000a2e7  test    eax, eax
0x18000a2e9  jz      short loc_18000A30A
0x18000a2eb  mov     rcx, [rsp+38h+hKey]; hKey
0x18000a2f0  call    cs:__imp_RegCloseKey
0x18000a2f7  nop     dword ptr [rax+rax+00h]
0x18000a2fc  mov     al, bl
0x18000a2fe  mov     rbx, [rsp+38h+arg_0]
0x18000a303  add     rsp, 30h
0x18000a307  pop     rdi
0x18000a308  retn
0x18000a30a  cmp     [rsp+38h+Type], 1
0x18000a30f  jnz     short loc_18000A2EB
0x18000a311  mov     bl, 1
0x18000a313  jmp     short loc_18000A2EB
```
