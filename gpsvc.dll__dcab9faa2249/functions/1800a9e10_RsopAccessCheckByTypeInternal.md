# RsopAccessCheckByTypeInternal

- ea: `0x1800a9e10`
- end: `0x1800aa177`
- name: `RsopAccessCheckByTypeInternal`
- size: `871`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR pSecurityDescriptor@<rcx>, struct _OBJECT_TYPE_LIST *, unsigned int, PGENERIC_MAPPING GenericMapping, int, int, bool, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d000`
- `0x180095314`
- `0x1800aa180`

## callees

- `0x180072a08`
- `0x1800a7ef0`
- `0x1800a855c`
- `0x1800a8c8c`
- `0x1800a9810`
- `0x1800a99b8`
- `0x1800a9e10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9ee8`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800a9f1d`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800a9f1d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800a9ede`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800a9ede`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800a9e57`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800a9e57`

## string_xrefs

- `0x1800a9e39`: `RsopAccessCheckByTypeInternal - Entering.`
- `0x1800a9ea6`: `RsopAccessCheckByTypeInternal - Function invoked with invalid arguments.`
- `0x1800a9f6b`: `RsopAccessCheckByTypeInternal - Leaving.`
- `0x1800aa0b5`: `RsopAccessCheckByTypeInternal - Leaving.`
- `0x1800aa0f8`: `RsopAccessCheckByTypeInternal - Leaving.`
- `0x1800aa149`: `RsopAccessCheckByTypeInternal - Leaving.`
- `0x1800a9eee`: `RsopAccessCheckByTypeInternal - GetSecurityDescriptorDacl failed. GetLastError=0x%08X`
- `0x1800aa12f`: `RsopAccessCheckByTypeInternal - No DACL present. All access is granted.`
- `0x1800a9f5c`: `RsopAccessCheckByTypeInternal - The DACL is present but it is empty. All access is denied.`
- `0x1800a9f9d`: `RsopAccessCheckByTypeInternal - CAccumulatedPermissions failed to initialize.`
- `0x1800aa09d`: `RsopAccessCheckByTypeInternal - ProcessAce failed. Return code: 0x%08X`
- `0x1800aa078`: `RsopAccessCheckByTypeInternal - An ACE explicitly denies any of the requested access rights. Access is denied.`
- `0x1800aa063`: `RsopAccessCheckByTypeInternal - dwDesiredAccessMask != MAXIMUM_ALLOWED && dwAccumulatedPermissions == dwDesiredAccessMask. Access is granted.`

## pseudocode

```c
__int64 __fastcall RsopAccessCheckByTypeInternal(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        __int64 a2,
        _QWORD *a3,
        DWORD a4,
        struct _OBJECT_TYPE_LIST *a5,
        unsigned int a6,
        PGENERIC_MAPPING GenericMapping,
        int a8,
        int a9,
        DWORD *a10,
        _DWORD *a11)
{
  DWORD *v13; // rdi
  BOOL valid; // eax
  PGENERIC_MAPPING v15; // rbx
  unsigned int v16; // r15d
  _DWORD *v17; // rsi
  BOOL v18; // ecx
  int v19; // eax
  int v20; // ecx
  int v21; // eax
  unsigned int v22; // ebx
  DWORD LastError; // eax
  DWORD v24; // eax
  unsigned int AceCount; // r12d
  _QWORD *i; // rbx
  DWORD v28; // r11d
  struct _ACE_HEADER *v29; // r14
  int v30; // eax
  unsigned int AccumulatedPermissions; // eax
  unsigned int v32; // eax
  PACL pDacl; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v34[40]; // [rsp+48h] [rbp-28h] BYREF
  WINBOOL bDaclPresent; // [rsp+B0h] [rbp+40h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+C0h] [rbp+50h] BYREF
  DWORD AccessMask; // [rsp+C8h] [rbp+58h] BYREF

  AccessMask = a4;
  CDebugWrapper::Msg((CDebugWrapper *)dbgAccessCheck, 4u, L"RsopAccessCheckByTypeInternal - Entering.");
  v13 = a10;
  valid = IsValidSecurityDescriptor(pSecurityDescriptor);
  v15 = GenericMapping;
  v16 = 0;
  v17 = a11;
  v18 = pSecurityDescriptor == 0 || !valid;
  v19 = 0;
  if ( !a3 )
    v18 = 1;
  LOBYTE(v19) = GenericMapping == 0;
  v20 = v19 | v18;
  v21 = 0;
  if ( !v13 )
    v20 = 1;
  LOBYTE(v21) = a11 == 0;
  if ( v21 | v20 )
  {
    CDebugWrapper::Msg(
      (CDebugWrapper *)dbgAccessCheck,
      2u,
      L"RsopAccessCheckByTypeInternal - Function invoked with invalid arguments.");
    v22 = -2147024809;
LABEL_15:
    CDebugWrapper::Msg((CDebugWrapper *)dbgAccessCheck, 4u, L"RsopAccessCheckByTypeInternal - Leaving.");
    return v22;
  }
  bDaclPresent = 0;
  pDacl = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    LastError = GetLastError();
    CDebugWrapper::Msg(
      (CDebugWrapper *)dbgAccessCheck,
      2u,
      L"RsopAccessCheckByTypeInternal - GetSecurityDescriptorDacl failed. GetLastError=0x%08X",
      LastError);
    v22 = -2147467259;
    goto LABEL_15;
  }
  v24 = AccessMask;
  if ( AccessMask != 0x2000000 )
  {
    MapGenericMask(&AccessMask, v15);
    v24 = AccessMask;
  }
  if ( bDaclPresent && pDacl )
  {
    AceCount = pDacl->AceCount;
    if ( !pDacl->AceCount )
    {
      *v13 = 0;
      *v17 = 0;
      CDebugWrapper::Msg(
        (CDebugWrapper *)dbgAccessCheck,
        AceCount + 4,
        L"RsopAccessCheckByTypeInternal - The DACL is present but it is empty. All access is denied.");
      v22 = 0;
      goto LABEL_15;
    }
    CAccumulatedPermissions::CAccumulatedPermissions((CAccumulatedPermissions *)v34, a5, a6);
    if ( !v34[32] )
    {
      CDebugWrapper::Msg(
        (CDebugWrapper *)dbgAccessCheck,
        2u,
        L"RsopAccessCheckByTypeInternal - CAccumulatedPermissions failed to initialize.");
      v22 = -2147467259;
LABEL_33:
      CDebugWrapper::Msg((CDebugWrapper *)dbgAccessCheck, 4u, L"RsopAccessCheckByTypeInternal - Leaving.");
      CAccumulatedPermissions::~CAccumulatedPermissions((CAccumulatedPermissions *)v34);
      return v22;
    }
    *v13 = 0;
    *v17 = 0;
    for ( i = (_QWORD *)*a3; i; i = (_QWORD *)i[1] )
      LogSid(*(PSID *)(*i + 8LL));
    v28 = AccessMask;
    v29 = (struct _ACE_HEADER *)&pDacl[1];
    while ( v16 < AceCount )
    {
      LOBYTE(a10) = 0;
      v30 = ProcessAce(v29, a3, a5, a6, v28, (struct CAccumulatedPermissions *)v34, (bool *)&a10);
      v22 = v30;
      if ( v30 < 0 )
      {
        CDebugWrapper::Msg(
          (CDebugWrapper *)dbgAccessCheck,
          2u,
          L"RsopAccessCheckByTypeInternal - ProcessAce failed. Return code: 0x%08X",
          (unsigned int)v30);
        goto LABEL_33;
      }
      if ( (_BYTE)a10 )
      {
        *v13 = 0;
        *v17 = 0;
        CDebugWrapper::Msg(
          (CDebugWrapper *)dbgAccessCheck,
          4u,
          L"RsopAccessCheckByTypeInternal - An ACE explicitly denies any of the requested access rights. Access is denied.");
        goto LABEL_31;
      }
      v28 = AccessMask;
      if ( AccessMask != 0x2000000 )
      {
        AccumulatedPermissions = CAccumulatedPermissions::GetAccumulatedPermissions((CAccumulatedPermissions *)v34);
        if ( AccumulatedPermissions == v28 )
        {
          *v13 = v28;
          *v17 = 1;
          CDebugWrapper::Msg(
            (CDebugWrapper *)dbgAccessCheck,
            4u,
            L"RsopAccessCheckByTypeInternal - dwDesiredAccessMask != MAXIMUM_ALLOWED && dwAccumulatedPermissions == dwDesi"
             "redAccessMask. Access is granted.");
LABEL_31:
          v22 = 0;
          goto LABEL_33;
        }
      }
      v29 = (struct _ACE_HEADER *)((char *)v29 + v29->AceSize);
      ++v16;
    }
    if ( v28 == 0x2000000 )
    {
      v32 = CAccumulatedPermissions::GetAccumulatedPermissions((CAccumulatedPermissions *)v34);
      *v13 = v32;
      *v17 = v32 != 0;
    }
    CDebugWrapper::Msg((CDebugWrapper *)dbgAccessCheck, 4u, L"RsopAccessCheckByTypeInternal - Leaving.");
    CAccumulatedPermissions::~CAccumulatedPermissions((CAccumulatedPermissions *)v34);
  }
  else
  {
    if ( v24 == 0x2000000 )
      v24 = v15->GenericRead | v15->GenericWrite | v15->GenericExecute | v15->GenericAll;
    *v13 = v24;
    *v17 = 1;
    CDebugWrapper::Msg(
      (CDebugWrapper *)dbgAccessCheck,
      4u,
      L"RsopAccessCheckByTypeInternal - No DACL present. All access is granted.");
    CDebugWrapper::Msg((CDebugWrapper *)dbgAccessCheck, 4u, L"RsopAccessCheckByTypeInternal - Leaving.");
  }
  return 0;
}

```

## disassembly

```asm
0x1800a9e10  mov     [rsp-38h+arg_8], rbx
0x1800a9e15  mov     [rsp-38h+AccessMask], r9d
0x1800a9e1a  push    rbp
0x1800a9e1b  push    rsi
0x1800a9e1c  push    rdi
0x1800a9e1d  push    r12
0x1800a9e1f  push    r13
0x1800a9e21  push    r14
0x1800a9e23  push    r15
0x1800a9e25  mov     rbp, rsp
0x1800a9e28  sub     rsp, 70h
0x1800a9e2c  mov     r13, r8
0x1800a9e2f  lea     r12, ?dbgAccessCheck@@3VCDebugWrapper@@A; CDebugWrapper dbgAccessCheck
0x1800a9e36  mov     r14, rcx
0x1800a9e39  lea     r8, aRsopaccesschec_4; "RsopAccessCheckByTypeInternal - Enterin"...
0x1800a9e40  mov     rcx, r12; this
0x1800a9e43  mov     edx, 4; unsigned int
0x1800a9e48  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800a9e4d  mov     rdi, [rbp+arg_48]
0x1800a9e54  mov     rcx, r14; pSecurityDescriptor
0x1800a9e57  call    cs:__imp_IsValidSecurityDescriptor
0x1800a9e5d  mov     rbx, [rbp+GenericMapping]
0x1800a9e61  xor     r15d, r15d
0x1800a9e64  mov     rsi, [rbp+arg_50]
0x1800a9e6b  test    eax, eax
0x1800a9e6d  mov     eax, r15d
0x1800a9e70  mov     ecx, r15d
0x1800a9e73  setz    cl
0x1800a9e76  test    r14, r14
0x1800a9e79  lea     edx, [r15+1]
0x1800a9e7d  setz    al
0x1800a9e80  or      ecx, eax
0x1800a9e82  mov     eax, r15d
0x1800a9e85  test    r13, r13
0x1800a9e88  cmovz   ecx, edx
0x1800a9e8b  test    rbx, rbx
0x1800a9e8e  setz    al
0x1800a9e91  or      ecx, eax
0x1800a9e93  mov     eax, r15d
0x1800a9e96  test    rdi, rdi
0x1800a9e99  cmovz   ecx, edx
0x1800a9e9c  test    rsi, rsi
0x1800a9e9f  setz    al
0x1800a9ea2  or      ecx, eax
0x1800a9ea4  jz      short loc_1800A9EC3
0x1800a9ea6  lea     r8, aRsopaccesschec_6; "RsopAccessCheckByTypeInternal - Functio"...
0x1800a9ead  mov     rcx, r12; this
0x1800a9eb0  lea     edx, [r15+2]; unsigned int
0x1800a9eb4  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800a9eb9  mov     ebx, 80070057h
0x1800a9ebe  jmp     loc_1800A9F6B
0x1800a9ec3  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1800a9ec7  mov     [rbp+bDaclPresent], r15d
0x1800a9ecb  lea     r8, [rbp+pDacl]; pDacl
0x1800a9ecf  mov     [rbp+pDacl], r15
0x1800a9ed3  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800a9ed7  mov     [rbp+bDaclDefaulted], r15d
0x1800a9edb  mov     rcx, r14; pSecurityDescriptor
0x1800a9ede  call    cs:__imp_GetSecurityDescriptorDacl
0x1800a9ee4  test    eax, eax
0x1800a9ee6  jnz     short loc_1800A9F0C
0x1800a9ee8  call    cs:__imp_GetLastError
0x1800a9eee  lea     r8, aRsopaccesschec_3; "RsopAccessCheckByTypeInternal - GetSecu"...
0x1800a9ef5  mov     edx, 2; unsigned int
0x1800a9efa  mov     r9d, eax
0x1800a9efd  mov     rcx, r12; this
0x1800a9f00  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800a9f05  mov     ebx, 80004005h
0x1800a9f0a  jmp     short loc_1800A9F6B
0x1800a9f0c  mov     eax, [rbp+AccessMask]
0x1800a9f0f  cmp     eax, 2000000h
0x1800a9f14  jz      short loc_1800A9F26
0x1800a9f16  mov     rdx, rbx; GenericMapping
0x1800a9f19  lea     rcx, [rbp+AccessMask]; AccessMask
0x1800a9f1d  call    cs:__imp_MapGenericMask
0x1800a9f23  mov     eax, [rbp+AccessMask]
0x1800a9f26  cmp     [rbp+bDaclPresent], r15d
0x1800a9f2a  jz      loc_1800AA11B
0x1800a9f30  mov     rcx, [rbp+pDacl]
0x1800a9f34  test    rcx, rcx
0x1800a9f37  jz      loc_1800AA11B
0x1800a9f3d  movzx   r12d, word ptr [rcx+4]
0x1800a9f42  test    r12d, r12d
0x1800a9f45  jnz     short loc_1800A9F86
0x1800a9f47  lea     edx, [r12+4]; unsigned int
0x1800a9f4c  mov     [rdi], r15d
0x1800a9f4f  lea     r12, ?dbgAccessCheck@@3VCDebugWrapper@@A; CDebugWrapper dbgAccessCheck
0x1800a9f56  mov     [rsi], r15d
0x1800a9f59  mov     rcx, r12; this
0x1800a9f5c  lea     r8, aRsopaccesschec_2; "RsopAccessCheckByTypeInternal - The DAC"...
0x1800a9f63  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800a9f68  mov     ebx, r15d
0x1800a9f6b  lea     r8, aRsopaccesschec_1; "RsopAccessCheckByTypeInternal - Leaving"...
0x1800a9f72  mov     edx, 4; unsigned int
0x1800a9f77  mov     rcx, r12; this
0x1800a9f7a  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800a9f7f  mov     eax, ebx
0x1800a9f81  jmp     loc_1800AA15F
0x1800a9f86  mov     r8d, [rbp+arg_28]; unsigned int
0x1800a9f8a  lea     rcx, [rbp+var_28]; this
0x1800a9f8e  mov     rdx, [rbp+arg_20]; struct _OBJECT_TYPE_LIST *
0x1800a9f92  call    ??0CAccumulatedPermissions@@QEAA@PEAU_OBJECT_TYPE_LIST@@K@Z; CAccumulatedPermissions::CAccumulatedPermissions(_OBJECT_TYPE_LIST *,ulong)
0x1800a9f97  cmp     [rbp+var_8], r15b
0x1800a9f9b  jnz     short loc_1800A9FBF
0x1800a9f9d  lea     r8, aRsopaccesschec_5; "RsopAccessCheckByTypeInternal - CAccumu"...
0x1800a9fa4  mov     edx, 2; unsigned int
0x1800a9fa9  lea     rcx, ?dbgAccessCheck@@3VCDebugWrapper@@A; this
0x1800a9fb0  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800a9fb5  mov     ebx, 80004005h
0x1800a9fba  jmp     loc_1800AA0B5
0x1800a9fbf  mov     [rdi], r15d
0x1800a9fc2  mov     [rsi], r15d
0x1800a9fc5  mov     rbx, [r13+0]
0x1800a9fc9  jmp     short loc_1800A9FDB
0x1800a9fcb  mov     rcx, [rbx]
0x1800a9fce  mov     rcx, [rcx+8]; pSourceSid
0x1800a9fd2  call    ?LogSid@@YAXPEAX@Z; LogSid(void *)
0x1800a9fd7  mov     rbx, [rbx+8]
0x1800a9fdb  test    rbx, rbx
0x1800a9fde  jnz     short loc_1800A9FCB
0x1800a9fe0  mov     r14, [rbp+pDacl]
0x1800a9fe4  mov     r11d, [rbp+AccessMask]
0x1800a9fe8  add     r14, 8
0x1800a9fec  cmp     r15d, r12d
0x1800a9fef  jnb     loc_1800AA0DB
0x1800a9ff5  mov     r9d, [rbp+arg_28]; unsigned int
0x1800a9ff9  lea     rax, [rbp+arg_48]
0x1800aa000  mov     r8, [rbp+arg_20]; struct _OBJECT_TYPE_LIST *
0x1800aa004  mov     rdx, r13; void *
0x1800aa007  mov     [rsp+70h+var_40], rax; bool *
0x1800aa00c  mov     rcx, r14; struct _ACE_HEADER *
0x1800aa00f  lea     rax, [rbp+var_28]
0x1800aa013  mov     byte ptr [rbp+arg_48], 0
0x1800aa01a  mov     [rsp+70h+var_48], rax; struct CAccumulatedPermissions *
0x1800aa01f  mov     [rsp+70h+var_50], r11d; unsigned int
0x1800aa024  call    ?ProcessAce@@YAJPEAU_ACE_HEADER@@PEAXPEAU_OBJECT_TYPE_LIST@@KKAEAVCAccumulatedPermissions@@PEA_N@Z; ProcessAce(_ACE_HEADER *,void *,_OBJECT_TYPE_LIST *,ulong,ulong,CAccumulatedPermissions &,bool *)
0x1800aa029  mov     ebx, eax
0x1800aa02b  test    eax, eax
0x1800aa02d  js      short loc_1800AA09A
0x1800aa02f  cmp     byte ptr [rbp+arg_48], 0
0x1800aa036  jnz     short loc_1800AA072
0x1800aa038  mov     r11d, [rbp+AccessMask]
0x1800aa03c  cmp     r11d, 2000000h
0x1800aa043  jz      short loc_1800AA053
0x1800aa045  lea     rcx, [rbp+var_28]; this
0x1800aa049  call    ?GetAccumulatedPermissions@CAccumulatedPermissions@@QEAAKXZ; CAccumulatedPermissions::GetAccumulatedPermissions(void)
0x1800aa04e  cmp     eax, r11d
0x1800aa051  jz      short loc_1800AA060
0x1800aa053  movzx   eax, word ptr [r14+2]
0x1800aa058  add     r14, rax
0x1800aa05b  inc     r15d
0x1800aa05e  jmp     short loc_1800A9FEC
0x1800aa060  mov     [rdi], r11d
0x1800aa063  lea     r8, aRsopaccesschec_9; "RsopAccessCheckByTypeInternal - dwDesir"...
0x1800aa06a  mov     dword ptr [rsi], 1
0x1800aa070  jmp     short loc_1800AA085
0x1800aa072  mov     dword ptr [rdi], 0
0x1800aa078  lea     r8, aRsopaccesschec_0; "RsopAccessCheckByTypeInternal - An ACE "...
0x1800aa07f  mov     dword ptr [rsi], 0
0x1800aa085  mov     edx, 4; unsigned int
0x1800aa08a  lea     rcx, ?dbgAccessCheck@@3VCDebugWrapper@@A; this
0x1800aa091  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800aa096  xor     ebx, ebx
0x1800aa098  jmp     short loc_1800AA0B5
0x1800aa09a  mov     r9d, eax
0x1800aa09d  lea     r8, aRsopaccesschec_7; "RsopAccessCheckByTypeInternal - Process"...
0x1800aa0a4  mov     edx, 2; unsigned int
0x1800aa0a9  lea     rcx, ?dbgAccessCheck@@3VCDebugWrapper@@A; this
0x1800aa0b0  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800aa0b5  lea     r8, aRsopaccesschec_1; "RsopAccessCheckByTypeInternal - Leaving"...
0x1800aa0bc  mov     edx, 4; unsigned int
0x1800aa0c1  lea     rcx, ?dbgAccessCheck@@3VCDebugWrapper@@A; this
0x1800aa0c8  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800aa0cd  lea     rcx, [rbp+var_28]; this
0x1800aa0d1  call    ??1CAccumulatedPermissions@@QEAA@XZ; CAccumulatedPermissions::~CAccumulatedPermissions(void)
0x1800aa0d6  jmp     loc_1800A9F7F
0x1800aa0db  cmp     r11d, 2000000h
0x1800aa0e2  jnz     short loc_1800AA0F8
0x1800aa0e4  lea     rcx, [rbp+var_28]; this
0x1800aa0e8  call    ?GetAccumulatedPermissions@CAccumulatedPermissions@@QEAAKXZ; CAccumulatedPermissions::GetAccumulatedPermissions(void)
0x1800aa0ed  xor     ecx, ecx
0x1800aa0ef  mov     [rdi], eax
0x1800aa0f1  test    eax, eax
0x1800aa0f3  setnz   cl
0x1800aa0f6  mov     [rsi], ecx
0x1800aa0f8  lea     r8, aRsopaccesschec_1; "RsopAccessCheckByTypeInternal - Leaving"...
0x1800aa0ff  mov     edx, 4; unsigned int
0x1800aa104  lea     rcx, ?dbgAccessCheck@@3VCDebugWrapper@@A; this
0x1800aa10b  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800aa110  lea     rcx, [rbp+var_28]; this
0x1800aa114  call    ??1CAccumulatedPermissions@@QEAA@XZ; CAccumulatedPermissions::~CAccumulatedPermissions(void)
0x1800aa119  jmp     short loc_1800AA15D
0x1800aa11b  cmp     eax, 2000000h
0x1800aa120  jnz     short loc_1800AA12D
0x1800aa122  mov     eax, [rbx+0Ch]
0x1800aa125  or      eax, [rbx+8]
0x1800aa128  or      eax, [rbx+4]
0x1800aa12b  or      eax, [rbx]
0x1800aa12d  mov     [rdi], eax
0x1800aa12f  lea     r8, aRsopaccesschec_8; "RsopAccessCheckByTypeInternal - No DACL"...
0x1800aa136  mov     edx, 4; unsigned int
0x1800aa13b  mov     dword ptr [rsi], 1
0x1800aa141  mov     rcx, r12; this
0x1800aa144  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800aa149  lea     r8, aRsopaccesschec_1; "RsopAccessCheckByTypeInternal - Leaving"...
0x1800aa150  mov     edx, 4; unsigned int
0x1800aa155  mov     rcx, r12; this
0x1800aa158  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800aa15d  xor     eax, eax
0x1800aa15f  mov     rbx, [rsp+70h+arg_8]
0x1800aa167  add     rsp, 70h
0x1800aa16b  pop     r15
0x1800aa16d  pop     r14
0x1800aa16f  pop     r13
0x1800aa171  pop     r12
0x1800aa173  pop     rdi
0x1800aa174  pop     rsi
0x1800aa175  pop     rbp
0x1800aa176  retn
```
