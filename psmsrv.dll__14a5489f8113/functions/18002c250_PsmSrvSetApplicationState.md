# PsmSrvSetApplicationState

- ea: `0x18002c250`
- end: `0x18002c5c8`
- name: `PsmSrvSetApplicationState`
- size: `888`
- prototype: `__int64 __fastcall(__int64, unsigned int, void *, unsigned int, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800017b0`
- `0x1800093d0`
- `0x180009b40`
- `0x18000d010`
- `0x1800114d0`
- `0x180014f28`
- `0x1800156b4`
- `0x18001622c`
- `0x180017f60`
- `0x180017fa0`
- `0x18002c250`
- `0x18002c9e8`
- `0x18002cab8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002c452`
- `ntdll!RtlFreeHeap` at `0x18002c545`
- `ntdll!RtlFreeHeap` at `0x18002c452`
- `ntdll!RtlFreeHeap` at `0x18002c545`
- `ntdll!NtSetInformationThread` at `0x18002c361`
- `ntdll!NtSetInformationThread` at `0x18002c56f`
- `ntdll!NtSetInformationThread` at `0x18002c361`
- `ntdll!NtSetInformationThread` at `0x18002c56f`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002c389`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002c389`
- `ntdll!RtlLengthSid` at `0x18002c2a4`
- `ntdll!RtlLengthSid` at `0x18002c2a4`
- `ntdll!NtQueryInformationThread` at `0x18002c342`
- `ntdll!NtQueryInformationThread` at `0x18002c342`
- `ntdll!RtlValidSid` at `0x18002c2b5`
- `ntdll!RtlValidSid` at `0x18002c2b5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c407`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c502`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c407`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c502`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c45c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c54f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c45c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c54f`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002c36e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002c36e`

## pseudocode

```c
__int64 __fastcall PsmSrvSetApplicationState(
        __int64 a1,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6)
{
  __int64 v8; // rsi
  int v9; // ebx
  __int64 v10; // r9
  unsigned int v11; // r14d
  char v12; // r13
  _QWORD *UserContext; // rdi
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rsi
  __int64 v18; // r9
  __int64 Application; // rax
  int v20; // r8d
  __int64 v21; // r15
  __int64 v22; // rbx
  __int64 v23; // rdx
  _QWORD *v24; // r8
  int v25; // eax
  int v26; // edx
  int v27; // r8d
  __int64 v28; // rsi
  __int64 v29; // rcx
  _QWORD *v30; // rdx
  int v32; // [rsp+40h] [rbp-40h] BYREF
  __int64 v33; // [rsp+48h] [rbp-38h] BYREF
  _OWORD ThreadInformation[2]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v35; // [rsp+70h] [rbp-10h] BYREF
  int v36; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int v37; // [rsp+C8h] [rbp+48h] BYREF

  v32 = 0;
  v36 = 0;
  v37 = 0;
  v33 = 0;
  memset(ThreadInformation, 0, sizeof(ThreadInformation));
  v35 = 0;
  if ( a2 >= 2 )
  {
    v8 = *(_QWORD *)(a1 + 56);
    if ( RtlLengthSid(a3) == a2 )
    {
      if ( RtlValidSid(a3) )
      {
        v9 = PsmpConvertExternalApplicationState(a6, &v37);
        if ( v9 < 0 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids, v10);
          return (unsigned int)v9;
        }
        v11 = v37;
        v12 = 0;
        PsmpComputeStateChangeParameters(v37, &v32, &v33);
        if ( !v11
          && NtQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadBasicInformation, ThreadInformation, 0x30u, 0) >= 0 )
        {
          v36 = 10;
          NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadActualBasePriority, &v36, 4u);
          v12 = 1;
        }
        RtlAcquireSRWLockShared(v8 + 8);
        UserContext = (_QWORD *)PsmpFindUserContext(v8, a4, a3);
        RtlReleaseSRWLockShared(v8 + 8, v14, v15, v16);
        if ( !UserContext )
          goto LABEL_12;
        v17 = a5;
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)(a5 + 2 * v18) );
        Application = PsmpFindApplication(0, UserContext, a5, 2 * v18 + 2);
        v21 = Application;
        if ( !Application )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              45,
              (unsigned int)&WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids,
              v17,
              a4);
          v22 = UserContext[7];
          RtlAcquireSRWLockExclusive(v22 + 8);
          if ( !(unsigned __int8)PsmpDereferenceObjectEx(UserContext, 0) )
            goto LABEL_23;
          v23 = UserContext[1];
          if ( *(_QWORD **)(v23 + 8) == UserContext + 1 )
          {
            v24 = (_QWORD *)UserContext[2];
            if ( (_QWORD *)*v24 == UserContext + 1 )
            {
              *v24 = v23;
              *(_QWORD *)(v23 + 8) = v24;
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UserContext);
LABEL_23:
              RtlReleaseSRWLockExclusive(v22 + 8);
LABEL_12:
              v9 = -1073741772;
              goto LABEL_36;
            }
          }
LABEL_39:
          __fastfail(3u);
        }
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_iLS(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, v20, *(_QWORD *)(Application + 96), v11, v17);
        v25 = PsmpChangeApplicationState(v21, 0, v33, v11, v32, 0);
        v9 = v25;
        if ( v25 < 0 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_iDLSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, v27, *(_QWORD *)(v21 + 96), v25, v11, v17, a4);
        PsmpDereferenceApplicationEx(v21, 0);
        v28 = UserContext[7];
        RtlAcquireSRWLockExclusive(v28 + 8);
        if ( (unsigned __int8)PsmpDereferenceObjectEx(UserContext, 0) )
        {
          v29 = UserContext[1];
          if ( *(_QWORD **)(v29 + 8) != UserContext + 1 )
            goto LABEL_39;
          v30 = (_QWORD *)UserContext[2];
          if ( (_QWORD *)*v30 != UserContext + 1 )
            goto LABEL_39;
          *v30 = v29;
          *(_QWORD *)(v29 + 8) = v30;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UserContext);
        }
        RtlReleaseSRWLockExclusive(v28 + 8);
LABEL_36:
        if ( v12 )
          NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadBasePriority, (char *)&v35 + 12, 4u);
        return (unsigned int)v9;
      }
    }
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
  return 3221225713LL;
}

```

## disassembly

```asm
0x18002c250  mov     [rsp-38h+arg_10], rbx
0x18002c255  push    rbp
0x18002c256  push    rsi
0x18002c257  push    rdi
0x18002c258  push    r12
0x18002c25a  push    r13
0x18002c25c  push    r14
0x18002c25e  push    r15
0x18002c260  mov     rbp, rsp
0x18002c263  sub     rsp, 80h
0x18002c26a  xor     r15d, r15d
0x18002c26d  xorps   xmm0, xmm0
0x18002c270  mov     [rbp+var_40], r15d
0x18002c274  mov     r12d, r9d
0x18002c277  mov     [rbp+arg_0], r15d
0x18002c27b  mov     rdi, r8
0x18002c27e  mov     [rbp+arg_8], r15d
0x18002c282  mov     ebx, edx
0x18002c284  mov     [rbp+var_38], r15
0x18002c288  movups  [rbp+ThreadInformation], xmm0
0x18002c28c  movups  [rbp+var_20], xmm0
0x18002c290  movups  [rbp+var_10], xmm0
0x18002c294  cmp     edx, 2
0x18002c297  jb      loc_18002C580
0x18002c29d  mov     rsi, [rcx+38h]
0x18002c2a1  mov     rcx, r8; Sid
0x18002c2a4  call    cs:__imp_RtlLengthSid
0x18002c2aa  cmp     eax, ebx
0x18002c2ac  jnz     loc_18002C580
0x18002c2b2  mov     rcx, rdi; Sid
0x18002c2b5  call    cs:__imp_RtlValidSid
0x18002c2bb  test    al, al
0x18002c2bd  jz      loc_18002C580
0x18002c2c3  mov     r9d, [rbp+arg_28]
0x18002c2c7  lea     rdx, [rbp+arg_8]
0x18002c2cb  mov     ecx, r9d
0x18002c2ce  call    PsmpConvertExternalApplicationState
0x18002c2d3  mov     ebx, eax
0x18002c2d5  test    eax, eax
0x18002c2d7  jns     short loc_18002C30D
0x18002c2d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c2e0  test    byte ptr [rcx+1Ch], 2
0x18002c2e4  jz      loc_18002C575
0x18002c2ea  cmp     byte ptr [rcx+19h], 2
0x18002c2ee  jb      loc_18002C575
0x18002c2f4  mov     rcx, [rcx+10h]
0x18002c2f8  lea     edx, [r15+2Ch]
0x18002c2fc  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002c303  call    WPP_SF_d
0x18002c308  jmp     loc_18002C575
0x18002c30d  mov     r14d, [rbp+arg_8]
0x18002c311  lea     r8, [rbp+var_38]
0x18002c315  mov     ecx, r14d
0x18002c318  lea     rdx, [rbp+var_40]
0x18002c31c  mov     r13b, r15b
0x18002c31f  call    PsmpComputeStateChangeParameters
0x18002c324  mov     rbx, 0FFFFFFFFFFFFFFFEh
0x18002c32b  test    r14d, r14d
0x18002c32e  jnz     short loc_18002C36A
0x18002c330  lea     r9d, [r14+30h]; ThreadInformationLength
0x18002c334  mov     [rsp+80h+ReturnLength], r15; ReturnLength
0x18002c339  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x18002c33d  xor     edx, edx; ThreadInformationClass
0x18002c33f  mov     rcx, rbx; ThreadHandle
0x18002c342  call    cs:__imp_NtQueryInformationThread
0x18002c348  test    eax, eax
0x18002c34a  js      short loc_18002C36A
0x18002c34c  lea     r9d, [r14+4]; ThreadInformationLength
0x18002c350  mov     [rbp+arg_0], 0Ah
0x18002c357  lea     r8, [rbp+arg_0]; ThreadInformation
0x18002c35b  mov     rcx, rbx; ThreadHandle
0x18002c35e  lea     edx, [rbx+1Bh]; ThreadInformationClass
0x18002c361  call    cs:__imp_NtSetInformationThread
0x18002c367  mov     r13b, 1
0x18002c36a  lea     rcx, [rsi+8]
0x18002c36e  call    cs:__imp_RtlAcquireSRWLockShared
0x18002c374  mov     r8, rdi
0x18002c377  mov     edx, r12d
0x18002c37a  mov     rcx, rsi
0x18002c37d  call    PsmpFindUserContext
0x18002c382  lea     rcx, [rsi+8]
0x18002c386  mov     rdi, rax
0x18002c389  call    cs:__imp_RtlReleaseSRWLockShared
0x18002c38f  test    rdi, rdi
0x18002c392  jnz     short loc_18002C39E
0x18002c394  mov     ebx, 0C0000034h
0x18002c399  jmp     loc_18002C555
0x18002c39e  mov     rsi, [rbp+arg_20]
0x18002c3a2  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002c3a6  inc     r9
0x18002c3a9  cmp     [rsi+r9*2], r15w
0x18002c3ae  jnz     short loc_18002C3A6
0x18002c3b0  lea     r9, ds:2[r9*2]
0x18002c3b8  mov     r8, rsi
0x18002c3bb  mov     rdx, rdi
0x18002c3be  xor     ecx, ecx
0x18002c3c0  call    PsmpFindApplication
0x18002c3c5  mov     r15, rax
0x18002c3c8  test    rax, rax
0x18002c3cb  jnz     loc_18002C467
0x18002c3d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c3d8  test    byte ptr [rcx+1Ch], 2
0x18002c3dc  jz      short loc_18002C3FF
0x18002c3de  cmp     byte ptr [rcx+19h], 2
0x18002c3e2  jb      short loc_18002C3FF
0x18002c3e4  mov     rcx, [rcx+10h]
0x18002c3e8  lea     edx, [rax+2Dh]
0x18002c3eb  mov     r9, rsi
0x18002c3ee  mov     dword ptr [rsp+80h+ReturnLength], r12d
0x18002c3f3  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002c3fa  call    WPP_SF_Sd
0x18002c3ff  mov     rbx, [rdi+38h]
0x18002c403  lea     rcx, [rbx+8]
0x18002c407  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002c40d  xor     edx, edx
0x18002c40f  mov     rcx, rdi
0x18002c412  call    PsmpDereferenceObjectEx
0x18002c417  test    al, al
0x18002c419  jz      short loc_18002C458
0x18002c41b  lea     rax, [rdi+8]
0x18002c41f  mov     rdx, [rax]
0x18002c422  cmp     [rdx+8], rax
0x18002c426  jnz     loc_18002C579
0x18002c42c  mov     r8, [rax+8]
0x18002c430  cmp     [r8], rax
0x18002c433  jnz     loc_18002C579
0x18002c439  mov     [r8], rdx
0x18002c43c  mov     [rdx+8], r8
0x18002c440  mov     r8, rdi; P
0x18002c443  mov     rcx, gs:60h
0x18002c44c  xor     edx, edx; Flags
0x18002c44e  mov     rcx, [rcx+30h]; HeapHandle
0x18002c452  call    cs:__imp_RtlFreeHeap
0x18002c458  lea     rcx, [rbx+8]
0x18002c45c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002c462  jmp     loc_18002C394
0x18002c467  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c46e  test    byte ptr [rcx+1Ch], 2
0x18002c472  jz      short loc_18002C496
0x18002c474  cmp     byte ptr [rcx+19h], 4
0x18002c478  jb      short loc_18002C496
0x18002c47a  mov     r9, [rax+60h]
0x18002c47e  mov     edx, 2Eh ; '.'
0x18002c483  mov     rcx, [rcx+10h]
0x18002c487  mov     [rsp+80h+var_58], rsi
0x18002c48c  mov     dword ptr [rsp+80h+ReturnLength], r14d
0x18002c491  call    WPP_SF_iLS
0x18002c496  mov     eax, [rbp+var_40]
0x18002c499  mov     r9d, r14d
0x18002c49c  mov     r8, [rbp+var_38]
0x18002c4a0  xor     edx, edx
0x18002c4a2  mov     [rsp+80h+var_58], 0
0x18002c4ab  mov     rcx, r15
0x18002c4ae  mov     dword ptr [rsp+80h+ReturnLength], eax
0x18002c4b2  call    PsmpChangeApplicationState
0x18002c4b7  mov     ebx, eax
0x18002c4b9  test    eax, eax
0x18002c4bb  jns     short loc_18002C4F0
0x18002c4bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4c4  test    byte ptr [rcx+1Ch], 2
0x18002c4c8  jz      short loc_18002C4F0
0x18002c4ca  cmp     byte ptr [rcx+19h], 2
0x18002c4ce  jb      short loc_18002C4F0
0x18002c4d0  mov     r9, [r15+60h]
0x18002c4d4  mov     rcx, [rcx+10h]
0x18002c4d8  mov     [rsp+80h+var_48], r12d
0x18002c4dd  mov     [rsp+80h+var_50], rsi
0x18002c4e2  mov     dword ptr [rsp+80h+var_58], r14d
0x18002c4e7  mov     dword ptr [rsp+80h+ReturnLength], eax
0x18002c4eb  call    WPP_SF_iDLSd
0x18002c4f0  xor     edx, edx
0x18002c4f2  mov     rcx, r15
0x18002c4f5  call    PsmpDereferenceApplicationEx
0x18002c4fa  mov     rsi, [rdi+38h]
0x18002c4fe  lea     rcx, [rsi+8]
0x18002c502  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002c508  xor     edx, edx
0x18002c50a  mov     rcx, rdi
0x18002c50d  call    PsmpDereferenceObjectEx
0x18002c512  test    al, al
0x18002c514  jz      short loc_18002C54B
0x18002c516  lea     rax, [rdi+8]
0x18002c51a  mov     rcx, [rax]
0x18002c51d  cmp     [rcx+8], rax
0x18002c521  jnz     short loc_18002C579
0x18002c523  mov     rdx, [rax+8]
0x18002c527  cmp     [rdx], rax
0x18002c52a  jnz     short loc_18002C579
0x18002c52c  mov     [rdx], rcx
0x18002c52f  mov     r8, rdi; P
0x18002c532  mov     [rcx+8], rdx
0x18002c536  xor     edx, edx; Flags
0x18002c538  mov     rcx, gs:60h
0x18002c541  mov     rcx, [rcx+30h]; HeapHandle
0x18002c545  call    cs:__imp_RtlFreeHeap
0x18002c54b  lea     rcx, [rsi+8]
0x18002c54f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002c555  test    r13b, r13b
0x18002c558  jz      short loc_18002C575
0x18002c55a  mov     r9d, 4; ThreadInformationLength
0x18002c560  lea     r8, [rbp+var_10+0Ch]; ThreadInformation
0x18002c564  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18002c56b  lea     edx, [r9-1]; ThreadInformationClass
0x18002c56f  call    cs:__imp_NtSetInformationThread
0x18002c575  mov     eax, ebx
0x18002c577  jmp     short loc_18002C5AD
0x18002c579  mov     ecx, 3
0x18002c57e  int     29h; Win8: RtlFailFast(ecx)
0x18002c580  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c587  test    byte ptr [rcx+1Ch], 2
0x18002c58b  jz      short loc_18002C5A8
0x18002c58d  cmp     byte ptr [rcx+19h], 2
0x18002c591  jb      short loc_18002C5A8
0x18002c593  mov     rcx, [rcx+10h]
0x18002c597  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002c59e  mov     edx, 2Bh ; '+'
0x18002c5a3  call    WPP_SF_
0x18002c5a8  mov     eax, 0C00000F1h
0x18002c5ad  mov     rbx, [rsp+80h+arg_10]
0x18002c5b5  add     rsp, 80h
0x18002c5bc  pop     r15
0x18002c5be  pop     r14
0x18002c5c0  pop     r13
0x18002c5c2  pop     r12
0x18002c5c4  pop     rdi
0x18002c5c5  pop     rsi
0x18002c5c6  pop     rbp
0x18002c5c7  retn
```
