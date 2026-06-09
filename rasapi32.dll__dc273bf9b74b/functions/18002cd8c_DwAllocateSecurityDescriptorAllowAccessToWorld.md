# DwAllocateSecurityDescriptorAllowAccessToWorld

- ea: `0x18002cd8c`
- end: `0x18002d2f8`
- name: `DwAllocateSecurityDescriptorAllowAccessToWorld`
- size: `1388`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c8a8`

## callees

- `0x18002cd8c`
- `0x18004e580`
- `0x18004e984`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002ce8d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002cee6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002ce8d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002cee6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d281`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d29a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800deec1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800deed4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d281`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d29a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800deec1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800deed4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002ced1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002ced1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002d1ec`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800deee4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002d1ec`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800deee4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002ce7b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002ce7b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18002cf4f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18002cf4f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002ceb1`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002ceb1`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002cf09`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002cf09`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002ce68`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002ce68`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18002cf39`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18002cf39`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002cf23`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002cf23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cfc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d04b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d0cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d10b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d14c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d18d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cfc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d04b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d0cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d10b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d14c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d18d`

## pseudocode

```c
__int64 __fastcall DwAllocateSecurityDescriptorAllowAccessToWorld(_QWORD *a1, struct _ACL **a2)
{
  struct _ACL **v2; // r15
  char *v4; // rcx
  void *v5; // r14
  struct _ACL *v6; // r12
  DWORD LastError; // ebx
  DWORD v8; // r15d
  struct _ACL *v9; // rax
  HGLOBAL v10; // rax
  char *v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rdx
  PSID pSid; // [rsp+70h] [rbp-68h] BYREF
  HGLOBAL v17; // [rsp+78h] [rbp-60h]
  struct _ACL *v18; // [rsp+80h] [rbp-58h]
  _QWORD *v19; // [rsp+88h] [rbp-50h]
  struct _ACL **v20; // [rsp+90h] [rbp-48h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+98h] [rbp-40h] BYREF

  v2 = a2;
  v19 = a1;
  v20 = a2;
  v4 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    v4 = (char *)WPP_GLOBAL_Control;
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
      v11 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LastError);
        v11 = (char *)WPP_GLOBAL_Control;
      }
LABEL_53:
      if ( LastError )
      {
        if ( v5 )
        {
          GlobalFree(v5);
          v11 = (char *)WPP_GLOBAL_Control;
        }
        if ( !v6 )
          goto LABEL_56;
        GlobalFree(v6);
      }
      else
      {
        *a1 = v5;
        *v2 = v6;
      }
      v11 = (char *)WPP_GLOBAL_Control;
LABEL_56:
      if ( pSid )
      {
        FreeSid(pSid);
        v11 = (char *)WPP_GLOBAL_Control;
      }
      if ( v11 != (char *)&WPP_GLOBAL_Control && v11[28] < 0 && (unsigned __int8)v11[25] >= 6u )
        WPP_SF_d(*((_QWORD *)v11 + 2), 28, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LastError);
      return LastError;
    }
    v8 = GetLengthSid(pSid) + 20;
    v9 = (struct _ACL *)GlobalAlloc(0x40u, v8);
    v6 = v9;
    v18 = v9;
    if ( v9 )
    {
      if ( InitializeAcl(v9, v8, 2u) )
      {
        if ( AddAccessAllowedAce(v6, 2u, 0x13FFFFu, pSid) )
        {
          v10 = GlobalAlloc(0x40u, 0x28u);
          v5 = v10;
          v17 = v10;
          if ( !v10 )
          {
            v12 = 8;
            LastError = 8;
            v11 = (char *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || *((char *)WPP_GLOBAL_Control + 28) >= 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_15;
            }
            v13 = 23;
            goto LABEL_28;
          }
          if ( InitializeSecurityDescriptor(v10, 1u) )
          {
            if ( SetSecurityDescriptorDacl(v5, 1, v6, 0) )
            {
              if ( SetSecurityDescriptorOwner(v5, 0, 0) )
              {
                if ( SetSecurityDescriptorGroup(v5, 0, 0) )
                {
LABEL_13:
                  v11 = (char *)WPP_GLOBAL_Control;
LABEL_15:
                  v2 = a2;
                  goto LABEL_53;
                }
                LastError = GetLastError();
                v11 = (char *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || *((char *)WPP_GLOBAL_Control + 28) >= 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_15;
                }
                v13 = 27;
              }
              else
              {
                LastError = GetLastError();
                v11 = (char *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || *((char *)WPP_GLOBAL_Control + 28) >= 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_15;
                }
                v13 = 26;
              }
            }
            else
            {
              LastError = GetLastError();
              v11 = (char *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || *((char *)WPP_GLOBAL_Control + 28) >= 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_15;
              }
              v13 = 25;
            }
          }
          else
          {
            LastError = GetLastError();
            v11 = (char *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || *((char *)WPP_GLOBAL_Control + 28) >= 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_15;
            }
            v13 = 24;
          }
        }
        else
        {
          LastError = GetLastError();
          v11 = (char *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || *((char *)WPP_GLOBAL_Control + 28) >= 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_15;
          }
          v13 = 22;
        }
      }
      else
      {
        LastError = GetLastError();
        v11 = (char *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || *((char *)WPP_GLOBAL_Control + 28) >= 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_15;
        }
        v13 = 21;
      }
      v12 = LastError;
    }
    else
    {
      v12 = 8;
      LastError = 8;
      v11 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_15;
      }
      v13 = 20;
    }
LABEL_28:
    WPP_SF_d(*((_QWORD *)v11 + 2), v13, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v12);
    goto LABEL_13;
  }
  if ( v4 != (char *)&WPP_GLOBAL_Control && v4[28] < 0 && (unsigned __int8)v4[25] >= 6u )
    WPP_SF_d(*((_QWORD *)v4 + 2), 18, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 87);
  return 87;
}

```

## disassembly

```asm
0x18002cd8c  mov     [rsp+arg_10], rbx
0x18002cd91  push    rsi
0x18002cd92  push    r12
0x18002cd94  push    r13
0x18002cd96  push    r14
0x18002cd98  push    r15
0x18002cd9a  sub     rsp, 0B0h
0x18002cda1  mov     rax, cs:__security_cookie
0x18002cda8  xor     rax, rsp
0x18002cdab  mov     [rsp+0D8h+var_38], rax
0x18002cdb3  mov     r15, rdx
0x18002cdb6  mov     [rsp+0D8h+var_78], rdx
0x18002cdbb  mov     r13, rcx
0x18002cdbe  mov     [rsp+0D8h+var_50], rcx
0x18002cdc6  mov     [rsp+0D8h+var_48], rdx
0x18002cdce  lea     rax, WPP_GLOBAL_Control
0x18002cdd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cddc  cmp     rcx, rax
0x18002cddf  jnz     loc_18002D23A
0x18002cde5  lea     rsi, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18002cdec  xor     edx, edx
0x18002cdee  mov     [rsp+0D8h+var_68], rdx
0x18002cdf3  mov     dword ptr [rsp+0D8h+pIdentifierAuthority.Value], edx
0x18002cdfa  mov     word ptr [rsp+0D8h+pIdentifierAuthority.Value+4], 100h
0x18002ce04  test    r13, r13
0x18002ce07  jz      loc_18002D2C8
0x18002ce0d  test    r15, r15
0x18002ce10  jz      loc_18002D2C8
0x18002ce16  mov     r14d, edx
0x18002ce19  mov     [rsp+0D8h+var_60], rdx
0x18002ce1e  mov     r12d, edx
0x18002ce21  mov     [rsp+0D8h+var_58], rdx
0x18002ce29  mov     ebx, edx
0x18002ce2b  mov     [rsp+0D8h+var_70], edx
0x18002ce2f  mov     [r13+0], rdx
0x18002ce33  mov     [r15], rdx
0x18002ce36  lea     rax, [rsp+0D8h+var_68]
0x18002ce3b  mov     [rsp+0D8h+pSid], rax; pSid
0x18002ce40  mov     [rsp+0D8h+nSubAuthority7], edx; nSubAuthority7
0x18002ce44  mov     [rsp+0D8h+nSubAuthority6], edx; nSubAuthority6
0x18002ce48  mov     [rsp+0D8h+nSubAuthority5], edx; nSubAuthority5
0x18002ce4c  mov     [rsp+0D8h+nSubAuthority4], edx; nSubAuthority4
0x18002ce50  mov     [rsp+0D8h+nSubAuthority3], edx; nSubAuthority3
0x18002ce54  mov     [rsp+0D8h+nSubAuthority2], edx; nSubAuthority2
0x18002ce58  xor     r9d, r9d; nSubAuthority1
0x18002ce5b  xor     r8d, r8d; nSubAuthority0
0x18002ce5e  mov     dl, 1; nSubAuthorityCount
0x18002ce60  lea     rcx, [rsp+0D8h+pIdentifierAuthority]; pIdentifierAuthority
0x18002ce68  call    cs:__imp_AllocateAndInitializeSid
0x18002ce6e  test    eax, eax
0x18002ce70  jz      loc_18002D04B
0x18002ce76  mov     rcx, [rsp+0D8h+var_68]; pSid
0x18002ce7b  call    cs:__imp_GetLengthSid
0x18002ce81  lea     r15d, [rax+14h]
0x18002ce85  mov     edx, r15d; dwBytes
0x18002ce88  lea     ecx, [r12+40h]; uFlags
0x18002ce8d  call    cs:__imp_GlobalAlloc
0x18002ce93  mov     r12, rax
0x18002ce96  mov     [rsp+0D8h+var_58], rax
0x18002ce9e  test    rax, rax
0x18002cea1  jz      loc_18002CF66
0x18002cea7  lea     r8d, [r14+2]; dwAclRevision
0x18002ceab  mov     edx, r15d; nAclLength
0x18002ceae  mov     rcx, rax; pAcl
0x18002ceb1  call    cs:__imp_InitializeAcl
0x18002ceb7  test    eax, eax
0x18002ceb9  jz      loc_18002CF94
0x18002cebf  mov     r9, [rsp+0D8h+var_68]; pSid
0x18002cec4  lea     edx, [r14+2]; dwAceRevision
0x18002cec8  mov     r8d, 13FFFFh; AccessMask
0x18002cece  mov     rcx, r12; pAcl
0x18002ced1  call    cs:__imp_AddAccessAllowedAce
0x18002ced7  test    eax, eax
0x18002ced9  jz      loc_18002CFC9
0x18002cedf  lea     edx, [r14+28h]; dwBytes
0x18002cee3  lea     ecx, [rdx+18h]; uFlags
0x18002cee6  call    cs:__imp_GlobalAlloc
0x18002ceec  mov     r14, rax
0x18002ceef  mov     [rsp+0D8h+var_60], rax
0x18002cef4  test    rax, rax
0x18002cef7  jz      loc_18002CFFE
0x18002cefd  mov     r15d, 1
0x18002cf03  mov     edx, r15d; dwRevision
0x18002cf06  mov     rcx, rax; pSecurityDescriptor
0x18002cf09  call    cs:__imp_InitializeSecurityDescriptor
0x18002cf0f  test    eax, eax
0x18002cf11  jz      loc_18002D0CD
0x18002cf17  xor     r9d, r9d; bDaclDefaulted
0x18002cf1a  mov     r8, r12; pDacl
0x18002cf1d  mov     edx, r15d; bDaclPresent
0x18002cf20  mov     rcx, r14; pSecurityDescriptor
0x18002cf23  call    cs:__imp_SetSecurityDescriptorDacl
0x18002cf29  test    eax, eax
0x18002cf2b  jz      loc_18002D10B
0x18002cf31  xor     r8d, r8d; bOwnerDefaulted
0x18002cf34  xor     edx, edx; pOwner
0x18002cf36  mov     rcx, r14; pSecurityDescriptor
0x18002cf39  call    cs:__imp_SetSecurityDescriptorOwner
0x18002cf3f  test    eax, eax
0x18002cf41  jz      loc_18002D14C
0x18002cf47  xor     r8d, r8d; bGroupDefaulted
0x18002cf4a  xor     edx, edx; pGroup
0x18002cf4c  mov     rcx, r14; pSecurityDescriptor
0x18002cf4f  call    cs:__imp_SetSecurityDescriptorGroup
0x18002cf55  test    eax, eax
0x18002cf57  jz      loc_18002D18D
0x18002cf5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cf64  jmp     short loc_18002CF8A
0x18002cf66  mov     r9d, 8
0x18002cf6c  mov     ebx, r9d
0x18002cf6f  mov     [rsp+0D8h+var_70], ebx
0x18002cf73  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cf7a  lea     rax, WPP_GLOBAL_Control
0x18002cf81  cmp     rcx, rax
0x18002cf84  jnz     loc_18002D0A2
0x18002cf8a  mov     r15, [rsp+0D8h+var_78]
0x18002cf8f  jmp     loc_18002D1C9
0x18002cf94  call    cs:__imp_GetLastError
0x18002cf9a  mov     ebx, eax
0x18002cf9c  mov     [rsp+0D8h+var_70], eax
0x18002cfa0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cfa7  lea     rax, WPP_GLOBAL_Control
0x18002cfae  cmp     rcx, rax
0x18002cfb1  jz      short loc_18002CF8A
0x18002cfb3  test    byte ptr [rcx+1Ch], 80h
0x18002cfb7  jz      short loc_18002CF8A
0x18002cfb9  cmp     byte ptr [rcx+19h], 2
0x18002cfbd  jb      short loc_18002CF8A
0x18002cfbf  mov     edx, 15h
0x18002cfc4  jmp     loc_18002D0C5
0x18002cfc9  call    cs:__imp_GetLastError
0x18002cfcf  mov     ebx, eax
0x18002cfd1  mov     [rsp+0D8h+var_70], eax
0x18002cfd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cfdc  lea     rax, WPP_GLOBAL_Control
0x18002cfe3  cmp     rcx, rax
0x18002cfe6  jz      short loc_18002CF8A
0x18002cfe8  test    byte ptr [rcx+1Ch], 80h
0x18002cfec  jz      short loc_18002CF8A
0x18002cfee  cmp     byte ptr [rcx+19h], 2
0x18002cff2  jb      short loc_18002CF8A
0x18002cff4  mov     edx, 16h
0x18002cff9  jmp     loc_18002D0C5
0x18002cffe  mov     r9d, 8
0x18002d004  mov     ebx, r9d
0x18002d007  mov     [rsp+0D8h+var_70], ebx
0x18002d00b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d012  lea     rax, WPP_GLOBAL_Control
0x18002d019  cmp     rcx, rax
0x18002d01c  jz      loc_18002CF8A
0x18002d022  test    byte ptr [rcx+1Ch], 80h
0x18002d026  jz      loc_18002CF8A
0x18002d02c  cmp     byte ptr [rcx+19h], 2
0x18002d030  jb      loc_18002CF8A
0x18002d036  lea     edx, [r9+0Fh]
0x18002d03a  mov     r8, rsi
0x18002d03d  mov     rcx, [rcx+10h]
0x18002d041  call    WPP_SF_d
0x18002d046  jmp     loc_18002CF5D
0x18002d04b  call    cs:__imp_GetLastError
0x18002d051  mov     ebx, eax
0x18002d053  mov     [rsp+0D8h+var_70], eax
0x18002d057  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d05e  lea     rax, WPP_GLOBAL_Control
0x18002d065  cmp     rcx, rax
0x18002d068  jz      loc_18002D1C9
0x18002d06e  test    byte ptr [rcx+1Ch], 80h
0x18002d072  jz      loc_18002D1C9
0x18002d078  cmp     byte ptr [rcx+19h], 2
0x18002d07c  jb      loc_18002D1C9
0x18002d082  mov     edx, 13h
0x18002d087  mov     r9d, ebx
0x18002d08a  mov     r8, rsi
0x18002d08d  mov     rcx, [rcx+10h]
0x18002d091  call    WPP_SF_d
0x18002d096  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d09d  jmp     loc_18002D1C9
0x18002d0a2  test    byte ptr [rcx+1Ch], 80h
0x18002d0a6  jz      loc_18002CF8A
0x18002d0ac  cmp     byte ptr [rcx+19h], 2
0x18002d0b0  jb      loc_18002CF8A
0x18002d0b6  mov     edx, 14h
0x18002d0bb  jmp     loc_18002D03A
0x18002d0c0  mov     edx, 1Bh
0x18002d0c5  mov     r9d, ebx
0x18002d0c8  jmp     loc_18002D03A
0x18002d0cd  call    cs:__imp_GetLastError
0x18002d0d3  mov     ebx, eax
0x18002d0d5  mov     [rsp+0D8h+var_70], eax
0x18002d0d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d0e0  lea     rax, WPP_GLOBAL_Control
0x18002d0e7  cmp     rcx, rax
0x18002d0ea  jz      loc_18002CF8A
0x18002d0f0  test    byte ptr [rcx+1Ch], 80h
0x18002d0f4  jz      loc_18002CF8A
0x18002d0fa  cmp     byte ptr [rcx+19h], 2
0x18002d0fe  jb      loc_18002CF8A
0x18002d104  mov     edx, 18h
0x18002d109  jmp     short loc_18002D0C5
0x18002d10b  call    cs:__imp_GetLastError
0x18002d111  mov     ebx, eax
0x18002d113  mov     [rsp+0D8h+var_70], eax
0x18002d117  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d11e  lea     rax, WPP_GLOBAL_Control
0x18002d125  cmp     rcx, rax
0x18002d128  jz      loc_18002CF8A
0x18002d12e  test    byte ptr [rcx+1Ch], 80h
0x18002d132  jz      loc_18002CF8A
0x18002d138  cmp     byte ptr [rcx+19h], 2
0x18002d13c  jb      loc_18002CF8A
0x18002d142  mov     edx, 19h
0x18002d147  jmp     loc_18002D0C5
0x18002d14c  call    cs:__imp_GetLastError
0x18002d152  mov     ebx, eax
0x18002d154  mov     [rsp+0D8h+var_70], eax
0x18002d158  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d15f  lea     rax, WPP_GLOBAL_Control
0x18002d166  cmp     rcx, rax
0x18002d169  jz      loc_18002CF8A
0x18002d16f  test    byte ptr [rcx+1Ch], 80h
0x18002d173  jz      loc_18002CF8A
0x18002d179  cmp     byte ptr [rcx+19h], 2
0x18002d17d  jb      loc_18002CF8A
0x18002d183  mov     edx, 1Ah
0x18002d188  jmp     loc_18002D0C5
0x18002d18d  call    cs:__imp_GetLastError
0x18002d193  mov     ebx, eax
0x18002d195  mov     [rsp+0D8h+var_70], eax
0x18002d199  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1a0  lea     rax, WPP_GLOBAL_Control
0x18002d1a7  cmp     rcx, rax
0x18002d1aa  jz      loc_18002CF8A
0x18002d1b0  test    byte ptr [rcx+1Ch], 80h
0x18002d1b4  jz      loc_18002CF8A
0x18002d1ba  cmp     byte ptr [rcx+19h], 2
0x18002d1be  jb      loc_18002CF8A
0x18002d1c4  jmp     loc_18002D0C0
0x18002d1c9  test    ebx, ebx
0x18002d1cb  jnz     loc_18002D279
0x18002d1d1  mov     [r13+0], r14
0x18002d1d5  mov     [r15], r12
0x18002d1d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1df  mov     rax, [rsp+0D8h+var_68]
0x18002d1e4  test    rax, rax
0x18002d1e7  jz      short loc_18002D1F9
0x18002d1e9  mov     rcx, rax; pSid
0x18002d1ec  call    cs:__imp_FreeSid
0x18002d1f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1f9  lea     rax, WPP_GLOBAL_Control
0x18002d200  cmp     rcx, rax
0x18002d203  jz      short loc_18002D20F
0x18002d205  test    byte ptr [rcx+1Ch], 80h
0x18002d209  jnz     loc_18002D2A5
0x18002d20f  mov     eax, ebx
0x18002d211  mov     rcx, [rsp+0D8h+var_38]
0x18002d219  xor     rcx, rsp; StackCookie
0x18002d21c  call    __security_check_cookie
0x18002d221  mov     rbx, [rsp+0D8h+arg_10]
0x18002d229  add     rsp, 0B0h
0x18002d230  pop     r15
0x18002d232  pop     r14
0x18002d234  pop     r13
0x18002d236  pop     r12
0x18002d238  pop     rsi
0x18002d239  retn
0x18002d23a  test    byte ptr [rcx+1Ch], 80h
0x18002d23e  jz      loc_18002CDE5
0x18002d244  lea     rsi, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18002d24b  cmp     byte ptr [rcx+19h], 6
0x18002d24f  jb      loc_18002CDEC
0x18002d255  mov     edx, 11h
0x18002d25a  mov     r8, rsi
0x18002d25d  mov     rcx, [rcx+10h]
0x18002d261  call    WPP_SF_
0x18002d266  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d26d  lea     rax, WPP_GLOBAL_Control
0x18002d274  jmp     loc_18002CDEC
0x18002d279  test    r14, r14
0x18002d27c  jz      short loc_18002D28E
0x18002d27e  mov     rcx, r14; hMem
0x18002d281  call    cs:__imp_GlobalFree
0x18002d287  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d28e  test    r12, r12
0x18002d291  jz      loc_18002D1DF
0x18002d297  mov     rcx, r12; hMem
0x18002d29a  call    cs:__imp_GlobalFree
0x18002d2a0  jmp     loc_18002D1D8
0x18002d2a5  cmp     byte ptr [rcx+19h], 6
0x18002d2a9  jb      loc_18002D20F
0x18002d2af  mov     edx, 1Ch
0x18002d2b4  mov     r9d, ebx
0x18002d2b7  mov     r8, rsi
0x18002d2ba  mov     rcx, [rcx+10h]
0x18002d2be  call    WPP_SF_d
0x18002d2c3  jmp     loc_18002D20F
0x18002d2c8  cmp     rcx, rax
0x18002d2cb  jz      short loc_18002D2EE
0x18002d2cd  test    byte ptr [rcx+1Ch], 80h
0x18002d2d1  jz      short loc_18002D2EE
0x18002d2d3  cmp     byte ptr [rcx+19h], 6
  ... truncated ...
```
