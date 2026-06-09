# LuafvBuildAdminInformation

- ea: `0x14001f7c4`
- end: `0x14001fc89`
- name: `LuafvBuildAdminInformation`
- size: `1221`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001f620`

## callees

- `0x140006380`
- `0x14001f7c4`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x14001f95b`
- `ntoskrnl!RtlEqualSid` at `0x14001f95b`
- `ntoskrnl!RtlLengthSid` at `0x14001f8a0`
- `ntoskrnl!RtlLengthSid` at `0x14001fbb9`
- `ntoskrnl!RtlLengthSid` at `0x14001f8a0`
- `ntoskrnl!RtlLengthSid` at `0x14001fbb9`
- `ntoskrnl!SeQueryInformationToken` at `0x14001f835`
- `ntoskrnl!SeQueryInformationToken` at `0x14001f835`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14001fc09`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14001fc09`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14001fb92`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14001fb92`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f923`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f923`
- `ntoskrnl!ExAllocatePool2` at `0x14001f9ab`
- `ntoskrnl!ExAllocatePool2` at `0x14001f9ab`
- `ntoskrnl!SeExports` at `0x14001f946`
- `ntoskrnl!SeExports` at `0x14001fad1`
- `ntoskrnl!SeExports` at `0x14001fbdf`
- `ntoskrnl!SeExports` at `0x14001fc1a`
- `ntoskrnl!RtlCopySidAndAttributesArray` at `0x14001faa0`
- `ntoskrnl!RtlCopySidAndAttributesArray` at `0x14001fc78`
- `ntoskrnl!RtlCopySidAndAttributesArray` at `0x14001faa0`
- `ntoskrnl!RtlCopySidAndAttributesArray` at `0x14001fc78`
- `ntoskrnl!RtlSidHashInitialize` at `0x14001fb0c`
- `ntoskrnl!RtlSidHashInitialize` at `0x14001fb0c`
- `ntoskrnl!RtlCopyLuidAndAttributesArray` at `0x14001fb5a`
- `ntoskrnl!RtlCopyLuidAndAttributesArray` at `0x14001fb5a`
- `FLTMGR!FltReleasePushLockEx` at `0x14001f9ed`
- `FLTMGR!FltReleasePushLockEx` at `0x14001f9ed`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001f9d2`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001f9d2`

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
        dword_14000F2FC += v18;
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
0x14001f7c4  mov     [rsp-8+arg_8], rdx
0x14001f7c9  push    rbp
0x14001f7ca  push    rbx
0x14001f7cb  push    rsi
0x14001f7cc  push    rdi
0x14001f7cd  push    r12
0x14001f7cf  push    r13
0x14001f7d1  push    r14
0x14001f7d3  push    r15
0x14001f7d5  lea     rbp, [rsp-1Fh]
0x14001f7da  sub     rsp, 98h
0x14001f7e1  mov     rax, [rcx+10h]
0x14001f7e5  xorps   xmm0, xmm0
0x14001f7e8  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x14001f7ec  mov     [rbp+57h+TokenInformation], 0
0x14001f7f4  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x14001f7f8  mov     [rbp+57h+Sid2], 0
0x14001f800  mov     [rbp+57h+SidAreaSize], 0
0x14001f807  cmp     byte ptr [rax+4], 0
0x14001f80b  jnz     loc_14001FB8A
0x14001f811  mov     rax, [rax+18h]
0x14001f815  mov     rbx, [rax+8]
0x14001f819  add     rbx, 20h ; ' '
0x14001f81d  xor     dil, dil
0x14001f820  mov     rcx, [rbx]
0x14001f823  test    rcx, rcx
0x14001f826  jnz     short loc_14001F82C
0x14001f828  mov     rcx, [rbx+10h]; Token
0x14001f82c  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14001f830  mov     edx, 16h; TokenInformationClass
0x14001f835  call    cs:__imp_SeQueryInformationToken
0x14001f83c  nop     dword ptr [rax+rax+00h]
0x14001f841  mov     ebx, eax
0x14001f843  test    dil, dil
0x14001f846  jnz     loc_14001FC05
0x14001f84c  test    ebx, ebx
0x14001f84e  js      loc_14001FBD8
0x14001f854  mov     rax, [rbp+57h+TokenInformation]
0x14001f858  mov     r8d, 0FFFFFFFFh
0x14001f85e  mov     r12, [rax]
0x14001f861  mov     [rbp+57h+var_90], r12
0x14001f865  mov     r14d, [r12]
0x14001f869  mov     ebx, r14d
0x14001f86c  shl     rbx, 4
0x14001f870  cmp     rbx, r8
0x14001f873  ja      loc_14001F918
0x14001f879  mov     rax, [rax+10h]
0x14001f87d  xor     edi, edi
0x14001f87f  mov     [rbp+57h+var_88], rax
0x14001f883  mov     r13d, r8d
0x14001f886  mov     r15d, r8d
0x14001f889  test    r14d, r14d
0x14001f88c  jz      short loc_14001F8DC
0x14001f88e  mov     rax, [r12+8]
0x14001f893  mov     esi, edi
0x14001f895  add     rsi, rsi
0x14001f898  mov     rcx, [rax+rsi*8]; Sid
0x14001f89c  mov     [rbp+57h+Sid2], rcx
0x14001f8a0  call    cs:__imp_RtlLengthSid
0x14001f8a7  nop     dword ptr [rax+rax+00h]
0x14001f8ac  add     ebx, eax
0x14001f8ae  mov     r8d, 0FFFFFFFFh
0x14001f8b4  cmp     r13d, r8d
0x14001f8b7  jz      loc_14001F946
0x14001f8bd  cmp     r15d, r8d
0x14001f8c0  jnz     short loc_14001F8D5
0x14001f8c2  mov     rax, [r12+8]
0x14001f8c7  mov     cl, [rax+rsi*8+8]
0x14001f8cb  and     cl, 60h
0x14001f8ce  cmp     cl, 60h ; '`'
0x14001f8d1  cmovz   r15d, edi
0x14001f8d5  inc     edi
0x14001f8d7  cmp     edi, r14d
0x14001f8da  jb      short loc_14001F88E
0x14001f8dc  xor     esi, esi
0x14001f8de  cmp     r13d, r8d
0x14001f8e1  jz      loc_14001FBDF
0x14001f8e7  cmp     r15d, r8d
0x14001f8ea  jz      loc_14001FC1A
0x14001f8f0  test    esi, esi
0x14001f8f2  jnz     loc_14001FBA6
0x14001f8f8  lea     r12d, [rbx+8]
0x14001f8fc  cmp     r12d, ebx
0x14001f8ff  jb      loc_14001FB80
0x14001f905  mov     rax, [rbp+57h+var_88]
0x14001f909  mov     eax, [rax]
0x14001f90b  lea     rcx, [rax+rax*2]
0x14001f90f  shl     rcx, 2
0x14001f913  cmp     rcx, r8
0x14001f916  jbe     short loc_14001F97D
0x14001f918  mov     edi, 0C000000Dh
0x14001f91d  mov     rcx, [rbp+57h+TokenInformation]; P
0x14001f921  xor     edx, edx; Tag
0x14001f923  call    cs:__imp_ExFreePoolWithTag
0x14001f92a  nop     dword ptr [rax+rax+00h]
0x14001f92f  mov     eax, edi
0x14001f931  add     rsp, 98h
0x14001f938  pop     r15
0x14001f93a  pop     r14
0x14001f93c  pop     r13
0x14001f93e  pop     r12
0x14001f940  pop     rdi
0x14001f941  pop     rsi
0x14001f942  pop     rbx
0x14001f943  pop     rbp
0x14001f944  retn
0x14001f946  mov     rax, cs:__imp_SeExports
0x14001f94d  mov     rdx, [rbp+57h+Sid2]; Sid2
0x14001f951  mov     rcx, [rax]
0x14001f954  mov     rcx, [rcx+110h]; Sid1
0x14001f95b  call    cs:__imp_RtlEqualSid
0x14001f962  nop     dword ptr [rax+rax+00h]
0x14001f967  mov     r8d, 0FFFFFFFFh
0x14001f96d  test    al, al
0x14001f96f  jz      loc_14001F8BD
0x14001f975  mov     r13d, edi
0x14001f978  jmp     loc_14001F8D5
0x14001f97d  and     r12d, 0FFFFFFF8h
0x14001f981  lea     eax, [rcx+398h]
0x14001f987  add     eax, r12d
0x14001f98a  test    ecx, ecx
0x14001f98c  lea     ebx, [rax-0Ch]
0x14001f98f  cmovz   ebx, eax
0x14001f992  lea     eax, [rbx+8]
0x14001f995  cmp     eax, 8
0x14001f998  jb      loc_14001FB76
0x14001f99e  mov     edx, eax
0x14001f9a0  mov     ecx, 100h
0x14001f9a5  mov     r8d, 6661754Ch
0x14001f9ab  call    cs:__imp_ExAllocatePool2
0x14001f9b2  nop     dword ptr [rax+rax+00h]
0x14001f9b7  mov     r14, rax
0x14001f9ba  test    rax, rax
0x14001f9bd  jz      loc_14001FB76
0x14001f9c3  xor     edx, edx
0x14001f9c5  mov     [rax], ebx
0x14001f9c7  lea     rcx, PoolLock
0x14001f9ce  mov     byte ptr [rax+4], 0FFh
0x14001f9d2  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001f9d9  nop     dword ptr [rax+rax+00h]
0x14001f9de  add     cs:dword_14000F2FC, ebx
0x14001f9e4  lea     rcx, PoolLock
0x14001f9eb  xor     edx, edx
0x14001f9ed  call    cs:__imp_FltReleasePushLockEx
0x14001f9f4  nop     dword ptr [rax+rax+00h]
0x14001f9f9  add     r14, 8
0x14001f9fd  jz      loc_14001FB76
0x14001fa03  xor     edi, edi
0x14001fa05  xor     edx, edx; Val
0x14001fa07  mov     rcx, r14; void *
0x14001fa0a  lea     r8d, [rdi+58h]; Size
0x14001fa0e  call    memset
0x14001fa13  mov     rax, [rbp+57h+TokenInformation]
0x14001fa17  lea     rbx, [r14+58h]
0x14001fa1b  mov     r10, [rbp+57h+var_90]
0x14001fa1f  lea     r9, [rbx+110h]; Dest
0x14001fa26  mov     r8d, r12d
0x14001fa29  mov     rcx, [rax+18h]
0x14001fa2d  mov     [r14+18h], rcx
0x14001fa31  mov     rax, [rbp+57h+TokenInformation]
0x14001fa35  mov     ecx, [rax+20h]
0x14001fa38  mov     [r14+20h], ecx
0x14001fa3c  mov     rax, [rbp+57h+TokenInformation]
0x14001fa40  mov     ecx, [rax+24h]
0x14001fa43  mov     [r14+24h], ecx
0x14001fa47  mov     rax, [rbp+57h+TokenInformation]
0x14001fa4b  mov     ecx, [rax+28h]
0x14001fa4e  mov     [r14+28h], ecx
0x14001fa52  mov     rax, [rbp+57h+TokenInformation]
0x14001fa56  mov     ecx, [rax+2Ch]
0x14001fa59  btr     ecx, 0Eh
0x14001fa5d  bts     ecx, 0Dh
0x14001fa61  mov     [r14+2Ch], ecx
0x14001fa65  mov     ecx, [r10]
0x14001fa68  add     ecx, esi
0x14001fa6a  mov     [rbx+8], r9
0x14001fa6e  mov     [rbx], ecx
0x14001fa70  mov     rdx, [r10+8]; Src
0x14001fa74  shl     ecx, 4
0x14001fa77  mov     eax, ecx
0x14001fa79  lea     rcx, [rbx+110h]
0x14001fa80  add     rcx, rax
0x14001fa83  sub     r8d, eax; SidAreaSize
0x14001fa86  lea     rax, [rbp+57h+SidAreaSize]
0x14001fa8a  mov     [rsp+0D0h+RemainingSidAreaSize], rax; RemainingSidAreaSize
0x14001fa8f  lea     rax, [rbp+57h+Sid2]
0x14001fa93  mov     [rsp+0D0h+RemainingSidArea], rax; RemainingSidArea
0x14001fa98  mov     [rsp+0D0h+SidArea], rcx; SidArea
0x14001fa9d  mov     ecx, [r10]; Count
0x14001faa0  call    cs:__imp_RtlCopySidAndAttributesArray
0x14001faa7  nop     dword ptr [rax+rax+00h]
0x14001faac  mov     edx, 0FFFFFFFFh
0x14001fab1  cmp     r13d, edx
0x14001fab4  jnb     short loc_14001FAC8
0x14001fab6  mov     rax, [rbx+8]
0x14001faba  mov     ecx, r13d
0x14001fabd  add     rcx, rcx
0x14001fac0  mov     dword ptr [rax+rcx*8+8], 7
0x14001fac8  cmp     r15d, edx
0x14001facb  jnb     short loc_14001FAF8
0x14001facd  mov     rcx, [rbx+8]
0x14001fad1  mov     rax, cs:__imp_SeExports
0x14001fad8  mov     edx, r15d
0x14001fadb  add     rdx, rdx
0x14001fade  mov     rax, [rax]
0x14001fae1  mov     rax, [rax+1F0h]
0x14001fae8  mov     [rcx+rdx*8], rax
0x14001faec  mov     rax, [rbx+8]
0x14001faf0  mov     dword ptr [rax+rdx*8+8], 60h ; '`'
0x14001faf8  xor     r15d, r15d
0x14001fafb  test    esi, esi
0x14001fafd  jnz     loc_14001FC44
0x14001fb03  mov     edx, [rbx]
0x14001fb05  mov     r8, rbx
0x14001fb08  mov     rcx, [rbx+8]
0x14001fb0c  call    cs:__imp_RtlSidHashInitialize
0x14001fb13  nop     dword ptr [rax+rax+00h]
0x14001fb18  mov     rax, [rbp+57h+var_88]
0x14001fb1c  mov     [r14], rbx
0x14001fb1f  mov     edx, r12d
0x14001fb22  add     rdx, [rbx+8]
0x14001fb26  mov     [rdx], r15d
0x14001fb29  mov     [rdx+8], r15
0x14001fb2d  mov     [r14+8], rdx
0x14001fb31  add     rdx, 110h
0x14001fb38  mov     [rdx], r15d
0x14001fb3b  lea     rbx, [rdx+110h]
0x14001fb42  mov     [rdx+8], r15
0x14001fb46  lea     r8, [rbx+4]; Dest
0x14001fb4a  mov     [r14+40h], rdx
0x14001fb4e  lea     rdx, [rax+4]; Src
0x14001fb52  mov     [r14+38h], r15
0x14001fb56  mov     ecx, [rax]; Count
0x14001fb58  mov     [rbx], ecx
0x14001fb5a  call    cs:__imp_RtlCopyLuidAndAttributesArray
0x14001fb61  nop     dword ptr [rax+rax+00h]
0x14001fb66  mov     rax, [rbp+57h+arg_8]
0x14001fb6a  mov     [r14+10h], rbx
0x14001fb6e  mov     [rax], r14
0x14001fb71  jmp     loc_14001F91D
0x14001fb76  mov     edi, 0C000009Ah
0x14001fb7b  jmp     loc_14001F91D
0x14001fb80  mov     edi, 0C0000095h
0x14001fb85  jmp     loc_14001F91D
0x14001fb8a  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14001fb8e  lea     rbx, [rbp+57h+SubjectContext]
0x14001fb92  call    cs:__imp_SeCaptureSubjectContext
0x14001fb99  nop     dword ptr [rax+rax+00h]
0x14001fb9e  mov     dil, 1
0x14001fba1  jmp     loc_14001F820
0x14001fba6  mov     eax, esi
0x14001fba8  shl     eax, 4
0x14001fbab  add     ebx, eax
0x14001fbad  xor     edi, edi
0x14001fbaf  mov     ecx, edi
0x14001fbb1  add     rcx, rcx
0x14001fbb4  mov     rcx, [rbp+rcx*8+57h+Sid]; Sid
0x14001fbb9  call    cs:__imp_RtlLengthSid
0x14001fbc0  nop     dword ptr [rax+rax+00h]
0x14001fbc5  add     ebx, eax
0x14001fbc7  inc     edi
0x14001fbc9  cmp     edi, esi
0x14001fbcb  jb      short loc_14001FBAF
0x14001fbcd  mov     r8d, 0FFFFFFFFh
0x14001fbd3  jmp     loc_14001F8F8
0x14001fbd8  mov     eax, ebx
0x14001fbda  jmp     loc_14001F931
0x14001fbdf  mov     rax, cs:__imp_SeExports
0x14001fbe6  mov     esi, 1
0x14001fbeb  mov     rcx, [rax]
0x14001fbee  mov     rax, [rcx+110h]
0x14001fbf5  mov     [rbp+57h+Sid], rax
0x14001fbf9  mov     [rbp+57h+var_78], 7
0x14001fc00  jmp     loc_14001F8E7
0x14001fc05  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14001fc09  call    cs:__imp_SeReleaseSubjectContext
0x14001fc10  nop     dword ptr [rax+rax+00h]
0x14001fc15  jmp     loc_14001F84C
0x14001fc1a  mov     rax, cs:__imp_SeExports
0x14001fc21  mov     edx, esi
0x14001fc23  add     rdx, rdx
0x14001fc26  inc     esi
0x14001fc28  mov     rcx, [rax]
0x14001fc2b  mov     rax, [rcx+1F0h]
0x14001fc32  mov     [rbp+rdx*8+57h+Sid], rax
0x14001fc37  mov     [rbp+rdx*8+57h+var_78], 60h ; '`'
0x14001fc3f  jmp     loc_14001F8F0
0x14001fc44  mov     rax, [rbp+57h+var_90]
0x14001fc48  lea     rdx, [rbp+57h+Sid]; Src
0x14001fc4c  mov     r8d, [rbp+57h+SidAreaSize]; SidAreaSize
0x14001fc50  mov     ecx, esi; Count
0x14001fc52  mov     r9d, [rax]
0x14001fc55  lea     rax, [rbp+57h+SidAreaSize]
0x14001fc59  mov     [rsp+0D0h+RemainingSidAreaSize], rax; RemainingSidAreaSize
0x14001fc5e  lea     rax, [rbp+57h+Sid2]
0x14001fc62  mov     [rsp+0D0h+RemainingSidArea], rax; RemainingSidArea
0x14001fc67  mov     rax, [rbp+57h+Sid2]
0x14001fc6b  shl     r9, 4
0x14001fc6f  add     r9, [rbx+8]; Dest
0x14001fc73  mov     [rsp+0D0h+SidArea], rax; SidArea
  ... truncated ...
```
