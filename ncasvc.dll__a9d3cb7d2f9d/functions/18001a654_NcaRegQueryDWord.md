# NcaRegQueryDWord

- ea: `0x18001a654`
- end: `0x18001a7bb`
- name: `NcaRegQueryDWord`
- size: `359`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, LPBYTE lpData, int *)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180005260`
- `0x180010bcc`
- `0x180014058`
- `0x180014ea0`

## callees

- `0x180002d50`
- `0x1800033bc`
- `0x1800037b0`
- `0x180016e30`
- `0x1800199b4`
- `0x18001a654`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a726`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a726`

## pseudocode

```c
__int64 __fastcall NcaRegQueryDWord(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, LPBYTE lpData, int *a5)
{
  int v5; // ebx
  int *v10; // rdi
  int v11; // eax
  __int64 v12; // rdx
  unsigned int v13; // eax
  DWORD Type; // [rsp+30h] [rbp-38h] BYREF
  HKEY v16; // [rsp+38h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+10h] BYREF

  v5 = 0;
  v16 = 0;
  Type = 0;
  cbData = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_149084e4aca63d179354f111bb13106e_Traceguids,
      (_DWORD)lpSubKey,
      (__int64)lpValueName);
  v10 = a5;
  if ( lpSubKey )
  {
    v11 = NcaRegOpenKey(hKey, lpSubKey, 1u, &v16, a5);
    v5 = v11;
    if ( v11 < 0 )
    {
      v12 = (unsigned int)v11;
      goto LABEL_18;
    }
    if ( !*v10 )
      goto LABEL_19;
    hKey = v16;
  }
  cbData = 4;
  v13 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
  if ( v13 == 2 )
  {
    *v10 = 0;
    goto LABEL_19;
  }
  if ( v13 != 234 )
  {
    if ( v13 )
    {
      v5 = NcaReportErrorAsWinError("NcaRegQueryDWord", "RegQueryValueExW", v13);
      goto LABEL_19;
    }
    if ( Type == 4 && cbData == 4 )
    {
      *v10 = 1;
      goto LABEL_19;
    }
  }
  v12 = 2147942413LL;
  v5 = -2147024883;
LABEL_18:
  NcaReportReturnError("NcaRegQueryDWord", v12);
LABEL_19:
  NcaRegCloseKey(v16);
  if ( v5 < 0 )
    return (unsigned int)NcaReportReturnError("NcaRegQueryDWord", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001a654  mov     rax, rsp
0x18001a657  mov     [rax+8], rbx
0x18001a65b  mov     [rax+18h], rbp
0x18001a65f  push    rsi
0x18001a660  push    rdi
0x18001a661  push    r13
0x18001a663  push    r14
0x18001a665  push    r15
0x18001a667  sub     rsp, 40h
0x18001a66b  xor     ebx, ebx
0x18001a66d  mov     r15, r9
0x18001a670  mov     [rax-30h], rbx
0x18001a674  mov     r14, r8
0x18001a677  mov     [rax-38h], ebx
0x18001a67a  mov     rsi, rdx
0x18001a67d  mov     [rax+10h], ebx
0x18001a680  mov     rbp, rcx
0x18001a683  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a68a  lea     rax, WPP_GLOBAL_Control
0x18001a691  cmp     rcx, rax
0x18001a694  jz      short loc_18001A6B7
0x18001a696  test    byte ptr [rcx+1Ch], 8
0x18001a69a  jz      short loc_18001A6B7
0x18001a69c  mov     rcx, [rcx+10h]
0x18001a6a0  lea     edx, [rbx+10h]
0x18001a6a3  mov     [rsp+68h+lpData], r8
0x18001a6a8  mov     r9, rsi
0x18001a6ab  lea     r8, WPP_149084e4aca63d179354f111bb13106e_Traceguids
0x18001a6b2  call    WPP_SF_SS
0x18001a6b7  mov     rdi, [rsp+68h+arg_20]
0x18001a6bf  lea     r13, aNcaregquerydwo; "NcaRegQueryDWord"
0x18001a6c6  test    rsi, rsi
0x18001a6c9  jz      short loc_18001A701
0x18001a6cb  lea     r9, [rsp+68h+var_30]
0x18001a6d0  mov     [rsp+68h+lpData], rdi; __int64
0x18001a6d5  mov     r8d, 1; samDesired
0x18001a6db  mov     rdx, rsi; lpSubKey
0x18001a6de  mov     rcx, rbp; hKey
0x18001a6e1  call    NcaRegOpenKey
0x18001a6e6  mov     ebx, eax
0x18001a6e8  test    eax, eax
0x18001a6ea  jns     short loc_18001A6F3
0x18001a6ec  mov     edx, eax
0x18001a6ee  jmp     loc_18001A77D
0x18001a6f3  cmp     dword ptr [rdi], 0
0x18001a6f6  jz      loc_18001A785
0x18001a6fc  mov     rbp, [rsp+68h+var_30]
0x18001a701  lea     rax, [rsp+68h+cbData]
0x18001a706  mov     [rsp+68h+cbData], 4
0x18001a70e  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18001a713  lea     r9, [rsp+68h+Type]; lpType
0x18001a718  xor     r8d, r8d; lpReserved
0x18001a71b  mov     [rsp+68h+lpData], r15; lpData
0x18001a720  mov     rdx, r14; lpValueName
0x18001a723  mov     rcx, rbp; hKey
0x18001a726  call    cs:__imp_RegQueryValueExW
0x18001a72d  nop     dword ptr [rax+rax+00h]
0x18001a732  cmp     eax, 2
0x18001a735  jnz     short loc_18001A73F
0x18001a737  mov     dword ptr [rdi], 0
0x18001a73d  jmp     short loc_18001A785
0x18001a73f  cmp     eax, 0EAh
0x18001a744  jz      short loc_18001A776
0x18001a746  test    eax, eax
0x18001a748  jz      short loc_18001A760
0x18001a74a  mov     r8d, eax
0x18001a74d  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x18001a754  mov     rcx, r13
0x18001a757  call    NcaReportErrorAsWinError
0x18001a75c  mov     ebx, eax
0x18001a75e  jmp     short loc_18001A785
0x18001a760  cmp     [rsp+68h+Type], 4
0x18001a765  jnz     short loc_18001A776
0x18001a767  cmp     [rsp+68h+cbData], 4
0x18001a76c  jnz     short loc_18001A776
0x18001a76e  mov     dword ptr [rdi], 1
0x18001a774  jmp     short loc_18001A785
0x18001a776  mov     edx, 8007000Dh
0x18001a77b  mov     ebx, edx
0x18001a77d  mov     rcx, r13
0x18001a780  call    NcaReportReturnError
0x18001a785  mov     rcx, [rsp+68h+var_30]
0x18001a78a  call    NcaRegCloseKey
0x18001a78f  test    ebx, ebx
0x18001a791  jns     short loc_18001A79F
0x18001a793  mov     edx, ebx
0x18001a795  mov     rcx, r13
0x18001a798  call    NcaReportReturnError
0x18001a79d  mov     ebx, eax
0x18001a79f  lea     r11, [rsp+68h+var_28]
0x18001a7a4  mov     eax, ebx
0x18001a7a6  mov     rbx, [r11+30h]
0x18001a7aa  mov     rbp, [r11+40h]
0x18001a7ae  mov     rsp, r11
0x18001a7b1  pop     r15
0x18001a7b3  pop     r14
0x18001a7b5  pop     r13
0x18001a7b7  pop     rdi
0x18001a7b8  pop     rsi
0x18001a7b9  retn
```
