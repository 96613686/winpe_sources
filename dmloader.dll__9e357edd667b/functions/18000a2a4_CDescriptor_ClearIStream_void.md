# CDescriptor::ClearIStream(void)

- ea: `0x18000a2a4`
- end: `0x18000a307`
- name: `?ClearIStream@CDescriptor@@QEAAXXZ`
- size: `99`
- prototype: `void __fastcall(CDescriptor *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180009550`
- `0x18000a1e4`
- `0x18000a484`
- `0x18000c018`
- `0x18000c3f0`

## callees

- `0x18000a2a4`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a2bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a2bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a300`

## pseudocode

```c
void __fastcall CDescriptor::ClearIStream(CDescriptor *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v3; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  v3 = *((_QWORD *)this + 13);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  *((_DWORD *)this + 2) &= ~0x800u;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x18000a2a4  mov     [rsp+arg_0], rbx
0x18000a2a9  push    rdi
0x18000a2aa  sub     rsp, 20h
0x18000a2ae  lea     rdi, [rcx+80h]
0x18000a2b5  mov     rbx, rcx
0x18000a2b8  mov     rcx, rdi; lpCriticalSection
0x18000a2bb  call    cs:__imp_EnterCriticalSection
0x18000a2c1  mov     rcx, [rbx+68h]
0x18000a2c5  test    rcx, rcx
0x18000a2c8  jz      short loc_18000A2D6
0x18000a2ca  mov     rax, [rcx]
0x18000a2cd  mov     rax, [rax+10h]
0x18000a2d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2d6  btr     dword ptr [rbx+8], 0Bh
0x18000a2db  mov     rcx, rdi
0x18000a2de  mov     qword ptr [rbx+68h], 0
0x18000a2e6  mov     qword ptr [rbx+70h], 0
0x18000a2ee  mov     qword ptr [rbx+78h], 0
0x18000a2f6  mov     rbx, [rsp+28h+arg_0]
0x18000a2fb  add     rsp, 20h
0x18000a2ff  pop     rdi
0x18000a300  jmp     cs:__imp_LeaveCriticalSection
```
