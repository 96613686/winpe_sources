# OnLaunchRelevantTaskThread(void *)

- ea: `0x18000dc90`
- end: `0x18000dd6e`
- name: `?OnLaunchRelevantTaskThread@@YAKPEAX@Z`
- size: `222`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000dc90`
- `0x180014274`
- `0x18001ee80`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd2a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000dcc5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000dcc5`

## pseudocode

```c
__int64 __fastcall OnLaunchRelevantTaskThread(PVOID Parameter)
{
  HRESULT Instance; // ebx
  struct IUnknown *v4; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  Instance = CoCreateInstance(&CLSID_CXWizard, 0, 0x401u, &GUID_777ba87a_2498_4875_933a_3067de883070, (LPVOID *)&v4);
  if ( Instance >= 0 )
  {
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, void *, PVOID, _DWORD, _DWORD, _QWORD, _QWORD, _DWORD))v4->lpVtbl[7].AddRef)(
                 v4,
                 0,
                 &unk_180028390,
                 Parameter,
                 0,
                 0,
                 0,
                 0,
                 0);
    ReleaseObj(v4);
  }
  CoTaskMemFree(Parameter);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      110,
      &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids,
      (unsigned int)Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000dc90  mov     r11, rsp
0x18000dc93  mov     [r11+10h], rbx
0x18000dc97  push    rdi
0x18000dc98  sub     rsp, 50h
0x18000dc9c  mov     rdi, rcx
0x18000dc9f  mov     qword ptr [r11+8], 0
0x18000dca7  lea     rax, [r11+8]
0x18000dcab  xor     edx, edx; pUnkOuter
0x18000dcad  lea     rcx, CLSID_CXWizard; rclsid
0x18000dcb4  mov     [r11-38h], rax
0x18000dcb8  lea     r9, _GUID_777ba87a_2498_4875_933a_3067de883070; riid
0x18000dcbf  mov     r8d, 401h; dwClsContext
0x18000dcc5  call    cs:__imp_CoCreateInstance
0x18000dccb  mov     ebx, eax
0x18000dccd  test    eax, eax
0x18000dccf  js      short loc_18000DD27
0x18000dcd1  mov     rcx, [rsp+58h+arg_0]
0x18000dcd6  lea     r8, unk_180028390
0x18000dcdd  mov     [rsp+58h+var_18], 0
0x18000dce5  mov     r9, rdi
0x18000dce8  mov     [rsp+58h+var_20], 0
0x18000dcf1  xor     edx, edx
0x18000dcf3  mov     [rsp+58h+var_28], 0
0x18000dcfc  mov     rax, [rcx]
0x18000dcff  mov     [rsp+58h+var_30], 0
0x18000dd07  mov     [rsp+58h+var_38], 0
0x18000dd0f  mov     rax, [rax+0B0h]
0x18000dd16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd1b  mov     rcx, [rsp+58h+arg_0]; struct IUnknown *
0x18000dd20  mov     ebx, eax
0x18000dd22  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18000dd27  mov     rcx, rdi; pv
0x18000dd2a  call    cs:__imp_CoTaskMemFree
0x18000dd30  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd37  lea     rax, WPP_GLOBAL_Control
0x18000dd3e  cmp     rcx, rax
0x18000dd41  jz      short loc_18000DD61
0x18000dd43  test    byte ptr [rcx+1Ch], 8
0x18000dd47  jz      short loc_18000DD61
0x18000dd49  mov     rcx, [rcx+10h]
0x18000dd4d  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000dd54  mov     edx, 6Eh ; 'n'
0x18000dd59  mov     r9d, ebx
0x18000dd5c  call    WPP_SF_d
0x18000dd61  mov     eax, ebx
0x18000dd63  mov     rbx, [rsp+58h+arg_8]
0x18000dd68  add     rsp, 50h
0x18000dd6c  pop     rdi
0x18000dd6d  retn
```
