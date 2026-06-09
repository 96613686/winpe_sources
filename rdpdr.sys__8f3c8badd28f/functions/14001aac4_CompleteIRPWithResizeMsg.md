# CompleteIRPWithResizeMsg

- ea: `0x14001aac4`
- end: `0x14001ab8d`
- name: `CompleteIRPWithResizeMsg`
- size: `201`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001f10`
- `0x1400027b0`

## callees

- `0x14000324c`
- `0x14001aac4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001ab47`
- `ntoskrnl!IofCompleteRequest` at `0x14001ab47`

## pseudocode

```c
__int64 __fastcall CompleteIRPWithResizeMsg(PIRP Irp, int a2)
{
  unsigned int v3; // edi
  ULONG_PTR v4; // rax
  struct _IRP *MasterIrp; // rax

  if ( Irp->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length >= 0xC )
  {
    MasterIrp = Irp->AssociatedIrp.MasterIrp;
    *(_DWORD *)&MasterIrp->Type = 2;
    *(_DWORD *)(&MasterIrp->Size + 1) = 4;
    LODWORD(Irp->AssociatedIrp.MasterIrp->MdlAddress) = a2;
    v3 = 0;
    v4 = 12;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids);
    v3 = -1073741306;
    v4 = 0;
  }
  Irp->IoStatus.Status = v3;
  Irp->IoStatus.Information = v4;
  IofCompleteRequest(Irp, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x14001aac4  mov     [rsp+arg_0], rbx
0x14001aac9  mov     [rsp+arg_8], rsi
0x14001aace  push    rdi
0x14001aacf  sub     rsp, 20h
0x14001aad3  mov     rax, [rcx+0B8h]
0x14001aada  lea     rsi, WPP_GLOBAL_Control
0x14001aae1  mov     rbx, rcx
0x14001aae4  cmp     dword ptr [rax+8], 0Ch
0x14001aae8  jnb     short loc_14001AB1A
0x14001aaea  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aaf1  cmp     rcx, rsi
0x14001aaf4  jz      short loc_14001AB11
0x14001aaf6  cmp     byte ptr [rcx+29h], 4
0x14001aafa  jb      short loc_14001AB11
0x14001aafc  mov     rcx, [rcx+18h]
0x14001ab00  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x14001ab07  mov     edx, 1Fh
0x14001ab0c  call    WPP_SF_
0x14001ab11  mov     edi, 0C0000206h
0x14001ab16  xor     eax, eax
0x14001ab18  jmp     short loc_14001AB3B
0x14001ab1a  mov     rax, [rcx+18h]
0x14001ab1e  mov     dword ptr [rax], 2
0x14001ab24  mov     dword ptr [rax+4], 4
0x14001ab2b  mov     rax, [rcx+18h]
0x14001ab2f  mov     [rax+8], edx
0x14001ab32  xor     eax, eax
0x14001ab34  mov     edi, eax
0x14001ab36  mov     eax, 0Ch
0x14001ab3b  xor     edx, edx; PriorityBoost
0x14001ab3d  mov     [rbx+30h], edi
0x14001ab40  mov     rcx, rbx; Irp
0x14001ab43  mov     [rbx+38h], rax
0x14001ab47  call    cs:__imp_IofCompleteRequest
0x14001ab4e  nop     dword ptr [rax+rax+00h]
0x14001ab53  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ab5a  cmp     rcx, rsi
0x14001ab5d  jz      short loc_14001AB7A
0x14001ab5f  cmp     byte ptr [rcx+29h], 4
0x14001ab63  jb      short loc_14001AB7A
0x14001ab65  mov     rcx, [rcx+18h]
0x14001ab69  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x14001ab70  mov     edx, 20h ; ' '
0x14001ab75  call    WPP_SF_
0x14001ab7a  mov     rbx, [rsp+28h+arg_0]
0x14001ab7f  mov     eax, edi
0x14001ab81  mov     rsi, [rsp+28h+arg_8]
0x14001ab86  add     rsp, 20h
0x14001ab8a  pop     rdi
0x14001ab8b  retn
```
