# SetSidOnAcl(_ACL *,void *,ulong,uchar,int,_ACL * *)

- ea: `0x1800650b0`
- end: `0x18006531b`
- name: `?SetSidOnAcl@@YAHPEAU_ACL@@PEAXKEHPEAPEAU1@@Z`
- size: `619`
- prototype: `__int64 __usercall@<rax>(PACL pAcl@<rcx>, PSID pSid1@<rdx>, unsigned int@<r8d>, unsigned __int8@<r9b>, int, struct _ACL **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180065324`

## callees

- `0x180053fec`
- `0x1800650b0`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006516e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800651de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006516e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800651de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065252`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006512d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006512d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065125`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065125`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180065225`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180065225`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800651a8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800652cf`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800651a8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800652cf`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180065276`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180065276`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18006518e`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180065289`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800652af`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18006518e`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180065289`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800652af`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800652f2`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800652f2`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180065164`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180065164`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180065115`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180065115`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180065248`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180065248`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800651d2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800651f6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800651d2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800651f6`

## pseudocode

```c
__int64 __fastcall SetSidOnAcl(PACL pAcl, PSID pSid1, DWORD a3, __int64 a4, int a5, struct _ACL **a6)
{
  struct _ACL **v6; // rax
  struct _ACL *v8; // r14
  unsigned int v10; // edi
  DWORD LastError; // ebx
  int v13; // r12d
  DWORD v14; // ebx
  unsigned int v15; // esi
  DWORD LengthSid; // eax
  struct _ACL *v17; // rax
  struct _ACL *v18; // rsi
  DWORD i; // ebx
  unsigned __int16 *v20; // r9
  LPVOID v21; // [rsp+38h] [rbp-48h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-40h] BYREF
  DWORD AccessMask; // [rsp+48h] [rbp-38h]
  PACL pAcla; // [rsp+50h] [rbp-30h]
  struct _ACL **v25; // [rsp+58h] [rbp-28h]
  __int64 pAclInformation; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+68h] [rbp-18h]

  v6 = a6;
  pAcla = pAcl;
  v8 = 0;
  AccessMask = a3;
  v25 = a6;
  pAclInformation = 0;
  v27 = 0;
  pAce = 0;
  if ( !pAcl )
  {
    v10 = 1;
    goto LABEL_42;
  }
  v10 = 0;
  if ( !IsValidSid(pSid1) )
  {
    LastError = 87;
    goto LABEL_5;
  }
  if ( !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    LastError = GetLastError();
    goto LABEL_5;
  }
  v13 = 0;
  v14 = 0;
  v10 = 1;
  while ( v14 < (unsigned int)pAclInformation )
  {
    if ( !GetAce(pAcl, v14, &pAce) )
    {
      LastError = GetLastError();
      v10 = 0;
      goto LABEL_5;
    }
    if ( !*(_BYTE *)pAce && EqualSid(pSid1, (char *)pAce + 8) )
    {
      v13 = 1;
      break;
    }
    ++v14;
  }
  LastError = 8;
  v15 = HIDWORD(pAclInformation);
  LODWORD(v21) = HIDWORD(pAclInformation);
  if ( a5 )
  {
    if ( !v13 )
      v15 += GetLengthSid(pSid1) + 8;
  }
  else if ( v13 )
  {
    LengthSid = GetLengthSid(pSid1);
    if ( (int)ULongSub(v15, LengthSid + 8, (unsigned int *)&v21) < 0 )
    {
      LastError = 534;
      v10 = 0;
      goto LABEL_5;
    }
    v15 = (unsigned int)v21;
  }
  v17 = (struct _ACL *)LocalAlloc(0x40u, v15);
  v8 = v17;
  if ( !v17 )
  {
LABEL_25:
    v10 = 0;
    goto LABEL_5;
  }
  if ( !InitializeAcl(v17, v15, 2u) )
  {
LABEL_27:
    LastError = GetLastError();
    goto LABEL_25;
  }
  if ( a5 )
  {
    v21 = 0;
    if ( !AddAccessAllowedAce(v8, 2u, AccessMask, pSid1) || !GetAce(v8, 0, &v21) )
      goto LABEL_27;
    *((_BYTE *)v21 + 1) = 0;
  }
  v18 = pAcla;
  for ( i = 0; i < (unsigned int)pAclInformation; ++i )
  {
    if ( !GetAce(v18, i, &pAce) )
      goto LABEL_27;
    if ( v13 )
    {
      v20 = (unsigned __int16 *)pAce;
      if ( *(_BYTE *)pAce )
        goto LABEL_39;
      if ( EqualSid(pSid1, (char *)pAce + 8) )
        continue;
    }
    v20 = (unsigned __int16 *)pAce;
LABEL_39:
    if ( !AddAce(v8, 2u, 0xFFFFFFFF, v20, v20[1]) )
      goto LABEL_27;
  }
  v6 = v25;
LABEL_42:
  LastError = 0;
  if ( v6 )
  {
    *v6 = v8;
    goto LABEL_6;
  }
LABEL_5:
  LocalFree(v8);
LABEL_6:
  SetLastError(LastError);
  return v10;
}

```

## disassembly

```asm
0x1800650b0  push    rbp
0x1800650b2  push    rbx
0x1800650b3  push    rsi
0x1800650b4  push    rdi
0x1800650b5  push    r12
0x1800650b7  push    r14
0x1800650b9  push    r15
0x1800650bb  mov     rbp, rsp
0x1800650be  sub     rsp, 80h
0x1800650c5  mov     rax, cs:__security_cookie
0x1800650cc  xor     rax, rsp
0x1800650cf  mov     [rbp+var_10], rax
0x1800650d3  mov     rax, [rbp+arg_28]
0x1800650d7  mov     rsi, rcx
0x1800650da  mov     [rbp+pAcl], rcx
0x1800650de  xor     r14d, r14d
0x1800650e1  xor     ecx, ecx
0x1800650e3  mov     [rbp+AccessMask], r8d
0x1800650e7  mov     [rbp+var_28], rax
0x1800650eb  mov     r15, rdx
0x1800650ee  mov     [rbp+pAclInformation], rcx
0x1800650f2  mov     [rbp+var_18], ecx
0x1800650f5  mov     [rbp+pAce], rcx
0x1800650f9  test    rsi, rsi
0x1800650fc  jnz     short loc_18006510D
0x1800650fe  mov     [rbp+var_50], 1
0x180065105  mov     edi, [rbp+var_50]
0x180065108  jmp     loc_180065308
0x18006510d  xor     edi, edi
0x18006510f  mov     rcx, r15; pSid
0x180065112  mov     [rbp+var_50], edi
0x180065115  call    cs:__imp_IsValidSid
0x18006511b  test    eax, eax
0x18006511d  jnz     short loc_180065153
0x18006511f  lea     ebx, [rdi+57h]
0x180065122  mov     rcx, r14; hMem
0x180065125  call    cs:__imp_LocalFree
0x18006512b  mov     ecx, ebx; dwErrCode
0x18006512d  call    cs:__imp_SetLastError
0x180065133  mov     eax, edi
0x180065135  mov     rcx, [rbp+var_10]
0x180065139  xor     rcx, rsp; StackCookie
0x18006513c  call    __security_check_cookie
0x180065141  add     rsp, 80h
0x180065148  pop     r15
0x18006514a  pop     r14
0x18006514c  pop     r12
0x18006514e  pop     rdi
0x18006514f  pop     rsi
0x180065150  pop     rbx
0x180065151  pop     rbp
0x180065152  retn
0x180065153  mov     r9d, 2; dwAclInformationClass
0x180065159  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x18006515d  mov     rcx, rsi; pAcl
0x180065160  lea     r8d, [r9+0Ah]; nAclInformationLength
0x180065164  call    cs:__imp_GetAclInformation
0x18006516a  test    eax, eax
0x18006516c  jnz     short loc_180065178
0x18006516e  call    cs:__imp_GetLastError
0x180065174  mov     ebx, eax
0x180065176  jmp     short loc_180065122
0x180065178  xor     r12d, r12d
0x18006517b  xor     ebx, ebx
0x18006517d  lea     edi, [rbx+1]
0x180065180  cmp     ebx, dword ptr [rbp+pAclInformation]
0x180065183  jnb     short loc_1800651B9
0x180065185  lea     r8, [rbp+pAce]; pAce
0x180065189  mov     edx, ebx; dwAceIndex
0x18006518b  mov     rcx, rsi; pAcl
0x18006518e  call    cs:__imp_GetAce
0x180065194  test    eax, eax
0x180065196  jz      short loc_1800651DE
0x180065198  mov     rdx, [rbp+pAce]
0x18006519c  cmp     [rdx], r12b
0x18006519f  jnz     short loc_1800651B2
0x1800651a1  add     rdx, 8; pSid2
0x1800651a5  mov     rcx, r15; pSid1
0x1800651a8  call    cs:__imp_EqualSid
0x1800651ae  test    eax, eax
0x1800651b0  jnz     short loc_1800651B6
0x1800651b2  add     ebx, edi
0x1800651b4  jmp     short loc_180065180
0x1800651b6  mov     r12d, edi
0x1800651b9  mov     ebx, 8
0x1800651be  mov     esi, dword ptr [rbp+pAclInformation+4]
0x1800651c1  mov     dword ptr [rbp+var_48], esi
0x1800651c4  cmp     [rbp+arg_20], r14d
0x1800651c8  jz      short loc_1800651EE
0x1800651ca  test    r12d, r12d
0x1800651cd  jnz     short loc_18006521E
0x1800651cf  mov     rcx, r15; pSid
0x1800651d2  call    cs:__imp_GetLengthSid
0x1800651d8  add     esi, ebx
0x1800651da  add     esi, eax
0x1800651dc  jmp     short loc_18006521E
0x1800651de  call    cs:__imp_GetLastError
0x1800651e4  mov     ebx, eax
0x1800651e6  mov     edi, r12d
0x1800651e9  jmp     loc_180065122
0x1800651ee  test    r12d, r12d
0x1800651f1  jz      short loc_18006521E
0x1800651f3  mov     rcx, r15; pSid
0x1800651f6  call    cs:__imp_GetLengthSid
0x1800651fc  lea     r8, [rbp+var_48]; unsigned int *
0x180065200  mov     ecx, esi; unsigned int
0x180065202  lea     edx, [rbx+rax]; unsigned int
0x180065205  call    ?ULongSub@@YAJKKPEAK@Z; ULongSub(ulong,ulong,ulong *)
0x18006520a  test    eax, eax
0x18006520c  jns     short loc_18006521B
0x18006520e  mov     ebx, 216h
0x180065213  mov     edi, r14d
0x180065216  jmp     loc_180065122
0x18006521b  mov     esi, dword ptr [rbp+var_48]
0x18006521e  mov     edx, esi; uBytes
0x180065220  mov     ecx, 40h ; '@'; uFlags
0x180065225  call    cs:__imp_LocalAlloc
0x18006522b  mov     r14, rax
0x18006522e  test    rax, rax
0x180065231  jnz     short loc_18006523B
0x180065233  mov     edi, [rbp+var_50]
0x180065236  jmp     loc_180065122
0x18006523b  mov     ebx, 2
0x180065240  mov     edx, esi; nAclLength
0x180065242  mov     r8d, ebx; dwAclRevision
0x180065245  mov     rcx, r14; pAcl
0x180065248  call    cs:__imp_InitializeAcl
0x18006524e  test    eax, eax
0x180065250  jnz     short loc_18006525C
0x180065252  call    cs:__imp_GetLastError
0x180065258  mov     ebx, eax
0x18006525a  jmp     short loc_180065233
0x18006525c  cmp     [rbp+arg_20], 0
0x180065260  jz      short loc_18006529B
0x180065262  mov     r8d, [rbp+AccessMask]; AccessMask
0x180065266  mov     r9, r15; pSid
0x180065269  mov     edx, ebx; dwAceRevision
0x18006526b  mov     [rbp+var_48], 0
0x180065273  mov     rcx, r14; pAcl
0x180065276  call    cs:__imp_AddAccessAllowedAce
0x18006527c  test    eax, eax
0x18006527e  jz      short loc_180065252
0x180065280  lea     r8, [rbp+var_48]; pAce
0x180065284  xor     edx, edx; dwAceIndex
0x180065286  mov     rcx, r14; pAcl
0x180065289  call    cs:__imp_GetAce
0x18006528f  test    eax, eax
0x180065291  jz      short loc_180065252
0x180065293  mov     rax, [rbp+var_48]
0x180065297  mov     byte ptr [rax+1], 0
0x18006529b  mov     rsi, [rbp+pAcl]
0x18006529f  xor     ebx, ebx
0x1800652a1  cmp     ebx, dword ptr [rbp+pAclInformation]
0x1800652a4  jnb     short loc_180065304
0x1800652a6  lea     r8, [rbp+pAce]; pAce
0x1800652aa  mov     edx, ebx; dwAceIndex
0x1800652ac  mov     rcx, rsi; pAcl
0x1800652af  call    cs:__imp_GetAce
0x1800652b5  test    eax, eax
0x1800652b7  jz      short loc_180065252
0x1800652b9  test    r12d, r12d
0x1800652bc  jz      short loc_1800652D9
0x1800652be  mov     r9, [rbp+pAce]
0x1800652c2  cmp     byte ptr [r9], 0
0x1800652c6  jnz     short loc_1800652DD
0x1800652c8  lea     rdx, [r9+8]; pSid2
0x1800652cc  mov     rcx, r15; pSid1
0x1800652cf  call    cs:__imp_EqualSid
0x1800652d5  test    eax, eax
0x1800652d7  jnz     short loc_180065300
0x1800652d9  mov     r9, [rbp+pAce]; pAceList
0x1800652dd  movzx   eax, word ptr [r9+2]
0x1800652e2  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x1800652e6  mov     edx, 2; dwAceRevision
0x1800652eb  mov     [rsp+80h+nAceListLength], eax; nAceListLength
0x1800652ef  mov     rcx, r14; pAcl
0x1800652f2  call    cs:__imp_AddAce
0x1800652f8  test    eax, eax
0x1800652fa  jz      loc_180065252
0x180065300  add     ebx, edi
0x180065302  jmp     short loc_1800652A1
0x180065304  mov     rax, [rbp+var_28]
0x180065308  xor     ebx, ebx
0x18006530a  test    rax, rax
0x18006530d  jz      loc_180065122
0x180065313  mov     [rax], r14
0x180065316  jmp     loc_18006512B
```
