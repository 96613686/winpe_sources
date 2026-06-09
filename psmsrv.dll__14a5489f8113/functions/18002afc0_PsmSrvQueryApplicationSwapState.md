# PsmSrvQueryApplicationSwapState

- ea: `0x18002afc0`
- end: `0x18002b1f9`
- name: `PsmSrvQueryApplicationSwapState`
- size: `569`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800017b0`
- `0x1800093d0`
- `0x180009b40`
- `0x18000d010`
- `0x18001622c`
- `0x180017fa0`
- `0x18002afc0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002b0f4`
- `ntdll!RtlFreeHeap` at `0x18002b1a6`
- `ntdll!RtlFreeHeap` at `0x18002b0f4`
- `ntdll!RtlFreeHeap` at `0x18002b1a6`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002b028`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002b14b`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002b028`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002b14b`
- `ntdll!RtlLengthSid` at `0x18002afe2`
- `ntdll!RtlLengthSid` at `0x18002afe2`
- `ntdll!RtlValidSid` at `0x18002aff3`
- `ntdll!RtlValidSid` at `0x18002aff3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b0a9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b163`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b0a9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b163`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b0fe`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b1b0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b0fe`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b1b0`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002b00f`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002b11e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002b00f`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002b11e`

## pseudocode

```c
__int64 __fastcall PsmSrvQueryApplicationSwapState(
        __int64 a1,
        unsigned int a2,
        void *a3,
        int a4,
        WCHAR *a5,
        _DWORD *a6)
{
  __int64 v9; // rbx
  __int64 *UserContext; // rax
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v17; // r9
  _QWORD *Application; // rax
  __int64 v19; // rdi
  __int64 v20; // rdi
  __int64 v21; // rdx
  _QWORD *v22; // r8
  _QWORD *v23; // rbp
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rdi
  __int64 v28; // rcx
  _QWORD *v29; // rdx

  if ( a2 >= 2 && RtlLengthSid(a3) == a2 && RtlValidSid(a3) )
  {
    v9 = *(_QWORD *)(a1 + 56);
    RtlAcquireSRWLockShared(v9 + 8);
    UserContext = PsmpFindUserContext(v9, a4, a3);
    v11 = v9 + 8;
    v12 = (__int64)UserContext;
    RtlReleaseSRWLockShared(v11, v13, v14, v15);
    if ( !v12 )
      return 3221225524LL;
    v17 = -1;
    do
      ++v17;
    while ( a5[v17] );
    Application = PsmpFindApplication(0, v12, a5, 2 * v17 + 2);
    v19 = (__int64)Application;
    if ( !Application )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)&WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids,
          (_DWORD)a5,
          a4);
      v20 = *(_QWORD *)(v12 + 56);
      RtlAcquireSRWLockExclusive(v20 + 8);
      if ( !PsmpDereferenceObjectEx((volatile signed __int32 *)v12, 0) )
        goto LABEL_16;
      v21 = *(_QWORD *)(v12 + 8);
      if ( *(_QWORD *)(v21 + 8) == v12 + 8 )
      {
        v22 = *(_QWORD **)(v12 + 16);
        if ( *v22 == v12 + 8 )
        {
          *v22 = v21;
          *(_QWORD *)(v21 + 8) = v22;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v12);
LABEL_16:
          RtlReleaseSRWLockExclusive(v20 + 8);
          return 3221225524LL;
        }
      }
LABEL_26:
      __fastfail(3u);
    }
    v23 = Application + 41;
    *a6 = 0;
    RtlAcquireSRWLockShared(Application + 41);
    v26 = *(unsigned int *)(v19 + 344);
    if ( (((_DWORD)v26 - 1) & 0xFFFFFFFC) == 0 && (_DWORD)v26 != 3 && (*(_BYTE *)(v19 + 132) & 0x60) != 0 )
      *a6 = 3;
    RtlReleaseSRWLockShared(v23, v26, v24, v25);
    PsmpDereferenceApplicationEx(v19, 0);
    v27 = *(_QWORD *)(v12 + 56);
    RtlAcquireSRWLockExclusive(v27 + 8);
    if ( PsmpDereferenceObjectEx((volatile signed __int32 *)v12, 0) )
    {
      v28 = *(_QWORD *)(v12 + 8);
      if ( *(_QWORD *)(v28 + 8) != v12 + 8 )
        goto LABEL_26;
      v29 = *(_QWORD **)(v12 + 16);
      if ( *v29 != v12 + 8 )
        goto LABEL_26;
      *v29 = v28;
      *(_QWORD *)(v28 + 8) = v29;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v12);
    }
    RtlReleaseSRWLockExclusive(v27 + 8);
    return 0;
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
    return 3221225713LL;
  }
}

```

## disassembly

```asm
0x18002afc0  push    rbx
0x18002afc2  push    rbp
0x18002afc3  push    rsi
0x18002afc4  push    rdi
0x18002afc5  push    r14
0x18002afc7  sub     rsp, 30h
0x18002afcb  mov     ebp, r9d
0x18002afce  mov     rsi, r8
0x18002afd1  mov     ebx, edx
0x18002afd3  mov     rdi, rcx
0x18002afd6  cmp     edx, 2
0x18002afd9  jb      loc_18002B1C1
0x18002afdf  mov     rcx, r8; Sid
0x18002afe2  call    cs:__imp_RtlLengthSid
0x18002afe8  cmp     eax, ebx
0x18002afea  jnz     loc_18002B1C1
0x18002aff0  mov     rcx, rsi; Sid
0x18002aff3  call    cs:__imp_RtlValidSid
0x18002aff9  xor     r14d, r14d
0x18002affc  test    al, al
0x18002affe  jz      loc_18002B1C1
0x18002b004  mov     rbx, [rdi+38h]
0x18002b008  lea     rdi, [rbx+8]
0x18002b00c  mov     rcx, rdi
0x18002b00f  call    cs:__imp_RtlAcquireSRWLockShared
0x18002b015  mov     r8, rsi
0x18002b018  mov     edx, ebp
0x18002b01a  mov     rcx, rbx
0x18002b01d  call    PsmpFindUserContext
0x18002b022  mov     rcx, rdi
0x18002b025  mov     rbx, rax
0x18002b028  call    cs:__imp_RtlReleaseSRWLockShared
0x18002b02e  test    rbx, rbx
0x18002b031  jnz     short loc_18002B03D
0x18002b033  mov     eax, 0C0000034h
0x18002b038  jmp     loc_18002B1EE
0x18002b03d  mov     rsi, [rsp+58h+arg_20]
0x18002b045  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002b049  inc     r9
0x18002b04c  cmp     [rsi+r9*2], r14w
0x18002b051  jnz     short loc_18002B049
0x18002b053  lea     r9, ds:2[r9*2]
0x18002b05b  mov     r8, rsi
0x18002b05e  mov     rdx, rbx
0x18002b061  xor     ecx, ecx
0x18002b063  call    PsmpFindApplication
0x18002b068  mov     rdi, rax
0x18002b06b  test    rax, rax
0x18002b06e  jnz     loc_18002B109
0x18002b074  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b07b  test    byte ptr [rcx+1Ch], 2
0x18002b07f  jz      short loc_18002B0A1
0x18002b081  cmp     byte ptr [rcx+19h], 2
0x18002b085  jb      short loc_18002B0A1
0x18002b087  mov     rcx, [rcx+10h]
0x18002b08b  lea     edx, [rax+16h]
0x18002b08e  mov     r9, rsi
0x18002b091  mov     [rsp+58h+var_38], ebp
0x18002b095  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002b09c  call    WPP_SF_Sd
0x18002b0a1  mov     rdi, [rbx+38h]
0x18002b0a5  lea     rcx, [rdi+8]
0x18002b0a9  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002b0af  xor     edx, edx
0x18002b0b1  mov     rcx, rbx
0x18002b0b4  call    PsmpDereferenceObjectEx
0x18002b0b9  test    al, al
0x18002b0bb  jz      short loc_18002B0FA
0x18002b0bd  lea     rax, [rbx+8]
0x18002b0c1  mov     rdx, [rax]
0x18002b0c4  cmp     [rdx+8], rax
0x18002b0c8  jnz     loc_18002B1BA
0x18002b0ce  mov     r8, [rax+8]
0x18002b0d2  cmp     [r8], rax
0x18002b0d5  jnz     loc_18002B1BA
0x18002b0db  mov     [r8], rdx
0x18002b0de  mov     [rdx+8], r8
0x18002b0e2  mov     r8, rbx; P
0x18002b0e5  mov     rcx, gs:60h
0x18002b0ee  xor     edx, edx; Flags
0x18002b0f0  mov     rcx, [rcx+30h]; HeapHandle
0x18002b0f4  call    cs:__imp_RtlFreeHeap
0x18002b0fa  lea     rcx, [rdi+8]
0x18002b0fe  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002b104  jmp     loc_18002B033
0x18002b109  mov     rsi, [rsp+58h+arg_28]
0x18002b111  lea     rbp, [rax+148h]
0x18002b118  mov     rcx, rbp
0x18002b11b  mov     [rsi], r14d
0x18002b11e  call    cs:__imp_RtlAcquireSRWLockShared
0x18002b124  mov     edx, [rdi+158h]
0x18002b12a  lea     eax, [rdx-1]
0x18002b12d  test    eax, 0FFFFFFFCh
0x18002b132  jnz     short loc_18002B148
0x18002b134  cmp     edx, 3
0x18002b137  jz      short loc_18002B148
0x18002b139  test    byte ptr [rdi+84h], 60h
0x18002b140  jz      short loc_18002B148
0x18002b142  mov     dword ptr [rsi], 3
0x18002b148  mov     rcx, rbp
0x18002b14b  call    cs:__imp_RtlReleaseSRWLockShared
0x18002b151  xor     edx, edx
0x18002b153  mov     rcx, rdi
0x18002b156  call    PsmpDereferenceApplicationEx
0x18002b15b  mov     rdi, [rbx+38h]
0x18002b15f  lea     rcx, [rdi+8]
0x18002b163  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002b169  xor     edx, edx
0x18002b16b  mov     rcx, rbx
0x18002b16e  call    PsmpDereferenceObjectEx
0x18002b173  test    al, al
0x18002b175  jz      short loc_18002B1AC
0x18002b177  lea     rax, [rbx+8]
0x18002b17b  mov     rcx, [rax]
0x18002b17e  cmp     [rcx+8], rax
0x18002b182  jnz     short loc_18002B1BA
0x18002b184  mov     rdx, [rax+8]
0x18002b188  cmp     [rdx], rax
0x18002b18b  jnz     short loc_18002B1BA
0x18002b18d  mov     [rdx], rcx
0x18002b190  mov     r8, rbx; P
0x18002b193  mov     [rcx+8], rdx
0x18002b197  xor     edx, edx; Flags
0x18002b199  mov     rcx, gs:60h
0x18002b1a2  mov     rcx, [rcx+30h]; HeapHandle
0x18002b1a6  call    cs:__imp_RtlFreeHeap
0x18002b1ac  lea     rcx, [rdi+8]
0x18002b1b0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002b1b6  xor     eax, eax
0x18002b1b8  jmp     short loc_18002B1EE
0x18002b1ba  mov     ecx, 3
0x18002b1bf  int     29h; Win8: RtlFailFast(ecx)
0x18002b1c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1c8  test    byte ptr [rcx+1Ch], 2
0x18002b1cc  jz      short loc_18002B1E9
0x18002b1ce  cmp     byte ptr [rcx+19h], 2
0x18002b1d2  jb      short loc_18002B1E9
0x18002b1d4  mov     rcx, [rcx+10h]
0x18002b1d8  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002b1df  mov     edx, 15h
0x18002b1e4  call    WPP_SF_
0x18002b1e9  mov     eax, 0C00000F1h
0x18002b1ee  add     rsp, 30h
0x18002b1f2  pop     r14
0x18002b1f4  pop     rdi
0x18002b1f5  pop     rsi
0x18002b1f6  pop     rbp
0x18002b1f7  pop     rbx
0x18002b1f8  retn
```
