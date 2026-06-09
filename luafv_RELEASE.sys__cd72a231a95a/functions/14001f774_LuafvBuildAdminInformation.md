# LuafvBuildAdminInformation

- ea: `0x14001f774`
- end: `0x14001fc39`
- name: `LuafvBuildAdminInformation`
- size: `1221`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001f5d0`

## callees

- `0x140006000`
- `0x14001f774`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x14001f90b`
- `ntoskrnl!RtlEqualSid` at `0x14001f90b`
- `ntoskrnl!RtlLengthSid` at `0x14001f850`
- `ntoskrnl!RtlLengthSid` at `0x14001fb69`
- `ntoskrnl!RtlLengthSid` at `0x14001f850`
- `ntoskrnl!RtlLengthSid` at `0x14001fb69`
- `ntoskrnl!SeQueryInformationToken` at `0x14001f7e5`
- `ntoskrnl!SeQueryInformationToken` at `0x14001f7e5`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14001fbb9`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14001fbb9`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14001fb42`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14001fb42`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f8d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f8d3`
- `ntoskrnl!ExAllocatePool2` at `0x14001f95b`
- `ntoskrnl!ExAllocatePool2` at `0x14001f95b`
- `ntoskrnl!SeExports` at `0x14001f8f6`
- `ntoskrnl!SeExports` at `0x14001fa81`
- `ntoskrnl!SeExports` at `0x14001fb8f`
- `ntoskrnl!SeExports` at `0x14001fbca`
- `ntoskrnl!RtlCopySidAndAttributesArray` at `0x14001fa50`
- `ntoskrnl!RtlCopySidAndAttributesArray` at `0x14001fc28`
- `ntoskrnl!RtlCopySidAndAttributesArray` at `0x14001fa50`
- `ntoskrnl!RtlCopySidAndAttributesArray` at `0x14001fc28`
- `ntoskrnl!RtlSidHashInitialize` at `0x14001fabc`
- `ntoskrnl!RtlSidHashInitialize` at `0x14001fabc`
- `ntoskrnl!RtlCopyLuidAndAttributesArray` at `0x14001fb0a`
- `ntoskrnl!RtlCopyLuidAndAttributesArray` at `0x14001fb0a`
- `FLTMGR!FltReleasePushLockEx` at `0x14001f99d`
- `FLTMGR!FltReleasePushLockEx` at `0x14001f99d`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001f982`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001f982`

## pseudocode

```c
__int64 __fastcall LuafvBuildAdminInformation(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rax
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectContext; // rbx
  char v4; // di
  PACCESS_TOKEN ClientToken; // rcx
  NTSTATUS v6; // ebx
  unsigned int *v7; // r12
  unsigned int v8; // r14d
  unsigned __int64 v9; // rbx
  unsigned int v10; // edi
  unsigned int v11; // r13d
  unsigned int i; // r15d
  ULONG v13; // esi
  unsigned __int64 v14; // rcx
  unsigned int v15; // edi
  unsigned int v17; // r12d
  unsigned int v18; // ebx
  __int64 Pool2; // rax
  __int64 v20; // r14
  _QWORD *v21; // r14
  unsigned int *v22; // rbx
  ULONG v23; // ecx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rbx
  ULONG v27; // ecx
  _QWORD *v28; // rax
  ULONG j; // edi
  __int64 v30; // rdx
  unsigned int *v31; // [rsp+40h] [rbp-39h]
  unsigned int *v32; // [rsp+48h] [rbp-31h]
  struct _SID_AND_ATTRIBUTES Sid[2]; // [rsp+50h] [rbp-29h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+70h] [rbp-9h] BYREF
  ULONG SidAreaSize; // [rsp+E0h] [rbp+67h] BYREF
  _QWORD *v36; // [rsp+E8h] [rbp+6Fh]
  PVOID TokenInformation; // [rsp+F0h] [rbp+77h] BYREF
  PSID Sid2; // [rsp+F8h] [rbp+7Fh] BYREF

  v36 = a2;
  v2 = *(_QWORD *)(a1 + 16);
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  TokenInformation = 0;
  Sid2 = 0;
  SidAreaSize = 0;
  if ( *(_BYTE *)(v2 + 4) )
  {
    p_SubjectContext = &SubjectContext;
    SeCaptureSubjectContext(&SubjectContext);
    v4 = 1;
  }
  else
  {
    p_SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(*(_QWORD *)(v2 + 24) + 8LL) + 32LL);
    v4 = 0;
  }
  ClientToken = p_SubjectContext->ClientToken;
  if ( !p_SubjectContext->ClientToken )
    ClientToken = p_SubjectContext->PrimaryToken;
  v6 = SeQueryInformationToken(ClientToken, TokenAccessInformation, &TokenInformation);
  if ( v4 )
    SeReleaseSubjectContext(&SubjectContext);
  if ( v6 >= 0 )
  {
    v7 = *(unsigned int **)TokenInformation;
    v31 = *(unsigned int **)TokenInformation;
    v8 = **(_DWORD **)TokenInformation;
    v9 = 16LL * v8;
    if ( v9 <= 0xFFFFFFFF )
    {
      v10 = 0;
      v32 = (unsigned int *)*((_QWORD *)TokenInformation + 2);
      v11 = -1;
      for ( i = -1; v10 < v8; ++v10 )
      {
        Sid2 = *(PSID *)(*((_QWORD *)v7 + 1) + 16LL * v10);
        LODWORD(v9) = RtlLengthSid(Sid2) + v9;
        if ( v11 == -1 && RtlEqualSid(SeExports->SeAliasAdminsSid, Sid2) )
        {
          v11 = v10;
        }
        else if ( i == -1 && (*(_BYTE *)(*((_QWORD *)v7 + 1) + 16LL * v10 + 8) & 0x60) == 0x60 )
        {
          i = v10;
        }
      }
      v13 = 0;
      if ( v11 == -1 )
      {
        v13 = 1;
        Sid[0].Sid = SeExports->SeAliasAdminsSid;
        Sid[0].Attributes = 7;
      }
      if ( i == -1 )
      {
        v30 = v13++;
        Sid[v30].Sid = SeExports->SeHighMandatorySid;
        Sid[v30].Attributes = 96;
      }
      if ( v13 )
      {
        LODWORD(v9) = 16 * v13 + v9;
        for ( j = 0; j < v13; ++j )
          LODWORD(v9) = RtlLengthSid(Sid[j].Sid) + v9;
      }
      if ( (int)v9 + 8 < (unsigned int)v9 )
      {
        v15 = -1073741675;
        goto LABEL_23;
      }
      v14 = 12LL * *v32;
      if ( v14 <= 0xFFFFFFFF )
      {
        v17 = (v9 + 8) & 0xFFFFFFF8;
        v18 = v17 + v14 + 920 - 12;
        if ( !(_DWORD)v14 )
          v18 = v17 + 920;
        if ( v18 >= 0xFFFFFFF8 )
          goto LABEL_38;
        Pool2 = ExAllocatePool2(256, v18 + 8, 1717663052);
        v20 = Pool2;
        if ( !Pool2 )
          goto LABEL_38;
        *(_DWORD *)Pool2 = v18;
        *(_BYTE *)(Pool2 + 4) = -1;
        FltAcquirePushLockExclusiveEx(&PoolLock, 0);
        dword_14000ECBC += v18;
        FltReleasePushLockEx(&PoolLock, 0);
        v21 = (_QWORD *)(v20 + 8);
        if ( v21 )
        {
          v15 = 0;
          memset(v21, 0, 0x58u);
          v22 = (unsigned int *)(v21 + 11);
          v21[3] = *((_QWORD *)TokenInformation + 3);
          *((_DWORD *)v21 + 8) = *((_DWORD *)TokenInformation + 8);
          *((_DWORD *)v21 + 9) = *((_DWORD *)TokenInformation + 9);
          *((_DWORD *)v21 + 10) = *((_DWORD *)TokenInformation + 10);
          *((_DWORD *)v21 + 11) = *((_DWORD *)TokenInformation + 11) & 0xFFFF9FFF | 0x2000;
          v23 = v13 + *v31;
          v21[12] = v21 + 45;
          *((_DWORD *)v21 + 22) = v23;
          RtlCopySidAndAttributesArray(
            *v31,
            *((PSID_AND_ATTRIBUTES *)v31 + 1),
            v17 - 16 * v23,
            (PSID_AND_ATTRIBUTES)(v21 + 45),
            &v21[2 * v23 + 45],
            &Sid2,
            &SidAreaSize);
          if ( v11 != -1 )
            *(_DWORD *)(v21[12] + 16LL * v11 + 8) = 7;
          if ( i != -1 )
          {
            v24 = 2LL * i;
            *(_QWORD *)(v21[12] + 8 * v24) = SeExports->SeHighMandatorySid;
            *(_DWORD *)(v21[12] + 8 * v24 + 8) = 96;
          }
          if ( v13 )
            RtlCopySidAndAttributesArray(
              v13,
              Sid,
              SidAreaSize,
              (PSID_AND_ATTRIBUTES)(v21[12] + 16LL * *v31),
              Sid2,
              &Sid2,
              &SidAreaSize);
          RtlSidHashInitialize(v21[12], *v22, v21 + 11);
          *v21 = v22;
          v25 = v21[12] + v17;
          *(_DWORD *)v25 = 0;
          *(_QWORD *)(v25 + 8) = 0;
          v21[1] = v25;
          v25 += 272;
          *(_DWORD *)v25 = 0;
          v26 = v25 + 272;
          *(_QWORD *)(v25 + 8) = 0;
          v21[8] = v25;
          v21[7] = 0;
          v27 = *v32;
          *(_DWORD *)(v25 + 272) = *v32;
          RtlCopyLuidAndAttributesArray(v27, (PLUID_AND_ATTRIBUTES)(v32 + 1), (PLUID_AND_ATTRIBUTES)(v25 + 276));
          v28 = v36;
          v21[2] = v26;
          *v28 = v21;
        }
        else
        {
LABEL_38:
          v15 = -1073741670;
        }
        goto LABEL_23;
      }
    }
    v15 = -1073741811;
LABEL_23:
    ExFreePoolWithTag(TokenInformation, 0);
    return v15;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001f774  mov     [rsp-8+arg_8], rdx
0x14001f779  push    rbp
0x14001f77a  push    rbx
0x14001f77b  push    rsi
0x14001f77c  push    rdi
0x14001f77d  push    r12
0x14001f77f  push    r13
0x14001f781  push    r14
0x14001f783  push    r15
0x14001f785  lea     rbp, [rsp-1Fh]
0x14001f78a  sub     rsp, 98h
0x14001f791  mov     rax, [rcx+10h]
0x14001f795  xorps   xmm0, xmm0
0x14001f798  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x14001f79c  mov     [rbp+57h+TokenInformation], 0
0x14001f7a4  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x14001f7a8  mov     [rbp+57h+Sid2], 0
0x14001f7b0  mov     [rbp+57h+SidAreaSize], 0
0x14001f7b7  cmp     byte ptr [rax+4], 0
0x14001f7bb  jnz     loc_14001FB3A
0x14001f7c1  mov     rax, [rax+18h]
0x14001f7c5  mov     rbx, [rax+8]
0x14001f7c9  add     rbx, 20h ; ' '
0x14001f7cd  xor     dil, dil
0x14001f7d0  mov     rcx, [rbx]
0x14001f7d3  test    rcx, rcx
0x14001f7d6  jnz     short loc_14001F7DC
0x14001f7d8  mov     rcx, [rbx+10h]; Token
0x14001f7dc  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14001f7e0  mov     edx, 16h; TokenInformationClass
0x14001f7e5  call    cs:__imp_SeQueryInformationToken
0x14001f7ec  nop     dword ptr [rax+rax+00h]
0x14001f7f1  mov     ebx, eax
0x14001f7f3  test    dil, dil
0x14001f7f6  jnz     loc_14001FBB5
0x14001f7fc  test    ebx, ebx
0x14001f7fe  js      loc_14001FB88
0x14001f804  mov     rax, [rbp+57h+TokenInformation]
0x14001f808  mov     r8d, 0FFFFFFFFh
0x14001f80e  mov     r12, [rax]
0x14001f811  mov     [rbp+57h+var_90], r12
0x14001f815  mov     r14d, [r12]
0x14001f819  mov     ebx, r14d
0x14001f81c  shl     rbx, 4
0x14001f820  cmp     rbx, r8
0x14001f823  ja      loc_14001F8C8
0x14001f829  mov     rax, [rax+10h]
0x14001f82d  xor     edi, edi
0x14001f82f  mov     [rbp+57h+var_88], rax
0x14001f833  mov     r13d, r8d
0x14001f836  mov     r15d, r8d
0x14001f839  test    r14d, r14d
0x14001f83c  jz      short loc_14001F88C
0x14001f83e  mov     rax, [r12+8]
0x14001f843  mov     esi, edi
0x14001f845  add     rsi, rsi
0x14001f848  mov     rcx, [rax+rsi*8]; Sid
0x14001f84c  mov     [rbp+57h+Sid2], rcx
0x14001f850  call    cs:__imp_RtlLengthSid
0x14001f857  nop     dword ptr [rax+rax+00h]
0x14001f85c  add     ebx, eax
0x14001f85e  mov     r8d, 0FFFFFFFFh
0x14001f864  cmp     r13d, r8d
0x14001f867  jz      loc_14001F8F6
0x14001f86d  cmp     r15d, r8d
0x14001f870  jnz     short loc_14001F885
0x14001f872  mov     rax, [r12+8]
0x14001f877  mov     cl, [rax+rsi*8+8]
0x14001f87b  and     cl, 60h
0x14001f87e  cmp     cl, 60h ; '`'
0x14001f881  cmovz   r15d, edi
0x14001f885  inc     edi
0x14001f887  cmp     edi, r14d
0x14001f88a  jb      short loc_14001F83E
0x14001f88c  xor     esi, esi
0x14001f88e  cmp     r13d, r8d
0x14001f891  jz      loc_14001FB8F
0x14001f897  cmp     r15d, r8d
0x14001f89a  jz      loc_14001FBCA
0x14001f8a0  test    esi, esi
0x14001f8a2  jnz     loc_14001FB56
0x14001f8a8  lea     r12d, [rbx+8]
0x14001f8ac  cmp     r12d, ebx
0x14001f8af  jb      loc_14001FB30
0x14001f8b5  mov     rax, [rbp+57h+var_88]
0x14001f8b9  mov     eax, [rax]
0x14001f8bb  lea     rcx, [rax+rax*2]
0x14001f8bf  shl     rcx, 2
0x14001f8c3  cmp     rcx, r8
0x14001f8c6  jbe     short loc_14001F92D
0x14001f8c8  mov     edi, 0C000000Dh
0x14001f8cd  mov     rcx, [rbp+57h+TokenInformation]; P
0x14001f8d1  xor     edx, edx; Tag
0x14001f8d3  call    cs:__imp_ExFreePoolWithTag
0x14001f8da  nop     dword ptr [rax+rax+00h]
0x14001f8df  mov     eax, edi
0x14001f8e1  add     rsp, 98h
0x14001f8e8  pop     r15
0x14001f8ea  pop     r14
0x14001f8ec  pop     r13
0x14001f8ee  pop     r12
0x14001f8f0  pop     rdi
0x14001f8f1  pop     rsi
0x14001f8f2  pop     rbx
0x14001f8f3  pop     rbp
0x14001f8f4  retn
0x14001f8f6  mov     rax, cs:__imp_SeExports
0x14001f8fd  mov     rdx, [rbp+57h+Sid2]; Sid2
0x14001f901  mov     rcx, [rax]
0x14001f904  mov     rcx, [rcx+110h]; Sid1
0x14001f90b  call    cs:__imp_RtlEqualSid
0x14001f912  nop     dword ptr [rax+rax+00h]
0x14001f917  mov     r8d, 0FFFFFFFFh
0x14001f91d  test    al, al
0x14001f91f  jz      loc_14001F86D
0x14001f925  mov     r13d, edi
0x14001f928  jmp     loc_14001F885
0x14001f92d  and     r12d, 0FFFFFFF8h
0x14001f931  lea     eax, [rcx+398h]
0x14001f937  add     eax, r12d
0x14001f93a  test    ecx, ecx
0x14001f93c  lea     ebx, [rax-0Ch]
0x14001f93f  cmovz   ebx, eax
0x14001f942  lea     eax, [rbx+8]
0x14001f945  cmp     eax, 8
0x14001f948  jb      loc_14001FB26
0x14001f94e  mov     edx, eax
0x14001f950  mov     ecx, 100h
0x14001f955  mov     r8d, 6661754Ch
0x14001f95b  call    cs:__imp_ExAllocatePool2
0x14001f962  nop     dword ptr [rax+rax+00h]
0x14001f967  mov     r14, rax
0x14001f96a  test    rax, rax
0x14001f96d  jz      loc_14001FB26
0x14001f973  xor     edx, edx
0x14001f975  mov     [rax], ebx
0x14001f977  lea     rcx, PoolLock
0x14001f97e  mov     byte ptr [rax+4], 0FFh
0x14001f982  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001f989  nop     dword ptr [rax+rax+00h]
0x14001f98e  add     cs:dword_14000ECBC, ebx
0x14001f994  lea     rcx, PoolLock
0x14001f99b  xor     edx, edx
0x14001f99d  call    cs:__imp_FltReleasePushLockEx
0x14001f9a4  nop     dword ptr [rax+rax+00h]
0x14001f9a9  add     r14, 8
0x14001f9ad  jz      loc_14001FB26
0x14001f9b3  xor     edi, edi
0x14001f9b5  xor     edx, edx; Val
0x14001f9b7  mov     rcx, r14; void *
0x14001f9ba  lea     r8d, [rdi+58h]; Size
0x14001f9be  call    memset
0x14001f9c3  mov     rax, [rbp+57h+TokenInformation]
0x14001f9c7  lea     rbx, [r14+58h]
0x14001f9cb  mov     r10, [rbp+57h+var_90]
0x14001f9cf  lea     r9, [rbx+110h]; Dest
0x14001f9d6  mov     r8d, r12d
0x14001f9d9  mov     rcx, [rax+18h]
0x14001f9dd  mov     [r14+18h], rcx
0x14001f9e1  mov     rax, [rbp+57h+TokenInformation]
0x14001f9e5  mov     ecx, [rax+20h]
0x14001f9e8  mov     [r14+20h], ecx
0x14001f9ec  mov     rax, [rbp+57h+TokenInformation]
0x14001f9f0  mov     ecx, [rax+24h]
0x14001f9f3  mov     [r14+24h], ecx
0x14001f9f7  mov     rax, [rbp+57h+TokenInformation]
0x14001f9fb  mov     ecx, [rax+28h]
0x14001f9fe  mov     [r14+28h], ecx
0x14001fa02  mov     rax, [rbp+57h+TokenInformation]
0x14001fa06  mov     ecx, [rax+2Ch]
0x14001fa09  btr     ecx, 0Eh
0x14001fa0d  bts     ecx, 0Dh
0x14001fa11  mov     [r14+2Ch], ecx
0x14001fa15  mov     ecx, [r10]
0x14001fa18  add     ecx, esi
0x14001fa1a  mov     [rbx+8], r9
0x14001fa1e  mov     [rbx], ecx
0x14001fa20  mov     rdx, [r10+8]; Src
0x14001fa24  shl     ecx, 4
0x14001fa27  mov     eax, ecx
0x14001fa29  lea     rcx, [rbx+110h]
0x14001fa30  add     rcx, rax
0x14001fa33  sub     r8d, eax; SidAreaSize
0x14001fa36  lea     rax, [rbp+57h+SidAreaSize]
0x14001fa3a  mov     [rsp+0D0h+RemainingSidAreaSize], rax; RemainingSidAreaSize
0x14001fa3f  lea     rax, [rbp+57h+Sid2]
0x14001fa43  mov     [rsp+0D0h+RemainingSidArea], rax; RemainingSidArea
0x14001fa48  mov     [rsp+0D0h+SidArea], rcx; SidArea
0x14001fa4d  mov     ecx, [r10]; Count
0x14001fa50  call    cs:__imp_RtlCopySidAndAttributesArray
0x14001fa57  nop     dword ptr [rax+rax+00h]
0x14001fa5c  mov     edx, 0FFFFFFFFh
0x14001fa61  cmp     r13d, edx
0x14001fa64  jnb     short loc_14001FA78
0x14001fa66  mov     rax, [rbx+8]
0x14001fa6a  mov     ecx, r13d
0x14001fa6d  add     rcx, rcx
0x14001fa70  mov     dword ptr [rax+rcx*8+8], 7
0x14001fa78  cmp     r15d, edx
0x14001fa7b  jnb     short loc_14001FAA8
0x14001fa7d  mov     rcx, [rbx+8]
0x14001fa81  mov     rax, cs:__imp_SeExports
0x14001fa88  mov     edx, r15d
0x14001fa8b  add     rdx, rdx
0x14001fa8e  mov     rax, [rax]
0x14001fa91  mov     rax, [rax+1F0h]
0x14001fa98  mov     [rcx+rdx*8], rax
0x14001fa9c  mov     rax, [rbx+8]
0x14001faa0  mov     dword ptr [rax+rdx*8+8], 60h ; '`'
0x14001faa8  xor     r15d, r15d
0x14001faab  test    esi, esi
0x14001faad  jnz     loc_14001FBF4
0x14001fab3  mov     edx, [rbx]
0x14001fab5  mov     r8, rbx
0x14001fab8  mov     rcx, [rbx+8]
0x14001fabc  call    cs:__imp_RtlSidHashInitialize
0x14001fac3  nop     dword ptr [rax+rax+00h]
0x14001fac8  mov     rax, [rbp+57h+var_88]
0x14001facc  mov     [r14], rbx
0x14001facf  mov     edx, r12d
0x14001fad2  add     rdx, [rbx+8]
0x14001fad6  mov     [rdx], r15d
0x14001fad9  mov     [rdx+8], r15
0x14001fadd  mov     [r14+8], rdx
0x14001fae1  add     rdx, 110h
0x14001fae8  mov     [rdx], r15d
0x14001faeb  lea     rbx, [rdx+110h]
0x14001faf2  mov     [rdx+8], r15
0x14001faf6  lea     r8, [rbx+4]; Dest
0x14001fafa  mov     [r14+40h], rdx
0x14001fafe  lea     rdx, [rax+4]; Src
0x14001fb02  mov     [r14+38h], r15
0x14001fb06  mov     ecx, [rax]; Count
0x14001fb08  mov     [rbx], ecx
0x14001fb0a  call    cs:__imp_RtlCopyLuidAndAttributesArray
0x14001fb11  nop     dword ptr [rax+rax+00h]
0x14001fb16  mov     rax, [rbp+57h+arg_8]
0x14001fb1a  mov     [r14+10h], rbx
0x14001fb1e  mov     [rax], r14
0x14001fb21  jmp     loc_14001F8CD
0x14001fb26  mov     edi, 0C000009Ah
0x14001fb2b  jmp     loc_14001F8CD
0x14001fb30  mov     edi, 0C0000095h
0x14001fb35  jmp     loc_14001F8CD
0x14001fb3a  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14001fb3e  lea     rbx, [rbp+57h+SubjectContext]
0x14001fb42  call    cs:__imp_SeCaptureSubjectContext
0x14001fb49  nop     dword ptr [rax+rax+00h]
0x14001fb4e  mov     dil, 1
0x14001fb51  jmp     loc_14001F7D0
0x14001fb56  mov     eax, esi
0x14001fb58  shl     eax, 4
0x14001fb5b  add     ebx, eax
0x14001fb5d  xor     edi, edi
0x14001fb5f  mov     ecx, edi
0x14001fb61  add     rcx, rcx
0x14001fb64  mov     rcx, [rbp+rcx*8+57h+Sid]; Sid
0x14001fb69  call    cs:__imp_RtlLengthSid
0x14001fb70  nop     dword ptr [rax+rax+00h]
0x14001fb75  add     ebx, eax
0x14001fb77  inc     edi
0x14001fb79  cmp     edi, esi
0x14001fb7b  jb      short loc_14001FB5F
0x14001fb7d  mov     r8d, 0FFFFFFFFh
0x14001fb83  jmp     loc_14001F8A8
0x14001fb88  mov     eax, ebx
0x14001fb8a  jmp     loc_14001F8E1
0x14001fb8f  mov     rax, cs:__imp_SeExports
0x14001fb96  mov     esi, 1
0x14001fb9b  mov     rcx, [rax]
0x14001fb9e  mov     rax, [rcx+110h]
0x14001fba5  mov     [rbp+57h+Sid], rax
0x14001fba9  mov     [rbp+57h+var_78], 7
0x14001fbb0  jmp     loc_14001F897
0x14001fbb5  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14001fbb9  call    cs:__imp_SeReleaseSubjectContext
0x14001fbc0  nop     dword ptr [rax+rax+00h]
0x14001fbc5  jmp     loc_14001F7FC
0x14001fbca  mov     rax, cs:__imp_SeExports
0x14001fbd1  mov     edx, esi
0x14001fbd3  add     rdx, rdx
0x14001fbd6  inc     esi
0x14001fbd8  mov     rcx, [rax]
0x14001fbdb  mov     rax, [rcx+1F0h]
0x14001fbe2  mov     [rbp+rdx*8+57h+Sid], rax
0x14001fbe7  mov     [rbp+rdx*8+57h+var_78], 60h ; '`'
0x14001fbef  jmp     loc_14001F8A0
0x14001fbf4  mov     rax, [rbp+57h+var_90]
0x14001fbf8  lea     rdx, [rbp+57h+Sid]; Src
0x14001fbfc  mov     r8d, [rbp+57h+SidAreaSize]; SidAreaSize
0x14001fc00  mov     ecx, esi; Count
0x14001fc02  mov     r9d, [rax]
0x14001fc05  lea     rax, [rbp+57h+SidAreaSize]
0x14001fc09  mov     [rsp+0D0h+RemainingSidAreaSize], rax; RemainingSidAreaSize
0x14001fc0e  lea     rax, [rbp+57h+Sid2]
0x14001fc12  mov     [rsp+0D0h+RemainingSidArea], rax; RemainingSidArea
0x14001fc17  mov     rax, [rbp+57h+Sid2]
0x14001fc1b  shl     r9, 4
0x14001fc1f  add     r9, [rbx+8]; Dest
0x14001fc23  mov     [rsp+0D0h+SidArea], rax; SidArea
  ... truncated ...
```
