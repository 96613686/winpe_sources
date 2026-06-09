# CSettingsManager::SaveSettings(void)

- ea: `0x1400376c8`
- end: `0x14003780a`
- name: `?SaveSettings@CSettingsManager@@QEAAJXZ`
- size: `322`
- prototype: `__int64 __fastcall(CSettingsManager *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002d118`
- `0x14002d684`
- `0x1400374c8`

## callees

- `0x1400376c8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140037722`
- `ADVAPI32!RegCloseKey` at `0x140037722`
- `ADVAPI32!RegSetValueExW` at `0x1400377e8`
- `ADVAPI32!RegSetValueExW` at `0x1400377e8`
- `ADVAPI32!RegCreateKeyExW` at `0x1400377a4`
- `ADVAPI32!RegCreateKeyExW` at `0x1400377a4`
- `KERNEL32!ReleaseMutex` at `0x14003773f`
- `KERNEL32!ReleaseMutex` at `0x14003773f`
- `KERNEL32!WaitForSingleObject` at `0x1400376fe`
- `KERNEL32!WaitForSingleObject` at `0x1400376fe`

## pseudocode

```c
__int64 __fastcall CSettingsManager::SaveSettings(const BYTE *this)
{
  HANDLE v2; // rcx
  unsigned int v3; // ebx
  int v4; // esi
  __int64 v6; // rbx
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  dwDisposition = 0;
  v2 = *(HANDLE *)this;
  hKey = 0;
  if ( v2 )
  {
    if ( WaitForSingleObject(v2, 0x64u) == 258 )
    {
      v4 = 0;
    }
    else
    {
      v4 = 1;
      if ( !RegCreateKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Remote Assistance",
              0,
              0,
              0,
              0x20006u,
              0,
              &hKey,
              &dwDisposition) )
      {
        v6 = 0;
        while ( !RegSetValueExW(hKey, (LPCWSTR)(&RA_SETTINGS_DWORD)[v6], 0, 4u, &this[4 * v6 + 8], 4u) )
        {
          v6 = (unsigned int)(v6 + 1);
          if ( (int)v6 >= 5 )
          {
            v3 = 0;
            goto LABEL_6;
          }
        }
      }
    }
    v3 = -2147467259;
LABEL_6:
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    if ( v4 == 1 )
      ReleaseMutex(*(HANDLE *)this);
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return v3;
}

```

## disassembly

```asm
0x1400376c8  mov     rax, rsp
0x1400376cb  mov     [rax+18h], rbx
0x1400376cf  mov     [rax+20h], rsi
0x1400376d3  push    rdi
0x1400376d4  sub     rsp, 50h
0x1400376d8  mov     rdi, rcx
0x1400376db  mov     dword ptr [rax+8], 0
0x1400376e2  mov     rcx, [rcx]; hHandle
0x1400376e5  mov     qword ptr [rax+10h], 0
0x1400376ed  test    rcx, rcx
0x1400376f0  jnz     short loc_1400376F9
0x1400376f2  mov     ebx, 8000FFFFh
0x1400376f7  jmp     short loc_14003774B
0x1400376f9  mov     edx, 64h ; 'd'; dwMilliseconds
0x1400376fe  call    cs:__imp_WaitForSingleObject
0x140037705  nop     dword ptr [rax+rax+00h]
0x14003770a  cmp     eax, 102h
0x14003770f  jnz     short loc_14003775E
0x140037711  xor     esi, esi
0x140037713  mov     ebx, 80004005h
0x140037718  mov     rcx, [rsp+58h+hKey]; hKey
0x14003771d  test    rcx, rcx
0x140037720  jz      short loc_140037737
0x140037722  call    cs:__imp_RegCloseKey
0x140037729  nop     dword ptr [rax+rax+00h]
0x14003772e  mov     [rsp+58h+hKey], 0
0x140037737  cmp     esi, 1
0x14003773a  jnz     short loc_14003774B
0x14003773c  mov     rcx, [rdi]; hMutex
0x14003773f  call    cs:__imp_ReleaseMutex
0x140037746  nop     dword ptr [rax+rax+00h]
0x14003774b  mov     rsi, [rsp+58h+arg_18]
0x140037750  mov     eax, ebx
0x140037752  mov     rbx, [rsp+58h+arg_10]
0x140037757  add     rsp, 50h
0x14003775b  pop     rdi
0x14003775c  retn
0x14003775e  lea     rax, [rsp+58h+dwDisposition]
0x140037763  xor     r9d, r9d; lpClass
0x140037766  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x14003776b  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Remote Assistance"
0x140037772  lea     rax, [rsp+58h+hKey]
0x140037777  xor     r8d, r8d; Reserved
0x14003777a  mov     [rsp+58h+phkResult], rax; phkResult
0x14003777f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140037786  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14003778f  mov     esi, 1
0x140037794  mov     [rsp+58h+samDesired], 20006h; samDesired
0x14003779c  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1400377a4  call    cs:__imp_RegCreateKeyExW
0x1400377ab  nop     dword ptr [rax+rax+00h]
0x1400377b0  test    eax, eax
0x1400377b2  jnz     loc_140037713
0x1400377b8  xor     ebx, ebx
0x1400377ba  lea     rcx, ?RA_SETTINGS_DWORD@@3PAPEBGA; ushort const * near * RA_SETTINGS_DWORD
0x1400377c1  mov     [rsp+58h+samDesired], 4; cbData
0x1400377c9  mov     rdx, [rcx+rbx*8]; lpValueName
0x1400377cd  lea     rax, [rdi+8]
0x1400377d1  mov     rcx, [rsp+58h+hKey]; hKey
0x1400377d6  lea     rax, [rax+rbx*4]
0x1400377da  mov     r9d, 4; dwType
0x1400377e0  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1400377e5  xor     r8d, r8d; Reserved
0x1400377e8  call    cs:__imp_RegSetValueExW
0x1400377ef  nop     dword ptr [rax+rax+00h]
0x1400377f4  test    eax, eax
0x1400377f6  jnz     loc_140037713
0x1400377fc  inc     ebx
0x1400377fe  cmp     ebx, 5
0x140037801  jl      short loc_1400377BA
0x140037803  xor     ebx, ebx
0x140037805  jmp     loc_140037718
```
