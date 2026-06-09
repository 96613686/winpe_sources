# GetTypeLibraryFromTypeLibKey

- ea: `0x180054efc`
- end: `0x180055221`
- name: `GetTypeLibraryFromTypeLibKey`
- size: `805`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180091680`

## callees

- `0x180054efc`
- `0x180058dc8`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `msvcrt!atoi` at `0x1800550e5`
- `msvcrt!atoi` at `0x180055100`
- `msvcrt!atoi` at `0x1800550e5`
- `msvcrt!atoi` at `0x180055100`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180055174`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180055174`
- `ADVAPI32!RegOpenKeyExA` at `0x180054f86`
- `ADVAPI32!RegOpenKeyExA` at `0x180055039`
- `ADVAPI32!RegOpenKeyExA` at `0x180054f86`
- `ADVAPI32!RegOpenKeyExA` at `0x180055039`
- `ADVAPI32!RegCloseKey` at `0x1800551b0`
- `ADVAPI32!RegCloseKey` at `0x1800551cf`
- `ADVAPI32!RegCloseKey` at `0x1800551b0`
- `ADVAPI32!RegCloseKey` at `0x1800551cf`
- `ADVAPI32!RegQueryValueExA` at `0x180054fcd`
- `ADVAPI32!RegQueryValueExA` at `0x18005507b`
- `ADVAPI32!RegQueryValueExA` at `0x180054fcd`
- `ADVAPI32!RegQueryValueExA` at `0x18005507b`
- `KERNEL32!MultiByteToWideChar` at `0x18005512d`
- `KERNEL32!MultiByteToWideChar` at `0x18005512d`
- `ole32!CLSIDFromString` at `0x180055146`
- `ole32!CLSIDFromString` at `0x180055146`

## pseudocode

```c
__int64 __fastcall GetTypeLibraryFromTypeLibKey(HKEY hKey, ITypeLib **a2)
{
  LSTATUS v4; // eax
  int v5; // ebx
  LSTATUS v6; // eax
  __int64 v7; // rax
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  __int64 v10; // rdx
  const char *v11; // rdi
  __int64 i; // rbx
  WORD v13; // si
  WORD v14; // di
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD lpcbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  ITypeLib *pptlib; // [rsp+50h] [rbp-B0h] BYREF
  CLSID pclsid; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v23[16]; // [rsp+68h] [rbp-98h] BYREF
  CHAR Data[56]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR WideCharStr[48]; // [rsp+B0h] [rbp-50h] BYREF

  *a2 = 0;
  hKeya = 0;
  phkResult = 0;
  cbData = 48;
  lpcbData = 10;
  pclsid = 0;
  Type = 0;
  pptlib = 0;
  v4 = RegOpenKeyExA(hKey, "TypeLib", 0, 0x20019u, &hKeya);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
    v6 = RegQueryValueExA(hKeya, 0, 0, &Type, (LPBYTE)Data, &cbData);
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( v5 >= 0 )
    {
      if ( Type != 1 )
        goto LABEL_32;
      if ( !cbData )
        goto LABEL_32;
      v7 = cbData - 1;
      if ( (unsigned int)v7 >= 0x2F )
        goto LABEL_32;
      Data[v7] = 0;
      v8 = RegOpenKeyExA(hKey, "Version", 0, 0x20019u, &phkResult);
      v5 = v8;
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      if ( v5 >= 0 )
      {
        v9 = RegQueryValueExA(phkResult, 0, 0, &Type, v23, &lpcbData);
        v5 = v9;
        if ( v9 > 0 )
          v5 = (unsigned __int16)v9 | 0x80070000;
        if ( v5 >= 0 )
        {
          if ( Type == 1 && lpcbData )
          {
            v11 = 0;
            for ( i = 0; (unsigned int)i < lpcbData; i = (unsigned int)(i + 1) )
            {
              if ( v23[i] == 46 )
              {
                if ( (unsigned int)i >= 0xAuLL )
                  _report_rangecheckfailure(lpcbData, v10);
                v23[i] = 0;
                v11 = (const char *)&v23[(unsigned int)(i + 1)];
                break;
              }
            }
            v13 = atoi((const char *)v23);
            v14 = (_DWORD)i == lpcbData ? 0 : atoi(v11);
            if ( MultiByteToWideChar(0, 0, Data, -1, WideCharStr, 48) )
            {
              v5 = CLSIDFromString(WideCharStr, &pclsid);
              if ( v5 >= 0 )
              {
                v5 = LoadRegTypeLib(&pclsid, v13, v14, 0x400u, &pptlib);
                if ( v5 >= 0 )
                {
                  v5 = 0;
                  *a2 = pptlib;
                  pptlib = 0;
                }
              }
              goto LABEL_33;
            }
          }
LABEL_32:
          v5 = -2147467259;
        }
      }
    }
  }
LABEL_33:
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( pptlib )
    ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180054efc  mov     [rsp-8+arg_10], rbx
0x180054f01  mov     [rsp-8+arg_18], rsi
0x180054f06  push    rbp
0x180054f07  push    rdi
0x180054f08  push    r14
0x180054f0a  lea     rbp, [rsp-20h]
0x180054f0f  sub     rsp, 120h
0x180054f16  mov     rax, cs:__security_cookie
0x180054f1d  xor     rax, rsp
0x180054f20  mov     [rbp+30h+var_20], rax
0x180054f24  mov     r14, rdx
0x180054f27  mov     qword ptr [rdx], 0
0x180054f2e  xorps   xmm0, xmm0
0x180054f31  mov     [rsp+130h+hKey], 0
0x180054f3a  lea     rax, [rsp+130h+hKey]
0x180054f3f  mov     [rsp+130h+var_E8], 0
0x180054f48  lea     rdx, aTypelib; "TypeLib"
0x180054f4f  mov     [rsp+130h+phkResult], rax; phkResult
0x180054f54  mov     r9d, 20019h; samDesired
0x180054f5a  mov     [rsp+130h+cbData], 30h ; '0'
0x180054f62  xor     r8d, r8d; ulOptions
0x180054f65  mov     [rsp+130h+var_FC], 0Ah
0x180054f6d  movups  xmmword ptr [rsp+130h+pclsid.Data1], xmm0
0x180054f72  mov     rdi, rcx
0x180054f75  mov     [rsp+130h+Type], 0
0x180054f7d  mov     [rsp+130h+pptlib], 0
0x180054f86  call    cs:__imp_RegOpenKeyExA
0x180054f8d  nop     dword ptr [rax+rax+00h]
0x180054f92  mov     ebx, eax
0x180054f94  mov     esi, 80070000h
0x180054f99  test    eax, eax
0x180054f9b  jle     short loc_180054FA2
0x180054f9d  movzx   ebx, ax
0x180054fa0  or      ebx, esi
0x180054fa2  test    ebx, ebx
0x180054fa4  js      loc_1800551A6
0x180054faa  mov     rcx, [rsp+130h+hKey]; hKey
0x180054faf  lea     rax, [rsp+130h+cbData]
0x180054fb4  mov     [rsp+130h+lpcbData], rax; lpcbData
0x180054fb9  lea     r9, [rsp+130h+Type]; lpType
0x180054fbe  lea     rax, [rsp+130h+Data]
0x180054fc3  xor     r8d, r8d; lpReserved
0x180054fc6  xor     edx, edx; lpValueName
0x180054fc8  mov     [rsp+130h+phkResult], rax; lpData
0x180054fcd  call    cs:__imp_RegQueryValueExA
0x180054fd4  nop     dword ptr [rax+rax+00h]
0x180054fd9  mov     ebx, eax
0x180054fdb  test    eax, eax
0x180054fdd  jle     short loc_180054FE4
0x180054fdf  movzx   ebx, ax
0x180054fe2  or      ebx, esi
0x180054fe4  test    ebx, ebx
0x180054fe6  js      loc_1800551A6
0x180054fec  cmp     [rsp+130h+Type], 1
0x180054ff1  jnz     loc_1800551A1
0x180054ff7  mov     eax, [rsp+130h+cbData]
0x180054ffb  test    eax, eax
0x180054ffd  jz      loc_1800551A1
0x180055003  dec     eax
0x180055005  cmp     eax, 2Fh ; '/'
0x180055008  jnb     loc_1800551A1
0x18005500e  cmp     eax, 30h ; '0'
0x180055011  jnb     loc_18005519B
0x180055017  mov     [rsp+rax+130h+Data], 0
0x18005501c  lea     rdx, aVersion; "Version"
0x180055023  lea     rax, [rsp+130h+var_E8]
0x180055028  mov     r9d, 20019h; samDesired
0x18005502e  xor     r8d, r8d; ulOptions
0x180055031  mov     [rsp+130h+phkResult], rax; phkResult
0x180055036  mov     rcx, rdi; hKey
0x180055039  call    cs:__imp_RegOpenKeyExA
0x180055040  nop     dword ptr [rax+rax+00h]
0x180055045  mov     ebx, eax
0x180055047  test    eax, eax
0x180055049  jle     short loc_180055050
0x18005504b  movzx   ebx, ax
0x18005504e  or      ebx, esi
0x180055050  test    ebx, ebx
0x180055052  js      loc_1800551A6
0x180055058  mov     rcx, [rsp+130h+var_E8]; hKey
0x18005505d  lea     rax, [rsp+130h+var_FC]
0x180055062  mov     [rsp+130h+lpcbData], rax; lpcbData
0x180055067  lea     r9, [rsp+130h+Type]; lpType
0x18005506c  lea     rax, [rsp+130h+var_C8]
0x180055071  xor     r8d, r8d; lpReserved
0x180055074  xor     edx, edx; lpValueName
0x180055076  mov     [rsp+130h+phkResult], rax; lpData
0x18005507b  call    cs:__imp_RegQueryValueExA
0x180055082  nop     dword ptr [rax+rax+00h]
0x180055087  mov     ebx, eax
0x180055089  test    eax, eax
0x18005508b  jle     short loc_180055092
0x18005508d  movzx   ebx, ax
0x180055090  or      ebx, esi
0x180055092  test    ebx, ebx
0x180055094  js      loc_1800551A6
0x18005509a  cmp     [rsp+130h+Type], 1
0x18005509f  jnz     loc_1800551A1
0x1800550a5  mov     ecx, [rsp+130h+var_FC]
0x1800550a9  test    ecx, ecx
0x1800550ab  jz      loc_1800551A1
0x1800550b1  xor     edi, edi
0x1800550b3  xor     ebx, ebx
0x1800550b5  cmp     ebx, ecx
0x1800550b7  jnb     short loc_1800550E0
0x1800550b9  cmp     [rsp+rbx+130h+var_C8], 2Eh ; '.'
0x1800550be  mov     eax, ebx
0x1800550c0  jz      short loc_1800550C6
0x1800550c2  inc     ebx
0x1800550c4  jmp     short loc_1800550B5
0x1800550c6  cmp     rax, 0Ah
0x1800550ca  jnb     loc_18005519B
0x1800550d0  mov     [rsp+rbx+130h+var_C8], dil
0x1800550d5  lea     ecx, [rbx+1]
0x1800550d8  lea     rdi, [rsp+130h+var_C8]
0x1800550dd  add     rdi, rcx
0x1800550e0  lea     rcx, [rsp+130h+var_C8]; String
0x1800550e5  call    cs:__imp_atoi
0x1800550ec  nop     dword ptr [rax+rax+00h]
0x1800550f1  mov     esi, eax
0x1800550f3  cmp     ebx, [rsp+130h+var_FC]
0x1800550f7  jnz     short loc_1800550FD
0x1800550f9  xor     edi, edi
0x1800550fb  jmp     short loc_18005510F
0x1800550fd  mov     rcx, rdi; String
0x180055100  call    cs:__imp_atoi
0x180055107  nop     dword ptr [rax+rax+00h]
0x18005510c  movzx   edi, ax
0x18005510f  lea     rax, [rbp+30h+WideCharStr]
0x180055113  mov     dword ptr [rsp+130h+lpcbData], 30h ; '0'; cchWideChar
0x18005511b  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18005511f  mov     [rsp+130h+phkResult], rax; lpWideCharStr
0x180055124  lea     r8, [rsp+130h+Data]; lpMultiByteStr
0x180055129  xor     edx, edx; dwFlags
0x18005512b  xor     ecx, ecx; CodePage
0x18005512d  call    cs:__imp_MultiByteToWideChar
0x180055134  nop     dword ptr [rax+rax+00h]
0x180055139  test    eax, eax
0x18005513b  jz      short loc_1800551A1
0x18005513d  lea     rdx, [rsp+130h+pclsid]; pclsid
0x180055142  lea     rcx, [rbp+30h+WideCharStr]; lpsz
0x180055146  call    cs:__imp_CLSIDFromString
0x18005514d  nop     dword ptr [rax+rax+00h]
0x180055152  mov     ebx, eax
0x180055154  test    eax, eax
0x180055156  js      short loc_1800551A6
0x180055158  lea     rax, [rsp+130h+pptlib]
0x18005515d  movzx   edx, si; wVerMajor
0x180055160  mov     r9d, 400h; lcid
0x180055166  mov     [rsp+130h+phkResult], rax; pptlib
0x18005516b  movzx   r8d, di; wVerMinor
0x18005516f  lea     rcx, [rsp+130h+pclsid]; rguid
0x180055174  call    cs:__imp_LoadRegTypeLib
0x18005517b  nop     dword ptr [rax+rax+00h]
0x180055180  mov     ebx, eax
0x180055182  test    eax, eax
0x180055184  js      short loc_1800551A6
0x180055186  mov     rax, [rsp+130h+pptlib]
0x18005518b  xor     ebx, ebx
0x18005518d  mov     [r14], rax
0x180055190  mov     [rsp+130h+pptlib], 0
0x180055199  jmp     short loc_1800551A6
0x18005519b  call    __report_rangecheckfailure
0x1800551a1  mov     ebx, 80004005h
0x1800551a6  mov     rcx, [rsp+130h+hKey]; hKey
0x1800551ab  test    rcx, rcx
0x1800551ae  jz      short loc_1800551C5
0x1800551b0  call    cs:__imp_RegCloseKey
0x1800551b7  nop     dword ptr [rax+rax+00h]
0x1800551bc  mov     [rsp+130h+hKey], 0
0x1800551c5  mov     rcx, [rsp+130h+var_E8]; hKey
0x1800551ca  test    rcx, rcx
0x1800551cd  jz      short loc_1800551E4
0x1800551cf  call    cs:__imp_RegCloseKey
0x1800551d6  nop     dword ptr [rax+rax+00h]
0x1800551db  mov     [rsp+130h+var_E8], 0
0x1800551e4  mov     rcx, [rsp+130h+pptlib]
0x1800551e9  test    rcx, rcx
0x1800551ec  jz      short loc_1800551FA
0x1800551ee  mov     rax, [rcx]
0x1800551f1  mov     rax, [rax+10h]
0x1800551f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551fa  mov     eax, ebx
0x1800551fc  mov     rcx, [rbp+30h+var_20]
0x180055200  xor     rcx, rsp; StackCookie
0x180055203  call    __security_check_cookie
0x180055208  lea     r11, [rsp+130h+var_10]
0x180055210  mov     rbx, [r11+30h]
0x180055214  mov     rsi, [r11+38h]
0x180055218  mov     rsp, r11
0x18005521b  pop     r14
0x18005521d  pop     rdi
0x18005521e  pop     rbp
0x18005521f  retn
```
