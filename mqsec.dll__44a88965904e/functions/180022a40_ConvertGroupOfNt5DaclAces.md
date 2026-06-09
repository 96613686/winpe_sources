# _ConvertGroupOfNt5DaclAces

- ea: `0x180022a40`
- end: `0x180022d01`
- name: `_ConvertGroupOfNt5DaclAces`
- size: `705`
- prototype: `__int64 __fastcall(unsigned int, struct _ACL *, DWORD, DWORD, int, PACL pAcl)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1800227e4`

## callees

- `0x1800049ac`
- `0x1800136f0`
- `0x18001722c`
- `0x180021b30`
- `0x180021b5c`
- `0x180021ba8`
- `0x180022a40`
- `0x180023160`
- `0x1800231ac`

## import_xrefs

- `ADVAPI32!AddAccessDeniedAceEx` at `0x180022c03`
- `ADVAPI32!AddAccessDeniedAceEx` at `0x180022c03`
- `ADVAPI32!AddAccessAllowedAce` at `0x180022b99`
- `ADVAPI32!AddAccessAllowedAce` at `0x180022b99`
- `ADVAPI32!EqualSid` at `0x180022b5b`
- `ADVAPI32!EqualSid` at `0x180022b5b`
- `ADVAPI32!GetAce` at `0x180022abf`
- `ADVAPI32!GetAce` at `0x180022b2a`
- `ADVAPI32!GetAce` at `0x180022abf`
- `ADVAPI32!GetAce` at `0x180022b2a`
- `KERNEL32!GetLastError` at `0x180022ba3`
- `KERNEL32!GetLastError` at `0x180022c4e`
- `KERNEL32!GetLastError` at `0x180022c5b`
- `KERNEL32!GetLastError` at `0x180022cad`
- `KERNEL32!GetLastError` at `0x180022ba3`
- `KERNEL32!GetLastError` at `0x180022c4e`
- `KERNEL32!GetLastError` at `0x180022c5b`
- `KERNEL32!GetLastError` at `0x180022cad`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConvertGroupOfNt5DaclAces(unsigned int a1, struct _ACL *a2, DWORD a3, DWORD a4, int a5, PACL pAcl)
{
  DWORD v7; // edi
  DWORD v10; // eax
  DWORD v11; // ebx
  void *v12; // rsi
  DWORD v13; // esi
  DWORD v14; // ebx
  PSID pSid; // r15
  DWORD v16; // ebx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  DWORD LastError; // eax
  __int64 v21; // rdx
  int v22; // [rsp+30h] [rbp-38h] BYREF
  LPVOID pAce; // [rsp+38h] [rbp-30h] BYREF
  void *v24; // [rsp+40h] [rbp-28h]
  PSID pSid1; // [rsp+48h] [rbp-20h] BYREF
  _BYTE v26[24]; // [rsp+50h] [rbp-18h] BYREF
  int v27; // [rsp+C8h] [rbp+60h] BYREF

  v7 = a3;
  v10 = a4 + 1;
  if ( a4 == -1 || v10 < a3 )
    return 2147942934LL;
  v11 = v10 - a3;
  v12 = MmAllocate(saturated_mul(v10 - a3, 8u));
  v24 = v12;
  aPtrs<_SID>::aPtrs<_SID>(v26, v12, v11);
  v22 = 0;
  while ( 1 )
  {
    pAce = 0;
    if ( !GetAce(a2, v7, &pAce) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        LastError = GetLastError();
        v21 = 16;
LABEL_34:
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          v21,
          WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids,
          v7,
          LastError);
      }
LABEL_35:
      v16 = -1072821238;
      goto LABEL_36;
    }
    ++v7;
    if ( (unsigned int)IsNewNt5Sid(pAce, v12, &v22) )
      break;
LABEL_23:
    if ( v7 > a4 )
    {
      aPtrs<_SID>::~aPtrs<_SID>(v26);
      return 0;
    }
  }
  pSid1 = 0;
  v27 = 0;
  GetpSidAndObj((struct _ACCESS_ALLOWED_ACE *)pAce, &pSid1, &v27, 0);
  v13 = MapNt5RightsToNt4Ace(a1, (unsigned int)v27, pAce, 0);
  v14 = v7;
  pSid = pSid1;
  while ( v14 <= a4 )
  {
    if ( !GetAce(a2, v14, &pAce) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        LastError = GetLastError();
        v21 = 17;
        goto LABEL_34;
      }
      goto LABEL_35;
    }
    pSid1 = 0;
    GetpSidAndObj((struct _ACCESS_ALLOWED_ACE *)pAce, &pSid1, &v27, 0);
    if ( EqualSid(pSid, pSid1) )
      v13 = MapNt5RightsToNt4Ace(a1, (unsigned int)v27, pAce, v13);
    ++v14;
  }
  if ( !v13 )
    goto LABEL_22;
  if ( a5 )
  {
    if ( !AddAccessAllowedAce(pAcl, 2u, v13, pSid) )
    {
      v16 = GetLastError();
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        v18 = 18;
        goto LABEL_18;
      }
      goto LABEL_19;
    }
LABEL_22:
    v12 = v24;
    goto LABEL_23;
  }
  if ( AddAccessDeniedAceEx(pAcl, 2u, 0, v13, pSid) )
    goto LABEL_22;
  v16 = GetLastError();
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
  {
    v18 = 19;
LABEL_18:
    WPP_SF_d(v17[32], v18, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids, v16);
  }
LABEL_19:
  if ( (int)v16 > 0 )
    v16 = (unsigned __int16)v16 | 0x80070000;
LABEL_36:
  aPtrs<_SID>::~aPtrs<_SID>(v26);
  return v16;
}

```

## disassembly

```asm
0x180022a40  push    rbp
0x180022a42  push    rbx
0x180022a43  push    rsi
0x180022a44  push    rdi
0x180022a45  push    r12
0x180022a47  push    r13
0x180022a49  push    r14
0x180022a4b  push    r15
0x180022a4d  mov     rbp, rsp
0x180022a50  sub     rsp, 68h
0x180022a54  mov     r14d, r9d
0x180022a57  mov     edi, r8d
0x180022a5a  mov     r12, rdx
0x180022a5d  mov     r13d, ecx
0x180022a60  lea     eax, [r9+1]
0x180022a64  cmp     eax, 1
0x180022a67  jb      loc_180022CEB
0x180022a6d  cmp     eax, r8d
0x180022a70  jb      loc_180022CEB
0x180022a76  sub     eax, r8d
0x180022a79  mov     ebx, eax
0x180022a7b  mov     eax, 8
0x180022a80  mul     rbx
0x180022a83  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180022a8a  cmovb   rax, rcx
0x180022a8e  mov     rcx, rax; unsigned __int64
0x180022a91  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180022a96  mov     rsi, rax
0x180022a99  mov     [rbp+var_28], rax
0x180022a9d  mov     r8d, ebx
0x180022aa0  mov     rdx, rax
0x180022aa3  lea     rcx, [rbp+var_18]
0x180022aa7  call    ??0?$aPtrs@U_SID@@@@QEAA@PEAPEAU_SID@@K@Z; aPtrs<_SID>::aPtrs<_SID>(_SID * *,ulong)
0x180022aac  nop
0x180022aad  xor     ebx, ebx
0x180022aaf  mov     [rbp+var_38], ebx
0x180022ab2  mov     [rbp+pAce], rbx
0x180022ab6  lea     r8, [rbp+pAce]; pAce
0x180022aba  mov     edx, edi; dwAceIndex
0x180022abc  mov     rcx, r12; pAcl
0x180022abf  call    cs:__imp_GetAce
0x180022ac5  test    eax, eax
0x180022ac7  jz      loc_180022C91
0x180022acd  inc     edi
0x180022acf  lea     r8, [rbp+var_38]
0x180022ad3  mov     rdx, rsi
0x180022ad6  mov     rcx, [rbp+pAce]
0x180022ada  call    _IsNewNt5Sid
0x180022adf  test    eax, eax
0x180022ae1  jz      loc_180022C11
0x180022ae7  mov     [rbp+pSid1], rbx
0x180022aeb  mov     [rbp+arg_18], ebx
0x180022aee  xor     r9d, r9d; struct _GUID **
0x180022af1  lea     r8, [rbp+arg_18]; int *
0x180022af5  lea     rdx, [rbp+pSid1]; void **
0x180022af9  mov     rcx, [rbp+pAce]; struct _ACCESS_ALLOWED_ACE *
0x180022afd  call    ?GetpSidAndObj@@YAXPEAU_ACCESS_ALLOWED_ACE@@PEAPEAXPEAHPEAPEAU_GUID@@@Z; GetpSidAndObj(_ACCESS_ALLOWED_ACE *,void * *,int *,_GUID * *)
0x180022b02  xor     r9d, r9d
0x180022b05  mov     r8, [rbp+pAce]
0x180022b09  mov     edx, [rbp+arg_18]
0x180022b0c  mov     ecx, r13d
0x180022b0f  call    _MapNt5RightsToNt4Ace
0x180022b14  mov     esi, eax
0x180022b16  mov     ebx, edi
0x180022b18  mov     r15, [rbp+pSid1]
0x180022b1c  cmp     ebx, r14d
0x180022b1f  ja      short loc_180022B7D
0x180022b21  lea     r8, [rbp+pAce]; pAce
0x180022b25  mov     edx, ebx; dwAceIndex
0x180022b27  mov     rcx, r12; pAcl
0x180022b2a  call    cs:__imp_GetAce
0x180022b30  test    eax, eax
0x180022b32  jz      loc_180022C2A
0x180022b38  mov     [rbp+pSid1], 0
0x180022b40  xor     r9d, r9d; struct _GUID **
0x180022b43  lea     r8, [rbp+arg_18]; int *
0x180022b47  lea     rdx, [rbp+pSid1]; void **
0x180022b4b  mov     rcx, [rbp+pAce]; struct _ACCESS_ALLOWED_ACE *
0x180022b4f  call    ?GetpSidAndObj@@YAXPEAU_ACCESS_ALLOWED_ACE@@PEAPEAXPEAHPEAPEAU_GUID@@@Z; GetpSidAndObj(_ACCESS_ALLOWED_ACE *,void * *,int *,_GUID * *)
0x180022b54  mov     rdx, [rbp+pSid1]; pSid2
0x180022b58  mov     rcx, r15; pSid1
0x180022b5b  call    cs:__imp_EqualSid
0x180022b61  test    eax, eax
0x180022b63  jz      short loc_180022B79
0x180022b65  mov     r9d, esi
0x180022b68  mov     r8, [rbp+pAce]
0x180022b6c  mov     edx, [rbp+arg_18]
0x180022b6f  mov     ecx, r13d
0x180022b72  call    _MapNt5RightsToNt4Ace
0x180022b77  mov     esi, eax
0x180022b79  inc     ebx
0x180022b7b  jmp     short loc_180022B1C
0x180022b7d  xor     ebx, ebx
0x180022b7f  test    esi, esi
0x180022b81  jz      loc_180022C0D
0x180022b87  lea     edx, [rbx+2]; dwAceRevision
0x180022b8a  mov     rcx, [rbp+pAcl]; pAcl
0x180022b8e  cmp     [rbp+arg_20], ebx
0x180022b91  jz      short loc_180022BF8
0x180022b93  mov     r9, r15; pSid
0x180022b96  mov     r8d, esi; AccessMask
0x180022b99  call    cs:__imp_AddAccessAllowedAce
0x180022b9f  test    eax, eax
0x180022ba1  jnz     short loc_180022C0D
0x180022ba3  call    cs:__imp_GetLastError
0x180022ba9  mov     ebx, eax
0x180022bab  lea     rax, WPP_GLOBAL_Control
0x180022bb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bb9  cmp     rcx, rax
0x180022bbc  jz      short loc_180022BE2
0x180022bbe  test    byte ptr [rcx+10Ch], 1
0x180022bc5  jz      short loc_180022BE2
0x180022bc7  mov     edx, 12h
0x180022bcc  mov     r9d, ebx
0x180022bcf  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x180022bd6  mov     rcx, [rcx+100h]
0x180022bdd  call    WPP_SF_d
0x180022be2  test    ebx, ebx
0x180022be4  jle     loc_180022CDE
0x180022bea  movzx   ebx, bx
0x180022bed  or      ebx, 80070000h
0x180022bf3  jmp     loc_180022CDE
0x180022bf8  mov     [rsp+68h+pSid], r15; pSid
0x180022bfd  mov     r9d, esi; AccessMask
0x180022c00  xor     r8d, r8d; AceFlags
0x180022c03  call    cs:__imp_AddAccessDeniedAceEx
0x180022c09  test    eax, eax
0x180022c0b  jz      short loc_180022C5B
0x180022c0d  mov     rsi, [rbp+var_28]
0x180022c11  cmp     edi, r14d
0x180022c14  jbe     loc_180022AB2
0x180022c1a  lea     rcx, [rbp+var_18]
0x180022c1e  call    ??1?$aPtrs@U_SID@@@@QEAA@XZ; aPtrs<_SID>::~aPtrs<_SID>(void)
0x180022c23  xor     eax, eax
0x180022c25  jmp     loc_180022CF0
0x180022c2a  lea     rax, WPP_GLOBAL_Control
0x180022c31  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c38  cmp     rcx, rax
0x180022c3b  jz      loc_180022CD9
0x180022c41  test    byte ptr [rcx+10Ch], 1
0x180022c48  jz      loc_180022CD9
0x180022c4e  call    cs:__imp_GetLastError
0x180022c54  mov     edx, 11h
0x180022c59  jmp     short loc_180022CB8
0x180022c5b  call    cs:__imp_GetLastError
0x180022c61  mov     ebx, eax
0x180022c63  lea     rax, WPP_GLOBAL_Control
0x180022c6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c71  cmp     rcx, rax
0x180022c74  jz      loc_180022BE2
0x180022c7a  test    byte ptr [rcx+10Ch], 1
0x180022c81  jz      loc_180022BE2
0x180022c87  mov     edx, 13h
0x180022c8c  jmp     loc_180022BCC
0x180022c91  lea     rax, WPP_GLOBAL_Control
0x180022c98  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c9f  cmp     rcx, rax
0x180022ca2  jz      short loc_180022CD9
0x180022ca4  test    byte ptr [rcx+10Ch], 1
0x180022cab  jz      short loc_180022CD9
0x180022cad  call    cs:__imp_GetLastError
0x180022cb3  mov     edx, 10h
0x180022cb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180022cbf  mov     dword ptr [rsp+68h+pSid], eax
0x180022cc3  mov     r9d, edi
0x180022cc6  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x180022ccd  mov     rcx, [rcx+100h]
0x180022cd4  call    WPP_SF_dd
0x180022cd9  mov     ebx, 0C00E0C0Ah
0x180022cde  lea     rcx, [rbp+var_18]
0x180022ce2  call    ??1?$aPtrs@U_SID@@@@QEAA@XZ; aPtrs<_SID>::~aPtrs<_SID>(void)
0x180022ce7  mov     eax, ebx
0x180022ce9  jmp     short loc_180022CF0
0x180022ceb  mov     eax, 80070216h
0x180022cf0  add     rsp, 68h
0x180022cf4  pop     r15
0x180022cf6  pop     r14
0x180022cf8  pop     r13
0x180022cfa  pop     r12
0x180022cfc  pop     rdi
0x180022cfd  pop     rsi
0x180022cfe  pop     rbx
0x180022cff  pop     rbp
0x180022d00  retn
```
