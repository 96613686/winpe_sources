# ClassWmiFireEvent

- ea: `0x140028b40`
- end: `0x140028c2c`
- name: `ClassWmiFireEvent`
- size: `236`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, LPGUID Guid, ULONG InstanceIndex, ULONG EventDataSize, PVOID EventData)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140021a20`

## callees

- `0x140028b40`
- `0x14003e640`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140028b77`
- `ntoskrnl!ExAllocatePool2` at `0x140028b77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028c08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028c08`
- `ntoskrnl!IoWMIDeviceObjectToProviderId` at `0x140028b9b`
- `ntoskrnl!IoWMIDeviceObjectToProviderId` at `0x140028b9b`
- `ntoskrnl!IoWMIWriteEvent` at `0x140028bf1`
- `ntoskrnl!IoWMIWriteEvent` at `0x140028bf1`

## pseudocode

```c
NTSTATUS __stdcall ClassWmiFireEvent(
        PDEVICE_OBJECT DeviceObject,
        LPGUID Guid,
        ULONG InstanceIndex,
        ULONG EventDataSize,
        PVOID EventData)
{
  ULONG v8; // edi
  __int64 Pool2; // rax
  _DWORD *v10; // rbx
  int v11; // edi

  v8 = EventData != 0 ? EventDataSize : 0;
  Pool2 = ExAllocatePool2(64, v8 + 64, 2001494867);
  v10 = (_DWORD *)Pool2;
  if ( !Pool2 )
    return -1073741670;
  *(GUID *)(Pool2 + 24) = *Guid;
  *(_DWORD *)(Pool2 + 4) = IoWMIDeviceObjectToProviderId(DeviceObject);
  *v10 = v8 + 64;
  v10[11] = 138;
  *((_QWORD *)v10 + 2) = MEMORY[0xFFFFF78000000014];
  v10[13] = InstanceIndex;
  v10[15] = v8;
  v10[14] = 64;
  if ( EventData )
    memmove(v10 + 16, EventData, v8);
  v11 = IoWMIWriteEvent(v10);
  if ( v11 < 0 )
    ExFreePoolWithTag(v10, 0);
  return v11;
}

```

## disassembly

```asm
0x140028b40  push    rbx
0x140028b42  push    rbp
0x140028b43  push    rdi
0x140028b44  push    r12
0x140028b46  push    r14
0x140028b48  push    r15
0x140028b4a  sub     rsp, 28h
0x140028b4e  mov     rax, [rsp+58h+EventData]
0x140028b56  mov     r14d, r8d
0x140028b59  neg     rax
0x140028b5c  mov     r15, rdx
0x140028b5f  mov     r12, rcx
0x140028b62  mov     r8d, 774C6353h
0x140028b68  sbb     edi, edi
0x140028b6a  mov     ecx, 40h ; '@'
0x140028b6f  and     edi, r9d
0x140028b72  lea     ebp, [rdi+40h]
0x140028b75  mov     edx, ebp
0x140028b77  call    cs:__imp_ExAllocatePool2
0x140028b7e  nop     dword ptr [rax+rax+00h]
0x140028b83  mov     rbx, rax
0x140028b86  test    rax, rax
0x140028b89  jz      loc_140028C16
0x140028b8f  movups  xmm0, xmmword ptr [r15]
0x140028b93  mov     rcx, r12; DeviceObject
0x140028b96  movdqu  xmmword ptr [rax+18h], xmm0
0x140028b9b  call    cs:__imp_IoWMIDeviceObjectToProviderId
0x140028ba2  nop     dword ptr [rax+rax+00h]
0x140028ba7  cmp     [rsp+58h+EventData], 0
0x140028bb0  mov     [rbx+4], eax
0x140028bb3  mov     [rbx], ebp
0x140028bb5  mov     dword ptr [rbx+2Ch], 8Ah
0x140028bbc  mov     rax, ds:0FFFFF78000000014h
0x140028bc6  mov     [rbx+10h], rax
0x140028bca  mov     [rbx+34h], r14d
0x140028bce  mov     [rbx+3Ch], edi
0x140028bd1  mov     dword ptr [rbx+38h], 40h ; '@'
0x140028bd8  jz      short loc_140028BEE
0x140028bda  mov     rdx, [rsp+58h+EventData]; Src
0x140028be2  lea     rcx, [rbx+40h]; void *
0x140028be6  mov     r8d, edi; Size
0x140028be9  call    memmove
0x140028bee  mov     rcx, rbx; WnodeEventItem
0x140028bf1  call    cs:__imp_IoWMIWriteEvent
0x140028bf8  nop     dword ptr [rax+rax+00h]
0x140028bfd  mov     edi, eax
0x140028bff  test    eax, eax
0x140028c01  jns     short loc_140028C1B
0x140028c03  xor     edx, edx; Tag
0x140028c05  mov     rcx, rbx; P
0x140028c08  call    cs:__imp_ExFreePoolWithTag
0x140028c0f  nop     dword ptr [rax+rax+00h]
0x140028c14  jmp     short loc_140028C1B
0x140028c16  mov     edi, 0C000009Ah
0x140028c1b  mov     eax, edi
0x140028c1d  add     rsp, 28h
0x140028c21  pop     r15
0x140028c23  pop     r14
0x140028c25  pop     r12
0x140028c27  pop     rdi
0x140028c28  pop     rbp
0x140028c29  pop     rbx
0x140028c2a  retn
```
