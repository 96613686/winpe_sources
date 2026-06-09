# CopyMediaType(_AMMediaType *,_AMMediaType const *)

- ea: `0x1800129d8`
- end: `0x180012a6a`
- name: `?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z`
- size: `146`
- prototype: `__int64 __fastcall(struct _AMMediaType *, const struct _AMMediaType *)`
- caller_count: `7`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180012950`
- `0x180016f60`
- `0x180027000`
- `0x18002f8d0`
- `0x18003e1ac`
- `0x18003e1cc`
- `0x18003e32c`

## callees

- `0x1800129d8`
- `0x180044850`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180012a21`
- `ole32!CoTaskMemAlloc` at `0x180012a21`

## pseudocode

```c
__int64 __fastcall CopyMediaType(struct _AMMediaType *a1, const struct _AMMediaType *a2)
{
  unsigned __int8 *v4; // rax

  *a1 = *a2;
  if ( !a2->cbFormat )
    goto LABEL_4;
  v4 = (unsigned __int8 *)CoTaskMemAlloc(a2->cbFormat);
  a1->pbFormat = v4;
  if ( v4 )
  {
    memcpy_0(v4, a2->pbFormat, a1->cbFormat);
LABEL_4:
    a1->pUnk = 0;
    return 0;
  }
  a1->cbFormat = 0;
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800129d8  mov     [rsp+arg_0], rbx
0x1800129dd  push    rdi
0x1800129de  sub     rsp, 20h
0x1800129e2  movups  xmm0, xmmword ptr [rdx]
0x1800129e5  mov     rdi, rdx
0x1800129e8  mov     rbx, rcx
0x1800129eb  movups  xmmword ptr [rcx], xmm0
0x1800129ee  movups  xmm1, xmmword ptr [rdx+10h]
0x1800129f2  movups  xmmword ptr [rcx+10h], xmm1
0x1800129f6  movups  xmm0, xmmword ptr [rdx+20h]
0x1800129fa  movups  xmmword ptr [rcx+20h], xmm0
0x1800129fe  movups  xmm1, xmmword ptr [rdx+30h]
0x180012a02  movups  xmmword ptr [rcx+30h], xmm1
0x180012a06  movups  xmm0, xmmword ptr [rdx+40h]
0x180012a0a  movups  xmmword ptr [rcx+40h], xmm0
0x180012a0e  movsd   xmm1, qword ptr [rdx+50h]
0x180012a13  movsd   qword ptr [rcx+50h], xmm1
0x180012a18  cmp     dword ptr [rdx+48h], 0
0x180012a1c  jz      short loc_180012A46
0x180012a1e  mov     ecx, [rdx+48h]; cb
0x180012a21  call    cs:__imp_CoTaskMemAlloc
0x180012a28  nop     dword ptr [rax+rax+00h]
0x180012a2d  mov     [rbx+50h], rax
0x180012a31  test    rax, rax
0x180012a34  jz      short loc_180012A5C
0x180012a36  mov     r8d, [rbx+48h]; Size
0x180012a3a  mov     rcx, rax; void *
0x180012a3d  mov     rdx, [rdi+50h]; Src
0x180012a41  call    memcpy_0
0x180012a46  mov     qword ptr [rbx+40h], 0
0x180012a4e  xor     eax, eax
0x180012a50  mov     rbx, [rsp+28h+arg_0]
0x180012a55  add     rsp, 20h
0x180012a59  pop     rdi
0x180012a5a  retn
0x180012a5c  mov     dword ptr [rbx+48h], 0
0x180012a63  mov     eax, 8007000Eh
0x180012a68  jmp     short loc_180012A50
```
