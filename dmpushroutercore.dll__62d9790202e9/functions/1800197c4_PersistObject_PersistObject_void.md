# PersistObject::~PersistObject(void)

- ea: `0x1800197c4`
- end: `0x18001986f`
- name: `??1PersistObject@@UEAA@XZ`
- size: `171`
- prototype: `void __fastcall(PersistObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180019880`
- `0x1800198c0`

## callees

- `0x180003a14`
- `0x1800197c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019853`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019853`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019868`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800197e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800197e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019818`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019840`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001984a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019818`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019840`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001984a`

## pseudocode

```c
void __fastcall PersistObject::~PersistObject(PersistObject *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // r14
  __int64 v3; // rbp
  HLOCAL *v4; // rbx
  _QWORD *v5; // rdi
  void *v6; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  *(_QWORD *)this = &PersistObject::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v3 = 0;
  v4 = (HLOCAL *)((char *)this + 8);
  if ( *((_DWORD *)this + 4) )
  {
    while ( 1 )
    {
      v5 = (_QWORD *)*((_QWORD *)*v4 + v3);
      if ( v5 )
        break;
LABEL_9:
      *((_QWORD *)*v4 + v3) = 0;
      v3 = (unsigned int)(v3 + 1);
      if ( (unsigned int)v3 >= *((_DWORD *)this + 4) )
        goto LABEL_10;
    }
    if ( *(_DWORD *)v5 == 1 )
    {
      v6 = (void *)v5[2];
    }
    else
    {
      if ( *(_DWORD *)v5 != 3 )
      {
LABEL_8:
        operator delete(v5, (const struct std::nothrow_t *)0x20);
        goto LABEL_9;
      }
      v6 = (void *)v5[3];
    }
    LocalFree(v6);
    goto LABEL_8;
  }
LABEL_10:
  LocalFree(*v4);
  LocalFree(*((HLOCAL *)this + 3));
  LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
}

```

## disassembly

```asm
0x1800197c4  push    rbx
0x1800197c6  push    rbp
0x1800197c7  push    rsi
0x1800197c8  push    rdi
0x1800197c9  push    r14
0x1800197cb  push    r15
0x1800197cd  sub     rsp, 28h
0x1800197d1  lea     rax, ??_7PersistObject@@6B@; const PersistObject::`vftable'
0x1800197d8  mov     rsi, rcx
0x1800197db  lea     r14, [rcx+20h]
0x1800197df  mov     [rcx], rax
0x1800197e2  mov     rcx, r14; lpCriticalSection
0x1800197e5  call    cs:__imp_EnterCriticalSection
0x1800197eb  xor     ebp, ebp
0x1800197ed  lea     rbx, [rsi+8]
0x1800197f1  cmp     [rsi+10h], ebp
0x1800197f4  jbe     short loc_18001983D
0x1800197f6  mov     rax, [rbx]
0x1800197f9  mov     rdi, [rax+rbp*8]
0x1800197fd  test    rdi, rdi
0x180019800  jz      short loc_18001982B
0x180019802  mov     ecx, [rdi]
0x180019804  sub     ecx, 1
0x180019807  jz      short loc_180019814
0x180019809  cmp     ecx, 2
0x18001980c  jnz     short loc_18001981E
0x18001980e  mov     rcx, [rdi+18h]
0x180019812  jmp     short loc_180019818
0x180019814  mov     rcx, [rdi+10h]; hMem
0x180019818  call    cs:__imp_LocalFree
0x18001981e  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180019823  mov     rcx, rdi; void *
0x180019826  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001982b  mov     rax, [rbx]
0x18001982e  mov     qword ptr [rax+rbp*8], 0
0x180019836  inc     ebp
0x180019838  cmp     ebp, [rsi+10h]
0x18001983b  jb      short loc_1800197F6
0x18001983d  mov     rcx, [rbx]; hMem
0x180019840  call    cs:__imp_LocalFree
0x180019846  mov     rcx, [rsi+18h]; hMem
0x18001984a  call    cs:__imp_LocalFree
0x180019850  mov     rcx, r14; lpCriticalSection
0x180019853  call    cs:__imp_LeaveCriticalSection
0x180019859  mov     rcx, r14
0x18001985c  add     rsp, 28h
0x180019860  pop     r15
0x180019862  pop     r14
0x180019864  pop     rdi
0x180019865  pop     rsi
0x180019866  pop     rbp
0x180019867  pop     rbx
0x180019868  jmp     cs:__imp_DeleteCriticalSection
```
