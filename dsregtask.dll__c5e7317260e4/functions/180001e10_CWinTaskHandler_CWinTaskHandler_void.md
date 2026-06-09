# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180001e10`
- end: `0x180001e71`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180001ec0`

## callees

- `0x180001e10`
- `0x180004010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180001e56`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180001e56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001e27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001e27`

## pseudocode

```c
void __fastcall CWinTaskHandler::~CWinTaskHandler(CWinTaskHandler *this)
{
  char *v2; // rcx
  __int64 v3; // rcx

  v2 = (char *)*((_QWORD *)this + 5);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 5) = -1;
  }
  v3 = *((_QWORD *)this + 6);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 6) = 0;
  }
  free(*((void **)this + 1));
  *((_QWORD *)this + 1) = 0;
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
}

```

## disassembly

```asm
0x180001e10  push    rbx
0x180001e12  sub     rsp, 20h
0x180001e16  mov     rbx, rcx
0x180001e19  mov     rcx, [rcx+28h]; hObject
0x180001e1d  lea     rax, [rcx-1]
0x180001e21  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001e25  ja      short loc_180001E35
0x180001e27  call    cs:__imp_CloseHandle
0x180001e2d  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180001e35  mov     rcx, [rbx+30h]
0x180001e39  test    rcx, rcx
0x180001e3c  jz      short loc_180001E52
0x180001e3e  mov     rax, [rcx]
0x180001e41  mov     rax, [rax+10h]
0x180001e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e4a  mov     qword ptr [rbx+30h], 0
0x180001e52  mov     rcx, [rbx+8]; Block
0x180001e56  call    cs:__imp_free
0x180001e5c  mov     qword ptr [rbx+8], 0
0x180001e64  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180001e6b  add     rsp, 20h
0x180001e6f  pop     rbx
0x180001e70  retn
```
