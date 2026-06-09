# DwAllocateSecurityDescriptorAllowAccessToWorld

- ea: `0x18006bb54`
- end: `0x18006c0db`
- name: `DwAllocateSecurityDescriptorAllowAccessToWorld`
- size: `1415`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006e3fc`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18006bb54`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bc70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bd6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bdd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006be98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006befa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bf59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bfac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bc70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bd6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bdd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006be98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006befa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bf59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bfac`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006bcd2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006bcd2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18006bf49`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18006bf49`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18006bdc8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18006bdc8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18006bf9c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18006bf9c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18006be88`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18006be88`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18006c043`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800e98b5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18006c043`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800e98b5`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18006bd5e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18006bd5e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18006bc60`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18006bc60`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18006beea`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18006beea`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006c008`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006c023`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800e9886`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800e989f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006c008`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006c023`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800e9886`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800e989f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006bcea`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006be24`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006bcea`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006be24`

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
0x18006bb54  mov     [rsp+arg_10], rbx
0x18006bb59  push    rsi
0x18006bb5a  push    r12
0x18006bb5c  push    r13
0x18006bb5e  push    r14
0x18006bb60  push    r15
0x18006bb62  sub     rsp, 0B0h
0x18006bb69  mov     rax, cs:__security_cookie
0x18006bb70  xor     rax, rsp
0x18006bb73  mov     [rsp+0D8h+var_38], rax
0x18006bb7b  mov     r15, rdx
0x18006bb7e  mov     [rsp+0D8h+var_78], rdx
0x18006bb83  mov     r13, rcx
0x18006bb86  mov     [rsp+0D8h+var_50], rcx
0x18006bb8e  mov     [rsp+0D8h+var_48], rdx
0x18006bb96  lea     rax, WPP_GLOBAL_Control
0x18006bb9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bba4  cmp     rcx, rax
0x18006bba7  jz      short loc_18006BBDD
0x18006bba9  test    byte ptr [rcx+1Ch], 80h
0x18006bbad  jz      short loc_18006BBDD
0x18006bbaf  lea     rsi, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006bbb6  cmp     byte ptr [rcx+19h], 6
0x18006bbba  jb      short loc_18006BBE4
0x18006bbbc  mov     edx, 11h
0x18006bbc1  mov     r8, rsi
0x18006bbc4  mov     rcx, [rcx+10h]
0x18006bbc8  call    WPP_SF_
0x18006bbcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bbd4  lea     rax, WPP_GLOBAL_Control
0x18006bbdb  jmp     short loc_18006BBE4
0x18006bbdd  lea     rsi, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006bbe4  xor     edx, edx
0x18006bbe6  mov     [rsp+0D8h+var_68], rdx
0x18006bbeb  mov     dword ptr [rsp+0D8h+pIdentifierAuthority.Value], edx
0x18006bbf2  mov     word ptr [rsp+0D8h+pIdentifierAuthority.Value+4], 100h
0x18006bbfc  test    r13, r13
0x18006bbff  jz      loc_18006C086
0x18006bc05  test    r15, r15
0x18006bc08  jz      loc_18006C086
0x18006bc0e  mov     r14d, edx
0x18006bc11  mov     [rsp+0D8h+var_60], rdx
0x18006bc16  mov     r12d, edx
0x18006bc19  mov     [rsp+0D8h+var_58], rdx
0x18006bc21  mov     ebx, edx
0x18006bc23  mov     [rsp+0D8h+var_70], edx
0x18006bc27  mov     [r13+0], rdx
0x18006bc2b  mov     [r15], rdx
0x18006bc2e  lea     rax, [rsp+0D8h+var_68]
0x18006bc33  mov     [rsp+0D8h+pSid], rax; pSid
0x18006bc38  mov     [rsp+0D8h+nSubAuthority7], edx; nSubAuthority7
0x18006bc3c  mov     [rsp+0D8h+nSubAuthority6], edx; nSubAuthority6
0x18006bc40  mov     [rsp+0D8h+nSubAuthority5], edx; nSubAuthority5
0x18006bc44  mov     [rsp+0D8h+nSubAuthority4], edx; nSubAuthority4
0x18006bc48  mov     [rsp+0D8h+nSubAuthority3], edx; nSubAuthority3
0x18006bc4c  mov     [rsp+0D8h+nSubAuthority2], edx; nSubAuthority2
0x18006bc50  xor     r9d, r9d; nSubAuthority1
0x18006bc53  xor     r8d, r8d; nSubAuthority0
0x18006bc56  mov     dl, 1; nSubAuthorityCount
0x18006bc58  lea     rcx, [rsp+0D8h+pIdentifierAuthority]; pIdentifierAuthority
0x18006bc60  call    cs:__imp_AllocateAndInitializeSid
0x18006bc67  nop     dword ptr [rax+rax+00h]
0x18006bc6c  test    eax, eax
0x18006bc6e  jnz     short loc_18006BCCD
0x18006bc70  call    cs:__imp_GetLastError
0x18006bc77  nop     dword ptr [rax+rax+00h]
0x18006bc7c  mov     ebx, eax
0x18006bc7e  mov     [rsp+0D8h+var_70], eax
0x18006bc82  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bc89  lea     rax, WPP_GLOBAL_Control
0x18006bc90  cmp     rcx, rax
0x18006bc93  jz      loc_18006BFF3
0x18006bc99  test    byte ptr [rcx+1Ch], 80h
0x18006bc9d  jz      loc_18006BFF3
0x18006bca3  cmp     byte ptr [rcx+19h], 2
0x18006bca7  jb      loc_18006BFF3
0x18006bcad  lea     edx, [r12+13h]
0x18006bcb2  mov     r9d, ebx
0x18006bcb5  mov     r8, rsi
0x18006bcb8  mov     rcx, [rcx+10h]
0x18006bcbc  call    WPP_SF_d
0x18006bcc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bcc8  jmp     loc_18006BFF3
0x18006bccd  mov     rcx, [rsp+0D8h+var_68]; pSid
0x18006bcd2  call    cs:__imp_GetLengthSid
0x18006bcd9  nop     dword ptr [rax+rax+00h]
0x18006bcde  lea     r15d, [rax+14h]
0x18006bce2  mov     edx, r15d; dwBytes
0x18006bce5  mov     ecx, 40h ; '@'; uFlags
0x18006bcea  call    cs:__imp_GlobalAlloc
0x18006bcf1  nop     dword ptr [rax+rax+00h]
0x18006bcf6  mov     r12, rax
0x18006bcf9  mov     [rsp+0D8h+var_58], rax
0x18006bd01  test    rax, rax
0x18006bd04  jnz     short loc_18006BD52
0x18006bd06  lea     r9d, [rax+8]
0x18006bd0a  mov     ebx, r9d
0x18006bd0d  mov     [rsp+0D8h+var_70], ebx
0x18006bd11  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bd18  lea     rax, WPP_GLOBAL_Control
0x18006bd1f  cmp     rcx, rax
0x18006bd22  jz      loc_18006BFEE
0x18006bd28  test    byte ptr [rcx+1Ch], 80h
0x18006bd2c  jz      loc_18006BFEE
0x18006bd32  cmp     byte ptr [rcx+19h], 2
0x18006bd36  jb      loc_18006BFEE
0x18006bd3c  lea     edx, [r12+14h]
0x18006bd41  mov     r8, rsi
0x18006bd44  mov     rcx, [rcx+10h]
0x18006bd48  call    WPP_SF_d
0x18006bd4d  jmp     loc_18006BFE7
0x18006bd52  mov     r8d, 2; dwAclRevision
0x18006bd58  mov     edx, r15d; nAclLength
0x18006bd5b  mov     rcx, r12; pAcl
0x18006bd5e  call    cs:__imp_InitializeAcl
0x18006bd65  nop     dword ptr [rax+rax+00h]
0x18006bd6a  test    eax, eax
0x18006bd6c  jnz     short loc_18006BDB5
0x18006bd6e  call    cs:__imp_GetLastError
0x18006bd75  nop     dword ptr [rax+rax+00h]
0x18006bd7a  mov     ebx, eax
0x18006bd7c  mov     [rsp+0D8h+var_70], eax
0x18006bd80  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bd87  lea     rax, WPP_GLOBAL_Control
0x18006bd8e  cmp     rcx, rax
0x18006bd91  jz      loc_18006BFEE
0x18006bd97  test    byte ptr [rcx+1Ch], 80h
0x18006bd9b  jz      loc_18006BFEE
0x18006bda1  cmp     byte ptr [rcx+19h], 2
0x18006bda5  jb      loc_18006BFEE
0x18006bdab  mov     edx, 15h
0x18006bdb0  mov     r9d, ebx
0x18006bdb3  jmp     short loc_18006BD41
0x18006bdb5  mov     r9, [rsp+0D8h+var_68]; pSid
0x18006bdba  mov     edx, 2; dwAceRevision
0x18006bdbf  mov     r8d, 13FFFFh; AccessMask
0x18006bdc5  mov     rcx, r12; pAcl
0x18006bdc8  call    cs:__imp_AddAccessAllowedAce
0x18006bdcf  nop     dword ptr [rax+rax+00h]
0x18006bdd4  test    eax, eax
0x18006bdd6  jnz     short loc_18006BE1C
0x18006bdd8  call    cs:__imp_GetLastError
0x18006bddf  nop     dword ptr [rax+rax+00h]
0x18006bde4  mov     ebx, eax
0x18006bde6  mov     [rsp+0D8h+var_70], eax
0x18006bdea  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bdf1  lea     rax, WPP_GLOBAL_Control
0x18006bdf8  cmp     rcx, rax
0x18006bdfb  jz      loc_18006BFEE
0x18006be01  test    byte ptr [rcx+1Ch], 80h
0x18006be05  jz      loc_18006BFEE
0x18006be0b  cmp     byte ptr [rcx+19h], 2
0x18006be0f  jb      loc_18006BFEE
0x18006be15  mov     edx, 16h
0x18006be1a  jmp     short loc_18006BDB0
0x18006be1c  mov     edx, 28h ; '('; dwBytes
0x18006be21  lea     ecx, [rdx+18h]; uFlags
0x18006be24  call    cs:__imp_GlobalAlloc
0x18006be2b  nop     dword ptr [rax+rax+00h]
0x18006be30  mov     r14, rax
0x18006be33  mov     [rsp+0D8h+var_60], rax
0x18006be38  test    rax, rax
0x18006be3b  jnz     short loc_18006BE7C
0x18006be3d  lea     r9d, [rax+8]
0x18006be41  mov     ebx, r9d
0x18006be44  mov     [rsp+0D8h+var_70], ebx
0x18006be48  mov     rcx, cs:WPP_GLOBAL_Control
0x18006be4f  lea     rax, WPP_GLOBAL_Control
0x18006be56  cmp     rcx, rax
0x18006be59  jz      loc_18006BFEE
0x18006be5f  test    byte ptr [rcx+1Ch], 80h
0x18006be63  jz      loc_18006BFEE
0x18006be69  cmp     byte ptr [rcx+19h], 2
0x18006be6d  jb      loc_18006BFEE
0x18006be73  lea     edx, [r14+17h]
0x18006be77  jmp     loc_18006BD41
0x18006be7c  mov     r15d, 1
0x18006be82  mov     edx, r15d; dwRevision
0x18006be85  mov     rcx, r14; pSecurityDescriptor
0x18006be88  call    cs:__imp_InitializeSecurityDescriptor
0x18006be8f  nop     dword ptr [rax+rax+00h]
0x18006be94  test    eax, eax
0x18006be96  jnz     short loc_18006BEDE
0x18006be98  call    cs:__imp_GetLastError
0x18006be9f  nop     dword ptr [rax+rax+00h]
0x18006bea4  mov     ebx, eax
0x18006bea6  mov     [rsp+0D8h+var_70], eax
0x18006beaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18006beb1  lea     rax, WPP_GLOBAL_Control
0x18006beb8  cmp     rcx, rax
0x18006bebb  jz      loc_18006BFEE
0x18006bec1  test    byte ptr [rcx+1Ch], 80h
0x18006bec5  jz      loc_18006BFEE
0x18006becb  cmp     byte ptr [rcx+19h], 2
0x18006becf  jb      loc_18006BFEE
0x18006bed5  lea     edx, [r15+17h]
0x18006bed9  jmp     loc_18006BDB0
0x18006bede  xor     r9d, r9d; bDaclDefaulted
0x18006bee1  mov     r8, r12; pDacl
0x18006bee4  mov     edx, r15d; bDaclPresent
0x18006bee7  mov     rcx, r14; pSecurityDescriptor
0x18006beea  call    cs:__imp_SetSecurityDescriptorDacl
0x18006bef1  nop     dword ptr [rax+rax+00h]
0x18006bef6  test    eax, eax
0x18006bef8  jnz     short loc_18006BF41
0x18006befa  call    cs:__imp_GetLastError
0x18006bf01  nop     dword ptr [rax+rax+00h]
0x18006bf06  mov     ebx, eax
0x18006bf08  mov     [rsp+0D8h+var_70], eax
0x18006bf0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bf13  lea     rax, WPP_GLOBAL_Control
0x18006bf1a  cmp     rcx, rax
0x18006bf1d  jz      loc_18006BFEE
0x18006bf23  test    byte ptr [rcx+1Ch], 80h
0x18006bf27  jz      loc_18006BFEE
0x18006bf2d  cmp     byte ptr [rcx+19h], 2
0x18006bf31  jb      loc_18006BFEE
0x18006bf37  mov     edx, 19h
0x18006bf3c  jmp     loc_18006BDB0
0x18006bf41  xor     r8d, r8d; bOwnerDefaulted
0x18006bf44  xor     edx, edx; pOwner
0x18006bf46  mov     rcx, r14; pSecurityDescriptor
0x18006bf49  call    cs:__imp_SetSecurityDescriptorOwner
0x18006bf50  nop     dword ptr [rax+rax+00h]
0x18006bf55  test    eax, eax
0x18006bf57  jnz     short loc_18006BF94
0x18006bf59  call    cs:__imp_GetLastError
0x18006bf60  nop     dword ptr [rax+rax+00h]
0x18006bf65  mov     ebx, eax
0x18006bf67  mov     [rsp+0D8h+var_70], eax
0x18006bf6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bf72  lea     rax, WPP_GLOBAL_Control
0x18006bf79  cmp     rcx, rax
0x18006bf7c  jz      short loc_18006BFEE
0x18006bf7e  test    byte ptr [rcx+1Ch], 80h
0x18006bf82  jz      short loc_18006BFEE
0x18006bf84  cmp     byte ptr [rcx+19h], 2
0x18006bf88  jb      short loc_18006BFEE
0x18006bf8a  mov     edx, 1Ah
0x18006bf8f  jmp     loc_18006BDB0
0x18006bf94  xor     r8d, r8d; bGroupDefaulted
0x18006bf97  xor     edx, edx; pGroup
0x18006bf99  mov     rcx, r14; pSecurityDescriptor
0x18006bf9c  call    cs:__imp_SetSecurityDescriptorGroup
0x18006bfa3  nop     dword ptr [rax+rax+00h]
0x18006bfa8  test    eax, eax
0x18006bfaa  jnz     short loc_18006BFE7
0x18006bfac  call    cs:__imp_GetLastError
0x18006bfb3  nop     dword ptr [rax+rax+00h]
0x18006bfb8  mov     ebx, eax
0x18006bfba  mov     [rsp+0D8h+var_70], eax
0x18006bfbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bfc5  lea     rax, WPP_GLOBAL_Control
0x18006bfcc  cmp     rcx, rax
0x18006bfcf  jz      short loc_18006BFEE
0x18006bfd1  test    byte ptr [rcx+1Ch], 80h
0x18006bfd5  jz      short loc_18006BFEE
0x18006bfd7  cmp     byte ptr [rcx+19h], 2
0x18006bfdb  jb      short loc_18006BFEE
0x18006bfdd  mov     edx, 1Bh
0x18006bfe2  jmp     loc_18006BDB0
0x18006bfe7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bfee  mov     r15, [rsp+0D8h+var_78]
0x18006bff3  test    ebx, ebx
0x18006bff5  jnz     short loc_18006C000
0x18006bff7  mov     [r13+0], r14
0x18006bffb  mov     [r15], r12
0x18006bffe  jmp     short loc_18006C02F
0x18006c000  test    r14, r14
0x18006c003  jz      short loc_18006C01B
0x18006c005  mov     rcx, r14; hMem
0x18006c008  call    cs:__imp_GlobalFree
0x18006c00f  nop     dword ptr [rax+rax+00h]
0x18006c014  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c01b  test    r12, r12
0x18006c01e  jz      short loc_18006C036
0x18006c020  mov     rcx, r12; hMem
0x18006c023  call    cs:__imp_GlobalFree
0x18006c02a  nop     dword ptr [rax+rax+00h]
0x18006c02f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c036  mov     rax, [rsp+0D8h+var_68]
0x18006c03b  test    rax, rax
0x18006c03e  jz      short loc_18006C056
0x18006c040  mov     rcx, rax; pSid
0x18006c043  call    cs:__imp_FreeSid
0x18006c04a  nop     dword ptr [rax+rax+00h]
0x18006c04f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c056  lea     rax, WPP_GLOBAL_Control
0x18006c05d  cmp     rcx, rax
0x18006c060  jz      short loc_18006C082
0x18006c062  test    byte ptr [rcx+1Ch], 80h
0x18006c066  jz      short loc_18006C082
0x18006c068  cmp     byte ptr [rcx+19h], 6
0x18006c06c  jb      short loc_18006C082
0x18006c06e  mov     edx, 1Ch
0x18006c073  mov     r9d, ebx
0x18006c076  mov     r8, rsi
0x18006c079  mov     rcx, [rcx+10h]
0x18006c07d  call    WPP_SF_d
0x18006c082  mov     eax, ebx
  ... truncated ...
```
