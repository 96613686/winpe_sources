# _BuildNt5ObjAce

- ea: `0x180024344`
- end: `0x18002458a`
- name: `_BuildNt5ObjAce`
- size: `582`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180024b90`
- `0x180024dbc`

## callees

- `0x1800049ac`
- `0x180024344`

## import_xrefs

- `ADVAPI32!AddAuditAccessObjectAce` at `0x180024507`
- `ADVAPI32!AddAuditAccessObjectAce` at `0x180024507`
- `ADVAPI32!AddAccessAllowedObjectAce` at `0x180024408`
- `ADVAPI32!AddAccessAllowedObjectAce` at `0x180024408`
- `ADVAPI32!AddAccessDeniedObjectAce` at `0x180024497`
- `ADVAPI32!AddAccessDeniedObjectAce` at `0x180024497`
- `KERNEL32!GetLastError` at `0x180024416`
- `KERNEL32!GetLastError` at `0x1800244a1`
- `KERNEL32!GetLastError` at `0x180024539`
- `KERNEL32!GetLastError` at `0x180024416`
- `KERNEL32!GetLastError` at `0x1800244a1`
- `KERNEL32!GetLastError` at `0x180024539`

## pseudocode

```c
__int64 __fastcall BuildNt5ObjAce(
        unsigned int a1,
        char a2,
        BOOL bAuditSuccess,
        BOOL bAuditFailure,
        PSID pSid,
        unsigned int a6,
        struct _ACL *pAcl)
{
  unsigned int v7; // edi
  struct RIGHTSMAP * near *v9; // rdx
  unsigned int v10; // ebp
  unsigned int v11; // r13d
  int i; // r14d
  __int64 j; // rbx
  DWORD LastError; // ebx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  struct RIGHTSMAP **v18; // [rsp+50h] [rbp-38h]
  BOOL v19; // [rsp+A0h] [rbp+18h]
  BOOL v20; // [rsp+A8h] [rbp+20h]

  v20 = bAuditFailure;
  v19 = bAuditSuccess;
  v7 = a6;
  if ( a6 != *((_DWORD *)&g_dwFullControlNT4 + a1) )
  {
    v9 = (&g_psExtendRightsMap5to4)[a1];
    v10 = 0;
    v11 = *((_DWORD *)&g_pdwExtendRightsSize5to4 + a1);
    v18 = v9;
    for ( i = 1; ; i *= 2 )
    {
      if ( v10 >= 8 )
        return 0;
      if ( (v7 & 1) != 0 )
        break;
LABEL_26:
      v7 >>= 1;
      ++v10;
    }
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      if ( (unsigned int)j >= v11 )
        goto LABEL_26;
      if ( HIDWORD(v9[3 * j + 2]) == i )
      {
        if ( a2 )
        {
          if ( a2 == 1 )
          {
            if ( !AddAccessDeniedObjectAce(pAcl, 4u, 0, 0x100u, (GUID *)&v9[3 * j], 0, pSid) )
            {
              LastError = GetLastError();
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
              {
                v16 = 18;
                goto LABEL_13;
              }
              goto LABEL_14;
            }
          }
          else
          {
            if ( a2 != 2 )
              continue;
            if ( !AddAuditAccessObjectAce(
                    pAcl,
                    4u,
                    0,
                    0x100u,
                    (GUID *)&v9[3 * j],
                    0,
                    pSid,
                    bAuditSuccess,
                    bAuditFailure) )
            {
              LastError = GetLastError();
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
              {
                v16 = 19;
LABEL_13:
                WPP_SF_d(v15[32], v16, &WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids, LastError);
              }
LABEL_14:
              if ( (int)LastError > 0 )
                return (unsigned __int16)LastError | 0x80070000;
              return LastError;
            }
          }
        }
        else if ( !AddAccessAllowedObjectAce(pAcl, 4u, 0, 0x100u, (GUID *)&v9[3 * j], 0, pSid) )
        {
          LastError = GetLastError();
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          {
            v16 = 17;
            goto LABEL_13;
          }
          goto LABEL_14;
        }
        bAuditFailure = v20;
        bAuditSuccess = v19;
        v9 = v18;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180024344  mov     rax, rsp
0x180024347  mov     [rax+8], rbx
0x18002434b  mov     [rax+10h], rbp
0x18002434f  mov     [rax+20h], r9d
0x180024353  mov     [rax+18h], r8d
0x180024357  push    rsi
0x180024358  push    rdi
0x180024359  push    r12
0x18002435b  push    r13
0x18002435d  push    r14
0x18002435f  sub     rsp, 60h
0x180024363  mov     edi, [rsp+88h+arg_28]
0x18002436a  lea     r13, cs:180000000h
0x180024371  mov     eax, ecx
0x180024373  mov     sil, dl
0x180024376  cmp     edi, ds:rva ?g_dwFullControlNT4@@3PAKA[r13+rax*4]; ulong near * g_dwFullControlNT4 ...
0x18002437e  jz      loc_18002456F
0x180024384  mov     rdx, ds:rva ?g_psExtendRightsMap5to4@@3PAPEAURIGHTSMAP@@A[r13+rax*8]; RIGHTSMAP * near * g_psExtendRightsMap5to4 ...
0x18002438c  xor     ebp, ebp
0x18002438e  mov     r13d, ds:rva ?g_pdwExtendRightsSize5to4@@3PAKA[r13+rax*4]; ulong near * g_pdwExtendRightsSize5to4 ...
0x180024396  mov     r12, [rsp+88h+arg_20]
0x18002439e  mov     [rsp+88h+var_38], rdx
0x1800243a3  lea     r14d, [rbp+1]
0x1800243a7  cmp     ebp, 8
0x1800243aa  jnb     loc_18002456F
0x1800243b0  test    dil, 1
0x1800243b4  jz      loc_18002452D
0x1800243ba  xor     ebx, ebx
0x1800243bc  cmp     ebx, r13d
0x1800243bf  jnb     loc_18002452D
0x1800243c5  lea     rcx, [rbx+rbx*2]
0x1800243c9  lea     rax, [rdx+rcx*8]
0x1800243cd  cmp     [rax+14h], r14d
0x1800243d1  jnz     loc_180024526
0x1800243d7  test    sil, sil
0x1800243da  jnz     loc_180024469
0x1800243e0  mov     rcx, [rsp+88h+pAcl]; pAcl
0x1800243e8  xor     r8d, r8d; AceFlags
0x1800243eb  mov     [rsp+88h+pSid], r12; pSid
0x1800243f0  mov     r9d, 100h; AccessMask
0x1800243f6  mov     [rsp+88h+InheritedObjectTypeGuid], 0; InheritedObjectTypeGuid
0x1800243ff  mov     [rsp+88h+ObjectTypeGuid], rax; ObjectTypeGuid
0x180024404  lea     edx, [r8+4]; dwAceRevision
0x180024408  call    cs:__imp_AddAccessAllowedObjectAce
0x18002440e  test    eax, eax
0x180024410  jnz     loc_180024511
0x180024416  call    cs:__imp_GetLastError
0x18002441c  mov     ebx, eax
0x18002441e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024425  lea     rax, WPP_GLOBAL_Control
0x18002442c  cmp     rcx, rax
0x18002442f  jz      short loc_180024455
0x180024431  test    byte ptr [rcx+10Ch], 1
0x180024438  jz      short loc_180024455
0x18002443a  mov     edx, 11h
0x18002443f  mov     rcx, [rcx+100h]
0x180024446  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x18002444d  mov     r9d, ebx
0x180024450  call    WPP_SF_d
0x180024455  test    ebx, ebx
0x180024457  jle     short loc_180024462
0x180024459  movzx   ebx, bx
0x18002445c  or      ebx, 80070000h
0x180024462  mov     eax, ebx
0x180024464  jmp     loc_180024571
0x180024469  cmp     sil, 1
0x18002446d  jnz     short loc_1800244CF
0x18002446f  mov     rcx, [rsp+88h+pAcl]; pAcl
0x180024477  xor     r8d, r8d; AceFlags
0x18002447a  mov     [rsp+88h+pSid], r12; pSid
0x18002447f  mov     r9d, 100h; AccessMask
0x180024485  mov     [rsp+88h+InheritedObjectTypeGuid], 0; InheritedObjectTypeGuid
0x18002448e  mov     [rsp+88h+ObjectTypeGuid], rax; ObjectTypeGuid
0x180024493  lea     edx, [r8+4]; dwAceRevision
0x180024497  call    cs:__imp_AddAccessDeniedObjectAce
0x18002449d  test    eax, eax
0x18002449f  jnz     short loc_180024511
0x1800244a1  call    cs:__imp_GetLastError
0x1800244a7  mov     ebx, eax
0x1800244a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800244b0  lea     rax, WPP_GLOBAL_Control
0x1800244b7  cmp     rcx, rax
0x1800244ba  jz      short loc_180024455
0x1800244bc  test    [rcx+10Ch], sil
0x1800244c3  jz      short loc_180024455
0x1800244c5  mov     edx, 12h
0x1800244ca  jmp     loc_18002443F
0x1800244cf  cmp     sil, 2
0x1800244d3  jnz     short loc_180024526
0x1800244d5  mov     rcx, [rsp+88h+pAcl]; pAcl
0x1800244dd  mov     [rsp+88h+bAuditFailure], r9d; bAuditFailure
0x1800244e2  mov     r9d, 100h; AccessMask
0x1800244e8  mov     [rsp+88h+bAuditSuccess], r8d; bAuditSuccess
0x1800244ed  xor     r8d, r8d; AceFlags
0x1800244f0  mov     [rsp+88h+pSid], r12; pSid
0x1800244f5  mov     [rsp+88h+InheritedObjectTypeGuid], 0; InheritedObjectTypeGuid
0x1800244fe  mov     [rsp+88h+ObjectTypeGuid], rax; ObjectTypeGuid
0x180024503  lea     edx, [r8+4]; dwAceRevision
0x180024507  call    cs:__imp_AddAuditAccessObjectAce
0x18002450d  test    eax, eax
0x18002450f  jz      short loc_180024539
0x180024511  mov     r9d, [rsp+88h+arg_18]
0x180024519  mov     r8d, [rsp+88h+arg_10]
0x180024521  mov     rdx, [rsp+88h+var_38]
0x180024526  inc     ebx
0x180024528  jmp     loc_1800243BC
0x18002452d  shr     edi, 1
0x18002452f  add     r14d, r14d
0x180024532  inc     ebp
0x180024534  jmp     loc_1800243A7
0x180024539  call    cs:__imp_GetLastError
0x18002453f  mov     ebx, eax
0x180024541  mov     rcx, cs:WPP_GLOBAL_Control
0x180024548  lea     rax, WPP_GLOBAL_Control
0x18002454f  cmp     rcx, rax
0x180024552  jz      loc_180024455
0x180024558  test    byte ptr [rcx+10Ch], 1
0x18002455f  jz      loc_180024455
0x180024565  mov     edx, 13h
0x18002456a  jmp     loc_18002443F
0x18002456f  xor     eax, eax
0x180024571  lea     r11, [rsp+88h+var_28]
0x180024576  mov     rbx, [r11+30h]
0x18002457a  mov     rbp, [r11+38h]
0x18002457e  mov     rsp, r11
0x180024581  pop     r14
0x180024583  pop     r13
0x180024585  pop     r12
0x180024587  pop     rdi
0x180024588  pop     rsi
0x180024589  retn
```
