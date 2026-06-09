# FILE_LISTENER::~FILE_LISTENER(void)

- ea: `0x180003e1c`
- end: `0x180003ea6`
- name: `??1FILE_LISTENER@@QEAA@XZ`
- size: `138`
- prototype: `void __fastcall(FILE_LISTENER *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003eb0`
- `0x18000401c`
- `0x180004544`
- `0x180007090`
- `0x180007b00`

## callees

- `0x180003e1c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e39`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003e98`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003e89`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003e89`

## pseudocode

```c
void __fastcall FILE_LISTENER::~FILE_LISTENER(FILE_LISTENER *this)
{
  void *v2; // rcx
  char *v3; // rcx
  __int64 v4; // rax
  char **v5; // rdx

  *((_DWORD *)this + 46) = 1;
  v2 = (void *)*((_QWORD *)this + 10);
  if ( v2 != (void *)-1LL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 10) = -1;
  }
  if ( *((_DWORD *)this + 47) == 1 )
  {
    v3 = (char *)this + 192;
    v4 = *((_QWORD *)this + 24);
    if ( v4 )
    {
      if ( *(char **)(v4 + 8) != v3 || (v5 = (char **)*((_QWORD *)this + 25), *v5 != v3) )
        __fastfail(3u);
      *v5 = (char *)v4;
      *(_QWORD *)(v4 + 8) = v5;
    }
  }
  _InterlockedDecrement(&FILE_LISTENER::sm_cListeners);
  *(_DWORD *)this = 1718842220;
  BUFFER::~BUFFER((FILE_LISTENER *)((char *)this + 136));
  STRU::~STRU((FILE_LISTENER *)((char *)this + 16));
}

```

## disassembly

```asm
0x180003e1c  push    rbx
0x180003e1e  sub     rsp, 20h
0x180003e22  mov     rbx, rcx
0x180003e25  mov     dword ptr [rcx+0B8h], 1
0x180003e2f  mov     rcx, [rcx+50h]; hObject
0x180003e33  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003e37  jz      short loc_180003E47
0x180003e39  call    cs:__imp_CloseHandle
0x180003e3f  mov     qword ptr [rbx+50h], 0FFFFFFFFFFFFFFFFh
0x180003e47  cmp     dword ptr [rbx+0BCh], 1
0x180003e4e  jnz     short loc_180003E75
0x180003e50  lea     rcx, [rbx+0C0h]
0x180003e57  mov     rax, [rcx]
0x180003e5a  test    rax, rax
0x180003e5d  jz      short loc_180003E75
0x180003e5f  cmp     [rax+8], rcx
0x180003e63  jnz     short loc_180003E9F
0x180003e65  mov     rdx, [rcx+8]
0x180003e69  cmp     [rdx], rcx
0x180003e6c  jnz     short loc_180003E9F
0x180003e6e  mov     [rdx], rax
0x180003e71  mov     [rax+8], rdx
0x180003e75  lock dec cs:?sm_cListeners@FILE_LISTENER@@0JA; long FILE_LISTENER::sm_cListeners
0x180003e7c  lea     rcx, [rbx+88h]
0x180003e83  mov     dword ptr [rbx], 6673736Ch
0x180003e89  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003e8f  lea     rcx, [rbx+10h]
0x180003e93  add     rsp, 20h
0x180003e97  pop     rbx
0x180003e98  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003e9f  mov     ecx, 3
0x180003ea4  int     29h; Win8: RtlFailFast(ecx)
```
