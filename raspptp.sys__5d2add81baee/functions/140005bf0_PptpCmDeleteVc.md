# PptpCmDeleteVc

- ea: `0x140005bf0`
- end: `0x140005ceb`
- name: `PptpCmDeleteVc`
- size: `251`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140001a70`
- `0x140003564`
- `0x140003aa8`
- `0x140003e08`
- `0x140003e38`
- `0x140005bf0`
- `0x140012798`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140005c81`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005c81`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005c38`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005c38`

## pseudocode

```c
__int64 __fastcall PptpCmDeleteVc(__int64 a1)
{
  char v2; // di
  KIRQL v3; // al
  int v4; // eax

  v2 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
  }
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  *(_DWORD *)(a1 + 424) &= ~1u;
  *(_BYTE *)(a1 + 104) = v3;
  v4 = *(_DWORD *)(a1 + 424);
  *(_QWORD *)(a1 + 224) = 0;
  if ( (v4 & 0x4000) != 0 )
  {
    v2 = 1;
    *(_DWORD *)(a1 + 424) = v4 & 0xFFFFBFFF;
  }
  CallDetachFromAdapter(a1);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        45,
        WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids,
        *(unsigned int *)(a1 + 200));
    }
    CtlDisconnectCall(a1);
  }
  CallpCancelCallTimers(a1);
  DereferenceRefCount(a1);
  return 0;
}

```

## disassembly

```asm
0x140005bf0  push    rbx
0x140005bf2  push    rbp
0x140005bf3  push    rsi
0x140005bf4  push    rdi
0x140005bf5  sub     rsp, 28h
0x140005bf9  mov     rbx, rcx
0x140005bfc  xor     dil, dil
0x140005bff  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c06  lea     rbp, WPP_GLOBAL_Control
0x140005c0d  cmp     rcx, rbp
0x140005c10  jz      short loc_140005C34
0x140005c12  mov     eax, [rcx+2Ch]
0x140005c15  test    al, 4
0x140005c17  jz      short loc_140005C34
0x140005c19  cmp     byte ptr [rcx+29h], 2
0x140005c1d  jb      short loc_140005C34
0x140005c1f  mov     rcx, [rcx+18h]
0x140005c23  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140005c2a  mov     edx, 2Ch ; ','
0x140005c2f  call    WPP_SF_
0x140005c34  lea     rcx, [rbx+60h]; SpinLock
0x140005c38  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005c3f  nop     dword ptr [rax+rax+00h]
0x140005c44  and     dword ptr [rbx+1A8h], 0FFFFFFFEh
0x140005c4b  mov     [rbx+68h], al
0x140005c4e  mov     eax, [rbx+1A8h]
0x140005c54  mov     qword ptr [rbx+0E0h], 0
0x140005c5f  bt      eax, 0Eh
0x140005c63  jnb     short loc_140005C72
0x140005c65  btr     eax, 0Eh
0x140005c69  mov     dil, 1
0x140005c6c  mov     [rbx+1A8h], eax
0x140005c72  mov     rcx, rbx
0x140005c75  call    CallDetachFromAdapter
0x140005c7a  mov     dl, [rbx+68h]; NewIrql
0x140005c7d  lea     rcx, [rbx+60h]; SpinLock
0x140005c81  call    cs:__imp_KeReleaseSpinLock
0x140005c88  nop     dword ptr [rax+rax+00h]
0x140005c8d  test    dil, dil
0x140005c90  jz      short loc_140005CCF
0x140005c92  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c99  cmp     rcx, rbp
0x140005c9c  jz      short loc_140005CC7
0x140005c9e  mov     eax, [rcx+2Ch]
0x140005ca1  test    al, 10h
0x140005ca3  jz      short loc_140005CC7
0x140005ca5  cmp     byte ptr [rcx+29h], 2
0x140005ca9  jb      short loc_140005CC7
0x140005cab  mov     r9d, [rbx+0C8h]
0x140005cb2  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140005cb9  mov     rcx, [rcx+18h]
0x140005cbd  mov     edx, 2Dh ; '-'
0x140005cc2  call    WPP_SF_d
0x140005cc7  mov     rcx, rbx
0x140005cca  call    CtlDisconnectCall
0x140005ccf  mov     rcx, rbx
0x140005cd2  call    CallpCancelCallTimers
0x140005cd7  mov     rcx, rbx
0x140005cda  call    DereferenceRefCount
0x140005cdf  xor     eax, eax
0x140005ce1  add     rsp, 28h
0x140005ce5  pop     rdi
0x140005ce6  pop     rsi
0x140005ce7  pop     rbp
0x140005ce8  pop     rbx
0x140005ce9  retn
```
