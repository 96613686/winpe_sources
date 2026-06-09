# CscDclMrxUpdateSuspendedItem

- ea: `0x14004e438`
- end: `0x14004e954`
- name: `CscDclMrxUpdateSuspendedItem`
- size: `1308`
- prototype: `__int64 __fastcall(_QWORD *, char, char, void *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14007ae70`

## callees

- `0x14000eef0`
- `0x14000f8b0`
- `0x14001404c`
- `0x1400169d4`
- `0x1400190ec`
- `0x140019788`
- `0x14001d200`
- `0x14002384c`
- `0x14002f010`
- `0x14002f440`
- `0x14004e438`
- `0x140086870`
- `0x140086dd8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14004e8d7`
- `ntoskrnl!ObfDereferenceObject` at `0x14004e8d7`
- `ntoskrnl!SeQueryInformationToken` at `0x14004e5ed`
- `ntoskrnl!SeQueryInformationToken` at `0x14004e5ed`
- `ntoskrnl!IoFileObjectType` at `0x14004e712`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004e72f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004e72f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14004e58b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14004e5ca`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14004e600`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14004e58b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14004e5ca`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14004e600`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e8ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e8ef`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14004e564`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14004e564`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004e84e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004e84e`
- `rdbss!RxDoesRedirSupportLogicalViews` at `0x14004e7a8`
- `rdbss!RxDoesRedirSupportLogicalViews` at `0x14004e7a8`
- `MUP!MupSurrogateGetFileName` at `0x14004e7e8`
- `MUP!MupSurrogateGetFileName` at `0x14004e812`
- `MUP!MupSurrogateGetFileName` at `0x14004e7e8`
- `MUP!MupSurrogateGetFileName` at `0x14004e812`

## pseudocode

```c
__int64 __fastcall CscDclMrxUpdateSuspendedItem(_QWORD *a1, char a2, char a3, void *a4, __int64 a5)
{
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 v11; // r13
  __int64 v12; // rdx
  NTSTATUS StoreEntry; // ebx
  int v14; // edi
  PACCESS_TOKEN PrimaryToken; // rdi
  __int64 v16; // r15
  NTSTATUS updated; // eax
  int v18; // r8d
  __int64 v19; // rbx
  __int64 v20; // rsi
  int v21; // edx
  PVOID Object; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  PVOID TokenInformation; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+88h] [rbp-78h]
  UNICODE_STRING String2; // [rsp+90h] [rbp-70h] BYREF
  UNICODE_STRING String1; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v32[20]; // [rsp+B0h] [rbp-50h] BYREF

  v29 = a5;
  v25 = 0;
  v27 = 0;
  memset(v32, 0, sizeof(v32));
  v8 = CscFcbContext(a1[7]);
  v9 = a1[8];
  Object = 0;
  v10 = v8;
  v11 = *(_QWORD *)(v9 + 32);
  TokenInformation = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  String1 = 0;
  String2 = 0;
  StoreEntry = CscDclMRx_GetStoreEntry(&v25, v11);
  if ( StoreEntry < 0 )
  {
    v14 = 5496;
    goto LABEL_54;
  }
  if ( (*(_DWORD *)(v10 + 4) & 0x1001) == 0 )
  {
    v14 = 5501;
LABEL_53:
    StoreEntry = -1073741811;
    goto LABEL_54;
  }
  LOBYTE(v12) = 1;
  if ( !(unsigned __int8)_CscObtainFcbMostlyExclusive(a1, v12) && *(_WORD *)a1[7] != 0xEC21 )
  {
    StoreEntry = -1073741757;
    v14 = 5508;
    goto LABEL_54;
  }
  StoreEntry = CscDclMRx_GetStoreOpenHandle(&v27, *(_QWORD *)(a1[8] + 32LL));
  if ( StoreEntry < 0 )
  {
    v14 = 5518;
    goto LABEL_54;
  }
  SeCaptureSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  if ( !PrimaryToken )
  {
    SeReleaseSubjectContext(&SubjectContext);
    v14 = 5534;
    goto LABEL_54;
  }
  if ( (unsigned __int8)CscCheckTokenMembership(&SubjectContext, *(PSECURITY_DESCRIPTOR *)(CscDevExtn + 1416)) )
  {
    StoreEntry = -1073741790;
    SeReleaseSubjectContext(&SubjectContext);
    v14 = 5553;
    goto LABEL_54;
  }
  StoreEntry = SeQueryInformationToken(PrimaryToken, TokenUser, &TokenInformation);
  SeReleaseSubjectContext(&SubjectContext);
  if ( StoreEntry < 0 )
  {
    v14 = 5562;
    goto LABEL_54;
  }
  v14 = 0;
  v16 = *(_QWORD *)TokenInformation;
  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids);
    updated = CscStoreSetExplicitAccessEntry(v25, 0, v16, 0, 1);
LABEL_23:
    StoreEntry = updated;
    goto LABEL_54;
  }
  StoreEntry = CscStoreQueryInformationEntryEx(v25, 0, (unsigned int)v32, 0, 0, 0, 0);
  if ( StoreEntry < 0 )
  {
    v14 = 5584;
    goto LABEL_54;
  }
  if ( (v32[0] & 0x80417) == 0 || (v18 = *(_DWORD *)(v11 + 152), (v18 & 2) != 0) )
  {
    StoreEntry = ObReferenceObjectByHandle(a4, 0, (POBJECT_TYPE)IoFileObjectType, *(_BYTE *)(a1[5] + 64LL), &Object, 0);
    if ( StoreEntry < 0 )
    {
      v14 = 5619;
      goto LABEL_54;
    }
    v19 = *((_QWORD *)Object + 3);
    if ( !v19
      || (v20 = *((_QWORD *)Object + 4)) == 0
      || (*(_WORD *)v19 & 0xFFF0) != 0xEC20
      || *(_WORD *)v20 != 0xEC30
      || *(_QWORD *)(v19 + 128)
      || !(unsigned __int8)RxDoesRedirSupportLogicalViews(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v19 + 120) + 32LL) + 48LL))
      || CscDeviceObject == *(PDEVICE_OBJECT *)(*(_QWORD *)(*(_QWORD *)(v19 + 120) + 32LL) + 48LL) )
    {
      v14 = 5635;
      goto LABEL_53;
    }
    StoreEntry = MupSurrogateGetFileName(Object, 3, 0, &String1);
    if ( StoreEntry < 0 )
    {
      v14 = 5647;
      goto LABEL_54;
    }
    StoreEntry = MupSurrogateGetFileName(*(_QWORD *)(v20 + 48), 3, 0, &String2);
    if ( StoreEntry < 0 )
    {
      v14 = 5653;
      goto LABEL_54;
    }
    if ( !RtlEqualUnicodeString(
            &String1,
            &String2,
            (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1[7] + 120LL) + 32LL) + 96LL) & 8) != 0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids);
      v14 = 5662;
      goto LABEL_53;
    }
    LOBYTE(v21) = a3;
    updated = CscStoreUpdateSuspendedEntry(v27, v21, v29, v16, *(_DWORD *)(*(_QWORD *)(v20 + 32) + 152LL));
    goto LABEL_23;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 105, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids, 2, v18);
  StoreEntry = -1073741790;
  v14 = 5599;
LABEL_54:
  if ( Object )
    ObfDereferenceObject(Object);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      107,
      WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
      (unsigned int)StoreEntry,
      v14);
  return (unsigned int)StoreEntry;
}

```

## disassembly

```asm
0x14004e438  mov     [rsp-8+arg_8], rbx
0x14004e43d  push    rbp
0x14004e43e  push    rsi
0x14004e43f  push    rdi
0x14004e440  push    r12
0x14004e442  push    r13
0x14004e444  push    r14
0x14004e446  push    r15
0x14004e448  lea     rbp, [rsp-10h]
0x14004e44d  sub     rsp, 110h
0x14004e454  mov     rax, cs:__security_cookie
0x14004e45b  xor     rax, rsp
0x14004e45e  mov     [rbp+40h+var_40], rax
0x14004e462  mov     rax, [rbp+40h+arg_20]
0x14004e466  mov     sil, dl
0x14004e469  xor     edx, edx; Val
0x14004e46b  mov     [rsp+140h+var_100], r8b
0x14004e470  mov     r14, rcx
0x14004e473  mov     [rbp+40h+var_B8], rax
0x14004e477  lea     rcx, [rbp+40h+var_90]; void *
0x14004e47b  mov     [rsp+140h+var_F0], 0
0x14004e484  mov     r12, r9
0x14004e487  mov     [rsp+140h+var_E0], 0
0x14004e490  lea     r8d, [rdx+50h]; Size
0x14004e494  call    memset
0x14004e499  mov     rcx, [r14+38h]
0x14004e49d  call    CscFcbContext
0x14004e4a2  mov     rcx, [r14+40h]
0x14004e4a6  xorps   xmm0, xmm0
0x14004e4a9  mov     [rsp+140h+var_F8], 0
0x14004e4b2  xorps   xmm1, xmm1
0x14004e4b5  mov     rdi, rax
0x14004e4b8  mov     r13, [rcx+20h]
0x14004e4bc  lea     rcx, [rsp+140h+var_F0]
0x14004e4c1  mov     rdx, r13
0x14004e4c4  mov     [rsp+140h+TokenInformation], 0
0x14004e4cd  movups  xmmword ptr [rsp+140h+SubjectContext.ClientToken], xmm0
0x14004e4d2  movups  xmmword ptr [rsp+140h+SubjectContext.PrimaryToken], xmm0
0x14004e4d7  movups  xmmword ptr [rbp+40h+String1.Length], xmm0
0x14004e4db  movups  xmmword ptr [rbp+40h+String2.Length], xmm1
0x14004e4df  call    CscDclMRx_GetStoreEntry
0x14004e4e4  lea     r15, WPP_GLOBAL_Control
0x14004e4eb  mov     ebx, eax
0x14004e4ed  test    eax, eax
0x14004e4ef  jns     short loc_14004E4FB
0x14004e4f1  mov     edi, 1578h
0x14004e4f6  jmp     loc_14004E8CD
0x14004e4fb  test    dword ptr [rdi+4], 1001h
0x14004e502  jnz     short loc_14004E50E
0x14004e504  mov     edi, 157Dh
0x14004e509  jmp     loc_14004E8C8
0x14004e50e  mov     r8b, 1
0x14004e511  mov     rcx, r14
0x14004e514  mov     dl, r8b
0x14004e517  call    __CscObtainFcbMostlyExclusive
0x14004e51c  test    al, al
0x14004e51e  jnz     short loc_14004E53D
0x14004e520  mov     rax, [r14+38h]
0x14004e524  mov     ecx, 0EC21h
0x14004e529  cmp     cx, [rax]
0x14004e52c  jz      short loc_14004E53D
0x14004e52e  mov     ebx, 0C0000043h
0x14004e533  mov     edi, 1584h
0x14004e538  jmp     loc_14004E8CD
0x14004e53d  mov     rdx, [r14+40h]
0x14004e541  lea     rcx, [rsp+140h+var_E0]
0x14004e546  mov     rdx, [rdx+20h]
0x14004e54a  call    CscDclMRx_GetStoreOpenHandle
0x14004e54f  mov     ebx, eax
0x14004e551  test    eax, eax
0x14004e553  jns     short loc_14004E55F
0x14004e555  mov     edi, 158Eh
0x14004e55a  jmp     loc_14004E8CD
0x14004e55f  lea     rcx, [rsp+140h+SubjectContext]; SubjectContext
0x14004e564  call    cs:__imp_SeCaptureSubjectContext
0x14004e56b  nop     dword ptr [rax+rax+00h]
0x14004e570  mov     rax, [rsp+140h+SubjectContext.ClientToken]
0x14004e575  lea     rcx, [rsp+140h+SubjectContext]; SubjectSecurityContext
0x14004e57a  mov     rdi, [rsp+140h+SubjectContext.PrimaryToken]
0x14004e57f  test    rax, rax
0x14004e582  cmovnz  rdi, rax
0x14004e586  test    rdi, rdi
0x14004e589  jnz     short loc_14004E5A1
0x14004e58b  call    cs:__imp_SeReleaseSubjectContext
0x14004e592  nop     dword ptr [rax+rax+00h]
0x14004e597  mov     edi, 159Eh
0x14004e59c  jmp     loc_14004E8CD
0x14004e5a1  mov     r8, [r14+28h]
0x14004e5a5  mov     rdx, cs:CscDevExtn
0x14004e5ac  mov     r8b, [r8+40h]
0x14004e5b0  mov     rdx, [rdx+588h]; SecurityDescriptor
0x14004e5b7  call    CscCheckTokenMembership
0x14004e5bc  test    al, al
0x14004e5be  jz      short loc_14004E5E0
0x14004e5c0  lea     rcx, [rsp+140h+SubjectContext]; SubjectContext
0x14004e5c5  mov     ebx, 0C0000022h
0x14004e5ca  call    cs:__imp_SeReleaseSubjectContext
0x14004e5d1  nop     dword ptr [rax+rax+00h]
0x14004e5d6  mov     edi, 15B1h
0x14004e5db  jmp     loc_14004E8CD
0x14004e5e0  lea     r8, [rsp+140h+TokenInformation]; TokenInformation
0x14004e5e5  mov     edx, 1; TokenInformationClass
0x14004e5ea  mov     rcx, rdi; Token
0x14004e5ed  call    cs:__imp_SeQueryInformationToken
0x14004e5f4  nop     dword ptr [rax+rax+00h]
0x14004e5f9  lea     rcx, [rsp+140h+SubjectContext]; SubjectContext
0x14004e5fe  mov     ebx, eax
0x14004e600  call    cs:__imp_SeReleaseSubjectContext
0x14004e607  nop     dword ptr [rax+rax+00h]
0x14004e60c  test    ebx, ebx
0x14004e60e  jns     short loc_14004E61A
0x14004e610  mov     edi, 15BAh
0x14004e615  jmp     loc_14004E8CD
0x14004e61a  mov     rax, [rsp+140h+TokenInformation]
0x14004e61f  xor     edi, edi
0x14004e621  mov     r15, [rax]
0x14004e624  test    sil, sil
0x14004e627  jz      short loc_14004E67B
0x14004e629  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e630  lea     rax, WPP_GLOBAL_Control
0x14004e637  cmp     rcx, rax
0x14004e63a  jz      short loc_14004E656
0x14004e63c  mov     eax, [rcx+2Ch]
0x14004e63f  test    al, 40h
0x14004e641  jz      short loc_14004E656
0x14004e643  mov     rcx, [rcx+18h]
0x14004e647  lea     edx, [rdi+68h]
0x14004e64a  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x14004e651  call    WPP_SF_
0x14004e656  mov     rcx, [rsp+140h+var_F0]
0x14004e65b  xor     r9d, r9d
0x14004e65e  mov     r8, r15
0x14004e661  mov     byte ptr [rsp+140h+Object], 1
0x14004e666  xor     edx, edx
0x14004e668  call    CscStoreSetExplicitAccessEntry
0x14004e66d  mov     ebx, eax
0x14004e66f  lea     r15, WPP_GLOBAL_Control
0x14004e676  jmp     loc_14004E8CD
0x14004e67b  mov     rcx, [rsp+140h+var_F0]
0x14004e680  lea     r8, [rbp+40h+var_90]
0x14004e684  xor     esi, esi
0x14004e686  xor     r9d, r9d
0x14004e689  mov     [rsp+140h+var_110], rsi
0x14004e68e  xor     edx, edx
0x14004e690  mov     [rsp+140h+HandleInformation], rsi
0x14004e695  mov     [rsp+140h+Object], rsi
0x14004e69a  call    CscStoreQueryInformationEntryEx
0x14004e69f  mov     ebx, eax
0x14004e6a1  test    eax, eax
0x14004e6a3  jns     short loc_14004E6AC
0x14004e6a5  mov     edi, 15D0h
0x14004e6aa  jmp     short loc_14004E66F
0x14004e6ac  test    [rbp+40h+var_90], 80417h
0x14004e6b3  jz      short loc_14004E709
0x14004e6b5  mov     r8d, [r13+98h]
0x14004e6bc  mov     r9d, 2
0x14004e6c2  test    r9b, r8b
0x14004e6c5  jnz     short loc_14004E709
0x14004e6c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e6ce  lea     r15, WPP_GLOBAL_Control
0x14004e6d5  cmp     rcx, r15
0x14004e6d8  jz      short loc_14004E6FA
0x14004e6da  mov     eax, [rcx+2Ch]
0x14004e6dd  test    al, 40h
0x14004e6df  jz      short loc_14004E6FA
0x14004e6e1  mov     rcx, [rcx+18h]
0x14004e6e5  lea     edx, [r9+67h]
0x14004e6e9  mov     dword ptr [rsp+140h+Object], r8d
0x14004e6ee  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x14004e6f5  call    WPP_SF_Dd
0x14004e6fa  mov     ebx, 0C0000022h
0x14004e6ff  mov     edi, 15DFh
0x14004e704  jmp     loc_14004E8CD
0x14004e709  mov     r9, [r14+28h]
0x14004e70d  lea     rax, [rsp+140h+var_F8]
0x14004e712  mov     r8, cs:__imp_IoFileObjectType
0x14004e719  xor     edx, edx; DesiredAccess
0x14004e71b  mov     [rsp+140h+HandleInformation], rsi; HandleInformation
0x14004e720  mov     rcx, r12; Handle
0x14004e723  mov     [rsp+140h+Object], rax; Object
0x14004e728  mov     r9b, [r9+40h]; AccessMode
0x14004e72c  mov     r8, [r8]; ObjectType
0x14004e72f  call    cs:__imp_ObReferenceObjectByHandle
0x14004e736  nop     dword ptr [rax+rax+00h]
0x14004e73b  mov     ebx, eax
0x14004e73d  test    eax, eax
0x14004e73f  jns     short loc_14004E74B
0x14004e741  mov     edi, 15F3h
0x14004e746  jmp     loc_14004E66F
0x14004e74b  mov     rcx, [rsp+140h+var_F8]
0x14004e750  mov     rbx, [rcx+18h]
0x14004e754  test    rbx, rbx
0x14004e757  jz      loc_14004E8BC
0x14004e75d  mov     rsi, [rcx+20h]
0x14004e761  test    rsi, rsi
0x14004e764  jz      loc_14004E8BC
0x14004e76a  movzx   eax, word ptr [rbx]
0x14004e76d  mov     ecx, 0FFF0h
0x14004e772  and     ax, cx
0x14004e775  mov     ecx, 0EC20h
0x14004e77a  cmp     ax, cx
0x14004e77d  jnz     loc_14004E8BC
0x14004e783  lea     eax, [rcx+10h]
0x14004e786  cmp     ax, [rsi]
0x14004e789  jnz     loc_14004E8BC
0x14004e78f  cmp     [rbx+80h], rdi
0x14004e796  jnz     loc_14004E8BC
0x14004e79c  mov     rax, [rbx+78h]
0x14004e7a0  mov     rcx, [rax+20h]
0x14004e7a4  mov     rcx, [rcx+30h]
0x14004e7a8  call    cs:__imp_RxDoesRedirSupportLogicalViews
0x14004e7af  nop     dword ptr [rax+rax+00h]
0x14004e7b4  test    al, al
0x14004e7b6  jz      loc_14004E8BC
0x14004e7bc  mov     rax, [rbx+78h]
0x14004e7c0  mov     rcx, [rax+20h]
0x14004e7c4  mov     rax, [rcx+30h]
0x14004e7c8  cmp     cs:CscDeviceObject, rax
0x14004e7cf  jz      loc_14004E8BC
0x14004e7d5  mov     rcx, [rsp+140h+var_F8]
0x14004e7da  lea     r9, [rbp+40h+String1]
0x14004e7de  xor     r8d, r8d
0x14004e7e1  lea     r12d, [r8+3]
0x14004e7e5  mov     edx, r12d
0x14004e7e8  call    cs:__imp_MupSurrogateGetFileName
0x14004e7ef  nop     dword ptr [rax+rax+00h]
0x14004e7f4  mov     ebx, eax
0x14004e7f6  test    eax, eax
0x14004e7f8  jns     short loc_14004E804
0x14004e7fa  mov     edi, 160Fh
0x14004e7ff  jmp     loc_14004E66F
0x14004e804  mov     rcx, [rsi+30h]
0x14004e808  lea     r9, [rbp+40h+String2]
0x14004e80c  xor     r8d, r8d
0x14004e80f  mov     edx, r12d
0x14004e812  call    cs:__imp_MupSurrogateGetFileName
0x14004e819  nop     dword ptr [rax+rax+00h]
0x14004e81e  mov     ebx, eax
0x14004e820  test    eax, eax
0x14004e822  jns     short loc_14004E82E
0x14004e824  mov     edi, 1615h
0x14004e829  jmp     loc_14004E66F
0x14004e82e  mov     rax, [r14+38h]
0x14004e832  lea     rdx, [rbp+40h+String2]; String2
0x14004e836  mov     rcx, [rax+78h]
0x14004e83a  mov     rax, [rcx+20h]
0x14004e83e  lea     rcx, [rbp+40h+String1]; String1
0x14004e842  mov     r8d, [rax+60h]
0x14004e846  shr     r8d, 3
0x14004e84a  and     r8b, 1; CaseInSensitive
0x14004e84e  call    cs:__imp_RtlEqualUnicodeString
0x14004e855  nop     dword ptr [rax+rax+00h]
0x14004e85a  test    al, al
0x14004e85c  jnz     short loc_14004E894
0x14004e85e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e865  lea     r15, WPP_GLOBAL_Control
0x14004e86c  cmp     rcx, r15
0x14004e86f  jz      short loc_14004E88D
0x14004e871  mov     eax, [rcx+2Ch]
0x14004e874  test    al, 40h
0x14004e876  jz      short loc_14004E88D
0x14004e878  mov     rcx, [rcx+18h]
0x14004e87c  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x14004e883  mov     edx, 6Ah ; 'j'
0x14004e888  call    WPP_SF_
0x14004e88d  mov     edi, 161Eh
0x14004e892  jmp     short loc_14004E8C8
0x14004e894  mov     rax, [rsi+20h]
0x14004e898  mov     r9, r15
0x14004e89b  mov     r8, [rbp+40h+var_B8]
0x14004e89f  mov     dl, [rsp+140h+var_100]
0x14004e8a3  mov     ecx, [rax+98h]
0x14004e8a9  mov     dword ptr [rsp+140h+Object], ecx
0x14004e8ad  mov     rcx, [rsp+140h+var_E0]
0x14004e8b2  call    CscStoreUpdateSuspendedEntry
0x14004e8b7  jmp     loc_14004E66D
0x14004e8bc  mov     edi, 1603h
0x14004e8c1  lea     r15, WPP_GLOBAL_Control
0x14004e8c8  mov     ebx, 0C000000Dh
0x14004e8cd  mov     rcx, [rsp+140h+var_F8]; Object
0x14004e8d2  test    rcx, rcx
0x14004e8d5  jz      short loc_14004E8E3
0x14004e8d7  call    cs:__imp_ObfDereferenceObject
0x14004e8de  nop     dword ptr [rax+rax+00h]
0x14004e8e3  mov     rcx, [rsp+140h+TokenInformation]; P
0x14004e8e8  test    rcx, rcx
0x14004e8eb  jz      short loc_14004E8FB
0x14004e8ed  xor     edx, edx; Tag
0x14004e8ef  call    cs:__imp_ExFreePoolWithTag
0x14004e8f6  nop     dword ptr [rax+rax+00h]
0x14004e8fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e902  cmp     rcx, r15
0x14004e905  jz      short loc_14004E92A
0x14004e907  mov     eax, [rcx+2Ch]
0x14004e90a  test    al, 40h
0x14004e90c  jz      short loc_14004E92A
0x14004e90e  mov     rcx, [rcx+18h]
0x14004e912  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x14004e919  mov     edx, 6Bh ; 'k'
0x14004e91e  mov     dword ptr [rsp+140h+Object], edi
  ... truncated ...
```
