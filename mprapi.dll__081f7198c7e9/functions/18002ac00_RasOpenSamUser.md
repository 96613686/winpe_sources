# RasOpenSamUser

- ea: `0x18002ac00`
- end: `0x18002ae53`
- name: `RasOpenSamUser`
- size: `595`
- prototype: `__int64 __fastcall(LPCWSTR lpSystemName, LPCWSTR lpAccountName)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002aaf0`

## callees

- `0x18002ac00`
- `0x18005111e`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002acf8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ad06`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ad17`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002acf8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ad06`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ad17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ae14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ae22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ae30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ae14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ae22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ae30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acd0`
- `ntdll!RtlSubAuthoritySid` at `0x18002ada7`
- `ntdll!RtlSubAuthoritySid` at `0x18002ada7`
- `ntdll!RtlInitUnicodeString` at `0x18002ac62`
- `ntdll!RtlInitUnicodeString` at `0x18002ac62`
- `ntdll!RtlLengthSid` at `0x18002ad82`
- `ntdll!RtlLengthSid` at `0x18002ad82`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002ad70`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002ad99`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002ad70`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002ad99`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18002acbf`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18002ad5f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18002acbf`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18002ad5f`
- `SAMLIB!SamOpenUser` at `0x18002add9`
- `SAMLIB!SamOpenUser` at `0x18002add9`
- `SAMLIB!SamOpenDomain` at `0x18002adbf`
- `SAMLIB!SamOpenDomain` at `0x18002adbf`
- `SAMLIB!SamCloseHandle` at `0x18002adf7`
- `SAMLIB!SamCloseHandle` at `0x18002ae06`
- `SAMLIB!SamCloseHandle` at `0x18002adf7`
- `SAMLIB!SamCloseHandle` at `0x18002ae06`
- `SAMLIB!SamConnect` at `0x18002ac77`
- `SAMLIB!SamConnect` at `0x18002ac77`

## pseudocode

```c
__int64 __fastcall RasOpenSamUser(LPCWSTR lpSystemName, LPCWSTR lpAccountName, unsigned int a3, __int64 a4)
{
  __int64 v4; // rbx
  HLOCAL v7; // rsi
  HLOCAL v8; // r14
  WCHAR *v9; // r15
  int v10; // eax
  DWORD LastError; // edi
  WCHAR *ReferencedDomainName; // rax
  int v13; // edi
  ULONG v14; // eax
  PUCHAR v15; // rax
  ULONG v16; // r12d
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-39h] BYREF
  DWORD cbSid; // [rsp+4Ch] [rbp-35h] BYREF
  _SID_NAME_USE peUse; // [rsp+50h] [rbp-31h] BYREF
  __int64 v21; // [rsp+58h] [rbp-29h] BYREF
  __int64 v22; // [rsp+60h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-19h] BYREF
  __int128 v24; // [rsp+78h] [rbp-9h]
  _BYTE v25[28]; // [rsp+88h] [rbp+7h] BYREF

  v4 = 0;
  v21 = 0;
  cbSid = 0;
  cchReferencedDomainName = 0;
  memset(v25, 0, sizeof(v25));
  peUse = 0;
  v22 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v24 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, lpSystemName);
  v10 = SamConnect(&DestinationString, &v22, 32, 0);
  LastError = v10;
  if ( v10 >= 0 )
  {
    v4 = v22;
    if ( !v10 )
    {
      cbSid = 0;
      cchReferencedDomainName = 0;
      LookupAccountNameW(lpSystemName, lpAccountName, 0, &cbSid, 0, &cchReferencedDomainName, &peUse);
      if ( GetLastError() != 122 )
        goto LABEL_4;
      ++cchReferencedDomainName;
      v7 = LocalAlloc(0x40u, cbSid);
      v8 = LocalAlloc(0x40u, cbSid);
      ReferencedDomainName = (WCHAR *)LocalAlloc(0x40u, 2LL * cchReferencedDomainName);
      v9 = ReferencedDomainName;
      if ( !v7 || !ReferencedDomainName || !v8 )
      {
        LastError = -1073741801;
        goto LABEL_16;
      }
      if ( LookupAccountNameW(
             lpSystemName,
             lpAccountName,
             v7,
             &cbSid,
             ReferencedDomainName,
             &cchReferencedDomainName,
             &peUse) )
      {
        v13 = *RtlSubAuthorityCountSid(v7);
        if ( (_BYTE)v13 )
        {
          v14 = RtlLengthSid(v7);
          memmove_0(v8, v7, v14);
          v15 = RtlSubAuthorityCountSid(v8);
          --*v15;
          v16 = *RtlSubAuthoritySid(v7, v13 - 1);
          LastError = SamOpenDomain(v4, 512, v8, &v21);
          if ( !LastError )
            LastError = SamOpenUser(v21, a3, v16, a4);
        }
        else
        {
          LastError = -1073741704;
        }
      }
      else
      {
LABEL_4:
        LastError = GetLastError();
        if ( LastError == 1332 )
          LastError = -1073741724;
      }
    }
  }
LABEL_16:
  if ( v4 )
    SamCloseHandle(v4);
  if ( v21 )
    SamCloseHandle(v21);
  if ( v9 )
    LocalFree(v9);
  if ( v7 )
    LocalFree(v7);
  if ( v8 )
    LocalFree(v8);
  return LastError;
}

```

## disassembly

```asm
0x18002ac00  mov     rax, rsp
0x18002ac03  mov     [rax+8], rbx
0x18002ac07  mov     [rax+20h], r9
0x18002ac0b  mov     [rax+18h], r8d
0x18002ac0f  push    rbp
0x18002ac10  push    rsi
0x18002ac11  push    rdi
0x18002ac12  push    r12
0x18002ac14  push    r13
0x18002ac16  push    r14
0x18002ac18  push    r15
0x18002ac1a  lea     rbp, [rax-5Fh]
0x18002ac1e  sub     rsp, 0A0h
0x18002ac25  xor     ebx, ebx
0x18002ac27  xorps   xmm0, xmm0
0x18002ac2a  mov     r13, rdx
0x18002ac2d  mov     [rbp+57h+var_80], rbx
0x18002ac31  mov     rdx, rcx; SourceString
0x18002ac34  mov     [rbp+57h+cbSid], ebx
0x18002ac37  mov     r12, rcx
0x18002ac3a  mov     [rbp+57h+var_90], ebx
0x18002ac3d  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18002ac41  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002ac45  mov     [rbp+57h+peUse], ebx
0x18002ac48  xor     eax, eax
0x18002ac4a  mov     [rbp+57h+var_78], rbx
0x18002ac4e  movups  xmmword ptr [rbp+57h+var_50+0Ch], xmm0
0x18002ac52  mov     esi, ebx
0x18002ac54  mov     r14d, ebx
0x18002ac57  mov     r15d, ebx
0x18002ac5a  movups  [rbp+57h+var_60], xmm0
0x18002ac5e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002ac62  call    cs:__imp_RtlInitUnicodeString
0x18002ac68  xor     r9d, r9d
0x18002ac6b  lea     r8d, [rbx+20h]
0x18002ac6f  lea     rdx, [rbp+57h+var_78]
0x18002ac73  lea     rcx, [rbp+57h+DestinationString]
0x18002ac77  call    cs:__imp_SamConnect
0x18002ac7d  mov     edi, eax
0x18002ac7f  test    eax, eax
0x18002ac81  js      loc_18002ADEF
0x18002ac87  mov     rbx, [rbp+57h+var_78]
0x18002ac8b  xor     ecx, ecx
0x18002ac8d  test    eax, eax
0x18002ac8f  jnz     loc_18002ADEF
0x18002ac95  lea     rax, [rbp+57h+peUse]
0x18002ac99  mov     [rbp+57h+cbSid], ecx
0x18002ac9c  mov     [rsp+30h], rax; peUse
0x18002aca1  lea     r9, [rbp+57h+cbSid]; cbSid
0x18002aca5  lea     rax, [rbp+57h+var_90]
0x18002aca9  mov     [rbp+57h+var_90], ecx
0x18002acac  mov     [rsp+0D0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18002acb1  xor     r8d, r8d; Sid
0x18002acb4  mov     [rsp+0D0h+ReferencedDomainName], rcx; ReferencedDomainName
0x18002acb9  mov     rdx, r13; lpAccountName
0x18002acbc  mov     rcx, r12; lpSystemName
0x18002acbf  call    cs:__imp_LookupAccountNameW
0x18002acc5  call    cs:__imp_GetLastError
0x18002accb  cmp     eax, 7Ah ; 'z'
0x18002acce  jz      short loc_18002ACEB
0x18002acd0  call    cs:__imp_GetLastError
0x18002acd6  mov     edi, eax
0x18002acd8  mov     eax, 0C0000064h
0x18002acdd  cmp     edi, 534h
0x18002ace3  cmovz   edi, eax
0x18002ace6  jmp     loc_18002ADEF
0x18002aceb  mov     edx, [rbp+57h+cbSid]; uBytes
0x18002acee  mov     edi, 40h ; '@'
0x18002acf3  inc     [rbp+57h+var_90]
0x18002acf6  mov     ecx, edi; uFlags
0x18002acf8  call    cs:__imp_LocalAlloc
0x18002acfe  mov     edx, [rbp+57h+cbSid]; uBytes
0x18002ad01  mov     ecx, edi; uFlags
0x18002ad03  mov     rsi, rax
0x18002ad06  call    cs:__imp_LocalAlloc
0x18002ad0c  mov     edx, [rbp+57h+var_90]
0x18002ad0f  mov     ecx, edi; uFlags
0x18002ad11  add     rdx, rdx; uBytes
0x18002ad14  mov     r14, rax
0x18002ad17  call    cs:__imp_LocalAlloc
0x18002ad1d  mov     r15, rax
0x18002ad20  test    rsi, rsi
0x18002ad23  jz      loc_18002ADEA
0x18002ad29  test    rax, rax
0x18002ad2c  jz      loc_18002ADEA
0x18002ad32  test    r14, r14
0x18002ad35  jz      loc_18002ADEA
0x18002ad3b  lea     rax, [rbp+57h+peUse]
0x18002ad3f  mov     r8, rsi; Sid
0x18002ad42  mov     [rsp+30h], rax; peUse
0x18002ad47  lea     r9, [rbp+57h+cbSid]; cbSid
0x18002ad4b  lea     rax, [rbp+57h+var_90]
0x18002ad4f  mov     rdx, r13; lpAccountName
0x18002ad52  mov     [rsp+0D0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18002ad57  mov     rcx, r12; lpSystemName
0x18002ad5a  mov     [rsp+0D0h+ReferencedDomainName], r15; ReferencedDomainName
0x18002ad5f  call    cs:__imp_LookupAccountNameW
0x18002ad65  test    eax, eax
0x18002ad67  jz      loc_18002ACD0
0x18002ad6d  mov     rcx, rsi; Sid
0x18002ad70  call    cs:__imp_RtlSubAuthorityCountSid
0x18002ad76  movzx   edi, byte ptr [rax]
0x18002ad79  cmp     dil, 1
0x18002ad7d  jb      short loc_18002ADE3
0x18002ad7f  mov     rcx, rsi; Sid
0x18002ad82  call    cs:__imp_RtlLengthSid
0x18002ad88  mov     r8d, eax; Size
0x18002ad8b  mov     rdx, rsi; Src
0x18002ad8e  mov     rcx, r14; void *
0x18002ad91  call    memmove_0
0x18002ad96  mov     rcx, r14; Sid
0x18002ad99  call    cs:__imp_RtlSubAuthorityCountSid
0x18002ad9f  lea     edx, [rdi-1]; SubAuthority
0x18002ada2  mov     rcx, rsi; Sid
0x18002ada5  dec     byte ptr [rax]
0x18002ada7  call    cs:__imp_RtlSubAuthoritySid
0x18002adad  lea     r9, [rbp+57h+var_80]
0x18002adb1  mov     r8, r14
0x18002adb4  mov     edx, 200h
0x18002adb9  mov     rcx, rbx
0x18002adbc  mov     r12d, [rax]
0x18002adbf  call    cs:__imp_SamOpenDomain
0x18002adc5  mov     edi, eax
0x18002adc7  test    eax, eax
0x18002adc9  jnz     short loc_18002ADEF
0x18002adcb  mov     r9, [rbp+57h+arg_18]
0x18002adcf  mov     r8d, r12d
0x18002add2  mov     edx, [rbp+57h+arg_10]
0x18002add5  mov     rcx, [rbp+57h+var_80]
0x18002add9  call    cs:__imp_SamOpenUser
0x18002addf  mov     edi, eax
0x18002ade1  jmp     short loc_18002ADEF
0x18002ade3  mov     edi, 0C0000078h
0x18002ade8  jmp     short loc_18002ADEF
0x18002adea  mov     edi, 0C0000017h
0x18002adef  test    rbx, rbx
0x18002adf2  jz      short loc_18002ADFD
0x18002adf4  mov     rcx, rbx
0x18002adf7  call    cs:__imp_SamCloseHandle
0x18002adfd  mov     rcx, [rbp+57h+var_80]
0x18002ae01  test    rcx, rcx
0x18002ae04  jz      short loc_18002AE0C
0x18002ae06  call    cs:__imp_SamCloseHandle
0x18002ae0c  test    r15, r15
0x18002ae0f  jz      short loc_18002AE1A
0x18002ae11  mov     rcx, r15; hMem
0x18002ae14  call    cs:__imp_LocalFree
0x18002ae1a  test    rsi, rsi
0x18002ae1d  jz      short loc_18002AE28
0x18002ae1f  mov     rcx, rsi; hMem
0x18002ae22  call    cs:__imp_LocalFree
0x18002ae28  test    r14, r14
0x18002ae2b  jz      short loc_18002AE36
0x18002ae2d  mov     rcx, r14; hMem
0x18002ae30  call    cs:__imp_LocalFree
0x18002ae36  mov     rbx, [rsp+0D0h+arg_0]
0x18002ae3e  mov     eax, edi
0x18002ae40  add     rsp, 0A0h
0x18002ae47  pop     r15
0x18002ae49  pop     r14
0x18002ae4b  pop     r13
0x18002ae4d  pop     r12
0x18002ae4f  pop     rdi
0x18002ae50  pop     rsi
0x18002ae51  pop     rbp
0x18002ae52  retn
```
