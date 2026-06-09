# CFtpFolder::_GetBindCtx(IBindCtx * *)

- ea: `0x180018244`
- end: `0x1800182bd`
- name: `?_GetBindCtx@CFtpFolder@@IEAAJPEAPEAUIBindCtx@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(CFtpFolder *__hidden this, struct IBindCtx **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018568`
- `0x180018ee4`

## callees

- `0x180018244`
- `0x180028010`

## import_xrefs

- `ole32!CreateBindCtx` at `0x18001825b`
- `ole32!CreateBindCtx` at `0x18001825b`

## string_xrefs

- `0x180018271`: `Skip Binding CLSID`

## pseudocode

```c
__int64 __fastcall CFtpFolder::_GetBindCtx(CFtpFolder *this, struct IBindCtx **a2)
{
  HRESULT BindCtx; // edi
  LPBC v5; // rcx

  BindCtx = CreateBindCtx(0, a2);
  if ( BindCtx >= 0 )
  {
    BindCtx = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, unsigned __int64))(*a2)->lpVtbl->RegisterObjectParam)(
                *a2,
                L"Skip Binding CLSID",
                ((unsigned __int64)this + 80) & -(__int64)(this != 0));
    if ( BindCtx < 0 )
    {
      v5 = *a2;
      *a2 = 0;
      if ( v5 )
        ((void (__fastcall *)(LPBC))v5->lpVtbl->Release)(v5);
    }
  }
  return (unsigned int)BindCtx;
}

```

## disassembly

```asm
0x180018244  mov     [rsp+arg_0], rbx
0x180018249  mov     [rsp+arg_8], rsi
0x18001824e  push    rdi
0x18001824f  sub     rsp, 20h
0x180018253  mov     rsi, rcx
0x180018256  mov     rbx, rdx
0x180018259  xor     ecx, ecx; reserved
0x18001825b  call    cs:__imp_CreateBindCtx
0x180018261  mov     edi, eax
0x180018263  test    eax, eax
0x180018265  js      short loc_1800182AB
0x180018267  mov     rcx, [rbx]
0x18001826a  lea     rax, [rsi+50h]
0x18001826e  neg     rsi
0x180018271  lea     rdx, aSkipBindingCls; "Skip Binding CLSID"
0x180018278  sbb     r8, r8
0x18001827b  mov     r9, [rcx]
0x18001827e  and     r8, rax
0x180018281  mov     rax, [r9+48h]
0x180018285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001828a  mov     edi, eax
0x18001828c  test    eax, eax
0x18001828e  jns     short loc_1800182AB
0x180018290  mov     rcx, [rbx]
0x180018293  mov     qword ptr [rbx], 0
0x18001829a  test    rcx, rcx
0x18001829d  jz      short loc_1800182AB
0x18001829f  mov     rax, [rcx]
0x1800182a2  mov     rax, [rax+10h]
0x1800182a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182ab  mov     rbx, [rsp+28h+arg_0]
0x1800182b0  mov     eax, edi
0x1800182b2  mov     rsi, [rsp+28h+arg_8]
0x1800182b7  add     rsp, 20h
0x1800182bb  pop     rdi
0x1800182bc  retn
```
