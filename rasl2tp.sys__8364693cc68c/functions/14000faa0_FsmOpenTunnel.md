# FsmOpenTunnel

- ea: `0x14000faa0`
- end: `0x14000fd03`
- name: `FsmOpenTunnel`
- size: `611`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001850`
- `0x140003050`
- `0x140003080`
- `0x1400032f0`
- `0x14000faa0`
- `0x14000fd0c`
- `0x1400102a0`
- `0x1400109d0`
- `0x140012138`
- `0x140018f2c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000fbb9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fbd4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fbb9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fbd4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000fac3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000fac3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fb3a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fb8f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fb3a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fb8f`

## pseudocode

```c
void __fastcall FsmOpenTunnel(PVOID Entry, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v6; // rdx
  _DWORD *v7; // r14
  unsigned int v8; // ebp
  KIRQL v9; // al
  _QWORD *v10; // rdx
  _QWORD *v11; // r8
  _WORD *v12; // [rsp+28h] [rbp-50h]

  v3 = *(_QWORD *)(a3 + 24);
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 960), Entry);
  v7 = (_DWORD *)(a2 + 120);
  v8 = 0;
  if ( (*(_DWORD *)(a2 + 120) & 1) == 0 )
  {
    LOBYTE(v6) = *(_BYTE *)(a2 + 112);
    v8 = TransportOpen(v3 + 240, v6);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_6ae8e3282b593c5549b818ef668891aa_Traceguids, v8);
      }
    }
    else
    {
      SetFlags(a2 + 120, 1);
    }
  }
  *(_BYTE *)(a2 + 40) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
  if ( v8 )
    goto LABEL_15;
  if ( (*v7 & 0x100) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_6ae8e3282b593c5549b818ef668891aa_Traceguids);
    }
    v8 = -1073668063;
LABEL_15:
    v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 40));
    *(_DWORD *)(a3 + 128) = v8;
    *(_BYTE *)(a3 + 48) = v9;
    CallTransitionComplete(a2, a3, 0);
    KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 40), *(_BYTE *)(a3 + 48));
    CompleteVcs(a2);
    goto LABEL_16;
  }
  if ( (*v7 & 2) != 0 )
  {
    v10 = *(_QWORD **)(a2 + 136);
    if ( *v10 == a2 + 128 )
    {
      *(_QWORD *)(a3 + 96) = a2 + 128;
      *(_QWORD *)(a3 + 104) = v10;
      *v10 = a3 + 96;
      *(_QWORD *)(a2 + 136) = a3 + 96;
      goto LABEL_16;
    }
LABEL_31:
    __fastfail(3u);
  }
  if ( *(_DWORD *)(a2 + 124) != 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_6ae8e3282b593c5549b818ef668891aa_Traceguids);
    }
    SetFlags(a2 + 120, 2);
    v11 = *(_QWORD **)(a2 + 136);
    if ( *v11 == a2 + 128 )
    {
      *(_QWORD *)(a3 + 96) = a2 + 128;
      *(_QWORD *)(a3 + 104) = v11;
      *v11 = a3 + 96;
      *(_QWORD *)(a2 + 136) = a3 + 96;
      *(_DWORD *)(a2 + 124) = 1;
      SendControl(a2, 0, 1u, 0, 0, v12, 0);
      goto LABEL_16;
    }
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_6ae8e3282b593c5549b818ef668891aa_Traceguids);
  }
  FsmOpenCall(a2, a3);
LABEL_16:
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 32), *(_BYTE *)(a2 + 40));
}

```

## disassembly

```asm
0x14000faa0  push    rbx
0x14000faa2  push    rbp
0x14000faa3  push    rsi
0x14000faa4  push    rdi
0x14000faa5  push    r13
0x14000faa7  push    r14
0x14000faa9  push    r15
0x14000faab  sub     rsp, 40h
0x14000faaf  mov     rbx, [r8+18h]
0x14000fab3  mov     rdi, rdx
0x14000fab6  mov     rdx, rcx; Entry
0x14000fab9  mov     rsi, r8
0x14000fabc  lea     rcx, [rbx+3C0h]; Lookaside
0x14000fac3  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000faca  nop     dword ptr [rax+rax+00h]
0x14000facf  lea     r14, [rdi+78h]
0x14000fad3  xor     ebp, ebp
0x14000fad5  mov     eax, [r14]
0x14000fad8  lea     r13, WPP_GLOBAL_Control
0x14000fadf  test    al, 1
0x14000fae1  jnz     short loc_14000FB36
0x14000fae3  mov     dl, [rdi+70h]
0x14000fae6  lea     rcx, [rbx+0F0h]
0x14000faed  call    TransportOpen
0x14000faf2  mov     ebp, eax
0x14000faf4  test    eax, eax
0x14000faf6  jnz     short loc_14000FB05
0x14000faf8  lea     edx, [rax+1]
0x14000fafb  mov     rcx, r14
0x14000fafe  call    SetFlags
0x14000fb03  jmp     short loc_14000FB36
0x14000fb05  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fb0c  cmp     rcx, r13
0x14000fb0f  jz      short loc_14000FB36
0x14000fb11  mov     eax, [rcx+2Ch]
0x14000fb14  test    al, 8
0x14000fb16  jz      short loc_14000FB36
0x14000fb18  cmp     byte ptr [rcx+29h], 1
0x14000fb1c  jb      short loc_14000FB36
0x14000fb1e  mov     rcx, [rcx+18h]
0x14000fb22  lea     r8, WPP_6ae8e3282b593c5549b818ef668891aa_Traceguids
0x14000fb29  mov     edx, 0Bh
0x14000fb2e  mov     r9d, ebp
0x14000fb31  call    WPP_SF_d
0x14000fb36  lea     rcx, [rdi+20h]; SpinLock
0x14000fb3a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fb41  nop     dword ptr [rax+rax+00h]
0x14000fb46  mov     [rdi+28h], al
0x14000fb49  test    ebp, ebp
0x14000fb4b  jnz     short loc_14000FB8B
0x14000fb4d  mov     eax, [r14]
0x14000fb50  bt      eax, 8
0x14000fb54  jnb     loc_14000FBF0
0x14000fb5a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fb61  cmp     rcx, r13
0x14000fb64  jz      short loc_14000FB86
0x14000fb66  mov     eax, [rcx+2Ch]
0x14000fb69  test    al, 8
0x14000fb6b  jz      short loc_14000FB86
0x14000fb6d  cmp     byte ptr [rcx+29h], 1
0x14000fb71  jb      short loc_14000FB86
0x14000fb73  mov     rcx, [rcx+18h]
0x14000fb77  lea     edx, [rbp+0Ch]
0x14000fb7a  lea     r8, WPP_6ae8e3282b593c5549b818ef668891aa_Traceguids
0x14000fb81  call    WPP_SF_
0x14000fb86  mov     ebp, 0C0012021h
0x14000fb8b  lea     rcx, [rsi+28h]; SpinLock
0x14000fb8f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fb96  nop     dword ptr [rax+rax+00h]
0x14000fb9b  xor     r8d, r8d
0x14000fb9e  mov     [rsi+80h], ebp
0x14000fba4  mov     rdx, rsi
0x14000fba7  mov     [rsi+30h], al
0x14000fbaa  mov     rcx, rdi
0x14000fbad  call    CallTransitionComplete
0x14000fbb2  mov     dl, [rsi+30h]; NewIrql
0x14000fbb5  lea     rcx, [rsi+28h]; SpinLock
0x14000fbb9  call    cs:__imp_KeReleaseSpinLock
0x14000fbc0  nop     dword ptr [rax+rax+00h]
0x14000fbc5  mov     rcx, rdi
0x14000fbc8  call    CompleteVcs
0x14000fbcd  mov     dl, [rdi+28h]; NewIrql
0x14000fbd0  lea     rcx, [rdi+20h]; SpinLock
0x14000fbd4  call    cs:__imp_KeReleaseSpinLock
0x14000fbdb  nop     dword ptr [rax+rax+00h]
0x14000fbe0  add     rsp, 40h
0x14000fbe4  pop     r15
0x14000fbe6  pop     r14
0x14000fbe8  pop     r13
0x14000fbea  pop     rdi
0x14000fbeb  pop     rsi
0x14000fbec  pop     rbp
0x14000fbed  pop     rbx
0x14000fbee  retn
0x14000fbf0  mov     ebx, 2
0x14000fbf5  test    bl, al
0x14000fbf7  jz      short loc_14000FC21
0x14000fbf9  lea     rcx, [rdi+80h]
0x14000fc00  mov     rdx, [rcx+8]
0x14000fc04  cmp     [rdx], rcx
0x14000fc07  jnz     loc_14000FCBB
0x14000fc0d  lea     rax, [rsi+60h]
0x14000fc11  mov     [rax], rcx
0x14000fc14  mov     [rax+8], rdx
0x14000fc18  mov     [rdx], rax
0x14000fc1b  mov     [rcx+8], rax
0x14000fc1f  jmp     short loc_14000FBCD
0x14000fc21  cmp     dword ptr [rdi+7Ch], 3
0x14000fc25  jnz     short loc_14000FC6C
0x14000fc27  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc2e  cmp     rcx, r13
0x14000fc31  jz      short loc_14000FC5C
0x14000fc33  mov     eax, [rcx+2Ch]
0x14000fc36  test    al, 8
0x14000fc38  jz      short loc_14000FC5C
0x14000fc3a  cmp     [rcx+29h], bl
0x14000fc3d  jb      short loc_14000FC5C
0x14000fc3f  mov     rcx, [rcx+18h]
0x14000fc43  lea     r8, WPP_6ae8e3282b593c5549b818ef668891aa_Traceguids
0x14000fc4a  mov     edx, 0Dh
0x14000fc4f  mov     [rsp+78h+var_58], rsi
0x14000fc54  mov     r9, rdi
0x14000fc57  call    WPP_SF_qq
0x14000fc5c  mov     rdx, rsi
0x14000fc5f  mov     rcx, rdi
0x14000fc62  call    FsmOpenCall
0x14000fc67  jmp     loc_14000FBCD
0x14000fc6c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc73  cmp     rcx, r13
0x14000fc76  jz      short loc_14000FCA1
0x14000fc78  mov     eax, [rcx+2Ch]
0x14000fc7b  test    al, 8
0x14000fc7d  jz      short loc_14000FCA1
0x14000fc7f  cmp     [rcx+29h], bl
0x14000fc82  jb      short loc_14000FCA1
0x14000fc84  mov     rcx, [rcx+18h]
0x14000fc88  lea     r8, WPP_6ae8e3282b593c5549b818ef668891aa_Traceguids
0x14000fc8f  mov     edx, 0Eh
0x14000fc94  mov     [rsp+78h+var_58], rsi
0x14000fc99  mov     r9, rdi
0x14000fc9c  call    WPP_SF_qq
0x14000fca1  mov     edx, ebx
0x14000fca3  mov     rcx, r14
0x14000fca6  call    SetFlags
0x14000fcab  lea     rdx, [rdi+80h]
0x14000fcb2  mov     r8, [rdx+8]
0x14000fcb6  cmp     [r8], rdx
0x14000fcb9  jz      short loc_14000FCC2
0x14000fcbb  mov     ecx, 3
0x14000fcc0  int     29h; Win8: RtlFailFast(ecx)
0x14000fcc2  lea     rax, [rsi+60h]
0x14000fcc6  mov     [rsp+78h+var_48], 0
0x14000fcce  mov     [rax], rdx
0x14000fcd1  xor     r9d, r9d
0x14000fcd4  mov     [rax+8], r8
0x14000fcd8  mov     rcx, rdi
0x14000fcdb  mov     [r8], rax
0x14000fcde  mov     r8d, 1
0x14000fce4  mov     [rdx+8], rax
0x14000fce8  xor     edx, edx
0x14000fcea  mov     dword ptr [rdi+7Ch], 1
0x14000fcf1  mov     dword ptr [rsp+78h+var_58], 0
0x14000fcf9  call    SendControl
0x14000fcfe  jmp     loc_14000FBCD
```
