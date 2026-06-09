# ClrDataAccess::GetAssemblyName(unsigned __int64,uint,ushort *,uint *)

- ea: `0x18003a510`
- end: `0x18003a809`
- name: `?GetAssemblyName@ClrDataAccess@@UEAAJ_KIPEAGPEAI@Z`
- size: `761`
- prototype: `int(ClrDataAccess *__hidden this, unsigned __int64, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18000b8c0`
- `0x180020f50`
- `0x1800210f0`
- `0x18002127c`
- `0x18003a510`
- `0x180040974`
- `0x18007344c`
- `0x180074898`
- `0x1800f0d20`
- `0x1800f5978`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18003a554`
- `KERNEL32!EnterCriticalSection` at `0x18003a554`
- `KERNEL32!LeaveCriticalSection` at `0x18003a7de`
- `KERNEL32!LeaveCriticalSection` at `0x18003a7de`
- `KERNEL32!HeapFree` at `0x18003a7b4`
- `KERNEL32!HeapFree` at `0x18003a7b4`
- `KERNEL32!GetProcessHeap` at `0x18003a79f`
- `KERNEL32!GetProcessHeap` at `0x18003a79f`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ClrDataAccess::GetAssemblyName(
        ClrDataAccess *this,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int *a5)
{
  rsize_t v6; // r14
  ClrDataAccess *v9; // r12
  unsigned int v10; // ebx
  _QWORD *v11; // rax
  _QWORD *v12; // rdi
  __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  __int64 v15; // r8
  unsigned __int64 *v16; // rax
  _DWORD *v17; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  __int64 v20; // r8
  unsigned __int64 *v21; // rax
  SString *v22; // rax
  __int64 *v23; // rax
  int v24; // r8d
  wchar_t *v25; // rdi
  wchar_t *v26; // rdi
  HANDLE ProcessHeap; // rax
  struct Exception *v29; // rbx
  BOOL v30; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v32; // rcx
  unsigned int v33; // [rsp+20h] [rbp-2B8h] BYREF
  __int64 v34; // [rsp+28h] [rbp-2B0h]
  BOOL v35; // [rsp+30h] [rbp-2A8h]
  ClrDataAccess *v36; // [rsp+38h] [rbp-2A0h]
  unsigned __int64 v37; // [rsp+48h] [rbp-290h]
  _QWORD v38[3]; // [rsp+50h] [rbp-288h] BYREF
  unsigned __int64 v39; // [rsp+68h] [rbp-270h] BYREF
  _DWORD v40[2]; // [rsp+70h] [rbp-268h] BYREF
  int v41; // [rsp+78h] [rbp-260h]
  wchar_t *Source; // [rsp+80h] [rbp-258h]
  __int16 v43; // [rsp+88h] [rbp-250h] BYREF

  v6 = a3;
  EnterCriticalSection(&g_dacCritSec);
  v9 = g_dacImpl;
  v36 = g_dacImpl;
  g_dacImpl = (ClrDataAccess *)((char *)this - 16);
  v10 = 0;
  v33 = 0;
  v37 = 0;
  try
  {
    try
    {
      v34 = a2;
      v11 = DacInstantiateTypeByAddressHelper(a2, 0x118u, 1, 1);
      v12 = v11;
      if ( a4 )
        *a4 = 0;
      v14 = DacInstantiateClassByVTable(v11[12], 280, 1)[1];
      if ( v14 )
      {
        v17 = DacInstantiateTypeByAddressHelper(v14, 0xD0u, 1, 1);
      }
      else
      {
        v34 = (unsigned int)*SString::s_Empty[0] + DacGlobalBase(0, v13, v15);
        v16 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(v34, 8u, 1, 1);
        v17 = DacInstantiateTypeByAddressHelper(*v16, 0x18u, 1, 1);
      }
      if ( *v17 >> ((v17[2] & 1) == 0) == 1 )
      {
        if ( DacInstantiateClassByVTable(v12[12], 280, 1)[1] )
        {
          v41 = 0;
          Source = (wchar_t *)&v43;
          v40[1] = 512;
          v40[0] = 2;
          v43 = 0;
          v23 = DacInstantiateClassByVTable(v12[12], 280, 1);
          PEAssembly::GetDisplayName((PEAssembly *)v23, (struct SString *)v40, v24);
          SString::ConvertToUnicode((SString *)v40);
          v25 = Source;
          if ( a5 )
            *a5 = SString::GetCount((SString *)v40) + 1;
          if ( a4 && (_DWORD)v6 )
          {
            wcsncpy_s(a4, v6, v25, 0xFFFFFFFFFFFFFFFFuLL);
            a4[(unsigned int)(v6 - 1)] = 0;
          }
          if ( (v41 & 8) != 0 )
          {
            v26 = Source;
            if ( Source )
            {
              ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
              if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
              {
                ProcessHeap = GetProcessHeap();
                `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
              }
              HeapFree(ProcessHeap, 0, v26);
            }
          }
          goto LABEL_46;
        }
      }
      else
      {
        v19 = DacInstantiateClassByVTable(v12[12], 280, 1)[1];
        if ( v19 )
        {
          v22 = (SString *)DacInstantiateTypeByAddressHelper(v19, 0xD0u, 1, 1);
        }
        else
        {
          v34 = (unsigned int)*SString::s_Empty[0] + DacGlobalBase(0, v18, v20);
          v21 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(v34, 8u, 1, 1);
          v22 = (SString *)DacInstantiateTypeByAddressHelper(*v21, 0x18u, 1, 1);
        }
        if ( SString::DacGetUnicode(v22, v6, a4, a5) )
        {
          if ( a4 )
            a4[(unsigned int)(v6 - 1)] = 0;
          goto LABEL_46;
        }
      }
      v10 = -2147467259;
      v33 = -2147467259;
    }
    catch ( Exception *v39 )
    {
      v37 = v39;
      throw;
    }
  }
  catch ( ... )
  {
    v38[1] = 0;
    v38[0] = &DelegatingException::`vftable';
    v38[2] = -1;
    v29 = (struct Exception *)v37;
    v34 = v37;
    v30 = v37 != 0;
    v35 = v30;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v32 = (struct Exception *)v38;
    if ( v29 )
      v32 = v29;
    if ( !DacExceptionFilter(v32, (ClrDataAccess *)((char *)this - 16), (int *)&v33) )
    {
      v35 = 0;
      throw;
    }
    if ( v30 )
    {
      if ( v29 )
      {
        if ( !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v29 + 80LL))(v29) )
          (**(void (__fastcall ***)(struct Exception *, __int64))v29)(v29, 5);
      }
      v35 = 0;
    }
    DelegatingException::~DelegatingException((DelegatingException *)v38);
    v9 = v36;
    v10 = v33;
  }
LABEL_46:
  g_dacImpl = v9;
  LeaveCriticalSection(&g_dacCritSec);
  return v10;
}

```

## disassembly

```asm
0x18003a510  mov     [rsp+arg_0], rcx
0x18003a515  push    rbx
0x18003a516  push    rsi
0x18003a517  push    rdi
0x18003a518  push    r12
0x18003a51a  push    r13
0x18003a51c  push    r14
0x18003a51e  push    r15
0x18003a520  sub     rsp, 2A0h
0x18003a527  mov     rax, cs:__security_cookie
0x18003a52e  xor     rax, rsp
0x18003a531  mov     [rsp+2D8h+var_48], rax
0x18003a539  mov     rsi, r9
0x18003a53c  mov     r14d, r8d
0x18003a53f  mov     rdi, rdx
0x18003a542  mov     rbx, rcx
0x18003a545  mov     r15, [rsp+2D8h+arg_20]
0x18003a54d  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a554  call    cs:__imp_EnterCriticalSection
0x18003a55a  mov     r12, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x18003a561  mov     [rsp+2D8h+var_2A0], r12
0x18003a566  lea     rax, [rbx-10h]
0x18003a56a  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rax; ClrDataAccess * g_dacImpl
0x18003a571  xor     ebx, ebx
0x18003a573  mov     [rsp+2D8h+var_2B8], ebx
0x18003a577  mov     [rsp+2D8h+var_290], rbx
0x18003a57c  lea     rax, [rsp+2D8h+var_298]
0x18003a581  mov     [rsp+2D8h+var_2B0], rax
0x18003a586  mov     [rsp+2D8h+var_2B0], rdi
0x18003a58b  mov     r9b, 1; bool
0x18003a58e  mov     r8b, r9b; bool
0x18003a591  mov     r13d, 118h
0x18003a597  mov     edx, r13d; unsigned int
0x18003a59a  mov     rcx, rdi; unsigned __int64
0x18003a59d  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003a5a2  mov     rdi, rax
0x18003a5a5  test    rsi, rsi
0x18003a5a8  jz      short loc_18003A5AD
0x18003a5aa  mov     [rsi], bx
0x18003a5ad  mov     r8b, 1
0x18003a5b0  mov     edx, r13d
0x18003a5b3  mov     rcx, [rax+60h]; unsigned __int64
0x18003a5b7  call    DacInstantiateClassByVTable
0x18003a5bc  mov     rcx, [rax+8]; unsigned __int64
0x18003a5c0  test    rcx, rcx
0x18003a5c3  jnz     short loc_18003A606
0x18003a5c5  call    DacGlobalBase
0x18003a5ca  mov     r10, rax
0x18003a5cd  mov     rax, cs:?s_Empty@SString@@0V?$__GlobalPtr@PEAVSString@@V?$__DPtr@VSString@@@@@@A; __GlobalPtr<SString *,__DPtr<SString>> SString::s_Empty
0x18003a5d4  mov     ecx, [rax]
0x18003a5d6  add     r10, rcx
0x18003a5d9  mov     [rsp+2D8h+var_2B0], r10
0x18003a5de  mov     r9b, 1; bool
0x18003a5e1  mov     r8b, r9b; bool
0x18003a5e4  mov     edx, 8; unsigned int
0x18003a5e9  mov     rcx, r10; unsigned __int64
0x18003a5ec  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003a5f1  mov     r9b, 1; bool
0x18003a5f4  mov     r8b, r9b; bool
0x18003a5f7  mov     edx, 18h; unsigned int
0x18003a5fc  mov     rcx, [rax]; unsigned __int64
0x18003a5ff  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003a604  jmp     short loc_18003A616
0x18003a606  mov     r9b, 1; bool
0x18003a609  mov     r8b, r9b; bool
0x18003a60c  mov     edx, 0D0h; unsigned int
0x18003a611  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003a616  mov     ecx, [rax+8]
0x18003a619  not     ecx
0x18003a61b  and     ecx, 1
0x18003a61e  mov     eax, [rax]
0x18003a620  shr     eax, cl
0x18003a622  cmp     eax, 1
0x18003a625  jz      loc_18003A6C1
0x18003a62b  mov     r8b, 1
0x18003a62e  mov     edx, r13d
0x18003a631  mov     rcx, [rdi+60h]; unsigned __int64
0x18003a635  call    DacInstantiateClassByVTable
0x18003a63a  mov     rcx, [rax+8]; unsigned __int64
0x18003a63e  test    rcx, rcx
0x18003a641  jnz     short loc_18003A682
0x18003a643  call    DacGlobalBase
0x18003a648  mov     rcx, rax
0x18003a64b  mov     rax, cs:?s_Empty@SString@@0V?$__GlobalPtr@PEAVSString@@V?$__DPtr@VSString@@@@@@A; __GlobalPtr<SString *,__DPtr<SString>> SString::s_Empty
0x18003a652  mov     r8d, [rax]
0x18003a655  add     rcx, r8; unsigned __int64
0x18003a658  mov     [rsp+2D8h+var_2B0], rcx
0x18003a65d  mov     r9b, 1; bool
0x18003a660  mov     r8b, r9b; bool
0x18003a663  mov     edx, 8; unsigned int
0x18003a668  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003a66d  mov     r9b, 1; bool
0x18003a670  mov     r8b, r9b; bool
0x18003a673  mov     edx, 18h; unsigned int
0x18003a678  mov     rcx, [rax]; unsigned __int64
0x18003a67b  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003a680  jmp     short loc_18003A692
0x18003a682  mov     r9b, 1; bool
0x18003a685  mov     r8b, r9b; bool
0x18003a688  mov     edx, 0D0h; unsigned int
0x18003a68d  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003a692  mov     r9, r15; unsigned int *
0x18003a695  mov     r8, rsi; unsigned __int16 *
0x18003a698  mov     edx, r14d; cchWideChar
0x18003a69b  mov     rcx, rax; this
0x18003a69e  call    ?DacGetUnicode@SString@@QEBA_NIPEAGPEAI@Z; SString::DacGetUnicode(uint,ushort *,uint *)
0x18003a6a3  test    al, al
0x18003a6a5  jz      loc_18003A7BC
0x18003a6ab  test    rsi, rsi
0x18003a6ae  jz      loc_18003A7C5
0x18003a6b4  lea     eax, [r14-1]
0x18003a6b8  mov     [rsi+rax*2], bx
0x18003a6bc  jmp     loc_18003A7C5
0x18003a6c1  mov     r8b, 1
0x18003a6c4  mov     edx, r13d
0x18003a6c7  mov     rcx, [rdi+60h]; unsigned __int64
0x18003a6cb  call    DacInstantiateClassByVTable
0x18003a6d0  cmp     [rax+8], rbx
0x18003a6d4  jz      loc_18003A7BC
0x18003a6da  mov     [rsp+2D8h+var_268], ebx
0x18003a6de  mov     [rsp+2D8h+var_264], ebx
0x18003a6e2  mov     [rsp+2D8h+var_260], ebx
0x18003a6e6  mov     [rsp+2D8h+Source], rbx
0x18003a6ee  lea     rax, [rsp+2D8h+var_250]
0x18003a6f6  mov     [rsp+2D8h+Source], rax
0x18003a6fe  mov     [rsp+2D8h+var_264], 200h
0x18003a706  mov     [rsp+2D8h+var_268], 2
0x18003a70e  mov     rax, [rsp+2D8h+Source]
0x18003a716  mov     [rax], bx
0x18003a719  mov     r8b, 1
0x18003a71c  mov     edx, r13d
0x18003a71f  mov     rcx, [rdi+60h]; unsigned __int64
0x18003a723  call    DacInstantiateClassByVTable
0x18003a728  mov     rcx, rax; this
0x18003a72b  lea     rdx, [rsp+2D8h+var_268]; struct SString *
0x18003a730  call    ?GetDisplayName@PEAssembly@@QEAAXAEAVSString@@K@Z; PEAssembly::GetDisplayName(SString &,ulong)
0x18003a735  lea     rcx, [rsp+2D8h+var_268]; this
0x18003a73a  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003a73f  mov     rdi, [rsp+2D8h+Source]
0x18003a747  test    r15, r15
0x18003a74a  jz      short loc_18003A75B
0x18003a74c  lea     rcx, [rsp+2D8h+var_268]; this
0x18003a751  call    ?GetCount@SString@@QEBAIXZ; SString::GetCount(void)
0x18003a756  inc     eax
0x18003a758  mov     [r15], eax
0x18003a75b  test    rsi, rsi
0x18003a75e  jz      short loc_18003A77F
0x18003a760  test    r14d, r14d
0x18003a763  jz      short loc_18003A77F
0x18003a765  mov     rdx, r14; SizeInWords
0x18003a768  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18003a76c  mov     r8, rdi; Source
0x18003a76f  mov     rcx, rsi; Destination
0x18003a772  call    wcsncpy_s
0x18003a777  lea     eax, [r14-1]
0x18003a77b  mov     [rsi+rax*2], bx
0x18003a77f  test    byte ptr [rsp+2D8h+var_260], 8
0x18003a784  jz      short loc_18003A7BA
0x18003a786  mov     rdi, [rsp+2D8h+Source]
0x18003a78e  test    rdi, rdi
0x18003a791  jz      short loc_18003A7BA
0x18003a793  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18003a79a  test    rax, rax
0x18003a79d  jnz     short loc_18003A7AC
0x18003a79f  call    cs:__imp_GetProcessHeap
0x18003a7a5  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18003a7ac  mov     r8, rdi; lpMem
0x18003a7af  xor     edx, edx; dwFlags
0x18003a7b1  mov     rcx, rax; hHeap
0x18003a7b4  call    cs:__imp_HeapFree
0x18003a7ba  jmp     short loc_18003A7C5
0x18003a7bc  mov     ebx, 80004005h
0x18003a7c1  mov     [rsp+2D8h+var_2B8], ebx
0x18003a7c5  jmp     short loc_18003A7D0
0x18003a7c7  mov     r12, [rsp+2D8h+var_2A0]
0x18003a7cc  mov     ebx, [rsp+2D8h+var_2B8]
0x18003a7d0  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r12; ClrDataAccess * g_dacImpl
0x18003a7d7  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a7de  call    cs:__imp_LeaveCriticalSection
0x18003a7e4  mov     eax, ebx
0x18003a7e6  mov     rcx, [rsp+2D8h+var_48]
0x18003a7ee  xor     rcx, rsp; StackCookie
0x18003a7f1  call    __security_check_cookie
0x18003a7f6  add     rsp, 2A0h
0x18003a7fd  pop     r15
0x18003a7ff  pop     r14
0x18003a801  pop     r13
0x18003a803  pop     r12
0x18003a805  pop     rdi
0x18003a806  pop     rsi
0x18003a807  pop     rbx
0x18003a808  retn
```
