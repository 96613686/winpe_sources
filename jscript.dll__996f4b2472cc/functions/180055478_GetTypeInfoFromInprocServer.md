# GetTypeInfoFromInprocServer

- ea: `0x180055478`
- end: `0x1800556d2`
- name: `GetTypeInfoFromInprocServer`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18009150c`

## callees

- `0x180055478`
- `0x180058dc8`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `OLEAUT32!__imp_LoadTypeLibEx` at `0x18005560d`
- `OLEAUT32!__imp_LoadTypeLibEx` at `0x18005560d`
- `ADVAPI32!RegOpenKeyExA` at `0x1800554f4`
- `ADVAPI32!RegOpenKeyExA` at `0x1800554f4`
- `ADVAPI32!RegCloseKey` at `0x180055668`
- `ADVAPI32!RegCloseKey` at `0x180055668`
- `ADVAPI32!RegQueryValueExA` at `0x18005553a`
- `ADVAPI32!RegQueryValueExA` at `0x18005553a`
- `KERNEL32!MultiByteToWideChar` at `0x1800555af`
- `KERNEL32!MultiByteToWideChar` at `0x1800555af`

## pseudocode

```c
__int64 __fastcall GetTypeInfoFromInprocServer(HKEY a1, __int64 a2, __int16 a3, _QWORD *a4)
{
  LSTATUS v7; // eax
  int v8; // ebx
  LSTATUS v9; // eax
  __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  DWORD v13; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  ITypeLib *pptlib; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  CHAR Data[272]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+160h] [rbp+60h] BYREF

  *a4 = 0;
  hKey = 0;
  cbData = 260;
  pptlib = 0;
  v19 = 0;
  Type = 0;
  v7 = RegOpenKeyExA(a1, "InprocServer32", 0, 0x20019u, &hKey);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 >= 0 )
  {
    v9 = RegQueryValueExA(hKey, 0, 0, &Type, (LPBYTE)Data, &cbData);
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( v8 >= 0 )
    {
      if ( Type == 1 && cbData && cbData < 0x103 )
      {
        v12 = cbData - 1;
        if ( (unsigned int)v12 >= 0x104 )
          goto LABEL_17;
        Data[v12] = 0;
        v13 = MultiByteToWideChar(0, 0, Data, -1, WideCharStr, 260);
        v10 = v13;
        cbData = v13;
        if ( v13 && v13 < 0x105 )
        {
          WideCharStr[v13 - 1] = 92;
          v11 = 2LL * (v13 + 1);
          WideCharStr[v13] = a3 + 48;
          if ( v11 < 0x20C )
          {
            WideCharStr[v13 + 1] = 0;
            v8 = LoadTypeLibEx(WideCharStr, REGKIND_NONE, &pptlib);
            if ( v8 >= 0 )
            {
              v8 = ((__int64 (__fastcall *)(ITypeLib *, __int64, __int64 *))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                     pptlib,
                     a2,
                     &v19);
              if ( v8 >= 0 )
              {
                v8 = 0;
                *a4 = v19;
                v19 = 0;
              }
            }
            goto LABEL_19;
          }
LABEL_17:
          _report_rangecheckfailure(v11, v10);
        }
      }
      v8 = -2147467259;
    }
  }
LABEL_19:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( pptlib )
  {
    ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
    pptlib = 0;
  }
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180055478  push    rbp
0x18005547a  push    rbx
0x18005547b  push    rsi
0x18005547c  push    rdi
0x18005547d  push    r14
0x18005547f  lea     rbp, [rsp-280h]
0x180055487  sub     rsp, 380h
0x18005548e  mov     rax, cs:__security_cookie
0x180055495  xor     rax, rsp
0x180055498  mov     [rbp+2A0h+var_30], rax
0x18005549f  mov     rsi, r9
0x1800554a2  mov     qword ptr [r9], 0
0x1800554a9  mov     edi, r8d
0x1800554ac  mov     [rsp+3A0h+hKey], 0
0x1800554b5  mov     r14, rdx
0x1800554b8  mov     [rsp+3A0h+cbData], 104h
0x1800554c0  lea     rax, [rsp+3A0h+hKey]
0x1800554c5  mov     [rsp+3A0h+pptlib], 0
0x1800554ce  mov     r9d, 20019h; samDesired
0x1800554d4  mov     [rsp+3A0h+phkResult], rax; phkResult
0x1800554d9  xor     r8d, r8d; ulOptions
0x1800554dc  mov     [rsp+3A0h+var_358], 0
0x1800554e5  lea     rdx, aInprocserver32; "InprocServer32"
0x1800554ec  mov     [rsp+3A0h+Type], 0
0x1800554f4  call    cs:__imp_RegOpenKeyExA
0x1800554fb  nop     dword ptr [rax+rax+00h]
0x180055500  mov     ebx, eax
0x180055502  test    eax, eax
0x180055504  jle     short loc_18005550F
0x180055506  movzx   ebx, ax
0x180055509  or      ebx, 80070000h
0x18005550f  test    ebx, ebx
0x180055511  js      loc_18005565E
0x180055517  mov     rcx, [rsp+3A0h+hKey]; hKey
0x18005551c  lea     rax, [rsp+3A0h+cbData]
0x180055521  mov     [rsp+3A0h+lpcbData], rax; lpcbData
0x180055526  lea     r9, [rsp+3A0h+Type]; lpType
0x18005552b  lea     rax, [rsp+3A0h+Data]
0x180055530  xor     r8d, r8d; lpReserved
0x180055533  xor     edx, edx; lpValueName
0x180055535  mov     [rsp+3A0h+phkResult], rax; lpData
0x18005553a  call    cs:__imp_RegQueryValueExA
0x180055541  nop     dword ptr [rax+rax+00h]
0x180055546  mov     ebx, eax
0x180055548  test    eax, eax
0x18005554a  jle     short loc_180055555
0x18005554c  movzx   ebx, ax
0x18005554f  or      ebx, 80070000h
0x180055555  test    ebx, ebx
0x180055557  js      loc_18005565E
0x18005555d  cmp     [rsp+3A0h+Type], 1
0x180055562  jnz     loc_180055659
0x180055568  mov     eax, [rsp+3A0h+cbData]
0x18005556c  test    eax, eax
0x18005556e  jz      loc_180055659
0x180055574  cmp     eax, 103h
0x180055579  jnb     loc_180055659
0x18005557f  dec     eax
0x180055581  cmp     eax, 104h
0x180055586  jnb     loc_180055653
0x18005558c  mov     [rsp+rax+3A0h+Data], 0
0x180055591  lea     r8, [rsp+3A0h+Data]; lpMultiByteStr
0x180055596  lea     rax, [rbp+2A0h+WideCharStr]
0x18005559a  mov     dword ptr [rsp+3A0h+lpcbData], 104h; cchWideChar
0x1800555a2  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800555a6  mov     [rsp+3A0h+phkResult], rax; lpWideCharStr
0x1800555ab  xor     edx, edx; dwFlags
0x1800555ad  xor     ecx, ecx; CodePage
0x1800555af  call    cs:__imp_MultiByteToWideChar
0x1800555b6  nop     dword ptr [rax+rax+00h]
0x1800555bb  mov     edx, eax
0x1800555bd  mov     [rsp+3A0h+cbData], edx
0x1800555c1  test    eax, eax
0x1800555c3  jz      loc_180055659
0x1800555c9  cmp     edx, 105h
0x1800555cf  jnb     loc_180055659
0x1800555d5  lea     ecx, [rdx-1]
0x1800555d8  add     di, 30h ; '0'
0x1800555dc  mov     eax, 5Ch ; '\'
0x1800555e1  mov     [rbp+rcx*2+2A0h+WideCharStr], ax
0x1800555e6  lea     ecx, [rdx+1]
0x1800555e9  add     rcx, rcx
0x1800555ec  mov     [rbp+rdx*2+2A0h+WideCharStr], di
0x1800555f1  cmp     rcx, 20Ch
0x1800555f8  jnb     short loc_180055653
0x1800555fa  xor     eax, eax
0x1800555fc  lea     r8, [rsp+3A0h+pptlib]; pptlib
0x180055601  mov     [rbp+rcx+2A0h+WideCharStr], ax
0x180055606  lea     rcx, [rbp+2A0h+WideCharStr]; szFile
0x18005560a  lea     edx, [rax+2]; regkind
0x18005560d  call    cs:__imp_LoadTypeLibEx
0x180055614  nop     dword ptr [rax+rax+00h]
0x180055619  mov     ebx, eax
0x18005561b  test    eax, eax
0x18005561d  js      short loc_18005565E
0x18005561f  mov     rcx, [rsp+3A0h+pptlib]
0x180055624  lea     r8, [rsp+3A0h+var_358]
0x180055629  mov     rdx, r14
0x18005562c  mov     rax, [rcx]
0x18005562f  mov     rax, [rax+30h]
0x180055633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055638  mov     ebx, eax
0x18005563a  test    eax, eax
0x18005563c  js      short loc_18005565E
0x18005563e  mov     rax, [rsp+3A0h+var_358]
0x180055643  xor     ebx, ebx
0x180055645  mov     [rsi], rax
0x180055648  mov     [rsp+3A0h+var_358], 0
0x180055651  jmp     short loc_18005565E
0x180055653  call    __report_rangecheckfailure
0x180055659  mov     ebx, 80004005h
0x18005565e  mov     rcx, [rsp+3A0h+hKey]; hKey
0x180055663  test    rcx, rcx
0x180055666  jz      short loc_18005567D
0x180055668  call    cs:__imp_RegCloseKey
0x18005566f  nop     dword ptr [rax+rax+00h]
0x180055674  mov     [rsp+3A0h+hKey], 0
0x18005567d  mov     rcx, [rsp+3A0h+pptlib]
0x180055682  test    rcx, rcx
0x180055685  jz      short loc_18005569C
0x180055687  mov     rax, [rcx]
0x18005568a  mov     rax, [rax+10h]
0x18005568e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055693  mov     [rsp+3A0h+pptlib], 0
0x18005569c  mov     rcx, [rsp+3A0h+var_358]
0x1800556a1  test    rcx, rcx
0x1800556a4  jz      short loc_1800556B2
0x1800556a6  mov     rax, [rcx]
0x1800556a9  mov     rax, [rax+10h]
0x1800556ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556b2  mov     eax, ebx
0x1800556b4  mov     rcx, [rbp+2A0h+var_30]
0x1800556bb  xor     rcx, rsp; StackCookie
0x1800556be  call    __security_check_cookie
0x1800556c3  add     rsp, 380h
0x1800556ca  pop     r14
0x1800556cc  pop     rdi
0x1800556cd  pop     rsi
0x1800556ce  pop     rbx
0x1800556cf  pop     rbp
0x1800556d0  retn
```
