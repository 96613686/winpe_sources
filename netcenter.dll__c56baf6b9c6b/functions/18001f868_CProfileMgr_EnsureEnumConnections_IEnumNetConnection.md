# CProfileMgr::EnsureEnumConnections(IEnumNetConnection * *)

- ea: `0x18001f868`
- end: `0x18001fa0f`
- name: `?EnsureEnumConnections@CProfileMgr@@IEAAJPEAPEAUIEnumNetConnection@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(CProfileMgr *__hidden this, struct IEnumNetConnection **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001fde8`

## callees

- `0x180006b70`
- `0x180007e50`
- `0x180014274`
- `0x18001ecd0`
- `0x18001ecf8`
- `0x18001f868`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001f99f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001f99f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProfileMgr::EnsureEnumConnections(CProfileMgr *this, struct IEnumNetConnection **a2)
{
  __int64 v5; // rcx
  HRESULT Instance; // ebx
  PVOID *v7; // rcx
  struct IUnknown *ppv; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500035LL;
  if ( (unsigned int)IsServiceStopPending((const unsigned __int16 *)this) )
    (*(void (__fastcall **)(CProfileMgr *))(*(_QWORD *)this + 240LL))(this);
  v5 = *((_QWORD *)this + 5);
  if ( !v5 )
  {
    ppv = 0;
    Instance = CoCreateInstance(
                 &CLSID_ConnectionManager,
                 0,
                 0x404u,
                 &GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e,
                 (LPVOID *)&ppv);
    *((_DWORD *)this + 6) = Instance;
    if ( Instance >= 0 )
    {
      NcCoSetProxyBlanket(ppv);
      Instance = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct IEnumNetConnection **))ppv->lpVtbl[1].QueryInterface)(
                   ppv,
                   0,
                   a2);
    }
    ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(&ppv);
    goto LABEL_18;
  }
  Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IEnumNetConnection **))(*(_QWORD *)v5 + 24LL))(
               v5,
               0,
               a2);
  if ( ((Instance + 2147023174) & 0xFFFFFFFB) != 0 )
  {
LABEL_18:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_edb4701937c33b484ee7d731345f6be9_Traceguids);
  (*(void (__fastcall **)(CProfileMgr *))(*(_QWORD *)this + 240LL))(this);
  Instance = (*(__int64 (__fastcall **)(CProfileMgr *))(*(_QWORD *)this + 256LL))(this);
  if ( Instance >= 0 )
    Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IEnumNetConnection **))(**((_QWORD **)this + 5) + 24LL))(
                 *((_QWORD *)this + 5),
                 0,
                 a2);
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)Instance;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      &WPP_edb4701937c33b484ee7d731345f6be9_Traceguids,
      (unsigned int)Instance);
    goto LABEL_18;
  }
LABEL_19:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
    WPP_SF_d(v7[2], 42, &WPP_edb4701937c33b484ee7d731345f6be9_Traceguids, (unsigned int)Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001f868  push    rbx
0x18001f86a  push    rbp
0x18001f86b  push    rsi
0x18001f86c  push    rdi
0x18001f86d  sub     rsp, 38h
0x18001f871  mov     rsi, rdx
0x18001f874  mov     rdi, rcx
0x18001f877  test    rdx, rdx
0x18001f87a  jnz     short loc_18001F886
0x18001f87c  mov     eax, 80004003h
0x18001f881  jmp     loc_18001FA06
0x18001f886  call    ?IsServiceStopPending@@YAHPEBG@Z; IsServiceStopPending(ushort const *)
0x18001f88b  test    eax, eax
0x18001f88d  jz      short loc_18001F8A1
0x18001f88f  mov     rax, [rdi]
0x18001f892  mov     rcx, rdi
0x18001f895  mov     rax, [rax+0F0h]
0x18001f89c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8a1  mov     rcx, [rdi+28h]
0x18001f8a5  lea     rbp, WPP_GLOBAL_Control
0x18001f8ac  test    rcx, rcx
0x18001f8af  jz      loc_18001F976
0x18001f8b5  mov     rax, [rcx]
0x18001f8b8  mov     r8, rsi
0x18001f8bb  xor     edx, edx
0x18001f8bd  mov     rax, [rax+18h]
0x18001f8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8c6  mov     ebx, eax
0x18001f8c8  lea     ecx, [rax+7FF8F946h]
0x18001f8ce  test    ecx, 0FFFFFFFBh
0x18001f8d4  jnz     loc_18001F9DA
0x18001f8da  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8e1  cmp     rcx, rbp
0x18001f8e4  jz      short loc_18001F901
0x18001f8e6  test    byte ptr [rcx+1Ch], 2
0x18001f8ea  jz      short loc_18001F901
0x18001f8ec  mov     edx, 28h ; '('
0x18001f8f1  lea     r8, WPP_edb4701937c33b484ee7d731345f6be9_Traceguids
0x18001f8f8  mov     rcx, [rcx+10h]
0x18001f8fc  call    WPP_SF_
0x18001f901  mov     rax, [rdi]
0x18001f904  mov     rcx, rdi
0x18001f907  mov     rax, [rax+0F0h]
0x18001f90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f913  mov     rax, [rdi]
0x18001f916  mov     rcx, rdi
0x18001f919  mov     rax, [rax+100h]
0x18001f920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f925  mov     ebx, eax
0x18001f927  test    eax, eax
0x18001f929  js      short loc_18001F942
0x18001f92b  mov     rcx, [rdi+28h]
0x18001f92f  mov     rax, [rcx]
0x18001f932  mov     r8, rsi
0x18001f935  xor     edx, edx
0x18001f937  mov     rax, [rax+18h]
0x18001f93b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f940  mov     ebx, eax
0x18001f942  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f949  cmp     rcx, rbp
0x18001f94c  jz      loc_18001FA04
0x18001f952  test    byte ptr [rcx+1Ch], 2
0x18001f956  jz      loc_18001F9E1
0x18001f95c  mov     edx, 29h ; ')'
0x18001f961  mov     r9d, ebx
0x18001f964  lea     r8, WPP_edb4701937c33b484ee7d731345f6be9_Traceguids
0x18001f96b  mov     rcx, [rcx+10h]
0x18001f96f  call    WPP_SF_d
0x18001f974  jmp     short loc_18001F9DA
0x18001f976  mov     [rsp+58h+arg_8], 0
0x18001f97f  lea     rax, [rsp+58h+arg_8]
0x18001f984  mov     [rsp+58h+ppv], rax; ppv
0x18001f989  lea     r9, _GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e; riid
0x18001f990  xor     edx, edx; pUnkOuter
0x18001f992  mov     r8d, 404h; dwClsContext
0x18001f998  lea     rcx, CLSID_ConnectionManager; rclsid
0x18001f99f  call    cs:__imp_CoCreateInstance
0x18001f9a5  mov     ebx, eax
0x18001f9a7  mov     [rdi+18h], eax
0x18001f9aa  test    eax, eax
0x18001f9ac  js      short loc_18001F9D0
0x18001f9ae  mov     rcx, [rsp+58h+arg_8]; struct IUnknown *
0x18001f9b3  call    ?NcCoSetProxyBlanket@@YAXPEAUIUnknown@@@Z; NcCoSetProxyBlanket(IUnknown *)
0x18001f9b8  mov     rcx, [rsp+58h+arg_8]
0x18001f9bd  mov     rax, [rcx]
0x18001f9c0  mov     r8, rsi
0x18001f9c3  xor     edx, edx
0x18001f9c5  mov     rax, [rax+18h]
0x18001f9c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9ce  mov     ebx, eax
0x18001f9d0  lea     rcx, [rsp+58h+arg_8]
0x18001f9d5  call    ??1?$CComPtrBase@UIShellFolder2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(void)
0x18001f9da  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9e1  cmp     rcx, rbp
0x18001f9e4  jz      short loc_18001FA04
0x18001f9e6  test    byte ptr [rcx+1Ch], 8
0x18001f9ea  jz      short loc_18001FA04
0x18001f9ec  mov     edx, 2Ah ; '*'
0x18001f9f1  mov     r9d, ebx
0x18001f9f4  lea     r8, WPP_edb4701937c33b484ee7d731345f6be9_Traceguids
0x18001f9fb  mov     rcx, [rcx+10h]
0x18001f9ff  call    WPP_SF_d
0x18001fa04  mov     eax, ebx
0x18001fa06  add     rsp, 38h
0x18001fa0a  pop     rdi
0x18001fa0b  pop     rsi
0x18001fa0c  pop     rbp
0x18001fa0d  pop     rbx
0x18001fa0e  retn
```
