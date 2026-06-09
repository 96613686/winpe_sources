# RpcSrvReleaseIpAddressLeaseEx

- ea: `0x18002b830`
- end: `0x18002baf8`
- name: `RpcSrvReleaseIpAddressLeaseEx`
- size: `712`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x18002b830`
- `0x18002bb00`
- `0x18003c554`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18002b9a0`
- `RPCRT4!RpcImpersonateClient` at `0x18002b9a0`
- `RPCRT4!RpcRevertToSelf` at `0x18002bad6`
- `RPCRT4!RpcRevertToSelf` at `0x18002bad6`

## pseudocode

```c
__int64 __fastcall RpcSrvReleaseIpAddressLeaseEx(
        CRpcWatchDog *a1,
        u_long a2,
        u_long *a3,
        _OWORD *a4,
        _OWORD *a5,
        unsigned int a6)
{
  _OWORD *v10; // rax
  unsigned int *v11; // r8
  __int64 v12; // rdi
  __int64 v13; // rcx
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  _OWORD *v21; // rcx
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int64 v30; // rdi
  int v31; // ebx
  unsigned int v32; // esi
  unsigned int v33; // eax
  _OWORD *v34; // rax
  _OWORD *v35; // rcx
  __int64 v36; // r8
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  unsigned int *v44; // rcx
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v53; // [rsp+40h] [rbp-C0h]
  unsigned int v54[68]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v55[320]; // [rsp+160h] [rbp+60h] BYREF

  v52 = 0;
  v53 = 0;
  if ( !g_fVelocityApistubStyleUpdate )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_(1028, 210, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
    v30 = 2;
    if ( a3 )
    {
      *(_QWORD *)&v52 = &RpcSrvReleaseIpAddressLeaseEx;
      CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)&v52, (int)a3);
      v33 = RpcImpersonateClient(0);
      v32 = v33;
      if ( !v33 )
      {
        v34 = a5;
        v35 = v55;
        v36 = 2;
        do
        {
          v37 = v34[1];
          *v35 = *v34;
          v38 = v34[2];
          v35[1] = v37;
          v39 = v34[3];
          v35[2] = v38;
          v40 = v34[4];
          v35[3] = v39;
          v41 = v34[5];
          v35[4] = v40;
          v42 = v34[6];
          v35[5] = v41;
          v43 = v34[7];
          v34 += 8;
          v35[6] = v42;
          v35[7] = v43;
          v35 += 8;
          --v36;
        }
        while ( v36 );
        *(_DWORD *)v35 = *(_DWORD *)v34;
        v44 = v54;
        do
        {
          v45 = a4[1];
          *(_OWORD *)v44 = *a4;
          v46 = a4[2];
          *((_OWORD *)v44 + 1) = v45;
          v47 = a4[3];
          *((_OWORD *)v44 + 2) = v46;
          v48 = a4[4];
          *((_OWORD *)v44 + 3) = v47;
          v49 = a4[5];
          *((_OWORD *)v44 + 4) = v48;
          v50 = a4[6];
          *((_OWORD *)v44 + 5) = v49;
          v51 = a4[7];
          a4 += 8;
          *((_OWORD *)v44 + 6) = v50;
          *((_OWORD *)v44 + 7) = v51;
          v44 += 32;
          --v30;
        }
        while ( v30 );
        *v44 = *(_DWORD *)a4;
        v32 = ReleaseIpAddressLeaseEx(a2, a3, v54, (__int64)v55, a6);
        RpcRevertToSelf();
        goto LABEL_23;
      }
      v31 = 1;
      if ( (xmmword_1800616A0 & 2) == 0 )
      {
LABEL_16:
        if ( !v31 )
          return v32;
LABEL_23:
        CRpcWatchDog::RemoveEntry(a1, (struct _WatchDogEntry *)&v52);
        return v32;
      }
      WPP_SF_D(1025, 211, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v33);
    }
    else
    {
      v31 = 0;
      v32 = 87;
    }
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 212, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v32);
    goto LABEL_16;
  }
  v10 = a5;
  v11 = v54;
  v12 = 2;
  v13 = 2;
  do
  {
    v14 = v10[1];
    *(_OWORD *)v11 = *v10;
    v15 = v10[2];
    *((_OWORD *)v11 + 1) = v14;
    v16 = v10[3];
    *((_OWORD *)v11 + 2) = v15;
    v17 = v10[4];
    *((_OWORD *)v11 + 3) = v16;
    v18 = v10[5];
    *((_OWORD *)v11 + 4) = v17;
    v19 = v10[6];
    *((_OWORD *)v11 + 5) = v18;
    v20 = v10[7];
    v10 += 8;
    *((_OWORD *)v11 + 6) = v19;
    *((_OWORD *)v11 + 7) = v20;
    v11 += 32;
    --v13;
  }
  while ( v13 );
  v21 = v55;
  *v11 = *(_DWORD *)v10;
  do
  {
    v22 = a4[1];
    *v21 = *a4;
    v23 = a4[2];
    v21[1] = v22;
    v24 = a4[3];
    v21[2] = v23;
    v25 = a4[4];
    v21[3] = v24;
    v26 = a4[5];
    v21[4] = v25;
    v27 = a4[6];
    v21[5] = v26;
    v28 = a4[7];
    a4 += 8;
    v21[6] = v27;
    v21[7] = v28;
    v21 += 8;
    --v12;
  }
  while ( v12 );
  *(_DWORD *)v21 = *(_DWORD *)a4;
  return RpcSrvReleaseIpAddressLeaseEx_New(
           a1,
           a2,
           a3,
           v55,
           v54,
           a6,
           v52,
           *((_QWORD *)&v52 + 1),
           v53,
           *((_QWORD *)&v53 + 1));
}

```

## disassembly

```asm
0x18002b830  push    rbp
0x18002b832  push    rbx
0x18002b833  push    rsi
0x18002b834  push    rdi
0x18002b835  push    r14
0x18002b837  push    r15
0x18002b839  lea     rbp, [rsp-178h]
0x18002b841  sub     rsp, 278h
0x18002b848  cmp     cs:g_fVelocityApistubStyleUpdate, 0
0x18002b84f  xorps   xmm0, xmm0
0x18002b852  movups  [rsp+2A0h+var_270], xmm0
0x18002b857  mov     rbx, r9
0x18002b85a  mov     r14, r8
0x18002b85d  movups  [rsp+2A0h+var_260], xmm0
0x18002b862  mov     r15d, edx
0x18002b865  mov     r10, rcx
0x18002b868  jz      loc_18002B958
0x18002b86e  mov     rax, [rbp+1A0h+arg_20]
0x18002b875  lea     r8, [rsp+2A0h+var_250]
0x18002b87a  mov     edi, 2
0x18002b87f  mov     ecx, edi
0x18002b881  lea     edx, [rdi+7Eh]
0x18002b884  movups  xmm0, xmmword ptr [rax]
0x18002b887  movups  xmm1, xmmword ptr [rax+10h]
0x18002b88b  movups  xmmword ptr [r8], xmm0
0x18002b88f  movups  xmm0, xmmword ptr [rax+20h]
0x18002b893  movups  xmmword ptr [r8+10h], xmm1
0x18002b898  movups  xmm1, xmmword ptr [rax+30h]
0x18002b89c  movups  xmmword ptr [r8+20h], xmm0
0x18002b8a1  movups  xmm0, xmmword ptr [rax+40h]
0x18002b8a5  movups  xmmword ptr [r8+30h], xmm1
0x18002b8aa  movups  xmm1, xmmword ptr [rax+50h]
0x18002b8ae  movups  xmmword ptr [r8+40h], xmm0
0x18002b8b3  movups  xmm0, xmmword ptr [rax+60h]
0x18002b8b7  movups  xmmword ptr [r8+50h], xmm1
0x18002b8bc  movups  xmm1, xmmword ptr [rax+70h]
0x18002b8c0  add     rax, rdx
0x18002b8c3  movups  xmmword ptr [r8+60h], xmm0
0x18002b8c8  movups  xmmword ptr [r8+70h], xmm1
0x18002b8cd  add     r8, rdx
0x18002b8d0  sub     rcx, 1
0x18002b8d4  jnz     short loc_18002B884
0x18002b8d6  mov     eax, [rax]
0x18002b8d8  lea     rcx, [rbp+1A0h+var_140]
0x18002b8dc  mov     [r8], eax
0x18002b8df  movups  xmm0, xmmword ptr [rbx]
0x18002b8e2  movups  xmm1, xmmword ptr [rbx+10h]
0x18002b8e6  movups  xmmword ptr [rcx], xmm0
0x18002b8e9  movups  xmm0, xmmword ptr [rbx+20h]
0x18002b8ed  movups  xmmword ptr [rcx+10h], xmm1
0x18002b8f1  movups  xmm1, xmmword ptr [rbx+30h]
0x18002b8f5  movups  xmmword ptr [rcx+20h], xmm0
0x18002b8f9  movups  xmm0, xmmword ptr [rbx+40h]
0x18002b8fd  movups  xmmword ptr [rcx+30h], xmm1
0x18002b901  movups  xmm1, xmmword ptr [rbx+50h]
0x18002b905  movups  xmmword ptr [rcx+40h], xmm0
0x18002b909  movups  xmm0, xmmword ptr [rbx+60h]
0x18002b90d  movups  xmmword ptr [rcx+50h], xmm1
0x18002b911  movups  xmm1, xmmword ptr [rbx+70h]
0x18002b915  add     rbx, rdx
0x18002b918  movups  xmmword ptr [rcx+60h], xmm0
0x18002b91c  movups  xmmword ptr [rcx+70h], xmm1
0x18002b920  add     rcx, rdx
0x18002b923  sub     rdi, 1
0x18002b927  jnz     short loc_18002B8DF
0x18002b929  mov     eax, [rbx]
0x18002b92b  lea     r9, [rbp+1A0h+var_140]
0x18002b92f  mov     [rcx], eax
0x18002b931  mov     r8, r14
0x18002b934  mov     eax, [rbp+1A0h+arg_28]
0x18002b93a  mov     edx, r15d
0x18002b93d  mov     [rsp+2A0h+var_278], eax
0x18002b941  mov     rcx, r10
0x18002b944  lea     rax, [rsp+2A0h+var_250]
0x18002b949  mov     qword ptr [rsp+2A0h+var_280], rax
0x18002b94e  call    RpcSrvReleaseIpAddressLeaseEx_New
0x18002b953  jmp     loc_18002BAE8
0x18002b958  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002b95f  jz      short loc_18002B977
0x18002b961  mov     edx, 0D2h
0x18002b966  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002b96d  mov     ecx, 404h
0x18002b972  call    WPP_SF_
0x18002b977  mov     edi, 2
0x18002b97c  test    r14, r14
0x18002b97f  jnz     short loc_18002B988
0x18002b981  xor     ebx, ebx
0x18002b983  lea     esi, [rdi+55h]
0x18002b986  jmp     short loc_18002B9D3
0x18002b988  lea     rax, RpcSrvReleaseIpAddressLeaseEx
0x18002b98f  lea     rdx, [rsp+2A0h+var_270]; struct _WatchDogEntry *
0x18002b994  mov     qword ptr [rsp+2A0h+var_270], rax
0x18002b999  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002b99e  xor     ecx, ecx; BindingHandle
0x18002b9a0  call    cs:__imp_RpcImpersonateClient
0x18002b9a6  mov     esi, eax
0x18002b9a8  test    eax, eax
0x18002b9aa  jz      short loc_18002BA02
0x18002b9ac  mov     ebx, 1
0x18002b9b1  test    byte ptr cs:xmmword_1800616A0, dil
0x18002b9b8  jz      short loc_18002B9F5
0x18002b9ba  mov     edx, 0D3h
0x18002b9bf  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002b9c6  mov     ecx, 401h
0x18002b9cb  mov     r9d, eax
0x18002b9ce  call    WPP_SF_D
0x18002b9d3  test    byte ptr cs:xmmword_1800616A0, dil
0x18002b9da  jz      short loc_18002B9F5
0x18002b9dc  mov     edx, 0D4h
0x18002b9e1  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002b9e8  mov     ecx, 401h
0x18002b9ed  mov     r9d, esi
0x18002b9f0  call    WPP_SF_D
0x18002b9f5  test    ebx, ebx
0x18002b9f7  jz      loc_18002BAE6
0x18002b9fd  jmp     loc_18002BADC
0x18002ba02  mov     rax, [rbp+1A0h+arg_20]
0x18002ba09  lea     rcx, [rbp+1A0h+var_140]
0x18002ba0d  mov     r8, rdi
0x18002ba10  mov     edx, 80h
0x18002ba15  movups  xmm0, xmmword ptr [rax]
0x18002ba18  movups  xmm1, xmmword ptr [rax+10h]
0x18002ba1c  movups  xmmword ptr [rcx], xmm0
0x18002ba1f  movups  xmm0, xmmword ptr [rax+20h]
0x18002ba23  movups  xmmword ptr [rcx+10h], xmm1
0x18002ba27  movups  xmm1, xmmword ptr [rax+30h]
0x18002ba2b  movups  xmmword ptr [rcx+20h], xmm0
0x18002ba2f  movups  xmm0, xmmword ptr [rax+40h]
0x18002ba33  movups  xmmword ptr [rcx+30h], xmm1
0x18002ba37  movups  xmm1, xmmword ptr [rax+50h]
0x18002ba3b  movups  xmmword ptr [rcx+40h], xmm0
0x18002ba3f  movups  xmm0, xmmword ptr [rax+60h]
0x18002ba43  movups  xmmword ptr [rcx+50h], xmm1
0x18002ba47  movups  xmm1, xmmword ptr [rax+70h]
0x18002ba4b  add     rax, rdx
0x18002ba4e  movups  xmmword ptr [rcx+60h], xmm0
0x18002ba52  movups  xmmword ptr [rcx+70h], xmm1
0x18002ba56  add     rcx, rdx
0x18002ba59  sub     r8, 1
0x18002ba5d  jnz     short loc_18002BA15
0x18002ba5f  mov     eax, [rax]
0x18002ba61  mov     [rcx], eax
0x18002ba63  lea     rcx, [rsp+2A0h+var_250]
0x18002ba68  movups  xmm0, xmmword ptr [rbx]
0x18002ba6b  movups  xmm1, xmmword ptr [rbx+10h]
0x18002ba6f  movups  xmmword ptr [rcx], xmm0
0x18002ba72  movups  xmm0, xmmword ptr [rbx+20h]
0x18002ba76  movups  xmmword ptr [rcx+10h], xmm1
0x18002ba7a  movups  xmm1, xmmword ptr [rbx+30h]
0x18002ba7e  movups  xmmword ptr [rcx+20h], xmm0
0x18002ba82  movups  xmm0, xmmword ptr [rbx+40h]
0x18002ba86  movups  xmmword ptr [rcx+30h], xmm1
0x18002ba8a  movups  xmm1, xmmword ptr [rbx+50h]
0x18002ba8e  movups  xmmword ptr [rcx+40h], xmm0
0x18002ba92  movups  xmm0, xmmword ptr [rbx+60h]
0x18002ba96  movups  xmmword ptr [rcx+50h], xmm1
0x18002ba9a  movups  xmm1, xmmword ptr [rbx+70h]
0x18002ba9e  add     rbx, rdx
0x18002baa1  movups  xmmword ptr [rcx+60h], xmm0
0x18002baa5  movups  xmmword ptr [rcx+70h], xmm1
0x18002baa9  add     rcx, rdx
0x18002baac  sub     rdi, 1
0x18002bab0  jnz     short loc_18002BA68
0x18002bab2  mov     eax, [rbx]
0x18002bab4  lea     r9, [rbp+1A0h+var_140]
0x18002bab8  mov     [rcx], eax
0x18002baba  lea     r8, [rsp+2A0h+var_250]
0x18002babf  mov     eax, [rbp+1A0h+arg_28]
0x18002bac5  mov     ecx, r15d; hostlong
0x18002bac8  mov     rdx, r14
0x18002bacb  mov     [rsp+2A0h+var_280], eax; int
0x18002bacf  call    ReleaseIpAddressLeaseEx
0x18002bad4  mov     esi, eax
0x18002bad6  call    cs:__imp_RpcRevertToSelf
0x18002badc  lea     rdx, [rsp+2A0h+var_270]; struct _WatchDogEntry *
0x18002bae1  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002bae6  mov     eax, esi
0x18002bae8  add     rsp, 278h
0x18002baef  pop     r15
0x18002baf1  pop     r14
0x18002baf3  pop     rdi
0x18002baf4  pop     rsi
0x18002baf5  pop     rbx
0x18002baf6  pop     rbp
0x18002baf7  retn
```
