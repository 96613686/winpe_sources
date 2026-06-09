# NsiRegisterChangeNotificationEx

- ea: `0x140021820`
- end: `0x140021d23`
- name: `NsiRegisterChangeNotificationEx`
- size: `1283`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004fa00`

## callees

- `0x140021820`
- `0x1400223f0`
- `0x140023a40`
- `0x140023c30`
- `0x140025a60`
- `0x14004f3bc`
- `0x140050b00`
- `0x140050ea4`
- `0x14005f044`
- `0x14005f0b0`
- `0x14005f1c4`
- `0x140077fa0`
- `0x140078080`
- `0x140078400`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14007ae9f`
- `ntoskrnl!KeSetEvent` at `0x14007ae9f`
- `ntoskrnl!KeInitializeEvent` at `0x140021aae`
- `ntoskrnl!KeInitializeEvent` at `0x140021ac5`
- `ntoskrnl!KeInitializeEvent` at `0x140021aae`
- `ntoskrnl!KeInitializeEvent` at `0x140021ac5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400218ee`
- `ntoskrnl!KeWaitForSingleObject` at `0x140021934`
- `ntoskrnl!KeWaitForSingleObject` at `0x140021b1f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007ae82`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400218ee`
- `ntoskrnl!KeWaitForSingleObject` at `0x140021934`
- `ntoskrnl!KeWaitForSingleObject` at `0x140021b1f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007ae82`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007acce`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007adce`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007ae41`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007acce`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007adce`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007ae41`
- `ntoskrnl!KeReleaseMutex` at `0x14002194f`
- `ntoskrnl!KeReleaseMutex` at `0x140021964`
- `ntoskrnl!KeReleaseMutex` at `0x140021ba8`
- `ntoskrnl!KeReleaseMutex` at `0x140021bbd`
- `ntoskrnl!KeReleaseMutex` at `0x14007aeb0`
- `ntoskrnl!KeReleaseMutex` at `0x14002194f`
- `ntoskrnl!KeReleaseMutex` at `0x140021964`
- `ntoskrnl!KeReleaseMutex` at `0x140021ba8`
- `ntoskrnl!KeReleaseMutex` at `0x140021bbd`
- `ntoskrnl!KeReleaseMutex` at `0x14007aeb0`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002187d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002187d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021c13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021c13`

## pseudocode

```c
__int64 __fastcall NsiRegisterChangeNotificationEx(__int64 a1)
{
  char *v2; // r15
  int v3; // esi
  int v4; // ecx
  int v5; // edx
  __int64 v6; // rdx
  __int64 NmpContext; // rax
  __int64 v8; // r8
  __int64 v9; // r14
  __int64 v10; // r13
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // r12
  __int64 v14; // rdx
  __int64 v15; // r12
  __int64 LowPriority; // rax
  char *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // rax
  __int64 v23; // r12
  int v24; // ebx
  int v25; // r13d
  __int128 *v26; // r14
  unsigned int v27; // r9d
  __int64 v28; // r8
  __int64 v29; // rax
  __int128 *v30; // rdx
  unsigned __int8 CurrentProcessId; // al
  _QWORD *v32; // rcx
  unsigned int v33; // eax
  int v34; // ebx
  __int64 v35; // r8
  unsigned int v36; // eax
  int v37; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+68h] [rbp-98h] BYREF
  __int128 v39; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+80h] [rbp-80h]
  _QWORD v41[10]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v42; // [rsp+E0h] [rbp-20h] BYREF

  v2 = 0;
  memset(v41, 0, sizeof(v41));
  v3 = 0;
  v4 = *(_DWORD *)(a1 + 48);
  v5 = *(_DWORD *)(a1 + 52);
  v37 = v4;
  LODWORD(v38) = v5;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    v22 = *(_QWORD *)(a1 + 8);
    v23 = *(_QWORD *)(a1 + 24);
    v24 = *(_DWORD *)(a1 + 56);
    v25 = *(_DWORD *)(a1 + 16);
    v26 = (__int128 *)(v22 + 8);
    v42 = 0;
    if ( !v22 )
      v26 = &v42;
    if ( !v24 )
    {
      CurrentProcessId = (unsigned __int8)PsGetCurrentProcessId();
      v4 = v37;
      LOBYTE(v24) = CurrentProcessId;
      v5 = v38;
    }
    if ( !v4 && !v5 )
    {
      NdisGetCurrentThreadCompartmentScope(&v37, &v38);
      LOBYTE(v4) = v37;
      v5 = v38;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_s_guid_dddqdd(
        WPP_GLOBAL_Control->AttachedDevice,
        v5,
        (_DWORD)WPP_GLOBAL_Control,
        (unsigned int)"NsiRegisterChangeNotificationEx",
        (__int64)v26,
        v25,
        1,
        v24,
        v23,
        v5,
        v4);
    }
  }
  if ( KeGetCurrentIrql() >= 2u || (LOBYTE(v6) = 1, v9 = 0, v3 = NsipAccessCheck(a1, v6, 0), v3 >= 0) )
  {
    NmpContext = NsipGetNmpContext(a1);
    v9 = NmpContext;
    if ( !NmpContext )
    {
      v3 = -1073741637;
      goto LABEL_11;
    }
    v8 = *(unsigned int *)(a1 + 16);
    v10 = *(_QWORD *)(NmpContext + 48);
    v37 = v8;
    v11 = *(unsigned int *)(v10 + 4);
    if ( (unsigned int)v8 >= (unsigned int)v11
      || (v12 = *(_QWORD *)(v10 + 8), v13 = (unsigned int)v8, v38 = 104 * v8, !*(_QWORD *)(104 * v8 + v12 + 72)) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids);
      }
      v3 = -1073741811;
      goto LABEL_11;
    }
    KeWaitForSingleObject((PVOID)(v9 + 136), Executive, 0, 0, 0);
    v14 = *(_QWORD *)(v9 + 72);
    if ( !v14 )
    {
      LowPriority = NsipAllocateLowPriority(24 * v11);
      v14 = LowPriority;
      if ( !LowPriority )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            48,
            WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids,
            (unsigned int)(24 * v11));
        }
        goto LABEL_19;
      }
      v27 = 0;
      if ( (_DWORD)v11 )
      {
        v28 = 0;
        do
        {
          ++v27;
          v32 = (_QWORD *)(LowPriority + 24 * v28++);
          v32[1] = v32;
          *v32 = v32;
          v32[2] = 0;
        }
        while ( v27 < (unsigned int)v11 );
      }
      *(_QWORD *)(v9 + 72) = LowPriority;
    }
    if ( !*(_QWORD *)(a1 + 24) )
    {
      v15 = 3 * v13;
      if ( *(_DWORD *)(v14 + 8 * v15 + 20)
        || *(_DWORD *)(v14 + 8 * v15 + 16)
        || (v41[0] = *(_QWORD *)(v9 + 40),
            v41[1] = *(_QWORD *)(v38 + *(_QWORD *)(v10 + 8) + 24),
            v3 = (*(__int64 (__fastcall **)(_QWORD *))(v38 + *(_QWORD *)(v10 + 8) + 72))(v41),
            v3 >= 0) )
      {
        KeWaitForSingleObject((PVOID)(v9 + 80), Executive, 0, 0, 0);
        ++*(_DWORD *)(*(_QWORD *)(v9 + 72) + 8 * v15 + 16);
        KeReleaseMutex((PRKMUTEX)(v9 + 80), 0);
      }
      else
      {
        v3 = 0;
      }
      goto LABEL_10;
    }
    **(_QWORD **)(a1 + 64) = 0;
    if ( !*(_DWORD *)(a1 + 48) && !*(_DWORD *)(a1 + 52) )
      NdisGetCurrentThreadCompartmentScope(a1 + 48, a1 + 52);
    v18 = (char *)NsipAllocateLowPriority(112);
    v2 = v18;
    if ( v18 )
    {
      memset(v18, 0, 0x70u);
      *((_DWORD *)v2 + 12) = 1;
      KeInitializeEvent((PRKEVENT)(v2 + 56), NotificationEvent, *(_BYTE *)(a1 + 32) == 0);
      KeInitializeEvent((PRKEVENT)(v2 + 80), SynchronizationEvent, 0);
      *((_QWORD *)v2 + 3) = *(_QWORD *)(a1 + 24);
      *((_QWORD *)v2 + 4) = *(_QWORD *)(a1 + 40);
      *((_QWORD *)v2 + 5) = *(_QWORD *)(a1 + 48);
      v2[16] = 0;
      *((_DWORD *)v2 + 26) = *(_DWORD *)(a1 + 56);
      v19 = *(_QWORD *)(v9 + 72);
      if ( *(_DWORD *)(v19 + 24 * v13 + 20)
        || *(_DWORD *)(v19 + 24 * v13 + 16)
        || (v41[0] = *(_QWORD *)(v9 + 40),
            v41[1] = *(_QWORD *)(v38 + *(_QWORD *)(v10 + 8) + 24),
            v3 = (*(__int64 (__fastcall **)(_QWORD *))(v38 + *(_QWORD *)(v10 + 8) + 72))(v41),
            v3 >= 0) )
      {
        KeWaitForSingleObject((PVOID)(v9 + 80), Executive, 0, 0, 0);
        if ( !*(_BYTE *)(a1 + 32) )
          *((_DWORD *)v2 + 5) = 1;
        ++*(_DWORD *)(*(_QWORD *)(v9 + 72) + 24 * v13 + 20);
        v20 = *(_QWORD *)(v9 + 72) + 24 * v13;
        v21 = *(_QWORD **)(v20 + 8);
        if ( *v21 != v20 )
          __fastfail(3u);
        *(_QWORD *)v2 = v20;
        *((_QWORD *)v2 + 1) = v21;
        *v21 = v2;
        *(_QWORD *)(v20 + 8) = v2;
        KeReleaseMutex((PRKMUTEX)(v9 + 80), 0);
        KeReleaseMutex((PRKMUTEX)(v9 + 136), 0);
        if ( *(_BYTE *)(a1 + 32) == 1 )
        {
          v42 = 0;
          v40 = 0;
          v39 = 0;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || BYTE1(WPP_GLOBAL_Control->Timer) < 5u
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
          {
            v34 = v37;
          }
          else
          {
            v33 = *(_DWORD *)(a1 + 56);
            if ( !v33 )
              v33 = (unsigned int)PsGetCurrentProcessId();
            v34 = v37;
            WPP_SF_qDd(WPP_GLOBAL_Control->AttachedDevice, 49, v8, *(_QWORD *)(a1 + 24), v33, v37);
          }
          (*(void (__fastcall **)(_QWORD, __int128 *, __int128 *, __int64))(a1 + 24))(
            *(_QWORD *)(a1 + 40),
            &v42,
            &v39,
            3);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
          {
            v36 = *(_DWORD *)(a1 + 56);
            if ( !v36 )
              v36 = (unsigned int)PsGetCurrentProcessId();
            WPP_SF_qDd(WPP_GLOBAL_Control->AttachedDevice, 50, v35, *(_QWORD *)(a1 + 24), v36, v34);
          }
          KeWaitForSingleObject((PVOID)(v9 + 80), Executive, 0, 0, 0);
          *((_DWORD *)v2 + 5) = 1;
          KeSetEvent((PRKEVENT)(v2 + 56), 0, 0);
          KeReleaseMutex((PRKMUTEX)(v9 + 80), 0);
        }
        goto LABEL_11;
      }
      ExFreePoolWithTag(v2, 0);
      v2 = 0;
LABEL_10:
      KeReleaseMutex((PRKMUTEX)(v9 + 136), 0);
      goto LABEL_11;
    }
LABEL_19:
    v3 = -1073741670;
    goto LABEL_10;
  }
LABEL_11:
  **(_QWORD **)(a1 + 64) = v2;
  if ( v9 )
    NsipDereferenceNmpContext(v9);
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    v29 = *(_QWORD *)(a1 + 8);
    v42 = 0;
    v30 = (__int128 *)(v29 + 8);
    if ( !v29 )
      v30 = &v42;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_s_guid_dddqddD(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v30,
        v8,
        (unsigned int)"NsiRegisterChangeNotificationEx",
        (__int64)v30,
        *(_DWORD *)(a1 + 16),
        1,
        *(_DWORD *)(a1 + 56),
        *(_QWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 52),
        *(_DWORD *)(a1 + 48),
        v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140021820  push    rbp
0x140021822  push    rbx
0x140021823  push    rsi
0x140021824  push    rdi
0x140021825  push    r12
0x140021827  push    r13
0x140021829  push    r14
0x14002182b  push    r15
0x14002182d  lea     rbp, [rsp-8]
0x140021832  sub     rsp, 108h
0x140021839  mov     rax, cs:__security_cookie
0x140021840  xor     rax, rsp
0x140021843  mov     [rbp+40h+var_50], rax
0x140021847  mov     rdi, rcx
0x14002184a  xor     r15d, r15d
0x14002184d  xor     edx, edx; Val
0x14002184f  lea     rcx, [rbp+40h+var_B0]; void *
0x140021853  lea     r8d, [r15+50h]; Size
0x140021857  call    memset
0x14002185c  mov     rax, cs:WPP_GLOBAL_Control
0x140021863  xor     esi, esi
0x140021865  mov     ecx, [rdi+30h]
0x140021868  mov     edx, [rdi+34h]
0x14002186b  mov     [rsp+140h+var_E0], ecx
0x14002186f  mov     dword ptr [rsp+140h+var_D8], edx
0x140021873  cmp     byte ptr [rax+29h], 5
0x140021877  jnb     loc_140021C27
0x14002187d  call    cs:__imp_KeGetCurrentIrql
0x140021884  nop     dword ptr [rax+rax+00h]
0x140021889  cmp     al, 2
0x14002188b  jb      loc_1400219BF
0x140021891  mov     rcx, rdi
0x140021894  call    NsipGetNmpContext
0x140021899  mov     r14, rax
0x14002189c  test    rax, rax
0x14002189f  jz      loc_140021C5E
0x1400218a5  mov     r8d, [rdi+10h]
0x1400218a9  mov     r13, [rax+30h]
0x1400218ad  mov     [rsp+140h+var_E0], r8d
0x1400218b2  mov     ebx, [r13+4]
0x1400218b6  cmp     r8d, ebx
0x1400218b9  jnb     loc_140021B59
0x1400218bf  mov     rax, [r13+8]
0x1400218c3  mov     r12d, r8d
0x1400218c6  imul    rcx, r8, 68h ; 'h'
0x1400218ca  mov     [rsp+140h+var_D8], rcx
0x1400218cf  cmp     [rcx+rax+48h], r15
0x1400218d4  jz      loc_140021B59
0x1400218da  lea     rcx, [r14+88h]; Object
0x1400218e1  mov     [rsp+140h+Timeout], r15; Timeout
0x1400218e6  xor     r9d, r9d; Alertable
0x1400218e9  xor     r8d, r8d; WaitMode
0x1400218ec  xor     edx, edx; WaitReason
0x1400218ee  call    cs:__imp_KeWaitForSingleObject
0x1400218f5  nop     dword ptr [rax+rax+00h]
0x1400218fa  mov     rdx, [r14+48h]
0x1400218fe  xor     r10d, r10d
0x140021901  test    rdx, rdx
0x140021904  jz      loc_1400219DB
0x14002190a  cmp     [rdi+18h], r10
0x14002190e  jnz     loc_140021A64
0x140021914  lea     r12, [r12+r12*2]
0x140021918  cmp     [rdx+r12*8+14h], r10d
0x14002191d  jz      loc_140021A18
0x140021923  xor     r9d, r9d; Alertable
0x140021926  mov     [rsp+140h+Timeout], r10; Timeout
0x14002192b  xor     r8d, r8d; WaitMode
0x14002192e  lea     rcx, [r14+50h]; Object
0x140021932  xor     edx, edx; WaitReason
0x140021934  call    cs:__imp_KeWaitForSingleObject
0x14002193b  nop     dword ptr [rax+rax+00h]
0x140021940  mov     rax, [r14+48h]
0x140021944  lea     rcx, [r14+50h]; Mutex
0x140021948  xor     edx, edx; Wait
0x14002194a  inc     dword ptr [rax+r12*8+10h]
0x14002194f  call    cs:__imp_KeReleaseMutex
0x140021956  nop     dword ptr [rax+rax+00h]
0x14002195b  xor     edx, edx; Wait
0x14002195d  lea     rcx, [r14+88h]; Mutex
0x140021964  call    cs:__imp_KeReleaseMutex
0x14002196b  nop     dword ptr [rax+rax+00h]
0x140021970  lea     r13, WPP_GLOBAL_Control
0x140021977  mov     rax, [rdi+40h]
0x14002197b  mov     [rax], r15
0x14002197e  test    r14, r14
0x140021981  jz      short loc_14002198B
0x140021983  mov     rcx, r14
0x140021986  call    NsipDereferenceNmpContext
0x14002198b  mov     rcx, cs:WPP_GLOBAL_Control
0x140021992  cmp     byte ptr [rcx+29h], 5
0x140021996  jnb     loc_140021CF7
0x14002199c  mov     eax, esi
0x14002199e  mov     rcx, [rbp+40h+var_50]
0x1400219a2  xor     rcx, rsp; StackCookie
0x1400219a5  call    __security_check_cookie
0x1400219aa  add     rsp, 108h
0x1400219b1  pop     r15
0x1400219b3  pop     r14
0x1400219b5  pop     r13
0x1400219b7  pop     r12
0x1400219b9  pop     rdi
0x1400219ba  pop     rsi
0x1400219bb  pop     rbx
0x1400219bc  pop     rbp
0x1400219bd  retn
0x1400219bf  xor     r8d, r8d
0x1400219c2  mov     dl, 1
0x1400219c4  mov     rcx, rdi
0x1400219c7  xor     r14d, r14d
0x1400219ca  call    NsipAccessCheck
0x1400219cf  mov     esi, eax
0x1400219d1  test    eax, eax
0x1400219d3  jns     loc_140021891
0x1400219d9  jmp     short loc_140021970
0x1400219db  lea     rcx, [rbx+rbx*2]
0x1400219df  shl     rcx, 3
0x1400219e3  call    NsipAllocateLowPriority
0x1400219e8  xor     r10d, r10d
0x1400219eb  mov     rdx, rax
0x1400219ee  test    rax, rax
0x1400219f1  jnz     loc_140021C9F
0x1400219f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400219fe  lea     rax, WPP_GLOBAL_Control
0x140021a05  cmp     rcx, rax
0x140021a08  jnz     loc_140021C68
0x140021a0e  mov     esi, 0C000009Ah
0x140021a13  jmp     loc_14002195B
0x140021a18  cmp     [rdx+r12*8+10h], r10d
0x140021a1d  jnz     loc_140021923
0x140021a23  mov     rax, [r14+28h]
0x140021a27  mov     rdx, [rsp+140h+var_D8]
0x140021a2c  mov     [rbp+40h+var_B0], rax
0x140021a30  mov     rax, [r13+8]
0x140021a34  mov     rcx, [rdx+rax+18h]
0x140021a39  mov     [rbp+40h+var_A8], rcx
0x140021a3d  lea     rcx, [rbp+40h+var_B0]
0x140021a41  mov     rax, [r13+8]
0x140021a45  mov     rax, [rdx+rax+48h]
0x140021a4a  call    _guard_dispatch_icall
0x140021a4f  xor     r10d, r10d
0x140021a52  mov     esi, eax
0x140021a54  test    eax, eax
0x140021a56  jns     loc_140021923
0x140021a5c  mov     esi, r10d
0x140021a5f  jmp     loc_14002195B
0x140021a64  mov     rax, [rdi+40h]
0x140021a68  lea     rbx, [rdi+30h]
0x140021a6c  mov     [rax], r10
0x140021a6f  cmp     [rbx], r10d
0x140021a72  jz      loc_140021B7A
0x140021a78  mov     ecx, 70h ; 'p'
0x140021a7d  call    NsipAllocateLowPriority
0x140021a82  mov     r15, rax
0x140021a85  test    rax, rax
0x140021a88  jz      short loc_140021A0E
0x140021a8a  xor     edx, edx; Val
0x140021a8c  mov     rcx, rax; void *
0x140021a8f  lea     r8d, [rdx+70h]; Size
0x140021a93  call    memset
0x140021a98  mov     dword ptr [r15+30h], 1
0x140021aa0  lea     rcx, [r15+38h]; Event
0x140021aa4  cmp     byte ptr [rdi+20h], 0
0x140021aa8  setz    r8b; State
0x140021aac  xor     edx, edx; Type
0x140021aae  call    cs:__imp_KeInitializeEvent
0x140021ab5  nop     dword ptr [rax+rax+00h]
0x140021aba  xor     r8d, r8d; State
0x140021abd  lea     rcx, [r15+50h]; Event
0x140021ac1  lea     edx, [r8+1]; Type
0x140021ac5  call    cs:__imp_KeInitializeEvent
0x140021acc  nop     dword ptr [rax+rax+00h]
0x140021ad1  mov     rax, [rdi+18h]
0x140021ad5  xor     ecx, ecx
0x140021ad7  mov     [r15+18h], rax
0x140021adb  mov     rax, [rdi+28h]
0x140021adf  mov     [r15+20h], rax
0x140021ae3  mov     rax, [rbx]
0x140021ae6  lea     rbx, [r12+r12*2]
0x140021aea  mov     [r15+28h], rax
0x140021aee  mov     [r15+10h], cl
0x140021af2  mov     eax, [rdi+38h]
0x140021af5  mov     [r15+68h], eax
0x140021af9  mov     rax, [r14+48h]
0x140021afd  cmp     [rax+rbx*8+14h], ecx
0x140021b01  jz      loc_140021CB2
0x140021b07  lea     r12, [r14+50h]
0x140021b0b  mov     [rsp+140h+Timeout], 0; Timeout
0x140021b14  mov     rcx, r12; Object
0x140021b17  xor     r9d, r9d; Alertable
0x140021b1a  xor     r8d, r8d; WaitMode
0x140021b1d  xor     edx, edx; WaitReason
0x140021b1f  call    cs:__imp_KeWaitForSingleObject
0x140021b26  nop     dword ptr [rax+rax+00h]
0x140021b2b  cmp     byte ptr [rdi+20h], 0
0x140021b2f  jnz     short loc_140021B39
0x140021b31  mov     dword ptr [r15+14h], 1
0x140021b39  mov     rax, [r14+48h]
0x140021b3d  inc     dword ptr [rax+rbx*8+14h]
0x140021b41  mov     rax, [r14+48h]
0x140021b45  lea     rcx, [rax+rbx*8]
0x140021b49  mov     rax, [rcx+8]
0x140021b4d  cmp     [rax], rcx
0x140021b50  jz      short loc_140021B95
0x140021b52  mov     ecx, 3
0x140021b57  int     29h; Win8: RtlFailFast(ecx)
0x140021b59  mov     rcx, cs:WPP_GLOBAL_Control
0x140021b60  lea     r13, WPP_GLOBAL_Control
0x140021b67  cmp     rcx, r13
0x140021b6a  jnz     loc_140021CC1
0x140021b70  mov     esi, 0C000000Dh
0x140021b75  jmp     loc_140021977
0x140021b7a  cmp     [rdi+34h], r10d
0x140021b7e  jnz     loc_140021A78
0x140021b84  lea     rdx, [rdi+34h]
0x140021b88  mov     rcx, rbx
0x140021b8b  call    NdisGetCurrentThreadCompartmentScope
0x140021b90  jmp     loc_140021A78
0x140021b95  mov     [r15], rcx
0x140021b98  xor     edx, edx; Wait
0x140021b9a  mov     [r15+8], rax
0x140021b9e  mov     [rax], r15
0x140021ba1  mov     [rcx+8], r15
0x140021ba5  mov     rcx, r12; Mutex
0x140021ba8  call    cs:__imp_KeReleaseMutex
0x140021baf  nop     dword ptr [rax+rax+00h]
0x140021bb4  xor     edx, edx; Wait
0x140021bb6  lea     rcx, [r14+88h]; Mutex
0x140021bbd  call    cs:__imp_KeReleaseMutex
0x140021bc4  nop     dword ptr [rax+rax+00h]
0x140021bc9  cmp     byte ptr [rdi+20h], 1
0x140021bcd  jnz     loc_140021970
0x140021bd3  jmp     loc_14007AD92
0x140021bd8  mov     rax, [r14+28h]
0x140021bdc  mov     rdx, [rsp+140h+var_D8]
0x140021be1  mov     [rbp+40h+var_B0], rax
0x140021be5  mov     rax, [r13+8]
0x140021be9  mov     rcx, [rdx+rax+18h]
0x140021bee  mov     [rbp+40h+var_A8], rcx
0x140021bf2  lea     rcx, [rbp+40h+var_B0]
0x140021bf6  mov     rax, [r13+8]
0x140021bfa  mov     rax, [rdx+rax+48h]
0x140021bff  call    _guard_dispatch_icall
0x140021c04  mov     esi, eax
0x140021c06  test    eax, eax
0x140021c08  jns     loc_140021B07
0x140021c0e  xor     edx, edx; Tag
0x140021c10  mov     rcx, r15; P
0x140021c13  call    cs:__imp_ExFreePoolWithTag
0x140021c1a  nop     dword ptr [rax+rax+00h]
0x140021c1f  xor     r15d, r15d
0x140021c22  jmp     loc_14002195B
0x140021c27  mov     eax, [rax+2Ch]
0x140021c2a  test    al, 10h
0x140021c2c  jz      loc_14002187D
0x140021c32  mov     rax, [rdi+8]
0x140021c36  xorps   xmm0, xmm0
0x140021c39  mov     r12, [rdi+18h]
0x140021c3d  mov     ebx, [rdi+38h]
0x140021c40  mov     r13d, [rdi+10h]
0x140021c44  lea     r14, [rax+8]
0x140021c48  movups  [rbp+40h+var_60], xmm0
0x140021c4c  test    rax, rax
0x140021c4f  jnz     loc_14007ACCA
0x140021c55  lea     r14, [rbp+40h+var_60]
0x140021c59  jmp     loc_14007ACCA
0x140021c5e  mov     esi, 0C00000BBh
0x140021c63  jmp     loc_140021970
0x140021c68  cmp     byte ptr [rcx+29h], 2
0x140021c6c  jb      loc_140021A0E
0x140021c72  mov     eax, [rcx+2Ch]
0x140021c75  test    al, 10h
0x140021c77  jz      loc_140021A0E
0x140021c7d  mov     rcx, [rcx+18h]
0x140021c81  lea     r9d, [rbx+rbx*2]
0x140021c85  shl     r9d, 3
0x140021c89  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x140021c90  mov     edx, 30h ; '0'
0x140021c95  call    WPP_SF_d
0x140021c9a  jmp     loc_140021A0E
0x140021c9f  mov     r9d, r10d
0x140021ca2  test    ebx, ebx
0x140021ca4  jz      loc_14007AD89
0x140021caa  mov     r8, r10
0x140021cad  jmp     loc_14007AD6B
0x140021cb2  cmp     [rax+rbx*8+10h], ecx
0x140021cb6  jnz     loc_140021B07
0x140021cbc  jmp     loc_140021BD8
0x140021cc1  cmp     byte ptr [rcx+29h], 2
0x140021cc5  jb      loc_140021B70
0x140021ccb  mov     eax, [rcx+2Ch]
0x140021cce  test    al, 10h
0x140021cd0  jz      loc_140021B70
0x140021cd6  mov     rcx, [rcx+18h]
0x140021cda  mov     r9d, r8d
0x140021cdd  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x140021ce4  mov     dword ptr [rsp+140h+Timeout], ebx
0x140021ce8  mov     edx, 2Fh ; '/'
0x140021ced  call    WPP_SF_Dd
0x140021cf2  jmp     loc_140021B70
0x140021cf7  mov     eax, [rcx+2Ch]
  ... truncated ...
```
