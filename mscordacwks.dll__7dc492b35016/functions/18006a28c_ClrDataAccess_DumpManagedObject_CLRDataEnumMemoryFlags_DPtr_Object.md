# ClrDataAccess::DumpManagedObject(CLRDataEnumMemoryFlags,__DPtr<Object>)

- ea: `0x18006a28c`
- end: `0x18006a502`
- name: `?DumpManagedObject@ClrDataAccess@@QEAAJW4CLRDataEnumMemoryFlags@@V?$__DPtr@VObject@@@@@Z`
- size: `630`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x18006a504`
- `0x18006abf0`
- `0x18006be20`

## callees

- `0x180020f50`
- `0x1800210f0`
- `0x180022068`
- `0x18006a28c`
- `0x18006de78`
- `0x180082d98`
- `0x18008dae8`
- `0x1800f0d20`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18006a457`
- `KERNEL32!HeapFree` at `0x18006a457`
- `KERNEL32!GetProcessHeap` at `0x18006a442`
- `KERNEL32!GetProcessHeap` at `0x18006a442`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall ClrDataAccess::DumpManagedObject(__int64 a1, __int64 a2, unsigned __int64 *a3)
{
  unsigned __int64 *v3; // rsi
  unsigned int v4; // r12d
  __int64 v5; // rax
  unsigned __int64 *v6; // rax
  _QWORD *v7; // rax
  __int64 v8; // rdx
  bool v9; // r8
  void *v10; // r14
  HANDLE ProcessHeap; // rax
  unsigned __int64 v12; // rcx
  _QWORD *v13; // rdi
  Object *v14; // rax
  void ***v16; // rbx
  int v17; // edi
  void ***v18; // rcx
  void ***v19; // rbx
  BOOL v20; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  void ***v22; // rcx
  __int64 v23; // [rsp+0h] [rbp-2F8h] BYREF
  int *TargetAddrForHostAddr; // [rsp+20h] [rbp-2D8h]
  void ***v25; // [rsp+28h] [rbp-2D0h]
  int v26; // [rsp+30h] [rbp-2C8h]
  unsigned int v27; // [rsp+38h] [rbp-2C0h]
  void **v28; // [rsp+40h] [rbp-2B8h] BYREF
  __int64 v29; // [rsp+48h] [rbp-2B0h]
  __int64 v30; // [rsp+50h] [rbp-2A8h]
  int v31; // [rsp+58h] [rbp-2A0h] BYREF
  void ***v32; // [rsp+60h] [rbp-298h]
  _QWORD *v33; // [rsp+68h] [rbp-290h]
  unsigned __int64 *v34; // [rsp+70h] [rbp-288h]
  unsigned __int64 v35; // [rsp+78h] [rbp-280h]
  char v36; // [rsp+80h] [rbp-278h] BYREF
  void ***v37; // [rsp+88h] [rbp-270h]
  __int64 v38; // [rsp+90h] [rbp-268h] BYREF
  int v39; // [rsp+98h] [rbp-260h]
  void ***v40; // [rsp+A0h] [rbp-258h] BYREF
  void ***v41; // [rsp+A8h] [rbp-250h] BYREF
  _DWORD v42[2]; // [rsp+B0h] [rbp-248h] BYREF
  int v43; // [rsp+B8h] [rbp-240h]
  LPVOID lpMem; // [rsp+C0h] [rbp-238h]
  __int16 v45; // [rsp+C8h] [rbp-230h] BYREF

  v3 = a3;
  v4 = a2;
  v27 = a2;
  v34 = a3;
  if ( *a3 )
  {
    v5 = DacGlobalBase(a1, a2, a3);
    v6 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper((unsigned int)*g_gcDacGlobals + v5, 8u, 1, 1);
    v7 = DacInstantiateTypeByAddressHelper(*v6, 0xE8u, 1, 1);
    if ( !*(_DWORD *)DacInstantiateTypeByAddressHelper(v7[23], 4u, 1, 1) )
    {
      v37 = 0;
      try
      {
        try
        {
          v35 = (unsigned __int64)&v36;
          v35 = *(_QWORD *)DacInstantiateTypeByAddressHelper(*v3, 8u, 1, 1);
          TargetAddrForHostAddr = (int *)(v35 & 0xFFFFFFFFFFFFFFFCuLL);
          v13 = DacInstantiateTypeByAddressHelper(v35 & 0xFFFFFFFFFFFFFFFCuLL, 0x40u, 1, 1);
          v33 = v13;
          while ( v13 )
          {
            v31 = 0;
            v32 = 0;
            try
            {
              try
              {
                TargetAddrForHostAddr = &v31;
                MethodTable::EnumMemoryRegions(v13, v4);
                v43 = 0;
                lpMem = &v45;
                v42[1] = 512;
                v42[0] = 2;
                v45 = 0;
                LOBYTE(v8) = 1;
                TargetAddrForHostAddr = (int *)DacGetTargetAddrForHostAddr(v13, v8);
                v38 = 0;
                v39 = 0;
                TypeString::AppendType(v42, TargetAddrForHostAddr, &v38, 3);
                if ( (v43 & 8) != 0 )
                {
                  v10 = lpMem;
                  if ( lpMem )
                  {
                    ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
                    if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
                    {
                      ProcessHeap = GetProcessHeap();
                      `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
                    }
                    HeapFree(ProcessHeap, 0, v10);
                  }
                }
              }
              catch ( Exception *v40 )
              {
                Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v31);
                v32 = v40;
                throw;
              }
            }
            catch ( ... )
            {
              v29 = 0;
              v28 = &DelegatingException::`vftable';
              v30 = -1;
              v16 = v32;
              v25 = v32;
              v17 = 0;
              v26 = 0;
              if ( v32 )
              {
                v17 = 1;
                v26 = 1;
              }
              Exception::HandlerState::SetupCatch((Exception::HandlerState *)&v31, (int)&v23, v9);
              v18 = &v28;
              if ( v16 )
                v18 = v16;
              if ( ((unsigned int (__fastcall *)(void ***))(*v18)[2])(v18) == -2146233029 )
              {
                v26 = 0;
                throw;
              }
              if ( v17 )
              {
                if ( v16 )
                {
                  if ( !((unsigned int (__fastcall *)(void ***))(*v16)[10])(v16) )
                    ((void (__fastcall *)(void ***, __int64))**v16)(v16, 5);
                }
                v26 = 0;
              }
              DelegatingException::~DelegatingException((DelegatingException *)&v28);
              v13 = v33;
              v4 = v27;
              v3 = v34;
            }
            v12 = v13[2];
            if ( (*(_DWORD *)v13 & 0x800000) != 0 )
            {
              TargetAddrForHostAddr = (int *)(v12 + 16);
              v12 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v12 + 16, 8u, 1, 1);
            }
            TargetAddrForHostAddr = (int *)v12;
            v13 = DacInstantiateTypeByAddressHelper(v12, 0x40u, 1, 1);
            v33 = v13;
          }
          v14 = (Object *)DacInstantiateTypeByAddressHelper(*v3, 8u, 1, 1);
          Object::EnumMemoryRegions(v14);
        }
        catch ( Exception *v41 )
        {
          v37 = v41;
          throw;
        }
      }
      catch ( ... )
      {
        v29 = 0;
        v28 = &DelegatingException::`vftable';
        v30 = -1;
        v19 = v37;
        v25 = v37;
        v20 = v37 != 0;
        v26 = v20;
        if ( !(__int64)__ClrFlsGetBlock() )
        {
          ExecutionEngine = GetExecutionEngine();
          (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
            ExecutionEngine,
            18);
        }
        v22 = &v28;
        if ( v19 )
          v22 = v19;
        if ( ((unsigned int (__fastcall *)(void ***))(*v22)[2])(v22) == -2146233029 )
        {
          v26 = 0;
          throw;
        }
        if ( v20 )
        {
          if ( v19 && !((unsigned int (__fastcall *)(void ***))(*v19)[10])(v19) )
            ((void (__fastcall *)(void ***, __int64))**v19)(v19, 5);
          v26 = 0;
        }
        DelegatingException::~DelegatingException((DelegatingException *)&v28);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18006a28c  mov     [rsp+arg_0], rbx
0x18006a291  mov     [rsp+arg_18], rsi
0x18006a296  push    rdi
0x18006a297  push    r12
0x18006a299  push    r14
0x18006a29b  sub     rsp, 2E0h
0x18006a2a2  mov     rax, cs:__security_cookie
0x18006a2a9  xor     rax, rsp
0x18006a2ac  mov     [rsp+2F8h+var_28], rax
0x18006a2b4  mov     rsi, r8
0x18006a2b7  mov     r12d, edx
0x18006a2ba  mov     [rsp+2F8h+var_2C0], edx
0x18006a2be  mov     [rsp+2F8h+var_288], r8
0x18006a2c3  xor     ebx, ebx
0x18006a2c5  cmp     [r8], rbx
0x18006a2c8  jz      loc_18006A4D7
0x18006a2ce  call    DacGlobalBase
0x18006a2d3  mov     rcx, rax
0x18006a2d6  mov     rax, cs:?g_gcDacGlobals@@3V?$__GlobalPtr@PEAUGcDacVars@@V?$__DPtr@UGcDacVars@@@@@@A; __GlobalPtr<GcDacVars *,__DPtr<GcDacVars>> g_gcDacGlobals
0x18006a2dd  mov     edx, [rax]
0x18006a2df  add     rcx, rdx; unsigned __int64
0x18006a2e2  mov     r9b, 1; bool
0x18006a2e5  mov     r8b, r9b; bool
0x18006a2e8  lea     edx, [rbx+8]; unsigned int
0x18006a2eb  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006a2f0  mov     r9b, 1; bool
0x18006a2f3  mov     r8b, r9b; bool
0x18006a2f6  mov     edx, 0E8h; unsigned int
0x18006a2fb  mov     rcx, [rax]; unsigned __int64
0x18006a2fe  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006a303  mov     r9b, 1; bool
0x18006a306  mov     r8b, r9b; bool
0x18006a309  lea     edx, [rbx+4]; unsigned int
0x18006a30c  mov     rcx, [rax+0B8h]; unsigned __int64
0x18006a313  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006a318  cmp     [rax], ebx
0x18006a31a  jnz     loc_18006A4D7
0x18006a320  mov     [rsp+2F8h+var_270], rbx
0x18006a328  lea     rax, [rsp+2F8h+var_278]
0x18006a330  mov     [rsp+2F8h+var_280], rax
0x18006a335  mov     r9b, 1; bool
0x18006a338  mov     r8b, r9b; bool
0x18006a33b  lea     edx, [rbx+8]; unsigned int
0x18006a33e  mov     rcx, [rsi]; unsigned __int64
0x18006a341  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006a346  mov     rcx, [rax]
0x18006a349  mov     [rsp+2F8h+var_280], rcx
0x18006a34e  and     rcx, 0FFFFFFFFFFFFFFFCh; unsigned __int64
0x18006a352  mov     [rsp+2F8h+var_2D8], rcx
0x18006a357  mov     r9b, 1; bool
0x18006a35a  mov     r8b, r9b; bool
0x18006a35d  lea     edx, [rbx+40h]; unsigned int
0x18006a360  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006a365  mov     rdi, rax
0x18006a368  mov     [rsp+2F8h+var_290], rax
0x18006a36d  test    rdi, rdi
0x18006a370  jz      loc_18006A4BB
0x18006a376  mov     [rsp+2F8h+var_2A0], ebx
0x18006a37a  mov     [rsp+2F8h+var_298], rbx
0x18006a37f  lea     rax, [rsp+2F8h+var_2A0]
0x18006a384  mov     [rsp+2F8h+var_2D8], rax
0x18006a389  mov     edx, r12d
0x18006a38c  mov     rcx, rdi
0x18006a38f  call    ?EnumMemoryRegions@MethodTable@@QEAAXW4CLRDataEnumMemoryFlags@@@Z; MethodTable::EnumMemoryRegions(CLRDataEnumMemoryFlags)
0x18006a394  mov     [rsp+2F8h+var_248], ebx
0x18006a39b  mov     [rsp+2F8h+var_244], ebx
0x18006a3a2  mov     [rsp+2F8h+var_240], ebx
0x18006a3a9  mov     [rsp+2F8h+lpMem], rbx
0x18006a3b1  lea     rax, [rsp+2F8h+var_230]
0x18006a3b9  mov     [rsp+2F8h+lpMem], rax
0x18006a3c1  mov     [rsp+2F8h+var_244], 200h
0x18006a3cc  mov     [rsp+2F8h+var_248], 2
0x18006a3d7  mov     rax, [rsp+2F8h+lpMem]
0x18006a3df  mov     [rax], bx
0x18006a3e2  mov     dl, 1
0x18006a3e4  mov     rcx, rdi
0x18006a3e7  call    DacGetTargetAddrForHostAddr
0x18006a3ec  mov     [rsp+2F8h+var_2D8], rax
0x18006a3f1  mov     [rsp+2F8h+var_268], rbx
0x18006a3f9  mov     [rsp+2F8h+var_260], ebx
0x18006a400  mov     r9d, 3
0x18006a406  lea     r8, [rsp+2F8h+var_268]
0x18006a40e  mov     rdx, rax
0x18006a411  lea     rcx, [rsp+2F8h+var_248]
0x18006a419  call    ?AppendType@TypeString@@SAXAEAVSString@@VTypeHandle@@VInstantiation@@K@Z; TypeString::AppendType(SString &,TypeHandle,Instantiation,ulong)
0x18006a41e  nop
0x18006a41f  test    byte ptr [rsp+2F8h+var_240], 8
0x18006a427  jz      short loc_18006A45E
0x18006a429  mov     r14, [rsp+2F8h+lpMem]
0x18006a431  test    r14, r14
0x18006a434  jz      short loc_18006A45E
0x18006a436  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18006a43d  test    rax, rax
0x18006a440  jnz     short loc_18006A44F
0x18006a442  call    cs:__imp_GetProcessHeap
0x18006a448  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18006a44f  mov     r8, r14; lpMem
0x18006a452  xor     edx, edx; dwFlags
0x18006a454  mov     rcx, rax; hHeap
0x18006a457  call    cs:__imp_HeapFree
0x18006a45d  nop
0x18006a45e  jmp     short loc_18006A471
0x18006a460  xor     ebx, ebx
0x18006a462  mov     rdi, [rsp+2F8h+var_290]
0x18006a467  mov     r12d, [rsp+2F8h+var_2C0]
0x18006a46c  mov     rsi, [rsp+2F8h+var_288]
0x18006a471  mov     rcx, [rdi+10h]
0x18006a475  test    dword ptr [rdi], 800000h
0x18006a47b  jz      short loc_18006A499
0x18006a47d  add     rcx, 10h; unsigned __int64
0x18006a481  mov     [rsp+2F8h+var_2D8], rcx
0x18006a486  mov     r9b, 1; bool
0x18006a489  mov     r8b, r9b; bool
0x18006a48c  mov     edx, 8; unsigned int
0x18006a491  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006a496  mov     rcx, [rax]; unsigned __int64
0x18006a499  mov     [rsp+2F8h+var_2D8], rcx
0x18006a49e  mov     r9b, 1; bool
0x18006a4a1  mov     r8b, r9b; bool
0x18006a4a4  mov     edx, 40h ; '@'; unsigned int
0x18006a4a9  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006a4ae  mov     rdi, rax
0x18006a4b1  mov     [rsp+2F8h+var_290], rax
0x18006a4b6  jmp     loc_18006A36D
0x18006a4bb  mov     r9b, 1; bool
0x18006a4be  mov     r8b, r9b; bool
0x18006a4c1  mov     edx, 8; unsigned int
0x18006a4c6  mov     rcx, [rsi]; unsigned __int64
0x18006a4c9  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18006a4ce  mov     rcx, rax; this
0x18006a4d1  call    ?EnumMemoryRegions@Object@@QEAAXXZ; Object::EnumMemoryRegions(void)
0x18006a4d6  nop
0x18006a4d7  xor     eax, eax
0x18006a4d9  mov     rcx, [rsp+2F8h+var_28]
0x18006a4e1  xor     rcx, rsp; StackCookie
0x18006a4e4  call    __security_check_cookie
0x18006a4e9  lea     r11, [rsp+2F8h+var_18]
0x18006a4f1  mov     rbx, [r11+20h]
0x18006a4f5  mov     rsi, [r11+38h]
0x18006a4f9  mov     rsp, r11
0x18006a4fc  pop     r14
0x18006a4fe  pop     r12
0x18006a500  pop     rdi
0x18006a501  retn
```
