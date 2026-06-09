# GetPolicySDs

- ea: `0x1802aeff0`
- end: `0x1802af6b3`
- name: `GetPolicySDs`
- size: `1731`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1802afc08`

## callees

- `0x180002b10`
- `0x180006330`
- `0x1800067d0`
- `0x180021aa3`
- `0x180181c60`
- `0x1801c4a34`
- `0x1801d2bc8`
- `0x1801e13ec`
- `0x1802aeff0`
- `0x1802af6bc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1802af369`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1802af369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802af373`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802af373`
- `ntdll!RtlAddAccessDeniedAce` at `0x1802af448`
- `ntdll!RtlAddAccessDeniedAce` at `0x1802af448`
- `ntdll!RtlAddAccessAllowedAce` at `0x1802af472`
- `ntdll!RtlAddAccessAllowedAce` at `0x1802af527`
- `ntdll!RtlAddAccessAllowedAce` at `0x1802af472`
- `ntdll!RtlAddAccessAllowedAce` at `0x1802af527`
- `ntdll!RtlNtStatusToDosError` at `0x1802af556`
- `ntdll!RtlNtStatusToDosError` at `0x1802af556`
- `ntdll!RtlLengthSid` at `0x1802af3af`
- `ntdll!RtlLengthSid` at `0x1802af3d0`
- `ntdll!RtlLengthSid` at `0x1802af4b4`
- `ntdll!RtlLengthSid` at `0x1802af3af`
- `ntdll!RtlLengthSid` at `0x1802af3d0`
- `ntdll!RtlLengthSid` at `0x1802af4b4`
- `ntdll!RtlCreateAcl` at `0x1802af410`
- `ntdll!RtlCreateAcl` at `0x1802af4fb`
- `ntdll!RtlCreateAcl` at `0x1802af410`
- `ntdll!RtlCreateAcl` at `0x1802af4fb`

## pseudocode

```c
__int64 __fastcall GetPolicySDs(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, _QWORD *a5)
{
  __int64 v8; // r13
  __int64 v9; // r12
  ULONG v10; // eax
  ULONG v11; // edi
  __int64 v12; // rdx
  __int64 v13; // rcx
  ULONG v14; // eax
  int v15; // r9d
  int v16; // r14d
  int v17; // r9d
  int v18; // r15d
  unsigned int v19; // r12d
  void *v20; // rcx
  __int64 v21; // rax
  ULONG v22; // eax
  int v23; // r14d
  int v24; // r9d
  int v25; // r15d
  unsigned int v26; // r13d
  void *v27; // rcx
  __int64 v28; // rax
  ULONG v29; // eax
  void *v30; // rax
  int v31; // r8d
  int v32; // r9d
  void *v33; // r12
  DWORD LastError; // eax
  __int64 v35; // rbx
  ULONG v36; // r14d
  int v37; // r15d
  __int64 v38; // r14
  ULONG v39; // eax
  ULONG v40; // ebx
  int SecurityDescriptor; // eax
  __int64 v42; // rbx
  PACL v43; // rbx
  __int64 i; // rbx
  ULONG v45; // eax
  struct _ACL *v46; // r14
  __int64 v47; // rbx
  __int64 v48; // r15
  __int64 j; // rbx
  __int64 v50; // rdx
  __int64 k; // rbx
  __int64 v52; // rdx
  __int64 v53; // rdx
  __int64 v54; // rdx
  unsigned int v56; // [rsp+48h] [rbp-41h]
  unsigned int v57; // [rsp+4Ch] [rbp-3Dh]
  int v58; // [rsp+50h] [rbp-39h] BYREF
  int v59; // [rsp+54h] [rbp-35h] BYREF
  int v60; // [rsp+58h] [rbp-31h] BYREF
  int v61; // [rsp+5Ch] [rbp-2Dh] BYREF
  DWORD cbSid; // [rsp+60h] [rbp-29h] BYREF
  __int64 v63; // [rsp+68h] [rbp-21h]
  __int64 v64; // [rsp+70h] [rbp-19h] BYREF
  __int64 v65; // [rsp+78h] [rbp-11h] BYREF
  PACL Acl; // [rsp+80h] [rbp-9h]
  PACL v67; // [rsp+88h] [rbp-1h]
  __int64 v68; // [rsp+90h] [rbp+7h]
  __int64 v69; // [rsp+98h] [rbp+Fh]
  __int64 v70; // [rsp+A0h] [rbp+17h]

  v69 = 0;
  v70 = 0;
  cbSid = 68;
  v57 = 0;
  v56 = 0;
  Acl = 0;
  v67 = 0;
  v68 = THAlloc_(a1, 1, 16, 1, 0, 19137245);
  v8 = v68;
  v63 = THAlloc_(a1, 1, 16, 1, 0, 19137246);
  v9 = v63;
  v10 = DBFindDSName(a2, a3);
  v11 = v10;
  if ( v10 )
  {
    v12 = v10;
    v13 = 19137253;
  }
  else
  {
    v14 = DBLocateServerRelatedObject(a2, 196638);
    v11 = v14;
    if ( v14 )
    {
      v12 = v14;
      v13 = 19137258;
    }
    else
    {
      v64 = 0;
      v59 = 0;
      v58 = 0;
      v16 = 2;
      v11 = DBGetAttValRealloc(a2, 1, 591752, v15, (__int64)&v59, (__int64)&v58, (__int64)&v64);
      v18 = 2;
      if ( !v11 )
      {
        v19 = 0;
        do
        {
          if ( *(_DWORD *)(v64 + 4) )
          {
            v20 = (void *)THAlloc_(a1, 1, *(_DWORD *)(v64 + 4), 1, 0, 19137288);
            v21 = v19++;
            *(_QWORD *)(v8 + 8 * v21) = v20;
            memcpy_0(v20, (const void *)(v64 + 24), *(unsigned int *)(v64 + 4));
            if ( v19 == v16 )
            {
              v16 *= 2;
              v8 = THReAlloc_(a1, v8, 1, 8 * v16, 1, 0, 19137292);
            }
          }
          v22 = DBGetAttValRealloc(a2, v18++, 591752, v17, (__int64)&v59, (__int64)&v58, (__int64)&v64);
          v11 = v22;
        }
        while ( !v22 );
        v57 = v19;
        v9 = v63;
        v68 = v8;
      }
      if ( v11 == 8995 )
      {
        v65 = 0;
        v23 = 2;
        v61 = 0;
        v60 = 0;
        v11 = DBGetAttValRealloc(a2, 1, 591750, v17, (__int64)&v61, (__int64)&v60, (__int64)&v65);
        v25 = 2;
        if ( !v11 )
        {
          v26 = 0;
          do
          {
            if ( *(_DWORD *)(v65 + 4) )
            {
              v27 = (void *)THAlloc_(a1, 1, *(_DWORD *)(v65 + 4), 1, 0, 19137328);
              v28 = v26++;
              *(_QWORD *)(v9 + 8 * v28) = v27;
              memcpy_0(v27, (const void *)(v65 + 24), *(unsigned int *)(v65 + 4));
              if ( v26 == v23 )
              {
                v23 *= 2;
                v9 = THReAlloc_(a1, v9, 1, 8 * v23, 1, 0, 19137332);
              }
            }
            v29 = DBGetAttValRealloc(a2, v25++, 591750, v24, (__int64)&v61, (__int64)&v60, (__int64)&v65);
            v11 = v29;
          }
          while ( !v29 );
          v56 = v26;
          v8 = v68;
          v63 = v9;
        }
        if ( v11 == 8995 )
        {
          v11 = 0;
          goto LABEL_26;
        }
        v13 = 19137341;
      }
      else
      {
        v13 = 19137301;
      }
      v12 = v11;
    }
  }
  DoLogUnhandledError(v13, v12, 1);
LABEL_26:
  v30 = (void *)THAlloc_(a1, 1, cbSid, 1, 0, 19137350);
  v33 = v30;
  if ( v11 )
    goto LABEL_50;
  if ( !CreateWellKnownSid(WinWorldSid, 0, v30, &cbSid) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError )
    {
      DoLogUnhandledError(19137355, LastError, 1);
      goto LABEL_50;
    }
  }
  v35 = 0;
  v36 = 8;
  v37 = 8;
  if ( v56 )
  {
    v38 = v63;
    do
    {
      v39 = RtlLengthSid(*(PSID *)(v38 + 8 * v35));
      v35 = (unsigned int)(v35 + 1);
      v37 += v39 + 8;
    }
    while ( (unsigned int)v35 < v56 );
    v8 = v68;
    v36 = 8;
  }
  v40 = v37 + RtlLengthSid(v33) + 8;
  Acl = (PACL)THAlloc_(a1, 1, v40, 1, 0, 19137379);
  SecurityDescriptor = RtlCreateAcl(Acl, v40, 2u);
  if ( SecurityDescriptor >= 0 )
  {
    v42 = 0;
    if ( v56 )
    {
      while ( SecurityDescriptor >= 0 )
      {
        SecurityDescriptor = RtlAddAccessDeniedAce(Acl, 2u, 0xF07FFu, *(PSID *)(v63 + 8 * v42));
        v42 = (unsigned int)(v42 + 1);
        if ( (unsigned int)v42 >= v56 )
        {
          if ( SecurityDescriptor < 0 )
            break;
          goto LABEL_39;
        }
      }
    }
    else
    {
LABEL_39:
      v43 = Acl;
      SecurityDescriptor = RtlAddAccessAllowedAce(Acl, 2u, 0xF07FFu, v33);
      if ( SecurityDescriptor >= 0 )
      {
        SecurityDescriptor = GetSecurityDescriptor(a1, a3 + 24, v43);
        if ( SecurityDescriptor >= 0 )
        {
          for ( i = 0; (unsigned int)i < v57; v36 += v45 + 8 )
          {
            v45 = RtlLengthSid(*(PSID *)(v8 + 8 * i));
            i = (unsigned int)(i + 1);
          }
          v67 = (PACL)THAlloc_(a1, 1, v36, 1, 0, 19137420);
          SecurityDescriptor = RtlCreateAcl(v67, v36, 2u);
          if ( SecurityDescriptor >= 0 )
          {
            v46 = v67;
            v47 = 0;
            if ( v57 )
            {
              while ( SecurityDescriptor >= 0 )
              {
                SecurityDescriptor = RtlAddAccessAllowedAce(v46, 2u, 0xF07FFu, *(PSID *)(v8 + 8 * v47));
                v47 = (unsigned int)(v47 + 1);
                if ( (unsigned int)v47 >= v57 )
                {
                  if ( SecurityDescriptor < 0 )
                    break;
                  goto LABEL_48;
                }
              }
            }
            else
            {
LABEL_48:
              SecurityDescriptor = GetSecurityDescriptor(a1, a3 + 24, v46);
              if ( SecurityDescriptor >= 0 )
                goto LABEL_50;
            }
          }
        }
      }
    }
  }
  v11 = RtlNtStatusToDosError(SecurityDescriptor);
LABEL_50:
  v48 = v63;
  if ( v63 )
  {
    for ( j = 0; (unsigned int)j < v56; j = (unsigned int)(j + 1) )
    {
      v50 = *(_QWORD *)(v48 + 8 * j);
      if ( v50 )
        THFreeAux(a1, v50, v31, v32, 19137447);
      *(_QWORD *)(v48 + 8 * j) = 0;
    }
    THFreeAux(a1, v48, v31, v32, 19137449);
  }
  if ( v8 )
  {
    for ( k = 0; (unsigned int)k < v57; k = (unsigned int)(k + 1) )
    {
      v52 = *(_QWORD *)(v8 + 8 * k);
      if ( v52 )
        THFreeAux(a1, v52, v31, v32, 19137454);
      *(_QWORD *)(v8 + 8 * k) = 0;
    }
    THFreeAux(a1, v8, v31, v32, 19137456);
  }
  if ( Acl )
    THFreeAux(a1, (_DWORD)Acl, v31, v32, 19137460);
  if ( v67 )
    THFreeAux(a1, (_DWORD)v67, v31, v32, 19137464);
  if ( v11 )
  {
    if ( v69 )
      THFreeAux(a1, v69, v31, v32, 19137473);
    v54 = v70;
    *a4 = 0;
    if ( v54 )
      THFreeAux(a1, v54, v31, v32, 19137477);
    *a5 = 0;
  }
  else
  {
    v53 = v70;
    *a4 = v69;
    *a5 = v53;
  }
  return v11;
}

```

## disassembly

```asm
0x1802aeff0  mov     rax, rsp
0x1802aeff3  mov     [rax+8], rbx
0x1802aeff7  mov     [rax+20h], r9
0x1802aeffb  mov     [rax+18h], r8
0x1802aefff  push    rbp
0x1802af000  push    rsi
0x1802af001  push    rdi
0x1802af002  push    r12
0x1802af004  push    r13
0x1802af006  push    r14
0x1802af008  push    r15
0x1802af00a  lea     rbp, [rax-57h]
0x1802af00e  sub     rsp, 0A0h
0x1802af015  xor     r15d, r15d
0x1802af018  mov     dword ptr [rsp+0D0h+var_A8], 12402DDh
0x1802af020  mov     rdi, r8
0x1802af023  mov     [rbp+4Fh+var_40], r15
0x1802af027  mov     rbx, rdx
0x1802af02a  mov     [rbp+4Fh+var_38], r15
0x1802af02e  mov     rsi, rcx
0x1802af031  mov     [rbp+4Fh+cbSid], 44h ; 'D'
0x1802af038  lea     eax, [r15+1]
0x1802af03c  mov     [rbp+4Fh+var_8C], r15d
0x1802af040  lea     r14d, [r15+10h]
0x1802af044  mov     [rbp+4Fh+var_90], r15d
0x1802af048  mov     r9d, eax
0x1802af04b  mov     [rbp+4Fh+Acl], r15
0x1802af04f  mov     r8d, r14d
0x1802af052  mov     [rbp+4Fh+var_50], r15
0x1802af056  mov     edx, eax
0x1802af058  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x1802af05d  call    THAlloc_
0x1802af062  mov     dword ptr [rsp+0D0h+var_A8], 12402DEh
0x1802af06a  mov     r8d, r14d
0x1802af06d  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x1802af072  mov     rcx, rsi
0x1802af075  lea     r15d, [r14-0Fh]
0x1802af079  mov     [rbp+4Fh+var_48], rax
0x1802af07d  mov     r9d, r15d
0x1802af080  mov     edx, r15d
0x1802af083  mov     r13, rax
0x1802af086  call    THAlloc_
0x1802af08b  mov     rdx, rdi
0x1802af08e  mov     [rbp+4Fh+var_70], rax
0x1802af092  mov     rcx, rbx
0x1802af095  mov     r12, rax
0x1802af098  call    DBFindDSName
0x1802af09d  mov     edi, eax
0x1802af09f  test    eax, eax
0x1802af0a1  jz      short loc_1802AF0AF
0x1802af0a3  mov     edx, eax
0x1802af0a5  mov     ecx, 12402E5h
0x1802af0aa  jmp     loc_1802AF328
0x1802af0af  mov     edx, 3001Eh
0x1802af0b4  mov     rcx, rbx
0x1802af0b7  call    DBLocateServerRelatedObject
0x1802af0bc  mov     edi, eax
0x1802af0be  test    eax, eax
0x1802af0c0  jz      short loc_1802AF0CE
0x1802af0c2  mov     edx, eax
0x1802af0c4  mov     ecx, 12402EAh
0x1802af0c9  jmp     loc_1802AF328
0x1802af0ce  xor     eax, eax
0x1802af0d0  mov     r8d, 90788h
0x1802af0d6  mov     [rbp+4Fh+var_68], rax
0x1802af0da  mov     edx, r15d
0x1802af0dd  mov     [rbp+4Fh+var_84], eax
0x1802af0e0  mov     rcx, rbx
0x1802af0e3  mov     [rbp+4Fh+var_88], eax
0x1802af0e6  lea     r14d, [rax+2]
0x1802af0ea  lea     rax, [rbp+4Fh+var_68]
0x1802af0ee  mov     [rsp+30h], rax
0x1802af0f3  lea     rax, [rbp+4Fh+var_88]
0x1802af0f7  mov     [rsp+0D0h+var_A8], rax
0x1802af0fc  lea     rax, [rbp+4Fh+var_84]
0x1802af100  mov     [rsp+0D0h+var_B0], rax
0x1802af105  call    DBGetAttValRealloc
0x1802af10a  xor     ecx, ecx
0x1802af10c  mov     edi, eax
0x1802af10e  mov     r15d, r14d
0x1802af111  test    eax, eax
0x1802af113  jnz     loc_1802AF1E1
0x1802af119  mov     r12d, ecx
0x1802af11c  mov     rax, [rbp+4Fh+var_68]
0x1802af120  cmp     [rax+4], ecx
0x1802af123  jz      short loc_1802AF19A
0x1802af125  mov     r8d, [rax+4]
0x1802af129  mov     edi, 1
0x1802af12e  mov     dword ptr [rsp+0D0h+var_A8], 1240308h
0x1802af136  mov     r9d, edi
0x1802af139  mov     dword ptr [rsp+0D0h+var_B0], ecx
0x1802af13d  mov     edx, edi
0x1802af13f  mov     rcx, rsi
0x1802af142  call    THAlloc_
0x1802af147  mov     rcx, rax; void *
0x1802af14a  mov     eax, r12d
0x1802af14d  add     r12d, edi
0x1802af150  mov     [r13+rax*8+0], rcx
0x1802af155  mov     rdx, [rbp+4Fh+var_68]
0x1802af159  mov     r8d, [rdx+4]; Size
0x1802af15d  add     rdx, 18h; Src
0x1802af161  call    memcpy_0
0x1802af166  cmp     r12d, r14d
0x1802af169  jnz     short loc_1802AF19A
0x1802af16b  add     r14d, r14d
0x1802af16e  mov     dword ptr [rsp+30h], 124030Ch
0x1802af176  mov     r9d, r14d
0x1802af179  mov     r8d, edi
0x1802af17c  shl     r9, 3
0x1802af180  mov     rdx, r13
0x1802af183  mov     dword ptr [rsp+0D0h+var_A8], 0
0x1802af18b  mov     rcx, rsi
0x1802af18e  mov     dword ptr [rsp+0D0h+var_B0], edi
0x1802af192  call    THReAlloc_
0x1802af197  mov     r13, rax
0x1802af19a  lea     rax, [rbp+4Fh+var_68]
0x1802af19e  mov     r8d, 90788h
0x1802af1a4  mov     [rsp+30h], rax
0x1802af1a9  mov     edx, r15d
0x1802af1ac  lea     rax, [rbp+4Fh+var_88]
0x1802af1b0  mov     rcx, rbx
0x1802af1b3  mov     [rsp+0D0h+var_A8], rax
0x1802af1b8  lea     rax, [rbp+4Fh+var_84]
0x1802af1bc  mov     [rsp+0D0h+var_B0], rax
0x1802af1c1  call    DBGetAttValRealloc
0x1802af1c6  xor     ecx, ecx
0x1802af1c8  inc     r15d
0x1802af1cb  mov     edi, eax
0x1802af1cd  test    eax, eax
0x1802af1cf  jz      loc_1802AF11C
0x1802af1d5  mov     [rbp+4Fh+var_8C], r12d
0x1802af1d9  mov     r12, [rbp+4Fh+var_70]
0x1802af1dd  mov     [rbp+4Fh+var_48], r13
0x1802af1e1  cmp     edi, 2323h
0x1802af1e7  jnz     loc_1802AF31B
0x1802af1ed  lea     rax, [rbp+4Fh+var_60]
0x1802af1f1  mov     [rbp+4Fh+var_60], rcx
0x1802af1f5  mov     [rsp+30h], rax
0x1802af1fa  mov     r14d, 2
0x1802af200  lea     rax, [rbp+4Fh+var_80]
0x1802af204  mov     [rbp+4Fh+var_7C], ecx
0x1802af207  mov     [rsp+0D0h+var_A8], rax
0x1802af20c  mov     r8d, 90786h
0x1802af212  lea     rax, [rbp+4Fh+var_7C]
0x1802af216  mov     [rbp+4Fh+var_80], ecx
0x1802af219  lea     edx, [r14-1]
0x1802af21d  mov     [rsp+0D0h+var_B0], rax
0x1802af222  mov     rcx, rbx
0x1802af225  call    DBGetAttValRealloc
0x1802af22a  mov     edi, eax
0x1802af22c  mov     r15d, r14d
0x1802af22f  test    eax, eax
0x1802af231  jnz     loc_1802AF302
0x1802af237  mov     r13d, [rbp+4Fh+var_90]
0x1802af23b  mov     rax, [rbp+4Fh+var_60]
0x1802af23f  cmp     dword ptr [rax+4], 0
0x1802af243  jz      short loc_1802AF2BD
0x1802af245  mov     r8d, [rax+4]
0x1802af249  mov     edi, 1
0x1802af24e  mov     r9d, edi
0x1802af251  mov     dword ptr [rsp+0D0h+var_A8], 1240330h
0x1802af259  mov     edx, edi
0x1802af25b  mov     dword ptr [rsp+0D0h+var_B0], 0
0x1802af263  mov     rcx, rsi
0x1802af266  call    THAlloc_
0x1802af26b  mov     rcx, rax; void *
0x1802af26e  mov     eax, r13d
0x1802af271  add     r13d, edi
0x1802af274  mov     [r12+rax*8], rcx
0x1802af278  mov     rdx, [rbp+4Fh+var_60]
0x1802af27c  mov     r8d, [rdx+4]; Size
0x1802af280  add     rdx, 18h; Src
0x1802af284  call    memcpy_0
0x1802af289  cmp     r13d, r14d
0x1802af28c  jnz     short loc_1802AF2BD
0x1802af28e  add     r14d, r14d
0x1802af291  mov     dword ptr [rsp+30h], 1240334h
0x1802af299  mov     r9d, r14d
0x1802af29c  mov     r8d, edi
0x1802af29f  shl     r9, 3
0x1802af2a3  mov     rdx, r12
0x1802af2a6  mov     dword ptr [rsp+0D0h+var_A8], 0
0x1802af2ae  mov     rcx, rsi
0x1802af2b1  mov     dword ptr [rsp+0D0h+var_B0], edi
0x1802af2b5  call    THReAlloc_
0x1802af2ba  mov     r12, rax
0x1802af2bd  lea     rax, [rbp+4Fh+var_60]
0x1802af2c1  mov     r8d, 90786h
0x1802af2c7  mov     [rsp+30h], rax
0x1802af2cc  mov     edx, r15d
0x1802af2cf  lea     rax, [rbp+4Fh+var_80]
0x1802af2d3  mov     rcx, rbx
0x1802af2d6  mov     [rsp+0D0h+var_A8], rax
0x1802af2db  lea     rax, [rbp+4Fh+var_7C]
0x1802af2df  mov     [rsp+0D0h+var_B0], rax
0x1802af2e4  call    DBGetAttValRealloc
0x1802af2e9  inc     r15d
0x1802af2ec  mov     edi, eax
0x1802af2ee  test    eax, eax
0x1802af2f0  jz      loc_1802AF23B
0x1802af2f6  mov     [rbp+4Fh+var_90], r13d
0x1802af2fa  mov     r13, [rbp+4Fh+var_48]
0x1802af2fe  mov     [rbp+4Fh+var_70], r12
0x1802af302  mov     r15d, 1
0x1802af308  cmp     edi, 2323h
0x1802af30e  jnz     short loc_1802AF314
0x1802af310  xor     edi, edi
0x1802af312  jmp     short loc_1802AF330
0x1802af314  mov     ecx, 124033Dh
0x1802af319  jmp     short loc_1802AF326
0x1802af31b  mov     r15d, 1
0x1802af321  mov     ecx, 1240315h
0x1802af326  mov     edx, edi
0x1802af328  mov     r8d, r15d
0x1802af32b  call    DoLogUnhandledError
0x1802af330  mov     r8d, [rbp+4Fh+cbSid]
0x1802af334  mov     r9d, r15d
0x1802af337  mov     dword ptr [rsp+0D0h+var_A8], 1240346h
0x1802af33f  mov     rdx, r15
0x1802af342  mov     rcx, rsi
0x1802af345  mov     dword ptr [rsp+0D0h+var_B0], 0
0x1802af34d  call    THAlloc_
0x1802af352  mov     r12, rax
0x1802af355  test    edi, edi
0x1802af357  jnz     loc_1802AF55E
0x1802af35d  lea     r9, [rbp+4Fh+cbSid]; cbSid
0x1802af361  mov     r8, rax; pSid
0x1802af364  xor     edx, edx; DomainSid
0x1802af366  mov     ecx, r15d; WellKnownSidType
0x1802af369  call    cs:__imp_CreateWellKnownSid
0x1802af36f  test    eax, eax
0x1802af371  jnz     short loc_1802AF393
0x1802af373  call    cs:__imp_GetLastError
0x1802af379  mov     edi, eax
0x1802af37b  test    eax, eax
0x1802af37d  jz      short loc_1802AF393
0x1802af37f  mov     r8d, r15d
0x1802af382  mov     edx, eax
0x1802af384  mov     ecx, 124034Bh
0x1802af389  call    DoLogUnhandledError
0x1802af38e  jmp     loc_1802AF55E
0x1802af393  xor     ebx, ebx
0x1802af395  mov     r14d, 8
0x1802af39b  mov     r15d, r14d
0x1802af39e  cmp     [rbp+4Fh+var_90], ebx
0x1802af3a1  jbe     short loc_1802AF3CD
0x1802af3a3  mov     r14, [rbp+4Fh+var_70]
0x1802af3a7  mov     r13d, [rbp+4Fh+var_90]
0x1802af3ab  mov     rcx, [r14+rbx*8]; Sid
0x1802af3af  call    cs:__imp_RtlLengthSid
0x1802af3b5  add     r15d, 8
0x1802af3b9  inc     ebx
0x1802af3bb  add     r15d, eax
0x1802af3be  cmp     ebx, r13d
0x1802af3c1  jb      short loc_1802AF3AB
0x1802af3c3  mov     r13, [rbp+4Fh+var_48]
0x1802af3c7  mov     r14d, 8
0x1802af3cd  mov     rcx, r12; Sid
0x1802af3d0  call    cs:__imp_RtlLengthSid
0x1802af3d6  mov     dword ptr [rsp+0D0h+var_A8], 1240363h
0x1802af3de  mov     rcx, rsi
0x1802af3e1  mov     dword ptr [rsp+0D0h+var_B0], 0
0x1802af3e9  lea     ebx, [rax+8]
0x1802af3ec  mov     eax, 1
0x1802af3f1  add     ebx, r15d
0x1802af3f4  mov     r9d, eax
0x1802af3f7  mov     r8d, ebx
0x1802af3fa  mov     edx, eax
0x1802af3fc  call    THAlloc_
0x1802af401  mov     r8d, 2; AclRevision
0x1802af407  mov     [rbp+4Fh+Acl], rax
0x1802af40b  mov     edx, ebx; AclSize
0x1802af40d  mov     rcx, rax; Acl
0x1802af410  call    cs:__imp_RtlCreateAcl
0x1802af416  test    eax, eax
0x1802af418  js      loc_1802AF554
0x1802af41e  mov     r15d, [rbp+4Fh+var_90]
0x1802af422  xor     ebx, ebx
0x1802af424  test    r15d, r15d
0x1802af427  jz      short loc_1802AF45D
0x1802af429  test    eax, eax
0x1802af42b  js      loc_1802AF554
0x1802af431  mov     rax, [rbp+4Fh+var_70]
0x1802af435  mov     edx, 2; Revision
0x1802af43a  mov     rcx, [rbp+4Fh+Acl]; Acl
0x1802af43e  mov     r8d, 0F07FFh; AccessMask
0x1802af444  mov     r9, [rax+rbx*8]; Sid
0x1802af448  call    cs:__imp_RtlAddAccessDeniedAce
0x1802af44e  inc     ebx
0x1802af450  cmp     ebx, r15d
0x1802af453  jb      short loc_1802AF429
0x1802af455  test    eax, eax
0x1802af457  js      loc_1802AF554
0x1802af45d  mov     rbx, [rbp+4Fh+Acl]
0x1802af461  mov     r9, r12; Sid
0x1802af464  mov     rcx, rbx; Acl
0x1802af467  mov     edx, 2; Revision
0x1802af46c  mov     r8d, 0F07FFh; AccessMask
0x1802af472  call    cs:__imp_RtlAddAccessAllowedAce
0x1802af478  test    eax, eax
  ... truncated ...
```
