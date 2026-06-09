# CAccServerDocMgr::~CAccServerDocMgr(void)

- ea: `0x18000cac8`
- end: `0x18000cb27`
- name: `??1CAccServerDocMgr@@QEAA@XZ`
- size: `95`
- prototype: `void __fastcall(CAccServerDocMgr *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f2f0`
- `0x18000fa4c`
- `0x180011a20`
- `0x180011cf0`

## callees

- `0x1800026d0`
- `0x18000cac8`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAccServerDocMgr::~CAccServerDocMgr(CAccServerDocMgr *this)
{
  __int64 v2; // rcx
  int v3; // [rsp+20h] [rbp-28h]

  v2 = *((_QWORD *)this + 4);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *((_QWORD *)this + 2) || *((_QWORD *)this + 3) )
    InternalTrace(L"windows\\oleacc\\inc\\list_dl.h", 0x41u, 8u, 0, v3, 0, (wchar_t *)L"~List_dl(), list not empty?");
}

```

## disassembly

```asm
0x18000cac8  push    rbx
0x18000caca  sub     rsp, 40h
0x18000cace  mov     rbx, rcx
0x18000cad1  mov     rcx, [rcx+20h]
0x18000cad5  test    rcx, rcx
0x18000cad8  jz      short loc_18000CAE7
0x18000cada  mov     rax, [rcx]
0x18000cadd  mov     rax, [rax+10h]
0x18000cae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cae6  nop
0x18000cae7  cmp     qword ptr [rbx+10h], 0
0x18000caec  jnz     short loc_18000CAF5
0x18000caee  cmp     qword ptr [rbx+18h], 0
0x18000caf3  jz      short loc_18000CB21
0x18000caf5  lea     rax, aListDlListNotE; "~List_dl(), list not empty?"
0x18000cafc  mov     [rsp+48h+var_18], rax; __int64
0x18000cb01  mov     [rsp+48h+var_20], 0; int
0x18000cb09  xor     r9d, r9d
0x18000cb0c  lea     edx, [r9+41h]; Value
0x18000cb10  lea     r8d, [r9+8]
0x18000cb14  lea     rcx, aWindowsOleaccI; "windows\\oleacc\\inc\\list_dl.h"
0x18000cb1b  call    InternalTrace
0x18000cb20  nop
0x18000cb21  add     rsp, 40h
0x18000cb25  pop     rbx
0x18000cb26  retn
```
