# RfcommRemoveFirewallEntry

- ea: `0x140003074`
- end: `0x1400031be`
- name: `RfcommRemoveFirewallEntry`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002ac8`

## callees

- `0x140002e20`
- `0x140003074`
- `0x140003cb4`
- `0x140004b4c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003092`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003092`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400031a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400031a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000312b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000312b`

## pseudocode

```c
__int64 __fastcall RfcommRemoveFirewallEntry(__int64 a1, __int64 a2, __int64 a3)
{
  KSPIN_LOCK *v3; // rbp
  KIRQL v7; // r14
  __int64 v8; // rcx
  _QWORD *FirewallEntry; // rax
  int v10; // edx
  void *v11; // rbx
  _QWORD *v12; // rcx
  void **v13; // rax
  unsigned int v14; // edi
  int v15; // r9d

  v3 = (KSPIN_LOCK *)(a1 + 368);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 368));
  FirewallEntry = (_QWORD *)RfcommFindFirewallEntry(v8, (unsigned __int64 *)(a1 + 384), a3);
  v11 = FirewallEntry;
  if ( !FirewallEntry )
  {
    v14 = -1073741275;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_14;
    v15 = 56;
    goto LABEL_13;
  }
  if ( FirewallEntry[2] != a2 )
  {
    v14 = -1073741734;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_14;
    v15 = 55;
LABEL_13:
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      19,
      v15,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      v14);
    goto LABEL_14;
  }
  v12 = (_QWORD *)*FirewallEntry;
  if ( *(_QWORD **)(*FirewallEntry + 8LL) != FirewallEntry || (v13 = (void **)FirewallEntry[1], *v13 != v11) )
    __fastfail(3u);
  *v13 = v12;
  v14 = 0;
  v12[1] = v13;
  --*(_DWORD *)(a1 + 376);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      19,
      54,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      (char)v11,
      *(_DWORD *)(a1 + 376));
  ExFreePoolWithTag(v11, 0);
LABEL_14:
  KeReleaseSpinLock(v3, v7);
  return v14;
}

```

## disassembly

```asm
0x140003074  push    rbx
0x140003076  push    rbp
0x140003077  push    rsi
0x140003078  push    rdi
0x140003079  push    r14
0x14000307b  sub     rsp, 40h
0x14000307f  lea     rbp, [rcx+170h]
0x140003086  mov     rsi, rcx
0x140003089  mov     rcx, rbp; SpinLock
0x14000308c  mov     rbx, r8
0x14000308f  mov     rdi, rdx
0x140003092  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003099  nop     dword ptr [rax+rax+00h]
0x14000309e  lea     rdx, [rsi+180h]
0x1400030a5  mov     r8, rbx
0x1400030a8  mov     r14b, al
0x1400030ab  call    RfcommFindFirewallEntry
0x1400030b0  mov     rbx, rax
0x1400030b3  test    rax, rax
0x1400030b6  jz      loc_14000315D
0x1400030bc  cmp     [rax+10h], rdi
0x1400030c0  jnz     short loc_140003140
0x1400030c2  mov     rcx, [rax]
0x1400030c5  cmp     [rcx+8], rax
0x1400030c9  jnz     short loc_140003139
0x1400030cb  mov     rax, [rax+8]
0x1400030cf  cmp     [rax], rbx
0x1400030d2  jnz     short loc_140003139
0x1400030d4  mov     [rax], rcx
0x1400030d7  xor     edi, edi
0x1400030d9  mov     [rcx+8], rax
0x1400030dd  dec     dword ptr [rsi+178h]
0x1400030e3  mov     ecx, [rsi+178h]
0x1400030e9  lea     rax, WPP_RECORDER_INITIALIZED
0x1400030f0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400030f7  jz      short loc_140003126
0x1400030f9  mov     [rsp+68h+var_38], ecx
0x1400030fd  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140003104  mov     rcx, cs:WPP_GLOBAL_Control
0x14000310b  lea     r9d, [rdi+36h]
0x14000310f  mov     [rsp+68h+var_40], rbx
0x140003114  lea     r8d, [rdi+13h]
0x140003118  mov     [rsp+68h+var_48], rax
0x14000311d  mov     rcx, [rcx+40h]
0x140003121  call    WPP_RECORDER_SF_qD
0x140003126  xor     edx, edx; Tag
0x140003128  mov     rcx, rbx; P
0x14000312b  call    cs:__imp_ExFreePoolWithTag
0x140003132  nop     dword ptr [rax+rax+00h]
0x140003137  jmp     short loc_14000319E
0x140003139  mov     ecx, 3
0x14000313e  int     29h; Win8: RtlFailFast(ecx)
0x140003140  mov     edi, 0C000005Ah
0x140003145  lea     rax, WPP_RECORDER_INITIALIZED
0x14000314c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003153  jz      short loc_14000319E
0x140003155  mov     r9d, 37h ; '7'
0x14000315b  jmp     short loc_140003178
0x14000315d  mov     edi, 0C0000225h
0x140003162  lea     rax, WPP_RECORDER_INITIALIZED
0x140003169  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003170  jz      short loc_14000319E
0x140003172  mov     r9d, 38h ; '8'
0x140003178  mov     rcx, cs:WPP_GLOBAL_Control
0x14000317f  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140003186  mov     dword ptr [rsp+68h+var_40], edi
0x14000318a  mov     r8d, 13h
0x140003190  mov     [rsp+68h+var_48], rax
0x140003195  mov     rcx, [rcx+40h]
0x140003199  call    WPP_RECORDER_SF_d
0x14000319e  mov     dl, r14b; NewIrql
0x1400031a1  mov     rcx, rbp; SpinLock
0x1400031a4  call    cs:__imp_KeReleaseSpinLock
0x1400031ab  nop     dword ptr [rax+rax+00h]
0x1400031b0  mov     eax, edi
0x1400031b2  add     rsp, 40h
0x1400031b6  pop     r14
0x1400031b8  pop     rdi
0x1400031b9  pop     rsi
0x1400031ba  pop     rbp
0x1400031bb  pop     rbx
0x1400031bc  retn
```
