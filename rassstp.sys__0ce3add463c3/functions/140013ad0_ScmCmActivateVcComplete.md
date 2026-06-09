# ScmCmActivateVcComplete

- ea: `0x140013ad0`
- end: `0x140013db4`
- name: `ScmCmActivateVcComplete`
- size: `740`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140013150`

## callees

- `0x1400018b0`
- `0x140002030`
- `0x140002bd8`
- `0x140002f88`
- `0x140003068`
- `0x140003938`
- `0x140013ad0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013b1d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013bec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013d2f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013b1d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013bec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013d2f`
- `ntoskrnl!IofCompleteRequest` at `0x140013bd5`
- `ntoskrnl!IofCompleteRequest` at `0x140013bd5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013b6f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013c3a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013d4f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013b6f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013c3a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013d4f`
- `NDIS!NdisCmMakeCallComplete` at `0x140013d20`
- `NDIS!NdisCmMakeCallComplete` at `0x140013d20`

## pseudocode

```c
void __fastcall ScmCmActivateVcComplete(int a1, __int64 a2)
{
  KIRQL v4; // al
  __int64 v5; // rsi
  KIRQL v6; // al
  __int64 v7; // r8
  KIRQL v8; // si
  bool v9; // zf
  struct _CO_CALL_PARAMETERS *CallParameters; // rdi
  __int64 v11; // r8
  __int64 v12; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
  *(_DWORD *)(a2 + 21088) &= ~8u;
  if ( !a1 )
  {
    _InterlockedIncrement((volatile signed __int32 *)a2);
    *(_DWORD *)(a2 + 21088) |= 0x100010u;
    *(_BYTE *)(a2 + 507) = 1;
  }
  v5 = *(_QWORD *)(a2 + 64);
  *(_QWORD *)(a2 + 64) = 0;
  if ( !v5 && !*(_BYTE *)(a2 + 21132) )
    a1 = -1073741536;
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 32), v4);
  if ( v5 )
  {
    if ( _InterlockedExchange64((volatile __int64 *)(v5 + 104), 0) )
    {
      *(_DWORD *)(v5 + 48) = a1;
      *(_QWORD *)(v5 + 56) = 0;
      IofCompleteRequest((PIRP)v5, 2);
      DereferenceRefCount(a2);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids, a2 + 484);
      }
      a1 = -1073741536;
    }
  }
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
  v8 = v6;
  v9 = a1 == 0;
  if ( a1 >= 0 )
  {
    if ( !*(_BYTE *)(a2 + 21092) )
    {
      CallParameters = *(struct _CO_CALL_PARAMETERS **)(a2 + 21048);
      if ( *(_BYTE *)(a2 + 505) )
      {
        FreeCallParams(*(_QWORD *)(a2 + 21048));
      }
      else
      {
        *(_DWORD *)(a2 + 21088) &= ~0x4000u;
        KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 32), v6);
        if ( *(_BYTE *)(a2 + 21132) )
        {
          v11 = *(_QWORD *)(a2 + 21112) >> 3;
        }
        else
        {
          CallParameters->Flags |= 2u;
          v12 = *(_QWORD *)(a2 + 21104) >> 3;
          CallParameters->CallMgrParameters->Transmit.TokenRate = v12;
          CallParameters->CallMgrParameters->Transmit.PeakBandwidth = v12;
          CallParameters->CallMgrParameters->Transmit.MaxSduSize = 4095;
          v11 = *(_QWORD *)(a2 + 21112) >> 3;
          CallParameters->CallMgrParameters->Receive.TokenRate = v11;
          CallParameters->CallMgrParameters->Receive.PeakBandwidth = v11;
          CallParameters->CallMgrParameters->Receive.MaxSduSize = 4095;
        }
        *(_DWORD *)(*(_QWORD *)(a2 + 21120) + 4LL) = *(_DWORD *)(a2 + 21128);
        **(_DWORD **)(a2 + 21120) = 1396789842;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF__guid_dd(
            WPP_GLOBAL_Control->AttachedDevice,
            47,
            (unsigned int)WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids,
            a2 + 484,
            *(_DWORD *)(a2 + 21128),
            v11);
        }
        if ( !*(_BYTE *)(a2 + 21132) )
          NdisCmMakeCallComplete(0, *(NDIS_HANDLE *)(a2 + 40), 0, 0, CallParameters);
        v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
      }
      *(_QWORD *)(a2 + 21048) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 32), v8);
      goto LABEL_36;
    }
    v9 = a1 == 0;
  }
  if ( v9 )
    a1 = -1073741536;
  LOBYTE(v7) = v6;
  *(_DWORD *)(a2 + 21096) = a1;
  InitiateSstpContextCleanup(a2, 4, v7);
LABEL_36:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
}

```

## disassembly

```asm
0x140013ad0  push    rbx
0x140013ad2  push    rbp
0x140013ad3  push    rsi
0x140013ad4  push    rdi
0x140013ad5  push    r12
0x140013ad7  push    r13
0x140013ad9  sub     rsp, 38h
0x140013add  mov     rbx, rdx
0x140013ae0  mov     edi, ecx
0x140013ae2  mov     rcx, cs:WPP_GLOBAL_Control
0x140013ae9  lea     r13, WPP_GLOBAL_Control
0x140013af0  cmp     rcx, r13
0x140013af3  jz      short loc_140013B16
0x140013af5  mov     eax, [rcx+2Ch]
0x140013af8  and     eax, 81h
0x140013afd  cmp     al, 81h
0x140013aff  jnz     short loc_140013B16
0x140013b01  mov     rcx, [rcx+18h]
0x140013b05  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140013b0c  mov     edx, 2Dh ; '-'
0x140013b11  call    WPP_SF_
0x140013b16  lea     rbp, [rbx+20h]
0x140013b1a  mov     rcx, rbp; SpinLock
0x140013b1d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013b24  nop     dword ptr [rax+rax+00h]
0x140013b29  and     dword ptr [rbx+5260h], 0FFFFFFF7h
0x140013b30  test    edi, edi
0x140013b32  jnz     short loc_140013B48
0x140013b34  lock inc dword ptr [rbx]
0x140013b37  or      dword ptr [rbx+5260h], 100010h
0x140013b41  mov     byte ptr [rbx+1FBh], 1
0x140013b48  mov     rsi, [rbx+40h]
0x140013b4c  mov     r12d, 0C0000120h
0x140013b52  mov     qword ptr [rbx+40h], 0
0x140013b5a  test    rsi, rsi
0x140013b5d  jnz     short loc_140013B6A
0x140013b5f  cmp     [rbx+528Ch], sil
0x140013b66  cmovz   edi, r12d
0x140013b6a  mov     dl, al; NewIrql
0x140013b6c  mov     rcx, rbp; SpinLock
0x140013b6f  call    cs:__imp_KeReleaseSpinLock
0x140013b76  nop     dword ptr [rax+rax+00h]
0x140013b7b  test    rsi, rsi
0x140013b7e  jz      short loc_140013BE9
0x140013b80  xor     eax, eax
0x140013b82  xchg    rax, [rsi+68h]
0x140013b86  test    rax, rax
0x140013b89  jnz     short loc_140013BC5
0x140013b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140013b92  cmp     rcx, r13
0x140013b95  jz      short loc_140013BC0
0x140013b97  mov     eax, [rcx+2Ch]
0x140013b9a  test    al, 2
0x140013b9c  jz      short loc_140013BC0
0x140013b9e  cmp     byte ptr [rcx+29h], 1
0x140013ba2  jb      short loc_140013BC0
0x140013ba4  mov     rcx, [rcx+18h]
0x140013ba8  lea     r9, [rbx+1E4h]
0x140013baf  mov     edx, 2Eh ; '.'
0x140013bb4  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140013bbb  call    WPP_SF__guid_
0x140013bc0  mov     edi, r12d
0x140013bc3  jmp     short loc_140013BE9
0x140013bc5  mov     dl, 2; PriorityBoost
0x140013bc7  mov     [rsi+30h], edi
0x140013bca  mov     rcx, rsi; Irp
0x140013bcd  mov     qword ptr [rsi+38h], 0
0x140013bd5  call    cs:__imp_IofCompleteRequest
0x140013bdc  nop     dword ptr [rax+rax+00h]
0x140013be1  mov     rcx, rbx
0x140013be4  call    DereferenceRefCount
0x140013be9  mov     rcx, rbp; SpinLock
0x140013bec  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013bf3  nop     dword ptr [rax+rax+00h]
0x140013bf8  mov     sil, al
0x140013bfb  test    edi, edi
0x140013bfd  js      loc_140013D5F
0x140013c03  cmp     byte ptr [rbx+5264h], 0
0x140013c0a  jnz     loc_140013D5D
0x140013c10  cmp     byte ptr [rbx+1F9h], 0
0x140013c17  mov     rdi, [rbx+5238h]
0x140013c1e  jz      short loc_140013C2D
0x140013c20  mov     rcx, rdi
0x140013c23  call    FreeCallParams
0x140013c28  jmp     loc_140013D3E
0x140013c2d  btr     dword ptr [rbx+5260h], 0Eh
0x140013c35  mov     dl, al; NewIrql
0x140013c37  mov     rcx, rbp; SpinLock
0x140013c3a  call    cs:__imp_KeReleaseSpinLock
0x140013c41  nop     dword ptr [rax+rax+00h]
0x140013c46  cmp     byte ptr [rbx+528Ch], 0
0x140013c4d  jz      short loc_140013C5C
0x140013c4f  mov     r8, [rbx+5278h]
0x140013c56  shr     r8, 3
0x140013c5a  jmp     short loc_140013CA5
0x140013c5c  or      dword ptr [rdi], 2
0x140013c5f  mov     rax, [rdi+8]
0x140013c63  mov     rcx, [rbx+5270h]
0x140013c6a  shr     rcx, 3
0x140013c6e  mov     [rax], ecx
0x140013c70  mov     rax, [rdi+8]
0x140013c74  mov     [rax+8], ecx
0x140013c77  mov     ecx, 0FFFh
0x140013c7c  mov     rax, [rdi+8]
0x140013c80  mov     [rax+18h], ecx
0x140013c83  mov     rax, [rdi+8]
0x140013c87  mov     r8, [rbx+5278h]
0x140013c8e  shr     r8, 3
0x140013c92  mov     [rax+20h], r8d
0x140013c96  mov     rax, [rdi+8]
0x140013c9a  mov     [rax+28h], r8d
0x140013c9e  mov     rax, [rdi+8]
0x140013ca2  mov     [rax+38h], ecx
0x140013ca5  mov     eax, [rbx+5288h]
0x140013cab  mov     rcx, [rbx+5280h]
0x140013cb2  mov     [rcx+4], eax
0x140013cb5  mov     rax, [rbx+5280h]
0x140013cbc  mov     dword ptr [rax], 53415252h
0x140013cc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140013cc9  cmp     rcx, r13
0x140013ccc  jz      short loc_140013D06
0x140013cce  mov     eax, [rcx+2Ch]
0x140013cd1  test    al, 2
0x140013cd3  jz      short loc_140013D06
0x140013cd5  cmp     byte ptr [rcx+29h], 3
0x140013cd9  jb      short loc_140013D06
0x140013cdb  mov     eax, [rbx+5288h]
0x140013ce1  lea     r9, [rbx+1E4h]
0x140013ce8  mov     rcx, [rcx+18h]
0x140013cec  mov     edx, 2Fh ; '/'
0x140013cf1  mov     [rsp+68h+var_40], r8d
0x140013cf6  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140013cfd  mov     dword ptr [rsp+68h+CallParameters], eax
0x140013d01  call    WPP_SF__guid_dd
0x140013d06  cmp     byte ptr [rbx+528Ch], 0
0x140013d0d  jnz     short loc_140013D2C
0x140013d0f  mov     rdx, [rbx+28h]; NdisVcHandle
0x140013d13  xor     r9d, r9d; CallMgrPartyContext
0x140013d16  xor     r8d, r8d; NdisPartyHandle
0x140013d19  mov     [rsp+68h+CallParameters], rdi; CallParameters
0x140013d1e  xor     ecx, ecx; Status
0x140013d20  call    cs:__imp_NdisCmMakeCallComplete
0x140013d27  nop     dword ptr [rax+rax+00h]
0x140013d2c  mov     rcx, rbp; SpinLock
0x140013d2f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013d36  nop     dword ptr [rax+rax+00h]
0x140013d3b  mov     sil, al
0x140013d3e  mov     dl, sil; NewIrql
0x140013d41  mov     qword ptr [rbx+5238h], 0
0x140013d4c  mov     rcx, rbp; SpinLock
0x140013d4f  call    cs:__imp_KeReleaseSpinLock
0x140013d56  nop     dword ptr [rax+rax+00h]
0x140013d5b  jmp     short loc_140013D79
0x140013d5d  test    edi, edi
0x140013d5f  cmovz   edi, r12d
0x140013d63  mov     r8b, al
0x140013d66  mov     edx, 4
0x140013d6b  mov     [rbx+5268h], edi
0x140013d71  mov     rcx, rbx
0x140013d74  call    InitiateSstpContextCleanup
0x140013d79  mov     rcx, cs:WPP_GLOBAL_Control
0x140013d80  cmp     rcx, r13
0x140013d83  jz      short loc_140013DA6
0x140013d85  mov     eax, [rcx+2Ch]
0x140013d88  and     eax, 81h
0x140013d8d  cmp     al, 81h
0x140013d8f  jnz     short loc_140013DA6
0x140013d91  mov     rcx, [rcx+18h]
0x140013d95  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140013d9c  mov     edx, 30h ; '0'
0x140013da1  call    WPP_SF_
0x140013da6  add     rsp, 38h
0x140013daa  pop     r13
0x140013dac  pop     r12
0x140013dae  pop     rdi
0x140013daf  pop     rsi
0x140013db0  pop     rbp
0x140013db1  pop     rbx
0x140013db2  retn
```
