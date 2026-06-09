# Smb2PackCredentialsIntoConnectInfo

- ea: `0x1400104c0`
- end: `0x1400108e7`
- name: `Smb2PackCredentialsIntoConnectInfo`
- size: `1063`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, __int64, unsigned int *, unsigned int, _DWORD *, char)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140018110`
- `0x1400189b0`
- `0x14003081c`

## callees

- `0x1400104c0`
- `0x140012210`
- `0x1400122d0`
- `0x1400282b0`
- `0x140030b3c`
- `0x140037190`
- `0x140050280`
- `0x1400502e4`
- `0x140050370`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140010648`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140039f4c`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140010648`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140039f4c`
- `ntoskrnl!LsaFreeReturnBuffer` at `0x1400108d6`
- `ntoskrnl!LsaFreeReturnBuffer` at `0x1400108d6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140039fa5`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140039fa5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140039f61`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140039f61`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010675`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010675`
- `ksecdd!FreeContextBuffer` at `0x1400105e3`
- `ksecdd!FreeContextBuffer` at `0x1400105e3`
- `ksecdd!QueryContextAttributesW` at `0x140039f8d`
- `ksecdd!QueryContextAttributesW` at `0x140039f8d`
- `ksecdd!GetSecurityUserInfo` at `0x140010573`
- `ksecdd!GetSecurityUserInfo` at `0x140010573`
- `ksecdd!MapSecurityError` at `0x140010657`
- `ksecdd!MapSecurityError` at `0x140010657`
- `mrxsmb!SmbCeDereferenceBindingObject` at `0x140039fb4`
- `mrxsmb!SmbCeDereferenceBindingObject` at `0x140039fb4`
- `mrxsmb!SmbCeReferenceBindingObject` at `0x140039f2b`
- `mrxsmb!SmbCeReferenceBindingObject` at `0x140039f2b`

## pseudocode

```c
__int64 __fastcall Smb2PackCredentialsIntoConnectInfo(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int *a6,
        unsigned int a7,
        _DWORD *a8,
        char a9)
{
  int v12; // ecx
  __int64 v13; // rax
  unsigned int SecurityUserInfo; // ebx
  __int64 v16; // rbx
  SECURITY_STATUS v17; // r12d
  KIRQL v18; // r13
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 i; // rax
  struct _SecHandle *v23; // r15
  __int64 v24; // rcx
  unsigned int v25; // edx
  SECURITY_STRING *p_LogonDomainName; // r13
  __int16 v27; // ax
  PSecurityUserData v28; // rdi
  unsigned __int16 *v29; // rcx
  size_t v30; // r12
  size_t Length; // r14
  unsigned __int16 v32; // ax
  __int64 v33; // rax
  unsigned __int16 v34; // ax
  __int64 v35; // r10
  unsigned int v36; // eax
  __int64 v37; // rsi
  void *v38; // rdx
  void *v39; // rcx
  __int64 v40; // rdx
  __int16 v41; // si
  PWSTR Buffer; // rdx
  void *v43; // rcx
  __int64 v44; // rdx
  _LUID LogonId; // [rsp+48h] [rbp-51h] BYREF
  PVOID pvContextBuffer; // [rsp+50h] [rbp-49h] BYREF
  PSecurityUserData UserInformation; // [rsp+58h] [rbp-41h] BYREF
  __int128 v48; // [rsp+60h] [rbp-39h] BYREF
  __int128 v49; // [rsp+70h] [rbp-29h] BYREF
  _QWORD v50[2]; // [rsp+80h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-9h] BYREF
  unsigned __int16 *p_Length; // [rsp+E0h] [rbp+47h]

  UserInformation = 0;
  pvContextBuffer = 0;
  DestinationString = 0;
  v49 = 0;
  v48 = 0;
  if ( a1 == 1 )
  {
    v13 = *(_QWORD *)(a2 + 128);
    if ( v13 )
    {
      p_LogonDomainName = *(SECURITY_STRING **)(v13 + 32);
      p_Length = *(unsigned __int16 **)(v13 + 16);
      LogonId = (_LUID)p_LogonDomainName;
      if ( p_Length && p_LogonDomainName )
      {
        SecurityUserInfo = 0;
        goto LABEL_32;
      }
    }
    else
    {
      p_Length = 0;
      LogonId = 0;
    }
  }
  else
  {
    p_Length = 0;
    LogonId = 0;
    v12 = a1 - 2;
    if ( v12 )
    {
      if ( v12 != 1 )
      {
LABEL_11:
        SecurityUserInfo = -1073741726;
        goto LABEL_14;
      }
      goto LABEL_8;
    }
  }
  if ( *(_DWORD *)(a2 + 12) )
    goto LABEL_8;
  v16 = *(_QWORD *)(a2 + 24);
  v17 = -1073741309;
  v18 = SmbCeAcquireSpinLock(v16, 0, a3, a4);
  for ( i = SmbCeGetFirstBindingObjectEx(a2, v19, v20, v21); ; i = SmbCeGetNextBindingObject(a2) )
  {
    v23 = (struct _SecHandle *)i;
    if ( !i )
    {
      *(_DWORD *)(v16 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v16 + 1920), v18);
      goto LABEL_22;
    }
    if ( !*(_DWORD *)(i + 12) )
      break;
  }
  SmbCeReferenceBindingObject(i);
  *(_DWORD *)(v16 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v16 + 1920), v18);
  ExAcquirePushLockSharedEx(&v23[28].dwUpper, 0);
  if ( v23[29].dwLower != -1 && v23[29].dwUpper != -1 )
    v17 = QueryContextAttributesW(v23 + 29, 1u, &pvContextBuffer);
  ExReleasePushLockSharedEx(&v23[28].dwUpper, 0);
  SmbCeDereferenceBindingObject(v23);
LABEL_22:
  SecurityUserInfo = MapSecurityError(v17);
  if ( SecurityUserInfo )
    goto LABEL_8;
  RtlInitUnicodeString(&DestinationString, (PCWSTR)pvContextBuffer);
  v24 = 0;
  v25 = DestinationString.Length >> 1;
  if ( !v25 )
  {
LABEL_26:
    if ( (unsigned int)v24 < v25 )
      goto LABEL_27;
LABEL_8:
    LogonId = (_LUID)996LL;
    if ( *(_DWORD *)(a2 + 96) != `RxIsGlobalMappingLuid'::`2'::globalMappingLuid
      || *(_DWORD *)(a2 + 100) != dword_140046144 )
    {
      LogonId = *(_LUID *)(a2 + 96);
    }
    SecurityUserInfo = GetSecurityUserInfo(&LogonId, 1u, &UserInformation);
    if ( SecurityUserInfo )
      goto LABEL_11;
    v28 = UserInformation;
    p_LogonDomainName = &UserInformation->LogonDomainName;
    goto LABEL_31;
  }
  while ( DestinationString.Buffer[v24] != 92 )
  {
    v24 = (unsigned int)(v24 + 1);
    if ( (unsigned int)v24 >= v25 )
      goto LABEL_26;
  }
LABEL_27:
  p_LogonDomainName = (SECURITY_STRING *)LogonId;
  if ( LogonId )
  {
    v27 = v48;
  }
  else
  {
    *((_QWORD *)&v48 + 1) = DestinationString.Buffer;
    v27 = 2 * v24;
    p_LogonDomainName = (SECURITY_STRING *)&v48;
    WORD1(v48) = 2 * v24;
    LOWORD(v48) = 2 * v24;
  }
  if ( !p_Length )
  {
    v28 = (PSecurityUserData)&v49;
    WORD1(v49) = DestinationString.Length - v27 - 2;
    LOWORD(v49) = WORD1(v49);
    *((_QWORD *)&v49 + 1) = &DestinationString.Buffer[v24 + 1];
LABEL_31:
    p_Length = &v28->UserName.Length;
  }
LABEL_32:
  v29 = p_Length;
  v50[0] = 131074;
  v30 = *p_Length;
  v50[1] = L"\\";
  if ( *a6 >= (unsigned int)v30 )
  {
    v32 = *p_Length;
    if ( a9 )
    {
      *(_WORD *)a3 = v32;
      *(_WORD *)(a3 + 2) = *p_Length;
    }
    else
    {
      RtlWriteUShortToUser(a3, v32);
      RtlWriteUShortToUser(a3 + 2, *p_Length);
      v29 = p_Length;
    }
    *a6 -= v30;
    v33 = *a6;
    if ( a8 )
    {
      *a8 += v30;
      v33 = *a6;
    }
    v38 = (void *)*((_QWORD *)v29 + 1);
    v39 = (void *)(v33 + a5);
    if ( a9 )
      RtlCopyVolatileMemory(v39, v38, v30);
    else
      RtlCopyToUser(v39, v38, v30);
    v35 = a5;
    v40 = a5 + *a6 - (unsigned __int64)a7;
    if ( a9 )
    {
      *(_QWORD *)(a3 + 8) = v40;
    }
    else
    {
      RtlWriteULong64ToUser(a3 + 8, v40);
      v35 = a5;
    }
    if ( a4 )
    {
      Length = p_LogonDomainName->Length;
      if ( *a6 >= (unsigned int)Length )
      {
        v34 = p_LogonDomainName->Length;
        if ( a9 )
        {
          *(_WORD *)a4 = v34;
          *(_WORD *)(a4 + 2) = p_LogonDomainName->Length;
        }
        else
        {
          RtlWriteUShortToUser(a4, v34);
          RtlWriteUShortToUser(a4 + 2, p_LogonDomainName->Length);
          v35 = a5;
        }
        *a6 -= Length;
        v36 = *a6;
        if ( a8 )
        {
          *a8 += Length;
          v36 = *a6;
        }
        Buffer = p_LogonDomainName->Buffer;
        v43 = (void *)(v35 + v36);
        if ( a9 )
          RtlCopyVolatileMemory(v43, Buffer, Length);
        else
          RtlCopyToUser(v43, Buffer, Length);
        v44 = a5 + *a6 - (unsigned __int64)a7;
        if ( a9 )
          *(_QWORD *)(a4 + 8) = v44;
        else
          RtlWriteULong64ToUser(a4 + 8, v44);
      }
      else
      {
        if ( a9 )
        {
          *(_WORD *)a4 = 0;
          *(_WORD *)(a4 + 2) = 0;
        }
        else
        {
          RtlWriteUShortToUser(a4, 0);
          RtlWriteUShortToUser(a4 + 2, 0);
        }
        SecurityUserInfo = -1073741789;
      }
    }
    else
    {
      v37 = *p_Length;
      if ( PackStringIntoConnectInfo(a3, (unsigned __int16 *)v50, v35, a6, a7, a8, a9) )
      {
        if ( PackStringIntoConnectInfo(a3, &p_LogonDomainName->Length, a5, a6, a7, a8, a9) )
        {
          v41 = *(_WORD *)a3 + v37 + 2;
          *(_WORD *)(a3 + 2) = v41;
          *(_WORD *)a3 = v41;
        }
        else
        {
          SecurityUserInfo = -1073741789;
        }
      }
      else
      {
        SecurityUserInfo = -1073741789;
      }
    }
  }
  else
  {
    if ( a9 )
    {
      *(_WORD *)a3 = 0;
      *(_WORD *)(a3 + 2) = 0;
    }
    else
    {
      RtlWriteUShortToUser(a3, 0);
      RtlWriteUShortToUser(a3 + 2, 0);
    }
    SecurityUserInfo = -1073741789;
  }
LABEL_14:
  if ( pvContextBuffer )
    FreeContextBuffer(pvContextBuffer);
  if ( UserInformation )
    LsaFreeReturnBuffer(UserInformation);
  return SecurityUserInfo;
}

```

## disassembly

```asm
0x1400104c0  mov     rax, rsp
0x1400104c3  push    rbp
0x1400104c4  push    rbx
0x1400104c5  lea     rbp, [rax-37h]
0x1400104c9  sub     rsp, 0B8h
0x1400104d0  mov     [rax+8], rsi
0x1400104d4  xorps   xmm0, xmm0
0x1400104d7  mov     [rax+18h], rdi
0x1400104db  xorps   xmm1, xmm1
0x1400104de  mov     [rax+20h], r12
0x1400104e2  mov     rdi, rdx
0x1400104e5  xor     edx, edx
0x1400104e7  mov     [rax-18h], r13
0x1400104eb  mov     [rax-20h], r14
0x1400104ef  mov     rsi, r9
0x1400104f2  mov     [rax-28h], r15
0x1400104f6  mov     r14, r8
0x1400104f9  mov     [rbp+2Fh+UserInformation], rdx
0x1400104fd  mov     [rbp+2Fh+pvContextBuffer], rdx
0x140010501  movups  xmmword ptr [rbp+2Fh+DestinationString.Length], xmm0
0x140010505  movups  [rbp+2Fh+var_58], xmm1
0x140010509  movups  [rbp+2Fh+var_68], xmm0
0x14001050d  cmp     ecx, 1
0x140010510  jz      short loc_140010526
0x140010512  mov     [rbp+2Fh+arg_8], rdx
0x140010516  mov     qword ptr [rbp+2Fh+LogonId.LowPart], rdx
0x14001051a  sub     ecx, 2
0x14001051d  jz      short loc_14001053E
0x14001051f  cmp     ecx, 1
0x140010522  jnz     short loc_140010589
0x140010524  jmp     short loc_140010547
0x140010526  mov     rax, [rdi+80h]
0x14001052d  test    rax, rax
0x140010530  jnz     loc_140010784
0x140010536  mov     [rbp+2Fh+arg_8], rdx
0x14001053a  mov     qword ptr [rbp+2Fh+LogonId.LowPart], rdx
0x14001053e  cmp     [rdi+0Ch], edx
0x140010541  jz      loc_140010609
0x140010547  mov     eax, cs:?globalMappingLuid@?1??RxIsGlobalMappingLuid@@9@9; `RxIsGlobalMappingLuid'::`2'::globalMappingLuid
0x14001054d  mov     qword ptr [rbp+2Fh+LogonId.LowPart], 3E4h
0x140010555  cmp     [rdi+60h], eax
0x140010558  jz      loc_140010877
0x14001055e  mov     rax, [rdi+60h]
0x140010562  mov     qword ptr [rbp+2Fh+LogonId.LowPart], rax
0x140010566  lea     r8, [rbp+2Fh+UserInformation]; UserInformation
0x14001056a  mov     edx, 1; Flags
0x14001056f  lea     rcx, [rbp+2Fh+LogonId]; LogonId
0x140010573  call    cs:__imp_GetSecurityUserInfo
0x14001057a  nop     dword ptr [rax+rax+00h]
0x14001057f  mov     ebx, eax
0x140010581  test    eax, eax
0x140010583  jz      loc_14001088B
0x140010589  mov     ebx, 0C0000062h
0x14001058e  jmp     short loc_1400105AA
0x140010590  xor     edx, edx
0x140010592  mov     rcx, r14
0x140010595  call    RtlWriteUShortToUser
0x14001059a  xor     edx, edx
0x14001059c  lea     rcx, [r14+2]
0x1400105a0  call    RtlWriteUShortToUser
0x1400105a5  mov     ebx, 0C0000023h
0x1400105aa  mov     rcx, [rbp+2Fh+pvContextBuffer]; pvContextBuffer
0x1400105ae  mov     r15, [rsp+0C0h+var_20]
0x1400105b6  mov     r14, [rsp+0C0h+var_18]
0x1400105be  mov     r13, [rsp+0B0h]
0x1400105c6  mov     r12, [rsp+0C0h+arg_18]
0x1400105ce  mov     rdi, [rsp+0C0h+arg_10]
0x1400105d6  mov     rsi, [rsp+0C0h+arg_0]
0x1400105de  test    rcx, rcx
0x1400105e1  jz      short loc_1400105EF
0x1400105e3  call    cs:__imp_FreeContextBuffer
0x1400105ea  nop     dword ptr [rax+rax+00h]
0x1400105ef  mov     rcx, [rbp+2Fh+UserInformation]; Buffer
0x1400105f3  test    rcx, rcx
0x1400105f6  jnz     loc_1400108D6
0x1400105fc  mov     eax, ebx
0x1400105fe  add     rsp, 0B8h
0x140010605  pop     rbx
0x140010606  pop     rbp
0x140010607  retn
0x140010609  mov     rbx, [rdi+18h]
0x14001060d  mov     r12d, 0C0000203h
0x140010613  mov     rcx, rbx
0x140010616  call    SmbCeAcquireSpinLock
0x14001061b  mov     rcx, rdi
0x14001061e  movzx   r13d, al
0x140010622  call    SmbCeGetFirstBindingObjectEx
0x140010627  mov     r15, rax
0x14001062a  test    rax, rax
0x14001062d  jnz     loc_1400107AD
0x140010633  lea     rcx, [rbx+780h]; SpinLock
0x14001063a  mov     dword ptr [rbx+930h], 0FFFFFFFFh
0x140010644  movzx   edx, r13b; OldIrql
0x140010648  call    cs:__imp_ExReleaseSpinLockExclusive
0x14001064f  nop     dword ptr [rax+rax+00h]
0x140010654  mov     ecx, r12d; SecStatus
0x140010657  call    cs:__imp_MapSecurityError
0x14001065e  nop     dword ptr [rax+rax+00h]
0x140010663  mov     ebx, eax
0x140010665  test    eax, eax
0x140010667  jnz     loc_140010547
0x14001066d  mov     rdx, [rbp+2Fh+pvContextBuffer]; SourceString
0x140010671  lea     rcx, [rbp+2Fh+DestinationString]; DestinationString
0x140010675  call    cs:__imp_RtlInitUnicodeString
0x14001067c  nop     dword ptr [rax+rax+00h]
0x140010681  movzx   r9d, [rbp+2Fh+DestinationString.Length]
0x140010686  xor     ecx, ecx
0x140010688  mov     r8, [rbp+2Fh+DestinationString.Buffer]
0x14001068c  mov     edx, r9d
0x14001068f  shr     edx, 1
0x140010691  jz      short loc_1400106A1
0x140010693  cmp     word ptr [r8+rcx*2], 5Ch ; '\'
0x140010699  jz      short loc_1400106A9
0x14001069b  inc     ecx
0x14001069d  cmp     ecx, edx
0x14001069f  jb      short loc_140010693
0x1400106a1  cmp     ecx, edx
0x1400106a3  jnb     loc_140010547
0x1400106a9  mov     r13, qword ptr [rbp+2Fh+LogonId.LowPart]
0x1400106ad  test    r13, r13
0x1400106b0  jnz     loc_14001086E
0x1400106b6  movzx   eax, cx
0x1400106b9  mov     qword ptr [rbp+2Fh+var_68+8], r8
0x1400106bd  add     ax, ax
0x1400106c0  lea     r13, [rbp+2Fh+var_68]
0x1400106c4  mov     word ptr [rbp+2Fh+var_68+2], ax
0x1400106c8  mov     word ptr [rbp+2Fh+var_68], ax
0x1400106cc  cmp     [rbp+2Fh+arg_8], 0
0x1400106d1  jnz     short loc_1400106F9
0x1400106d3  sub     r9w, ax
0x1400106d7  lea     rdi, [rbp+2Fh+var_58]
0x1400106db  sub     r9w, 2
0x1400106e0  inc     rcx
0x1400106e3  mov     word ptr [rbp+2Fh+var_58+2], r9w
0x1400106e8  mov     word ptr [rbp+2Fh+var_58], r9w
0x1400106ed  lea     rcx, [r8+rcx*2]
0x1400106f1  mov     qword ptr [rbp+2Fh+var_58+8], rcx
0x1400106f5  mov     [rbp+2Fh+arg_8], rdi
0x1400106f9  xor     edx, edx
0x1400106fb  mov     rcx, [rbp+2Fh+arg_8]
0x1400106ff  lea     rax, asc_14003EDD8; "\\"
0x140010706  mov     r15, [rbp+2Fh+arg_28]
0x14001070a  movzx   edi, [rbp+2Fh+arg_40]
0x14001070e  mov     [rbp+2Fh+var_48], 20002h
0x140010716  movzx   r12d, word ptr [rcx]
0x14001071a  mov     [rbp+2Fh+var_40], rax
0x14001071e  cmp     [r15], r12d
0x140010721  jnb     loc_1400107C8
0x140010727  test    dil, dil
0x14001072a  jz      loc_140010590
0x140010730  mov     [r14], dx
0x140010734  mov     [r14+2], dx
0x140010739  jmp     loc_1400105A5
0x14001073e  test    rsi, rsi
0x140010741  jz      loc_140010898
0x140010747  movzx   r14d, word ptr [r13+0]
0x14001074c  cmp     [r15], r14d
0x14001074f  jnb     loc_14001081B
0x140010755  test    dil, dil
0x140010758  jnz     short loc_140010779
0x14001075a  xor     edx, edx
0x14001075c  mov     rcx, rsi
0x14001075f  call    RtlWriteUShortToUser
0x140010764  xor     edx, edx
0x140010766  lea     rcx, [rsi+2]
0x14001076a  call    RtlWriteUShortToUser
0x14001076f  mov     ebx, 0C0000023h
0x140010774  jmp     loc_1400105AA
0x140010779  xor     eax, eax
0x14001077b  mov     [rsi], ax
0x14001077e  mov     [rsi+2], ax
0x140010782  jmp     short loc_14001076F
0x140010784  mov     rbx, [rax+10h]
0x140010788  mov     r13, [rax+20h]
0x14001078c  mov     [rbp+2Fh+arg_8], rbx
0x140010790  mov     qword ptr [rbp+2Fh+LogonId.LowPart], r13
0x140010794  test    rbx, rbx
0x140010797  jz      loc_14001053E
0x14001079d  test    r13, r13
0x1400107a0  jz      loc_14001053E
0x1400107a6  mov     ebx, edx
0x1400107a8  jmp     loc_1400106FB
0x1400107ad  cmp     dword ptr [r15+0Ch], 0
0x1400107b2  jz      loc_140039F28
0x1400107b8  mov     rdx, r15
0x1400107bb  mov     rcx, rdi
0x1400107be  call    SmbCeGetNextBindingObject
0x1400107c3  jmp     loc_140010627
0x1400107c8  movzx   eax, word ptr [rcx]
0x1400107cb  test    dil, dil
0x1400107ce  jnz     short loc_14001080D
0x1400107d0  movzx   edx, ax
0x1400107d3  mov     rcx, r14
0x1400107d6  call    RtlWriteUShortToUser
0x1400107db  mov     rdx, [rbp+2Fh+arg_8]
0x1400107df  lea     rcx, [r14+2]
0x1400107e3  movzx   edx, word ptr [rdx]
0x1400107e6  call    RtlWriteUShortToUser
0x1400107eb  mov     rcx, [rbp+2Fh+arg_8]
0x1400107ef  sub     [r15], r12d
0x1400107f2  mov     rdx, [rbp+2Fh+arg_38]
0x1400107f6  mov     eax, [r15]
0x1400107f9  test    rdx, rdx
0x1400107fc  jz      loc_140039FC6
0x140010802  add     [rdx], r12d
0x140010805  mov     eax, [r15]
0x140010808  jmp     loc_140039FC6
0x14001080d  mov     [r14], ax
0x140010811  movzx   eax, word ptr [rcx]
0x140010814  mov     [r14+2], ax
0x140010819  jmp     short loc_1400107EF
0x14001081b  movzx   eax, word ptr [r13+0]
0x140010820  test    dil, dil
0x140010823  jnz     short loc_140010860
0x140010825  movzx   edx, ax
0x140010828  mov     rcx, rsi
0x14001082b  call    RtlWriteUShortToUser
0x140010830  movzx   edx, word ptr [r13+0]
0x140010835  lea     rcx, [rsi+2]
0x140010839  call    RtlWriteUShortToUser
0x14001083e  mov     r10, [rbp+2Fh+arg_20]
0x140010842  sub     [r15], r14d
0x140010845  mov     rcx, [rbp+2Fh+arg_38]
0x140010849  mov     eax, [r15]
0x14001084c  test    rcx, rcx
0x14001084f  jz      loc_14003A05F
0x140010855  add     [rcx], r14d
0x140010858  mov     eax, [r15]
0x14001085b  jmp     loc_14003A05F
0x140010860  mov     [rsi], ax
0x140010863  movzx   eax, word ptr [r13+0]
0x140010868  mov     [rsi+2], ax
0x14001086c  jmp     short loc_140010842
0x14001086e  movzx   eax, word ptr [rbp+2Fh+var_68]
0x140010872  jmp     loc_1400106CC
0x140010877  mov     eax, cs:dword_140046144
0x14001087d  cmp     [rdi+64h], eax
0x140010880  jz      loc_140010566
0x140010886  jmp     loc_14001055E
0x14001088b  mov     rdi, [rbp+2Fh+UserInformation]
0x14001088f  lea     r13, [rdi+10h]
0x140010893  jmp     loc_1400106F5
0x140010898  mov     rdx, [rbp+2Fh+arg_8]
0x14001089c  mov     r9, r15
0x14001089f  mov     rax, [rbp+2Fh+arg_38]
0x1400108a3  mov     r8, r10
0x1400108a6  mov     [rsp+30h], dil
0x1400108ab  mov     rcx, r14
0x1400108ae  mov     qword ptr [rsp+0C0h+var_98], rax
0x1400108b3  movzx   esi, word ptr [rdx]
0x1400108b6  lea     rdx, [rbp+2Fh+var_48]
0x1400108ba  mov     dword ptr [rsp+0C0h+var_A0], r12d
0x1400108bf  call    PackStringIntoConnectInfo
0x1400108c4  test    al, al
0x1400108c6  jnz     loc_14003A016
0x1400108cc  mov     ebx, 0C0000023h
0x1400108d1  jmp     loc_1400105AA
0x1400108d6  call    cs:__imp_LsaFreeReturnBuffer
0x1400108dd  nop     dword ptr [rax+rax+00h]
0x1400108e2  jmp     loc_1400105FC
0x140039f28  mov     rcx, r15
0x140039f2b  call    cs:__imp_SmbCeReferenceBindingObject
0x140039f32  nop     dword ptr [rax+rax+00h]
0x140039f37  lea     rcx, [rbx+780h]; SpinLock
0x140039f3e  mov     dword ptr [rbx+930h], 0FFFFFFFFh
0x140039f48  movzx   edx, r13b; OldIrql
0x140039f4c  call    cs:__imp_ExReleaseSpinLockExclusive
0x140039f53  nop     dword ptr [rax+rax+00h]
0x140039f58  xor     edx, edx
0x140039f5a  lea     rcx, [r15+1C8h]
0x140039f61  call    cs:__imp_ExAcquirePushLockSharedEx
0x140039f68  nop     dword ptr [rax+rax+00h]
0x140039f6d  lea     rcx, [r15+1D0h]; phContext
0x140039f74  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x140039f78  jz      short loc_140039F9C
0x140039f7a  cmp     qword ptr [r15+1D8h], 0FFFFFFFFFFFFFFFFh
0x140039f82  jz      short loc_140039F9C
0x140039f84  lea     r8, [rbp+2Fh+pvContextBuffer]; pBuffer
0x140039f88  mov     edx, 1; ulAttribute
0x140039f8d  call    cs:__imp_QueryContextAttributesW
0x140039f94  nop     dword ptr [rax+rax+00h]
0x140039f99  mov     r12d, eax
0x140039f9c  xor     edx, edx
0x140039f9e  lea     rcx, [r15+1C8h]
0x140039fa5  call    cs:__imp_ExReleasePushLockSharedEx
0x140039fac  nop     dword ptr [rax+rax+00h]
0x140039fb1  mov     rcx, r15
0x140039fb4  call    cs:__imp_SmbCeDereferenceBindingObject
0x140039fbb  nop     dword ptr [rax+rax+00h]
0x140039fc0  nop
0x140039fc1  jmp     loc_140010654
0x140039fc6  mov     rdx, [rcx+8]; Src
0x140039fca  mov     r8, r12; Size
0x140039fcd  mov     rcx, [rbp+2Fh+arg_20]
0x140039fd1  add     rcx, rax; void *
0x140039fd4  test    dil, dil
0x140039fd7  jnz     short loc_140039FE0
0x140039fd9  call    RtlCopyToUser
0x140039fde  jmp     short loc_140039FE5
0x140039fe0  call    RtlCopyVolatileMemory
  ... truncated ...
```
