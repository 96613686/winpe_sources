# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180001a74`
- end: `0x180001ad5`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180001a44`

## callees

- `0x180001a74`
- `0x180004010`

## import_xrefs

- `msvcrt!free` at `0x180001aba`
- `msvcrt!free` at `0x180001aba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001a8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001a8b`

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
0x180001a74  push    rbx
0x180001a76  sub     rsp, 20h
0x180001a7a  mov     rbx, rcx
0x180001a7d  mov     rcx, [rcx+28h]; hObject
0x180001a81  lea     rax, [rcx-1]
0x180001a85  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001a89  ja      short loc_180001A99
0x180001a8b  call    cs:__imp_CloseHandle
0x180001a91  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180001a99  mov     rcx, [rbx+30h]
0x180001a9d  test    rcx, rcx
0x180001aa0  jz      short loc_180001AB6
0x180001aa2  mov     rax, [rcx]
0x180001aa5  mov     rax, [rax+10h]
0x180001aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001aae  mov     qword ptr [rbx+30h], 0
0x180001ab6  mov     rcx, [rbx+8]; Block
0x180001aba  call    cs:__imp_free
0x180001ac0  mov     qword ptr [rbx+8], 0
0x180001ac8  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180001acf  add     rsp, 20h
0x180001ad3  pop     rbx
0x180001ad4  retn
```
