# NdisRegisterUserThreadExitCallback

- ea: `0x1400e8460`
- end: `0x1400e891c`
- name: `NdisRegisterUserThreadExitCallback`
- size: `1212`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x1400110b0`
- `0x14001cf60`
- `0x14002ab60`
- `0x140041060`
- `0x14008b1b0`
- `0x1400df86c`
- `0x1400e8308`
- `0x1400e8340`
- `0x1400e8368`
- `0x1400e83d0`
- `0x1400e8408`
- `0x1400e8460`
- `0x1400e8ae0`
- `0x1400e8ca4`
- `0x140164da0`
- `0x140169f50`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400e862b`
- `ntoskrnl!ObfReferenceObject` at `0x1400e862b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400e87fd`
- `ntoskrnl!PsIsSystemThread` at `0x1400e8580`
- `ntoskrnl!PsIsSystemThread` at `0x1400e8580`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e86b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e8758`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e86b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e8758`
- `ntoskrnl!ExAllocatePool2` at `0x1400e85e4`
- `ntoskrnl!ExAllocatePool2` at `0x1400e85e4`
- `ntoskrnl!PsSetThreadProperty` at `0x1400e87a6`
- `ntoskrnl!PsSetThreadProperty` at `0x1400e87a6`

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
  v9 = qword_140122A40;
  KLockThisShared::KLockThisShared((KLockThisShared *)&v30, qword_140122A40);
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
  if ( qword_1401236C8 )
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
0x1400e8460  push    rbp
0x1400e8462  push    rbx
0x1400e8463  push    rsi
0x1400e8464  push    rdi
0x1400e8465  push    r12
0x1400e8467  push    r13
0x1400e8469  push    r14
0x1400e846b  push    r15
0x1400e846d  mov     rbp, rsp
0x1400e8470  sub     rsp, 78h
0x1400e8474  xor     edi, edi
0x1400e8476  mov     r15, r9
0x1400e8479  mov     r13, r8
0x1400e847c  mov     r12, rdx
0x1400e847f  mov     r14, rcx
0x1400e8482  test    r9, r9
0x1400e8485  jnz     short loc_1400E84A6
0x1400e8487  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e848e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e8495  jz      loc_1400E85CA
0x1400e849b  lea     r9d, [r15+0Ah]
0x1400e849f  mov     dl, 4
0x1400e84a1  jmp     loc_1400E85A8
0x1400e84a6  mov     [r9], rdi
0x1400e84a9  test    r14, r14
0x1400e84ac  jnz     short loc_1400E84CB
0x1400e84ae  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e84b5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e84bc  jz      loc_1400E85CA
0x1400e84c2  lea     r9d, [r14+0Bh]
0x1400e84c6  jmp     loc_1400E85A6
0x1400e84cb  mov     rbx, cs:qword_140122A40
0x1400e84d2  lea     rcx, [rbp+var_20]; this
0x1400e84d6  mov     rdx, rbx; struct KPushLockBase *
0x1400e84d9  call    ??0KLockThisShared@@QEAA@AEAVKPushLockBase@@@Z; KLockThisShared::KLockThisShared(KPushLockBase &)
0x1400e84de  add     rbx, 8
0x1400e84e2  mov     rax, [rbx]
0x1400e84e5  cmp     rax, rbx
0x1400e84e8  jz      short loc_1400E84F9
0x1400e84ea  cmp     [rax+48h], r14
0x1400e84ee  jz      short loc_1400E84F5
0x1400e84f0  mov     rax, [rax]
0x1400e84f3  jmp     short loc_1400E84E5
0x1400e84f5  mov     bl, 1
0x1400e84f7  jmp     short loc_1400E84FC
0x1400e84f9  mov     bl, dil
0x1400e84fc  lea     rcx, [rbp+var_20]; this
0x1400e8500  call    ??1KLockHolder@@QEAA@XZ; KLockHolder::~KLockHolder(void)
0x1400e8505  test    bl, bl
0x1400e8507  jnz     short loc_1400E854B
0x1400e8509  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e8510  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e8517  jz      short loc_1400E8541
0x1400e8519  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8520  lea     rax, WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids
0x1400e8527  mov     r9d, 0Ch; int
0x1400e852d  mov     [rsp+78h+var_58], rax; struct _GUID *
0x1400e8532  mov     dl, 2; int
0x1400e8534  mov     rcx, [rcx+40h]; int
0x1400e8538  lea     r8d, [r9+0Fh]; int
0x1400e853c  call    WPP_RECORDER_SF_
0x1400e8541  mov     eax, 0C0000002h
0x1400e8546  jmp     loc_1400E890A
0x1400e854b  cmp     cs:qword_1401236C8, rdi
0x1400e8552  jz      loc_1400E88CD
0x1400e8558  test    r12, r12
0x1400e855b  jnz     short loc_1400E8574
0x1400e855d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e8564  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e856b  jz      short loc_1400E85CA
0x1400e856d  lea     r9d, [r12+0Eh]
0x1400e8572  jmp     short loc_1400E85A6
0x1400e8574  mov     rsi, gs:188h
0x1400e857d  mov     rcx, rsi; Thread
0x1400e8580  call    cs:__imp_PsIsSystemThread
0x1400e8587  nop     dword ptr [rax+rax+00h]
0x1400e858c  test    al, al
0x1400e858e  jz      short loc_1400E85D4
0x1400e8590  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e8597  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e859e  jz      short loc_1400E85CA
0x1400e85a0  mov     r9d, 0Fh; int
0x1400e85a6  mov     dl, 2; int
0x1400e85a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e85af  lea     rax, WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids
0x1400e85b6  mov     r8d, 1Bh; int
0x1400e85bc  mov     [rsp+78h+var_58], rax; struct _GUID *
0x1400e85c1  mov     rcx, [rcx+40h]; int
0x1400e85c5  call    WPP_RECORDER_SF_
0x1400e85ca  mov     eax, 0C000000Dh
0x1400e85cf  jmp     loc_1400E890A
0x1400e85d4  mov     ebx, 10h
0x1400e85d9  mov     r8d, 52456854h
0x1400e85df  mov     edx, ebx
0x1400e85e1  lea     ecx, [rbx+30h]
0x1400e85e4  call    cs:__imp_ExAllocatePool2
0x1400e85eb  nop     dword ptr [rax+rax+00h]
0x1400e85f0  lea     rcx, [rbp+P]
0x1400e85f4  test    rax, rax
0x1400e85f7  jnz     short loc_1400E8600
0x1400e85f9  call    ??$?0$00X@?$unique_ptr@_WU?$KFreePool@_W@@@wistd@@QEAA@$$T@Z; wistd::unique_ptr<wchar_t,KFreePool<wchar_t>>::unique_ptr<wchar_t,KFreePool<wchar_t>>(std::nullptr_t)
0x1400e85fe  jmp     short loc_1400E860F
0x1400e8600  mov     [rax], rdi
0x1400e8603  mov     rdx, rax
0x1400e8606  mov     [rax+8], rdi
0x1400e860a  call    ??$?0$00X@?$unique_ptr@VInterfaceProfileKnobCollection@@U?$KFreePool@VInterfaceProfileKnobCollection@@@@@wistd@@QEAA@PEAVInterfaceProfileKnobCollection@@@Z; wistd::unique_ptr<InterfaceProfileKnobCollection,KFreePool<InterfaceProfileKnobCollection>>::unique_ptr<InterfaceProfileKnobCollection,KFreePool<InterfaceProfileKnobCollection>>(InterfaceProfileKnobCollection *)
0x1400e860f  mov     rdi, [rbp+P]
0x1400e8613  test    rdi, rdi
0x1400e8616  jz      loc_1400E888F
0x1400e861c  mov     rdx, r14
0x1400e861f  lea     rcx, [rbp+var_38]
0x1400e8623  call    ?AcquireDriverObjectReference@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_DRIVER_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_DRIVER_OBJECT@@@Z; AcquireDriverObjectReference(_DRIVER_OBJECT *)
0x1400e8628  mov     rcx, rsi; Object
0x1400e862b  call    cs:__imp_ObfReferenceObject
0x1400e8632  nop     dword ptr [rax+rax+00h]
0x1400e8637  mov     rdx, rsi
0x1400e863a  mov     [rbp+var_48], rsi
0x1400e863e  lea     rcx, [rbp+var_40]
0x1400e8642  call    ?ndisGetThreadStateReferenceFromThread@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUNDIS_THREAD_STATE@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_ETHREAD@@@Z; ndisGetThreadStateReferenceFromThread(_ETHREAD *)
0x1400e8647  cmp     [rbp+var_40], 0
0x1400e864c  jz      short loc_1400E86C9
0x1400e864e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e8655  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e865c  jz      short loc_1400E8686
0x1400e865e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8665  lea     rax, WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids
0x1400e866c  mov     r9d, 11h; int
0x1400e8672  mov     [rsp+78h+var_58], rax; struct _GUID *
0x1400e8677  mov     dl, 2; int
0x1400e8679  mov     rcx, [rcx+40h]; int
0x1400e867d  lea     r8d, [r9+0Ah]; int
0x1400e8681  call    WPP_RECORDER_SF_
0x1400e8686  lea     rcx, [rbp+var_40]
0x1400e868a  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e868f  lea     rcx, [rbp+var_48]
0x1400e8693  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e8698  lea     rcx, [rbp+var_38]
0x1400e869c  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e86a1  test    rdi, rdi
0x1400e86a4  jz      short loc_1400E86BF
0x1400e86a6  mov     rcx, rdi; this
0x1400e86a9  call    ??1_NDIS_THREAD_EXIT_REGISTRATION@@QEAA@XZ; _NDIS_THREAD_EXIT_REGISTRATION::~_NDIS_THREAD_EXIT_REGISTRATION(void)
0x1400e86ae  xor     edx, edx; Tag
0x1400e86b0  mov     rcx, rdi; P
0x1400e86b3  call    cs:__imp_ExFreePoolWithTag
0x1400e86ba  nop     dword ptr [rax+rax+00h]
0x1400e86bf  mov     eax, 0C0000510h
0x1400e86c4  jmp     loc_1400E890A
0x1400e86c9  lea     rcx, [rbp+P]
0x1400e86cd  mov     [rbp+P], 0
0x1400e86d5  call    ?ndisCreateThreadStateObject@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUNDIS_THREAD_STATE@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; ndisCreateThreadStateObject(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<NDIS_THREAD_STATE *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,NDIS_THREAD_STATE *,NDIS_THREAD_STATE *,0,std::nullptr_t>>> &)
0x1400e86da  mov     ebx, eax
0x1400e86dc  test    eax, eax
0x1400e86de  jz      loc_1400E876B
0x1400e86e4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e86eb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e86f2  jz      short loc_1400E8722
0x1400e86f4  mov     r9d, 12h; int
0x1400e86fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8701  lea     rax, WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids
0x1400e8708  mov     dword ptr [rsp+78h+var_50], ebx; char
0x1400e870c  mov     r8d, 1Bh; int
0x1400e8712  mov     dl, 2; int
0x1400e8714  mov     [rsp+78h+var_58], rax; struct _GUID *
0x1400e8719  mov     rcx, [rcx+40h]; int
0x1400e871d  call    WPP_RECORDER_SF_d
0x1400e8722  lea     rcx, [rbp+P]
0x1400e8726  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e872b  lea     rcx, [rbp+var_40]
0x1400e872f  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e8734  lea     rcx, [rbp+var_48]
0x1400e8738  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e873d  lea     rcx, [rbp+var_38]
0x1400e8741  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e8746  test    rdi, rdi
0x1400e8749  jz      short loc_1400E8764
0x1400e874b  mov     rcx, rdi; this
0x1400e874e  call    ??1_NDIS_THREAD_EXIT_REGISTRATION@@QEAA@XZ; _NDIS_THREAD_EXIT_REGISTRATION::~_NDIS_THREAD_EXIT_REGISTRATION(void)
0x1400e8753  xor     edx, edx; Tag
0x1400e8755  mov     rcx, rdi; P
0x1400e8758  call    cs:__imp_ExFreePoolWithTag
0x1400e875f  nop     dword ptr [rax+rax+00h]
0x1400e8764  mov     eax, ebx
0x1400e8766  jmp     loc_1400E890A
0x1400e876b  mov     rdx, r14
0x1400e876e  lea     rcx, [rbp+var_30]
0x1400e8772  call    ?AcquireDriverObjectReference@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_DRIVER_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_DRIVER_OBJECT@@@Z; AcquireDriverObjectReference(_DRIVER_OBJECT *)
0x1400e8777  mov     rbx, [rbp+P]
0x1400e877b  mov     rdx, rax
0x1400e877e  mov     rcx, rbx
0x1400e8781  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_DRIVER_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_DRIVER_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_DRIVER_OBJECT *,_DRIVER_OBJECT *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_DRIVER_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_DRIVER_OBJECT *,_DRIVER_OBJECT *,0,std::nullptr_t>>> &&)
0x1400e8786  lea     rcx, [rbp+var_30]
0x1400e878a  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e878f  mov     [rbx+8], rsi
0x1400e8793  mov     r8, rbx
0x1400e8796  mov     [rbx+10h], r12
0x1400e879a  mov     edx, 53544345h
0x1400e879f  mov     rcx, rsi
0x1400e87a2  mov     [rbx+18h], r13
0x1400e87a6  call    cs:__imp_PsSetThreadProperty
0x1400e87ad  nop     dword ptr [rax+rax+00h]
0x1400e87b2  mov     ebx, eax
0x1400e87b4  test    eax, eax
0x1400e87b6  jz      short loc_1400E87D7
0x1400e87b8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e87bf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e87c6  jz      loc_1400E8722
0x1400e87cc  mov     r9d, 13h
0x1400e87d2  jmp     loc_1400E86FA
0x1400e87d7  lea     rcx, [rdi+8]
0x1400e87db  lea     rdx, [rbp+var_38]
0x1400e87df  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_DRIVER_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_DRIVER_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_DRIVER_OBJECT *,_DRIVER_OBJECT *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_DRIVER_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_DRIVER_OBJECT *,_DRIVER_OBJECT *,0,std::nullptr_t>>> &&)
0x1400e87e4  lea     rax, [rbp+var_48]
0x1400e87e8  cmp     rdi, rax
0x1400e87eb  jz      short loc_1400E881C
0x1400e87ed  mov     rax, [rdi]
0x1400e87f0  test    rax, rax
0x1400e87f3  jz      short loc_1400E8811
0x1400e87f5  mov     [rbp+var_30], rax
0x1400e87f9  lea     rdx, [rbp+var_30]
0x1400e87fd  mov     rax, cs:__imp_ObfDereferenceObject
0x1400e8804  lea     rcx, [rbp+var_28]
0x1400e8808  mov     [rbp+var_28], rax
0x1400e880c  call    ??$invoke@P6A_JPEAX@ZAEAPEAU_DRIVER_OBJECT@@@wistd@@YA_J$$QEAP6A_JPEAX@ZAEAPEAU_DRIVER_OBJECT@@@Z; wistd::invoke<__int64 (*)(void *),_DRIVER_OBJECT * &>(__int64 (*&&)(void *),_DRIVER_OBJECT * &)
0x1400e8811  mov     [rdi], rsi
0x1400e8814  mov     [rbp+var_48], 0
0x1400e881c  xor     edx, edx
0x1400e881e  lea     rcx, [rbp+P]
0x1400e8822  call    ?reset@?$unique_storage@U?$resource_policy@PEAUNDIS_THREAD_STATE@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUNDIS_THREAD_STATE@@@Z; wil::details::unique_storage<wil::details::resource_policy<NDIS_THREAD_STATE *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,NDIS_THREAD_STATE *,NDIS_THREAD_STATE *,0,std::nullptr_t>>::reset(NDIS_THREAD_STATE *)
0x1400e8827  mov     [r15], rdi
0x1400e882a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e8831  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e8838  jz      short loc_1400E8867
0x1400e883a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8841  lea     rax, WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids
0x1400e8848  mov     r9d, 14h; int
0x1400e884e  mov     qword ptr [rsp+78h+var_50], rdi; char
0x1400e8853  mov     dl, 4; int
0x1400e8855  mov     [rsp+78h+var_58], rax; struct _GUID *
0x1400e885a  mov     rcx, [rcx+40h]; int
0x1400e885e  lea     r8d, [r9+7]; int
0x1400e8862  call    WPP_RECORDER_SF_q
0x1400e8867  lea     rcx, [rbp+P]
0x1400e886b  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e8870  lea     rcx, [rbp+var_40]
0x1400e8874  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e8879  lea     rcx, [rbp+var_48]
0x1400e887d  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e8882  lea     rcx, [rbp+var_38]
0x1400e8886  call    ??1?$unique_storage@U?$resource_policy@PEAU_ETHREAD@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ETHREAD *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_ETHREAD *,_ETHREAD *,0,std::nullptr_t>>(void)
0x1400e888b  xor     eax, eax
0x1400e888d  jmp     short loc_1400E890A
0x1400e888f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e8896  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e889d  jz      short loc_1400E88C6
0x1400e889f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e88a6  lea     rax, WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids
0x1400e88ad  mov     r9d, ebx; int
0x1400e88b0  mov     [rsp+78h+var_58], rax; struct _GUID *
0x1400e88b5  mov     r8d, 1Bh; int
0x1400e88bb  mov     dl, 2; int
0x1400e88bd  mov     rcx, [rcx+40h]; int
0x1400e88c1  call    WPP_RECORDER_SF_
0x1400e88c6  mov     eax, 0C000009Ah
0x1400e88cb  jmp     short loc_1400E890A
0x1400e88cd  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400e88d4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e88db  jz      short loc_1400E8905
0x1400e88dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e88e4  lea     rax, WPP_a7bdd0433f833af46cc07abd1e9cfe56_Traceguids
0x1400e88eb  mov     r9d, 0Dh; int
0x1400e88f1  mov     [rsp+78h+var_58], rax; struct _GUID *
0x1400e88f6  mov     dl, 2; int
0x1400e88f8  mov     rcx, [rcx+40h]; int
0x1400e88fc  lea     r8d, [r9+0Eh]; int
0x1400e8900  call    WPP_RECORDER_SF_
0x1400e8905  mov     eax, 0C0000001h
0x1400e890a  add     rsp, 78h
0x1400e890e  pop     r15
0x1400e8910  pop     r14
0x1400e8912  pop     r13
0x1400e8914  pop     r12
0x1400e8916  pop     rdi
0x1400e8917  pop     rsi
0x1400e8918  pop     rbx
0x1400e8919  pop     rbp
0x1400e891a  retn
```
