# CopyMediaType(_AMMediaType *,_AMMediaType const *)

- ea: `0x180007104`
- end: `0x18000718b`
- name: `?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z`
- size: `135`
- prototype: `__int64 __fastcall(struct _AMMediaType *, const struct _AMMediaType *)`
- caller_count: `13`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800043a0`
- `0x180007194`
- `0x18000724c`
- `0x1800083d0`
- `0x180008980`
- `0x180009020`
- `0x180009d70`
- `0x180014f78`
- `0x180015a10`
- `0x180015c64`
- `0x18001a600`
- `0x18001a88c`
- `0x18001b820`

## callees

- `0x180007104`
- `0x18001e5c5`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000714d`
- `ole32!CoTaskMemAlloc` at `0x18000714d`

## pseudocode

```c
__int64 __fastcall CopyMediaType(struct _AMMediaType *a1, const struct _AMMediaType *a2)
{
  BYTE *v4; // rax

  *a1 = *a2;
  if ( a2->cbFormat )
  {
    v4 = (BYTE *)CoTaskMemAlloc(a2->cbFormat);
    a1->pbFormat = v4;
    if ( !v4 )
    {
      a1->cbFormat = 0;
      return 2147942414LL;
    }
    memcpy_0(v4, a2->pbFormat, a1->cbFormat);
  }
  a1->pUnk = 0;
  return 0;
}

```

## disassembly

```asm
0x180007104  mov     [rsp+arg_0], rbx
0x180007109  push    rdi
0x18000710a  sub     rsp, 20h
0x18000710e  movups  xmm0, xmmword ptr [rdx]
0x180007111  mov     rdi, rdx
0x180007114  mov     rbx, rcx
0x180007117  movups  xmmword ptr [rcx], xmm0
0x18000711a  movups  xmm1, xmmword ptr [rdx+10h]
0x18000711e  movups  xmmword ptr [rcx+10h], xmm1
0x180007122  movups  xmm0, xmmword ptr [rdx+20h]
0x180007126  movups  xmmword ptr [rcx+20h], xmm0
0x18000712a  movups  xmm1, xmmword ptr [rdx+30h]
0x18000712e  movups  xmmword ptr [rcx+30h], xmm1
0x180007132  movups  xmm0, xmmword ptr [rdx+40h]
0x180007136  movups  xmmword ptr [rcx+40h], xmm0
0x18000713a  movsd   xmm1, qword ptr [rdx+50h]
0x18000713f  movsd   qword ptr [rcx+50h], xmm1
0x180007144  cmp     dword ptr [rdx+48h], 0
0x180007148  jz      short loc_180007176
0x18000714a  mov     ecx, [rdx+48h]; cb
0x18000714d  call    cs:__imp_CoTaskMemAlloc
0x180007153  mov     [rbx+50h], rax
0x180007157  test    rax, rax
0x18000715a  jnz     short loc_180007166
0x18000715c  mov     [rbx+48h], eax
0x18000715f  mov     eax, 8007000Eh
0x180007164  jmp     short loc_180007180
0x180007166  mov     r8d, [rbx+48h]; Size
0x18000716a  mov     rcx, rax; void *
0x18000716d  mov     rdx, [rdi+50h]; Src
0x180007171  call    memcpy_0
0x180007176  mov     qword ptr [rbx+40h], 0
0x18000717e  xor     eax, eax
0x180007180  mov     rbx, [rsp+28h+arg_0]
0x180007185  add     rsp, 20h
0x180007189  pop     rdi
0x18000718a  retn
```
