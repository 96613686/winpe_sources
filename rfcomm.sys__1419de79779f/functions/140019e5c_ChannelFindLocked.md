# ChannelFindLocked

- ea: `0x140019e5c`
- end: `0x140019f67`
- name: `ChannelFindLocked`
- size: `267`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001127c`
- `0x14001138c`
- `0x140011634`
- `0x14001190c`
- `0x14001204c`
- `0x1400121d4`
- `0x140012590`
- `0x14001291c`
- `0x140012c60`
- `0x140013d20`
- `0x140018e9c`

## callees

- `0x140004a68`
- `0x140019e5c`
- `0x14001a20c`
- `0x14001e74c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019ebb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019ebb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019f16`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019f16`

## string_xrefs

- `0x140019eef`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`

## pseudocode

```c
__int64 *__fastcall ChannelFindLocked(__int64 a1, char a2, char a3)
{
  __int64 *v6; // rdi
  __int64 *i; // rcx

  v6 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_Ddd(WPP_GLOBAL_Control->DeviceExtension, a2, a3, a2 & 1);
  if ( !a3 )
    *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  for ( i = *(__int64 **)(a1 + 80); i != (__int64 *)(a1 + 80); i = (__int64 *)*i )
  {
    if ( *((_BYTE *)i + 184) == a2 && *((_DWORD *)i + 12) != 9 )
    {
      v6 = i;
      RefObj_AddRefEx(i + 3, 1145981254, 150, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
      break;
    }
  }
  if ( !a3 )
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      14,
      (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids,
      v6);
  return v6;
}

```

## disassembly

```asm
0x140019e5c  push    rbx
0x140019e5e  push    rbp
0x140019e5f  push    rsi
0x140019e60  push    rdi
0x140019e61  push    r14
0x140019e63  push    r15
0x140019e65  sub     rsp, 48h
0x140019e69  mov     bpl, r8b
0x140019e6c  movzx   r14d, dl
0x140019e70  mov     rbx, rcx
0x140019e73  xor     edi, edi
0x140019e75  lea     r15, WPP_RECORDER_INITIALIZED
0x140019e7c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140019e83  jz      short loc_140019EB2
0x140019e85  mov     rcx, cs:WPP_GLOBAL_Control
0x140019e8c  mov     eax, r14d
0x140019e8f  mov     r9d, r14d
0x140019e92  shr     eax, 1
0x140019e94  and     r9d, 1
0x140019e98  and     eax, 1Fh
0x140019e9b  mov     [rsp+78h+var_40], r9d
0x140019ea0  mov     rcx, [rcx+40h]
0x140019ea4  mov     [rsp+78h+var_48], eax
0x140019ea8  mov     dword ptr [rsp+78h+var_50], r14d
0x140019ead  call    WPP_RECORDER_SF_Ddd
0x140019eb2  test    bpl, bpl
0x140019eb5  jnz     short loc_140019ECA
0x140019eb7  lea     rcx, [rbx+38h]; SpinLock
0x140019ebb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019ec2  nop     dword ptr [rax+rax+00h]
0x140019ec7  mov     [rbx+40h], al
0x140019eca  lea     rax, [rbx+50h]
0x140019ece  mov     rcx, [rax]
0x140019ed1  jmp     short loc_140019EE5
0x140019ed3  cmp     [rcx+0B8h], r14b
0x140019eda  jnz     short loc_140019EE2
0x140019edc  cmp     dword ptr [rcx+30h], 9
0x140019ee0  jnz     short loc_140019EEC
0x140019ee2  mov     rcx, [rcx]
0x140019ee5  cmp     rcx, rax
0x140019ee8  jnz     short loc_140019ED3
0x140019eea  jmp     short loc_140019F0A
0x140019eec  mov     rdi, rcx
0x140019eef  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140019ef6  add     rcx, 18h
0x140019efa  mov     edx, 444E4946h
0x140019eff  mov     r8d, 96h
0x140019f05  call    RefObj_AddRefEx
0x140019f0a  test    bpl, bpl
0x140019f0d  jnz     short loc_140019F22
0x140019f0f  mov     dl, [rbx+40h]; NewIrql
0x140019f12  lea     rcx, [rbx+38h]; SpinLock
0x140019f16  call    cs:__imp_KeReleaseSpinLock
0x140019f1d  nop     dword ptr [rax+rax+00h]
0x140019f22  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140019f29  jz      short loc_140019F56
0x140019f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140019f32  lea     rax, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x140019f39  mov     r9d, 0Eh
0x140019f3f  mov     [rsp+78h+var_50], rdi
0x140019f44  mov     [rsp+78h+var_58], rax
0x140019f49  mov     rcx, [rcx+40h]
0x140019f4d  lea     r8d, [r9-0Bh]
0x140019f51  call    WPP_RECORDER_SF_q
0x140019f56  mov     rax, rdi
0x140019f59  add     rsp, 48h
0x140019f5d  pop     r15
0x140019f5f  pop     r14
0x140019f61  pop     rdi
0x140019f62  pop     rsi
0x140019f63  pop     rbp
0x140019f64  pop     rbx
0x140019f65  retn
```
