# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180002408`
- end: `0x180002469`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800024b0`

## callees

- `0x180002408`
- `0x180014010`

## import_xrefs

- `msvcrt!free` at `0x18000244e`
- `msvcrt!free` at `0x18000244e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000241f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000241f`

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
0x180002408  push    rbx
0x18000240a  sub     rsp, 20h
0x18000240e  mov     rbx, rcx
0x180002411  mov     rcx, [rcx+28h]; hObject
0x180002415  lea     rax, [rcx-1]
0x180002419  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000241d  ja      short loc_18000242D
0x18000241f  call    cs:__imp_CloseHandle
0x180002425  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x18000242d  mov     rcx, [rbx+30h]
0x180002431  test    rcx, rcx
0x180002434  jz      short loc_18000244A
0x180002436  mov     rax, [rcx]
0x180002439  mov     rax, [rax+10h]
0x18000243d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002442  mov     qword ptr [rbx+30h], 0
0x18000244a  mov     rcx, [rbx+8]; Block
0x18000244e  call    cs:__imp_free
0x180002454  mov     qword ptr [rbx+8], 0
0x18000245c  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180002463  add     rsp, 20h
0x180002467  pop     rbx
0x180002468  retn
```
