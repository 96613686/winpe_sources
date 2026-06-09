# RxCommonDeviceControl

- ea: `0x140065fa0`
- end: `0x14006627a`
- name: `RxCommonDeviceControl`
- size: `730`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp, __int64 FsContext2)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140007ca0`
- `0x1400146a0`
- `0x140016e20`
- `0x140016e70`
- `0x140016fc0`
- `0x140017280`
- `0x140065fa0`
- `0x140067ad0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140066090`
- `ntoskrnl!KeInitializeEvent` at `0x140066090`

## pseudocode

```c
__int64 __fastcall RxCommonDeviceControl(PRX_CONTEXT RxContext, PIRP Irp, PVOID FsContext2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  ULONG LowPart; // ebp
  PFILE_OBJECT FileObject; // rax
  struct _FCB *FsContext; // rdi
  CSHORT NodeTypeCode; // cx
  int v10; // ebx
  char v11; // al
  NTSTATUS v12; // eax
  __int64 result; // rax
  unsigned __int16 v14; // dx

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, &WPP_f50d4438d5ba35c472c496784879ba96_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, &WPP_f50d4438d5ba35c472c496784879ba96_Traceguids, Irp);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          &WPP_f50d4438d5ba35c472c496784879ba96_Traceguids,
          CurrentStackLocation->MinorFunction);
      }
    }
  }
  FileObject = CurrentStackLocation->FileObject;
  if ( FileObject )
  {
    FsContext = (struct _FCB *)FileObject->FsContext;
    FsContext2 = FileObject->FsContext2;
    NodeTypeCode = FsContext->Header.NodeTypeCode;
    if ( FsContext->Header.NodeTypeCode == -5085 && FsContext2 )
    {
      v14 = -5080;
LABEL_20:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qqqL(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          &WPP_f50d4438d5ba35c472c496784879ba96_Traceguids,
          RxContext,
          FsContext2,
          FsContext,
          v14);
      }
      return 3221225485LL;
    }
    if ( (unsigned __int16)(NodeTypeCode + 5087) > 1u )
    {
      v14 = FsContext->Header.NodeTypeCode;
      if ( NodeTypeCode != -5088 )
        goto LABEL_20;
    }
  }
  else
  {
    FsContext = 0;
  }
  if ( ((LowPart - 1311119) & 0xFFFFFFFB) != 0 )
  {
    v10 = -1073741811;
    v11 = 1;
  }
  else
  {
    v10 = -1073741808;
    v11 = 0;
  }
  if ( LowPart == 1344540 || LowPart == 1328152 )
  {
    LOBYTE(FsContext2) = 1;
    result = RxProcessCopyChunkIoctlOrFsCtl(RxContext, Irp, (__int64)FsContext2);
    v10 = result;
    if ( (_DWORD)result == 259 )
      return result;
  }
  else if ( v11 )
  {
    KeInitializeEvent((PRKEVENT)&RxContext->PrefixClaim.NetRootType, NotificationEvent, 0);
    *((_WORD *)&RxContext->9 + 60) = 7;
    RxContext->Create.PipeCompletionMode = 0;
    *((_QWORD *)&RxContext->9 + 21) = 0;
    RxContext->Create.TransportName.Buffer = 0;
    *((_BYTE *)&RxContext->9 + 176) = 0;
    *((_QWORD *)&RxContext->9 + 19) = 0;
    v12 = RxLowIoSubmit(RxContext, Irp, FsContext, RxLowIoIoCtlShellCompletion);
LABEL_16:
    v10 = v12;
    goto LABEL_17;
  }
  if ( BYTE3(RxContext->RealDevice) )
  {
    v12 = RxFsdPostRequest(RxContext);
    goto LABEL_16;
  }
LABEL_17:
  if ( v10 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        &WPP_f50d4438d5ba35c472c496784879ba96_Traceguids,
        (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140065fa0  push    rbx
0x140065fa2  push    rbp
0x140065fa3  push    rsi
0x140065fa4  push    r12
0x140065fa6  push    r14
0x140065fa8  push    r15
0x140065faa  sub     rsp, 48h
0x140065fae  mov     rbx, [rdx+0B8h]
0x140065fb5  mov     rsi, rdx
0x140065fb8  mov     r14, rcx
0x140065fbb  mov     ebp, [rbx+18h]
0x140065fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x140065fc5  lea     r15, WPP_GLOBAL_Control
0x140065fcc  cmp     rcx, r15
0x140065fcf  jz      short loc_14006600A
0x140065fd1  mov     eax, [rcx+2Ch]
0x140065fd4  test    al, 2
0x140065fd6  jnz     loc_140066156
0x140065fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x140065fe3  cmp     rcx, r15
0x140065fe6  jz      short loc_14006600A
0x140065fe8  mov     eax, [rcx+2Ch]
0x140065feb  test    al, 2
0x140065fed  jnz     loc_14006617A
0x140065ff3  mov     rcx, cs:WPP_GLOBAL_Control
0x140065ffa  cmp     rcx, r15
0x140065ffd  jz      short loc_14006600A
0x140065fff  mov     eax, [rcx+2Ch]
0x140066002  test    al, 2
0x140066004  jnz     loc_1400661A1
0x14006600a  mov     rax, [rbx+30h]
0x14006600e  xor     r12d, r12d
0x140066011  mov     [rsp+78h+arg_0], rdi
0x140066019  test    rax, rax
0x14006601c  jz      loc_14006620D
0x140066022  mov     rdi, [rax+18h]
0x140066026  mov     r8, [rax+20h]
0x14006602a  mov     eax, 0EC23h
0x14006602f  movzx   ecx, word ptr [rdi]
0x140066032  cmp     cx, ax
0x140066035  jz      loc_140066146
0x14006603b  mov     eax, 13DFh
0x140066040  add     eax, ecx
0x140066042  cmp     ax, 1
0x140066046  ja      loc_140066101
0x14006604c  lea     eax, [rbp-14018Fh]
0x140066052  test    eax, 0FFFFFFFBh
0x140066057  jz      loc_140066215
0x14006605d  mov     ebx, 0C000000Dh
0x140066062  mov     al, 1
0x140066064  cmp     ebp, 14841Ch
0x14006606a  jz      loc_140066129
0x140066070  cmp     ebp, 144418h
0x140066076  jz      loc_140066129
0x14006607c  test    al, al
0x14006607e  jz      loc_140066221
0x140066084  lea     rcx, [r14+180h]; Event
0x14006608b  xor     r8d, r8d; State
0x14006608e  xor     edx, edx; Type
0x140066090  call    cs:__imp_KeInitializeEvent
0x140066097  nop     dword ptr [rax+rax+00h]
0x14006609c  mov     word ptr [r14+208h], 7
0x1400660a6  lea     r9, RxLowIoIoCtlShellCompletion; CompletionRoutine
0x1400660ad  mov     [r14+218h], r12d
0x1400660b4  mov     r8, rdi; Fcb
0x1400660b7  mov     [r14+238h], r12
0x1400660be  mov     rdx, rsi; Irp
0x1400660c1  mov     [r14+230h], r12
0x1400660c8  mov     rcx, r14; RxContext
0x1400660cb  mov     [r14+240h], r12b
0x1400660d2  mov     [r14+228h], r12
0x1400660d9  call    RxLowIoSubmit
0x1400660de  mov     ebx, eax
0x1400660e0  test    ebx, ebx
0x1400660e2  js      loc_140066238
0x1400660e8  mov     eax, ebx
0x1400660ea  mov     rdi, [rsp+78h+arg_0]
0x1400660f2  add     rsp, 48h
0x1400660f6  pop     r15
0x1400660f8  pop     r14
0x1400660fa  pop     r12
0x1400660fc  pop     rsi
0x1400660fd  pop     rbp
0x1400660fe  pop     rbx
0x1400660ff  retn
0x140066101  mov     eax, 0EC20h
0x140066106  movzx   edx, cx
0x140066109  cmp     cx, ax
0x14006610c  jz      loc_14006604C
0x140066112  mov     rcx, cs:WPP_GLOBAL_Control
0x140066119  cmp     rcx, r15
0x14006611c  jnz     loc_1400661CA
0x140066122  mov     eax, 0C000000Dh
0x140066127  jmp     short loc_1400660EA
0x140066129  mov     r8b, 1
0x14006612c  mov     rdx, rsi; Irp
0x14006612f  mov     rcx, r14; RxContext
0x140066132  call    RxProcessCopyChunkIoctlOrFsCtl
0x140066137  mov     ebx, eax
0x140066139  cmp     eax, 103h
0x14006613e  jnz     loc_140066221
0x140066144  jmp     short loc_1400660EA
0x140066146  test    r8, r8
0x140066149  jz      loc_14006603B
0x14006614f  mov     edx, 0EC28h
0x140066154  jmp     short loc_140066112
0x140066156  cmp     byte ptr [rcx+29h], 4
0x14006615a  jb      loc_140065FDC
0x140066160  mov     rcx, [rcx+18h]
0x140066164  lea     r8, WPP_f50d4438d5ba35c472c496784879ba96_Traceguids
0x14006616b  mov     edx, 0Ah
0x140066170  call    WPP_SF_
0x140066175  jmp     loc_140065FDC
0x14006617a  cmp     byte ptr [rcx+29h], 4
0x14006617e  jb      loc_140065FF3
0x140066184  mov     rcx, [rcx+18h]
0x140066188  lea     r8, WPP_f50d4438d5ba35c472c496784879ba96_Traceguids
0x14006618f  mov     edx, 0Bh
0x140066194  mov     r9, rsi
0x140066197  call    WPP_SF_q
0x14006619c  jmp     loc_140065FF3
0x1400661a1  cmp     byte ptr [rcx+29h], 4
0x1400661a5  jb      loc_14006600A
0x1400661ab  movzx   r9d, byte ptr [rbx+1]
0x1400661b0  lea     r8, WPP_f50d4438d5ba35c472c496784879ba96_Traceguids
0x1400661b7  mov     rcx, [rcx+18h]
0x1400661bb  mov     edx, 0Ch
0x1400661c0  call    WPP_SF_d
0x1400661c5  jmp     loc_14006600A
0x1400661ca  mov     eax, [rcx+2Ch]
0x1400661cd  test    al, 1
0x1400661cf  jz      loc_140066122
0x1400661d5  cmp     byte ptr [rcx+29h], 1
0x1400661d9  jb      loc_140066122
0x1400661df  mov     rcx, [rcx+18h]
0x1400661e3  mov     r9, r14
0x1400661e6  movzx   eax, dx
0x1400661e9  mov     edx, 0Dh
0x1400661ee  mov     [rsp+78h+var_48], eax
0x1400661f2  mov     [rsp+78h+var_50], rdi
0x1400661f7  mov     [rsp+78h+var_58], r8
0x1400661fc  lea     r8, WPP_f50d4438d5ba35c472c496784879ba96_Traceguids
0x140066203  call    WPP_SF_qqqL
0x140066208  jmp     loc_140066122
0x14006620d  mov     rdi, r12
0x140066210  jmp     loc_14006604C
0x140066215  mov     ebx, 0C0000010h
0x14006621a  xor     al, al
0x14006621c  jmp     loc_140066064
0x140066221  cmp     [r14+23h], r12b
0x140066225  jz      loc_1400660E0
0x14006622b  mov     rcx, r14; RxContext
0x14006622e  call    RxFsdPostRequest
0x140066233  jmp     loc_1400660DE
0x140066238  mov     rcx, cs:WPP_GLOBAL_Control
0x14006623f  cmp     rcx, r15
0x140066242  jz      loc_1400660E8
0x140066248  mov     eax, [rcx+2Ch]
0x14006624b  test    al, 1
0x14006624d  jz      loc_1400660E8
0x140066253  cmp     byte ptr [rcx+29h], 1
0x140066257  jb      loc_1400660E8
0x14006625d  mov     rcx, [rcx+18h]
0x140066261  lea     r8, WPP_f50d4438d5ba35c472c496784879ba96_Traceguids
0x140066268  mov     edx, 0Eh
0x14006626d  mov     r9d, ebx
0x140066270  call    WPP_SF_d
0x140066275  jmp     loc_1400660E8
```
