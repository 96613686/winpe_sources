# ClrDataAccess::GetObjectClassName(unsigned __int64,uint,ushort *,uint *)

- ea: `0x180035cb0`
- end: `0x180035f79`
- name: `?GetObjectClassName@ClrDataAccess@@UEAAJ_KIPEAGPEAI@Z`
- size: `713`
- prototype: `int(ClrDataAccess *__hidden this, unsigned __int64, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x18000b8c0`
- `0x1800210f0`
- `0x18002127c`
- `0x180022068`
- `0x180032724`
- `0x1800328f0`
- `0x180035cb0`
- `0x18007344c`
- `0x180081de0`
- `0x18008dae8`
- `0x1800f0d20`
- `0x1800f5978`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180035d06`
- `KERNEL32!EnterCriticalSection` at `0x180035d06`
- `KERNEL32!LeaveCriticalSection` at `0x180035f4e`
- `KERNEL32!LeaveCriticalSection` at `0x180035f4e`
- `KERNEL32!HeapFree` at `0x180035f20`
- `KERNEL32!HeapFree` at `0x180035f20`
- `KERNEL32!GetProcessHeap` at `0x180035f0b`
- `KERNEL32!GetProcessHeap` at `0x180035f0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ClrDataAccess::GetObjectClassName(
        struct ICorDebugDataTarget **this,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int *a5)
{
  rsize_t v6; // r13
  unsigned int v9; // ebx
  ClrDataAccess *v11; // r12
  unsigned __int64 v12; // rax
  struct MethodTable *v13; // rsi
  unsigned __int64 *Module; // rax
  __int64 *v15; // rax
  __int64 *v16; // rdi
  __int64 v17; // rdx
  wchar_t *v18; // rdi
  wchar_t *v19; // rdi
  HANDLE ProcessHeap; // rax
  struct Exception *v21; // rbx
  BOOL v22; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v24; // rcx
  unsigned int v25; // [rsp+20h] [rbp-2D8h] BYREF
  int v26[2]; // [rsp+28h] [rbp-2D0h] BYREF
  __int64 TargetAddrForHostAddr; // [rsp+30h] [rbp-2C8h] BYREF
  BOOL v28; // [rsp+38h] [rbp-2C0h]
  struct ICorDebugDataTarget **v29; // [rsp+40h] [rbp-2B8h]
  ClrDataAccess *v30; // [rsp+48h] [rbp-2B0h]
  char v31; // [rsp+50h] [rbp-2A8h] BYREF
  __int64 v32; // [rsp+58h] [rbp-2A0h]
  _QWORD v33[3]; // [rsp+60h] [rbp-298h] BYREF
  __int64 v34; // [rsp+78h] [rbp-280h] BYREF
  int v35; // [rsp+80h] [rbp-278h]
  __int64 v36; // [rsp+88h] [rbp-270h] BYREF
  _DWORD v37[2]; // [rsp+90h] [rbp-268h] BYREF
  int v38; // [rsp+98h] [rbp-260h]
  wchar_t *Source; // [rsp+A0h] [rbp-258h]
  __int16 v40; // [rsp+A8h] [rbp-250h] BYREF

  v6 = a3;
  v29 = this;
  v9 = 0;
  if ( !a2 )
    return 2147942487LL;
  EnterCriticalSection(&g_dacCritSec);
  v11 = g_dacImpl;
  v30 = g_dacImpl;
  g_dacImpl = (ClrDataAccess *)(this - 2);
  v25 = 0;
  v32 = 0;
  try
  {
    try
    {
      *(_QWORD *)v26 = &v31;
      v12 = DACGetMethodTableFromObjectPointer(a2, this[3]);
      if ( v12 )
      {
        v26[1] = HIDWORD(v12);
        v13 = (struct MethodTable *)DacInstantiateTypeByAddressHelper(v12, 0x40u, 1, 1);
        v26[0] = 0;
        if ( (unsigned int)DacValidateMethodTable(v13, v26) )
        {
          Module = (unsigned __int64 *)MethodTable::GetModule(v13, &TargetAddrForHostAddr);
          v15 = DacInstantiateClassByVTable(*Module, 1576, 1);
          v16 = DacInstantiateClassByVTable(v15[2], 200, 1);
          if ( DacInstantiateTypeByAddressHelper(v16[3], 0xD0u, 1, 1) || (TargetAddrForHostAddr = v16[2]) != 0 )
          {
            v38 = 0;
            Source = (wchar_t *)&v40;
            v37[1] = 512;
            v37[0] = 2;
            v40 = 0;
            LOBYTE(v17) = 1;
            TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(v13, v17);
            v34 = 0;
            v35 = 0;
            TypeString::AppendType(v37, TargetAddrForHostAddr, &v34, 3);
            SString::ConvertToUnicode((SString *)v37);
            v18 = Source;
            if ( a5 )
              *a5 = SString::GetCount((SString *)v37) + 1;
            if ( a4 && (_DWORD)v6 )
            {
              wcsncpy_s(a4, v6, v18, 0xFFFFFFFFFFFFFFFFuLL);
              a4[(unsigned int)(v6 - 1)] = 0;
            }
            if ( (v38 & 8) != 0 )
            {
              v19 = Source;
              if ( Source )
              {
                ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
                if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
                {
                  ProcessHeap = GetProcessHeap();
                  `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
                }
                HeapFree(ProcessHeap, 0, v19);
              }
            }
          }
          else
          {
            if ( a5 )
              *a5 = 16;
            if ( a4 )
              wcsncpy_s(a4, v6, L"<Unloaded Type>", 0xFFFFFFFFFFFFFFFFuLL);
          }
        }
        else
        {
          v9 = -2147024809;
          v25 = -2147024809;
        }
      }
      else
      {
        v9 = -2147024809;
        v25 = -2147024809;
        v26[0] = 0;
      }
    }
    catch ( Exception *v36 )
    {
      v32 = v36;
      throw;
    }
  }
  catch ( ... )
  {
    v33[1] = 0;
    v33[0] = &DelegatingException::`vftable';
    v33[2] = -1;
    v21 = (struct Exception *)v32;
    TargetAddrForHostAddr = v32;
    v22 = v32 != 0;
    v28 = v22;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v24 = (struct Exception *)v33;
    if ( v21 )
      v24 = v21;
    if ( !DacExceptionFilter(v24, (struct ClrDataAccess *)(v29 - 2), (int *)&v25) )
    {
      v28 = 0;
      throw;
    }
    if ( v22 )
    {
      if ( v21 )
      {
        if ( !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v21 + 80LL))(v21) )
          (**(void (__fastcall ***)(struct Exception *, __int64))v21)(v21, 5);
      }
      v28 = 0;
    }
    DelegatingException::~DelegatingException((DelegatingException *)v33);
    v11 = v30;
    v9 = v25;
  }
  g_dacImpl = v11;
  LeaveCriticalSection(&g_dacCritSec);
  return v9;
}

```

## disassembly

```asm
0x180035cb0  push    rbx
0x180035cb2  push    rsi
0x180035cb3  push    rdi
0x180035cb4  push    r12
0x180035cb6  push    r13
0x180035cb8  push    r14
0x180035cba  push    r15
0x180035cbc  sub     rsp, 2C0h
0x180035cc3  mov     rax, cs:__security_cookie
0x180035cca  xor     rax, rsp
0x180035ccd  mov     [rsp+2F8h+var_48], rax
0x180035cd5  mov     r15, r9
0x180035cd8  mov     r13d, r8d
0x180035cdb  mov     rsi, rdx
0x180035cde  mov     rdi, rcx
0x180035ce1  mov     [rsp+2F8h+var_2B8], rcx
0x180035ce6  mov     r14, [rsp+2F8h+arg_20]
0x180035cee  xor     ebx, ebx
0x180035cf0  test    rdx, rdx
0x180035cf3  jnz     short loc_180035CFF
0x180035cf5  mov     eax, 80070057h
0x180035cfa  jmp     loc_180035F56
0x180035cff  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180035d06  call    cs:__imp_EnterCriticalSection
0x180035d0c  mov     r12, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x180035d13  mov     [rsp+2F8h+var_2B0], r12
0x180035d18  lea     rax, [rdi-10h]
0x180035d1c  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rax; ClrDataAccess * g_dacImpl
0x180035d23  mov     [rsp+2F8h+var_2D8], ebx
0x180035d27  and     [rsp+2F8h+var_2A0], rbx
0x180035d2c  lea     rax, [rsp+2F8h+var_2A8]
0x180035d31  mov     qword ptr [rsp+2F8h+var_2D0], rax
0x180035d36  mov     rdx, [rdi+18h]; struct ICorDebugDataTarget *
0x180035d3a  mov     rcx, rsi; unsigned __int64
0x180035d3d  call    ?DACGetMethodTableFromObjectPointer@@YA_K_KPEAUICorDebugDataTarget@@@Z; DACGetMethodTableFromObjectPointer(unsigned __int64,ICorDebugDataTarget *)
0x180035d42  xor     edi, edi
0x180035d44  test    rax, rax
0x180035d47  jz      loc_180035F28
0x180035d4d  mov     qword ptr [rsp+2F8h+var_2D0], rax
0x180035d52  mov     r9b, 1; bool
0x180035d55  mov     r8b, r9b; bool
0x180035d58  lea     edx, [rdi+40h]; unsigned int
0x180035d5b  mov     rcx, rax; unsigned __int64
0x180035d5e  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180035d63  mov     rsi, rax
0x180035d66  mov     [rsp+2F8h+var_2D0], edi
0x180035d6a  lea     rdx, [rsp+2F8h+var_2D0]; int *
0x180035d6f  mov     rcx, rax; struct MethodTable *
0x180035d72  call    ?DacValidateMethodTable@@YAHPEAVMethodTable@@AEAH@Z; DacValidateMethodTable(MethodTable *,int &)
0x180035d77  test    eax, eax
0x180035d79  jnz     short loc_180035D89
0x180035d7b  mov     ebx, 80070057h
0x180035d80  mov     [rsp+2F8h+var_2D8], ebx
0x180035d84  jmp     loc_180035F35
0x180035d89  lea     rdx, [rsp+2F8h+var_2C8]
0x180035d8e  mov     rcx, rsi
0x180035d91  call    ?GetModule@MethodTable@@QEAA?AV?$__VPtr@VModule@@@@XZ; MethodTable::GetModule(void)
0x180035d96  mov     r8b, 1
0x180035d99  mov     edx, 628h
0x180035d9e  mov     rcx, [rax]; unsigned __int64
0x180035da1  call    DacInstantiateClassByVTable
0x180035da6  mov     r8b, 1
0x180035da9  mov     edx, 0C8h
0x180035dae  mov     rcx, [rax+10h]; unsigned __int64
0x180035db2  call    DacInstantiateClassByVTable
0x180035db7  mov     rdi, rax
0x180035dba  mov     r9b, 1; bool
0x180035dbd  mov     r8b, r9b; bool
0x180035dc0  mov     edx, 0D0h; unsigned int
0x180035dc5  mov     rcx, [rax+18h]; unsigned __int64
0x180035dc9  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180035dce  xor     ecx, ecx
0x180035dd0  test    rax, rax
0x180035dd3  jnz     short loc_180035E13
0x180035dd5  mov     rax, [rdi+10h]
0x180035dd9  mov     [rsp+2F8h+var_2C8], rax
0x180035dde  test    rax, rax
0x180035de1  jnz     short loc_180035E13
0x180035de3  test    r14, r14
0x180035de6  jz      short loc_180035DEF
0x180035de8  mov     dword ptr [r14], 10h
0x180035def  test    r15, r15
0x180035df2  jz      loc_180035F35
0x180035df8  mov     rdx, r13; SizeInWords
0x180035dfb  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180035dff  lea     r8, aUnloadedType; "<Unloaded Type>"
0x180035e06  mov     rcx, r15; Destination
0x180035e09  call    wcsncpy_s
0x180035e0e  jmp     loc_180035F35
0x180035e13  mov     [rsp+2F8h+var_268], ecx
0x180035e1a  mov     [rsp+2F8h+var_264], ecx
0x180035e21  mov     [rsp+2F8h+var_260], ecx
0x180035e28  mov     [rsp+2F8h+Source], rcx
0x180035e30  lea     rax, [rsp+2F8h+var_250]
0x180035e38  mov     [rsp+2F8h+Source], rax
0x180035e40  mov     [rsp+2F8h+var_264], 200h
0x180035e4b  mov     [rsp+2F8h+var_268], 2
0x180035e56  mov     rax, [rsp+2F8h+Source]
0x180035e5e  mov     [rax], cx
0x180035e61  mov     dl, 1
0x180035e63  mov     rcx, rsi
0x180035e66  call    DacGetTargetAddrForHostAddr
0x180035e6b  mov     [rsp+2F8h+var_2C8], rax
0x180035e70  xor     esi, esi
0x180035e72  mov     [rsp+2F8h+var_280], rsi
0x180035e77  mov     [rsp+2F8h+var_278], esi
0x180035e7e  lea     r9d, [rsi+3]
0x180035e82  lea     r8, [rsp+2F8h+var_280]
0x180035e87  mov     rdx, rax
0x180035e8a  lea     rcx, [rsp+2F8h+var_268]
0x180035e92  call    ?AppendType@TypeString@@SAXAEAVSString@@VTypeHandle@@VInstantiation@@K@Z; TypeString::AppendType(SString &,TypeHandle,Instantiation,ulong)
0x180035e97  lea     rcx, [rsp+2F8h+var_268]; this
0x180035e9f  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180035ea4  mov     rdi, [rsp+2F8h+Source]
0x180035eac  test    r14, r14
0x180035eaf  jz      short loc_180035EC3
0x180035eb1  lea     rcx, [rsp+2F8h+var_268]; this
0x180035eb9  call    ?GetCount@SString@@QEBAIXZ; SString::GetCount(void)
0x180035ebe  inc     eax
0x180035ec0  mov     [r14], eax
0x180035ec3  test    r15, r15
0x180035ec6  jz      short loc_180035EE8
0x180035ec8  test    r13d, r13d
0x180035ecb  jz      short loc_180035EE8
0x180035ecd  mov     rdx, r13; SizeInWords
0x180035ed0  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180035ed4  mov     r8, rdi; Source
0x180035ed7  mov     rcx, r15; Destination
0x180035eda  call    wcsncpy_s
0x180035edf  lea     eax, [r13-1]
0x180035ee3  mov     [r15+rax*2], si
0x180035ee8  test    byte ptr [rsp+2F8h+var_260], 8
0x180035ef0  jz      short loc_180035F26
0x180035ef2  mov     rdi, [rsp+2F8h+Source]
0x180035efa  test    rdi, rdi
0x180035efd  jz      short loc_180035F26
0x180035eff  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180035f06  test    rax, rax
0x180035f09  jnz     short loc_180035F18
0x180035f0b  call    cs:__imp_GetProcessHeap
0x180035f11  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180035f18  mov     r8, rdi; lpMem
0x180035f1b  xor     edx, edx; dwFlags
0x180035f1d  mov     rcx, rax; hHeap
0x180035f20  call    cs:__imp_HeapFree
0x180035f26  jmp     short loc_180035F35
0x180035f28  mov     ebx, 80070057h
0x180035f2d  mov     [rsp+2F8h+var_2D8], ebx
0x180035f31  mov     [rsp+2F8h+var_2D0], edi
0x180035f35  jmp     short loc_180035F40
0x180035f37  mov     r12, [rsp+2F8h+var_2B0]
0x180035f3c  mov     ebx, [rsp+2F8h+var_2D8]
0x180035f40  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r12; ClrDataAccess * g_dacImpl
0x180035f47  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180035f4e  call    cs:__imp_LeaveCriticalSection
0x180035f54  mov     eax, ebx
0x180035f56  mov     rcx, [rsp+2F8h+var_48]
0x180035f5e  xor     rcx, rsp; StackCookie
0x180035f61  call    __security_check_cookie
0x180035f66  add     rsp, 2C0h
0x180035f6d  pop     r15
0x180035f6f  pop     r14
0x180035f71  pop     r13
0x180035f73  pop     r12
0x180035f75  pop     rdi
0x180035f76  pop     rsi
0x180035f77  pop     rbx
0x180035f78  retn
```
