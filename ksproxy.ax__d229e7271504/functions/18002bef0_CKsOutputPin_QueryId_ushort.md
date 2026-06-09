# CKsOutputPin::QueryId(ushort * *)

- ea: `0x18002bef0`
- end: `0x18002bf49`
- name: `?QueryId@CKsOutputPin@@UEAAJPEAPEAG@Z`
- size: `89`
- prototype: `__int64 __fastcall(CKsOutputPin *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180028f34`
- `0x18002bef0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18002bf05`
- `ole32!CoTaskMemAlloc` at `0x18002bf05`

## pseudocode

```c
__int64 __fastcall CKsOutputPin::QueryId(CKsOutputPin *this, unsigned __int16 **a2)
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
0x18002bef0  mov     [rsp+arg_0], rbx
0x18002bef5  push    rdi
0x18002bef6  sub     rsp, 20h
0x18002befa  mov     rdi, rcx
0x18002befd  mov     rbx, rdx
0x18002bf00  mov     ecx, 16h; cb
0x18002bf05  call    cs:__imp_CoTaskMemAlloc
0x18002bf0c  nop     dword ptr [rax+rax+00h]
0x18002bf11  mov     [rbx], rax
0x18002bf14  test    rax, rax
0x18002bf17  jz      short loc_18002BF38
0x18002bf19  mov     r9d, [rdi+230h]
0x18002bf20  lea     r8, aU; "%u"
0x18002bf27  mov     edx, 16h; unsigned __int64
0x18002bf2c  mov     rcx, rax; unsigned __int16 *
0x18002bf2f  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bf34  xor     eax, eax
0x18002bf36  jmp     short loc_18002BF3D
0x18002bf38  mov     eax, 8007000Eh
0x18002bf3d  mov     rbx, [rsp+28h+arg_0]
0x18002bf42  add     rsp, 20h
0x18002bf46  pop     rdi
0x18002bf47  retn
```
