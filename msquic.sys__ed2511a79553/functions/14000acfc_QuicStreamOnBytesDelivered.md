# QuicStreamOnBytesDelivered

- ea: `0x14000acfc`
- end: `0x14000af22`
- name: `QuicStreamOnBytesDelivered`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000a6f0`

## callees

- `0x14000acfc`
- `0x14000d230`
- `0x14000d490`
- `0x140010820`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14000ae3f`
- `ntoskrnl!_snprintf_s` at `0x14000ae9d`
- `ntoskrnl!_snprintf_s` at `0x14000ae3f`
- `ntoskrnl!_snprintf_s` at `0x14000ae9d`
- `HAL!KeQueryPerformanceCounter` at `0x14000ad9d`
- `HAL!KeQueryPerformanceCounter` at `0x14000ad9d`

## string_xrefs

- `0x14000ae1c`: `Increasing max RX buffer size to %u (MinRtt=%llu; TimeNow=%llu; LastUpdate=%llu)`

## pseudocode

```c
__int64 __fastcall QuicStreamOnBytesDelivered(__int64 a1, __int64 a2)
{
  unsigned __int64 v3; // rsi
  __int64 v4; // rax
  __int64 v5; // rcx
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v7; // rax
  unsigned int v8; // r8d
  __int64 v9; // rdi
  __int64 v10; // r9
  __int64 v11; // r10
  __int64 v12; // rcx
  __int64 result; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  char DstBuf[128]; // [rsp+40h] [rbp-98h] BYREF

  v3 = (unsigned __int64)*(unsigned int *)(a1 + 656) >> 2;
  v4 = *(_QWORD *)(a1 + 72);
  *(_QWORD *)(a1 + 432) += a2;
  *(_QWORD *)(v4 + 3448) += a2;
  *(_QWORD *)(*(_QWORD *)(a1 + 72) + 3480LL) += a2;
  v5 = *(_QWORD *)(a1 + 72);
  if ( *(_QWORD *)(v5 + 3480) >= (unsigned __int64)*(unsigned int *)(v5 + 172) >> 2 )
  {
    *(_QWORD *)(v5 + 3480) = 0;
    QuicSendSetSendFlag(*(_QWORD *)(a1 + 72) + 3416LL, 32);
  }
  if ( *(_QWORD *)(a1 + 432) < v3 )
  {
    result = *(_QWORD *)(a1 + 72);
    if ( (*(_DWORD *)(result + 3488) & 1) == 0 )
      return result;
  }
  else
  {
    PerformanceCounter = KeQueryPerformanceCounter(0);
    v7 = ((__int64 (__fastcall *)(_QWORD))QuicTimePlatToUs64)((LARGE_INTEGER)PerformanceCounter.QuadPart);
    v8 = *(_DWORD *)(a1 + 656);
    v9 = v7;
    if ( v8 )
    {
      v10 = *(_QWORD *)(a1 + 72);
      if ( v8 < *(_DWORD *)(v10 + 172) )
      {
        v11 = *(_QWORD *)(a1 + 440);
        if ( v7 - v11 <= *(_QWORD *)(a1 + 432) * *(_QWORD *)(v10 + 472) / v3 )
        {
          *(_DWORD *)(a1 + 656) = 2 * v8;
          if ( (byte_14005C48D & 1) != 0 )
          {
            _snprintf_s(
              DstBuf,
              0x80u,
              0xFFFFFFFFFFFFFFFFuLL,
              "Increasing max RX buffer size to %u (MinRtt=%llu; TimeNow=%llu; LastUpdate=%llu)",
              4 * v8,
              *(_QWORD *)(v10 + 488),
              v7,
              v11);
            McTemplateU0ps_EtwWriteTransfer(v12, (const EVENT_DESCRIPTOR *)QuicStreamLogVerbose, a1, DstBuf);
          }
        }
      }
    }
    *(_QWORD *)(a1 + 432) = 0;
    *(_QWORD *)(a1 + 440) = v9;
  }
  if ( (byte_14005C48D & 1) != 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Updating flow control window");
    McTemplateU0ps_EtwWriteTransfer(v14, (const EVENT_DESCRIPTOR *)QuicStreamLogVerbose, a1, DstBuf);
  }
  v15 = *(_QWORD *)(a1 + 72) + 3416LL;
  *(_QWORD *)(a1 + 424) = *(_QWORD *)(a1 + 640) + *(unsigned int *)(a1 + 656);
  QuicSendSetSendFlag(v15, 32);
  return QuicSendSetStreamSendFlag(*(_QWORD *)(a1 + 72) + 3416LL, a1, 2);
}

```

## disassembly

```asm
0x14000acfc  mov     [rsp+arg_8], rbx
0x14000ad01  mov     [rsp+arg_10], rbp
0x14000ad06  mov     [rsp+arg_18], rsi
0x14000ad0b  push    rdi
0x14000ad0c  sub     rsp, 0D0h
0x14000ad13  mov     rax, cs:__security_cookie
0x14000ad1a  xor     rax, rsp
0x14000ad1d  mov     [rsp+0D8h+var_18], rax
0x14000ad25  mov     esi, [rcx+290h]
0x14000ad2b  mov     rbx, rcx
0x14000ad2e  mov     rcx, [rcx+1B0h]
0x14000ad35  mov     ebp, 0D58h
0x14000ad3a  add     rcx, rdx
0x14000ad3d  shr     rsi, 2
0x14000ad41  mov     rax, [rbx+48h]
0x14000ad45  mov     [rbx+1B0h], rcx
0x14000ad4c  add     [rax+0D78h], rdx
0x14000ad53  mov     rax, [rbx+48h]
0x14000ad57  add     [rax+0D98h], rdx
0x14000ad5e  mov     rcx, [rbx+48h]
0x14000ad62  mov     eax, [rcx+0ACh]
0x14000ad68  shr     rax, 2
0x14000ad6c  cmp     [rcx+0D98h], rax
0x14000ad73  jb      short loc_14000AD8E
0x14000ad75  and     qword ptr [rcx+0D98h], 0
0x14000ad7d  mov     edx, 20h ; ' '
0x14000ad82  mov     rcx, [rbx+48h]
0x14000ad86  add     rcx, rbp
0x14000ad89  call    QuicSendSetSendFlag
0x14000ad8e  cmp     [rbx+1B0h], rsi
0x14000ad95  jb      loc_14000AE70
0x14000ad9b  xor     ecx, ecx; PerformanceFrequency
0x14000ad9d  call    cs:__imp_KeQueryPerformanceCounter
0x14000ada4  nop     dword ptr [rax+rax+00h]
0x14000ada9  mov     rcx, rax
0x14000adac  call    QuicTimePlatToUs64
0x14000adb1  mov     r8d, [rbx+290h]
0x14000adb8  mov     rdi, rax
0x14000adbb  test    r8d, r8d
0x14000adbe  jz      loc_14000AE5F
0x14000adc4  mov     r9, [rbx+48h]
0x14000adc8  cmp     r8d, [r9+0ACh]
0x14000adcf  jnb     loc_14000AE5F
0x14000add5  mov     rax, [r9+1D8h]
0x14000addc  xor     edx, edx
0x14000adde  imul    rax, [rbx+1B0h]
0x14000ade6  mov     r10, [rbx+1B8h]
0x14000aded  mov     rcx, rdi
0x14000adf0  div     rsi
0x14000adf3  sub     rcx, r10
0x14000adf6  cmp     rcx, rax
0x14000adf9  ja      short loc_14000AE5F
0x14000adfb  lea     ecx, [r8+r8]
0x14000adff  mov     [rbx+290h], ecx
0x14000ae05  test    cs:byte_14005C48D, 1
0x14000ae0c  jz      short loc_14000AE5F
0x14000ae0e  mov     rax, [r9+1E8h]
0x14000ae15  add     ecx, ecx
0x14000ae17  mov     [rsp+0D8h+var_A0], r10
0x14000ae1c  lea     r9, aIncreasingMaxR; "Increasing max RX buffer size to %u (Mi"...
0x14000ae23  mov     [rsp+0D8h+var_A8], rdi
0x14000ae28  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000ae2c  mov     [rsp+0D8h+var_B0], rax
0x14000ae31  mov     edx, 80h; SizeInBytes
0x14000ae36  mov     [rsp+0D8h+var_B8], ecx
0x14000ae3a  lea     rcx, [rsp+0D8h+DstBuf]; DstBuf
0x14000ae3f  call    cs:__imp__snprintf_s
0x14000ae46  nop     dword ptr [rax+rax+00h]
0x14000ae4b  lea     r9, [rsp+0D8h+DstBuf]
0x14000ae50  mov     r8, rbx
0x14000ae53  lea     rdx, QuicStreamLogVerbose
0x14000ae5a  call    McTemplateU0ps_EtwWriteTransfer
0x14000ae5f  and     qword ptr [rbx+1B0h], 0
0x14000ae67  mov     [rbx+1B8h], rdi
0x14000ae6e  jmp     short loc_14000AE7F
0x14000ae70  mov     rax, [rbx+48h]
0x14000ae74  mov     ecx, [rax+0DA0h]
0x14000ae7a  test    cl, 1
0x14000ae7d  jz      short loc_14000AEF8
0x14000ae7f  test    cs:byte_14005C48D, 1
0x14000ae86  jz      short loc_14000AEBD
0x14000ae88  lea     r9, aUpdatingFlowCo; "Updating flow control window"
0x14000ae8f  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000ae93  mov     edx, 80h; SizeInBytes
0x14000ae98  lea     rcx, [rsp+0D8h+DstBuf]; DstBuf
0x14000ae9d  call    cs:__imp__snprintf_s
0x14000aea4  nop     dword ptr [rax+rax+00h]
0x14000aea9  lea     r9, [rsp+0D8h+DstBuf]
0x14000aeae  mov     r8, rbx
0x14000aeb1  lea     rdx, QuicStreamLogVerbose
0x14000aeb8  call    McTemplateU0ps_EtwWriteTransfer
0x14000aebd  mov     eax, [rbx+290h]
0x14000aec3  mov     edx, 20h ; ' '
0x14000aec8  mov     rcx, [rbx+48h]
0x14000aecc  add     rax, [rbx+280h]
0x14000aed3  add     rcx, rbp
0x14000aed6  mov     [rbx+1A8h], rax
0x14000aedd  call    QuicSendSetSendFlag
0x14000aee2  mov     rcx, [rbx+48h]
0x14000aee6  xor     r9d, r9d
0x14000aee9  add     rcx, rbp
0x14000aeec  mov     rdx, rbx
0x14000aeef  lea     r8d, [r9+2]
0x14000aef3  call    QuicSendSetStreamSendFlag
0x14000aef8  mov     rcx, [rsp+0D8h+var_18]
0x14000af00  xor     rcx, rsp; StackCookie
0x14000af03  call    __security_check_cookie
0x14000af08  lea     r11, [rsp+0D8h+var_8]
0x14000af10  mov     rbx, [r11+18h]
0x14000af14  mov     rbp, [r11+20h]
0x14000af18  mov     rsi, [r11+28h]
0x14000af1c  mov     rsp, r11
0x14000af1f  pop     rdi
0x14000af20  retn
```
