# CreatePropertySheetPageW

- ea: `0x18001c400`
- end: `0x18001c495`
- name: `CreatePropertySheetPageW`
- size: `149`
- prototype: `HPROPSHEETPAGE __stdcall(LPCPROPSHEETPAGEW constPropSheetPagePointer)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016120`

## callees

- `0x18001c0c4`
- `0x18001c400`
- `0x18001cc10`
- `0x18001f010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x18001c481`
- `KERNEL32!DeactivateActCtx` at `0x18001c481`

## string_xrefs

- `0x18001c42f`: `CreatePropertySheetPageW`

## pseudocode

```c
HPROPSHEETPAGE __stdcall CreatePropertySheetPageW(LPCPROPSHEETPAGEW constPropSheetPagePointer)
{
  struct _PSP *v2; // rdi
  __int64 (__fastcall *v3)(LPCPROPSHEETPAGEW); // rax
  ULONG_PTR ulCookie; // [rsp+38h] [rbp+10h] BYREF

  ulCookie = 0;
  v2 = 0;
  SHActivateContext(&ulCookie);
  v3 = (__int64 (__fastcall *)(LPCPROPSHEETPAGEW))qword_180028260;
  if ( qword_180028260 == -1 )
  {
    GetProcFromComCtl32(&qword_180028260, "CreatePropertySheetPageW");
    v3 = (__int64 (__fastcall *)(LPCPROPSHEETPAGEW))qword_180028260;
  }
  if ( v3 )
  {
    if ( constPropSheetPagePointer->dwSize > 0x58 )
    {
      constPropSheetPagePointer->dwFlags |= 0x4000u;
      constPropSheetPagePointer->hActCtx = g_hActCtx;
      v3 = (__int64 (__fastcall *)(LPCPROPSHEETPAGEW))qword_180028260;
    }
    v2 = (struct _PSP *)v3(constPropSheetPagePointer);
  }
  if ( ulCookie )
    DeactivateActCtx(0, ulCookie);
  return v2;
}

```

## disassembly

```asm
0x18001c400  mov     [rsp+arg_0], rbx
0x18001c405  push    rdi
0x18001c406  sub     rsp, 20h
0x18001c40a  mov     rbx, rcx
0x18001c40d  mov     [rsp+28h+ulCookie], 0
0x18001c416  lea     rcx, [rsp+28h+ulCookie]
0x18001c41b  xor     edi, edi
0x18001c41d  call    SHActivateContext
0x18001c422  mov     rax, cs:qword_180028260
0x18001c429  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c42d  jnz     short loc_18001C449
0x18001c42f  lea     rdx, aCreateproperty; "CreatePropertySheetPageW"
0x18001c436  lea     rcx, qword_180028260
0x18001c43d  call    _GetProcFromComCtl32
0x18001c442  mov     rax, cs:qword_180028260
0x18001c449  test    rax, rax
0x18001c44c  jz      short loc_18001C475
0x18001c44e  cmp     dword ptr [rbx], 58h ; 'X'
0x18001c451  jbe     short loc_18001C46A
0x18001c453  bts     dword ptr [rbx+4], 0Eh
0x18001c458  mov     rax, cs:g_hActCtx
0x18001c45f  mov     [rbx+58h], rax
0x18001c463  mov     rax, cs:qword_180028260
0x18001c46a  mov     rcx, rbx
0x18001c46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c472  mov     rdi, rax
0x18001c475  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x18001c47a  test    rdx, rdx
0x18001c47d  jz      short loc_18001C487
0x18001c47f  xor     ecx, ecx; dwFlags
0x18001c481  call    cs:__imp_DeactivateActCtx
0x18001c487  mov     rbx, [rsp+28h+arg_0]
0x18001c48c  mov     rax, rdi
0x18001c48f  add     rsp, 20h
0x18001c493  pop     rdi
0x18001c494  retn
```
