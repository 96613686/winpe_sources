# PersistObject::~PersistObject(void)

- ea: `0x180026744`
- end: `0x1800267eb`
- name: `??1PersistObject@@UEAA@XZ`
- size: `167`
- prototype: `void __fastcall(PersistObject *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180026920`

## callees

- `0x180026744`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800267a1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800267a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026765`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026765`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800267cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800267cf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800267e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026798`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800267bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800267c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026798`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800267bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800267c6`

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
        operator delete(v5);
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
0x180026744  push    rbx
0x180026746  push    rbp
0x180026747  push    rsi
0x180026748  push    rdi
0x180026749  push    r14
0x18002674b  push    r15
0x18002674d  sub     rsp, 28h
0x180026751  lea     rax, ??_7PersistObject@@6B@; const PersistObject::`vftable'
0x180026758  mov     rsi, rcx
0x18002675b  lea     r14, [rcx+20h]
0x18002675f  mov     [rcx], rax
0x180026762  mov     rcx, r14; lpCriticalSection
0x180026765  call    cs:__imp_EnterCriticalSection
0x18002676b  xor     ebp, ebp
0x18002676d  lea     rbx, [rsi+8]
0x180026771  cmp     [rsi+10h], ebp
0x180026774  jbe     short loc_1800267B9
0x180026776  mov     rax, [rbx]
0x180026779  mov     rdi, [rax+rbp*8]
0x18002677d  test    rdi, rdi
0x180026780  jz      short loc_1800267A7
0x180026782  mov     ecx, [rdi]
0x180026784  sub     ecx, 1
0x180026787  jz      short loc_180026794
0x180026789  cmp     ecx, 2
0x18002678c  jnz     short loc_18002679E
0x18002678e  mov     rcx, [rdi+18h]
0x180026792  jmp     short loc_180026798
0x180026794  mov     rcx, [rdi+10h]; hMem
0x180026798  call    cs:__imp_LocalFree
0x18002679e  mov     rcx, rdi
0x1800267a1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800267a7  mov     rax, [rbx]
0x1800267aa  mov     qword ptr [rax+rbp*8], 0
0x1800267b2  inc     ebp
0x1800267b4  cmp     ebp, [rsi+10h]
0x1800267b7  jb      short loc_180026776
0x1800267b9  mov     rcx, [rbx]; hMem
0x1800267bc  call    cs:__imp_LocalFree
0x1800267c2  mov     rcx, [rsi+18h]; hMem
0x1800267c6  call    cs:__imp_LocalFree
0x1800267cc  mov     rcx, r14; lpCriticalSection
0x1800267cf  call    cs:__imp_LeaveCriticalSection
0x1800267d5  mov     rcx, r14
0x1800267d8  add     rsp, 28h
0x1800267dc  pop     r15
0x1800267de  pop     r14
0x1800267e0  pop     rdi
0x1800267e1  pop     rsi
0x1800267e2  pop     rbp
0x1800267e3  pop     rbx
0x1800267e4  jmp     cs:__imp_DeleteCriticalSection
```
