# HrConnectOrDisconnectNetConObject(HWND__ *,INetConnection *,CDFLAG,ulong)

- ea: `0x18004c00c`
- end: `0x18004c206`
- name: `?HrConnectOrDisconnectNetConObject@@YAJPEAUHWND__@@PEAUINetConnection@@W4CDFLAG@@K@Z`
- size: `506`
- prototype: `__int64 __fastcall(HWND, struct INetConnection *, int, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180044f34`
- `0x1800455c4`

## callees

- `0x180009930`
- `0x180018d74`
- `0x18001bc10`
- `0x18001e1e0`
- `0x180034fdc`
- `0x18004c00c`
- `0x18004c2ac`
- `0x18004c798`
- `0x180065010`

## import_xrefs

- `ntdll!WinSqmSetDWORD` at `0x18004c169`
- `ntdll!WinSqmSetDWORD` at `0x18004c190`
- `ntdll!WinSqmSetDWORD` at `0x18004c169`
- `ntdll!WinSqmSetDWORD` at `0x18004c190`
- `ole32!CoCreateInstance` at `0x18004c0b8`
- `ole32!CoCreateInstance` at `0x18004c0b8`

## pseudocode

```c
__int64 __fastcall HrConnectOrDisconnectNetConObject(HWND a1, struct INetConnection *a2, int a3, unsigned int a4)
{
  struct INetConnection v4; // rax
  int v9; // ebx
  struct INetConnectionVtbl *lpVtbl; // rax
  HRESULT v11; // eax
  struct IUnknownVtbl *v12; // rax
  int v13; // eax
  unsigned int v14; // r9d
  unsigned int v15; // eax
  int v16; // ebx
  int v17; // eax
  struct IUnknown *ppv; // [rsp+30h] [rbp-30h] BYREF
  NETCON_PROPERTIES *pProps; // [rsp+38h] [rbp-28h] BYREF
  IID rclsid; // [rsp+40h] [rbp-20h] BYREF

  v4.lpVtbl = a2->lpVtbl;
  ppv = 0;
  pProps = 0;
  v9 = ((__int64 (__fastcall *)(struct INetConnection *, NETCON_PROPERTIES **))v4.lpVtbl->GetProperties)(a2, &pProps);
  if ( v9 >= 0 )
  {
    if ( pProps->MediaType == NCM_BRIDGE )
    {
      lpVtbl = a2->lpVtbl;
      ppv = 0;
      rclsid = 0;
      v9 = ((__int64 (__fastcall *)(struct INetConnection *, IID *))lpVtbl->GetUiObjectClassId)(a2, &rclsid);
      if ( v9 < 0 )
        goto LABEL_24;
      v11 = CoCreateInstance(&rclsid, 0, 0x401u, &IID_INetConnectionConnectUi, (LPVOID *)&ppv);
    }
    else
    {
      v11 = HrUIInterfaceFromNetCon(a2, &IID_INetConnectionConnectUi, (void **)&ppv);
    }
    v9 = v11;
    if ( v11 >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(struct IUnknown *, struct INetConnection *))ppv->lpVtbl[1].QueryInterface)(ppv, a2);
      if ( v9 < 0 )
      {
LABEL_20:
        ReleaseObj(ppv);
        goto LABEL_24;
      }
      v12 = ppv->lpVtbl;
      if ( a3 )
      {
        v15 = ((__int64 (__fastcall *)(struct IUnknown *, HWND, _QWORD))v12[1].Release)(ppv, a1, a4);
        v16 = v15;
        if ( pProps->MediaType == NCM_BRIDGE )
          WinSqmSetDWORD(0, 1897, v15);
        v9 = HrHandleDisconnectHResult(v16, a2);
        goto LABEL_20;
      }
      v13 = ((__int64 (__fastcall *)(struct IUnknown *, HWND, _QWORD))v12[1].AddRef)(ppv, a1, a4);
      v9 = v13;
      if ( v13 < 0 )
      {
        if ( v13 == -2147022646 )
        {
          v14 = 1073;
        }
        else
        {
          if ( !(unsigned int)HR_NO_ACCESS(v13) )
            goto LABEL_15;
          v14 = 1096;
        }
        NcMsgBox(hInst, a1, 0x430u, v14, 0x30u);
      }
LABEL_15:
      if ( pProps->MediaType == NCM_BRIDGE )
        WinSqmSetDWORD(0, 1896, (unsigned int)v9);
      goto LABEL_20;
    }
  }
  if ( v9 == -2147467262 && a3 == 1 )
  {
    v17 = ((__int64 (__fastcall *)(struct INetConnection *))a2->lpVtbl->Disconnect)(a2);
    v9 = HrHandleDisconnectHResult(v17, a2);
  }
LABEL_24:
  if ( pProps )
    NcFreeNetconProperties(pProps);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004c00c  mov     [rsp-28h+arg_10], rbx
0x18004c011  push    rbp
0x18004c012  push    rsi
0x18004c013  push    rdi
0x18004c014  push    r14
0x18004c016  push    r15
0x18004c018  mov     rbp, rsp
0x18004c01b  sub     rsp, 60h
0x18004c01f  mov     rax, cs:__security_cookie
0x18004c026  xor     rax, rsp
0x18004c029  mov     [rbp+var_10], rax
0x18004c02d  mov     rax, [rdx]
0x18004c030  mov     rdi, rdx
0x18004c033  mov     rsi, rcx
0x18004c036  mov     [rbp+var_30], 0
0x18004c03e  lea     rdx, [rbp+pProps]
0x18004c042  mov     [rbp+pProps], 0
0x18004c04a  mov     rcx, rdi
0x18004c04d  mov     r15d, r9d
0x18004c050  mov     rax, [rax+38h]
0x18004c054  mov     r14d, r8d
0x18004c057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c05c  mov     ebx, eax
0x18004c05e  test    eax, eax
0x18004c060  js      loc_18004C1AD
0x18004c066  mov     rax, [rbp+pProps]
0x18004c06a  mov     rcx, rdi; struct INetConnection *
0x18004c06d  cmp     dword ptr [rax+24h], 7
0x18004c071  jnz     short loc_18004C0C0
0x18004c073  mov     rax, [rdi]
0x18004c076  lea     rdx, [rbp+rclsid]
0x18004c07a  xorps   xmm0, xmm0
0x18004c07d  mov     [rbp+var_30], 0
0x18004c085  movups  xmmword ptr [rbp+rclsid.Data1], xmm0
0x18004c089  mov     rax, [rax+40h]
0x18004c08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c092  mov     ebx, eax
0x18004c094  test    eax, eax
0x18004c096  js      loc_18004C1D6
0x18004c09c  lea     rax, [rbp+var_30]
0x18004c0a0  xor     edx, edx; pUnkOuter
0x18004c0a2  lea     r9, IID_INetConnectionConnectUi; riid
0x18004c0a9  mov     [rsp+60h+ppv], rax; ppv
0x18004c0ae  mov     r8d, 401h; dwClsContext
0x18004c0b4  lea     rcx, [rbp+rclsid]; rclsid
0x18004c0b8  call    cs:__imp_CoCreateInstance
0x18004c0be  jmp     short loc_18004C0D0
0x18004c0c0  lea     r8, [rbp+var_30]; void **
0x18004c0c4  lea     rdx, IID_INetConnectionConnectUi; struct _GUID *
0x18004c0cb  call    ?HrUIInterfaceFromNetCon@@YAJPEAUINetConnection@@AEBU_GUID@@PEAPEAX@Z; HrUIInterfaceFromNetCon(INetConnection *,_GUID const &,void * *)
0x18004c0d0  mov     ebx, eax
0x18004c0d2  test    eax, eax
0x18004c0d4  js      loc_18004C1AD
0x18004c0da  mov     rcx, [rbp+var_30]
0x18004c0de  mov     rdx, rdi
0x18004c0e1  mov     rax, [rcx]
0x18004c0e4  mov     rax, [rax+18h]
0x18004c0e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0ed  mov     ebx, eax
0x18004c0ef  test    eax, eax
0x18004c0f1  js      loc_18004C1A2
0x18004c0f7  mov     rcx, [rbp+var_30]
0x18004c0fb  mov     r8d, r15d
0x18004c0fe  mov     rdx, rsi
0x18004c101  mov     rax, [rcx]
0x18004c104  test    r14d, r14d
0x18004c107  jnz     short loc_18004C171
0x18004c109  mov     rax, [rax+20h]
0x18004c10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c112  mov     ebx, eax
0x18004c114  test    eax, eax
0x18004c116  jns     short loc_18004C155
0x18004c118  cmp     eax, 800708CAh
0x18004c11d  jnz     short loc_18004C127
0x18004c11f  mov     r9d, 431h
0x18004c125  jmp     short loc_18004C138
0x18004c127  mov     ecx, ebx; int
0x18004c129  call    ?HR_NO_ACCESS@@YAHJ@Z; HR_NO_ACCESS(long)
0x18004c12e  test    eax, eax
0x18004c130  jz      short loc_18004C155
0x18004c132  mov     r9d, 448h; unsigned int
0x18004c138  mov     rcx, cs:hInst; hModule
0x18004c13f  mov     r8d, 430h; unsigned int
0x18004c145  mov     rdx, rsi; hWnd
0x18004c148  mov     dword ptr [rsp+60h+ppv], 30h ; '0'; uType
0x18004c150  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18004c155  mov     rax, [rbp+pProps]
0x18004c159  cmp     dword ptr [rax+24h], 7
0x18004c15d  jnz     short loc_18004C1A2
0x18004c15f  mov     r8d, ebx
0x18004c162  mov     edx, 768h
0x18004c167  xor     ecx, ecx
0x18004c169  call    cs:__imp_WinSqmSetDWORD
0x18004c16f  jmp     short loc_18004C1A2
0x18004c171  mov     rax, [rax+28h]
0x18004c175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c17a  mov     rcx, [rbp+pProps]
0x18004c17e  mov     ebx, eax
0x18004c180  cmp     dword ptr [rcx+24h], 7
0x18004c184  jnz     short loc_18004C196
0x18004c186  mov     r8d, eax
0x18004c189  mov     edx, 769h
0x18004c18e  xor     ecx, ecx
0x18004c190  call    cs:__imp_WinSqmSetDWORD
0x18004c196  mov     rdx, rdi; struct INetConnection *
0x18004c199  mov     ecx, ebx; int
0x18004c19b  call    ?HrHandleDisconnectHResult@@YAJJPEAUINetConnection@@@Z; HrHandleDisconnectHResult(long,INetConnection *)
0x18004c1a0  mov     ebx, eax
0x18004c1a2  mov     rcx, [rbp+var_30]; struct IUnknown *
0x18004c1a6  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18004c1ab  jmp     short loc_18004C1D6
0x18004c1ad  cmp     ebx, 80004002h
0x18004c1b3  jnz     short loc_18004C1D6
0x18004c1b5  cmp     r14d, 1
0x18004c1b9  jnz     short loc_18004C1D6
0x18004c1bb  mov     rax, [rdi]
0x18004c1be  mov     rcx, rdi
0x18004c1c1  mov     rax, [rax+20h]
0x18004c1c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c1ca  mov     rdx, rdi; struct INetConnection *
0x18004c1cd  mov     ecx, eax; int
0x18004c1cf  call    ?HrHandleDisconnectHResult@@YAJJPEAUINetConnection@@@Z; HrHandleDisconnectHResult(long,INetConnection *)
0x18004c1d4  mov     ebx, eax
0x18004c1d6  mov     rcx, [rbp+pProps]; pProps
0x18004c1da  test    rcx, rcx
0x18004c1dd  jz      short loc_18004C1E4
0x18004c1df  call    NcFreeNetconProperties
0x18004c1e4  mov     eax, ebx
0x18004c1e6  mov     rcx, [rbp+var_10]
0x18004c1ea  xor     rcx, rsp; StackCookie
0x18004c1ed  call    __security_check_cookie
0x18004c1f2  mov     rbx, [rsp+60h+arg_10]
0x18004c1fa  add     rsp, 60h
0x18004c1fe  pop     r15
0x18004c200  pop     r14
0x18004c202  pop     rdi
0x18004c203  pop     rsi
0x18004c204  pop     rbp
0x18004c205  retn
```
