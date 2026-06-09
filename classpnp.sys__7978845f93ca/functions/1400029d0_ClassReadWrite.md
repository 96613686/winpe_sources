# ClassReadWrite

- ea: `0x1400029d0`
- end: `0x140002d28`
- name: `ClassReadWrite`
- size: `856`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140023980`

## callees

- `0x1400024b0`
- `0x1400029d0`
- `0x140002fb0`
- `0x140005190`
- `0x1400134a0`
- `0x14001fbf4`
- `0x14003e470`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140002b25`
- `ntoskrnl!IofCallDriver` at `0x140002d17`
- `ntoskrnl!IofCallDriver` at `0x140002b25`
- `ntoskrnl!IofCallDriver` at `0x140002d17`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140002b69`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140002b69`
- `ntoskrnl!IoStartPacket` at `0x140002aa1`
- `ntoskrnl!IoStartPacket` at `0x140002aa1`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140002a1a`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140002a1a`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140002c9f`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140002c9f`

## pseudocode

```c
__int64 __fastcall ClassReadWrite(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  void *DeviceExtension; // rbx
  _IO_STACK_LOCATION *CurrentStackLocation; // r14
  __int64 v6; // r13
  struct _DEVICE_OBJECT *v7; // r12
  unsigned int Length; // r15d
  volatile signed __int32 **v9; // rdi
  int v10; // eax
  unsigned int v11; // edi
  _IO_STACK_LOCATION *v14; // rax

  DeviceExtension = DeviceObject->DeviceExtension;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v6 = *((_QWORD *)DeviceExtension + 143);
  v7 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 2);
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( (*((_BYTE *)DeviceExtension + 104) & 1) != 0
    && !*((_DWORD *)DeviceExtension + 27)
    && (*((_WORD *)DeviceExtension + 320) & 0x40) != 0
    && (!ClassDisableForwardedIo || *(_DWORD *)(*((_QWORD *)DeviceExtension + 65) + 28LL) == 16)
    && (CurrentStackLocation->MajorFunction == 3
     || (*((_WORD *)DeviceExtension + 320) & 0x80u) == 0
     || Length <= *(_DWORD *)(v6 + 652)) )
  {
    ++Irp->CurrentLocation;
    ++Irp->Tail.Overlay.CurrentStackLocation;
    return (unsigned int)IofCallDriver(v7, Irp);
  }
  v9 = (volatile signed __int32 **)DeviceObject->DeviceExtension;
  if ( !ExAcquireRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v9[55] + 2)) )
  {
    _InterlockedIncrement(v9[55]);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_a22cc05f221e30b8049471910da99059_Traceguids,
        *(unsigned int *)v9[55]);
    }
  }
  if ( *((_DWORD *)v9 + 27) )
  {
    v11 = -1073741632;
    goto LABEL_26;
  }
  if ( (DeviceObject->Flags & 2) != 0
    && CurrentStackLocation->MinorFunction != 52
    && (CurrentStackLocation->Flags & 2) == 0 )
  {
    if ( Irp->Tail.Overlay.Thread )
      IoSetHardErrorOrVerifyDevice(Irp, DeviceObject);
    v11 = -2147483626;
    goto LABEL_26;
  }
  CurrentStackLocation->MinorFunction = 52;
  v10 = (*(__int64 (__fastcall **)(PDEVICE_OBJECT, PIRP))(*((_QWORD *)DeviceExtension + 20) + 24LL))(DeviceObject, Irp);
  v11 = v10;
  if ( v10 < 0 )
  {
LABEL_27:
    Irp->IoStatus.Information = 0;
    ClassReleaseRemoveLock(DeviceObject, Irp);
    ClassCompleteRequest(DeviceObject, Irp, 0);
    return v11;
  }
  if ( v10 != 259 )
  {
    if ( !Length )
    {
      Irp->IoStatus.Status = 0;
      Irp->IoStatus.Information = 0;
      ClassReleaseRemoveLock(DeviceObject, Irp);
      ClassCompleteRequest(DeviceObject, Irp, 0);
      return 0;
    }
    if ( *(_QWORD *)(*((_QWORD *)DeviceExtension + 4) + 384LL) )
    {
      Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      IoStartPacket(DeviceObject, Irp, 0, 0);
      return 259;
    }
    CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart += *((_QWORD *)DeviceExtension + 19);
    if ( (*((_BYTE *)DeviceExtension + 104) & 1) != 0 )
    {
      CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart += *(unsigned int *)(*((_QWORD *)DeviceExtension + 3)
                                                                                   + 540LL);
      if ( (*((_WORD *)DeviceExtension + 320) & 0x20) == 0
        && CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart >> *((_BYTE *)DeviceExtension + 642) > 0xFFFFFFFFLL )
      {
        v11 = -1073741811;
LABEL_26:
        Irp->IoStatus.Status = v11;
        goto LABEL_27;
      }
      if ( IoGetIoPriorityHint(Irp) <= IoPriorityLow
        && (*(_DWORD *)(v6 + 664) & 1) != 0
        && (*(_BYTE *)(v6 + 112) & 4) == 0
        && (*(_BYTE *)(v6 + 284) & 4) == 0 )
      {
        *((_BYTE *)&Irp->Tail.CompletionKey + 8) = 1;
        return (unsigned int)ClasspEnqueueIdleRequest(DeviceObject, Irp);
      }
      *((_BYTE *)&Irp->Tail.CompletionKey + 8) = 0;
      return (unsigned int)ServiceTransferRequest((__int64)DeviceObject, (__int64)Irp, 0);
    }
    else
    {
      v14 = Irp->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&v14[-1].MajorFunction = *(_OWORD *)&v14->MajorFunction;
      *(_OWORD *)&v14[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v14->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v14[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v14->Parameters.SetQuota + 6);
      v14[-1].FileObject = v14->FileObject;
      v14[-1].Control = 0;
      ClassReleaseRemoveLock(DeviceObject, Irp);
      return (unsigned int)IofCallDriver(v7, Irp);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x1400029d0  push    rbx
0x1400029d2  push    rbp
0x1400029d3  push    rsi
0x1400029d4  push    rdi
0x1400029d5  push    r12
0x1400029d7  push    r13
0x1400029d9  push    r14
0x1400029db  push    r15
0x1400029dd  sub     rsp, 28h
0x1400029e1  mov     rbx, [rcx+40h]
0x1400029e5  mov     rbp, rdx
0x1400029e8  mov     r14, [rdx+0B8h]
0x1400029ef  mov     rsi, rcx
0x1400029f2  test    byte ptr [rbx+68h], 1
0x1400029f6  mov     r13, [rbx+478h]
0x1400029fd  mov     r12, [rbx+10h]
0x140002a01  mov     r15d, [r14+8]
0x140002a05  jnz     loc_140002AC6
0x140002a0b  mov     rdi, [rcx+40h]
0x140002a0f  mov     rcx, [rdi+1B8h]
0x140002a16  add     rcx, 8; RunRefCacheAware
0x140002a1a  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140002a21  nop     dword ptr [rax+rax+00h]
0x140002a26  test    al, al
0x140002a28  jz      loc_140002C0F
0x140002a2e  cmp     dword ptr [rdi+6Ch], 0
0x140002a32  jnz     loc_140002C6B
0x140002a38  mov     eax, [rsi+30h]
0x140002a3b  test    al, 2
0x140002a3d  jnz     loc_140002C75
0x140002a43  mov     byte ptr [r14+1], 34h ; '4'
0x140002a48  mov     rdx, rbp
0x140002a4b  mov     rax, [rbx+0A0h]
0x140002a52  mov     rcx, rsi
0x140002a55  mov     rax, [rax+18h]
0x140002a59  call    _guard_dispatch_icall
0x140002a5e  mov     edi, eax
0x140002a60  test    eax, eax
0x140002a62  js      loc_140002BB6
0x140002a68  cmp     eax, 103h
0x140002a6d  jz      short loc_140002AB2
0x140002a6f  test    r15d, r15d
0x140002a72  jz      loc_140002CB1
0x140002a78  mov     rax, [rbx+20h]
0x140002a7c  cmp     qword ptr [rax+180h], 0
0x140002a84  jz      loc_140002B38
0x140002a8a  mov     rax, [rbp+0B8h]
0x140002a91  xor     r9d, r9d; CancelFunction
0x140002a94  xor     r8d, r8d; Key
0x140002a97  mov     rdx, rbp; Irp
0x140002a9a  mov     rcx, rsi; DeviceObject
0x140002a9d  or      byte ptr [rax+3], 1
0x140002aa1  call    cs:__imp_IoStartPacket
0x140002aa8  nop     dword ptr [rax+rax+00h]
0x140002aad  mov     edi, 103h
0x140002ab2  mov     eax, edi
0x140002ab4  add     rsp, 28h
0x140002ab8  pop     r15
0x140002aba  pop     r14
0x140002abc  pop     r13
0x140002abe  pop     r12
0x140002ac0  pop     rdi
0x140002ac1  pop     rsi
0x140002ac2  pop     rbp
0x140002ac3  pop     rbx
0x140002ac4  retn
0x140002ac6  cmp     dword ptr [rbx+6Ch], 0
0x140002aca  jnz     loc_140002A0B
0x140002ad0  movzx   eax, word ptr [rbx+280h]
0x140002ad7  test    al, 40h
0x140002ad9  jz      loc_140002A0B
0x140002adf  cmp     cs:ClassDisableForwardedIo, 0
0x140002ae6  jz      short loc_140002AF9
0x140002ae8  mov     rax, [rbx+208h]
0x140002aef  cmp     dword ptr [rax+1Ch], 10h
0x140002af3  jnz     loc_140002A0B
0x140002af9  cmp     byte ptr [r14], 3
0x140002afd  jz      short loc_140002B17
0x140002aff  movzx   eax, word ptr [rbx+280h]
0x140002b06  test    al, al
0x140002b08  jns     short loc_140002B17
0x140002b0a  cmp     r15d, [r13+28Ch]
0x140002b11  ja      loc_140002A0B
0x140002b17  inc     byte ptr [rdx+43h]
0x140002b1a  mov     rcx, r12; DeviceObject
0x140002b1d  add     qword ptr [rdx+0B8h], 48h ; 'H'
0x140002b25  call    cs:__imp_IofCallDriver
0x140002b2c  nop     dword ptr [rax+rax+00h]
0x140002b31  mov     edi, eax
0x140002b33  jmp     loc_140002AB2
0x140002b38  mov     rax, [rbx+98h]
0x140002b3f  add     [r14+18h], rax
0x140002b43  test    byte ptr [rbx+68h], 1
0x140002b47  jz      loc_140002CDA
0x140002b4d  mov     rax, [rbx+18h]
0x140002b51  mov     ecx, [rax+21Ch]
0x140002b57  add     [r14+18h], rcx
0x140002b5b  movzx   eax, word ptr [rbx+280h]
0x140002b62  test    al, 20h
0x140002b64  jz      short loc_140002B96
0x140002b66  mov     rcx, rbp; Irp
0x140002b69  call    cs:__imp_IoGetIoPriorityHint
0x140002b70  nop     dword ptr [rax+rax+00h]
0x140002b75  cmp     eax, 1
0x140002b78  jle     short loc_140002BDA
0x140002b7a  xor     r8d, r8d
0x140002b7d  mov     byte ptr [rbp+80h], 0
0x140002b84  mov     rdx, rbp
0x140002b87  mov     rcx, rsi
0x140002b8a  call    ServiceTransferRequest
0x140002b8f  mov     edi, eax
0x140002b91  jmp     loc_140002AB2
0x140002b96  movzx   ecx, byte ptr [rbx+282h]
0x140002b9d  mov     rax, [r14+18h]
0x140002ba1  sar     rax, cl
0x140002ba4  mov     ecx, 0FFFFFFFFh
0x140002ba9  cmp     rax, rcx
0x140002bac  jle     short loc_140002B66
0x140002bae  mov     edi, 0C000000Dh
0x140002bb3  mov     [rbp+30h], edi
0x140002bb6  xor     ebx, ebx
0x140002bb8  mov     rdx, rbp; Tag
0x140002bbb  mov     rcx, rsi; DeviceObject
0x140002bbe  mov     [rbp+38h], rbx
0x140002bc2  call    ClassReleaseRemoveLock
0x140002bc7  xor     r8d, r8d; PriorityBoost
0x140002bca  mov     rdx, rbp; Irp
0x140002bcd  mov     rcx, rsi; DeviceObject
0x140002bd0  call    ClassCompleteRequest
0x140002bd5  jmp     loc_140002AB2
0x140002bda  mov     eax, [r13+298h]
0x140002be1  test    al, 1
0x140002be3  jz      short loc_140002B7A
0x140002be5  test    byte ptr [r13+70h], 4
0x140002bea  jnz     short loc_140002B7A
0x140002bec  test    byte ptr [r13+11Ch], 4
0x140002bf4  jnz     short loc_140002B7A
0x140002bf6  mov     rdx, rbp
0x140002bf9  mov     byte ptr [rbp+80h], 1
0x140002c00  mov     rcx, rsi
0x140002c03  call    ClasspEnqueueIdleRequest
0x140002c08  mov     edi, eax
0x140002c0a  jmp     loc_140002AB2
0x140002c0f  mov     rax, [rdi+1B8h]
0x140002c16  lock inc dword ptr [rax]
0x140002c19  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c20  lea     rax, WPP_GLOBAL_Control
0x140002c27  cmp     rcx, rax
0x140002c2a  jz      loc_140002A2E
0x140002c30  test    dword ptr [rcx+2Ch], 200h
0x140002c37  jz      loc_140002A2E
0x140002c3d  cmp     byte ptr [rcx+29h], 5
0x140002c41  jb      loc_140002A2E
0x140002c47  mov     r9, [rdi+1B8h]
0x140002c4e  lea     r8, WPP_a22cc05f221e30b8049471910da99059_Traceguids
0x140002c55  mov     rcx, [rcx+18h]
0x140002c59  mov     edx, 0Eh
0x140002c5e  mov     r9d, [r9]
0x140002c61  call    WPP_SF_d
0x140002c66  jmp     loc_140002A2E
0x140002c6b  mov     edi, 0C00000C0h
0x140002c70  jmp     loc_140002BB3
0x140002c75  cmp     byte ptr [r14+1], 34h ; '4'
0x140002c7a  jz      loc_140002A43
0x140002c80  test    byte ptr [r14+2], 2
0x140002c85  jnz     loc_140002A43
0x140002c8b  cmp     qword ptr [rbp+98h], 0
0x140002c93  jz      loc_14003EE4E
0x140002c99  mov     rdx, rsi; DeviceObject
0x140002c9c  mov     rcx, rbp; Irp
0x140002c9f  call    cs:__imp_IoSetHardErrorOrVerifyDevice
0x140002ca6  nop     dword ptr [rax+rax+00h]
0x140002cab  nop
0x140002cac  jmp     loc_14003EE4E
0x140002cb1  xor     ebx, ebx
0x140002cb3  mov     rdx, rbp; Tag
0x140002cb6  mov     rcx, rsi; DeviceObject
0x140002cb9  mov     [rbp+30h], ebx
0x140002cbc  mov     [rbp+38h], rbx
0x140002cc0  call    ClassReleaseRemoveLock
0x140002cc5  xor     r8d, r8d; PriorityBoost
0x140002cc8  mov     rdx, rbp; Irp
0x140002ccb  mov     rcx, rsi; DeviceObject
0x140002cce  call    ClassCompleteRequest
0x140002cd3  mov     edi, ebx
0x140002cd5  jmp     loc_140002AB2
0x140002cda  mov     rax, [rbp+0B8h]
0x140002ce1  mov     rdx, rbp; Tag
0x140002ce4  mov     rcx, rsi; DeviceObject
0x140002ce7  movups  xmm0, xmmword ptr [rax]
0x140002cea  movups  xmmword ptr [rax-48h], xmm0
0x140002cee  movups  xmm1, xmmword ptr [rax+10h]
0x140002cf2  movups  xmmword ptr [rax-38h], xmm1
0x140002cf6  movups  xmm0, xmmword ptr [rax+20h]
0x140002cfa  movups  xmmword ptr [rax-28h], xmm0
0x140002cfe  movsd   xmm1, qword ptr [rax+30h]
0x140002d03  movsd   qword ptr [rax-18h], xmm1
0x140002d08  mov     byte ptr [rax-45h], 0
0x140002d0c  call    ClassReleaseRemoveLock
0x140002d11  mov     rdx, rbp; Irp
0x140002d14  mov     rcx, r12; DeviceObject
0x140002d17  call    cs:__imp_IofCallDriver
0x140002d1e  nop     dword ptr [rax+rax+00h]
0x140002d23  jmp     loc_140002B8F
0x14003ee4e  mov     edi, 80000016h
0x14003ee53  jmp     loc_140002BB3
```
