# CreateMediaType(_AMMediaType const *)

- ea: `0x18003e1cc`
- end: `0x18003e225`
- name: `?CreateMediaType@@YAPEAU_AMMediaType@@PEBU1@@Z`
- size: `89`
- prototype: `struct _AMMediaType *__fastcall(const struct _AMMediaType *)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000eea0`
- `0x18002998c`
- `0x18002da70`
- `0x18003cfe0`
- `0x18003f6d0`
- `0x18003f8a0`

## callees

- `0x1800129d8`
- `0x18003e1cc`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18003e1de`
- `ole32!CoTaskMemAlloc` at `0x18003e1de`
- `ole32!CoTaskMemFree` at `0x18003e208`
- `ole32!CoTaskMemFree` at `0x18003e208`

## pseudocode

```c
struct _AMMediaType *__fastcall CreateMediaType(const struct _AMMediaType *a1)
{
  struct _AMMediaType *v2; // rax
  struct _AMMediaType *v3; // rbx

  v2 = (struct _AMMediaType *)CoTaskMemAlloc(0x58u);
  v3 = v2;
  if ( !v2 )
    return 0;
  if ( (int)CopyMediaType(v2, a1) < 0 )
  {
    CoTaskMemFree((LPVOID)v3);
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x18003e1cc  mov     [rsp+arg_0], rbx
0x18003e1d1  push    rdi
0x18003e1d2  sub     rsp, 20h
0x18003e1d6  mov     rdi, rcx
0x18003e1d9  mov     ecx, 58h ; 'X'; cb
0x18003e1de  call    cs:__imp_CoTaskMemAlloc
0x18003e1e5  nop     dword ptr [rax+rax+00h]
0x18003e1ea  mov     rbx, rax
0x18003e1ed  test    rax, rax
0x18003e1f0  jnz     short loc_18003E1F6
0x18003e1f2  xor     eax, eax
0x18003e1f4  jmp     short loc_18003E219
0x18003e1f6  mov     rdx, rdi; const struct _AMMediaType *
0x18003e1f9  mov     rcx, rbx; struct _AMMediaType *
0x18003e1fc  call    ?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x18003e201  test    eax, eax
0x18003e203  jns     short loc_18003E216
0x18003e205  mov     rcx, rbx; pv
0x18003e208  call    cs:__imp_CoTaskMemFree
0x18003e20f  nop     dword ptr [rax+rax+00h]
0x18003e214  jmp     short loc_18003E1F2
0x18003e216  mov     rax, rbx
0x18003e219  mov     rbx, [rsp+28h+arg_0]
0x18003e21e  add     rsp, 20h
0x18003e222  pop     rdi
0x18003e223  retn
```
