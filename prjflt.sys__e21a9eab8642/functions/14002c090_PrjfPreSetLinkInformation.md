# PrjfPreSetLinkInformation

- ea: `0x14002c090`
- end: `0x14002c1ed`
- name: `PrjfPreSetLinkInformation`
- size: `349`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002c030`

## callees

- `0x14000b1d0`
- `0x14000d128`
- `0x14002c090`
- `0x14002c98c`

## import_xrefs

- `FLTMGR!FltGetDestinationFileNameInformation` at `0x14002c0f0`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x14002c0f0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002c1b5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002c1b5`

## pseudocode

```c
__int64 __fastcall PrjfPreSetLinkInformation(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  struct _FILE_OBJECT *v6; // rdx
  unsigned int v8; // edi
  int v9; // edx
  int DestinationFileNameInformation; // ebx
  int v11; // r8d
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+80h] [rbp+8h] BYREF

  *a3 = 0;
  Iopb = CallbackData->Iopb;
  v6 = *(struct _FILE_OBJECT **)(a2 + 32);
  FileNameInformation = 0;
  v8 = 1;
  DestinationFileNameInformation = FltGetDestinationFileNameInformation(
                                     *(PFLT_INSTANCE *)(a2 + 24),
                                     v6,
                                     *((HANDLE *)Iopb->Parameters.Create.EaBuffer + 1),
                                     (PWSTR)Iopb->Parameters.Create.EaBuffer + 10,
                                     *((_DWORD *)Iopb->Parameters.Create.EaBuffer + 4),
                                     0x101u,
                                     &FileNameInformation);
  if ( DestinationFileNameInformation >= 0 )
  {
    v12 = PrjfProcessPreRenameOrLinkInformation(CallbackData, a2, FileNameInformation, 64, a3);
    DestinationFileNameInformation = v12;
    if ( *a3 )
    {
      if ( v12 < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, v13, v15);
      v8 = 0;
    }
  }
  else if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = BYTE1(xmmword_14001A3D0) & 0x20;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      525,
      v9,
      v11,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      13,
      34,
      (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
      140,
      DestinationFileNameInformation);
  }
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( DestinationFileNameInformation < 0 )
  {
    CallbackData->IoStatus.Status = DestinationFileNameInformation;
    v8 = 4;
    CallbackData->IoStatus.Information = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x14002c090  mov     r11, rsp
0x14002c093  mov     [r11+10h], rbx
0x14002c097  mov     [r11+18h], rbp
0x14002c09b  push    rsi
0x14002c09c  push    rdi
0x14002c09d  push    r14
0x14002c09f  sub     rsp, 60h
0x14002c0a3  mov     qword ptr [r8], 0
0x14002c0aa  mov     r14, r8
0x14002c0ad  mov     rax, [rcx+10h]
0x14002c0b1  mov     rbp, rdx
0x14002c0b4  mov     rdx, [rdx+20h]; FileObject
0x14002c0b8  mov     rsi, rcx
0x14002c0bb  mov     qword ptr [r11+8], 0
0x14002c0c3  mov     edi, 1
0x14002c0c8  mov     r8, [rax+38h]
0x14002c0cc  lea     rax, [r11+8]
0x14002c0d0  mov     rcx, [rbp+18h]; Instance
0x14002c0d4  mov     [r11-48h], rax
0x14002c0d8  mov     [rsp+78h+NameOptions], 101h; NameOptions
0x14002c0e0  mov     eax, [r8+10h]
0x14002c0e4  lea     r9, [r8+14h]; FileName
0x14002c0e8  mov     r8, [r8+8]; RootDirectory
0x14002c0ec  mov     [rsp+78h+FileNameLength], eax; FileNameLength
0x14002c0f0  call    cs:__imp_FltGetDestinationFileNameInformation
0x14002c0f7  nop     dword ptr [rax+rax+00h]
0x14002c0fc  mov     ebx, eax
0x14002c0fe  test    eax, eax
0x14002c100  jns     short loc_14002C177
0x14002c102  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002c108  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c10f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c116  setnz   r8b
0x14002c11a  and     dl, 20h
0x14002c11d  jnz     short loc_14002C128
0x14002c11f  test    r8b, r8b
0x14002c122  jz      loc_14002C1A8
0x14002c128  mov     r9, cs:WPP_GLOBAL_Control
0x14002c12f  lea     rax, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002c136  mov     [rsp+78h+var_28], ebx
0x14002c13a  mov     ecx, 20Dh
0x14002c13f  mov     [rsp+78h+var_30], 38Ch
0x14002c147  mov     [rsp+78h+var_38], rax
0x14002c14c  lea     rax, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002c153  mov     r9, [r9+40h]
0x14002c157  mov     [rsp+78h+var_40], rax
0x14002c15c  mov     [rsp+78h+var_48], 22h ; '"'
0x14002c163  mov     [rsp+78h+NameOptions], 0Dh
0x14002c16b  mov     byte ptr [rsp+78h+FileNameLength], 2
0x14002c170  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002c175  jmp     short loc_14002C1A8
0x14002c177  mov     r8, [rsp+78h+FileNameInformation]
0x14002c17f  mov     r9d, 40h ; '@'
0x14002c185  mov     rdx, rbp
0x14002c188  mov     qword ptr [rsp+78h+FileNameLength], r14; __int64
0x14002c18d  mov     rcx, rsi; CallbackData
0x14002c190  call    PrjfProcessPreRenameOrLinkInformation
0x14002c195  cmp     qword ptr [r14], 0
0x14002c199  mov     ebx, eax
0x14002c19b  jz      short loc_14002C1A8
0x14002c19d  test    eax, eax
0x14002c19f  jns     short loc_14002C1A6
0x14002c1a1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002c1a6  xor     edi, edi
0x14002c1a8  mov     rcx, [rsp+78h+FileNameInformation]; FileNameInformation
0x14002c1b0  test    rcx, rcx
0x14002c1b3  jz      short loc_14002C1C1
0x14002c1b5  call    cs:__imp_FltReleaseFileNameInformation
0x14002c1bc  nop     dword ptr [rax+rax+00h]
0x14002c1c1  test    ebx, ebx
0x14002c1c3  jns     short loc_14002C1D5
0x14002c1c5  mov     [rsi+18h], ebx
0x14002c1c8  mov     edi, 4
0x14002c1cd  mov     qword ptr [rsi+20h], 0
0x14002c1d5  lea     r11, [rsp+78h+var_18]
0x14002c1da  mov     eax, edi
0x14002c1dc  mov     rbx, [r11+28h]
0x14002c1e0  mov     rbp, [r11+30h]
0x14002c1e4  mov     rsp, r11
0x14002c1e7  pop     r14
0x14002c1e9  pop     rdi
0x14002c1ea  pop     rsi
0x14002c1eb  retn
```
