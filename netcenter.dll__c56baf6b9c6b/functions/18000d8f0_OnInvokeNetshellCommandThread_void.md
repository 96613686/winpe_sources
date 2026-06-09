# OnInvokeNetshellCommandThread(void *)

- ea: `0x18000d8f0`
- end: `0x18000dadb`
- name: `?OnInvokeNetshellCommandThread@@YAKPEAX@Z`
- size: `491`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002270`
- `0x18000d8f0`
- `0x180012580`
- `0x1800126b0`
- `0x180014274`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da81`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d93f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d93f`

## pseudocode

```c
__int64 __fastcall OnInvokeNetshellCommandThread(PVOID Parameter)
{
  HRESULT v2; // ebx
  unsigned int v3; // r8d
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v6; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v8; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v9[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v10; // [rsp+90h] [rbp-70h]
  int v11; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v12[46]; // [rsp+A4h] [rbp-5Ch] BYREF

  ppv = 0;
  v2 = CoCreateInstance(&CLSID_NetworkConnections, 0, 1u, &GUID_000214e6_0000_0000_c000_000000000046, &ppv);
  if ( v2 < 0 )
    goto LABEL_7;
  pv = 0;
  v11 = 3801146;
  StringFromGUID2((struct _GUID *)Parameter, v12, v3);
  v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, int *, _QWORD, LPVOID *, _QWORD))(*(_QWORD *)ppv + 24LL))(
         ppv,
         0,
         0,
         &v11,
         0,
         &pv,
         0);
  if ( v2 >= 0 )
  {
    v8 = pv;
    v6 = 0;
    v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, LPVOID *, GUID *, _QWORD, __int64 *))(*(_QWORD *)ppv + 80LL))(
           ppv,
           0,
           1,
           &v8,
           &IID_IContextMenu,
           0,
           &v6);
    if ( v2 >= 0 )
    {
      v10 = 0;
      v9[1] = (unsigned __int64)(*((_DWORD *)Parameter + 4) != 0) + 3;
      v9[0] = 0;
      v9[2] = 0;
      v2 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v6 + 32LL))(v6, v9);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    CoTaskMemFree(pv);
  }
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v2 < 0 )
LABEL_7:
    ThrowErrorBox(*((HWND *)Parameter + 3), v2);
  CoTaskMemFree(Parameter);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      109,
      &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids,
      (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000d8f0  mov     [rsp-8+arg_8], rbx
0x18000d8f5  mov     [rsp-8+arg_10], rdi
0x18000d8fa  push    rbp
0x18000d8fb  lea     rbp, [rsp-10h]
0x18000d900  sub     rsp, 110h
0x18000d907  mov     rax, cs:__security_cookie
0x18000d90e  xor     rax, rsp
0x18000d911  mov     [rbp+10h+var_10], rax
0x18000d915  xor     edx, edx; pUnkOuter
0x18000d917  mov     [rsp+110h+var_D0], 0
0x18000d920  mov     rdi, rcx
0x18000d923  lea     rax, [rsp+110h+var_D0]
0x18000d928  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18000d92f  mov     [rsp+110h+ppv], rax; ppv
0x18000d934  lea     rcx, CLSID_NetworkConnections; rclsid
0x18000d93b  lea     r8d, [rdx+1]; dwClsContext
0x18000d93f  call    cs:__imp_CoCreateInstance
0x18000d945  mov     ebx, eax
0x18000d947  test    eax, eax
0x18000d949  js      loc_18000DA73
0x18000d94f  lea     rdx, [rbp+10h+var_6C]; unsigned __int16 *
0x18000d953  mov     [rsp+110h+pv], 0
0x18000d95c  mov     rcx, rdi; struct _GUID *
0x18000d95f  mov     [rbp+10h+var_70], 3A003Ah
0x18000d966  call    ?StringFromGUID2@@YAXAEAU_GUID@@PEAGK@Z; StringFromGUID2(_GUID &,ushort *,ulong)
0x18000d96b  mov     rcx, [rsp+110h+var_D0]
0x18000d970  lea     rdx, [rsp+110h+pv]
0x18000d975  mov     [rsp+110h+var_E0], 0
0x18000d97e  lea     r9, [rbp+10h+var_70]
0x18000d982  mov     [rsp+110h+var_E8], rdx
0x18000d987  xor     r8d, r8d
0x18000d98a  xor     edx, edx
0x18000d98c  mov     [rsp+110h+ppv], 0
0x18000d995  mov     rax, [rcx]
0x18000d998  mov     rax, [rax+18h]
0x18000d99c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9a1  mov     ebx, eax
0x18000d9a3  test    eax, eax
0x18000d9a5  js      loc_18000DA5E
0x18000d9ab  mov     rax, [rsp+110h+pv]
0x18000d9b0  lea     rdx, [rsp+110h+var_C8]
0x18000d9b5  mov     rcx, [rsp+110h+var_D0]
0x18000d9ba  lea     r9, [rsp+110h+var_B8]
0x18000d9bf  mov     [rsp+110h+var_E0], rdx
0x18000d9c4  lea     rdx, IID_IContextMenu
0x18000d9cb  mov     [rsp+110h+var_B8], rax
0x18000d9d0  mov     [rsp+110h+var_C8], 0
0x18000d9d9  mov     rax, [rcx]
0x18000d9dc  mov     [rsp+110h+var_E8], 0
0x18000d9e5  mov     [rsp+110h+ppv], rdx
0x18000d9ea  xor     edx, edx
0x18000d9ec  mov     rax, [rax+50h]
0x18000d9f0  lea     r8d, [rdx+1]
0x18000d9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9f9  mov     ebx, eax
0x18000d9fb  test    eax, eax
0x18000d9fd  js      short loc_18000DA53
0x18000d9ff  xor     eax, eax
0x18000da01  lea     rdx, [rsp+110h+var_B0]
0x18000da06  mov     [rbp+10h+var_80], rax
0x18000da0a  xorps   xmm0, xmm0
0x18000da0d  mov     eax, [rdi+10h]
0x18000da10  neg     eax
0x18000da12  movups  [rsp+110h+var_A0], xmm0
0x18000da17  sbb     rcx, rcx
0x18000da1a  neg     rcx
0x18000da1d  add     rcx, 3
0x18000da21  mov     qword ptr [rsp+110h+var_A0], rcx
0x18000da26  mov     rcx, [rsp+110h+var_C8]
0x18000da2b  movups  [rsp+110h+var_B0], xmm0
0x18000da30  movups  [rbp+10h+var_90], xmm0
0x18000da34  mov     rax, [rcx]
0x18000da37  mov     rax, [rax+20h]
0x18000da3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da40  mov     rcx, [rsp+110h+var_C8]
0x18000da45  mov     ebx, eax
0x18000da47  mov     rax, [rcx]
0x18000da4a  mov     rax, [rax+10h]
0x18000da4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da53  mov     rcx, [rsp+110h+pv]; pv
0x18000da58  call    cs:__imp_CoTaskMemFree
0x18000da5e  mov     rcx, [rsp+110h+var_D0]
0x18000da63  mov     rax, [rcx]
0x18000da66  mov     rax, [rax+10h]
0x18000da6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da6f  test    ebx, ebx
0x18000da71  jns     short loc_18000DA7E
0x18000da73  mov     rcx, [rdi+18h]; hWnd
0x18000da77  mov     edx, ebx; dwMessageId
0x18000da79  call    ?ThrowErrorBox@@YAXQEAUHWND__@@J@Z; ThrowErrorBox(HWND__ * const,long)
0x18000da7e  mov     rcx, rdi; pv
0x18000da81  call    cs:__imp_CoTaskMemFree
0x18000da87  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da8e  lea     rax, WPP_GLOBAL_Control
0x18000da95  cmp     rcx, rax
0x18000da98  jz      short loc_18000DAB8
0x18000da9a  test    byte ptr [rcx+1Ch], 8
0x18000da9e  jz      short loc_18000DAB8
0x18000daa0  mov     rcx, [rcx+10h]
0x18000daa4  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000daab  mov     edx, 6Dh ; 'm'
0x18000dab0  mov     r9d, ebx
0x18000dab3  call    WPP_SF_d
0x18000dab8  mov     eax, ebx
0x18000daba  mov     rcx, [rbp+10h+var_10]
0x18000dabe  xor     rcx, rsp; StackCookie
0x18000dac1  call    __security_check_cookie
0x18000dac6  lea     r11, [rsp+110h+var_s0]
0x18000dace  mov     rbx, [r11+18h]
0x18000dad2  mov     rdi, [r11+20h]
0x18000dad6  mov     rsp, r11
0x18000dad9  pop     rbp
0x18000dada  retn
```
