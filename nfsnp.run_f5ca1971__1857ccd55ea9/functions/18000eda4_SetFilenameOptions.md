# SetFilenameOptions

- ea: `0x18000eda4`
- end: `0x18000ef22`
- name: `SetFilenameOptions`
- size: `382`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000c738`
- `0x18000f1c8`

## callees

- `0x18000eda4`
- `0x180012e32`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x18000ee30`
- `msvcrt!_snwprintf_s` at `0x18000ee30`
- `KERNEL32!GlobalFree` at `0x18000eee7`
- `KERNEL32!GlobalFree` at `0x18000eee7`
- `KERNEL32!GlobalAlloc` at `0x18000eddd`
- `KERNEL32!GlobalAlloc` at `0x18000eddd`
- `ADVAPI32!RegCloseKey` at `0x18000eed8`
- `ADVAPI32!RegCloseKey` at `0x18000eed8`
- `ADVAPI32!RegQueryValueExW` at `0x18000ee92`
- `ADVAPI32!RegQueryValueExW` at `0x18000eec8`
- `ADVAPI32!RegQueryValueExW` at `0x18000ee92`
- `ADVAPI32!RegQueryValueExW` at `0x18000eec8`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ee58`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ee58`

## string_xrefs

- `0x18000eeab`: `NFSReaddir`

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
0x18000eda4  mov     qword ptr [rsp-18h+cbData], rdx
0x18000eda9  mov     qword ptr [rsp-18h+Data], rcx
0x18000edae  push    rbp
0x18000edaf  push    rbx
0x18000edb0  push    rdi
0x18000edb1  mov     rbp, rsp
0x18000edb4  sub     rsp, 40h
0x18000edb8  mov     eax, 1
0x18000edbd  mov     [rbp+hKey], 0
0x18000edc5  mov     edx, 8Ch; dwBytes
0x18000edca  mov     [rbp+Data], eax
0x18000edcd  mov     rbx, r8
0x18000edd0  mov     [rbp+arg_18], eax
0x18000edd3  mov     [rbp+cbData], 0
0x18000edda  lea     ecx, [rax+3Fh]; uFlags
0x18000eddd  call    cs:__imp_GlobalAlloc
0x18000ede4  nop     dword ptr [rax+rax+00h]
0x18000ede9  mov     rdi, rax
0x18000edec  test    rax, rax
0x18000edef  jz      loc_18000EF19
0x18000edf5  xor     edx, edx; Val
0x18000edf7  mov     r8d, 8Ch; Size
0x18000edfd  mov     rcx, rax; void *
0x18000ee00  call    memset_0
0x18000ee05  mov     edx, 46h ; 'F'; BufferCount
0x18000ee0a  lea     rax, aDefaults; "\\Defaults"
0x18000ee11  mov     [rsp+40h+lpcbData], rax
0x18000ee16  lea     r9, aSS_0; "%s%s"
0x18000ee1d  lea     rax, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000ee24  mov     rcx, rdi; Buffer
0x18000ee27  mov     [rsp+40h+phkResult], rax
0x18000ee2c  lea     r8d, [rdx-1]; MaxCount
0x18000ee30  call    cs:__imp__snwprintf_s
0x18000ee37  nop     dword ptr [rax+rax+00h]
0x18000ee3c  lea     rax, [rbp+hKey]
0x18000ee40  mov     r9d, 20019h; samDesired
0x18000ee46  xor     r8d, r8d; ulOptions
0x18000ee49  mov     [rsp+40h+phkResult], rax; phkResult
0x18000ee4e  mov     rdx, rdi; lpSubKey
0x18000ee51  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ee58  call    cs:__imp_RegOpenKeyExW
0x18000ee5f  nop     dword ptr [rax+rax+00h]
0x18000ee64  test    eax, eax
0x18000ee66  jnz     short loc_18000EEE4
0x18000ee68  mov     rcx, [rbp+hKey]; hKey
0x18000ee6c  lea     rax, [rbp+cbData]
0x18000ee70  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000ee75  lea     rdx, aNfslookup; "NFSLookup"
0x18000ee7c  lea     rax, [rbp+Data]
0x18000ee80  mov     [rbp+cbData], 4
0x18000ee87  xor     r9d, r9d; lpType
0x18000ee8a  mov     [rsp+40h+phkResult], rax; lpData
0x18000ee8f  xor     r8d, r8d; lpReserved
0x18000ee92  call    cs:__imp_RegQueryValueExW
0x18000ee99  nop     dword ptr [rax+rax+00h]
0x18000ee9e  mov     rcx, [rbp+hKey]; hKey
0x18000eea2  lea     rax, [rbp+cbData]
0x18000eea6  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000eeab  lea     rdx, aNfsreaddir; "NFSReaddir"
0x18000eeb2  lea     rax, [rbp+arg_18]
0x18000eeb6  mov     [rbp+cbData], 4
0x18000eebd  xor     r9d, r9d; lpType
0x18000eec0  mov     [rsp+40h+phkResult], rax; lpData
0x18000eec5  xor     r8d, r8d; lpReserved
0x18000eec8  call    cs:__imp_RegQueryValueExW
0x18000eecf  nop     dword ptr [rax+rax+00h]
0x18000eed4  mov     rcx, [rbp+hKey]; hKey
0x18000eed8  call    cs:__imp_RegCloseKey
0x18000eedf  nop     dword ptr [rax+rax+00h]
0x18000eee4  mov     rcx, rdi; hMem
0x18000eee7  call    cs:__imp_GlobalFree
0x18000eeee  nop     dword ptr [rax+rax+00h]
0x18000eef3  cmp     [rbp+Data], 0
0x18000eef7  mov     eax, [rbx+38h]
0x18000eefa  jz      short loc_18000EF02
0x18000eefc  bts     eax, 7
0x18000ef00  jmp     short loc_18000EF06
0x18000ef02  btr     eax, 7
0x18000ef06  cmp     [rbp+arg_18], 0
0x18000ef0a  jz      short loc_18000EF12
0x18000ef0c  bts     eax, 8
0x18000ef10  jmp     short loc_18000EF16
0x18000ef12  btr     eax, 8
0x18000ef16  mov     [rbx+38h], eax
0x18000ef19  add     rsp, 40h
0x18000ef1d  pop     rdi
0x18000ef1e  pop     rbx
0x18000ef1f  pop     rbp
0x18000ef20  retn
```
