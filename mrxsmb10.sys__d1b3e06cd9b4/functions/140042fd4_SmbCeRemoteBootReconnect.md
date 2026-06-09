# SmbCeRemoteBootReconnect

- ea: `0x140042fd4`
- end: `0x140043220`
- name: `SmbCeRemoteBootReconnect`
- size: `588`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x14003bd40`
- `0x140044c70`
- `0x14004ccf0`

## callees

- `0x14000dfd8`
- `0x14000e998`
- `0x1400104d4`
- `0x140012014`
- `0x140016560`
- `0x1400381d0`
- `0x140042fd4`
- `0x14004ee60`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x140043098`
- `ntoskrnl!IoGetCurrentProcess` at `0x140043098`
- `ntoskrnl!RtlRandom` at `0x14004313f`
- `ntoskrnl!RtlRandom` at `0x14004313f`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400431b2`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400431b2`
- `ntoskrnl!KeStackAttachProcess` at `0x1400430bc`
- `ntoskrnl!KeStackAttachProcess` at `0x1400430bc`
- `ntoskrnl!KeDelayExecutionThread` at `0x140043173`
- `ntoskrnl!KeDelayExecutionThread` at `0x140043173`
- `rdbss!RxGetRDBSSProcess` at `0x140043089`
- `rdbss!RxGetRDBSSProcess` at `0x1400430a9`
- `rdbss!RxGetRDBSSProcess` at `0x140043089`
- `rdbss!RxGetRDBSSProcess` at `0x1400430a9`

## pseudocode

```c
__int64 __fastcall SmbCeRemoteBootReconnect(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v3; // r13
  __int64 v6; // r14
  unsigned int v7; // edi
  struct _KPROCESS *RDBSSProcess; // rbx
  struct _KPROCESS *v9; // rax
  __int64 v10; // rbx
  __int32 v11; // esi
  void *v12; // r12
  union _LARGE_INTEGER v13; // rax
  char v15; // [rsp+20h] [rbp-50h]
  ULONG Seed[2]; // [rsp+28h] [rbp-48h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp-40h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+38h] [rbp-38h] BYREF

  v2 = *(_QWORD *)(a2 + 64);
  v3 = *(_QWORD *)(a2 + 56);
  memset(&ApcState, 0, sizeof(ApcState));
  v6 = *(_QWORD *)(v2 + 32);
  if ( v6 )
    v6 = *(_QWORD *)(v6 + 48);
  *(_QWORD *)Seed = *(_QWORD *)(a1 + 80);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_2ad9b1edddb136952f475e6aa9483122_Traceguids, v3 + 360);
  if ( (*(_BYTE *)(v3 + 256) & 1) != 0 || ((*(_BYTE *)(a2 + 32) - 2) & 0xEF) == 0 )
    return 3221225996LL;
  v7 = 0;
  v15 = 0;
  RDBSSProcess = RxGetRDBSSProcess();
  if ( IoGetCurrentProcess() != RDBSSProcess )
  {
    v9 = RxGetRDBSSProcess();
    KeStackAttachProcess(v9, &ApcState);
    v15 = 1;
  }
  if ( (*(_DWORD *)(v3 + 156) & 4) == 0 )
  {
    v10 = qword_140020338;
    v11 = _InterlockedExchange((volatile __int32 *)(v6 + 128), 1);
    SmbCeUninitializeExchangeTransport(a1);
    v12 = *(void **)Seed;
    while ( 1 )
    {
      v7 = MRxSmbDeferredCreate(a2);
      if ( v7 == -1073741300 )
      {
        SmbCeTransportDisconnectIndicated(v12);
      }
      else if ( !v7 )
      {
        goto LABEL_16;
      }
      Interval.QuadPart = 0xFFFFFFFF00000000uLL;
      *(_QWORD *)Seed = MEMORY[0xFFFFF78000000014];
      v13.QuadPart = -(__int64)(RtlRandom(Seed) % 0x2FAF080);
      v10 += v13.QuadPart;
      Interval = v13;
      KeDelayExecutionThread(0, 0, &Interval);
LABEL_16:
      if ( !(unsigned __int8)SmbCeIsReconnectableError(v7) || v10 <= 0 )
      {
        if ( !v11 )
          *(_DWORD *)(v6 + 128) = 0;
        if ( v7 )
          v7 = -1073741632;
        break;
      }
    }
  }
  if ( v15 )
    KeUnstackDetachProcess(&ApcState);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_2ad9b1edddb136952f475e6aa9483122_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x140042fd4  mov     [rsp-38h+arg_10], rbx
0x140042fd9  push    rbp
0x140042fda  push    rsi
0x140042fdb  push    rdi
0x140042fdc  push    r12
0x140042fde  push    r13
0x140042fe0  push    r14
0x140042fe2  push    r15
0x140042fe4  mov     rbp, rsp
0x140042fe7  sub     rsp, 70h
0x140042feb  mov     rax, cs:__security_cookie
0x140042ff2  xor     rax, rsp
0x140042ff5  mov     [rbp+var_8], rax
0x140042ff9  mov     rax, [rdx+40h]
0x140042ffd  xorps   xmm0, xmm0
0x140043000  mov     r13, [rdx+38h]
0x140043004  mov     r15, rdx
0x140043007  movups  xmmword ptr [rbp+ApcState.ApcListHead.Flink], xmm0
0x14004300b  mov     r12, rcx
0x14004300e  movups  xmmword ptr [rbp+ApcState.ApcListHead.Flink+10h], xmm0
0x140043012  movups  xmmword ptr [rbp+ApcState.Process], xmm0
0x140043016  mov     r14, [rax+20h]
0x14004301a  test    r14, r14
0x14004301d  jz      short loc_140043023
0x14004301f  mov     r14, [r14+30h]
0x140043023  mov     rax, [rcx+50h]
0x140043027  mov     qword ptr [rbp+Seed], rax
0x14004302b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140043032  lea     rax, WPP_GLOBAL_Control
0x140043039  cmp     rcx, rax
0x14004303c  jz      short loc_140043063
0x14004303e  test    dword ptr [rcx+2Ch], 200h
0x140043045  jz      short loc_140043063
0x140043047  mov     rcx, [rcx+18h]
0x14004304b  lea     r9, [r13+168h]
0x140043052  mov     edx, 0Ah
0x140043057  lea     r8, WPP_2ad9b1edddb136952f475e6aa9483122_Traceguids
0x14004305e  call    WPP_SF_Z
0x140043063  mov     esi, 1
0x140043068  test    [r13+100h], sil
0x14004306f  jnz     loc_1400431F6
0x140043075  mov     al, [r15+20h]
0x140043079  sub     al, 2
0x14004307b  test    al, 0EFh
0x14004307d  jz      loc_1400431F6
0x140043083  xor     edi, edi
0x140043085  mov     [rbp+var_50], dil
0x140043089  call    cs:__imp_RxGetRDBSSProcess
0x140043090  nop     dword ptr [rax+rax+00h]
0x140043095  mov     rbx, rax
0x140043098  call    cs:__imp_IoGetCurrentProcess
0x14004309f  nop     dword ptr [rax+rax+00h]
0x1400430a4  cmp     rax, rbx
0x1400430a7  jz      short loc_1400430CC
0x1400430a9  call    cs:__imp_RxGetRDBSSProcess
0x1400430b0  nop     dword ptr [rax+rax+00h]
0x1400430b5  mov     rcx, rax; PROCESS
0x1400430b8  lea     rdx, [rbp+ApcState]; ApcState
0x1400430bc  call    cs:__imp_KeStackAttachProcess
0x1400430c3  nop     dword ptr [rax+rax+00h]
0x1400430c8  mov     [rbp+var_50], sil
0x1400430cc  mov     eax, [r13+9Ch]
0x1400430d3  test    al, 4
0x1400430d5  jnz     loc_1400431A8
0x1400430db  mov     rbx, cs:qword_140020338
0x1400430e2  mov     rcx, r12
0x1400430e5  xchg    esi, [r14+80h]
0x1400430ec  call    SmbCeUninitializeExchangeTransport
0x1400430f1  mov     r12, qword ptr [rbp+Seed]
0x1400430f5  mov     rcx, r15
0x1400430f8  call    MRxSmbDeferredCreate
0x1400430fd  mov     edi, eax
0x1400430ff  cmp     eax, 0C000020Ch
0x140043104  jnz     short loc_140043110
0x140043106  mov     rcx, r12; pContext
0x140043109  call    SmbCeTransportDisconnectIndicated
0x14004310e  jmp     short loc_140043114
0x140043110  test    edi, edi
0x140043112  jz      short loc_14004317F
0x140043114  mov     qword ptr [rbp+Seed], 0
0x14004311c  lea     rcx, [rbp+Seed]; Seed
0x140043120  mov     dword ptr [rbp+Interval], 0
0x140043127  mov     rax, 0FFFFF78000000014h
0x140043131  mov     dword ptr [rbp+Interval+4], 0FFFFFFFFh
0x140043138  mov     rax, [rax]
0x14004313b  mov     qword ptr [rbp+Seed], rax
0x14004313f  call    cs:__imp_RtlRandom
0x140043146  nop     dword ptr [rax+rax+00h]
0x14004314b  mov     ecx, eax
0x14004314d  lea     r8, [rbp+Interval]; Interval
0x140043151  mov     eax, 55E63B89h
0x140043156  mul     ecx
0x140043158  shr     edx, 18h
0x14004315b  imul    eax, edx, 2FAF080h
0x140043161  xor     edx, edx; Alertable
0x140043163  sub     ecx, eax
0x140043165  mov     eax, ecx
0x140043167  xor     ecx, ecx; WaitMode
0x140043169  neg     rax
0x14004316c  add     rbx, rax
0x14004316f  mov     qword ptr [rbp+Interval], rax
0x140043173  call    cs:__imp_KeDelayExecutionThread
0x14004317a  nop     dword ptr [rax+rax+00h]
0x14004317f  mov     ecx, edi
0x140043181  call    SmbCeIsReconnectableError
0x140043186  test    al, al
0x140043188  jz      short loc_140043193
0x14004318a  test    rbx, rbx
0x14004318d  jg      loc_1400430F5
0x140043193  test    esi, esi
0x140043195  jnz     short loc_14004319E
0x140043197  mov     [r14+80h], esi
0x14004319e  test    edi, edi
0x1400431a0  mov     eax, 0C00000C0h
0x1400431a5  cmovnz  edi, eax
0x1400431a8  cmp     [rbp+var_50], 0
0x1400431ac  jz      short loc_1400431BE
0x1400431ae  lea     rcx, [rbp+ApcState]; ApcState
0x1400431b2  call    cs:__imp_KeUnstackDetachProcess
0x1400431b9  nop     dword ptr [rax+rax+00h]
0x1400431be  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400431c5  lea     rax, WPP_GLOBAL_Control
0x1400431cc  cmp     rcx, rax
0x1400431cf  jz      short loc_1400431F2
0x1400431d1  test    dword ptr [rcx+2Ch], 200h
0x1400431d8  jz      short loc_1400431F2
0x1400431da  mov     rcx, [rcx+18h]
0x1400431de  lea     r8, WPP_2ad9b1edddb136952f475e6aa9483122_Traceguids
0x1400431e5  mov     edx, 0Bh
0x1400431ea  mov     r9d, edi
0x1400431ed  call    WPP_SF_d
0x1400431f2  mov     eax, edi
0x1400431f4  jmp     short loc_1400431FB
0x1400431f6  mov     eax, 0C000020Ch
0x1400431fb  mov     rcx, [rbp+var_8]
0x1400431ff  xor     rcx, rsp; StackCookie
0x140043202  call    __security_check_cookie
0x140043207  mov     rbx, [rsp+70h+arg_10]
0x14004320f  add     rsp, 70h
0x140043213  pop     r15
0x140043215  pop     r14
0x140043217  pop     r13
0x140043219  pop     r12
0x14004321b  pop     rdi
0x14004321c  pop     rsi
0x14004321d  pop     rbp
0x14004321e  retn
```
