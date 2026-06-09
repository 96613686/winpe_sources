# FltTagFile

- ea: `0x180071370`
- end: `0x180071504`
- name: `FltTagFile`
- size: `404`
- prototype: `NTSTATUS __stdcall(PFLT_INSTANCE InitiatingInstance, PFILE_OBJECT FileObject, ULONG FileTag, GUID *Guid, PVOID DataBuffer, USHORT DataBufferLength)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180085b20`

## callees

- `0x180008000`
- `0x180008080`
- `0x180008a70`
- `0x180009f20`
- `0x180024900`
- `0x180071370`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180071497`
- `ntoskrnl!ExFreePoolWithTag` at `0x180071497`
- `ntoskrnl!ExAllocatePool2` at `0x180071405`
- `ntoskrnl!ExAllocatePool2` at `0x180071405`
- `ntoskrnl!RtlCompareMemory` at `0x1800714d9`
- `ntoskrnl!RtlCompareMemory` at `0x1800714d9`

## pseudocode

```c
NTSTATUS __stdcall FltTagFile(
        PFLT_INSTANCE InitiatingInstance,
        PFILE_OBJECT FileObject,
        ULONG FileTag,
        GUID *Guid,
        PVOID DataBuffer,
        USHORT DataBufferLength)
{
  ULONG *v10; // rbx
  NTSTATUS Status; // esi
  int v12; // eax
  PFLT_CALLBACK_DATA v13; // rdi
  int v14; // r15d
  ULONG v15; // r15d
  ULONG *Pool2; // rax
  GUID *v17; // rcx
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+20h] [rbp-28h] BYREF

  RetNewCallbackData = 0;
  if ( (FileTag & 0x80000000) == 0 && (!Guid || RtlCompareMemory(Guid, &GUID_NULL, 0x10u) == 16) )
    return -1073741811;
  v10 = 0;
  Status = FltAllocateCallbackData(InitiatingInstance, FileObject, &RetNewCallbackData);
  v12 = FltpDbgStatus(Status);
  v13 = RetNewCallbackData;
  if ( v12 >= 0 )
  {
    v14 = 8;
    if ( Guid )
      v14 = 24;
    v15 = DataBufferLength + v14;
    Pool2 = (ULONG *)ExAllocatePool2(64, v15, 1886539078);
    v10 = Pool2;
    if ( Pool2 )
    {
      v17 = (GUID *)(Pool2 + 2);
      *Pool2 = FileTag;
      Pool2[1] = DataBufferLength;
      if ( Guid )
      {
        *v17 = *Guid;
        v17 = (GUID *)(Pool2 + 6);
      }
      memmove(v17, DataBuffer, DataBufferLength);
      v13->Iopb->MajorFunction = 13;
      v13->Iopb->Parameters.Read.ByteOffset.LowPart = 589988;
      v13->Iopb->Parameters.CreatePipe.Parameters = v10;
      v13->Iopb->Parameters.Create.Options = v15;
      v13->Iopb->IrpFlags |= 1u;
      FltPerformSynchronousIo(v13);
      Status = v13->IoStatus.Status;
    }
    else
    {
      Status = -1073741670;
    }
  }
  if ( v13 )
    FltFreeCallbackData(v13);
  if ( v10 )
    ExFreePoolWithTag(v10, 0x70724D46u);
  return Status;
}

```

## disassembly

```asm
0x180071370  mov     [rsp+arg_10], rbp
0x180071375  push    rsi
0x180071376  push    rdi
0x180071377  push    r14
0x180071379  sub     rsp, 30h
0x18007137d  mov     [rsp+48h+RetNewCallbackData], 0
0x180071386  mov     r14, r9
0x180071389  mov     ebp, r8d
0x18007138c  mov     rdi, rdx
0x18007138f  mov     rsi, rcx
0x180071392  test    r8d, r8d
0x180071395  jns     loc_1800714C0
0x18007139b  mov     [rsp+48h+arg_0], rbx
0x1800713a0  lea     r8, [rsp+48h+RetNewCallbackData]; RetNewCallbackData
0x1800713a5  mov     rdx, rdi; FileObject
0x1800713a8  mov     rcx, rsi; Instance
0x1800713ab  xor     ebx, ebx
0x1800713ad  call    FltAllocateCallbackData
0x1800713b2  mov     r8d, 17E3h
0x1800713b8  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x1800713bf  xor     r9d, r9d
0x1800713c2  mov     ecx, eax
0x1800713c4  mov     esi, eax
0x1800713c6  call    FltpDbgStatus
0x1800713cb  mov     rdi, [rsp+48h+RetNewCallbackData]
0x1800713d0  test    eax, eax
0x1800713d2  js      loc_18007147D
0x1800713d8  movzx   esi, [rsp+48h+DataBufferLength]
0x1800713dd  mov     eax, 18h
0x1800713e2  mov     [rsp+48h+arg_8], r15
0x1800713e7  test    r14, r14
0x1800713ea  mov     r15d, 8
0x1800713f0  mov     ecx, 40h ; '@'
0x1800713f5  cmovnz  r15d, eax
0x1800713f9  mov     r8d, 70724D46h
0x1800713ff  add     r15d, esi
0x180071402  mov     edx, r15d
0x180071405  call    cs:__imp_ExAllocatePool2
0x18007140c  nop     dword ptr [rax+rax+00h]
0x180071411  mov     rbx, rax
0x180071414  test    rax, rax
0x180071417  jz      loc_1800714B9
0x18007141d  mov     rdx, [rsp+48h+DataBuffer]; Src
0x180071422  lea     rcx, [rbx+8]; void *
0x180071426  mov     [rax], ebp
0x180071428  mov     r8d, esi; Size
0x18007142b  mov     [rax+4], si
0x18007142f  xor     eax, eax
0x180071431  mov     [rbx+6], ax
0x180071435  test    r14, r14
0x180071438  jnz     loc_1800714F4
0x18007143e  call    memmove
0x180071443  mov     rax, [rdi+10h]
0x180071447  mov     rcx, rdi; CallbackData
0x18007144a  mov     byte ptr [rax+4], 0Dh
0x18007144e  mov     rax, [rdi+10h]
0x180071452  mov     dword ptr [rax+28h], 900A4h
0x180071459  mov     rax, [rdi+10h]
0x18007145d  mov     [rax+30h], rbx
0x180071461  mov     rax, [rdi+10h]
0x180071465  mov     [rax+20h], r15d
0x180071469  mov     rax, [rdi+10h]
0x18007146d  or      dword ptr [rax], 1
0x180071470  call    FltPerformSynchronousIo
0x180071475  mov     esi, [rdi+18h]
0x180071478  mov     r15, [rsp+48h+arg_8]
0x18007147d  test    rdi, rdi
0x180071480  jz      short loc_18007148A
0x180071482  mov     rcx, rdi; CallbackData
0x180071485  call    FltFreeCallbackData
0x18007148a  test    rbx, rbx
0x18007148d  jz      short loc_1800714A3
0x18007148f  mov     edx, 70724D46h; Tag
0x180071494  mov     rcx, rbx; P
0x180071497  call    cs:__imp_ExFreePoolWithTag
0x18007149e  nop     dword ptr [rax+rax+00h]
0x1800714a3  mov     rbx, [rsp+48h+arg_0]
0x1800714a8  mov     eax, esi
0x1800714aa  mov     rbp, [rsp+48h+arg_10]
0x1800714af  add     rsp, 30h
0x1800714b3  pop     r14
0x1800714b5  pop     rdi
0x1800714b6  pop     rsi
0x1800714b7  retn
0x1800714b9  mov     esi, 0C000009Ah
0x1800714be  jmp     short loc_180071478
0x1800714c0  test    r14, r14
0x1800714c3  jz      loc_18007AE3E
0x1800714c9  mov     r8d, 10h; Length
0x1800714cf  lea     rdx, GUID_NULL; Source2
0x1800714d6  mov     rcx, r14; Source1
0x1800714d9  call    cs:__imp_RtlCompareMemory
0x1800714e0  nop     dword ptr [rax+rax+00h]
0x1800714e5  cmp     rax, 10h
0x1800714e9  jnz     loc_18007139B
0x1800714ef  jmp     loc_18007AE3E
0x1800714f4  movups  xmm0, xmmword ptr [r14]
0x1800714f8  movups  xmmword ptr [rcx], xmm0
0x1800714fb  lea     rcx, [rbx+18h]
0x1800714ff  jmp     loc_18007143E
0x18007ae3e  mov     eax, 0C000000Dh
0x18007ae43  jmp     loc_1800714AA
```
