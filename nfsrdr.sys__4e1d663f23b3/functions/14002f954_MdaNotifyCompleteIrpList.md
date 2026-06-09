# MdaNotifyCompleteIrpList

- ea: `0x14002f954`
- end: `0x14002fa5e`
- name: `MdaNotifyCompleteIrpList`
- size: `266`
- prototype: `void __fastcall(__int64, NTSTATUS)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002f57c`
- `0x14002fa64`
- `0x14002fe10`

## callees

- `0x1400159cc`
- `0x14002f744`
- `0x14002f954`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002fa07`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fa07`
- `rdbss!RxSetMinirdrCancelRoutine` at `0x14002f9cb`
- `rdbss!RxSetMinirdrCancelRoutine` at `0x14002f9cb`

## pseudocode

```c
void __fastcall MdaNotifyCompleteIrpList(__int64 a1, NTSTATUS a2)
{
  unsigned int v4; // r15d
  __int64 v5; // rdi
  __int64 *v6; // rsi
  struct _RX_CONTEXT *v7; // rbp
  __int64 *v8; // rax
  __int64 v9; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids);
  v4 = *(_DWORD *)(a1 + 624);
  v5 = a1 + 576;
  *(_QWORD *)(a1 + 624) = 0;
  *(_WORD *)(a1 + 592) &= ~2u;
  do
  {
    v6 = *(__int64 **)v5;
    v7 = *(struct _RX_CONTEXT **)(*(_QWORD *)v5 - 8LL);
    RxSetMinirdrCancelRoutine(v7, 0);
    v8 = *(__int64 **)v5;
    if ( *(_QWORD *)(*(_QWORD *)v5 + 8LL) != v5 || (v9 = *v8, *(__int64 **)(*v8 + 8) != v8) )
      __fastfail(3u);
    *(_QWORD *)v5 = v9;
    *(_QWORD *)(v9 + 8) = v5;
    MdaNotifyCompleteIrp(v7, a1, v4, a2);
    ExFreePoolWithTag(v6 - 1, 0);
  }
  while ( a2 && *(_QWORD *)v5 != v5 );
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids);
}

```

## disassembly

```asm
0x14002f954  push    rbx
0x14002f956  push    rbp
0x14002f957  push    rsi
0x14002f958  push    rdi
0x14002f959  push    r13
0x14002f95b  push    r14
0x14002f95d  push    r15
0x14002f95f  sub     rsp, 20h
0x14002f963  mov     r14d, edx
0x14002f966  mov     rbx, rcx
0x14002f969  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f970  lea     r13, WPP_GLOBAL_Control
0x14002f977  cmp     rcx, r13
0x14002f97a  jz      short loc_14002F99A
0x14002f97c  test    dword ptr [rcx+2Ch], 80000h
0x14002f983  jz      short loc_14002F99A
0x14002f985  mov     rcx, [rcx+18h]
0x14002f989  lea     r8, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids
0x14002f990  mov     edx, 21h ; '!'
0x14002f995  call    WPP_SF_
0x14002f99a  mov     r15d, [rbx+270h]
0x14002f9a1  lea     rdi, [rbx+240h]
0x14002f9a8  mov     eax, 0FFFDh
0x14002f9ad  mov     qword ptr [rbx+270h], 0
0x14002f9b8  and     [rbx+250h], ax
0x14002f9bf  mov     rsi, [rdi]
0x14002f9c2  xor     edx, edx; MRxCancelRoutine
0x14002f9c4  mov     rbp, [rsi-8]
0x14002f9c8  mov     rcx, rbp; RxContext
0x14002f9cb  call    cs:__imp_RxSetMinirdrCancelRoutine
0x14002f9d2  nop     dword ptr [rax+rax+00h]
0x14002f9d7  mov     rax, [rdi]
0x14002f9da  cmp     [rax+8], rdi
0x14002f9de  jnz     short loc_14002FA57
0x14002f9e0  mov     rdx, [rax]
0x14002f9e3  cmp     [rdx+8], rax
0x14002f9e7  jnz     short loc_14002FA57
0x14002f9e9  mov     [rdi], rdx
0x14002f9ec  mov     r9d, r14d
0x14002f9ef  mov     [rdx+8], rdi
0x14002f9f3  mov     r8d, r15d
0x14002f9f6  mov     rdx, rbx
0x14002f9f9  mov     rcx, rbp; RxContext
0x14002f9fc  call    MdaNotifyCompleteIrp
0x14002fa01  xor     edx, edx; Tag
0x14002fa03  lea     rcx, [rsi-8]; P
0x14002fa07  call    cs:__imp_ExFreePoolWithTag
0x14002fa0e  nop     dword ptr [rax+rax+00h]
0x14002fa13  test    r14d, r14d
0x14002fa16  jz      short loc_14002FA1D
0x14002fa18  cmp     [rdi], rdi
0x14002fa1b  jnz     short loc_14002F9BF
0x14002fa1d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fa24  cmp     rcx, r13
0x14002fa27  jz      short loc_14002FA47
0x14002fa29  test    dword ptr [rcx+2Ch], 80000h
0x14002fa30  jz      short loc_14002FA47
0x14002fa32  mov     rcx, [rcx+18h]
0x14002fa36  lea     r8, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids
0x14002fa3d  mov     edx, 22h ; '"'
0x14002fa42  call    WPP_SF_
0x14002fa47  add     rsp, 20h
0x14002fa4b  pop     r15
0x14002fa4d  pop     r14
0x14002fa4f  pop     r13
0x14002fa51  pop     rdi
0x14002fa52  pop     rsi
0x14002fa53  pop     rbp
0x14002fa54  pop     rbx
0x14002fa55  retn
0x14002fa57  mov     ecx, 3
0x14002fa5c  int     29h; Win8: RtlFailFast(ecx)
```
