# DiskFlushComplete

- ea: `0x1400019d0`
- end: `0x140001d8d`
- name: `DiskFlushComplete`
- size: `957`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400019d0`
- `0x1400022b0`
- `0x1400034a0`
- `0x140004078`
- `0x1400040a8`
- `0x1400042c0`
- `0x14000431c`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140001d12`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140001d12`
- `ntoskrnl!KeSetEvent` at `0x140001bc4`
- `ntoskrnl!KeSetEvent` at `0x140001bc4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001ac6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001ba0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001ca7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001ac6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001ba0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001ca7`
- `ntoskrnl!IoGetStackLimits` at `0x140001ccd`
- `ntoskrnl!IoGetStackLimits` at `0x140001ccd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001a6b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001a6b`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x140001b6f`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x140001b6f`
- `CLASSPNP!ClassCompleteRequest` at `0x140001b84`
- `CLASSPNP!ClassCompleteRequest` at `0x140001b84`
- `CLASSPNP!ClassIoComplete` at `0x140001a36`
- `CLASSPNP!ClassIoComplete` at `0x140001a36`

## pseudocode

```c
__int64 __fastcall DiskFlushComplete(PDEVICE_OBJECT DeviceObject, PIRP Irp, NTSTATUS a3)
{
  __int64 v6; // rbx
  NTSTATUS v7; // esi
  _QWORD *v8; // rax
  KIRQL v9; // al
  KIRQL v10; // r14
  __int64 **v11; // rax
  __int64 *v12; // rcx
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 *v16; // rdx
  __int64 **v17; // rdx
  __int64 v18; // rcx
  IRP *v19; // rdi
  NTSTATUS v20; // eax
  unsigned __int64 HighLimit; // [rsp+30h] [rbp-48h] BYREF
  _QWORD Parameter[8]; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int64 LowLimit; // [rsp+80h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      30,
      WPP_0d021951613e35be7880fae860fb7f50_Traceguids,
      DeviceObject,
      Irp);
  }
  v6 = *((_QWORD *)DeviceObject->DeviceExtension + 12) + 112LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_0d021951613e35be7880fae860fb7f50_Traceguids, Irp);
  }
  v7 = ClassIoComplete(DeviceObject, Irp, (PVOID)(v6 + 48));
  if ( v7 >= 0 && a3 < 0 )
  {
    v7 = a3;
    Irp->IoStatus.Status = a3;
  }
  while ( 1 )
  {
    v8 = *(_QWORD **)v6;
    if ( *(_QWORD *)v6 == v6 )
      break;
    if ( v8[1] != v6 || (v18 = *v8, *(_QWORD **)(*v8 + 8LL) != v8) )
LABEL_20:
      __fastfail(3u);
    *(_QWORD *)v6 = v18;
    v19 = (IRP *)(v8 - 21);
    *(_QWORD *)(v18 + 8) = v6;
    v8[1] = v8;
    *v8 = v8;
    *(_OWORD *)(v8 - 15) = *(_OWORD *)&Irp->IoStatus.Status;
    ClassReleaseRemoveLock(DeviceObject, v8 - 21);
    ClassCompleteRequest(DeviceObject, v19, 0);
  }
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 360));
  v10 = v9;
  if ( *(_BYTE *)(v6 + 400) )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 360), v9);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    KeSetEvent((PRKEVENT)(v6 + 368), 0, 0);
  }
  else
  {
    v11 = (__int64 **)(v6 + 24);
    while ( 1 )
    {
      v12 = *v11;
      if ( *v11 == (__int64 *)v11 )
        break;
      if ( (__int64 **)v12[1] != v11 )
        goto LABEL_20;
      v16 = (__int64 *)*v12;
      if ( *(__int64 **)(*v12 + 8) != v12 )
        goto LABEL_20;
      *v11 = v16;
      v16[1] = (__int64)v11;
      v17 = *(__int64 ***)(v6 + 8);
      if ( *v17 != (__int64 *)v6 )
        goto LABEL_20;
      *v12 = v6;
      v12[1] = (__int64)v17;
      *v17 = v12;
      *(_QWORD *)(v6 + 8) = v12;
    }
    v13 = *(_QWORD *)(v6 + 40);
    *(_QWORD *)(v6 + 16) = v13;
    *(_QWORD *)(v6 + 40) = 0;
    *(_BYTE *)(v6 + 400) = 0;
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_0d021951613e35be7880fae860fb7f50_Traceguids, v13);
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 360), v10);
      HighLimit = 0;
      LowLimit = 0;
      IoGetStackLimits(&LowLimit, &HighLimit);
      if ( (unsigned __int64)&Parameter[-1] - LowLimit < 0x3000 )
      {
        Parameter[0] = DeviceObject;
        Parameter[1] = v6;
        v20 = KeExpandKernelStackAndCalloutEx(DiskFlushDispatchAsyncCallout, Parameter, 0x3000u, 0, 0);
        if ( v20 >= 0 )
          goto LABEL_14;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            34,
            WPP_0d021951613e35be7880fae860fb7f50_Traceguids,
            (unsigned int)v20);
        }
      }
      DiskFlushDispatchAsync(DeviceObject);
      goto LABEL_14;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 360), v10);
  }
LABEL_14:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 35, v14, Irp, v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400019d0  mov     [rsp+arg_18], rbx
0x1400019d5  push    rbp
0x1400019d6  push    rsi
0x1400019d7  push    rdi
0x1400019d8  push    r12
0x1400019da  push    r15
0x1400019dc  sub     rsp, 50h
0x1400019e0  mov     rdi, r8
0x1400019e3  mov     r15, rdx
0x1400019e6  mov     rbp, rcx
0x1400019e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400019f0  lea     r12, WPP_GLOBAL_Control
0x1400019f7  cmp     rcx, r12
0x1400019fa  jz      short loc_140001A07
0x1400019fc  mov     eax, [rcx+2Ch]
0x1400019ff  test    al, 1
0x140001a01  jnz     loc_140001C0E
0x140001a07  mov     rbx, [rbp+40h]
0x140001a0b  mov     rbx, [rbx+60h]
0x140001a0f  add     rbx, 70h ; 'p'
0x140001a13  mov     rcx, cs:WPP_GLOBAL_Control
0x140001a1a  cmp     rcx, r12
0x140001a1d  jz      short loc_140001A2C
0x140001a1f  test    dword ptr [rcx+2Ch], 20000h
0x140001a26  jnz     loc_140001C3A
0x140001a2c  lea     r8, [rbx+30h]; Context
0x140001a30  mov     rdx, r15; Irp
0x140001a33  mov     rcx, rbp; DeviceObject
0x140001a36  call    cs:__imp_ClassIoComplete
0x140001a3d  nop     dword ptr [rax+rax+00h]
0x140001a42  mov     esi, eax
0x140001a44  test    eax, eax
0x140001a46  js      short loc_140001A50
0x140001a48  test    edi, edi
0x140001a4a  js      loc_140001C61
0x140001a50  mov     [rsp+78h+arg_10], r14
0x140001a58  mov     rax, [rbx]
0x140001a5b  cmp     rax, rbx
0x140001a5e  jnz     loc_140001B3C
0x140001a64  lea     rcx, [rbx+168h]; SpinLock
0x140001a6b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001a72  nop     dword ptr [rax+rax+00h]
0x140001a77  cmp     byte ptr [rbx+190h], 0
0x140001a7e  movzx   r14d, al
0x140001a82  jnz     loc_140001B95
0x140001a88  lea     rax, [rbx+18h]
0x140001a8c  mov     rcx, [rax]
0x140001a8f  cmp     rcx, rax
0x140001a92  jnz     short loc_140001B12
0x140001a94  mov     r9, [rbx+28h]
0x140001a98  mov     [rsp+78h+arg_8], r13
0x140001aa0  xor     r13d, r13d
0x140001aa3  mov     [rbx+10h], r9
0x140001aa7  mov     [rbx+28h], r13
0x140001aab  mov     [rbx+190h], r13b
0x140001ab2  test    r9, r9
0x140001ab5  jnz     loc_140001C6C
0x140001abb  movzx   edx, r14b; NewIrql
0x140001abf  lea     rcx, [rbx+168h]; SpinLock
0x140001ac6  call    cs:__imp_KeReleaseSpinLock
0x140001acd  nop     dword ptr [rax+rax+00h]
0x140001ad2  mov     r13, [rsp+78h+arg_8]
0x140001ada  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ae1  cmp     rcx, r12
0x140001ae4  jz      short loc_140001AF3
0x140001ae6  test    dword ptr [rcx+2Ch], 20000h
0x140001aed  jnz     loc_140001D69
0x140001af3  mov     r14, [rsp+78h+arg_10]
0x140001afb  mov     eax, esi
0x140001afd  mov     rbx, [rsp+78h+arg_18]
0x140001b05  add     rsp, 50h
0x140001b09  pop     r15
0x140001b0b  pop     r12
0x140001b0d  pop     rdi
0x140001b0e  pop     rsi
0x140001b0f  pop     rbp
0x140001b10  retn
0x140001b12  cmp     [rcx+8], rax
0x140001b16  jnz     short loc_140001B35
0x140001b18  mov     rdx, [rcx]
0x140001b1b  cmp     [rdx+8], rcx
0x140001b1f  jnz     short loc_140001B35
0x140001b21  mov     [rax], rdx
0x140001b24  mov     [rdx+8], rax
0x140001b28  mov     rdx, [rbx+8]
0x140001b2c  cmp     [rdx], rbx
0x140001b2f  jz      loc_140001BFB
0x140001b35  mov     ecx, 3
0x140001b3a  int     29h; Win8: RtlFailFast(ecx)
0x140001b3c  cmp     [rax+8], rbx
0x140001b40  jnz     short loc_140001B35
0x140001b42  mov     rcx, [rax]
0x140001b45  cmp     [rcx+8], rax
0x140001b49  jnz     short loc_140001B35
0x140001b4b  mov     [rbx], rcx
0x140001b4e  lea     rdi, [rax-0A8h]
0x140001b55  mov     [rcx+8], rbx
0x140001b59  mov     rdx, rdi; Tag
0x140001b5c  mov     [rax+8], rax
0x140001b60  mov     rcx, rbp; DeviceObject
0x140001b63  mov     [rax], rax
0x140001b66  movups  xmm0, xmmword ptr [r15+30h]
0x140001b6b  movups  xmmword ptr [rdi+30h], xmm0
0x140001b6f  call    cs:__imp_ClassReleaseRemoveLock
0x140001b76  nop     dword ptr [rax+rax+00h]
0x140001b7b  xor     r8d, r8d; PriorityBoost
0x140001b7e  mov     rdx, rdi; Irp
0x140001b81  mov     rcx, rbp; DeviceObject
0x140001b84  call    cs:__imp_ClassCompleteRequest
0x140001b8b  nop     dword ptr [rax+rax+00h]
0x140001b90  jmp     loc_140001A58
0x140001b95  movzx   edx, r14b; NewIrql
0x140001b99  lea     rcx, [rbx+168h]; SpinLock
0x140001ba0  call    cs:__imp_KeReleaseSpinLock
0x140001ba7  nop     dword ptr [rax+rax+00h]
0x140001bac  mov     rcx, cs:WPP_GLOBAL_Control
0x140001bb3  cmp     rcx, r12
0x140001bb6  jnz     short loc_140001BD5
0x140001bb8  lea     rcx, [rbx+170h]; Event
0x140001bbf  xor     r8d, r8d; Wait
0x140001bc2  xor     edx, edx; Increment
0x140001bc4  call    cs:__imp_KeSetEvent
0x140001bcb  nop     dword ptr [rax+rax+00h]
0x140001bd0  jmp     loc_140001ADA
0x140001bd5  test    dword ptr [rcx+2Ch], 20000h
0x140001bdc  jz      short loc_140001BB8
0x140001bde  cmp     byte ptr [rcx+29h], 5
0x140001be2  jb      short loc_140001BB8
0x140001be4  mov     rcx, [rcx+18h]
0x140001be8  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140001bef  mov     edx, 20h ; ' '
0x140001bf4  call    WPP_SF_
0x140001bf9  jmp     short loc_140001BB8
0x140001bfb  mov     [rcx], rbx
0x140001bfe  mov     [rcx+8], rdx
0x140001c02  mov     [rdx], rcx
0x140001c05  mov     [rbx+8], rcx
0x140001c09  jmp     loc_140001A8C
0x140001c0e  cmp     byte ptr [rcx+29h], 5
0x140001c12  jb      loc_140001A07
0x140001c18  mov     rcx, [rcx+18h]
0x140001c1c  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140001c23  mov     edx, 1Eh
0x140001c28  mov     [rsp+78h+Context], r15
0x140001c2d  mov     r9, rbp
0x140001c30  call    WPP_SF_qq
0x140001c35  jmp     loc_140001A07
0x140001c3a  cmp     byte ptr [rcx+29h], 5
0x140001c3e  jb      loc_140001A2C
0x140001c44  mov     rcx, [rcx+18h]
0x140001c48  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140001c4f  mov     edx, 1Fh
0x140001c54  mov     r9, r15
0x140001c57  call    WPP_SF_q
0x140001c5c  jmp     loc_140001A2C
0x140001c61  mov     esi, edi
0x140001c63  mov     [r15+30h], edi
0x140001c67  jmp     loc_140001A50
0x140001c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c73  cmp     rcx, r12
0x140001c76  jz      short loc_140001C9C
0x140001c78  test    dword ptr [rcx+2Ch], 20000h
0x140001c7f  jz      short loc_140001C9C
0x140001c81  cmp     byte ptr [rcx+29h], 5
0x140001c85  jb      short loc_140001C9C
0x140001c87  mov     rcx, [rcx+18h]
0x140001c8b  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140001c92  mov     edx, 21h ; '!'
0x140001c97  call    WPP_SF_q
0x140001c9c  movzx   edx, r14b; NewIrql
0x140001ca0  lea     rcx, [rbx+168h]; SpinLock
0x140001ca7  call    cs:__imp_KeReleaseSpinLock
0x140001cae  nop     dword ptr [rax+rax+00h]
0x140001cb3  lea     rdx, [rsp+78h+HighLimit]; HighLimit
0x140001cb8  mov     [rsp+78h+HighLimit], r13
0x140001cbd  lea     rcx, [rsp+78h+LowLimit]; LowLimit
0x140001cc5  mov     [rsp+78h+LowLimit], r13
0x140001ccd  call    cs:__imp_IoGetStackLimits
0x140001cd4  nop     dword ptr [rax+rax+00h]
0x140001cd9  lea     rax, [rsp+78h+HighLimit]
0x140001cde  sub     rax, [rsp+78h+LowLimit]
0x140001ce6  cmp     rax, 3000h
0x140001cec  jnb     short loc_140001D59
0x140001cee  xor     r9d, r9d; Wait
0x140001cf1  mov     [rsp+78h+Parameter], rbp
0x140001cf6  mov     r8d, 3000h; Size
0x140001cfc  mov     [rsp+78h+var_38], rbx
0x140001d01  lea     rdx, [rsp+78h+Parameter]; Parameter
0x140001d06  mov     [rsp+78h+Context], r13; Context
0x140001d0b  lea     rcx, DiskFlushDispatchAsyncCallout; Callout
0x140001d12  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x140001d19  nop     dword ptr [rax+rax+00h]
0x140001d1e  test    eax, eax
0x140001d20  jns     loc_140001AD2
0x140001d26  mov     rcx, cs:WPP_GLOBAL_Control
0x140001d2d  cmp     rcx, r12
0x140001d30  jz      short loc_140001D59
0x140001d32  test    dword ptr [rcx+2Ch], 20000h
0x140001d39  jz      short loc_140001D59
0x140001d3b  cmp     byte ptr [rcx+29h], 5
0x140001d3f  jb      short loc_140001D59
0x140001d41  mov     rcx, [rcx+18h]
0x140001d45  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140001d4c  mov     edx, 22h ; '"'
0x140001d51  mov     r9d, eax
0x140001d54  call    WPP_SF_D
0x140001d59  mov     rdx, rbx
0x140001d5c  mov     rcx, rbp; DeviceObject
0x140001d5f  call    DiskFlushDispatchAsync
0x140001d64  jmp     loc_140001AD2
0x140001d69  cmp     byte ptr [rcx+29h], 5
0x140001d6d  jb      loc_140001AF3
0x140001d73  mov     rcx, [rcx+18h]
0x140001d77  mov     edx, 23h ; '#'
0x140001d7c  mov     r9, r15
0x140001d7f  mov     dword ptr [rsp+78h+Context], esi
0x140001d83  call    WPP_SF_qD
0x140001d88  jmp     loc_140001AF3
```
