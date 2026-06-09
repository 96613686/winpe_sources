# Enrollment::get_SspHyperLink(ushort * *)

- ea: `0x1800106d0`
- end: `0x1800106fd`
- name: `?get_SspHyperLink@Enrollment@@UEAAJPEAPEAG@Z`
- size: `45`
- prototype: `__int64 __fastcall(Enrollment *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800106d0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800106e5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800106e5`

## pseudocode

```c
__int64 __fastcall Enrollment::get_SspHyperLink(Enrollment *this, unsigned __int16 **a2)
{
  const OLECHAR *v2; // rcx

  v2 = (const OLECHAR *)*((_QWORD *)this + 229);
  if ( !v2 )
    return 2147500037LL;
  *a2 = SysAllocString(v2);
  return 0;
}

```

## disassembly

```asm
0x1800106d0  push    rbx
0x1800106d2  sub     rsp, 20h
0x1800106d6  mov     rcx, [rcx+728h]; psz
0x1800106dd  mov     rbx, rdx
0x1800106e0  test    rcx, rcx
0x1800106e3  jz      short loc_1800106F2
0x1800106e5  call    cs:__imp_SysAllocString
0x1800106eb  mov     [rbx], rax
0x1800106ee  xor     eax, eax
0x1800106f0  jmp     short loc_1800106F7
0x1800106f2  mov     eax, 80004005h
0x1800106f7  add     rsp, 20h
0x1800106fb  pop     rbx
0x1800106fc  retn
```
