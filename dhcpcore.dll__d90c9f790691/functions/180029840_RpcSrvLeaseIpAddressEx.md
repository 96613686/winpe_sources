# RpcSrvLeaseIpAddressEx

- ea: `0x180029840`
- end: `0x180029b4e`
- name: `RpcSrvLeaseIpAddressEx`
- size: `782`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x180029840`
- `0x180029b54`
- `0x18003c064`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800299c8`
- `RPCRT4!RpcImpersonateClient` at `0x1800299c8`
- `RPCRT4!RpcRevertToSelf` at `0x180029b2d`
- `RPCRT4!RpcRevertToSelf` at `0x180029b2d`

## pseudocode

```c
__int64 __fastcall RpcSrvLeaseIpAddressEx(
        CRpcWatchDog *a1,
        u_long a2,
        _OWORD *a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _OWORD *a8,
        int a9)
{
  _OWORD *v10; // rbx
  _OWORD *v13; // rax
  _OWORD *v14; // r8
  __int64 v15; // rdi
  __int64 v16; // r9
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int64 *v24; // rcx
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  CRpcWatchDog *v33; // rcx
  unsigned int v34; // esi
  _OWORD *v35; // rax
  __int64 *v36; // rcx
  __int64 v37; // rdi
  __int64 v38; // r8
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  _OWORD *v46; // rcx
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  __int128 v53; // xmm1
  _OWORD v54[2]; // [rsp+50h] [rbp-268h] BYREF
  _BYTE v55[272]; // [rsp+70h] [rbp-248h] BYREF
  __int64 v56[39]; // [rsp+180h] [rbp-138h] BYREF

  memset(v54, 0, sizeof(v54));
  v10 = a3;
  if ( g_fVelocityApistubStyleUpdate )
  {
    v13 = a8;
    v14 = v55;
    v15 = 2;
    v16 = 2;
    do
    {
      v17 = v13[1];
      *v14 = *v13;
      v18 = v13[2];
      v14[1] = v17;
      v19 = v13[3];
      v14[2] = v18;
      v20 = v13[4];
      v14[3] = v19;
      v21 = v13[5];
      v14[4] = v20;
      v22 = v13[6];
      v14[5] = v21;
      v23 = v13[7];
      v13 += 8;
      v14[6] = v22;
      v14[7] = v23;
      v14 += 8;
      --v16;
    }
    while ( v16 );
    v24 = v56;
    *(_DWORD *)v14 = *(_DWORD *)v13;
    do
    {
      v25 = v10[1];
      *(_OWORD *)v24 = *v10;
      v26 = v10[2];
      *((_OWORD *)v24 + 1) = v25;
      v27 = v10[3];
      *((_OWORD *)v24 + 2) = v26;
      v28 = v10[4];
      *((_OWORD *)v24 + 3) = v27;
      v29 = v10[5];
      *((_OWORD *)v24 + 4) = v28;
      v30 = v10[6];
      *((_OWORD *)v24 + 5) = v29;
      v31 = v10[7];
      v10 += 8;
      *((_OWORD *)v24 + 6) = v30;
      *((_OWORD *)v24 + 7) = v31;
      v24 += 16;
      --v15;
    }
    while ( v15 );
    *(_DWORD *)v24 = *(_DWORD *)v10;
    return RpcSrvLeaseIpAddressEx_New(a1, a2, v56, a4, a5, a6, a7, v55, a9);
  }
  else
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_(1028, 198, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
    *(_QWORD *)&v54[0] = &RpcSrvLeaseIpAddressEx;
    CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)v54, (int)a3);
    v34 = RpcImpersonateClient(0);
    if ( v34 )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
      {
        WPP_SF_D(1025, 199, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v34);
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_D(1025, 200, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v34);
      }
    }
    else
    {
      v35 = a8;
      v36 = v56;
      v37 = 2;
      v38 = 2;
      do
      {
        v39 = v35[1];
        *(_OWORD *)v36 = *v35;
        v40 = v35[2];
        *((_OWORD *)v36 + 1) = v39;
        v41 = v35[3];
        *((_OWORD *)v36 + 2) = v40;
        v42 = v35[4];
        *((_OWORD *)v36 + 3) = v41;
        v43 = v35[5];
        *((_OWORD *)v36 + 4) = v42;
        v44 = v35[6];
        *((_OWORD *)v36 + 5) = v43;
        v45 = v35[7];
        v35 += 8;
        *((_OWORD *)v36 + 6) = v44;
        *((_OWORD *)v36 + 7) = v45;
        v36 += 16;
        --v38;
      }
      while ( v38 );
      *(_DWORD *)v36 = *(_DWORD *)v35;
      v46 = v55;
      do
      {
        v47 = v10[1];
        *v46 = *v10;
        v48 = v10[2];
        v46[1] = v47;
        v49 = v10[3];
        v46[2] = v48;
        v50 = v10[4];
        v46[3] = v49;
        v51 = v10[5];
        v46[4] = v50;
        v52 = v10[6];
        v46[5] = v51;
        v53 = v10[7];
        v10 += 8;
        v46[6] = v52;
        v46[7] = v53;
        v46 += 8;
        --v37;
      }
      while ( v37 );
      *(_DWORD *)v46 = *(_DWORD *)v10;
      v34 = LeaseIpAddressEx(a2, a6, a7, (__int64)v56, a9);
      RpcRevertToSelf();
    }
    CRpcWatchDog::RemoveEntry(v33, (struct _WatchDogEntry *)v54);
    return v34;
  }
}

```

## disassembly

```asm
0x180029840  push    rbx
0x180029842  push    rsi
0x180029843  push    rdi
0x180029844  push    r14
0x180029846  push    r15
0x180029848  sub     rsp, 290h
0x18002984f  cmp     cs:g_fVelocityApistubStyleUpdate, 0
0x180029856  xorps   xmm0, xmm0
0x180029859  movups  [rsp+2B8h+var_268], xmm0
0x18002985e  mov     r14d, r9d
0x180029861  mov     rbx, r8
0x180029864  movups  [rsp+2B8h+var_258], xmm0
0x180029869  mov     r15d, edx
0x18002986c  mov     r10, rcx
0x18002986f  jz      loc_180029991
0x180029875  mov     rax, [rsp+2B8h+arg_38]
0x18002987d  lea     r8, [rsp+2B8h+var_248]
0x180029882  mov     edi, 2
0x180029887  mov     r9d, edi
0x18002988a  lea     edx, [rdi+7Eh]
0x18002988d  movups  xmm0, xmmword ptr [rax]
0x180029890  movups  xmm1, xmmword ptr [rax+10h]
0x180029894  movups  xmmword ptr [r8], xmm0
0x180029898  movups  xmm0, xmmword ptr [rax+20h]
0x18002989c  movups  xmmword ptr [r8+10h], xmm1
0x1800298a1  movups  xmm1, xmmword ptr [rax+30h]
0x1800298a5  movups  xmmword ptr [r8+20h], xmm0
0x1800298aa  movups  xmm0, xmmword ptr [rax+40h]
0x1800298ae  movups  xmmword ptr [r8+30h], xmm1
0x1800298b3  movups  xmm1, xmmword ptr [rax+50h]
0x1800298b7  movups  xmmword ptr [r8+40h], xmm0
0x1800298bc  movups  xmm0, xmmword ptr [rax+60h]
0x1800298c0  movups  xmmword ptr [r8+50h], xmm1
0x1800298c5  movups  xmm1, xmmword ptr [rax+70h]
0x1800298c9  add     rax, rdx
0x1800298cc  movups  xmmword ptr [r8+60h], xmm0
0x1800298d1  movups  xmmword ptr [r8+70h], xmm1
0x1800298d6  add     r8, rdx
0x1800298d9  sub     r9, 1
0x1800298dd  jnz     short loc_18002988D
0x1800298df  mov     eax, [rax]
0x1800298e1  lea     rcx, [rsp+2B8h+var_138]
0x1800298e9  mov     [r8], eax
0x1800298ec  movups  xmm0, xmmword ptr [rbx]
0x1800298ef  movups  xmm1, xmmword ptr [rbx+10h]
0x1800298f3  movups  xmmword ptr [rcx], xmm0
0x1800298f6  movups  xmm0, xmmword ptr [rbx+20h]
0x1800298fa  movups  xmmword ptr [rcx+10h], xmm1
0x1800298fe  movups  xmm1, xmmword ptr [rbx+30h]
0x180029902  movups  xmmword ptr [rcx+20h], xmm0
0x180029906  movups  xmm0, xmmword ptr [rbx+40h]
0x18002990a  movups  xmmword ptr [rcx+30h], xmm1
0x18002990e  movups  xmm1, xmmword ptr [rbx+50h]
0x180029912  movups  xmmword ptr [rcx+40h], xmm0
0x180029916  movups  xmm0, xmmword ptr [rbx+60h]
0x18002991a  movups  xmmword ptr [rcx+50h], xmm1
0x18002991e  movups  xmm1, xmmword ptr [rbx+70h]
0x180029922  add     rbx, rdx
0x180029925  movups  xmmword ptr [rcx+60h], xmm0
0x180029929  movups  xmmword ptr [rcx+70h], xmm1
0x18002992d  add     rcx, rdx
0x180029930  sub     rdi, 1
0x180029934  jnz     short loc_1800298EC
0x180029936  mov     eax, [rbx]
0x180029938  lea     r8, [rsp+2B8h+var_138]
0x180029940  mov     [rcx], eax
0x180029942  mov     r9d, r14d
0x180029945  mov     eax, [rsp+2B8h+arg_40]
0x18002994c  mov     edx, r15d
0x18002994f  mov     [rsp+2B8h+var_278], eax
0x180029953  mov     rcx, r10
0x180029956  lea     rax, [rsp+2B8h+var_248]
0x18002995b  mov     qword ptr [rsp+2B8h+var_280], rax
0x180029960  mov     rax, [rsp+2B8h+arg_30]
0x180029968  mov     [rsp+2B8h+var_288], rax
0x18002996d  mov     rax, [rsp+2B8h+arg_28]
0x180029975  mov     [rsp+2B8h+var_290], rax
0x18002997a  mov     rax, [rsp+2B8h+arg_20]
0x180029982  mov     [rsp+2B8h+var_298], rax
0x180029987  call    RpcSrvLeaseIpAddressEx_New
0x18002998c  jmp     loc_180029B3F
0x180029991  test    byte ptr cs:xmmword_1800616A0, 10h
0x180029998  jz      short loc_1800299B0
0x18002999a  mov     edx, 0C6h
0x18002999f  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x1800299a6  mov     ecx, 404h
0x1800299ab  call    WPP_SF_
0x1800299b0  lea     rax, RpcSrvLeaseIpAddressEx
0x1800299b7  lea     rdx, [rsp+2B8h+var_268]; struct _WatchDogEntry *
0x1800299bc  mov     qword ptr [rsp+2B8h+var_268], rax
0x1800299c1  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x1800299c6  xor     ecx, ecx; BindingHandle
0x1800299c8  call    cs:__imp_RpcImpersonateClient
0x1800299ce  mov     esi, eax
0x1800299d0  test    eax, eax
0x1800299d2  jz      short loc_180029A2D
0x1800299d4  mov     al, byte ptr cs:xmmword_1800616A0
0x1800299da  mov     edi, 2
0x1800299df  mov     ebx, 401h
0x1800299e4  test    dil, al
0x1800299e7  jz      loc_180029B33
0x1800299ed  mov     edx, 0C7h
0x1800299f2  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x1800299f9  mov     ecx, ebx
0x1800299fb  mov     r9d, esi
0x1800299fe  call    WPP_SF_D
0x180029a03  mov     al, byte ptr cs:xmmword_1800616A0
0x180029a09  test    dil, al
0x180029a0c  jz      loc_180029B33
0x180029a12  mov     edx, 0C8h
0x180029a17  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x180029a1e  mov     ecx, ebx
0x180029a20  mov     r9d, esi
0x180029a23  call    WPP_SF_D
0x180029a28  jmp     loc_180029B33
0x180029a2d  mov     rax, [rsp+2B8h+arg_38]
0x180029a35  lea     rcx, [rsp+2B8h+var_138]
0x180029a3d  mov     edi, 2
0x180029a42  mov     r8d, edi
0x180029a45  lea     edx, [rdi+7Eh]
0x180029a48  movups  xmm0, xmmword ptr [rax]
0x180029a4b  movups  xmm1, xmmword ptr [rax+10h]
0x180029a4f  movups  xmmword ptr [rcx], xmm0
0x180029a52  movups  xmm0, xmmword ptr [rax+20h]
0x180029a56  movups  xmmword ptr [rcx+10h], xmm1
0x180029a5a  movups  xmm1, xmmword ptr [rax+30h]
0x180029a5e  movups  xmmword ptr [rcx+20h], xmm0
0x180029a62  movups  xmm0, xmmword ptr [rax+40h]
0x180029a66  movups  xmmword ptr [rcx+30h], xmm1
0x180029a6a  movups  xmm1, xmmword ptr [rax+50h]
0x180029a6e  movups  xmmword ptr [rcx+40h], xmm0
0x180029a72  movups  xmm0, xmmword ptr [rax+60h]
0x180029a76  movups  xmmword ptr [rcx+50h], xmm1
0x180029a7a  movups  xmm1, xmmword ptr [rax+70h]
0x180029a7e  add     rax, rdx
0x180029a81  movups  xmmword ptr [rcx+60h], xmm0
0x180029a85  movups  xmmword ptr [rcx+70h], xmm1
0x180029a89  add     rcx, rdx
0x180029a8c  sub     r8, 1
0x180029a90  jnz     short loc_180029A48
0x180029a92  mov     eax, [rax]
0x180029a94  mov     [rcx], eax
0x180029a96  lea     rcx, [rsp+2B8h+var_248]
0x180029a9b  movups  xmm0, xmmword ptr [rbx]
0x180029a9e  movups  xmm1, xmmword ptr [rbx+10h]
0x180029aa2  movups  xmmword ptr [rcx], xmm0
0x180029aa5  movups  xmm0, xmmword ptr [rbx+20h]
0x180029aa9  movups  xmmword ptr [rcx+10h], xmm1
0x180029aad  movups  xmm1, xmmword ptr [rbx+30h]
0x180029ab1  movups  xmmword ptr [rcx+20h], xmm0
0x180029ab5  movups  xmm0, xmmword ptr [rbx+40h]
0x180029ab9  movups  xmmword ptr [rcx+30h], xmm1
0x180029abd  movups  xmm1, xmmword ptr [rbx+50h]
0x180029ac1  movups  xmmword ptr [rcx+40h], xmm0
0x180029ac5  movups  xmm0, xmmword ptr [rbx+60h]
0x180029ac9  movups  xmmword ptr [rcx+50h], xmm1
0x180029acd  movups  xmm1, xmmword ptr [rbx+70h]
0x180029ad1  add     rbx, rdx
0x180029ad4  movups  xmmword ptr [rcx+60h], xmm0
0x180029ad8  movups  xmmword ptr [rcx+70h], xmm1
0x180029adc  add     rcx, rdx
0x180029adf  sub     rdi, 1
0x180029ae3  jnz     short loc_180029A9B
0x180029ae5  mov     eax, [rbx]
0x180029ae7  lea     rdx, [rsp+2B8h+var_248]
0x180029aec  mov     [rcx], eax
0x180029aee  mov     r8d, r14d
0x180029af1  mov     eax, [rsp+2B8h+arg_40]
0x180029af8  mov     ecx, r15d; netlong
0x180029afb  mov     [rsp+2B8h+var_280], eax; int
0x180029aff  lea     rax, [rsp+2B8h+var_138]
0x180029b07  mov     [rsp+2B8h+var_288], rax; __int64
0x180029b0c  mov     rax, [rsp+2B8h+arg_30]
0x180029b14  mov     [rsp+2B8h+var_290], rax; __int64
0x180029b19  mov     rax, [rsp+2B8h+arg_28]
0x180029b21  mov     [rsp+2B8h+var_298], rax; __int64
0x180029b26  call    LeaseIpAddressEx
0x180029b2b  mov     esi, eax
0x180029b2d  call    cs:__imp_RpcRevertToSelf
0x180029b33  lea     rdx, [rsp+2B8h+var_268]; struct _WatchDogEntry *
0x180029b38  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x180029b3d  mov     eax, esi
0x180029b3f  add     rsp, 290h
0x180029b46  pop     r15
0x180029b48  pop     r14
0x180029b4a  pop     rdi
0x180029b4b  pop     rsi
0x180029b4c  pop     rbx
0x180029b4d  retn
```
