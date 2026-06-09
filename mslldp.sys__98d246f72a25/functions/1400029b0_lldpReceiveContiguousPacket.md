# lldpReceiveContiguousPacket

- ea: `0x1400029b0`
- end: `0x140002b0b`
- name: `lldpReceiveContiguousPacket`
- size: `347`
- prototype: `void __fastcall(PVOID Context, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140002794`

## callees

- `0x1400029b0`
- `0x140002b20`
- `0x140002fe0`
- `0x140004860`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x140002ae0`
- `NDIS!NdisReleaseRWLock` at `0x140002ae0`
- `NDIS!NdisAcquireRWLockWrite` at `0x140002a98`
- `NDIS!NdisAcquireRWLockWrite` at `0x140002a98`

## pseudocode

```c
void __fastcall lldpReceiveContiguousPacket(PVOID Context, __int64 a2, char a3)
{
  __int64 v6; // r15
  int v7; // eax
  size_t Size; // [rsp+20h] [rbp-58h]
  size_t v9; // [rsp+28h] [rbp-50h]
  size_t v10[7]; // [rsp+40h] [rbp-38h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+88h] [rbp+10h] BYREF
  int v12; // [rsp+98h] [rbp+20h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( ((__int64)WPP_MAIN_CB.SecurityDescriptor & 0x40) != 0 )
    McTemplateK0qqqbr2_EtwWriteTransfer(
      (_DWORD)Context,
      a2,
      a3,
      *((_DWORD *)Context + 32),
      *(_DWORD *)(a2 + 88),
      *(_DWORD *)(a2 + 24),
      *(_QWORD *)(a2 + 80));
  v6 = *(_QWORD *)(a2 + 80);
  v12 = 0;
  v10[0] = 0;
  v7 = 22;
  if ( __ROR2__(*(_WORD *)(v6 + 12), 8) >= 0x600u )
    v7 = 14;
  _InterlockedIncrement64((volatile signed __int64 *)Context + 113);
  if ( (unsigned __int8)lldpValidateLldpduData(
                          (_DWORD)Context,
                          a2,
                          v7 + *(_DWORD *)(a2 + 80),
                          *(_DWORD *)(a2 + 24) - v7,
                          (__int64)v10 + 4,
                          (__int64)v10,
                          (__int64)&v12) )
  {
    NdisAcquireRWLockWrite(*((PNDIS_RW_LOCK_EX *)Context + 120), &LockState, a3 != 0);
    LODWORD(Size) = HIDWORD(v10[0]);
    LODWORD(v9) = v10[0];
    lldpUpdateNeighbor(Context, Size, v9, v12);
    NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)Context + 120), &LockState);
  }
  else
  {
    _InterlockedIncrement64((volatile signed __int64 *)Context + 112);
  }
}

```

## disassembly

```asm
0x1400029b0  mov     r11, rsp
0x1400029b3  mov     [r11+8], rbx
0x1400029b7  push    rbp
0x1400029b8  push    rsi
0x1400029b9  push    rdi
0x1400029ba  push    r14
0x1400029bc  push    r15
0x1400029be  sub     rsp, 50h
0x1400029c2  xor     eax, eax
0x1400029c4  movzx   ebp, r8b
0x1400029c8  test    byte ptr cs:WPP_MAIN_CB.SecurityDescriptor, 40h
0x1400029cf  mov     rbx, rdx
0x1400029d2  mov     rdi, rcx
0x1400029d5  mov     [r11+10h], ax
0x1400029da  mov     [r11+12h], al
0x1400029de  jz      short loc_140002A02
0x1400029e0  mov     rax, [rdx+50h]
0x1400029e4  mov     r9d, [rcx+80h]
0x1400029eb  mov     [r11-48h], rax
0x1400029ef  mov     eax, [rdx+18h]
0x1400029f2  mov     dword ptr [rsp+78h+var_50], eax
0x1400029f6  mov     eax, [rdx+58h]
0x1400029f9  mov     dword ptr [rsp+78h+Size], eax
0x1400029fd  call    McTemplateK0qqqbr2_EtwWriteTransfer
0x140002a02  mov     r15, [rbx+50h]
0x140002a06  xor     eax, eax
0x140002a08  mov     [rsp+78h+arg_18], eax
0x140002a0f  mov     r8d, 600h
0x140002a15  mov     dword ptr [rsp+78h+var_38], eax
0x140002a19  mov     edx, 0Eh
0x140002a1e  mov     dword ptr [rsp+78h+var_38+4], eax
0x140002a22  mov     eax, 16h
0x140002a27  movzx   ecx, word ptr [r15+0Ch]
0x140002a2c  ror     cx, 8
0x140002a30  cmp     cx, r8w
0x140002a34  cmovnb  eax, edx
0x140002a37  mov     ecx, eax
0x140002a39  lock inc qword ptr [rdi+388h]
0x140002a41  mov     r9d, [rbx+18h]
0x140002a45  mov     rdx, rbx
0x140002a48  mov     rsi, [rbx+50h]
0x140002a4c  sub     r9d, eax
0x140002a4f  add     rsi, rcx
0x140002a52  lea     rax, [rsp+78h+arg_18]
0x140002a5a  mov     qword ptr [rsp+78h+var_48], rax
0x140002a5f  mov     r8, rsi
0x140002a62  lea     rax, [rsp+78h+var_38]
0x140002a67  mov     rcx, rdi
0x140002a6a  mov     [rsp+78h+var_50], rax
0x140002a6f  lea     rax, [rsp+78h+var_38+4]
0x140002a74  mov     [rsp+78h+Size], rax
0x140002a79  call    lldpValidateLldpduData
0x140002a7e  test    al, al
0x140002a80  jz      short loc_140002B01
0x140002a82  mov     rcx, [rdi+3C0h]; Lock
0x140002a89  lea     rdx, [rsp+78h+LockState]; LockState
0x140002a91  test    bpl, bpl
0x140002a94  setnz   r8b; Flags
0x140002a98  call    cs:__imp_NdisAcquireRWLockWrite
0x140002a9f  nop     dword ptr [rax+rax+00h]
0x140002aa4  mov     eax, [rsp+78h+arg_18]
0x140002aab  lea     r8, [r15+6]
0x140002aaf  mov     [rsp+78h+var_48], eax; int
0x140002ab3  mov     r9, rsi
0x140002ab6  mov     eax, dword ptr [rsp+78h+var_38]
0x140002aba  mov     rdx, rbx
0x140002abd  mov     dword ptr [rsp+78h+var_50], eax; size_t
0x140002ac1  mov     rcx, rdi; Context
0x140002ac4  mov     eax, dword ptr [rsp+78h+var_38+4]
0x140002ac8  mov     dword ptr [rsp+78h+Size], eax; Size
0x140002acc  call    lldpUpdateNeighbor
0x140002ad1  mov     rcx, [rdi+3C0h]; Lock
0x140002ad8  lea     rdx, [rsp+78h+LockState]; LockState
0x140002ae0  call    cs:__imp_NdisReleaseRWLock
0x140002ae7  nop     dword ptr [rax+rax+00h]
0x140002aec  mov     rbx, [rsp+78h+arg_0]
0x140002af4  add     rsp, 50h
0x140002af8  pop     r15
0x140002afa  pop     r14
0x140002afc  pop     rdi
0x140002afd  pop     rsi
0x140002afe  pop     rbp
0x140002aff  retn
0x140002b01  lock inc qword ptr [rdi+380h]
0x140002b09  jmp     short loc_140002AEC
```
