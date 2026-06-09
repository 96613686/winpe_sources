# GetTypeLibraryFromTypeLibKey

- ea: `0x1800540fc`
- end: `0x1800543de`
- name: `GetTypeLibraryFromTypeLibKey`
- size: `738`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008f46c`

## callees

- `0x1800540fc`
- `0x180057e98`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `msvcrt!atoi` at `0x1800542cd`
- `msvcrt!atoi` at `0x1800542e2`
- `msvcrt!atoi` at `0x1800542cd`
- `msvcrt!atoi` at `0x1800542e2`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180054344`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180054344`
- `ADVAPI32!RegOpenKeyExA` at `0x180054186`
- `ADVAPI32!RegOpenKeyExA` at `0x18005422d`
- `ADVAPI32!RegOpenKeyExA` at `0x180054186`
- `ADVAPI32!RegOpenKeyExA` at `0x18005422d`
- `ADVAPI32!RegCloseKey` at `0x18005437a`
- `ADVAPI32!RegCloseKey` at `0x180054393`
- `ADVAPI32!RegCloseKey` at `0x18005437a`
- `ADVAPI32!RegCloseKey` at `0x180054393`
- `ADVAPI32!RegQueryValueExA` at `0x1800541c7`
- `ADVAPI32!RegQueryValueExA` at `0x180054269`
- `ADVAPI32!RegQueryValueExA` at `0x1800541c7`
- `ADVAPI32!RegQueryValueExA` at `0x180054269`
- `KERNEL32!MultiByteToWideChar` at `0x180054309`
- `KERNEL32!MultiByteToWideChar` at `0x180054309`
- `ole32!CLSIDFromString` at `0x18005431c`
- `ole32!CLSIDFromString` at `0x18005431c`

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
  const char *v10; // rdi
  __int64 i; // rbx
  WORD v12; // si
  WORD v13; // di
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD lpcbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  ITypeLib *pptlib; // [rsp+50h] [rbp-B0h] BYREF
  CLSID pclsid; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v22[16]; // [rsp+68h] [rbp-98h] BYREF
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
        v9 = RegQueryValueExA(phkResult, 0, 0, &Type, v22, &lpcbData);
        v5 = v9;
        if ( v9 > 0 )
          v5 = (unsigned __int16)v9 | 0x80070000;
        if ( v5 >= 0 )
        {
          if ( Type == 1 && lpcbData )
          {
            v10 = 0;
            for ( i = 0; (unsigned int)i < lpcbData; i = (unsigned int)(i + 1) )
            {
              if ( v22[i] == 46 )
              {
                if ( (unsigned int)i >= 0xAuLL )
                  _report_rangecheckfailure();
                v22[i] = 0;
                v10 = (const char *)&v22[(unsigned int)(i + 1)];
                break;
              }
            }
            v12 = atoi((const char *)v22);
            v13 = (_DWORD)i == lpcbData ? 0 : atoi(v10);
            if ( MultiByteToWideChar(0, 0, Data, -1, WideCharStr, 48) )
            {
              v5 = CLSIDFromString(WideCharStr, &pclsid);
              if ( v5 >= 0 )
              {
                v5 = LoadRegTypeLib(&pclsid, v12, v13, 0x400u, &pptlib);
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
0x1800540fc  mov     [rsp-8+arg_10], rbx
0x180054101  mov     [rsp-8+arg_18], rsi
0x180054106  push    rbp
0x180054107  push    rdi
0x180054108  push    r14
0x18005410a  lea     rbp, [rsp-20h]
0x18005410f  sub     rsp, 120h
0x180054116  mov     rax, cs:__security_cookie
0x18005411d  xor     rax, rsp
0x180054120  mov     [rbp+30h+var_20], rax
0x180054124  mov     r14, rdx
0x180054127  mov     qword ptr [rdx], 0
0x18005412e  xorps   xmm0, xmm0
0x180054131  mov     [rsp+130h+hKey], 0
0x18005413a  lea     rax, [rsp+130h+hKey]
0x18005413f  mov     [rsp+130h+var_E8], 0
0x180054148  lea     rdx, aTypelib; "TypeLib"
0x18005414f  mov     [rsp+130h+phkResult], rax; phkResult
0x180054154  mov     r9d, 20019h; samDesired
0x18005415a  mov     [rsp+130h+cbData], 30h ; '0'
0x180054162  xor     r8d, r8d; ulOptions
0x180054165  mov     [rsp+130h+var_FC], 0Ah
0x18005416d  movups  xmmword ptr [rsp+130h+pclsid.Data1], xmm0
0x180054172  mov     rdi, rcx
0x180054175  mov     [rsp+130h+Type], 0
0x18005417d  mov     [rsp+130h+pptlib], 0
0x180054186  call    cs:__imp_RegOpenKeyExA
0x18005418c  mov     ebx, eax
0x18005418e  mov     esi, 80070000h
0x180054193  test    eax, eax
0x180054195  jle     short loc_18005419C
0x180054197  movzx   ebx, ax
0x18005419a  or      ebx, esi
0x18005419c  test    ebx, ebx
0x18005419e  js      loc_180054370
0x1800541a4  mov     rcx, [rsp+130h+hKey]; hKey
0x1800541a9  lea     rax, [rsp+130h+cbData]
0x1800541ae  mov     [rsp+130h+lpcbData], rax; lpcbData
0x1800541b3  lea     r9, [rsp+130h+Type]; lpType
0x1800541b8  lea     rax, [rsp+130h+Data]
0x1800541bd  xor     r8d, r8d; lpReserved
0x1800541c0  xor     edx, edx; lpValueName
0x1800541c2  mov     [rsp+130h+phkResult], rax; lpData
0x1800541c7  call    cs:__imp_RegQueryValueExA
0x1800541cd  mov     ebx, eax
0x1800541cf  test    eax, eax
0x1800541d1  jle     short loc_1800541D8
0x1800541d3  movzx   ebx, ax
0x1800541d6  or      ebx, esi
0x1800541d8  test    ebx, ebx
0x1800541da  js      loc_180054370
0x1800541e0  cmp     [rsp+130h+Type], 1
0x1800541e5  jnz     loc_18005436B
0x1800541eb  mov     eax, [rsp+130h+cbData]
0x1800541ef  test    eax, eax
0x1800541f1  jz      loc_18005436B
0x1800541f7  dec     eax
0x1800541f9  cmp     eax, 2Fh ; '/'
0x1800541fc  jnb     loc_18005436B
0x180054202  cmp     eax, 30h ; '0'
0x180054205  jnb     loc_180054365
0x18005420b  mov     [rsp+rax+130h+Data], 0
0x180054210  lea     rdx, aVersion; "Version"
0x180054217  lea     rax, [rsp+130h+var_E8]
0x18005421c  mov     r9d, 20019h; samDesired
0x180054222  xor     r8d, r8d; ulOptions
0x180054225  mov     [rsp+130h+phkResult], rax; phkResult
0x18005422a  mov     rcx, rdi; hKey
0x18005422d  call    cs:__imp_RegOpenKeyExA
0x180054233  mov     ebx, eax
0x180054235  test    eax, eax
0x180054237  jle     short loc_18005423E
0x180054239  movzx   ebx, ax
0x18005423c  or      ebx, esi
0x18005423e  test    ebx, ebx
0x180054240  js      loc_180054370
0x180054246  mov     rcx, [rsp+130h+var_E8]; hKey
0x18005424b  lea     rax, [rsp+130h+var_FC]
0x180054250  mov     [rsp+130h+lpcbData], rax; lpcbData
0x180054255  lea     r9, [rsp+130h+Type]; lpType
0x18005425a  lea     rax, [rsp+130h+var_C8]
0x18005425f  xor     r8d, r8d; lpReserved
0x180054262  xor     edx, edx; lpValueName
0x180054264  mov     [rsp+130h+phkResult], rax; lpData
0x180054269  call    cs:__imp_RegQueryValueExA
0x18005426f  mov     ebx, eax
0x180054271  test    eax, eax
0x180054273  jle     short loc_18005427A
0x180054275  movzx   ebx, ax
0x180054278  or      ebx, esi
0x18005427a  test    ebx, ebx
0x18005427c  js      loc_180054370
0x180054282  cmp     [rsp+130h+Type], 1
0x180054287  jnz     loc_18005436B
0x18005428d  mov     ecx, [rsp+130h+var_FC]
0x180054291  test    ecx, ecx
0x180054293  jz      loc_18005436B
0x180054299  xor     edi, edi
0x18005429b  xor     ebx, ebx
0x18005429d  cmp     ebx, ecx
0x18005429f  jnb     short loc_1800542C8
0x1800542a1  cmp     [rsp+rbx+130h+var_C8], 2Eh ; '.'
0x1800542a6  mov     eax, ebx
0x1800542a8  jz      short loc_1800542AE
0x1800542aa  inc     ebx
0x1800542ac  jmp     short loc_18005429D
0x1800542ae  cmp     rax, 0Ah
0x1800542b2  jnb     loc_180054365
0x1800542b8  mov     [rsp+rbx+130h+var_C8], dil
0x1800542bd  lea     ecx, [rbx+1]
0x1800542c0  lea     rdi, [rsp+130h+var_C8]
0x1800542c5  add     rdi, rcx
0x1800542c8  lea     rcx, [rsp+130h+var_C8]; String
0x1800542cd  call    cs:__imp_atoi
0x1800542d3  mov     esi, eax
0x1800542d5  cmp     ebx, [rsp+130h+var_FC]
0x1800542d9  jnz     short loc_1800542DF
0x1800542db  xor     edi, edi
0x1800542dd  jmp     short loc_1800542EB
0x1800542df  mov     rcx, rdi; String
0x1800542e2  call    cs:__imp_atoi
0x1800542e8  movzx   edi, ax
0x1800542eb  lea     rax, [rbp+30h+WideCharStr]
0x1800542ef  mov     dword ptr [rsp+130h+lpcbData], 30h ; '0'; cchWideChar
0x1800542f7  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800542fb  mov     [rsp+130h+phkResult], rax; lpWideCharStr
0x180054300  lea     r8, [rsp+130h+Data]; lpMultiByteStr
0x180054305  xor     edx, edx; dwFlags
0x180054307  xor     ecx, ecx; CodePage
0x180054309  call    cs:__imp_MultiByteToWideChar
0x18005430f  test    eax, eax
0x180054311  jz      short loc_18005436B
0x180054313  lea     rdx, [rsp+130h+pclsid]; pclsid
0x180054318  lea     rcx, [rbp+30h+WideCharStr]; lpsz
0x18005431c  call    cs:__imp_CLSIDFromString
0x180054322  mov     ebx, eax
0x180054324  test    eax, eax
0x180054326  js      short loc_180054370
0x180054328  lea     rax, [rsp+130h+pptlib]
0x18005432d  movzx   edx, si; wVerMajor
0x180054330  mov     r9d, 400h; lcid
0x180054336  mov     [rsp+130h+phkResult], rax; pptlib
0x18005433b  movzx   r8d, di; wVerMinor
0x18005433f  lea     rcx, [rsp+130h+pclsid]; rguid
0x180054344  call    cs:__imp_LoadRegTypeLib
0x18005434a  mov     ebx, eax
0x18005434c  test    eax, eax
0x18005434e  js      short loc_180054370
0x180054350  mov     rax, [rsp+130h+pptlib]
0x180054355  xor     ebx, ebx
0x180054357  mov     [r14], rax
0x18005435a  mov     [rsp+130h+pptlib], 0
0x180054363  jmp     short loc_180054370
0x180054365  call    __report_rangecheckfailure
0x18005436b  mov     ebx, 80004005h
0x180054370  mov     rcx, [rsp+130h+hKey]; hKey
0x180054375  test    rcx, rcx
0x180054378  jz      short loc_180054389
0x18005437a  call    cs:__imp_RegCloseKey
0x180054380  mov     [rsp+130h+hKey], 0
0x180054389  mov     rcx, [rsp+130h+var_E8]; hKey
0x18005438e  test    rcx, rcx
0x180054391  jz      short loc_1800543A2
0x180054393  call    cs:__imp_RegCloseKey
0x180054399  mov     [rsp+130h+var_E8], 0
0x1800543a2  mov     rcx, [rsp+130h+pptlib]
0x1800543a7  test    rcx, rcx
0x1800543aa  jz      short loc_1800543B8
0x1800543ac  mov     rax, [rcx]
0x1800543af  mov     rax, [rax+10h]
0x1800543b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800543b8  mov     eax, ebx
0x1800543ba  mov     rcx, [rbp+30h+var_20]
0x1800543be  xor     rcx, rsp; StackCookie
0x1800543c1  call    __security_check_cookie
0x1800543c6  lea     r11, [rsp+130h+var_10]
0x1800543ce  mov     rbx, [r11+30h]
0x1800543d2  mov     rsi, [r11+38h]
0x1800543d6  mov     rsp, r11
0x1800543d9  pop     r14
0x1800543db  pop     rdi
0x1800543dc  pop     rbp
0x1800543dd  retn
```
