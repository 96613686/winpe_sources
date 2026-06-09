# RxCompleteMdl

- ea: `0x140044360`
- end: `0x1400444a2`
- name: `RxCompleteMdl`
- size: `322`
- prototype: `NTSTATUS __stdcall(PRX_CONTEXT RxContext, PIRP Irp)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400027b0`
- `0x140015230`
- `0x140017280`
- `0x140044360`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14004440f`
- `ntoskrnl!KeBugCheckEx` at `0x14004440f`
- `ntoskrnl!CcMdlWriteComplete` at `0x140044427`
- `ntoskrnl!CcMdlWriteComplete` at `0x140044427`
- `ntoskrnl!CcMdlReadComplete` at `0x140044443`
- `ntoskrnl!CcMdlReadComplete` at `0x140044443`

## pseudocode

```c
NTSTATUS __stdcall RxCompleteMdl(PRX_CONTEXT RxContext, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  struct _FILE_OBJECT *FileObject; // rbp

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 10, &WPP_7e41285f5a80379d3de9a5c7558e4e33_Traceguids, RxContext, Irp);
  }
  if ( LOBYTE(RxContext->RealDevice) == 3 )
  {
    CcMdlReadComplete(FileObject, Irp->MdlAddress);
  }
  else
  {
    if ( LOBYTE(RxContext->RealDevice) != 4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, &WPP_7e41285f5a80379d3de9a5c7558e4e33_Traceguids);
      }
      KeBugCheckEx(0x27u, 0xCA55005D, LOBYTE(RxContext->RealDevice), 0, 0);
    }
    CcMdlWriteComplete(FileObject, &CurrentStackLocation->Parameters.Read.ByteOffset, Irp->MdlAddress);
    Irp->IoStatus.Status = 0;
  }
  Irp->MdlAddress = 0;
  RxCompleteRequestEx(RxContext, RxContext->CurrentIrp);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, &WPP_7e41285f5a80379d3de9a5c7558e4e33_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140044360  push    rbx
0x140044362  push    rbp
0x140044363  push    rsi
0x140044364  push    rdi
0x140044365  push    r15
0x140044367  sub     rsp, 30h
0x14004436b  mov     rsi, [rdx+0B8h]
0x140044372  mov     rbx, rdx
0x140044375  mov     rdi, rcx
0x140044378  mov     rbp, [rsi+30h]
0x14004437c  mov     rcx, cs:WPP_GLOBAL_Control
0x140044383  lea     r15, WPP_GLOBAL_Control
0x14004438a  cmp     rcx, r15
0x14004438d  jz      short loc_1400443B9
0x14004438f  mov     eax, [rcx+2Ch]
0x140044392  test    al, 10h
0x140044394  jz      short loc_1400443B9
0x140044396  cmp     byte ptr [rcx+29h], 4
0x14004439a  jb      short loc_1400443B9
0x14004439c  mov     rcx, [rcx+18h]
0x1400443a0  lea     r8, WPP_7e41285f5a80379d3de9a5c7558e4e33_Traceguids
0x1400443a7  mov     edx, 0Ah
0x1400443ac  mov     [rsp+58h+BugCheckParameter4], rbx
0x1400443b1  mov     r9, rdi
0x1400443b4  call    WPP_SF_qq
0x1400443b9  movzx   ecx, byte ptr [rdi+20h]
0x1400443bd  sub     ecx, 3
0x1400443c0  jz      short loc_14004443C
0x1400443c2  cmp     ecx, 1
0x1400443c5  jz      short loc_14004441C
0x1400443c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400443ce  cmp     rcx, r15
0x1400443d1  jz      short loc_1400443F5
0x1400443d3  mov     eax, [rcx+2Ch]
0x1400443d6  test    al, 1
0x1400443d8  jz      short loc_1400443F5
0x1400443da  cmp     byte ptr [rcx+29h], 1
0x1400443de  jb      short loc_1400443F5
0x1400443e0  mov     rcx, [rcx+18h]
0x1400443e4  lea     r8, WPP_7e41285f5a80379d3de9a5c7558e4e33_Traceguids
0x1400443eb  mov     edx, 0Bh
0x1400443f0  call    WPP_SF_
0x1400443f5  movzx   r8d, byte ptr [rdi+20h]; BugCheckParameter2
0x1400443fa  xor     r9d, r9d; BugCheckParameter3
0x1400443fd  mov     edx, 0CA55005Dh; BugCheckParameter1
0x140044402  mov     [rsp+58h+BugCheckParameter4], 0; BugCheckParameter4
0x14004440b  lea     ecx, [r9+27h]; BugCheckCode
0x14004440f  call    cs:__imp_KeBugCheckEx
0x14004441c  mov     r8, [rbx+8]; MdlChain
0x140044420  lea     rdx, [rsi+18h]; FileOffset
0x140044424  mov     rcx, rbp; FileObject
0x140044427  call    cs:__imp_CcMdlWriteComplete
0x14004442e  nop     dword ptr [rax+rax+00h]
0x140044433  mov     dword ptr [rbx+30h], 0
0x14004443a  jmp     short loc_14004444F
0x14004443c  mov     rdx, [rbx+8]; MdlChain
0x140044440  mov     rcx, rbp; FileObject
0x140044443  call    cs:__imp_CcMdlReadComplete
0x14004444a  nop     dword ptr [rax+rax+00h]
0x14004444f  mov     qword ptr [rbx+8], 0
0x140044457  xor     r8d, r8d
0x14004445a  mov     rdx, [rdi+28h]; Irp
0x14004445e  mov     rcx, rdi; RxContext
0x140044461  call    RxCompleteRequestEx
0x140044466  mov     rcx, cs:WPP_GLOBAL_Control
0x14004446d  cmp     rcx, r15
0x140044470  jz      short loc_140044494
0x140044472  mov     eax, [rcx+2Ch]
0x140044475  test    al, 10h
0x140044477  jz      short loc_140044494
0x140044479  cmp     byte ptr [rcx+29h], 4
0x14004447d  jb      short loc_140044494
0x14004447f  mov     rcx, [rcx+18h]
0x140044483  lea     r8, WPP_7e41285f5a80379d3de9a5c7558e4e33_Traceguids
0x14004448a  mov     edx, 0Ch
0x14004448f  call    WPP_SF_
0x140044494  xor     eax, eax
0x140044496  add     rsp, 30h
0x14004449a  pop     r15
0x14004449c  pop     rdi
0x14004449d  pop     rsi
0x14004449e  pop     rbp
0x14004449f  pop     rbx
0x1400444a0  retn
```
