# CNetConnectionLuaImpl::Load(uchar const *,ulong)

- ea: `0x18005f8a0`
- end: `0x18005fa11`
- name: `?Load@CNetConnectionLuaImpl@@UEAAJPEBEK@Z`
- size: `369`
- prototype: `__int64 __fastcall(CNetConnectionLuaImpl *this, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001644c`
- `0x18004f930`
- `0x18005e198`
- `0x18005e958`
- `0x18005f8a0`
- `0x180062130`
- `0x180065010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18005f992`
- `ole32!CoTaskMemFree` at `0x18005f992`
- `ole32!CoTaskMemAlloc` at `0x18005f9bc`
- `ole32!CoTaskMemAlloc` at `0x18005f9bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CNetConnectionLuaImpl::Load(CNetConnectionLuaImpl *this, const unsigned __int8 *a2, unsigned int a3)
{
  SIZE_T v4; // r15
  int InnerObject; // ebx
  int v7; // eax
  void *v8; // rcx
  _DWORD *v9; // rsi
  void *v10; // rax
  GUID v12; // [rsp+20h] [rbp-10h] BYREF
  struct IUnknown *v13; // [rsp+60h] [rbp+30h] BYREF
  __int64 (__fastcall ***v14)(_QWORD, GUID *, struct IUnknown **); // [rsp+78h] [rbp+48h] BYREF

  v4 = a3;
  v14 = 0;
  InnerObject = CNetLuaImpl<INetConnection>::GetInnerObject((char *)this + 8, &v14);
  if ( InnerObject >= 0 )
  {
    v13 = 0;
    InnerObject = (**v14)(v14, &IID_IPersistNetConnection, &v13);
    if ( InnerObject >= 0 )
    {
      v7 = ((__int64 (__fastcall *)(struct IUnknown *, const unsigned __int8 *, _QWORD))v13->lpVtbl[1].Release)(
             v13,
             a2,
             (unsigned int)v4);
      InnerObject = v7;
      if ( v7 == -2147024156 || v7 == -2147220764 )
      {
        if ( v13 )
          ATL::AtlComPtrAssign(&v13, 0);
        v12 = IID_IPersistNetConnection;
        InnerObject = ((__int64 (__fastcall *)(char *, _QWORD, GUID *, struct IUnknown **))CNetLuaImpl<INetConnection>::AutoElevate)(
                        (char *)this + 8,
                        (unsigned int)InnerObject,
                        &v12,
                        &v13);
        if ( InnerObject < 0 )
          goto LABEL_16;
        InnerObject = ((__int64 (__fastcall *)(struct IUnknown *, const unsigned __int8 *, _QWORD))v13->lpVtbl[1].Release)(
                        v13,
                        a2,
                        (unsigned int)v4);
      }
      if ( InnerObject >= 0 )
      {
        v8 = (void *)*((_QWORD *)this + 19);
        if ( v8 )
        {
          CoTaskMemFree(v8);
          v9 = (_DWORD *)((char *)this + 144);
          *((_QWORD *)this + 19) = 0;
          *((_DWORD *)this + 36) = 0;
        }
        else
        {
          v9 = (_DWORD *)((char *)this + 144);
        }
        v10 = CoTaskMemAlloc(v4);
        *((_QWORD *)this + 19) = v10;
        if ( v10 )
        {
          *v9 = v4;
          memcpy_0(v10, a2, v4);
        }
        else
        {
          InnerObject = -2147024882;
        }
      }
    }
LABEL_16:
    ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(&v13);
  }
  ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(&v14);
  return (unsigned int)InnerObject;
}

```

## disassembly

```asm
0x18005f8a0  mov     [rsp-28h+arg_8], rbx
0x18005f8a5  mov     [rsp-28h+arg_10], rsi
0x18005f8aa  push    rbp
0x18005f8ab  push    rdi
0x18005f8ac  push    r12
0x18005f8ae  push    r14
0x18005f8b0  push    r15
0x18005f8b2  mov     rbp, rsp
0x18005f8b5  sub     rsp, 30h
0x18005f8b9  mov     r12, rdx
0x18005f8bc  mov     r15d, r8d
0x18005f8bf  mov     rdi, rcx
0x18005f8c2  mov     [rbp+arg_18], 0
0x18005f8ca  lea     rdx, [rbp+arg_18]
0x18005f8ce  add     rcx, 8
0x18005f8d2  call    ?GetInnerObject@?$CNetLuaImpl@UINetConnection@@@@IEAAJPEAPEAUINetConnection@@@Z; CNetLuaImpl<INetConnection>::GetInnerObject(INetConnection * *)
0x18005f8d7  mov     ebx, eax
0x18005f8d9  test    eax, eax
0x18005f8db  js      loc_18005F9EF
0x18005f8e1  mov     rcx, [rbp+arg_18]
0x18005f8e5  lea     r8, [rbp+arg_0]
0x18005f8e9  mov     [rbp+arg_0], 0
0x18005f8f1  lea     rdx, IID_IPersistNetConnection
0x18005f8f8  mov     rax, [rcx]
0x18005f8fb  mov     rax, [rax]
0x18005f8fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f903  mov     ebx, eax
0x18005f905  test    eax, eax
0x18005f907  js      loc_18005F9E6
0x18005f90d  mov     rcx, [rbp+arg_0]
0x18005f911  mov     r8d, r15d
0x18005f914  mov     rdx, r12
0x18005f917  mov     rax, [rcx]
0x18005f91a  mov     rax, [rax+28h]
0x18005f91e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f923  mov     ebx, eax
0x18005f925  cmp     eax, 800702E4h
0x18005f92a  jz      short loc_18005F933
0x18005f92c  cmp     eax, 800402E4h
0x18005f931  jnz     short loc_18005F982
0x18005f933  cmp     [rbp+arg_0], 0
0x18005f938  jz      short loc_18005F945
0x18005f93a  xor     edx, edx; struct IUnknown *
0x18005f93c  lea     rcx, [rbp+arg_0]; struct IUnknown **
0x18005f940  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18005f945  movups  xmm0, xmmword ptr cs:IID_IPersistNetConnection.Data1
0x18005f94c  lea     r9, [rbp+arg_0]
0x18005f950  mov     edx, ebx
0x18005f952  lea     r8, [rbp+var_10]
0x18005f956  lea     rcx, [rdi+8]
0x18005f95a  movdqu  [rbp+var_10], xmm0
0x18005f95f  call    ?AutoElevate@?$CNetLuaImpl@UINetConnection@@@@IEAAJJU_GUID@@PEAPEAX@Z; CNetLuaImpl<INetConnection>::AutoElevate(long,_GUID,void * *)
0x18005f964  mov     ebx, eax
0x18005f966  test    eax, eax
0x18005f968  js      short loc_18005F9E6
0x18005f96a  mov     rcx, [rbp+arg_0]
0x18005f96e  mov     r8d, r15d
0x18005f971  mov     rdx, r12
0x18005f974  mov     rax, [rcx]
0x18005f977  mov     rax, [rax+28h]
0x18005f97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f980  mov     ebx, eax
0x18005f982  test    ebx, ebx
0x18005f984  js      short loc_18005F9E6
0x18005f986  mov     rcx, [rdi+98h]; pv
0x18005f98d  test    rcx, rcx
0x18005f990  jz      short loc_18005F9B2
0x18005f992  call    cs:__imp_CoTaskMemFree
0x18005f998  lea     rsi, [rdi+90h]
0x18005f99f  mov     qword ptr [rdi+98h], 0
0x18005f9aa  mov     dword ptr [rsi], 0
0x18005f9b0  jmp     short loc_18005F9B9
0x18005f9b2  lea     rsi, [rdi+90h]
0x18005f9b9  mov     rcx, r15; cb
0x18005f9bc  call    cs:__imp_CoTaskMemAlloc
0x18005f9c2  mov     [rdi+98h], rax
0x18005f9c9  test    rax, rax
0x18005f9cc  jz      short loc_18005F9E1
0x18005f9ce  mov     r8, r15; Size
0x18005f9d1  mov     [rsi], r15d
0x18005f9d4  mov     rdx, r12; Src
0x18005f9d7  mov     rcx, rax; void *
0x18005f9da  call    memcpy_0
0x18005f9df  jmp     short loc_18005F9E6
0x18005f9e1  mov     ebx, 8007000Eh
0x18005f9e6  lea     rcx, [rbp+arg_0]
0x18005f9ea  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x18005f9ef  lea     rcx, [rbp+arg_18]
0x18005f9f3  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x18005f9f8  mov     rsi, [rsp+30h+arg_10]
0x18005f9fd  mov     eax, ebx
0x18005f9ff  mov     rbx, [rsp+30h+arg_8]
0x18005fa04  add     rsp, 30h
0x18005fa08  pop     r15
0x18005fa0a  pop     r14
0x18005fa0c  pop     r12
0x18005fa0e  pop     rdi
0x18005fa0f  pop     rbp
0x18005fa10  retn
```
