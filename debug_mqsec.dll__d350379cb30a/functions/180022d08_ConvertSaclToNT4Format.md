# _ConvertSaclToNT4Format

- ea: `0x180022d08`
- end: `0x18002315a`
- name: `_ConvertSaclToNT4Format`
- size: `1106`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180021d10`

## callees

- `0x1800049ac`
- `0x1800136f0`
- `0x18001722c`
- `0x180021b30`
- `0x180021b5c`
- `0x180021ba8`
- `0x180022d08`
- `0x180023160`
- `0x1800232b0`

## import_xrefs

- `msvcrt!free` at `0x180022dd1`
- `msvcrt!free` at `0x180022fa3`
- `msvcrt!free` at `0x180023005`
- `msvcrt!free` at `0x18002306a`
- `msvcrt!free` at `0x1800230cf`
- `msvcrt!free` at `0x180023131`
- `msvcrt!free` at `0x180022dd1`
- `msvcrt!free` at `0x180022fa3`
- `msvcrt!free` at `0x180023005`
- `msvcrt!free` at `0x18002306a`
- `msvcrt!free` at `0x1800230cf`
- `msvcrt!free` at `0x180023131`
- `ADVAPI32!AddAuditAccessAce` at `0x180022f40`
- `ADVAPI32!AddAuditAccessAce` at `0x180022f78`
- `ADVAPI32!AddAuditAccessAce` at `0x180022f40`
- `ADVAPI32!AddAuditAccessAce` at `0x180022f78`
- `ADVAPI32!EqualSid` at `0x180022ee3`
- `ADVAPI32!EqualSid` at `0x180022ee3`
- `ADVAPI32!GetAce` at `0x180022e28`
- `ADVAPI32!GetAce` at `0x180022eb1`
- `ADVAPI32!GetAce` at `0x180022e28`
- `ADVAPI32!GetAce` at `0x180022eb1`
- `ADVAPI32!InitializeAcl` at `0x180022d78`
- `ADVAPI32!InitializeAcl` at `0x180022d78`
- `KERNEL32!GetLastError` at `0x180022d82`
- `KERNEL32!GetLastError` at `0x180022fcb`
- `KERNEL32!GetLastError` at `0x180023011`
- `KERNEL32!GetLastError` at `0x180023076`
- `KERNEL32!GetLastError` at `0x1800230f7`
- `KERNEL32!GetLastError` at `0x180022d82`
- `KERNEL32!GetLastError` at `0x180022fcb`
- `KERNEL32!GetLastError` at `0x180023011`
- `KERNEL32!GetLastError` at `0x180023076`
- `KERNEL32!GetLastError` at `0x1800230f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ConvertSaclToNT4Format(int a1, struct _ACL *a2, DWORD *a3, PACL *a4)
{
  struct _ACL *v6; // r15
  int v7; // r14d
  unsigned __int64 AceCount; // r12
  DWORD AclSize; // eax
  struct _ACL *v11; // rbx
  signed int v12; // edi
  DWORD v13; // edi
  DWORD i; // r14d
  DWORD v15; // r14d
  DWORD v16; // r15d
  DWORD v17; // eax
  DWORD LastError; // eax
  int v19; // [rsp+30h] [rbp-50h] BYREF
  DWORD v20; // [rsp+34h] [rbp-4Ch] BYREF
  DWORD dwAccessMask; // [rsp+38h] [rbp-48h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-40h] BYREF
  PSID pSid1; // [rsp+48h] [rbp-38h] BYREF
  int v24; // [rsp+50h] [rbp-30h] BYREF
  PSID pSid2; // [rsp+58h] [rbp-28h] BYREF
  _BYTE v26[16]; // [rsp+60h] [rbp-20h] BYREF
  void *v27; // [rsp+70h] [rbp-10h]
  struct _ACL *v28; // [rsp+78h] [rbp-8h]

  v6 = a2;
  v7 = a1;
  AceCount = a2->AceCount;
  if ( a2->AceCount )
  {
    AclSize = a2->AclSize;
    *a3 = AclSize;
    v11 = (struct _ACL *)MmAllocate(AclSize);
    v28 = v11;
    *a4 = v11;
    if ( InitializeAcl(v11, *a3, 2u) )
    {
      v27 = MmAllocate(saturated_mul(AceCount, 8u));
      aPtrs<_SID>::aPtrs<_SID>(v26, v27, (unsigned int)AceCount);
      v24 = 0;
      v13 = 0;
      while ( 1 )
      {
        pAce = 0;
        if ( !GetAce(v6, v13, &pAce) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          {
            LastError = GetLastError();
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 32),
              12,
              &WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids,
              v13,
              LastError);
          }
LABEL_48:
          aPtrs<_SID>::~aPtrs<_SID>(v26);
          free(v11);
          return 3222146058LL;
        }
        ++v13;
        if ( (unsigned int)IsNewNt5Sid(pAce, v27, &v24) )
          break;
LABEL_27:
        if ( v13 >= (unsigned int)AceCount )
        {
          aPtrs<_SID>::~aPtrs<_SID>(v26);
          free(0);
          return 0;
        }
      }
      v19 = 0;
      pSid1 = 0;
      GetpSidAndObj((struct _ACCESS_ALLOWED_ACE *)pAce, &pSid1, &v19, 0);
      v20 = 0;
      dwAccessMask = 0;
      SetNt4AuditMasks((_DWORD)pAce, v7, v19, (unsigned int)&v20, (__int64)&dwAccessMask);
      for ( i = v13; i < (unsigned int)AceCount; ++i )
      {
        if ( !GetAce(v6, i, &pAce) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          {
            v17 = GetLastError();
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 32),
              13,
              &WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids,
              v13,
              v17);
          }
          goto LABEL_48;
        }
        pSid2 = 0;
        GetpSidAndObj((struct _ACCESS_ALLOWED_ACE *)pAce, &pSid2, &v19, 0);
        if ( EqualSid(pSid1, pSid2) )
          SetNt4AuditMasks((_DWORD)pAce, a1, v19, (unsigned int)&v20, (__int64)&dwAccessMask);
      }
      v15 = v20;
      v16 = dwAccessMask;
      if ( dwAccessMask && !AddAuditAccessAce(*a4, 2u, dwAccessMask, pSid1, 1, v20 == dwAccessMask) )
      {
        v12 = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            14,
            &WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids,
            (unsigned int)v12);
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
      }
      else
      {
        if ( !v15 || v15 == v16 || AddAuditAccessAce(*a4, 2u, v15, pSid1, 0, 1) )
        {
          v6 = a2;
          v7 = a1;
          goto LABEL_27;
        }
        v12 = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            15,
            &WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids,
            (unsigned int)v12);
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
      }
      aPtrs<_SID>::~aPtrs<_SID>(v26);
      free(v11);
    }
    else
    {
      v12 = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          11,
          &WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids,
          (unsigned int)v12);
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      free(v11);
    }
    return (unsigned int)v12;
  }
  else
  {
    *a3 = AceCount;
    *a4 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x180022d08  mov     rax, rsp
0x180022d0b  mov     [rax+18h], rbx
0x180022d0f  mov     [rax+20h], rdi
0x180022d13  mov     [rax+10h], rdx
0x180022d17  mov     [rax+8], ecx
0x180022d1a  push    rbp
0x180022d1b  push    r12
0x180022d1d  push    r13
0x180022d1f  push    r14
0x180022d21  push    r15
0x180022d23  mov     rbp, rsp
0x180022d26  sub     rsp, 80h
0x180022d2d  mov     r13, r9
0x180022d30  mov     rdi, r8
0x180022d33  mov     r15, rdx
0x180022d36  mov     r14d, ecx
0x180022d39  movzx   r12d, word ptr [rdx+4]
0x180022d3e  test    r12d, r12d
0x180022d41  jnz     short loc_180022D54
0x180022d43  mov     [r8], r12d
0x180022d46  mov     qword ptr [r9], 0
0x180022d4d  xor     eax, eax
0x180022d4f  jmp     loc_18002313D
0x180022d54  movzx   eax, word ptr [rdx+2]
0x180022d58  mov     [r8], eax
0x180022d5b  mov     ecx, eax; unsigned __int64
0x180022d5d  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180022d62  mov     rbx, rax
0x180022d65  mov     [rbp+var_8], rax
0x180022d69  mov     [r13+0], rax
0x180022d6d  mov     r8d, 2; dwAclRevision
0x180022d73  mov     edx, [rdi]; nAclLength
0x180022d75  mov     rcx, rax; pAcl
0x180022d78  call    cs:__imp_InitializeAcl
0x180022d7e  test    eax, eax
0x180022d80  jnz     short loc_180022DDF
0x180022d82  call    cs:__imp_GetLastError
0x180022d88  mov     edi, eax
0x180022d8a  lea     rax, WPP_GLOBAL_Control
0x180022d91  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d98  cmp     rcx, rax
0x180022d9b  jz      short loc_180022DC1
0x180022d9d  test    byte ptr [rcx+10Ch], 1
0x180022da4  jz      short loc_180022DC1
0x180022da6  mov     edx, 0Bh
0x180022dab  mov     r9d, edi
0x180022dae  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x180022db5  mov     rcx, [rcx+100h]
0x180022dbc  call    WPP_SF_d
0x180022dc1  test    edi, edi
0x180022dc3  jle     short loc_180022DCE
0x180022dc5  movzx   edi, di
0x180022dc8  or      edi, 80070000h
0x180022dce  mov     rcx, rbx; Block
0x180022dd1  call    cs:__imp_free
0x180022dd7  nop
0x180022dd8  mov     eax, edi
0x180022dda  jmp     loc_18002313D
0x180022ddf  mov     eax, 8
0x180022de4  mul     r12
0x180022de7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180022dee  cmovb   rax, rcx
0x180022df2  mov     rcx, rax; unsigned __int64
0x180022df5  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180022dfa  mov     [rbp+var_10], rax
0x180022dfe  mov     r8d, r12d
0x180022e01  mov     rdx, rax
0x180022e04  lea     rcx, [rbp+var_20]
0x180022e08  call    ??0?$aPtrs@U_SID@@@@QEAA@PEAPEAU_SID@@K@Z; aPtrs<_SID>::aPtrs<_SID>(_SID * *,ulong)
0x180022e0d  nop
0x180022e0e  mov     [rbp+var_30], 0
0x180022e15  xor     edi, edi
0x180022e17  mov     [rbp+pAce], 0
0x180022e1f  lea     r8, [rbp+pAce]; pAce
0x180022e23  mov     edx, edi; dwAceIndex
0x180022e25  mov     rcx, r15; pAcl
0x180022e28  call    cs:__imp_GetAce
0x180022e2e  test    eax, eax
0x180022e30  jz      loc_1800230DB
0x180022e36  inc     edi
0x180022e38  lea     r8, [rbp+var_30]
0x180022e3c  mov     rdx, [rbp+var_10]
0x180022e40  mov     rcx, [rbp+pAce]
0x180022e44  call    _IsNewNt5Sid
0x180022e49  test    eax, eax
0x180022e4b  jz      loc_180022F8E
0x180022e51  mov     [rbp+var_50], 0
0x180022e58  mov     [rbp+pSid1], 0
0x180022e60  xor     r9d, r9d; struct _GUID **
0x180022e63  lea     r8, [rbp+var_50]; int *
0x180022e67  lea     rdx, [rbp+pSid1]; void **
0x180022e6b  mov     rcx, [rbp+pAce]; struct _ACCESS_ALLOWED_ACE *
0x180022e6f  call    ?GetpSidAndObj@@YAXPEAU_ACCESS_ALLOWED_ACE@@PEAPEAXPEAHPEAPEAU_GUID@@@Z; GetpSidAndObj(_ACCESS_ALLOWED_ACE *,void * *,int *,_GUID * *)
0x180022e74  mov     [rbp+var_4C], 0
0x180022e7b  mov     [rbp+dwAccessMask], 0
0x180022e82  lea     rax, [rbp+dwAccessMask]
0x180022e86  mov     qword ptr [rsp+80h+bAuditSuccess], rax
0x180022e8b  lea     r9, [rbp+var_4C]
0x180022e8f  mov     r8d, [rbp+var_50]
0x180022e93  mov     edx, r14d
0x180022e96  mov     rcx, [rbp+pAce]
0x180022e9a  call    _SetNt4AuditMasks
0x180022e9f  mov     r14d, edi
0x180022ea2  cmp     r14d, r12d
0x180022ea5  jnb     short loc_180022F0F
0x180022ea7  lea     r8, [rbp+pAce]; pAce
0x180022eab  mov     edx, r14d; dwAceIndex
0x180022eae  mov     rcx, r15; pAcl
0x180022eb1  call    cs:__imp_GetAce
0x180022eb7  test    eax, eax
0x180022eb9  jz      loc_180022FAF
0x180022ebf  mov     [rbp+pSid2], 0
0x180022ec7  xor     r9d, r9d; struct _GUID **
0x180022eca  lea     r8, [rbp+var_50]; int *
0x180022ece  lea     rdx, [rbp+pSid2]; void **
0x180022ed2  mov     rcx, [rbp+pAce]; struct _ACCESS_ALLOWED_ACE *
0x180022ed6  call    ?GetpSidAndObj@@YAXPEAU_ACCESS_ALLOWED_ACE@@PEAPEAXPEAHPEAPEAU_GUID@@@Z; GetpSidAndObj(_ACCESS_ALLOWED_ACE *,void * *,int *,_GUID * *)
0x180022edb  mov     rdx, [rbp+pSid2]; pSid2
0x180022edf  mov     rcx, [rbp+pSid1]; pSid1
0x180022ee3  call    cs:__imp_EqualSid
0x180022ee9  test    eax, eax
0x180022eeb  jz      short loc_180022F0A
0x180022eed  lea     rax, [rbp+dwAccessMask]
0x180022ef1  mov     qword ptr [rsp+80h+bAuditSuccess], rax
0x180022ef6  lea     r9, [rbp+var_4C]
0x180022efa  mov     r8d, [rbp+var_50]
0x180022efe  mov     edx, [rbp+arg_0]
0x180022f01  mov     rcx, [rbp+pAce]
0x180022f05  call    _SetNt4AuditMasks
0x180022f0a  inc     r14d
0x180022f0d  jmp     short loc_180022EA2
0x180022f0f  mov     r14d, [rbp+var_4C]
0x180022f13  mov     r15d, [rbp+dwAccessMask]
0x180022f17  test    r15d, r15d
0x180022f1a  jz      short loc_180022F4E
0x180022f1c  xor     eax, eax
0x180022f1e  cmp     r14d, r15d
0x180022f21  setz    al
0x180022f24  mov     [rsp+80h+bAuditFailure], eax; bAuditFailure
0x180022f28  mov     [rsp+80h+bAuditSuccess], 1; bAuditSuccess
0x180022f30  mov     r9, [rbp+pSid1]; pSid
0x180022f34  mov     r8d, r15d; dwAccessMask
0x180022f37  mov     edx, 2; dwAceRevision
0x180022f3c  mov     rcx, [r13+0]; pAcl
0x180022f40  call    cs:__imp_AddAuditAccessAce
0x180022f46  test    eax, eax
0x180022f48  jz      loc_180023011
0x180022f4e  test    r14d, r14d
0x180022f51  jz      short loc_180022F86
0x180022f53  cmp     r14d, r15d
0x180022f56  jz      short loc_180022F86
0x180022f58  mov     [rsp+80h+bAuditFailure], 1; bAuditFailure
0x180022f60  mov     [rsp+80h+bAuditSuccess], 0; bAuditSuccess
0x180022f68  mov     r9, [rbp+pSid1]; pSid
0x180022f6c  mov     r8d, r14d; dwAccessMask
0x180022f6f  mov     edx, 2; dwAceRevision
0x180022f74  mov     rcx, [r13+0]; pAcl
0x180022f78  call    cs:__imp_AddAuditAccessAce
0x180022f7e  test    eax, eax
0x180022f80  jz      loc_180023076
0x180022f86  mov     r15, [rbp+arg_8]
0x180022f8a  mov     r14d, [rbp+arg_0]
0x180022f8e  cmp     edi, r12d
0x180022f91  jb      loc_180022E17
0x180022f97  lea     rcx, [rbp+var_20]
0x180022f9b  call    ??1?$aPtrs@U_SID@@@@QEAA@XZ; aPtrs<_SID>::~aPtrs<_SID>(void)
0x180022fa0  nop
0x180022fa1  xor     ecx, ecx; Block
0x180022fa3  call    cs:__imp_free
0x180022fa9  nop
0x180022faa  jmp     loc_180022D4D
0x180022faf  lea     rax, WPP_GLOBAL_Control
0x180022fb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180022fbd  cmp     rcx, rax
0x180022fc0  jz      short loc_180022FF8
0x180022fc2  test    byte ptr [rcx+10Ch], 1
0x180022fc9  jz      short loc_180022FF8
0x180022fcb  call    cs:__imp_GetLastError
0x180022fd1  mov     edx, 0Dh
0x180022fd6  mov     [rsp+80h+bAuditSuccess], eax
0x180022fda  mov     r9d, edi
0x180022fdd  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x180022fe4  mov     rcx, cs:WPP_GLOBAL_Control
0x180022feb  mov     rcx, [rcx+100h]
0x180022ff2  call    WPP_SF_dd
0x180022ff7  nop
0x180022ff8  lea     rcx, [rbp+var_20]
0x180022ffc  call    ??1?$aPtrs@U_SID@@@@QEAA@XZ; aPtrs<_SID>::~aPtrs<_SID>(void)
0x180023001  nop
0x180023002  mov     rcx, rbx; Block
0x180023005  call    cs:__imp_free
0x18002300b  nop
0x18002300c  jmp     loc_180023138
0x180023011  call    cs:__imp_GetLastError
0x180023017  mov     edi, eax
0x180023019  lea     rax, WPP_GLOBAL_Control
0x180023020  mov     rcx, cs:WPP_GLOBAL_Control
0x180023027  cmp     rcx, rax
0x18002302a  jz      short loc_180023050
0x18002302c  test    byte ptr [rcx+10Ch], 1
0x180023033  jz      short loc_180023050
0x180023035  mov     edx, 0Eh
0x18002303a  mov     r9d, edi
0x18002303d  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x180023044  mov     rcx, [rcx+100h]
0x18002304b  call    WPP_SF_d
0x180023050  test    edi, edi
0x180023052  jle     short loc_18002305D
0x180023054  movzx   edi, di
0x180023057  or      edi, 80070000h
0x18002305d  lea     rcx, [rbp+var_20]
0x180023061  call    ??1?$aPtrs@U_SID@@@@QEAA@XZ; aPtrs<_SID>::~aPtrs<_SID>(void)
0x180023066  nop
0x180023067  mov     rcx, rbx; Block
0x18002306a  call    cs:__imp_free
0x180023070  nop
0x180023071  jmp     loc_180022DD8
0x180023076  call    cs:__imp_GetLastError
0x18002307c  mov     edi, eax
0x18002307e  lea     rax, WPP_GLOBAL_Control
0x180023085  mov     rcx, cs:WPP_GLOBAL_Control
0x18002308c  cmp     rcx, rax
0x18002308f  jz      short loc_1800230B5
0x180023091  test    byte ptr [rcx+10Ch], 1
0x180023098  jz      short loc_1800230B5
0x18002309a  mov     edx, 0Fh
0x18002309f  mov     r9d, edi
0x1800230a2  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x1800230a9  mov     rcx, [rcx+100h]
0x1800230b0  call    WPP_SF_d
0x1800230b5  test    edi, edi
0x1800230b7  jle     short loc_1800230C2
0x1800230b9  movzx   edi, di
0x1800230bc  or      edi, 80070000h
0x1800230c2  lea     rcx, [rbp+var_20]
0x1800230c6  call    ??1?$aPtrs@U_SID@@@@QEAA@XZ; aPtrs<_SID>::~aPtrs<_SID>(void)
0x1800230cb  nop
0x1800230cc  mov     rcx, rbx; Block
0x1800230cf  call    cs:__imp_free
0x1800230d5  nop
0x1800230d6  jmp     loc_180022DD8
0x1800230db  lea     rax, WPP_GLOBAL_Control
0x1800230e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800230e9  cmp     rcx, rax
0x1800230ec  jz      short loc_180023124
0x1800230ee  test    byte ptr [rcx+10Ch], 1
0x1800230f5  jz      short loc_180023124
0x1800230f7  call    cs:__imp_GetLastError
0x1800230fd  mov     edx, 0Ch
0x180023102  mov     [rsp+80h+bAuditSuccess], eax
0x180023106  mov     r9d, edi
0x180023109  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x180023110  mov     rcx, cs:WPP_GLOBAL_Control
0x180023117  mov     rcx, [rcx+100h]
0x18002311e  call    WPP_SF_dd
0x180023123  nop
0x180023124  lea     rcx, [rbp+var_20]
0x180023128  call    ??1?$aPtrs@U_SID@@@@QEAA@XZ; aPtrs<_SID>::~aPtrs<_SID>(void)
0x18002312d  nop
0x18002312e  mov     rcx, rbx; Block
0x180023131  call    cs:__imp_free
0x180023137  nop
0x180023138  mov     eax, 0C00E0C0Ah
0x18002313d  lea     r11, [rsp+80h+var_s0]
0x180023145  mov     rbx, [r11+40h]
0x180023149  mov     rdi, [r11+48h]
0x18002314d  mov     rsp, r11
0x180023150  pop     r15
0x180023152  pop     r14
0x180023154  pop     r13
0x180023156  pop     r12
0x180023158  pop     rbp
0x180023159  retn
```
