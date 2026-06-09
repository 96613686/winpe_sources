# NtfsCacheSharedSecurityForCreate

- ea: `0x1401edd00`
- end: `0x1401ee1ca`
- name: `NtfsCacheSharedSecurityForCreate`
- size: `1226`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1402376ac`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14018751c`
- `0x1401edd00`
- `0x1401ee1d0`
- `0x1401ee360`
- `0x1401ef280`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x1401edd82`
- `ntoskrnl!SeDeassignSecurity` at `0x1401ee0f3`
- `ntoskrnl!SeDeassignSecurity` at `0x1402b185a`
- `ntoskrnl!SeDeassignSecurity` at `0x1401ee0f3`
- `ntoskrnl!SeDeassignSecurity` at `0x1402b185a`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1401edf7e`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1401edf7e`
- `ntoskrnl!ExGetPreviousMode` at `0x1401ee19b`
- `ntoskrnl!ExGetPreviousMode` at `0x1401ee19b`
- `ntoskrnl!SeComputeAutoInheritByObjectType` at `0x1401edd8c`
- `ntoskrnl!SeComputeAutoInheritByObjectType` at `0x1401edd8c`
- `ntoskrnl!SeAssignSecurityEx` at `0x1401edf5f`
- `ntoskrnl!SeAssignSecurityEx` at `0x1401edf5f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401edf10`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401edf10`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ee099`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b1830`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ee099`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b1830`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401edef4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ee07d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ee0c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b1771`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b17b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401edef4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ee07d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ee0c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b1771`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b17b0`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ede90`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ee063`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402b1801`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ede90`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ee063`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402b1801`

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
0x1401edd00  mov     r11, rsp
0x1401edd03  mov     [r11+8], rcx
0x1401edd07  push    rbx
0x1401edd08  push    rsi
0x1401edd09  push    rdi
0x1401edd0a  push    r12
0x1401edd0c  push    r13
0x1401edd0e  push    r14
0x1401edd10  push    r15
0x1401edd12  sub     rsp, 70h
0x1401edd16  mov     r15, rdx
0x1401edd19  mov     r13, rcx
0x1401edd1c  xor     eax, eax
0x1401edd1e  mov     [r11+20h], rax
0x1401edd22  mov     r12d, eax
0x1401edd25  mov     r14d, eax
0x1401edd28  mov     [r11-48h], rax
0x1401edd2c  mov     [rsp+0A8h+var_57], al
0x1401edd30  xor     sil, sil
0x1401edd33  mov     [rsp+0A8h+var_58], sil
0x1401edd38  mov     [r11-50h], rax
0x1401edd3c  mov     [rsp+0A8h+var_56], 1
0x1401edd41  mov     rax, [rcx+70h]
0x1401edd45  mov     rbx, [rax+0B8h]
0x1401edd4c  movzx   eax, byte ptr [rbx+10h]
0x1401edd50  and     al, 1
0x1401edd52  mov     [rsp+0A8h+arg_8], al
0x1401edd59  mov     rbx, [rbx+8]
0x1401edd5d  mov     rbx, [rbx+8]
0x1401edd61  mov     [rsp+0A8h+var_40], rbx
0x1401edd66  cmp     [rdx+0D0h], r14
0x1401edd6d  jz      loc_1401EE1C0
0x1401edd73  mov     r8, [r15+0D0h]
0x1401edd7a  add     r8, 1Ch; ParentSecurityDescriptor
0x1401edd7e  mov     rdx, [rbx+40h]; SecurityDescriptor
0x1401edd82  mov     rcx, cs:__imp_IoFileObjectType
0x1401edd89  mov     rcx, [rcx]; ObjectType
0x1401edd8c  call    cs:__imp_SeComputeAutoInheritByObjectType
0x1401edd93  nop     dword ptr [rax+rax+00h]
0x1401edd98  mov     edi, eax
0x1401edd9a  mov     rdx, [r13+70h]
0x1401edd9e  test    rdx, rdx
0x1401edda1  jz      loc_1401EE19B
0x1401edda7  mov     rcx, [rdx+0B8h]
0x1401eddae  movzx   eax, byte ptr [rcx]
0x1401eddb1  test    al, al
0x1401eddb3  jnz     loc_1401EE12A
0x1401eddb9  test    byte ptr [rcx+2], 1
0x1401eddbd  jnz     loc_1401EE123
0x1401eddc3  movzx   ecx, byte ptr [rdx+40h]
0x1401eddc7  mov     eax, 4018h
0x1401eddcc  mov     edx, 6000h
0x1401eddd1  test    cl, cl
0x1401eddd3  cmovnz  eax, edx
0x1401eddd6  or      edi, eax
0x1401eddd8  mov     [rsp+0A8h+arg_10], edi
0x1401edddf  cmp     qword ptr [rbx+40h], 0
0x1401edde4  jnz     short loc_1401EDE3F
0x1401edde6  mov     rdx, [r15+0D0h]
0x1401edded  cmp     dword ptr [rdx+0Ch], 0
0x1401eddf1  jz      short loc_1401EDE3F
0x1401eddf3  mov     rcx, [r15+60h]
0x1401eddf7  cmp     qword ptr [rcx+68h], 0
0x1401eddfc  jz      short loc_1401EDE3F
0x1401eddfe  lea     r9, [rbx+20h]
0x1401ede02  add     rdx, 8
0x1401ede06  movzx   eax, [rsp+0A8h+arg_8]
0x1401ede0e  mov     [rsp+0A8h+IsDirectoryObject], al
0x1401ede12  mov     r8d, edi
0x1401ede15  call    GetSharedSecurityForCreateUnsafe
0x1401ede1a  mov     r14, rax
0x1401ede1d  mov     [rsp+0A8h+var_48], rax
0x1401ede22  test    rax, rax
0x1401ede25  jz      short loc_1401EDE3F
0x1401ede27  mov     r8d, [rax+0Ch]
0x1401ede2b  test    r8d, r8d
0x1401ede2e  jz      short loc_1401EDE3F
0x1401ede30  mov     rdx, [r15+60h]
0x1401ede34  mov     rcx, r13
0x1401ede37  call    NtfsCacheSharedSecurityBySecurityId
0x1401ede3c  mov     r12, rax
0x1401ede3f  test    r12, r12
0x1401ede42  jz      loc_1401EDF05
0x1401ede48  mov     rdi, r12
0x1401ede4b  mov     [rsp+0A8h+var_57], 1
0x1401ede50  test    rdi, rdi
0x1401ede53  jz      short loc_1401EDE73
0x1401ede55  mov     rax, [rsp+0A8h+NewDescriptor]
0x1401ede5d  mov     [rsp+0A8h+SecurityDescriptor], rax
0x1401ede62  lea     rax, [rdi+1Ch]
0x1401ede66  mov     [rsp+0A8h+NewDescriptor], rax
0x1401ede6e  mov     [rsp+0A8h+var_56], 0
0x1401ede73  test    r14, r14
0x1401ede76  jz      loc_1401EE04E
0x1401ede7c  test    r12, r12
0x1401ede7f  jnz     loc_1401EE04E
0x1401ede85  mov     rcx, [r13+68h]
0x1401ede89  add     rcx, 298h; Mutex
0x1401ede90  call    cs:__imp_KeAcquireGuardedMutex
0x1401ede97  nop     dword ptr [rax+rax+00h]
0x1401ede9c  mov     sil, 1
0x1401ede9f  mov     [rsp+0A8h+var_58], sil
0x1401edea4  cmp     [r14+14h], r12d
0x1401edea8  jz      loc_1401EE04E
0x1401edeae  mov     rcx, [r15+60h]
0x1401edeb2  cmp     [rcx+68h], r12
0x1401edeb6  jz      loc_1401EE04E
0x1401edebc  mov     eax, [r14+4]
0x1401edec0  and     eax, 7Fh
0x1401edec3  lea     rdx, [rcx+rax*8]
0x1401edec7  mov     rcx, [rdx+2E10h]; P
0x1401edece  mov     rax, [rdi+8]
0x1401eded2  mov     [r14+8], rax
0x1401eded6  mov     [rdx+2E10h], r14
0x1401ededd  inc     dword ptr [r14]
0x1401edee0  test    rcx, rcx
0x1401edee3  jz      loc_1401EE04E
0x1401edee9  add     dword ptr [rcx], 0FFFFFFFFh
0x1401edeec  jnz     loc_1401EE04E
0x1401edef2  xor     edx, edx; Tag
0x1401edef4  call    cs:__imp_ExFreePoolWithTag
0x1401edefb  nop     dword ptr [rax+rax+00h]
0x1401edf00  jmp     loc_1401EE04E
0x1401edf05  mov     rsi, [rbx+40h]
0x1401edf09  mov     rdi, [r15+0D0h]
0x1401edf10  call    cs:__imp_IoGetFileObjectGenericMapping
0x1401edf17  nop     dword ptr [rax+rax+00h]
0x1401edf1c  lea     r9, [rbx+20h]
0x1401edf20  mov     r8d, cs:PoolType
0x1401edf27  mov     [rsp+0A8h+PoolType], r8d; PoolType
0x1401edf2c  mov     [rsp+0A8h+GenericMapping], rax; GenericMapping
0x1401edf31  mov     [rsp+0A8h+SubjectContext], r9; SubjectContext
0x1401edf36  mov     eax, [rsp+0A8h+arg_10]
0x1401edf3d  mov     [rsp+0A8h+AutoInheritFlags], eax; AutoInheritFlags
0x1401edf41  movzx   eax, [rsp+0A8h+arg_8]
0x1401edf49  mov     [rsp+0A8h+IsDirectoryObject], al; IsDirectoryObject
0x1401edf4d  xor     r9d, r9d; ObjectType
0x1401edf50  lea     r8, [rsp+0A8h+NewDescriptor]; NewDescriptor
0x1401edf58  mov     rdx, rsi; ExplicitDescriptor
0x1401edf5b  lea     rcx, [rdi+1Ch]; ParentDescriptor
0x1401edf5f  call    cs:__imp_SeAssignSecurityEx
0x1401edf66  nop     dword ptr [rax+rax+00h]
0x1401edf6b  mov     edi, eax
0x1401edf6d  test    eax, eax
0x1401edf6f  js      short loc_1401EDFB8
0x1401edf71  mov     [rsp+0A8h+var_57], 1
0x1401edf76  mov     rcx, [rsp+0A8h+NewDescriptor]; SecurityDescriptor
0x1401edf7e  call    cs:__imp_RtlLengthSecurityDescriptor
0x1401edf85  nop     dword ptr [rax+rax+00h]
0x1401edf8a  test    eax, eax
0x1401edf8c  jz      loc_1401EE013
0x1401edf92  mov     [rsp+0A8h+IsDirectoryObject], 1; char
0x1401edf97  mov     r9b, 1
0x1401edf9a  mov     r8d, eax; Length
0x1401edf9d  mov     rdx, [rsp+0A8h+NewDescriptor]; SecurityDescriptor
0x1401edfa5  mov     rcx, r13; int
0x1401edfa8  call    NtfsCacheSharedSecurityByDescriptor
0x1401edfad  mov     rdi, rax
0x1401edfb0  xor     sil, sil
0x1401edfb3  jmp     loc_1401EDE50
0x1401edfb8  movzx   ecx, cs:NtfsStatusDebugFlags
0x1401edfbf  test    cl, cl
0x1401edfc1  jz      short loc_1401EDFFA
0x1401edfc3  cmp     edi, 0FFFFFFEDh
0x1401edfc6  jnb     short loc_1401EDFFA
0x1401edfc8  cmp     edi, 0C0000016h
0x1401edfce  jz      short loc_1401EDFFA
0x1401edfd0  cmp     edi, 0C0000011h
0x1401edfd6  jz      short loc_1401EDFFA
0x1401edfd8  add     eax, 7FFFFFFBh
0x1401edfdd  cmp     eax, 1
0x1401edfe0  jbe     short loc_1401EDFFA
0x1401edfe2  cmp     edi, 0C00000D8h
0x1401edfe8  jz      short loc_1401EDFFA
0x1401edfea  mov     r8d, 1F1AEDh
0x1401edff0  mov     edx, edi
0x1401edff2  mov     rcx, r13
0x1401edff5  call    NtfsStatusTraceAndDebugInternal
0x1401edffa  mov     qword ptr [rsp+0A8h+IsDirectoryObject], 1F1AEDh
0x1401ee003  xor     r9d, r9d
0x1401ee006  xor     r8d, r8d
0x1401ee009  mov     edx, edi
0x1401ee00b  mov     rcx, r13
0x1401ee00e  call    NtfsRaiseStatusInternal
0x1401ee013  movzx   eax, cs:NtfsStatusDebugFlags
0x1401ee01a  test    al, al
0x1401ee01c  jz      short loc_1401EE031
0x1401ee01e  mov     edx, 0C000000Dh
0x1401ee023  mov     r8d, 1F1B11h
0x1401ee029  mov     rcx, r13
0x1401ee02c  call    NtfsStatusTraceAndDebugInternal
0x1401ee031  mov     qword ptr [rsp+0A8h+IsDirectoryObject], 1F1B11h
0x1401ee03a  xor     r9d, r9d
0x1401ee03d  xor     r8d, r8d
0x1401ee040  mov     edx, 0C000000Dh
0x1401ee045  mov     rcx, r13
0x1401ee048  call    NtfsRaiseStatusInternal
0x1401ee04d  nop
0x1401ee04e  test    r14, r14
0x1401ee051  jz      short loc_1401EE089
0x1401ee053  test    sil, sil
0x1401ee056  jnz     short loc_1401EE072
0x1401ee058  mov     rcx, [r13+68h]
0x1401ee05c  add     rcx, 298h; Mutex
0x1401ee063  call    cs:__imp_KeAcquireGuardedMutex
0x1401ee06a  nop     dword ptr [rax+rax+00h]
0x1401ee06f  mov     sil, 1
0x1401ee072  add     dword ptr [r14], 0FFFFFFFFh
0x1401ee076  jnz     short loc_1401EE089
0x1401ee078  xor     edx, edx; Tag
0x1401ee07a  mov     rcx, r14; P
0x1401ee07d  call    cs:__imp_ExFreePoolWithTag
0x1401ee084  nop     dword ptr [rax+rax+00h]
0x1401ee089  test    sil, sil
0x1401ee08c  jz      short loc_1401EE0A5
0x1401ee08e  mov     rcx, [r13+68h]
0x1401ee092  add     rcx, 298h; Mutex
0x1401ee099  call    cs:__imp_KeReleaseGuardedMutex
0x1401ee0a0  nop     dword ptr [rax+rax+00h]
0x1401ee0a5  mov     r14, [rsp+0A8h+NewDescriptor]
0x1401ee0ad  mov     rsi, [rbx+48h]
0x1401ee0b1  test    dword ptr [rbx+0Ch], 4000000h
0x1401ee0b8  jnz     short loc_1401EE0D1
0x1401ee0ba  mov     rcx, [rsi+30h]; P
0x1401ee0be  test    rcx, rcx
0x1401ee0c1  jz      short loc_1401EE0D1
0x1401ee0c3  xor     edx, edx; Tag
0x1401ee0c5  call    cs:__imp_ExFreePoolWithTag
0x1401ee0cc  nop     dword ptr [rax+rax+00h]
0x1401ee0d1  mov     eax, [rbx+0Ch]
0x1401ee0d4  cmp     [rsp+0A8h+var_56], 0
0x1401ee0d9  jz      short loc_1401EE113
0x1401ee0db  btr     eax, 1Ah
0x1401ee0df  mov     [rbx+0Ch], eax
0x1401ee0e2  mov     [rsi+30h], r14
0x1401ee0e6  cmp     [rsp+0A8h+SecurityDescriptor], 0
0x1401ee0ec  jz      short loc_1401EE0FF
0x1401ee0ee  lea     rcx, [rsp+0A8h+SecurityDescriptor]; SecurityDescriptor
0x1401ee0f3  call    cs:__imp_SeDeassignSecurity
0x1401ee0fa  nop     dword ptr [rax+rax+00h]
0x1401ee0ff  mov     rax, rdi
0x1401ee102  add     rsp, 70h
0x1401ee106  pop     r15
0x1401ee108  pop     r14
0x1401ee10a  pop     r13
0x1401ee10c  pop     r12
0x1401ee10e  pop     rdi
0x1401ee10f  pop     rsi
0x1401ee110  pop     rbx
0x1401ee111  retn
0x1401ee113  bts     eax, 1Ah
0x1401ee117  jmp     short loc_1401EE0DF
0x1401ee119  cmp     [rdx+40h], sil
0x1401ee11d  jz      loc_1401EE1AF
0x1401ee123  mov     cl, 1
0x1401ee125  jmp     loc_1401EDDC7
0x1401ee12a  cmp     al, 0Dh
0x1401ee12c  jz      short loc_1401EE119
0x1401ee12e  cmp     al, 6
0x1401ee130  jnz     short loc_1401EE178
0x1401ee132  mov     r8d, [rcx+10h]
0x1401ee136  lea     eax, [r8-0Ah]
0x1401ee13a  cmp     eax, 3Eh ; '>'
0x1401ee13d  ja      short loc_1401EE15D
0x1401ee13f  mov     r9, 4080000000000003h
0x1401ee149  bt      r9, rax
0x1401ee14d  jnb     short loc_1401EE15D
0x1401ee14f  movzx   ecx, byte ptr [rcx+2]
0x1401ee153  not     cl
0x1401ee155  and     cl, 1
0x1401ee158  jmp     loc_1401EDDC7
0x1401ee15d  cmp     r8d, 47h ; 'G'
0x1401ee161  jnz     loc_1401EDDC3
0x1401ee167  test    byte ptr [rcx+2], 1
0x1401ee16b  jz      loc_1401EDDC3
0x1401ee171  mov     cl, 1
0x1401ee173  jmp     loc_1401EDDC7
0x1401ee178  cmp     al, 5
0x1401ee17a  jnz     loc_1401EDDC3
0x1401ee180  cmp     dword ptr [rcx+10h], 47h ; 'G'
0x1401ee184  jnz     loc_1401EDDC3
0x1401ee18a  test    byte ptr [rcx+2], 1
0x1401ee18e  mov     cl, 1
0x1401ee190  jz      loc_1401EDDC3
0x1401ee196  jmp     loc_1401EDDC7
0x1401ee19b  call    cs:__imp_ExGetPreviousMode
0x1401ee1a2  nop     dword ptr [rax+rax+00h]
0x1401ee1a7  movzx   ecx, al
0x1401ee1aa  jmp     loc_1401EDDC7
0x1401ee1af  cmp     byte ptr [rcx+1], 4
0x1401ee1b3  jnz     loc_1401EE123
0x1401ee1b9  xor     cl, cl
0x1401ee1bb  jmp     loc_1401EDDC7
0x1401ee1c0  call    NtfsLoadSecurityDescriptor
0x1401ee1c5  jmp     loc_1401EDD73
0x1402b1750  push    rbx
0x1402b1752  push    rbp
0x1402b1753  push    rsi
0x1402b1754  push    rdi
0x1402b1755  sub     rsp, 58h
  ... truncated ...
```
