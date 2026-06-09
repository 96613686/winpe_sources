# RpcSrvMadcapRenewAddress_New

- ea: `0x18002a818`
- end: `0x18002a901`
- name: `RpcSrvMadcapRenewAddress_New`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18002a710`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x18002a818`
- `0x18003708c`
- `0x18004aae8`
- `0x18004d1a0`
- `0x18004dd28`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18002a87b`
- `RPCRT4!RpcImpersonateClient` at `0x18002a87b`
- `RPCRT4!RpcRevertToSelf` at `0x18002a89a`
- `RPCRT4!RpcRevertToSelf` at `0x18002a89a`

## pseudocode

```c
__int64 __fastcall RpcSrvMadcapRenewAddress_New(
        CRpcWatchDog *a1,
        unsigned __int16 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  unsigned int v8; // eax
  CRpcWatchDog *v9; // rcx
  unsigned int v10; // ebx
  _QWORD v12[9]; // [rsp+40h] [rbp-48h] BYREF

  memset(v12, 0, 32);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_dqqq(a1, 250, a3, a2, a3, a4, a5);
  v12[0] = RpcSrvMadcapRenewAddress;
  CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)v12, a3);
  v8 = RpcImpersonateClient(0);
  v10 = v8;
  if ( v8 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_Dd(1025, 251, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v8, v8);
  }
  else
  {
    v10 = RenewAddress(a2, a3, a4, a5);
    RpcRevertToSelf();
  }
  CRpcWatchDog::RemoveEntry(v9, (struct _WatchDogEntry *)v12);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 252, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18002a818  mov     rax, rsp
0x18002a81b  push    rbx
0x18002a81c  push    rbp
0x18002a81d  push    rsi
0x18002a81e  push    rdi
0x18002a81f  push    r14
0x18002a821  sub     rsp, 60h
0x18002a825  xorps   xmm0, xmm0
0x18002a828  movzx   ebp, dx
0x18002a82b  movups  xmmword ptr [rax-48h], xmm0
0x18002a82f  mov     rdi, r9
0x18002a832  mov     rsi, r8
0x18002a835  movups  xmmword ptr [rax-38h], xmm0
0x18002a839  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002a840  mov     r14, [rsp+88h+arg_20]
0x18002a848  jz      short loc_18002A863
0x18002a84a  mov     [rax-58h], r14
0x18002a84e  mov     r9d, ebp
0x18002a851  mov     [rax-60h], rdi
0x18002a855  mov     edx, 0FAh
0x18002a85a  mov     [rax-68h], r8
0x18002a85e  call    WPP_SF_dqqq
0x18002a863  lea     rax, RpcSrvMadcapRenewAddress
0x18002a86a  lea     rdx, [rsp+88h+var_48]; struct _WatchDogEntry *
0x18002a86f  mov     [rsp+88h+var_48], rax
0x18002a874  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002a879  xor     ecx, ecx; BindingHandle
0x18002a87b  call    cs:__imp_RpcImpersonateClient
0x18002a881  mov     ebx, eax
0x18002a883  test    eax, eax
0x18002a885  jnz     short loc_18002A8A2
0x18002a887  mov     r9, r14
0x18002a88a  mov     r8, rdi
0x18002a88d  mov     rdx, rsi
0x18002a890  movzx   ecx, bp
0x18002a893  call    RenewAddress
0x18002a898  mov     ebx, eax
0x18002a89a  call    cs:__imp_RpcRevertToSelf
0x18002a8a0  jmp     short loc_18002A8C8
0x18002a8a2  test    byte ptr cs:xmmword_1800616A0, 2
0x18002a8a9  jz      short loc_18002A8C8
0x18002a8ab  mov     edx, 0FBh
0x18002a8b0  mov     [rsp+88h+var_68], eax
0x18002a8b4  mov     ecx, 401h
0x18002a8b9  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a8c0  mov     r9d, eax
0x18002a8c3  call    WPP_SF_Dd
0x18002a8c8  lea     rdx, [rsp+88h+var_48]; struct _WatchDogEntry *
0x18002a8cd  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002a8d2  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002a8d9  jz      short loc_18002A8F4
0x18002a8db  mov     edx, 0FCh
0x18002a8e0  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a8e7  mov     ecx, 404h
0x18002a8ec  mov     r9d, ebx
0x18002a8ef  call    WPP_SF_D
0x18002a8f4  mov     eax, ebx
0x18002a8f6  add     rsp, 60h
0x18002a8fa  pop     r14
0x18002a8fc  pop     rdi
0x18002a8fd  pop     rsi
0x18002a8fe  pop     rbp
0x18002a8ff  pop     rbx
0x18002a900  retn
```
