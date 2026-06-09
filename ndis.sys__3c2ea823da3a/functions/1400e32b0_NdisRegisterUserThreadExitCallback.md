# NdisRegisterUserThreadExitCallback

- ea: `0x1400e32b0`
- end: `0x1400e376c`
- name: `NdisRegisterUserThreadExitCallback`
- size: `1212`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x14001cf50`
- `0x140028e00`
- `0x140029620`
- `0x14003e8b0`
- `0x140085f30`
- `0x1400da6bc`
- `0x1400e3158`
- `0x1400e3190`
- `0x1400e31b8`
- `0x1400e3220`
- `0x1400e3258`
- `0x1400e32b0`
- `0x1400e3930`
- `0x1400e3af4`
- `0x14015df00`
- `0x140162fc0`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400e347b`
- `ntoskrnl!ObfReferenceObject` at `0x1400e347b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400e364d`
- `ntoskrnl!PsIsSystemThread` at `0x1400e33d0`
- `ntoskrnl!PsIsSystemThread` at `0x1400e33d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e3503`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e35a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e3503`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e35a8`
- `ntoskrnl!ExAllocatePool2` at `0x1400e3434`
- `ntoskrnl!ExAllocatePool2` at `0x1400e3434`
- `ntoskrnl!PsSetThreadProperty` at `0x1400e35f6`
- `ntoskrnl!PsSetThreadProperty` at `0x1400e35f6`

## pseudocode

```c
__int64 __fastcall NdisRegisterUserThreadExitCallback(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _NDIS_THREAD_EXIT_REGISTRATION **a4)
{
  __int64 v6; // r12
  int v8; // r9d
  struct KPushLockBase *v9; // rbx
  unsigned __int64 *v10; // rbx
  unsigned __int64 *i; // rax
  char v12; // bl
  struct _KTHREAD *CurrentThread; // rsi
  _QWORD *Pool2; // rax
  int v16; // edx
  _NDIS_THREAD_EXIT_REGISTRATION *v17; // rdi
  int v18; // edx
  int v19; // edx
  unsigned int v20; // ebx
  int v21; // r9d
  __int64 v22; // rax
  _QWORD *v23; // rbx
  int v24; // edx
  struct _KTHREAD *v25; // [rsp+30h] [rbp-48h] BYREF
  __int64 v26; // [rsp+38h] [rbp-40h] BYREF
  char v27[8]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v28; // [rsp+48h] [rbp-30h] BYREF
  LONG_PTR (__stdcall *v29)(PVOID); // [rsp+50h] [rbp-28h] BYREF
  KLockHolder v30; // [rsp+58h] [rbp-20h] BYREF
  PVOID P; // [rsp+D8h] [rbp+60h] BYREF

  v6 = a2;
  if ( !a4 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v8 = 10;
      LOBYTE(a2) = 4;
LABEL_25:
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        a2,
        27,
        v8,
        (struct _GUID *)&WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids);
    }
    return 3221225485LL;
  }
  *a4 = 0;
  if ( !a1 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return 3221225485LL;
    v8 = 11;
LABEL_24:
    LOBYTE(a2) = 2;
    goto LABEL_25;
  }
  v9 = qword_14011CA40;
  KLockThisShared::KLockThisShared((KLockThisShared *)&v30, qword_14011CA40);
  v10 = (unsigned __int64 *)&v9[1];
  for ( i = (unsigned __int64 *)*v10; i != v10; i = (unsigned __int64 *)*i )
  {
    if ( i[9] == a1 )
    {
      v12 = 1;
      goto LABEL_13;
    }
  }
  v12 = 0;
LABEL_13:
  KLockHolder::~KLockHolder(&v30);
  if ( !v12 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        a2,
        27,
        12,
        (struct _GUID *)&WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids);
    }
    return 3221225474LL;
  }
  if ( qword_14011D6D8 )
  {
    if ( !v6 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return 3221225485LL;
      v8 = 14;
      goto LABEL_24;
    }
    CurrentThread = KeGetCurrentThread();
    if ( PsIsSystemThread(CurrentThread) )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return 3221225485LL;
      v8 = 15;
      goto LABEL_24;
    }
    Pool2 = (_QWORD *)ExAllocatePool2(64, 16, 1380280404);
    if ( Pool2 )
    {
      *Pool2 = 0;
      Pool2[1] = 0;
      wistd::unique_ptr<InterfaceProfileKnobCollection,KFreePool<InterfaceProfileKnobCollection>>::unique_ptr<InterfaceProfileKnobCollection,KFreePool<InterfaceProfileKnobCollection>>(
        &P,
        Pool2);
    }
    else
    {
      wistd::unique_ptr<wchar_t,KFreePool<wchar_t>>::unique_ptr<wchar_t,KFreePool<wchar_t>>(&P);
    }
    v17 = (_NDIS_THREAD_EXIT_REGISTRATION *)P;
    if ( P )
    {
      AcquireDriverObjectReference(v27, a1);
      ObfReferenceObject(CurrentThread);
      v25 = CurrentThread;
      ndisGetThreadStateReferenceFromThread(&v26, CurrentThread);
      if ( v26 )
      {
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v18) = 2;
          WPP_RECORDER_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v18,
            27,
            17,
            (struct _GUID *)&WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids);
        }
        wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(&v26);
        wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(&v25);
        wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(v27);
        if ( v17 )
        {
          _NDIS_THREAD_EXIT_REGISTRATION::~_NDIS_THREAD_EXIT_REGISTRATION(v17);
          ExFreePoolWithTag(v17, 0);
        }
        return 3221226768LL;
      }
      P = 0;
      v20 = ndisCreateThreadStateObject(&P);
      if ( v20 )
      {
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        {
LABEL_41:
          wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(&P);
          wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(&v26);
          wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(&v25);
          wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(v27);
          if ( v17 )
          {
            _NDIS_THREAD_EXIT_REGISTRATION::~_NDIS_THREAD_EXIT_REGISTRATION(v17);
            ExFreePoolWithTag(v17, 0);
          }
          return v20;
        }
        v21 = 18;
LABEL_40:
        LOBYTE(v19) = 2;
        WPP_RECORDER_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v19,
          27,
          v21,
          (struct _GUID *)&WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids,
          v20);
        goto LABEL_41;
      }
      v22 = AcquireDriverObjectReference(&v28, a1);
      v23 = P;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_DRIVER_OBJECT *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_DRIVER_OBJECT *,_DRIVER_OBJECT *,0,std::nullptr_t>>>::operator=(
        P,
        v22);
      wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(&v28);
      v23[1] = CurrentThread;
      v23[2] = v6;
      v23[3] = a3;
      v20 = PsSetThreadProperty(CurrentThread, 1398031173, v23);
      if ( v20 )
      {
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_41;
        v21 = 19;
        goto LABEL_40;
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_DRIVER_OBJECT *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_DRIVER_OBJECT *,_DRIVER_OBJECT *,0,std::nullptr_t>>>::operator=(
        (char *)v17 + 8,
        v27);
      if ( v17 != (_NDIS_THREAD_EXIT_REGISTRATION *)&v25 )
      {
        if ( *(_QWORD *)v17 )
        {
          v28 = *(_QWORD *)v17;
          v29 = ObfDereferenceObject;
          wistd::invoke<__int64 (*)(void *),_DRIVER_OBJECT * &>(&v29, &v28);
        }
        *(_QWORD *)v17 = CurrentThread;
        v25 = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<NDIS_THREAD_STATE *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,NDIS_THREAD_STATE *,NDIS_THREAD_STATE *,0,std::nullptr_t>>::reset(
        &P,
        0);
      *a4 = v17;
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v24) = 4;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v24,
          27,
          20,
          (struct _GUID *)&WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids,
          (char)v17);
      }
      wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(&P);
      wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(&v26);
      wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(&v25);
      wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(v27);
      return 0;
    }
    else
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = 2;
        WPP_RECORDER_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v16,
          27,
          16,
          (struct _GUID *)&WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids);
      }
      return 3221225626LL;
    }
  }
  else
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        a2,
        27,
        13,
        (struct _GUID *)&WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids);
    }
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x1400e32b0  push    rbp
0x1400e32b2  push    rbx
0x1400e32b3  push    rsi
0x1400e32b4  push    rdi
0x1400e32b5  push    r12
0x1400e32b7  push    r13
0x1400e32b9  push    r14
0x1400e32bb  push    r15
0x1400e32bd  mov     rbp, rsp
0x1400e32c0  sub     rsp, 78h
0x1400e32c4  xor     edi, edi
0x1400e32c6  mov     r15, r9
0x1400e32c9  mov     r13, r8
0x1400e32cc  mov     r12, rdx
0x1400e32cf  mov     r14, rcx
0x1400e32d2  test    r9, r9
0x1400e32d5  jnz     short loc_1400E32F6
0x1400e32d7  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e32de  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e32e5  jz      loc_1400E341A
0x1400e32eb  lea     r9d, [r15+0Ah]
0x1400e32ef  mov     dl, 4
0x1400e32f1  jmp     loc_1400E33F8
0x1400e32f6  mov     [r9], rdi
0x1400e32f9  test    r14, r14
0x1400e32fc  jnz     short loc_1400E331B
0x1400e32fe  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e3305  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e330c  jz      loc_1400E341A
0x1400e3312  lea     r9d, [r14+0Bh]
0x1400e3316  jmp     loc_1400E33F6
0x1400e331b  mov     rbx, cs:qword_14011CA40
0x1400e3322  lea     rcx, [rbp+var_20]; this
0x1400e3326  mov     rdx, rbx; struct KPushLockBase *
0x1400e3329  call    ??0KLockThisShared@@QEAA@AEAVKPushLockBase@@@Z; KLockThisShared::KLockThisShared(KPushLockBase &)
0x1400e332e  add     rbx, 8
0x1400e3332  mov     rax, [rbx]
0x1400e3335  cmp     rax, rbx
0x1400e3338  jz      short loc_1400E3349
0x1400e333a  cmp     [rax+48h], r14
0x1400e333e  jz      short loc_1400E3345
0x1400e3340  mov     rax, [rax]
0x1400e3343  jmp     short loc_1400E3335
0x1400e3345  mov     bl, 1
0x1400e3347  jmp     short loc_1400E334C
0x1400e3349  mov     bl, dil
0x1400e334c  lea     rcx, [rbp+var_20]; this
0x1400e3350  call    ??1KLockHolder@@QEAA@XZ; KLockHolder::~KLockHolder(void)
0x1400e3355  test    bl, bl
0x1400e3357  jnz     short loc_1400E339B
0x1400e3359  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e3360  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e3367  jz      short loc_1400E3391
0x1400e3369  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e3370  lea     rax, WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids
0x1400e3377  mov     r9d, 0Ch; int
0x1400e337d  mov     [rsp+78h+var_58], rax; struct _GUID *
0x1400e3382  mov     dl, 2; int
0x1400e3384  mov     rcx, [rcx+40h]; int
0x1400e3388  lea     r8d, [r9+0Fh]; int
0x1400e338c  call    WPP_RECORDER_SF_
0x1400e3391  mov     eax, 0C0000002h
0x1400e3396  jmp     loc_1400E375A
0x1400e339b  cmp     cs:qword_14011D6D8, rdi
0x1400e33a2  jz      loc_1400E371D
0x1400e33a8  test    r12, r12
0x1400e33ab  jnz     short loc_1400E33C4
0x1400e33ad  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e33b4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e33bb  jz      short loc_1400E341A
0x1400e33bd  lea     r9d, [r12+0Eh]
0x1400e33c2  jmp     short loc_1400E33F6
0x1400e33c4  mov     rsi, gs:188h
0x1400e33cd  mov     rcx, rsi; Thread
0x1400e33d0  call    cs:__imp_PsIsSystemThread
0x1400e33d7  nop     dword ptr [rax+rax+00h]
0x1400e33dc  test    al, al
0x1400e33de  jz      short loc_1400E3424
0x1400e33e0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e33e7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e33ee  jz      short loc_1400E341A
0x1400e33f0  mov     r9d, 0Fh; int
0x1400e33f6  mov     dl, 2; int
0x1400e33f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e33ff  lea     rax, WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids
0x1400e3406  mov     r8d, 1Bh; int
0x1400e340c  mov     [rsp+78h+var_58], rax; struct _GUID *
0x1400e3411  mov     rcx, [rcx+40h]; int
0x1400e3415  call    WPP_RECORDER_SF_
0x1400e341a  mov     eax, 0C000000Dh
0x1400e341f  jmp     loc_1400E375A
0x1400e3424  mov     ebx, 10h
0x1400e3429  mov     r8d, 52456854h
0x1400e342f  mov     edx, ebx
0x1400e3431  lea     ecx, [rbx+30h]
0x1400e3434  call    cs:__imp_ExAllocatePool2
0x1400e343b  nop     dword ptr [rax+rax+00h]
0x1400e3440  lea     rcx, [rbp+P]
0x1400e3444  test    rax, rax
0x1400e3447  jnz     short loc_1400E3450
0x1400e3449  call    ??$?0$00X@?$unique_ptr@_WU?$KFreePool@_W@@@wistd@@QEAA@$$T@Z; wistd::unique_ptr<wchar_t,KFreePool<wchar_t>>::unique_ptr<wchar_t,KFreePool<wchar_t>>(std::nullptr_t)
0x1400e344e  jmp     short loc_1400E345F
0x1400e3450  mov     [rax], rdi
0x1400e3453  mov     rdx, rax
0x1400e3456  mov     [rax+8], rdi
0x1400e345a  call    ??$?0$00X@?$unique_ptr@VInterfaceProfileKnobCollection@@U?$KFreePool@VInterfaceProfileKnobCollection@@@@@wistd@@QEAA@PEAVInterfaceProfileKnobCollection@@@Z; wistd::unique_ptr<InterfaceProfileKnobCollection,KFreePool<InterfaceProfileKnobCollection>>::unique_ptr<InterfaceProfileKnobCollection,KFreePool<InterfaceProfileKnobCollection>>(InterfaceProfileKnobCollection *)
0x1400e345f  mov     rdi, [rbp+P]
0x1400e3463  test    rdi, rdi
0x1400e3466  jz      loc_1400E36DF
0x1400e346c  mov     rdx, r14
0x1400e346f  lea     rcx, [rbp+var_38]
0x1400e3473  call    ?AcquireDriverObjectReference@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_DRIVER_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_DRIVER_OBJECT@@@Z; AcquireDriverObjectReference(_DRIVER_OBJECT *)
0x1400e3478  mov     rcx, rsi; Object
0x1400e347b  call    cs:__imp_ObfReferenceObject
0x1400e3482  nop     dword ptr [rax+rax+00h]
0x1400e3487  mov     rdx, rsi
0x1400e348a  mov     [rbp+var_48], rsi
0x1400e348e  lea     rcx, [rbp+var_40]
0x1400e3492  call    ?ndisGetThreadStateReferenceFromThread@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUNDIS_THREAD_STATE@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_ETHREAD@@@Z; ndisGetThreadStateReferenceFromThread(_ETHREAD *)
0x1400e3497  cmp     [rbp+var_40], 0
0x1400e349c  jz      short loc_1400E3519
0x1400e349e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e34a5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e34ac  jz      short loc_1400E34D6
0x1400e34ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e34b5  lea     rax, WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids
0x1400e34bc  mov     r9d, 11h; int
0x1400e34c2  mov     [rsp+78h+var_58], rax; struct _GUID *
0x1400e34c7  mov     dl, 2; int
0x1400e34c9  mov     rcx, [rcx+40h]; int
0x1400e34cd  lea     r8d, [r9+0Ah]; int
0x1400e34d1  call    WPP_RECORDER_SF_
0x1400e34d6  lea     rcx, [rbp+var_40]
0x1400e34da  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e34df  lea     rcx, [rbp+var_48]
0x1400e34e3  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e34e8  lea     rcx, [rbp+var_38]
0x1400e34ec  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e34f1  test    rdi, rdi
0x1400e34f4  jz      short loc_1400E350F
0x1400e34f6  mov     rcx, rdi; this
0x1400e34f9  call    ??1_NDIS_THREAD_EXIT_REGISTRATION@@QEAA@XZ; _NDIS_THREAD_EXIT_REGISTRATION::~_NDIS_THREAD_EXIT_REGISTRATION(void)
0x1400e34fe  xor     edx, edx; Tag
0x1400e3500  mov     rcx, rdi; P
0x1400e3503  call    cs:__imp_ExFreePoolWithTag
0x1400e350a  nop     dword ptr [rax+rax+00h]
0x1400e350f  mov     eax, 0C0000510h
0x1400e3514  jmp     loc_1400E375A
0x1400e3519  lea     rcx, [rbp+P]
0x1400e351d  mov     [rbp+P], 0
0x1400e3525  call    ?ndisCreateThreadStateObject@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUNDIS_THREAD_STATE@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; ndisCreateThreadStateObject(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<NDIS_THREAD_STATE *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,NDIS_THREAD_STATE *,NDIS_THREAD_STATE *,0,std::nullptr_t>>> &)
0x1400e352a  mov     ebx, eax
0x1400e352c  test    eax, eax
0x1400e352e  jz      loc_1400E35BB
0x1400e3534  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e353b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e3542  jz      short loc_1400E3572
0x1400e3544  mov     r9d, 12h; int
0x1400e354a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e3551  lea     rax, WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids
0x1400e3558  mov     dword ptr [rsp+78h+var_50], ebx; char
0x1400e355c  mov     r8d, 1Bh; int
0x1400e3562  mov     dl, 2; int
0x1400e3564  mov     [rsp+78h+var_58], rax; struct _GUID *
0x1400e3569  mov     rcx, [rcx+40h]; int
0x1400e356d  call    WPP_RECORDER_SF_d
0x1400e3572  lea     rcx, [rbp+P]
0x1400e3576  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e357b  lea     rcx, [rbp+var_40]
0x1400e357f  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e3584  lea     rcx, [rbp+var_48]
0x1400e3588  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e358d  lea     rcx, [rbp+var_38]
0x1400e3591  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e3596  test    rdi, rdi
0x1400e3599  jz      short loc_1400E35B4
0x1400e359b  mov     rcx, rdi; this
0x1400e359e  call    ??1_NDIS_THREAD_EXIT_REGISTRATION@@QEAA@XZ; _NDIS_THREAD_EXIT_REGISTRATION::~_NDIS_THREAD_EXIT_REGISTRATION(void)
0x1400e35a3  xor     edx, edx; Tag
0x1400e35a5  mov     rcx, rdi; P
0x1400e35a8  call    cs:__imp_ExFreePoolWithTag
0x1400e35af  nop     dword ptr [rax+rax+00h]
0x1400e35b4  mov     eax, ebx
0x1400e35b6  jmp     loc_1400E375A
0x1400e35bb  mov     rdx, r14
0x1400e35be  lea     rcx, [rbp+var_30]
0x1400e35c2  call    ?AcquireDriverObjectReference@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_DRIVER_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_DRIVER_OBJECT@@@Z; AcquireDriverObjectReference(_DRIVER_OBJECT *)
0x1400e35c7  mov     rbx, [rbp+P]
0x1400e35cb  mov     rdx, rax
0x1400e35ce  mov     rcx, rbx
0x1400e35d1  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_DRIVER_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_DRIVER_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_DRIVER_OBJECT *,_DRIVER_OBJECT *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_DRIVER_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_DRIVER_OBJECT *,_DRIVER_OBJECT *,0,std::nullptr_t>>> &&)
0x1400e35d6  lea     rcx, [rbp+var_30]
0x1400e35da  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e35df  mov     [rbx+8], rsi
0x1400e35e3  mov     r8, rbx
0x1400e35e6  mov     [rbx+10h], r12
0x1400e35ea  mov     edx, 53544345h
0x1400e35ef  mov     rcx, rsi
0x1400e35f2  mov     [rbx+18h], r13
0x1400e35f6  call    cs:__imp_PsSetThreadProperty
0x1400e35fd  nop     dword ptr [rax+rax+00h]
0x1400e3602  mov     ebx, eax
0x1400e3604  test    eax, eax
0x1400e3606  jz      short loc_1400E3627
0x1400e3608  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e360f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e3616  jz      loc_1400E3572
0x1400e361c  mov     r9d, 13h
0x1400e3622  jmp     loc_1400E354A
0x1400e3627  lea     rcx, [rdi+8]
0x1400e362b  lea     rdx, [rbp+var_38]
0x1400e362f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_DRIVER_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_DRIVER_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_DRIVER_OBJECT *,_DRIVER_OBJECT *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_DRIVER_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_DRIVER_OBJECT *,_DRIVER_OBJECT *,0,std::nullptr_t>>> &&)
0x1400e3634  lea     rax, [rbp+var_48]
0x1400e3638  cmp     rdi, rax
0x1400e363b  jz      short loc_1400E366C
0x1400e363d  mov     rax, [rdi]
0x1400e3640  test    rax, rax
0x1400e3643  jz      short loc_1400E3661
0x1400e3645  mov     [rbp+var_30], rax
0x1400e3649  lea     rdx, [rbp+var_30]
0x1400e364d  mov     rax, cs:__imp_ObfDereferenceObject
0x1400e3654  lea     rcx, [rbp+var_28]
0x1400e3658  mov     [rbp+var_28], rax
0x1400e365c  call    ??$invoke@P6A_JPEAX@ZAEAPEAU_DRIVER_OBJECT@@@wistd@@YA_J$$QEAP6A_JPEAX@ZAEAPEAU_DRIVER_OBJECT@@@Z; wistd::invoke<__int64 (*)(void *),_DRIVER_OBJECT * &>(__int64 (*&&)(void *),_DRIVER_OBJECT * &)
0x1400e3661  mov     [rdi], rsi
0x1400e3664  mov     [rbp+var_48], 0
0x1400e366c  xor     edx, edx
0x1400e366e  lea     rcx, [rbp+P]
0x1400e3672  call    ?reset@?$unique_storage@U?$resource_policy@PEAUNDIS_THREAD_STATE@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUNDIS_THREAD_STATE@@@Z; wil::details::unique_storage<wil::details::resource_policy<NDIS_THREAD_STATE *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,NDIS_THREAD_STATE *,NDIS_THREAD_STATE *,0,std::nullptr_t>>::reset(NDIS_THREAD_STATE *)
0x1400e3677  mov     [r15], rdi
0x1400e367a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e3681  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e3688  jz      short loc_1400E36B7
0x1400e368a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e3691  lea     rax, WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids
0x1400e3698  mov     r9d, 14h; int
0x1400e369e  mov     qword ptr [rsp+78h+var_50], rdi; char
0x1400e36a3  mov     dl, 4; int
0x1400e36a5  mov     [rsp+78h+var_58], rax; struct _GUID *
0x1400e36aa  mov     rcx, [rcx+40h]; int
0x1400e36ae  lea     r8d, [r9+7]; int
0x1400e36b2  call    WPP_RECORDER_SF_q
0x1400e36b7  lea     rcx, [rbp+P]
0x1400e36bb  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e36c0  lea     rcx, [rbp+var_40]
0x1400e36c4  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e36c9  lea     rcx, [rbp+var_48]
0x1400e36cd  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e36d2  lea     rcx, [rbp+var_38]
0x1400e36d6  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e36db  xor     eax, eax
0x1400e36dd  jmp     short loc_1400E375A
0x1400e36df  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e36e6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e36ed  jz      short loc_1400E3716
0x1400e36ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e36f6  lea     rax, WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids
0x1400e36fd  mov     r9d, ebx; int
0x1400e3700  mov     [rsp+78h+var_58], rax; struct _GUID *
0x1400e3705  mov     r8d, 1Bh; int
0x1400e370b  mov     dl, 2; int
0x1400e370d  mov     rcx, [rcx+40h]; int
0x1400e3711  call    WPP_RECORDER_SF_
0x1400e3716  mov     eax, 0C000009Ah
0x1400e371b  jmp     short loc_1400E375A
0x1400e371d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e3724  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e372b  jz      short loc_1400E3755
0x1400e372d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e3734  lea     rax, WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids
0x1400e373b  mov     r9d, 0Dh; int
0x1400e3741  mov     [rsp+78h+var_58], rax; struct _GUID *
0x1400e3746  mov     dl, 2; int
0x1400e3748  mov     rcx, [rcx+40h]; int
0x1400e374c  lea     r8d, [r9+0Eh]; int
0x1400e3750  call    WPP_RECORDER_SF_
0x1400e3755  mov     eax, 0C0000001h
0x1400e375a  add     rsp, 78h
0x1400e375e  pop     r15
0x1400e3760  pop     r14
0x1400e3762  pop     r13
0x1400e3764  pop     r12
0x1400e3766  pop     rdi
0x1400e3767  pop     rsi
0x1400e3768  pop     rbx
0x1400e3769  pop     rbp
0x1400e376a  retn
```
