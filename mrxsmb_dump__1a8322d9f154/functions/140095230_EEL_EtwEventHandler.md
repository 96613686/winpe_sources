# EEL_EtwEventHandler

- ea: `0x140095230`
- end: `0x140095421`
- name: `EEL_EtwEventHandler`
- size: `497`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x140059dc0`
- `0x1400869a0`
- `0x140086b04`
- `0x140095230`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400953f7`
- `ntoskrnl!EtwWriteTransfer` at `0x1400953f7`
- `ntoskrnl!ExAcquireFastMutex` at `0x140095259`
- `ntoskrnl!ExAcquireFastMutex` at `0x140095259`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400952af`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400952af`

## pseudocode

```c
void __fastcall EEL_EtwEventHandler(__int64 a1, int a2)
{
  int v3; // ebx
  __int16 *v4; // rax
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
    v4 = (__int16 *)&dword_140068C1C;
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
    v4 = (__int16 *)&byte_140068BF7;
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
    v4 = word_140068DCA;
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
0x140095230  mov     [rsp-8+arg_0], rbx
0x140095235  push    rbp
0x140095236  lea     rbp, [rsp-3Fh]
0x14009523b  sub     rsp, 90h
0x140095242  mov     rax, cs:__security_cookie
0x140095249  xor     rax, rsp
0x14009524c  mov     [rbp+3Fh+var_10], rax
0x140095250  lea     rcx, FastMutex; FastMutex
0x140095257  mov     ebx, edx
0x140095259  call    cs:__imp_ExAcquireFastMutex
0x140095260  nop     dword ptr [rax+rax+00h]
0x140095265  cmp     cs:dword_140070458, 0
0x14009526c  jz      short loc_140095298
0x14009526e  movaps  xmm0, cs:xmmword_140070460
0x140095275  lea     rcx, [rbp+3Fh+var_40]
0x140095279  movaps  xmm1, cs:xmmword_140070470
0x140095280  movaps  xmmword ptr [rbp+3Fh+var_40.Ptr], xmm0
0x140095284  movaps  xmm0, cs:xmmword_140070480
0x14009528b  movaps  [rbp+3Fh+var_20], xmm0
0x14009528f  movaps  [rbp+3Fh+var_30], xmm1
0x140095293  call    EEL_PolicyUpdate_WriteEvent
0x140095298  mov     ecx, cs:dword_140070490
0x14009529e  cmp     ecx, 2
0x1400952a1  jz      short loc_1400952A8
0x1400952a3  call    EEL_DplStateChange_WriteEvent
0x1400952a8  lea     rcx, FastMutex; FastMutex
0x1400952af  call    cs:__imp_ExReleaseFastMutex
0x1400952b6  nop     dword ptr [rax+rax+00h]
0x1400952bb  test    ebx, ebx
0x1400952bd  jz      loc_140095366
0x1400952c3  sub     ebx, 1
0x1400952c6  jz      short loc_14009531D
0x1400952c8  cmp     ebx, 1
0x1400952cb  jnz     loc_140095403
0x1400952d1  mov     eax, cs:dword_140070128
0x1400952d7  cmp     eax, 5
0x1400952da  jbe     loc_140095403
0x1400952e0  movzx   eax, cs:word_140068DC0
0x1400952e7  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x1400952ea  mov     rax, cs:off_140070130
0x1400952f1  mov     [rbp+3Fh+var_40.Ptr], rax
0x1400952f5  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], 0B000000h
0x1400952fc  mov     [rbp+3Fh+EventDescriptor.Keyword], 0
0x140095304  movzx   eax, word ptr [rax]
0x140095307  mov     [rbp+3Fh+var_40.Size], eax
0x14009530a  lea     rax, word_140068DCA
0x140095311  mov     dword ptr [rbp+3Fh+var_30+8], 17h
0x140095318  jmp     loc_1400953AD
0x14009531d  mov     eax, cs:dword_140070128
0x140095323  cmp     eax, 5
0x140095326  jbe     loc_140095403
0x14009532c  movzx   eax, cs:word_140068BED
0x140095333  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x140095336  mov     rax, cs:off_140070130
0x14009533d  mov     [rbp+3Fh+var_40.Ptr], rax
0x140095341  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], 0B000000h
0x140095348  mov     [rbp+3Fh+EventDescriptor.Keyword], 0
0x140095350  movzx   eax, word ptr [rax]
0x140095353  mov     [rbp+3Fh+var_40.Size], eax
0x140095356  lea     rax, byte_140068BF7
0x14009535d  mov     dword ptr [rbp+3Fh+var_30+8], 19h
0x140095364  jmp     short loc_1400953AD
0x140095366  mov     eax, cs:dword_140070128
0x14009536c  cmp     eax, 5
0x14009536f  jbe     loc_140095403
0x140095375  movzx   eax, cs:word_140068C12
0x14009537c  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x14009537f  mov     rax, cs:off_140070130
0x140095386  mov     [rbp+3Fh+var_40.Ptr], rax
0x14009538a  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], 0B000000h
0x140095391  mov     [rbp+3Fh+EventDescriptor.Keyword], 0
0x140095399  movzx   eax, word ptr [rax]
0x14009539c  mov     [rbp+3Fh+var_40.Size], eax
0x14009539f  lea     rax, dword_140068C1C
0x1400953a6  mov     dword ptr [rbp+3Fh+var_30+8], 1Ah
0x1400953ad  mov     qword ptr [rbp+3Fh+var_30], rax
0x1400953b1  lea     rcx, _TraceLoggingMetadata
0x1400953b8  lea     rax, _TraceLoggingMetadataEnd
0x1400953bf  mov     dword ptr [rbp+3Fh+var_40.0Ch], 2
0x1400953c6  sub     eax, ecx
0x1400953c8  mov     dword ptr [rbp+3Fh+var_30+0Ch], 1
0x1400953cf  mov     [rbp+3Fh+var_60], eax
0x1400953d2  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x1400953d6  mov     eax, [rbp+3Fh+var_60]
0x1400953d9  xor     r9d, r9d; RelatedActivityId
0x1400953dc  mov     rcx, cs:RegHandle; RegHandle
0x1400953e3  lea     rax, [rbp+3Fh+var_40]
0x1400953e7  mov     [rsp+90h+UserData], rax; UserData
0x1400953ec  xor     r8d, r8d; ActivityId
0x1400953ef  mov     [rsp+90h+UserDataCount], 2; UserDataCount
0x1400953f7  call    cs:__imp_EtwWriteTransfer
0x1400953fe  nop     dword ptr [rax+rax+00h]
0x140095403  mov     rcx, [rbp+3Fh+var_10]
0x140095407  xor     rcx, rsp; StackCookie
0x14009540a  call    __security_check_cookie
0x14009540f  mov     rbx, [rsp+90h+arg_0]
0x140095417  add     rsp, 90h
0x14009541e  pop     rbp
0x14009541f  retn
```
