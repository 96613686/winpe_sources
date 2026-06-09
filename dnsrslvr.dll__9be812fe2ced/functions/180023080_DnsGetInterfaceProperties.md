# DnsGetInterfaceProperties

- ea: `0x180023080`
- end: `0x180023376`
- name: `DnsGetInterfaceProperties`
- size: `758`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180023080`
- `0x180023380`
- `0x180046ec0`
- `0x180085fb8`
- `0x18008694c`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002320b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002321e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023358`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023367`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002320b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002321e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023358`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023367`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023131`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023153`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800231a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800231c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023131`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023153`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800231a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800231c6`

## pseudocode

```c
__int64 __fastcall DnsGetInterfaceProperties(
        HKEY hKey,
        int a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        _QWORD *a6,
        _DWORD *a7,
        _QWORD *a8)
{
  unsigned int InterfacePropertiesImpl; // eax
  unsigned int v12; // ebx
  unsigned int v14; // eax
  HKEY hKeya; // [rsp+68h] [rbp-29h] BYREF
  HKEY v16; // [rsp+70h] [rbp-21h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-19h] BYREF
  HKEY v18; // [rsp+80h] [rbp-11h] BYREF

  hKeya = 0;
  v16 = 0;
  phkResult = 0;
  v18 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qlSSqqqq(0, a2, a3, (_DWORD)hKey, a2, a3, a4, (__int64)a5, (__int64)a6, (__int64)a7, (__int64)a8);
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( !a3 )
    goto LABEL_38;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_S(1035, 315, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, a3);
  if ( (RegOpenKeyExW(hKey, L"DohInterfaceSettings", 0, 0x20019u, &hKeya),
        RegOpenKeyExW(hKey, L"DotInterfaceSettings", 0, 0x20019u, &phkResult),
        !hKeya)
    && !phkResult
    || (v14 = DnsGetInterfacePropertiesImpl(hKeya, phkResult, (__int64)a5, (__int64)a6), (v12 = v14) == 0)
    || v14 == 1168 )
  {
LABEL_38:
    if ( !a4 )
      goto LABEL_21;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_S(1035, 316, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, a4);
    if ( (RegOpenKeyExW(hKey, L"DohProfileSettings", 0, 0x20019u, &v16),
          RegOpenKeyExW(hKey, L"DotProfileSettings", 0, 0x20019u, &v18),
          !v16)
      && !v18
      || (InterfacePropertiesImpl = DnsGetInterfacePropertiesImpl(v16, v18, (__int64)a7, (__int64)a8),
          (v12 = InterfacePropertiesImpl) == 0)
      || InterfacePropertiesImpl == 1168 )
    {
LABEL_21:
      v12 = 0;
    }
  }
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  if ( v16 )
  {
    RegCloseKey(v16);
    v16 = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( v18 )
  {
    RegCloseKey(v18);
    v18 = 0;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 317, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x180023080  push    rbp
0x180023082  push    rbx
0x180023083  push    rsi
0x180023084  push    rdi
0x180023085  push    r12
0x180023087  push    r13
0x180023089  push    r14
0x18002308b  push    r15
0x18002308d  lea     rbp, [rsp-7]
0x180023092  sub     rsp, 98h
0x180023099  mov     rax, cs:__security_cookie
0x1800230a0  xor     rax, rsp
0x1800230a3  mov     [rbp+3Fh+var_48], rax
0x1800230a7  mov     rbx, [rbp+3Fh+arg_20]
0x1800230ab  mov     r13, rcx
0x1800230ae  mov     rdi, [rbp+3Fh+arg_28]
0x1800230b2  xor     ecx, ecx
0x1800230b4  mov     rsi, [rbp+3Fh+arg_30]
0x1800230b8  mov     r15, r9
0x1800230bb  mov     r14, [rbp+3Fh+arg_38]
0x1800230c2  mov     r12, r8
0x1800230c5  mov     [rbp+3Fh+hKey], rcx
0x1800230c9  mov     [rbp+3Fh+var_60], rcx
0x1800230cd  mov     [rbp+3Fh+var_58], rcx
0x1800230d1  mov     [rbp+3Fh+var_50], rcx
0x1800230d5  mov     [rbp+3Fh+var_70], edx
0x1800230d8  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800230df  jnz     loc_1800232AD
0x1800230e5  test    rbx, rbx
0x1800230e8  jz      short loc_1800230EC
0x1800230ea  mov     [rbx], ecx
0x1800230ec  test    rdi, rdi
0x1800230ef  jz      short loc_1800230F4
0x1800230f1  mov     [rdi], rcx
0x1800230f4  test    rsi, rsi
0x1800230f7  jz      short loc_1800230FB
0x1800230f9  mov     [rsi], ecx
0x1800230fb  test    r14, r14
0x1800230fe  jz      short loc_180023103
0x180023100  mov     [r14], rcx
0x180023103  test    r12, r12
0x180023106  jz      short loc_18002316F
0x180023108  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002310f  jnz     loc_1800232FC
0x180023115  lea     rax, [rbp+3Fh+hKey]
0x180023119  mov     r9d, 20019h; samDesired
0x18002311f  xor     r8d, r8d; ulOptions
0x180023122  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180023127  lea     rdx, SubKey; "DohInterfaceSettings"
0x18002312e  mov     rcx, r13; hKey
0x180023131  call    cs:__imp_RegOpenKeyExW
0x180023137  lea     rax, [rbp+3Fh+var_58]
0x18002313b  mov     r9d, 20019h; samDesired
0x180023141  xor     r8d, r8d; ulOptions
0x180023144  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180023149  lea     rdx, aDotinterfacese; "DotInterfaceSettings"
0x180023150  mov     rcx, r13; hKey
0x180023153  call    cs:__imp_RegOpenKeyExW
0x180023159  cmp     [rbp+3Fh+hKey], 0
0x18002315e  jnz     loc_180023271
0x180023164  cmp     [rbp+3Fh+var_58], 0
0x180023169  jnz     loc_180023271
0x18002316f  mov     edi, [rbp+3Fh+var_70]
0x180023172  test    r15, r15
0x180023175  jz      loc_1800231FE
0x18002317b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180023182  jnz     loc_18002331A
0x180023188  lea     rax, [rbp+3Fh+var_60]
0x18002318c  mov     r9d, 20019h; samDesired
0x180023192  xor     r8d, r8d; ulOptions
0x180023195  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18002319a  lea     rdx, aDohprofilesett; "DohProfileSettings"
0x1800231a1  mov     rcx, r13; hKey
0x1800231a4  call    cs:__imp_RegOpenKeyExW
0x1800231aa  lea     rax, [rbp+3Fh+var_50]
0x1800231ae  mov     r9d, 20019h; samDesired
0x1800231b4  xor     r8d, r8d; ulOptions
0x1800231b7  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800231bc  lea     rdx, aDotprofilesett; "DotProfileSettings"
0x1800231c3  mov     rcx, r13; hKey
0x1800231c6  call    cs:__imp_RegOpenKeyExW
0x1800231cc  cmp     [rbp+3Fh+var_60], 0
0x1800231d1  jz      loc_180023338
0x1800231d7  mov     rdx, [rbp+3Fh+var_50]; HKEY
0x1800231db  mov     r9, r15
0x1800231de  mov     rcx, [rbp+3Fh+var_60]; hKey
0x1800231e2  mov     r8d, edi
0x1800231e5  mov     [rsp+0D0h+var_A8], r14; __int64
0x1800231ea  mov     [rsp+0D0h+phkResult], rsi; __int64
0x1800231ef  call    DnsGetInterfacePropertiesImpl
0x1800231f4  mov     ebx, eax
0x1800231f6  test    eax, eax
0x1800231f8  jnz     loc_180023348
0x1800231fe  xor     edi, edi
0x180023200  mov     ebx, edi
0x180023202  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180023206  test    rcx, rcx
0x180023209  jz      short loc_180023215
0x18002320b  call    cs:__imp_RegCloseKey
0x180023211  mov     [rbp+3Fh+hKey], rdi
0x180023215  mov     rcx, [rbp+3Fh+var_60]; hKey
0x180023219  test    rcx, rcx
0x18002321c  jz      short loc_180023228
0x18002321e  call    cs:__imp_RegCloseKey
0x180023224  mov     [rbp+3Fh+var_60], rdi
0x180023228  mov     rcx, [rbp+3Fh+var_58]; hKey
0x18002322c  test    rcx, rcx
0x18002322f  jnz     loc_180023358
0x180023235  mov     rcx, [rbp+3Fh+var_50]; hKey
0x180023239  test    rcx, rcx
0x18002323c  jnz     loc_180023367
0x180023242  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180023249  jnz     loc_1800232DE
0x18002324f  mov     eax, ebx
0x180023251  mov     rcx, [rbp+3Fh+var_48]
0x180023255  xor     rcx, rsp; StackCookie
0x180023258  call    __security_check_cookie
0x18002325d  add     rsp, 98h
0x180023264  pop     r15
0x180023266  pop     r14
0x180023268  pop     r13
0x18002326a  pop     r12
0x18002326c  pop     rdi
0x18002326d  pop     rsi
0x18002326e  pop     rbx
0x18002326f  pop     rbp
0x180023270  retn
0x180023271  mov     rdx, [rbp+3Fh+var_58]; HKEY
0x180023275  mov     r9, r12
0x180023278  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18002327c  mov     [rsp+0D0h+var_A8], rdi; __int64
0x180023281  mov     edi, [rbp+3Fh+var_70]
0x180023284  mov     r8d, edi
0x180023287  mov     [rsp+0D0h+phkResult], rbx; __int64
0x18002328c  call    DnsGetInterfacePropertiesImpl
0x180023291  mov     ebx, eax
0x180023293  test    eax, eax
0x180023295  jz      loc_180023172
0x18002329b  cmp     eax, 490h
0x1800232a0  jz      loc_180023172
0x1800232a6  xor     edi, edi
0x1800232a8  jmp     loc_180023202
0x1800232ad  mov     [rsp+0D0h+var_80], r14
0x1800232b2  mov     r9, r13
0x1800232b5  mov     [rsp+0D0h+var_88], rsi
0x1800232ba  mov     [rsp+0D0h+var_90], rdi
0x1800232bf  mov     [rsp+0D0h+var_98], rbx
0x1800232c4  mov     [rsp+0D0h+var_A0], r15
0x1800232c9  mov     [rsp+0D0h+var_A8], r12
0x1800232ce  mov     dword ptr [rsp+0D0h+phkResult], edx
0x1800232d2  call    WPP_SF_qlSSqqqq
0x1800232d7  xor     ecx, ecx
0x1800232d9  jmp     loc_1800230E5
0x1800232de  mov     edx, 13Dh
0x1800232e3  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x1800232ea  mov     ecx, 40Bh
0x1800232ef  mov     r9d, ebx
0x1800232f2  call    WPP_SF_d
0x1800232f7  jmp     loc_18002324F
0x1800232fc  mov     edx, 13Bh
0x180023301  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180023308  mov     ecx, 40Bh
0x18002330d  mov     r9, r12
0x180023310  call    WPP_SF_S
0x180023315  jmp     loc_180023115
0x18002331a  mov     edx, 13Ch
0x18002331f  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180023326  mov     ecx, 40Bh
0x18002332b  mov     r9, r15
0x18002332e  call    WPP_SF_S
0x180023333  jmp     loc_180023188
0x180023338  cmp     [rbp+3Fh+var_50], 0
0x18002333d  jz      loc_1800231FE
0x180023343  jmp     loc_1800231D7
0x180023348  cmp     eax, 490h
0x18002334d  jz      loc_1800231FE
0x180023353  jmp     loc_1800232A6
0x180023358  call    cs:__imp_RegCloseKey
0x18002335e  mov     [rbp+3Fh+var_58], rdi
0x180023362  jmp     loc_180023235
0x180023367  call    cs:__imp_RegCloseKey
0x18002336d  mov     [rbp+3Fh+var_50], rdi
0x180023371  jmp     loc_180023242
```
