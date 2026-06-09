# ConvertPathToUNC(ushort const *,ushort * *)

- ea: `0x18003e788`
- end: `0x18003ea50`
- name: `?ConvertPathToUNC@@YAJPEBGPEAPEAG@Z`
- size: `712`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040dd4`

## callees

- `0x18000f900`
- `0x18003e788`
- `0x18003ea58`
- `0x18004d900`
- `0x18004dcf0`
- `0x18009a630`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003ea24`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003ea3c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003ea24`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003ea3c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003e972`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003e972`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e8c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e8c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e8ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e8ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e809`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e809`

## pseudocode

```c
__int64 __fastcall ConvertPathToUNC(WCHAR *a1, unsigned __int16 **a2)
{
  int Connection; // eax
  __int64 v6; // rbx
  __int64 v7; // rax
  wchar_t *v8; // rsi
  __int64 v9; // rcx
  unsigned int v10; // esi
  __int64 v11; // rax
  unsigned __int16 *v12; // rbx
  unsigned int v13; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-C4h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v18; // [rsp+48h] [rbp-B8h] BYREF
  int v19; // [rsp+4Ah] [rbp-B6h]
  wchar_t Str[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[508]; // [rsp+54h] [rbp-ACh] BYREF

  v13 = 0;
  if ( !*a1 || a1[1] != 58 )
    goto LABEL_7;
  if ( !dword_1800C2F04 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\OLEAUT", 0, 1u, &hKey) )
    {
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"RegisterNetDriveAsMapped", 0, &Type, Data, &cbData)
        && Type == 4
        && *(_DWORD *)Data == 1 )
      {
        dword_1800C2F00 = 1;
      }
      RegCloseKey(hKey);
    }
    dword_1800C2F04 = 1;
  }
  if ( dword_1800C2F00 )
    goto LABEL_7;
  v18 = *a1;
  v19 = 58;
  v13 = 256;
  Connection = oWNetGetConnection(&v18, (__int64)Str, (__int64)&v13);
  if ( Connection )
  {
    if ( Connection == 8 )
      return 2147942414LL;
    if ( Connection != 50 )
    {
      if ( Connection == 59 )
        return 2147680259LL;
      if ( Connection != 87 )
      {
        if ( Connection != 234 && Connection != 487 )
        {
          if ( Connection != 2250 )
            return 0;
          goto LABEL_7;
        }
        return 2147680259LL;
      }
    }
LABEL_7:
    *a2 = 0;
    return 0;
  }
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( Str[v7] );
  v13 = v7;
  if ( Str[0] == 92 && Str[1] == 92 )
  {
    do
LABEL_35:
      ++v6;
    while ( a1[v6] );
    v10 = 2 * (v6 + v7) - 2;
    v11 = MemAlloc(v10);
    v12 = (unsigned __int16 *)v11;
    if ( v11 )
    {
      _o_wcscpy_s(v11, v10, Str);
      _o_wcscpy_s(&v12[v13], v10 - v13, a1 + 2);
      *a2 = v12;
      return 0;
    }
    return 2147942414LL;
  }
  v8 = wcschr(Str, 0x2Fu);
  if ( !v8 || Str[v13 - 1] != 58 )
    goto LABEL_7;
  if ( v13 + 1 < 0x100 )
  {
    memmove_0(v21, Str, 2LL * (v13 - 1));
    *(_DWORD *)Str = 6029404;
    v8[2] = 92;
    v9 = v13 + 1;
    if ( (unsigned __int64)(2 * v9) >= 0x200 )
      _report_rangecheckfailure();
    Str[v9] = 0;
    LODWORD(v7) = v9;
    v13 = v9;
    goto LABEL_35;
  }
  return 2147647510LL;
}

```

## disassembly

```asm
0x18003e788  mov     [rsp-8+arg_10], rbx
0x18003e78d  push    rbp
0x18003e78e  push    rsi
0x18003e78f  push    rdi
0x18003e790  push    r12
0x18003e792  push    r13
0x18003e794  push    r14
0x18003e796  push    r15
0x18003e798  lea     rbp, [rsp-160h]
0x18003e7a0  sub     rsp, 260h
0x18003e7a7  mov     rax, cs:__security_cookie
0x18003e7ae  xor     rax, rsp
0x18003e7b1  mov     [rbp+190h+var_40], rax
0x18003e7b8  xor     r12d, r12d
0x18003e7bb  mov     r15, rdx
0x18003e7be  mov     rdi, rcx
0x18003e7c1  mov     [rsp+290h+var_260], r12d
0x18003e7c6  cmp     [rcx], r12w
0x18003e7ca  jz      short loc_18003E822
0x18003e7cc  lea     r13d, [r12+3Ah]
0x18003e7d1  cmp     [rcx+2], r13w
0x18003e7d6  jnz     short loc_18003E822
0x18003e7d8  cmp     cs:dword_1800C2F04, r12d
0x18003e7df  jnz     short loc_18003E819
0x18003e7e1  lea     rax, [rsp+290h+hKey]
0x18003e7e6  mov     [rsp+290h+hKey], r12
0x18003e7eb  lea     ebx, [r12+1]
0x18003e7f0  mov     [rsp+290h+phkResult], rax; phkResult
0x18003e7f5  mov     r9d, ebx; samDesired
0x18003e7f8  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\OLEAUT"
0x18003e7ff  xor     r8d, r8d; ulOptions
0x18003e802  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e809  call    cs:__imp_RegOpenKeyExW
0x18003e80f  test    eax, eax
0x18003e811  jz      short loc_18003E88E
0x18003e813  mov     cs:dword_1800C2F04, ebx
0x18003e819  cmp     cs:dword_1800C2F00, r12d
0x18003e820  jz      short loc_18003E851
0x18003e822  mov     [r15], r12
0x18003e825  xor     eax, eax
0x18003e827  mov     rcx, [rbp+190h+var_40]
0x18003e82e  xor     rcx, rsp; StackCookie
0x18003e831  call    __security_check_cookie
0x18003e836  mov     rbx, [rsp+290h+arg_10]
0x18003e83e  add     rsp, 260h
0x18003e845  pop     r15
0x18003e847  pop     r14
0x18003e849  pop     r13
0x18003e84b  pop     r12
0x18003e84d  pop     rdi
0x18003e84e  pop     rsi
0x18003e84f  pop     rbp
0x18003e850  retn
0x18003e851  movzx   eax, word ptr [rdi]
0x18003e854  lea     r8, [rsp+290h+var_260]
0x18003e859  lea     rdx, [rsp+290h+Str]
0x18003e85e  mov     [rsp+290h+var_248], ax
0x18003e863  lea     rcx, [rsp+290h+var_248]
0x18003e868  mov     [rsp+290h+var_246], r13d
0x18003e86d  mov     [rsp+290h+var_260], 100h
0x18003e875  call    oWNetGetConnection
0x18003e87a  test    eax, eax
0x18003e87c  jz      loc_18003E934
0x18003e882  cmp     eax, 8
0x18003e885  jnz     short loc_18003E8F5
0x18003e887  mov     eax, 8007000Eh
0x18003e88c  jmp     short loc_18003E827
0x18003e88e  mov     rcx, [rsp+290h+hKey]; hKey
0x18003e893  lea     rax, [rsp+290h+cbData]
0x18003e898  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18003e89d  lea     r9, [rsp+290h+Type]; lpType
0x18003e8a2  lea     rax, [rsp+290h+Data]
0x18003e8a7  mov     [rsp+290h+Type], r12d
0x18003e8ac  xor     r8d, r8d; lpReserved
0x18003e8af  mov     [rsp+290h+phkResult], rax; lpData
0x18003e8b4  lea     rdx, aRegisternetdri; "RegisterNetDriveAsMapped"
0x18003e8bb  mov     dword ptr [rsp+290h+Data], r12d
0x18003e8c0  mov     [rsp+290h+cbData], 4
0x18003e8c8  call    cs:__imp_RegQueryValueExW
0x18003e8ce  test    eax, eax
0x18003e8d0  jnz     short loc_18003E8E5
0x18003e8d2  cmp     [rsp+290h+Type], 4
0x18003e8d7  jnz     short loc_18003E8E5
0x18003e8d9  cmp     dword ptr [rsp+290h+Data], ebx
0x18003e8dd  jnz     short loc_18003E8E5
0x18003e8df  mov     cs:dword_1800C2F00, ebx
0x18003e8e5  mov     rcx, [rsp+290h+hKey]; hKey
0x18003e8ea  call    cs:__imp_RegCloseKey
0x18003e8f0  jmp     loc_18003E813
0x18003e8f5  cmp     eax, 32h ; '2'
0x18003e8f8  jz      loc_18003E822
0x18003e8fe  cmp     eax, 3Bh ; ';'
0x18003e901  jz      short loc_18003E92A
0x18003e903  cmp     eax, 57h ; 'W'
0x18003e906  jz      loc_18003E822
0x18003e90c  cmp     eax, 0EAh
0x18003e911  jz      short loc_18003E92A
0x18003e913  cmp     eax, 1E7h
0x18003e918  jz      short loc_18003E92A
0x18003e91a  cmp     eax, 8CAh
0x18003e91f  jz      loc_18003E822
0x18003e925  jmp     loc_18003E825
0x18003e92a  mov     eax, 80030003h
0x18003e92f  jmp     loc_18003E827
0x18003e934  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003e938  lea     rcx, [rsp+290h+Str]
0x18003e93d  mov     rax, rbx
0x18003e940  inc     rax
0x18003e943  cmp     [rcx+rax*2], r12w
0x18003e948  jnz     short loc_18003E940
0x18003e94a  mov     r14d, 5Ch ; '\'
0x18003e950  mov     [rsp+290h+var_260], eax
0x18003e954  cmp     [rsp+290h+Str], r14w
0x18003e95a  jnz     short loc_18003E968
0x18003e95c  cmp     [rsp+290h+Str+2], r14w
0x18003e962  jz      loc_18003E9F0
0x18003e968  mov     edx, 2Fh ; '/'; Ch
0x18003e96d  lea     rcx, [rsp+290h+Str]; Str
0x18003e972  call    cs:__imp_wcschr
0x18003e978  mov     rsi, rax
0x18003e97b  test    rax, rax
0x18003e97e  jz      loc_18003E822
0x18003e984  mov     r8d, [rsp+290h+var_260]
0x18003e989  lea     edx, [r8-1]
0x18003e98d  add     rdx, rdx
0x18003e990  cmp     [rsp+rdx+290h+Str], r13w
0x18003e996  jnz     loc_18003E822
0x18003e99c  lea     ecx, [r8+1]
0x18003e9a0  cmp     ecx, 100h
0x18003e9a6  jb      short loc_18003E9B2
0x18003e9a8  mov     eax, 80028016h
0x18003e9ad  jmp     loc_18003E827
0x18003e9b2  mov     r8, rdx; Size
0x18003e9b5  lea     rcx, [rsp+290h+var_23C]; void *
0x18003e9ba  lea     rdx, [rsp+290h+Str]; Src
0x18003e9bf  call    memmove_0
0x18003e9c4  mov     dword ptr [rsp+290h+Str], 5C005Ch
0x18003e9cc  mov     [rsi+4], r14w
0x18003e9d1  mov     ecx, [rsp+290h+var_260]
0x18003e9d5  inc     ecx
0x18003e9d7  lea     rdx, [rcx+rcx]
0x18003e9db  cmp     rdx, 200h
0x18003e9e2  jnb     short loc_18003EA4A
0x18003e9e4  mov     [rsp+rdx+290h+Str], r12w
0x18003e9ea  mov     eax, ecx
0x18003e9ec  mov     [rsp+290h+var_260], ecx
0x18003e9f0  inc     rbx
0x18003e9f3  cmp     [rdi+rbx*2], r12w
0x18003e9f8  jnz     short loc_18003E9F0
0x18003e9fa  add     eax, ebx
0x18003e9fc  lea     esi, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18003ea03  mov     ecx, esi
0x18003ea05  mov     r14d, esi
0x18003ea08  call    MemAlloc
0x18003ea0d  mov     rbx, rax
0x18003ea10  test    rax, rax
0x18003ea13  jz      loc_18003E887
0x18003ea19  lea     r8, [rsp+290h+Str]
0x18003ea1e  mov     edx, r14d
0x18003ea21  mov     rcx, rax
0x18003ea24  call    cs:__imp__o_wcscpy_s
0x18003ea2a  mov     eax, [rsp+290h+var_260]
0x18003ea2e  lea     r8, [rdi+4]
0x18003ea32  sub     esi, [rsp+290h+var_260]
0x18003ea36  mov     edx, esi
0x18003ea38  lea     rcx, [rbx+rax*2]
0x18003ea3c  call    cs:__imp__o_wcscpy_s
0x18003ea42  mov     [r15], rbx
0x18003ea45  jmp     loc_18003E825
0x18003ea4a  call    __report_rangecheckfailure
```
