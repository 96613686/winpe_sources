# GetDWORDFromReg(ushort const *,ushort const *)

- ea: `0x1800033a0`
- end: `0x18000349d`
- name: `?GetDWORDFromReg@@YAKPEBG0@Z`
- size: `253`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002ed8`
- `0x1800037bc`

## callees

- `0x180002c90`
- `0x1800033a0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800033e7`
- `ADVAPI32!RegOpenKeyExW` at `0x1800033e7`
- `ADVAPI32!RegCloseKey` at `0x18000347e`
- `ADVAPI32!RegCloseKey` at `0x18000347e`
- `ADVAPI32!RegQueryValueExW` at `0x180003437`
- `ADVAPI32!RegQueryValueExW` at `0x180003437`

## pseudocode

```c
__int64 __fastcall GetDWORDFromReg(LPCWSTR lpSubKey, LPCWSTR lpValueName)
{
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 result; // rax
  DWORD Type; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+60h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF

  Data = 0;
  Type = 4;
  cbData = 4;
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 19;
LABEL_9:
      WPP_SF_d(v4[2], v5, WPP_0ae963c2f6a739e5a6734f4927a5ba0b_Traceguids, v3);
    }
  }
  else
  {
    v3 = RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v3 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 20;
        goto LABEL_9;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v3 )
    return 0;
  result = Data;
  if ( !Data )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1800033a0  mov     r11, rsp
0x1800033a3  mov     [r11+8], rbx
0x1800033a7  push    rdi
0x1800033a8  sub     rsp, 40h
0x1800033ac  mov     eax, 4
0x1800033b1  mov     [rsp+48h+Data], 0
0x1800033b9  mov     [rsp+48h+Type], eax
0x1800033bd  mov     rdi, rdx
0x1800033c0  mov     [rsp+48h+cbData], eax
0x1800033c4  mov     rdx, rcx; lpSubKey
0x1800033c7  lea     rax, [r11-10h]
0x1800033cb  mov     qword ptr [r11-10h], 0
0x1800033d3  mov     r9d, 20019h; samDesired
0x1800033d9  mov     [r11-28h], rax
0x1800033dd  xor     r8d, r8d; ulOptions
0x1800033e0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800033e7  call    cs:__imp_RegOpenKeyExW
0x1800033ed  mov     ebx, eax
0x1800033ef  test    eax, eax
0x1800033f1  jz      short loc_180003413
0x1800033f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033fa  lea     rax, WPP_GLOBAL_Control
0x180003401  cmp     rcx, rax
0x180003404  jz      short loc_180003474
0x180003406  test    byte ptr [rcx+1Ch], 1
0x18000340a  jz      short loc_180003474
0x18000340c  mov     edx, 13h
0x180003411  jmp     short loc_180003461
0x180003413  mov     rcx, [rsp+48h+hKey]; hKey
0x180003418  lea     rax, [rsp+48h+cbData]
0x18000341d  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180003422  lea     r9, [rsp+48h+Type]; lpType
0x180003427  lea     rax, [rsp+48h+Data]
0x18000342c  xor     r8d, r8d; lpReserved
0x18000342f  mov     rdx, rdi; lpValueName
0x180003432  mov     [rsp+48h+lpData], rax; lpData
0x180003437  call    cs:__imp_RegQueryValueExW
0x18000343d  mov     ebx, eax
0x18000343f  test    eax, eax
0x180003441  jz      short loc_180003474
0x180003443  mov     rcx, cs:WPP_GLOBAL_Control
0x18000344a  lea     rax, WPP_GLOBAL_Control
0x180003451  cmp     rcx, rax
0x180003454  jz      short loc_180003474
0x180003456  test    byte ptr [rcx+1Ch], 1
0x18000345a  jz      short loc_180003474
0x18000345c  mov     edx, 14h
0x180003461  mov     rcx, [rcx+10h]
0x180003465  lea     r8, WPP_0ae963c2f6a739e5a6734f4927a5ba0b_Traceguids
0x18000346c  mov     r9d, ebx
0x18000346f  call    WPP_SF_d
0x180003474  mov     rcx, [rsp+48h+hKey]; hKey
0x180003479  test    rcx, rcx
0x18000347c  jz      short loc_180003484
0x18000347e  call    cs:__imp_RegCloseKey
0x180003484  test    ebx, ebx
0x180003486  jnz     short loc_180003490
0x180003488  mov     eax, [rsp+48h+Data]
0x18000348c  test    eax, eax
0x18000348e  jnz     short loc_180003492
0x180003490  xor     eax, eax
0x180003492  mov     rbx, [rsp+48h+arg_0]
0x180003497  add     rsp, 40h
0x18000349b  pop     rdi
0x18000349c  retn
```
