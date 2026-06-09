# PsmSrvQueryApplicationResourceUsage

- ea: `0x18002abe0`
- end: `0x18002ae5a`
- name: `PsmSrvQueryApplicationResourceUsage`
- size: `634`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800017b0`
- `0x18000772c`
- `0x180007bb0`
- `0x1800093d0`
- `0x180009b40`
- `0x18000d010`
- `0x18001622c`
- `0x180017fa0`
- `0x18001c10c`
- `0x18002abe0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002ad68`
- `ntdll!RtlFreeHeap` at `0x18002adfc`
- `ntdll!RtlFreeHeap` at `0x18002ad68`
- `ntdll!RtlFreeHeap` at `0x18002adfc`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002ac9c`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002ac9c`
- `ntdll!RtlLengthSid` at `0x18002ac17`
- `ntdll!RtlLengthSid` at `0x18002ac17`
- `ntdll!RtlValidSid` at `0x18002ac28`
- `ntdll!RtlValidSid` at `0x18002ac28`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002ad1d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002adb9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002ad1d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002adb9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002ad72`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002ae06`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002ad72`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002ae06`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002ac83`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002ac83`

## pseudocode

```c
__int64 __fastcall PsmSrvQueryApplicationResourceUsage(
        __int64 a1,
        unsigned int a2,
        void *a3,
        int a4,
        WCHAR *a5,
        _QWORD *a6)
{
  __int64 v11; // rbx
  __int64 *UserContext; // rax
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // r9
  _QWORD *Application; // rax
  __int64 v20; // rsi
  __int64 v21; // rdi
  __int64 v22; // rdx
  _QWORD *v23; // r8
  __int64 v24; // rdi
  __int64 v25; // rcx
  _QWORD *v26; // rdx
  _QWORD v27[17]; // [rsp+30h] [rbp-88h] BYREF

  memset_0(v27, 0, 0x50u);
  if ( a2 >= 2 && RtlLengthSid(a3) == a2 && RtlValidSid(a3) )
  {
    if ( !a6 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
      return 3221225716LL;
    }
    v11 = *(_QWORD *)(a1 + 56);
    RtlAcquireSRWLockShared(v11 + 8);
    UserContext = PsmpFindUserContext(v11, a4, a3);
    v13 = v11 + 8;
    v14 = (__int64)UserContext;
    RtlReleaseSRWLockShared(v13, v15, v16, v17);
    if ( !v14 )
      return 3221225524LL;
    v18 = -1;
    do
      ++v18;
    while ( a5[v18] );
    Application = PsmpFindApplication(0, v14, a5, 2 * v18 + 2);
    v20 = (__int64)Application;
    if ( !Application )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          (unsigned int)&WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids,
          (_DWORD)a5,
          a4);
      v21 = *(_QWORD *)(v14 + 56);
      RtlAcquireSRWLockExclusive(v21 + 8);
      if ( !PsmpDereferenceObjectEx((volatile signed __int32 *)v14, 0) )
        goto LABEL_21;
      v22 = *(_QWORD *)(v14 + 8);
      if ( *(_QWORD *)(v22 + 8) == v14 + 8 )
      {
        v23 = *(_QWORD **)(v14 + 16);
        if ( *v23 == v14 + 8 )
        {
          *v23 = v22;
          *(_QWORD *)(v22 + 8) = v23;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v14);
LABEL_21:
          RtlReleaseSRWLockExclusive(v21 + 8);
          return 3221225524LL;
        }
      }
LABEL_27:
      __fastfail(3u);
    }
    PsmpQueryAppResourceUsage(Application, 6, Application[849], v27);
    *a6 = v27[0];
    a6[1] = v27[1];
    PsmpDereferenceApplicationEx(v20, 0);
    v24 = *(_QWORD *)(v14 + 56);
    RtlAcquireSRWLockExclusive(v24 + 8);
    if ( PsmpDereferenceObjectEx((volatile signed __int32 *)v14, 0) )
    {
      v25 = *(_QWORD *)(v14 + 8);
      if ( *(_QWORD *)(v25 + 8) != v14 + 8 )
        goto LABEL_27;
      v26 = *(_QWORD **)(v14 + 16);
      if ( *v26 != v14 + 8 )
        goto LABEL_27;
      *v26 = v25;
      *(_QWORD *)(v25 + 8) = v26;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v14);
    }
    RtlReleaseSRWLockExclusive(v24 + 8);
    return PsmpQueryVolumeIoTimes(a6);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
  return 3221225713LL;
}

```

## disassembly

```asm
0x18002abe0  push    rbx
0x18002abe2  push    rbp
0x18002abe3  push    rsi
0x18002abe4  push    rdi
0x18002abe5  push    r12
0x18002abe7  push    r14
0x18002abe9  sub     rsp, 88h
0x18002abf0  mov     ebx, edx
0x18002abf2  mov     rsi, r8
0x18002abf5  xor     edx, edx; Val
0x18002abf7  mov     rdi, rcx
0x18002abfa  lea     rcx, [rsp+0B8h+var_88]; void *
0x18002abff  mov     ebp, r9d
0x18002ac02  lea     r8d, [rdx+50h]; Size
0x18002ac06  call    memset_0
0x18002ac0b  cmp     ebx, 2
0x18002ac0e  jb      loc_18002AE1D
0x18002ac14  mov     rcx, rsi; Sid
0x18002ac17  call    cs:__imp_RtlLengthSid
0x18002ac1d  cmp     eax, ebx
0x18002ac1f  jnz     loc_18002AE1D
0x18002ac25  mov     rcx, rsi; Sid
0x18002ac28  call    cs:__imp_RtlValidSid
0x18002ac2e  xor     r12d, r12d
0x18002ac31  test    al, al
0x18002ac33  jz      loc_18002AE1D
0x18002ac39  mov     r14, [rsp+0B8h+arg_28]
0x18002ac41  test    r14, r14
0x18002ac44  jnz     short loc_18002AC78
0x18002ac46  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac4d  test    byte ptr [rcx+1Ch], 2
0x18002ac51  jz      short loc_18002AC6E
0x18002ac53  cmp     byte ptr [rcx+19h], 2
0x18002ac57  jb      short loc_18002AC6E
0x18002ac59  mov     rcx, [rcx+10h]
0x18002ac5d  lea     edx, [r12+11h]
0x18002ac62  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002ac69  call    WPP_SF_
0x18002ac6e  mov     eax, 0C00000F4h
0x18002ac73  jmp     loc_18002AE4A
0x18002ac78  mov     rbx, [rdi+38h]
0x18002ac7c  lea     rdi, [rbx+8]
0x18002ac80  mov     rcx, rdi
0x18002ac83  call    cs:__imp_RtlAcquireSRWLockShared
0x18002ac89  mov     r8, rsi
0x18002ac8c  mov     edx, ebp
0x18002ac8e  mov     rcx, rbx
0x18002ac91  call    PsmpFindUserContext
0x18002ac96  mov     rcx, rdi
0x18002ac99  mov     rbx, rax
0x18002ac9c  call    cs:__imp_RtlReleaseSRWLockShared
0x18002aca2  test    rbx, rbx
0x18002aca5  jnz     short loc_18002ACB1
0x18002aca7  mov     eax, 0C0000034h
0x18002acac  jmp     loc_18002AE4A
0x18002acb1  mov     rdi, [rsp+0B8h+arg_20]
0x18002acb9  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002acbd  inc     r9
0x18002acc0  cmp     [rdi+r9*2], r12w
0x18002acc5  jnz     short loc_18002ACBD
0x18002acc7  lea     r9, ds:2[r9*2]
0x18002accf  mov     r8, rdi
0x18002acd2  mov     rdx, rbx
0x18002acd5  xor     ecx, ecx
0x18002acd7  call    PsmpFindApplication
0x18002acdc  mov     rsi, rax
0x18002acdf  test    rax, rax
0x18002ace2  jnz     loc_18002AD7D
0x18002ace8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002acef  test    byte ptr [rcx+1Ch], 2
0x18002acf3  jz      short loc_18002AD15
0x18002acf5  cmp     byte ptr [rcx+19h], 2
0x18002acf9  jb      short loc_18002AD15
0x18002acfb  mov     rcx, [rcx+10h]
0x18002acff  lea     edx, [rax+12h]
0x18002ad02  mov     r9, rdi
0x18002ad05  mov     [rsp+0B8h+var_98], ebp
0x18002ad09  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002ad10  call    WPP_SF_Sd
0x18002ad15  mov     rdi, [rbx+38h]
0x18002ad19  lea     rcx, [rdi+8]
0x18002ad1d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002ad23  xor     edx, edx
0x18002ad25  mov     rcx, rbx
0x18002ad28  call    PsmpDereferenceObjectEx
0x18002ad2d  test    al, al
0x18002ad2f  jz      short loc_18002AD6E
0x18002ad31  lea     rax, [rbx+8]
0x18002ad35  mov     rdx, [rax]
0x18002ad38  cmp     [rdx+8], rax
0x18002ad3c  jnz     loc_18002AE16
0x18002ad42  mov     r8, [rax+8]
0x18002ad46  cmp     [r8], rax
0x18002ad49  jnz     loc_18002AE16
0x18002ad4f  mov     [r8], rdx
0x18002ad52  mov     [rdx+8], r8
0x18002ad56  mov     r8, rbx; P
0x18002ad59  mov     rcx, gs:60h
0x18002ad62  xor     edx, edx; Flags
0x18002ad64  mov     rcx, [rcx+30h]; HeapHandle
0x18002ad68  call    cs:__imp_RtlFreeHeap
0x18002ad6e  lea     rcx, [rdi+8]
0x18002ad72  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002ad78  jmp     loc_18002ACA7
0x18002ad7d  mov     r8, [rax+1A88h]
0x18002ad84  lea     r9, [rsp+0B8h+var_88]
0x18002ad89  mov     edx, 6
0x18002ad8e  mov     rcx, rsi
0x18002ad91  call    PsmpQueryAppResourceUsage
0x18002ad96  mov     rax, [rsp+0B8h+var_88]
0x18002ad9b  xor     edx, edx
0x18002ad9d  mov     [r14], rax
0x18002ada0  mov     rcx, rsi
0x18002ada3  mov     rax, [rsp+0B8h+var_80]
0x18002ada8  mov     [r14+8], rax
0x18002adac  call    PsmpDereferenceApplicationEx
0x18002adb1  mov     rdi, [rbx+38h]
0x18002adb5  lea     rcx, [rdi+8]
0x18002adb9  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002adbf  xor     edx, edx
0x18002adc1  mov     rcx, rbx
0x18002adc4  call    PsmpDereferenceObjectEx
0x18002adc9  test    al, al
0x18002adcb  jz      short loc_18002AE02
0x18002adcd  lea     rax, [rbx+8]
0x18002add1  mov     rcx, [rax]
0x18002add4  cmp     [rcx+8], rax
0x18002add8  jnz     short loc_18002AE16
0x18002adda  mov     rdx, [rax+8]
0x18002adde  cmp     [rdx], rax
0x18002ade1  jnz     short loc_18002AE16
0x18002ade3  mov     [rdx], rcx
0x18002ade6  mov     r8, rbx; P
0x18002ade9  mov     [rcx+8], rdx
0x18002aded  xor     edx, edx; Flags
0x18002adef  mov     rcx, gs:60h
0x18002adf8  mov     rcx, [rcx+30h]; HeapHandle
0x18002adfc  call    cs:__imp_RtlFreeHeap
0x18002ae02  lea     rcx, [rdi+8]
0x18002ae06  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002ae0c  mov     rcx, r14
0x18002ae0f  call    PsmpQueryVolumeIoTimes
0x18002ae14  jmp     short loc_18002AE4A
0x18002ae16  mov     ecx, 3
0x18002ae1b  int     29h; Win8: RtlFailFast(ecx)
0x18002ae1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae24  test    byte ptr [rcx+1Ch], 2
0x18002ae28  jz      short loc_18002AE45
0x18002ae2a  cmp     byte ptr [rcx+19h], 2
0x18002ae2e  jb      short loc_18002AE45
0x18002ae30  mov     rcx, [rcx+10h]
0x18002ae34  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002ae3b  mov     edx, 10h
0x18002ae40  call    WPP_SF_
0x18002ae45  mov     eax, 0C00000F1h
0x18002ae4a  add     rsp, 88h
0x18002ae51  pop     r14
0x18002ae53  pop     r12
0x18002ae55  pop     rdi
0x18002ae56  pop     rsi
0x18002ae57  pop     rbp
0x18002ae58  pop     rbx
0x18002ae59  retn
```
