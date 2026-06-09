# GetTypeInfoFromInprocServer

- ea: `0x180054638`
- end: `0x18005486f`
- name: `GetTypeInfoFromInprocServer`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18008f30c`

## callees

- `0x180054638`
- `0x180057e98`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `OLEAUT32!__imp_LoadTypeLibEx` at `0x1800547b7`
- `OLEAUT32!__imp_LoadTypeLibEx` at `0x1800547b7`
- `ADVAPI32!RegOpenKeyExA` at `0x1800546b4`
- `ADVAPI32!RegOpenKeyExA` at `0x1800546b4`
- `ADVAPI32!RegCloseKey` at `0x18005480c`
- `ADVAPI32!RegCloseKey` at `0x18005480c`
- `ADVAPI32!RegQueryValueExA` at `0x1800546f4`
- `ADVAPI32!RegQueryValueExA` at `0x1800546f4`
- `KERNEL32!MultiByteToWideChar` at `0x180054763`
- `KERNEL32!MultiByteToWideChar` at `0x180054763`

## pseudocode

```c
__int64 __fastcall GetTypeInfoFromInprocServer(HKEY a1, __int64 a2, __int16 a3, _QWORD *a4)
{
  LSTATUS v7; // eax
  int v8; // ebx
  LSTATUS v9; // eax
  __int64 v10; // rax
  DWORD v11; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  ITypeLib *pptlib; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  CHAR Data[272]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+160h] [rbp+60h] BYREF

  *a4 = 0;
  hKey = 0;
  cbData = 260;
  pptlib = 0;
  v17 = 0;
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
        v10 = cbData - 1;
        if ( (unsigned int)v10 >= 0x104 )
          goto LABEL_17;
        Data[v10] = 0;
        v11 = MultiByteToWideChar(0, 0, Data, -1, WideCharStr, 260);
        cbData = v11;
        if ( v11 && v11 < 0x105 )
        {
          WideCharStr[v11 - 1] = 92;
          WideCharStr[v11] = a3 + 48;
          if ( 2 * (unsigned __int64)(v11 + 1) < 0x20C )
          {
            WideCharStr[v11 + 1] = 0;
            v8 = LoadTypeLibEx(WideCharStr, REGKIND_NONE, &pptlib);
            if ( v8 >= 0 )
            {
              v8 = ((__int64 (__fastcall *)(ITypeLib *, __int64, __int64 *))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                     pptlib,
                     a2,
                     &v17);
              if ( v8 >= 0 )
              {
                v8 = 0;
                *a4 = v17;
                v17 = 0;
              }
            }
            goto LABEL_19;
          }
LABEL_17:
          _report_rangecheckfailure();
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
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180054638  push    rbp
0x18005463a  push    rbx
0x18005463b  push    rsi
0x18005463c  push    rdi
0x18005463d  push    r14
0x18005463f  lea     rbp, [rsp-280h]
0x180054647  sub     rsp, 380h
0x18005464e  mov     rax, cs:__security_cookie
0x180054655  xor     rax, rsp
0x180054658  mov     [rbp+2A0h+var_30], rax
0x18005465f  mov     rsi, r9
0x180054662  mov     qword ptr [r9], 0
0x180054669  mov     edi, r8d
0x18005466c  mov     [rsp+3A0h+hKey], 0
0x180054675  mov     r14, rdx
0x180054678  mov     [rsp+3A0h+cbData], 104h
0x180054680  lea     rax, [rsp+3A0h+hKey]
0x180054685  mov     [rsp+3A0h+pptlib], 0
0x18005468e  mov     r9d, 20019h; samDesired
0x180054694  mov     [rsp+3A0h+phkResult], rax; phkResult
0x180054699  xor     r8d, r8d; ulOptions
0x18005469c  mov     [rsp+3A0h+var_358], 0
0x1800546a5  lea     rdx, aInprocserver32; "InprocServer32"
0x1800546ac  mov     [rsp+3A0h+Type], 0
0x1800546b4  call    cs:__imp_RegOpenKeyExA
0x1800546ba  mov     ebx, eax
0x1800546bc  test    eax, eax
0x1800546be  jle     short loc_1800546C9
0x1800546c0  movzx   ebx, ax
0x1800546c3  or      ebx, 80070000h
0x1800546c9  test    ebx, ebx
0x1800546cb  js      loc_180054802
0x1800546d1  mov     rcx, [rsp+3A0h+hKey]; hKey
0x1800546d6  lea     rax, [rsp+3A0h+cbData]
0x1800546db  mov     [rsp+3A0h+lpcbData], rax; lpcbData
0x1800546e0  lea     r9, [rsp+3A0h+Type]; lpType
0x1800546e5  lea     rax, [rsp+3A0h+Data]
0x1800546ea  xor     r8d, r8d; lpReserved
0x1800546ed  xor     edx, edx; lpValueName
0x1800546ef  mov     [rsp+3A0h+phkResult], rax; lpData
0x1800546f4  call    cs:__imp_RegQueryValueExA
0x1800546fa  mov     ebx, eax
0x1800546fc  test    eax, eax
0x1800546fe  jle     short loc_180054709
0x180054700  movzx   ebx, ax
0x180054703  or      ebx, 80070000h
0x180054709  test    ebx, ebx
0x18005470b  js      loc_180054802
0x180054711  cmp     [rsp+3A0h+Type], 1
0x180054716  jnz     loc_1800547FD
0x18005471c  mov     eax, [rsp+3A0h+cbData]
0x180054720  test    eax, eax
0x180054722  jz      loc_1800547FD
0x180054728  cmp     eax, 103h
0x18005472d  jnb     loc_1800547FD
0x180054733  dec     eax
0x180054735  cmp     eax, 104h
0x18005473a  jnb     loc_1800547F7
0x180054740  mov     [rsp+rax+3A0h+Data], 0
0x180054745  lea     r8, [rsp+3A0h+Data]; lpMultiByteStr
0x18005474a  lea     rax, [rbp+2A0h+WideCharStr]
0x18005474e  mov     dword ptr [rsp+3A0h+lpcbData], 104h; cchWideChar
0x180054756  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18005475a  mov     [rsp+3A0h+phkResult], rax; lpWideCharStr
0x18005475f  xor     edx, edx; dwFlags
0x180054761  xor     ecx, ecx; CodePage
0x180054763  call    cs:__imp_MultiByteToWideChar
0x180054769  mov     edx, eax
0x18005476b  mov     [rsp+3A0h+cbData], edx
0x18005476f  test    eax, eax
0x180054771  jz      loc_1800547FD
0x180054777  cmp     edx, 105h
0x18005477d  jnb     short loc_1800547FD
0x18005477f  lea     ecx, [rdx-1]
0x180054782  add     di, 30h ; '0'
0x180054786  mov     eax, 5Ch ; '\'
0x18005478b  mov     [rbp+rcx*2+2A0h+WideCharStr], ax
0x180054790  lea     ecx, [rdx+1]
0x180054793  add     rcx, rcx
0x180054796  mov     [rbp+rdx*2+2A0h+WideCharStr], di
0x18005479b  cmp     rcx, 20Ch
0x1800547a2  jnb     short loc_1800547F7
0x1800547a4  xor     eax, eax
0x1800547a6  lea     r8, [rsp+3A0h+pptlib]; pptlib
0x1800547ab  mov     [rbp+rcx+2A0h+WideCharStr], ax
0x1800547b0  lea     rcx, [rbp+2A0h+WideCharStr]; szFile
0x1800547b4  lea     edx, [rax+2]; regkind
0x1800547b7  call    cs:__imp_LoadTypeLibEx
0x1800547bd  mov     ebx, eax
0x1800547bf  test    eax, eax
0x1800547c1  js      short loc_180054802
0x1800547c3  mov     rcx, [rsp+3A0h+pptlib]
0x1800547c8  lea     r8, [rsp+3A0h+var_358]
0x1800547cd  mov     rdx, r14
0x1800547d0  mov     rax, [rcx]
0x1800547d3  mov     rax, [rax+30h]
0x1800547d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800547dc  mov     ebx, eax
0x1800547de  test    eax, eax
0x1800547e0  js      short loc_180054802
0x1800547e2  mov     rax, [rsp+3A0h+var_358]
0x1800547e7  xor     ebx, ebx
0x1800547e9  mov     [rsi], rax
0x1800547ec  mov     [rsp+3A0h+var_358], 0
0x1800547f5  jmp     short loc_180054802
0x1800547f7  call    __report_rangecheckfailure
0x1800547fd  mov     ebx, 80004005h
0x180054802  mov     rcx, [rsp+3A0h+hKey]; hKey
0x180054807  test    rcx, rcx
0x18005480a  jz      short loc_18005481B
0x18005480c  call    cs:__imp_RegCloseKey
0x180054812  mov     [rsp+3A0h+hKey], 0
0x18005481b  mov     rcx, [rsp+3A0h+pptlib]
0x180054820  test    rcx, rcx
0x180054823  jz      short loc_18005483A
0x180054825  mov     rax, [rcx]
0x180054828  mov     rax, [rax+10h]
0x18005482c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054831  mov     [rsp+3A0h+pptlib], 0
0x18005483a  mov     rcx, [rsp+3A0h+var_358]
0x18005483f  test    rcx, rcx
0x180054842  jz      short loc_180054850
0x180054844  mov     rax, [rcx]
0x180054847  mov     rax, [rax+10h]
0x18005484b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054850  mov     eax, ebx
0x180054852  mov     rcx, [rbp+2A0h+var_30]
0x180054859  xor     rcx, rsp; StackCookie
0x18005485c  call    __security_check_cookie
0x180054861  add     rsp, 380h
0x180054868  pop     r14
0x18005486a  pop     rdi
0x18005486b  pop     rsi
0x18005486c  pop     rbx
0x18005486d  pop     rbp
0x18005486e  retn
```
