# CEnumDebugStackFrames::Reset(void)

- ea: `0x180083390`
- end: `0x1800833e6`
- name: `?Reset@CEnumDebugStackFrames@@UEAAJXZ`
- size: `86`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180057100`
- `0x180083390`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800833a0`
- `KERNEL32!GetCurrentThreadId` at `0x1800833a0`

## pseudocode

```c
__int64 __fastcall CEnumDebugStackFrames::Reset(CEnumDebugStackFrames *this)
{
  int v1; // ebx
  CDebugStackFrame *v4; // rcx

  v1 = *((_DWORD *)this + 3);
  if ( GetCurrentThreadId() != v1 )
    return 2147549183LL;
  *((_DWORD *)this + 7) &= 0xFFFFFFFC;
  v4 = (CDebugStackFrame *)*((_QWORD *)this + 4);
  *((_DWORD *)this + 6) = 0;
  if ( v4 )
  {
    CDebugStackFrame::Release(v4);
    *((_QWORD *)this + 4) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180083390  mov     [rsp+arg_0], rbx
0x180083395  push    rdi
0x180083396  sub     rsp, 20h
0x18008339a  mov     ebx, [rcx+0Ch]
0x18008339d  mov     rdi, rcx
0x1800833a0  call    cs:__imp_GetCurrentThreadId
0x1800833a7  nop     dword ptr [rax+rax+00h]
0x1800833ac  cmp     eax, ebx
0x1800833ae  jz      short loc_1800833B7
0x1800833b0  mov     eax, 8000FFFFh
0x1800833b5  jmp     short loc_1800833DA
0x1800833b7  and     dword ptr [rdi+1Ch], 0FFFFFFFCh
0x1800833bb  mov     rcx, [rdi+20h]; this
0x1800833bf  mov     dword ptr [rdi+18h], 0
0x1800833c6  test    rcx, rcx
0x1800833c9  jz      short loc_1800833D8
0x1800833cb  call    ?Release@CDebugStackFrame@@UEAAKXZ; CDebugStackFrame::Release(void)
0x1800833d0  mov     qword ptr [rdi+20h], 0
0x1800833d8  xor     eax, eax
0x1800833da  mov     rbx, [rsp+28h+arg_0]
0x1800833df  add     rsp, 20h
0x1800833e3  pop     rdi
0x1800833e4  retn
```
