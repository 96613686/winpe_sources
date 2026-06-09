# PsmSrvQuerySharedCommit

- ea: `0x18002b760`
- end: `0x18002b985`
- name: `PsmSrvQuerySharedCommit`
- size: `549`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800017b0`
- `0x1800093d0`
- `0x180009b40`
- `0x18000c61c`
- `0x18000d010`
- `0x18001622c`
- `0x180017fa0`
- `0x18002b760`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002b892`
- `ntdll!RtlFreeHeap` at `0x18002b932`
- `ntdll!RtlFreeHeap` at `0x18002b892`
- `ntdll!RtlFreeHeap` at `0x18002b932`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002b7c6`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002b8d7`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002b7c6`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002b8d7`
- `ntdll!RtlLengthSid` at `0x18002b782`
- `ntdll!RtlLengthSid` at `0x18002b782`
- `ntdll!RtlValidSid` at `0x18002b793`
- `ntdll!RtlValidSid` at `0x18002b793`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b847`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b8ef`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b847`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b8ef`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b89c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b93c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b89c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b93c`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002b7ac`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002b8b1`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002b7ac`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002b8b1`

## pseudocode

```c
__int64 __fastcall PsmSrvQuerySharedCommit(__int64 a1, unsigned int a2, void *a3, int a4, WCHAR *a5, int a6, void *a7)
{
  __int64 v10; // rbx
  __int64 *UserContext; // rsi
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v16; // r9
  _QWORD *Application; // rax
  _QWORD *v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // rdx
  __int64 **v21; // r8
  _QWORD *v22; // rbx
  unsigned int SharedCommit; // ebp
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rbx
  __int64 v28; // rcx
  __int64 **v29; // rdx

  if ( a2 >= 2 && RtlLengthSid(a3) == a2 && RtlValidSid(a3) )
  {
    v10 = *(_QWORD *)(a1 + 56);
    RtlAcquireSRWLockShared(v10 + 8);
    UserContext = PsmpFindUserContext(v10, a4, a3);
    RtlReleaseSRWLockShared(v10 + 8, v12, v13, v14);
    if ( !UserContext )
      return 3221225524LL;
    v16 = -1;
    do
      ++v16;
    while ( a5[v16] );
    Application = PsmpFindApplication(0, (__int64)UserContext, a5, 2 * v16 + 2);
    v18 = Application;
    if ( !Application )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)&WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids,
          (_DWORD)a5,
          a4);
      v19 = UserContext[7];
      RtlAcquireSRWLockExclusive(v19 + 8);
      if ( !PsmpDereferenceObjectEx((volatile signed __int32 *)UserContext, 0) )
        goto LABEL_16;
      v20 = UserContext[1];
      if ( *(__int64 **)(v20 + 8) == UserContext + 1 )
      {
        v21 = (__int64 **)UserContext[2];
        if ( *v21 == UserContext + 1 )
        {
          *v21 = (__int64 *)v20;
          *(_QWORD *)(v20 + 8) = v21;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UserContext);
LABEL_16:
          RtlReleaseSRWLockExclusive(v19 + 8);
          return 3221225524LL;
        }
      }
LABEL_22:
      __fastfail(3u);
    }
    v22 = Application + 41;
    RtlAcquireSRWLockShared(Application + 41);
    SharedCommit = PsmpQuerySharedCommit(v18, a6, -1, a7);
    RtlReleaseSRWLockShared(v22, v24, v25, v26);
    PsmpDereferenceApplicationEx((__int64)v18, 0);
    v27 = UserContext[7];
    RtlAcquireSRWLockExclusive(v27 + 8);
    if ( PsmpDereferenceObjectEx((volatile signed __int32 *)UserContext, 0) )
    {
      v28 = UserContext[1];
      if ( *(__int64 **)(v28 + 8) != UserContext + 1 )
        goto LABEL_22;
      v29 = (__int64 **)UserContext[2];
      if ( *v29 != UserContext + 1 )
        goto LABEL_22;
      *v29 = (__int64 *)v28;
      *(_QWORD *)(v28 + 8) = v29;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UserContext);
    }
    RtlReleaseSRWLockExclusive(v27 + 8);
    return SharedCommit;
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
    return 3221225713LL;
  }
}

```

## disassembly

```asm
0x18002b760  push    rbx
0x18002b762  push    rbp
0x18002b763  push    rsi
0x18002b764  push    rdi
0x18002b765  push    r14
0x18002b767  sub     rsp, 30h
0x18002b76b  mov     ebp, r9d
0x18002b76e  mov     rsi, r8
0x18002b771  mov     ebx, edx
0x18002b773  mov     rdi, rcx
0x18002b776  cmp     edx, 2
0x18002b779  jb      loc_18002B94D
0x18002b77f  mov     rcx, r8; Sid
0x18002b782  call    cs:__imp_RtlLengthSid
0x18002b788  cmp     eax, ebx
0x18002b78a  jnz     loc_18002B94D
0x18002b790  mov     rcx, rsi; Sid
0x18002b793  call    cs:__imp_RtlValidSid
0x18002b799  xor     r14d, r14d
0x18002b79c  test    al, al
0x18002b79e  jz      loc_18002B94D
0x18002b7a4  mov     rbx, [rdi+38h]
0x18002b7a8  lea     rcx, [rbx+8]
0x18002b7ac  call    cs:__imp_RtlAcquireSRWLockShared
0x18002b7b2  mov     r8, rsi
0x18002b7b5  mov     edx, ebp
0x18002b7b7  mov     rcx, rbx
0x18002b7ba  call    PsmpFindUserContext
0x18002b7bf  lea     rcx, [rbx+8]
0x18002b7c3  mov     rsi, rax
0x18002b7c6  call    cs:__imp_RtlReleaseSRWLockShared
0x18002b7cc  test    rsi, rsi
0x18002b7cf  jnz     short loc_18002B7DB
0x18002b7d1  mov     eax, 0C0000034h
0x18002b7d6  jmp     loc_18002B97A
0x18002b7db  mov     rbx, [rsp+58h+arg_20]
0x18002b7e3  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002b7e7  inc     r9
0x18002b7ea  cmp     [rbx+r9*2], r14w
0x18002b7ef  jnz     short loc_18002B7E7
0x18002b7f1  lea     r9, ds:2[r9*2]
0x18002b7f9  mov     r8, rbx
0x18002b7fc  mov     rdx, rsi
0x18002b7ff  xor     ecx, ecx
0x18002b801  call    PsmpFindApplication
0x18002b806  mov     rdi, rax
0x18002b809  test    rax, rax
0x18002b80c  jnz     loc_18002B8A7
0x18002b812  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b819  test    byte ptr [rcx+1Ch], 2
0x18002b81d  jz      short loc_18002B83F
0x18002b81f  cmp     byte ptr [rcx+19h], 2
0x18002b823  jb      short loc_18002B83F
0x18002b825  mov     rcx, [rcx+10h]
0x18002b829  lea     edx, [rax+1Bh]
0x18002b82c  mov     r9, rbx
0x18002b82f  mov     [rsp+58h+var_38], ebp
0x18002b833  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002b83a  call    WPP_SF_Sd
0x18002b83f  mov     rbx, [rsi+38h]
0x18002b843  lea     rcx, [rbx+8]
0x18002b847  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002b84d  xor     edx, edx
0x18002b84f  mov     rcx, rsi
0x18002b852  call    PsmpDereferenceObjectEx
0x18002b857  test    al, al
0x18002b859  jz      short loc_18002B898
0x18002b85b  lea     rax, [rsi+8]
0x18002b85f  mov     rdx, [rax]
0x18002b862  cmp     [rdx+8], rax
0x18002b866  jnz     loc_18002B946
0x18002b86c  mov     r8, [rax+8]
0x18002b870  cmp     [r8], rax
0x18002b873  jnz     loc_18002B946
0x18002b879  mov     [r8], rdx
0x18002b87c  mov     [rdx+8], r8
0x18002b880  mov     r8, rsi; P
0x18002b883  mov     rcx, gs:60h
0x18002b88c  xor     edx, edx; Flags
0x18002b88e  mov     rcx, [rcx+30h]; HeapHandle
0x18002b892  call    cs:__imp_RtlFreeHeap
0x18002b898  lea     rcx, [rbx+8]
0x18002b89c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002b8a2  jmp     loc_18002B7D1
0x18002b8a7  lea     rbx, [rax+148h]
0x18002b8ae  mov     rcx, rbx
0x18002b8b1  call    cs:__imp_RtlAcquireSRWLockShared
0x18002b8b7  mov     r9, [rsp+58h+arg_30]
0x18002b8bf  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002b8c3  mov     edx, [rsp+58h+arg_28]
0x18002b8ca  mov     rcx, rdi
0x18002b8cd  call    PsmpQuerySharedCommit
0x18002b8d2  mov     rcx, rbx
0x18002b8d5  mov     ebp, eax
0x18002b8d7  call    cs:__imp_RtlReleaseSRWLockShared
0x18002b8dd  xor     edx, edx
0x18002b8df  mov     rcx, rdi
0x18002b8e2  call    PsmpDereferenceApplicationEx
0x18002b8e7  mov     rbx, [rsi+38h]
0x18002b8eb  lea     rcx, [rbx+8]
0x18002b8ef  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002b8f5  xor     edx, edx
0x18002b8f7  mov     rcx, rsi
0x18002b8fa  call    PsmpDereferenceObjectEx
0x18002b8ff  test    al, al
0x18002b901  jz      short loc_18002B938
0x18002b903  lea     rax, [rsi+8]
0x18002b907  mov     rcx, [rax]
0x18002b90a  cmp     [rcx+8], rax
0x18002b90e  jnz     short loc_18002B946
0x18002b910  mov     rdx, [rax+8]
0x18002b914  cmp     [rdx], rax
0x18002b917  jnz     short loc_18002B946
0x18002b919  mov     [rdx], rcx
0x18002b91c  mov     r8, rsi; P
0x18002b91f  mov     [rcx+8], rdx
0x18002b923  xor     edx, edx; Flags
0x18002b925  mov     rcx, gs:60h
0x18002b92e  mov     rcx, [rcx+30h]; HeapHandle
0x18002b932  call    cs:__imp_RtlFreeHeap
0x18002b938  lea     rcx, [rbx+8]
0x18002b93c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002b942  mov     eax, ebp
0x18002b944  jmp     short loc_18002B97A
0x18002b946  mov     ecx, 3
0x18002b94b  int     29h; Win8: RtlFailFast(ecx)
0x18002b94d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b954  test    byte ptr [rcx+1Ch], 2
0x18002b958  jz      short loc_18002B975
0x18002b95a  cmp     byte ptr [rcx+19h], 2
0x18002b95e  jb      short loc_18002B975
0x18002b960  mov     rcx, [rcx+10h]
0x18002b964  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002b96b  mov     edx, 1Ah
0x18002b970  call    WPP_SF_
0x18002b975  mov     eax, 0C00000F1h
0x18002b97a  add     rsp, 30h
0x18002b97e  pop     r14
0x18002b980  pop     rdi
0x18002b981  pop     rsi
0x18002b982  pop     rbp
0x18002b983  pop     rbx
0x18002b984  retn
```
