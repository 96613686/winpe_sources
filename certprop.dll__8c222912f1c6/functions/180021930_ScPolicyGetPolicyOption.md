# ScPolicyGetPolicyOption

- ea: `0x180021930`
- end: `0x180021a02`
- name: `ScPolicyGetPolicyOption`
- size: `210`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b5c0`
- `0x18001b9b0`

## callees

- `0x180021930`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800219ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800219ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180021974`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180021974`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800219a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800219a6`

## string_xrefs

- `0x18002198f`: `ScRemoveOption`

## pseudocode

```c
__int64 __fastcall ScPolicyGetPolicyOption(_DWORD *a1)
{
  unsigned int v2; // ebx
  LSTATUS v3; // eax
  BYTE Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  cbData = 2;
  *a1 = 0;
  v2 = RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
         0,
         0x20019u,
         &hKey);
  if ( !v2 )
  {
    v3 = RegQueryValueExA(hKey, "ScRemoveOption", 0, 0, &Data, &cbData);
    v2 = v3;
    if ( v3 )
    {
      if ( v3 == 2 )
        v2 = 0;
    }
    else
    {
      switch ( Data )
      {
        case '1':
          *a1 = 1;
          break;
        case '2':
          *a1 = 2;
          break;
        case '3':
          *a1 = 3;
          break;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180021930  mov     rax, rsp
0x180021933  mov     [rax+20h], rbx
0x180021937  push    rdi
0x180021938  sub     rsp, 30h
0x18002193c  mov     qword ptr [rax+18h], 0
0x180021944  mov     rdi, rcx
0x180021947  mov     dword ptr [rax+10h], 2
0x18002194e  lea     rax, [rax+18h]
0x180021952  mov     dword ptr [rcx], 0
0x180021958  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002195f  mov     r9d, 20019h; samDesired
0x180021965  mov     [rsp+38h+phkResult], rax; phkResult
0x18002196a  xor     r8d, r8d; ulOptions
0x18002196d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021974  call    cs:__imp_RegOpenKeyExA
0x18002197a  mov     ebx, eax
0x18002197c  test    eax, eax
0x18002197e  jnz     short loc_1800219E5
0x180021980  mov     rcx, [rsp+38h+hKey]; hKey
0x180021985  lea     rax, [rsp+38h+cbData]
0x18002198a  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002198f  lea     rdx, aScremoveoption; "ScRemoveOption"
0x180021996  lea     rax, [rsp+38h+Data]
0x18002199b  xor     r9d, r9d; lpType
0x18002199e  xor     r8d, r8d; lpReserved
0x1800219a1  mov     [rsp+38h+phkResult], rax; lpData
0x1800219a6  call    cs:__imp_RegQueryValueExA
0x1800219ac  mov     ebx, eax
0x1800219ae  test    eax, eax
0x1800219b0  jz      short loc_1800219BB
0x1800219b2  cmp     eax, 2
0x1800219b5  jnz     short loc_1800219E5
0x1800219b7  xor     ebx, ebx
0x1800219b9  jmp     short loc_1800219E5
0x1800219bb  movsx   ecx, [rsp+38h+Data]
0x1800219c0  sub     ecx, 31h ; '1'
0x1800219c3  jz      short loc_1800219DF
0x1800219c5  sub     ecx, 1
0x1800219c8  jz      short loc_1800219D7
0x1800219ca  cmp     ecx, 1
0x1800219cd  jnz     short loc_1800219E5
0x1800219cf  mov     dword ptr [rdi], 3
0x1800219d5  jmp     short loc_1800219E5
0x1800219d7  mov     dword ptr [rdi], 2
0x1800219dd  jmp     short loc_1800219E5
0x1800219df  mov     dword ptr [rdi], 1
0x1800219e5  mov     rcx, [rsp+38h+hKey]; hKey
0x1800219ea  test    rcx, rcx
0x1800219ed  jz      short loc_1800219F5
0x1800219ef  call    cs:__imp_RegCloseKey
0x1800219f5  mov     eax, ebx
0x1800219f7  mov     rbx, [rsp+38h+arg_18]
0x1800219fc  add     rsp, 30h
0x180021a00  pop     rdi
0x180021a01  retn
```
