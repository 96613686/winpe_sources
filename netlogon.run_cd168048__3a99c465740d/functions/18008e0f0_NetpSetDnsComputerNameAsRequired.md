# NetpSetDnsComputerNameAsRequired

- ea: `0x18008e0f0`
- end: `0x18008e236`
- name: `NetpSetDnsComputerNameAsRequired`
- size: `326`
- prototype: `__int64 __fastcall(LPCWSTR lpBuffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006e50c`

## callees

- `0x18008e0f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e20f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e20f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008e187`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008e187`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008e143`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008e143`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e1af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e1af`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x18008e1ff`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x18008e1ff`

## string_xrefs

- `0x18008e135`: `System\CurrentControlSet\Services\Tcpip\Parameters`

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
0x18008e0f0  push    rbp
0x18008e0f2  push    rbx
0x18008e0f3  push    rsi
0x18008e0f4  push    rdi
0x18008e0f5  push    r14
0x18008e0f7  push    r15
0x18008e0f9  mov     rbp, rsp
0x18008e0fc  sub     rsp, 38h
0x18008e100  xor     r14d, r14d
0x18008e103  mov     rsi, rcx
0x18008e106  mov     [rbp+hKey], r14
0x18008e10a  mov     [rbp+Type], r14d
0x18008e10e  mov     [rbp+Data], r14d
0x18008e112  mov     [rbp+cbData], r14d
0x18008e116  test    rcx, rcx
0x18008e119  jnz     short loc_18008E123
0x18008e11b  lea     eax, [rcx+57h]
0x18008e11e  jmp     loc_18008E228
0x18008e123  lea     rax, [rbp+hKey]
0x18008e127  mov     r9d, 1; samDesired
0x18008e12d  xor     r8d, r8d; ulOptions
0x18008e130  mov     [rsp+38h+phkResult], rax; phkResult
0x18008e135  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Tc"...
0x18008e13c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008e143  call    cs:__imp_RegOpenKeyExW
0x18008e14a  nop     dword ptr [rax+rax+00h]
0x18008e14f  mov     edi, eax
0x18008e151  test    eax, eax
0x18008e153  jnz     loc_18008E226
0x18008e159  mov     rcx, [rbp+hKey]; hKey
0x18008e15d  lea     rax, [rbp+cbData]
0x18008e161  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18008e166  lea     r9, [rbp+Type]; lpType
0x18008e16a  lea     rax, [rbp+Data]
0x18008e16e  mov     [rbp+cbData], 4
0x18008e175  xor     r8d, r8d; lpReserved
0x18008e178  mov     [rsp+38h+phkResult], rax; lpData
0x18008e17d  lea     rdx, aSyncdomainwith; "SyncDomainWithMembership"
0x18008e184  mov     bl, r14b
0x18008e187  call    cs:__imp_RegQueryValueExW
0x18008e18e  nop     dword ptr [rax+rax+00h]
0x18008e193  mov     edi, eax
0x18008e195  test    eax, eax
0x18008e197  jnz     short loc_18008E1A1
0x18008e199  cmp     [rbp+Data], 1
0x18008e19d  jnz     short loc_18008E1AB
0x18008e19f  jmp     short loc_18008E1A9
0x18008e1a1  cmp     eax, 2
0x18008e1a4  jnz     short loc_18008E1AB
0x18008e1a6  mov     edi, r14d
0x18008e1a9  mov     bl, 1
0x18008e1ab  mov     rcx, [rbp+hKey]; hKey
0x18008e1af  call    cs:__imp_RegCloseKey
0x18008e1b6  nop     dword ptr [rax+rax+00h]
0x18008e1bb  test    edi, edi
0x18008e1bd  jnz     short loc_18008E226
0x18008e1bf  cmp     bl, 1
0x18008e1c2  jnz     short loc_18008E226
0x18008e1c4  mov     rbx, r14
0x18008e1c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008e1cb  inc     rax
0x18008e1ce  cmp     [rsi+rax*2], r14w
0x18008e1d3  jnz     short loc_18008E1CB
0x18008e1d5  mov     r15d, 2Eh ; '.'
0x18008e1db  test    rax, rax
0x18008e1de  jz      short loc_18008E1F7
0x18008e1e0  lea     rbx, [rsi-2]
0x18008e1e4  lea     rbx, [rbx+rax*2]
0x18008e1e8  cmp     [rbx], r15w
0x18008e1ec  jnz     short loc_18008E1F4
0x18008e1ee  mov     [rbx], r14w
0x18008e1f2  jmp     short loc_18008E1F7
0x18008e1f4  mov     rbx, r14
0x18008e1f7  mov     rdx, rsi; lpBuffer
0x18008e1fa  mov     ecx, 6; NameType
0x18008e1ff  call    cs:__imp_SetComputerNameExW
0x18008e206  nop     dword ptr [rax+rax+00h]
0x18008e20b  test    eax, eax
0x18008e20d  jnz     short loc_18008E21D
0x18008e20f  call    cs:__imp_GetLastError
0x18008e216  nop     dword ptr [rax+rax+00h]
0x18008e21b  mov     edi, eax
0x18008e21d  test    rbx, rbx
0x18008e220  jz      short loc_18008E226
0x18008e222  mov     [rbx], r15w
0x18008e226  mov     eax, edi
0x18008e228  add     rsp, 38h
0x18008e22c  pop     r15
0x18008e22e  pop     r14
0x18008e230  pop     rdi
0x18008e231  pop     rsi
0x18008e232  pop     rbx
0x18008e233  pop     rbp
0x18008e234  retn
```
