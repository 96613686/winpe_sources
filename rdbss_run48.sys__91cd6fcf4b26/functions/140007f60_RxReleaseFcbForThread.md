# __RxReleaseFcbForThread

- ea: `0x140007f60`
- end: `0x140008024`
- name: `__RxReleaseFcbForThread`
- size: `196`
- prototype: `void __stdcall(PRX_CONTEXT RxContext, PMRX_FCB MrxFcb, ERESOURCE_THREAD ResourceThreadId, ULONG LineNumber, PCSTR FileName, ULONG SerialNumber)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140004ac0`
- `0x14001e460`
- `0x1400764b0`
- `0x140077a20`

## callees

- `0x140007f60`
- `0x14001810c`
- `0x14001e3b0`
- `0x140065690`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140007ff6`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140007ff6`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140007fb2`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140007fb2`

## pseudocode

```c
void __stdcall _RxReleaseFcbForThread(
        PRX_CONTEXT RxContext,
        PMRX_FCB MrxFcb,
        ERESOURCE_THREAD ResourceThreadId,
        ULONG LineNumber,
        PCSTR FileName,
        ULONG SerialNumber)
{
  int v9; // esi

  v9 = *(_DWORD *)(*(_QWORD *)&MrxFcb[1].OpenCount + 296LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqq(
      WPP_GLOBAL_Control->AttachedDevice,
      14,
      &WPP_16f2bee2656c381c8186d78b34bda825_Traceguids,
      RxContext,
      MrxFcb,
      ResourceThreadId);
  }
  if ( v9
    && ExIsResourceAcquiredExclusiveLite(MrxFcb->Header.Resource)
    && (unsigned __int8)RxIsSafeToProcessBufferingStateChange(RxContext, MrxFcb) )
  {
    RxProcessFcbChangeBufferingStateRequestInternal(MrxFcb);
  }
  if ( RxContext )
    LOBYTE(RxContext->Flags) = 0;
  ExReleaseResourceForThreadLite(MrxFcb->Header.Resource, ResourceThreadId);
}

```

## disassembly

```asm
0x140007f60  push    rbx
0x140007f62  push    rbp
0x140007f63  push    rsi
0x140007f64  push    rdi
0x140007f65  sub     rsp, 38h
0x140007f69  mov     rax, [rdx+130h]
0x140007f70  mov     rbp, r8
0x140007f73  mov     rdi, rdx
0x140007f76  mov     rbx, rcx
0x140007f79  mov     esi, [rax+128h]
0x140007f7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140007f86  lea     rax, WPP_GLOBAL_Control
0x140007f8d  cmp     rcx, rax
0x140007f90  jz      short loc_140007F9B
0x140007f92  test    dword ptr [rcx+2Ch], 100h
0x140007f99  jnz     short loc_140007FC8
0x140007f9b  test    esi, esi
0x140007f9d  jnz     short loc_140007FF2
0x140007f9f  test    rbx, rbx
0x140007fa2  jz      short loc_140007FAB
0x140007fa4  mov     byte ptr [rbx+0A8h], 0
0x140007fab  mov     rcx, [rdi+8]; Resource
0x140007faf  mov     rdx, rbp; ResourceThreadId
0x140007fb2  call    cs:__imp_ExReleaseResourceForThreadLite
0x140007fb9  nop     dword ptr [rax+rax+00h]
0x140007fbe  add     rsp, 38h
0x140007fc2  pop     rdi
0x140007fc3  pop     rsi
0x140007fc4  pop     rbp
0x140007fc5  pop     rbx
0x140007fc6  retn
0x140007fc8  cmp     byte ptr [rcx+29h], 4
0x140007fcc  jb      short loc_140007F9B
0x140007fce  mov     rcx, [rcx+18h]
0x140007fd2  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x140007fd9  mov     edx, 0Eh
0x140007fde  mov     [rsp+58h+var_30], rbp
0x140007fe3  mov     r9, rbx
0x140007fe6  mov     [rsp+58h+var_38], rdi
0x140007feb  call    WPP_SF_qqq
0x140007ff0  jmp     short loc_140007F9B
0x140007ff2  mov     rcx, [rdi+8]; Resource
0x140007ff6  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x140007ffd  nop     dword ptr [rax+rax+00h]
0x140008002  test    al, al
0x140008004  jz      short loc_140007F9F
0x140008006  mov     rdx, rdi
0x140008009  mov     rcx, rbx
0x14000800c  call    RxIsSafeToProcessBufferingStateChange
0x140008011  test    al, al
0x140008013  jz      short loc_140007F9F
0x140008015  xor     edx, edx
0x140008017  mov     rcx, rdi; Instance
0x14000801a  call    RxProcessFcbChangeBufferingStateRequestInternal
0x14000801f  jmp     loc_140007F9F
```
