# RefsFsdFlushBuffers

- ea: `0x1c01a4fe0`
- end: `0x1c01a51ed`
- name: `RefsFsdFlushBuffers`
- size: `525`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1c0005564`
- `0x1c0005650`
- `0x1c000f480`
- `0x1c00588cc`
- `0x1c0062ce0`
- `0x1c0068960`
- `0x1c01a40d0`
- `0x1c01a4fe0`
- `0x1c01cd29c`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x1c01a50d1`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c01a50d1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01a5036`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01a5036`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c01a504f`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c01a504f`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c01a518b`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c01a518b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c01a5197`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c01a5197`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c01a5090`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c01a5090`
- `HAL!KeQueryPerformanceCounter` at `0x1c01a5101`
- `HAL!KeQueryPerformanceCounter` at `0x1c01a5101`

## pseudocode

```c
__int64 __fastcall RefsFsdFlushBuffers(__int64 a1, IRP *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  PIRP v5; // rcx
  struct _LIST_ENTRY *Flink; // rax
  LARGE_INTEGER *v7; // rbx
  unsigned int v8; // edi
  LARGE_INTEGER *v10; // [rsp+20h] [rbp-78h] BYREF
  unsigned int v11; // [rsp+28h] [rbp-70h]
  BOOL v12; // [rsp+2Ch] [rbp-6Ch]
  __int64 v13; // [rsp+30h] [rbp-68h] BYREF
  PIRP Irp; // [rsp+38h] [rbp-60h]
  IRP *v15; // [rsp+40h] [rbp-58h]
  IRP *v16; // [rsp+48h] [rbp-50h]
  _OWORD v17[2]; // [rsp+50h] [rbp-48h] BYREF
  __int64 v18; // [rsp+70h] [rbp-28h]
  __int128 v19; // [rsp+78h] [rbp-20h] BYREF

  v16 = a2;
  memset(v17, 0, sizeof(v17));
  v18 = 0;
  v10 = 0;
  v19 = 0;
  v13 = 0;
  KeEnterCriticalRegion();
  v12 = (int)IoPropagateActivityIdToThread(a2, &v19, &v13) >= 0;
  v15 = (IRP *)RefsInitializeTopLevelIrp(v17, 0, 0);
  Irp = v15;
  LOBYTE(v3) = IoIsOperationSynchronous(a2);
  LOBYTE(v4) = 1;
  RefsInitializeIrpContext(a2, v3, v4, &v10);
  v5 = Irp;
  Flink = Irp->ThreadListEntry.Flink;
  if ( Flink )
  {
    v7 = v10;
  }
  else
  {
    *(_DWORD *)(&Irp->Size + 1) = 1397140410;
    v7 = v10;
    v5->ThreadListEntry.Flink = (struct _LIST_ENTRY *)v10;
    v7[1].LowPart |= 0x100000u;
    IoSetTopLevelIrp(v5);
    Flink = v15->ThreadListEntry.Flink;
  }
  v7[13].QuadPart = (LONGLONG)Flink;
  if ( *(_QWORD *)(v7[8].QuadPart + 3944) )
    v7[31] = KeQueryPerformanceCounter(0);
  RefsPreRequestProcessingExtend(v7);
  v8 = RefsCommonFlushBuffers(v7, a2);
  v11 = v8;
  if ( v12 )
    IoClearActivityIdThread(v13);
  KeLeaveCriticalRegion();
  return v8;
}

```

## disassembly

```asm
0x1c01a4fe0  mov     r11, rsp
0x1c01a4fe3  mov     [r11+8], rbx
0x1c01a4fe7  mov     [r11+18h], rsi
0x1c01a4feb  mov     [r11+20h], rdi
0x1c01a4fef  push    r14
0x1c01a4ff1  sub     rsp, 90h
0x1c01a4ff8  mov     rax, cs:__security_cookie
0x1c01a4fff  xor     rax, rsp
0x1c01a5002  mov     [rsp+98h+var_10], rax
0x1c01a500a  mov     rsi, rdx
0x1c01a500d  mov     [rsp+98h+var_50], rdx
0x1c01a5012  xorps   xmm0, xmm0
0x1c01a5015  xor     eax, eax
0x1c01a5017  movups  [rsp+98h+var_48], xmm0
0x1c01a501c  movups  [rsp+98h+var_38], xmm0
0x1c01a5021  mov     [r11-28h], rax
0x1c01a5025  xor     edi, edi
0x1c01a5027  xor     ebx, ebx
0x1c01a5029  mov     [r11-78h], rbx
0x1c01a502d  movups  [rsp+98h+var_20], xmm0
0x1c01a5032  and     [r11-68h], rax
0x1c01a5036  call    cs:__imp_KeEnterCriticalRegion
0x1c01a503d  nop     dword ptr [rax+rax+00h]
0x1c01a5042  lea     r8, [rsp+98h+var_68]
0x1c01a5047  lea     rdx, [rsp+98h+var_20]
0x1c01a504c  mov     rcx, rsi
0x1c01a504f  call    cs:__imp_IoPropagateActivityIdToThread
0x1c01a5056  nop     dword ptr [rax+rax+00h]
0x1c01a505b  xor     ecx, ecx
0x1c01a505d  lea     r14d, [rdi+1]
0x1c01a5061  test    eax, eax
0x1c01a5063  cmovns  ecx, r14d
0x1c01a5067  mov     [rsp+98h+var_6C], ecx
0x1c01a506b  xor     r8d, r8d
0x1c01a506e  xor     edx, edx
0x1c01a5070  lea     rcx, [rsp+98h+var_48]
0x1c01a5075  call    RefsInitializeTopLevelIrp
0x1c01a507a  mov     [rsp+98h+var_58], rax
0x1c01a507f  mov     [rsp+98h+Irp], rax
0x1c01a5084  test    rbx, rbx
0x1c01a5087  jnz     loc_1C01A5116
0x1c01a508d  mov     rcx, rsi; Irp
0x1c01a5090  call    cs:__imp_IoIsOperationSynchronous
0x1c01a5097  nop     dword ptr [rax+rax+00h]
0x1c01a509c  mov     dl, al
0x1c01a509e  lea     r9, [rsp+98h+var_78]
0x1c01a50a3  mov     r8b, r14b
0x1c01a50a6  mov     rcx, rsi
0x1c01a50a9  call    RefsInitializeIrpContext
0x1c01a50ae  mov     rcx, [rsp+98h+Irp]; Irp
0x1c01a50b3  mov     rax, [rcx+20h]
0x1c01a50b7  test    rax, rax
0x1c01a50ba  jnz     short loc_1C01A50E8
0x1c01a50bc  mov     dword ptr [rcx+4], 5346ABBAh
0x1c01a50c3  mov     rbx, [rsp+98h+var_78]
0x1c01a50c8  mov     [rcx+20h], rbx
0x1c01a50cc  bts     dword ptr [rbx+8], 14h
0x1c01a50d1  call    cs:__imp_IoSetTopLevelIrp
0x1c01a50d8  nop     dword ptr [rax+rax+00h]
0x1c01a50dd  mov     rax, [rsp+98h+var_58]
0x1c01a50e2  mov     rax, [rax+20h]
0x1c01a50e6  jmp     short loc_1C01A50ED
0x1c01a50e8  mov     rbx, [rsp+98h+var_78]
0x1c01a50ed  mov     [rbx+68h], rax
0x1c01a50f1  mov     rax, [rbx+40h]
0x1c01a50f5  cmp     qword ptr [rax+0F68h], 0
0x1c01a50fd  jz      short loc_1C01A5126
0x1c01a50ff  xor     ecx, ecx; PerformanceFrequency
0x1c01a5101  call    cs:__imp_KeQueryPerformanceCounter
0x1c01a5108  nop     dword ptr [rax+rax+00h]
0x1c01a510d  mov     [rbx+0F8h], rax
0x1c01a5114  jmp     short loc_1C01A5126
0x1c01a5116  cmp     edi, 0C0000188h
0x1c01a511c  jnz     short loc_1C01A5126
0x1c01a511e  mov     rcx, rbx
0x1c01a5121  call    RefsCheckpointForLogFileFull
0x1c01a5126  mov     rcx, rbx
0x1c01a5129  call    RefsPreRequestProcessingExtend
0x1c01a512e  mov     rdx, rsi
0x1c01a5131  mov     rcx, rbx
0x1c01a5134  call    RefsCommonFlushBuffers
0x1c01a5139  mov     edi, eax
0x1c01a513b  mov     [rsp+98h+var_70], eax
0x1c01a513f  jmp     short loc_1C01A517F
0x1c01a5141  mov     r8d, eax
0x1c01a5144  mov     rsi, [rsp+98h+var_50]
0x1c01a5149  mov     rdx, rsi
0x1c01a514c  mov     rbx, [rsp+98h+var_78]
0x1c01a5151  mov     rcx, rbx
0x1c01a5154  call    RefsProcessException
0x1c01a5159  mov     edi, eax
0x1c01a515b  mov     [rsp+98h+var_70], eax
0x1c01a515f  cmp     eax, 0C00000D8h
0x1c01a5164  jz      short loc_1C01A516D
0x1c01a5166  cmp     eax, 0C00001A8h
0x1c01a516b  jnz     short loc_1C01A5178
0x1c01a516d  mov     r14d, 1
0x1c01a5173  jmp     loc_1C01A5084
0x1c01a5178  cmp     eax, 0C0000188h
0x1c01a517d  jz      short loc_1C01A516D
0x1c01a517f  cmp     [rsp+98h+var_6C], 0
0x1c01a5184  jz      short loc_1C01A5197
0x1c01a5186  mov     rcx, [rsp+98h+var_68]
0x1c01a518b  call    cs:__imp_IoClearActivityIdThread
0x1c01a5192  nop     dword ptr [rax+rax+00h]
0x1c01a5197  call    cs:__imp_KeLeaveCriticalRegion
0x1c01a519e  nop     dword ptr [rax+rax+00h]
0x1c01a51a3  mov     eax, edi
0x1c01a51a5  mov     rcx, [rsp+98h+var_10]
0x1c01a51ad  xor     rcx, rsp; StackCookie
0x1c01a51b0  call    __security_check_cookie
0x1c01a51b5  lea     r11, [rsp+98h+var_8]
0x1c01a51bd  mov     rbx, [r11+10h]
0x1c01a51c1  mov     rsi, [r11+20h]
0x1c01a51c5  mov     rdi, [r11+28h]
0x1c01a51c9  mov     rsp, r11
0x1c01a51cc  pop     r14
0x1c01a51ce  retn
0x1c01a51d0  push    rbp
0x1c01a51d2  sub     rsp, 20h
0x1c01a51d6  mov     rbp, rdx
0x1c01a51d9  mov     rdx, rcx
0x1c01a51dc  mov     rcx, [rbp+20h]
0x1c01a51e0  call    RefsExceptionFilter
0x1c01a51e5  nop
0x1c01a51e6  add     rsp, 20h
0x1c01a51ea  pop     rbp
0x1c01a51eb  retn
```
