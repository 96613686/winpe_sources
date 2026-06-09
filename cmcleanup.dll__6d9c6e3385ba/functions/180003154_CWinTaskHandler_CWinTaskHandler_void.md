# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180003154`
- end: `0x1800031b5`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800033d0`

## callees

- `0x180003154`
- `0x180009010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000319a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000319a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000316b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000316b`

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
0x180003154  push    rbx
0x180003156  sub     rsp, 20h
0x18000315a  mov     rbx, rcx
0x18000315d  mov     rcx, [rcx+28h]; hObject
0x180003161  lea     rax, [rcx-1]
0x180003165  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003169  ja      short loc_180003179
0x18000316b  call    cs:__imp_CloseHandle
0x180003171  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180003179  mov     rcx, [rbx+30h]
0x18000317d  test    rcx, rcx
0x180003180  jz      short loc_180003196
0x180003182  mov     rax, [rcx]
0x180003185  mov     rax, [rax+10h]
0x180003189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000318e  mov     qword ptr [rbx+30h], 0
0x180003196  mov     rcx, [rbx+8]; Block
0x18000319a  call    cs:__imp_free
0x1800031a0  mov     qword ptr [rbx+8], 0
0x1800031a8  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800031af  add     rsp, 20h
0x1800031b3  pop     rbx
0x1800031b4  retn
```
