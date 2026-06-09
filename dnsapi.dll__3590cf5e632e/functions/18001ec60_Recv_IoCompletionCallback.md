# Recv_IoCompletionCallback

- ea: `0x18001ec60`
- end: `0x18001ef61`
- name: `Recv_IoCompletionCallback`
- size: `769`
- prototype: `__int64 __usercall@<rax>(PTP_CALLBACK_INSTANCE pci@<rcx>, LPVOID lpMem@<rdx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001d900`

## callees

- `0x18001ec60`
- `0x18001ef68`
- `0x18001f03c`
- `0x18001f218`
- `0x18001ffac`
- `0x180083954`
- `0x1800dc9e0`
- `0x1800ddfa8`
- `0x1800de650`
- `0x1800dfa80`
- `0x1800dfdc8`
- `0x1800e0f4c`
- `0x1800e25c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ed18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001edd6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ed18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001edd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ed48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001edec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ee2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ed48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001edec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ee2f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ecf8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ecf8`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x18001ed57`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x18001ed57`

## pseudocode

```c
char __fastcall Recv_IoCompletionCallback(
        PTP_CALLBACK_INSTANCE pci,
        __int64 lpMem,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v8; // rcx
  _QWORD *v10; // rsi
  char result; // al
  __int64 v12; // rdi
  __int64 v13; // rcx
  struct _TP_TIMER *v14; // rbx
  __int64 v15; // r9
  __int64 v16; // rcx

  v8 = a6;
  v10 = (_QWORD *)lpMem;
  result = BYTE1(xmmword_1801119E0);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    WPP_SF_qqqddq(a6, lpMem, a3, (_DWORD)pci, lpMem, a3, a4, a5, a6);
    result = BYTE1(xmmword_1801119E0);
  }
  if ( a3 )
  {
    v12 = v10[11];
    if ( !v12 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v8);
      result = BYTE1(xmmword_1801119E0);
    }
    if ( (result & 8) != 0 )
      WPP_SF_qD(1035, 115, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, v12, a4);
    if ( (unsigned int)Recv_IsMsgStateProcessIo(v12) )
    {
      if ( !*(_QWORD *)(v12 + 512) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v13);
      v14 = *(struct _TP_TIMER **)(v12 + 512);
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_q(1035, 22, WPP_0ee542721a7b375122a881c30985be4a_Traceguids, *(_QWORD *)(v12 + 512));
      if ( v14 )
        WaitForThreadpoolTimerCallbacks(v14, 1);
      *(_DWORD *)(v12 + 572) = 0;
      EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 528));
      v15 = *(unsigned int *)(v12 + 520);
      if ( (v15 & 0x300) != 0 || (*(_BYTE *)(v12 + 524) & 0xC) != 0 )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_d(1035, 116, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, v15);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 528));
      }
      else
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 528));
        DisassociateCurrentThreadFromCallback(pci);
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_qq(
            1035,
            117,
            (unsigned int)WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids,
            (_DWORD)v10,
            *(_QWORD *)(v12 + 304));
        v10 = *(_QWORD **)(v12 + 304);
        if ( !v10 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v16);
        *((_DWORD *)v10 + 49) = a4;
        if ( a4 == 1234 )
          *((_DWORD *)v10 + 49) = 10054;
        if ( *(_BYTE *)(v12 + 648) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v16);
        if ( !*((_DWORD *)v10 + 49) )
        {
          *(_WORD *)(v10[69] + 698LL) = a5;
          Recv_UpdateControlInfo();
        }
        Recv_UdpCallbackCompletion(v10);
      }
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 528));
    *(_DWORD *)(v12 + 520) &= ~0x20u;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 528));
    result = DeRefSendBlob(v10);
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      return WPP_SF_qqD(1035, 118, (unsigned int)WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, (_DWORD)v10, v12);
  }
  else if ( (result & 8) != 0 )
  {
    return WPP_SF_(1035, 114, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x18001ec60  mov     [rsp+arg_18], rbx
0x18001ec65  push    rsi
0x18001ec66  push    rdi
0x18001ec67  push    r12
0x18001ec69  push    r13
0x18001ec6b  push    r15
0x18001ec6d  sub     rsp, 50h
0x18001ec71  mov     r12, rcx
0x18001ec74  mov     r15d, r9d
0x18001ec77  mov     rcx, [rsp+78h+arg_28]
0x18001ec7f  mov     rbx, r8
0x18001ec82  mov     rsi, rdx
0x18001ec85  mov     al, byte ptr cs:xmmword_1801119E0+1
0x18001ec8b  mov     r13, [rsp+78h+arg_20]
0x18001ec93  test    al, 8
0x18001ec95  jnz     loc_18001EE59
0x18001ec9b  test    rbx, rbx
0x18001ec9e  jz      loc_18001EE3D
0x18001eca4  mov     rdi, [rsi+58h]
0x18001eca8  test    rdi, rdi
0x18001ecab  jz      loc_18001EF18
0x18001ecb1  test    al, 8
0x18001ecb3  jnz     loc_18001EED7
0x18001ecb9  mov     rcx, rdi
0x18001ecbc  call    Recv_IsMsgStateProcessIo
0x18001ecc1  test    eax, eax
0x18001ecc3  jz      loc_18001EDCC
0x18001ecc9  cmp     qword ptr [rdi+200h], 0
0x18001ecd1  jz      loc_18001EF28
0x18001ecd7  mov     rbx, [rdi+200h]
0x18001ecde  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001ece5  jnz     loc_18001EEFA
0x18001eceb  test    rbx, rbx
0x18001ecee  jz      short loc_18001ED04
0x18001ecf0  mov     edx, 1; fCancelPendingCallbacks
0x18001ecf5  mov     rcx, rbx; pti
0x18001ecf8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001ecff  nop     dword ptr [rax+rax+00h]
0x18001ed04  lea     rbx, [rdi+210h]
0x18001ed0b  mov     dword ptr [rdi+23Ch], 0
0x18001ed15  mov     rcx, rbx; lpCriticalSection
0x18001ed18  call    cs:__imp_EnterCriticalSection
0x18001ed1f  nop     dword ptr [rax+rax+00h]
0x18001ed24  mov     r9d, [rdi+208h]
0x18001ed2b  test    r9d, 300h
0x18001ed32  jnz     loc_18001EE1F
0x18001ed38  test    byte ptr [rdi+20Ch], 0Ch
0x18001ed3f  jnz     loc_18001EE1F
0x18001ed45  mov     rcx, rbx; lpCriticalSection
0x18001ed48  call    cs:__imp_LeaveCriticalSection
0x18001ed4f  nop     dword ptr [rax+rax+00h]
0x18001ed54  mov     rcx, r12; pci
0x18001ed57  call    cs:__imp_DisassociateCurrentThreadFromCallback
0x18001ed5e  nop     dword ptr [rax+rax+00h]
0x18001ed63  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001ed6a  jnz     loc_18001EEAD
0x18001ed70  mov     rsi, [rdi+130h]
0x18001ed77  test    rsi, rsi
0x18001ed7a  jz      loc_18001EF32
0x18001ed80  mov     [rsi+0C4h], r15d
0x18001ed87  cmp     r15d, 4D2h
0x18001ed8e  jnz     short loc_18001ED9A
0x18001ed90  mov     dword ptr [rsi+0C4h], 2746h
0x18001ed9a  cmp     byte ptr [rdi+288h], 0
0x18001eda1  jnz     loc_18001EF3C
0x18001eda7  cmp     dword ptr [rsi+0C4h], 0
0x18001edae  jnz     short loc_18001EDC4
0x18001edb0  mov     rcx, [rsi+228h]
0x18001edb7  mov     [rcx+2BAh], r13w
0x18001edbf  call    Recv_UpdateControlInfo
0x18001edc4  mov     rcx, rsi
0x18001edc7  call    Recv_UdpCallbackCompletion
0x18001edcc  lea     rbx, [rdi+210h]
0x18001edd3  mov     rcx, rbx; lpCriticalSection
0x18001edd6  call    cs:__imp_EnterCriticalSection
0x18001eddd  nop     dword ptr [rax+rax+00h]
0x18001ede2  and     dword ptr [rdi+208h], 0FFFFFFDFh
0x18001ede9  mov     rcx, rbx; lpCriticalSection
0x18001edec  call    cs:__imp_LeaveCriticalSection
0x18001edf3  nop     dword ptr [rax+rax+00h]
0x18001edf8  mov     rcx, rsi; lpMem
0x18001edfb  call    DeRefSendBlob
0x18001ee00  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001ee07  jnz     short loc_18001EE85
0x18001ee09  mov     rbx, [rsp+78h+arg_18]
0x18001ee11  add     rsp, 50h
0x18001ee15  pop     r15
0x18001ee17  pop     r13
0x18001ee19  pop     r12
0x18001ee1b  pop     rdi
0x18001ee1c  pop     rsi
0x18001ee1d  retn
0x18001ee1f  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18001ee26  jnz     loc_18001EF46
0x18001ee2c  mov     rcx, rbx; lpCriticalSection
0x18001ee2f  call    cs:__imp_LeaveCriticalSection
0x18001ee36  nop     dword ptr [rax+rax+00h]
0x18001ee3b  jmp     short loc_18001EDCC
0x18001ee3d  test    al, 8
0x18001ee3f  jz      short loc_18001EE09
0x18001ee41  mov     edx, 72h ; 'r'
0x18001ee46  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x18001ee4d  mov     ecx, 40Bh
0x18001ee52  call    WPP_SF_
0x18001ee57  jmp     short loc_18001EE09
0x18001ee59  mov     [rsp+78h+var_38], rcx
0x18001ee5e  mov     r9, r12
0x18001ee61  mov     [rsp+78h+var_40], r13d
0x18001ee66  mov     [rsp+78h+var_48], r15d
0x18001ee6b  mov     [rsp+78h+var_50], rbx
0x18001ee70  mov     [rsp+78h+var_58], rsi
0x18001ee75  call    WPP_SF_qqqddq
0x18001ee7a  mov     al, byte ptr cs:xmmword_1801119E0+1
0x18001ee80  jmp     loc_18001EC9B
0x18001ee85  mov     edx, 76h ; 'v'
0x18001ee8a  mov     dword ptr [rsp+78h+var_50], r15d
0x18001ee8f  mov     ecx, 40Bh
0x18001ee94  mov     [rsp+78h+var_58], rdi
0x18001ee99  mov     r9, rsi
0x18001ee9c  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x18001eea3  call    WPP_SF_qqD
0x18001eea8  jmp     loc_18001EE09
0x18001eead  mov     rax, [rdi+130h]
0x18001eeb4  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x18001eebb  mov     edx, 75h ; 'u'
0x18001eec0  mov     [rsp+78h+var_58], rax
0x18001eec5  mov     ecx, 40Bh
0x18001eeca  mov     r9, rsi
0x18001eecd  call    WPP_SF_qq
0x18001eed2  jmp     loc_18001ED70
0x18001eed7  mov     edx, 73h ; 's'
0x18001eedc  mov     dword ptr [rsp+78h+var_58], r15d
0x18001eee1  mov     ecx, 40Bh
0x18001eee6  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x18001eeed  mov     r9, rdi
0x18001eef0  call    WPP_SF_qD
0x18001eef5  jmp     loc_18001ECB9
0x18001eefa  mov     edx, 16h
0x18001eeff  lea     r8, WPP_0ee542721a7b375122a881c30985be4a_Traceguids
0x18001ef06  mov     ecx, 40Bh
0x18001ef0b  mov     r9, rbx
0x18001ef0e  call    WPP_SF_q
0x18001ef13  jmp     loc_18001ECEB
0x18001ef18  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001ef1d  mov     al, byte ptr cs:xmmword_1801119E0+1
0x18001ef23  jmp     loc_18001ECB1
0x18001ef28  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001ef2d  jmp     loc_18001ECD7
0x18001ef32  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001ef37  jmp     loc_18001ED80
0x18001ef3c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001ef41  jmp     loc_18001EDA7
0x18001ef46  mov     edx, 74h ; 't'
0x18001ef4b  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x18001ef52  mov     ecx, 40Bh
0x18001ef57  call    WPP_SF_d
0x18001ef5c  jmp     loc_18001EE2C
```
