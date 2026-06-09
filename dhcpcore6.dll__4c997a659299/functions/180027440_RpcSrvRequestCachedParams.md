# RpcSrvRequestCachedParams

- ea: `0x180027440`
- end: `0x18002752f`
- name: `RpcSrvRequestCachedParams`
- size: `239`
- prototype: `__int64 __fastcall(_WORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000a260`
- `0x18000a430`
- `0x18000a4c0`
- `0x18000b1e0`
- `0x18000bb2c`
- `0x180027440`
- `0x18002942c`

## pseudocode

```c
__int64 __fastcall RpcSrvRequestCachedParams(_WORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // r14d
  CRpcWatchDog *v8; // rcx
  unsigned int v9; // ebx
  int v10; // r8d
  CRpcWatchDog *v11; // rcx
  volatile signed __int32 *v13; // [rsp+20h] [rbp-58h] BYREF
  _OWORD v14[5]; // [rsp+28h] [rbp-50h] BYREF

  v13 = 0;
  v5 = 0;
  memset(v14, 0, 32);
  v9 = RpcValidateRequests(a1, 1u);
  if ( !v9 )
  {
    if ( a2 && *(_QWORD *)(a4 + 8) && *(_DWORD *)a4 )
    {
      *(_QWORD *)&v14[0] = RpcSrvRequestCachedParams;
      CRpcWatchDog::AddEntry(v8, (struct _WatchDogEntry *)v14, v10);
      v5 = 1;
      if ( a3 && (!*(_DWORD *)(a3 + 16) || !*(_QWORD *)(a3 + 8)) )
        a3 = 0;
      v9 = Dhcpv6FindAndRefContext(a2, &v13);
      if ( !v9 )
        v9 = RequestCachedParams(v13, a3, a4);
    }
    else
    {
      v9 = 87;
    }
  }
  v11 = (CRpcWatchDog *)v13;
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 4, 0xFFFFFFFF) == 1 )
      Dhcpv6DestroyContextEx(v13);
    v13 = 0;
  }
  if ( v5 )
    CRpcWatchDog::RemoveEntry(v11, (struct _WatchDogEntry *)v14);
  return v9;
}

```

## disassembly

```asm
0x180027440  push    rbx
0x180027442  push    rbp
0x180027443  push    rsi
0x180027444  push    rdi
0x180027445  push    r14
0x180027447  sub     rsp, 50h
0x18002744b  xorps   xmm0, xmm0
0x18002744e  mov     [rsp+78h+var_58], 0
0x180027457  mov     rbp, rdx
0x18002745a  xor     r14d, r14d
0x18002745d  mov     rsi, r9
0x180027460  mov     rdi, r8
0x180027463  movups  [rsp+78h+var_50], xmm0
0x180027468  lea     edx, [r14+1]
0x18002746c  movups  [rsp+78h+var_40], xmm0
0x180027471  call    RpcValidateRequests
0x180027476  mov     ebx, eax
0x180027478  test    eax, eax
0x18002747a  jnz     short loc_1800274E8
0x18002747c  test    rbp, rbp
0x18002747f  jnz     short loc_180027488
0x180027481  mov     ebx, 57h ; 'W'
0x180027486  jmp     short loc_1800274E8
0x180027488  cmp     [rsi+8], r14
0x18002748c  jz      short loc_180027481
0x18002748e  cmp     [rsi], r14d
0x180027491  jz      short loc_180027481
0x180027493  lea     rax, RpcSrvRequestCachedParams
0x18002749a  lea     rdx, [rsp+78h+var_50]; struct _WatchDogEntry *
0x18002749f  mov     qword ptr [rsp+78h+var_50], rax
0x1800274a4  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x1800274a9  mov     r14d, 1
0x1800274af  test    rdi, rdi
0x1800274b2  jz      short loc_1800274C3
0x1800274b4  cmp     dword ptr [rdi+10h], 0
0x1800274b8  jz      short loc_1800274C1
0x1800274ba  cmp     qword ptr [rdi+8], 0
0x1800274bf  jnz     short loc_1800274C3
0x1800274c1  xor     edi, edi
0x1800274c3  lea     rdx, [rsp+78h+var_58]
0x1800274c8  mov     rcx, rbp
0x1800274cb  call    Dhcpv6FindAndRefContext
0x1800274d0  mov     ebx, eax
0x1800274d2  test    eax, eax
0x1800274d4  jnz     short loc_1800274E8
0x1800274d6  mov     rcx, [rsp+78h+var_58]
0x1800274db  mov     r8, rsi
0x1800274de  mov     rdx, rdi
0x1800274e1  call    RequestCachedParams
0x1800274e6  mov     ebx, eax
0x1800274e8  mov     rcx, [rsp+78h+var_58]
0x1800274ed  test    rcx, rcx
0x1800274f0  jz      short loc_180027512
0x1800274f2  or      eax, 0FFFFFFFFh
0x1800274f5  lock xadd [rcx+10h], eax
0x1800274fa  cmp     eax, 1
0x1800274fd  jnz     short loc_180027509
0x1800274ff  mov     rcx, [rsp+78h+var_58]
0x180027504  call    Dhcpv6DestroyContextEx
0x180027509  mov     [rsp+78h+var_58], 0
0x180027512  test    r14d, r14d
0x180027515  jz      short loc_180027521
0x180027517  lea     rdx, [rsp+78h+var_50]; struct _WatchDogEntry *
0x18002751c  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x180027521  mov     eax, ebx
0x180027523  add     rsp, 50h
0x180027527  pop     r14
0x180027529  pop     rdi
0x18002752a  pop     rsi
0x18002752b  pop     rbp
0x18002752c  pop     rbx
0x18002752d  retn
```
