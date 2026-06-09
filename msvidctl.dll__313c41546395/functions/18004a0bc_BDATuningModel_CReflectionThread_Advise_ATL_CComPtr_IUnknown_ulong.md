# BDATuningModel::CReflectionThread::Advise(ATL::CComPtr<IUnknown> &,ulong *)

- ea: `0x18004a0bc`
- end: `0x18004a20d`
- name: `?Advise@CReflectionThread@BDATuningModel@@QEAAJAEAV?$CComPtr@UIUnknown@@@ATL@@PEAK@Z`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004a060`

## callees

- `0x180006b38`
- `0x18004a0bc`
- `0x18004adf4`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18004a100`
- `ole32!CoCreateInstance` at `0x18004a100`
- `KERNEL32!LeaveCriticalSection` at `0x18004a1e6`
- `KERNEL32!LeaveCriticalSection` at `0x18004a1e6`
- `KERNEL32!EnterCriticalSection` at `0x18004a179`
- `KERNEL32!EnterCriticalSection` at `0x18004a1ba`
- `KERNEL32!EnterCriticalSection` at `0x18004a179`
- `KERNEL32!EnterCriticalSection` at `0x18004a1ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall BDATuningModel::CReflectionThread::Advise(
        __int64 a1,
        void (__fastcall ****a2)(_QWORD, GUID *, __int64 *),
        _DWORD *a3)
{
  __int64 *v6; // rbx
  HRESULT result; // eax
  void (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v9; // rax
  struct _RTL_CRITICAL_SECTION *v10; // rdi
  __int64 v11; // rcx
  void (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rdx
  bool v13; // zf
  __int64 (__fastcall *v14)(__int64, void (__fastcall ***)(_QWORD, GUID *, __int64 *), GUID *, _DWORD *); // rax
  int v15; // ebx
  std::bad_alloc *v18; // [rsp+40h] [rbp-38h] BYREF
  std::bad_alloc *v19; // [rsp+48h] [rbp-30h] BYREF
  __int64 v22; // [rsp+98h] [rbp+20h] BYREF

  v6 = (__int64 *)(a1 + 128);
  if ( *(_QWORD *)(a1 + 128)
    || (result = CoCreateInstance(
                   &CLSID_StdGlobalInterfaceTable,
                   0,
                   1u,
                   &GUID_00000146_0000_0000_c000_000000000046,
                   (LPVOID *)(a1 + 128)),
        result >= 0) )
  {
    v8 = *a2;
    v9 = 0;
    v22 = 0;
    if ( v8 )
    {
      (**v8)(v8, &GUID_3d9e3887_1929_423f_8021_43682de95448, &v22);
      v9 = v22;
    }
    v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 88);
    v11 = *v6;
    v12 = *a2;
    v13 = v9 == 0;
    v14 = *(__int64 (__fastcall **)(__int64, void (__fastcall ***)(_QWORD, GUID *, __int64 *), GUID *, _DWORD *))(*(_QWORD *)*v6 + 24LL);
    if ( v13 )
    {
      v15 = v14(v11, v12, &IID_IBroadcastEvent, a3);
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
      if ( v15 >= 0 )
      {
        try
        {
          std::list<unsigned long>::push_back(a1 + 192, a3);
        }
        catch ( std::bad_alloc *v19 )
        {
          guard_dispatch_icall_thunk_10345483385596137414(*(_QWORD *)(a1 + 128), (unsigned int)*a3);
          *a3 = 0;
          v15 = -2147024882;
          v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 88);
        }
      }
    }
    else
    {
      v15 = v14(v11, v12, &IID_IBroadcastEventEx, a3);
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
      if ( v15 >= 0 )
      {
        try
        {
          std::list<unsigned long>::push_back(a1 + 208, a3);
        }
        catch ( std::bad_alloc *v18 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 128) + 32LL))(
            *(_QWORD *)(a1 + 128),
            (unsigned int)*a3);
          *a3 = 0;
          v15 = -2147024882;
          v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 88);
        }
      }
    }
    LeaveCriticalSection(v10);
    if ( v15 >= 0 )
      v15 = 0;
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v22);
    return v15;
  }
  return result;
}

```

## disassembly

```asm
0x18004a0bc  mov     [rsp+arg_10], r8
0x18004a0c1  mov     [rsp+arg_0], rcx
0x18004a0c6  push    rbx
0x18004a0c7  push    rsi
0x18004a0c8  push    rdi
0x18004a0c9  push    r14
0x18004a0cb  push    r15
0x18004a0cd  sub     rsp, 50h
0x18004a0d1  mov     r14, r8
0x18004a0d4  mov     r15, rdx
0x18004a0d7  mov     rsi, rcx
0x18004a0da  lea     rbx, [rcx+80h]
0x18004a0e1  cmp     qword ptr [rbx], 0
0x18004a0e5  jnz     short loc_18004A10E
0x18004a0e7  mov     [rsp+78h+ppv], rbx; ppv
0x18004a0ec  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18004a0f3  xor     edx, edx; pUnkOuter
0x18004a0f5  lea     r8d, [rdx+1]; dwClsContext
0x18004a0f9  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18004a100  call    cs:__imp_CoCreateInstance
0x18004a106  test    eax, eax
0x18004a108  js      loc_18004A201
0x18004a10e  mov     rcx, [r15]
0x18004a111  xor     eax, eax
0x18004a113  mov     [rsp+78h+arg_18], rax
0x18004a11b  test    rcx, rcx
0x18004a11e  jz      short loc_18004A142
0x18004a120  mov     rax, [rcx]
0x18004a123  lea     r8, [rsp+78h+arg_18]
0x18004a12b  lea     rdx, _GUID_3d9e3887_1929_423f_8021_43682de95448
0x18004a132  mov     rax, [rax]
0x18004a135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a13a  mov     rax, [rsp+78h+arg_18]
0x18004a142  lea     rdi, [rsi+58h]
0x18004a146  mov     [rsp+78h+var_48], rdi
0x18004a14b  mov     rcx, [rbx]
0x18004a14e  mov     r8, [rcx]
0x18004a151  mov     r10, [r8+18h]
0x18004a155  mov     r9, r14
0x18004a158  mov     rdx, [r15]
0x18004a15b  test    rax, rax
0x18004a15e  mov     rax, r10
0x18004a161  jz      short loc_18004A1A4
0x18004a163  lea     r8, IID_IBroadcastEventEx
0x18004a16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a16f  mov     ebx, eax
0x18004a171  mov     [rsp+78h+var_40], rdi
0x18004a176  mov     rcx, rdi; lpCriticalSection
0x18004a179  call    cs:__imp_EnterCriticalSection
0x18004a17f  nop
0x18004a180  test    ebx, ebx
0x18004a182  js      short loc_18004A1A2
0x18004a184  lea     rcx, [rsi+0D0h]
0x18004a18b  mov     rdx, r14
0x18004a18e  call    ?push_back@?$list@KV?$allocator@K@std@@@std@@QEAAXAEBK@Z; std::list<ulong>::push_back(ulong const &)
0x18004a193  nop
0x18004a194  jmp     short loc_18004A1A2
0x18004a196  mov     ebx, dword ptr [rsp+78h+arg_0]
0x18004a19d  mov     rdi, [rsp+78h+var_48]
0x18004a1a2  jmp     short loc_18004A1E3
0x18004a1a4  lea     r8, IID_IBroadcastEvent
0x18004a1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1b0  mov     ebx, eax
0x18004a1b2  mov     [rsp+78h+var_40], rdi
0x18004a1b7  mov     rcx, rdi; lpCriticalSection
0x18004a1ba  call    cs:__imp_EnterCriticalSection
0x18004a1c0  nop
0x18004a1c1  test    ebx, ebx
0x18004a1c3  js      short loc_18004A1E3
0x18004a1c5  lea     rcx, [rsi+0C0h]
0x18004a1cc  mov     rdx, r14
0x18004a1cf  call    ?push_back@?$list@KV?$allocator@K@std@@@std@@QEAAXAEBK@Z; std::list<ulong>::push_back(ulong const &)
0x18004a1d4  nop
0x18004a1d5  jmp     short loc_18004A1E3
0x18004a1d7  mov     ebx, dword ptr [rsp+78h+arg_0]
0x18004a1de  mov     rdi, [rsp+78h+var_48]
0x18004a1e3  mov     rcx, rdi; lpCriticalSection
0x18004a1e6  call    cs:__imp_LeaveCriticalSection
0x18004a1ec  test    ebx, ebx
0x18004a1ee  js      short loc_18004A1F2
0x18004a1f0  xor     ebx, ebx
0x18004a1f2  lea     rcx, [rsp+78h+arg_18]
0x18004a1fa  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18004a1ff  mov     eax, ebx
0x18004a201  add     rsp, 50h
0x18004a205  pop     r15
0x18004a207  pop     r14
0x18004a209  pop     rdi
0x18004a20a  pop     rsi
0x18004a20b  pop     rbx
0x18004a20c  retn
```
