# DiskContext::DiskContext(void *,ulong)

- ea: `0x1800039fc`
- end: `0x180003aa3`
- name: `??0DiskContext@@QEAA@PEAXK@Z`
- size: `167`
- prototype: `DiskContext *__fastcall(DiskContext *this, void *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ed8`
- `0x180007970`

## callees

- `0x18000833b`

## pseudocode

```c
DiskContext *__fastcall DiskContext::DiskContext(DiskContext *this, void *a2, int a3)
{
  *(_QWORD *)this = a2;
  *((_QWORD *)this + 1) = -1;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 73) = 0;
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 70) = 0;
  *((_QWORD *)this + 74) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 71) = 0;
  *((_DWORD *)this + 156) = 0;
  *((_DWORD *)this + 157) = a3;
  *(_QWORD *)((char *)this + 636) = 0;
  *((_DWORD *)this + 161) = 0;
  *((_DWORD *)this + 137) = 3;
  *((_DWORD *)this + 138) = 3;
  *((_BYTE *)this + 576) = 48;
  *((_BYTE *)this + 600) = 48;
  *((_BYTE *)this + 556) = 48;
  *((_BYTE *)this + 632) = 48;
  memset_0((char *)this + 32, 0, 0x204u);
  return this;
}

```

## disassembly

```asm
0x1800039fc  push    rbx
0x1800039fe  sub     rsp, 20h
0x180003a02  mov     rbx, rcx
0x180003a05  mov     [rcx], rdx
0x180003a08  mov     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x180003a10  xor     edx, edx; Val
0x180003a12  xor     ecx, ecx
0x180003a14  mov     [rbx+10h], rcx
0x180003a18  mov     [rbx+18h], rcx
0x180003a1c  lea     eax, [rcx+3]
0x180003a1f  mov     [rbx+248h], rcx
0x180003a26  mov     [rbx+260h], rcx
0x180003a2d  mov     [rbx+230h], rcx
0x180003a34  mov     [rbx+250h], rcx
0x180003a3b  mov     [rbx+268h], rcx
0x180003a42  mov     [rbx+238h], rcx
0x180003a49  mov     [rbx+270h], ecx
0x180003a4f  mov     [rbx+274h], r8d
0x180003a56  mov     r8d, 204h; Size
0x180003a5c  mov     [rbx+27Ch], rcx
0x180003a63  mov     [rbx+284h], ecx
0x180003a69  lea     rcx, [rbx+20h]; void *
0x180003a6d  mov     [rbx+224h], eax
0x180003a73  mov     [rbx+228h], eax
0x180003a79  mov     byte ptr [rbx+240h], 30h ; '0'
0x180003a80  mov     byte ptr [rbx+258h], 30h ; '0'
0x180003a87  mov     byte ptr [rbx+22Ch], 30h ; '0'
0x180003a8e  mov     byte ptr [rbx+278h], 30h ; '0'
0x180003a95  call    memset_0
0x180003a9a  mov     rax, rbx
0x180003a9d  add     rsp, 20h
0x180003aa1  pop     rbx
0x180003aa2  retn
```
