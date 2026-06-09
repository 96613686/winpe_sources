# CdCreateReferenceObject

- ea: `0x14000df80`
- end: `0x14000e04b`
- name: `CdCreateReferenceObject`
- size: `203`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000df80`
- `0x14000e060`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000dff1`
- `ntoskrnl!IofCompleteRequest` at `0x14000e01a`
- `ntoskrnl!IofCompleteRequest` at `0x14000dff1`
- `ntoskrnl!IofCompleteRequest` at `0x14000e01a`

## pseudocode

```c
__int64 __fastcall CdCreateReferenceObject(PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  PFILE_OBJECT FileObject; // rdi
  struct _FILE_OBJECT *RelatedFileObject; // rax
  __int64 **FsContext; // rdx
  NTSTATUS v6; // esi
  void *v8; // [rsp+50h] [rbp+8h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v8 = 0;
  FileObject = CurrentStackLocation->FileObject;
  RelatedFileObject = FileObject->RelatedFileObject;
  if ( RelatedFileObject
    && RelatedFileObject->DeviceObject == (PDEVICE_OBJECT)CdDeviceObject
    && (FsContext = (__int64 **)RelatedFileObject->FsContext) != 0 )
  {
    if ( *FsContext == CdServerType || *FsContext == CdConnectionType )
    {
      v6 = CdpAllocateReferenceObject(&v8);
      if ( v6 >= 0 )
      {
        FileObject->FsContext = v8;
        Irp->IoStatus.Status = 0;
        Irp->IoStatus.Information = 0;
        IofCompleteRequest(Irp, 0);
        return 0;
      }
    }
    else
    {
      v6 = -1073741788;
    }
  }
  else
  {
    v6 = -1073741816;
  }
  Irp->IoStatus.Status = v6;
  Irp->IoStatus.Information = 0;
  IofCompleteRequest(Irp, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000df80  push    rbx
0x14000df82  push    rbp
0x14000df83  push    rsi
0x14000df84  push    rdi
0x14000df85  sub     rsp, 28h
0x14000df89  mov     rax, [rcx+0B8h]
0x14000df90  xor     ebp, ebp
0x14000df92  mov     rbx, rcx
0x14000df95  mov     [rsp+48h+arg_0], rbp
0x14000df9a  mov     rdi, [rax+30h]
0x14000df9e  mov     rax, [rdi+40h]
0x14000dfa2  test    rax, rax
0x14000dfa5  jz      short loc_14000E009
0x14000dfa7  mov     rdx, cs:CdDeviceObject
0x14000dfae  cmp     [rax+8], rdx
0x14000dfb2  jnz     short loc_14000E009
0x14000dfb4  mov     rdx, [rax+18h]
0x14000dfb8  test    rdx, rdx
0x14000dfbb  jz      short loc_14000E009
0x14000dfbd  mov     rax, [rdx]
0x14000dfc0  lea     rcx, CdServerType
0x14000dfc7  cmp     rax, rcx
0x14000dfca  jnz     short loc_14000E032
0x14000dfcc  lea     rcx, [rsp+48h+arg_0]
0x14000dfd1  call    CdpAllocateReferenceObject
0x14000dfd6  mov     esi, eax
0x14000dfd8  test    eax, eax
0x14000dfda  js      short loc_14000E00E
0x14000dfdc  mov     rax, [rsp+48h+arg_0]
0x14000dfe1  xor     edx, edx; PriorityBoost
0x14000dfe3  mov     [rdi+18h], rax
0x14000dfe7  mov     rcx, rbx; Irp
0x14000dfea  mov     [rbx+30h], ebp
0x14000dfed  mov     [rbx+38h], rbp
0x14000dff1  call    cs:__imp_IofCompleteRequest
0x14000dff8  nop     dword ptr [rax+rax+00h]
0x14000dffd  xor     eax, eax
0x14000dfff  add     rsp, 28h
0x14000e003  pop     rdi
0x14000e004  pop     rsi
0x14000e005  pop     rbp
0x14000e006  pop     rbx
0x14000e007  retn
0x14000e009  mov     esi, 0C0000008h
0x14000e00e  xor     edx, edx; PriorityBoost
0x14000e010  mov     [rbx+30h], esi
0x14000e013  mov     rcx, rbx; Irp
0x14000e016  mov     [rbx+38h], rbp
0x14000e01a  call    cs:__imp_IofCompleteRequest
0x14000e021  nop     dword ptr [rax+rax+00h]
0x14000e026  mov     eax, esi
0x14000e028  add     rsp, 28h
0x14000e02c  pop     rdi
0x14000e02d  pop     rsi
0x14000e02e  pop     rbp
0x14000e02f  pop     rbx
0x14000e030  retn
0x14000e032  lea     rcx, CdConnectionType
0x14000e039  cmp     rax, rcx
0x14000e03c  jnz     short loc_14000E044
0x14000e03e  mov     rdx, [rdx+18h]
0x14000e042  jmp     short loc_14000DFCC
0x14000e044  mov     esi, 0C0000024h
0x14000e049  jmp     short loc_14000E00E
```
