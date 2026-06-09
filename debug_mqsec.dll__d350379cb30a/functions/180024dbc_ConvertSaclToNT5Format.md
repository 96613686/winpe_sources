# _ConvertSaclToNT5Format

- ea: `0x180024dbc`
- end: `0x180025356`
- name: `_ConvertSaclToNT5Format`
- size: `1434`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x180023310`

## callees

- `0x1800049ac`
- `0x1800136f0`
- `0x18001722c`
- `0x180021b30`
- `0x180021b5c`
- `0x180021c24`
- `0x180024344`
- `0x180024dbc`
- `0x18002535c`
- `0x1800253b8`
- `0x18002f0a2`

## import_xrefs

- `msvcrt!free` at `0x180024ea6`
- `msvcrt!free` at `0x1800250f3`
- `msvcrt!free` at `0x18002515e`
- `msvcrt!free` at `0x1800251c3`
- `msvcrt!free` at `0x180025228`
- `msvcrt!free` at `0x180025279`
- `msvcrt!free` at `0x1800252cd`
- `msvcrt!free` at `0x18002532f`
- `msvcrt!free` at `0x180024ea6`
- `msvcrt!free` at `0x1800250f3`
- `msvcrt!free` at `0x18002515e`
- `msvcrt!free` at `0x1800251c3`
- `msvcrt!free` at `0x180025228`
- `msvcrt!free` at `0x180025279`
- `msvcrt!free` at `0x1800252cd`
- `msvcrt!free` at `0x18002532f`
- `ADVAPI32!AddAuditAccessAce` at `0x180024ff9`
- `ADVAPI32!AddAuditAccessAce` at `0x180025040`
- `ADVAPI32!AddAuditAccessAce` at `0x180024ff9`
- `ADVAPI32!AddAuditAccessAce` at `0x180025040`
- `ADVAPI32!EqualSid` at `0x180024f95`
- `ADVAPI32!EqualSid` at `0x180024f95`
- `ADVAPI32!GetAce` at `0x180024f12`
- `ADVAPI32!GetAce` at `0x180024f7b`
- `ADVAPI32!GetAce` at `0x180024f12`
- `ADVAPI32!GetAce` at `0x180024f7b`
- `ADVAPI32!InitializeAcl` at `0x180024e4a`
- `ADVAPI32!InitializeAcl` at `0x180024e4a`
- `KERNEL32!GetLastError` at `0x180024e54`
- `KERNEL32!GetLastError` at `0x180025124`
- `KERNEL32!GetLastError` at `0x18002516a`
- `KERNEL32!GetLastError` at `0x1800251cf`
- `KERNEL32!GetLastError` at `0x1800252f5`
- `KERNEL32!GetLastError` at `0x180024e54`
- `KERNEL32!GetLastError` at `0x180025124`
- `KERNEL32!GetLastError` at `0x18002516a`
- `KERNEL32!GetLastError` at `0x1800251cf`
- `KERNEL32!GetLastError` at `0x1800252f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ConvertSaclToNT5Format(unsigned int a1, struct _ACL *a2, DWORD *a3, PACL *a4, _DWORD *a5)
{
  struct _ACL *v7; // r14
  bool v8; // zf
  DWORD AclSize; // eax
  struct _ACL *v10; // rax
  struct _ACL *v12; // rbx
  signed int LastError; // esi
  unsigned __int64 AceCount; // rdi
  struct _SID **v15; // rsi
  DWORD v16; // r15d
  PACL *v17; // r12
  __int64 v18; // rdx
  unsigned int v19; // r14d
  unsigned int v20; // esi
  DWORD i; // r12d
  unsigned int v22; // r10d
  DWORD v23; // eax
  PACL *v24; // r12
  DWORD v25; // eax
  int v26; // r12d
  DWORD v27; // eax
  DWORD v28; // eax
  unsigned int v29; // [rsp+40h] [rbp-40h] BYREF
  LPVOID pAce; // [rsp+48h] [rbp-38h] BYREF
  PSID pSid1; // [rsp+50h] [rbp-30h]
  struct _SID **v32; // [rsp+58h] [rbp-28h]
  struct _ACL *v33; // [rsp+60h] [rbp-20h]
  _BYTE v34[24]; // [rsp+68h] [rbp-18h] BYREF
  DWORD v38; // [rsp+E0h] [rbp+60h]

  v7 = a2;
  v8 = a2->AclRevision == 4;
  *a5 = v8;
  if ( v8 )
  {
    AclSize = a2->AclSize;
    *a3 = AclSize;
    v10 = (struct _ACL *)MmAllocate(AclSize);
    *a4 = v10;
    memcpy_0(v10, v7, *a3);
    return 0;
  }
  *a3 = 65520;
  v12 = (struct _ACL *)MmAllocate(0xFFF0u);
  v33 = v12;
  *a4 = v12;
  if ( !InitializeAcl(v12, *a3, 4u) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        20,
        &WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    free(v12);
    return (unsigned int)LastError;
  }
  AceCount = v7->AceCount;
  v38 = v7->AceCount;
  v15 = (struct _SID **)MmAllocate(saturated_mul(AceCount, 8u));
  v32 = v15;
  aPtrs<_SID>::aPtrs<_SID>(v34, v15, (unsigned int)AceCount);
  v29 = 0;
  v16 = 0;
  v17 = a4;
  do
  {
    pAce = 0;
    if ( !GetAce(v7, v16, &pAce) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        v28 = GetLastError();
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 32), 21, &WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids, v16, v28);
      }
LABEL_73:
      aPtrs<_SID>::~aPtrs<_SID>(v34);
      free(v12);
      return 3222146058LL;
    }
    if ( (unsigned int)IsNewSid((char *)pAce + 8, v15, &v29) )
    {
      pSid1 = (char *)pAce + 8;
      v19 = 0;
      v20 = 0;
      if ( *((char *)pAce + 1) < 0 )
        v19 = *((_DWORD *)pAce + 1);
      if ( (*((_BYTE *)pAce + 1) & 0x40) != 0 )
        v20 = *((_DWORD *)pAce + 1);
      for ( i = ++v16; i < v38; ++i )
      {
        if ( !GetAce(a2, i, &pAce) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          {
            v27 = GetLastError();
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 32),
              22,
              &WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
              v16,
              v27);
          }
          goto LABEL_73;
        }
        if ( EqualSid(pSid1, (char *)pAce + 8) )
        {
          if ( *((char *)pAce + 1) < 0 )
            v19 |= *((_DWORD *)pAce + 1);
          if ( (*((_BYTE *)pAce + 1) & 0x40) != 0 )
            v20 |= *((_DWORD *)pAce + 1);
        }
      }
      v22 = a1;
      if ( v20 )
      {
        v23 = MapNt4RightsToNt5Ace(a1, v20);
        v24 = a4;
        if ( v23 )
        {
          if ( !AddAuditAccessAce(*a4, 4u, v23, pSid1, 1, v19 == v20) )
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 32),
                25,
                &WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
                (unsigned int)LastError);
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_55;
          }
          v22 = a1;
        }
      }
      else
      {
        v24 = a4;
      }
      if ( v19
        && v19 != v20
        && (v25 = MapNt4RightsToNt5Ace(v22, v19)) != 0
        && !AddAuditAccessAce(*v24, 4u, v25, pSid1, 0, 1) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            26,
            &WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
            (unsigned int)LastError);
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        if ( v20 )
        {
          LOBYTE(v18) = 2;
          v26 = BuildNt5ObjAce(a1, v18, 1, v19 == v20, pSid1, v20, *v24);
          if ( v26 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 32),
                23,
                &WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
                (unsigned int)v26);
            aPtrs<_SID>::~aPtrs<_SID>(v34);
            free(v12);
            return (unsigned int)v26;
          }
        }
        v17 = a4;
        if ( !v19
          || v19 == v20
          || (LOBYTE(v18) = 2, LastError = BuildNt5ObjAce(a1, v18, 0, 1, pSid1, v19, *a4), LastError >= 0) )
        {
          v7 = a2;
          v15 = v32;
          continue;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            24,
            &WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
            (unsigned int)LastError);
      }
LABEL_55:
      aPtrs<_SID>::~aPtrs<_SID>(v34);
      free(v12);
      return (unsigned int)LastError;
    }
    ++v16;
  }
  while ( v16 < v38 );
  ShrinkAcl(v17, a3);
  aPtrs<_SID>::~aPtrs<_SID>(v34);
  free(0);
  return 0;
}

```

## disassembly

```asm
0x180024dbc  mov     rax, rsp
0x180024dbf  mov     [rax+18h], rbx
0x180024dc3  mov     [rax+20h], r9
0x180024dc7  mov     [rax+10h], rdx
0x180024dcb  mov     [rax+8], ecx
0x180024dce  push    rbp
0x180024dcf  push    rsi
0x180024dd0  push    rdi
0x180024dd1  push    r12
0x180024dd3  push    r13
0x180024dd5  push    r14
0x180024dd7  push    r15
0x180024dd9  mov     rbp, rsp
0x180024ddc  sub     rsp, 80h
0x180024de3  mov     rsi, r9
0x180024de6  mov     r13, r8
0x180024de9  mov     r14, rdx
0x180024dec  xor     r10d, r10d
0x180024def  cmp     byte ptr [rdx], 4
0x180024df2  setz    r10b
0x180024df6  mov     rax, [rbp+arg_20]
0x180024dfa  mov     [rax], r10d
0x180024dfd  jnz     short loc_180024E26
0x180024dff  movzx   eax, word ptr [rdx+2]
0x180024e03  mov     [r8], eax
0x180024e06  mov     ecx, eax; unsigned __int64
0x180024e08  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180024e0d  mov     [rsi], rax
0x180024e10  mov     r8d, [r13+0]; Size
0x180024e14  mov     rdx, r14; Src
0x180024e17  mov     rcx, rax; void *
0x180024e1a  call    memcpy_0
0x180024e1f  xor     eax, eax
0x180024e21  jmp     loc_18002533B
0x180024e26  mov     ecx, 0FFF0h; unsigned __int64
0x180024e2b  mov     [r8], ecx
0x180024e2e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180024e33  mov     rbx, rax
0x180024e36  mov     [rbp+var_20], rax
0x180024e3a  mov     [rsi], rax
0x180024e3d  mov     r8d, 4; dwAclRevision
0x180024e43  mov     edx, [r13+0]; nAclLength
0x180024e47  mov     rcx, rax; pAcl
0x180024e4a  call    cs:__imp_InitializeAcl
0x180024e50  test    eax, eax
0x180024e52  jnz     short loc_180024EB4
0x180024e54  call    cs:__imp_GetLastError
0x180024e5a  mov     esi, eax
0x180024e5c  lea     rax, WPP_GLOBAL_Control
0x180024e63  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e6a  cmp     rcx, rax
0x180024e6d  jz      short loc_180024E96
0x180024e6f  mov     edi, 1
0x180024e74  test    [rcx+10Ch], dil
0x180024e7b  jz      short loc_180024E96
0x180024e7d  lea     edx, [rdi+13h]
0x180024e80  mov     r9d, esi
0x180024e83  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x180024e8a  mov     rcx, [rcx+100h]
0x180024e91  call    WPP_SF_d
0x180024e96  test    esi, esi
0x180024e98  jle     short loc_180024EA3
0x180024e9a  movzx   esi, si
0x180024e9d  or      esi, 80070000h
0x180024ea3  mov     rcx, rbx; Block
0x180024ea6  call    cs:__imp_free
0x180024eac  nop
0x180024ead  mov     eax, esi
0x180024eaf  jmp     loc_18002533B
0x180024eb4  movzx   edi, word ptr [r14+4]
0x180024eb9  mov     dword ptr [rbp+arg_20], edi
0x180024ebc  mov     eax, 8
0x180024ec1  mul     rdi
0x180024ec4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180024ecb  cmovb   rax, rcx
0x180024ecf  mov     rcx, rax; unsigned __int64
0x180024ed2  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180024ed7  mov     rsi, rax
0x180024eda  mov     [rbp+var_28], rax
0x180024ede  mov     r8d, edi
0x180024ee1  mov     rdx, rax
0x180024ee4  lea     rcx, [rbp+var_18]
0x180024ee8  call    ??0?$aPtrs@U_SID@@@@QEAA@PEAPEAU_SID@@K@Z; aPtrs<_SID>::aPtrs<_SID>(_SID * *,ulong)
0x180024eed  nop
0x180024eee  mov     [rbp+var_40], 0
0x180024ef5  xor     r15d, r15d
0x180024ef8  lea     edi, [r15+1]
0x180024efc  mov     r12, [rbp+arg_18]
0x180024f00  mov     [rbp+pAce], 0
0x180024f08  lea     r8, [rbp+pAce]; pAce
0x180024f0c  mov     edx, r15d; dwAceIndex
0x180024f0f  mov     rcx, r14; pAcl
0x180024f12  call    cs:__imp_GetAce
0x180024f18  test    eax, eax
0x180024f1a  jz      loc_1800252D9
0x180024f20  mov     rcx, [rbp+pAce]
0x180024f24  add     rcx, 8; pSourceSid
0x180024f28  lea     r8, [rbp+var_40]; unsigned int *
0x180024f2c  mov     rdx, rsi; struct _SID **
0x180024f2f  call    ?IsNewSid@@YAHPEAXPEAPEAU_SID@@PEAK@Z; IsNewSid(void *,_SID * *,ulong *)
0x180024f34  test    eax, eax
0x180024f36  jnz     short loc_180024F40
0x180024f38  add     r15d, edi
0x180024f3b  jmp     loc_1800250D1
0x180024f40  mov     rax, [rbp+pAce]
0x180024f44  lea     r10, [rax+8]
0x180024f48  mov     [rbp+pSid1], r10
0x180024f4c  xor     r14d, r14d
0x180024f4f  xor     esi, esi
0x180024f51  cmp     [rax+1], sil
0x180024f55  jge     short loc_180024F5B
0x180024f57  mov     r14d, [rax+4]
0x180024f5b  test    byte ptr [rax+1], 40h
0x180024f5f  jz      short loc_180024F64
0x180024f61  mov     esi, [rax+4]
0x180024f64  add     r15d, edi
0x180024f67  mov     r12d, r15d
0x180024f6a  cmp     r12d, dword ptr [rbp+arg_20]
0x180024f6e  jnb     short loc_180024FBB
0x180024f70  lea     r8, [rbp+pAce]; pAce
0x180024f74  mov     edx, r12d; dwAceIndex
0x180024f77  mov     rcx, [rbp+pAcl]; pAcl
0x180024f7b  call    cs:__imp_GetAce
0x180024f81  test    eax, eax
0x180024f83  jz      loc_180025108
0x180024f89  mov     rdx, [rbp+pAce]
0x180024f8d  add     rdx, 8; pSid2
0x180024f91  mov     rcx, [rbp+pSid1]; pSid1
0x180024f95  call    cs:__imp_EqualSid
0x180024f9b  test    eax, eax
0x180024f9d  jz      short loc_180024FB6
0x180024f9f  mov     rax, [rbp+pAce]
0x180024fa3  cmp     byte ptr [rax+1], 0
0x180024fa7  jge     short loc_180024FAD
0x180024fa9  or      r14d, [rax+4]
0x180024fad  test    byte ptr [rax+1], 40h
0x180024fb1  jz      short loc_180024FB6
0x180024fb3  or      esi, [rax+4]
0x180024fb6  add     r12d, edi
0x180024fb9  jmp     short loc_180024F6A
0x180024fbb  mov     r10d, [rbp+arg_0]
0x180024fbf  test    esi, esi
0x180024fc1  jz      loc_1800250FF
0x180024fc7  mov     edx, esi
0x180024fc9  mov     ecx, r10d
0x180024fcc  call    _MapNt4RightsToNt5Ace
0x180024fd1  mov     r12, [rbp+arg_18]
0x180024fd5  test    eax, eax
0x180024fd7  jz      short loc_18002500B
0x180024fd9  xor     ecx, ecx
0x180024fdb  cmp     r14d, esi
0x180024fde  setz    cl
0x180024fe1  mov     [rsp+80h+bAuditFailure], ecx; bAuditFailure
0x180024fe5  mov     [rsp+80h+bAuditSuccess], edi; bAuditSuccess
0x180024fe9  mov     r9, [rbp+pSid1]; pSid
0x180024fed  mov     r8d, eax; dwAccessMask
0x180024ff0  mov     edx, 4; dwAceRevision
0x180024ff5  mov     rcx, [r12]; pAcl
0x180024ff9  call    cs:__imp_AddAuditAccessAce
0x180024fff  test    eax, eax
0x180025001  jz      loc_18002516A
0x180025007  mov     r10d, [rbp+arg_0]
0x18002500b  test    r14d, r14d
0x18002500e  jz      short loc_18002504E
0x180025010  cmp     r14d, esi
0x180025013  jz      short loc_18002504E
0x180025015  mov     edx, r14d
0x180025018  mov     ecx, r10d
0x18002501b  call    _MapNt4RightsToNt5Ace
0x180025020  test    eax, eax
0x180025022  jz      short loc_18002504E
0x180025024  mov     [rsp+80h+bAuditFailure], edi; bAuditFailure
0x180025028  mov     [rsp+80h+bAuditSuccess], 0; bAuditSuccess
0x180025030  mov     r9, [rbp+pSid1]; pSid
0x180025034  mov     r8d, eax; dwAccessMask
0x180025037  mov     edx, 4; dwAceRevision
0x18002503c  mov     rcx, [r12]; pAcl
0x180025040  call    cs:__imp_AddAuditAccessAce
0x180025046  test    eax, eax
0x180025048  jz      loc_1800251CF
0x18002504e  test    esi, esi
0x180025050  jz      short loc_18002508A
0x180025052  xor     r9d, r9d
0x180025055  cmp     r14d, esi
0x180025058  setz    r9b
0x18002505c  mov     rax, [r12]
0x180025060  mov     [rsp+80h+var_50], rax
0x180025065  mov     [rsp+80h+bAuditFailure], esi
0x180025069  mov     rax, [rbp+pSid1]
0x18002506d  mov     qword ptr [rsp+80h+bAuditSuccess], rax
0x180025072  mov     r8d, edi
0x180025075  mov     dl, 2
0x180025077  mov     ecx, [rbp+arg_0]
0x18002507a  call    _BuildNt5ObjAce
0x18002507f  mov     r12d, eax
0x180025082  test    eax, eax
0x180025084  js      loc_180025234
0x18002508a  mov     r12, [rbp+arg_18]
0x18002508e  test    r14d, r14d
0x180025091  jz      short loc_1800250C9
0x180025093  cmp     r14d, esi
0x180025096  jz      short loc_1800250C9
0x180025098  mov     rax, [r12]
0x18002509c  mov     [rsp+80h+var_50], rax
0x1800250a1  mov     [rsp+80h+bAuditFailure], r14d
0x1800250a6  mov     rax, [rbp+pSid1]
0x1800250aa  mov     qword ptr [rsp+80h+bAuditSuccess], rax
0x1800250af  mov     r9d, edi
0x1800250b2  xor     r8d, r8d
0x1800250b5  mov     dl, 2
0x1800250b7  mov     ecx, [rbp+arg_0]
0x1800250ba  call    _BuildNt5ObjAce
0x1800250bf  mov     esi, eax
0x1800250c1  test    eax, eax
0x1800250c3  js      loc_180025288
0x1800250c9  mov     r14, [rbp+pAcl]
0x1800250cd  mov     rsi, [rbp+var_28]
0x1800250d1  cmp     r15d, dword ptr [rbp+arg_20]
0x1800250d5  jb      loc_180024F00
0x1800250db  mov     rdx, r13
0x1800250de  mov     rcx, r12
0x1800250e1  call    _ShrinkAcl
0x1800250e6  nop
0x1800250e7  lea     rcx, [rbp+var_18]
0x1800250eb  call    ??1?$aPtrs@U_SID@@@@QEAA@XZ; aPtrs<_SID>::~aPtrs<_SID>(void)
0x1800250f0  nop
0x1800250f1  xor     ecx, ecx; Block
0x1800250f3  call    cs:__imp_free
0x1800250f9  nop
0x1800250fa  jmp     loc_180024E1F
0x1800250ff  mov     r12, [rbp+arg_18]
0x180025103  jmp     loc_18002500B
0x180025108  lea     rax, WPP_GLOBAL_Control
0x18002510f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025116  cmp     rcx, rax
0x180025119  jz      short loc_180025151
0x18002511b  test    [rcx+10Ch], dil
0x180025122  jz      short loc_180025151
0x180025124  call    cs:__imp_GetLastError
0x18002512a  mov     edx, 16h
0x18002512f  mov     [rsp+80h+bAuditSuccess], eax
0x180025133  mov     r9d, r15d
0x180025136  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x18002513d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025144  mov     rcx, [rcx+100h]
0x18002514b  call    WPP_SF_dd
0x180025150  nop
0x180025151  lea     rcx, [rbp+var_18]
0x180025155  call    ??1?$aPtrs@U_SID@@@@QEAA@XZ; aPtrs<_SID>::~aPtrs<_SID>(void)
0x18002515a  nop
0x18002515b  mov     rcx, rbx; Block
0x18002515e  call    cs:__imp_free
0x180025164  nop
0x180025165  jmp     loc_180025336
0x18002516a  call    cs:__imp_GetLastError
0x180025170  mov     esi, eax
0x180025172  lea     rax, WPP_GLOBAL_Control
0x180025179  mov     rcx, cs:WPP_GLOBAL_Control
0x180025180  cmp     rcx, rax
0x180025183  jz      short loc_1800251A9
0x180025185  test    [rcx+10Ch], dil
0x18002518c  jz      short loc_1800251A9
0x18002518e  mov     edx, 19h
0x180025193  mov     r9d, esi
0x180025196  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x18002519d  mov     rcx, [rcx+100h]
0x1800251a4  call    WPP_SF_d
0x1800251a9  test    esi, esi
0x1800251ab  jle     short loc_1800251B6
0x1800251ad  movzx   esi, si
0x1800251b0  or      esi, 80070000h
0x1800251b6  lea     rcx, [rbp+var_18]
0x1800251ba  call    ??1?$aPtrs@U_SID@@@@QEAA@XZ; aPtrs<_SID>::~aPtrs<_SID>(void)
0x1800251bf  nop
0x1800251c0  mov     rcx, rbx; Block
0x1800251c3  call    cs:__imp_free
0x1800251c9  nop
0x1800251ca  jmp     loc_180024EAD
0x1800251cf  call    cs:__imp_GetLastError
0x1800251d5  mov     esi, eax
0x1800251d7  lea     rax, WPP_GLOBAL_Control
0x1800251de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800251e5  cmp     rcx, rax
0x1800251e8  jz      short loc_18002520E
0x1800251ea  test    [rcx+10Ch], dil
0x1800251f1  jz      short loc_18002520E
0x1800251f3  mov     edx, 1Ah
0x1800251f8  mov     r9d, esi
0x1800251fb  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x180025202  mov     rcx, [rcx+100h]
0x180025209  call    WPP_SF_d
0x18002520e  test    esi, esi
0x180025210  jle     short loc_18002521B
0x180025212  movzx   esi, si
0x180025215  or      esi, 80070000h
0x18002521b  lea     rcx, [rbp+var_18]
0x18002521f  call    ??1?$aPtrs@U_SID@@@@QEAA@XZ; aPtrs<_SID>::~aPtrs<_SID>(void)
0x180025224  nop
0x180025225  mov     rcx, rbx; Block
0x180025228  call    cs:__imp_free
  ... truncated ...
```
