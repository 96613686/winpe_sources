# CFwProfile::GetNetworkList(CRefObjectList<INetworkPrivate *> &)

- ea: `0x18001eaac`
- end: `0x18001ec6e`
- name: `?GetNetworkList@CFwProfile@@QEAAJAEAV?$CRefObjectList@PEAUINetworkPrivate@@@@@Z`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800212e4`

## callees

- `0x180008b30`
- `0x180009040`
- `0x180009924`
- `0x18000994c`
- `0x180009a80`
- `0x18000d7cc`
- `0x18001c31c`
- `0x18001eaac`
- `0x180030ea0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001eb45`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001eb45`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFwProfile::GetNetworkList(__int64 a1, __int64 *a2)
{
  HRESULT v4; // eax
  __int64 *v5; // rcx
  unsigned int v6; // ebx
  CFwCplLua *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rax
  LPVOID ppv; // [rsp+30h] [rbp-40h] BYREF
  __int64 v12; // [rsp+38h] [rbp-38h] BYREF
  __int64 v13; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v14[16]; // [rsp+48h] [rbp-28h] BYREF
  __int128 v15; // [rsp+58h] [rbp-18h] BYREF

  v12 = 0;
  ppv = 0;
  v15 = 0;
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_3eafb88137b43a797d412ab5cad0a360_Traceguids);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    (__int64)v14,
    (struct _RTL_CRITICAL_SECTION *)(a1 + 24));
  v4 = CoCreateInstance(&CLSID_CNetworkListManager, 0, 0x17u, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, &ppv);
  v6 = v4;
  if ( v4 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control )
      goto LABEL_23;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v8 = 28;
LABEL_18:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_3eafb88137b43a797d412ab5cad0a360_Traceguids, (unsigned int)v4);
    goto LABEL_19;
  }
  v13 = *(_QWORD *)(a1 + 120);
  if ( !v13 )
  {
LABEL_19:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_20;
  }
  while ( 1 )
  {
    v15 = *(_OWORD *)ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::GetNext(
                       v5,
                       &v13);
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int64 *))(*(_QWORD *)ppv + 48LL))(ppv, &v15, &v12);
    v6 = v4;
    if ( v4 < 0 )
      break;
    v9 = ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::NewNode(a2, &v12, a2[1]);
    v5 = (__int64 *)a2[1];
    if ( v5 )
      *v5 = v9;
    else
      *a2 = v9;
    a2[1] = v9;
    if ( !v13 )
      goto LABEL_19;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_20:
      if ( v7 != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)v7 + 2), 30, WPP_3eafb88137b43a797d412ab5cad0a360_Traceguids, v6);
      goto LABEL_23;
    }
    v8 = 29;
    goto LABEL_18;
  }
LABEL_23:
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)v14);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return v6;
}

```

## disassembly

```asm
0x18001eaac  mov     [rsp-18h+arg_10], rbx
0x18001eab1  mov     [rsp-18h+arg_18], rsi
0x18001eab6  push    rbp
0x18001eab7  push    rdi
0x18001eab8  push    r15
0x18001eaba  mov     rbp, rsp
0x18001eabd  sub     rsp, 70h
0x18001eac1  mov     rax, cs:__security_cookie
0x18001eac8  xor     rax, rsp
0x18001eacb  mov     [rbp+var_8], rax
0x18001eacf  mov     rdi, rdx
0x18001ead2  mov     rsi, rcx
0x18001ead5  mov     [rbp+var_38], 0
0x18001eadd  mov     [rbp+var_40], 0
0x18001eae5  xorps   xmm0, xmm0
0x18001eae8  movups  [rbp+var_18], xmm0
0x18001eaec  lea     r15, WPP_GLOBAL_Control
0x18001eaf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eafa  cmp     rcx, r15
0x18001eafd  jz      short loc_18001EB1A
0x18001eaff  test    byte ptr [rcx+1Ch], 8
0x18001eb03  jz      short loc_18001EB1A
0x18001eb05  mov     edx, 1Bh
0x18001eb0a  lea     r8, WPP_3eafb88137b43a797d412ab5cad0a360_Traceguids
0x18001eb11  mov     rcx, [rcx+10h]
0x18001eb15  call    WPP_SF_
0x18001eb1a  lea     rdx, [rsi+18h]
0x18001eb1e  lea     rcx, [rbp+var_28]
0x18001eb22  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18001eb27  nop
0x18001eb28  lea     rax, [rbp+var_40]
0x18001eb2c  mov     [rsp+70h+ppv], rax; ppv
0x18001eb31  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x18001eb38  xor     edx, edx; pUnkOuter
0x18001eb3a  lea     r8d, [rdx+17h]; dwClsContext
0x18001eb3e  lea     rcx, CLSID_CNetworkListManager; rclsid
0x18001eb45  call    cs:__imp_CoCreateInstance
0x18001eb4b  mov     ebx, eax
0x18001eb4d  test    eax, eax
0x18001eb4f  jns     short loc_18001EB75
0x18001eb51  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb58  cmp     rcx, r15
0x18001eb5b  jz      loc_18001EC38
0x18001eb61  test    byte ptr [rcx+1Ch], 1
0x18001eb65  jz      loc_18001EC14
0x18001eb6b  mov     edx, 1Ch
0x18001eb70  jmp     loc_18001EBFA
0x18001eb75  mov     rax, [rsi+78h]
0x18001eb79  mov     [rbp+var_30], rax
0x18001eb7d  test    rax, rax
0x18001eb80  jz      loc_18001EC0D
0x18001eb86  lea     rdx, [rbp+var_30]
0x18001eb8a  call    ?GetNext@?$CAtlList@PEAVCFwProfileViewUpdate@@V?$CElementTraits@PEAVCFwProfileViewUpdate@@@ATL@@@ATL@@QEAAAEAPEAVCFwProfileViewUpdate@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::GetNext(__POSITION * &)
0x18001eb8f  movups  xmm0, xmmword ptr [rax]
0x18001eb92  movdqu  [rbp+var_18], xmm0
0x18001eb97  mov     rcx, [rbp+var_40]
0x18001eb9b  mov     rax, [rcx]
0x18001eb9e  lea     r8, [rbp+var_38]
0x18001eba2  lea     rdx, [rbp+var_18]
0x18001eba6  mov     rax, [rax+30h]
0x18001ebaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebaf  mov     ebx, eax
0x18001ebb1  test    eax, eax
0x18001ebb3  js      short loc_18001EBE3
0x18001ebb5  mov     r8, [rdi+8]
0x18001ebb9  lea     rdx, [rbp+var_38]
0x18001ebbd  mov     rcx, rdi
0x18001ebc0  call    ?NewNode@?$CAtlList@PEAVCFwProfileViewUpdate@@V?$CElementTraits@PEAVCFwProfileViewUpdate@@@ATL@@@ATL@@AEAAPEAVCNode@12@AEBQEAVCFwProfileViewUpdate@@PEAV312@1@Z; ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::NewNode(CFwProfileViewUpdate * const &,ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::CNode *,ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::CNode *)
0x18001ebc5  mov     rcx, [rdi+8]
0x18001ebc9  test    rcx, rcx
0x18001ebcc  jz      short loc_18001EBD3
0x18001ebce  mov     [rcx], rax
0x18001ebd1  jmp     short loc_18001EBD6
0x18001ebd3  mov     [rdi], rax
0x18001ebd6  mov     [rdi+8], rax
0x18001ebda  cmp     [rbp+var_30], 0
0x18001ebdf  jnz     short loc_18001EB86
0x18001ebe1  jmp     short loc_18001EC0D
0x18001ebe3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ebea  cmp     rcx, r15
0x18001ebed  jz      short loc_18001EC38
0x18001ebef  test    byte ptr [rcx+1Ch], 1
0x18001ebf3  jz      short loc_18001EC14
0x18001ebf5  mov     edx, 1Dh
0x18001ebfa  mov     r9d, eax
0x18001ebfd  lea     r8, WPP_3eafb88137b43a797d412ab5cad0a360_Traceguids
0x18001ec04  mov     rcx, [rcx+10h]
0x18001ec08  call    WPP_SF_d
0x18001ec0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec14  cmp     rcx, r15
0x18001ec17  jz      short loc_18001EC38
0x18001ec19  test    byte ptr [rcx+1Ch], 8
0x18001ec1d  jz      short loc_18001EC38
0x18001ec1f  mov     edx, 1Eh
0x18001ec24  mov     r9d, ebx
0x18001ec27  lea     r8, WPP_3eafb88137b43a797d412ab5cad0a360_Traceguids
0x18001ec2e  mov     rcx, [rcx+10h]
0x18001ec32  call    WPP_SF_d
0x18001ec37  nop
0x18001ec38  lea     rcx, [rbp+var_28]
0x18001ec3c  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001ec41  nop
0x18001ec42  lea     rcx, [rbp+var_40]
0x18001ec46  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ec4b  mov     eax, ebx
0x18001ec4d  mov     rcx, [rbp+var_8]
0x18001ec51  xor     rcx, rsp; StackCookie
0x18001ec54  call    __security_check_cookie
0x18001ec59  lea     r11, [rsp+70h+var_s0]
0x18001ec5e  mov     rbx, [r11+30h]
0x18001ec62  mov     rsi, [r11+38h]
0x18001ec66  mov     rsp, r11
0x18001ec69  pop     r15
0x18001ec6b  pop     rdi
0x18001ec6c  pop     rbp
0x18001ec6d  retn
```
