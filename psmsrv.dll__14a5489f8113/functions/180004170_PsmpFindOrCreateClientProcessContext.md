# PsmpFindOrCreateClientProcessContext

- ea: `0x180004170`
- end: `0x18000430d`
- name: `PsmpFindOrCreateClientProcessContext`
- size: `413`
- prototype: `__int64 __fastcall(__int64, unsigned int, HANDLE *, __int64 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180003af0`
- `0x180023ae8`

## callees

- `0x180001fdc`
- `0x180004170`
- `0x180004314`
- `0x18000436c`
- `0x18000438c`
- `0x180009b40`
- `0x18000defc`
- `0x1800179d8`
- `0x180019e3c`

## import_xrefs

- `ntdll!NtIsProcessInJob` at `0x1800041be`
- `ntdll!NtIsProcessInJob` at `0x1800041be`
- `ntdll!RtlReleaseSRWLockShared` at `0x180004221`
- `ntdll!RtlReleaseSRWLockShared` at `0x180004221`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004260`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004260`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800042a5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800042a5`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000420b`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000420b`

## pseudocode

```c
__int64 __fastcall PsmpFindOrCreateClientProcessContext(__int64 a1, unsigned int a2, HANDLE *a3, __int64 *a4)
{
  void *v6; // rdx
  NTSTATUS IsProcessInJob; // eax
  __int64 v11; // r14
  __int64 ClientProcessContext; // rsi
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  _QWORD *Heap; // rax
  _QWORD *v17; // rbx
  __int64 v18; // rdi
  _QWORD *v19; // rcx

  v6 = *(void **)(a1 + 192);
  if ( !v6 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF_iD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        &WPP_b5485372ff90327e3674091dc1985471_Traceguids,
        *(_QWORD *)(a1 + 96),
        a2);
    return 3221225659LL;
  }
  IsProcessInJob = NtIsProcessInJob(*a3, v6);
  if ( IsProcessInJob != 292 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF_iLL(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_b5485372ff90327e3674091dc1985471_Traceguids,
        *(_QWORD *)(a1 + 96),
        a2,
        IsProcessInJob);
    return 3221225659LL;
  }
  v11 = a1 + 328;
  RtlAcquireSRWLockShared(a1 + 328);
  ClientProcessContext = PsmpFindClientProcessContext(a2, a1);
  RtlReleaseSRWLockShared(a1 + 328, v13, v14, v15);
  if ( ClientProcessContext )
    goto LABEL_15;
  Heap = PsmpAllocateHeap(0x78u);
  v17 = Heap;
  if ( Heap )
  {
    PsmpInitializeClientContext(Heap, 2, a2, *a3);
    PsmpReferenceApplication(a1);
    v17[12] = a1;
    RtlAcquireSRWLockExclusive(a1 + 328);
    ClientProcessContext = PsmpFindClientProcessContext(a2, a1);
    if ( !ClientProcessContext )
    {
      v18 = a1 + 6704;
      *a3 = 0;
      v19 = *(_QWORD **)(v18 + 8);
      if ( *v19 != v18 )
        __fastfail(3u);
      ClientProcessContext = (__int64)v17;
      v17 = 0;
      *(_QWORD *)(ClientProcessContext + 104) = v18;
      *(_QWORD *)(ClientProcessContext + 112) = v19;
      *v19 = ClientProcessContext + 104;
      *(_QWORD *)(v18 + 8) = ClientProcessContext + 104;
    }
    RtlReleaseSRWLockExclusive(v11);
    if ( v17 )
    {
      PsmpDereferenceApplicationEx(v17[12], 0);
      PsmpFreeHeap(v17);
    }
LABEL_15:
    *a4 = ClientProcessContext;
    return 0;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x180004170  push    rbx
0x180004172  push    rbp
0x180004173  push    rsi
0x180004174  push    rdi
0x180004175  push    r12
0x180004177  push    r14
0x180004179  push    r15
0x18000417b  sub     rsp, 30h
0x18000417f  mov     ebp, edx
0x180004181  mov     r12, r9
0x180004184  mov     rdx, [rcx+0C0h]; JobHandle
0x18000418b  mov     r15, r8
0x18000418e  mov     rdi, rcx
0x180004191  test    rdx, rdx
0x180004194  jnz     short loc_1800041BB
0x180004196  mov     rcx, cs:WPP_GLOBAL_Control
0x18000419d  test    byte ptr [rcx+1Ch], 2
0x1800041a1  jnz     loc_1800042C5
0x1800041a7  mov     eax, 0C00000BBh
0x1800041ac  add     rsp, 30h
0x1800041b0  pop     r15
0x1800041b2  pop     r14
0x1800041b4  pop     r12
0x1800041b6  pop     rdi
0x1800041b7  pop     rsi
0x1800041b8  pop     rbp
0x1800041b9  pop     rbx
0x1800041ba  retn
0x1800041bb  mov     rcx, [r8]; ProcessHandle
0x1800041be  call    cs:__imp_NtIsProcessInJob
0x1800041c4  cmp     eax, 124h
0x1800041c9  jz      short loc_180004201
0x1800041cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041d2  test    byte ptr [rcx+1Ch], 2
0x1800041d6  jz      short loc_1800041A7
0x1800041d8  cmp     byte ptr [rcx+19h], 5
0x1800041dc  jb      short loc_1800041A7
0x1800041de  mov     r9, [rdi+60h]
0x1800041e2  lea     r8, WPP_b5485372ff90327e3674091dc1985471_Traceguids
0x1800041e9  mov     rcx, [rcx+10h]
0x1800041ed  mov     edx, 0Fh
0x1800041f2  mov     [rsp+68h+var_40], eax
0x1800041f6  mov     [rsp+68h+var_48], ebp
0x1800041fa  call    WPP_SF_iLL
0x1800041ff  jmp     short loc_1800041A7
0x180004201  lea     r14, [rdi+148h]
0x180004208  mov     rcx, r14
0x18000420b  call    cs:__imp_RtlAcquireSRWLockShared
0x180004211  mov     rdx, rdi
0x180004214  mov     ecx, ebp
0x180004216  call    PsmpFindClientProcessContext
0x18000421b  mov     rcx, r14
0x18000421e  mov     rsi, rax
0x180004221  call    cs:__imp_RtlReleaseSRWLockShared
0x180004227  test    rsi, rsi
0x18000422a  jnz     loc_1800042B0
0x180004230  lea     ecx, [rsi+78h]
0x180004233  call    PsmpAllocateHeap
0x180004238  mov     rbx, rax
0x18000423b  test    rax, rax
0x18000423e  jz      short loc_1800042BB
0x180004240  mov     r9, [r15]
0x180004243  lea     edx, [rsi+2]
0x180004246  mov     r8d, ebp
0x180004249  mov     rcx, rax
0x18000424c  call    PsmpInitializeClientContext
0x180004251  mov     rcx, rdi
0x180004254  call    PsmpReferenceApplication
0x180004259  mov     rcx, r14
0x18000425c  mov     [rbx+60h], rdi
0x180004260  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180004266  mov     rdx, rdi
0x180004269  mov     ecx, ebp
0x18000426b  call    PsmpFindClientProcessContext
0x180004270  mov     rsi, rax
0x180004273  test    rax, rax
0x180004276  jnz     short loc_1800042A2
0x180004278  add     rdi, 1A30h
0x18000427f  mov     [r15], rax
0x180004282  mov     rcx, [rdi+8]
0x180004286  cmp     [rcx], rdi
0x180004289  jnz     short loc_1800042F1
0x18000428b  mov     rsi, rbx
0x18000428e  xor     ebx, ebx
0x180004290  lea     rax, [rsi+68h]
0x180004294  mov     [rax], rdi
0x180004297  mov     [rax+8], rcx
0x18000429b  mov     [rcx], rax
0x18000429e  mov     [rdi+8], rax
0x1800042a2  mov     rcx, r14
0x1800042a5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800042ab  test    rbx, rbx
0x1800042ae  jnz     short loc_1800042F8
0x1800042b0  mov     [r12], rsi
0x1800042b4  xor     eax, eax
0x1800042b6  jmp     loc_1800041AC
0x1800042bb  mov     eax, 0C000009Ah
0x1800042c0  jmp     loc_1800041AC
0x1800042c5  cmp     byte ptr [rcx+19h], 5
0x1800042c9  jb      loc_1800041A7
0x1800042cf  mov     r9, [rdi+60h]
0x1800042d3  lea     r8, WPP_b5485372ff90327e3674091dc1985471_Traceguids
0x1800042da  mov     rcx, [rcx+10h]
0x1800042de  mov     edx, 0Eh
0x1800042e3  mov     [rsp+68h+var_48], ebp
0x1800042e7  call    WPP_SF_iD
0x1800042ec  jmp     loc_1800041A7
0x1800042f1  mov     ecx, 3
0x1800042f6  int     29h; Win8: RtlFailFast(ecx)
0x1800042f8  mov     rcx, [rbx+60h]
0x1800042fc  xor     edx, edx
0x1800042fe  call    PsmpDereferenceApplicationEx
0x180004303  mov     rcx, rbx
0x180004306  call    PsmpFreeHeap
0x18000430b  jmp     short loc_1800042B0
```
