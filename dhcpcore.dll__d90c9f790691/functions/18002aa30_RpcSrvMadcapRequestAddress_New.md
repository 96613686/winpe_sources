# RpcSrvMadcapRequestAddress_New

- ea: `0x18002aa30`
- end: `0x18002ab29`
- name: `RpcSrvMadcapRequestAddress_New`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18002a910`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x18002aa30`
- `0x180037294`
- `0x18004ab54`
- `0x18004d1a0`
- `0x18004dd28`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18002aa9c`
- `RPCRT4!RpcImpersonateClient` at `0x18002aa9c`
- `RPCRT4!RpcRevertToSelf` at `0x18002aac0`
- `RPCRT4!RpcRevertToSelf` at `0x18002aac0`

## pseudocode

```c
__int64 __fastcall RpcSrvMadcapRequestAddress_New(
        CRpcWatchDog *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  unsigned __int16 v6; // bp
  int v7; // edi
  int v8; // esi
  unsigned int v9; // eax
  CRpcWatchDog *v10; // rcx
  unsigned int v11; // ebx
  __int128 v13; // [rsp+40h] [rbp-58h] BYREF
  __int128 v14; // [rsp+50h] [rbp-48h]

  v6 = a2;
  v13 = 0;
  v7 = a4;
  v8 = a3;
  v14 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_dqqqq(
      a1,
      a2,
      a3,
      (unsigned __int16)a2,
      a3,
      a4,
      a5,
      a6,
      v13,
      *((_QWORD *)&v13 + 1),
      v14,
      *((_QWORD *)&v14 + 1));
  *(_QWORD *)&v13 = RpcSrvMadcapRequestAddress;
  CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)&v13, a3);
  v9 = RpcImpersonateClient(0);
  v11 = v9;
  if ( v9 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_Dd(1025, 245, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v9, v9);
  }
  else
  {
    v11 = RequestAddress(v6, v8, v7, a5, a6);
    RpcRevertToSelf();
  }
  CRpcWatchDog::RemoveEntry(v10, (struct _WatchDogEntry *)&v13);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 246, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x18002aa30  mov     rax, rsp
0x18002aa33  push    rbx
0x18002aa34  push    rbp
0x18002aa35  push    rsi
0x18002aa36  push    rdi
0x18002aa37  push    r14
0x18002aa39  push    r15
0x18002aa3b  sub     rsp, 68h
0x18002aa3f  xorps   xmm0, xmm0
0x18002aa42  movzx   ebp, dx
0x18002aa45  movups  xmmword ptr [rax-58h], xmm0
0x18002aa49  mov     rdi, r9
0x18002aa4c  mov     rsi, r8
0x18002aa4f  movups  xmmword ptr [rax-48h], xmm0
0x18002aa53  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002aa5a  mov     r14, [rsp+98h+arg_28]
0x18002aa62  mov     r15, [rsp+98h+arg_20]
0x18002aa6a  jz      short loc_18002AA84
0x18002aa6c  mov     [rax-60h], r14
0x18002aa70  mov     r9d, ebp
0x18002aa73  mov     [rax-68h], r15
0x18002aa77  mov     [rax-70h], rdi
0x18002aa7b  mov     [rax-78h], r8
0x18002aa7f  call    WPP_SF_dqqqq
0x18002aa84  lea     rax, RpcSrvMadcapRequestAddress
0x18002aa8b  lea     rdx, [rsp+98h+var_58]; struct _WatchDogEntry *
0x18002aa90  mov     qword ptr [rsp+98h+var_58], rax
0x18002aa95  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002aa9a  xor     ecx, ecx; BindingHandle
0x18002aa9c  call    cs:__imp_RpcImpersonateClient
0x18002aaa2  mov     ebx, eax
0x18002aaa4  test    eax, eax
0x18002aaa6  jnz     short loc_18002AAC8
0x18002aaa8  mov     r9, r15
0x18002aaab  mov     [rsp+98h+var_78], r14
0x18002aab0  mov     r8, rdi
0x18002aab3  mov     rdx, rsi
0x18002aab6  movzx   ecx, bp
0x18002aab9  call    RequestAddress
0x18002aabe  mov     ebx, eax
0x18002aac0  call    cs:__imp_RpcRevertToSelf
0x18002aac6  jmp     short loc_18002AAEE
0x18002aac8  test    byte ptr cs:xmmword_1800616A0, 2
0x18002aacf  jz      short loc_18002AAEE
0x18002aad1  mov     edx, 0F5h
0x18002aad6  mov     dword ptr [rsp+98h+var_78], eax
0x18002aada  mov     ecx, 401h
0x18002aadf  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002aae6  mov     r9d, eax
0x18002aae9  call    WPP_SF_Dd
0x18002aaee  lea     rdx, [rsp+98h+var_58]; struct _WatchDogEntry *
0x18002aaf3  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002aaf8  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002aaff  jz      short loc_18002AB1A
0x18002ab01  mov     edx, 0F6h
0x18002ab06  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002ab0d  mov     ecx, 404h
0x18002ab12  mov     r9d, ebx
0x18002ab15  call    WPP_SF_D
0x18002ab1a  mov     eax, ebx
0x18002ab1c  add     rsp, 68h
0x18002ab20  pop     r15
0x18002ab22  pop     r14
0x18002ab24  pop     rdi
0x18002ab25  pop     rsi
0x18002ab26  pop     rbp
0x18002ab27  pop     rbx
0x18002ab28  retn
```
