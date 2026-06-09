# MntUnmountAll

- ea: `0x140024c60`
- end: `0x140024f65`
- name: `MntUnmountAll`
- size: `773`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140034990`

## callees

- `0x140001010`
- `0x1400010c0`
- `0x140001600`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140024c60`
- `0x14002d1e4`
- `0x14003aba0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140024dcc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140024dec`
- `ntoskrnl!ExReleaseResourceLite` at `0x140024dcc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140024dec`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140024d9b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140024d9b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140024d8a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140024d8a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024dd8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024df8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024dd8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024df8`
- `rpcxdr!OncRpcSendReplyAndDestroy` at `0x140024dbd`
- `rpcxdr!OncRpcSendReplyAndDestroy` at `0x140024dbd`
- `rpcxdr!OncRpcBuildCall` at `0x140024d74`
- `rpcxdr!OncRpcBuildCall` at `0x140024d74`
- `rpcxdr!OncRpcDestroy` at `0x140024ea7`
- `rpcxdr!OncRpcDestroy` at `0x140024eb8`
- `rpcxdr!OncRpcDestroy` at `0x140024ea7`
- `rpcxdr!OncRpcDestroy` at `0x140024eb8`

## pseudocode

```c
NTSTATUS __fastcall MntUnmountAll(_QWORD *a1)
{
  __int64 v2; // rax
  __int128 v3; // xmm0
  __int64 v4; // rbx
  int v5; // esi
  __int64 v6; // rcx
  int v7; // edx
  NTSTATUS result; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // [rsp+50h] [rbp-B0h] BYREF
  int v13; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v14; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v15[12]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v16; // [rsp+D0h] [rbp-30h] BYREF
  int v17; // [rsp+E0h] [rbp-20h]
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+E8h] [rbp-18h] BYREF
  int *v19; // [rsp+108h] [rbp+8h]
  __int64 v20; // [rsp+110h] [rbp+10h]

  v12 = 0;
  v14 = 0;
  memset(v15, 0, 0x54u);
  v2 = a1[6];
  v3 = *(_OWORD *)(v2 + 1376);
  v17 = *(_DWORD *)(v2 + 1392);
  v16 = v3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids, a1[8]);
  v4 = a1[4];
  *(_OWORD *)&v15[1] = DaSystemUnixId;
  *(_OWORD *)&v15[5] = xmmword_1400410F0;
  LODWORD(v15[0]) = 1;
  *(_OWORD *)&v15[3] = xmmword_1400410E0;
  *(_OWORD *)&v15[7] = xmmword_140041100;
  *(_OWORD *)((char *)&v15[8] + 4) = *(__int128 *)((char *)&xmmword_140041100 + 12);
  v5 = OncRpcBuildCall(
         &v12,
         v4 + 44,
         *(unsigned int *)(v4 + 8),
         *(unsigned int *)(v4 + 12),
         *(_DWORD *)(v4 + 16),
         4,
         0,
         v15);
  if ( v5 >= 0 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite(*(PERESOURCE *)v4, 1u);
    if ( *(_DWORD *)(v4 + 8) == 17 && (v6 = *(_QWORD *)(v4 + 24)) != 0 )
    {
      OncRpcSendReplyAndDestroy(v6, 0, v12);
      ExReleaseResourceLite(*(PERESOURCE *)v4);
      KeLeaveCriticalRegion();
    }
    else
    {
      ExReleaseResourceLite(*(PERESOURCE *)v4);
      KeLeaveCriticalRegion();
      v5 = NfsSendWaitReplyWait(a1[6], v7, 0, 0, (__int64)&v16, v4, v12, (__int64)&v14, 0, 0);
      if ( v5 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids);
        if ( v14 )
          OncRpcDestroy(v14);
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          43,
          WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids,
          (unsigned int)v5);
      }
      OncRpcDestroy(v12);
      NfsForceDisconnect(v4, 0);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids, a1[8]);
  result = dword_140041028;
  if ( (unsigned int)dword_140041028 > 5 )
  {
    result = tlgKeywordOn();
    if ( (_BYTE)result )
    {
      v13 = v5;
      v19 = &v13;
      v20 = 4;
      return tlgWriteTransfer_EtwWriteTransfer(v9, (unsigned __int8 *)&byte_14003E455, v10, v11, 3u, &v18);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140024c60  mov     [rsp-8+arg_8], rbx
0x140024c65  mov     [rsp-8+arg_10], rsi
0x140024c6a  push    rbp
0x140024c6b  push    rdi
0x140024c6c  push    r12
0x140024c6e  lea     rbp, [rsp-20h]
0x140024c73  sub     rsp, 120h
0x140024c7a  mov     rax, cs:__security_cookie
0x140024c81  xor     rax, rsp
0x140024c84  mov     [rbp+30h+var_18], rax
0x140024c88  xor     eax, eax
0x140024c8a  mov     [rsp+130h+var_E0], 0
0x140024c93  mov     rdi, rcx
0x140024c96  mov     [rsp+130h+var_D0], 0
0x140024c9f  xor     edx, edx; Val
0x140024ca1  mov     [rsp+130h+var_BC], eax
0x140024ca5  lea     rcx, [rsp+130h+var_C0]; void *
0x140024caa  lea     r8d, [rax+54h]; Size
0x140024cae  call    memset
0x140024cb3  mov     rax, [rdi+30h]
0x140024cb7  movups  xmm0, xmmword ptr [rax+560h]
0x140024cbe  mov     eax, [rax+570h]
0x140024cc4  mov     [rbp+30h+var_50], eax
0x140024cc7  movups  [rbp+30h+var_60], xmm0
0x140024ccb  mov     rcx, cs:WPP_GLOBAL_Control
0x140024cd2  lea     r12, WPP_GLOBAL_Control
0x140024cd9  cmp     rcx, r12
0x140024cdc  jz      short loc_140024CFE
0x140024cde  mov     eax, [rcx+2Ch]
0x140024ce1  test    al, 10h
0x140024ce3  jz      short loc_140024CFE
0x140024ce5  mov     r9, [rdi+40h]
0x140024ce9  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x140024cf0  mov     rcx, [rcx+18h]
0x140024cf4  mov     edx, 2Ah ; '*'
0x140024cf9  call    WPP_SF_Z
0x140024cfe  mov     rbx, [rdi+20h]
0x140024d02  lea     rax, [rsp+130h+var_C0]
0x140024d07  movaps  xmm0, cs:DaSystemUnixId
0x140024d0e  lea     rcx, [rsp+130h+var_E0]
0x140024d13  movaps  xmm1, cs:xmmword_1400410E0
0x140024d1a  movups  [rsp+130h+var_B8], xmm0
0x140024d1f  lea     rdx, [rbx+2Ch]
0x140024d23  mov     [rsp+130h+var_F8], rax
0x140024d28  movaps  xmm0, cs:xmmword_1400410F0
0x140024d2f  movups  [rbp+30h+var_98], xmm0
0x140024d33  mov     [rsp+130h+var_C0], 1
0x140024d3b  movups  xmm0, cs:xmmword_140041100+0Ch
0x140024d42  mov     dword ptr [rsp+130h+var_100], 0
0x140024d4a  movups  [rbp+30h+var_A8], xmm1
0x140024d4e  mov     dword ptr [rsp+130h+var_108], 4
0x140024d56  movaps  xmm1, cs:xmmword_140041100
0x140024d5d  movups  [rbp+30h+var_88], xmm1
0x140024d61  movups  [rbp+30h+var_88+0Ch], xmm0
0x140024d65  mov     eax, [rbx+10h]
0x140024d68  mov     r9d, [rbx+0Ch]
0x140024d6c  mov     r8d, [rbx+8]
0x140024d70  mov     [rsp+130h+var_110], eax
0x140024d74  call    cs:__imp_OncRpcBuildCall
0x140024d7b  nop     dword ptr [rax+rax+00h]
0x140024d80  mov     esi, eax
0x140024d82  test    eax, eax
0x140024d84  js      loc_140024ECE
0x140024d8a  call    cs:__imp_KeEnterCriticalRegion
0x140024d91  nop     dword ptr [rax+rax+00h]
0x140024d96  mov     rcx, [rbx]; Resource
0x140024d99  mov     dl, 1; Wait
0x140024d9b  call    cs:__imp_ExAcquireResourceSharedLite
0x140024da2  nop     dword ptr [rax+rax+00h]
0x140024da7  cmp     dword ptr [rbx+8], 11h
0x140024dab  jnz     short loc_140024DE9
0x140024dad  mov     rcx, [rbx+18h]
0x140024db1  test    rcx, rcx
0x140024db4  jz      short loc_140024DE9
0x140024db6  mov     r8, [rsp+130h+var_E0]
0x140024dbb  xor     edx, edx
0x140024dbd  call    cs:__imp_OncRpcSendReplyAndDestroy
0x140024dc4  nop     dword ptr [rax+rax+00h]
0x140024dc9  mov     rcx, [rbx]; Resource
0x140024dcc  call    cs:__imp_ExReleaseResourceLite
0x140024dd3  nop     dword ptr [rax+rax+00h]
0x140024dd8  call    cs:__imp_KeLeaveCriticalRegion
0x140024ddf  nop     dword ptr [rax+rax+00h]
0x140024de4  jmp     loc_140024ECE
0x140024de9  mov     rcx, [rbx]; Resource
0x140024dec  call    cs:__imp_ExReleaseResourceLite
0x140024df3  nop     dword ptr [rax+rax+00h]
0x140024df8  call    cs:__imp_KeLeaveCriticalRegion
0x140024dff  nop     dword ptr [rax+rax+00h]
0x140024e04  mov     rcx, [rdi+30h]
0x140024e08  lea     rax, [rsp+130h+var_D0]
0x140024e0d  mov     [rsp+130h+var_E8], 0
0x140024e15  xor     r9d, r9d
0x140024e18  mov     [rsp+130h+var_F0], 0
0x140024e1d  xor     r8d, r8d
0x140024e20  mov     [rsp+130h+var_F8], rax
0x140024e25  mov     rax, [rsp+130h+var_E0]
0x140024e2a  mov     [rsp+130h+var_100], rax
0x140024e2f  lea     rax, [rbp+30h+var_60]
0x140024e33  mov     [rsp+130h+var_108], rbx
0x140024e38  mov     qword ptr [rsp+130h+var_110], rax
0x140024e3d  call    NfsSendWaitReplyWait
0x140024e42  mov     esi, eax
0x140024e44  test    eax, eax
0x140024e46  jns     short loc_140024E75
0x140024e48  mov     rcx, cs:WPP_GLOBAL_Control
0x140024e4f  cmp     rcx, r12
0x140024e52  jz      short loc_140024EB3
0x140024e54  mov     eax, [rcx+2Ch]
0x140024e57  test    al, 1
0x140024e59  jz      short loc_140024EB3
0x140024e5b  mov     rcx, [rcx+18h]
0x140024e5f  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x140024e66  mov     edx, 2Bh ; '+'
0x140024e6b  mov     r9d, esi
0x140024e6e  call    WPP_SF_d
0x140024e73  jmp     short loc_140024EB3
0x140024e75  mov     rcx, cs:WPP_GLOBAL_Control
0x140024e7c  cmp     rcx, r12
0x140024e7f  jz      short loc_140024E9D
0x140024e81  mov     eax, [rcx+2Ch]
0x140024e84  test    al, 4
0x140024e86  jz      short loc_140024E9D
0x140024e88  mov     rcx, [rcx+18h]
0x140024e8c  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x140024e93  mov     edx, 2Ch ; ','
0x140024e98  call    WPP_SF_
0x140024e9d  mov     rcx, [rsp+130h+var_D0]
0x140024ea2  test    rcx, rcx
0x140024ea5  jz      short loc_140024EB3
0x140024ea7  call    cs:__imp_OncRpcDestroy
0x140024eae  nop     dword ptr [rax+rax+00h]
0x140024eb3  mov     rcx, [rsp+130h+var_E0]
0x140024eb8  call    cs:__imp_OncRpcDestroy
0x140024ebf  nop     dword ptr [rax+rax+00h]
0x140024ec4  xor     edx, edx
0x140024ec6  mov     rcx, rbx
0x140024ec9  call    NfsForceDisconnect
0x140024ece  mov     rcx, cs:WPP_GLOBAL_Control
0x140024ed5  cmp     rcx, r12
0x140024ed8  jz      short loc_140024EFA
0x140024eda  mov     eax, [rcx+2Ch]
0x140024edd  test    al, 10h
0x140024edf  jz      short loc_140024EFA
0x140024ee1  mov     r9, [rdi+40h]
0x140024ee5  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x140024eec  mov     rcx, [rcx+18h]
0x140024ef0  mov     edx, 2Dh ; '-'
0x140024ef5  call    WPP_SF_Z
0x140024efa  mov     eax, cs:dword_140041028
0x140024f00  cmp     eax, 5
0x140024f03  jbe     short loc_140024F40
0x140024f05  call    _tlgKeywordOn
0x140024f0a  test    al, al
0x140024f0c  jz      short loc_140024F40
0x140024f0e  lea     rax, [rsp+130h+var_D8]
0x140024f13  mov     [rsp+130h+var_D8], esi
0x140024f17  mov     [rbp+30h+var_28], rax
0x140024f1b  lea     rdx, byte_14003E455; int
0x140024f22  lea     rax, [rbp+30h+var_48]
0x140024f26  mov     [rbp+30h+var_20], 4
0x140024f2e  mov     [rsp+130h+var_108], rax; PEVENT_DATA_DESCRIPTOR
0x140024f33  mov     [rsp+130h+var_110], 3; ULONG
0x140024f3b  call    _tlgWriteTransfer_EtwWriteTransfer
0x140024f40  mov     rcx, [rbp+30h+var_18]
0x140024f44  xor     rcx, rsp; StackCookie
0x140024f47  call    __security_check_cookie
0x140024f4c  lea     r11, [rsp+130h+var_10]
0x140024f54  mov     rbx, [r11+28h]
0x140024f58  mov     rsi, [r11+30h]
0x140024f5c  mov     rsp, r11
0x140024f5f  pop     r12
0x140024f61  pop     rdi
0x140024f62  pop     rbp
0x140024f63  retn
```
