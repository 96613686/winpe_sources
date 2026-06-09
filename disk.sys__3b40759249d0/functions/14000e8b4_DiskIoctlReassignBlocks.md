# DiskIoctlReassignBlocks

- ea: `0x14000e8b4`
- end: `0x14000ebff`
- name: `DiskIoctlReassignBlocks`
- size: `843`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400014a0`

## callees

- `0x140004078`
- `0x14000431c`
- `0x14000e8b4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000eb58`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ebe1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eb58`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ebe1`
- `ntoskrnl!ExAllocatePool2` at `0x14000ea16`
- `ntoskrnl!ExAllocatePool2` at `0x14000ea16`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14000eae5`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14000eae5`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000e8d8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000e8d8`
- `CLASSPNP!ClassSendSrbSynchronous` at `0x14000ebce`
- `CLASSPNP!ClassSendSrbSynchronous` at `0x14000ebce`

## pseudocode

```c
__int64 __fastcall DiskIoctlReassignBlocks(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _QWORD *DeviceExtension; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  struct _IRP *MasterIrp; // rbx
  unsigned int Options; // ecx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  int Size; // eax
  ULONG v12; // r15d
  unsigned int v13; // ecx
  unsigned int v14; // r12d
  __int64 Pool2; // rdi
  __int64 v16; // r8
  int v17; // ecx
  __int16 IoPriorityHint; // ax
  _BYTE *v19; // rax
  unsigned int v20; // ebx

  DeviceExtension = DeviceObject->DeviceExtension;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( KeGetCurrentIrql() >= 2u )
    return 3221225800LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      80,
      WPP_0d021951613e35be7880fae860fb7f50_Traceguids,
      DeviceObject,
      Irp);
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options < 8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return 3221225476LL;
    }
    v10 = 81;
LABEL_23:
    WPP_SF_(v9->AttachedDevice, v10, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    return 3221225476LL;
  }
  Size = MasterIrp->Size;
  if ( !(_WORD)Size )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return 3221225485LL;
  }
  v12 = 4 * Size + 4;
  if ( Options < v12 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return 3221225476LL;
    }
    v10 = 83;
    goto LABEL_23;
  }
  v13 = 184;
  if ( *(_BYTE *)(DeviceExtension[66] + 30LL) != 1 )
    v13 = 88;
  v14 = v13;
  Pool2 = ExAllocatePool2(64, v13, 1396990803);
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return 3221225626LL;
  }
  LODWORD(v16) = MasterIrp->Size;
  MasterIrp->Type = 0;
  MasterIrp->Size = __ROR2__(4 * v16, 8);
  while ( (_DWORD)v16 )
  {
    v16 = (unsigned int)(v16 - 1);
    v17 = *(_DWORD *)(&MasterIrp->Size + 2 * v16 + 1);
    *((_BYTE *)&MasterIrp->Size + 4 * v16 + 4) = BYTE1(v17);
    *((_BYTE *)&MasterIrp->Size + 4 * v16 + 5) = v17;
    *((_BYTE *)&MasterIrp->Size + 4 * v16 + 2) = HIBYTE(v17);
    *((_BYTE *)&MasterIrp->Size + 4 * v16 + 3) = BYTE2(v17);
  }
  if ( *(_BYTE *)(DeviceExtension[66] + 30LL) != 1 )
  {
    *(_WORD *)Pool2 = 88;
    *(_BYTE *)(Pool2 + 2) = 0;
    *(_BYTE *)(Pool2 + 10) = 6;
    *(_DWORD *)(Pool2 + 20) = *((_DWORD *)DeviceExtension + 146);
    v19 = (_BYTE *)(Pool2 + 72);
    goto LABEL_45;
  }
  *(_DWORD *)(Pool2 + 12) = 1;
  *(_WORD *)Pool2 = 8;
  *(_BYTE *)(Pool2 + 2) = 40;
  *(_DWORD *)(Pool2 + 8) = 1397899864;
  *(_DWORD *)(Pool2 + 16) = v14;
  *(_DWORD *)(Pool2 + 20) = 0;
  IoPriorityHint = IoGetIoPriorityHint(Irp);
  *(_DWORD *)(Pool2 + 52) = 128;
  *(_DWORD *)(Pool2 + 56) = 1;
  *(_WORD *)(Pool2 + 36) = IoPriorityHint;
  *(_DWORD *)(Pool2 + 40) = *((_DWORD *)DeviceExtension + 146);
  *(_WORD *)(Pool2 + 128) = 1;
  *(_DWORD *)(Pool2 + 132) = 4;
  *(_DWORD *)(Pool2 + 120) = 144;
  if ( *(_DWORD *)(Pool2 + 16) >= 0xB8u )
  {
    *(_DWORD *)(Pool2 + 144) = 64;
    v19 = (_BYTE *)(Pool2 + 168);
    *(_DWORD *)(Pool2 + 148) = 32;
    *(_BYTE *)(Pool2 + 154) = 6;
LABEL_45:
    *v19 = 7;
    v20 = ClassSendSrbSynchronous(DeviceObject, (PSCSI_REQUEST_BLOCK)Pool2, MasterIrp, v12, 1u);
    ExFreePoolWithTag((PVOID)Pool2, 0);
    return v20;
  }
  ExFreePoolWithTag((PVOID)Pool2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
  }
  return 3221225701LL;
}

```

## disassembly

```asm
0x14000e8b4  push    rbx
0x14000e8b6  push    rbp
0x14000e8b7  push    rsi
0x14000e8b8  push    rdi
0x14000e8b9  push    r12
0x14000e8bb  push    r14
0x14000e8bd  push    r15
0x14000e8bf  sub     rsp, 30h
0x14000e8c3  mov     r14, [rcx+40h]
0x14000e8c7  mov     rsi, rdx
0x14000e8ca  mov     rdi, [rdx+0B8h]
0x14000e8d1  mov     rbp, rcx
0x14000e8d4  mov     rbx, [rdx+18h]
0x14000e8d8  call    cs:__imp_KeGetCurrentIrql
0x14000e8df  nop     dword ptr [rax+rax+00h]
0x14000e8e4  cmp     al, 2
0x14000e8e6  jb      short loc_14000E8F2
0x14000e8e8  mov     eax, 0C0000148h
0x14000e8ed  jmp     loc_14000EBEF
0x14000e8f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e8f9  lea     rdx, WPP_GLOBAL_Control
0x14000e900  cmp     rcx, rdx
0x14000e903  jz      short loc_14000E936
0x14000e905  mov     eax, [rcx+2Ch]
0x14000e908  test    al, 10h
0x14000e90a  jz      short loc_14000E936
0x14000e90c  cmp     byte ptr [rcx+29h], 4
0x14000e910  jb      short loc_14000E936
0x14000e912  mov     rcx, [rcx+18h]
0x14000e916  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000e91d  mov     edx, 50h ; 'P'
0x14000e922  mov     qword ptr [rsp+68h+WriteToDevice], rsi
0x14000e927  mov     r9, rbp
0x14000e92a  call    WPP_SF_qq
0x14000e92f  lea     rdx, WPP_GLOBAL_Control
0x14000e936  mov     ecx, [rdi+10h]
0x14000e939  cmp     ecx, 8
0x14000e93c  jnb     short loc_14000E96A
0x14000e93e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e945  cmp     rcx, rdx
0x14000e948  jz      loc_14000E9E6
0x14000e94e  mov     eax, [rcx+2Ch]
0x14000e951  test    al, 10h
0x14000e953  jz      loc_14000E9E6
0x14000e959  cmp     byte ptr [rcx+29h], 2
0x14000e95d  jb      loc_14000E9E6
0x14000e963  mov     edx, 51h ; 'Q'
0x14000e968  jmp     short loc_14000E9D6
0x14000e96a  movzx   eax, word ptr [rbx+2]
0x14000e96e  test    ax, ax
0x14000e971  jnz     short loc_14000E9AB
0x14000e973  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e97a  cmp     rcx, rdx
0x14000e97d  jz      short loc_14000E9A1
0x14000e97f  mov     eax, [rcx+2Ch]
0x14000e982  test    al, 10h
0x14000e984  jz      short loc_14000E9A1
0x14000e986  cmp     byte ptr [rcx+29h], 2
0x14000e98a  jb      short loc_14000E9A1
0x14000e98c  mov     rcx, [rcx+18h]
0x14000e990  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000e997  mov     edx, 52h ; 'R'
0x14000e99c  call    WPP_SF_
0x14000e9a1  mov     eax, 0C000000Dh
0x14000e9a6  jmp     loc_14000EBEF
0x14000e9ab  lea     r15d, ds:4[rax*4]
0x14000e9b3  cmp     ecx, r15d
0x14000e9b6  jnb     short loc_14000E9F0
0x14000e9b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e9bf  cmp     rcx, rdx
0x14000e9c2  jz      short loc_14000E9E6
0x14000e9c4  mov     eax, [rcx+2Ch]
0x14000e9c7  test    al, 10h
0x14000e9c9  jz      short loc_14000E9E6
0x14000e9cb  cmp     byte ptr [rcx+29h], 2
0x14000e9cf  jb      short loc_14000E9E6
0x14000e9d1  mov     edx, 53h ; 'S'
0x14000e9d6  mov     rcx, [rcx+18h]
0x14000e9da  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000e9e1  call    WPP_SF_
0x14000e9e6  mov     eax, 0C0000004h
0x14000e9eb  jmp     loc_14000EBEF
0x14000e9f0  mov     rax, [r14+210h]
0x14000e9f7  mov     ecx, 0B8h
0x14000e9fc  mov     r8d, 53446353h
0x14000ea02  cmp     byte ptr [rax+1Eh], 1
0x14000ea06  lea     edx, [rcx-60h]
0x14000ea09  cmovnz  ecx, edx
0x14000ea0c  mov     r12d, ecx
0x14000ea0f  mov     edx, ecx
0x14000ea11  mov     ecx, 40h ; '@'
0x14000ea16  call    cs:__imp_ExAllocatePool2
0x14000ea1d  nop     dword ptr [rax+rax+00h]
0x14000ea22  xor     r9d, r9d
0x14000ea25  mov     rdi, rax
0x14000ea28  test    rax, rax
0x14000ea2b  jnz     short loc_14000EA6A
0x14000ea2d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea34  lea     rax, WPP_GLOBAL_Control
0x14000ea3b  cmp     rcx, rax
0x14000ea3e  jz      short loc_14000EA60
0x14000ea40  mov     eax, [rcx+2Ch]
0x14000ea43  test    al, 10h
0x14000ea45  jz      short loc_14000EA60
0x14000ea47  cmp     byte ptr [rcx+29h], 2
0x14000ea4b  jb      short loc_14000EA60
0x14000ea4d  mov     rcx, [rcx+18h]
0x14000ea51  lea     edx, [rdi+54h]
0x14000ea54  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000ea5b  call    WPP_SF_
0x14000ea60  mov     eax, 0C000009Ah
0x14000ea65  jmp     loc_14000EBEF
0x14000ea6a  movzx   r8d, word ptr [rbx+2]
0x14000ea6f  movzx   eax, r8w
0x14000ea73  mov     [rbx], r9w
0x14000ea77  shl     ax, 2
0x14000ea7b  ror     ax, 8
0x14000ea7f  mov     [rbx+2], ax
0x14000ea83  jmp     short loc_14000EAAE
0x14000ea85  dec     r8d
0x14000ea88  mov     ecx, [rbx+r8*4+4]
0x14000ea8d  mov     eax, ecx
0x14000ea8f  shr     eax, 8
0x14000ea92  mov     [rbx+r8*4+6], al
0x14000ea97  mov     eax, ecx
0x14000ea99  shr     eax, 10h
0x14000ea9c  mov     [rbx+r8*4+7], cl
0x14000eaa1  shr     ecx, 18h
0x14000eaa4  mov     [rbx+r8*4+4], cl
0x14000eaa9  mov     [rbx+r8*4+5], al
0x14000eaae  test    r8d, r8d
0x14000eab1  jnz     short loc_14000EA85
0x14000eab3  mov     rax, [r14+210h]
0x14000eaba  lea     ecx, [r8+1]
0x14000eabe  cmp     [rax+1Eh], cl
0x14000eac1  jnz     loc_14000EBA0
0x14000eac7  mov     [rdi+0Ch], ecx
0x14000eaca  mov     rcx, rsi; Irp
0x14000eacd  mov     word ptr [rdi], 8
0x14000ead2  mov     byte ptr [rdi+2], 28h ; '('
0x14000ead6  mov     dword ptr [rdi+8], 53524258h
0x14000eadd  mov     [rdi+10h], r12d
0x14000eae1  mov     [rdi+14h], r9d
0x14000eae5  call    cs:__imp_IoGetIoPriorityHint
0x14000eaec  nop     dword ptr [rax+rax+00h]
0x14000eaf1  mov     dword ptr [rdi+34h], 80h
0x14000eaf8  mov     ecx, 1
0x14000eafd  mov     [rdi+38h], ecx
0x14000eb00  mov     [rdi+24h], ax
0x14000eb04  mov     eax, [r14+248h]
0x14000eb0b  mov     [rdi+28h], eax
0x14000eb0e  mov     [rdi+80h], cx
0x14000eb15  mov     dword ptr [rdi+84h], 4
0x14000eb1f  mov     dword ptr [rdi+78h], 90h
0x14000eb26  cmp     dword ptr [rdi+10h], 0B8h
0x14000eb2d  jb      short loc_14000EB53
0x14000eb2f  mov     dword ptr [rdi+90h], 40h ; '@'
0x14000eb39  lea     rax, [rdi+0A8h]
0x14000eb40  mov     dword ptr [rdi+94h], 20h ; ' '
0x14000eb4a  mov     byte ptr [rdi+9Ah], 6
0x14000eb51  jmp     short loc_14000EBBB
0x14000eb53  xor     edx, edx; Tag
0x14000eb55  mov     rcx, rdi; P
0x14000eb58  call    cs:__imp_ExFreePoolWithTag
0x14000eb5f  nop     dword ptr [rax+rax+00h]
0x14000eb64  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eb6b  lea     rax, WPP_GLOBAL_Control
0x14000eb72  cmp     rcx, rax
0x14000eb75  jz      short loc_14000EB99
0x14000eb77  mov     eax, [rcx+2Ch]
0x14000eb7a  test    al, 10h
0x14000eb7c  jz      short loc_14000EB99
0x14000eb7e  cmp     byte ptr [rcx+29h], 2
0x14000eb82  jb      short loc_14000EB99
0x14000eb84  mov     rcx, [rcx+18h]
0x14000eb88  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000eb8f  mov     edx, 55h ; 'U'
0x14000eb94  call    WPP_SF_
0x14000eb99  mov     eax, 0C00000E5h
0x14000eb9e  jmp     short loc_14000EBEF
0x14000eba0  mov     word ptr [rdi], 58h ; 'X'
0x14000eba5  mov     [rdi+2], r9b
0x14000eba9  mov     byte ptr [rdi+0Ah], 6
0x14000ebad  mov     eax, [r14+248h]
0x14000ebb4  mov     [rdi+14h], eax
0x14000ebb7  lea     rax, [rdi+48h]
0x14000ebbb  mov     [rsp+68h+WriteToDevice], cl; WriteToDevice
0x14000ebbf  mov     r9d, r15d; BufferLength
0x14000ebc2  mov     rcx, rbp; DeviceObject
0x14000ebc5  mov     byte ptr [rax], 7
0x14000ebc8  mov     r8, rbx; BufferAddress
0x14000ebcb  mov     rdx, rdi; Srb
0x14000ebce  call    cs:__imp_ClassSendSrbSynchronous
0x14000ebd5  nop     dword ptr [rax+rax+00h]
0x14000ebda  xor     edx, edx; Tag
0x14000ebdc  mov     rcx, rdi; P
0x14000ebdf  mov     ebx, eax
0x14000ebe1  call    cs:__imp_ExFreePoolWithTag
0x14000ebe8  nop     dword ptr [rax+rax+00h]
0x14000ebed  mov     eax, ebx
0x14000ebef  add     rsp, 30h
0x14000ebf3  pop     r15
0x14000ebf5  pop     r14
0x14000ebf7  pop     r12
0x14000ebf9  pop     rdi
0x14000ebfa  pop     rsi
0x14000ebfb  pop     rbp
0x14000ebfc  pop     rbx
0x14000ebfd  retn
```
