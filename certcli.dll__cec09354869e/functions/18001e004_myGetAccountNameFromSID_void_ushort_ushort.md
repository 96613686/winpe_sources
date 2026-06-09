# myGetAccountNameFromSID(void *,ushort * *,ushort * *)

- ea: `0x18001e004`
- end: `0x18001e168`
- name: `?myGetAccountNameFromSID@@YAJPEAXPEAPEAG1@Z`
- size: `356`
- prototype: `__int64 __fastcall(PSID Sid, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001e660`

## callees

- `0x18001e004`
- `0x180021438`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e0a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e0ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e0a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e0ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e146`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e14f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e146`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e14f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001e08e`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001e08e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001e06d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001e112`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001e06d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001e112`

## pseudocode

```c
__int64 __fastcall myGetAccountNameFromSID(PSID Sid, unsigned __int16 **a2, unsigned __int16 **a3)
{
  WCHAR *ReferencedDomainName; // rsi
  unsigned int v7; // eax
  unsigned int v8; // ebx
  WCHAR *v9; // rdi
  unsigned int v10; // ecx
  int v11; // edx
  DWORD cchReferencedDomainName; // [rsp+78h] [rbp+10h] BYREF
  DWORD cchName; // [rsp+80h] [rbp+18h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+88h] [rbp+20h] BYREF

  ReferencedDomainName = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( !LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
  {
    v7 = myHLastError();
    v8 = v7;
    if ( v7 != -2147024774 )
    {
      v9 = 0;
      v10 = 628294042;
LABEL_8:
      v11 = v7;
LABEL_9:
      CSPrintErrorLineFile(v10, v11);
      goto LABEL_21;
    }
  }
  v9 = (WCHAR *)LocalAlloc(0, 2LL * cchName);
  if ( !v9 )
  {
    v11 = -2147024882;
    v10 = 628818330;
    v8 = -2147024882;
    goto LABEL_9;
  }
  ReferencedDomainName = (WCHAR *)LocalAlloc(0, 2LL * cchReferencedDomainName);
  if ( !ReferencedDomainName )
  {
    v11 = -2147024882;
    v10 = 629277082;
    v8 = -2147024882;
    goto LABEL_9;
  }
  if ( !LookupAccountSidW(0, Sid, v9, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v7 = myHLastError();
    v8 = v7;
    v10 = 630129050;
    goto LABEL_8;
  }
  if ( a3 )
  {
    *a3 = ReferencedDomainName;
    ReferencedDomainName = 0;
  }
  if ( a2 )
  {
    *a2 = v9;
    v9 = 0;
  }
  v8 = 0;
LABEL_21:
  LocalFree(ReferencedDomainName);
  LocalFree(v9);
  return v8;
}

```

## disassembly

```asm
0x18001e004  mov     [rsp+arg_0], rbx
0x18001e009  push    rbp
0x18001e00a  push    rsi
0x18001e00b  push    rdi
0x18001e00c  push    r14
0x18001e00e  push    r15
0x18001e010  sub     rsp, 40h
0x18001e014  xor     esi, esi
0x18001e016  mov     r14, r8
0x18001e019  mov     r15, rdx
0x18001e01c  mov     rbp, rcx
0x18001e01f  test    rdx, rdx
0x18001e022  jz      short loc_18001E027
0x18001e024  mov     [rdx], rsi
0x18001e027  test    r14, r14
0x18001e02a  jz      short loc_18001E02F
0x18001e02c  mov     [r8], rsi
0x18001e02f  lea     rax, [rsp+68h+arg_18]
0x18001e037  mov     [rsp+68h+cchName], esi
0x18001e03e  mov     [rsp+68h+peUse], rax; peUse
0x18001e043  lea     r9, [rsp+68h+cchName]; cchName
0x18001e04b  lea     rax, [rsp+68h+arg_8]
0x18001e050  mov     [rsp+68h+arg_8], esi
0x18001e054  mov     [rsp+68h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001e059  xor     r8d, r8d; Name
0x18001e05c  mov     rdx, rbp; Sid
0x18001e05f  mov     [rsp+68h+ReferencedDomainName], rsi; ReferencedDomainName
0x18001e064  xor     ecx, ecx; lpSystemName
0x18001e066  mov     [rsp+68h+arg_18], esi
0x18001e06d  call    cs:__imp_LookupAccountSidW
0x18001e073  test    eax, eax
0x18001e075  jnz     short loc_18001E099
0x18001e077  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001e07c  mov     ebx, eax
0x18001e07e  cmp     eax, 8007007Ah
0x18001e083  jz      short loc_18001E099
0x18001e085  xor     edi, edi
0x18001e087  mov     ecx, 2573019Ah
0x18001e08c  mov     edx, eax
0x18001e08e  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001e094  jmp     loc_18001E143
0x18001e099  mov     edx, [rsp+68h+cchName]
0x18001e0a0  xor     ecx, ecx; uFlags
0x18001e0a2  add     rdx, rdx; uBytes
0x18001e0a5  call    cs:__imp_LocalAlloc
0x18001e0ab  mov     rdi, rax
0x18001e0ae  test    rax, rax
0x18001e0b1  jnz     short loc_18001E0C1
0x18001e0b3  mov     edx, 8007000Eh
0x18001e0b8  mov     ecx, 257B019Ah
0x18001e0bd  mov     ebx, edx
0x18001e0bf  jmp     short loc_18001E08E
0x18001e0c1  mov     edx, [rsp+68h+arg_8]
0x18001e0c5  xor     ecx, ecx; uFlags
0x18001e0c7  add     rdx, rdx; uBytes
0x18001e0ca  call    cs:__imp_LocalAlloc
0x18001e0d0  mov     rsi, rax
0x18001e0d3  test    rax, rax
0x18001e0d6  jnz     short loc_18001E0E6
0x18001e0d8  mov     edx, 8007000Eh
0x18001e0dd  mov     ecx, 2582019Ah
0x18001e0e2  mov     ebx, edx
0x18001e0e4  jmp     short loc_18001E08E
0x18001e0e6  lea     rax, [rsp+68h+arg_18]
0x18001e0ee  mov     r8, rdi; Name
0x18001e0f1  mov     [rsp+68h+peUse], rax; peUse
0x18001e0f6  lea     r9, [rsp+68h+cchName]; cchName
0x18001e0fe  lea     rax, [rsp+68h+arg_8]
0x18001e103  mov     rdx, rbp; Sid
0x18001e106  mov     [rsp+68h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001e10b  xor     ecx, ecx; lpSystemName
0x18001e10d  mov     [rsp+68h+ReferencedDomainName], rsi; ReferencedDomainName
0x18001e112  call    cs:__imp_LookupAccountSidW
0x18001e118  test    eax, eax
0x18001e11a  jnz     short loc_18001E12D
0x18001e11c  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001e121  mov     ebx, eax
0x18001e123  mov     ecx, 258F019Ah
0x18001e128  jmp     loc_18001E08C
0x18001e12d  test    r14, r14
0x18001e130  jz      short loc_18001E137
0x18001e132  mov     [r14], rsi
0x18001e135  xor     esi, esi
0x18001e137  test    r15, r15
0x18001e13a  jz      short loc_18001E141
0x18001e13c  mov     [r15], rdi
0x18001e13f  xor     edi, edi
0x18001e141  xor     ebx, ebx
0x18001e143  mov     rcx, rsi; hMem
0x18001e146  call    cs:__imp_LocalFree
0x18001e14c  mov     rcx, rdi; hMem
0x18001e14f  call    cs:__imp_LocalFree
0x18001e155  mov     eax, ebx
0x18001e157  mov     rbx, [rsp+68h+arg_0]
0x18001e15c  add     rsp, 40h
0x18001e160  pop     r15
0x18001e162  pop     r14
0x18001e164  pop     rdi
0x18001e165  pop     rsi
0x18001e166  pop     rbp
0x18001e167  retn
```
