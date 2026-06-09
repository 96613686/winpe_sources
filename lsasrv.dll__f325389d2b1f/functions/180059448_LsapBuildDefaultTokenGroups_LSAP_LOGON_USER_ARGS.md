# LsapBuildDefaultTokenGroups(_LSAP_LOGON_USER_ARGS *)

- ea: `0x180059448`
- end: `0x180059664`
- name: `?LsapBuildDefaultTokenGroups@@YAJPEAU_LSAP_LOGON_USER_ARGS@@@Z`
- size: `540`
- prototype: `__int64 __fastcall(struct _LSAP_LOGON_USER_ARGS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180056fec`

## callees

- `0x18000c300`
- `0x180016f70`
- `0x180059448`
- `0x1800b86d0`

## import_xrefs

- `ntdll!NtAllocateLocallyUniqueId` at `0x180059499`
- `ntdll!NtAllocateLocallyUniqueId` at `0x180059499`
- `ntdll!RtlSubAuthoritySid` at `0x18005952f`
- `ntdll!RtlSubAuthoritySid` at `0x180059549`
- `ntdll!RtlSubAuthoritySid` at `0x180059562`
- `ntdll!RtlSubAuthoritySid` at `0x18005960f`
- `ntdll!RtlSubAuthoritySid` at `0x18005952f`
- `ntdll!RtlSubAuthoritySid` at `0x180059549`
- `ntdll!RtlSubAuthoritySid` at `0x180059562`
- `ntdll!RtlSubAuthoritySid` at `0x18005960f`
- `ntdll!RtlInitializeSid` at `0x18005951e`
- `ntdll!RtlInitializeSid` at `0x1800595fe`
- `ntdll!RtlInitializeSid` at `0x18005951e`
- `ntdll!RtlInitializeSid` at `0x1800595fe`
- `ntdll!RtlLengthRequiredSid` at `0x1800594f5`
- `ntdll!RtlLengthRequiredSid` at `0x1800595d9`
- `ntdll!RtlLengthRequiredSid` at `0x1800594f5`
- `ntdll!RtlLengthRequiredSid` at `0x1800595d9`

## pseudocode

```c
NTSTATUS __fastcall LsapBuildDefaultTokenGroups(struct _LSAP_LOGON_USER_ARGS *a1)
{
  NTSTATUS result; // eax
  int v3; // ebx
  int v4; // eax
  char v5; // r15
  struct _RTL_BALANCED_NODE *v6; // rax
  struct _RTL_BALANCED_NODE *v7; // rdi
  struct _RTL_BALANCED_NODE *v8; // rsi
  ULONG v9; // eax
  struct _RTL_BALANCED_NODE *v10; // rax
  void *v11; // rdx
  struct _RTL_BALANCED_NODE *v12; // r15
  PULONG v13; // rax
  PULONG v14; // rax
  ULONG v15; // eax
  struct _RTL_BALANCED_NODE *v16; // rax
  LUID LocallyUniqueId; // [rsp+20h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v18; // [rsp+28h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+30h] [rbp-10h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *((_DWORD *)a1 + 9) = 0;
  *((_QWORD *)a1 + 5) = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v18.Value = 0;
  *(_WORD *)&v18.Value[4] = 512;
  LocallyUniqueId = 0;
  result = NtAllocateLocallyUniqueId(&LocallyUniqueId);
  v3 = result;
  if ( result >= 0 )
  {
    if ( (unsigned int)(*((_DWORD *)a1 + 4) - 4) <= 1 )
    {
      v4 = 2;
      v5 = 1;
    }
    else
    {
      v4 = 1;
      v5 = 0;
    }
    v6 = (struct _RTL_BALANCED_NODE *)LsapAllocate((unsigned int)(16 * (v4 - 1) + 24));
    v7 = v6;
    if ( !v6 )
      return -1073741801;
    LODWORD(v6->Children[0]) = 0;
    v8 = 0;
    if ( v5 )
    {
      v15 = RtlLengthRequiredSid(1u);
      v16 = (struct _RTL_BALANCED_NODE *)LsapAllocate(v15);
      v8 = v16;
      if ( !v16 )
      {
        v3 = -1073741801;
        goto LABEL_17;
      }
      RtlInitializeSid(v16, &v18, 1u);
      *RtlSubAuthoritySid(v8, 0) = 0;
      v7->Children[2 * LODWORD(v7->Children[0]) + 1] = v8;
      *((_DWORD *)&v7->16 + 4 * (unsigned int)LODWORD(v7->Children[0])++) = 7;
    }
    v9 = RtlLengthRequiredSid(3u);
    v10 = (struct _RTL_BALANCED_NODE *)LsapAllocate(v9);
    v12 = v10;
    if ( v10 )
    {
      RtlInitializeSid(v10, &IdentifierAuthority, 3u);
      *RtlSubAuthoritySid(v12, 0) = 5;
      v13 = RtlSubAuthoritySid(v12, 1u);
      *v13 = LocallyUniqueId.HighPart;
      v14 = RtlSubAuthoritySid(v12, 2u);
      *v14 = LocallyUniqueId.LowPart;
      v7->Children[2 * LODWORD(v7->Children[0]) + 1] = v12;
      *((_DWORD *)&v7->16 + 4 * (unsigned int)LODWORD(v7->Children[0])++) = -1073741817;
      *((_DWORD *)a1 + 9) = v7->Children[0];
      *((_QWORD *)a1 + 5) = v7;
      return v3;
    }
    v3 = -1073741801;
    if ( v8 )
      LsapSubProv_FreeRoutine(v8, v11);
LABEL_17:
    LsapSubProv_FreeRoutine(v7, v11);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180059448  mov     [rsp-28h+arg_8], rbx
0x18005944d  mov     [rsp-28h+arg_10], rsi
0x180059452  push    rbp
0x180059453  push    rdi
0x180059454  push    r12
0x180059456  push    r14
0x180059458  push    r15
0x18005945a  mov     rbp, rsp
0x18005945d  sub     rsp, 40h
0x180059461  mov     rax, cs:__security_cookie
0x180059468  xor     rax, rsp
0x18005946b  mov     [rbp+var_8], rax
0x18005946f  xor     r12d, r12d
0x180059472  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x180059478  mov     [rcx+24h], r12d
0x18005947c  mov     r14, rcx
0x18005947f  mov     [rcx+28h], r12
0x180059483  lea     rcx, [rbp+LocallyUniqueId]; LocallyUniqueId
0x180059487  mov     dword ptr [rbp+IdentifierAuthority.Value], r12d
0x18005948b  mov     dword ptr [rbp+var_18.Value], r12d
0x18005948f  mov     word ptr [rbp+var_18.Value+4], 200h
0x180059495  mov     qword ptr [rbp+LocallyUniqueId.LowPart], r12
0x180059499  call    cs:__imp_NtAllocateLocallyUniqueId
0x1800594a0  nop     dword ptr [rax+rax+00h]
0x1800594a5  mov     ebx, eax
0x1800594a7  test    eax, eax
0x1800594a9  js      loc_18005959A
0x1800594af  mov     eax, [r14+10h]
0x1800594b3  sub     eax, 4
0x1800594b6  cmp     eax, 1
0x1800594b9  jbe     loc_1800595C0
0x1800594bf  lea     eax, [r12+1]
0x1800594c4  mov     r15b, r12b
0x1800594c7  lea     ecx, [rax-1]
0x1800594ca  shl     ecx, 4
0x1800594cd  add     ecx, 18h
0x1800594d0  call    LsapAllocate
0x1800594d5  mov     rdi, rax
0x1800594d8  test    rax, rax
0x1800594db  jz      loc_1800595CD
0x1800594e1  mov     [rax], r12d
0x1800594e4  mov     rsi, r12
0x1800594e7  test    r15b, r15b
0x1800594ea  jnz     loc_1800595D4
0x1800594f0  mov     ecx, 3; SubAuthorityCount
0x1800594f5  call    cs:__imp_RtlLengthRequiredSid
0x1800594fc  nop     dword ptr [rax+rax+00h]
0x180059501  mov     ecx, eax
0x180059503  call    LsapAllocate
0x180059508  mov     r15, rax
0x18005950b  test    rax, rax
0x18005950e  jz      loc_180059645
0x180059514  mov     r8b, 3; SubAuthorityCount
0x180059517  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x18005951b  mov     rcx, rax; Sid
0x18005951e  call    cs:__imp_RtlInitializeSid
0x180059525  nop     dword ptr [rax+rax+00h]
0x18005952a  xor     edx, edx; SubAuthority
0x18005952c  mov     rcx, r15; Sid
0x18005952f  call    cs:__imp_RtlSubAuthoritySid
0x180059536  nop     dword ptr [rax+rax+00h]
0x18005953b  mov     edx, 1; SubAuthority
0x180059540  mov     rcx, r15; Sid
0x180059543  mov     dword ptr [rax], 5
0x180059549  call    cs:__imp_RtlSubAuthoritySid
0x180059550  nop     dword ptr [rax+rax+00h]
0x180059555  mov     ecx, [rbp+LocallyUniqueId.HighPart]
0x180059558  mov     edx, 2; SubAuthority
0x18005955d  mov     [rax], ecx
0x18005955f  mov     rcx, r15; Sid
0x180059562  call    cs:__imp_RtlSubAuthoritySid
0x180059569  nop     dword ptr [rax+rax+00h]
0x18005956e  mov     ecx, [rbp+LocallyUniqueId.LowPart]
0x180059571  mov     [rax], ecx
0x180059573  mov     eax, [rdi]
0x180059575  add     rax, rax
0x180059578  mov     [rdi+rax*8+8], r15
0x18005957d  mov     eax, [rdi]
0x18005957f  inc     rax
0x180059582  add     rax, rax
0x180059585  mov     dword ptr [rdi+rax*8], 0C0000007h
0x18005958c  inc     dword ptr [rdi]
0x18005958e  mov     eax, [rdi]
0x180059590  mov     [r14+24h], eax
0x180059594  mov     [r14+28h], rdi
0x180059598  mov     eax, ebx
0x18005959a  mov     rcx, [rbp+var_8]
0x18005959e  xor     rcx, rsp; StackCookie
0x1800595a1  call    __security_check_cookie
0x1800595a6  lea     r11, [rsp+40h+var_s0]
0x1800595ab  mov     rbx, [r11+38h]
0x1800595af  mov     rsi, [r11+40h]
0x1800595b3  mov     rsp, r11
0x1800595b6  pop     r15
0x1800595b8  pop     r14
0x1800595ba  pop     r12
0x1800595bc  pop     rdi
0x1800595bd  pop     rbp
0x1800595be  retn
0x1800595c0  mov     eax, 2
0x1800595c5  mov     r15b, 1
0x1800595c8  jmp     loc_1800594C7
0x1800595cd  mov     eax, 0C0000017h
0x1800595d2  jmp     short loc_18005959A
0x1800595d4  mov     ecx, 1; SubAuthorityCount
0x1800595d9  call    cs:__imp_RtlLengthRequiredSid
0x1800595e0  nop     dword ptr [rax+rax+00h]
0x1800595e5  mov     ecx, eax
0x1800595e7  call    LsapAllocate
0x1800595ec  mov     rsi, rax
0x1800595ef  test    rax, rax
0x1800595f2  jz      short loc_18005963E
0x1800595f4  mov     r8b, 1; SubAuthorityCount
0x1800595f7  lea     rdx, [rbp+var_18]; IdentifierAuthority
0x1800595fb  mov     rcx, rax; Sid
0x1800595fe  call    cs:__imp_RtlInitializeSid
0x180059605  nop     dword ptr [rax+rax+00h]
0x18005960a  xor     edx, edx; SubAuthority
0x18005960c  mov     rcx, rsi; Sid
0x18005960f  call    cs:__imp_RtlSubAuthoritySid
0x180059616  nop     dword ptr [rax+rax+00h]
0x18005961b  mov     [rax], r12d
0x18005961e  mov     eax, [rdi]
0x180059620  add     rax, rax
0x180059623  mov     [rdi+rax*8+8], rsi
0x180059628  mov     eax, [rdi]
0x18005962a  inc     rax
0x18005962d  add     rax, rax
0x180059630  mov     dword ptr [rdi+rax*8], 7
0x180059637  inc     dword ptr [rdi]
0x180059639  jmp     loc_1800594F0
0x18005963e  mov     ebx, 0C0000017h
0x180059643  jmp     short loc_180059657
0x180059645  mov     ebx, 0C0000017h
0x18005964a  test    rsi, rsi
0x18005964d  jz      short loc_180059657
0x18005964f  mov     rcx, rsi; struct _RTL_BALANCED_NODE *
0x180059652  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180059657  mov     rcx, rdi; struct _RTL_BALANCED_NODE *
0x18005965a  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18005965f  jmp     loc_180059598
```
