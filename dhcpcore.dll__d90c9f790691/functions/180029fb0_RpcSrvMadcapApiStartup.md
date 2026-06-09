# RpcSrvMadcapApiStartup

- ea: `0x180029fb0`
- end: `0x18002a0a2`
- name: `RpcSrvMadcapApiStartup`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x180029fb0`
- `0x18002a0a8`
- `0x180036d60`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18002a020`
- `RPCRT4!RpcImpersonateClient` at `0x18002a020`
- `RPCRT4!RpcRevertToSelf` at `0x18002a085`
- `RPCRT4!RpcRevertToSelf` at `0x18002a085`

## pseudocode

```c
__int64 __fastcall RpcSrvMadcapApiStartup(CRpcWatchDog *a1, __int64 a2, int a3)
{
  __int64 v3; // rdi
  unsigned int v5; // ebx
  unsigned int v6; // eax
  _OWORD v7[2]; // [rsp+20h] [rbp-28h] BYREF

  memset(v7, 0, sizeof(v7));
  v3 = a2;
  if ( g_fVelocityApistubStyleUpdate )
    return RpcSrvMadcapApiStartup_New(a1, a2, a3);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 223, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
  if ( !v3 )
  {
    v5 = 87;
    goto LABEL_10;
  }
  *(_QWORD *)&v7[0] = RpcSrvMadcapApiStartup;
  CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)v7, a3);
  v6 = RpcImpersonateClient(0);
  v5 = v6;
  if ( !v6 )
  {
    v5 = ApiStartup(v3);
    RpcRevertToSelf();
LABEL_15:
    CRpcWatchDog::RemoveEntry(a1, (struct _WatchDogEntry *)v7);
    return v5;
  }
  LODWORD(v3) = 1;
  if ( (xmmword_1800616A0 & 2) != 0 )
  {
    WPP_SF_D(1025, 224, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v6);
LABEL_10:
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 225, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v5);
  }
  if ( (_DWORD)v3 )
    goto LABEL_15;
  return v5;
}

```

## disassembly

```asm
0x180029fb0  mov     [rsp+arg_0], rbx
0x180029fb5  push    rdi
0x180029fb6  sub     rsp, 40h
0x180029fba  cmp     cs:g_fVelocityApistubStyleUpdate, 0
0x180029fc1  xorps   xmm0, xmm0
0x180029fc4  movups  [rsp+48h+var_28], xmm0
0x180029fc9  mov     rdi, rdx
0x180029fcc  movups  [rsp+48h+var_18], xmm0
0x180029fd1  jz      short loc_180029FDD
0x180029fd3  call    RpcSrvMadcapApiStartup_New
0x180029fd8  jmp     loc_18002A097
0x180029fdd  test    byte ptr cs:xmmword_1800616A0, 10h
0x180029fe4  jz      short loc_180029FFC
0x180029fe6  mov     edx, 0DFh
0x180029feb  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x180029ff2  mov     ecx, 404h
0x180029ff7  call    WPP_SF_
0x180029ffc  test    rdi, rdi
0x180029fff  jnz     short loc_18002A008
0x18002a001  mov     ebx, 57h ; 'W'
0x18002a006  jmp     short loc_18002A053
0x18002a008  lea     rax, RpcSrvMadcapApiStartup
0x18002a00f  lea     rdx, [rsp+48h+var_28]; struct _WatchDogEntry *
0x18002a014  mov     qword ptr [rsp+48h+var_28], rax
0x18002a019  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002a01e  xor     ecx, ecx; BindingHandle
0x18002a020  call    cs:__imp_RpcImpersonateClient
0x18002a026  mov     ebx, eax
0x18002a028  test    eax, eax
0x18002a02a  jz      short loc_18002A07B
0x18002a02c  mov     edi, 1
0x18002a031  test    byte ptr cs:xmmword_1800616A0, 2
0x18002a038  jz      short loc_18002A075
0x18002a03a  mov     edx, 0E0h
0x18002a03f  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a046  mov     ecx, 401h
0x18002a04b  mov     r9d, eax
0x18002a04e  call    WPP_SF_D
0x18002a053  test    byte ptr cs:xmmword_1800616A0, 2
0x18002a05a  jz      short loc_18002A075
0x18002a05c  mov     edx, 0E1h
0x18002a061  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a068  mov     ecx, 401h
0x18002a06d  mov     r9d, ebx
0x18002a070  call    WPP_SF_D
0x18002a075  test    edi, edi
0x18002a077  jz      short loc_18002A095
0x18002a079  jmp     short loc_18002A08B
0x18002a07b  mov     rcx, rdi
0x18002a07e  call    ApiStartup
0x18002a083  mov     ebx, eax
0x18002a085  call    cs:__imp_RpcRevertToSelf
0x18002a08b  lea     rdx, [rsp+48h+var_28]; struct _WatchDogEntry *
0x18002a090  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002a095  mov     eax, ebx
0x18002a097  mov     rbx, [rsp+48h+arg_0]
0x18002a09c  add     rsp, 40h
0x18002a0a0  pop     rdi
0x18002a0a1  retn
```
