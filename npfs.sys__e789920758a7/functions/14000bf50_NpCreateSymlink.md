# NpCreateSymlink

- ea: `0x14000bf50`
- end: `0x14000c3ab`
- name: `NpCreateSymlink`
- size: `1115`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, int, struct _UNICODE_PREFIX_TABLE *, struct _SECURITY_SUBJECT_CONTEXT *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000b15c`

## callees

- `0x140001f40`
- `0x140002240`
- `0x14000bf50`
- `0x140012730`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000bfd3`
- `ntoskrnl!ExAllocatePool2` at `0x14000c040`
- `ntoskrnl!ExAllocatePool2` at `0x14000c1f9`
- `ntoskrnl!ExAllocatePool2` at `0x14000c245`
- `ntoskrnl!ExAllocatePool2` at `0x14000bfd3`
- `ntoskrnl!ExAllocatePool2` at `0x14000c040`
- `ntoskrnl!ExAllocatePool2` at `0x14000c1f9`
- `ntoskrnl!ExAllocatePool2` at `0x14000c245`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c06c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c086`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c1bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c06c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c086`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c1bf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c276`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c276`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c28e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c28e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c362`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c362`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c36e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c36e`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000c14a`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000c14a`
- `ntoskrnl!SeAssignSecurity` at `0x14000c17c`
- `ntoskrnl!SeAssignSecurity` at `0x14000c17c`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000c0a3`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000c0a3`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x14000c31c`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x14000c31c`
- `ntoskrnl!KeInitializeEvent` at `0x14000c0f4`
- `ntoskrnl!KeInitializeEvent` at `0x14000c0f4`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x14000c1a7`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x14000c1a7`

## pseudocode

```c
__int64 __fastcall NpCreateSymlink(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        int a3,
        struct _UNICODE_PREFIX_TABLE *a4,
        struct _SECURITY_SUBJECT_CONTEXT *a5,
        _QWORD *a6)
{
  char *Pool2; // rax
  char *v11; // rsi
  NTSTATUS v12; // ebx
  char v13; // al
  __int64 v14; // rax
  void *v15; // rcx
  void *v16; // rcx
  __int64 v17; // rcx
  void *v18; // rcx
  struct _UNICODE_PREFIX_TABLE_ENTRY *v19; // rbp
  _QWORD *v20; // r14
  struct _SECURITY_SUBJECT_CONTEXT *v21; // rbx
  PACCESS_TOKEN ClientToken; // rdi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  unsigned int v24; // ecx
  void *v25; // rax
  _WORD *v26; // rbx
  __int64 v27; // rdx
  void *v28; // rax
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // r8
  _WORD *Prefix; // rax
  __int16 v33; // cx
  struct _UNICODE_PREFIX_TABLE **LastNextEntry; // rcx
  _QWORD *v35; // rdx
  __int128 v37[5]; // [rsp+40h] [rbp-58h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+A0h] [rbp+8h] BYREF

  v37[0] = 0;
  NewDescriptor = 0;
  if ( *a1 < 2u || (*a1 & 1) != 0 || *a2 < 2u || (*a2 & 1) != 0 )
    return (unsigned int)-1073741773;
  if ( (a3 & 0xFFFFFFFC) != 0 || (a3 & 3) == 3 )
    return (unsigned int)-1073741811;
  Pool2 = (char *)ExAllocatePool2(257, 408, 1281781838);
  v11 = Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  memset(Pool2, 0, 0x198u);
  v13 = v11[7];
  v11[4] |= 0x40u;
  v11[6] |= 2u;
  v11[7] = v13 & 0xF | 0x50;
  *((_QWORD *)v11 + 8) = v11 + 56;
  *((_QWORD *)v11 + 7) = v11 + 56;
  *((_QWORD *)v11 + 9) = 0;
  *((_QWORD *)v11 + 10) = 0;
  *((_QWORD *)v11 + 11) = 0;
  *((_QWORD *)v11 + 12) = 0;
  *((_DWORD *)v11 + 26) = 0;
  *((_QWORD *)v11 + 14) = 0;
  v14 = ExAllocatePool2(65, 56, 1281781838);
  *((_QWORD *)v11 + 6) = v14;
  if ( v14 )
  {
    *(_DWORD *)v14 = 1;
    *(_QWORD *)(v14 + 8) = 0;
    *(_DWORD *)(v14 + 16) = 0;
    KeInitializeEvent((PRKEVENT)(v14 + 24), SynchronizationEvent, 0);
    *(_DWORD *)v11 = 26739207;
    v19 = (struct _UNICODE_PREFIX_TABLE_ENTRY *)(v11 + 136);
    *((_DWORD *)v11 + 30) = 1;
    v20 = v11 + 232;
    *((_DWORD *)v11 + 31) = 1;
    *((_QWORD *)v11 + 16) = 0;
    *((_QWORD *)v11 + 18) = v11 + 136;
    *((_QWORD *)v11 + 17) = v11 + 136;
    *((_QWORD *)v11 + 30) = v11 + 232;
    *((_QWORD *)v11 + 29) = v11 + 232;
    *((_DWORD *)v11 + 62) = a3;
    v21 = a5;
    ClientToken = a5[2].ClientToken;
    GenericMapping = IoGetFileObjectGenericMapping();
    v12 = SeAssignSecurity(0, ClientToken, &NewDescriptor, 0, v21 + 1, GenericMapping, PagedPool);
    if ( v12 < 0 )
      goto LABEL_11;
    v12 = ObLogSecurityDescriptor(NewDescriptor, v11 + 152, 1);
    ExFreePoolWithTag(NewDescriptor, 0);
    if ( v12 < 0 )
      goto LABEL_11;
    v24 = *a1;
    *((_WORD *)v11 + 80) = v24;
    *((_WORD *)v11 + 81) = *a1;
    v25 = (void *)ExAllocatePool2(257, v24, 1281781838);
    v26 = 0;
    *((_QWORD *)v11 + 21) = v25;
    if ( v25 )
    {
      memmove(v25, *((const void **)a1 + 1), *((unsigned __int16 *)v11 + 80));
      v27 = *a2;
      *((_WORD *)v11 + 128) = v27;
      *((_WORD *)v11 + 129) = v27;
      v28 = (void *)ExAllocatePool2(257, v27, 1281781838);
      *((_QWORD *)v11 + 33) = v28;
      if ( v28 )
      {
        memmove(v28, *((const void **)a2 + 1), *((unsigned __int16 *)v11 + 128));
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(&a4[8], 0, v29, v30);
        LOBYTE(v31) = 1;
        Prefix = (_WORD *)NpFindPrefix(a4, a1, v31, v37);
        if ( Prefix )
        {
          v33 = *Prefix;
          if ( *Prefix == 514 || v33 == 519 )
            goto LABEL_29;
          if ( v33 == 515 )
          {
            if ( !LOWORD(v37[0]) )
            {
LABEL_29:
              v12 = -1073741771;
              goto LABEL_36;
            }
            v26 = Prefix;
          }
        }
        LastNextEntry = (struct _UNICODE_PREFIX_TABLE **)a4[8].LastNextEntry;
        if ( *LastNextEntry == (struct _UNICODE_PREFIX_TABLE *)&a4[8].NextPrefixTree )
        {
          *((_QWORD *)v11 + 18) = LastNextEntry;
          *(_QWORD *)&v19->NodeTypeCode = (char *)a4 + 200;
          *LastNextEntry = (struct _UNICODE_PREFIX_TABLE *)v19;
          a4[8].LastNextEntry = v19;
          RtlInsertUnicodePrefix(a4 + 9, (PUNICODE_STRING)v11 + 10, (PUNICODE_PREFIX_TABLE_ENTRY)(v11 + 176));
          if ( !v26 )
          {
LABEL_35:
            v12 = 0;
            *a6 = v11;
            v11 = 0;
LABEL_36:
            ExReleasePushLockExclusiveEx(&a4[8], 0);
            KeLeaveCriticalRegion();
            if ( !v11 )
              return (unsigned int)v12;
            goto LABEL_11;
          }
          v35 = (_QWORD *)*((_QWORD *)v26 + 32);
          if ( (_WORD *)*v35 == v26 + 124 )
          {
            *v20 = v26 + 124;
            *((_QWORD *)v11 + 30) = v35;
            *v35 = v20;
            *((_QWORD *)v26 + 32) = v20;
            goto LABEL_35;
          }
        }
        __fastfail(3u);
      }
    }
  }
  v12 = -1073741670;
LABEL_11:
  v15 = (void *)*((_QWORD *)v11 + 33);
  if ( v15 )
    ExFreePoolWithTag(v15, 0);
  v16 = (void *)*((_QWORD *)v11 + 21);
  if ( v16 )
    ExFreePoolWithTag(v16, 0);
  v17 = *((_QWORD *)v11 + 19);
  if ( v17 )
    ObDereferenceSecurityDescriptor(v17, 1);
  v18 = (void *)*((_QWORD *)v11 + 6);
  if ( v18 )
    ExFreePoolWithTag(v18, 0);
  ExFreePoolWithTag(v11, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000bf50  mov     rax, rsp
0x14000bf53  push    rbx
0x14000bf54  push    rbp
0x14000bf55  push    rsi
0x14000bf56  push    rdi
0x14000bf57  push    r12
0x14000bf59  push    r13
0x14000bf5b  push    r14
0x14000bf5d  push    r15
0x14000bf5f  sub     rsp, 58h
0x14000bf63  xor     edi, edi
0x14000bf65  xorps   xmm0, xmm0
0x14000bf68  movups  xmmword ptr [rax-58h], xmm0
0x14000bf6c  mov     [rax+8], rdi
0x14000bf70  mov     r13, r9
0x14000bf73  movzx   eax, word ptr [rcx]
0x14000bf76  mov     ebx, r8d
0x14000bf79  lea     ebp, [rdi+2]
0x14000bf7c  mov     r12, rdx
0x14000bf7f  mov     r15, rcx
0x14000bf82  cmp     bp, ax
0x14000bf85  ja      loc_14000C392
0x14000bf8b  test    al, 1
0x14000bf8d  jnz     loc_14000C392
0x14000bf93  movzx   eax, word ptr [rdx]
0x14000bf96  cmp     bp, ax
0x14000bf99  ja      loc_14000C392
0x14000bf9f  test    al, 1
0x14000bfa1  jnz     loc_14000C392
0x14000bfa7  test    ebx, 0FFFFFFFCh
0x14000bfad  jnz     loc_14000C38B
0x14000bfb3  mov     eax, ebx
0x14000bfb5  and     eax, 3
0x14000bfb8  cmp     al, 3
0x14000bfba  jz      loc_14000C38B
0x14000bfc0  mov     r14d, 4C66704Eh
0x14000bfc6  mov     edx, 198h
0x14000bfcb  mov     r8d, r14d
0x14000bfce  mov     ecx, 101h
0x14000bfd3  call    cs:__imp_ExAllocatePool2
0x14000bfda  nop     dword ptr [rax+rax+00h]
0x14000bfdf  mov     rsi, rax
0x14000bfe2  test    rax, rax
0x14000bfe5  jnz     short loc_14000BFF1
0x14000bfe7  mov     ebx, 0C000009Ah
0x14000bfec  jmp     loc_14000C397
0x14000bff1  xor     edx, edx; Val
0x14000bff3  mov     r8d, 198h; Size
0x14000bff9  mov     rcx, rsi; void *
0x14000bffc  call    memset
0x14000c001  mov     al, [rsi+7]
0x14000c004  mov     edx, 38h ; '8'
0x14000c009  or      byte ptr [rsi+4], 40h
0x14000c00d  and     al, 0Fh
0x14000c00f  or      [rsi+6], bpl
0x14000c013  or      al, 50h
0x14000c015  mov     [rsi+7], al
0x14000c018  mov     r8d, r14d
0x14000c01b  lea     rax, [rsi+38h]
0x14000c01f  mov     [rax+8], rax
0x14000c023  lea     ecx, [rdx+9]
0x14000c026  mov     [rax], rax
0x14000c029  mov     [rsi+48h], rdi
0x14000c02d  mov     [rsi+50h], rdi
0x14000c031  mov     [rsi+58h], rdi
0x14000c035  mov     [rsi+60h], rdi
0x14000c039  mov     [rsi+68h], edi
0x14000c03c  mov     [rsi+70h], rdi
0x14000c040  call    cs:__imp_ExAllocatePool2
0x14000c047  nop     dword ptr [rax+rax+00h]
0x14000c04c  mov     [rsi+30h], rax
0x14000c050  test    rax, rax
0x14000c053  jnz     loc_14000C0DC
0x14000c059  mov     ebx, 0C000009Ah
0x14000c05e  mov     rcx, [rsi+108h]; P
0x14000c065  test    rcx, rcx
0x14000c068  jz      short loc_14000C078
0x14000c06a  xor     edx, edx; Tag
0x14000c06c  call    cs:__imp_ExFreePoolWithTag
0x14000c073  nop     dword ptr [rax+rax+00h]
0x14000c078  mov     rcx, [rsi+0A8h]; P
0x14000c07f  test    rcx, rcx
0x14000c082  jz      short loc_14000C092
0x14000c084  xor     edx, edx; Tag
0x14000c086  call    cs:__imp_ExFreePoolWithTag
0x14000c08d  nop     dword ptr [rax+rax+00h]
0x14000c092  mov     rcx, [rsi+98h]
0x14000c099  test    rcx, rcx
0x14000c09c  jz      short loc_14000C0AF
0x14000c09e  mov     edx, 1
0x14000c0a3  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000c0aa  nop     dword ptr [rax+rax+00h]
0x14000c0af  mov     rcx, [rsi+30h]; P
0x14000c0b3  test    rcx, rcx
0x14000c0b6  jz      short loc_14000C0C6
0x14000c0b8  xor     edx, edx; Tag
0x14000c0ba  call    cs:__imp_ExFreePoolWithTag
0x14000c0c1  nop     dword ptr [rax+rax+00h]
0x14000c0c6  xor     edx, edx; Tag
0x14000c0c8  mov     rcx, rsi; P
0x14000c0cb  call    cs:__imp_ExFreePoolWithTag
0x14000c0d2  nop     dword ptr [rax+rax+00h]
0x14000c0d7  jmp     loc_14000C397
0x14000c0dc  xor     r8d, r8d; State
0x14000c0df  mov     dword ptr [rax], 1
0x14000c0e5  lea     rcx, [rax+18h]; Event
0x14000c0e9  mov     [rax+8], rdi
0x14000c0ed  mov     [rax+10h], edi
0x14000c0f0  lea     edx, [r8+1]; Type
0x14000c0f4  call    cs:__imp_KeInitializeEvent
0x14000c0fb  nop     dword ptr [rax+rax+00h]
0x14000c100  mov     dword ptr [rsi], 1980207h
0x14000c106  lea     rbp, [rsi+88h]
0x14000c10d  mov     dword ptr [rsi+78h], 1
0x14000c114  lea     r14, [rsi+0E8h]
0x14000c11b  mov     dword ptr [rsi+7Ch], 1
0x14000c122  mov     [rsi+80h], rdi
0x14000c129  mov     [rbp+8], rbp
0x14000c12d  mov     [rbp+0], rbp
0x14000c131  mov     [r14+8], r14
0x14000c135  mov     [r14], r14
0x14000c138  mov     [rsi+0F8h], ebx
0x14000c13e  mov     rbx, [rsp+98h+arg_20]
0x14000c146  mov     rdi, [rbx+40h]
0x14000c14a  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000c151  nop     dword ptr [rax+rax+00h]
0x14000c156  lea     rcx, [rbx+20h]
0x14000c15a  mov     [rsp+98h+PoolType], 1; PoolType
0x14000c162  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x14000c167  lea     r8, [rsp+98h+NewDescriptor]; NewDescriptor
0x14000c16f  mov     [rsp+98h+SubjectContext], rcx; SubjectContext
0x14000c174  xor     r9d, r9d; IsDirectoryObject
0x14000c177  xor     ecx, ecx; ParentDescriptor
0x14000c179  mov     rdx, rdi; ExplicitDescriptor
0x14000c17c  call    cs:__imp_SeAssignSecurity
0x14000c183  nop     dword ptr [rax+rax+00h]
0x14000c188  mov     ebx, eax
0x14000c18a  test    eax, eax
0x14000c18c  js      loc_14000C05E
0x14000c192  mov     rcx, [rsp+98h+NewDescriptor]
0x14000c19a  lea     rdx, [rsi+98h]
0x14000c1a1  mov     r8d, 1
0x14000c1a7  call    cs:__imp_ObLogSecurityDescriptor
0x14000c1ae  nop     dword ptr [rax+rax+00h]
0x14000c1b3  mov     rcx, [rsp+98h+NewDescriptor]; P
0x14000c1bb  xor     edx, edx; Tag
0x14000c1bd  mov     ebx, eax
0x14000c1bf  call    cs:__imp_ExFreePoolWithTag
0x14000c1c6  nop     dword ptr [rax+rax+00h]
0x14000c1cb  test    ebx, ebx
0x14000c1cd  js      loc_14000C05E
0x14000c1d3  movzx   ecx, word ptr [r15]
0x14000c1d7  lea     rdi, [rsi+0A0h]
0x14000c1de  mov     [rdi], cx
0x14000c1e1  mov     edx, ecx
0x14000c1e3  movzx   eax, word ptr [r15]
0x14000c1e7  mov     ecx, 101h
0x14000c1ec  mov     r8d, 4C66704Eh
0x14000c1f2  mov     [rsi+0A2h], ax
0x14000c1f9  call    cs:__imp_ExAllocatePool2
0x14000c200  nop     dword ptr [rax+rax+00h]
0x14000c205  xor     ebx, ebx
0x14000c207  mov     [rsi+0A8h], rax
0x14000c20e  test    rax, rax
0x14000c211  jz      loc_14000C059
0x14000c217  movzx   r8d, word ptr [rdi]; Size
0x14000c21b  mov     rcx, rax; void *
0x14000c21e  mov     rdx, [r15+8]; Src
0x14000c222  call    memmove
0x14000c227  movzx   edx, word ptr [r12]
0x14000c22c  mov     ecx, 101h
0x14000c231  mov     r8d, 4C66704Eh
0x14000c237  mov     [rsi+100h], dx
0x14000c23e  mov     [rsi+102h], dx
0x14000c245  call    cs:__imp_ExAllocatePool2
0x14000c24c  nop     dword ptr [rax+rax+00h]
0x14000c251  mov     [rsi+108h], rax
0x14000c258  test    rax, rax
0x14000c25b  jz      loc_14000C059
0x14000c261  movzx   r8d, word ptr [rsi+100h]; Size
0x14000c269  mov     rcx, rax; void *
0x14000c26c  mov     rdx, [r12+8]; Src
0x14000c271  call    memmove
0x14000c276  call    cs:__imp_KeEnterCriticalRegion
0x14000c27d  nop     dword ptr [rax+rax+00h]
0x14000c282  lea     r12, [r13+0C0h]
0x14000c289  xor     edx, edx
0x14000c28b  mov     rcx, r12
0x14000c28e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c295  nop     dword ptr [rax+rax+00h]
0x14000c29a  lea     r9, [rsp+98h+var_58]
0x14000c29f  mov     r8b, 1
0x14000c2a2  mov     rdx, r15
0x14000c2a5  mov     rcx, r13
0x14000c2a8  call    NpFindPrefix
0x14000c2ad  xor     r8d, r8d
0x14000c2b0  test    rax, rax
0x14000c2b3  jz      short loc_14000C2E8
0x14000c2b5  movzx   ecx, word ptr [rax]
0x14000c2b8  mov     edx, 202h
0x14000c2bd  cmp     cx, dx
0x14000c2c0  jz      short loc_14000C2DE
0x14000c2c2  mov     edx, 207h
0x14000c2c7  cmp     cx, dx
0x14000c2ca  jz      short loc_14000C2DE
0x14000c2cc  mov     edx, 203h
0x14000c2d1  cmp     cx, dx
0x14000c2d4  jnz     short loc_14000C2E8
0x14000c2d6  cmp     word ptr [rsp+98h+var_58], r8w
0x14000c2dc  jnz     short loc_14000C2E5
0x14000c2de  mov     ebx, 0C0000035h
0x14000c2e3  jmp     short loc_14000C35D
0x14000c2e5  mov     rbx, rax
0x14000c2e8  lea     rax, [r13+0C8h]
0x14000c2ef  mov     rcx, [rax+8]
0x14000c2f3  cmp     [rcx], rax
0x14000c2f6  jnz     loc_14000C384
0x14000c2fc  mov     [rbp+8], rcx
0x14000c300  lea     r8, [rsi+0B0h]; PrefixTableEntry
0x14000c307  mov     [rbp+0], rax
0x14000c30b  mov     rdx, rdi; Prefix
0x14000c30e  mov     [rcx], rbp
0x14000c311  lea     rcx, [r13+0D8h]; PrefixTable
0x14000c318  mov     [rax+8], rbp
0x14000c31c  call    cs:__imp_RtlInsertUnicodePrefix
0x14000c323  nop     dword ptr [rax+rax+00h]
0x14000c328  xor     edi, edi
0x14000c32a  test    rbx, rbx
0x14000c32d  jz      short loc_14000C34D
0x14000c32f  lea     rax, [rbx+0F8h]
0x14000c336  mov     rdx, [rax+8]
0x14000c33a  cmp     [rdx], rax
0x14000c33d  jnz     short loc_14000C384
0x14000c33f  mov     [r14], rax
0x14000c342  mov     [r14+8], rdx
0x14000c346  mov     [rdx], r14
0x14000c349  mov     [rax+8], r14
0x14000c34d  mov     rax, [rsp+98h+arg_28]
0x14000c355  mov     ebx, edi
0x14000c357  mov     [rax], rsi
0x14000c35a  mov     rsi, rdi
0x14000c35d  xor     edx, edx
0x14000c35f  mov     rcx, r12
0x14000c362  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c369  nop     dword ptr [rax+rax+00h]
0x14000c36e  call    cs:__imp_KeLeaveCriticalRegion
0x14000c375  nop     dword ptr [rax+rax+00h]
0x14000c37a  test    rsi, rsi
0x14000c37d  jz      short loc_14000C397
0x14000c37f  jmp     loc_14000C05E
0x14000c384  mov     ecx, 3
0x14000c389  int     29h; Win8: RtlFailFast(ecx)
0x14000c38b  mov     ebx, 0C000000Dh
0x14000c390  jmp     short loc_14000C397
0x14000c392  mov     ebx, 0C0000033h
0x14000c397  mov     eax, ebx
0x14000c399  add     rsp, 58h
0x14000c39d  pop     r15
0x14000c39f  pop     r14
0x14000c3a1  pop     r13
0x14000c3a3  pop     r12
0x14000c3a5  pop     rdi
0x14000c3a6  pop     rsi
0x14000c3a7  pop     rbp
0x14000c3a8  pop     rbx
0x14000c3a9  retn
```
