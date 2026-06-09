# CHNBridge::AddMember(IHNetConnection *,IHNetBridgedConnection * *,unsigned __int64)

- ea: `0x180026300`
- end: `0x180026468`
- name: `?AddMember@CHNBridge@@UEAAJPEAUIHNetConnection@@PEAPEAUIHNetBridgedConnection@@_K@Z`
- size: `360`
- prototype: `__int64 __fastcall(CHNBridge *this, struct IHNetConnection *, struct IHNetBridgedConnection **, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001e7f0`
- `0x180021458`
- `0x180025904`
- `0x180026300`
- `0x18002ab30`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800263c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800263c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026404`

## pseudocode

```c
__int64 __fastcall CHNBridge::AddMember(
        CHNBridge *this,
        struct IHNetConnection *a2,
        struct IHNetBridgedConnection **a3,
        __int64 a4)
{
  __int64 result; // rax
  CHNetConn *v7; // rsi
  int v8; // eax
  __int64 v9; // rax
  int v10; // ebx
  __int64 v11; // rax
  int v12; // [rsp+20h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-38h] BYREF
  LPVOID v14[2]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v15; // [rsp+40h] [rbp-20h] BYREF

  if ( a4 )
    return 2147942487LL;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( !a2 )
    return 2147942487LL;
  v7 = (CHNBridge *)((char *)this - 152);
  v8 = *((_DWORD *)this + 2);
  v12 = v8;
  if ( v8 == 2 )
  {
    v12 = 0;
    goto LABEL_8;
  }
  if ( v8 != 1 )
  {
LABEL_8:
    if ( CHNetConn::ProhibitedByPolicy((CHNBridge *)((char *)this - 152), 0x34u) )
      return 2147942405LL;
  }
  v9 = *(_QWORD *)a2;
  pv = 0;
  v10 = (*(__int64 (__fastcall **)(struct IHNetConnection *, LPVOID *))(v9 + 56))(a2, &pv);
  if ( !v10 )
  {
    UpdatePropertiesWithNetcon2(a2, (struct tagHNET_CONN_PROPERTIES *)pv);
    if ( !*((_BYTE *)pv + 6) )
      v10 = -2147418113;
    CoTaskMemFree(pv);
  }
  if ( v10 < 0 )
    return (unsigned int)v10;
  v11 = *(_QWORD *)a2;
  v14[0] = 0;
  v15 = 0;
  result = (*(__int64 (__fastcall **)(struct IHNetConnection *, LPVOID *))(v11 + 32))(a2, v14);
  if ( (int)result >= 0 )
  {
    v15 = *(_OWORD *)v14[0];
    CoTaskMemFree(v14[0]);
    v14[0] = &v12;
    v14[1] = &v15;
    result = wil::ResultFromException__lambda_bf7e30a7e824391af5decde2e4f8fce9___(v14);
    if ( (int)result >= 0 )
    {
      (*(void (__fastcall **)(struct IHNetConnection *, GUID *, struct IHNetBridgedConnection **))(*(_QWORD *)a2 + 64LL))(
        a2,
        &GUID_85d18b76_3032_11d4_9348_00c04f8eeb71,
        a3);
      CHNetConn::UpdateNetman(v7);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180026300  push    rbp
0x180026302  push    rbx
0x180026303  push    rsi
0x180026304  push    rdi
0x180026305  push    r14
0x180026307  mov     rbp, rsp
0x18002630a  sub     rsp, 60h
0x18002630e  mov     rax, cs:__security_cookie
0x180026315  xor     rax, rsp
0x180026318  mov     [rbp+var_10], rax
0x18002631c  mov     r14, r8
0x18002631f  mov     rdi, rdx
0x180026322  test    r9, r9
0x180026325  jnz     loc_18002644C
0x18002632b  test    r8, r8
0x18002632e  jnz     short loc_18002633A
0x180026330  mov     eax, 80004003h
0x180026335  jmp     loc_180026451
0x18002633a  mov     qword ptr [r8], 0
0x180026341  test    rdi, rdi
0x180026344  jz      loc_18002644C
0x18002634a  lea     rsi, [rcx-98h]
0x180026351  mov     eax, [rsi+0A0h]
0x180026357  mov     [rbp+var_40], eax
0x18002635a  cmp     eax, 2
0x18002635d  jnz     short loc_180026368
0x18002635f  mov     [rbp+var_40], 0
0x180026366  jmp     short loc_18002636D
0x180026368  cmp     eax, 1
0x18002636b  jz      short loc_180026388
0x18002636d  mov     edx, 34h ; '4'; unsigned int
0x180026372  mov     rcx, rsi; this
0x180026375  call    ?ProhibitedByPolicy@CHNetConn@@IEAAEK@Z; CHNetConn::ProhibitedByPolicy(ulong)
0x18002637a  test    al, al
0x18002637c  jz      short loc_180026388
0x18002637e  mov     eax, 80070005h
0x180026383  jmp     loc_180026451
0x180026388  mov     rax, [rdi]
0x18002638b  lea     rdx, [rbp+pv]
0x18002638f  mov     rcx, rdi
0x180026392  mov     [rbp+pv], 0
0x18002639a  mov     rax, [rax+38h]
0x18002639e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263a3  mov     ebx, eax
0x1800263a5  test    eax, eax
0x1800263a7  jnz     short loc_1800263CA
0x1800263a9  mov     rdx, [rbp+pv]; struct tagHNET_CONN_PROPERTIES *
0x1800263ad  mov     rcx, rdi; struct IHNetConnection *
0x1800263b0  call    ?UpdatePropertiesWithNetcon2@@YAJPEAUIHNetConnection@@PEAUtagHNET_CONN_PROPERTIES@@@Z; UpdatePropertiesWithNetcon2(IHNetConnection *,tagHNET_CONN_PROPERTIES *)
0x1800263b5  mov     rcx, [rbp+pv]; pv
0x1800263b9  mov     eax, 8000FFFFh
0x1800263be  cmp     [rcx+6], bl
0x1800263c1  cmovz   ebx, eax
0x1800263c4  call    cs:__imp_CoTaskMemFree
0x1800263ca  test    ebx, ebx
0x1800263cc  jns     short loc_1800263D2
0x1800263ce  mov     eax, ebx
0x1800263d0  jmp     short loc_180026451
0x1800263d2  mov     rax, [rdi]
0x1800263d5  lea     rdx, [rbp+var_30]
0x1800263d9  xorps   xmm0, xmm0
0x1800263dc  mov     [rbp+var_30], 0
0x1800263e4  mov     rcx, rdi
0x1800263e7  movups  [rbp+var_20], xmm0
0x1800263eb  mov     rax, [rax+20h]
0x1800263ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263f4  test    eax, eax
0x1800263f6  js      short loc_180026451
0x1800263f8  mov     rcx, [rbp+var_30]; pv
0x1800263fc  movups  xmm0, xmmword ptr [rcx]
0x1800263ff  movdqu  [rbp+var_20], xmm0
0x180026404  call    cs:__imp_CoTaskMemFree
0x18002640a  lea     rax, [rbp+var_40]
0x18002640e  mov     [rbp+var_30], rax
0x180026412  lea     rcx, [rbp+var_30]
0x180026416  lea     rax, [rbp+var_20]
0x18002641a  mov     [rbp+var_28], rax
0x18002641e  call    wil__ResultFromException__lambda_bf7e30a7e824391af5decde2e4f8fce9___
0x180026423  test    eax, eax
0x180026425  js      short loc_180026451
0x180026427  mov     rax, [rdi]
0x18002642a  lea     rdx, _GUID_85d18b76_3032_11d4_9348_00c04f8eeb71
0x180026431  mov     r8, r14
0x180026434  mov     rcx, rdi
0x180026437  mov     rax, [rax+40h]
0x18002643b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026440  mov     rcx, rsi; this
0x180026443  call    ?UpdateNetman@CHNetConn@@IEAAJXZ; CHNetConn::UpdateNetman(void)
0x180026448  xor     eax, eax
0x18002644a  jmp     short loc_180026451
0x18002644c  mov     eax, 80070057h
0x180026451  mov     rcx, [rbp+var_10]
0x180026455  xor     rcx, rsp; StackCookie
0x180026458  call    __security_check_cookie
0x18002645d  add     rsp, 60h
0x180026461  pop     r14
0x180026463  pop     rdi
0x180026464  pop     rsi
0x180026465  pop     rbx
0x180026466  pop     rbp
0x180026467  retn
```
