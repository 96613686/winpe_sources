# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180008148`
- end: `0x1800081a9`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180008a30`
- `0x18001a208`
- `0x1800209c7`

## callees

- `0x180008148`
- `0x180023010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000818e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000818e`
- `KERNEL32!CloseHandle` at `0x18000815f`
- `KERNEL32!CloseHandle` at `0x18000815f`

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
0x180008148  push    rbx
0x18000814a  sub     rsp, 20h
0x18000814e  mov     rbx, rcx
0x180008151  mov     rcx, [rcx+28h]; hObject
0x180008155  lea     rax, [rcx-1]
0x180008159  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000815d  ja      short loc_18000816D
0x18000815f  call    cs:__imp_CloseHandle
0x180008165  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x18000816d  mov     rcx, [rbx+30h]
0x180008171  test    rcx, rcx
0x180008174  jz      short loc_18000818A
0x180008176  mov     rax, [rcx]
0x180008179  mov     rax, [rax+10h]
0x18000817d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008182  mov     qword ptr [rbx+30h], 0
0x18000818a  mov     rcx, [rbx+8]; Block
0x18000818e  call    cs:__imp_free
0x180008194  mov     qword ptr [rbx+8], 0
0x18000819c  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800081a3  add     rsp, 20h
0x1800081a7  pop     rbx
0x1800081a8  retn
```
