# CSplash::~CSplash(void)

- ea: `0x14003ef40`
- end: `0x14003efed`
- name: `??1CSplash@@UEAA@XZ`
- size: `173`
- prototype: `void __fastcall(CSplash *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140036e20`
- `0x14003ef00`

## callees

- `0x140002190`
- `0x140003f60`
- `0x1400086e8`
- `0x14002ec14`
- `0x14003ef40`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14003efb2`
- `KERNEL32!CloseHandle` at `0x14003efcc`
- `KERNEL32!CloseHandle` at `0x14003efb2`
- `KERNEL32!CloseHandle` at `0x14003efcc`
- `KERNEL32!DeleteCriticalSection` at `0x14003ef8b`
- `KERNEL32!DeleteCriticalSection` at `0x14003ef8b`

## pseudocode

```c
void __fastcall CSplash::~CSplash(CSplash *this, __int64 a2, __int64 a3, const unsigned __int16 *a4)
{
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  void *v6; // rcx
  void *v7; // rcx

  *(_QWORD *)this = &CSplash::`vftable';
  v5 = lpCriticalSection;
  if ( lpCriticalSection )
  {
    lpCriticalSection = 0;
    DeleteCriticalSection(v5);
    operator delete(v5, (const struct std::nothrow_t *)0x28);
  }
  else
  {
    ActivityLog::LogEntry(
      (ActivityLog *)1,
      (int)L"Microsoft Visual Studio Appid Stub",
      L"TermSync should be called after InitSync",
      a4);
  }
  CSplash::DestroySplashScreen(this);
  v6 = (void *)*((_QWORD *)this + 17);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 17) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 16);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 16) = 0;
  }
  CSplash::DisplayParams::~DisplayParams((CSplash *)((char *)this + 8));
}

```

## disassembly

```asm
0x14003ef40  mov     [rsp+arg_8], rbx
0x14003ef45  push    rdi
0x14003ef46  sub     rsp, 20h
0x14003ef4a  mov     rbx, rcx
0x14003ef4d  lea     rax, ??_7CSplash@@6B@; const CSplash::`vftable'
0x14003ef54  mov     [rcx], rax
0x14003ef57  mov     rdi, cs:lpCriticalSection
0x14003ef5e  test    rdi, rdi
0x14003ef61  jnz     short loc_14003EF7B
0x14003ef63  lea     r8, aTermsyncShould; "TermSync should be called after InitSyn"...
0x14003ef6a  lea     rdx, aMicrosoftVisua_1; "Microsoft Visual Studio Appid Stub"
0x14003ef71  lea     ecx, [rdi+1]; this
0x14003ef74  call    ?LogEntry@ActivityLog@@YAJHPEBG0@Z; ActivityLog::LogEntry(int,ushort const *,ushort const *)
0x14003ef79  jmp     short loc_14003EF9E
0x14003ef7b  and     cs:lpCriticalSection, 0
0x14003ef83  test    rdi, rdi
0x14003ef86  jz      short loc_14003EF9E
0x14003ef88  mov     rcx, rdi; lpCriticalSection
0x14003ef8b  call    cs:__imp_DeleteCriticalSection
0x14003ef91  mov     edx, 28h ; '('; struct std::nothrow_t *
0x14003ef96  mov     rcx, rdi; void *
0x14003ef99  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003ef9e  mov     rcx, rbx; this
0x14003efa1  call    ?DestroySplashScreen@CSplash@@QEAAXXZ; CSplash::DestroySplashScreen(void)
0x14003efa6  mov     rcx, [rbx+88h]; hObject
0x14003efad  test    rcx, rcx
0x14003efb0  jz      short loc_14003EFC0
0x14003efb2  call    cs:__imp_CloseHandle
0x14003efb8  and     qword ptr [rbx+88h], 0
0x14003efc0  mov     rcx, [rbx+80h]; hObject
0x14003efc7  test    rcx, rcx
0x14003efca  jz      short loc_14003EFDA
0x14003efcc  call    cs:__imp_CloseHandle
0x14003efd2  and     qword ptr [rbx+80h], 0
0x14003efda  lea     rcx, [rbx+8]; this
0x14003efde  mov     rbx, [rsp+28h+arg_8]
0x14003efe3  add     rsp, 20h
0x14003efe7  pop     rdi
0x14003efe8  jmp     ??1DisplayParams@CSplash@@QEAA@XZ; CSplash::DisplayParams::~DisplayParams(void)
```
