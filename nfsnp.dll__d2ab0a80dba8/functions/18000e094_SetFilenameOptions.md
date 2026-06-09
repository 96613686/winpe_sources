# SetFilenameOptions

- ea: `0x18000e094`
- end: `0x18000e1e7`
- name: `SetFilenameOptions`
- size: `339`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000be24`
- `0x18000e454`

## callees

- `0x18000e094`
- `0x180011b62`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x18000e11a`
- `msvcrt!_snwprintf_s` at `0x18000e11a`
- `KERNEL32!GlobalFree` at `0x18000e1b3`
- `KERNEL32!GlobalFree` at `0x18000e1b3`
- `KERNEL32!GlobalAlloc` at `0x18000e0cd`
- `KERNEL32!GlobalAlloc` at `0x18000e0cd`
- `ADVAPI32!RegCloseKey` at `0x18000e1aa`
- `ADVAPI32!RegCloseKey` at `0x18000e1aa`
- `ADVAPI32!RegQueryValueExW` at `0x18000e170`
- `ADVAPI32!RegQueryValueExW` at `0x18000e1a0`
- `ADVAPI32!RegQueryValueExW` at `0x18000e170`
- `ADVAPI32!RegQueryValueExW` at `0x18000e1a0`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e13c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e13c`

## string_xrefs

- `0x18000e183`: `NFSReaddir`

## pseudocode

```c
int __fastcall SetFilenameOptions(__int64 a1, __int64 a2, __int64 a3)
{
  wchar_t *v4; // rax
  wchar_t *v5; // rdi
  int v6; // eax
  unsigned int v7; // eax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+60h] [rbp+20h] BYREF
  int v11; // [rsp+64h] [rbp+24h]
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  int v13; // [rsp+6Ch] [rbp+2Ch]
  int v14; // [rsp+78h] [rbp+38h] BYREF

  v13 = HIDWORD(a2);
  v11 = HIDWORD(a1);
  hKey = 0;
  Data = 1;
  v14 = 1;
  cbData = 0;
  v4 = (wchar_t *)GlobalAlloc(0x40u, 0x8Cu);
  v5 = v4;
  if ( v4 )
  {
    memset_0(v4, 0, 0x8Cu);
    _snwprintf_s(
      v5,
      0x46u,
      0x45u,
      L"%s%s",
      L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default",
      L"\\Defaults");
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey) )
    {
      cbData = 4;
      RegQueryValueExW(hKey, L"NFSLookup", 0, 0, (LPBYTE)&Data, &cbData);
      cbData = 4;
      RegQueryValueExW(hKey, L"NFSReaddir", 0, 0, (LPBYTE)&v14, &cbData);
      RegCloseKey(hKey);
    }
    GlobalFree(v5);
    v6 = *(_DWORD *)(a3 + 56);
    if ( Data )
      v7 = v6 | 0x80;
    else
      v7 = v6 & 0xFFFFFF7F;
    if ( v14 )
      LODWORD(v4) = v7 | 0x100;
    else
      LODWORD(v4) = v7 & 0xFFFFFEFF;
    *(_DWORD *)(a3 + 56) = (_DWORD)v4;
  }
  return (int)v4;
}

```

## disassembly

```asm
0x18000e094  mov     qword ptr [rsp-18h+cbData], rdx
0x18000e099  mov     qword ptr [rsp-18h+Data], rcx
0x18000e09e  push    rbp
0x18000e09f  push    rbx
0x18000e0a0  push    rdi
0x18000e0a1  mov     rbp, rsp
0x18000e0a4  sub     rsp, 40h
0x18000e0a8  mov     eax, 1
0x18000e0ad  mov     [rbp+hKey], 0
0x18000e0b5  mov     edx, 8Ch; dwBytes
0x18000e0ba  mov     [rbp+Data], eax
0x18000e0bd  mov     rbx, r8
0x18000e0c0  mov     [rbp+arg_18], eax
0x18000e0c3  mov     [rbp+cbData], 0
0x18000e0ca  lea     ecx, [rax+3Fh]; uFlags
0x18000e0cd  call    cs:__imp_GlobalAlloc
0x18000e0d3  mov     rdi, rax
0x18000e0d6  test    rax, rax
0x18000e0d9  jz      loc_18000E1DF
0x18000e0df  xor     edx, edx; Val
0x18000e0e1  mov     r8d, 8Ch; Size
0x18000e0e7  mov     rcx, rax; void *
0x18000e0ea  call    memset_0
0x18000e0ef  mov     edx, 46h ; 'F'; BufferCount
0x18000e0f4  lea     rax, aDefaults; "\\Defaults"
0x18000e0fb  mov     [rsp+40h+lpcbData], rax
0x18000e100  lea     r9, aSS_0; "%s%s"
0x18000e107  lea     rax, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000e10e  mov     rcx, rdi; Buffer
0x18000e111  mov     [rsp+40h+phkResult], rax
0x18000e116  lea     r8d, [rdx-1]; MaxCount
0x18000e11a  call    cs:__imp__snwprintf_s
0x18000e120  lea     rax, [rbp+hKey]
0x18000e124  mov     r9d, 20019h; samDesired
0x18000e12a  xor     r8d, r8d; ulOptions
0x18000e12d  mov     [rsp+40h+phkResult], rax; phkResult
0x18000e132  mov     rdx, rdi; lpSubKey
0x18000e135  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e13c  call    cs:__imp_RegOpenKeyExW
0x18000e142  test    eax, eax
0x18000e144  jnz     short loc_18000E1B0
0x18000e146  mov     rcx, [rbp+hKey]; hKey
0x18000e14a  lea     rax, [rbp+cbData]
0x18000e14e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000e153  lea     rdx, aNfslookup; "NFSLookup"
0x18000e15a  lea     rax, [rbp+Data]
0x18000e15e  mov     [rbp+cbData], 4
0x18000e165  xor     r9d, r9d; lpType
0x18000e168  mov     [rsp+40h+phkResult], rax; lpData
0x18000e16d  xor     r8d, r8d; lpReserved
0x18000e170  call    cs:__imp_RegQueryValueExW
0x18000e176  mov     rcx, [rbp+hKey]; hKey
0x18000e17a  lea     rax, [rbp+cbData]
0x18000e17e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000e183  lea     rdx, aNfsreaddir; "NFSReaddir"
0x18000e18a  lea     rax, [rbp+arg_18]
0x18000e18e  mov     [rbp+cbData], 4
0x18000e195  xor     r9d, r9d; lpType
0x18000e198  mov     [rsp+40h+phkResult], rax; lpData
0x18000e19d  xor     r8d, r8d; lpReserved
0x18000e1a0  call    cs:__imp_RegQueryValueExW
0x18000e1a6  mov     rcx, [rbp+hKey]; hKey
0x18000e1aa  call    cs:__imp_RegCloseKey
0x18000e1b0  mov     rcx, rdi; hMem
0x18000e1b3  call    cs:__imp_GlobalFree
0x18000e1b9  cmp     [rbp+Data], 0
0x18000e1bd  mov     eax, [rbx+38h]
0x18000e1c0  jz      short loc_18000E1C8
0x18000e1c2  bts     eax, 7
0x18000e1c6  jmp     short loc_18000E1CC
0x18000e1c8  btr     eax, 7
0x18000e1cc  cmp     [rbp+arg_18], 0
0x18000e1d0  jz      short loc_18000E1D8
0x18000e1d2  bts     eax, 8
0x18000e1d6  jmp     short loc_18000E1DC
0x18000e1d8  btr     eax, 8
0x18000e1dc  mov     [rbx+38h], eax
0x18000e1df  add     rsp, 40h
0x18000e1e3  pop     rdi
0x18000e1e4  pop     rbx
0x18000e1e5  pop     rbp
0x18000e1e6  retn
```
