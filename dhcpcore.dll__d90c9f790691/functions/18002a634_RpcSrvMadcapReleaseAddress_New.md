# RpcSrvMadcapReleaseAddress_New

- ea: `0x18002a634`
- end: `0x18002a705`
- name: `RpcSrvMadcapReleaseAddress_New`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18002a540`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x18002a634`
- `0x180036ef0`
- `0x18004aa84`
- `0x18004d1a0`
- `0x18004dd28`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18002a684`
- `RPCRT4!RpcImpersonateClient` at `0x18002a684`
- `RPCRT4!RpcRevertToSelf` at `0x18002a6a0`
- `RPCRT4!RpcRevertToSelf` at `0x18002a6a0`

## pseudocode

```c
__int64 __fastcall RpcSrvMadcapReleaseAddress_New(CRpcWatchDog *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int16 v4; // bp
  unsigned int v7; // eax
  CRpcWatchDog *v8; // rcx
  unsigned int v9; // ebx
  __int128 v11; // [rsp+30h] [rbp-48h] BYREF
  __int128 v12; // [rsp+40h] [rbp-38h]

  v4 = a2;
  v11 = 0;
  v12 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_dqq(a1, a2, a3, (unsigned __int16)a2, a3, a4, v11, *((_QWORD *)&v11 + 1), v12, *((_QWORD *)&v12 + 1));
  *(_QWORD *)&v11 = RpcSrvMadcapReleaseAddress;
  CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)&v11, a3);
  v7 = RpcImpersonateClient(0);
  v9 = v7;
  if ( v7 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_Dd(1025, 257, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v7, v7);
  }
  else
  {
    v9 = ReleaseAddress(v4, a3, a4);
    RpcRevertToSelf();
  }
  CRpcWatchDog::RemoveEntry(v8, (struct _WatchDogEntry *)&v11);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 258, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18002a634  mov     rax, rsp
0x18002a637  push    rbx
0x18002a638  push    rbp
0x18002a639  push    rsi
0x18002a63a  push    rdi
0x18002a63b  sub     rsp, 58h
0x18002a63f  xorps   xmm0, xmm0
0x18002a642  movzx   ebp, dx
0x18002a645  movups  xmmword ptr [rax-48h], xmm0
0x18002a649  mov     rdi, r9
0x18002a64c  mov     rsi, r8
0x18002a64f  movups  xmmword ptr [rax-38h], xmm0
0x18002a653  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002a65a  jz      short loc_18002A66C
0x18002a65c  mov     [rax-50h], rdi
0x18002a660  mov     r9d, ebp
0x18002a663  mov     [rax-58h], r8
0x18002a667  call    WPP_SF_dqq
0x18002a66c  lea     rax, RpcSrvMadcapReleaseAddress
0x18002a673  lea     rdx, [rsp+78h+var_48]; struct _WatchDogEntry *
0x18002a678  mov     qword ptr [rsp+78h+var_48], rax
0x18002a67d  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002a682  xor     ecx, ecx; BindingHandle
0x18002a684  call    cs:__imp_RpcImpersonateClient
0x18002a68a  mov     ebx, eax
0x18002a68c  test    eax, eax
0x18002a68e  jnz     short loc_18002A6A8
0x18002a690  mov     r8, rdi
0x18002a693  mov     rdx, rsi
0x18002a696  movzx   ecx, bp
0x18002a699  call    ReleaseAddress
0x18002a69e  mov     ebx, eax
0x18002a6a0  call    cs:__imp_RpcRevertToSelf
0x18002a6a6  jmp     short loc_18002A6CE
0x18002a6a8  test    byte ptr cs:xmmword_1800616A0, 2
0x18002a6af  jz      short loc_18002A6CE
0x18002a6b1  mov     edx, 101h
0x18002a6b6  mov     [rsp+78h+var_58], eax
0x18002a6ba  mov     ecx, 401h
0x18002a6bf  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a6c6  mov     r9d, eax
0x18002a6c9  call    WPP_SF_Dd
0x18002a6ce  lea     rdx, [rsp+78h+var_48]; struct _WatchDogEntry *
0x18002a6d3  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002a6d8  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002a6df  jz      short loc_18002A6FA
0x18002a6e1  mov     edx, 102h
0x18002a6e6  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a6ed  mov     ecx, 404h
0x18002a6f2  mov     r9d, ebx
0x18002a6f5  call    WPP_SF_D
0x18002a6fa  mov     eax, ebx
0x18002a6fc  add     rsp, 58h
0x18002a700  pop     rdi
0x18002a701  pop     rsi
0x18002a702  pop     rbp
0x18002a703  pop     rbx
0x18002a704  retn
```
