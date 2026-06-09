# HsmFltPreACQUIRE_FOR_SECTION_SYNCHRONIZATION

- ea: `0x140062f30`
- end: `0x1400631ef`
- name: `HsmFltPreACQUIRE_FOR_SECTION_SYNCHRONIZATION`
- size: `703`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x140001910`
- `0x140001ab4`
- `0x140001d00`
- `0x140003c50`
- `0x1400044f0`
- `0x140006f40`
- `0x140007ddc`
- `0x14000cd0c`
- `0x140058ddc`
- `0x140062f30`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x140062f7e`
- `FLTMGR!FltGetStreamHandleContext` at `0x140062f7e`
- `FLTMGR!FltDeleteContext` at `0x140063136`
- `FLTMGR!FltDeleteContext` at `0x140063136`
- `FLTMGR!FltGetRequestorProcess` at `0x140062fbf`
- `FLTMGR!FltGetRequestorProcess` at `0x140062fbf`
- `FLTMGR!FltReleaseContext` at `0x140062fe3`
- `FLTMGR!FltReleaseContext` at `0x1400630d2`
- `FLTMGR!FltReleaseContext` at `0x140062fe3`
- `FLTMGR!FltReleaseContext` at `0x1400630d2`

## pseudocode

```c
__int64 __fastcall HsmFltPreACQUIRE_FOR_SECTION_SYNCHRONIZATION(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        __int64 *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  struct _FLT_INSTANCE *v6; // rdi
  ULONG PageProtection; // r12d
  struct _FILE_OBJECT *v8; // r15
  __int64 v9; // rcx
  PEPROCESS RequestorProcess; // rax
  int v11; // r8d
  PFLT_CONTEXT v12; // rcx
  __int64 *v13; // r14
  __int64 v14; // rbp
  __int64 v15; // rax
  __int64 v16; // r13
  int v17; // edi
  unsigned int v18; // edi
  int v19; // r9d
  unsigned int v20; // eax
  int v21; // r9d
  char StreamSize; // al
  __int64 v24; // r10
  PFLT_CONTEXT Context; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+10h]

  Iopb = CallbackData->Iopb;
  if ( Iopb->Parameters.Read.Length != 1 )
    return 1;
  v6 = *(struct _FLT_INSTANCE **)(a2 + 24);
  PageProtection = Iopb->Parameters.AcquireForSectionSynchronization.PageProtection;
  v8 = *(struct _FILE_OBJECT **)(a2 + 32);
  Context = 0;
  FltGetStreamHandleContext(v6, v8, &Context);
  if ( !Context )
    return 1;
  v9 = *((_QWORD *)Context + 2);
  if ( (*(_DWORD *)(v9 + 28) & 1) == 0 )
  {
    if ( !Context )
      return 1;
    FltDeleteContext(Context);
    goto LABEL_6;
  }
  if ( *(struct _FLT_INSTANCE **)(*(_QWORD *)(*(_QWORD *)(v9 + 16) + 16LL) + 32LL) != v6 )
  {
    v12 = Context;
    goto LABEL_7;
  }
  RequestorProcess = FltGetRequestorProcess(CallbackData);
  if ( (unsigned __int8)HsmOsIsPassThroughModeEnabled(RequestorProcess) )
  {
LABEL_6:
    v12 = Context;
LABEL_7:
    FltReleaseContext(v12);
    v13 = 0;
    Context = 0;
    goto LABEL_8;
  }
  v13 = (__int64 *)Context;
LABEL_8:
  if ( !v13 )
    return 1;
  LOBYTE(v11) = 1;
  HsmpTracePreCallbackEnter((_DWORD)CallbackData, 0, v11, (_DWORD)v13, v13[2]);
  v14 = v13[2];
  v15 = *(_QWORD *)(v14 + 16);
  v16 = *(_QWORD *)(v15 + 16);
  v26 = *(_QWORD *)(v15 + 32);
  v17 = HsmpAcquireUserRequestRundownProtection((PFLT_CONTEXT)v14, CallbackData);
  HsmDbgBreakOnStatus(v17);
  if ( v17 >= 0 )
  {
    if ( (PageProtection & 0x44) != 0 )
      v19 = 10;
    else
      v19 = ((PageProtection & 0xF0) != 0) + 2;
    v20 = HsmpRecallInitiateHydration(
            (_DWORD)v13,
            v14,
            CallbackData->Iopb->TargetFileObject,
            v19,
            (__int64)CallbackData,
            0,
            0);
    v18 = v20;
    if ( v20 )
    {
      if ( v20 != 2 )
        HsmpReleaseUserRequestRundownProtection((PFLT_CONTEXT)v14);
    }
    else
    {
      *a3 = v14;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      StreamSize = HsmpGetStreamSize(v14);
      WPP_SF_qqLiqiqd(
        *(_QWORD *)(v24 + 24),
        10,
        (unsigned int)WPP_d740c0600e633b6822d4efc3e3ecf6a6_Traceguids,
        v16,
        v14,
        *(_DWORD *)(v14 + 28),
        StreamSize,
        (char)v8,
        v26,
        CallbackData,
        v17);
    }
    CallbackData->IoStatus.Status = v17;
    v18 = 4;
    CallbackData->IoStatus.Information = 0;
  }
  FltReleaseContext(v13);
  LOBYTE(v21) = 0;
  HsmpTracePreCallbackExit(v18, (_DWORD)CallbackData, 0, v21, 1);
  return v18;
}

```

## disassembly

```asm
0x140062f30  mov     r11, rsp
0x140062f33  push    rbx
0x140062f34  push    rsi
0x140062f35  sub     rsp, 88h
0x140062f3c  mov     rax, [rcx+10h]
0x140062f40  mov     rsi, r8
0x140062f43  mov     rbx, rcx
0x140062f46  cmp     dword ptr [rax+18h], 1
0x140062f4a  jnz     loc_140063147
0x140062f50  mov     [r11-18h], rdi
0x140062f54  lea     r8, [r11+8]; Context
0x140062f58  mov     rdi, [rdx+18h]
0x140062f5c  mov     [r11-20h], r12
0x140062f60  mov     rcx, rdi; Instance
0x140062f63  mov     r12d, [rax+1Ch]
0x140062f67  mov     [r11-30h], r14
0x140062f6b  mov     [r11-38h], r15
0x140062f6f  mov     r15, [rdx+20h]
0x140062f73  mov     rdx, r15; FileObject
0x140062f76  mov     qword ptr [r11+8], 0
0x140062f7e  call    cs:__imp_FltGetStreamHandleContext
0x140062f85  nop     dword ptr [rax+rax+00h]
0x140062f8a  mov     r14, [rsp+98h+Context]
0x140062f92  test    r14, r14
0x140062f95  jz      loc_140063127
0x140062f9b  mov     rcx, [r14+10h]
0x140062f9f  mov     eax, [rcx+1Ch]
0x140062fa2  test    al, 1
0x140062fa4  jz      loc_14006312E
0x140062faa  mov     rax, [rcx+10h]
0x140062fae  mov     rcx, [rax+10h]
0x140062fb2  cmp     [rcx+20h], rdi
0x140062fb6  jnz     loc_14006314E
0x140062fbc  mov     rcx, rbx; CallbackData
0x140062fbf  call    cs:__imp_FltGetRequestorProcess
0x140062fc6  nop     dword ptr [rax+rax+00h]
0x140062fcb  mov     rcx, rax
0x140062fce  call    HsmOsIsPassThroughModeEnabled
0x140062fd3  test    al, al
0x140062fd5  jz      loc_140063156
0x140062fdb  mov     rcx, [rsp+98h+Context]; Context
0x140062fe3  call    cs:__imp_FltReleaseContext
0x140062fea  nop     dword ptr [rax+rax+00h]
0x140062fef  xor     r14d, r14d
0x140062ff2  mov     [rsp+98h+Context], r14
0x140062ffa  test    r14, r14
0x140062ffd  jz      loc_140063127
0x140063003  mov     rax, [r14+10h]
0x140063007  mov     r9, r14
0x14006300a  mov     [rsp+98h+arg_10], rbp
0x140063012  mov     r8b, 1
0x140063015  xor     edx, edx
0x140063017  mov     [rsp+98h+var_78], rax
0x14006301c  mov     rcx, rbx
0x14006301f  mov     [rsp+98h+var_28], r13
0x140063024  call    HsmpTracePreCallbackEnter
0x140063029  mov     rbp, [r14+10h]
0x14006302d  mov     rdx, rbx; CallbackData
0x140063030  mov     rcx, rbp; Context
0x140063033  mov     rax, [rbp+10h]
0x140063037  mov     r13, [rax+10h]
0x14006303b  mov     rax, [rax+20h]
0x14006303f  mov     [rsp+98h+arg_8], rax
0x140063047  call    HsmpAcquireUserRequestRundownProtection
0x14006304c  mov     ecx, eax
0x14006304e  mov     edi, eax
0x140063050  call    HsmDbgBreakOnStatus
0x140063055  test    edi, edi
0x140063057  jns     short loc_140063082
0x140063059  mov     r10, cs:WPP_GLOBAL_Control
0x140063060  lea     rax, WPP_GLOBAL_Control
0x140063067  cmp     r10, rax
0x14006306a  jnz     loc_140063163
0x140063070  mov     [rbx+18h], edi
0x140063073  mov     edi, 4
0x140063078  mov     qword ptr [rbx+20h], 0
0x140063080  jmp     short loc_1400630CF
0x140063082  test    r12b, 44h
0x140063086  jnz     loc_1400631CC
0x14006308c  test    r12b, 0F0h
0x140063090  mov     eax, 0
0x140063095  mov     r9d, eax
0x140063098  setnz   r9b
0x14006309c  add     r9d, 2
0x1400630a0  mov     r8, [rbx+10h]
0x1400630a4  mov     rdx, rbp
0x1400630a7  mov     [rsp+98h+var_68], rax
0x1400630ac  mov     rcx, r14
0x1400630af  mov     [rsp+98h+var_70], rax
0x1400630b4  mov     [rsp+98h+var_78], rbx
0x1400630b9  mov     r8, [r8+8]
0x1400630bd  call    HsmpRecallInitiateHydration
0x1400630c2  mov     edi, eax
0x1400630c4  test    eax, eax
0x1400630c6  jnz     loc_1400631D9
0x1400630cc  mov     [rsi], rbp
0x1400630cf  mov     rcx, r14; Context
0x1400630d2  call    cs:__imp_FltReleaseContext
0x1400630d9  nop     dword ptr [rax+rax+00h]
0x1400630de  mov     r9b, 1
0x1400630e1  mov     byte ptr [rsp+98h+var_78], 1
0x1400630e6  xor     r9b, r9b
0x1400630e9  xor     r8d, r8d
0x1400630ec  mov     rdx, rbx
0x1400630ef  mov     ecx, edi
0x1400630f1  call    HsmpTracePreCallbackExit
0x1400630f6  mov     r13, [rsp+98h+var_28]
0x1400630fb  mov     eax, edi
0x1400630fd  mov     rbp, [rsp+98h+arg_10]
0x140063105  mov     r14, [rsp+98h+var_30]
0x14006310a  mov     r12, [rsp+98h+var_20]
0x14006310f  mov     rdi, [rsp+98h+var_18]
0x140063117  mov     r15, [rsp+98h+var_38]
0x14006311c  add     rsp, 88h
0x140063123  pop     rsi
0x140063124  pop     rbx
0x140063125  retn
0x140063127  mov     eax, 1
0x14006312c  jmp     short loc_140063105
0x14006312e  test    r14, r14
0x140063131  jz      short loc_140063127
0x140063133  mov     rcx, r14; Context
0x140063136  call    cs:__imp_FltDeleteContext
0x14006313d  nop     dword ptr [rax+rax+00h]
0x140063142  jmp     loc_140062FDB
0x140063147  mov     eax, 1
0x14006314c  jmp     short loc_14006311C
0x14006314e  mov     rcx, r14
0x140063151  jmp     loc_140062FE3
0x140063156  mov     r14, [rsp+98h+Context]
0x14006315e  jmp     loc_140062FFA
0x140063163  mov     ecx, [r10+2Ch]
0x140063167  test    cl, 1
0x14006316a  jz      loc_140063070
0x140063170  cmp     byte ptr [r10+29h], 2
0x140063175  jb      loc_140063070
0x14006317b  mov     rcx, rbp
0x14006317e  call    HsmpGetStreamSize
0x140063183  mov     rcx, [rsp+98h+arg_8]
0x14006318b  lea     r8, WPP_d740c0600e633b6822d4efc3e3ecf6a6_Traceguids
0x140063192  mov     [rsp+98h+var_48], edi
0x140063196  mov     edx, 0Ah
0x14006319b  mov     [rsp+98h+var_50], rbx
0x1400631a0  mov     r9, r13
0x1400631a3  mov     [rsp+98h+var_58], rcx
0x1400631a8  mov     rcx, [r10+18h]
0x1400631ac  mov     [rsp+98h+var_60], r15
0x1400631b1  mov     [rsp+98h+var_68], rax
0x1400631b6  mov     eax, [rbp+1Ch]
0x1400631b9  mov     dword ptr [rsp+98h+var_70], eax
0x1400631bd  mov     [rsp+98h+var_78], rbp
0x1400631c2  call    WPP_SF_qqLiqiqd
0x1400631c7  jmp     loc_140063070
0x1400631cc  xor     eax, eax
0x1400631ce  mov     r9d, 0Ah
0x1400631d4  jmp     loc_1400630A0
0x1400631d9  cmp     eax, 2
0x1400631dc  jz      loc_1400630CF
0x1400631e2  mov     rcx, rbp; Context
0x1400631e5  call    HsmpReleaseUserRequestRundownProtection
0x1400631ea  jmp     loc_1400630CF
```
