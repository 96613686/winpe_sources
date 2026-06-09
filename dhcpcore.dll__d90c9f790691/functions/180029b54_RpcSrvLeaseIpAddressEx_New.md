# RpcSrvLeaseIpAddressEx_New

- ea: `0x180029b54`
- end: `0x180029d3f`
- name: `RpcSrvLeaseIpAddressEx_New`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180029840`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x180029b54`
- `0x18003c064`
- `0x18004a6a0`
- `0x18004d1a0`
- `0x18004dd28`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180029bd6`
- `RPCRT4!RpcImpersonateClient` at `0x180029bd6`
- `RPCRT4!RpcRevertToSelf` at `0x180029ccd`
- `RPCRT4!RpcRevertToSelf` at `0x180029ccd`

## pseudocode

```c
__int64 __fastcall RpcSrvLeaseIpAddressEx_New(
        CRpcWatchDog *a1,
        u_long a2,
        _OWORD *a3,
        __int64 a4,
        char a5,
        __int64 a6,
        __int64 a7,
        _OWORD *a8,
        int a9)
{
  _OWORD *v9; // rdi
  unsigned int v11; // eax
  CRpcWatchDog *v12; // rcx
  unsigned int v13; // ebx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 *v17; // rcx
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  char *v25; // rcx
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v34; // [rsp+40h] [rbp-278h] BYREF
  __int128 v35; // [rsp+50h] [rbp-268h]
  __int64 v36[34]; // [rsp+60h] [rbp-258h] BYREF
  char v37; // [rsp+170h] [rbp-148h] BYREF

  v34 = 0;
  v9 = a3;
  v35 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_Dqqqd((_DWORD)a1, a2, (_DWORD)a3, a2, a5, a6, a7, a9, v34, v35);
  *(_QWORD *)&v34 = RpcSrvLeaseIpAddressEx;
  CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)&v34, (int)a3);
  v11 = RpcImpersonateClient(0);
  v13 = v11;
  if ( v11 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_Dd(1025, 196, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v11, v11);
  }
  else
  {
    v15 = 2;
    v16 = 2;
    v17 = v36;
    do
    {
      v18 = a8[1];
      *(_OWORD *)v17 = *a8;
      v19 = a8[2];
      *((_OWORD *)v17 + 1) = v18;
      v20 = a8[3];
      *((_OWORD *)v17 + 2) = v19;
      v21 = a8[4];
      *((_OWORD *)v17 + 3) = v20;
      v22 = a8[5];
      *((_OWORD *)v17 + 4) = v21;
      v23 = a8[6];
      *((_OWORD *)v17 + 5) = v22;
      v24 = a8[7];
      a8 += 8;
      *((_OWORD *)v17 + 6) = v23;
      *((_OWORD *)v17 + 7) = v24;
      v17 += 16;
      --v16;
    }
    while ( v16 );
    *(_DWORD *)v17 = *(_DWORD *)a8;
    v25 = &v37;
    do
    {
      v26 = v9[1];
      *(_OWORD *)v25 = *v9;
      v27 = v9[2];
      *((_OWORD *)v25 + 1) = v26;
      v28 = v9[3];
      *((_OWORD *)v25 + 2) = v27;
      v29 = v9[4];
      *((_OWORD *)v25 + 3) = v28;
      v30 = v9[5];
      *((_OWORD *)v25 + 4) = v29;
      v31 = v9[6];
      *((_OWORD *)v25 + 5) = v30;
      v32 = v9[7];
      v9 += 8;
      *((_OWORD *)v25 + 6) = v31;
      *((_OWORD *)v25 + 7) = v32;
      v25 += 128;
      --v15;
    }
    while ( v15 );
    *(_DWORD *)v25 = *(_DWORD *)v9;
    v13 = LeaseIpAddressEx(a2, a6, a7, (__int64)v36, a9);
    RpcRevertToSelf();
  }
  CRpcWatchDog::RemoveEntry(v12, (struct _WatchDogEntry *)&v34);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 197, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x180029b54  push    rbx
0x180029b56  push    rbp
0x180029b57  push    rsi
0x180029b58  push    rdi
0x180029b59  push    r12
0x180029b5b  push    r14
0x180029b5d  push    r15
0x180029b5f  sub     rsp, 280h
0x180029b66  xorps   xmm0, xmm0
0x180029b69  mov     r12d, r9d
0x180029b6c  movups  [rsp+2B8h+var_278], xmm0
0x180029b71  mov     rdi, r8
0x180029b74  mov     esi, edx
0x180029b76  movups  [rsp+2B8h+var_268], xmm0
0x180029b7b  test    byte ptr cs:xmmword_1800616A0, 10h
0x180029b82  mov     ebp, [rsp+2B8h+arg_40]
0x180029b89  mov     r14, [rsp+2B8h+arg_30]
0x180029b91  mov     r15, [rsp+2B8h+arg_28]
0x180029b99  jz      short loc_180029BBE
0x180029b9b  mov     rax, [rsp+2B8h+arg_20]
0x180029ba3  mov     r9d, edx
0x180029ba6  mov     [rsp+2B8h+var_280], ebp
0x180029baa  mov     [rsp+2B8h+var_288], r14
0x180029baf  mov     [rsp+2B8h+var_290], r15
0x180029bb4  mov     [rsp+2B8h+var_298], rax
0x180029bb9  call    WPP_SF_Dqqqd
0x180029bbe  lea     rax, RpcSrvLeaseIpAddressEx
0x180029bc5  lea     rdx, [rsp+2B8h+var_278]; struct _WatchDogEntry *
0x180029bca  mov     qword ptr [rsp+2B8h+var_278], rax
0x180029bcf  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x180029bd4  xor     ecx, ecx; BindingHandle
0x180029bd6  call    cs:__imp_RpcImpersonateClient
0x180029bdc  mov     ebx, eax
0x180029bde  test    eax, eax
0x180029be0  jnz     loc_180029CD5
0x180029be6  mov     rax, [rsp+2B8h+arg_38]
0x180029bee  lea     edx, [rbx+2]
0x180029bf1  mov     r8d, edx
0x180029bf4  lea     r9d, [rdx+7Eh]
0x180029bf8  lea     rcx, [rsp+2B8h+var_258]
0x180029bfd  movups  xmm0, xmmword ptr [rax]
0x180029c00  movups  xmm1, xmmword ptr [rax+10h]
0x180029c04  movups  xmmword ptr [rcx], xmm0
0x180029c07  movups  xmm0, xmmword ptr [rax+20h]
0x180029c0b  movups  xmmword ptr [rcx+10h], xmm1
0x180029c0f  movups  xmm1, xmmword ptr [rax+30h]
0x180029c13  movups  xmmword ptr [rcx+20h], xmm0
0x180029c17  movups  xmm0, xmmword ptr [rax+40h]
0x180029c1b  movups  xmmword ptr [rcx+30h], xmm1
0x180029c1f  movups  xmm1, xmmword ptr [rax+50h]
0x180029c23  movups  xmmword ptr [rcx+40h], xmm0
0x180029c27  movups  xmm0, xmmword ptr [rax+60h]
0x180029c2b  movups  xmmword ptr [rcx+50h], xmm1
0x180029c2f  movups  xmm1, xmmword ptr [rax+70h]
0x180029c33  add     rax, r9
0x180029c36  movups  xmmword ptr [rcx+60h], xmm0
0x180029c3a  movups  xmmword ptr [rcx+70h], xmm1
0x180029c3e  add     rcx, r9
0x180029c41  sub     r8, 1
0x180029c45  jnz     short loc_180029BFD
0x180029c47  mov     eax, [rax]
0x180029c49  mov     [rcx], eax
0x180029c4b  lea     rcx, [rsp+2B8h+var_148]
0x180029c53  movups  xmm0, xmmword ptr [rdi]
0x180029c56  movups  xmm1, xmmword ptr [rdi+10h]
0x180029c5a  movups  xmmword ptr [rcx], xmm0
0x180029c5d  movups  xmm0, xmmword ptr [rdi+20h]
0x180029c61  movups  xmmword ptr [rcx+10h], xmm1
0x180029c65  movups  xmm1, xmmword ptr [rdi+30h]
0x180029c69  movups  xmmword ptr [rcx+20h], xmm0
0x180029c6d  movups  xmm0, xmmword ptr [rdi+40h]
0x180029c71  movups  xmmword ptr [rcx+30h], xmm1
0x180029c75  movups  xmm1, xmmword ptr [rdi+50h]
0x180029c79  movups  xmmword ptr [rcx+40h], xmm0
0x180029c7d  movups  xmm0, xmmword ptr [rdi+60h]
0x180029c81  movups  xmmword ptr [rcx+50h], xmm1
0x180029c85  movups  xmm1, xmmword ptr [rdi+70h]
0x180029c89  add     rdi, r9
0x180029c8c  movups  xmmword ptr [rcx+60h], xmm0
0x180029c90  movups  xmmword ptr [rcx+70h], xmm1
0x180029c94  add     rcx, r9
0x180029c97  sub     rdx, 1
0x180029c9b  jnz     short loc_180029C53
0x180029c9d  mov     eax, [rdi]
0x180029c9f  lea     rdx, [rsp+2B8h+var_148]
0x180029ca7  mov     [rcx], eax
0x180029ca9  mov     r8d, r12d
0x180029cac  mov     [rsp+2B8h+var_280], ebp; int
0x180029cb0  lea     rax, [rsp+2B8h+var_258]
0x180029cb5  mov     [rsp+2B8h+var_288], rax; __int64
0x180029cba  mov     ecx, esi; netlong
0x180029cbc  mov     [rsp+2B8h+var_290], r14; __int64
0x180029cc1  mov     [rsp+2B8h+var_298], r15; __int64
0x180029cc6  call    LeaseIpAddressEx
0x180029ccb  mov     ebx, eax
0x180029ccd  call    cs:__imp_RpcRevertToSelf
0x180029cd3  jmp     short loc_180029CFF
0x180029cd5  mov     edx, 2
0x180029cda  test    byte ptr cs:xmmword_1800616A0, dl
0x180029ce0  jz      short loc_180029CFF
0x180029ce2  mov     edx, 0C4h
0x180029ce7  mov     dword ptr [rsp+2B8h+var_298], eax
0x180029ceb  mov     ecx, 401h
0x180029cf0  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x180029cf7  mov     r9d, eax
0x180029cfa  call    WPP_SF_Dd
0x180029cff  lea     rdx, [rsp+2B8h+var_278]; struct _WatchDogEntry *
0x180029d04  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x180029d09  test    byte ptr cs:xmmword_1800616A0, 10h
0x180029d10  jz      short loc_180029D2B
0x180029d12  mov     edx, 0C5h
0x180029d17  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x180029d1e  mov     ecx, 404h
0x180029d23  mov     r9d, ebx
0x180029d26  call    WPP_SF_D
0x180029d2b  mov     eax, ebx
0x180029d2d  add     rsp, 280h
0x180029d34  pop     r15
0x180029d36  pop     r14
0x180029d38  pop     r12
0x180029d3a  pop     rdi
0x180029d3b  pop     rsi
0x180029d3c  pop     rbp
0x180029d3d  pop     rbx
0x180029d3e  retn
```
