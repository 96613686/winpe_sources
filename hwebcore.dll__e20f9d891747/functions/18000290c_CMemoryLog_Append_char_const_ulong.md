# CMemoryLog::Append(char const *,ulong)

- ea: `0x18000290c`
- end: `0x1800029ba`
- name: `?Append@CMemoryLog@@QEAAKPEBDK@Z`
- size: `174`
- prototype: `unsigned int(CMemoryLog *__hidden this, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800022ac`

## callees

- `0x18000290c`
- `0x180002b96`
- `0x180002ba2`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000298e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000298e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002952`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002952`

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
0x18000290c  push    rbx
0x18000290e  push    rbp
0x18000290f  push    rsi
0x180002910  push    rdi
0x180002911  push    r14
0x180002913  sub     rsp, 20h
0x180002917  cmp     dword ptr [rcx+48h], 0
0x18000291b  mov     r14, rdx
0x18000291e  mov     rbx, rcx
0x180002921  jz      loc_1800029AA
0x180002927  cmp     dword ptr [rcx+78h], 0
0x18000292b  jz      short loc_1800029AA
0x18000292d  mov     edi, r8d
0x180002930  mov     ecx, 0FFFFFFFFh
0x180002935  lea     rax, [rdi+1]
0x180002939  cmp     rax, rcx
0x18000293c  jbe     short loc_180002945
0x18000293e  mov     eax, 216h
0x180002943  jmp     short loc_1800029AF
0x180002945  lea     eax, [r8+1]
0x180002949  cmp     eax, [rbx+40h]
0x18000294c  ja      short loc_1800029AA
0x18000294e  lea     rcx, [rbx+50h]; lpCriticalSection
0x180002952  call    cs:__imp_EnterCriticalSection
0x180002958  mov     rcx, [rbx+8]; void *
0x18000295c  lea     rax, [rdi+1]
0x180002960  mov     r8, [rbx+10h]
0x180002964  add     rax, rcx
0x180002967  cmp     rax, r8
0x18000296a  jnb     short loc_180002971
0x18000296c  mov     rsi, rcx
0x18000296f  jmp     short loc_18000297F
0x180002971  mov     rsi, [rbx+38h]
0x180002975  sub     r8, rcx; Size
0x180002978  xor     edx, edx; Val
0x18000297a  call    memset_0
0x18000297f  lea     rax, [rdi+1]
0x180002983  add     rax, rsi
0x180002986  lea     rcx, [rbx+50h]; lpCriticalSection
0x18000298a  mov     [rbx+8], rax
0x18000298e  call    cs:__imp_LeaveCriticalSection
0x180002994  mov     r8, rdi; Size
0x180002997  mov     rdx, r14; Src
0x18000299a  mov     rcx, rsi; void *
0x18000299d  call    memcpy_0
0x1800029a2  xor     eax, eax
0x1800029a4  mov     byte ptr [rdi+rsi], 0
0x1800029a8  jmp     short loc_1800029AF
0x1800029aa  mov     eax, 8
0x1800029af  add     rsp, 20h
0x1800029b3  pop     r14
0x1800029b5  pop     rdi
0x1800029b6  pop     rsi
0x1800029b7  pop     rbp
0x1800029b8  pop     rbx
0x1800029b9  retn
```
