# StateContainer::EnumerateContainerItems(tag_ENUMERATE_ITEM_TYPE,tag_STATE_ENUM_ITEM *,uint *)

- ea: `0x1800a3228`
- end: `0x1800a368b`
- name: `?EnumerateContainerItems@StateContainer@@QEAAJW4tag_ENUMERATE_ITEM_TYPE@@PEAUtag_STATE_ENUM_ITEM@@PEAI@Z`
- size: `1123`
- prototype: `int __high(enum tag_ENUMERATE_ITEM_TYPE, struct tag_STATE_ENUM_ITEM *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800fc260`

## callees

- `0x18005997c`
- `0x18009eee0`
- `0x1800a2078`
- `0x1800a3228`
- `0x1800a39cc`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x1800a331d`
- `ntdll!RtlDeleteCriticalSection` at `0x1800a3358`
- `ntdll!RtlDeleteCriticalSection` at `0x1800a344a`
- `ntdll!RtlDeleteCriticalSection` at `0x1800a3485`
- `ntdll!RtlDeleteCriticalSection` at `0x1800a34e8`
- `ntdll!RtlDeleteCriticalSection` at `0x1800a3523`
- `ntdll!RtlDeleteCriticalSection` at `0x1800a3592`
- `ntdll!RtlDeleteCriticalSection` at `0x1800a35cd`
- `ntdll!RtlDeleteCriticalSection` at `0x1800a331d`
- `ntdll!RtlDeleteCriticalSection` at `0x1800a3358`
- `ntdll!RtlDeleteCriticalSection` at `0x1800a344a`
- `ntdll!RtlDeleteCriticalSection` at `0x1800a3485`
- `ntdll!RtlDeleteCriticalSection` at `0x1800a34e8`
- `ntdll!RtlDeleteCriticalSection` at `0x1800a3523`
- `ntdll!RtlDeleteCriticalSection` at `0x1800a3592`
- `ntdll!RtlDeleteCriticalSection` at `0x1800a35cd`
- `ntdll!RtlInitializeCriticalSection` at `0x1800a32c5`
- `ntdll!RtlInitializeCriticalSection` at `0x1800a33e2`
- `ntdll!RtlInitializeCriticalSection` at `0x1800a32c5`
- `ntdll!RtlInitializeCriticalSection` at `0x1800a33e2`
- `ntdll!RtlFreeHeap` at `0x1800a333b`
- `ntdll!RtlFreeHeap` at `0x1800a3376`
- `ntdll!RtlFreeHeap` at `0x1800a3468`
- `ntdll!RtlFreeHeap` at `0x1800a34a3`
- `ntdll!RtlFreeHeap` at `0x1800a3506`
- `ntdll!RtlFreeHeap` at `0x1800a3541`
- `ntdll!RtlFreeHeap` at `0x1800a35b0`
- `ntdll!RtlFreeHeap` at `0x1800a35eb`
- `ntdll!RtlFreeHeap` at `0x1800a333b`
- `ntdll!RtlFreeHeap` at `0x1800a3376`
- `ntdll!RtlFreeHeap` at `0x1800a3468`
- `ntdll!RtlFreeHeap` at `0x1800a34a3`
- `ntdll!RtlFreeHeap` at `0x1800a3506`
- `ntdll!RtlFreeHeap` at `0x1800a3541`
- `ntdll!RtlFreeHeap` at `0x1800a35b0`
- `ntdll!RtlFreeHeap` at `0x1800a35eb`
- `ntdll!RtlAllocateHeap` at `0x1800a3287`
- `ntdll!RtlAllocateHeap` at `0x1800a33a4`
- `ntdll!RtlAllocateHeap` at `0x1800a3287`
- `ntdll!RtlAllocateHeap` at `0x1800a33a4`

## string_xrefs

- `0x1800a32e8`: `Create RegKeyItemFetcher`
- `0x1800a367a`: `Create RegValueItemFetcher`

## pseudocode

```c
__int64 __fastcall StateContainer::EnumerateContainerItems(__int64 *a1, int a2, __int64 a3, int *a4)
{
  __int64 v7; // rax
  int v8; // ebx
  char *Heap; // rax
  char *v10; // rdi
  int Item; // ebx
  const char *v12; // rax
  __int64 v13; // rdx
  char *v14; // rdi
  char *v15; // rdi
  char *v17; // rax
  char *v18; // rdi
  int v19; // eax
  char *v20; // rbx
  char *v21; // rbx
  char *v22; // rbx
  char *v23; // rbx
  char *v24; // [rsp+28h] [rbp-28h]
  PVOID P; // [rsp+30h] [rbp-20h] BYREF
  PVOID v26; // [rsp+38h] [rbp-18h] BYREF
  __int64 v27; // [rsp+40h] [rbp-10h] BYREF
  int v28; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  char v30; // [rsp+88h] [rbp+38h] BYREF
  int v31; // [rsp+98h] [rbp+48h] BYREF

  v7 = *a1;
  v8 = *a4;
  v26 = 0;
  P = 0;
  v31 = 0;
  v30 = 0;
  if ( a2 == 1 )
  {
    v27 = v7;
    v28 = 0;
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x58u);
    v10 = Heap;
    if ( Heap )
    {
      *(_QWORD *)Heap = a3;
      *((_QWORD *)Heap + 1) = 0;
      *((_DWORD *)Heap + 4) = v8;
      *((_QWORD *)Heap + 3) = &v31;
      *((_QWORD *)Heap + 4) = &v30;
      *((_QWORD *)Heap + 5) = &v27;
      RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 48));
      Item = 0;
    }
    else
    {
      LODWORD(v24) = v8;
      Item = -2147024882;
      v10 = 0;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xD9,
        (unsigned int)"onecore\\base\\appmodel\\StateManager\\ApiSet\\Inc\\StateContainerEnum.hpp",
        (const char *)0x8007000ELL,
        (int)"new %u",
        v24);
    }
    wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(
      &v26,
      v10);
    if ( Item < 0 )
    {
      v12 = "Create RegKeyItemFetcher";
      v13 = 312;
LABEL_6:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statecontainer.cpp",
        (const char *)(unsigned int)Item,
        (int)v12,
        v24);
      v14 = (char *)P;
      P = 0;
      if ( v14 )
      {
        RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v14 + 48));
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
      }
      v15 = (char *)v26;
      v26 = 0;
      if ( v15 )
      {
        RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v15 + 48));
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
      }
      return (unsigned int)Item;
    }
    do
      Item = StateEnumerator<RegKeyItemFetcher>::EnumerateNextItem(v26);
    while ( Item >= 0 );
  }
  else
  {
    v27 = v7;
    v28 = 0;
    v17 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x58u);
    v18 = v17;
    if ( v17 )
    {
      *(_QWORD *)v17 = a3;
      *((_QWORD *)v17 + 1) = 0;
      *((_DWORD *)v17 + 4) = v8;
      *((_QWORD *)v17 + 3) = &v31;
      *((_QWORD *)v17 + 4) = &v30;
      *((_QWORD *)v17 + 5) = &v27;
      RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v17 + 48));
      Item = 0;
    }
    else
    {
      LODWORD(v24) = v8;
      Item = -2147024882;
      v18 = 0;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xD9,
        (unsigned int)"onecore\\base\\appmodel\\StateManager\\ApiSet\\Inc\\StateContainerEnum.hpp",
        (const char *)0x8007000ELL,
        (int)"new %u",
        v24);
    }
    wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(
      &P,
      v18);
    if ( Item < 0 )
    {
      v12 = "Create RegValueItemFetcher";
      v13 = 335;
      goto LABEL_6;
    }
    do
      Item = StateEnumerator<RegValueItemFetcher>::EnumerateNextItem(P);
    while ( Item >= 0 );
  }
  if ( Item != -2147024637 )
  {
    LODWORD(v24) = a2;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x16E,
      (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statecontainer.cpp",
      (const char *)(unsigned int)Item,
      (int)"Type %u",
      v24);
    wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(
      &P,
      0);
    wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(
      &v26,
      0);
    return (unsigned int)Item;
  }
  v19 = v31;
  v20 = (char *)P;
  *a4 = v31;
  P = 0;
  if ( v19 )
  {
    if ( v30 )
    {
      if ( v20 )
      {
        RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v20 + 48));
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
      }
      v23 = (char *)v26;
      v26 = 0;
      if ( v23 )
      {
        RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v23 + 48));
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
      }
      return 2147942522LL;
    }
    else
    {
      if ( v20 )
      {
        RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v20 + 48));
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
      }
      v21 = (char *)v26;
      v26 = 0;
      if ( v21 )
      {
        RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v21 + 48));
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
      }
      return 0;
    }
  }
  else
  {
    if ( v20 )
    {
      RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v20 + 48));
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
    }
    v22 = (char *)v26;
    v26 = 0;
    if ( v22 )
    {
      RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v22 + 48));
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
    }
    return 2147942659LL;
  }
}

```

## disassembly

```asm
0x1800a3228  mov     [rsp-28h+arg_0], rbx
0x1800a322d  mov     [rsp-28h+arg_10], rsi
0x1800a3232  push    rbp
0x1800a3233  push    rdi
0x1800a3234  push    r12
0x1800a3236  push    r14
0x1800a3238  push    r15
0x1800a323a  mov     rbp, rsp
0x1800a323d  sub     rsp, 50h
0x1800a3241  mov     r14, r9
0x1800a3244  mov     rsi, r8
0x1800a3247  mov     r15d, edx
0x1800a324a  mov     rax, [rcx]; __annotation("Debug", "TelemetryAssert", "enumerateItemType > ENUMERATE_ITEM_UNDEFINED && enumerateItemType < ENUMERATE_ITEM_LAST")
0x1800a324d  xor     r12d, r12d
0x1800a3250  mov     ebx, [r9]
0x1800a3253  mov     [rbp+var_18], r12
0x1800a3257  mov     [rbp+P], r12
0x1800a325b  mov     [rbp+arg_18], r12d
0x1800a325f  mov     [rbp+arg_8], r12b
0x1800a3263  cmp     edx, 1
0x1800a3266  jnz     loc_1800A3389
0x1800a326c  mov     [rbp+var_10], rax; __annotation("Debug", "TelemetryAssert", "containerKey != NULL")
0x1800a3270  lea     r8d, [r15+57h]; Size
0x1800a3274  mov     [rbp+var_8], r12d
0x1800a3278  xor     edx, edx; Flags
0x1800a327a  mov     rcx, gs:60h
0x1800a3283  mov     rcx, [rcx+30h]; HeapHandle
0x1800a3287  call    cs:__imp_RtlAllocateHeap
0x1800a328e  nop     dword ptr [rax+rax+00h]
0x1800a3293  mov     rdi, rax
0x1800a3296  test    rax, rax
0x1800a3299  jz      loc_1800A3554
0x1800a329f  mov     [rax], rsi
0x1800a32a2  lea     rcx, [rdi+30h]; CriticalSection
0x1800a32a6  mov     [rax+8], r12
0x1800a32aa  mov     [rax+10h], ebx
0x1800a32ad  lea     rax, [rbp+arg_18]
0x1800a32b1  mov     [rdi+18h], rax
0x1800a32b5  lea     rax, [rbp+arg_8]
0x1800a32b9  mov     [rdi+20h], rax
0x1800a32bd  lea     rax, [rbp+var_10]
0x1800a32c1  mov     [rdi+28h], rax
0x1800a32c5  call    cs:__imp_RtlInitializeCriticalSection
0x1800a32cc  nop     dword ptr [rax+rax+00h]
0x1800a32d1  mov     ebx, r12d
0x1800a32d4  mov     rdx, rdi
0x1800a32d7  lea     rcx, [rbp+var_18]
0x1800a32db  call    ?reset@?$unique_ptr@V?$StateEnumerator@VRegKeyItemFetcher@@@@U?$default_delete@V?$StateEnumerator@VRegKeyItemFetcher@@@@@wistd@@@wistd@@QEAAXPEAV?$StateEnumerator@VRegKeyItemFetcher@@@@@Z; wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(StateEnumerator<RegKeyItemFetcher> *)
0x1800a32e0  test    ebx, ebx
0x1800a32e2  jns     loc_1800A34CB
0x1800a32e8  lea     rax, aCreateRegkeyit; "Create RegKeyItemFetcher"
0x1800a32ef  mov     edx, 138h; void *
0x1800a32f4  mov     rcx, [rbp+28h]; this
0x1800a32f8  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\statemanager\\"...
0x1800a32ff  mov     r9d, ebx; char *
0x1800a3302  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800a3307  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a330c  mov     rdi, [rbp+P]
0x1800a3310  mov     [rbp+P], r12
0x1800a3314  test    rdi, rdi
0x1800a3317  jz      short loc_1800A3347
0x1800a3319  lea     rcx, [rdi+30h]; CriticalSection
0x1800a331d  call    cs:__imp_RtlDeleteCriticalSection
0x1800a3324  nop     dword ptr [rax+rax+00h]
0x1800a3329  mov     rcx, gs:60h
0x1800a3332  mov     r8, rdi; P
0x1800a3335  xor     edx, edx; Flags
0x1800a3337  mov     rcx, [rcx+30h]; HeapHandle
0x1800a333b  call    cs:__imp_RtlFreeHeap
0x1800a3342  nop     dword ptr [rax+rax+00h]
0x1800a3347  mov     rdi, [rbp+var_18]
0x1800a334b  mov     [rbp+var_18], r12
0x1800a334f  test    rdi, rdi
0x1800a3352  jz      short loc_1800A3382
0x1800a3354  lea     rcx, [rdi+30h]; CriticalSection
0x1800a3358  call    cs:__imp_RtlDeleteCriticalSection
0x1800a335f  nop     dword ptr [rax+rax+00h]
0x1800a3364  mov     rcx, gs:60h
0x1800a336d  mov     r8, rdi; P
0x1800a3370  xor     edx, edx; Flags
0x1800a3372  mov     rcx, [rcx+30h]; HeapHandle
0x1800a3376  call    cs:__imp_RtlFreeHeap
0x1800a337d  nop     dword ptr [rax+rax+00h]
0x1800a3382  mov     eax, ebx
0x1800a3384  jmp     loc_1800A34B1
0x1800a3389  mov     [rbp+var_10], rax; __annotation("Debug", "TelemetryAssert", "containerKey != NULL")
0x1800a338d  xor     edx, edx; Flags
0x1800a338f  mov     [rbp+var_8], r12d
0x1800a3393  mov     rcx, gs:60h
0x1800a339c  lea     r8d, [rdx+58h]; Size
0x1800a33a0  mov     rcx, [rcx+30h]; HeapHandle
0x1800a33a4  call    cs:__imp_RtlAllocateHeap
0x1800a33ab  nop     dword ptr [rax+rax+00h]
0x1800a33b0  mov     rdi, rax
0x1800a33b3  test    rax, rax
0x1800a33b6  jz      loc_1800A3601
0x1800a33bc  mov     [rax], rsi
0x1800a33bf  lea     rcx, [rdi+30h]; CriticalSection
0x1800a33c3  mov     [rax+8], r12
0x1800a33c7  mov     [rax+10h], ebx
0x1800a33ca  lea     rax, [rbp+arg_18]
0x1800a33ce  mov     [rdi+18h], rax
0x1800a33d2  lea     rax, [rbp+arg_8]
0x1800a33d6  mov     [rdi+20h], rax
0x1800a33da  lea     rax, [rbp+var_10]
0x1800a33de  mov     [rdi+28h], rax
0x1800a33e2  call    cs:__imp_RtlInitializeCriticalSection
0x1800a33e9  nop     dword ptr [rax+rax+00h]
0x1800a33ee  mov     ebx, r12d
0x1800a33f1  mov     rdx, rdi
0x1800a33f4  lea     rcx, [rbp+P]
0x1800a33f8  call    ?reset@?$unique_ptr@V?$StateEnumerator@VRegKeyItemFetcher@@@@U?$default_delete@V?$StateEnumerator@VRegKeyItemFetcher@@@@@wistd@@@wistd@@QEAAXPEAV?$StateEnumerator@VRegKeyItemFetcher@@@@@Z; wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(StateEnumerator<RegKeyItemFetcher> *)
0x1800a33fd  test    ebx, ebx
0x1800a33ff  js      loc_1800A367A
0x1800a3405  mov     rcx, [rbp+P]; __annotation("Debug", "TelemetryAssert", "containerValueEnumerator != NULL")
0x1800a3409  call    ?EnumerateNextItem@?$StateEnumerator@VRegValueItemFetcher@@@@QEAAJXZ; StateEnumerator<RegValueItemFetcher>::EnumerateNextItem(void)
0x1800a340e  mov     ebx, eax
0x1800a3410  test    eax, eax
0x1800a3412  jns     short loc_1800A3405
0x1800a3414  mov     edi, 80070103h
0x1800a3419  cmp     ebx, edi
0x1800a341b  jnz     loc_1800A3636
0x1800a3421  mov     eax, [rbp+arg_18]
0x1800a3424  mov     rbx, [rbp+P]
0x1800a3428  mov     [r14], eax
0x1800a342b  mov     [rbp+P], r12
0x1800a342f  test    eax, eax
0x1800a3431  jz      loc_1800A34DF
0x1800a3437  cmp     [rbp+arg_8], r12b
0x1800a343b  jnz     loc_1800A3589
0x1800a3441  test    rbx, rbx
0x1800a3444  jz      short loc_1800A3474
0x1800a3446  lea     rcx, [rbx+30h]; CriticalSection
0x1800a344a  call    cs:__imp_RtlDeleteCriticalSection
0x1800a3451  nop     dword ptr [rax+rax+00h]
0x1800a3456  mov     rcx, gs:60h
0x1800a345f  mov     r8, rbx; P
0x1800a3462  xor     edx, edx; Flags
0x1800a3464  mov     rcx, [rcx+30h]; HeapHandle
0x1800a3468  call    cs:__imp_RtlFreeHeap
0x1800a346f  nop     dword ptr [rax+rax+00h]
0x1800a3474  mov     rbx, [rbp+var_18]
0x1800a3478  mov     [rbp+var_18], r12
0x1800a347c  test    rbx, rbx
0x1800a347f  jz      short loc_1800A34AF
0x1800a3481  lea     rcx, [rbx+30h]; CriticalSection
0x1800a3485  call    cs:__imp_RtlDeleteCriticalSection
0x1800a348c  nop     dword ptr [rax+rax+00h]
0x1800a3491  mov     rcx, gs:60h
0x1800a349a  mov     r8, rbx; P
0x1800a349d  xor     edx, edx; Flags
0x1800a349f  mov     rcx, [rcx+30h]; HeapHandle
0x1800a34a3  call    cs:__imp_RtlFreeHeap
0x1800a34aa  nop     dword ptr [rax+rax+00h]
0x1800a34af  xor     eax, eax
0x1800a34b1  lea     r11, [rsp+50h+var_s0]
0x1800a34b6  mov     rbx, [r11+30h]
0x1800a34ba  mov     rsi, [r11+40h]
0x1800a34be  mov     rsp, r11
0x1800a34c1  pop     r15
0x1800a34c3  pop     r14
0x1800a34c5  pop     r12
0x1800a34c7  pop     rdi
0x1800a34c8  pop     rbp
0x1800a34c9  retn
0x1800a34cb  mov     rcx, [rbp+var_18]; __annotation("Debug", "TelemetryAssert", "containerKeyEnumerator != NULL")
0x1800a34cf  call    ?EnumerateNextItem@?$StateEnumerator@VRegKeyItemFetcher@@@@QEAAJXZ; StateEnumerator<RegKeyItemFetcher>::EnumerateNextItem(void)
0x1800a34d4  mov     ebx, eax
0x1800a34d6  test    eax, eax
0x1800a34d8  jns     short loc_1800A34CB
0x1800a34da  jmp     loc_1800A3414
0x1800a34df  test    rbx, rbx
0x1800a34e2  jz      short loc_1800A3512
0x1800a34e4  lea     rcx, [rbx+30h]; CriticalSection
0x1800a34e8  call    cs:__imp_RtlDeleteCriticalSection
0x1800a34ef  nop     dword ptr [rax+rax+00h]
0x1800a34f4  mov     rcx, gs:60h
0x1800a34fd  mov     r8, rbx; P
0x1800a3500  xor     edx, edx; Flags
0x1800a3502  mov     rcx, [rcx+30h]; HeapHandle
0x1800a3506  call    cs:__imp_RtlFreeHeap
0x1800a350d  nop     dword ptr [rax+rax+00h]
0x1800a3512  mov     rbx, [rbp+var_18]
0x1800a3516  mov     [rbp+var_18], r12
0x1800a351a  test    rbx, rbx
0x1800a351d  jz      short loc_1800A354D
0x1800a351f  lea     rcx, [rbx+30h]; CriticalSection
0x1800a3523  call    cs:__imp_RtlDeleteCriticalSection
0x1800a352a  nop     dword ptr [rax+rax+00h]
0x1800a352f  mov     rcx, gs:60h
0x1800a3538  mov     r8, rbx; P
0x1800a353b  xor     edx, edx; Flags
0x1800a353d  mov     rcx, [rcx+30h]; HeapHandle
0x1800a3541  call    cs:__imp_RtlFreeHeap
0x1800a3548  nop     dword ptr [rax+rax+00h]
0x1800a354d  mov     eax, edi
0x1800a354f  jmp     loc_1800A34B1
0x1800a3554  mov     rcx, [rbp+28h]; this
0x1800a3558  lea     rax, aNewU; "new %u"
0x1800a355f  mov     dword ptr [rsp+50h+var_28], ebx; char *
0x1800a3563  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\StateManager\\"...
0x1800a356a  mov     ebx, 8007000Eh
0x1800a356f  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800a3574  mov     r9d, ebx; char *
0x1800a3577  mov     edx, 0D9h; void *
0x1800a357c  mov     rdi, r12
0x1800a357f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a3584  jmp     loc_1800A32D4
0x1800a3589  test    rbx, rbx
0x1800a358c  jz      short loc_1800A35BC
0x1800a358e  lea     rcx, [rbx+30h]; CriticalSection
0x1800a3592  call    cs:__imp_RtlDeleteCriticalSection
0x1800a3599  nop     dword ptr [rax+rax+00h]
0x1800a359e  mov     rcx, gs:60h
0x1800a35a7  mov     r8, rbx; P
0x1800a35aa  xor     edx, edx; Flags
0x1800a35ac  mov     rcx, [rcx+30h]; HeapHandle
0x1800a35b0  call    cs:__imp_RtlFreeHeap
0x1800a35b7  nop     dword ptr [rax+rax+00h]
0x1800a35bc  mov     rbx, [rbp+var_18]
0x1800a35c0  mov     [rbp+var_18], r12
0x1800a35c4  test    rbx, rbx
0x1800a35c7  jz      short loc_1800A35F7
0x1800a35c9  lea     rcx, [rbx+30h]; CriticalSection
0x1800a35cd  call    cs:__imp_RtlDeleteCriticalSection
0x1800a35d4  nop     dword ptr [rax+rax+00h]
0x1800a35d9  mov     rcx, gs:60h
0x1800a35e2  mov     r8, rbx; P
0x1800a35e5  xor     edx, edx; Flags
0x1800a35e7  mov     rcx, [rcx+30h]; HeapHandle
0x1800a35eb  call    cs:__imp_RtlFreeHeap
0x1800a35f2  nop     dword ptr [rax+rax+00h]
0x1800a35f7  mov     eax, 8007007Ah
0x1800a35fc  jmp     loc_1800A34B1
0x1800a3601  mov     rcx, [rbp+28h]; this
0x1800a3605  lea     rax, aNewU; "new %u"
0x1800a360c  mov     dword ptr [rsp+50h+var_28], ebx; char *
0x1800a3610  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\StateManager\\"...
0x1800a3617  mov     ebx, 8007000Eh
0x1800a361c  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800a3621  mov     r9d, ebx; char *
0x1800a3624  mov     edx, 0D9h; void *
0x1800a3629  mov     rdi, r12
0x1800a362c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a3631  jmp     loc_1800A33F1
0x1800a3636  mov     rcx, [rbp+28h]; this
0x1800a363a  lea     rax, aTypeU; "Type %u"
0x1800a3641  mov     dword ptr [rsp+50h+var_28], r15d; char *
0x1800a3646  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\statemanager\\"...
0x1800a364d  mov     r9d, ebx; char *
0x1800a3650  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800a3655  mov     edx, 16Eh; void *
0x1800a365a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a365f  xor     edx, edx
0x1800a3661  lea     rcx, [rbp+P]
0x1800a3665  call    ?reset@?$unique_ptr@V?$StateEnumerator@VRegKeyItemFetcher@@@@U?$default_delete@V?$StateEnumerator@VRegKeyItemFetcher@@@@@wistd@@@wistd@@QEAAXPEAV?$StateEnumerator@VRegKeyItemFetcher@@@@@Z; wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(StateEnumerator<RegKeyItemFetcher> *)
0x1800a366a  xor     edx, edx
0x1800a366c  lea     rcx, [rbp+var_18]
0x1800a3670  call    ?reset@?$unique_ptr@V?$StateEnumerator@VRegKeyItemFetcher@@@@U?$default_delete@V?$StateEnumerator@VRegKeyItemFetcher@@@@@wistd@@@wistd@@QEAAXPEAV?$StateEnumerator@VRegKeyItemFetcher@@@@@Z; wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(StateEnumerator<RegKeyItemFetcher> *)
0x1800a3675  jmp     loc_1800A3382
0x1800a367a  lea     rax, aCreateRegvalue; "Create RegValueItemFetcher"
0x1800a3681  mov     edx, 14Fh
0x1800a3686  jmp     loc_1800A32F4
```
