# CNetConnectionLuaImpl::LuaCreateInner(HWND__ *,tagNET_LUA_ELEVATION_LEVEL,INetConnection * *)

- ea: `0x18005fa20`
- end: `0x18005fbda`
- name: `?LuaCreateInner@CNetConnectionLuaImpl@@UEAAJPEAUHWND__@@W4tagNET_LUA_ELEVATION_LEVEL@@PEAPEAUINetConnection@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18001644c`
- `0x18005fa20`
- `0x180065010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18005fa66`
- `ole32!CoTaskMemFree` at `0x18005fa66`
- `ole32!StringFromCLSID` at `0x18005fa58`
- `ole32!StringFromCLSID` at `0x18005fa58`

## pseudocode

```c
__int64 __fastcall CNetConnectionLuaImpl::LuaCreateInner(__int64 a1, __int64 a2, unsigned int a3, _QWORD *a4)
{
  _QWORD *v8; // rdi
  __int64 v9; // rax
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  int v11; // ebx
  __int64 (__fastcall ***v12)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-20h] BYREF
  __int64 v15; // [rsp+28h] [rbp-18h] BYREF
  LPOLESTR lpsz; // [rsp+30h] [rbp-10h] BYREF
  __int64 v17; // [rsp+70h] [rbp+30h] BYREF

  lpsz = 0;
  v8 = (_QWORD *)(a1 + 120);
  if ( StringFromCLSID((const IID *const)(a1 + 120), &lpsz) >= 0 )
    CoTaskMemFree(lpsz);
  v9 = *v8 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *v8 == *(_QWORD *)&GUID_NULL.Data1 )
    v9 = v8[1] - *(_QWORD *)GUID_NULL.Data4;
  if ( !v9 )
    return 2147549183LL;
  v10 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(a1 + 152);
  if ( !v10 )
    return 2147549183LL;
  v14 = 0;
  v17 = 0;
  v11 = (**v10)(v10, &IID_INetLua, &v17);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v17 + 40LL))(v17, a2, a3);
    if ( v11 >= 0 )
    {
      v15 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v17 + 56LL))(
              v17,
              &IID_INetConnectionManager3,
              &v15);
      if ( v11 >= 0 )
        v11 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v15 + 24LL))(v15, v8, &v14);
      ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(&v15);
      if ( v11 >= 0 )
      {
        v15 = 0;
        v11 = (**v14)(v14, &IID_IPersistNetConnection, &v15);
        if ( v11 >= 0 )
          v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v15 + 40LL))(
                  v15,
                  *(_QWORD *)(a1 + 144),
                  *(unsigned int *)(a1 + 136));
        ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(&v15);
        if ( v11 >= 0 )
        {
          v12 = v14;
          *a4 = v14;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v12)[1])(v12);
        }
      }
    }
  }
  ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(&v17);
  ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(&v14);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18005fa20  mov     [rsp-28h+arg_8], rbx
0x18005fa25  mov     [rsp-28h+arg_10], rsi
0x18005fa2a  push    rbp
0x18005fa2b  push    rdi
0x18005fa2c  push    r12
0x18005fa2e  push    r14
0x18005fa30  push    r15
0x18005fa32  mov     rbp, rsp
0x18005fa35  sub     rsp, 40h
0x18005fa39  mov     r12, r9
0x18005fa3c  mov     r14d, r8d
0x18005fa3f  mov     r15, rdx
0x18005fa42  mov     rsi, rcx
0x18005fa45  mov     [rbp+lpsz], 0
0x18005fa4d  lea     rdi, [rcx+78h]
0x18005fa51  lea     rdx, [rbp+lpsz]; lplpsz
0x18005fa55  mov     rcx, rdi; rclsid
0x18005fa58  call    cs:__imp_StringFromCLSID
0x18005fa5e  test    eax, eax
0x18005fa60  js      short loc_18005FA6C
0x18005fa62  mov     rcx, [rbp+lpsz]; pv
0x18005fa66  call    cs:__imp_CoTaskMemFree
0x18005fa6c  mov     rax, [rdi]
0x18005fa6f  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18005fa76  jnz     short loc_18005FA83
0x18005fa78  mov     rax, [rdi+8]
0x18005fa7c  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18005fa83  test    rax, rax
0x18005fa86  jz      loc_18005FBBC
0x18005fa8c  mov     rcx, [rsi+98h]
0x18005fa93  test    rcx, rcx
0x18005fa96  jz      loc_18005FBBC
0x18005fa9c  mov     [rbp+var_20], 0
0x18005faa4  mov     [rbp+arg_0], 0
0x18005faac  mov     rax, [rcx]
0x18005faaf  lea     r8, [rbp+arg_0]
0x18005fab3  lea     rdx, IID_INetLua
0x18005faba  mov     rax, [rax]
0x18005fabd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fac2  mov     ebx, eax
0x18005fac4  test    eax, eax
0x18005fac6  js      loc_18005FBA5
0x18005facc  mov     rcx, [rbp+arg_0]
0x18005fad0  mov     rax, [rcx]
0x18005fad3  mov     r8d, r14d
0x18005fad6  mov     rdx, r15
0x18005fad9  mov     rax, [rax+28h]
0x18005fadd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fae2  mov     ebx, eax
0x18005fae4  test    eax, eax
0x18005fae6  js      loc_18005FBA5
0x18005faec  mov     [rbp+var_18], 0
0x18005faf4  mov     rcx, [rbp+arg_0]
0x18005faf8  mov     rax, [rcx]
0x18005fafb  lea     r8, [rbp+var_18]
0x18005faff  lea     rdx, IID_INetConnectionManager3
0x18005fb06  mov     rax, [rax+38h]
0x18005fb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb0f  mov     ebx, eax
0x18005fb11  test    eax, eax
0x18005fb13  js      short loc_18005FB2E
0x18005fb15  mov     rcx, [rbp+var_18]
0x18005fb19  mov     rax, [rcx]
0x18005fb1c  lea     r8, [rbp+var_20]
0x18005fb20  mov     rdx, rdi
0x18005fb23  mov     rax, [rax+18h]
0x18005fb27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb2c  mov     ebx, eax
0x18005fb2e  lea     rcx, [rbp+var_18]
0x18005fb32  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x18005fb37  test    ebx, ebx
0x18005fb39  js      short loc_18005FBA5
0x18005fb3b  mov     [rbp+var_18], 0
0x18005fb43  mov     rcx, [rbp+var_20]
0x18005fb47  mov     rax, [rcx]
0x18005fb4a  lea     r8, [rbp+var_18]
0x18005fb4e  lea     rdx, IID_IPersistNetConnection
0x18005fb55  mov     rax, [rax]
0x18005fb58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb5d  mov     ebx, eax
0x18005fb5f  test    eax, eax
0x18005fb61  js      short loc_18005FB83
0x18005fb63  mov     rcx, [rbp+var_18]
0x18005fb67  mov     rax, [rcx]
0x18005fb6a  mov     r8d, [rsi+88h]
0x18005fb71  mov     rdx, [rsi+90h]
0x18005fb78  mov     rax, [rax+28h]
0x18005fb7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb81  mov     ebx, eax
0x18005fb83  lea     rcx, [rbp+var_18]
0x18005fb87  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x18005fb8c  test    ebx, ebx
0x18005fb8e  js      short loc_18005FBA5
0x18005fb90  mov     rcx, [rbp+var_20]
0x18005fb94  mov     [r12], rcx
0x18005fb98  mov     rax, [rcx]
0x18005fb9b  mov     rax, [rax+8]
0x18005fb9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fba4  nop
0x18005fba5  lea     rcx, [rbp+arg_0]
0x18005fba9  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x18005fbae  nop
0x18005fbaf  lea     rcx, [rbp+var_20]
0x18005fbb3  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x18005fbb8  mov     eax, ebx
0x18005fbba  jmp     short loc_18005FBC1
0x18005fbbc  mov     eax, 8000FFFFh
0x18005fbc1  lea     r11, [rsp+40h+var_s0]
0x18005fbc6  mov     rbx, [r11+38h]
0x18005fbca  mov     rsi, [r11+40h]
0x18005fbce  mov     rsp, r11
0x18005fbd1  pop     r15
0x18005fbd3  pop     r14
0x18005fbd5  pop     r12
0x18005fbd7  pop     rdi
0x18005fbd8  pop     rbp
0x18005fbd9  retn
```
