# RpcSrvMadcapEnumerateScopes

- ea: `0x18002a190`
- end: `0x18002a2ff`
- name: `RpcSrvMadcapEnumerateScopes`
- size: `367`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x18002a190`
- `0x18002a308`
- `0x180036dc0`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18002a279`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18002a279`
- `RPCRT4!RpcImpersonateClient` at `0x18002a236`
- `RPCRT4!RpcImpersonateClient` at `0x18002a236`
- `RPCRT4!RpcRevertToSelf` at `0x18002a28b`
- `RPCRT4!RpcRevertToSelf` at `0x18002a2e0`
- `RPCRT4!RpcRevertToSelf` at `0x18002a28b`
- `RPCRT4!RpcRevertToSelf` at `0x18002a2e0`

## pseudocode

```c
__int64 __fastcall RpcSrvMadcapEnumerateScopes(
        CRpcWatchDog *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        _DWORD *a6,
        __int64 a7)
{
  unsigned int v8; // r14d
  unsigned __int16 v9; // r15
  int v11; // esi
  unsigned int v12; // ebx
  unsigned int v13; // eax
  HLOCAL v14; // rax
  _OWORD v15[5]; // [rsp+40h] [rbp-58h] BYREF

  memset(v15, 0, 32);
  v8 = a3;
  v9 = a2;
  if ( g_fVelocityApistubStyleUpdate )
    return RpcSrvMadcapEnumerateScopes_New(a1, a2, a3, a4, a5, a6, (__int64)a6);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 235, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
  if ( !a6 )
  {
    v11 = 0;
    v12 = 87;
    goto LABEL_13;
  }
  *(_QWORD *)&v15[0] = RpcSrvMadcapEnumerateScopes;
  CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)v15, a3);
  v11 = 1;
  v13 = RpcImpersonateClient(0);
  v12 = v13;
  if ( !v13 )
  {
    if ( a4 )
    {
      v14 = LocalAlloc(0x40u, (unsigned int)*a6);
      *(_QWORD *)(a5 + 8) = v14;
      if ( !v14 )
      {
        v12 = 8;
        RpcRevertToSelf();
        goto LABEL_13;
      }
      *(_DWORD *)(a5 + 4) = *a6;
    }
    v12 = EnumerateScopes(v9, v8, *(_QWORD *)(a5 + 8), a6, a7);
    RpcRevertToSelf();
LABEL_19:
    CRpcWatchDog::RemoveEntry(a1, (struct _WatchDogEntry *)v15);
    return v12;
  }
  if ( (xmmword_1800616A0 & 2) == 0 )
    goto LABEL_15;
  WPP_SF_D(1025, 236, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v13);
LABEL_13:
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 237, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v12);
LABEL_15:
  if ( v11 )
    goto LABEL_19;
  return v12;
}

```

## disassembly

```asm
0x18002a190  push    rbx
0x18002a192  push    rbp
0x18002a193  push    rsi
0x18002a194  push    rdi
0x18002a195  push    r14
0x18002a197  push    r15
0x18002a199  sub     rsp, 68h
0x18002a19d  cmp     cs:g_fVelocityApistubStyleUpdate, 0
0x18002a1a4  xorps   xmm0, xmm0
0x18002a1a7  movups  [rsp+98h+var_58], xmm0
0x18002a1ac  mov     ebp, r9d
0x18002a1af  mov     r14d, r8d
0x18002a1b2  movups  [rsp+98h+var_48], xmm0
0x18002a1b7  movzx   r15d, dx
0x18002a1bb  jz      short loc_18002A1E6
0x18002a1bd  mov     rax, [rsp+98h+arg_28]
0x18002a1c5  mov     [rsp+98h+var_68], rax
0x18002a1ca  mov     [rsp+98h+var_70], rax
0x18002a1cf  mov     rax, [rsp+98h+arg_20]
0x18002a1d7  mov     [rsp+98h+var_78], rax
0x18002a1dc  call    RpcSrvMadcapEnumerateScopes_New
0x18002a1e1  jmp     loc_18002A2F2
0x18002a1e6  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002a1ed  jz      short loc_18002A205
0x18002a1ef  mov     edx, 0EBh
0x18002a1f4  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a1fb  mov     ecx, 404h
0x18002a200  call    WPP_SF_
0x18002a205  mov     rdi, [rsp+98h+arg_28]
0x18002a20d  test    rdi, rdi
0x18002a210  jnz     short loc_18002A219
0x18002a212  xor     esi, esi
0x18002a214  lea     ebx, [rdi+57h]
0x18002a217  jmp     short loc_18002A291
0x18002a219  lea     rax, RpcSrvMadcapEnumerateScopes
0x18002a220  lea     rdx, [rsp+98h+var_58]; struct _WatchDogEntry *
0x18002a225  mov     qword ptr [rsp+98h+var_58], rax
0x18002a22a  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002a22f  xor     ecx, ecx; BindingHandle
0x18002a231  mov     esi, 1
0x18002a236  call    cs:__imp_RpcImpersonateClient
0x18002a23c  mov     ebx, eax
0x18002a23e  test    eax, eax
0x18002a240  jz      short loc_18002A266
0x18002a242  test    byte ptr cs:xmmword_1800616A0, 2
0x18002a249  jz      short loc_18002A2B3
0x18002a24b  mov     edx, 0ECh
0x18002a250  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a257  mov     ecx, 401h
0x18002a25c  mov     r9d, eax
0x18002a25f  call    WPP_SF_D
0x18002a264  jmp     short loc_18002A291
0x18002a266  mov     rbx, [rsp+98h+arg_20]
0x18002a26e  test    ebp, ebp
0x18002a270  jz      short loc_18002A2BE
0x18002a272  mov     edx, [rdi]; uBytes
0x18002a274  mov     ecx, 40h ; '@'; uFlags
0x18002a279  call    cs:__imp_LocalAlloc
0x18002a27f  mov     [rbx+8], rax
0x18002a283  test    rax, rax
0x18002a286  jnz     short loc_18002A2B9
0x18002a288  lea     ebx, [rax+8]
0x18002a28b  call    cs:__imp_RpcRevertToSelf
0x18002a291  test    byte ptr cs:xmmword_1800616A0, 2
0x18002a298  jz      short loc_18002A2B3
0x18002a29a  mov     edx, 0EDh
0x18002a29f  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a2a6  mov     ecx, 401h
0x18002a2ab  mov     r9d, ebx
0x18002a2ae  call    WPP_SF_D
0x18002a2b3  test    esi, esi
0x18002a2b5  jz      short loc_18002A2F0
0x18002a2b7  jmp     short loc_18002A2E6
0x18002a2b9  mov     eax, [rdi]
0x18002a2bb  mov     [rbx+4], eax
0x18002a2be  mov     rax, [rsp+98h+arg_30]
0x18002a2c6  mov     r9, rdi
0x18002a2c9  mov     r8, [rbx+8]
0x18002a2cd  mov     edx, r14d
0x18002a2d0  movzx   ecx, r15w
0x18002a2d4  mov     [rsp+98h+var_78], rax
0x18002a2d9  call    EnumerateScopes
0x18002a2de  mov     ebx, eax
0x18002a2e0  call    cs:__imp_RpcRevertToSelf
0x18002a2e6  lea     rdx, [rsp+98h+var_58]; struct _WatchDogEntry *
0x18002a2eb  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002a2f0  mov     eax, ebx
0x18002a2f2  add     rsp, 68h
0x18002a2f6  pop     r15
0x18002a2f8  pop     r14
0x18002a2fa  pop     rdi
0x18002a2fb  pop     rsi
0x18002a2fc  pop     rbp
0x18002a2fd  pop     rbx
0x18002a2fe  retn
```
