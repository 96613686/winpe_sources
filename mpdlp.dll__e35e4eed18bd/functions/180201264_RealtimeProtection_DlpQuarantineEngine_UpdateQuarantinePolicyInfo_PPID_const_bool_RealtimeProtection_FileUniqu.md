# RealtimeProtection::DlpQuarantineEngine::UpdateQuarantinePolicyInfo(PPID const &,bool,RealtimeProtection::FileUniqueId const &,RealtimeProtection::_DlpQuarantinePolicyInformation const &)

- ea: `0x180201264`
- end: `0x180201703`
- name: `?UpdateQuarantinePolicyInfo@DlpQuarantineEngine@RealtimeProtection@@QEAAJAEBUPPID@@_NAEBVFileUniqueId@2@AEBU_DlpQuarantinePolicyInformation@2@@Z`
- size: `1183`
- prototype: `int(RealtimeProtection::DlpQuarantineEngine *__hidden this, const struct PPID *, bool, const struct RealtimeProtection::FileUniqueId *, const struct RealtimeProtection::_DlpQuarantinePolicyInformation *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801e826c`

## callees

- `0x180049b34`
- `0x18004b3bc`
- `0x18006b998`
- `0x18006bbd0`
- `0x180080030`
- `0x1800809d0`
- `0x180088248`
- `0x18009351c`
- `0x180094e70`
- `0x18010cb40`
- `0x1801405f4`
- `0x18016a574`
- `0x180179e04`
- `0x1801fcdd4`
- `0x180201264`
- `0x18023a310`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180201366`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1802013fe`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1802016d9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180201366`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1802013fe`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1802016d9`
- `KERNEL32!CompareFileTime` at `0x1802013ea`
- `KERNEL32!CompareFileTime` at `0x1802013ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RealtimeProtection::DlpQuarantineEngine::UpdateQuarantinePolicyInfo(
        RealtimeProtection::DlpQuarantineEngine *this,
        const FILETIME *a2,
        char a3,
        const struct RealtimeProtection::FileUniqueId *a4,
        const struct RealtimeProtection::_DlpQuarantinePolicyInformation *a5)
{
  __int64 v8; // rbx
  unsigned int v9; // r15d
  PVOID *v10; // rcx
  __int64 v12; // rax
  __int64 v13; // rsi
  const FILETIME *v14; // r8
  _QWORD *v15; // r9
  _QWORD *v16; // r13
  const struct RealtimeProtection::_DlpQuarantinePolicyInformation *v17; // r9
  unsigned __int64 v18; // rdx
  const wchar_t *v19; // r8
  int PolicyInfoFromRuleId; // eax
  struct DlpPolicyInfo *v21; // rdx
  _QWORD *v22; // rcx
  int v23; // edx
  int v24; // edi
  _QWORD *v25; // rbx
  _QWORD *v26; // rcx
  _QWORD *v27; // rax
  _QWORD *v28; // r8
  PSRWLOCK SRWLock; // [rsp+D8h] [rbp-78h] BYREF
  char v31; // [rsp+E0h] [rbp-70h]
  __int64 v32; // [rsp+E8h] [rbp-68h] BYREF
  _BYTE v33[32]; // [rsp+F0h] [rbp-60h] BYREF
  char v34; // [rsp+110h] [rbp-40h]
  __int128 v35; // [rsp+118h] [rbp-38h] BYREF
  __int64 v36; // [rsp+128h] [rbp-28h]
  _DWORD v37[16]; // [rsp+130h] [rbp-20h] BYREF
  _DWORD v38[136]; // [rsp+170h] [rbp+20h] BYREF

  LODWORD(v8) = (_DWORD)a5;
  v9 = 0;
  if ( *((_DWORD *)this + 40) != 3 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
        *((unsigned int *)this + 40));
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
      WPP_SF_d(v10[2], 29, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, 2147947423LL);
    return 2147947423LL;
  }
  CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>(
    &SRWLock,
    (char *)this + 128);
  v32 = 0;
  std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::_DlpQuarantineItem,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::_DlpQuarantineItem>>,0>>::find(
    this,
    &v32,
    a4);
  v12 = v32;
  if ( v32 == *((_QWORD *)this + 1) )
  {
    if ( v31 )
      ReleaseSRWLockExclusive(SRWLock);
    return 2147943568LL;
  }
  v13 = v32 + 16;
  v14 = (const FILETIME *)(v32 + 624);
  *(_BYTE *)(v32 + 1906) = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v15 = (_QWORD *)(v12 + 272);
    if ( *(_QWORD *)(v12 + 296) > 7u )
      v15 = (_QWORD *)*v15;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, v15);
    v14 = (const FILETIME *)(v13 + 608);
  }
  if ( a3 && (v14[1].dwLowDateTime != a2[1].dwLowDateTime || CompareFileTime(v14, a2)) )
  {
    if ( v31 )
      ReleaseSRWLockExclusive(SRWLock);
    return 0;
  }
  v16 = (_QWORD *)(v13 + 792);
  RealtimeProtection::_DlpQuarantinePolicyInformation::operator=(v13 + 792, a5, v14);
  if ( *((_QWORD *)a5 + 2) && (!*((_QWORD *)a5 + 14) || !*((_QWORD *)a5 + 10)) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v17 = a5;
      if ( *((_QWORD *)a5 + 3) > 7u )
        v17 = *(const struct RealtimeProtection::_DlpQuarantinePolicyInformation **)a5;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, v17);
    }
    memset(&v38[1], 0, 0x214u);
    v38[0] = 257;
    v19 = (const wchar_t *)a5;
    if ( *((_QWORD *)a5 + 3) > 7u )
      v19 = *(const wchar_t **)a5;
    PolicyInfoFromRuleId = StringCbCopyW((wchar_t *)&v38[31] + 1, v18, v19);
    if ( PolicyInfoFromRuleId >= 0 )
    {
      PolicyInfoFromRuleId = EndpointDlp::Client::GetPolicyInfoFromRuleId((EndpointDlp::Client *)v38, v21);
      v9 = PolicyInfoFromRuleId;
      if ( PolicyInfoFromRuleId >= 0 )
      {
        std::wstring::assign((void *)(v13 + 888), &v38[101]);
        std::wstring::assign((void *)(v13 + 856), (char *)&v38[68] + 2);
        goto LABEL_49;
      }
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_47;
      if ( *((_QWORD *)a5 + 3) > 7u )
        v8 = *(_QWORD *)a5;
      v23 = 33;
    }
    else
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_47;
      if ( *((_QWORD *)a5 + 3) > 7u )
        v8 = *(_QWORD *)a5;
      v23 = 32;
    }
    WPP_SF_Sd(v22[2], v23, (unsigned int)&WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, v8, PolicyInfoFromRuleId);
LABEL_47:
    v9 = 0;
  }
LABEL_49:
  if ( *(_BYTE *)(v13 + 115) )
  {
    v24 = 10;
    if ( *(_DWORD *)(v13 + 68) == 2 )
    {
      v24 = 0;
    }
    else if ( *(_DWORD *)(v13 + 68) == 3 )
    {
      v24 = 1;
    }
    v25 = (_QWORD *)(v13 + (-(__int64)(*(_BYTE *)(v13 + 114) != 0) & 0xFFFFFFFFFFFFFFC0uLL) + 432);
    memset(v37, 0, sizeof(v37));
    v37[0] = 263;
    v37[1] = 3;
    v37[2] = 2;
    v35 = 0;
    v36 = 0;
    v34 = 0;
    v26 = (_QWORD *)(v13 + 664);
    if ( *(_QWORD *)(v13 + 688) > 7u )
      v26 = (_QWORD *)*v26;
    if ( v25[3] > 7u )
      v25 = (_QWORD *)*v25;
    v27 = (_QWORD *)(v13 + 256);
    if ( *(_QWORD *)(v13 + 280) > 7u )
      v27 = (_QWORD *)*v27;
    v28 = (_QWORD *)(v13 + 824);
    if ( *(_QWORD *)(v13 + 848) > 7u )
      v28 = (_QWORD *)*v28;
    if ( *(_QWORD *)(v13 + 816) > 7u )
      v16 = (_QWORD *)*v16;
    RealtimeProtection::DlpEngineTelemetry::GenerateDlpTelemetryEvent(
      (unsigned int)&v35,
      (_DWORD)v16,
      (_DWORD)v28,
      3,
      v24,
      0,
      (__int64)v27,
      (__int64)v25,
      (__int64)v26,
      v13 + 608,
      *(_DWORD *)(v13 + 620),
      0,
      0,
      0,
      (__int64)v37,
      0,
      (__int64)v33,
      0,
      (__int64)&qword_18025C818,
      (__int64)&qword_18025C818,
      1,
      (__int64)&qword_18025C818,
      0,
      (__int64)&qword_18025C818,
      (__int64)&qword_18025C818,
      0);
    if ( v34 )
      std::string::`scalar deleting destructor'(v33);
    RealtimeProtection::DlpEngineTelemetry::SendDlpTelemetryEvent(&v35);
    std::vector<RealtimeProtection::DlpEngineTelemetry::DlpTelemetryEvent>::_Tidy(&v35);
  }
  if ( v31 )
    ReleaseSRWLockExclusive(SRWLock);
  return v9;
}

```

## disassembly

```asm
0x180201264  push    rbp
0x180201266  push    rbx
0x180201267  push    rsi
0x180201268  push    rdi
0x180201269  push    r12
0x18020126b  push    r13
0x18020126d  push    r15
0x18020126f  lea     rbp, [rsp-250h]
0x180201277  sub     rsp, 3A0h
0x18020127e  mov     rax, cs:__security_cookie
0x180201285  xor     rax, rsp
0x180201288  mov     [rbp+280h+var_40], rax
0x18020128f  mov     rdi, r9
0x180201292  mov     [rbp+280h+var_300], r8b
0x180201296  mov     r13, rdx
0x180201299  mov     rsi, rcx
0x18020129c  mov     rbx, [rbp+280h+arg_20]
0x1802012a3  xor     r15d, r15d
0x1802012a6  mov     eax, [rcx+0A0h]
0x1802012ac  nop
0x1802012ad  cmp     eax, 3
0x1802012b0  jz      short loc_18020132A
0x1802012b2  lea     rdi, WPP_GLOBAL_Control
0x1802012b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1802012c0  cmp     rcx, rdi
0x1802012c3  jz      short loc_1802012F5
0x1802012c5  test    byte ptr [rcx+1Ch], 10h
0x1802012c9  jz      short loc_1802012F5
0x1802012cb  mov     r9d, [rsi+0A0h]
0x1802012d2  nop
0x1802012d3  lea     edx, [r15+1Ch]
0x1802012d7  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x1802012de  mov     rcx, cs:WPP_GLOBAL_Control
0x1802012e5  mov     rcx, [rcx+10h]
0x1802012e9  call    WPP_SF_d
0x1802012ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1802012f5  mov     ebx, 8007139Fh
0x1802012fa  cmp     rcx, rdi
0x1802012fd  jz      short loc_180201323
0x1802012ff  mov     r12d, 1
0x180201305  test    [rcx+1Ch], r12b
0x180201309  jz      short loc_180201323
0x18020130b  lea     edx, [r12+1Ch]
0x180201310  mov     r9d, ebx
0x180201313  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x18020131a  mov     rcx, [rcx+10h]
0x18020131e  call    WPP_SF_d
0x180201323  mov     eax, ebx
0x180201325  jmp     loc_1802016E2
0x18020132a  lea     rdx, [rcx+80h]
0x180201331  lea     rcx, [rbp+280h+SRWLock]
0x180201335  call    ??0?$CGenericAutoLock@U?$CMpWriteLockFunctor@VCMpSRWLock@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@AEAVCMpSRWLock@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>(CommonUtil::CMpSRWLock &,CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::ENUM_LOCK_INITIAL_STATE)
0x18020133a  nop
0x18020133b  mov     [rbp+280h+var_2E8], 0
0x180201343  mov     r8, rdi
0x180201346  lea     rdx, [rbp+280h+var_2E8]
0x18020134a  mov     rcx, rsi
0x18020134d  call    ?find@?$_Hash@V?$_Umap_traits@VFileUniqueId@RealtimeProtection@@U_DlpQuarantineItem@2@V?$_Uhash_compare@VFileUniqueId@RealtimeProtection@@UFileUniqueIdHasher@2@UFileUniqueIdComparer@2@@std@@V?$allocator@U?$pair@$$CBVFileUniqueId@RealtimeProtection@@U_DlpQuarantineItem@2@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVFileUniqueId@RealtimeProtection@@U_DlpQuarantineItem@2@@std@@@std@@@std@@@2@AEBVFileUniqueId@RealtimeProtection@@@Z; std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::_DlpQuarantineItem,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::_DlpQuarantineItem>>,0>>::find(RealtimeProtection::FileUniqueId const &)
0x180201352  mov     rax, [rbp+280h+var_2E8]
0x180201356  cmp     rax, [rsi+8]
0x18020135a  jnz     short loc_180201376
0x18020135c  cmp     [rbp+280h+var_2F0], 0
0x180201360  jz      short loc_18020136C
0x180201362  mov     rcx, [rbp+280h+SRWLock]; SRWLock
0x180201366  call    cs:__imp_ReleaseSRWLockExclusive
0x18020136c  mov     eax, 80070490h
0x180201371  jmp     loc_1802016E2
0x180201376  lea     rsi, [rax+10h]
0x18020137a  lea     r8, [rsi+260h]
0x180201381  mov     r12d, 1
0x180201387  mov     [rsi+762h], r12b
0x18020138e  lea     rdi, WPP_GLOBAL_Control
0x180201395  mov     rcx, cs:WPP_GLOBAL_Control
0x18020139c  cmp     rcx, rdi
0x18020139f  jz      short loc_1802013D4
0x1802013a1  test    byte ptr [rcx+1Ch], 4
0x1802013a5  jz      short loc_1802013D4
0x1802013a7  lea     r9, [rsi+100h]
0x1802013ae  cmp     qword ptr [r9+18h], 7
0x1802013b3  jbe     short loc_1802013B8
0x1802013b5  mov     r9, [r9]
0x1802013b8  mov     edx, 1Eh
0x1802013bd  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x1802013c4  mov     rcx, [rcx+10h]
0x1802013c8  call    WPP_SF_S
0x1802013cd  lea     r8, [rsi+260h]
0x1802013d4  cmp     [rbp+280h+var_300], 0
0x1802013d8  jz      short loc_18020140B
0x1802013da  mov     eax, [r13+8]
0x1802013de  cmp     [r8+8], eax
0x1802013e2  jnz     short loc_1802013F4
0x1802013e4  mov     rdx, r13; lpFileTime2
0x1802013e7  mov     rcx, r8; lpFileTime1
0x1802013ea  call    cs:__imp_CompareFileTime
0x1802013f0  test    eax, eax
0x1802013f2  jz      short loc_18020140B
0x1802013f4  cmp     [rbp+280h+var_2F0], 0
0x1802013f8  jz      short loc_180201404
0x1802013fa  mov     rcx, [rbp+280h+SRWLock]; SRWLock
0x1802013fe  call    cs:__imp_ReleaseSRWLockExclusive
0x180201404  xor     eax, eax
0x180201406  jmp     loc_1802016E2
0x18020140b  lea     r13, [rsi+318h]
0x180201412  mov     rdx, rbx
0x180201415  mov     rcx, r13
0x180201418  call    ??4_DlpQuarantinePolicyInformation@RealtimeProtection@@QEAAAEAU01@AEBU01@@Z; RealtimeProtection::_DlpQuarantinePolicyInformation::operator=(RealtimeProtection::_DlpQuarantinePolicyInformation const &)
0x18020141d  xor     eax, eax
0x18020141f  cmp     [rbx+10h], rax
0x180201423  jz      loc_180201538
0x180201429  cmp     [rbx+70h], rax
0x18020142d  jz      short loc_180201439
0x18020142f  cmp     [rbx+50h], rax
0x180201433  jnz     loc_180201538
0x180201439  mov     rcx, cs:WPP_GLOBAL_Control
0x180201440  cmp     rcx, rdi
0x180201443  jz      short loc_18020146D
0x180201445  test    byte ptr [rcx+1Ch], 4
0x180201449  jz      short loc_18020146D
0x18020144b  mov     r9, rbx
0x18020144e  cmp     qword ptr [rbx+18h], 7
0x180201453  jbe     short loc_180201458
0x180201455  mov     r9, [rbx]
0x180201458  mov     edx, 1Fh
0x18020145d  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x180201464  mov     rcx, [rcx+10h]
0x180201468  call    WPP_SF_S
0x18020146d  xor     edx, edx; Val
0x18020146f  mov     r8d, 214h; Size
0x180201475  lea     rcx, [rbp+280h+var_25C]; void *
0x180201479  call    memset
0x18020147e  mov     [rbp+280h+var_260], 101h
0x180201485  mov     r8, rbx
0x180201488  cmp     qword ptr [rbx+18h], 7
0x18020148d  jbe     short loc_180201492
0x18020148f  mov     r8, [rbx]; wchar_t *
0x180201492  lea     rcx, [rbp+280h+var_1E2]; wchar_t *
0x180201499  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18020149e  test    eax, eax
0x1802014a0  jns     short loc_1802014C5
0x1802014a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1802014a9  cmp     rcx, rdi
0x1802014ac  jz      short loc_18020150D
0x1802014ae  test    [rcx+1Ch], r12b
0x1802014b2  jz      short loc_18020150D
0x1802014b4  cmp     qword ptr [rbx+18h], 7
0x1802014b9  jbe     short loc_1802014BE
0x1802014bb  mov     rbx, [rbx]
0x1802014be  mov     edx, 20h ; ' '
0x1802014c3  jmp     short loc_1802014F6
0x1802014c5  lea     rcx, [rbp+280h+var_260]; this
0x1802014c9  call    ?GetPolicyInfoFromRuleId@Client@EndpointDlp@@YAJPEAUDlpPolicyInfo@@@Z; EndpointDlp::Client::GetPolicyInfoFromRuleId(DlpPolicyInfo *)
0x1802014ce  mov     r15d, eax
0x1802014d1  test    eax, eax
0x1802014d3  jns     short loc_180201512
0x1802014d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1802014dc  cmp     rcx, rdi
0x1802014df  jz      short loc_18020150D
0x1802014e1  test    [rcx+1Ch], r12b
0x1802014e5  jz      short loc_18020150D
0x1802014e7  cmp     qword ptr [rbx+18h], 7
0x1802014ec  jbe     short loc_1802014F1
0x1802014ee  mov     rbx, [rbx]
0x1802014f1  mov     edx, 21h ; '!'
0x1802014f6  mov     [rsp+3D0h+var_3B0], eax
0x1802014fa  mov     r9, rbx
0x1802014fd  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x180201504  mov     rcx, [rcx+10h]
0x180201508  call    WPP_SF_Sd
0x18020150d  xor     r15d, r15d
0x180201510  jmp     short loc_180201538
0x180201512  lea     rcx, [rsi+378h]; void *
0x180201519  lea     rdx, [rbp+280h+Src]; Src
0x180201520  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180201525  lea     rcx, [rsi+358h]; void *
0x18020152c  lea     rdx, [rbp+280h+var_14E]; Src
0x180201533  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180201538  cmp     byte ptr [rsi+73h], 0
0x18020153c  jz      loc_1802016CF
0x180201542  mov     edi, 0Ah
0x180201547  cmp     dword ptr [rsi+44h], 2
0x18020154b  jnz     short loc_180201551
0x18020154d  xor     edi, edi
0x18020154f  jmp     short loc_180201559
0x180201551  cmp     dword ptr [rsi+44h], 3
0x180201555  cmovz   edi, r12d
0x180201559  mov     al, [rsi+72h]
0x18020155c  neg     al
0x18020155e  sbb     rbx, rbx
0x180201561  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180201565  add     rbx, 1B0h
0x18020156c  add     rbx, rsi
0x18020156f  xor     edx, edx; Val
0x180201571  lea     r8d, [rdx+40h]; Size
0x180201575  lea     rcx, [rbp+280h+var_2A0]; void *
0x180201579  call    memset
0x18020157e  mov     [rbp+280h+var_2A0], 107h
0x180201585  mov     r11d, 3
0x18020158b  mov     [rbp+280h+var_29C], r11d
0x18020158f  mov     [rbp+280h+var_298], 2
0x180201596  xorps   xmm0, xmm0
0x180201599  xor     eax, eax
0x18020159b  movups  [rbp+280h+var_2B8], xmm0
0x18020159f  mov     [rbp+280h+var_2A8], rax
0x1802015a3  mov     [rbp+280h+var_2C0], al
0x1802015a6  lea     r9, [rsi+260h]
0x1802015ad  mov     edx, [r9+0Ch]
0x1802015b1  lea     rcx, [r9+38h]
0x1802015b5  cmp     qword ptr [rcx+18h], 7
0x1802015ba  jbe     short loc_1802015BF
0x1802015bc  mov     rcx, [rcx]
0x1802015bf  cmp     qword ptr [rbx+18h], 7
0x1802015c4  jbe     short loc_1802015C9
0x1802015c6  mov     rbx, [rbx]
0x1802015c9  lea     rax, [rsi+100h]
0x1802015d0  cmp     qword ptr [rax+18h], 7
0x1802015d5  jbe     short loc_1802015DA
0x1802015d7  mov     rax, [rax]
0x1802015da  lea     r8, [r13+20h]
0x1802015de  cmp     qword ptr [r8+18h], 7
0x1802015e3  jbe     short loc_1802015E8
0x1802015e5  mov     r8, [r8]
0x1802015e8  cmp     qword ptr [r13+18h], 7
0x1802015ed  jbe     short loc_1802015F3
0x1802015ef  mov     r13, [r13+0]
0x1802015f3  mov     [rsp+3D0h+var_308], 0
0x1802015fe  lea     r10, qword_18025C818
0x180201605  mov     [rsp+3D0h+var_310], r10
0x18020160d  mov     [rsp+3D0h+var_318], r10
0x180201615  mov     [rsp+3D0h+var_320], 0
0x18020161d  mov     [rsp+3D0h+var_328], r10
0x180201625  mov     [rsp+3D0h+var_330], r12b
0x18020162d  mov     [rsp+3D0h+var_338], r10
0x180201635  mov     [rsp+3D0h+var_340], r10
0x18020163d  mov     [rsp+3D0h+var_348], 0
0x180201648  lea     r10, [rbp+280h+var_2E0]
0x18020164c  mov     [rsp+3D0h+var_350], r10
0x180201654  mov     [rsp+3D0h+var_358], 0
0x180201659  lea     r10, [rbp+280h+var_2A0]
0x18020165d  mov     [rsp+3D0h+var_360], r10
0x180201662  mov     [rsp+3D0h+var_368], 0
0x18020166a  mov     [rsp+3D0h+var_370], 0
0x180201673  mov     [rsp+3D0h+var_378], 0
0x180201678  mov     [rsp+3D0h+var_380], edx
0x18020167c  mov     [rsp+3D0h+var_388], r9
0x180201681  mov     [rsp+3D0h+var_390], rcx
0x180201686  mov     [rsp+3D0h+var_398], rbx
0x18020168b  mov     [rsp+3D0h+var_3A0], rax
0x180201690  mov     [rsp+3D0h+var_3A8], 0
0x180201698  mov     [rsp+3D0h+var_3B0], edi
0x18020169c  mov     r9d, r11d
0x18020169f  mov     rdx, r13
0x1802016a2  lea     rcx, [rbp+280h+var_2B8]
0x1802016a6  call    ?GenerateDlpTelemetryEvent@DlpEngineTelemetry@RealtimeProtection@@YA?AV?$vector@UDlpTelemetryEvent@DlpEngineTelemetry@RealtimeProtection@@V?$allocator@UDlpTelemetryEvent@DlpEngineTelemetry@RealtimeProtection@@@std@@@std@@PEB_W0W4DlpEnforcementLevel@@W4DlpActionType@@K000AEBUPPID@@K_N0W4_DLP_JIT_SYNC_CLASSIFICATION_REASON@@QEAU_DLPEVENT_EXTRAINFO@@4$$QEBV?$optional@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@4@W4DlpUnallowedAppType@@004QEB_W400W4_DLP_NOTIFICATION_TYPE@@@Z; RealtimeProtection::DlpEngineTelemetry::GenerateDlpTelemetryEvent(wchar_t const *,wchar_t const *,DlpEnforcementLevel,DlpActionType,ulong,wchar_t const *,wchar_t const *,wchar_t const *,PPID const &,ulong,bool,wchar_t const *,_DLP_JIT_SYNC_CLASSIFICATION_REASON,_DLPEVENT_EXTRAINFO * const,bool,std::optional<std::string> const &&,DlpUnallowedAppType,wchar_t const *,wchar_t const *,bool,wchar_t const * const,bool,wchar_t const *,wchar_t const *,_DLP_NOTIFICATION_TYPE)
0x1802016ab  cmp     [rbp+280h+var_2C0], 0
0x1802016af  jz      short loc_1802016BC
0x1802016b1  xor     edx, edx
0x1802016b3  lea     rcx, [rbp+280h+var_2E0]; void *
0x1802016b7  call    ??_G?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAPEAXI@Z; std::string::`scalar deleting destructor'(uint)
0x1802016bc  lea     rcx, [rbp+280h+var_2B8]
0x1802016c0  call    ?SendDlpTelemetryEvent@DlpEngineTelemetry@RealtimeProtection@@YAX$$QEAV?$vector@UDlpTelemetryEvent@DlpEngineTelemetry@RealtimeProtection@@V?$allocator@UDlpTelemetryEvent@DlpEngineTelemetry@RealtimeProtection@@@std@@@std@@@Z; RealtimeProtection::DlpEngineTelemetry::SendDlpTelemetryEvent(std::vector<RealtimeProtection::DlpEngineTelemetry::DlpTelemetryEvent> &&)
0x1802016c5  lea     rcx, [rbp+280h+var_2B8]
0x1802016c9  call    ?_Tidy@?$vector@UDlpTelemetryEvent@DlpEngineTelemetry@RealtimeProtection@@V?$allocator@UDlpTelemetryEvent@DlpEngineTelemetry@RealtimeProtection@@@std@@@std@@AEAAXXZ; std::vector<RealtimeProtection::DlpEngineTelemetry::DlpTelemetryEvent>::_Tidy(void)
0x1802016ce  nop
0x1802016cf  cmp     [rbp+280h+var_2F0], 0
0x1802016d3  jz      short loc_1802016DF
0x1802016d5  mov     rcx, [rbp+280h+SRWLock]; SRWLock
0x1802016d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1802016df  mov     eax, r15d
0x1802016e2  mov     rcx, [rbp+280h+var_40]
0x1802016e9  xor     rcx, rsp; StackCookie
0x1802016ec  call    __security_check_cookie
0x1802016f1  add     rsp, 3A0h
0x1802016f8  pop     r15
0x1802016fa  pop     r13
0x1802016fc  pop     r12
0x1802016fe  pop     rdi
0x1802016ff  pop     rsi
0x180201700  pop     rbx
0x180201701  pop     rbp
0x180201702  retn
```
