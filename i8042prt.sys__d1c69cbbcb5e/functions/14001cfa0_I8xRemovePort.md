# I8xRemovePort

- ea: `0x14001cfa0`
- end: `0x14001d052`
- name: `I8xRemovePort`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001c808`
- `0x14001cce0`

## callees

- `0x14000cc5c`
- `0x14001cfa0`

## pseudocode

```c
char __fastcall I8xRemovePort(__int64 a1)
{
  ULONG SortKey; // r8d
  __int64 v2; // rdx
  __int64 i; // r9

  SortKey = WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.SortKey;
  v2 = *(unsigned int *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 240LL);
  if ( (_DWORD)v2 != -1 )
  {
    for ( i = 0; (unsigned int)i < (unsigned int)v2; i = (unsigned int)(i + 1) )
    {
      if ( *(_QWORD *)(a1 + 16) == *(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 8 * i + 224) )
        return 1;
    }
    if ( (unsigned int)v2 < 2 )
    {
      *(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 8 * v2 + 224) = *(_QWORD *)(a1 + 16);
      ++*(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 240LL);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_DDDD(WPP_GLOBAL_Control->DeviceExtension, v2, SortKey, 25);
  }
  return 0;
}

```

## disassembly

```asm
0x14001cfa0  sub     rsp, 58h
0x14001cfa4  mov     r8, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001cfab  mov     r10, rcx
0x14001cfae  mov     edx, [r8+0F0h]
0x14001cfb5  cmp     edx, 0FFFFFFFFh
0x14001cfb8  jz      loc_14001D04A
0x14001cfbe  mov     rax, [rcx+10h]
0x14001cfc2  xor     r9d, r9d
0x14001cfc5  mov     [rsp+58h+arg_8], rax
0x14001cfca  mov     r11d, dword ptr [rsp+58h+arg_8+4]
0x14001cfcf  cmp     r9d, edx
0x14001cfd2  jnb     short loc_14001CFF1
0x14001cfd4  cmp     eax, [r8+r9*8+0E0h]
0x14001cfdc  jnz     short loc_14001CFE8
0x14001cfde  cmp     r11d, [r8+r9*8+0E4h]
0x14001cfe6  jz      short loc_14001CFED
0x14001cfe8  inc     r9d
0x14001cfeb  jmp     short loc_14001CFCF
0x14001cfed  mov     al, 1
0x14001cfef  jmp     short loc_14001D04C
0x14001cff1  cmp     edx, 2
0x14001cff4  jnb     short loc_14001D00B
0x14001cff6  mov     [r8+rdx*8+0E0h], rax
0x14001cffe  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001d005  inc     dword ptr [rcx+0F0h]
0x14001d00b  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001d012  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001d019  jz      short loc_14001D04A
0x14001d01b  mov     ecx, [r10+18h]
0x14001d01f  mov     r9d, 19h
0x14001d025  mov     [rsp+58h+var_18], ecx
0x14001d029  mov     ecx, [r10+1Ch]
0x14001d02d  mov     [rsp+58h+var_20], ecx
0x14001d031  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d038  mov     [rsp+58h+var_28], eax
0x14001d03c  mov     [rsp+58h+var_30], r11d
0x14001d041  mov     rcx, [rcx+40h]
0x14001d045  call    WPP_RECORDER_SF_DDDD
0x14001d04a  xor     al, al
0x14001d04c  add     rsp, 58h
0x14001d050  retn
```
