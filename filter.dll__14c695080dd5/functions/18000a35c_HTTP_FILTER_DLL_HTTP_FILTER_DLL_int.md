# HTTP_FILTER_DLL::HTTP_FILTER_DLL(int)

- ea: `0x18000a35c`
- end: `0x18000a3da`
- name: `??0HTTP_FILTER_DLL@@QEAA@H@Z`
- size: `126`
- prototype: `HTTP_FILTER_DLL *__fastcall(HTTP_FILTER_DLL *__hidden this, int)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006f50`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a3ab`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a3ab`

## pseudocode

```c
HTTP_FILTER_DLL *__fastcall HTTP_FILTER_DLL::HTTP_FILTER_DLL(HTTP_FILTER_DLL *this, int a2)
{
  *(_DWORD *)this = 1280066630;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_DWORD *)this + 17) = 1;
  STRU::STRU((HTTP_FILTER_DLL *)((char *)this + 72));
  *((_DWORD *)this + 33) = a2;
  *((_DWORD *)this + 32) = 0;
  *((_QWORD *)this + 2) = (char *)this + 8;
  *((_QWORD *)this + 1) = (char *)this + 8;
  return this;
}

```

## disassembly

```asm
0x18000a35c  mov     [rsp+arg_0], rbx
0x18000a361  push    rdi
0x18000a362  sub     rsp, 20h
0x18000a366  mov     rdi, rcx
0x18000a369  mov     dword ptr [rcx], 4C4C4446h
0x18000a36f  mov     qword ptr [rcx+18h], 0
0x18000a377  mov     ebx, edx
0x18000a379  mov     qword ptr [rcx+20h], 0
0x18000a381  mov     qword ptr [rcx+28h], 0
0x18000a389  mov     qword ptr [rcx+30h], 0
0x18000a391  mov     qword ptr [rcx+38h], 0
0x18000a399  mov     dword ptr [rcx+40h], 0
0x18000a3a0  mov     dword ptr [rcx+44h], 1
0x18000a3a7  add     rcx, 48h ; 'H'
0x18000a3ab  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000a3b1  lea     rax, [rdi+8]
0x18000a3b5  mov     [rdi+84h], ebx
0x18000a3bb  mov     rbx, [rsp+28h+arg_0]
0x18000a3c0  mov     dword ptr [rdi+80h], 0
0x18000a3ca  mov     [rax+8], rax
0x18000a3ce  mov     [rax], rax
0x18000a3d1  mov     rax, rdi
0x18000a3d4  add     rsp, 20h
0x18000a3d8  pop     rdi
0x18000a3d9  retn
```
