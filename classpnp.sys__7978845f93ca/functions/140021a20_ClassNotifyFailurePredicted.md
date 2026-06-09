# ClassNotifyFailurePredicted

- ea: `0x140021a20`
- end: `0x140021b9d`
- name: `ClassNotifyFailurePredicted`
- size: `381`
- prototype: `void __stdcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, PUCHAR Buffer, ULONG BufferSize, BOOLEAN LogError, ULONG UniqueErrorValue, UCHAR PathId, UCHAR TargetId, UCHAR Lun)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400084b0`
- `0x140014860`

## callees

- `0x14001fc38`
- `0x140021a20`
- `0x140028b40`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!IoWriteErrorLogEntry` at `0x140021b0f`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x140021b0f`
- `ntoskrnl!EtwWrite` at `0x140021b78`
- `ntoskrnl!EtwWrite` at `0x140021b78`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140021abc`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140021abc`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140021b3d`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140021b3d`

## pseudocode

```c
void __stdcall ClassNotifyFailurePredicted(
        PFUNCTIONAL_DEVICE_EXTENSION FdoExtension,
        PUCHAR Buffer,
        ULONG BufferSize,
        BOOLEAN LogError,
        ULONG UniqueErrorValue,
        UCHAR PathId,
        UCHAR TargetId,
        UCHAR Lun)
{
  char *ErrorLogEntry; // rax
  _QWORD *DriverObjectExtension; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-48h] BYREF

  EventDescriptor = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      106,
      WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
      FdoExtension->DeviceObject);
  }
  ClassWmiFireEvent(FdoExtension->DeviceObject, &StoragePredictFailureEventGuid, 0, BufferSize, Buffer);
  if ( LogError )
  {
    ErrorLogEntry = (char *)IoAllocateErrorLogEntry(FdoExtension->DeviceObject, 0x3Cu);
    if ( ErrorLogEntry )
    {
      *((_DWORD *)ErrorLogEntry + 10) = PathId;
      *(_QWORD *)(ErrorLogEntry + 20) = 0;
      *((_DWORD *)ErrorLogEntry + 3) = -2147221452;
      *(_DWORD *)ErrorLogEntry = 196622;
      *((_DWORD *)ErrorLogEntry + 7) = 2953472;
      *((_DWORD *)ErrorLogEntry + 4) = UniqueErrorValue;
      *((_DWORD *)ErrorLogEntry + 11) = TargetId;
      *((_DWORD *)ErrorLogEntry + 12) = Lun;
      IoWriteErrorLogEntry(ErrorLogEntry);
    }
    if ( LogError == 1 )
      goto LABEL_11;
  }
  if ( !FdoExtension->FailurePredicted && UniqueErrorValue == 4 )
  {
LABEL_11:
    DriverObjectExtension = IoGetDriverObjectExtension(FdoExtension->DeviceObject->DriverObject, ClassInitialize);
    if ( DriverObjectExtension )
    {
      if ( DriverObjectExtension[54] )
      {
        *(_QWORD *)&EventDescriptor.Id = 1;
        EventDescriptor.Keyword = 0;
        EtwWrite(DriverObjectExtension[54], &EventDescriptor, 0, 0, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x140021a20  push    rbx
0x140021a22  push    rbp
0x140021a23  push    rsi
0x140021a24  push    rdi
0x140021a25  push    r14
0x140021a27  sub     rsp, 50h
0x140021a2b  mov     rax, cs:__security_cookie
0x140021a32  xor     rax, rsp
0x140021a35  mov     [rsp+78h+var_38], rax
0x140021a3a  xorps   xmm0, xmm0
0x140021a3d  mov     sil, r9b
0x140021a40  movups  xmmword ptr [rsp+78h+EventDescriptor.Id], xmm0
0x140021a45  mov     ebp, r8d
0x140021a48  mov     rdi, rdx
0x140021a4b  mov     rbx, rcx
0x140021a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140021a55  lea     rax, WPP_GLOBAL_Control
0x140021a5c  cmp     rcx, rax
0x140021a5f  jz      short loc_140021A87
0x140021a61  mov     eax, [rcx+2Ch]
0x140021a64  test    al, 40h
0x140021a66  jz      short loc_140021A87
0x140021a68  cmp     byte ptr [rcx+29h], 4
0x140021a6c  jb      short loc_140021A87
0x140021a6e  mov     r9, [rbx+8]
0x140021a72  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140021a79  mov     rcx, [rcx+18h]
0x140021a7d  mov     edx, 6Ah ; 'j'
0x140021a82  call    WPP_SF_q
0x140021a87  mov     rcx, [rbx+8]; DeviceObject
0x140021a8b  lea     rdx, StoragePredictFailureEventGuid; Guid
0x140021a92  mov     r9d, ebp; EventDataSize
0x140021a95  mov     [rsp+78h+EventData], rdi; EventData
0x140021a9a  xor     r8d, r8d; InstanceIndex
0x140021a9d  call    ClassWmiFireEvent
0x140021aa2  mov     edi, [rsp+78h+UniqueErrorValue]
0x140021aa9  xor     ebp, ebp
0x140021aab  mov     r14d, 1
0x140021ab1  test    sil, sil
0x140021ab4  jz      short loc_140021B20
0x140021ab6  mov     rcx, [rbx+8]; IoObject
0x140021aba  mov     dl, 3Ch ; '<'; EntrySize
0x140021abc  call    cs:__imp_IoAllocateErrorLogEntry
0x140021ac3  nop     dword ptr [rax+rax+00h]
0x140021ac8  mov     rdx, rax
0x140021acb  test    rax, rax
0x140021ace  jz      short loc_140021B1B
0x140021ad0  movzx   ecx, [rsp+78h+PathId]
0x140021ad8  mov     [rax+28h], ecx
0x140021adb  mov     rcx, rdx; ElEntry
0x140021ade  mov     [rax+14h], rbp
0x140021ae2  mov     dword ptr [rax+0Ch], 80040034h
0x140021ae9  mov     dword ptr [rax], 3000Eh
0x140021aef  mov     dword ptr [rax+1Ch], 2D1100h
0x140021af6  mov     [rax+10h], edi
0x140021af9  movzx   eax, [rsp+78h+TargetId]
0x140021b01  mov     [rdx+2Ch], eax
0x140021b04  movzx   eax, [rsp+78h+Lun]
0x140021b0c  mov     [rdx+30h], eax
0x140021b0f  call    cs:__imp_IoWriteErrorLogEntry
0x140021b16  nop     dword ptr [rax+rax+00h]
0x140021b1b  cmp     sil, r14b
0x140021b1e  jz      short loc_140021B2E
0x140021b20  cmp     [rbx+333h], bpl
0x140021b27  jnz     short loc_140021B84
0x140021b29  cmp     edi, 4
0x140021b2c  jnz     short loc_140021B84
0x140021b2e  mov     rcx, [rbx+8]
0x140021b32  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x140021b39  mov     rcx, [rcx+8]; DriverObject
0x140021b3d  call    cs:__imp_IoGetDriverObjectExtension
0x140021b44  nop     dword ptr [rax+rax+00h]
0x140021b49  test    rax, rax
0x140021b4c  jz      short loc_140021B84
0x140021b4e  cmp     [rax+1B0h], rbp
0x140021b55  jz      short loc_140021B84
0x140021b57  mov     qword ptr [rsp+78h+EventDescriptor.Id], r14
0x140021b5c  lea     rdx, [rsp+78h+EventDescriptor]; EventDescriptor
0x140021b61  mov     [rsp+78h+EventDescriptor.Keyword], rbp
0x140021b66  xor     r9d, r9d; UserDataCount
0x140021b69  mov     rcx, [rax+1B0h]; RegHandle
0x140021b70  xor     r8d, r8d; ActivityId
0x140021b73  mov     [rsp+78h+EventData], rbp; UserData
0x140021b78  call    cs:__imp_EtwWrite
0x140021b7f  nop     dword ptr [rax+rax+00h]
0x140021b84  mov     rcx, [rsp+78h+var_38]
0x140021b89  xor     rcx, rsp; StackCookie
0x140021b8c  call    __security_check_cookie
0x140021b91  add     rsp, 50h
0x140021b95  pop     r14
0x140021b97  pop     rdi
0x140021b98  pop     rsi
0x140021b99  pop     rbp
0x140021b9a  pop     rbx
0x140021b9b  retn
```
