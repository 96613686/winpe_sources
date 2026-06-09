# RpcSrvMadcapRequestAddress

- ea: `0x18002a910`
- end: `0x18002aa2a`
- name: `RpcSrvMadcapRequestAddress`
- size: `282`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x18002a910`
- `0x18002aa30`
- `0x180037294`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18002a995`
- `RPCRT4!RpcImpersonateClient` at `0x18002a995`
- `RPCRT4!RpcRevertToSelf` at `0x18002aa0e`
- `RPCRT4!RpcRevertToSelf` at `0x18002aa0e`

## pseudocode

```c
__int64 __fastcall RpcSrvMadcapRequestAddress(
        CRpcWatchDog *a1,
        unsigned __int16 a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6)
{
  CRpcWatchDog *v10; // rcx
  unsigned int v11; // ebx
  _OWORD v12[4]; // [rsp+30h] [rbp-48h] BYREF

  memset(v12, 0, 32);
  if ( g_fVelocityApistubStyleUpdate )
    return RpcSrvMadcapRequestAddress_New((_DWORD)a1, a2, a3, a4, a5, a6);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 247, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
  *(_QWORD *)&v12[0] = RpcSrvMadcapRequestAddress;
  CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)v12, a3);
  v11 = RpcImpersonateClient(0);
  if ( v11 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
    {
      WPP_SF_D(1025, 248, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v11);
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_D(1025, 249, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v11);
    }
  }
  else
  {
    v11 = RequestAddress(a2, a3, a4, a5, a6);
    RpcRevertToSelf();
  }
  CRpcWatchDog::RemoveEntry(v10, (struct _WatchDogEntry *)v12);
  return v11;
}

```

## disassembly

```asm
0x18002a910  push    rbx
0x18002a912  push    rsi
0x18002a913  push    rdi
0x18002a914  push    r14
0x18002a916  sub     rsp, 58h
0x18002a91a  cmp     cs:g_fVelocityApistubStyleUpdate, 0
0x18002a921  xorps   xmm0, xmm0
0x18002a924  movups  [rsp+78h+var_48], xmm0
0x18002a929  mov     rdi, r9
0x18002a92c  mov     rsi, r8
0x18002a92f  movups  [rsp+78h+var_38], xmm0
0x18002a934  movzx   r14d, dx
0x18002a938  jz      short loc_18002A95E
0x18002a93a  mov     rax, [rsp+78h+arg_28]
0x18002a942  mov     [rsp+78h+var_50], rax
0x18002a947  mov     rax, [rsp+78h+arg_20]
0x18002a94f  mov     [rsp+78h+var_58], rax
0x18002a954  call    RpcSrvMadcapRequestAddress_New
0x18002a959  jmp     loc_18002AA20
0x18002a95e  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002a965  jz      short loc_18002A97D
0x18002a967  mov     edx, 0F7h
0x18002a96c  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a973  mov     ecx, 404h
0x18002a978  call    WPP_SF_
0x18002a97d  lea     rax, RpcSrvMadcapRequestAddress
0x18002a984  lea     rdx, [rsp+78h+var_48]; struct _WatchDogEntry *
0x18002a989  mov     qword ptr [rsp+78h+var_48], rax
0x18002a98e  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002a993  xor     ecx, ecx; BindingHandle
0x18002a995  call    cs:__imp_RpcImpersonateClient
0x18002a99b  mov     ebx, eax
0x18002a99d  test    eax, eax
0x18002a99f  jz      short loc_18002A9E8
0x18002a9a1  mov     al, byte ptr cs:xmmword_1800616A0
0x18002a9a7  mov     edi, 401h
0x18002a9ac  test    al, 2
0x18002a9ae  jz      short loc_18002AA14
0x18002a9b0  mov     edx, 0F8h
0x18002a9b5  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a9bc  mov     ecx, edi
0x18002a9be  mov     r9d, ebx
0x18002a9c1  call    WPP_SF_D
0x18002a9c6  mov     al, byte ptr cs:xmmword_1800616A0
0x18002a9cc  test    al, 2
0x18002a9ce  jz      short loc_18002AA14
0x18002a9d0  mov     edx, 0F9h
0x18002a9d5  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a9dc  mov     ecx, edi
0x18002a9de  mov     r9d, ebx
0x18002a9e1  call    WPP_SF_D
0x18002a9e6  jmp     short loc_18002AA14
0x18002a9e8  mov     rax, [rsp+78h+arg_28]
0x18002a9f0  mov     r8, rdi
0x18002a9f3  mov     r9, [rsp+78h+arg_20]
0x18002a9fb  mov     rdx, rsi
0x18002a9fe  movzx   ecx, r14w
0x18002aa02  mov     [rsp+78h+var_58], rax
0x18002aa07  call    RequestAddress
0x18002aa0c  mov     ebx, eax
0x18002aa0e  call    cs:__imp_RpcRevertToSelf
0x18002aa14  lea     rdx, [rsp+78h+var_48]; struct _WatchDogEntry *
0x18002aa19  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002aa1e  mov     eax, ebx
0x18002aa20  add     rsp, 58h
0x18002aa24  pop     r14
0x18002aa26  pop     rdi
0x18002aa27  pop     rsi
0x18002aa28  pop     rbx
0x18002aa29  retn
```
