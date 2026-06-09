# CreateRemoteHandler

- ea: `0x180096e70`
- end: `0x180097031`
- name: `CreateRemoteHandler`
- size: `449`
- prototype: `HRESULT __fastcall(const _GUID *rclsid, IUnknown *pUnkOuter, const _GUID *ppv, void **flags, unsigned int fComOuterObject, int *fOle1Server, int *rclsid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002fa3c`

## callees

- `0x18006dbd4`
- `0x180096e70`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-0!InternalCreateIdentityHandler` at `0x180096f81`
- `api-ms-win-core-com-private-l1-1-0!InternalCreateIdentityHandler` at `0x180096f81`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x180096ea8`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x180096ea8`
- `api-ms-win-core-com-private-l1-1-1!InternalCStdIdentityUpdateFlags` at `0x180096fe4`
- `api-ms-win-core-com-private-l1-1-1!InternalCStdIdentityUpdateFlags` at `0x180096fe4`
- `api-ms-win-core-com-private-l1-1-1!InternalCStdIdentityGetIProxyManager` at `0x180096ff5`
- `api-ms-win-core-com-private-l1-1-1!InternalCStdIdentityGetIProxyManager` at `0x180096ff5`
- `api-ms-win-core-com-private-l1-1-1!InternalCStdIdentityGetInternalUnk` at `0x180096fb9`
- `api-ms-win-core-com-private-l1-1-1!InternalCStdIdentityGetInternalUnk` at `0x180096fb9`

## pseudocode

```c
__int64 __fastcall CreateRemoteHandler(
        const _GUID *rclsid,
        IUnknown *pUnkOuter,
        _GUID *ppv,
        void **flags,
        __int16 fComOuterObject,
        int *fOle1Server,
        int *rclsid_0)
{
  int *v7; // r15
  int *v9; // rdi
  struct _TEB *v12; // rax
  int v13; // ebx
  IUnknown *v14; // rax
  IUnknown *v15; // rdi
  void *InternalUnk; // rax
  __int64 IProxyManager; // rax
  int v19; // [rsp+30h] [rbp-28h]
  CStdIdentity *pStdId; // [rsp+70h] [rbp+18h] BYREF

  pStdId = (CStdIdentity *)ppv;
  v7 = fOle1Server;
  v9 = rclsid_0;
  *fOle1Server = 0;
  *v9 = 0;
  if ( CoIsOle1Class(rclsid) )
  {
    v12 = NtCurrentTeb();
    *v9 = 1;
    if ( (*((_BYTE *)v12->ReservedForOle + 20) & 0x40) != 0 )
    {
      return (unsigned int)-2147467242;
    }
    else
    {
      if ( (*((_BYTE *)NtCurrentTeb()->ReservedForOle + 20) & 0x40) != 0 )
        return (unsigned int)-2147024882;
      v14 = CDdeObject::Create(pUnkOuter, rclsid, 2u, 0, 0, 0, v19);
      if ( (v15 = v14) == 0 )
      {
        return (unsigned int)-2147024882;
      }
      else
      {
        v13 = ((__int64 (__fastcall *)(IUnknown *, GUID *, void **))v14->lpVtbl->QueryInterface)(
                v14,
                &IID_IUnknown,
                flags);
        ((void (__fastcall *)(IUnknown *))v15->lpVtbl->Release)(v15);
      }
    }
  }
  else
  {
    pStdId = 0;
    if ( (fComOuterObject & 0x200) != 0 || (fComOuterObject & 0x2200) == 0 )
    {
      v13 = ((__int64 (__fastcall *)(IUnknown *, GUID *, CStdIdentity **))pUnkOuter->lpVtbl->QueryInterface)(
              pUnkOuter,
              &IID_IStdIdentity,
              &pStdId);
      if ( v13 >= 0 )
      {
        InternalUnk = (void *)InternalCStdIdentityGetInternalUnk(pStdId);
        *flags = InternalUnk;
        (*(void (__fastcall **)(void *))(*(_QWORD *)InternalUnk + 8LL))(InternalUnk);
        InternalCStdIdentityUpdateFlags(pStdId, 1025);
        IProxyManager = InternalCStdIdentityGetIProxyManager(pStdId);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)IProxyManager + 16LL))(IProxyManager);
        *v7 = 1;
      }
    }
    else
    {
      return (unsigned int)InternalCreateIdentityHandler(pUnkOuter, &IID_IUnknown, flags);
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180096e70  mov     [rsp+arg_0], rbx
0x180096e75  mov     [rsp+arg_8], rsi
0x180096e7a  mov     [rsp+pStdId], r8
0x180096e7f  push    rdi
0x180096e80  push    r14
0x180096e82  push    r15
0x180096e84  sub     rsp, 40h
0x180096e88  mov     r15, [rsp+58h+arg_28]
0x180096e90  mov     r14, ppv
0x180096e93  mov     rdi, [rsp+58h+rclsid_0]
0x180096e9b  mov     rbx, pUnkOuter
0x180096e9e  mov     rsi, rclsid
0x180096ea1  and     dword ptr [r15], 0
0x180096ea5  and     dword ptr [rdi], 0
0x180096ea8  call    cs:__imp_CoIsOle1Class
0x180096eaf  nop     dword ptr [rax+rax+00h]
0x180096eb4  test    eax, eax
0x180096eb6  jz      loc_180096F54
0x180096ebc  mov     rax, gs:30h
0x180096ec5  mov     dword ptr [rdi], 1
0x180096ecb  mov     rclsid, [rax+1758h]
0x180096ed2  test    byte ptr [rclsid+14h], 40h
0x180096ed6  jz      short loc_180096EE2
0x180096ed8  mov     ebx, 80004016h
0x180096edd  jmp     loc_18009701A
0x180096ee2  mov     rax, gs:30h
0x180096eeb  mov     rclsid, [rax+1758h]
0x180096ef2  test    byte ptr [rclsid+14h], 40h
0x180096ef6  jnz     short loc_180096F4A
0x180096ef8  xor     r9d, r9d; aTopic
0x180096efb  mov     pUnkOuter, rsi; clsid
0x180096efe  and     [rsp+58h+var_30], ppv
0x180096f03  mov     rclsid, rbx; pUnkOuter
0x180096f06  and     [rsp+58h+var_38], ppv
0x180096f0b  lea     r8d, [ppv+2]; ulObjType
0x180096f0f  call    ?Create@CDdeObject@@SAPEAUIUnknown@@PEAU2@AEBU_GUID@@KGPEAGPEAPEAV1@H@Z; CDdeObject::Create(IUnknown *,_GUID const &,ulong,ushort,ushort *,CDdeObject * *,int)
0x180096f14  mov     rdi, rax
0x180096f17  test    rax, rax
0x180096f1a  jz      short loc_180096F4A
0x180096f1c  mov     rclsid, [rax]
0x180096f1f  lea     pUnkOuter, IID_IUnknown
0x180096f26  mov     r8, r14
0x180096f29  mov     rax, [rclsid]
0x180096f2c  mov     rclsid, rdi
0x180096f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096f34  mov     rclsid, [rdi]
0x180096f37  mov     ebx, eax
0x180096f39  mov     rax, [rclsid+10h]
0x180096f3d  mov     rclsid, rdi
0x180096f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096f45  jmp     loc_18009701A
0x180096f4a  mov     ebx, 8007000Eh
0x180096f4f  jmp     loc_18009701A
0x180096f54  and     [rsp+58h+pStdId], 0
0x180096f5a  test    dword ptr [rsp+58h+arg_20], 200h
0x180096f65  jnz     short loc_180096F94
0x180096f67  test    dword ptr [rsp+58h+arg_20], 2200h
0x180096f72  jz      short loc_180096F94
0x180096f74  mov     r8, r14
0x180096f77  lea     pUnkOuter, IID_IUnknown
0x180096f7e  mov     rclsid, rbx
0x180096f81  call    cs:__imp_InternalCreateIdentityHandler
0x180096f88  nop     dword ptr [rax+rax+00h]
0x180096f8d  mov     ebx, eax
0x180096f8f  jmp     loc_18009701A
0x180096f94  mov     rax, [rbx]
0x180096f97  lea     r8, [rsp+58h+pStdId]
0x180096f9c  lea     pUnkOuter, IID_IStdIdentity
0x180096fa3  mov     rclsid, rbx
0x180096fa6  mov     rax, [rax]
0x180096fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096fae  mov     ebx, eax
0x180096fb0  test    eax, eax
0x180096fb2  js      short loc_18009701A
0x180096fb4  mov     rclsid, [rsp+58h+pStdId]
0x180096fb9  call    cs:__imp_InternalCStdIdentityGetInternalUnk
0x180096fc0  nop     dword ptr [rax+rax+00h]
0x180096fc5  mov     [r14], rax
0x180096fc8  mov     pUnkOuter, rax
0x180096fcb  mov     rclsid, [rax]
0x180096fce  mov     rax, [rclsid+8]
0x180096fd2  mov     rclsid, pUnkOuter
0x180096fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096fda  mov     rclsid, [rsp+58h+pStdId]
0x180096fdf  mov     edx, 401h
0x180096fe4  call    cs:__imp_InternalCStdIdentityUpdateFlags
0x180096feb  nop     dword ptr [rax+rax+00h]
0x180096ff0  mov     rclsid, [rsp+58h+pStdId]
0x180096ff5  call    cs:__imp_InternalCStdIdentityGetIProxyManager
0x180096ffc  nop     dword ptr [rax+rax+00h]
0x180097001  mov     pUnkOuter, rax
0x180097004  mov     rclsid, [rax]
0x180097007  mov     rax, [rclsid+10h]
0x18009700b  mov     rclsid, pUnkOuter
0x18009700e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097013  mov     dword ptr [r15], 1
0x18009701a  mov     rsi, [rsp+58h+arg_8]
0x18009701f  mov     eax, ebx
0x180097021  mov     rbx, [rsp+58h+arg_0]
0x180097026  add     rsp, 40h
0x18009702a  pop     r15
0x18009702c  pop     r14
0x18009702e  pop     rdi
0x18009702f  retn
```
