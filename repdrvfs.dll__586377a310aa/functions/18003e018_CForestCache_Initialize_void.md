# CForestCache::Initialize(void)

- ea: `0x18003e018`
- end: `0x18003e1ea`
- name: `?Initialize@CForestCache@@QEAAJXZ`
- size: `466`
- prototype: `__int64 __fastcall(CForestCache *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003ad0c`

## callees

- `0x1800012b8`
- `0x180018c3c`
- `0x180024ca0`
- `0x180038e6c`
- `0x18003e018`
- `0x180044170`
- `0x180044208`

## import_xrefs

- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003e02d`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003e02d`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003e1da`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003e1da`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18003e046`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18003e046`
- `wbemcomn!?GetRegistryPathCIMOM@CWbemInstallObject@@SAPEBGXZ` at `0x18003e050`
- `wbemcomn!?GetRegistryPathCIMOM@CWbemInstallObject@@SAPEBGXZ` at `0x18003e050`
- `wbemcomn!?GetRegistryPathRoot@CWbemInstallObject@@SAPEAUHKEY__@@XZ` at `0x18003e059`
- `wbemcomn!?GetRegistryPathRoot@CWbemInstallObject@@SAPEAUHKEY__@@XZ` at `0x18003e059`
- `wbemcomn!GetMemLogObject` at `0x18003e098`
- `wbemcomn!GetMemLogObject` at `0x18003e098`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e0a3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e0a3`

## string_xrefs

- `0x18003e173`: `Max Class Cache Item Age (ms)`
- `0x18003e19e`: `Max Class Cache Item Age (ms)`
- `0x18003e11d`: `Max Class Cache Size`
- `0x18003e144`: `Max Class Cache Size`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CForestCache::Initialize(struct _RTL_CRITICAL_SECTION *this)
{
  int v2; // r8d
  int RegistryPathCIMOM; // ebx
  int RegistryPathRoot; // eax
  int v5; // r8d
  unsigned int v6; // eax
  int v7; // r8d
  unsigned int v8; // ebx
  CMemoryLog *MemLogObject; // rax
  int v10; // r8d
  int v11; // r8d
  __int64 v13; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v14[8]; // [rsp+38h] [rbp-8h] BYREF
  int v15; // [rsp+60h] [rbp+20h] BYREF
  int v16; // [rsp+68h] [rbp+28h] BYREF
  int v17; // [rsp+70h] [rbp+30h] BYREF
  __int64 v18; // [rsp+78h] [rbp+38h] BYREF

  CInCritSec::CInCritSec((CInCritSec *)v14, this);
  if ( this[2].RecursionCount )
  {
LABEL_15:
    v8 = 0;
    goto LABEL_16;
  }
  v18 = 0;
  if ( (unsigned __int8)CWbemInstallObject::IsOffline() )
  {
    RegistryPathCIMOM = CWbemInstallObject::GetRegistryPathCIMOM();
    RegistryPathRoot = CWbemInstallObject::GetRegistryPathRoot();
    v6 = DLRegOpenKeyExW(RegistryPathRoot, RegistryPathCIMOM, v5, 131103, (__int64)&v18);
  }
  else
  {
    v6 = DLRegOpenKeyExW(-2147483646, (unsigned int)L"SOFTWARE\\Microsoft\\WBEM\\CIMOM", v2, 131103, (__int64)&v18);
  }
  v8 = v6;
  if ( !v6 )
  {
    v13 = v18;
    v17 = 4;
    v15 = 0;
    if ( (unsigned int)DLRegQueryValueExW(
                         v18,
                         (unsigned int)L"Max Class Cache Size",
                         v7,
                         0,
                         (__int64)&v15,
                         (__int64)&v17) )
    {
      v15 = 5000000;
      DLRegSetValueExW(v18, (unsigned int)L"Max Class Cache Size", v10, 4, (__int64)&v15, 4);
    }
    v17 = 4;
    v16 = 0;
    if ( (unsigned int)DLRegQueryValueExW(
                         v18,
                         (unsigned int)L"Max Class Cache Item Age (ms)",
                         v10,
                         0,
                         (__int64)&v16,
                         (__int64)&v17) )
    {
      v16 = 120000;
      DLRegSetValueExW(v18, (unsigned int)L"Max Class Cache Item Age (ms)", v11, 4, (__int64)&v16, 4);
    }
    LODWORD(this[1].LockSemaphore) = v15;
    HIDWORD(this[1].LockSemaphore) = v16;
    CForestCache::MakeRoom((CForestCache *)this, 0);
    this[2].RecursionCount = 1;
    CRegCloseMe::~CRegCloseMe((CRegCloseMe *)&v13);
    goto LABEL_15;
  }
  MemLogObject = GetMemLogObject();
  CMemoryLog::Write(MemLogObject, v8);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_73e6a18982e8318987457e2893328bf6_Traceguids, v8);
  }
LABEL_16:
  CInCritSec::~CInCritSec((CInCritSec *)v14);
  return v8;
}

```

## disassembly

```asm
0x18003e018  push    rbp
0x18003e01a  push    rbx
0x18003e01b  push    rdi
0x18003e01c  mov     rbp, rsp
0x18003e01f  sub     rsp, 40h
0x18003e023  mov     rdi, rcx
0x18003e026  mov     rdx, rcx
0x18003e029  lea     rcx, [rbp+var_8]
0x18003e02d  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18003e033  nop
0x18003e034  cmp     dword ptr [rdi+5Ch], 0
0x18003e038  jnz     loc_18003E1D4
0x18003e03e  mov     [rbp+arg_18], 0
0x18003e046  call    cs:__imp_?IsOffline@CWbemInstallObject@@SA_NXZ; CWbemInstallObject::IsOffline(void)
0x18003e04c  test    al, al
0x18003e04e  jz      short loc_18003E070
0x18003e050  call    cs:__imp_?GetRegistryPathCIMOM@CWbemInstallObject@@SAPEBGXZ; CWbemInstallObject::GetRegistryPathCIMOM(void)
0x18003e056  mov     rbx, rax
0x18003e059  call    cs:__imp_?GetRegistryPathRoot@CWbemInstallObject@@SAPEAUHKEY__@@XZ; CWbemInstallObject::GetRegistryPathRoot(void)
0x18003e05f  lea     rcx, [rbp+arg_18]
0x18003e063  mov     [rsp+40h+var_20], rcx
0x18003e068  mov     rdx, rbx
0x18003e06b  mov     rcx, rax
0x18003e06e  jmp     short loc_18003E087
0x18003e070  lea     rax, [rbp+arg_18]
0x18003e074  mov     [rsp+40h+var_20], rax
0x18003e079  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WBEM\\CIMOM"
0x18003e080  mov     rcx, 0FFFFFFFF80000002h
0x18003e087  mov     r9d, 2001Fh
0x18003e08d  call    DLRegOpenKeyExW
0x18003e092  mov     ebx, eax
0x18003e094  test    eax, eax
0x18003e096  jz      short loc_18003E0F1
0x18003e098  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003e09e  mov     edx, ebx
0x18003e0a0  mov     rcx, rax
0x18003e0a3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e0a9  lea     rax, WPP_GLOBAL_Control
0x18003e0b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e0b7  cmp     rcx, rax
0x18003e0ba  jz      loc_18003E1D6
0x18003e0c0  test    byte ptr [rcx+1Ch], 1
0x18003e0c4  jz      loc_18003E1D6
0x18003e0ca  cmp     byte ptr [rcx+19h], 2
0x18003e0ce  jb      loc_18003E1D6
0x18003e0d4  mov     edx, 17h
0x18003e0d9  mov     r9d, ebx
0x18003e0dc  lea     r8, WPP_73e6a18982e8318987457e2893328bf6_Traceguids
0x18003e0e3  mov     rcx, [rcx+10h]
0x18003e0e7  call    WPP_SF_d
0x18003e0ec  jmp     loc_18003E1D6
0x18003e0f1  mov     rcx, [rbp+arg_18]
0x18003e0f5  mov     [rbp+var_10], rcx
0x18003e0f9  mov     ebx, 4
0x18003e0fe  mov     [rbp+arg_10], ebx
0x18003e101  mov     [rbp+arg_0], 0
0x18003e108  lea     rax, [rbp+arg_10]
0x18003e10c  mov     [rsp+40h+var_18], rax
0x18003e111  lea     rax, [rbp+arg_0]
0x18003e115  mov     [rsp+40h+var_20], rax
0x18003e11a  xor     r9d, r9d
0x18003e11d  lea     rdx, aMaxClassCacheS; "Max Class Cache Size"
0x18003e124  call    DLRegQueryValueExW
0x18003e129  test    eax, eax
0x18003e12b  jz      short loc_18003E154
0x18003e12d  mov     [rbp+arg_0], 4C4B40h
0x18003e134  mov     dword ptr [rsp+40h+var_18], ebx
0x18003e138  lea     rax, [rbp+arg_0]
0x18003e13c  mov     [rsp+40h+var_20], rax
0x18003e141  mov     r9d, ebx
0x18003e144  lea     rdx, aMaxClassCacheS; "Max Class Cache Size"
0x18003e14b  mov     rcx, [rbp+arg_18]
0x18003e14f  call    DLRegSetValueExW
0x18003e154  mov     [rbp+arg_10], ebx
0x18003e157  mov     [rbp+arg_8], 0
0x18003e15e  lea     rax, [rbp+arg_10]
0x18003e162  mov     [rsp+40h+var_18], rax
0x18003e167  lea     rax, [rbp+arg_8]
0x18003e16b  mov     [rsp+40h+var_20], rax
0x18003e170  xor     r9d, r9d
0x18003e173  lea     rdx, aMaxClassCacheI; "Max Class Cache Item Age (ms)"
0x18003e17a  mov     rcx, [rbp+arg_18]
0x18003e17e  call    DLRegQueryValueExW
0x18003e183  test    eax, eax
0x18003e185  jz      short loc_18003E1AE
0x18003e187  mov     [rbp+arg_8], 1D4C0h
0x18003e18e  mov     dword ptr [rsp+40h+var_18], ebx
0x18003e192  lea     rax, [rbp+arg_8]
0x18003e196  mov     [rsp+40h+var_20], rax
0x18003e19b  mov     r9d, ebx
0x18003e19e  lea     rdx, aMaxClassCacheI; "Max Class Cache Item Age (ms)"
0x18003e1a5  mov     rcx, [rbp+arg_18]
0x18003e1a9  call    DLRegSetValueExW
0x18003e1ae  mov     eax, [rbp+arg_0]
0x18003e1b1  mov     [rdi+40h], eax
0x18003e1b4  mov     eax, [rbp+arg_8]
0x18003e1b7  mov     [rdi+44h], eax
0x18003e1ba  xor     edx, edx; unsigned int
0x18003e1bc  mov     rcx, rdi; this
0x18003e1bf  call    ?MakeRoom@CForestCache@@QEAA_NK@Z; CForestCache::MakeRoom(ulong)
0x18003e1c4  mov     dword ptr [rdi+5Ch], 1
0x18003e1cb  lea     rcx, [rbp+var_10]; this
0x18003e1cf  call    ??1CRegCloseMe@@QEAA@XZ; CRegCloseMe::~CRegCloseMe(void)
0x18003e1d4  xor     ebx, ebx
0x18003e1d6  lea     rcx, [rbp+var_8]
0x18003e1da  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18003e1e0  mov     eax, ebx
0x18003e1e2  add     rsp, 40h
0x18003e1e6  pop     rdi
0x18003e1e7  pop     rbx
0x18003e1e8  pop     rbp
0x18003e1e9  retn
```
