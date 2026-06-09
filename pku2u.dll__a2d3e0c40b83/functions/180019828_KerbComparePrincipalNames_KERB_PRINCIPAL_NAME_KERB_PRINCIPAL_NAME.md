# KerbComparePrincipalNames(KERB_PRINCIPAL_NAME *,KERB_PRINCIPAL_NAME *)

- ea: `0x180019828`
- end: `0x180019922`
- name: `?KerbComparePrincipalNames@@YAEPEAUKERB_PRINCIPAL_NAME@@0@Z`
- size: `250`
- prototype: `unsigned __int8 __fastcall(struct KERB_PRINCIPAL_NAME *, struct KERB_PRINCIPAL_NAME *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e900`

## callees

- `0x180003700`
- `0x180004d60`
- `0x180019828`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x180019890`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x180019890`
- `ntdll!RtlEqualUnicodeString` at `0x180019901`
- `ntdll!RtlEqualUnicodeString` at `0x180019901`

## pseudocode

```c
bool __fastcall KerbComparePrincipalNames(struct KERB_PRINCIPAL_NAME *a1, struct KERB_PRINCIPAL_NAME *a2)
{
  __int64 **v5; // rsi
  __int64 **v6; // rdi
  BOOLEAN v7; // bl
  UNICODE_STRING String1; // [rsp+20h] [rbp-20h] BYREF
  UNICODE_STRING String2; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v10; // [rsp+60h] [rbp+20h] BYREF

  if ( !a1 )
    return !a2;
  if ( !a2 )
    return 0;
  if ( !*(_DWORD *)a1 || !*(_DWORD *)a2 || *(_DWORD *)a1 == *(_DWORD *)a2 )
  {
    v5 = (__int64 **)*((_QWORD *)a1 + 1);
    v6 = (__int64 **)*((_QWORD *)a2 + 1);
    while ( v5 )
    {
      if ( !v6 || lstrcmpiA((LPCSTR)v5[1], (LPCSTR)v6[1]) )
        goto LABEL_15;
      v5 = (__int64 **)*v5;
      v6 = (__int64 **)*v6;
    }
    if ( !v6 )
      return 1;
  }
LABEL_15:
  v10 = 0;
  String1 = 0;
  String2 = 0;
  if ( (unsigned int)KerbConvertPrincipalNameToString(&String1, &v10, a1) )
    return 0;
  if ( (unsigned int)KerbConvertPrincipalNameToString(&String2, &v10, a2) )
  {
    KerbFreeString(&String1);
    return 0;
  }
  v7 = RtlEqualUnicodeString(&String1, &String2, 1u);
  KerbFreeString(&String1);
  KerbFreeString(&String2);
  return v7;
}

```

## disassembly

```asm
0x180019828  mov     [rsp-18h+arg_8], rbx
0x18001982d  mov     [rsp-18h+arg_10], rsi
0x180019832  push    rbp
0x180019833  push    rdi
0x180019834  push    r14
0x180019836  mov     rbp, rsp
0x180019839  sub     rsp, 40h
0x18001983d  mov     rbx, rdx
0x180019840  mov     r14, rcx
0x180019843  test    rcx, rcx
0x180019846  jnz     short loc_180019862
0x180019848  test    rdx, rdx
0x18001984b  jz      short loc_1800198A7
0x18001984d  xor     al, al
0x18001984f  mov     rbx, [rsp+40h+arg_8]
0x180019854  mov     rsi, [rsp+40h+arg_10]
0x180019859  add     rsp, 40h
0x18001985d  pop     r14
0x18001985f  pop     rdi
0x180019860  pop     rbp
0x180019861  retn
0x180019862  test    rbx, rbx
0x180019865  jz      short loc_18001984D
0x180019867  cmp     dword ptr [rcx], 0
0x18001986a  jz      short loc_180019876
0x18001986c  mov     eax, [rdx]
0x18001986e  test    eax, eax
0x180019870  jz      short loc_180019876
0x180019872  cmp     [rcx], eax
0x180019874  jnz     short loc_1800198AB
0x180019876  mov     rsi, [rcx+8]
0x18001987a  mov     rdi, [rdx+8]
0x18001987e  test    rsi, rsi
0x180019881  jz      short loc_1800198A2
0x180019883  test    rdi, rdi
0x180019886  jz      short loc_1800198AB
0x180019888  mov     rdx, [rdi+8]; lpString2
0x18001988c  mov     rcx, [rsi+8]; lpString1
0x180019890  call    cs:__imp_lstrcmpiA
0x180019896  test    eax, eax
0x180019898  jnz     short loc_1800198AB
0x18001989a  mov     rsi, [rsi]
0x18001989d  mov     rdi, [rdi]
0x1800198a0  jmp     short loc_18001987E
0x1800198a2  test    rdi, rdi
0x1800198a5  jnz     short loc_1800198AB
0x1800198a7  mov     al, 1
0x1800198a9  jmp     short loc_18001984F
0x1800198ab  xorps   xmm0, xmm0
0x1800198ae  mov     [rbp+arg_0], 0
0x1800198b5  xorps   xmm1, xmm1
0x1800198b8  lea     rdx, [rbp+arg_0]; unsigned int *
0x1800198bc  mov     r8, r14; struct KERB_PRINCIPAL_NAME *
0x1800198bf  lea     rcx, [rbp+String1]; struct _UNICODE_STRING *
0x1800198c3  movups  xmmword ptr [rbp+String1.Length], xmm0
0x1800198c7  movups  xmmword ptr [rbp+String2.Length], xmm1
0x1800198cb  call    ?KerbConvertPrincipalNameToString@@YAJPEAU_UNICODE_STRING@@PEAKPEAUKERB_PRINCIPAL_NAME@@@Z; KerbConvertPrincipalNameToString(_UNICODE_STRING *,ulong *,KERB_PRINCIPAL_NAME *)
0x1800198d0  test    eax, eax
0x1800198d2  jnz     loc_18001984D
0x1800198d8  mov     r8, rbx; struct KERB_PRINCIPAL_NAME *
0x1800198db  lea     rdx, [rbp+arg_0]; unsigned int *
0x1800198df  lea     rcx, [rbp+String2]; struct _UNICODE_STRING *
0x1800198e3  call    ?KerbConvertPrincipalNameToString@@YAJPEAU_UNICODE_STRING@@PEAKPEAUKERB_PRINCIPAL_NAME@@@Z; KerbConvertPrincipalNameToString(_UNICODE_STRING *,ulong *,KERB_PRINCIPAL_NAME *)
0x1800198e8  lea     rcx, [rbp+String1]; struct _UNICODE_STRING *
0x1800198ec  test    eax, eax
0x1800198ee  jz      short loc_1800198FA
0x1800198f0  call    ?KerbFreeString@@YAXPEAU_UNICODE_STRING@@@Z; KerbFreeString(_UNICODE_STRING *)
0x1800198f5  jmp     loc_18001984D
0x1800198fa  mov     r8b, 1; CaseInsensitive
0x1800198fd  lea     rdx, [rbp+String2]; String2
0x180019901  call    cs:__imp_RtlEqualUnicodeString
0x180019907  lea     rcx, [rbp+String1]; struct _UNICODE_STRING *
0x18001990b  mov     bl, al
0x18001990d  call    ?KerbFreeString@@YAXPEAU_UNICODE_STRING@@@Z; KerbFreeString(_UNICODE_STRING *)
0x180019912  lea     rcx, [rbp+String2]; struct _UNICODE_STRING *
0x180019916  call    ?KerbFreeString@@YAXPEAU_UNICODE_STRING@@@Z; KerbFreeString(_UNICODE_STRING *)
0x18001991b  mov     al, bl
0x18001991d  jmp     loc_18001984F
```
