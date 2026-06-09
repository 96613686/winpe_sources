# BDATuningModel::CBaseThread::CBaseThread(ulong)

- ea: `0x180038680`
- end: `0x1800386df`
- name: `??0CBaseThread@BDATuningModel@@QEAA@K@Z`
- size: `95`
- prototype: `__int64 __fastcall(BDATuningModel::CBaseThread *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800458b0`
- `0x180049cbc`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180038693`
- `KERNEL32!CreateEventW` at `0x1800386b0`
- `KERNEL32!CreateEventW` at `0x180038693`
- `KERNEL32!CreateEventW` at `0x1800386b0`
- `KERNEL32!InitializeCriticalSection` at `0x1800386be`
- `KERNEL32!InitializeCriticalSection` at `0x1800386c8`
- `KERNEL32!InitializeCriticalSection` at `0x1800386be`
- `KERNEL32!InitializeCriticalSection` at `0x1800386c8`

## pseudocode

```c
BDATuningModel::CBaseThread *__fastcall BDATuningModel::CBaseThread::CBaseThread(BDATuningModel::CBaseThread *this)
{
  BDATuningModel::CBaseThread *result; // rax

  *((_QWORD *)this + 1) = CreateEventW(0, 0, 0, 0);
  *((_DWORD *)this + 6) = 2;
  *((_QWORD *)this + 4) = CreateEventW(0, 1, 0, 0);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  result = this;
  *((_QWORD *)this + 5) = 0;
  return result;
}

```

## disassembly

```asm
0x180038680  push    rbx
0x180038682  sub     rsp, 20h
0x180038686  mov     rbx, rcx
0x180038689  xor     r9d, r9d; lpName
0x18003868c  xor     ecx, ecx; lpEventAttributes
0x18003868e  xor     r8d, r8d; bInitialState
0x180038691  xor     edx, edx; bManualReset
0x180038693  call    cs:__imp_CreateEventW
0x180038699  xor     r9d, r9d; lpName
0x18003869c  mov     [rbx+8], rax
0x1800386a0  xor     r8d, r8d; bInitialState
0x1800386a3  mov     dword ptr [rbx+18h], 2
0x1800386aa  xor     ecx, ecx; lpEventAttributes
0x1800386ac  lea     edx, [r9+1]; bManualReset
0x1800386b0  call    cs:__imp_CreateEventW
0x1800386b6  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800386ba  mov     [rbx+20h], rax
0x1800386be  call    cs:__imp_InitializeCriticalSection
0x1800386c4  lea     rcx, [rbx+58h]; lpCriticalSection
0x1800386c8  call    cs:__imp_InitializeCriticalSection
0x1800386ce  mov     rax, rbx
0x1800386d1  mov     qword ptr [rbx+28h], 0
0x1800386d9  add     rsp, 20h
0x1800386dd  pop     rbx
0x1800386de  retn
```
