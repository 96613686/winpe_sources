# GetRegistryDwordEx

- ea: `0x18000d7e4`
- end: `0x18000d946`
- name: `GetRegistryDwordEx`
- size: `354`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, LPBYTE lpData)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800155f8`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000d7e4`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000d863`
- `ADVAPI32!RegQueryValueExW` at `0x18000d8f5`
- `ADVAPI32!RegQueryValueExW` at `0x18000d863`
- `ADVAPI32!RegQueryValueExW` at `0x18000d8f5`

## pseudocode

```c
__int64 __fastcall GetRegistryDwordEx(HKEY hKey, LPCWSTR lpValueName, LPBYTE lpData)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  DWORD cbData[10]; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type; // [rsp+78h] [rbp+20h] BYREF

  Type = 4;
  cbData[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids);
  }
  v6 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, cbData);
  v7 = v6;
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 15;
LABEL_21:
      WPP_SF_d(v8[2], v9, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids, v6);
    }
  }
  else if ( Type == 4 )
  {
    v6 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, cbData);
    v7 = v6;
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 17;
        goto LABEL_21;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids);
    }
    return 1009;
  }
  return v7;
}

```

## disassembly

```asm
0x18000d7e4  mov     rax, rsp
0x18000d7e7  mov     [rax+8], rbx
0x18000d7eb  mov     [rax+10h], rbp
0x18000d7ef  push    rsi
0x18000d7f0  push    rdi
0x18000d7f1  push    r15
0x18000d7f3  sub     rsp, 40h
0x18000d7f7  mov     rbp, r8
0x18000d7fa  mov     dword ptr [rax+20h], 4
0x18000d801  mov     rdi, rdx
0x18000d804  mov     dword ptr [rax-28h], 0
0x18000d80b  mov     rsi, rcx
0x18000d80e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d815  lea     r15, WPP_GLOBAL_Control
0x18000d81c  cmp     rcx, r15
0x18000d81f  jz      short loc_18000D842
0x18000d821  test    byte ptr [rcx+1Ch], 2
0x18000d825  jz      short loc_18000D842
0x18000d827  cmp     byte ptr [rcx+19h], 5
0x18000d82b  jb      short loc_18000D842
0x18000d82d  mov     rcx, [rcx+10h]
0x18000d831  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x18000d838  mov     edx, 0Eh
0x18000d83d  call    WPP_SF_
0x18000d842  lea     rax, [rsp+58h+cbData]
0x18000d847  xor     r8d, r8d; lpReserved
0x18000d84a  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000d84f  lea     r9, [rsp+58h+Type]; lpType
0x18000d854  mov     rdx, rdi; lpValueName
0x18000d857  mov     [rsp+58h+lpData], 0; lpData
0x18000d860  mov     rcx, rsi; hKey
0x18000d863  call    cs:__imp_RegQueryValueExW
0x18000d869  mov     ebx, eax
0x18000d86b  test    eax, eax
0x18000d86d  jz      short loc_18000D89D
0x18000d86f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d876  cmp     rcx, r15
0x18000d879  jz      loc_18000D931
0x18000d87f  test    byte ptr [rcx+1Ch], 2
0x18000d883  jz      loc_18000D931
0x18000d889  cmp     byte ptr [rcx+19h], 2
0x18000d88d  jb      loc_18000D931
0x18000d893  mov     edx, 0Fh
0x18000d898  jmp     loc_18000D91E
0x18000d89d  cmp     [rsp+58h+Type], 4
0x18000d8a2  jz      short loc_18000D8D8
0x18000d8a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8ab  cmp     rcx, r15
0x18000d8ae  jz      short loc_18000D8D1
0x18000d8b0  test    byte ptr [rcx+1Ch], 2
0x18000d8b4  jz      short loc_18000D8D1
0x18000d8b6  cmp     byte ptr [rcx+19h], 2
0x18000d8ba  jb      short loc_18000D8D1
0x18000d8bc  mov     rcx, [rcx+10h]
0x18000d8c0  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x18000d8c7  mov     edx, 10h
0x18000d8cc  call    WPP_SF_
0x18000d8d1  mov     ebx, 3F1h
0x18000d8d6  jmp     short loc_18000D931
0x18000d8d8  lea     rax, [rsp+58h+cbData]
0x18000d8dd  xor     r8d, r8d; lpReserved
0x18000d8e0  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000d8e5  lea     r9, [rsp+58h+Type]; lpType
0x18000d8ea  mov     rdx, rdi; lpValueName
0x18000d8ed  mov     [rsp+58h+lpData], rbp; lpData
0x18000d8f2  mov     rcx, rsi; hKey
0x18000d8f5  call    cs:__imp_RegQueryValueExW
0x18000d8fb  mov     ebx, eax
0x18000d8fd  test    eax, eax
0x18000d8ff  jz      short loc_18000D931
0x18000d901  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d908  cmp     rcx, r15
0x18000d90b  jz      short loc_18000D931
0x18000d90d  test    byte ptr [rcx+1Ch], 2
0x18000d911  jz      short loc_18000D931
0x18000d913  cmp     byte ptr [rcx+19h], 2
0x18000d917  jb      short loc_18000D931
0x18000d919  mov     edx, 11h
0x18000d91e  mov     rcx, [rcx+10h]
0x18000d922  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x18000d929  mov     r9d, eax
0x18000d92c  call    WPP_SF_d
0x18000d931  mov     rbp, [rsp+58h+arg_8]
0x18000d936  mov     eax, ebx
0x18000d938  mov     rbx, [rsp+58h+arg_0]
0x18000d93d  add     rsp, 40h
0x18000d941  pop     r15
0x18000d943  pop     rdi
0x18000d944  pop     rsi
0x18000d945  retn
```
