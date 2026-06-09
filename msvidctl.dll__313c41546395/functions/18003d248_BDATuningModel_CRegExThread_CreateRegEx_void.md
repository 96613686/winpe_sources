# BDATuningModel::CRegExThread::CreateRegEx(void)

- ea: `0x18003d248`
- end: `0x18003d378`
- name: `?CreateRegEx@CRegExThread@BDATuningModel@@AEAAJXZ`
- size: `304`
- prototype: `__int64 __fastcall(BDATuningModel::CRegExThread *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180045780`

## callees

- `0x180006b38`
- `0x18003d248`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18003d295`
- `ole32!CoCreateInstance` at `0x18003d2d8`
- `ole32!CoCreateInstance` at `0x18003d295`
- `ole32!CoCreateInstance` at `0x18003d2d8`
- `KERNEL32!LeaveCriticalSection` at `0x18003d2a4`
- `KERNEL32!LeaveCriticalSection` at `0x18003d362`
- `KERNEL32!LeaveCriticalSection` at `0x18003d2a4`
- `KERNEL32!LeaveCriticalSection` at `0x18003d362`
- `KERNEL32!EnterCriticalSection` at `0x18003d264`
- `KERNEL32!EnterCriticalSection` at `0x18003d264`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BDATuningModel::CRegExThread::CreateRegEx(BDATuningModel::CRegExThread *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  HRESULT Instance; // esi
  int v5; // edi
  LPVOID ppv; // [rsp+50h] [rbp+8h] BYREF
  char *v7; // [rsp+58h] [rbp+10h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  v7 = (char *)this + 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( *((_QWORD *)this + 16) )
    goto LABEL_11;
  Instance = CoCreateInstance(
               &CLSID_StdGlobalInterfaceTable,
               0,
               1u,
               &GUID_00000146_0000_0000_c000_000000000046,
               (LPVOID *)this + 16);
  if ( Instance < 0 )
  {
LABEL_3:
    LeaveCriticalSection(v2);
    return (unsigned int)Instance;
  }
  ppv = 0;
  Instance = CoCreateInstance(
               &GUID_3f4daca4_160d_11d2_a8e9_00104b365c9f,
               0,
               3u,
               &GUID_3f4daca0_160d_11d2_a8e9_00104b365c9f,
               &ppv);
  if ( Instance < 0
    || (Instance = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 80LL))(ppv, 0xFFFFFFFFLL), Instance < 0)
    || (Instance = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 96LL))(ppv, 0xFFFFFFFFLL), Instance < 0) )
  {
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
    goto LABEL_3;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, LPVOID, GUID *, char *))(**((_QWORD **)this + 16) + 24LL))(
         *((_QWORD *)this + 16),
         ppv,
         &GUID_3f4daca0_160d_11d2_a8e9_00104b365c9f,
         (char *)this + 136);
  if ( v5 >= 0 )
  {
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
LABEL_11:
    v5 = 0;
    goto LABEL_12;
  }
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
LABEL_12:
  LeaveCriticalSection(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003d248  mov     [rsp+arg_10], rbx
0x18003d24d  push    rsi
0x18003d24e  push    rdi
0x18003d24f  push    r14
0x18003d251  sub     rsp, 30h
0x18003d255  mov     rdi, rcx
0x18003d258  lea     rbx, [rcx+58h]
0x18003d25c  mov     [rsp+48h+arg_8], rbx
0x18003d261  mov     rcx, rbx; lpCriticalSection
0x18003d264  call    cs:__imp_EnterCriticalSection
0x18003d26a  nop
0x18003d26b  lea     r14, [rdi+80h]
0x18003d272  cmp     qword ptr [r14], 0
0x18003d276  jnz     loc_18003D35D
0x18003d27c  mov     [rsp+48h+ppv], r14; ppv
0x18003d281  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18003d288  xor     edx, edx; pUnkOuter
0x18003d28a  lea     r8d, [rdx+1]; dwClsContext
0x18003d28e  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18003d295  call    cs:__imp_CoCreateInstance
0x18003d29b  mov     esi, eax
0x18003d29d  test    eax, eax
0x18003d29f  jns     short loc_18003D2B1
0x18003d2a1  mov     rcx, rbx; lpCriticalSection
0x18003d2a4  call    cs:__imp_LeaveCriticalSection
0x18003d2aa  mov     eax, esi
0x18003d2ac  jmp     loc_18003D36A
0x18003d2b1  mov     [rsp+48h+arg_0], 0
0x18003d2ba  lea     rax, [rsp+48h+arg_0]
0x18003d2bf  mov     [rsp+48h+ppv], rax; ppv
0x18003d2c4  lea     r9, _GUID_3f4daca0_160d_11d2_a8e9_00104b365c9f; riid
0x18003d2cb  xor     edx, edx; pUnkOuter
0x18003d2cd  lea     r8d, [rdx+3]; dwClsContext
0x18003d2d1  lea     rcx, _GUID_3f4daca4_160d_11d2_a8e9_00104b365c9f; rclsid
0x18003d2d8  call    cs:__imp_CoCreateInstance
0x18003d2de  mov     esi, eax
0x18003d2e0  test    eax, eax
0x18003d2e2  jns     short loc_18003D2F0
0x18003d2e4  lea     rcx, [rsp+48h+arg_0]
0x18003d2e9  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18003d2ee  jmp     short loc_18003D2A1
0x18003d2f0  mov     rcx, [rsp+48h+arg_0]
0x18003d2f5  mov     rax, [rcx]
0x18003d2f8  or      edx, 0FFFFFFFFh
0x18003d2fb  mov     rax, [rax+50h]
0x18003d2ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d304  mov     esi, eax
0x18003d306  test    eax, eax
0x18003d308  js      short loc_18003D2E4
0x18003d30a  mov     rcx, [rsp+48h+arg_0]
0x18003d30f  mov     rax, [rcx]
0x18003d312  or      edx, 0FFFFFFFFh
0x18003d315  mov     rax, [rax+60h]
0x18003d319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d31e  mov     esi, eax
0x18003d320  test    eax, eax
0x18003d322  js      short loc_18003D2E4
0x18003d324  mov     rcx, [r14]
0x18003d327  mov     rax, [rcx]
0x18003d32a  lea     r9, [rdi+88h]
0x18003d331  lea     r8, _GUID_3f4daca0_160d_11d2_a8e9_00104b365c9f
0x18003d338  mov     rdx, [rsp+48h+arg_0]
0x18003d33d  mov     rax, [rax+18h]
0x18003d341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d346  mov     edi, eax
0x18003d348  lea     rcx, [rsp+48h+arg_0]
0x18003d34d  test    eax, eax
0x18003d34f  jns     short loc_18003D358
0x18003d351  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18003d356  jmp     short loc_18003D35F
0x18003d358  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18003d35d  xor     edi, edi
0x18003d35f  mov     rcx, rbx; lpCriticalSection
0x18003d362  call    cs:__imp_LeaveCriticalSection
0x18003d368  mov     eax, edi
0x18003d36a  mov     rbx, [rsp+48h+arg_10]
0x18003d36f  add     rsp, 30h
0x18003d373  pop     r14
0x18003d375  pop     rdi
0x18003d376  pop     rsi
0x18003d377  retn
```
