# LoadIpHlpApiDll(void)

- ea: `0x180026a20`
- end: `0x180026c74`
- name: `?LoadIpHlpApiDll@@YAKXZ`
- size: `596`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800204cc`
- `0x1800266b0`

## callees

- `0x180007c0c`
- `0x180026a20`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180026afe`
- `KERNEL32!GetProcAddress` at `0x180026b79`
- `KERNEL32!GetProcAddress` at `0x180026afe`
- `KERNEL32!GetProcAddress` at `0x180026b79`
- `KERNEL32!FreeLibrary` at `0x180026c3a`
- `KERNEL32!FreeLibrary` at `0x180026c3a`
- `KERNEL32!LoadLibraryExW` at `0x180026a84`
- `KERNEL32!LoadLibraryExW` at `0x180026a84`
- `KERNEL32!GetLastError` at `0x180026a9c`
- `KERNEL32!GetLastError` at `0x180026b16`
- `KERNEL32!GetLastError` at `0x180026b95`
- `KERNEL32!GetLastError` at `0x180026a9c`
- `KERNEL32!GetLastError` at `0x180026b16`
- `KERNEL32!GetLastError` at `0x180026b95`

## string_xrefs

- `0x180026a77`: `iphlpapi.dll`
- `0x180026abf`: `LoadLibrary(iphlpapi.dll) failed: %d`

## pseudocode

```c
__int64 LoadIpHlpApiDll(void)
{
  DWORD v0; // ebx
  HMODULE Library; // rax
  DWORD LastError; // eax
  __int64 v4; // r8
  __int64 v5; // rax
  DWORD v6; // eax
  DWORD v7; // eax
  _BYTE v8[16]; // [rsp+30h] [rbp-D0h] BYREF
  int *v9; // [rsp+40h] [rbp-C0h]
  int v10; // [rsp+48h] [rbp-B8h]
  int v11; // [rsp+4Ch] [rbp-B4h]
  int v12; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v13[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v12 = 0;
  v0 = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( hLibModule )
    return 0;
  Library = LoadLibraryExW(L"iphlpapi.dll", 0, 0x800u);
  hLibModule = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v0 = LastError;
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v12) = 0;
      FormatRRASErrorString(&v12, L"LoadLibrary(iphlpapi.dll) failed: %d", LastError);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v5 = -1;
        do
          ++v5;
        while ( *(_WORD *)&v13[2 * v5 - 4] );
LABEL_20:
        v11 = 0;
        v10 = 2 * v5 + 2;
        v9 = &v12;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v4, 2, v8);
        goto LABEL_21;
      }
    }
    goto LABEL_21;
  }
  qword_1800CF528 = (__int64)GetProcAddress(Library, "GetIfTable");
  if ( !qword_1800CF528 )
  {
    v6 = GetLastError();
    v0 = v6;
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v12) = 0;
      FormatRRASErrorString(&v12, L"GetProcAddress( GetIfTable ) failed: %d", v6);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v5 = -1;
        do
          ++v5;
        while ( *(_WORD *)&v13[2 * v5 - 4] );
        goto LABEL_20;
      }
    }
LABEL_21:
    if ( v0 )
    {
      qword_1800CF528 = 0;
      qword_1800CF530 = 0;
      if ( hLibModule )
      {
        FreeLibrary(hLibModule);
        hLibModule = 0;
      }
    }
    return v0;
  }
  qword_1800CF530 = (__int64)GetProcAddress(hLibModule, "GetIpAddrTable");
  if ( !qword_1800CF530 )
  {
    v7 = GetLastError();
    v0 = v7;
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v12) = 0;
      FormatRRASErrorString(&v12, L"GetProcAddress( GetIpAddrTable ) failed: %d", v7);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v5 = -1;
        do
          ++v5;
        while ( *(_WORD *)&v13[2 * v5 - 4] );
        goto LABEL_20;
      }
    }
    goto LABEL_21;
  }
  return v0;
}

```

## disassembly

```asm
0x180026a20  mov     [rsp-8+arg_0], rbx
0x180026a25  mov     [rsp-8+arg_8], rdi
0x180026a2a  push    rbp
0x180026a2b  lea     rbp, [rsp-760h]
0x180026a33  sub     rsp, 860h
0x180026a3a  mov     rax, cs:__security_cookie
0x180026a41  xor     rax, rsp
0x180026a44  mov     [rbp+760h+var_10], rax
0x180026a4b  xor     edi, edi
0x180026a4d  lea     rcx, [rsp+860h+var_80C]; void *
0x180026a52  xor     edx, edx; Val
0x180026a54  mov     [rsp+860h+var_810], edi
0x180026a58  mov     r8d, 7FCh; Size
0x180026a5e  mov     ebx, edi
0x180026a60  call    memset_0
0x180026a65  cmp     cs:hLibModule, rdi
0x180026a6c  jz      short loc_180026A75
0x180026a6e  xor     eax, eax
0x180026a70  jmp     loc_180026C4F
0x180026a75  xor     edx, edx; hFile
0x180026a77  lea     rcx, LibFileName; "iphlpapi.dll"
0x180026a7e  mov     r8d, 800h; dwFlags
0x180026a84  call    cs:__imp_LoadLibraryExW
0x180026a8b  nop     dword ptr [rax+rax+00h]
0x180026a90  mov     cs:hLibModule, rax
0x180026a97  test    rax, rax
0x180026a9a  jnz     short loc_180026AF4
0x180026a9c  call    cs:__imp_GetLastError
0x180026aa3  nop     dword ptr [rax+rax+00h]
0x180026aa8  test    cs:byte_1800CF404, 8
0x180026aaf  mov     ebx, eax
0x180026ab1  jz      loc_180026C1C
0x180026ab7  mov     r8d, eax
0x180026aba  mov     word ptr [rsp+860h+var_810], di
0x180026abf  lea     rdx, aLoadlibraryIph; "LoadLibrary(iphlpapi.dll) failed: %d"
0x180026ac6  lea     rcx, [rsp+860h+var_810]
0x180026acb  call    FormatRRASErrorString
0x180026ad0  test    cs:byte_1800CF404, 8
0x180026ad7  jz      loc_180026C1C
0x180026add  lea     rcx, [rsp+860h+var_810]
0x180026ae2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026ae6  inc     rax
0x180026ae9  cmp     [rcx+rax*2], di
0x180026aed  jnz     short loc_180026AE6
0x180026aef  jmp     loc_180026BE0
0x180026af4  lea     rdx, aGetiftable; "GetIfTable"
0x180026afb  mov     rcx, rax; hModule
0x180026afe  call    cs:__imp_GetProcAddress
0x180026b05  nop     dword ptr [rax+rax+00h]
0x180026b0a  mov     cs:qword_1800CF528, rax
0x180026b11  test    rax, rax
0x180026b14  jnz     short loc_180026B6B
0x180026b16  call    cs:__imp_GetLastError
0x180026b1d  nop     dword ptr [rax+rax+00h]
0x180026b22  test    cs:byte_1800CF404, 8
0x180026b29  mov     ebx, eax
0x180026b2b  jz      loc_180026C1C
0x180026b31  mov     r8d, eax
0x180026b34  mov     word ptr [rsp+860h+var_810], di
0x180026b39  lea     rdx, aGetprocaddress_0; "GetProcAddress( GetIfTable ) failed: %d"
0x180026b40  lea     rcx, [rsp+860h+var_810]
0x180026b45  call    FormatRRASErrorString
0x180026b4a  test    cs:byte_1800CF404, 8
0x180026b51  jz      loc_180026C1C
0x180026b57  lea     rcx, [rsp+860h+var_810]
0x180026b5c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026b60  inc     rax
0x180026b63  cmp     [rcx+rax*2], di
0x180026b67  jnz     short loc_180026B60
0x180026b69  jmp     short loc_180026BE0
0x180026b6b  mov     rcx, cs:hLibModule; hModule
0x180026b72  lea     rdx, aGetipaddrtable; "GetIpAddrTable"
0x180026b79  call    cs:__imp_GetProcAddress
0x180026b80  nop     dword ptr [rax+rax+00h]
0x180026b85  mov     cs:qword_1800CF530, rax
0x180026b8c  test    rax, rax
0x180026b8f  jnz     loc_180026C4D
0x180026b95  call    cs:__imp_GetLastError
0x180026b9c  nop     dword ptr [rax+rax+00h]
0x180026ba1  test    cs:byte_1800CF404, 8
0x180026ba8  mov     ebx, eax
0x180026baa  jz      short loc_180026C1C
0x180026bac  mov     r8d, eax
0x180026baf  mov     word ptr [rsp+860h+var_810], di
0x180026bb4  lea     rdx, aGetprocaddress; "GetProcAddress( GetIpAddrTable ) failed"...
0x180026bbb  lea     rcx, [rsp+860h+var_810]
0x180026bc0  call    FormatRRASErrorString
0x180026bc5  test    cs:byte_1800CF404, 8
0x180026bcc  jz      short loc_180026C1C
0x180026bce  lea     rcx, [rsp+860h+var_810]
0x180026bd3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026bd7  inc     rax
0x180026bda  cmp     [rcx+rax*2], di
0x180026bde  jnz     short loc_180026BD7
0x180026be0  lea     eax, ds:2[rax*2]
0x180026be7  mov     [rsp+860h+var_814], edi
0x180026beb  lea     rcx, [rsp+860h+var_810]
0x180026bf0  mov     [rsp+860h+var_818], eax
0x180026bf4  lea     rax, [rsp+860h+var_830]
0x180026bf9  mov     [rsp+860h+var_820], rcx
0x180026bfe  mov     r9d, 2
0x180026c04  mov     [rsp+860h+var_840], rax
0x180026c09  lea     rdx, RasDdmTraceError
0x180026c10  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026c17  call    McGenEventWrite_EventWriteTransfer
0x180026c1c  test    ebx, ebx
0x180026c1e  jz      short loc_180026C4D
0x180026c20  mov     rcx, cs:hLibModule; hLibModule
0x180026c27  mov     cs:qword_1800CF528, rdi
0x180026c2e  mov     cs:qword_1800CF530, rdi
0x180026c35  test    rcx, rcx
0x180026c38  jz      short loc_180026C4D
0x180026c3a  call    cs:__imp_FreeLibrary
0x180026c41  nop     dword ptr [rax+rax+00h]
0x180026c46  mov     cs:hLibModule, rdi
0x180026c4d  mov     eax, ebx
0x180026c4f  mov     rcx, [rbp+760h+var_10]
0x180026c56  xor     rcx, rsp; StackCookie
0x180026c59  call    __security_check_cookie
0x180026c5e  lea     r11, [rsp+860h+var_s0]
0x180026c66  mov     rbx, [r11+10h]
0x180026c6a  mov     rdi, [r11+18h]
0x180026c6e  mov     rsp, r11
0x180026c71  pop     rbp
0x180026c72  retn
```
