# GetDomainNameFromTextualSid(ushort *,ushort *,ulong)

- ea: `0x180045b50`
- end: `0x180045ca1`
- name: `?GetDomainNameFromTextualSid@@YAJPEAG0K@Z`
- size: `337`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800470b0`

## callees

- `0x18001c6a4`
- `0x180045b50`
- `0x180049868`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045c78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045c86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045c78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045c86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045bbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045bd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045bbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045b97`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180045c6a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180045c6a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180045c07`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180045c07`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180045b8b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180045b8b`

## pseudocode

```c
__int64 __fastcall GetDomainNameFromTextualSid(unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned __int16 *v3; // rsi
  unsigned __int16 *v5; // rdi
  signed int LastError; // eax
  signed int v7; // ebx
  unsigned __int64 v8; // rdx
  signed int v9; // eax
  unsigned __int64 v10; // rdx
  enum _SID_NAME_USE peUse; // [rsp+30h] [rbp-10h] BYREF
  PSID Sid; // [rsp+38h] [rbp-8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+70h] [rbp+30h] BYREF
  DWORD cchName; // [rsp+78h] [rbp+38h] BYREF

  cchName = 1024;
  v3 = 0;
  cchReferencedDomainName = 1024;
  peUse = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) )
  {
    v5 = (unsigned __int16 *)CoTaskMemAlloc(2LL * cchName);
    if ( !v5 || (v3 = (unsigned __int16 *)CoTaskMemAlloc(2LL * cchReferencedDomainName)) == 0 )
    {
      v7 = -2147024882;
      goto LABEL_14;
    }
    if ( LookupAccountSidLocalW(Sid, v5, &cchName, v3, &cchReferencedDomainName, &peUse) )
    {
      *a2 = 0;
      if ( cchReferencedDomainName )
      {
        v7 = StringCbCatW(a2, v8, v3);
        if ( v7 < 0 )
          goto LABEL_14;
        v7 = StringCbCatW(a2, v10, L"\\");
        if ( v7 < 0 )
          goto LABEL_14;
      }
      v9 = StringCbCatW(a2, v8, v5);
    }
    else
    {
      v9 = StringCbCopyW(a2, 0x400u, a1);
    }
    v7 = v9;
    goto LABEL_14;
  }
  v5 = 0;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_14:
  if ( Sid )
    FreeSid(Sid);
  if ( v3 )
    CoTaskMemFree(v3);
  if ( v5 )
    CoTaskMemFree(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180045b50  mov     [rsp-18h+arg_0], rbx
0x180045b55  mov     [rsp-18h+arg_8], rsi
0x180045b5a  mov     [rsp-18h+arg_10], r8d
0x180045b5f  push    rbp
0x180045b60  push    rdi
0x180045b61  push    r14
0x180045b63  mov     rbp, rsp
0x180045b66  sub     rsp, 40h
0x180045b6a  mov     r14, rdx
0x180045b6d  mov     [rbp+cchName], 400h
0x180045b74  xor     esi, esi
0x180045b76  mov     [rbp+arg_10], 400h
0x180045b7d  lea     rdx, [rbp+Sid]; Sid
0x180045b81  mov     [rbp+var_10], esi
0x180045b84  mov     [rbp+Sid], rsi
0x180045b88  mov     rbx, rcx
0x180045b8b  call    cs:__imp_ConvertStringSidToSidW
0x180045b91  test    eax, eax
0x180045b93  jnz     short loc_180045BB5
0x180045b95  xor     edi, edi
0x180045b97  call    cs:__imp_GetLastError
0x180045b9d  mov     ebx, eax
0x180045b9f  test    eax, eax
0x180045ba1  jle     loc_180045C61
0x180045ba7  movzx   ebx, ax
0x180045baa  or      ebx, 80070000h
0x180045bb0  jmp     loc_180045C61
0x180045bb5  mov     ecx, [rbp+cchName]
0x180045bb8  add     rcx, rcx; cb
0x180045bbb  call    cs:__imp_CoTaskMemAlloc
0x180045bc1  mov     rdi, rax
0x180045bc4  test    rax, rax
0x180045bc7  jnz     short loc_180045BD3
0x180045bc9  mov     ebx, 8007000Eh
0x180045bce  jmp     loc_180045C61
0x180045bd3  mov     ecx, [rbp+arg_10]
0x180045bd6  add     rcx, rcx; cb
0x180045bd9  call    cs:__imp_CoTaskMemAlloc
0x180045bdf  mov     rsi, rax
0x180045be2  test    rax, rax
0x180045be5  jz      short loc_180045BC9
0x180045be7  mov     rcx, [rbp+Sid]; Sid
0x180045beb  lea     rax, [rbp+var_10]
0x180045bef  mov     [rsp+40h+peUse], rax; peUse
0x180045bf4  lea     r8, [rbp+cchName]; cchName
0x180045bf8  lea     rax, [rbp+arg_10]
0x180045bfc  mov     r9, rsi; ReferencedDomainName
0x180045bff  mov     rdx, rdi; Name
0x180045c02  mov     [rsp+40h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180045c07  call    cs:__imp_LookupAccountSidLocalW
0x180045c0d  test    eax, eax
0x180045c0f  jnz     short loc_180045C23
0x180045c11  mov     r8, rbx; unsigned __int16 *
0x180045c14  mov     edx, 400h; unsigned __int64
0x180045c19  mov     rcx, r14; unsigned __int16 *
0x180045c1c  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180045c21  jmp     short loc_180045C5F
0x180045c23  xor     eax, eax
0x180045c25  mov     [r14], ax
0x180045c29  cmp     [rbp+arg_10], eax
0x180045c2c  jbe     short loc_180045C54
0x180045c2e  mov     r8, rsi; unsigned __int16 *
0x180045c31  mov     rcx, r14; unsigned __int16 *
0x180045c34  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180045c39  mov     ebx, eax
0x180045c3b  test    eax, eax
0x180045c3d  js      short loc_180045C61
0x180045c3f  lea     r8, asc_180061B34; "\\"
0x180045c46  mov     rcx, r14; unsigned __int16 *
0x180045c49  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180045c4e  mov     ebx, eax
0x180045c50  test    eax, eax
0x180045c52  js      short loc_180045C61
0x180045c54  mov     r8, rdi; unsigned __int16 *
0x180045c57  mov     rcx, r14; unsigned __int16 *
0x180045c5a  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180045c5f  mov     ebx, eax
0x180045c61  mov     rcx, [rbp+Sid]; pSid
0x180045c65  test    rcx, rcx
0x180045c68  jz      short loc_180045C70
0x180045c6a  call    cs:__imp_FreeSid
0x180045c70  test    rsi, rsi
0x180045c73  jz      short loc_180045C7E
0x180045c75  mov     rcx, rsi; pv
0x180045c78  call    cs:__imp_CoTaskMemFree
0x180045c7e  test    rdi, rdi
0x180045c81  jz      short loc_180045C8C
0x180045c83  mov     rcx, rdi; pv
0x180045c86  call    cs:__imp_CoTaskMemFree
0x180045c8c  mov     rsi, [rsp+40h+arg_8]
0x180045c91  mov     eax, ebx
0x180045c93  mov     rbx, [rsp+40h+arg_0]
0x180045c98  add     rsp, 40h
0x180045c9c  pop     r14
0x180045c9e  pop     rdi
0x180045c9f  pop     rbp
0x180045ca0  retn
```
