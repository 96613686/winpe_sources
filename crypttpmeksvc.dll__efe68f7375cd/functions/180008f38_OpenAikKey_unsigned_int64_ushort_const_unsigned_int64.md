# _OpenAikKey(unsigned __int64,ushort const *,unsigned __int64 *)

- ea: `0x180008f38`
- end: `0x18000910d`
- name: `?_OpenAikKey@@YAK_KPEBGPEA_K@Z`
- size: `469`
- prototype: `__int64 __fastcall(NCRYPT_PROV_HANDLE hProvider, LPCWSTR pszKeyName, NCRYPT_KEY_HANDLE *phKey)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004440`
- `0x180009880`

## callees

- `0x180003750`
- `0x180006f10`
- `0x180008f38`
- `0x18000a800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090c6`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180008fb2`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180008fb2`
- `ncrypt!NCryptSetProperty` at `0x180009028`
- `ncrypt!NCryptSetProperty` at `0x180009028`
- `ncrypt!NCryptOpenKey` at `0x180009048`
- `ncrypt!NCryptOpenKey` at `0x180009048`

## string_xrefs

- `0x180008f5f`: `\ServiceProfiles\LocalService\AppData\Local\Microsoft\Crypto\PCPKSP`
- `0x180008f6e`: `\System32\Config\SystemProfile\AppData\Local\Microsoft\Crypto\PCPKSP`
- `0x180009055`: `ERROR: NCryptOpenKey[%u: %ws]. Return=%x\n`
- `0x1800090d5`: `ERROR: NCryptOpenKey. Return=%x\n`

## pseudocode

```c
__int64 __fastcall _OpenAikKey(NCRYPT_PROV_HANDLE hProvider, LPCWSTR pszKeyName, NCRYPT_KEY_HANDLE *phKey)
{
  DWORD LastError; // ebx
  unsigned int i; // edi
  const unsigned __int16 *v8; // rbx
  UINT WindowsDirectoryW; // eax
  __int64 v10; // rax
  unsigned __int64 v11; // r9
  __int64 v13; // [rsp+28h] [rbp-280h]
  unsigned __int16 *v14; // [rsp+30h] [rbp-278h]
  const wchar_t *v15; // [rsp+38h] [rbp-270h]
  const wchar_t *v16; // [rsp+40h] [rbp-268h]
  WCHAR Buffer[264]; // [rsp+50h] [rbp-258h] BYREF

  v15 = L"\\ServiceProfiles\\LocalService\\AppData\\Local\\Microsoft\\Crypto\\PCPKSP";
  v14 = 0;
  v16 = L"\\System32\\Config\\SystemProfile\\AppData\\Local\\Microsoft\\Crypto\\PCPKSP";
  LastError = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
      goto LABEL_18;
    v8 = (&v14)[i];
    if ( !v8 )
      goto LABEL_11;
    WindowsDirectoryW = GetWindowsDirectoryW(Buffer, 0x104u);
    if ( !WindowsDirectoryW )
      break;
    if ( WindowsDirectoryW >= 0x104 )
    {
      LastError = -2147024785;
      goto LABEL_19;
    }
    LastError = StringCchCopyW(&Buffer[WindowsDirectoryW], 260LL - WindowsDirectoryW, v8);
    if ( LastError )
      goto LABEL_19;
    v10 = -1;
    do
      ++v10;
    while ( Buffer[v10] );
    v11 = 2 * v10 + 2;
    if ( v11 > 0x100000 )
    {
      LastError = -2147024362;
      ekTraceFmt(0xB812C2u, 1u, "ERROR: pwszPropertyValue. Return=%d\n", 2147942934LL);
      goto LABEL_15;
    }
    LastError = NCryptSetProperty(hProvider, L"PCP_ALTERNATE_KEY_STORAGE_LOCATION", (PBYTE)Buffer, v11, 0);
    if ( LastError )
    {
      ekTraceFmt(0xC412C2u, 1u, "ERROR: NCryptSetProperty. Return=%x\n", LastError);
LABEL_15:
      ekTraceFmt(0x10412C2u, 1u, "ERROR: _SetNCryptStringProperty. Return=%x\n", LastError);
      goto LABEL_19;
    }
LABEL_11:
    LODWORD(v13) = NCryptOpenKey(hProvider, phKey, pszKeyName, 0, 0x40u);
    LastError = v13;
    ekTraceFmt(0x10E12C2u, 1u, "ERROR: NCryptOpenKey[%u: %ws]. Return=%x\n", i, pszKeyName, v13, v14, v15, v16);
    if ( !LastError )
      return LastError;
  }
  LastError = GetLastError();
LABEL_18:
  if ( !LastError )
    return LastError;
LABEL_19:
  ekTraceFmt(0x11A12C2u, 1u, "ERROR: NCryptOpenKey. Return=%x\n", LastError);
  return LastError;
}

```

## disassembly

```asm
0x180008f38  push    rbx
0x180008f3a  push    rbp
0x180008f3b  push    rsi
0x180008f3c  push    rdi
0x180008f3d  push    r12
0x180008f3f  push    r14
0x180008f41  push    r15
0x180008f43  sub     rsp, 270h
0x180008f4a  mov     rax, cs:__security_cookie
0x180008f51  xor     rax, rsp
0x180008f54  mov     [rsp+2A8h+var_48], rax
0x180008f5c  xor     r15d, r15d
0x180008f5f  lea     rax, aServiceprofile; "\\ServiceProfiles\\LocalService\\AppDat"...
0x180008f66  mov     [rsp+2A8h+var_270], rax
0x180008f6b  mov     r14, r8
0x180008f6e  lea     rax, aSystem32Config; "\\System32\\Config\\SystemProfile\\AppD"...
0x180008f75  mov     [rsp+2A8h+var_278], r15
0x180008f7a  mov     [rsp+2A8h+var_268], rax
0x180008f7f  mov     rbp, rdx
0x180008f82  lea     r12d, [r15+1]
0x180008f86  mov     rsi, rcx
0x180008f89  mov     ebx, r15d
0x180008f8c  mov     edi, r15d
0x180008f8f  cmp     edi, 3
0x180008f92  jnb     loc_1800090CE
0x180008f98  mov     eax, edi
0x180008f9a  mov     rbx, [rsp+rax*8+2A8h+var_278]
0x180008f9f  test    rbx, rbx
0x180008fa2  jz      loc_180009034
0x180008fa8  mov     edx, 104h; uSize
0x180008fad  lea     rcx, [rsp+2A8h+Buffer]; lpBuffer
0x180008fb2  call    cs:__imp_GetWindowsDirectoryW
0x180008fb8  test    eax, eax
0x180008fba  jz      loc_1800090C6
0x180008fc0  cmp     eax, 104h
0x180008fc5  jnb     loc_1800090BF
0x180008fcb  mov     eax, eax
0x180008fcd  lea     rcx, [rsp+2A8h+Buffer]
0x180008fd2  mov     edx, 104h
0x180008fd7  mov     r8, rbx; unsigned __int16 *
0x180008fda  sub     rdx, rax; unsigned __int64
0x180008fdd  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x180008fe1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008fe6  mov     ebx, eax
0x180008fe8  test    eax, eax
0x180008fea  jnz     loc_1800090D2
0x180008ff0  lea     rcx, [rsp+2A8h+Buffer]
0x180008ff5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008ff9  inc     rax
0x180008ffc  cmp     [rcx+rax*2], r15w
0x180009001  jnz     short loc_180008FF9
0x180009003  lea     r9, ds:2[rax*2]; cbInput
0x18000900b  cmp     r9, 100000h
0x180009012  ja      short loc_18000908A
0x180009014  lea     r8, [rsp+2A8h+Buffer]; pbInput
0x180009019  mov     [rsp+2A8h+dwFlags], r15d; dwFlags
0x18000901e  lea     rdx, aPcpAlternateKe; "PCP_ALTERNATE_KEY_STORAGE_LOCATION"
0x180009025  mov     rcx, rsi; hObject
0x180009028  call    cs:__imp_NCryptSetProperty
0x18000902e  mov     ebx, eax
0x180009030  test    eax, eax
0x180009032  jnz     short loc_18000907C
0x180009034  xor     r9d, r9d; dwLegacyKeySpec
0x180009037  mov     [rsp+2A8h+dwFlags], 40h ; '@'; dwFlags
0x18000903f  mov     r8, rbp; pszKeyName
0x180009042  mov     rdx, r14; phKey
0x180009045  mov     rcx, rsi; hProvider
0x180009048  call    cs:__imp_NCryptOpenKey
0x18000904e  mov     dword ptr [rsp+2A8h+var_280], eax
0x180009052  mov     r9d, edi
0x180009055  lea     r8, aErrorNcryptope_2; "ERROR: NCryptOpenKey[%u: %ws]. Return=%"...
0x18000905c  mov     qword ptr [rsp+2A8h+dwFlags], rbp
0x180009061  mov     edx, r12d; unsigned int
0x180009064  mov     ecx, 10E12C2h; unsigned int
0x180009069  mov     ebx, eax
0x18000906b  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180009070  test    ebx, ebx
0x180009072  jz      short loc_1800090E9
0x180009074  add     edi, r12d
0x180009077  jmp     loc_180008F8F
0x18000907c  mov     ecx, 0C412C2h
0x180009081  lea     r8, aErrorNcryptset; "ERROR: NCryptSetProperty. Return=%x\n"
0x180009088  jmp     short loc_18000909B
0x18000908a  mov     ebx, 80070216h
0x18000908f  lea     r8, aErrorPwszprope; "ERROR: pwszPropertyValue. Return=%d\n"
0x180009096  mov     ecx, 0B812C2h; unsigned int
0x18000909b  mov     r9d, ebx
0x18000909e  mov     edx, r12d; unsigned int
0x1800090a1  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800090a6  mov     r9d, ebx
0x1800090a9  lea     r8, aErrorSetncrypt; "ERROR: _SetNCryptStringProperty. Return"...
0x1800090b0  mov     edx, r12d; unsigned int
0x1800090b3  mov     ecx, 10412C2h; unsigned int
0x1800090b8  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800090bd  jmp     short loc_1800090D2
0x1800090bf  mov     ebx, 8007006Fh
0x1800090c4  jmp     short loc_1800090D2
0x1800090c6  call    cs:__imp_GetLastError
0x1800090cc  mov     ebx, eax
0x1800090ce  test    ebx, ebx
0x1800090d0  jz      short loc_1800090E9
0x1800090d2  mov     r9d, ebx
0x1800090d5  lea     r8, aErrorNcryptope_0; "ERROR: NCryptOpenKey. Return=%x\n"
0x1800090dc  mov     edx, r12d; unsigned int
0x1800090df  mov     ecx, 11A12C2h; unsigned int
0x1800090e4  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800090e9  mov     eax, ebx
0x1800090eb  mov     rcx, [rsp+2A8h+var_48]
0x1800090f3  xor     rcx, rsp; StackCookie
0x1800090f6  call    __security_check_cookie
0x1800090fb  add     rsp, 270h
0x180009102  pop     r15
0x180009104  pop     r14
0x180009106  pop     r12
0x180009108  pop     rdi
0x180009109  pop     rsi
0x18000910a  pop     rbp
0x18000910b  pop     rbx
0x18000910c  retn
```
