# GetDomainAccountSid(ushort *,ushort *,void * *)

- ea: `0x180072da4`
- end: `0x180072ed4`
- name: `?GetDomainAccountSid@@YAJPEAG0PEAPEAX@Z`
- size: `304`
- prototype: `__int64 __fastcall(LPCWSTR lpSystemName, LPCWSTR lpAccountName, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180072cd4`

## callees

- `0x180011ac0`
- `0x18001d178`
- `0x18001d184`
- `0x180072da4`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072e53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072e53`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180072dd8`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180072dd8`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180072e48`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180072e48`

## string_xrefs

- `0x180072e7c`: `com\complus\dtc\shared\util\security.cpp`
- `0x180072e83`: `InstallDTC: LookupAccountNameW failed`

## pseudocode

```c
__int64 __fastcall GetDomainAccountSid(LPCWSTR lpSystemName, LPCWSTR lpAccountName, void **a3)
{
  unsigned int v3; // ebx
  int v7; // esi
  void *v8; // rax
  signed int LastError; // eax
  DWORD cbSid; // [rsp+40h] [rbp-258h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-254h] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-250h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+50h] [rbp-248h] BYREF

  v3 = 0;
  *a3 = 0;
  v7 = 2;
  cbSid = GetSidLengthRequired(2u);
  while ( v7 )
  {
    if ( *a3 )
      operator delete(*a3);
    v8 = operator new[](cbSid);
    *a3 = v8;
    if ( !v8 )
    {
      v3 = -2147024882;
      goto LABEL_14;
    }
    peUse = 0;
    cchReferencedDomainName = 260;
    if ( LookupAccountNameW(
           lpSystemName,
           lpAccountName,
           v8,
           &cbSid,
           ReferencedDomainName,
           &cchReferencedDomainName,
           &peUse) )
    {
      return 0;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    else
      v3 = LastError;
    if ( LastError != 122 )
    {
      TraceFile(v3, "InstallDTC: LookupAccountNameW failed", "com\\complus\\dtc\\shared\\util\\security.cpp", 0x287u);
      break;
    }
    --v7;
  }
  if ( (v3 & 0x80000000) == 0 )
    return v3;
LABEL_14:
  if ( *a3 )
  {
    operator delete(*a3);
    *a3 = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180072da4  push    rbx
0x180072da6  push    rbp
0x180072da7  push    rsi
0x180072da8  push    rdi
0x180072da9  push    r14
0x180072dab  sub     rsp, 270h
0x180072db2  mov     rax, cs:__security_cookie
0x180072db9  xor     rax, rsp
0x180072dbc  mov     [rsp+298h+var_38], rax
0x180072dc4  xor     ebx, ebx
0x180072dc6  mov     rbp, rcx
0x180072dc9  mov     rdi, r8
0x180072dcc  mov     [r8], rbx
0x180072dcf  mov     r14, rdx
0x180072dd2  lea     esi, [rbx+2]
0x180072dd5  mov     cl, sil; nSubAuthorityCount
0x180072dd8  call    cs:__imp_GetSidLengthRequired
0x180072dde  mov     [rsp+298h+cbSid], eax
0x180072de2  test    esi, esi
0x180072de4  jz      loc_180072E91
0x180072dea  mov     rcx, [rdi]; Block
0x180072ded  test    rcx, rcx
0x180072df0  jz      short loc_180072DF7
0x180072df2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180072df7  mov     ecx, [rsp+298h+cbSid]; unsigned __int64
0x180072dfb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180072e00  mov     [rdi], rax
0x180072e03  test    rax, rax
0x180072e06  jz      loc_180072ECD
0x180072e0c  lea     rcx, [rsp+298h+var_254]
0x180072e11  mov     [rsp+298h+var_254], 0
0x180072e19  mov     [rsp+298h+peUse], rcx; peUse
0x180072e1e  lea     r9, [rsp+298h+cbSid]; cbSid
0x180072e23  lea     rcx, [rsp+298h+var_250]
0x180072e28  mov     [rsp+298h+var_250], 104h
0x180072e30  mov     [rsp+298h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180072e35  mov     r8, rax; Sid
0x180072e38  lea     rcx, [rsp+298h+var_248]
0x180072e3d  mov     rdx, r14; lpAccountName
0x180072e40  mov     [rsp+298h+ReferencedDomainName], rcx; ReferencedDomainName
0x180072e45  mov     rcx, rbp; lpSystemName
0x180072e48  call    cs:__imp_LookupAccountNameW
0x180072e4e  cmp     eax, 1
0x180072e51  jz      short loc_180072EC9
0x180072e53  call    cs:__imp_GetLastError
0x180072e59  test    eax, eax
0x180072e5b  jg      short loc_180072E61
0x180072e5d  mov     ebx, eax
0x180072e5f  jmp     short loc_180072E6A
0x180072e61  movzx   ebx, ax
0x180072e64  or      ebx, 80070000h
0x180072e6a  cmp     eax, 7Ah ; 'z'
0x180072e6d  jnz     short loc_180072E76
0x180072e6f  dec     esi
0x180072e71  jmp     loc_180072DE2
0x180072e76  mov     r9d, 287h; unsigned int
0x180072e7c  lea     r8, aComComplusDtcS_9; "com\\complus\\dtc\\shared\\util\\securi"...
0x180072e83  lea     rdx, aInstalldtcLook; "InstallDTC: LookupAccountNameW failed"
0x180072e8a  mov     ecx, ebx; int
0x180072e8c  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180072e91  test    ebx, ebx
0x180072e93  jns     short loc_180072EA9
0x180072e95  mov     rcx, [rdi]; Block
0x180072e98  test    rcx, rcx
0x180072e9b  jz      short loc_180072EA9
0x180072e9d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180072ea2  mov     qword ptr [rdi], 0
0x180072ea9  mov     eax, ebx
0x180072eab  mov     rcx, [rsp+298h+var_38]
0x180072eb3  xor     rcx, rsp; StackCookie
0x180072eb6  call    __security_check_cookie
0x180072ebb  add     rsp, 270h
0x180072ec2  pop     r14
0x180072ec4  pop     rdi
0x180072ec5  pop     rsi
0x180072ec6  pop     rbp
0x180072ec7  pop     rbx
0x180072ec8  retn
0x180072ec9  xor     ebx, ebx
0x180072ecb  jmp     short loc_180072EA9
0x180072ecd  mov     ebx, 8007000Eh
0x180072ed2  jmp     short loc_180072E95
```
