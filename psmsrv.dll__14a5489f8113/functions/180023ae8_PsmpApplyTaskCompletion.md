# PsmpApplyTaskCompletion

- ea: `0x180023ae8`
- end: `0x180023deb`
- name: `PsmpApplyTaskCompletion`
- size: `771`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a250`

## callees

- `0x180003ec8`
- `0x180004170`
- `0x180008cc0`
- `0x180009b40`
- `0x180019bfc`
- `0x18001b7e0`
- `0x18001c10c`
- `0x180022640`
- `0x18002377c`
- `0x1800238b0`
- `0x180023ae8`
- `0x180023ebc`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180023d18`
- `ntdll!RtlFreeHeap` at `0x180023d18`
- `ntdll!TpSetWait` at `0x180023d7a`
- `ntdll!TpSetWait` at `0x180023d7a`
- `ntdll!NtClose` at `0x180023db9`
- `ntdll!NtClose` at `0x180023db9`
- `ntdll!TpAllocWait` at `0x180023cfa`
- `ntdll!TpAllocWait` at `0x180023cfa`
- `ntdll!NtQueryInformationProcess` at `0x180023b74`
- `ntdll!NtQueryInformationProcess` at `0x180023b74`
- `ntdll!RtlInitializeSRWLock` at `0x180023d2f`
- `ntdll!RtlInitializeSRWLock` at `0x180023d2f`
- `ntdll!RtlAllocateHeap` at `0x180023cc6`
- `ntdll!RtlAllocateHeap` at `0x180023cc6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180023c20`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180023c20`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180023c35`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180023c35`

## pseudocode

```c
__int64 __fastcall PsmpApplyTaskCompletion(__int64 a1, void *a2, unsigned int a3, char a4)
{
  int InformationProcess; // edi
  __int64 v9; // r8
  unsigned int v10; // r15d
  _QWORD *v11; // r14
  _QWORD *i; // rax
  unsigned int *v13; // rbx
  char v14; // si
  __int64 v15; // rsi
  unsigned int *Heap; // rax
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD ProcessInformation[3]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v25[29]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE Sid2[72]; // [rsp+258h] [rbp+158h] BYREF

  Handle = a2;
  memset_0(v25, 0, 0x220u);
  v22 = 0;
  v20 = 0;
  v23 = 0;
  memset(ProcessInformation, 0, 44);
  InformationProcess = NtQueryInformationProcess(a2, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
  if ( InformationProcess >= 0 )
  {
    v10 = ProcessInformation[2];
    v11 = (_QWORD *)(a1 + 32);
    for ( i = (_QWORD *)*v11; i != v11; i = (_QWORD *)*i )
    {
      v13 = (unsigned int *)(i - 8);
      if ( *((_DWORD *)i - 16) == LODWORD(ProcessInformation[2]) )
      {
        v14 = 0;
        goto LABEL_26;
      }
    }
    if ( !a4 )
    {
      InformationProcess = -1073741811;
      goto LABEL_31;
    }
    InformationProcess = PsmpQueryClientApplicationInformation(Handle, 0, v25, 0);
    if ( InformationProcess >= 0 )
    {
      InformationProcess = PsmpFindApplicationByManagerForUser(Sid2, v25[0], (__int64)v25 + 8, DWORD1(v25[0]), 0, &v22);
      if ( InformationProcess >= 0 )
      {
        v15 = v22;
        if ( !*(_QWORD *)(v22 + 80) )
        {
          RtlAcquireSRWLockExclusive(v22 + 328);
          InformationProcess = PsmpAllocateTcNotify(v15, 0);
          RtlReleaseSRWLockExclusive(v15 + 328);
          if ( InformationProcess < 0 )
          {
            PsmpDereferenceApplicationEx(v15, 0);
            goto LABEL_31;
          }
        }
        InformationProcess = PsmpFindOrCreateClientProcessContext(v15, v10, &Handle, &v20);
        PsmpDereferenceApplicationEx(v15, 0);
        if ( InformationProcess >= 0 )
        {
          Heap = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x50u);
          v13 = Heap;
          if ( Heap )
          {
            InformationProcess = TpAllocWait(&v23, PsmpClientTcRundown, Heap, 0);
            if ( InformationProcess >= 0 )
            {
              memset_0(v13, 0, 0x50u);
              RtlInitializeSRWLock(v13 + 10);
              v17 = v20;
              *((_QWORD *)v13 + 6) = v20;
              *v13 = v10;
              *((_QWORD *)v13 + 7) = v23;
              v18 = (_QWORD *)v11[1];
              if ( (_QWORD *)*v18 != v11 )
                __fastfail(3u);
              *((_QWORD *)v13 + 8) = v11;
              v14 = 1;
              *((_QWORD *)v13 + 9) = v18;
              *v18 = v13 + 16;
              v11[1] = v13 + 16;
              TpSetWait(*((_QWORD *)v13 + 7), *(_QWORD *)(v17 + 16), 0);
LABEL_26:
              LOBYTE(v9) = a4;
              InformationProcess = PsmpAdjustTcEntry(v13, a3, v9, 0);
              if ( InformationProcess >= 0 )
              {
                if ( v13[1] )
                  goto LABEL_31;
              }
              else if ( !v14 )
              {
                goto LABEL_31;
              }
              PsmpDestroyTcEntry(v13);
              goto LABEL_31;
            }
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
          }
          else
          {
            InformationProcess = -1073741670;
          }
          PsmpDereferenceClientContext(v20);
          goto LABEL_31;
        }
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            WPP_2676a593e7783fc6fea2dce701a66333_Traceguids,
            v10,
            InformationProcess);
      }
    }
  }
LABEL_31:
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)InformationProcess;
}

```

## disassembly

```asm
0x180023ae8  mov     [rsp-8+arg_18], rbx
0x180023aed  push    rbp
0x180023aee  push    rsi
0x180023aef  push    rdi
0x180023af0  push    r12
0x180023af2  push    r13
0x180023af4  push    r14
0x180023af6  push    r15
0x180023af8  lea     rbp, [rsp-1B0h]
0x180023b00  sub     rsp, 2B0h
0x180023b07  mov     rax, cs:__security_cookie
0x180023b0e  xor     rax, rsp
0x180023b11  mov     [rbp+1E0h+var_40], rax
0x180023b18  mov     r13d, r8d
0x180023b1b  mov     [rsp+2E0h+Handle], rdx
0x180023b20  mov     rbx, rdx
0x180023b23  mov     r14, rcx
0x180023b26  xor     edx, edx; Val
0x180023b28  lea     rcx, [rbp+1E0h+var_260]; void *
0x180023b2c  mov     r8d, 220h; Size
0x180023b32  mov     r12b, r9b
0x180023b35  call    memset_0
0x180023b3a  xor     eax, eax
0x180023b3c  mov     [rsp+2E0h+var_2A0], 0
0x180023b45  xorps   xmm0, xmm0
0x180023b48  mov     [rsp+2E0h+var_2B0], rax
0x180023b4d  movups  [rsp+2E0h+var_280], xmm0
0x180023b52  lea     r8, [rsp+2E0h+ProcessInformation]; ProcessInformation
0x180023b57  mov     [rsp+2E0h+var_298], rax
0x180023b5c  lea     r9d, [rax+30h]; ProcessInformationLength
0x180023b60  mov     [rsp+2E0h+ReturnLength], rax; ReturnLength
0x180023b65  xor     edx, edx; ProcessInformationClass
0x180023b67  mov     rcx, rbx; ProcessHandle
0x180023b6a  movups  [rsp+2E0h+ProcessInformation], xmm0
0x180023b6f  movups  [rsp+2E0h+var_280+0Ch], xmm0
0x180023b74  call    cs:__imp_NtQueryInformationProcess
0x180023b7a  mov     edi, eax
0x180023b7c  test    eax, eax
0x180023b7e  js      loc_180023DAC
0x180023b84  mov     r15d, [rsp+2E0h+var_270]
0x180023b89  add     r14, 20h ; ' '
0x180023b8d  mov     rax, [r14]
0x180023b90  cmp     rax, r14
0x180023b93  jz      short loc_180023BAB
0x180023b95  lea     rbx, [rax-40h]
0x180023b99  cmp     [rbx], r15d
0x180023b9c  jz      short loc_180023BA3
0x180023b9e  mov     rax, [rax]
0x180023ba1  jmp     short loc_180023B90
0x180023ba3  xor     sil, sil
0x180023ba6  jmp     loc_180023D80
0x180023bab  test    r12b, r12b
0x180023bae  jnz     short loc_180023BBA
0x180023bb0  mov     edi, 0C000000Dh
0x180023bb5  jmp     loc_180023DAC
0x180023bba  mov     rcx, [rsp+2E0h+Handle]; ProcessHandle
0x180023bbf  lea     r8, [rbp+1E0h+var_260]
0x180023bc3  xor     r9d, r9d
0x180023bc6  xor     edx, edx; TokenHandle
0x180023bc8  call    PsmpQueryClientApplicationInformation
0x180023bcd  mov     edi, eax
0x180023bcf  test    eax, eax
0x180023bd1  js      loc_180023DAC
0x180023bd7  mov     r9d, [rbp+1E0h+var_25C]
0x180023bdb  lea     rax, [rsp+2E0h+var_2A0]
0x180023be0  mov     edx, [rbp+1E0h+var_260]
0x180023be3  lea     r8, [rbp+1E0h+var_258]
0x180023be7  mov     [rsp+2E0h+var_2B8], rax; __int64
0x180023bec  lea     rcx, [rbp+1E0h+Sid2]; Sid2
0x180023bf3  mov     dword ptr [rsp+2E0h+ReturnLength], 0; int
0x180023bfb  call    PsmpFindApplicationByManagerForUser
0x180023c00  mov     edi, eax
0x180023c02  test    eax, eax
0x180023c04  js      loc_180023DAC
0x180023c0a  mov     rsi, [rsp+2E0h+var_2A0]
0x180023c0f  cmp     qword ptr [rsi+50h], 0
0x180023c14  jnz     short loc_180023C4E
0x180023c16  lea     rbx, [rsi+148h]
0x180023c1d  mov     rcx, rbx
0x180023c20  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180023c26  xor     edx, edx
0x180023c28  mov     rcx, rsi
0x180023c2b  call    PsmpAllocateTcNotify
0x180023c30  mov     rcx, rbx
0x180023c33  mov     edi, eax
0x180023c35  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180023c3b  test    edi, edi
0x180023c3d  jns     short loc_180023C4E
0x180023c3f  xor     edx, edx
0x180023c41  mov     rcx, rsi
0x180023c44  call    PsmpDereferenceApplicationEx
0x180023c49  jmp     loc_180023DAC
0x180023c4e  lea     r9, [rsp+2E0h+var_2B0]
0x180023c53  mov     edx, r15d
0x180023c56  lea     r8, [rsp+2E0h+Handle]
0x180023c5b  mov     rcx, rsi
0x180023c5e  call    PsmpFindOrCreateClientProcessContext
0x180023c63  xor     edx, edx
0x180023c65  mov     rcx, rsi
0x180023c68  mov     edi, eax
0x180023c6a  call    PsmpDereferenceApplicationEx
0x180023c6f  test    edi, edi
0x180023c71  jns     short loc_180023CAF
0x180023c73  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c7a  test    byte ptr [rcx+1Ch], 10h
0x180023c7e  jz      loc_180023DAC
0x180023c84  cmp     byte ptr [rcx+19h], 2
0x180023c88  jb      loc_180023DAC
0x180023c8e  mov     rcx, [rcx+10h]
0x180023c92  lea     r8, WPP_2676a593e7783fc6fea2dce701a66333_Traceguids
0x180023c99  mov     edx, 0Bh
0x180023c9e  mov     dword ptr [rsp+2E0h+ReturnLength], edi
0x180023ca2  mov     r9d, r15d
0x180023ca5  call    WPP_SF_Dd
0x180023caa  jmp     loc_180023DAC
0x180023caf  mov     rcx, gs:60h
0x180023cb8  mov     esi, 50h ; 'P'
0x180023cbd  mov     r8d, esi; Size
0x180023cc0  xor     edx, edx; Flags
0x180023cc2  mov     rcx, [rcx+30h]; HeapHandle
0x180023cc6  call    cs:__imp_RtlAllocateHeap
0x180023ccc  mov     rbx, rax
0x180023ccf  test    rax, rax
0x180023cd2  jnz     short loc_180023CE8
0x180023cd4  mov     edi, 0C000009Ah
0x180023cd9  mov     rcx, [rsp+2E0h+var_2B0]
0x180023cde  call    PsmpDereferenceClientContext
0x180023ce3  jmp     loc_180023DAC
0x180023ce8  xor     r9d, r9d
0x180023ceb  lea     rdx, PsmpClientTcRundown
0x180023cf2  mov     r8, rbx
0x180023cf5  lea     rcx, [rsp+2E0h+var_298]
0x180023cfa  call    cs:__imp_TpAllocWait
0x180023d00  xor     edx, edx; Val
0x180023d02  mov     edi, eax
0x180023d04  test    eax, eax
0x180023d06  jns     short loc_180023D20
0x180023d08  mov     rcx, gs:60h
0x180023d11  mov     r8, rbx; P
0x180023d14  mov     rcx, [rcx+30h]; HeapHandle
0x180023d18  call    cs:__imp_RtlFreeHeap
0x180023d1e  jmp     short loc_180023CD9
0x180023d20  mov     r8, rsi; Size
0x180023d23  mov     rcx, rbx; void *
0x180023d26  call    memset_0
0x180023d2b  lea     rcx, [rbx+28h]
0x180023d2f  call    cs:__imp_RtlInitializeSRWLock
0x180023d35  mov     rdx, [rsp+2E0h+var_2B0]
0x180023d3a  mov     [rbx+30h], rdx
0x180023d3e  mov     [rbx], r15d
0x180023d41  mov     rax, [rsp+2E0h+var_298]
0x180023d46  mov     [rbx+38h], rax
0x180023d4a  mov     rcx, [r14+8]
0x180023d4e  cmp     [rcx], r14
0x180023d51  jz      short loc_180023D5A
0x180023d53  mov     ecx, 3
0x180023d58  int     29h; Win8: RtlFailFast(ecx)
0x180023d5a  lea     rax, [rbx+40h]
0x180023d5e  xor     r8d, r8d
0x180023d61  mov     [rax], r14
0x180023d64  mov     sil, 1
0x180023d67  mov     [rax+8], rcx
0x180023d6b  mov     [rcx], rax
0x180023d6e  mov     [r14+8], rax
0x180023d72  mov     rdx, [rdx+10h]
0x180023d76  mov     rcx, [rbx+38h]
0x180023d7a  call    cs:__imp_TpSetWait
0x180023d80  xor     r9d, r9d
0x180023d83  mov     r8b, r12b
0x180023d86  mov     edx, r13d
0x180023d89  mov     rcx, rbx
0x180023d8c  call    PsmpAdjustTcEntry
0x180023d91  mov     edi, eax
0x180023d93  test    eax, eax
0x180023d95  jns     short loc_180023D9E
0x180023d97  test    sil, sil
0x180023d9a  jnz     short loc_180023DA4
0x180023d9c  jmp     short loc_180023DAC
0x180023d9e  cmp     dword ptr [rbx+4], 0
0x180023da2  jnz     short loc_180023DAC
0x180023da4  mov     rcx, rbx
0x180023da7  call    PsmpDestroyTcEntry
0x180023dac  mov     rbx, [rsp+2E0h+Handle]
0x180023db1  test    rbx, rbx
0x180023db4  jz      short loc_180023DBF
0x180023db6  mov     rcx, rbx; Handle
0x180023db9  call    cs:__imp_NtClose
0x180023dbf  mov     eax, edi
0x180023dc1  mov     rcx, [rbp+1E0h+var_40]
0x180023dc8  xor     rcx, rsp; StackCookie
0x180023dcb  call    __security_check_cookie
0x180023dd0  mov     rbx, [rsp+2E0h+arg_18]
0x180023dd8  add     rsp, 2B0h
0x180023ddf  pop     r15
0x180023de1  pop     r14
0x180023de3  pop     r13
0x180023de5  pop     r12
0x180023de7  pop     rdi
0x180023de8  pop     rsi
0x180023de9  pop     rbp
0x180023dea  retn
```
