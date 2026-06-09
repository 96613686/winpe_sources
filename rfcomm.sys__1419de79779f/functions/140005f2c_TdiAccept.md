# TdiAccept

- ea: `0x140005f2c`
- end: `0x1400060bc`
- name: `TdiAccept`
- size: `400`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140012590`
- `0x140018330`
- `0x1400186b4`

## callees

- `0x140003bf4`
- `0x140005f2c`
- `0x140006f68`
- `0x140009658`
- `0x14000c704`
- `0x14000dd28`
- `0x140018d08`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005fd3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005fd3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006034`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006054`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006034`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006054`
- `ntoskrnl!KeGetCurrentIrql` at `0x140005f67`
- `ntoskrnl!KeGetCurrentIrql` at `0x140005f67`

## string_xrefs

- `0x140006074`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
_UNKNOWN **__fastcall TdiAccept(__int64 a1)
{
  __int64 v1; // rbx
  unsigned int v3; // edi
  __int64 v4; // rbp
  KIRQL CurrentIrql; // al
  int v6; // edx
  __int64 Listener; // rdi
  _UNKNOWN **result; // rax
  int v9; // edx
  KIRQL v10; // al
  int v11; // edx
  char v12; // si

  v1 = *(_QWORD *)(a1 + 56);
  v3 = (*(unsigned __int8 *)(a1 + 184) >> 1) & 0x1F;
  v4 = *(_QWORD *)(v1 + 72);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentIrql = KeGetCurrentIrql();
    WPP_RECORDER_SF_qdd(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      15,
      74,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      v1,
      v3,
      CurrentIrql);
  }
  Listener = TdiFindListener(v4, v3);
  if ( Listener )
  {
    v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 56));
    v11 = *(_DWORD *)(v1 + 476);
    *(_BYTE *)(v1 + 64) = v10;
    *(_DWORD *)(v1 + 472) |= *(_DWORD *)(Listener + 212) & 0x60000;
    *(_DWORD *)(v1 + 288) |= *(_DWORD *)(Listener + 204) & 3;
    if ( (*(_DWORD *)(Listener + 212) & v11) == *(_DWORD *)(Listener + 212) )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 56), v10);
      TdiClientAcceptWithPolicy(a1, Listener);
    }
    else
    {
      v12 = 0;
      if ( !*(_DWORD *)(v1 + 468) )
      {
        v12 = 1;
        *(_DWORD *)(v1 + 468) = 1;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 56), v10);
      if ( v12 )
        BrbUpdate(v1);
    }
    result = (_UNKNOWN **)RefObj_ReleaseEx(
                            Listener + 24,
                            1145981254,
                            1965,
                            "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  }
  else
  {
    result = ChannelCompleteAccept(a1, 0, 0, -1073741258);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return (_UNKNOWN **)WPP_RECORDER_SF_(
                          WPP_GLOBAL_Control->DeviceExtension,
                          v9,
                          15,
                          75,
                          (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140005f2c  push    rbx
0x140005f2e  push    rbp
0x140005f2f  push    rsi
0x140005f30  push    rdi
0x140005f31  push    r12
0x140005f33  push    r14
0x140005f35  sub     rsp, 48h
0x140005f39  mov     rbx, [rcx+38h]
0x140005f3d  mov     rsi, rcx
0x140005f40  movzx   edi, byte ptr [rcx+0B8h]
0x140005f47  shr     edi, 1
0x140005f49  and     edi, 1Fh
0x140005f4c  mov     rbp, [rbx+48h]
0x140005f50  lea     r14, WPP_RECORDER_INITIALIZED
0x140005f57  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140005f5e  lea     r12, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140005f65  jz      short loc_140005FA2
0x140005f67  call    cs:__imp_KeGetCurrentIrql
0x140005f6e  nop     dword ptr [rax+rax+00h]
0x140005f73  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f7a  mov     r9d, 4Ah ; 'J'
0x140005f80  movzx   eax, al
0x140005f83  mov     [rsp+78h+var_40], eax
0x140005f87  mov     [rsp+78h+var_48], edi
0x140005f8b  mov     rcx, [rcx+40h]
0x140005f8f  lea     r8d, [r9-3Bh]
0x140005f93  mov     [rsp+78h+var_50], rbx
0x140005f98  mov     [rsp+78h+var_58], r12
0x140005f9d  call    WPP_RECORDER_SF_qdd
0x140005fa2  mov     edx, edi
0x140005fa4  mov     rcx, rbp
0x140005fa7  call    TdiFindListener
0x140005fac  mov     rdi, rax
0x140005faf  test    rax, rax
0x140005fb2  jnz     short loc_140005FCC
0x140005fb4  mov     r9d, 0C0000236h
0x140005fba  xor     r8d, r8d
0x140005fbd  xor     edx, edx
0x140005fbf  mov     rcx, rsi
0x140005fc2  call    ChannelCompleteAccept
0x140005fc7  jmp     loc_140006086
0x140005fcc  lea     rbp, [rbx+38h]
0x140005fd0  mov     rcx, rbp; SpinLock
0x140005fd3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005fda  nop     dword ptr [rax+rax+00h]
0x140005fdf  mov     edx, [rbx+1DCh]
0x140005fe5  mov     [rbx+40h], al
0x140005fe8  mov     ecx, [rdi+0D4h]
0x140005fee  and     ecx, 60000h
0x140005ff4  or      [rbx+1D8h], ecx
0x140005ffa  mov     ecx, [rdi+0CCh]
0x140006000  and     ecx, 3
0x140006003  or      [rbx+120h], ecx
0x140006009  mov     r8d, [rdi+0D4h]
0x140006010  and     edx, r8d
0x140006013  cmp     edx, r8d
0x140006016  jz      short loc_14000604F
0x140006018  xor     sil, sil
0x14000601b  cmp     dword ptr [rbx+1D4h], 0
0x140006022  jnz     short loc_14000602F
0x140006024  mov     esi, 1
0x140006029  mov     [rbx+1D4h], esi
0x14000602f  mov     dl, al; NewIrql
0x140006031  mov     rcx, rbp; SpinLock
0x140006034  call    cs:__imp_KeReleaseSpinLock
0x14000603b  nop     dword ptr [rax+rax+00h]
0x140006040  test    sil, sil
0x140006043  jz      short loc_14000606B
0x140006045  mov     rcx, rbx
0x140006048  call    BrbUpdate
0x14000604d  jmp     short loc_14000606B
0x14000604f  mov     dl, al; NewIrql
0x140006051  mov     rcx, rbp; SpinLock
0x140006054  call    cs:__imp_KeReleaseSpinLock
0x14000605b  nop     dword ptr [rax+rax+00h]
0x140006060  mov     rdx, rdi
0x140006063  mov     rcx, rsi
0x140006066  call    TdiClientAcceptWithPolicy
0x14000606b  lea     rcx, [rdi+18h]
0x14000606f  mov     edx, 444E4946h
0x140006074  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000607b  mov     r8d, 7ADh
0x140006081  call    RefObj_ReleaseEx
0x140006086  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000608d  jz      short loc_1400060AE
0x14000608f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006096  mov     r9d, 4Bh ; 'K'
0x14000609c  mov     [rsp+78h+var_58], r12
0x1400060a1  mov     rcx, [rcx+40h]
0x1400060a5  lea     r8d, [r9-3Ch]
0x1400060a9  call    WPP_RECORDER_SF_
0x1400060ae  add     rsp, 48h
0x1400060b2  pop     r14
0x1400060b4  pop     r12
0x1400060b6  pop     rdi
0x1400060b7  pop     rsi
0x1400060b8  pop     rbp
0x1400060b9  pop     rbx
0x1400060ba  retn
```
