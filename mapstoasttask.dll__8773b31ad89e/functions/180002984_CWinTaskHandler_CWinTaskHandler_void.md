# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180002984`
- end: `0x1800029e5`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180002cf0`

## callees

- `0x180002984`
- `0x18000a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800029ca`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800029ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000299b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000299b`

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
0x180002984  push    rbx
0x180002986  sub     rsp, 20h
0x18000298a  mov     rbx, rcx
0x18000298d  mov     rcx, [rcx+28h]; hObject
0x180002991  lea     rax, [rcx-1]
0x180002995  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002999  ja      short loc_1800029A9
0x18000299b  call    cs:__imp_CloseHandle
0x1800029a1  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x1800029a9  mov     rcx, [rbx+30h]
0x1800029ad  test    rcx, rcx
0x1800029b0  jz      short loc_1800029C6
0x1800029b2  mov     rax, [rcx]
0x1800029b5  mov     rax, [rax+10h]
0x1800029b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029be  mov     qword ptr [rbx+30h], 0
0x1800029c6  mov     rcx, [rbx+8]; Block
0x1800029ca  call    cs:__imp_free
0x1800029d0  mov     qword ptr [rbx+8], 0
0x1800029d8  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800029df  add     rsp, 20h
0x1800029e3  pop     rbx
0x1800029e4  retn
```
