# KbdHid_Flush

- ea: `0x140005800`
- end: `0x1400058ce`
- name: `KbdHid_Flush`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005800`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000589c`
- `ntoskrnl!IofCallDriver` at `0x14000589c`
- `ntoskrnl!IofCompleteRequest` at `0x140005849`
- `ntoskrnl!IofCompleteRequest` at `0x140005849`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400058b6`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400058b6`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000582f`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000582f`

## pseudocode

```c
__int64 __fastcall KbdHid_Flush(__int64 a1, IRP *a2)
{
  __int64 v2; // rsi
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v7; // rax

  v2 = *(_QWORD *)(a1 + 64);
  v4 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 152), a2, File, 1u, 0x20u);
  v5 = v4;
  if ( v4 >= 0 )
  {
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
    *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                               + 6);
    CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
    CurrentStackLocation[-1].Control = 0;
    v7 = a2->Tail.Overlay.CurrentStackLocation;
    v7[-1].MajorFunction = 14;
    v7[-1].Parameters.Read.ByteOffset.LowPart = 721303;
    v5 = IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 8), a2);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 152), a2, 0x20u);
  }
  else
  {
    a2->IoStatus.Status = v4;
    IofCompleteRequest(a2, 0);
  }
  return v5;
}

```

## disassembly

```asm
0x140005800  push    rbx
0x140005802  push    rbp
0x140005803  push    rsi
0x140005804  push    rdi
0x140005805  sub     rsp, 38h
0x140005809  mov     rsi, [rcx+40h]
0x14000580d  lea     r8, File; File
0x140005814  mov     r9d, 1; Line
0x14000581a  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x140005822  mov     rdi, rdx
0x140005825  lea     rbp, [rsi+98h]
0x14000582c  mov     rcx, rbp; RemoveLock
0x14000582f  call    cs:__imp_IoAcquireRemoveLockEx
0x140005836  nop     dword ptr [rax+rax+00h]
0x14000583b  mov     ebx, eax
0x14000583d  test    eax, eax
0x14000583f  jns     short loc_140005857
0x140005841  xor     edx, edx; PriorityBoost
0x140005843  mov     [rdi+30h], eax
0x140005846  mov     rcx, rdi; Irp
0x140005849  call    cs:__imp_IofCompleteRequest
0x140005850  nop     dword ptr [rax+rax+00h]
0x140005855  jmp     short loc_1400058C2
0x140005857  mov     rax, [rdi+0B8h]
0x14000585e  mov     rdx, rdi; Irp
0x140005861  movups  xmm0, xmmword ptr [rax]
0x140005864  movups  xmmword ptr [rax-48h], xmm0
0x140005868  movups  xmm1, xmmword ptr [rax+10h]
0x14000586c  movups  xmmword ptr [rax-38h], xmm1
0x140005870  movups  xmm0, xmmword ptr [rax+20h]
0x140005874  movups  xmmword ptr [rax-28h], xmm0
0x140005878  movsd   xmm1, qword ptr [rax+30h]
0x14000587d  movsd   qword ptr [rax-18h], xmm1
0x140005882  mov     byte ptr [rax-45h], 0
0x140005886  mov     rax, [rdi+0B8h]
0x14000588d  mov     byte ptr [rax-48h], 0Eh
0x140005891  mov     dword ptr [rax-30h], 0B0197h
0x140005898  mov     rcx, [rsi+8]; DeviceObject
0x14000589c  call    cs:__imp_IofCallDriver
0x1400058a3  nop     dword ptr [rax+rax+00h]
0x1400058a8  mov     r8d, 20h ; ' '; RemlockSize
0x1400058ae  mov     rdx, rdi; Tag
0x1400058b1  mov     rcx, rbp; RemoveLock
0x1400058b4  mov     ebx, eax
0x1400058b6  call    cs:__imp_IoReleaseRemoveLockEx
0x1400058bd  nop     dword ptr [rax+rax+00h]
0x1400058c2  mov     eax, ebx
0x1400058c4  add     rsp, 38h
0x1400058c8  pop     rdi
0x1400058c9  pop     rsi
0x1400058ca  pop     rbp
0x1400058cb  pop     rbx
0x1400058cc  retn
```
