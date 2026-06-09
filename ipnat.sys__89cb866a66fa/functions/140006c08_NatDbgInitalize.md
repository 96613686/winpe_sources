# NatDbgInitalize

- ea: `0x140006c08`
- end: `0x140006e12`
- name: `NatDbgInitalize`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140045078`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x1400068d8`
- `0x1400069b8`
- `0x140006c08`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x140006c9a`
- `ntoskrnl!ExAllocatePool3` at `0x140006c9a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140006d04`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140006d04`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140006c54`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140006c54`
- `ntoskrnl!KeInitializeSpinLock` at `0x140006ccd`
- `ntoskrnl!KeInitializeSpinLock` at `0x140006ccd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d6e`

## pseudocode

```c
__int64 NatDbgInitalize()
{
  __int64 v0; // rsi
  __int64 Pool3; // rax
  _DWORD *v2; // rbx
  int v3; // ebp
  __int64 v4; // r14
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rdi
  unsigned int v7; // edi
  _QWORD v9[9]; // [rsp+40h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
  }
  McGenEventRegister_EtwRegister();
  v9[1] = 0;
  v9[0] = 1;
  v0 = KeQueryMaximumProcessorCountEx(0xFFFFu) + 1;
  Pool3 = ExAllocatePool3(72, (v0 << 7) + 64, 1668437070, v9, 1);
  v2 = (_DWORD *)Pool3;
  if ( Pool3 )
  {
    v3 = 0;
    if ( (int)v0 > 0 )
    {
      v4 = Pool3 + 64;
      do
      {
        v5 = (unsigned __int64)(unsigned int)v3 << 7;
        v6 = v5 + v4;
        KeInitializeSpinLock((PKSPIN_LOCK)(v5 + v4 + 104));
        if ( v3 )
        {
          *(_QWORD *)(v6 + 96) = v4;
          *(_BYTE *)(v6 + 112) = 0;
        }
        else
        {
          if ( ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)v6, 0, 0, (POOL_TYPE)512, 0, 0x80u, 0x6372544Eu, 0) < 0 )
          {
            ExFreePoolWithTag(v2, 0x6372544Eu);
            goto LABEL_15;
          }
          *(_QWORD *)(v6 + 96) = 0;
          *(_BYTE *)(v6 + 112) = 1;
        }
        ++v3;
      }
      while ( v3 < (int)v0 );
    }
    v7 = 0;
    *v2 = v0;
    v2[1] = 0;
    *((_WORD *)v2 + 18) = 0;
    *((_QWORD *)v2 + 3) = 0;
    v2[2] = 1668437070;
    v2[3] = 1668437070;
    *((_QWORD *)v2 + 2) = 128;
    v2[8] = 512;
    NatDbgBufPool = v2;
    goto LABEL_21;
  }
LABEL_15:
  NatDbgBufPool = 0;
  if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 1) != 0 )
    McTemplateK0s_EtwWriteTransfer();
  v7 = -1073741801;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids, 3221225495LL);
LABEL_21:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids, v7);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140006c08  push    rbx
0x140006c0a  push    rbp
0x140006c0b  push    rsi
0x140006c0c  push    rdi
0x140006c0d  push    r13
0x140006c0f  push    r14
0x140006c11  sub     rsp, 58h
0x140006c15  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c1c  lea     r14, WPP_GLOBAL_Control
0x140006c23  cmp     rcx, r14
0x140006c26  jz      short loc_140006C4A
0x140006c28  mov     eax, [rcx+2Ch]
0x140006c2b  test    al, 1
0x140006c2d  jz      short loc_140006C4A
0x140006c2f  cmp     byte ptr [rcx+29h], 6
0x140006c33  jb      short loc_140006C4A
0x140006c35  mov     rcx, [rcx+18h]
0x140006c39  lea     r8, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140006c40  mov     edx, 0Ah
0x140006c45  call    WPP_SF_
0x140006c4a  call    McGenEventRegister_EtwRegister
0x140006c4f  mov     ecx, 0FFFFh; GroupNumber
0x140006c54  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x140006c5b  nop     dword ptr [rax+rax+00h]
0x140006c60  mov     r13d, 6372544Eh
0x140006c66  mov     [rsp+88h+var_40], 0
0x140006c6f  lea     r9, [rsp+88h+var_48]
0x140006c74  mov     [rsp+88h+var_48], 1
0x140006c7d  mov     r8d, r13d
0x140006c80  mov     [rsp+88h+Flags], 1
0x140006c88  lea     esi, [rax+1]
0x140006c8b  mov     ecx, 48h ; 'H'
0x140006c90  mov     edx, esi
0x140006c92  shl     rdx, 7
0x140006c96  add     rdx, 40h ; '@'
0x140006c9a  call    cs:__imp_ExAllocatePool3
0x140006ca1  nop     dword ptr [rax+rax+00h]
0x140006ca6  mov     rbx, rax
0x140006ca9  test    rax, rax
0x140006cac  jz      loc_140006D81
0x140006cb2  xor     ebp, ebp
0x140006cb4  test    esi, esi
0x140006cb6  jle     short loc_140006D37
0x140006cb8  lea     r14, [rax+40h]
0x140006cbc  mov     eax, ebp
0x140006cbe  lea     rcx, [r14+68h]
0x140006cc2  shl     rax, 7
0x140006cc6  add     rcx, rax; SpinLock
0x140006cc9  lea     rdi, [rax+r14]
0x140006ccd  call    cs:__imp_KeInitializeSpinLock
0x140006cd4  nop     dword ptr [rax+rax+00h]
0x140006cd9  test    ebp, ebp
0x140006cdb  jnz     short loc_140006D22
0x140006cdd  xor     eax, eax
0x140006cdf  mov     r9d, 200h; PoolType
0x140006ce5  mov     [rsp+88h+Depth], ax; Depth
0x140006cea  xor     r8d, r8d; Free
0x140006ced  mov     [rsp+88h+Tag], r13d; Tag
0x140006cf2  xor     edx, edx; Allocate
0x140006cf4  mov     [rsp+88h+Size], 80h; Size
0x140006cfd  mov     rcx, rdi; Lookaside
0x140006d00  mov     [rsp+88h+Flags], eax; Flags
0x140006d04  call    cs:__imp_ExInitializeLookasideListEx
0x140006d0b  nop     dword ptr [rax+rax+00h]
0x140006d10  test    eax, eax
0x140006d12  js      short loc_140006D68
0x140006d14  mov     qword ptr [rdi+60h], 0
0x140006d1c  mov     byte ptr [rdi+70h], 1
0x140006d20  jmp     short loc_140006D2A
0x140006d22  mov     [rdi+60h], r14
0x140006d26  mov     byte ptr [rdi+70h], 0
0x140006d2a  inc     ebp
0x140006d2c  cmp     ebp, esi
0x140006d2e  jl      short loc_140006CBC
0x140006d30  lea     r14, WPP_GLOBAL_Control
0x140006d37  xor     edi, edi
0x140006d39  mov     [rbx], esi
0x140006d3b  xor     eax, eax
0x140006d3d  mov     [rbx+4], edi
0x140006d40  mov     [rbx+24h], ax
0x140006d44  mov     [rbx+18h], rax
0x140006d48  mov     [rbx+8], r13d
0x140006d4c  mov     [rbx+0Ch], r13d
0x140006d50  mov     qword ptr [rbx+10h], 80h
0x140006d58  mov     dword ptr [rbx+20h], 200h
0x140006d5f  mov     cs:NatDbgBufPool, rbx
0x140006d66  jmp     short loc_140006DD0
0x140006d68  mov     edx, r13d; Tag
0x140006d6b  mov     rcx, rbx; P
0x140006d6e  call    cs:__imp_ExFreePoolWithTag
0x140006d75  nop     dword ptr [rax+rax+00h]
0x140006d7a  lea     r14, WPP_GLOBAL_Control
0x140006d81  test    byte ptr cs:WPP_MAIN_CB.Dpc.SystemArgument1, 1
0x140006d88  mov     cs:NatDbgBufPool, 0
0x140006d93  jz      short loc_140006D9A
0x140006d95  call    McTemplateK0s_EtwWriteTransfer
0x140006d9a  mov     edi, 0C0000017h
0x140006d9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006da6  cmp     rcx, r14
0x140006da9  jz      short loc_140006E02
0x140006dab  mov     eax, [rcx+2Ch]
0x140006dae  test    al, 1
0x140006db0  jz      short loc_140006DD0
0x140006db2  cmp     byte ptr [rcx+29h], 2
0x140006db6  jb      short loc_140006DD0
0x140006db8  mov     rcx, [rcx+18h]
0x140006dbc  lea     r8, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140006dc3  mov     edx, 0Bh
0x140006dc8  mov     r9d, edi
0x140006dcb  call    WPP_SF_d
0x140006dd0  mov     rcx, cs:WPP_GLOBAL_Control
0x140006dd7  cmp     rcx, r14
0x140006dda  jz      short loc_140006E02
0x140006ddc  mov     edx, [rcx+2Ch]
0x140006ddf  test    dl, 1
0x140006de2  jz      short loc_140006E02
0x140006de4  cmp     byte ptr [rcx+29h], 6
0x140006de8  jb      short loc_140006E02
0x140006dea  mov     rcx, [rcx+18h]
0x140006dee  lea     r8, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140006df5  mov     edx, 0Ch
0x140006dfa  mov     r9d, edi
0x140006dfd  call    WPP_SF_d
0x140006e02  mov     eax, edi
0x140006e04  add     rsp, 58h
0x140006e08  pop     r14
0x140006e0a  pop     r13
0x140006e0c  pop     rdi
0x140006e0d  pop     rsi
0x140006e0e  pop     rbp
0x140006e0f  pop     rbx
0x140006e10  retn
```
