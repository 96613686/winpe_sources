# CSplashHash::Read(HKEY__ *,ushort const *)

- ea: `0x140044948`
- end: `0x140044ba3`
- name: `?Read@CSplashHash@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `603`
- prototype: `__int64 __fastcall(CSplashHash *__hidden this, HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x14003f244`

## callees

- `0x140001020`
- `0x140002190`
- `0x14000fea0`
- `0x1400448cc`
- `0x140044914`
- `0x140044948`
- `0x140063d50`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400449ec`
- `ADVAPI32!RegCloseKey` at `0x140044a4c`
- `ADVAPI32!RegCloseKey` at `0x140044ae3`
- `ADVAPI32!RegCloseKey` at `0x140044b45`
- `ADVAPI32!RegCloseKey` at `0x140044b59`
- `ADVAPI32!RegCloseKey` at `0x1400449ec`
- `ADVAPI32!RegCloseKey` at `0x140044a4c`
- `ADVAPI32!RegCloseKey` at `0x140044ae3`
- `ADVAPI32!RegCloseKey` at `0x140044b45`
- `ADVAPI32!RegCloseKey` at `0x140044b59`
- `ADVAPI32!RegOpenKeyExW` at `0x1400449b4`
- `ADVAPI32!RegOpenKeyExW` at `0x1400449b4`
- `ADVAPI32!RegQueryValueExW` at `0x140044a20`
- `ADVAPI32!RegQueryValueExW` at `0x140044aaf`
- `ADVAPI32!RegQueryValueExW` at `0x140044a20`
- `ADVAPI32!RegQueryValueExW` at `0x140044aaf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSplashHash::Read(void **this, HKEY hKey, LPCWSTR lpSubKey)
{
  HKEY v6; // r15
  LSTATUS v7; // eax
  int v8; // edx
  unsigned int v9; // ebx
  const struct std::nothrow_t *v11; // rdx
  LSTATUS v12; // ebx
  unsigned int v13; // edi
  DWORD v14; // ebx
  BYTE *v15; // rax
  LSTATUS v16; // ebx
  unsigned int v17; // edi
  __int64 v18; // r8
  char *v19; // rcx
  __int64 v20; // r8
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-50h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-38h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-30h] BYREF

  CSplashHash::Free((CSplashHash *)this);
  v6 = 0;
  phkResult = 0;
  v7 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult);
  if ( !v7 )
    v6 = phkResult;
  v8 = v7 != 0 ? v7 : 0;
  if ( v8 )
  {
    v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      v9 = v7 != 0 ? v7 : 0;
    if ( v6 )
      RegCloseKey(v6);
    return v9;
  }
  cbData = 0;
  v12 = RegQueryValueExW(v6, L"SplashHash", 0, (LPDWORD)&phkResult, 0, &cbData);
  if ( v12 )
    goto LABEL_12;
  if ( (_DWORD)phkResult != 3 )
  {
    v12 = 13;
LABEL_12:
    v13 = (unsigned __int16)v12 | 0x80070000;
    if ( v12 <= 0 )
      v13 = v12;
    if ( v6 )
      RegCloseKey(v6);
    return v13;
  }
  v14 = cbData;
  operator delete(this[1], v11);
  *(_DWORD *)this = 0;
  this[1] = 0;
  if ( v14 )
  {
    v15 = (BYTE *)operator new[](v14);
    this[1] = v15;
    if ( !v15 )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    }
  }
  else
  {
    v15 = 0;
  }
  *(_DWORD *)this = v14;
  v16 = RegQueryValueExW(v6, L"SplashHash", 0, (LPDWORD)&phkResult, v15, &cbData);
  if ( v16 )
    goto LABEL_24;
  if ( (_DWORD)phkResult != 3 )
  {
    v16 = 13;
LABEL_24:
    CSplashHash::Free((CSplashHash *)this);
    v17 = (unsigned __int16)v16 | 0x80070000;
    if ( v16 <= 0 )
      v17 = v16;
    if ( v6 )
      RegCloseKey(v6);
    return v17;
  }
  LODWORD(v18) = cbData;
  if ( cbData >= 8 )
  {
    v18 = cbData - 8;
    v19 = (char *)this[1];
    *((_DWORD *)this + 7) = *(_DWORD *)&v19[v18];
    *((_DWORD *)this + 8) = *(_DWORD *)&v19[v18 + 4];
    if ( (unsigned int)v18 <= *(_DWORD *)this )
      *(_DWORD *)this = v18;
  }
  if ( (unsigned int)v18 >= 4 )
  {
    v20 = (unsigned int)(v18 - 4);
    *((_DWORD *)this + 6) = *(_DWORD *)((char *)this[1] + v20);
    if ( (unsigned int)v20 <= *(_DWORD *)this )
      *(_DWORD *)this = v20;
  }
  if ( v6 )
    RegCloseKey(v6);
  return 0;
}

```

## disassembly

```asm
0x140044948  mov     [rsp+arg_18], rbx
0x14004494d  push    rdi
0x14004494e  push    r14
0x140044950  push    r15
0x140044952  sub     rsp, 80h
0x140044959  mov     rax, cs:__security_cookie
0x140044960  xor     rax, rsp
0x140044963  mov     [rsp+98h+var_28], rax
0x140044968  mov     rdi, r8
0x14004496b  mov     rbx, rdx
0x14004496e  mov     r14, rcx
0x140044971  call    ?Free@CSplashHash@@QEAAXXZ; CSplashHash::Free(void)
0x140044976  xorps   xmm0, xmm0
0x140044979  xor     eax, eax
0x14004497b  movups  xmmword ptr [rsp+98h+hKey], xmm0
0x140044980  mov     [rsp+98h+var_58], rax
0x140044985  xor     r15d, r15d
0x140044988  mov     [rsp+98h+hKey], r15
0x14004498d  and     dword ptr [rsp+98h+hKey+8], eax
0x140044991  and     [rsp+98h+var_58], rax
0x140044996  and     [rsp+98h+var_30], r15
0x14004499b  lea     rax, [rsp+98h+var_30]
0x1400449a0  mov     [rsp+98h+phkResult], rax; lpData
0x1400449a5  mov     r9d, 20019h; samDesired
0x1400449ab  xor     r8d, r8d; ulOptions
0x1400449ae  mov     rdx, rdi; lpSubKey
0x1400449b1  mov     rcx, rbx; hKey
0x1400449b4  call    cs:__imp_RegOpenKeyExW
0x1400449ba  test    eax, eax
0x1400449bc  jnz     short loc_1400449CC
0x1400449be  mov     r15, [rsp+98h+var_30]
0x1400449c3  mov     [rsp+98h+hKey], r15
0x1400449c8  and     dword ptr [rsp+98h+hKey+8], eax
0x1400449cc  mov     ecx, eax
0x1400449ce  neg     ecx
0x1400449d0  sbb     edx, edx
0x1400449d2  and     edx, eax
0x1400449d4  jz      short loc_1400449F9
0x1400449d6  movzx   ebx, dx
0x1400449d9  or      ebx, 80070000h
0x1400449df  test    edx, edx
0x1400449e1  cmovle  ebx, edx
0x1400449e4  test    r15, r15
0x1400449e7  jz      short loc_1400449F2
0x1400449e9  mov     rcx, r15; hKey
0x1400449ec  call    cs:__imp_RegCloseKey
0x1400449f2  mov     eax, ebx
0x1400449f4  jmp     loc_140044B64
0x1400449f9  and     [rsp+98h+cbData], 0
0x1400449fe  lea     rax, [rsp+98h+cbData]
0x140044a03  mov     [rsp+98h+lpcbData], rax; lpcbData
0x140044a08  and     [rsp+98h+phkResult], 0
0x140044a0e  lea     r9, [rsp+98h+var_30]; lpType
0x140044a13  xor     r8d, r8d; lpReserved
0x140044a16  lea     rdx, aSplashhash; "SplashHash"
0x140044a1d  mov     rcx, r15; hKey
0x140044a20  call    cs:__imp_RegQueryValueExW
0x140044a26  mov     ebx, eax
0x140044a28  test    eax, eax
0x140044a2a  jnz     short loc_140044A36
0x140044a2c  cmp     dword ptr [rsp+98h+var_30], 3
0x140044a31  jz      short loc_140044A59
0x140044a33  lea     ebx, [rax+0Dh]
0x140044a36  movzx   edi, bx
0x140044a39  or      edi, 80070000h
0x140044a3f  test    ebx, ebx
0x140044a41  cmovle  edi, ebx
0x140044a44  test    r15, r15
0x140044a47  jz      short loc_140044A52
0x140044a49  mov     rcx, r15; hKey
0x140044a4c  call    cs:__imp_RegCloseKey
0x140044a52  mov     eax, edi
0x140044a54  jmp     loc_140044B64
0x140044a59  mov     ebx, [rsp+98h+cbData]
0x140044a5d  mov     rcx, [r14+8]; void *
0x140044a61  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140044a66  and     dword ptr [r14], 0
0x140044a6a  and     qword ptr [r14+8], 0
0x140044a6f  test    ebx, ebx
0x140044a71  jz      short loc_140044A89
0x140044a73  mov     ecx, ebx; unsigned __int64
0x140044a75  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140044a7a  mov     [r14+8], rax
0x140044a7e  test    rax, rax
0x140044a81  jz      loc_140044B86
0x140044a87  jmp     short loc_140044A8B
0x140044a89  xor     eax, eax
0x140044a8b  mov     [r14], ebx
0x140044a8e  lea     rcx, [rsp+98h+cbData]
0x140044a93  mov     [rsp+98h+lpcbData], rcx; lpcbData
0x140044a98  mov     [rsp+98h+phkResult], rax; lpData
0x140044a9d  lea     r9, [rsp+98h+var_30]; lpType
0x140044aa2  xor     r8d, r8d; lpReserved
0x140044aa5  lea     rdx, aSplashhash; "SplashHash"
0x140044aac  mov     rcx, r15; hKey
0x140044aaf  call    cs:__imp_RegQueryValueExW
0x140044ab5  mov     ebx, eax
0x140044ab7  test    eax, eax
0x140044ab9  jnz     short loc_140044AC5
0x140044abb  cmp     dword ptr [rsp+98h+var_30], 3
0x140044ac0  jz      short loc_140044AF3
0x140044ac2  lea     ebx, [rax+0Dh]
0x140044ac5  mov     rcx, r14; this
0x140044ac8  call    ?Free@CSplashHash@@QEAAXXZ; CSplashHash::Free(void)
0x140044acd  movzx   edi, bx
0x140044ad0  or      edi, 80070000h
0x140044ad6  test    ebx, ebx
0x140044ad8  cmovle  edi, ebx
0x140044adb  test    r15, r15
0x140044ade  jz      short loc_140044AEF
0x140044ae0  mov     rcx, r15; hKey
0x140044ae3  call    cs:__imp_RegCloseKey
0x140044ae9  and     [rsp+98h+hKey], 0
0x140044aef  mov     eax, edi
0x140044af1  jmp     short loc_140044B64
0x140044af3  mov     r8d, [rsp+98h+cbData]
0x140044af8  cmp     r8d, 8
0x140044afc  jb      short loc_140044B1F
0x140044afe  add     r8d, 0FFFFFFF8h
0x140044b02  mov     rcx, [r14+8]
0x140044b06  mov     eax, [r8+rcx]
0x140044b0a  mov     [r14+1Ch], eax
0x140044b0e  mov     eax, [r8+rcx+4]
0x140044b13  mov     [r14+20h], eax
0x140044b17  cmp     r8d, [r14]
0x140044b1a  ja      short loc_140044B1F
0x140044b1c  mov     [r14], r8d
0x140044b1f  cmp     r8d, 4
0x140044b23  jb      short loc_140044B3D
0x140044b25  add     r8d, 0FFFFFFFCh
0x140044b29  mov     rax, [r14+8]
0x140044b2d  mov     ecx, [r8+rax]
0x140044b31  mov     [r14+18h], ecx
0x140044b35  cmp     r8d, [r14]
0x140044b38  ja      short loc_140044B3D
0x140044b3a  mov     [r14], r8d
0x140044b3d  test    r15, r15
0x140044b40  jz      short loc_140044B4B
0x140044b42  mov     rcx, r15; hKey
0x140044b45  call    cs:__imp_RegCloseKey
0x140044b4b  xor     eax, eax
0x140044b4d  jmp     short loc_140044B64
0x140044b4f  mov     rcx, [rsp+98h+hKey]; hKey
0x140044b54  test    rcx, rcx
0x140044b57  jz      short loc_140044B5F
0x140044b59  call    cs:__imp_RegCloseKey
0x140044b5f  mov     eax, 8007000Eh
0x140044b64  mov     rcx, [rsp+98h+var_28]
0x140044b69  xor     rcx, rsp; StackCookie
0x140044b6c  call    __security_check_cookie
0x140044b71  mov     rbx, [rsp+98h+arg_18]
0x140044b79  add     rsp, 80h
0x140044b80  pop     r15
0x140044b82  pop     r14
0x140044b84  pop     rdi
0x140044b85  retn
0x140044b86  lea     rcx, [rsp+98h+pExceptionObject]; this
0x140044b8b  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x140044b90  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x140044b97  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x140044b9c  call    _CxxThrowException_0
```
