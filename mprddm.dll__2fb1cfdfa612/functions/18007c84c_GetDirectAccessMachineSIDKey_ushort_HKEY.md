# GetDirectAccessMachineSIDKey(ushort *,HKEY__ * *)

- ea: `0x18007c84c`
- end: `0x18007cb33`
- name: `?GetDirectAccessMachineSIDKey@@YAKPEAGPEAPEAUHKEY__@@@Z`
- size: `743`
- prototype: `unsigned int(unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007cb3c`

## callees

- `0x180001338`
- `0x1800028a8`
- `0x180025e2c`
- `0x18007c84c`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18007cace`
- `msvcrt!??3@YAXPEAX@Z` at `0x18007cadc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18007cace`
- `msvcrt!??3@YAXPEAX@Z` at `0x18007cadc`
- `msvcrt!malloc` at `0x18007ca0f`
- `msvcrt!malloc` at `0x18007ca0f`
- `msvcrt!free` at `0x18007caea`
- `msvcrt!free` at `0x18007caea`
- `KERNEL32!LocalFree` at `0x18007cafa`
- `KERNEL32!LocalFree` at `0x18007cafa`
- `KERNEL32!GetComputerNameW` at `0x18007c8c5`
- `KERNEL32!GetComputerNameW` at `0x18007c8c5`
- `KERNEL32!GetLastError` at `0x18007c8cf`
- `KERNEL32!GetLastError` at `0x18007c942`
- `KERNEL32!GetLastError` at `0x18007c9ca`
- `KERNEL32!GetLastError` at `0x18007c8cf`
- `KERNEL32!GetLastError` at `0x18007c942`
- `KERNEL32!GetLastError` at `0x18007c9ca`
- `ADVAPI32!RegOpenKeyExW` at `0x18007cab6`
- `ADVAPI32!RegOpenKeyExW` at `0x18007cab6`
- `ADVAPI32!RegCloseKey` at `0x18007cac5`
- `ADVAPI32!RegCloseKey` at `0x18007cac5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18007c93c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18007c9c0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18007c93c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18007c9c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007c9df`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007c9df`

## string_xrefs

- `0x18007ca3e`: `Software\Policies\Microsoft\Windows\RemoteAccess\Config\MachineSIDs`

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
  __int64 v13; // rcx
  const wchar_t *v14; // r8
  unsigned __int64 v15; // rdx
  unsigned __int16 *v16; // rcx
  DWORD nSize; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbSid; // [rsp+48h] [rbp-B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+4Ch] [rbp-B4h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer; // [rsp+60h] [rbp-A0h] BYREF
  char v24[526]; // [rsp+62h] [rbp-9Eh] BYREF

  cbSid = 0;
  cchReferencedDomainName = 0;
  Buffer = 0;
  memset_0(v24, 0, 0x200u);
  peUse = 0;
  StringSid = 0;
  *a2 = 0;
  nSize = 257;
  if ( GetComputerNameW(&Buffer, &nSize) )
  {
    v4 = nSize;
    if ( nSize > 0xFF )
      goto LABEL_4;
    *(_WORD *)&v24[2 * nSize - 2] = 36;
    v5 = 2LL * (v4 + 1);
    if ( v5 >= 0x202 )
      _report_rangecheckfailure();
    *(_WORD *)&v24[v5 - 2] = 0;
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
                if ( v11 )
                {
                  if ( v11 <= 0x7FFFFFFF )
                  {
                    v13 = 2147483646;
                    v14 = L"Software\\Policies\\Microsoft\\Windows\\RemoteAccess\\Config\\MachineSIDs";
                    v15 = v11;
                    do
                    {
                      if ( !v13 )
                        break;
                      if ( !*v14 )
                        break;
                      *v12++ = *v14++;
                      --v13;
                      --v15;
                    }
                    while ( v15 );
                    v16 = v12 - 1;
                    if ( v15 )
                      v16 = v12;
                    *v16 = 0;
                  }
                  else
                  {
                    *v12 = 0;
                  }
                }
                StringCchCatW(v8, v11, L"\\");
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
0x18007c84c  mov     [rsp-8+arg_0], rbx
0x18007c851  mov     [rsp-8+arg_10], rsi
0x18007c856  push    rbp
0x18007c857  push    rdi
0x18007c858  push    r12
0x18007c85a  push    r14
0x18007c85c  push    r15
0x18007c85e  lea     rbp, [rsp-180h]
0x18007c866  sub     rsp, 280h
0x18007c86d  mov     rax, cs:__security_cookie
0x18007c874  xor     rax, rsp
0x18007c877  mov     [rbp+1A0h+var_30], rax
0x18007c87e  xor     r12d, r12d
0x18007c881  lea     rcx, [rsp+2A0h+var_23E]; void *
0x18007c886  mov     r15, rdx
0x18007c889  mov     [rsp+2A0h+cbSid], r12d
0x18007c88e  xor     edx, edx; Val
0x18007c890  mov     [rsp+2A0h+var_25C], r12d
0x18007c895  mov     r8d, 200h; Size
0x18007c89b  mov     [rsp+2A0h+Buffer], r12w
0x18007c8a1  call    memset_0
0x18007c8a6  lea     rdx, [rsp+2A0h+nSize]; nSize
0x18007c8ab  mov     [rsp+2A0h+var_254], r12d
0x18007c8b0  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x18007c8b5  mov     [rsp+2A0h+StringSid], r12
0x18007c8ba  mov     [r15], r12
0x18007c8bd  mov     [rsp+2A0h+nSize], 101h
0x18007c8c5  call    cs:__imp_GetComputerNameW
0x18007c8cb  test    eax, eax
0x18007c8cd  jnz     short loc_18007C8DC
0x18007c8cf  call    cs:__imp_GetLastError
0x18007c8d5  mov     ebx, eax
0x18007c8d7  jmp     loc_18007CAF0
0x18007c8dc  mov     ecx, [rsp+2A0h+nSize]
0x18007c8e0  cmp     ecx, 0FFh
0x18007c8e6  jbe     short loc_18007C8F2
0x18007c8e8  mov     ebx, 3EBh
0x18007c8ed  jmp     loc_18007CAF0
0x18007c8f2  mov     edx, 24h ; '$'
0x18007c8f7  mov     [rsp+rcx*2+2A0h+Buffer], dx
0x18007c8fc  inc     ecx
0x18007c8fe  add     rcx, rcx
0x18007c901  cmp     rcx, 202h
0x18007c908  jnb     loc_18007CB2D
0x18007c90e  lea     rax, [rsp+2A0h+var_254]
0x18007c913  mov     [rsp+rcx+2A0h+Buffer], r12w
0x18007c919  mov     [rsp+2A0h+peUse], rax; peUse
0x18007c91e  lea     r9, [rsp+2A0h+cbSid]; cbSid
0x18007c923  lea     rax, [rsp+2A0h+var_25C]
0x18007c928  xor     r8d, r8d; Sid
0x18007c92b  mov     [rsp+2A0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18007c930  lea     rdx, [rsp+2A0h+Buffer]; lpAccountName
0x18007c935  xor     ecx, ecx; lpSystemName
0x18007c937  mov     [rsp+2A0h+ReferencedDomainName], r12; ReferencedDomainName
0x18007c93c  call    cs:__imp_LookupAccountNameW
0x18007c942  call    cs:__imp_GetLastError
0x18007c948  cmp     eax, 7Ah ; 'z'
0x18007c94b  jnz     short loc_18007C8E8
0x18007c94d  mov     ecx, [rsp+2A0h+cbSid]; Size
0x18007c951  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007c956  mov     rsi, rax
0x18007c959  test    rax, rax
0x18007c95c  jnz     short loc_18007C966
0x18007c95e  lea     ebx, [rax+0Eh]
0x18007c961  jmp     loc_18007CAF0
0x18007c966  mov     ecx, [rsp+2A0h+var_25C]
0x18007c96a  mov     eax, 2
0x18007c96f  mul     rcx
0x18007c972  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18007c979  mov     rdi, r12
0x18007c97c  cmovb   rax, rbx
0x18007c980  mov     rcx, rax; Size
0x18007c983  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007c988  mov     r14, rax
0x18007c98b  test    rax, rax
0x18007c98e  jnz     short loc_18007C998
0x18007c990  lea     ebx, [rax+0Eh]
0x18007c993  jmp     loc_18007CACB
0x18007c998  lea     rax, [rsp+2A0h+var_254]
0x18007c99d  mov     r8, rsi; Sid
0x18007c9a0  mov     [rsp+2A0h+peUse], rax; peUse
0x18007c9a5  lea     r9, [rsp+2A0h+cbSid]; cbSid
0x18007c9aa  lea     rax, [rsp+2A0h+var_25C]
0x18007c9af  xor     ecx, ecx; lpSystemName
0x18007c9b1  mov     [rsp+2A0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18007c9b6  lea     rdx, [rsp+2A0h+Buffer]; lpAccountName
0x18007c9bb  mov     [rsp+2A0h+ReferencedDomainName], r14; ReferencedDomainName
0x18007c9c0  call    cs:__imp_LookupAccountNameW
0x18007c9c6  test    eax, eax
0x18007c9c8  jnz     short loc_18007C9D7
0x18007c9ca  call    cs:__imp_GetLastError
0x18007c9d0  mov     ebx, eax
0x18007c9d2  jmp     loc_18007CACB
0x18007c9d7  lea     rdx, [rsp+2A0h+StringSid]; StringSid
0x18007c9dc  mov     rcx, rsi; Sid
0x18007c9df  call    cs:__imp_ConvertSidToStringSidW
0x18007c9e5  test    eax, eax
0x18007c9e7  jnz     short loc_18007C9F3
0x18007c9e9  mov     ebx, 3EBh
0x18007c9ee  jmp     loc_18007CACB
0x18007c9f3  mov     rax, [rsp+2A0h+StringSid]
0x18007c9f8  inc     rbx
0x18007c9fb  cmp     [rax+rbx*2], r12w
0x18007ca00  jnz     short loc_18007C9F8
0x18007ca02  lea     eax, [rbx+45h]
0x18007ca05  lea     rcx, [rax+rax]; Size
0x18007ca09  mov     [rsp+2A0h+nSize], eax
0x18007ca0d  mov     ebx, eax
0x18007ca0f  call    cs:__imp_malloc
0x18007ca15  mov     rdi, rax
0x18007ca18  test    rax, rax
0x18007ca1b  jnz     short loc_18007CA25
0x18007ca1d  lea     ebx, [rax+0Eh]
0x18007ca20  jmp     loc_18007CABE
0x18007ca25  test    rbx, rbx
0x18007ca28  jz      short loc_18007CA7B
0x18007ca2a  cmp     rbx, 7FFFFFFFh
0x18007ca31  jbe     short loc_18007CA39
0x18007ca33  mov     [rax], r12w
0x18007ca37  jmp     short loc_18007CA7B
0x18007ca39  mov     ecx, 7FFFFFFEh
0x18007ca3e  lea     r8, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18007ca45  mov     rdx, rbx
0x18007ca48  test    rcx, rcx
0x18007ca4b  jz      short loc_18007CA6C
0x18007ca4d  movzx   r9d, word ptr [r8]
0x18007ca51  test    r9w, r9w
0x18007ca55  jz      short loc_18007CA6C
0x18007ca57  mov     [rax], r9w
0x18007ca5b  add     r8, 2
0x18007ca5f  add     rax, 2
0x18007ca63  dec     rcx
0x18007ca66  sub     rdx, 1
0x18007ca6a  jnz     short loc_18007CA48
0x18007ca6c  test    rdx, rdx
0x18007ca6f  lea     rcx, [rax-2]
0x18007ca73  cmovnz  rcx, rax
0x18007ca77  mov     [rcx], r12w
0x18007ca7b  lea     r8, asc_180091AD8; "\\"
0x18007ca82  mov     rdx, rbx; unsigned __int64
0x18007ca85  mov     rcx, rdi; unsigned __int16 *
0x18007ca88  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007ca8d  mov     edx, [rsp+2A0h+nSize]; unsigned __int64
0x18007ca91  mov     rcx, rdi; unsigned __int16 *
0x18007ca94  mov     r8, [rsp+2A0h+StringSid]; unsigned __int16 *
0x18007ca99  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007ca9e  mov     r9d, 20019h; samDesired
0x18007caa4  mov     [rsp+2A0h+ReferencedDomainName], r15; phkResult
0x18007caa9  xor     r8d, r8d; ulOptions
0x18007caac  mov     rdx, rdi; lpSubKey
0x18007caaf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007cab6  call    cs:__imp_RegOpenKeyExW
0x18007cabc  mov     ebx, eax
0x18007cabe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007cac5  call    cs:__imp_RegCloseKey
0x18007cacb  mov     rcx, rsi
0x18007cace  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18007cad4  test    r14, r14
0x18007cad7  jz      short loc_18007CAE2
0x18007cad9  mov     rcx, r14
0x18007cadc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18007cae2  test    rdi, rdi
0x18007cae5  jz      short loc_18007CAF0
0x18007cae7  mov     rcx, rdi; Block
0x18007caea  call    cs:__imp_free
0x18007caf0  mov     rcx, [rsp+2A0h+StringSid]; hMem
0x18007caf5  test    rcx, rcx
0x18007caf8  jz      short loc_18007CB00
0x18007cafa  call    cs:__imp_LocalFree
0x18007cb00  mov     eax, ebx
0x18007cb02  mov     rcx, [rbp+1A0h+var_30]
0x18007cb09  xor     rcx, rsp; StackCookie
0x18007cb0c  call    __security_check_cookie
0x18007cb11  lea     r11, [rsp+2A0h+var_20]
0x18007cb19  mov     rbx, [r11+30h]
0x18007cb1d  mov     rsi, [r11+40h]
0x18007cb21  mov     rsp, r11
0x18007cb24  pop     r15
0x18007cb26  pop     r14
0x18007cb28  pop     r12
0x18007cb2a  pop     rdi
0x18007cb2b  pop     rbp
0x18007cb2c  retn
0x18007cb2d  call    __report_rangecheckfailure
```
