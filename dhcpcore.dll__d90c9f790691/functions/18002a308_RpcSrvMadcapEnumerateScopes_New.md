# RpcSrvMadcapEnumerateScopes_New

- ea: `0x18002a308`
- end: `0x18002a43b`
- name: `RpcSrvMadcapEnumerateScopes_New`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002a190`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x18002a308`
- `0x180036dc0`
- `0x18004aa14`
- `0x18004d1a0`
- `0x18004dd28`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18002a3a0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18002a3a0`
- `RPCRT4!RpcImpersonateClient` at `0x18002a383`
- `RPCRT4!RpcImpersonateClient` at `0x18002a383`
- `RPCRT4!RpcRevertToSelf` at `0x18002a360`
- `RPCRT4!RpcRevertToSelf` at `0x18002a3b2`
- `RPCRT4!RpcRevertToSelf` at `0x18002a360`
- `RPCRT4!RpcRevertToSelf` at `0x18002a3b2`

## pseudocode

```c
__int64 __fastcall RpcSrvMadcapEnumerateScopes_New(
        CRpcWatchDog *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        _DWORD *a6,
        __int64 a7)
{
  unsigned __int16 v7; // r14
  unsigned int v9; // ebp
  unsigned int v10; // ebx
  unsigned int v11; // eax
  CRpcWatchDog *v12; // rcx
  HLOCAL v13; // rax
  _QWORD v15[11]; // [rsp+40h] [rbp-58h] BYREF

  v7 = a2;
  memset(v15, 0, 32);
  v9 = a3;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_dllq(a1, a2, a3, (unsigned __int16)a2, a3, a4, a7);
  if ( !a6 )
  {
    v10 = 8;
    RpcRevertToSelf();
    goto LABEL_15;
  }
  v15[0] = RpcSrvMadcapEnumerateScopes;
  CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)v15, a3);
  v11 = RpcImpersonateClient(0);
  v10 = v11;
  if ( v11 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_Dd(1025, 233, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v11, v11);
    goto LABEL_14;
  }
  if ( !a4 )
    goto LABEL_11;
  v13 = LocalAlloc(0x40u, (unsigned int)*a6);
  *(_QWORD *)(a5 + 8) = v13;
  if ( v13 )
  {
    *(_DWORD *)(a5 + 4) = *a6;
LABEL_11:
    v10 = EnumerateScopes(v7, v9, *(_QWORD *)(a5 + 8), a6, a7);
    goto LABEL_9;
  }
  v10 = 8;
LABEL_9:
  RpcRevertToSelf();
LABEL_14:
  CRpcWatchDog::RemoveEntry(v12, (struct _WatchDogEntry *)v15);
LABEL_15:
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 234, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18002a308  mov     rax, rsp
0x18002a30b  push    rbx
0x18002a30c  push    rbp
0x18002a30d  push    rsi
0x18002a30e  push    rdi
0x18002a30f  push    r14
0x18002a311  push    r15
0x18002a313  sub     rsp, 68h
0x18002a317  xorps   xmm0, xmm0
0x18002a31a  movzx   r14d, dx
0x18002a31e  movups  xmmword ptr [rax-58h], xmm0
0x18002a322  mov     esi, r9d
0x18002a325  mov     ebp, r8d
0x18002a328  movups  xmmword ptr [rax-48h], xmm0
0x18002a32c  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002a333  mov     r15, [rsp+98h+arg_30]
0x18002a33b  jz      short loc_18002A350
0x18002a33d  mov     [rax-68h], r15
0x18002a341  mov     r9d, r14d
0x18002a344  mov     [rax-70h], esi
0x18002a347  mov     [rax-78h], r8d
0x18002a34b  call    WPP_SF_dllq
0x18002a350  mov     rdi, [rsp+98h+arg_28]
0x18002a358  test    rdi, rdi
0x18002a35b  jnz     short loc_18002A36B
0x18002a35d  lea     ebx, [rdi+8]
0x18002a360  call    cs:__imp_RpcRevertToSelf
0x18002a366  jmp     loc_18002A40A
0x18002a36b  lea     rax, RpcSrvMadcapEnumerateScopes
0x18002a372  lea     rdx, [rsp+98h+var_58]; struct _WatchDogEntry *
0x18002a377  mov     [rsp+98h+var_58], rax
0x18002a37c  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002a381  xor     ecx, ecx; BindingHandle
0x18002a383  call    cs:__imp_RpcImpersonateClient
0x18002a389  mov     ebx, eax
0x18002a38b  test    eax, eax
0x18002a38d  jnz     short loc_18002A3DA
0x18002a38f  mov     rbx, [rsp+98h+arg_20]
0x18002a397  test    esi, esi
0x18002a399  jz      short loc_18002A3BF
0x18002a39b  mov     edx, [rdi]; uBytes
0x18002a39d  lea     ecx, [rax+40h]; uFlags
0x18002a3a0  call    cs:__imp_LocalAlloc
0x18002a3a6  mov     [rbx+8], rax
0x18002a3aa  test    rax, rax
0x18002a3ad  jnz     short loc_18002A3BA
0x18002a3af  lea     ebx, [rax+8]
0x18002a3b2  call    cs:__imp_RpcRevertToSelf
0x18002a3b8  jmp     short loc_18002A400
0x18002a3ba  mov     eax, [rdi]
0x18002a3bc  mov     [rbx+4], eax
0x18002a3bf  mov     r8, [rbx+8]
0x18002a3c3  mov     r9, rdi
0x18002a3c6  mov     edx, ebp
0x18002a3c8  mov     [rsp+98h+var_78], r15
0x18002a3cd  movzx   ecx, r14w
0x18002a3d1  call    EnumerateScopes
0x18002a3d6  mov     ebx, eax
0x18002a3d8  jmp     short loc_18002A3B2
0x18002a3da  test    byte ptr cs:xmmword_1800616A0, 2
0x18002a3e1  jz      short loc_18002A400
0x18002a3e3  mov     edx, 0E9h
0x18002a3e8  mov     dword ptr [rsp+98h+var_78], eax
0x18002a3ec  mov     ecx, 401h
0x18002a3f1  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a3f8  mov     r9d, eax
0x18002a3fb  call    WPP_SF_Dd
0x18002a400  lea     rdx, [rsp+98h+var_58]; struct _WatchDogEntry *
0x18002a405  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002a40a  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002a411  jz      short loc_18002A42C
0x18002a413  mov     edx, 0EAh
0x18002a418  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002a41f  mov     ecx, 404h
0x18002a424  mov     r9d, ebx
0x18002a427  call    WPP_SF_D
0x18002a42c  mov     eax, ebx
0x18002a42e  add     rsp, 68h
0x18002a432  pop     r15
0x18002a434  pop     r14
0x18002a436  pop     rdi
0x18002a437  pop     rsi
0x18002a438  pop     rbp
0x18002a439  pop     rbx
0x18002a43a  retn
```
