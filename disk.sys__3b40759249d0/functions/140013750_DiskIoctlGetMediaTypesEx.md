# DiskIoctlGetMediaTypesEx

- ea: `0x140013750`
- end: `0x140013b3e`
- name: `DiskIoctlGetMediaTypesEx`
- size: `1006`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400014a0`

## callees

- `0x140004078`
- `0x14000431c`
- `0x140013750`
- `0x140013b50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400138a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400139fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a92`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400139fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a92`
- `ntoskrnl!ExAllocatePool2` at `0x1400137db`
- `ntoskrnl!ExAllocatePool2` at `0x140013850`
- `ntoskrnl!ExAllocatePool2` at `0x1400137db`
- `ntoskrnl!ExAllocatePool2` at `0x140013850`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140013977`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140013977`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001376d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001376d`
- `CLASSPNP!ClassSendSrbSynchronous` at `0x140013831`
- `CLASSPNP!ClassSendSrbSynchronous` at `0x140013831`
- `CLASSPNP!ClassModeSense` at `0x140013877`
- `CLASSPNP!ClassModeSense` at `0x140013877`

## pseudocode

```c
__int64 __fastcall DiskIoctlGetMediaTypesEx(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _QWORD *DeviceExtension; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned int v6; // ecx
  unsigned int v7; // r14d
  __int64 Pool2; // rbx
  _BYTE *v9; // rcx
  NTSTATUS v10; // r14d
  CHAR *v11; // rax
  unsigned __int8 *v12; // rdi
  int v13; // r9d
  unsigned int v14; // esi
  char v16; // r14

  DeviceExtension = DeviceObject->DeviceExtension;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( KeGetCurrentIrql() >= 2u )
    return 3221225800LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      63,
      WPP_0d021951613e35be7880fae860fb7f50_Traceguids,
      DeviceObject,
      Irp);
  }
  if ( CurrentStackLocation->Parameters.Read.Length < 0x28 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return 3221225507LL;
  }
  else
  {
    v6 = 184;
    if ( *(_BYTE *)(DeviceExtension[66] + 30LL) != 1 )
      v6 = 88;
    v7 = v6;
    Pool2 = ExAllocatePool2(64, v6, 1396990803);
    if ( Pool2 )
    {
      if ( *(_BYTE *)(DeviceExtension[66] + 30LL) != 1 )
      {
        *(_WORD *)Pool2 = 88;
        v9 = (_BYTE *)(Pool2 + 72);
        *(_BYTE *)(Pool2 + 2) = 0;
        *(_BYTE *)(Pool2 + 10) = 6;
        *(_DWORD *)(Pool2 + 20) = *((_DWORD *)DeviceExtension + 146);
        goto LABEL_9;
      }
      *(_WORD *)Pool2 = 8;
      *(_DWORD *)(Pool2 + 12) = 1;
      *(_BYTE *)(Pool2 + 2) = 40;
      *(_DWORD *)(Pool2 + 8) = 1397899864;
      *(_DWORD *)(Pool2 + 16) = v7;
      *(_DWORD *)(Pool2 + 20) = 0;
      *(_WORD *)(Pool2 + 36) = IoGetIoPriorityHint(Irp);
      *(_DWORD *)(Pool2 + 52) = 128;
      *(_DWORD *)(Pool2 + 56) = 1;
      *(_DWORD *)(Pool2 + 40) = *((_DWORD *)DeviceExtension + 146);
      *(_WORD *)(Pool2 + 128) = 1;
      *(_DWORD *)(Pool2 + 132) = 4;
      *(_DWORD *)(Pool2 + 120) = 144;
      if ( *(_DWORD *)(Pool2 + 16) >= 0xB8u )
      {
        *(_DWORD *)(Pool2 + 144) = 64;
        v9 = (_BYTE *)(Pool2 + 168);
        *(_DWORD *)(Pool2 + 148) = 32;
        *(_BYTE *)(Pool2 + 154) = 6;
LABEL_9:
        *v9 = 0;
        v10 = ClassSendSrbSynchronous(DeviceObject, (PSCSI_REQUEST_BLOCK)Pool2, 0, 0, 0);
        v11 = (CHAR *)ExAllocatePool2(72, 192, 1296327507);
        v12 = (unsigned __int8 *)v11;
        if ( v11 )
        {
          if ( ClassModeSense(DeviceObject, v11, 0xC0u, 0x3Fu) )
          {
            LOBYTE(v13) = 0;
            v16 = v10 >= 0;
            if ( v12[3] )
              v13 = v12[4];
            v14 = DiskDetermineMediaTypes(
                    (_DWORD)DeviceObject,
                    (_DWORD)Irp,
                    v12[1],
                    v13,
                    v16,
                    (unsigned __int8)~v12[2] >> 7);
          }
          else
          {
            v14 = -1073741823;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
            }
          }
          ExFreePoolWithTag((PVOID)Pool2, 0);
          ExFreePoolWithTag(v12, 0);
          return v14;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
          }
          ExFreePoolWithTag((PVOID)Pool2, 0);
          return 3221225626LL;
        }
      }
      ExFreePoolWithTag((PVOID)Pool2, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
      }
      return 3221225701LL;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
      }
      return 3221225626LL;
    }
  }
}

```

## disassembly

```asm
0x140013750  mov     [rsp+arg_18], rbx
0x140013755  push    rbp
0x140013756  push    rsi
0x140013757  push    rdi
0x140013758  sub     rsp, 30h
0x14001375c  mov     rdi, [rcx+40h]
0x140013760  mov     rbp, rdx
0x140013763  mov     rbx, [rdx+0B8h]
0x14001376a  mov     rsi, rcx
0x14001376d  call    cs:__imp_KeGetCurrentIrql
0x140013774  nop     dword ptr [rax+rax+00h]
0x140013779  cmp     al, 2
0x14001377b  jnb     loc_140013A13
0x140013781  mov     rcx, cs:WPP_GLOBAL_Control
0x140013788  mov     [rsp+48h+arg_0], r12
0x14001378d  lea     r12, WPP_GLOBAL_Control
0x140013794  cmp     rcx, r12
0x140013797  jnz     loc_140013918
0x14001379d  cmp     dword ptr [rbx+8], 28h ; '('
0x1400137a1  jb      loc_140013A1D
0x1400137a7  mov     rax, [rdi+210h]
0x1400137ae  mov     ecx, 0B8h
0x1400137b3  mov     [rsp+48h+arg_8], r14
0x1400137b8  mov     r8d, 53446353h
0x1400137be  mov     [rsp+48h+arg_10], r15
0x1400137c3  mov     r15d, 58h ; 'X'
0x1400137c9  cmp     byte ptr [rax+1Eh], 1
0x1400137cd  cmovnz  ecx, r15d
0x1400137d1  mov     r14d, ecx
0x1400137d4  mov     edx, ecx
0x1400137d6  mov     ecx, 40h ; '@'
0x1400137db  call    cs:__imp_ExAllocatePool2
0x1400137e2  nop     dword ptr [rax+rax+00h]
0x1400137e7  mov     rbx, rax
0x1400137ea  test    rax, rax
0x1400137ed  jz      loc_140013A55
0x1400137f3  mov     rax, [rdi+210h]
0x1400137fa  cmp     byte ptr [rax+1Eh], 1
0x1400137fe  jz      loc_14001394F
0x140013804  mov     [rbx], r15w
0x140013808  lea     rcx, [rbx+48h]
0x14001380c  mov     byte ptr [rbx+2], 0
0x140013810  mov     byte ptr [rbx+0Ah], 6
0x140013814  mov     eax, [rdi+248h]
0x14001381a  mov     [rbx+14h], eax
0x14001381d  mov     byte ptr [rcx], 0
0x140013820  xor     r9d, r9d; BufferLength
0x140013823  mov     rcx, rsi; DeviceObject
0x140013826  mov     [rsp+48h+WriteToDevice], 0; WriteToDevice
0x14001382b  xor     r8d, r8d; BufferAddress
0x14001382e  mov     rdx, rbx; Srb
0x140013831  call    cs:__imp_ClassSendSrbSynchronous
0x140013838  nop     dword ptr [rax+rax+00h]
0x14001383d  mov     edx, 0C0h
0x140013842  mov     ecx, 48h ; 'H'
0x140013847  mov     r8d, 4D446353h
0x14001384d  mov     r14d, eax
0x140013850  call    cs:__imp_ExAllocatePool2
0x140013857  nop     dword ptr [rax+rax+00h]
0x14001385c  mov     rdi, rax
0x14001385f  test    rax, rax
0x140013862  jz      loc_1400139E8
0x140013868  mov     r9b, 3Fh ; '?'; PageMode
0x14001386b  mov     r8d, 0C0h; Length
0x140013871  mov     rdx, rax; ModeSenseBuffer
0x140013874  mov     rcx, rsi; DeviceObject
0x140013877  call    cs:__imp_ClassModeSense
0x14001387e  nop     dword ptr [rax+rax+00h]
0x140013883  test    eax, eax
0x140013885  jnz     short loc_1400138DD
0x140013887  mov     esi, 0C0000001h
0x14001388c  mov     rcx, cs:WPP_GLOBAL_Control
0x140013893  cmp     rcx, r12
0x140013896  jnz     loc_140013B0F
0x14001389c  xor     edx, edx; Tag
0x14001389e  mov     rcx, rbx; P
0x1400138a1  call    cs:__imp_ExFreePoolWithTag
0x1400138a8  nop     dword ptr [rax+rax+00h]
0x1400138ad  xor     edx, edx; Tag
0x1400138af  mov     rcx, rdi; P
0x1400138b2  call    cs:__imp_ExFreePoolWithTag
0x1400138b9  nop     dword ptr [rax+rax+00h]
0x1400138be  mov     eax, esi
0x1400138c0  mov     r14, [rsp+48h+arg_8]
0x1400138c5  mov     r15, [rsp+48h+arg_10]
0x1400138ca  mov     r12, [rsp+48h+arg_0]
0x1400138cf  mov     rbx, [rsp+48h+arg_18]
0x1400138d4  add     rsp, 30h
0x1400138d8  pop     rdi
0x1400138d9  pop     rsi
0x1400138da  pop     rbp
0x1400138db  retn
0x1400138dd  shr     r14d, 1Fh
0x1400138e1  xor     r9b, r9b
0x1400138e4  xor     r14b, 1
0x1400138e8  cmp     [rdi+3], r9b
0x1400138ec  jnz     loc_140013B05
0x1400138f2  movzx   eax, byte ptr [rdi+2]
0x1400138f6  mov     rdx, rbp
0x1400138f9  movzx   r8d, byte ptr [rdi+1]
0x1400138fe  not     al
0x140013900  shr     al, 7
0x140013903  mov     rcx, rsi
0x140013906  mov     [rsp+48h+var_20], al
0x14001390a  mov     [rsp+48h+WriteToDevice], r14b
0x14001390f  call    DiskDetermineMediaTypes
0x140013914  mov     esi, eax
0x140013916  jmp     short loc_14001389C
0x140013918  mov     eax, [rcx+2Ch]
0x14001391b  test    al, 10h
0x14001391d  jz      loc_14001379D
0x140013923  cmp     byte ptr [rcx+29h], 4
0x140013927  jb      loc_14001379D
0x14001392d  mov     rcx, [rcx+18h]
0x140013931  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140013938  mov     edx, 3Fh ; '?'
0x14001393d  mov     qword ptr [rsp+48h+WriteToDevice], rbp
0x140013942  mov     r9, rsi
0x140013945  call    WPP_SF_qq
0x14001394a  jmp     loc_14001379D
0x14001394f  mov     r15d, 1
0x140013955  mov     word ptr [rbx], 8
0x14001395a  mov     rcx, rbp; Irp
0x14001395d  mov     [rbx+0Ch], r15d
0x140013961  mov     byte ptr [rbx+2], 28h ; '('
0x140013965  mov     dword ptr [rbx+8], 53524258h
0x14001396c  mov     [rbx+10h], r14d
0x140013970  mov     dword ptr [rbx+14h], 0
0x140013977  call    cs:__imp_IoGetIoPriorityHint
0x14001397e  nop     dword ptr [rax+rax+00h]
0x140013983  mov     [rbx+24h], ax
0x140013987  mov     dword ptr [rbx+34h], 80h
0x14001398e  mov     [rbx+38h], r15d
0x140013992  mov     eax, [rdi+248h]
0x140013998  mov     [rbx+28h], eax
0x14001399b  mov     [rbx+80h], r15w
0x1400139a3  mov     dword ptr [rbx+84h], 4
0x1400139ad  mov     dword ptr [rbx+78h], 90h
0x1400139b4  cmp     dword ptr [rbx+10h], 0B8h
0x1400139bb  jb      loc_140013A8D
0x1400139c1  mov     dword ptr [rbx+90h], 40h ; '@'
0x1400139cb  lea     rcx, [rbx+0A8h]
0x1400139d2  mov     dword ptr [rbx+94h], 20h ; ' '
0x1400139dc  mov     byte ptr [rbx+9Ah], 6
0x1400139e3  jmp     loc_14001381D
0x1400139e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400139ef  cmp     rcx, r12
0x1400139f2  jnz     loc_140013AD6
0x1400139f8  xor     edx, edx; Tag
0x1400139fa  mov     rcx, rbx; P
0x1400139fd  call    cs:__imp_ExFreePoolWithTag
0x140013a04  nop     dword ptr [rax+rax+00h]
0x140013a09  mov     eax, 0C000009Ah
0x140013a0e  jmp     loc_1400138C0
0x140013a13  mov     eax, 0C0000148h
0x140013a18  jmp     loc_1400138CF
0x140013a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013a24  cmp     rcx, r12
0x140013a27  jz      short loc_140013A4B
0x140013a29  mov     eax, [rcx+2Ch]
0x140013a2c  test    al, 10h
0x140013a2e  jz      short loc_140013A4B
0x140013a30  cmp     byte ptr [rcx+29h], 2
0x140013a34  jb      short loc_140013A4B
0x140013a36  mov     rcx, [rcx+18h]
0x140013a3a  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140013a41  mov     edx, 40h ; '@'
0x140013a46  call    WPP_SF_
0x140013a4b  mov     eax, 0C0000023h
0x140013a50  jmp     loc_1400138CA
0x140013a55  mov     rcx, cs:WPP_GLOBAL_Control
0x140013a5c  cmp     rcx, r12
0x140013a5f  jz      short loc_140013A83
0x140013a61  mov     eax, [rcx+2Ch]
0x140013a64  test    al, 10h
0x140013a66  jz      short loc_140013A83
0x140013a68  cmp     byte ptr [rcx+29h], 2
0x140013a6c  jb      short loc_140013A83
0x140013a6e  mov     rcx, [rcx+18h]
0x140013a72  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140013a79  mov     edx, 41h ; 'A'
0x140013a7e  call    WPP_SF_
0x140013a83  mov     eax, 0C000009Ah
0x140013a88  jmp     loc_1400138C0
0x140013a8d  xor     edx, edx; Tag
0x140013a8f  mov     rcx, rbx; P
0x140013a92  call    cs:__imp_ExFreePoolWithTag
0x140013a99  nop     dword ptr [rax+rax+00h]
0x140013a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140013aa5  cmp     rcx, r12
0x140013aa8  jz      short loc_140013ACC
0x140013aaa  mov     eax, [rcx+2Ch]
0x140013aad  test    al, 10h
0x140013aaf  jz      short loc_140013ACC
0x140013ab1  cmp     byte ptr [rcx+29h], 2
0x140013ab5  jb      short loc_140013ACC
0x140013ab7  mov     rcx, [rcx+18h]
0x140013abb  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140013ac2  mov     edx, 42h ; 'B'
0x140013ac7  call    WPP_SF_
0x140013acc  mov     eax, 0C00000E5h
0x140013ad1  jmp     loc_1400138C0
0x140013ad6  mov     eax, [rcx+2Ch]
0x140013ad9  test    al, 10h
0x140013adb  jz      loc_1400139F8
0x140013ae1  cmp     byte ptr [rcx+29h], 2
0x140013ae5  jb      loc_1400139F8
0x140013aeb  mov     rcx, [rcx+18h]
0x140013aef  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140013af6  mov     edx, 43h ; 'C'
0x140013afb  call    WPP_SF_
0x140013b00  jmp     loc_1400139F8
0x140013b05  movzx   r9d, byte ptr [rdi+4]
0x140013b0a  jmp     loc_1400138F2
0x140013b0f  mov     eax, [rcx+2Ch]
0x140013b12  test    al, 10h
0x140013b14  jz      loc_14001389C
0x140013b1a  cmp     byte ptr [rcx+29h], 2
0x140013b1e  jb      loc_14001389C
0x140013b24  mov     rcx, [rcx+18h]
0x140013b28  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140013b2f  mov     edx, 44h ; 'D'
0x140013b34  call    WPP_SF_
0x140013b39  jmp     loc_14001389C
```
