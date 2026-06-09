# CheckForSetup(void)

- ea: `0x18001b520`
- end: `0x18001b5d5`
- name: `?CheckForSetup@@YAJXZ`
- size: `181`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180025990`

## callees

- `0x18001b520`

## import_xrefs

- `ADVAPI32!RegQueryValueExA` at `0x18001b596`
- `ADVAPI32!RegQueryValueExA` at `0x18001b596`
- `ADVAPI32!RegOpenKeyA` at `0x18001b559`
- `ADVAPI32!RegOpenKeyA` at `0x18001b559`
- `ADVAPI32!RegCloseKey` at `0x18001b5c6`
- `ADVAPI32!RegCloseKey` at `0x18001b5c6`

## string_xrefs

- `0x18001b58a`: `CurrentInstallState`

## pseudocode

```c
__int64 CheckForSetup(void)
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  bool v2; // cc
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+30h] BYREF

  phkResult = 0;
  Data = 0;
  Type = 0;
  cbData = 4;
  v0 = RegOpenKeyA(HKEY_LOCAL_MACHINE, "SOFTWARE\\Microsoft\\InetStp", &phkResult);
  v1 = v0;
  v2 = v0 <= 0;
  if ( v0
    || (v0 = RegQueryValueExA(phkResult, "CurrentInstallState", 0, &Type, (LPBYTE)&Data, &cbData),
        v1 = v0,
        v2 = v0 <= 0,
        v0) )
  {
    if ( !v2 )
      v1 = (unsigned __int16)v0 | 0x80070000;
  }
  else if ( Type == 4 && cbData == 4 )
  {
    v1 = (Data & 1) == 0;
  }
  else
  {
    v1 = -2147467259;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return v1;
}

```

## disassembly

```asm
0x18001b520  push    rbp
0x18001b522  push    rbx
0x18001b523  mov     rbp, rsp
0x18001b526  sub     rsp, 38h
0x18001b52a  lea     r8, [rbp+phkResult]; phkResult
0x18001b52e  mov     [rbp+phkResult], 0
0x18001b536  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\InetStp"
0x18001b53d  mov     [rbp+Data], 0
0x18001b544  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b54b  mov     [rbp+Type], 0
0x18001b552  mov     [rbp+cbData], 4
0x18001b559  call    cs:__imp_RegOpenKeyA
0x18001b55f  mov     ebx, eax
0x18001b561  test    eax, eax
0x18001b563  jz      short loc_18001B572
0x18001b565  jle     short loc_18001B5BD
0x18001b567  movzx   ebx, ax
0x18001b56a  or      ebx, 80070000h
0x18001b570  jmp     short loc_18001B5BD
0x18001b572  mov     rcx, [rbp+phkResult]; hKey
0x18001b576  lea     rax, [rbp+cbData]
0x18001b57a  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18001b57f  lea     r9, [rbp+Type]; lpType
0x18001b583  lea     rax, [rbp+Data]
0x18001b587  xor     r8d, r8d; lpReserved
0x18001b58a  lea     rdx, aCurrentinstall; "CurrentInstallState"
0x18001b591  mov     [rsp+38h+lpData], rax; lpData
0x18001b596  call    cs:__imp_RegQueryValueExA
0x18001b59c  mov     ebx, eax
0x18001b59e  test    eax, eax
0x18001b5a0  jnz     short loc_18001B565
0x18001b5a2  cmp     [rbp+Type], 4
0x18001b5a6  jnz     short loc_18001B5B8
0x18001b5a8  cmp     [rbp+cbData], 4
0x18001b5ac  jnz     short loc_18001B5B8
0x18001b5ae  mov     ebx, [rbp+Data]
0x18001b5b1  not     ebx
0x18001b5b3  and     ebx, 1
0x18001b5b6  jmp     short loc_18001B5BD
0x18001b5b8  mov     ebx, 80004005h
0x18001b5bd  mov     rcx, [rbp+phkResult]; hKey
0x18001b5c1  test    rcx, rcx
0x18001b5c4  jz      short loc_18001B5CC
0x18001b5c6  call    cs:__imp_RegCloseKey
0x18001b5cc  mov     eax, ebx
0x18001b5ce  add     rsp, 38h
0x18001b5d2  pop     rbx
0x18001b5d3  pop     rbp
0x18001b5d4  retn
```
