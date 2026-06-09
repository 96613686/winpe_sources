# EAPSessionTable::remove(ulong)

- ea: `0x180018460`
- end: `0x1800184eb`
- name: `?remove@EAPSessionTable@@QEAAPEAVEAPSession@@K@Z`
- size: `139`
- prototype: `struct EAPSession *__fastcall(EAPSessionTable *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180017330`

## callees

- `0x180017d20`
- `0x180018090`
- `0x1800180f4`
- `0x18001814c`
- `0x180018218`
- `0x180018460`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800184da`
- `KERNEL32!LeaveCriticalSection` at `0x1800184da`

## pseudocode

```c
struct EAPSession *__fastcall EAPSessionTable::remove(struct _RTL_CRITICAL_SECTION *this, unsigned int a2)
{
  __int64 v2; // rbx
  unsigned __int64 SystemTimeAsDWORDLONG; // rax
  _QWORD *i; // r8
  __int64 v6; // rbx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v9; // [rsp+48h] [rbp+10h] BYREF
  char v10; // [rsp+50h] [rbp+18h] BYREF

  v9 = a2;
  v2 = a2;
  Guard<Guardable>::Guard<Guardable>(&lpCriticalSection, this);
  SystemTimeAsDWORDLONG = GetSystemTimeAsDWORDLONG();
  EAPSessionTable::evict((EAPSessionTable *)this, SystemTimeAsDWORDLONG);
  for ( i = (_QWORD *)*((_QWORD *)&this[2].DebugInfo->Type + (v2 & (__int64)this[1].LockSemaphore)); i; i = (_QWORD *)*i )
  {
    if ( *(_DWORD *)i[1] == (_DWORD)v2 )
    {
      v6 = i[1];
      std::list<std::pair<unsigned __int64,EAPSession *>>::erase(&this[1], &v10, i[2]);
      hash_table<unsigned long,identity<unsigned long>,std::pair<EAPSession *,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64,EAPSession *>>>>>,EAPSessionTable::Extractor,std::equal_to<unsigned long>>::erase(
        &this[1].OwningThread,
        &v9);
      goto LABEL_7;
    }
  }
  v6 = 0;
LABEL_7:
  LeaveCriticalSection(lpCriticalSection);
  return (struct EAPSession *)v6;
}

```

## disassembly

```asm
0x180018460  mov     [rsp+arg_8], edx
0x180018464  push    rbx
0x180018465  push    rsi
0x180018466  push    rdi
0x180018467  sub     rsp, 20h
0x18001846b  mov     ebx, edx
0x18001846d  mov     rdi, rcx
0x180018470  mov     rdx, rcx
0x180018473  lea     rcx, [rsp+38h+lpCriticalSection]
0x180018478  call    ??0?$Guard@VGuardable@@@@QEAA@AEBVGuardable@@@Z; Guard<Guardable>::Guard<Guardable>(Guardable const &)
0x18001847d  call    GetSystemTimeAsDWORDLONG
0x180018482  mov     rdx, rax; unsigned __int64
0x180018485  mov     rcx, rdi; this
0x180018488  call    ?evict@EAPSessionTable@@IEAAX_K@Z; EAPSessionTable::evict(unsigned __int64)
0x18001848d  mov     r8, [rdi+40h]
0x180018491  mov     rax, [rdi+50h]
0x180018495  and     r8, rbx
0x180018498  mov     r8, [rax+r8*8]
0x18001849c  test    r8, r8
0x18001849f  jz      short loc_1800184D3
0x1800184a1  mov     rax, [r8+8]
0x1800184a5  cmp     [rax], ebx
0x1800184a7  jz      short loc_1800184AE
0x1800184a9  mov     r8, [r8]
0x1800184ac  jmp     short loc_18001849C
0x1800184ae  mov     r8, [r8+10h]
0x1800184b2  lea     rcx, [rdi+28h]
0x1800184b6  lea     rdx, [rsp+38h+arg_10]
0x1800184bb  mov     rbx, rax
0x1800184be  call    ?erase@?$list@U?$pair@_KPEAVEAPSession@@@std@@V?$allocator@U?$pair@_KPEAVEAPSession@@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@_KPEAVEAPSession@@@std@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@_KPEAVEAPSession@@@std@@@std@@@std@@@2@@Z; std::list<std::pair<unsigned __int64,EAPSession *>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64,EAPSession *>>>>)
0x1800184c3  lea     rdx, [rsp+38h+arg_8]
0x1800184c8  lea     rcx, [rdi+38h]
0x1800184cc  call    ?erase@?$hash_table@KU?$identity@K@@U?$pair@PEAVEAPSession@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@_KPEAVEAPSession@@@std@@@std@@@std@@@std@@@std@@UExtractor@EAPSessionTable@@U?$equal_to@K@3@@@QEAA_KAEBK@Z; hash_table<ulong,identity<ulong>,std::pair<EAPSession *,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64,EAPSession *>>>>>,EAPSessionTable::Extractor,std::equal_to<ulong>>::erase(ulong const &)
0x1800184d1  jmp     short loc_1800184D5
0x1800184d3  xor     ebx, ebx
0x1800184d5  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800184da  call    cs:__imp_LeaveCriticalSection
0x1800184e0  mov     rax, rbx
0x1800184e3  add     rsp, 20h
0x1800184e7  pop     rdi
0x1800184e8  pop     rsi
0x1800184e9  pop     rbx
0x1800184ea  retn
```
