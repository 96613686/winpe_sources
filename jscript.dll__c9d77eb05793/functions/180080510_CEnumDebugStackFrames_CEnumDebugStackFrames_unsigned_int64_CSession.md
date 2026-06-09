# CEnumDebugStackFrames::CEnumDebugStackFrames(unsigned __int64,CSession *)

- ea: `0x180080510`
- end: `0x180080573`
- name: `??0CEnumDebugStackFrames@@QEAA@_KPEAVCSession@@@Z`
- size: `99`
- prototype: `CEnumDebugStackFrames *__fastcall(CEnumDebugStackFrames *__hidden this, unsigned __int64, struct CSession *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800787c0`
- `0x180078880`
- `0x1800808c0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180080539`
- `KERNEL32!GetCurrentThreadId` at `0x180080539`

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
0x180080510  mov     [rsp+arg_0], rbx
0x180080515  mov     [rsp+arg_8], rsi
0x18008051a  push    rdi
0x18008051b  sub     rsp, 20h
0x18008051f  lea     rax, ??_7CEnumDebugStackFrames@@6B@; const CEnumDebugStackFrames::`vftable'
0x180080526  mov     dword ptr [rcx+8], 1
0x18008052d  mov     [rcx], rax
0x180080530  mov     rbx, r8
0x180080533  mov     rdi, rdx
0x180080536  mov     rsi, rcx
0x180080539  call    cs:__imp_GetCurrentThreadId
0x18008053f  and     dword ptr [rsi+1Ch], 0FFFFFFFCh
0x180080543  mov     [rsi+0Ch], eax
0x180080546  mov     dword ptr [rsi+18h], 0
0x18008054d  mov     qword ptr [rsi+20h], 0
0x180080555  mov     [rsi+28h], rbx
0x180080559  lock inc dword ptr [rbx]
0x18008055c  mov     rbx, [rsp+28h+arg_0]
0x180080561  mov     rax, rsi
0x180080564  mov     [rsi+10h], rdi
0x180080568  mov     rsi, [rsp+28h+arg_8]
0x18008056d  add     rsp, 20h
0x180080571  pop     rdi
0x180080572  retn
```
