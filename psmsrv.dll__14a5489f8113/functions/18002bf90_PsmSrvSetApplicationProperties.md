# PsmSrvSetApplicationProperties

- ea: `0x18002bf90`
- end: `0x18002c242`
- name: `PsmSrvSetApplicationProperties`
- size: `690`
- prototype: `__int64 __fastcall(__int64, unsigned int, void *, unsigned int, __int64, int, int, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800017b0`
- `0x1800093d0`
- `0x180009b40`
- `0x18000d010`
- `0x18000f7dc`
- `0x18001622c`
- `0x180017fa0`
- `0x18002bf90`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002c109`
- `ntdll!RtlFreeHeap` at `0x18002c1ed`
- `ntdll!RtlFreeHeap` at `0x18002c109`
- `ntdll!RtlFreeHeap` at `0x18002c1ed`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002c03c`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002c03c`
- `ntdll!RtlLengthSid` at `0x18002bfb4`
- `ntdll!RtlLengthSid` at `0x18002bfb4`
- `ntdll!RtlValidSid` at `0x18002bfc5`
- `ntdll!RtlValidSid` at `0x18002bfc5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c0be`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c128`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c1aa`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c0be`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c128`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c1aa`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c113`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c192`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c1f7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c113`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c192`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c1f7`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002c021`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002c021`

## pseudocode

```c
__int64 __fastcall PsmSrvSetApplicationProperties(
        __int64 a1,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  __int64 v15; // rbx
  _QWORD *UserContext; // rsi
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // r9
  __int64 Application; // rax
  __int64 v22; // rdi
  __int64 v23; // rbx
  __int64 v24; // rdx
  _QWORD *v25; // r8
  __int64 v26; // rbx
  __int64 v27; // r8
  unsigned int v28; // ebp
  __int64 v29; // rbx
  __int64 v30; // rcx
  _QWORD *v31; // rdx

  if ( a2 >= 2 && RtlLengthSid(a3) == a2 && RtlValidSid(a3) )
  {
    if ( a6 != 2 && a6 != 8 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
      return 3221225716LL;
    }
    v15 = *(_QWORD *)(a1 + 56);
    RtlAcquireSRWLockShared(v15 + 8);
    UserContext = (_QWORD *)PsmpFindUserContext(v15, a4, a3);
    RtlReleaseSRWLockShared(v15 + 8, v17, v18, v19);
    if ( !UserContext )
      return 3221225524LL;
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)(a5 + 2 * v20) );
    Application = PsmpFindApplication(0, UserContext, a5, 2 * v20 + 2);
    v22 = Application;
    if ( !Application )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          (unsigned int)&WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids,
          a5,
          a4);
      v23 = UserContext[7];
      RtlAcquireSRWLockExclusive(v23 + 8);
      if ( !(unsigned __int8)PsmpDereferenceObjectEx(UserContext, 0) )
        goto LABEL_22;
      v24 = UserContext[1];
      if ( *(_QWORD **)(v24 + 8) == UserContext + 1 )
      {
        v25 = (_QWORD *)UserContext[2];
        if ( (_QWORD *)*v25 == UserContext + 1 )
        {
          *v25 = v24;
          *(_QWORD *)(v24 + 8) = v25;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UserContext);
LABEL_22:
          RtlReleaseSRWLockExclusive(v23 + 8);
          return 3221225524LL;
        }
      }
LABEL_30:
      __fastfail(3u);
    }
    v26 = Application + 328;
    RtlAcquireSRWLockExclusive(Application + 328);
    v27 = 6800;
    if ( a6 != 2 )
      v27 = 6808;
    v28 = PsmpSetApplicationProperties(v22, a6, *(_QWORD *)(v27 + v22), a7, a8, a9, a10, a11, 0);
    RtlReleaseSRWLockExclusive(v26);
    PsmpDereferenceApplicationEx(v22, 0);
    v29 = UserContext[7];
    RtlAcquireSRWLockExclusive(v29 + 8);
    if ( (unsigned __int8)PsmpDereferenceObjectEx(UserContext, 0) )
    {
      v30 = UserContext[1];
      if ( *(_QWORD **)(v30 + 8) != UserContext + 1 )
        goto LABEL_30;
      v31 = (_QWORD *)UserContext[2];
      if ( (_QWORD *)*v31 != UserContext + 1 )
        goto LABEL_30;
      *v31 = v30;
      *(_QWORD *)(v30 + 8) = v31;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UserContext);
    }
    RtlReleaseSRWLockExclusive(v29 + 8);
    return v28;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
  return 3221225713LL;
}

```

## disassembly

```asm
0x18002bf90  push    rbx
0x18002bf92  push    rbp
0x18002bf93  push    rsi
0x18002bf94  push    rdi
0x18002bf95  push    r12
0x18002bf97  push    r14
0x18002bf99  sub     rsp, 58h
0x18002bf9d  mov     r14d, r9d
0x18002bfa0  mov     rsi, r8
0x18002bfa3  mov     ebx, edx
0x18002bfa5  mov     rdi, rcx
0x18002bfa8  cmp     edx, 2
0x18002bfab  jb      loc_18002C208
0x18002bfb1  mov     rcx, r8; Sid
0x18002bfb4  call    cs:__imp_RtlLengthSid
0x18002bfba  cmp     eax, ebx
0x18002bfbc  jnz     loc_18002C208
0x18002bfc2  mov     rcx, rsi; Sid
0x18002bfc5  call    cs:__imp_RtlValidSid
0x18002bfcb  xor     r12d, r12d
0x18002bfce  test    al, al
0x18002bfd0  jz      loc_18002C208
0x18002bfd6  mov     ebp, [rsp+88h+arg_28]
0x18002bfdd  cmp     ebp, 2
0x18002bfe0  jz      short loc_18002C019
0x18002bfe2  cmp     ebp, 8
0x18002bfe5  jz      short loc_18002C019
0x18002bfe7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfee  test    byte ptr [rcx+1Ch], 2
0x18002bff2  jz      short loc_18002C00F
0x18002bff4  cmp     byte ptr [rcx+19h], 2
0x18002bff8  jb      short loc_18002C00F
0x18002bffa  mov     rcx, [rcx+10h]
0x18002bffe  lea     edx, [r12+29h]
0x18002c003  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002c00a  call    WPP_SF_
0x18002c00f  mov     eax, 0C00000F4h
0x18002c014  jmp     loc_18002C235
0x18002c019  mov     rbx, [rdi+38h]
0x18002c01d  lea     rcx, [rbx+8]
0x18002c021  call    cs:__imp_RtlAcquireSRWLockShared
0x18002c027  mov     r8, rsi
0x18002c02a  mov     edx, r14d
0x18002c02d  mov     rcx, rbx
0x18002c030  call    PsmpFindUserContext
0x18002c035  lea     rcx, [rbx+8]
0x18002c039  mov     rsi, rax
0x18002c03c  call    cs:__imp_RtlReleaseSRWLockShared
0x18002c042  test    rsi, rsi
0x18002c045  jnz     short loc_18002C051
0x18002c047  mov     eax, 0C0000034h
0x18002c04c  jmp     loc_18002C235
0x18002c051  mov     rbx, [rsp+88h+arg_20]
0x18002c059  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002c05d  inc     r9
0x18002c060  cmp     [rbx+r9*2], r12w
0x18002c065  jnz     short loc_18002C05D
0x18002c067  lea     r9, ds:2[r9*2]
0x18002c06f  mov     r8, rbx
0x18002c072  mov     rdx, rsi
0x18002c075  xor     ecx, ecx
0x18002c077  call    PsmpFindApplication
0x18002c07c  mov     rdi, rax
0x18002c07f  test    rax, rax
0x18002c082  jnz     loc_18002C11E
0x18002c088  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c08f  test    byte ptr [rcx+1Ch], 2
0x18002c093  jz      short loc_18002C0B6
0x18002c095  cmp     byte ptr [rcx+19h], 2
0x18002c099  jb      short loc_18002C0B6
0x18002c09b  mov     rcx, [rcx+10h]
0x18002c09f  lea     edx, [rax+2Ah]
0x18002c0a2  mov     r9, rbx
0x18002c0a5  mov     dword ptr [rsp+88h+var_68], r14d
0x18002c0aa  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002c0b1  call    WPP_SF_Sd
0x18002c0b6  mov     rbx, [rsi+38h]
0x18002c0ba  lea     rcx, [rbx+8]
0x18002c0be  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002c0c4  xor     edx, edx
0x18002c0c6  mov     rcx, rsi
0x18002c0c9  call    PsmpDereferenceObjectEx
0x18002c0ce  test    al, al
0x18002c0d0  jz      short loc_18002C10F
0x18002c0d2  lea     rax, [rsi+8]
0x18002c0d6  mov     rdx, [rax]
0x18002c0d9  cmp     [rdx+8], rax
0x18002c0dd  jnz     loc_18002C201
0x18002c0e3  mov     r8, [rax+8]
0x18002c0e7  cmp     [r8], rax
0x18002c0ea  jnz     loc_18002C201
0x18002c0f0  mov     [r8], rdx
0x18002c0f3  mov     [rdx+8], r8
0x18002c0f7  mov     r8, rsi; P
0x18002c0fa  mov     rcx, gs:60h
0x18002c103  xor     edx, edx; Flags
0x18002c105  mov     rcx, [rcx+30h]; HeapHandle
0x18002c109  call    cs:__imp_RtlFreeHeap
0x18002c10f  lea     rcx, [rbx+8]
0x18002c113  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002c119  jmp     loc_18002C047
0x18002c11e  lea     rbx, [rax+148h]
0x18002c125  mov     rcx, rbx
0x18002c128  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002c12e  mov     r9, [rsp+88h+arg_30]
0x18002c136  mov     eax, 1A98h
0x18002c13b  mov     [rsp+88h+var_48], r12
0x18002c140  cmp     ebp, 2
0x18002c143  mov     edx, ebp
0x18002c145  mov     rcx, rdi
0x18002c148  lea     r8d, [rax-8]
0x18002c14c  cmovnz  r8d, eax
0x18002c150  mov     rax, [rsp+88h+arg_50]
0x18002c158  mov     [rsp+88h+var_50], rax
0x18002c15d  mov     rax, [rsp+88h+arg_48]
0x18002c165  mov     [rsp+88h+var_58], rax
0x18002c16a  mov     rax, [rsp+88h+arg_40]
0x18002c172  mov     r8, [r8+rdi]
0x18002c176  mov     [rsp+88h+var_60], rax
0x18002c17b  mov     rax, [rsp+88h+arg_38]
0x18002c183  mov     [rsp+88h+var_68], rax
0x18002c188  call    PsmpSetApplicationProperties
0x18002c18d  mov     rcx, rbx
0x18002c190  mov     ebp, eax
0x18002c192  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002c198  xor     edx, edx
0x18002c19a  mov     rcx, rdi
0x18002c19d  call    PsmpDereferenceApplicationEx
0x18002c1a2  mov     rbx, [rsi+38h]
0x18002c1a6  lea     rcx, [rbx+8]
0x18002c1aa  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002c1b0  xor     edx, edx
0x18002c1b2  mov     rcx, rsi
0x18002c1b5  call    PsmpDereferenceObjectEx
0x18002c1ba  test    al, al
0x18002c1bc  jz      short loc_18002C1F3
0x18002c1be  lea     rax, [rsi+8]
0x18002c1c2  mov     rcx, [rax]
0x18002c1c5  cmp     [rcx+8], rax
0x18002c1c9  jnz     short loc_18002C201
0x18002c1cb  mov     rdx, [rax+8]
0x18002c1cf  cmp     [rdx], rax
0x18002c1d2  jnz     short loc_18002C201
0x18002c1d4  mov     [rdx], rcx
0x18002c1d7  mov     r8, rsi; P
0x18002c1da  mov     [rcx+8], rdx
0x18002c1de  xor     edx, edx; Flags
0x18002c1e0  mov     rcx, gs:60h
0x18002c1e9  mov     rcx, [rcx+30h]; HeapHandle
0x18002c1ed  call    cs:__imp_RtlFreeHeap
0x18002c1f3  lea     rcx, [rbx+8]
0x18002c1f7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002c1fd  mov     eax, ebp
0x18002c1ff  jmp     short loc_18002C235
0x18002c201  mov     ecx, 3
0x18002c206  int     29h; Win8: RtlFailFast(ecx)
0x18002c208  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c20f  test    byte ptr [rcx+1Ch], 2
0x18002c213  jz      short loc_18002C230
0x18002c215  cmp     byte ptr [rcx+19h], 2
0x18002c219  jb      short loc_18002C230
0x18002c21b  mov     rcx, [rcx+10h]
0x18002c21f  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002c226  mov     edx, 28h ; '('
0x18002c22b  call    WPP_SF_
0x18002c230  mov     eax, 0C00000F1h
0x18002c235  add     rsp, 58h
0x18002c239  pop     r14
0x18002c23b  pop     r12
0x18002c23d  pop     rdi
0x18002c23e  pop     rsi
0x18002c23f  pop     rbp
0x18002c240  pop     rbx
0x18002c241  retn
```
