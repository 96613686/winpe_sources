# PsmSrvQueryApplicationProperties

- ea: `0x18001a190`
- end: `0x18001a43d`
- name: `PsmSrvQueryApplicationProperties`
- size: `685`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800017b0`
- `0x1800093d0`
- `0x180009b40`
- `0x18000d010`
- `0x18001622c`
- `0x180017fa0`
- `0x18001a190`
- `0x18001a444`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001a309`
- `ntdll!RtlFreeHeap` at `0x18001a3e8`
- `ntdll!RtlFreeHeap` at `0x18001a309`
- `ntdll!RtlFreeHeap` at `0x18001a3e8`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001a23c`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001a38d`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001a23c`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001a38d`
- `ntdll!RtlLengthSid` at `0x18001a1b4`
- `ntdll!RtlLengthSid` at `0x18001a1b4`
- `ntdll!RtlValidSid` at `0x18001a1c5`
- `ntdll!RtlValidSid` at `0x18001a1c5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a2be`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a3a5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a2be`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a3a5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a313`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a3f2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a313`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a3f2`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001a221`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001a328`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001a221`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001a328`

## pseudocode

```c
__int64 __fastcall PsmSrvQueryApplicationProperties(
        __int64 a1,
        unsigned int a2,
        void *a3,
        int a4,
        WCHAR *a5,
        int a6,
        int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  __int64 v15; // rbx
  __int64 *UserContext; // rsi
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // r9
  _QWORD *Application; // rax
  __int64 v22; // rdi
  __int64 v23; // rbx
  __int64 v24; // rdx
  __int64 **v25; // r8
  _QWORD *v26; // rbx
  __int64 v27; // r8
  unsigned int ApplicationProperties; // ebp
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rbx
  __int64 v33; // rcx
  __int64 **v34; // rdx

  if ( a2 >= 2 && RtlLengthSid(a3) == a2 && RtlValidSid(a3) )
  {
    if ( a6 != 2 && a6 != 8 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
      return 3221225716LL;
    }
    v15 = *(_QWORD *)(a1 + 56);
    RtlAcquireSRWLockShared(v15 + 8);
    UserContext = PsmpFindUserContext(v15, a4, a3);
    RtlReleaseSRWLockShared(v15 + 8, v17, v18, v19);
    if ( !UserContext )
      return 3221225524LL;
    v20 = -1;
    do
      ++v20;
    while ( a5[v20] );
    Application = PsmpFindApplication(0, (__int64)UserContext, a5, 2 * v20 + 2);
    v22 = (__int64)Application;
    if ( !Application )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)&WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids,
          (_DWORD)a5,
          a4);
      v23 = UserContext[7];
      RtlAcquireSRWLockExclusive(v23 + 8);
      if ( !PsmpDereferenceObjectEx((volatile signed __int32 *)UserContext, 0) )
        goto LABEL_22;
      v24 = UserContext[1];
      if ( *(__int64 **)(v24 + 8) == UserContext + 1 )
      {
        v25 = (__int64 **)UserContext[2];
        if ( *v25 == UserContext + 1 )
        {
          *v25 = (__int64 *)v24;
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
    v26 = Application + 41;
    RtlAcquireSRWLockShared(Application + 41);
    v27 = 6800;
    if ( a6 != 2 )
      v27 = 6808;
    ApplicationProperties = PsmpQueryApplicationProperties(v22, a6, *(_QWORD *)(v27 + v22), a7, a8, a9, a10, a11);
    RtlReleaseSRWLockShared(v26, v29, v30, v31);
    PsmpDereferenceApplicationEx(v22, 0);
    v32 = UserContext[7];
    RtlAcquireSRWLockExclusive(v32 + 8);
    if ( PsmpDereferenceObjectEx((volatile signed __int32 *)UserContext, 0) )
    {
      v33 = UserContext[1];
      if ( *(__int64 **)(v33 + 8) != UserContext + 1 )
        goto LABEL_30;
      v34 = (__int64 **)UserContext[2];
      if ( *v34 != UserContext + 1 )
        goto LABEL_30;
      *v34 = (__int64 *)v33;
      *(_QWORD *)(v33 + 8) = v34;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UserContext);
    }
    RtlReleaseSRWLockExclusive(v32 + 8);
    return ApplicationProperties;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
  return 3221225713LL;
}

```

## disassembly

```asm
0x18001a190  push    rbx
0x18001a192  push    rbp
0x18001a193  push    rsi
0x18001a194  push    rdi
0x18001a195  push    r12
0x18001a197  push    r14
0x18001a199  sub     rsp, 58h
0x18001a19d  mov     r14d, r9d
0x18001a1a0  mov     rsi, r8
0x18001a1a3  mov     ebx, edx
0x18001a1a5  mov     rdi, rcx
0x18001a1a8  cmp     edx, 2
0x18001a1ab  jb      loc_18001A403
0x18001a1b1  mov     rcx, r8; Sid
0x18001a1b4  call    cs:__imp_RtlLengthSid
0x18001a1ba  cmp     eax, ebx
0x18001a1bc  jnz     loc_18001A403
0x18001a1c2  mov     rcx, rsi; Sid
0x18001a1c5  call    cs:__imp_RtlValidSid
0x18001a1cb  xor     r12d, r12d
0x18001a1ce  test    al, al
0x18001a1d0  jz      loc_18001A403
0x18001a1d6  mov     ebp, [rsp+88h+arg_28]
0x18001a1dd  cmp     ebp, 2
0x18001a1e0  jz      short loc_18001A219
0x18001a1e2  cmp     ebp, 8
0x18001a1e5  jz      short loc_18001A219
0x18001a1e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1ee  test    byte ptr [rcx+1Ch], 2
0x18001a1f2  jz      short loc_18001A20F
0x18001a1f4  cmp     byte ptr [rcx+19h], 2
0x18001a1f8  jb      short loc_18001A20F
0x18001a1fa  mov     rcx, [rcx+10h]
0x18001a1fe  lea     edx, [r12+0Eh]
0x18001a203  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18001a20a  call    WPP_SF_
0x18001a20f  mov     eax, 0C00000F4h
0x18001a214  jmp     loc_18001A430
0x18001a219  mov     rbx, [rdi+38h]
0x18001a21d  lea     rcx, [rbx+8]
0x18001a221  call    cs:__imp_RtlAcquireSRWLockShared
0x18001a227  mov     r8, rsi
0x18001a22a  mov     edx, r14d
0x18001a22d  mov     rcx, rbx
0x18001a230  call    PsmpFindUserContext
0x18001a235  lea     rcx, [rbx+8]
0x18001a239  mov     rsi, rax
0x18001a23c  call    cs:__imp_RtlReleaseSRWLockShared
0x18001a242  test    rsi, rsi
0x18001a245  jnz     short loc_18001A251
0x18001a247  mov     eax, 0C0000034h
0x18001a24c  jmp     loc_18001A430
0x18001a251  mov     rbx, [rsp+88h+arg_20]
0x18001a259  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001a25d  inc     r9
0x18001a260  cmp     [rbx+r9*2], r12w
0x18001a265  jnz     short loc_18001A25D
0x18001a267  lea     r9, ds:2[r9*2]
0x18001a26f  mov     r8, rbx
0x18001a272  mov     rdx, rsi
0x18001a275  xor     ecx, ecx
0x18001a277  call    PsmpFindApplication
0x18001a27c  mov     rdi, rax
0x18001a27f  test    rax, rax
0x18001a282  jnz     loc_18001A31E
0x18001a288  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a28f  test    byte ptr [rcx+1Ch], 2
0x18001a293  jz      short loc_18001A2B6
0x18001a295  cmp     byte ptr [rcx+19h], 2
0x18001a299  jb      short loc_18001A2B6
0x18001a29b  mov     rcx, [rcx+10h]
0x18001a29f  lea     edx, [rax+0Fh]
0x18001a2a2  mov     r9, rbx
0x18001a2a5  mov     dword ptr [rsp+88h+var_68], r14d
0x18001a2aa  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18001a2b1  call    WPP_SF_Sd
0x18001a2b6  mov     rbx, [rsi+38h]
0x18001a2ba  lea     rcx, [rbx+8]
0x18001a2be  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001a2c4  xor     edx, edx
0x18001a2c6  mov     rcx, rsi
0x18001a2c9  call    PsmpDereferenceObjectEx
0x18001a2ce  test    al, al
0x18001a2d0  jz      short loc_18001A30F
0x18001a2d2  lea     rax, [rsi+8]
0x18001a2d6  mov     rdx, [rax]
0x18001a2d9  cmp     [rdx+8], rax
0x18001a2dd  jnz     loc_18001A3FC
0x18001a2e3  mov     r8, [rax+8]
0x18001a2e7  cmp     [r8], rax
0x18001a2ea  jnz     loc_18001A3FC
0x18001a2f0  mov     [r8], rdx
0x18001a2f3  mov     [rdx+8], r8
0x18001a2f7  mov     r8, rsi; P
0x18001a2fa  mov     rcx, gs:60h
0x18001a303  xor     edx, edx; Flags
0x18001a305  mov     rcx, [rcx+30h]; HeapHandle
0x18001a309  call    cs:__imp_RtlFreeHeap
0x18001a30f  lea     rcx, [rbx+8]
0x18001a313  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001a319  jmp     loc_18001A247
0x18001a31e  lea     rbx, [rax+148h]
0x18001a325  mov     rcx, rbx
0x18001a328  call    cs:__imp_RtlAcquireSRWLockShared
0x18001a32e  mov     r9, [rsp+88h+arg_30]
0x18001a336  mov     eax, 1A98h
0x18001a33b  cmp     ebp, 2
0x18001a33e  mov     edx, ebp
0x18001a340  mov     rcx, rdi
0x18001a343  lea     r8d, [rax-8]
0x18001a347  cmovnz  r8d, eax
0x18001a34b  mov     rax, [rsp+88h+arg_50]
0x18001a353  mov     [rsp+88h+var_50], rax
0x18001a358  mov     rax, [rsp+88h+arg_48]
0x18001a360  mov     [rsp+88h+var_58], rax
0x18001a365  mov     rax, [rsp+88h+arg_40]
0x18001a36d  mov     r8, [r8+rdi]
0x18001a371  mov     [rsp+88h+var_60], rax
0x18001a376  mov     rax, [rsp+88h+arg_38]
0x18001a37e  mov     [rsp+88h+var_68], rax
0x18001a383  call    PsmpQueryApplicationProperties
0x18001a388  mov     rcx, rbx
0x18001a38b  mov     ebp, eax
0x18001a38d  call    cs:__imp_RtlReleaseSRWLockShared
0x18001a393  xor     edx, edx
0x18001a395  mov     rcx, rdi
0x18001a398  call    PsmpDereferenceApplicationEx
0x18001a39d  mov     rbx, [rsi+38h]
0x18001a3a1  lea     rcx, [rbx+8]
0x18001a3a5  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001a3ab  xor     edx, edx
0x18001a3ad  mov     rcx, rsi
0x18001a3b0  call    PsmpDereferenceObjectEx
0x18001a3b5  test    al, al
0x18001a3b7  jz      short loc_18001A3EE
0x18001a3b9  lea     rax, [rsi+8]
0x18001a3bd  mov     rcx, [rax]
0x18001a3c0  cmp     [rcx+8], rax
0x18001a3c4  jnz     short loc_18001A3FC
0x18001a3c6  mov     rdx, [rax+8]
0x18001a3ca  cmp     [rdx], rax
0x18001a3cd  jnz     short loc_18001A3FC
0x18001a3cf  mov     [rdx], rcx
0x18001a3d2  mov     r8, rsi; P
0x18001a3d5  mov     [rcx+8], rdx
0x18001a3d9  xor     edx, edx; Flags
0x18001a3db  mov     rcx, gs:60h
0x18001a3e4  mov     rcx, [rcx+30h]; HeapHandle
0x18001a3e8  call    cs:__imp_RtlFreeHeap
0x18001a3ee  lea     rcx, [rbx+8]
0x18001a3f2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001a3f8  mov     eax, ebp
0x18001a3fa  jmp     short loc_18001A430
0x18001a3fc  mov     ecx, 3
0x18001a401  int     29h; Win8: RtlFailFast(ecx)
0x18001a403  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a40a  test    byte ptr [rcx+1Ch], 2
0x18001a40e  jz      short loc_18001A42B
0x18001a410  cmp     byte ptr [rcx+19h], 2
0x18001a414  jb      short loc_18001A42B
0x18001a416  mov     rcx, [rcx+10h]
0x18001a41a  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18001a421  mov     edx, 0Dh
0x18001a426  call    WPP_SF_
0x18001a42b  mov     eax, 0C00000F1h
0x18001a430  add     rsp, 58h
0x18001a434  pop     r14
0x18001a436  pop     r12
0x18001a438  pop     rdi
0x18001a439  pop     rsi
0x18001a43a  pop     rbp
0x18001a43b  pop     rbx
0x18001a43c  retn
```
