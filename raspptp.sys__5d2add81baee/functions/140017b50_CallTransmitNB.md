# CallTransmitNB

- ea: `0x140017b50`
- end: `0x140017f11`
- name: `CallTransmitNB`
- size: `961`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140017650`

## callees

- `0x140003e08`
- `0x140003e38`
- `0x1400076d0`
- `0x140017b50`
- `0x140017f20`
- `0x14001e1e0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140017bfa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017dc5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017bfa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017dc5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017bc2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017bc2`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140017c38`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140017c38`
- `NDIS!NdisGetDataBuffer` at `0x140017c94`
- `NDIS!NdisGetDataBuffer` at `0x140017c94`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140017ef8`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140017ef8`

## pseudocode

```c
__int64 __fastcall CallTransmitNB(__int64 a1, __int64 a2, __int64 a3, int a4, int a5, int a6, char a7)
{
  unsigned int v9; // ebp
  int v10; // r13d
  KIRQL v11; // al
  bool v12; // zf
  KSPIN_LOCK *v13; // rcx
  __int64 v14; // r14
  ULONG v15; // edi
  unsigned int v16; // r12d
  unsigned int v17; // eax
  __int64 v18; // rbp
  PVOID DataBuffer; // rax
  __int64 v20; // r8
  PDEVICE_OBJECT v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  int v26; // [rsp+28h] [rbp-A0h]
  __int64 v28; // [rsp+48h] [rbp-80h] BYREF
  _BYTE v29[40]; // [rsp+50h] [rbp-78h] BYREF

  v9 = -1073741823;
  v28 = a2;
  v10 = *((_DWORD *)GreSize + (a4 & 3));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
  }
  v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  v12 = *(_DWORD *)(a1 + 112) == 9;
  v13 = (KSPIN_LOCK *)(a1 + 96);
  *(_BYTE *)(a1 + 104) = v11;
  if ( !v12 )
  {
    KeReleaseSpinLock(v13, v11);
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 676));
    goto LABEL_14;
  }
  v14 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 64LL);
  KeReleaseSpinLock(v13, v11);
  if ( *(_WORD *)(a1 + 280) != 2 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_20;
    }
    v23 = 104;
    goto LABEL_32;
  }
  if ( !v14 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_20;
    }
    v23 = 105;
LABEL_32:
    WPP_SF_(v22->AttachedDevice, v23, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
LABEL_20:
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 676));
    goto LABEL_14;
  }
  v15 = v10 + 20;
  v16 = *(_DWORD *)(a3 + 24);
  v17 = NdisRetreatNetBufferDataStart((PNET_BUFFER)a3, v10 + 20, 0, 0);
  v9 = v17;
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids, v17);
    }
    goto LABEL_20;
  }
  v18 = v28;
  *(_QWORD *)(a3 + 128) = v28;
  *(_DWORD *)(a3 + 136) = v15;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids, v16);
  }
  DataBuffer = NdisGetDataBuffer((PNET_BUFFER)a3, v15, 0, 1u, 0);
  if ( DataBuffer )
  {
    PptpBuildIpGreHdrs((_DWORD)DataBuffer, a1, a4, a5, a6, 1, v16);
  }
  else
  {
    PptpBuildIpGreHdrs((unsigned int)v29, a1, a4, a5, a6, 1, v16);
    v24 = *(unsigned int *)(a3 + 16);
    v25 = *(_QWORD *)(a3 + 8);
    v28 = 0;
    RtlCopyKernelBufferToMdl(v29, v25, v24, v15, &v28);
  }
  if ( a7 )
    _InterlockedIncrement((volatile signed __int32 *)a1);
  else
    _InterlockedIncrement((volatile signed __int32 *)(v18 + 112));
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 660));
  _InterlockedIncrement(&dword_14000B3F0);
  WskSendDatagram(v14, a1 + 280, v20, a3, a1, v26, a3);
  v9 = 259;
LABEL_14:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x140017b50  mov     r11, rsp
0x140017b53  push    rbp
0x140017b54  sub     rsp, 0C0h
0x140017b5b  mov     rax, cs:__security_cookie
0x140017b62  xor     rax, rsp
0x140017b65  mov     [rsp+0C8h+var_50], rax
0x140017b6a  mov     [r11-10h], rbx
0x140017b6e  mov     eax, r9d
0x140017b71  mov     [r11-18h], rsi
0x140017b75  mov     rbx, rcx
0x140017b78  mov     [rsp+0C8h+var_88], eax
0x140017b7c  mov     rsi, r8
0x140017b7f  and     eax, 3
0x140017b82  mov     [r11-20h], rdi
0x140017b86  mov     [r11-30h], r13
0x140017b8a  mov     ebp, 0C0000001h
0x140017b8f  lea     r13, GreSize
0x140017b96  mov     [rsp+0C8h+var_80], rdx
0x140017b9b  mov     r13d, [r13+rax*4+0]
0x140017ba0  mov     rcx, cs:WPP_GLOBAL_Control
0x140017ba7  lea     rax, WPP_GLOBAL_Control
0x140017bae  cmp     rcx, rax
0x140017bb1  jz      short loc_140017BBE
0x140017bb3  mov     eax, [rcx+2Ch]
0x140017bb6  test    al, 20h
0x140017bb8  jnz     loc_140017DE4
0x140017bbe  lea     rcx, [rbx+60h]; SpinLock
0x140017bc2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017bc9  nop     dword ptr [rax+rax+00h]
0x140017bce  cmp     dword ptr [rbx+70h], 9
0x140017bd2  lea     rcx, [rbx+60h]; SpinLock
0x140017bd6  movzx   edx, al; NewIrql
0x140017bd9  mov     [rbx+68h], al
0x140017bdc  jnz     loc_140017DC5
0x140017be2  mov     rax, [rbx+38h]
0x140017be6  mov     [rsp+0C8h+var_38], r14
0x140017bee  mov     [rsp+0C8h+var_40], r15
0x140017bf6  mov     r14, [rax+40h]
0x140017bfa  call    cs:__imp_KeReleaseSpinLock
0x140017c01  nop     dword ptr [rax+rax+00h]
0x140017c06  cmp     word ptr [rbx+118h], 2
0x140017c0e  jnz     loc_140017E08
0x140017c14  test    r14, r14
0x140017c17  jz      loc_140017E2F
0x140017c1d  lea     edi, [r13+14h]
0x140017c21  mov     [rsp+0C8h+var_28], r12
0x140017c29  mov     r12d, [rsi+18h]
0x140017c2d  mov     edx, edi; DataOffsetDelta
0x140017c2f  xor     r9d, r9d; AllocateMdlHandler
0x140017c32  xor     r8d, r8d; DataBackFill
0x140017c35  mov     rcx, rsi; NetBuffer
0x140017c38  call    cs:__imp_NdisRetreatNetBufferDataStart
0x140017c3f  nop     dword ptr [rax+rax+00h]
0x140017c44  mov     ebp, eax
0x140017c46  test    eax, eax
0x140017c48  jnz     loc_140017DA2
0x140017c4e  mov     rbp, [rsp+0C8h+var_80]
0x140017c53  mov     [rsi+80h], rbp
0x140017c5a  mov     [rsi+88h], edi
0x140017c60  mov     rcx, cs:WPP_GLOBAL_Control
0x140017c67  lea     rax, WPP_GLOBAL_Control
0x140017c6e  cmp     rcx, rax
0x140017c71  jz      short loc_140017C7E
0x140017c73  mov     eax, [rcx+2Ch]
0x140017c76  test    al, 20h
0x140017c78  jnz     loc_140017EA3
0x140017c7e  mov     r9d, 1; AlignMultiple
0x140017c84  mov     [rsp+0C8h+AlignOffset], 0; AlignOffset
0x140017c8c  xor     r8d, r8d; Storage
0x140017c8f  mov     edx, edi; BytesNeeded
0x140017c91  mov     rcx, rsi; NetBuffer
0x140017c94  call    cs:__imp_NdisGetDataBuffer
0x140017c9b  nop     dword ptr [rax+rax+00h]
0x140017ca0  mov     r9d, [rsp+0C8h+arg_20]
0x140017ca8  mov     rdx, rbx
0x140017cab  mov     r8d, [rsp+0C8h+var_88]
0x140017cb0  mov     rcx, rax
0x140017cb3  mov     dword ptr [rsp+0C8h+var_98], r12d
0x140017cb8  test    rax, rax
0x140017cbb  mov     eax, [rsp+0C8h+arg_28]
0x140017cc2  mov     [rsp+0C8h+var_A0], 1
0x140017cc7  mov     [rsp+0C8h+AlignOffset], eax
0x140017ccb  jz      loc_140017ECA
0x140017cd1  call    PptpBuildIpGreHdrs
0x140017cd6  cmp     [rsp+0C8h+arg_30], 0
0x140017cde  jnz     loc_140017F09
0x140017ce4  lock inc dword ptr [rbp+70h]
0x140017ce8  lock inc dword ptr [rbx+294h]
0x140017cef  lock inc cs:dword_14000B3F0
0x140017cf6  mov     [rsp+0C8h+var_98], rsi
0x140017cfb  lea     rdx, [rbx+118h]
0x140017d02  mov     r9, rsi
0x140017d05  mov     qword ptr [rsp+0C8h+AlignOffset], rbx
0x140017d0a  mov     rcx, r14
0x140017d0d  call    WskSendDatagram
0x140017d12  mov     ebp, 103h
0x140017d17  lea     rdi, WPP_GLOBAL_Control
0x140017d1e  mov     r12, [rsp+0C8h+var_28]
0x140017d26  mov     r14, [rsp+0C8h+var_38]
0x140017d2e  mov     r15, [rsp+0C8h+var_40]
0x140017d36  mov     rcx, cs:WPP_GLOBAL_Control
0x140017d3d  mov     r13, [rsp+0C8h+var_30]
0x140017d45  cmp     rcx, rdi
0x140017d48  mov     rdi, [rsp+0C8h+var_20]
0x140017d50  mov     rsi, [rsp+0C8h+var_18]
0x140017d58  mov     rbx, [rsp+0C8h+var_10]
0x140017d60  jnz     short loc_140017D7B
0x140017d62  mov     eax, ebp
0x140017d64  mov     rcx, [rsp+0C8h+var_50]
0x140017d69  xor     rcx, rsp; StackCookie
0x140017d6c  call    __security_check_cookie
0x140017d71  add     rsp, 0C0h
0x140017d78  pop     rbp
0x140017d79  retn
0x140017d7b  mov     eax, [rcx+2Ch]
0x140017d7e  test    al, 20h
0x140017d80  jz      short loc_140017D62
0x140017d82  cmp     byte ptr [rcx+29h], 1
0x140017d86  jb      short loc_140017D62
0x140017d88  mov     rcx, [rcx+18h]
0x140017d8c  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140017d93  mov     edx, 6Ch ; 'l'
0x140017d98  mov     r9d, ebp
0x140017d9b  call    WPP_SF_d
0x140017da0  jmp     short loc_140017D62
0x140017da2  mov     rcx, cs:WPP_GLOBAL_Control
0x140017da9  lea     rdi, WPP_GLOBAL_Control
0x140017db0  cmp     rcx, rdi
0x140017db3  jnz     loc_140017E70
0x140017db9  lock inc dword ptr [rbx+2A4h]
0x140017dc0  jmp     loc_140017D1E
0x140017dc5  call    cs:__imp_KeReleaseSpinLock
0x140017dcc  nop     dword ptr [rax+rax+00h]
0x140017dd1  lock inc dword ptr [rbx+2A4h]
0x140017dd8  lea     rdi, WPP_GLOBAL_Control
0x140017ddf  jmp     loc_140017D36
0x140017de4  cmp     byte ptr [rcx+29h], 1
0x140017de8  jb      loc_140017BBE
0x140017dee  mov     rcx, [rcx+18h]
0x140017df2  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140017df9  mov     edx, 67h ; 'g'
0x140017dfe  call    WPP_SF_
0x140017e03  jmp     loc_140017BBE
0x140017e08  mov     rcx, cs:WPP_GLOBAL_Control
0x140017e0f  lea     rdi, WPP_GLOBAL_Control
0x140017e16  cmp     rcx, rdi
0x140017e19  jz      short loc_140017E64
0x140017e1b  mov     eax, [rcx+2Ch]
0x140017e1e  test    al, 20h
0x140017e20  jz      short loc_140017E64
0x140017e22  cmp     byte ptr [rcx+29h], 1
0x140017e26  jb      short loc_140017E64
0x140017e28  mov     edx, 68h ; 'h'
0x140017e2d  jmp     short loc_140017E54
0x140017e2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140017e36  lea     rdi, WPP_GLOBAL_Control
0x140017e3d  cmp     rcx, rdi
0x140017e40  jz      short loc_140017E64
0x140017e42  mov     eax, [rcx+2Ch]
0x140017e45  test    al, 20h
0x140017e47  jz      short loc_140017E64
0x140017e49  cmp     byte ptr [rcx+29h], 1
0x140017e4d  jb      short loc_140017E64
0x140017e4f  mov     edx, 69h ; 'i'
0x140017e54  mov     rcx, [rcx+18h]
0x140017e58  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140017e5f  call    WPP_SF_
0x140017e64  lock inc dword ptr [rbx+2A4h]
0x140017e6b  jmp     loc_140017D26
0x140017e70  mov     edx, [rcx+2Ch]
0x140017e73  test    dl, 20h
0x140017e76  jz      loc_140017DB9
0x140017e7c  cmp     byte ptr [rcx+29h], 2
0x140017e80  jb      loc_140017DB9
0x140017e86  mov     rcx, [rcx+18h]
0x140017e8a  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140017e91  mov     edx, 6Ah ; 'j'
0x140017e96  mov     r9d, eax
0x140017e99  call    WPP_SF_d
0x140017e9e  jmp     loc_140017DB9
0x140017ea3  cmp     byte ptr [rcx+29h], 2
0x140017ea7  jb      loc_140017C7E
0x140017ead  mov     rcx, [rcx+18h]
0x140017eb1  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140017eb8  mov     edx, 6Bh ; 'k'
0x140017ebd  mov     r9d, r12d
0x140017ec0  call    WPP_SF_d
0x140017ec5  jmp     loc_140017C7E
0x140017eca  lea     r13, [rsp+0C8h+var_78]
0x140017ecf  mov     rcx, r13
0x140017ed2  call    PptpBuildIpGreHdrs
0x140017ed7  mov     r8d, [rsi+10h]
0x140017edb  lea     rax, [rsp+0C8h+var_80]
0x140017ee0  mov     rdx, [rsi+8]
0x140017ee4  mov     rcx, r13
0x140017ee7  mov     r9d, edi
0x140017eea  mov     qword ptr [rsp+0C8h+AlignOffset], rax
0x140017eef  mov     [rsp+0C8h+var_80], 0
0x140017ef8  call    cs:__imp_RtlCopyKernelBufferToMdl
0x140017eff  nop     dword ptr [rax+rax+00h]
0x140017f04  jmp     loc_140017CD6
0x140017f09  lock inc dword ptr [rbx]
0x140017f0c  jmp     loc_140017CE8
```
