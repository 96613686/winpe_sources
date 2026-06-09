# CClfsRequest::Close(_IRP *)

- ea: `0x14006ddb0`
- end: `0x14006defd`
- name: `?Close@CClfsRequest@@SAJPEAU_IRP@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14006c520`

## callees

- `0x1400055a8`
- `0x140005840`
- `0x14000c2f0`
- `0x140017f20`
- `0x140059e80`
- `0x14006ddb0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006de6c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006de6c`
- `ntoskrnl!KeBugCheckEx` at `0x14006de10`
- `ntoskrnl!KeBugCheckEx` at `0x14006de10`
- `ntoskrnl!IofCompleteRequest` at `0x14006dee0`
- `ntoskrnl!IofCompleteRequest` at `0x14007b9af`
- `ntoskrnl!IofCompleteRequest` at `0x14006dee0`
- `ntoskrnl!IofCompleteRequest` at `0x14007b9af`

## pseudocode

```c
__int64 __fastcall CClfsRequest::Close(PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  PFILE_OBJECT FileObject; // r14
  CClfsLogFcbCommon *v4; // rsi
  CClfsLogCcb *FsContext2; // rdi
  PVOID v6; // rcx
  struct _FILE_OBJECT *v7; // rdx
  BOOLEAN v9; // [rsp+30h] [rbp-58h]

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->MajorFunction != 2 )
    KeBugCheckEx(0xC1F5u, 0x46u, CurrentStackLocation->MajorFunction, 0, 0);
  FileObject = CurrentStackLocation->FileObject;
  v4 = (CClfsLogFcbCommon *)*((_QWORD *)FileObject->FsContext + 15);
  (*(void (__fastcall **)(CClfsLogFcbCommon *))(*(_QWORD *)v4 + 64LL))(v4);
  FsContext2 = (CClfsLogCcb *)CurrentStackLocation->FileObject->FsContext2;
  if ( FsContext2 )
  {
    CClfsLogCcb::AddRef(FsContext2);
    CClfsLogCcb::Release(v6);
  }
  v9 = ExAcquireResourceExclusiveLite((PERESOURCE)((char *)v4 + 200), 1u);
  CClfsLogFcbCommon::Close(v4, v7);
  if ( v9 )
    ClfsReleaseResourceLite((char *)v4 + 200);
  FileObject->FsContext = 0;
  FileObject->FsContext2 = 0;
  if ( FsContext2 )
    CClfsLogCcb::Release(FsContext2);
  (*(void (__fastcall **)(CClfsLogFcbCommon *))(*(_QWORD *)v4 + 72LL))(v4);
  Irp->IoStatus.Status = 0;
  Irp->IoStatus.Information = 0;
  IofCompleteRequest(Irp, 0);
  return 0;
}

```

## disassembly

```asm
0x14006ddb0  mov     rax, rsp
0x14006ddb3  mov     [rax+8], rcx
0x14006ddb7  push    rbx
0x14006ddb8  push    rsi
0x14006ddb9  push    rdi
0x14006ddba  push    r12
0x14006ddbc  push    r14
0x14006ddbe  push    r15
0x14006ddc0  sub     rsp, 58h
0x14006ddc4  mov     rbx, rcx
0x14006ddc7  mov     dword ptr [rax-54h], 0
0x14006ddce  mov     byte ptr [rax-58h], 0
0x14006ddd2  mov     qword ptr [rax-48h], 0
0x14006ddda  mov     qword ptr [rax-50h], 0
0x14006dde2  mov     qword ptr [rax-40h], 0
0x14006ddea  mov     rdi, [rcx+0B8h]
0x14006ddf1  movzx   eax, byte ptr [rdi]
0x14006ddf4  cmp     al, 2
0x14006ddf6  jz      short loc_14006DE1C
0x14006ddf8  mov     r8d, eax; BugCheckParameter2
0x14006ddfb  mov     [rsp+88h+BugCheckParameter4], 0; BugCheckParameter4
0x14006de04  xor     r9d, r9d; BugCheckParameter3
0x14006de07  lea     edx, [r9+46h]; BugCheckParameter1
0x14006de0b  mov     ecx, 0C1F5h; BugCheckCode
0x14006de10  call    cs:__imp_KeBugCheckEx
0x14006de1c  mov     r14, [rdi+30h]
0x14006de20  mov     [rsp+88h+var_48], r14
0x14006de25  mov     rax, [r14+18h]
0x14006de29  mov     rsi, [rax+78h]
0x14006de2d  mov     [rsp+88h+var_50], rsi
0x14006de32  mov     rax, [rsi]
0x14006de35  mov     rax, [rax+40h]
0x14006de39  mov     rcx, rsi
0x14006de3c  call    _guard_dispatch_icall
0x14006de41  mov     rax, [rdi+30h]
0x14006de45  mov     rdi, [rax+20h]
0x14006de49  mov     [rsp+88h+var_40], rdi
0x14006de4e  test    rdi, rdi
0x14006de51  jz      short loc_14006DE60
0x14006de53  mov     rcx, rdi; this
0x14006de56  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x14006de5b  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14006de60  lea     r12, [rsi+0C8h]
0x14006de67  mov     dl, 1; Wait
0x14006de69  mov     rcx, r12; Resource
0x14006de6c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14006de73  nop     dword ptr [rax+rax+00h]
0x14006de78  mov     r15b, al
0x14006de7b  mov     [rsp+88h+var_58], al
0x14006de7f  mov     rcx, rsi; this
0x14006de82  call    ?Close@CClfsLogFcbCommon@@QEAAJPEAU_FILE_OBJECT@@@Z; CClfsLogFcbCommon::Close(_FILE_OBJECT *)
0x14006de87  mov     [rsp+88h+var_54], eax
0x14006de8b  mov     [rsp+88h+var_54], 0
0x14006de93  test    r15b, r15b
0x14006de96  jz      short loc_14006DEA0
0x14006de98  mov     rcx, r12
0x14006de9b  call    ClfsReleaseResourceLite
0x14006dea0  mov     qword ptr [r14+18h], 0
0x14006dea8  mov     qword ptr [r14+20h], 0
0x14006deb0  test    rdi, rdi
0x14006deb3  jz      short loc_14006DEBD
0x14006deb5  mov     rcx, rdi; Entry
0x14006deb8  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14006debd  mov     rax, [rsi]
0x14006dec0  mov     rax, [rax+48h]
0x14006dec4  mov     rcx, rsi
0x14006dec7  call    _guard_dispatch_icall
0x14006decc  mov     dword ptr [rbx+30h], 0
0x14006ded3  mov     qword ptr [rbx+38h], 0
0x14006dedb  xor     edx, edx; PriorityBoost
0x14006dedd  mov     rcx, rbx; Irp
0x14006dee0  call    cs:__imp_IofCompleteRequest
0x14006dee7  nop     dword ptr [rax+rax+00h]
0x14006deec  xor     eax, eax
0x14006deee  add     rsp, 58h
0x14006def2  pop     r15
0x14006def4  pop     r14
0x14006def6  pop     r12
0x14006def8  pop     rdi
0x14006def9  pop     rsi
0x14006defa  pop     rbx
0x14006defb  retn
0x14007b937  push    rbp
0x14007b939  sub     rsp, 30h
0x14007b93d  mov     rbp, rdx
0x14007b940  cmp     byte ptr [rbp+30h], 0
0x14007b944  jz      short loc_14007B95A
0x14007b946  mov     rcx, [rbp+38h]
0x14007b94a  add     rcx, 0C8h
0x14007b951  call    ClfsReleaseResourceLite
0x14007b956  mov     byte ptr [rbp+30h], 0
0x14007b95a  mov     rax, [rbp+40h]
0x14007b95e  test    rax, rax
0x14007b961  jz      short loc_14007B973
0x14007b963  mov     qword ptr [rax+18h], 0
0x14007b96b  mov     qword ptr [rax+20h], 0
0x14007b973  mov     rcx, [rbp+48h]; Entry
0x14007b977  test    rcx, rcx
0x14007b97a  jz      short loc_14007B982
0x14007b97c  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14007b981  nop
0x14007b982  mov     rcx, [rbp+38h]
0x14007b986  test    rcx, rcx
0x14007b989  jz      short loc_14007B998
0x14007b98b  mov     rax, [rcx]
0x14007b98e  mov     rax, [rax+48h]
0x14007b992  call    _guard_dispatch_icall
0x14007b997  nop
0x14007b998  mov     eax, [rbp+34h]
0x14007b99b  mov     rcx, [rbp+90h]; Irp
0x14007b9a2  mov     [rcx+30h], eax
0x14007b9a5  mov     qword ptr [rcx+38h], 0
0x14007b9ad  xor     edx, edx; PriorityBoost
0x14007b9af  call    cs:__imp_IofCompleteRequest
0x14007b9b6  nop     dword ptr [rax+rax+00h]
0x14007b9bb  nop
0x14007b9bc  add     rsp, 30h
0x14007b9c0  pop     rbp
0x14007b9c1  retn
```
