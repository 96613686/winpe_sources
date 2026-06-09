# DfscNetUseTableLookup

- ea: `0x140026ed0`
- end: `0x140026f56`
- name: `DfscNetUseTableLookup`
- size: `134`
- prototype: `_QWORD *__fastcall(struct _RTL_AVL_TABLE *, void *, PVOID *, TABLE_SEARCH_RESULT *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14000141c`
- `0x140003a94`
- `0x14001134c`
- `0x140013db8`
- `0x140017458`
- `0x14002545c`

## callees

- `0x140004718`
- `0x140026ed0`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x140026f20`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x140026f20`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140026ede`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140026ede`

## pseudocode

```c
_QWORD *__fastcall DfscNetUseTableLookup(struct _RTL_AVL_TABLE *a1, void *a2, PVOID *a3, TABLE_SEARCH_RESULT *a4)
{
  int v4; // ebx
  _QWORD *result; // rax
  __int64 v6; // rdi

  v4 = (int)a2;
  if ( a3 )
    result = RtlLookupElementGenericTableFullAvl(a1, a2, a3, a4);
  else
    result = RtlLookupElementGenericTableAvl(a1, a2);
  if ( result )
  {
    v6 = result[4];
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 4));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_Zq(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        (unsigned int)WPP_4cbf8115eb6f3bebf2b1c99b588386c6_Traceguids,
        v4,
        v6);
    }
    return (_QWORD *)v6;
  }
  return result;
}

```

## disassembly

```asm
0x140026ed0  push    rbx
0x140026ed2  sub     rsp, 30h
0x140026ed6  mov     rbx, rdx
0x140026ed9  test    r8, r8
0x140026edc  jnz     short loc_140026F20
0x140026ede  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140026ee5  nop     dword ptr [rax+rax+00h]
0x140026eea  test    rax, rax
0x140026eed  jnz     short loc_140026EF6
0x140026eef  add     rsp, 30h
0x140026ef3  pop     rbx
0x140026ef4  retn
0x140026ef6  mov     [rsp+38h+arg_0], rdi
0x140026efb  mov     rdi, [rax+20h]
0x140026eff  lock inc dword ptr [rdi+4]
0x140026f03  mov     rcx, cs:WPP_GLOBAL_Control; Table
0x140026f0a  lea     rax, WPP_GLOBAL_Control
0x140026f11  cmp     rcx, rax
0x140026f14  jnz     short loc_140026F2E
0x140026f16  mov     rax, rdi
0x140026f19  mov     rdi, [rsp+38h+arg_0]
0x140026f1e  jmp     short loc_140026EEF
0x140026f20  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x140026f27  nop     dword ptr [rax+rax+00h]
0x140026f2c  jmp     short loc_140026EEA
0x140026f2e  test    dword ptr [rcx+2Ch], 400000h
0x140026f35  jz      short loc_140026F16
0x140026f37  mov     rcx, [rcx+18h]
0x140026f3b  lea     r8, WPP_4cbf8115eb6f3bebf2b1c99b588386c6_Traceguids
0x140026f42  mov     edx, 0Ah
0x140026f47  mov     [rsp+38h+var_18], rdi
0x140026f4c  mov     r9, rbx
0x140026f4f  call    WPP_SF_Zq
0x140026f54  jmp     short loc_140026F16
```
