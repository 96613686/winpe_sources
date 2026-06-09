# SmbCepTearDownVNetRootContext

- ea: `0x140030a20`
- end: `0x140030b27`
- name: `SmbCepTearDownVNetRootContext`
- size: `263`
- prototype: `void __stdcall(PVOID Context)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140013f00`
- `0x14001c0f0`
- `0x140021130`
- `0x140026d60`
- `0x140030a20`
- `0x1400383d0`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140030ac4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030ac4`
- `rdbss!RxTearDownDiagnosticLogger` at `0x140030af6`
- `rdbss!RxTearDownDiagnosticLogger` at `0x140030af6`
- `rdbss!RxFinalizeSecurityContext` at `0x140030aa7`
- `rdbss!RxFinalizeSecurityContext` at `0x140030aa7`

## pseudocode

```c
void __fastcall SmbCepTearDownVNetRootContext(char *Context)
{
  __int64 v1; // rdi
  void *v3; // rcx
  __int64 v4; // rcx

  v1 = *((_QWORD *)Context + 3);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids, Context);
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)Context + 52) + 384LL) + 56LL) + 768LL))(Context);
  SmbCeDereferenceSessionEntryEx(*((unsigned __int16 **)Context + 52), 0);
  *((_QWORD *)Context + 52) = 0;
  RxFinalizeSecurityContext(Context + 96);
  v3 = (void *)*((_QWORD *)Context + 58);
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0x6D537541u);
    *((_QWORD *)Context + 58) = 0;
  }
  SmbCeDereferenceNetRootEntry(*((PVOID *)Context + 53));
  v4 = *((_QWORD *)Context + 2);
  *((_QWORD *)Context + 53) = 0;
  RxTearDownDiagnosticLogger(v4);
  SmbCeDecrementTeardownOpCounterAndUnblockWaiters(v1, Context, 4);
  SmbMmFreeObjectPool(Context);
}

```

## disassembly

```asm
0x140030a20  mov     [rsp+arg_0], rbx
0x140030a25  push    rdi
0x140030a26  sub     rsp, 20h
0x140030a2a  mov     rdi, [rcx+18h]
0x140030a2e  mov     rbx, rcx
0x140030a31  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030a38  lea     rax, WPP_GLOBAL_Control
0x140030a3f  cmp     rcx, rax
0x140030a42  jz      short loc_140030A69
0x140030a44  mov     eax, [rcx+2Ch]
0x140030a47  test    al, 40h
0x140030a49  jz      short loc_140030A69
0x140030a4b  cmp     byte ptr [rcx+29h], 2
0x140030a4f  jb      short loc_140030A69
0x140030a51  mov     rcx, [rcx+18h]
0x140030a55  lea     r8, WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids
0x140030a5c  mov     edx, 23h ; '#'
0x140030a61  mov     r9, rbx
0x140030a64  call    WPP_SF_q
0x140030a69  mov     rax, [rbx+1A0h]
0x140030a70  mov     rcx, [rax+180h]
0x140030a77  mov     rax, [rcx+38h]
0x140030a7b  mov     rcx, rbx
0x140030a7e  mov     rax, [rax+300h]
0x140030a85  call    _guard_dispatch_icall
0x140030a8a  mov     rcx, [rbx+1A0h]; BugCheckParameter2
0x140030a91  xor     edx, edx
0x140030a93  call    SmbCeDereferenceSessionEntryEx
0x140030a98  lea     rcx, [rbx+60h]
0x140030a9c  mov     qword ptr [rbx+1A0h], 0
0x140030aa7  call    cs:__imp_RxFinalizeSecurityContext
0x140030aae  nop     dword ptr [rax+rax+00h]
0x140030ab3  mov     rcx, [rbx+1D0h]; P
0x140030aba  test    rcx, rcx
0x140030abd  jz      short loc_140030ADB
0x140030abf  mov     edx, 6D537541h; Tag
0x140030ac4  call    cs:__imp_ExFreePoolWithTag
0x140030acb  nop     dword ptr [rax+rax+00h]
0x140030ad0  mov     qword ptr [rbx+1D0h], 0
0x140030adb  mov     rcx, [rbx+1A8h]; pContext
0x140030ae2  call    SmbCeDereferenceNetRootEntry
0x140030ae7  mov     rcx, [rbx+10h]
0x140030aeb  mov     qword ptr [rbx+1A8h], 0
0x140030af6  call    cs:__imp_RxTearDownDiagnosticLogger
0x140030afd  nop     dword ptr [rax+rax+00h]
0x140030b02  mov     r8d, 4
0x140030b08  mov     rdx, rbx
0x140030b0b  mov     rcx, rdi
0x140030b0e  call    SmbCeDecrementTeardownOpCounterAndUnblockWaiters
0x140030b13  mov     rcx, rbx
0x140030b16  call    SmbMmFreeObjectPool
0x140030b1b  mov     rbx, [rsp+28h+arg_0]
0x140030b20  add     rsp, 20h
0x140030b24  pop     rdi
0x140030b25  retn
```
