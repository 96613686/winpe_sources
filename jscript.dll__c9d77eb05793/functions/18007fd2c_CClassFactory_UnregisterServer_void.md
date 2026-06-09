# CClassFactory::UnregisterServer(void)

- ea: `0x18007fd2c`
- end: `0x180080141`
- name: `?UnregisterServer@CClassFactory@@QEAAJXZ`
- size: `1045`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180073460`
- `0x18007f5cc`

## callees

- `0x18007fc64`
- `0x18007fd2c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x18007fd7e`
- `ADVAPI32!RegOpenKeyExA` at `0x18007fda3`
- `ADVAPI32!RegOpenKeyExA` at `0x18007fdd9`
- `ADVAPI32!RegOpenKeyExA` at `0x18007ff77`
- `ADVAPI32!RegOpenKeyExA` at `0x18008005e`
- `ADVAPI32!RegOpenKeyExA` at `0x18007fd7e`
- `ADVAPI32!RegOpenKeyExA` at `0x18007fda3`
- `ADVAPI32!RegOpenKeyExA` at `0x18007fdd9`
- `ADVAPI32!RegOpenKeyExA` at `0x18007ff77`
- `ADVAPI32!RegOpenKeyExA` at `0x18008005e`
- `ADVAPI32!RegCloseKey` at `0x18007fdb5`
- `ADVAPI32!RegCloseKey` at `0x18007fdeb`
- `ADVAPI32!RegCloseKey` at `0x18007feaf`
- `ADVAPI32!RegCloseKey` at `0x18007fec1`
- `ADVAPI32!RegCloseKey` at `0x18007ffc8`
- `ADVAPI32!RegCloseKey` at `0x1800800e0`
- `ADVAPI32!RegCloseKey` at `0x180080103`
- `ADVAPI32!RegCloseKey` at `0x18007fdb5`
- `ADVAPI32!RegCloseKey` at `0x18007fdeb`
- `ADVAPI32!RegCloseKey` at `0x18007feaf`
- `ADVAPI32!RegCloseKey` at `0x18007fec1`
- `ADVAPI32!RegCloseKey` at `0x18007ffc8`
- `ADVAPI32!RegCloseKey` at `0x1800800e0`
- `ADVAPI32!RegCloseKey` at `0x180080103`
- `ADVAPI32!RegCreateKeyExA` at `0x180080036`
- `ADVAPI32!RegCreateKeyExA` at `0x180080036`
- `ADVAPI32!RegDeleteKeyExA` at `0x18007fe02`
- `ADVAPI32!RegDeleteKeyExA` at `0x18007fea5`
- `ADVAPI32!RegDeleteKeyExA` at `0x18007ff9d`
- `ADVAPI32!RegDeleteKeyExA` at `0x18007ffb9`
- `ADVAPI32!RegDeleteKeyExA` at `0x18007ffe6`
- `ADVAPI32!RegDeleteKeyExA` at `0x18008007d`
- `ADVAPI32!RegDeleteKeyExA` at `0x180080099`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800800b5`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800800d1`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800800f4`
- `ADVAPI32!RegDeleteKeyExA` at `0x18008011b`
- `ADVAPI32!RegDeleteKeyExA` at `0x18007fe02`
- `ADVAPI32!RegDeleteKeyExA` at `0x18007fea5`
- `ADVAPI32!RegDeleteKeyExA` at `0x18007ff9d`
- `ADVAPI32!RegDeleteKeyExA` at `0x18007ffb9`
- `ADVAPI32!RegDeleteKeyExA` at `0x18007ffe6`
- `ADVAPI32!RegDeleteKeyExA` at `0x18008007d`
- `ADVAPI32!RegDeleteKeyExA` at `0x180080099`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800800b5`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800800d1`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800800f4`
- `ADVAPI32!RegDeleteKeyExA` at `0x18008011b`

## string_xrefs

- `0x18007fd6e`: `CLSID`
- `0x18007ff90`: `CLSID`
- `0x180080010`: `CLSID`

## pseudocode

```c
__int64 __fastcall CClassFactory::UnregisterServer(CClassFactory *this)
{
  unsigned int v2; // r14d
  unsigned int v4; // edi
  int i; // r14d
  const CHAR *v6; // rdx
  GUID v7; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp+40h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( !RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0x2000000u, &hKey) )
  {
    if ( !RegOpenKeyExA(hKey, *((LPCSTR *)this + 3), 0, 0x2000000u, &phkResult) )
    {
      RegCloseKey(hKey);
      hKey = phkResult;
      if ( !RegOpenKeyExA(phkResult, "InprocServer", 0, 0x2000000u, &phkResult) )
      {
        RegCloseKey(phkResult);
        v2 = RegDeleteKeyExA(hKey, "InprocServer32", 0, 0) != 0 ? 0x80004005 : 0;
        if ( (*((_BYTE *)this + 84) & 1) != 0 )
        {
          v7 = CATID_ActiveScript;
          UnRegisterCLSIDInCategory((char *)this + 68, &v7);
        }
        if ( (*((_BYTE *)this + 84) & 2) != 0 )
        {
          v7 = CATID_ActiveScriptParse;
          UnRegisterCLSIDInCategory((char *)this + 68, &v7);
        }
        if ( (*((_BYTE *)this + 84) & 4) != 0 )
        {
          v7 = CATID_ActiveScriptAuthor;
          UnRegisterCLSIDInCategory((char *)this + 68, &v7);
        }
        if ( (*((_BYTE *)this + 84) & 8) != 0 )
        {
          v7 = CATID_ActiveScriptEncode;
          UnRegisterCLSIDInCategory((char *)this + 68, &v7);
        }
        RegDeleteKeyExA(hKey, "Implemented Categories", 0, 0);
        RegCloseKey(hKey);
        return v2;
      }
    }
    RegCloseKey(hKey);
  }
  v4 = 0;
  if ( (*((_BYTE *)this + 84) & 1) != 0 )
  {
    v7 = CATID_ActiveScript;
    UnRegisterCLSIDInCategory((char *)this + 68, &v7);
  }
  if ( (*((_BYTE *)this + 84) & 2) != 0 )
  {
    v7 = CATID_ActiveScriptParse;
    UnRegisterCLSIDInCategory((char *)this + 68, &v7);
  }
  if ( (*((_BYTE *)this + 84) & 4) != 0 )
  {
    v7 = CATID_ActiveScriptAuthor;
    UnRegisterCLSIDInCategory((char *)this + 68, &v7);
  }
  if ( (*((_BYTE *)this + 84) & 8) != 0 )
  {
    v7 = CATID_ActiveScriptEncode;
    UnRegisterCLSIDInCategory((char *)this + 68, &v7);
  }
  for ( i = 0; i < *((_DWORD *)this + 16); ++i )
  {
    if ( RegOpenKeyExA(HKEY_CLASSES_ROOT, *(LPCSTR *)(*((_QWORD *)this + 7) + 8LL * i), 0, 0x2000000u, &hKey) )
    {
      v4 = -2147467259;
    }
    else
    {
      if ( RegDeleteKeyExA(hKey, "CLSID", 0, 0) )
        v4 = -2147467259;
      if ( RegDeleteKeyExA(hKey, "OLEScript", 0, 0) )
        v4 = -2147467259;
      RegCloseKey(hKey);
      if ( RegDeleteKeyExA(HKEY_CLASSES_ROOT, *(LPCSTR *)(*((_QWORD *)this + 7) + 8LL * i), 0, 0) )
        v4 = -2147467259;
    }
  }
  if ( RegCreateKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0, 0, 0x2000000u, 0, &hKey, 0) )
  {
    v4 = -2147467259;
  }
  else
  {
    if ( RegOpenKeyExA(hKey, *((LPCSTR *)this + 3), 0, 0x2000000u, &phkResult) )
    {
      v4 = -2147467259;
    }
    else
    {
      if ( RegDeleteKeyExA(phkResult, "ProgID", 0, 0) )
        v4 = -2147467259;
      if ( RegDeleteKeyExA(phkResult, "OLEScript", 0, 0) )
        v4 = -2147467259;
      if ( RegDeleteKeyExA(phkResult, "Implemented Categories", 0, 0) )
        v4 = -2147467259;
      if ( RegDeleteKeyExA(phkResult, "InprocServer32", 0, 0) )
        v4 = -2147467259;
      RegCloseKey(phkResult);
    }
    if ( RegDeleteKeyExA(hKey, *((LPCSTR *)this + 3), 0, 0) )
      v4 = -2147467259;
    RegCloseKey(hKey);
  }
  v6 = (const CHAR *)*((_QWORD *)this + 5);
  if ( v6 && RegDeleteKeyExA(HKEY_CLASSES_ROOT, v6, 0, 0) )
    return (unsigned int)-2147467259;
  return v4;
}

```

## disassembly

```asm
0x18007fd2c  mov     [rsp-28h+arg_0], rbx
0x18007fd31  mov     [rsp-28h+arg_18], rsi
0x18007fd36  push    rbp
0x18007fd37  push    rdi
0x18007fd38  push    r13
0x18007fd3a  push    r14
0x18007fd3c  push    r15
0x18007fd3e  mov     rbp, rsp
0x18007fd41  sub     rsp, 60h
0x18007fd45  mov     rbx, rcx
0x18007fd48  mov     [rbp+hKey], 0
0x18007fd50  lea     rax, [rbp+hKey]
0x18007fd54  mov     [rbp+arg_10], 0
0x18007fd5c  mov     r13d, 2000000h
0x18007fd62  mov     [rsp+60h+phkResult], rax; phkResult
0x18007fd67  mov     r15, 0FFFFFFFF80000000h
0x18007fd6e  lea     rdx, aClsid; "CLSID"
0x18007fd75  mov     r9d, r13d; samDesired
0x18007fd78  mov     rcx, r15; hKey
0x18007fd7b  xor     r8d, r8d; ulOptions
0x18007fd7e  call    cs:__imp_RegOpenKeyExA
0x18007fd84  test    eax, eax
0x18007fd86  jnz     loc_18007FEC7
0x18007fd8c  mov     rdx, [rbx+18h]; lpSubKey
0x18007fd90  lea     rax, [rbp+arg_10]
0x18007fd94  mov     rcx, [rbp+hKey]; hKey
0x18007fd98  mov     r9d, r13d; samDesired
0x18007fd9b  xor     r8d, r8d; ulOptions
0x18007fd9e  mov     [rsp+60h+phkResult], rax; phkResult
0x18007fda3  call    cs:__imp_RegOpenKeyExA
0x18007fda9  test    eax, eax
0x18007fdab  jnz     loc_18007FEBD
0x18007fdb1  mov     rcx, [rbp+hKey]; hKey
0x18007fdb5  call    cs:__imp_RegCloseKey
0x18007fdbb  mov     rcx, [rbp+arg_10]; hKey
0x18007fdbf  lea     rax, [rbp+arg_10]
0x18007fdc3  mov     r9d, r13d; samDesired
0x18007fdc6  mov     [rbp+hKey], rcx
0x18007fdca  xor     r8d, r8d; ulOptions
0x18007fdcd  mov     [rsp+60h+phkResult], rax; phkResult
0x18007fdd2  lea     rdx, aInprocserver; "InprocServer"
0x18007fdd9  call    cs:__imp_RegOpenKeyExA
0x18007fddf  test    eax, eax
0x18007fde1  jnz     loc_18007FEBD
0x18007fde7  mov     rcx, [rbp+arg_10]; hKey
0x18007fdeb  call    cs:__imp_RegCloseKey
0x18007fdf1  mov     rcx, [rbp+hKey]; hKey
0x18007fdf5  lea     rdx, aInprocserver32; "InprocServer32"
0x18007fdfc  xor     r9d, r9d; Reserved
0x18007fdff  xor     r8d, r8d; samDesired
0x18007fe02  call    cs:__imp_RegDeleteKeyExA
0x18007fe08  xor     ecx, ecx
0x18007fe0a  lea     rdi, [rbx+44h]
0x18007fe0e  sub     ecx, eax
0x18007fe10  neg     ecx
0x18007fe12  sbb     r14d, r14d
0x18007fe15  and     r14d, 80004005h
0x18007fe1c  test    byte ptr [rbx+54h], 1
0x18007fe20  jz      short loc_18007FE3A
0x18007fe22  movups  xmm0, xmmword ptr cs:CATID_ActiveScript.Data1
0x18007fe29  lea     rdx, [rbp+var_10]
0x18007fe2d  mov     rcx, rdi
0x18007fe30  movdqu  [rbp+var_10], xmm0
0x18007fe35  call    UnRegisterCLSIDInCategory
0x18007fe3a  test    byte ptr [rbx+54h], 2
0x18007fe3e  jz      short loc_18007FE58
0x18007fe40  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptParse.Data1
0x18007fe47  lea     rdx, [rbp+var_10]
0x18007fe4b  mov     rcx, rdi
0x18007fe4e  movdqu  [rbp+var_10], xmm0
0x18007fe53  call    UnRegisterCLSIDInCategory
0x18007fe58  test    byte ptr [rbx+54h], 4
0x18007fe5c  jz      short loc_18007FE76
0x18007fe5e  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptAuthor.Data1
0x18007fe65  lea     rdx, [rbp+var_10]
0x18007fe69  mov     rcx, rdi
0x18007fe6c  movdqu  [rbp+var_10], xmm0
0x18007fe71  call    UnRegisterCLSIDInCategory
0x18007fe76  test    byte ptr [rbx+54h], 8
0x18007fe7a  jz      short loc_18007FE94
0x18007fe7c  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptEncode.Data1
0x18007fe83  lea     rdx, [rbp+var_10]
0x18007fe87  mov     rcx, rdi
0x18007fe8a  movdqu  [rbp+var_10], xmm0
0x18007fe8f  call    UnRegisterCLSIDInCategory
0x18007fe94  mov     rcx, [rbp+hKey]; hKey
0x18007fe98  lea     rdx, aImplementedCat; "Implemented Categories"
0x18007fe9f  xor     r9d, r9d; Reserved
0x18007fea2  xor     r8d, r8d; samDesired
0x18007fea5  call    cs:__imp_RegDeleteKeyExA
0x18007feab  mov     rcx, [rbp+hKey]; hKey
0x18007feaf  call    cs:__imp_RegCloseKey
0x18007feb5  mov     eax, r14d
0x18007feb8  jmp     loc_180080128
0x18007febd  mov     rcx, [rbp+hKey]; hKey
0x18007fec1  call    cs:__imp_RegCloseKey
0x18007fec7  xor     edi, edi
0x18007fec9  lea     rsi, [rbx+44h]
0x18007fecd  test    byte ptr [rbx+54h], 1
0x18007fed1  jz      short loc_18007FEEB
0x18007fed3  movups  xmm0, xmmword ptr cs:CATID_ActiveScript.Data1
0x18007feda  lea     rdx, [rbp+var_10]
0x18007fede  mov     rcx, rsi
0x18007fee1  movdqu  [rbp+var_10], xmm0
0x18007fee6  call    UnRegisterCLSIDInCategory
0x18007feeb  test    byte ptr [rbx+54h], 2
0x18007feef  jz      short loc_18007FF09
0x18007fef1  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptParse.Data1
0x18007fef8  lea     rdx, [rbp+var_10]
0x18007fefc  mov     rcx, rsi
0x18007feff  movdqu  [rbp+var_10], xmm0
0x18007ff04  call    UnRegisterCLSIDInCategory
0x18007ff09  test    byte ptr [rbx+54h], 4
0x18007ff0d  jz      short loc_18007FF27
0x18007ff0f  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptAuthor.Data1
0x18007ff16  lea     rdx, [rbp+var_10]
0x18007ff1a  mov     rcx, rsi
0x18007ff1d  movdqu  [rbp+var_10], xmm0
0x18007ff22  call    UnRegisterCLSIDInCategory
0x18007ff27  test    byte ptr [rbx+54h], 8
0x18007ff2b  jz      short loc_18007FF45
0x18007ff2d  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptEncode.Data1
0x18007ff34  lea     rdx, [rbp+var_10]
0x18007ff38  mov     rcx, rsi
0x18007ff3b  movdqu  [rbp+var_10], xmm0
0x18007ff40  call    UnRegisterCLSIDInCategory
0x18007ff45  xor     r14d, r14d
0x18007ff48  mov     esi, 80004005h
0x18007ff4d  cmp     [rbx+40h], edi
0x18007ff50  jle     loc_18007FFFE
0x18007ff56  mov     rdx, [rbx+38h]
0x18007ff5a  lea     rax, [rbp+hKey]
0x18007ff5e  movsxd  r15, r14d
0x18007ff61  mov     r9d, r13d; samDesired
0x18007ff64  xor     r8d, r8d; ulOptions
0x18007ff67  mov     [rsp+60h+phkResult], rax; phkResult
0x18007ff6c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18007ff73  mov     rdx, [rdx+r15*8]; lpSubKey
0x18007ff77  call    cs:__imp_RegOpenKeyExA
0x18007ff7d  test    eax, eax
0x18007ff7f  jz      short loc_18007FF8C
0x18007ff81  mov     edi, esi
0x18007ff83  mov     r15, 0FFFFFFFF80000000h
0x18007ff8a  jmp     short loc_18007FFF1
0x18007ff8c  mov     rcx, [rbp+hKey]; hKey
0x18007ff90  lea     rdx, aClsid; "CLSID"
0x18007ff97  xor     r9d, r9d; Reserved
0x18007ff9a  xor     r8d, r8d; samDesired
0x18007ff9d  call    cs:__imp_RegDeleteKeyExA
0x18007ffa3  mov     rcx, [rbp+hKey]; hKey
0x18007ffa7  lea     rdx, aOlescript; "OLEScript"
0x18007ffae  test    eax, eax
0x18007ffb0  cmovnz  edi, esi
0x18007ffb3  xor     r9d, r9d; Reserved
0x18007ffb6  xor     r8d, r8d; samDesired
0x18007ffb9  call    cs:__imp_RegDeleteKeyExA
0x18007ffbf  mov     rcx, [rbp+hKey]; hKey
0x18007ffc3  test    eax, eax
0x18007ffc5  cmovnz  edi, esi
0x18007ffc8  call    cs:__imp_RegCloseKey
0x18007ffce  mov     rdx, [rbx+38h]
0x18007ffd2  xor     r9d, r9d; Reserved
0x18007ffd5  xor     r8d, r8d; samDesired
0x18007ffd8  mov     rdx, [rdx+r15*8]; lpSubKey
0x18007ffdc  mov     r15, 0FFFFFFFF80000000h
0x18007ffe3  mov     rcx, r15; hKey
0x18007ffe6  call    cs:__imp_RegDeleteKeyExA
0x18007ffec  test    eax, eax
0x18007ffee  cmovnz  edi, esi
0x18007fff1  inc     r14d
0x18007fff4  cmp     r14d, [rbx+40h]
0x18007fff8  jl      loc_18007FF56
0x18007fffe  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x180080007  lea     rax, [rbp+hKey]
0x18008000b  mov     [rsp+60h+var_28], rax; phkResult
0x180080010  lea     rdx, aClsid; "CLSID"
0x180080017  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180080020  xor     r9d, r9d; lpClass
0x180080023  mov     [rsp+60h+samDesired], r13d; samDesired
0x180080028  xor     r8d, r8d; Reserved
0x18008002b  mov     rcx, r15; hKey
0x18008002e  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x180080036  call    cs:__imp_RegCreateKeyExA
0x18008003c  test    eax, eax
0x18008003e  jz      short loc_180080047
0x180080040  mov     edi, esi
0x180080042  jmp     loc_180080109
0x180080047  mov     rdx, [rbx+18h]; lpSubKey
0x18008004b  lea     rax, [rbp+arg_10]
0x18008004f  mov     rcx, [rbp+hKey]; hKey
0x180080053  mov     r9d, r13d; samDesired
0x180080056  xor     r8d, r8d; ulOptions
0x180080059  mov     [rsp+60h+phkResult], rax; phkResult
0x18008005e  call    cs:__imp_RegOpenKeyExA
0x180080064  test    eax, eax
0x180080066  jz      short loc_18008006C
0x180080068  mov     edi, esi
0x18008006a  jmp     short loc_1800800E6
0x18008006c  mov     rcx, [rbp+arg_10]; hKey
0x180080070  lea     rdx, aProgid; "ProgID"
0x180080077  xor     r9d, r9d; Reserved
0x18008007a  xor     r8d, r8d; samDesired
0x18008007d  call    cs:__imp_RegDeleteKeyExA
0x180080083  mov     rcx, [rbp+arg_10]; hKey
0x180080087  lea     rdx, aOlescript; "OLEScript"
0x18008008e  test    eax, eax
0x180080090  cmovnz  edi, esi
0x180080093  xor     r9d, r9d; Reserved
0x180080096  xor     r8d, r8d; samDesired
0x180080099  call    cs:__imp_RegDeleteKeyExA
0x18008009f  mov     rcx, [rbp+arg_10]; hKey
0x1800800a3  lea     rdx, aImplementedCat; "Implemented Categories"
0x1800800aa  test    eax, eax
0x1800800ac  cmovnz  edi, esi
0x1800800af  xor     r9d, r9d; Reserved
0x1800800b2  xor     r8d, r8d; samDesired
0x1800800b5  call    cs:__imp_RegDeleteKeyExA
0x1800800bb  mov     rcx, [rbp+arg_10]; hKey
0x1800800bf  lea     rdx, aInprocserver32; "InprocServer32"
0x1800800c6  test    eax, eax
0x1800800c8  cmovnz  edi, esi
0x1800800cb  xor     r9d, r9d; Reserved
0x1800800ce  xor     r8d, r8d; samDesired
0x1800800d1  call    cs:__imp_RegDeleteKeyExA
0x1800800d7  mov     rcx, [rbp+arg_10]; hKey
0x1800800db  test    eax, eax
0x1800800dd  cmovnz  edi, esi
0x1800800e0  call    cs:__imp_RegCloseKey
0x1800800e6  mov     rdx, [rbx+18h]; lpSubKey
0x1800800ea  xor     r9d, r9d; Reserved
0x1800800ed  mov     rcx, [rbp+hKey]; hKey
0x1800800f1  xor     r8d, r8d; samDesired
0x1800800f4  call    cs:__imp_RegDeleteKeyExA
0x1800800fa  mov     rcx, [rbp+hKey]; hKey
0x1800800fe  test    eax, eax
0x180080100  cmovnz  edi, esi
0x180080103  call    cs:__imp_RegCloseKey
0x180080109  mov     rdx, [rbx+28h]; lpSubKey
0x18008010d  test    rdx, rdx
0x180080110  jz      short loc_180080126
0x180080112  xor     r9d, r9d; Reserved
0x180080115  xor     r8d, r8d; samDesired
0x180080118  mov     rcx, r15; hKey
0x18008011b  call    cs:__imp_RegDeleteKeyExA
0x180080121  test    eax, eax
0x180080123  cmovnz  edi, esi
0x180080126  mov     eax, edi
0x180080128  lea     r11, [rsp+60h+var_s0]
0x18008012d  mov     rbx, [r11+30h]
0x180080131  mov     rsi, [r11+48h]
0x180080135  mov     rsp, r11
0x180080138  pop     r15
0x18008013a  pop     r14
0x18008013c  pop     r13
0x18008013e  pop     rdi
0x18008013f  pop     rbp
0x180080140  retn
```
