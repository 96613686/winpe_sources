# RpcSrvMadcapReleaseAddress

- ea: `0x18002a540`
- end: `0x18002a62b`
- name: `RpcSrvMadcapReleaseAddress`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x18002a540`
- `0x18002a634`
- `0x180036ef0`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18002a5ab`
- `RPCRT4!RpcImpersonateClient` at `0x18002a5ab`
- `RPCRT4!RpcRevertToSelf` at `0x18002a60f`
- `RPCRT4!RpcRevertToSelf` at `0x18002a60f`

## pseudocode

```c
__int64 __fastcall RpcSrvMadcapReleaseAddress(CRpcWatchDog *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int16 v6; // r14
  CRpcWatchDog *v8; // rcx
  unsigned int v9; // ebx
  _OWORD v10[4]; // [rsp+20h] [rbp-48h] BYREF

  memset(v10, 0, 32);
  v6 = a2;
  if ( g_fVelocityApistubStyleUpdate )
    return RpcSrvMadcapReleaseAddress_New(a1, a2, a3, a4);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 259, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
  *(_QWORD *)&v10[0] = RpcSrvMadcapReleaseAddress;
  CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)v10, a3);
  v9 = RpcImpersonateClient(0);
  if ( v9 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
    {
      WPP_SF_D(1025, 260, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v9);
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_D(1025, 261, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v9);
    }
  }
  else
  {
    v9 = ReleaseAddress(v6, a3, a4);
    RpcRevertToSelf();
  }
  CRpcWatchDog::RemoveEntry(v8, (struct _WatchDogEntry *)v10);
  return v9;
}

```

## disassembly

```asm
0x18002a540  push    rbx
0x18002a542  push    rsi
0x18002a543  push    rdi
0x18002a544  push    r14
0x18002a546  sub     rsp, 48h
0x18002a54a  cmp     cs:g_fVelocityApistubStyleUpdate, 0
0x18002a551  xorps   xmm0, xmm0
0x18002a554  movups  [rsp+68h+var_48], xmm0
0x18002a559  mov     rdi, r9
0x18002a55c  mov     rsi, r8
0x18002a55f  movups  [rsp+68h+var_38], xmm0
0x18002a564  movzx   r14d, dx
0x18002a568  jz      short loc_18002A574
0x18002a56a  call    RpcSrvMadcapReleaseAddress_New
0x18002a56f  jmp     loc_18002A621
0x18002a574  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002a57b  jz      short loc_18002A593
0x18002a57d  mov     edx, 103h
0x18002a582  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a589  mov     ecx, 404h
0x18002a58e  call    WPP_SF_
0x18002a593  lea     rax, RpcSrvMadcapReleaseAddress
0x18002a59a  lea     rdx, [rsp+68h+var_48]; struct _WatchDogEntry *
0x18002a59f  mov     qword ptr [rsp+68h+var_48], rax
0x18002a5a4  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002a5a9  xor     ecx, ecx; BindingHandle
0x18002a5ab  call    cs:__imp_RpcImpersonateClient
0x18002a5b1  mov     ebx, eax
0x18002a5b3  test    eax, eax
0x18002a5b5  jz      short loc_18002A5FE
0x18002a5b7  mov     al, byte ptr cs:xmmword_1800616A0
0x18002a5bd  mov     edi, 401h
0x18002a5c2  test    al, 2
0x18002a5c4  jz      short loc_18002A615
0x18002a5c6  mov     edx, 104h
0x18002a5cb  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a5d2  mov     ecx, edi
0x18002a5d4  mov     r9d, ebx
0x18002a5d7  call    WPP_SF_D
0x18002a5dc  mov     al, byte ptr cs:xmmword_1800616A0
0x18002a5e2  test    al, 2
0x18002a5e4  jz      short loc_18002A615
0x18002a5e6  mov     edx, 105h
0x18002a5eb  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a5f2  mov     ecx, edi
0x18002a5f4  mov     r9d, ebx
0x18002a5f7  call    WPP_SF_D
0x18002a5fc  jmp     short loc_18002A615
0x18002a5fe  mov     r8, rdi
0x18002a601  mov     rdx, rsi
0x18002a604  movzx   ecx, r14w
0x18002a608  call    ReleaseAddress
0x18002a60d  mov     ebx, eax
0x18002a60f  call    cs:__imp_RpcRevertToSelf
0x18002a615  lea     rdx, [rsp+68h+var_48]; struct _WatchDogEntry *
0x18002a61a  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002a61f  mov     eax, ebx
0x18002a621  add     rsp, 48h
0x18002a625  pop     r14
0x18002a627  pop     rdi
0x18002a628  pop     rsi
0x18002a629  pop     rbx
0x18002a62a  retn
```
