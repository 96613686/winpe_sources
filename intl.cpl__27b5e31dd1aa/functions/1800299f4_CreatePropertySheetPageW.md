# CreatePropertySheetPageW

- ea: `0x1800299f4`
- end: `0x180029a81`
- name: `CreatePropertySheetPageW`
- size: `141`
- prototype: `HPROPSHEETPAGE __stdcall(LPCPROPSHEETPAGEW constPropSheetPagePointer)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800243f8`

## callees

- `0x180029800`
- `0x180029870`
- `0x1800299f4`
- `0x180029e64`
- `0x18002b010`

## string_xrefs

- `0x180029a23`: `CreatePropertySheetPageW`

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
  v3 = (__int64 (__fastcall *)(LPCPROPSHEETPAGEW))qword_18003A7C0;
  if ( qword_18003A7C0 == -1 )
  {
    GetProcFromComCtl32(&qword_18003A7C0, "CreatePropertySheetPageW");
    v3 = (__int64 (__fastcall *)(LPCPROPSHEETPAGEW))qword_18003A7C0;
  }
  if ( v3 )
  {
    if ( constPropSheetPagePointer->dwSize > 0x58 )
    {
      constPropSheetPagePointer->dwFlags |= 0x4000u;
      constPropSheetPagePointer->hActCtx = g_hActCtx;
      v3 = (__int64 (__fastcall *)(LPCPROPSHEETPAGEW))qword_18003A7C0;
    }
    v2 = (struct _PSP *)v3(constPropSheetPagePointer);
  }
  SHDeactivateContext(ulCookie);
  return v2;
}

```

## disassembly

```asm
0x1800299f4  mov     [rsp+arg_0], rbx
0x1800299f9  push    rdi
0x1800299fa  sub     rsp, 20h
0x1800299fe  mov     rbx, rcx
0x180029a01  mov     [rsp+28h+ulCookie], 0
0x180029a0a  lea     rcx, [rsp+28h+ulCookie]
0x180029a0f  xor     edi, edi
0x180029a11  call    SHActivateContext
0x180029a16  mov     rax, cs:qword_18003A7C0
0x180029a1d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029a21  jnz     short loc_180029A3D
0x180029a23  lea     rdx, aCreateproperty; "CreatePropertySheetPageW"
0x180029a2a  lea     rcx, qword_18003A7C0
0x180029a31  call    _GetProcFromComCtl32
0x180029a36  mov     rax, cs:qword_18003A7C0
0x180029a3d  test    rax, rax
0x180029a40  jz      short loc_180029A69
0x180029a42  cmp     dword ptr [rbx], 58h ; 'X'
0x180029a45  jbe     short loc_180029A5E
0x180029a47  bts     dword ptr [rbx+4], 0Eh
0x180029a4c  mov     rax, cs:g_hActCtx
0x180029a53  mov     [rbx+58h], rax
0x180029a57  mov     rax, cs:qword_18003A7C0
0x180029a5e  mov     rcx, rbx
0x180029a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a66  mov     rdi, rax
0x180029a69  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x180029a6e  call    SHDeactivateContext
0x180029a73  mov     rbx, [rsp+28h+arg_0]
0x180029a78  mov     rax, rdi
0x180029a7b  add     rsp, 20h
0x180029a7f  pop     rdi
0x180029a80  retn
```
