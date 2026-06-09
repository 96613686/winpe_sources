# RegistryPath::OpenSubKey(ulong,int)

- ea: `0x18001ba8c`
- end: `0x18001bb75`
- name: `?OpenSubKey@RegistryPath@@QEAAKKH@Z`
- size: `233`
- prototype: `__int64 __fastcall(RegistryPath *this, REGSAM, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004218`
- `0x18009716c`
- `0x180097300`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x18001ba8c`
- `0x180043e54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bae1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bae1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001baae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bb67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001baae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bb67`

## string_xrefs

- `0x18001bb05`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18001bafe`: `RegistryPath::OpenSubKey`
- `0x18001bb20`: `RegistryPath::OpenSubKey`
- `0x18001bb49`: `RegistryPath::OpenSubKey`
- `0x18001bb38`: `RegOpenKeyExW`
- `0x18001bb53`: `%s: Failed to open registry key "%s". Error code: 0x%08x.`
- `0x18001bb27`: `%s: Registry key "%s" does not exist.`

## pseudocode

```c
__int64 __fastcall RegistryPath::OpenSubKey(RegistryPath *this, REGSAM a2, int a3)
{
  HKEY *phkResult; // rsi
  HKEY v5; // rcx
  HKEY v8; // rcx
  _WORD *v9; // rdx
  LSTATUS v10; // eax
  unsigned int v11; // ebx

  phkResult = (HKEY *)((char *)this + 40);
  v5 = (HKEY)*((_QWORD *)this + 5);
  if ( v5 )
    RegCloseKey(v5);
  *phkResult = 0;
  v8 = (HKEY)*((_QWORD *)this + 4);
  if ( !v8 || (v9 = *(_WORD **)this) == 0 || !*v9 )
  {
    Logger::TraceError(
      L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
      L"RegistryPath::OpenSubKey");
    return 87;
  }
  v10 = RegOpenKeyExW(v8, &v9[*((_QWORD *)this + 3)], 0, a2, phkResult);
  v11 = v10;
  if ( a3 || v10 != 2 )
  {
    if ( !v10 )
      return v11;
    Logger::WriteRegistryFailureEvent(v10, L"RegOpenKeyExW", *(const unsigned __int16 **)this);
    Logger::TraceError(
      L"%s: Failed to open registry key \"%s\". Error code: 0x%08x.",
      L"RegistryPath::OpenSubKey",
      *(_QWORD *)this,
      v11);
  }
  else
  {
    Logger::TraceVerbose(
      (wchar_t *)L"%s: Registry key \"%s\" does not exist.",
      L"RegistryPath::OpenSubKey",
      *(_QWORD *)this);
  }
  if ( *phkResult )
  {
    RegCloseKey(*phkResult);
    *phkResult = 0;
  }
  return v11;
}

```

## disassembly

```asm
0x18001ba8c  push    rbx
0x18001ba8e  push    rbp
0x18001ba8f  push    rsi
0x18001ba90  push    rdi
0x18001ba91  push    r14
0x18001ba93  sub     rsp, 30h
0x18001ba97  lea     rsi, [rcx+28h]
0x18001ba9b  mov     rdi, rcx
0x18001ba9e  mov     rcx, [rsi]; hKey
0x18001baa1  xor     r14d, r14d
0x18001baa4  mov     ebp, r8d
0x18001baa7  mov     ebx, edx
0x18001baa9  test    rcx, rcx
0x18001baac  jz      short loc_18001BAB4
0x18001baae  call    cs:__imp_RegCloseKey
0x18001bab4  mov     [rsi], r14
0x18001bab7  mov     rcx, [rdi+20h]; hKey
0x18001babb  test    rcx, rcx
0x18001babe  jz      short loc_18001BAFE
0x18001bac0  mov     rdx, [rdi]
0x18001bac3  test    rdx, rdx
0x18001bac6  jz      short loc_18001BAFE
0x18001bac8  cmp     [rdx], r14w
0x18001bacc  jz      short loc_18001BAFE
0x18001bace  mov     rax, [rdi+18h]
0x18001bad2  mov     r9d, ebx; samDesired
0x18001bad5  xor     r8d, r8d; ulOptions
0x18001bad8  mov     [rsp+58h+phkResult], rsi; phkResult
0x18001badd  lea     rdx, [rdx+rax*2]; lpSubKey
0x18001bae1  call    cs:__imp_RegOpenKeyExW
0x18001bae7  mov     ebx, eax
0x18001bae9  test    ebp, ebp
0x18001baeb  jz      short loc_18001BB18
0x18001baed  test    ebx, ebx
0x18001baef  jnz     short loc_18001BB35
0x18001baf1  mov     eax, ebx
0x18001baf3  add     rsp, 30h
0x18001baf7  pop     r14
0x18001baf9  pop     rdi
0x18001bafa  pop     rsi
0x18001bafb  pop     rbp
0x18001bafc  pop     rbx
0x18001bafd  retn
0x18001bafe  lea     rdx, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x18001bb05  lea     rcx, aSThisPathObjec; "%s: This path object has not been prope"...
0x18001bb0c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001bb11  mov     ebx, 57h ; 'W'
0x18001bb16  jmp     short loc_18001BAF1
0x18001bb18  cmp     ebx, 2
0x18001bb1b  jnz     short loc_18001BAED
0x18001bb1d  mov     r8, [rdi]
0x18001bb20  lea     rdx, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x18001bb27  lea     rcx, aSRegistryKeySD; "%s: Registry key \"%s\" does not exist."
0x18001bb2e  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18001bb33  jmp     short loc_18001BB5F
0x18001bb35  mov     r8, [rdi]; unsigned __int16 *
0x18001bb38  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18001bb3f  mov     ecx, ebx; unsigned int
0x18001bb41  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x18001bb46  mov     r8, [rdi]
0x18001bb49  lea     rdx, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x18001bb50  mov     r9d, ebx
0x18001bb53  lea     rcx, aSFailedToOpenR; "%s: Failed to open registry key \"%s\"."...
0x18001bb5a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001bb5f  mov     rcx, [rsi]; hKey
0x18001bb62  test    rcx, rcx
0x18001bb65  jz      short loc_18001BAF1
0x18001bb67  call    cs:__imp_RegCloseKey
0x18001bb6d  mov     [rsi], r14
0x18001bb70  jmp     loc_18001BAF1
```
