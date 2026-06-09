# sqlencrypt::SymmetricKeyCache::~SymmetricKeyCache(void)

- ea: `0x100480f80`
- end: `0x100481098`
- name: `??1SymmetricKeyCache@sqlencrypt@@QEAA@XZ`
- size: `280`
- prototype: `void __fastcall(sqlencrypt::SymmetricKeyCache *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1004ebd04`

## callees

- `0x10040128c`
- `0x100480f80`
- `0x100481bb0`
- `0x100481e28`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x100481059`
- `KERNEL32!DeleteCriticalSection` at `0x100481059`
- `KERNEL32!WaitForSingleObject` at `0x100480fe7`
- `KERNEL32!WaitForSingleObject` at `0x100480fe7`
- `KERNEL32!SetEvent` at `0x100480fc0`
- `KERNEL32!SetEvent` at `0x100480fc0`
- `KERNEL32!GetLastError` at `0x100480fca`
- `KERNEL32!GetLastError` at `0x100480ff2`
- `KERNEL32!GetLastError` at `0x10048102e`
- `KERNEL32!GetLastError` at `0x100480fca`
- `KERNEL32!GetLastError` at `0x100480ff2`
- `KERNEL32!GetLastError` at `0x10048102e`
- `KERNEL32!CloseHandle` at `0x100481014`
- `KERNEL32!CloseHandle` at `0x100481014`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall sqlencrypt::SymmetricKeyCache::~SymmetricKeyCache(sqlencrypt::SymmetricKeyCache *this)
{
  char *v2; // rdi
  void *v3; // rcx
  BOOL v4; // eax
  sqlencrypt::SymmetricKeyCache *v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = this;
  v2 = (char *)this + 64;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 8) + 8LL))((char *)this + 64);
  if ( *((_BYTE *)this + 57) )
  {
    *((_BYTE *)this + 56) = 1;
    if ( !SetEvent(*((HANDLE *)this + 17)) )
      GetLastError();
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 24LL))(v2);
    if ( WaitForSingleObject(*((HANDLE *)this + 6), 0xFFFFFFFF) == -1 )
      GetLastError();
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  }
  v3 = (void *)*((_QWORD *)this + 17);
  if ( v3 )
  {
    v4 = CloseHandle(v3);
    *((_QWORD *)this + 17) = 0;
    *((_QWORD *)this + 16) = 0;
    if ( !v4 )
      GetLastError();
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 24LL))(v2);
  *(_QWORD *)v2 = &CMutex::`vftable';
  if ( v2[56] )
    DeleteCriticalSection((LPCRITICAL_SECTION)(v2 + 16));
  *(_QWORD *)v2 = &ICriticalSection::`vftable';
  std::vector<sqlencrypt::SymmetricKeyCache::KeyExpiry>::_Tidy((char *)this + 16);
  std::_Tree<std::_Tmap_traits<std::basic_string<unsigned char>,std::shared_ptr<sqlencrypt::SecureCek>,std::less<std::basic_string<unsigned char>>,std::allocator<std::pair<std::basic_string<unsigned char> const,std::shared_ptr<sqlencrypt::SecureCek>>>,0>>::erase(
    this,
    &v5,
    **(_QWORD **)this);
  operator delete(*(void **)this);
}

```

## disassembly

```asm
0x100480f80  mov     [rsp+arg_0], rcx
0x100480f85  push    rdi
0x100480f86  sub     rsp, 30h
0x100480f8a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x100480f93  mov     [rsp+38h+arg_8], rbx
0x100480f98  mov     rbx, rcx
0x100480f9b  lea     rdi, [rcx+40h]
0x100480f9f  mov     rax, [rdi]
0x100480fa2  mov     rcx, rdi
0x100480fa5  mov     rax, [rax+8]
0x100480fa9  call    cs:__guard_dispatch_icall_fptr
0x100480faf  cmp     byte ptr [rbx+39h], 0
0x100480fb3  jz      short loc_100481008
0x100480fb5  mov     byte ptr [rbx+38h], 1
0x100480fb9  mov     rcx, [rbx+88h]; hEvent
0x100480fc0  call    cs:__imp_SetEvent
0x100480fc6  test    eax, eax
0x100480fc8  jnz     short loc_100480FD0
0x100480fca  call    cs:__imp_GetLastError
0x100480fd0  mov     rax, [rdi]
0x100480fd3  mov     rcx, rdi
0x100480fd6  mov     rax, [rax+18h]
0x100480fda  call    cs:__guard_dispatch_icall_fptr
0x100480fe0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x100480fe3  mov     rcx, [rbx+30h]; hHandle
0x100480fe7  call    cs:__imp_WaitForSingleObject
0x100480fed  cmp     eax, 0FFFFFFFFh
0x100480ff0  jnz     short loc_100480FF8
0x100480ff2  call    cs:__imp_GetLastError
0x100480ff8  mov     rax, [rdi]
0x100480ffb  mov     rcx, rdi
0x100480ffe  mov     rax, [rax+8]
0x100481002  call    cs:__guard_dispatch_icall_fptr
0x100481008  mov     rcx, [rbx+88h]; hObject
0x10048100f  test    rcx, rcx
0x100481012  jz      short loc_100481034
0x100481014  call    cs:__imp_CloseHandle
0x10048101a  and     qword ptr [rbx+88h], 0
0x100481022  and     qword ptr [rbx+80h], 0
0x10048102a  test    eax, eax
0x10048102c  jnz     short loc_100481034
0x10048102e  call    cs:__imp_GetLastError
0x100481034  mov     rax, [rdi]
0x100481037  mov     rcx, rdi
0x10048103a  mov     rax, [rax+18h]
0x10048103e  call    cs:__guard_dispatch_icall_fptr
0x100481044  nop
0x100481045  lea     rax, ??_7CMutex@@6B@; const CMutex::`vftable'
0x10048104c  mov     [rdi], rax
0x10048104f  cmp     byte ptr [rdi+38h], 0
0x100481053  jz      short loc_10048105F
0x100481055  lea     rcx, [rdi+10h]; lpCriticalSection
0x100481059  call    cs:__imp_DeleteCriticalSection
0x10048105f  lea     rax, ??_7ICriticalSection@@6B@; const ICriticalSection::`vftable'
0x100481066  mov     [rdi], rax
0x100481069  lea     rcx, [rbx+10h]
0x10048106d  call    ?_Tidy@?$vector@UKeyExpiry@SymmetricKeyCache@sqlencrypt@@V?$allocator@UKeyExpiry@SymmetricKeyCache@sqlencrypt@@@std@@@std@@AEAAXXZ; std::vector<sqlencrypt::SymmetricKeyCache::KeyExpiry>::_Tidy(void)
0x100481072  nop
0x100481073  mov     r9, [rbx]
0x100481076  mov     r8, [r9]
0x100481079  lea     rdx, [rsp+38h+arg_0]
0x10048107e  mov     rcx, rbx
0x100481081  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@U?$less@V?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@@std@@@std@@@std@@@2@0@Z; std::_Tree<std::_Tmap_traits<std::basic_string<uchar>,std::shared_ptr<sqlencrypt::SecureCek>,std::less<std::basic_string<uchar>>,std::allocator<std::pair<std::basic_string<uchar> const,std::shared_ptr<sqlencrypt::SecureCek>>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<uchar> const,std::shared_ptr<sqlencrypt::SecureCek>>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<uchar> const,std::shared_ptr<sqlencrypt::SecureCek>>>>>)
0x100481086  mov     rcx, [rbx]; void *
0x100481089  mov     rbx, [rsp+38h+arg_8]
0x10048108e  add     rsp, 30h
0x100481092  pop     rdi
0x100481093  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
