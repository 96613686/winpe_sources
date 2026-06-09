# CSecurityAdmin2::CanonicalizeUserName(ushort *,ushort * *,int)

- ea: `0x180029e90`
- end: `0x18002a340`
- name: `?CanonicalizeUserName@CSecurityAdmin2@@UEAAJPEAGPEAPEAGH@Z`
- size: `1200`
- prototype: `int __fastcall(CSecurityAdmin2 *this, unsigned __int16 *, LPVOID *, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001e60`
- `0x180015594`
- `0x18001c6a4`
- `0x1800275d4`
- `0x180029e90`
- `0x18002a69c`
- `0x18002a850`
- `0x18002a8a8`
- `0x18005583a`
- `0x180055880`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002a133`
- `msvcrt!_wcsicmp` at `0x18002a1ec`
- `msvcrt!_wcsicmp` at `0x18002a24c`
- `msvcrt!_wcsicmp` at `0x18002a133`
- `msvcrt!_wcsicmp` at `0x18002a1ec`
- `msvcrt!_wcsicmp` at `0x18002a24c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029f78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a0ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a302`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029f78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a0ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a302`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029f50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a085`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a290`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029f50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a085`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a290`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029f37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029f37`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18002a073`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18002a0c3`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18002a073`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18002a0c3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180029f28`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180029f28`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall CSecurityAdmin2::CanonicalizeUserName(CSecurityAdmin2 *this, unsigned __int16 *a2, LPVOID *a3, int a4)
{
  CGetAccountDomain *v7; // rcx
  int result; // eax
  const WCHAR *v9; // rcx
  SIZE_T v10; // rdi
  unsigned __int16 *v11; // rax
  int v12; // ebx
  void *v13; // r11
  int v14; // eax
  const unsigned __int16 *v15; // rcx
  int v16; // r10d
  unsigned __int16 v17; // si
  __int64 v18; // r11
  void *v19; // rbx
  BOOL v20; // esi
  __int64 v21; // rax
  __int64 v22; // rcx
  SIZE_T v23; // rbx
  unsigned __int16 *v24; // rax
  int v25; // eax
  PSID Sid; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbSid; // [rsp+3Ch] [rbp-C4h] BYREF
  wchar_t ReferencedDomainName[280]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR AccountName[280]; // [rsp+270h] [rbp+170h] BYREF

  memset_0(ReferencedDomainName, 0, 0x222u);
  memset_0(AccountName, 0, 0x222u);
  *a3 = 0;
  result = CGetAccountDomain::Init(v7);
  if ( result < 0 )
    return result;
  if ( (int)safe_lstrlenW(a2) >= 273 )
    return -2147024809;
  if ( a4 || (Sid = 0, !ConvertStringSidToSidW(v9, &Sid)) )
  {
    while ( 1 )
    {
      v14 = safe_lstrlenW(a2);
      if ( v16 >= v14 )
        break;
      v17 = a2[v16];
      if ( v17 == 92 || v17 == 47 )
      {
        a2[v16] = 0;
        result = StringCchCopyW(ReferencedDomainName, 0x111u, a2);
        a2[v18] = v17;
        if ( result < 0 )
          return result;
        result = StringCchCopyW(AccountName, 0x111u, &a2[v18 + 1]);
        if ( result < 0 )
          return result;
      }
    }
    if ( ReferencedDomainName[0] )
      goto LABEL_29;
    if ( AccountName[0] )
    {
LABEL_20:
      cbSid = 0;
      LODWORD(Sid) = 0;
      cchReferencedDomainName = 16;
      if ( LookupAccountNameLocalW(
             AccountName,
             0,
             &cbSid,
             ReferencedDomainName,
             &cchReferencedDomainName,
             (PSID_NAME_USE)&Sid) )
      {
        goto LABEL_42;
      }
      v19 = CoTaskMemAlloc(cbSid);
      if ( !v19 )
        return -2147024882;
      cchReferencedDomainName = 16;
      v20 = LookupAccountNameLocalW(
              AccountName,
              v19,
              &cbSid,
              ReferencedDomainName,
              &cchReferencedDomainName,
              (PSID_NAME_USE)&Sid);
      CoTaskMemFree(v19);
      if ( a4 )
      {
        if ( !v20 )
          goto LABEL_24;
LABEL_42:
        if ( _wcsicmp(ReferencedDomainName, qword_1800733E8) )
        {
LABEL_43:
          v21 = -1;
          v22 = -1;
          do
            ++v22;
          while ( ReferencedDomainName[v22] );
          do
            ++v21;
          while ( AccountName[v21] );
          v23 = (unsigned int)(2 * (v22 + v21) + 4);
          v24 = (unsigned __int16 *)CoTaskMemAlloc(v23);
          *a3 = v24;
          if ( v24 )
          {
            if ( ReferencedDomainName[0] )
              v25 = StringCbPrintfW(v24, v23, L"%s/%s", ReferencedDomainName, AccountName);
            else
              v25 = StringCbCopyW(v24, v23, AccountName);
            v12 = v25;
            if ( v25 < 0 )
            {
              CoTaskMemFree(*a3);
              *a3 = 0;
            }
            return v12;
          }
          return -2147024882;
        }
LABEL_35:
        result = StringCchCopyW(ReferencedDomainName, 0x111u, L".");
        if ( result < 0 )
          return result;
        goto LABEL_43;
      }
      if ( v20 && !ReferencedDomainName[0] )
        goto LABEL_42;
      result = StringCchCopyW(ReferencedDomainName, 0x111u, L".");
      if ( result < 0 )
        return result;
LABEL_29:
      if ( _wcsicmp(ReferencedDomainName, L".") )
      {
        if ( (unsigned int)IsValidUserName(ReferencedDomainName, AccountName) )
          goto LABEL_42;
        if ( _wcsicmp(ReferencedDomainName, qword_1800733E8) )
        {
          if ( a4 )
            return -2147023564;
          goto LABEL_42;
        }
        Sid = 0;
        result = GetLocalizedBUILTIN((unsigned __int16 **)&Sid);
        if ( result < 0 )
          return result;
        if ( (unsigned int)IsValidUserName(Sid, AccountName) )
        {
          result = StringCchCopyW(ReferencedDomainName, 0x111u, (const unsigned __int16 *)Sid);
          if ( result < 0 )
            return result;
          goto LABEL_42;
        }
        if ( !a4 )
          goto LABEL_42;
      }
      else
      {
        Sid = 0;
        result = GetLocalizedBUILTIN((unsigned __int16 **)&Sid);
        if ( result < 0 )
          return result;
        result = StringCchCopyW(ReferencedDomainName, 0x111u, (const unsigned __int16 *)Sid);
        if ( result < 0 )
          return result;
        if ( (unsigned int)IsValidUserName(ReferencedDomainName, AccountName) )
          goto LABEL_43;
        if ( !a4 || (unsigned int)IsValidUserName(qword_1800733E8, AccountName) )
          goto LABEL_35;
      }
LABEL_24:
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    if ( (int)safe_lstrlenW(v15) <= 256 )
    {
      result = StringCchCopyW(AccountName, 0x111u, a2);
      if ( result < 0 )
        return result;
      goto LABEL_20;
    }
    return -2147024809;
  }
  LocalFree(Sid);
  v10 = 2 * (unsigned int)safe_lstrlenW(a2) + 2;
  v11 = (unsigned __int16 *)CoTaskMemAlloc(v10);
  if ( !v11 )
    return -2147024882;
  v12 = StringCbCopyW(v11, (unsigned int)v10, a2);
  if ( v12 < 0 )
  {
    CoTaskMemFree(v13);
    return v12;
  }
  *a3 = v13;
  return 0;
}

```

## disassembly

```asm
0x180029e90  mov     [rsp-8+arg_0], rbx
0x180029e95  mov     [rsp-8+arg_18], rsi
0x180029e9a  push    rbp
0x180029e9b  push    rdi
0x180029e9c  push    r12
0x180029e9e  push    r14
0x180029ea0  push    r15
0x180029ea2  lea     rbp, [rsp-3B0h]
0x180029eaa  sub     rsp, 4B0h
0x180029eb1  mov     rax, cs:__security_cookie
0x180029eb8  xor     rax, rsp
0x180029ebb  mov     [rbp+3D0h+var_30], rax
0x180029ec2  mov     r14, r8
0x180029ec5  lea     rcx, [rsp+4D0h+ReferencedDomainName]; void *
0x180029eca  mov     rbx, rdx
0x180029ecd  mov     esi, 222h
0x180029ed2  mov     r8d, esi; Size
0x180029ed5  xor     edx, edx; Val
0x180029ed7  mov     edi, r9d
0x180029eda  call    memset_0
0x180029edf  mov     r8d, esi; Size
0x180029ee2  lea     rcx, [rbp+3D0h+AccountName]; void *
0x180029ee9  xor     edx, edx; Val
0x180029eeb  call    memset_0
0x180029ef0  xor     r15d, r15d
0x180029ef3  mov     [r14], r15
0x180029ef6  call    ?Init@CGetAccountDomain@@QEAAJXZ; CGetAccountDomain::Init(void)
0x180029efb  test    eax, eax
0x180029efd  js      loc_18002A315
0x180029f03  mov     rcx, rbx; unsigned __int16 *
0x180029f06  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180029f0b  mov     r12d, 111h
0x180029f11  cmp     eax, r12d
0x180029f14  jge     loc_18002A310
0x180029f1a  test    edi, edi
0x180029f1c  jnz     short loc_180029F8F
0x180029f1e  lea     rdx, [rsp+4D0h+Sid]; Sid
0x180029f23  mov     [rsp+4D0h+Sid], r15
0x180029f28  call    cs:__imp_ConvertStringSidToSidW
0x180029f2e  test    eax, eax
0x180029f30  jz      short loc_180029F8F
0x180029f32  mov     rcx, [rsp+4D0h+Sid]; hMem
0x180029f37  call    cs:__imp_LocalFree
0x180029f3d  mov     rcx, rbx; unsigned __int16 *
0x180029f40  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180029f45  lea     eax, ds:2[rax*2]
0x180029f4c  mov     ecx, eax; cb
0x180029f4e  mov     edi, eax
0x180029f50  call    cs:__imp_CoTaskMemAlloc
0x180029f56  mov     r11, rax
0x180029f59  test    rax, rax
0x180029f5c  jz      loc_18002A29E
0x180029f62  mov     r8, rbx; unsigned __int16 *
0x180029f65  mov     edx, edi; unsigned __int64
0x180029f67  mov     rcx, rax; unsigned __int16 *
0x180029f6a  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180029f6f  mov     ebx, eax
0x180029f71  test    eax, eax
0x180029f73  jns     short loc_180029F85
0x180029f75  mov     rcx, r11; pv
0x180029f78  call    cs:__imp_CoTaskMemFree
0x180029f7e  mov     eax, ebx
0x180029f80  jmp     loc_18002A315
0x180029f85  mov     [r14], r11
0x180029f88  xor     eax, eax
0x180029f8a  jmp     loc_18002A315
0x180029f8f  mov     r10d, r15d
0x180029f92  mov     rcx, rbx; unsigned __int16 *
0x180029f95  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180029f9a  cmp     r10d, eax
0x180029f9d  jge     short loc_180029FF9
0x180029f9f  movsxd  r11, r10d
0x180029fa2  movzx   esi, word ptr [rbx+r11*2]
0x180029fa7  cmp     si, 5Ch ; '\'
0x180029fab  jz      short loc_180029FB3
0x180029fad  cmp     si, 2Fh ; '/'
0x180029fb1  jnz     short loc_180029FF4
0x180029fb3  mov     r8, rbx; unsigned __int16 *
0x180029fb6  mov     [rbx+r11*2], r15w
0x180029fbb  mov     rdx, r12; unsigned __int64
0x180029fbe  lea     rcx, [rsp+4D0h+ReferencedDomainName]; unsigned __int16 *
0x180029fc3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029fc8  mov     [rbx+r11*2], si
0x180029fcd  test    eax, eax
0x180029fcf  js      loc_18002A315
0x180029fd5  lea     r8, [rbx+2]
0x180029fd9  mov     rdx, r12; unsigned __int64
0x180029fdc  lea     r8, [r8+r11*2]; unsigned __int16 *
0x180029fe0  lea     rcx, [rbp+3D0h+AccountName]; unsigned __int16 *
0x180029fe7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029fec  test    eax, eax
0x180029fee  js      loc_18002A315
0x180029ff4  inc     r10d
0x180029ff7  jmp     short loc_180029F92
0x180029ff9  cmp     [rsp+4D0h+ReferencedDomainName], r15w
0x180029fff  jnz     loc_18002A127
0x18002a005  cmp     [rbp+3D0h+AccountName], r15w
0x18002a00d  jnz     short loc_18002A039
0x18002a00f  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18002a014  cmp     eax, 100h
0x18002a019  jg      loc_18002A310
0x18002a01f  mov     r8, rbx; unsigned __int16 *
0x18002a022  lea     rcx, [rbp+3D0h+AccountName]; unsigned __int16 *
0x18002a029  mov     rdx, r12; unsigned __int64
0x18002a02c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a031  test    eax, eax
0x18002a033  js      loc_18002A315
0x18002a039  lea     rax, [rsp+4D0h+Sid]
0x18002a03e  mov     [rsp+4D0h+cbSid], r15d
0x18002a043  mov     [rsp+4D0h+peUse], rax; peUse
0x18002a048  lea     r9, [rsp+4D0h+ReferencedDomainName]; ReferencedDomainName
0x18002a04d  lea     rax, [rsp+4D0h+var_498]
0x18002a052  mov     dword ptr [rsp+4D0h+Sid], r15d
0x18002a057  mov     esi, 10h
0x18002a05c  mov     [rsp+4D0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18002a061  lea     r8, [rsp+4D0h+cbSid]; cbSid
0x18002a066  mov     [rsp+4D0h+var_498], esi
0x18002a06a  xor     edx, edx; Sid
0x18002a06c  lea     rcx, [rbp+3D0h+AccountName]; lpAccountName
0x18002a073  call    cs:__imp_LookupAccountNameLocalW
0x18002a079  test    eax, eax
0x18002a07b  jnz     loc_18002A240
0x18002a081  mov     ecx, [rsp+4D0h+cbSid]; cb
0x18002a085  call    cs:__imp_CoTaskMemAlloc
0x18002a08b  mov     rbx, rax
0x18002a08e  test    rax, rax
0x18002a091  jz      loc_18002A29E
0x18002a097  lea     rax, [rsp+4D0h+Sid]
0x18002a09c  mov     [rsp+4D0h+var_498], esi
0x18002a0a0  mov     [rsp+4D0h+peUse], rax; peUse
0x18002a0a5  lea     r9, [rsp+4D0h+ReferencedDomainName]; ReferencedDomainName
0x18002a0aa  lea     rax, [rsp+4D0h+var_498]
0x18002a0af  mov     rdx, rbx; Sid
0x18002a0b2  lea     r8, [rsp+4D0h+cbSid]; cbSid
0x18002a0b7  mov     [rsp+4D0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18002a0bc  lea     rcx, [rbp+3D0h+AccountName]; lpAccountName
0x18002a0c3  call    cs:__imp_LookupAccountNameLocalW
0x18002a0c9  mov     rcx, rbx; pv
0x18002a0cc  mov     esi, eax
0x18002a0ce  call    cs:__imp_CoTaskMemFree
0x18002a0d4  test    edi, edi
0x18002a0d6  jz      short loc_18002A0FB
0x18002a0d8  test    esi, esi
0x18002a0da  jnz     loc_18002A240
0x18002a0e0  call    cs:__imp_GetLastError
0x18002a0e6  test    eax, eax
0x18002a0e8  jle     loc_18002A315
0x18002a0ee  movzx   eax, ax
0x18002a0f1  or      eax, 80070000h
0x18002a0f6  jmp     loc_18002A315
0x18002a0fb  test    esi, esi
0x18002a0fd  jz      short loc_18002A10B
0x18002a0ff  cmp     [rsp+4D0h+ReferencedDomainName], r15w
0x18002a105  jz      loc_18002A240
0x18002a10b  lea     r8, asc_180064E8C; "."
0x18002a112  mov     rdx, r12; unsigned __int64
0x18002a115  lea     rcx, [rsp+4D0h+ReferencedDomainName]; unsigned __int16 *
0x18002a11a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a11f  test    eax, eax
0x18002a121  js      loc_18002A315
0x18002a127  lea     rdx, asc_180064E8C; "."
0x18002a12e  lea     rcx, [rsp+4D0h+ReferencedDomainName]; String1
0x18002a133  call    cs:__imp__wcsicmp
0x18002a139  test    eax, eax
0x18002a13b  jnz     loc_18002A1CB
0x18002a141  lea     rcx, [rsp+4D0h+Sid]; unsigned __int16 **
0x18002a146  mov     [rsp+4D0h+Sid], r15
0x18002a14b  call    ?GetLocalizedBUILTIN@@YAJPEAPEAG@Z; GetLocalizedBUILTIN(ushort * *)
0x18002a150  test    eax, eax
0x18002a152  js      loc_18002A315
0x18002a158  mov     r8, [rsp+4D0h+Sid]; unsigned __int16 *
0x18002a15d  lea     rcx, [rsp+4D0h+ReferencedDomainName]; unsigned __int16 *
0x18002a162  mov     rdx, r12; unsigned __int64
0x18002a165  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a16a  test    eax, eax
0x18002a16c  js      loc_18002A315
0x18002a172  lea     rdx, [rbp+3D0h+AccountName]
0x18002a179  lea     rcx, [rsp+4D0h+ReferencedDomainName]
0x18002a17e  call    IsValidUserName
0x18002a183  test    eax, eax
0x18002a185  jnz     loc_18002A25A
0x18002a18b  test    edi, edi
0x18002a18d  jz      short loc_18002A1AA
0x18002a18f  mov     rcx, cs:qword_1800733E8
0x18002a196  lea     rdx, [rbp+3D0h+AccountName]
0x18002a19d  call    IsValidUserName
0x18002a1a2  test    eax, eax
0x18002a1a4  jz      loc_18002A0E0
0x18002a1aa  lea     r8, asc_180064E8C; "."
0x18002a1b1  mov     rdx, r12; unsigned __int64
0x18002a1b4  lea     rcx, [rsp+4D0h+ReferencedDomainName]; unsigned __int16 *
0x18002a1b9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a1be  test    eax, eax
0x18002a1c0  jns     loc_18002A25A
0x18002a1c6  jmp     loc_18002A315
0x18002a1cb  lea     rdx, [rbp+3D0h+AccountName]
0x18002a1d2  lea     rcx, [rsp+4D0h+ReferencedDomainName]
0x18002a1d7  call    IsValidUserName
0x18002a1dc  test    eax, eax
0x18002a1de  jnz     short loc_18002A240
0x18002a1e0  mov     rdx, cs:qword_1800733E8; String2
0x18002a1e7  lea     rcx, [rsp+4D0h+ReferencedDomainName]; String1
0x18002a1ec  call    cs:__imp__wcsicmp
0x18002a1f2  test    eax, eax
0x18002a1f4  jnz     loc_18002A2AE
0x18002a1fa  lea     rcx, [rsp+4D0h+Sid]; unsigned __int16 **
0x18002a1ff  mov     [rsp+4D0h+Sid], r15
0x18002a204  call    ?GetLocalizedBUILTIN@@YAJPEAPEAG@Z; GetLocalizedBUILTIN(ushort * *)
0x18002a209  test    eax, eax
0x18002a20b  js      loc_18002A315
0x18002a211  mov     rcx, [rsp+4D0h+Sid]
0x18002a216  lea     rdx, [rbp+3D0h+AccountName]
0x18002a21d  call    IsValidUserName
0x18002a222  test    eax, eax
0x18002a224  jz      short loc_18002A2A5
0x18002a226  mov     r8, [rsp+4D0h+Sid]; unsigned __int16 *
0x18002a22b  lea     rcx, [rsp+4D0h+ReferencedDomainName]; unsigned __int16 *
0x18002a230  mov     rdx, r12; unsigned __int64
0x18002a233  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a238  test    eax, eax
0x18002a23a  js      loc_18002A315
0x18002a240  mov     rdx, cs:qword_1800733E8; String2
0x18002a247  lea     rcx, [rsp+4D0h+ReferencedDomainName]; String1
0x18002a24c  call    cs:__imp__wcsicmp
0x18002a252  test    eax, eax
0x18002a254  jz      loc_18002A1AA
0x18002a25a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a25e  lea     rdx, [rsp+4D0h+ReferencedDomainName]
0x18002a263  mov     rcx, rax
0x18002a266  inc     rcx
0x18002a269  cmp     [rdx+rcx*2], r15w
0x18002a26e  jnz     short loc_18002A266
0x18002a270  lea     rdx, [rbp+3D0h+AccountName]
0x18002a277  inc     rax
0x18002a27a  cmp     [rdx+rax*2], r15w
0x18002a27f  jnz     short loc_18002A277
0x18002a281  add     rax, rcx
0x18002a284  lea     rax, ds:4[rax*2]
0x18002a28c  mov     ecx, eax; cb
0x18002a28e  mov     ebx, eax
0x18002a290  call    cs:__imp_CoTaskMemAlloc
0x18002a296  mov     [r14], rax
0x18002a299  test    rax, rax
0x18002a29c  jnz     short loc_18002A2B9
0x18002a29e  mov     eax, 8007000Eh
0x18002a2a3  jmp     short loc_18002A315
0x18002a2a5  test    edi, edi
0x18002a2a7  jz      short loc_18002A240
0x18002a2a9  jmp     loc_18002A0E0
0x18002a2ae  test    edi, edi
0x18002a2b0  jz      short loc_18002A240
0x18002a2b2  mov     eax, 80070534h
0x18002a2b7  jmp     short loc_18002A315
0x18002a2b9  mov     rdx, rbx; unsigned __int64
0x18002a2bc  cmp     [rsp+4D0h+ReferencedDomainName], r15w
0x18002a2c2  jz      short loc_18002A2E6
0x18002a2c4  lea     rcx, [rbp+3D0h+AccountName]
0x18002a2cb  mov     [rsp+4D0h+cchReferencedDomainName], rcx
0x18002a2d0  lea     r9, [rsp+4D0h+ReferencedDomainName]
0x18002a2d5  mov     rcx, rax; unsigned __int16 *
0x18002a2d8  lea     r8, aSS_3; "%s/%s"
0x18002a2df  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a2e4  jmp     short loc_18002A2F5
0x18002a2e6  lea     r8, [rbp+3D0h+AccountName]; unsigned __int16 *
0x18002a2ed  mov     rcx, rax; unsigned __int16 *
0x18002a2f0  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a2f5  mov     ebx, eax
0x18002a2f7  test    eax, eax
0x18002a2f9  jns     loc_180029F7E
0x18002a2ff  mov     rcx, [r14]; pv
0x18002a302  call    cs:__imp_CoTaskMemFree
0x18002a308  mov     [r14], r15
0x18002a30b  jmp     loc_180029F7E
0x18002a310  mov     eax, 80070057h
0x18002a315  mov     rcx, [rbp+3D0h+var_30]
0x18002a31c  xor     rcx, rsp; StackCookie
0x18002a31f  call    __security_check_cookie
0x18002a324  lea     r11, [rsp+4D0h+var_20]
0x18002a32c  mov     rbx, [r11+30h]
0x18002a330  mov     rsi, [r11+48h]
0x18002a334  mov     rsp, r11
0x18002a337  pop     r15
0x18002a339  pop     r14
0x18002a33b  pop     r12
0x18002a33d  pop     rdi
0x18002a33e  pop     rbp
0x18002a33f  retn
```
