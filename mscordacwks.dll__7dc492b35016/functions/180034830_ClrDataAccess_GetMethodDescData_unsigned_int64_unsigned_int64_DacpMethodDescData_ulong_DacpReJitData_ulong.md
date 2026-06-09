# ClrDataAccess::GetMethodDescData(unsigned __int64,unsigned __int64,DacpMethodDescData *,ulong,DacpReJitData *,ulong *)

- ea: `0x180034830`
- end: `0x180035181`
- name: `?GetMethodDescData@ClrDataAccess@@UEAAJ_K0PEAUDacpMethodDescData@@KPEAUDacpReJitData@@PEAK@Z`
- size: `2385`
- prototype: `int(ClrDataAccess *__hidden this, unsigned __int64, unsigned __int64, struct DacpMethodDescData *, unsigned int, struct DacpReJitData *, unsigned int *)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, installer_update`

## callees

- `0x18001df18`
- `0x180020e20`
- `0x180020f50`
- `0x1800210f0`
- `0x18002127c`
- `0x180022068`
- `0x180032a38`
- `0x1800347ac`
- `0x180034830`
- `0x180078e68`
- `0x180083c6c`
- `0x1800841b0`
- `0x18008a5a8`
- `0x18008a61c`
- `0x18008aa0c`
- `0x1800930c8`
- `0x180093280`
- `0x1800933dc`
- `0x1800f0d20`
- `0x1800f3020`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800348ea`
- `KERNEL32!EnterCriticalSection` at `0x1800348ea`
- `KERNEL32!LeaveCriticalSection` at `0x180035168`
- `KERNEL32!LeaveCriticalSection` at `0x180035168`
- `KERNEL32!HeapFree` at `0x180034eff`
- `KERNEL32!HeapFree` at `0x180034eff`
- `KERNEL32!GetProcessHeap` at `0x180034eea`
- `KERNEL32!GetProcessHeap` at `0x180034eea`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall ClrDataAccess::GetMethodDescData(
        ClrDataAccess *this,
        unsigned __int64 a2,
        __int64 a3,
        struct DacpMethodDescData *a4,
        unsigned int a5,
        struct DacpReJitData *a6,
        unsigned int *a7)
{
  unsigned __int64 v9; // rdi
  unsigned int v11; // ebx
  struct MethodDesc *v13; // rax
  MethodDesc *v14; // rax
  _BYTE *v15; // rax
  __int64 v16; // rdx
  BOOL v17; // eax
  _WORD *v18; // rax
  __int16 v19; // cx
  MethodDesc *v20; // rax
  MethodDesc *v21; // rax
  MethodDesc *v22; // rax
  unsigned __int64 AddrOfNativeCodeSlot; // rax
  unsigned __int8 *v24; // r14
  __int64 v25; // rdx
  void *v26; // rax
  unsigned __int64 *MethodTable; // rax
  void *v28; // rax
  __int64 v29; // rdx
  MethodDesc *v30; // rax
  struct Module *Module; // rax
  __int64 v32; // rdx
  MethodDesc *v33; // rax
  struct Module *v34; // rax
  _QWORD *v35; // rax
  __int64 v36; // rax
  int v37; // r13d
  struct ReJitInfo *v38; // rax
  struct DacpMethodDescData *v39; // r14
  __int64 v40; // r9
  unsigned __int64 *ReJitInfo; // rax
  struct ReJitInfo *v42; // rax
  bool v43; // r8
  unsigned int v44; // r14d
  __int64 v45; // rdx
  unsigned int v46; // r12d
  unsigned int v47; // r14d
  unsigned int v48; // r15d
  unsigned __int64 *v49; // rax
  void *v50; // rax
  struct ReJitInfo *v51; // r13
  void *v52; // r14
  HANDLE ProcessHeap; // rax
  void *v54; // rax
  _QWORD *v55; // rax
  struct DacpMethodDescData *v56; // rdi
  unsigned __int64 v57; // rcx
  char v58; // dl
  unsigned __int64 v59; // rcx
  FieldDesc *v60; // rax
  unsigned __int64 v61; // rdi
  void *v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rbx
  int v65; // edi
  struct Exception *v66; // rbx
  BOOL v67; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v69; // rcx
  __int64 v70; // [rsp+0h] [rbp-308h] BYREF
  int ReJITIDs; // [rsp+30h] [rbp-2D8h] BYREF
  unsigned int v72; // [rsp+34h] [rbp-2D4h]
  int *TargetAddrForHostAddr; // [rsp+38h] [rbp-2D0h] BYREF
  struct DacpMethodDescData *v74; // [rsp+40h] [rbp-2C8h]
  unsigned __int64 v75; // [rsp+48h] [rbp-2C0h] BYREF
  unsigned __int64 v76; // [rsp+50h] [rbp-2B8h]
  __int64 v77; // [rsp+58h] [rbp-2B0h] BYREF
  void *v78; // [rsp+60h] [rbp-2A8h]
  __int64 v79; // [rsp+68h] [rbp-2A0h]
  unsigned __int64 v80; // [rsp+70h] [rbp-298h]
  BOOL v81; // [rsp+78h] [rbp-290h]
  unsigned int v82; // [rsp+80h] [rbp-288h]
  int v83; // [rsp+84h] [rbp-284h]
  unsigned __int64 v84; // [rsp+88h] [rbp-280h] BYREF
  int v85; // [rsp+90h] [rbp-278h] BYREF
  __int64 v86; // [rsp+98h] [rbp-270h]
  __int64 v87; // [rsp+A0h] [rbp-268h]
  __int128 v88; // [rsp+B0h] [rbp-258h] BYREF
  __int64 v89; // [rsp+C0h] [rbp-248h]
  unsigned __int64 v90; // [rsp+D0h] [rbp-238h] BYREF
  unsigned __int64 v91; // [rsp+D8h] [rbp-230h] BYREF
  unsigned __int64 v92; // [rsp+E0h] [rbp-228h] BYREF
  ClrDataAccess *v93; // [rsp+E8h] [rbp-220h]
  __int64 v94; // [rsp+F0h] [rbp-218h]
  int v95; // [rsp+F8h] [rbp-210h]
  __int128 v96; // [rsp+100h] [rbp-208h]
  struct Exception *v97; // [rsp+118h] [rbp-1F0h]
  _QWORD v98[4]; // [rsp+120h] [rbp-1E8h] BYREF
  __int128 v99; // [rsp+140h] [rbp-1C8h]
  __int64 v100; // [rsp+150h] [rbp-1B8h] BYREF
  _QWORD v101[3]; // [rsp+158h] [rbp-1B0h] BYREF
  char v102; // [rsp+170h] [rbp-198h]
  unsigned __int64 v103; // [rsp+178h] [rbp-190h]
  char v104; // [rsp+180h] [rbp-188h] BYREF
  __int128 v105; // [rsp+190h] [rbp-178h]
  int v106; // [rsp+1A0h] [rbp-168h] BYREF
  unsigned int v107; // [rsp+1A4h] [rbp-164h]
  int v108; // [rsp+1A8h] [rbp-160h]
  LPVOID lpMem; // [rsp+1B0h] [rbp-158h]
  char v110; // [rsp+1B8h] [rbp-150h] BYREF

  v79 = (__int64)a4;
  v9 = a2;
  v74 = a4;
  v72 = a5;
  v78 = a6;
  v76 = (unsigned __int64)a7;
  v87 = (__int64)a7;
  v11 = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( a5 )
  {
    if ( !a6 )
      return 2147942487LL;
  }
  else if ( !a6 )
  {
    goto LABEL_7;
  }
  if ( !a7 )
    return 2147942487LL;
LABEL_7:
  EnterCriticalSection(&g_dacCritSec);
  v93 = g_dacImpl;
  g_dacImpl = (ClrDataAccess *)((char *)this - 16);
  ReJITIDs = 0;
  v97 = 0;
  try
  {
    try
    {
      TargetAddrForHostAddr = (int *)v9;
      v13 = (struct MethodDesc *)DacInstantiateTypeByAddressHelper(v9, 8u, 1, 1);
      if ( (unsigned int)DacValidateMD(v13) )
      {
        memset(a4, 0, 0x98u);
        if ( v78 )
          memset(v78, 0, 24LL * v72);
        if ( a7 )
          *a7 = 0;
        *((_QWORD *)a4 + 11) = a3;
        v14 = (MethodDesc *)DacInstantiateTypeByAddressHelper(v9, 8u, 1, 1);
        *(_DWORD *)a4 = MethodDesc::GetNativeCode(v14) != 0;
        v15 = DacInstantiateTypeByAddressHelper(v9, 8u, 1, 1);
        v17 = 0;
        if ( (v15[6] & 7) == 7 )
        {
          LOBYTE(v16) = 1;
          TargetAddrForHostAddr = (int *)DacGetTargetAddrForHostAddr(v15, v16);
          if ( (*((_DWORD *)DacInstantiateTypeByAddressHelper((unsigned __int64)TargetAddrForHostAddr, 0x28u, 1, 1) + 5)
              & 0x20000) != 0 )
            v17 = 1;
        }
        *((_DWORD *)a4 + 1) = v17;
        v18 = DacInstantiateTypeByAddressHelper(v9, 8u, 1, 1);
        v19 = v18[2];
        if ( (__int16)v18[3] >= 0 )
          v19 &= 0x3FFu;
        *((_WORD *)a4 + 4) = v19;
        v20 = (MethodDesc *)DacInstantiateTypeByAddressHelper(v9, 8u, 1, 1);
        if ( MethodDesc::GetNativeCode(v20) )
        {
          v21 = (MethodDesc *)DacInstantiateTypeByAddressHelper(v9, 8u, 1, 1);
          *((_QWORD *)a4 + 2) = MethodDesc::GetNativeCode(v21);
        }
        else
        {
          *((_QWORD *)a4 + 2) = -1;
        }
        if ( (*((_BYTE *)DacInstantiateTypeByAddressHelper(v9, 8u, 1, 1) + 3) & 8) != 0 )
        {
          v22 = (MethodDesc *)DacInstantiateTypeByAddressHelper(v9, 8u, 1, 1);
          AddrOfNativeCodeSlot = MethodDesc::GetAddrOfNativeCodeSlot(v22);
        }
        else
        {
          AddrOfNativeCodeSlot = 0;
        }
        *((_QWORD *)a4 + 3) = AddrOfNativeCodeSlot;
        v24 = (unsigned __int8 *)DacInstantiateTypeByAddressHelper(v9, 8u, 1, 1);
        LOBYTE(v25) = 1;
        TargetAddrForHostAddr = (int *)(DacGetTargetAddrForHostAddr(v24, v25) - 8LL * v24[2] - 24);
        *((_DWORD *)a4 + 14) = *(_WORD *)v24 & 0x3FFF
                             | ((*((_WORD *)DacInstantiateTypeByAddressHelper(
                                              (unsigned __int64)TargetAddrForHostAddr,
                                              0x18u,
                                              1,
                                              1)
                                 + 9)
                               & 0x3FF
                               | 0x1800) << 14);
        *((_QWORD *)a4 + 4) = v9;
        v26 = DacInstantiateTypeByAddressHelper(v9, 8u, 1, 1);
        MethodTable = (unsigned __int64 *)MethodDesc::GetMethodTable(v26, &TargetAddrForHostAddr);
        v28 = DacInstantiateTypeByAddressHelper(*MethodTable, 0x40u, 1, 1);
        LOBYTE(v29) = 1;
        *((_QWORD *)a4 + 5) = DacGetTargetAddrForHostAddr(v28, v29);
        v30 = (MethodDesc *)DacInstantiateTypeByAddressHelper(v9, 8u, 1, 1);
        Module = MethodDesc::GetModule(v30);
        LOBYTE(v32) = 1;
        *((_QWORD *)a4 + 6) = DacGetTargetAddrForHostAddr(Module, v32);
        v85 = 0;
        v86 = 0;
        try
        {
          try
          {
            TargetAddrForHostAddr = &v85;
            v33 = (MethodDesc *)DacInstantiateTypeByAddressHelper(v9, 8u, 1, 1);
            v34 = MethodDesc::GetModule(v33);
            v35 = DacInstantiateTypeByAddressHelper(*((_QWORD *)v34 + 6), 0x118u, 1, 1);
            v36 = DacInstantiateClassByVTable(v35[8]);
            v37 = v36 + 1280;
            TargetAddrForHostAddr = (int *)(v36 + 1280);
            v103 = v9;
            v101[1] = 0;
            v75 = v9;
            ReJitManager::FindNonRevertedReJitInfoHelper(v36 + 1280, (unsigned int)&v84, (unsigned int)&v75, 0, 0);
            v38 = (struct ReJitInfo *)DacInstantiateTypeByAddressHelper(v84, 0x38u, 1, 1);
            v39 = (struct DacpMethodDescData *)v79;
            if ( v38 )
              CopyReJitInfoToReJitData(v38, (struct DacpReJitData *)(v79 + 96));
            v40 = *((_QWORD *)v39 + 11);
            if ( v40 )
            {
              v84 = v9;
              ReJitInfo = (unsigned __int64 *)ReJitManager::FindReJitInfo(
                                                v37,
                                                (unsigned int)&v77,
                                                (unsigned int)&v84,
                                                v40,
                                                0);
              v42 = (struct ReJitInfo *)DacInstantiateTypeByAddressHelper(*ReJitInfo, 0x38u, 1, 1);
              if ( v42 )
                CopyReJitInfoToReJitData(v42, (struct DacpMethodDescData *)((char *)v39 + 120));
            }
            v90 = v9;
            if ( (int)ReJitManager::GetReJITIDs(v37, (unsigned int)&v90, 0, (unsigned int)&v75, 0) >= 0 )
              *((_DWORD *)v39 + 36) = v75;
            if ( v78 )
            {
              v106 = 0;
              v108 = 0;
              lpMem = &v110;
              v107 = 256;
              v44 = 8 * v72 + 8;
              v45 = 256;
              if ( v44 > 0x100 )
              {
                SBuffer::ReallocateBuffer(&v106, v44, 1);
                v45 = v107;
              }
              v106 = 8 * v72 + 8;
              if ( (v108 & 0x10) != 0 )
                SBuffer::ReallocateBuffer(&v106, v45, 1);
              if ( lpMem )
              {
                v91 = v9;
                ReJITIDs = ReJitManager::GetReJITIDs(
                             v37,
                             (unsigned int)&v91,
                             v72 + 1,
                             (unsigned int)&v75,
                             (__int64)lpMem);
                if ( ReJITIDs >= 0 )
                {
                  v46 = v75;
                  v106 = 8 * v75;
                  v47 = 0;
                  v82 = 0;
                  v48 = 0;
                  v83 = 0;
                  while ( v48 < v46 && v47 < v72 )
                  {
                    v92 = v9;
                    v49 = (unsigned __int64 *)ReJitManager::FindReJitInfo(
                                                v37,
                                                (unsigned int)&v104,
                                                (unsigned int)&v92,
                                                0,
                                                *((_QWORD *)lpMem + v48));
                    v50 = DacInstantiateTypeByAddressHelper(*v49, 0x38u, 1, 1);
                    v51 = (struct ReJitInfo *)v50;
                    if ( v50
                      && (*(_BYTE *)DacInstantiateTypeByAddressHelper(*((_QWORD *)v50 + 4), 0x38u, 1, 1) & 0xF) == 3 )
                    {
                      CopyReJitInfoToReJitData(v51, (struct DacpReJitData *)((char *)v78 + 24 * v47++));
                      v82 = v47;
                    }
                    v83 = ++v48;
                    v37 = (int)TargetAddrForHostAddr;
                  }
                  *(_DWORD *)v76 = v47;
                }
              }
              if ( (v108 & 8) != 0 )
              {
                v52 = lpMem;
                if ( lpMem )
                {
                  ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
                  if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
                  {
                    ProcessHeap = GetProcessHeap();
                    `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
                  }
                  HeapFree(ProcessHeap, 0, v52);
                }
              }
              v39 = (struct DacpMethodDescData *)v79;
            }
            else if ( v76 )
            {
              *(_DWORD *)v76 = *((_DWORD *)v39 + 36);
            }
          }
          catch ( Exception *v100 )
          {
            Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v85);
            v86 = v100;
            throw;
          }
        }
        catch ( ... )
        {
          v98[1] = 0;
          v98[0] = &DelegatingException::`vftable';
          v98[2] = -1;
          v64 = v86;
          v94 = v86;
          v65 = 0;
          v95 = 0;
          if ( v86 )
          {
            v65 = 1;
            v95 = 1;
          }
          Exception::HandlerState::SetupCatch((Exception::HandlerState *)&v85, (int)&v70, v43);
          if ( v87 )
            *(_DWORD *)v87 = 0;
          if ( v65 )
          {
            if ( v64 && !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v64 + 80LL))(v64) )
              (**(void (__fastcall ***)(__int64, __int64))v64)(v64, 5);
            v95 = 0;
          }
          DelegatingException::~DelegatingException((DelegatingException *)v98);
          v11 = 0;
          v9 = a2;
          v39 = v74;
        }
        ReJITIDs = 0;
        if ( *((_DWORD *)v39 + 1) )
        {
          v77 = v9;
          v54 = DacInstantiateTypeByAddressHelper(v9, 0x28u, 1, 1);
          if ( v54 )
          {
            v74 = (struct DacpMethodDescData *)*((_QWORD *)v54 + 4);
            v55 = DacInstantiateTypeByAddressHelper((unsigned __int64)v74, 0x88u, 1, 1);
            if ( v55 )
            {
              v77 = v55[2];
              v56 = *(struct DacpMethodDescData **)DacInstantiateTypeByAddressHelper(v77, 8u, 1, 1);
              v74 = v56;
              if ( DacInstantiateTypeByAddressHelper((unsigned __int64)v56, 8u, 1, 1) )
              {
                v77 = (unsigned int)*g_Mscorlib[0] + DacGlobalBase();
                DacInstantiateTypeByAddressHelper(v77, 0x40u, 1, 1);
                v77 = (unsigned int)*g_Mscorlib[0] + DacGlobalBase();
                v57 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v77, 0x40u, 1, 1) + 3);
                v80 = v57;
                v58 = 0;
                LOBYTE(v81) = 0;
                *(_QWORD *)&v99 = 8;
                BYTE8(v99) = 0;
                v105 = v99;
                v101[2] = 19;
                v102 = 0;
                BYTE8(v96) = 0;
                v87 = 8;
                v79 = 19;
                *(_QWORD *)&v96 = 152;
                v88 = v96;
                if ( ~v57 >= 0x98 )
                {
                  v59 = v57 + 152;
                  v80 = v59;
                }
                else
                {
                  v58 = 1;
                  LOBYTE(v81) = 1;
                  v59 = 0;
                  v80 = 0;
                }
                if ( v58 )
                  DacError(-2146231242);
                v77 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v59, 8u, 1, 1);
                v60 = (FieldDesc *)DacInstantiateTypeByAddressHelper(v77, 0x10u, 1, 1);
                if ( !v60 )
                  v60 = (FieldDesc *)MscorlibBinder::LookupField();
                v78 = v56;
                v76 = 0;
                v74 = v56;
                FieldDesc::GetInstanceField(v60);
                v61 = v76;
                v74 = (struct DacpMethodDescData *)v76;
                if ( DacInstantiateTypeByAddressHelper(v76, 8u, 1, 1) )
                {
                  v62 = DacInstantiateTypeByAddressHelper(v61, 8u, 1, 1);
                  LOBYTE(v63) = 1;
                  *((_QWORD *)v39 + 10) = DacGetTargetAddrForHostAddr(v62, v63);
                }
              }
            }
          }
        }
      }
      else
      {
        v11 = -2147024809;
        ReJITIDs = -2147024809;
      }
    }
    catch ( Exception *v101 )
    {
      v97 = (struct Exception *)v101[0];
      throw;
    }
  }
  catch ( ... )
  {
    *((_QWORD *)&v88 + 1) = 0;
    *(_QWORD *)&v88 = &DelegatingException::`vftable';
    v89 = -1;
    v66 = v97;
    v80 = (unsigned __int64)v97;
    v67 = v97 != 0;
    v81 = v67;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v69 = (struct Exception *)&v88;
    if ( v66 )
      v69 = v66;
    if ( !DacExceptionFilter(v69, (ClrDataAccess *)((char *)this - 16), &ReJITIDs) )
    {
      v81 = 0;
      throw;
    }
    if ( v67 )
    {
      if ( v66 )
      {
        if ( !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v66 + 80LL))(v66) )
          (**(void (__fastcall ***)(struct Exception *, __int64))v66)(v66, 5);
      }
      v81 = 0;
    }
    DelegatingException::~DelegatingException((DelegatingException *)&v88);
    v11 = ReJITIDs;
  }
  g_dacImpl = v93;
  LeaveCriticalSection(&g_dacCritSec);
  return v11;
}

```

## disassembly

```asm
0x180034830  mov     [rsp+arg_8], rdx
0x180034835  mov     [rsp+arg_0], rcx
0x18003483a  push    rbx
0x18003483b  push    rsi
0x18003483c  push    rdi
0x18003483d  push    r12
0x18003483f  push    r13
0x180034841  push    r14
0x180034843  push    r15
0x180034845  sub     rsp, 2D0h
0x18003484c  mov     rax, cs:__security_cookie
0x180034853  xor     rax, rsp
0x180034856  mov     [rsp+308h+var_48], rax
0x18003485e  mov     r13, r9
0x180034861  mov     [rsp+308h+var_2A0], r9
0x180034866  mov     r14, r8
0x180034869  mov     rdi, rdx
0x18003486c  mov     rsi, rcx
0x18003486f  mov     [rsp+308h+var_2C8], r9
0x180034874  mov     ecx, [rsp+308h+arg_20]
0x18003487b  mov     [rsp+308h+var_2D4], ecx
0x18003487f  mov     rax, [rsp+308h+arg_28]
0x180034887  mov     [rsp+308h+var_2A8], rax
0x18003488c  mov     r15, [rsp+308h+arg_30]
0x180034894  mov     [rsp+308h+var_2B8], r15
0x180034899  mov     [rsp+308h+var_268], r15
0x1800348a1  xor     ebx, ebx
0x1800348a3  test    rdx, rdx
0x1800348a6  jz      short loc_1800348B1
0x1800348a8  test    ecx, ecx
0x1800348aa  jz      short loc_1800348D9
0x1800348ac  test    rax, rax
0x1800348af  jnz     short loc_1800348DE
0x1800348b1  mov     eax, 80070057h
0x1800348b6  mov     rcx, [rsp+308h+var_48]
0x1800348be  xor     rcx, rsp; StackCookie
0x1800348c1  call    __security_check_cookie
0x1800348c6  add     rsp, 2D0h
0x1800348cd  pop     r15
0x1800348cf  pop     r14
0x1800348d1  pop     r13
0x1800348d3  pop     r12
0x1800348d5  pop     rdi
0x1800348d6  pop     rsi
0x1800348d7  pop     rbx
0x1800348d8  retn
0x1800348d9  test    rax, rax
0x1800348dc  jz      short loc_1800348E3
0x1800348de  test    r15, r15
0x1800348e1  jz      short loc_1800348B1
0x1800348e3  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800348ea  call    cs:__imp_EnterCriticalSection
0x1800348f0  mov     rax, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x1800348f7  mov     [rsp+308h+var_220], rax
0x1800348ff  lea     rax, [rsi-10h]
0x180034903  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rax; ClrDataAccess * g_dacImpl
0x18003490a  mov     [rsp+308h+var_2D8], ebx
0x18003490e  mov     [rsp+308h+var_1F0], rbx
0x180034916  lea     rax, [rsp+308h+var_1F8]
0x18003491e  mov     [rsp+308h+var_2D0], rax
0x180034923  mov     [rsp+308h+var_2D0], rdi
0x180034928  mov     esi, 1
0x18003492d  mov     r9b, sil; bool
0x180034930  mov     r8b, sil; bool
0x180034933  lea     r12d, [rsi+7]
0x180034937  mov     edx, r12d; unsigned int
0x18003493a  mov     rcx, rdi; unsigned __int64
0x18003493d  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180034942  mov     rcx, rax; struct MethodDesc *
0x180034945  call    ?DacValidateMD@@YAHPEAVMethodDesc@@@Z; DacValidateMD(MethodDesc *)
0x18003494a  test    eax, eax
0x18003494c  jnz     short loc_18003495C
0x18003494e  mov     ebx, 80070057h
0x180034953  mov     [rsp+308h+var_2D8], ebx
0x180034957  jmp     loc_18003514C
0x18003495c  xor     edx, edx; Val
0x18003495e  mov     r8d, 98h; Size
0x180034964  mov     rcx, r13; void *
0x180034967  call    memset
0x18003496c  mov     rcx, [rsp+308h+var_2A8]; void *
0x180034971  test    rcx, rcx
0x180034974  jz      short loc_180034989
0x180034976  mov     eax, [rsp+308h+var_2D4]
0x18003497a  lea     r8, [rax+rax*2]
0x18003497e  shl     r8, 3; Size
0x180034982  xor     edx, edx; Val
0x180034984  call    memset
0x180034989  test    r15, r15
0x18003498c  jz      short loc_180034991
0x18003498e  mov     [r15], ebx
0x180034991  mov     [r13+58h], r14
0x180034995  mov     r9b, sil; bool
0x180034998  mov     r8b, sil; bool
0x18003499b  mov     edx, r12d; unsigned int
0x18003499e  mov     rcx, rdi; unsigned __int64
0x1800349a1  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800349a6  mov     rcx, rax; this
0x1800349a9  call    ?GetNativeCode@MethodDesc@@QEAA_KXZ; MethodDesc::GetNativeCode(void)
0x1800349ae  mov     ecx, ebx
0x1800349b0  test    rax, rax
0x1800349b3  setnz   cl
0x1800349b6  mov     [r13+0], ecx
0x1800349ba  mov     r9b, sil; bool
0x1800349bd  mov     r8b, sil; bool
0x1800349c0  mov     edx, r12d; unsigned int
0x1800349c3  mov     rcx, rdi; unsigned __int64
0x1800349c6  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800349cb  mov     cl, [rax+6]
0x1800349ce  and     cl, 7
0x1800349d1  cmp     cl, 7
0x1800349d4  jnz     short loc_180034A08
0x1800349d6  mov     dl, sil
0x1800349d9  mov     rcx, rax
0x1800349dc  call    DacGetTargetAddrForHostAddr
0x1800349e1  mov     [rsp+308h+var_2D0], rax
0x1800349e6  mov     r9b, sil; bool
0x1800349e9  mov     r8b, sil; bool
0x1800349ec  mov     edx, 28h ; '('; unsigned int
0x1800349f1  mov     rcx, rax; unsigned __int64
0x1800349f4  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800349f9  mov     eax, [rax+14h]
0x1800349fc  shr     eax, 11h
0x1800349ff  test    sil, al
0x180034a02  jz      short loc_180034A08
0x180034a04  mov     eax, esi
0x180034a06  jmp     short loc_180034A0A
0x180034a08  mov     eax, ebx
0x180034a0a  mov     [r13+4], eax
0x180034a0e  mov     r9b, sil; bool
0x180034a11  mov     r8b, sil; bool
0x180034a14  mov     edx, r12d; unsigned int
0x180034a17  mov     rcx, rdi; unsigned __int64
0x180034a1a  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180034a1f  movzx   ecx, word ptr [rax+4]
0x180034a23  cmp     [rax+6], bx
0x180034a27  jl      short loc_180034A35
0x180034a29  mov     r15d, 3FFh
0x180034a2f  and     cx, r15w
0x180034a33  jmp     short loc_180034A3B
0x180034a35  mov     r15d, 3FFh
0x180034a3b  mov     [r13+8], cx
0x180034a40  mov     r9b, sil; bool
0x180034a43  mov     r8b, sil; bool
0x180034a46  mov     edx, r12d; unsigned int
0x180034a49  mov     rcx, rdi; unsigned __int64
0x180034a4c  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180034a51  mov     rcx, rax; this
0x180034a54  call    ?GetNativeCode@MethodDesc@@QEAA_KXZ; MethodDesc::GetNativeCode(void)
0x180034a59  test    rax, rax
0x180034a5c  jz      short loc_180034A7D
0x180034a5e  mov     r9b, sil; bool
0x180034a61  mov     r8b, sil; bool
0x180034a64  mov     edx, r12d; unsigned int
0x180034a67  mov     rcx, rdi; unsigned __int64
0x180034a6a  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180034a6f  mov     rcx, rax; this
0x180034a72  call    ?GetNativeCode@MethodDesc@@QEAA_KXZ; MethodDesc::GetNativeCode(void)
0x180034a77  mov     [r13+10h], rax
0x180034a7b  jmp     short loc_180034A82
0x180034a7d  or      qword ptr [r13+10h], 0FFFFFFFFFFFFFFFFh
0x180034a82  mov     r9b, sil; bool
0x180034a85  mov     r8b, sil; bool
0x180034a88  mov     edx, r12d; unsigned int
0x180034a8b  mov     rcx, rdi; unsigned __int64
0x180034a8e  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180034a93  test    [rax+3], r12b
0x180034a97  jz      short loc_180034AB4
0x180034a99  mov     r9b, sil; bool
0x180034a9c  mov     r8b, sil; bool
0x180034a9f  mov     edx, r12d; unsigned int
0x180034aa2  mov     rcx, rdi; unsigned __int64
0x180034aa5  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180034aaa  mov     rcx, rax; this
0x180034aad  call    ?GetAddrOfNativeCodeSlot@MethodDesc@@QEAA_KXZ; MethodDesc::GetAddrOfNativeCodeSlot(void)
0x180034ab2  jmp     short loc_180034AB7
0x180034ab4  mov     rax, rbx
0x180034ab7  mov     [r13+18h], rax
0x180034abb  mov     r9b, sil; bool
0x180034abe  mov     r8b, sil; bool
0x180034ac1  mov     edx, r12d; unsigned int
0x180034ac4  mov     rcx, rdi; unsigned __int64
0x180034ac7  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180034acc  mov     r14, rax
0x180034acf  mov     dl, sil
0x180034ad2  mov     rcx, rax
0x180034ad5  call    DacGetTargetAddrForHostAddr
0x180034ada  movzx   ecx, byte ptr [r14+2]
0x180034adf  shl     rcx, 3
0x180034ae3  sub     rax, rcx
0x180034ae6  sub     rax, 18h
0x180034aea  mov     [rsp+308h+var_2D0], rax
0x180034aef  mov     r9b, sil; bool
0x180034af2  mov     r8b, sil; bool
0x180034af5  mov     edx, 18h; unsigned int
0x180034afa  mov     rcx, rax; unsigned __int64
0x180034afd  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180034b02  movzx   eax, word ptr [rax+12h]
0x180034b06  and     ax, r15w
0x180034b0a  movzx   edx, word ptr [r14]
0x180034b0e  mov     ecx, 3FFFh
0x180034b13  and     dx, cx
0x180034b16  movzx   ecx, ax
0x180034b19  or      ecx, 1800h
0x180034b1f  shl     ecx, 0Eh
0x180034b22  movzx   eax, dx
0x180034b25  or      ecx, eax
0x180034b27  mov     [r13+38h], ecx
0x180034b2b  mov     [r13+20h], rdi
0x180034b2f  mov     r9b, sil; bool
0x180034b32  mov     r8b, sil; bool
0x180034b35  mov     edx, r12d; unsigned int
0x180034b38  mov     rcx, rdi; unsigned __int64
0x180034b3b  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180034b40  lea     rdx, [rsp+308h+var_2D0]
0x180034b45  mov     rcx, rax
0x180034b48  call    ?GetMethodTable@MethodDesc@@QEBA?AV?$__DPtr@VMethodTable@@@@XZ; MethodDesc::GetMethodTable(void)
0x180034b4d  mov     r9b, sil; bool
0x180034b50  mov     r8b, sil; bool
0x180034b53  mov     edx, 40h ; '@'; unsigned int
0x180034b58  mov     rcx, [rax]; unsigned __int64
0x180034b5b  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180034b60  mov     dl, sil
0x180034b63  mov     rcx, rax
0x180034b66  call    DacGetTargetAddrForHostAddr
0x180034b6b  mov     [r13+28h], rax
0x180034b6f  mov     r9b, sil; bool
0x180034b72  mov     r8b, sil; bool
0x180034b75  mov     edx, r12d; unsigned int
0x180034b78  mov     rcx, rdi; unsigned __int64
0x180034b7b  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180034b80  mov     rcx, rax; this
0x180034b83  call    ?GetModule@MethodDesc@@QEBAPEAVModule@@XZ; MethodDesc::GetModule(void)
0x180034b88  mov     rcx, rax
0x180034b8b  mov     dl, sil
0x180034b8e  call    DacGetTargetAddrForHostAddr
0x180034b93  mov     [r13+30h], rax
0x180034b97  mov     [rsp+308h+var_278], ebx
0x180034b9e  mov     [rsp+308h+var_270], rbx
0x180034ba6  lea     rax, [rsp+308h+var_278]
0x180034bae  mov     [rsp+308h+var_2D0], rax
0x180034bb3  mov     r9b, sil; bool
0x180034bb6  mov     r8b, sil; bool
0x180034bb9  mov     edx, r12d; unsigned int
0x180034bbc  mov     rcx, rdi; unsigned __int64
0x180034bbf  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180034bc4  mov     rcx, rax; this
0x180034bc7  call    ?GetModule@MethodDesc@@QEBAPEAVModule@@XZ; MethodDesc::GetModule(void)
0x180034bcc  mov     r9b, sil; bool
0x180034bcf  mov     r8b, sil; bool
0x180034bd2  mov     edx, 118h; unsigned int
0x180034bd7  mov     rcx, [rax+30h]; unsigned __int64
0x180034bdb  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180034be0  mov     r8b, sil
0x180034be3  mov     edx, 550h
0x180034be8  mov     rcx, [rax+40h]; unsigned __int64
0x180034bec  call    DacInstantiateClassByVTable
0x180034bf1  lea     r13, [rax+500h]
0x180034bf8  mov     [rsp+308h+var_2D0], r13
0x180034bfd  mov     [rsp+308h+var_190], rdi
0x180034c05  mov     [rsp+308h+var_1A8], rbx
0x180034c0d  mov     [rsp+308h+var_2C0], rdi
0x180034c12  mov     dword ptr [rsp+308h+var_2E8], ebx
0x180034c16  mov     r9, rbx
0x180034c19  lea     r8, [rsp+308h+var_2C0]
0x180034c1e  lea     rdx, [rsp+308h+var_280]
0x180034c26  mov     rcx, r13
0x180034c29  call    ?FindNonRevertedReJitInfoHelper@ReJitManager@@AEAA?AV?$__DPtr@UReJitInfo@@@@V?$__DPtr@VMethodDesc@@@@V?$__VPtr@VModule@@@@I@Z; ReJitManager::FindNonRevertedReJitInfoHelper(__DPtr<MethodDesc>,__VPtr<Module>,uint)
0x180034c2e  mov     r9b, sil; bool
0x180034c31  mov     r8b, sil; bool
0x180034c34  mov     r15d, 38h ; '8'
0x180034c3a  mov     edx, r15d; unsigned int
0x180034c3d  mov     rcx, [rsp+308h+var_280]; unsigned __int64
0x180034c45  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180034c4a  mov     r14, [rsp+308h+var_2A0]
0x180034c4f  test    rax, rax
0x180034c52  jz      short loc_180034C60
0x180034c54  lea     rdx, [r14+60h]; struct DacpReJitData *
0x180034c58  mov     rcx, rax; struct ReJitInfo *
0x180034c5b  call    ?CopyReJitInfoToReJitData@@YAXPEAUReJitInfo@@PEAUDacpReJitData@@@Z; CopyReJitInfoToReJitData(ReJitInfo *,DacpReJitData *)
0x180034c60  mov     r9, [r14+58h]
0x180034c64  test    r9, r9
0x180034c67  jz      short loc_180034CAD
0x180034c69  mov     [rsp+308h+var_280], rdi
0x180034c71  mov     [rsp+308h+var_2E8], rbx
0x180034c76  lea     r8, [rsp+308h+var_280]
0x180034c7e  lea     rdx, [rsp+308h+var_2B0]
0x180034c83  mov     rcx, r13
0x180034c86  call    ?FindReJitInfo@ReJitManager@@AEAA?AV?$__DPtr@UReJitInfo@@@@V?$__DPtr@VMethodDesc@@@@_K1@Z; ReJitManager::FindReJitInfo(__DPtr<MethodDesc>,unsigned __int64,unsigned __int64)
0x180034c8b  mov     r9b, sil; bool
0x180034c8e  mov     r8b, sil; bool
0x180034c91  mov     edx, r15d; unsigned int
0x180034c94  mov     rcx, [rax]; unsigned __int64
0x180034c97  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180034c9c  test    rax, rax
0x180034c9f  jz      short loc_180034CAD
0x180034ca1  lea     rdx, [r14+78h]; struct DacpReJitData *
0x180034ca5  mov     rcx, rax; struct ReJitInfo *
0x180034ca8  call    ?CopyReJitInfoToReJitData@@YAXPEAUReJitInfo@@PEAUDacpReJitData@@@Z; CopyReJitInfoToReJitData(ReJitInfo *,DacpReJitData *)
0x180034cad  mov     [rsp+308h+var_238], rdi
0x180034cb5  mov     [rsp+308h+var_2E8], rbx
  ... truncated ...
```
