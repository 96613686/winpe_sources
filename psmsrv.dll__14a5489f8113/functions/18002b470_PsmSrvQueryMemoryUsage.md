# PsmSrvQueryMemoryUsage

- ea: `0x18002b470`
- end: `0x18002b6f6`
- name: `PsmSrvQueryMemoryUsage`
- size: `646`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800017b0`
- `0x1800093d0`
- `0x180009b40`
- `0x18000bc20`
- `0x18000d010`
- `0x18001622c`
- `0x180017fa0`
- `0x18002b470`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002b5e9`
- `ntdll!RtlFreeHeap` at `0x18002b6a1`
- `ntdll!RtlFreeHeap` at `0x18002b5e9`
- `ntdll!RtlFreeHeap` at `0x18002b6a1`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002b51c`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002b646`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002b51c`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002b646`
- `ntdll!RtlLengthSid` at `0x18002b494`
- `ntdll!RtlLengthSid` at `0x18002b494`
- `ntdll!RtlValidSid` at `0x18002b4a5`
- `ntdll!RtlValidSid` at `0x18002b4a5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b59e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b65e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b59e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b65e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b5f3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b6ab`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b5f3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b6ab`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002b501`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002b608`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002b501`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002b608`

## pseudocode

```c
__int64 __fastcall PsmSrvQueryMemoryUsage(
        __int64 a1,
        unsigned int a2,
        void *a3,
        int a4,
        WCHAR *a5,
        int a6,
        int a7,
        __int64 a8)
{
  __int64 v12; // rbx
  __int64 *UserContext; // rsi
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // r9
  _QWORD *Application; // rax
  __int64 v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // rdx
  __int64 **v22; // r8
  _QWORD *v23; // rbx
  __int64 v24; // r8
  unsigned int MemoryUsage; // ebp
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rbx
  __int64 v30; // rcx
  __int64 **v31; // rdx

  if ( a2 >= 2 && RtlLengthSid(a3) == a2 && RtlValidSid(a3) )
  {
    if ( a6 != 2 && a6 != 8 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
      return 3221225716LL;
    }
    v12 = *(_QWORD *)(a1 + 56);
    RtlAcquireSRWLockShared(v12 + 8);
    UserContext = PsmpFindUserContext(v12, a4, a3);
    RtlReleaseSRWLockShared(v12 + 8, v14, v15, v16);
    if ( !UserContext )
      return 3221225524LL;
    v17 = -1;
    do
      ++v17;
    while ( a5[v17] );
    Application = PsmpFindApplication(0, (__int64)UserContext, a5, 2 * v17 + 2);
    v19 = (__int64)Application;
    if ( !Application )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          (unsigned int)&WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids,
          (_DWORD)a5,
          a4);
      v20 = UserContext[7];
      RtlAcquireSRWLockExclusive(v20 + 8);
      if ( !PsmpDereferenceObjectEx((volatile signed __int32 *)UserContext, 0) )
        goto LABEL_22;
      v21 = UserContext[1];
      if ( *(__int64 **)(v21 + 8) == UserContext + 1 )
      {
        v22 = (__int64 **)UserContext[2];
        if ( *v22 == UserContext + 1 )
        {
          *v22 = (__int64 *)v21;
          *(_QWORD *)(v21 + 8) = v22;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UserContext);
LABEL_22:
          RtlReleaseSRWLockExclusive(v20 + 8);
          return 3221225524LL;
        }
      }
LABEL_30:
      __fastfail(3u);
    }
    v23 = Application + 41;
    RtlAcquireSRWLockShared(Application + 41);
    v24 = 6800;
    if ( a6 != 2 )
      v24 = 6808;
    MemoryUsage = PsmpQueryMemoryUsage(v19, a6, *(_QWORD *)(v24 + v19), a7, a8);
    RtlReleaseSRWLockShared(v23, v26, v27, v28);
    PsmpDereferenceApplicationEx(v19, 0);
    v29 = UserContext[7];
    RtlAcquireSRWLockExclusive(v29 + 8);
    if ( PsmpDereferenceObjectEx((volatile signed __int32 *)UserContext, 0) )
    {
      v30 = UserContext[1];
      if ( *(__int64 **)(v30 + 8) != UserContext + 1 )
        goto LABEL_30;
      v31 = (__int64 **)UserContext[2];
      if ( *v31 != UserContext + 1 )
        goto LABEL_30;
      *v31 = (__int64 *)v30;
      *(_QWORD *)(v30 + 8) = v31;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UserContext);
    }
    RtlReleaseSRWLockExclusive(v29 + 8);
    return MemoryUsage;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
  return 3221225713LL;
}

```

## disassembly

```asm
0x18002b470  push    rbx
0x18002b472  push    rbp
0x18002b473  push    rsi
0x18002b474  push    rdi
0x18002b475  push    r12
0x18002b477  push    r14
0x18002b479  sub     rsp, 38h
0x18002b47d  mov     r14d, r9d
0x18002b480  mov     rsi, r8
0x18002b483  mov     ebx, edx
0x18002b485  mov     rdi, rcx
0x18002b488  cmp     edx, 2
0x18002b48b  jb      loc_18002B6BC
0x18002b491  mov     rcx, r8; Sid
0x18002b494  call    cs:__imp_RtlLengthSid
0x18002b49a  cmp     eax, ebx
0x18002b49c  jnz     loc_18002B6BC
0x18002b4a2  mov     rcx, rsi; Sid
0x18002b4a5  call    cs:__imp_RtlValidSid
0x18002b4ab  xor     r12d, r12d
0x18002b4ae  test    al, al
0x18002b4b0  jz      loc_18002B6BC
0x18002b4b6  mov     ebp, [rsp+68h+arg_28]
0x18002b4bd  cmp     ebp, 2
0x18002b4c0  jz      short loc_18002B4F9
0x18002b4c2  cmp     ebp, 8
0x18002b4c5  jz      short loc_18002B4F9
0x18002b4c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4ce  test    byte ptr [rcx+1Ch], 2
0x18002b4d2  jz      short loc_18002B4EF
0x18002b4d4  cmp     byte ptr [rcx+19h], 2
0x18002b4d8  jb      short loc_18002B4EF
0x18002b4da  mov     rcx, [rcx+10h]
0x18002b4de  lea     edx, [r12+18h]
0x18002b4e3  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002b4ea  call    WPP_SF_
0x18002b4ef  mov     eax, 0C00000F4h
0x18002b4f4  jmp     loc_18002B6E9
0x18002b4f9  mov     rbx, [rdi+38h]
0x18002b4fd  lea     rcx, [rbx+8]
0x18002b501  call    cs:__imp_RtlAcquireSRWLockShared
0x18002b507  mov     r8, rsi
0x18002b50a  mov     edx, r14d
0x18002b50d  mov     rcx, rbx
0x18002b510  call    PsmpFindUserContext
0x18002b515  lea     rcx, [rbx+8]
0x18002b519  mov     rsi, rax
0x18002b51c  call    cs:__imp_RtlReleaseSRWLockShared
0x18002b522  test    rsi, rsi
0x18002b525  jnz     short loc_18002B531
0x18002b527  mov     eax, 0C0000034h
0x18002b52c  jmp     loc_18002B6E9
0x18002b531  mov     rbx, [rsp+68h+arg_20]
0x18002b539  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002b53d  inc     r9
0x18002b540  cmp     [rbx+r9*2], r12w
0x18002b545  jnz     short loc_18002B53D
0x18002b547  lea     r9, ds:2[r9*2]
0x18002b54f  mov     r8, rbx
0x18002b552  mov     rdx, rsi
0x18002b555  xor     ecx, ecx
0x18002b557  call    PsmpFindApplication
0x18002b55c  mov     rdi, rax
0x18002b55f  test    rax, rax
0x18002b562  jnz     loc_18002B5FE
0x18002b568  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b56f  test    byte ptr [rcx+1Ch], 2
0x18002b573  jz      short loc_18002B596
0x18002b575  cmp     byte ptr [rcx+19h], 2
0x18002b579  jb      short loc_18002B596
0x18002b57b  mov     rcx, [rcx+10h]
0x18002b57f  lea     edx, [rax+19h]
0x18002b582  mov     r9, rbx
0x18002b585  mov     dword ptr [rsp+68h+var_48], r14d
0x18002b58a  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002b591  call    WPP_SF_Sd
0x18002b596  mov     rbx, [rsi+38h]
0x18002b59a  lea     rcx, [rbx+8]
0x18002b59e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002b5a4  xor     edx, edx
0x18002b5a6  mov     rcx, rsi
0x18002b5a9  call    PsmpDereferenceObjectEx
0x18002b5ae  test    al, al
0x18002b5b0  jz      short loc_18002B5EF
0x18002b5b2  lea     rax, [rsi+8]
0x18002b5b6  mov     rdx, [rax]
0x18002b5b9  cmp     [rdx+8], rax
0x18002b5bd  jnz     loc_18002B6B5
0x18002b5c3  mov     r8, [rax+8]
0x18002b5c7  cmp     [r8], rax
0x18002b5ca  jnz     loc_18002B6B5
0x18002b5d0  mov     [r8], rdx
0x18002b5d3  mov     [rdx+8], r8
0x18002b5d7  mov     r8, rsi; P
0x18002b5da  mov     rcx, gs:60h
0x18002b5e3  xor     edx, edx; Flags
0x18002b5e5  mov     rcx, [rcx+30h]; HeapHandle
0x18002b5e9  call    cs:__imp_RtlFreeHeap
0x18002b5ef  lea     rcx, [rbx+8]
0x18002b5f3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002b5f9  jmp     loc_18002B527
0x18002b5fe  lea     rbx, [rax+148h]
0x18002b605  mov     rcx, rbx
0x18002b608  call    cs:__imp_RtlAcquireSRWLockShared
0x18002b60e  mov     r9, [rsp+68h+arg_30]
0x18002b616  mov     eax, 1A98h
0x18002b61b  cmp     ebp, 2
0x18002b61e  mov     edx, ebp
0x18002b620  mov     rcx, rdi
0x18002b623  lea     r8d, [rax-8]
0x18002b627  cmovnz  r8d, eax
0x18002b62b  mov     rax, [rsp+68h+arg_38]
0x18002b633  mov     [rsp+68h+var_48], rax
0x18002b638  mov     r8, [r8+rdi]
0x18002b63c  call    PsmpQueryMemoryUsage
0x18002b641  mov     rcx, rbx
0x18002b644  mov     ebp, eax
0x18002b646  call    cs:__imp_RtlReleaseSRWLockShared
0x18002b64c  xor     edx, edx
0x18002b64e  mov     rcx, rdi
0x18002b651  call    PsmpDereferenceApplicationEx
0x18002b656  mov     rbx, [rsi+38h]
0x18002b65a  lea     rcx, [rbx+8]
0x18002b65e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002b664  xor     edx, edx
0x18002b666  mov     rcx, rsi
0x18002b669  call    PsmpDereferenceObjectEx
0x18002b66e  test    al, al
0x18002b670  jz      short loc_18002B6A7
0x18002b672  lea     rax, [rsi+8]
0x18002b676  mov     rcx, [rax]
0x18002b679  cmp     [rcx+8], rax
0x18002b67d  jnz     short loc_18002B6B5
0x18002b67f  mov     rdx, [rax+8]
0x18002b683  cmp     [rdx], rax
0x18002b686  jnz     short loc_18002B6B5
0x18002b688  mov     [rdx], rcx
0x18002b68b  mov     r8, rsi; P
0x18002b68e  mov     [rcx+8], rdx
0x18002b692  xor     edx, edx; Flags
0x18002b694  mov     rcx, gs:60h
0x18002b69d  mov     rcx, [rcx+30h]; HeapHandle
0x18002b6a1  call    cs:__imp_RtlFreeHeap
0x18002b6a7  lea     rcx, [rbx+8]
0x18002b6ab  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002b6b1  mov     eax, ebp
0x18002b6b3  jmp     short loc_18002B6E9
0x18002b6b5  mov     ecx, 3
0x18002b6ba  int     29h; Win8: RtlFailFast(ecx)
0x18002b6bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b6c3  test    byte ptr [rcx+1Ch], 2
0x18002b6c7  jz      short loc_18002B6E4
0x18002b6c9  cmp     byte ptr [rcx+19h], 2
0x18002b6cd  jb      short loc_18002B6E4
0x18002b6cf  mov     rcx, [rcx+10h]
0x18002b6d3  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002b6da  mov     edx, 17h
0x18002b6df  call    WPP_SF_
0x18002b6e4  mov     eax, 0C00000F1h
0x18002b6e9  add     rsp, 38h
0x18002b6ed  pop     r14
0x18002b6ef  pop     r12
0x18002b6f1  pop     rdi
0x18002b6f2  pop     rsi
0x18002b6f3  pop     rbp
0x18002b6f4  pop     rbx
0x18002b6f5  retn
```
