# EaiSignalCallback

- ea: `0x1800069d0`
- end: `0x180006c0b`
- name: `EaiSignalCallback`
- size: `571`
- prototype: `ULONG __fastcall(int, __int64, int, int, int, int, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800038c0`
- `0x180005cc0`
- `0x180008410`

## callees

- `0x1800064b0`
- `0x1800066d0`
- `0x1800069d0`
- `0x1800072e0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006ab3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006be5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006ab3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006be5`

## pseudocode

```c
ULONG __fastcall EaiSignalCallback(int a1, __int64 a2, int a3, int a4, int a5, int a6, __int64 a7)
{
  __int64 v11; // r8
  ULONG result; // eax
  int v13; // eax
  unsigned int v14; // [rsp+40h] [rbp-91h] BYREF
  int v15; // [rsp+44h] [rbp-8Dh] BYREF
  __int64 v16; // [rsp+48h] [rbp-89h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-81h] BYREF
  EVENT_DESCRIPTOR v18; // [rsp+60h] [rbp-71h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-61h] BYREF
  char *v20; // [rsp+80h] [rbp-51h]
  int v21; // [rsp+88h] [rbp-49h]
  int v22; // [rsp+8Ch] [rbp-45h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+90h] [rbp-41h]
  __int64 v24; // [rsp+98h] [rbp-39h]
  unsigned int *v25; // [rsp+A0h] [rbp-31h]
  __int64 v26; // [rsp+A8h] [rbp-29h]
  int *v27; // [rsp+B0h] [rbp-21h]
  __int64 v28; // [rsp+B8h] [rbp-19h]

  if ( (unsigned int)dword_180012000 > 4 )
  {
    v16 = a2;
    p_EventDescriptor = (EVENT_DESCRIPTOR *)&v16;
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_180012008;
    v24 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v20 = byte_18000F2AB;
    UserData.Reserved = 2;
    v21 = 32;
    v22 = 1;
    v14 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  if ( (*(_BYTE *)(a2 + 140) & 0x10) != 0 )
  {
    EaiSignalAggregateEvent(a2, a1, a3, a4, a5, a6, a7);
    goto LABEL_10;
  }
  if ( a1 )
  {
    if ( a1 != 1 )
      goto LABEL_10;
    v11 = *(_QWORD *)(a2 + 32);
  }
  else
  {
    v11 = *(_QWORD *)(a2 + 24);
  }
  EaiSignalAggregateCallback(a2, a3, v11, a4, a5);
LABEL_10:
  result = dword_180012000;
  if ( (unsigned int)dword_180012000 > 4 )
  {
    *(_QWORD *)&EventDescriptor.Id = a2;
    p_EventDescriptor = &EventDescriptor;
    v13 = (*(_DWORD *)(a2 + 140) >> 4) & 1;
    v24 = 8;
    v14 = v13;
    v25 = &v14;
    v27 = &v15;
    *(_DWORD *)&v18.Level = 516;
    UserData.Ptr = (ULONGLONG)off_180012008;
    v26 = 4;
    v15 = a1;
    v28 = 4;
    *(_DWORD *)&v18.Id = 184549376;
    v18.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v20 = byte_18000F1B5;
    UserData.Reserved = 2;
    v21 = 61;
    v22 = 1;
    LODWORD(v16) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    return EventWriteTransfer(RegHandle, &v18, 0, 0, 5u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x1800069d0  push    rbp
0x1800069d2  push    rbx
0x1800069d3  push    rsi
0x1800069d4  push    rdi
0x1800069d5  push    r12
0x1800069d7  push    r13
0x1800069d9  push    r14
0x1800069db  push    r15
0x1800069dd  lea     rbp, [rsp-7]
0x1800069e2  sub     rsp, 0D8h
0x1800069e9  mov     rax, cs:__security_cookie
0x1800069f0  xor     rax, rsp
0x1800069f3  mov     [rbp+3Fh+var_50], rax
0x1800069f7  mov     eax, cs:dword_180012000
0x1800069fd  lea     r12, _TraceLoggingMetadataEnd
0x180006a04  mov     r15, [rbp+3Fh+arg_30]
0x180006a08  xor     r13d, r13d
0x180006a0b  mov     edi, ecx
0x180006a0d  mov     r14, r9
0x180006a10  lea     rcx, _TraceLoggingMetadata
0x180006a17  mov     rsi, r8
0x180006a1a  mov     rbx, rdx
0x180006a1d  cmp     eax, 4
0x180006a20  jbe     loc_180006AB9
0x180006a26  mov     [rsp+110h+var_C8], rdx
0x180006a2b  lea     rax, [rsp+110h+var_C8]
0x180006a30  mov     [rbp+3Fh+var_80], rax
0x180006a34  lea     rdx, [rsp+110h+EventDescriptor]; EventDescriptor
0x180006a39  movzx   eax, cs:word_18000F2A1
0x180006a40  xor     r9d, r9d; RelatedActivityId
0x180006a43  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x180006a46  xor     r8d, r8d; ActivityId
0x180006a49  mov     rax, cs:off_180012008
0x180006a50  mov     [rbp+3Fh+var_A0.Ptr], rax
0x180006a54  mov     [rbp+3Fh+var_78], 8
0x180006a5c  mov     dword ptr [rsp+110h+EventDescriptor.Id], 0B000000h
0x180006a64  mov     [rbp+3Fh+EventDescriptor.Keyword], r13
0x180006a68  movzx   eax, word ptr [rax]
0x180006a6b  mov     [rbp+3Fh+var_A0.Size], eax
0x180006a6e  lea     rax, byte_18000F2AB
0x180006a75  mov     [rbp+3Fh+var_90], rax
0x180006a79  mov     rax, r12
0x180006a7c  sub     eax, ecx
0x180006a7e  mov     dword ptr [rbp+3Fh+var_A0.0Ch], 2
0x180006a85  mov     [rbp+3Fh+var_88], 20h ; ' '
0x180006a8c  mov     [rbp+3Fh+var_84], 1
0x180006a93  mov     [rsp+110h+var_D0], eax
0x180006a97  mov     eax, [rsp+110h+var_D0]
0x180006a9b  mov     rcx, cs:RegHandle; RegHandle
0x180006aa2  lea     rax, [rbp+3Fh+var_A0]
0x180006aa6  mov     [rsp+110h+UserData], rax; UserData
0x180006aab  mov     [rsp+110h+UserDataCount], 3; UserDataCount
0x180006ab3  call    cs:__imp_EventWriteTransfer
0x180006ab9  test    byte ptr [rbx+8Ch], 10h
0x180006ac0  jz      short loc_180006AE7
0x180006ac2  mov     eax, [rbp+3Fh+arg_28]
0x180006ac5  mov     r9, r14
0x180006ac8  mov     [rsp+110h+var_E0], r15
0x180006acd  mov     r8, rsi
0x180006ad0  mov     dword ptr [rsp+110h+UserData], eax
0x180006ad4  mov     edx, edi
0x180006ad6  mov     eax, [rbp+3Fh+arg_20]
0x180006ad9  mov     rcx, rbx
0x180006adc  mov     [rsp+110h+UserDataCount], eax
0x180006ae0  call    EaiSignalAggregateEvent
0x180006ae5  jmp     short loc_180006B0F
0x180006ae7  test    edi, edi
0x180006ae9  jnz     short loc_180006AF1
0x180006aeb  mov     r8, [rbx+18h]
0x180006aef  jmp     short loc_180006AFA
0x180006af1  cmp     edi, 1
0x180006af4  jnz     short loc_180006B0F
0x180006af6  mov     r8, [rbx+20h]
0x180006afa  mov     eax, [rbp+3Fh+arg_20]
0x180006afd  mov     r9, r14
0x180006b00  mov     rdx, rsi
0x180006b03  mov     [rsp+110h+UserDataCount], eax
0x180006b07  mov     rcx, rbx
0x180006b0a  call    EaiSignalAggregateCallback
0x180006b0f  mov     eax, cs:dword_180012000
0x180006b15  cmp     eax, 4
0x180006b18  jbe     loc_180006BEB
0x180006b1e  lea     rax, [rsp+110h+EventDescriptor]
0x180006b23  mov     qword ptr [rsp+110h+EventDescriptor.Id], rbx
0x180006b28  mov     [rbp+3Fh+var_80], rax
0x180006b2c  lea     rdx, [rbp+3Fh+var_B0]; EventDescriptor
0x180006b30  mov     eax, [rbx+8Ch]
0x180006b36  xor     r9d, r9d; RelatedActivityId
0x180006b39  shr     eax, 4
0x180006b3c  xor     r8d, r8d; ActivityId
0x180006b3f  and     eax, 1
0x180006b42  mov     [rbp+3Fh+var_78], 8
0x180006b4a  mov     [rsp+110h+var_D0], eax
0x180006b4e  lea     rax, [rsp+110h+var_D0]
0x180006b53  mov     [rbp+3Fh+var_70], rax
0x180006b57  lea     rax, [rsp+110h+var_CC]
0x180006b5c  mov     [rbp+3Fh+var_60], rax
0x180006b60  movzx   eax, cs:word_18000F1AB
0x180006b67  mov     dword ptr [rbp+3Fh+var_B0.Level], eax
0x180006b6a  mov     rax, cs:off_180012008
0x180006b71  mov     [rbp+3Fh+var_A0.Ptr], rax
0x180006b75  mov     [rbp+3Fh+var_68], 4
0x180006b7d  mov     [rsp+110h+var_CC], edi
0x180006b81  mov     [rbp+3Fh+var_58], 4
0x180006b89  mov     dword ptr [rbp+3Fh+var_B0.Id], 0B000000h
0x180006b90  mov     [rbp+3Fh+var_B0.Keyword], r13
0x180006b94  movzx   eax, word ptr [rax]
0x180006b97  mov     [rbp+3Fh+var_A0.Size], eax
0x180006b9a  lea     rax, byte_18000F1B5
0x180006ba1  mov     [rbp+3Fh+var_90], rax
0x180006ba5  lea     rax, _TraceLoggingMetadata
0x180006bac  sub     r12d, eax
0x180006baf  mov     dword ptr [rbp+3Fh+var_A0.0Ch], 2
0x180006bb6  mov     [rbp+3Fh+var_88], 3Dh ; '='
0x180006bbd  mov     [rbp+3Fh+var_84], 1
0x180006bc4  mov     dword ptr [rsp+110h+var_C8], r12d
0x180006bc9  mov     eax, dword ptr [rsp+110h+var_C8]
0x180006bcd  mov     rcx, cs:RegHandle; RegHandle
0x180006bd4  lea     rax, [rbp+3Fh+var_A0]
0x180006bd8  mov     [rsp+110h+UserData], rax; UserData
0x180006bdd  mov     [rsp+110h+UserDataCount], 5; UserDataCount
0x180006be5  call    cs:__imp_EventWriteTransfer
0x180006beb  mov     rcx, [rbp+3Fh+var_50]
0x180006bef  xor     rcx, rsp; StackCookie
0x180006bf2  call    __security_check_cookie
0x180006bf7  add     rsp, 0D8h
0x180006bfe  pop     r15
0x180006c00  pop     r14
0x180006c02  pop     r13
0x180006c04  pop     r12
0x180006c06  pop     rdi
0x180006c07  pop     rsi
0x180006c08  pop     rbx
0x180006c09  pop     rbp
0x180006c0a  retn
```
