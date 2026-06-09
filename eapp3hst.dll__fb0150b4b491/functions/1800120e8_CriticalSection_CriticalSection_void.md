# CriticalSection::~CriticalSection(void)

- ea: `0x1800120e8`
- end: `0x180012148`
- name: `??1CriticalSection@@UEAA@XZ`
- size: `96`
- prototype: `void __fastcall(CriticalSection *this, const char *, __int64, const char *)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d30`
- `0x1800121b0`
- `0x180020280`
- `0x180021b48`
- `0x180027f68`
- `0x1800295f0`
- `0x18002b800`
- `0x18002e3cc`
- `0x18003204e`
- `0x180032ce6`
- `0x180032ee8`
- `0x18003395e`

## callees

- `0x1800120e8`
- `0x180012c84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001212d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001212d`

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
0x1800120e8  mov     [rsp+arg_0], rbx
0x1800120ed  push    rdi
0x1800120ee  sub     rsp, 50h
0x1800120f2  lea     rax, ??_7CriticalSection@@6B@; const CriticalSection::`vftable'
0x1800120f9  mov     rbx, rcx
0x1800120fc  mov     [rcx], rax
0x1800120ff  mov     rax, gs:30h
0x180012108  mov     rcx, [rcx+20h]; unsigned int
0x18001210c  cmp     [rax+48h], rcx
0x180012110  jnz     short loc_180012129
0x180012112  movsxd  rax, dword ptr [rbx+18h]
0x180012116  lea     r8, [rbx+10h]; unsigned __int64
0x18001211a  mov     [rsp+58h+var_18], rcx; unsigned __int64
0x18001211f  mov     [rsp+58h+var_38], rax; unsigned __int64
0x180012124  call    ?VerifierStop@@YAXIPEBD_K0101010@Z; VerifierStop(uint,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *)
0x180012129  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001212d  call    cs:__imp_DeleteCriticalSection
0x180012133  lea     rax, ??_7ReferenceCounted@@6B@; const ReferenceCounted::`vftable'
0x18001213a  mov     [rbx], rax
0x18001213d  mov     rbx, [rsp+58h+arg_0]
0x180012142  add     rsp, 50h
0x180012146  pop     rdi
0x180012147  retn
```
