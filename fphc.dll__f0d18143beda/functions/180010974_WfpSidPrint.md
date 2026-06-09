# WfpSidPrint

- ea: `0x180010974`
- end: `0x1800109f0`
- name: `WfpSidPrint`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000f2d8`
- `0x18000f7f0`

## callees

- `0x180010974`
- `0x180012010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800109c0`
- `ntdll!RtlFreeUnicodeString` at `0x1800109c0`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001099a`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001099a`

## pseudocode

```c
void __fastcall WfpSidPrint(void (__fastcall *a1)(__int64, const wchar_t *), __int64 a2, void *a3)
{
  NTSTATUS v5; // eax
  const wchar_t *v6; // rdx
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-18h] BYREF

  UnicodeString = 0;
  v5 = RtlConvertSidToUnicodeString(&UnicodeString, a3, 1u);
  if ( v5 < 0 )
  {
    v6 = L"<not enough memory>";
    if ( v5 != -1073741801 )
      v6 = L"<invalid>";
    a1(a2, v6);
  }
  else
  {
    ((void (*)(__int64, const wchar_t *, ...))a1)(a2, L"%s", UnicodeString.Buffer);
    RtlFreeUnicodeString(&UnicodeString);
  }
}

```

## disassembly

```asm
0x180010974  mov     [rsp+arg_0], rbx
0x180010979  push    rdi
0x18001097a  sub     rsp, 30h
0x18001097e  mov     rax, r8
0x180010981  mov     rbx, rdx
0x180010984  mov     rdi, rcx
0x180010987  xorps   xmm0, xmm0
0x18001098a  mov     rdx, rax; Sid
0x18001098d  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x180010992  mov     r8b, 1; AllocateDestinationString
0x180010995  movups  xmmword ptr [rsp+38h+UnicodeString.Length], xmm0
0x18001099a  call    cs:__imp_RtlConvertSidToUnicodeString
0x1800109a0  mov     rcx, rbx
0x1800109a3  test    eax, eax
0x1800109a5  js      short loc_1800109C8
0x1800109a7  mov     r8, [rsp+38h+UnicodeString.Buffer]
0x1800109ac  lea     rdx, aS_1; "%s"
0x1800109b3  mov     rax, rdi
0x1800109b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109bb  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x1800109c0  call    cs:__imp_RtlFreeUnicodeString
0x1800109c6  jmp     short loc_1800109E5
0x1800109c8  cmp     eax, 0C0000017h
0x1800109cd  lea     rdx, aNotEnoughMemor_0; "<not enough memory>"
0x1800109d4  mov     rax, rdi
0x1800109d7  jz      short loc_1800109E0
0x1800109d9  lea     rdx, aInvalid; "<invalid>"
0x1800109e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109e5  mov     rbx, [rsp+38h+arg_0]
0x1800109ea  add     rsp, 30h
0x1800109ee  pop     rdi
0x1800109ef  retn
```
