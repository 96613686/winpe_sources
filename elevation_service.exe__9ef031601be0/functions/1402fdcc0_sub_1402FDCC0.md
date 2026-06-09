# sub_1402FDCC0

- ea: `0x1402fdcc0`
- end: `0x1402fdd17`
- name: `sub_1402FDCC0`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1402fdcc0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1402fdcde`
- `ole32!CoTaskMemAlloc` at `0x1402fdcde`

## pseudocode

```c
__int64 __fastcall sub_1402FDCC0(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  _OWORD *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = xmmword_14032C4B0;
  v5[1] = xmmword_140358D78;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1402fdcc0  push    rsi
0x1402fdcc1  push    rdi
0x1402fdcc2  sub     rsp, 28h
0x1402fdcc6  mov     rsi, r8
0x1402fdcc9  mov     rdi, rdx
0x1402fdccc  mov     qword ptr [r8], 0
0x1402fdcd3  mov     dword ptr [rdx], 0
0x1402fdcd9  mov     ecx, 20h ; ' '; cb
0x1402fdcde  call    cs:CoTaskMemAlloc
0x1402fdce4  test    rax, rax
0x1402fdce7  jz      short loc_1402FDD10
0x1402fdce9  movups  xmm0, cs:xmmword_14032C4B0
0x1402fdcf0  movups  xmmword ptr [rax], xmm0
0x1402fdcf3  movups  xmm0, cs:xmmword_140358D78
0x1402fdcfa  movups  xmmword ptr [rax+10h], xmm0
0x1402fdcfe  mov     dword ptr [rdi], 2
0x1402fdd04  mov     [rsi], rax
0x1402fdd07  xor     eax, eax
0x1402fdd09  add     rsp, 28h
0x1402fdd0d  pop     rdi
0x1402fdd0e  pop     rsi
0x1402fdd0f  retn
0x1402fdd10  mov     eax, 8007000Eh
0x1402fdd15  jmp     short loc_1402FDD09
```
