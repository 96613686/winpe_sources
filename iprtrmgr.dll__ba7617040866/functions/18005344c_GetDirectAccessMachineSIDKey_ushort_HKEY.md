# GetDirectAccessMachineSIDKey(ushort *,HKEY__ * *)

- ea: `0x18005344c`
- end: `0x1800536ed`
- name: `?GetDirectAccessMachineSIDKey@@YAKPEAGPEAPEAUHKEY__@@@Z`
- size: `673`
- prototype: `unsigned int(unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005381c`

## callees

- `0x1800036b8`
- `0x180003b00`
- `0x18005344c`
- `0x1800536f4`
- `0x180053780`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `msvcrt!free` at `0x1800536a4`
- `msvcrt!free` at `0x1800536a4`
- `msvcrt!malloc` at `0x18005360f`
- `msvcrt!malloc` at `0x18005360f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180053688`
- `msvcrt!??3@YAXPEAX@Z` at `0x180053696`
- `msvcrt!??3@YAXPEAX@Z` at `0x180053688`
- `msvcrt!??3@YAXPEAX@Z` at `0x180053696`
- `KERNEL32!LocalFree` at `0x1800536b4`
- `KERNEL32!LocalFree` at `0x1800536b4`
- `KERNEL32!GetLastError` at `0x1800534cf`
- `KERNEL32!GetLastError` at `0x180053542`
- `KERNEL32!GetLastError` at `0x1800535ca`
- `KERNEL32!GetLastError` at `0x1800534cf`
- `KERNEL32!GetLastError` at `0x180053542`
- `KERNEL32!GetLastError` at `0x1800535ca`
- `KERNEL32!GetComputerNameW` at `0x1800534c5`
- `KERNEL32!GetComputerNameW` at `0x1800534c5`
- `ADVAPI32!LookupAccountNameW` at `0x18005353c`
- `ADVAPI32!LookupAccountNameW` at `0x1800535c0`
- `ADVAPI32!LookupAccountNameW` at `0x18005353c`
- `ADVAPI32!LookupAccountNameW` at `0x1800535c0`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800535df`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800535df`
- `ADVAPI32!RegCloseKey` at `0x18005367f`
- `ADVAPI32!RegCloseKey` at `0x18005367f`
- `ADVAPI32!RegOpenKeyExW` at `0x180053670`
- `ADVAPI32!RegOpenKeyExW` at `0x180053670`

## string_xrefs

- `0x180053622`: `Software\Policies\Microsoft\Windows\RemoteAccess\Config\MachineSIDs`

## pseudocode

```c
__int64 __fastcall GetDirectAccessMachineSIDKey(unsigned __int16 *a1, HKEY *a2)
{
  DWORD LastError; // ebx
  DWORD v4; // ecx
  unsigned __int64 v5; // rcx
  void *v6; // rsi
  __int64 v7; // rbx
  unsigned __int16 *v8; // rdi
  WCHAR *ReferencedDomainName; // r14
  size_t v10; // rcx
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rax
  DWORD nSize; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbSid; // [rsp+48h] [rbp-B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+4Ch] [rbp-B4h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[526]; // [rsp+62h] [rbp-9Eh] BYREF

  cbSid = 0;
  cchReferencedDomainName = 0;
  Buffer = 0;
  memset_0(v20, 0, 0x200u);
  peUse = 0;
  StringSid = 0;
  *a2 = 0;
  nSize = 257;
  if ( GetComputerNameW(&Buffer, &nSize) )
  {
    v4 = nSize;
    if ( nSize > 0xFF )
      goto LABEL_4;
    *(_WORD *)&v20[2 * nSize - 2] = 36;
    v5 = 2LL * (v4 + 1);
    if ( v5 >= 0x202 )
      _report_rangecheckfailure();
    *(_WORD *)&v20[v5 - 2] = 0;
    LookupAccountNameW(0, &Buffer, 0, &cbSid, 0, &cchReferencedDomainName, &peUse);
    if ( GetLastError() == 122 )
    {
      v6 = operator new(cbSid);
      if ( v6 )
      {
        v7 = -1;
        v8 = 0;
        ReferencedDomainName = (WCHAR *)operator new(saturated_mul(cchReferencedDomainName, 2u));
        if ( ReferencedDomainName )
        {
          if ( LookupAccountNameW(0, &Buffer, v6, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
          {
            if ( ConvertSidToStringSidW(v6, &StringSid) )
            {
              do
                ++v7;
              while ( StringSid[v7] );
              v10 = 2LL * (unsigned int)(v7 + 69);
              nSize = v7 + 69;
              v11 = (unsigned int)(v7 + 69);
              v12 = (unsigned __int16 *)malloc(v10);
              v8 = v12;
              if ( v12 )
              {
                StringCchCopyW(v12, v11, L"Software\\Policies\\Microsoft\\Windows\\RemoteAccess\\Config\\MachineSIDs");
                StringCchCatW(v8, nSize, L"\\");
                StringCchCatW(v8, nSize, StringSid);
                LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x20019u, a2);
              }
              else
              {
                LastError = 14;
              }
              RegCloseKey(HKEY_LOCAL_MACHINE);
            }
            else
            {
              LastError = 1003;
            }
          }
          else
          {
            LastError = GetLastError();
          }
        }
        else
        {
          LastError = 14;
        }
        operator delete(v6);
        if ( ReferencedDomainName )
          operator delete(ReferencedDomainName);
        if ( v8 )
          free(v8);
      }
      else
      {
        LastError = 14;
      }
    }
    else
    {
LABEL_4:
      LastError = 1003;
    }
  }
  else
  {
    LastError = GetLastError();
  }
  if ( StringSid )
    LocalFree(StringSid);
  return LastError;
}

```

## disassembly

```asm
0x18005344c  mov     [rsp-8+arg_0], rbx
0x180053451  mov     [rsp-8+arg_10], rsi
0x180053456  push    rbp
0x180053457  push    rdi
0x180053458  push    r12
0x18005345a  push    r14
0x18005345c  push    r15
0x18005345e  lea     rbp, [rsp-180h]
0x180053466  sub     rsp, 280h
0x18005346d  mov     rax, cs:__security_cookie
0x180053474  xor     rax, rsp
0x180053477  mov     [rbp+1A0h+var_30], rax
0x18005347e  xor     r12d, r12d
0x180053481  lea     rcx, [rsp+2A0h+var_23E]; void *
0x180053486  mov     r15, rdx
0x180053489  mov     [rsp+2A0h+cbSid], r12d
0x18005348e  xor     edx, edx; Val
0x180053490  mov     [rsp+2A0h+var_25C], r12d
0x180053495  mov     r8d, 200h; Size
0x18005349b  mov     [rsp+2A0h+Buffer], r12w
0x1800534a1  call    memset_0
0x1800534a6  lea     rdx, [rsp+2A0h+nSize]; nSize
0x1800534ab  mov     [rsp+2A0h+var_254], r12d
0x1800534b0  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x1800534b5  mov     [rsp+2A0h+StringSid], r12
0x1800534ba  mov     [r15], r12
0x1800534bd  mov     [rsp+2A0h+nSize], 101h
0x1800534c5  call    cs:__imp_GetComputerNameW
0x1800534cb  test    eax, eax
0x1800534cd  jnz     short loc_1800534DC
0x1800534cf  call    cs:__imp_GetLastError
0x1800534d5  mov     ebx, eax
0x1800534d7  jmp     loc_1800536AA
0x1800534dc  mov     ecx, [rsp+2A0h+nSize]
0x1800534e0  cmp     ecx, 0FFh
0x1800534e6  jbe     short loc_1800534F2
0x1800534e8  mov     ebx, 3EBh
0x1800534ed  jmp     loc_1800536AA
0x1800534f2  mov     edx, 24h ; '$'
0x1800534f7  mov     [rsp+rcx*2+2A0h+Buffer], dx
0x1800534fc  inc     ecx
0x1800534fe  add     rcx, rcx
0x180053501  cmp     rcx, 202h
0x180053508  jnb     loc_1800536E7
0x18005350e  lea     rax, [rsp+2A0h+var_254]
0x180053513  mov     [rsp+rcx+2A0h+Buffer], r12w
0x180053519  mov     [rsp+2A0h+peUse], rax; peUse
0x18005351e  lea     r9, [rsp+2A0h+cbSid]; cbSid
0x180053523  lea     rax, [rsp+2A0h+var_25C]
0x180053528  xor     r8d, r8d; Sid
0x18005352b  mov     [rsp+2A0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180053530  lea     rdx, [rsp+2A0h+Buffer]; lpAccountName
0x180053535  xor     ecx, ecx; lpSystemName
0x180053537  mov     [rsp+2A0h+ReferencedDomainName], r12; ReferencedDomainName
0x18005353c  call    cs:__imp_LookupAccountNameW
0x180053542  call    cs:__imp_GetLastError
0x180053548  cmp     eax, 7Ah ; 'z'
0x18005354b  jnz     short loc_1800534E8
0x18005354d  mov     ecx, [rsp+2A0h+cbSid]; Size
0x180053551  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180053556  mov     rsi, rax
0x180053559  test    rax, rax
0x18005355c  jnz     short loc_180053566
0x18005355e  lea     ebx, [rax+0Eh]
0x180053561  jmp     loc_1800536AA
0x180053566  mov     ecx, [rsp+2A0h+var_25C]
0x18005356a  mov     eax, 2
0x18005356f  mul     rcx
0x180053572  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180053579  mov     rdi, r12
0x18005357c  cmovb   rax, rbx
0x180053580  mov     rcx, rax; Size
0x180053583  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180053588  mov     r14, rax
0x18005358b  test    rax, rax
0x18005358e  jnz     short loc_180053598
0x180053590  lea     ebx, [rax+0Eh]
0x180053593  jmp     loc_180053685
0x180053598  lea     rax, [rsp+2A0h+var_254]
0x18005359d  mov     r8, rsi; Sid
0x1800535a0  mov     [rsp+2A0h+peUse], rax; peUse
0x1800535a5  lea     r9, [rsp+2A0h+cbSid]; cbSid
0x1800535aa  lea     rax, [rsp+2A0h+var_25C]
0x1800535af  xor     ecx, ecx; lpSystemName
0x1800535b1  mov     [rsp+2A0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800535b6  lea     rdx, [rsp+2A0h+Buffer]; lpAccountName
0x1800535bb  mov     [rsp+2A0h+ReferencedDomainName], r14; ReferencedDomainName
0x1800535c0  call    cs:__imp_LookupAccountNameW
0x1800535c6  test    eax, eax
0x1800535c8  jnz     short loc_1800535D7
0x1800535ca  call    cs:__imp_GetLastError
0x1800535d0  mov     ebx, eax
0x1800535d2  jmp     loc_180053685
0x1800535d7  lea     rdx, [rsp+2A0h+StringSid]; StringSid
0x1800535dc  mov     rcx, rsi; Sid
0x1800535df  call    cs:__imp_ConvertSidToStringSidW
0x1800535e5  test    eax, eax
0x1800535e7  jnz     short loc_1800535F3
0x1800535e9  mov     ebx, 3EBh
0x1800535ee  jmp     loc_180053685
0x1800535f3  mov     rax, [rsp+2A0h+StringSid]
0x1800535f8  inc     rbx
0x1800535fb  cmp     [rax+rbx*2], r12w
0x180053600  jnz     short loc_1800535F8
0x180053602  lea     eax, [rbx+45h]
0x180053605  lea     rcx, [rax+rax]; Size
0x180053609  mov     [rsp+2A0h+nSize], eax
0x18005360d  mov     ebx, eax
0x18005360f  call    cs:__imp_malloc
0x180053615  mov     rdi, rax
0x180053618  test    rax, rax
0x18005361b  jnz     short loc_180053622
0x18005361d  lea     ebx, [rax+0Eh]
0x180053620  jmp     short loc_180053678
0x180053622  lea     r8, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180053629  mov     rdx, rbx; unsigned __int64
0x18005362c  mov     rcx, rdi; unsigned __int16 *
0x18005362f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180053634  mov     edx, [rsp+2A0h+nSize]; unsigned __int64
0x180053638  lea     r8, asc_18005B0E0; "\\"
0x18005363f  mov     rcx, rdi; unsigned __int16 *
0x180053642  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180053647  mov     edx, [rsp+2A0h+nSize]; unsigned __int64
0x18005364b  mov     rcx, rdi; unsigned __int16 *
0x18005364e  mov     r8, [rsp+2A0h+StringSid]; unsigned __int16 *
0x180053653  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180053658  mov     r9d, 20019h; samDesired
0x18005365e  mov     [rsp+2A0h+ReferencedDomainName], r15; phkResult
0x180053663  xor     r8d, r8d; ulOptions
0x180053666  mov     rdx, rdi; lpSubKey
0x180053669  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180053670  call    cs:__imp_RegOpenKeyExW
0x180053676  mov     ebx, eax
0x180053678  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005367f  call    cs:__imp_RegCloseKey
0x180053685  mov     rcx, rsi
0x180053688  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18005368e  test    r14, r14
0x180053691  jz      short loc_18005369C
0x180053693  mov     rcx, r14
0x180053696  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18005369c  test    rdi, rdi
0x18005369f  jz      short loc_1800536AA
0x1800536a1  mov     rcx, rdi; Block
0x1800536a4  call    cs:__imp_free
0x1800536aa  mov     rcx, [rsp+2A0h+StringSid]; hMem
0x1800536af  test    rcx, rcx
0x1800536b2  jz      short loc_1800536BA
0x1800536b4  call    cs:__imp_LocalFree
0x1800536ba  mov     eax, ebx
0x1800536bc  mov     rcx, [rbp+1A0h+var_30]
0x1800536c3  xor     rcx, rsp; StackCookie
0x1800536c6  call    __security_check_cookie
0x1800536cb  lea     r11, [rsp+2A0h+var_20]
0x1800536d3  mov     rbx, [r11+30h]
0x1800536d7  mov     rsi, [r11+40h]
0x1800536db  mov     rsp, r11
0x1800536de  pop     r15
0x1800536e0  pop     r14
0x1800536e2  pop     r12
0x1800536e4  pop     rdi
0x1800536e5  pop     rbp
0x1800536e6  retn
0x1800536e7  call    __report_rangecheckfailure
```
