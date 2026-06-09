# ACOpenQueue

- ea: `0x140007460`
- end: `0x1400075d0`
- name: `ACOpenQueue`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140001128`
- `0x140001c34`
- `0x140003d84`
- `0x140007460`
- `0x14001ac74`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400074d4`
- `ntoskrnl!ProbeForRead` at `0x1400074d4`

## pseudocode

```c
__int64 __fastcall ACOpenQueue(__int64 a1, __int64 a2, __int64 a3, __int128 *a4)
{
  __int64 v8; // r9
  __int128 v9; // xmm6
  _QWORD *v10; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 121, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a3);
  }
  v8 = *(_QWORD *)(a3 + 24);
  if ( v8 || **(_QWORD **)(a3 + 32) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 122, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v8);
    }
    return 3221225488LL;
  }
  else
  {
    ProbeForRead(a4, 0x10u, 1u);
    v9 = *a4;
    v10 = operator new(0x30u, 0x40u, 0x5141514Du, LowPoolPriority);
    if ( v10 )
    {
      v10[2] = a2;
      v10[3] = a3;
      *((_OWORD *)v10 + 2) = v9;
      return CQMInterface::HoldOpenQueueRequest(
               (CQMInterface *)(*(_QWORD *)(a1 + 64) + 72LL),
               (struct CACOpenQueueRequest *)v10);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 124, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, 0);
      }
      return 3221225626LL;
    }
  }
}

```

## disassembly

```asm
0x140007460  push    rbx
0x140007462  push    rsi
0x140007463  push    rdi
0x140007464  push    r14
0x140007466  push    r15
0x140007468  sub     rsp, 40h
0x14000746c  movaps  [rsp+68h+var_38], xmm6
0x140007471  mov     rdi, r9
0x140007474  mov     rbx, r8
0x140007477  mov     r14, rdx
0x14000747a  mov     rsi, rcx
0x14000747d  lea     r15, WPP_GLOBAL_Control
0x140007484  mov     rcx, cs:WPP_GLOBAL_Control
0x14000748b  cmp     rcx, r15
0x14000748e  jz      short loc_1400074AF
0x140007490  mov     eax, [rcx+6Ch]
0x140007493  test    al, 4
0x140007495  jz      short loc_1400074AF
0x140007497  mov     edx, 79h ; 'y'
0x14000749c  mov     r9, rbx
0x14000749f  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400074a6  mov     rcx, [rcx+58h]
0x1400074aa  call    WPP_SF_q
0x1400074af  mov     r9, [rbx+18h]
0x1400074b3  test    r9, r9
0x1400074b6  jnz     loc_140007591
0x1400074bc  mov     rax, [rbx+20h]
0x1400074c0  cmp     [rax], r9
0x1400074c3  jnz     loc_140007591
0x1400074c9  lea     edx, [r9+10h]; Length
0x1400074cd  lea     r8d, [r9+1]; Alignment
0x1400074d1  mov     rcx, rdi; Address
0x1400074d4  call    cs:__imp_ProbeForRead
0x1400074db  nop     dword ptr [rax+rax+00h]
0x1400074e0  movups  xmm6, xmmword ptr [rdi]
0x1400074e3  movaps  [rsp+68h+var_48], xmm6
0x1400074e8  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x1400074eb  lea     edx, [r9+40h]; unsigned __int64
0x1400074ef  mov     r8d, 5141514Dh; unsigned int
0x1400074f5  lea     ecx, [rdx-10h]; unsigned __int64
0x1400074f8  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x1400074fd  test    rax, rax
0x140007500  jz      short loc_14000750F
0x140007502  mov     [rax+10h], r14
0x140007506  mov     [rax+18h], rbx
0x14000750a  movdqu  xmmword ptr [rax+20h], xmm6
0x14000750f  test    rax, rax
0x140007512  jnz     short loc_140007546
0x140007514  mov     rcx, cs:WPP_GLOBAL_Control
0x14000751b  cmp     rcx, r15
0x14000751e  jz      short loc_14000753F
0x140007520  mov     eax, [rcx+6Ch]
0x140007523  test    al, 1
0x140007525  jz      short loc_14000753F
0x140007527  mov     edx, 7Ch ; '|'
0x14000752c  xor     r9d, r9d
0x14000752f  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140007536  mov     rcx, [rcx+58h]
0x14000753a  call    WPP_SF_q
0x14000753f  mov     eax, 0C000009Ah
0x140007544  jmp     short loc_1400075BE
0x140007546  mov     rcx, [rsi+40h]
0x14000754a  add     rcx, 48h ; 'H'; this
0x14000754e  mov     rdx, rax; struct CACOpenQueueRequest *
0x140007551  call    ?HoldOpenQueueRequest@CQMInterface@@QEAAJPEAVCACOpenQueueRequest@@@Z; CQMInterface::HoldOpenQueueRequest(CACOpenQueueRequest *)
0x140007556  jmp     short loc_1400075BE
0x140007558  mov     ebx, eax
0x14000755a  lea     rax, WPP_GLOBAL_Control
0x140007561  mov     rcx, cs:WPP_GLOBAL_Control
0x140007568  cmp     rcx, rax
0x14000756b  jz      short loc_14000758D
0x14000756d  mov     edx, [rcx+6Ch]
0x140007570  test    dl, 1
0x140007573  jz      short loc_14000758D
0x140007575  mov     edx, 7Bh ; '{'
0x14000757a  mov     r9d, ebx
0x14000757d  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140007584  mov     rcx, [rcx+58h]
0x140007588  call    WPP_SF_d
0x14000758d  mov     eax, ebx
0x14000758f  jmp     short loc_1400075BE
0x140007591  mov     rcx, cs:WPP_GLOBAL_Control
0x140007598  cmp     rcx, r15
0x14000759b  jz      short loc_1400075B9
0x14000759d  mov     eax, [rcx+6Ch]
0x1400075a0  test    al, 1
0x1400075a2  jz      short loc_1400075B9
0x1400075a4  mov     edx, 7Ah ; 'z'
0x1400075a9  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400075b0  mov     rcx, [rcx+58h]
0x1400075b4  call    WPP_SF_q
0x1400075b9  mov     eax, 0C0000010h
0x1400075be  movaps  xmm6, [rsp+68h+var_38]
0x1400075c3  add     rsp, 40h
0x1400075c7  pop     r15
0x1400075c9  pop     r14
0x1400075cb  pop     rdi
0x1400075cc  pop     rsi
0x1400075cd  pop     rbx
0x1400075ce  retn
```
