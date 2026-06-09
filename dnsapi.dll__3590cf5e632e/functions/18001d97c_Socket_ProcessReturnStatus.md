# Socket_ProcessReturnStatus

- ea: `0x18001d97c`
- end: `0x18001dbf2`
- name: `Socket_ProcessReturnStatus`
- size: `630`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001cc18`

## callees

- `0x18001d97c`
- `0x18001f03c`
- `0x180021490`
- `0x180053ce0`
- `0x1800dc9e0`
- `0x1800ddfa8`
- `0x1800de650`
- `0x1800dfa80`
- `0x1800dfdc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dad1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dad1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d9f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001daa5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d9f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001daa5`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001db2c`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001db2c`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x18001db98`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x18001db98`

## pseudocode

```c
__int64 __fastcall Socket_ProcessReturnStatus(_QWORD *lpMem, unsigned int a2)
{
  __int64 v2; // rbx
  unsigned int v3; // edi
  int v5; // r13d
  char v6; // al
  int v7; // r14d
  struct _RTL_CRITICAL_SECTION *v8; // rcx
  __int64 v10; // rdx
  struct _TP_CALLBACK_INSTANCE *v11; // rbp
  __int64 v12; // r8
  struct _TP_CALLBACK_INSTANCE *v13; // rax
  int v14; // r12d
  __int64 v15; // rax
  struct _TP_IO *v16; // rcx

  v2 = lpMem[11];
  v3 = a2;
  v5 = 0;
  v6 = BYTE1(xmmword_1801119E0);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    WPP_SF_qD(1035, 128, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, lpMem, a2);
    v6 = BYTE1(xmmword_1801119E0);
  }
  if ( *(_DWORD *)(v2 + 580) )
  {
    if ( (v6 & 8) != 0 )
    {
      v10 = 129;
LABEL_21:
      WPP_SF_(1035, v10, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids);
    }
LABEL_9:
    v8 = (struct _RTL_CRITICAL_SECTION *)(v2 + 528);
    goto LABEL_10;
  }
  if ( (*(_DWORD *)(v2 + 520) & 0x200) != 0 || *((_DWORD *)lpMem + 108) )
  {
    if ( (v6 & 8) != 0 )
    {
      v10 = 130;
      goto LABEL_21;
    }
    goto LABEL_9;
  }
  v7 = 997;
  if ( v3 == 997 )
  {
    if ( (v6 & 8) != 0 )
      WPP_SF_q(1035, 131, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, v2);
    goto LABEL_9;
  }
  if ( !v3 )
  {
    if ( (v6 & 8) != 0 )
      WPP_SF_q(1035, 134, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, v2);
    v3 = 997;
    goto LABEL_9;
  }
  v11 = 0;
  if ( (v6 & 8) != 0 )
    WPP_SF_d(1035, 132, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, v3);
  v12 = *(unsigned __int8 *)(v2 + 648);
  *(_BYTE *)(v2 + 658) = 0;
  Trace_LogRecvEvent(v2, v3, v12);
  *(_DWORD *)(v2 + 524) |= 8u;
  v13 = *(struct _TP_CALLBACK_INSTANCE **)(v2 + 456);
  *(_DWORD *)(v2 + 520) &= ~0x80u;
  v14 = *(_DWORD *)(v2 + 524);
  if ( v13 )
  {
    v11 = v13;
    *(_QWORD *)(v2 + 456) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 528));
  if ( v11 )
    DisassociateCurrentThreadFromCallback(v11);
  if ( (v14 & 0x10) != 0 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_qq(1035, 133, (unsigned int)WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, v2, *(_QWORD *)(v2 + 496));
    v16 = *(struct _TP_IO **)(v2 + 496);
    if ( v16 )
      CancelThreadpoolIo(v16);
    v5 = 1;
  }
  ThreadPool_WaitForTimer(*(PTP_TIMER *)(v2 + 512), 0);
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 528));
  v8 = (struct _RTL_CRITICAL_SECTION *)(v2 + 528);
  v15 = *(_QWORD *)(v2 + 216);
  if ( (*(_DWORD *)(v2 + 520) & 0x200) == 0 )
    v7 = v3;
  *(_DWORD *)(v2 + 572) = 0;
  v3 = v7;
  *(_QWORD *)(v2 + 48) = v15;
LABEL_10:
  LeaveCriticalSection(v8);
  DeRefSendBlob(lpMem);
  if ( v5 )
    DeRefSendBlob(lpMem);
  return v3;
}

```

## disassembly

```asm
0x18001d97c  push    rbx
0x18001d97e  push    rbp
0x18001d97f  push    rsi
0x18001d980  push    rdi
0x18001d981  push    r12
0x18001d983  push    r13
0x18001d985  push    r14
0x18001d987  push    r15
0x18001d989  sub     rsp, 38h
0x18001d98d  mov     rbx, [rcx+58h]
0x18001d991  mov     edi, edx
0x18001d993  mov     rsi, rcx
0x18001d996  xor     r13d, r13d
0x18001d999  mov     al, byte ptr cs:xmmword_1801119E0+1
0x18001d99f  lea     r15d, [r13+8]
0x18001d9a3  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x18001d9aa  mov     ecx, 40Bh
0x18001d9af  test    r15b, al
0x18001d9b2  jnz     loc_18001DB3A
0x18001d9b8  cmp     [rbx+244h], r13d
0x18001d9bf  jnz     short loc_18001DA34
0x18001d9c1  test    dword ptr [rbx+208h], 200h
0x18001d9cb  jnz     short loc_18001DA40
0x18001d9cd  cmp     [rsi+1B0h], r13d
0x18001d9d4  jnz     short loc_18001DA40
0x18001d9d6  mov     r14d, 3E5h
0x18001d9dc  cmp     edi, r14d
0x18001d9df  jnz     short loc_18001DA22
0x18001d9e1  test    r15b, al
0x18001d9e4  jnz     loc_18001DB62
0x18001d9ea  lea     rcx, [rbx+210h]; lpCriticalSection
0x18001d9f1  call    cs:__imp_LeaveCriticalSection
0x18001d9f8  nop     dword ptr [rax+rax+00h]
0x18001d9fd  mov     rcx, rsi; lpMem
0x18001da00  call    DeRefSendBlob
0x18001da05  test    r13d, r13d
0x18001da08  jnz     loc_18001DBE5
0x18001da0e  mov     eax, edi
0x18001da10  add     rsp, 38h
0x18001da14  pop     r15
0x18001da16  pop     r14
0x18001da18  pop     r13
0x18001da1a  pop     r12
0x18001da1c  pop     rdi
0x18001da1d  pop     rsi
0x18001da1e  pop     rbp
0x18001da1f  pop     rbx
0x18001da20  retn
0x18001da22  test    edi, edi
0x18001da24  jnz     short loc_18001DA51
0x18001da26  test    r15b, al
0x18001da29  jnz     loc_18001DBD3
0x18001da2f  mov     edi, r14d
0x18001da32  jmp     short loc_18001D9EA
0x18001da34  test    r15b, al
0x18001da37  jz      short loc_18001D9EA
0x18001da39  mov     edx, 81h
0x18001da3e  jmp     short loc_18001DA4A
0x18001da40  test    r15b, al
0x18001da43  jz      short loc_18001D9EA
0x18001da45  mov     edx, 82h
0x18001da4a  call    WPP_SF_
0x18001da4f  jmp     short loc_18001D9EA
0x18001da51  xor     ebp, ebp
0x18001da53  test    r15b, al
0x18001da56  jnz     loc_18001DB74
0x18001da5c  movzx   r8d, byte ptr [rbx+288h]
0x18001da64  mov     edx, edi
0x18001da66  mov     rcx, rbx
0x18001da69  mov     [rbx+292h], bpl
0x18001da70  call    Trace_LogRecvEvent
0x18001da75  or      [rbx+20Ch], r15d
0x18001da7c  mov     rax, [rbx+1C8h]
0x18001da83  btr     dword ptr [rbx+208h], 7
0x18001da8b  mov     r12d, [rbx+20Ch]
0x18001da92  test    rax, rax
0x18001da95  jnz     loc_18001DB86
0x18001da9b  lea     r15, [rbx+210h]
0x18001daa2  mov     rcx, r15; lpCriticalSection
0x18001daa5  call    cs:__imp_LeaveCriticalSection
0x18001daac  nop     dword ptr [rax+rax+00h]
0x18001dab1  test    rbp, rbp
0x18001dab4  jnz     loc_18001DB95
0x18001daba  test    r12b, 10h
0x18001dabe  jnz     short loc_18001DB0B
0x18001dac0  mov     rcx, [rbx+200h]; pti
0x18001dac7  xor     edx, edx
0x18001dac9  call    ThreadPool_WaitForTimer
0x18001dace  mov     rcx, r15; lpCriticalSection
0x18001dad1  call    cs:__imp_EnterCriticalSection
0x18001dad8  nop     dword ptr [rax+rax+00h]
0x18001dadd  test    dword ptr [rbx+208h], 200h
0x18001dae7  mov     rcx, r15
0x18001daea  mov     rax, [rbx+0D8h]
0x18001daf1  cmovz   r14d, edi
0x18001daf5  mov     dword ptr [rbx+23Ch], 0
0x18001daff  mov     edi, r14d
0x18001db02  mov     [rbx+30h], rax
0x18001db06  jmp     loc_18001D9F1
0x18001db0b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001db12  jnz     loc_18001DBA9
0x18001db18  mov     rcx, [rbx+1F0h]; pio
0x18001db1f  test    rcx, rcx
0x18001db22  jnz     short loc_18001DB2C
0x18001db24  mov     r13d, 1
0x18001db2a  jmp     short loc_18001DAC0
0x18001db2c  call    cs:__imp_CancelThreadpoolIo
0x18001db33  nop     dword ptr [rax+rax+00h]
0x18001db38  jmp     short loc_18001DB24
0x18001db3a  mov     edx, 80h
0x18001db3f  mov     dword ptr [rsp+78h+var_58], edi
0x18001db43  mov     r9, rsi
0x18001db46  call    WPP_SF_qD
0x18001db4b  mov     al, byte ptr cs:xmmword_1801119E0+1
0x18001db51  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x18001db58  mov     ecx, 40Bh
0x18001db5d  jmp     loc_18001D9B8
0x18001db62  mov     edx, 83h
0x18001db67  mov     r9, rbx
0x18001db6a  call    WPP_SF_q
0x18001db6f  jmp     loc_18001D9EA
0x18001db74  mov     edx, 84h
0x18001db79  mov     r9d, edi
0x18001db7c  call    WPP_SF_d
0x18001db81  jmp     loc_18001DA5C
0x18001db86  mov     rbp, rax
0x18001db89  mov     [rbx+1C8h], r13
0x18001db90  jmp     loc_18001DA9B
0x18001db95  mov     rcx, rbp; pci
0x18001db98  call    cs:__imp_DisassociateCurrentThreadFromCallback
0x18001db9f  nop     dword ptr [rax+rax+00h]
0x18001dba4  jmp     loc_18001DABA
0x18001dba9  mov     rax, [rbx+1F0h]
0x18001dbb0  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x18001dbb7  mov     edx, 85h
0x18001dbbc  mov     [rsp+78h+var_58], rax
0x18001dbc1  mov     ecx, 40Bh
0x18001dbc6  mov     r9, rbx
0x18001dbc9  call    WPP_SF_qq
0x18001dbce  jmp     loc_18001DB18
0x18001dbd3  mov     edx, 86h
0x18001dbd8  mov     r9, rbx
0x18001dbdb  call    WPP_SF_q
0x18001dbe0  jmp     loc_18001DA2F
0x18001dbe5  mov     rcx, rsi; lpMem
0x18001dbe8  call    DeRefSendBlob
0x18001dbed  jmp     loc_18001DA0E
```
