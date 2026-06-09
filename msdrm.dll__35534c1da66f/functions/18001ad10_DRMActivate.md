# DRMActivate

- ea: `0x18001ad10`
- end: `0x18001b06c`
- name: `DRMActivate`
- size: `860`
- prototype: `HRESULT __stdcall(DRMHSESSION hClient, UINT uFlags, UINT uLangID, DRM_ACTSERV_INFO *pActServInfo, void *pvContext, HWND hParentWnd)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18005ad7c`

## callees

- `0x180001284`
- `0x18000420c`
- `0x180004260`
- `0x1800046c8`
- `0x18000f034`
- `0x180019734`
- `0x18001991c`
- `0x18001ad10`
- `0x18001fa40`
- `0x18001ff90`
- `0x1800205ec`
- `0x180022730`
- `0x180022770`
- `0x18002b454`
- `0x180034bb0`
- `0x1800356f8`
- `0x1800370d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001af17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001af1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001afba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001af17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001af1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001afba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001af03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001afa9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001af03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001afa9`
- `USER32!IsWindow` at `0x18001ad6e`
- `USER32!IsWindow` at `0x18001ad6e`

## string_xrefs

- `0x18001ae00`: `DRM_ACTIVATE_TEMPORARY`

## pseudocode

```c
HRESULT __stdcall DRMActivate(
        DRMHSESSION hClient,
        UINT uFlags,
        UINT uLangID,
        DRM_ACTSERV_INFO *pActServInfo,
        void *pvContext,
        HWND hParentWnd)
{
  char v6; // si
  HRESULT v8; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  HWND v12; // r12
  PWSTR wszURL; // r15
  char v14; // si
  const wchar_t *v15; // r9
  unsigned int v16; // edi
  const wchar_t *v17; // rax
  unsigned int v18; // r14d
  unsigned int v19; // ebx
  unsigned int v20; // ebp
  const unsigned __int16 *v21; // rdx
  const unsigned __int16 *v22; // rax
  CHandleTable *v23; // rcx
  void *v25; // rsi
  __int64 v26; // rdi
  __int64 v27; // rbx
  struct _RTL_CRITICAL_SECTION *v28; // rcx
  unsigned __int16 *MaxVersion; // rsi
  wchar_t *String1; // rbp
  unsigned int CallbackVersion; // ebx
  int (*Callback)(enum _DRM_STATUS_MSG, int, void *, void *); // rax
  unsigned int v33; // [rsp+50h] [rbp-58h]
  void *Block; // [rsp+58h] [rbp-50h] BYREF
  unsigned int v35; // [rsp+60h] [rbp-48h]
  _QWORD v36[8]; // [rsp+68h] [rbp-40h] BYREF
  unsigned int v37; // [rsp+B8h] [rbp+10h] BYREF
  unsigned int v38; // [rsp+C0h] [rbp+18h]

  v38 = uLangID;
  v37 = uFlags;
  v6 = uFlags;
  v36[0] = 0;
  v8 = 0;
  if ( (int)CDRMCLock::Lock((CDRMCLock *)v36, L"msdrm_DRMActivate") < 0 )
    goto LABEL_22;
  if ( !hClient )
    goto LABEL_21;
  v12 = hParentWnd;
  if ( hParentWnd )
  {
    if ( !IsWindow(hParentWnd) )
      goto LABEL_21;
  }
  wszURL = 0;
  if ( (v6 & 1) == 0 )
  {
    if ( pActServInfo )
    {
      if ( !(unsigned __int8)DRMIsValidStringT<unsigned short>(pActServInfo->wszURL, 0, v10, v11) )
        goto LABEL_21;
      wszURL = pActServInfo->wszURL;
      if ( !*wszURL )
        goto LABEL_21;
    }
  }
  EnableUIInFlagIfNeeded(&v37);
  v14 = v37;
  v15 = L"DRM_ACTIVATE_CANCEL";
  v16 = v37 & 1;
  v35 = v16;
  v17 = L"DRM_ACTIVATE_GROUPIDENTITY";
  v18 = v37 & 2;
  if ( (v37 & 2) == 0 )
    v17 = (const wchar_t *)((unsigned __int64)L"DRM_ACTIVATE_MACHINE" & -(__int64)(v16 != 0));
  v19 = v37 & 8;
  v33 = v19;
  if ( (v37 & 8) == 0 )
    v15 = v17;
  v20 = v37 & 4;
  LODWORD(Block) = v37 & 0x10;
  v21 = &Src;
  v22 = &Src;
  if ( ((unsigned __int64)L"DRM_ACTIVATE_SILENT" & -(__int64)((_DWORD)Block != 0)) != 0 )
    v22 = (const unsigned __int16 *)((unsigned __int64)L"DRM_ACTIVATE_SILENT" & -(__int64)((_DWORD)Block != 0));
  if ( ((unsigned __int64)L"DRM_ACTIVATE_TEMPORARY" & -(__int64)(v20 != 0)) != 0 )
    v21 = (const unsigned __int16 *)((unsigned __int64)L"DRM_ACTIVATE_TEMPORARY" & -(__int64)(v20 != 0));
  _RTLTRACE("[msdrm]:+DRMActivate - uLangID=%d,wszServer=%S,uFlags=%d,%S %S %S\n", v38, wszURL, v37, v15, v22, v21);
  if ( !v19 )
  {
    if ( v16 )
    {
      if ( v18 || v20 || !(_DWORD)Block )
        goto LABEL_21;
    }
    else if ( !v18 || (v14 & 0x40) != 0 )
    {
LABEL_21:
      v8 = -2147024809;
      goto LABEL_22;
    }
  }
  Block = 0;
  if ( CHandleTable::Get(v23, hClient, (struct DRMCInt **)&Block) < 0 )
    goto LABEL_50;
  v25 = Block;
  if ( !Block )
    goto LABEL_50;
  if ( *(_DWORD *)Block == 2 )
  {
    v27 = *((_QWORD *)Block + 1);
    EnterCriticalSection((LPCRITICAL_SECTION)(v27 + 88));
    v28 = (struct _RTL_CRITICAL_SECTION *)(v27 + 88);
    if ( *(_DWORD *)(v27 + 136) == -1 )
    {
      v26 = 0;
      LeaveCriticalSection(v28);
    }
    else
    {
      LeaveCriticalSection(v28);
      v26 = *((_QWORD *)v25 + 1);
    }
    v19 = v33;
  }
  else
  {
    v26 = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25 + 4, 0xFFFFFFFF) == 1 )
    operator delete(v25);
  if ( !v26 )
  {
LABEL_50:
    v8 = -2147024890;
    goto LABEL_22;
  }
  if ( !v19 && (unsigned int)CDRMCBase::IsThreadAlive((CDRMCBase *)v26, 0) )
  {
    v8 = -2147168456;
    goto LABEL_22;
  }
  MaxVersion = 0;
  String1 = 0;
  if ( v19 )
  {
LABEL_43:
    if ( !v18 )
      goto LABEL_45;
    goto LABEL_44;
  }
  if ( v35 )
  {
    DeleteAllLicense(1);
    DeleteAllLicense(0);
    DeleteAllLicense(6);
    DeleteMachineKeys();
    goto LABEL_43;
  }
  if ( v18 )
  {
    if ( g_fGlobalOptionUseServerProc )
    {
      DeleteAllLicense(1);
      DeleteAllLicense(3);
      CloseGlobalSignerHandle();
    }
LABEL_44:
    MaxVersion = CUsagePolicy::GetMaxVersion((CUsagePolicy *)v26);
    EnterCriticalSection((LPCRITICAL_SECTION)(v26 + 88));
    String1 = *(wchar_t **)(v26 + 152);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v26 + 88));
  }
LABEL_45:
  CallbackVersion = CDRMClient::GetCallbackVersion((CDRMClient *)v26);
  Callback = CDRMClient::GetCallback((CDRMClient *)v26);
  v8 = Activate(hClient, Callback, CallbackVersion, wszURL, MaxVersion, String1, v37, pvContext, v12, v38);
  if ( v8 >= 0 )
    v8 = CDRMClient::DeleteAllCache((CDRMClient *)v26, 1u);
LABEL_22:
  _RTLTRACE("[msdrm]:-DRMActivate HR=%x\n", v8);
  CDRMCLock::~CDRMCLock((CDRMCLock *)v36);
  return v8;
}

```

## disassembly

```asm
0x18001ad10  mov     rax, rsp
0x18001ad13  mov     [rax+8], rbx
0x18001ad17  mov     [rax+18h], r8d
0x18001ad1b  mov     [rax+10h], edx
0x18001ad1e  push    rbp
0x18001ad1f  push    rsi
0x18001ad20  push    rdi
0x18001ad21  push    r12
0x18001ad23  push    r13
0x18001ad25  push    r14
0x18001ad27  push    r15
0x18001ad29  sub     rsp, 70h
0x18001ad2d  mov     esi, edx
0x18001ad2f  mov     r13d, ecx
0x18001ad32  xor     ebp, ebp
0x18001ad34  lea     rdx, aMsdrmDrmactiva_1; "msdrm_DRMActivate"
0x18001ad3b  lea     rcx, [rax-40h]; this
0x18001ad3f  mov     [rax-40h], rbp
0x18001ad43  mov     ebx, ebp
0x18001ad45  mov     rdi, r9
0x18001ad48  call    ?Lock@CDRMCLock@@QEAAJPEAG@Z; CDRMCLock::Lock(ushort *)
0x18001ad4d  test    eax, eax
0x18001ad4f  js      loc_18001AE82
0x18001ad55  test    r13d, r13d
0x18001ad58  jz      loc_18001AE7D
0x18001ad5e  mov     r12, [rsp+0A8h+hParentWnd]
0x18001ad66  test    r12, r12
0x18001ad69  jz      short loc_18001AD7C
0x18001ad6b  mov     rcx, r12; hWnd
0x18001ad6e  call    cs:__imp_IsWindow
0x18001ad74  test    eax, eax
0x18001ad76  jz      loc_18001AE7D
0x18001ad7c  mov     r15, rbp
0x18001ad7f  test    sil, 1
0x18001ad83  jnz     short loc_18001ADAB
0x18001ad85  test    rdi, rdi
0x18001ad88  jz      short loc_18001ADAB
0x18001ad8a  mov     rcx, [rdi+10h]
0x18001ad8e  xor     edx, edx
0x18001ad90  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x18001ad95  test    al, al
0x18001ad97  jz      loc_18001AE7D
0x18001ad9d  mov     r15, [rdi+10h]
0x18001ada1  cmp     [r15], bp
0x18001ada5  jz      loc_18001AE7D
0x18001adab  lea     rcx, [rsp+0A8h+arg_8]; unsigned int *
0x18001adb3  call    ?EnableUIInFlagIfNeeded@@YAXAEAI@Z; EnableUIInFlagIfNeeded(uint &)
0x18001adb8  mov     esi, [rsp+0A8h+arg_8]
0x18001adbf  lea     rdx, aDrmActivateMac; "DRM_ACTIVATE_MACHINE"
0x18001adc6  mov     edi, esi
0x18001adc8  lea     r9, aDrmActivateCan; "DRM_ACTIVATE_CANCEL"
0x18001adcf  and     edi, 1
0x18001add2  mov     r14d, esi
0x18001add5  mov     eax, edi
0x18001add7  mov     [rsp+0A8h+var_48], edi
0x18001addb  neg     eax
0x18001addd  mov     ebx, esi
0x18001addf  lea     rax, aDrmActivateGro; "DRM_ACTIVATE_GROUPIDENTITY"
0x18001ade6  mov     ebp, esi
0x18001ade8  sbb     rcx, rcx
0x18001adeb  and     rcx, rdx
0x18001adee  lea     rdx, aDrmActivateSil; "DRM_ACTIVATE_SILENT"
0x18001adf5  and     r14d, 2
0x18001adf9  cmovz   rax, rcx
0x18001adfd  and     ebx, 8
0x18001ae00  lea     rcx, aDrmActivateTem; "DRM_ACTIVATE_TEMPORARY"
0x18001ae07  mov     [rsp+0A8h+var_58], ebx
0x18001ae0b  cmovz   r9, rax
0x18001ae0f  and     ebp, 4
0x18001ae12  mov     eax, ebp
0x18001ae14  neg     eax
0x18001ae16  mov     eax, esi
0x18001ae18  sbb     r8, r8
0x18001ae1b  and     eax, 10h
0x18001ae1e  and     r8, rcx
0x18001ae21  mov     dword ptr [rsp+0A8h+Block], eax
0x18001ae25  neg     eax
0x18001ae27  sbb     rcx, rcx
0x18001ae2a  and     rcx, rdx
0x18001ae2d  lea     rdx, Src
0x18001ae34  mov     rax, rdx
0x18001ae37  cmovnz  rax, rcx
0x18001ae3b  test    r8, r8
0x18001ae3e  lea     rcx, aMsdrmDrmactiva; "[msdrm]:+DRMActivate - uLangID=%d,wszSe"...
0x18001ae45  cmovnz  rdx, r8
0x18001ae49  mov     r8, r15
0x18001ae4c  mov     qword ptr [rsp+0A8h+var_78], rdx
0x18001ae51  mov     edx, [rsp+0A8h+arg_10]
0x18001ae58  mov     [rsp+0A8h+String1], rax
0x18001ae5d  mov     [rsp+0A8h+var_88], r9
0x18001ae62  mov     r9d, esi
0x18001ae65  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001ae6a  test    ebx, ebx
0x18001ae6c  jnz     short loc_18001AEC3
0x18001ae6e  test    edi, edi
0x18001ae70  jnz     short loc_18001AEB4
0x18001ae72  test    r14d, r14d
0x18001ae75  jz      short loc_18001AE7D
0x18001ae77  test    sil, 40h
0x18001ae7b  jz      short loc_18001AEC3
0x18001ae7d  mov     ebx, 80070057h
0x18001ae82  mov     edx, ebx
0x18001ae84  lea     rcx, aMsdrmDrmactiva_0; "[msdrm]:-DRMActivate HR=%x\n"
0x18001ae8b  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001ae90  lea     rcx, [rsp+0A8h+var_40]; this
0x18001ae95  call    ??1CDRMCLock@@QEAA@XZ; CDRMCLock::~CDRMCLock(void)
0x18001ae9a  mov     eax, ebx
0x18001ae9c  mov     rbx, [rsp+0A8h+arg_0]
0x18001aea4  add     rsp, 70h
0x18001aea8  pop     r15
0x18001aeaa  pop     r14
0x18001aeac  pop     r13
0x18001aeae  pop     r12
0x18001aeb0  pop     rdi
0x18001aeb1  pop     rsi
0x18001aeb2  pop     rbp
0x18001aeb3  retn
0x18001aeb4  test    r14d, r14d
0x18001aeb7  jnz     short loc_18001AE7D
0x18001aeb9  test    ebp, ebp
0x18001aebb  jnz     short loc_18001AE7D
0x18001aebd  cmp     dword ptr [rsp+0A8h+Block], ebp
0x18001aec1  jz      short loc_18001AE7D
0x18001aec3  lea     r8, [rsp+0A8h+Block]; struct DRMCInt **
0x18001aec8  mov     [rsp+0A8h+Block], 0
0x18001aed1  mov     edx, r13d; unsigned int
0x18001aed4  call    ?Get@CHandleTable@@QEAAJKPEAPEAUDRMCInt@@@Z; CHandleTable::Get(ulong,DRMCInt * *)
0x18001aed9  test    eax, eax
0x18001aedb  js      loc_18001B062
0x18001aee1  mov     rsi, [rsp+0A8h+Block]
0x18001aee6  test    rsi, rsi
0x18001aee9  jz      loc_18001B062
0x18001aeef  cmp     dword ptr [rsi], 2
0x18001aef2  jz      short loc_18001AEF8
0x18001aef4  xor     edi, edi
0x18001aef6  jmp     short loc_18001AF2D
0x18001aef8  mov     rbx, [rsi+8]
0x18001aefc  lea     rbp, [rbx+58h]
0x18001af00  mov     rcx, rbp; lpCriticalSection
0x18001af03  call    cs:__imp_EnterCriticalSection
0x18001af09  cmp     dword ptr [rbx+88h], 0FFFFFFFFh
0x18001af10  mov     rcx, rbp; lpCriticalSection
0x18001af13  jnz     short loc_18001AF1F
0x18001af15  xor     edi, edi
0x18001af17  call    cs:__imp_LeaveCriticalSection
0x18001af1d  jmp     short loc_18001AF29
0x18001af1f  call    cs:__imp_LeaveCriticalSection
0x18001af25  mov     rdi, [rsi+8]
0x18001af29  mov     ebx, [rsp+0A8h+var_58]
0x18001af2d  or      eax, 0FFFFFFFFh
0x18001af30  lock xadd [rsi+10h], eax
0x18001af35  cmp     eax, 1
0x18001af38  jnz     short loc_18001AF42
0x18001af3a  mov     rcx, rsi; Block
0x18001af3d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001af42  test    rdi, rdi
0x18001af45  jz      loc_18001B062
0x18001af4b  test    ebx, ebx
0x18001af4d  jnz     short loc_18001AF67
0x18001af4f  xor     edx, edx; unsigned int
0x18001af51  mov     rcx, rdi; this
0x18001af54  call    ?IsThreadAlive@CDRMCBase@@QEAAHI@Z; CDRMCBase::IsThreadAlive(uint)
0x18001af59  test    eax, eax
0x18001af5b  jz      short loc_18001AF67
0x18001af5d  mov     ebx, 8004CF38h
0x18001af62  jmp     loc_18001AE82
0x18001af67  xor     esi, esi
0x18001af69  xor     ebp, ebp
0x18001af6b  test    ebx, ebx
0x18001af6d  jnz     short loc_18001AF95
0x18001af6f  cmp     [rsp+0A8h+var_48], esi
0x18001af73  jz      loc_18001B033
0x18001af79  lea     ecx, [rsi+1]
0x18001af7c  call    ?DeleteAllLicense@@YAJW4DRM_LICENSE_TYPE@@@Z; DeleteAllLicense(DRM_LICENSE_TYPE)
0x18001af81  xor     ecx, ecx
0x18001af83  call    ?DeleteAllLicense@@YAJW4DRM_LICENSE_TYPE@@@Z; DeleteAllLicense(DRM_LICENSE_TYPE)
0x18001af88  lea     ecx, [rsi+6]
0x18001af8b  call    ?DeleteAllLicense@@YAJW4DRM_LICENSE_TYPE@@@Z; DeleteAllLicense(DRM_LICENSE_TYPE)
0x18001af90  call    ?DeleteMachineKeys@@YAJXZ; DeleteMachineKeys(void)
0x18001af95  test    r14d, r14d
0x18001af98  jz      short loc_18001AFC0
0x18001af9a  mov     rcx, rdi; this
0x18001af9d  call    ?GetMaxVersion@CUsagePolicy@@QEAAPEAGXZ; CUsagePolicy::GetMaxVersion(void)
0x18001afa2  lea     rcx, [rdi+58h]; lpCriticalSection
0x18001afa6  mov     rsi, rax
0x18001afa9  call    cs:__imp_EnterCriticalSection
0x18001afaf  mov     rbp, [rdi+98h]
0x18001afb6  lea     rcx, [rdi+58h]; lpCriticalSection
0x18001afba  call    cs:__imp_LeaveCriticalSection
0x18001afc0  mov     rcx, rdi; this
0x18001afc3  call    ?GetCallbackVersion@CDRMClient@@QEAAIXZ; CDRMClient::GetCallbackVersion(void)
0x18001afc8  mov     rcx, rdi; this
0x18001afcb  mov     ebx, eax
0x18001afcd  call    ?GetCallback@CDRMClient@@QEAAP6AJW4_DRM_STATUS_MSG@@JPEAX1@ZXZ; CDRMClient::GetCallback(void)
0x18001afd2  mov     ecx, [rsp+0A8h+arg_10]
0x18001afd9  mov     r9, r15; unsigned __int16 *
0x18001afdc  mov     r8, [rsp+0A8h+pvContext]
0x18001afe4  mov     rdx, rax; int (*)(enum _DRM_STATUS_MSG, int, void *, void *)
0x18001afe7  mov     [rsp+0A8h+var_60], ecx; unsigned int
0x18001afeb  mov     ecx, [rsp+0A8h+arg_8]
0x18001aff2  mov     [rsp+0A8h+var_68], r12; HWND
0x18001aff7  mov     [rsp+0A8h+var_70], r8; void *
0x18001affc  mov     r8d, ebx; unsigned int
0x18001afff  mov     [rsp+0A8h+var_78], ecx; unsigned int
0x18001b003  mov     ecx, r13d; unsigned int
0x18001b006  mov     [rsp+0A8h+String1], rbp; String1
0x18001b00b  mov     [rsp+0A8h+var_88], rsi; unsigned __int16 *
0x18001b010  call    ?Activate@@YAJKP6AJW4_DRM_STATUS_MSG@@JPEAX1@ZIPEAG33I1PEAUHWND__@@I@Z; Activate(ulong,long (*)(_DRM_STATUS_MSG,long,void *,void *),uint,ushort *,ushort *,ushort *,uint,void *,HWND__ *,uint)
0x18001b015  mov     ebx, eax
0x18001b017  test    eax, eax
0x18001b019  js      loc_18001AE82
0x18001b01f  mov     edx, 1; unsigned int
0x18001b024  mov     rcx, rdi; this
0x18001b027  call    ?DeleteAllCache@CDRMClient@@QEAAJI@Z; CDRMClient::DeleteAllCache(uint)
0x18001b02c  mov     ebx, eax
0x18001b02e  jmp     loc_18001AE82
0x18001b033  test    r14d, r14d
0x18001b036  jz      short loc_18001AFC0
0x18001b038  cmp     cs:?g_fGlobalOptionUseServerProc@@3HA, esi; int g_fGlobalOptionUseServerProc
0x18001b03e  jz      loc_18001AF9A
0x18001b044  mov     ecx, 1
0x18001b049  call    ?DeleteAllLicense@@YAJW4DRM_LICENSE_TYPE@@@Z; DeleteAllLicense(DRM_LICENSE_TYPE)
0x18001b04e  mov     ecx, 3
0x18001b053  call    ?DeleteAllLicense@@YAJW4DRM_LICENSE_TYPE@@@Z; DeleteAllLicense(DRM_LICENSE_TYPE)
0x18001b058  call    ?CloseGlobalSignerHandle@@YAXXZ; CloseGlobalSignerHandle(void)
0x18001b05d  jmp     loc_18001AF9A
0x18001b062  mov     ebx, 80070006h
0x18001b067  jmp     loc_18001AE82
```
