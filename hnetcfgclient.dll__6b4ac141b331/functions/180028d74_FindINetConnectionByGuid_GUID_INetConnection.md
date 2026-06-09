# FindINetConnectionByGuid(_GUID *,INetConnection * *)

- ea: `0x180028d74`
- end: `0x180028f80`
- name: `?FindINetConnectionByGuid@@YAJPEAU_GUID@@PEAPEAUINetConnection@@@Z`
- size: `524`
- prototype: `__int64 __fastcall(struct _GUID *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014760`
- `0x18001c070`

## callees

- `0x180028d74`
- `0x18002a6a0`
- `0x18002aef4`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028de6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028de6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FindINetConnectionByGuid(struct _GUID *a1, struct IUnknown **a2)
{
  unsigned int Instance; // ebx
  int v5; // edi
  struct IUnknown *v6; // rcx
  int v8; // [rsp+30h] [rbp-50h] BYREF
  struct IUnknown *v9; // [rsp+38h] [rbp-48h] BYREF
  struct IUnknown *ppv; // [rsp+40h] [rbp-40h] BYREF
  struct IUnknown *v11; // [rsp+48h] [rbp-38h] BYREF
  __int64 v12; // [rsp+50h] [rbp-30h] BYREF
  NETCON_PROPERTIES *pProps; // [rsp+58h] [rbp-28h] BYREF
  GUID guidId; // [rsp+60h] [rbp-20h] BYREF

  ppv = 0;
  v11 = 0;
  v9 = 0;
  v12 = 0;
  guidId = 0;
  Instance = CoCreateInstance(
               &CLSID_ConnectionManager,
               0,
               0x8005u,
               &GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e,
               (LPVOID *)&ppv);
  if ( !Instance )
  {
    SetProxyBlanket(ppv);
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct IUnknown **))ppv->lpVtbl[1].QueryInterface)(
                 ppv,
                 0,
                 &v11);
    ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
    if ( !Instance )
    {
      v8 = 0;
      SetProxyBlanket(v11);
      while ( 1 )
      {
        if ( ((int (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **, int *))v11->lpVtbl[1].QueryInterface)(
               v11,
               1,
               &v9,
               &v8) < 0
          || v8 != 1 )
        {
LABEL_16:
          ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
          return (_BYTE)Instance == 0 ? 0x80004005 : 0;
        }
        SetProxyBlanket(v9);
        if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v9->lpVtbl->QueryInterface)(
               v9,
               &GUID_faedcf54_31fe_11d1_aad2_00805fc1270e,
               &v12) < 0 )
        {
          pProps = 0;
          v5 = ((__int64 (__fastcall *)(struct IUnknown *, NETCON_PROPERTIES **))v9->lpVtbl[2].AddRef)(v9, &pProps);
          if ( v5 >= 0 )
          {
            guidId = pProps->guidId;
            NcFreeNetconProperties(pProps);
LABEL_11:
            if ( *(_OWORD *)&guidId == *(_OWORD *)a1 )
            {
              v6 = v9;
              LOBYTE(Instance) = 1;
              *a2 = v9;
              ((void (__fastcall *)(struct IUnknown *))v6->lpVtbl->AddRef)(v6);
            }
          }
        }
        else
        {
          v5 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v12 + 40LL))(v12, &guidId);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          if ( v5 >= 0 )
            goto LABEL_11;
        }
        ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->Release)(v9);
        if ( (_BYTE)Instance || v5 < 0 || v8 != 1 )
          goto LABEL_16;
      }
    }
  }
  return Instance;
}

```

## disassembly

```asm
0x180028d74  mov     [rsp-18h+arg_0], rbx
0x180028d79  mov     [rsp-18h+arg_10], rsi
0x180028d7e  push    rbp
0x180028d7f  push    rdi
0x180028d80  push    r14
0x180028d82  mov     rbp, rsp
0x180028d85  sub     rsp, 80h
0x180028d8c  mov     rax, cs:__security_cookie
0x180028d93  xor     rax, rsp
0x180028d96  mov     [rbp+var_10], rax
0x180028d9a  mov     r14, rdx
0x180028d9d  mov     [rbp+var_40], 0
0x180028da5  mov     rsi, rcx
0x180028da8  mov     [rbp+var_38], 0
0x180028db0  xorps   xmm0, xmm0
0x180028db3  mov     [rbp+var_48], 0
0x180028dbb  lea     rax, [rbp+var_40]
0x180028dbf  mov     [rbp+var_30], 0
0x180028dc7  xor     edx, edx; pUnkOuter
0x180028dc9  mov     [rsp+80h+ppv], rax; ppv
0x180028dce  lea     rcx, CLSID_ConnectionManager; rclsid
0x180028dd5  mov     r8d, 8005h; dwClsContext
0x180028ddb  lea     r9, _GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e; riid
0x180028de2  movups  [rbp+var_20], xmm0
0x180028de6  call    cs:__imp_CoCreateInstance
0x180028dec  mov     ebx, eax
0x180028dee  test    eax, eax
0x180028df0  jnz     loc_180028F5A
0x180028df6  mov     rcx, [rbp+var_40]; struct IUnknown *
0x180028dfa  call    ?SetProxyBlanket@@YAXPEAUIUnknown@@@Z; SetProxyBlanket(IUnknown *)
0x180028dff  mov     rcx, [rbp+var_40]
0x180028e03  lea     r8, [rbp+var_38]
0x180028e07  xor     edx, edx
0x180028e09  mov     rax, [rcx]
0x180028e0c  mov     rax, [rax+18h]
0x180028e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e15  mov     rcx, [rbp+var_40]
0x180028e19  mov     ebx, eax
0x180028e1b  mov     rax, [rcx]
0x180028e1e  mov     rax, [rax+10h]
0x180028e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e27  test    ebx, ebx
0x180028e29  jnz     loc_180028F5A
0x180028e2f  mov     rcx, [rbp+var_38]; struct IUnknown *
0x180028e33  mov     [rbp+var_50], ebx
0x180028e36  call    ?SetProxyBlanket@@YAXPEAUIUnknown@@@Z; SetProxyBlanket(IUnknown *)
0x180028e3b  mov     rcx, [rbp+var_38]
0x180028e3f  lea     r9, [rbp+var_50]
0x180028e43  lea     r8, [rbp+var_48]
0x180028e47  mov     edx, 1
0x180028e4c  mov     rax, [rcx]
0x180028e4f  mov     rax, [rax+18h]
0x180028e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e58  test    eax, eax
0x180028e5a  js      loc_180028F3E
0x180028e60  mov     eax, [rbp+var_50]
0x180028e63  cmp     eax, 1
0x180028e66  jnz     loc_180028F3E
0x180028e6c  mov     rcx, [rbp+var_48]; struct IUnknown *
0x180028e70  call    ?SetProxyBlanket@@YAXPEAUIUnknown@@@Z; SetProxyBlanket(IUnknown *)
0x180028e75  mov     rcx, [rbp+var_48]
0x180028e79  lea     r8, [rbp+var_30]
0x180028e7d  lea     rdx, _GUID_faedcf54_31fe_11d1_aad2_00805fc1270e
0x180028e84  mov     rax, [rcx]
0x180028e87  mov     rax, [rax]
0x180028e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e8f  test    eax, eax
0x180028e91  js      short loc_180028EBF
0x180028e93  mov     rcx, [rbp+var_30]
0x180028e97  lea     rdx, [rbp+var_20]
0x180028e9b  mov     rax, [rcx]
0x180028e9e  mov     rax, [rax+28h]
0x180028ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ea7  mov     rcx, [rbp+var_30]
0x180028eab  mov     edi, eax
0x180028ead  mov     rax, [rcx]
0x180028eb0  mov     rax, [rax+10h]
0x180028eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028eb9  test    edi, edi
0x180028ebb  js      short loc_180028F1A
0x180028ebd  jmp     short loc_180028EF2
0x180028ebf  mov     rcx, [rbp+var_48]
0x180028ec3  lea     rdx, [rbp+pProps]
0x180028ec7  mov     [rbp+pProps], 0
0x180028ecf  mov     rax, [rcx]
0x180028ed2  mov     rax, [rax+38h]
0x180028ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028edb  mov     edi, eax
0x180028edd  test    eax, eax
0x180028edf  js      short loc_180028F1A
0x180028ee1  mov     rcx, [rbp+pProps]; pProps
0x180028ee5  movups  xmm0, xmmword ptr [rcx]
0x180028ee8  movdqu  [rbp+var_20], xmm0
0x180028eed  call    NcFreeNetconProperties
0x180028ef2  mov     rcx, qword ptr [rbp+var_20]
0x180028ef6  cmp     rcx, [rsi]
0x180028ef9  jnz     short loc_180028F1A
0x180028efb  mov     rax, qword ptr [rbp+var_20+8]
0x180028eff  cmp     rax, [rsi+8]
0x180028f03  jnz     short loc_180028F1A
0x180028f05  mov     rcx, [rbp+var_48]
0x180028f09  mov     bl, 1
0x180028f0b  mov     [r14], rcx
0x180028f0e  mov     rax, [rcx]
0x180028f11  mov     rax, [rax+8]
0x180028f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f1a  mov     rcx, [rbp+var_48]
0x180028f1e  mov     rax, [rcx]
0x180028f21  mov     rax, [rax+10h]
0x180028f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f2a  test    bl, bl
0x180028f2c  jnz     short loc_180028F3E
0x180028f2e  test    edi, edi
0x180028f30  js      short loc_180028F3E
0x180028f32  mov     eax, [rbp+var_50]
0x180028f35  cmp     eax, 1
0x180028f38  jz      loc_180028E3B
0x180028f3e  mov     rcx, [rbp+var_38]
0x180028f42  mov     rax, [rcx]
0x180028f45  mov     rax, [rax+10h]
0x180028f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f4e  neg     bl
0x180028f50  sbb     ebx, ebx
0x180028f52  not     ebx
0x180028f54  and     ebx, 80004005h
0x180028f5a  mov     eax, ebx
0x180028f5c  mov     rcx, [rbp+var_10]
0x180028f60  xor     rcx, rsp; StackCookie
0x180028f63  call    __security_check_cookie
0x180028f68  lea     r11, [rsp+80h+var_s0]
0x180028f70  mov     rbx, [r11+20h]
0x180028f74  mov     rsi, [r11+30h]
0x180028f78  mov     rsp, r11
0x180028f7b  pop     r14
0x180028f7d  pop     rdi
0x180028f7e  pop     rbp
0x180028f7f  retn
```
