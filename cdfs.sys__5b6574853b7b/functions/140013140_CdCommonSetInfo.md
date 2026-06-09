# CdCommonSetInfo

- ea: `0x140013140`
- end: `0x140013280`
- name: `CdCommonSetInfo`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140001240`
- `0x140002250`

## callees

- `0x140001160`
- `0x140013140`
- `0x1400181a4`
- `0x14001a2a0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1400131eb`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400131eb`
- `ntoskrnl!ExReleaseFastMutex` at `0x140013238`
- `ntoskrnl!ExReleaseFastMutex` at `0x140013238`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001324a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b97e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001324a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b97e`

## pseudocode

```c
__int64 __fastcall CdCommonSetInfo(void *a1, IRP *a2)
{
  IRP *v2; // r14
  void *v3; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  PFILE_OBJECT FileObject; // rbx
  int v6; // eax
  PVOID FsContext; // rbx
  unsigned int v8; // edi
  struct _IRP *MasterIrp; // r12
  struct _KTHREAD *CurrentThread; // rdi

  v2 = a2;
  v3 = a1;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  v6 = (__int64)FileObject->FsContext2 & 7;
  if ( v6 )
    FsContext = FileObject->FsContext;
  else
    FsContext = 0;
  if ( v6 == 4 && CurrentStackLocation->Parameters.Create.Options == 14 )
  {
    v8 = -1073741811;
    CdAcquireResource(a1, *((_QWORD *)FsContext + 1), 0, 1);
    CdVerifyFcbOperation(v3, FsContext);
    MasterIrp = v2->AssociatedIrp.MasterIrp;
    if ( (CurrentStackLocation->FileObject->Flags & 8) == 0
      || (*(_DWORD *)(*((_QWORD *)FsContext + 15) + 440LL) & *(_DWORD *)&MasterIrp->Type) == 0 )
    {
      CurrentThread = KeGetCurrentThread();
      if ( CurrentThread != *((struct _KTHREAD **)FsContext + 23) )
      {
        ExAcquireFastMutex((PFAST_MUTEX)(*((_QWORD *)FsContext + 25) + 136LL));
        *((_QWORD *)FsContext + 23) = CurrentThread;
      }
      ++*((_DWORD *)FsContext + 48);
      CurrentStackLocation->FileObject->CurrentByteOffset.QuadPart = *(_QWORD *)&MasterIrp->Type;
      if ( (*((_DWORD *)FsContext + 48))-- == 1 )
      {
        *((_QWORD *)FsContext + 23) = 0;
        ExReleaseFastMutex((PFAST_MUTEX)(*((_QWORD *)FsContext + 25) + 136LL));
      }
      v8 = 0;
    }
    ExReleaseResourceLite(*((PERESOURCE *)FsContext + 1));
    a2 = v2;
    a1 = v3;
  }
  else
  {
    v8 = -1073741811;
  }
  CdCompleteRequest(a1, a2, v8);
  return v8;
}

```

## disassembly

```asm
0x140013140  mov     [rsp+arg_0], rbx
0x140013145  push    rsi
0x140013146  push    rdi
0x140013147  push    r12
0x140013149  push    r14
0x14001314b  push    r15
0x14001314d  sub     rsp, 20h
0x140013151  mov     r14, rdx
0x140013154  mov     r15, rcx
0x140013157  mov     rsi, [rdx+0B8h]
0x14001315e  mov     rbx, [rsi+30h]
0x140013162  mov     eax, [rbx+20h]
0x140013165  and     eax, 7
0x140013168  jnz     short loc_14001316E
0x14001316a  xor     ebx, ebx
0x14001316c  jmp     short loc_140013172
0x14001316e  mov     rbx, [rbx+18h]
0x140013172  mov     [rsp+48h+arg_10], rbx
0x140013177  cmp     eax, 4
0x14001317a  jnz     loc_14001325E
0x140013180  cmp     dword ptr [rsi+10h], 0Eh
0x140013184  jnz     loc_14001325E
0x14001318a  mov     edi, 0C000000Dh
0x14001318f  lea     r9d, [rax-3]
0x140013193  xor     r8d, r8d
0x140013196  mov     rdx, [rbx+8]
0x14001319a  call    CdAcquireResource
0x14001319f  nop
0x1400131a0  mov     rdx, rbx
0x1400131a3  mov     rcx, r15
0x1400131a6  call    CdVerifyFcbOperation
0x1400131ab  mov     r12, [r14+18h]
0x1400131af  mov     rax, [rsi+30h]
0x1400131b3  mov     ecx, [rax+50h]
0x1400131b6  test    cl, 8
0x1400131b9  jz      short loc_1400131CB
0x1400131bb  mov     rax, [rbx+78h]
0x1400131bf  mov     ecx, [rax+1B8h]
0x1400131c5  test    [r12], ecx
0x1400131c9  jnz     short loc_140013246
0x1400131cb  mov     rdi, gs:188h
0x1400131d4  cmp     rdi, [rbx+0B8h]
0x1400131db  jz      short loc_1400131FE
0x1400131dd  mov     rcx, [rbx+0C8h]
0x1400131e4  add     rcx, 88h; FastMutex
0x1400131eb  call    cs:__imp_ExAcquireFastMutex
0x1400131f2  nop     dword ptr [rax+rax+00h]
0x1400131f7  mov     [rbx+0B8h], rdi
0x1400131fe  inc     dword ptr [rbx+0C0h]
0x140013204  mov     rcx, [rsi+30h]
0x140013208  mov     rax, [r12]
0x14001320c  mov     [rcx+68h], rax
0x140013210  add     dword ptr [rbx+0C0h], 0FFFFFFFFh
0x140013217  mov     eax, [rbx+0C0h]
0x14001321d  jnz     short loc_140013244
0x14001321f  mov     qword ptr [rbx+0B8h], 0
0x14001322a  mov     rcx, [rbx+0C8h]
0x140013231  add     rcx, 88h; FastMutex
0x140013238  call    cs:__imp_ExReleaseFastMutex
0x14001323f  nop     dword ptr [rax+rax+00h]
0x140013244  xor     edi, edi
0x140013246  mov     rcx, [rbx+8]; Resource
0x14001324a  call    cs:__imp_ExReleaseResourceLite
0x140013251  nop     dword ptr [rax+rax+00h]
0x140013256  mov     rdx, r14
0x140013259  mov     rcx, r15
0x14001325c  jmp     short loc_140013263
0x14001325e  mov     edi, 0C000000Dh
0x140013263  mov     r8d, edi
0x140013266  call    CdCompleteRequest
0x14001326b  mov     eax, edi
0x14001326d  mov     rbx, [rsp+48h+arg_0]
0x140013272  add     rsp, 20h
0x140013276  pop     r15
0x140013278  pop     r14
0x14001327a  pop     r12
0x14001327c  pop     rdi
0x14001327d  pop     rsi
0x14001327e  retn
0x14001b96d  push    rbp
0x14001b96f  sub     rsp, 20h
0x14001b973  mov     rbp, rdx
0x14001b976  mov     rcx, [rbp+60h]
0x14001b97a  mov     rcx, [rcx+8]; Resource
0x14001b97e  call    cs:__imp_ExReleaseResourceLite
0x14001b985  nop     dword ptr [rax+rax+00h]
0x14001b98a  nop
0x14001b98b  add     rsp, 20h
0x14001b98f  pop     rbp
0x14001b990  retn
```
