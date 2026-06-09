# CSidContainer::Allocate(ulong)

- ea: `0x180024bec`
- end: `0x180024c6d`
- name: `?Allocate@CSidContainer@@QEAAXK@Z`
- size: `129`
- prototype: `void __fastcall(CSidContainer *this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180021770`
- `0x1800219a0`

## callees

- `0x18000e7fc`
- `0x180024bec`
- `0x180024c74`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024c0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024c0d`

## string_xrefs

- `0x180024c20`: `onecoreuap\base\appmodel\search\mssrch\common\sssutill\efssids.cxx`

## pseudocode

```c
void __fastcall CSidContainer::Allocate(CSidContainer *this, unsigned int a2)
{
  LPVOID v4; // rax
  unsigned int i; // edx
  __int64 v6; // rcx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  CSidContainer::FreeBlobs(this);
  *((_DWORD *)this + 2) = a2;
  if ( a2 )
  {
    v4 = CoTaskMemAlloc(16LL * a2);
    *(_QWORD *)this = v4;
    if ( !v4 )
    {
      *((_DWORD *)this + 2) = 0;
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\common\\sssutill\\efssids.cxx",
        (const char *)0x8007000ELL,
        v7);
    }
    for ( i = 0; i < *((_DWORD *)this + 2); *(_QWORD *)(*(_QWORD *)this + 8 * v6 + 8) = 0 )
    {
      v6 = i++;
      v6 *= 2;
      *(_DWORD *)(*(_QWORD *)this + 8 * v6) = 0;
    }
  }
}

```

## disassembly

```asm
0x180024bec  mov     [rsp+arg_0], rbx
0x180024bf1  push    rdi; int
0x180024bf2  sub     rsp, 20h
0x180024bf6  mov     edi, edx
0x180024bf8  mov     rbx, rcx
0x180024bfb  call    ?FreeBlobs@CSidContainer@@QEAAXXZ; CSidContainer::FreeBlobs(void)
0x180024c00  mov     [rbx+8], edi
0x180024c03  test    edi, edi
0x180024c05  jz      short loc_180024C62
0x180024c07  mov     ecx, edi
0x180024c09  shl     rcx, 4; cb
0x180024c0d  call    cs:__imp_CoTaskMemAlloc
0x180024c13  mov     [rbx], rax
0x180024c16  test    rax, rax
0x180024c19  jnz     short loc_180024C39
0x180024c1b  mov     rcx, [rsp+28h]; this
0x180024c20  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180024c27  mov     r9d, 8007000Eh; char *
0x180024c2d  mov     [rbx+8], eax
0x180024c30  lea     edx, [rax+63h]; void *
0x180024c33  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024c39  xor     edx, edx
0x180024c3b  cmp     [rbx+8], edx
0x180024c3e  jbe     short loc_180024C62
0x180024c40  mov     rax, [rbx]
0x180024c43  mov     ecx, edx
0x180024c45  inc     edx
0x180024c47  add     rcx, rcx
0x180024c4a  mov     dword ptr [rax+rcx*8], 0
0x180024c51  mov     rax, [rbx]
0x180024c54  mov     qword ptr [rax+rcx*8+8], 0
0x180024c5d  cmp     edx, [rbx+8]
0x180024c60  jb      short loc_180024C40
0x180024c62  mov     rbx, [rsp+28h+arg_0]
0x180024c67  add     rsp, 20h
0x180024c6b  pop     rdi
0x180024c6c  retn
```
