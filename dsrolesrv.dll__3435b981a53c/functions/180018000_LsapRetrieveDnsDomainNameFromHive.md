# LsapRetrieveDnsDomainNameFromHive

- ea: `0x180018000`
- end: `0x18001812d`
- name: `LsapRetrieveDnsDomainNameFromHive`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180016e94`

## callees

- `0x180018000`
- `0x18002c012`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018092`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018092`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018061`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018061`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001809f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001809f`

## pseudocode

```c
__int64 __fastcall LsapRetrieveDnsDomainNameFromHive(HKEY a1, _DWORD *a2, void *a3)
{
  LSTATUS v5; // ebx
  size_t v6; // r8
  __int64 result; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE Src[520]; // [rsp+48h] [rbp-B8h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 520;
  if ( RegOpenKeyExW(a1, L"Policy\\PolDnDDN", 0, 0x2000000u, &hKey) )
    return 3221226021LL;
  v5 = RegQueryValueExW(hKey, 0, 0, &Type, Data, &cbData);
  RegCloseKey(hKey);
  if ( v5 )
    return 3221226021LL;
  if ( Type != 3 && Type )
    return 3221225534LL;
  if ( cbData <= 8 )
    return 3221225534LL;
  v6 = *(unsigned __int16 *)Data;
  if ( (unsigned __int64)*(unsigned __int16 *)Data + 8 > cbData )
    return 3221225534LL;
  if ( (unsigned __int64)*(unsigned __int16 *)Data + 2 > (unsigned int)*a2 )
    return 3221225507LL;
  *a2 = *(unsigned __int16 *)Data;
  memcpy_0(a3, Src, v6);
  result = 0;
  *((_WORD *)a3 + ((unsigned __int64)(unsigned int)*a2 >> 1)) = 0;
  return result;
}

```

## disassembly

```asm
0x180018000  mov     [rsp-8+arg_18], rbx
0x180018005  push    rbp
0x180018006  push    rsi
0x180018007  push    rdi
0x180018008  lea     rbp, [rsp-160h]
0x180018010  sub     rsp, 260h
0x180018017  mov     rax, cs:__security_cookie
0x18001801e  xor     rax, rsp
0x180018021  mov     [rbp+170h+var_20], rax
0x180018028  mov     rsi, r8
0x18001802b  mov     [rsp+270h+hKey], 0
0x180018034  mov     rdi, rdx
0x180018037  mov     [rsp+270h+Type], 0
0x18001803f  lea     rax, [rsp+270h+hKey]
0x180018044  mov     [rsp+270h+cbData], 208h
0x18001804c  xor     r8d, r8d; ulOptions
0x18001804f  mov     [rsp+270h+phkResult], rax; phkResult
0x180018054  lea     rdx, aPolicyPoldnddn; "Policy\\PolDnDDN"
0x18001805b  mov     r9d, 2000000h; samDesired
0x180018061  call    cs:__imp_RegOpenKeyExW
0x180018067  test    eax, eax
0x180018069  jnz     loc_180018106
0x18001806f  mov     rcx, [rsp+270h+hKey]; hKey
0x180018074  lea     rax, [rsp+270h+cbData]
0x180018079  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18001807e  lea     r9, [rsp+270h+Type]; lpType
0x180018083  lea     rax, [rsp+270h+Data]
0x180018088  xor     r8d, r8d; lpReserved
0x18001808b  xor     edx, edx; lpValueName
0x18001808d  mov     [rsp+270h+phkResult], rax; lpData
0x180018092  call    cs:__imp_RegQueryValueExW
0x180018098  mov     rcx, [rsp+270h+hKey]; hKey
0x18001809d  mov     ebx, eax
0x18001809f  call    cs:__imp_RegCloseKey
0x1800180a5  test    ebx, ebx
0x1800180a7  jnz     short loc_180018106
0x1800180a9  mov     eax, [rsp+270h+Type]
0x1800180ad  cmp     eax, 3
0x1800180b0  jz      short loc_1800180B6
0x1800180b2  test    eax, eax
0x1800180b4  jnz     short loc_1800180FF
0x1800180b6  cmp     [rsp+270h+cbData], 8
0x1800180bb  jbe     short loc_1800180FF
0x1800180bd  movzx   r8d, word ptr [rsp+270h+Data]; Size
0x1800180c3  mov     eax, [rsp+270h+cbData]
0x1800180c7  lea     rcx, [r8+8]
0x1800180cb  cmp     rcx, rax
0x1800180ce  ja      short loc_1800180FF
0x1800180d0  mov     eax, [rdi]
0x1800180d2  lea     rcx, [r8+2]
0x1800180d6  cmp     rcx, rax
0x1800180d9  jbe     short loc_1800180E2
0x1800180db  mov     eax, 0C0000023h
0x1800180e0  jmp     short loc_18001810B
0x1800180e2  lea     rdx, [rsp+270h+Src]; Src
0x1800180e7  mov     [rdi], r8d
0x1800180ea  mov     rcx, rsi; void *
0x1800180ed  call    memcpy_0
0x1800180f2  mov     ecx, [rdi]
0x1800180f4  shr     rcx, 1
0x1800180f7  xor     eax, eax
0x1800180f9  mov     [rsi+rcx*2], ax
0x1800180fd  jmp     short loc_18001810B
0x1800180ff  mov     eax, 0C000003Eh
0x180018104  jmp     short loc_18001810B
0x180018106  mov     eax, 0C0000225h
0x18001810b  mov     rcx, [rbp+170h+var_20]
0x180018112  xor     rcx, rsp; StackCookie
0x180018115  call    __security_check_cookie
0x18001811a  mov     rbx, [rsp+270h+arg_18]
0x180018122  add     rsp, 260h
0x180018129  pop     rdi
0x18001812a  pop     rsi
0x18001812b  pop     rbp
0x18001812c  retn
```
