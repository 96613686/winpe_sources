# HsmiInfoHydratePlaceholderOnRename

- ea: `0x140034010`
- end: `0x14003425f`
- name: `HsmiInfoHydratePlaceholderOnRename`
- size: `591`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001d00`
- `0x140002aec`
- `0x140003c50`
- `0x140007ddc`
- `0x140009300`
- `0x14001afdc`
- `0x140034010`
- `0x14004c5e0`
- `0x140058cbc`
- `0x14005aaf0`
- `0x14007634c`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140034241`
- `FLTMGR!FltReleaseContext` at `0x140034241`

## pseudocode

```c
__int64 __fastcall HsmiInfoHydratePlaceholderOnRename(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        __int16 a3,
        struct _FLT_CALLBACK_DATA *a4)
{
  int Status; // ebx
  struct _FLT_INSTANCE *v8; // r15
  _QWORD *StreamHandleContext; // rax
  _QWORD *v10; // r14
  _DWORD *v11; // rsi
  __int64 StreamSize; // rax
  __int64 v13; // r8
  __int64 v14; // r10
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx

  Status = 0;
  if ( (a3 & 0x400) == 0 )
    return (unsigned int)Status;
  v8 = *(struct _FLT_INSTANCE **)(a1 + 32);
  Status = HsmpSetupContexts(a1, a2, 0, 0);
  HsmDbgBreakOnStatus((unsigned int)Status);
  if ( Status >= 0 )
  {
    StreamHandleContext = HsmpGetStreamHandleContext(a4, v8, a2);
    v10 = StreamHandleContext;
    if ( !StreamHandleContext )
      return (unsigned int)Status;
    v11 = (_DWORD *)StreamHandleContext[2];
    Status = HsmpAcquireUserRequestRundownProtection(v11, a4);
    HsmDbgBreakOnStatus((unsigned int)Status);
    if ( Status < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        StreamSize = HsmpGetStreamSize((__int64)v11);
        WPP_SF_qqLiiqd(
          *(_QWORD *)(v14 + 24),
          17,
          *(_QWORD *)(v13 + 32),
          a1,
          v11,
          v11[7],
          StreamSize,
          *(_QWORD *)(v13 + 32),
          a4,
          Status);
      }
      goto LABEL_26;
    }
    if ( (v11[7] & 2) != 0 )
    {
      Status = HsmpRpRemove(v11, a2, 0);
      HsmDbgBreakOnStatus((unsigned int)Status);
      if ( Status >= 0 )
        goto LABEL_25;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_25;
      }
      v16 = 18;
    }
    else
    {
      HsmpRecallInitiateHydrationEx(
        (int)v10,
        v10[2],
        (int)a2,
        65543,
        a4,
        0,
        -1,
        0,
        (__int64)&HsmiInfoRecallForRenameCompletion);
      Status = a4->IoStatus.Status;
      HsmDbgBreakOnStatus((unsigned int)Status);
      if ( Status >= 0 )
        goto LABEL_25;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_25;
      }
      v16 = 19;
    }
    WPP_SF_qqd(v15->AttachedDevice, v16, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids, v8, a2, Status);
LABEL_25:
    HsmpReleaseUserRequestRundownProtection(v11);
LABEL_26:
    FltReleaseContext(v10);
    return (unsigned int)Status;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids, v8, a2, Status);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140034010  push    rbx
0x140034012  push    rbp
0x140034013  push    rsi
0x140034014  push    rdi
0x140034015  push    r13
0x140034017  push    r14
0x140034019  push    r15
0x14003401b  sub     rsp, 50h
0x14003401f  xor     ebx, ebx
0x140034021  mov     rbp, r9
0x140034024  mov     rdi, rdx
0x140034027  mov     r13, rcx
0x14003402a  bt      r8d, 0Ah
0x14003402f  jnb     loc_14003424D
0x140034035  mov     r15, [rcx+20h]
0x140034039  xor     r9d, r9d
0x14003403c  xor     r8d, r8d
0x14003403f  call    HsmpSetupContexts
0x140034044  mov     ecx, eax
0x140034046  mov     ebx, eax
0x140034048  call    HsmDbgBreakOnStatus
0x14003404d  test    ebx, ebx
0x14003404f  jns     short loc_1400340A4
0x140034051  mov     rcx, cs:WPP_GLOBAL_Control
0x140034058  lea     rax, WPP_GLOBAL_Control
0x14003405f  cmp     rcx, rax
0x140034062  jz      loc_14003424D
0x140034068  mov     edx, [rcx+2Ch]
0x14003406b  test    dl, 1
0x14003406e  jz      loc_14003424D
0x140034074  cmp     byte ptr [rcx+29h], 2
0x140034078  jb      loc_14003424D
0x14003407e  mov     rcx, [rcx+18h]
0x140034082  lea     r8, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids
0x140034089  mov     edx, 10h
0x14003408e  mov     dword ptr [rsp+88h+var_60], ebx
0x140034092  mov     r9, r15
0x140034095  mov     [rsp+88h+CallbackData], rdi
0x14003409a  call    WPP_SF_qqd
0x14003409f  jmp     loc_14003424D
0x1400340a4  mov     r8, rdi; FileObject
0x1400340a7  mov     rdx, r15; Instance
0x1400340aa  mov     rcx, rbp; CallbackData
0x1400340ad  call    HsmpGetStreamHandleContext
0x1400340b2  mov     r14, rax
0x1400340b5  test    rax, rax
0x1400340b8  jz      loc_14003424D
0x1400340be  mov     rsi, [rax+10h]
0x1400340c2  mov     rdx, rbp; CallbackData
0x1400340c5  mov     rcx, rsi; Context
0x1400340c8  call    HsmpAcquireUserRequestRundownProtection
0x1400340cd  mov     ecx, eax
0x1400340cf  mov     ebx, eax
0x1400340d1  call    HsmDbgBreakOnStatus
0x1400340d6  test    ebx, ebx
0x1400340d8  jns     short loc_14003414D
0x1400340da  mov     r10, cs:WPP_GLOBAL_Control
0x1400340e1  lea     rax, WPP_GLOBAL_Control
0x1400340e8  cmp     r10, rax
0x1400340eb  jz      loc_14003423E
0x1400340f1  mov     eax, [r10+2Ch]
0x1400340f5  test    al, 1
0x1400340f7  jz      loc_14003423E
0x1400340fd  cmp     byte ptr [r10+29h], 2
0x140034102  jb      loc_14003423E
0x140034108  mov     r8, [rsi+10h]
0x14003410c  mov     rcx, rsi
0x14003410f  call    HsmpGetStreamSize
0x140034114  mov     r8, [r8+20h]
0x140034118  mov     edx, 11h
0x14003411d  mov     rcx, [r10+18h]
0x140034121  mov     r9, r13
0x140034124  mov     [rsp+88h+var_40], ebx
0x140034128  mov     [rsp+88h+var_48], rbp
0x14003412d  mov     qword ptr [rsp+88h+var_50], r8
0x140034132  mov     [rsp+88h+var_58], rax
0x140034137  mov     eax, [rsi+1Ch]
0x14003413a  mov     dword ptr [rsp+88h+var_60], eax
0x14003413e  mov     [rsp+88h+CallbackData], rsi
0x140034143  call    WPP_SF_qqLiiqd
0x140034148  jmp     loc_14003423E
0x14003414d  mov     eax, [rsi+1Ch]
0x140034150  test    al, 2
0x140034152  jz      short loc_1400341A6
0x140034154  xor     r8d, r8d
0x140034157  mov     rdx, rdi; FileObject
0x14003415a  mov     rcx, rsi; Context
0x14003415d  call    HsmpRpRemove
0x140034162  mov     ecx, eax
0x140034164  mov     ebx, eax
0x140034166  call    HsmDbgBreakOnStatus
0x14003416b  test    ebx, ebx
0x14003416d  jns     loc_140034236
0x140034173  mov     rcx, cs:WPP_GLOBAL_Control
0x14003417a  lea     rax, WPP_GLOBAL_Control
0x140034181  cmp     rcx, rax
0x140034184  jz      loc_140034236
0x14003418a  mov     eax, [rcx+2Ch]
0x14003418d  test    al, 1
0x14003418f  jz      loc_140034236
0x140034195  cmp     byte ptr [rcx+29h], 2
0x140034199  jb      loc_140034236
0x14003419f  mov     edx, 12h
0x1400341a4  jmp     short loc_14003421A
0x1400341a6  mov     rdx, [r14+10h]; int
0x1400341aa  lea     rax, HsmiInfoRecallForRenameCompletion
0x1400341b1  mov     [rsp+88h+var_48], rax; __int64
0x1400341b6  mov     r9d, 10007h; int
0x1400341bc  mov     qword ptr [rsp+88h+var_50], 0; int
0x1400341c5  mov     r8, rdi; int
0x1400341c8  mov     [rsp+88h+var_58], 0FFFFFFFFFFFFFFFFh; __int64
0x1400341d1  mov     rcx, r14; int
0x1400341d4  mov     [rsp+88h+var_60], 0; __int64
0x1400341dd  mov     [rsp+88h+CallbackData], rbp; CallbackData
0x1400341e2  call    HsmpRecallInitiateHydrationEx
0x1400341e7  mov     ebx, [rbp+18h]
0x1400341ea  mov     ecx, ebx
0x1400341ec  call    HsmDbgBreakOnStatus
0x1400341f1  test    ebx, ebx
0x1400341f3  jns     short loc_140034236
0x1400341f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400341fc  lea     rax, WPP_GLOBAL_Control
0x140034203  cmp     rcx, rax
0x140034206  jz      short loc_140034236
0x140034208  mov     eax, [rcx+2Ch]
0x14003420b  test    al, 1
0x14003420d  jz      short loc_140034236
0x14003420f  cmp     byte ptr [rcx+29h], 2
0x140034213  jb      short loc_140034236
0x140034215  mov     edx, 13h
0x14003421a  mov     rcx, [rcx+18h]
0x14003421e  lea     r8, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids
0x140034225  mov     dword ptr [rsp+88h+var_60], ebx
0x140034229  mov     r9, r15
0x14003422c  mov     [rsp+88h+CallbackData], rdi
0x140034231  call    WPP_SF_qqd
0x140034236  mov     rcx, rsi; Context
0x140034239  call    HsmpReleaseUserRequestRundownProtection
0x14003423e  mov     rcx, r14; Context
0x140034241  call    cs:__imp_FltReleaseContext
0x140034248  nop     dword ptr [rax+rax+00h]
0x14003424d  mov     eax, ebx
0x14003424f  add     rsp, 50h
0x140034253  pop     r15
0x140034255  pop     r14
0x140034257  pop     r13
0x140034259  pop     rdi
0x14003425a  pop     rsi
0x14003425b  pop     rbp
0x14003425c  pop     rbx
0x14003425d  retn
```
