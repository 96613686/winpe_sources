# PsmSrvResetMaxMemoryUsage

- ea: `0x18001aba0`
- end: `0x18001adc1`
- name: `PsmSrvResetMaxMemoryUsage`
- size: `545`
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
- `0x18001aba0`
- `0x18001adc8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001acd2`
- `ntdll!RtlFreeHeap` at `0x18001ad6e`
- `ntdll!RtlFreeHeap` at `0x18001acd2`
- `ntdll!RtlFreeHeap` at `0x18001ad6e`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001ac06`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001ac06`
- `ntdll!RtlLengthSid` at `0x18001abc2`
- `ntdll!RtlLengthSid` at `0x18001abc2`
- `ntdll!RtlValidSid` at `0x18001abd3`
- `ntdll!RtlValidSid` at `0x18001abd3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001ac87`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001acf1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001ad2b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001ac87`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001acf1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001ad2b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001acdc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001ad13`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001ad78`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001acdc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001ad13`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001ad78`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001abec`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001abec`

## pseudocode

```c
__int64 __fastcall PsmSrvResetMaxMemoryUsage(
        __int64 a1,
        unsigned int a2,
        void *a3,
        int a4,
        WCHAR *a5,
        unsigned int a6,
        __int64 a7)
{
  __int64 v10; // rbx
  __int64 *UserContext; // rsi
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v16; // r9
  _QWORD *Application; // rax
  __int64 v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // rdx
  __int64 **v21; // r8
  _QWORD *v22; // rbx
  unsigned int v23; // ebp
  __int64 v24; // rbx
  __int64 v25; // rcx
  __int64 **v26; // rdx

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
    v18 = (__int64)Application;
    if ( !Application )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
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
    RtlAcquireSRWLockExclusive(Application + 41);
    v23 = PsmpResetMaxMemoryUsage(v18, a6, a7);
    RtlReleaseSRWLockExclusive(v22);
    PsmpDereferenceApplicationEx(v18, 0);
    v24 = UserContext[7];
    RtlAcquireSRWLockExclusive(v24 + 8);
    if ( PsmpDereferenceObjectEx((volatile signed __int32 *)UserContext, 0) )
    {
      v25 = UserContext[1];
      if ( *(__int64 **)(v25 + 8) != UserContext + 1 )
        goto LABEL_22;
      v26 = (__int64 **)UserContext[2];
      if ( *v26 != UserContext + 1 )
        goto LABEL_22;
      *v26 = (__int64 *)v25;
      *(_QWORD *)(v25 + 8) = v26;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UserContext);
    }
    RtlReleaseSRWLockExclusive(v24 + 8);
    return v23;
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
    return 3221225713LL;
  }
}

```

## disassembly

```asm
0x18001aba0  push    rbx
0x18001aba2  push    rbp
0x18001aba3  push    rsi
0x18001aba4  push    rdi
0x18001aba5  push    r14
0x18001aba7  sub     rsp, 30h
0x18001abab  mov     ebp, r9d
0x18001abae  mov     rsi, r8
0x18001abb1  mov     ebx, edx
0x18001abb3  mov     rdi, rcx
0x18001abb6  cmp     edx, 2
0x18001abb9  jb      loc_18001AD89
0x18001abbf  mov     rcx, r8; Sid
0x18001abc2  call    cs:__imp_RtlLengthSid
0x18001abc8  cmp     eax, ebx
0x18001abca  jnz     loc_18001AD89
0x18001abd0  mov     rcx, rsi; Sid
0x18001abd3  call    cs:__imp_RtlValidSid
0x18001abd9  xor     r14d, r14d
0x18001abdc  test    al, al
0x18001abde  jz      loc_18001AD89
0x18001abe4  mov     rbx, [rdi+38h]
0x18001abe8  lea     rcx, [rbx+8]
0x18001abec  call    cs:__imp_RtlAcquireSRWLockShared
0x18001abf2  mov     r8, rsi
0x18001abf5  mov     edx, ebp
0x18001abf7  mov     rcx, rbx
0x18001abfa  call    PsmpFindUserContext
0x18001abff  lea     rcx, [rbx+8]
0x18001ac03  mov     rsi, rax
0x18001ac06  call    cs:__imp_RtlReleaseSRWLockShared
0x18001ac0c  test    rsi, rsi
0x18001ac0f  jnz     short loc_18001AC1B
0x18001ac11  mov     eax, 0C0000034h
0x18001ac16  jmp     loc_18001ADB6
0x18001ac1b  mov     rbx, [rsp+58h+arg_20]
0x18001ac23  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001ac27  inc     r9
0x18001ac2a  cmp     [rbx+r9*2], r14w
0x18001ac2f  jnz     short loc_18001AC27
0x18001ac31  lea     r9, ds:2[r9*2]
0x18001ac39  mov     r8, rbx
0x18001ac3c  mov     rdx, rsi
0x18001ac3f  xor     ecx, ecx
0x18001ac41  call    PsmpFindApplication
0x18001ac46  mov     rdi, rax
0x18001ac49  test    rax, rax
0x18001ac4c  jnz     loc_18001ACE7
0x18001ac52  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac59  test    byte ptr [rcx+1Ch], 2
0x18001ac5d  jz      short loc_18001AC7F
0x18001ac5f  cmp     byte ptr [rcx+19h], 2
0x18001ac63  jb      short loc_18001AC7F
0x18001ac65  mov     rcx, [rcx+10h]
0x18001ac69  lea     edx, [rax+23h]
0x18001ac6c  mov     r9, rbx
0x18001ac6f  mov     [rsp+58h+var_38], ebp
0x18001ac73  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18001ac7a  call    WPP_SF_Sd
0x18001ac7f  mov     rbx, [rsi+38h]
0x18001ac83  lea     rcx, [rbx+8]
0x18001ac87  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001ac8d  xor     edx, edx
0x18001ac8f  mov     rcx, rsi
0x18001ac92  call    PsmpDereferenceObjectEx
0x18001ac97  test    al, al
0x18001ac99  jz      short loc_18001ACD8
0x18001ac9b  lea     rax, [rsi+8]
0x18001ac9f  mov     rdx, [rax]
0x18001aca2  cmp     [rdx+8], rax
0x18001aca6  jnz     loc_18001AD82
0x18001acac  mov     r8, [rax+8]
0x18001acb0  cmp     [r8], rax
0x18001acb3  jnz     loc_18001AD82
0x18001acb9  mov     [r8], rdx
0x18001acbc  mov     [rdx+8], r8
0x18001acc0  mov     r8, rsi; P
0x18001acc3  mov     rcx, gs:60h
0x18001accc  xor     edx, edx; Flags
0x18001acce  mov     rcx, [rcx+30h]; HeapHandle
0x18001acd2  call    cs:__imp_RtlFreeHeap
0x18001acd8  lea     rcx, [rbx+8]
0x18001acdc  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001ace2  jmp     loc_18001AC11
0x18001ace7  lea     rbx, [rax+148h]
0x18001acee  mov     rcx, rbx
0x18001acf1  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001acf7  mov     r8, [rsp+58h+arg_30]
0x18001acff  mov     rcx, rdi
0x18001ad02  mov     edx, [rsp+58h+arg_28]
0x18001ad09  call    PsmpResetMaxMemoryUsage
0x18001ad0e  mov     rcx, rbx
0x18001ad11  mov     ebp, eax
0x18001ad13  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001ad19  xor     edx, edx
0x18001ad1b  mov     rcx, rdi
0x18001ad1e  call    PsmpDereferenceApplicationEx
0x18001ad23  mov     rbx, [rsi+38h]
0x18001ad27  lea     rcx, [rbx+8]
0x18001ad2b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001ad31  xor     edx, edx
0x18001ad33  mov     rcx, rsi
0x18001ad36  call    PsmpDereferenceObjectEx
0x18001ad3b  test    al, al
0x18001ad3d  jz      short loc_18001AD74
0x18001ad3f  lea     rax, [rsi+8]
0x18001ad43  mov     rcx, [rax]
0x18001ad46  cmp     [rcx+8], rax
0x18001ad4a  jnz     short loc_18001AD82
0x18001ad4c  mov     rdx, [rax+8]
0x18001ad50  cmp     [rdx], rax
0x18001ad53  jnz     short loc_18001AD82
0x18001ad55  mov     [rdx], rcx
0x18001ad58  mov     r8, rsi; P
0x18001ad5b  mov     [rcx+8], rdx
0x18001ad5f  xor     edx, edx; Flags
0x18001ad61  mov     rcx, gs:60h
0x18001ad6a  mov     rcx, [rcx+30h]; HeapHandle
0x18001ad6e  call    cs:__imp_RtlFreeHeap
0x18001ad74  lea     rcx, [rbx+8]
0x18001ad78  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001ad7e  mov     eax, ebp
0x18001ad80  jmp     short loc_18001ADB6
0x18001ad82  mov     ecx, 3
0x18001ad87  int     29h; Win8: RtlFailFast(ecx)
0x18001ad89  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad90  test    byte ptr [rcx+1Ch], 2
0x18001ad94  jz      short loc_18001ADB1
0x18001ad96  cmp     byte ptr [rcx+19h], 2
0x18001ad9a  jb      short loc_18001ADB1
0x18001ad9c  mov     rcx, [rcx+10h]
0x18001ada0  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18001ada7  mov     edx, 22h ; '"'
0x18001adac  call    WPP_SF_
0x18001adb1  mov     eax, 0C00000F1h
0x18001adb6  add     rsp, 30h
0x18001adba  pop     r14
0x18001adbc  pop     rdi
0x18001adbd  pop     rsi
0x18001adbe  pop     rbp
0x18001adbf  pop     rbx
0x18001adc0  retn
```
