# IsMsdadiagEnabledForCurrentProcess

- ea: `0x1800c8bf4`
- end: `0x1800c8db1`
- name: `IsMsdadiagEnabledForCurrentProcess`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c59f0`

## callees

- `0x180063ed8`
- `0x1800c5a3c`
- `0x1800c67d4`
- `0x1800c8bf4`
- `0x1800cdb20`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800c8d76`
- `ADVAPI32!RegCloseKey` at `0x1800c8d76`
- `ADVAPI32!RegOpenKeyExW` at `0x1800c8c82`
- `ADVAPI32!RegOpenKeyExW` at `0x1800c8c82`

## string_xrefs

- `0x1800c8d58`: `:Path`

## pseudocode

```c
__int64 IsMsdadiagEnabledForCurrentProcess()
{
  unsigned int v0; // ebx
  __int64 v1; // rax
  unsigned __int64 v2; // rcx
  int v3; // eax
  unsigned int v5; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v7; // [rsp+40h] [rbp-C0h]
  __int64 v8; // [rsp+48h] [rbp-B8h]
  WCHAR SubKey[40]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[280]; // [rsp+A0h] [rbp-60h] BYREF

  wcscpy(SubKey, L"SOFTWARE\\Microsoft\\BidInterfac\\Loader");
  v0 = 0;
  hKey = 0;
  v5 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
    v8 = 0;
    v7 = 0;
    if ( (unsigned int)BuildApplicationPid(Filename) )
    {
      if ( (unsigned int)IsMsdadiagEnabledForCurrentProcessInternal(hKey, Filename, &v5) )
        goto LABEL_14;
      if ( (unsigned __int64)(2 * v7) >= 0x224 )
        goto LABEL_13;
      Filename[v7] = 0;
      if ( (unsigned int)IsMsdadiagEnabledForCurrentProcessInternal(hKey, Filename, &v5) )
      {
LABEL_14:
        v0 = v5;
        goto LABEL_10;
      }
      v1 = v8;
      if ( v8 )
      {
        Filename[v8] = 42;
        v2 = 2 * v1 + 2;
        if ( v2 < 0x224 )
        {
          *(WCHAR *)((char *)Filename + v2) = 0;
          if ( !(unsigned int)IsMsdadiagEnabledForCurrentProcessInternal(hKey, Filename, &v5) )
            goto LABEL_9;
          goto LABEL_14;
        }
LABEL_13:
        _report_rangecheckfailure();
      }
    }
LABEL_9:
    v3 = IsMsdadiagEnabledForCurrentProcessInternal(hKey, L":Path", &v5);
    v0 = v3 != 0 ? v5 : 0;
  }
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x1800c8bf4  mov     [rsp-8+arg_0], rbx
0x1800c8bf9  push    rbp
0x1800c8bfa  lea     rbp, [rsp-1E0h]
0x1800c8c02  sub     rsp, 2E0h
0x1800c8c09  mov     rax, cs:__security_cookie
0x1800c8c10  xor     rax, rsp
0x1800c8c13  mov     [rbp+1E0h+var_10], rax
0x1800c8c1a  movaps  xmm0, xmmword ptr cs:aSoftwareMicros; "SOFTWARE\\Microsoft\\BidInterface\\Load"...
0x1800c8c21  lea     rax, [rsp+2E0h+hKey]
0x1800c8c26  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+10h; "\\Microsoft\\BidInterface\\Loader"
0x1800c8c2d  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x1800c8c32  movaps  xmmword ptr [rsp+2E0h+SubKey], xmm0
0x1800c8c37  xor     ebx, ebx
0x1800c8c39  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+20h; "ft\\BidInterface\\Loader"
0x1800c8c40  mov     r9d, 20019h; samDesired
0x1800c8c46  movaps  [rsp+2E0h+var_270], xmm0
0x1800c8c4b  xor     r8d, r8d; ulOptions
0x1800c8c4e  movups  xmm0, xmmword ptr cs:aSoftwareMicros+3Eh; "\\Loader"
0x1800c8c55  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c8c5c  mov     [rsp+2E0h+hKey], 0
0x1800c8c65  movaps  [rsp+2E0h+var_280], xmm1
0x1800c8c6a  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+30h; "terface\\Loader"
0x1800c8c71  movaps  [rbp+1E0h+var_260], xmm1
0x1800c8c75  movups  [rbp+1E0h+var_260+0Eh], xmm0
0x1800c8c79  mov     [rsp+2E0h+var_2B0], ebx
0x1800c8c7d  mov     [rsp+2E0h+phkResult], rax; phkResult
0x1800c8c82  call    cs:__imp_RegOpenKeyExW
0x1800c8c89  nop     dword ptr [rax+rax+00h]
0x1800c8c8e  test    eax, eax
0x1800c8c90  jnz     loc_1800C8D6C
0x1800c8c96  lea     r9, [rsp+2E0h+var_2A0]
0x1800c8c9b  mov     [rsp+2E0h+var_298], rbx
0x1800c8ca0  lea     r8, [rsp+2E0h+var_298]
0x1800c8ca5  mov     [rsp+2E0h+var_2A0], rbx
0x1800c8caa  lea     rcx, [rbp+1E0h+Filename]; lpFilename
0x1800c8cae  call    BuildApplicationPid
0x1800c8cb3  test    eax, eax
0x1800c8cb5  jz      loc_1800C8D4E
0x1800c8cbb  mov     rcx, [rsp+2E0h+hKey]
0x1800c8cc0  lea     r8, [rsp+2E0h+var_2B0]
0x1800c8cc5  lea     rdx, [rbp+1E0h+Filename]
0x1800c8cc9  call    IsMsdadiagEnabledForCurrentProcessInternal
0x1800c8cce  test    eax, eax
0x1800c8cd0  jnz     loc_1800C8DAB
0x1800c8cd6  mov     rax, [rsp+2E0h+var_2A0]
0x1800c8cdb  mov     ebx, 224h
0x1800c8ce0  lea     rcx, [rax+rax]
0x1800c8ce4  cmp     rcx, rbx
0x1800c8ce7  jnb     loc_1800C8DA5
0x1800c8ced  xor     eax, eax
0x1800c8cef  lea     r8, [rsp+2E0h+var_2B0]
0x1800c8cf4  mov     [rbp+rcx+1E0h+Filename], ax
0x1800c8cf9  lea     rdx, [rbp+1E0h+Filename]
0x1800c8cfd  mov     rcx, [rsp+2E0h+hKey]
0x1800c8d02  call    IsMsdadiagEnabledForCurrentProcessInternal
0x1800c8d07  test    eax, eax
0x1800c8d09  jnz     loc_1800C8DAB
0x1800c8d0f  mov     rax, [rsp+2E0h+var_298]
0x1800c8d14  test    rax, rax
0x1800c8d17  jz      short loc_1800C8D4E
0x1800c8d19  mov     ecx, 2Ah ; '*'
0x1800c8d1e  mov     [rbp+rax*2+1E0h+Filename], cx
0x1800c8d23  lea     rcx, ds:2[rax*2]
0x1800c8d2b  cmp     rcx, rbx
0x1800c8d2e  jnb     short loc_1800C8DA5
0x1800c8d30  xor     eax, eax
0x1800c8d32  lea     r8, [rsp+2E0h+var_2B0]
0x1800c8d37  mov     [rbp+rcx+1E0h+Filename], ax
0x1800c8d3c  lea     rdx, [rbp+1E0h+Filename]
0x1800c8d40  mov     rcx, [rsp+2E0h+hKey]
0x1800c8d45  call    IsMsdadiagEnabledForCurrentProcessInternal
0x1800c8d4a  test    eax, eax
0x1800c8d4c  jnz     short loc_1800C8DAB
0x1800c8d4e  mov     rcx, [rsp+2E0h+hKey]
0x1800c8d53  lea     r8, [rsp+2E0h+var_2B0]
0x1800c8d58  lea     rdx, aPath; ":Path"
0x1800c8d5f  call    IsMsdadiagEnabledForCurrentProcessInternal
0x1800c8d64  neg     eax
0x1800c8d66  sbb     ebx, ebx
0x1800c8d68  and     ebx, [rsp+2E0h+var_2B0]
0x1800c8d6c  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800c8d71  test    rcx, rcx
0x1800c8d74  jz      short loc_1800C8D82
0x1800c8d76  call    cs:__imp_RegCloseKey
0x1800c8d7d  nop     dword ptr [rax+rax+00h]
0x1800c8d82  mov     eax, ebx
0x1800c8d84  mov     rcx, [rbp+1E0h+var_10]
0x1800c8d8b  xor     rcx, rsp; StackCookie
0x1800c8d8e  call    __security_check_cookie
0x1800c8d93  mov     rbx, [rsp+2E0h+arg_0]
0x1800c8d9b  add     rsp, 2E0h
0x1800c8da2  pop     rbp
0x1800c8da3  retn
0x1800c8da5  call    __report_rangecheckfailure
0x1800c8dab  mov     ebx, [rsp+2E0h+var_2B0]
0x1800c8daf  jmp     short loc_1800C8D6C
```
