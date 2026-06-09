# CVPMThread::Post(CVPMThread::Message *)

- ea: `0x1800cb39c`
- end: `0x1800cb449`
- name: `?Post@CVPMThread@@AEAAJPEAUMessage@1@@Z`
- size: `173`
- prototype: `__int64 __fastcall(CVPMThread *__hidden this, struct Message *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800cb180`
- `0x1800cb30c`
- `0x1800cb5e8`
- `0x1800cb674`
- `0x1800cb724`

## callees

- `0x180025d9c`
- `0x1800cb39c`
- `0x1800cb450`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800cb40d`
- `KERNEL32!SetEvent` at `0x1800cb40d`
- `KERNEL32!LeaveCriticalSection` at `0x1800cb3fd`
- `KERNEL32!LeaveCriticalSection` at `0x1800cb3fd`
- `KERNEL32!EnterCriticalSection` at `0x1800cb3da`
- `KERNEL32!EnterCriticalSection` at `0x1800cb3da`
- `KERNEL32!GetCurrentThreadId` at `0x1800cb3b4`
- `KERNEL32!GetCurrentThreadId` at `0x1800cb3b4`

## pseudocode

```c
__int64 __fastcall CVPMThread::Post(CVPMThread *this, struct Message *a2)
{
  int v2; // ebx
  __int64 v6; // rax
  bool v7; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 4);
  if ( GetCurrentThreadId() == v2 )
    return CVPMThread::ProcessMessage(this, a2, &v7);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v6 = *((_QWORD *)this + 13);
  *((_QWORD *)a2 + 1) = 0;
  if ( v6 )
  {
    while ( *(_QWORD *)(v6 + 8) )
      v6 = *(_QWORD *)(v6 + 8);
    *(_QWORD *)(v6 + 8) = a2;
  }
  else
  {
    *((_QWORD *)this + 13) = a2;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  SetEvent(*((HANDLE *)this + 12));
  CAMEvent::Wait((struct Message *)((char *)a2 + 16), 0xFFFFFFFF);
  return *((unsigned int *)a2 + 6);
}

```

## disassembly

```asm
0x1800cb39c  mov     [rsp+arg_8], rbx
0x1800cb3a1  mov     [rsp+arg_10], rsi
0x1800cb3a6  push    rdi
0x1800cb3a7  sub     rsp, 20h
0x1800cb3ab  mov     ebx, [rcx+10h]
0x1800cb3ae  mov     rdi, rdx
0x1800cb3b1  mov     rsi, rcx
0x1800cb3b4  call    cs:__imp_GetCurrentThreadId
0x1800cb3bb  nop     dword ptr [rax+rax+00h]
0x1800cb3c0  cmp     eax, ebx
0x1800cb3c2  jnz     short loc_1800CB3D6
0x1800cb3c4  lea     r8, [rsp+28h+arg_0]; bool *
0x1800cb3c9  mov     rdx, rdi; struct Message *
0x1800cb3cc  mov     rcx, rsi; this
0x1800cb3cf  call    ?ProcessMessage@CVPMThread@@AEAAJPEAUMessage@1@PEA_N@Z; CVPMThread::ProcessMessage(CVPMThread::Message *,bool *)
0x1800cb3d4  jmp     short loc_1800CB428
0x1800cb3d6  lea     rcx, [rsi+38h]; lpCriticalSection
0x1800cb3da  call    cs:__imp_EnterCriticalSection
0x1800cb3e1  nop     dword ptr [rax+rax+00h]
0x1800cb3e6  mov     rax, [rsi+68h]
0x1800cb3ea  xor     ecx, ecx
0x1800cb3ec  mov     [rdi+8], rcx
0x1800cb3f0  test    rax, rax
0x1800cb3f3  jnz     short loc_1800CB43D
0x1800cb3f5  mov     [rsi+68h], rdi
0x1800cb3f9  lea     rcx, [rsi+38h]; lpCriticalSection
0x1800cb3fd  call    cs:__imp_LeaveCriticalSection
0x1800cb404  nop     dword ptr [rax+rax+00h]
0x1800cb409  mov     rcx, [rsi+60h]; hEvent
0x1800cb40d  call    cs:__imp_SetEvent
0x1800cb414  nop     dword ptr [rax+rax+00h]
0x1800cb419  lea     rcx, [rdi+10h]; this
0x1800cb41d  or      edx, 0FFFFFFFFh; unsigned int
0x1800cb420  call    ?Wait@CAMEvent@@QEAAHK@Z; CAMEvent::Wait(ulong)
0x1800cb425  mov     eax, [rdi+18h]
0x1800cb428  mov     rbx, [rsp+28h+arg_8]
0x1800cb42d  mov     rsi, [rsp+28h+arg_10]
0x1800cb432  add     rsp, 20h
0x1800cb436  pop     rdi
0x1800cb437  retn
0x1800cb439  mov     rax, [rax+8]
0x1800cb43d  cmp     [rax+8], rcx
0x1800cb441  jnz     short loc_1800CB439
0x1800cb443  mov     [rax+8], rdi
0x1800cb447  jmp     short loc_1800CB3F9
```
