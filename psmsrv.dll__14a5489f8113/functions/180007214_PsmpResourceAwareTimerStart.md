# PsmpResourceAwareTimerStart

- ea: `0x180007214`
- end: `0x180007725`
- name: `PsmpResourceAwareTimerStart`
- size: `1297`
- prototype: `__int64 __usercall@<rax>(PVOID P@<rcx>, PSID Sid2@<rdx>, int, __int64, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006460`

## callees

- `0x180004f08`
- `0x180005948`
- `0x1800065a0`
- `0x180006b7c`
- `0x180006c8c`
- `0x1800070e4`
- `0x180007214`
- `0x180008cc0`
- `0x180009b40`
- `0x18000a750`
- `0x18000aab0`
- `0x18001b7e0`
- `0x18002e17c`

## import_xrefs

- `ntdll!TpSetTimer` at `0x1800076a1`
- `ntdll!TpSetTimer` at `0x1800076a1`
- `ntdll!TpAllocTimer` at `0x1800073ed`
- `ntdll!TpAllocTimer` at `0x1800073ed`
- `ntdll!RtlFreeHeap` at `0x1800076d7`
- `ntdll!RtlFreeHeap` at `0x18000771a`
- `ntdll!RtlFreeHeap` at `0x1800076d7`
- `ntdll!RtlFreeHeap` at `0x18000771a`
- `ntdll!TpReleaseTimer` at `0x1800076ba`
- `ntdll!TpReleaseTimer` at `0x1800076ba`
- `ntdll!TpWaitForTimer` at `0x1800076b0`
- `ntdll!TpWaitForTimer` at `0x1800076b0`
- `ntdll!NtCreateWnfStateName` at `0x180007314`
- `ntdll!NtCreateWnfStateName` at `0x180007314`
- `ntdll!NtDeleteWnfStateName` at `0x1800076e6`
- `ntdll!NtDeleteWnfStateName` at `0x1800076f5`
- `ntdll!NtDeleteWnfStateName` at `0x1800076e6`
- `ntdll!NtDeleteWnfStateName` at `0x1800076f5`
- `ntdll!RtlAllocateHeap` at `0x180007339`
- `ntdll!RtlAllocateHeap` at `0x180007339`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000760a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007644`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000760a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007644`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000762d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000767a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000762d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000767a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007393`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007393`

## pseudocode

```c
__int64 __fastcall PsmpResourceAwareTimerStart(
        char *P,
        PSID Sid2,
        int a3,
        char *a4,
        unsigned int a5,
        __int64 a6,
        int a7,
        __int128 *a8,
        __int64 a9,
        _QWORD *a10)
{
  _WORD *v10; // r15
  __int64 *v13; // r12
  _QWORD *v14; // rbx
  __int64 v15; // r9
  int ApplicationByManagerForUser; // eax
  __int64 v17; // r14
  int v18; // edi
  __int64 *v19; // rax
  __int64 v20; // r13
  _WORD *Heap; // rax
  char *v22; // r8
  __int64 v23; // rcx
  __int64 v24; // rdx
  _WORD *v25; // rcx
  DWORD LengthSid; // eax
  int v27; // r13d
  int ApplicationHostJob; // eax
  __int64 v30; // rax
  char *v31; // rcx
  __int64 v32; // rax
  __int128 *v33; // rax
  __int128 v34; // xmm0
  _QWORD *v35; // rax
  _QWORD *v36; // rax
  _QWORD *v37; // rcx
  __int64 *v38; // [rsp+40h] [rbp-51h] BYREF
  unsigned int v39; // [rsp+48h] [rbp-49h]
  int v40; // [rsp+4Ch] [rbp-45h]
  __int64 *v41; // [rsp+50h] [rbp-41h] BYREF
  PSID pSid; // [rsp+58h] [rbp-39h]
  __int128 *v43; // [rsp+60h] [rbp-31h]
  char *v44; // [rsp+68h] [rbp-29h]
  _QWORD *v45; // [rsp+70h] [rbp-21h]
  __int64 v46; // [rsp+78h] [rbp-19h] BYREF
  __int64 v47; // [rsp+80h] [rbp-11h] BYREF

  v10 = 0;
  v43 = a8;
  v44 = a4;
  v45 = a10;
  v39 = a3;
  v13 = 0;
  pSid = Sid2;
  v14 = 0;
  v38 = 0;
  v15 = -1;
  v46 = 0;
  v41 = 0;
  v47 = 0;
  v40 = 0;
  do
    ++v15;
  while ( *(_WORD *)&a4[2 * v15] );
  ApplicationByManagerForUser = PsmpFindApplicationByManagerForUser(Sid2, a3, (__int64)a4, 2 * v15 + 2, a7, &v46);
  v17 = v46;
  v18 = ApplicationByManagerForUser;
  if ( ApplicationByManagerForUser < 0 )
    goto LABEL_39;
  if ( a5 != 2 )
  {
    if ( a5 == 8 )
    {
      v19 = *(__int64 **)(v46 + 200);
      v20 = v46 + 6856;
      goto LABEL_6;
    }
    ApplicationHostJob = PsmpGetApplicationHostJob(v46, a5, a6, 0, (__int64)&v38, (__int64)&v41);
    v13 = v41;
    v18 = ApplicationHostJob;
    if ( ApplicationHostJob >= 0 )
    {
      v19 = v38;
      v20 = (__int64)(v41 + 13);
      goto LABEL_6;
    }
LABEL_39:
    v27 = (int)pSid;
    goto LABEL_22;
  }
  v19 = *(__int64 **)(v46 + 192);
  v20 = v46 + 6840;
LABEL_6:
  v41 = v19;
  v38 = 0;
  v46 = 0;
  v18 = NtCreateWnfStateName(&v46, 3, 0);
  if ( v18 >= 0 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x230u);
    v10 = Heap;
    if ( Heap )
    {
      v22 = v44;
      v23 = 2147483646;
      v24 = 232;
      do
      {
        if ( !v23 )
          break;
        if ( !*(_WORD *)v22 )
          break;
        *Heap = *(_WORD *)v22;
        v22 += 2;
        ++Heap;
        --v23;
        --v24;
      }
      while ( v24 );
      v25 = Heap - 1;
      if ( v24 )
        v25 = Heap;
      *v25 = 0;
      LengthSid = GetLengthSid(pSid);
      memcpy_0(v10 + 232, pSid, LengthSid);
      *((_DWORD *)v10 + 133) = v39;
      *((_DWORD *)v10 + 134) = a5;
      *((_QWORD *)v10 + 68) = a6;
      *((_DWORD *)v10 + 138) = *(_DWORD *)(*(_QWORD *)(v17 + 320) + 16LL);
      v18 = TpAllocTimer(&v38, PsmpResourceAwareTimerCallback, v10, 0);
      if ( v18 >= 0 )
      {
        *((_QWORD *)P + 5) = v38;
        v47 = v46;
        v33 = v43;
        *((_QWORD *)P + 11) = v10;
        v38 = 0;
        v46 = 0;
        v34 = *v33;
        *((_QWORD *)P + 12) = v41;
        *(_OWORD *)(P + 68) = v34;
        *((_QWORD *)P + 3) = v17;
        *((_DWORD *)P + 4) = 1;
        PsmpResourceAwareTimerReference(P);
        RtlAcquireSRWLockExclusive(v17 + 328);
        v35 = *(_QWORD **)(v20 + 8);
        if ( *v35 != v20 )
          goto LABEL_48;
        *(_QWORD *)P = v20;
        *((_QWORD *)P + 1) = v35;
        v10 = 0;
        *v35 = P;
        *(_QWORD *)(v20 + 8) = P;
        RtlReleaseSRWLockExclusive(v17 + 328);
        v18 = 0;
      }
    }
    else
    {
      v18 = -1073741670;
    }
  }
  v27 = (int)pSid;
  PsmpLogResourceAwareTimerCreate(v44, (__int64)pSid, v39, a5, a6, (__int64)v43, v18);
  if ( v38 )
  {
    TpSetTimer(v38, 0, 0, 0);
    TpWaitForTimer(v38, 1);
    TpReleaseTimer(v38);
  }
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  if ( v46 )
    NtDeleteWnfStateName(&v46);
  if ( v18 >= 0 )
  {
    v30 = v47;
    v14 = P;
    v40 = 1;
    v31 = P;
    v47 = 0;
    *((_QWORD *)P + 6) = v30;
    P = 0;
    v18 = PsmpResourceAwareTimerSetEx(v31, v17, a9, 0);
    if ( v18 >= 0 )
    {
      v18 = 0;
      v32 = v14[6];
      v40 = 0;
      *v45 = v32;
    }
  }
LABEL_22:
  PsmpLogResourceAwareTimerStart((_DWORD)v44, v27, v39, a5, a6, (__int64)v43, a9, v18);
  if ( !v40 )
    goto LABEL_23;
  RtlAcquireSRWLockExclusive(v17 + 328);
  v36 = (_QWORD *)*v14;
  if ( (_QWORD *)*v14 != v14 )
  {
    if ( (_QWORD *)v36[1] == v14 )
    {
      v37 = (_QWORD *)v14[1];
      if ( (_QWORD *)*v37 == v14 )
      {
        *v37 = v36;
        v36[1] = v37;
        v14[1] = v14;
        *v14 = v14;
        PsmpResourceAwareTimerDereference(v14);
        goto LABEL_47;
      }
    }
LABEL_48:
    __fastfail(3u);
  }
LABEL_47:
  RtlReleaseSRWLockExclusive(v17 + 328);
LABEL_23:
  if ( v14 )
    PsmpResourceAwareTimerDereference(v14);
  if ( v13 )
    PsmpDereferenceHostContext(v13, 0);
  if ( v17 )
    PsmpDereferenceApplicationEx(v17, 0);
  if ( v47 )
    NtDeleteWnfStateName(&v47);
  if ( P )
  {
    PsmpResourceAwareTimerCleanup((__int64)P);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180007214  push    rbp
0x180007216  push    rbx
0x180007217  push    rsi
0x180007218  push    rdi
0x180007219  push    r12
0x18000721b  push    r13
0x18000721d  push    r14
0x18000721f  push    r15
0x180007221  lea     rbp, [rsp-7]
0x180007226  sub     rsp, 98h
0x18000722d  mov     rax, cs:__security_cookie
0x180007234  xor     rax, rsp
0x180007237  mov     [rbp+3Fh+var_48], rax
0x18000723b  mov     rax, [rbp+3Fh+arg_38]
0x180007242  xor     r15d, r15d
0x180007245  mov     [rbp+3Fh+var_70], rax
0x180007249  mov     r10, r9
0x18000724c  mov     rax, [rbp+3Fh+arg_48]
0x180007253  mov     edi, r8d
0x180007256  mov     [rbp+3Fh+var_68], r9
0x18000725a  mov     r11, rdx
0x18000725d  mov     [rbp+3Fh+var_60], rax
0x180007261  mov     rsi, rcx
0x180007264  mov     [rbp+3Fh+var_88], r8d
0x180007268  mov     r12d, r15d
0x18000726b  mov     [rbp+3Fh+pSid], rdx
0x18000726f  mov     ebx, r15d
0x180007272  mov     [rbp+3Fh+var_90], r15
0x180007276  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000727a  mov     [rbp+3Fh+var_58], r15
0x18000727e  mov     [rbp+3Fh+var_80], r15
0x180007282  mov     [rbp+3Fh+var_50], r15
0x180007286  mov     [rbp+3Fh+var_84], r15d
0x18000728a  inc     r9
0x18000728d  cmp     [r10+r9*2], r15w
0x180007292  jnz     short loc_18000728A
0x180007294  lea     rax, [rbp+3Fh+var_58]
0x180007298  mov     r8, r10
0x18000729b  mov     [rsp+0D0h+var_A8], rax; __int64
0x1800072a0  lea     r9, ds:2[r9*2]
0x1800072a8  mov     eax, [rbp+3Fh+arg_30]
0x1800072ab  mov     edx, edi
0x1800072ad  mov     rcx, r11; Sid2
0x1800072b0  mov     [rsp+0D0h+var_B0], eax; int
0x1800072b4  call    PsmpFindApplicationByManagerForUser
0x1800072b9  mov     r14, [rbp+3Fh+var_58]
0x1800072bd  mov     edi, eax
0x1800072bf  test    eax, eax
0x1800072c1  js      loc_1800075A1
0x1800072c7  mov     eax, [rbp+3Fh+arg_20]
0x1800072ca  cmp     eax, 2
0x1800072cd  jnz     loc_18000750E
0x1800072d3  mov     rax, [r14+0C0h]
0x1800072da  lea     r13, [r14+1AB8h]
0x1800072e1  xor     r9d, r9d
0x1800072e4  mov     [rbp+3Fh+var_80], rax
0x1800072e8  lea     rax, PsmpResourceTimerDescriptor
0x1800072ef  mov     [rbp+3Fh+var_90], r15
0x1800072f3  mov     [rsp+0D0h+var_A0], rax
0x1800072f8  lea     rcx, [rbp+3Fh+var_58]
0x1800072fc  mov     dword ptr [rsp+0D0h+var_A8], 10h
0x180007304  xor     r8d, r8d
0x180007307  lea     edx, [r9+3]
0x18000730b  mov     [rbp+3Fh+var_58], r15
0x18000730f  mov     qword ptr [rsp+0D0h+var_B0], rbx
0x180007314  call    cs:__imp_NtCreateWnfStateName
0x18000731a  mov     edi, eax
0x18000731c  test    eax, eax
0x18000731e  js      loc_1800073FF
0x180007324  mov     rcx, gs:60h
0x18000732d  xor     edx, edx; Flags
0x18000732f  mov     r8d, 230h; Size
0x180007335  mov     rcx, [rcx+30h]; HeapHandle
0x180007339  call    cs:__imp_RtlAllocateHeap
0x18000733f  xor     r10d, r10d
0x180007342  mov     r15, rax
0x180007345  test    rax, rax
0x180007348  jz      loc_18000768F
0x18000734e  mov     r8, [rbp+3Fh+var_68]
0x180007352  mov     ecx, 7FFFFFFEh
0x180007357  mov     edx, 0E8h
0x18000735c  test    rcx, rcx
0x18000735f  jz      short loc_180007380
0x180007361  movzx   r9d, word ptr [r8]
0x180007365  test    r9w, r9w
0x180007369  jz      short loc_180007380
0x18000736b  mov     [rax], r9w
0x18000736f  add     r8, 2
0x180007373  add     rax, 2
0x180007377  dec     rcx
0x18000737a  sub     rdx, 1
0x18000737e  jnz     short loc_18000735C
0x180007380  test    rdx, rdx
0x180007383  lea     rcx, [rax-2]
0x180007387  cmovnz  rcx, rax
0x18000738b  mov     [rcx], r10w
0x18000738f  mov     rcx, [rbp+3Fh+pSid]; pSid
0x180007393  call    cs:__imp_GetLengthSid
0x180007399  mov     rdx, [rbp+3Fh+pSid]; Src
0x18000739d  lea     rcx, [r15+1D0h]; void *
0x1800073a4  mov     r8d, eax; Size
0x1800073a7  call    memcpy_0
0x1800073ac  mov     eax, [rbp+3Fh+var_88]
0x1800073af  lea     rdx, PsmpResourceAwareTimerCallback
0x1800073b6  mov     [r15+214h], eax
0x1800073bd  xor     r9d, r9d
0x1800073c0  mov     eax, [rbp+3Fh+arg_20]
0x1800073c3  mov     r8, r15
0x1800073c6  mov     [r15+218h], eax
0x1800073cd  mov     rax, [rbp+3Fh+arg_28]
0x1800073d1  mov     [r15+220h], rax
0x1800073d8  mov     rax, [r14+140h]
0x1800073df  mov     ecx, [rax+10h]
0x1800073e2  mov     [r15+228h], ecx
0x1800073e9  lea     rcx, [rbp+3Fh+var_90]
0x1800073ed  call    cs:__imp_TpAllocTimer
0x1800073f3  xor     ecx, ecx
0x1800073f5  mov     edi, eax
0x1800073f7  test    eax, eax
0x1800073f9  jns     loc_1800075BD
0x1800073ff  mov     rax, [rbp+3Fh+var_70]
0x180007403  mov     r13, [rbp+3Fh+pSid]
0x180007407  mov     r9d, [rbp+3Fh+arg_20]
0x18000740b  mov     rdx, r13
0x18000740e  mov     r8d, [rbp+3Fh+var_88]
0x180007412  mov     rcx, [rbp+3Fh+var_68]
0x180007416  mov     dword ptr [rsp+0D0h+var_A0], edi
0x18000741a  mov     [rsp+0D0h+var_A8], rax
0x18000741f  mov     rax, [rbp+3Fh+arg_28]
0x180007423  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180007428  call    PsmpLogResourceAwareTimerCreate
0x18000742d  mov     rcx, [rbp+3Fh+var_90]
0x180007431  test    rcx, rcx
0x180007434  jnz     loc_180007699
0x18000743a  test    r15, r15
0x18000743d  jnz     loc_1800076C5
0x180007443  xor     r15d, r15d
0x180007446  cmp     dword ptr [rbp+3Fh+var_58], r15d
0x18000744a  jnz     loc_1800076E2
0x180007450  cmp     dword ptr [rbp+3Fh+var_58+4], r15d
0x180007454  jnz     loc_1800076E2
0x18000745a  test    edi, edi
0x18000745c  jns     loc_180007552
0x180007462  mov     rax, [rbp+3Fh+arg_40]
0x180007469  mov     rdx, r13
0x18000746c  mov     r9d, [rbp+3Fh+arg_20]
0x180007470  mov     r8d, [rbp+3Fh+var_88]
0x180007474  mov     rcx, [rbp+3Fh+var_68]
0x180007478  mov     [rsp+0D0h+var_98], edi
0x18000747c  mov     [rsp+0D0h+var_A0], rax
0x180007481  mov     rax, [rbp+3Fh+var_70]
0x180007485  mov     [rsp+0D0h+var_A8], rax
0x18000748a  mov     rax, [rbp+3Fh+arg_28]
0x18000748e  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180007493  call    PsmpLogResourceAwareTimerStart
0x180007498  cmp     [rbp+3Fh+var_84], r15d
0x18000749c  jnz     loc_18000763A
0x1800074a2  test    rbx, rbx
0x1800074a5  jnz     short loc_180007504
0x1800074a7  test    r12, r12
0x1800074aa  jz      short loc_1800074B6
0x1800074ac  xor     edx, edx
0x1800074ae  mov     rcx, r12
0x1800074b1  call    PsmpDereferenceHostContext
0x1800074b6  test    r14, r14
0x1800074b9  jz      short loc_1800074C5
0x1800074bb  xor     edx, edx
0x1800074bd  mov     rcx, r14
0x1800074c0  call    PsmpDereferenceApplicationEx
0x1800074c5  cmp     dword ptr [rbp+3Fh+var_50], r15d
0x1800074c9  jnz     loc_1800076F1
0x1800074cf  cmp     dword ptr [rbp+3Fh+var_50+4], r15d
0x1800074d3  jnz     loc_1800076F1
0x1800074d9  test    rsi, rsi
0x1800074dc  jnz     loc_180007700
0x1800074e2  mov     eax, edi
0x1800074e4  mov     rcx, [rbp+3Fh+var_48]
0x1800074e8  xor     rcx, rsp; StackCookie
0x1800074eb  call    __security_check_cookie
0x1800074f0  add     rsp, 98h
0x1800074f7  pop     r15
0x1800074f9  pop     r14
0x1800074fb  pop     r13
0x1800074fd  pop     r12
0x1800074ff  pop     rdi
0x180007500  pop     rsi
0x180007501  pop     rbx
0x180007502  pop     rbp
0x180007503  retn
0x180007504  mov     rcx, rbx; P
0x180007507  call    PsmpResourceAwareTimerDereference
0x18000750c  jmp     short loc_1800074A7
0x18000750e  cmp     eax, 8
0x180007511  jz      loc_1800075AA
0x180007517  mov     r8, [rbp+3Fh+arg_28]
0x18000751b  lea     rcx, [rbp+3Fh+var_80]
0x18000751f  mov     [rsp+0D0h+var_A8], rcx
0x180007524  xor     r9d, r9d
0x180007527  lea     rcx, [rbp+3Fh+var_90]
0x18000752b  mov     edx, eax
0x18000752d  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x180007532  mov     rcx, r14
0x180007535  call    PsmpGetApplicationHostJob
0x18000753a  mov     r12, [rbp+3Fh+var_80]
0x18000753e  mov     edi, eax
0x180007540  test    eax, eax
0x180007542  js      short loc_1800075A1
0x180007544  mov     rax, [rbp+3Fh+var_90]
0x180007548  lea     r13, [r12+68h]
0x18000754d  jmp     loc_1800072E1
0x180007552  mov     rax, [rbp+3Fh+var_50]
0x180007556  mov     rbx, rsi
0x180007559  mov     r8, [rbp+3Fh+arg_40]
0x180007560  xor     r9d, r9d
0x180007563  mov     rdx, r14
0x180007566  mov     [rbp+3Fh+var_84], 1
0x18000756d  mov     rcx, rbx
0x180007570  mov     [rbp+3Fh+var_50], r15
0x180007574  mov     [rbx+30h], rax
0x180007578  mov     rsi, r15
0x18000757b  call    PsmpResourceAwareTimerSetEx
0x180007580  mov     edi, eax
0x180007582  test    eax, eax
0x180007584  js      loc_180007462
0x18000758a  mov     rcx, [rbp+3Fh+var_60]
0x18000758e  mov     edi, r15d
0x180007591  mov     rax, [rbx+30h]
0x180007595  mov     [rbp+3Fh+var_84], r15d
0x180007599  mov     [rcx], rax
0x18000759c  jmp     loc_180007462
0x1800075a1  mov     r13, [rbp+3Fh+pSid]
0x1800075a5  jmp     loc_180007462
0x1800075aa  mov     rax, [r14+0C8h]
0x1800075b1  lea     r13, [r14+1AC8h]
0x1800075b8  jmp     loc_1800072E1
0x1800075bd  mov     rax, [rbp+3Fh+var_90]
0x1800075c1  mov     [rsi+28h], rax
0x1800075c5  mov     rax, [rbp+3Fh+var_58]
0x1800075c9  mov     [rbp+3Fh+var_50], rax
0x1800075cd  mov     rax, [rbp+3Fh+var_70]
0x1800075d1  mov     [rsi+58h], r15
0x1800075d5  mov     [rbp+3Fh+var_90], rcx
0x1800075d9  mov     [rbp+3Fh+var_58], rcx
0x1800075dd  mov     rcx, rsi
0x1800075e0  movups  xmm0, xmmword ptr [rax]
0x1800075e3  mov     rax, [rbp+3Fh+var_80]
0x1800075e7  mov     [rsi+60h], rax
0x1800075eb  movdqu  xmmword ptr [rsi+44h], xmm0
0x1800075f0  mov     [rsi+18h], r14
0x1800075f4  mov     dword ptr [rsi+10h], 1
0x1800075fb  call    PsmpResourceAwareTimerReference
0x180007600  lea     rdi, [r14+148h]
0x180007607  mov     rcx, rdi
0x18000760a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180007610  mov     rax, [r13+8]
0x180007614  cmp     [rax], r13
0x180007617  jnz     short loc_180007688
0x180007619  mov     [rsi], r13
0x18000761c  mov     rcx, rdi
0x18000761f  mov     [rsi+8], rax
0x180007623  xor     r15d, r15d
0x180007626  mov     [rax], rsi
0x180007629  mov     [r13+8], rsi
0x18000762d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180007633  xor     edi, edi
0x180007635  jmp     loc_1800073FF
0x18000763a  lea     r15, [r14+148h]
0x180007641  mov     rcx, r15
0x180007644  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000764a  mov     rax, [rbx]
0x18000764d  cmp     rax, rbx
0x180007650  jz      short loc_180007677
0x180007652  cmp     [rax+8], rbx
0x180007656  jnz     short loc_180007688
0x180007658  mov     rcx, [rbx+8]
0x18000765c  cmp     [rcx], rbx
0x18000765f  jnz     short loc_180007688
0x180007661  mov     [rcx], rax
0x180007664  mov     [rax+8], rcx
0x180007668  mov     rcx, rbx; P
0x18000766b  mov     [rbx+8], rbx
0x18000766f  mov     [rbx], rbx
0x180007672  call    PsmpResourceAwareTimerDereference
0x180007677  mov     rcx, r15
0x18000767a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180007680  xor     r15d, r15d
0x180007683  jmp     loc_1800074A2
0x180007688  mov     ecx, 3
0x18000768d  int     29h; Win8: RtlFailFast(ecx)
0x18000768f  mov     edi, 0C000009Ah
0x180007694  jmp     loc_1800073FF
0x180007699  xor     r9d, r9d
0x18000769c  xor     r8d, r8d
0x18000769f  xor     edx, edx
0x1800076a1  call    cs:__imp_TpSetTimer
0x1800076a7  mov     rcx, [rbp+3Fh+var_90]
0x1800076ab  mov     edx, 1
0x1800076b0  call    cs:__imp_TpWaitForTimer
0x1800076b6  mov     rcx, [rbp+3Fh+var_90]
0x1800076ba  call    cs:__imp_TpReleaseTimer
  ... truncated ...
```
