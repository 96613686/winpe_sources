# sqlencrypt::SymmetricKeyCache::SymmetricKeyCache(void)

- ea: `0x100480e0c`
- end: `0x100480eb6`
- name: `??0SymmetricKeyCache@sqlencrypt@@QEAA@XZ`
- size: `170`
- prototype: `__int64 __fastcall(sqlencrypt::SymmetricKeyCache *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1004815fc`

## callees

- `0x100480e0c`
- `0x100481844`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x100480e6f`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x100480e6f`
- `KERNEL32!CreateEventW` at `0x100480e87`
- `KERNEL32!CreateEventW` at `0x100480e87`
- `KERNEL32!GetLastError` at `0x100480e99`
- `KERNEL32!GetLastError` at `0x100480e99`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall sqlencrypt::SymmetricKeyCache::SymmetricKeyCache(
        struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE EventW; // rax

  this->DebugInfo = 0;
  *(_QWORD *)&this->LockCount = 0;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)std::_Tree_comp_alloc<std::_Tmap_traits<std::basic_string<unsigned char>,std::shared_ptr<sqlencrypt::SecureCek>,std::less<std::basic_string<unsigned char>>,std::allocator<std::pair<std::basic_string<unsigned char> const,std::shared_ptr<sqlencrypt::SecureCek>>>,0>>::_Buyheadnode();
  this->OwningThread = 0;
  this->LockSemaphore = 0;
  this->SpinCount = 0;
  *(_QWORD *)&this[1].LockCount = 0;
  LOWORD(this[1].OwningThread) = 0;
  LODWORD(this[1].SpinCount) = -1;
  this[1].LockSemaphore = &CMutex::`vftable';
  LOBYTE(this[3].DebugInfo) = 0;
  *(_QWORD *)&this[3].LockCount = 0;
  this[3].OwningThread = 0;
  LOBYTE(this[3].DebugInfo) = InitializeCriticalSectionAndSpinCount(this + 2, 0);
  EventW = CreateEventW(0, 0, 0, 0);
  this[3].OwningThread = EventW;
  if ( EventW )
    *(_QWORD *)&this[3].LockCount = (char *)this + 64;
  else
    GetLastError();
  return this;
}

```

## disassembly

```asm
0x100480e0c  mov     [rsp+arg_8], rbx
0x100480e11  push    rdi
0x100480e12  sub     rsp, 20h
0x100480e16  and     qword ptr [rcx], 0
0x100480e1a  mov     rbx, rcx
0x100480e1d  and     qword ptr [rcx+8], 0
0x100480e22  call    ?_Buyheadnode@?$_Tree_comp_alloc@V?$_Tmap_traits@V?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@U?$less@V?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@@std@@@2@$0A@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@@std@@PEAX@2@XZ; std::_Tree_comp_alloc<std::_Tmap_traits<std::basic_string<uchar>,std::shared_ptr<sqlencrypt::SecureCek>,std::less<std::basic_string<uchar>>,std::allocator<std::pair<std::basic_string<uchar> const,std::shared_ptr<sqlencrypt::SecureCek>>>,0>>::_Buyheadnode(void)
0x100480e27  mov     [rbx], rax
0x100480e2a  lea     rdi, [rbx+40h]
0x100480e2e  and     qword ptr [rbx+10h], 0
0x100480e33  lea     rax, ??_7CMutex@@6B@; const CMutex::`vftable'
0x100480e3a  and     qword ptr [rbx+18h], 0
0x100480e3f  lea     rcx, [rdi+10h]; lpCriticalSection
0x100480e43  and     qword ptr [rbx+20h], 0
0x100480e48  xor     edx, edx; dwSpinCount
0x100480e4a  and     qword ptr [rbx+30h], 0
0x100480e4f  and     word ptr [rbx+38h], 0
0x100480e54  or      dword ptr [rdi+8], 0FFFFFFFFh
0x100480e58  mov     [rdi], rax
0x100480e5b  mov     byte ptr [rdi+38h], 0
0x100480e5f  and     qword ptr [rbx+80h], 0
0x100480e67  and     qword ptr [rbx+88h], 0
0x100480e6f  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x100480e75  test    eax, eax
0x100480e77  setnz   al
0x100480e7a  xor     r9d, r9d; lpName
0x100480e7d  xor     r8d, r8d; bInitialState
0x100480e80  mov     [rdi+38h], al
0x100480e83  xor     edx, edx; bManualReset
0x100480e85  xor     ecx, ecx; lpEventAttributes
0x100480e87  call    cs:__imp_CreateEventW
0x100480e8d  mov     [rbx+88h], rax
0x100480e94  test    rax, rax
0x100480e97  jnz     short loc_100480EA1
0x100480e99  call    cs:__imp_GetLastError
0x100480e9f  jmp     short loc_100480EA8
0x100480ea1  mov     [rbx+80h], rdi
0x100480ea8  mov     rax, rbx
0x100480eab  mov     rbx, [rsp+28h+arg_8]
0x100480eb0  add     rsp, 20h
0x100480eb4  pop     rdi
0x100480eb5  retn
```
