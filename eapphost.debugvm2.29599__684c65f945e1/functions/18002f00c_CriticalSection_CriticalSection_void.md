# CriticalSection::~CriticalSection(void)

- ea: `0x18002f00c`
- end: `0x18002f0a8`
- name: `??1CriticalSection@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(CriticalSection *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180010bc0`
- `0x1800177ac`
- `0x180018eac`
- `0x180019ed4`
- `0x18001cea8`
- `0x180023080`
- `0x18002f0b0`
- `0x1800357f9`
- `0x180035945`
- `0x18003647a`
- `0x180037310`

## callees

- `0x18002f00c`
- `0x180031368`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f08d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f08d`

## string_xrefs

- `0x18002f03c`: `owning thread`

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
0x18002f00c  mov     r11, rsp
0x18002f00f  mov     [r11+8], rbx
0x18002f013  push    rdi
0x18002f014  sub     rsp, 50h
0x18002f018  lea     rax, ??_7CriticalSection@@6B@; const CriticalSection::`vftable'
0x18002f01f  mov     rbx, rcx
0x18002f022  mov     [rcx], rax
0x18002f025  mov     rax, gs:30h
0x18002f02e  mov     rcx, [rcx+20h]
0x18002f032  cmp     [rax+48h], rcx
0x18002f036  jnz     short loc_18002F089
0x18002f038  movsxd  rax, dword ptr [rbx+18h]
0x18002f03c  lea     rdx, aOwningThread; "owning thread"
0x18002f043  mov     [r11-10h], rdx
0x18002f047  lea     r9, aCriticalSectio; "critical section address"
0x18002f04e  mov     [r11-18h], rcx
0x18002f052  lea     r8, [rbx+10h]; unsigned __int64
0x18002f056  lea     rcx, aExpectedLockCo; "expected lock count"
0x18002f05d  mov     [r11-20h], rcx
0x18002f061  lea     rdx, aDeletingActive; "deleting active critical section"
0x18002f068  lea     rcx, aLockCount; "lock count"
0x18002f06f  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFFh
0x18002f077  mov     [r11-30h], rcx
0x18002f07b  mov     ecx, 208h; unsigned int
0x18002f080  mov     [r11-38h], rax
0x18002f084  call    ?VerifierStop@@YAXIPEBD_K0101010@Z; VerifierStop(uint,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *)
0x18002f089  lea     rcx, [rbx+10h]; lpCriticalSection
0x18002f08d  call    cs:__imp_DeleteCriticalSection
0x18002f093  lea     rax, ??_7ReferenceCounted@@6B@; const ReferenceCounted::`vftable'
0x18002f09a  mov     [rbx], rax
0x18002f09d  mov     rbx, [rsp+58h+arg_0]
0x18002f0a2  add     rsp, 50h
0x18002f0a6  pop     rdi
0x18002f0a7  retn
```
