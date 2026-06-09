# CriticalSection::~CriticalSection(void)

- ea: `0x18000d8cc`
- end: `0x18000d933`
- name: `??1CriticalSection@@UEAA@XZ`
- size: `103`
- prototype: `void __fastcall(CriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d940`

## callees

- `0x18000d8cc`
- `0x18000d9f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d911`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d911`

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
0x18000d8cc  mov     [rsp+arg_0], rbx
0x18000d8d1  push    rdi
0x18000d8d2  sub     rsp, 50h
0x18000d8d6  lea     rax, ??_7CriticalSection@@6B@; const CriticalSection::`vftable'
0x18000d8dd  mov     rbx, rcx
0x18000d8e0  mov     [rcx], rax
0x18000d8e3  mov     rax, gs:30h
0x18000d8ec  mov     rcx, [rcx+20h]; unsigned int
0x18000d8f0  cmp     [rax+48h], rcx
0x18000d8f4  jnz     short loc_18000D90D
0x18000d8f6  movsxd  rax, dword ptr [rbx+18h]
0x18000d8fa  lea     r8, [rbx+10h]; unsigned __int64
0x18000d8fe  mov     [rsp+58h+var_18], rcx; unsigned __int64
0x18000d903  mov     [rsp+58h+var_38], rax; unsigned __int64
0x18000d908  call    ?VerifierStop@@YAXIPEBD_K0101010@Z; VerifierStop(uint,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *)
0x18000d90d  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000d911  call    cs:__imp_DeleteCriticalSection
0x18000d918  nop     dword ptr [rax+rax+00h]
0x18000d91d  lea     rax, ??_7ReferenceCounted@@6B@; const ReferenceCounted::`vftable'
0x18000d924  mov     [rbx], rax
0x18000d927  mov     rbx, [rsp+58h+arg_0]
0x18000d92c  add     rsp, 50h
0x18000d930  pop     rdi
0x18000d931  retn
```
