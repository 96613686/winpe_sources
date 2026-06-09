# PointerList::Remove(void * *,uint)

- ea: `0x18001127c`
- end: `0x1800112e2`
- name: `?Remove@PointerList@@QEAAHPEAPEAXI@Z`
- size: `102`
- prototype: `int(PointerList *__hidden this, void **, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000c8c4`
- `0x18000f564`
- `0x180016b5c`
- `0x180016bd0`
- `0x180016d98`

## callees

- `0x18001127c`
- `0x18001c4f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800112c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800112ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800112c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800112ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001129c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001129c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PointerList::Remove(HDPA *this, void **a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbp
  unsigned int v7; // r14d
  PVOID v8; // rax

  v6 = (struct _RTL_CRITICAL_SECTION *)(this + 2);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 2));
  v7 = 1;
  v8 = DPA_DeletePtr(this[1], a3);
  *a2 = v8;
  if ( v8 )
  {
    LeaveCriticalSection(v6);
  }
  else
  {
    LeaveCriticalSection(v6);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18001127c  push    rbx
0x18001127e  push    rbp
0x18001127f  push    rsi
0x180011280  push    rdi
0x180011281  push    r14
0x180011283  sub     rsp, 30h
0x180011287  mov     edi, r8d
0x18001128a  mov     rsi, rdx
0x18001128d  mov     rbx, rcx
0x180011290  lea     rbp, [rcx+10h]
0x180011294  mov     [rsp+58h+var_38], rbp
0x180011299  mov     rcx, rbp; lpCriticalSection
0x18001129c  call    cs:__imp_EnterCriticalSection
0x1800112a2  mov     r14d, 1
0x1800112a8  mov     [rsp+58h+var_30], r14d
0x1800112ad  mov     edx, edi; i
0x1800112af  mov     rcx, [rbx+8]; hdpa
0x1800112b3  call    DPA_DeletePtr
0x1800112b8  mov     [rsi], rax
0x1800112bb  mov     rcx, rbp; lpCriticalSection
0x1800112be  test    rax, rax
0x1800112c1  jnz     short loc_1800112CE
0x1800112c3  call    cs:__imp_LeaveCriticalSection
0x1800112c9  xor     r14d, r14d
0x1800112cc  jmp     short loc_1800112D4
0x1800112ce  call    cs:__imp_LeaveCriticalSection
0x1800112d4  mov     eax, r14d
0x1800112d7  add     rsp, 30h
0x1800112db  pop     r14
0x1800112dd  pop     rdi
0x1800112de  pop     rsi
0x1800112df  pop     rbp
0x1800112e0  pop     rbx
0x1800112e1  retn
```
