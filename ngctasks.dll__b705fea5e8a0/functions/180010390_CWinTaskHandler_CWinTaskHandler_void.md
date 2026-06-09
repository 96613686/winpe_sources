# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180010390`
- end: `0x1800103f1`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001036c`
- `0x18001feb1`
- `0x180020231`

## callees

- `0x180010390`
- `0x180022010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800103d6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800103d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800103a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800103a7`

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
0x180010390  push    rbx
0x180010392  sub     rsp, 20h
0x180010396  mov     rbx, rcx
0x180010399  mov     rcx, [rcx+28h]; hObject
0x18001039d  lea     rax, [rcx-1]
0x1800103a1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800103a5  ja      short loc_1800103B5
0x1800103a7  call    cs:__imp_CloseHandle
0x1800103ad  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x1800103b5  mov     rcx, [rbx+30h]
0x1800103b9  test    rcx, rcx
0x1800103bc  jz      short loc_1800103D2
0x1800103be  mov     rax, [rcx]
0x1800103c1  mov     rax, [rax+10h]
0x1800103c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103ca  mov     qword ptr [rbx+30h], 0
0x1800103d2  mov     rcx, [rbx+8]; Block
0x1800103d6  call    cs:__imp_free
0x1800103dc  mov     qword ptr [rbx+8], 0
0x1800103e4  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800103eb  add     rsp, 20h
0x1800103ef  pop     rbx
0x1800103f0  retn
```
