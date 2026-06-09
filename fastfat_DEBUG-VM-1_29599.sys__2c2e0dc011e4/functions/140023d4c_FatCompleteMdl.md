# FatCompleteMdl

- ea: `0x140023d4c`
- end: `0x140023dec`
- name: `FatCompleteMdl`
- size: `160`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006030`
- `0x140007530`

## callees

- `0x140023d4c`
- `0x140038eb4`

## import_xrefs

- `ntoskrnl!CcMdlReadComplete` at `0x140023dbc`
- `ntoskrnl!CcMdlReadComplete` at `0x140023dbc`
- `ntoskrnl!CcMdlWriteComplete` at `0x140023da3`
- `ntoskrnl!CcMdlWriteComplete` at `0x140023da3`
- `ntoskrnl!KeBugCheckEx` at `0x140023d8e`
- `ntoskrnl!KeBugCheckEx` at `0x140023d8e`

## pseudocode

```c
__int64 __fastcall FatCompleteMdl(unsigned __int8 *Entry, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r9
  ULONG_PTR v5; // r8
  struct _FILE_OBJECT *FileObject; // rcx

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v5 = Entry[64];
  FileObject = CurrentStackLocation->FileObject;
  if ( (_DWORD)v5 == 3 )
  {
    CcMdlReadComplete(FileObject, Irp->MdlAddress);
  }
  else
  {
    if ( (_DWORD)v5 != 4 )
      KeBugCheckEx(0x23u, 0x307F5u, v5, 0, 0);
    CcMdlWriteComplete(FileObject, &CurrentStackLocation->Parameters.Read.ByteOffset, Irp->MdlAddress);
    Irp->IoStatus.Status = 0;
  }
  Irp->MdlAddress = 0;
  FatCompleteRequest_Real(Entry, Irp);
  return 0;
}

```

## disassembly

```asm
0x140023d4c  mov     [rsp+arg_0], rbx
0x140023d51  push    rdi
0x140023d52  sub     rsp, 30h
0x140023d56  mov     r9, [rdx+0B8h]
0x140023d5d  mov     rdi, rcx
0x140023d60  mov     rbx, rdx
0x140023d63  movzx   r8d, byte ptr [rdi+40h]; BugCheckParameter2
0x140023d68  mov     rcx, [r9+30h]; FileObject
0x140023d6c  mov     edx, r8d
0x140023d6f  sub     edx, 3
0x140023d72  jz      short loc_140023DB8
0x140023d74  cmp     edx, 1
0x140023d77  jz      short loc_140023D9B
0x140023d79  xor     r9d, r9d; BugCheckParameter3
0x140023d7c  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x140023d85  mov     edx, 307F5h; BugCheckParameter1
0x140023d8a  lea     ecx, [r9+23h]; BugCheckCode
0x140023d8e  call    cs:__imp_KeBugCheckEx
0x140023d9b  mov     r8, [rbx+8]; MdlChain
0x140023d9f  lea     rdx, [r9+18h]; FileOffset
0x140023da3  call    cs:__imp_CcMdlWriteComplete
0x140023daa  nop     dword ptr [rax+rax+00h]
0x140023daf  mov     dword ptr [rbx+30h], 0
0x140023db6  jmp     short loc_140023DC8
0x140023db8  mov     rdx, [rbx+8]; MdlChain
0x140023dbc  call    cs:__imp_CcMdlReadComplete
0x140023dc3  nop     dword ptr [rax+rax+00h]
0x140023dc8  xor     r8d, r8d
0x140023dcb  mov     qword ptr [rbx+8], 0
0x140023dd3  mov     rdx, rbx; Irp
0x140023dd6  mov     rcx, rdi; Entry
0x140023dd9  call    FatCompleteRequest_Real
0x140023dde  mov     rbx, [rsp+38h+arg_0]
0x140023de3  xor     eax, eax
0x140023de5  add     rsp, 30h
0x140023de9  pop     rdi
0x140023dea  retn
```
