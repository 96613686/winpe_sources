# FltpFreeFileNameInformation

- ea: `0x18005cf00`
- end: `0x18005cfda`
- name: `FltpFreeFileNameInformation`
- size: `218`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18005c8e0`

## callees

- `0x18002289c`
- `0x18005cf00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18005cf83`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005cf83`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18005cf59`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18005cfc5`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18005cf59`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18005cfc5`

## pseudocode

```c
void __fastcall FltpFreeFileNameInformation(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  int v4; // ecx
  __int64 v5; // rax
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rax
  ULONG v8; // edx
  unsigned int v9; // [rsp+28h] [rbp-20h]

  v3 = a1 - 80;
  if ( (byte_1800404C3 & 2) != 0 )
  {
    v9 = *(unsigned __int16 *)(v3 + 88) >> 1;
    McTemplateU0spdw_EtwWriteTransfer(
      (unsigned __int16)*(_DWORD *)(v3 + 72),
      v9,
      a3,
      a1 - 80,
      (unsigned __int16)*(_DWORD *)(v3 + 72),
      v9,
      *(_QWORD *)(v3 + 96));
  }
  v4 = *(_DWORD *)(v3 + 72);
  if ( (v4 & 0x1000) != 0 )
  {
    v5 = *(unsigned __int16 *)(v3 + 2);
    if ( (unsigned __int16)v5 <= 0x150u )
      LOWORD(v6) = 0;
    else
      v6 = (unsigned __int64)(v5 - 273) >> 6;
    v7 = (unsigned __int64)(unsigned __int16)v6 << 7;
    if ( (v4 & 0x800) != 0 )
      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)qword_18003F840 + v7), (PVOID)v3);
    else
      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)qword_18003F4C0 + v7), (PVOID)v3);
  }
  else
  {
    if ( (v4 & 0x800) != 0 )
      v8 = 946752838;
    else
      v8 = 846089542;
    ExFreePoolWithTag((PVOID)v3, v8);
  }
}

```

## disassembly

```asm
0x18005cf00  mov     [rsp+arg_0], rbx
0x18005cf05  push    rdi
0x18005cf06  sub     rsp, 40h
0x18005cf0a  test    cs:byte_1800404C3, 2
0x18005cf11  lea     rdi, [rcx-50h]
0x18005cf15  jnz     short loc_18005CF91
0x18005cf17  mov     ecx, [rdi+48h]
0x18005cf1a  bt      ecx, 0Ch
0x18005cf1e  jnb     short loc_18005CF75
0x18005cf20  movzx   eax, word ptr [rdi+2]
0x18005cf24  mov     edx, 150h
0x18005cf29  cmp     ax, dx
0x18005cf2c  jbe     short loc_18005CF71
0x18005cf2e  sub     rax, 111h
0x18005cf34  shr     rax, 6
0x18005cf38  movzx   eax, ax
0x18005cf3b  mov     rdx, rdi; Entry
0x18005cf3e  shl     rax, 7
0x18005cf42  bt      ecx, 0Bh
0x18005cf46  lea     rcx, FltGlobals
0x18005cf4d  jb      short loc_18005CFBB
0x18005cf4f  add     rcx, 0D80h
0x18005cf56  add     rcx, rax; Lookaside
0x18005cf59  call    cs:__imp_ExFreeToPagedLookasideList
0x18005cf60  nop     dword ptr [rax+rax+00h]
0x18005cf65  mov     rbx, [rsp+48h+arg_0]
0x18005cf6a  add     rsp, 40h
0x18005cf6e  pop     rdi
0x18005cf6f  retn
0x18005cf71  xor     eax, eax
0x18005cf73  jmp     short loc_18005CF38
0x18005cf75  bt      ecx, 0Bh
0x18005cf79  mov     rcx, rdi; P
0x18005cf7c  jb      short loc_18005CFD3
0x18005cf7e  mov     edx, 326E4D46h; Tag
0x18005cf83  call    cs:__imp_ExFreePoolWithTag
0x18005cf8a  nop     dword ptr [rax+rax+00h]
0x18005cf8f  jmp     short loc_18005CF65
0x18005cf91  mov     eax, [rdi+48h]
0x18005cf94  mov     r9, rdi
0x18005cf97  movzx   edx, word ptr [rdi+58h]
0x18005cf9b  movzx   ecx, ax
0x18005cf9e  mov     rax, [rdi+60h]
0x18005cfa2  mov     [rsp+48h+var_18], rax
0x18005cfa7  shr     edx, 1
0x18005cfa9  mov     [rsp+48h+var_20], edx
0x18005cfad  mov     [rsp+48h+var_28], ecx
0x18005cfb1  call    McTemplateU0spdw_EtwWriteTransfer
0x18005cfb6  jmp     loc_18005CF17
0x18005cfbb  add     rcx, 1100h
0x18005cfc2  add     rcx, rax; Lookaside
0x18005cfc5  call    cs:__imp_ExFreeToPagedLookasideList
0x18005cfcc  nop     dword ptr [rax+rax+00h]
0x18005cfd1  jmp     short loc_18005CF65
0x18005cfd3  mov     edx, 386E4D46h
0x18005cfd8  jmp     short loc_18005CF83
```
