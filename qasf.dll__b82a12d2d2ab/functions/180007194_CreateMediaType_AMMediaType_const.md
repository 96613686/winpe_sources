# CreateMediaType(_AMMediaType const *)

- ea: `0x180007194`
- end: `0x1800071e0`
- name: `?CreateMediaType@@YAPEAU_AMMediaType@@PEBU1@@Z`
- size: `76`
- prototype: `struct _AMMediaType *__fastcall(const struct _AMMediaType *)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004c10`
- `0x180006510`
- `0x180006630`
- `0x180014250`
- `0x18001657c`
- `0x18001a600`

## callees

- `0x180007104`
- `0x180007194`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800071a6`
- `ole32!CoTaskMemAlloc` at `0x1800071a6`
- `ole32!CoTaskMemFree` at `0x1800071ca`
- `ole32!CoTaskMemFree` at `0x1800071ca`

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
    CoTaskMemFree(v3);
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180007194  mov     [rsp+arg_0], rbx
0x180007199  push    rdi
0x18000719a  sub     rsp, 20h
0x18000719e  mov     rdi, rcx
0x1800071a1  mov     ecx, 58h ; 'X'; cb
0x1800071a6  call    cs:__imp_CoTaskMemAlloc
0x1800071ac  mov     rbx, rax
0x1800071af  test    rax, rax
0x1800071b2  jnz     short loc_1800071B8
0x1800071b4  xor     eax, eax
0x1800071b6  jmp     short loc_1800071D5
0x1800071b8  mov     rdx, rdi; struct _AMMediaType *
0x1800071bb  mov     rcx, rbx; struct _AMMediaType *
0x1800071be  call    ?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x1800071c3  test    eax, eax
0x1800071c5  jns     short loc_1800071D2
0x1800071c7  mov     rcx, rbx; pv
0x1800071ca  call    cs:__imp_CoTaskMemFree
0x1800071d0  jmp     short loc_1800071B4
0x1800071d2  mov     rax, rbx
0x1800071d5  mov     rbx, [rsp+28h+arg_0]
0x1800071da  add     rsp, 20h
0x1800071de  pop     rdi
0x1800071df  retn
```
