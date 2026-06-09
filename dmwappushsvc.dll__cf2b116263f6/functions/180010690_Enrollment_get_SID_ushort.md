# Enrollment::get_SID(ushort * *)

- ea: `0x180010690`
- end: `0x1800106bd`
- name: `?get_SID@Enrollment@@UEAAJPEAPEAG@Z`
- size: `45`
- prototype: `__int64 __fastcall(Enrollment *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180010690`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800106a5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800106a5`

## pseudocode

```c
__int64 __fastcall Enrollment::get_SID(Enrollment *this, unsigned __int16 **a2)
{
  const OLECHAR *v2; // rcx

  v2 = (const OLECHAR *)*((_QWORD *)this + 225);
  if ( !v2 )
    return 2147500037LL;
  *a2 = SysAllocString(v2);
  return 0;
}

```

## disassembly

```asm
0x180010690  push    rbx
0x180010692  sub     rsp, 20h
0x180010696  mov     rcx, [rcx+708h]; psz
0x18001069d  mov     rbx, rdx
0x1800106a0  test    rcx, rcx
0x1800106a3  jz      short loc_1800106B2
0x1800106a5  call    cs:__imp_SysAllocString
0x1800106ab  mov     [rbx], rax
0x1800106ae  xor     eax, eax
0x1800106b0  jmp     short loc_1800106B7
0x1800106b2  mov     eax, 80004005h
0x1800106b7  add     rsp, 20h
0x1800106bb  pop     rbx
0x1800106bc  retn
```
