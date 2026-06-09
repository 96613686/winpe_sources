# IsMsdadiagEnabledForCurrentProcess

- ea: `0x18001acc4`
- end: `0x18001ae81`
- name: `IsMsdadiagEnabledForCurrentProcess`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800194a0`

## callees

- `0x180001858`
- `0x1800194ec`
- `0x1800198f4`
- `0x18001acc4`
- `0x18002f0e0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18001ad52`
- `ADVAPI32!RegOpenKeyExW` at `0x18001ad52`
- `ADVAPI32!RegCloseKey` at `0x18001ae46`
- `ADVAPI32!RegCloseKey` at `0x18001ae46`

## string_xrefs

- `0x18001ae28`: `:Path`

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
0x18001acc4  mov     [rsp-8+arg_0], rbx
0x18001acc9  push    rbp
0x18001acca  lea     rbp, [rsp-1E0h]
0x18001acd2  sub     rsp, 2E0h
0x18001acd9  mov     rax, cs:__security_cookie
0x18001ace0  xor     rax, rsp
0x18001ace3  mov     [rbp+1E0h+var_10], rax
0x18001acea  movaps  xmm0, xmmword ptr cs:SubKey; "SOFTWARE\\Microsoft\\BidInterface\\Load"...
0x18001acf1  lea     rax, [rsp+2E0h+hKey]
0x18001acf6  movaps  xmm1, xmmword ptr cs:SubKey+10h; "\\Microsoft\\BidInterface\\Loader"
0x18001acfd  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x18001ad02  movaps  xmmword ptr [rsp+2E0h+SubKey], xmm0
0x18001ad07  xor     ebx, ebx
0x18001ad09  movaps  xmm0, xmmword ptr cs:SubKey+20h; "ft\\BidInterface\\Loader"
0x18001ad10  mov     r9d, 20019h; samDesired
0x18001ad16  movaps  [rsp+2E0h+var_270], xmm0
0x18001ad1b  xor     r8d, r8d; ulOptions
0x18001ad1e  movups  xmm0, xmmword ptr cs:SubKey+3Eh; "\\Loader"
0x18001ad25  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ad2c  mov     [rsp+2E0h+hKey], 0
0x18001ad35  movaps  [rsp+2E0h+var_280], xmm1
0x18001ad3a  movaps  xmm1, xmmword ptr cs:SubKey+30h; "terface\\Loader"
0x18001ad41  movaps  [rbp+1E0h+var_260], xmm1
0x18001ad45  movups  [rbp+1E0h+var_260+0Eh], xmm0
0x18001ad49  mov     [rsp+2E0h+var_2B0], ebx
0x18001ad4d  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18001ad52  call    cs:__imp_RegOpenKeyExW
0x18001ad59  nop     dword ptr [rax+rax+00h]
0x18001ad5e  test    eax, eax
0x18001ad60  jnz     loc_18001AE3C
0x18001ad66  lea     r9, [rsp+2E0h+var_2A0]
0x18001ad6b  mov     [rsp+2E0h+var_298], rbx
0x18001ad70  lea     r8, [rsp+2E0h+var_298]
0x18001ad75  mov     [rsp+2E0h+var_2A0], rbx
0x18001ad7a  lea     rcx, [rbp+1E0h+Filename]; lpFilename
0x18001ad7e  call    BuildApplicationPid
0x18001ad83  test    eax, eax
0x18001ad85  jz      loc_18001AE1E
0x18001ad8b  mov     rcx, [rsp+2E0h+hKey]
0x18001ad90  lea     r8, [rsp+2E0h+var_2B0]
0x18001ad95  lea     rdx, [rbp+1E0h+Filename]
0x18001ad99  call    IsMsdadiagEnabledForCurrentProcessInternal
0x18001ad9e  test    eax, eax
0x18001ada0  jnz     loc_18001AE7B
0x18001ada6  mov     rax, [rsp+2E0h+var_2A0]
0x18001adab  mov     ebx, 224h
0x18001adb0  lea     rcx, [rax+rax]
0x18001adb4  cmp     rcx, rbx
0x18001adb7  jnb     loc_18001AE75
0x18001adbd  xor     eax, eax
0x18001adbf  lea     r8, [rsp+2E0h+var_2B0]
0x18001adc4  mov     [rbp+rcx+1E0h+Filename], ax
0x18001adc9  lea     rdx, [rbp+1E0h+Filename]
0x18001adcd  mov     rcx, [rsp+2E0h+hKey]
0x18001add2  call    IsMsdadiagEnabledForCurrentProcessInternal
0x18001add7  test    eax, eax
0x18001add9  jnz     loc_18001AE7B
0x18001addf  mov     rax, [rsp+2E0h+var_298]
0x18001ade4  test    rax, rax
0x18001ade7  jz      short loc_18001AE1E
0x18001ade9  mov     ecx, 2Ah ; '*'
0x18001adee  mov     [rbp+rax*2+1E0h+Filename], cx
0x18001adf3  lea     rcx, ds:2[rax*2]
0x18001adfb  cmp     rcx, rbx
0x18001adfe  jnb     short loc_18001AE75
0x18001ae00  xor     eax, eax
0x18001ae02  lea     r8, [rsp+2E0h+var_2B0]
0x18001ae07  mov     [rbp+rcx+1E0h+Filename], ax
0x18001ae0c  lea     rdx, [rbp+1E0h+Filename]
0x18001ae10  mov     rcx, [rsp+2E0h+hKey]
0x18001ae15  call    IsMsdadiagEnabledForCurrentProcessInternal
0x18001ae1a  test    eax, eax
0x18001ae1c  jnz     short loc_18001AE7B
0x18001ae1e  mov     rcx, [rsp+2E0h+hKey]
0x18001ae23  lea     r8, [rsp+2E0h+var_2B0]
0x18001ae28  lea     rdx, aPath; ":Path"
0x18001ae2f  call    IsMsdadiagEnabledForCurrentProcessInternal
0x18001ae34  neg     eax
0x18001ae36  sbb     ebx, ebx
0x18001ae38  and     ebx, [rsp+2E0h+var_2B0]
0x18001ae3c  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001ae41  test    rcx, rcx
0x18001ae44  jz      short loc_18001AE52
0x18001ae46  call    cs:__imp_RegCloseKey
0x18001ae4d  nop     dword ptr [rax+rax+00h]
0x18001ae52  mov     eax, ebx
0x18001ae54  mov     rcx, [rbp+1E0h+var_10]
0x18001ae5b  xor     rcx, rsp; StackCookie
0x18001ae5e  call    __security_check_cookie
0x18001ae63  mov     rbx, [rsp+2E0h+arg_0]
0x18001ae6b  add     rsp, 2E0h
0x18001ae72  pop     rbp
0x18001ae73  retn
0x18001ae75  call    __report_rangecheckfailure
0x18001ae7b  mov     ebx, [rsp+2E0h+var_2B0]
0x18001ae7f  jmp     short loc_18001AE3C
```
