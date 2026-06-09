# DacDbiInterfaceImpl::EnumerateInternalFrames(VMPTR_Base<Thread,__VPtr<Thread>>,void (*)(DebuggerIPCE_STRData const *,void *),void *)

- ea: `0x18006e830`
- end: `0x18006ed4d`
- name: `?EnumerateInternalFrames@DacDbiInterfaceImpl@@UEAAXV?$VMPTR_Base@VThread@@V?$__VPtr@VThread@@@@@@P6AXPEBUDebuggerIPCE_STRData@@PEAX@Z2@Z`
- size: `1309`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x180020f50`
- `0x1800210f0`
- `0x18002127c`
- `0x180022068`
- `0x180022230`
- `0x18006e830`
- `0x18006f788`
- `0x18006fa7c`
- `0x18007ef20`
- `0x18008aa0c`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18006e883`
- `KERNEL32!EnterCriticalSection` at `0x18006e883`
- `KERNEL32!LeaveCriticalSection` at `0x18006ed24`
- `KERNEL32!LeaveCriticalSection` at `0x18006ed24`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall DacDbiInterfaceImpl::EnumerateInternalFrames(
        __int64 a1,
        unsigned __int64 a2,
        void (__fastcall *a3)(__int64 *, __int64),
        __int64 a4)
{
  ClrDataAccess *v5; // rdi
  ClrDataAccess *v6; // rsi
  __int64 v7; // r13
  __int64 *v8; // rbx
  __int64 *v9; // r15
  __int64 *v10; // r12
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  unsigned __int8 *v15; // r14
  __int64 TargetVtForHostVt; // rbx
  _QWORD *v17; // r13
  __int64 v18; // rdx
  unsigned __int64 v19; // rbx
  unsigned __int64 v20; // rsi
  _QWORD *v21; // rax
  int v22; // ebx
  _DWORD *v23; // rax
  _QWORD *v25; // rax
  Module *Module; // rax
  struct DomainFile *DomainFile; // rbx
  unsigned __int64 v28; // rax
  __int64 *v29; // rax
  __int64 v30; // rbx
  __int64 v31; // rdx
  _QWORD *v32; // rax
  __int64 *v33; // rax
  __int64 v34; // rax
  __int64 v35; // rdx
  struct AppDomain *ReturnDomain; // rax
  BOOL v37; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  unsigned __int64 v39; // [rsp+20h] [rbp-7B8h]
  unsigned __int64 v40; // [rsp+20h] [rbp-7B8h]
  unsigned __int64 v41; // [rsp+20h] [rbp-7B8h]
  __int64 v42; // [rsp+28h] [rbp-7B0h]
  ClrDataAccess *v43; // [rsp+30h] [rbp-7A8h]
  int v44; // [rsp+38h] [rbp-7A0h] BYREF
  __int64 v45; // [rsp+40h] [rbp-798h]
  unsigned __int8 *v46; // [rsp+48h] [rbp-790h]
  __int64 v47; // [rsp+50h] [rbp-788h]
  void (__fastcall *v48)(__int64 *, __int64); // [rsp+58h] [rbp-780h]
  __int64 *v49; // [rsp+60h] [rbp-778h]
  __int64 *v50; // [rsp+68h] [rbp-770h]
  __int64 v51; // [rsp+70h] [rbp-768h]
  BOOL v52; // [rsp+78h] [rbp-760h]
  _QWORD v53[3]; // [rsp+80h] [rbp-758h] BYREF
  unsigned __int64 v54; // [rsp+98h] [rbp-740h]
  void (__fastcall *v55)(__int64 *, __int64); // [rsp+A0h] [rbp-738h]
  __int64 v56; // [rsp+A8h] [rbp-730h]
  ClrDataAccess *v57; // [rsp+B0h] [rbp-728h]
  __int64 v58; // [rsp+B8h] [rbp-720h]
  __int64 v59; // [rsp+C0h] [rbp-718h] BYREF
  __int64 v60[188]; // [rsp+D0h] [rbp-708h] BYREF
  char v61; // [rsp+6B0h] [rbp-128h]
  __int64 TargetAddrForHostAddr; // [rsp+6B8h] [rbp-120h]
  int v63; // [rsp+6C0h] [rbp-118h]
  int v64; // [rsp+6C8h] [rbp-110h]
  __int64 v65; // [rsp+6D0h] [rbp-108h]
  __int64 v66; // [rsp+6D8h] [rbp-100h]
  int InternalFrameType; // [rsp+6E0h] [rbp-F8h]

  v47 = a4;
  v48 = a3;
  v55 = a3;
  v56 = a4;
  v5 = (ClrDataAccess *)(a1 - 352);
  EnterCriticalSection(&g_dacCritSec);
  v6 = g_dacImpl;
  v43 = g_dacImpl;
  v57 = g_dacImpl;
  v7 = g_pAllocator;
  v42 = g_pAllocator;
  v58 = g_pAllocator;
  g_dacImpl = v5;
  g_pAllocator = *((_QWORD *)v5 + 45);
  v8 = DacInstantiateClassByVTable(a2, 1992, 1);
  v9 = DacInstantiateClassByVTable(v8[2], 16, 1);
  v50 = v9;
  v10 = DacInstantiateClassByVTable(v8[4], 4144, 1);
  v49 = v10;
  v61 = 0;
  v63 = 2;
  while ( v9 != DacInstantiateClassByVTable(0xFFFFFFFFFFFFFFFFuLL, 16, 1) )
  {
    InternalFrameType = DacDbiInterfaceImpl::GetInternalFrameType(v11, v9);
    if ( InternalFrameType )
    {
      LOBYTE(v12) = 1;
      v60[0] = DacGetTargetAddrForHostAddr(v9, v12);
      LOBYTE(v13) = 1;
      TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(v10, v13);
      v15 = (unsigned __int8 *)(*(__int64 (__fastcall **)(__int64 *))(*v9 + 48))(v9);
      v46 = v15;
      if ( InternalFrameType == 2 )
      {
        v44 = 0;
        v45 = 0;
        try
        {
          try
          {
            TargetVtForHostVt = DacGetTargetVtForHostVt(*v9);
            if ( TargetVtForHostVt == (unsigned int)dword_180163874 + DacGlobalBase() )
            {
              LOBYTE(v14) = 1;
              v39 = DacGetTargetAddrForHostAddr(v9, v14);
              v17 = DacInstantiateTypeByAddressHelper(v39, 0x20u, 1, 1);
              LOBYTE(v18) = 1;
              v40 = DacGetTargetAddrForHostAddr(v17, v18) + 32;
              v19 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v40, 8u, 1, 1) & 0xFFFFFFFFFFFFFFC0uLL;
              v41 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v19, 0x40u, 1, 1) + 1);
              v20 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v41, 0xD8u, 1, 1) + 18);
              if ( DacInstantiateTypeByAddressHelper(v20, 0x40u, 1, 1) )
              {
                v54 = v20;
              }
              else
              {
                v54 = v19;
                v20 = v19;
              }
              v21 = DacInstantiateTypeByAddressHelper(v20, 0x40u, 1, 1);
              v22 = *((_DWORD *)v10 + 2);
              v23 = DacInstantiateTypeByAddressHelper(v21[1], 0xD8u, 1, 1);
              if ( v23[50] == v22 || (v23[51] & 0x10) != 0 )
              {
                v25 = DacInstantiateTypeByAddressHelper(v17[2], 0x28u, 1, 1);
                v15 = (unsigned __int8 *)DacInstantiateTypeByAddressHelper(v25[2], 8u, 1, 1);
                v46 = v15;
              }
              v7 = v42;
              v6 = v43;
            }
          }
          catch ( Exception *v59 )
          {
            Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v44);
            v45 = v59;
            throw;
          }
        }
        catch ( ... )
        {
          v53[1] = 0;
          v53[0] = &DelegatingException::`vftable';
          v53[2] = -1;
          v51 = v45;
          v37 = v45 != 0;
          v52 = v37;
          if ( !(__int64)__ClrFlsGetBlock() )
          {
            ExecutionEngine = GetExecutionEngine();
            (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
              ExecutionEngine,
              18);
          }
          if ( (*(unsigned int (__fastcall **)(_QWORD *))(v53[0] + 16LL))(v53) != -2147024597
            && (*(unsigned int (__fastcall **)(_QWORD *))(v53[0] + 16LL))(v53) != -2146231223 )
          {
            v52 = 0;
            throw;
          }
          if ( v37 )
            v52 = 0;
          DelegatingException::~DelegatingException((DelegatingException *)v53);
          v7 = v58;
          v42 = v58;
          v6 = v57;
          v43 = v57;
          v9 = v50;
          v10 = v49;
          v15 = v46;
          v48 = v55;
          v47 = v56;
        }
      }
      if ( v15 && (Module = MethodDesc::GetModule((MethodDesc *)v15)) != 0 )
        DomainFile = Module::GetDomainFile(Module, (struct AppDomain *)v10);
      else
        DomainFile = 0;
      if ( InternalFrameType == 5 )
      {
        LOBYTE(v14) = 1;
        v28 = DacGetTargetAddrForHostAddr(v9, v14);
        v29 = DacInstantiateClassByVTable(v28, 40, 1);
        v30 = (*(__int64 (__fastcall **)(__int64 *))(*v29 + 152))(v29);
        v64 = *(_DWORD *)(v30 + 1260);
        if ( DacInstantiateTypeByAddressHelper(*(_QWORD *)(v30 + 1272), 0x30u, 1, 1) )
        {
          v32 = DacInstantiateTypeByAddressHelper(*(_QWORD *)(v30 + 1272), 0x30u, 1, 1);
          v33 = DacInstantiateClassByVTable(v32[3], 104, 1);
        }
        else
        {
          v33 = 0;
        }
        LOBYTE(v31) = 1;
        v65 = DacGetTargetAddrForHostAddr(v33, v31);
        v66 = 0;
      }
      else
      {
        if ( v15 )
        {
          LOBYTE(v14) = 1;
          v34 = DacGetTargetAddrForHostAddr(v15, v14);
          v64 = *(_WORD *)v15 & 0x3FFF
              | ((*((_WORD *)DacInstantiateTypeByAddressHelper(v34 - 8LL * v15[2] - 24, 0x18u, 1, 1) + 9) & 0x3FF
                | 0x1800) << 14);
        }
        else
        {
          v64 = 0;
        }
        LOBYTE(v14) = 1;
        v65 = DacGetTargetAddrForHostAddr(DomainFile, v14);
        LOBYTE(v35) = 1;
        v66 = DacGetTargetAddrForHostAddr(v15, v35);
      }
      v48(v60, v47);
    }
    ReturnDomain = Frame::GetReturnDomain((Frame *)v9);
    if ( ReturnDomain )
      v10 = (__int64 *)ReturnDomain;
    v49 = v10;
    v9 = DacInstantiateClassByVTable(v9[1], 16, 1);
    v50 = v9;
  }
  g_dacImpl = v6;
  g_pAllocator = v7;
  LeaveCriticalSection(&g_dacCritSec);
}

```

## disassembly

```asm
0x18006e830  push    rbx
0x18006e832  push    rsi
0x18006e833  push    rdi
0x18006e834  push    r12
0x18006e836  push    r13
0x18006e838  push    r14
0x18006e83a  push    r15
0x18006e83c  sub     rsp, 7A0h
0x18006e843  mov     rax, cs:__security_cookie
0x18006e84a  xor     rax, rsp
0x18006e84d  mov     [rsp+7D8h+var_48], rax
0x18006e855  mov     [rsp+7D8h+var_788], r9
0x18006e85a  mov     rax, r8
0x18006e85d  mov     [rsp+7D8h+var_780], rax
0x18006e862  mov     rbx, rdx
0x18006e865  mov     [rsp+7D8h+var_738], rax
0x18006e86d  mov     [rsp+7D8h+var_730], r9
0x18006e875  lea     rdi, [rcx-160h]
0x18006e87c  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006e883  call    cs:__imp_EnterCriticalSection
0x18006e889  mov     rsi, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x18006e890  mov     [rsp+7D8h+var_7A8], rsi
0x18006e895  mov     [rsp+7D8h+var_728], rsi
0x18006e89d  mov     r13, cs:g_pAllocator
0x18006e8a4  mov     [rsp+7D8h+var_7B0], r13
0x18006e8a9  mov     [rsp+7D8h+var_720], r13
0x18006e8b1  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rdi; ClrDataAccess * g_dacImpl
0x18006e8b8  mov     rax, [rdi+168h]
0x18006e8bf  mov     cs:g_pAllocator, rax
0x18006e8c6  mov     r8b, 1
0x18006e8c9  mov     edx, 7C8h
0x18006e8ce  mov     rcx, rbx; unsigned __int64
0x18006e8d1  call    DacInstantiateClassByVTable
0x18006e8d6  mov     rbx, rax
0x18006e8d9  mov     r8b, 1
0x18006e8dc  mov     edx, 10h
0x18006e8e1  mov     rcx, [rax+10h]; unsigned __int64
0x18006e8e5  call    DacInstantiateClassByVTable
0x18006e8ea  mov     r15, rax
0x18006e8ed  mov     [rsp+7D8h+var_770], rax
0x18006e8f2  mov     r8b, 1
0x18006e8f5  mov     edx, 1030h
0x18006e8fa  mov     rcx, [rbx+20h]; unsigned __int64
0x18006e8fe  call    DacInstantiateClassByVTable
0x18006e903  mov     r12, rax
0x18006e906  mov     [rsp+7D8h+var_778], rax
0x18006e90b  xor     edi, edi
0x18006e90d  mov     [rsp+7D8h+var_128], dil
0x18006e915  mov     [rsp+7D8h+var_118], 2
0x18006e920  mov     r8b, 1
0x18006e923  mov     edx, 10h
0x18006e928  or      rcx, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x18006e92c  call    DacInstantiateClassByVTable
0x18006e931  cmp     r15, rax
0x18006e934  jz      loc_18006ED0F
0x18006e93a  mov     rdx, r15
0x18006e93d  call    ?GetInternalFrameType@DacDbiInterfaceImpl@@AEAA?AW4CorDebugInternalFrameType@@PEAVFrame@@@Z; DacDbiInterfaceImpl::GetInternalFrameType(Frame *)
0x18006e942  mov     [rsp+7D8h+var_F8], eax
0x18006e949  test    eax, eax
0x18006e94b  jz      loc_18006ECDD
0x18006e951  mov     dl, 1
0x18006e953  mov     rcx, r15
0x18006e956  call    DacGetTargetAddrForHostAddr
0x18006e95b  mov     [rsp+7D8h+var_708], rax
0x18006e963  mov     dl, 1
0x18006e965  mov     rcx, r12
0x18006e968  call    DacGetTargetAddrForHostAddr
0x18006e96d  mov     [rsp+7D8h+var_120], rax
0x18006e975  mov     rax, [r15]
0x18006e978  mov     rcx, r15
0x18006e97b  mov     rax, [rax+30h]
0x18006e97f  call    cs:__guard_dispatch_icall_fptr
0x18006e985  mov     r14, rax
0x18006e988  mov     [rsp+7D8h+var_790], rax
0x18006e98d  cmp     [rsp+7D8h+var_F8], 2
0x18006e995  jnz     loc_18006EB66
0x18006e99b  mov     [rsp+7D8h+var_7A0], edi
0x18006e99f  mov     [rsp+7D8h+var_798], rdi
0x18006e9a4  lea     rax, [rsp+7D8h+var_7A0]
0x18006e9a9  mov     [rsp+7D8h+var_7B8], rax
0x18006e9ae  mov     rcx, [r15]
0x18006e9b1  call    DacGetTargetVtForHostVt
0x18006e9b6  mov     rbx, rax
0x18006e9b9  call    DacGlobalBase
0x18006e9be  mov     ecx, cs:dword_180163874
0x18006e9c4  add     rax, rcx
0x18006e9c7  cmp     rbx, rax
0x18006e9ca  jnz     loc_18006EB1F
0x18006e9d0  mov     dl, 1
0x18006e9d2  mov     rcx, r15
0x18006e9d5  call    DacGetTargetAddrForHostAddr
0x18006e9da  mov     [rsp+7D8h+var_7B8], rax
0x18006e9df  mov     r9b, 1; bool
0x18006e9e2  mov     r8b, r9b; bool
0x18006e9e5  mov     edx, 20h ; ' '; unsigned int
0x18006e9ea  mov     rcx, rax; unsigned __int64
0x18006e9ed  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006e9f2  mov     r13, rax
0x18006e9f5  mov     dl, 1
0x18006e9f7  mov     rcx, rax
0x18006e9fa  call    DacGetTargetAddrForHostAddr
0x18006e9ff  lea     rcx, [rax+20h]; unsigned __int64
0x18006ea03  mov     [rsp+7D8h+var_7B8], rcx
0x18006ea08  mov     [rsp+7D8h+var_7B8], rcx
0x18006ea0d  mov     r9b, 1; bool
0x18006ea10  mov     r8b, r9b; bool
0x18006ea13  mov     edx, 8; unsigned int
0x18006ea18  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006ea1d  mov     rbx, [rax]
0x18006ea20  mov     [rsp+7D8h+var_7B8], rbx
0x18006ea25  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18006ea29  mov     [rsp+7D8h+var_7B8], rbx
0x18006ea2e  mov     r9b, 1; bool
0x18006ea31  mov     r8b, r9b; bool
0x18006ea34  mov     edx, 40h ; '@'; unsigned int
0x18006ea39  mov     rcx, rbx; unsigned __int64
0x18006ea3c  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006ea41  mov     rcx, [rax+8]; unsigned __int64
0x18006ea45  mov     [rsp+7D8h+var_7B8], rcx
0x18006ea4a  mov     r9b, 1; bool
0x18006ea4d  mov     r8b, r9b; bool
0x18006ea50  mov     edx, 0D8h; unsigned int
0x18006ea55  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006ea5a  mov     rsi, [rax+90h]
0x18006ea61  mov     [rsp+7D8h+var_7B8], rsi
0x18006ea66  mov     r9b, 1; bool
0x18006ea69  mov     r8b, r9b; bool
0x18006ea6c  mov     edx, 40h ; '@'; unsigned int
0x18006ea71  mov     rcx, rsi; unsigned __int64
0x18006ea74  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006ea79  test    rax, rax
0x18006ea7c  jz      short loc_18006EA88
0x18006ea7e  mov     [rsp+7D8h+var_740], rsi
0x18006ea86  jmp     short loc_18006EA93
0x18006ea88  mov     [rsp+7D8h+var_740], rbx
0x18006ea90  mov     rsi, rbx
0x18006ea93  mov     r9b, 1; bool
0x18006ea96  mov     r8b, r9b; bool
0x18006ea99  mov     edx, 40h ; '@'; unsigned int
0x18006ea9e  mov     rcx, rsi; unsigned __int64
0x18006eaa1  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006eaa6  mov     ebx, [r12+8]
0x18006eaab  mov     rcx, [rax+8]; unsigned __int64
0x18006eaaf  mov     [rsp+7D8h+var_7B8], rcx
0x18006eab4  mov     r9b, 1; bool
0x18006eab7  mov     r8b, r9b; bool
0x18006eaba  mov     edx, 0D8h; unsigned int
0x18006eabf  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006eac4  cmp     [rax+0C8h], ebx
0x18006eaca  jz      short loc_18006EADC
0x18006eacc  test    byte ptr [rax+0CCh], 10h
0x18006ead3  jnz     short loc_18006EADC
0x18006ead5  mov     eax, 1
0x18006eada  jmp     short loc_18006EADE
0x18006eadc  mov     eax, edi
0x18006eade  test    eax, eax
0x18006eae0  jnz     short loc_18006EB15
0x18006eae2  mov     rcx, [r13+10h]; unsigned __int64
0x18006eae6  mov     [rsp+7D8h+var_7B8], rcx
0x18006eaeb  mov     r9b, 1; bool
0x18006eaee  mov     r8b, r9b; bool
0x18006eaf1  lea     edx, [rax+28h]; unsigned int
0x18006eaf4  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006eaf9  mov     r9b, 1; bool
0x18006eafc  mov     r8b, r9b; bool
0x18006eaff  mov     edx, 8; unsigned int
0x18006eb04  mov     rcx, [rax+10h]; unsigned __int64
0x18006eb08  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006eb0d  mov     r14, rax
0x18006eb10  mov     [rsp+7D8h+var_790], rax
0x18006eb15  mov     r13, [rsp+7D8h+var_7B0]
0x18006eb1a  mov     rsi, [rsp+7D8h+var_7A8]
0x18006eb1f  jmp     short loc_18006EB66
0x18006eb21  xor     edi, edi
0x18006eb23  mov     r13, [rsp+7D8h+var_720]
0x18006eb2b  mov     [rsp+7D8h+var_7B0], r13
0x18006eb30  mov     rsi, [rsp+7D8h+var_728]
0x18006eb38  mov     [rsp+7D8h+var_7A8], rsi
0x18006eb3d  mov     r15, [rsp+7D8h+var_770]
0x18006eb42  mov     r12, [rsp+7D8h+var_778]
0x18006eb47  mov     r14, [rsp+7D8h+var_790]
0x18006eb4c  mov     rax, [rsp+7D8h+var_738]
0x18006eb54  mov     [rsp+7D8h+var_780], rax
0x18006eb59  mov     rax, [rsp+7D8h+var_730]
0x18006eb61  mov     [rsp+7D8h+var_788], rax
0x18006eb66  test    r14, r14
0x18006eb69  jz      short loc_18006EB88
0x18006eb6b  mov     rcx, r14; this
0x18006eb6e  call    ?GetModule@MethodDesc@@QEBAPEAVModule@@XZ; MethodDesc::GetModule(void)
0x18006eb73  test    rax, rax
0x18006eb76  jz      short loc_18006EB88
0x18006eb78  mov     rdx, r12; struct AppDomain *
0x18006eb7b  mov     rcx, rax; this
0x18006eb7e  call    ?GetDomainFile@Module@@QEAAPEAVDomainFile@@PEAVAppDomain@@@Z; Module::GetDomainFile(AppDomain *)
0x18006eb83  mov     rbx, rax
0x18006eb86  jmp     short loc_18006EB8B
0x18006eb88  mov     rbx, rdi
0x18006eb8b  cmp     [rsp+7D8h+var_F8], 5
0x18006eb93  jnz     loc_18006EC41
0x18006eb99  mov     dl, 1
0x18006eb9b  mov     rcx, r15
0x18006eb9e  call    DacGetTargetAddrForHostAddr
0x18006eba3  mov     r8b, 1
0x18006eba6  mov     edx, 28h ; '('
0x18006ebab  mov     rcx, rax; unsigned __int64
0x18006ebae  call    DacInstantiateClassByVTable
0x18006ebb3  mov     rdx, rax
0x18006ebb6  mov     rcx, [rax]
0x18006ebb9  mov     rax, [rcx+98h]
0x18006ebc0  mov     rcx, rdx
0x18006ebc3  call    cs:__guard_dispatch_icall_fptr
0x18006ebc9  mov     rbx, rax
0x18006ebcc  mov     ecx, [rax+4ECh]
0x18006ebd2  mov     [rsp+7D8h+var_110], ecx
0x18006ebd9  mov     r9b, 1; bool
0x18006ebdc  mov     r8b, r9b; bool
0x18006ebdf  mov     edx, 30h ; '0'; unsigned int
0x18006ebe4  mov     rcx, [rax+4F8h]; unsigned __int64
0x18006ebeb  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006ebf0  test    rax, rax
0x18006ebf3  jz      short loc_18006EC1F
0x18006ebf5  mov     r9b, 1; bool
0x18006ebf8  mov     r8b, r9b; bool
0x18006ebfb  mov     edx, 30h ; '0'; unsigned int
0x18006ec00  mov     rcx, [rbx+4F8h]; unsigned __int64
0x18006ec07  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006ec0c  mov     r8b, 1
0x18006ec0f  mov     edx, 68h ; 'h'
0x18006ec14  mov     rcx, [rax+18h]; unsigned __int64
0x18006ec18  call    DacInstantiateClassByVTable
0x18006ec1d  jmp     short loc_18006EC22
0x18006ec1f  mov     rax, rdi
0x18006ec22  mov     dl, 1
0x18006ec24  mov     rcx, rax
0x18006ec27  call    DacGetTargetAddrForHostAddr
0x18006ec2c  mov     [rsp+7D8h+var_108], rax
0x18006ec34  mov     [rsp+7D8h+var_100], rdi
0x18006ec3c  jmp     loc_18006ECC5
0x18006ec41  test    r14, r14
0x18006ec44  jnz     short loc_18006EC4F
0x18006ec46  mov     [rsp+7D8h+var_110], edi
0x18006ec4d  jmp     short loc_18006ECA1
0x18006ec4f  mov     dl, 1
0x18006ec51  mov     rcx, r14
0x18006ec54  call    DacGetTargetAddrForHostAddr
0x18006ec59  mov     rcx, rax
0x18006ec5c  movzx   eax, byte ptr [r14+2]
0x18006ec61  shl     rax, 3
0x18006ec65  sub     rcx, rax
0x18006ec68  sub     rcx, 18h; unsigned __int64
0x18006ec6c  mov     r9b, 1; bool
0x18006ec6f  mov     r8b, r9b; bool
0x18006ec72  mov     edx, 18h; unsigned int
0x18006ec77  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006ec7c  movzx   ecx, word ptr [rax+12h]
0x18006ec80  and     ecx, 3FFh
0x18006ec86  or      ecx, 1800h
0x18006ec8c  shl     ecx, 0Eh
0x18006ec8f  movzx   eax, word ptr [r14]
0x18006ec93  and     eax, 3FFFh
0x18006ec98  or      ecx, eax
0x18006ec9a  mov     [rsp+7D8h+var_110], ecx
0x18006eca1  mov     dl, 1
0x18006eca3  mov     rcx, rbx
0x18006eca6  call    DacGetTargetAddrForHostAddr
0x18006ecab  mov     [rsp+7D8h+var_108], rax
0x18006ecb3  mov     dl, 1
0x18006ecb5  mov     rcx, r14
0x18006ecb8  call    DacGetTargetAddrForHostAddr
0x18006ecbd  mov     [rsp+7D8h+var_100], rax
0x18006ecc5  mov     rdx, [rsp+7D8h+var_788]
0x18006ecca  lea     rcx, [rsp+7D8h+var_708]
0x18006ecd2  mov     rax, [rsp+7D8h+var_780]
0x18006ecd7  call    cs:__guard_dispatch_icall_fptr
0x18006ecdd  mov     rcx, r15; this
0x18006ece0  call    ?GetReturnDomain@Frame@@QEAAPEAVAppDomain@@XZ; Frame::GetReturnDomain(void)
0x18006ece5  test    rax, rax
0x18006ece8  cmovnz  r12, rax
0x18006ecec  mov     [rsp+7D8h+var_778], r12
0x18006ecf1  mov     r8b, 1
0x18006ecf4  mov     edx, 10h
0x18006ecf9  mov     rcx, [r15+8]; unsigned __int64
0x18006ecfd  call    DacInstantiateClassByVTable
0x18006ed02  mov     r15, rax
0x18006ed05  mov     [rsp+7D8h+var_770], rax
0x18006ed0a  jmp     loc_18006E920
0x18006ed0f  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rsi; ClrDataAccess * g_dacImpl
0x18006ed16  mov     cs:g_pAllocator, r13
0x18006ed1d  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006ed24  call    cs:__imp_LeaveCriticalSection
0x18006ed2a  mov     rcx, [rsp+7D8h+var_48]
0x18006ed32  xor     rcx, rsp; StackCookie
0x18006ed35  call    __security_check_cookie
0x18006ed3a  add     rsp, 7A0h
0x18006ed41  pop     r15
0x18006ed43  pop     r14
0x18006ed45  pop     r13
0x18006ed47  pop     r12
0x18006ed49  pop     rdi
0x18006ed4a  pop     rsi
  ... truncated ...
```
