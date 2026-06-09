# CContentDirectory::SetObjectID(ushort const *)

- ea: `0x180027bb0`
- end: `0x180027be1`
- name: `?SetObjectID@CContentDirectory@@UEAAJPEBG@Z`
- size: `49`
- prototype: `__int64 __fastcall(CContentDirectory *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027bc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027bc4`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180027bda`

## pseudocode

```c
HRESULT __fastcall CContentDirectory::SetObjectID(LPVOID *this, const unsigned __int16 *a2)
{
  LPWSTR *v2; // rbx

  v2 = (LPWSTR *)(this + 2);
  CoTaskMemFree(this[2]);
  return SHStrDupW(a2, v2);
}

```

## disassembly

```asm
0x180027bb0  mov     [rsp+arg_0], rbx
0x180027bb5  push    rdi
0x180027bb6  sub     rsp, 20h
0x180027bba  lea     rbx, [rcx+10h]
0x180027bbe  mov     rdi, rdx
0x180027bc1  mov     rcx, [rbx]; pv
0x180027bc4  call    cs:__imp_CoTaskMemFree
0x180027bca  mov     rdx, rbx
0x180027bcd  mov     rcx, rdi
0x180027bd0  mov     rbx, [rsp+28h+arg_0]
0x180027bd5  add     rsp, 20h
0x180027bd9  pop     rdi
0x180027bda  jmp     cs:__imp_SHStrDupW
```
