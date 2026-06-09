# CMemoryLog::~CMemoryLog(void)

- ea: `0x18000351c`
- end: `0x18000356f`
- name: `??1CMemoryLog@@QEAA@XZ`
- size: `83`
- prototype: `void __fastcall(CMemoryLog *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f84`

## callees

- `0x180002ff8`
- `0x18000351c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000354d`
- `KERNEL32!DeleteCriticalSection` at `0x18000354d`

## pseudocode

```c
void __fastcall CMemoryLog::~CMemoryLog(struct _RTL_CRITICAL_SECTION *this)
{
  bool v1; // zf

  v1 = LODWORD(this[3].DebugInfo) == 0;
  this->DebugInfo = 0;
  *(_QWORD *)&this->LockCount = 0;
  this->OwningThread = 0;
  LODWORD(this[1].SpinCount) = 0;
  if ( !v1 )
  {
    DeleteCriticalSection(this + 2);
    LODWORD(this[3].DebugInfo) = 0;
  }
  if ( BYTE4(this[1].LockSemaphore) )
    BUFFER::FreeMemoryInternal((BUFFER *)&this->LockSemaphore);
}

```

## disassembly

```asm
0x18000351c  push    rbx
0x18000351e  sub     rsp, 20h
0x180003522  cmp     dword ptr [rcx+78h], 0
0x180003526  mov     rbx, rcx
0x180003529  mov     qword ptr [rcx], 0
0x180003530  mov     qword ptr [rcx+8], 0
0x180003538  mov     qword ptr [rcx+10h], 0
0x180003540  mov     dword ptr [rcx+48h], 0
0x180003547  jz      short loc_18000355A
0x180003549  add     rcx, 50h ; 'P'; lpCriticalSection
0x18000354d  call    cs:__imp_DeleteCriticalSection
0x180003553  mov     dword ptr [rbx+78h], 0
0x18000355a  lea     rcx, [rbx+18h]; this
0x18000355e  cmp     byte ptr [rcx+2Ch], 0
0x180003562  jz      short loc_180003569
0x180003564  call    ?FreeMemoryInternal@BUFFER@@AEAAXXZ; BUFFER::FreeMemoryInternal(void)
0x180003569  add     rsp, 20h
0x18000356d  pop     rbx
0x18000356e  retn
```
