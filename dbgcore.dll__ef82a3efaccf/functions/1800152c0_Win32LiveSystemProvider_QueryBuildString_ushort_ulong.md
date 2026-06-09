# Win32LiveSystemProvider::QueryBuildString(ushort *,ulong)

- ea: `0x1800152c0`
- end: `0x180015380`
- name: `?QueryBuildString@Win32LiveSystemProvider@@UEAAJPEAGK@Z`
- size: `192`
- prototype: `int(Win32LiveSystemProvider *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021f4`
- `0x1800152c0`

## import_xrefs

- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x180015368`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x180015368`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x180015314`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x180015314`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x18001534c`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x18001534c`

## pseudocode

```c
__int64 __fastcall Win32LiveSystemProvider::QueryBuildString(
        Win32LiveSystemProvider *this,
        unsigned __int16 *a2,
        unsigned int a3)
{
  unsigned int v5; // edi
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  v5 = -2147467259;
  memset_0(a2, 0, 2LL * a3);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion", 0, 0x20019u, &hKey) )
  {
    Type = 0;
    cbData = 2 * a3;
    if ( !RegQueryValueExW(hKey, L"BuildLabEx", 0, &Type, (LPBYTE)a2, &cbData) && a3 )
    {
      v5 = 0;
      a2[a3 - 1] = 0;
    }
    RegCloseKey(hKey);
  }
  return v5;
}

```

## disassembly

```asm
0x1800152c0  mov     [rsp+arg_0], rbx
0x1800152c5  mov     [rsp+arg_8], rsi
0x1800152ca  push    rdi
0x1800152cb  sub     rsp, 40h
0x1800152cf  mov     ebx, r8d
0x1800152d2  mov     rsi, rdx
0x1800152d5  mov     r8d, r8d
0x1800152d8  xor     edx, edx; Val
0x1800152da  add     r8, r8; Size
0x1800152dd  mov     [rsp+48h+hKey], 0
0x1800152e6  mov     rcx, rsi; void *
0x1800152e9  mov     edi, 80004005h
0x1800152ee  call    memset_0
0x1800152f3  lea     rax, [rsp+48h+hKey]
0x1800152f8  mov     r9d, 20019h; samDesired
0x1800152fe  xor     r8d, r8d; ulOptions
0x180015301  mov     [rsp+48h+phkResult], rax; phkResult
0x180015306  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001530d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015314  call    cs:__imp_RegOpenKeyExW
0x18001531a  test    eax, eax
0x18001531c  jnz     short loc_18001536E
0x18001531e  mov     rcx, [rsp+48h+hKey]; hKey
0x180015323  lea     r9, [rsp+48h+Type]; lpType
0x180015328  mov     [rsp+48h+Type], eax
0x18001532c  lea     rdx, aBuildlabex; "BuildLabEx"
0x180015333  lea     eax, [rbx+rbx]
0x180015336  xor     r8d, r8d; lpReserved
0x180015339  mov     [rsp+48h+cbData], eax
0x18001533d  lea     rax, [rsp+48h+cbData]
0x180015342  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180015347  mov     [rsp+48h+phkResult], rsi; lpData
0x18001534c  call    cs:__imp_RegQueryValueExW
0x180015352  test    eax, eax
0x180015354  jnz     short loc_180015363
0x180015356  test    ebx, ebx
0x180015358  jz      short loc_180015363
0x18001535a  lea     ecx, [rbx-1]
0x18001535d  xor     edi, edi
0x18001535f  mov     [rsi+rcx*2], ax
0x180015363  mov     rcx, [rsp+48h+hKey]; hKey
0x180015368  call    cs:__imp_RegCloseKey
0x18001536e  mov     rbx, [rsp+48h+arg_0]
0x180015373  mov     eax, edi
0x180015375  mov     rsi, [rsp+48h+arg_8]
0x18001537a  add     rsp, 40h
0x18001537e  pop     rdi
0x18001537f  retn
```
