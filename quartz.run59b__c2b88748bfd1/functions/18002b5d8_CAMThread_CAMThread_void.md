# CAMThread::~CAMThread(void)

- ea: `0x18002b5d8`
- end: `0x18002b667`
- name: `??1CAMThread@@UEAA@XZ`
- size: `143`
- prototype: `void __fastcall(CAMThread *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18007c350`
- `0x180118608`
- `0x18011c8e0`
- `0x1801517f4`
- `0x180151950`
- `0x180153b80`

## callees

- `0x18002b5d8`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18002b5f6`
- `KERNEL32!WaitForSingleObject` at `0x18002b5f6`
- `KERNEL32!DeleteCriticalSection` at `0x18002b615`
- `KERNEL32!DeleteCriticalSection` at `0x18002b625`
- `KERNEL32!DeleteCriticalSection` at `0x18002b615`
- `KERNEL32!DeleteCriticalSection` at `0x18002b625`
- `KERNEL32!CloseHandle` at `0x18002b605`
- `KERNEL32!CloseHandle` at `0x18002b63a`
- `KERNEL32!CloseHandle` at `0x18002b64f`
- `KERNEL32!CloseHandle` at `0x18002b605`
- `KERNEL32!CloseHandle` at `0x18002b63a`
- `KERNEL32!CloseHandle` at `0x18002b64f`

## pseudocode

```c
void __fastcall CAMThread::~CAMThread(struct _RTL_CRITICAL_SECTION *this)
{
  void *v2; // rdi
  HANDLE OwningThread; // rcx
  void *v4; // rcx

  v2 = (void *)_InterlockedExchange64((volatile __int64 *)&this->SpinCount, 0);
  if ( v2 )
  {
    WaitForSingleObject(v2, 0xFFFFFFFF);
    CloseHandle(v2);
  }
  DeleteCriticalSection(this + 2);
  DeleteCriticalSection(this + 1);
  OwningThread = this->OwningThread;
  if ( OwningThread )
    CloseHandle(OwningThread);
  v4 = *(void **)&this->LockCount;
  if ( v4 )
    CloseHandle(v4);
}

```

## disassembly

```asm
0x18002b5d8  mov     [rsp+arg_0], rbx
0x18002b5dd  push    rdi
0x18002b5de  sub     rsp, 20h
0x18002b5e2  xor     edi, edi
0x18002b5e4  mov     rbx, rcx
0x18002b5e7  xchg    rdi, [rcx+20h]
0x18002b5eb  test    rdi, rdi
0x18002b5ee  jz      short loc_18002B611
0x18002b5f0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002b5f3  mov     rcx, rdi; hHandle
0x18002b5f6  call    cs:__imp_WaitForSingleObject
0x18002b5fd  nop     dword ptr [rax+rax+00h]
0x18002b602  mov     rcx, rdi; hObject
0x18002b605  call    cs:__imp_CloseHandle
0x18002b60c  nop     dword ptr [rax+rax+00h]
0x18002b611  lea     rcx, [rbx+50h]; lpCriticalSection
0x18002b615  call    cs:__imp_DeleteCriticalSection
0x18002b61c  nop     dword ptr [rax+rax+00h]
0x18002b621  lea     rcx, [rbx+28h]; lpCriticalSection
0x18002b625  call    cs:__imp_DeleteCriticalSection
0x18002b62c  nop     dword ptr [rax+rax+00h]
0x18002b631  mov     rcx, [rbx+10h]; hObject
0x18002b635  test    rcx, rcx
0x18002b638  jz      short loc_18002B646
0x18002b63a  call    cs:__imp_CloseHandle
0x18002b641  nop     dword ptr [rax+rax+00h]
0x18002b646  mov     rcx, [rbx+8]; hObject
0x18002b64a  test    rcx, rcx
0x18002b64d  jz      short loc_18002B65B
0x18002b64f  call    cs:__imp_CloseHandle
0x18002b656  nop     dword ptr [rax+rax+00h]
0x18002b65b  mov     rbx, [rsp+28h+arg_0]
0x18002b660  add     rsp, 20h
0x18002b664  pop     rdi
0x18002b665  retn
```
