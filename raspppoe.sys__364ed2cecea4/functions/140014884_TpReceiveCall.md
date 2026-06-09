# TpReceiveCall

- ea: `0x140014884`
- end: `0x140014d26`
- name: `TpReceiveCall`
- size: `1186`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14000e290`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x1400023c0`
- `0x140002520`
- `0x140002958`
- `0x140002a60`
- `0x1400053c4`
- `0x14000547c`
- `0x140006b80`
- `0x140014884`
- `0x140016534`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001496e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014a24`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014ae5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014b3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014bbb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014c2b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014cbb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001496e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014a24`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014ae5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014b3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014bbb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014c2b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014cbb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400148e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014ac3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014b98`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014c94`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400148e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014ac3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014b98`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014c94`
- `NDIS!NdisAllocateMemoryWithTag` at `0x140014991`
- `NDIS!NdisAllocateMemoryWithTag` at `0x140014991`
- `NDIS!NdisMCmCreateVc` at `0x140014a46`
- `NDIS!NdisMCmCreateVc` at `0x140014a46`

## pseudocode

```c
void __fastcall TpReceiveCall(__int64 a1, __int64 a2, __int64 a3)
{
  KIRQL v5; // al
  unsigned int v6; // edi
  unsigned int v7; // ecx
  __int64 v8; // rdx
  char v9; // r12
  unsigned int Vc; // r14d
  __int64 *v11; // rsi
  __int64 v12; // rcx
  _QWORD *v13; // rax
  _DWORD *v14; // rdi
  _BYTE *v15; // rbx
  PVOID v16; // rbx
  KIRQL v17; // al
  int v18; // edx
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  void (**v21)(void); // rcx
  KIRQL v22; // al
  _QWORD *v23; // rdx
  __int64 v24; // rcx
  KIRQL v25; // dl
  PVOID VirtualAddress; // [rsp+70h] [rbp+40h] BYREF
  __int64 v27; // [rsp+78h] [rbp+48h]

  v27 = a2;
  VirtualAddress = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 119, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
  }
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  v6 = 0;
  v7 = *(_DWORD *)(a1 + 676) * *(_DWORD *)(a1 + 680);
  *(_BYTE *)(a1 + 16) = v5;
  if ( v7 )
  {
    v8 = *(_QWORD *)(a1 + 96);
    if ( !v8 )
      goto LABEL_17;
    do
    {
      if ( (unsigned int)(unsigned __int16)v6 >= *(_DWORD *)(v8 + 8) )
        break;
      if ( !*(_BYTE *)(*(_QWORD *)v8 + 24LL * (unsigned __int16)v6) )
        break;
      if ( !*(_QWORD *)(*(_QWORD *)v8 + 24LL * (unsigned __int16)v6 + 8) )
        break;
      ++v6;
    }
    while ( v6 < v7 );
  }
  if ( v6 == v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 120, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), *(_BYTE *)(a1 + 16));
    return;
  }
LABEL_17:
  v9 = 0;
  if ( NdisAllocateMemoryWithTag(&VirtualAddress, 0x358u, 0x68456F50u) )
  {
    Vc = -1073741670;
    goto LABEL_34;
  }
  Vc = TpCallInitialize(VirtualAddress);
  if ( Vc )
  {
LABEL_34:
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), *(_BYTE *)(a1 + 16));
    if ( !Vc )
      goto LABEL_35;
    v11 = (__int64 *)(a1 + 96);
    v14 = (_DWORD *)(a1 + 684);
    if ( !v9 )
    {
LABEL_57:
      if ( VirtualAddress )
        TpCallCleanup(VirtualAddress);
      goto LABEL_59;
    }
LABEL_56:
    v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
    v23 = VirtualAddress;
    v24 = *v11;
    *(_BYTE *)(a1 + 16) = v22;
    RemoveFromHandleTable(v24, v23[14]);
    v25 = *(_BYTE *)(a1 + 16);
    --*v14;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v25);
    goto LABEL_57;
  }
  v11 = (__int64 *)(a1 + 96);
  v12 = InsertToHandleTable(*(_QWORD *)(a1 + 96), (unsigned __int16)v6, VirtualAddress);
  if ( !v12 )
  {
    Vc = -1073668094;
    goto LABEL_34;
  }
  v13 = VirtualAddress;
  v14 = (_DWORD *)(a1 + 684);
  ++*(_DWORD *)(a1 + 684);
  v13[14] = v12;
  *((_QWORD *)VirtualAddress + 12) = a1;
  if ( !*(_QWORD *)(a1 + 128) || !*(_QWORD *)(a1 + 136) )
  {
    v9 = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 121, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
    }
    goto LABEL_34;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), *(_BYTE *)(a1 + 16));
  Vc = NdisMCmCreateVc(
         *(NDIS_HANDLE *)(a1 + 72),
         *(NDIS_HANDLE *)(a1 + 128),
         VirtualAddress,
         (PNDIS_HANDLE)VirtualAddress + 21);
  if ( Vc )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        122,
        WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids,
        VirtualAddress,
        Vc);
    }
    goto LABEL_56;
  }
  ReferenceAdapter(a1, 0);
  _InterlockedIncrement((volatile signed __int32 *)VirtualAddress + 6);
  v15 = VirtualAddress;
  v15[64] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)VirtualAddress + 7);
  *((_DWORD *)VirtualAddress + 22) |= 2u;
  KeReleaseSpinLock((PKSPIN_LOCK)VirtualAddress + 7, *((_BYTE *)VirtualAddress + 64));
  _InterlockedIncrement((volatile signed __int32 *)VirtualAddress + 6);
  Vc = 0;
LABEL_35:
  v16 = VirtualAddress;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_d5eca6e7fcdc3e512a30350b25826940_Traceguids);
  }
  v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v16 + 7);
  v18 = *((_DWORD *)v16 + 20);
  *((_BYTE *)v16 + 64) = v17;
  if ( (v18 & 0xC) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_d5eca6e7fcdc3e512a30350b25826940_Traceguids);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)v16 + 7, *((_BYTE *)v16 + 64));
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      goto LABEL_53;
    }
    v20 = 16;
    goto LABEL_52;
  }
  *((_DWORD *)v16 + 18) = 5;
  KeReleaseSpinLock((PKSPIN_LOCK)v16 + 7, v17);
  FsmRun(v16, v27, a3, 0);
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    v20 = 17;
LABEL_52:
    WPP_SF_(v19->AttachedDevice, v20, WPP_d5eca6e7fcdc3e512a30350b25826940_Traceguids);
  }
LABEL_53:
  v21 = (void (**)(void))((char *)VirtualAddress + 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)VirtualAddress + 6, 0xFFFFFFFF) == 1 )
    v21[1]();
LABEL_59:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 123, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, Vc);
  }
}

```

## disassembly

```asm
0x140014884  mov     [rsp-38h+arg_10], rbx
0x140014889  mov     [rsp-38h+arg_8], rdx
0x14001488e  push    rbp
0x14001488f  push    rsi
0x140014890  push    rdi
0x140014891  push    r12
0x140014893  push    r13
0x140014895  push    r14
0x140014897  push    r15
0x140014899  mov     rbp, rsp
0x14001489c  sub     rsp, 30h
0x1400148a0  xor     r14d, r14d
0x1400148a3  mov     r13, r8
0x1400148a6  mov     [rbp+VirtualAddress], r14
0x1400148aa  mov     rbx, rcx
0x1400148ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400148b4  lea     rsi, WPP_GLOBAL_Control
0x1400148bb  cmp     rcx, rsi
0x1400148be  jz      short loc_1400148E1
0x1400148c0  mov     eax, [rcx+2Ch]
0x1400148c3  test    al, 2
0x1400148c5  jz      short loc_1400148E1
0x1400148c7  cmp     byte ptr [rcx+29h], 3
0x1400148cb  jb      short loc_1400148E1
0x1400148cd  mov     rcx, [rcx+18h]
0x1400148d1  lea     edx, [r14+77h]
0x1400148d5  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x1400148dc  call    WPP_SF_
0x1400148e1  lea     r15, [rbx+8]
0x1400148e5  mov     rcx, r15; SpinLock
0x1400148e8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400148ef  nop     dword ptr [rax+rax+00h]
0x1400148f4  mov     ecx, [rbx+2A8h]
0x1400148fa  mov     edi, r14d
0x1400148fd  imul    ecx, [rbx+2A4h]
0x140014904  mov     [rbx+10h], al
0x140014907  test    ecx, ecx
0x140014909  jz      short loc_140014936
0x14001490b  mov     rdx, [rbx+60h]
0x14001490f  test    rdx, rdx
0x140014912  jz      short loc_14001497F
0x140014914  movzx   eax, di
0x140014917  cmp     eax, [rdx+8]
0x14001491a  jnb     short loc_140014936
0x14001491c  lea     r8, [rax+rax*2]
0x140014920  mov     rax, [rdx]
0x140014923  cmp     [rax+r8*8], r14b
0x140014927  jz      short loc_140014936
0x140014929  cmp     [rax+r8*8+8], r14
0x14001492e  jz      short loc_140014936
0x140014930  inc     edi
0x140014932  cmp     edi, ecx
0x140014934  jb      short loc_140014914
0x140014936  cmp     edi, ecx
0x140014938  jnz     short loc_14001497F
0x14001493a  mov     rcx, cs:WPP_GLOBAL_Control
0x140014941  cmp     rcx, rsi
0x140014944  jz      short loc_140014968
0x140014946  mov     eax, [rcx+2Ch]
0x140014949  test    al, 2
0x14001494b  jz      short loc_140014968
0x14001494d  cmp     byte ptr [rcx+29h], 3
0x140014951  jb      short loc_140014968
0x140014953  mov     rcx, [rcx+18h]
0x140014957  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x14001495e  mov     edx, 78h ; 'x'
0x140014963  call    WPP_SF_
0x140014968  mov     dl, [rbx+10h]; NewIrql
0x14001496b  mov     rcx, r15; SpinLock
0x14001496e  call    cs:__imp_KeReleaseSpinLock
0x140014975  nop     dword ptr [rax+rax+00h]
0x14001497a  jmp     loc_140014D0D
0x14001497f  mov     edx, 358h; Length
0x140014984  lea     rcx, [rbp+VirtualAddress]; VirtualAddress
0x140014988  mov     r8d, 68456F50h; Tag
0x14001498e  mov     r12b, r14b
0x140014991  call    cs:__imp_NdisAllocateMemoryWithTag
0x140014998  nop     dword ptr [rax+rax+00h]
0x14001499d  test    eax, eax
0x14001499f  jz      short loc_1400149AC
0x1400149a1  mov     r14d, 0C000009Ah
0x1400149a7  jmp     loc_140014B36
0x1400149ac  mov     rcx, [rbp+VirtualAddress]; void *
0x1400149b0  mov     r9b, 1
0x1400149b3  call    TpCallInitialize
0x1400149b8  mov     r14d, eax
0x1400149bb  test    eax, eax
0x1400149bd  jnz     loc_140014B36
0x1400149c3  mov     r8, [rbp+VirtualAddress]
0x1400149c7  lea     rsi, [rbx+60h]
0x1400149cb  mov     rcx, [rsi]
0x1400149ce  movzx   edx, di
0x1400149d1  call    InsertToHandleTable
0x1400149d6  mov     rcx, rax
0x1400149d9  test    rax, rax
0x1400149dc  jnz     short loc_1400149E9
0x1400149de  mov     r14d, 0C0012002h
0x1400149e4  jmp     loc_140014B36
0x1400149e9  mov     rax, [rbp+VirtualAddress]
0x1400149ed  lea     rdi, [rbx+2ACh]
0x1400149f4  inc     dword ptr [rdi]
0x1400149f6  mov     [rax+70h], rcx
0x1400149fa  mov     rax, [rbp+VirtualAddress]
0x1400149fe  mov     [rax+60h], rbx
0x140014a02  cmp     qword ptr [rbx+80h], 0
0x140014a0a  jz      loc_140014AFE
0x140014a10  cmp     qword ptr [rbx+88h], 0
0x140014a18  jz      loc_140014AFE
0x140014a1e  mov     dl, [rbx+10h]; NewIrql
0x140014a21  mov     rcx, r15; SpinLock
0x140014a24  call    cs:__imp_KeReleaseSpinLock
0x140014a2b  nop     dword ptr [rax+rax+00h]
0x140014a30  mov     r8, [rbp+VirtualAddress]; MiniportVcContext
0x140014a34  mov     rdx, [rbx+80h]; NdisAfHandle
0x140014a3b  mov     rcx, [rbx+48h]; MiniportAdapterHandle
0x140014a3f  lea     r9, [r8+0A8h]; NdisVcHandle
0x140014a46  call    cs:__imp_NdisMCmCreateVc
0x140014a4d  nop     dword ptr [rax+rax+00h]
0x140014a52  mov     r14d, eax
0x140014a55  test    eax, eax
0x140014a57  jz      short loc_140014AA9
0x140014a59  mov     rcx, cs:WPP_GLOBAL_Control
0x140014a60  lea     rax, WPP_GLOBAL_Control
0x140014a67  cmp     rcx, rax
0x140014a6a  jz      loc_140014C91
0x140014a70  mov     edx, [rcx+2Ch]
0x140014a73  test    dl, 2
0x140014a76  jz      loc_140014C91
0x140014a7c  cmp     byte ptr [rcx+29h], 1
0x140014a80  jb      loc_140014C91
0x140014a86  mov     r9, [rbp+VirtualAddress]
0x140014a8a  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140014a91  mov     rcx, [rcx+18h]
0x140014a95  mov     edx, 7Ah ; 'z'
0x140014a9a  mov     [rsp+30h+var_10], r14d
0x140014a9f  call    WPP_SF_qd
0x140014aa4  jmp     loc_140014C91
0x140014aa9  xor     edx, edx
0x140014aab  mov     rcx, rbx
0x140014aae  call    ReferenceAdapter
0x140014ab3  mov     rax, [rbp+VirtualAddress]
0x140014ab7  lock inc dword ptr [rax+18h]
0x140014abb  mov     rbx, [rbp+VirtualAddress]
0x140014abf  lea     rcx, [rbx+38h]; SpinLock
0x140014ac3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014aca  nop     dword ptr [rax+rax+00h]
0x140014acf  mov     [rbx+40h], al
0x140014ad2  mov     rax, [rbp+VirtualAddress]
0x140014ad6  or      dword ptr [rax+58h], 2
0x140014ada  mov     rdx, [rbp+VirtualAddress]
0x140014ade  lea     rcx, [rdx+38h]; SpinLock
0x140014ae2  mov     dl, [rdx+40h]; NewIrql
0x140014ae5  call    cs:__imp_KeReleaseSpinLock
0x140014aec  nop     dword ptr [rax+rax+00h]
0x140014af1  mov     rax, [rbp+VirtualAddress]
0x140014af5  lock inc dword ptr [rax+18h]
0x140014af9  xor     r14d, r14d
0x140014afc  jmp     short loc_140014B51
0x140014afe  mov     rcx, cs:WPP_GLOBAL_Control
0x140014b05  lea     rax, WPP_GLOBAL_Control
0x140014b0c  mov     r12b, 1
0x140014b0f  cmp     rcx, rax
0x140014b12  jz      short loc_140014B36
0x140014b14  mov     eax, [rcx+2Ch]
0x140014b17  test    al, 2
0x140014b19  jz      short loc_140014B36
0x140014b1b  cmp     [rcx+29h], r12b
0x140014b1f  jb      short loc_140014B36
0x140014b21  mov     rcx, [rcx+18h]
0x140014b25  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140014b2c  mov     edx, 79h ; 'y'
0x140014b31  call    WPP_SF_
0x140014b36  mov     dl, [rbx+10h]; NewIrql
0x140014b39  mov     rcx, r15; SpinLock
0x140014b3c  call    cs:__imp_KeReleaseSpinLock
0x140014b43  nop     dword ptr [rax+rax+00h]
0x140014b48  test    r14d, r14d
0x140014b4b  jnz     loc_140014C81
0x140014b51  mov     rbx, [rbp+VirtualAddress]
0x140014b55  mov     rcx, cs:WPP_GLOBAL_Control
0x140014b5c  lea     rsi, WPP_GLOBAL_Control
0x140014b63  lea     r12, WPP_d5eca6e7fcdc3e512a30350b25826940_Traceguids
0x140014b6a  mov     r15b, 8
0x140014b6d  cmp     rcx, rsi
0x140014b70  jz      short loc_140014B91
0x140014b72  mov     eax, [rcx+2Ch]
0x140014b75  test    r15b, al
0x140014b78  jz      short loc_140014B91
0x140014b7a  cmp     byte ptr [rcx+29h], 3
0x140014b7e  jb      short loc_140014B91
0x140014b80  mov     rcx, [rcx+18h]
0x140014b84  mov     edx, 0Eh
0x140014b89  mov     r8, r12
0x140014b8c  call    WPP_SF_
0x140014b91  lea     rdi, [rbx+38h]
0x140014b95  mov     rcx, rdi; SpinLock
0x140014b98  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014b9f  nop     dword ptr [rax+rax+00h]
0x140014ba4  mov     edx, [rbx+50h]
0x140014ba7  mov     [rbx+40h], al
0x140014baa  test    dl, 0Ch
0x140014bad  jnz     short loc_140014BFA
0x140014baf  mov     dl, al; NewIrql
0x140014bb1  mov     dword ptr [rbx+48h], 5
0x140014bb8  mov     rcx, rdi; SpinLock
0x140014bbb  call    cs:__imp_KeReleaseSpinLock
0x140014bc2  nop     dword ptr [rax+rax+00h]
0x140014bc7  mov     rdx, [rbp+arg_8]
0x140014bcb  xor     r9d, r9d
0x140014bce  mov     r8, r13
0x140014bd1  mov     rcx, rbx
0x140014bd4  call    FsmRun
0x140014bd9  mov     rcx, cs:WPP_GLOBAL_Control
0x140014be0  cmp     rcx, rsi
0x140014be3  jz      short loc_140014C62
0x140014be5  mov     eax, [rcx+2Ch]
0x140014be8  test    r15b, al
0x140014beb  jz      short loc_140014C62
0x140014bed  cmp     byte ptr [rcx+29h], 3
0x140014bf1  jb      short loc_140014C62
0x140014bf3  mov     edx, 11h
0x140014bf8  jmp     short loc_140014C56
0x140014bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x140014c01  cmp     rcx, rsi
0x140014c04  jz      short loc_140014C25
0x140014c06  mov     eax, [rcx+2Ch]
0x140014c09  test    r15b, al
0x140014c0c  jz      short loc_140014C25
0x140014c0e  cmp     byte ptr [rcx+29h], 3
0x140014c12  jb      short loc_140014C25
0x140014c14  mov     rcx, [rcx+18h]
0x140014c18  mov     edx, 0Fh
0x140014c1d  mov     r8, r12
0x140014c20  call    WPP_SF_
0x140014c25  mov     dl, [rbx+40h]; NewIrql
0x140014c28  mov     rcx, rdi; SpinLock
0x140014c2b  call    cs:__imp_KeReleaseSpinLock
0x140014c32  nop     dword ptr [rax+rax+00h]
0x140014c37  mov     rcx, cs:WPP_GLOBAL_Control
0x140014c3e  cmp     rcx, rsi
0x140014c41  jz      short loc_140014C62
0x140014c43  mov     eax, [rcx+2Ch]
0x140014c46  test    r15b, al
0x140014c49  jz      short loc_140014C62
0x140014c4b  cmp     byte ptr [rcx+29h], 3
0x140014c4f  jb      short loc_140014C62
0x140014c51  mov     edx, 10h
0x140014c56  mov     rcx, [rcx+18h]
0x140014c5a  mov     r8, r12
0x140014c5d  call    WPP_SF_
0x140014c62  mov     rcx, [rbp+VirtualAddress]
0x140014c66  add     rcx, 18h
0x140014c6a  or      eax, 0FFFFFFFFh
0x140014c6d  lock xadd [rcx], eax
0x140014c71  cmp     eax, 1
0x140014c74  jnz     short loc_140014CDC
0x140014c76  mov     rax, [rcx+8]
0x140014c7a  call    _guard_dispatch_icall
0x140014c7f  jmp     short loc_140014CDC
0x140014c81  lea     rsi, [rbx+60h]
0x140014c85  lea     rdi, [rbx+2ACh]
0x140014c8c  test    r12b, r12b
0x140014c8f  jz      short loc_140014CC7
0x140014c91  mov     rcx, r15; SpinLock
0x140014c94  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014c9b  nop     dword ptr [rax+rax+00h]
0x140014ca0  mov     rdx, [rbp+VirtualAddress]
0x140014ca4  mov     rcx, [rsi]
0x140014ca7  mov     [rbx+10h], al
0x140014caa  mov     rdx, [rdx+70h]
0x140014cae  call    RemoveFromHandleTable
0x140014cb3  mov     dl, [rbx+10h]; NewIrql
0x140014cb6  mov     rcx, r15; SpinLock
0x140014cb9  dec     dword ptr [rdi]
0x140014cbb  call    cs:__imp_KeReleaseSpinLock
0x140014cc2  nop     dword ptr [rax+rax+00h]
0x140014cc7  mov     rcx, [rbp+VirtualAddress]; VirtualAddress
0x140014ccb  test    rcx, rcx
0x140014cce  jz      short loc_140014CD5
0x140014cd0  call    TpCallCleanup
0x140014cd5  lea     rsi, WPP_GLOBAL_Control
0x140014cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x140014ce3  cmp     rcx, rsi
0x140014ce6  jz      short loc_140014D0D
0x140014ce8  mov     eax, [rcx+2Ch]
0x140014ceb  test    al, 2
0x140014ced  jz      short loc_140014D0D
0x140014cef  cmp     byte ptr [rcx+29h], 3
0x140014cf3  jb      short loc_140014D0D
0x140014cf5  mov     rcx, [rcx+18h]
0x140014cf9  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140014d00  mov     edx, 7Bh ; '{'
0x140014d05  mov     r9d, r14d
0x140014d08  call    WPP_SF_d
0x140014d0d  mov     rbx, [rsp+30h+arg_10]
0x140014d15  add     rsp, 30h
0x140014d19  pop     r15
0x140014d1b  pop     r14
0x140014d1d  pop     r13
0x140014d1f  pop     r12
  ... truncated ...
```
