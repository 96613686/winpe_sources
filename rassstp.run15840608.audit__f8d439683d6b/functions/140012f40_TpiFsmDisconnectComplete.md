# TpiFsmDisconnectComplete

- ea: `0x140012f40`
- end: `0x140013001`
- name: `TpiFsmDisconnectComplete`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400133f0`

## callees

- `0x1400018b0`
- `0x140002bd8`
- `0x140012f40`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012f8b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012f8b`

## pseudocode

```c
__int64 __fastcall TpiFsmDisconnectComplete(__int64 a1, char a2, char a3)
{
  KIRQL v6; // al
  __int64 v7; // r8
  int v8; // edx
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 32));
  *(_DWORD *)(a1 + 21088) &= ~0x200u;
  *(_BYTE *)(a1 + 508) = a3;
  if ( a2 )
  {
    *(_DWORD *)(a1 + 21088) &= ~4u;
    v8 = 3;
  }
  else
  {
    v8 = 4;
  }
  LOBYTE(v7) = v6;
  result = InitiateSstpContextCleanup(a1, v8, v7);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer) & 0x82;
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140012f40  push    rbx
0x140012f42  push    rsi
0x140012f43  push    rdi
0x140012f44  push    r14
0x140012f46  sub     rsp, 28h
0x140012f4a  mov     dil, r8b
0x140012f4d  mov     sil, dl
0x140012f50  mov     rbx, rcx
0x140012f53  mov     rcx, cs:WPP_GLOBAL_Control
0x140012f5a  lea     r14, WPP_GLOBAL_Control
0x140012f61  cmp     rcx, r14
0x140012f64  jz      short loc_140012F87
0x140012f66  mov     eax, [rcx+2Ch]
0x140012f69  and     eax, 82h
0x140012f6e  cmp     al, 82h
0x140012f70  jnz     short loc_140012F87
0x140012f72  mov     rcx, [rcx+18h]
0x140012f76  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140012f7d  mov     edx, 51h ; 'Q'
0x140012f82  call    WPP_SF_
0x140012f87  lea     rcx, [rbx+20h]; SpinLock
0x140012f8b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012f92  nop     dword ptr [rax+rax+00h]
0x140012f97  btr     dword ptr [rbx+5260h], 9
0x140012f9f  mov     [rbx+1FCh], dil
0x140012fa6  test    sil, sil
0x140012fa9  jz      short loc_140012FB9
0x140012fab  and     dword ptr [rbx+5260h], 0FFFFFFFBh
0x140012fb2  mov     edx, 3
0x140012fb7  jmp     short loc_140012FBE
0x140012fb9  mov     edx, 4
0x140012fbe  mov     r8b, al
0x140012fc1  mov     rcx, rbx
0x140012fc4  call    InitiateSstpContextCleanup
0x140012fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x140012fd0  cmp     rcx, r14
0x140012fd3  jz      short loc_140012FF6
0x140012fd5  mov     eax, [rcx+2Ch]
0x140012fd8  and     eax, 82h
0x140012fdd  cmp     al, 82h
0x140012fdf  jnz     short loc_140012FF6
0x140012fe1  mov     rcx, [rcx+18h]
0x140012fe5  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140012fec  mov     edx, 52h ; 'R'
0x140012ff1  call    WPP_SF_
0x140012ff6  add     rsp, 28h
0x140012ffa  pop     r14
0x140012ffc  pop     rdi
0x140012ffd  pop     rsi
0x140012ffe  pop     rbx
0x140012fff  retn
```
