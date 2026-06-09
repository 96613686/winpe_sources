# Rdp::Stack::Shim::CAdapterShim::OnEncoderEvent(Rdp::Avenc::AVENC_ENCODER_EVENT_ID)

- ea: `0x1800196c0`
- end: `0x180019713`
- name: `?OnEncoderEvent@CAdapterShim@Shim@Stack@Rdp@@UEAAJW4AVENC_ENCODER_EVENT_ID@Avenc@4@@Z`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180011b1c`
- `0x1800196c0`
- `0x18002a010`

## string_xrefs

- `0x1800196eb`: `Failed to update static frame re-encode count`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Shim::CAdapterShim::OnEncoderEvent(__int64 a1, int a2)
{
  int v2; // ebx
  const char *v4; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = -2147024809;
  if ( a2 == 1 )
  {
    v2 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 64) + 72LL))(*(_QWORD *)(a1 + 64));
    if ( v2 < 0 )
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x432,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
        (const char *)(unsigned int)v2,
        (int)"Failed to update static frame re-encode count",
        v4);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800196c0  push    rbx
0x1800196c2  sub     rsp, 30h
0x1800196c6  mov     ebx, 80070057h
0x1800196cb  cmp     edx, 1
0x1800196ce  jnz     short loc_18001970B
0x1800196d0  mov     rcx, [rcx+40h]
0x1800196d4  mov     rax, [rcx]
0x1800196d7  mov     rax, [rax+48h]
0x1800196db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196e0  mov     ebx, eax
0x1800196e2  test    eax, eax
0x1800196e4  jns     short loc_18001970B
0x1800196e6  mov     rcx, [rsp+38h]; this
0x1800196eb  lea     rax, aFailedToUpdate; "Failed to update static frame re-encode"...
0x1800196f2  mov     r9d, ebx; char *
0x1800196f5  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800196fa  lea     r8, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180019701  mov     edx, 432h; void *
0x180019706  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001970b  mov     eax, ebx
0x18001970d  add     rsp, 30h
0x180019711  pop     rbx
0x180019712  retn
```
