# NfsService::~NfsService(void)

- ea: `0x180023484`
- end: `0x1800234c9`
- name: `??1NfsService@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(NfsService *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800103cc`
- `0x180010f28`
- `0x18001323c`
- `0x180013378`
- `0x1800134b4`
- `0x1800135ec`
- `0x1800363d1`
- `0x180036473`
- `0x18003654b`

## callees

- `0x180023484`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x180023499`
- `ADVAPI32!CloseServiceHandle` at `0x1800234ab`
- `ADVAPI32!CloseServiceHandle` at `0x1800234bd`
- `ADVAPI32!CloseServiceHandle` at `0x180023499`
- `ADVAPI32!CloseServiceHandle` at `0x1800234ab`
- `ADVAPI32!CloseServiceHandle` at `0x1800234bd`

## pseudocode

```c
void __fastcall NfsService::~NfsService(NfsService *this)
{
  SC_HANDLE v2; // rcx
  SC_HANDLE v3; // rcx
  SC_HANDLE v4; // rcx

  v2 = (SC_HANDLE)*((_QWORD *)this + 129);
  if ( v2 )
    CloseServiceHandle(v2);
  v3 = (SC_HANDLE)*((_QWORD *)this + 130);
  if ( v3 )
    CloseServiceHandle(v3);
  v4 = (SC_HANDLE)*((_QWORD *)this + 128);
  if ( v4 )
    CloseServiceHandle(v4);
}

```

## disassembly

```asm
0x180023484  push    rbx
0x180023486  sub     rsp, 20h
0x18002348a  mov     rbx, rcx
0x18002348d  mov     rcx, [rcx+408h]; hSCObject
0x180023494  test    rcx, rcx
0x180023497  jz      short loc_18002349F
0x180023499  call    cs:__imp_CloseServiceHandle
0x18002349f  mov     rcx, [rbx+410h]; hSCObject
0x1800234a6  test    rcx, rcx
0x1800234a9  jz      short loc_1800234B1
0x1800234ab  call    cs:__imp_CloseServiceHandle
0x1800234b1  mov     rcx, [rbx+400h]; hSCObject
0x1800234b8  test    rcx, rcx
0x1800234bb  jz      short loc_1800234C3
0x1800234bd  call    cs:__imp_CloseServiceHandle
0x1800234c3  add     rsp, 20h
0x1800234c7  pop     rbx
0x1800234c8  retn
```
