# WriteCacheOpts

- ea: `0x180010364`
- end: `0x18001056e`
- name: `WriteCacheOpts`
- size: `522`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010bec`

## callees

- `0x180010364`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800103e1`
- `msvcrt!wcscat_s` at `0x1800103e1`
- `msvcrt!wcscpy_s` at `0x1800103c4`
- `msvcrt!wcscpy_s` at `0x1800103c4`
- `ADVAPI32!RegCreateKeyExW` at `0x180010428`
- `ADVAPI32!RegCreateKeyExW` at `0x180010428`
- `ADVAPI32!RegSetValueExW` at `0x18001046e`
- `ADVAPI32!RegSetValueExW` at `0x1800104a7`
- `ADVAPI32!RegSetValueExW` at `0x1800104d5`
- `ADVAPI32!RegSetValueExW` at `0x180010503`
- `ADVAPI32!RegSetValueExW` at `0x18001052e`
- `ADVAPI32!RegSetValueExW` at `0x18001046e`
- `ADVAPI32!RegSetValueExW` at `0x1800104a7`
- `ADVAPI32!RegSetValueExW` at `0x1800104d5`
- `ADVAPI32!RegSetValueExW` at `0x180010503`
- `ADVAPI32!RegSetValueExW` at `0x18001052e`
- `ADVAPI32!RegCloseKey` at `0x18001053f`
- `ADVAPI32!RegCloseKey` at `0x18001053f`

## string_xrefs

- `0x1800103d0`: `\Cache`
- `0x18001043f`: `FileAttributeCache`
- `0x18001047d`: `RemoteWriteCache`
- `0x18001051c`: `CacheBlocks`

## pseudocode

```c
LSTATUS __fastcall WriteCacheOpts(HKEY hKey, wchar_t *Source, const BYTE *a3)
{
  __int64 v3; // rsi
  LSTATUS result; // eax
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition[4]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Destination[264]; // [rsp+70h] [rbp-90h] BYREF

  v3 = *(_QWORD *)a3;
  *(_DWORD *)Data = 0;
  dwDisposition[0] = 0;
  hKeya = 0;
  Destination[259] = 0;
  wcscpy_s(Destination, 0x104u, Source);
  wcscat_s(Destination, 0x104u, L"\\Cache");
  result = RegCreateKeyExW(hKey, Destination, 0, 0, 0, 0xF003Fu, 0, &hKeya, dwDisposition);
  if ( !result )
  {
    *(_DWORD *)Data = (*(_DWORD *)(v3 + 56) >> 4) & 1;
    RegSetValueExW(hKeya, L"FileAttributeCache", 0, 4u, Data, 4u);
    *(_DWORD *)Data = (*(_DWORD *)(v3 + 56) >> 3) & 1;
    RegSetValueExW(hKeya, L"RemoteWriteCache", 0, 4u, Data, 4u);
    RegSetValueExW(hKeya, L"HashTableSize", 0, 4u, (const BYTE *)(*(_QWORD *)a3 + 40LL), 4u);
    RegSetValueExW(hKeya, L"AttributeTimeDelta", 0, 4u, (const BYTE *)(*(_QWORD *)a3 + 48LL), 4u);
    RegSetValueExW(hKeya, L"CacheBlocks", 0, 4u, a3 + 32, 4u);
    return RegCloseKey(hKeya);
  }
  return result;
}

```

## disassembly

```asm
0x180010364  mov     [rsp-8+arg_18], rbx
0x180010369  push    rbp
0x18001036a  push    rsi
0x18001036b  push    rdi
0x18001036c  lea     rbp, [rsp-190h]
0x180010374  sub     rsp, 290h
0x18001037b  mov     rax, cs:__security_cookie
0x180010382  xor     rax, rsp
0x180010385  mov     [rbp+1A0h+var_20], rax
0x18001038c  mov     rsi, [r8]
0x18001038f  mov     rdi, r8
0x180010392  mov     r8, rdx; Source
0x180010395  mov     dword ptr [rsp+2A0h+Data], 0
0x18001039d  mov     rbx, rcx
0x1800103a0  mov     [rsp+2A0h+dwDisposition], 0
0x1800103a8  xor     eax, eax
0x1800103aa  mov     [rsp+2A0h+hKey], 0
0x1800103b3  mov     edx, 104h; SizeInWords
0x1800103b8  mov     [rbp+1A0h+var_2A], ax
0x1800103bf  lea     rcx, [rsp+2A0h+Destination]; Destination
0x1800103c4  call    cs:__imp_wcscpy_s
0x1800103cb  nop     dword ptr [rax+rax+00h]
0x1800103d0  lea     r8, aCache; "\\Cache"
0x1800103d7  mov     edx, 104h; SizeInWords
0x1800103dc  lea     rcx, [rsp+2A0h+Destination]; Destination
0x1800103e1  call    cs:__imp_wcscat_s
0x1800103e8  nop     dword ptr [rax+rax+00h]
0x1800103ed  lea     rax, [rsp+2A0h+dwDisposition]
0x1800103f2  xor     r9d, r9d; lpClass
0x1800103f5  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x1800103fa  lea     rdx, [rsp+2A0h+Destination]; lpSubKey
0x1800103ff  lea     rax, [rsp+2A0h+hKey]
0x180010404  xor     r8d, r8d; Reserved
0x180010407  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18001040c  mov     rcx, rbx; hKey
0x18001040f  mov     [rsp+2A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180010418  mov     [rsp+2A0h+samDesired], 0F003Fh; samDesired
0x180010420  mov     [rsp+2A0h+dwOptions], 0; dwOptions
0x180010428  call    cs:__imp_RegCreateKeyExW
0x18001042f  nop     dword ptr [rax+rax+00h]
0x180010434  test    eax, eax
0x180010436  jnz     loc_18001054B
0x18001043c  mov     eax, [rsi+38h]
0x18001043f  lea     rdx, aFileattributec; "FileAttributeCache"
0x180010446  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001044b  mov     ebx, 4
0x180010450  shr     eax, 4
0x180010453  mov     r9d, ebx; dwType
0x180010456  and     eax, 1
0x180010459  mov     [rsp+2A0h+samDesired], ebx; cbData
0x18001045d  mov     dword ptr [rsp+2A0h+Data], eax
0x180010461  xor     r8d, r8d; Reserved
0x180010464  lea     rax, [rsp+2A0h+Data]
0x180010469  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x18001046e  call    cs:__imp_RegSetValueExW
0x180010475  nop     dword ptr [rax+rax+00h]
0x18001047a  mov     eax, [rsi+38h]
0x18001047d  lea     rdx, aRemotewritecac; "RemoteWriteCache"
0x180010484  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180010489  mov     r9d, ebx; dwType
0x18001048c  shr     eax, 3
0x18001048f  xor     r8d, r8d; Reserved
0x180010492  and     eax, 1
0x180010495  mov     [rsp+2A0h+samDesired], ebx; cbData
0x180010499  mov     dword ptr [rsp+2A0h+Data], eax
0x18001049d  lea     rax, [rsp+2A0h+Data]
0x1800104a2  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x1800104a7  call    cs:__imp_RegSetValueExW
0x1800104ae  nop     dword ptr [rax+rax+00h]
0x1800104b3  mov     rax, [rdi]
0x1800104b6  lea     rdx, aHashtablesize; "HashTableSize"
0x1800104bd  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800104c2  add     rax, 28h ; '('
0x1800104c6  mov     [rsp+2A0h+samDesired], ebx; cbData
0x1800104ca  mov     r9d, ebx; dwType
0x1800104cd  xor     r8d, r8d; Reserved
0x1800104d0  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x1800104d5  call    cs:__imp_RegSetValueExW
0x1800104dc  nop     dword ptr [rax+rax+00h]
0x1800104e1  mov     rax, [rdi]
0x1800104e4  lea     rdx, aAttributetimed; "AttributeTimeDelta"
0x1800104eb  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800104f0  add     rax, 30h ; '0'
0x1800104f4  mov     [rsp+2A0h+samDesired], ebx; cbData
0x1800104f8  mov     r9d, ebx; dwType
0x1800104fb  xor     r8d, r8d; Reserved
0x1800104fe  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x180010503  call    cs:__imp_RegSetValueExW
0x18001050a  nop     dword ptr [rax+rax+00h]
0x18001050f  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180010514  lea     rax, [rdi+20h]
0x180010518  mov     [rsp+2A0h+samDesired], ebx; cbData
0x18001051c  lea     rdx, aCacheblocks; "CacheBlocks"
0x180010523  mov     r9d, ebx; dwType
0x180010526  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x18001052b  xor     r8d, r8d; Reserved
0x18001052e  call    cs:__imp_RegSetValueExW
0x180010535  nop     dword ptr [rax+rax+00h]
0x18001053a  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001053f  call    cs:__imp_RegCloseKey
0x180010546  nop     dword ptr [rax+rax+00h]
0x18001054b  mov     rcx, [rbp+1A0h+var_20]
0x180010552  xor     rcx, rsp; StackCookie
0x180010555  call    __security_check_cookie
0x18001055a  mov     rbx, [rsp+2A0h+arg_18]
0x180010562  add     rsp, 290h
0x180010569  pop     rdi
0x18001056a  pop     rsi
0x18001056b  pop     rbp
0x18001056c  retn
```
