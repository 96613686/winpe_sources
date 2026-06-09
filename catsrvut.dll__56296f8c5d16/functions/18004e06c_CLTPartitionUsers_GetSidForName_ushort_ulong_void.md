# CLTPartitionUsers::GetSidForName(ushort *,ulong *,void * *)

- ea: `0x18004e06c`
- end: `0x18004e19a`
- name: `?GetSidForName@CLTPartitionUsers@@AEAAJPEAGPEAKPEAPEAX@Z`
- size: `302`
- prototype: `int(CLTPartitionUsers *__hidden this, unsigned __int16 *, unsigned int *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004ebe0`
- `0x18004ef74`

## callees

- `0x18004e06c`
- `0x180055880`
- `0x180055940`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e0fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e0fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e0da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e16e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e0da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e16e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18004e0c6`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18004e15b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18004e0c6`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18004e15b`

## pseudocode

```c
int __fastcall CLTPartitionUsers::GetSidForName(
        CLTPartitionUsers *this,
        unsigned __int16 *a2,
        unsigned int *a3,
        void **a4)
{
  int result; // eax
  void *v8; // rbx
  unsigned __int64 v9; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  DWORD v14; // eax
  DWORD cbSid; // [rsp+30h] [rbp+0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+34h] [rbp+4h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp+8h] BYREF

  cbSid = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( LookupAccountNameLocalW(a2, 0, &cbSid, 0, &cchReferencedDomainName, &peUse) )
    return -2147418113;
  result = GetLastError();
  if ( result == 122 )
  {
    v8 = CoTaskMemAlloc(cbSid);
    if ( !v8 )
      return -2147024882;
    v9 = 2LL * cchReferencedDomainName;
    v10 = v9 + 15;
    if ( v9 + 15 < v9 )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
    v12 = alloca(v11);
    v13 = alloca(v11);
    if ( LookupAccountNameLocalW(a2, v8, &cbSid, (LPWSTR)&cbSid, &cchReferencedDomainName, &peUse) )
    {
      v14 = cbSid;
      *a4 = v8;
      *a3 = v14;
      return 0;
    }
    CoTaskMemFree(v8);
    result = GetLastError();
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18004e06c  push    rbp
0x18004e06e  push    rbx
0x18004e06f  push    rsi
0x18004e070  push    rdi
0x18004e071  push    r14
0x18004e073  sub     rsp, 50h
0x18004e077  lea     rbp, [rsp+30h]
0x18004e07c  mov     rax, cs:__security_cookie
0x18004e083  xor     rax, rbp
0x18004e086  mov     [rbp+40h+var_30], rax
0x18004e08a  mov     r14, rdx
0x18004e08d  mov     [rbp+40h+cbSid], 0
0x18004e094  lea     rax, [rbp+40h+var_38]
0x18004e098  mov     [rbp+40h+var_3C], 0
0x18004e09f  mov     [rsp+70h+peUse], rax; peUse
0x18004e0a4  mov     rdi, r9
0x18004e0a7  lea     rax, [rbp+40h+var_3C]
0x18004e0ab  mov     [rbp+40h+var_38], 0
0x18004e0b2  mov     rsi, r8
0x18004e0b5  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18004e0ba  xor     r9d, r9d; ReferencedDomainName
0x18004e0bd  lea     r8, [rbp+40h+cbSid]; cbSid
0x18004e0c1  xor     edx, edx; Sid
0x18004e0c3  mov     rcx, r14; lpAccountName
0x18004e0c6  call    cs:__imp_LookupAccountNameLocalW
0x18004e0cc  test    eax, eax
0x18004e0ce  jz      short loc_18004E0DA
0x18004e0d0  mov     eax, 8000FFFFh
0x18004e0d5  jmp     loc_18004E183
0x18004e0da  call    cs:__imp_GetLastError
0x18004e0e0  cmp     eax, 7Ah ; 'z'
0x18004e0e3  jz      short loc_18004E0FA
0x18004e0e5  test    eax, eax
0x18004e0e7  jle     loc_18004E183
0x18004e0ed  movzx   eax, ax
0x18004e0f0  or      eax, 80070000h
0x18004e0f5  jmp     loc_18004E183
0x18004e0fa  mov     ecx, [rbp+40h+cbSid]; cb
0x18004e0fd  call    cs:__imp_CoTaskMemAlloc
0x18004e103  mov     rbx, rax
0x18004e106  test    rax, rax
0x18004e109  jnz     short loc_18004E112
0x18004e10b  mov     eax, 8007000Eh
0x18004e110  jmp     short loc_18004E183
0x18004e112  mov     eax, [rbp+40h+var_3C]
0x18004e115  add     rax, rax
0x18004e118  lea     rcx, [rax+0Fh]
0x18004e11c  cmp     rcx, rax
0x18004e11f  ja      short loc_18004E12B
0x18004e121  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18004e12b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18004e12f  mov     rax, rcx
0x18004e132  call    _alloca_probe
0x18004e137  sub     rsp, rcx
0x18004e13a  lea     rax, [rbp+40h+var_38]
0x18004e13e  lea     r8, [rbp+40h+cbSid]; cbSid
0x18004e142  mov     rdx, rbx; Sid
0x18004e145  mov     rcx, r14; lpAccountName
0x18004e148  mov     [rsp+70h+peUse], rax; peUse
0x18004e14d  lea     r9, [rsp+70h+cbSid]; ReferencedDomainName
0x18004e152  lea     rax, [rbp+40h+var_3C]
0x18004e156  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18004e15b  call    cs:__imp_LookupAccountNameLocalW
0x18004e161  test    eax, eax
0x18004e163  jnz     short loc_18004E179
0x18004e165  mov     rcx, rbx; pv
0x18004e168  call    cs:__imp_CoTaskMemFree
0x18004e16e  call    cs:__imp_GetLastError
0x18004e174  jmp     loc_18004E0E5
0x18004e179  mov     eax, [rbp+40h+cbSid]
0x18004e17c  mov     [rdi], rbx
0x18004e17f  mov     [rsi], eax
0x18004e181  xor     eax, eax
0x18004e183  mov     rcx, [rbp+40h+var_30]
0x18004e187  xor     rcx, rbp; StackCookie
0x18004e18a  call    __security_check_cookie
0x18004e18f  lea     rsp, [rbp+20h]
0x18004e193  pop     r14
0x18004e195  pop     rdi
0x18004e196  pop     rsi
0x18004e197  pop     rbx
0x18004e198  pop     rbp
0x18004e199  retn
```
