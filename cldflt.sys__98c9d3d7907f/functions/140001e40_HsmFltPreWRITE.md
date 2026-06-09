# HsmFltPreWRITE

- ea: `0x140001e40`
- end: `0x1400021d9`
- name: `HsmFltPreWRITE`
- size: `921`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callees

- `0x140001a00`
- `0x140001d00`
- `0x140001e40`
- `0x140002aec`
- `0x140003c50`
- `0x1400044f0`
- `0x14000c9f4`
- `0x14000cd0c`
- `0x14004b934`
- `0x14004c5e0`
- `0x140058cbc`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140001e76`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140001f21`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140001e76`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140001f21`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x140001f32`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x140001f32`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001fc5`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001fc5`
- `FLTMGR!FltIsOperationSynchronous` at `0x140002116`
- `FLTMGR!FltIsOperationSynchronous` at `0x140002116`
- `FLTMGR!FltReleaseContext` at `0x140001fd4`
- `FLTMGR!FltReleaseContext` at `0x14000201c`
- `FLTMGR!FltReleaseContext` at `0x140001fd4`
- `FLTMGR!FltReleaseContext` at `0x14000201c`

## pseudocode

```c
__int64 __fastcall HsmFltPreWRITE(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  __int64 v7; // r15
  _QWORD *StreamHandleContext; // rax
  __int64 v9; // r8
  _QWORD *v10; // rsi
  __int64 v11; // rbp
  __int64 v12; // rax
  __int64 v13; // r12
  __int64 v14; // r13
  unsigned int v15; // eax
  unsigned int v16; // edi
  __int64 Status; // r8
  ULONG_PTR Information; // r9
  char StreamSize; // al
  __int64 v21; // r10
  PFLT_IO_PARAMETER_BLOCK v22; // rax
  struct _DEVICE_OBJECT *AttachedDevice; // r12
  PFILE_OBJECT TargetFileObject; // rsi
  ULONG Length; // ebp
  char v26; // r15
  LARGE_INTEGER ByteOffset; // r14
  char v28; // di
  BOOLEAN IsOperationSynchronous; // al
  int v30; // [rsp+A0h] [rbp+8h]
  char v31; // [rsp+A8h] [rbp+10h]
  _QWORD *v32; // [rsp+B8h] [rbp+20h]

  Iopb = CallbackData->Iopb;
  if ( !Iopb->Parameters.Read.Length )
    return 1;
  if ( (Iopb->IrpFlags & 2) != 0 )
    return 1;
  v7 = *(_QWORD *)(a2 + 32);
  if ( IoGetTopLevelIrp() )
    return 1;
  StreamHandleContext = HsmpGetStreamHandleContext(
                          CallbackData,
                          *(PFLT_INSTANCE *)(a2 + 24),
                          *(PFILE_OBJECT *)(a2 + 32));
  v32 = StreamHandleContext;
  v10 = StreamHandleContext;
  if ( !StreamHandleContext )
    return 1;
  LOBYTE(v9) = 1;
  HsmpTracePreCallbackEnter((__int64)CallbackData, 0, v9, (__int64)StreamHandleContext, StreamHandleContext[2]);
  v11 = v10[2];
  v12 = *(_QWORD *)(v11 + 16);
  v13 = *(_QWORD *)(v12 + 32);
  v14 = *(_QWORD *)(v12 + 16);
  v31 = v13;
  v30 = HsmpAcquireUserRequestRundownProtection((PFLT_CONTEXT)v11, CallbackData);
  HsmDbgBreakOnStatus((unsigned int)v30);
  if ( v30 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      StreamSize = HsmpGetStreamSize(v11);
      WPP_SF_qqLiqiqd(
        *(_QWORD *)(v21 + 24),
        11,
        (unsigned int)WPP_d740c0600e633b6822d4efc3e3ecf6a6_Traceguids,
        v14,
        v11,
        *(_DWORD *)(v11 + 28),
        StreamSize,
        v7,
        v13,
        CallbackData,
        v30);
    }
    CallbackData->IoStatus.Status = v30;
    CallbackData->IoStatus.Information = 0;
    v16 = 4;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v22 = CallbackData->Iopb;
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      TargetFileObject = v22->TargetFileObject;
      Length = v22->Parameters.Read.Length;
      v26 = (v22->IrpFlags & 1) == 0;
      ByteOffset = v22->Parameters.Read.ByteOffset;
      v28 = (v22->IrpFlags & 2) != 0;
      IsOperationSynchronous = FltIsOperationSynchronous(CallbackData);
      WPP_SF_qiDcccqid(
        (_DWORD)AttachedDevice,
        12,
        (unsigned int)WPP_d740c0600e633b6822d4efc3e3ecf6a6_Traceguids,
        (_DWORD)CallbackData,
        ByteOffset.QuadPart,
        Length,
        IsOperationSynchronous,
        v26,
        v28,
        (char)TargetFileObject,
        v31,
        v30);
      v10 = v32;
      v16 = 4;
    }
    goto LABEL_15;
  }
  if ( !IoGetTopLevelIrp()
    && !KeAreAllApcsDisabled()
    && !*(_BYTE *)(v14 + 24)
    && *((_QWORD *)&_Config + 1)
    && !*(_DWORD *)(v11 + 36) )
  {
    HsmpUpdateLastAccessTime(CallbackData);
  }
  v15 = HsmpRecallInitiateHydrationEx(
          (int)v10,
          v11,
          (int)CallbackData->Iopb->TargetFileObject,
          9,
          CallbackData,
          CallbackData->Iopb->Parameters.Read.ByteOffset.QuadPart,
          CallbackData->Iopb->Parameters.Read.Length,
          0,
          0);
  v16 = v15;
  if ( !v15 )
  {
    *a3 = v11;
    goto LABEL_15;
  }
  if ( v15 != 2 )
  {
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)(*(_QWORD *)(v11 + 16) + 56LL));
    FltReleaseContext((PFLT_CONTEXT)v11);
LABEL_15:
    Status = (unsigned int)CallbackData->IoStatus.Status;
    Information = CallbackData->IoStatus.Information;
    goto LABEL_16;
  }
  Status = 259;
  Information = 0;
LABEL_16:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qldPq(WPP_GLOBAL_Control->AttachedDevice, 38, Status, CallbackData, v16, Status, Information, 0);
  }
  FltReleaseContext(v10);
  return v16;
}

```

## disassembly

```asm
0x140001e40  push    rbx
0x140001e42  push    rdi
0x140001e43  push    r14
0x140001e45  sub     rsp, 80h
0x140001e4c  mov     rax, [rcx+10h]
0x140001e50  mov     r14, r8
0x140001e53  mov     rdi, rdx
0x140001e56  mov     rbx, rcx
0x140001e59  cmp     dword ptr [rax+18h], 0
0x140001e5d  jz      loc_1400021A8
0x140001e63  mov     eax, [rax]
0x140001e65  mov     [rsp+98h+var_38], r15
0x140001e6a  test    al, 2
0x140001e6c  jnz     loc_140002036
0x140001e72  mov     r15, [rdx+20h]
0x140001e76  call    cs:__imp_IoGetTopLevelIrp
0x140001e7d  nop     dword ptr [rax+rax+00h]
0x140001e82  test    rax, rax
0x140001e85  jnz     loc_140002036
0x140001e8b  mov     r8, [rdi+20h]; FileObject
0x140001e8f  mov     rcx, rbx; CallbackData
0x140001e92  mov     rdx, [rdi+18h]; Instance
0x140001e96  mov     [rsp+98h+var_20], rsi
0x140001e9b  call    HsmpGetStreamHandleContext
0x140001ea0  mov     [rsp+98h+arg_18], rax
0x140001ea8  mov     rsi, rax
0x140001eab  test    rax, rax
0x140001eae  jz      loc_1400021B2
0x140001eb4  mov     rax, [rax+10h]
0x140001eb8  mov     r9, rsi
0x140001ebb  mov     [rsp+98h+arg_10], rbp
0x140001ec3  mov     r8b, 1
0x140001ec6  mov     [rsp+98h+var_28], r12
0x140001ecb  xor     edx, edx
0x140001ecd  mov     rcx, rbx
0x140001ed0  mov     [rsp+98h+var_30], r13
0x140001ed5  mov     [rsp+98h+CallbackData], rax
0x140001eda  call    HsmpTracePreCallbackEnter
0x140001edf  mov     rbp, [rsi+10h]
0x140001ee3  mov     rdx, rbx; CallbackData
0x140001ee6  mov     rcx, rbp; Context
0x140001ee9  mov     rax, [rbp+10h]
0x140001eed  mov     r12, [rax+20h]
0x140001ef1  mov     r13, [rax+10h]
0x140001ef5  mov     [rsp+98h+arg_8], r12
0x140001efd  call    HsmpAcquireUserRequestRundownProtection
0x140001f02  mov     ecx, eax
0x140001f04  mov     [rsp+98h+arg_0], eax
0x140001f0b  mov     edi, eax
0x140001f0d  call    HsmDbgBreakOnStatus
0x140001f12  lea     rax, WPP_GLOBAL_Control
0x140001f19  test    edi, edi
0x140001f1b  js      loc_14000204D
0x140001f21  call    cs:__imp_IoGetTopLevelIrp
0x140001f28  nop     dword ptr [rax+rax+00h]
0x140001f2d  test    rax, rax
0x140001f30  jnz     short loc_140001F6D
0x140001f32  call    cs:__imp_KeAreAllApcsDisabled
0x140001f39  nop     dword ptr [rax+rax+00h]
0x140001f3e  test    al, al
0x140001f40  jnz     short loc_140001F6D
0x140001f42  movzx   eax, byte ptr [r13+18h]
0x140001f47  test    al, al
0x140001f49  jnz     short loc_140001F6D
0x140001f4b  cmp     qword ptr cs:__Config+8, 0
0x140001f53  jz      short loc_140001F6D
0x140001f55  mov     eax, [rbp+24h]
0x140001f58  test    eax, eax
0x140001f5a  jnz     short loc_140001F6D
0x140001f5c  mov     r9, r15
0x140001f5f  mov     r8, rsi
0x140001f62  mov     rdx, rbp
0x140001f65  mov     rcx, rbx; CallbackData
0x140001f68  call    HsmpUpdateLastAccessTime
0x140001f6d  mov     r8, [rbx+10h]
0x140001f71  xor     r13d, r13d
0x140001f74  mov     [rsp+98h+var_58], r13; __int64
0x140001f79  mov     r9d, 9; int
0x140001f7f  mov     qword ptr [rsp+98h+var_60], r13; int
0x140001f84  mov     rdx, rbp; int
0x140001f87  mov     rcx, rsi; int
0x140001f8a  mov     eax, [r8+18h]
0x140001f8e  mov     [rsp+98h+var_68], rax; __int64
0x140001f93  mov     rax, [r8+28h]
0x140001f97  mov     r8, [r8+8]; int
0x140001f9b  mov     [rsp+98h+var_70], rax; __int64
0x140001fa0  mov     [rsp+98h+CallbackData], rbx; CallbackData
0x140001fa5  call    HsmpRecallInitiateHydrationEx
0x140001faa  mov     edi, eax
0x140001fac  test    eax, eax
0x140001fae  jz      loc_1400021BC
0x140001fb4  cmp     eax, 2
0x140001fb7  jz      loc_1400021C4
0x140001fbd  mov     rcx, [rbp+10h]
0x140001fc1  add     rcx, 38h ; '8'; RunRef
0x140001fc5  call    cs:__imp_ExReleaseRundownProtection
0x140001fcc  nop     dword ptr [rax+rax+00h]
0x140001fd1  mov     rcx, rbp; Context
0x140001fd4  call    cs:__imp_FltReleaseContext
0x140001fdb  nop     dword ptr [rax+rax+00h]
0x140001fe0  lea     rax, WPP_GLOBAL_Control
0x140001fe7  mov     r8d, [rbx+18h]
0x140001feb  mov     r9, [rbx+20h]
0x140001fef  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ff6  mov     r12, [rsp+98h+var_28]
0x140001ffb  mov     rbp, [rsp+98h+arg_10]
0x140002003  cmp     rcx, rax
0x140002006  jz      short loc_140002019
0x140002008  mov     eax, [rcx+2Ch]
0x14000200b  test    al, 4
0x14000200d  jz      short loc_140002019
0x14000200f  cmp     byte ptr [rcx+29h], 4
0x140002013  jnb     loc_14000217F
0x140002019  mov     rcx, rsi; Context
0x14000201c  call    cs:__imp_FltReleaseContext
0x140002023  nop     dword ptr [rax+rax+00h]
0x140002028  mov     r13, [rsp+98h+var_30]
0x14000202d  mov     eax, edi
0x14000202f  mov     rsi, [rsp+98h+var_20]
0x140002034  jmp     short loc_14000203B
0x140002036  mov     eax, 1
0x14000203b  mov     r15, [rsp+98h+var_38]
0x140002040  add     rsp, 80h
0x140002047  pop     r14
0x140002049  pop     rdi
0x14000204a  pop     rbx
0x14000204b  retn
0x14000204d  mov     r10, cs:WPP_GLOBAL_Control
0x140002054  cmp     r10, rax
0x140002057  jz      short loc_1400020B4
0x140002059  mov     ecx, [r10+2Ch]
0x14000205d  test    cl, 1
0x140002060  jz      short loc_1400020B4
0x140002062  cmp     byte ptr [r10+29h], 2
0x140002067  jb      short loc_1400020B4
0x140002069  mov     rcx, rbp
0x14000206c  call    HsmpGetStreamSize
0x140002071  mov     rcx, [r10+18h]
0x140002075  lea     r8, WPP_d740c0600e633b6822d4efc3e3ecf6a6_Traceguids
0x14000207c  mov     dword ptr [rsp+98h+var_48], edi
0x140002080  mov     edx, 0Bh
0x140002085  mov     [rsp+98h+var_50], rbx
0x14000208a  mov     r9, r13
0x14000208d  mov     [rsp+98h+var_58], r12
0x140002092  mov     qword ptr [rsp+98h+var_60], r15
0x140002097  mov     [rsp+98h+var_68], rax
0x14000209c  mov     eax, [rbp+1Ch]
0x14000209f  mov     dword ptr [rsp+98h+var_70], eax
0x1400020a3  mov     [rsp+98h+CallbackData], rbp
0x1400020a8  call    WPP_SF_qqLiqiqd
0x1400020ad  lea     rax, WPP_GLOBAL_Control
0x1400020b4  xor     r13d, r13d
0x1400020b7  mov     [rbx+18h], edi
0x1400020ba  mov     [rbx+20h], r13
0x1400020be  mov     r12, cs:WPP_GLOBAL_Control
0x1400020c5  mov     edi, 4
0x1400020ca  cmp     r12, rax
0x1400020cd  jz      loc_140001FE7
0x1400020d3  mov     eax, [r12+2Ch]
0x1400020d8  test    al, 1
0x1400020da  jz      loc_140001FE0
0x1400020e0  cmp     byte ptr [r12+29h], 2
0x1400020e6  jb      loc_140001FE0
0x1400020ec  mov     rax, [rbx+10h]
0x1400020f0  mov     rcx, rbx; CallbackData
0x1400020f3  mov     r12, [r12+18h]
0x1400020f8  mov     r15d, [rax]
0x1400020fb  mov     edi, r15d
0x1400020fe  mov     rsi, [rax+8]
0x140002102  not     r15b
0x140002105  mov     ebp, [rax+18h]
0x140002108  and     r15b, 1
0x14000210c  mov     r14, [rax+28h]
0x140002110  shr     edi, 1
0x140002112  and     dil, 1
0x140002116  call    cs:__imp_FltIsOperationSynchronous
0x14000211d  nop     dword ptr [rax+rax+00h]
0x140002122  mov     ecx, [rsp+98h+arg_0]
0x140002129  lea     r8, WPP_d740c0600e633b6822d4efc3e3ecf6a6_Traceguids
0x140002130  mov     [rsp+98h+var_40], ecx
0x140002134  mov     edx, 0Ch
0x140002139  mov     rcx, [rsp+98h+arg_8]
0x140002141  mov     r9, rbx
0x140002144  mov     [rsp+98h+var_48], rcx
0x140002149  mov     rcx, r12
0x14000214c  mov     [rsp+98h+var_50], rsi
0x140002151  mov     byte ptr [rsp+98h+var_58], dil
0x140002156  mov     byte ptr [rsp+98h+var_60], r15b
0x14000215b  mov     byte ptr [rsp+98h+var_68], al
0x14000215f  mov     dword ptr [rsp+98h+var_70], ebp
0x140002163  mov     [rsp+98h+CallbackData], r14
0x140002168  call    WPP_SF_qiDcccqid
0x14000216d  mov     rsi, [rsp+98h+arg_18]
0x140002175  mov     edi, 4
0x14000217a  jmp     loc_140001FE0
0x14000217f  mov     rcx, [rcx+18h]
0x140002183  mov     edx, 26h ; '&'
0x140002188  mov     qword ptr [rsp+98h+var_60], r13
0x14000218d  mov     [rsp+98h+var_68], r9
0x140002192  mov     r9, rbx
0x140002195  mov     dword ptr [rsp+98h+var_70], r8d
0x14000219a  mov     dword ptr [rsp+98h+CallbackData], edi
0x14000219e  call    WPP_SF_qldPq
0x1400021a3  jmp     loc_140002019
0x1400021a8  mov     eax, 1
0x1400021ad  jmp     loc_140002040
0x1400021b2  mov     eax, 1
0x1400021b7  jmp     loc_14000202F
0x1400021bc  mov     [r14], rbp
0x1400021bf  jmp     loc_140001FE0
0x1400021c4  mov     r8d, 103h
0x1400021ca  lea     rax, WPP_GLOBAL_Control
0x1400021d1  mov     r9, r13
0x1400021d4  jmp     loc_140001FEF
```
