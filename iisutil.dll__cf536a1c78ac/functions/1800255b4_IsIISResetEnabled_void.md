# IsIISResetEnabled(void)

- ea: `0x1800255b4`
- end: `0x180025666`
- name: `?IsIISResetEnabled@@YAHXZ`
- size: `178`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024db4`

## callees

- `0x1800255b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800255ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800255ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025650`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025650`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025628`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025628`

## pseudocode

```c
__int64 IsIISResetEnabled(void)
{
  unsigned int v0; // ebx
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v0 = 0;
  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\INetStp", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"EnableRestart", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
      v0 = 1;
    else
      LOBYTE(v0) = Data == 1;
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x1800255b4  push    rbp
0x1800255b6  push    rbx
0x1800255b7  mov     rbp, rsp
0x1800255ba  sub     rsp, 38h
0x1800255be  xor     ebx, ebx
0x1800255c0  lea     rax, [rbp+hKey]
0x1800255c4  mov     r9d, 20019h; samDesired
0x1800255ca  mov     [rbp+hKey], rbx
0x1800255ce  xor     r8d, r8d; ulOptions
0x1800255d1  mov     [rbp+Data], ebx
0x1800255d4  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\INetStp"
0x1800255db  mov     [rbp+Type], ebx
0x1800255de  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800255e5  mov     [rbp+cbData], ebx
0x1800255e8  mov     [rsp+38h+phkResult], rax; phkResult
0x1800255ed  call    cs:__imp_RegOpenKeyExW
0x1800255f4  nop     dword ptr [rax+rax+00h]
0x1800255f9  test    eax, eax
0x1800255fb  jnz     short loc_18002565C
0x1800255fd  mov     rcx, [rbp+hKey]; hKey
0x180025601  lea     rax, [rbp+cbData]
0x180025605  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002560a  lea     r9, [rbp+Type]; lpType
0x18002560e  lea     rax, [rbp+Data]
0x180025612  mov     [rbp+cbData], 4
0x180025619  xor     r8d, r8d; lpReserved
0x18002561c  mov     [rsp+38h+phkResult], rax; lpData
0x180025621  lea     rdx, aEnablerestart; "EnableRestart"
0x180025628  call    cs:__imp_RegQueryValueExW
0x18002562f  nop     dword ptr [rax+rax+00h]
0x180025634  test    eax, eax
0x180025636  jnz     short loc_180025647
0x180025638  cmp     [rbp+Type], 4
0x18002563c  jnz     short loc_180025647
0x18002563e  cmp     [rbp+Data], 1
0x180025642  setz    bl
0x180025645  jmp     short loc_18002564C
0x180025647  mov     ebx, 1
0x18002564c  mov     rcx, [rbp+hKey]; hKey
0x180025650  call    cs:__imp_RegCloseKey
0x180025657  nop     dword ptr [rax+rax+00h]
0x18002565c  mov     eax, ebx
0x18002565e  add     rsp, 38h
0x180025662  pop     rbx
0x180025663  pop     rbp
0x180025664  retn
```
