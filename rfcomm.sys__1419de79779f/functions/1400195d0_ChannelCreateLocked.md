# ChannelCreateLocked

- ea: `0x1400195d0`
- end: `0x1400197e6`
- name: `ChannelCreateLocked`
- size: `534`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001190c`
- `0x1400121d4`
- `0x140012590`
- `0x140018e9c`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x140004a68`
- `0x1400195d0`
- `0x14001e74c`
- `0x14001e8f4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140019666`
- `ntoskrnl!ExAllocatePool2` at `0x140019666`

## string_xrefs

- `0x14001967e`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`

## pseudocode

```c
__int64 __fastcall ChannelCreateLocked(__int64 a1, char a2, char a3)
{
  __int64 v6; // rbx
  __int64 Pool2; // rax
  int v8; // eax
  __int64 *v9; // rax
  __int64 v10; // rdi

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      10,
      (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids,
      a2);
  if ( *(int *)(a1 + 48) < 5 )
  {
    Pool2 = ExAllocatePool2(64, 272, 1212376658);
    v6 = Pool2;
    if ( Pool2 )
    {
      RefObj_InitEx(
        Pool2 + 24,
        (unsigned int)ChannelFree,
        1414090313,
        52,
        (__int64)"onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
      *(_QWORD *)(v6 + 64) = 0;
      *(_QWORD *)(v6 + 96) = v6 + 88;
      *(_QWORD *)(v6 + 88) = v6 + 88;
      *(_DWORD *)(v6 + 16) = 1312901187;
      *(_QWORD *)(v6 + 80) = v6 + 72;
      *(_QWORD *)(v6 + 72) = v6 + 72;
      *(_QWORD *)(v6 + 112) = v6 + 104;
      *(_QWORD *)(v6 + 104) = v6 + 104;
      *(_QWORD *)(v6 + 128) = v6 + 120;
      *(_QWORD *)(v6 + 120) = v6 + 120;
      *(_QWORD *)(v6 + 160) = v6 + 152;
      *(_QWORD *)(v6 + 152) = v6 + 152;
      *(_QWORD *)(v6 + 176) = v6 + 168;
      *(_QWORD *)(v6 + 168) = v6 + 168;
      *(_QWORD *)(v6 + 248) = v6 + 240;
      *(_QWORD *)(v6 + 240) = v6 + 240;
      *(_QWORD *)(v6 + 264) = v6 + 256;
      *(_QWORD *)(v6 + 256) = v6 + 256;
      v8 = 1 << a2;
      *(_DWORD *)(v6 + 48) = 0;
      *(_QWORD *)(v6 + 56) = a1;
      *(_BYTE *)(v6 + 186) = 0;
      if ( a3 )
      {
        *(_BYTE *)(v6 + 185) = 1;
        *(_DWORD *)(a1 + 256) |= v8;
      }
      else
      {
        *(_BYTE *)(v6 + 185) = 0;
        *(_DWORD *)(a1 + 260) |= v8;
      }
      *(_BYTE *)(v6 + 184) = (2 * (a2 & 0x1F)) | (*(_BYTE *)(a1 + 272) ^ a3) & 1;
      RefObj_AddRefEx(a1 + 24, 1312901187, 92, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
      v9 = *(__int64 **)(a1 + 88);
      v10 = a1 + 80;
      if ( *v9 != v10 )
        __fastfail(3u);
      *(_QWORD *)v6 = v10;
      *(_QWORD *)(v6 + 8) = v9;
      *v9 = v6;
      *(_QWORD *)(v10 + 8) = v6;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        11,
        (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids);
    v6 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      12,
      (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids,
      v6);
  return v6;
}

```

## disassembly

```asm
0x1400195d0  push    rbx
0x1400195d2  push    rbp
0x1400195d3  push    rsi
0x1400195d4  push    rdi
0x1400195d5  push    r12
0x1400195d7  push    r13
0x1400195d9  push    r14
0x1400195db  sub     rsp, 30h
0x1400195df  mov     bpl, r8b
0x1400195e2  mov     esi, edx
0x1400195e4  mov     rdi, rcx
0x1400195e7  lea     r14, WPP_RECORDER_INITIALIZED
0x1400195ee  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400195f5  lea     r12, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x1400195fc  jz      short loc_140019621
0x1400195fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140019605  mov     r9d, 0Ah
0x14001960b  mov     dword ptr [rsp+68h+var_40], edx
0x14001960f  mov     [rsp+68h+var_48], r12
0x140019614  mov     rcx, [rcx+40h]
0x140019618  lea     r8d, [r9-7]
0x14001961c  call    WPP_RECORDER_SF_d
0x140019621  cmp     dword ptr [rdi+30h], 5
0x140019625  jl      short loc_140019656
0x140019627  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001962e  jz      short loc_14001964F
0x140019630  mov     rcx, cs:WPP_GLOBAL_Control
0x140019637  mov     r9d, 0Bh
0x14001963d  mov     [rsp+68h+var_48], r12
0x140019642  mov     rcx, [rcx+40h]
0x140019646  lea     r8d, [r9-0Ah]
0x14001964a  call    WPP_RECORDER_SF_
0x14001964f  xor     ebx, ebx
0x140019651  jmp     loc_1400197A6
0x140019656  mov     edx, 110h
0x14001965b  mov     ecx, 40h ; '@'
0x140019660  mov     r8d, 48436652h
0x140019666  call    cs:__imp_ExAllocatePool2
0x14001966d  nop     dword ptr [rax+rax+00h]
0x140019672  mov     rbx, rax
0x140019675  test    rax, rax
0x140019678  jz      loc_1400197A6
0x14001967e  lea     r13, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140019685  mov     r9d, 34h ; '4'
0x14001968b  lea     rcx, [rax+18h]
0x14001968f  mov     [rsp+68h+var_48], r13
0x140019694  mov     r8d, 54494E49h
0x14001969a  lea     rdx, ChannelFree
0x1400196a1  call    RefObj_InitEx
0x1400196a6  lea     rax, [rbx+58h]
0x1400196aa  mov     qword ptr [rbx+40h], 0
0x1400196b2  mov     [rax+8], rax
0x1400196b6  mov     ecx, esi
0x1400196b8  mov     [rax], rax
0x1400196bb  mov     edx, 4E414843h
0x1400196c0  lea     rax, [rbx+48h]
0x1400196c4  mov     [rbx+10h], edx
0x1400196c7  mov     [rax+8], rax
0x1400196cb  mov     [rax], rax
0x1400196ce  lea     rax, [rbx+68h]
0x1400196d2  mov     [rax+8], rax
0x1400196d6  mov     [rax], rax
0x1400196d9  lea     rax, [rbx+78h]
0x1400196dd  mov     [rax+8], rax
0x1400196e1  mov     [rax], rax
0x1400196e4  lea     rax, [rbx+98h]
0x1400196eb  mov     [rax+8], rax
0x1400196ef  mov     [rax], rax
0x1400196f2  lea     rax, [rbx+0A8h]
0x1400196f9  mov     [rax+8], rax
0x1400196fd  mov     [rax], rax
0x140019700  lea     rax, [rbx+0F0h]
0x140019707  mov     [rax+8], rax
0x14001970b  mov     [rax], rax
0x14001970e  lea     rax, [rbx+100h]
0x140019715  mov     [rax+8], rax
0x140019719  mov     [rax], rax
0x14001971c  mov     eax, 1
0x140019721  shl     eax, cl
0x140019723  mov     dword ptr [rbx+30h], 0
0x14001972a  mov     [rbx+38h], rdi
0x14001972e  mov     byte ptr [rbx+0BAh], 0
0x140019735  test    bpl, bpl
0x140019738  jz      short loc_140019749
0x14001973a  mov     byte ptr [rbx+0B9h], 1
0x140019741  or      [rdi+100h], eax
0x140019747  jmp     short loc_140019756
0x140019749  mov     byte ptr [rbx+0B9h], 0
0x140019750  or      [rdi+104h], eax
0x140019756  xor     bpl, [rdi+110h]
0x14001975d  lea     rcx, [rdi+18h]
0x140019761  and     sil, 1Fh
0x140019765  and     bpl, 1
0x140019769  add     sil, sil
0x14001976c  mov     r9, r13
0x14001976f  or      bpl, sil
0x140019772  mov     r8d, 5Ch ; '\'
0x140019778  mov     [rbx+0B8h], bpl
0x14001977f  call    RefObj_AddRefEx
0x140019784  mov     rax, [rdi+58h]
0x140019788  add     rdi, 50h ; 'P'
0x14001978c  cmp     [rax], rdi
0x14001978f  jz      short loc_140019798
0x140019791  mov     ecx, 3
0x140019796  int     29h; Win8: RtlFailFast(ecx)
0x140019798  mov     [rbx], rdi
0x14001979b  mov     [rbx+8], rax
0x14001979f  mov     [rax], rbx
0x1400197a2  mov     [rdi+8], rbx
0x1400197a6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400197ad  jz      short loc_1400197D3
0x1400197af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400197b6  mov     r9d, 0Ch
0x1400197bc  mov     [rsp+68h+var_40], rbx
0x1400197c1  mov     [rsp+68h+var_48], r12
0x1400197c6  mov     rcx, [rcx+40h]
0x1400197ca  lea     r8d, [r9-9]
0x1400197ce  call    WPP_RECORDER_SF_q
0x1400197d3  mov     rax, rbx
0x1400197d6  add     rsp, 30h
0x1400197da  pop     r14
0x1400197dc  pop     r13
0x1400197de  pop     r12
0x1400197e0  pop     rdi
0x1400197e1  pop     rsi
0x1400197e2  pop     rbp
0x1400197e3  pop     rbx
0x1400197e4  retn
```
