# RpcSrvMadcapRenewAddress

- ea: `0x18002a710`
- end: `0x18002a810`
- name: `RpcSrvMadcapRenewAddress`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x18002a710`
- `0x18002a818`
- `0x18003708c`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18002a788`
- `RPCRT4!RpcImpersonateClient` at `0x18002a788`
- `RPCRT4!RpcRevertToSelf` at `0x18002a7f4`
- `RPCRT4!RpcRevertToSelf` at `0x18002a7f4`

## pseudocode

```c
__int64 __fastcall RpcSrvMadcapRenewAddress(CRpcWatchDog *a1, unsigned __int16 a2, __int64 a3, __int64 a4, __int64 a5)
{
  CRpcWatchDog *v9; // rcx
  unsigned int v10; // ebx
  _OWORD v11[4]; // [rsp+30h] [rbp-48h] BYREF

  memset(v11, 0, 32);
  if ( g_fVelocityApistubStyleUpdate )
    return RpcSrvMadcapRenewAddress_New((_DWORD)a1, a2, a3, a4, a5);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 253, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
  *(_QWORD *)&v11[0] = RpcSrvMadcapRenewAddress;
  CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)v11, a3);
  v10 = RpcImpersonateClient(0);
  if ( v10 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
    {
      WPP_SF_D(1025, 254, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v10);
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_D(1025, 255, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v10);
    }
  }
  else
  {
    v10 = RenewAddress(a2, a3, a4, a5);
    RpcRevertToSelf();
  }
  CRpcWatchDog::RemoveEntry(v9, (struct _WatchDogEntry *)v11);
  return v10;
}

```

## disassembly

```asm
0x18002a710  push    rbx
0x18002a712  push    rsi
0x18002a713  push    rdi
0x18002a714  push    r14
0x18002a716  sub     rsp, 58h
0x18002a71a  cmp     cs:g_fVelocityApistubStyleUpdate, 0
0x18002a721  xorps   xmm0, xmm0
0x18002a724  movups  [rsp+78h+var_48], xmm0
0x18002a729  mov     rdi, r9
0x18002a72c  mov     rsi, r8
0x18002a72f  movups  [rsp+78h+var_38], xmm0
0x18002a734  movzx   r14d, dx
0x18002a738  jz      short loc_18002A751
0x18002a73a  mov     rax, [rsp+78h+arg_20]
0x18002a742  mov     [rsp+78h+var_58], rax
0x18002a747  call    RpcSrvMadcapRenewAddress_New
0x18002a74c  jmp     loc_18002A806
0x18002a751  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002a758  jz      short loc_18002A770
0x18002a75a  mov     edx, 0FDh
0x18002a75f  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a766  mov     ecx, 404h
0x18002a76b  call    WPP_SF_
0x18002a770  lea     rax, RpcSrvMadcapRenewAddress
0x18002a777  lea     rdx, [rsp+78h+var_48]; struct _WatchDogEntry *
0x18002a77c  mov     qword ptr [rsp+78h+var_48], rax
0x18002a781  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002a786  xor     ecx, ecx; BindingHandle
0x18002a788  call    cs:__imp_RpcImpersonateClient
0x18002a78e  mov     ebx, eax
0x18002a790  test    eax, eax
0x18002a792  jz      short loc_18002A7DB
0x18002a794  mov     al, byte ptr cs:xmmword_1800616A0
0x18002a79a  mov     edi, 401h
0x18002a79f  test    al, 2
0x18002a7a1  jz      short loc_18002A7FA
0x18002a7a3  mov     edx, 0FEh
0x18002a7a8  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a7af  mov     ecx, edi
0x18002a7b1  mov     r9d, ebx
0x18002a7b4  call    WPP_SF_D
0x18002a7b9  mov     al, byte ptr cs:xmmword_1800616A0
0x18002a7bf  test    al, 2
0x18002a7c1  jz      short loc_18002A7FA
0x18002a7c3  mov     edx, 0FFh
0x18002a7c8  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a7cf  mov     ecx, edi
0x18002a7d1  mov     r9d, ebx
0x18002a7d4  call    WPP_SF_D
0x18002a7d9  jmp     short loc_18002A7FA
0x18002a7db  mov     r9, [rsp+78h+arg_20]
0x18002a7e3  mov     r8, rdi
0x18002a7e6  mov     rdx, rsi
0x18002a7e9  movzx   ecx, r14w
0x18002a7ed  call    RenewAddress
0x18002a7f2  mov     ebx, eax
0x18002a7f4  call    cs:__imp_RpcRevertToSelf
0x18002a7fa  lea     rdx, [rsp+78h+var_48]; struct _WatchDogEntry *
0x18002a7ff  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002a804  mov     eax, ebx
0x18002a806  add     rsp, 58h
0x18002a80a  pop     r14
0x18002a80c  pop     rdi
0x18002a80d  pop     rsi
0x18002a80e  pop     rbx
0x18002a80f  retn
```
