# HashTableBase::remove(void const *)

- ea: `0x18002db60`
- end: `0x18002dbe7`
- name: `?remove@HashTableBase@@QEAAPEAVHashTableEntry@@PEBX@Z`
- size: `135`
- prototype: `struct HashTableEntry *__fastcall(HashTableBase *__hidden this, const void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002d890`
- `0x18002ddbc`

## callees

- `0x18002db60`
- `0x180030010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002db84`
- `KERNEL32!EnterCriticalSection` at `0x18002db84`
- `KERNEL32!LeaveCriticalSection` at `0x18002dbd3`
- `KERNEL32!LeaveCriticalSection` at `0x18002dbd3`

## pseudocode

```c
struct HashTableEntry *__fastcall HashTableBase::remove(HashTableBase *this, const void *a2)
{
  __int64 v4; // rsi
  unsigned int v5; // ebx
  __int64 v6; // r8
  _QWORD *i; // rbx
  char v8; // al
  __int64 v9; // rcx

  v4 = 0;
  v5 = (*(__int64 (__fastcall **)(const void *))this)(a2);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v6 = *((_QWORD *)this + 1);
  if ( v6 )
  {
    for ( i = (_QWORD *)(v6 + 8LL * (v5 % *((_DWORD *)this + 4))); *i; i = (_QWORD *)(v9 + 8) )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, const void *))(*(_QWORD *)*i + 24LL))(*i, a2);
      v9 = *i;
      if ( v8 )
      {
        v4 = *i;
        *i = *(_QWORD *)(v9 + 8);
        --*((_DWORD *)this + 5);
        break;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return (struct HashTableEntry *)v4;
}

```

## disassembly

```asm
0x18002db60  push    rbx
0x18002db62  push    rbp
0x18002db63  push    rsi
0x18002db64  push    rdi
0x18002db65  push    r14
0x18002db67  sub     rsp, 20h
0x18002db6b  mov     r14, rdx
0x18002db6e  mov     rdi, rcx
0x18002db71  xor     esi, esi
0x18002db73  mov     rcx, rdx
0x18002db76  mov     rax, [rdi]
0x18002db79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db7e  mov     ebx, eax
0x18002db80  lea     rcx, [rdi+18h]; lpCriticalSection
0x18002db84  call    cs:__imp_EnterCriticalSection
0x18002db8a  mov     r8, [rdi+8]
0x18002db8e  test    r8, r8
0x18002db91  jz      short loc_18002DBCF
0x18002db93  xor     edx, edx
0x18002db95  mov     eax, ebx
0x18002db97  div     dword ptr [rdi+10h]
0x18002db9a  lea     rbx, [r8+rdx*8]
0x18002db9e  mov     rcx, [rbx]
0x18002dba1  test    rcx, rcx
0x18002dba4  jz      short loc_18002DBCF
0x18002dba6  mov     rax, [rcx]
0x18002dba9  mov     rdx, r14
0x18002dbac  mov     rax, [rax+18h]
0x18002dbb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dbb5  mov     rcx, [rbx]
0x18002dbb8  test    al, al
0x18002dbba  jnz     short loc_18002DBC2
0x18002dbbc  lea     rbx, [rcx+8]
0x18002dbc0  jmp     short loc_18002DB9E
0x18002dbc2  mov     rsi, rcx
0x18002dbc5  mov     rdx, [rcx+8]
0x18002dbc9  mov     [rbx], rdx
0x18002dbcc  dec     dword ptr [rdi+14h]
0x18002dbcf  lea     rcx, [rdi+18h]; lpCriticalSection
0x18002dbd3  call    cs:__imp_LeaveCriticalSection
0x18002dbd9  mov     rax, rsi
0x18002dbdc  add     rsp, 20h
0x18002dbe0  pop     r14
0x18002dbe2  pop     rdi
0x18002dbe3  pop     rsi
0x18002dbe4  pop     rbp
0x18002dbe5  pop     rbx
0x18002dbe6  retn
```
