# lProtocolEnabled

- ea: `0x180018d8c`
- end: `0x180018eb0`
- name: `lProtocolEnabled`
- size: `292`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bcc0`
- `0x180017fc8`

## callees

- `0x180018d8c`

## import_xrefs

- `ADVAPI32!RegOpenKeyW` at `0x180018df8`
- `ADVAPI32!RegOpenKeyW` at `0x180018df8`
- `ADVAPI32!RegQueryValueExW` at `0x180018e38`
- `ADVAPI32!RegQueryValueExW` at `0x180018e38`
- `ADVAPI32!RegCloseKey` at `0x180018e8e`
- `ADVAPI32!RegCloseKey` at `0x180018e8e`

## pseudocode

```c
__int64 __fastcall lProtocolEnabled(HKEY a1, int a2, __int64 a3, int a4, int *a5)
{
  int v5; // edi
  const WCHAR *v8; // rdx
  int *v9; // rsi
  unsigned int v10; // ebx
  int v11; // eax
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF

  Data = 0;
  v5 = 0;
  phkResult = 0;
  switch ( a2 )
  {
    case '!':
      v8 = L"Ip";
      v5 = 4;
      break;
    case ')':
      v8 = L"AppleTalk";
      break;
    case 'W':
      v8 = L"Ipv6";
      v5 = 32;
      break;
    default:
      return 0;
  }
  v9 = a5;
  *a5 = 0;
  v10 = RegOpenKeyW(a1, v8, &phkResult);
  if ( !v10 )
  {
    Type = 0;
    cbData = 4;
    v10 = RegQueryValueExW(phkResult, L"EnableIn", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v10 )
    {
      if ( Type == 4 )
      {
        v11 = Data;
        goto LABEL_13;
      }
      v10 = 1804;
    }
    v11 = 0;
    Data = 0;
LABEL_13:
    if ( v10 == 2 || !v10 && v11 )
    {
      v10 = 0;
      *v9 = 1;
    }
    else if ( a4 )
    {
      *v9 = v5 & dword_1800CF64C;
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return v10;
}

```

## disassembly

```asm
0x180018d8c  mov     [rsp-18h+arg_0], rbx
0x180018d91  mov     [rsp-18h+arg_18], rsi
0x180018d96  mov     [rsp-18h+Data], r8d
0x180018d9b  push    rbp
0x180018d9c  push    rdi
0x180018d9d  push    r14
0x180018d9f  mov     rbp, rsp
0x180018da2  sub     rsp, 40h
0x180018da6  and     [rbp+Data], 0
0x180018daa  xor     edi, edi
0x180018dac  and     [rbp+phkResult], 0
0x180018db1  mov     r14d, r9d
0x180018db4  cmp     edx, 21h ; '!'
0x180018db7  jz      short loc_180018DE1
0x180018db9  cmp     edx, 29h ; ')'
0x180018dbc  jz      short loc_180018DD8
0x180018dbe  cmp     edx, 57h ; 'W'
0x180018dc1  jz      short loc_180018DCA
0x180018dc3  xor     eax, eax
0x180018dc5  jmp     loc_180018E9C
0x180018dca  lea     rdx, aIpv6_1; "Ipv6"
0x180018dd1  mov     edi, 20h ; ' '
0x180018dd6  jmp     short loc_180018DED
0x180018dd8  lea     rdx, aAppletalk; "AppleTalk"
0x180018ddf  jmp     short loc_180018DED
0x180018de1  lea     rdx, aIp; "Ip"
0x180018de8  mov     edi, 4
0x180018ded  mov     rsi, [rbp+arg_20]
0x180018df1  lea     r8, [rbp+phkResult]; phkResult
0x180018df5  and     dword ptr [rsi], 0
0x180018df8  call    cs:__imp_RegOpenKeyW
0x180018dff  nop     dword ptr [rax+rax+00h]
0x180018e04  mov     ebx, eax
0x180018e06  test    eax, eax
0x180018e08  jnz     short loc_180018E85
0x180018e0a  and     [rbp+Type], eax
0x180018e0d  lea     r9, [rbp+Type]; lpType
0x180018e11  mov     rcx, [rbp+phkResult]; hKey
0x180018e15  lea     rax, [rbp+cbData]
0x180018e19  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180018e1e  lea     rdx, aEnablein; "EnableIn"
0x180018e25  lea     rax, [rbp+Data]
0x180018e29  mov     [rbp+cbData], 4
0x180018e30  xor     r8d, r8d; lpReserved
0x180018e33  mov     [rsp+40h+lpData], rax; lpData
0x180018e38  call    cs:__imp_RegQueryValueExW
0x180018e3f  nop     dword ptr [rax+rax+00h]
0x180018e44  mov     ebx, eax
0x180018e46  test    eax, eax
0x180018e48  jnz     short loc_180018E55
0x180018e4a  cmp     [rbp+Type], 4
0x180018e4e  jz      short loc_180018E78
0x180018e50  mov     ebx, 70Ch
0x180018e55  xor     eax, eax
0x180018e57  mov     [rbp+Data], eax
0x180018e5a  cmp     ebx, 2
0x180018e5d  jz      short loc_180018E7D
0x180018e5f  test    ebx, ebx
0x180018e61  jnz     short loc_180018E67
0x180018e63  test    eax, eax
0x180018e65  jnz     short loc_180018E7D
0x180018e67  test    r14d, r14d
0x180018e6a  jz      short loc_180018E85
0x180018e6c  mov     eax, cs:dword_1800CF64C
0x180018e72  and     eax, edi
0x180018e74  mov     [rsi], eax
0x180018e76  jmp     short loc_180018E85
0x180018e78  mov     eax, [rbp+Data]
0x180018e7b  jmp     short loc_180018E5A
0x180018e7d  xor     ebx, ebx
0x180018e7f  mov     dword ptr [rsi], 1
0x180018e85  mov     rcx, [rbp+phkResult]; hKey
0x180018e89  test    rcx, rcx
0x180018e8c  jz      short loc_180018E9A
0x180018e8e  call    cs:__imp_RegCloseKey
0x180018e95  nop     dword ptr [rax+rax+00h]
0x180018e9a  mov     eax, ebx
0x180018e9c  mov     rbx, [rsp+40h+arg_0]
0x180018ea1  mov     rsi, [rsp+40h+arg_18]
0x180018ea6  add     rsp, 40h
0x180018eaa  pop     r14
0x180018eac  pop     rdi
0x180018ead  pop     rbp
0x180018eae  retn
```
