# ResetRegTreeSecurityInternal(HKEY__ *,ushort const *,void *)

- ea: `0x180008260`
- end: `0x180008519`
- name: `?ResetRegTreeSecurityInternal@@YAJPEAUHKEY__@@PEBGPEAX@Z`
- size: `697`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008044`

## callees

- `0x180008260`
- `0x18001268c`
- `0x18001b914`
- `0x1800227f2`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800084db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800084db`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180008439`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180008439`
- `NTMARTA!AccTreeResetNamedSecurityInfo` at `0x18000850b`
- `NTMARTA!AccTreeResetNamedSecurityInfo` at `0x18000850b`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!TreeResetNamedSecurityInfoW` at `0x180008491`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!TreeResetNamedSecurityInfoW` at `0x180008491`

## string_xrefs

- `0x1800082ef`: `onecore\admin\appmodel\common\removeregistrytree.cpp`
- `0x180008391`: `onecore\admin\appmodel\common\removeregistrytree.cpp`

## pseudocode

```c
__int64 __fastcall ResetRegTreeSecurityInternal(HKEY a1, const unsigned __int16 *a2, WCHAR *a3)
{
  __int64 v5; // r10
  __int64 v6; // rax
  WCHAR *p_pObjectName; // rcx
  unsigned int v8; // edi
  __int64 v10; // r11
  __int64 v11; // rdx
  _WORD *v12; // r9
  const wchar_t *v13; // r8
  _WORD *v14; // rdx
  WCHAR *v15; // rax
  unsigned int v16; // edi
  _WORD *v17; // rcx
  _WORD *v18; // rdx
  signed int v19; // ebx
  DWORD v20; // eax
  int pGroup; // [rsp+20h] [rbp-E0h]
  PACL NewAcl; // [rsp+60h] [rbp-A0h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+68h] [rbp-98h] BYREF
  WCHAR pObjectName; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v25[520]; // [rsp+A2h] [rbp-5Eh] BYREF
  _BYTE v26[6]; // [rsp+2AAh] [rbp+1AAh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  NewAcl = 0;
  pObjectName = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  memset_0(v25, 0, sizeof(v25));
  v5 = 261;
  v6 = 261;
  p_pObjectName = &pObjectName;
  while ( *p_pObjectName )
  {
    ++p_pObjectName;
    if ( !--v6 )
    {
      v8 = -2147024809;
LABEL_5:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
        (const char *)v8,
        pGroup);
      return v8;
    }
  }
  v10 = 2147483646;
  v11 = 2147483646;
  v12 = &v26[-2 * v6];
  v13 = L"USERS\\";
  do
  {
    if ( !v11 )
      break;
    if ( !*v13 )
      break;
    *v12++ = *v13++;
    --v11;
    --v6;
  }
  while ( v6 );
  v14 = v12 - 1;
  v8 = -2147024774;
  if ( v6 )
  {
    v14 = v12;
    v8 = 0;
  }
  *v14 = 0;
  if ( !v6 )
    goto LABEL_5;
  v15 = &pObjectName;
  while ( *v15 )
  {
    ++v15;
    if ( !--v5 )
    {
      v16 = -2147024809;
LABEL_17:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
        (const char *)v16,
        pGroup);
      return v16;
    }
  }
  v17 = &v26[-2 * v5];
  do
  {
    if ( !v10 )
      break;
    if ( !*a2 )
      break;
    *v17++ = *a2++;
    --v10;
    --v5;
  }
  while ( v5 );
  v18 = v17 - 1;
  v16 = -2147024774;
  if ( v5 )
  {
    v18 = v17;
    v16 = 0;
  }
  *v18 = 0;
  if ( !v5 )
    goto LABEL_17;
  pListOfExplicitEntries.grfAccessPermissions = 268697600;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.grfInheritance = 3;
  pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
  *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_USER;
  pListOfExplicitEntries.Trustee.ptstrName = a3;
  v19 = SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl);
  if ( !v19 )
  {
    if ( (unsigned __int8)IsTreeResetNamedSecurityInfoWPresent() )
      v20 = TreeResetNamedSecurityInfoW(
              &pObjectName,
              SE_REGISTRY_KEY,
              0x80000004,
              0,
              0,
              NewAcl,
              0,
              0,
              0,
              ProgressInvokeNever,
              0);
    else
      v20 = AccTreeResetNamedSecurityInfo(&pObjectName, 4, 2147483652LL, 0, 0, NewAcl, 0, 2, 0, 1, 0);
    v19 = v20;
  }
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( v19 > 0 )
    return (unsigned __int16)v19 | 0x80070000;
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180008260  mov     [rsp-8+arg_8], rbx
0x180008265  push    rbp
0x180008266  push    rsi
0x180008267  push    r14
0x180008269  lea     rbp, [rsp-1C0h]
0x180008271  sub     rsp, 2C0h
0x180008278  mov     rax, cs:__security_cookie
0x18000827f  xor     rax, rsp
0x180008282  mov     [rbp+1D0h+var_20], rax
0x180008289  xorps   xmm0, xmm0
0x18000828c  lea     rcx, [rbp+1D0h+var_22E]; void *
0x180008290  xor     r14d, r14d
0x180008293  mov     rsi, r8
0x180008296  mov     rbx, rdx
0x180008299  mov     [rsp+2D0h+NewAcl], r14
0x18000829e  xor     edx, edx; Val
0x1800082a0  mov     [rbp+1D0h+pObjectName], r14w
0x1800082a5  mov     r8d, 208h; Size
0x1800082ab  movups  xmmword ptr [rsp+2D0h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x1800082b0  movups  xmmword ptr [rsp+2D0h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x1800082b5  movups  xmmword ptr [rbp+1D0h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1800082b9  call    memset_0
0x1800082be  mov     r10d, 105h
0x1800082c4  mov     [rsp+2D0h+arg_0], rdi
0x1800082cc  mov     eax, r10d
0x1800082cf  lea     rcx, [rbp+1D0h+pObjectName]
0x1800082d3  cmp     [rcx], r14w
0x1800082d7  jz      short loc_18000830A
0x1800082d9  add     rcx, 2
0x1800082dd  sub     rax, 1
0x1800082e1  jnz     short loc_1800082D3
0x1800082e3  mov     edi, 80070057h
0x1800082e8  mov     rcx, [rbp+1D8h]; this
0x1800082ef  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\common\\remov"...
0x1800082f6  mov     r9d, edi; char *
0x1800082f9  mov     edx, 59h ; 'Y'; void *
0x1800082fe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008303  mov     eax, edi
0x180008305  jmp     loc_1800084AF
0x18000830a  lea     rcx, [rax+rax]
0x18000830e  mov     r11d, 7FFFFFFEh
0x180008314  lea     r9, [rbp+1D0h+var_26]
0x18000831b  mov     edx, r11d
0x18000831e  sub     r9, rcx
0x180008321  lea     r8, aUsers; "USERS\\"
0x180008328  test    rax, rax
0x18000832b  jz      short loc_180008353
0x18000832d  nop     dword ptr [rax]
0x180008330  test    rdx, rdx
0x180008333  jz      short loc_180008353
0x180008335  movzx   ecx, word ptr [r8]
0x180008339  test    cx, cx
0x18000833c  jz      short loc_180008353
0x18000833e  mov     [r9], cx
0x180008342  add     r8, 2
0x180008346  add     r9, 2
0x18000834a  dec     rdx
0x18000834d  sub     rax, 1
0x180008351  jnz     short loc_180008330
0x180008353  test    rax, rax
0x180008356  lea     rdx, [r9-2]
0x18000835a  mov     edi, 8007007Ah
0x18000835f  cmovnz  rdx, r9
0x180008363  cmovnz  edi, r14d
0x180008367  mov     [rdx], r14w
0x18000836b  jz      loc_1800082E8
0x180008371  lea     rax, [rbp+1D0h+pObjectName]
0x180008375  cmp     [rax], r14w
0x180008379  jz      short loc_1800083AC
0x18000837b  add     rax, 2
0x18000837f  sub     r10, 1
0x180008383  jnz     short loc_180008375
0x180008385  mov     edi, 80070057h
0x18000838a  mov     rcx, [rbp+1D8h]; this
0x180008391  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\common\\remov"...
0x180008398  mov     r9d, edi; char *
0x18000839b  mov     edx, 64h ; 'd'; void *
0x1800083a0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800083a5  mov     eax, edi
0x1800083a7  jmp     loc_1800084AF
0x1800083ac  lea     rax, [r10+r10]
0x1800083b0  lea     rcx, [rbp+1D0h+var_26]
0x1800083b7  sub     rcx, rax
0x1800083ba  test    r10, r10
0x1800083bd  jz      short loc_1800083E1
0x1800083bf  nop
0x1800083c0  test    r11, r11
0x1800083c3  jz      short loc_1800083E1
0x1800083c5  movzx   eax, word ptr [rbx]
0x1800083c8  test    ax, ax
0x1800083cb  jz      short loc_1800083E1
0x1800083cd  mov     [rcx], ax
0x1800083d0  add     rbx, 2
0x1800083d4  add     rcx, 2
0x1800083d8  dec     r11
0x1800083db  sub     r10, 1
0x1800083df  jnz     short loc_1800083C0
0x1800083e1  test    r10, r10
0x1800083e4  lea     rdx, [rcx-2]
0x1800083e8  mov     edi, 8007007Ah
0x1800083ed  cmovnz  rdx, rcx
0x1800083f1  cmovnz  edi, r14d
0x1800083f5  mov     [rdx], r14w
0x1800083f9  jz      short loc_18000838A
0x1800083fb  lea     r9, [rsp+2D0h+NewAcl]; NewAcl
0x180008400  mov     [rsp+2D0h+pListOfExplicitEntries.grfAccessPermissions], 10040000h
0x180008408  xor     r8d, r8d; OldAcl
0x18000840b  mov     [rsp+2D0h+pListOfExplicitEntries.grfAccessMode], 1
0x180008413  lea     rdx, [rsp+2D0h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180008418  mov     [rsp+2D0h+pListOfExplicitEntries.grfInheritance], 3
0x180008420  mov     ecx, 1; cCountOfExplicitEntries
0x180008425  mov     [rsp+2D0h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r14
0x18000842a  mov     qword ptr [rbp+1D0h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r14
0x18000842e  mov     [rbp+1D0h+pListOfExplicitEntries.Trustee.TrusteeType], 1
0x180008435  mov     [rbp+1D0h+pListOfExplicitEntries.Trustee.ptstrName], rsi
0x180008439  call    cs:__imp_SetEntriesInAclW
0x180008440  nop     dword ptr [rax+rax+00h]
0x180008445  mov     ebx, eax
0x180008447  test    eax, eax
0x180008449  jnz     short loc_18000849F
0x18000844b  call    IsTreeResetNamedSecurityInfoWPresent
0x180008450  mov     [rsp+2D0h+Args], r14; Args
0x180008455  lea     rcx, [rbp+1D0h+pObjectName]; pObjectName
0x180008459  xor     r9d, r9d; pOwner
0x18000845c  mov     [rsp+2D0h+ProgressInvokeSetting], 1; ProgressInvokeSetting
0x180008464  test    al, al
0x180008466  mov     [rsp+2D0h+fnProgress], r14; fnProgress
0x18000846b  mov     rax, [rsp+2D0h+NewAcl]
0x180008470  mov     edx, 4; ObjectType
0x180008475  mov     r8d, 80000004h; SecurityInfo
0x18000847b  jz      short loc_1800084F4
0x18000847d  mov     [rsp+2D0h+KeepExplicit], r14d; KeepExplicit
0x180008482  mov     [rsp+2D0h+pSacl], r14; pSacl
0x180008487  mov     [rsp+2D0h+pDacl], rax; pDacl
0x18000848c  mov     [rsp+2D0h+pGroup], r14; pGroup
0x180008491  call    cs:__imp_TreeResetNamedSecurityInfoW
0x180008498  nop     dword ptr [rax+rax+00h]
0x18000849d  mov     ebx, eax
0x18000849f  mov     rcx, [rsp+2D0h+NewAcl]; hMem
0x1800084a4  test    rcx, rcx
0x1800084a7  jnz     short loc_1800084DB
0x1800084a9  test    ebx, ebx
0x1800084ab  jg      short loc_1800084E9
0x1800084ad  mov     eax, ebx
0x1800084af  mov     rdi, [rsp+2D0h+arg_0]
0x1800084b7  mov     rcx, [rbp+1D0h+var_20]
0x1800084be  xor     rcx, rsp; StackCookie
0x1800084c1  call    __security_check_cookie
0x1800084c6  mov     rbx, [rsp+2D0h+arg_8]
0x1800084ce  add     rsp, 2C0h
0x1800084d5  pop     r14
0x1800084d7  pop     rsi
0x1800084d8  pop     rbp
0x1800084d9  retn
0x1800084db  call    cs:__imp_LocalFree
0x1800084e2  nop     dword ptr [rax+rax+00h]
0x1800084e7  jmp     short loc_1800084A9
0x1800084e9  movzx   ebx, bx
0x1800084ec  or      ebx, 80070000h
0x1800084f2  jmp     short loc_1800084AD
0x1800084f4  mov     [rsp+2D0h+KeepExplicit], 2
0x1800084fc  mov     [rsp+2D0h+pSacl], r14
0x180008501  mov     [rsp+2D0h+pDacl], rax
0x180008506  mov     [rsp+2D0h+pGroup], r14
0x18000850b  call    cs:__imp_AccTreeResetNamedSecurityInfo
0x180008512  nop     dword ptr [rax+rax+00h]
0x180008517  jmp     short loc_18000849D
```
