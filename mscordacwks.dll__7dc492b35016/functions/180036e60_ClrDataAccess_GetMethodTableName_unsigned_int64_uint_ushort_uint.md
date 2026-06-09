# ClrDataAccess::GetMethodTableName(unsigned __int64,uint,ushort *,uint *)

- ea: `0x180036e60`
- end: `0x1800371ad`
- name: `?GetMethodTableName@ClrDataAccess@@UEAAJ_KIPEAGPEAI@Z`
- size: `845`
- prototype: `int(ClrDataAccess *__hidden this, unsigned __int64, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x18000b8c0`
- `0x180020f50`
- `0x1800210f0`
- `0x18002127c`
- `0x180022068`
- `0x1800328f0`
- `0x180036e60`
- `0x18007344c`
- `0x180081de0`
- `0x18008dae8`
- `0x1800f0d20`
- `0x1800f5978`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180036eb6`
- `KERNEL32!EnterCriticalSection` at `0x180036eb6`
- `KERNEL32!LeaveCriticalSection` at `0x180037182`
- `KERNEL32!LeaveCriticalSection` at `0x180037182`
- `KERNEL32!HeapFree` at `0x180037162`
- `KERNEL32!HeapFree` at `0x180037162`
- `KERNEL32!GetProcessHeap` at `0x18003714d`
- `KERNEL32!GetProcessHeap` at `0x18003714d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ClrDataAccess::GetMethodTableName(
        ClrDataAccess *this,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int *a5)
{
  rsize_t v6; // r15
  ClrDataAccess *v10; // r13
  unsigned int v11; // ebx
  struct MethodTable *v12; // r12
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  unsigned __int64 *v16; // rax
  void *v17; // rax
  __int64 v18; // rdx
  const wchar_t *v19; // r8
  unsigned __int64 *Module; // rax
  __int64 *v21; // rax
  __int64 *v22; // r14
  __int64 v23; // rdx
  wchar_t *v24; // r14
  wchar_t *v25; // rdi
  HANDLE ProcessHeap; // rax
  struct Exception *v27; // rbx
  BOOL v28; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v30; // rcx
  unsigned int v31; // [rsp+20h] [rbp-2D8h] BYREF
  int v32[2]; // [rsp+28h] [rbp-2D0h] BYREF
  __int64 TargetAddrForHostAddr; // [rsp+30h] [rbp-2C8h] BYREF
  BOOL v34; // [rsp+38h] [rbp-2C0h]
  ClrDataAccess *v35; // [rsp+40h] [rbp-2B8h]
  __int64 v36; // [rsp+50h] [rbp-2A8h]
  _QWORD v37[3]; // [rsp+58h] [rbp-2A0h] BYREF
  __int64 v38; // [rsp+70h] [rbp-288h] BYREF
  int v39; // [rsp+78h] [rbp-280h]
  __int64 v40; // [rsp+80h] [rbp-278h] BYREF
  _DWORD v41[2]; // [rsp+90h] [rbp-268h] BYREF
  int v42; // [rsp+98h] [rbp-260h]
  wchar_t *Source; // [rsp+A0h] [rbp-258h]
  __int16 v44; // [rsp+A8h] [rbp-250h] BYREF

  v6 = a3;
  if ( !a2 )
    return 2147942487LL;
  EnterCriticalSection(&g_dacCritSec);
  v10 = g_dacImpl;
  v35 = g_dacImpl;
  g_dacImpl = (ClrDataAccess *)((char *)this - 16);
  v11 = 0;
  v31 = 0;
  v36 = 0;
  try
  {
    try
    {
      v32[1] = HIDWORD(a2);
      v12 = (struct MethodTable *)DacInstantiateTypeByAddressHelper(a2, 0x40u, 1, 1);
      v32[0] = 0;
      *(_QWORD *)v32 = (unsigned int)*g_pFreeObjectMethodTable[0] + DacGlobalBase(v14, v13, v15);
      v16 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(*(unsigned __int64 *)v32, 8u, 1, 1);
      v17 = DacInstantiateTypeByAddressHelper(*v16, 0x40u, 1, 1);
      LOBYTE(v18) = 1;
      if ( a2 == DacGetTargetAddrForHostAddr(v17, v18) )
      {
        if ( a5 )
          *a5 = 5;
        if ( !a4 || !(_DWORD)v6 )
          goto LABEL_50;
        v19 = L"Free";
        goto LABEL_18;
      }
      if ( !(unsigned int)DacValidateMethodTable(v12, v32) )
      {
        v11 = -2147024809;
        v31 = -2147024809;
        goto LABEL_50;
      }
      Module = (unsigned __int64 *)MethodTable::GetModule(v12, &TargetAddrForHostAddr);
      v21 = DacInstantiateClassByVTable(*Module, 1576, 1);
      v22 = DacInstantiateClassByVTable(v21[2], 200, 1);
      if ( DacInstantiateTypeByAddressHelper(v22[3], 0xD0u, 1, 1) || (TargetAddrForHostAddr = v22[2]) != 0 )
      {
        v42 = 0;
        Source = (wchar_t *)&v44;
        v41[1] = 512;
        v41[0] = 2;
        v44 = 0;
        LOBYTE(v23) = 1;
        TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(v12, v23);
        v38 = 0;
        v39 = 0;
        TypeString::AppendType(v41, TargetAddrForHostAddr, &v38, 3);
        if ( v41[0] >> ((v42 & 1) == 0) == 1 )
        {
          v11 = -2147024882;
          v31 = -2147024882;
        }
        else
        {
          SString::ConvertToUnicode((SString *)v41);
          v24 = Source;
          if ( a5 )
            *a5 = SString::GetCount((SString *)v41) + 1;
          if ( a4 && (_DWORD)v6 )
          {
            wcsncpy_s(a4, v6, v24, 0xFFFFFFFFFFFFFFFFuLL);
            a4[(unsigned int)(v6 - 1)] = 0;
          }
        }
        if ( (v42 & 8) != 0 )
        {
          v25 = Source;
          if ( Source )
          {
            ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
            if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
            {
              ProcessHeap = GetProcessHeap();
              `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
            }
            HeapFree(ProcessHeap, 0, v25);
          }
        }
        goto LABEL_50;
      }
      if ( a5 )
        *a5 = 16;
      if ( a4 )
      {
        v19 = L"<Unloaded Type>";
LABEL_18:
        wcsncpy_s(a4, v6, v19, 0xFFFFFFFFFFFFFFFFuLL);
      }
    }
    catch ( Exception *v40 )
    {
      v36 = v40;
      throw;
    }
  }
  catch ( ... )
  {
    v37[1] = 0;
    v37[0] = &DelegatingException::`vftable';
    v37[2] = -1;
    v27 = (struct Exception *)v36;
    TargetAddrForHostAddr = v36;
    v28 = v36 != 0;
    v34 = v28;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v30 = (struct Exception *)v37;
    if ( v27 )
      v30 = v27;
    if ( !DacExceptionFilter(v30, (ClrDataAccess *)((char *)this - 16), (int *)&v31) )
    {
      v34 = 0;
      throw;
    }
    if ( v28 )
    {
      if ( v27 )
      {
        if ( !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v27 + 80LL))(v27) )
          (**(void (__fastcall ***)(struct Exception *, __int64))v27)(v27, 5);
      }
      v34 = 0;
    }
    DelegatingException::~DelegatingException((DelegatingException *)v37);
    v10 = v35;
    v11 = v31;
  }
LABEL_50:
  g_dacImpl = v10;
  LeaveCriticalSection(&g_dacCritSec);
  return v11;
}

```

## disassembly

```asm
0x180036e60  mov     [rsp+arg_0], rcx
0x180036e65  push    rbx
0x180036e66  push    rsi
0x180036e67  push    rdi
0x180036e68  push    r12
0x180036e6a  push    r13
0x180036e6c  push    r14
0x180036e6e  push    r15
0x180036e70  sub     rsp, 2C0h
0x180036e77  mov     rax, cs:__security_cookie
0x180036e7e  xor     rax, rsp
0x180036e81  mov     [rsp+2F8h+var_48], rax
0x180036e89  mov     rsi, r9
0x180036e8c  mov     r15d, r8d
0x180036e8f  mov     r14, rdx
0x180036e92  mov     rbx, rcx
0x180036e95  mov     rdi, [rsp+2F8h+arg_20]
0x180036e9d  xor     r12d, r12d
0x180036ea0  test    rdx, rdx
0x180036ea3  jnz     short loc_180036EAF
0x180036ea5  mov     eax, 80070057h
0x180036eaa  jmp     loc_18003718A
0x180036eaf  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180036eb6  call    cs:__imp_EnterCriticalSection
0x180036ebc  mov     r13, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x180036ec3  mov     [rsp+2F8h+var_2B8], r13
0x180036ec8  lea     rax, [rbx-10h]
0x180036ecc  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rax; ClrDataAccess * g_dacImpl
0x180036ed3  mov     ebx, r12d
0x180036ed6  mov     [rsp+2F8h+var_2D8], ebx
0x180036eda  mov     [rsp+2F8h+var_2A8], r12
0x180036edf  lea     rax, [rsp+2F8h+var_2B0]
0x180036ee4  mov     qword ptr [rsp+2F8h+var_2D0], rax
0x180036ee9  mov     qword ptr [rsp+2F8h+var_2D0], r14
0x180036eee  mov     r9b, 1; bool
0x180036ef1  mov     r8b, r9b; bool
0x180036ef4  mov     edx, 40h ; '@'; unsigned int
0x180036ef9  mov     rcx, r14; unsigned __int64
0x180036efc  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036f01  mov     r12, rax
0x180036f04  and     [rsp+2F8h+var_2D0], 0
0x180036f09  call    DacGlobalBase
0x180036f0e  mov     r10, rax
0x180036f11  mov     rax, cs:?g_pFreeObjectMethodTable@@3V?$__GlobalPtr@PEAVMethodTable@@V?$__DPtr@VMethodTable@@@@@@A; __GlobalPtr<MethodTable *,__DPtr<MethodTable>> g_pFreeObjectMethodTable
0x180036f18  mov     ecx, [rax]
0x180036f1a  add     r10, rcx
0x180036f1d  mov     qword ptr [rsp+2F8h+var_2D0], r10
0x180036f22  mov     r9b, 1; bool
0x180036f25  mov     r8b, r9b; bool
0x180036f28  mov     edx, 8; unsigned int
0x180036f2d  mov     rcx, r10; unsigned __int64
0x180036f30  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036f35  mov     r9b, 1; bool
0x180036f38  mov     r8b, r9b; bool
0x180036f3b  mov     edx, 40h ; '@'; unsigned int
0x180036f40  mov     rcx, [rax]; unsigned __int64
0x180036f43  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036f48  mov     dl, 1
0x180036f4a  mov     rcx, rax
0x180036f4d  call    DacGetTargetAddrForHostAddr
0x180036f52  cmp     r14, rax
0x180036f55  jnz     short loc_180036F80
0x180036f57  test    rdi, rdi
0x180036f5a  jz      short loc_180036F62
0x180036f5c  mov     dword ptr [rdi], 5
0x180036f62  test    rsi, rsi
0x180036f65  jz      loc_180037169
0x180036f6b  test    r15d, r15d
0x180036f6e  jz      loc_180037169
0x180036f74  lea     r8, aFree; "Free"
0x180036f7b  jmp     loc_180037015
0x180036f80  lea     rdx, [rsp+2F8h+var_2D0]; int *
0x180036f85  mov     rcx, r12; struct MethodTable *
0x180036f88  call    ?DacValidateMethodTable@@YAHPEAVMethodTable@@AEAH@Z; DacValidateMethodTable(MethodTable *,int &)
0x180036f8d  test    eax, eax
0x180036f8f  jnz     short loc_180036F9F
0x180036f91  mov     ebx, 80070057h
0x180036f96  mov     [rsp+2F8h+var_2D8], ebx
0x180036f9a  jmp     loc_180037169
0x180036f9f  lea     rdx, [rsp+2F8h+var_2C8]
0x180036fa4  mov     rcx, r12
0x180036fa7  call    ?GetModule@MethodTable@@QEAA?AV?$__VPtr@VModule@@@@XZ; MethodTable::GetModule(void)
0x180036fac  mov     r8b, 1
0x180036faf  mov     edx, 628h
0x180036fb4  mov     rcx, [rax]; unsigned __int64
0x180036fb7  call    DacInstantiateClassByVTable
0x180036fbc  mov     r8b, 1
0x180036fbf  mov     edx, 0C8h
0x180036fc4  mov     rcx, [rax+10h]; unsigned __int64
0x180036fc8  call    DacInstantiateClassByVTable
0x180036fcd  mov     r14, rax
0x180036fd0  mov     r9b, 1; bool
0x180036fd3  mov     r8b, r9b; bool
0x180036fd6  mov     edx, 0D0h; unsigned int
0x180036fdb  mov     rcx, [rax+18h]; unsigned __int64
0x180036fdf  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036fe4  test    rax, rax
0x180036fe7  jnz     short loc_180037029
0x180036fe9  mov     rax, [r14+10h]
0x180036fed  mov     [rsp+2F8h+var_2C8], rax
0x180036ff2  xor     r14d, r14d
0x180036ff5  test    rax, rax
0x180036ff8  jnz     short loc_18003702C
0x180036ffa  test    rdi, rdi
0x180036ffd  jz      short loc_180037005
0x180036fff  mov     dword ptr [rdi], 10h
0x180037005  test    rsi, rsi
0x180037008  jz      loc_180037169
0x18003700e  lea     r8, aUnloadedType; "<Unloaded Type>"
0x180037015  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180037019  mov     rdx, r15; SizeInWords
0x18003701c  mov     rcx, rsi; Destination
0x18003701f  call    wcsncpy_s
0x180037024  jmp     loc_180037169
0x180037029  xor     r14d, r14d
0x18003702c  mov     [rsp+2F8h+var_268], r14d
0x180037034  mov     [rsp+2F8h+var_264], r14d
0x18003703c  mov     [rsp+2F8h+var_260], r14d
0x180037044  mov     [rsp+2F8h+Source], r14
0x18003704c  lea     rax, [rsp+2F8h+var_250]
0x180037054  mov     [rsp+2F8h+Source], rax
0x18003705c  mov     [rsp+2F8h+var_264], 200h
0x180037067  mov     [rsp+2F8h+var_268], 2
0x180037072  mov     rax, [rsp+2F8h+Source]
0x18003707a  mov     [rax], r14w
0x18003707e  mov     dl, 1
0x180037080  mov     rcx, r12
0x180037083  call    DacGetTargetAddrForHostAddr
0x180037088  mov     [rsp+2F8h+var_2C8], rax
0x18003708d  mov     [rsp+2F8h+var_288], r14
0x180037092  mov     [rsp+2F8h+var_280], r14d
0x180037097  mov     r9d, 3
0x18003709d  lea     r8, [rsp+2F8h+var_288]
0x1800370a2  mov     rdx, rax
0x1800370a5  lea     rcx, [rsp+2F8h+var_268]
0x1800370ad  call    ?AppendType@TypeString@@SAXAEAVSString@@VTypeHandle@@VInstantiation@@K@Z; TypeString::AppendType(SString &,TypeHandle,Instantiation,ulong)
0x1800370b2  mov     ecx, [rsp+2F8h+var_260]
0x1800370b9  not     ecx
0x1800370bb  and     ecx, 1
0x1800370be  mov     eax, [rsp+2F8h+var_268]
0x1800370c5  shr     eax, cl
0x1800370c7  cmp     eax, 1
0x1800370ca  jnz     short loc_1800370D7
0x1800370cc  mov     ebx, 8007000Eh
0x1800370d1  mov     [rsp+2F8h+var_2D8], ebx
0x1800370d5  jmp     short loc_18003712A
0x1800370d7  lea     rcx, [rsp+2F8h+var_268]; this
0x1800370df  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800370e4  mov     r14, [rsp+2F8h+Source]
0x1800370ec  test    rdi, rdi
0x1800370ef  jz      short loc_180037102
0x1800370f1  lea     rcx, [rsp+2F8h+var_268]; this
0x1800370f9  call    ?GetCount@SString@@QEBAIXZ; SString::GetCount(void)
0x1800370fe  inc     eax
0x180037100  mov     [rdi], eax
0x180037102  test    rsi, rsi
0x180037105  jz      short loc_18003712A
0x180037107  test    r15d, r15d
0x18003710a  jz      short loc_18003712A
0x18003710c  mov     rdx, r15; SizeInWords
0x18003710f  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180037113  mov     r8, r14; Source
0x180037116  mov     rcx, rsi; Destination
0x180037119  call    wcsncpy_s
0x18003711e  lea     eax, [r15-1]
0x180037122  xor     r14d, r14d
0x180037125  mov     [rsi+rax*2], r14w
0x18003712a  test    byte ptr [rsp+2F8h+var_260], 8
0x180037132  jz      short loc_180037169
0x180037134  mov     rdi, [rsp+2F8h+Source]
0x18003713c  test    rdi, rdi
0x18003713f  jz      short loc_180037169
0x180037141  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180037148  test    rax, rax
0x18003714b  jnz     short loc_18003715A
0x18003714d  call    cs:__imp_GetProcessHeap
0x180037153  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18003715a  mov     r8, rdi; lpMem
0x18003715d  xor     edx, edx; dwFlags
0x18003715f  mov     rcx, rax; hHeap
0x180037162  call    cs:__imp_HeapFree
0x180037168  nop
0x180037169  jmp     short loc_180037174
0x18003716b  mov     r13, [rsp+2F8h+var_2B8]
0x180037170  mov     ebx, [rsp+2F8h+var_2D8]
0x180037174  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r13; ClrDataAccess * g_dacImpl
0x18003717b  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180037182  call    cs:__imp_LeaveCriticalSection
0x180037188  mov     eax, ebx
0x18003718a  mov     rcx, [rsp+2F8h+var_48]
0x180037192  xor     rcx, rsp; StackCookie
0x180037195  call    __security_check_cookie
0x18003719a  add     rsp, 2C0h
0x1800371a1  pop     r15
0x1800371a3  pop     r14
0x1800371a5  pop     r13
0x1800371a7  pop     r12
0x1800371a9  pop     rdi
0x1800371aa  pop     rsi
0x1800371ab  pop     rbx
0x1800371ac  retn
```
