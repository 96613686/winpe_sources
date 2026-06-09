# MyComparePBaseObject(void const *,void const *)

- ea: `0x1800210b0`
- end: `0x180021110`
- name: `?MyComparePBaseObject@@YAHPEBX0@Z`
- size: `96`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007810`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1800210fc`
- `KERNEL32!CompareStringW` at `0x1800210fc`

## pseudocode

```c
__int64 __fastcall MyComparePBaseObject(CMDBaseObject **a1, CMDBaseObject **a2)
{
  CMDBaseObject *v2; // rdi
  const WCHAR *lpString2; // rbx
  const WCHAR *Name; // rax

  v2 = *a1;
  lpString2 = (const WCHAR *)CMDBaseObject::GetName(*a2, 1, 0);
  Name = (const WCHAR *)CMDBaseObject::GetName(v2, 1, 0);
  return (unsigned int)(CompareStringW(0x800u, 0x1001u, Name, -1, lpString2, -1) - 2);
}

```

## disassembly

```asm
0x1800210b0  mov     [rsp+arg_0], rbx
0x1800210b5  push    rdi
0x1800210b6  sub     rsp, 30h
0x1800210ba  mov     rdi, [rcx]
0x1800210bd  mov     rax, rdx
0x1800210c0  xor     r8d, r8d; unsigned int *
0x1800210c3  mov     rcx, [rax]; this
0x1800210c6  lea     edx, [r8+1]; int
0x1800210ca  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x1800210cf  xor     r8d, r8d; unsigned int *
0x1800210d2  mov     rcx, rdi; this
0x1800210d5  mov     rbx, rax
0x1800210d8  lea     edx, [r8+1]; int
0x1800210dc  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x1800210e1  or      r9d, 0FFFFFFFFh; cchCount1
0x1800210e5  mov     r8, rax; lpString1
0x1800210e8  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x1800210ed  mov     edx, 1001h; dwCmpFlags
0x1800210f2  mov     ecx, 800h; Locale
0x1800210f7  mov     [rsp+38h+lpString2], rbx; lpString2
0x1800210fc  call    cs:__imp_CompareStringW
0x180021102  mov     rbx, [rsp+38h+arg_0]
0x180021107  sub     eax, 2
0x18002110a  add     rsp, 30h
0x18002110e  pop     rdi
0x18002110f  retn
```
