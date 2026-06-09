# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180003380`
- end: `0x1800033e1`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180003680`

## callees

- `0x180003380`
- `0x180009010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800033c6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800033c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003397`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003397`

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
0x180003380  push    rbx
0x180003382  sub     rsp, 20h
0x180003386  mov     rbx, rcx
0x180003389  mov     rcx, [rcx+28h]; hObject
0x18000338d  lea     rax, [rcx-1]
0x180003391  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003395  ja      short loc_1800033A5
0x180003397  call    cs:__imp_CloseHandle
0x18000339d  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x1800033a5  mov     rcx, [rbx+30h]
0x1800033a9  test    rcx, rcx
0x1800033ac  jz      short loc_1800033C2
0x1800033ae  mov     rax, [rcx]
0x1800033b1  mov     rax, [rax+10h]
0x1800033b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ba  mov     qword ptr [rbx+30h], 0
0x1800033c2  mov     rcx, [rbx+8]; Block
0x1800033c6  call    cs:__imp_free
0x1800033cc  mov     qword ptr [rbx+8], 0
0x1800033d4  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800033db  add     rsp, 20h
0x1800033df  pop     rbx
0x1800033e0  retn
```
