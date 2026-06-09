# VidSchiSelectContext

- ea: `0x14000fdc0`
- end: `0x1400101f5`
- name: `VidSchiSelectContext`
- size: `1077`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1400e39ac`

## callees

- `0x14000a2ac`
- `0x14000a488`
- `0x14000fdc0`
- `0x140010200`
- `0x140011610`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000fdff`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000fdff`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400101e4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400101e4`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000ff65`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x140010054`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x140010089`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000ff65`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x140010054`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x140010089`
- `ntoskrnl!RtlCopyBitMapEx` at `0x14000fe55`
- `ntoskrnl!RtlCopyBitMapEx` at `0x14000fe9c`
- `ntoskrnl!RtlCopyBitMapEx` at `0x14000fe55`
- `ntoskrnl!RtlCopyBitMapEx` at `0x14000fe9c`
- `ntoskrnl!RtlIntersectBitMapsEx` at `0x14000fe6b`
- `ntoskrnl!RtlIntersectBitMapsEx` at `0x14000fe6b`
- `ntoskrnl!RtlAreBitsClearEx` at `0x14000fe7f`
- `ntoskrnl!RtlAreBitsClearEx` at `0x14000fe7f`
- `ntoskrnl!RtlFindSetBitsEx` at `0x14000feba`
- `ntoskrnl!RtlFindSetBitsEx` at `0x14000feba`
- `watchdog!WdLogSingleEntry1` at `0x14001019b`
- `watchdog!WdLogSingleEntry1` at `0x1400101c1`
- `watchdog!WdLogSingleEntry1` at `0x14001019b`
- `watchdog!WdLogSingleEntry1` at `0x1400101c1`
- `dxgkrnl!DpSynchronizeExecution` at `0x14000ff43`
- `dxgkrnl!DpSynchronizeExecution` at `0x14000ff43`
- `HAL!KeQueryPerformanceCounter` at `0x1400100bf`
- `HAL!KeQueryPerformanceCounter` at `0x140010146`
- `HAL!KeQueryPerformanceCounter` at `0x1400100bf`
- `HAL!KeQueryPerformanceCounter` at `0x140010146`

## pseudocode

```c
struct _VIDSCH_CONTEXT *__fastcall VidSchiSelectContext(__int64 a1, int a2)
{
  struct _VIDSCH_CONTEXT *v4; // rdi
  __int64 v5; // rax
  __int64 SetBits; // rax
  __int64 *v7; // rbp
  __int64 v8; // rbp
  __int64 v9; // rcx
  __int64 v10; // rdx
  CCHAR v11; // al
  __int64 v13; // rax
  CCHAR MostSignificantBit; // al
  CCHAR v15; // al
  LARGE_INTEGER v16; // r14
  unsigned int v17; // edx
  __int64 v18; // rcx
  LARGE_INTEGER v19; // r14
  unsigned int v20; // edx
  __int64 v21; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-68h] BYREF
  __int64 v23; // [rsp+58h] [rbp-50h] BYREF
  __int128 v24; // [rsp+60h] [rbp-48h]
  __int64 v25; // [rsp+70h] [rbp-38h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+B0h] [rbp+8h] BYREF
  char v27; // [rsp+B8h] [rbp+10h] BYREF

  v4 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !a2 )
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 2096), &LockHandle);
  if ( *(_DWORD *)(a1 + 864) )
  {
    v5 = *(_QWORD *)(a1 + 272);
    if ( v5 && (*(_DWORD *)(v5 + 192) & 1) != 0 )
    {
      v4 = *(struct _VIDSCH_CONTEXT **)(a1 + 272);
    }
    else
    {
      RtlCopyBitMapEx(a1 + 584, a1 + 680, 0);
      RtlIntersectBitMapsEx(a1 + 680, a1 + 632);
      if ( (unsigned __int8)RtlAreBitsClearEx(a1 + 680, 0, *(_QWORD *)(a1 + 680)) )
        RtlCopyBitMapEx(a1 + 584, a1 + 680, 0);
      SetBits = RtlFindSetBitsEx(a1 + 680, 1, (unsigned int)(*(_DWORD *)(a1 + 856) + 1));
      if ( SetBits != -1 )
      {
        v7 = *(__int64 **)(a1 + 776);
        if ( (unsigned int)SetBits < *(_DWORD *)(a1 + 848) )
          v7 += (unsigned int)SetBits;
        v8 = *v7;
        *(_DWORD *)(a1 + 856) = SetBits;
        if ( v8 )
        {
          if ( *(_DWORD *)(v8 + 1900) )
          {
            v9 = *(_QWORD *)(v8 + 24);
            v27 = 0;
            v25 = 0;
            v23 = v8;
            v24 = 0;
            DpSynchronizeExecution(
              *(_QWORD *)(v9 + 32),
              VidSchiUpdateNodeRunningTimeAtISR,
              &v23,
              *(unsigned int *)(v9 + 40),
              &v27);
          }
          v10 = *(unsigned int *)(v8 + 1896);
          if ( *(_BYTE *)(v8 + 2152)
            && (v10 & 0xC0000000) == 0
            && (v13 = *(_QWORD *)(v8 + 24), (v10 & (0xFFFFFFFFuLL >> (31 - *(_BYTE *)(v13 + 224)))) != 0) )
          {
            MostSignificantBit = RtlFindMostSignificantBit(v10 & (0xFFFFFFFFuLL >> (31 - *(_BYTE *)(v13 + 224))));
            v4 = VidSchiSelectContextFromThisPriority((struct _VIDSCH_NODE *)v8, MostSignificantBit, 1);
            if ( v4 )
            {
              VidSchiUpdateNodeYieldStatus((struct _VIDSCH_NODE *)v8);
            }
            else
            {
              v15 = RtlFindMostSignificantBit(*(unsigned int *)(v8 + 1896));
              v4 = VidSchiSelectContextFromThisPriority((struct _VIDSCH_NODE *)v8, v15, 0);
              if ( !*(_QWORD *)(v8 + 2128) )
              {
                PerformanceFrequency.QuadPart = 0;
                v16 = KeQueryPerformanceCounter(&PerformanceFrequency);
                v17 = *(_DWORD *)(*((_QWORD *)v4 + 13) + 512LL);
                v18 = 0;
                if ( v17 <= *(_DWORD *)(a1 + 48) )
                  v18 = v17;
                if ( !*(_DWORD *)(*(_QWORD *)(a1 + 8 * v18 + 3528) + 83104LL) )
                {
                  WdLogSingleEntry1(3, (unsigned int)v18);
                  WdLogGlobalForLineNumber = 18990;
                }
                ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))VidSchiStartNodeYield)(
                  v8,
                  (LARGE_INTEGER)v16.QuadPart,
                  (union _LARGE_INTEGER)PerformanceFrequency.QuadPart);
              }
              VidSchiProfilePerformanceTick(20, a1, v8, 0, (__int64)v4, 0, 0, 1);
            }
          }
          else
          {
            v11 = RtlFindMostSignificantBit(*(unsigned int *)(v8 + 1896));
            v4 = VidSchiSelectContextFromThisPriority((struct _VIDSCH_NODE *)v8, v11, 0);
            if ( (*(_DWORD *)(a1 + 2904) & 8) != 0 && *(_BYTE *)(v8 + 2152) && !*(_QWORD *)(v8 + 2128) )
            {
              PerformanceFrequency.QuadPart = 0;
              v19 = KeQueryPerformanceCounter(&PerformanceFrequency);
              v20 = *(_DWORD *)(*((_QWORD *)v4 + 13) + 512LL);
              v21 = 0;
              if ( v20 <= *(_DWORD *)(a1 + 48) )
                v21 = v20;
              if ( !*(_DWORD *)(*(_QWORD *)(a1 + 8 * v21 + 3528) + 83104LL) )
              {
                WdLogSingleEntry1(3, (unsigned int)v21);
                WdLogGlobalForLineNumber = 18990;
              }
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))VidSchiStartNodeYield)(
                v8,
                (LARGE_INTEGER)v19.QuadPart,
                (union _LARGE_INTEGER)PerformanceFrequency.QuadPart);
            }
            VidSchiProfilePerformanceTick(20, a1, v8, 0, (__int64)v4, 0, 0, 0);
          }
        }
      }
    }
  }
  VidSchiProfilePerformanceTick(2, a1, 0, 0, (__int64)v4, 0, 0, 0);
  if ( !a2 )
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  return v4;
}

```

## disassembly

```asm
0x14000fdc0  mov     r11, rsp
0x14000fdc3  push    rdi
0x14000fdc4  sub     rsp, 0A0h
0x14000fdcb  mov     [r11+18h], rbx
0x14000fdcf  xor     eax, eax
0x14000fdd1  mov     [r11-18h], rsi
0x14000fdd5  xorps   xmm0, xmm0
0x14000fdd8  mov     [r11-28h], r15
0x14000fddc  mov     esi, edx
0x14000fdde  xor     r15d, r15d
0x14000fde1  mov     rbx, rcx
0x14000fde4  mov     edi, r15d
0x14000fde7  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14000fdec  mov     [r11-58h], rax
0x14000fdf0  test    edx, edx
0x14000fdf2  jnz     short loc_14000FE0B
0x14000fdf4  add     rcx, 830h; SpinLock
0x14000fdfb  lea     rdx, [r11-68h]; LockHandle
0x14000fdff  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000fe06  nop     dword ptr [rax+rax+00h]
0x14000fe0b  cmp     [rbx+360h], edi
0x14000fe11  jz      loc_14000FFC7
0x14000fe17  mov     rax, [rbx+110h]
0x14000fe1e  test    rax, rax
0x14000fe21  jz      short loc_14000FE31
0x14000fe23  mov     eax, [rax+0C0h]
0x14000fe29  test    al, 1
0x14000fe2b  jnz     loc_14001001B
0x14000fe31  mov     [rsp+0A8h+var_10], rbp
0x14000fe39  lea     rcx, [rbx+248h]
0x14000fe40  mov     [rsp+0A8h+var_20], r14
0x14000fe48  xor     r8d, r8d
0x14000fe4b  lea     r14, [rbx+2A8h]
0x14000fe52  mov     rdx, r14
0x14000fe55  call    cs:__imp_RtlCopyBitMapEx
0x14000fe5c  nop     dword ptr [rax+rax+00h]
0x14000fe61  lea     rdx, [rbx+278h]
0x14000fe68  mov     rcx, r14
0x14000fe6b  call    cs:__imp_RtlIntersectBitMapsEx
0x14000fe72  nop     dword ptr [rax+rax+00h]
0x14000fe77  mov     r8, [r14]
0x14000fe7a  xor     edx, edx
0x14000fe7c  mov     rcx, r14
0x14000fe7f  call    cs:__imp_RtlAreBitsClearEx
0x14000fe86  nop     dword ptr [rax+rax+00h]
0x14000fe8b  test    al, al
0x14000fe8d  jz      short loc_14000FEA8
0x14000fe8f  xor     r8d, r8d
0x14000fe92  lea     rcx, [rbx+248h]
0x14000fe99  mov     rdx, r14
0x14000fe9c  call    cs:__imp_RtlCopyBitMapEx
0x14000fea3  nop     dword ptr [rax+rax+00h]
0x14000fea8  mov     r8d, [rbx+358h]
0x14000feaf  mov     edx, 1
0x14000feb4  inc     r8d
0x14000feb7  mov     rcx, r14
0x14000feba  call    cs:__imp_RtlFindSetBitsEx
0x14000fec1  nop     dword ptr [rax+rax+00h]
0x14000fec6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000feca  jz      loc_14000FFB7
0x14000fed0  mov     rbp, [rbx+308h]
0x14000fed7  cmp     eax, [rbx+350h]
0x14000fedd  jnb     short loc_14000FEE6
0x14000fedf  mov     ecx, eax
0x14000fee1  lea     rbp, [rbp+rcx*8+0]
0x14000fee6  mov     rbp, [rbp+0]
0x14000feea  mov     [rbx+358h], eax
0x14000fef0  test    rbp, rbp
0x14000fef3  jz      loc_14000FFB7
0x14000fef9  mov     eax, [rbp+76Ch]
0x14000feff  test    eax, eax
0x14000ff01  jz      short loc_14000FF4F
0x14000ff03  mov     rcx, [rbp+18h]
0x14000ff07  lea     rax, [rsp+0A8h+arg_8]
0x14000ff0f  mov     [rsp+0A8h+arg_8], dil
0x14000ff17  lea     r8, [rsp+0A8h+var_50]
0x14000ff1c  mov     [rsp+0A8h+var_38], r15
0x14000ff21  lea     rdx, VidSchiUpdateNodeRunningTimeAtISR
0x14000ff28  mov     [rsp+0A8h+var_50], rbp
0x14000ff2d  xorps   xmm0, xmm0
0x14000ff30  movdqu  [rsp+0A8h+var_48], xmm0
0x14000ff36  mov     r9d, [rcx+28h]
0x14000ff3a  mov     rcx, [rcx+20h]
0x14000ff3e  mov     [rsp+0A8h+var_88], rax
0x14000ff43  call    cs:__imp_DpSynchronizeExecution
0x14000ff4a  nop     dword ptr [rax+rax+00h]
0x14000ff4f  mov     edx, [rbp+768h]
0x14000ff55  cmp     [rbp+868h], dil
0x14000ff5c  jnz     loc_140010024
0x14000ff62  mov     rcx, rdx; Set
0x14000ff65  call    cs:__imp_RtlFindMostSignificantBit
0x14000ff6c  nop     dword ptr [rax+rax+00h]
0x14000ff71  movsx   edx, al; unsigned int
0x14000ff74  xor     r8d, r8d; bool
0x14000ff77  mov     rcx, rbp; struct _VIDSCH_NODE *
0x14000ff7a  call    ?VidSchiSelectContextFromThisPriority@@YAPEAU_VIDSCH_CONTEXT@@PEAU_VIDSCH_NODE@@K_N@Z; VidSchiSelectContextFromThisPriority(_VIDSCH_NODE *,ulong,bool)
0x14000ff7f  mov     rdi, rax
0x14000ff82  mov     eax, [rbx+0B58h]
0x14000ff88  test    al, 8
0x14000ff8a  jnz     loc_14001011C
0x14000ff90  mov     [rsp+0A8h+var_70], r15
0x14000ff95  mov     [rsp+0A8h+var_78], r15
0x14000ff9a  xor     r9d, r9d
0x14000ff9d  mov     [rsp+0A8h+var_80], r15
0x14000ffa2  mov     r8, rbp
0x14000ffa5  mov     rdx, rbx
0x14000ffa8  mov     [rsp+0A8h+var_88], rdi
0x14000ffad  mov     ecx, 14h
0x14000ffb2  call    VidSchiProfilePerformanceTick
0x14000ffb7  mov     rbp, [rsp+0A8h+var_10]
0x14000ffbf  mov     r14, [rsp+0A8h+var_20]
0x14000ffc7  mov     [rsp+0A8h+var_70], r15
0x14000ffcc  xor     r9d, r9d
0x14000ffcf  mov     [rsp+0A8h+var_78], r15
0x14000ffd4  xor     r8d, r8d
0x14000ffd7  mov     [rsp+0A8h+var_80], r15
0x14000ffdc  mov     rdx, rbx
0x14000ffdf  mov     ecx, 2
0x14000ffe4  mov     [rsp+0A8h+var_88], rdi
0x14000ffe9  call    VidSchiProfilePerformanceTick
0x14000ffee  mov     r15, [rsp+0A8h+var_28]
0x14000fff6  test    esi, esi
0x14000fff8  mov     rsi, [rsp+0A8h+var_18]
0x140010000  mov     rbx, [rsp+0A8h+arg_10]
0x140010008  jz      loc_1400101DF
0x14001000e  mov     rax, rdi
0x140010011  add     rsp, 0A0h
0x140010018  pop     rdi
0x140010019  retn
0x14001001b  mov     rdi, [rbx+110h]
0x140010022  jmp     short loc_14000FFC7
0x140010024  test    edx, 0C0000000h
0x14001002a  jnz     loc_14000FF62
0x140010030  mov     rax, [rbp+18h]
0x140010034  mov     ecx, 1Fh
0x140010039  mov     r8d, 0FFFFFFFFh
0x14001003f  sub     ecx, [rax+0E0h]
0x140010045  shr     r8, cl
0x140010048  and     r8, rdx
0x14001004b  jz      loc_14000FF62
0x140010051  mov     rcx, r8; Set
0x140010054  call    cs:__imp_RtlFindMostSignificantBit
0x14001005b  nop     dword ptr [rax+rax+00h]
0x140010060  movsx   edx, al; unsigned int
0x140010063  mov     r8b, 1; bool
0x140010066  mov     rcx, rbp; struct _VIDSCH_NODE *
0x140010069  call    ?VidSchiSelectContextFromThisPriority@@YAPEAU_VIDSCH_CONTEXT@@PEAU_VIDSCH_NODE@@K_N@Z; VidSchiSelectContextFromThisPriority(_VIDSCH_NODE *,ulong,bool)
0x14001006e  mov     rdi, rax
0x140010071  test    rax, rax
0x140010074  jz      short loc_140010083
0x140010076  mov     rcx, rbp; struct _VIDSCH_NODE *
0x140010079  call    ?VidSchiUpdateNodeYieldStatus@@YAXPEAU_VIDSCH_NODE@@@Z; VidSchiUpdateNodeYieldStatus(_VIDSCH_NODE *)
0x14001007e  jmp     loc_14000FFB7
0x140010083  mov     ecx, [rbp+768h]; Set
0x140010089  call    cs:__imp_RtlFindMostSignificantBit
0x140010090  nop     dword ptr [rax+rax+00h]
0x140010095  movsx   edx, al; unsigned int
0x140010098  xor     r8d, r8d; bool
0x14001009b  mov     rcx, rbp; struct _VIDSCH_NODE *
0x14001009e  call    ?VidSchiSelectContextFromThisPriority@@YAPEAU_VIDSCH_CONTEXT@@PEAU_VIDSCH_NODE@@K_N@Z; VidSchiSelectContextFromThisPriority(_VIDSCH_NODE *,ulong,bool)
0x1400100a3  mov     rdi, rax
0x1400100a6  cmp     [rbp+850h], r15
0x1400100ad  jnz     short loc_14001010E
0x1400100af  lea     rcx, [rsp+0A8h+PerformanceFrequency]; PerformanceFrequency
0x1400100b7  mov     qword ptr [rsp+0A8h+PerformanceFrequency], r15
0x1400100bf  call    cs:__imp_KeQueryPerformanceCounter
0x1400100c6  nop     dword ptr [rax+rax+00h]
0x1400100cb  mov     rcx, [rdi+68h]
0x1400100cf  mov     r14, rax
0x1400100d2  mov     edx, [rcx+200h]
0x1400100d8  mov     ecx, r15d
0x1400100db  cmp     edx, [rbx+30h]
0x1400100de  cmovbe  ecx, edx
0x1400100e1  mov     edx, ecx
0x1400100e3  mov     rcx, [rbx+rcx*8+0DC8h]
0x1400100eb  mov     r9d, [rcx+144A0h]
0x1400100f2  test    r9d, r9d
0x1400100f5  jz      loc_140010196
0x1400100fb  mov     r8, qword ptr [rsp+0A8h+PerformanceFrequency]
0x140010103  mov     rdx, r14
0x140010106  mov     rcx, rbp
0x140010109  call    VidSchiStartNodeYield
0x14001010e  mov     [rsp+0A8h+var_70], 1
0x140010117  jmp     loc_14000FF95
0x14001011c  cmp     [rbp+868h], r15b
0x140010123  jz      loc_14000FF90
0x140010129  cmp     [rbp+850h], r15
0x140010130  jnz     loc_14000FF90
0x140010136  lea     rcx, [rsp+0A8h+PerformanceFrequency]; PerformanceFrequency
0x14001013e  mov     qword ptr [rsp+0A8h+PerformanceFrequency], r15
0x140010146  call    cs:__imp_KeQueryPerformanceCounter
0x14001014d  nop     dword ptr [rax+rax+00h]
0x140010152  mov     rcx, [rdi+68h]
0x140010156  mov     r14, rax
0x140010159  mov     edx, [rcx+200h]
0x14001015f  mov     ecx, r15d
0x140010162  cmp     edx, [rbx+30h]
0x140010165  cmovbe  ecx, edx
0x140010168  mov     edx, ecx
0x14001016a  mov     rcx, [rbx+rcx*8+0DC8h]
0x140010172  mov     r9d, [rcx+144A0h]
0x140010179  test    r9d, r9d
0x14001017c  jz      short loc_1400101BC
0x14001017e  mov     r8, qword ptr [rsp+0A8h+PerformanceFrequency]
0x140010186  mov     rdx, r14
0x140010189  mov     rcx, rbp
0x14001018c  call    VidSchiStartNodeYield
0x140010191  jmp     loc_14000FF90
0x140010196  mov     ecx, 3
0x14001019b  call    cs:__imp_WdLogSingleEntry1
0x1400101a2  nop     dword ptr [rax+rax+00h]
0x1400101a7  mov     r9d, 10h
0x1400101ad  mov     cs:WdLogGlobalForLineNumber, 4A2Eh
0x1400101b7  jmp     loc_1400100FB
0x1400101bc  mov     ecx, 3
0x1400101c1  call    cs:__imp_WdLogSingleEntry1
0x1400101c8  nop     dword ptr [rax+rax+00h]
0x1400101cd  mov     r9d, 10h
0x1400101d3  mov     cs:WdLogGlobalForLineNumber, 4A2Eh
0x1400101dd  jmp     short loc_14001017E
0x1400101df  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x1400101e4  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400101eb  nop     dword ptr [rax+rax+00h]
0x1400101f0  jmp     loc_14001000E
```
