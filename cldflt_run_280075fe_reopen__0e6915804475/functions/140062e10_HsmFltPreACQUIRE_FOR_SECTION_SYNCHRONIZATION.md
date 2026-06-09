# HsmFltPreACQUIRE_FOR_SECTION_SYNCHRONIZATION

- ea: `0x140062e10`
- end: `0x1400630cf`
- name: `HsmFltPreACQUIRE_FOR_SECTION_SYNCHRONIZATION`
- size: `703`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
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
- `0x140058cbc`
- `0x140062e10`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x140062e5e`
- `FLTMGR!FltGetStreamHandleContext` at `0x140062e5e`
- `FLTMGR!FltDeleteContext` at `0x140063016`
- `FLTMGR!FltDeleteContext` at `0x140063016`
- `FLTMGR!FltGetRequestorProcess` at `0x140062e9f`
- `FLTMGR!FltGetRequestorProcess` at `0x140062e9f`
- `FLTMGR!FltReleaseContext` at `0x140062ec3`
- `FLTMGR!FltReleaseContext` at `0x140062fb2`
- `FLTMGR!FltReleaseContext` at `0x140062ec3`
- `FLTMGR!FltReleaseContext` at `0x140062fb2`

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
  __int64 v17; // rdi
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
  v17 = (unsigned int)HsmpAcquireUserRequestRundownProtection((PFLT_CONTEXT)v14, CallbackData);
  HsmDbgBreakOnStatus(v17);
  if ( (int)v17 >= 0 )
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
0x140062e10  mov     r11, rsp
0x140062e13  push    rbx
0x140062e14  push    rsi
0x140062e15  sub     rsp, 88h
0x140062e1c  mov     rax, [rcx+10h]
0x140062e20  mov     rsi, r8
0x140062e23  mov     rbx, rcx
0x140062e26  cmp     dword ptr [rax+18h], 1
0x140062e2a  jnz     loc_140063027
0x140062e30  mov     [r11-18h], rdi
0x140062e34  lea     r8, [r11+8]; Context
0x140062e38  mov     rdi, [rdx+18h]
0x140062e3c  mov     [r11-20h], r12
0x140062e40  mov     rcx, rdi; Instance
0x140062e43  mov     r12d, [rax+1Ch]
0x140062e47  mov     [r11-30h], r14
0x140062e4b  mov     [r11-38h], r15
0x140062e4f  mov     r15, [rdx+20h]
0x140062e53  mov     rdx, r15; FileObject
0x140062e56  mov     qword ptr [r11+8], 0
0x140062e5e  call    cs:__imp_FltGetStreamHandleContext
0x140062e65  nop     dword ptr [rax+rax+00h]
0x140062e6a  mov     r14, [rsp+98h+Context]
0x140062e72  test    r14, r14
0x140062e75  jz      loc_140063007
0x140062e7b  mov     rcx, [r14+10h]
0x140062e7f  mov     eax, [rcx+1Ch]
0x140062e82  test    al, 1
0x140062e84  jz      loc_14006300E
0x140062e8a  mov     rax, [rcx+10h]
0x140062e8e  mov     rcx, [rax+10h]
0x140062e92  cmp     [rcx+20h], rdi
0x140062e96  jnz     loc_14006302E
0x140062e9c  mov     rcx, rbx; CallbackData
0x140062e9f  call    cs:__imp_FltGetRequestorProcess
0x140062ea6  nop     dword ptr [rax+rax+00h]
0x140062eab  mov     rcx, rax
0x140062eae  call    HsmOsIsPassThroughModeEnabled
0x140062eb3  test    al, al
0x140062eb5  jz      loc_140063036
0x140062ebb  mov     rcx, [rsp+98h+Context]; Context
0x140062ec3  call    cs:__imp_FltReleaseContext
0x140062eca  nop     dword ptr [rax+rax+00h]
0x140062ecf  xor     r14d, r14d
0x140062ed2  mov     [rsp+98h+Context], r14
0x140062eda  test    r14, r14
0x140062edd  jz      loc_140063007
0x140062ee3  mov     rax, [r14+10h]
0x140062ee7  mov     r9, r14
0x140062eea  mov     [rsp+98h+arg_10], rbp
0x140062ef2  mov     r8b, 1
0x140062ef5  xor     edx, edx
0x140062ef7  mov     [rsp+98h+var_78], rax
0x140062efc  mov     rcx, rbx
0x140062eff  mov     [rsp+98h+var_28], r13
0x140062f04  call    HsmpTracePreCallbackEnter
0x140062f09  mov     rbp, [r14+10h]
0x140062f0d  mov     rdx, rbx; CallbackData
0x140062f10  mov     rcx, rbp; Context
0x140062f13  mov     rax, [rbp+10h]
0x140062f17  mov     r13, [rax+10h]
0x140062f1b  mov     rax, [rax+20h]
0x140062f1f  mov     [rsp+98h+arg_8], rax
0x140062f27  call    HsmpAcquireUserRequestRundownProtection
0x140062f2c  mov     ecx, eax
0x140062f2e  mov     edi, eax
0x140062f30  call    HsmDbgBreakOnStatus
0x140062f35  test    edi, edi
0x140062f37  jns     short loc_140062F62
0x140062f39  mov     r10, cs:WPP_GLOBAL_Control
0x140062f40  lea     rax, WPP_GLOBAL_Control
0x140062f47  cmp     r10, rax
0x140062f4a  jnz     loc_140063043
0x140062f50  mov     [rbx+18h], edi
0x140062f53  mov     edi, 4
0x140062f58  mov     qword ptr [rbx+20h], 0
0x140062f60  jmp     short loc_140062FAF
0x140062f62  test    r12b, 44h
0x140062f66  jnz     loc_1400630AC
0x140062f6c  test    r12b, 0F0h
0x140062f70  mov     eax, 0
0x140062f75  mov     r9d, eax
0x140062f78  setnz   r9b
0x140062f7c  add     r9d, 2
0x140062f80  mov     r8, [rbx+10h]
0x140062f84  mov     rdx, rbp
0x140062f87  mov     [rsp+98h+var_68], rax
0x140062f8c  mov     rcx, r14
0x140062f8f  mov     [rsp+98h+var_70], rax
0x140062f94  mov     [rsp+98h+var_78], rbx
0x140062f99  mov     r8, [r8+8]
0x140062f9d  call    HsmpRecallInitiateHydration
0x140062fa2  mov     edi, eax
0x140062fa4  test    eax, eax
0x140062fa6  jnz     loc_1400630B9
0x140062fac  mov     [rsi], rbp
0x140062faf  mov     rcx, r14; Context
0x140062fb2  call    cs:__imp_FltReleaseContext
0x140062fb9  nop     dword ptr [rax+rax+00h]
0x140062fbe  mov     r9b, 1
0x140062fc1  mov     byte ptr [rsp+98h+var_78], 1
0x140062fc6  xor     r9b, r9b
0x140062fc9  xor     r8d, r8d
0x140062fcc  mov     rdx, rbx
0x140062fcf  mov     ecx, edi
0x140062fd1  call    HsmpTracePreCallbackExit
0x140062fd6  mov     r13, [rsp+98h+var_28]
0x140062fdb  mov     eax, edi
0x140062fdd  mov     rbp, [rsp+98h+arg_10]
0x140062fe5  mov     r14, [rsp+98h+var_30]
0x140062fea  mov     r12, [rsp+98h+var_20]
0x140062fef  mov     rdi, [rsp+98h+var_18]
0x140062ff7  mov     r15, [rsp+98h+var_38]
0x140062ffc  add     rsp, 88h
0x140063003  pop     rsi
0x140063004  pop     rbx
0x140063005  retn
0x140063007  mov     eax, 1
0x14006300c  jmp     short loc_140062FE5
0x14006300e  test    r14, r14
0x140063011  jz      short loc_140063007
0x140063013  mov     rcx, r14; Context
0x140063016  call    cs:__imp_FltDeleteContext
0x14006301d  nop     dword ptr [rax+rax+00h]
0x140063022  jmp     loc_140062EBB
0x140063027  mov     eax, 1
0x14006302c  jmp     short loc_140062FFC
0x14006302e  mov     rcx, r14
0x140063031  jmp     loc_140062EC3
0x140063036  mov     r14, [rsp+98h+Context]
0x14006303e  jmp     loc_140062EDA
0x140063043  mov     ecx, [r10+2Ch]
0x140063047  test    cl, 1
0x14006304a  jz      loc_140062F50
0x140063050  cmp     byte ptr [r10+29h], 2
0x140063055  jb      loc_140062F50
0x14006305b  mov     rcx, rbp
0x14006305e  call    HsmpGetStreamSize
0x140063063  mov     rcx, [rsp+98h+arg_8]
0x14006306b  lea     r8, WPP_d740c0600e633b6822d4efc3e3ecf6a6_Traceguids
0x140063072  mov     [rsp+98h+var_48], edi
0x140063076  mov     edx, 0Ah
0x14006307b  mov     [rsp+98h+var_50], rbx
0x140063080  mov     r9, r13
0x140063083  mov     [rsp+98h+var_58], rcx
0x140063088  mov     rcx, [r10+18h]
0x14006308c  mov     [rsp+98h+var_60], r15
0x140063091  mov     [rsp+98h+var_68], rax
0x140063096  mov     eax, [rbp+1Ch]
0x140063099  mov     dword ptr [rsp+98h+var_70], eax
0x14006309d  mov     [rsp+98h+var_78], rbp
0x1400630a2  call    WPP_SF_qqLiqiqd
0x1400630a7  jmp     loc_140062F50
0x1400630ac  xor     eax, eax
0x1400630ae  mov     r9d, 0Ah
0x1400630b4  jmp     loc_140062F80
0x1400630b9  cmp     eax, 2
0x1400630bc  jz      loc_140062FAF
0x1400630c2  mov     rcx, rbp; Context
0x1400630c5  call    HsmpReleaseUserRequestRundownProtection
0x1400630ca  jmp     loc_140062FAF
```
