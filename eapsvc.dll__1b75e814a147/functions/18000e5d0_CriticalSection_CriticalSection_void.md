# CriticalSection::~CriticalSection(void)

- ea: `0x18000e5d0`
- end: `0x18000e630`
- name: `??1CriticalSection@@UEAA@XZ`
- size: `96`
- prototype: `void __fastcall(CriticalSection *this, const char *, __int64, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e17c`
- `0x18000e188`
- `0x18000e640`

## callees

- `0x18000e5d0`
- `0x18000e728`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e615`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e615`

## pseudocode

```c
void __fastcall CriticalSection::~CriticalSection(CriticalSection *this, const char *a2, __int64 a3, const char *a4)
{
  HANDLE v5; // rcx
  const char *v6; // [rsp+28h] [rbp-30h]
  unsigned __int64 v7; // [rsp+30h] [rbp-28h]
  const char *v8; // [rsp+38h] [rbp-20h]
  const char *v9; // [rsp+48h] [rbp-10h]

  *(_QWORD *)this = &CriticalSection::`vftable';
  v5 = (HANDLE)*((_QWORD *)this + 4);
  if ( NtCurrentTeb()->ClientId.UniqueThread == v5 )
    VerifierStop(
      (unsigned int)v5,
      a2,
      (unsigned __int64)this + 16,
      a4,
      *((int *)this + 6),
      v6,
      v7,
      v8,
      (unsigned __int64)v5,
      v9);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *(_QWORD *)this = &ReferenceCounted::`vftable';
}

```

## disassembly

```asm
0x18000e5d0  mov     [rsp+arg_0], rbx
0x18000e5d5  push    rdi
0x18000e5d6  sub     rsp, 50h
0x18000e5da  lea     rax, ??_7CriticalSection@@6B@; const CriticalSection::`vftable'
0x18000e5e1  mov     rbx, rcx
0x18000e5e4  mov     [rcx], rax
0x18000e5e7  mov     rax, gs:30h
0x18000e5f0  mov     rcx, [rcx+20h]; unsigned int
0x18000e5f4  cmp     [rax+48h], rcx
0x18000e5f8  jnz     short loc_18000E611
0x18000e5fa  movsxd  rax, dword ptr [rbx+18h]
0x18000e5fe  lea     r8, [rbx+10h]; unsigned __int64
0x18000e602  mov     [rsp+58h+var_18], rcx; unsigned __int64
0x18000e607  mov     [rsp+58h+var_38], rax; unsigned __int64
0x18000e60c  call    ?VerifierStop@@YAXIPEBD_K0101010@Z; VerifierStop(uint,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *)
0x18000e611  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000e615  call    cs:__imp_DeleteCriticalSection
0x18000e61b  lea     rax, ??_7ReferenceCounted@@6B@; const ReferenceCounted::`vftable'
0x18000e622  mov     [rbx], rax
0x18000e625  mov     rbx, [rsp+58h+arg_0]
0x18000e62a  add     rsp, 50h
0x18000e62e  pop     rdi
0x18000e62f  retn
```
