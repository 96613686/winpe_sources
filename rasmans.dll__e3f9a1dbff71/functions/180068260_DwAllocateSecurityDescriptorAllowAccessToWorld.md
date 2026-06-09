# DwAllocateSecurityDescriptorAllowAccessToWorld

- ea: `0x180068260`
- end: `0x18006876e`
- name: `DwAllocateSecurityDescriptorAllowAccessToWorld`
- size: `1294`
- prototype: `__int64 __fastcall(_QWORD *, struct _ACL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006a988`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180068260`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006845c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800684ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800685be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068658`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006845c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800684ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800685be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068658`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800683d2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800683d2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180068607`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180068607`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800684b0`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800684b0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18006864e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18006864e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18006855e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18006855e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180068452`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180068452`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800686dd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800e7bd1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800686dd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800e7bd1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18006836c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18006836c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800685b4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800685b4`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800683e4`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180068500`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800683e4`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180068500`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800686ae`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800686c3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800e7bae`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800e7bc1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800686ae`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800686c3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800e7bae`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800e7bc1`

## pseudocode

```c
__int64 __fastcall DwAllocateSecurityDescriptorAllowAccessToWorld(_QWORD *a1, struct _ACL **a2)
{
  struct _ACL **v2; // r15
  struct _LIST_ENTRY *v4; // rcx
  void *v5; // r14
  struct _ACL *v6; // r12
  DWORD LastError; // ebx
  struct _LIST_ENTRY *v8; // rcx
  DWORD v9; // r15d
  struct _ACL *v10; // rax
  __int64 v11; // r9
  __int64 v12; // rdx
  HGLOBAL v13; // rax
  PSID pSid; // [rsp+70h] [rbp-68h] BYREF
  HGLOBAL v17; // [rsp+78h] [rbp-60h]
  struct _ACL *v18; // [rsp+80h] [rbp-58h]
  _QWORD *v19; // [rsp+88h] [rbp-50h]
  struct _ACL **v20; // [rsp+90h] [rbp-48h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+98h] [rbp-40h] BYREF

  v2 = a2;
  v19 = a1;
  v20 = a2;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 17, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  pSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  if ( a1 && v2 )
  {
    v5 = 0;
    v17 = 0;
    v6 = 0;
    v18 = 0;
    LastError = 0;
    *a1 = 0;
    *v2 = 0;
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 19, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LastError);
        v8 = WPP_GLOBAL_Control;
      }
LABEL_56:
      if ( LastError )
      {
        if ( v5 )
        {
          GlobalFree(v5);
          v8 = WPP_GLOBAL_Control;
        }
        if ( !v6 )
          goto LABEL_63;
        GlobalFree(v6);
      }
      else
      {
        *a1 = v5;
        *v2 = v6;
      }
      v8 = WPP_GLOBAL_Control;
LABEL_63:
      if ( pSid )
      {
        FreeSid(pSid);
        v8 = WPP_GLOBAL_Control;
      }
      if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v8[1].Blink) < 0 && BYTE1(v8[1].Blink) >= 6u )
        WPP_SF_d(v8[1].Flink, 28, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LastError);
      return LastError;
    }
    v9 = GetLengthSid(pSid) + 20;
    v10 = (struct _ACL *)GlobalAlloc(0x40u, v9);
    v6 = v10;
    v18 = v10;
    if ( !v10 )
    {
      v11 = 8;
      LastError = 8;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_55;
      }
      v12 = 20;
      goto LABEL_17;
    }
    if ( InitializeAcl(v10, v9, 2u) )
    {
      if ( AddAccessAllowedAce(v6, 2u, 0x13FFFFu, pSid) )
      {
        v13 = GlobalAlloc(0x40u, 0x28u);
        v5 = v13;
        v17 = v13;
        if ( !v13 )
        {
          v11 = 8;
          LastError = 8;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_55;
          }
          v12 = 23;
          goto LABEL_17;
        }
        if ( InitializeSecurityDescriptor(v13, 1u) )
        {
          if ( SetSecurityDescriptorDacl(v5, 1, v6, 0) )
          {
            if ( SetSecurityDescriptorOwner(v5, 0, 0) )
            {
              if ( SetSecurityDescriptorGroup(v5, 0, 0) )
                goto LABEL_54;
              LastError = GetLastError();
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              {
                goto LABEL_55;
              }
              v12 = 27;
            }
            else
            {
              LastError = GetLastError();
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              {
                goto LABEL_55;
              }
              v12 = 26;
            }
          }
          else
          {
            LastError = GetLastError();
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_55;
            }
            v12 = 25;
          }
        }
        else
        {
          LastError = GetLastError();
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_55;
          }
          v12 = 24;
        }
      }
      else
      {
        LastError = GetLastError();
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_55;
        }
        v12 = 22;
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_55;
      }
      v12 = 21;
    }
    v11 = LastError;
LABEL_17:
    WPP_SF_d(v8[1].Flink, v12, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v11);
LABEL_54:
    v8 = WPP_GLOBAL_Control;
LABEL_55:
    v2 = a2;
    goto LABEL_56;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
    WPP_SF_d(v4[1].Flink, 18, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 87);
  return 87;
}

```

## disassembly

```asm
0x180068260  mov     [rsp+arg_10], rbx
0x180068265  push    rsi
0x180068266  push    r12
0x180068268  push    r13
0x18006826a  push    r14
0x18006826c  push    r15
0x18006826e  sub     rsp, 0B0h
0x180068275  mov     rax, cs:__security_cookie
0x18006827c  xor     rax, rsp
0x18006827f  mov     [rsp+0D8h+var_38], rax
0x180068287  mov     r15, rdx
0x18006828a  mov     [rsp+0D8h+var_78], rdx
0x18006828f  mov     r13, rcx
0x180068292  mov     [rsp+0D8h+var_50], rcx
0x18006829a  mov     [rsp+0D8h+var_48], rdx
0x1800682a2  lea     rax, WPP_GLOBAL_Control
0x1800682a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800682b0  cmp     rcx, rax
0x1800682b3  jz      short loc_1800682E9
0x1800682b5  test    byte ptr [rcx+1Ch], 80h
0x1800682b9  jz      short loc_1800682E9
0x1800682bb  lea     rsi, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800682c2  cmp     byte ptr [rcx+19h], 6
0x1800682c6  jb      short loc_1800682F0
0x1800682c8  mov     edx, 11h
0x1800682cd  mov     r8, rsi
0x1800682d0  mov     rcx, [rcx+10h]
0x1800682d4  call    WPP_SF_
0x1800682d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800682e0  lea     rax, WPP_GLOBAL_Control
0x1800682e7  jmp     short loc_1800682F0
0x1800682e9  lea     rsi, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800682f0  xor     edx, edx
0x1800682f2  mov     [rsp+0D8h+var_68], rdx
0x1800682f7  mov     dword ptr [rsp+0D8h+pIdentifierAuthority.Value], edx
0x1800682fe  mov     word ptr [rsp+0D8h+pIdentifierAuthority.Value+4], 100h
0x180068308  test    r13, r13
0x18006830b  jz      loc_18006871A
0x180068311  test    r15, r15
0x180068314  jz      loc_18006871A
0x18006831a  mov     r14d, edx
0x18006831d  mov     [rsp+0D8h+var_60], rdx
0x180068322  mov     r12d, edx
0x180068325  mov     [rsp+0D8h+var_58], rdx
0x18006832d  mov     ebx, edx
0x18006832f  mov     [rsp+0D8h+var_70], edx
0x180068333  mov     [r13+0], rdx
0x180068337  mov     [r15], rdx
0x18006833a  lea     rax, [rsp+0D8h+var_68]
0x18006833f  mov     [rsp+0D8h+pSid], rax; pSid
0x180068344  mov     [rsp+0D8h+nSubAuthority7], edx; nSubAuthority7
0x180068348  mov     [rsp+0D8h+nSubAuthority6], edx; nSubAuthority6
0x18006834c  mov     [rsp+0D8h+nSubAuthority5], edx; nSubAuthority5
0x180068350  mov     [rsp+0D8h+nSubAuthority4], edx; nSubAuthority4
0x180068354  mov     [rsp+0D8h+nSubAuthority3], edx; nSubAuthority3
0x180068358  mov     [rsp+0D8h+nSubAuthority2], edx; nSubAuthority2
0x18006835c  xor     r9d, r9d; nSubAuthority1
0x18006835f  xor     r8d, r8d; nSubAuthority0
0x180068362  mov     dl, 1; nSubAuthorityCount
0x180068364  lea     rcx, [rsp+0D8h+pIdentifierAuthority]; pIdentifierAuthority
0x18006836c  call    cs:__imp_AllocateAndInitializeSid
0x180068372  test    eax, eax
0x180068374  jnz     short loc_1800683CD
0x180068376  call    cs:__imp_GetLastError
0x18006837c  mov     ebx, eax
0x18006837e  mov     [rsp+0D8h+var_70], eax
0x180068382  mov     rcx, cs:WPP_GLOBAL_Control
0x180068389  lea     rax, WPP_GLOBAL_Control
0x180068390  cmp     rcx, rax
0x180068393  jz      loc_180068699
0x180068399  test    byte ptr [rcx+1Ch], 80h
0x18006839d  jz      loc_180068699
0x1800683a3  cmp     byte ptr [rcx+19h], 2
0x1800683a7  jb      loc_180068699
0x1800683ad  lea     edx, [r12+13h]
0x1800683b2  mov     r9d, ebx
0x1800683b5  mov     r8, rsi
0x1800683b8  mov     rcx, [rcx+10h]
0x1800683bc  call    WPP_SF_d
0x1800683c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800683c8  jmp     loc_180068699
0x1800683cd  mov     rcx, [rsp+0D8h+var_68]; pSid
0x1800683d2  call    cs:__imp_GetLengthSid
0x1800683d8  lea     r15d, [rax+14h]
0x1800683dc  mov     edx, r15d; dwBytes
0x1800683df  mov     ecx, 40h ; '@'; uFlags
0x1800683e4  call    cs:__imp_GlobalAlloc
0x1800683ea  mov     r12, rax
0x1800683ed  mov     [rsp+0D8h+var_58], rax
0x1800683f5  test    rax, rax
0x1800683f8  jnz     short loc_180068446
0x1800683fa  lea     r9d, [rax+8]
0x1800683fe  mov     ebx, r9d
0x180068401  mov     [rsp+0D8h+var_70], ebx
0x180068405  mov     rcx, cs:WPP_GLOBAL_Control
0x18006840c  lea     rax, WPP_GLOBAL_Control
0x180068413  cmp     rcx, rax
0x180068416  jz      loc_180068694
0x18006841c  test    byte ptr [rcx+1Ch], 80h
0x180068420  jz      loc_180068694
0x180068426  cmp     byte ptr [rcx+19h], 2
0x18006842a  jb      loc_180068694
0x180068430  lea     edx, [r12+14h]
0x180068435  mov     r8, rsi
0x180068438  mov     rcx, [rcx+10h]
0x18006843c  call    WPP_SF_d
0x180068441  jmp     loc_18006868D
0x180068446  mov     r8d, 2; dwAclRevision
0x18006844c  mov     edx, r15d; nAclLength
0x18006844f  mov     rcx, r12; pAcl
0x180068452  call    cs:__imp_InitializeAcl
0x180068458  test    eax, eax
0x18006845a  jnz     short loc_18006849D
0x18006845c  call    cs:__imp_GetLastError
0x180068462  mov     ebx, eax
0x180068464  mov     [rsp+0D8h+var_70], eax
0x180068468  mov     rcx, cs:WPP_GLOBAL_Control
0x18006846f  lea     rax, WPP_GLOBAL_Control
0x180068476  cmp     rcx, rax
0x180068479  jz      loc_180068694
0x18006847f  test    byte ptr [rcx+1Ch], 80h
0x180068483  jz      loc_180068694
0x180068489  cmp     byte ptr [rcx+19h], 2
0x18006848d  jb      loc_180068694
0x180068493  mov     edx, 15h
0x180068498  mov     r9d, ebx
0x18006849b  jmp     short loc_180068435
0x18006849d  mov     r9, [rsp+0D8h+var_68]; pSid
0x1800684a2  mov     edx, 2; dwAceRevision
0x1800684a7  mov     r8d, 13FFFFh; AccessMask
0x1800684ad  mov     rcx, r12; pAcl
0x1800684b0  call    cs:__imp_AddAccessAllowedAce
0x1800684b6  test    eax, eax
0x1800684b8  jnz     short loc_1800684F8
0x1800684ba  call    cs:__imp_GetLastError
0x1800684c0  mov     ebx, eax
0x1800684c2  mov     [rsp+0D8h+var_70], eax
0x1800684c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800684cd  lea     rax, WPP_GLOBAL_Control
0x1800684d4  cmp     rcx, rax
0x1800684d7  jz      loc_180068694
0x1800684dd  test    byte ptr [rcx+1Ch], 80h
0x1800684e1  jz      loc_180068694
0x1800684e7  cmp     byte ptr [rcx+19h], 2
0x1800684eb  jb      loc_180068694
0x1800684f1  mov     edx, 16h
0x1800684f6  jmp     short loc_180068498
0x1800684f8  mov     edx, 28h ; '('; dwBytes
0x1800684fd  lea     ecx, [rdx+18h]; uFlags
0x180068500  call    cs:__imp_GlobalAlloc
0x180068506  mov     r14, rax
0x180068509  mov     [rsp+0D8h+var_60], rax
0x18006850e  test    rax, rax
0x180068511  jnz     short loc_180068552
0x180068513  lea     r9d, [rax+8]
0x180068517  mov     ebx, r9d
0x18006851a  mov     [rsp+0D8h+var_70], ebx
0x18006851e  mov     rcx, cs:WPP_GLOBAL_Control
0x180068525  lea     rax, WPP_GLOBAL_Control
0x18006852c  cmp     rcx, rax
0x18006852f  jz      loc_180068694
0x180068535  test    byte ptr [rcx+1Ch], 80h
0x180068539  jz      loc_180068694
0x18006853f  cmp     byte ptr [rcx+19h], 2
0x180068543  jb      loc_180068694
0x180068549  lea     edx, [r14+17h]
0x18006854d  jmp     loc_180068435
0x180068552  mov     r15d, 1
0x180068558  mov     edx, r15d; dwRevision
0x18006855b  mov     rcx, r14; pSecurityDescriptor
0x18006855e  call    cs:__imp_InitializeSecurityDescriptor
0x180068564  test    eax, eax
0x180068566  jnz     short loc_1800685A8
0x180068568  call    cs:__imp_GetLastError
0x18006856e  mov     ebx, eax
0x180068570  mov     [rsp+0D8h+var_70], eax
0x180068574  mov     rcx, cs:WPP_GLOBAL_Control
0x18006857b  lea     rax, WPP_GLOBAL_Control
0x180068582  cmp     rcx, rax
0x180068585  jz      loc_180068694
0x18006858b  test    byte ptr [rcx+1Ch], 80h
0x18006858f  jz      loc_180068694
0x180068595  cmp     byte ptr [rcx+19h], 2
0x180068599  jb      loc_180068694
0x18006859f  lea     edx, [r15+17h]
0x1800685a3  jmp     loc_180068498
0x1800685a8  xor     r9d, r9d; bDaclDefaulted
0x1800685ab  mov     r8, r12; pDacl
0x1800685ae  mov     edx, r15d; bDaclPresent
0x1800685b1  mov     rcx, r14; pSecurityDescriptor
0x1800685b4  call    cs:__imp_SetSecurityDescriptorDacl
0x1800685ba  test    eax, eax
0x1800685bc  jnz     short loc_1800685FF
0x1800685be  call    cs:__imp_GetLastError
0x1800685c4  mov     ebx, eax
0x1800685c6  mov     [rsp+0D8h+var_70], eax
0x1800685ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800685d1  lea     rax, WPP_GLOBAL_Control
0x1800685d8  cmp     rcx, rax
0x1800685db  jz      loc_180068694
0x1800685e1  test    byte ptr [rcx+1Ch], 80h
0x1800685e5  jz      loc_180068694
0x1800685eb  cmp     byte ptr [rcx+19h], 2
0x1800685ef  jb      loc_180068694
0x1800685f5  mov     edx, 19h
0x1800685fa  jmp     loc_180068498
0x1800685ff  xor     r8d, r8d; bOwnerDefaulted
0x180068602  xor     edx, edx; pOwner
0x180068604  mov     rcx, r14; pSecurityDescriptor
0x180068607  call    cs:__imp_SetSecurityDescriptorOwner
0x18006860d  test    eax, eax
0x18006860f  jnz     short loc_180068646
0x180068611  call    cs:__imp_GetLastError
0x180068617  mov     ebx, eax
0x180068619  mov     [rsp+0D8h+var_70], eax
0x18006861d  mov     rcx, cs:WPP_GLOBAL_Control
0x180068624  lea     rax, WPP_GLOBAL_Control
0x18006862b  cmp     rcx, rax
0x18006862e  jz      short loc_180068694
0x180068630  test    byte ptr [rcx+1Ch], 80h
0x180068634  jz      short loc_180068694
0x180068636  cmp     byte ptr [rcx+19h], 2
0x18006863a  jb      short loc_180068694
0x18006863c  mov     edx, 1Ah
0x180068641  jmp     loc_180068498
0x180068646  xor     r8d, r8d; bGroupDefaulted
0x180068649  xor     edx, edx; pGroup
0x18006864b  mov     rcx, r14; pSecurityDescriptor
0x18006864e  call    cs:__imp_SetSecurityDescriptorGroup
0x180068654  test    eax, eax
0x180068656  jnz     short loc_18006868D
0x180068658  call    cs:__imp_GetLastError
0x18006865e  mov     ebx, eax
0x180068660  mov     [rsp+0D8h+var_70], eax
0x180068664  mov     rcx, cs:WPP_GLOBAL_Control
0x18006866b  lea     rax, WPP_GLOBAL_Control
0x180068672  cmp     rcx, rax
0x180068675  jz      short loc_180068694
0x180068677  test    byte ptr [rcx+1Ch], 80h
0x18006867b  jz      short loc_180068694
0x18006867d  cmp     byte ptr [rcx+19h], 2
0x180068681  jb      short loc_180068694
0x180068683  mov     edx, 1Bh
0x180068688  jmp     loc_180068498
0x18006868d  mov     rcx, cs:WPP_GLOBAL_Control
0x180068694  mov     r15, [rsp+0D8h+var_78]
0x180068699  test    ebx, ebx
0x18006869b  jnz     short loc_1800686A6
0x18006869d  mov     [r13+0], r14
0x1800686a1  mov     [r15], r12
0x1800686a4  jmp     short loc_1800686C9
0x1800686a6  test    r14, r14
0x1800686a9  jz      short loc_1800686BB
0x1800686ab  mov     rcx, r14; hMem
0x1800686ae  call    cs:__imp_GlobalFree
0x1800686b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800686bb  test    r12, r12
0x1800686be  jz      short loc_1800686D0
0x1800686c0  mov     rcx, r12; hMem
0x1800686c3  call    cs:__imp_GlobalFree
0x1800686c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800686d0  mov     rax, [rsp+0D8h+var_68]
0x1800686d5  test    rax, rax
0x1800686d8  jz      short loc_1800686EA
0x1800686da  mov     rcx, rax; pSid
0x1800686dd  call    cs:__imp_FreeSid
0x1800686e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800686ea  lea     rax, WPP_GLOBAL_Control
0x1800686f1  cmp     rcx, rax
0x1800686f4  jz      short loc_180068716
0x1800686f6  test    byte ptr [rcx+1Ch], 80h
0x1800686fa  jz      short loc_180068716
0x1800686fc  cmp     byte ptr [rcx+19h], 6
0x180068700  jb      short loc_180068716
0x180068702  mov     edx, 1Ch
0x180068707  mov     r9d, ebx
0x18006870a  mov     r8, rsi
0x18006870d  mov     rcx, [rcx+10h]
0x180068711  call    WPP_SF_d
0x180068716  mov     eax, ebx
0x180068718  jmp     short loc_180068745
0x18006871a  cmp     rcx, rax
0x18006871d  jz      short loc_180068740
0x18006871f  test    byte ptr [rcx+1Ch], 80h
0x180068723  jz      short loc_180068740
0x180068725  cmp     byte ptr [rcx+19h], 6
0x180068729  jb      short loc_180068740
0x18006872b  mov     edx, 12h
0x180068730  lea     r9d, [rdx+45h]
0x180068734  mov     r8, rsi
0x180068737  mov     rcx, [rcx+10h]
0x18006873b  call    WPP_SF_d
0x180068740  mov     eax, 57h ; 'W'
0x180068745  mov     rcx, [rsp+0D8h+var_38]
0x18006874d  xor     rcx, rsp; StackCookie
0x180068750  call    __security_check_cookie
0x180068755  mov     rbx, [rsp+0D8h+arg_10]
0x18006875d  add     rsp, 0B0h
0x180068764  pop     r15
0x180068766  pop     r14
  ... truncated ...
```
