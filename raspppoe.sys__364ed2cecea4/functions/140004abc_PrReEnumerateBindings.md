# PrReEnumerateBindings

- ea: `0x140004abc`
- end: `0x140004ba2`
- name: `PrReEnumerateBindings`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000e7b0`

## callees

- `0x14000110c`
- `0x140004abc`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140004b20`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004b20`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004afe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004afe`
- `NDIS!NdisReEnumerateProtocolBindings` at `0x140004b61`
- `NDIS!NdisReEnumerateProtocolBindings` at `0x140004b61`

## pseudocode

```c
void PrReEnumerateBindings()
{
  KIRQL v0; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 113, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  v0 = KeAcquireSpinLockRaiseToDpc(&gl_lockProtocol);
  gl_fBindProtocol = 1;
  byte_14000A1F8 = v0;
  KeReleaseSpinLock(&gl_lockProtocol, v0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 114, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  NdisReEnumerateProtocolBindings(gl_NdisProtocolDriverHandle);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 115, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
}

```

## disassembly

```asm
0x140004abc  push    rbp
0x140004abe  sub     rsp, 20h
0x140004ac2  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ac9  lea     rbp, WPP_GLOBAL_Control
0x140004ad0  cmp     rcx, rbp
0x140004ad3  jz      short loc_140004AF7
0x140004ad5  mov     eax, [rcx+2Ch]
0x140004ad8  test    al, 4
0x140004ada  jz      short loc_140004AF7
0x140004adc  cmp     byte ptr [rcx+29h], 3
0x140004ae0  jb      short loc_140004AF7
0x140004ae2  mov     rcx, [rcx+18h]
0x140004ae6  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x140004aed  mov     edx, 71h ; 'q'
0x140004af2  call    WPP_SF_
0x140004af7  lea     rcx, gl_lockProtocol; SpinLock
0x140004afe  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004b05  nop     dword ptr [rax+rax+00h]
0x140004b0a  lea     rcx, gl_lockProtocol; SpinLock
0x140004b11  mov     cs:gl_fBindProtocol, 1
0x140004b18  mov     dl, al; NewIrql
0x140004b1a  mov     cs:byte_14000A1F8, al
0x140004b20  call    cs:__imp_KeReleaseSpinLock
0x140004b27  nop     dword ptr [rax+rax+00h]
0x140004b2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b33  cmp     rcx, rbp
0x140004b36  jz      short loc_140004B5A
0x140004b38  mov     eax, [rcx+2Ch]
0x140004b3b  test    al, 4
0x140004b3d  jz      short loc_140004B5A
0x140004b3f  cmp     byte ptr [rcx+29h], 3
0x140004b43  jb      short loc_140004B5A
0x140004b45  mov     rcx, [rcx+18h]
0x140004b49  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x140004b50  mov     edx, 72h ; 'r'
0x140004b55  call    WPP_SF_
0x140004b5a  mov     rcx, cs:gl_NdisProtocolDriverHandle; NdisProtocolHandle
0x140004b61  call    cs:__imp_NdisReEnumerateProtocolBindings
0x140004b68  nop     dword ptr [rax+rax+00h]
0x140004b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b74  cmp     rcx, rbp
0x140004b77  jz      short loc_140004B9B
0x140004b79  mov     eax, [rcx+2Ch]
0x140004b7c  test    al, 4
0x140004b7e  jz      short loc_140004B9B
0x140004b80  cmp     byte ptr [rcx+29h], 3
0x140004b84  jb      short loc_140004B9B
0x140004b86  mov     rcx, [rcx+18h]
0x140004b8a  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x140004b91  mov     edx, 73h ; 's'
0x140004b96  call    WPP_SF_
0x140004b9b  add     rsp, 20h
0x140004b9f  pop     rbp
0x140004ba0  retn
```
