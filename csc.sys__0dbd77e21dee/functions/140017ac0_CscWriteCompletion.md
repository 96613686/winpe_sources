# CscWriteCompletion

- ea: `0x140017ac0`
- end: `0x140017cf6`
- name: `CscWriteCompletion`
- size: `566`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140003a00`
- `0x14000e070`
- `0x140014888`
- `0x1400170cc`
- `0x140017ac0`
- `0x1400190ec`
- `0x14001ef50`
- `0x14001f4dc`
- `0x14002f010`
- `0x14002f0f0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140017b21`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140017b21`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140017c7b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140017c7b`

## pseudocode

```c
__int64 __fastcall CscWriteCompletion(PRX_CONTEXT RxContext)
{
  PMRX_FCB pFcb; // rbx
  PMRX_SRV_OPEN pRelevantSrvOpen; // rsi
  _QWORD *Parameter; // r13
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // r8
  int v10; // eax
  int v11; // esi
  unsigned int v12; // ebx
  unsigned int v13; // eax
  int v15; // [rsp+20h] [rbp-49h]
  __int64 v16; // [rsp+28h] [rbp-41h]
  __int128 v17; // [rsp+60h] [rbp-9h] BYREF
  __int128 v18; // [rsp+70h] [rbp+7h]
  __int64 v19; // [rsp+80h] [rbp+17h]
  __int128 v20; // [rsp+88h] [rbp+1Fh] BYREF

  pFcb = RxContext->pFcb;
  pRelevantSrvOpen = RxContext->pRelevantSrvOpen;
  Parameter = RxContext->WorkQueueItem.Parameter;
  v17 = 0;
  v19 = 0;
  v18 = 0;
  v20 = 0;
  KeEnterCriticalRegion();
  CscGetContextsEx(RxContext, RxContext->pFcb, &v17);
  CscUpdateAndCaptureConnectionStateEx(
    (__int64)pFcb,
    (__int64)pRelevantSrvOpen,
    (__int64)RxContext,
    1u,
    (__int64)&v20,
    1);
  *((_QWORD *)&RxContext->9 + 16) = Parameter[2];
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    {
      LODWORD(v16) = HIDWORD(pFcb->SrvOpenList.Flink);
      v15 = (int)pRelevantSrvOpen;
      WPP_SF_qqDDDDDi(WPP_GLOBAL_Control->AttachedDevice, v5, v6, pFcb);
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      if ( (_QWORD)v18 )
        v9 = *(_QWORD *)(v18 + 8);
      else
        v9 = 0;
      if ( (_QWORD)v18 )
        v10 = *(_DWORD *)(v18 + 24);
      else
        v10 = 0;
      v16 = v9;
      v15 = v10;
      WPP_SF_qdq(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_a14d127135023115663fdf7ff6985b18_Traceguids, v18);
    }
  }
  if ( (BYTE1(v20) & 0x40) != 0 )
  {
    v11 = 2133;
    v12 = (BYTE2(v20) & 1) != 0 ? -1073741628 : -1073741300;
  }
  else
  {
    v11 = 0;
    v12 = CscWriteFinalize(RxContext, (__int64)&v17, (char *)&v20, (unsigned int)RxContext->StoredStatus);
  }
  if ( (v20 & 0x20) != 0 )
  {
    CscReadWriteAsyncContextFree(v8, Parameter, v6, v7, v15, v16);
    RxContext->WorkQueueItem.Parameter = 0;
  }
  KeLeaveCriticalRegion();
  v13 = (*((__int64 (__fastcall **)(PRX_CONTEXT))&RxContext->9 + 16))(RxContext);
  if ( !v12 )
    v12 = v13;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_a14d127135023115663fdf7ff6985b18_Traceguids, v12, v11);
  return v12;
}

```

## disassembly

```asm
0x140017ac0  mov     [rsp-8+arg_8], rbx
0x140017ac5  mov     [rsp-8+arg_10], rsi
0x140017aca  push    rbp
0x140017acb  push    rdi
0x140017acc  push    r13
0x140017ace  push    r14
0x140017ad0  push    r15
0x140017ad2  lea     rbp, [rsp-37h]
0x140017ad7  sub     rsp, 0A0h
0x140017ade  mov     rax, cs:__security_cookie
0x140017ae5  xor     rax, rsp
0x140017ae8  mov     [rbp+57h+var_28], rax
0x140017aec  mov     rbx, [rcx+38h]
0x140017af0  xorps   xmm0, xmm0
0x140017af3  mov     rsi, [rcx+48h]
0x140017af7  xor     eax, eax
0x140017af9  mov     r14d, [rcx+238h]
0x140017b00  mov     rdi, rcx
0x140017b03  mov     r15, [rcx+230h]
0x140017b0a  mov     r13, [rcx+110h]
0x140017b11  movups  [rbp+57h+var_60], xmm0
0x140017b15  mov     [rbp+57h+var_40], rax
0x140017b19  movups  [rbp+57h+var_50], xmm0
0x140017b1d  movups  [rbp+57h+var_38], xmm0
0x140017b21  call    cs:__imp_KeEnterCriticalRegion
0x140017b28  nop     dword ptr [rax+rax+00h]
0x140017b2d  mov     rdx, [rdi+38h]
0x140017b31  lea     r8, [rbp+57h+var_60]
0x140017b35  mov     rcx, rdi
0x140017b38  call    CscGetContextsEx
0x140017b3d  lea     rax, [rbp+57h+var_38]
0x140017b41  mov     byte ptr [rsp+0C0h+var_98], 1
0x140017b46  mov     r9b, 1
0x140017b49  mov     [rsp+0C0h+var_A0], rax
0x140017b4e  mov     r8, rdi
0x140017b51  mov     rdx, rsi
0x140017b54  mov     rcx, rbx
0x140017b57  call    CscUpdateAndCaptureConnectionStateEx
0x140017b5c  mov     rax, [r13+10h]
0x140017b60  mov     [rdi+210h], rax
0x140017b67  mov     rcx, cs:WPP_GLOBAL_Control
0x140017b6e  lea     rax, WPP_GLOBAL_Control
0x140017b75  cmp     rcx, rax
0x140017b78  jz      loc_140017C1E
0x140017b7e  mov     eax, [rcx+2Ch]
0x140017b81  test    al, 20h
0x140017b83  jz      short loc_140017BC5
0x140017b85  mov     eax, [rsi+48h]
0x140017b88  mov     r9, rbx
0x140017b8b  mov     rcx, [rcx+18h]
0x140017b8f  mov     [rsp+0C0h+var_70], r15
0x140017b94  mov     [rsp+0C0h+var_78], r14d
0x140017b99  mov     [rsp+0C0h+var_80], eax
0x140017b9d  mov     eax, [rbx+0A0h]
0x140017ba3  mov     [rsp+0C0h+var_88], eax
0x140017ba7  mov     eax, [rbx+0A4h]
0x140017bad  mov     [rsp+0C0h+var_90], eax
0x140017bb1  mov     eax, [rbx+9Ch]
0x140017bb7  mov     dword ptr [rsp+0C0h+var_98], eax
0x140017bbb  mov     [rsp+0C0h+var_A0], rsi
0x140017bc0  call    WPP_SF_qqDDDDDi
0x140017bc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140017bcc  lea     r14, WPP_GLOBAL_Control
0x140017bd3  cmp     rcx, r14
0x140017bd6  jz      short loc_140017C25
0x140017bd8  mov     eax, [rcx+2Ch]
0x140017bdb  test    al, 40h
0x140017bdd  jz      short loc_140017C25
0x140017bdf  mov     r9, qword ptr [rbp+57h+var_50]
0x140017be3  test    r9, r9
0x140017be6  jz      short loc_140017BEE
0x140017be8  mov     r8, [r9+8]
0x140017bec  jmp     short loc_140017BF1
0x140017bee  xor     r8d, r8d
0x140017bf1  test    r9, r9
0x140017bf4  jz      short loc_140017BFC
0x140017bf6  mov     eax, [r9+18h]
0x140017bfa  jmp     short loc_140017BFE
0x140017bfc  xor     eax, eax
0x140017bfe  mov     rcx, [rcx+18h]
0x140017c02  mov     edx, 3Ch ; '<'
0x140017c07  mov     [rsp+0C0h+var_98], r8
0x140017c0c  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x140017c13  mov     dword ptr [rsp+0C0h+var_A0], eax
0x140017c17  call    WPP_SF_qdq
0x140017c1c  jmp     short loc_140017C25
0x140017c1e  lea     r14, WPP_GLOBAL_Control
0x140017c25  test    byte ptr [rbp+57h+var_38+1], 40h
0x140017c29  jz      short loc_140017C47
0x140017c2b  mov     al, byte ptr [rbp+57h+var_38+2]
0x140017c2e  mov     esi, 855h
0x140017c33  and     al, 1
0x140017c35  neg     al
0x140017c37  sbb     ebx, ebx
0x140017c39  and     ebx, 0FFFFFEB8h
0x140017c3f  add     ebx, 0C000020Ch
0x140017c45  jmp     short loc_140017C62
0x140017c47  mov     r9d, [rdi+0B0h]
0x140017c4e  lea     r8, [rbp+57h+var_38]
0x140017c52  xor     esi, esi
0x140017c54  lea     rdx, [rbp+57h+var_60]
0x140017c58  mov     rcx, rdi; RxContext
0x140017c5b  call    CscWriteFinalize
0x140017c60  mov     ebx, eax
0x140017c62  test    byte ptr [rbp+57h+var_38], 20h
0x140017c66  jz      short loc_140017C7B
0x140017c68  mov     rdx, r13
0x140017c6b  call    CscReadWriteAsyncContextFree
0x140017c70  mov     qword ptr [rdi+110h], 0
0x140017c7b  call    cs:__imp_KeLeaveCriticalRegion
0x140017c82  nop     dword ptr [rax+rax+00h]
0x140017c87  mov     rax, [rdi+210h]
0x140017c8e  mov     rcx, rdi
0x140017c91  call    _guard_dispatch_icall
0x140017c96  test    ebx, ebx
0x140017c98  cmovz   ebx, eax
0x140017c9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140017ca2  cmp     rcx, r14
0x140017ca5  jz      short loc_140017CCB
0x140017ca7  mov     edx, [rcx+2Ch]
0x140017caa  test    dl, 20h
0x140017cad  jz      short loc_140017CCB
0x140017caf  mov     rcx, [rcx+18h]
0x140017cb3  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x140017cba  mov     edx, 3Dh ; '='
0x140017cbf  mov     dword ptr [rsp+0C0h+var_A0], esi
0x140017cc3  mov     r9d, ebx
0x140017cc6  call    WPP_SF_Dd
0x140017ccb  mov     eax, ebx
0x140017ccd  mov     rcx, [rbp+57h+var_28]
0x140017cd1  xor     rcx, rsp; StackCookie
0x140017cd4  call    __security_check_cookie
0x140017cd9  lea     r11, [rsp+0C0h+var_20]
0x140017ce1  mov     rbx, [r11+38h]
0x140017ce5  mov     rsi, [r11+40h]
0x140017ce9  mov     rsp, r11
0x140017cec  pop     r15
0x140017cee  pop     r14
0x140017cf0  pop     r13
0x140017cf2  pop     rdi
0x140017cf3  pop     rbp
0x140017cf4  retn
```
