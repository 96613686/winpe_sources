# SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x180014b4c`
- end: `0x180014c28`
- name: `?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z`
- size: `220`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006dbc`
- `0x180012b14`
- `0x180012ca0`
- `0x1800133d4`
- `0x180013db0`
- `0x180030050`
- `0x180037bbc`
- `0x1800393f8`
- `0x180041f2c`

## callees

- `0x180014b4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014c1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014c1a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014b96`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014b96`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014bf3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014bf3`

## pseudocode

```c
__int64 __fastcall SHRegSetDWORD(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  HKEY v5; // rdi
  LSTATUS v6; // ebx
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF
  int Data; // [rsp+88h] [rbp+20h] BYREF

  Data = a4;
  hKey = 0;
  v5 = a1;
  if ( a2 && *a2 )
  {
    v6 = RegCreateKeyExW(a1, a2, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v6 )
      goto LABEL_5;
    a1 = hKey;
  }
  else
  {
    hKey = a1;
  }
  v6 = RegSetValueExW(a1, a3, 0, 4u, (const BYTE *)&Data, 4u);
  if ( hKey != v5 )
    RegCloseKey(hKey);
LABEL_5:
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180014b4c  mov     [rsp+arg_0], rbx
0x180014b51  mov     [rsp+Data], r9d
0x180014b56  push    rbp
0x180014b57  push    rsi
0x180014b58  push    rdi
0x180014b59  sub     rsp, 50h
0x180014b5d  xor     ebp, ebp
0x180014b5f  mov     rsi, r8
0x180014b62  mov     [rsp+68h+hKey], rbp
0x180014b67  mov     rdi, rcx
0x180014b6a  test    rdx, rdx
0x180014b6d  jnz     loc_180014C0F
0x180014b73  mov     [rsp+68h+hKey], rcx
0x180014b78  mov     r9d, 4; dwType
0x180014b7e  lea     rax, [rsp+68h+Data]
0x180014b86  mov     [rsp+68h+cbData], r9d; cbData
0x180014b8b  xor     r8d, r8d; Reserved
0x180014b8e  mov     rdx, rsi; lpValueName
0x180014b91  mov     [rsp+68h+lpData], rax; lpData
0x180014b96  call    cs:__imp_RegSetValueExW
0x180014b9d  nop     dword ptr [rax+rax+00h]
0x180014ba2  mov     rcx, [rsp+68h+hKey]; hKey
0x180014ba7  mov     ebx, eax
0x180014ba9  cmp     rcx, rdi
0x180014bac  jnz     short loc_180014C1A
0x180014bae  test    ebx, ebx
0x180014bb0  jg      short loc_180014BC2
0x180014bb2  mov     eax, ebx
0x180014bb4  mov     rbx, [rsp+68h+arg_0]
0x180014bb9  add     rsp, 50h
0x180014bbd  pop     rdi
0x180014bbe  pop     rsi
0x180014bbf  pop     rbp
0x180014bc0  retn
0x180014bc2  movzx   ebx, bx
0x180014bc5  or      ebx, 80070000h
0x180014bcb  jmp     short loc_180014BB2
0x180014bcd  mov     [rsp+68h+lpdwDisposition], rbp; lpdwDisposition
0x180014bd2  lea     rax, [rsp+68h+hKey]
0x180014bd7  mov     [rsp+68h+phkResult], rax; phkResult
0x180014bdc  xor     r9d, r9d; lpClass
0x180014bdf  mov     [rsp+68h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x180014be4  xor     r8d, r8d; Reserved
0x180014be7  mov     [rsp+68h+cbData], 2; samDesired
0x180014bef  mov     dword ptr [rsp+68h+lpData], ebp; dwOptions
0x180014bf3  call    cs:__imp_RegCreateKeyExW
0x180014bfa  nop     dword ptr [rax+rax+00h]
0x180014bff  mov     ebx, eax
0x180014c01  test    eax, eax
0x180014c03  jnz     short loc_180014BAE
0x180014c05  mov     rcx, [rsp+68h+hKey]
0x180014c0a  jmp     loc_180014B78
0x180014c0f  cmp     [rdx], bp
0x180014c12  jz      loc_180014B73
0x180014c18  jmp     short loc_180014BCD
0x180014c1a  call    cs:__imp_RegCloseKey
0x180014c21  nop     dword ptr [rax+rax+00h]
0x180014c26  jmp     short loc_180014BAE
```
