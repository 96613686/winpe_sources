# CMutex::~CMutex(void)

- ea: `0x18000ca3c`
- end: `0x18000ca6c`
- name: `??1CMutex@@UEAA@XZ`
- size: `48`
- prototype: `void __fastcall(CMutex *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180008e20`
- `0x18000ca80`
- `0x18000cb6c`
- `0x18000cb90`

## callees

- `0x18000ca3c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000ca58`
- `KERNEL32!CloseHandle` at `0x18000ca58`

## pseudocode

```c
void __fastcall CMutex::~CMutex(CMutex *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CMutex::`vftable';
  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18000ca3c  push    rbx
0x18000ca3e  sub     rsp, 20h
0x18000ca42  lea     rax, ??_7CMutex@@6B@; const CMutex::`vftable'
0x18000ca49  mov     rbx, rcx
0x18000ca4c  mov     [rcx], rax
0x18000ca4f  mov     rcx, [rcx+8]; hObject
0x18000ca53  test    rcx, rcx
0x18000ca56  jz      short loc_18000CA66
0x18000ca58  call    cs:__imp_CloseHandle
0x18000ca5e  mov     qword ptr [rbx+8], 0
0x18000ca66  add     rsp, 20h
0x18000ca6a  pop     rbx
0x18000ca6b  retn
```
