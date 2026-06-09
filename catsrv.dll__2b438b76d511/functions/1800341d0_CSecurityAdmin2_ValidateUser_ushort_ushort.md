# CSecurityAdmin2::ValidateUser(ushort *,ushort *)

- ea: `0x1800341d0`
- end: `0x18003441d`
- name: `?ValidateUser@CSecurityAdmin2@@UEAAJPEAG0@Z`
- size: `589`
- prototype: `int(CSecurityAdmin2 *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000b440`
- `0x18001a6c8`
- `0x1800341d0`
- `0x180034424`
- `0x180055550`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180034297`
- `msvcrt!_wcsnicmp` at `0x180034297`
- `msvcrt!_wcsicmp` at `0x1800342ee`
- `msvcrt!_wcsicmp` at `0x1800342ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342cb`
- `KERNEL32!GetComputerNameW` at `0x1800342b3`
- `KERNEL32!GetComputerNameW` at `0x1800342b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034378`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800343b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800343bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800343cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800343e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034378`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800343b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800343bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800343cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800343e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034250`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034323`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034362`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034250`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034323`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034362`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180034359`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800343a5`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180034359`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800343a5`

## pseudocode

```c
int __fastcall CSecurityAdmin2::ValidateUser(CSecurityAdmin2 *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned __int16 *v5; // rdi
  int v6; // eax
  int v7; // r8d
  int v8; // r9d
  unsigned __int64 v9; // rsi
  int v10; // r14d
  unsigned __int16 *v11; // rax
  int v12; // esi
  unsigned __int16 *v13; // r14
  int result; // eax
  WCHAR *v15; // rax
  void *v16; // rsi
  int v17; // ebx
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
      goto LABEL_9;
    v9 = v7;
    v10 = v7 + 1;
  }
  while ( a2[v7] != 92 );
  v11 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v10, 2u));
  v5 = v11;
  if ( !v11 )
    return -2147024882;
  v12 = StringCchCopyNW(v11, v10, a2, v9);
  if ( v12 < 0 )
  {
LABEL_24:
    CoTaskMemFree(v5);
    return v12;
  }
  v8 = v10;
LABEL_9:
  v13 = &a2[v8];
  if ( _wcsnicmp(v13, L"COM_", 4u) )
    goto LABEL_19;
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
  if ( _wcsicmp(v13 + 4, Buffer) )
  {
LABEL_19:
    if ( !v5 )
    {
      cbSid = 0;
      cchReferencedDomainName = 16;
      nSize = 0;
      v15 = (WCHAR *)CoTaskMemAlloc(0x20u);
      v5 = v15;
      if ( !v15 )
        return -2147024882;
      LookupAccountNameLocalW(a2, 0, &cbSid, v15, &cchReferencedDomainName, (PSID_NAME_USE)&nSize);
      v16 = CoTaskMemAlloc(cbSid);
      if ( !v16 )
      {
        v12 = -2147024882;
        goto LABEL_24;
      }
      cchReferencedDomainName = 16;
      if ( !LookupAccountNameLocalW(a2, v16, &cbSid, v5, &cchReferencedDomainName, (PSID_NAME_USE)&nSize) )
      {
        CoTaskMemFree(v5);
        CoTaskMemFree(v16);
        return 1;
      }
      CoTaskMemFree(v16);
    }
    v17 = SSPLogonUser(v5, v13, a3);
    CoTaskMemFree(v5);
    return v17 == 0;
  }
  if ( v5 )
    CoTaskMemFree(v5);
  return 0;
}

```

## disassembly

```asm
0x1800341d0  mov     [rsp-28h+arg_0], rbx
0x1800341d5  mov     [rsp-28h+arg_18], rsi
0x1800341da  push    rbp
0x1800341db  push    rdi
0x1800341dc  push    r12
0x1800341de  push    r14
0x1800341e0  push    r15
0x1800341e2  mov     rbp, rsp
0x1800341e5  sub     rsp, 70h
0x1800341e9  mov     rax, cs:__security_cookie
0x1800341f0  xor     rax, rsp
0x1800341f3  mov     [rbp+var_10], rax
0x1800341f7  mov     r12, r8
0x1800341fa  mov     rbx, rdx
0x1800341fd  test    rdx, rdx
0x180034200  jz      loc_1800343F3
0x180034206  test    r8, r8
0x180034209  jz      loc_1800343F3
0x18003420f  xor     edi, edi
0x180034211  xor     r9d, r9d
0x180034214  xor     r8d, r8d
0x180034217  mov     rcx, rbx; unsigned __int16 *
0x18003421a  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003421f  cmp     r8d, eax
0x180034222  jge     short loc_180034280
0x180034224  movsxd  rsi, r8d
0x180034227  lea     r14d, [r8+1]
0x18003422b  cmp     word ptr [rbx+rsi*2], 5Ch ; '\'
0x180034230  jz      short loc_180034237
0x180034232  mov     r8d, r14d
0x180034235  jmp     short loc_180034217
0x180034237  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003423e  movsxd  r15, r14d
0x180034241  mov     eax, 2
0x180034246  mul     r15
0x180034249  cmovb   rax, rcx
0x18003424d  mov     rcx, rax; cb
0x180034250  call    cs:__imp_CoTaskMemAlloc
0x180034256  mov     rdi, rax
0x180034259  test    rax, rax
0x18003425c  jz      loc_180034331
0x180034262  mov     r9, rsi; unsigned __int64
0x180034265  mov     r8, rbx; unsigned __int16 *
0x180034268  mov     rdx, r15; unsigned __int64
0x18003426b  mov     rcx, rax; unsigned __int16 *
0x18003426e  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180034273  mov     esi, eax
0x180034275  test    eax, eax
0x180034277  js      loc_180034375
0x18003427d  mov     r9d, r14d
0x180034280  mov     eax, r9d
0x180034283  lea     rdx, aCom; "COM_"
0x18003428a  mov     r8d, 4; MaxCount
0x180034290  lea     r14, [rbx+rax*2]
0x180034294  mov     rcx, r14; String1
0x180034297  call    cs:__imp__wcsnicmp
0x18003429d  mov     r15d, 10h
0x1800342a3  test    eax, eax
0x1800342a5  jnz     short loc_18003430D
0x1800342a7  lea     rdx, [rbp+nSize]; nSize
0x1800342ab  mov     [rbp+nSize], r15d
0x1800342af  lea     rcx, [rbp+Buffer]; lpBuffer
0x1800342b3  call    cs:__imp_GetComputerNameW
0x1800342b9  test    eax, eax
0x1800342bb  jnz     short loc_1800342E6
0x1800342bd  test    rdi, rdi
0x1800342c0  jz      short loc_1800342CB
0x1800342c2  mov     rcx, rdi; pv
0x1800342c5  call    cs:__imp_CoTaskMemFree
0x1800342cb  call    cs:__imp_GetLastError
0x1800342d1  test    eax, eax
0x1800342d3  jle     loc_1800343F8
0x1800342d9  movzx   eax, ax
0x1800342dc  or      eax, 80070000h
0x1800342e1  jmp     loc_1800343F8
0x1800342e6  lea     rcx, [r14+8]; String1
0x1800342ea  lea     rdx, [rbp+Buffer]; String2
0x1800342ee  call    cs:__imp__wcsicmp
0x1800342f4  test    eax, eax
0x1800342f6  jnz     short loc_18003430D
0x1800342f8  test    rdi, rdi
0x1800342fb  jz      short loc_180034306
0x1800342fd  mov     rcx, rdi; pv
0x180034300  call    cs:__imp_CoTaskMemFree
0x180034306  xor     eax, eax
0x180034308  jmp     loc_1800343F8
0x18003430d  test    rdi, rdi
0x180034310  jnz     loc_1800343D1
0x180034316  lea     ecx, [rdi+20h]; cb
0x180034319  mov     [rbp+cbSid], edi
0x18003431c  mov     [rbp+var_3C], r15d
0x180034320  mov     [rbp+nSize], edi
0x180034323  call    cs:__imp_CoTaskMemAlloc
0x180034329  mov     rdi, rax
0x18003432c  test    rax, rax
0x18003432f  jnz     short loc_18003433B
0x180034331  mov     eax, 8007000Eh
0x180034336  jmp     loc_1800343F8
0x18003433b  lea     rax, [rbp+nSize]
0x18003433f  mov     r9, rdi; ReferencedDomainName
0x180034342  mov     [rsp+70h+peUse], rax; peUse
0x180034347  lea     r8, [rbp+cbSid]; cbSid
0x18003434b  lea     rax, [rbp+var_3C]
0x18003434f  xor     edx, edx; Sid
0x180034351  mov     rcx, rbx; lpAccountName
0x180034354  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180034359  call    cs:__imp_LookupAccountNameLocalW
0x18003435f  mov     ecx, [rbp+cbSid]; cb
0x180034362  call    cs:__imp_CoTaskMemAlloc
0x180034368  mov     rsi, rax
0x18003436b  test    rax, rax
0x18003436e  jnz     short loc_180034382
0x180034370  mov     esi, 8007000Eh
0x180034375  mov     rcx, rdi; pv
0x180034378  call    cs:__imp_CoTaskMemFree
0x18003437e  mov     eax, esi
0x180034380  jmp     short loc_1800343F8
0x180034382  lea     rax, [rbp+nSize]
0x180034386  mov     [rbp+var_3C], r15d
0x18003438a  mov     [rsp+70h+peUse], rax; peUse
0x18003438f  lea     r8, [rbp+cbSid]; cbSid
0x180034393  lea     rax, [rbp+var_3C]
0x180034397  mov     r9, rdi; ReferencedDomainName
0x18003439a  mov     rdx, rsi; Sid
0x18003439d  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800343a2  mov     rcx, rbx; lpAccountName
0x1800343a5  call    cs:__imp_LookupAccountNameLocalW
0x1800343ab  test    eax, eax
0x1800343ad  jnz     short loc_1800343C8
0x1800343af  mov     rcx, rdi; pv
0x1800343b2  call    cs:__imp_CoTaskMemFree
0x1800343b8  mov     rcx, rsi; pv
0x1800343bb  call    cs:__imp_CoTaskMemFree
0x1800343c1  mov     eax, 1
0x1800343c6  jmp     short loc_1800343F8
0x1800343c8  mov     rcx, rsi; pv
0x1800343cb  call    cs:__imp_CoTaskMemFree
0x1800343d1  mov     r8, r12; unsigned __int16 *
0x1800343d4  mov     rdx, r14; unsigned __int16 *
0x1800343d7  mov     rcx, rdi; unsigned __int16 *
0x1800343da  call    ?SSPLogonUser@@YAHPEAG00@Z; SSPLogonUser(ushort *,ushort *,ushort *)
0x1800343df  mov     rcx, rdi; pv
0x1800343e2  mov     ebx, eax
0x1800343e4  call    cs:__imp_CoTaskMemFree
0x1800343ea  xor     eax, eax
0x1800343ec  test    ebx, ebx
0x1800343ee  setz    al
0x1800343f1  jmp     short loc_1800343F8
0x1800343f3  mov     eax, 80004003h
0x1800343f8  mov     rcx, [rbp+var_10]
0x1800343fc  xor     rcx, rsp; StackCookie
0x1800343ff  call    __security_check_cookie
0x180034404  lea     r11, [rsp+70h+var_s0]
0x180034409  mov     rbx, [r11+30h]
0x18003440d  mov     rsi, [r11+48h]
0x180034411  mov     rsp, r11
0x180034414  pop     r15
0x180034416  pop     r14
0x180034418  pop     r12
0x18003441a  pop     rdi
0x18003441b  pop     rbp
0x18003441c  retn
```
