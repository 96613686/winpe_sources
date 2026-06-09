# CDefragService::Run(void)

- ea: `0x18001457c`
- end: `0x1800146b1`
- name: `?Run@CDefragService@@QEAAJXZ`
- size: `309`
- prototype: `__int64 __fastcall(CDefragService *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800271f8`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001457c`
- `0x1800146b8`
- `0x1800147c4`
- `0x18001a630`
- `0x18004a92c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001461d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001461d`

## string_xrefs

- `0x180014595`: `CDefragService::Run`
- `0x1800145a6`: `SeBackupPrivilege`
- `0x1800145d3`: `SeManageVolumePrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDefragService::Run(CDefragService *this)
{
  __int16 v1; // ax
  int LastFailureAsHRESULT; // ebx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  const char *v9; // r9
  int v11; // [rsp+20h] [rbp-40h] BYREF
  __int16 v12; // [rsp+24h] [rbp-3Ch]
  __int16 v13; // [rsp+26h] [rbp-3Ah]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "CDefragService::Run", 414, 1);
  v11 = AssertPrivilege(L"SeBackupPrivilege");
  v1 = 418;
  if ( v11 < 0 || (v12 = 418, v11 = AssertPrivilege(L"SeManageVolumePrivilege"), v1 = 419, v11 < 0) )
  {
    LastFailureAsHRESULT = -2147024891;
    v11 = -2147024891;
LABEL_3:
    v13 = v1;
    goto LABEL_15;
  }
  v12 = 419;
  LOBYTE(v4) = 2;
  LastFailureAsHRESULT = SxSetProcessPriorities(v3, 5, v4);
  v11 = LastFailureAsHRESULT;
  v1 = 422;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v12 = 422;
  if ( hTimer )
  {
    if ( WaitForSingleObject(hTimer, 0xFFFFFFFF) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6, v5, v7, v8);
      v11 = LastFailureAsHRESULT;
      v1 = 428;
      goto LABEL_3;
    }
    LastFailureAsHRESULT = 0;
    v11 = 0;
    v12 = 428;
  }
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    v9 = "Shutdown";
    if ( !dword_180089AD8 )
      v9 = "Idle timeout";
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_9dfa55146e94391ee67982bf00c934b1_Traceguids, v9);
    LastFailureAsHRESULT = v11;
  }
LABEL_15:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001457c  mov     [rsp-8+arg_0], rbx
0x180014581  push    rbp
0x180014582  mov     rbp, rsp
0x180014585  sub     rsp, 60h
0x180014589  mov     r9d, 1; unsigned __int16
0x18001458f  mov     r8d, 19Eh; unsigned __int16
0x180014595  lea     rdx, aCdefragservice_4; "CDefragService::Run"
0x18001459c  lea     rcx, [rbp+var_40]; this
0x1800145a0  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800145a5  nop
0x1800145a6  lea     rcx, Name; "SeBackupPrivilege"
0x1800145ad  call    ?AssertPrivilege@@YAJPEBG@Z; AssertPrivilege(ushort const *)
0x1800145b2  mov     [rbp+var_40], eax
0x1800145b5  test    eax, eax
0x1800145b7  mov     eax, 1A2h
0x1800145bc  jns     short loc_1800145CF
0x1800145be  mov     ebx, 80070005h
0x1800145c3  mov     [rbp+var_40], ebx
0x1800145c6  mov     [rbp+var_3A], ax
0x1800145ca  jmp     loc_18001469B
0x1800145cf  mov     [rbp+var_3C], ax
0x1800145d3  lea     rcx, aSemanagevolume; "SeManageVolumePrivilege"
0x1800145da  call    ?AssertPrivilege@@YAJPEBG@Z; AssertPrivilege(ushort const *)
0x1800145df  mov     [rbp+var_40], eax
0x1800145e2  test    eax, eax
0x1800145e4  mov     eax, 1A3h
0x1800145e9  js      short loc_1800145BE
0x1800145eb  mov     [rbp+var_3C], ax
0x1800145ef  mov     r8b, 2
0x1800145f2  mov     edx, 5
0x1800145f7  call    ?SxSetProcessPriorities@@YAJW4_IO_PRIORITY_HINT@@KE@Z; SxSetProcessPriorities(_IO_PRIORITY_HINT,ulong,uchar)
0x1800145fc  mov     ebx, eax
0x1800145fe  mov     [rbp+var_40], eax
0x180014601  test    eax, eax
0x180014603  mov     eax, 1A6h
0x180014608  js      short loc_1800145C6
0x18001460a  mov     [rbp+var_3C], ax
0x18001460e  mov     rcx, cs:hTimer; hHandle
0x180014615  test    rcx, rcx
0x180014618  jz      short loc_180014646
0x18001461a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001461d  call    cs:__imp_WaitForSingleObject
0x180014623  test    eax, eax
0x180014625  jz      short loc_180014638
0x180014627  call    GetLastFailureAsHRESULT
0x18001462c  mov     ebx, eax
0x18001462e  mov     [rbp+var_40], eax
0x180014631  mov     eax, 1ACh
0x180014636  jmp     short loc_1800145C6
0x180014638  xor     ebx, ebx
0x18001463a  mov     [rbp+var_40], ebx
0x18001463d  mov     eax, 1ACh
0x180014642  mov     [rbp+var_3C], ax
0x180014646  lea     rcx, WPP_GLOBAL_Control
0x18001464d  mov     rax, cs:WPP_GLOBAL_Control
0x180014654  cmp     rax, rcx
0x180014657  jz      short loc_18001469B
0x180014659  test    dword ptr [rax+1Ch], 8000000h
0x180014660  jz      short loc_18001469B
0x180014662  mov     eax, cs:dword_180089AD8
0x180014668  lea     rcx, aIdleTimeout; "Idle timeout"
0x18001466f  lea     r9, aShutdown; "Shutdown"
0x180014676  test    eax, eax
0x180014678  cmovz   r9, rcx
0x18001467c  mov     edx, 0Eh
0x180014681  lea     r8, WPP_9dfa55146e94391ee67982bf00c934b1_Traceguids
0x180014688  mov     rcx, cs:WPP_GLOBAL_Control
0x18001468f  mov     rcx, [rcx+10h]
0x180014693  call    WPP_SF_s
0x180014698  mov     ebx, [rbp+var_40]
0x18001469b  lea     rcx, [rbp+var_40]; this
0x18001469f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800146a4  mov     eax, ebx
0x1800146a6  mov     rbx, [rsp+60h+arg_0]
0x1800146ab  add     rsp, 60h
0x1800146af  pop     rbp
0x1800146b0  retn
```
