# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x18000b298`
- end: `0x18000b2f9`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000b340`

## callees

- `0x18000b298`
- `0x18000e010`

## import_xrefs

- `msvcrt!free` at `0x18000b2de`
- `msvcrt!free` at `0x18000b2de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b2af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b2af`

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
0x18000b298  push    rbx
0x18000b29a  sub     rsp, 20h
0x18000b29e  mov     rbx, rcx
0x18000b2a1  mov     rcx, [rcx+28h]; hObject
0x18000b2a5  lea     rax, [rcx-1]
0x18000b2a9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b2ad  ja      short loc_18000B2BD
0x18000b2af  call    cs:__imp_CloseHandle
0x18000b2b5  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x18000b2bd  mov     rcx, [rbx+30h]
0x18000b2c1  test    rcx, rcx
0x18000b2c4  jz      short loc_18000B2DA
0x18000b2c6  mov     rax, [rcx]
0x18000b2c9  mov     rax, [rax+10h]
0x18000b2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2d2  mov     qword ptr [rbx+30h], 0
0x18000b2da  mov     rcx, [rbx+8]; Block
0x18000b2de  call    cs:__imp_free
0x18000b2e4  mov     qword ptr [rbx+8], 0
0x18000b2ec  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000b2f3  add     rsp, 20h
0x18000b2f7  pop     rbx
0x18000b2f8  retn
```
