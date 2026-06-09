# LcmCmCloseCall

- ea: `0x140001e60`
- end: `0x140001fb0`
- name: `LcmCmCloseCall`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140001850`
- `0x140001e60`
- `0x140003050`
- `0x1400031ec`
- `0x14001c050`
- `0x14001c860`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140001f41`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001f41`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001e83`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001e83`
- `NDIS!NdisCmCloseCallComplete` at `0x140001f95`
- `NDIS!NdisCmCloseCallComplete` at `0x140001f95`

## pseudocode

```c
__int64 __fastcall LcmCmCloseCall(__int64 a1)
{
  KIRQL v3; // al
  __int64 v4; // rcx
  int v5; // r11d
  char v6; // di
  __int64 v7; // rcx
  __int16 v8; // r11
  int v9; // [rsp+28h] [rbp-50h]
  int v10; // [rsp+30h] [rbp-48h]

  if ( *(_DWORD *)(a1 + 16) != 861155916 )
    return 3221291029LL;
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 40));
  v4 = a1 + 60;
  *(_BYTE *)(a1 + 48) = v3;
  v5 = *(_DWORD *)(a1 + 60);
  if ( (v5 & 0x200000) != 0 )
    ClearFlags(v4, 0x200000);
  if ( (v5 & 2) != 0 )
  {
    v6 = 1;
    ClearFlags(v4, 20486);
    SetFlags(v7, 0x8000);
    if ( (v8 & 0x2000) != 0 )
      *(_DWORD *)(a1 + 128) = -1073668064;
    ScheduleTunnelWork(*(_QWORD *)(a1 + 32), a1, (__int64)FsmCloseCall, 3, 0, v9, v10, 0);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids, a1);
    }
    v6 = 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 40), *(_BYTE *)(a1 + 48));
  if ( !v6 )
  {
    ++g_ulCallsNotClosable;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids);
    }
    NdisCmCloseCallComplete(-1073741823, *(NDIS_HANDLE *)(a1 + 304), 0);
  }
  return 259;
}

```

## disassembly

```asm
0x140001e60  push    rbx
0x140001e62  push    rbp
0x140001e63  push    rsi
0x140001e64  push    rdi
0x140001e65  sub     rsp, 58h
0x140001e69  cmp     dword ptr [rcx+10h], 3354324Ch
0x140001e70  mov     rbx, rcx
0x140001e73  jz      short loc_140001E7F
0x140001e75  mov     eax, 0C0010015h
0x140001e7a  jmp     loc_140001FA6
0x140001e7f  add     rcx, 28h ; '('; SpinLock
0x140001e83  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001e8a  nop     dword ptr [rax+rax+00h]
0x140001e8f  lea     rcx, [rbx+3Ch]
0x140001e93  mov     edx, 200000h
0x140001e98  mov     [rbx+30h], al
0x140001e9b  mov     r11d, [rcx]
0x140001e9e  test    edx, r11d
0x140001ea1  jz      short loc_140001EA8
0x140001ea3  call    ClearFlags
0x140001ea8  lea     rbp, WPP_GLOBAL_Control
0x140001eaf  test    r11b, 2
0x140001eb3  jz      short loc_140001F06
0x140001eb5  mov     edx, 5006h
0x140001eba  mov     dil, 1
0x140001ebd  call    ClearFlags
0x140001ec2  mov     edx, 8000h
0x140001ec7  call    SetFlags
0x140001ecc  bt      r11d, 0Dh
0x140001ed1  jnb     short loc_140001EDD
0x140001ed3  mov     dword ptr [rbx+80h], 0C0012020h
0x140001edd  mov     rcx, [rbx+20h]
0x140001ee1  lea     r8, FsmCloseCall
0x140001ee8  mov     [rsp+78h+var_40], 0
0x140001eed  mov     r9d, 3
0x140001ef3  mov     rdx, rbx
0x140001ef6  mov     [rsp+78h+var_58], 0
0x140001eff  call    ScheduleTunnelWork
0x140001f04  jmp     short loc_140001F3A
0x140001f06  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f0d  cmp     rcx, rbp
0x140001f10  jz      short loc_140001F37
0x140001f12  mov     eax, [rcx+2Ch]
0x140001f15  test    al, 4
0x140001f17  jz      short loc_140001F37
0x140001f19  cmp     byte ptr [rcx+29h], 1
0x140001f1d  jb      short loc_140001F37
0x140001f1f  mov     rcx, [rcx+18h]
0x140001f23  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x140001f2a  mov     edx, 1Eh
0x140001f2f  mov     r9, rbx
0x140001f32  call    WPP_SF_q
0x140001f37  xor     dil, dil
0x140001f3a  mov     dl, [rbx+30h]; NewIrql
0x140001f3d  lea     rcx, [rbx+28h]; SpinLock
0x140001f41  call    cs:__imp_KeReleaseSpinLock
0x140001f48  nop     dword ptr [rax+rax+00h]
0x140001f4d  test    dil, dil
0x140001f50  jnz     short loc_140001FA1
0x140001f52  inc     cs:g_ulCallsNotClosable
0x140001f58  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f5f  cmp     rcx, rbp
0x140001f62  jz      short loc_140001F86
0x140001f64  mov     eax, [rcx+2Ch]
0x140001f67  test    al, 4
0x140001f69  jz      short loc_140001F86
0x140001f6b  cmp     byte ptr [rcx+29h], 1
0x140001f6f  jb      short loc_140001F86
0x140001f71  mov     rcx, [rcx+18h]
0x140001f75  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x140001f7c  mov     edx, 1Fh
0x140001f81  call    WPP_SF_
0x140001f86  mov     rdx, [rbx+130h]; NdisVcHandle
0x140001f8d  xor     r8d, r8d; NdisPartyHandle
0x140001f90  mov     ecx, 0C0000001h; Status
0x140001f95  call    cs:__imp_NdisCmCloseCallComplete
0x140001f9c  nop     dword ptr [rax+rax+00h]
0x140001fa1  mov     eax, 103h
0x140001fa6  add     rsp, 58h
0x140001faa  pop     rdi
0x140001fab  pop     rsi
0x140001fac  pop     rbp
0x140001fad  pop     rbx
0x140001fae  retn
```
