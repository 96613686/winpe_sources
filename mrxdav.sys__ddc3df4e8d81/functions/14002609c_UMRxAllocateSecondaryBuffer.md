# UMRxAllocateSecondaryBuffer

- ea: `0x14002609c`
- end: `0x1400262be`
- name: `UMRxAllocateSecondaryBuffer`
- size: `546`
- prototype: `PVOID __fastcall(__int64, ULONG_PTR)`
- caller_count: `12`
- callee_count: `6`
- tags: ``

## callers

- `0x140004b00`
- `0x140010620`
- `0x1400145d0`
- `0x140014e00`
- `0x1400199a0`
- `0x14001a480`
- `0x14001b360`
- `0x14001bc30`
- `0x14001dec0`
- `0x140020090`
- `0x140020660`
- `0x140020e80`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140001838`
- `0x14000650c`
- `0x14002609c`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400260e1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002611d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400261bc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026235`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002627e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400260e1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002611d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400261bc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026235`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002627e`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x140026178`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x140026178`

## pseudocode

```c
PVOID __fastcall UMRxAllocateSecondaryBuffer(__int64 a1, ULONG_PTR a2)
{
  __int64 v3; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v5; // rbx
  HANDLE v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  PVOID v9; // rax
  int v10; // ebx
  __int64 v11; // rdi
  HANDLE v12; // rax
  __int64 v13; // rbx
  HANDLE v14; // rax
  __int64 v16; // rbx
  HANDLE v17; // rax
  PVOID BaseAddress; // [rsp+50h] [rbp+20h] BYREF
  ULONG_PTR RegionSize; // [rsp+58h] [rbp+28h] BYREF

  RegionSize = a2;
  BaseAddress = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v3 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v3, 107, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v5 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v6 = PsGetCurrentThreadId();
      WPP_SF_qql(v5, v7, v8, v6, a1, RegionSize);
    }
  }
  if ( !RegionSize )
    RegionSize = 4096;
  if ( *(_DWORD *)(a1 + 224) >= 8u )
    return 0;
  if ( ZwAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &RegionSize, 0x1000u, 4u) >= 0 )
  {
    v9 = BaseAddress;
  }
  else
  {
    v9 = 0;
    BaseAddress = 0;
  }
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
    {
      v16 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v17 = PsGetCurrentThreadId();
      WPP_SF_qD(v16, 110, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v17, RegionSize);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0 )
  {
    v10 = *(_DWORD *)(a1 + 224);
    v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v12 = PsGetCurrentThreadId();
    WPP_SF_qqD(v11, 109, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v12, BaseAddress, v10);
  }
  *(_QWORD *)(a1 + 16 * (*(unsigned int *)(a1 + 224) + 15LL)) = RegionSize;
  *(_QWORD *)(a1 + 16LL * (unsigned int)(*(_DWORD *)(a1 + 224))++ + 232) = BaseAddress;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
  {
    v13 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v14 = PsGetCurrentThreadId();
    WPP_SF_qq(v13, 111, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v14, BaseAddress);
  }
  return BaseAddress;
}

```

## disassembly

```asm
0x14002609c  mov     [rsp-18h+arg_10], rbx
0x1400260a1  mov     [rsp-18h+arg_18], rsi
0x1400260a6  mov     [rsp-18h+RegionSize], rdx
0x1400260ab  push    rbp
0x1400260ac  push    rdi
0x1400260ad  push    r14
0x1400260af  mov     rbp, rsp
0x1400260b2  sub     rsp, 30h
0x1400260b6  mov     rsi, rcx
0x1400260b9  mov     [rbp+BaseAddress], 0
0x1400260c1  mov     rbx, cs:WPP_GLOBAL_Control
0x1400260c8  lea     r14, WPP_GLOBAL_Control
0x1400260cf  cmp     rbx, r14
0x1400260d2  jz      short loc_140026140
0x1400260d4  test    dword ptr [rbx+2Ch], 800h
0x1400260db  jz      short loc_140026104
0x1400260dd  mov     rbx, [rbx+18h]
0x1400260e1  call    cs:__imp_PsGetCurrentThreadId
0x1400260e8  nop     dword ptr [rax+rax+00h]
0x1400260ed  mov     edx, 6Bh ; 'k'
0x1400260f2  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400260f9  mov     r9, rax
0x1400260fc  mov     rcx, rbx
0x1400260ff  call    WPP_SF_q
0x140026104  mov     rbx, cs:WPP_GLOBAL_Control
0x14002610b  cmp     rbx, r14
0x14002610e  jz      short loc_140026140
0x140026110  test    dword ptr [rbx+2Ch], 200h
0x140026117  jz      short loc_140026140
0x140026119  mov     rbx, [rbx+18h]
0x14002611d  call    cs:__imp_PsGetCurrentThreadId
0x140026124  nop     dword ptr [rax+rax+00h]
0x140026129  mov     r9, rax
0x14002612c  mov     rcx, rbx
0x14002612f  mov     eax, dword ptr [rbp+RegionSize]
0x140026132  mov     [rsp+30h+Protect], eax
0x140026136  mov     qword ptr [rsp+30h+AllocationType], rsi
0x14002613b  call    WPP_SF_qql
0x140026140  cmp     [rbp+RegionSize], 0
0x140026145  mov     eax, 1000h
0x14002614a  jnz     short loc_140026150
0x14002614c  mov     [rbp+RegionSize], rax
0x140026150  cmp     dword ptr [rsi+0E0h], 8
0x140026157  jnb     loc_1400262A8
0x14002615d  mov     [rsp+30h+Protect], 4; Protect
0x140026165  lea     r9, [rbp+RegionSize]; RegionSize
0x140026169  xor     r8d, r8d; ZeroBits
0x14002616c  mov     [rsp+30h+AllocationType], eax; AllocationType
0x140026170  lea     rdx, [rbp+BaseAddress]; BaseAddress
0x140026174  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140026178  call    cs:__imp_ZwAllocateVirtualMemory
0x14002617f  nop     dword ptr [rax+rax+00h]
0x140026184  test    eax, eax
0x140026186  jns     short loc_140026190
0x140026188  xor     eax, eax
0x14002618a  mov     [rbp+BaseAddress], rax
0x14002618e  jmp     short loc_140026194
0x140026190  mov     rax, [rbp+BaseAddress]
0x140026194  test    rax, rax
0x140026197  jz      loc_140026267
0x14002619d  mov     rdi, cs:WPP_GLOBAL_Control
0x1400261a4  cmp     rdi, r14
0x1400261a7  jz      short loc_1400261EC
0x1400261a9  test    dword ptr [rdi+2Ch], 400h
0x1400261b0  jz      short loc_1400261EC
0x1400261b2  mov     ebx, [rsi+0E0h]
0x1400261b8  mov     rdi, [rdi+18h]
0x1400261bc  call    cs:__imp_PsGetCurrentThreadId
0x1400261c3  nop     dword ptr [rax+rax+00h]
0x1400261c8  mov     edx, 6Dh ; 'm'
0x1400261cd  mov     [rsp+30h+Protect], ebx
0x1400261d1  mov     r9, rax
0x1400261d4  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400261db  mov     rax, [rbp+BaseAddress]
0x1400261df  mov     rcx, rdi
0x1400261e2  mov     qword ptr [rsp+30h+AllocationType], rax
0x1400261e7  call    WPP_SF_qqD
0x1400261ec  mov     ecx, [rsi+0E0h]
0x1400261f2  mov     rax, [rbp+RegionSize]
0x1400261f6  add     rcx, 0Fh
0x1400261fa  add     rcx, rcx
0x1400261fd  mov     [rsi+rcx*8], rax
0x140026201  mov     ecx, [rsi+0E0h]
0x140026207  mov     rax, [rbp+BaseAddress]
0x14002620b  add     rcx, rcx
0x14002620e  mov     [rsi+rcx*8+0E8h], rax
0x140026216  inc     dword ptr [rsi+0E0h]
0x14002621c  mov     rbx, cs:WPP_GLOBAL_Control
0x140026223  cmp     rbx, r14
0x140026226  jz      short loc_140026261
0x140026228  test    dword ptr [rbx+2Ch], 800h
0x14002622f  jz      short loc_140026261
0x140026231  mov     rbx, [rbx+18h]
0x140026235  call    cs:__imp_PsGetCurrentThreadId
0x14002623c  nop     dword ptr [rax+rax+00h]
0x140026241  mov     edx, 6Fh ; 'o'
0x140026246  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x14002624d  mov     r9, rax
0x140026250  mov     rcx, rbx
0x140026253  mov     rax, [rbp+BaseAddress]
0x140026257  mov     qword ptr [rsp+30h+AllocationType], rax
0x14002625c  call    WPP_SF_qq
0x140026261  mov     rax, [rbp+BaseAddress]
0x140026265  jmp     short loc_1400262AA
0x140026267  mov     rbx, cs:WPP_GLOBAL_Control
0x14002626e  cmp     rbx, r14
0x140026271  jz      short loc_1400262A8
0x140026273  mov     eax, [rbx+2Ch]
0x140026276  test    al, al
0x140026278  jns     short loc_1400262A8
0x14002627a  mov     rbx, [rbx+18h]
0x14002627e  call    cs:__imp_PsGetCurrentThreadId
0x140026285  nop     dword ptr [rax+rax+00h]
0x14002628a  mov     edx, 6Eh ; 'n'
0x14002628f  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140026296  mov     r9, rax
0x140026299  mov     rcx, rbx
0x14002629c  mov     eax, dword ptr [rbp+RegionSize]
0x14002629f  mov     [rsp+30h+AllocationType], eax
0x1400262a3  call    WPP_SF_qD
0x1400262a8  xor     eax, eax
0x1400262aa  mov     rbx, [rsp+30h+arg_10]
0x1400262af  mov     rsi, [rsp+30h+arg_18]
0x1400262b4  add     rsp, 30h
0x1400262b8  pop     r14
0x1400262ba  pop     rdi
0x1400262bb  pop     rbp
0x1400262bc  retn
```
