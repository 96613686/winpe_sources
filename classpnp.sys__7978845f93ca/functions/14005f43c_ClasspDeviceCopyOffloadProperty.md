# ClasspDeviceCopyOffloadProperty

- ea: `0x14005f43c`
- end: `0x14005f683`
- name: `ClasspDeviceCopyOffloadProperty`
- size: `583`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140005190`
- `0x1400134a0`
- `0x14001fc38`
- `0x14002001c`
- `0x14003e940`
- `0x14005f43c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14005f497`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005f497`

## pseudocode

```c
__int64 __fastcall ClasspDeviceCopyOffloadProperty(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _IRP *MasterIrp; // r14
  _QWORD *DeviceExtension; // rbp
  _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  int v7; // r8d
  ULONG_PTR v8; // rbx
  size_t Length; // r8
  __int64 v10; // rdi
  NTSTATUS v11; // edi
  __int64 v13; // rax

  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  DeviceExtension = DeviceObject->DeviceExtension;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
  }
  v7 = *(_DWORD *)(&MasterIrp->Size + 1);
  v8 = 0;
  if ( v7 == 1 )
  {
    v11 = 0;
  }
  else if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        99,
        WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
        DeviceObject,
        v7);
    }
    v11 = -1073741637;
  }
  else if ( KeGetCurrentIrql() >= 2u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
    }
    v11 = -1073741496;
  }
  else
  {
    Length = CurrentStackLocation->Parameters.Read.Length;
    if ( (unsigned int)Length < 0x30 )
    {
      if ( (unsigned int)Length < 8 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            102,
            WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
            DeviceObject,
            Length);
        }
        v11 = -1073741789;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            101,
            WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
            DeviceObject,
            Length);
        }
        v11 = 0;
        *(_DWORD *)&MasterIrp->Type = 48;
        v8 = 8;
        *(_DWORD *)(&MasterIrp->Size + 1) = 48;
      }
    }
    else
    {
      v10 = DeviceExtension[144];
      if ( (*(_DWORD *)(v10 + 16) & 8) != 0 )
      {
        v11 = *(_DWORD *)(v10 + 128);
        if ( v11 >= 0 )
        {
          memset(MasterIrp, 0, Length);
          *(_DWORD *)&MasterIrp->Type = 1;
          *(_DWORD *)(&MasterIrp->Size + 1) = 48;
          LODWORD(MasterIrp->MdlAddress) = *(_DWORD *)(DeviceExtension[144] + 136LL);
          HIDWORD(MasterIrp->MdlAddress) = *(_DWORD *)(DeviceExtension[144] + 140LL);
          *(_QWORD *)&MasterIrp->Flags = *(_QWORD *)(DeviceExtension[144] + 144LL);
          MasterIrp->AssociatedIrp.MasterIrp = *(_IRP **)(DeviceExtension[144] + 152LL);
          LODWORD(MasterIrp->ThreadListEntry.Flink) = *(unsigned __int16 *)(DeviceExtension[144] + 132LL);
          v13 = DeviceExtension[144];
          if ( *(int *)(v13 + 40) >= 0 )
          {
            HIDWORD(MasterIrp->ThreadListEntry.Flink) = *(_DWORD *)(v13 + 64);
            LODWORD(MasterIrp->ThreadListEntry.Blink) = *(_DWORD *)(DeviceExtension[144] + 68LL);
            WORD2(MasterIrp->ThreadListEntry.Blink) = *(_WORD *)(DeviceExtension[144] + 62LL);
          }
          v11 = 0;
          v8 = 48;
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            104,
            WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
            DeviceObject,
            v11);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            103,
            WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
            DeviceObject);
        }
        v11 = -1073740701;
      }
    }
  }
  Irp->IoStatus.Information = v8;
  Irp->IoStatus.Status = v11;
  ClassReleaseRemoveLock(DeviceObject, Irp);
  ClassCompleteRequest(DeviceObject, Irp, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      105,
      WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
      DeviceObject,
      v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14005f43c  push    rbx
0x14005f43e  push    rbp
0x14005f43f  push    rsi
0x14005f440  push    rdi
0x14005f441  push    r13
0x14005f443  push    r14
0x14005f445  push    r15
0x14005f447  sub     rsp, 30h
0x14005f44b  mov     r14, [rdx+18h]
0x14005f44f  mov     r15, rdx
0x14005f452  mov     rbp, [rcx+40h]
0x14005f456  mov     rsi, rcx
0x14005f459  mov     rdi, [rdx+0B8h]
0x14005f460  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f467  lea     r13, WPP_GLOBAL_Control
0x14005f46e  cmp     rcx, r13
0x14005f471  jz      short loc_14005F47E
0x14005f473  mov     eax, [rcx+2Ch]
0x14005f476  test    al, 10h
0x14005f478  jnz     loc_14005F558
0x14005f47e  mov     r8d, [r14+4]
0x14005f482  xor     ebx, ebx
0x14005f484  cmp     r8d, 1
0x14005f488  jz      loc_14005F554
0x14005f48e  test    r8d, r8d
0x14005f491  jnz     loc_14005F57F
0x14005f497  call    cs:__imp_KeGetCurrentIrql
0x14005f49e  nop     dword ptr [rax+rax+00h]
0x14005f4a3  mov     dl, 2
0x14005f4a5  cmp     al, dl
0x14005f4a7  jnb     loc_14005F5C8
0x14005f4ad  mov     r8d, [rdi+8]; Size
0x14005f4b1  cmp     r8d, 30h ; '0'
0x14005f4b5  jb      loc_140061AF4
0x14005f4bb  mov     rdi, [rbp+480h]
0x14005f4c2  mov     eax, [rdi+10h]
0x14005f4c5  test    al, 8
0x14005f4c7  jnz     loc_14005F630
0x14005f4cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f4d4  cmp     rcx, r13
0x14005f4d7  jz      short loc_14005F4E4
0x14005f4d9  mov     eax, [rcx+2Ch]
0x14005f4dc  test    al, 10h
0x14005f4de  jnz     loc_14005F60A
0x14005f4e4  mov     edi, 0C0000463h
0x14005f4e9  mov     rdx, r15; Tag
0x14005f4ec  mov     [r15+38h], rbx
0x14005f4f0  mov     rcx, rsi; DeviceObject
0x14005f4f3  mov     [r15+30h], edi
0x14005f4f7  call    ClassReleaseRemoveLock
0x14005f4fc  xor     r8d, r8d; PriorityBoost
0x14005f4ff  mov     rdx, r15; Irp
0x14005f502  mov     rcx, rsi; DeviceObject
0x14005f505  call    ClassCompleteRequest
0x14005f50a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f511  cmp     rcx, r13
0x14005f514  jnz     short loc_14005F528
0x14005f516  mov     eax, edi
0x14005f518  add     rsp, 30h
0x14005f51c  pop     r15
0x14005f51e  pop     r14
0x14005f520  pop     r13
0x14005f522  pop     rdi
0x14005f523  pop     rsi
0x14005f524  pop     rbp
0x14005f525  pop     rbx
0x14005f526  retn
0x14005f528  mov     edx, [rcx+2Ch]
0x14005f52b  test    dl, 10h
0x14005f52e  jz      short loc_14005F516
0x14005f530  cmp     byte ptr [rcx+29h], 5
0x14005f534  jb      short loc_14005F516
0x14005f536  mov     rcx, [rcx+18h]
0x14005f53a  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14005f541  mov     edx, 69h ; 'i'
0x14005f546  mov     [rsp+68h+var_48], edi
0x14005f54a  mov     r9, rsi
0x14005f54d  call    WPP_SF_qD
0x14005f552  jmp     short loc_14005F516
0x14005f554  mov     edi, ebx
0x14005f556  jmp     short loc_14005F4E9
0x14005f558  cmp     byte ptr [rcx+29h], 5
0x14005f55c  jb      loc_14005F47E
0x14005f562  mov     rcx, [rcx+18h]
0x14005f566  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14005f56d  mov     edx, 62h ; 'b'
0x14005f572  mov     r9, rsi
0x14005f575  call    WPP_SF_q
0x14005f57a  jmp     loc_14005F47E
0x14005f57f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f586  cmp     rcx, r13
0x14005f589  jz      loc_140061AE0
0x14005f58f  mov     eax, [rcx+2Ch]
0x14005f592  test    al, 10h
0x14005f594  jz      loc_140061AE0
0x14005f59a  mov     dl, 2
0x14005f59c  cmp     [rcx+29h], dl
0x14005f59f  jb      loc_140061AE0
0x14005f5a5  mov     rcx, [rcx+18h]
0x14005f5a9  mov     edx, 63h ; 'c'
0x14005f5ae  mov     [rsp+68h+var_48], r8d
0x14005f5b3  mov     r9, rsi
0x14005f5b6  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14005f5bd  call    WPP_SF_qD
0x14005f5c2  nop
0x14005f5c3  jmp     loc_140061AE0
0x14005f5c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f5cf  cmp     rcx, r13
0x14005f5d2  jz      loc_140061AEA
0x14005f5d8  mov     eax, [rcx+2Ch]
0x14005f5db  test    al, 10h
0x14005f5dd  jz      loc_140061AEA
0x14005f5e3  cmp     [rcx+29h], dl
0x14005f5e6  jb      loc_140061AEA
0x14005f5ec  mov     rcx, [rcx+18h]
0x14005f5f0  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14005f5f7  mov     edx, 64h ; 'd'
0x14005f5fc  mov     r9, rsi
0x14005f5ff  call    WPP_SF_q
0x14005f604  nop
0x14005f605  jmp     loc_140061AEA
0x14005f60a  cmp     [rcx+29h], dl
0x14005f60d  jb      loc_14005F4E4
0x14005f613  mov     rcx, [rcx+18h]
0x14005f617  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14005f61e  mov     edx, 67h ; 'g'
0x14005f623  mov     r9, rsi
0x14005f626  call    WPP_SF_q
0x14005f62b  jmp     loc_14005F4E4
0x14005f630  mov     edi, [rdi+80h]
0x14005f636  test    edi, edi
0x14005f638  jns     loc_140061B8A
0x14005f63e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f645  cmp     rcx, r13
0x14005f648  jz      loc_14005F4E9
0x14005f64e  mov     eax, [rcx+2Ch]
0x14005f651  test    al, 10h
0x14005f653  jz      loc_14005F4E9
0x14005f659  cmp     [rcx+29h], dl
0x14005f65c  jb      loc_14005F4E9
0x14005f662  mov     rcx, [rcx+18h]
0x14005f666  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14005f66d  mov     edx, 68h ; 'h'
0x14005f672  mov     [rsp+68h+var_48], edi
0x14005f676  mov     r9, rsi
0x14005f679  call    WPP_SF_qD
0x14005f67e  jmp     loc_14005F4E9
0x140061ae0  mov     edi, 0C00000BBh
0x140061ae5  jmp     loc_14005F4E9
0x140061aea  mov     edi, 0C0000148h
0x140061aef  jmp     loc_14005F4E9
0x140061af4  cmp     r8d, 8
0x140061af8  jb      short loc_140061B4B
0x140061afa  mov     rcx, cs:WPP_GLOBAL_Control
0x140061b01  cmp     rcx, r13
0x140061b04  jz      short loc_140061B30
0x140061b06  mov     eax, [rcx+2Ch]
0x140061b09  test    al, 10h
0x140061b0b  jz      short loc_140061B30
0x140061b0d  cmp     byte ptr [rcx+29h], 3
0x140061b11  jb      short loc_140061B30
0x140061b13  mov     rcx, [rcx+18h]
0x140061b17  mov     edx, 65h ; 'e'
0x140061b1c  mov     [rsp+68h+var_48], r8d
0x140061b21  mov     r9, rsi
0x140061b24  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140061b2b  call    WPP_SF_qD
0x140061b30  mov     edi, ebx
0x140061b32  mov     dword ptr [r14], 30h ; '0'
0x140061b39  mov     ebx, 8
0x140061b3e  mov     dword ptr [r14+4], 30h ; '0'
0x140061b46  jmp     loc_14005F4E9
0x140061b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140061b52  cmp     rcx, r13
0x140061b55  jz      short loc_140061B80
0x140061b57  mov     eax, [rcx+2Ch]
0x140061b5a  test    al, 10h
0x140061b5c  jz      short loc_140061B80
0x140061b5e  cmp     [rcx+29h], dl
0x140061b61  jb      short loc_140061B80
0x140061b63  mov     rcx, [rcx+18h]
0x140061b67  mov     edx, 66h ; 'f'
0x140061b6c  mov     [rsp+68h+var_48], r8d
0x140061b71  mov     r9, rsi
0x140061b74  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140061b7b  call    WPP_SF_qD
0x140061b80  mov     edi, 0C0000023h
0x140061b85  jmp     loc_14005F4E9
0x140061b8a  xor     edx, edx; Val
0x140061b8c  mov     rcx, r14; void *
0x140061b8f  call    memset
0x140061b94  mov     dword ptr [r14], 1
0x140061b9b  mov     edx, 30h ; '0'
0x140061ba0  mov     [r14+4], edx
0x140061ba4  mov     rax, [rbp+480h]
0x140061bab  mov     ecx, [rax+88h]
0x140061bb1  mov     [r14+8], ecx
0x140061bb5  mov     rax, [rbp+480h]
0x140061bbc  mov     ecx, [rax+8Ch]
0x140061bc2  mov     [r14+0Ch], ecx
0x140061bc6  mov     rax, [rbp+480h]
0x140061bcd  mov     rcx, [rax+90h]
0x140061bd4  mov     [r14+10h], rcx
0x140061bd8  mov     rax, [rbp+480h]
0x140061bdf  mov     rcx, [rax+98h]
0x140061be6  mov     [r14+18h], rcx
0x140061bea  mov     rax, [rbp+480h]
0x140061bf1  movzx   ecx, word ptr [rax+84h]
0x140061bf8  mov     [r14+20h], ecx
0x140061bfc  mov     rax, [rbp+480h]
0x140061c03  cmp     [rax+28h], ebx
0x140061c06  jl      short loc_140061C2D
0x140061c08  mov     eax, [rax+40h]
0x140061c0b  mov     [r14+24h], eax
0x140061c0f  mov     rax, [rbp+480h]
0x140061c16  mov     ecx, [rax+44h]
0x140061c19  mov     [r14+28h], ecx
0x140061c1d  mov     rax, [rbp+480h]
0x140061c24  movzx   ecx, word ptr [rax+3Eh]
0x140061c28  mov     [r14+2Ch], cx
0x140061c2d  mov     edi, ebx
0x140061c2f  mov     rbx, rdx
0x140061c32  jmp     loc_14005F4E9
```
