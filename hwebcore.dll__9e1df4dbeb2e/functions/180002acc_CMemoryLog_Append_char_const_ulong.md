# CMemoryLog::Append(char const *,ulong)

- ea: `0x180002acc`
- end: `0x180002b8b`
- name: `?Append@CMemoryLog@@QEAAKPEBDK@Z`
- size: `191`
- prototype: `unsigned int(CMemoryLog *__hidden this, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800023a8`

## callees

- `0x180002acc`
- `0x180002d96`
- `0x180002da2`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b16`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b16`

## pseudocode

```c
__int64 __fastcall CMemoryLog::Append(struct _RTL_CRITICAL_SECTION *this, const char *a2, unsigned int a3)
{
  size_t v5; // rdi
  __int64 result; // rax
  void *v7; // rcx
  unsigned __int64 OwningThread; // r8
  char *v9; // rsi

  if ( !LODWORD(this[1].SpinCount) || !LODWORD(this[3].DebugInfo) )
    return 8;
  v5 = a3;
  if ( (unsigned __int64)a3 + 1 > 0xFFFFFFFF )
    return 534;
  if ( a3 + 1 > LODWORD(this[1].LockSemaphore) )
    return 8;
  EnterCriticalSection(this + 2);
  v7 = *(void **)&this->LockCount;
  OwningThread = (unsigned __int64)this->OwningThread;
  if ( (unsigned __int64)v7 + v5 + 1 >= OwningThread )
  {
    v9 = (char *)this[1].OwningThread;
    memset_0(v7, 0, OwningThread - (_QWORD)v7);
  }
  else
  {
    v9 = *(char **)&this->LockCount;
  }
  *(_QWORD *)&this->LockCount = &v9[v5 + 1];
  LeaveCriticalSection(this + 2);
  memcpy_0(v9, a2, v5);
  result = 0;
  v9[v5] = 0;
  return result;
}

```

## disassembly

```asm
0x180002acc  push    rbx
0x180002ace  push    rbp
0x180002acf  push    rsi
0x180002ad0  push    rdi
0x180002ad1  push    r14
0x180002ad3  sub     rsp, 20h
0x180002ad7  cmp     dword ptr [rcx+48h], 0
0x180002adb  mov     r14, rdx
0x180002ade  mov     rbx, rcx
0x180002ae1  jz      loc_180002B7A
0x180002ae7  cmp     dword ptr [rcx+78h], 0
0x180002aeb  jz      loc_180002B7A
0x180002af1  mov     edi, r8d
0x180002af4  mov     ecx, 0FFFFFFFFh
0x180002af9  lea     rax, [rdi+1]
0x180002afd  cmp     rax, rcx
0x180002b00  jbe     short loc_180002B09
0x180002b02  mov     eax, 216h
0x180002b07  jmp     short loc_180002B7F
0x180002b09  lea     eax, [r8+1]
0x180002b0d  cmp     eax, [rbx+40h]
0x180002b10  ja      short loc_180002B7A
0x180002b12  lea     rcx, [rbx+50h]; lpCriticalSection
0x180002b16  call    cs:__imp_EnterCriticalSection
0x180002b1d  nop     dword ptr [rax+rax+00h]
0x180002b22  mov     rcx, [rbx+8]; void *
0x180002b26  lea     rax, [rdi+1]
0x180002b2a  mov     r8, [rbx+10h]
0x180002b2e  add     rax, rcx
0x180002b31  cmp     rax, r8
0x180002b34  jnb     short loc_180002B3B
0x180002b36  mov     rsi, rcx
0x180002b39  jmp     short loc_180002B49
0x180002b3b  mov     rsi, [rbx+38h]
0x180002b3f  sub     r8, rcx; Size
0x180002b42  xor     edx, edx; Val
0x180002b44  call    memset_0
0x180002b49  lea     rax, [rdi+1]
0x180002b4d  add     rax, rsi
0x180002b50  lea     rcx, [rbx+50h]; lpCriticalSection
0x180002b54  mov     [rbx+8], rax
0x180002b58  call    cs:__imp_LeaveCriticalSection
0x180002b5f  nop     dword ptr [rax+rax+00h]
0x180002b64  mov     r8, rdi; Size
0x180002b67  mov     rdx, r14; Src
0x180002b6a  mov     rcx, rsi; void *
0x180002b6d  call    memcpy_0
0x180002b72  xor     eax, eax
0x180002b74  mov     byte ptr [rdi+rsi], 0
0x180002b78  jmp     short loc_180002B7F
0x180002b7a  mov     eax, 8
0x180002b7f  add     rsp, 20h
0x180002b83  pop     r14
0x180002b85  pop     rdi
0x180002b86  pop     rsi
0x180002b87  pop     rbp
0x180002b88  pop     rbx
0x180002b89  retn
```
