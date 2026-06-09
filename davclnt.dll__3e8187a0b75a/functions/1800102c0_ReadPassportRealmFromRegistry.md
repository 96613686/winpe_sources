# ReadPassportRealmFromRegistry

- ea: `0x1800102c0`
- end: `0x18001037d`
- name: `ReadPassportRealmFromRegistry`
- size: `189`
- prototype: `__int64 __fastcall(LPBYTE lpData, HKEY hKey)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ef88`

## callees

- `0x1800102c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010300`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010300`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001036d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001036d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010339`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010339`

## pseudocode

```c
__int64 __fastcall ReadPassportRealmFromRegistry(LPBYTE lpData, HKEY hKey)
{
  unsigned int v4; // ebx
  DWORD Type; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp+20h] BYREF

  hKeya = 0;
  if ( !lpData )
    return 0;
  v4 = 0;
  if ( !RegOpenKeyExW(
          hKey,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Passport",
          0,
          0x20019u,
          &hKeya) )
  {
    Type = 0;
    cbData = 512;
    if ( RegQueryValueExW(hKeya, L"LoginServerRealm", 0, &Type, lpData, &cbData) )
    {
      *(_WORD *)lpData = 0;
    }
    else
    {
      v4 = 1;
      if ( Type != 1 || cbData < 4 || *(_WORD *)&lpData[2 * ((unsigned __int64)(cbData - 1) >> 1)] )
        v4 = 0;
    }
    RegCloseKey(hKeya);
  }
  return v4;
}

```

## disassembly

```asm
0x1800102c0  push    rbx
0x1800102c2  push    rsi
0x1800102c3  push    rdi
0x1800102c4  sub     rsp, 30h
0x1800102c8  xor     esi, esi
0x1800102ca  mov     rax, rdx
0x1800102cd  mov     [rsp+48h+hKey], rsi
0x1800102d2  mov     rdi, rcx
0x1800102d5  test    rcx, rcx
0x1800102d8  jnz     short loc_1800102E1
0x1800102da  xor     eax, eax
0x1800102dc  jmp     loc_180010375
0x1800102e1  lea     rcx, [rsp+48h+hKey]
0x1800102e6  mov     r9d, 20019h; samDesired
0x1800102ec  mov     [rsp+48h+phkResult], rcx; phkResult
0x1800102f1  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800102f8  mov     rcx, rax; hKey
0x1800102fb  xor     r8d, r8d; ulOptions
0x1800102fe  mov     ebx, esi
0x180010300  call    cs:__imp_RegOpenKeyExW
0x180010306  test    eax, eax
0x180010308  jnz     short loc_180010373
0x18001030a  mov     rcx, [rsp+48h+hKey]; hKey
0x18001030f  lea     rax, [rsp+48h+cbData]
0x180010314  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180010319  lea     r9, [rsp+48h+Type]; lpType
0x18001031e  xor     r8d, r8d; lpReserved
0x180010321  mov     [rsp+48h+phkResult], rdi; lpData
0x180010326  lea     rdx, aLoginserverrea; "LoginServerRealm"
0x18001032d  mov     [rsp+48h+Type], esi
0x180010331  mov     [rsp+48h+cbData], 200h
0x180010339  call    cs:__imp_RegQueryValueExW
0x18001033f  test    eax, eax
0x180010341  jnz     short loc_180010365
0x180010343  lea     ebx, [rax+1]
0x180010346  cmp     [rsp+48h+Type], ebx
0x18001034a  jnz     short loc_180010361
0x18001034c  mov     eax, [rsp+48h+cbData]
0x180010350  cmp     eax, 4
0x180010353  jb      short loc_180010361
0x180010355  lea     ecx, [rax-1]
0x180010358  shr     rcx, 1
0x18001035b  cmp     [rdi+rcx*2], si
0x18001035f  jz      short loc_180010368
0x180010361  mov     ebx, esi
0x180010363  jmp     short loc_180010368
0x180010365  mov     [rdi], si
0x180010368  mov     rcx, [rsp+48h+hKey]; hKey
0x18001036d  call    cs:__imp_RegCloseKey
0x180010373  mov     eax, ebx
0x180010375  add     rsp, 30h
0x180010379  pop     rdi
0x18001037a  pop     rsi
0x18001037b  pop     rbx
0x18001037c  retn
```
