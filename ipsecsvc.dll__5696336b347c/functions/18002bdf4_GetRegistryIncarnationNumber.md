# GetRegistryIncarnationNumber

- ea: `0x18002bdf4`
- end: `0x18002bf53`
- name: `GetRegistryIncarnationNumber`
- size: `351`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002d2ec`

## callees

- `0x18000e510`
- `0x18002bdf4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002becc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002becc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002be3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002be3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bf43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bf43`

## pseudocode

```c
__int64 __fastcall GetRegistryIncarnationNumber(LPCWSTR lpSubKey, _DWORD *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+68h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  *a2 = 0;
  Type = 4;
  cbData = 4;
  hKey = 0;
  Data = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  v4 = v3;
  if ( v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v6 = 130;
LABEL_13:
        v7 = v3;
LABEL_14:
        WPP_SF_d(v5[2], v6, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v7);
        v5 = WPP_GLOBAL_Control;
        goto LABEL_15;
      }
      goto LABEL_15;
    }
  }
  else
  {
    if ( !hKey )
    {
      v4 = 1359;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v4;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_15;
      v6 = 131;
      v7 = 1359;
      goto LABEL_14;
    }
    v3 = RegQueryValueExW(hKey, L"whenChanged", 0, &Type, (LPBYTE)&Data, &cbData);
    v4 = v3;
    if ( v3 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v6 = 132;
          goto LABEL_13;
        }
LABEL_15:
        if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 )
          WPP_SF_d(v5[2], 133, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v4);
      }
    }
    else
    {
      *a2 = Data;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x18002bdf4  push    rbp
0x18002bdf6  push    rbx
0x18002bdf7  push    rdi
0x18002bdf8  mov     rbp, rsp
0x18002bdfb  sub     rsp, 40h
0x18002bdff  mov     eax, 4
0x18002be04  mov     dword ptr [rdx], 0
0x18002be0a  mov     [rbp+Type], eax
0x18002be0d  mov     rdi, rdx
0x18002be10  mov     [rbp+cbData], eax
0x18002be13  mov     rdx, rcx; lpSubKey
0x18002be16  lea     rax, [rbp+hKey]
0x18002be1a  mov     [rbp+hKey], 0
0x18002be22  mov     r9d, 20019h; samDesired
0x18002be28  mov     [rsp+40h+phkResult], rax; phkResult
0x18002be2d  xor     r8d, r8d; ulOptions
0x18002be30  mov     [rbp+Data], 0
0x18002be37  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002be3e  call    cs:__imp_RegOpenKeyExW
0x18002be44  mov     ebx, eax
0x18002be46  test    eax, eax
0x18002be48  jz      short loc_18002BE75
0x18002be4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be51  lea     rdi, WPP_GLOBAL_Control
0x18002be58  cmp     rcx, rdi
0x18002be5b  jz      loc_18002BF3A
0x18002be61  test    byte ptr [rcx+1Ch], 10h
0x18002be65  jz      loc_18002BF10
0x18002be6b  mov     edx, 82h
0x18002be70  jmp     loc_18002BEF6
0x18002be75  cmp     [rbp+hKey], 0
0x18002be7a  jnz     short loc_18002BEA8
0x18002be7c  mov     ebx, 54Fh
0x18002be81  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be88  lea     rdi, WPP_GLOBAL_Control
0x18002be8f  cmp     rcx, rdi
0x18002be92  jz      loc_18002BF49
0x18002be98  test    byte ptr [rcx+1Ch], 10h
0x18002be9c  jz      short loc_18002BF10
0x18002be9e  mov     edx, 83h
0x18002bea3  mov     r9d, ebx
0x18002bea6  jmp     short loc_18002BEF9
0x18002bea8  mov     rcx, [rbp+hKey]; hKey
0x18002beac  lea     rax, [rbp+cbData]
0x18002beb0  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002beb5  lea     r9, [rbp+Type]; lpType
0x18002beb9  lea     rax, [rbp+Data]
0x18002bebd  xor     r8d, r8d; lpReserved
0x18002bec0  lea     rdx, aWhenchanged_0; "whenChanged"
0x18002bec7  mov     [rsp+40h+phkResult], rax; lpData
0x18002becc  call    cs:__imp_RegQueryValueExW
0x18002bed2  mov     ebx, eax
0x18002bed4  test    eax, eax
0x18002bed6  jz      short loc_18002BF35
0x18002bed8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bedf  lea     rdi, WPP_GLOBAL_Control
0x18002bee6  cmp     rcx, rdi
0x18002bee9  jz      short loc_18002BF3A
0x18002beeb  test    byte ptr [rcx+1Ch], 10h
0x18002beef  jz      short loc_18002BF10
0x18002bef1  mov     edx, 84h
0x18002bef6  mov     r9d, eax
0x18002bef9  mov     rcx, [rcx+10h]
0x18002befd  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002bf04  call    WPP_SF_d
0x18002bf09  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf10  cmp     rcx, rdi
0x18002bf13  jz      short loc_18002BF3A
0x18002bf15  test    byte ptr [rcx+1Ch], 10h
0x18002bf19  jz      short loc_18002BF3A
0x18002bf1b  mov     rcx, [rcx+10h]
0x18002bf1f  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002bf26  mov     edx, 85h
0x18002bf2b  mov     r9d, ebx
0x18002bf2e  call    WPP_SF_d
0x18002bf33  jmp     short loc_18002BF3A
0x18002bf35  mov     eax, [rbp+Data]
0x18002bf38  mov     [rdi], eax
0x18002bf3a  mov     rcx, [rbp+hKey]; hKey
0x18002bf3e  test    rcx, rcx
0x18002bf41  jz      short loc_18002BF49
0x18002bf43  call    cs:__imp_RegCloseKey
0x18002bf49  mov     eax, ebx
0x18002bf4b  add     rsp, 40h
0x18002bf4f  pop     rdi
0x18002bf50  pop     rbx
0x18002bf51  pop     rbp
0x18002bf52  retn
```
