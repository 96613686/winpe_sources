# DbgRpcValidateSystemServerRegistry(void)

- ea: `0x1803f609c`
- end: `0x1803f623e`
- name: `?DbgRpcValidateSystemServerRegistry@@YAXXZ`
- size: `418`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801af230`

## callees

- `0x1800f0f40`
- `0x1803f609c`

## import_xrefs

- `api-ms-win-crt-convert-l1-1-0!wcstoul` at `0x1803f6151`
- `api-ms-win-crt-convert-l1-1-0!wcstoul` at `0x1803f6151`
- `api-ms-win-core-synch-l1-1-0!OpenProcess` at `0x1803f616b`
- `api-ms-win-core-synch-l1-1-0!OpenProcess` at `0x1803f616b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f618d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f618d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803f617f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803f617f`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x1803f6103`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x1803f6103`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1803f6205`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1803f6205`
- `api-ms-win-core-localregistry-l1-1-0!RegDeleteValueW` at `0x1803f61a6`
- `api-ms-win-core-localregistry-l1-1-0!RegDeleteValueW` at `0x1803f61a6`
- `api-ms-win-core-localregistry-l1-1-0!RegEnumValueW` at `0x1803f61ed`
- `api-ms-win-core-localregistry-l1-1-0!RegEnumValueW` at `0x1803f61ed`

## pseudocode

```c
void DbgRpcValidateSystemServerRegistry(void)
{
  unsigned int i; // ebx
  const WCHAR *v1; // rdx
  DWORD v2; // edi
  DWORD j; // edx
  DWORD v4; // eax
  HANDLE v5; // rax
  DWORD cchValueName; // [rsp+40h] [rbp-9h] BYREF
  DWORD Type; // [rsp+44h] [rbp-5h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-1h] BYREF
  wchar_t String[32]; // [rsp+50h] [rbp+7h] BYREF

  hKey = 0;
  if ( !g_DbgRpcOnWin9x )
  {
    for ( i = 0; i < 2; ++i )
    {
      v1 = L"Software\\Microsoft\\Debug Engine\\Servers";
      if ( i )
        v1 = L"SOFTWARE\\Wow6432Node\\Microsoft\\Debug Engine\\Servers";
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0xF013Fu, &hKey) )
      {
        v2 = 0;
        Type = 0;
        for ( j = 0; ; j = v2 )
        {
          cchValueName = 32;
          if ( RegEnumValueW(hKey, j, String, &cchValueName, 0, &Type, 0, 0) )
            break;
          if ( Type == 1 && cchValueName >= 0x1A )
          {
            v4 = wcstoul(String, 0, 16);
            if ( v4 )
            {
              v5 = OpenProcess(0x400u, 0, v4);
              if ( v5 )
              {
                CloseHandle(v5);
              }
              else if ( GetLastError() == 87 )
              {
                RegDeleteValueW(hKey, String);
              }
            }
          }
          ++v2;
        }
        RegCloseKey(hKey);
      }
    }
  }
}

```

## disassembly

```asm
0x1803f609c  mov     [rsp-8+arg_0], rbx
0x1803f60a1  mov     [rsp-8+arg_8], rdi
0x1803f60a6  push    rbp
0x1803f60a7  lea     rbp, [rsp-57h]
0x1803f60ac  sub     rsp, 0A0h
0x1803f60b3  mov     rax, cs:__security_cookie
0x1803f60ba  xor     rax, rsp
0x1803f60bd  mov     [rbp+57h+var_10], rax
0x1803f60c1  cmp     cs:?g_DbgRpcOnWin9x@@3KA, 0; ulong g_DbgRpcOnWin9x
0x1803f60c8  mov     [rbp+57h+hKey], 0
0x1803f60d0  jnz     loc_1803F621C
0x1803f60d6  xor     ebx, ebx
0x1803f60d8  xor     r8d, r8d; ulOptions
0x1803f60db  lea     rax, [rbp+57h+hKey]
0x1803f60df  mov     [rsp+0A0h+phkResult], rax; phkResult
0x1803f60e4  mov     r9d, 0F013Fh; samDesired
0x1803f60ea  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Debug Engine\\Serv"...
0x1803f60f1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1803f60f8  test    ebx, ebx
0x1803f60fa  jz      short loc_1803F6103
0x1803f60fc  lea     rdx, aSoftwareWow643_0; "SOFTWARE\\Wow6432Node\\Microsoft\\Debug"...
0x1803f6103  call    cs:__imp_RegOpenKeyExW
0x1803f610a  nop     dword ptr [rax+rax+00h]
0x1803f610f  test    eax, eax
0x1803f6111  jnz     loc_1803F6211
0x1803f6117  xor     edi, edi
0x1803f6119  mov     [rbp+57h+Type], eax
0x1803f611c  mov     [rsp+0A0h+lpcbData], rdi
0x1803f6121  lea     rax, [rbp+57h+Type]
0x1803f6125  mov     [rsp+0A0h+lpData], rdi
0x1803f612a  xor     edx, edx
0x1803f612c  mov     [rsp+0A0h+lpType], rax
0x1803f6131  mov     [rsp+0A0h+phkResult], rdi
0x1803f6136  jmp     loc_1803F61DA
0x1803f613b  cmp     [rbp+57h+Type], 1
0x1803f613f  jnz     short loc_1803F61B2
0x1803f6141  cmp     [rbp+57h+cchValueName], 1Ah
0x1803f6145  jb      short loc_1803F61B2
0x1803f6147  xor     edx, edx; EndPtr
0x1803f6149  lea     rcx, [rbp+57h+String]; String
0x1803f614d  lea     r8d, [rdx+10h]; Radix
0x1803f6151  call    cs:__imp_wcstoul
0x1803f6158  nop     dword ptr [rax+rax+00h]
0x1803f615d  test    eax, eax
0x1803f615f  jz      short loc_1803F61B2
0x1803f6161  mov     r8d, eax; dwProcessId
0x1803f6164  xor     edx, edx; bInheritHandle
0x1803f6166  mov     ecx, 400h; dwDesiredAccess
0x1803f616b  call    cs:__imp_OpenProcess
0x1803f6172  nop     dword ptr [rax+rax+00h]
0x1803f6177  test    rax, rax
0x1803f617a  jz      short loc_1803F618D
0x1803f617c  mov     rcx, rax; hObject
0x1803f617f  call    cs:__imp_CloseHandle
0x1803f6186  nop     dword ptr [rax+rax+00h]
0x1803f618b  jmp     short loc_1803F61B2
0x1803f618d  call    cs:__imp_GetLastError
0x1803f6194  nop     dword ptr [rax+rax+00h]
0x1803f6199  cmp     eax, 57h ; 'W'
0x1803f619c  jnz     short loc_1803F61B2
0x1803f619e  mov     rcx, [rbp+57h+hKey]; hKey
0x1803f61a2  lea     rdx, [rbp+57h+String]; lpValueName
0x1803f61a6  call    cs:__imp_RegDeleteValueW
0x1803f61ad  nop     dword ptr [rax+rax+00h]
0x1803f61b2  mov     [rsp+0A0h+lpcbData], 0; lpcbData
0x1803f61bb  lea     rax, [rbp+57h+Type]
0x1803f61bf  mov     [rsp+0A0h+lpData], 0; lpData
0x1803f61c8  inc     edi
0x1803f61ca  mov     [rsp+0A0h+lpType], rax; lpType
0x1803f61cf  mov     edx, edi; dwIndex
0x1803f61d1  mov     [rsp+0A0h+phkResult], 0; lpReserved
0x1803f61da  mov     rcx, [rbp+57h+hKey]; hKey
0x1803f61de  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1803f61e2  lea     r8, [rbp+57h+String]; lpValueName
0x1803f61e6  mov     [rbp+57h+cchValueName], 20h ; ' '
0x1803f61ed  call    cs:__imp_RegEnumValueW
0x1803f61f4  nop     dword ptr [rax+rax+00h]
0x1803f61f9  test    eax, eax
0x1803f61fb  jz      loc_1803F613B
0x1803f6201  mov     rcx, [rbp+57h+hKey]; hKey
0x1803f6205  call    cs:__imp_RegCloseKey
0x1803f620c  nop     dword ptr [rax+rax+00h]
0x1803f6211  inc     ebx
0x1803f6213  cmp     ebx, 2
0x1803f6216  jb      loc_1803F60D8
0x1803f621c  mov     rcx, [rbp+57h+var_10]
0x1803f6220  xor     rcx, rsp; StackCookie
0x1803f6223  call    __security_check_cookie
0x1803f6228  lea     r11, [rsp+0A0h+var_s0]
0x1803f6230  mov     rbx, [r11+10h]
0x1803f6234  mov     rdi, [r11+18h]
0x1803f6238  mov     rsp, r11
0x1803f623b  pop     rbp
0x1803f623c  retn
```
