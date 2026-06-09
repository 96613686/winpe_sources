# CDescriptor::SetIStream(IStream *)

- ea: `0x18000c3f0`
- end: `0x18000c48c`
- name: `?SetIStream@CDescriptor@@QEAAXPEAUIStream@@@Z`
- size: `156`
- prototype: `void __fastcall(CDescriptor *__hidden this, struct IStream *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a484`
- `0x18000b358`
- `0x18000c018`

## callees

- `0x18000a2a4`
- `0x18000c3f0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c40f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c40f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c485`

## pseudocode

```c
void __fastcall CDescriptor::SetIStream(CDescriptor *this, struct IStream *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  CDescriptor::ClearIStream(this);
  *((_QWORD *)this + 13) = a2;
  if ( a2 )
  {
    *((_QWORD *)this + 15) = 0;
    v5 = *((_QWORD *)this + 15);
    v7 = 0;
    ((void (__fastcall *)(struct IStream *, __int64, __int64, __int64 *))a2->lpVtbl->Seek)(a2, v5, 1, &v7);
    v6 = *((_QWORD *)this + 13);
    *((_QWORD *)this + 15) = v7;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    *((_DWORD *)this + 2) |= 0x800u;
  }
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x18000c3f0  mov     [rsp+arg_8], rbx
0x18000c3f5  mov     [rsp+arg_10], rsi
0x18000c3fa  push    rdi
0x18000c3fb  sub     rsp, 30h
0x18000c3ff  lea     rsi, [rcx+80h]
0x18000c406  mov     rbx, rcx
0x18000c409  mov     rcx, rsi; lpCriticalSection
0x18000c40c  mov     rdi, rdx
0x18000c40f  call    cs:__imp_EnterCriticalSection
0x18000c415  mov     rcx, rbx; this
0x18000c418  call    ?ClearIStream@CDescriptor@@QEAAXXZ; CDescriptor::ClearIStream(void)
0x18000c41d  mov     [rbx+68h], rdi
0x18000c421  test    rdi, rdi
0x18000c424  jz      short loc_18000C473
0x18000c426  mov     qword ptr [rbx+78h], 0
0x18000c42e  lea     r9, [rsp+38h+arg_0]
0x18000c433  mov     rdx, [rbx+78h]
0x18000c437  mov     r8d, 1
0x18000c43d  mov     [rsp+38h+arg_0], 0
0x18000c446  mov     rcx, rdi
0x18000c449  mov     rax, [rdi]
0x18000c44c  mov     rax, [rax+28h]
0x18000c450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c455  mov     rax, [rsp+38h+arg_0]
0x18000c45a  mov     rcx, [rbx+68h]
0x18000c45e  mov     [rbx+78h], rax
0x18000c462  mov     rax, [rcx]
0x18000c465  mov     rax, [rax+8]
0x18000c469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c46e  bts     dword ptr [rbx+8], 0Bh
0x18000c473  mov     rcx, rsi
0x18000c476  mov     rbx, [rsp+38h+arg_8]
0x18000c47b  mov     rsi, [rsp+38h+arg_10]
0x18000c480  add     rsp, 30h
0x18000c484  pop     rdi
0x18000c485  jmp     cs:__imp_LeaveCriticalSection
```
