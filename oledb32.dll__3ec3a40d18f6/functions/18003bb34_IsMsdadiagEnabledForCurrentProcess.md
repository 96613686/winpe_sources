# IsMsdadiagEnabledForCurrentProcess

- ea: `0x18003bb34`
- end: `0x18003bce4`
- name: `IsMsdadiagEnabledForCurrentProcess`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032420`

## callees

- `0x180026154`
- `0x18002e848`
- `0x180037eb0`
- `0x18003bb34`
- `0x18007e700`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18003bbc2`
- `ADVAPI32!RegOpenKeyExW` at `0x18003bbc2`
- `ADVAPI32!RegCloseKey` at `0x18003bcb0`
- `ADVAPI32!RegCloseKey` at `0x18003bcb0`

## string_xrefs

- `0x18003bc92`: `:Path`

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
0x18003bb34  mov     [rsp-8+arg_0], rbx
0x18003bb39  push    rbp
0x18003bb3a  lea     rbp, [rsp-1E0h]
0x18003bb42  sub     rsp, 2E0h
0x18003bb49  mov     rax, cs:__security_cookie
0x18003bb50  xor     rax, rsp
0x18003bb53  mov     [rbp+1E0h+var_10], rax
0x18003bb5a  movaps  xmm0, xmmword ptr cs:aSoftwareMicros; "SOFTWARE\\Microsoft\\BidInterface\\Load"...
0x18003bb61  lea     rax, [rsp+2E0h+hKey]
0x18003bb66  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+10h; "\\Microsoft\\BidInterface\\Loader"
0x18003bb6d  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x18003bb72  movaps  xmmword ptr [rsp+2E0h+SubKey], xmm0
0x18003bb77  xor     ebx, ebx
0x18003bb79  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+20h; "ft\\BidInterface\\Loader"
0x18003bb80  mov     r9d, 20019h; samDesired
0x18003bb86  movaps  [rsp+2E0h+var_270], xmm0
0x18003bb8b  xor     r8d, r8d; ulOptions
0x18003bb8e  movups  xmm0, xmmword ptr cs:aSoftwareMicros+3Eh; "\\Loader"
0x18003bb95  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003bb9c  mov     [rsp+2E0h+hKey], 0
0x18003bba5  movaps  [rsp+2E0h+var_280], xmm1
0x18003bbaa  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+30h; "terface\\Loader"
0x18003bbb1  movaps  [rbp+1E0h+var_260], xmm1
0x18003bbb5  movups  [rbp+1E0h+var_260+0Eh], xmm0
0x18003bbb9  mov     [rsp+2E0h+var_2B0], ebx
0x18003bbbd  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18003bbc2  call    cs:__imp_RegOpenKeyExW
0x18003bbc8  test    eax, eax
0x18003bbca  jnz     loc_18003BCA6
0x18003bbd0  lea     r9, [rsp+2E0h+var_2A0]
0x18003bbd5  mov     [rsp+2E0h+var_298], rbx
0x18003bbda  lea     r8, [rsp+2E0h+var_298]
0x18003bbdf  mov     [rsp+2E0h+var_2A0], rbx
0x18003bbe4  lea     rcx, [rbp+1E0h+Filename]; lpFilename
0x18003bbe8  call    BuildApplicationPid
0x18003bbed  test    eax, eax
0x18003bbef  jz      loc_18003BC88
0x18003bbf5  mov     rcx, [rsp+2E0h+hKey]
0x18003bbfa  lea     r8, [rsp+2E0h+var_2B0]
0x18003bbff  lea     rdx, [rbp+1E0h+Filename]
0x18003bc03  call    IsMsdadiagEnabledForCurrentProcessInternal
0x18003bc08  test    eax, eax
0x18003bc0a  jnz     loc_18003BCDE
0x18003bc10  mov     rax, [rsp+2E0h+var_2A0]
0x18003bc15  mov     ebx, 224h
0x18003bc1a  lea     rcx, [rax+rax]
0x18003bc1e  cmp     rcx, rbx
0x18003bc21  jnb     loc_18003BCD8
0x18003bc27  xor     eax, eax
0x18003bc29  lea     r8, [rsp+2E0h+var_2B0]
0x18003bc2e  mov     [rbp+rcx+1E0h+Filename], ax
0x18003bc33  lea     rdx, [rbp+1E0h+Filename]
0x18003bc37  mov     rcx, [rsp+2E0h+hKey]
0x18003bc3c  call    IsMsdadiagEnabledForCurrentProcessInternal
0x18003bc41  test    eax, eax
0x18003bc43  jnz     loc_18003BCDE
0x18003bc49  mov     rax, [rsp+2E0h+var_298]
0x18003bc4e  test    rax, rax
0x18003bc51  jz      short loc_18003BC88
0x18003bc53  mov     ecx, 2Ah ; '*'
0x18003bc58  mov     [rbp+rax*2+1E0h+Filename], cx
0x18003bc5d  lea     rcx, ds:2[rax*2]
0x18003bc65  cmp     rcx, rbx
0x18003bc68  jnb     short loc_18003BCD8
0x18003bc6a  xor     eax, eax
0x18003bc6c  lea     r8, [rsp+2E0h+var_2B0]
0x18003bc71  mov     [rbp+rcx+1E0h+Filename], ax
0x18003bc76  lea     rdx, [rbp+1E0h+Filename]
0x18003bc7a  mov     rcx, [rsp+2E0h+hKey]
0x18003bc7f  call    IsMsdadiagEnabledForCurrentProcessInternal
0x18003bc84  test    eax, eax
0x18003bc86  jnz     short loc_18003BCDE
0x18003bc88  mov     rcx, [rsp+2E0h+hKey]
0x18003bc8d  lea     r8, [rsp+2E0h+var_2B0]
0x18003bc92  lea     rdx, aPath; ":Path"
0x18003bc99  call    IsMsdadiagEnabledForCurrentProcessInternal
0x18003bc9e  neg     eax
0x18003bca0  sbb     ebx, ebx
0x18003bca2  and     ebx, [rsp+2E0h+var_2B0]
0x18003bca6  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18003bcab  test    rcx, rcx
0x18003bcae  jz      short loc_18003BCB6
0x18003bcb0  call    cs:__imp_RegCloseKey
0x18003bcb6  mov     eax, ebx
0x18003bcb8  mov     rcx, [rbp+1E0h+var_10]
0x18003bcbf  xor     rcx, rsp; StackCookie
0x18003bcc2  call    __security_check_cookie
0x18003bcc7  mov     rbx, [rsp+2E0h+arg_0]
0x18003bccf  add     rsp, 2E0h
0x18003bcd6  pop     rbp
0x18003bcd7  retn
0x18003bcd8  call    __report_rangecheckfailure
0x18003bcde  mov     ebx, [rsp+2E0h+var_2B0]
0x18003bce2  jmp     short loc_18003BCA6
```
