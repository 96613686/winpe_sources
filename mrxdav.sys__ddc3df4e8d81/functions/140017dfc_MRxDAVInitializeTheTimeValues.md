# MRxDAVInitializeTheTimeValues

- ea: `0x140017dfc`
- end: `0x140018181`
- name: `MRxDAVInitializeTheTimeValues`
- size: `901`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x140016d2c`

## callees

- `0x140017dfc`
- `0x1400282d4`

## string_xrefs

- `0x140017e09`: `FileInformationCacheLifeTimeInSec`
- `0x140017e2a`: `FileNotFoundCacheLifeTimeInSec`
- `0x140017e4b`: `NameCacheMaxEntries`
- `0x140017e6c`: `CreateRequestTimeoutInSec`
- `0x140017e94`: `CreateVNetRootRequestTimeoutInSec`
- `0x140017ecf`: `QueryDirectoryRequestTimeoutInSec`
- `0x140017f31`: `CreateSrvCallRequestTimeoutInSec`
- `0x14001802a`: `ReNameRequestTimeoutInSec`
- `0x14001805b`: `SetFileInfoRequestTimeoutInSec`

## pseudocode

```c
__int64 __fastcall MRxDAVInitializeTheTimeValues(__int64 a1)
{
  __int64 v1; // rcx
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 result; // rax

  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(
                       a1,
                       L"FileInformationCacheLifeTimeInSec",
                       &FileInformationCacheLifeTimeInSec) )
    FileInformationCacheLifeTimeInSec = 60;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(
                       v1,
                       L"FileNotFoundCacheLifeTimeInSec",
                       &FileNotFoundCacheLifeTimeInSec) )
    FileNotFoundCacheLifeTimeInSec = 60;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(v2, L"NameCacheMaxEntries", &NameCacheMaxEntries) )
    NameCacheMaxEntries = 300;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(v3, L"CreateRequestTimeoutInSec", &CreateRequestTimeoutValueInSec) )
    CreateRequestTimeoutValueInSec = 600;
  TimerThreadSleepTimeInSec = CreateRequestTimeoutValueInSec;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(
                       v4,
                       L"CreateVNetRootRequestTimeoutInSec",
                       &CreateVNetRootRequestTimeoutValueInSec) )
    CreateVNetRootRequestTimeoutValueInSec = 60;
  if ( CreateVNetRootRequestTimeoutValueInSec < (unsigned int)TimerThreadSleepTimeInSec )
    TimerThreadSleepTimeInSec = CreateVNetRootRequestTimeoutValueInSec;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(
                       v5,
                       L"QueryDirectoryRequestTimeoutInSec",
                       &QueryDirectoryRequestTimeoutValueInSec) )
    QueryDirectoryRequestTimeoutValueInSec = 600;
  if ( QueryDirectoryRequestTimeoutValueInSec < (unsigned int)TimerThreadSleepTimeInSec )
    TimerThreadSleepTimeInSec = QueryDirectoryRequestTimeoutValueInSec;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(v6, L"CloseRequestTimeoutInSec", &CloseRequestTimeoutValueInSec) )
    CloseRequestTimeoutValueInSec = 600;
  if ( CloseRequestTimeoutValueInSec < (unsigned int)TimerThreadSleepTimeInSec )
    TimerThreadSleepTimeInSec = CloseRequestTimeoutValueInSec;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(
                       v7,
                       L"CreateSrvCallRequestTimeoutInSec",
                       &CreateSrvCallRequestTimeoutValueInSec) )
    CreateSrvCallRequestTimeoutValueInSec = 20;
  if ( CreateSrvCallRequestTimeoutValueInSec < (unsigned int)TimerThreadSleepTimeInSec )
    TimerThreadSleepTimeInSec = CreateSrvCallRequestTimeoutValueInSec;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(
                       v8,
                       L"FinalizeSrvCallRequestTimeoutInSec",
                       &FinalizeSrvCallRequestTimeoutValueInSec) )
    FinalizeSrvCallRequestTimeoutValueInSec = 600;
  if ( FinalizeSrvCallRequestTimeoutValueInSec < (unsigned int)TimerThreadSleepTimeInSec )
    TimerThreadSleepTimeInSec = FinalizeSrvCallRequestTimeoutValueInSec;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(
                       v9,
                       L"FinalizeFobxRequestTimeoutInSec",
                       &FinalizeFobxRequestTimeoutValueInSec) )
    FinalizeFobxRequestTimeoutValueInSec = 600;
  if ( FinalizeFobxRequestTimeoutValueInSec < (unsigned int)TimerThreadSleepTimeInSec )
    TimerThreadSleepTimeInSec = FinalizeFobxRequestTimeoutValueInSec;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(
                       v10,
                       L"FinalizeFcbRequestTimeoutInSec",
                       &FinalizeFcbRequestTimeoutValueInSec) )
    FinalizeFcbRequestTimeoutValueInSec = 600;
  if ( FinalizeFcbRequestTimeoutValueInSec < (unsigned int)TimerThreadSleepTimeInSec )
    TimerThreadSleepTimeInSec = FinalizeFcbRequestTimeoutValueInSec;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(
                       v11,
                       L"FinalizeVNetRootRequestTimeoutInSec",
                       &FinalizeVNetRootRequestTimeoutValueInSec) )
    FinalizeVNetRootRequestTimeoutValueInSec = 600;
  if ( FinalizeVNetRootRequestTimeoutValueInSec < (unsigned int)TimerThreadSleepTimeInSec )
    TimerThreadSleepTimeInSec = FinalizeVNetRootRequestTimeoutValueInSec;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(v12, L"ReNameRequestTimeoutInSec", &ReNameRequestTimeoutValueInSec) )
    ReNameRequestTimeoutValueInSec = 600;
  if ( ReNameRequestTimeoutValueInSec < (unsigned int)TimerThreadSleepTimeInSec )
    TimerThreadSleepTimeInSec = ReNameRequestTimeoutValueInSec;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(
                       v13,
                       L"SetFileInfoRequestTimeoutInSec",
                       &SetFileInfoRequestTimeoutValueInSec) )
    SetFileInfoRequestTimeoutValueInSec = 600;
  if ( SetFileInfoRequestTimeoutValueInSec < (unsigned int)TimerThreadSleepTimeInSec )
    TimerThreadSleepTimeInSec = SetFileInfoRequestTimeoutValueInSec;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(
                       v14,
                       L"QueryFileInfoRequestTimeoutInSec",
                       &QueryFileInfoRequestTimeoutValueInSec) )
    QueryFileInfoRequestTimeoutValueInSec = 600;
  if ( QueryFileInfoRequestTimeoutValueInSec < (unsigned int)TimerThreadSleepTimeInSec )
    TimerThreadSleepTimeInSec = QueryFileInfoRequestTimeoutValueInSec;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(
                       v15,
                       L"QueryVolumeInfoRequestTimeoutInSec",
                       &QueryVolumeInfoRequestTimeoutValueInSec) )
    QueryVolumeInfoRequestTimeoutValueInSec = 600;
  if ( QueryVolumeInfoRequestTimeoutValueInSec < (unsigned int)TimerThreadSleepTimeInSec )
    TimerThreadSleepTimeInSec = QueryVolumeInfoRequestTimeoutValueInSec;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(
                       v16,
                       L"LockRefreshRequestTimeoutInSec",
                       &LockRefreshRequestTimeoutValueInSec) )
    LockRefreshRequestTimeoutValueInSec = 600;
  if ( LockRefreshRequestTimeoutValueInSec < (unsigned int)TimerThreadSleepTimeInSec )
    TimerThreadSleepTimeInSec = LockRefreshRequestTimeoutValueInSec;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(v17, L"FsCtlRequestTimeoutInSec", &FsCtlRequestTimeoutValueInSec) )
    FsCtlRequestTimeoutValueInSec = 600;
  if ( FsCtlRequestTimeoutValueInSec < (unsigned int)TimerThreadSleepTimeInSec )
    TimerThreadSleepTimeInSec = FsCtlRequestTimeoutValueInSec;
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(
                       v18,
                       L"DevFsCtlRequestTimeoutInSec",
                       &DevFsCtlRequestTimeoutValueInSec) )
    DevFsCtlRequestTimeoutValueInSec = 600;
  result = (unsigned int)DevFsCtlRequestTimeoutValueInSec;
  if ( DevFsCtlRequestTimeoutValueInSec < (unsigned int)TimerThreadSleepTimeInSec )
    TimerThreadSleepTimeInSec = DevFsCtlRequestTimeoutValueInSec;
  return result;
}

```

## disassembly

```asm
0x140017dfc  push    rbx
0x140017dfe  sub     rsp, 20h
0x140017e02  lea     r8, FileInformationCacheLifeTimeInSec
0x140017e09  lea     rdx, aFileinformatio; "FileInformationCacheLifeTimeInSec"
0x140017e10  call    UMRxReadDWORDFromTheRegistry
0x140017e15  test    eax, eax
0x140017e17  jz      short loc_140017E23
0x140017e19  mov     cs:FileInformationCacheLifeTimeInSec, 3Ch ; '<'
0x140017e23  lea     r8, FileNotFoundCacheLifeTimeInSec
0x140017e2a  lea     rdx, aFilenotfoundca; "FileNotFoundCacheLifeTimeInSec"
0x140017e31  call    UMRxReadDWORDFromTheRegistry
0x140017e36  test    eax, eax
0x140017e38  jz      short loc_140017E44
0x140017e3a  mov     cs:FileNotFoundCacheLifeTimeInSec, 3Ch ; '<'
0x140017e44  lea     r8, NameCacheMaxEntries
0x140017e4b  lea     rdx, aNamecachemaxen; "NameCacheMaxEntries"
0x140017e52  call    UMRxReadDWORDFromTheRegistry
0x140017e57  test    eax, eax
0x140017e59  jz      short loc_140017E65
0x140017e5b  mov     cs:NameCacheMaxEntries, 12Ch
0x140017e65  lea     r8, CreateRequestTimeoutValueInSec
0x140017e6c  lea     rdx, aCreaterequestt; "CreateRequestTimeoutInSec"
0x140017e73  call    UMRxReadDWORDFromTheRegistry
0x140017e78  mov     ebx, 258h
0x140017e7d  test    eax, eax
0x140017e7f  jz      short loc_140017E87
0x140017e81  mov     cs:CreateRequestTimeoutValueInSec, ebx
0x140017e87  mov     eax, cs:CreateRequestTimeoutValueInSec
0x140017e8d  lea     r8, CreateVNetRootRequestTimeoutValueInSec
0x140017e94  lea     rdx, aCreatevnetroot; "CreateVNetRootRequestTimeoutInSec"
0x140017e9b  mov     cs:TimerThreadSleepTimeInSec, eax
0x140017ea1  call    UMRxReadDWORDFromTheRegistry
0x140017ea6  test    eax, eax
0x140017ea8  jz      short loc_140017EB4
0x140017eaa  mov     cs:CreateVNetRootRequestTimeoutValueInSec, 3Ch ; '<'
0x140017eb4  mov     eax, cs:CreateVNetRootRequestTimeoutValueInSec
0x140017eba  cmp     eax, cs:TimerThreadSleepTimeInSec
0x140017ec0  jnb     short loc_140017EC8
0x140017ec2  mov     cs:TimerThreadSleepTimeInSec, eax
0x140017ec8  lea     r8, QueryDirectoryRequestTimeoutValueInSec
0x140017ecf  lea     rdx, aQuerydirectory; "QueryDirectoryRequestTimeoutInSec"
0x140017ed6  call    UMRxReadDWORDFromTheRegistry
0x140017edb  test    eax, eax
0x140017edd  jz      short loc_140017EE5
0x140017edf  mov     cs:QueryDirectoryRequestTimeoutValueInSec, ebx
0x140017ee5  mov     eax, cs:QueryDirectoryRequestTimeoutValueInSec
0x140017eeb  cmp     eax, cs:TimerThreadSleepTimeInSec
0x140017ef1  jnb     short loc_140017EF9
0x140017ef3  mov     cs:TimerThreadSleepTimeInSec, eax
0x140017ef9  lea     r8, CloseRequestTimeoutValueInSec
0x140017f00  lea     rdx, aCloserequestti; "CloseRequestTimeoutInSec"
0x140017f07  call    UMRxReadDWORDFromTheRegistry
0x140017f0c  test    eax, eax
0x140017f0e  jz      short loc_140017F16
0x140017f10  mov     cs:CloseRequestTimeoutValueInSec, ebx
0x140017f16  mov     eax, cs:CloseRequestTimeoutValueInSec
0x140017f1c  cmp     eax, cs:TimerThreadSleepTimeInSec
0x140017f22  jnb     short loc_140017F2A
0x140017f24  mov     cs:TimerThreadSleepTimeInSec, eax
0x140017f2a  lea     r8, CreateSrvCallRequestTimeoutValueInSec
0x140017f31  lea     rdx, aCreatesrvcallr; "CreateSrvCallRequestTimeoutInSec"
0x140017f38  call    UMRxReadDWORDFromTheRegistry
0x140017f3d  test    eax, eax
0x140017f3f  jz      short loc_140017F4B
0x140017f41  mov     cs:CreateSrvCallRequestTimeoutValueInSec, 14h
0x140017f4b  mov     eax, cs:CreateSrvCallRequestTimeoutValueInSec
0x140017f51  cmp     eax, cs:TimerThreadSleepTimeInSec
0x140017f57  jnb     short loc_140017F5F
0x140017f59  mov     cs:TimerThreadSleepTimeInSec, eax
0x140017f5f  lea     r8, FinalizeSrvCallRequestTimeoutValueInSec
0x140017f66  lea     rdx, aFinalizesrvcal; "FinalizeSrvCallRequestTimeoutInSec"
0x140017f6d  call    UMRxReadDWORDFromTheRegistry
0x140017f72  test    eax, eax
0x140017f74  jz      short loc_140017F7C
0x140017f76  mov     cs:FinalizeSrvCallRequestTimeoutValueInSec, ebx
0x140017f7c  mov     eax, cs:FinalizeSrvCallRequestTimeoutValueInSec
0x140017f82  cmp     eax, cs:TimerThreadSleepTimeInSec
0x140017f88  jnb     short loc_140017F90
0x140017f8a  mov     cs:TimerThreadSleepTimeInSec, eax
0x140017f90  lea     r8, FinalizeFobxRequestTimeoutValueInSec
0x140017f97  lea     rdx, aFinalizefobxre; "FinalizeFobxRequestTimeoutInSec"
0x140017f9e  call    UMRxReadDWORDFromTheRegistry
0x140017fa3  test    eax, eax
0x140017fa5  jz      short loc_140017FAD
0x140017fa7  mov     cs:FinalizeFobxRequestTimeoutValueInSec, ebx
0x140017fad  mov     eax, cs:FinalizeFobxRequestTimeoutValueInSec
0x140017fb3  cmp     eax, cs:TimerThreadSleepTimeInSec
0x140017fb9  jnb     short loc_140017FC1
0x140017fbb  mov     cs:TimerThreadSleepTimeInSec, eax
0x140017fc1  lea     r8, FinalizeFcbRequestTimeoutValueInSec
0x140017fc8  lea     rdx, aFinalizefcbreq; "FinalizeFcbRequestTimeoutInSec"
0x140017fcf  call    UMRxReadDWORDFromTheRegistry
0x140017fd4  test    eax, eax
0x140017fd6  jz      short loc_140017FDE
0x140017fd8  mov     cs:FinalizeFcbRequestTimeoutValueInSec, ebx
0x140017fde  mov     eax, cs:FinalizeFcbRequestTimeoutValueInSec
0x140017fe4  cmp     eax, cs:TimerThreadSleepTimeInSec
0x140017fea  jnb     short loc_140017FF2
0x140017fec  mov     cs:TimerThreadSleepTimeInSec, eax
0x140017ff2  lea     r8, FinalizeVNetRootRequestTimeoutValueInSec
0x140017ff9  lea     rdx, aFinalizevnetro; "FinalizeVNetRootRequestTimeoutInSec"
0x140018000  call    UMRxReadDWORDFromTheRegistry
0x140018005  test    eax, eax
0x140018007  jz      short loc_14001800F
0x140018009  mov     cs:FinalizeVNetRootRequestTimeoutValueInSec, ebx
0x14001800f  mov     eax, cs:FinalizeVNetRootRequestTimeoutValueInSec
0x140018015  cmp     eax, cs:TimerThreadSleepTimeInSec
0x14001801b  jnb     short loc_140018023
0x14001801d  mov     cs:TimerThreadSleepTimeInSec, eax
0x140018023  lea     r8, ReNameRequestTimeoutValueInSec
0x14001802a  lea     rdx, aRenamerequestt; "ReNameRequestTimeoutInSec"
0x140018031  call    UMRxReadDWORDFromTheRegistry
0x140018036  test    eax, eax
0x140018038  jz      short loc_140018040
0x14001803a  mov     cs:ReNameRequestTimeoutValueInSec, ebx
0x140018040  mov     eax, cs:ReNameRequestTimeoutValueInSec
0x140018046  cmp     eax, cs:TimerThreadSleepTimeInSec
0x14001804c  jnb     short loc_140018054
0x14001804e  mov     cs:TimerThreadSleepTimeInSec, eax
0x140018054  lea     r8, SetFileInfoRequestTimeoutValueInSec
0x14001805b  lea     rdx, aSetfileinforeq; "SetFileInfoRequestTimeoutInSec"
0x140018062  call    UMRxReadDWORDFromTheRegistry
0x140018067  test    eax, eax
0x140018069  jz      short loc_140018071
0x14001806b  mov     cs:SetFileInfoRequestTimeoutValueInSec, ebx
0x140018071  mov     eax, cs:SetFileInfoRequestTimeoutValueInSec
0x140018077  cmp     eax, cs:TimerThreadSleepTimeInSec
0x14001807d  jnb     short loc_140018085
0x14001807f  mov     cs:TimerThreadSleepTimeInSec, eax
0x140018085  lea     r8, QueryFileInfoRequestTimeoutValueInSec
0x14001808c  lea     rdx, aQueryfileinfor; "QueryFileInfoRequestTimeoutInSec"
0x140018093  call    UMRxReadDWORDFromTheRegistry
0x140018098  test    eax, eax
0x14001809a  jz      short loc_1400180A2
0x14001809c  mov     cs:QueryFileInfoRequestTimeoutValueInSec, ebx
0x1400180a2  mov     eax, cs:QueryFileInfoRequestTimeoutValueInSec
0x1400180a8  cmp     eax, cs:TimerThreadSleepTimeInSec
0x1400180ae  jnb     short loc_1400180B6
0x1400180b0  mov     cs:TimerThreadSleepTimeInSec, eax
0x1400180b6  lea     r8, QueryVolumeInfoRequestTimeoutValueInSec
0x1400180bd  lea     rdx, aQueryvolumeinf; "QueryVolumeInfoRequestTimeoutInSec"
0x1400180c4  call    UMRxReadDWORDFromTheRegistry
0x1400180c9  test    eax, eax
0x1400180cb  jz      short loc_1400180D3
0x1400180cd  mov     cs:QueryVolumeInfoRequestTimeoutValueInSec, ebx
0x1400180d3  mov     eax, cs:QueryVolumeInfoRequestTimeoutValueInSec
0x1400180d9  cmp     eax, cs:TimerThreadSleepTimeInSec
0x1400180df  jnb     short loc_1400180E7
0x1400180e1  mov     cs:TimerThreadSleepTimeInSec, eax
0x1400180e7  lea     r8, LockRefreshRequestTimeoutValueInSec
0x1400180ee  lea     rdx, aLockrefreshreq; "LockRefreshRequestTimeoutInSec"
0x1400180f5  call    UMRxReadDWORDFromTheRegistry
0x1400180fa  test    eax, eax
0x1400180fc  jz      short loc_140018104
0x1400180fe  mov     cs:LockRefreshRequestTimeoutValueInSec, ebx
0x140018104  mov     eax, cs:LockRefreshRequestTimeoutValueInSec
0x14001810a  cmp     eax, cs:TimerThreadSleepTimeInSec
0x140018110  jnb     short loc_140018118
0x140018112  mov     cs:TimerThreadSleepTimeInSec, eax
0x140018118  lea     r8, FsCtlRequestTimeoutValueInSec
0x14001811f  lea     rdx, aFsctlrequestti; "FsCtlRequestTimeoutInSec"
0x140018126  call    UMRxReadDWORDFromTheRegistry
0x14001812b  test    eax, eax
0x14001812d  jz      short loc_140018135
0x14001812f  mov     cs:FsCtlRequestTimeoutValueInSec, ebx
0x140018135  mov     eax, cs:FsCtlRequestTimeoutValueInSec
0x14001813b  cmp     eax, cs:TimerThreadSleepTimeInSec
0x140018141  jnb     short loc_140018149
0x140018143  mov     cs:TimerThreadSleepTimeInSec, eax
0x140018149  lea     r8, DevFsCtlRequestTimeoutValueInSec
0x140018150  lea     rdx, aDevfsctlreques; "DevFsCtlRequestTimeoutInSec"
0x140018157  call    UMRxReadDWORDFromTheRegistry
0x14001815c  test    eax, eax
0x14001815e  jz      short loc_140018166
0x140018160  mov     cs:DevFsCtlRequestTimeoutValueInSec, ebx
0x140018166  mov     eax, cs:DevFsCtlRequestTimeoutValueInSec
0x14001816c  cmp     eax, cs:TimerThreadSleepTimeInSec
0x140018172  jnb     short loc_14001817A
0x140018174  mov     cs:TimerThreadSleepTimeInSec, eax
0x14001817a  add     rsp, 20h
0x14001817e  pop     rbx
0x14001817f  retn
```
