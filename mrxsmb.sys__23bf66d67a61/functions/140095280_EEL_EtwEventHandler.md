# EEL_EtwEventHandler

- ea: `0x140095280`
- end: `0x140095471`
- name: `EEL_EtwEventHandler`
- size: `497`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x140059dc0`
- `0x1400869f0`
- `0x140086b54`
- `0x140095280`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140095447`
- `ntoskrnl!EtwWriteTransfer` at `0x140095447`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400952a9`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400952a9`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400952ff`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400952ff`

## pseudocode

```c
void __fastcall EEL_EtwEventHandler(__int64 a1, int a2)
{
  int v3; // ebx
  char *v4; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-19h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-1h] BYREF
  __int128 v7; // [rsp+60h] [rbp+Fh]
  __int128 v8; // [rsp+70h] [rbp+1Fh]

  ExAcquireFastMutex(&FastMutex);
  if ( dword_140070458 )
  {
    UserData = (struct _EVENT_DATA_DESCRIPTOR)xmmword_140070460;
    v8 = xmmword_140070480;
    v7 = xmmword_140070470;
    EEL_PolicyUpdate_WriteEvent(&UserData);
  }
  if ( dword_140070490 != 2 )
    EEL_DplStateChange_WriteEvent();
  ExReleaseFastMutex(&FastMutex);
  if ( !a2 )
  {
    if ( (unsigned int)dword_140070128 <= 5 )
      return;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_140070130;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_140070130;
    v4 = &byte_140068D7F;
    DWORD2(v7) = 26;
    goto LABEL_14;
  }
  v3 = a2 - 1;
  if ( !v3 )
  {
    if ( (unsigned int)dword_140070128 <= 5 )
      return;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_140070130;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_140070130;
    v4 = (char *)qword_140068DC8;
    DWORD2(v7) = 25;
    goto LABEL_14;
  }
  if ( v3 == 1 && (unsigned int)dword_140070128 > 5 )
  {
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_140070130;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_140070130;
    v4 = byte_140068DA5;
    DWORD2(v7) = 23;
LABEL_14:
    *(_QWORD *)&v7 = v4;
    UserData.Reserved = 2;
    HIDWORD(v7) = 1;
    EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
  }
}

```

## disassembly

```asm
0x140095280  mov     [rsp-8+arg_0], rbx
0x140095285  push    rbp
0x140095286  lea     rbp, [rsp-3Fh]
0x14009528b  sub     rsp, 90h
0x140095292  mov     rax, cs:__security_cookie
0x140095299  xor     rax, rsp
0x14009529c  mov     [rbp+3Fh+var_10], rax
0x1400952a0  lea     rcx, FastMutex; FastMutex
0x1400952a7  mov     ebx, edx
0x1400952a9  call    cs:__imp_ExAcquireFastMutex
0x1400952b0  nop     dword ptr [rax+rax+00h]
0x1400952b5  cmp     cs:dword_140070458, 0
0x1400952bc  jz      short loc_1400952E8
0x1400952be  movaps  xmm0, cs:xmmword_140070460
0x1400952c5  lea     rcx, [rbp+3Fh+var_40]
0x1400952c9  movaps  xmm1, cs:xmmword_140070470
0x1400952d0  movaps  xmmword ptr [rbp+3Fh+var_40.Ptr], xmm0
0x1400952d4  movaps  xmm0, cs:xmmword_140070480
0x1400952db  movaps  [rbp+3Fh+var_20], xmm0
0x1400952df  movaps  [rbp+3Fh+var_30], xmm1
0x1400952e3  call    EEL_PolicyUpdate_WriteEvent
0x1400952e8  mov     ecx, cs:dword_140070490
0x1400952ee  cmp     ecx, 2
0x1400952f1  jz      short loc_1400952F8
0x1400952f3  call    EEL_DplStateChange_WriteEvent
0x1400952f8  lea     rcx, FastMutex; FastMutex
0x1400952ff  call    cs:__imp_ExReleaseFastMutex
0x140095306  nop     dword ptr [rax+rax+00h]
0x14009530b  test    ebx, ebx
0x14009530d  jz      loc_1400953B6
0x140095313  sub     ebx, 1
0x140095316  jz      short loc_14009536D
0x140095318  cmp     ebx, 1
0x14009531b  jnz     loc_140095453
0x140095321  mov     eax, cs:dword_140070128
0x140095327  cmp     eax, 5
0x14009532a  jbe     loc_140095453
0x140095330  movzx   eax, cs:word_140068D9B
0x140095337  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x14009533a  mov     rax, cs:off_140070130
0x140095341  mov     [rbp+3Fh+var_40.Ptr], rax
0x140095345  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], 0B000000h
0x14009534c  mov     [rbp+3Fh+EventDescriptor.Keyword], 0
0x140095354  movzx   eax, word ptr [rax]
0x140095357  mov     [rbp+3Fh+var_40.Size], eax
0x14009535a  lea     rax, byte_140068DA5
0x140095361  mov     dword ptr [rbp+3Fh+var_30+8], 17h
0x140095368  jmp     loc_1400953FD
0x14009536d  mov     eax, cs:dword_140070128
0x140095373  cmp     eax, 5
0x140095376  jbe     loc_140095453
0x14009537c  movzx   eax, cs:word_140068DBE
0x140095383  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x140095386  mov     rax, cs:off_140070130
0x14009538d  mov     [rbp+3Fh+var_40.Ptr], rax
0x140095391  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], 0B000000h
0x140095398  mov     [rbp+3Fh+EventDescriptor.Keyword], 0
0x1400953a0  movzx   eax, word ptr [rax]
0x1400953a3  mov     [rbp+3Fh+var_40.Size], eax
0x1400953a6  lea     rax, qword_140068DC8
0x1400953ad  mov     dword ptr [rbp+3Fh+var_30+8], 19h
0x1400953b4  jmp     short loc_1400953FD
0x1400953b6  mov     eax, cs:dword_140070128
0x1400953bc  cmp     eax, 5
0x1400953bf  jbe     loc_140095453
0x1400953c5  movzx   eax, cs:word_140068D75
0x1400953cc  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x1400953cf  mov     rax, cs:off_140070130
0x1400953d6  mov     [rbp+3Fh+var_40.Ptr], rax
0x1400953da  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], 0B000000h
0x1400953e1  mov     [rbp+3Fh+EventDescriptor.Keyword], 0
0x1400953e9  movzx   eax, word ptr [rax]
0x1400953ec  mov     [rbp+3Fh+var_40.Size], eax
0x1400953ef  lea     rax, byte_140068D7F
0x1400953f6  mov     dword ptr [rbp+3Fh+var_30+8], 1Ah
0x1400953fd  mov     qword ptr [rbp+3Fh+var_30], rax
0x140095401  lea     rcx, _TraceLoggingMetadata
0x140095408  lea     rax, _TraceLoggingMetadataEnd
0x14009540f  mov     dword ptr [rbp+3Fh+var_40.0Ch], 2
0x140095416  sub     eax, ecx
0x140095418  mov     dword ptr [rbp+3Fh+var_30+0Ch], 1
0x14009541f  mov     [rbp+3Fh+var_60], eax
0x140095422  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x140095426  mov     eax, [rbp+3Fh+var_60]
0x140095429  xor     r9d, r9d; RelatedActivityId
0x14009542c  mov     rcx, cs:RegHandle; RegHandle
0x140095433  lea     rax, [rbp+3Fh+var_40]
0x140095437  mov     [rsp+90h+UserData], rax; UserData
0x14009543c  xor     r8d, r8d; ActivityId
0x14009543f  mov     [rsp+90h+UserDataCount], 2; UserDataCount
0x140095447  call    cs:__imp_EtwWriteTransfer
0x14009544e  nop     dword ptr [rax+rax+00h]
0x140095453  mov     rcx, [rbp+3Fh+var_10]
0x140095457  xor     rcx, rsp; StackCookie
0x14009545a  call    __security_check_cookie
0x14009545f  mov     rbx, [rsp+90h+arg_0]
0x140095467  add     rsp, 90h
0x14009546e  pop     rbp
0x14009546f  retn
```
