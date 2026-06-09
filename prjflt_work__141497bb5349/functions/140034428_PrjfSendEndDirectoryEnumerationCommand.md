# PrjfSendEndDirectoryEnumerationCommand

- ea: `0x140034428`
- end: `0x1400346e9`
- name: `PrjfSendEndDirectoryEnumerationCommand`
- size: `705`
- prototype: `__int64 __fastcall(__int64, struct _FLT_INSTANCE *, struct _FILE_OBJECT *, __int128 *, _OWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400211e0`
- `0x140039de8`

## callees

- `0x14000b1d0`
- `0x14000be80`
- `0x14000d128`
- `0x14000d754`
- `0x140032db4`
- `0x140032fd8`
- `0x140033bd0`
- `0x140034428`
- `0x14003a5cc`

## pseudocode

```c
__int64 __fastcall PrjfSendEndDirectoryEnumerationCommand(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        __int128 *a4,
        _OWORD *a5)
{
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // edx
  int v12; // ebx
  int v13; // r8d
  __int128 v14; // xmm1
  int v15; // edx
  int v16; // r8d
  int v17; // edx
  int v18; // r8d
  int v20; // [rsp+20h] [rbp-E0h]
  PVOID Entry; // [rsp+60h] [rbp-A0h] BYREF
  int v22; // [rsp+68h] [rbp-98h] BYREF
  int v23; // [rsp+6Ch] [rbp-94h] BYREF
  __int128 v24; // [rsp+70h] [rbp-90h] BYREF
  __int128 v25; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v26[34]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v27; // [rsp+2E0h] [rbp+1E0h] BYREF

  Entry = 0;
  memset(v26, 0, sizeof(v26));
  v27 = 0;
  v23 = 0;
  v22 = 4;
  v26[0] = *a5;
  if ( a3 )
  {
    if ( a4 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v10, v9);
    v12 = PrjfPrepareCommandForFileObject(a2, a3, 2, (__int64)v26, v20, &Entry, (__int64)&v27);
    if ( v12 < 0 )
    {
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 0x40;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          526,
          v11,
          v13,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          169,
          (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
          183,
          v12,
          (__int64)&a3->FileName);
      }
      goto LABEL_17;
    }
    goto LABEL_13;
  }
  v14 = *a4;
  v24 = 0;
  v25 = v14;
  v12 = PrjfPrepareCommandForFilePath((unsigned __int16 *)&v24, &v25, 2, 0, v26, 0, 0, &Entry, &v27);
  if ( v12 >= 0 )
  {
LABEL_13:
    v12 = PrjfSendCommand(a1, a2, Entry, 0, (__int64)&v23, (__int64)&v22);
    if ( v12 < 0
      && ((BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
    {
      LOBYTE(v17) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        v17,
        v18,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        171,
        (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        226,
        v12);
    }
    goto LABEL_17;
  }
  if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v15) = BYTE1(xmmword_14001A3D0) & 0x40;
    LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDdZ(
      526,
      v15,
      v16,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      14,
      170,
      (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      206,
      v12,
      (__int64)&v24);
  }
LABEL_17:
  if ( Entry )
    PrjfFreeCommandBuffer(Entry);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140034428  mov     [rsp-8+arg_0], rbx
0x14003442d  mov     [rsp-8+arg_8], rsi
0x140034432  push    rbp
0x140034433  push    rdi
0x140034434  push    r14
0x140034436  lea     rbp, [rsp-1B0h]
0x14003443e  sub     rsp, 2B0h
0x140034445  mov     rdi, r8
0x140034448  mov     [rsp+2C0h+Entry], 0
0x140034451  mov     rsi, rdx
0x140034454  mov     r14, rcx
0x140034457  xor     edx, edx; Val
0x140034459  lea     rcx, [rbp+1C0h+var_230]; void *
0x14003445d  mov     r8d, 220h; Size
0x140034463  mov     rbx, r9
0x140034466  call    memset
0x14003446b  mov     rax, [rbp+1C0h+arg_20]
0x140034472  mov     [rbp+1C0h+arg_10], 0
0x14003447c  mov     [rsp+2C0h+var_254], 0
0x140034484  mov     [rsp+2C0h+var_258], 4
0x14003448c  movaps  xmm0, xmmword ptr [rax]
0x14003448f  movdqu  [rbp+1C0h+var_230], xmm0
0x140034494  test    rdi, rdi
0x140034497  jz      loc_14003453B
0x14003449d  test    rbx, rbx
0x1400344a0  jz      short loc_1400344A7
0x1400344a2  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400344a7  lea     rax, [rbp+1C0h+arg_10]
0x1400344ae  mov     r8d, 2
0x1400344b4  mov     [rsp+2C0h+var_290], rax
0x1400344b9  lea     r9, [rbp+1C0h+var_230]
0x1400344bd  lea     rax, [rsp+2C0h+Entry]
0x1400344c2  mov     rdx, rdi
0x1400344c5  mov     rcx, rsi
0x1400344c8  mov     [rsp+2C0h+var_298], rax
0x1400344cd  call    PrjfPrepareCommandForFileObject
0x1400344d2  mov     ebx, eax
0x1400344d4  test    eax, eax
0x1400344d6  jns     loc_14003461D
0x1400344dc  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400344e2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400344e9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400344f0  setnz   r8b
0x1400344f4  and     dl, 40h
0x1400344f7  jnz     short loc_140034502
0x1400344f9  test    r8b, r8b
0x1400344fc  jz      loc_1400346B9
0x140034502  lea     rax, [rdi+58h]
0x140034506  mov     [rsp+2C0h+var_268], rax
0x14003450b  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140034512  mov     [rsp+2C0h+var_270], ebx
0x140034516  mov     [rsp+2C0h+var_278], 13B7h
0x14003451e  mov     [rsp+2C0h+var_280], rax
0x140034523  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14003452a  mov     [rsp+2C0h+var_288], rax
0x14003452f  mov     word ptr [rsp+2C0h+var_290], 0A9h
0x140034536  jmp     loc_1400345F6
0x14003453b  movups  xmm1, xmmword ptr [rbx]
0x14003453e  lea     rax, [rbp+1C0h+arg_10]
0x140034545  xor     r9d, r9d
0x140034548  mov     [rsp+2C0h+var_280], rax
0x14003454d  lea     rdx, [rbp+1C0h+var_240]
0x140034551  lea     rax, [rsp+2C0h+Entry]
0x140034556  xorps   xmm0, xmm0
0x140034559  mov     [rsp+2C0h+var_288], rax
0x14003455e  lea     rcx, [rsp+2C0h+var_250]
0x140034563  mov     [rsp+2C0h+var_290], 0
0x14003456c  lea     rax, [rbp+1C0h+var_230]
0x140034570  mov     [rsp+2C0h+var_298], 0
0x140034579  lea     r8d, [r9+2]
0x14003457d  mov     [rsp+2C0h+var_2A0], rax
0x140034582  movups  [rsp+2C0h+var_250], xmm0
0x140034587  movdqu  [rbp+1C0h+var_240], xmm1
0x14003458c  call    PrjfPrepareCommandForFilePath
0x140034591  mov     ebx, eax
0x140034593  test    eax, eax
0x140034595  jns     loc_14003461D
0x14003459b  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400345a1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400345a8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400345af  setnz   r8b
0x1400345b3  and     dl, 40h
0x1400345b6  jnz     short loc_1400345C1
0x1400345b8  test    r8b, r8b
0x1400345bb  jz      loc_1400346B9
0x1400345c1  lea     rax, [rsp+2C0h+var_250]
0x1400345c6  mov     [rsp+2C0h+var_268], rax
0x1400345cb  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400345d2  mov     [rsp+2C0h+var_270], ebx
0x1400345d6  mov     [rsp+2C0h+var_278], 13CEh
0x1400345de  mov     [rsp+2C0h+var_280], rax
0x1400345e3  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400345ea  mov     [rsp+2C0h+var_288], rax
0x1400345ef  mov     word ptr [rsp+2C0h+var_290], 0AAh
0x1400345f6  mov     r9, cs:WPP_GLOBAL_Control
0x1400345fd  mov     ecx, 20Eh
0x140034602  mov     dword ptr [rsp+2C0h+var_298], 0Eh
0x14003460a  mov     byte ptr [rsp+2C0h+var_2A0], 2
0x14003460f  mov     r9, [r9+40h]
0x140034613  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140034618  jmp     loc_1400346B9
0x14003461d  mov     r8, [rsp+2C0h+Entry]
0x140034622  lea     rax, [rsp+2C0h+var_258]
0x140034627  mov     [rsp+2C0h+var_298], rax
0x14003462c  xor     r9d, r9d
0x14003462f  lea     rax, [rsp+2C0h+var_254]
0x140034634  mov     rdx, rsi
0x140034637  mov     rcx, r14
0x14003463a  mov     [rsp+2C0h+var_2A0], rax
0x14003463f  call    PrjfSendCommand
0x140034644  mov     ebx, eax
0x140034646  test    eax, eax
0x140034648  jns     short loc_1400346B9
0x14003464a  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140034650  lea     rax, WPP_RECORDER_INITIALIZED
0x140034657  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003465e  setnz   r8b
0x140034662  and     dl, 40h
0x140034665  jnz     short loc_14003466C
0x140034667  test    r8b, r8b
0x14003466a  jz      short loc_1400346B9
0x14003466c  mov     r9, cs:WPP_GLOBAL_Control
0x140034673  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003467a  mov     [rsp+2C0h+var_270], ebx
0x14003467e  mov     ecx, 20Eh
0x140034683  mov     [rsp+2C0h+var_278], 13E2h
0x14003468b  mov     [rsp+2C0h+var_280], rax
0x140034690  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140034697  mov     r9, [r9+40h]
0x14003469b  mov     [rsp+2C0h+var_288], rax
0x1400346a0  mov     word ptr [rsp+2C0h+var_290], 0ABh
0x1400346a7  mov     dword ptr [rsp+2C0h+var_298], 0Eh
0x1400346af  mov     byte ptr [rsp+2C0h+var_2A0], 2
0x1400346b4  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400346b9  mov     rcx, [rsp+2C0h+Entry]; Entry
0x1400346be  test    rcx, rcx
0x1400346c1  jz      short loc_1400346CE
0x1400346c3  mov     edx, [rbp+1C0h+arg_10]
0x1400346c9  call    PrjfFreeCommandBuffer
0x1400346ce  lea     r11, [rsp+2C0h+var_10]
0x1400346d6  mov     eax, ebx
0x1400346d8  mov     rbx, [r11+20h]
0x1400346dc  mov     rsi, [r11+28h]
0x1400346e0  mov     rsp, r11
0x1400346e3  pop     r14
0x1400346e5  pop     rdi
0x1400346e6  pop     rbp
0x1400346e7  retn
```
