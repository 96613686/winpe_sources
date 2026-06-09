# I8042ErrorLogDpc

- ea: `0x140008f80`
- end: `0x1400090b2`
- name: `I8042ErrorLogDpc`
- size: `306`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140004530`
- `0x140008f80`
- `0x140009a30`
- `0x140009aac`

## import_xrefs

- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140008fcc`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140008fcc`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x140009051`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x140009051`

## pseudocode

```c
void __fastcall I8042ErrorLogDpc(
        struct _KDPC *Dpc,
        PVOID DeferredContext,
        PVOID SystemArgument1,
        char *SystemArgument2)
{
  _WORD *ErrorLogEntry; // rax
  int v7; // edx
  _WORD *v8; // rbx
  int v9; // ecx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)DeferredContext,
      7,
      26,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
  ErrorLogEntry = IoAllocateErrorLogEntry(DeferredContext, 0x38u);
  v7 = 0;
  v8 = ErrorLogEntry;
  if ( ErrorLogEntry )
  {
    ErrorLogEntry[1] = 8;
    if ( SystemArgument2 == (char *)1074069515 )
    {
      *((_DWORD *)ErrorLogEntry + 4) = 1310;
      *((_DWORD *)ErrorLogEntry + 10) = 12;
      v9 = *(_DWORD *)(*((_QWORD *)DeferredContext + 8) + 700LL);
    }
    else if ( SystemArgument2 == (char *)1074069516 )
    {
      *((_DWORD *)ErrorLogEntry + 4) = 1320;
      *((_DWORD *)ErrorLogEntry + 10) = 24;
      v9 = *(_DWORD *)(*((_QWORD *)DeferredContext + 8) + 592LL);
    }
    else
    {
      *((_DWORD *)ErrorLogEntry + 4) = 1330;
      v9 = 0;
      *((_DWORD *)ErrorLogEntry + 10) = 0;
    }
    *((_DWORD *)ErrorLogEntry + 11) = v9;
    *((_DWORD *)ErrorLogEntry + 3) = (_DWORD)SystemArgument2;
    *((_QWORD *)ErrorLogEntry + 3) = 0;
    *ErrorLogEntry = 0;
    *((_DWORD *)ErrorLogEntry + 5) = 0;
    IoWriteErrorLogEntry(ErrorLogEntry);
    if ( (unsigned __int64)(SystemArgument2 - 1074069515) < 2 )
      TraceLoggingBufferOverflow(*((unsigned int *)v8 + 3));
    else
      TraceLoggingErrorInDpcDiscovered(*((unsigned int *)v8 + 3));
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      7,
      27,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
}

```

## disassembly

```asm
0x140008f80  push    rbx
0x140008f82  push    rbp
0x140008f83  push    rsi
0x140008f84  push    rdi
0x140008f85  push    r15
0x140008f87  sub     rsp, 30h
0x140008f8b  mov     rdi, r9
0x140008f8e  mov     rsi, rdx
0x140008f91  lea     rbp, WPP_RECORDER_INITIALIZED
0x140008f98  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140008f9f  lea     r15, WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids
0x140008fa6  jz      short loc_140008FC7
0x140008fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x140008faf  mov     r9d, 1Ah
0x140008fb5  mov     [rsp+58h+var_38], r15
0x140008fba  mov     rcx, [rcx+40h]
0x140008fbe  lea     r8d, [r9-13h]
0x140008fc2  call    WPP_RECORDER_SF_
0x140008fc7  mov     dl, 38h ; '8'; EntrySize
0x140008fc9  mov     rcx, rsi; IoObject
0x140008fcc  call    cs:__imp_IoAllocateErrorLogEntry
0x140008fd3  nop     dword ptr [rax+rax+00h]
0x140008fd8  xor     edx, edx
0x140008fda  mov     rbx, rax
0x140008fdd  test    rax, rax
0x140008fe0  jz      loc_14000907E
0x140008fe6  mov     word ptr [rax+2], 8
0x140008fec  cmp     rdi, 4005000Bh
0x140008ff3  jnz     short loc_14000900F
0x140008ff5  mov     dword ptr [rax+10h], 51Eh
0x140008ffc  mov     dword ptr [rax+28h], 0Ch
0x140009003  mov     rax, [rsi+40h]
0x140009007  mov     ecx, [rax+2BCh]
0x14000900d  jmp     short loc_14000903E
0x14000900f  cmp     rdi, 4005000Ch
0x140009016  jnz     short loc_140009032
0x140009018  mov     dword ptr [rax+10h], 528h
0x14000901f  mov     dword ptr [rax+28h], 18h
0x140009026  mov     rax, [rsi+40h]
0x14000902a  mov     ecx, [rax+250h]
0x140009030  jmp     short loc_14000903E
0x140009032  mov     dword ptr [rax+10h], 532h
0x140009039  mov     ecx, edx
0x14000903b  mov     [rax+28h], edx
0x14000903e  mov     [rbx+2Ch], ecx
0x140009041  mov     rcx, rbx; ElEntry
0x140009044  mov     [rbx+0Ch], edi
0x140009047  mov     [rbx+18h], rdx
0x14000904b  mov     [rbx], dx
0x14000904e  mov     [rbx+14h], edx
0x140009051  call    cs:__imp_IoWriteErrorLogEntry
0x140009058  nop     dword ptr [rax+rax+00h]
0x14000905d  sub     rdi, 4005000Bh
0x140009064  jz      short loc_140009076
0x140009066  cmp     rdi, 1
0x14000906a  jz      short loc_140009076
0x14000906c  mov     ecx, [rbx+0Ch]
0x14000906f  call    TraceLoggingErrorInDpcDiscovered
0x140009074  jmp     short loc_14000907E
0x140009076  mov     ecx, [rbx+0Ch]
0x140009079  call    TraceLoggingBufferOverflow
0x14000907e  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140009085  jz      short loc_1400090A6
0x140009087  mov     rcx, cs:WPP_GLOBAL_Control
0x14000908e  mov     r9d, 1Bh
0x140009094  mov     [rsp+58h+var_38], r15
0x140009099  mov     rcx, [rcx+40h]
0x14000909d  lea     r8d, [r9-14h]
0x1400090a1  call    WPP_RECORDER_SF_
0x1400090a6  add     rsp, 30h
0x1400090aa  pop     r15
0x1400090ac  pop     rdi
0x1400090ad  pop     rsi
0x1400090ae  pop     rbp
0x1400090af  pop     rbx
0x1400090b0  retn
```
