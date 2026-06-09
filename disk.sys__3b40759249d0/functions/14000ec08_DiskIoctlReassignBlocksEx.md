# DiskIoctlReassignBlocksEx

- ea: `0x14000ec08`
- end: `0x14000ef92`
- name: `DiskIoctlReassignBlocksEx`
- size: `906`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400014a0`

## callees

- `0x140004078`
- `0x14000431c`
- `0x14000ec08`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000eee1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ef72`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eee1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ef72`
- `ntoskrnl!ExAllocatePool2` at `0x14000ed6a`
- `ntoskrnl!ExAllocatePool2` at `0x14000ed6a`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14000ee6e`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14000ee6e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ec2e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ec2e`
- `CLASSPNP!ClassSendSrbSynchronous` at `0x14000ef5f`
- `CLASSPNP!ClassSendSrbSynchronous` at `0x14000ef5f`

## pseudocode

```c
__int64 __fastcall DiskIoctlReassignBlocksEx(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _QWORD *DeviceExtension; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  struct _IRP *MasterIrp; // rbx
  unsigned int Options; // ecx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  int Size; // eax
  ULONG v12; // r12d
  unsigned int v13; // ecx
  unsigned int v14; // r13d
  __int64 Pool2; // rdi
  __int64 v16; // r8
  __int64 v17; // rax
  __int16 IoPriorityHint; // ax
  _BYTE *v19; // rcx
  char v20; // al
  unsigned int v21; // ebx

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
      86,
      WPP_0d021951613e35be7880fae860fb7f50_Traceguids,
      DeviceObject,
      Irp);
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options < 0xC )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return 3221225476LL;
    }
    v10 = 87;
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
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return 3221225485LL;
  }
  v12 = 8 * Size + 4;
  if ( Options < v12 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return 3221225476LL;
    }
    v10 = 89;
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
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 90, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return 3221225626LL;
  }
  LODWORD(v16) = MasterIrp->Size;
  MasterIrp->Type = 0;
  MasterIrp->Size = __ROR2__(8 * v16, 8);
  while ( (_DWORD)v16 )
  {
    v16 = (unsigned int)(v16 - 1);
    v17 = *(_QWORD *)(&MasterIrp->Size + 4 * v16 + 1);
    *((_BYTE *)&MasterIrp->MdlAddress + 8 * v16 + 3) = v17;
    *((_BYTE *)&MasterIrp->MdlAddress + 8 * v16 + 2) = BYTE1(v17);
    *((_BYTE *)&MasterIrp->MdlAddress + 8 * v16 + 1) = BYTE2(v17);
    *((_BYTE *)&MasterIrp->MdlAddress + 8 * v16) = BYTE3(v17);
    *((_BYTE *)&MasterIrp->Size + 8 * v16 + 5) = BYTE4(v17);
    *((_BYTE *)&MasterIrp->Size + 8 * v16 + 4) = BYTE5(v17);
    *((_BYTE *)&MasterIrp->Size + 8 * v16 + 2) = HIBYTE(v17);
    *((_BYTE *)&MasterIrp->Size + 8 * v16 + 3) = BYTE6(v17);
  }
  if ( *(_BYTE *)(DeviceExtension[66] + 30LL) != 1 )
  {
    *(_WORD *)Pool2 = 88;
    v19 = (_BYTE *)(Pool2 + 72);
    *(_BYTE *)(Pool2 + 2) = 0;
    *(_BYTE *)(Pool2 + 10) = 6;
    *(_DWORD *)(Pool2 + 20) = *((_DWORD *)DeviceExtension + 146);
    goto LABEL_45;
  }
  *(_WORD *)Pool2 = 8;
  *(_BYTE *)(Pool2 + 2) = 40;
  *(_DWORD *)(Pool2 + 8) = 1397899864;
  *(_DWORD *)(Pool2 + 12) = 1;
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
    v20 = v19[1] & 0xE3;
    *v19 = 7;
    v19[1] = v20 | 2;
    v21 = ClassSendSrbSynchronous(DeviceObject, (PSCSI_REQUEST_BLOCK)Pool2, MasterIrp, v12, 1u);
    ExFreePoolWithTag((PVOID)Pool2, 0);
    return v21;
  }
  ExFreePoolWithTag((PVOID)Pool2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
  }
  return 3221225701LL;
}

```

## disassembly

```asm
0x14000ec08  push    rbx
0x14000ec0a  push    rbp
0x14000ec0b  push    rsi
0x14000ec0c  push    rdi
0x14000ec0d  push    r12
0x14000ec0f  push    r13
0x14000ec11  push    r14
0x14000ec13  push    r15
0x14000ec15  sub     rsp, 38h
0x14000ec19  mov     r14, [rcx+40h]
0x14000ec1d  mov     rbp, rdx
0x14000ec20  mov     rdi, [rdx+0B8h]
0x14000ec27  mov     r15, rcx
0x14000ec2a  mov     rbx, [rdx+18h]
0x14000ec2e  call    cs:__imp_KeGetCurrentIrql
0x14000ec35  nop     dword ptr [rax+rax+00h]
0x14000ec3a  cmp     al, 2
0x14000ec3c  jb      short loc_14000EC48
0x14000ec3e  mov     eax, 0C0000148h
0x14000ec43  jmp     loc_14000EF80
0x14000ec48  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec4f  lea     rdx, WPP_GLOBAL_Control
0x14000ec56  cmp     rcx, rdx
0x14000ec59  jz      short loc_14000EC8C
0x14000ec5b  mov     eax, [rcx+2Ch]
0x14000ec5e  test    al, 10h
0x14000ec60  jz      short loc_14000EC8C
0x14000ec62  cmp     byte ptr [rcx+29h], 4
0x14000ec66  jb      short loc_14000EC8C
0x14000ec68  mov     rcx, [rcx+18h]
0x14000ec6c  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000ec73  mov     edx, 56h ; 'V'
0x14000ec78  mov     qword ptr [rsp+78h+WriteToDevice], rbp
0x14000ec7d  mov     r9, r15
0x14000ec80  call    WPP_SF_qq
0x14000ec85  lea     rdx, WPP_GLOBAL_Control
0x14000ec8c  mov     ecx, [rdi+10h]
0x14000ec8f  cmp     ecx, 0Ch
0x14000ec92  jnb     short loc_14000ECC0
0x14000ec94  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec9b  cmp     rcx, rdx
0x14000ec9e  jz      loc_14000ED3C
0x14000eca4  mov     eax, [rcx+2Ch]
0x14000eca7  test    al, 10h
0x14000eca9  jz      loc_14000ED3C
0x14000ecaf  cmp     byte ptr [rcx+29h], 2
0x14000ecb3  jb      loc_14000ED3C
0x14000ecb9  mov     edx, 57h ; 'W'
0x14000ecbe  jmp     short loc_14000ED2C
0x14000ecc0  movzx   eax, word ptr [rbx+2]
0x14000ecc4  test    ax, ax
0x14000ecc7  jnz     short loc_14000ED01
0x14000ecc9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ecd0  cmp     rcx, rdx
0x14000ecd3  jz      short loc_14000ECF7
0x14000ecd5  mov     eax, [rcx+2Ch]
0x14000ecd8  test    al, 10h
0x14000ecda  jz      short loc_14000ECF7
0x14000ecdc  cmp     byte ptr [rcx+29h], 2
0x14000ece0  jb      short loc_14000ECF7
0x14000ece2  mov     rcx, [rcx+18h]
0x14000ece6  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000eced  mov     edx, 58h ; 'X'
0x14000ecf2  call    WPP_SF_
0x14000ecf7  mov     eax, 0C000000Dh
0x14000ecfc  jmp     loc_14000EF80
0x14000ed01  lea     r12d, ds:4[rax*8]
0x14000ed09  cmp     ecx, r12d
0x14000ed0c  jnb     short loc_14000ED46
0x14000ed0e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed15  cmp     rcx, rdx
0x14000ed18  jz      short loc_14000ED3C
0x14000ed1a  mov     eax, [rcx+2Ch]
0x14000ed1d  test    al, 10h
0x14000ed1f  jz      short loc_14000ED3C
0x14000ed21  cmp     byte ptr [rcx+29h], 2
0x14000ed25  jb      short loc_14000ED3C
0x14000ed27  mov     edx, 59h ; 'Y'
0x14000ed2c  mov     rcx, [rcx+18h]
0x14000ed30  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000ed37  call    WPP_SF_
0x14000ed3c  mov     eax, 0C0000004h
0x14000ed41  jmp     loc_14000EF80
0x14000ed46  mov     rax, [r14+210h]
0x14000ed4d  mov     ecx, 0B8h
0x14000ed52  mov     r8d, 53446353h
0x14000ed58  cmp     byte ptr [rax+1Eh], 1
0x14000ed5c  lea     esi, [rcx-60h]
0x14000ed5f  cmovnz  ecx, esi
0x14000ed62  mov     r13d, ecx
0x14000ed65  mov     edx, ecx
0x14000ed67  lea     ecx, [rsi-18h]
0x14000ed6a  call    cs:__imp_ExAllocatePool2
0x14000ed71  nop     dword ptr [rax+rax+00h]
0x14000ed76  xor     r9d, r9d
0x14000ed79  mov     rdi, rax
0x14000ed7c  test    rax, rax
0x14000ed7f  jnz     short loc_14000EDBE
0x14000ed81  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed88  lea     rax, WPP_GLOBAL_Control
0x14000ed8f  cmp     rcx, rax
0x14000ed92  jz      short loc_14000EDB4
0x14000ed94  mov     eax, [rcx+2Ch]
0x14000ed97  test    al, 10h
0x14000ed99  jz      short loc_14000EDB4
0x14000ed9b  cmp     byte ptr [rcx+29h], 2
0x14000ed9f  jb      short loc_14000EDB4
0x14000eda1  mov     rcx, [rcx+18h]
0x14000eda5  lea     edx, [rsi+2]
0x14000eda8  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000edaf  call    WPP_SF_
0x14000edb4  mov     eax, 0C000009Ah
0x14000edb9  jmp     loc_14000EF80
0x14000edbe  movzx   r8d, word ptr [rbx+2]
0x14000edc3  movzx   eax, r8w
0x14000edc7  mov     [rbx], r9w
0x14000edcb  shl     ax, 3
0x14000edcf  ror     ax, 8
0x14000edd3  mov     [rbx+2], ax
0x14000edd7  jmp     short loc_14000EE37
0x14000edd9  dec     r8d
0x14000eddc  mov     rax, [rbx+r8*8+4]
0x14000ede1  mov     rcx, rax
0x14000ede4  mov     [rbx+r8*8+0Bh], al
0x14000ede9  shr     rcx, 8
0x14000eded  mov     [rbx+r8*8+0Ah], cl
0x14000edf2  mov     rcx, rax
0x14000edf5  shr     rcx, 10h
0x14000edf9  mov     [rbx+r8*8+9], cl
0x14000edfe  mov     rcx, rax
0x14000ee01  shr     rcx, 18h
0x14000ee05  mov     [rbx+r8*8+8], cl
0x14000ee0a  mov     rcx, rax
0x14000ee0d  shr     rcx, 20h
0x14000ee11  mov     [rbx+r8*8+7], cl
0x14000ee16  mov     rcx, rax
0x14000ee19  shr     rcx, 28h
0x14000ee1d  mov     [rbx+r8*8+6], cl
0x14000ee22  mov     rcx, rax
0x14000ee25  shr     rcx, 30h
0x14000ee29  shr     rax, 38h
0x14000ee2d  mov     [rbx+r8*8+4], al
0x14000ee32  mov     [rbx+r8*8+5], cl
0x14000ee37  test    r8d, r8d
0x14000ee3a  jnz     short loc_14000EDD9
0x14000ee3c  mov     rax, [r14+210h]
0x14000ee43  lea     edx, [r8+1]
0x14000ee47  cmp     [rax+1Eh], dl
0x14000ee4a  jnz     loc_14000EF29
0x14000ee50  mov     rcx, rbp; Irp
0x14000ee53  mov     word ptr [rdi], 8
0x14000ee58  mov     byte ptr [rdi+2], 28h ; '('
0x14000ee5c  mov     dword ptr [rdi+8], 53524258h
0x14000ee63  mov     [rdi+0Ch], edx
0x14000ee66  mov     [rdi+10h], r13d
0x14000ee6a  mov     [rdi+14h], r9d
0x14000ee6e  call    cs:__imp_IoGetIoPriorityHint
0x14000ee75  nop     dword ptr [rax+rax+00h]
0x14000ee7a  mov     dword ptr [rdi+34h], 80h
0x14000ee81  mov     edx, 1
0x14000ee86  mov     [rdi+38h], edx
0x14000ee89  mov     [rdi+24h], ax
0x14000ee8d  mov     eax, [r14+248h]
0x14000ee94  mov     [rdi+28h], eax
0x14000ee97  mov     [rdi+80h], dx
0x14000ee9e  mov     dword ptr [rdi+84h], 4
0x14000eea8  mov     dword ptr [rdi+78h], 90h
0x14000eeaf  cmp     dword ptr [rdi+10h], 0B8h
0x14000eeb6  jb      short loc_14000EEDC
0x14000eeb8  mov     dword ptr [rdi+90h], 40h ; '@'
0x14000eec2  lea     rcx, [rdi+0A8h]
0x14000eec9  mov     dword ptr [rdi+94h], 20h ; ' '
0x14000eed3  mov     byte ptr [rdi+9Ah], 6
0x14000eeda  jmp     short loc_14000EF42
0x14000eedc  xor     edx, edx; Tag
0x14000eede  mov     rcx, rdi; P
0x14000eee1  call    cs:__imp_ExFreePoolWithTag
0x14000eee8  nop     dword ptr [rax+rax+00h]
0x14000eeed  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eef4  lea     rax, WPP_GLOBAL_Control
0x14000eefb  cmp     rcx, rax
0x14000eefe  jz      short loc_14000EF22
0x14000ef00  mov     eax, [rcx+2Ch]
0x14000ef03  test    al, 10h
0x14000ef05  jz      short loc_14000EF22
0x14000ef07  cmp     byte ptr [rcx+29h], 2
0x14000ef0b  jb      short loc_14000EF22
0x14000ef0d  mov     rcx, [rcx+18h]
0x14000ef11  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000ef18  mov     edx, 5Bh ; '['
0x14000ef1d  call    WPP_SF_
0x14000ef22  mov     eax, 0C00000E5h
0x14000ef27  jmp     short loc_14000EF80
0x14000ef29  mov     [rdi], si
0x14000ef2c  lea     rcx, [rdi+48h]
0x14000ef30  mov     [rdi+2], r9b
0x14000ef34  mov     byte ptr [rdi+0Ah], 6
0x14000ef38  mov     eax, [r14+248h]
0x14000ef3f  mov     [rdi+14h], eax
0x14000ef42  mov     al, [rcx+1]
0x14000ef45  mov     r9d, r12d; BufferLength
0x14000ef48  and     al, 0E3h
0x14000ef4a  mov     byte ptr [rcx], 7
0x14000ef4d  or      al, 2
0x14000ef4f  mov     [rsp+78h+WriteToDevice], dl; WriteToDevice
0x14000ef53  mov     [rcx+1], al
0x14000ef56  mov     r8, rbx; BufferAddress
0x14000ef59  mov     rcx, r15; DeviceObject
0x14000ef5c  mov     rdx, rdi; Srb
0x14000ef5f  call    cs:__imp_ClassSendSrbSynchronous
0x14000ef66  nop     dword ptr [rax+rax+00h]
0x14000ef6b  xor     edx, edx; Tag
0x14000ef6d  mov     rcx, rdi; P
0x14000ef70  mov     ebx, eax
0x14000ef72  call    cs:__imp_ExFreePoolWithTag
0x14000ef79  nop     dword ptr [rax+rax+00h]
0x14000ef7e  mov     eax, ebx
0x14000ef80  add     rsp, 38h
0x14000ef84  pop     r15
0x14000ef86  pop     r14
0x14000ef88  pop     r13
0x14000ef8a  pop     r12
0x14000ef8c  pop     rdi
0x14000ef8d  pop     rsi
0x14000ef8e  pop     rbp
0x14000ef8f  pop     rbx
0x14000ef90  retn
```
