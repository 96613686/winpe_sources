# RpcSrvRenewIpAddressLeaseEx_New

- ea: `0x18002c324`
- end: `0x18002c527`
- name: `RpcSrvRenewIpAddressLeaseEx_New`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18002c020`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x18002c324`
- `0x18003c9d8`
- `0x18004a734`
- `0x18004d1a0`
- `0x18004dd28`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18002c3b2`
- `RPCRT4!RpcImpersonateClient` at `0x18002c3b2`
- `RPCRT4!RpcRevertToSelf` at `0x18002c4aa`
- `RPCRT4!RpcRevertToSelf` at `0x18002c4aa`

## pseudocode

```c
__int64 __fastcall RpcSrvRenewIpAddressLeaseEx_New(
        CRpcWatchDog *a1,
        int a2,
        int a3,
        _OWORD *a4,
        __int64 a5,
        __int64 a6,
        _OWORD *a7,
        int a8)
{
  _OWORD *v8; // rdi
  unsigned int v12; // eax
  CRpcWatchDog *v13; // rcx
  unsigned int v14; // ebx
  __int64 v15; // r10
  __int64 v16; // rax
  _OWORD *v17; // rcx
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  _OWORD *v25; // r8
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  _OWORD v34[2]; // [rsp+50h] [rbp-278h] BYREF
  _BYTE v35[272]; // [rsp+70h] [rbp-258h] BYREF
  _BYTE v36[328]; // [rsp+180h] [rbp-148h] BYREF

  v8 = a4;
  memset(v34, 0, sizeof(v34));
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_Dqqqqd((_DWORD)a1, a2, a3, a2, a3, (char)a4, a5, a6, a8);
  *(_QWORD *)&v34[0] = RpcSrvRenewIpAddressLeaseEx;
  CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)v34, a3);
  v12 = RpcImpersonateClient(0);
  v14 = v12;
  if ( v12 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_Dd(1025, 202, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v12, v12);
  }
  else
  {
    v15 = 2;
    v16 = 2;
    v17 = v35;
    do
    {
      v18 = a7[1];
      *v17 = *a7;
      v19 = a7[2];
      v17[1] = v18;
      v20 = a7[3];
      v17[2] = v19;
      v21 = a7[4];
      v17[3] = v20;
      v22 = a7[5];
      v17[4] = v21;
      v23 = a7[6];
      v17[5] = v22;
      v24 = a7[7];
      a7 += 8;
      v17[6] = v23;
      v17[7] = v24;
      v17 += 8;
      --v16;
    }
    while ( v16 );
    v25 = v36;
    *(_DWORD *)v17 = *(_DWORD *)a7;
    do
    {
      v26 = v8[1];
      *v25 = *v8;
      v27 = v8[2];
      v25[1] = v26;
      v28 = v8[3];
      v25[2] = v27;
      v29 = v8[4];
      v25[3] = v28;
      v30 = v8[5];
      v25[4] = v29;
      v31 = v8[6];
      v25[5] = v30;
      v32 = v8[7];
      v8 += 8;
      v25[6] = v31;
      v25[7] = v32;
      v25 += 8;
      --v15;
    }
    while ( v15 );
    *(_DWORD *)v25 = *(_DWORD *)v8;
    v14 = RenewIpAddressLeaseEx(a2, a3, (unsigned int)v36, a5, a6, (__int64)v35, a8);
    RpcRevertToSelf();
  }
  CRpcWatchDog::RemoveEntry(v13, (struct _WatchDogEntry *)v34);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 203, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x18002c324  mov     [rsp+arg_0], rbx
0x18002c329  push    rbp
0x18002c32a  push    rsi
0x18002c32b  push    rdi
0x18002c32c  push    r12
0x18002c32e  push    r13
0x18002c330  push    r14
0x18002c332  push    r15
0x18002c334  sub     rsp, 290h
0x18002c33b  mov     r15, [rsp+2C8h+arg_20]
0x18002c343  xorps   xmm0, xmm0
0x18002c346  mov     r12, [rsp+2C8h+arg_28]
0x18002c34e  mov     rdi, r9
0x18002c351  mov     rsi, [rsp+2C8h+arg_30]
0x18002c359  mov     r14, r8
0x18002c35c  movups  [rsp+2C8h+var_278], xmm0
0x18002c361  mov     ebp, edx
0x18002c363  movups  [rsp+2C8h+var_268], xmm0
0x18002c368  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002c36f  mov     r13d, [rsp+2C8h+arg_38]
0x18002c377  jz      short loc_18002C39A
0x18002c379  mov     [rsp+2C8h+var_288], r13d
0x18002c37e  mov     [rsp+2C8h+var_290], r12
0x18002c383  mov     [rsp+2C8h+var_298], r15
0x18002c388  mov     [rsp+2C8h+var_2A0], r9
0x18002c38d  mov     r9d, edx
0x18002c390  mov     [rsp+2C8h+var_2A8], r8
0x18002c395  call    WPP_SF_Dqqqqd
0x18002c39a  lea     rax, RpcSrvRenewIpAddressLeaseEx
0x18002c3a1  lea     rdx, [rsp+2C8h+var_278]; struct _WatchDogEntry *
0x18002c3a6  mov     qword ptr [rsp+2C8h+var_278], rax
0x18002c3ab  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002c3b0  xor     ecx, ecx; BindingHandle
0x18002c3b2  call    cs:__imp_RpcImpersonateClient
0x18002c3b8  mov     ebx, eax
0x18002c3ba  test    eax, eax
0x18002c3bc  jnz     loc_18002C4B2
0x18002c3c2  lea     r10d, [rax+2]
0x18002c3c6  mov     eax, r10d
0x18002c3c9  lea     edx, [r10+7Eh]
0x18002c3cd  lea     rcx, [rsp+2C8h+var_258]
0x18002c3d2  movups  xmm0, xmmword ptr [rsi]
0x18002c3d5  movups  xmm1, xmmword ptr [rsi+10h]
0x18002c3d9  movups  xmmword ptr [rcx], xmm0
0x18002c3dc  movups  xmm0, xmmword ptr [rsi+20h]
0x18002c3e0  movups  xmmword ptr [rcx+10h], xmm1
0x18002c3e4  movups  xmm1, xmmword ptr [rsi+30h]
0x18002c3e8  movups  xmmword ptr [rcx+20h], xmm0
0x18002c3ec  movups  xmm0, xmmword ptr [rsi+40h]
0x18002c3f0  movups  xmmword ptr [rcx+30h], xmm1
0x18002c3f4  movups  xmm1, xmmword ptr [rsi+50h]
0x18002c3f8  movups  xmmword ptr [rcx+40h], xmm0
0x18002c3fc  movups  xmm0, xmmword ptr [rsi+60h]
0x18002c400  movups  xmmword ptr [rcx+50h], xmm1
0x18002c404  movups  xmm1, xmmword ptr [rsi+70h]
0x18002c408  add     rsi, rdx
0x18002c40b  movups  xmmword ptr [rcx+60h], xmm0
0x18002c40f  movups  xmmword ptr [rcx+70h], xmm1
0x18002c413  add     rcx, rdx
0x18002c416  sub     rax, 1
0x18002c41a  jnz     short loc_18002C3D2
0x18002c41c  mov     eax, [rsi]
0x18002c41e  lea     r8, [rsp+2C8h+var_148]
0x18002c426  mov     [rcx], eax
0x18002c428  movups  xmm0, xmmword ptr [rdi]
0x18002c42b  movups  xmm1, xmmword ptr [rdi+10h]
0x18002c42f  movups  xmmword ptr [r8], xmm0
0x18002c433  movups  xmm0, xmmword ptr [rdi+20h]
0x18002c437  movups  xmmword ptr [r8+10h], xmm1
0x18002c43c  movups  xmm1, xmmword ptr [rdi+30h]
0x18002c440  movups  xmmword ptr [r8+20h], xmm0
0x18002c445  movups  xmm0, xmmword ptr [rdi+40h]
0x18002c449  movups  xmmword ptr [r8+30h], xmm1
0x18002c44e  movups  xmm1, xmmword ptr [rdi+50h]
0x18002c452  movups  xmmword ptr [r8+40h], xmm0
0x18002c457  movups  xmm0, xmmword ptr [rdi+60h]
0x18002c45b  movups  xmmword ptr [r8+50h], xmm1
0x18002c460  movups  xmm1, xmmword ptr [rdi+70h]
0x18002c464  add     rdi, rdx
0x18002c467  movups  xmmword ptr [r8+60h], xmm0
0x18002c46c  movups  xmmword ptr [r8+70h], xmm1
0x18002c471  add     r8, rdx
0x18002c474  sub     r10, 1
0x18002c478  jnz     short loc_18002C428
0x18002c47a  mov     eax, [rdi]
0x18002c47c  mov     r9, r15
0x18002c47f  mov     [r8], eax
0x18002c482  mov     rdx, r14
0x18002c485  lea     rax, [rsp+2C8h+var_258]
0x18002c48a  mov     dword ptr [rsp+2C8h+var_298], r13d
0x18002c48f  mov     [rsp+2C8h+var_2A0], rax
0x18002c494  lea     r8, [rsp+2C8h+var_148]
0x18002c49c  mov     ecx, ebp
0x18002c49e  mov     [rsp+2C8h+var_2A8], r12
0x18002c4a3  call    RenewIpAddressLeaseEx
0x18002c4a8  mov     ebx, eax
0x18002c4aa  call    cs:__imp_RpcRevertToSelf
0x18002c4b0  jmp     short loc_18002C4DE
0x18002c4b2  mov     r10d, 2
0x18002c4b8  test    byte ptr cs:xmmword_1800616A0, r10b
0x18002c4bf  jz      short loc_18002C4DE
0x18002c4c1  mov     edx, 0CAh
0x18002c4c6  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x18002c4ca  mov     ecx, 401h
0x18002c4cf  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002c4d6  mov     r9d, eax
0x18002c4d9  call    WPP_SF_Dd
0x18002c4de  lea     rdx, [rsp+2C8h+var_278]; struct _WatchDogEntry *
0x18002c4e3  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002c4e8  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002c4ef  jz      short loc_18002C50A
0x18002c4f1  mov     edx, 0CBh
0x18002c4f6  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002c4fd  mov     ecx, 404h
0x18002c502  mov     r9d, ebx
0x18002c505  call    WPP_SF_D
0x18002c50a  mov     eax, ebx
0x18002c50c  mov     rbx, [rsp+2C8h+arg_0]
0x18002c514  add     rsp, 290h
0x18002c51b  pop     r15
0x18002c51d  pop     r14
0x18002c51f  pop     r13
0x18002c521  pop     r12
0x18002c523  pop     rdi
0x18002c524  pop     rsi
0x18002c525  pop     rbp
0x18002c526  retn
```
