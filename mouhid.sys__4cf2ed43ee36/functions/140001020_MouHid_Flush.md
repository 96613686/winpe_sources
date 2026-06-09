# MouHid_Flush

- ea: `0x140001020`
- end: `0x1400010ee`
- name: `MouHid_Flush`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001020`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140001069`
- `ntoskrnl!IofCompleteRequest` at `0x140001069`
- `ntoskrnl!IofCallDriver` at `0x1400010bc`
- `ntoskrnl!IofCallDriver` at `0x1400010bc`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400010d6`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400010d6`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000104f`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000104f`

## pseudocode

```c
__int64 __fastcall MouHid_Flush(__int64 a1, IRP *a2)
{
  __int64 v2; // rsi
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v7; // rax

  v2 = *(_QWORD *)(a1 + 64);
  v4 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 240), a2, File, 1u, 0x20u);
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
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 240), a2, 0x20u);
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
0x140001020  push    rbx
0x140001022  push    rbp
0x140001023  push    rsi
0x140001024  push    rdi
0x140001025  sub     rsp, 38h
0x140001029  mov     rsi, [rcx+40h]
0x14000102d  lea     r8, File; File
0x140001034  mov     r9d, 1; Line
0x14000103a  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x140001042  mov     rdi, rdx
0x140001045  lea     rbp, [rsi+0F0h]
0x14000104c  mov     rcx, rbp; RemoveLock
0x14000104f  call    cs:__imp_IoAcquireRemoveLockEx
0x140001056  nop     dword ptr [rax+rax+00h]
0x14000105b  mov     ebx, eax
0x14000105d  test    eax, eax
0x14000105f  jns     short loc_140001077
0x140001061  xor     edx, edx; PriorityBoost
0x140001063  mov     [rdi+30h], eax
0x140001066  mov     rcx, rdi; Irp
0x140001069  call    cs:__imp_IofCompleteRequest
0x140001070  nop     dword ptr [rax+rax+00h]
0x140001075  jmp     short loc_1400010E2
0x140001077  mov     rax, [rdi+0B8h]
0x14000107e  mov     rdx, rdi; Irp
0x140001081  movups  xmm0, xmmword ptr [rax]
0x140001084  movups  xmmword ptr [rax-48h], xmm0
0x140001088  movups  xmm1, xmmword ptr [rax+10h]
0x14000108c  movups  xmmword ptr [rax-38h], xmm1
0x140001090  movups  xmm0, xmmword ptr [rax+20h]
0x140001094  movups  xmmword ptr [rax-28h], xmm0
0x140001098  movsd   xmm1, qword ptr [rax+30h]
0x14000109d  movsd   qword ptr [rax-18h], xmm1
0x1400010a2  mov     byte ptr [rax-45h], 0
0x1400010a6  mov     rax, [rdi+0B8h]
0x1400010ad  mov     byte ptr [rax-48h], 0Eh
0x1400010b1  mov     dword ptr [rax-30h], 0B0197h
0x1400010b8  mov     rcx, [rsi+8]; DeviceObject
0x1400010bc  call    cs:__imp_IofCallDriver
0x1400010c3  nop     dword ptr [rax+rax+00h]
0x1400010c8  mov     r8d, 20h ; ' '; RemlockSize
0x1400010ce  mov     rdx, rdi; Tag
0x1400010d1  mov     rcx, rbp; RemoveLock
0x1400010d4  mov     ebx, eax
0x1400010d6  call    cs:__imp_IoReleaseRemoveLockEx
0x1400010dd  nop     dword ptr [rax+rax+00h]
0x1400010e2  mov     eax, ebx
0x1400010e4  add     rsp, 38h
0x1400010e8  pop     rdi
0x1400010e9  pop     rsi
0x1400010ea  pop     rbp
0x1400010eb  pop     rbx
0x1400010ec  retn
```
