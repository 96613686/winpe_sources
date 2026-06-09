# NetpSetDnsComputerNameAsRequired

- ea: `0x180087b8c`
- end: `0x180087cb3`
- name: `NetpSetDnsComputerNameAsRequired`
- size: `295`
- prototype: `__int64 __fastcall(LPCWSTR lpBuffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180069580`

## callees

- `0x180087b8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087c93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087c93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180087c1d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180087c1d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087bdf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087bdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180087c3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180087c3f`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x180087c89`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x180087c89`

## string_xrefs

- `0x180087bd1`: `System\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
__int64 __fastcall NetpSetDnsComputerNameAsRequired(LPCWSTR lpBuffer)
{
  DWORD LastError; // edi
  char v4; // bl
  LSTATUS v5; // eax
  WCHAR *v6; // rbx
  __int64 v7; // rax
  DWORD cbData; // [rsp+70h] [rbp+38h] BYREF
  int Data; // [rsp+78h] [rbp+40h] BYREF
  DWORD Type; // [rsp+80h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+50h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  if ( !lpBuffer )
    return 87;
  LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters", 0, 1u, &hKey);
  if ( !LastError )
  {
    cbData = 4;
    v4 = 0;
    v5 = RegQueryValueExW(hKey, L"SyncDomainWithMembership", 0, &Type, (LPBYTE)&Data, &cbData);
    LastError = v5;
    if ( v5 )
    {
      if ( v5 == 2 )
      {
        LastError = 0;
LABEL_9:
        v4 = 1;
      }
    }
    else if ( Data == 1 )
    {
      goto LABEL_9;
    }
    RegCloseKey(hKey);
    if ( !LastError && v4 == 1 )
    {
      v6 = 0;
      v7 = -1;
      do
        ++v7;
      while ( lpBuffer[v7] );
      if ( v7 )
      {
        v6 = (WCHAR *)&lpBuffer[v7 - 1];
        if ( *v6 == 46 )
          *v6 = 0;
        else
          v6 = 0;
      }
      if ( !SetComputerNameExW(ComputerNamePhysicalDnsDomain, lpBuffer) )
        LastError = GetLastError();
      if ( v6 )
        *v6 = 46;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180087b8c  push    rbp
0x180087b8e  push    rbx
0x180087b8f  push    rsi
0x180087b90  push    rdi
0x180087b91  push    r14
0x180087b93  push    r15
0x180087b95  mov     rbp, rsp
0x180087b98  sub     rsp, 38h
0x180087b9c  xor     r14d, r14d
0x180087b9f  mov     rsi, rcx
0x180087ba2  mov     [rbp+hKey], r14
0x180087ba6  mov     [rbp+Type], r14d
0x180087baa  mov     [rbp+Data], r14d
0x180087bae  mov     [rbp+cbData], r14d
0x180087bb2  test    rcx, rcx
0x180087bb5  jnz     short loc_180087BBF
0x180087bb7  lea     eax, [rcx+57h]
0x180087bba  jmp     loc_180087CA6
0x180087bbf  lea     rax, [rbp+hKey]
0x180087bc3  mov     r9d, 1; samDesired
0x180087bc9  xor     r8d, r8d; ulOptions
0x180087bcc  mov     [rsp+38h+phkResult], rax; phkResult
0x180087bd1  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Tc"...
0x180087bd8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180087bdf  call    cs:__imp_RegOpenKeyExW
0x180087be5  mov     edi, eax
0x180087be7  test    eax, eax
0x180087be9  jnz     loc_180087CA4
0x180087bef  mov     rcx, [rbp+hKey]; hKey
0x180087bf3  lea     rax, [rbp+cbData]
0x180087bf7  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180087bfc  lea     r9, [rbp+Type]; lpType
0x180087c00  lea     rax, [rbp+Data]
0x180087c04  mov     [rbp+cbData], 4
0x180087c0b  xor     r8d, r8d; lpReserved
0x180087c0e  mov     [rsp+38h+phkResult], rax; lpData
0x180087c13  lea     rdx, aSyncdomainwith; "SyncDomainWithMembership"
0x180087c1a  mov     bl, r14b
0x180087c1d  call    cs:__imp_RegQueryValueExW
0x180087c23  mov     edi, eax
0x180087c25  test    eax, eax
0x180087c27  jnz     short loc_180087C31
0x180087c29  cmp     [rbp+Data], 1
0x180087c2d  jnz     short loc_180087C3B
0x180087c2f  jmp     short loc_180087C39
0x180087c31  cmp     eax, 2
0x180087c34  jnz     short loc_180087C3B
0x180087c36  mov     edi, r14d
0x180087c39  mov     bl, 1
0x180087c3b  mov     rcx, [rbp+hKey]; hKey
0x180087c3f  call    cs:__imp_RegCloseKey
0x180087c45  test    edi, edi
0x180087c47  jnz     short loc_180087CA4
0x180087c49  cmp     bl, 1
0x180087c4c  jnz     short loc_180087CA4
0x180087c4e  mov     rbx, r14
0x180087c51  or      rax, 0FFFFFFFFFFFFFFFFh
0x180087c55  inc     rax
0x180087c58  cmp     [rsi+rax*2], r14w
0x180087c5d  jnz     short loc_180087C55
0x180087c5f  mov     r15d, 2Eh ; '.'
0x180087c65  test    rax, rax
0x180087c68  jz      short loc_180087C81
0x180087c6a  lea     rbx, [rsi-2]
0x180087c6e  lea     rbx, [rbx+rax*2]
0x180087c72  cmp     [rbx], r15w
0x180087c76  jnz     short loc_180087C7E
0x180087c78  mov     [rbx], r14w
0x180087c7c  jmp     short loc_180087C81
0x180087c7e  mov     rbx, r14
0x180087c81  mov     rdx, rsi; lpBuffer
0x180087c84  mov     ecx, 6; NameType
0x180087c89  call    cs:__imp_SetComputerNameExW
0x180087c8f  test    eax, eax
0x180087c91  jnz     short loc_180087C9B
0x180087c93  call    cs:__imp_GetLastError
0x180087c99  mov     edi, eax
0x180087c9b  test    rbx, rbx
0x180087c9e  jz      short loc_180087CA4
0x180087ca0  mov     [rbx], r15w
0x180087ca4  mov     eax, edi
0x180087ca6  add     rsp, 38h
0x180087caa  pop     r15
0x180087cac  pop     r14
0x180087cae  pop     rdi
0x180087caf  pop     rsi
0x180087cb0  pop     rbx
0x180087cb1  pop     rbp
0x180087cb2  retn
```
