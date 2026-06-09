# TOKEN_ENTRY::~TOKEN_ENTRY(void)

- ea: `0x180010a80`
- end: `0x180010afd`
- name: `??1TOKEN_ENTRY@@EEAA@XZ`
- size: `125`
- prototype: `void __fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010b10`

## callees

- `0x18000c45c`
- `0x180010a80`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010ab3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010acf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010ab3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010acf`
- `iisutil!??1CSmallSpinLock@@QEAA@XZ` at `0x180010ae4`
- `iisutil!??1CSmallSpinLock@@QEAA@XZ` at `0x180010ae4`

## pseudocode

```c
void __fastcall TOKEN_ENTRY::~TOKEN_ENTRY(TOKEN_ENTRY *this)
{
  void *v2; // rcx
  _BYTE *v3; // rdi
  void *v4; // rcx

  *((_DWORD *)this + 2) = 1852534644;
  *(_QWORD *)this = &TOKEN_ENTRY::`vftable';
  v2 = (void *)*((_QWORD *)this + 2);
  v3 = (char *)this + 260;
  if ( v2 )
  {
    if ( (*v3 & 1) != 0 )
      CloseHandle(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    if ( (*v3 & 2) != 0 )
      CloseHandle(v4);
    *((_QWORD *)this + 3) = 0;
  }
  CSmallSpinLock::~CSmallSpinLock((TOKEN_ENTRY *)((char *)this + 248));
  TOKEN_KEY::~TOKEN_KEY((TOKEN_ENTRY *)((char *)this + 120));
}

```

## disassembly

```asm
0x180010a80  mov     [rsp+arg_0], rbx
0x180010a85  push    rdi
0x180010a86  sub     rsp, 20h
0x180010a8a  mov     rbx, rcx
0x180010a8d  mov     dword ptr [rcx+8], 6E6B6F74h
0x180010a94  lea     rax, ??_7TOKEN_ENTRY@@6B@; const TOKEN_ENTRY::`vftable'
0x180010a9b  mov     [rcx], rax
0x180010a9e  mov     rcx, [rcx+10h]; hObject
0x180010aa2  lea     rdi, [rbx+104h]
0x180010aa9  test    rcx, rcx
0x180010aac  jz      short loc_180010AC1
0x180010aae  test    byte ptr [rdi], 1
0x180010ab1  jz      short loc_180010AB9
0x180010ab3  call    cs:__imp_CloseHandle
0x180010ab9  mov     qword ptr [rbx+10h], 0
0x180010ac1  mov     rcx, [rbx+18h]; hObject
0x180010ac5  test    rcx, rcx
0x180010ac8  jz      short loc_180010ADD
0x180010aca  test    byte ptr [rdi], 2
0x180010acd  jz      short loc_180010AD5
0x180010acf  call    cs:__imp_CloseHandle
0x180010ad5  mov     qword ptr [rbx+18h], 0
0x180010add  lea     rcx, [rbx+0F8h]
0x180010ae4  call    cs:__imp_??1CSmallSpinLock@@QEAA@XZ; CSmallSpinLock::~CSmallSpinLock(void)
0x180010aea  lea     rcx, [rbx+78h]; this
0x180010aee  mov     rbx, [rsp+28h+arg_0]
0x180010af3  add     rsp, 20h
0x180010af7  pop     rdi
0x180010af8  jmp     ??1TOKEN_KEY@@QEAA@XZ; TOKEN_KEY::~TOKEN_KEY(void)
```
