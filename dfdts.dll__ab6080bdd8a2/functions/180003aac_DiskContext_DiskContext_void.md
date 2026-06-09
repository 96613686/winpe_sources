# DiskContext::~DiskContext(void)

- ea: `0x180003aac`
- end: `0x180003ba4`
- name: `??1DiskContext@@QEAA@XZ`
- size: `248`
- prototype: `void __fastcall(DiskContext *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002ed8`
- `0x180007970`
- `0x180008778`
- `0x18000878a`

## callees

- `0x180003aac`
- `0x180005328`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003ae5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003ae5`
- `KERNEL32!GetProcessHeap` at `0x180003afc`
- `KERNEL32!GetProcessHeap` at `0x180003b24`
- `KERNEL32!GetProcessHeap` at `0x180003b4f`
- `KERNEL32!GetProcessHeap` at `0x180003b7a`
- `KERNEL32!GetProcessHeap` at `0x180003afc`
- `KERNEL32!GetProcessHeap` at `0x180003b24`
- `KERNEL32!GetProcessHeap` at `0x180003b4f`
- `KERNEL32!GetProcessHeap` at `0x180003b7a`
- `KERNEL32!HeapFree` at `0x180003b0a`
- `KERNEL32!HeapFree` at `0x180003b32`
- `KERNEL32!HeapFree` at `0x180003b5d`
- `KERNEL32!HeapFree` at `0x180003b88`
- `KERNEL32!HeapFree` at `0x180003b0a`
- `KERNEL32!HeapFree` at `0x180003b32`
- `KERNEL32!HeapFree` at `0x180003b5d`
- `KERNEL32!HeapFree` at `0x180003b88`
- `KERNEL32!CloseHandle` at `0x180003ac3`
- `KERNEL32!CloseHandle` at `0x180003ac3`

## pseudocode

```c
void __fastcall DiskContext::~DiskContext(DiskContext *this)
{
  void *v2; // rcx
  void *v3; // rdi
  void *v4; // rdi
  HANDLE ProcessHeap; // rax
  void *v6; // rdi
  HANDLE v7; // rax
  void *v8; // rdi
  HANDLE v9; // rax
  void *v10; // rdi
  HANDLE v11; // rax

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 != (void *)-1LL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 1) = -1;
  }
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    DfdDuid::~DfdDuid(*((DfdDuid **)this + 3));
    operator delete(v3);
    *((_QWORD *)this + 3) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *((_QWORD *)this + 2) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 73);
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
    *((_QWORD *)this + 73) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 76);
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
    *((_QWORD *)this + 76) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 70);
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
    *((_QWORD *)this + 70) = 0;
  }
}

```

## disassembly

```asm
0x180003aac  mov     [rsp+arg_0], rbx
0x180003ab1  push    rdi
0x180003ab2  sub     rsp, 20h
0x180003ab6  mov     rbx, rcx
0x180003ab9  mov     rcx, [rcx+8]; hObject
0x180003abd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003ac1  jz      short loc_180003AD1
0x180003ac3  call    cs:__imp_CloseHandle
0x180003ac9  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x180003ad1  mov     rdi, [rbx+18h]
0x180003ad5  test    rdi, rdi
0x180003ad8  jz      short loc_180003AF3
0x180003ada  mov     rcx, rdi; this
0x180003add  call    ??1DfdDuid@@QEAA@XZ; DfdDuid::~DfdDuid(void)
0x180003ae2  mov     rcx, rdi
0x180003ae5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003aeb  mov     qword ptr [rbx+18h], 0
0x180003af3  mov     rdi, [rbx+10h]
0x180003af7  test    rdi, rdi
0x180003afa  jz      short loc_180003B18
0x180003afc  call    cs:__imp_GetProcessHeap
0x180003b02  mov     r8, rdi; lpMem
0x180003b05  xor     edx, edx; dwFlags
0x180003b07  mov     rcx, rax; hHeap
0x180003b0a  call    cs:__imp_HeapFree
0x180003b10  mov     qword ptr [rbx+10h], 0
0x180003b18  mov     rdi, [rbx+248h]
0x180003b1f  test    rdi, rdi
0x180003b22  jz      short loc_180003B43
0x180003b24  call    cs:__imp_GetProcessHeap
0x180003b2a  mov     r8, rdi; lpMem
0x180003b2d  xor     edx, edx; dwFlags
0x180003b2f  mov     rcx, rax; hHeap
0x180003b32  call    cs:__imp_HeapFree
0x180003b38  mov     qword ptr [rbx+248h], 0
0x180003b43  mov     rdi, [rbx+260h]
0x180003b4a  test    rdi, rdi
0x180003b4d  jz      short loc_180003B6E
0x180003b4f  call    cs:__imp_GetProcessHeap
0x180003b55  mov     r8, rdi; lpMem
0x180003b58  xor     edx, edx; dwFlags
0x180003b5a  mov     rcx, rax; hHeap
0x180003b5d  call    cs:__imp_HeapFree
0x180003b63  mov     qword ptr [rbx+260h], 0
0x180003b6e  mov     rdi, [rbx+230h]
0x180003b75  test    rdi, rdi
0x180003b78  jz      short loc_180003B99
0x180003b7a  call    cs:__imp_GetProcessHeap
0x180003b80  mov     r8, rdi; lpMem
0x180003b83  xor     edx, edx; dwFlags
0x180003b85  mov     rcx, rax; hHeap
0x180003b88  call    cs:__imp_HeapFree
0x180003b8e  mov     qword ptr [rbx+230h], 0
0x180003b99  mov     rbx, [rsp+28h+arg_0]
0x180003b9e  add     rsp, 20h
0x180003ba2  pop     rdi
0x180003ba3  retn
```
