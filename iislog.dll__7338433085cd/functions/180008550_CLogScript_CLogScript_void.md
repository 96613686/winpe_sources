# CLogScript::~CLogScript(void)

- ea: `0x180008550`
- end: `0x18000863c`
- name: `??1CLogScript@@MEAA@XZ`
- size: `236`
- prototype: `void __fastcall(CLogScript *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003984`
- `0x1800075f4`
- `0x180008650`
- `0x18000bf30`

## callees

- `0x180001048`
- `0x180008550`
- `0x180010010`

## import_xrefs

- `msvcrt!fclose` at `0x18000857d`
- `msvcrt!fclose` at `0x18000857d`
- `IisRTL!??1STR@@QEAA@XZ` at `0x1800085db`
- `IisRTL!??1STR@@QEAA@XZ` at `0x1800085e5`
- `IisRTL!??1STR@@QEAA@XZ` at `0x1800085db`
- `IisRTL!??1STR@@QEAA@XZ` at `0x1800085e5`
- `KERNEL32!EnterCriticalSection` at `0x18000856e`
- `KERNEL32!EnterCriticalSection` at `0x1800085f2`
- `KERNEL32!EnterCriticalSection` at `0x18000856e`
- `KERNEL32!EnterCriticalSection` at `0x1800085f2`
- `KERNEL32!LeaveCriticalSection` at `0x1800085c5`
- `KERNEL32!LeaveCriticalSection` at `0x1800085c5`
- `KERNEL32!LeaveCriticalSection` at `0x180008635`
- `KERNEL32!DeleteCriticalSection` at `0x1800085ce`
- `KERNEL32!DeleteCriticalSection` at `0x1800085ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1800085b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800085b1`

## pseudocode

```c
void __fastcall CLogScript::~CLogScript(CLogScript *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  FILE *v3; // rcx
  void *v4; // rcx
  OLECHAR *v5; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  *(_QWORD *)this = &CLogScript::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v3 = (FILE *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    fclose(v3);
    *((_QWORD *)this + 6) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 143);
  if ( v4 && *((_DWORD *)this + 288) )
    operator delete(v4);
  v5 = (OLECHAR *)*((_QWORD *)this + 145);
  if ( v5 )
  {
    SysFreeString(v5);
    *((_QWORD *)this + 145) = 0;
  }
  LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
  STR::~STR((CLogScript *)((char *)this + 1088));
  STR::~STR((CLogScript *)((char *)this + 56));
  EnterCriticalSection(&CriticalSection);
  if ( !--dword_180017138 )
  {
    if ( qword_180017130 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180017130 + 16LL))(qword_180017130);
    qword_180017130 = 0;
  }
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180008550  mov     [rsp+arg_8], rbx
0x180008555  push    rdi
0x180008556  sub     rsp, 20h
0x18000855a  lea     rax, ??_7CLogScript@@6B@; const CLogScript::`vftable'
0x180008561  mov     rbx, rcx
0x180008564  lea     rdi, [rcx+8]
0x180008568  mov     [rcx], rax
0x18000856b  mov     rcx, rdi; lpCriticalSection
0x18000856e  call    cs:__imp_EnterCriticalSection
0x180008574  mov     rcx, [rbx+30h]; Stream
0x180008578  test    rcx, rcx
0x18000857b  jz      short loc_18000858B
0x18000857d  call    cs:__imp_fclose
0x180008583  mov     qword ptr [rbx+30h], 0
0x18000858b  mov     rcx, [rbx+478h]; Block
0x180008592  test    rcx, rcx
0x180008595  jz      short loc_1800085A5
0x180008597  cmp     dword ptr [rbx+480h], 0
0x18000859e  jz      short loc_1800085A5
0x1800085a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800085a5  mov     rcx, [rbx+488h]; bstrString
0x1800085ac  test    rcx, rcx
0x1800085af  jz      short loc_1800085C2
0x1800085b1  call    cs:__imp_SysFreeString
0x1800085b7  mov     qword ptr [rbx+488h], 0
0x1800085c2  mov     rcx, rdi; lpCriticalSection
0x1800085c5  call    cs:__imp_LeaveCriticalSection
0x1800085cb  mov     rcx, rdi; lpCriticalSection
0x1800085ce  call    cs:__imp_DeleteCriticalSection
0x1800085d4  lea     rcx, [rbx+440h]
0x1800085db  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x1800085e1  lea     rcx, [rbx+38h]
0x1800085e5  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x1800085eb  lea     rcx, CriticalSection; lpCriticalSection
0x1800085f2  call    cs:__imp_EnterCriticalSection
0x1800085f8  sub     cs:dword_180017138, 1
0x1800085ff  jnz     short loc_180008624
0x180008601  mov     rcx, cs:qword_180017130
0x180008608  test    rcx, rcx
0x18000860b  jz      short loc_180008619
0x18000860d  mov     rax, [rcx]
0x180008610  mov     rax, [rax+10h]
0x180008614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008619  mov     cs:qword_180017130, 0
0x180008624  lea     rcx, CriticalSection
0x18000862b  mov     rbx, [rsp+28h+arg_8]
0x180008630  add     rsp, 20h
0x180008634  pop     rdi
0x180008635  jmp     cs:__imp_LeaveCriticalSection
```
