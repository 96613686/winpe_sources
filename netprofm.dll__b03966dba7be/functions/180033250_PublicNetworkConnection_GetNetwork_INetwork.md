# PublicNetworkConnection::GetNetwork(INetwork * *)

- ea: `0x180033250`
- end: `0x1800333fd`
- name: `?GetNetwork@PublicNetworkConnection@@UEAAJPEAPEAUINetwork@@@Z`
- size: `429`
- prototype: `__int64 __fastcall(PublicNetworkConnection *__hidden this, struct INetwork **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006770`
- `0x180006810`
- `0x1800086b0`
- `0x1800120d0`
- `0x180030eac`
- `0x180033250`
- `0x180033404`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033351`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033351`

## pseudocode

```c
__int64 __fastcall PublicNetworkConnection::GetNetwork(struct IGlobalInterfaceTable **this, struct INetwork **a2)
{
  PVOID *v4; // rcx
  HRESULT PrivateNetworkInterface; // ebx
  struct INetworkPrivate *v7; // [rsp+30h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-28h] BYREF
  struct INetworkInterfacePrivate *v9; // [rsp+40h] [rbp-20h] BYREF
  __int128 v10; // [rsp+48h] [rbp-18h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_cbe8f8d8b9e533271e4839292fb068f7_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    *a2 = 0;
    v9 = 0;
    PrivateNetworkInterface = PublicNetworkConnection::GetPrivateNetworkInterface((PublicNetworkConnection *)this, &v9);
    if ( PrivateNetworkInterface >= 0 )
    {
      v10 = 0;
      PrivateNetworkInterface = (*(__int64 (__fastcall **)(struct INetworkInterfacePrivate *, __int128 *))(*(_QWORD *)v9 + 40LL))(
                                  v9,
                                  &v10);
      if ( PrivateNetworkInterface >= 0 )
      {
        ppv = 0;
        PrivateNetworkInterface = CoCreateInstance(
                                    &CLSID_CNetworkListManager,
                                    0,
                                    4u,
                                    &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b,
                                    &ppv);
        if ( PrivateNetworkInterface >= 0 )
        {
          v7 = 0;
          PrivateNetworkInterface = (*(__int64 (__fastcall **)(LPVOID, __int128 *, struct INetworkPrivate **))(*(_QWORD *)ppv + 48LL))(
                                      ppv,
                                      &v10,
                                      &v7);
          if ( PrivateNetworkInterface >= 0 )
            PrivateNetworkInterface = PublicNetwork::CreateInstance(this[9], v7, a2);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v7);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_cbe8f8d8b9e533271e4839292fb068f7_Traceguids,
        (unsigned int)PrivateNetworkInterface);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v9);
  }
  else
  {
    PrivateNetworkInterface = -2147467261;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
      WPP_SF_d(v4[2], 16, WPP_cbe8f8d8b9e533271e4839292fb068f7_Traceguids, 2147500035LL);
  }
  return (unsigned int)PrivateNetworkInterface;
}

```

## disassembly

```asm
0x180033250  mov     [rsp-18h+arg_10], rbx
0x180033255  mov     [rsp-18h+arg_18], rsi
0x18003325a  push    rbp
0x18003325b  push    rdi
0x18003325c  push    r12
0x18003325e  mov     rbp, rsp
0x180033261  sub     rsp, 60h
0x180033265  mov     rax, cs:__security_cookie
0x18003326c  xor     rax, rsp
0x18003326f  mov     [rbp+var_8], rax
0x180033273  mov     rdi, rdx
0x180033276  mov     rsi, rcx
0x180033279  lea     r12, WPP_GLOBAL_Control
0x180033280  mov     rcx, cs:WPP_GLOBAL_Control
0x180033287  cmp     rcx, r12
0x18003328a  jz      short loc_1800332AE
0x18003328c  test    byte ptr [rcx+1Ch], 8
0x180033290  jz      short loc_1800332AE
0x180033292  mov     edx, 0Fh
0x180033297  lea     r8, WPP_cbe8f8d8b9e533271e4839292fb068f7_Traceguids
0x18003329e  mov     rcx, [rcx+10h]
0x1800332a2  call    WPP_SF_
0x1800332a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800332ae  test    rdi, rdi
0x1800332b1  jnz     short loc_1800332E6
0x1800332b3  mov     ebx, 80004003h
0x1800332b8  cmp     rcx, r12
0x1800332bb  jz      loc_1800333DA
0x1800332c1  test    byte ptr [rcx+1Ch], 8
0x1800332c5  jz      loc_1800333DA
0x1800332cb  lea     edx, [rdi+10h]
0x1800332ce  mov     r9d, ebx
0x1800332d1  lea     r8, WPP_cbe8f8d8b9e533271e4839292fb068f7_Traceguids
0x1800332d8  mov     rcx, [rcx+10h]
0x1800332dc  call    WPP_SF_d
0x1800332e1  jmp     loc_1800333DA
0x1800332e6  mov     qword ptr [rdi], 0
0x1800332ed  mov     [rbp+var_20], 0
0x1800332f5  lea     rdx, [rbp+var_20]; struct INetworkInterfacePrivate **
0x1800332f9  mov     rcx, rsi; this
0x1800332fc  call    ?GetPrivateNetworkInterface@PublicNetworkConnection@@AEBAJPEAPEAUINetworkInterfacePrivate@@@Z; PublicNetworkConnection::GetPrivateNetworkInterface(INetworkInterfacePrivate * *)
0x180033301  mov     ebx, eax
0x180033303  test    eax, eax
0x180033305  js      loc_1800333A7
0x18003330b  xorps   xmm0, xmm0
0x18003330e  movups  [rbp+var_18], xmm0
0x180033312  mov     rcx, [rbp+var_20]
0x180033316  mov     rax, [rcx]
0x180033319  lea     rdx, [rbp+var_18]
0x18003331d  mov     rax, [rax+28h]
0x180033321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033326  mov     ebx, eax
0x180033328  test    eax, eax
0x18003332a  js      short loc_1800333A7
0x18003332c  mov     [rbp+var_28], 0
0x180033334  lea     rax, [rbp+var_28]
0x180033338  mov     [rsp+60h+ppv], rax; ppv
0x18003333d  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x180033344  xor     edx, edx; pUnkOuter
0x180033346  lea     r8d, [rdx+4]; dwClsContext
0x18003334a  lea     rcx, CLSID_CNetworkListManager; rclsid
0x180033351  call    cs:__imp_CoCreateInstance
0x180033357  mov     ebx, eax
0x180033359  test    eax, eax
0x18003335b  js      short loc_18003339E
0x18003335d  mov     [rbp+var_30], 0
0x180033365  mov     rcx, [rbp+var_28]
0x180033369  mov     rax, [rcx]
0x18003336c  lea     r8, [rbp+var_30]
0x180033370  lea     rdx, [rbp+var_18]
0x180033374  mov     rax, [rax+30h]
0x180033378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003337d  mov     ebx, eax
0x18003337f  test    eax, eax
0x180033381  js      short loc_180033395
0x180033383  mov     r8, rdi; struct INetwork **
0x180033386  mov     rdx, [rbp+var_30]; struct INetworkPrivate *
0x18003338a  mov     rcx, [rsi+48h]; struct IGlobalInterfaceTable *
0x18003338e  call    ?CreateInstance@PublicNetwork@@SAJPEAUIGlobalInterfaceTable@@PEAUINetworkPrivate@@PEAPEAUINetwork@@@Z; PublicNetwork::CreateInstance(IGlobalInterfaceTable *,INetworkPrivate *,INetwork * *)
0x180033393  mov     ebx, eax
0x180033395  lea     rcx, [rbp+var_30]
0x180033399  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003339e  lea     rcx, [rbp+var_28]
0x1800333a2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800333a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333ae  cmp     rcx, r12
0x1800333b1  jz      short loc_1800333D1
0x1800333b3  test    byte ptr [rcx+1Ch], 8
0x1800333b7  jz      short loc_1800333D1
0x1800333b9  mov     edx, 11h
0x1800333be  mov     r9d, ebx
0x1800333c1  lea     r8, WPP_cbe8f8d8b9e533271e4839292fb068f7_Traceguids
0x1800333c8  mov     rcx, [rcx+10h]
0x1800333cc  call    WPP_SF_d
0x1800333d1  lea     rcx, [rbp+var_20]
0x1800333d5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800333da  mov     eax, ebx
0x1800333dc  mov     rcx, [rbp+var_8]
0x1800333e0  xor     rcx, rsp; StackCookie
0x1800333e3  call    __security_check_cookie
0x1800333e8  lea     r11, [rsp+60h+var_s0]
0x1800333ed  mov     rbx, [r11+30h]
0x1800333f1  mov     rsi, [r11+38h]
0x1800333f5  mov     rsp, r11
0x1800333f8  pop     r12
0x1800333fa  pop     rdi
0x1800333fb  pop     rbp
0x1800333fc  retn
```
