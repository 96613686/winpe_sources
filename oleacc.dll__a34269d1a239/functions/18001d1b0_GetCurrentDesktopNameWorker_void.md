# GetCurrentDesktopNameWorker(void *)

- ea: `0x18001d1b0`
- end: `0x18001d293`
- name: `?GetCurrentDesktopNameWorker@@YAKPEAX@Z`
- size: `227`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180019ad8`
- `0x18001aa30`
- `0x18001c50c`
- `0x18001d1b0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d25c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d25c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d1f6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d1f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetCurrentDesktopNameWorker(PVOID Parameter)
{
  HRESULT v1; // edi
  __int64 v2; // rbx
  unsigned int v3; // ebx
  LPVOID ppv; // [rsp+58h] [rbp+28h] BYREF
  __int64 v6; // [rsp+60h] [rbp+30h] BYREF
  __int64 v7; // [rsp+68h] [rbp+38h] BYREF

  v7 = 0;
  ATL::CComPtrBase__anonymous_namespace_::DesktopNameWorkerThreadResult_::Attach(&v7, Parameter);
  ppv = 0;
  v1 = CoCreateInstance(
         &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
         0,
         0x404u,
         &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
         &ppv);
  v2 = v7;
  if ( v1 >= 0 )
  {
    v6 = 0;
    v1 = (*(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
           ppv,
           &IID_IVirtualDesktopAccessibility,
           &GUID_9975b71d_0a84_4909_bdde_b455bbfa55c6,
           &v6);
    if ( v1 >= 0 )
      v1 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 24LL))(v6, v2 + 16);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
  }
  *(_DWORD *)(v2 + 32) = v1;
  if ( SetEvent(*(HANDLE *)(v2 + 24)) )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    v3 = 0;
  }
  else
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    v3 = 1;
  }
  ATL::CComPtrBase__anonymous_namespace_::DesktopNameWorkerThreadResult_::_CComPtrBase__anonymous_namespace_::DesktopNameWorkerThreadResult_(&v7);
  return v3;
}

```

## disassembly

```asm
0x18001d1b0  push    rbp
0x18001d1b2  push    rbx
0x18001d1b3  push    rdi
0x18001d1b4  mov     rbp, rsp
0x18001d1b7  sub     rsp, 30h
0x18001d1bb  mov     [rbp+arg_18], 0
0x18001d1c3  mov     rdx, rcx
0x18001d1c6  lea     rcx, [rbp+arg_18]
0x18001d1ca  call    ATL__CComPtrBase__anonymous_namespace___DesktopNameWorkerThreadResult___Attach
0x18001d1cf  mov     [rbp+arg_8], 0
0x18001d1d7  lea     rax, [rbp+arg_8]
0x18001d1db  mov     [rsp+30h+ppv], rax; ppv
0x18001d1e0  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18001d1e7  xor     edx, edx; pUnkOuter
0x18001d1e9  mov     r8d, 404h; dwClsContext
0x18001d1ef  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x18001d1f6  call    cs:__imp_CoCreateInstance
0x18001d1fc  mov     edi, eax
0x18001d1fe  mov     rbx, [rbp+arg_18]
0x18001d202  test    eax, eax
0x18001d204  js      short loc_18001D255
0x18001d206  mov     [rbp+arg_10], 0
0x18001d20e  mov     rcx, [rbp+arg_8]
0x18001d212  mov     rax, [rcx]
0x18001d215  lea     r9, [rbp+arg_10]
0x18001d219  lea     r8, _GUID_9975b71d_0a84_4909_bdde_b455bbfa55c6
0x18001d220  lea     rdx, IID_IVirtualDesktopAccessibility
0x18001d227  mov     rax, [rax+18h]
0x18001d22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d230  mov     edi, eax
0x18001d232  test    eax, eax
0x18001d234  js      short loc_18001D24C
0x18001d236  mov     rcx, [rbp+arg_10]
0x18001d23a  mov     rax, [rcx]
0x18001d23d  lea     rdx, [rbx+10h]
0x18001d241  mov     rax, [rax+18h]
0x18001d245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d24a  mov     edi, eax
0x18001d24c  lea     rcx, [rbp+arg_10]
0x18001d250  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d255  mov     [rbx+20h], edi
0x18001d258  mov     rcx, [rbx+18h]; hEvent
0x18001d25c  call    cs:__imp_SetEvent
0x18001d262  nop
0x18001d263  lea     rcx, [rbp+arg_8]
0x18001d267  test    eax, eax
0x18001d269  jz      short loc_18001D275
0x18001d26b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d270  nop
0x18001d271  xor     ebx, ebx
0x18001d273  jmp     short loc_18001D280
0x18001d275  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d27a  nop
0x18001d27b  mov     ebx, 1
0x18001d280  lea     rcx, [rbp+arg_18]
0x18001d284  call    ATL__CComPtrBase__anonymous_namespace___DesktopNameWorkerThreadResult____CComPtrBase__anonymous_namespace___DesktopNameWorkerThreadResult_
0x18001d289  mov     eax, ebx
0x18001d28b  add     rsp, 30h
0x18001d28f  pop     rdi
0x18001d290  pop     rbx
0x18001d291  pop     rbp
0x18001d292  retn
```
