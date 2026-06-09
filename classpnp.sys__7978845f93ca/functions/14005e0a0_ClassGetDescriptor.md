# ClassGetDescriptor

- ea: `0x14005e0a0`
- end: `0x14005e2d3`
- name: `ClassGetDescriptor`
- size: `563`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PSTORAGE_PROPERTY_ID PropertyId, PVOID *Descriptor)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140030a20`
- `0x1400579b4`
- `0x140059500`
- `0x14005b8b8`

## callees

- `0x14001fbf4`
- `0x14003e430`
- `0x14005e0a0`
- `0x14005e2e0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005e1bc`
- `ntoskrnl!ExAllocatePool2` at `0x14005e1bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e29f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e29f`

## pseudocode

```c
NTSTATUS __stdcall ClassGetDescriptor(PDEVICE_OBJECT DeviceObject, PSTORAGE_PROPERTY_ID PropertyId, PVOID *Descriptor)
{
  NTSTATUS Status; // ebx
  ULONG OutputBufferLength; // edi
  _QWORD *Pool2; // rax
  void *v10; // rbx
  NTSTATUS v11; // edi
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+40h] [rbp-30h] BYREF
  enum _STORAGE_PROPERTY_ID Buffer; // [rsp+50h] [rbp-20h] BYREF
  __int64 Buffer_4; // [rsp+54h] [rbp-1Ch]

  *Descriptor = 0;
  Buffer = *PropertyId;
  Buffer_4 = 0;
  IoStatus = 0;
  ClassSendDeviceIoControlSynchronous(0x2D1400u, DeviceObject, &Buffer, 0xCu, 8u, 0, &IoStatus);
  Status = IoStatus.Status;
  if ( IoStatus.Status >= 0 )
  {
    if ( (_DWORD)Buffer_4 )
    {
      OutputBufferLength = 12;
      if ( (unsigned int)Buffer_4 > 0xC )
        OutputBufferLength = Buffer_4;
      Pool2 = (_QWORD *)ExAllocatePool2(64, OutputBufferLength, 876766035);
      v10 = Pool2;
      if ( Pool2 )
      {
        Buffer = *PropertyId;
        Buffer_4 = 0;
        *Pool2 = (unsigned int)Buffer;
        *((_DWORD *)Pool2 + 2) = HIDWORD(Buffer_4);
        ClassSendDeviceIoControlSynchronous(0x2D1400u, DeviceObject, Pool2, 0xCu, OutputBufferLength, 0, &IoStatus);
        v11 = IoStatus.Status;
        if ( IoStatus.Status >= 0 )
        {
          *Descriptor = v10;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              176,
              WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
              (unsigned int)IoStatus.Status);
          }
          ExFreePoolWithTag(v10, 0);
        }
        return v11;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            175,
            WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
            OutputBufferLength);
        }
        return -1073741670;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          174,
          WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
          (unsigned int)IoStatus.Status);
      }
      return -1073741823;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        173,
        WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
        (unsigned int)IoStatus.Status);
    }
    return Status;
  }
}

```

## disassembly

```asm
0x14005e0a0  mov     [rsp-28h+arg_18], rbx
0x14005e0a5  push    rbp
0x14005e0a6  push    rsi
0x14005e0a7  push    rdi
0x14005e0a8  push    r14
0x14005e0aa  push    r15
0x14005e0ac  mov     rbp, rsp
0x14005e0af  sub     rsp, 70h
0x14005e0b3  mov     rax, cs:__security_cookie
0x14005e0ba  xor     rax, rsp
0x14005e0bd  mov     [rbp+var_10], rax
0x14005e0c1  mov     qword ptr [r8], 0
0x14005e0c8  mov     r15, rdx
0x14005e0cb  mov     eax, [rdx]
0x14005e0cd  mov     rsi, r8
0x14005e0d0  mov     dword ptr [rbp+Buffer], eax
0x14005e0d3  lea     r8, [rbp+Buffer]; Buffer
0x14005e0d7  lea     rax, [rbp+var_30]
0x14005e0db  mov     [rbp+Buffer+4], 0
0x14005e0e3  mov     [rsp+70h+IoStatus], rax; IoStatus
0x14005e0e8  mov     r14, rcx
0x14005e0eb  xorps   xmm0, xmm0
0x14005e0ee  mov     [rsp+70h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x14005e0f3  mov     rdx, rcx; TargetDeviceObject
0x14005e0f6  mov     [rsp+70h+OutputBufferLength], 8; OutputBufferLength
0x14005e0fe  mov     r9d, 0Ch; InputBufferLength
0x14005e104  mov     ecx, 2D1400h; IoControlCode
0x14005e109  movups  xmmword ptr [rbp+var_30], xmm0
0x14005e10d  call    ClassSendDeviceIoControlSynchronous
0x14005e112  mov     ebx, dword ptr [rbp+var_30]
0x14005e115  test    ebx, ebx
0x14005e117  jns     short loc_14005E15A
0x14005e119  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e120  lea     rax, WPP_GLOBAL_Control
0x14005e127  cmp     rcx, rax
0x14005e12a  jz      short loc_14005E153
0x14005e12c  test    dword ptr [rcx+2Ch], 100h
0x14005e133  jz      short loc_14005E153
0x14005e135  cmp     byte ptr [rcx+29h], 2
0x14005e139  jb      short loc_14005E153
0x14005e13b  mov     rcx, [rcx+18h]
0x14005e13f  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x14005e146  mov     edx, 0ADh
0x14005e14b  mov     r9d, ebx
0x14005e14e  call    WPP_SF_d
0x14005e153  mov     eax, ebx
0x14005e155  jmp     loc_14005E2B2
0x14005e15a  mov     eax, dword ptr [rbp+Buffer+4]
0x14005e15d  test    eax, eax
0x14005e15f  jnz     short loc_14005E1A5
0x14005e161  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e168  lea     rax, WPP_GLOBAL_Control
0x14005e16f  cmp     rcx, rax
0x14005e172  jz      short loc_14005E19B
0x14005e174  test    dword ptr [rcx+2Ch], 100h
0x14005e17b  jz      short loc_14005E19B
0x14005e17d  cmp     byte ptr [rcx+29h], 2
0x14005e181  jb      short loc_14005E19B
0x14005e183  mov     rcx, [rcx+18h]
0x14005e187  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x14005e18e  mov     edx, 0AEh
0x14005e193  mov     r9d, ebx
0x14005e196  call    WPP_SF_d
0x14005e19b  mov     eax, 0C0000001h
0x14005e1a0  jmp     loc_14005E2B2
0x14005e1a5  mov     edi, 0Ch
0x14005e1aa  mov     ecx, 40h ; '@'
0x14005e1af  cmp     eax, edi
0x14005e1b1  mov     r8d, 34426353h
0x14005e1b7  cmova   edi, eax
0x14005e1ba  mov     edx, edi
0x14005e1bc  call    cs:__imp_ExAllocatePool2
0x14005e1c3  nop     dword ptr [rax+rax+00h]
0x14005e1c8  mov     rbx, rax
0x14005e1cb  test    rax, rax
0x14005e1ce  jnz     short loc_14005E214
0x14005e1d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e1d7  lea     rax, WPP_GLOBAL_Control
0x14005e1de  cmp     rcx, rax
0x14005e1e1  jz      short loc_14005E20A
0x14005e1e3  test    dword ptr [rcx+2Ch], 100h
0x14005e1ea  jz      short loc_14005E20A
0x14005e1ec  cmp     byte ptr [rcx+29h], 2
0x14005e1f0  jb      short loc_14005E20A
0x14005e1f2  mov     rcx, [rcx+18h]
0x14005e1f6  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x14005e1fd  mov     edx, 0AFh
0x14005e202  mov     r9d, edi
0x14005e205  call    WPP_SF_d
0x14005e20a  mov     eax, 0C000009Ah
0x14005e20f  jmp     loc_14005E2B2
0x14005e214  mov     eax, [r15]
0x14005e217  mov     r9d, 0Ch; InputBufferLength
0x14005e21d  mov     dword ptr [rbp+Buffer], eax
0x14005e220  mov     r8, rbx; Buffer
0x14005e223  mov     [rbp+Buffer+4], 0
0x14005e22b  mov     rdx, r14; TargetDeviceObject
0x14005e22e  movsd   xmm0, [rbp+Buffer]
0x14005e233  mov     ecx, 2D1400h; IoControlCode
0x14005e238  movsd   qword ptr [rbx], xmm0
0x14005e23c  mov     eax, [rbp+var_18]
0x14005e23f  mov     [rbx+8], eax
0x14005e242  lea     rax, [rbp+var_30]
0x14005e246  mov     [rsp+70h+IoStatus], rax; IoStatus
0x14005e24b  mov     [rsp+70h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x14005e250  mov     [rsp+70h+OutputBufferLength], edi; OutputBufferLength
0x14005e254  call    ClassSendDeviceIoControlSynchronous
0x14005e259  mov     edi, dword ptr [rbp+var_30]
0x14005e25c  test    edi, edi
0x14005e25e  jns     short loc_14005E2AD
0x14005e260  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e267  lea     rax, WPP_GLOBAL_Control
0x14005e26e  cmp     rcx, rax
0x14005e271  jz      short loc_14005E29A
0x14005e273  test    dword ptr [rcx+2Ch], 100h
0x14005e27a  jz      short loc_14005E29A
0x14005e27c  cmp     byte ptr [rcx+29h], 2
0x14005e280  jb      short loc_14005E29A
0x14005e282  mov     rcx, [rcx+18h]
0x14005e286  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x14005e28d  mov     edx, 0B0h
0x14005e292  mov     r9d, edi
0x14005e295  call    WPP_SF_d
0x14005e29a  xor     edx, edx; Tag
0x14005e29c  mov     rcx, rbx; P
0x14005e29f  call    cs:__imp_ExFreePoolWithTag
0x14005e2a6  nop     dword ptr [rax+rax+00h]
0x14005e2ab  jmp     short loc_14005E2B0
0x14005e2ad  mov     [rsi], rbx
0x14005e2b0  mov     eax, edi
0x14005e2b2  mov     rcx, [rbp+var_10]
0x14005e2b6  xor     rcx, rsp; StackCookie
0x14005e2b9  call    __security_check_cookie
0x14005e2be  mov     rbx, [rsp+70h+arg_18]
0x14005e2c6  add     rsp, 70h
0x14005e2ca  pop     r15
0x14005e2cc  pop     r14
0x14005e2ce  pop     rdi
0x14005e2cf  pop     rsi
0x14005e2d0  pop     rbp
0x14005e2d1  retn
```
