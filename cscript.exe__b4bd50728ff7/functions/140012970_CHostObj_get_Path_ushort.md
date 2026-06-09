# CHostObj::get_Path(ushort * *)

- ea: `0x140012970`
- end: `0x1400129a7`
- name: `?get_Path@CHostObj@@UEAAJPEAPEAG@Z`
- size: `55`
- prototype: `__int64 __fastcall(CHostObj *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140012970`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140012989`
- `OLEAUT32!__imp_SysAllocString` at `0x140012989`

## pseudocode

```c
__int64 __fastcall CHostObj::get_Path(const OLECHAR **this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rax
  unsigned int v5; // ecx

  if ( !a2 )
    return 2147500035LL;
  v4 = SysAllocString(this[11]);
  v5 = 0;
  *a2 = v4;
  if ( !v4 )
    return (unsigned int)-2147024882;
  return v5;
}

```

## disassembly

```asm
0x140012970  push    rbx
0x140012972  sub     rsp, 20h
0x140012976  mov     rbx, rdx
0x140012979  test    rdx, rdx
0x14001297c  jnz     short loc_140012985
0x14001297e  mov     eax, 80004003h
0x140012983  jmp     short loc_1400129A1
0x140012985  mov     rcx, [rcx+58h]; psz
0x140012989  call    cs:__imp_SysAllocString
0x14001298f  xor     ecx, ecx
0x140012991  mov     edx, 8007000Eh
0x140012996  test    rax, rax
0x140012999  mov     [rbx], rax
0x14001299c  cmovz   ecx, edx
0x14001299f  mov     eax, ecx
0x1400129a1  add     rsp, 20h
0x1400129a5  pop     rbx
0x1400129a6  retn
```
