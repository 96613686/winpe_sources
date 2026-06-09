# RpcSrvMadcapApiStartup_New

- ea: `0x18002a0a8`
- end: `0x18002a189`
- name: `RpcSrvMadcapApiStartup_New`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180029fb0`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x18002a0a8`
- `0x180036d60`
- `0x18004d1a0`
- `0x18004d4c0`
- `0x18004dd28`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18002a10c`
- `RPCRT4!RpcImpersonateClient` at `0x18002a10c`
- `RPCRT4!RpcRevertToSelf` at `0x18002a0ec`
- `RPCRT4!RpcRevertToSelf` at `0x18002a122`
- `RPCRT4!RpcRevertToSelf` at `0x18002a0ec`
- `RPCRT4!RpcRevertToSelf` at `0x18002a122`

## pseudocode

```c
__int64 __fastcall RpcSrvMadcapApiStartup_New(CRpcWatchDog *a1, __int64 a2, int a3)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  CRpcWatchDog *v6; // rcx
  _OWORD v8[2]; // [rsp+30h] [rbp-28h] BYREF

  memset(v8, 0, sizeof(v8));
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 220, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, a2);
  if ( a2 )
  {
    *(_QWORD *)&v8[0] = RpcSrvMadcapApiStartup;
    CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)v8, a3);
    v5 = RpcImpersonateClient(0);
    v4 = v5;
    if ( v5 )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_Dd(1025, 221, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v5, v5);
    }
    else
    {
      v4 = ApiStartup(a2);
      RpcRevertToSelf();
    }
    CRpcWatchDog::RemoveEntry(v6, (struct _WatchDogEntry *)v8);
  }
  else
  {
    v4 = 87;
    RpcRevertToSelf();
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 222, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18002a0a8  mov     [rsp+arg_0], rbx
0x18002a0ad  push    rdi
0x18002a0ae  sub     rsp, 50h
0x18002a0b2  xorps   xmm0, xmm0
0x18002a0b5  mov     rdi, rdx
0x18002a0b8  movups  [rsp+58h+var_28], xmm0
0x18002a0bd  movups  [rsp+58h+var_18], xmm0
0x18002a0c2  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002a0c9  jz      short loc_18002A0E4
0x18002a0cb  mov     edx, 0DCh
0x18002a0d0  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a0d7  mov     ecx, 404h
0x18002a0dc  mov     r9, rdi
0x18002a0df  call    WPP_SF_q
0x18002a0e4  test    rdi, rdi
0x18002a0e7  jnz     short loc_18002A0F4
0x18002a0e9  lea     ebx, [rdi+57h]
0x18002a0ec  call    cs:__imp_RpcRevertToSelf
0x18002a0f2  jmp     short loc_18002A15A
0x18002a0f4  lea     rax, RpcSrvMadcapApiStartup
0x18002a0fb  lea     rdx, [rsp+58h+var_28]; struct _WatchDogEntry *
0x18002a100  mov     qword ptr [rsp+58h+var_28], rax
0x18002a105  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002a10a  xor     ecx, ecx; BindingHandle
0x18002a10c  call    cs:__imp_RpcImpersonateClient
0x18002a112  mov     ebx, eax
0x18002a114  test    eax, eax
0x18002a116  jnz     short loc_18002A12A
0x18002a118  mov     rcx, rdi
0x18002a11b  call    ApiStartup
0x18002a120  mov     ebx, eax
0x18002a122  call    cs:__imp_RpcRevertToSelf
0x18002a128  jmp     short loc_18002A150
0x18002a12a  test    byte ptr cs:xmmword_1800616A0, 2
0x18002a131  jz      short loc_18002A150
0x18002a133  mov     edx, 0DDh
0x18002a138  mov     [rsp+58h+var_38], eax
0x18002a13c  mov     ecx, 401h
0x18002a141  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a148  mov     r9d, eax
0x18002a14b  call    WPP_SF_Dd
0x18002a150  lea     rdx, [rsp+58h+var_28]; struct _WatchDogEntry *
0x18002a155  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002a15a  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002a161  jz      short loc_18002A17C
0x18002a163  mov     edx, 0DEh
0x18002a168  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a16f  mov     ecx, 404h
0x18002a174  mov     r9d, ebx
0x18002a177  call    WPP_SF_D
0x18002a17c  mov     eax, ebx
0x18002a17e  mov     rbx, [rsp+58h+arg_0]
0x18002a183  add     rsp, 50h
0x18002a187  pop     rdi
0x18002a188  retn
```
