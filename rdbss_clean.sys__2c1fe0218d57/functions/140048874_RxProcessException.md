# RxProcessException

- ea: `0x140048874`
- end: `0x1400489f8`
- name: `RxProcessException`
- size: `388`
- prototype: `NTSTATUS __stdcall(PRX_CONTEXT RxContext, NTSTATUS ExceptionCode)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140015290`
- `0x140047970`
- `0x140048f10`
- `0x14004a4e0`

## callees

- `0x1400027b0`
- `0x140004050`
- `0x140008030`
- `0x140009b80`
- `0x140016e20`
- `0x140017280`
- `0x140048874`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1400488c5`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1400488c5`
- `ntoskrnl!CcMdlWriteAbort` at `0x140048930`
- `ntoskrnl!CcMdlWriteAbort` at `0x140048930`
- `ntoskrnl!KeBugCheckEx` at `0x1400488ed`
- `ntoskrnl!KeBugCheckEx` at `0x1400488ed`

## pseudocode

```c
NTSTATUS __stdcall RxProcessException(PRX_CONTEXT RxContext, NTSTATUS ExceptionCode)
{
  PIRP CurrentIrp; // rdi
  NTSTATUS StoredStatus; // esi
  ULONG v5; // r8d
  const CHAR *v6; // r9
  struct _MDL *MdlAddress; // rdx
  struct _MRX_FCB_ *pFcb; // rdi
  ULONG BugCheckParameter4; // [rsp+20h] [rbp-38h]

  CurrentIrp = RxContext->CurrentIrp;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      12,
      &WPP_654ab715b6f236bf7ede1261f25b1912_Traceguids,
      (unsigned int)ExceptionCode);
  }
  StoredStatus = RxContext->StoredStatus;
  if ( !FsRtlIsNtstatusExpected(StoredStatus) )
    KeBugCheckEx(0x27u, 0xBAAD00B7, 0, 0, 0);
  if ( !LOBYTE(RxContext->RealDevice) )
    RxpPrepareCreateContextForReuse(RxContext);
  if ( LOBYTE(RxContext->RealDevice) == 4 && (BYTE1(RxContext->RealDevice) & 6) == 2 )
  {
    if ( CurrentIrp )
    {
      MdlAddress = CurrentIrp->MdlAddress;
      if ( MdlAddress )
      {
        CcMdlWriteAbort(CurrentIrp->Tail.Overlay.CurrentStackLocation->FileObject, MdlAddress);
        CurrentIrp->MdlAddress = 0;
      }
    }
  }
  pFcb = RxContext->pFcb;
  if ( pFcb )
  {
    if ( LOBYTE(RxContext->Flags) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, &WPP_654ab715b6f236bf7ede1261f25b1912_Traceguids);
      }
      _RxReleaseFcb(RxContext, pFcb, v5, v6, BugCheckParameter4);
      LOBYTE(RxContext->Flags) = 0;
    }
    if ( BYTE1(RxContext->Flags) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, &WPP_654ab715b6f236bf7ede1261f25b1912_Traceguids);
      }
      RxReleasePagingIoResource(RxContext, pFcb);
    }
  }
  RxCompleteRequestEx(RxContext, RxContext->CurrentIrp, StoredStatus);
  return StoredStatus;
}

```

## disassembly

```asm
0x140048874  push    rbx
0x140048876  push    rsi
0x140048877  push    rdi
0x140048878  push    r12
0x14004887a  sub     rsp, 38h
0x14004887e  mov     rdi, [rcx+28h]
0x140048882  mov     r9d, edx
0x140048885  mov     rbx, rcx
0x140048888  mov     rcx, cs:WPP_GLOBAL_Control
0x14004888f  lea     r12, WPP_GLOBAL_Control
0x140048896  cmp     rcx, r12
0x140048899  jz      short loc_1400488BD
0x14004889b  mov     eax, [rcx+2Ch]
0x14004889e  test    al, 2
0x1400488a0  jz      short loc_1400488BD
0x1400488a2  cmp     byte ptr [rcx+29h], 2
0x1400488a6  jb      short loc_1400488BD
0x1400488a8  mov     rcx, [rcx+18h]
0x1400488ac  lea     r8, WPP_654ab715b6f236bf7ede1261f25b1912_Traceguids
0x1400488b3  mov     edx, 0Ch
0x1400488b8  call    WPP_SF_d
0x1400488bd  mov     esi, [rbx+0B0h]
0x1400488c3  mov     ecx, esi; Exception
0x1400488c5  call    cs:__imp_FsRtlIsNtstatusExpected
0x1400488cc  nop     dword ptr [rax+rax+00h]
0x1400488d1  test    al, al
0x1400488d3  jnz     short loc_1400488FA
0x1400488d5  xor     r9d, r9d; BugCheckParameter3
0x1400488d8  mov     qword ptr [rsp+58h+BugCheckParameter4], 0; BugCheckParameter4
0x1400488e1  xor     r8d, r8d; BugCheckParameter2
0x1400488e4  mov     edx, 0BAAD00B7h; BugCheckParameter1
0x1400488e9  lea     ecx, [r9+27h]; BugCheckCode
0x1400488ed  call    cs:__imp_KeBugCheckEx
0x1400488fa  cmp     byte ptr [rbx+20h], 0
0x1400488fe  jnz     short loc_140048908
0x140048900  mov     rcx, rbx; RxContext
0x140048903  call    RxpPrepareCreateContextForReuse
0x140048908  cmp     byte ptr [rbx+20h], 4
0x14004890c  jnz     short loc_140048944
0x14004890e  mov     al, [rbx+21h]
0x140048911  and     al, 6
0x140048913  cmp     al, 2
0x140048915  jnz     short loc_140048944
0x140048917  test    rdi, rdi
0x14004891a  jz      short loc_140048944
0x14004891c  mov     rdx, [rdi+8]; MdlChain
0x140048920  test    rdx, rdx
0x140048923  jz      short loc_140048944
0x140048925  mov     rcx, [rdi+0B8h]
0x14004892c  mov     rcx, [rcx+30h]; FileObject
0x140048930  call    cs:__imp_CcMdlWriteAbort
0x140048937  nop     dword ptr [rax+rax+00h]
0x14004893c  mov     qword ptr [rdi+8], 0
0x140048944  mov     rdi, [rbx+38h]
0x140048948  test    rdi, rdi
0x14004894b  jz      loc_1400489DC
0x140048951  cmp     byte ptr [rbx+0A8h], 0
0x140048958  jz      short loc_14004899A
0x14004895a  mov     rcx, cs:WPP_GLOBAL_Control
0x140048961  cmp     rcx, r12
0x140048964  jz      short loc_140048988
0x140048966  mov     eax, [rcx+2Ch]
0x140048969  test    al, 2
0x14004896b  jz      short loc_140048988
0x14004896d  cmp     byte ptr [rcx+29h], 4
0x140048971  jb      short loc_140048988
0x140048973  mov     rcx, [rcx+18h]
0x140048977  lea     r8, WPP_654ab715b6f236bf7ede1261f25b1912_Traceguids
0x14004897e  mov     edx, 0Dh
0x140048983  call    WPP_SF_
0x140048988  mov     rdx, rdi; MrxFcb
0x14004898b  mov     rcx, rbx; RxContext
0x14004898e  call    __RxReleaseFcb
0x140048993  mov     byte ptr [rbx+0A8h], 0
0x14004899a  cmp     byte ptr [rbx+0A9h], 0
0x1400489a1  jz      short loc_1400489DC
0x1400489a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400489aa  cmp     rcx, r12
0x1400489ad  jz      short loc_1400489D1
0x1400489af  mov     eax, [rcx+2Ch]
0x1400489b2  test    al, 2
0x1400489b4  jz      short loc_1400489D1
0x1400489b6  cmp     byte ptr [rcx+29h], 4
0x1400489ba  jb      short loc_1400489D1
0x1400489bc  mov     rcx, [rcx+18h]
0x1400489c0  lea     r8, WPP_654ab715b6f236bf7ede1261f25b1912_Traceguids
0x1400489c7  mov     edx, 0Eh
0x1400489cc  call    WPP_SF_
0x1400489d1  mov     rdx, rdi
0x1400489d4  mov     rcx, rbx
0x1400489d7  call    RxReleasePagingIoResource
0x1400489dc  mov     rdx, [rbx+28h]; Irp
0x1400489e0  mov     r8d, esi
0x1400489e3  mov     rcx, rbx; RxContext
0x1400489e6  call    RxCompleteRequestEx
0x1400489eb  mov     eax, esi
0x1400489ed  add     rsp, 38h
0x1400489f1  pop     r12
0x1400489f3  pop     rdi
0x1400489f4  pop     rsi
0x1400489f5  pop     rbx
0x1400489f6  retn
```
