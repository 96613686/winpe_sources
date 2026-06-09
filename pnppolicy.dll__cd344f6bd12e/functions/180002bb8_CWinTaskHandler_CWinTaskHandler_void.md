# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180002bb8`
- end: `0x180002c19`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180002c60`

## callees

- `0x180002bb8`
- `0x18000b010`

## import_xrefs

- `msvcrt!free` at `0x180002bfe`
- `msvcrt!free` at `0x180002bfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002bcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002bcf`

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
0x180002bb8  push    rbx
0x180002bba  sub     rsp, 20h
0x180002bbe  mov     rbx, rcx
0x180002bc1  mov     rcx, [rcx+28h]; hObject
0x180002bc5  lea     rax, [rcx-1]
0x180002bc9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002bcd  ja      short loc_180002BDD
0x180002bcf  call    cs:__imp_CloseHandle
0x180002bd5  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180002bdd  mov     rcx, [rbx+30h]
0x180002be1  test    rcx, rcx
0x180002be4  jz      short loc_180002BFA
0x180002be6  mov     rax, [rcx]
0x180002be9  mov     rax, [rax+10h]
0x180002bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf2  mov     qword ptr [rbx+30h], 0
0x180002bfa  mov     rcx, [rbx+8]; Block
0x180002bfe  call    cs:__imp_free
0x180002c04  mov     qword ptr [rbx+8], 0
0x180002c0c  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180002c13  add     rsp, 20h
0x180002c17  pop     rbx
0x180002c18  retn
```
