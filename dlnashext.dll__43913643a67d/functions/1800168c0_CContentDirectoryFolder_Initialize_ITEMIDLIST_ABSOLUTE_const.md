# CContentDirectoryFolder::Initialize(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x1800168c0`
- end: `0x180016910`
- name: `?Initialize@CContentDirectoryFolder@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `80`
- prototype: `int(CContentDirectoryFolder *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800168c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800168dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800168dc`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x1800168ef`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x1800168ef`

## pseudocode

```c
__int64 __fastcall CContentDirectoryFolder::Initialize(CContentDirectoryFolder *this, const ITEMIDLIST *a2)
{
  void *v4; // rcx
  __int64 result; // rax
  LPITEMIDLIST v6; // rax

  v4 = (void *)*((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  CoTaskMemFree(v4);
  result = 2147942487LL;
  if ( a2 )
  {
    v6 = ILClone(a2);
    *((_QWORD *)this + 10) = v6;
    return v6 == 0 ? 0x8007000E : 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800168c0  mov     [rsp+arg_0], rbx
0x1800168c5  push    rdi
0x1800168c6  sub     rsp, 20h
0x1800168ca  mov     rbx, rcx
0x1800168cd  mov     rdi, rdx
0x1800168d0  mov     rcx, [rcx+50h]; pv
0x1800168d4  mov     qword ptr [rbx+50h], 0
0x1800168dc  call    cs:__imp_CoTaskMemFree
0x1800168e2  mov     eax, 80070057h
0x1800168e7  test    rdi, rdi
0x1800168ea  jz      short loc_180016905
0x1800168ec  mov     rcx, rdi; pidl
0x1800168ef  call    cs:__imp_ILClone
0x1800168f5  mov     [rbx+50h], rax
0x1800168f9  neg     rax
0x1800168fc  sbb     eax, eax
0x1800168fe  not     eax
0x180016900  and     eax, 8007000Eh
0x180016905  mov     rbx, [rsp+28h+arg_0]
0x18001690a  add     rsp, 20h
0x18001690e  pop     rdi
0x18001690f  retn
```
