# Mso::Logging::GetProcessLogString(void)

- ea: `0x18012be04`
- end: `0x18012bf43`
- name: `?GetProcessLogString@Logging@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180142740`

## callees

- `0x180009748`
- `0x18000c5f8`
- `0x18003a770`
- `0x18003a9ac`
- `0x18003e690`
- `0x1800543a4`
- `0x1800543dc`
- `0x18006829c`
- `0x18012be04`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18012be98`
- `KERNEL32!GetCurrentProcessId` at `0x18012becb`
- `KERNEL32!GetCurrentProcessId` at `0x18012be98`
- `KERNEL32!GetCurrentProcessId` at `0x18012becb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Mso::Logging::GetProcessLogString(__int64 a1)
{
  char v2; // bl
  DWORD v4; // [rsp+20h] [rbp-C8h]
  DWORD CurrentProcessId; // [rsp+28h] [rbp-C0h]
  _QWORD v6[4]; // [rsp+30h] [rbp-B8h] BYREF
  wchar_t Buffer[64]; // [rsp+50h] [rbp-98h] BYREF

  v6[0] = a1;
  v2 = 0;
  Mso::TLocker<Mso::Lockable<Mso::SRWLock::SharedLockBase,Mso::MultiThreaded>,Mso::MultiThreaded>::TLocker<Mso::Lockable<Mso::SRWLock::SharedLockBase,Mso::MultiThreaded>,Mso::MultiThreaded>(
    v6,
    &off_180214E48);
  if ( qword_180214E60 && (byte_18021D8D0 || !(_BYTE)qword_18021A2B0) )
  {
    std::wstring::wstring(a1, &qword_180214E50);
    Mso::TLocker<Mso::Lockable<Mso::SRWLock::SharedLockBase,Mso::MultiThreaded>,Mso::MultiThreaded>::~TLocker<Mso::Lockable<Mso::SRWLock::SharedLockBase,Mso::MultiThreaded>,Mso::MultiThreaded>(v6);
  }
  else
  {
    Mso::TLocker<Mso::Lockable<Mso::SRWLock::SharedLockBase,Mso::MultiThreaded>,Mso::MultiThreaded>::~TLocker<Mso::Lockable<Mso::SRWLock::SharedLockBase,Mso::MultiThreaded>,Mso::MultiThreaded>(v6);
    Mso::TLocker<Mso::Lockable<Mso::SRWLock::ExclusiveLockBase,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::TLocker<Mso::Lockable<Mso::SRWLock::ExclusiveLockBase,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(
      v6,
      off_180214E40);
    if ( (_BYTE)qword_18021A2B0 )
    {
      CurrentProcessId = GetCurrentProcessId();
      snwprintf_s(Buffer, 0x40u, 0xFFFFFFFFFFFFFFFFuLL, L"%S (%#x)", &qword_18021A2B0, CurrentProcessId);
      v2 = 1;
    }
    else
    {
      v4 = GetCurrentProcessId();
      snwprintf_s(Buffer, 0x40u, 0xFFFFFFFFFFFFFFFFuLL, L"(%#x)", v4);
    }
    byte_18021D8D0 = v2;
    std::wstring::assign(&qword_180214E50, Buffer);
    std::wstring::wstring(a1, &qword_180214E50);
    Mso::TLocker<Mso::Lockable<Mso::SRWLock::ExclusiveLockBase,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::~TLocker<Mso::Lockable<Mso::SRWLock::ExclusiveLockBase,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(v6);
  }
  return a1;
}

```

## disassembly

```asm
0x18012be04  mov     [rsp+arg_8], rbx
0x18012be09  push    rdi
0x18012be0a  sub     rsp, 0E0h
0x18012be11  mov     rax, cs:__security_cookie
0x18012be18  xor     rax, rsp
0x18012be1b  mov     [rsp+0E8h+var_18], rax
0x18012be23  mov     rdi, rcx
0x18012be26  mov     [rsp+0E8h+var_B8], rcx
0x18012be2b  xor     ebx, ebx
0x18012be2d  lea     rdx, off_180214E48
0x18012be34  lea     rcx, [rsp+0E8h+var_B8]
0x18012be39  call    ??0?$TLocker@V?$Lockable@VSharedLockBase@SRWLock@Mso@@VMultiThreaded@3@@Mso@@VMultiThreaded@2@@Mso@@QEAA@AEAV?$Lockable@VSharedLockBase@SRWLock@Mso@@VMultiThreaded@3@@1@@Z; Mso::TLocker<Mso::Lockable<Mso::SRWLock::SharedLockBase,Mso::MultiThreaded>,Mso::MultiThreaded>::TLocker<Mso::Lockable<Mso::SRWLock::SharedLockBase,Mso::MultiThreaded>,Mso::MultiThreaded>(Mso::Lockable<Mso::SRWLock::SharedLockBase,Mso::MultiThreaded> &)
0x18012be3e  cmp     cs:qword_180214E60, rbx
0x18012be45  jz      short loc_18012BE75
0x18012be47  cmp     cs:byte_18021D8D0, bl
0x18012be4d  jnz     short loc_18012BE57
0x18012be4f  cmp     byte ptr cs:qword_18021A2B0, bl
0x18012be55  jnz     short loc_18012BE75
0x18012be57  lea     rdx, qword_180214E50
0x18012be5e  mov     rcx, rdi
0x18012be61  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18012be66  lea     rcx, [rsp+0E8h+var_B8]
0x18012be6b  call    ??1?$TLocker@V?$Lockable@VSharedLockBase@SRWLock@Mso@@VMultiThreaded@3@@Mso@@VMultiThreaded@2@@Mso@@QEAA@XZ; Mso::TLocker<Mso::Lockable<Mso::SRWLock::SharedLockBase,Mso::MultiThreaded>,Mso::MultiThreaded>::~TLocker<Mso::Lockable<Mso::SRWLock::SharedLockBase,Mso::MultiThreaded>,Mso::MultiThreaded>(void)
0x18012be70  jmp     loc_18012BF1F
0x18012be75  lea     rcx, [rsp+0E8h+var_B8]
0x18012be7a  call    ??1?$TLocker@V?$Lockable@VSharedLockBase@SRWLock@Mso@@VMultiThreaded@3@@Mso@@VMultiThreaded@2@@Mso@@QEAA@XZ; Mso::TLocker<Mso::Lockable<Mso::SRWLock::SharedLockBase,Mso::MultiThreaded>,Mso::MultiThreaded>::~TLocker<Mso::Lockable<Mso::SRWLock::SharedLockBase,Mso::MultiThreaded>,Mso::MultiThreaded>(void)
0x18012be7f  lea     rdx, off_180214E40
0x18012be86  lea     rcx, [rsp+0E8h+var_B8]
0x18012be8b  call    ??0?$TLocker@V?$Lockable@VExclusiveLockBase@SRWLock@Mso@@VZeroOrOneThreaded@3@@Mso@@VZeroOrOneThreaded@2@@Mso@@QEAA@AEAV?$Lockable@VExclusiveLockBase@SRWLock@Mso@@VZeroOrOneThreaded@3@@1@@Z; Mso::TLocker<Mso::Lockable<Mso::SRWLock::ExclusiveLockBase,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::TLocker<Mso::Lockable<Mso::SRWLock::ExclusiveLockBase,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(Mso::Lockable<Mso::SRWLock::ExclusiveLockBase,Mso::ZeroOrOneThreaded> &)
0x18012be90  cmp     byte ptr cs:qword_18021A2B0, bl
0x18012be96  jz      short loc_18012BECB
0x18012be98  call    cs:__imp_GetCurrentProcessId
0x18012be9e  mov     [rsp+0E8h+var_C0], eax
0x18012bea2  lea     rax, qword_18021A2B0
0x18012bea9  mov     [rsp+0E8h+var_C8], rax
0x18012beae  lea     r9, aSX; "%S (%#x)"
0x18012beb5  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18012beb9  lea     edx, [r8+41h]; BufferCount
0x18012bebd  lea     rcx, [rsp+0E8h+Buffer]; Buffer
0x18012bec2  call    _snwprintf_s
0x18012bec7  mov     bl, 1
0x18012bec9  jmp     short loc_18012BEEE
0x18012becb  call    cs:__imp_GetCurrentProcessId
0x18012bed1  mov     dword ptr [rsp+0E8h+var_C8], eax
0x18012bed5  lea     r9, asc_1801AFAC0; "(%#x)"
0x18012bedc  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18012bee0  lea     edx, [r8+41h]; BufferCount
0x18012bee4  lea     rcx, [rsp+0E8h+Buffer]; Buffer
0x18012bee9  call    _snwprintf_s
0x18012beee  mov     cs:byte_18021D8D0, bl
0x18012bef4  lea     rdx, [rsp+0E8h+Buffer]; Src
0x18012bef9  lea     rcx, qword_180214E50; void *
0x18012bf00  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18012bf05  lea     rdx, qword_180214E50
0x18012bf0c  mov     rcx, rdi
0x18012bf0f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18012bf14  nop
0x18012bf15  lea     rcx, [rsp+0E8h+var_B8]
0x18012bf1a  call    ??1?$TLocker@V?$Lockable@VExclusiveLockBase@SRWLock@Mso@@VZeroOrOneThreaded@3@@Mso@@VZeroOrOneThreaded@2@@Mso@@QEAA@XZ; Mso::TLocker<Mso::Lockable<Mso::SRWLock::ExclusiveLockBase,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::~TLocker<Mso::Lockable<Mso::SRWLock::ExclusiveLockBase,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(void)
0x18012bf1f  mov     rax, rdi
0x18012bf22  mov     rcx, [rsp+0E8h+var_18]
0x18012bf2a  xor     rcx, rsp; StackCookie
0x18012bf2d  call    __security_check_cookie
0x18012bf32  mov     rbx, [rsp+0E8h+arg_8]
0x18012bf3a  add     rsp, 0E0h
0x18012bf41  pop     rdi
0x18012bf42  retn
```
