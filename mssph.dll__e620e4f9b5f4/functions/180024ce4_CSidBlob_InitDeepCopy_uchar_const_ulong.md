# CSidBlob::InitDeepCopy(uchar const *,ulong)

- ea: `0x180024ce4`
- end: `0x180024d42`
- name: `?InitDeepCopy@CSidBlob@@QEAAXPEBEK@Z`
- size: `94`
- prototype: `void(CSidBlob *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180021770`
- `0x1800219a0`

## callees

- `0x18000e7fc`
- `0x180011135`
- `0x180024ce4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024cff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024cff`

## string_xrefs

- `0x180024d13`: `onecoreuap\base\appmodel\search\mssrch\common\sssutill\efssids.cxx`

## pseudocode

```c
void __fastcall CSidBlob::InitDeepCopy(CSidBlob *this, const unsigned __int8 *a2, unsigned int a3)
{
  void *v5; // rax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_DWORD *)this = a3;
  if ( a3 )
  {
    v5 = CoTaskMemAlloc(a3);
    *((_QWORD *)this + 1) = v5;
    if ( !v5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\common\\sssutill\\efssids.cxx",
        (const char *)0x8007000ELL,
        v6);
    memcpy_0(v5, a2, *(unsigned int *)this);
  }
}

```

## disassembly

```asm
0x180024ce4  mov     [rsp+arg_0], rbx
0x180024ce9  push    rdi; int
0x180024cea  sub     rsp, 20h
0x180024cee  mov     [rcx], r8d
0x180024cf1  mov     rdi, rdx
0x180024cf4  mov     rbx, rcx
0x180024cf7  test    r8d, r8d
0x180024cfa  jz      short loc_180024D37
0x180024cfc  mov     ecx, r8d; cb
0x180024cff  call    cs:__imp_CoTaskMemAlloc
0x180024d05  mov     [rbx+8], rax
0x180024d09  test    rax, rax
0x180024d0c  jnz     short loc_180024D29
0x180024d0e  mov     rcx, [rsp+28h]; this
0x180024d13  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180024d1a  mov     r9d, 8007000Eh; char *
0x180024d20  lea     edx, [rax+25h]; void *
0x180024d23  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024d29  mov     r8d, [rbx]; Size
0x180024d2c  mov     rdx, rdi; Src
0x180024d2f  mov     rcx, rax; void *
0x180024d32  call    memcpy_0
0x180024d37  mov     rbx, [rsp+28h+arg_0]
0x180024d3c  add     rsp, 20h
0x180024d40  pop     rdi
0x180024d41  retn
```
