# SetRegistryValue(ushort *,ulong)

- ea: `0x140035fb8`
- end: `0x140036069`
- name: `?SetRegistryValue@@YAJPEAGK@Z`
- size: `177`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ea24`
- `0x1400241a0`
- `0x140024b5c`
- `0x140025138`
- `0x140025a20`

## callees

- `0x140035fb8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140036019`
- `ADVAPI32!RegCloseKey` at `0x140036019`
- `ADVAPI32!RegOpenKeyExW` at `0x140035ff2`
- `ADVAPI32!RegOpenKeyExW` at `0x140035ff2`
- `ADVAPI32!RegSetValueExW` at `0x140036053`
- `ADVAPI32!RegSetValueExW` at `0x140036053`

## pseudocode

```c
__int64 __fastcall SetRegistryValue(LPCWSTR lpValueName, int a2)
{
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  int Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  Data = a2;
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Remote Assistance", 0, 2u, &hKey);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 <= 0 )
      goto LABEL_4;
    goto LABEL_3;
  }
  v4 = 0;
  v3 = RegSetValueExW(hKey, lpValueName, 0, 4u, (const BYTE *)&Data, 4u);
  if ( v3 )
  {
    if ( v3 > 0 )
    {
LABEL_3:
      v4 = (unsigned __int16)v3 | 0x80070000;
      goto LABEL_4;
    }
    v4 = v3;
  }
LABEL_4:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x140035fb8  mov     rax, rsp
0x140035fbb  mov     [rax+8], rbx
0x140035fbf  mov     [rax+10h], edx
0x140035fc2  push    rdi
0x140035fc3  sub     rsp, 30h
0x140035fc7  mov     qword ptr [rax+18h], 0
0x140035fcf  lea     rax, [rax+18h]
0x140035fd3  mov     rdi, rcx
0x140035fd6  mov     [rsp+38h+phkResult], rax; phkResult
0x140035fdb  mov     r9d, 2; samDesired
0x140035fe1  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Remote Assistance"
0x140035fe8  xor     r8d, r8d; ulOptions
0x140035feb  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140035ff2  call    cs:__imp_RegOpenKeyExW
0x140035ff9  nop     dword ptr [rax+rax+00h]
0x140035ffe  mov     ebx, eax
0x140036000  test    eax, eax
0x140036002  jz      short loc_140036033
0x140036004  jle     short loc_14003600F
0x140036006  movzx   ebx, ax
0x140036009  or      ebx, 80070000h
0x14003600f  mov     rcx, [rsp+38h+hKey]; hKey
0x140036014  test    rcx, rcx
0x140036017  jz      short loc_140036025
0x140036019  call    cs:__imp_RegCloseKey
0x140036020  nop     dword ptr [rax+rax+00h]
0x140036025  mov     eax, ebx
0x140036027  mov     rbx, [rsp+38h+arg_0]
0x14003602c  add     rsp, 30h
0x140036030  pop     rdi
0x140036031  retn
0x140036033  mov     rcx, [rsp+38h+hKey]; hKey
0x140036038  lea     rax, [rsp+38h+Data]
0x14003603d  xor     ebx, ebx
0x14003603f  xor     r8d, r8d; Reserved
0x140036042  mov     rdx, rdi; lpValueName
0x140036045  lea     r9d, [rbx+4]; dwType
0x140036049  mov     [rsp+38h+cbData], r9d; cbData
0x14003604e  mov     [rsp+38h+phkResult], rax; lpData
0x140036053  call    cs:__imp_RegSetValueExW
0x14003605a  nop     dword ptr [rax+rax+00h]
0x14003605f  test    eax, eax
0x140036061  jz      short loc_14003600F
0x140036063  jg      short loc_140036006
0x140036065  mov     ebx, eax
0x140036067  jmp     short loc_14003600F
```
