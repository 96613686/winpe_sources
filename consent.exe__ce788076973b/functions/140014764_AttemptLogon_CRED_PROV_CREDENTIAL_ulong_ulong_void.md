# AttemptLogon(_CRED_PROV_CREDENTIAL *,ulong,ulong,void * *)

- ea: `0x140014764`
- end: `0x1400148f0`
- name: `?AttemptLogon@@YAKPEAU_CRED_PROV_CREDENTIAL@@KKPEAPEAX@Z`
- size: `396`
- prototype: `__int64 __fastcall(struct _CRED_PROV_CREDENTIAL *, ULONG, ULONG, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140015d68`

## callees

- `0x1400140c8`
- `0x140014764`
- `0x14001e050`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400148c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400148c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400147d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400147d3`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x1400148a0`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x1400148a0`
- `SspiCli!SeciFreeCallContext` at `0x1400148bb`
- `SspiCli!SeciFreeCallContext` at `0x1400148bb`
- `ntdll!RtlLengthRequiredSid` at `0x1400147ba`
- `ntdll!RtlLengthRequiredSid` at `0x1400147c5`
- `ntdll!RtlLengthRequiredSid` at `0x1400147f2`
- `ntdll!RtlLengthRequiredSid` at `0x1400147ba`
- `ntdll!RtlLengthRequiredSid` at `0x1400147c5`
- `ntdll!RtlLengthRequiredSid` at `0x1400147f2`
- `ntdll!RtlSubAuthoritySid` at `0x140014818`
- `ntdll!RtlSubAuthoritySid` at `0x14001482c`
- `ntdll!RtlSubAuthoritySid` at `0x14001483d`
- `ntdll!RtlSubAuthoritySid` at `0x140014866`
- `ntdll!RtlSubAuthoritySid` at `0x140014818`
- `ntdll!RtlSubAuthoritySid` at `0x14001482c`
- `ntdll!RtlSubAuthoritySid` at `0x14001483d`
- `ntdll!RtlSubAuthoritySid` at `0x140014866`
- `ntdll!RtlInitializeSid` at `0x14001480d`
- `ntdll!RtlInitializeSid` at `0x14001485b`
- `ntdll!RtlInitializeSid` at `0x14001480d`
- `ntdll!RtlInitializeSid` at `0x14001485b`

## pseudocode

```c
__int64 __fastcall AttemptLogon(struct _CRED_PROV_CREDENTIAL *a1, ULONG a2, ULONG a3, void **a4)
{
  ULONG v8; // ebx
  ULONG v9; // eax
  char *v10; // rax
  char *v11; // rsi
  unsigned int v12; // ebx
  char *v13; // rbx
  ULONG v14; // eax
  char *v15; // rdi
  int v17; // [rsp+20h] [rbp-40h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+24h] [rbp-3Ch] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v19; // [rsp+2Ch] [rbp-34h] BYREF
  _OWORD v20[2]; // [rsp+38h] [rbp-28h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v19.Value = 0;
  memset(v20, 0, 28);
  *(_WORD *)&v19.Value[4] = 512;
  v17 = 0;
  v8 = RtlLengthRequiredSid(3u);
  v9 = RtlLengthRequiredSid(1u);
  v10 = (char *)LocalAlloc(0x40u, v8 + v9 + 40);
  v11 = v10;
  if ( v10 )
  {
    v13 = v10 + 40;
    v14 = RtlLengthRequiredSid(3u);
    *(_DWORD *)v11 = 2;
    v15 = &v13[v14];
    RtlInitializeSid(v13, &IdentifierAuthority, 3u);
    *RtlSubAuthoritySid(v13, 0) = 5;
    *RtlSubAuthoritySid(v13, 1u) = a2;
    *RtlSubAuthoritySid(v13, 2u) = a3;
    *((_QWORD *)v11 + 1) = v13;
    *((_DWORD *)v11 + 4) = -1073741817;
    RtlInitializeSid(v15, &v19, 1u);
    *RtlSubAuthoritySid(v15, 0) = 0;
    *((_QWORD *)v11 + 3) = v15;
    *((_DWORD *)v11 + 8) = 7;
    memset((char *)v20 + 8, 0, 20);
    *(_QWORD *)&v20[0] = 23;
    BYTE7(v20[1]) = 1;
    SeciAllocateAndSetIPAddress(v20, 28, &v17);
    v12 = AttemptCredProvLogon(a1, (struct _TOKEN_GROUPS *)v11, a4);
  }
  else
  {
    v12 = 8;
  }
  if ( v17 )
    SeciFreeCallContext();
  LocalFree(v11);
  return v12;
}

```

## disassembly

```asm
0x140014764  mov     [rsp-38h+arg_8], rbx
0x140014769  push    rbp
0x14001476a  push    rsi
0x14001476b  push    rdi
0x14001476c  push    r12
0x14001476e  push    r13
0x140014770  push    r14
0x140014772  push    r15
0x140014774  mov     rbp, rsp
0x140014777  sub     rsp, 60h
0x14001477b  mov     rax, cs:__security_cookie
0x140014782  xor     rax, rsp
0x140014785  mov     [rbp+var_8], rax
0x140014789  xor     edi, edi
0x14001478b  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x140014791  xorps   xmm0, xmm0
0x140014794  mov     dword ptr [rbp+IdentifierAuthority.Value], edi
0x140014797  mov     r12, rcx
0x14001479a  mov     dword ptr [rbp+var_34.Value], edi
0x14001479d  movups  [rbp+var_28], xmm0
0x1400147a1  lea     ecx, [rdi+3]; SubAuthorityCount
0x1400147a4  mov     word ptr [rbp+var_34.Value+4], 200h
0x1400147aa  mov     r13, r9
0x1400147ad  mov     [rbp+var_40], edi
0x1400147b0  mov     r14d, r8d
0x1400147b3  mov     r15d, edx
0x1400147b6  movups  [rbp+var_28+0Ch], xmm0
0x1400147ba  call    cs:__imp_RtlLengthRequiredSid
0x1400147c0  lea     ecx, [rdi+1]; SubAuthorityCount
0x1400147c3  mov     ebx, eax
0x1400147c5  call    cs:__imp_RtlLengthRequiredSid
0x1400147cb  lea     ecx, [rdi+40h]; uFlags
0x1400147ce  lea     edx, [rax+28h]
0x1400147d1  add     edx, ebx; uBytes
0x1400147d3  call    cs:__imp_LocalAlloc
0x1400147d9  mov     rsi, rax
0x1400147dc  test    rax, rax
0x1400147df  jnz     short loc_1400147E9
0x1400147e1  lea     ebx, [rdi+8]
0x1400147e4  jmp     loc_1400148B6
0x1400147e9  mov     ecx, 3; SubAuthorityCount
0x1400147ee  lea     rbx, [rax+28h]
0x1400147f2  call    cs:__imp_RtlLengthRequiredSid
0x1400147f8  mov     r8b, 3; SubAuthorityCount
0x1400147fb  mov     dword ptr [rsi], 2
0x140014801  mov     edi, eax
0x140014803  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x140014807  mov     rcx, rbx; Sid
0x14001480a  add     rdi, rbx
0x14001480d  call    cs:__imp_RtlInitializeSid
0x140014813  xor     edx, edx; SubAuthority
0x140014815  mov     rcx, rbx; Sid
0x140014818  call    cs:__imp_RtlSubAuthoritySid
0x14001481e  mov     edx, 1; SubAuthority
0x140014823  mov     rcx, rbx; Sid
0x140014826  mov     dword ptr [rax], 5
0x14001482c  call    cs:__imp_RtlSubAuthoritySid
0x140014832  mov     edx, 2; SubAuthority
0x140014837  mov     rcx, rbx; Sid
0x14001483a  mov     [rax], r15d
0x14001483d  call    cs:__imp_RtlSubAuthoritySid
0x140014843  mov     r8b, 1; SubAuthorityCount
0x140014846  lea     rdx, [rbp+var_34]; IdentifierAuthority
0x14001484a  mov     rcx, rdi; Sid
0x14001484d  mov     [rax], r14d
0x140014850  mov     [rsi+8], rbx
0x140014854  mov     dword ptr [rsi+10h], 0C0000007h
0x14001485b  call    cs:__imp_RtlInitializeSid
0x140014861  xor     edx, edx; SubAuthority
0x140014863  mov     rcx, rdi; Sid
0x140014866  call    cs:__imp_RtlSubAuthoritySid
0x14001486c  xorps   xmm0, xmm0
0x14001486f  lea     r8, [rbp+var_40]
0x140014873  lea     rcx, [rbp+var_28]
0x140014877  mov     dword ptr [rax], 0
0x14001487d  mov     [rsi+18h], rdi
0x140014881  xor     edi, edi
0x140014883  mov     dword ptr [rsi+20h], 7
0x14001488a  movups  [rbp+var_28+8], xmm0
0x14001488e  mov     qword ptr [rbp+var_28], 17h
0x140014896  lea     edx, [rdi+1Ch]
0x140014899  mov     [rbp+var_11], 1
0x14001489d  mov     [rbp+var_10], edi
0x1400148a0  call    cs:__imp_SeciAllocateAndSetIPAddress
0x1400148a6  mov     r8, r13; void **
0x1400148a9  mov     rdx, rsi; struct _TOKEN_GROUPS *
0x1400148ac  mov     rcx, r12; struct _CRED_PROV_CREDENTIAL *
0x1400148af  call    ?AttemptCredProvLogon@@YAKPEAU_CRED_PROV_CREDENTIAL@@PEAU_TOKEN_GROUPS@@PEAPEAX@Z; AttemptCredProvLogon(_CRED_PROV_CREDENTIAL *,_TOKEN_GROUPS *,void * *)
0x1400148b4  mov     ebx, eax
0x1400148b6  cmp     [rbp+var_40], edi
0x1400148b9  jz      short loc_1400148C1
0x1400148bb  call    cs:__imp_SeciFreeCallContext
0x1400148c1  mov     rcx, rsi; hMem
0x1400148c4  call    cs:__imp_LocalFree
0x1400148ca  mov     eax, ebx
0x1400148cc  mov     rcx, [rbp+var_8]
0x1400148d0  xor     rcx, rsp; StackCookie
0x1400148d3  call    __security_check_cookie
0x1400148d8  mov     rbx, [rsp+60h+arg_8]
0x1400148e0  add     rsp, 60h
0x1400148e4  pop     r15
0x1400148e6  pop     r14
0x1400148e8  pop     r13
0x1400148ea  pop     r12
0x1400148ec  pop     rdi
0x1400148ed  pop     rsi
0x1400148ee  pop     rbp
0x1400148ef  retn
```
