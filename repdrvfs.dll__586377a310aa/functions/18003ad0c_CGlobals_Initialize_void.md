# CGlobals::Initialize(void)

- ea: `0x18003ad0c`
- end: `0x18003b05d`
- name: `?Initialize@CGlobals@@QEAAJXZ`
- size: `849`
- prototype: `__int64 __fastcall(CGlobals *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003b064`

## callees

- `0x1800012b8`
- `0x180029fbc`
- `0x18003ad0c`
- `0x18003e018`
- `0x180048010`

## import_xrefs

- `wbemcomn!?CoGetClassObject@CWbemInstallObject@@SAJAEBU_GUID@@KPEAU_COSERVERINFO@@0PEAPEAX@Z` at `0x18003adab`
- `wbemcomn!?CoGetClassObject@CWbemInstallObject@@SAJAEBU_GUID@@KPEAU_COSERVERINFO@@0PEAPEAX@Z` at `0x18003ae63`
- `wbemcomn!?CoGetClassObject@CWbemInstallObject@@SAJAEBU_GUID@@KPEAU_COSERVERINFO@@0PEAPEAX@Z` at `0x18003adab`
- `wbemcomn!?CoGetClassObject@CWbemInstallObject@@SAJAEBU_GUID@@KPEAU_COSERVERINFO@@0PEAPEAX@Z` at `0x18003ae63`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003ad26`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003ad26`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003b049`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003b049`
- `wbemcomn!GetMemLogObject` at `0x18003adb7`
- `wbemcomn!GetMemLogObject` at `0x18003ae6f`
- `wbemcomn!GetMemLogObject` at `0x18003af16`
- `wbemcomn!GetMemLogObject` at `0x18003af90`
- `wbemcomn!GetMemLogObject` at `0x18003adb7`
- `wbemcomn!GetMemLogObject` at `0x18003ae6f`
- `wbemcomn!GetMemLogObject` at `0x18003af16`
- `wbemcomn!GetMemLogObject` at `0x18003af90`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003adc2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ae7a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003af21`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003af9b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003adc2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ae7a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003af21`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003af9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003b00f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003b00f`
- `ntdll!RtlNtStatusToDosError` at `0x18003ad44`
- `ntdll!RtlNtStatusToDosError` at `0x18003ad44`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CGlobals::Initialize(CGlobals *this)
{
  signed int ClassObject; // ebx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v4; // rax
  CMemoryLog *v5; // rax
  CMemoryLog *v6; // rax
  char v8[8]; // [rsp+30h] [rbp-30h] BYREF
  __int64 (__fastcall *v9)(); // [rsp+38h] [rbp-28h]
  struct IClassFactory **v10; // [rsp+40h] [rbp-20h]
  char v11[8]; // [rsp+48h] [rbp-18h] BYREF
  __int64 (__fastcall *v12)(); // [rsp+50h] [rbp-10h]
  struct IClassFactory **v13; // [rsp+58h] [rbp-8h]
  DWORD nSize; // [rsp+90h] [rbp+30h] BYREF
  __int64 v15; // [rsp+98h] [rbp+38h] BYREF
  char v16; // [rsp+A0h] [rbp+40h] BYREF
  __int64 *v17; // [rsp+A8h] [rbp+48h]

  CInCritSec::CInCritSec((CInCritSec *)&v16, (struct _RTL_CRITICAL_SECTION *)((char *)this + 8));
  if ( *(_DWORD *)this )
    goto LABEL_38;
  if ( !g_ShutDownFlags )
  {
    v11[0] = 0;
    v12 = FactoryReleaseAndClean;
    v13 = &g_pCoreSvcFac;
    v8[0] = 0;
    v9 = FactoryReleaseAndClean;
    v10 = &g_pWbemCobjFac;
    v15 = 0;
    v17 = &v15;
    ClassObject = CWbemInstallObject::CoGetClassObject(
                    &CLSID_IWmiCoreServices,
                    1u,
                    0,
                    &IID_IClassFactory,
                    (void **)&g_pCoreSvcFac);
    if ( ClassObject < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, ClassObject);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          86,
          WPP_53e1474670223052d7bc731b72ed24d6_Traceguids,
          (unsigned int)ClassObject);
      }
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v15 = 0;
LABEL_12:
      ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v8);
      ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v11);
      goto LABEL_39;
    }
    ((void (__fastcall *)(struct IClassFactory *, __int64))g_pCoreSvcFac->lpVtbl->LockServer)(g_pCoreSvcFac, 1);
    ClassObject = CWbemInstallObject::CoGetClassObject(
                    &CLSID_WbemClassObject,
                    1u,
                    0,
                    &IID_IClassFactory,
                    (void **)&g_pWbemCobjFac);
    if ( ClassObject < 0 )
    {
      v4 = GetMemLogObject();
      CMemoryLog::Write(v4, ClassObject);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          87,
          WPP_53e1474670223052d7bc731b72ed24d6_Traceguids,
          (unsigned int)ClassObject);
      }
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v15 = 0;
      goto LABEL_12;
    }
    ((void (__fastcall *)(struct IClassFactory *, __int64))g_pWbemCobjFac->lpVtbl->LockServer)(g_pWbemCobjFac, 1);
    ClassObject = ((__int64 (__fastcall *)(struct IClassFactory *, _QWORD, GUID *, __int64 *))g_pCoreSvcFac->lpVtbl->CreateInstance)(
                    g_pCoreSvcFac,
                    0,
                    &IID__IWmiCoreServices,
                    &v15);
    if ( ClassObject < 0 )
    {
      v5 = GetMemLogObject();
      CMemoryLog::Write(v5, ClassObject);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          88,
          WPP_53e1474670223052d7bc731b72ed24d6_Traceguids,
          (unsigned int)ClassObject);
      }
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v15 = 0;
      goto LABEL_12;
    }
    ClassObject = CForestCache::Initialize((CGlobals *)((char *)this + 64));
    if ( ClassObject < 0 )
    {
      v6 = GetMemLogObject();
      CMemoryLog::Write(v6, ClassObject);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          89,
          WPP_53e1474670223052d7bc731b72ed24d6_Traceguids,
          (unsigned int)ClassObject);
      }
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v15 = 0;
      goto LABEL_12;
    }
    nSize = 16;
    GetComputerNameExW(ComputerNameNetBIOS, (LPWSTR)this + 1974, &nSize);
    *((_QWORD *)this + 7) = v15;
    v11[0] = 1;
    v8[0] = 1;
    *(_DWORD *)this = 1;
    v15 = 0;
    ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v8);
    ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v11);
LABEL_38:
    ClassObject = 0;
    goto LABEL_39;
  }
  ClassObject = RtlNtStatusToDosError(-1073741431);
LABEL_39:
  CInCritSec::~CInCritSec((CInCritSec *)&v16);
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x18003ad0c  push    rbp
0x18003ad0e  push    rbx
0x18003ad0f  push    rdi
0x18003ad10  push    r14
0x18003ad12  push    r15
0x18003ad14  mov     rbp, rsp
0x18003ad17  sub     rsp, 60h
0x18003ad1b  mov     rdi, rcx
0x18003ad1e  lea     rdx, [rcx+8]
0x18003ad22  lea     rcx, [rbp+arg_10]
0x18003ad26  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18003ad2c  nop
0x18003ad2d  cmp     dword ptr [rdi], 0
0x18003ad30  jnz     loc_18003B043
0x18003ad36  cmp     cs:?g_ShutDownFlags@@3KA, 0; ulong g_ShutDownFlags
0x18003ad3d  jz      short loc_18003AD51
0x18003ad3f  mov     ecx, 0C0000189h; Status
0x18003ad44  call    cs:__imp_RtlNtStatusToDosError
0x18003ad4a  mov     ebx, eax
0x18003ad4c  jmp     loc_18003B045
0x18003ad51  mov     [rbp+var_18], 0
0x18003ad55  lea     rax, FactoryReleaseAndClean
0x18003ad5c  mov     [rbp+var_10], rax
0x18003ad60  lea     rcx, ?g_pCoreSvcFac@@3PEAUIClassFactory@@EA; IClassFactory * g_pCoreSvcFac
0x18003ad67  mov     [rbp+var_8], rcx
0x18003ad6b  mov     [rbp+var_30], 0
0x18003ad6f  mov     [rbp+var_28], rax
0x18003ad73  lea     r15, ?g_pWbemCobjFac@@3PEAUIClassFactory@@EA; IClassFactory * g_pWbemCobjFac
0x18003ad7a  mov     [rbp+var_20], r15
0x18003ad7e  mov     [rbp+arg_8], 0
0x18003ad86  lea     rax, [rbp+arg_8]
0x18003ad8a  mov     [rbp+arg_18], rax
0x18003ad8e  mov     [rsp+60h+var_40], rcx
0x18003ad93  lea     r9, IID_IClassFactory
0x18003ad9a  xor     r8d, r8d
0x18003ad9d  lea     r14d, [r8+1]
0x18003ada1  mov     edx, r14d
0x18003ada4  lea     rcx, CLSID_IWmiCoreServices
0x18003adab  call    cs:__imp_?CoGetClassObject@CWbemInstallObject@@SAJAEBU_GUID@@KPEAU_COSERVERINFO@@0PEAPEAX@Z; CWbemInstallObject::CoGetClassObject(_GUID const &,ulong,_COSERVERINFO *,_GUID const &,void * *)
0x18003adb1  mov     ebx, eax
0x18003adb3  test    eax, eax
0x18003adb5  jns     short loc_18003AE34
0x18003adb7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003adbd  mov     edx, ebx
0x18003adbf  mov     rcx, rax
0x18003adc2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003adc8  lea     rax, WPP_GLOBAL_Control
0x18003adcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003add6  cmp     rcx, rax
0x18003add9  jz      short loc_18003ADFF
0x18003addb  test    [rcx+1Ch], r14b
0x18003addf  jz      short loc_18003ADFF
0x18003ade1  cmp     byte ptr [rcx+19h], 2
0x18003ade5  jb      short loc_18003ADFF
0x18003ade7  lea     edx, [r14+55h]
0x18003adeb  mov     r9d, ebx
0x18003adee  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003adf5  mov     rcx, [rcx+10h]
0x18003adf9  call    WPP_SF_d
0x18003adfe  nop
0x18003adff  mov     rcx, [rbp+arg_8]
0x18003ae03  test    rcx, rcx
0x18003ae06  jz      short loc_18003AE14
0x18003ae08  mov     rax, [rcx]
0x18003ae0b  mov     rax, [rax+10h]
0x18003ae0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae14  mov     [rbp+arg_8], 0
0x18003ae1c  lea     rcx, [rbp+var_30]
0x18003ae20  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18003ae25  nop
0x18003ae26  lea     rcx, [rbp+var_18]
0x18003ae2a  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18003ae2f  jmp     loc_18003B045
0x18003ae34  mov     rcx, cs:?g_pCoreSvcFac@@3PEAUIClassFactory@@EA; IClassFactory * g_pCoreSvcFac
0x18003ae3b  mov     rax, [rcx]
0x18003ae3e  mov     edx, r14d
0x18003ae41  mov     rax, [rax+20h]
0x18003ae45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae4a  mov     [rsp+60h+var_40], r15
0x18003ae4f  lea     r9, IID_IClassFactory
0x18003ae56  xor     r8d, r8d
0x18003ae59  mov     edx, r14d
0x18003ae5c  lea     rcx, CLSID_WbemClassObject
0x18003ae63  call    cs:__imp_?CoGetClassObject@CWbemInstallObject@@SAJAEBU_GUID@@KPEAU_COSERVERINFO@@0PEAPEAX@Z; CWbemInstallObject::CoGetClassObject(_GUID const &,ulong,_COSERVERINFO *,_GUID const &,void * *)
0x18003ae69  mov     ebx, eax
0x18003ae6b  test    eax, eax
0x18003ae6d  jns     short loc_18003AEDA
0x18003ae6f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003ae75  mov     edx, ebx
0x18003ae77  mov     rcx, rax
0x18003ae7a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003ae80  lea     rax, WPP_GLOBAL_Control
0x18003ae87  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ae8e  cmp     rcx, rax
0x18003ae91  jz      short loc_18003AEB8
0x18003ae93  test    [rcx+1Ch], r14b
0x18003ae97  jz      short loc_18003AEB8
0x18003ae99  cmp     byte ptr [rcx+19h], 2
0x18003ae9d  jb      short loc_18003AEB8
0x18003ae9f  mov     edx, 57h ; 'W'
0x18003aea4  mov     r9d, ebx
0x18003aea7  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003aeae  mov     rcx, [rcx+10h]
0x18003aeb2  call    WPP_SF_d
0x18003aeb7  nop
0x18003aeb8  mov     rcx, [rbp+arg_8]
0x18003aebc  test    rcx, rcx
0x18003aebf  jz      short loc_18003AECD
0x18003aec1  mov     rax, [rcx]
0x18003aec4  mov     rax, [rax+10h]
0x18003aec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aecd  mov     [rbp+arg_8], 0
0x18003aed5  jmp     loc_18003AE1C
0x18003aeda  mov     rcx, cs:?g_pWbemCobjFac@@3PEAUIClassFactory@@EA; IClassFactory * g_pWbemCobjFac
0x18003aee1  mov     rax, [rcx]
0x18003aee4  mov     edx, r14d
0x18003aee7  mov     rax, [rax+20h]
0x18003aeeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aef0  mov     rcx, cs:?g_pCoreSvcFac@@3PEAUIClassFactory@@EA; IClassFactory * g_pCoreSvcFac
0x18003aef7  mov     rax, [rcx]
0x18003aefa  lea     r9, [rbp+arg_8]
0x18003aefe  lea     r8, IID__IWmiCoreServices
0x18003af05  xor     edx, edx
0x18003af07  mov     rax, [rax+18h]
0x18003af0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af10  mov     ebx, eax
0x18003af12  test    eax, eax
0x18003af14  jns     short loc_18003AF81
0x18003af16  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003af1c  mov     edx, ebx
0x18003af1e  mov     rcx, rax
0x18003af21  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003af27  lea     rax, WPP_GLOBAL_Control
0x18003af2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003af35  cmp     rcx, rax
0x18003af38  jz      short loc_18003AF5F
0x18003af3a  test    [rcx+1Ch], r14b
0x18003af3e  jz      short loc_18003AF5F
0x18003af40  cmp     byte ptr [rcx+19h], 2
0x18003af44  jb      short loc_18003AF5F
0x18003af46  mov     edx, 58h ; 'X'
0x18003af4b  mov     r9d, ebx
0x18003af4e  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003af55  mov     rcx, [rcx+10h]
0x18003af59  call    WPP_SF_d
0x18003af5e  nop
0x18003af5f  mov     rcx, [rbp+arg_8]
0x18003af63  test    rcx, rcx
0x18003af66  jz      short loc_18003AF74
0x18003af68  mov     rax, [rcx]
0x18003af6b  mov     rax, [rax+10h]
0x18003af6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af74  mov     [rbp+arg_8], 0
0x18003af7c  jmp     loc_18003AE1C
0x18003af81  lea     rcx, [rdi+40h]; this
0x18003af85  call    ?Initialize@CForestCache@@QEAAJXZ; CForestCache::Initialize(void)
0x18003af8a  mov     ebx, eax
0x18003af8c  test    eax, eax
0x18003af8e  jns     short loc_18003AFFB
0x18003af90  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003af96  mov     edx, ebx
0x18003af98  mov     rcx, rax
0x18003af9b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003afa1  lea     rax, WPP_GLOBAL_Control
0x18003afa8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003afaf  cmp     rcx, rax
0x18003afb2  jz      short loc_18003AFD9
0x18003afb4  test    [rcx+1Ch], r14b
0x18003afb8  jz      short loc_18003AFD9
0x18003afba  cmp     byte ptr [rcx+19h], 2
0x18003afbe  jb      short loc_18003AFD9
0x18003afc0  mov     edx, 59h ; 'Y'
0x18003afc5  mov     r9d, ebx
0x18003afc8  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003afcf  mov     rcx, [rcx+10h]
0x18003afd3  call    WPP_SF_d
0x18003afd8  nop
0x18003afd9  mov     rcx, [rbp+arg_8]
0x18003afdd  test    rcx, rcx
0x18003afe0  jz      short loc_18003AFEE
0x18003afe2  mov     rax, [rcx]
0x18003afe5  mov     rax, [rax+10h]
0x18003afe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afee  mov     [rbp+arg_8], 0
0x18003aff6  jmp     loc_18003AE1C
0x18003affb  mov     [rbp+nSize], 10h
0x18003b002  lea     rdx, [rdi+0F6Ch]; lpBuffer
0x18003b009  lea     r8, [rbp+nSize]; nSize
0x18003b00d  xor     ecx, ecx; NameType
0x18003b00f  call    cs:__imp_GetComputerNameExW
0x18003b015  mov     rax, [rbp+arg_8]
0x18003b019  mov     [rdi+38h], rax
0x18003b01d  mov     [rbp+var_18], r14b
0x18003b021  mov     [rbp+var_30], r14b
0x18003b025  mov     [rdi], r14d
0x18003b028  mov     [rbp+arg_8], 0
0x18003b030  lea     rcx, [rbp+var_30]
0x18003b034  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18003b039  nop
0x18003b03a  lea     rcx, [rbp+var_18]
0x18003b03e  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18003b043  xor     ebx, ebx
0x18003b045  lea     rcx, [rbp+arg_10]
0x18003b049  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18003b04f  mov     eax, ebx
0x18003b051  add     rsp, 60h
0x18003b055  pop     r15
0x18003b057  pop     r14
0x18003b059  pop     rdi
0x18003b05a  pop     rbx
0x18003b05b  pop     rbp
0x18003b05c  retn
```
