# CSNOCplCore::OnLaunchDiagnoseTask(void)

- ea: `0x18000dae4`
- end: `0x18000db94`
- name: `?OnLaunchDiagnoseTask@CSNOCplCore@@AEAAJXZ`
- size: `176`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000dd74`

## callees

- `0x180007e50`
- `0x18000dae4`
- `0x180014274`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000db17`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000db17`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSNOCplCore::OnLaunchDiagnoseTask(CSNOCplCore *this)
{
  HRESULT v2; // ebx
  LPVOID v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v2 = CoCreateInstance(&CLSID_OpenControlPanel, 0, 0x17u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, &v4);
  if ( v2 >= 0 )
    v2 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v4 + 24LL))(
           v4,
           L"Microsoft.Troubleshooting",
           L"Network",
           *((_QWORD *)this + 43));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      158,
      &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids,
      (unsigned int)v2);
  ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(&v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000dae4  mov     r11, rsp
0x18000dae7  mov     [r11+8], rbx
0x18000daeb  push    rdi
0x18000daec  sub     rsp, 30h
0x18000daf0  mov     rdi, rcx
0x18000daf3  mov     qword ptr [r11+10h], 0
0x18000dafb  lea     rax, [r11+10h]
0x18000daff  mov     [r11-18h], rax
0x18000db03  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x18000db0a  xor     edx, edx; pUnkOuter
0x18000db0c  lea     r8d, [rdx+17h]; dwClsContext
0x18000db10  lea     rcx, CLSID_OpenControlPanel; rclsid
0x18000db17  call    cs:__imp_CoCreateInstance
0x18000db1d  mov     ebx, eax
0x18000db1f  test    eax, eax
0x18000db21  js      short loc_18000DB4B
0x18000db23  mov     rcx, [rsp+38h+arg_8]
0x18000db28  mov     rax, [rcx]
0x18000db2b  mov     r9, [rdi+158h]
0x18000db32  lea     r8, aNetwork; "Network"
0x18000db39  lea     rdx, aMicrosoftTroub; "Microsoft.Troubleshooting"
0x18000db40  mov     rax, [rax+18h]
0x18000db44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db49  mov     ebx, eax
0x18000db4b  lea     rax, WPP_GLOBAL_Control
0x18000db52  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db59  cmp     rcx, rax
0x18000db5c  jz      short loc_18000DB7D
0x18000db5e  test    byte ptr [rcx+1Ch], 8
0x18000db62  jz      short loc_18000DB7D
0x18000db64  mov     edx, 9Eh
0x18000db69  mov     r9d, ebx
0x18000db6c  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000db73  mov     rcx, [rcx+10h]
0x18000db77  call    WPP_SF_d
0x18000db7c  nop
0x18000db7d  lea     rcx, [rsp+38h+arg_8]
0x18000db82  call    ??1?$CComPtrBase@UIShellFolder2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(void)
0x18000db87  mov     eax, ebx
0x18000db89  mov     rbx, [rsp+38h+arg_0]
0x18000db8e  add     rsp, 30h
0x18000db92  pop     rdi
0x18000db93  retn
```
