# NsiDeregisterChangeNotificationEx

- ea: `0x1400224b0`
- end: `0x14002298f`
- name: `NsiDeregisterChangeNotificationEx`
- size: `1247`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005e9c0`

## callees

- `0x140020a48`
- `0x1400223f0`
- `0x1400224b0`
- `0x140023a40`
- `0x14004f3bc`
- `0x140050b00`
- `0x1400512d8`
- `0x14005f0b0`
- `0x14005f1c4`
- `0x140077fa0`
- `0x140078080`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140022577`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400225be`
- `ntoskrnl!KeWaitForSingleObject` at `0x140022659`
- `ntoskrnl!KeWaitForSingleObject` at `0x140022821`
- `ntoskrnl!KeWaitForSingleObject` at `0x140022577`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400225be`
- `ntoskrnl!KeWaitForSingleObject` at `0x140022659`
- `ntoskrnl!KeWaitForSingleObject` at `0x140022821`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007b1b4`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007b1b4`
- `ntoskrnl!KeReleaseMutex` at `0x1400225dc`
- `ntoskrnl!KeReleaseMutex` at `0x140022637`
- `ntoskrnl!KeReleaseMutex` at `0x1400226f0`
- `ntoskrnl!KeReleaseMutex` at `0x140022847`
- `ntoskrnl!KeReleaseMutex` at `0x1400225dc`
- `ntoskrnl!KeReleaseMutex` at `0x140022637`
- `ntoskrnl!KeReleaseMutex` at `0x1400226f0`
- `ntoskrnl!KeReleaseMutex` at `0x140022847`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002266a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022799`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002266a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022799`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022788`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400228be`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022788`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400228be`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140022731`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140022731`

## string_xrefs

- `0x14007b208`: `NsiDeregisterChangeNotificationEx`
- `0x14007b258`: `NsiDeregisterChangeNotificationEx`

## pseudocode

```c
__int64 __fastcall NsiDeregisterChangeNotificationEx(__int64 a1)
{
  char v2; // bp
  bool v3; // cf
  PVOID *v4; // rdi
  __int64 NmpContext; // rax
  __int64 v6; // rbx
  __int64 v7; // rbp
  __int64 v8; // r9
  unsigned int v9; // ecx
  __int64 v10; // rdi
  __int64 v11; // r12
  __int64 v12; // rcx
  void **v13; // r13
  void **v14; // rax
  void **v15; // r14
  char v16; // al
  unsigned int v17; // edi
  int v18; // r8d
  KIRQL v20; // al
  PVOID *v21; // rbx
  KIRQL v22; // dl
  PVOID *v23; // rcx
  PVOID *v24; // rax
  __int64 v25; // rax
  int CurrentProcessId; // ebx
  int v27; // r14d
  __int128 *v28; // rdi
  __int64 v29; // rax
  __int128 *v30; // rax
  int v31; // r8d
  int v32; // [rsp+60h] [rbp-68h] BYREF
  int v33; // [rsp+68h] [rbp-60h] BYREF
  void *v34; // [rsp+70h] [rbp-58h]
  __int128 v35; // [rsp+78h] [rbp-50h] BYREF
  __int128 v36; // [rsp+88h] [rbp-40h] BYREF

  v35 = 0;
  v32 = 0;
  v33 = 0;
  v2 = 0;
  v3 = BYTE1(WPP_GLOBAL_Control->Timer) < 5u;
  v34 = 0;
  if ( !v3 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    v25 = *(_QWORD *)(a1 + 8);
    CurrentProcessId = *(_DWORD *)(a1 + 32);
    v27 = *(_DWORD *)(a1 + 16);
    v36 = 0;
    v28 = (__int128 *)(v25 + 8);
    if ( !v25 )
      v28 = &v36;
    if ( !CurrentProcessId )
      CurrentProcessId = (unsigned __int8)PsGetCurrentProcessId();
    NdisGetCurrentThreadCompartmentScope(&v32, &v33);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_s_guid_dddqdd(
        WPP_GLOBAL_Control->AttachedDevice,
        v32,
        v31,
        (unsigned int)"NsiDeregisterChangeNotificationEx",
        (__int64)v28,
        v27,
        1,
        CurrentProcessId,
        0,
        v33,
        v32);
    }
  }
  v4 = *(PVOID **)(a1 + 24);
  NmpContext = NsipGetNmpContext(a1);
  v6 = NmpContext;
  if ( NmpContext )
  {
    v7 = *(_QWORD *)(NmpContext + 48);
    v8 = *(unsigned int *)(a1 + 16);
    v9 = *(_DWORD *)(v7 + 4);
    if ( (unsigned int)v8 < v9
      && (v10 = (unsigned int)v8, v11 = 104 * v8, *(_QWORD *)(104 * v8 + *(_QWORD *)(v7 + 8) + 80)) )
    {
      KeWaitForSingleObject((PVOID)(NmpContext + 136), Executive, 0, 0, 0);
      v12 = *(_QWORD *)(v6 + 72);
      if ( v12 )
      {
        LOBYTE(v32) = 0;
        v13 = (void **)(v12 + 24 * v10);
        v14 = *(void ***)(a1 + 24);
        if ( v14 )
        {
          v15 = (void **)*v13;
          if ( *v13 == v13 )
            goto LABEL_34;
          while ( v15 != v14 || *((_DWORD *)v15 + 5) != 1 )
          {
            v15 = (void **)*v15;
            if ( v15 == v13 )
              goto LABEL_34;
          }
          if ( v15 == v13 )
          {
LABEL_34:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids);
            }
            v17 = -1073741811;
            goto LABEL_11;
          }
          KeWaitForSingleObject((PVOID)(v6 + 80), Executive, 0, 0, 0);
          --*((_DWORD *)v13 + 5);
          *((_DWORD *)v15 + 5) = 2;
          NsipLockedDereferenceNotificationContext(v15);
          KeReleaseMutex((PRKMUTEX)(v6 + 80), 0);
          v16 = v32;
          if ( !*((_DWORD *)v13 + 5) && !*((_DWORD *)v13 + 4) )
            v16 = 1;
          v34 = v15[3];
        }
        else
        {
          v15 = 0;
          KeWaitForSingleObject((PVOID)(v6 + 80), Executive, 0, 0, 0);
          v33 = --*((_DWORD *)v13 + 4);
          KeReleaseMutex((PRKMUTEX)(v6 + 80), 0);
          if ( *((_DWORD *)v13 + 5) || v33 )
            v16 = v32;
          else
            v16 = 1;
        }
        v17 = 0;
        if ( v16 == 1 )
        {
          *(_QWORD *)&v35 = *(_QWORD *)(v6 + 40);
          *((_QWORD *)&v35 + 1) = *(_QWORD *)(v11 + *(_QWORD *)(v7 + 8) + 24);
          (*(void (__fastcall **)(__int128 *))(v11 + *(_QWORD *)(v7 + 8) + 80))(&v35);
        }
LABEL_11:
        KeReleaseMutex((PRKMUTEX)(v6 + 136), 0);
        if ( v15 )
        {
          KeWaitForSingleObject(v15 + 10, Executive, 0, 0, 0);
          ExFreePoolWithTag(v15, 0);
        }
        goto LABEL_13;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids);
      }
      v17 = -1073741811;
      KeReleaseMutex((PRKMUTEX)(v6 + 136), 0);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids, v8, v9);
      }
      v17 = -1073741811;
    }
LABEL_13:
    NsipDereferenceNmpContext(v6);
    v2 = (char)v34;
LABEL_14:
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      v29 = *(_QWORD *)(a1 + 8);
      v36 = 0;
      if ( v29 )
        v30 = (__int128 *)(v29 + 8);
      else
        v30 = &v36;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_s_guid_dddqddD(
          WPP_GLOBAL_Control->AttachedDevice,
          *(_DWORD *)(a1 + 16),
          v18,
          (unsigned int)"NsiDeregisterChangeNotificationEx",
          (__int64)v30,
          *(_DWORD *)(a1 + 16),
          1,
          *(_DWORD *)(a1 + 32),
          v2,
          0,
          0,
          v17);
    }
    return v17;
  }
  v20 = KeAcquireSpinLockRaiseToDpc(&NsipDeregisterProviderNotificationListLock);
  v21 = (PVOID *)NsipDeregisterProviderNotificationList;
  v22 = v20;
  while ( 1 )
  {
    if ( v21 == &NsipDeregisterProviderNotificationList )
    {
      KeReleaseSpinLock(&NsipDeregisterProviderNotificationListLock, v20);
      v17 = -1073741637;
      goto LABEL_14;
    }
    v23 = (PVOID *)*v21;
    if ( v21 == v4 )
      break;
    v21 = (PVOID *)*v21;
  }
  if ( v23[1] != v21 || (v24 = (PVOID *)v21[1], *v24 != v21) )
    __fastfail(3u);
  *v24 = v23;
  v23[1] = v24;
  KeReleaseSpinLock(&NsipDeregisterProviderNotificationListLock, v22);
  ExFreePoolWithTag(v21, 0);
  return 0;
}

```

## disassembly

```asm
0x1400224b0  mov     [rsp+arg_10], rbx
0x1400224b5  mov     [rsp+arg_18], rbp
0x1400224ba  push    rsi
0x1400224bb  push    rdi
0x1400224bc  push    r13
0x1400224be  push    r14
0x1400224c0  push    r15
0x1400224c2  sub     rsp, 0A0h
0x1400224c9  mov     rax, cs:__security_cookie
0x1400224d0  xor     rax, rsp
0x1400224d3  mov     [rsp+0C8h+var_30], rax
0x1400224db  mov     rax, cs:WPP_GLOBAL_Control
0x1400224e2  lea     r14, WPP_GLOBAL_Control
0x1400224e9  xor     r13d, r13d
0x1400224ec  xorps   xmm0, xmm0
0x1400224ef  movups  [rsp+0C8h+var_50], xmm0
0x1400224f4  mov     [rsp+0C8h+var_68], r13d
0x1400224f9  mov     rsi, rcx
0x1400224fc  mov     [rsp+0C8h+var_60], r13d
0x140022501  mov     ebp, r13d
0x140022504  cmp     byte ptr [rax+29h], 5
0x140022508  mov     r15d, 1
0x14002250e  mov     [rsp+0C8h+var_58], r13
0x140022513  jnb     loc_140022877
0x140022519  mov     rdi, [rsi+18h]
0x14002251d  mov     rcx, rsi
0x140022520  call    NsipGetNmpContext
0x140022525  mov     rbx, rax
0x140022528  test    rax, rax
0x14002252b  jz      loc_14002272A
0x140022531  mov     rbp, [rax+30h]
0x140022535  mov     r9d, [rsi+10h]
0x140022539  mov     [rsp+0C8h+arg_8], r12
0x140022541  mov     ecx, [rbp+4]
0x140022544  cmp     r9d, ecx
0x140022547  jnb     loc_140022701
0x14002254d  mov     rax, [rbp+8]
0x140022551  mov     edi, r9d
0x140022554  imul    r12, r9, 68h ; 'h'
0x140022558  cmp     [r12+rax+50h], r13
0x14002255d  jz      loc_140022701
0x140022563  xor     r9d, r9d; Alertable
0x140022566  mov     [rsp+0C8h+Timeout], r13; Timeout
0x14002256b  xor     r8d, r8d; WaitMode
0x14002256e  lea     rcx, [rbx+88h]; Object
0x140022575  xor     edx, edx; WaitReason
0x140022577  call    cs:__imp_KeWaitForSingleObject
0x14002257e  nop     dword ptr [rax+rax+00h]
0x140022583  mov     rcx, [rbx+48h]
0x140022587  test    rcx, rcx
0x14002258a  jz      loc_1400226D2
0x140022590  lea     rax, [rdi+rdi*2]
0x140022594  mov     byte ptr [rsp+0C8h+var_68], r13b
0x140022599  lea     r13, [rcx+rax*8]
0x14002259d  mov     rax, [rsi+18h]
0x1400225a1  test    rax, rax
0x1400225a4  jnz     loc_1400227C0
0x1400225aa  xor     r14d, r14d
0x1400225ad  lea     rcx, [rbx+50h]; Object
0x1400225b1  xor     r9d, r9d; Alertable
0x1400225b4  mov     [rsp+0C8h+Timeout], r14; Timeout
0x1400225b9  xor     r8d, r8d; WaitMode
0x1400225bc  xor     edx, edx; WaitReason
0x1400225be  call    cs:__imp_KeWaitForSingleObject
0x1400225c5  nop     dword ptr [rax+rax+00h]
0x1400225ca  dec     dword ptr [r13+10h]
0x1400225ce  lea     rcx, [rbx+50h]; Mutex
0x1400225d2  mov     eax, [r13+10h]
0x1400225d6  xor     edx, edx; Wait
0x1400225d8  mov     [rsp+0C8h+var_60], eax
0x1400225dc  call    cs:__imp_KeReleaseMutex
0x1400225e3  nop     dword ptr [rax+rax+00h]
0x1400225e8  cmp     [r13+14h], r14d
0x1400225ec  jz      loc_1400227AC
0x1400225f2  mov     eax, [rsp+0C8h+var_68]
0x1400225f6  xor     r13d, r13d
0x1400225f9  mov     edi, r13d
0x1400225fc  cmp     al, r15b
0x1400225ff  jnz     short loc_14002262E
0x140022601  mov     rax, [rbx+28h]
0x140022605  mov     qword ptr [rsp+0C8h+var_50], rax
0x14002260a  mov     rax, [rbp+8]
0x14002260e  mov     rcx, [r12+rax+18h]
0x140022613  mov     qword ptr [rsp+0C8h+var_50+8], rcx
0x14002261b  lea     rcx, [rsp+0C8h+var_50]
0x140022620  mov     rax, [rbp+8]
0x140022624  mov     rax, [r12+rax+50h]
0x140022629  call    _guard_dispatch_icall
0x14002262e  xor     edx, edx; Wait
0x140022630  lea     rcx, [rbx+88h]; Mutex
0x140022637  call    cs:__imp_KeReleaseMutex
0x14002263e  nop     dword ptr [rax+rax+00h]
0x140022643  test    r14, r14
0x140022646  jz      short loc_140022676
0x140022648  lea     rcx, [r14+50h]; Object
0x14002264c  mov     [rsp+0C8h+Timeout], r13; Timeout
0x140022651  xor     r9d, r9d; Alertable
0x140022654  xor     r8d, r8d; WaitMode
0x140022657  xor     edx, edx; WaitReason
0x140022659  call    cs:__imp_KeWaitForSingleObject
0x140022660  nop     dword ptr [rax+rax+00h]
0x140022665  xor     edx, edx; Tag
0x140022667  mov     rcx, r14; P
0x14002266a  call    cs:__imp_ExFreePoolWithTag
0x140022671  nop     dword ptr [rax+rax+00h]
0x140022676  lea     r14, WPP_GLOBAL_Control
0x14002267d  mov     rcx, rbx
0x140022680  call    NsipDereferenceNmpContext
0x140022685  mov     rbp, [rsp+0C8h+var_58]
0x14002268a  mov     r12, [rsp+0C8h+arg_8]
0x140022692  mov     rcx, cs:WPP_GLOBAL_Control
0x140022699  cmp     byte ptr [rcx+29h], 5
0x14002269d  jnb     loc_140022963
0x1400226a3  mov     eax, edi
0x1400226a5  mov     rcx, [rsp+0C8h+var_30]
0x1400226ad  xor     rcx, rsp; StackCookie
0x1400226b0  call    __security_check_cookie
0x1400226b5  lea     r11, [rsp+0C8h+var_28]
0x1400226bd  mov     rbx, [r11+40h]
0x1400226c1  mov     rbp, [r11+48h]
0x1400226c5  mov     rsp, r11
0x1400226c8  pop     r15
0x1400226ca  pop     r14
0x1400226cc  pop     r13
0x1400226ce  pop     rdi
0x1400226cf  pop     rsi
0x1400226d0  retn
0x1400226d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400226d9  cmp     rcx, r14
0x1400226dc  jnz     loc_1400228D4
0x1400226e2  xor     edx, edx; Wait
0x1400226e4  lea     rcx, [rbx+88h]; Mutex
0x1400226eb  mov     edi, 0C000000Dh
0x1400226f0  call    cs:__imp_KeReleaseMutex
0x1400226f7  nop     dword ptr [rax+rax+00h]
0x1400226fc  jmp     loc_14002267D
0x140022701  mov     r10, cs:WPP_GLOBAL_Control
0x140022708  cmp     r10, r14
0x14002270b  jz      short loc_140022720
0x14002270d  cmp     byte ptr [r10+29h], 2
0x140022712  jb      short loc_140022720
0x140022714  mov     eax, [r10+2Ch]
0x140022718  test    al, 10h
0x14002271a  jnz     loc_140022945
0x140022720  mov     edi, 0C000000Dh
0x140022725  jmp     loc_14002267D
0x14002272a  lea     rcx, NsipDeregisterProviderNotificationListLock; SpinLock
0x140022731  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140022738  nop     dword ptr [rax+rax+00h]
0x14002273d  mov     rbx, cs:NsipDeregisterProviderNotificationList
0x140022744  movzx   edx, al; NewIrql
0x140022747  lea     rax, NsipDeregisterProviderNotificationList
0x14002274e  cmp     rbx, rax
0x140022751  jz      loc_1400228B7
0x140022757  mov     rcx, [rbx]
0x14002275a  cmp     rbx, rdi
0x14002275d  jnz     loc_1400228AF
0x140022763  cmp     [rcx+8], rbx
0x140022767  jnz     loc_140022870
0x14002276d  mov     rax, [rbx+8]
0x140022771  cmp     [rax], rbx
0x140022774  jnz     loc_140022870
0x14002277a  mov     [rax], rcx
0x14002277d  mov     [rcx+8], rax
0x140022781  lea     rcx, NsipDeregisterProviderNotificationListLock; SpinLock
0x140022788  call    cs:__imp_KeReleaseSpinLock
0x14002278f  nop     dword ptr [rax+rax+00h]
0x140022794  xor     edx, edx; Tag
0x140022796  mov     rcx, rbx; P
0x140022799  call    cs:__imp_ExFreePoolWithTag
0x1400227a0  nop     dword ptr [rax+rax+00h]
0x1400227a5  xor     eax, eax
0x1400227a7  jmp     loc_1400226A5
0x1400227ac  cmp     [rsp+0C8h+var_60], r14d
0x1400227b1  jnz     loc_1400225F2
0x1400227b7  movzx   eax, r15b
0x1400227bb  jmp     loc_1400225F6
0x1400227c0  mov     r14, [r13+0]
0x1400227c4  cmp     r14, r13
0x1400227c7  jz      short loc_1400227DD
0x1400227c9  nop     dword ptr [rax+00000000h]
0x1400227d0  cmp     r14, rax
0x1400227d3  jz      short loc_140022801
0x1400227d5  mov     r14, [r14]
0x1400227d8  cmp     r14, r13
0x1400227db  jnz     short loc_1400227D0
0x1400227dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400227e4  lea     rax, WPP_GLOBAL_Control
0x1400227eb  cmp     rcx, rax
0x1400227ee  jnz     loc_140022916
0x1400227f4  mov     edi, 0C000000Dh
0x1400227f9  xor     r13d, r13d
0x1400227fc  jmp     loc_14002262E
0x140022801  cmp     [r14+14h], r15d
0x140022805  jnz     short loc_1400227D5
0x140022807  cmp     r14, r13
0x14002280a  jz      short loc_1400227DD
0x14002280c  xor     r9d, r9d; Alertable
0x14002280f  mov     [rsp+0C8h+Timeout], 0; Timeout
0x140022818  xor     r8d, r8d; WaitMode
0x14002281b  lea     rcx, [rbx+50h]; Object
0x14002281f  xor     edx, edx; WaitReason
0x140022821  call    cs:__imp_KeWaitForSingleObject
0x140022828  nop     dword ptr [rax+rax+00h]
0x14002282d  dec     dword ptr [r13+14h]
0x140022831  mov     rcx, r14
0x140022834  mov     dword ptr [r14+14h], 2
0x14002283c  call    NsipLockedDereferenceNotificationContext
0x140022841  xor     edx, edx; Wait
0x140022843  lea     rcx, [rbx+50h]; Mutex
0x140022847  call    cs:__imp_KeReleaseMutex
0x14002284e  nop     dword ptr [rax+rax+00h]
0x140022853  cmp     dword ptr [r13+14h], 0
0x140022858  mov     eax, [rsp+0C8h+var_68]
0x14002285c  jz      loc_140022903
0x140022862  mov     rcx, [r14+18h]
0x140022866  mov     [rsp+0C8h+var_58], rcx
0x14002286b  jmp     loc_1400225F6
0x140022870  mov     ecx, 3
0x140022875  int     29h; Win8: RtlFailFast(ecx)
0x140022877  mov     eax, [rax+2Ch]
0x14002287a  test    al, 10h
0x14002287c  jz      loc_140022519
0x140022882  mov     rax, [rcx+8]
0x140022886  mov     ebx, [rcx+20h]
0x140022889  mov     r14d, [rcx+10h]
0x14002288d  movups  [rsp+0C8h+var_40], xmm0
0x140022895  lea     rdi, [rax+8]
0x140022899  test    rax, rax
0x14002289c  jnz     loc_14007B1B0
0x1400228a2  lea     rdi, [rsp+0C8h+var_40]
0x1400228aa  jmp     loc_14007B1B0
0x1400228af  mov     rbx, rcx
0x1400228b2  jmp     loc_14002274E
0x1400228b7  lea     rcx, NsipDeregisterProviderNotificationListLock; SpinLock
0x1400228be  call    cs:__imp_KeReleaseSpinLock
0x1400228c5  nop     dword ptr [rax+rax+00h]
0x1400228ca  mov     edi, 0C00000BBh
0x1400228cf  jmp     loc_140022692
0x1400228d4  cmp     byte ptr [rcx+29h], 2
0x1400228d8  jb      loc_1400226E2
0x1400228de  mov     eax, [rcx+2Ch]
0x1400228e1  test    al, 10h
0x1400228e3  jz      loc_1400226E2
0x1400228e9  mov     rcx, [rcx+18h]
0x1400228ed  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x1400228f4  mov     edx, 34h ; '4'
0x1400228f9  call    WPP_SF_
0x1400228fe  jmp     loc_1400226E2
0x140022903  cmp     dword ptr [r13+10h], 0
0x140022908  mov     ecx, r15d
0x14002290b  movzx   eax, al
0x14002290e  cmovz   eax, ecx
0x140022911  jmp     loc_140022862
0x140022916  cmp     byte ptr [rcx+29h], 2
0x14002291a  jb      loc_1400227F4
0x140022920  mov     eax, [rcx+2Ch]
0x140022923  test    al, 10h
0x140022925  jz      loc_1400227F4
0x14002292b  mov     rcx, [rcx+18h]
0x14002292f  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x140022936  mov     edx, 35h ; '5'
0x14002293b  call    WPP_SF_
0x140022940  jmp     loc_1400227F4
0x140022945  mov     dword ptr [rsp+0C8h+Timeout], ecx
0x140022949  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x140022950  mov     rcx, [r10+18h]
0x140022954  mov     edx, 33h ; '3'
0x140022959  call    WPP_SF_Dd
0x14002295e  jmp     loc_140022720
0x140022963  mov     eax, [rcx+2Ch]
0x140022966  test    al, 10h
0x140022968  jz      loc_1400226A3
0x14002296e  mov     rax, [rsi+8]
0x140022972  xorps   xmm0, xmm0
0x140022975  movups  [rsp+0C8h+var_40], xmm0
0x14002297d  test    rax, rax
0x140022980  jz      loc_14007B244
0x140022986  add     rax, 8
0x14002298a  jmp     loc_14007B24C
0x14007b1b0  test    ebx, ebx
0x14007b1b2  jnz     short loc_14007B1D1
0x14007b1b4  call    cs:__imp_PsGetCurrentProcessId
0x14007b1bb  nop     dword ptr [rax+rax+00h]
0x14007b1c0  mov     edx, [rsp+0C8h+var_68]
0x14007b1c4  mov     rbx, rax
0x14007b1c7  test    edx, edx
0x14007b1c9  jnz     short loc_14007B1E4
0x14007b1cb  cmp     [rsp+0C8h+var_60], ebp
0x14007b1cf  jnz     short loc_14007B1E4
0x14007b1d1  lea     rdx, [rsp+0C8h+var_60]
0x14007b1d6  lea     rcx, [rsp+0C8h+var_68]
0x14007b1db  call    NdisGetCurrentThreadCompartmentScope
0x14007b1e0  mov     edx, [rsp+0C8h+var_68]
0x14007b1e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b1eb  lea     rax, WPP_GLOBAL_Control
0x14007b1f2  cmp     rcx, rax
0x14007b1f5  jz      short loc_14007B238
0x14007b1f7  cmp     byte ptr [rcx+29h], 5
0x14007b1fb  jb      short loc_14007B238
  ... truncated ...
```
