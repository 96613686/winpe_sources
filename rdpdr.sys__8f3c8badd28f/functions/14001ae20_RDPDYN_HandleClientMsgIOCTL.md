# RDPDYN_HandleClientMsgIOCTL

- ea: `0x14001ae20`
- end: `0x14001af0a`
- name: `RDPDYN_HandleClientMsgIOCTL`
- size: `234`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002b930`

## callees

- `0x14000324c`
- `0x14000327c`
- `0x14001ac10`
- `0x14001ae20`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001aef2`
- `ntoskrnl!IofCompleteRequest` at `0x14001aef2`

## pseudocode

```c
__int64 __fastcall RDPDYN_HandleClientMsgIOCTL(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  PFILE_OBJECT FileObject; // rbx
  unsigned int *FsContext; // rbx
  unsigned int v6; // ebx
  NTSTATUS v7; // eax

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  if ( FileObject && (FsContext = (unsigned int *)FileObject->FsContext) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids, *FsContext);
    v6 = DrSendMessageToSession(
           *FsContext,
           a2->AssociatedIrp.MasterIrp,
           CurrentStackLocation->Parameters.Create.Options);
    if ( !v6 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids);
      a2->IoStatus.Information = 0;
      v7 = 0;
      goto LABEL_16;
    }
  }
  else
  {
    v6 = -1073741808;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids);
  v7 = v6;
LABEL_16:
  a2->IoStatus.Status = v7;
  IofCompleteRequest(a2, 0);
  return v6;
}

```

## disassembly

```asm
0x14001ae20  push    rbx
0x14001ae22  push    rbp
0x14001ae23  push    rsi
0x14001ae24  push    rdi
0x14001ae25  sub     rsp, 38h
0x14001ae29  mov     rsi, [rdx+0B8h]
0x14001ae30  lea     rbp, WPP_GLOBAL_Control
0x14001ae37  mov     rdi, rdx
0x14001ae3a  mov     rbx, [rsi+30h]
0x14001ae3e  test    rbx, rbx
0x14001ae41  jz      short loc_14001AEBC
0x14001ae43  mov     rbx, [rbx+18h]
0x14001ae47  test    rbx, rbx
0x14001ae4a  jz      short loc_14001AEBC
0x14001ae4c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ae53  cmp     rcx, rbp
0x14001ae56  jz      short loc_14001AE76
0x14001ae58  cmp     byte ptr [rcx+29h], 4
0x14001ae5c  jb      short loc_14001AE76
0x14001ae5e  mov     r9d, [rbx]
0x14001ae61  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x14001ae68  mov     rcx, [rcx+18h]
0x14001ae6c  mov     edx, 14h
0x14001ae71  call    WPP_SF_d
0x14001ae76  mov     r8d, [rsi+10h]
0x14001ae7a  mov     rdx, [rdi+18h]
0x14001ae7e  mov     ecx, [rbx]
0x14001ae80  call    DrSendMessageToSession
0x14001ae85  mov     ebx, eax
0x14001ae87  test    eax, eax
0x14001ae89  jnz     short loc_14001AEC1
0x14001ae8b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ae92  cmp     rcx, rbp
0x14001ae95  jz      short loc_14001AEB0
0x14001ae97  cmp     byte ptr [rcx+29h], 2
0x14001ae9b  jb      short loc_14001AEB0
0x14001ae9d  mov     rcx, [rcx+18h]
0x14001aea1  lea     edx, [rax+16h]
0x14001aea4  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x14001aeab  call    WPP_SF_
0x14001aeb0  mov     qword ptr [rdi+38h], 0
0x14001aeb8  xor     eax, eax
0x14001aeba  jmp     short loc_14001AEEA
0x14001aebc  mov     ebx, 0C0000010h
0x14001aec1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aec8  cmp     rcx, rbp
0x14001aecb  jz      short loc_14001AEE8
0x14001aecd  cmp     byte ptr [rcx+29h], 2
0x14001aed1  jb      short loc_14001AEE8
0x14001aed3  mov     rcx, [rcx+18h]
0x14001aed7  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x14001aede  mov     edx, 15h
0x14001aee3  call    WPP_SF_
0x14001aee8  mov     eax, ebx
0x14001aeea  xor     edx, edx; PriorityBoost
0x14001aeec  mov     [rdi+30h], eax
0x14001aeef  mov     rcx, rdi; Irp
0x14001aef2  call    cs:__imp_IofCompleteRequest
0x14001aef9  nop     dword ptr [rax+rax+00h]
0x14001aefe  mov     eax, ebx
0x14001af00  add     rsp, 38h
0x14001af04  pop     rdi
0x14001af05  pop     rsi
0x14001af06  pop     rbp
0x14001af07  pop     rbx
0x14001af08  retn
```
