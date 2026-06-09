# NdisWanAllocateProtocolCB

- ea: `0x140035ad8`
- end: `0x140035e64`
- name: `NdisWanAllocateProtocolCB`
- size: `908`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140026c80`

## callees

- `0x14000176c`
- `0x140005728`
- `0x14000a280`
- `0x14000a290`
- `0x14000a2c0`
- `0x140010f7c`
- `0x1400161f0`
- `0x140016400`
- `0x140016700`
- `0x140035ad8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140035c03`
- `ntoskrnl!KeInitializeEvent` at `0x140035c03`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140035c71`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140035c71`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035cf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035e45`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035cf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035e45`
- `ntoskrnl!ExAllocatePool2` at `0x140035b8d`
- `ntoskrnl!ExAllocatePool2` at `0x140035d2d`
- `ntoskrnl!ExAllocatePool2` at `0x140035b8d`
- `ntoskrnl!ExAllocatePool2` at `0x140035d2d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140035d0c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140035d0c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140035b17`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140035b17`

## pseudocode

```c
char *__fastcall NdisWanAllocateProtocolCB(__int64 a1)
{
  char *v2; // rax
  char *v3; // rdi
  unsigned __int16 v4; // bp
  unsigned __int16 v5; // si
  unsigned __int16 v6; // ax
  void *v7; // rax
  __int64 (__fastcall *v8)(); // rax
  __int64 v9; // rbx
  __int64 Pool2; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // rbp
  void *v14; // rcx
  __int128 v15; // [rsp+20h] [rbp-258h] BYREF
  int v16; // [rsp+30h] [rbp-248h]
  _WORD v17[264]; // [rsp+40h] [rbp-238h] BYREF

  v15 = 0;
  v16 = 0;
  v2 = (char *)ExAllocateFromNPagedLookasideList(&LinkProtoCBList);
  v3 = v2;
  if ( !v2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids);
    }
    return 0;
  }
  memset(v2, 0, 0x158u);
  *((_DWORD *)v3 + 4) = 1953460816;
  if ( *(_DWORD *)(a1 + 1044) )
  {
    Pool2 = ExAllocatePool2(64, *(unsigned int *)(a1 + 1044), 1517183319);
    if ( !Pool2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          27,
          WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids,
          *(unsigned int *)(a1 + 1044));
      }
      goto LABEL_19;
    }
    *((_QWORD *)v3 + 42) = Pool2;
  }
  v4 = *(_WORD *)(a1 + 10);
  v5 = 512;
  if ( v4 )
  {
    memset(v17, 0, 0x202u);
    if ( v4 > 0x200u )
      v4 = 512;
    memmove(v17, (const void *)(a1 + 12), v4);
    v13 = v4 & 0xFFFE;
    if ( v13 >= 0x202 )
      _report_rangecheckfailure(v12);
    *(_WORD *)((char *)v17 + v13) = 0;
    NdisWanStringToNdisString((PUNICODE_STRING)v3 + 16);
  }
  v6 = *(_WORD *)(a1 + 524);
  if ( v6 )
  {
    if ( v6 <= 0x200u )
      v5 = *(_WORD *)(a1 + 524);
    v7 = (void *)ExAllocatePool2(64, v5, 1299079511);
    *((_QWORD *)v3 + 35) = v7;
    if ( v7 )
    {
      *((_WORD *)v3 + 137) = v5;
      *((_WORD *)v3 + 136) = v5;
      memmove(v7, (const void *)(a1 + 526), v5);
    }
  }
  *((_DWORD *)v3 + 82) = *(_DWORD *)(a1 + 1044);
  if ( *(_DWORD *)(a1 + 1044) )
    memmove(*((void **)v3 + 42), (const void *)(a1 + 1048), *(unsigned int *)(a1 + 1044));
  *((_WORD *)v3 + 106) = *(_WORD *)(a1 + 8);
  LOWORD(v15) = *(_WORD *)(a1 + 8);
  if ( (unsigned __int8)GetProtocolInfo(&v15) != 1 )
  {
    if ( *((_WORD *)v3 + 128) )
      NdisWanFreeNdisString();
    v14 = (void *)*((_QWORD *)v3 + 42);
    if ( v14 )
      ExFreePoolWithTag(v14, 0);
    if ( *((_WORD *)v3 + 136) )
      ExFreePoolWithTag(*((PVOID *)v3 + 35), 0);
LABEL_19:
    ExFreeToNPagedLookasideList(&LinkProtoCBList, v3);
    return 0;
  }
  *((_QWORD *)v3 + 10) = v3 + 72;
  *((_QWORD *)v3 + 9) = v3 + 72;
  KeInitializeEvent((PRKEVENT)(v3 + 304), SynchronizationEvent, 0);
  *((_WORD *)v3 + 107) = WORD1(v15);
  *((_QWORD *)v3 + 27) = *((_QWORD *)&v15 + 1);
  *(_QWORD *)(v3 + 20) = 2;
  *((_QWORD *)v3 + 4) = DoDerefProtocolCBWork;
  _InterlockedIncrement((volatile signed __int32 *)v3 + 6);
  v8 = 0;
  if ( *(_WORD *)(a1 + 8) == 2048 )
    v8 = IpIsDataFrame;
  *((_QWORD *)v3 + 29) = v8;
  v9 = MEMORY[0xFFFFF78000000320];
  *((_QWORD *)v3 + 28) = v9 * KeQueryTimeIncrement();
  return v3;
}

```

## disassembly

```asm
0x140035ad8  mov     [rsp+arg_8], rbx
0x140035add  mov     [rsp+arg_10], rbp
0x140035ae2  push    rsi
0x140035ae3  push    rdi
0x140035ae4  push    r14
0x140035ae6  sub     rsp, 260h
0x140035aed  mov     rax, cs:__security_cookie
0x140035af4  xor     rax, rsp
0x140035af7  mov     [rsp+278h+var_28], rax
0x140035aff  mov     rbx, rcx
0x140035b02  xorps   xmm0, xmm0
0x140035b05  xor     eax, eax
0x140035b07  lea     rcx, LinkProtoCBList; Lookaside
0x140035b0e  movups  [rsp+278h+var_258], xmm0
0x140035b13  mov     [rsp+278h+var_248], eax
0x140035b17  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140035b1e  nop     dword ptr [rax+rax+00h]
0x140035b23  xor     r14d, r14d
0x140035b26  mov     rdi, rax
0x140035b29  test    rax, rax
0x140035b2c  jz      loc_140035CB6
0x140035b32  xor     edx, edx; Val
0x140035b34  mov     r8d, 158h; Size
0x140035b3a  mov     rcx, rax; void *
0x140035b3d  call    memset
0x140035b42  mov     dword ptr [rdi+10h], 746F7250h
0x140035b49  mov     eax, [rbx+414h]
0x140035b4f  test    eax, eax
0x140035b51  jnz     loc_140035D1F
0x140035b57  movzx   ebp, word ptr [rbx+0Ah]
0x140035b5b  mov     esi, 200h
0x140035b60  test    bp, bp
0x140035b63  jnz     loc_140035D88
0x140035b69  movzx   eax, word ptr [rbx+20Ch]
0x140035b70  test    ax, ax
0x140035b73  jz      short loc_140035BA9
0x140035b75  cmp     ax, si
0x140035b78  ja      short loc_140035B7D
0x140035b7a  movzx   esi, ax
0x140035b7d  movzx   ebp, si
0x140035b80  mov     r8d, 4D6E6157h
0x140035b86  mov     edx, ebp
0x140035b88  mov     ecx, 40h ; '@'
0x140035b8d  call    cs:__imp_ExAllocatePool2
0x140035b94  nop     dword ptr [rax+rax+00h]
0x140035b99  mov     [rdi+118h], rax
0x140035ba0  test    rax, rax
0x140035ba3  jnz     loc_140035DE5
0x140035ba9  mov     eax, [rbx+414h]
0x140035baf  mov     [rdi+148h], eax
0x140035bb5  mov     eax, [rbx+414h]
0x140035bbb  test    eax, eax
0x140035bbd  jnz     loc_140035E0A
0x140035bc3  movzx   eax, word ptr [rbx+8]
0x140035bc7  lea     rcx, [rsp+278h+var_258]
0x140035bcc  mov     [rdi+0D4h], ax
0x140035bd3  movzx   eax, word ptr [rbx+8]
0x140035bd7  mov     word ptr [rsp+278h+var_258], ax
0x140035bdc  call    GetProtocolInfo
0x140035be1  mov     edx, 1; Type
0x140035be6  cmp     al, dl
0x140035be8  jnz     loc_140035E25
0x140035bee  lea     rax, [rdi+48h]
0x140035bf2  xor     r8d, r8d; State
0x140035bf5  lea     rcx, [rdi+130h]; Event
0x140035bfc  mov     [rax+8], rax
0x140035c00  mov     [rax], rax
0x140035c03  call    cs:__imp_KeInitializeEvent
0x140035c0a  nop     dword ptr [rax+rax+00h]
0x140035c0f  movzx   eax, word ptr [rsp+278h+var_258+2]
0x140035c14  mov     [rdi+0D6h], ax
0x140035c1b  mov     eax, dword ptr [rsp+278h+var_258+8]
0x140035c1f  mov     [rdi+0D8h], eax
0x140035c25  mov     eax, dword ptr [rsp+278h+var_258+0Ch]
0x140035c29  mov     [rdi+0DCh], eax
0x140035c2f  lea     rax, DoDerefProtocolCBWork
0x140035c36  mov     qword ptr [rdi+14h], 2
0x140035c3e  mov     [rdi+20h], rax
0x140035c42  lock inc dword ptr [rdi+18h]
0x140035c46  mov     edx, 800h
0x140035c4b  lea     rcx, IpIsDataFrame
0x140035c52  cmp     [rbx+8], dx
0x140035c56  mov     rax, r14
0x140035c59  mov     rbx, 0FFFFF78000000320h
0x140035c63  cmovz   rax, rcx
0x140035c67  mov     [rdi+0E8h], rax
0x140035c6e  mov     rbx, [rbx]
0x140035c71  call    cs:__imp_KeQueryTimeIncrement
0x140035c78  nop     dword ptr [rax+rax+00h]
0x140035c7d  mov     eax, eax
0x140035c7f  imul    rax, rbx
0x140035c83  mov     [rdi+0E0h], rax
0x140035c8a  mov     rax, rdi
0x140035c8d  mov     rcx, [rsp+278h+var_28]
0x140035c95  xor     rcx, rsp; StackCookie
0x140035c98  call    __security_check_cookie
0x140035c9d  lea     r11, [rsp+278h+var_18]
0x140035ca5  mov     rbx, [r11+28h]
0x140035ca9  mov     rbp, [r11+30h]
0x140035cad  mov     rsp, r11
0x140035cb0  pop     r14
0x140035cb2  pop     rdi
0x140035cb3  pop     rsi
0x140035cb4  retn
0x140035cb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140035cbd  lea     rax, WPP_GLOBAL_Control
0x140035cc4  cmp     rcx, rax
0x140035cc7  jz      short loc_140035D18
0x140035cc9  mov     eax, [rcx+2Ch]
0x140035ccc  test    al, 40h
0x140035cce  jz      short loc_140035D18
0x140035cd0  cmp     byte ptr [rcx+29h], 2
0x140035cd4  jb      short loc_140035D18
0x140035cd6  mov     rcx, [rcx+18h]
0x140035cda  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x140035ce1  mov     edx, 1Ah
0x140035ce6  call    WPP_SF_
0x140035ceb  jmp     short loc_140035D18
0x140035ced  mov     rcx, [rdi+118h]; P
0x140035cf4  xor     edx, edx; Tag
0x140035cf6  call    cs:__imp_ExFreePoolWithTag
0x140035cfd  nop     dword ptr [rax+rax+00h]
0x140035d02  mov     rdx, rdi; Entry
0x140035d05  lea     rcx, LinkProtoCBList; Lookaside
0x140035d0c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140035d13  nop     dword ptr [rax+rax+00h]
0x140035d18  xor     eax, eax
0x140035d1a  jmp     loc_140035C8D
0x140035d1f  mov     rdx, rax
0x140035d22  mov     ecx, 40h ; '@'
0x140035d27  mov     r8d, 5A6E6157h
0x140035d2d  call    cs:__imp_ExAllocatePool2
0x140035d34  nop     dword ptr [rax+rax+00h]
0x140035d39  test    rax, rax
0x140035d3c  jnz     short loc_140035D7C
0x140035d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140035d45  lea     rax, WPP_GLOBAL_Control
0x140035d4c  cmp     rcx, rax
0x140035d4f  jz      short loc_140035D02
0x140035d51  mov     eax, [rcx+2Ch]
0x140035d54  test    al, 40h
0x140035d56  jz      short loc_140035D02
0x140035d58  cmp     byte ptr [rcx+29h], 2
0x140035d5c  jb      short loc_140035D02
0x140035d5e  mov     r9d, [rbx+414h]
0x140035d65  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x140035d6c  mov     rcx, [rcx+18h]
0x140035d70  mov     edx, 1Bh
0x140035d75  call    WPP_SF_d
0x140035d7a  jmp     short loc_140035D02
0x140035d7c  mov     [rdi+150h], rax
0x140035d83  jmp     loc_140035B57
0x140035d88  xor     edx, edx; Val
0x140035d8a  lea     rcx, [rsp+278h+var_238]; void *
0x140035d8f  mov     r8d, 202h; Size
0x140035d95  call    memset
0x140035d9a  cmp     bp, si
0x140035d9d  jbe     short loc_140035DA2
0x140035d9f  movzx   ebp, si
0x140035da2  movzx   ebp, bp
0x140035da5  lea     rdx, [rbx+0Ch]; Src
0x140035da9  mov     r8d, ebp; Size
0x140035dac  lea     rcx, [rsp+278h+var_238]; void *
0x140035db1  call    memmove
0x140035db6  and     rbp, 0FFFFFFFFFFFFFFFEh
0x140035dba  cmp     rbp, 202h
0x140035dc1  jnb     short loc_140035DDF
0x140035dc3  lea     rcx, [rdi+100h]; DestinationString
0x140035dca  mov     [rsp+rbp+278h+var_238], r14w
0x140035dd0  lea     rdx, [rsp+278h+var_238]
0x140035dd5  call    NdisWanStringToNdisString
0x140035dda  jmp     loc_140035B69
0x140035ddf  call    __report_rangecheckfailure
0x140035de5  lea     rdx, [rbx+20Eh]; Src
0x140035dec  mov     [rdi+112h], si
0x140035df3  mov     r8, rbp; Size
0x140035df6  mov     [rdi+110h], si
0x140035dfd  mov     rcx, rax; void *
0x140035e00  call    memmove
0x140035e05  jmp     loc_140035BA9
0x140035e0a  mov     rcx, [rdi+150h]; void *
0x140035e11  lea     rdx, [rbx+418h]; Src
0x140035e18  mov     r8, rax; Size
0x140035e1b  call    memmove
0x140035e20  jmp     loc_140035BC3
0x140035e25  lea     rcx, [rdi+100h]
0x140035e2c  cmp     [rcx], r14w
0x140035e30  jz      short loc_140035E37
0x140035e32  call    NdisWanFreeNdisString
0x140035e37  mov     rcx, [rdi+150h]; P
0x140035e3e  test    rcx, rcx
0x140035e41  jz      short loc_140035E51
0x140035e43  xor     edx, edx; Tag
0x140035e45  call    cs:__imp_ExFreePoolWithTag
0x140035e4c  nop     dword ptr [rax+rax+00h]
0x140035e51  cmp     [rdi+110h], r14w
0x140035e59  jz      loc_140035D02
0x140035e5f  jmp     loc_140035CED
```
