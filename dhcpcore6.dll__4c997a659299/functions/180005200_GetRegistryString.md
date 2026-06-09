# GetRegistryString

- ea: `0x180005200`
- end: `0x18000535f`
- name: `GetRegistryString`
- size: `351`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180004d78`
- `0x180016350`

## callees

- `0x180005200`
- `0x180007564`
- `0x18000c740`
- `0x1800338c0`
- `0x180033900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005275`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800052fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005275`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800052fc`

## pseudocode

```c
__int64 __fastcall GetRegistryString(HKEY hKey, LPCWSTR lpValueName, BYTE **a3, __int64 a4)
{
  unsigned int v7; // ebx
  BYTE *v9; // rdi
  unsigned int v10; // eax
  __int64 v11; // rcx
  BYTE *lpData; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+20h] BYREF
  int v15; // [rsp+7Ch] [rbp+24h]

  v15 = HIDWORD(a4);
  Type = 0;
  cbData = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_(1028, 10, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids);
  *a3 = 0;
  v7 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
  if ( !v7 && cbData )
  {
    lpData = (BYTE *)DhcpAlloc(cbData + 2LL);
    v9 = lpData;
    if ( lpData )
    {
      v10 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
      v7 = v10;
      if ( v10 )
      {
        if ( (xmmword_1800423E0 & 2) != 0 )
          WPP_SF_D(1025, 11, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids, v10);
        DhcpFree((LPVOID *)&lpData);
      }
      else
      {
        v11 = cbData & 0xFFFFFFFE;
        *a3 = lpData;
        *(_WORD *)&v9[v11] = 0;
      }
    }
    else
    {
      v7 = 8;
    }
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 12, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180005200  mov     rax, rsp
0x180005203  mov     [rax+8], rbx
0x180005207  mov     [rax+10h], rbp
0x18000520b  mov     [rax+20h], r9
0x18000520f  push    rsi
0x180005210  push    rdi
0x180005211  push    r14
0x180005213  sub     rsp, 40h
0x180005217  mov     rsi, r8
0x18000521a  mov     dword ptr [rax+18h], 0
0x180005221  mov     rbp, rdx
0x180005224  mov     dword ptr [rax+20h], 0
0x18000522b  mov     r14, rcx
0x18000522e  test    byte ptr cs:xmmword_1800423E0, 10h
0x180005235  jz      short loc_18000524D
0x180005237  mov     edx, 0Ah
0x18000523c  lea     r8, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids
0x180005243  mov     ecx, 404h
0x180005248  call    WPP_SF_
0x18000524d  lea     rax, [rsp+58h+cbData]
0x180005252  mov     qword ptr [rsi], 0
0x180005259  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000525e  lea     r9, [rsp+58h+Type]; lpType
0x180005263  xor     r8d, r8d; lpReserved
0x180005266  mov     [rsp+58h+lpData], 0; lpData
0x18000526f  mov     rdx, rbp; lpValueName
0x180005272  mov     rcx, r14; hKey
0x180005275  call    cs:__imp_RegQueryValueExW
0x18000527c  nop     dword ptr [rax+rax+00h]
0x180005281  mov     ebx, eax
0x180005283  test    eax, eax
0x180005285  jz      short loc_1800052C1
0x180005287  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000528e  jnz     short loc_1800052A6
0x180005290  mov     rbp, [rsp+58h+arg_8]
0x180005295  mov     eax, ebx
0x180005297  mov     rbx, [rsp+58h+arg_0]
0x18000529c  add     rsp, 40h
0x1800052a0  pop     r14
0x1800052a2  pop     rdi
0x1800052a3  pop     rsi
0x1800052a4  retn
0x1800052a6  mov     edx, 0Ch
0x1800052ab  lea     r8, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids
0x1800052b2  mov     ecx, 404h
0x1800052b7  mov     r9d, ebx
0x1800052ba  call    WPP_SF_D
0x1800052bf  jmp     short loc_180005290
0x1800052c1  mov     eax, [rsp+58h+cbData]
0x1800052c5  test    eax, eax
0x1800052c7  jz      short loc_180005287
0x1800052c9  lea     rcx, [rax+2]
0x1800052cd  call    DhcpAlloc
0x1800052d2  mov     [rsp+58h+var_28], rax
0x1800052d7  mov     rdi, rax
0x1800052da  test    rax, rax
0x1800052dd  jz      short loc_18000533F
0x1800052df  lea     rax, [rsp+58h+cbData]
0x1800052e4  xor     r8d, r8d; lpReserved
0x1800052e7  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800052ec  lea     r9, [rsp+58h+Type]; lpType
0x1800052f1  mov     rdx, rbp; lpValueName
0x1800052f4  mov     [rsp+58h+lpData], rdi; lpData
0x1800052f9  mov     rcx, r14; hKey
0x1800052fc  call    cs:__imp_RegQueryValueExW
0x180005303  nop     dword ptr [rax+rax+00h]
0x180005308  mov     ebx, eax
0x18000530a  test    eax, eax
0x18000530c  jz      short loc_180005349
0x18000530e  test    byte ptr cs:xmmword_1800423E0, 2
0x180005315  jz      short loc_180005330
0x180005317  mov     edx, 0Bh
0x18000531c  lea     r8, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids
0x180005323  mov     ecx, 401h
0x180005328  mov     r9d, eax
0x18000532b  call    WPP_SF_D
0x180005330  lea     rcx, [rsp+58h+var_28]
0x180005335  call    DhcpFree
0x18000533a  jmp     loc_180005287
0x18000533f  mov     ebx, 8
0x180005344  jmp     loc_180005287
0x180005349  mov     ecx, [rsp+58h+cbData]
0x18000534d  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180005351  mov     [rsi], rdi
0x180005354  xor     eax, eax
0x180005356  mov     [rcx+rdi], ax
0x18000535a  jmp     loc_180005287
```
