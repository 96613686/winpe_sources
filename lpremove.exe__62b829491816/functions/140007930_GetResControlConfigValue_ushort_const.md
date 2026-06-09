# GetResControlConfigValue(ushort const *)

- ea: `0x140007930`
- end: `0x1400079d5`
- name: `?GetResControlConfigValue@@YAKPEBG@Z`
- size: `165`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000809c`

## callees

- `0x140007930`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400079c6`
- `ADVAPI32!RegCloseKey` at `0x1400079c6`
- `ADVAPI32!RegOpenKeyExW` at `0x14000796d`
- `ADVAPI32!RegOpenKeyExW` at `0x14000796d`
- `ADVAPI32!RegQueryValueExW` at `0x1400079a4`
- `ADVAPI32!RegQueryValueExW` at `0x1400079a4`

## string_xrefs

- `0x14000795f`: `System\CurrentControlSet\Control\CMF\Config`

## pseudocode

```c
__int64 __fastcall GetResControlConfigValue(const unsigned __int16 *a1)
{
  unsigned int v1; // ebx
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF
  int v4; // [rsp+54h] [rbp+1Ch]
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v4 = HIDWORD(a1);
  Data = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\CMF\\Config", 0, 0x20019u, &hKey)
    || (Type = 4, cbData = 4, !RegQueryValueExW(hKey, L"SYSTEM-LP", 0, &Type, (LPBYTE)&Data, &cbData)) && Type == 4 )
  {
    v1 = Data;
  }
  else
  {
    v1 = 0;
    Data = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x140007930  mov     qword ptr [rsp-10h+Data], rcx
0x140007935  push    rbp
0x140007936  push    rbx
0x140007937  mov     rbp, rsp
0x14000793a  sub     rsp, 38h
0x14000793e  lea     rax, [rbp+hKey]
0x140007942  mov     [rbp+Data], 0
0x140007949  mov     r9d, 20019h; samDesired
0x14000794f  mov     [rsp+38h+phkResult], rax; phkResult
0x140007954  xor     r8d, r8d; ulOptions
0x140007957  mov     [rbp+hKey], 0
0x14000795f  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\CMF"...
0x140007966  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000796d  call    cs:__imp_RegOpenKeyExW
0x140007973  test    eax, eax
0x140007975  jnz     short loc_1400079BA
0x140007977  mov     rcx, [rbp+hKey]; hKey
0x14000797b  lea     ebx, [rax+4]
0x14000797e  lea     rax, [rbp+cbData]
0x140007982  mov     [rbp+Type], ebx
0x140007985  mov     [rsp+38h+lpcbData], rax; lpcbData
0x14000798a  lea     r9, [rbp+Type]; lpType
0x14000798e  lea     rax, [rbp+Data]
0x140007992  mov     [rbp+cbData], ebx
0x140007995  xor     r8d, r8d; lpReserved
0x140007998  mov     [rsp+38h+phkResult], rax; lpData
0x14000799d  lea     rdx, ValueName; "SYSTEM-LP"
0x1400079a4  call    cs:__imp_RegQueryValueExW
0x1400079aa  test    eax, eax
0x1400079ac  jnz     short loc_1400079B3
0x1400079ae  cmp     [rbp+Type], ebx
0x1400079b1  jz      short loc_1400079BA
0x1400079b3  xor     ebx, ebx
0x1400079b5  mov     [rbp+Data], ebx
0x1400079b8  jmp     short loc_1400079BD
0x1400079ba  mov     ebx, [rbp+Data]
0x1400079bd  mov     rcx, [rbp+hKey]; hKey
0x1400079c1  test    rcx, rcx
0x1400079c4  jz      short loc_1400079CC
0x1400079c6  call    cs:__imp_RegCloseKey
0x1400079cc  mov     eax, ebx
0x1400079ce  add     rsp, 38h
0x1400079d2  pop     rbx
0x1400079d3  pop     rbp
0x1400079d4  retn
```
