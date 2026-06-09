# re2::Prog::GetDFA(re2::Prog::MatchKind)

- ea: `0x18021fe40`
- end: `0x18022004e`
- name: `?GetDFA@Prog@re2@@AEAAPEAVDFA@2@W4MatchKind@12@@Z`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180220bf0`

## callees

- `0x18020aae4`
- `0x18021efc0`
- `0x18021fe40`
- `0x180236938`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18021fe67`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18021fefe`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18021ff77`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18021fe67`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18021fefe`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18021ff77`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18021fecd`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18021ff58`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18022001b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18021fecd`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18021ff58`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18022001b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall re2::Prog::GetDFA(__int64 a1, int a2)
{
  union _RTL_RUN_ONCE *v3; // rdi
  void *v4; // rax
  union _RTL_RUN_ONCE *v6; // rdi
  void *v7; // rax
  union _RTL_RUN_ONCE *v8; // rdi
  void *v9; // rax
  __int64 v10; // rbx
  WINBOOL fPending; // [rsp+48h] [rbp+10h] BYREF
  void *v12; // [rsp+50h] [rbp+18h]

  if ( !a2 )
  {
    v3 = (union _RTL_RUN_ONCE *)(a1 + 424);
    if ( __std_init_once_begin_initialize((LPINIT_ONCE)(a1 + 424), 0, &fPending, 0) )
    {
      if ( fPending )
      {
        v4 = operator new(0xD0u);
        v12 = v4;
        if ( v4 )
          v4 = (void *)re2::DFA::DFA(v4, a1, 0, *(_QWORD *)(a1 + 144) / 2LL, v3, 4);
        *(_QWORD *)(a1 + 152) = v4;
        if ( !InitOnceComplete(v3, 0, 0) )
          _std_init_once_link_alternate_names_and_abort();
      }
      return *(_QWORD *)(a1 + 152);
    }
    goto LABEL_16;
  }
  if ( a2 == 3 )
  {
    v6 = (union _RTL_RUN_ONCE *)(a1 + 424);
    if ( __std_init_once_begin_initialize((LPINIT_ONCE)(a1 + 424), 0, &fPending, 0) )
    {
      if ( fPending )
      {
        v7 = operator new(0xD0u);
        v12 = v7;
        if ( v7 )
          v7 = (void *)re2::DFA::DFA(v7, a1, 3, *(_QWORD *)(a1 + 144), v6, 4);
        *(_QWORD *)(a1 + 152) = v7;
        if ( !InitOnceComplete(v6, 0, 0) )
          _std_init_once_link_alternate_names_and_abort();
      }
      return *(_QWORD *)(a1 + 152);
    }
LABEL_16:
    __fastfail(5u);
  }
  v8 = (union _RTL_RUN_ONCE *)(a1 + 432);
  if ( !__std_init_once_begin_initialize((LPINIT_ONCE)(a1 + 432), 0, &fPending, 0) )
    goto LABEL_16;
  if ( fPending )
  {
    if ( *(_BYTE *)(a1 + 2) )
    {
      v9 = operator new(0xD0u);
      v12 = v9;
      if ( v9 )
        v9 = (void *)re2::DFA::DFA(v9, a1, 1, *(_QWORD *)(a1 + 144), v8, 4);
    }
    else
    {
      v9 = operator new(0xD0u);
      v12 = v9;
      if ( v9 )
        v9 = (void *)re2::DFA::DFA(v9, a1, 1, *(_QWORD *)(a1 + 144) / 2LL, v8, 4);
    }
    v10 = a1 + 160;
    *(_QWORD *)v10 = v9;
    if ( !InitOnceComplete(v8, 0, 0) )
      _std_init_once_link_alternate_names_and_abort();
  }
  else
  {
    v10 = a1 + 160;
  }
  return *(_QWORD *)v10;
}

```

## disassembly

```asm
0x18021fe40  mov     [rsp+arg_0], rbx
0x18021fe45  push    rdi
0x18021fe46  sub     rsp, 30h
0x18021fe4a  mov     rbx, rcx
0x18021fe4d  xor     r9d, r9d; lpContext
0x18021fe50  lea     r8, [rsp+38h+fPending]; fPending
0x18021fe55  test    edx, edx
0x18021fe57  jnz     loc_18021FEED
0x18021fe5d  lea     rdi, [rcx+1A8h]
0x18021fe64  mov     rcx, rdi; lpInitOnce
0x18021fe67  call    cs:__imp___std_init_once_begin_initialize
0x18021fe6d  test    eax, eax
0x18021fe6f  jz      loc_18021FF81
0x18021fe75  cmp     [rsp+38h+fPending], 0
0x18021fe7a  jz      short loc_18021FEDB
0x18021fe7c  mov     [rsp+38h+var_18], rdi
0x18021fe81  mov     [rsp+38h+var_10], 4
0x18021fe89  mov     ecx, 0D0h; Size
0x18021fe8e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18021fe93  mov     rcx, rax
0x18021fe96  mov     [rsp+38h+arg_10], rax
0x18021fe9b  test    rax, rax
0x18021fe9e  jz      short loc_18021FEBE
0x18021fea0  mov     rax, [rbx+90h]
0x18021fea7  cqo
0x18021fea9  sub     rax, rdx
0x18021feac  sar     rax, 1
0x18021feaf  mov     r9, rax
0x18021feb2  xor     r8d, r8d
0x18021feb5  mov     rdx, rbx
0x18021feb8  call    ??0DFA@re2@@QEAA@PEAVProg@1@W4MatchKind@21@_J@Z; re2::DFA::DFA(re2::Prog *,re2::Prog::MatchKind,__int64)
0x18021febd  nop
0x18021febe  mov     [rbx+98h], rax
0x18021fec5  xor     r8d, r8d; lpContext
0x18021fec8  xor     edx, edx; dwFlags
0x18021feca  mov     rcx, rdi; lpInitOnce
0x18021fecd  call    cs:__imp_InitOnceComplete
0x18021fed3  test    eax, eax
0x18021fed5  jz      loc_18022003C
0x18021fedb  mov     rax, [rbx+98h]
0x18021fee2  mov     rbx, [rsp+38h+arg_0]
0x18021fee7  add     rsp, 30h
0x18021feeb  pop     rdi
0x18021feec  retn
0x18021feed  cmp     edx, 3
0x18021fef0  jnz     short loc_18021FF6B
0x18021fef2  lea     rdi, [rcx+1A8h]
0x18021fef9  xor     edx, edx; dwFlags
0x18021fefb  mov     rcx, rdi; lpInitOnce
0x18021fefe  call    cs:__imp___std_init_once_begin_initialize
0x18021ff04  test    eax, eax
0x18021ff06  jz      short loc_18021FF81
0x18021ff08  cmp     [rsp+38h+fPending], 0
0x18021ff0d  jz      short loc_18021FEDB
0x18021ff0f  mov     [rsp+38h+var_18], rdi
0x18021ff14  mov     [rsp+38h+var_10], 4
0x18021ff1c  mov     ecx, 0D0h; Size
0x18021ff21  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18021ff26  mov     [rsp+38h+arg_10], rax
0x18021ff2b  test    rax, rax
0x18021ff2e  jz      short loc_18021FF49
0x18021ff30  mov     r9, [rbx+90h]
0x18021ff37  mov     r8d, 3
0x18021ff3d  mov     rdx, rbx
0x18021ff40  mov     rcx, rax
0x18021ff43  call    ??0DFA@re2@@QEAA@PEAVProg@1@W4MatchKind@21@_J@Z; re2::DFA::DFA(re2::Prog *,re2::Prog::MatchKind,__int64)
0x18021ff48  nop
0x18021ff49  mov     [rbx+98h], rax
0x18021ff50  xor     r8d, r8d; lpContext
0x18021ff53  xor     edx, edx; dwFlags
0x18021ff55  mov     rcx, rdi; lpInitOnce
0x18021ff58  call    cs:__imp_InitOnceComplete
0x18021ff5e  test    eax, eax
0x18021ff60  jz      loc_180220042
0x18021ff66  jmp     loc_18021FEDB
0x18021ff6b  lea     rdi, [rcx+1B0h]
0x18021ff72  xor     edx, edx; dwFlags
0x18021ff74  mov     rcx, rdi; lpInitOnce
0x18021ff77  call    cs:__imp___std_init_once_begin_initialize
0x18021ff7d  test    eax, eax
0x18021ff7f  jnz     short loc_18021FF88
0x18021ff81  mov     ecx, 5
0x18021ff86  int     29h; Win8: RtlFailFast(ecx)
0x18021ff88  cmp     [rsp+38h+fPending], 0
0x18021ff8d  jz      loc_180220027
0x18021ff93  mov     [rsp+38h+var_18], rdi
0x18021ff98  mov     [rsp+38h+var_10], 4
0x18021ffa0  mov     ecx, 0D0h; Size
0x18021ffa5  cmp     byte ptr [rbx+2], 0
0x18021ffa9  jnz     short loc_18021FFE0
0x18021ffab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18021ffb0  mov     rcx, rax
0x18021ffb3  mov     [rsp+38h+arg_10], rax
0x18021ffb8  test    rax, rax
0x18021ffbb  jz      short loc_18021FFDE
0x18021ffbd  mov     rax, [rbx+90h]
0x18021ffc4  cqo
0x18021ffc6  sub     rax, rdx
0x18021ffc9  sar     rax, 1
0x18021ffcc  mov     r9, rax
0x18021ffcf  mov     r8d, 1
0x18021ffd5  mov     rdx, rbx
0x18021ffd8  call    ??0DFA@re2@@QEAA@PEAVProg@1@W4MatchKind@21@_J@Z; re2::DFA::DFA(re2::Prog *,re2::Prog::MatchKind,__int64)
0x18021ffdd  nop
0x18021ffde  jmp     short loc_180220008
0x18021ffe0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18021ffe5  mov     [rsp+38h+arg_10], rax
0x18021ffea  test    rax, rax
0x18021ffed  jz      short loc_180220008
0x18021ffef  mov     r9, [rbx+90h]
0x18021fff6  mov     r8d, 1
0x18021fffc  mov     rdx, rbx
0x18021ffff  mov     rcx, rax
0x180220002  call    ??0DFA@re2@@QEAA@PEAVProg@1@W4MatchKind@21@_J@Z; re2::DFA::DFA(re2::Prog *,re2::Prog::MatchKind,__int64)
0x180220007  nop
0x180220008  mov     ecx, 0A0h
0x18022000d  add     rbx, rcx
0x180220010  mov     [rbx], rax
0x180220013  xor     r8d, r8d; lpContext
0x180220016  xor     edx, edx; dwFlags
0x180220018  mov     rcx, rdi; lpInitOnce
0x18022001b  call    cs:__imp_InitOnceComplete
0x180220021  test    eax, eax
0x180220023  jz      short loc_180220048
0x180220025  jmp     short loc_18022002E
0x180220027  add     rbx, 0A0h
0x18022002e  mov     rax, [rbx]
0x180220031  mov     rbx, [rsp+38h+arg_0]
0x180220036  add     rsp, 30h
0x18022003a  pop     rdi
0x18022003b  retn
0x18022003c  call    __std_init_once_link_alternate_names_and_abort
0x180220042  call    __std_init_once_link_alternate_names_and_abort
0x180220048  call    __std_init_once_link_alternate_names_and_abort
```
