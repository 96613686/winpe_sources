# PrjfExpansionCsqCompleteCanceledIo

- ea: `0x140029d90`
- end: `0x140029e81`
- name: `PrjfExpansionCsqCompleteCanceledIo`
- size: `241`
- prototype: `void __stdcall(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000d26c`
- `0x140029d90`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140029e6e`
- `ntoskrnl!KeSetEvent` at `0x140029e6e`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140029dcb`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140029dcb`
- `FLTMGR!FltCompletePendedPostOperation` at `0x140029da7`
- `FLTMGR!FltCompletePendedPostOperation` at `0x140029da7`

## pseudocode

```c
void __fastcall PrjfExpansionCsqCompleteCanceledIo(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)
{
  int v3; // edx
  int v4; // r8d

  if ( (Cbd->Flags & 0x80000) != 0 )
  {
    FltCompletePendedPostOperation(Cbd);
  }
  else
  {
    Cbd->IoStatus.Status = -1073741536;
    Cbd->IoStatus.Information = 0;
    FltCompletePendedPreOperation(Cbd, FLT_PREOP_COMPLETE, 0);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&Cbdq[-1].CompleteCanceledIo + 1, 0xFFFFFFFF) == 1 )
  {
    if ( (BYTE9(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = BYTE9(xmmword_14001A3D0) & 4;
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDZ(
        778,
        v3,
        v4,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        3,
        10,
        10,
        (__int64)&WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
        255,
        (__int64)Cbdq[1].Instance + 120);
    }
    KeSetEvent((PRKEVENT)&Cbdq[-1].PeekNextIo, 0, 0);
  }
}

```

## disassembly

```asm
0x140029d90  push    rbx
0x140029d92  sub     rsp, 60h
0x140029d96  test    dword ptr [rdx], 80000h
0x140029d9c  mov     rbx, rcx
0x140029d9f  mov     rcx, rdx; CallbackData
0x140029da2  mov     r9, rdx
0x140029da5  jz      short loc_140029DB5
0x140029da7  call    cs:__imp_FltCompletePendedPostOperation
0x140029dae  nop     dword ptr [rax+rax+00h]
0x140029db3  jmp     short loc_140029DD7
0x140029db5  xor     r8d, r8d; Context
0x140029db8  mov     dword ptr [rdx+18h], 0C0000120h
0x140029dbf  mov     qword ptr [rdx+20h], 0
0x140029dc7  lea     edx, [r8+4]; CallbackStatus
0x140029dcb  call    cs:__imp_FltCompletePendedPreOperation
0x140029dd2  nop     dword ptr [rax+rax+00h]
0x140029dd7  or      eax, 0FFFFFFFFh
0x140029dda  lock xadd [rbx-4], eax
0x140029ddf  cmp     eax, 1
0x140029de2  jnz     loc_140029E7A
0x140029de8  mov     dl, byte ptr cs:xmmword_14001A3D0+9
0x140029dee  lea     rax, WPP_RECORDER_INITIALIZED
0x140029df5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140029dfc  setnz   r8b
0x140029e00  and     dl, 4
0x140029e03  jnz     short loc_140029E0A
0x140029e05  test    r8b, r8b
0x140029e08  jz      short loc_140029E65
0x140029e0a  mov     rax, [rbx+0C8h]
0x140029e11  mov     r9d, 0Ah
0x140029e17  add     rax, 78h ; 'x'
0x140029e1b  mov     ecx, 30Ah
0x140029e20  mov     [rsp+68h+var_18], rax
0x140029e25  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140029e2c  mov     [rsp+68h+var_20], 1FFh
0x140029e34  mov     [rsp+68h+var_28], rax
0x140029e39  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x140029e40  mov     [rsp+68h+var_30], rax
0x140029e45  mov     [rsp+68h+var_38], r9w
0x140029e4b  mov     [rsp+68h+var_40], r9d
0x140029e50  mov     r9, cs:WPP_GLOBAL_Control
0x140029e57  mov     [rsp+68h+var_48], 3
0x140029e5c  mov     r9, [r9+40h]
0x140029e60  call    WPP_RECORDER_AND_TRACE_SF_sDZ
0x140029e65  lea     rcx, [rbx-20h]; Event
0x140029e69  xor     r8d, r8d; Wait
0x140029e6c  xor     edx, edx; Increment
0x140029e6e  call    cs:__imp_KeSetEvent
0x140029e75  nop     dword ptr [rax+rax+00h]
0x140029e7a  add     rsp, 60h
0x140029e7e  pop     rbx
0x140029e7f  retn
```
