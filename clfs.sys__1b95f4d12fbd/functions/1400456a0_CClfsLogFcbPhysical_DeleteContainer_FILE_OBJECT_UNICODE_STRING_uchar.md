# CClfsLogFcbPhysical::DeleteContainer(_FILE_OBJECT *,_UNICODE_STRING *,uchar)

- ea: `0x1400456a0`
- end: `0x140045d12`
- name: `?DeleteContainer@CClfsLogFcbPhysical@@UEAAJPEAU_FILE_OBJECT@@PEAU_UNICODE_STRING@@E@Z`
- size: `1650`
- prototype: `__int64 __fastcall(CClfsLogFcbPhysical *__hidden this, struct _FILE_OBJECT *, struct _UNICODE_STRING *, unsigned __int8)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400155a0`

## callees

- `0x140003590`
- `0x1400035a8`
- `0x140005840`
- `0x140005868`
- `0x14000a29c`
- `0x14000b6b0`
- `0x14000c3a4`
- `0x140010548`
- `0x1400121e4`
- `0x140017e40`
- `0x140017f20`
- `0x140018280`
- `0x1400388f4`
- `0x1400456a0`
- `0x1400616cc`
- `0x140061c00`
- `0x140061d00`
- `0x140067060`
- `0x14007493c`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140045734`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140045750`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140045734`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140045750`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140045840`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140045840`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400458b6`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400458b6`
- `ntoskrnl!ExGetPreviousMode` at `0x14004584c`
- `ntoskrnl!ExGetPreviousMode` at `0x14004584c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045899`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045899`

## string_xrefs

- `0x14004596a`: `CClfsLogFcbPhysical::DeleteContainer`
- `0x140045acf`: `CClfsLogFcbPhysical::DeleteContainer`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::DeleteContainer(
        CClfsLogFcbPhysical *this,
        struct _FILE_OBJECT *a2,
        struct _UNICODE_STRING *a3,
        char a4)
{
  __int64 v8; // r14
  BOOLEAN v9; // si
  BOOLEAN v10; // r15
  int Container; // edi
  struct _CLFS_CONTAINER_CONTEXT *v12; // r15
  CLFS_CONTAINER_ID v13; // esi
  struct CClfsAuthContainer *v14; // rcx
  KPROCESSOR_MODE PreviousMode; // al
  struct _CLFS_CONTAINER_CONTEXT *v16; // r15
  int v17; // eax
  struct _CLFS_CONTAINER_CONTEXT *v18; // r15
  unsigned int v19; // r12d
  BOOLEAN v21; // [rsp+40h] [rbp-158h]
  BOOLEAN v22; // [rsp+41h] [rbp-157h]
  struct _CLFS_CONTAINER_CONTEXT *v23; // [rsp+48h] [rbp-150h] BYREF
  struct _CLFS_CONTAINER_CONTEXT *v24; // [rsp+50h] [rbp-148h] BYREF
  PVOID P; // [rsp+58h] [rbp-140h] BYREF
  unsigned int v26; // [rsp+60h] [rbp-138h] BYREF
  __int64 v27; // [rsp+68h] [rbp-130h]
  CClfsLogFcbPhysical *v28; // [rsp+70h] [rbp-128h]
  struct _FILE_OBJECT *v29; // [rsp+78h] [rbp-120h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+80h] [rbp-118h] BYREF
  __int64 v31; // [rsp+A0h] [rbp-F8h]
  struct _ACCESS_STATE AccessState; // [rsp+B0h] [rbp-E8h] BYREF

  v28 = this;
  v29 = a2;
  memset(&AccessState, 0, sizeof(AccessState));
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  P = 0;
  v23 = 0;
  v8 = 0;
  v27 = 0;
  LODWORD(v24) = 0;
  v26 = 0;
  v9 = ExAcquireResourceExclusiveLite((PERESOURCE)((char *)this + 200), 1u);
  v21 = v9;
  v10 = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 176), 1u);
  v22 = v10;
  if ( (*((_DWORD *)this + 91) & 0x1000) != 0 )
  {
    Container = -1072037845;
    CClfsLogFcbCommon::SetInvalidLogTag(this, 6u, -1072037845);
    goto LABEL_43;
  }
  Container = CClfsBaseFile::FindContainer(*((CClfsBaseFile **)this + 89), &v26, a3);
  if ( Container >= 0 )
  {
    Container = CClfsBaseFile::AcquireContainerContext(*((PERESOURCE **)this + 89), v26, &v23);
    if ( Container >= 0 )
    {
      v12 = v23;
      v13 = *((_DWORD *)v23 + 5);
      if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 76) + 64LL))((char *)this + 608) )
      {
        v14 = (struct CClfsAuthContainer *)*((_QWORD *)v12 + 3);
        if ( v14 )
        {
          Container = CClfsBaseFilePersisted::QueryContainerSecurity(v14, &P, 0, (unsigned int *)&v24);
          if ( Container < 0 )
            goto LABEL_42;
          SeCaptureSubjectContext(&SubjectContext);
          PreviousMode = ExGetPreviousMode();
          Container = ClfsSecurityAccessCheck(P, &SubjectContext, 0x10000, 0xC0020000, &AccessState, PreviousMode, 1);
          ExFreePoolWithTag(P, 0);
          P = 0;
          SeReleaseSubjectContext(&SubjectContext);
          if ( Container < 0 )
            goto LABEL_42;
        }
        else if ( (*((_DWORD *)v12 + 9) & 0x29) == 0 )
        {
          Container = -1072037875;
          goto LABEL_42;
        }
      }
      v16 = v23;
      v17 = *((_DWORD *)v23 + 9);
      if ( (v17 & 1) == 0 )
      {
        if ( (v17 & 0x28) != 0 )
        {
          Container = -1073741533;
          goto LABEL_42;
        }
        if ( (*((_BYTE *)this + 376) & 0x20) != 0
          && v13 > ClfsLsnContainer((const CLFS_LSN *)this + 62)
          && v13 < ClfsLsnContainer((const CLFS_LSN *)this + 61) )
        {
          if ( !a4 )
          {
            *((_DWORD *)v16 + 9) = 32;
            _InterlockedIncrement((volatile signed __int32 *)this + 1380);
            if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
            {
              WPP_SF_slid(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                26,
                (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
                (unsigned int)"CClfsLogFcbPhysical::DeleteContainer",
                14,
                (char)this,
                v13);
            }
            goto LABEL_42;
          }
        }
        else if ( v13 < ClfsLsnContainer((const CLFS_LSN *)this + 61)
               || v13 > ClfsLsnContainer((const CLFS_LSN *)this + 63) )
        {
          if ( *((_QWORD *)this + 87) <= *((_QWORD *)this + 58) )
          {
            v31 = *(_QWORD *)(*(__int64 (__fastcall **)(CClfsLogFcbPhysical *, PVOID *))(*(_QWORD *)this + 352LL))(
                               this,
                               &P);
            if ( v13 >= HIDWORD(v31) )
            {
              if ( v13 > ClfsLsnContainer((const CLFS_LSN *)this + 63) )
              {
                v24 = 0;
                v18 = v23;
                v8 = *((_QWORD *)v23 + 3);
                v27 = v8;
                *((_QWORD *)v23 + 3) = 0;
                v19 = *((_DWORD *)this + (--*((_DWORD *)this + 354) & 0x3FF) + 356);
                Container = CClfsBaseFile::AcquireContainerContext(*((PERESOURCE **)this + 89), v19, &v24);
                if ( Container >= 0 )
                {
                  *((_DWORD *)v24 + 5) = v13;
                  Container = CClfsBaseFile::ReleaseContainerContext(*((CClfsBaseFile **)this + 89), &v24);
                  *((_DWORD *)this + (v13 & 0x3FF) + 356) = v19;
                  *((_DWORD *)this + (*((_DWORD *)this + 354) & 0x3FFLL) + 356) = -1;
                  CClfsBaseFilePersisted::RemoveContainer(*((CClfsBaseFilePersisted **)this + 89), v26);
                  CClfsBaseFile::UnlockImage(*((PERESOURCE **)this + 89));
                  v23 = 0;
                }
                else
                {
                  *((_QWORD *)v18 + 3) = v8;
                  v8 = 0;
                  v27 = 0;
                  ++*((_DWORD *)this + 354);
                  CClfsBaseFile::ReleaseContainerContext(*((CClfsBaseFile **)this + 89), &v23);
                }
              }
            }
            else
            {
              *((_DWORD *)v16 + 9) = 8;
              _InterlockedIncrement((volatile signed __int32 *)this + 1380);
              if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
              {
                WPP_SF_slid(
                  *((_QWORD *)WPP_GLOBAL_Control + 3),
                  29,
                  (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
                  (unsigned int)"CClfsLogFcbPhysical::DeleteContainer",
                  126,
                  (char)this,
                  v13);
              }
              CClfsBaseFile::ReleaseContainerContext(*((CClfsBaseFile **)this + 89), &v23);
              CClfsLogFcbPhysical::WrapContainers(this, a2);
            }
            goto LABEL_42;
          }
          if ( !a4 )
          {
            *((_DWORD *)v16 + 9) = 8;
            _InterlockedIncrement((volatile signed __int32 *)this + 1380);
            if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
            {
              WPP_SF_slid(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                28,
                (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
                (unsigned int)"CClfsLogFcbPhysical::DeleteContainer",
                100,
                (char)this,
                v13);
            }
            goto LABEL_42;
          }
        }
        else if ( !a4 )
        {
          *((_DWORD *)v16 + 9) = 8;
          _InterlockedIncrement((volatile signed __int32 *)this + 1380);
          if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
          {
            WPP_SF_slid(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              27,
              (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
              (unsigned int)"CClfsLogFcbPhysical::DeleteContainer",
              56,
              (char)this,
              v13);
          }
          goto LABEL_42;
        }
      }
      Container = -1072037871;
LABEL_42:
      v9 = v21;
      v10 = v22;
    }
  }
LABEL_43:
  if ( Container >= 0 )
  {
    if ( v8 )
    {
      *((_QWORD *)this + 57) -= *((_QWORD *)this + 87);
      *((_QWORD *)this + 58) = CClfsLogFcbPhysical::CalculateAvailableFreeSpace(this);
      P = (PVOID)*((_QWORD *)this + 57);
      v24 = (struct _CLFS_CONTAINER_CONTEXT *)-1LL;
      CClfsLogFcbPhysical::SetCacheFileSizes((union _CLS_LSN *)this, a2, (union _CLS_LSN *)&v24, (signed __int64 *)&P);
    }
    Container = (*(__int64 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 112LL))(this);
  }
  if ( v23 )
    CClfsBaseFile::ReleaseContainerContext(*((CClfsBaseFile **)this + 89), &v23);
  if ( v9 )
    ClfsReleaseResourceLite((struct _ERESOURCE *)((char *)this + 200));
  if ( v10 )
    ClfsReleaseResourceLite(*((struct _ERESOURCE **)this + 176));
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  }
  CClfsLogFcbCommon::NotifyObservers(this, 0xCF03u, 0, 0);
  (*(void (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 232LL))(this);
  return (unsigned int)Container;
}

```

## disassembly

```asm
0x1400456a0  push    rbx
0x1400456a2  push    rsi
0x1400456a3  push    rdi
0x1400456a4  push    r12
0x1400456a6  push    r13
0x1400456a8  push    r14
0x1400456aa  push    r15
0x1400456ac  sub     rsp, 160h
0x1400456b3  mov     rax, cs:__security_cookie
0x1400456ba  xor     rax, rsp
0x1400456bd  mov     [rsp+198h+var_48], rax
0x1400456c5  mov     r12b, r9b
0x1400456c8  mov     rdi, r8
0x1400456cb  mov     r13, rdx
0x1400456ce  mov     rbx, rcx
0x1400456d1  mov     [rsp+198h+var_128], rcx
0x1400456d6  mov     [rsp+198h+var_120], rdx
0x1400456db  xor     edx, edx; Val
0x1400456dd  mov     r8d, 0A0h; Size
0x1400456e3  lea     rcx, [rsp+198h+var_E8]; void *
0x1400456eb  call    memset
0x1400456f0  xorps   xmm0, xmm0
0x1400456f3  movups  xmmword ptr [rsp+198h+SubjectContext.ClientToken], xmm0
0x1400456fb  movups  xmmword ptr [rsp+198h+SubjectContext.PrimaryToken], xmm0
0x140045703  xor     eax, eax
0x140045705  mov     [rsp+198h+P], rax
0x14004570a  mov     [rsp+198h+var_150], rax
0x14004570f  mov     r14d, eax
0x140045712  mov     [rsp+198h+var_130], rax
0x140045717  mov     [rsp+198h+var_154], eax
0x14004571b  mov     dword ptr [rsp+198h+var_148], eax
0x14004571f  mov     [rsp+198h+var_157], al
0x140045723  mov     [rsp+198h+var_158], al
0x140045727  mov     [rsp+198h+var_138], eax
0x14004572b  lea     rcx, [rbx+0C8h]; Resource
0x140045732  mov     dl, 1; Wait
0x140045734  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004573b  nop     dword ptr [rax+rax+00h]
0x140045740  mov     sil, al
0x140045743  mov     [rsp+198h+var_158], al
0x140045747  mov     dl, 1; Wait
0x140045749  mov     rcx, [rbx+580h]; Resource
0x140045750  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140045757  nop     dword ptr [rax+rax+00h]
0x14004575c  mov     r15b, al
0x14004575f  mov     [rsp+198h+var_157], al
0x140045763  test    dword ptr [rbx+16Ch], 1000h
0x14004576d  jz      short loc_14004578C
0x14004576f  mov     edi, 0C01A002Bh
0x140045774  mov     [rsp+198h+var_154], edi
0x140045778  mov     r8d, edi; int
0x14004577b  lea     edx, [r14+6]; unsigned int
0x14004577f  mov     rcx, rbx; this
0x140045782  call    ?SetInvalidLogTag@CClfsLogFcbCommon@@QEAAXKJ@Z; CClfsLogFcbCommon::SetInvalidLogTag(ulong,long)
0x140045787  jmp     loc_140045C08
0x14004578c  mov     r8, rdi; struct _UNICODE_STRING *
0x14004578f  lea     rdx, [rsp+198h+var_138]; unsigned int *
0x140045794  mov     rcx, [rbx+2C8h]; this
0x14004579b  call    ?FindContainer@CClfsBaseFile@@QEAAJPEAKPEAU_UNICODE_STRING@@@Z; CClfsBaseFile::FindContainer(ulong *,_UNICODE_STRING *)
0x1400457a0  mov     edi, eax
0x1400457a2  mov     [rsp+198h+var_154], eax
0x1400457a6  test    eax, eax
0x1400457a8  js      loc_140045C08
0x1400457ae  lea     r8, [rsp+198h+var_150]; struct _CLFS_CONTAINER_CONTEXT **
0x1400457b3  mov     edx, [rsp+198h+var_138]; unsigned int
0x1400457b7  mov     rcx, [rbx+2C8h]; this
0x1400457be  call    ?AcquireContainerContext@CClfsBaseFile@@QEAAJKPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::AcquireContainerContext(ulong,_CLFS_CONTAINER_CONTEXT * *)
0x1400457c3  mov     edi, eax
0x1400457c5  mov     [rsp+198h+var_154], eax
0x1400457c9  test    eax, eax
0x1400457cb  js      loc_140045C08
0x1400457d1  mov     r15, [rsp+198h+var_150]
0x1400457d6  mov     esi, [r15+14h]
0x1400457da  lea     rcx, [rbx+260h]
0x1400457e1  mov     rax, [rcx]
0x1400457e4  mov     rax, [rax+40h]
0x1400457e8  call    _guard_dispatch_icall
0x1400457ed  test    al, al
0x1400457ef  jz      loc_1400458CA
0x1400457f5  mov     rcx, [r15+18h]; this
0x1400457f9  test    rcx, rcx
0x1400457fc  jnz     short loc_140045818
0x1400457fe  mov     eax, [r15+24h]
0x140045802  test    al, 29h
0x140045804  jnz     loc_1400458CA
0x14004580a  mov     edi, 0C01A000Dh
0x14004580f  mov     [rsp+198h+var_154], edi
0x140045813  jmp     loc_140045BFE
0x140045818  lea     r9, [rsp+198h+var_148]; unsigned int *
0x14004581d  xor     r8d, r8d; unsigned int
0x140045820  lea     rdx, [rsp+198h+P]; void **
0x140045825  call    ?QueryContainerSecurity@CClfsBaseFilePersisted@@SAJPEAVCClfsAuthContainer@@AEAPEAXKAEAK@Z; CClfsBaseFilePersisted::QueryContainerSecurity(CClfsAuthContainer *,void * &,ulong,ulong &)
0x14004582a  mov     edi, eax
0x14004582c  mov     [rsp+198h+var_154], eax
0x140045830  test    eax, eax
0x140045832  js      loc_140045BFE
0x140045838  lea     rcx, [rsp+198h+SubjectContext]; SubjectContext
0x140045840  call    cs:__imp_SeCaptureSubjectContext
0x140045847  nop     dword ptr [rax+rax+00h]
0x14004584c  call    cs:__imp_ExGetPreviousMode
0x140045853  nop     dword ptr [rax+rax+00h]
0x140045858  mov     [rsp+198h+var_168], 1; char
0x14004585d  mov     [rsp+198h+var_170], al; KPROCESSOR_MODE
0x140045861  lea     rax, [rsp+198h+var_E8]
0x140045869  mov     [rsp+198h+AccessState], rax; AccessState
0x14004586e  mov     r9d, 0C0020000h
0x140045874  mov     r8d, 10000h
0x14004587a  lea     rdx, [rsp+198h+SubjectContext]; SubjectContext
0x140045882  mov     rcx, [rsp+198h+P]; SecurityDescriptor
0x140045887  call    ClfsSecurityAccessCheck
0x14004588c  mov     edi, eax
0x14004588e  mov     [rsp+198h+var_154], eax
0x140045892  xor     edx, edx; Tag
0x140045894  mov     rcx, [rsp+198h+P]; P
0x140045899  call    cs:__imp_ExFreePoolWithTag
0x1400458a0  nop     dword ptr [rax+rax+00h]
0x1400458a5  mov     [rsp+198h+P], 0
0x1400458ae  lea     rcx, [rsp+198h+SubjectContext]; SubjectContext
0x1400458b6  call    cs:__imp_SeReleaseSubjectContext
0x1400458bd  nop     dword ptr [rax+rax+00h]
0x1400458c2  test    edi, edi
0x1400458c4  js      loc_140045BFE
0x1400458ca  mov     r15, [rsp+198h+var_150]
0x1400458cf  mov     eax, [r15+24h]
0x1400458d3  test    al, 1
0x1400458d5  jz      short loc_1400458E1
0x1400458d7  mov     edi, 0C01A0011h
0x1400458dc  jmp     loc_14004580F
0x1400458e1  test    al, 28h
0x1400458e3  jz      short loc_1400458EF
0x1400458e5  mov     edi, 0C0000123h
0x1400458ea  jmp     loc_14004580F
0x1400458ef  test    byte ptr [rbx+178h], 20h
0x1400458f6  jz      loc_140045986
0x1400458fc  lea     rcx, [rbx+1F0h]; plsn
0x140045903  call    ClfsLsnContainer
0x140045908  cmp     esi, eax
0x14004590a  jbe     short loc_140045986
0x14004590c  lea     rcx, [rbx+1E8h]; plsn
0x140045913  call    ClfsLsnContainer
0x140045918  cmp     esi, eax
0x14004591a  jnb     short loc_140045986
0x14004591c  test    r12b, r12b
0x14004591f  jnz     short loc_1400458D7
0x140045921  mov     dword ptr [r15+24h], 20h ; ' '
0x140045929  lock inc dword ptr [rbx+1590h]
0x140045930  lea     rax, WPP_GLOBAL_Control
0x140045937  mov     rcx, cs:WPP_GLOBAL_Control
0x14004593e  cmp     rcx, rax
0x140045941  jz      loc_140045BFE
0x140045947  test    dword ptr [rcx+2Ch], 8000000h
0x14004594e  jz      loc_140045BFE
0x140045954  mov     edx, 1Ah
0x140045959  mov     dword ptr [rsp+198h+var_168], esi
0x14004595d  mov     qword ptr [rsp+198h+var_170], rbx
0x140045962  mov     dword ptr [rsp+198h+AccessState], 3A0Eh
0x14004596a  lea     r9, aCclfslogfcbphy; "CClfsLogFcbPhysical::DeleteContainer"
0x140045971  lea     r8, WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids
0x140045978  mov     rcx, [rcx+18h]
0x14004597c  call    WPP_SF_slid
0x140045981  jmp     loc_140045BFE
0x140045986  lea     rcx, [rbx+1E8h]; plsn
0x14004598d  call    ClfsLsnContainer
0x140045992  cmp     esi, eax
0x140045994  jb      short loc_1400459FD
0x140045996  lea     rcx, [rbx+1F8h]; plsn
0x14004599d  call    ClfsLsnContainer
0x1400459a2  cmp     esi, eax
0x1400459a4  ja      short loc_1400459FD
0x1400459a6  test    r12b, r12b
0x1400459a9  jnz     loc_1400458D7
0x1400459af  mov     dword ptr [r15+24h], 8
0x1400459b7  lock inc dword ptr [rbx+1590h]
0x1400459be  lea     rax, WPP_GLOBAL_Control
0x1400459c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400459cc  cmp     rcx, rax
0x1400459cf  jz      loc_140045BFE
0x1400459d5  test    dword ptr [rcx+2Ch], 8000000h
0x1400459dc  jz      loc_140045BFE
0x1400459e2  mov     edx, 1Bh
0x1400459e7  mov     dword ptr [rsp+198h+var_168], esi
0x1400459eb  mov     qword ptr [rsp+198h+var_170], rbx
0x1400459f0  mov     dword ptr [rsp+198h+AccessState], 3A38h
0x1400459f8  jmp     loc_14004596A
0x1400459fd  mov     rax, [rbx+1D0h]
0x140045a04  cmp     [rbx+2B8h], rax
0x140045a0b  jle     short loc_140045A64
0x140045a0d  test    r12b, r12b
0x140045a10  jnz     loc_1400458D7
0x140045a16  mov     dword ptr [r15+24h], 8
0x140045a1e  lock inc dword ptr [rbx+1590h]
0x140045a25  lea     rax, WPP_GLOBAL_Control
0x140045a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140045a33  cmp     rcx, rax
0x140045a36  jz      loc_140045BFE
0x140045a3c  test    dword ptr [rcx+2Ch], 8000000h
0x140045a43  jz      loc_140045BFE
0x140045a49  mov     edx, 1Ch
0x140045a4e  mov     dword ptr [rsp+198h+var_168], esi
0x140045a52  mov     qword ptr [rsp+198h+var_170], rbx
0x140045a57  mov     dword ptr [rsp+198h+AccessState], 3A64h
0x140045a5f  jmp     loc_14004596A
0x140045a64  mov     rax, [rbx]
0x140045a67  mov     rax, [rax+160h]
0x140045a6e  lea     rdx, [rsp+198h+P]
0x140045a73  mov     rcx, rbx
0x140045a76  call    _guard_dispatch_icall
0x140045a7b  mov     rcx, [rax]
0x140045a7e  mov     [rsp+198h+var_F8], rcx
0x140045a86  shr     rcx, 20h
0x140045a8a  cmp     esi, ecx
0x140045a8c  jnb     short loc_140045B07
0x140045a8e  mov     dword ptr [r15+24h], 8
0x140045a96  lock inc dword ptr [rbx+1590h]
0x140045a9d  lea     rax, WPP_GLOBAL_Control
0x140045aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x140045aab  cmp     rcx, rax
0x140045aae  jz      short loc_140045AE6
0x140045ab0  test    dword ptr [rcx+2Ch], 8000000h
0x140045ab7  jz      short loc_140045AE6
0x140045ab9  mov     edx, 1Dh
0x140045abe  mov     dword ptr [rsp+198h+var_168], esi
0x140045ac2  mov     qword ptr [rsp+198h+var_170], rbx
0x140045ac7  mov     dword ptr [rsp+198h+AccessState], 3A7Eh
0x140045acf  lea     r9, aCclfslogfcbphy; "CClfsLogFcbPhysical::DeleteContainer"
0x140045ad6  lea     r8, WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids
0x140045add  mov     rcx, [rcx+18h]
0x140045ae1  call    WPP_SF_slid
0x140045ae6  lea     rdx, [rsp+198h+var_150]; struct _CLFS_CONTAINER_CONTEXT **
0x140045aeb  mov     rcx, [rbx+2C8h]; this
0x140045af2  call    ?ReleaseContainerContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::ReleaseContainerContext(_CLFS_CONTAINER_CONTEXT * *)
0x140045af7  mov     rdx, r13; struct _FILE_OBJECT *
0x140045afa  mov     rcx, rbx; this
0x140045afd  call    ?WrapContainers@CClfsLogFcbPhysical@@AEAAXPEAU_FILE_OBJECT@@@Z; CClfsLogFcbPhysical::WrapContainers(_FILE_OBJECT *)
0x140045b02  jmp     loc_140045BFE
0x140045b07  lea     rcx, [rbx+1F8h]; plsn
0x140045b0e  call    ClfsLsnContainer
0x140045b13  cmp     esi, eax
0x140045b15  jbe     loc_140045BFE
0x140045b1b  mov     [rsp+198h+var_148], 0
0x140045b24  mov     r15, [rsp+198h+var_150]
0x140045b29  mov     r14, [r15+18h]
0x140045b2d  mov     [rsp+198h+var_130], r14
0x140045b32  mov     qword ptr [r15+18h], 0
0x140045b3a  dec     dword ptr [rbx+588h]
0x140045b40  mov     eax, [rbx+588h]
0x140045b46  and     eax, 3FFh
0x140045b4b  mov     r12d, [rbx+rax*4+590h]
0x140045b53  lea     r8, [rsp+198h+var_148]; struct _CLFS_CONTAINER_CONTEXT **
0x140045b58  mov     edx, r12d; unsigned int
0x140045b5b  mov     rcx, [rbx+2C8h]; this
0x140045b62  call    ?AcquireContainerContext@CClfsBaseFile@@QEAAJKPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::AcquireContainerContext(ulong,_CLFS_CONTAINER_CONTEXT * *)
0x140045b67  mov     edi, eax
0x140045b69  mov     [rsp+198h+var_154], eax
0x140045b6d  test    eax, eax
0x140045b6f  jns     short loc_140045B96
0x140045b71  mov     [r15+18h], r14
0x140045b75  xor     r14d, r14d
0x140045b78  mov     [rsp+198h+var_130], r14
0x140045b7d  inc     dword ptr [rbx+588h]
0x140045b83  lea     rdx, [rsp+198h+var_150]; struct _CLFS_CONTAINER_CONTEXT **
0x140045b88  mov     rcx, [rbx+2C8h]; this
0x140045b8f  call    ?ReleaseContainerContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::ReleaseContainerContext(_CLFS_CONTAINER_CONTEXT * *)
0x140045b94  jmp     short loc_140045BFE
0x140045b96  mov     rax, [rsp+198h+var_148]
0x140045b9b  mov     [rax+14h], esi
0x140045b9e  lea     rdx, [rsp+198h+var_148]; struct _CLFS_CONTAINER_CONTEXT **
0x140045ba3  mov     rcx, [rbx+2C8h]; this
0x140045baa  call    ?ReleaseContainerContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::ReleaseContainerContext(_CLFS_CONTAINER_CONTEXT * *)
0x140045baf  mov     edi, eax
0x140045bb1  mov     [rsp+198h+var_154], eax
0x140045bb5  mov     ecx, 3FFh
0x140045bba  and     rsi, rcx
0x140045bbd  mov     [rbx+rsi*4+590h], r12d
0x140045bc5  mov     eax, [rbx+588h]
0x140045bcb  and     rax, rcx
0x140045bce  mov     dword ptr [rbx+rax*4+590h], 0FFFFFFFFh
0x140045bd9  mov     edx, [rsp+198h+var_138]; unsigned int
0x140045bdd  mov     rcx, [rbx+2C8h]; this
0x140045be4  call    ?RemoveContainer@CClfsBaseFilePersisted@@QEAAJK@Z; CClfsBaseFilePersisted::RemoveContainer(ulong)
0x140045be9  mov     rcx, [rbx+2C8h]; this
0x140045bf0  call    ?UnlockImage@CClfsBaseFile@@QEAAXXZ; CClfsBaseFile::UnlockImage(void)
0x140045bf5  mov     [rsp+198h+var_150], 0
0x140045bfe  mov     sil, [rsp+198h+var_158]
0x140045c03  mov     r15b, [rsp+198h+var_157]
0x140045c08  test    edi, edi
0x140045c0a  js      short loc_140045C69
0x140045c0c  test    r14, r14
0x140045c0f  jz      short loc_140045C58
0x140045c11  mov     rax, [rbx+2B8h]
0x140045c18  sub     [rbx+1C8h], rax
0x140045c1f  mov     rcx, rbx; this
0x140045c22  call    ?CalculateAvailableFreeSpace@CClfsLogFcbPhysical@@QEAA_KXZ; CClfsLogFcbPhysical::CalculateAvailableFreeSpace(void)
0x140045c27  mov     [rbx+1D0h], rax
0x140045c2e  mov     rax, [rbx+1C8h]
0x140045c35  mov     [rsp+198h+P], rax
0x140045c3a  mov     [rsp+198h+var_148], 0FFFFFFFFFFFFFFFFh
0x140045c43  lea     r9, [rsp+198h+P]; __int64 *
0x140045c48  lea     r8, [rsp+198h+var_148]; __int64 *
0x140045c4d  mov     rdx, r13; struct _FILE_OBJECT *
  ... truncated ...
```
