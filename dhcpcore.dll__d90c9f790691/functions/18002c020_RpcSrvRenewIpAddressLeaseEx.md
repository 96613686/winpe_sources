# RpcSrvRenewIpAddressLeaseEx

- ea: `0x18002c020`
- end: `0x18002c31c`
- name: `RpcSrvRenewIpAddressLeaseEx`
- size: `764`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x18002c020`
- `0x18002c324`
- `0x18003c9d8`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18002c19b`
- `RPCRT4!RpcImpersonateClient` at `0x18002c19b`
- `RPCRT4!RpcRevertToSelf` at `0x18002c2fb`
- `RPCRT4!RpcRevertToSelf` at `0x18002c2fb`

## pseudocode

```c
__int64 __fastcall RpcSrvRenewIpAddressLeaseEx(
        CRpcWatchDog *a1,
        int a2,
        int a3,
        _OWORD *a4,
        __int64 a5,
        __int64 a6,
        _OWORD *a7,
        int a8)
{
  int v11; // r10d
  _OWORD *v12; // rax
  _OWORD *v13; // r9
  __int64 v14; // rdi
  __int64 v15; // r8
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  _OWORD *v23; // rcx
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  CRpcWatchDog *v32; // rcx
  unsigned int v33; // esi
  _OWORD *v34; // rax
  _OWORD *v35; // rcx
  __int64 v36; // rdi
  __int64 v37; // r8
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  _OWORD *v45; // rcx
  __int128 v46; // xmm1
  __int128 v47; // xmm0
  __int128 v48; // xmm1
  __int128 v49; // xmm0
  __int128 v50; // xmm1
  __int128 v51; // xmm0
  __int128 v52; // xmm1
  _OWORD v53[2]; // [rsp+40h] [rbp-268h] BYREF
  _BYTE v54[272]; // [rsp+60h] [rbp-248h] BYREF
  _BYTE v55[312]; // [rsp+170h] [rbp-138h] BYREF

  memset(v53, 0, sizeof(v53));
  v11 = (int)a1;
  if ( g_fVelocityApistubStyleUpdate )
  {
    v12 = a7;
    v13 = v54;
    v14 = 2;
    v15 = 2;
    do
    {
      v16 = v12[1];
      *v13 = *v12;
      v17 = v12[2];
      v13[1] = v16;
      v18 = v12[3];
      v13[2] = v17;
      v19 = v12[4];
      v13[3] = v18;
      v20 = v12[5];
      v13[4] = v19;
      v21 = v12[6];
      v13[5] = v20;
      v22 = v12[7];
      v12 += 8;
      v13[6] = v21;
      v13[7] = v22;
      v13 += 8;
      --v15;
    }
    while ( v15 );
    v23 = v55;
    *(_DWORD *)v13 = *(_DWORD *)v12;
    do
    {
      v24 = a4[1];
      *v23 = *a4;
      v25 = a4[2];
      v23[1] = v24;
      v26 = a4[3];
      v23[2] = v25;
      v27 = a4[4];
      v23[3] = v26;
      v28 = a4[5];
      v23[4] = v27;
      v29 = a4[6];
      v23[5] = v28;
      v30 = a4[7];
      a4 += 8;
      v23[6] = v29;
      v23[7] = v30;
      v23 += 8;
      --v14;
    }
    while ( v14 );
    *(_DWORD *)v23 = *(_DWORD *)a4;
    return RpcSrvRenewIpAddressLeaseEx_New(v11, a2, a3, (unsigned int)v55, a5, a6, (__int64)v54, a8);
  }
  else
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_(1028, 204, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
    *(_QWORD *)&v53[0] = RpcSrvRenewIpAddressLeaseEx;
    CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)v53, a3);
    v33 = RpcImpersonateClient(0);
    if ( v33 )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
      {
        WPP_SF_D(1025, 205, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v33);
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_D(1025, 206, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v33);
      }
    }
    else
    {
      v34 = a7;
      v35 = v55;
      v36 = 2;
      v37 = 2;
      do
      {
        v38 = v34[1];
        *v35 = *v34;
        v39 = v34[2];
        v35[1] = v38;
        v40 = v34[3];
        v35[2] = v39;
        v41 = v34[4];
        v35[3] = v40;
        v42 = v34[5];
        v35[4] = v41;
        v43 = v34[6];
        v35[5] = v42;
        v44 = v34[7];
        v34 += 8;
        v35[6] = v43;
        v35[7] = v44;
        v35 += 8;
        --v37;
      }
      while ( v37 );
      *(_DWORD *)v35 = *(_DWORD *)v34;
      v45 = v54;
      do
      {
        v46 = a4[1];
        *v45 = *a4;
        v47 = a4[2];
        v45[1] = v46;
        v48 = a4[3];
        v45[2] = v47;
        v49 = a4[4];
        v45[3] = v48;
        v50 = a4[5];
        v45[4] = v49;
        v51 = a4[6];
        v45[5] = v50;
        v52 = a4[7];
        a4 += 8;
        v45[6] = v51;
        v45[7] = v52;
        v45 += 8;
        --v36;
      }
      while ( v36 );
      *(_DWORD *)v45 = *(_DWORD *)a4;
      v33 = RenewIpAddressLeaseEx(a2, a3, (unsigned int)v54, a5, a6, (__int64)v55, a8);
      RpcRevertToSelf();
    }
    CRpcWatchDog::RemoveEntry(v32, (struct _WatchDogEntry *)v53);
    return v33;
  }
}

```

## disassembly

```asm
0x18002c020  push    rbx
0x18002c022  push    rsi
0x18002c023  push    rdi
0x18002c024  push    r14
0x18002c026  push    r15
0x18002c028  sub     rsp, 280h
0x18002c02f  cmp     cs:g_fVelocityApistubStyleUpdate, 0
0x18002c036  xorps   xmm0, xmm0
0x18002c039  movups  [rsp+2A8h+var_268], xmm0
0x18002c03e  mov     rbx, r9
0x18002c041  mov     r14, r8
0x18002c044  movups  [rsp+2A8h+var_258], xmm0
0x18002c049  mov     r15d, edx
0x18002c04c  mov     r10, rcx
0x18002c04f  jz      loc_18002C164
0x18002c055  mov     rax, [rsp+2A8h+arg_30]
0x18002c05d  lea     r9, [rsp+2A8h+var_248]
0x18002c062  mov     edi, 2
0x18002c067  mov     r8d, edi
0x18002c06a  lea     edx, [rdi+7Eh]
0x18002c06d  movups  xmm0, xmmword ptr [rax]
0x18002c070  movups  xmm1, xmmword ptr [rax+10h]
0x18002c074  movups  xmmword ptr [r9], xmm0
0x18002c078  movups  xmm0, xmmword ptr [rax+20h]
0x18002c07c  movups  xmmword ptr [r9+10h], xmm1
0x18002c081  movups  xmm1, xmmword ptr [rax+30h]
0x18002c085  movups  xmmword ptr [r9+20h], xmm0
0x18002c08a  movups  xmm0, xmmword ptr [rax+40h]
0x18002c08e  movups  xmmword ptr [r9+30h], xmm1
0x18002c093  movups  xmm1, xmmword ptr [rax+50h]
0x18002c097  movups  xmmword ptr [r9+40h], xmm0
0x18002c09c  movups  xmm0, xmmword ptr [rax+60h]
0x18002c0a0  movups  xmmword ptr [r9+50h], xmm1
0x18002c0a5  movups  xmm1, xmmword ptr [rax+70h]
0x18002c0a9  add     rax, rdx
0x18002c0ac  movups  xmmword ptr [r9+60h], xmm0
0x18002c0b1  movups  xmmword ptr [r9+70h], xmm1
0x18002c0b6  add     r9, rdx
0x18002c0b9  sub     r8, 1
0x18002c0bd  jnz     short loc_18002C06D
0x18002c0bf  mov     eax, [rax]
0x18002c0c1  lea     rcx, [rsp+2A8h+var_138]
0x18002c0c9  mov     [r9], eax
0x18002c0cc  movups  xmm0, xmmword ptr [rbx]
0x18002c0cf  movups  xmm1, xmmword ptr [rbx+10h]
0x18002c0d3  movups  xmmword ptr [rcx], xmm0
0x18002c0d6  movups  xmm0, xmmword ptr [rbx+20h]
0x18002c0da  movups  xmmword ptr [rcx+10h], xmm1
0x18002c0de  movups  xmm1, xmmword ptr [rbx+30h]
0x18002c0e2  movups  xmmword ptr [rcx+20h], xmm0
0x18002c0e6  movups  xmm0, xmmword ptr [rbx+40h]
0x18002c0ea  movups  xmmword ptr [rcx+30h], xmm1
0x18002c0ee  movups  xmm1, xmmword ptr [rbx+50h]
0x18002c0f2  movups  xmmword ptr [rcx+40h], xmm0
0x18002c0f6  movups  xmm0, xmmword ptr [rbx+60h]
0x18002c0fa  movups  xmmword ptr [rcx+50h], xmm1
0x18002c0fe  movups  xmm1, xmmword ptr [rbx+70h]
0x18002c102  add     rbx, rdx
0x18002c105  movups  xmmword ptr [rcx+60h], xmm0
0x18002c109  movups  xmmword ptr [rcx+70h], xmm1
0x18002c10d  add     rcx, rdx
0x18002c110  sub     rdi, 1
0x18002c114  jnz     short loc_18002C0CC
0x18002c116  mov     eax, [rbx]
0x18002c118  lea     r9, [rsp+2A8h+var_138]
0x18002c120  mov     [rcx], eax
0x18002c122  mov     r8, r14
0x18002c125  mov     eax, [rsp+2A8h+arg_38]
0x18002c12c  mov     edx, r15d
0x18002c12f  mov     [rsp+2A8h+var_270], eax
0x18002c133  mov     rcx, r10
0x18002c136  lea     rax, [rsp+2A8h+var_248]
0x18002c13b  mov     [rsp+2A8h+var_278], rax
0x18002c140  mov     rax, [rsp+2A8h+arg_28]
0x18002c148  mov     [rsp+2A8h+var_280], rax
0x18002c14d  mov     rax, [rsp+2A8h+arg_20]
0x18002c155  mov     [rsp+2A8h+var_288], rax
0x18002c15a  call    RpcSrvRenewIpAddressLeaseEx_New
0x18002c15f  jmp     loc_18002C30D
0x18002c164  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002c16b  jz      short loc_18002C183
0x18002c16d  mov     edx, 0CCh
0x18002c172  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002c179  mov     ecx, 404h
0x18002c17e  call    WPP_SF_
0x18002c183  lea     rax, RpcSrvRenewIpAddressLeaseEx
0x18002c18a  lea     rdx, [rsp+2A8h+var_268]; struct _WatchDogEntry *
0x18002c18f  mov     qword ptr [rsp+2A8h+var_268], rax
0x18002c194  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002c199  xor     ecx, ecx; BindingHandle
0x18002c19b  call    cs:__imp_RpcImpersonateClient
0x18002c1a1  mov     esi, eax
0x18002c1a3  test    eax, eax
0x18002c1a5  jz      short loc_18002C200
0x18002c1a7  mov     al, byte ptr cs:xmmword_1800616A0
0x18002c1ad  mov     edi, 2
0x18002c1b2  mov     ebx, 401h
0x18002c1b7  test    dil, al
0x18002c1ba  jz      loc_18002C301
0x18002c1c0  mov     edx, 0CDh
0x18002c1c5  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002c1cc  mov     ecx, ebx
0x18002c1ce  mov     r9d, esi
0x18002c1d1  call    WPP_SF_D
0x18002c1d6  mov     al, byte ptr cs:xmmword_1800616A0
0x18002c1dc  test    dil, al
0x18002c1df  jz      loc_18002C301
0x18002c1e5  mov     edx, 0CEh
0x18002c1ea  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002c1f1  mov     ecx, ebx
0x18002c1f3  mov     r9d, esi
0x18002c1f6  call    WPP_SF_D
0x18002c1fb  jmp     loc_18002C301
0x18002c200  mov     rax, [rsp+2A8h+arg_30]
0x18002c208  lea     rcx, [rsp+2A8h+var_138]
0x18002c210  mov     edi, 2
0x18002c215  mov     r8d, edi
0x18002c218  lea     edx, [rdi+7Eh]
0x18002c21b  movups  xmm0, xmmword ptr [rax]
0x18002c21e  movups  xmm1, xmmword ptr [rax+10h]
0x18002c222  movups  xmmword ptr [rcx], xmm0
0x18002c225  movups  xmm0, xmmword ptr [rax+20h]
0x18002c229  movups  xmmword ptr [rcx+10h], xmm1
0x18002c22d  movups  xmm1, xmmword ptr [rax+30h]
0x18002c231  movups  xmmword ptr [rcx+20h], xmm0
0x18002c235  movups  xmm0, xmmword ptr [rax+40h]
0x18002c239  movups  xmmword ptr [rcx+30h], xmm1
0x18002c23d  movups  xmm1, xmmword ptr [rax+50h]
0x18002c241  movups  xmmword ptr [rcx+40h], xmm0
0x18002c245  movups  xmm0, xmmword ptr [rax+60h]
0x18002c249  movups  xmmword ptr [rcx+50h], xmm1
0x18002c24d  movups  xmm1, xmmword ptr [rax+70h]
0x18002c251  add     rax, rdx
0x18002c254  movups  xmmword ptr [rcx+60h], xmm0
0x18002c258  movups  xmmword ptr [rcx+70h], xmm1
0x18002c25c  add     rcx, rdx
0x18002c25f  sub     r8, 1
0x18002c263  jnz     short loc_18002C21B
0x18002c265  mov     eax, [rax]
0x18002c267  mov     [rcx], eax
0x18002c269  lea     rcx, [rsp+2A8h+var_248]
0x18002c26e  movups  xmm0, xmmword ptr [rbx]
0x18002c271  movups  xmm1, xmmword ptr [rbx+10h]
0x18002c275  movups  xmmword ptr [rcx], xmm0
0x18002c278  movups  xmm0, xmmword ptr [rbx+20h]
0x18002c27c  movups  xmmword ptr [rcx+10h], xmm1
0x18002c280  movups  xmm1, xmmword ptr [rbx+30h]
0x18002c284  movups  xmmword ptr [rcx+20h], xmm0
0x18002c288  movups  xmm0, xmmword ptr [rbx+40h]
0x18002c28c  movups  xmmword ptr [rcx+30h], xmm1
0x18002c290  movups  xmm1, xmmword ptr [rbx+50h]
0x18002c294  movups  xmmword ptr [rcx+40h], xmm0
0x18002c298  movups  xmm0, xmmword ptr [rbx+60h]
0x18002c29c  movups  xmmword ptr [rcx+50h], xmm1
0x18002c2a0  movups  xmm1, xmmword ptr [rbx+70h]
0x18002c2a4  add     rbx, rdx
0x18002c2a7  movups  xmmword ptr [rcx+60h], xmm0
0x18002c2ab  movups  xmmword ptr [rcx+70h], xmm1
0x18002c2af  add     rcx, rdx
0x18002c2b2  sub     rdi, 1
0x18002c2b6  jnz     short loc_18002C26E
0x18002c2b8  mov     eax, [rbx]
0x18002c2ba  lea     r8, [rsp+2A8h+var_248]
0x18002c2bf  mov     r9, [rsp+2A8h+arg_20]
0x18002c2c7  mov     rdx, r14
0x18002c2ca  mov     [rcx], eax
0x18002c2cc  mov     ecx, r15d
0x18002c2cf  mov     eax, [rsp+2A8h+arg_38]
0x18002c2d6  mov     dword ptr [rsp+2A8h+var_278], eax
0x18002c2da  lea     rax, [rsp+2A8h+var_138]
0x18002c2e2  mov     [rsp+2A8h+var_280], rax
0x18002c2e7  mov     rax, [rsp+2A8h+arg_28]
0x18002c2ef  mov     [rsp+2A8h+var_288], rax
0x18002c2f4  call    RenewIpAddressLeaseEx
0x18002c2f9  mov     esi, eax
0x18002c2fb  call    cs:__imp_RpcRevertToSelf
0x18002c301  lea     rdx, [rsp+2A8h+var_268]; struct _WatchDogEntry *
0x18002c306  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002c30b  mov     eax, esi
0x18002c30d  add     rsp, 280h
0x18002c314  pop     r15
0x18002c316  pop     r14
0x18002c318  pop     rdi
0x18002c319  pop     rsi
0x18002c31a  pop     rbx
0x18002c31b  retn
```
