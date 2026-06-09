# ScPolicyGetPolicyOption

- ea: `0x180007014`
- end: `0x1800070e6`
- name: `ScPolicyGetPolicyOption`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001ee0`

## callees

- `0x180007014`

## import_xrefs

- `KERNEL32!RegCloseKey` at `0x1800070d3`
- `KERNEL32!RegCloseKey` at `0x1800070d3`
- `KERNEL32!RegOpenKeyExA` at `0x180007058`
- `KERNEL32!RegOpenKeyExA` at `0x180007058`
- `KERNEL32!RegQueryValueExA` at `0x18000708a`
- `KERNEL32!RegQueryValueExA` at `0x18000708a`

## string_xrefs

- `0x180007073`: `ScRemoveOption`

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
0x180007014  mov     rax, rsp
0x180007017  mov     [rax+20h], rbx
0x18000701b  push    rdi
0x18000701c  sub     rsp, 30h
0x180007020  mov     qword ptr [rax+18h], 0
0x180007028  mov     rdi, rcx
0x18000702b  mov     dword ptr [rax+10h], 2
0x180007032  lea     rax, [rax+18h]
0x180007036  mov     dword ptr [rcx], 0
0x18000703c  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x180007043  mov     r9d, 20019h; samDesired
0x180007049  mov     [rsp+38h+phkResult], rax; phkResult
0x18000704e  xor     r8d, r8d; ulOptions
0x180007051  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007058  call    cs:__imp_RegOpenKeyExA
0x18000705e  mov     ebx, eax
0x180007060  test    eax, eax
0x180007062  jnz     short loc_1800070C9
0x180007064  mov     rcx, [rsp+38h+hKey]; hKey
0x180007069  lea     rax, [rsp+38h+cbData]
0x18000706e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180007073  lea     rdx, ValueName; "ScRemoveOption"
0x18000707a  lea     rax, [rsp+38h+Data]
0x18000707f  xor     r9d, r9d; lpType
0x180007082  xor     r8d, r8d; lpReserved
0x180007085  mov     [rsp+38h+phkResult], rax; lpData
0x18000708a  call    cs:__imp_RegQueryValueExA
0x180007090  mov     ebx, eax
0x180007092  test    eax, eax
0x180007094  jz      short loc_18000709F
0x180007096  cmp     eax, 2
0x180007099  jnz     short loc_1800070C9
0x18000709b  xor     ebx, ebx
0x18000709d  jmp     short loc_1800070C9
0x18000709f  movsx   ecx, [rsp+38h+Data]
0x1800070a4  sub     ecx, 31h ; '1'
0x1800070a7  jz      short loc_1800070C3
0x1800070a9  sub     ecx, 1
0x1800070ac  jz      short loc_1800070BB
0x1800070ae  cmp     ecx, 1
0x1800070b1  jnz     short loc_1800070C9
0x1800070b3  mov     dword ptr [rdi], 3
0x1800070b9  jmp     short loc_1800070C9
0x1800070bb  mov     dword ptr [rdi], 2
0x1800070c1  jmp     short loc_1800070C9
0x1800070c3  mov     dword ptr [rdi], 1
0x1800070c9  mov     rcx, [rsp+38h+hKey]; hKey
0x1800070ce  test    rcx, rcx
0x1800070d1  jz      short loc_1800070D9
0x1800070d3  call    cs:__imp_RegCloseKey
0x1800070d9  mov     eax, ebx
0x1800070db  mov     rbx, [rsp+38h+arg_18]
0x1800070e0  add     rsp, 30h
0x1800070e4  pop     rdi
0x1800070e5  retn
```
