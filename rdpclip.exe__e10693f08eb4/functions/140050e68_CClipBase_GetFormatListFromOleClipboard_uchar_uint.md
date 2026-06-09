# CClipBase::GetFormatListFromOleClipboard(uchar * *,uint *)

- ea: `0x140050e68`
- end: `0x1400513da`
- name: `?GetFormatListFromOleClipboard@CClipBase@@IEAAJPEAPEAEPEAI@Z`
- size: `1394`
- prototype: `__int64 __fastcall(CClipBase *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x14003bd80`

## callees

- `0x140004b1c`
- `0x140004cf4`
- `0x1400056c4`
- `0x140005704`
- `0x140005750`
- `0x1400081d0`
- `0x140011054`
- `0x1400186e4`
- `0x140035e34`
- `0x140050e68`
- `0x1400648e8`
- `0x140066dc8`
- `0x140066f80`
- `0x14006b010`

## import_xrefs

- `USER32!IsClipboardFormatAvailable` at `0x14005104f`
- `USER32!IsClipboardFormatAvailable` at `0x14005104f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140050fca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140050fca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400510cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400510db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400510cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400510db`

## string_xrefs

- `0x1400511a9`: `CreateFormatNamePacker failed!`
- `0x1400510a0`: `CreateReader failed!`
- `0x140051039`: `CFileContentsReaderManager::CreateInstance failed!`

## pseudocode

```c
__int64 __fastcall CClipBase::GetFormatListFromOleClipboard(CClipBase *this, unsigned __int8 **a2, unsigned int *a3)
{
  struct CFormatNamePacker *v6; // rsi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v8; // edx
  const char *v9; // rcx
  int Instance; // ebx
  unsigned int v11; // eax
  CFileContentsReaderManager **v12; // r14
  struct IDataObject *v13; // r9
  unsigned int v14; // eax
  int v15; // edx
  const char *v16; // rcx
  BOOL v17; // edx
  struct IFormatNameIdEnum *v18; // rbx
  struct IClipboardLevelCallback *v19; // rsi
  unsigned __int8 v20; // al
  int v21; // edx
  int v22; // ecx
  int v23; // r8d
  unsigned int v24; // eax
  unsigned int v25; // eax
  int v26; // edx
  const char *v27; // rcx
  unsigned int v28; // ebx
  unsigned int v29; // eax
  unsigned __int8 *v30; // rax
  unsigned int v31; // eax
  unsigned int v32; // eax
  __int64 v34; // [rsp+28h] [rbp-38h]
  struct IFormatNameIdEnum *v35[2]; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v36; // [rsp+A8h] [rbp+48h] BYREF
  struct CFormatNamePacker *v37; // [rsp+B8h] [rbp+58h] BYREF

  v36 = 0;
  v37 = 0;
  v35[0] = 0;
  v6 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 193;
    v9 = "pbFormatList";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v9);
LABEL_7:
    Instance = -2147467261;
    goto LABEL_76;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 194;
    v9 = "pcbFormatList";
    goto LABEL_6;
  }
  *a2 = 0;
  *a3 = 0;
  Instance = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IFormatNameIdEnum **))(*((_QWORD *)this + 44) + 48LL))(
               *((_QWORD *)this + 44) + 48LL,
               &IID_IFormatNameIdEnum,
               v35);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        195,
        (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v11,
        (__int64)"QueryInterface (IID_IFormatNameIdEnum) failed!",
        Instance);
    }
    goto LABEL_76;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
  v12 = (CFileContentsReaderManager **)((char *)this + 288);
  if ( *((_QWORD *)this + 36) )
  {
    TCntPtr<CRdpClipMainWnd>::SafeRelease((char *)this + 288);
    *v12 = 0;
    TCntPtr<CRdpWindowTracker>::SafeAddRef((char *)this + 288);
  }
  Instance = CFileContentsReaderManager::CreateInstance(
               *((struct RdpEdpPolicyManager **)this + 102),
               (struct CFileContentsReaderManager **)this + 36);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_35;
    }
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 196;
    v16 = "CFileContentsReaderManager::CreateInstance failed!";
LABEL_34:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
      v14,
      (__int64)v16,
      Instance);
LABEL_35:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
    goto LABEL_74;
  }
  v17 = *((_DWORD *)this + 63) && IsClipboardFormatAvailable(0xFu);
  Instance = CFileContentsReaderManager::CreateReader(*v12, v17, (CClipBase *)((char *)this + 296), v13);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_35;
    }
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 197;
    v16 = "CreateReader failed!";
    goto LABEL_34;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
  v18 = v35[0];
  v19 = (struct IClipboardLevelCallback *)(*(__int64 (__fastcall **)(CClipBase *))(*(_QWORD *)this + 200LL))(this);
  v20 = (*(__int64 (__fastcall **)(CClipBase *))(*(_QWORD *)this + 184LL))(this);
  v21 = *((_DWORD *)this + 198);
  if ( v21 )
    v22 = *((_DWORD *)this + 62);
  else
    v22 = 0;
  if ( v21 )
    v23 = *(_DWORD *)(*((_QWORD *)this + 77) + 48LL);
  else
    v23 = 0;
  Instance = CreateFormatNamePacker(
               &v37,
               *((_DWORD *)this + 61),
               v23,
               *((_DWORD *)this + 47),
               v22,
               *((_DWORD *)this + 63),
               *((_QWORD *)this + 102) != 0,
               v20,
               v19,
               v18);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v34) = Instance;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        198,
        (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v24,
        (__int64)"CreateFormatNamePacker failed!",
        v34);
    }
    v6 = v37;
    goto LABEL_74;
  }
  v6 = v37;
  Instance = (*(__int64 (__fastcall **)(struct CFormatNamePacker *, _QWORD, unsigned int *))(*(_QWORD *)v37 + 8LL))(
               v37,
               0,
               &v36);
  if ( Instance >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v28 = v36;
      v29 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v29, v28);
    }
    v30 = (unsigned __int8 *)PAL_System_MemAlloc(v36);
    *a2 = v30;
    if ( !v30 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v31 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          201,
          (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
          v31,
          (__int64)"BYTE");
      }
      Instance = -2147024882;
      goto LABEL_74;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v32 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v32);
    }
    Instance = (*(__int64 (__fastcall **)(struct CFormatNamePacker *, _QWORD, unsigned int *))(*(_QWORD *)v6 + 8LL))(
                 v6,
                 *a2,
                 &v36);
    if ( Instance >= 0 )
    {
      Instance = 0;
      *a3 = v36;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = RdpWppGetCurrentThreadActivityIdPrefix();
      v26 = 203;
      v27 = "EncodeFormatNames failed.";
      goto LABEL_53;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v25 = RdpWppGetCurrentThreadActivityIdPrefix();
    v26 = 199;
    v27 = "Unable to determine space required for format list!";
LABEL_53:
    LODWORD(v34) = Instance;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v26,
      (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
      v25,
      (__int64)v27,
      v34);
  }
LABEL_74:
  if ( v6 )
    (**(void (__fastcall ***)(struct CFormatNamePacker *, __int64))v6)(v6, 1);
LABEL_76:
  TCntPtr<IRdpHintApiEventSink>::SafeRelease(v35);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140050e68  mov     [rsp-38h+arg_0], rbx
0x140050e6d  push    rbp
0x140050e6e  push    rsi
0x140050e6f  push    rdi
0x140050e70  push    r12
0x140050e72  push    r13
0x140050e74  push    r14
0x140050e76  push    r15
0x140050e78  mov     rbp, rsp
0x140050e7b  sub     rsp, 60h
0x140050e7f  xor     r14d, r14d
0x140050e82  mov     r13, r8
0x140050e85  mov     [rbp+arg_8], r14d
0x140050e89  mov     r15, rdx
0x140050e8c  mov     [rbp+arg_18], r14
0x140050e90  mov     rdi, rcx
0x140050e93  mov     [rbp+var_10], r14
0x140050e97  mov     esi, r14d
0x140050e9a  test    rdx, rdx
0x140050e9d  jnz     short loc_140050EF8
0x140050e9f  mov     rax, cs:WPP_GLOBAL_Control
0x140050ea6  lea     rdi, WPP_GLOBAL_Control
0x140050ead  cmp     rax, rdi
0x140050eb0  jz      short loc_140050EEE
0x140050eb2  test    byte ptr [rax+1Ch], 8
0x140050eb6  jz      short loc_140050EEE
0x140050eb8  cmp     byte ptr [rax+19h], 2
0x140050ebc  jb      short loc_140050EEE
0x140050ebe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140050ec3  mov     edx, 0C1h
0x140050ec8  lea     rcx, aPbformatlist; "pbFormatList"
0x140050ecf  mov     qword ptr [rsp+60h+var_40], rcx
0x140050ed4  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140050edb  mov     rcx, cs:WPP_GLOBAL_Control
0x140050ee2  mov     r9d, eax
0x140050ee5  mov     rcx, [rcx+10h]
0x140050ee9  call    WPP_SF_Ds
0x140050eee  mov     ebx, 80004003h
0x140050ef3  jmp     loc_1400513B7
0x140050ef8  test    r13, r13
0x140050efb  jnz     short loc_140050F2F
0x140050efd  mov     rax, cs:WPP_GLOBAL_Control
0x140050f04  lea     rdi, WPP_GLOBAL_Control
0x140050f0b  cmp     rax, rdi
0x140050f0e  jz      short loc_140050EEE
0x140050f10  test    byte ptr [rax+1Ch], 8
0x140050f14  jz      short loc_140050EEE
0x140050f16  cmp     byte ptr [rax+19h], 2
0x140050f1a  jb      short loc_140050EEE
0x140050f1c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140050f21  mov     edx, 0C2h
0x140050f26  lea     rcx, aPcbformatlist; "pcbFormatList"
0x140050f2d  jmp     short loc_140050ECF
0x140050f2f  mov     [rdx], r14
0x140050f32  lea     rdx, IID_IFormatNameIdEnum
0x140050f39  mov     [r8], r14d
0x140050f3c  lea     r8, [rbp+var_10]
0x140050f40  mov     rcx, [rcx+160h]
0x140050f47  add     rcx, 30h ; '0'
0x140050f4b  mov     rax, [rcx]
0x140050f4e  mov     rax, [rax]
0x140050f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050f56  mov     ebx, eax
0x140050f58  test    eax, eax
0x140050f5a  jns     short loc_140050FC0
0x140050f5c  mov     rax, cs:WPP_GLOBAL_Control
0x140050f63  lea     rdi, WPP_GLOBAL_Control
0x140050f6a  cmp     rax, rdi
0x140050f6d  jz      loc_1400513B7
0x140050f73  test    byte ptr [rax+1Ch], 8
0x140050f77  jz      loc_1400513B7
0x140050f7d  cmp     byte ptr [rax+19h], 2
0x140050f81  jb      loc_1400513B7
0x140050f87  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140050f8c  lea     rcx, aQueryinterface_2; "QueryInterface (IID_IFormatNameIdEnum) "...
0x140050f93  mov     dword ptr [rsp+60h+var_38], ebx
0x140050f97  mov     qword ptr [rsp+60h+var_40], rcx
0x140050f9c  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140050fa3  mov     rcx, cs:WPP_GLOBAL_Control
0x140050faa  mov     edx, 0C3h
0x140050faf  mov     r9d, eax
0x140050fb2  mov     rcx, [rcx+10h]
0x140050fb6  call    WPP_SF_DsD
0x140050fbb  jmp     loc_1400513B7
0x140050fc0  lea     r12, [rdi+2C8h]
0x140050fc7  mov     rcx, r12; lpCriticalSection
0x140050fca  call    cs:__imp_EnterCriticalSection
0x140050fd0  lea     r14, [rdi+120h]
0x140050fd7  cmp     [r14], rsi
0x140050fda  jz      short loc_140050FEF
0x140050fdc  mov     rcx, r14
0x140050fdf  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x140050fe4  mov     rcx, r14
0x140050fe7  mov     [r14], rsi
0x140050fea  call    ?SafeAddRef@?$TCntPtr@VCRdpWindowTracker@@@@AEAAXXZ; TCntPtr<CRdpWindowTracker>::SafeAddRef(void)
0x140050fef  mov     rcx, [rdi+330h]; struct RdpEdpPolicyManager *
0x140050ff6  mov     rdx, r14; struct CFileContentsReaderManager **
0x140050ff9  call    ?CreateInstance@CFileContentsReaderManager@@SAJPEAVRdpEdpPolicyManager@@PEAPEAV1@@Z; CFileContentsReaderManager::CreateInstance(RdpEdpPolicyManager *,CFileContentsReaderManager * *)
0x140050ffe  mov     ebx, eax
0x140051000  test    eax, eax
0x140051002  jns     short loc_140051042
0x140051004  mov     rax, cs:WPP_GLOBAL_Control
0x14005100b  lea     rdi, WPP_GLOBAL_Control
0x140051012  cmp     rax, rdi
0x140051015  jz      loc_1400510CA
0x14005101b  test    byte ptr [rax+1Ch], 8
0x14005101f  jz      loc_1400510CA
0x140051025  cmp     byte ptr [rax+19h], 2
0x140051029  jb      loc_1400510CA
0x14005102f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051034  mov     edx, 0C4h
0x140051039  lea     rcx, aCfilecontentsr; "CFileContentsReaderManager::CreateInsta"...
0x140051040  jmp     short loc_1400510A7
0x140051042  cmp     [rdi+0FCh], esi
0x140051048  jz      short loc_140051060
0x14005104a  mov     ecx, 0Fh; format
0x14005104f  call    cs:__imp_IsClipboardFormatAvailable
0x140051055  test    eax, eax
0x140051057  jz      short loc_140051060
0x140051059  mov     edx, 1
0x14005105e  jmp     short loc_140051062
0x140051060  xor     edx, edx; int
0x140051062  mov     rcx, [r14]; this
0x140051065  lea     r8, [rdi+128h]; struct CHdropToFgdConverter *
0x14005106c  call    ?CreateReader@CFileContentsReaderManager@@QEAAJHPEAVCHdropToFgdConverter@@PEAUIDataObject@@@Z; CFileContentsReaderManager::CreateReader(int,CHdropToFgdConverter *,IDataObject *)
0x140051071  mov     ebx, eax
0x140051073  test    eax, eax
0x140051075  jns     short loc_1400510D8
0x140051077  mov     rax, cs:WPP_GLOBAL_Control
0x14005107e  lea     rdi, WPP_GLOBAL_Control
0x140051085  cmp     rax, rdi
0x140051088  jz      short loc_1400510CA
0x14005108a  test    byte ptr [rax+1Ch], 8
0x14005108e  jz      short loc_1400510CA
0x140051090  cmp     byte ptr [rax+19h], 2
0x140051094  jb      short loc_1400510CA
0x140051096  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005109b  mov     edx, 0C5h
0x1400510a0  lea     rcx, aCreatereaderFa; "CreateReader failed!"
0x1400510a7  mov     dword ptr [rsp+60h+var_38], ebx
0x1400510ab  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x1400510b2  mov     qword ptr [rsp+60h+var_40], rcx
0x1400510b7  mov     r9d, eax
0x1400510ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400510c1  mov     rcx, [rcx+10h]
0x1400510c5  call    WPP_SF_DsD
0x1400510ca  mov     rcx, r12; lpCriticalSection
0x1400510cd  call    cs:__imp_LeaveCriticalSection
0x1400510d3  jmp     loc_14005139F
0x1400510d8  mov     rcx, r12; lpCriticalSection
0x1400510db  call    cs:__imp_LeaveCriticalSection
0x1400510e1  mov     rax, [rdi]
0x1400510e4  mov     rcx, rdi
0x1400510e7  mov     rbx, [rbp+var_10]
0x1400510eb  mov     rax, [rax+0C8h]
0x1400510f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400510f7  mov     rcx, [rdi]
0x1400510fa  mov     rsi, rax
0x1400510fd  mov     rax, [rcx+0B8h]
0x140051104  mov     rcx, rdi
0x140051107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005110c  mov     edx, [rdi+318h]
0x140051112  xor     r9d, r9d
0x140051115  cmp     [rdi+330h], r9
0x14005111c  mov     r10b, al
0x14005111f  mov     r11d, [rdi+0FCh]
0x140051126  setnz   r9b
0x14005112a  test    edx, edx
0x14005112c  jz      short loc_140051136
0x14005112e  mov     ecx, [rdi+0F8h]
0x140051134  jmp     short loc_140051138
0x140051136  xor     ecx, ecx
0x140051138  test    edx, edx
0x14005113a  jz      short loc_140051149
0x14005113c  mov     rax, [rdi+268h]
0x140051143  mov     r8d, [rax+30h]
0x140051147  jmp     short loc_14005114C
0x140051149  xor     r8d, r8d; int
0x14005114c  mov     edx, [rdi+0F4h]; int
0x140051152  mov     [rsp+60h+var_18], rbx; struct IFormatNameIdEnum *
0x140051157  mov     [rsp+60h+var_20], rsi; struct IClipboardLevelCallback *
0x14005115c  mov     [rsp+60h+var_28], r10b; unsigned __int8
0x140051161  mov     [rsp+60h+var_30], r9d; int
0x140051166  mov     r9d, [rdi+0BCh]; int
0x14005116d  mov     dword ptr [rsp+60h+var_38], r11d; int
0x140051172  mov     [rsp+60h+var_40], ecx; int
0x140051176  lea     rcx, [rbp+arg_18]; struct CFormatNamePacker **
0x14005117a  call    ?CreateFormatNamePacker@@YAJPEAPEAVCFormatNamePacker@@HHHHHHEPEAVIClipboardLevelCallback@@PEAVIFormatNameIdEnum@@@Z; CreateFormatNamePacker(CFormatNamePacker * *,int,int,int,int,int,int,uchar,IClipboardLevelCallback *,IFormatNameIdEnum *)
0x14005117f  mov     ebx, eax
0x140051181  test    eax, eax
0x140051183  jns     short loc_1400511E1
0x140051185  mov     rax, cs:WPP_GLOBAL_Control
0x14005118c  lea     rdi, WPP_GLOBAL_Control
0x140051193  cmp     rax, rdi
0x140051196  jz      short loc_1400511D8
0x140051198  test    byte ptr [rax+1Ch], 8
0x14005119c  jz      short loc_1400511D8
0x14005119e  cmp     byte ptr [rax+19h], 2
0x1400511a2  jb      short loc_1400511D8
0x1400511a4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400511a9  lea     rcx, aCreateformatna; "CreateFormatNamePacker failed!"
0x1400511b0  mov     dword ptr [rsp+60h+var_38], ebx
0x1400511b4  mov     qword ptr [rsp+60h+var_40], rcx
0x1400511b9  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x1400511c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400511c7  mov     edx, 0C6h
0x1400511cc  mov     r9d, eax
0x1400511cf  mov     rcx, [rcx+10h]
0x1400511d3  call    WPP_SF_DsD
0x1400511d8  mov     rsi, [rbp+arg_18]
0x1400511dc  jmp     loc_14005139F
0x1400511e1  mov     rsi, [rbp+arg_18]
0x1400511e5  lea     r8, [rbp+arg_8]
0x1400511e9  xor     edx, edx
0x1400511eb  mov     rcx, rsi
0x1400511ee  mov     rax, [rsi]
0x1400511f1  mov     rax, [rax+8]
0x1400511f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400511fa  mov     ebx, eax
0x1400511fc  test    eax, eax
0x1400511fe  jns     short loc_140051264
0x140051200  mov     rax, cs:WPP_GLOBAL_Control
0x140051207  lea     rdi, WPP_GLOBAL_Control
0x14005120e  cmp     rax, rdi
0x140051211  jz      loc_14005139F
0x140051217  test    byte ptr [rax+1Ch], 8
0x14005121b  jz      loc_14005139F
0x140051221  cmp     byte ptr [rax+19h], 2
0x140051225  jb      loc_14005139F
0x14005122b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051230  mov     edx, 0C7h
0x140051235  lea     rcx, aUnableToDeterm; "Unable to determine space required for "...
0x14005123c  mov     dword ptr [rsp+60h+var_38], ebx
0x140051240  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140051247  mov     qword ptr [rsp+60h+var_40], rcx
0x14005124c  mov     r9d, eax
0x14005124f  mov     rcx, cs:WPP_GLOBAL_Control
0x140051256  mov     rcx, [rcx+10h]
0x14005125a  call    WPP_SF_DsD
0x14005125f  jmp     loc_14005139F
0x140051264  mov     rax, cs:WPP_GLOBAL_Control
0x14005126b  lea     rdi, WPP_GLOBAL_Control
0x140051272  cmp     rax, rdi
0x140051275  jz      short loc_1400512AE
0x140051277  test    byte ptr [rax+1Ch], 1
0x14005127b  jz      short loc_1400512AE
0x14005127d  cmp     byte ptr [rax+19h], 5
0x140051281  jb      short loc_1400512AE
0x140051283  mov     ebx, [rbp+arg_8]
0x140051286  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005128b  mov     rcx, cs:WPP_GLOBAL_Control
0x140051292  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140051299  mov     edx, 0C8h
0x14005129e  mov     [rsp+60h+var_40], ebx
0x1400512a2  mov     r9d, eax
0x1400512a5  mov     rcx, [rcx+10h]
0x1400512a9  call    WPP_SF_Dd
0x1400512ae  mov     ecx, [rbp+arg_8]
0x1400512b1  call    PAL_System_MemAlloc
0x1400512b6  mov     [r15], rax
0x1400512b9  test    rax, rax
0x1400512bc  jnz     short loc_140051310
0x1400512be  mov     rax, cs:WPP_GLOBAL_Control
0x1400512c5  cmp     rax, rdi
0x1400512c8  jz      short loc_140051306
0x1400512ca  test    byte ptr [rax+1Ch], 8
0x1400512ce  jz      short loc_140051306
0x1400512d0  cmp     byte ptr [rax+19h], 2
0x1400512d4  jb      short loc_140051306
0x1400512d6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400512db  lea     rcx, aByte; "BYTE"
0x1400512e2  mov     edx, 0C9h
0x1400512e7  mov     qword ptr [rsp+60h+var_40], rcx
0x1400512ec  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x1400512f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400512fa  mov     r9d, eax
0x1400512fd  mov     rcx, [rcx+10h]
0x140051301  call    WPP_SF_Ds
0x140051306  mov     ebx, 8007000Eh
0x14005130b  jmp     loc_14005139F
0x140051310  mov     rax, cs:WPP_GLOBAL_Control
0x140051317  cmp     rax, rdi
0x14005131a  jz      short loc_14005134C
0x14005131c  test    byte ptr [rax+1Ch], 1
0x140051320  jz      short loc_14005134C
0x140051322  cmp     byte ptr [rax+19h], 5
0x140051326  jb      short loc_14005134C
0x140051328  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005132d  mov     rcx, cs:WPP_GLOBAL_Control
0x140051334  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x14005133b  mov     edx, 0CAh
0x140051340  mov     r9d, eax
0x140051343  mov     rcx, [rcx+10h]
0x140051347  call    WPP_SF_d
0x14005134c  mov     rax, [rsi]
0x14005134f  lea     r8, [rbp+arg_8]
0x140051353  mov     rdx, [r15]
0x140051356  mov     rcx, rsi
0x140051359  mov     rax, [rax+8]
0x14005135d  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
