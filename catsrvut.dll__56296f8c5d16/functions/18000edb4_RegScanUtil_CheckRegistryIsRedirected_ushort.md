# RegScanUtil::CheckRegistryIsRedirected(ushort *)

- ea: `0x18000edb4`
- end: `0x18000eed0`
- name: `?CheckRegistryIsRedirected@RegScanUtil@@SAXPEAG@Z`
- size: `284`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000eaf8`

## callees

- `0x180005944`
- `0x18000edb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000edf7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000edf7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ee37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ee37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ee43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ee43`

## string_xrefs

- `0x18000ee6e`: `com\complus\src\comcat\regscan\regscanutil.cpp`

## pseudocode

```c
void __fastcall RegScanUtil::CheckRegistryIsRedirected(unsigned __int16 *a1)
{
  LSTATUS v2; // ebx
  HKEY hKey; // [rsp+30h] [rbp-40h] BYREF
  int v4; // [rsp+38h] [rbp-38h] BYREF
  __int16 v5; // [rsp+3Ch] [rbp-34h]
  int v6; // [rsp+40h] [rbp-30h]
  unsigned __int16 *v7; // [rsp+48h] [rbp-28h]
  __int64 v8; // [rsp+50h] [rbp-20h]
  __int64 v9; // [rsp+58h] [rbp-18h]
  int v10; // [rsp+60h] [rbp-10h]
  int v11; // [rsp+64h] [rbp-Ch]
  DWORD Type; // [rsp+98h] [rbp+28h] BYREF
  int Data; // [rsp+A0h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+A8h] [rbp+38h] BYREF

  if ( *(_DWORD *)&RegScanUtil::sm_dwCookie != -1 )
  {
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, L"REDIRECTED", 0, 0x20019u, &hKey)
      || !hKey
      || (Type = 0,
          Data = 0,
          cbData = 4,
          v2 = RegQueryValueExW(hKey, L"Cookie", 0, &Type, (LPBYTE)&Data, &cbData),
          RegCloseKey(hKey),
          v2)
      || Type != 4
      || Data != *(_DWORD *)&RegScanUtil::sm_dwCookie )
    {
      v4 = 0;
      v5 = 22;
      v6 = -2147479184;
      v8 = 0;
      if ( !a1 )
        a1 = (unsigned __int16 *)&Password;
      v9 = 0;
      v7 = a1;
      v10 = 0;
      v11 = 1;
      CError::WriteToLog((CError *)&v4, L"com\\complus\\src\\comcat\\regscan\\regscanutil.cpp", 0x390u, a1);
      *(_DWORD *)&RegScanUtil::sm_dwCookie = -1;
    }
  }
}

```

## disassembly

```asm
0x18000edb4  push    rbp
0x18000edb6  push    rbx
0x18000edb7  push    rdi
0x18000edb8  mov     rbp, rsp
0x18000edbb  sub     rsp, 70h
0x18000edbf  cmp     cs:?sm_dwCookie@RegScanUtil@@0KA, 0FFFFFFFFh; ulong RegScanUtil::sm_dwCookie
0x18000edc6  mov     rdi, rcx
0x18000edc9  jz      loc_18000EEC8
0x18000edcf  lea     rax, [rbp+hKey]
0x18000edd3  mov     [rbp+hKey], 0
0x18000eddb  mov     r9d, 20019h; samDesired
0x18000ede1  mov     [rsp+70h+phkResult], rax; phkResult
0x18000ede6  xor     r8d, r8d; ulOptions
0x18000ede9  lea     rdx, aRedirected; "REDIRECTED"
0x18000edf0  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000edf7  call    cs:__imp_RegOpenKeyExW
0x18000edfd  test    eax, eax
0x18000edff  jnz     short loc_18000EE5E
0x18000ee01  mov     rcx, [rbp+hKey]; hKey
0x18000ee05  test    rcx, rcx
0x18000ee08  jz      short loc_18000EE5E
0x18000ee0a  mov     [rbp+Type], eax
0x18000ee0d  lea     r9, [rbp+Type]; lpType
0x18000ee11  mov     [rbp+Data], eax
0x18000ee14  lea     rdx, ValueName; "Cookie"
0x18000ee1b  lea     rax, [rbp+cbData]
0x18000ee1f  mov     [rbp+cbData], 4
0x18000ee26  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18000ee2b  xor     r8d, r8d; lpReserved
0x18000ee2e  lea     rax, [rbp+Data]
0x18000ee32  mov     [rsp+70h+phkResult], rax; lpData
0x18000ee37  call    cs:__imp_RegQueryValueExW
0x18000ee3d  mov     rcx, [rbp+hKey]; hKey
0x18000ee41  mov     ebx, eax
0x18000ee43  call    cs:__imp_RegCloseKey
0x18000ee49  test    ebx, ebx
0x18000ee4b  jnz     short loc_18000EE5E
0x18000ee4d  cmp     [rbp+Type], 4
0x18000ee51  jnz     short loc_18000EE5E
0x18000ee53  mov     eax, cs:?sm_dwCookie@RegScanUtil@@0KA; ulong RegScanUtil::sm_dwCookie
0x18000ee59  cmp     [rbp+Data], eax
0x18000ee5c  jz      short loc_18000EEC8
0x18000ee5e  mov     eax, 16h
0x18000ee63  mov     [rbp+var_38], 0
0x18000ee6a  mov     [rbp+var_34], ax
0x18000ee6e  lea     rdx, aComComplusSrcC_2; "com\\complus\\src\\comcat\\regscan\\reg"...
0x18000ee75  test    rdi, rdi
0x18000ee78  mov     [rbp+var_30], 80001170h
0x18000ee7f  lea     rax, Password
0x18000ee86  mov     [rbp+var_20], 0
0x18000ee8e  cmovz   rdi, rax
0x18000ee92  mov     [rbp+var_18], 0
0x18000ee9a  mov     r9, rdi; unsigned __int16 *
0x18000ee9d  mov     [rbp+var_28], rdi
0x18000eea1  mov     r8d, 390h; unsigned int
0x18000eea7  mov     [rbp+var_10], 0
0x18000eeae  lea     rcx, [rbp+var_38]; this
0x18000eeb2  mov     [rbp+var_C], 1
0x18000eeb9  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000eebe  mov     cs:?sm_dwCookie@RegScanUtil@@0KA, 0FFFFFFFFh; ulong RegScanUtil::sm_dwCookie
0x18000eec8  add     rsp, 70h
0x18000eecc  pop     rdi
0x18000eecd  pop     rbx
0x18000eece  pop     rbp
0x18000eecf  retn
```
