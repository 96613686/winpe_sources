# FramePacket

- ea: `0x140031b80`
- end: `0x1400320e6`
- name: `FramePacket`
- size: `1382`
- prototype: `__int64 __usercall@<rax>(PVOID Entry@<rcx>, int, ULONG)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1400312a0`

## callees

- `0x140005400`
- `0x140005494`
- `0x14000550c`
- `0x140006d80`
- `0x14000a290`
- `0x14000a2c0`
- `0x14000a744`
- `0x140016230`
- `0x140016700`
- `0x14002e080`
- `0x14002e3e8`
- `0x140030144`
- `0x140031b80`
- `0x1400320f0`
- `0x1400321d0`
- `0x140032300`
- `0x140032340`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140031f52`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003205b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400320a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031f52`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003205b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400320a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031e99`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031f22`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140032074`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031e99`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031f22`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140032074`
- `NDIS!NdisCopyFromNetBufferToNetBuffer` at `0x140031fd8`
- `NDIS!NdisCopyFromNetBufferToNetBuffer` at `0x140031fd8`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x140031db2`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x140031db2`

## pseudocode

```c
__int64 __fastcall FramePacket(PVOID Entry, __int64 a2, __int64 a3, __int64 **a4, int a5, ULONG BytesCopied)
{
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  unsigned int v13; // ebx
  __int64 *v14; // rax
  __int64 *v15; // rcx
  __int64 *v16; // r15
  __int64 v17; // r14
  __int64 SendDesc; // rax
  unsigned int v19; // ebx
  ULONG v21; // r12d
  __int64 v22; // r12
  PNET_BUFFER v23; // r13
  __int16 v24; // dx
  ULONG v25; // r8d
  _BYTE *v26; // rcx
  __int64 v27; // r9
  PMDL CurrentMdl; // rcx
  __int64 v29; // rdx
  __int64 v30; // rdx
  KIRQL v31; // al
  bool v32; // zf
  KIRQL v33; // al
  __int64 RecvNetBufferList; // rax
  __int16 v35; // ax
  KIRQL v36; // al
  __int64 v37; // [rsp+30h] [rbp-59h]
  int v38[2]; // [rsp+38h] [rbp-51h] BYREF
  _QWORD v39[11]; // [rsp+40h] [rbp-49h] BYREF
  __int64 v40; // [rsp+E0h] [rbp+57h] BYREF
  int v41; // [rsp+E8h] [rbp+5Fh] BYREF
  __int64 v42; // [rsp+F0h] [rbp+67h] BYREF
  PNET_BUFFER Source; // [rsp+F8h] [rbp+6Fh]

  v41 = 0;
  v42 = 0;
  memset(v39, 0, 0x50u);
  Source = *(PNET_BUFFER *)(a3 + 112);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids);
  }
  v10 = *((_DWORD *)Entry + 26);
  LOWORD(v40) = *(_WORD *)(a2 + 214);
  if ( (v10 & 6) != 0 )
  {
    v11 = *((_DWORD *)Entry + 4);
    if ( (v11 & 4) != 0 )
    {
      *((_DWORD *)Entry + 4) = v11 & 0xFFFFFFFB;
      v10 |= 0x20u;
    }
  }
  v12 = v10 | 0x10;
  v13 = v12 & 0xFFFFFFF8;
  if ( BytesCopied != 1 )
    v13 = v12;
  v14 = *a4;
  if ( (__int64 **)(*a4)[1] != a4 || (v15 = (__int64 *)*v14, *(__int64 **)(*v14 + 8) != v14) )
    __fastfail(3u);
  *a4 = v15;
  v15[1] = (__int64)a4;
  v16 = v14 - 30;
  v17 = *(_QWORD *)(a3 + 16) + *(unsigned __int16 *)(*(_QWORD *)(a3 + 16) + 10LL);
  _InterlockedIncrement((volatile signed __int32 *)(v17 + 40));
  SendDesc = NdisWanAllocateSendDesc(v14 - 30);
  v42 = SendDesc;
  if ( SendDesc )
  {
    *(_QWORD *)(SendDesc + 48) = a2;
    v21 = BytesCopied;
    *(_QWORD *)(v42 + 112) = a3;
    *(_DWORD *)(v42 + 32) = v21;
    *(_DWORD *)(v42 + 28) |= 8u;
    ++*((_DWORD *)Entry + 6);
    ++*((_DWORD *)Entry + 42);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids, v42, a3);
    }
    LODWORD(v39[0]) = *((_DWORD *)v16 + 72);
    HIDWORD(v39[1]) = v13;
    HIDWORD(v39[0]) = v21;
    BuildLinkHeader(v39, *(_QWORD *)(v42 + 88));
    v22 = *(_QWORD *)(v42 + 88) + LODWORD(v39[1]);
    *(_QWORD *)v38 = v22;
    if ( qword_14001E2D8 || gbEnablePacketCapture && *((_BYTE *)Entry + 2436) )
    {
      BytesCopied = 0;
      RecvNetBufferList = NdisWanAllocateRecvNetBufferList();
      v23 = Source;
      v37 = RecvNetBufferList;
      if ( RecvNetBufferList )
      {
        if ( !NdisCopyFromNetBufferToNetBuffer(
                *(PNET_BUFFER *)(RecvNetBufferList + 8),
                0,
                Source->DataLength,
                Source,
                0,
                &BytesCopied) )
        {
          *(_DWORD *)(*(_QWORD *)(v37 + 8) + 24LL) = BytesCopied;
          IndicatePromiscuousSendPacket(v16);
        }
        NdisWanFreeRecvNetBufferList(v37);
      }
    }
    else
    {
      v23 = Source;
    }
    v24 = v40;
    v25 = 14;
    BytesCopied = 14;
    if ( (v13 & 0x200) != 0 && (_WORD)v40 == 33 )
    {
      v35 = DoVJHeaderCompression((int)Entry, (int)v23, (int)v38, (int)&v41, (size_t)&BytesCopied);
      v25 = BytesCopied;
      v24 = v35;
      v22 = *(_QWORD *)v38;
    }
    if ( LODWORD(v39[8]) )
    {
      v26 = (_BYTE *)v39[9];
      if ( (v39[0] & 0x400) == 0 || (v39[1] & 0x600000000LL) != 0 )
      {
        *(_BYTE *)v39[9] = HIBYTE(v24);
        ++v26;
      }
      *v26 = v24;
    }
    v27 = v23->DataLength - v25;
    CurrentMdl = v23->CurrentMdl;
    v29 = v25 + v23->CurrentMdlOffset;
    v40 = 0;
    RtlCopyMdlToKernelBuffer(CurrentMdl, v29, v22, v27, &v40);
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v42 + 80) + 8LL) + 24LL) = v41 + v40 + LODWORD(v39[1]);
    *(_DWORD *)(v42 + 100) = v41 + v40;
    if ( (v13 & 6) == 0 || (unsigned __int8)DoCompressionEncryption(Entry, v39, &v42) )
    {
      if ( (v13 & 1) != 0 )
      {
        FragmentAndQueue((_DWORD)Entry, (unsigned int)v39, v42, (_DWORD)a4, a5);
        v19 = 0;
      }
      else
      {
        *(_DWORD *)(v42 + 96) = v39[1];
        *(_QWORD *)(v42 + 40) = v16;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            31,
            WPP_8fab404a276b37b5b154f85d9d785092_Traceguids,
            *(unsigned int *)(v42 + 24));
        }
        v19 = ((__int64 (__fastcall *)(__int64))v16[14])(v42);
      }
    }
    else
    {
      NdisWanFreeSendDesc(v42, v30);
      _InterlockedDecrement((volatile signed __int32 *)(v17 + 40));
      v31 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v16 + 92);
      v19 = -1;
      *((_BYTE *)v16 + 744) = v31;
      v32 = (*((_DWORD *)v16 + 7))-- == 1;
      if ( v32 )
        DoDerefLinkCBWork(v16);
      else
        KeReleaseSpinLock((PKSPIN_LOCK)v16 + 92, v31);
      --*((_DWORD *)Entry + 42);
      v36 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry + 221);
      v32 = (*((_DWORD *)Entry + 6))-- == 1;
      *((_BYTE *)Entry + 1776) = v36;
      if ( v32 )
        DoDerefBundleCBWork(Entry);
      else
        KeReleaseSpinLock((PKSPIN_LOCK)Entry + 221, v36);
    }
  }
  else
  {
    _InterlockedDecrement((volatile signed __int32 *)(v17 + 40));
    v19 = -1;
    if ( v16 )
    {
      v33 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v16 + 92);
      v32 = (*((_DWORD *)v16 + 7))-- == 1;
      *((_BYTE *)v16 + 744) = v33;
      if ( v32 )
        DoDerefLinkCBWork(v16);
      else
        KeReleaseSpinLock((PKSPIN_LOCK)v16 + 92, v33);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids, v19);
  }
  return v19;
}

```

## disassembly

```asm
0x140031b80  push    rbp
0x140031b82  push    rbx
0x140031b83  push    rsi
0x140031b84  push    rdi
0x140031b85  push    r12
0x140031b87  push    r13
0x140031b89  lea     rbp, [rsp-1Fh]
0x140031b8e  sub     rsp, 0A8h
0x140031b95  xor     eax, eax
0x140031b97  mov     r13, r8
0x140031b9a  mov     r12, rdx
0x140031b9d  mov     [rbp+47h+arg_8], eax
0x140031ba0  mov     rsi, rcx
0x140031ba3  mov     [rbp+47h+arg_10], rax
0x140031ba7  xor     edx, edx; Val
0x140031ba9  lea     rcx, [rbp+47h+var_90]; void *
0x140031bad  mov     r8d, 50h ; 'P'; Size
0x140031bb3  mov     rdi, r9
0x140031bb6  call    memset
0x140031bbb  mov     rax, [r13+70h]
0x140031bbf  mov     [rbp+47h+Source], rax
0x140031bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x140031bca  lea     rax, WPP_GLOBAL_Control
0x140031bd1  cmp     rcx, rax
0x140031bd4  jz      short loc_140031BE1
0x140031bd6  mov     eax, [rcx+2Ch]
0x140031bd9  test    al, 8
0x140031bdb  jnz     loc_140031EE9
0x140031be1  mov     eax, [rsi+68h]
0x140031be4  movzx   ecx, word ptr [r12+0D6h]
0x140031bed  mov     word ptr [rbp+47h+arg_0], cx
0x140031bf1  test    al, 6
0x140031bf3  jz      short loc_140031C01
0x140031bf5  mov     ecx, [rsi+10h]
0x140031bf8  test    cl, 4
0x140031bfb  jnz     loc_140031F0D
0x140031c01  or      eax, 10h
0x140031c04  mov     ebx, eax
0x140031c06  and     ebx, 0FFFFFFF8h
0x140031c09  cmp     [rbp+47h+arg_28], 1
0x140031c0d  cmovnz  ebx, eax
0x140031c10  mov     rax, [rdi]
0x140031c13  cmp     [rax+8], rdi
0x140031c17  jnz     loc_1400320DF
0x140031c1d  mov     rcx, [rax]
0x140031c20  cmp     [rcx+8], rax
0x140031c24  jnz     loc_1400320DF
0x140031c2a  mov     [rdi], rcx
0x140031c2d  mov     [rsp+0D0h+var_30], r14
0x140031c35  mov     [rcx+8], rdi
0x140031c39  mov     rcx, [r13+10h]
0x140031c3d  mov     [rsp+0D0h+var_38], r15
0x140031c45  lea     r15, [rax-0F0h]
0x140031c4c  movzx   r14d, word ptr [rcx+0Ah]
0x140031c51  add     r14, rcx
0x140031c54  lock inc dword ptr [r14+28h]
0x140031c59  mov     rcx, r15
0x140031c5c  call    NdisWanAllocateSendDesc
0x140031c61  mov     [rbp+47h+arg_10], rax
0x140031c65  test    rax, rax
0x140031c68  jnz     short loc_140031CB7
0x140031c6a  lock dec dword ptr [r14+28h]
0x140031c6f  mov     ebx, 0FFFFFFFFh
0x140031c74  test    r15, r15
0x140031c77  jnz     loc_140031F1B
0x140031c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140031c84  lea     rax, WPP_GLOBAL_Control
0x140031c8b  mov     r15, [rsp+0D0h+var_38]
0x140031c93  mov     r14, [rsp+0D0h+var_30]
0x140031c9b  cmp     rcx, rax
0x140031c9e  jnz     loc_140031E39
0x140031ca4  mov     eax, ebx
0x140031ca6  add     rsp, 0A8h
0x140031cad  pop     r13
0x140031caf  pop     r12
0x140031cb1  pop     rdi
0x140031cb2  pop     rsi
0x140031cb3  pop     rbx
0x140031cb4  pop     rbp
0x140031cb5  retn
0x140031cb7  mov     [rax+30h], r12
0x140031cbb  mov     rax, [rbp+47h+arg_10]
0x140031cbf  mov     r12d, [rbp+47h+arg_28]
0x140031cc3  mov     [rax+70h], r13
0x140031cc7  mov     rax, [rbp+47h+arg_10]
0x140031ccb  mov     [rax+20h], r12d
0x140031ccf  mov     rax, [rbp+47h+arg_10]
0x140031cd3  or      dword ptr [rax+1Ch], 8
0x140031cd7  inc     dword ptr [rsi+18h]
0x140031cda  inc     dword ptr [rsi+0A8h]
0x140031ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x140031ce7  lea     rax, WPP_GLOBAL_Control
0x140031cee  cmp     rcx, rax
0x140031cf1  jz      short loc_140031CFE
0x140031cf3  mov     eax, [rcx+2Ch]
0x140031cf6  test    al, 8
0x140031cf8  jnz     loc_140031F63
0x140031cfe  mov     eax, [r15+120h]
0x140031d05  lea     rcx, [rbp+47h+var_90]
0x140031d09  mov     rdx, [rbp+47h+arg_10]
0x140031d0d  mov     [rbp+47h+var_90], eax
0x140031d10  mov     [rbp+47h+var_84], ebx
0x140031d13  mov     [rbp+47h+var_8C], r12d
0x140031d17  mov     rdx, [rdx+58h]
0x140031d1b  call    BuildLinkHeader
0x140031d20  mov     rax, [rbp+47h+arg_10]
0x140031d24  mov     r12d, [rbp+47h+var_88]
0x140031d28  add     r12, [rax+58h]
0x140031d2c  cmp     cs:qword_14001E2D8, 0
0x140031d34  mov     qword ptr [rbp+47h+var_98], r12
0x140031d38  jnz     loc_140031F9D
0x140031d3e  cmp     cs:gbEnablePacketCapture, 0
0x140031d45  jnz     loc_140031F90
0x140031d4b  mov     r13, [rbp+47h+Source]
0x140031d4f  movzx   edx, word ptr [rbp+47h+arg_0]
0x140031d53  mov     r8d, 0Eh
0x140031d59  mov     [rbp+47h+arg_28], r8d
0x140031d5d  bt      ebx, 9
0x140031d61  jb      loc_14003200C
0x140031d67  cmp     [rbp+47h+var_50], 0
0x140031d6b  jz      short loc_140031D8C
0x140031d6d  test    [rbp+47h+var_90], 400h
0x140031d74  mov     rcx, [rbp+47h+var_48]
0x140031d78  jnz     loc_140032042
0x140031d7e  movzx   eax, dx
0x140031d81  shr     ax, 8
0x140031d85  mov     [rcx], al
0x140031d87  inc     rcx
0x140031d8a  mov     [rcx], dl
0x140031d8c  mov     r9d, [r13+18h]
0x140031d90  lea     rax, [rbp+47h+arg_0]
0x140031d94  mov     edx, [r13+10h]
0x140031d98  sub     r9d, r8d
0x140031d9b  mov     rcx, [r13+8]
0x140031d9f  add     edx, r8d
0x140031da2  mov     r8, r12
0x140031da5  mov     [rbp+47h+arg_0], 0
0x140031dad  mov     qword ptr [rsp+0D0h+SourceOffset], rax
0x140031db2  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x140031db9  nop     dword ptr [rax+rax+00h]
0x140031dbe  mov     rax, [rbp+47h+arg_10]
0x140031dc2  mov     edx, [rbp+47h+var_88]
0x140031dc5  add     edx, dword ptr [rbp+47h+arg_0]
0x140031dc8  add     edx, [rbp+47h+arg_8]
0x140031dcb  mov     rcx, [rax+50h]
0x140031dcf  mov     rax, [rcx+8]
0x140031dd3  mov     [rax+18h], edx
0x140031dd6  mov     ecx, dword ptr [rbp+47h+arg_0]
0x140031dd9  add     ecx, [rbp+47h+arg_8]
0x140031ddc  mov     rax, [rbp+47h+arg_10]
0x140031de0  mov     [rax+64h], ecx
0x140031de3  test    bl, 6
0x140031de6  jnz     loc_140031E6C
0x140031dec  test    bl, 1
0x140031def  jnz     loc_140031EC8
0x140031df5  mov     eax, [rbp+47h+var_88]
0x140031df8  mov     rcx, [rbp+47h+arg_10]
0x140031dfc  mov     [rcx+60h], eax
0x140031dff  mov     rax, [rbp+47h+arg_10]
0x140031e03  mov     [rax+28h], r15
0x140031e07  mov     rcx, cs:WPP_GLOBAL_Control
0x140031e0e  lea     rax, WPP_GLOBAL_Control
0x140031e15  cmp     rcx, rax
0x140031e18  jz      short loc_140031E25
0x140031e1a  mov     eax, [rcx+2Ch]
0x140031e1d  test    al, 8
0x140031e1f  jnz     loc_1400320B3
0x140031e25  mov     rax, [r15+70h]
0x140031e29  mov     rcx, [rbp+47h+arg_10]
0x140031e2d  call    _guard_dispatch_icall
0x140031e32  mov     ebx, eax
0x140031e34  jmp     loc_140031C7D
0x140031e39  mov     edx, [rcx+2Ch]
0x140031e3c  test    dl, 8
0x140031e3f  jz      loc_140031CA4
0x140031e45  cmp     byte ptr [rcx+29h], 5
0x140031e49  jb      loc_140031CA4
0x140031e4f  mov     rcx, [rcx+18h]
0x140031e53  lea     r8, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids
0x140031e5a  mov     edx, 20h ; ' '
0x140031e5f  mov     r9d, ebx
0x140031e62  call    WPP_SF_d
0x140031e67  jmp     loc_140031CA4
0x140031e6c  lea     r8, [rbp+47h+arg_10]
0x140031e70  mov     rcx, rsi
0x140031e73  lea     rdx, [rbp+47h+var_90]
0x140031e77  call    DoCompressionEncryption
0x140031e7c  test    al, al
0x140031e7e  jnz     loc_140031DEC
0x140031e84  mov     rcx, [rbp+47h+arg_10]
0x140031e88  call    NdisWanFreeSendDesc
0x140031e8d  lock dec dword ptr [r14+28h]
0x140031e92  lea     rcx, [r15+2E0h]; SpinLock
0x140031e99  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140031ea0  nop     dword ptr [rax+rax+00h]
0x140031ea5  mov     ebx, 0FFFFFFFFh
0x140031eaa  mov     [r15+2E8h], al
0x140031eb1  add     [r15+1Ch], ebx
0x140031eb5  jnz     loc_140032051
0x140031ebb  mov     rcx, r15; Entry
0x140031ebe  call    DoDerefLinkCBWork
0x140031ec3  jmp     loc_140032067
0x140031ec8  mov     eax, [rbp+47h+arg_20]
0x140031ecb  lea     rdx, [rbp+47h+var_90]
0x140031ecf  mov     r8, [rbp+47h+arg_10]
0x140031ed3  mov     r9, rdi
0x140031ed6  mov     rcx, rsi
0x140031ed9  mov     [rsp+0D0h+SourceOffset], eax
0x140031edd  call    FragmentAndQueue
0x140031ee2  xor     ebx, ebx
0x140031ee4  jmp     loc_140031C7D
0x140031ee9  cmp     byte ptr [rcx+29h], 5
0x140031eed  jb      loc_140031BE1
0x140031ef3  mov     rcx, [rcx+18h]
0x140031ef7  lea     r8, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids
0x140031efe  mov     edx, 1Dh
0x140031f03  call    WPP_SF_
0x140031f08  jmp     loc_140031BE1
0x140031f0d  and     ecx, 0FFFFFFFBh
0x140031f10  mov     [rsi+10h], ecx
0x140031f13  or      eax, 20h
0x140031f16  jmp     loc_140031C01
0x140031f1b  lea     rcx, [r15+2E0h]; SpinLock
0x140031f22  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140031f29  nop     dword ptr [rax+rax+00h]
0x140031f2e  add     [r15+1Ch], ebx
0x140031f32  mov     [r15+2E8h], al
0x140031f39  jnz     short loc_140031F48
0x140031f3b  mov     rcx, r15; Entry
0x140031f3e  call    DoDerefLinkCBWork
0x140031f43  jmp     loc_140031C7D
0x140031f48  movzx   edx, al; NewIrql
0x140031f4b  lea     rcx, [r15+2E0h]; SpinLock
0x140031f52  call    cs:__imp_KeReleaseSpinLock
0x140031f59  nop     dword ptr [rax+rax+00h]
0x140031f5e  jmp     loc_140031C7D
0x140031f63  cmp     byte ptr [rcx+29h], 5
0x140031f67  jb      loc_140031CFE
0x140031f6d  mov     r9, [rbp+47h+arg_10]
0x140031f71  lea     r8, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids
0x140031f78  mov     rcx, [rcx+18h]
0x140031f7c  mov     edx, 1Eh
0x140031f81  mov     qword ptr [rsp+0D0h+SourceOffset], r13
0x140031f86  call    WPP_SF_qq
0x140031f8b  jmp     loc_140031CFE
0x140031f90  cmp     byte ptr [rsi+984h], 0
0x140031f97  jz      loc_140031D4B
0x140031f9d  mov     [rbp+47h+arg_28], 0
0x140031fa4  call    NdisWanAllocateRecvNetBufferList
0x140031fa9  mov     r13, [rbp+47h+Source]
0x140031fad  mov     [rbp+47h+var_A0], rax
0x140031fb1  test    rax, rax
0x140031fb4  jz      loc_140031D4F
0x140031fba  mov     r8d, [r13+18h]; BytesToCopy
0x140031fbe  lea     rcx, [rbp+47h+arg_28]
0x140031fc2  mov     [rsp+0D0h+BytesCopied], rcx; BytesCopied
0x140031fc7  mov     r9, r13; Source
0x140031fca  mov     rcx, [rax+8]; Destination
0x140031fce  xor     edx, edx; DestinationOffset
0x140031fd0  mov     [rsp+0D0h+SourceOffset], 0; SourceOffset
0x140031fd8  call    cs:__imp_NdisCopyFromNetBufferToNetBuffer
0x140031fdf  nop     dword ptr [rax+rax+00h]
0x140031fe4  test    eax, eax
0x140031fe6  jnz     short loc_140031FFE
0x140031fe8  mov     rdx, [rbp+47h+var_A0]
0x140031fec  mov     eax, [rbp+47h+arg_28]
0x140031fef  mov     rcx, [rdx+8]
0x140031ff3  mov     [rcx+18h], eax
0x140031ff6  mov     rcx, r15
0x140031ff9  call    IndicatePromiscuousSendPacket
0x140031ffe  mov     rcx, [rbp+47h+var_A0]
0x140032002  call    NdisWanFreeRecvNetBufferList
0x140032007  jmp     loc_140031D4F
0x14003200c  cmp     dx, 21h ; '!'
0x140032010  jnz     loc_140031D67
0x140032016  lea     rax, [rbp+47h+arg_28]
0x14003201a  mov     rdx, r13; int
0x14003201d  lea     r9, [rbp+47h+arg_8]; int
0x140032021  mov     qword ptr [rsp+0D0h+SourceOffset], rax; Size
0x140032026  lea     r8, [rbp+47h+var_98]; int
0x14003202a  mov     rcx, rsi; int
0x14003202d  call    DoVJHeaderCompression
0x140032032  mov     r8d, [rbp+47h+arg_28]
0x140032036  movzx   edx, ax
0x140032039  mov     r12, qword ptr [rbp+47h+var_98]
0x14003203d  jmp     loc_140031D67
0x140032042  test    byte ptr [rbp+47h+var_84], 6
0x140032046  jz      loc_140031D8A
0x14003204c  jmp     loc_140031D7E
0x140032051  movzx   edx, al; NewIrql
0x140032054  lea     rcx, [r15+2E0h]; SpinLock
0x14003205b  call    cs:__imp_KeReleaseSpinLock
0x140032062  nop     dword ptr [rax+rax+00h]
0x140032067  add     [rsi+0A8h], ebx
0x14003206d  lea     rcx, [rsi+6E8h]; SpinLock
0x140032074  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003207b  nop     dword ptr [rax+rax+00h]
0x140032080  add     [rsi+18h], ebx
0x140032083  mov     [rsi+6F0h], al
0x140032089  jnz     short loc_140032098
  ... truncated ...
```
