# CallDisconnectFromCtl

- ea: `0x14000f0d8`
- end: `0x14000f21c`
- name: `CallDisconnectFromCtl`
- size: `324`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f588`
- `0x14000fbac`
- `0x140011050`
- `0x140012798`

## callees

- `0x140003e08`
- `0x140007710`
- `0x14000f0d8`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000f19c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f1af`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f19c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f1af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f127`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f13e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f127`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f13e`

## pseudocode

```c
void __fastcall CallDisconnectFromCtl(__int64 a1, __int64 a2)
{
  char v4; // bp
  KIRQL v5; // al
  __int64 v6; // rbx
  __int64 v7; // rdx
  _QWORD *v8; // rcx

  v4 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x57u,
      (__int64)WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
  }
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  v6 = *(_QWORD *)(a1 + 56);
  *(_BYTE *)(a1 + 104) = v5;
  *(_BYTE *)(v6 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 8));
  if ( a2 && *(_DWORD *)(a2 + 32) == 1414550608 && *(_QWORD *)(a1 + 80) == a2 )
  {
    *(_QWORD *)(a1 + 80) = 0;
    v7 = *(_QWORD *)(a1 + 16);
    if ( *(_QWORD *)(v7 + 8) != a1 + 16 || (v8 = *(_QWORD **)(a1 + 24), *v8 != a1 + 16) )
      __fastfail(3u);
    *v8 = v7;
    v4 = 1;
    *(_QWORD *)(v7 + 8) = v8;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 56) + 8LL), *(_BYTE *)(*(_QWORD *)(a1 + 56) + 16LL));
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x58u,
        (__int64)WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 16), 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(__int64))(a2 + 24))(a2);
  }
}

```

## disassembly

```asm
0x14000f0d8  push    rbx
0x14000f0da  push    rbp
0x14000f0db  push    rsi
0x14000f0dc  push    rdi
0x14000f0dd  push    r14
0x14000f0df  push    r15
0x14000f0e1  sub     rsp, 28h
0x14000f0e5  mov     rdi, rdx
0x14000f0e8  mov     rsi, rcx
0x14000f0eb  xor     bpl, bpl
0x14000f0ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f0f5  lea     r15, WPP_GLOBAL_Control
0x14000f0fc  cmp     rcx, r15
0x14000f0ff  jz      short loc_14000F123
0x14000f101  mov     eax, [rcx+2Ch]
0x14000f104  test    al, 8
0x14000f106  jz      short loc_14000F123
0x14000f108  cmp     byte ptr [rcx+29h], 2
0x14000f10c  jb      short loc_14000F123
0x14000f10e  mov     rcx, [rcx+18h]
0x14000f112  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x14000f119  mov     edx, 57h ; 'W'
0x14000f11e  call    WPP_SF_
0x14000f123  lea     rcx, [rsi+60h]; SpinLock
0x14000f127  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f12e  nop     dword ptr [rax+rax+00h]
0x14000f133  mov     rbx, [rsi+38h]
0x14000f137  mov     [rsi+68h], al
0x14000f13a  lea     rcx, [rbx+8]; SpinLock
0x14000f13e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f145  nop     dword ptr [rax+rax+00h]
0x14000f14a  mov     [rbx+10h], al
0x14000f14d  test    rdi, rdi
0x14000f150  jz      short loc_14000F191
0x14000f152  cmp     dword ptr [rdi+20h], 54505450h
0x14000f159  jnz     short loc_14000F191
0x14000f15b  cmp     [rsi+50h], rdi
0x14000f15f  jnz     short loc_14000F191
0x14000f161  lea     rax, [rsi+10h]
0x14000f165  mov     qword ptr [rsi+50h], 0
0x14000f16d  mov     rdx, [rax]
0x14000f170  cmp     [rdx+8], rax
0x14000f174  jnz     loc_14000F215
0x14000f17a  mov     rcx, [rax+8]
0x14000f17e  cmp     [rcx], rax
0x14000f181  jnz     loc_14000F215
0x14000f187  mov     [rcx], rdx
0x14000f18a  mov     bpl, 1
0x14000f18d  mov     [rdx+8], rcx
0x14000f191  mov     rdx, [rsi+38h]
0x14000f195  lea     rcx, [rdx+8]; SpinLock
0x14000f199  mov     dl, [rdx+10h]; NewIrql
0x14000f19c  call    cs:__imp_KeReleaseSpinLock
0x14000f1a3  nop     dword ptr [rax+rax+00h]
0x14000f1a8  mov     dl, [rsi+68h]; NewIrql
0x14000f1ab  lea     rcx, [rsi+60h]; SpinLock
0x14000f1af  call    cs:__imp_KeReleaseSpinLock
0x14000f1b6  nop     dword ptr [rax+rax+00h]
0x14000f1bb  test    bpl, bpl
0x14000f1be  jz      short loc_14000F207
0x14000f1c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f1c7  cmp     rcx, r15
0x14000f1ca  jz      short loc_14000F1EE
0x14000f1cc  mov     eax, [rcx+2Ch]
0x14000f1cf  test    al, 8
0x14000f1d1  jz      short loc_14000F1EE
0x14000f1d3  cmp     byte ptr [rcx+29h], 2
0x14000f1d7  jb      short loc_14000F1EE
0x14000f1d9  mov     rcx, [rcx+18h]
0x14000f1dd  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x14000f1e4  mov     edx, 58h ; 'X'
0x14000f1e9  call    WPP_SF_
0x14000f1ee  or      eax, 0FFFFFFFFh
0x14000f1f1  lock xadd [rdi+10h], eax
0x14000f1f6  cmp     eax, 1
0x14000f1f9  jnz     short loc_14000F207
0x14000f1fb  mov     rax, [rdi+18h]
0x14000f1ff  mov     rcx, rdi
0x14000f202  call    _guard_dispatch_icall
0x14000f207  add     rsp, 28h
0x14000f20b  pop     r15
0x14000f20d  pop     r14
0x14000f20f  pop     rdi
0x14000f210  pop     rsi
0x14000f211  pop     rbp
0x14000f212  pop     rbx
0x14000f213  retn
0x14000f215  mov     ecx, 3
0x14000f21a  int     29h; Win8: RtlFailFast(ecx)
```
