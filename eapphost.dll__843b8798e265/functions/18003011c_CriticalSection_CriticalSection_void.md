# CriticalSection::~CriticalSection(void)

- ea: `0x18003011c`
- end: `0x1800301bf`
- name: `??1CriticalSection@@UEAA@XZ`
- size: `163`
- prototype: `void __fastcall(CriticalSection *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180011270`
- `0x1800180c0`
- `0x180019860`
- `0x18001a8bc`
- `0x18001d940`
- `0x180023cf0`
- `0x1800301d0`
- `0x180036bb4`
- `0x180036d00`
- `0x18003784f`
- `0x180038710`

## callees

- `0x18003011c`
- `0x180032550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003019d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003019d`

## string_xrefs

- `0x18003014c`: `owning thread`

## pseudocode

```c
void __fastcall CriticalSection::~CriticalSection(CriticalSection *this)
{
  HANDLE v2; // rcx

  *(_QWORD *)this = &CriticalSection::`vftable';
  v2 = (HANDLE)*((_QWORD *)this + 4);
  if ( NtCurrentTeb()->ClientId.UniqueThread == v2 )
    VerifierStop(
      0x208u,
      "deleting active critical section",
      (unsigned __int64)this + 16,
      "critical section address",
      *((int *)this + 6),
      "lock count",
      0xFFFFFFFFFFFFFFFFuLL,
      "expected lock count",
      (unsigned __int64)v2,
      "owning thread");
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *(_QWORD *)this = &ReferenceCounted::`vftable';
}

```

## disassembly

```asm
0x18003011c  mov     r11, rsp
0x18003011f  mov     [r11+8], rbx
0x180030123  push    rdi
0x180030124  sub     rsp, 50h
0x180030128  lea     rax, ??_7CriticalSection@@6B@; const CriticalSection::`vftable'
0x18003012f  mov     rbx, rcx
0x180030132  mov     [rcx], rax
0x180030135  mov     rax, gs:30h
0x18003013e  mov     rcx, [rcx+20h]
0x180030142  cmp     [rax+48h], rcx
0x180030146  jnz     short loc_180030199
0x180030148  movsxd  rax, dword ptr [rbx+18h]
0x18003014c  lea     rdx, aOwningThread; "owning thread"
0x180030153  mov     [r11-10h], rdx
0x180030157  lea     r9, aCriticalSectio; "critical section address"
0x18003015e  mov     [r11-18h], rcx
0x180030162  lea     r8, [rbx+10h]; unsigned __int64
0x180030166  lea     rcx, aExpectedLockCo; "expected lock count"
0x18003016d  mov     [r11-20h], rcx
0x180030171  lea     rdx, aDeletingActive; "deleting active critical section"
0x180030178  lea     rcx, aLockCount; "lock count"
0x18003017f  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFFh
0x180030187  mov     [r11-30h], rcx
0x18003018b  mov     ecx, 208h; unsigned int
0x180030190  mov     [r11-38h], rax
0x180030194  call    ?VerifierStop@@YAXIPEBD_K0101010@Z; VerifierStop(uint,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *)
0x180030199  lea     rcx, [rbx+10h]; lpCriticalSection
0x18003019d  call    cs:__imp_DeleteCriticalSection
0x1800301a4  nop     dword ptr [rax+rax+00h]
0x1800301a9  lea     rax, ??_7ReferenceCounted@@6B@; const ReferenceCounted::`vftable'
0x1800301b0  mov     [rbx], rax
0x1800301b3  mov     rbx, [rsp+58h+arg_0]
0x1800301b8  add     rsp, 50h
0x1800301bc  pop     rdi
0x1800301bd  retn
```
