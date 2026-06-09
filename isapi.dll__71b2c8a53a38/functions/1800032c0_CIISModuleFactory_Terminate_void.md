# CIISModuleFactory::Terminate(void)

- ea: `0x1800032c0`
- end: `0x18000339a`
- name: `?Terminate@CIISModuleFactory@@UEAAXXZ`
- size: `218`
- prototype: `void __fastcall(CIISModuleFactory *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x180001060`
- `0x180001d8c`
- `0x1800032c0`
- `0x180005c44`
- `0x180005fc8`
- `0x18000c5e8`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800032f8`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800032f8`
- `iisutil!TerminateIISUtil` at `0x180003341`
- `iisutil!TerminateIISUtil` at `0x180003341`
- `iisutil!PuDeleteDebugPrintsObject` at `0x18000334e`
- `iisutil!PuDeleteDebugPrintsObject` at `0x18000334e`

## pseudocode

```c
void __fastcall CIISModuleFactory::Terminate(CIISModuleFactory *this, unsigned int a2)
{
  void *v3; // rbx
  unsigned int v4; // edx

  if ( W3_RESTRICTION_LIST::sm_pRestrictionList )
  {
    W3_RESTRICTION_LIST::`scalar deleting destructor'(W3_RESTRICTION_LIST::sm_pRestrictionList, a2);
    W3_RESTRICTION_LIST::sm_pRestrictionList = 0;
  }
  v3 = W3_RESTRICTION_LIST::sm_pRestrictionLock;
  if ( W3_RESTRICTION_LIST::sm_pRestrictionLock )
  {
    CReaderWriterLock3::~CReaderWriterLock3((CReaderWriterLock3 *)W3_RESTRICTION_LIST::sm_pRestrictionLock);
    operator delete(v3);
    W3_RESTRICTION_LIST::sm_pRestrictionLock = 0;
  }
  ISAPI_REQUEST::CleanupClass();
  ISAPI_CONTEXT::Terminate();
  if ( g_pDllManager )
    W3_RESTRICTION_LIST::`scalar deleting destructor'(g_pDllManager, v4);
  g_pDllManager = 0;
  ISAPI_DLL::Terminate();
  ISAPI_REQUEST::CleanupClass();
  TerminateIISUtil();
  g_pDebug = PuDeleteDebugPrintsObject(g_pDebug);
  if ( g_pEventLog )
  {
    operator delete(g_pEventLog);
    g_pEventLog = 0;
  }
  if ( this )
  {
    *((_QWORD *)this + 1) = &CHttpModule::`vftable';
    operator delete(this);
  }
}

```

## disassembly

```asm
0x1800032c0  mov     [rsp+arg_0], rbx
0x1800032c5  push    rdi
0x1800032c6  sub     rsp, 20h
0x1800032ca  mov     rdi, rcx
0x1800032cd  mov     rcx, cs:?sm_pRestrictionList@W3_RESTRICTION_LIST@@0PEAV1@EA; this
0x1800032d4  test    rcx, rcx
0x1800032d7  jz      short loc_1800032E9
0x1800032d9  call    ??_GW3_RESTRICTION_LIST@@QEAAPEAXI@Z; W3_RESTRICTION_LIST::`scalar deleting destructor'(uint)
0x1800032de  mov     cs:?sm_pRestrictionList@W3_RESTRICTION_LIST@@0PEAV1@EA, 0; W3_RESTRICTION_LIST * W3_RESTRICTION_LIST::sm_pRestrictionList
0x1800032e9  mov     rbx, cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x1800032f0  test    rbx, rbx
0x1800032f3  jz      short loc_180003311
0x1800032f5  mov     rcx, rbx
0x1800032f8  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x1800032fe  mov     rcx, rbx; Block
0x180003301  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003306  mov     cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA, 0; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x180003311  call    ?CleanupClass@ISAPI_REQUEST@@SAXXZ; ISAPI_REQUEST::CleanupClass(void)
0x180003316  call    ?Terminate@ISAPI_CONTEXT@@SAXXZ; ISAPI_CONTEXT::Terminate(void)
0x18000331b  mov     rcx, cs:?g_pDllManager@@3PEAVISAPI_DLL_MANAGER@@EA; this
0x180003322  test    rcx, rcx
0x180003325  jz      short loc_18000332C
0x180003327  call    ??_GW3_RESTRICTION_LIST@@QEAAPEAXI@Z; W3_RESTRICTION_LIST::`scalar deleting destructor'(uint)
0x18000332c  mov     cs:?g_pDllManager@@3PEAVISAPI_DLL_MANAGER@@EA, 0; ISAPI_DLL_MANAGER * g_pDllManager
0x180003337  call    ?Terminate@ISAPI_DLL@@SAXXZ; ISAPI_DLL::Terminate(void)
0x18000333c  call    ?CleanupClass@ISAPI_REQUEST@@SAXXZ; ISAPI_REQUEST::CleanupClass(void)
0x180003341  call    cs:__imp_TerminateIISUtil
0x180003347  mov     rcx, cs:g_pDebug
0x18000334e  call    cs:__imp_PuDeleteDebugPrintsObject
0x180003354  mov     rcx, cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA; Block
0x18000335b  mov     cs:g_pDebug, rax
0x180003362  test    rcx, rcx
0x180003365  jz      short loc_180003377
0x180003367  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000336c  mov     cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA, 0; EVENT_LOG * g_pEventLog
0x180003377  test    rdi, rdi
0x18000337a  jz      short loc_18000338F
0x18000337c  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x180003383  mov     rcx, rdi; Block
0x180003386  mov     [rdi+8], rax
0x18000338a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000338f  mov     rbx, [rsp+28h+arg_0]
0x180003394  add     rsp, 20h
0x180003398  pop     rdi
0x180003399  retn
```
