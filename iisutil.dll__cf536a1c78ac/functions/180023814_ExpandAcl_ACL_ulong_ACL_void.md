# ExpandAcl(_ACL *,ulong,_ACL * *,void *)

- ea: `0x180023814`
- end: `0x18002393e`
- name: `?ExpandAcl@@YAJPEAU_ACL@@KPEAPEAU1@PEAX@Z`
- size: `298`
- prototype: `__int64 __fastcall(PACL pAcl, unsigned int, struct _ACL **, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180023030`

## callees

- `0x180019230`
- `0x180019270`
- `0x180023814`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002390f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002390f`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800238ec`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800238ec`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180023854`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180023854`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800238a1`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800238a1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002386b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002386b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800238c3`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800238c3`

## pseudocode

```c
signed int __fastcall ExpandAcl(PACL pAcl, int a2, struct _ACL **a3, void *a4)
{
  signed int v8; // ebx
  struct _ACL *v9; // rax
  struct _ACL *v10; // rdi
  signed int result; // eax
  DWORD i; // ebx
  LPVOID pAce; // [rsp+30h] [rbp-48h] BYREF
  __int64 pAclInformation; // [rsp+38h] [rbp-40h] BYREF
  int v15; // [rsp+40h] [rbp-38h]

  pAclInformation = 0;
  v15 = 0;
  pAce = 0;
  if ( !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
    goto LABEL_12;
  v8 = GetLengthSid(a4) + a2 + 32;
  v9 = (struct _ACL *)operator new(v8);
  v10 = v9;
  if ( !v9 )
    return -2147024882;
  if ( !InitializeAcl(v9, v8, 2u) )
  {
LABEL_11:
    operator delete(v10);
LABEL_12:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  for ( i = 0; i < (unsigned int)pAclInformation; ++i )
  {
    if ( !GetAce(pAcl, i, &pAce) || !AddAce(v10, 2u, i, pAce, *((unsigned __int16 *)pAce + 1)) )
      goto LABEL_11;
  }
  *a3 = v10;
  return 0;
}

```

## disassembly

```asm
0x180023814  push    rbx
0x180023816  push    rbp
0x180023817  push    rsi
0x180023818  push    rdi
0x180023819  sub     rsp, 58h
0x18002381d  mov     rax, cs:__security_cookie
0x180023824  xor     rax, rsp
0x180023827  mov     [rsp+78h+var_30], rax
0x18002382c  xor     eax, eax
0x18002382e  mov     rdi, r9
0x180023831  mov     rsi, r8
0x180023834  mov     [rsp+78h+pAclInformation], rax
0x180023839  mov     ebx, edx
0x18002383b  mov     [rsp+78h+var_38], eax
0x18002383f  lea     rdx, [rsp+78h+pAclInformation]; pAclInformation
0x180023844  mov     [rsp+78h+pAce], rax
0x180023849  lea     r9d, [rax+2]; dwAclInformationClass
0x18002384d  mov     rbp, rcx
0x180023850  lea     r8d, [rax+0Ch]; nAclInformationLength
0x180023854  call    cs:__imp_GetAclInformation
0x18002385b  nop     dword ptr [rax+rax+00h]
0x180023860  test    eax, eax
0x180023862  jz      loc_18002390F
0x180023868  mov     rcx, rdi; pSid
0x18002386b  call    cs:__imp_GetLengthSid
0x180023872  nop     dword ptr [rax+rax+00h]
0x180023877  add     ebx, 20h ; ' '
0x18002387a  add     ebx, eax
0x18002387c  movsxd  rcx, ebx; Size
0x18002387f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023884  mov     rdi, rax
0x180023887  test    rax, rax
0x18002388a  jnz     short loc_180023896
0x18002388c  mov     eax, 8007000Eh
0x180023891  jmp     loc_180023927
0x180023896  mov     r8d, 2; dwAclRevision
0x18002389c  mov     edx, ebx; nAclLength
0x18002389e  mov     rcx, rdi; pAcl
0x1800238a1  call    cs:__imp_InitializeAcl
0x1800238a8  nop     dword ptr [rax+rax+00h]
0x1800238ad  test    eax, eax
0x1800238af  jz      short loc_180023907
0x1800238b1  xor     ebx, ebx
0x1800238b3  cmp     ebx, dword ptr [rsp+78h+pAclInformation]
0x1800238b7  jnb     short loc_180023900
0x1800238b9  lea     r8, [rsp+78h+pAce]; pAce
0x1800238be  mov     edx, ebx; dwAceIndex
0x1800238c0  mov     rcx, rbp; pAcl
0x1800238c3  call    cs:__imp_GetAce
0x1800238ca  nop     dword ptr [rax+rax+00h]
0x1800238cf  test    eax, eax
0x1800238d1  jz      short loc_180023907
0x1800238d3  mov     r9, [rsp+78h+pAce]; pAceList
0x1800238d8  mov     r8d, ebx; dwStartingAceIndex
0x1800238db  mov     edx, 2; dwAceRevision
0x1800238e0  mov     rcx, rdi; pAcl
0x1800238e3  movzx   eax, word ptr [r9+2]
0x1800238e8  mov     [rsp+78h+nAceListLength], eax; nAceListLength
0x1800238ec  call    cs:__imp_AddAce
0x1800238f3  nop     dword ptr [rax+rax+00h]
0x1800238f8  test    eax, eax
0x1800238fa  jz      short loc_180023907
0x1800238fc  inc     ebx
0x1800238fe  jmp     short loc_1800238B3
0x180023900  mov     [rsi], rdi
0x180023903  xor     eax, eax
0x180023905  jmp     short loc_180023927
0x180023907  mov     rcx, rdi; Block
0x18002390a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002390f  call    cs:__imp_GetLastError
0x180023916  nop     dword ptr [rax+rax+00h]
0x18002391b  test    eax, eax
0x18002391d  jle     short loc_180023927
0x18002391f  movzx   eax, ax
0x180023922  or      eax, 80070000h
0x180023927  mov     rcx, [rsp+78h+var_30]
0x18002392c  xor     rcx, rsp; StackCookie
0x18002392f  call    __security_check_cookie
0x180023934  add     rsp, 58h
0x180023938  pop     rdi
0x180023939  pop     rsi
0x18002393a  pop     rbp
0x18002393b  pop     rbx
0x18002393c  retn
```
