# RpcSrvReleaseIpAddressLeaseEx_New

- ea: `0x18002bb00`
- end: `0x18002bcc8`
- name: `RpcSrvReleaseIpAddressLeaseEx_New`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18002b830`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x18002bb00`
- `0x18003c554`
- `0x18004a63c`
- `0x18004d1a0`
- `0x18004dd28`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18002bb71`
- `RPCRT4!RpcImpersonateClient` at `0x18002bb71`
- `RPCRT4!RpcRevertToSelf` at `0x18002bb4e`
- `RPCRT4!RpcRevertToSelf` at `0x18002bc5a`
- `RPCRT4!RpcRevertToSelf` at `0x18002bb4e`
- `RPCRT4!RpcRevertToSelf` at `0x18002bc5a`

## pseudocode

```c
__int64 __fastcall RpcSrvReleaseIpAddressLeaseEx_New(
        CRpcWatchDog *a1,
        __int64 a2,
        u_long *a3,
        _OWORD *a4,
        _OWORD *a5,
        unsigned int a6)
{
  u_long v8; // ebp
  unsigned int v9; // ebx
  unsigned int v10; // eax
  CRpcWatchDog *v11; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  _OWORD *v15; // rcx
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  unsigned int *v23; // rcx
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v32; // [rsp+30h] [rbp-268h] BYREF
  __int128 v33; // [rsp+40h] [rbp-258h]
  _BYTE v34[272]; // [rsp+50h] [rbp-248h] BYREF
  unsigned int v35[78]; // [rsp+160h] [rbp-138h] BYREF

  v32 = 0;
  v8 = a2;
  v33 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_Dqd(a1, a2, a3, (unsigned int)a2, a3, a6, v32, *((_QWORD *)&v32 + 1), v33, *((_QWORD *)&v33 + 1));
  if ( a3 )
  {
    *(_QWORD *)&v32 = RpcSrvReleaseIpAddressLeaseEx;
    CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)&v32, (int)a3);
    v10 = RpcImpersonateClient(0);
    v9 = v10;
    if ( v10 )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_Dd(1025, 208, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v10, v10);
    }
    else
    {
      v13 = 2;
      v14 = 2;
      v15 = v34;
      do
      {
        v16 = a5[1];
        *v15 = *a5;
        v17 = a5[2];
        v15[1] = v16;
        v18 = a5[3];
        v15[2] = v17;
        v19 = a5[4];
        v15[3] = v18;
        v20 = a5[5];
        v15[4] = v19;
        v21 = a5[6];
        v15[5] = v20;
        v22 = a5[7];
        a5 += 8;
        v15[6] = v21;
        v15[7] = v22;
        v15 += 8;
        --v14;
      }
      while ( v14 );
      *(_DWORD *)v15 = *(_DWORD *)a5;
      v23 = v35;
      do
      {
        v24 = a4[1];
        *(_OWORD *)v23 = *a4;
        v25 = a4[2];
        *((_OWORD *)v23 + 1) = v24;
        v26 = a4[3];
        *((_OWORD *)v23 + 2) = v25;
        v27 = a4[4];
        *((_OWORD *)v23 + 3) = v26;
        v28 = a4[5];
        *((_OWORD *)v23 + 4) = v27;
        v29 = a4[6];
        *((_OWORD *)v23 + 5) = v28;
        v30 = a4[7];
        a4 += 8;
        *((_OWORD *)v23 + 6) = v29;
        *((_OWORD *)v23 + 7) = v30;
        v23 += 32;
        --v13;
      }
      while ( v13 );
      *v23 = *(_DWORD *)a4;
      v9 = ReleaseIpAddressLeaseEx(v8, a3, v35, (__int64)v34, a6);
      RpcRevertToSelf();
    }
    CRpcWatchDog::RemoveEntry(v11, (struct _WatchDogEntry *)&v32);
  }
  else
  {
    v9 = 87;
    RpcRevertToSelf();
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 209, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18002bb00  push    rbx
0x18002bb02  push    rbp
0x18002bb03  push    rsi
0x18002bb04  push    rdi
0x18002bb05  push    r14
0x18002bb07  sub     rsp, 270h
0x18002bb0e  xorps   xmm0, xmm0
0x18002bb11  mov     rdi, r9
0x18002bb14  movups  [rsp+298h+var_268], xmm0
0x18002bb19  mov     rsi, r8
0x18002bb1c  mov     ebp, edx
0x18002bb1e  movups  [rsp+298h+var_258], xmm0
0x18002bb23  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002bb2a  mov     r14d, [rsp+298h+arg_28]
0x18002bb32  jz      short loc_18002BB46
0x18002bb34  mov     [rsp+298h+var_270], r14d
0x18002bb39  mov     r9d, edx
0x18002bb3c  mov     qword ptr [rsp+298h+var_278], r8
0x18002bb41  call    WPP_SF_Dqd
0x18002bb46  test    rsi, rsi
0x18002bb49  jnz     short loc_18002BB59
0x18002bb4b  lea     ebx, [rsi+57h]
0x18002bb4e  call    cs:__imp_RpcRevertToSelf
0x18002bb54  jmp     loc_18002BC96
0x18002bb59  lea     rax, RpcSrvReleaseIpAddressLeaseEx
0x18002bb60  lea     rdx, [rsp+298h+var_268]; struct _WatchDogEntry *
0x18002bb65  mov     qword ptr [rsp+298h+var_268], rax
0x18002bb6a  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002bb6f  xor     ecx, ecx; BindingHandle
0x18002bb71  call    cs:__imp_RpcImpersonateClient
0x18002bb77  mov     ebx, eax
0x18002bb79  test    eax, eax
0x18002bb7b  jnz     loc_18002BC62
0x18002bb81  mov     rax, [rsp+298h+arg_20]
0x18002bb89  lea     edx, [rbx+2]
0x18002bb8c  mov     r8d, edx
0x18002bb8f  lea     r9d, [rdx+7Eh]
0x18002bb93  lea     rcx, [rsp+298h+var_248]
0x18002bb98  movups  xmm0, xmmword ptr [rax]
0x18002bb9b  movups  xmm1, xmmword ptr [rax+10h]
0x18002bb9f  movups  xmmword ptr [rcx], xmm0
0x18002bba2  movups  xmm0, xmmword ptr [rax+20h]
0x18002bba6  movups  xmmword ptr [rcx+10h], xmm1
0x18002bbaa  movups  xmm1, xmmword ptr [rax+30h]
0x18002bbae  movups  xmmword ptr [rcx+20h], xmm0
0x18002bbb2  movups  xmm0, xmmword ptr [rax+40h]
0x18002bbb6  movups  xmmword ptr [rcx+30h], xmm1
0x18002bbba  movups  xmm1, xmmword ptr [rax+50h]
0x18002bbbe  movups  xmmword ptr [rcx+40h], xmm0
0x18002bbc2  movups  xmm0, xmmword ptr [rax+60h]
0x18002bbc6  movups  xmmword ptr [rcx+50h], xmm1
0x18002bbca  movups  xmm1, xmmword ptr [rax+70h]
0x18002bbce  add     rax, r9
0x18002bbd1  movups  xmmword ptr [rcx+60h], xmm0
0x18002bbd5  movups  xmmword ptr [rcx+70h], xmm1
0x18002bbd9  add     rcx, r9
0x18002bbdc  sub     r8, 1
0x18002bbe0  jnz     short loc_18002BB98
0x18002bbe2  mov     eax, [rax]
0x18002bbe4  mov     [rcx], eax
0x18002bbe6  lea     rcx, [rsp+298h+var_138]
0x18002bbee  movups  xmm0, xmmword ptr [rdi]
0x18002bbf1  movups  xmm1, xmmword ptr [rdi+10h]
0x18002bbf5  movups  xmmword ptr [rcx], xmm0
0x18002bbf8  movups  xmm0, xmmword ptr [rdi+20h]
0x18002bbfc  movups  xmmword ptr [rcx+10h], xmm1
0x18002bc00  movups  xmm1, xmmword ptr [rdi+30h]
0x18002bc04  movups  xmmword ptr [rcx+20h], xmm0
0x18002bc08  movups  xmm0, xmmword ptr [rdi+40h]
0x18002bc0c  movups  xmmword ptr [rcx+30h], xmm1
0x18002bc10  movups  xmm1, xmmword ptr [rdi+50h]
0x18002bc14  movups  xmmword ptr [rcx+40h], xmm0
0x18002bc18  movups  xmm0, xmmword ptr [rdi+60h]
0x18002bc1c  movups  xmmword ptr [rcx+50h], xmm1
0x18002bc20  movups  xmm1, xmmword ptr [rdi+70h]
0x18002bc24  add     rdi, r9
0x18002bc27  movups  xmmword ptr [rcx+60h], xmm0
0x18002bc2b  movups  xmmword ptr [rcx+70h], xmm1
0x18002bc2f  add     rcx, r9
0x18002bc32  sub     rdx, 1
0x18002bc36  jnz     short loc_18002BBEE
0x18002bc38  mov     eax, [rdi]
0x18002bc3a  lea     r9, [rsp+298h+var_248]
0x18002bc3f  mov     [rcx], eax
0x18002bc41  lea     r8, [rsp+298h+var_138]
0x18002bc49  mov     ecx, ebp; hostlong
0x18002bc4b  mov     [rsp+298h+var_278], r14d; int
0x18002bc50  mov     rdx, rsi
0x18002bc53  call    ReleaseIpAddressLeaseEx
0x18002bc58  mov     ebx, eax
0x18002bc5a  call    cs:__imp_RpcRevertToSelf
0x18002bc60  jmp     short loc_18002BC8C
0x18002bc62  mov     edx, 2
0x18002bc67  test    byte ptr cs:xmmword_1800616A0, dl
0x18002bc6d  jz      short loc_18002BC8C
0x18002bc6f  mov     edx, 0D0h
0x18002bc74  mov     [rsp+298h+var_278], eax
0x18002bc78  mov     ecx, 401h
0x18002bc7d  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002bc84  mov     r9d, eax
0x18002bc87  call    WPP_SF_Dd
0x18002bc8c  lea     rdx, [rsp+298h+var_268]; struct _WatchDogEntry *
0x18002bc91  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002bc96  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002bc9d  jz      short loc_18002BCB8
0x18002bc9f  mov     edx, 0D1h
0x18002bca4  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002bcab  mov     ecx, 404h
0x18002bcb0  mov     r9d, ebx
0x18002bcb3  call    WPP_SF_D
0x18002bcb8  mov     eax, ebx
0x18002bcba  add     rsp, 270h
0x18002bcc1  pop     r14
0x18002bcc3  pop     rdi
0x18002bcc4  pop     rsi
0x18002bcc5  pop     rbp
0x18002bcc6  pop     rbx
0x18002bcc7  retn
```
