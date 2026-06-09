# PrjfSendCancelCommandInNewThread

- ea: `0x1400339a8`
- end: `0x140033bc8`
- name: `PrjfSendCancelCommandInNewThread`
- size: `544`
- prototype: `void __fastcall(PVOID FltObject, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140033de8`

## callees

- `0x14000d128`
- `0x140010048`
- `0x1400108a4`
- `0x140032fd8`
- `0x1400339a8`
- `0x14003a5cc`

## import_xrefs

- `FLTMGR!FltFreeGenericWorkItem` at `0x140033b8f`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140033b8f`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140033b3f`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140033b3f`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140033a9d`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140033a9d`

## pseudocode

```c
void __fastcall PrjfSendCancelCommandInNewThread(PVOID FltObject, __int64 a2)
{
  __int64 v2; // rax
  __int128 v4; // xmm0
  int v6; // edx
  int v7; // r8d
  PVOID v8; // rbx
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // rax
  int v10; // edx
  int v11; // r8d
  struct _FLT_GENERIC_WORKITEM *v12; // rdi
  int v13; // edx
  int v14; // r8d
  int Context; // [rsp+28h] [rbp-29h]
  int Contexta; // [rsp+28h] [rbp-29h]
  int v17; // [rsp+30h] [rbp-21h]
  int v18; // [rsp+38h] [rbp-19h]
  int v19; // [rsp+40h] [rbp-11h]
  int v20; // [rsp+48h] [rbp-9h]
  _QWORD v21[2]; // [rsp+78h] [rbp+27h] BYREF
  __int128 v22; // [rsp+88h] [rbp+37h] BYREF
  unsigned int v23; // [rsp+C0h] [rbp+6Fh] BYREF
  PVOID Entry; // [rsp+C8h] [rbp+77h] BYREF

  v2 = a2 + *(unsigned int *)(a2 + 864);
  Entry = 0;
  v21[0] = 0;
  v21[1] = v2;
  v4 = *(_OWORD *)(a2 + 8);
  LOWORD(v21[0]) = *(_WORD *)(a2 + 868);
  v23 = 0;
  v22 = v4;
  if ( (int)PrjfPrepareCommandForFilePath((unsigned __int16 *)v21, &v22, 8, 0, 0, 0, 0, &Entry, &v23) >= 0 )
  {
    v8 = Entry;
    *((_DWORD *)Entry + 6) = *(_DWORD *)(a2 + 24);
    GenericWorkItem = FltAllocateGenericWorkItem();
    v12 = GenericWorkItem;
    if ( GenericWorkItem )
    {
      if ( FltQueueGenericWorkItem(
             GenericWorkItem,
             FltObject,
             (PFLT_GENERIC_WORKITEM_ROUTINE)PrjfSendCancelCommandWorker,
             CriticalWorkQueue,
             v8) >= 0 )
      {
        v8 = 0;
      }
      else
      {
        if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = BYTE1(xmmword_14001A3D0) & 0x40;
          LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDLd(
            (unsigned int)&WPP_RECORDER_INITIALIZED,
            v13,
            v14,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            Contexta,
            v17,
            v18,
            v19,
            v20);
        }
        FltFreeGenericWorkItem(v12);
      }
    }
    else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
           || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        v10,
        v11,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        146,
        (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        59,
        154);
    }
  }
  else
  {
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZL(
        (unsigned int)&WPP_RECORDER_INITIALIZED,
        v6,
        v7,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        Context,
        v17,
        v18,
        v19,
        v20);
    }
    v8 = Entry;
  }
  if ( v8 )
    PrjfFreeCommandBuffer(v8);
}

```

## disassembly

```asm
0x1400339a8  mov     r11, rsp
0x1400339ab  mov     [r11+8], rbx
0x1400339af  mov     [r11+20h], rsi
0x1400339b3  push    rbp
0x1400339b4  push    rdi
0x1400339b5  push    r14
0x1400339b7  lea     rbp, [r11-5Fh]
0x1400339bb  sub     rsp, 90h
0x1400339c2  mov     eax, [rdx+360h]
0x1400339c8  xorps   xmm0, xmm0
0x1400339cb  add     rax, rdx
0x1400339ce  mov     [rbp+57h+Entry], 0
0x1400339d6  movups  [rbp+57h+var_30], xmm0
0x1400339da  mov     qword ptr [rbp+57h+var_30+8], rax
0x1400339de  xor     r9d, r9d
0x1400339e1  movzx   eax, word ptr [rdx+364h]
0x1400339e8  mov     rsi, rdx
0x1400339eb  movups  xmm0, xmmword ptr [rdx+8]
0x1400339ef  mov     word ptr [rbp+57h+var_30], ax
0x1400339f3  lea     rdx, [rbp+57h+var_20]
0x1400339f7  lea     rax, [rbp+57h+arg_8]
0x1400339fb  mov     [rbp+57h+arg_8], 0
0x140033a02  mov     [r11-68h], rax
0x140033a06  lea     r8d, [r9+8]
0x140033a0a  lea     rax, [rbp+57h+Entry]
0x140033a0e  mov     r14, rcx
0x140033a11  mov     [r11-70h], rax
0x140033a15  lea     rcx, [rbp+57h+var_30]
0x140033a19  mov     qword ptr [r11-78h], 0
0x140033a21  mov     qword ptr [r11-80h], 0
0x140033a29  mov     [rsp+0A0h+Context], 0
0x140033a32  movdqu  [rbp+57h+var_20], xmm0
0x140033a37  call    PrjfPrepareCommandForFilePath
0x140033a3c  mov     r9d, eax
0x140033a3f  test    eax, eax
0x140033a41  jns     short loc_140033A93
0x140033a43  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140033a49  lea     rcx, WPP_RECORDER_INITIALIZED
0x140033a50  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140033a57  setnz   r8b
0x140033a5b  and     dl, 40h
0x140033a5e  jnz     short loc_140033A65
0x140033a60  test    r8b, r8b
0x140033a63  jz      short loc_140033A8A
0x140033a65  mov     eax, [rsi+18h]
0x140033a68  mov     [rsp+0A0h+var_40], eax
0x140033a6c  lea     rax, [rbp+57h+var_30]
0x140033a70  mov     qword ptr [rsp+0A0h+var_48], rax
0x140033a75  mov     dword ptr [rsp+0A0h+var_50], r9d
0x140033a7a  mov     r9, cs:WPP_GLOBAL_Control
0x140033a81  mov     r9, [r9+40h]
0x140033a85  call    WPP_RECORDER_AND_TRACE_SF_sDdZL
0x140033a8a  mov     rbx, [rbp+57h+Entry]
0x140033a8e  jmp     loc_140033B9F
0x140033a93  mov     eax, [rsi+18h]
0x140033a96  mov     rbx, [rbp+57h+Entry]
0x140033a9a  mov     [rbx+18h], eax
0x140033a9d  call    cs:__imp_FltAllocateGenericWorkItem
0x140033aa4  nop     dword ptr [rax+rax+00h]
0x140033aa9  mov     rdi, rax
0x140033aac  test    rax, rax
0x140033aaf  jnz     short loc_140033B2A
0x140033ab1  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140033ab7  lea     rcx, WPP_RECORDER_INITIALIZED
0x140033abe  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140033ac5  setnz   r8b
0x140033ac9  and     dl, 40h
0x140033acc  jnz     short loc_140033AD7
0x140033ace  test    r8b, r8b
0x140033ad1  jz      loc_140033B9F
0x140033ad7  mov     r9, cs:WPP_GLOBAL_Control
0x140033ade  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140033ae5  mov     dword ptr [rsp+0A0h+var_50], 0C000009Ah
0x140033aed  mov     ecx, 20Eh
0x140033af2  mov     [rsp+0A0h+var_58], 103Bh
0x140033afa  mov     qword ptr [rsp+0A0h+var_60], rax
0x140033aff  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140033b06  mov     r9, [r9+40h]
0x140033b0a  mov     [rsp+0A0h+var_68], rax
0x140033b0f  mov     word ptr [rsp+0A0h+var_70], 92h
0x140033b16  mov     dword ptr [rsp+0A0h+var_78], 0Eh
0x140033b1e  mov     byte ptr [rsp+0A0h+Context], 2
0x140033b23  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140033b28  jmp     short loc_140033B9F
0x140033b2a  xor     r9d, r9d; QueueType
0x140033b2d  mov     [rsp+0A0h+Context], rbx; Context
0x140033b32  lea     r8, PrjfSendCancelCommandWorker; WorkerRoutine
0x140033b39  mov     rdx, r14; FltObject
0x140033b3c  mov     rcx, rdi; FltWorkItem
0x140033b3f  call    cs:__imp_FltQueueGenericWorkItem
0x140033b46  nop     dword ptr [rax+rax+00h]
0x140033b4b  test    eax, eax
0x140033b4d  jns     short loc_140033B9D
0x140033b4f  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140033b55  lea     rcx, WPP_RECORDER_INITIALIZED
0x140033b5c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140033b63  setnz   r8b
0x140033b67  and     dl, 40h
0x140033b6a  jnz     short loc_140033B71
0x140033b6c  test    r8b, r8b
0x140033b6f  jz      short loc_140033B8C
0x140033b71  mov     r9, cs:WPP_GLOBAL_Control
0x140033b78  mov     [rsp+0A0h+var_48], eax
0x140033b7c  mov     eax, [rsi+18h]
0x140033b7f  mov     dword ptr [rsp+0A0h+var_50], eax
0x140033b83  mov     r9, [r9+40h]
0x140033b87  call    WPP_RECORDER_AND_TRACE_SF_sDLd
0x140033b8c  mov     rcx, rdi; FltWorkItem
0x140033b8f  call    cs:__imp_FltFreeGenericWorkItem
0x140033b96  nop     dword ptr [rax+rax+00h]
0x140033b9b  jmp     short loc_140033B9F
0x140033b9d  xor     ebx, ebx
0x140033b9f  test    rbx, rbx
0x140033ba2  jz      short loc_140033BAF
0x140033ba4  mov     edx, [rbp+57h+arg_8]
0x140033ba7  mov     rcx, rbx; Entry
0x140033baa  call    PrjfFreeCommandBuffer
0x140033baf  lea     r11, [rsp+0A0h+var_10]
0x140033bb7  mov     rbx, [r11+20h]
0x140033bbb  mov     rsi, [r11+38h]
0x140033bbf  mov     rsp, r11
0x140033bc2  pop     r14
0x140033bc4  pop     rdi
0x140033bc5  pop     rbp
0x140033bc6  retn
```
