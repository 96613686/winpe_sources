# CompleteResilientHandleReconnect

- ea: `0x140035a18`
- end: `0x140035a96`
- name: `CompleteResilientHandleReconnect`
- size: `126`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140035a9c`
- `0x140035ef0`

## callees

- `0x14002a6a8`
- `0x140035a18`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140035a6f`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140035a6f`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140035a7e`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140035a7e`

## pseudocode

```c
void __fastcall CompleteResilientHandleReconnect(PRX_CONTEXT RxContext, struct _EX_RUNDOWN_REF *a2, int a3)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_826bdefea5f439a79d7b4a7e09ca5b98_Traceguids,
      RxContext->pFobx,
      RxContext,
      a3);
  }
  ExReleaseRundownProtection(a2 + 3);
  RxDereferenceAndDeleteRxContext_Real(RxContext);
}

```

## disassembly

```asm
0x140035a18  mov     [rsp+arg_0], rbx
0x140035a1d  push    rdi
0x140035a1e  sub     rsp, 30h
0x140035a22  mov     rdi, rdx
0x140035a25  mov     rbx, rcx
0x140035a28  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140035a2f  lea     rax, WPP_GLOBAL_Control
0x140035a36  cmp     rcx, rax
0x140035a39  jz      short loc_140035A6B
0x140035a3b  mov     eax, [rcx+2Ch]
0x140035a3e  test    al, 40h
0x140035a40  jz      short loc_140035A6B
0x140035a42  cmp     byte ptr [rcx+29h], 4
0x140035a46  jb      short loc_140035A6B
0x140035a48  mov     r9, [rbx+40h]
0x140035a4c  mov     edx, 0Dh
0x140035a51  mov     rcx, [rcx+18h]
0x140035a55  mov     [rsp+38h+var_10], r8d
0x140035a5a  lea     r8, WPP_826bdefea5f439a79d7b4a7e09ca5b98_Traceguids
0x140035a61  mov     [rsp+38h+var_18], rbx
0x140035a66  call    WPP_SF_qqD
0x140035a6b  lea     rcx, [rdi+18h]; RunRef
0x140035a6f  call    cs:__imp_ExReleaseRundownProtection
0x140035a76  nop     dword ptr [rax+rax+00h]
0x140035a7b  mov     rcx, rbx; RxContext
0x140035a7e  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140035a85  nop     dword ptr [rax+rax+00h]
0x140035a8a  mov     rbx, [rsp+38h+arg_0]
0x140035a8f  add     rsp, 30h
0x140035a93  pop     rdi
0x140035a94  retn
```
