# RpcSrvRequestCachedParamsEx

- ea: `0x180027540`
- end: `0x1800276a4`
- name: `RpcSrvRequestCachedParamsEx`
- size: `356`
- prototype: `__int64 __fastcall(_WORD *, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x18000a260`
- `0x18000a430`
- `0x18000a4c0`
- `0x18000b1e0`
- `0x18000bb2c`
- `0x180027540`
- `0x180029544`
- `0x1800322c0`
- `0x1800338c0`

## pseudocode

```c
__int64 __fastcall RpcSrvRequestCachedParamsEx(_WORD *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  int v7; // r12d
  int v10; // r13d
  CRpcWatchDog *v11; // rcx
  unsigned int v12; // ebx
  int v13; // r8d
  int v14; // esi
  CRpcWatchDog *v15; // rcx
  volatile signed __int32 *v17; // [rsp+40h] [rbp-78h] BYREF
  _OWORD v18[7]; // [rsp+48h] [rbp-70h] BYREF

  v17 = 0;
  memset(v18, 0, 32);
  v7 = a3;
  v10 = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_Dqqq(a1, a2, a3, (unsigned int)a3, a4, a5, a6);
  v12 = RpcValidateRequests(a1, 1u);
  if ( !v12 )
  {
    if ( a2 && a5 && *(_QWORD *)(a5 + 8) && *(_DWORD *)a5 && a6 )
    {
      v14 = 0;
      *(_QWORD *)&v18[0] = RpcSrvRequestCachedParamsEx;
      CRpcWatchDog::AddEntry(v11, (struct _WatchDogEntry *)v18, v13);
      v10 = 1;
      if ( a4 && *(_DWORD *)(a4 + 16) && *(_QWORD *)(a4 + 8) )
        v14 = a4;
      v12 = Dhcpv6FindAndRefContext(a2, &v17);
      if ( !v12 )
        v12 = RequestCachedParams_New((_DWORD)v17, v7, v14, a5, a6);
    }
    else
    {
      v12 = 87;
    }
  }
  v15 = (CRpcWatchDog *)v17;
  if ( v17 )
  {
    if ( _InterlockedExchangeAdd(v17 + 4, 0xFFFFFFFF) == 1 )
      Dhcpv6DestroyContextEx(v17);
    v17 = 0;
  }
  if ( v10 )
    CRpcWatchDog::RemoveEntry(v15, (struct _WatchDogEntry *)v18);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 55, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x180027540  push    rbx
0x180027542  push    rbp
0x180027543  push    rsi
0x180027544  push    rdi
0x180027545  push    r12
0x180027547  push    r13
0x180027549  push    r14
0x18002754b  push    r15
0x18002754d  sub     rsp, 78h
0x180027551  xorps   xmm0, xmm0
0x180027554  mov     [rsp+0B8h+var_78], 0
0x18002755d  movups  [rsp+0B8h+var_70], xmm0
0x180027562  mov     rbp, r9
0x180027565  mov     r12d, r8d
0x180027568  movups  [rsp+0B8h+var_60], xmm0
0x18002756d  mov     r15, rdx
0x180027570  mov     rbx, rcx
0x180027573  xor     r13d, r13d
0x180027576  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002757d  mov     r14, [rsp+0B8h+arg_28]
0x180027585  mov     rdi, [rsp+0B8h+arg_20]
0x18002758d  jz      short loc_1800275A6
0x18002758f  mov     [rsp+0B8h+var_88], r14
0x180027594  mov     [rsp+0B8h+var_90], rdi
0x180027599  mov     [rsp+0B8h+var_98], r9
0x18002759e  mov     r9d, r8d
0x1800275a1  call    WPP_SF_Dqqq
0x1800275a6  mov     edx, 1
0x1800275ab  mov     rcx, rbx
0x1800275ae  call    RpcValidateRequests
0x1800275b3  mov     ebx, eax
0x1800275b5  test    eax, eax
0x1800275b7  jnz     short loc_180027635
0x1800275b9  test    r15, r15
0x1800275bc  jnz     short loc_1800275C5
0x1800275be  mov     ebx, 57h ; 'W'
0x1800275c3  jmp     short loc_180027635
0x1800275c5  test    rdi, rdi
0x1800275c8  jz      short loc_1800275BE
0x1800275ca  cmp     [rdi+8], r13
0x1800275ce  jz      short loc_1800275BE
0x1800275d0  cmp     [rdi], r13d
0x1800275d3  jz      short loc_1800275BE
0x1800275d5  test    r14, r14
0x1800275d8  jz      short loc_1800275BE
0x1800275da  lea     rax, RpcSrvRequestCachedParamsEx
0x1800275e1  xor     esi, esi
0x1800275e3  lea     rdx, [rsp+0B8h+var_70]; struct _WatchDogEntry *
0x1800275e8  mov     qword ptr [rsp+0B8h+var_70], rax
0x1800275ed  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x1800275f2  lea     r13d, [rsi+1]
0x1800275f6  test    rbp, rbp
0x1800275f9  jz      short loc_180027608
0x1800275fb  cmp     [rbp+10h], esi
0x1800275fe  jz      short loc_180027608
0x180027600  cmp     [rbp+8], rsi
0x180027604  cmovnz  rsi, rbp
0x180027608  lea     rdx, [rsp+0B8h+var_78]
0x18002760d  mov     rcx, r15
0x180027610  call    Dhcpv6FindAndRefContext
0x180027615  mov     ebx, eax
0x180027617  test    eax, eax
0x180027619  jnz     short loc_180027635
0x18002761b  mov     rcx, [rsp+0B8h+var_78]
0x180027620  mov     r9, rdi
0x180027623  mov     r8, rsi
0x180027626  mov     [rsp+0B8h+var_98], r14
0x18002762b  mov     edx, r12d
0x18002762e  call    RequestCachedParams_New
0x180027633  mov     ebx, eax
0x180027635  mov     rcx, [rsp+0B8h+var_78]
0x18002763a  test    rcx, rcx
0x18002763d  jz      short loc_18002765F
0x18002763f  or      eax, 0FFFFFFFFh
0x180027642  lock xadd [rcx+10h], eax
0x180027647  cmp     eax, 1
0x18002764a  jnz     short loc_180027656
0x18002764c  mov     rcx, [rsp+0B8h+var_78]
0x180027651  call    Dhcpv6DestroyContextEx
0x180027656  mov     [rsp+0B8h+var_78], 0
0x18002765f  test    r13d, r13d
0x180027662  jz      short loc_18002766E
0x180027664  lea     rdx, [rsp+0B8h+var_70]; struct _WatchDogEntry *
0x180027669  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002766e  test    byte ptr cs:xmmword_1800423E0, 10h
0x180027675  jz      short loc_180027690
0x180027677  mov     edx, 37h ; '7'
0x18002767c  lea     r8, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids
0x180027683  mov     ecx, 404h
0x180027688  mov     r9d, ebx
0x18002768b  call    WPP_SF_D
0x180027690  mov     eax, ebx
0x180027692  add     rsp, 78h
0x180027696  pop     r15
0x180027698  pop     r14
0x18002769a  pop     r13
0x18002769c  pop     r12
0x18002769e  pop     rdi
0x18002769f  pop     rsi
0x1800276a0  pop     rbp
0x1800276a1  pop     rbx
0x1800276a2  retn
```
