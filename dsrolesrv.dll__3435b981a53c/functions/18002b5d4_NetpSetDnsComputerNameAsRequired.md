# NetpSetDnsComputerNameAsRequired

- ea: `0x18002b5d4`
- end: `0x18002b6fb`
- name: `NetpSetDnsComputerNameAsRequired`
- size: `295`
- prototype: `__int64 __fastcall(LPCWSTR lpBuffer)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011240`
- `0x180012460`

## callees

- `0x18002b5d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b665`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b665`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b627`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b627`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b687`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6db`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x18002b6d1`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x18002b6d1`

## string_xrefs

- `0x18002b619`: `System\CurrentControlSet\Services\Tcpip\Parameters`

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
0x18002b5d4  push    rbp
0x18002b5d6  push    rbx
0x18002b5d7  push    rsi
0x18002b5d8  push    rdi
0x18002b5d9  push    r14
0x18002b5db  push    r15
0x18002b5dd  mov     rbp, rsp
0x18002b5e0  sub     rsp, 38h
0x18002b5e4  xor     r14d, r14d
0x18002b5e7  mov     rsi, rcx
0x18002b5ea  mov     [rbp+hKey], r14
0x18002b5ee  mov     [rbp+Type], r14d
0x18002b5f2  mov     [rbp+Data], r14d
0x18002b5f6  mov     [rbp+cbData], r14d
0x18002b5fa  test    rcx, rcx
0x18002b5fd  jnz     short loc_18002B607
0x18002b5ff  lea     eax, [rcx+57h]
0x18002b602  jmp     loc_18002B6EE
0x18002b607  lea     rax, [rbp+hKey]
0x18002b60b  mov     r9d, 1; samDesired
0x18002b611  xor     r8d, r8d; ulOptions
0x18002b614  mov     [rsp+38h+phkResult], rax; phkResult
0x18002b619  lea     rdx, aSystemCurrentc_13; "System\\CurrentControlSet\\Services\\Tc"...
0x18002b620  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b627  call    cs:__imp_RegOpenKeyExW
0x18002b62d  mov     edi, eax
0x18002b62f  test    eax, eax
0x18002b631  jnz     loc_18002B6EC
0x18002b637  mov     rcx, [rbp+hKey]; hKey
0x18002b63b  lea     rax, [rbp+cbData]
0x18002b63f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002b644  lea     r9, [rbp+Type]; lpType
0x18002b648  lea     rax, [rbp+Data]
0x18002b64c  mov     [rbp+cbData], 4
0x18002b653  xor     r8d, r8d; lpReserved
0x18002b656  mov     [rsp+38h+phkResult], rax; lpData
0x18002b65b  lea     rdx, aSyncdomainwith; "SyncDomainWithMembership"
0x18002b662  mov     bl, r14b
0x18002b665  call    cs:__imp_RegQueryValueExW
0x18002b66b  mov     edi, eax
0x18002b66d  test    eax, eax
0x18002b66f  jnz     short loc_18002B679
0x18002b671  cmp     [rbp+Data], 1
0x18002b675  jnz     short loc_18002B683
0x18002b677  jmp     short loc_18002B681
0x18002b679  cmp     eax, 2
0x18002b67c  jnz     short loc_18002B683
0x18002b67e  mov     edi, r14d
0x18002b681  mov     bl, 1
0x18002b683  mov     rcx, [rbp+hKey]; hKey
0x18002b687  call    cs:__imp_RegCloseKey
0x18002b68d  test    edi, edi
0x18002b68f  jnz     short loc_18002B6EC
0x18002b691  cmp     bl, 1
0x18002b694  jnz     short loc_18002B6EC
0x18002b696  mov     rbx, r14
0x18002b699  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b69d  inc     rax
0x18002b6a0  cmp     [rsi+rax*2], r14w
0x18002b6a5  jnz     short loc_18002B69D
0x18002b6a7  mov     r15d, 2Eh ; '.'
0x18002b6ad  test    rax, rax
0x18002b6b0  jz      short loc_18002B6C9
0x18002b6b2  lea     rbx, [rsi-2]
0x18002b6b6  lea     rbx, [rbx+rax*2]
0x18002b6ba  cmp     [rbx], r15w
0x18002b6be  jnz     short loc_18002B6C6
0x18002b6c0  mov     [rbx], r14w
0x18002b6c4  jmp     short loc_18002B6C9
0x18002b6c6  mov     rbx, r14
0x18002b6c9  mov     rdx, rsi; lpBuffer
0x18002b6cc  mov     ecx, 6; NameType
0x18002b6d1  call    cs:__imp_SetComputerNameExW
0x18002b6d7  test    eax, eax
0x18002b6d9  jnz     short loc_18002B6E3
0x18002b6db  call    cs:__imp_GetLastError
0x18002b6e1  mov     edi, eax
0x18002b6e3  test    rbx, rbx
0x18002b6e6  jz      short loc_18002B6EC
0x18002b6e8  mov     [rbx], r15w
0x18002b6ec  mov     eax, edi
0x18002b6ee  add     rsp, 38h
0x18002b6f2  pop     r15
0x18002b6f4  pop     r14
0x18002b6f6  pop     rdi
0x18002b6f7  pop     rsi
0x18002b6f8  pop     rbx
0x18002b6f9  pop     rbp
0x18002b6fa  retn
```
