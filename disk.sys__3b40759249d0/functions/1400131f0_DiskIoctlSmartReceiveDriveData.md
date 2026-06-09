# DiskIoctlSmartReceiveDriveData

- ea: `0x1400131f0`
- end: `0x140013659`
- name: `DiskIoctlSmartReceiveDriveData`
- size: `1129`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400014a0`

## callees

- `0x140004078`
- `0x14000431c`
- `0x140005d00`
- `0x1400131f0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140013615`
- `ntoskrnl!KeWaitForSingleObject` at `0x140013615`
- `ntoskrnl!KeInitializeEvent` at `0x14001328f`
- `ntoskrnl!KeInitializeEvent` at `0x14001328f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013379`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400133f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013379`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400133f4`
- `ntoskrnl!IofCallDriver` at `0x1400133b9`
- `ntoskrnl!IofCallDriver` at `0x1400133b9`
- `ntoskrnl!ExAllocatePool2` at `0x1400132c4`
- `ntoskrnl!ExAllocatePool2` at `0x1400132c4`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140013353`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140013353`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013233`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013233`

## pseudocode

```c
__int64 __fastcall DiskIoctlSmartReceiveDriveData(__int64 a1, __int64 a2)
{
  __int64 v2; // rbp
  __int64 v3; // rbx
  unsigned __int8 *v4; // r14
  __int64 v7; // r13
  unsigned __int8 v8; // al
  int v9; // r15d
  unsigned int v10; // esi
  __int64 Pool2; // rax
  __int64 OutputBuffer; // rbx
  IRP *v13; // rax
  NTSTATUS Status; // ebp
  __int64 v16; // rsi
  size_t v17; // r8
  int v18; // ecx
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  int v23; // ecx
  int v24; // esi
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-58h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-48h] BYREF

  v2 = *(_QWORD *)(a1 + 64);
  v3 = *(_QWORD *)(a2 + 184);
  v4 = *(unsigned __int8 **)(a2 + 24);
  v7 = *(_QWORD *)(v2 + 96);
  IoStatusBlock = 0;
  memset(&Event, 0, sizeof(Event));
  if ( KeGetCurrentIrql() >= 2u )
    return 3221225800LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_0d021951613e35be7880fae860fb7f50_Traceguids, a1, a2);
  }
  if ( *(_DWORD *)(v3 + 16) < 0x20u )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return 3221225485LL;
    }
    v20 = 104;
LABEL_64:
    WPP_SF_(v19->AttachedDevice, v20, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    return 3221225485LL;
  }
  if ( *(_DWORD *)(v3 + 8) < 0x210u )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return 3221225507LL;
    }
    v22 = 105;
    goto LABEL_49;
  }
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v8 = v4[10];
  if ( v8 == 0xEC )
  {
    v9 = 1770753;
LABEL_7:
    v10 = 529;
    goto LABEL_8;
  }
  if ( v8 != 0xB0 )
    goto LABEL_24;
  v18 = v4[4];
  if ( v18 == 208 )
  {
    v9 = 1770754;
    goto LABEL_7;
  }
  v23 = v18 - 209;
  if ( !v23 )
  {
    v9 = 1770755;
    goto LABEL_7;
  }
  if ( v23 != 4 )
  {
LABEL_24:
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return 3221225485LL;
    }
    v20 = 108;
    goto LABEL_64;
  }
  if ( *(_DWORD *)(v7 + 16) == 2 )
  {
    v24 = v4[5] << 9;
    if ( v24 )
    {
      v10 = v24 + 33;
      if ( *(_DWORD *)(v3 + 8) >= v10 - 1 )
      {
        v9 = 1770763;
LABEL_8:
        Pool2 = ExAllocatePool2(64, v10 + 28LL, 1631871827);
        OutputBuffer = Pool2;
        if ( Pool2 )
        {
          *(_DWORD *)Pool2 = 28;
          *(_QWORD *)(Pool2 + 4) = 0x4B53494449534353LL;
          *(_DWORD *)(Pool2 + 12) = *(_DWORD *)(v2 + 584);
          *(_DWORD *)(Pool2 + 24) = v10;
          *(_DWORD *)(Pool2 + 16) = v9;
          v4[12] = *(_BYTE *)(v7 + 14);
          memmove((void *)(Pool2 + 28), *(const void **)(a2 + 24), 0x20u);
          v13 = IoBuildDeviceIoControlRequest(
                  0x4D008u,
                  *(PDEVICE_OBJECT *)(v2 + 16),
                  (PVOID)OutputBuffer,
                  0x3Cu,
                  (PVOID)OutputBuffer,
                  v10 + 28,
                  0,
                  &Event,
                  &IoStatusBlock);
          if ( v13 )
          {
            Status = IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 16), v13);
            if ( Status == 259 )
            {
              KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
              Status = IoStatusBlock.Status;
            }
            if ( Status < 0 )
            {
              v16 = 16;
              v17 = 16;
            }
            else
            {
              v16 = v10 - 1;
              v17 = v16;
            }
            memmove(*(void **)(a2 + 24), (const void *)(OutputBuffer + 28), v17);
            *(_QWORD *)(a2 + 56) = v16;
            ExFreePoolWithTag((PVOID)OutputBuffer, 0);
            return (unsigned int)Status;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 110, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
            }
            ExFreePoolWithTag((PVOID)OutputBuffer, 0);
            return 3221225626LL;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 109, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
          }
          return 3221225626LL;
        }
      }
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return 3221225507LL;
      }
      v22 = 107;
LABEL_49:
      WPP_SF_(v21->AttachedDevice, v22, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
      return 3221225507LL;
    }
    return 3221225485LL;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
  }
  return 3221225488LL;
}

```

## disassembly

```asm
0x1400131f0  mov     [rsp+arg_10], rbx
0x1400131f5  push    rbp
0x1400131f6  push    rsi
0x1400131f7  push    rdi
0x1400131f8  push    r13
0x1400131fa  push    r14
0x1400131fc  sub     rsp, 80h
0x140013203  mov     rbp, [rcx+40h]
0x140013207  xorps   xmm0, xmm0
0x14001320a  mov     rbx, [rdx+0B8h]
0x140013211  xorps   xmm1, xmm1
0x140013214  mov     r14, [rdx+18h]
0x140013218  xor     eax, eax
0x14001321a  mov     rdi, rdx
0x14001321d  mov     rsi, rcx
0x140013220  mov     r13, [rbp+60h]
0x140013224  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x140013229  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rax
0x14001322e  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm1
0x140013233  call    cs:__imp_KeGetCurrentIrql
0x14001323a  nop     dword ptr [rax+rax+00h]
0x14001323f  cmp     al, 2
0x140013241  jnb     loc_14001347F
0x140013247  mov     rcx, cs:WPP_GLOBAL_Control
0x14001324e  mov     [rsp+0A8h+arg_0], r12
0x140013256  lea     r12, WPP_GLOBAL_Control
0x14001325d  cmp     rcx, r12
0x140013260  jnz     loc_14001342E
0x140013266  cmp     dword ptr [rbx+10h], 20h ; ' '
0x14001326a  mov     [rsp+0A8h+arg_8], r15
0x140013272  jb      loc_140013489
0x140013278  cmp     dword ptr [rbx+8], 210h
0x14001327f  jb      loc_1400134AC
0x140013285  xor     r8d, r8d; State
0x140013288  lea     rcx, [rsp+0A8h+Event]; Event
0x14001328d  xor     edx, edx; Type
0x14001328f  call    cs:__imp_KeInitializeEvent
0x140013296  nop     dword ptr [rax+rax+00h]
0x14001329b  movzx   eax, byte ptr [r14+0Ah]
0x1400132a0  cmp     al, 0ECh
0x1400132a2  jnz     loc_14001340E
0x1400132a8  mov     r15d, 1B0501h
0x1400132ae  mov     esi, 211h
0x1400132b3  mov     edx, esi
0x1400132b5  mov     ecx, 40h ; '@'
0x1400132ba  add     rdx, 1Ch
0x1400132be  mov     r8d, 61446353h
0x1400132c4  call    cs:__imp_ExAllocatePool2
0x1400132cb  nop     dword ptr [rax+rax+00h]
0x1400132d0  mov     rbx, rax
0x1400132d3  test    rax, rax
0x1400132d6  jz      loc_140013598
0x1400132dc  mov     dword ptr [rax], 1Ch
0x1400132e2  lea     rcx, [rbx+1Ch]; void *
0x1400132e6  mov     rax, 4B53494449534353h
0x1400132f0  mov     r8d, 20h ; ' '; Size
0x1400132f6  mov     [rbx+4], rax
0x1400132fa  mov     eax, [rbp+248h]
0x140013300  mov     [rbx+0Ch], eax
0x140013303  mov     [rbx+18h], esi
0x140013306  mov     [rbx+10h], r15d
0x14001330a  movzx   eax, byte ptr [r13+0Eh]
0x14001330f  mov     [r14+0Ch], al
0x140013313  mov     rdx, [rdi+18h]; Src
0x140013317  call    memmove
0x14001331c  mov     rdx, [rbp+10h]; DeviceObject
0x140013320  lea     rcx, [rsp+0A8h+var_58]
0x140013325  mov     [rsp+0A8h+IoStatusBlock], rcx; IoStatusBlock
0x14001332a  lea     eax, [rsi+1Ch]
0x14001332d  lea     rcx, [rsp+0A8h+Event]
0x140013332  mov     r9d, 3Ch ; '<'; InputBufferLength
0x140013338  mov     [rsp+0A8h+var_70], rcx; Event
0x14001333d  mov     r8, rbx; InputBuffer
0x140013340  mov     [rsp+0A8h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x140013345  mov     ecx, 4D008h; IoControlCode
0x14001334a  mov     [rsp+0A8h+OutputBufferLength], eax; OutputBufferLength
0x14001334e  mov     [rsp+0A8h+OutputBuffer], rbx; OutputBuffer
0x140013353  call    cs:__imp_IoBuildDeviceIoControlRequest
0x14001335a  nop     dword ptr [rax+rax+00h]
0x14001335f  test    rax, rax
0x140013362  jnz     short loc_1400133B2
0x140013364  mov     rcx, cs:WPP_GLOBAL_Control
0x14001336b  cmp     rcx, r12
0x14001336e  jnz     loc_1400135D0
0x140013374  xor     edx, edx; Tag
0x140013376  mov     rcx, rbx; P
0x140013379  call    cs:__imp_ExFreePoolWithTag
0x140013380  nop     dword ptr [rax+rax+00h]
0x140013385  mov     eax, 0C000009Ah
0x14001338a  mov     r15, [rsp+0A8h+arg_8]
0x140013392  mov     r12, [rsp+0A8h+arg_0]
0x14001339a  mov     rbx, [rsp+0A8h+arg_10]
0x1400133a2  add     rsp, 80h
0x1400133a9  pop     r14
0x1400133ab  pop     r13
0x1400133ad  pop     rdi
0x1400133ae  pop     rsi
0x1400133af  pop     rbp
0x1400133b0  retn
0x1400133b2  mov     rcx, [rbp+10h]; DeviceObject
0x1400133b6  mov     rdx, rax; Irp
0x1400133b9  call    cs:__imp_IofCallDriver
0x1400133c0  nop     dword ptr [rax+rax+00h]
0x1400133c5  mov     ebp, eax
0x1400133c7  cmp     eax, 103h
0x1400133cc  jz      loc_1400135FF
0x1400133d2  mov     rcx, [rdi+18h]; void *
0x1400133d6  lea     rdx, [rbx+1Ch]; Src
0x1400133da  test    ebp, ebp
0x1400133dc  js      short loc_140013404
0x1400133de  lea     eax, [rsi-1]
0x1400133e1  mov     esi, eax
0x1400133e3  mov     r8d, eax; Size
0x1400133e6  call    memmove
0x1400133eb  xor     edx, edx; Tag
0x1400133ed  mov     [rdi+38h], rsi
0x1400133f1  mov     rcx, rbx; P
0x1400133f4  call    cs:__imp_ExFreePoolWithTag
0x1400133fb  nop     dword ptr [rax+rax+00h]
0x140013400  mov     eax, ebp
0x140013402  jmp     short loc_14001338A
0x140013404  mov     esi, 10h
0x140013409  mov     r8d, esi
0x14001340c  jmp     short loc_1400133E6
0x14001340e  cmp     al, 0B0h
0x140013410  jnz     short loc_140013465
0x140013412  movzx   ecx, byte ptr [r14+4]
0x140013417  cmp     ecx, 0D0h
0x14001341d  jnz     loc_1400134DB
0x140013423  mov     r15d, 1B0502h
0x140013429  jmp     loc_1400132AE
0x14001342e  mov     eax, [rcx+2Ch]
0x140013431  test    al, 10h
0x140013433  jz      loc_140013266
0x140013439  cmp     byte ptr [rcx+29h], 4
0x14001343d  jb      loc_140013266
0x140013443  mov     rcx, [rcx+18h]
0x140013447  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14001344e  mov     edx, 67h ; 'g'
0x140013453  mov     [rsp+0A8h+OutputBuffer], rdi
0x140013458  mov     r9, rsi
0x14001345b  call    WPP_SF_qq
0x140013460  jmp     loc_140013266
0x140013465  mov     rcx, cs:WPP_GLOBAL_Control
0x14001346c  cmp     rcx, r12
0x14001346f  jnz     loc_14001362A
0x140013475  mov     eax, 0C000000Dh
0x14001347a  jmp     loc_14001338A
0x14001347f  mov     eax, 0C0000148h
0x140013484  jmp     loc_14001339A
0x140013489  mov     rcx, cs:WPP_GLOBAL_Control
0x140013490  cmp     rcx, r12
0x140013493  jz      short loc_140013475
0x140013495  mov     eax, [rcx+2Ch]
0x140013498  test    al, 10h
0x14001349a  jz      short loc_140013475
0x14001349c  cmp     byte ptr [rcx+29h], 2
0x1400134a0  jb      short loc_140013475
0x1400134a2  mov     edx, 68h ; 'h'
0x1400134a7  jmp     loc_140013644
0x1400134ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400134b3  cmp     rcx, r12
0x1400134b6  jz      loc_140013578
0x1400134bc  mov     eax, [rcx+2Ch]
0x1400134bf  test    al, 10h
0x1400134c1  jz      loc_140013578
0x1400134c7  cmp     byte ptr [rcx+29h], 2
0x1400134cb  jb      loc_140013578
0x1400134d1  mov     edx, 69h ; 'i'
0x1400134d6  jmp     loc_140013568
0x1400134db  sub     ecx, 0D1h
0x1400134e1  jz      loc_14001358D
0x1400134e7  cmp     ecx, 4
0x1400134ea  jnz     loc_140013465
0x1400134f0  cmp     dword ptr [r13+10h], 2
0x1400134f5  jz      short loc_14001352F
0x1400134f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400134fe  cmp     rcx, r12
0x140013501  jz      short loc_140013525
0x140013503  mov     eax, [rcx+2Ch]
0x140013506  test    al, 10h
0x140013508  jz      short loc_140013525
0x14001350a  cmp     byte ptr [rcx+29h], 2
0x14001350e  jb      short loc_140013525
0x140013510  mov     rcx, [rcx+18h]
0x140013514  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14001351b  mov     edx, 6Ah ; 'j'
0x140013520  call    WPP_SF_
0x140013525  mov     eax, 0C0000010h
0x14001352a  jmp     loc_14001338A
0x14001352f  movzx   esi, byte ptr [r14+5]
0x140013534  shl     esi, 9
0x140013537  test    esi, esi
0x140013539  jz      loc_140013475
0x14001353f  add     esi, 21h ; '!'
0x140013542  lea     eax, [rsi-1]
0x140013545  cmp     [rbx+8], eax
0x140013548  jnb     short loc_140013582
0x14001354a  mov     rcx, cs:WPP_GLOBAL_Control
0x140013551  cmp     rcx, r12
0x140013554  jz      short loc_140013578
0x140013556  mov     eax, [rcx+2Ch]
0x140013559  test    al, 10h
0x14001355b  jz      short loc_140013578
0x14001355d  cmp     byte ptr [rcx+29h], 2
0x140013561  jb      short loc_140013578
0x140013563  mov     edx, 6Bh ; 'k'
0x140013568  mov     rcx, [rcx+18h]
0x14001356c  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140013573  call    WPP_SF_
0x140013578  mov     eax, 0C0000023h
0x14001357d  jmp     loc_14001338A
0x140013582  mov     r15d, 1B050Bh
0x140013588  jmp     loc_1400132B3
0x14001358d  mov     r15d, 1B0503h
0x140013593  jmp     loc_1400132AE
0x140013598  mov     rcx, cs:WPP_GLOBAL_Control
0x14001359f  cmp     rcx, r12
0x1400135a2  jz      short loc_1400135C6
0x1400135a4  mov     eax, [rcx+2Ch]
0x1400135a7  test    al, 10h
0x1400135a9  jz      short loc_1400135C6
0x1400135ab  cmp     byte ptr [rcx+29h], 2
0x1400135af  jb      short loc_1400135C6
0x1400135b1  mov     rcx, [rcx+18h]
0x1400135b5  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x1400135bc  mov     edx, 6Dh ; 'm'
0x1400135c1  call    WPP_SF_
0x1400135c6  mov     eax, 0C000009Ah
0x1400135cb  jmp     loc_14001338A
0x1400135d0  mov     eax, [rcx+2Ch]
0x1400135d3  test    al, 10h
0x1400135d5  jz      loc_140013374
0x1400135db  cmp     byte ptr [rcx+29h], 2
0x1400135df  jb      loc_140013374
0x1400135e5  mov     rcx, [rcx+18h]
0x1400135e9  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x1400135f0  mov     edx, 6Eh ; 'n'
0x1400135f5  call    WPP_SF_
0x1400135fa  jmp     loc_140013374
0x1400135ff  xor     r9d, r9d; Alertable
0x140013602  mov     [rsp+0A8h+OutputBuffer], 0; Timeout
0x14001360b  xor     r8d, r8d; WaitMode
0x14001360e  lea     rcx, [rsp+0A8h+Event]; Object
0x140013613  xor     edx, edx; WaitReason
0x140013615  call    cs:__imp_KeWaitForSingleObject
0x14001361c  nop     dword ptr [rax+rax+00h]
0x140013621  mov     ebp, dword ptr [rsp+0A8h+var_58]
0x140013625  jmp     loc_1400133D2
0x14001362a  mov     eax, [rcx+2Ch]
0x14001362d  test    al, 10h
0x14001362f  jz      loc_140013475
0x140013635  cmp     byte ptr [rcx+29h], 2
0x140013639  jb      loc_140013475
0x14001363f  mov     edx, 6Ch ; 'l'
0x140013644  mov     rcx, [rcx+18h]
0x140013648  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14001364f  call    WPP_SF_
0x140013654  jmp     loc_140013475
```
