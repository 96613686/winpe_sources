# QuicListenerStopComplete

- ea: `0x14002be60`
- end: `0x14002bfd0`
- name: `QuicListenerStopComplete`
- size: `368`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002bdf0`

## callees

- `0x140003348`
- `0x1400291f0`
- `0x14002bc40`
- `0x14002be60`
- `0x14003c8e0`
- `0x14003ead8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14002bf32`
- `ntoskrnl!_snprintf_s` at `0x14002bf32`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bead`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bead`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002bf4f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002bf4f`
- `ntoskrnl!KeSetEvent` at `0x14002bf96`
- `ntoskrnl!KeSetEvent` at `0x14002bf96`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14002bf7a`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14002bf7a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14002bf01`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14002bf01`

## string_xrefs

- `0x14002bf1d`: `[list][%p] Indicating STOP_COMPLETE`

## pseudocode

```c
LONG __fastcall QuicListenerStopComplete(char *P, char a2)
{
  void *v4; // rcx
  char v5; // cl
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rcx
  char v9; // bl
  LONG result; // eax
  _DWORD v11[8]; // [rsp+30h] [rbp-B8h] BYREF
  char DstBuf[128]; // [rsp+50h] [rbp-98h] BYREF

  if ( (byte_14005C489 & 0x10) != 0 )
    McTemplateU0p_EtwWriteTransfer(P, QuicListenerStopped);
  v4 = (void *)*((_QWORD *)P + 23);
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0x30316351u);
    *((_QWORD *)P + 23) = 0;
  }
  if ( a2 )
  {
    v5 = P[17] & 1;
    v11[0] = 1;
    *(_OWORD *)&v11[1] = 0;
    LOBYTE(v11[2]) = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4)) & 0xFE | v5;
    v6 = *((_QWORD *)P + 9);
    if ( v6 )
      v7 = PsAttachSiloToCurrentThread(v6);
    else
      v7 = -1;
    if ( byte_14005C48E < 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[list][%p] Indicating STOP_COMPLETE", P);
      McTemplateU0s_EtwWriteTransfer(v8, QuicLogVerbose, DstBuf);
    }
    *((_QWORD *)P + 3) = PsGetCurrentThreadId();
    QuicListenerIndicateEvent(P, v11);
    *((_QWORD *)P + 3) = 0;
    if ( v7 != -1 )
      PsDetachSiloFromCurrentThread(v7);
  }
  v9 = P[19];
  P[18] = 1;
  result = KeSetEvent((PRKEVENT)(P + 88), 0, 0);
  if ( v9 )
    return QuicListenerFree(P);
  return result;
}

```

## disassembly

```asm
0x14002be60  mov     [rsp+arg_8], rbx
0x14002be65  push    rdi
0x14002be66  sub     rsp, 0E0h
0x14002be6d  mov     rax, cs:__security_cookie
0x14002be74  xor     rax, rsp
0x14002be77  mov     [rsp+0E8h+var_18], rax
0x14002be7f  test    cs:byte_14005C489, 10h
0x14002be86  mov     bl, dl
0x14002be88  mov     rdi, rcx
0x14002be8b  jz      short loc_14002BE9C
0x14002be8d  mov     r8, rcx
0x14002be90  lea     rdx, QuicListenerStopped
0x14002be97  call    McTemplateU0p_EtwWriteTransfer
0x14002be9c  mov     rcx, [rdi+0B8h]; P
0x14002bea3  test    rcx, rcx
0x14002bea6  jz      short loc_14002BEC1
0x14002bea8  mov     edx, 30316351h; Tag
0x14002bead  call    cs:__imp_ExFreePoolWithTag
0x14002beb4  nop     dword ptr [rax+rax+00h]
0x14002beb9  and     qword ptr [rdi+0B8h], 0
0x14002bec1  test    bl, bl
0x14002bec3  jz      loc_14002BF86
0x14002bec9  mov     cl, [rdi+11h]
0x14002becc  xorps   xmm0, xmm0
0x14002becf  and     cl, 1
0x14002bed2  mov     qword ptr [rsp+0E8h+var_B8], 1
0x14002bedb  movdqu  xmmword ptr [rsp+0E8h+var_B8+4], xmm0
0x14002bee1  psrldq  xmm0, 4
0x14002bee6  movd    eax, xmm0
0x14002beea  and     al, 0FEh
0x14002beec  or      cl, al
0x14002beee  mov     [rsp+0E8h+var_B8+8], cl
0x14002bef2  mov     rcx, [rdi+48h]
0x14002bef6  test    rcx, rcx
0x14002bef9  jnz     short loc_14002BF01
0x14002befb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14002beff  jmp     short loc_14002BF10
0x14002bf01  call    cs:__imp_PsAttachSiloToCurrentThread
0x14002bf08  nop     dword ptr [rax+rax+00h]
0x14002bf0d  mov     rbx, rax
0x14002bf10  mov     edx, 80h; SizeInBytes
0x14002bf15  test    cs:byte_14005C48E, dl
0x14002bf1b  jz      short loc_14002BF4F
0x14002bf1d  lea     r9, aListPIndicatin_0; "[list][%p] Indicating STOP_COMPLETE"
0x14002bf24  mov     [rsp+0E8h+var_C8], rdi
0x14002bf29  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002bf2d  lea     rcx, [rsp+0E8h+DstBuf]; DstBuf
0x14002bf32  call    cs:__imp__snprintf_s
0x14002bf39  nop     dword ptr [rax+rax+00h]
0x14002bf3e  lea     r8, [rsp+0E8h+DstBuf]
0x14002bf43  lea     rdx, QuicLogVerbose
0x14002bf4a  call    McTemplateU0s_EtwWriteTransfer
0x14002bf4f  call    cs:__imp_PsGetCurrentThreadId
0x14002bf56  nop     dword ptr [rax+rax+00h]
0x14002bf5b  lea     rdx, [rsp+0E8h+var_B8]
0x14002bf60  mov     rcx, rdi
0x14002bf63  mov     [rdi+18h], rax
0x14002bf67  call    QuicListenerIndicateEvent
0x14002bf6c  and     qword ptr [rdi+18h], 0
0x14002bf71  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14002bf75  jz      short loc_14002BF86
0x14002bf77  mov     rcx, rbx
0x14002bf7a  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14002bf81  nop     dword ptr [rax+rax+00h]
0x14002bf86  mov     bl, [rdi+13h]
0x14002bf89  lea     rcx, [rdi+58h]; Event
0x14002bf8d  xor     r8d, r8d; Wait
0x14002bf90  mov     byte ptr [rdi+12h], 1
0x14002bf94  xor     edx, edx; Increment
0x14002bf96  call    cs:__imp_KeSetEvent
0x14002bf9d  nop     dword ptr [rax+rax+00h]
0x14002bfa2  test    bl, bl
0x14002bfa4  jz      short loc_14002BFAE
0x14002bfa6  mov     rcx, rdi; P
0x14002bfa9  call    QuicListenerFree
0x14002bfae  mov     rcx, [rsp+0E8h+var_18]
0x14002bfb6  xor     rcx, rsp; StackCookie
0x14002bfb9  call    __security_check_cookie
0x14002bfbe  mov     rbx, [rsp+0E8h+arg_8]
0x14002bfc6  add     rsp, 0E0h
0x14002bfcd  pop     rdi
0x14002bfce  retn
```
