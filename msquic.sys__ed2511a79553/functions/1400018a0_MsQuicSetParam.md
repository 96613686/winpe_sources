# MsQuicSetParam

- ea: `0x1400018a0`
- end: `0x140001af9`
- name: `MsQuicSetParam`
- size: `601`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1400018a0`
- `0x140001b00`
- `0x14000c4b8`
- `0x14002b6f4`
- `0x1400337e4`
- `0x14003eb54`
- `0x14003eca4`
- `0x14003f350`
- `0x140040c2c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400019fd`
- `ntoskrnl!KeInitializeEvent` at `0x1400019fd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400019a8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400019a8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001a67`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001a67`

## pseudocode

```c
__int64 __fastcall MsQuicSetParam(unsigned int *a1, __int64 a2, unsigned int a3, __int64 a4)
{
  unsigned int v4; // esi
  int v5; // r14d
  int v6; // ebx
  unsigned int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // eax
  unsigned int *v14; // rbx
  __int64 v15; // rcx
  char v16; // r14
  __int128 v17; // [rsp+30h] [rbp-59h] BYREF
  __int128 v18; // [rsp+40h] [rbp-49h]
  __int128 v19; // [rsp+50h] [rbp-39h]
  int v20; // [rsp+60h] [rbp-29h]
  _KEVENT Event; // [rsp+68h] [rbp-21h] BYREF
  __int128 v22; // [rsp+80h] [rbp-9h] BYREF
  __int64 v23; // [rsp+90h] [rbp+7h]
  __int128 *v24; // [rsp+98h] [rbp+Fh]
  __int128 v25; // [rsp+A0h] [rbp+17h]
  __int64 v26; // [rsp+B0h] [rbp+27h]
  unsigned int v27; // [rsp+F8h] [rbp+6Fh] BYREF

  v4 = a2 & 0xBFFFFFFF;
  v5 = a2 & 0x40000000;
  v6 = a2 & 0x3F000000;
  if ( (a1 == 0) != ((a2 & 0x3F000000) == 0x1000000) )
    return 3221225485LL;
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, a2, 0, a1);
  v27 = 0;
  if ( v6 == 0x1000000 )
  {
    v11 = QuicLibrarySetGlobalParam(v4, a3, a4);
LABEL_29:
    v27 = v11;
    goto LABEL_30;
  }
  v13 = *a1;
  if ( *a1 <= 2 )
  {
    v11 = QuicLibrarySetParam(a1, v4, a3, a4);
    goto LABEL_29;
  }
  v12 = 0;
  memset(&Event, 0, sizeof(Event));
  if ( v13 == 5 )
  {
    v14 = (unsigned int *)*((_QWORD *)a1 + 9);
    goto LABEL_13;
  }
  if ( v13 - 3 <= 1 )
  {
    v14 = a1;
LABEL_13:
    if ( (v14[63] & 0x40) != 0 && (*((_BYTE *)v14 + 249) & 4) != 0 )
    {
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 1617, "!Connection->State.Freed");
      __int2c();
    }
    if ( (MsQuicLib & 4) != 0 || *((HANDLE *)v14 + 32) == PsGetCurrentThreadId() )
    {
      v16 = *((_BYTE *)v14 + 251) & 0x20;
      if ( !v16 )
        *((_BYTE *)v14 + 251) |= 0x20u;
      v27 = QuicLibrarySetParam(a1, v4, a3, a4);
      if ( !v16 )
        *((_BYTE *)v14 + 251) &= ~0x20u;
    }
    else
    {
      v26 = 0;
      v20 = 0;
      v23 = 0;
      v24 = &v17;
      v17 = 0;
      LODWORD(v17) = 11;
      v22 = 0;
      v25 = 0;
      v18 = 0;
      v19 = 0;
      KeInitializeEvent(&Event, NotificationEvent, 0);
      *((_QWORD *)&v18 + 1) = a1;
      *(_QWORD *)&v18 = &Event;
      *((_QWORD *)&v17 + 1) = &v27;
      *(_QWORD *)&v19 = __PAIR64__(a3, v4);
      *((_QWORD *)&v19 + 1) = a4;
      if ( v5 )
        QuicConnQueuePriorityOper(v14, &v22);
      else
        QuicConnQueueOper(v14, &v22);
      if ( (Microsoft_QuicEnableBits & 8) != 0 )
        McTemplateU0_EtwWriteTransfer(v15, QuicApiWaitOperation);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    }
    goto LABEL_30;
  }
  v27 = -1073741811;
LABEL_30:
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer(v12, QuicApiExitStatus, v27);
  return v27;
}

```

## disassembly

```asm
0x1400018a0  mov     [rsp-8+arg_0], rbx
0x1400018a5  mov     [rsp-8+arg_10], rsi
0x1400018aa  push    rbp
0x1400018ab  push    rdi
0x1400018ac  push    r12
0x1400018ae  push    r14
0x1400018b0  push    r15
0x1400018b2  lea     rbp, [rsp-37h]
0x1400018b7  sub     rsp, 0C0h
0x1400018be  xor     r10d, r10d
0x1400018c1  mov     esi, edx
0x1400018c3  btr     esi, 1Eh
0x1400018c7  mov     r14d, edx
0x1400018ca  and     r14d, 40000000h
0x1400018d1  mov     ebx, esi
0x1400018d3  and     ebx, 3F000000h
0x1400018d9  mov     r15, r9
0x1400018dc  cmp     ebx, 1000000h
0x1400018e2  mov     r12d, r8d
0x1400018e5  mov     rdi, rcx
0x1400018e8  setz    r10b
0x1400018ec  xor     eax, eax
0x1400018ee  test    rcx, rcx
0x1400018f1  setz    al
0x1400018f4  cmp     eax, r10d
0x1400018f7  jz      short loc_140001903
0x1400018f9  mov     eax, 0C000000Dh
0x1400018fe  jmp     loc_140001ADC
0x140001903  test    cs:Microsoft_QuicEnableBits, 8
0x14000190a  jz      short loc_140001917
0x14000190c  mov     r9, rdi
0x14000190f  xor     r8d, r8d
0x140001912  call    McTemplateU0qp_EtwWriteTransfer
0x140001917  and     [rbp+57h+arg_8], 0
0x14000191b  cmp     ebx, 1000000h
0x140001921  jnz     short loc_140001935
0x140001923  mov     r8, r15
0x140001926  mov     edx, r12d
0x140001929  mov     ecx, esi
0x14000192b  call    QuicLibrarySetGlobalParam
0x140001930  jmp     loc_140001ABD
0x140001935  mov     eax, [rdi]
0x140001937  cmp     eax, 2
0x14000193a  jbe     loc_140001AAD
0x140001940  xor     ecx, ecx
0x140001942  xorps   xmm0, xmm0
0x140001945  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rcx
0x140001949  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x14000194d  cmp     eax, 5
0x140001950  jnz     short loc_140001958
0x140001952  mov     rbx, [rdi+48h]
0x140001956  jmp     short loc_14000196F
0x140001958  add     eax, 0FFFFFFFDh
0x14000195b  cmp     eax, 1
0x14000195e  jbe     short loc_14000196C
0x140001960  mov     [rbp+57h+arg_8], 0C000000Dh
0x140001967  jmp     loc_140001AC0
0x14000196c  mov     rbx, rdi
0x14000196f  test    byte ptr [rbx+0FCh], 40h
0x140001976  jz      short loc_14000199B
0x140001978  test    byte ptr [rbx+0F9h], 4
0x14000197f  jz      short loc_14000199B
0x140001981  lea     r8, aConnectionStat_2; "!Connection->State.Freed"
0x140001988  mov     edx, 651h
0x14000198d  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x140001994  call    CxPlatLogAssert
0x140001999  int     2Ch; Windows NT - assertion failure
0x14000199b  test    cs:MsQuicLib, 4
0x1400019a2  jnz     loc_140001A75
0x1400019a8  call    cs:__imp_PsGetCurrentThreadId
0x1400019af  nop     dword ptr [rax+rax+00h]
0x1400019b4  cmp     [rbx+100h], rax
0x1400019bb  jz      loc_140001A75
0x1400019c1  xorps   xmm0, xmm0
0x1400019c4  lea     rcx, [rbp+57h+Event]; Event
0x1400019c8  xor     eax, eax
0x1400019ca  xor     r8d, r8d; State
0x1400019cd  mov     [rbp+57h+var_30], rax
0x1400019d1  xor     edx, edx; Type
0x1400019d3  mov     [rbp+57h+var_80], eax
0x1400019d6  lea     rax, [rbp+57h+var_B0]
0x1400019da  movups  [rbp+57h+var_50], xmm0
0x1400019de  mov     qword ptr [rbp+57h+var_50+8], rax
0x1400019e2  movups  [rbp+57h+var_B0], xmm0
0x1400019e6  mov     dword ptr [rbp+57h+var_B0], 0Bh
0x1400019ed  movups  [rbp+57h+var_60], xmm0
0x1400019f1  movups  [rbp+57h+var_40], xmm0
0x1400019f5  movups  [rbp+57h+var_A0], xmm0
0x1400019f9  movups  [rbp+57h+var_90], xmm0
0x1400019fd  call    cs:__imp_KeInitializeEvent
0x140001a04  nop     dword ptr [rax+rax+00h]
0x140001a09  mov     qword ptr [rbp+57h+var_A0+8], rdi
0x140001a0d  lea     rax, [rbp+57h+Event]
0x140001a11  mov     qword ptr [rbp+57h+var_A0], rax
0x140001a15  lea     rax, [rbp+57h+arg_8]
0x140001a19  mov     qword ptr [rbp+57h+var_B0+8], rax
0x140001a1d  lea     rdx, [rbp+57h+var_60]
0x140001a21  mov     dword ptr [rbp+57h+var_90], esi
0x140001a24  mov     rcx, rbx
0x140001a27  mov     dword ptr [rbp+57h+var_90+4], r12d
0x140001a2b  mov     qword ptr [rbp+57h+var_90+8], r15
0x140001a2f  test    r14d, r14d
0x140001a32  jz      short loc_140001A3B
0x140001a34  call    QuicConnQueuePriorityOper
0x140001a39  jmp     short loc_140001A40
0x140001a3b  call    QuicConnQueueOper
0x140001a40  test    cs:Microsoft_QuicEnableBits, 8
0x140001a47  jz      short loc_140001A55
0x140001a49  lea     rdx, QuicApiWaitOperation
0x140001a50  call    McTemplateU0_EtwWriteTransfer
0x140001a55  and     [rsp+0E0h+var_C0], 0
0x140001a5b  lea     rcx, [rbp+57h+Event]; Object
0x140001a5f  xor     r9d, r9d; Alertable
0x140001a62  xor     r8d, r8d; WaitMode
0x140001a65  xor     edx, edx; WaitReason
0x140001a67  call    cs:__imp_KeWaitForSingleObject
0x140001a6e  nop     dword ptr [rax+rax+00h]
0x140001a73  jmp     short loc_140001AC0
0x140001a75  mov     al, [rbx+0FBh]
0x140001a7b  mov     r14b, al
0x140001a7e  and     r14b, 20h
0x140001a82  jnz     short loc_140001A8C
0x140001a84  or      al, 20h
0x140001a86  mov     [rbx+0FBh], al
0x140001a8c  mov     r9, r15
0x140001a8f  mov     r8d, r12d
0x140001a92  mov     edx, esi
0x140001a94  mov     rcx, rdi
0x140001a97  call    QuicLibrarySetParam
0x140001a9c  mov     [rbp+57h+arg_8], eax
0x140001a9f  test    r14b, r14b
0x140001aa2  jnz     short loc_140001AC0
0x140001aa4  and     byte ptr [rbx+0FBh], 0DFh
0x140001aab  jmp     short loc_140001AC0
0x140001aad  mov     r9, r15
0x140001ab0  mov     r8d, r12d
0x140001ab3  mov     edx, esi
0x140001ab5  mov     rcx, rdi
0x140001ab8  call    QuicLibrarySetParam
0x140001abd  mov     [rbp+57h+arg_8], eax
0x140001ac0  test    cs:Microsoft_QuicEnableBits, 8
0x140001ac7  jz      short loc_140001AD9
0x140001ac9  mov     r8d, [rbp+57h+arg_8]
0x140001acd  lea     rdx, QuicApiExitStatus
0x140001ad4  call    McTemplateU0q_EtwWriteTransfer
0x140001ad9  mov     eax, [rbp+57h+arg_8]
0x140001adc  lea     r11, [rsp+0E0h+var_20]
0x140001ae4  mov     rbx, [r11+30h]
0x140001ae8  mov     rsi, [r11+40h]
0x140001aec  mov     rsp, r11
0x140001aef  pop     r15
0x140001af1  pop     r14
0x140001af3  pop     r12
0x140001af5  pop     rdi
0x140001af6  pop     rbp
0x140001af7  retn
```
