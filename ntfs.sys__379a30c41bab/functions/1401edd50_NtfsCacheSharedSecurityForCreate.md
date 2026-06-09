# NtfsCacheSharedSecurityForCreate

- ea: `0x1401edd50`
- end: `0x1401ee21a`
- name: `NtfsCacheSharedSecurityForCreate`
- size: `1226`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1402376fc`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14018756c`
- `0x1401edd50`
- `0x1401ee220`
- `0x1401ee3b0`
- `0x1401ef2d0`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x1401eddd2`
- `ntoskrnl!SeDeassignSecurity` at `0x1401ee143`
- `ntoskrnl!SeDeassignSecurity` at `0x1402b18aa`
- `ntoskrnl!SeDeassignSecurity` at `0x1401ee143`
- `ntoskrnl!SeDeassignSecurity` at `0x1402b18aa`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1401edfce`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1401edfce`
- `ntoskrnl!ExGetPreviousMode` at `0x1401ee1eb`
- `ntoskrnl!ExGetPreviousMode` at `0x1401ee1eb`
- `ntoskrnl!SeComputeAutoInheritByObjectType` at `0x1401edddc`
- `ntoskrnl!SeComputeAutoInheritByObjectType` at `0x1401edddc`
- `ntoskrnl!SeAssignSecurityEx` at `0x1401edfaf`
- `ntoskrnl!SeAssignSecurityEx` at `0x1401edfaf`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401edf60`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401edf60`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ee0e9`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b1880`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ee0e9`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b1880`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401edf44`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ee0cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ee115`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b17c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b1800`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401edf44`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ee0cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ee115`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b17c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b1800`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401edee0`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ee0b3`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402b1851`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401edee0`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ee0b3`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402b1851`

## pseudocode

```c
__int64 __fastcall NtfsCacheSharedSecurityForCreate(__int64 a1, __int64 a2)
{
  __int64 v4; // r12
  _DWORD *v5; // r14
  void *v6; // rsi
  __int64 v7; // rbx
  __int64 v8; // rbx
  ULONG v9; // edi
  __int64 v10; // rdx
  char *v11; // rcx
  char v12; // al
  char PreviousMode; // cl
  int v14; // eax
  int v15; // edi
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 Unsafe; // rax
  __int64 v19; // rdi
  __int64 v20; // rcx
  __int64 v21; // rdx
  _DWORD *v22; // rcx
  bool v23; // zf
  __int64 v24; // rdi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  unsigned int v26; // eax
  ULONG v27; // eax
  PSECURITY_DESCRIPTOR v28; // r14
  __int64 v29; // rsi
  void *v30; // rcx
  int v31; // eax
  unsigned int v32; // eax
  int v34; // r8d
  unsigned __int64 v35; // rax
  __int64 v36; // r9
  char v37; // [rsp+52h] [rbp-56h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-50h] BYREF
  __int64 v39; // [rsp+60h] [rbp-48h]
  __int64 v40; // [rsp+68h] [rbp-40h]
  char IsDirectoryObject; // [rsp+B8h] [rbp+10h]
  ULONG AutoInheritFlags; // [rsp+C0h] [rbp+18h]
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+C8h] [rbp+20h] BYREF

  NewDescriptor = 0;
  v4 = 0;
  v5 = 0;
  v39 = 0;
  LOBYTE(v6) = 0;
  SecurityDescriptor = 0;
  v37 = 1;
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 112) + 184LL);
  IsDirectoryObject = *(_BYTE *)(v7 + 16) & 1;
  v8 = *(_QWORD *)(*(_QWORD *)(v7 + 8) + 8LL);
  v40 = v8;
  if ( !*(_QWORD *)(a2 + 208) )
    NtfsLoadSecurityDescriptor(a1, a2);
  v9 = SeComputeAutoInheritByObjectType(
         IoFileObjectType,
         *(PSECURITY_DESCRIPTOR *)(v8 + 64),
         (PSECURITY_DESCRIPTOR)(*(_QWORD *)(a2 + 208) + 28LL));
  v10 = *(_QWORD *)(a1 + 112);
  if ( v10 )
  {
    v11 = *(char **)(v10 + 184);
    v12 = *v11;
    if ( !*v11 )
    {
      if ( (v11[2] & 1) == 0 )
      {
LABEL_6:
        PreviousMode = *(_BYTE *)(v10 + 64);
        goto LABEL_7;
      }
      goto LABEL_57;
    }
    switch ( v12 )
    {
      case 13:
        if ( *(_BYTE *)(v10 + 64) || v11[1] != 4 )
        {
LABEL_57:
          PreviousMode = 1;
          break;
        }
        PreviousMode = 0;
        break;
      case 6:
        v34 = *((_DWORD *)v11 + 4);
        v35 = (unsigned int)(v34 - 10);
        if ( (unsigned int)v35 <= 0x3E && (v36 = 0x4080000000000003LL, _bittest64(&v36, v35)) )
        {
          PreviousMode = (v11[2] & 1) == 0;
        }
        else
        {
          if ( v34 != 71 || (v11[2] & 1) == 0 )
            goto LABEL_6;
          PreviousMode = 1;
        }
        break;
      case 5:
        if ( *((_DWORD *)v11 + 4) != 71 )
          goto LABEL_6;
        v23 = (v11[2] & 1) == 0;
        PreviousMode = 1;
        if ( v23 )
          goto LABEL_6;
        break;
      default:
        goto LABEL_6;
    }
  }
  else
  {
    PreviousMode = ExGetPreviousMode();
  }
LABEL_7:
  v14 = 16408;
  if ( PreviousMode )
    v14 = 24576;
  v15 = v14 | v9;
  AutoInheritFlags = v15;
  if ( !*(_QWORD *)(v8 + 64) )
  {
    v16 = *(_QWORD *)(a2 + 208);
    if ( *(_DWORD *)(v16 + 12) )
    {
      v17 = *(_QWORD *)(a2 + 96);
      if ( *(_QWORD *)(v17 + 104) )
      {
        Unsafe = GetSharedSecurityForCreateUnsafe(v17, (int)v16 + 8, v15, (int)v8 + 32, IsDirectoryObject);
        v5 = (_DWORD *)Unsafe;
        v39 = Unsafe;
        if ( Unsafe )
        {
          if ( *(_DWORD *)(Unsafe + 12) )
            v4 = NtfsCacheSharedSecurityBySecurityId(a1);
        }
      }
    }
  }
  if ( v4 )
  {
    v19 = v4;
LABEL_17:
    if ( v19 )
    {
      SecurityDescriptor = NewDescriptor;
      NewDescriptor = (PSECURITY_DESCRIPTOR)(v19 + 28);
      v37 = 0;
    }
    if ( v5 )
    {
      if ( !v4 )
      {
        KeAcquireGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 104) + 664LL));
        LOBYTE(v6) = 1;
        if ( v5[5] )
        {
          v20 = *(_QWORD *)(a2 + 96);
          if ( *(_QWORD *)(v20 + 104) )
          {
            v21 = v20 + 8LL * (v5[1] & 0x7F);
            v22 = *(_DWORD **)(v21 + 11792);
            *((_QWORD *)v5 + 1) = *(_QWORD *)(v19 + 8);
            *(_QWORD *)(v21 + 11792) = v5;
            ++*v5;
            if ( v22 )
            {
              v23 = (*v22)-- == 1;
              if ( v23 )
                ExFreePoolWithTag(v22, 0);
            }
          }
        }
      }
    }
    goto LABEL_40;
  }
  v6 = *(void **)(v8 + 64);
  v24 = *(_QWORD *)(a2 + 208);
  GenericMapping = IoGetFileObjectGenericMapping();
  v26 = SeAssignSecurityEx(
          (PSECURITY_DESCRIPTOR)(v24 + 28),
          v6,
          &NewDescriptor,
          0,
          IsDirectoryObject,
          AutoInheritFlags,
          (PSECURITY_SUBJECT_CONTEXT)(v8 + 32),
          GenericMapping,
          PoolType);
  v19 = v26;
  if ( (v26 & 0x80000000) != 0 )
  {
    if ( NtfsStatusDebugFlags
      && v26 < 0xFFFFFFED
      && v26 != -1073741802
      && v26 != -1073741807
      && v26 + 2147483643 > 1
      && v26 != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(a1, v26, 2038509);
    }
    NtfsRaiseStatusInternal(a1, v19, 0, 0, 2038509);
  }
  else
  {
    v27 = RtlLengthSecurityDescriptor(NewDescriptor);
    if ( v27 )
    {
      v19 = NtfsCacheSharedSecurityByDescriptor(a1, NewDescriptor, v27, 1);
      LOBYTE(v6) = 0;
      goto LABEL_17;
    }
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 2038545);
  NtfsRaiseStatusInternal(a1, -1073741811, 0, 0, 2038545);
LABEL_40:
  if ( v5 )
  {
    if ( !(_BYTE)v6 )
    {
      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 104) + 664LL));
      LOBYTE(v6) = 1;
    }
    v23 = (*v5)-- == 1;
    if ( v23 )
      ExFreePoolWithTag(v5, 0);
  }
  if ( (_BYTE)v6 )
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 104) + 664LL));
  v28 = NewDescriptor;
  v29 = *(_QWORD *)(v8 + 72);
  if ( (*(_DWORD *)(v8 + 12) & 0x4000000) == 0 )
  {
    v30 = *(void **)(v29 + 48);
    if ( v30 )
      ExFreePoolWithTag(v30, 0);
  }
  v31 = *(_DWORD *)(v8 + 12);
  if ( v37 )
    v32 = v31 & 0xFBFFFFFF;
  else
    v32 = v31 | 0x4000000;
  *(_DWORD *)(v8 + 12) = v32;
  *(_QWORD *)(v29 + 48) = v28;
  if ( SecurityDescriptor )
    SeDeassignSecurity(&SecurityDescriptor);
  return v19;
}

```

## disassembly

```asm
0x1401edd50  mov     r11, rsp
0x1401edd53  mov     [r11+8], rcx
0x1401edd57  push    rbx
0x1401edd58  push    rsi
0x1401edd59  push    rdi
0x1401edd5a  push    r12
0x1401edd5c  push    r13
0x1401edd5e  push    r14
0x1401edd60  push    r15
0x1401edd62  sub     rsp, 70h
0x1401edd66  mov     r15, rdx
0x1401edd69  mov     r13, rcx
0x1401edd6c  xor     eax, eax
0x1401edd6e  mov     [r11+20h], rax
0x1401edd72  mov     r12d, eax
0x1401edd75  mov     r14d, eax
0x1401edd78  mov     [r11-48h], rax
0x1401edd7c  mov     [rsp+0A8h+var_57], al
0x1401edd80  xor     sil, sil
0x1401edd83  mov     [rsp+0A8h+var_58], sil
0x1401edd88  mov     [r11-50h], rax
0x1401edd8c  mov     [rsp+0A8h+var_56], 1
0x1401edd91  mov     rax, [rcx+70h]
0x1401edd95  mov     rbx, [rax+0B8h]
0x1401edd9c  movzx   eax, byte ptr [rbx+10h]
0x1401edda0  and     al, 1
0x1401edda2  mov     [rsp+0A8h+arg_8], al
0x1401edda9  mov     rbx, [rbx+8]
0x1401eddad  mov     rbx, [rbx+8]
0x1401eddb1  mov     [rsp+0A8h+var_40], rbx
0x1401eddb6  cmp     [rdx+0D0h], r14
0x1401eddbd  jz      loc_1401EE210
0x1401eddc3  mov     r8, [r15+0D0h]
0x1401eddca  add     r8, 1Ch; ParentSecurityDescriptor
0x1401eddce  mov     rdx, [rbx+40h]; SecurityDescriptor
0x1401eddd2  mov     rcx, cs:__imp_IoFileObjectType
0x1401eddd9  mov     rcx, [rcx]; ObjectType
0x1401edddc  call    cs:__imp_SeComputeAutoInheritByObjectType
0x1401edde3  nop     dword ptr [rax+rax+00h]
0x1401edde8  mov     edi, eax
0x1401eddea  mov     rdx, [r13+70h]
0x1401eddee  test    rdx, rdx
0x1401eddf1  jz      loc_1401EE1EB
0x1401eddf7  mov     rcx, [rdx+0B8h]
0x1401eddfe  movzx   eax, byte ptr [rcx]
0x1401ede01  test    al, al
0x1401ede03  jnz     loc_1401EE17A
0x1401ede09  test    byte ptr [rcx+2], 1
0x1401ede0d  jnz     loc_1401EE173
0x1401ede13  movzx   ecx, byte ptr [rdx+40h]
0x1401ede17  mov     eax, 4018h
0x1401ede1c  mov     edx, 6000h
0x1401ede21  test    cl, cl
0x1401ede23  cmovnz  eax, edx
0x1401ede26  or      edi, eax
0x1401ede28  mov     [rsp+0A8h+arg_10], edi
0x1401ede2f  cmp     qword ptr [rbx+40h], 0
0x1401ede34  jnz     short loc_1401EDE8F
0x1401ede36  mov     rdx, [r15+0D0h]
0x1401ede3d  cmp     dword ptr [rdx+0Ch], 0
0x1401ede41  jz      short loc_1401EDE8F
0x1401ede43  mov     rcx, [r15+60h]
0x1401ede47  cmp     qword ptr [rcx+68h], 0
0x1401ede4c  jz      short loc_1401EDE8F
0x1401ede4e  lea     r9, [rbx+20h]
0x1401ede52  add     rdx, 8
0x1401ede56  movzx   eax, [rsp+0A8h+arg_8]
0x1401ede5e  mov     [rsp+0A8h+IsDirectoryObject], al
0x1401ede62  mov     r8d, edi
0x1401ede65  call    GetSharedSecurityForCreateUnsafe
0x1401ede6a  mov     r14, rax
0x1401ede6d  mov     [rsp+0A8h+var_48], rax
0x1401ede72  test    rax, rax
0x1401ede75  jz      short loc_1401EDE8F
0x1401ede77  mov     r8d, [rax+0Ch]
0x1401ede7b  test    r8d, r8d
0x1401ede7e  jz      short loc_1401EDE8F
0x1401ede80  mov     rdx, [r15+60h]
0x1401ede84  mov     rcx, r13
0x1401ede87  call    NtfsCacheSharedSecurityBySecurityId
0x1401ede8c  mov     r12, rax
0x1401ede8f  test    r12, r12
0x1401ede92  jz      loc_1401EDF55
0x1401ede98  mov     rdi, r12
0x1401ede9b  mov     [rsp+0A8h+var_57], 1
0x1401edea0  test    rdi, rdi
0x1401edea3  jz      short loc_1401EDEC3
0x1401edea5  mov     rax, [rsp+0A8h+NewDescriptor]
0x1401edead  mov     [rsp+0A8h+SecurityDescriptor], rax
0x1401edeb2  lea     rax, [rdi+1Ch]
0x1401edeb6  mov     [rsp+0A8h+NewDescriptor], rax
0x1401edebe  mov     [rsp+0A8h+var_56], 0
0x1401edec3  test    r14, r14
0x1401edec6  jz      loc_1401EE09E
0x1401edecc  test    r12, r12
0x1401edecf  jnz     loc_1401EE09E
0x1401eded5  mov     rcx, [r13+68h]
0x1401eded9  add     rcx, 298h; Mutex
0x1401edee0  call    cs:__imp_KeAcquireGuardedMutex
0x1401edee7  nop     dword ptr [rax+rax+00h]
0x1401edeec  mov     sil, 1
0x1401edeef  mov     [rsp+0A8h+var_58], sil
0x1401edef4  cmp     [r14+14h], r12d
0x1401edef8  jz      loc_1401EE09E
0x1401edefe  mov     rcx, [r15+60h]
0x1401edf02  cmp     [rcx+68h], r12
0x1401edf06  jz      loc_1401EE09E
0x1401edf0c  mov     eax, [r14+4]
0x1401edf10  and     eax, 7Fh
0x1401edf13  lea     rdx, [rcx+rax*8]
0x1401edf17  mov     rcx, [rdx+2E10h]; P
0x1401edf1e  mov     rax, [rdi+8]
0x1401edf22  mov     [r14+8], rax
0x1401edf26  mov     [rdx+2E10h], r14
0x1401edf2d  inc     dword ptr [r14]
0x1401edf30  test    rcx, rcx
0x1401edf33  jz      loc_1401EE09E
0x1401edf39  add     dword ptr [rcx], 0FFFFFFFFh
0x1401edf3c  jnz     loc_1401EE09E
0x1401edf42  xor     edx, edx; Tag
0x1401edf44  call    cs:__imp_ExFreePoolWithTag
0x1401edf4b  nop     dword ptr [rax+rax+00h]
0x1401edf50  jmp     loc_1401EE09E
0x1401edf55  mov     rsi, [rbx+40h]
0x1401edf59  mov     rdi, [r15+0D0h]
0x1401edf60  call    cs:__imp_IoGetFileObjectGenericMapping
0x1401edf67  nop     dword ptr [rax+rax+00h]
0x1401edf6c  lea     r9, [rbx+20h]
0x1401edf70  mov     r8d, cs:PoolType
0x1401edf77  mov     [rsp+0A8h+PoolType], r8d; PoolType
0x1401edf7c  mov     [rsp+0A8h+GenericMapping], rax; GenericMapping
0x1401edf81  mov     [rsp+0A8h+SubjectContext], r9; SubjectContext
0x1401edf86  mov     eax, [rsp+0A8h+arg_10]
0x1401edf8d  mov     [rsp+0A8h+AutoInheritFlags], eax; AutoInheritFlags
0x1401edf91  movzx   eax, [rsp+0A8h+arg_8]
0x1401edf99  mov     [rsp+0A8h+IsDirectoryObject], al; IsDirectoryObject
0x1401edf9d  xor     r9d, r9d; ObjectType
0x1401edfa0  lea     r8, [rsp+0A8h+NewDescriptor]; NewDescriptor
0x1401edfa8  mov     rdx, rsi; ExplicitDescriptor
0x1401edfab  lea     rcx, [rdi+1Ch]; ParentDescriptor
0x1401edfaf  call    cs:__imp_SeAssignSecurityEx
0x1401edfb6  nop     dword ptr [rax+rax+00h]
0x1401edfbb  mov     edi, eax
0x1401edfbd  test    eax, eax
0x1401edfbf  js      short loc_1401EE008
0x1401edfc1  mov     [rsp+0A8h+var_57], 1
0x1401edfc6  mov     rcx, [rsp+0A8h+NewDescriptor]; SecurityDescriptor
0x1401edfce  call    cs:__imp_RtlLengthSecurityDescriptor
0x1401edfd5  nop     dword ptr [rax+rax+00h]
0x1401edfda  test    eax, eax
0x1401edfdc  jz      loc_1401EE063
0x1401edfe2  mov     [rsp+0A8h+IsDirectoryObject], 1; char
0x1401edfe7  mov     r9b, 1
0x1401edfea  mov     r8d, eax; Length
0x1401edfed  mov     rdx, [rsp+0A8h+NewDescriptor]; SecurityDescriptor
0x1401edff5  mov     rcx, r13; int
0x1401edff8  call    NtfsCacheSharedSecurityByDescriptor
0x1401edffd  mov     rdi, rax
0x1401ee000  xor     sil, sil
0x1401ee003  jmp     loc_1401EDEA0
0x1401ee008  movzx   ecx, cs:NtfsStatusDebugFlags
0x1401ee00f  test    cl, cl
0x1401ee011  jz      short loc_1401EE04A
0x1401ee013  cmp     edi, 0FFFFFFEDh
0x1401ee016  jnb     short loc_1401EE04A
0x1401ee018  cmp     edi, 0C0000016h
0x1401ee01e  jz      short loc_1401EE04A
0x1401ee020  cmp     edi, 0C0000011h
0x1401ee026  jz      short loc_1401EE04A
0x1401ee028  add     eax, 7FFFFFFBh
0x1401ee02d  cmp     eax, 1
0x1401ee030  jbe     short loc_1401EE04A
0x1401ee032  cmp     edi, 0C00000D8h
0x1401ee038  jz      short loc_1401EE04A
0x1401ee03a  mov     r8d, 1F1AEDh
0x1401ee040  mov     edx, edi
0x1401ee042  mov     rcx, r13
0x1401ee045  call    NtfsStatusTraceAndDebugInternal
0x1401ee04a  mov     qword ptr [rsp+0A8h+IsDirectoryObject], 1F1AEDh
0x1401ee053  xor     r9d, r9d
0x1401ee056  xor     r8d, r8d
0x1401ee059  mov     edx, edi
0x1401ee05b  mov     rcx, r13
0x1401ee05e  call    NtfsRaiseStatusInternal
0x1401ee063  movzx   eax, cs:NtfsStatusDebugFlags
0x1401ee06a  test    al, al
0x1401ee06c  jz      short loc_1401EE081
0x1401ee06e  mov     edx, 0C000000Dh
0x1401ee073  mov     r8d, 1F1B11h
0x1401ee079  mov     rcx, r13
0x1401ee07c  call    NtfsStatusTraceAndDebugInternal
0x1401ee081  mov     qword ptr [rsp+0A8h+IsDirectoryObject], 1F1B11h
0x1401ee08a  xor     r9d, r9d
0x1401ee08d  xor     r8d, r8d
0x1401ee090  mov     edx, 0C000000Dh
0x1401ee095  mov     rcx, r13
0x1401ee098  call    NtfsRaiseStatusInternal
0x1401ee09d  nop
0x1401ee09e  test    r14, r14
0x1401ee0a1  jz      short loc_1401EE0D9
0x1401ee0a3  test    sil, sil
0x1401ee0a6  jnz     short loc_1401EE0C2
0x1401ee0a8  mov     rcx, [r13+68h]
0x1401ee0ac  add     rcx, 298h; Mutex
0x1401ee0b3  call    cs:__imp_KeAcquireGuardedMutex
0x1401ee0ba  nop     dword ptr [rax+rax+00h]
0x1401ee0bf  mov     sil, 1
0x1401ee0c2  add     dword ptr [r14], 0FFFFFFFFh
0x1401ee0c6  jnz     short loc_1401EE0D9
0x1401ee0c8  xor     edx, edx; Tag
0x1401ee0ca  mov     rcx, r14; P
0x1401ee0cd  call    cs:__imp_ExFreePoolWithTag
0x1401ee0d4  nop     dword ptr [rax+rax+00h]
0x1401ee0d9  test    sil, sil
0x1401ee0dc  jz      short loc_1401EE0F5
0x1401ee0de  mov     rcx, [r13+68h]
0x1401ee0e2  add     rcx, 298h; Mutex
0x1401ee0e9  call    cs:__imp_KeReleaseGuardedMutex
0x1401ee0f0  nop     dword ptr [rax+rax+00h]
0x1401ee0f5  mov     r14, [rsp+0A8h+NewDescriptor]
0x1401ee0fd  mov     rsi, [rbx+48h]
0x1401ee101  test    dword ptr [rbx+0Ch], 4000000h
0x1401ee108  jnz     short loc_1401EE121
0x1401ee10a  mov     rcx, [rsi+30h]; P
0x1401ee10e  test    rcx, rcx
0x1401ee111  jz      short loc_1401EE121
0x1401ee113  xor     edx, edx; Tag
0x1401ee115  call    cs:__imp_ExFreePoolWithTag
0x1401ee11c  nop     dword ptr [rax+rax+00h]
0x1401ee121  mov     eax, [rbx+0Ch]
0x1401ee124  cmp     [rsp+0A8h+var_56], 0
0x1401ee129  jz      short loc_1401EE163
0x1401ee12b  btr     eax, 1Ah
0x1401ee12f  mov     [rbx+0Ch], eax
0x1401ee132  mov     [rsi+30h], r14
0x1401ee136  cmp     [rsp+0A8h+SecurityDescriptor], 0
0x1401ee13c  jz      short loc_1401EE14F
0x1401ee13e  lea     rcx, [rsp+0A8h+SecurityDescriptor]; SecurityDescriptor
0x1401ee143  call    cs:__imp_SeDeassignSecurity
0x1401ee14a  nop     dword ptr [rax+rax+00h]
0x1401ee14f  mov     rax, rdi
0x1401ee152  add     rsp, 70h
0x1401ee156  pop     r15
0x1401ee158  pop     r14
0x1401ee15a  pop     r13
0x1401ee15c  pop     r12
0x1401ee15e  pop     rdi
0x1401ee15f  pop     rsi
0x1401ee160  pop     rbx
0x1401ee161  retn
0x1401ee163  bts     eax, 1Ah
0x1401ee167  jmp     short loc_1401EE12F
0x1401ee169  cmp     [rdx+40h], sil
0x1401ee16d  jz      loc_1401EE1FF
0x1401ee173  mov     cl, 1
0x1401ee175  jmp     loc_1401EDE17
0x1401ee17a  cmp     al, 0Dh
0x1401ee17c  jz      short loc_1401EE169
0x1401ee17e  cmp     al, 6
0x1401ee180  jnz     short loc_1401EE1C8
0x1401ee182  mov     r8d, [rcx+10h]
0x1401ee186  lea     eax, [r8-0Ah]
0x1401ee18a  cmp     eax, 3Eh ; '>'
0x1401ee18d  ja      short loc_1401EE1AD
0x1401ee18f  mov     r9, 4080000000000003h
0x1401ee199  bt      r9, rax
0x1401ee19d  jnb     short loc_1401EE1AD
0x1401ee19f  movzx   ecx, byte ptr [rcx+2]
0x1401ee1a3  not     cl
0x1401ee1a5  and     cl, 1
0x1401ee1a8  jmp     loc_1401EDE17
0x1401ee1ad  cmp     r8d, 47h ; 'G'
0x1401ee1b1  jnz     loc_1401EDE13
0x1401ee1b7  test    byte ptr [rcx+2], 1
0x1401ee1bb  jz      loc_1401EDE13
0x1401ee1c1  mov     cl, 1
0x1401ee1c3  jmp     loc_1401EDE17
0x1401ee1c8  cmp     al, 5
0x1401ee1ca  jnz     loc_1401EDE13
0x1401ee1d0  cmp     dword ptr [rcx+10h], 47h ; 'G'
0x1401ee1d4  jnz     loc_1401EDE13
0x1401ee1da  test    byte ptr [rcx+2], 1
0x1401ee1de  mov     cl, 1
0x1401ee1e0  jz      loc_1401EDE13
0x1401ee1e6  jmp     loc_1401EDE17
0x1401ee1eb  call    cs:__imp_ExGetPreviousMode
0x1401ee1f2  nop     dword ptr [rax+rax+00h]
0x1401ee1f7  movzx   ecx, al
0x1401ee1fa  jmp     loc_1401EDE17
0x1401ee1ff  cmp     byte ptr [rcx+1], 4
0x1401ee203  jnz     loc_1401EE173
0x1401ee209  xor     cl, cl
0x1401ee20b  jmp     loc_1401EDE17
0x1401ee210  call    NtfsLoadSecurityDescriptor
0x1401ee215  jmp     loc_1401EDDC3
0x1402b17a0  push    rbx
0x1402b17a2  push    rbp
0x1402b17a3  push    rsi
0x1402b17a4  push    rdi
0x1402b17a5  sub     rsp, 58h
  ... truncated ...
```
