# QuicConnTryClose

- ea: `0x14001c664`
- end: `0x14001ca6f`
- name: `QuicConnTryClose`
- size: `1035`
- prototype: ``
- caller_count: `12`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1400108c0`
- `0x140014d80`
- `0x140015480`
- `0x140017580`
- `0x14001be88`
- `0x14001c52c`
- `0x14001c5b8`
- `0x14001c638`
- `0x140021e20`
- `0x14002f0ec`
- `0x14002f204`
- `0x140042e10`

## callees

- `0x14000d490`
- `0x14000d7a0`
- `0x14000f370`
- `0x14001c440`
- `0x14001c664`
- `0x14001ca78`
- `0x14001cb14`
- `0x14001d404`
- `0x14001ddac`
- `0x140029ef0`
- `0x140030168`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ec10`
- `0x14003ed00`
- `0x14004275c`
- `0x14004290c`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14001c730`
- `ntoskrnl!_snprintf_s` at `0x14001c9c5`
- `ntoskrnl!_snprintf_s` at `0x14001c730`
- `ntoskrnl!_snprintf_s` at `0x14001c9c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c8ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c8ad`
- `ntoskrnl!ExAllocatePool2` at `0x14001c8da`
- `ntoskrnl!ExAllocatePool2` at `0x14001c8da`

## string_xrefs

- `0x14001c9b0`: `Connection close complete`

## pseudocode

```c
char __fastcall QuicConnTryClose(__int64 a1, char a2, __int64 a3, const void *a4, unsigned __int16 a5)
{
  int v6; // r15d
  char v9; // r13
  char v10; // si
  char v11; // al
  char v12; // cl
  char result; // al
  bool v14; // zf
  __int64 v15; // rcx
  char v16; // al
  unsigned __int64 v17; // r8
  __int64 v18; // rdx
  void *v19; // rcx
  void *Pool2; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned __int64 v24; // r8
  char DstBuf[128]; // [rsp+40h] [rbp-C8h] BYREF

  v6 = a2 & 8;
  v9 = v6 != 0;
  v10 = a2 & 1;
  v11 = *(_BYTE *)(a1 + 248) & 0xBF;
  v12 = v11 | ((a2 & 1) << 6);
  *(_BYTE *)(a1 + 248) = v12;
  if ( (a2 & 8) == 0 )
    goto LABEL_5;
  if ( (v11 & 0x20) == 0 )
  {
    if ( (a2 & 8) != 0 )
    {
      *(_BYTE *)(a1 + 248) = v12 | 0x20;
      goto LABEL_14;
    }
LABEL_5:
    result = v11 & 0x10;
    if ( (v12 & 0x10) != 0 )
      goto LABEL_6;
    *(_BYTE *)(a1 + 248) = v12 | 0x10;
    if ( (*(_BYTE *)(a1 + 249) & 0x20) == 0 )
    {
      if ( (byte_14005C48C & 1) != 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Abandoning internal, closed connection");
        McTemplateU0ps_EtwWriteTransfer(v15, QuicConnLogVerbose, a1, DstBuf);
      }
      *(_BYTE *)(a1 + 251) |= 1u;
    }
LABEL_14:
    v16 = *(_BYTE *)(a1 + 248);
    if ( v6 )
    {
      if ( (v16 & 0x10) == 0 )
      {
        if ( (v16 & 8) == 0 && (unsigned __int8)QuicConnIsClient(a1) )
        {
          v10 = 1;
LABEL_27:
          *(_BYTE *)(a1 + 250) |= 0x80u;
          QuicConnTimerCancel(a1, 4);
          if ( (a2 & 0x10) != 0 )
          {
            *(_DWORD *)(a1 + 1588) = a3;
            *(_QWORD *)(a1 + 1592) = 1;
          }
          else
          {
            *(_DWORD *)(a1 + 1588) = QuicErrorCodeToStatus(a3);
            *(_QWORD *)(a1 + 1592) = a3;
            if ( (unsigned __int64)(a3 - 3) <= 0xC )
              _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(a1 + 72) + 2256LL));
          }
          if ( (a2 & 4) != 0 )
            *(_BYTE *)(a1 + 248) |= 0x80u;
          if ( (a2 & 2) != 0 && (*(_BYTE *)(a1 + 249) & 0x20) != 0 )
            QuicConnIndicateShutdownBegin(a1);
          v19 = *(void **)(a1 + 1600);
          if ( v19 )
          {
            ExFreePoolWithTag(v19, 0x35336351u);
            *(_QWORD *)(a1 + 1600) = 0;
          }
          if ( a5 )
          {
            Pool2 = (void *)ExAllocatePool2(66, (unsigned int)a5 + 1, 892560209);
            *(_QWORD *)(a1 + 1600) = Pool2;
            if ( Pool2 )
            {
              memmove(Pool2, a4, a5);
              *(_BYTE *)(a5 + *(_QWORD *)(a1 + 1600)) = 0;
            }
            else if ( (Microsoft_QuicEnableBits & 2) != 0 )
            {
              McTemplateU0sx_EtwWriteTransfer(v19, v21, "close reason", (unsigned int)a5 + 1);
            }
          }
          if ( (*(_BYTE *)(a1 + 248) & 4) != 0 )
            QuicConnLogStatistics(a1);
          if ( (a2 & 4) != 0 )
          {
            if ( (byte_14005C489 & 0x40) != 0 )
              McTemplateU0pxu_EtwWriteTransfer((_DWORD)v19, (unsigned int)QuicConnAppShutdown, a1, a3, v9);
          }
          else if ( (byte_14005C489 & 0x40) != 0 )
          {
            McTemplateU0pxuu_EtwWriteTransfer(
              (_DWORD)v19,
              (unsigned int)QuicConnTransportShutdown,
              a1,
              a3,
              v9,
              (a2 & 0x10) != 0);
          }
          QuicStreamSetShutdown(a1 + 2032);
          QuicDatagramSendShutdown(a1 + 3552);
          goto LABEL_58;
        }
        if ( v10 )
          goto LABEL_27;
        v17 = 2LL * *(_QWORD *)(a1 + 472);
        if ( v17 < 0x3A98 )
          v17 = 15000;
        QuicConnTimerSet(a1, 5, v17);
        v18 = 4;
LABEL_26:
        QuicSendSetSendFlag(a1 + 3416, v18);
        goto LABEL_27;
      }
    }
    else if ( (v16 & 0x20) == 0 )
    {
      if ( v10 )
        goto LABEL_27;
      QuicConnTimerSet(
        a1,
        5,
        3 * (*(_QWORD *)(a1 + 472) + 4 * (*(_QWORD *)(a1 + 504) + 250LL * *(_QWORD *)(a1 + 1704))));
      v18 = (a2 & 4) != 0 ? 8 : 4;
      goto LABEL_26;
    }
    if ( byte_14005C48B < 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Connection close complete");
      McTemplateU0ps_EtwWriteTransfer(v22, QuicConnLogInfo, a1, DstBuf);
    }
    if ( !(unsigned __int8)QuicConnIsClient(a1) )
    {
      if ( v10 )
        goto LABEL_59;
      v24 = 2LL * *(_QWORD *)(a1 + 472);
      if ( v24 < 0x3A98 )
        v24 = 15000;
      QuicConnTimerSet(v23, 5, v24);
    }
LABEL_58:
    if ( !v10 )
    {
      result = *(_BYTE *)(a1 + 248) & 0x30;
      v14 = result == 48;
LABEL_61:
      if ( !v14 )
        return result;
      goto LABEL_62;
    }
LABEL_59:
    result = QuicSendClear(a1 + 3416);
LABEL_62:
    *(_BYTE *)(a1 + 250) &= ~0x80u;
    *(_BYTE *)(a1 + 251) |= 1u;
    return result;
  }
  result = v11 & 0x10;
LABEL_6:
  if ( v10 && result )
  {
    v14 = (v12 & 0x20) == 0;
    goto LABEL_61;
  }
  return result;
}

```

## disassembly

```asm
0x14001c664  mov     [rsp+arg_8], rbx
0x14001c669  push    rbp
0x14001c66a  push    rsi
0x14001c66b  push    rdi
0x14001c66c  push    r12
0x14001c66e  push    r13
0x14001c670  push    r14
0x14001c672  push    r15
0x14001c674  sub     rsp, 0D0h
0x14001c67b  mov     rax, cs:__security_cookie
0x14001c682  xor     rax, rsp
0x14001c685  mov     [rsp+108h+var_48], rax
0x14001c68d  movzx   r12d, [rsp+108h+arg_20]
0x14001c696  mov     rdi, rcx
0x14001c699  mov     r15d, edx
0x14001c69c  mov     [rsp+108h+Src], r9
0x14001c6a1  and     r15d, 8
0x14001c6a5  mov     esi, edx
0x14001c6a7  mov     r14, r8
0x14001c6aa  mov     ebp, edx
0x14001c6ac  mov     al, [rdi+0F8h]
0x14001c6b2  setnz   r13b
0x14001c6b6  and     esi, 1
0x14001c6b9  and     al, 0BFh
0x14001c6bb  mov     cl, sil
0x14001c6be  mov     r8b, 20h ; ' '
0x14001c6c1  shl     cl, 6
0x14001c6c4  or      cl, al
0x14001c6c6  mov     [rdi+0F8h], cl
0x14001c6cc  test    r15d, r15d
0x14001c6cf  jz      short loc_14001C6E1
0x14001c6d1  test    r8b, cl
0x14001c6d4  jz      short loc_14001C6DC
0x14001c6d6  mov     al, cl
0x14001c6d8  and     al, 10h
0x14001c6da  jmp     short loc_14001C6E7
0x14001c6dc  test    r15d, r15d
0x14001c6df  jnz     short loc_14001C75C
0x14001c6e1  mov     al, cl
0x14001c6e3  and     al, 10h
0x14001c6e5  jz      short loc_14001C700
0x14001c6e7  test    sil, sil
0x14001c6ea  jz      loc_14001CA43
0x14001c6f0  test    al, al
0x14001c6f2  jz      loc_14001CA43
0x14001c6f8  test    r8b, cl
0x14001c6fb  jmp     loc_14001CA33
0x14001c700  or      cl, 10h
0x14001c703  mov     [rdi+0F8h], cl
0x14001c709  test    [rdi+0F9h], r8b
0x14001c710  jnz     short loc_14001C765
0x14001c712  test    cs:byte_14005C48C, 1
0x14001c719  jz      short loc_14001C753
0x14001c71b  lea     r9, aAbandoningInte; "Abandoning internal, closed connection"
0x14001c722  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001c726  mov     edx, 80h; SizeInBytes
0x14001c72b  lea     rcx, [rsp+108h+DstBuf]; DstBuf
0x14001c730  call    cs:__imp__snprintf_s
0x14001c737  nop     dword ptr [rax+rax+00h]
0x14001c73c  lea     r9, [rsp+108h+DstBuf]
0x14001c741  mov     r8, rdi
0x14001c744  lea     rdx, QuicConnLogVerbose
0x14001c74b  call    McTemplateU0ps_EtwWriteTransfer
0x14001c750  mov     r8b, 20h ; ' '
0x14001c753  or      byte ptr [rdi+0FBh], 1
0x14001c75a  jmp     short loc_14001C765
0x14001c75c  or      cl, r8b
0x14001c75f  mov     [rdi+0F8h], cl
0x14001c765  mov     al, [rdi+0F8h]
0x14001c76b  mov     ebx, ebp
0x14001c76d  and     ebx, 10h
0x14001c770  test    r15d, r15d
0x14001c773  jz      short loc_14001C7C8
0x14001c775  test    al, 10h
0x14001c777  jnz     loc_14001C9A6
0x14001c77d  test    al, 8
0x14001c77f  jnz     short loc_14001C795
0x14001c781  mov     rcx, rdi
0x14001c784  call    QuicConnIsClient
0x14001c789  test    al, al
0x14001c78b  jz      short loc_14001C795
0x14001c78d  mov     sil, 1
0x14001c790  jmp     loc_14001C81E
0x14001c795  test    sil, sil
0x14001c798  jnz     loc_14001C81E
0x14001c79e  mov     r8, [rdi+1D8h]
0x14001c7a5  mov     eax, 3A98h
0x14001c7aa  add     r8, r8
0x14001c7ad  mov     edx, 5
0x14001c7b2  cmp     r8, rax
0x14001c7b5  mov     rcx, rdi
0x14001c7b8  cmovb   r8, rax
0x14001c7bc  call    QuicConnTimerSet
0x14001c7c1  mov     edx, 4
0x14001c7c6  jmp     short loc_14001C812
0x14001c7c8  test    r8b, al
0x14001c7cb  jnz     loc_14001C9A6
0x14001c7d1  test    sil, sil
0x14001c7d4  jnz     short loc_14001C81E
0x14001c7d6  imul    rcx, [rdi+6A8h], 0FAh
0x14001c7e1  mov     rax, [rdi+1D8h]
0x14001c7e8  mov     edx, 5
0x14001c7ed  add     rcx, [rdi+1F8h]
0x14001c7f4  lea     rcx, [rax+rcx*4]
0x14001c7f8  lea     r8, [rcx+rcx*2]
0x14001c7fc  mov     rcx, rdi
0x14001c7ff  call    QuicConnTimerSet
0x14001c804  mov     eax, ebp
0x14001c806  and     al, 4
0x14001c808  neg     al
0x14001c80a  sbb     edx, edx
0x14001c80c  and     edx, 4
0x14001c80f  add     edx, 4
0x14001c812  lea     rcx, [rdi+0D58h]
0x14001c819  call    QuicSendSetSendFlag
0x14001c81e  or      byte ptr [rdi+0FAh], 80h
0x14001c825  mov     edx, 4
0x14001c82a  mov     rcx, rdi
0x14001c82d  call    QuicConnTimerCancel
0x14001c832  xor     r15d, r15d
0x14001c835  test    ebx, ebx
0x14001c837  jz      short loc_14001C84D
0x14001c839  mov     [rdi+634h], r14d
0x14001c840  mov     qword ptr [rdi+638h], 1
0x14001c84b  jmp     short loc_14001C878
0x14001c84d  mov     rcx, r14
0x14001c850  call    QuicErrorCodeToStatus
0x14001c855  mov     [rdi+634h], eax
0x14001c85b  lea     rax, [r14-3]
0x14001c85f  mov     [rdi+638h], r14
0x14001c866  cmp     rax, 0Ch
0x14001c86a  ja      short loc_14001C878
0x14001c86c  mov     rax, [rdi+48h]
0x14001c870  lock inc qword ptr [rax+8D0h]
0x14001c878  test    bpl, 4
0x14001c87c  jz      short loc_14001C885
0x14001c87e  or      byte ptr [rdi+0F8h], 80h
0x14001c885  test    bpl, 2
0x14001c889  jz      short loc_14001C89C
0x14001c88b  test    byte ptr [rdi+0F9h], 20h
0x14001c892  jz      short loc_14001C89C
0x14001c894  mov     rcx, rdi
0x14001c897  call    QuicConnIndicateShutdownBegin
0x14001c89c  mov     rcx, [rdi+640h]; P
0x14001c8a3  test    rcx, rcx
0x14001c8a6  jz      short loc_14001C8C0
0x14001c8a8  mov     edx, 35336351h; Tag
0x14001c8ad  call    cs:__imp_ExFreePoolWithTag
0x14001c8b4  nop     dword ptr [rax+rax+00h]
0x14001c8b9  mov     [rdi+640h], r15
0x14001c8c0  test    r12w, r12w
0x14001c8c4  jz      short loc_14001C927
0x14001c8c6  lea     eax, [r12+1]
0x14001c8cb  mov     r8d, 35336351h
0x14001c8d1  mov     edx, eax
0x14001c8d3  mov     ecx, 42h ; 'B'
0x14001c8d8  mov     ebx, eax
0x14001c8da  call    cs:__imp_ExAllocatePool2
0x14001c8e1  nop     dword ptr [rax+rax+00h]
0x14001c8e6  mov     [rdi+640h], rax
0x14001c8ed  test    rax, rax
0x14001c8f0  jz      short loc_14001C90F
0x14001c8f2  mov     rdx, [rsp+108h+Src]; Src
0x14001c8f7  mov     r8, r12; Size
0x14001c8fa  mov     rcx, rax; void *
0x14001c8fd  call    memmove
0x14001c902  mov     rax, [rdi+640h]
0x14001c909  mov     [r12+rax], r15b
0x14001c90d  jmp     short loc_14001C927
0x14001c90f  test    cs:Microsoft_QuicEnableBits, 2
0x14001c916  jz      short loc_14001C927
0x14001c918  mov     r9, rbx
0x14001c91b  lea     r8, aCloseReason; "close reason"
0x14001c922  call    McTemplateU0sx_EtwWriteTransfer
0x14001c927  test    byte ptr [rdi+0F8h], 4
0x14001c92e  jz      short loc_14001C938
0x14001c930  mov     rcx, rdi
0x14001c933  call    QuicConnLogStatistics
0x14001c938  test    bpl, 4
0x14001c93c  jz      short loc_14001C960
0x14001c93e  test    cs:byte_14005C489, 40h
0x14001c945  jz      short loc_14001C98C
0x14001c947  mov     r9, r14
0x14001c94a  mov     [rsp+108h+var_E8], r13b
0x14001c94f  mov     r8, rdi
0x14001c952  lea     rdx, QuicConnAppShutdown
0x14001c959  call    McTemplateU0pxu_EtwWriteTransfer
0x14001c95e  jmp     short loc_14001C98C
0x14001c960  test    cs:byte_14005C489, 40h
0x14001c967  jz      short loc_14001C98C
0x14001c969  shr     ebp, 4
0x14001c96c  lea     rdx, QuicConnTransportShutdown
0x14001c973  and     bpl, 1
0x14001c977  mov     r9, r14
0x14001c97a  mov     [rsp+108h+var_E0], bpl
0x14001c97f  mov     r8, rdi
0x14001c982  mov     [rsp+108h+var_E8], r13b
0x14001c987  call    McTemplateU0pxuu_EtwWriteTransfer
0x14001c98c  lea     rcx, [rdi+7F0h]
0x14001c993  call    QuicStreamSetShutdown
0x14001c998  lea     rcx, [rdi+0DE0h]
0x14001c99f  call    QuicDatagramSendShutdown
0x14001c9a4  jmp     short loc_14001CA16
0x14001c9a6  mov     al, cs:byte_14005C48B
0x14001c9ac  test    al, al
0x14001c9ae  jns     short loc_14001C9E5
0x14001c9b0  lea     r9, aConnectionClos; "Connection close complete"
0x14001c9b7  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001c9bb  mov     edx, 80h; SizeInBytes
0x14001c9c0  lea     rcx, [rsp+108h+DstBuf]; DstBuf
0x14001c9c5  call    cs:__imp__snprintf_s
0x14001c9cc  nop     dword ptr [rax+rax+00h]
0x14001c9d1  lea     r9, [rsp+108h+DstBuf]
0x14001c9d6  mov     r8, rdi
0x14001c9d9  lea     rdx, QuicConnLogInfo
0x14001c9e0  call    McTemplateU0ps_EtwWriteTransfer
0x14001c9e5  mov     rcx, rdi
0x14001c9e8  call    QuicConnIsClient
0x14001c9ed  test    al, al
0x14001c9ef  jnz     short loc_14001CA16
0x14001c9f1  test    sil, sil
0x14001c9f4  jnz     short loc_14001CA1B
0x14001c9f6  mov     r8, [rdi+1D8h]
0x14001c9fd  mov     eax, 3A98h
0x14001ca02  add     r8, r8
0x14001ca05  mov     edx, 5
0x14001ca0a  cmp     r8, rax
0x14001ca0d  cmovb   r8, rax
0x14001ca11  call    QuicConnTimerSet
0x14001ca16  test    sil, sil
0x14001ca19  jz      short loc_14001CA29
0x14001ca1b  lea     rcx, [rdi+0D58h]
0x14001ca22  call    QuicSendClear
0x14001ca27  jmp     short loc_14001CA35
0x14001ca29  mov     al, [rdi+0F8h]
0x14001ca2f  and     al, 30h
0x14001ca31  cmp     al, 30h ; '0'
0x14001ca33  jnz     short loc_14001CA43
0x14001ca35  and     byte ptr [rdi+0FAh], 7Fh
0x14001ca3c  or      byte ptr [rdi+0FBh], 1
0x14001ca43  mov     rcx, [rsp+108h+var_48]
0x14001ca4b  xor     rcx, rsp; StackCookie
0x14001ca4e  call    __security_check_cookie
0x14001ca53  mov     rbx, [rsp+108h+arg_8]
0x14001ca5b  add     rsp, 0D0h
0x14001ca62  pop     r15
0x14001ca64  pop     r14
0x14001ca66  pop     r13
0x14001ca68  pop     r12
0x14001ca6a  pop     rdi
0x14001ca6b  pop     rsi
0x14001ca6c  pop     rbp
0x14001ca6d  retn
```
