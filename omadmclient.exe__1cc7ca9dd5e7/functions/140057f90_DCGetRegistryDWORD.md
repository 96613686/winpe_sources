# DCGetRegistryDWORD

- ea: `0x140057f90`
- end: `0x1400580a3`
- name: `DCGetRegistryDWORD`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140058a5c`

## callees

- `0x140057f90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140057ff4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140057ff4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140058039`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140058039`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058081`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058081`

## pseudocode

```c
__int64 __fastcall DCGetRegistryDWORD(HKEY a1, const WCHAR *a2, const WCHAR *a3, _DWORD *a4)
{
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  int Data; // [rsp+68h] [rbp+28h] BYREF

  Data = 0;
  Type = 4;
  hKey = 0;
  cbData = 4;
  if ( !a1 || !a4 )
  {
    v8 = -2147024809;
    goto LABEL_16;
  }
  if ( !a2 )
  {
    hKey = a1;
LABEL_9:
    v9 = RegQueryValueExW(a1, a3, 0, &Type, (LPBYTE)&Data, &cbData);
    v8 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
    }
    else if ( Type == 4 )
    {
      v8 = 0;
      *a4 = Data;
    }
    else
    {
      v8 = -2147418113;
    }
LABEL_16:
    if ( !a2 )
      return v8;
    goto LABEL_17;
  }
  v7 = RegOpenKeyExW(a1, a2, 0, 0x20119u, &hKey);
  v8 = v7;
  if ( !v7 )
  {
    a1 = hKey;
    goto LABEL_9;
  }
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x140057f90  mov     [rsp-18h+arg_10], rbx
0x140057f95  mov     [rsp-18h+arg_18], rsi
0x140057f9a  push    rbp
0x140057f9b  push    rdi
0x140057f9c  push    r14
0x140057f9e  mov     rbp, rsp
0x140057fa1  sub     rsp, 40h
0x140057fa5  mov     [rbp+Data], 0
0x140057fac  mov     rsi, r9
0x140057faf  mov     [rbp+Type], 4
0x140057fb6  mov     r14, r8
0x140057fb9  mov     [rbp+hKey], 0
0x140057fc1  mov     rdi, rdx
0x140057fc4  mov     [rbp+cbData], 4
0x140057fcb  test    rcx, rcx
0x140057fce  jz      loc_14005806E
0x140057fd4  test    r9, r9
0x140057fd7  jz      loc_14005806E
0x140057fdd  test    rdx, rdx
0x140057fe0  jz      short loc_140058019
0x140057fe2  lea     rax, [rbp+hKey]
0x140057fe6  mov     r9d, 20119h; samDesired
0x140057fec  xor     r8d, r8d; ulOptions
0x140057fef  mov     [rsp+40h+phkResult], rax; phkResult
0x140057ff4  call    cs:__imp_RegOpenKeyExW
0x140057ffb  nop     dword ptr [rax+rax+00h]
0x140058000  mov     ebx, eax
0x140058002  test    eax, eax
0x140058004  jz      short loc_140058013
0x140058006  jle     short loc_140058078
0x140058008  movzx   ebx, ax
0x14005800b  or      ebx, 80070000h
0x140058011  jmp     short loc_140058078
0x140058013  mov     rcx, [rbp+hKey]; hKey
0x140058017  jmp     short loc_14005801D
0x140058019  mov     [rbp+hKey], rcx
0x14005801d  lea     rax, [rbp+cbData]
0x140058021  xor     r8d, r8d; lpReserved
0x140058024  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140058029  lea     r9, [rbp+Type]; lpType
0x14005802d  lea     rax, [rbp+Data]
0x140058031  mov     rdx, r14; lpValueName
0x140058034  mov     [rsp+40h+phkResult], rax; lpData
0x140058039  call    cs:__imp_RegQueryValueExW
0x140058040  nop     dword ptr [rax+rax+00h]
0x140058045  mov     ebx, eax
0x140058047  test    eax, eax
0x140058049  jz      short loc_140058058
0x14005804b  jle     short loc_140058073
0x14005804d  movzx   ebx, ax
0x140058050  or      ebx, 80070000h
0x140058056  jmp     short loc_140058073
0x140058058  cmp     [rbp+Type], 4
0x14005805c  jz      short loc_140058065
0x14005805e  mov     ebx, 8000FFFFh
0x140058063  jmp     short loc_140058073
0x140058065  mov     eax, [rbp+Data]
0x140058068  xor     ebx, ebx
0x14005806a  mov     [rsi], eax
0x14005806c  jmp     short loc_140058073
0x14005806e  mov     ebx, 80070057h
0x140058073  test    rdi, rdi
0x140058076  jz      short loc_14005808D
0x140058078  mov     rcx, [rbp+hKey]; hKey
0x14005807c  test    rcx, rcx
0x14005807f  jz      short loc_14005808D
0x140058081  call    cs:__imp_RegCloseKey
0x140058088  nop     dword ptr [rax+rax+00h]
0x14005808d  mov     rsi, [rsp+40h+arg_18]
0x140058092  mov     eax, ebx
0x140058094  mov     rbx, [rsp+40h+arg_10]
0x140058099  add     rsp, 40h
0x14005809d  pop     r14
0x14005809f  pop     rdi
0x1400580a0  pop     rbp
0x1400580a1  retn
```
