# GetDirectAccessMachineSIDKey(ushort *,HKEY__ * *)

- ea: `0x180081844`
- end: `0x180081b81`
- name: `?GetDirectAccessMachineSIDKey@@YAKPEAGPEAPEAUHKEY__@@@Z`
- size: `829`
- prototype: `unsigned int(unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180081b88`

## callees

- `0x180001328`
- `0x1800028f4`
- `0x180028058`
- `0x180081844`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180081b03`
- `msvcrt!??3@YAXPEAX@Z` at `0x180081b17`
- `msvcrt!??3@YAXPEAX@Z` at `0x180081b03`
- `msvcrt!??3@YAXPEAX@Z` at `0x180081b17`
- `msvcrt!malloc` at `0x180081a32`
- `msvcrt!malloc` at `0x180081a32`
- `msvcrt!free` at `0x180081b2b`
- `msvcrt!free` at `0x180081b2b`
- `KERNEL32!LocalFree` at `0x180081b41`
- `KERNEL32!LocalFree` at `0x180081b41`
- `KERNEL32!GetComputerNameW` at `0x1800818c0`
- `KERNEL32!GetComputerNameW` at `0x1800818c0`
- `KERNEL32!GetLastError` at `0x1800818d0`
- `KERNEL32!GetLastError` at `0x180081945`
- `KERNEL32!GetLastError` at `0x1800819e0`
- `KERNEL32!GetLastError` at `0x1800818d0`
- `KERNEL32!GetLastError` at `0x180081945`
- `KERNEL32!GetLastError` at `0x1800819e0`
- `ADVAPI32!RegOpenKeyExW` at `0x180081adf`
- `ADVAPI32!RegOpenKeyExW` at `0x180081adf`
- `ADVAPI32!RegCloseKey` at `0x180081af4`
- `ADVAPI32!RegCloseKey` at `0x180081af4`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180081939`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800819d0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180081939`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800819d0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800819fb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800819fb`

## string_xrefs

- `0x180081a62`: `Software\Policies\Microsoft\Windows\RemoteAccess\Config\MachineSIDs`

## pseudocode

```c
__int64 __fastcall GetDirectAccessMachineSIDKey(unsigned __int16 *a1, HKEY *a2)
{
  unsigned __int16 *v3; // rdi
  DWORD LastError; // ebx
  DWORD v5; // ecx
  unsigned __int64 v6; // rcx
  void *v7; // rsi
  __int64 v8; // rbx
  WCHAR *ReferencedDomainName; // r14
  size_t v10; // rcx
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rax
  unsigned __int64 v13; // rdx
  char *v14; // r9
  unsigned __int16 *v15; // rcx
  unsigned __int16 v16; // ax
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
  v3 = 0;
  *a2 = 0;
  nSize = 257;
  if ( GetComputerNameW(&Buffer, &nSize) )
  {
    v5 = nSize;
    if ( nSize > 0xFF )
      goto LABEL_6;
    *(_WORD *)&v24[2 * nSize - 2] = 36;
    v6 = 2LL * (v5 + 1);
    if ( v6 >= 0x202 )
      _report_rangecheckfailure();
    *(_WORD *)&v24[v6 - 2] = 0;
    LookupAccountNameW(0, &Buffer, 0, &cbSid, 0, &cchReferencedDomainName, &peUse);
    if ( GetLastError() == 122 )
    {
      v7 = operator new(cbSid);
      if ( v7 )
      {
        v8 = -1;
        ReferencedDomainName = (WCHAR *)operator new(saturated_mul(cchReferencedDomainName, 2u));
        if ( ReferencedDomainName )
        {
          if ( LookupAccountNameW(0, &Buffer, v7, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
          {
            if ( ConvertSidToStringSidW(v7, &StringSid) )
            {
              do
                ++v8;
              while ( StringSid[v8] );
              v10 = 2LL * (unsigned int)(v8 + 69);
              nSize = v8 + 69;
              v11 = (unsigned int)(v8 + 69);
              v12 = (unsigned __int16 *)malloc(v10);
              v3 = v12;
              if ( v12 )
              {
                if ( v11 )
                {
                  if ( v11 <= 0x7FFFFFFF )
                  {
                    v13 = v11;
                    v14 = (char *)((char *)L"Software\\Policies\\Microsoft\\Windows\\RemoteAccess\\Config\\MachineSIDs"
                                 - (char *)v12);
                    v15 = v12;
                    do
                    {
                      if ( !(2147483646 - v11 + v13) )
                        break;
                      v16 = *(unsigned __int16 *)((char *)v15 + (_QWORD)v14);
                      if ( !v16 )
                        break;
                      *v15++ = v16;
                      --v13;
                    }
                    while ( v13 );
                    v12 = v15 - 1;
                    if ( v13 )
                      v12 = v15;
                  }
                  *v12 = 0;
                }
                StringCchCatW(v3, v11, L"\\");
                StringCchCatW(v3, nSize, StringSid);
                LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, a2);
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
        operator delete(v7);
        if ( ReferencedDomainName )
          operator delete(ReferencedDomainName);
        if ( v3 )
          free(v3);
      }
      else
      {
        LastError = 14;
      }
    }
    else
    {
LABEL_6:
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
0x180081844  mov     [rsp-8+arg_0], rbx
0x180081849  mov     [rsp-8+arg_10], rsi
0x18008184e  push    rbp
0x18008184f  push    rdi
0x180081850  push    r12
0x180081852  push    r14
0x180081854  push    r15
0x180081856  lea     rbp, [rsp-180h]
0x18008185e  sub     rsp, 280h
0x180081865  mov     rax, cs:__security_cookie
0x18008186c  xor     rax, rsp
0x18008186f  mov     [rbp+1A0h+var_30], rax
0x180081876  xor     r12d, r12d
0x180081879  lea     rcx, [rsp+2A0h+var_23E]; void *
0x18008187e  mov     r15, rdx
0x180081881  mov     [rsp+2A0h+cbSid], r12d
0x180081886  xor     edx, edx; Val
0x180081888  mov     [rsp+2A0h+var_25C], r12d
0x18008188d  mov     r8d, 200h; Size
0x180081893  mov     [rsp+2A0h+Buffer], r12w
0x180081899  call    memset_0
0x18008189e  lea     rdx, [rsp+2A0h+nSize]; nSize
0x1800818a3  mov     [rsp+2A0h+var_254], r12d
0x1800818a8  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x1800818ad  mov     [rsp+2A0h+StringSid], r12
0x1800818b2  mov     edi, r12d
0x1800818b5  mov     [r15], r12
0x1800818b8  mov     [rsp+2A0h+nSize], 101h
0x1800818c0  call    cs:__imp_GetComputerNameW
0x1800818c7  nop     dword ptr [rax+rax+00h]
0x1800818cc  test    eax, eax
0x1800818ce  jnz     short loc_1800818E3
0x1800818d0  call    cs:__imp_GetLastError
0x1800818d7  nop     dword ptr [rax+rax+00h]
0x1800818dc  mov     ebx, eax
0x1800818de  jmp     loc_180081B37
0x1800818e3  mov     ecx, [rsp+2A0h+nSize]
0x1800818e7  cmp     ecx, 0FFh
0x1800818ed  ja      short loc_180081956
0x1800818ef  mov     edx, 24h ; '$'
0x1800818f4  mov     [rsp+rcx*2+2A0h+Buffer], dx
0x1800818f9  inc     ecx
0x1800818fb  add     rcx, rcx
0x1800818fe  cmp     rcx, 202h
0x180081905  jnb     loc_180081B7B
0x18008190b  lea     rax, [rsp+2A0h+var_254]
0x180081910  mov     [rsp+rcx+2A0h+Buffer], r12w
0x180081916  mov     [rsp+2A0h+peUse], rax; peUse
0x18008191b  lea     r9, [rsp+2A0h+cbSid]; cbSid
0x180081920  lea     rax, [rsp+2A0h+var_25C]
0x180081925  xor     r8d, r8d; Sid
0x180081928  mov     [rsp+2A0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18008192d  lea     rdx, [rsp+2A0h+Buffer]; lpAccountName
0x180081932  xor     ecx, ecx; lpSystemName
0x180081934  mov     [rsp+2A0h+ReferencedDomainName], r12; ReferencedDomainName
0x180081939  call    cs:__imp_LookupAccountNameW
0x180081940  nop     dword ptr [rax+rax+00h]
0x180081945  call    cs:__imp_GetLastError
0x18008194c  nop     dword ptr [rax+rax+00h]
0x180081951  cmp     eax, 7Ah ; 'z'
0x180081954  jz      short loc_180081960
0x180081956  mov     ebx, 3EBh
0x18008195b  jmp     loc_180081B37
0x180081960  mov     ecx, [rsp+2A0h+cbSid]; Size
0x180081964  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180081969  mov     rsi, rax
0x18008196c  test    rax, rax
0x18008196f  jnz     short loc_180081979
0x180081971  lea     ebx, [rax+0Eh]
0x180081974  jmp     loc_180081B37
0x180081979  mov     ecx, [rsp+2A0h+var_25C]
0x18008197d  mov     eax, 2
0x180081982  mul     rcx
0x180081985  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18008198c  cmovo   rax, rbx
0x180081990  mov     rcx, rax; Size
0x180081993  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180081998  mov     r14, rax
0x18008199b  test    rax, rax
0x18008199e  jnz     short loc_1800819A8
0x1800819a0  lea     ebx, [rax+0Eh]
0x1800819a3  jmp     loc_180081B00
0x1800819a8  lea     rax, [rsp+2A0h+var_254]
0x1800819ad  mov     r8, rsi; Sid
0x1800819b0  mov     [rsp+2A0h+peUse], rax; peUse
0x1800819b5  lea     r9, [rsp+2A0h+cbSid]; cbSid
0x1800819ba  lea     rax, [rsp+2A0h+var_25C]
0x1800819bf  xor     ecx, ecx; lpSystemName
0x1800819c1  mov     [rsp+2A0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800819c6  lea     rdx, [rsp+2A0h+Buffer]; lpAccountName
0x1800819cb  mov     [rsp+2A0h+ReferencedDomainName], r14; ReferencedDomainName
0x1800819d0  call    cs:__imp_LookupAccountNameW
0x1800819d7  nop     dword ptr [rax+rax+00h]
0x1800819dc  test    eax, eax
0x1800819de  jnz     short loc_1800819F3
0x1800819e0  call    cs:__imp_GetLastError
0x1800819e7  nop     dword ptr [rax+rax+00h]
0x1800819ec  mov     ebx, eax
0x1800819ee  jmp     loc_180081B00
0x1800819f3  lea     rdx, [rsp+2A0h+StringSid]; StringSid
0x1800819f8  mov     rcx, rsi; Sid
0x1800819fb  call    cs:__imp_ConvertSidToStringSidW
0x180081a02  nop     dword ptr [rax+rax+00h]
0x180081a07  test    eax, eax
0x180081a09  jnz     short loc_180081A15
0x180081a0b  mov     ebx, 3EBh
0x180081a10  jmp     loc_180081B00
0x180081a15  mov     rax, [rsp+2A0h+StringSid]
0x180081a1a  inc     rbx
0x180081a1d  cmp     [rax+rbx*2], r12w
0x180081a22  jnz     short loc_180081A1A
0x180081a24  lea     eax, [rbx+45h]
0x180081a27  mov     ecx, eax
0x180081a29  add     rcx, rcx; Size
0x180081a2c  mov     [rsp+2A0h+nSize], eax
0x180081a30  mov     ebx, eax
0x180081a32  call    cs:__imp_malloc
0x180081a39  nop     dword ptr [rax+rax+00h]
0x180081a3e  mov     rdi, rax
0x180081a41  test    rax, rax
0x180081a44  jnz     short loc_180081A4E
0x180081a46  lea     ebx, [rax+0Eh]
0x180081a49  jmp     loc_180081AED
0x180081a4e  test    rbx, rbx
0x180081a51  jz      short loc_180081AA4
0x180081a53  cmp     rbx, 7FFFFFFFh
0x180081a5a  ja      short loc_180081AA0
0x180081a5c  mov     r8d, 7FFFFFFEh
0x180081a62  lea     r9, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180081a69  sub     r8, rbx
0x180081a6c  mov     rdx, rbx
0x180081a6f  sub     r9, rdi
0x180081a72  mov     rcx, rdi
0x180081a75  lea     rax, [r8+rdx]
0x180081a79  test    rax, rax
0x180081a7c  jz      short loc_180081A95
0x180081a7e  movzx   eax, word ptr [r9+rcx]
0x180081a83  test    ax, ax
0x180081a86  jz      short loc_180081A95
0x180081a88  mov     [rcx], ax
0x180081a8b  add     rcx, 2
0x180081a8f  sub     rdx, 1
0x180081a93  jnz     short loc_180081A75
0x180081a95  test    rdx, rdx
0x180081a98  lea     rax, [rcx-2]
0x180081a9c  cmovnz  rax, rcx
0x180081aa0  mov     [rax], r12w
0x180081aa4  lea     r8, asc_180098AD8; "\\"
0x180081aab  mov     rdx, rbx; unsigned __int64
0x180081aae  mov     rcx, rdi; unsigned __int16 *
0x180081ab1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180081ab6  mov     edx, [rsp+2A0h+nSize]; unsigned __int64
0x180081aba  mov     rcx, rdi; unsigned __int16 *
0x180081abd  mov     r8, [rsp+2A0h+StringSid]; unsigned __int16 *
0x180081ac2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180081ac7  mov     r9d, 20019h; samDesired
0x180081acd  mov     [rsp+2A0h+ReferencedDomainName], r15; phkResult
0x180081ad2  xor     r8d, r8d; ulOptions
0x180081ad5  mov     rdx, rdi; lpSubKey
0x180081ad8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180081adf  call    cs:__imp_RegOpenKeyExW
0x180081ae6  nop     dword ptr [rax+rax+00h]
0x180081aeb  mov     ebx, eax
0x180081aed  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180081af4  call    cs:__imp_RegCloseKey
0x180081afb  nop     dword ptr [rax+rax+00h]
0x180081b00  mov     rcx, rsi
0x180081b03  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180081b0a  nop     dword ptr [rax+rax+00h]
0x180081b0f  test    r14, r14
0x180081b12  jz      short loc_180081B23
0x180081b14  mov     rcx, r14
0x180081b17  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180081b1e  nop     dword ptr [rax+rax+00h]
0x180081b23  test    rdi, rdi
0x180081b26  jz      short loc_180081B37
0x180081b28  mov     rcx, rdi; Block
0x180081b2b  call    cs:__imp_free
0x180081b32  nop     dword ptr [rax+rax+00h]
0x180081b37  mov     rcx, [rsp+2A0h+StringSid]; hMem
0x180081b3c  test    rcx, rcx
0x180081b3f  jz      short loc_180081B4D
0x180081b41  call    cs:__imp_LocalFree
0x180081b48  nop     dword ptr [rax+rax+00h]
0x180081b4d  mov     eax, ebx
0x180081b4f  mov     rcx, [rbp+1A0h+var_30]
0x180081b56  xor     rcx, rsp; StackCookie
0x180081b59  call    __security_check_cookie
0x180081b5e  lea     r11, [rsp+2A0h+var_20]
0x180081b66  mov     rbx, [r11+30h]
0x180081b6a  mov     rsi, [r11+40h]
0x180081b6e  mov     rsp, r11
0x180081b71  pop     r15
0x180081b73  pop     r14
0x180081b75  pop     r12
0x180081b77  pop     rdi
0x180081b78  pop     rbp
0x180081b79  retn
0x180081b7b  call    __report_rangecheckfailure
```
