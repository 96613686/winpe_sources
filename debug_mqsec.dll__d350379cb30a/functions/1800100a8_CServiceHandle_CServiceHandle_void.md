# CServiceHandle::~CServiceHandle(void)

- ea: `0x1800100a8`
- end: `0x1800100ca`
- name: `??1CServiceHandle@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(CServiceHandle *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002ff6f`
- `0x18002ff81`

## callees

- `0x1800100a8`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x1800100be`
- `ADVAPI32!CloseServiceHandle` at `0x1800100be`

## pseudocode

```c
void __fastcall CServiceHandle::~CServiceHandle(SC_HANDLE *this)
{
  SC_HANDLE v1; // rax

  v1 = *this;
  if ( *this )
  {
    *this = 0;
    CloseServiceHandle(v1);
  }
}

```

## disassembly

```asm
0x1800100a8  sub     rsp, 28h
0x1800100ac  mov     rax, [rcx]
0x1800100af  test    rax, rax
0x1800100b2  jz      short loc_1800100C5
0x1800100b4  mov     qword ptr [rcx], 0
0x1800100bb  mov     rcx, rax; hSCObject
0x1800100be  call    cs:__imp_CloseServiceHandle
0x1800100c4  nop
0x1800100c5  add     rsp, 28h
0x1800100c9  retn
```
