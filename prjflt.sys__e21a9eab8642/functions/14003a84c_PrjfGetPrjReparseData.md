# PrjfGetPrjReparseData

- ea: `0x14003a84c`
- end: `0x14003ac61`
- name: `PrjfGetPrjReparseData`
- size: `1045`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, unsigned __int16 **, _BYTE *)`
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140002f3c`
- `0x14002e1a4`
- `0x14002e374`

## callees

- `0x14000b1d0`
- `0x14000dab0`
- `0x14003a84c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003a935`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ac32`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a935`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ac32`
- `ntoskrnl!ExAllocatePool2` at `0x14003a890`
- `ntoskrnl!ExAllocatePool2` at `0x14003a890`
- `FLTMGR!FltFsControlFile` at `0x14003a8d5`
- `FLTMGR!FltFsControlFile` at `0x14003a8d5`

## pseudocode

```c
__int64 __fastcall PrjfGetPrjReparseData(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        unsigned __int16 **a3,
        _BYTE *a4)
{
  ULONG v5; // edi
  unsigned __int16 *OutputBuffer; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  NTSTATUS v12; // edi
  __int64 v13; // r8
  int v14; // edi
  int v15; // edx
  char v16; // r10
  unsigned __int16 v17; // ax
  __int16 OutputBufferLength; // [rsp+30h] [rbp-58h]
  char v20; // [rsp+48h] [rbp-40h]
  char v21; // [rsp+50h] [rbp-38h]
  char v22; // [rsp+58h] [rbp-30h]
  ULONG LengthReturned; // [rsp+98h] [rbp+10h] BYREF

  v5 = FileObject->FileName.Length + 26;
  LengthReturned = 0;
  while ( 1 )
  {
    OutputBuffer = (unsigned __int16 *)ExAllocatePool2(256, v5, 1769097808);
    if ( !OutputBuffer )
      break;
    v12 = FltFsControlFile(Instance, FileObject, 0x900A8u, 0, 0, OutputBuffer, v5, &LengthReturned);
    if ( v12 == 259 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v11, v10, v13);
    }
    else if ( v12 == -1073741195 )
    {
      *a4 = 0;
      v12 = 0;
      *a3 = 0;
      goto LABEL_39;
    }
    if ( LengthReturned < 8 )
      goto LABEL_17;
    if ( *(_DWORD *)OutputBuffer != -1879048164 )
    {
      v12 = 0;
      *a4 = 0;
      *a3 = 0;
      goto LABEL_39;
    }
    if ( v12 != -2147483643 )
    {
LABEL_17:
      if ( v12 < 0 )
      {
        if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = xmmword_14001A3D0 & 0x20;
          LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDqd(
            517,
            v10,
            v13,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            5,
            26,
            (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
            222,
            (char)FileObject,
            v12);
        }
        goto LABEL_39;
      }
      v15 = OutputBuffer[2];
      if ( LengthReturned < v15 + 8 )
      {
        v15 = -1073689086;
        v12 = -1073689086;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        v16 = xmmword_14001A3E0 & 0x20;
        if ( (xmmword_14001A3E0 & 0x20) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_39;
        v22 = 2;
        v21 = (char)FileObject;
        v20 = -9;
        OutputBufferLength = 28;
        goto LABEL_14;
      }
      v17 = OutputBuffer[144];
      if ( (unsigned __int16)(v17 + 282) < v17 )
      {
        v15 = -1073689086;
        v12 = -1073689086;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        v16 = xmmword_14001A3E0 & 0x20;
        if ( (xmmword_14001A3E0 & 0x20) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_39;
        v22 = 2;
        v21 = (char)FileObject;
        v20 = 5;
        OutputBufferLength = 29;
        goto LABEL_14;
      }
      if ( (_WORD)v15 != v17 + 282 )
      {
        v15 = -1073689086;
        v12 = -1073689086;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        v16 = xmmword_14001A3E0 & 0x20;
        if ( (xmmword_14001A3E0 & 0x20) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_39;
        v22 = 2;
        v21 = (char)FileObject;
        v20 = 20;
        OutputBufferLength = 30;
        goto LABEL_14;
      }
      if ( *((_DWORD *)OutputBuffer + 2) >= 2u )
      {
        v12 = 0;
        *a4 = 1;
        *a3 = OutputBuffer;
        return (unsigned int)v12;
      }
      v12 = -1073741637;
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v15) = xmmword_14001A3E0 & 0x20;
      if ( (xmmword_14001A3E0 & 0x20) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_39;
      v22 = -69;
      v21 = (char)FileObject;
      v20 = 32;
      OutputBufferLength = 31;
LABEL_15:
      WPP_RECORDER_AND_TRACE_SF_sDqd(
        1029,
        v15,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        4,
        5,
        OutputBufferLength,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        v20,
        v21,
        v22);
LABEL_39:
      ExFreePoolWithTag(OutputBuffer, 0x69724A50u);
      return (unsigned int)v12;
    }
    v14 = OutputBuffer[2];
    if ( (unsigned __int16)v14 < 0x11Au )
    {
      v15 = -1073689086;
      v12 = -1073689086;
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      v16 = xmmword_14001A3E0 & 0x20;
      if ( (xmmword_14001A3E0 & 0x20) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_39;
      v22 = 2;
      v21 = (char)FileObject;
      v20 = -49;
      OutputBufferLength = 25;
LABEL_14:
      LOBYTE(v15) = v16;
      goto LABEL_15;
    }
    ExFreePoolWithTag(OutputBuffer, 0x69724A50u);
    v5 = v14 + 8;
  }
  return (unsigned int)-1073741670;
}

```

## disassembly

```asm
0x14003a84c  mov     rax, rsp
0x14003a84f  mov     [rax+8], rbx
0x14003a853  mov     [rax+18h], rbp
0x14003a857  push    rsi
0x14003a858  push    rdi
0x14003a859  push    r13
0x14003a85b  push    r14
0x14003a85d  push    r15
0x14003a85f  sub     rsp, 60h
0x14003a863  movzx   edi, word ptr [rdx+58h]
0x14003a867  mov     rsi, r9
0x14003a86a  add     edi, 1Ah
0x14003a86d  mov     dword ptr [rax+10h], 0
0x14003a874  mov     r14, r8
0x14003a877  mov     rbp, rdx
0x14003a87a  mov     r15, rcx
0x14003a87d  mov     r13d, 11Ah
0x14003a883  mov     edx, edi
0x14003a885  mov     ecx, 100h
0x14003a88a  mov     r8d, 69724A50h
0x14003a890  call    cs:__imp_ExAllocatePool2
0x14003a897  nop     dword ptr [rax+rax+00h]
0x14003a89c  mov     rbx, rax
0x14003a89f  test    rax, rax
0x14003a8a2  jz      loc_14003AC40
0x14003a8a8  lea     rax, [rsp+88h+arg_8]
0x14003a8b0  xor     r9d, r9d; InputBuffer
0x14003a8b3  mov     [rsp+88h+LengthReturned], rax; LengthReturned
0x14003a8b8  mov     r8d, 900A8h; FsControlCode
0x14003a8be  mov     dword ptr [rsp+88h+OutputBufferLength], edi; OutputBufferLength
0x14003a8c2  mov     rdx, rbp; FileObject
0x14003a8c5  mov     [rsp+88h+OutputBuffer], rbx; OutputBuffer
0x14003a8ca  mov     rcx, r15; Instance
0x14003a8cd  mov     [rsp+88h+InputBufferLength], 0; InputBufferLength
0x14003a8d5  call    cs:__imp_FltFsControlFile
0x14003a8dc  nop     dword ptr [rax+rax+00h]
0x14003a8e1  mov     edi, eax
0x14003a8e3  cmp     eax, 103h
0x14003a8e8  jnz     short loc_14003A8F1
0x14003a8ea  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003a8ef  jmp     short loc_14003A8FD
0x14003a8f1  cmp     edi, 0C0000275h
0x14003a8f7  jz      loc_14003AC1E
0x14003a8fd  cmp     [rsp+88h+arg_8], 8
0x14003a905  jb      loc_14003A9DF
0x14003a90b  cmp     dword ptr [rbx], 9000001Ch
0x14003a911  jnz     loc_14003A9D2
0x14003a917  cmp     edi, 80000005h
0x14003a91d  jnz     loc_14003A9DF
0x14003a923  movzx   edi, word ptr [rbx+4]
0x14003a927  cmp     di, r13w
0x14003a92b  jb      short loc_14003A949
0x14003a92d  mov     edx, 69724A50h; Tag
0x14003a932  mov     rcx, rbx; P
0x14003a935  call    cs:__imp_ExFreePoolWithTag
0x14003a93c  nop     dword ptr [rax+rax+00h]
0x14003a941  add     edi, 8
0x14003a944  jmp     loc_14003A883
0x14003a949  mov     edx, 0C000CE02h
0x14003a94e  mov     edi, edx
0x14003a950  mov     r10b, byte ptr cs:xmmword_14001A3E0
0x14003a957  lea     rax, WPP_RECORDER_INITIALIZED
0x14003a95e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003a965  setnz   r8b
0x14003a969  and     r10b, 20h
0x14003a96d  jnz     short loc_14003A978
0x14003a96f  test    r8b, r8b
0x14003a972  jz      loc_14003AC2A
0x14003a978  mov     dword ptr [rsp+88h+var_30], edx
0x14003a97c  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003a983  mov     [rsp+88h+var_38], rbp
0x14003a988  mov     dword ptr [rsp+88h+var_40], 3CFh
0x14003a990  mov     [rsp+88h+var_48], rax
0x14003a995  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003a99c  mov     [rsp+88h+LengthReturned], rax
0x14003a9a1  mov     [rsp+88h+OutputBufferLength], 19h
0x14003a9a8  mov     ecx, 405h
0x14003a9ad  mov     dl, r10b
0x14003a9b0  mov     dword ptr [rsp+88h+OutputBuffer], 5
0x14003a9b8  mov     byte ptr [rsp+88h+InputBufferLength], 4
0x14003a9bd  mov     r9, cs:WPP_GLOBAL_Control
0x14003a9c4  mov     r9, [r9+40h]
0x14003a9c8  call    WPP_RECORDER_AND_TRACE_SF_sDqd
0x14003a9cd  jmp     loc_14003AC2A
0x14003a9d2  xor     edi, edi
0x14003a9d4  mov     [rsi], dil
0x14003a9d7  mov     [r14], rdi
0x14003a9da  jmp     loc_14003AC2A
0x14003a9df  test    edi, edi
0x14003a9e1  js      loc_14003ABB5
0x14003a9e7  movzx   edx, word ptr [rbx+4]
0x14003a9eb  lea     eax, [rdx+8]
0x14003a9ee  cmp     [rsp+88h+arg_8], eax
0x14003a9f5  jnb     short loc_14003AA5B
0x14003a9f7  mov     edx, 0C000CE02h
0x14003a9fc  mov     edi, edx
0x14003a9fe  mov     r10b, byte ptr cs:xmmword_14001A3E0
0x14003aa05  lea     rax, WPP_RECORDER_INITIALIZED
0x14003aa0c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003aa13  setnz   r8b
0x14003aa17  and     r10b, 20h
0x14003aa1b  jnz     short loc_14003AA26
0x14003aa1d  test    r8b, r8b
0x14003aa20  jz      loc_14003AC2A
0x14003aa26  mov     dword ptr [rsp+88h+var_30], edx
0x14003aa2a  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003aa31  mov     [rsp+88h+var_38], rbp
0x14003aa36  mov     dword ptr [rsp+88h+var_40], 3F7h
0x14003aa3e  mov     [rsp+88h+var_48], rax
0x14003aa43  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003aa4a  mov     [rsp+88h+LengthReturned], rax
0x14003aa4f  mov     [rsp+88h+OutputBufferLength], 1Ch
0x14003aa56  jmp     loc_14003A9A8
0x14003aa5b  movzx   eax, word ptr [rbx+120h]
0x14003aa62  lea     ecx, [rax+r13]
0x14003aa66  cmp     cx, ax
0x14003aa69  jb      loc_14003AB50
0x14003aa6f  cmp     dx, cx
0x14003aa72  jz      short loc_14003AAD8
0x14003aa74  mov     edx, 0C000CE02h
0x14003aa79  mov     edi, edx
0x14003aa7b  mov     r10b, byte ptr cs:xmmword_14001A3E0
0x14003aa82  lea     rax, WPP_RECORDER_INITIALIZED
0x14003aa89  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003aa90  setnz   r8b
0x14003aa94  and     r10b, 20h
0x14003aa98  jnz     short loc_14003AAA3
0x14003aa9a  test    r8b, r8b
0x14003aa9d  jz      loc_14003AC2A
0x14003aaa3  mov     dword ptr [rsp+88h+var_30], edx
0x14003aaa7  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003aaae  mov     [rsp+88h+var_38], rbp
0x14003aab3  mov     dword ptr [rsp+88h+var_40], 414h
0x14003aabb  mov     [rsp+88h+var_48], rax
0x14003aac0  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003aac7  mov     [rsp+88h+LengthReturned], rax
0x14003aacc  mov     [rsp+88h+OutputBufferLength], 1Eh
0x14003aad3  jmp     loc_14003A9A8
0x14003aad8  cmp     dword ptr [rbx+8], 2
0x14003aadc  jnb     short loc_14003AB43
0x14003aade  mov     edi, 0C00000BBh
0x14003aae3  mov     dl, byte ptr cs:xmmword_14001A3E0
0x14003aae9  lea     rax, WPP_RECORDER_INITIALIZED
0x14003aaf0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003aaf7  setnz   r8b
0x14003aafb  and     dl, 20h
0x14003aafe  jnz     short loc_14003AB09
0x14003ab00  test    r8b, r8b
0x14003ab03  jz      loc_14003AC2A
0x14003ab09  mov     dword ptr [rsp+88h+var_30], edi
0x14003ab0d  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003ab14  mov     [rsp+88h+var_38], rbp
0x14003ab19  mov     ecx, 405h
0x14003ab1e  mov     dword ptr [rsp+88h+var_40], 420h
0x14003ab26  mov     [rsp+88h+var_48], rax
0x14003ab2b  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003ab32  mov     [rsp+88h+LengthReturned], rax
0x14003ab37  mov     [rsp+88h+OutputBufferLength], 1Fh
0x14003ab3e  jmp     loc_14003A9B0
0x14003ab43  xor     edi, edi
0x14003ab45  mov     byte ptr [rsi], 1
0x14003ab48  mov     [r14], rbx
0x14003ab4b  jmp     loc_14003AC45
0x14003ab50  mov     edx, 0C000CE02h
0x14003ab55  mov     edi, edx
0x14003ab57  mov     r10b, byte ptr cs:xmmword_14001A3E0
0x14003ab5e  lea     rax, WPP_RECORDER_INITIALIZED
0x14003ab65  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003ab6c  setnz   r8b
0x14003ab70  and     r10b, 20h
0x14003ab74  jnz     short loc_14003AB7F
0x14003ab76  test    r8b, r8b
0x14003ab79  jz      loc_14003AC2A
0x14003ab7f  mov     dword ptr [rsp+88h+var_30], edx
0x14003ab83  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003ab8a  mov     [rsp+88h+var_38], rbp
0x14003ab8f  mov     ecx, 405h
0x14003ab94  mov     dword ptr [rsp+88h+var_40], ecx
0x14003ab98  mov     [rsp+88h+var_48], rax
0x14003ab9d  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003aba4  mov     [rsp+88h+LengthReturned], rax
0x14003aba9  mov     [rsp+88h+OutputBufferLength], 1Dh
0x14003abb0  jmp     loc_14003A9AD
0x14003abb5  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003abbb  lea     rax, WPP_RECORDER_INITIALIZED
0x14003abc2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003abc9  setnz   r8b
0x14003abcd  and     dl, 20h
0x14003abd0  jnz     short loc_14003ABD7
0x14003abd2  test    r8b, r8b
0x14003abd5  jz      short loc_14003AC2A
0x14003abd7  mov     dword ptr [rsp+88h+var_30], edi
0x14003abdb  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003abe2  mov     [rsp+88h+var_38], rbp
0x14003abe7  mov     ecx, 205h
0x14003abec  mov     dword ptr [rsp+88h+var_40], 3DEh
0x14003abf4  mov     [rsp+88h+var_48], rax
0x14003abf9  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003ac00  mov     [rsp+88h+LengthReturned], rax
0x14003ac05  mov     [rsp+88h+OutputBufferLength], 1Ah
0x14003ac0c  mov     dword ptr [rsp+88h+OutputBuffer], 5
0x14003ac14  mov     byte ptr [rsp+88h+InputBufferLength], 2
0x14003ac19  jmp     loc_14003A9BD
0x14003ac1e  mov     byte ptr [rsi], 0
0x14003ac21  xor     edi, edi
0x14003ac23  mov     qword ptr [r14], 0
0x14003ac2a  mov     edx, 69724A50h; Tag
0x14003ac2f  mov     rcx, rbx; P
0x14003ac32  call    cs:__imp_ExFreePoolWithTag
0x14003ac39  nop     dword ptr [rax+rax+00h]
0x14003ac3e  jmp     short loc_14003AC45
0x14003ac40  mov     edi, 0C000009Ah
0x14003ac45  lea     r11, [rsp+88h+var_28]
0x14003ac4a  mov     eax, edi
0x14003ac4c  mov     rbx, [r11+30h]
0x14003ac50  mov     rbp, [r11+40h]
0x14003ac54  mov     rsp, r11
0x14003ac57  pop     r15
0x14003ac59  pop     r14
0x14003ac5b  pop     r13
0x14003ac5d  pop     rdi
0x14003ac5e  pop     rsi
0x14003ac5f  retn
```
