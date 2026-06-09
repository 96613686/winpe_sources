# CKsInputPin::QueryId(ushort * *)

- ea: `0x1800288f0`
- end: `0x180028949`
- name: `?QueryId@CKsInputPin@@UEAAJPEAPEAG@Z`
- size: `89`
- prototype: `__int64 __fastcall(CKsInputPin *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800288f0`
- `0x180028f34`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180028905`
- `ole32!CoTaskMemAlloc` at `0x180028905`

## pseudocode

```c
__int64 __fastcall CKsInputPin::QueryId(CKsInputPin *this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rax

  v4 = (unsigned __int16 *)CoTaskMemAlloc(0x16u);
  *a2 = v4;
  if ( !v4 )
    return 2147942414LL;
  StringCbPrintfW(v4, 0x16u, L"%u", LODWORD(this->m_DataTypeHandler));
  return 0;
}

```

## disassembly

```asm
0x1800288f0  mov     [rsp+arg_0], rbx
0x1800288f5  push    rdi
0x1800288f6  sub     rsp, 20h
0x1800288fa  mov     rdi, rcx
0x1800288fd  mov     rbx, rdx
0x180028900  mov     ecx, 16h; cb
0x180028905  call    cs:__imp_CoTaskMemAlloc
0x18002890c  nop     dword ptr [rax+rax+00h]
0x180028911  mov     [rbx], rax
0x180028914  test    rax, rax
0x180028917  jz      short loc_180028938
0x180028919  mov     r9d, [rdi+180h]
0x180028920  lea     r8, aU; "%u"
0x180028927  mov     edx, 16h; unsigned __int64
0x18002892c  mov     rcx, rax; unsigned __int16 *
0x18002892f  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028934  xor     eax, eax
0x180028936  jmp     short loc_18002893D
0x180028938  mov     eax, 8007000Eh
0x18002893d  mov     rbx, [rsp+28h+arg_0]
0x180028942  add     rsp, 20h
0x180028946  pop     rdi
0x180028947  retn
```
