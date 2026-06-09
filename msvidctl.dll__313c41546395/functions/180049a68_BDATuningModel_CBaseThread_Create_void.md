# BDATuningModel::CBaseThread::Create(void)

- ea: `0x180049a68`
- end: `0x180049adf`
- name: `?Create@CBaseThread@BDATuningModel@@QEAAHXZ`
- size: `119`
- prototype: `__int64 __fastcall(BDATuningModel::CBaseThread *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800458b0`
- `0x180049cbc`

## callees

- `0x180049a68`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180049ab1`
- `KERNEL32!CreateThread` at `0x180049ab1`
- `KERNEL32!LeaveCriticalSection` at `0x180049acc`
- `KERNEL32!LeaveCriticalSection` at `0x180049acc`
- `KERNEL32!EnterCriticalSection` at `0x180049a84`
- `KERNEL32!EnterCriticalSection` at `0x180049a84`

## pseudocode

```c
_BOOL8 __fastcall BDATuningModel::CBaseThread::Create(BDATuningModel::CBaseThread *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  HANDLE v3; // rax
  BOOL v4; // ebx
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  ThreadId = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v4 = 0;
  if ( !*((_QWORD *)this + 5) )
  {
    v3 = CreateThread(0, 0, BDATuningModel::CBaseThread::InitialThreadProc, this, 0, &ThreadId);
    *((_QWORD *)this + 5) = v3;
    if ( v3 )
      v4 = 1;
  }
  LeaveCriticalSection(v1);
  return v4;
}

```

## disassembly

```asm
0x180049a68  mov     [rsp+arg_8], rbx
0x180049a6d  push    rdi
0x180049a6e  sub     rsp, 30h
0x180049a72  lea     rdi, [rcx+30h]
0x180049a76  mov     [rsp+38h+ThreadId], 0
0x180049a7e  mov     rbx, rcx
0x180049a81  mov     rcx, rdi; lpCriticalSection
0x180049a84  call    cs:__imp_EnterCriticalSection
0x180049a8a  cmp     qword ptr [rbx+28h], 0
0x180049a8f  jnz     short loc_180049AC7
0x180049a91  lea     rax, [rsp+38h+ThreadId]
0x180049a96  mov     r9, rbx; lpParameter
0x180049a99  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180049a9e  lea     r8, ?InitialThreadProc@CBaseThread@BDATuningModel@@SAKPEAX@Z; lpStartAddress
0x180049aa5  xor     edx, edx; dwStackSize
0x180049aa7  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180049aaf  xor     ecx, ecx; lpThreadAttributes
0x180049ab1  call    cs:__imp_CreateThread
0x180049ab7  mov     [rbx+28h], rax
0x180049abb  test    rax, rax
0x180049abe  jz      short loc_180049AC7
0x180049ac0  mov     ebx, 1
0x180049ac5  jmp     short loc_180049AC9
0x180049ac7  xor     ebx, ebx
0x180049ac9  mov     rcx, rdi; lpCriticalSection
0x180049acc  call    cs:__imp_LeaveCriticalSection
0x180049ad2  mov     eax, ebx
0x180049ad4  mov     rbx, [rsp+38h+arg_8]
0x180049ad9  add     rsp, 30h
0x180049add  pop     rdi
0x180049ade  retn
```
