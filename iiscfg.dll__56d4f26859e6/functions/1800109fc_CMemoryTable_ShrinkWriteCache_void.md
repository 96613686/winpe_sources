# CMemoryTable::ShrinkWriteCache(void)

- ea: `0x1800109fc`
- end: `0x180010b00`
- name: `?ShrinkWriteCache@CMemoryTable@@AEAAJXZ`
- size: `260`
- prototype: `__int64 __fastcall(CMemoryTable *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000feb0`
- `0x180010b10`

## callees

- `0x1800109fc`
- `0x18002e0b2`
- `0x18002e0be`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x180010a87`
- `ole32!CoTaskMemRealloc` at `0x180010ae7`
- `ole32!CoTaskMemRealloc` at `0x180010a87`
- `ole32!CoTaskMemRealloc` at `0x180010ae7`

## pseudocode

```c
__int64 __fastcall CMemoryTable::ShrinkWriteCache(CMemoryTable *this)
{
  bool v2; // zf
  SIZE_T v3; // rcx
  int v4; // eax
  const void *v5; // rdi
  void *v6; // rax
  LPVOID v8; // rax

  if ( *((_DWORD *)this + 40) >= *((_DWORD *)this + 41) )
    return 0;
  memmove_0(
    (void *)(*((_QWORD *)this + 19)
           + (unsigned int)(8
                          * *((_DWORD *)this + 34)
                          * (*((_DWORD *)this + 10) + 1 + *((_DWORD *)this + 12) + *((_DWORD *)this + 11)))),
    *((const void **)this + 18),
    *((unsigned int *)this + 35));
  v2 = (*((_DWORD *)this + 8) & 0x1000000) == 0;
  v3 = *((unsigned int *)this + 40);
  *((_DWORD *)this + 41) = v3;
  if ( v2 && (v4 = *((_DWORD *)this + 23), (v4 & 0x20000) != 0) )
  {
    v5 = (const void *)*((_QWORD *)this + 19);
    *((_DWORD *)this + 23) = v4 & 0xFFFDFFFF;
    *((_QWORD *)this + 19) = 0;
    v6 = CoTaskMemRealloc(0, (unsigned int)v3);
    *((_QWORD *)this + 19) = v6;
    if ( v6 )
    {
      memcpy_0(v6, v5, *((unsigned int *)this + 40));
LABEL_6:
      *((_QWORD *)this + 18) = *((_QWORD *)this + 19)
                             + (unsigned int)(8
                                            * *((_DWORD *)this + 34)
                                            * (*((_DWORD *)this + 12)
                                             + *((_DWORD *)this + 11)
                                             + *((_DWORD *)this + 10)
                                             + 1));
      return 0;
    }
  }
  else
  {
    v8 = CoTaskMemRealloc(*((LPVOID *)this + 19), v3);
    *((_QWORD *)this + 19) = v8;
    if ( v8 )
      goto LABEL_6;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800109fc  mov     [rsp+arg_0], rbx
0x180010a01  push    rdi
0x180010a02  sub     rsp, 20h
0x180010a06  mov     eax, [rcx+0A4h]
0x180010a0c  mov     rbx, rcx
0x180010a0f  cmp     [rcx+0A0h], eax
0x180010a15  jnb     loc_180010AD0
0x180010a1b  mov     r8d, [rcx+8Ch]; Size
0x180010a22  mov     ecx, [rcx+2Ch]
0x180010a25  add     ecx, [rbx+30h]
0x180010a28  mov     eax, [rbx+28h]
0x180010a2b  mov     rdx, [rbx+90h]; Src
0x180010a32  inc     eax
0x180010a34  add     ecx, eax
0x180010a36  imul    ecx, [rbx+88h]
0x180010a3d  shl     ecx, 3
0x180010a40  add     rcx, [rbx+98h]; void *
0x180010a47  call    memmove_0
0x180010a4c  test    dword ptr [rbx+20h], 1000000h
0x180010a53  mov     ecx, [rbx+0A0h]
0x180010a59  mov     [rbx+0A4h], ecx
0x180010a5f  jnz     short loc_180010ADD
0x180010a61  mov     eax, [rbx+5Ch]
0x180010a64  bt      eax, 11h
0x180010a68  jnb     short loc_180010ADD
0x180010a6a  mov     rdi, [rbx+98h]
0x180010a71  btr     eax, 11h
0x180010a75  mov     edx, ecx; cb
0x180010a77  mov     [rbx+5Ch], eax
0x180010a7a  xor     ecx, ecx; pv
0x180010a7c  mov     qword ptr [rbx+98h], 0
0x180010a87  call    cs:__imp_CoTaskMemRealloc
0x180010a8d  mov     [rbx+98h], rax
0x180010a94  test    rax, rax
0x180010a97  jz      short loc_180010AF9
0x180010a99  mov     r8d, [rbx+0A0h]; Size
0x180010aa0  mov     rdx, rdi; Src
0x180010aa3  mov     rcx, rax; void *
0x180010aa6  call    memcpy_0
0x180010aab  mov     eax, [rbx+28h]
0x180010aae  mov     ecx, [rbx+2Ch]
0x180010ab1  inc     eax
0x180010ab3  add     ecx, [rbx+30h]
0x180010ab6  add     eax, ecx
0x180010ab8  imul    eax, [rbx+88h]
0x180010abf  shl     eax, 3
0x180010ac2  add     rax, [rbx+98h]
0x180010ac9  mov     [rbx+90h], rax
0x180010ad0  xor     eax, eax
0x180010ad2  mov     rbx, [rsp+28h+arg_0]
0x180010ad7  add     rsp, 20h
0x180010adb  pop     rdi
0x180010adc  retn
0x180010add  mov     rdx, rcx; cb
0x180010ae0  mov     rcx, [rbx+98h]; pv
0x180010ae7  call    cs:__imp_CoTaskMemRealloc
0x180010aed  mov     [rbx+98h], rax
0x180010af4  test    rax, rax
0x180010af7  jnz     short loc_180010AAB
0x180010af9  mov     eax, 8007000Eh
0x180010afe  jmp     short loc_180010AD2
```
