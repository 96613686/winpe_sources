# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180007f58`
- end: `0x180007fbd`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `101`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180008a10`
- `0x18001b190`
- `0x180022171`

## callees

- `0x180007f58`
- `0x180024010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f9e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f9e`
- `KERNEL32!CloseHandle` at `0x180007f6f`
- `KERNEL32!CloseHandle` at `0x180007f6f`

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
0x180007f58  push    rbx
0x180007f5a  sub     rsp, 20h
0x180007f5e  mov     rbx, rcx
0x180007f61  mov     rcx, [rcx+28h]; hObject
0x180007f65  lea     rax, [rcx-1]
0x180007f69  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007f6d  ja      short loc_180007F80
0x180007f6f  call    cs:__imp_CloseHandle
0x180007f76  nop     dword ptr [rax+rax+00h]
0x180007f7b  or      qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180007f80  mov     rcx, [rbx+30h]
0x180007f84  test    rcx, rcx
0x180007f87  jz      short loc_180007F9A
0x180007f89  mov     rax, [rcx]
0x180007f8c  mov     rax, [rax+10h]
0x180007f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f95  and     qword ptr [rbx+30h], 0
0x180007f9a  mov     rcx, [rbx+8]; Block
0x180007f9e  call    cs:__imp_free
0x180007fa5  nop     dword ptr [rax+rax+00h]
0x180007faa  and     qword ptr [rbx+8], 0
0x180007faf  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180007fb6  add     rsp, 20h
0x180007fba  pop     rbx
0x180007fbb  retn
```
