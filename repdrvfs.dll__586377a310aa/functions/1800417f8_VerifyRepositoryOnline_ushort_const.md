# VerifyRepositoryOnline(ushort const *)

- ea: `0x1800417f8`
- end: `0x180041a3c`
- name: `?VerifyRepositoryOnline@@YAJPEBG@Z`
- size: `580`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180041610`

## callees

- `0x1800012b8`
- `0x180038e10`
- `0x18003c16c`
- `0x180040e24`
- `0x1800417f8`
- `0x180048010`

## import_xrefs

- `wbemcomn!EnableAllPrivileges` at `0x180041827`
- `wbemcomn!EnableAllPrivileges` at `0x180041827`
- `wbemcomn!GetMemLogObject` at `0x180041860`
- `wbemcomn!GetMemLogObject` at `0x18004190a`
- `wbemcomn!GetMemLogObject` at `0x180041979`
- `wbemcomn!GetMemLogObject` at `0x1800419d2`
- `wbemcomn!GetMemLogObject` at `0x180041860`
- `wbemcomn!GetMemLogObject` at `0x18004190a`
- `wbemcomn!GetMemLogObject` at `0x180041979`
- `wbemcomn!GetMemLogObject` at `0x1800419d2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004186b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041915`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041984`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800419dd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004186b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041915`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041984`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800419dd`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800418fe`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800418fe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041854`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041854`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VerifyRepositoryOnline(const unsigned __int16 *a1)
{
  HRESULT Instance; // ebx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v4; // rax
  CVarObjHeap *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  CMemoryLog *v8; // rax
  CMemoryLog *v9; // rax
  _BYTE v11[8]; // [rsp+40h] [rbp-28h] BYREF
  IUnknown *v12; // [rsp+48h] [rbp-20h]
  __int64 (__fastcall *v13)(); // [rsp+50h] [rbp-18h]
  IUnknown *pProxy; // [rsp+78h] [rbp+10h] BYREF

  if ( !g_bVerifyRepositoryCalledFromService )
  {
    EnableAllPrivileges(1u);
    pProxy = 0;
    Instance = CoCreateInstance(&CLSID_WbemBackupRestore, 0, 0x17u, &IID_IWbemBackupRestoreEx, (LPVOID *)&pProxy);
    if ( Instance < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, Instance);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_c47982387556333a241fa51fba0ef2c5_Traceguids,
          (unsigned int)Instance);
      }
      return (unsigned int)Instance;
    }
    v11[0] = 0;
    v12 = pProxy;
    v13 =  IUnknown::`vcall'{16,{flat}};
    Instance = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x20u);
    if ( Instance >= 0 )
    {
      Instance = ((__int64 (__fastcall *)(IUnknown *))pProxy->lpVtbl[1].Release)(pProxy);
      if ( Instance >= 0 )
      {
        PerformAllValidations(a1);
        Instance = -2147217303;
        if ( ((unsigned int (__fastcall *)(IUnknown *))pProxy->lpVtbl[2].QueryInterface)(pProxy) != -2147217303 )
        {
          Instance = 0;
          ObjScopeGuardImpl0<CLock,int (CLock::*)(void)>::~ObjScopeGuardImpl0<CLock,int (CLock::*)(void)>(v11);
LABEL_28:
          ReportFutureCorruption();
          return (unsigned int)Instance;
        }
        v9 = GetMemLogObject();
        CMemoryLog::Write(v9, -2147217303);
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_16;
        }
        v6 = 16;
        v7 = 2147749993LL;
        goto LABEL_15;
      }
      v8 = GetMemLogObject();
      CMemoryLog::Write(v8, Instance);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_16;
      }
      v6 = 15;
    }
    else
    {
      v4 = GetMemLogObject();
      CMemoryLog::Write(v4, Instance);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_16;
      }
      v6 = 14;
    }
    v7 = (unsigned int)Instance;
LABEL_15:
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids, v7);
LABEL_16:
    ObjScopeGuardImpl0<CLock,int (CLock::*)(void)>::~ObjScopeGuardImpl0<CLock,int (CLock::*)(void)>(v11);
    return (unsigned int)Instance;
  }
  Instance = PerformAllValidations(a1);
  if ( Instance >= 0 )
    goto LABEL_28;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800417f8  mov     [rsp+arg_0], rbx
0x1800417fd  push    rdi
0x1800417fe  sub     rsp, 60h
0x180041802  mov     rdi, rcx
0x180041805  cmp     cs:?g_bVerifyRepositoryCalledFromService@@3_NA, 0; bool g_bVerifyRepositoryCalledFromService
0x18004180c  jz      short loc_180041822
0x18004180e  call    ?PerformAllValidations@@YAJPEBG@Z; PerformAllValidations(ushort const *)
0x180041813  mov     ebx, eax
0x180041815  test    eax, eax
0x180041817  js      loc_180041A2F
0x18004181d  jmp     loc_180041A2A
0x180041822  mov     ecx, 1
0x180041827  call    cs:__imp_?EnableAllPrivileges@@YAJK@Z; EnableAllPrivileges(ulong)
0x18004182d  mov     [rsp+68h+pProxy], 0
0x180041836  lea     rax, [rsp+68h+pProxy]
0x18004183b  mov     [rsp+68h+ppv], rax; ppv
0x180041840  lea     r9, IID_IWbemBackupRestoreEx; riid
0x180041847  xor     edx, edx; pUnkOuter
0x180041849  lea     r8d, [rdx+17h]; dwClsContext
0x18004184d  lea     rcx, CLSID_WbemBackupRestore; rclsid
0x180041854  call    cs:__imp_CoCreateInstance
0x18004185a  mov     ebx, eax
0x18004185c  test    eax, eax
0x18004185e  jns     short loc_1800418B9
0x180041860  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180041866  mov     edx, ebx
0x180041868  mov     rcx, rax
0x18004186b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180041871  lea     rax, WPP_GLOBAL_Control
0x180041878  mov     rcx, cs:WPP_GLOBAL_Control
0x18004187f  cmp     rcx, rax
0x180041882  jz      loc_180041A2F
0x180041888  test    byte ptr [rcx+1Ch], 1
0x18004188c  jz      loc_180041A2F
0x180041892  cmp     byte ptr [rcx+19h], 2
0x180041896  jb      loc_180041A2F
0x18004189c  mov     edx, 0Dh
0x1800418a1  mov     r9d, ebx
0x1800418a4  lea     r8, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids
0x1800418ab  mov     rcx, [rcx+10h]
0x1800418af  call    WPP_SF_d
0x1800418b4  jmp     loc_180041A2F
0x1800418b9  mov     rcx, [rsp+68h+pProxy]; pProxy
0x1800418be  mov     [rsp+68h+var_28], 0
0x1800418c3  mov     [rsp+68h+var_20], rcx
0x1800418c8  lea     rax, ??_9IUnknown@@$BBA@AA; [thunk]: IUnknown::`vcall'{16,{flat}}
0x1800418cf  mov     [rsp+68h+var_18], rax
0x1800418d4  mov     [rsp+68h+dwCapabilities], 20h ; ' '; dwCapabilities
0x1800418dc  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x1800418e5  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x1800418ed  mov     dword ptr [rsp+68h+ppv], 0; dwAuthnLevel
0x1800418f5  xor     r9d, r9d; pServerPrincName
0x1800418f8  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800418fb  mov     r8d, edx; dwAuthzSvc
0x1800418fe  call    cs:__imp_CoSetProxyBlanket
0x180041904  mov     ebx, eax
0x180041906  test    eax, eax
0x180041908  jns     short loc_180041962
0x18004190a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180041910  mov     edx, ebx
0x180041912  mov     rcx, rax
0x180041915  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004191b  lea     rax, WPP_GLOBAL_Control
0x180041922  mov     rcx, cs:WPP_GLOBAL_Control
0x180041929  cmp     rcx, rax
0x18004192c  jz      short loc_180041953
0x18004192e  test    byte ptr [rcx+1Ch], 1
0x180041932  jz      short loc_180041953
0x180041934  cmp     byte ptr [rcx+19h], 2
0x180041938  jb      short loc_180041953
0x18004193a  mov     edx, 0Eh
0x18004193f  mov     r9d, ebx
0x180041942  lea     r8, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids
0x180041949  mov     rcx, [rcx+10h]
0x18004194d  call    WPP_SF_d
0x180041952  nop
0x180041953  lea     rcx, [rsp+68h+var_28]
0x180041958  call    ??1?$ObjScopeGuardImpl0@VCLock@@P81@EAAHXZ@@QEAA@XZ; ObjScopeGuardImpl0<CLock,int (CLock::*)(void)>::~ObjScopeGuardImpl0<CLock,int (CLock::*)(void)>(void)
0x18004195d  jmp     loc_180041A2F
0x180041962  mov     rcx, [rsp+68h+pProxy]
0x180041967  mov     rax, [rcx]
0x18004196a  mov     rax, [rax+28h]
0x18004196e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041973  mov     ebx, eax
0x180041975  test    eax, eax
0x180041977  jns     short loc_1800419B0
0x180041979  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004197f  mov     edx, ebx
0x180041981  mov     rcx, rax
0x180041984  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004198a  lea     rax, WPP_GLOBAL_Control
0x180041991  mov     rcx, cs:WPP_GLOBAL_Control
0x180041998  cmp     rcx, rax
0x18004199b  jz      short loc_180041953
0x18004199d  test    byte ptr [rcx+1Ch], 1
0x1800419a1  jz      short loc_180041953
0x1800419a3  cmp     byte ptr [rcx+19h], 2
0x1800419a7  jb      short loc_180041953
0x1800419a9  mov     edx, 0Fh
0x1800419ae  jmp     short loc_18004193F
0x1800419b0  mov     rcx, rdi; unsigned __int16 *
0x1800419b3  call    ?PerformAllValidations@@YAJPEBG@Z; PerformAllValidations(ushort const *)
0x1800419b8  mov     rcx, [rsp+68h+pProxy]
0x1800419bd  mov     rax, [rcx]
0x1800419c0  mov     rax, [rax+30h]
0x1800419c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800419c9  mov     ebx, 80041069h
0x1800419ce  cmp     eax, ebx
0x1800419d0  jnz     short loc_180041A1E
0x1800419d2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800419d8  mov     edx, ebx
0x1800419da  mov     rcx, rax
0x1800419dd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800419e3  lea     rax, WPP_GLOBAL_Control
0x1800419ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800419f1  cmp     rcx, rax
0x1800419f4  jz      loc_180041953
0x1800419fa  test    byte ptr [rcx+1Ch], 1
0x1800419fe  jz      loc_180041953
0x180041a04  cmp     byte ptr [rcx+19h], 2
0x180041a08  jb      loc_180041953
0x180041a0e  mov     edx, 10h
0x180041a13  mov     r9d, 80041069h
0x180041a19  jmp     loc_180041942
0x180041a1e  xor     ebx, ebx
0x180041a20  lea     rcx, [rsp+68h+var_28]
0x180041a25  call    ??1?$ObjScopeGuardImpl0@VCLock@@P81@EAAHXZ@@QEAA@XZ; ObjScopeGuardImpl0<CLock,int (CLock::*)(void)>::~ObjScopeGuardImpl0<CLock,int (CLock::*)(void)>(void)
0x180041a2a  call    ?ReportFutureCorruption@@YAJXZ; ReportFutureCorruption(void)
0x180041a2f  mov     eax, ebx
0x180041a31  mov     rbx, [rsp+68h+arg_0]
0x180041a36  add     rsp, 60h
0x180041a3a  pop     rdi
0x180041a3b  retn
```
