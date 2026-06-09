# PcpCreateFlow

- ea: `0x14000adf8`
- end: `0x14000b095`
- name: `PcpCreateFlow`
- size: `669`
- prototype: `__int64 __fastcall(_QWORD *, char, int, __int64, ULONG, int, void *, char, __int64)`
- caller_count: `6`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140005c10`
- `0x14000aaa4`
- `0x14000c550`
- `0x14000c6c0`
- `0x14000dc3c`
- `0x140010040`

## callees

- `0x140003ab0`
- `0x14000adf8`
- `0x14000b09c`
- `0x14000b0e0`
- `0x14000b868`
- `0x14000bacc`
- `0x14000bb5c`
- `0x14000f54c`
- `0x14000f874`
- `0x14000f938`
- `0x1400116ec`
- `0x140012918`
- `0x140013110`
- `0x140013600`

## pseudocode

```c
__int64 __fastcall PcpCreateFlow(
        _QWORD *a1,
        char a2,
        int a3,
        __int64 a4,
        ULONG a5,
        int a6,
        void *a7,
        char a8,
        __int64 a9)
{
  __int64 v9; // rbx
  char *Src; // rsi
  int Flow; // eax
  __int64 v16; // rcx
  _DWORD *v17; // rdi
  char *v18; // rcx
  char *v19; // rdx
  _DWORD *v20; // rax
  int updated; // [rsp+A0h] [rbp-29h] BYREF
  _WORD v23[2]; // [rsp+A4h] [rbp-25h] BYREF
  __int16 v24; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v25; // [rsp+B0h] [rbp-19h] BYREF
  PVOID P[2]; // [rsp+B8h] [rbp-11h] BYREF

  v9 = a9;
  Src = (char *)a7;
  v25 = a9;
  v24 = 0;
  v23[0] = 0;
  P[0] = 0;
  Flow = PcpAllocateFlow(a5, P);
  v17 = P[0];
  updated = Flow;
  if ( Flow >= 0 )
  {
    PcpInitializeFlow(P[0]);
    if ( !a8 )
      v17[154] |= 3u;
    if ( (v17[154] & 1) != 0 && (updated = PcpIncrementHold(), updated < 0) )
    {
      PcpUninitializeFlow(v17);
      PcpFreeFlow(v17);
    }
    else
    {
      memset(v17 + 34, 0, 0x1A8u);
      QosTbcFlowInitialize(v17 + 34);
      if ( (a2 & 1) == 0 )
      {
        updated = PcpUpdateFlow((KAFFINITY)v17, a4, a5, a6, Src, 1, a3, 0, &v24, v23);
        if ( updated < 0 )
        {
          if ( (v17[154] & 1) != 0 )
            PcpDecrementHold();
          PcpUninitializeFlow(v17);
          PcpFreeFlow(v17);
        }
      }
      v9 = v25;
    }
  }
  if ( updated >= 0 )
  {
    *a1 = v17;
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
      P[1] = *((PVOID *)&QOS_FLOW_PROVIDER_GUID + 1);
      P[0] = v17;
      EtwEx_tidActivityInfo(v16, ActivityStart, P);
      if ( (a2 & 2) != 0 )
        PcpEtwTransferActivityIdGuid(P, v9, 0);
    }
  }
  else
  {
    v17 = 0;
    *a1 = 0;
  }
  if ( PcgEventTraceEnabled )
  {
    if ( a6 == 1 )
    {
      v18 = Src + 524;
      v19 = Src + 592;
      v20 = Src + 588;
    }
    else
    {
      v19 = (char *)*((_QWORD *)Src + 9);
      v20 = Src + 64;
      v18 = Src;
    }
    LODWORD(v25) = *v20;
    PcpEtwWriteFlowEvent(
      QOS_EVENT_PACER_CREATE_FLOW,
      v17,
      8,
      &updated,
      4,
      &a6,
      4,
      v18,
      32,
      &v24,
      2,
      v23,
      2,
      &v25,
      4,
      v19,
      v25,
      &a8,
      1);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x14000adf8  mov     [rsp-8+arg_8], rbx
0x14000adfd  push    rbp
0x14000adfe  push    rsi
0x14000adff  push    rdi
0x14000ae00  push    r12
0x14000ae02  push    r13
0x14000ae04  push    r14
0x14000ae06  push    r15
0x14000ae08  lea     rbp, [rsp-7]
0x14000ae0d  sub     rsp, 0D0h
0x14000ae14  mov     rax, cs:__security_cookie
0x14000ae1b  xor     rax, rsp
0x14000ae1e  mov     [rbp+37h+var_38], rax
0x14000ae22  mov     rbx, [rbp+37h+arg_40]
0x14000ae29  xor     eax, eax
0x14000ae2b  mov     rsi, [rbp+37h+arg_30]
0x14000ae2f  mov     r15d, edx
0x14000ae32  mov     r14, rcx
0x14000ae35  mov     [rbp+37h+var_50], rbx
0x14000ae39  mov     ecx, [rbp+37h+arg_20]
0x14000ae3c  lea     rdx, [rbp+37h+P]
0x14000ae40  mov     word ptr [rbp+37h+var_5C+4], ax
0x14000ae44  mov     r13, r9
0x14000ae47  mov     word ptr [rbp+37h+var_5C], ax
0x14000ae4b  mov     r12d, r8d
0x14000ae4e  mov     [rbp+37h+var_60], 0
0x14000ae55  mov     [rbp+37h+P], 0
0x14000ae5d  call    PcpAllocateFlow
0x14000ae62  mov     rdi, [rbp+37h+P]
0x14000ae66  mov     [rbp+37h+var_60], eax
0x14000ae69  test    eax, eax
0x14000ae6b  js      loc_14000AF3D
0x14000ae71  mov     rcx, rdi
0x14000ae74  call    PcpInitializeFlow
0x14000ae79  cmp     [rbp+37h+arg_38], 0
0x14000ae7d  jnz     short loc_14000AE86
0x14000ae7f  or      dword ptr [rdi+268h], 3
0x14000ae86  mov     eax, [rdi+268h]
0x14000ae8c  test    al, 1
0x14000ae8e  jz      short loc_14000AEB1
0x14000ae90  call    PcpIncrementHold
0x14000ae95  mov     [rbp+37h+var_60], eax
0x14000ae98  test    eax, eax
0x14000ae9a  jns     short loc_14000AEB1
0x14000ae9c  mov     rcx, rdi
0x14000ae9f  call    PcpUninitializeFlow
0x14000aea4  mov     rcx, rdi; P
0x14000aea7  call    PcpFreeFlow
0x14000aeac  jmp     loc_14000AF3D
0x14000aeb1  lea     rbx, [rdi+88h]
0x14000aeb8  xor     edx, edx; Val
0x14000aeba  mov     rcx, rbx; void *
0x14000aebd  mov     r8d, 1A8h; Size
0x14000aec3  call    memset
0x14000aec8  mov     rcx, rbx
0x14000aecb  call    QosTbcFlowInitialize
0x14000aed0  test    r15b, 1
0x14000aed4  jnz     short loc_14000AF39
0x14000aed6  mov     r9d, [rbp+37h+arg_28]; int
0x14000aeda  lea     rax, [rbp+37h+var_5C]
0x14000aede  mov     r8d, [rbp+37h+arg_20]; int
0x14000aee2  mov     rdx, r13; int
0x14000aee5  mov     [rsp+100h+var_B8], rax; __int64
0x14000aeea  mov     rcx, rdi; int
0x14000aeed  lea     rax, [rbp+37h+var_5C+4]
0x14000aef1  mov     [rsp+100h+var_C0], rax; __int64
0x14000aef6  mov     [rsp+100h+var_C8], 0; __int64
0x14000aeff  mov     [rsp+100h+var_D0], r12d; int
0x14000af04  mov     [rsp+100h+var_D8], 1; char
0x14000af09  mov     [rsp+100h+Src], rsi; Src
0x14000af0e  call    PcpUpdateFlow
0x14000af13  mov     [rbp+37h+var_60], eax
0x14000af16  test    eax, eax
0x14000af18  jns     short loc_14000AF39
0x14000af1a  mov     eax, [rdi+268h]
0x14000af20  test    al, 1
0x14000af22  jz      short loc_14000AF29
0x14000af24  call    PcpDecrementHold
0x14000af29  mov     rcx, rdi
0x14000af2c  call    PcpUninitializeFlow
0x14000af31  mov     rcx, rdi; P
0x14000af34  call    PcpFreeFlow
0x14000af39  mov     rbx, [rbp+37h+var_50]
0x14000af3d  cmp     [rbp+37h+var_60], 0
0x14000af41  mov     r12d, 2
0x14000af47  jge     short loc_14000AF50
0x14000af49  xor     edi, edi
0x14000af4b  mov     [r14], rdi
0x14000af4e  jmp     short loc_14000AF9B
0x14000af50  mov     [r14], rdi
0x14000af53  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000af59  test    eax, eax
0x14000af5b  jz      short loc_14000AF9B
0x14000af5d  movups  xmm0, cs:QOS_FLOW_PROVIDER_GUID
0x14000af64  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000af6a  movdqu  xmmword ptr [rbp+37h+P], xmm0
0x14000af6f  mov     [rbp+37h+P], rdi
0x14000af73  test    eax, eax
0x14000af75  jz      short loc_14000AF87
0x14000af77  lea     r8, [rbp+37h+P]
0x14000af7b  lea     rdx, ActivityStart
0x14000af82  call    EtwEx_tidActivityInfo
0x14000af87  test    r12b, r15b
0x14000af8a  jz      short loc_14000AF9B
0x14000af8c  xor     r8d, r8d
0x14000af8f  lea     rcx, [rbp+37h+P]
0x14000af93  mov     rdx, rbx
0x14000af96  call    PcpEtwTransferActivityIdGuid
0x14000af9b  mov     eax, cs:PcgEventTraceEnabled
0x14000afa1  test    eax, eax
0x14000afa3  jz      loc_14000B06A
0x14000afa9  cmp     [rbp+37h+arg_28], r12d
0x14000afad  jz      short loc_14000AFCC
0x14000afaf  cmp     [rbp+37h+arg_28], 1
0x14000afb3  jnz     short loc_14000AFCC
0x14000afb5  lea     rcx, [rsi+20Ch]
0x14000afbc  lea     rdx, [rsi+250h]
0x14000afc3  lea     rax, [rsi+24Ch]
0x14000afca  jmp     short loc_14000AFD7
0x14000afcc  mov     rdx, [rsi+48h]
0x14000afd0  lea     rax, [rsi+40h]
0x14000afd4  mov     rcx, rsi
0x14000afd7  mov     eax, [rax]
0x14000afd9  lea     r8, [rbp+37h+arg_38]
0x14000afdd  mov     [rsp+100h+var_70], 1
0x14000afe9  lea     r9, [rbp+37h+var_60]
0x14000afed  mov     [rsp+100h+var_78], r8
0x14000aff5  mov     r10d, 8
0x14000affb  mov     [rsp+100h+var_80], eax
0x14000b002  mov     r8d, r10d
0x14000b005  mov     [rsp+100h+var_88], rdx
0x14000b00a  mov     dword ptr [rbp+37h+var_50], eax
0x14000b00d  lea     rax, [rbp+37h+var_50]
0x14000b011  lea     edx, [r10-4]
0x14000b015  mov     [rsp+100h+var_90], rdx
0x14000b01a  mov     [rsp+100h+var_98], rax
0x14000b01f  lea     rax, [rbp+37h+var_5C]
0x14000b023  mov     [rsp+100h+var_A0], r12
0x14000b028  mov     [rsp+100h+var_A8], rax
0x14000b02d  lea     rax, [rbp+37h+var_5C+4]
0x14000b031  mov     [rsp+100h+var_B0], r12
0x14000b036  mov     [rsp+100h+var_B8], rax
0x14000b03b  lea     rax, [rbp+37h+arg_28]
0x14000b03f  mov     dword ptr [rsp+100h+var_C0], 20h ; ' '
0x14000b047  mov     [rsp+100h+var_C8], rcx
0x14000b04c  lea     rcx, QOS_EVENT_PACER_CREATE_FLOW
0x14000b053  mov     qword ptr [rsp+100h+var_D0], rdx
0x14000b058  mov     qword ptr [rsp+100h+var_D8], rax
0x14000b05d  mov     [rsp+100h+Src], rdx
0x14000b062  mov     rdx, rdi
0x14000b065  call    PcpEtwWriteFlowEvent
0x14000b06a  mov     eax, [rbp+37h+var_60]
0x14000b06d  mov     rcx, [rbp+37h+var_38]
0x14000b071  xor     rcx, rsp; StackCookie
0x14000b074  call    __security_check_cookie
0x14000b079  mov     rbx, [rsp+100h+arg_8]
0x14000b081  add     rsp, 0D0h
0x14000b088  pop     r15
0x14000b08a  pop     r14
0x14000b08c  pop     r13
0x14000b08e  pop     r12
0x14000b090  pop     rdi
0x14000b091  pop     rsi
0x14000b092  pop     rbp
0x14000b093  retn
```
