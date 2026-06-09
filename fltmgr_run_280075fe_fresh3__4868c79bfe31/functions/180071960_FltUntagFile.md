# FltUntagFile

- ea: `0x180071960`
- end: `0x180071ab8`
- name: `FltUntagFile`
- size: `344`
- prototype: `NTSTATUS __stdcall(PFLT_INSTANCE InitiatingInstance, PFILE_OBJECT FileObject, ULONG FileTag, GUID *Guid)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180085ca0`

## callees

- `0x180008000`
- `0x180008080`
- `0x180008a70`
- `0x180009f20`
- `0x180071960`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180071a52`
- `ntoskrnl!ExFreePoolWithTag` at `0x180071a52`
- `ntoskrnl!ExAllocatePool2` at `0x1800719e0`
- `ntoskrnl!ExAllocatePool2` at `0x1800719e0`
- `ntoskrnl!RtlCompareMemory` at `0x180071a90`
- `ntoskrnl!RtlCompareMemory` at `0x180071a90`

## pseudocode

```c
NTSTATUS __stdcall FltUntagFile(PFLT_INSTANCE InitiatingInstance, PFILE_OBJECT FileObject, ULONG FileTag, GUID *Guid)
{
  void *v8; // rbx
  unsigned int Status; // esi
  int v10; // eax
  PFLT_CALLBACK_DATA v11; // rdi
  unsigned int v12; // eax
  ULONG v13; // esi
  __int64 Pool2; // rax
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+20h] [rbp-38h] BYREF

  RetNewCallbackData = 0;
  if ( (FileTag & 0x80000000) == 0 && (!Guid || RtlCompareMemory(Guid, &GUID_NULL, 0x10u) == 16) )
    return -1073741811;
  v8 = 0;
  Status = FltAllocateCallbackData(InitiatingInstance, FileObject, &RetNewCallbackData);
  v10 = FltpDbgStatus(Status, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 6436, 0);
  v11 = RetNewCallbackData;
  if ( v10 >= 0 )
  {
    v12 = 8;
    if ( Guid )
      v12 = 24;
    v13 = v12;
    Pool2 = ExAllocatePool2(64, v12, 1886539078);
    v8 = (void *)Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)Pool2 = FileTag;
      *(_DWORD *)(Pool2 + 4) = 0;
      if ( Guid )
        *(GUID *)(Pool2 + 8) = *Guid;
      v11->Iopb->MajorFunction = 13;
      v11->Iopb->Parameters.Read.ByteOffset.LowPart = 589996;
      v11->Iopb->Parameters.CreatePipe.Parameters = (PVOID)Pool2;
      v11->Iopb->Parameters.Create.Options = v13;
      v11->Iopb->IrpFlags |= 1u;
      FltPerformSynchronousIo(v11);
      Status = v11->IoStatus.Status;
    }
    else
    {
      Status = -1073741670;
    }
  }
  if ( v11 )
    FltFreeCallbackData(v11);
  if ( v8 )
    ExFreePoolWithTag(v8, 0x70724D46u);
  return Status;
}

```

## disassembly

```asm
0x180071960  push    rbp
0x180071962  push    rsi
0x180071963  push    rdi
0x180071964  push    r14
0x180071966  sub     rsp, 38h
0x18007196a  mov     [rsp+58h+RetNewCallbackData], 0
0x180071973  mov     r14, r9
0x180071976  mov     ebp, r8d
0x180071979  mov     rdi, rdx
0x18007197c  mov     rsi, rcx
0x18007197f  test    r8d, r8d
0x180071982  jns     loc_180071A77
0x180071988  mov     [rsp+58h+arg_0], rbx
0x18007198d  lea     r8, [rsp+58h+RetNewCallbackData]; RetNewCallbackData
0x180071992  mov     rdx, rdi; FileObject
0x180071995  mov     rcx, rsi; Instance
0x180071998  xor     ebx, ebx
0x18007199a  call    FltAllocateCallbackData
0x18007199f  mov     r8d, 1924h
0x1800719a5  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x1800719ac  xor     r9d, r9d
0x1800719af  mov     ecx, eax
0x1800719b1  mov     esi, eax
0x1800719b3  call    FltpDbgStatus
0x1800719b8  mov     rdi, [rsp+58h+RetNewCallbackData]
0x1800719bd  test    eax, eax
0x1800719bf  js      short loc_180071A38
0x1800719c1  mov     eax, 8
0x1800719c6  mov     ecx, 18h
0x1800719cb  test    r14, r14
0x1800719ce  mov     r8d, 70724D46h
0x1800719d4  cmovnz  eax, ecx
0x1800719d7  mov     ecx, 40h ; '@'
0x1800719dc  mov     edx, eax
0x1800719de  mov     esi, eax
0x1800719e0  call    cs:__imp_ExAllocatePool2
0x1800719e7  nop     dword ptr [rax+rax+00h]
0x1800719ec  mov     rbx, rax
0x1800719ef  test    rax, rax
0x1800719f2  jz      short loc_180071A70
0x1800719f4  mov     [rax], ebp
0x1800719f6  xor     eax, eax
0x1800719f8  mov     [rbx+4], eax
0x1800719fb  test    r14, r14
0x1800719fe  jnz     loc_180071AAB
0x180071a04  mov     rax, [rdi+10h]
0x180071a08  mov     rcx, rdi; CallbackData
0x180071a0b  mov     byte ptr [rax+4], 0Dh
0x180071a0f  mov     rax, [rdi+10h]
0x180071a13  mov     dword ptr [rax+28h], 900ACh
0x180071a1a  mov     rax, [rdi+10h]
0x180071a1e  mov     [rax+30h], rbx
0x180071a22  mov     rax, [rdi+10h]
0x180071a26  mov     [rax+20h], esi
0x180071a29  mov     rax, [rdi+10h]
0x180071a2d  or      dword ptr [rax], 1
0x180071a30  call    FltPerformSynchronousIo
0x180071a35  mov     esi, [rdi+18h]
0x180071a38  test    rdi, rdi
0x180071a3b  jz      short loc_180071A45
0x180071a3d  mov     rcx, rdi; CallbackData
0x180071a40  call    FltFreeCallbackData
0x180071a45  test    rbx, rbx
0x180071a48  jz      short loc_180071A5E
0x180071a4a  mov     edx, 70724D46h; Tag
0x180071a4f  mov     rcx, rbx; P
0x180071a52  call    cs:__imp_ExFreePoolWithTag
0x180071a59  nop     dword ptr [rax+rax+00h]
0x180071a5e  mov     rbx, [rsp+58h+arg_0]
0x180071a63  mov     eax, esi
0x180071a65  add     rsp, 38h
0x180071a69  pop     r14
0x180071a6b  pop     rdi
0x180071a6c  pop     rsi
0x180071a6d  pop     rbp
0x180071a6e  retn
0x180071a70  mov     esi, 0C000009Ah
0x180071a75  jmp     short loc_180071A38
0x180071a77  test    r14, r14
0x180071a7a  jz      loc_18007AED4
0x180071a80  mov     r8d, 10h; Length
0x180071a86  lea     rdx, GUID_NULL; Source2
0x180071a8d  mov     rcx, r14; Source1
0x180071a90  call    cs:__imp_RtlCompareMemory
0x180071a97  nop     dword ptr [rax+rax+00h]
0x180071a9c  cmp     rax, 10h
0x180071aa0  jnz     loc_180071988
0x180071aa6  jmp     loc_18007AED4
0x180071aab  movups  xmm0, xmmword ptr [r14]
0x180071aaf  movups  xmmword ptr [rbx+8], xmm0
0x180071ab3  jmp     loc_180071A04
0x18007aed4  mov     eax, 0C000000Dh
0x18007aed9  jmp     loc_180071A65
```
