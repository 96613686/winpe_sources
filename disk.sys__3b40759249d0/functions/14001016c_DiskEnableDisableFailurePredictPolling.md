# DiskEnableDisableFailurePredictPolling

- ea: `0x14001016c`
- end: `0x1400101bc`
- name: `DiskEnableDisableFailurePredictPolling`
- size: `80`
- prototype: `__int64 __fastcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000e510`
- `0x140010490`
- `0x140014b00`

## callees

- `0x14001016c`
- `0x140014d90`

## import_xrefs

- `CLASSPNP!ClassSetFailurePredictionPoll` at `0x14001019f`
- `CLASSPNP!ClassSetFailurePredictionPoll` at `0x14001019f`

## pseudocode

```c
NTSTATUS __fastcall DiskEnableDisableFailurePredictPolling(
        PFUNCTIONAL_DEVICE_EXTENSION FdoExtension,
        __int64 a2,
        __int64 a3)
{
  ULONG v3; // esi
  PVOID DriverData; // rdi
  NTSTATUS result; // eax
  FAILURE_PREDICTION_METHOD v7; // edx

  v3 = a3;
  if ( (_BYTE)a2 )
  {
    DriverData = FdoExtension->CommonExtension.DriverData;
    result = DiskEnableDisableFailurePrediction(FdoExtension, a2, a3);
    if ( result < 0 )
      return result;
    v7 = *((_DWORD *)DriverData + 4);
  }
  else
  {
    v7 = FailurePredictionNone;
  }
  return ClassSetFailurePredictionPoll(FdoExtension, v7, v3);
}

```

## disassembly

```asm
0x14001016c  mov     [rsp+arg_0], rbx
0x140010171  mov     [rsp+arg_8], rsi
0x140010176  push    rdi
0x140010177  sub     rsp, 20h
0x14001017b  mov     esi, r8d
0x14001017e  mov     rbx, rcx
0x140010181  test    dl, dl
0x140010183  jz      short loc_140010197
0x140010185  mov     rdi, [rcx+60h]
0x140010189  call    DiskEnableDisableFailurePrediction
0x14001018e  test    eax, eax
0x140010190  js      short loc_1400101AB
0x140010192  mov     edx, [rdi+10h]
0x140010195  jmp     short loc_140010199
0x140010197  xor     edx, edx; FailurePredictionMethod
0x140010199  mov     r8d, esi; PollingPeriod
0x14001019c  mov     rcx, rbx; FdoExtension
0x14001019f  call    cs:__imp_ClassSetFailurePredictionPoll
0x1400101a6  nop     dword ptr [rax+rax+00h]
0x1400101ab  mov     rbx, [rsp+28h+arg_0]
0x1400101b0  mov     rsi, [rsp+28h+arg_8]
0x1400101b5  add     rsp, 20h
0x1400101b9  pop     rdi
0x1400101ba  retn
```
