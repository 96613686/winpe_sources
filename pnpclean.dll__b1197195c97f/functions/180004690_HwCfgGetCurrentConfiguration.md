# HwCfgGetCurrentConfiguration

- ea: `0x180004690`
- end: `0x180004745`
- name: `HwCfgGetCurrentConfiguration`
- size: `181`
- prototype: `__int64 __fastcall(__int64, __int64, BYTE *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003d70`
- `0x180004c14`

## callees

- `0x180004690`
- `0x18000474c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180004732`
- `ADVAPI32!RegCloseKey` at `0x180004732`
- `ADVAPI32!RegQueryValueExW` at `0x180004706`
- `ADVAPI32!RegQueryValueExW` at `0x180004706`

## pseudocode

```c
__int64 __fastcall HwCfgGetCurrentConfiguration(__int64 a1, __int64 a2, BYTE *a3)
{
  unsigned int CurrentKey; // ebx
  DWORD Type; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  int v8; // [rsp+4Ch] [rbp+14h]
  HKEY hKey; // [rsp+58h] [rbp+20h]

  v8 = HIDWORD(a2);
  CurrentKey = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( a3 )
  {
    CurrentKey = HwCfgGetCurrentKey(0x20019u);
    if ( !CurrentKey )
    {
      Type = 0;
      cbData = 4;
      CurrentKey = RegQueryValueExW(hKey, L"Id", 0, &Type, a3, &cbData);
      if ( !CurrentKey && (Type != 4 || cbData != 4) )
        CurrentKey = 13;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return CurrentKey;
}

```

## disassembly

```asm
0x180004690  mov     rax, rsp
0x180004693  mov     [rax+18h], rbx
0x180004697  mov     [rax+10h], rdx
0x18000469b  mov     [rax+8], ecx
0x18000469e  push    rsi
0x18000469f  sub     rsp, 30h
0x1800046a3  xor     ebx, ebx
0x1800046a5  mov     qword ptr [rax+20h], 0
0x1800046ad  mov     dword ptr [rax+8], 0
0x1800046b4  mov     rsi, r8
0x1800046b7  mov     dword ptr [rax+10h], 0
0x1800046be  test    r8, r8
0x1800046c1  jz      short loc_180004738
0x1800046c3  lea     rdx, [rax+20h]
0x1800046c7  mov     ecx, 20019h; samDesired
0x1800046cc  call    HwCfgGetCurrentKey
0x1800046d1  mov     ebx, eax
0x1800046d3  test    eax, eax
0x1800046d5  jnz     short loc_180004725
0x1800046d7  mov     rcx, [rsp+38h+hKey]; hKey
0x1800046dc  lea     r9, [rsp+38h+Type]; lpType
0x1800046e1  mov     [rsp+38h+Type], eax
0x1800046e5  lea     rdx, aId; "Id"
0x1800046ec  lea     rax, [rsp+38h+cbData]
0x1800046f1  mov     [rsp+38h+cbData], 4
0x1800046f9  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800046fe  xor     r8d, r8d; lpReserved
0x180004701  mov     [rsp+38h+lpData], rsi; lpData
0x180004706  call    cs:__imp_RegQueryValueExW
0x18000470c  mov     ebx, eax
0x18000470e  test    eax, eax
0x180004710  jnz     short loc_180004725
0x180004712  cmp     [rsp+38h+Type], 4
0x180004717  jnz     short loc_180004720
0x180004719  cmp     [rsp+38h+cbData], 4
0x18000471e  jz      short loc_180004725
0x180004720  mov     ebx, 0Dh
0x180004725  cmp     [rsp+38h+hKey], 0
0x18000472b  jz      short loc_180004738
0x18000472d  mov     rcx, [rsp+38h+hKey]; hKey
0x180004732  call    cs:__imp_RegCloseKey
0x180004738  mov     eax, ebx
0x18000473a  mov     rbx, [rsp+38h+arg_10]
0x18000473f  add     rsp, 30h
0x180004743  pop     rsi
0x180004744  retn
```
