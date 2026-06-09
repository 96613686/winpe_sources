# lProtocolEnabled

- ea: `0x18001846c`
- end: `0x18001858b`
- name: `lProtocolEnabled`
- size: `287`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b9f0`
- `0x180017794`

## callees

- `0x18001846c`

## import_xrefs

- `ADVAPI32!RegOpenKeyW` at `0x1800184e1`
- `ADVAPI32!RegOpenKeyW` at `0x1800184e1`
- `ADVAPI32!RegQueryValueExW` at `0x18001851b`
- `ADVAPI32!RegQueryValueExW` at `0x18001851b`
- `ADVAPI32!RegCloseKey` at `0x180018570`
- `ADVAPI32!RegCloseKey` at `0x180018570`

## pseudocode

```c
__int64 __fastcall lProtocolEnabled(HKEY a1, int a2, __int64 a3, int a4, int *a5)
{
  const WCHAR *v7; // rdx
  int v8; // edi
  int *v9; // rsi
  unsigned int v10; // ebx
  int v11; // eax
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF

  Data = 0;
  phkResult = 0;
  switch ( a2 )
  {
    case '!':
      v7 = L"Ip";
      v8 = 4;
      break;
    case ')':
      v8 = 0;
      v7 = L"AppleTalk";
      break;
    case 'W':
      v7 = L"Ipv6";
      v8 = 32;
      break;
    default:
      return 0;
  }
  v9 = a5;
  *a5 = 0;
  v10 = RegOpenKeyW(a1, v7, &phkResult);
  if ( !v10 )
  {
    Type = 0;
    cbData = 4;
    v10 = RegQueryValueExW(phkResult, L"EnableIn", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v10 )
    {
      v11 = 0;
      Data = 0;
      if ( v10 == 2 )
      {
LABEL_18:
        v10 = 0;
        *v9 = 1;
        goto LABEL_19;
      }
    }
    else
    {
      if ( Type != 4 )
      {
        Data = 0;
        v10 = 1804;
        goto LABEL_16;
      }
      v11 = Data;
    }
    if ( v10 || !v11 )
    {
LABEL_16:
      if ( a4 )
        *v9 = v8 & dword_1800C864C;
      goto LABEL_19;
    }
    goto LABEL_18;
  }
LABEL_19:
  if ( phkResult )
    RegCloseKey(phkResult);
  return v10;
}

```

## disassembly

```asm
0x18001846c  mov     [rsp-18h+arg_0], rbx
0x180018471  mov     [rsp-18h+arg_18], rsi
0x180018476  mov     [rsp-18h+Data], r8d
0x18001847b  push    rbp
0x18001847c  push    rdi
0x18001847d  push    r14
0x18001847f  mov     rbp, rsp
0x180018482  sub     rsp, 40h
0x180018486  mov     [rbp+Data], 0
0x18001848d  mov     r14d, r9d
0x180018490  mov     [rbp+phkResult], 0
0x180018498  cmp     edx, 21h ; '!'
0x18001849b  jz      short loc_1800184C7
0x18001849d  cmp     edx, 29h ; ')'
0x1800184a0  jz      short loc_1800184BC
0x1800184a2  cmp     edx, 57h ; 'W'
0x1800184a5  jz      short loc_1800184AE
0x1800184a7  xor     eax, eax
0x1800184a9  jmp     loc_180018578
0x1800184ae  lea     rdx, aIpv6_1; "Ipv6"
0x1800184b5  mov     edi, 20h ; ' '
0x1800184ba  jmp     short loc_1800184D3
0x1800184bc  xor     edi, edi
0x1800184be  lea     rdx, aAppletalk; "AppleTalk"
0x1800184c5  jmp     short loc_1800184D3
0x1800184c7  lea     rdx, aIp; "Ip"
0x1800184ce  mov     edi, 4
0x1800184d3  mov     rsi, [rbp+arg_20]
0x1800184d7  lea     r8, [rbp+phkResult]; phkResult
0x1800184db  mov     dword ptr [rsi], 0
0x1800184e1  call    cs:__imp_RegOpenKeyW
0x1800184e7  mov     ebx, eax
0x1800184e9  test    eax, eax
0x1800184eb  jnz     short loc_180018567
0x1800184ed  mov     rcx, [rbp+phkResult]; hKey
0x1800184f1  lea     r9, [rbp+Type]; lpType
0x1800184f5  mov     [rbp+Type], eax
0x1800184f8  lea     rdx, aEnablein; "EnableIn"
0x1800184ff  lea     rax, [rbp+cbData]
0x180018503  mov     [rbp+cbData], 4
0x18001850a  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001850f  xor     r8d, r8d; lpReserved
0x180018512  lea     rax, [rbp+Data]
0x180018516  mov     [rsp+40h+lpData], rax; lpData
0x18001851b  call    cs:__imp_RegQueryValueExW
0x180018521  mov     ebx, eax
0x180018523  test    eax, eax
0x180018525  jnz     short loc_18001853C
0x180018527  cmp     [rbp+Type], 4
0x18001852b  jz      short loc_180018537
0x18001852d  mov     [rbp+Data], eax
0x180018530  mov     ebx, 70Ch
0x180018535  jmp     short loc_18001854E
0x180018537  mov     eax, [rbp+Data]
0x18001853a  jmp     short loc_180018546
0x18001853c  xor     eax, eax
0x18001853e  mov     [rbp+Data], eax
0x180018541  cmp     ebx, 2
0x180018544  jz      short loc_18001855F
0x180018546  test    ebx, ebx
0x180018548  jnz     short loc_18001854E
0x18001854a  test    eax, eax
0x18001854c  jnz     short loc_18001855F
0x18001854e  test    r14d, r14d
0x180018551  jz      short loc_180018567
0x180018553  mov     eax, cs:dword_1800C864C
0x180018559  and     eax, edi
0x18001855b  mov     [rsi], eax
0x18001855d  jmp     short loc_180018567
0x18001855f  xor     ebx, ebx
0x180018561  mov     dword ptr [rsi], 1
0x180018567  mov     rcx, [rbp+phkResult]; hKey
0x18001856b  test    rcx, rcx
0x18001856e  jz      short loc_180018576
0x180018570  call    cs:__imp_RegCloseKey
0x180018576  mov     eax, ebx
0x180018578  mov     rbx, [rsp+40h+arg_0]
0x18001857d  mov     rsi, [rsp+40h+arg_18]
0x180018582  add     rsp, 40h
0x180018586  pop     r14
0x180018588  pop     rdi
0x180018589  pop     rbp
0x18001858a  retn
```
