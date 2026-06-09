# NdisWanAllocateLinkCB

- ea: `0x14000c25c`
- end: `0x14000c47f`
- name: `NdisWanAllocateLinkCB`
- size: `547`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000a310`
- `0x140024008`

## callees

- `0x14000a290`
- `0x14000a648`
- `0x14000c25c`
- `0x140016700`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14000c450`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000c450`
- `ntoskrnl!KeInitializeEvent` at `0x14000c2e3`
- `ntoskrnl!KeInitializeEvent` at `0x14000c2e3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000c277`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000c277`

## pseudocode

```c
PVOID __fastcall NdisWanAllocateLinkCB(__int64 a1, unsigned int a2)
{
  PVOID v4; // rax
  PVOID v5; // rbx
  int v7; // ecx
  int v8; // eax
  __int64 (__fastcall *v9)(); // rax
  int v10; // eax

  v4 = ExAllocateFromNPagedLookasideList(&LinkProtoCBList);
  v5 = v4;
  if ( v4 )
  {
    memset(v4, 0, 0x2F0u);
    KeInitializeEvent((PRKEVENT)v5 + 9, SynchronizationEvent, 0);
    v7 = glMaxMTU;
    *((_DWORD *)v5 + 48) = 100;
    *((_DWORD *)v5 + 49) = 100;
    *((_DWORD *)v5 + 46) = glMRRU;
    *((_DWORD *)v5 + 38) = v7;
    *((_DWORD *)v5 + 4) = 1802398028;
    *((_QWORD *)v5 + 6) = 0;
    *((_DWORD *)v5 + 5) = 2;
    *((_QWORD *)v5 + 9) = a1;
    *((_DWORD *)v5 + 53) = 0;
    *((_BYTE *)v5 + 201) = 1;
    *((_DWORD *)v5 + 70) = *(_DWORD *)(a1 + 176);
    *((_DWORD *)v5 + 71) = *(_DWORD *)(a1 + 180);
    v8 = *(_DWORD *)(a1 + 204);
    *((_DWORD *)v5 + 77) = v8;
    *((_DWORD *)v5 + 76) = v8;
    *((_DWORD *)v5 + 69) = glMRU;
    *((_DWORD *)v5 + 68) = v7;
    v9 = SendOnLegacyLink;
    if ( (*(_DWORD *)(a1 + 20) & 1) == 0 )
      v9 = SendOnLink;
    *((_QWORD *)v5 + 14) = v9;
    if ( *(_DWORD *)(a1 + 120) == 12 && *(_DWORD *)(a1 + 124) == 12 )
    {
      *((_QWORD *)v5 + 15) = DetectBroadbandFraming;
      *((_DWORD *)v5 + 72) = 768;
      *((_DWORD *)v5 + 73) = 768;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids, v5);
      }
    }
    else
    {
      *((_QWORD *)v5 + 15) = DetectFraming;
    }
    if ( !a2 || a2 > *(_DWORD *)(a1 + 172) )
      a2 = *(_DWORD *)(a1 + 172);
    *((_DWORD *)v5 + 52) = a2;
    if ( !a2 )
      *((_DWORD *)v5 + 52) = 1;
    if ( (*(_DWORD *)(a1 + 20) & 1) != 0 )
      v10 = *(_DWORD *)(a1 + 260);
    else
      v10 = 1000;
    *((_DWORD *)v5 + 51) = v10;
    KeInitializeSpinLock((PKSPIN_LOCK)v5 + 92);
    *((_DWORD *)v5 + 7) = 1;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 48));
    return v5;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x14000c25c  mov     [rsp+arg_0], rbx
0x14000c261  mov     [rsp+arg_8], rsi
0x14000c266  push    rdi
0x14000c267  sub     rsp, 20h
0x14000c26b  mov     rdi, rcx
0x14000c26e  mov     esi, edx
0x14000c270  lea     rcx, LinkProtoCBList; Lookaside
0x14000c277  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000c27e  nop     dword ptr [rax+rax+00h]
0x14000c283  mov     rbx, rax
0x14000c286  test    rax, rax
0x14000c289  jnz     short loc_14000C2C5
0x14000c28b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c292  lea     rax, WPP_GLOBAL_Control
0x14000c299  cmp     rcx, rax
0x14000c29c  jz      short loc_14000C2BE
0x14000c29e  mov     eax, [rcx+2Ch]
0x14000c2a1  test    al, 40h
0x14000c2a3  jz      short loc_14000C2BE
0x14000c2a5  cmp     byte ptr [rcx+29h], 2
0x14000c2a9  jb      short loc_14000C2BE
0x14000c2ab  mov     rcx, [rcx+18h]
0x14000c2af  lea     edx, [rbx+1Ch]
0x14000c2b2  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x14000c2b9  call    WPP_SF_
0x14000c2be  xor     eax, eax
0x14000c2c0  jmp     loc_14000C46E
0x14000c2c5  xor     edx, edx; Val
0x14000c2c7  mov     r8d, 2F0h; Size
0x14000c2cd  mov     rcx, rbx; void *
0x14000c2d0  call    memset
0x14000c2d5  xor     r8d, r8d; State
0x14000c2d8  lea     rcx, [rbx+0D8h]; Event
0x14000c2df  lea     edx, [r8+1]; Type
0x14000c2e3  call    cs:__imp_KeInitializeEvent
0x14000c2ea  nop     dword ptr [rax+rax+00h]
0x14000c2ef  mov     ecx, cs:glMaxMTU
0x14000c2f5  mov     eax, 64h ; 'd'
0x14000c2fa  mov     [rbx+0C0h], eax
0x14000c300  mov     [rbx+0C4h], eax
0x14000c306  mov     eax, cs:glMRRU
0x14000c30c  mov     [rbx+0B8h], eax
0x14000c312  mov     [rbx+98h], ecx
0x14000c318  mov     dword ptr [rbx+10h], 6B6E694Ch
0x14000c31f  mov     qword ptr [rbx+30h], 0
0x14000c327  mov     dword ptr [rbx+14h], 2
0x14000c32e  mov     [rbx+48h], rdi
0x14000c332  mov     dword ptr [rbx+0D4h], 0
0x14000c33c  mov     byte ptr [rbx+0C9h], 1
0x14000c343  mov     eax, [rdi+0B0h]
0x14000c349  mov     [rbx+118h], eax
0x14000c34f  mov     eax, [rdi+0B4h]
0x14000c355  mov     [rbx+11Ch], eax
0x14000c35b  mov     eax, [rdi+0CCh]
0x14000c361  mov     [rbx+134h], eax
0x14000c367  mov     [rbx+130h], eax
0x14000c36d  mov     eax, cs:glMRU
0x14000c373  mov     [rbx+114h], eax
0x14000c379  mov     [rbx+110h], ecx
0x14000c37f  lea     rcx, SendOnLink
0x14000c386  mov     eax, [rdi+14h]
0x14000c389  test    al, 1
0x14000c38b  lea     rax, SendOnLegacyLink
0x14000c392  cmovz   rax, rcx
0x14000c396  mov     [rbx+70h], rax
0x14000c39a  cmp     dword ptr [rdi+78h], 0Ch
0x14000c39e  jnz     short loc_14000C3FE
0x14000c3a0  cmp     dword ptr [rdi+7Ch], 0Ch
0x14000c3a4  jnz     short loc_14000C3FE
0x14000c3a6  lea     rax, DetectBroadbandFraming
0x14000c3ad  mov     [rbx+78h], rax
0x14000c3b1  mov     eax, 300h
0x14000c3b6  mov     [rbx+120h], eax
0x14000c3bc  mov     [rbx+124h], eax
0x14000c3c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c3c9  lea     rax, WPP_GLOBAL_Control
0x14000c3d0  cmp     rcx, rax
0x14000c3d3  jz      short loc_14000C409
0x14000c3d5  test    dword ptr [rcx+2Ch], 8000h
0x14000c3dc  jz      short loc_14000C409
0x14000c3de  cmp     byte ptr [rcx+29h], 5
0x14000c3e2  jb      short loc_14000C409
0x14000c3e4  mov     rcx, [rcx+18h]
0x14000c3e8  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x14000c3ef  mov     edx, 1Dh
0x14000c3f4  mov     r9, rbx
0x14000c3f7  call    WPP_SF_q
0x14000c3fc  jmp     short loc_14000C409
0x14000c3fe  lea     rax, DetectFraming
0x14000c405  mov     [rbx+78h], rax
0x14000c409  test    esi, esi
0x14000c40b  jz      short loc_14000C415
0x14000c40d  cmp     esi, [rdi+0ACh]
0x14000c413  jbe     short loc_14000C41B
0x14000c415  mov     esi, [rdi+0ACh]
0x14000c41b  mov     [rbx+0D0h], esi
0x14000c421  test    esi, esi
0x14000c423  jnz     short loc_14000C42F
0x14000c425  mov     dword ptr [rbx+0D0h], 1
0x14000c42f  mov     eax, [rdi+14h]
0x14000c432  test    al, 1
0x14000c434  jz      short loc_14000C43E
0x14000c436  mov     eax, [rdi+104h]
0x14000c43c  jmp     short loc_14000C443
0x14000c43e  mov     eax, 3E8h
0x14000c443  lea     rcx, [rbx+2E0h]; SpinLock
0x14000c44a  mov     [rbx+0CCh], eax
0x14000c450  call    cs:__imp_KeInitializeSpinLock
0x14000c457  nop     dword ptr [rax+rax+00h]
0x14000c45c  mov     dword ptr [rbx+1Ch], 1
0x14000c463  lock inc dword ptr [rdi+10h]
0x14000c467  lock inc dword ptr [rdi+30h]
0x14000c46b  mov     rax, rbx
0x14000c46e  mov     rbx, [rsp+28h+arg_0]
0x14000c473  mov     rsi, [rsp+28h+arg_8]
0x14000c478  add     rsp, 20h
0x14000c47c  pop     rdi
0x14000c47d  retn
```
