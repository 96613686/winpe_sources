# CSecurityAdmin2::ValidateUser(ushort *,ushort *)

- ea: `0x180026e10`
- end: `0x18002706d`
- name: `?ValidateUser@CSecurityAdmin2@@UEAAJPEAG0@Z`
- size: `605`
- prototype: `int(CSecurityAdmin2 *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180015594`
- `0x180018550`
- `0x180026e10`
- `0x180027074`
- `0x180055880`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180026ee7`
- `msvcrt!_wcsnicmp` at `0x180026ee7`
- `msvcrt!_wcsicmp` at `0x180026f3f`
- `msvcrt!_wcsicmp` at `0x180026f3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026ebe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026fc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026ffe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027008`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027019`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026ebe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026fc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026ffe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027008`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027019`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026e91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026f75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026fb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026e91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026f75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026fb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f1c`
- `KERNEL32!GetComputerNameW` at `0x180026f03`
- `KERNEL32!GetComputerNameW` at `0x180026f03`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180026fab`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180026ff1`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180026fab`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180026ff1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall CSecurityAdmin2::ValidateUser(CSecurityAdmin2 *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  void *v5; // rdi
  int v6; // eax
  int v7; // r8d
  int v8; // r9d
  int v9; // esi
  unsigned __int64 v10; // r14
  unsigned __int16 *v11; // rax
  int v12; // r14d
  int result; // eax
  unsigned __int16 *v14; // r14
  void *v15; // rsi
  int v16; // ebx
  DWORD nSize; // [rsp+30h] [rbp-40h] BYREF
  DWORD cchReferencedDomainName; // [rsp+34h] [rbp-3Ch] BYREF
  DWORD cbSid; // [rsp+38h] [rbp-38h] BYREF
  WCHAR Buffer[16]; // [rsp+40h] [rbp-30h] BYREF

  if ( !a2 || !a3 )
    return -2147467261;
  v5 = 0;
  do
  {
    v6 = safe_lstrlenW(a2);
    if ( v7 >= v6 )
      goto LABEL_10;
    v9 = v7 + 1;
    v10 = v7;
  }
  while ( a2[v7] != 92 );
  v11 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v9, 2u));
  v5 = v11;
  if ( !v11 )
    return -2147024882;
  v12 = StringCchCopyNW(v11, v9, a2, v10);
  if ( v12 < 0 )
  {
    CoTaskMemFree(v5);
    return v12;
  }
  v8 = v9;
LABEL_10:
  v14 = &a2[v8];
  if ( _wcsnicmp(v14, L"COM_", 4u) )
    goto LABEL_20;
  nSize = 16;
  if ( !GetComputerNameW(Buffer, &nSize) )
  {
    if ( v5 )
      CoTaskMemFree(v5);
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( _wcsicmp(v14 + 4, Buffer) )
  {
LABEL_20:
    if ( !v5 )
    {
      cbSid = 0;
      cchReferencedDomainName = 16;
      nSize = 0;
      v5 = CoTaskMemAlloc(0x20u);
      if ( !v5 )
        return -2147024882;
      LookupAccountNameLocalW(a2, 0, &cbSid, (LPWSTR)v5, &cchReferencedDomainName, (PSID_NAME_USE)&nSize);
      v15 = CoTaskMemAlloc(cbSid);
      if ( !v15 )
      {
        CoTaskMemFree(v5);
        return -2147024882;
      }
      cchReferencedDomainName = 16;
      if ( !LookupAccountNameLocalW(a2, v15, &cbSid, (LPWSTR)v5, &cchReferencedDomainName, (PSID_NAME_USE)&nSize) )
      {
        CoTaskMemFree(v5);
        CoTaskMemFree(v15);
        return 1;
      }
      CoTaskMemFree(v15);
    }
    v16 = SSPLogonUser((unsigned __int16 *)v5, v14, a3);
    CoTaskMemFree(v5);
    return v16 == 0;
  }
  if ( v5 )
    CoTaskMemFree(v5);
  return 0;
}

```

## disassembly

```asm
0x180026e10  mov     [rsp-28h+arg_0], rbx
0x180026e15  mov     [rsp-28h+arg_18], rsi
0x180026e1a  push    rbp
0x180026e1b  push    rdi
0x180026e1c  push    r12
0x180026e1e  push    r14
0x180026e20  push    r15
0x180026e22  mov     rbp, rsp
0x180026e25  sub     rsp, 70h
0x180026e29  mov     rax, cs:__security_cookie
0x180026e30  xor     rax, rsp
0x180026e33  mov     [rbp+var_10], rax
0x180026e37  mov     r12, r8
0x180026e3a  mov     rbx, rdx
0x180026e3d  test    rdx, rdx
0x180026e40  jz      loc_180027043
0x180026e46  test    r8, r8
0x180026e49  jz      loc_180027043
0x180026e4f  xor     edi, edi
0x180026e51  xor     r9d, r9d
0x180026e54  xor     r8d, r8d
0x180026e57  mov     rcx, rbx; unsigned __int16 *
0x180026e5a  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180026e5f  cmp     r8d, eax
0x180026e62  jge     short loc_180026ED0
0x180026e64  lea     esi, [r8+1]
0x180026e68  movsxd  r14, r8d
0x180026e6b  cmp     word ptr [rbx+r14*2], 5Ch ; '\'
0x180026e71  jz      short loc_180026E78
0x180026e73  mov     r8d, esi
0x180026e76  jmp     short loc_180026E57
0x180026e78  movsxd  r15, esi
0x180026e7b  mov     eax, 2
0x180026e80  mul     r15
0x180026e83  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180026e8a  cmovb   rax, rcx
0x180026e8e  mov     rcx, rax; cb
0x180026e91  call    cs:__imp_CoTaskMemAlloc
0x180026e97  mov     rdi, rax
0x180026e9a  test    rax, rax
0x180026e9d  jz      loc_180026F83
0x180026ea3  mov     r9, r14; unsigned __int64
0x180026ea6  mov     r8, rbx; unsigned __int16 *
0x180026ea9  mov     rdx, r15; unsigned __int64
0x180026eac  mov     rcx, rax; unsigned __int16 *
0x180026eaf  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180026eb4  mov     r14d, eax
0x180026eb7  test    eax, eax
0x180026eb9  jns     short loc_180026ECD
0x180026ebb  mov     rcx, rdi; pv
0x180026ebe  call    cs:__imp_CoTaskMemFree
0x180026ec4  nop
0x180026ec5  mov     eax, r14d
0x180026ec8  jmp     loc_180027048
0x180026ecd  mov     r9d, esi
0x180026ed0  mov     eax, r9d
0x180026ed3  lea     r14, [rbx+rax*2]
0x180026ed7  mov     r8d, 4; MaxCount
0x180026edd  lea     rdx, aCom; "COM_"
0x180026ee4  mov     rcx, r14; String1
0x180026ee7  call    cs:__imp__wcsnicmp
0x180026eed  mov     r15d, 10h
0x180026ef3  test    eax, eax
0x180026ef5  jnz     short loc_180026F5F
0x180026ef7  mov     [rbp+nSize], r15d
0x180026efb  lea     rdx, [rbp+nSize]; nSize
0x180026eff  lea     rcx, [rbp+Buffer]; lpBuffer
0x180026f03  call    cs:__imp_GetComputerNameW
0x180026f09  test    eax, eax
0x180026f0b  jnz     short loc_180026F37
0x180026f0d  test    rdi, rdi
0x180026f10  jz      short loc_180026F1C
0x180026f12  mov     rcx, rdi; pv
0x180026f15  call    cs:__imp_CoTaskMemFree
0x180026f1b  nop
0x180026f1c  call    cs:__imp_GetLastError
0x180026f22  test    eax, eax
0x180026f24  jle     loc_180027048
0x180026f2a  movzx   eax, ax
0x180026f2d  or      eax, 80070000h
0x180026f32  jmp     loc_180027048
0x180026f37  lea     rcx, [r14+8]; String1
0x180026f3b  lea     rdx, [rbp+Buffer]; String2
0x180026f3f  call    cs:__imp__wcsicmp
0x180026f45  test    eax, eax
0x180026f47  jnz     short loc_180026F5F
0x180026f49  test    rdi, rdi
0x180026f4c  jz      short loc_180026F58
0x180026f4e  mov     rcx, rdi; pv
0x180026f51  call    cs:__imp_CoTaskMemFree
0x180026f57  nop
0x180026f58  xor     eax, eax
0x180026f5a  jmp     loc_180027048
0x180026f5f  test    rdi, rdi
0x180026f62  jnz     loc_180027020
0x180026f68  mov     [rbp+cbSid], edi
0x180026f6b  mov     [rbp+var_3C], r15d
0x180026f6f  mov     [rbp+nSize], edi
0x180026f72  lea     ecx, [rdi+20h]; cb
0x180026f75  call    cs:__imp_CoTaskMemAlloc
0x180026f7b  mov     rdi, rax
0x180026f7e  test    rax, rax
0x180026f81  jnz     short loc_180026F8D
0x180026f83  mov     eax, 8007000Eh
0x180026f88  jmp     loc_180027048
0x180026f8d  lea     rax, [rbp+nSize]
0x180026f91  mov     [rsp+70h+peUse], rax; peUse
0x180026f96  lea     rax, [rbp+var_3C]
0x180026f9a  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180026f9f  mov     r9, rdi; ReferencedDomainName
0x180026fa2  lea     r8, [rbp+cbSid]; cbSid
0x180026fa6  xor     edx, edx; Sid
0x180026fa8  mov     rcx, rbx; lpAccountName
0x180026fab  call    cs:__imp_LookupAccountNameLocalW
0x180026fb1  mov     ecx, [rbp+cbSid]; cb
0x180026fb4  call    cs:__imp_CoTaskMemAlloc
0x180026fba  mov     rsi, rax
0x180026fbd  test    rax, rax
0x180026fc0  jnz     short loc_180026FCE
0x180026fc2  mov     rcx, rdi; pv
0x180026fc5  call    cs:__imp_CoTaskMemFree
0x180026fcb  nop
0x180026fcc  jmp     short loc_180026F83
0x180026fce  mov     [rbp+var_3C], r15d
0x180026fd2  lea     rax, [rbp+nSize]
0x180026fd6  mov     [rsp+70h+peUse], rax; peUse
0x180026fdb  lea     rax, [rbp+var_3C]
0x180026fdf  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180026fe4  mov     r9, rdi; ReferencedDomainName
0x180026fe7  lea     r8, [rbp+cbSid]; cbSid
0x180026feb  mov     rdx, rsi; Sid
0x180026fee  mov     rcx, rbx; lpAccountName
0x180026ff1  call    cs:__imp_LookupAccountNameLocalW
0x180026ff7  test    eax, eax
0x180026ff9  jnz     short loc_180027016
0x180026ffb  mov     rcx, rdi; pv
0x180026ffe  call    cs:__imp_CoTaskMemFree
0x180027004  nop
0x180027005  mov     rcx, rsi; pv
0x180027008  call    cs:__imp_CoTaskMemFree
0x18002700e  nop
0x18002700f  mov     eax, 1
0x180027014  jmp     short loc_180027048
0x180027016  mov     rcx, rsi; pv
0x180027019  call    cs:__imp_CoTaskMemFree
0x18002701f  nop
0x180027020  mov     r8, r12; unsigned __int16 *
0x180027023  mov     rdx, r14; unsigned __int16 *
0x180027026  mov     rcx, rdi; unsigned __int16 *
0x180027029  call    ?SSPLogonUser@@YAHPEAG00@Z; SSPLogonUser(ushort *,ushort *,ushort *)
0x18002702e  mov     ebx, eax
0x180027030  mov     rcx, rdi; pv
0x180027033  call    cs:__imp_CoTaskMemFree
0x180027039  nop
0x18002703a  xor     eax, eax
0x18002703c  test    ebx, ebx
0x18002703e  setz    al
0x180027041  jmp     short loc_180027048
0x180027043  mov     eax, 80004003h
0x180027048  mov     rcx, [rbp+var_10]
0x18002704c  xor     rcx, rsp; StackCookie
0x18002704f  call    __security_check_cookie
0x180027054  lea     r11, [rsp+70h+var_s0]
0x180027059  mov     rbx, [r11+30h]
0x18002705d  mov     rsi, [r11+48h]
0x180027061  mov     rsp, r11
0x180027064  pop     r15
0x180027066  pop     r14
0x180027068  pop     r12
0x18002706a  pop     rdi
0x18002706b  pop     rbp
0x18002706c  retn
```
