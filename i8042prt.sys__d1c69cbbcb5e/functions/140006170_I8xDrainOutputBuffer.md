# I8xDrainOutputBuffer

- ea: `0x140006170`
- end: `0x1400062a4`
- name: `I8xDrainOutputBuffer`
- size: `308`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400059c0`
- `0x14001eea0`

## callees

- `0x140004530`
- `0x140006170`
- `0x14000daa0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140006285`
- `ntoskrnl!KeDelayExecutionThread` at `0x140006285`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400061b2`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400061b2`
- `HAL!KeStallExecutionProcessor` at `0x14000626b`
- `HAL!KeStallExecutionProcessor` at `0x14000626b`

## pseudocode

```c
__int64 __fastcall I8xDrainOutputBuffer(__int64 a1, __int64 a2)
{
  KIRQL CurrentIrql; // si
  unsigned int i; // edi
  __int64 result; // rax
  int v7; // edx
  union _LARGE_INTEGER Interval; // [rsp+80h] [rbp+18h] BYREF

  Interval.QuadPart = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      19,
      13,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  Interval.QuadPart = -10000;
  CurrentIrql = KeGetCurrentIrql();
  for ( i = 0; i < 0x3E8; ++i )
  {
    if ( ((*(__int64 (__fastcall **)(__int64))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(a2) & 2) == 0 )
      break;
    if ( CurrentIrql )
      KeStallExecutionProcessor(0x3E8u);
    else
      KeDelayExecutionThread(0, 0, &Interval);
  }
  while ( 1 )
  {
    result = (*(__int64 (__fastcall **)(__int64))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(a2);
    if ( (result & 1) == 0 )
      break;
    (*(void (__fastcall **)(__int64))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(a1);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_(
             WPP_GLOBAL_Control->DeviceExtension,
             v7,
             19,
             14,
             (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140006170  push    rbx
0x140006172  push    rbp
0x140006173  push    rsi
0x140006174  push    rdi
0x140006175  push    r14
0x140006177  push    r15
0x140006179  sub     rsp, 38h
0x14000617d  mov     rbx, rdx
0x140006180  mov     qword ptr [rsp+68h+Interval], 0
0x14000618c  mov     rbp, rcx
0x14000618f  lea     r14, WPP_RECORDER_INITIALIZED
0x140006196  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000619d  lea     r15, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x1400061a4  jnz     short loc_140006204
0x1400061a6  mov     qword ptr [rsp+68h+Interval], 0FFFFFFFFFFFFD8F0h
0x1400061b2  call    cs:__imp_KeGetCurrentIrql
0x1400061b9  nop     dword ptr [rax+rax+00h]
0x1400061be  movzx   esi, al
0x1400061c1  xor     edi, edi
0x1400061c3  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x1400061ca  mov     rcx, rbx
0x1400061cd  call    _guard_dispatch_icall
0x1400061d2  test    al, 2
0x1400061d4  jnz     loc_140006261
0x1400061da  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x1400061e1  mov     rcx, rbx
0x1400061e4  call    _guard_dispatch_icall
0x1400061e9  test    al, 1
0x1400061eb  jnz     short loc_14000624D
0x1400061ed  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400061f4  jnz     short loc_14000622A
0x1400061f6  add     rsp, 38h
0x1400061fa  pop     r15
0x1400061fc  pop     r14
0x1400061fe  pop     rdi
0x1400061ff  pop     rsi
0x140006200  pop     rbp
0x140006201  pop     rbx
0x140006202  retn
0x140006204  mov     rcx, cs:WPP_GLOBAL_Control
0x14000620b  mov     r9d, 0Dh
0x140006211  mov     r8d, 13h
0x140006217  mov     [rsp+68h+var_48], r15
0x14000621c  mov     rcx, [rcx+40h]
0x140006220  call    WPP_RECORDER_SF_
0x140006225  jmp     loc_1400061A6
0x14000622a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006231  mov     r9d, 0Eh
0x140006237  mov     r8d, 13h
0x14000623d  mov     [rsp+68h+var_48], r15
0x140006242  mov     rcx, [rcx+40h]
0x140006246  call    WPP_RECORDER_SF_
0x14000624b  jmp     short loc_1400061F6
0x14000624d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x140006254  mov     rcx, rbp
0x140006257  call    _guard_dispatch_icall
0x14000625c  jmp     loc_1400061DA
0x140006261  test    sil, sil
0x140006264  jz      short loc_140006279
0x140006266  mov     ecx, 3E8h; MicroSeconds
0x14000626b  call    cs:__imp_KeStallExecutionProcessor
0x140006272  nop     dword ptr [rax+rax+00h]
0x140006277  jmp     short loc_140006291
0x140006279  lea     r8, [rsp+68h+Interval]; Interval
0x140006281  xor     edx, edx; Alertable
0x140006283  xor     ecx, ecx; WaitMode
0x140006285  call    cs:__imp_KeDelayExecutionThread
0x14000628c  nop     dword ptr [rax+rax+00h]
0x140006291  inc     edi
0x140006293  cmp     edi, 3E8h
0x140006299  jb      loc_1400061C3
0x14000629f  jmp     loc_1400061DA
```
