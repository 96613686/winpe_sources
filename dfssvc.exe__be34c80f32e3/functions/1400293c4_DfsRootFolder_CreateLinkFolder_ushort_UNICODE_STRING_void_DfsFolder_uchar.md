# DfsRootFolder::CreateLinkFolder(ushort *,_UNICODE_STRING *,void *,DfsFolder * *,uchar)

- ea: `0x1400293c4`
- end: `0x1400296d0`
- name: `?CreateLinkFolder@DfsRootFolder@@QEAAKPEAGPEAU_UNICODE_STRING@@PEAXPEAPEAVDfsFolder@@E@Z`
- size: `780`
- prototype: `unsigned int __usercall@<eax>(DfsRootFolder *__hidden this@<rcx>, unsigned __int16 *@<rdx>, struct _UNICODE_STRING *@<r8>, void *@<r9>, struct DfsFolder **, unsigned __int8)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, loader_planting, installer_update`

## callers

- `0x140031108`

## callees

- `0x1400011d0`
- `0x1400097f8`
- `0x14000abc4`
- `0x140012c20`
- `0x140017088`
- `0x140026ec8`
- `0x1400293c4`
- `0x14002a7b4`
- `0x14002b870`
- `0x14002e798`
- `0x14002ffe0`
- `0x140032254`
- `0x140058ce0`
- `0x140058d7c`
- `0x14005abf4`
- `0x14005ce70`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x140029503`
- `ntdll!RtlNtStatusToDosError` at `0x140029503`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400294b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400294b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400294f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400294f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140029550`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140029550`

## pseudocode

```c
__int64 __fastcall DfsRootFolder::CreateLinkFolder(
        DfsRootFolder *this,
        unsigned __int16 *a2,
        struct _UNICODE_STRING *a3,
        void *a4,
        struct DfsFolder **a5,
        unsigned __int8 a6)
{
  void *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdi
  unsigned int UnicodeStringFromString; // ebx
  DfsGeneric *v13; // rcx
  unsigned __int8 v14; // dl
  __int64 v15; // rbx
  NTSTATUS v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // ebp
  unsigned int v21; // ecx
  unsigned int v23; // [rsp+30h] [rbp-88h] BYREF
  void *v24; // [rsp+38h] [rbp-80h]
  unsigned __int16 *v25[2]; // [rsp+40h] [rbp-78h] BYREF
  __int128 v26; // [rsp+50h] [rbp-68h]

  v23 = 0;
  v24 = a4;
  *a5 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_SZ(*((_QWORD *)pWppControl + 2), (_DWORD)a2, (_DWORD)a3, (_DWORD)a2, (__int64)a3);
  }
  v9 = operator new(0x70u);
  if ( v9 && (v10 = DfsFolder::DfsFolder(v9, this, 1819231812), (v11 = v10) != 0) )
  {
    UnicodeStringFromString = DfsCreateUnicodeStringFromString(v10 + 64, a2);
    v13 = (DfsGeneric *)v11;
    if ( UnicodeStringFromString )
      goto LABEL_31;
    UnicodeStringFromString = DfsCreateUnicodeString(v11 + 80, (const void **)a3);
    v13 = (DfsGeneric *)v11;
    if ( UnicodeStringFromString )
      goto LABEL_31;
    DfsFolder::AcquireLinkLock((DfsFolder *)v11, v14);
    v15 = *((_QWORD *)this + 57);
    EnterCriticalSection(*(LPCRITICAL_SECTION *)(v15 + 16));
    *(_DWORD *)(v15 + 8) |= 1u;
    v16 = DfsInsertInNameTableLocked(*((_QWORD *)this + 57), v11 + 64, v11);
    if ( !v16 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
      *(_DWORD *)(v11 + 52) |= 2u;
    }
    v17 = *((_QWORD *)this + 57);
    *(_DWORD *)(v17 + 8) &= ~1u;
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v17 + 16));
    UnicodeStringFromString = RtlNtStatusToDosError(v16);
    if ( !UnicodeStringFromString )
    {
      UnicodeStringFromString = DfsRootFolder::InsertLinkFolderInLogicalPrefixTable(this, (struct DfsFolder *)v11);
      if ( UnicodeStringFromString )
      {
        DfsRootFolder::RemoveLinkFolderFromMetadataNameTable(this, (struct DfsFolder *)v11);
      }
      else
      {
        ++*((_DWORD *)this + 62);
        v18 = *((_QWORD *)this + 61);
        if ( v18 )
          ++*(_QWORD *)(v18 + 120);
      }
    }
    ++*(_DWORD *)(v11 + 48);
    ReleaseSRWLockExclusive((PSRWLOCK)(v11 + 40));
    v13 = (DfsGeneric *)v11;
    if ( UnicodeStringFromString )
      goto LABEL_31;
    v19 = DfsRootFolder::SetupLinkReparsePoint(this, *(const unsigned __int16 **)(v11 + 88), v24, (int *)&v23);
    v20 = v19;
    if ( a6 )
    {
      UnicodeStringFromString = v19;
    }
    else if ( v19 )
    {
      v25[0] = *(unsigned __int16 **)(v11 + 88);
      v25[1] = *((unsigned __int16 **)this + 24);
      v21 = v19;
      v26 = 0;
      if ( v23 )
        v21 = v23;
      DfsRootFolder::GenerateEventLog(this, 0xC00038A7, 2u, (const unsigned __int16 **const)v25, v21);
      *(_DWORD *)(v11 + 100) = v20;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (((1 << (v20 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_qZD(
        *((_QWORD *)pWppControl + 2),
        22,
        (unsigned int)WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids,
        v11,
        (__int64)a3,
        UnicodeStringFromString);
    }
    v13 = (DfsGeneric *)v11;
    if ( UnicodeStringFromString )
    {
LABEL_31:
      DfsGeneric::ReleaseReference(v13);
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 60) + 64LL));
      *a5 = (struct DfsFolder *)v11;
    }
  }
  else
  {
    UnicodeStringFromString = 8;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (((1 << (UnicodeStringFromString != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_SqD(
      *((_QWORD *)pWppControl + 2),
      23,
      (unsigned int)WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids,
      (_DWORD)a2,
      (char)*a5,
      UnicodeStringFromString);
  }
  return UnicodeStringFromString;
}

```

## disassembly

```asm
0x1400293c4  push    rbx
0x1400293c6  push    rbp
0x1400293c7  push    rsi
0x1400293c8  push    rdi
0x1400293c9  push    r12
0x1400293cb  push    r13
0x1400293cd  push    r14
0x1400293cf  push    r15
0x1400293d1  sub     rsp, 78h
0x1400293d5  mov     rax, cs:__security_cookie
0x1400293dc  xor     rax, rsp
0x1400293df  mov     [rsp+0B8h+var_58], rax
0x1400293e4  mov     r13, [rsp+0B8h+arg_20]
0x1400293ec  mov     r15, r8
0x1400293ef  and     [rsp+0B8h+var_88], 0
0x1400293f4  mov     r12, rdx
0x1400293f7  mov     [rsp+0B8h+var_80], r9
0x1400293fc  mov     rsi, rcx
0x1400293ff  and     qword ptr [r13+0], 0
0x140029404  lea     rax, WPP_GLOBAL_Control
0x14002940b  mov     r14d, 20h ; ' '
0x140029411  cmp     cs:WPP_GLOBAL_Control, rax
0x140029418  jz      short loc_140029443
0x14002941a  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140029421  test    rcx, rcx
0x140029424  jz      short loc_140029443
0x140029426  test    [rcx+1Ch], r14b
0x14002942a  jz      short loc_140029443
0x14002942c  cmp     byte ptr [rcx+19h], 3
0x140029430  jb      short loc_140029443
0x140029432  mov     rcx, [rcx+10h]
0x140029436  mov     r9, rdx
0x140029439  mov     qword ptr [rsp+0B8h+var_98], r8
0x14002943e  call    WPP_SF_SZ
0x140029443  mov     ecx, 70h ; 'p'; Size
0x140029448  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002944d  test    rax, rax
0x140029450  jz      loc_14002964D
0x140029456  mov     r8d, 6C6F4644h
0x14002945c  mov     rdx, rsi
0x14002945f  mov     rcx, rax
0x140029462  call    ??0DfsFolder@@QEAA@PEAV0@W4DfsObjectTypeEnumeration@@@Z; DfsFolder::DfsFolder(DfsFolder *,DfsObjectTypeEnumeration)
0x140029467  mov     rdi, rax
0x14002946a  test    rax, rax
0x14002946d  jz      loc_14002964D
0x140029473  mov     rdx, r12
0x140029476  lea     rcx, [rax+40h]
0x14002947a  call    DfsCreateUnicodeStringFromString
0x14002947f  mov     ebx, eax
0x140029481  mov     rcx, rdi; this
0x140029484  test    eax, eax
0x140029486  jnz     loc_140029646
0x14002948c  lea     rcx, [rdi+50h]
0x140029490  mov     rdx, r15
0x140029493  call    DfsCreateUnicodeString
0x140029498  mov     ebx, eax
0x14002949a  mov     rcx, rdi; this
0x14002949d  test    eax, eax
0x14002949f  jnz     loc_140029646
0x1400294a5  call    ?AcquireLinkLock@DfsFolder@@QEAAXE@Z; DfsFolder::AcquireLinkLock(uchar)
0x1400294aa  mov     rbx, [rsi+1C8h]
0x1400294b1  mov     rcx, [rbx+10h]; lpCriticalSection
0x1400294b5  call    cs:__imp_EnterCriticalSection
0x1400294bc  nop     dword ptr [rax+rax+00h]
0x1400294c1  or      dword ptr [rbx+8], 1
0x1400294c5  lea     rdx, [rdi+40h]
0x1400294c9  mov     rcx, [rsi+1C8h]
0x1400294d0  mov     r8, rdi
0x1400294d3  call    DfsInsertInNameTableLocked
0x1400294d8  mov     ebx, eax
0x1400294da  test    eax, eax
0x1400294dc  jnz     short loc_1400294E6
0x1400294de  lock inc dword ptr [rdi+8]
0x1400294e2  or      dword ptr [rdi+34h], 2
0x1400294e6  mov     rcx, [rsi+1C8h]
0x1400294ed  and     dword ptr [rcx+8], 0FFFFFFFEh
0x1400294f1  mov     rcx, [rcx+10h]; lpCriticalSection
0x1400294f5  call    cs:__imp_LeaveCriticalSection
0x1400294fc  nop     dword ptr [rax+rax+00h]
0x140029501  mov     ecx, ebx; Status
0x140029503  call    cs:__imp_RtlNtStatusToDosError
0x14002950a  nop     dword ptr [rax+rax+00h]
0x14002950f  mov     ebx, eax
0x140029511  test    eax, eax
0x140029513  jnz     short loc_140029549
0x140029515  mov     rdx, rdi; struct DfsFolder *
0x140029518  mov     rcx, rsi; this
0x14002951b  call    ?InsertLinkFolderInLogicalPrefixTable@DfsRootFolder@@QEAAKPEAVDfsFolder@@@Z; DfsRootFolder::InsertLinkFolderInLogicalPrefixTable(DfsFolder *)
0x140029520  mov     ebx, eax
0x140029522  test    eax, eax
0x140029524  jnz     short loc_14002953E
0x140029526  inc     dword ptr [rsi+0F8h]
0x14002952c  mov     rax, [rsi+1E8h]
0x140029533  test    rax, rax
0x140029536  jz      short loc_140029549
0x140029538  inc     qword ptr [rax+78h]
0x14002953c  jmp     short loc_140029549
0x14002953e  mov     rdx, rdi; struct DfsFolder *
0x140029541  mov     rcx, rsi; this
0x140029544  call    ?RemoveLinkFolderFromMetadataNameTable@DfsRootFolder@@QEAAKPEAVDfsFolder@@@Z; DfsRootFolder::RemoveLinkFolderFromMetadataNameTable(DfsFolder *)
0x140029549  inc     dword ptr [rdi+30h]
0x14002954c  lea     rcx, [rdi+28h]; SRWLock
0x140029550  call    cs:__imp_ReleaseSRWLockExclusive
0x140029557  nop     dword ptr [rax+rax+00h]
0x14002955c  mov     rcx, rdi
0x14002955f  test    ebx, ebx
0x140029561  jnz     loc_140029646
0x140029567  mov     r8, [rsp+0B8h+var_80]; void *
0x14002956c  lea     r9, [rsp+0B8h+var_88]; int *
0x140029571  mov     rdx, [rdi+58h]; unsigned __int16 *
0x140029575  mov     rcx, rsi; this
0x140029578  call    ?SetupLinkReparsePoint@DfsRootFolder@@IEAAKPEBGPEAXPEAJ@Z; DfsRootFolder::SetupLinkReparsePoint(ushort const *,void *,long *)
0x14002957d  mov     ebp, eax
0x14002957f  cmp     [rsp+0B8h+arg_28], bl
0x140029586  jnz     short loc_1400295D4
0x140029588  test    eax, eax
0x14002958a  jz      short loc_1400295D6
0x14002958c  mov     rcx, [rdi+58h]
0x140029590  lea     r8d, [rbx+2]; unsigned __int16
0x140029594  mov     [rsp+0B8h+var_78], rcx
0x140029599  lea     r9, [rsp+0B8h+var_78]; unsigned __int16 **
0x14002959e  mov     rcx, [rsi+0C0h]
0x1400295a5  xorps   xmm0, xmm0
0x1400295a8  mov     [rsp+0B8h+var_70], rcx
0x1400295ad  mov     edx, 0C00038A7h; unsigned int
0x1400295b2  mov     ecx, eax
0x1400295b4  mov     eax, [rsp+0B8h+var_88]
0x1400295b8  test    eax, eax
0x1400295ba  movdqu  [rsp+0B8h+var_68], xmm0
0x1400295c0  cmovnz  ecx, eax
0x1400295c3  mov     [rsp+0B8h+var_98], ecx; unsigned int
0x1400295c7  mov     rcx, rsi; this
0x1400295ca  call    ?GenerateEventLog@DfsRootFolder@@QEAAXKGQEAPEBGK@Z; DfsRootFolder::GenerateEventLog(ulong,ushort,ushort const * * const,ulong)
0x1400295cf  mov     [rdi+64h], ebp
0x1400295d2  jmp     short loc_1400295D6
0x1400295d4  mov     ebx, ebp
0x1400295d6  lea     rax, WPP_GLOBAL_Control
0x1400295dd  cmp     cs:WPP_GLOBAL_Control, rax
0x1400295e4  jz      short loc_14002962E
0x1400295e6  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400295ed  test    rcx, rcx
0x1400295f0  jz      short loc_14002962E
0x1400295f2  neg     ebp
0x1400295f4  mov     eax, r14d
0x1400295f7  sbb     edx, edx
0x1400295f9  and     edx, 0FFFFFFECh
0x1400295fc  add     edx, 1Fh
0x1400295ff  bts     eax, edx
0x140029602  test    [rcx+1Ch], eax
0x140029605  jz      short loc_14002962E
0x140029607  cmp     byte ptr [rcx+19h], 3
0x14002960b  jb      short loc_14002962E
0x14002960d  mov     rcx, [rcx+10h]
0x140029611  lea     r8, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids
0x140029618  mov     edx, 16h
0x14002961d  mov     [rsp+0B8h+var_90], ebx
0x140029621  mov     r9, rdi
0x140029624  mov     qword ptr [rsp+0B8h+var_98], r15
0x140029629  call    WPP_SF_qZD
0x14002962e  mov     rcx, rdi
0x140029631  test    ebx, ebx
0x140029633  jnz     short loc_140029646
0x140029635  mov     rax, [rsi+1E0h]
0x14002963c  lock inc dword ptr [rax+40h]
0x140029640  mov     [r13+0], rdi
0x140029644  jmp     short loc_140029652
0x140029646  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x14002964b  jmp     short loc_140029652
0x14002964d  mov     ebx, 8
0x140029652  lea     rax, WPP_GLOBAL_Control
0x140029659  cmp     cs:WPP_GLOBAL_Control, rax
0x140029660  jz      short loc_1400296AF
0x140029662  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140029669  test    rcx, rcx
0x14002966c  jz      short loc_1400296AF
0x14002966e  mov     eax, ebx
0x140029670  neg     eax
0x140029672  sbb     edx, edx
0x140029674  and     edx, 0FFFFFFECh
0x140029677  add     edx, 1Fh
0x14002967a  bts     r14d, edx
0x14002967e  test    [rcx+1Ch], r14d
0x140029682  jz      short loc_1400296AF
0x140029684  cmp     byte ptr [rcx+19h], 3
0x140029688  jb      short loc_1400296AF
0x14002968a  mov     rax, [r13+0]
0x14002968e  lea     r8, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids
0x140029695  mov     rcx, [rcx+10h]
0x140029699  mov     edx, 17h
0x14002969e  mov     [rsp+0B8h+var_90], ebx
0x1400296a2  mov     r9, r12
0x1400296a5  mov     qword ptr [rsp+0B8h+var_98], rax
0x1400296aa  call    WPP_SF_SqD
0x1400296af  mov     eax, ebx
0x1400296b1  mov     rcx, [rsp+0B8h+var_58]
0x1400296b6  xor     rcx, rsp; StackCookie
0x1400296b9  call    __security_check_cookie
0x1400296be  add     rsp, 78h
0x1400296c2  pop     r15
0x1400296c4  pop     r14
0x1400296c6  pop     r13
0x1400296c8  pop     r12
0x1400296ca  pop     rdi
0x1400296cb  pop     rsi
0x1400296cc  pop     rbp
0x1400296cd  pop     rbx
0x1400296ce  retn
```
