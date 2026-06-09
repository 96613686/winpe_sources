# CEnumDebugStackFrames::CEnumDebugStackFrames(unsigned __int64,CSession *)

- ea: `0x1800820b0`
- end: `0x18008211a`
- name: `??0CEnumDebugStackFrames@@QEAA@_KPEAVCSession@@@Z`
- size: `106`
- prototype: `CEnumDebugStackFrames *__fastcall(CEnumDebugStackFrames *__hidden this, unsigned __int64, struct CSession *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180079de0`
- `0x180079ea0`
- `0x180082480`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800820d9`
- `KERNEL32!GetCurrentThreadId` at `0x1800820d9`

## pseudocode

```c
CEnumDebugStackFrames *__fastcall CEnumDebugStackFrames::CEnumDebugStackFrames(
        CEnumDebugStackFrames *this,
        __int64 a2,
        struct CSession *a3)
{
  DWORD CurrentThreadId; // eax
  CEnumDebugStackFrames *result; // rax

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CEnumDebugStackFrames::`vftable';
  CurrentThreadId = GetCurrentThreadId();
  *((_DWORD *)this + 7) &= 0xFFFFFFFC;
  *((_DWORD *)this + 3) = CurrentThreadId;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = a3;
  _InterlockedIncrement((volatile signed __int32 *)a3);
  result = this;
  *((_QWORD *)this + 2) = a2;
  return result;
}

```

## disassembly

```asm
0x1800820b0  mov     [rsp+arg_0], rbx
0x1800820b5  mov     [rsp+arg_8], rsi
0x1800820ba  push    rdi
0x1800820bb  sub     rsp, 20h
0x1800820bf  lea     rax, ??_7CEnumDebugStackFrames@@6B@; const CEnumDebugStackFrames::`vftable'
0x1800820c6  mov     dword ptr [rcx+8], 1
0x1800820cd  mov     [rcx], rax
0x1800820d0  mov     rbx, r8
0x1800820d3  mov     rdi, rdx
0x1800820d6  mov     rsi, rcx
0x1800820d9  call    cs:__imp_GetCurrentThreadId
0x1800820e0  nop     dword ptr [rax+rax+00h]
0x1800820e5  and     dword ptr [rsi+1Ch], 0FFFFFFFCh
0x1800820e9  mov     [rsi+0Ch], eax
0x1800820ec  mov     dword ptr [rsi+18h], 0
0x1800820f3  mov     qword ptr [rsi+20h], 0
0x1800820fb  mov     [rsi+28h], rbx
0x1800820ff  lock inc dword ptr [rbx]
0x180082102  mov     rbx, [rsp+28h+arg_0]
0x180082107  mov     rax, rsi
0x18008210a  mov     [rsi+10h], rdi
0x18008210e  mov     rsi, [rsp+28h+arg_8]
0x180082113  add     rsp, 20h
0x180082117  pop     rdi
0x180082118  retn
```
