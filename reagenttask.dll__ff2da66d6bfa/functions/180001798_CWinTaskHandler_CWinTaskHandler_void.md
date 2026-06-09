# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180001798`
- end: `0x1800017fd`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `101`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180001850`

## callees

- `0x180001798`
- `0x180003010`

## import_xrefs

- `msvcrt!free` at `0x1800017de`
- `msvcrt!free` at `0x1800017de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800017af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800017af`

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
0x180001798  push    rbx
0x18000179a  sub     rsp, 20h
0x18000179e  mov     rbx, rcx
0x1800017a1  mov     rcx, [rcx+28h]; hObject
0x1800017a5  lea     rax, [rcx-1]
0x1800017a9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800017ad  ja      short loc_1800017C0
0x1800017af  call    cs:__imp_CloseHandle
0x1800017b6  nop     dword ptr [rax+rax+00h]
0x1800017bb  or      qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x1800017c0  mov     rcx, [rbx+30h]
0x1800017c4  test    rcx, rcx
0x1800017c7  jz      short loc_1800017DA
0x1800017c9  mov     rax, [rcx]
0x1800017cc  mov     rax, [rax+10h]
0x1800017d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017d5  and     qword ptr [rbx+30h], 0
0x1800017da  mov     rcx, [rbx+8]; Block
0x1800017de  call    cs:__imp_free
0x1800017e5  nop     dword ptr [rax+rax+00h]
0x1800017ea  and     qword ptr [rbx+8], 0
0x1800017ef  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800017f6  add     rsp, 20h
0x1800017fa  pop     rbx
0x1800017fb  retn
```
