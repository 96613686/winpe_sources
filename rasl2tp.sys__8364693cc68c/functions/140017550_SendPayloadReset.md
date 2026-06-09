# SendPayloadReset

- ea: `0x140017550`
- end: `0x1400175e8`
- name: `SendPayloadReset`
- size: `152`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x140003080`
- `0x140017550`
- `0x140017fa0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017577`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017577`

## pseudocode

```c
__int64 __fastcall SendPayloadReset(PVOID Entry, __int64 a2, __int64 a3, unsigned __int16 *a4)
{
  unsigned int v4; // ebx
  int v5; // esi

  v4 = *a4;
  v5 = a2;
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a2 + 24) + 960LL), Entry);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids, v4);
  }
  return SendZlb(v5, a3, (unsigned __int16)v4, *(unsigned __int16 *)(a3 + 280), 1);
}

```

## disassembly

```asm
0x140017550  mov     [rsp+arg_0], rbx
0x140017555  mov     [rsp+arg_8], rsi
0x14001755a  push    rdi
0x14001755b  sub     rsp, 30h
0x14001755f  movzx   ebx, word ptr [r9]
0x140017563  mov     rsi, rdx
0x140017566  mov     rdx, rcx; Entry
0x140017569  mov     rdi, r8
0x14001756c  mov     rcx, [rsi+18h]
0x140017570  add     rcx, 3C0h; Lookaside
0x140017577  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001757e  nop     dword ptr [rax+rax+00h]
0x140017583  mov     rcx, cs:WPP_GLOBAL_Control
0x14001758a  lea     rax, WPP_GLOBAL_Control
0x140017591  cmp     rcx, rax
0x140017594  jz      short loc_1400175BB
0x140017596  mov     eax, [rcx+2Ch]
0x140017599  test    al, 10h
0x14001759b  jz      short loc_1400175BB
0x14001759d  cmp     byte ptr [rcx+29h], 1
0x1400175a1  jb      short loc_1400175BB
0x1400175a3  mov     rcx, [rcx+18h]
0x1400175a7  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x1400175ae  mov     r9d, ebx
0x1400175b1  mov     edx, 1Dh
0x1400175b6  call    WPP_SF_d
0x1400175bb  movzx   r9d, word ptr [rdi+118h]
0x1400175c3  movzx   r8d, bx
0x1400175c7  mov     rdx, rdi
0x1400175ca  mov     [rsp+38h+var_18], 1
0x1400175cf  mov     rcx, rsi
0x1400175d2  call    SendZlb
0x1400175d7  mov     rbx, [rsp+38h+arg_0]
0x1400175dc  mov     rsi, [rsp+38h+arg_8]
0x1400175e1  add     rsp, 30h
0x1400175e5  pop     rdi
0x1400175e6  retn
```
