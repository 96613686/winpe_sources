# HidpGetDeviceString

- ea: `0x180009ef8`
- end: `0x180009fd4`
- name: `HidpGetDeviceString`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006ac8`

## callees

- `0x180003900`
- `0x180009ef8`
- `0x18000a020`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180009f3b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180009f3b`
- `ntoskrnl!IofCompleteRequest` at `0x180009fbb`
- `ntoskrnl!IofCompleteRequest` at `0x180009fbb`

## pseudocode

```c
__int64 __fastcall HidpGetDeviceString(__int64 *a1, IRP *a2, unsigned __int16 a3)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  _MDL *MdlAddress; // rcx
  PVOID MappedSystemVa; // rax
  __int64 v9; // rcx
  _IO_STACK_LOCATION *v10; // rdx
  __int64 v11; // rax
  unsigned int v12; // edi

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  MdlAddress = a2->MdlAddress;
  MappedSystemVa = 0;
  if ( MdlAddress )
  {
    if ( (MdlAddress->MdlFlags & 5) != 0 )
      MappedSystemVa = MdlAddress->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
  }
  a2->UserBuffer = MappedSystemVa;
  if ( MappedSystemVa )
  {
    CurrentStackLocation[-1].MajorFunction = 15;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 720915;
    CurrentStackLocation[-1].Parameters.Read.Length = CurrentStackLocation->Parameters.Read.Length;
    CurrentStackLocation[-1].Parameters.CreatePipe.Parameters = (_NAMED_PIPE_CREATE_PARAMETERS *)((unsigned int)a3
                                                                                                + 67698688);
    v9 = *a1;
    v10 = a2->Tail.Overlay.CurrentStackLocation;
    v11 = *(_QWORD *)(*a1 + 64) + 32LL;
    v10[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))HidpAsynchronousCallCompletion;
    v10[-1].Context = (void *)v11;
    v10[-1].Control = -32;
    return (unsigned int)HidpCallDriver(v9, a2);
  }
  else
  {
    v12 = -1073741592;
    a2->IoStatus.Status = -1073741592;
    IofCompleteRequest(a2, 0);
    HidpFdoResumeIdleForIo(a1, a2);
  }
  return v12;
}

```

## disassembly

```asm
0x180009ef8  push    rbx
0x180009efa  push    rbp
0x180009efb  push    rsi
0x180009efc  push    rdi
0x180009efd  sub     rsp, 38h
0x180009f01  mov     rdi, [rdx+0B8h]
0x180009f08  mov     rsi, rcx
0x180009f0b  mov     rcx, [rdx+8]; MemoryDescriptorList
0x180009f0f  xor     eax, eax
0x180009f11  mov     ebp, r8d
0x180009f14  mov     rbx, rdx
0x180009f17  test    rcx, rcx
0x180009f1a  jz      short loc_180009F47
0x180009f1c  test    byte ptr [rcx+0Ah], 5
0x180009f20  jnz     loc_180009FA8
0x180009f26  mov     [rsp+58h+Priority], 40000010h; Priority
0x180009f2e  lea     r8d, [rax+1]; CacheType
0x180009f32  xor     r9d, r9d; RequestedAddress
0x180009f35  mov     [rsp+58h+BugCheckOnFailure], eax; BugCheckOnFailure
0x180009f39  xor     edx, edx; AccessMode
0x180009f3b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x180009f42  nop     dword ptr [rax+rax+00h]
0x180009f47  mov     [rbx+70h], rax
0x180009f4b  test    rax, rax
0x180009f4e  jz      short loc_180009FAE
0x180009f50  mov     byte ptr [rdi-48h], 0Fh
0x180009f54  lea     r8, HidpAsynchronousCallCompletion
0x180009f5b  mov     dword ptr [rdi-30h], 0B0013h
0x180009f62  mov     eax, [rdi+8]
0x180009f65  mov     [rdi-40h], eax
0x180009f68  movzx   eax, bp
0x180009f6b  add     eax, 4090000h
0x180009f70  mov     [rdi-28h], rax
0x180009f74  mov     rcx, [rsi]
0x180009f77  mov     rdx, [rbx+0B8h]
0x180009f7e  mov     rax, [rcx+40h]
0x180009f82  add     rax, 20h ; ' '
0x180009f86  mov     [rdx-10h], r8
0x180009f8a  mov     [rdx-8], rax
0x180009f8e  mov     byte ptr [rdx-45h], 0E0h
0x180009f92  mov     rdx, rbx
0x180009f95  call    HidpCallDriver
0x180009f9a  mov     edi, eax
0x180009f9c  mov     eax, edi
0x180009f9e  add     rsp, 38h
0x180009fa2  pop     rdi
0x180009fa3  pop     rsi
0x180009fa4  pop     rbp
0x180009fa5  pop     rbx
0x180009fa6  retn
0x180009fa8  mov     rax, [rcx+18h]
0x180009fac  jmp     short loc_180009F47
0x180009fae  mov     edi, 0C00000E8h
0x180009fb3  xor     edx, edx; PriorityBoost
0x180009fb5  mov     rcx, rbx; Irp
0x180009fb8  mov     [rbx+30h], edi
0x180009fbb  call    cs:__imp_IofCompleteRequest
0x180009fc2  nop     dword ptr [rax+rax+00h]
0x180009fc7  mov     rdx, rbx
0x180009fca  mov     rcx, rsi
0x180009fcd  call    HidpFdoResumeIdleForIo
0x180009fd2  jmp     short loc_180009F9C
```
