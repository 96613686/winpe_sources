# PrjfSendCommand

- ea: `0x140033bd0`
- end: `0x140033de2`
- name: `PrjfSendCommand`
- size: `530`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400047cc`
- `0x140034428`
- `0x1400346f0`
- `0x1400349fc`
- `0x140034c70`
- `0x140034e88`
- `0x140035060`

## callees

- `0x140003480`
- `0x140003e6c`
- `0x140005e8c`
- `0x14000b1d0`
- `0x14000d008`
- `0x14000d128`
- `0x140033bd0`
- `0x140033de8`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x140033d44`
- `HAL!KeQueryPerformanceCounter` at `0x140033d91`
- `HAL!KeQueryPerformanceCounter` at `0x140033d44`
- `HAL!KeQueryPerformanceCounter` at `0x140033d91`

## pseudocode

```c
__int64 __fastcall PrjfSendCommand(
        struct _FLT_CALLBACK_DATA *a1,
        void *a2,
        _DWORD *a3,
        __int64 a4,
        __int64 a5,
        _DWORD *a6)
{
  bool v6; // cc
  _DWORD *v8; // rbp
  void *v9; // r14
  __int64 v11; // rdi
  unsigned int v12; // edi
  __int64 UnionContext; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rsi
  LARGE_INTEGER v18; // rbx
  __int128 v19; // rtt
  __int128 v21; // [rsp+60h] [rbp-38h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+B0h] [rbp+18h] BYREF

  v6 = *a3 <= 0x380u;
  v8 = a3;
  PerformanceFrequency.QuadPart = 0;
  v9 = a2;
  if ( v6 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
  v11 = a5;
  if ( a5 )
  {
    v21 = *(_OWORD *)(v8 + 2);
    UnionContext = PrjfGetUnionContext(v9, &v21);
    v17 = UnionContext;
    if ( UnionContext )
    {
      if ( *(_QWORD *)(UnionContext + 80) )
      {
        v18 = KeQueryPerformanceCounter(&PerformanceFrequency);
        v8[6] = _InterlockedIncrement((volatile signed __int32 *)(v17 + 304));
        v12 = PrjfSendCommandAndWaitForCompletion(a1, v9, v8, a4, v17, v11, a6);
        v19 = 1000000 * (*(_QWORD *)&KeQueryPerformanceCounter(0) - v18.QuadPart);
        PrjfAggregateTelemetry(v8, v12, v19 / PerformanceFrequency.QuadPart);
      }
      else
      {
        v12 = -1073689087;
        LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 0x40;
        if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_sDL(
            526,
            v14,
            v15,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            14,
            149,
            (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
            168,
            1);
      }
      PrjfReleaseUnionContext((char *)v17, v14, v15, v16);
    }
    else
    {
      return (unsigned int)-1073689087;
    }
  }
  else
  {
    v12 = -1073741811;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        526,
        (_DWORD)a2,
        (_DWORD)a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        148,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        153);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x140033bd0  mov     rax, rsp
0x140033bd3  mov     [rax+8], rbx
0x140033bd7  mov     [rax+10h], rbp
0x140033bdb  push    rsi
0x140033bdc  push    rdi
0x140033bdd  push    r12
0x140033bdf  push    r14
0x140033be1  push    r15
0x140033be3  sub     rsp, 70h
0x140033be7  cmp     dword ptr [r8], 380h
0x140033bee  mov     r15, r9
0x140033bf1  mov     rbp, r8
0x140033bf4  mov     qword ptr [rax+18h], 0
0x140033bfc  mov     r14, rdx
0x140033bff  mov     r12, rcx
0x140033c02  ja      short loc_140033C09
0x140033c04  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140033c09  mov     rdi, [rsp+98h+arg_20]
0x140033c11  test    rdi, rdi
0x140033c14  jnz     short loc_140033C8F
0x140033c16  mov     edi, 0C000000Dh
0x140033c1b  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140033c21  lea     rax, WPP_RECORDER_INITIALIZED
0x140033c28  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140033c2f  setnz   r8b
0x140033c33  and     dl, 40h
0x140033c36  jnz     short loc_140033C41
0x140033c38  test    r8b, r8b
0x140033c3b  jz      loc_140033DC6
0x140033c41  mov     r9, cs:WPP_GLOBAL_Control
0x140033c48  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140033c4f  mov     [rsp+98h+var_50], 1099h
0x140033c57  mov     ecx, 20Eh
0x140033c5c  mov     [rsp+98h+var_58], rax
0x140033c61  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140033c68  mov     [rsp+98h+var_60], rax
0x140033c6d  mov     r9, [r9+40h]
0x140033c71  mov     word ptr [rsp+98h+var_68], 94h
0x140033c78  mov     dword ptr [rsp+98h+var_70], 0Eh
0x140033c80  mov     byte ptr [rsp+98h+var_78], 2
0x140033c85  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140033c8a  jmp     loc_140033DC6
0x140033c8f  movups  xmm0, xmmword ptr [rbp+8]
0x140033c93  lea     rdx, [rsp+98h+var_38]
0x140033c98  mov     rcx, r14
0x140033c9b  movdqu  [rsp+98h+var_38], xmm0
0x140033ca1  call    PrjfGetUnionContext
0x140033ca6  mov     rsi, rax
0x140033ca9  test    rax, rax
0x140033cac  jnz     short loc_140033CB8
0x140033cae  mov     edi, 0C000CE01h
0x140033cb3  jmp     loc_140033DC6
0x140033cb8  cmp     qword ptr [rax+50h], 0
0x140033cbd  jnz     short loc_140033D3C
0x140033cbf  mov     edi, 0C000CE01h
0x140033cc4  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140033cca  lea     rax, WPP_RECORDER_INITIALIZED
0x140033cd1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140033cd8  setnz   r8b
0x140033cdc  and     dl, 40h
0x140033cdf  jnz     short loc_140033CEA
0x140033ce1  test    r8b, r8b
0x140033ce4  jz      loc_140033DBE
0x140033cea  mov     r9, cs:WPP_GLOBAL_Control
0x140033cf1  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140033cf8  mov     [rsp+98h+var_48], edi
0x140033cfc  mov     ecx, 20Eh
0x140033d01  mov     [rsp+98h+var_50], 10A8h
0x140033d09  mov     [rsp+98h+var_58], rax
0x140033d0e  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140033d15  mov     r9, [r9+40h]
0x140033d19  mov     [rsp+98h+var_60], rax
0x140033d1e  mov     word ptr [rsp+98h+var_68], 95h
0x140033d25  mov     dword ptr [rsp+98h+var_70], 0Eh
0x140033d2d  mov     byte ptr [rsp+98h+var_78], 2
0x140033d32  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140033d37  jmp     loc_140033DBE
0x140033d3c  lea     rcx, [rsp+98h+PerformanceFrequency]; PerformanceFrequency
0x140033d44  call    cs:__imp_KeQueryPerformanceCounter
0x140033d4b  nop     dword ptr [rax+rax+00h]
0x140033d50  mov     rbx, rax
0x140033d53  mov     eax, 1
0x140033d58  lock xadd [rsi+130h], eax
0x140033d60  inc     eax
0x140033d62  mov     r9, r15
0x140033d65  mov     [rbp+18h], eax
0x140033d68  mov     r8, rbp
0x140033d6b  mov     rax, [rsp+98h+arg_28]
0x140033d73  mov     rdx, r14
0x140033d76  mov     [rsp+98h+var_68], rax
0x140033d7b  mov     rcx, r12
0x140033d7e  mov     [rsp+98h+var_70], rdi
0x140033d83  mov     [rsp+98h+var_78], rsi
0x140033d88  call    PrjfSendCommandAndWaitForCompletion
0x140033d8d  xor     ecx, ecx; PerformanceFrequency
0x140033d8f  mov     edi, eax
0x140033d91  call    cs:__imp_KeQueryPerformanceCounter
0x140033d98  nop     dword ptr [rax+rax+00h]
0x140033d9d  sub     rax, rbx
0x140033da0  mov     rcx, rbp
0x140033da3  imul    rax, 0F4240h
0x140033daa  cqo
0x140033dac  idiv    qword ptr [rsp+98h+PerformanceFrequency]
0x140033db4  mov     edx, edi
0x140033db6  mov     r8, rax
0x140033db9  call    PrjfAggregateTelemetry
0x140033dbe  mov     rcx, rsi; P
0x140033dc1  call    PrjfReleaseUnionContext
0x140033dc6  lea     r11, [rsp+98h+var_28]
0x140033dcb  mov     eax, edi
0x140033dcd  mov     rbx, [r11+30h]
0x140033dd1  mov     rbp, [r11+38h]
0x140033dd5  mov     rsp, r11
0x140033dd8  pop     r15
0x140033dda  pop     r14
0x140033ddc  pop     r12
0x140033dde  pop     rdi
0x140033ddf  pop     rsi
0x140033de0  retn
```
