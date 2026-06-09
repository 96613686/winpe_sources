# GetFriendlyNameFromSid(void *,wchar_t * *)

- ea: `0x1800a0448`
- end: `0x1800a05dc`
- name: `?GetFriendlyNameFromSid@@YAKPEAXPEAPEA_W@Z`
- size: `404`
- prototype: `unsigned int __fastcall(PSID Sid, wchar_t **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800a0124`
- `0x1800a07f8`

## callees

- `0x180003c14`
- `0x18001230c`
- `0x18001236c`
- `0x1800a0448`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a04ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a04d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a04f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a04ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a04d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a04f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a05ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a05bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a05ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a05bb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a04c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a04e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a054b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a04c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a04e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a054b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800a04a1`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800a0525`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800a04a1`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800a0525`

## pseudocode

```c
__int64 __fastcall GetFriendlyNameFromSid(PSID Sid, wchar_t **a2)
{
  DWORD LastError; // ebx
  WCHAR *v5; // rsi
  WCHAR *ReferencedDomainName; // rdi
  DWORD v7; // eax
  __int64 v8; // rax
  unsigned int v9; // r14d
  size_t v10; // r15
  wchar_t *v11; // rax
  wchar_t *v12; // rbx
  enum _SID_NAME_USE peUse[4]; // [rsp+40h] [rbp-10h] BYREF
  DWORD cchReferencedDomainName; // [rsp+90h] [rbp+40h] BYREF
  DWORD cchName; // [rsp+98h] [rbp+48h] BYREF

  cchName = 0;
  cchReferencedDomainName = 0;
  peUse[0] = 0;
  if ( LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, peUse)
    || (LastError = GetLastError(), LastError == 122) )
  {
    v5 = (WCHAR *)LocalAlloc(0, 2LL * cchName);
    if ( v5 )
    {
      ReferencedDomainName = (WCHAR *)LocalAlloc(0, 2LL * cchReferencedDomainName);
      if ( !ReferencedDomainName
        || !LookupAccountSidW(0, Sid, v5, &cchName, ReferencedDomainName, &cchReferencedDomainName, peUse) )
      {
        goto LABEL_6;
      }
      v7 = cchName;
      if ( cchReferencedDomainName )
        v7 = cchReferencedDomainName + cchName + 1;
      v8 = v7 + 1;
      v9 = v8;
      v10 = 2 * v8;
      v11 = (wchar_t *)LocalAlloc(0, 2 * v8);
      v12 = v11;
      if ( v11 )
      {
        memset_0(v11, 0, v10);
        if ( cchReferencedDomainName )
        {
          StringCchCopyW(v12, v9, ReferencedDomainName);
          StringCchCatW(v12, v9, L"\\");
          StringCchCatW(v12, v9, v5);
        }
        else
        {
          StringCchCopyW(v12, v9, v5);
        }
        *a2 = v12;
        LastError = 0;
      }
      else
      {
LABEL_6:
        LastError = GetLastError();
      }
      LocalFree(v5);
      if ( ReferencedDomainName )
        LocalFree(ReferencedDomainName);
    }
    else
    {
      return GetLastError();
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800a0448  mov     r11, rsp
0x1800a044b  mov     [r11+8], rbx
0x1800a044f  mov     [r11+10h], rsi
0x1800a0453  push    rbp
0x1800a0454  push    rdi
0x1800a0455  push    r12
0x1800a0457  push    r14
0x1800a0459  push    r15
0x1800a045b  mov     rbp, rsp
0x1800a045e  sub     rsp, 50h
0x1800a0462  lea     rax, [rbp+var_10]
0x1800a0466  mov     [rbp+cchName], 0
0x1800a046d  mov     [r11-48h], rax
0x1800a0471  lea     r9, [rbp+cchName]; cchName
0x1800a0475  lea     rax, [rbp+arg_10]
0x1800a0479  mov     [rbp+arg_10], 0
0x1800a0480  mov     r12, rdx
0x1800a0483  mov     [r11-50h], rax
0x1800a0487  mov     r14, rcx
0x1800a048a  mov     qword ptr [r11-58h], 0
0x1800a0492  mov     rdx, rcx; Sid
0x1800a0495  mov     [rbp+var_10], 0
0x1800a049c  xor     r8d, r8d; Name
0x1800a049f  xor     ecx, ecx; lpSystemName
0x1800a04a1  call    cs:__imp_LookupAccountSidW
0x1800a04a7  test    eax, eax
0x1800a04a9  jnz     short loc_1800A04BC
0x1800a04ab  call    cs:__imp_GetLastError
0x1800a04b1  mov     ebx, eax
0x1800a04b3  cmp     eax, 7Ah ; 'z'
0x1800a04b6  jnz     loc_1800A05C1
0x1800a04bc  mov     edx, [rbp+cchName]
0x1800a04bf  xor     ecx, ecx; uFlags
0x1800a04c1  add     rdx, rdx; uBytes
0x1800a04c4  call    cs:__imp_LocalAlloc
0x1800a04ca  mov     rsi, rax
0x1800a04cd  test    rax, rax
0x1800a04d0  jnz     short loc_1800A04DF
0x1800a04d2  call    cs:__imp_GetLastError
0x1800a04d8  mov     ebx, eax
0x1800a04da  jmp     loc_1800A05C1
0x1800a04df  mov     edx, [rbp+arg_10]
0x1800a04e2  xor     ecx, ecx; uFlags
0x1800a04e4  add     rdx, rdx; uBytes
0x1800a04e7  call    cs:__imp_LocalAlloc
0x1800a04ed  mov     rdi, rax
0x1800a04f0  test    rax, rax
0x1800a04f3  jnz     short loc_1800A0502
0x1800a04f5  call    cs:__imp_GetLastError
0x1800a04fb  mov     ebx, eax
0x1800a04fd  jmp     loc_1800A05AA
0x1800a0502  lea     rax, [rbp+var_10]
0x1800a0506  mov     r8, rsi; Name
0x1800a0509  mov     [rsp+50h+peUse], rax; peUse
0x1800a050e  lea     r9, [rbp+cchName]; cchName
0x1800a0512  lea     rax, [rbp+arg_10]
0x1800a0516  mov     rdx, r14; Sid
0x1800a0519  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800a051e  xor     ecx, ecx; lpSystemName
0x1800a0520  mov     [rsp+50h+ReferencedDomainName], rdi; ReferencedDomainName
0x1800a0525  call    cs:__imp_LookupAccountSidW
0x1800a052b  test    eax, eax
0x1800a052d  jz      short loc_1800A04F5
0x1800a052f  mov     ecx, [rbp+arg_10]
0x1800a0532  mov     eax, [rbp+cchName]
0x1800a0535  test    ecx, ecx
0x1800a0537  jz      short loc_1800A053D
0x1800a0539  inc     eax
0x1800a053b  add     eax, ecx
0x1800a053d  inc     eax
0x1800a053f  xor     ecx, ecx; uFlags
0x1800a0541  mov     r14d, eax
0x1800a0544  lea     r15, [rax+rax]
0x1800a0548  mov     rdx, r15; uBytes
0x1800a054b  call    cs:__imp_LocalAlloc
0x1800a0551  mov     rbx, rax
0x1800a0554  test    rax, rax
0x1800a0557  jz      short loc_1800A04F5
0x1800a0559  mov     r8, r15; Size
0x1800a055c  xor     edx, edx; Val
0x1800a055e  mov     rcx, rax; void *
0x1800a0561  call    memset_0
0x1800a0566  cmp     [rbp+arg_10], 0
0x1800a056a  mov     edx, r14d; unsigned __int64
0x1800a056d  mov     rcx, rbx; wchar_t *
0x1800a0570  jbe     short loc_1800A059C
0x1800a0572  mov     r8, rdi; wchar_t *
0x1800a0575  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800a057a  lea     r8, asc_1800C4454; "\\"
0x1800a0581  mov     edx, r14d; unsigned __int64
0x1800a0584  mov     rcx, rbx; wchar_t *
0x1800a0587  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800a058c  mov     r8, rsi; wchar_t *
0x1800a058f  mov     edx, r14d; unsigned __int64
0x1800a0592  mov     rcx, rbx; wchar_t *
0x1800a0595  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800a059a  jmp     short loc_1800A05A4
0x1800a059c  mov     r8, rsi; wchar_t *
0x1800a059f  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800a05a4  mov     [r12], rbx
0x1800a05a8  xor     ebx, ebx
0x1800a05aa  mov     rcx, rsi; hMem
0x1800a05ad  call    cs:__imp_LocalFree
0x1800a05b3  test    rdi, rdi
0x1800a05b6  jz      short loc_1800A05C1
0x1800a05b8  mov     rcx, rdi; hMem
0x1800a05bb  call    cs:__imp_LocalFree
0x1800a05c1  lea     r11, [rsp+50h+var_s0]
0x1800a05c6  mov     eax, ebx
0x1800a05c8  mov     rbx, [r11+30h]
0x1800a05cc  mov     rsi, [r11+38h]
0x1800a05d0  mov     rsp, r11
0x1800a05d3  pop     r15
0x1800a05d5  pop     r14
0x1800a05d7  pop     r12
0x1800a05d9  pop     rdi
0x1800a05da  pop     rbp
0x1800a05db  retn
```
