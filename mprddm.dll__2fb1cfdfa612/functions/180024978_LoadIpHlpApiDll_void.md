# LoadIpHlpApiDll(void)

- ea: `0x180024978`
- end: `0x180024ba3`
- name: `?LoadIpHlpApiDll@@YAKXZ`
- size: `555`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f818`
- `0x180024668`

## callees

- `0x180007b7c`
- `0x180024978`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180024a48`
- `KERNEL32!GetProcAddress` at `0x180024ab7`
- `KERNEL32!GetProcAddress` at `0x180024a48`
- `KERNEL32!GetProcAddress` at `0x180024ab7`
- `KERNEL32!FreeLibrary` at `0x180024b6c`
- `KERNEL32!FreeLibrary` at `0x180024b6c`
- `KERNEL32!LoadLibraryExW` at `0x1800249da`
- `KERNEL32!LoadLibraryExW` at `0x1800249da`
- `KERNEL32!GetLastError` at `0x1800249ec`
- `KERNEL32!GetLastError` at `0x180024a5a`
- `KERNEL32!GetLastError` at `0x180024acd`
- `KERNEL32!GetLastError` at `0x1800249ec`
- `KERNEL32!GetLastError` at `0x180024a5a`
- `KERNEL32!GetLastError` at `0x180024acd`

## string_xrefs

- `0x1800249cd`: `iphlpapi.dll`
- `0x180024a09`: `LoadLibrary(iphlpapi.dll) failed: %d`

## pseudocode

```c
__int64 LoadIpHlpApiDll(void)
{
  HMODULE Library; // rax
  DWORD LastError; // eax
  DWORD v3; // ebx
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
  memset_0(v13, 0, sizeof(v13));
  if ( hLibModule )
    return 0;
  Library = LoadLibraryExW(L"iphlpapi.dll", 0, 0x800u);
  hLibModule = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v12) = 0;
      FormatRRASErrorString(&v12, L"LoadLibrary(iphlpapi.dll) failed: %d", LastError);
      if ( (byte_1800C8404 & 8) != 0 )
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
  qword_1800C8528 = (__int64)GetProcAddress(Library, "GetIfTable");
  if ( !qword_1800C8528 )
  {
    v6 = GetLastError();
    v3 = v6;
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v12) = 0;
      FormatRRASErrorString(&v12, L"GetProcAddress( GetIfTable ) failed: %d", v6);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v5 = -1;
        do
          ++v5;
        while ( *(_WORD *)&v13[2 * v5 - 4] );
        goto LABEL_20;
      }
    }
LABEL_21:
    if ( v3 )
    {
      qword_1800C8528 = 0;
      qword_1800C8530 = 0;
      if ( hLibModule )
      {
        FreeLibrary(hLibModule);
        hLibModule = 0;
      }
    }
    return v3;
  }
  qword_1800C8530 = (__int64)GetProcAddress(hLibModule, "GetIpAddrTable");
  if ( !qword_1800C8530 )
  {
    v7 = GetLastError();
    v3 = v7;
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v12) = 0;
      FormatRRASErrorString(&v12, L"GetProcAddress( GetIpAddrTable ) failed: %d", v7);
      if ( (byte_1800C8404 & 8) != 0 )
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
  return 0;
}

```

## disassembly

```asm
0x180024978  mov     [rsp-8+arg_0], rbx
0x18002497d  mov     [rsp-8+arg_8], rdi
0x180024982  push    rbp
0x180024983  lea     rbp, [rsp-760h]
0x18002498b  sub     rsp, 860h
0x180024992  mov     rax, cs:__security_cookie
0x180024999  xor     rax, rsp
0x18002499c  mov     [rbp+760h+var_10], rax
0x1800249a3  xor     edi, edi
0x1800249a5  lea     rcx, [rsp+860h+var_80C]; void *
0x1800249aa  xor     edx, edx; Val
0x1800249ac  mov     [rsp+860h+var_810], edi
0x1800249b0  mov     r8d, 7FCh; Size
0x1800249b6  call    memset_0
0x1800249bb  cmp     cs:hLibModule, rdi
0x1800249c2  jz      short loc_1800249CB
0x1800249c4  xor     eax, eax
0x1800249c6  jmp     loc_180024B7F
0x1800249cb  xor     edx, edx; hFile
0x1800249cd  lea     rcx, LibFileName; "iphlpapi.dll"
0x1800249d4  mov     r8d, 800h; dwFlags
0x1800249da  call    cs:__imp_LoadLibraryExW
0x1800249e0  mov     cs:hLibModule, rax
0x1800249e7  test    rax, rax
0x1800249ea  jnz     short loc_180024A3E
0x1800249ec  call    cs:__imp_GetLastError
0x1800249f2  test    cs:byte_1800C8404, 8
0x1800249f9  mov     ebx, eax
0x1800249fb  jz      loc_180024B4E
0x180024a01  mov     r8d, eax
0x180024a04  mov     word ptr [rsp+860h+var_810], di
0x180024a09  lea     rdx, aLoadlibraryIph; "LoadLibrary(iphlpapi.dll) failed: %d"
0x180024a10  lea     rcx, [rsp+860h+var_810]
0x180024a15  call    FormatRRASErrorString
0x180024a1a  test    cs:byte_1800C8404, 8
0x180024a21  jz      loc_180024B4E
0x180024a27  lea     rcx, [rsp+860h+var_810]
0x180024a2c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024a30  inc     rax
0x180024a33  cmp     [rcx+rax*2], di
0x180024a37  jnz     short loc_180024A30
0x180024a39  jmp     loc_180024B12
0x180024a3e  lea     rdx, aGetiftable; "GetIfTable"
0x180024a45  mov     rcx, rax; hModule
0x180024a48  call    cs:__imp_GetProcAddress
0x180024a4e  mov     cs:qword_1800C8528, rax
0x180024a55  test    rax, rax
0x180024a58  jnz     short loc_180024AA9
0x180024a5a  call    cs:__imp_GetLastError
0x180024a60  test    cs:byte_1800C8404, 8
0x180024a67  mov     ebx, eax
0x180024a69  jz      loc_180024B4E
0x180024a6f  mov     r8d, eax
0x180024a72  mov     word ptr [rsp+860h+var_810], di
0x180024a77  lea     rdx, aGetprocaddress_0; "GetProcAddress( GetIfTable ) failed: %d"
0x180024a7e  lea     rcx, [rsp+860h+var_810]
0x180024a83  call    FormatRRASErrorString
0x180024a88  test    cs:byte_1800C8404, 8
0x180024a8f  jz      loc_180024B4E
0x180024a95  lea     rcx, [rsp+860h+var_810]
0x180024a9a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024a9e  inc     rax
0x180024aa1  cmp     [rcx+rax*2], di
0x180024aa5  jnz     short loc_180024A9E
0x180024aa7  jmp     short loc_180024B12
0x180024aa9  mov     rcx, cs:hLibModule; hModule
0x180024ab0  lea     rdx, aGetipaddrtable; "GetIpAddrTable"
0x180024ab7  call    cs:__imp_GetProcAddress
0x180024abd  mov     cs:qword_1800C8530, rax
0x180024ac4  test    rax, rax
0x180024ac7  jnz     loc_180024B7B
0x180024acd  call    cs:__imp_GetLastError
0x180024ad3  test    cs:byte_1800C8404, 8
0x180024ada  mov     ebx, eax
0x180024adc  jz      short loc_180024B4E
0x180024ade  mov     r8d, eax
0x180024ae1  mov     word ptr [rsp+860h+var_810], di
0x180024ae6  lea     rdx, aGetprocaddress; "GetProcAddress( GetIpAddrTable ) failed"...
0x180024aed  lea     rcx, [rsp+860h+var_810]
0x180024af2  call    FormatRRASErrorString
0x180024af7  test    cs:byte_1800C8404, 8
0x180024afe  jz      short loc_180024B4E
0x180024b00  lea     rcx, [rsp+860h+var_810]
0x180024b05  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024b09  inc     rax
0x180024b0c  cmp     [rcx+rax*2], di
0x180024b10  jnz     short loc_180024B09
0x180024b12  lea     eax, ds:2[rax*2]
0x180024b19  mov     [rsp+860h+var_814], edi
0x180024b1d  lea     rcx, [rsp+860h+var_810]
0x180024b22  mov     [rsp+860h+var_818], eax
0x180024b26  lea     rax, [rsp+860h+var_830]
0x180024b2b  mov     [rsp+860h+var_820], rcx
0x180024b30  mov     r9d, 2
0x180024b36  mov     [rsp+860h+var_840], rax
0x180024b3b  lea     rdx, RasDdmTraceError
0x180024b42  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180024b49  call    McGenEventWrite_EventWriteTransfer
0x180024b4e  test    ebx, ebx
0x180024b50  jz      short loc_180024B7D
0x180024b52  mov     rcx, cs:hLibModule; hLibModule
0x180024b59  mov     cs:qword_1800C8528, rdi
0x180024b60  mov     cs:qword_1800C8530, rdi
0x180024b67  test    rcx, rcx
0x180024b6a  jz      short loc_180024B7D
0x180024b6c  call    cs:__imp_FreeLibrary
0x180024b72  mov     cs:hLibModule, rdi
0x180024b79  jmp     short loc_180024B7D
0x180024b7b  mov     ebx, edi
0x180024b7d  mov     eax, ebx
0x180024b7f  mov     rcx, [rbp+760h+var_10]
0x180024b86  xor     rcx, rsp; StackCookie
0x180024b89  call    __security_check_cookie
0x180024b8e  lea     r11, [rsp+860h+var_s0]
0x180024b96  mov     rbx, [r11+10h]
0x180024b9a  mov     rdi, [r11+18h]
0x180024b9e  mov     rsp, r11
0x180024ba1  pop     rbp
0x180024ba2  retn
```
