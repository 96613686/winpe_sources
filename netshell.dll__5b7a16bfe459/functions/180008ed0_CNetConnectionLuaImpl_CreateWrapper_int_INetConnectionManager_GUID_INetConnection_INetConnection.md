# CNetConnectionLuaImpl::CreateWrapper(int,INetConnectionManager *,_GUID,INetConnection *,INetConnection * *)

- ea: `0x180008ed0`
- end: `0x180009131`
- name: `?CreateWrapper@CNetConnectionLuaImpl@@SAJHPEAUINetConnectionManager@@U_GUID@@PEAUINetConnection@@PEAPEAU4@@Z`
- size: `609`
- prototype: `__int64 __fastcall(unsigned int, struct IUnknown *, struct _GUID *, struct INetConnection *, struct INetConnection **)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005dab0`
- `0x18005e340`
- `0x18005eeb0`

## callees

- `0x180008ed0`
- `0x180009930`
- `0x18001644c`
- `0x18004f930`
- `0x18005e590`
- `0x18005eb94`
- `0x180062124`
- `0x180065010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800090c8`
- `ole32!CoTaskMemFree` at `0x1800090c8`
- `ole32!CoTaskMemAlloc` at `0x180009071`
- `ole32!CoTaskMemAlloc` at `0x180009071`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNetConnectionLuaImpl::CreateWrapper(
        unsigned int a1,
        struct IUnknown *a2,
        struct _GUID *a3,
        struct INetConnection *a4,
        struct INetConnection **a5)
{
  struct INetConnection **v9; // rdi
  int v11; // r12d
  NETCON_PROPERTIES *v12; // r15
  WCHAR *v13; // r9
  NETCON_PROPERTIES *pProps; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v15[10]; // [rsp+28h] [rbp-50h] BYREF

  v9 = a5;
  if ( !a5 )
    return 2147500035LL;
  if ( !a4 )
    return 2147942487LL;
  pProps = 0;
  v15[0] = 0;
  v11 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD *))a2->lpVtbl->QueryInterface)(a2, &IID_INetLua, v15);
  if ( v11 >= 0 )
  {
    LODWORD(a5) = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, struct INetConnection ***))(*(_QWORD *)v15[0] + 48LL))(v15[0], &a5);
    if ( v11 >= 0 )
    {
      v11 = ATL::CComObject<CNetConnectionLuaImpl>::CreateInstance(&pProps);
      if ( v11 >= 0 )
      {
        v12 = pProps;
        if ( *(struct IUnknown **)&pProps[2].Status != a2 )
          ATL::AtlComPtrAssign((struct IUnknown **)&pProps[2].Status, a2);
        v12[1].guidId.Data1 = a1;
        v11 = CNetLuaImpl<INetConnection>::SetObject(&v12->dwCharacter, (unsigned int)a5, a4);
        if ( v11 >= 0 )
        {
          if ( !memcmp_0(a3, &GUID_NULL, 0x10u) )
          {
            pProps = 0;
            v11 = ((__int64 (__fastcall *)(struct INetConnection *, NETCON_PROPERTIES **))a4->lpVtbl->GetProperties)(
                    a4,
                    &pProps);
            if ( v11 < 0 )
              goto LABEL_19;
            v12[2].guidId = pProps->clsidThisObject;
            NcFreeNetconProperties(pProps);
            a5 = 0;
            v11 = ((__int64 (__fastcall *)(struct INetConnection *, GUID *, struct INetConnection ***))a4->lpVtbl->QueryInterface)(
                    a4,
                    &IID_IPersistNetConnection,
                    &a5);
            if ( v11 >= 0 )
            {
              v11 = ((__int64 (__fastcall *)(struct INetConnection **, LPWSTR *))(*a5)[4].lpVtbl)(a5, &v12[2].pszwName);
              if ( v11 >= 0 )
              {
                v13 = (WCHAR *)CoTaskMemAlloc(LODWORD(v12[2].pszwName));
                v12[2].pszwDeviceName = v13;
                if ( v13 )
                  v11 = ((__int64 (__fastcall *)(struct INetConnection **, WCHAR *, _QWORD))(*a5)[5].lpVtbl)(
                          a5,
                          v13,
                          LODWORD(v12[2].pszwName));
                else
                  v11 = -2147024882;
              }
            }
            ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(&a5);
            if ( v11 < 0 )
            {
LABEL_19:
              CoTaskMemFree(v12[2].pszwDeviceName);
              v12[2].pszwDeviceName = 0;
              LODWORD(v12[2].pszwName) = 0;
              v12[2].guidId = GUID_NULL;
              goto LABEL_22;
            }
          }
          else
          {
            v12[2].guidId = *a3;
          }
          v11 = (**(__int64 (__fastcall ***)(NETCON_PROPERTIES *, GUID *, struct INetConnection **))&v12->guidId.Data1)(
                  v12,
                  &IID_INetConnection,
                  v9);
        }
      }
    }
  }
LABEL_22:
  ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(v15);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180008ed0  push    rbx
0x180008ed2  push    rbp
0x180008ed3  push    rsi
0x180008ed4  push    rdi
0x180008ed5  push    r12
0x180008ed7  push    r13
0x180008ed9  push    r14
0x180008edb  push    r15
0x180008edd  sub     rsp, 38h
0x180008ee1  mov     rbx, r9
0x180008ee4  mov     rsi, r8
0x180008ee7  mov     r14, rdx
0x180008eea  mov     ebp, ecx
0x180008eec  mov     rdi, [rsp+78h+arg_20]
0x180008ef4  test    rdi, rdi
0x180008ef7  jnz     short loc_180008F03
0x180008ef9  mov     eax, 80004003h
0x180008efe  jmp     loc_180009120
0x180008f03  test    rbx, rbx
0x180008f06  jnz     short loc_180008F12
0x180008f08  mov     eax, 80070057h
0x180008f0d  jmp     loc_180009120
0x180008f12  xor     r13d, r13d
0x180008f15  mov     [rsp+78h+pProps], r13
0x180008f1a  mov     [rsp+78h+var_50], r13
0x180008f1f  mov     rax, [rdx]
0x180008f22  lea     r8, [rsp+78h+var_50]
0x180008f27  lea     rdx, IID_INetLua
0x180008f2e  mov     rcx, r14
0x180008f31  mov     rax, [rax]
0x180008f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f39  mov     r12d, eax
0x180008f3c  test    eax, eax
0x180008f3e  js      loc_180009113
0x180008f44  mov     dword ptr [rsp+78h+arg_20], r13d
0x180008f4c  mov     rcx, [rsp+78h+var_50]
0x180008f51  mov     rax, [rcx]
0x180008f54  lea     rdx, [rsp+78h+arg_20]
0x180008f5c  mov     rax, [rax+30h]
0x180008f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f65  mov     r12d, eax
0x180008f68  test    eax, eax
0x180008f6a  js      loc_180009113
0x180008f70  lea     rcx, [rsp+78h+pProps]
0x180008f75  call    ?CreateInstance@?$CComObject@VCNetConnectionLuaImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CNetConnectionLuaImpl>::CreateInstance(ATL::CComObject<CNetConnectionLuaImpl> * *)
0x180008f7a  mov     r12d, eax
0x180008f7d  test    eax, eax
0x180008f7f  js      loc_180009113
0x180008f85  mov     r15, [rsp+78h+pProps]
0x180008f8a  lea     rcx, [r15+0C0h]; struct IUnknown **
0x180008f91  cmp     [rcx], r14
0x180008f94  jz      short loc_180008F9E
0x180008f96  mov     rdx, r14; struct IUnknown *
0x180008f99  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180008f9e  mov     [r15+50h], ebp
0x180008fa2  lea     rcx, [r15+28h]
0x180008fa6  mov     r8, rbx
0x180008fa9  mov     edx, dword ptr [rsp+78h+arg_20]
0x180008fb0  call    ?SetObject@?$CNetLuaImpl@UINetConnection@@@@IEAAJW4tagNET_LUA_ELEVATION_LEVEL@@PEAUINetConnection@@@Z; CNetLuaImpl<INetConnection>::SetObject(tagNET_LUA_ELEVATION_LEVEL,INetConnection *)
0x180008fb5  mov     r12d, eax
0x180008fb8  test    eax, eax
0x180008fba  js      loc_180009113
0x180008fc0  mov     r8d, 10h; Size
0x180008fc6  lea     rdx, GUID_NULL; Buf2
0x180008fcd  mov     rcx, rsi; Buf1
0x180008fd0  call    memcmp_0
0x180008fd5  test    eax, eax
0x180008fd7  jnz     loc_1800090ED
0x180008fdd  mov     [rsp+78h+pProps], r13
0x180008fe2  mov     rax, [rbx]
0x180008fe5  lea     rdx, [rsp+78h+pProps]
0x180008fea  mov     rcx, rbx
0x180008fed  mov     rax, [rax+38h]
0x180008ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ff6  mov     r12d, eax
0x180008ff9  test    eax, eax
0x180008ffb  js      loc_1800090C1
0x180009001  mov     rax, [rsp+78h+pProps]
0x180009006  movups  xmm0, xmmword ptr [rax+2Ch]
0x18000900a  movups  xmmword ptr [r15+0A0h], xmm0
0x180009012  mov     rcx, [rsp+78h+pProps]; pProps
0x180009017  call    NcFreeNetconProperties
0x18000901c  mov     [rsp+78h+arg_20], r13
0x180009024  mov     rax, [rbx]
0x180009027  lea     r8, [rsp+78h+arg_20]
0x18000902f  lea     rdx, IID_IPersistNetConnection
0x180009036  mov     rcx, rbx
0x180009039  mov     rax, [rax]
0x18000903c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009041  mov     r12d, eax
0x180009044  test    eax, eax
0x180009046  js      short loc_1800090AF
0x180009048  mov     rcx, [rsp+78h+arg_20]
0x180009050  mov     rax, [rcx]
0x180009053  lea     rdx, [r15+0B0h]
0x18000905a  mov     rax, [rax+20h]
0x18000905e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009063  mov     r12d, eax
0x180009066  test    eax, eax
0x180009068  js      short loc_1800090AF
0x18000906a  mov     ecx, [r15+0B0h]; cb
0x180009071  call    cs:__imp_CoTaskMemAlloc
0x180009077  mov     r9, rax
0x18000907a  mov     [r15+0B8h], rax
0x180009081  test    rax, rax
0x180009084  jz      short loc_1800090A9
0x180009086  mov     rcx, [rsp+78h+arg_20]
0x18000908e  mov     rdx, [rcx]
0x180009091  mov     rax, [rdx+28h]
0x180009095  mov     r8d, [r15+0B0h]
0x18000909c  mov     rdx, r9
0x18000909f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090a4  mov     r12d, eax
0x1800090a7  jmp     short loc_1800090AF
0x1800090a9  mov     r12d, 8007000Eh
0x1800090af  lea     rcx, [rsp+78h+arg_20]
0x1800090b7  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x1800090bc  test    r12d, r12d
0x1800090bf  jns     short loc_1800090F8
0x1800090c1  mov     rcx, [r15+0B8h]; pv
0x1800090c8  call    cs:__imp_CoTaskMemFree
0x1800090ce  mov     [r15+0B8h], r13
0x1800090d5  mov     [r15+0B0h], r13d
0x1800090dc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800090e3  movups  xmmword ptr [r15+0A0h], xmm0
0x1800090eb  jmp     short loc_180009113
0x1800090ed  movaps  xmm0, xmmword ptr [rsi]
0x1800090f0  movups  xmmword ptr [r15+0A0h], xmm0
0x1800090f8  mov     rax, [r15]
0x1800090fb  mov     r8, rdi
0x1800090fe  lea     rdx, IID_INetConnection
0x180009105  mov     rcx, r15
0x180009108  mov     rax, [rax]
0x18000910b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009110  mov     r12d, eax
0x180009113  lea     rcx, [rsp+78h+var_50]
0x180009118  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x18000911d  mov     eax, r12d
0x180009120  add     rsp, 38h
0x180009124  pop     r15
0x180009126  pop     r14
0x180009128  pop     r13
0x18000912a  pop     r12
0x18000912c  pop     rdi
0x18000912d  pop     rsi
0x18000912e  pop     rbp
0x18000912f  pop     rbx
0x180009130  retn
```
