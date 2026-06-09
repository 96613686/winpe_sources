# I8xMouseEnableTransmission

- ea: `0x14000b72c`
- end: `0x14000b8a2`
- name: `I8xMouseEnableTransmission`
- size: `374`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000c330`
- `0x14001b924`
- `0x14001be20`
- `0x14001e950`

## callees

- `0x140004530`
- `0x1400059c0`
- `0x140007b10`
- `0x14000b72c`
- `0x14000bbf8`

## import_xrefs

- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14000b810`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14000b810`
- `ntoskrnl!KeSetTimerEx` at `0x14000b79a`
- `ntoskrnl!KeSetTimerEx` at `0x14000b79a`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14000b84c`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14000b84c`

## pseudocode

```c
__int64 __fastcall I8xMouseEnableTransmission(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  int v5; // eax
  int v6; // edx
  unsigned int v7; // edi
  char *ErrorLogEntry; // rax
  __int64 v10; // [rsp+28h] [rbp-40h]
  int v11; // [rsp+28h] [rbp-40h]
  __int128 v12; // [rsp+30h] [rbp-38h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      77,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
  if ( *(_BYTE *)(a1 + 930) )
  {
    *(_BYTE *)(a1 + 930) = 0;
    KeSetTimerEx((PKTIMER)(a1 + 864), (LARGE_INTEGER)-50000000LL, 5000, (PKDPC)(a1 + 800));
  }
  LOBYTE(a4) = -12;
  LOBYTE(a3) = 2;
  v5 = I8xPutBytePolled(0, 0, a3, a4);
  v7 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = v5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        17,
        78,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
        v11);
    }
    *(_QWORD *)&v12 = 1;
    *((_QWORD *)&v12 + 1) = 0xF4000000D4LL;
    TraceLoggingEnableTransmissionFailed(v7);
    ErrorLogEntry = (char *)IoAllocateErrorLogEntry(*(PVOID *)a1, 0x40u);
    if ( ErrorLogEntry )
    {
      *((_DWORD *)ErrorLogEntry + 3) = -1073414120;
      *(_DWORD *)ErrorLogEntry = 0x100000;
      *((_QWORD *)ErrorLogEntry + 3) = 0;
      *((_DWORD *)ErrorLogEntry + 4) = 1475;
      *((_DWORD *)ErrorLogEntry + 5) = v7;
      *(_OWORD *)(ErrorLogEntry + 40) = v12;
      IoWriteErrorLogEntry(ErrorLogEntry);
    }
  }
  *(_BYTE *)(a1 + 1015) = 0;
  *(_DWORD *)(a1 + 1000) = 4;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v10) = v7;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      15,
      79,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
      v10);
  }
  return v7;
}

```

## disassembly

```asm
0x14000b72c  push    rbx
0x14000b72e  push    rbp
0x14000b72f  push    rdi
0x14000b730  push    r14
0x14000b732  sub     rsp, 48h
0x14000b736  mov     rbx, rcx
0x14000b739  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000b740  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000b747  lea     r14, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14000b74e  jz      short loc_14000B76F
0x14000b750  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b757  mov     r9d, 4Dh ; 'M'
0x14000b75d  mov     [rsp+68h+var_48], r14
0x14000b762  mov     rcx, [rcx+40h]
0x14000b766  lea     r8d, [r9-3Eh]
0x14000b76a  call    WPP_RECORDER_SF_
0x14000b76f  cmp     byte ptr [rbx+3A2h], 0
0x14000b776  jz      short loc_14000B7A6
0x14000b778  lea     r9, [rbx+320h]; Dpc
0x14000b77f  mov     byte ptr [rbx+3A2h], 0
0x14000b786  lea     rcx, [rbx+360h]; Timer
0x14000b78d  mov     rdx, 0FFFFFFFFFD050F80h; DueTime
0x14000b794  mov     r8d, 1388h; Period
0x14000b79a  call    cs:__imp_KeSetTimerEx
0x14000b7a1  nop     dword ptr [rax+rax+00h]
0x14000b7a6  mov     r9b, 0F4h
0x14000b7a9  mov     r8b, 2
0x14000b7ac  xor     edx, edx
0x14000b7ae  xor     ecx, ecx
0x14000b7b0  call    I8xPutBytePolled
0x14000b7b5  mov     edi, eax
0x14000b7b7  test    eax, eax
0x14000b7b9  jns     loc_14000B858
0x14000b7bf  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000b7c6  jz      short loc_14000B7EB
0x14000b7c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b7cf  mov     r9d, 4Eh ; 'N'
0x14000b7d5  mov     dword ptr [rsp+68h+var_40], eax
0x14000b7d9  mov     [rsp+68h+var_48], r14
0x14000b7de  mov     rcx, [rcx+40h]
0x14000b7e2  lea     r8d, [r9-3Dh]
0x14000b7e6  call    WPP_RECORDER_SF_D
0x14000b7eb  mov     ecx, edi
0x14000b7ed  mov     qword ptr [rsp+68h+var_38], 1
0x14000b7f6  mov     dword ptr [rsp+68h+var_38+8], 0D4h
0x14000b7fe  mov     dword ptr [rsp+68h+var_38+0Ch], 0F4h
0x14000b806  call    TraceLoggingEnableTransmissionFailed
0x14000b80b  mov     rcx, [rbx]; IoObject
0x14000b80e  mov     dl, 40h ; '@'; EntrySize
0x14000b810  call    cs:__imp_IoAllocateErrorLogEntry
0x14000b817  nop     dword ptr [rax+rax+00h]
0x14000b81c  test    rax, rax
0x14000b81f  jz      short loc_14000B858
0x14000b821  movups  xmm0, [rsp+68h+var_38]
0x14000b826  mov     dword ptr [rax+0Ch], 0C0050018h
0x14000b82d  mov     rcx, rax; ElEntry
0x14000b830  mov     dword ptr [rax], 100000h
0x14000b836  mov     qword ptr [rax+18h], 0
0x14000b83e  mov     dword ptr [rax+10h], 5C3h
0x14000b845  mov     [rax+14h], edi
0x14000b848  movups  xmmword ptr [rax+28h], xmm0
0x14000b84c  call    cs:__imp_IoWriteErrorLogEntry
0x14000b853  nop     dword ptr [rax+rax+00h]
0x14000b858  mov     byte ptr [rbx+3F7h], 0
0x14000b85f  mov     dword ptr [rbx+3E8h], 4
0x14000b869  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000b870  jz      short loc_14000B895
0x14000b872  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b879  mov     r9d, 4Fh ; 'O'
0x14000b87f  mov     dword ptr [rsp+68h+var_40], edi
0x14000b883  mov     [rsp+68h+var_48], r14
0x14000b888  mov     rcx, [rcx+40h]
0x14000b88c  lea     r8d, [r9-40h]
0x14000b890  call    WPP_RECORDER_SF_D
0x14000b895  mov     eax, edi
0x14000b897  add     rsp, 48h
0x14000b89b  pop     r14
0x14000b89d  pop     rdi
0x14000b89e  pop     rbp
0x14000b89f  pop     rbx
0x14000b8a0  retn
```
