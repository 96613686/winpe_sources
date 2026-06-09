# CopyMediaType(_AMMediaType *,_AMMediaType const *)

- ea: `0x180029ec8`
- end: `0x180029f56`
- name: `?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z`
- size: `142`
- prototype: `__int64 __fastcall(struct _AMMediaType *, const struct _AMMediaType *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800168e0`
- `0x1800196c0`
- `0x180026b30`
- `0x1800285c0`

## callees

- `0x180029ec8`
- `0x1800886fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029f11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029f11`

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
0x180029ec8  mov     [rsp+arg_0], rbx
0x180029ecd  push    rdi
0x180029ece  sub     rsp, 20h
0x180029ed2  movups  xmm0, xmmword ptr [rdx]
0x180029ed5  mov     rdi, rdx
0x180029ed8  mov     rbx, rcx
0x180029edb  movups  xmmword ptr [rcx], xmm0
0x180029ede  movups  xmm1, xmmword ptr [rdx+10h]
0x180029ee2  movups  xmmword ptr [rcx+10h], xmm1
0x180029ee6  movups  xmm0, xmmword ptr [rdx+20h]
0x180029eea  movups  xmmword ptr [rcx+20h], xmm0
0x180029eee  movups  xmm1, xmmword ptr [rdx+30h]
0x180029ef2  movups  xmmword ptr [rcx+30h], xmm1
0x180029ef6  movups  xmm0, xmmword ptr [rdx+40h]
0x180029efa  movups  xmmword ptr [rcx+40h], xmm0
0x180029efe  movsd   xmm1, qword ptr [rdx+50h]
0x180029f03  movsd   qword ptr [rcx+50h], xmm1
0x180029f08  cmp     dword ptr [rdx+48h], 0
0x180029f0c  jz      short loc_180029F40
0x180029f0e  mov     ecx, [rdx+48h]; cb
0x180029f11  call    cs:__imp_CoTaskMemAlloc
0x180029f18  nop     dword ptr [rax+rax+00h]
0x180029f1d  mov     [rbx+50h], rax
0x180029f21  test    rax, rax
0x180029f24  jnz     short loc_180029F30
0x180029f26  mov     [rbx+48h], eax
0x180029f29  mov     eax, 8007000Eh
0x180029f2e  jmp     short loc_180029F4A
0x180029f30  mov     r8d, [rbx+48h]; Size
0x180029f34  mov     rcx, rax; void *
0x180029f37  mov     rdx, [rdi+50h]; Src
0x180029f3b  call    memcpy_0
0x180029f40  mov     qword ptr [rbx+40h], 0
0x180029f48  xor     eax, eax
0x180029f4a  mov     rbx, [rsp+28h+arg_0]
0x180029f4f  add     rsp, 20h
0x180029f53  pop     rdi
0x180029f54  retn
```
