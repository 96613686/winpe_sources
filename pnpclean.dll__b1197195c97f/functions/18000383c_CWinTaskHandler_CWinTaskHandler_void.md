# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x18000383c`
- end: `0x18000389d`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800038b0`

## callees

- `0x18000383c`
- `0x18000a010`

## import_xrefs

- `msvcrt!free` at `0x180003882`
- `msvcrt!free` at `0x180003882`
- `KERNEL32!CloseHandle` at `0x180003853`
- `KERNEL32!CloseHandle` at `0x180003853`

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
0x18000383c  push    rbx
0x18000383e  sub     rsp, 20h
0x180003842  mov     rbx, rcx
0x180003845  mov     rcx, [rcx+28h]; hObject
0x180003849  lea     rax, [rcx-1]
0x18000384d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003851  ja      short loc_180003861
0x180003853  call    cs:__imp_CloseHandle
0x180003859  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180003861  mov     rcx, [rbx+30h]
0x180003865  test    rcx, rcx
0x180003868  jz      short loc_18000387E
0x18000386a  mov     rax, [rcx]
0x18000386d  mov     rax, [rax+10h]
0x180003871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003876  mov     qword ptr [rbx+30h], 0
0x18000387e  mov     rcx, [rbx+8]; Block
0x180003882  call    cs:__imp_free
0x180003888  mov     qword ptr [rbx+8], 0
0x180003890  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180003897  add     rsp, 20h
0x18000389b  pop     rbx
0x18000389c  retn
```
