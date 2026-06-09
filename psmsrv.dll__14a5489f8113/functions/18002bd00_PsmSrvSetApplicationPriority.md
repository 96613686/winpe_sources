# PsmSrvSetApplicationPriority

- ea: `0x18002bd00`
- end: `0x18002bf8a`
- name: `PsmSrvSetApplicationPriority`
- size: `650`
- prototype: `__int64 __fastcall(__int64, unsigned int, void *, unsigned int, __int64, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800017b0`
- `0x1800093d0`
- `0x180009b40`
- `0x18000d010`
- `0x180010074`
- `0x18001622c`
- `0x180017fa0`
- `0x18002bd00`
- `0x18002c95c`
- `0x18002cab8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002be78`
- `ntdll!RtlFreeHeap` at `0x18002bf35`
- `ntdll!RtlFreeHeap` at `0x18002be78`
- `ntdll!RtlFreeHeap` at `0x18002bf35`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002bdab`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002bdab`
- `ntdll!RtlLengthSid` at `0x18002bd24`
- `ntdll!RtlLengthSid` at `0x18002bd24`
- `ntdll!RtlValidSid` at `0x18002bd35`
- `ntdll!RtlValidSid` at `0x18002bd35`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002be2d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002bec5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002bef2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002be2d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002bec5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002bef2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002be82`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002beda`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002bf3f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002be82`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002beda`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002bf3f`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002bd90`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002bd90`

## pseudocode

```c
__int64 __fastcall PsmSrvSetApplicationPriority(
        __int64 a1,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        __int64 a5,
        int a6)
{
  int v9; // edx
  int v10; // r8d
  __int64 v12; // rbx
  _QWORD *UserContext; // rsi
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // r9
  __int64 Application; // rax
  int v19; // r8d
  __int64 v20; // rdi
  __int64 v21; // rbx
  __int64 v22; // rdx
  _QWORD *v23; // r8
  unsigned int v24; // ebp
  __int64 v25; // rbx
  __int64 v26; // rcx
  _QWORD *v27; // rdx

  if ( a2 >= 2 && RtlLengthSid(a3) == a2 && RtlValidSid(a3) )
  {
    if ( a6 >= 2 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, a6, a5);
      return 3221225716LL;
    }
    v12 = *(_QWORD *)(a1 + 56);
    RtlAcquireSRWLockShared(v12 + 8);
    UserContext = (_QWORD *)PsmpFindUserContext(v12, a4, a3);
    RtlReleaseSRWLockShared(v12 + 8, v14, v15, v16);
    if ( !UserContext )
      return 3221225524LL;
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)(a5 + 2 * v17) );
    Application = PsmpFindApplication(0, UserContext, a5, 2 * v17 + 2);
    v20 = Application;
    if ( !Application )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          (unsigned int)&WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids,
          a5,
          a4);
      v21 = UserContext[7];
      RtlAcquireSRWLockExclusive(v21 + 8);
      if ( !(unsigned __int8)PsmpDereferenceObjectEx(UserContext, 0) )
        goto LABEL_21;
      v22 = UserContext[1];
      if ( *(_QWORD **)(v22 + 8) == UserContext + 1 )
      {
        v23 = (_QWORD *)UserContext[2];
        if ( (_QWORD *)*v23 == UserContext + 1 )
        {
          *v23 = v22;
          *(_QWORD *)(v22 + 8) = v23;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UserContext);
LABEL_21:
          RtlReleaseSRWLockExclusive(v21 + 8);
          return 3221225524LL;
        }
      }
LABEL_30:
      __fastfail(3u);
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_iLS(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, v19, *(_QWORD *)(Application + 96), a6, a5);
    RtlAcquireSRWLockExclusive(v20 + 328);
    v24 = PsmpSetApplicationPriority(v20, (unsigned int)a6);
    RtlReleaseSRWLockExclusive(v20 + 328);
    PsmpDereferenceApplicationEx(v20, 0);
    v25 = UserContext[7];
    RtlAcquireSRWLockExclusive(v25 + 8);
    if ( (unsigned __int8)PsmpDereferenceObjectEx(UserContext, 0) )
    {
      v26 = UserContext[1];
      if ( *(_QWORD **)(v26 + 8) != UserContext + 1 )
        goto LABEL_30;
      v27 = (_QWORD *)UserContext[2];
      if ( (_QWORD *)*v27 != UserContext + 1 )
        goto LABEL_30;
      *v27 = v26;
      *(_QWORD *)(v26 + 8) = v27;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UserContext);
    }
    RtlReleaseSRWLockExclusive(v25 + 8);
    return v24;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
  return 3221225713LL;
}

```

## disassembly

```asm
0x18002bd00  push    rbx
0x18002bd02  push    rbp
0x18002bd03  push    rsi
0x18002bd04  push    rdi
0x18002bd05  push    r12
0x18002bd07  push    r14
0x18002bd09  sub     rsp, 38h
0x18002bd0d  mov     r14d, r9d
0x18002bd10  mov     rsi, r8
0x18002bd13  mov     ebx, edx
0x18002bd15  mov     rdi, rcx
0x18002bd18  cmp     edx, 2
0x18002bd1b  jb      loc_18002BF50
0x18002bd21  mov     rcx, r8; Sid
0x18002bd24  call    cs:__imp_RtlLengthSid
0x18002bd2a  cmp     eax, ebx
0x18002bd2c  jnz     loc_18002BF50
0x18002bd32  mov     rcx, rsi; Sid
0x18002bd35  call    cs:__imp_RtlValidSid
0x18002bd3b  xor     r12d, r12d
0x18002bd3e  test    al, al
0x18002bd40  jz      loc_18002BF50
0x18002bd46  mov     ebp, [rsp+68h+arg_28]
0x18002bd4d  cmp     ebp, 2
0x18002bd50  jl      short loc_18002BD88
0x18002bd52  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bd59  test    byte ptr [rcx+1Ch], 2
0x18002bd5d  jz      short loc_18002BD7E
0x18002bd5f  cmp     byte ptr [rcx+19h], 2
0x18002bd63  jb      short loc_18002BD7E
0x18002bd65  mov     rax, [rsp+68h+arg_20]
0x18002bd6d  mov     r9d, ebp
0x18002bd70  mov     rcx, [rcx+10h]
0x18002bd74  mov     [rsp+68h+var_48], rax
0x18002bd79  call    WPP_SF_dS
0x18002bd7e  mov     eax, 0C00000F4h
0x18002bd83  jmp     loc_18002BF7D
0x18002bd88  mov     rbx, [rdi+38h]
0x18002bd8c  lea     rcx, [rbx+8]
0x18002bd90  call    cs:__imp_RtlAcquireSRWLockShared
0x18002bd96  mov     r8, rsi
0x18002bd99  mov     edx, r14d
0x18002bd9c  mov     rcx, rbx
0x18002bd9f  call    PsmpFindUserContext
0x18002bda4  lea     rcx, [rbx+8]
0x18002bda8  mov     rsi, rax
0x18002bdab  call    cs:__imp_RtlReleaseSRWLockShared
0x18002bdb1  test    rsi, rsi
0x18002bdb4  jnz     short loc_18002BDC0
0x18002bdb6  mov     eax, 0C0000034h
0x18002bdbb  jmp     loc_18002BF7D
0x18002bdc0  mov     rbx, [rsp+68h+arg_20]
0x18002bdc8  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002bdcc  inc     r9
0x18002bdcf  cmp     [rbx+r9*2], r12w
0x18002bdd4  jnz     short loc_18002BDCC
0x18002bdd6  lea     r9, ds:2[r9*2]
0x18002bdde  mov     r8, rbx
0x18002bde1  mov     rdx, rsi
0x18002bde4  xor     ecx, ecx
0x18002bde6  call    PsmpFindApplication
0x18002bdeb  mov     rdi, rax
0x18002bdee  test    rax, rax
0x18002bdf1  jnz     loc_18002BE8D
0x18002bdf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bdfe  test    byte ptr [rcx+1Ch], 2
0x18002be02  jz      short loc_18002BE25
0x18002be04  cmp     byte ptr [rcx+19h], 2
0x18002be08  jb      short loc_18002BE25
0x18002be0a  mov     rcx, [rcx+10h]
0x18002be0e  lea     edx, [rax+26h]
0x18002be11  mov     r9, rbx
0x18002be14  mov     dword ptr [rsp+68h+var_48], r14d
0x18002be19  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002be20  call    WPP_SF_Sd
0x18002be25  mov     rbx, [rsi+38h]
0x18002be29  lea     rcx, [rbx+8]
0x18002be2d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002be33  xor     edx, edx
0x18002be35  mov     rcx, rsi
0x18002be38  call    PsmpDereferenceObjectEx
0x18002be3d  test    al, al
0x18002be3f  jz      short loc_18002BE7E
0x18002be41  lea     rax, [rsi+8]
0x18002be45  mov     rdx, [rax]
0x18002be48  cmp     [rdx+8], rax
0x18002be4c  jnz     loc_18002BF49
0x18002be52  mov     r8, [rax+8]
0x18002be56  cmp     [r8], rax
0x18002be59  jnz     loc_18002BF49
0x18002be5f  mov     [r8], rdx
0x18002be62  mov     [rdx+8], r8
0x18002be66  mov     r8, rsi; P
0x18002be69  mov     rcx, gs:60h
0x18002be72  xor     edx, edx; Flags
0x18002be74  mov     rcx, [rcx+30h]; HeapHandle
0x18002be78  call    cs:__imp_RtlFreeHeap
0x18002be7e  lea     rcx, [rbx+8]
0x18002be82  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002be88  jmp     loc_18002BDB6
0x18002be8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be94  test    byte ptr [rcx+1Ch], 2
0x18002be98  jz      short loc_18002BEBB
0x18002be9a  cmp     byte ptr [rcx+19h], 4
0x18002be9e  jb      short loc_18002BEBB
0x18002bea0  mov     r9, [rax+60h]
0x18002bea4  mov     edx, 27h ; '''
0x18002bea9  mov     rcx, [rcx+10h]
0x18002bead  mov     [rsp+68h+var_40], rbx
0x18002beb2  mov     dword ptr [rsp+68h+var_48], ebp
0x18002beb6  call    WPP_SF_iLS
0x18002bebb  lea     rbx, [rdi+148h]
0x18002bec2  mov     rcx, rbx
0x18002bec5  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002becb  mov     edx, ebp
0x18002becd  mov     rcx, rdi
0x18002bed0  call    PsmpSetApplicationPriority
0x18002bed5  mov     rcx, rbx
0x18002bed8  mov     ebp, eax
0x18002beda  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002bee0  xor     edx, edx
0x18002bee2  mov     rcx, rdi
0x18002bee5  call    PsmpDereferenceApplicationEx
0x18002beea  mov     rbx, [rsi+38h]
0x18002beee  lea     rcx, [rbx+8]
0x18002bef2  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002bef8  xor     edx, edx
0x18002befa  mov     rcx, rsi
0x18002befd  call    PsmpDereferenceObjectEx
0x18002bf02  test    al, al
0x18002bf04  jz      short loc_18002BF3B
0x18002bf06  lea     rax, [rsi+8]
0x18002bf0a  mov     rcx, [rax]
0x18002bf0d  cmp     [rcx+8], rax
0x18002bf11  jnz     short loc_18002BF49
0x18002bf13  mov     rdx, [rax+8]
0x18002bf17  cmp     [rdx], rax
0x18002bf1a  jnz     short loc_18002BF49
0x18002bf1c  mov     [rdx], rcx
0x18002bf1f  mov     r8, rsi; P
0x18002bf22  mov     [rcx+8], rdx
0x18002bf26  xor     edx, edx; Flags
0x18002bf28  mov     rcx, gs:60h
0x18002bf31  mov     rcx, [rcx+30h]; HeapHandle
0x18002bf35  call    cs:__imp_RtlFreeHeap
0x18002bf3b  lea     rcx, [rbx+8]
0x18002bf3f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002bf45  mov     eax, ebp
0x18002bf47  jmp     short loc_18002BF7D
0x18002bf49  mov     ecx, 3
0x18002bf4e  int     29h; Win8: RtlFailFast(ecx)
0x18002bf50  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf57  test    byte ptr [rcx+1Ch], 2
0x18002bf5b  jz      short loc_18002BF78
0x18002bf5d  cmp     byte ptr [rcx+19h], 2
0x18002bf61  jb      short loc_18002BF78
0x18002bf63  mov     rcx, [rcx+10h]
0x18002bf67  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002bf6e  mov     edx, 24h ; '$'
0x18002bf73  call    WPP_SF_
0x18002bf78  mov     eax, 0C00000F1h
0x18002bf7d  add     rsp, 38h
0x18002bf81  pop     r14
0x18002bf83  pop     r12
0x18002bf85  pop     rdi
0x18002bf86  pop     rsi
0x18002bf87  pop     rbp
0x18002bf88  pop     rbx
0x18002bf89  retn
```
