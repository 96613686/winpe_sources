# LsaDbpOpenTrustedDomain(void *,void *,ulong,void * *,ulong)

- ea: `0x18000c1ac`
- end: `0x18000c3fa`
- name: `?LsaDbpOpenTrustedDomain@@YAJPEAX0KPEAPEAXK@Z`
- size: `590`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, PSID Sid@<rdx>, unsigned int@<r8d>, void **@<r9>, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000c960`
- `0x18000d5e0`

## callees

- `0x180001fb8`
- `0x18000a080`
- `0x18000beb4`
- `0x18000c1ac`
- `0x18003ad30`

## import_xrefs

- `LSASRV!LsapDbOpenObject` at `0x18000c36f`
- `LSASRV!LsapDbOpenObject` at `0x18000c36f`
- `LSASRV!LsapDbDereferenceObject` at `0x18000c3a9`
- `LSASRV!LsapDbDereferenceObject` at `0x18000c3a9`
- `LSASRV!LsapDbReleaseLockEx` at `0x18000c3de`
- `LSASRV!LsapDbReleaseLockEx` at `0x18000c3de`
- `LSASRV!LsapDbApplyTransaction` at `0x18000c3d1`
- `LSASRV!LsapDbApplyTransaction` at `0x18000c3d1`
- `LSASRV!LsapDbSidToLogicalNameObject` at `0x18000c328`
- `LSASRV!LsapDbSidToLogicalNameObject` at `0x18000c328`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18000c297`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18000c297`
- `LSASRV!LsapDbReferenceObject` at `0x18000c23e`
- `LSASRV!LsapDbReferenceObject` at `0x18000c23e`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000c2c5`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000c2ea`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000c319`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000c2c5`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000c2ea`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000c319`
- `LSASRV!LsapAllocateLsaHeap` at `0x18000c2d8`
- `LSASRV!LsapAllocateLsaHeap` at `0x18000c2d8`
- `ntdll!RtlValidSid` at `0x18000c213`
- `ntdll!RtlValidSid` at `0x18000c213`
- `ntdll!RtlFreeUnicodeString` at `0x18000c37b`
- `ntdll!RtlFreeUnicodeString` at `0x18000c37b`

## pseudocode

```c
__int64 __fastcall LsaDbpOpenTrustedDomain(_BYTE *a1, PSID Sid, unsigned int a3, void **a4, unsigned int a5)
{
  int LockTrustedDomainList; // ebx
  unsigned int v10; // r15d
  unsigned int v11; // edi
  __int64 v12; // rcx
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned int v17; // [rsp+20h] [rbp-81h]
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-71h] BYREF
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v19; // [rsp+40h] [rbp-61h] BYREF
  __int128 v20; // [rsp+48h] [rbp-59h] BYREF
  PSID v21; // [rsp+58h] [rbp-49h]
  _DWORD v22[4]; // [rsp+60h] [rbp-41h] BYREF
  void *v23; // [rsp+70h] [rbp-31h]
  struct _UNICODE_STRING *p_UnicodeString; // [rsp+78h] [rbp-29h]
  int v25; // [rsp+80h] [rbp-21h]
  __int64 v26; // [rsp+88h] [rbp-19h]
  __int64 v27; // [rsp+90h] [rbp-11h]
  PSID v28; // [rsp+98h] [rbp-9h]
  char v29; // [rsp+A0h] [rbp-1h]
  unsigned int v30; // [rsp+A4h] [rbp+3h]
  void *v31; // [rsp+100h] [rbp+5Fh] BYREF

  v31 = a1;
  memset_0(v22, 0, 0x48u);
  UnicodeString = 0;
  if ( !HIBYTE(word_18004706B) )
    return (unsigned int)-1073741135;
  LockTrustedDomainList = LsaDbpCheckIfCallerHasAccessToTDOs(a1);
  if ( LockTrustedDomainList < 0 )
    return (unsigned int)LockTrustedDomainList;
  if ( !RtlValidSid(Sid) )
    return (unsigned int)-1073741811;
  v10 = a5;
  v17 = a5;
  LockTrustedDomainList = LsapDbReferenceObject(v31, 0, 1, 2);
  if ( LockTrustedDomainList < 0 )
    return (unsigned int)LockTrustedDomainList;
  v22[0] = 2;
  v22[1] = 1;
  v11 = v10 | 1;
  v28 = Sid;
  v29 = 0;
  v30 = a3;
  if ( (v10 & 1) == 0 )
    v11 = v10;
  if ( !HIBYTE(word_18004706B) )
  {
    LockTrustedDomainList = LsapDbSidToLogicalNameObject(Sid, &UnicodeString);
    if ( LockTrustedDomainList < 0 )
      goto LABEL_18;
    goto LABEL_17;
  }
  v19 = 0;
  v20 = 0;
  v21 = 0;
  LockTrustedDomainList = LsapDbExpAcquireReadLockTrustedDomainList(0);
  if ( LockTrustedDomainList >= 0 )
  {
    v21 = Sid;
    v20 = 0;
    LockTrustedDomainList = LsaDbpLookupEntryTrustedDomainList((struct _LSAPR_TRUST_INFORMATION *)&v20, &v19);
    if ( LockTrustedDomainList < 0 )
    {
      LsapDbExpReleaseLockTrustedDomainList(v12);
      goto LABEL_18;
    }
    v13 = v19;
    UnicodeString.Buffer = (PWSTR)LsapAllocateLsaHeap(*((unsigned __int16 *)v19 + 9));
    if ( !UnicodeString.Buffer )
    {
      LsapDbExpReleaseLockTrustedDomainList(v14);
      LockTrustedDomainList = -1073741670;
      goto LABEL_18;
    }
    UnicodeString.Length = *((_WORD *)v13 + 8);
    UnicodeString.MaximumLength = *((_WORD *)v13 + 9);
    memcpy_0(UnicodeString.Buffer, *((const void **)v13 + 3), UnicodeString.Length);
    LsapDbExpReleaseLockTrustedDomainList(v15);
LABEL_17:
    v23 = v31;
    v22[2] = 48;
    p_UnicodeString = &UnicodeString;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    LockTrustedDomainList = LsapDbOpenObject(v22, a3, v10, a4, v17);
    RtlFreeUnicodeString(&UnicodeString);
    if ( LockTrustedDomainList >= 0 )
      goto LABEL_19;
  }
LABEL_18:
  *a4 = 0;
  LsapDbDereferenceObject(&v31, 1, 2, v11, 0, LockTrustedDomainList);
LABEL_19:
  if ( (v10 & 1) != 0 )
  {
    LsapDbApplyTransaction(v31, 50331648, 0);
    LsapDbReleaseLockEx(2);
  }
  return (unsigned int)LockTrustedDomainList;
}

```

## disassembly

```asm
0x18000c1ac  mov     [rsp-8+arg_0], rcx
0x18000c1b1  push    rbp
0x18000c1b2  push    rbx
0x18000c1b3  push    rsi
0x18000c1b4  push    rdi
0x18000c1b5  push    r12
0x18000c1b7  push    r13
0x18000c1b9  push    r14
0x18000c1bb  push    r15
0x18000c1bd  lea     rbp, [rsp-17h]
0x18000c1c2  sub     rsp, 0B8h
0x18000c1c9  mov     rsi, rdx
0x18000c1cc  mov     r12d, r8d
0x18000c1cf  xor     edx, edx; Val
0x18000c1d1  mov     rbx, rcx
0x18000c1d4  lea     rcx, [rbp+4Fh+var_90]; void *
0x18000c1d8  mov     r13, r9
0x18000c1db  lea     r8d, [rdx+48h]; Size
0x18000c1df  call    memset_0
0x18000c1e4  cmp     byte ptr cs:word_18004706B+1, 0
0x18000c1eb  xorps   xmm0, xmm0
0x18000c1ee  movups  xmmword ptr [rbp+4Fh+UnicodeString.Length], xmm0
0x18000c1f2  jnz     short loc_18000C1FE
0x18000c1f4  mov     ebx, 0C00002B1h
0x18000c1f9  jmp     loc_18000C3E4
0x18000c1fe  mov     rcx, rbx; void *
0x18000c201  call    ?LsaDbpCheckIfCallerHasAccessToTDOs@@YAJQEAX@Z; LsaDbpCheckIfCallerHasAccessToTDOs(void * const)
0x18000c206  mov     ebx, eax
0x18000c208  test    eax, eax
0x18000c20a  js      loc_18000C3E4
0x18000c210  mov     rcx, rsi; Sid
0x18000c213  call    cs:__imp_RtlValidSid
0x18000c219  test    al, al
0x18000c21b  jnz     short loc_18000C227
0x18000c21d  mov     ebx, 0C000000Dh
0x18000c222  jmp     loc_18000C3E4
0x18000c227  mov     r15d, [rbp+4Fh+arg_20]
0x18000c22b  xor     edx, edx
0x18000c22d  mov     rcx, [rbp+4Fh+arg_0]
0x18000c231  mov     [rsp+0F0h+var_D0], r15d
0x18000c236  lea     r9d, [rdx+2]
0x18000c23a  lea     r8d, [rdx+1]
0x18000c23e  call    cs:__imp_LsapDbReferenceObject
0x18000c244  mov     ebx, eax
0x18000c246  test    eax, eax
0x18000c248  js      loc_18000C3E4
0x18000c24e  xor     ecx, ecx
0x18000c250  mov     [rbp+4Fh+var_90], 2
0x18000c257  mov     edi, r15d
0x18000c25a  mov     [rbp+4Fh+var_8C], 1
0x18000c261  or      edi, 1
0x18000c264  mov     [rbp+4Fh+var_58], rsi
0x18000c268  mov     r14d, r15d
0x18000c26b  mov     [rbp+4Fh+var_50], cl
0x18000c26e  and     r14d, 1
0x18000c272  mov     [rbp+4Fh+var_4C], r12d
0x18000c276  cmovz   edi, r15d
0x18000c27a  cmp     byte ptr cs:word_18004706B+1, cl
0x18000c280  jz      loc_18000C321
0x18000c286  xorps   xmm0, xmm0
0x18000c289  mov     [rbp+4Fh+var_B0], rcx
0x18000c28d  xor     eax, eax
0x18000c28f  movups  [rbp+4Fh+var_A8], xmm0
0x18000c293  mov     [rbp+4Fh+var_98], rax
0x18000c297  call    cs:__imp_LsapDbExpAcquireReadLockTrustedDomainList
0x18000c29d  mov     ebx, eax
0x18000c29f  test    eax, eax
0x18000c2a1  js      loc_18000C385
0x18000c2a7  xorps   xmm0, xmm0
0x18000c2aa  mov     [rbp+4Fh+var_98], rsi
0x18000c2ae  lea     rdx, [rbp+4Fh+var_B0]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18000c2b2  lea     rcx, [rbp+4Fh+var_A8]; struct _LSAPR_TRUST_INFORMATION *
0x18000c2b6  movups  [rbp+4Fh+var_A8], xmm0
0x18000c2ba  call    ?LsaDbpLookupEntryTrustedDomainList@@YAJPEAU_LSAPR_TRUST_INFORMATION@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupEntryTrustedDomainList(_LSAPR_TRUST_INFORMATION *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18000c2bf  mov     ebx, eax
0x18000c2c1  test    eax, eax
0x18000c2c3  jns     short loc_18000C2D0
0x18000c2c5  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x18000c2cb  jmp     loc_18000C385
0x18000c2d0  mov     rbx, [rbp+4Fh+var_B0]
0x18000c2d4  movzx   ecx, word ptr [rbx+12h]
0x18000c2d8  call    cs:__imp_LsapAllocateLsaHeap
0x18000c2de  mov     [rbp+4Fh+UnicodeString.Buffer], rax
0x18000c2e2  mov     r9, rax
0x18000c2e5  test    rax, rax
0x18000c2e8  jnz     short loc_18000C2FA
0x18000c2ea  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x18000c2f0  mov     ebx, 0C000009Ah
0x18000c2f5  jmp     loc_18000C385
0x18000c2fa  movzx   ecx, word ptr [rbx+10h]
0x18000c2fe  mov     [rbp+4Fh+UnicodeString.Length], cx
0x18000c302  mov     r8d, ecx; Size
0x18000c305  movzx   eax, word ptr [rbx+12h]
0x18000c309  mov     rcx, r9; void *
0x18000c30c  mov     [rbp+4Fh+UnicodeString.MaximumLength], ax
0x18000c310  mov     rdx, [rbx+18h]; Src
0x18000c314  call    memcpy_0
0x18000c319  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x18000c31f  jmp     short loc_18000C334
0x18000c321  lea     rdx, [rbp+4Fh+UnicodeString]
0x18000c325  mov     rcx, rsi
0x18000c328  call    cs:__imp_LsapDbSidToLogicalNameObject
0x18000c32e  mov     ebx, eax
0x18000c330  test    eax, eax
0x18000c332  js      short loc_18000C385
0x18000c334  mov     rax, [rbp+4Fh+arg_0]
0x18000c338  lea     rcx, [rbp+4Fh+var_90]
0x18000c33c  mov     [rbp+4Fh+var_80], rax
0x18000c340  mov     r9, r13
0x18000c343  lea     rax, [rbp+4Fh+UnicodeString]
0x18000c347  mov     [rbp+4Fh+var_88], 30h ; '0'
0x18000c34e  mov     r8d, r15d
0x18000c351  mov     [rbp+4Fh+var_78], rax
0x18000c355  mov     edx, r12d
0x18000c358  mov     [rbp+4Fh+var_70], 0
0x18000c35f  mov     [rbp+4Fh+var_68], 0
0x18000c367  mov     [rbp+4Fh+var_60], 0
0x18000c36f  call    cs:__imp_LsapDbOpenObject
0x18000c375  lea     rcx, [rbp+4Fh+UnicodeString]; UnicodeString
0x18000c379  mov     ebx, eax
0x18000c37b  call    cs:__imp_RtlFreeUnicodeString
0x18000c381  test    ebx, ebx
0x18000c383  jns     short loc_18000C3C0
0x18000c385  mov     edx, 1
0x18000c38a  mov     [rsp+0F0h+var_C8], ebx
0x18000c38e  mov     r9d, edi
0x18000c391  mov     qword ptr [r13+0], 0
0x18000c399  lea     rcx, [rbp+4Fh+arg_0]
0x18000c39d  mov     [rsp+0F0h+var_D0], 0
0x18000c3a5  lea     r8d, [rdx+1]
0x18000c3a9  call    cs:__imp_LsapDbDereferenceObject
0x18000c3af  test    r14d, r14d
0x18000c3b2  jz      short loc_18000C3BA
0x18000c3b4  and     edi, 0FFFFFFFEh
0x18000c3b7  or      edi, 2
0x18000c3ba  test    ebx, ebx
0x18000c3bc  js      short loc_18000C3C0
0x18000c3be  mov     ebx, eax
0x18000c3c0  test    r14b, r14b
0x18000c3c3  jz      short loc_18000C3E4
0x18000c3c5  mov     rcx, [rbp+4Fh+arg_0]
0x18000c3c9  xor     r8d, r8d
0x18000c3cc  mov     edx, 3000000h
0x18000c3d1  call    cs:__imp_LsapDbApplyTransaction
0x18000c3d7  mov     edx, edi
0x18000c3d9  mov     ecx, 2
0x18000c3de  call    cs:__imp_LsapDbReleaseLockEx
0x18000c3e4  mov     eax, ebx
0x18000c3e6  add     rsp, 0B8h
0x18000c3ed  pop     r15
0x18000c3ef  pop     r14
0x18000c3f1  pop     r13
0x18000c3f3  pop     r12
0x18000c3f5  pop     rdi
0x18000c3f6  pop     rsi
0x18000c3f7  pop     rbx
0x18000c3f8  pop     rbp
0x18000c3f9  retn
```
