# StateAtom::EnumerateSettingNodes(tag_STATE_ENUM_ITEM *,uint *)

- ea: `0x18009e9fc`
- end: `0x18009ecb3`
- name: `?EnumerateSettingNodes@StateAtom@@QEBAJPEAUtag_STATE_ENUM_ITEM@@PEAI@Z`
- size: `695`
- prototype: `__int64 __fastcall(StateAtom *__hidden this, struct tag_STATE_ENUM_ITEM *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18009e948`

## callees

- `0x18005997c`
- `0x18009e9fc`
- `0x18009ecbc`
- `0x18009eee0`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18009eb14`
- `ntdll!RtlDeleteCriticalSection` at `0x18009ebc6`
- `ntdll!RtlDeleteCriticalSection` at `0x18009ec82`
- `ntdll!RtlDeleteCriticalSection` at `0x18009eb14`
- `ntdll!RtlDeleteCriticalSection` at `0x18009ebc6`
- `ntdll!RtlDeleteCriticalSection` at `0x18009ec82`
- `ntdll!RtlInitializeCriticalSection` at `0x18009eaa8`
- `ntdll!RtlInitializeCriticalSection` at `0x18009eaa8`
- `ntdll!RtlReleaseSRWLockShared` at `0x18009eaf3`
- `ntdll!RtlReleaseSRWLockShared` at `0x18009eb80`
- `ntdll!RtlReleaseSRWLockShared` at `0x18009eba5`
- `ntdll!RtlReleaseSRWLockShared` at `0x18009ec61`
- `ntdll!RtlReleaseSRWLockShared` at `0x18009eaf3`
- `ntdll!RtlReleaseSRWLockShared` at `0x18009eb80`
- `ntdll!RtlReleaseSRWLockShared` at `0x18009eba5`
- `ntdll!RtlReleaseSRWLockShared` at `0x18009ec61`
- `ntdll!RtlAcquireSRWLockShared` at `0x18009ea44`
- `ntdll!RtlAcquireSRWLockShared` at `0x18009ea44`
- `ntdll!RtlFreeHeap` at `0x18009eb32`
- `ntdll!RtlFreeHeap` at `0x18009ebe4`
- `ntdll!RtlFreeHeap` at `0x18009eca0`
- `ntdll!RtlFreeHeap` at `0x18009eb32`
- `ntdll!RtlFreeHeap` at `0x18009ebe4`
- `ntdll!RtlFreeHeap` at `0x18009eca0`
- `ntdll!RtlAllocateHeap` at `0x18009ea66`
- `ntdll!RtlAllocateHeap` at `0x18009ea66`

## string_xrefs

- `0x18009ec48`: `Create %u`

## pseudocode

```c
__int64 __fastcall StateAtom::EnumerateSettingNodes(StateAtom *this, struct tag_STATE_ENUM_ITEM *a2, unsigned int *a3)
{
  char *v5; // rbx
  int v6; // esi
  char *Heap; // rax
  char *v8; // rdi
  int v9; // esi
  int Item; // eax
  unsigned int v11; // edi
  unsigned int v12; // eax
  char *v13; // rcx
  char *v14; // rbx
  char *v16; // rbx
  char *v17; // rbx
  char *v18; // [rsp+28h] [rbp-18h]
  __int64 v19; // [rsp+30h] [rbp-10h] BYREF
  __int64 v20; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  char v22; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v23; // [rsp+80h] [rbp+40h] BYREF
  PVOID P; // [rsp+88h] [rbp+48h] BYREF

  v5 = (char *)this + 24;
  v19 = *((_QWORD *)this + 2);
  v20 = *((unsigned int *)this + 1);
  P = 0;
  v23 = 0;
  v22 = 0;
  RtlAcquireSRWLockShared((char *)this + 24);
  v6 = *a3;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x58u);
  v8 = Heap;
  if ( Heap )
  {
    *(_QWORD *)Heap = a2;
    *((_QWORD *)Heap + 1) = 0;
    *((_DWORD *)Heap + 4) = v6;
    *((_QWORD *)Heap + 3) = &v23;
    *((_QWORD *)Heap + 4) = &v22;
    *((_QWORD *)Heap + 5) = &v19;
    RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 48));
    v9 = 0;
  }
  else
  {
    LODWORD(v18) = v6;
    v9 = -2147024882;
    v8 = 0;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\base\\appmodel\\StateManager\\ApiSet\\Inc\\StateContainerEnum.hpp",
      (const char *)0x8007000ELL,
      (int)"new %u",
      v18,
      v19,
      v20);
  }
  wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(
    &P,
    v8);
  if ( v9 < 0 )
  {
    LODWORD(v18) = *a3;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2B4,
      (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\stateatom.cpp",
      (const char *)(unsigned int)v9,
      (int)"Create %u",
      v18);
    v13 = v5;
LABEL_7:
    RtlReleaseSRWLockShared(v13);
    v14 = (char *)P;
    P = 0;
    if ( v14 )
    {
      RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v14 + 48));
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
    }
    return (unsigned int)v9;
  }
  do
  {
    Item = StateEnumerator<AtomSettingsItemFetcher>::EnumerateNextItem(P);
    v11 = Item;
  }
  while ( Item >= 0 );
  v9 = -2147024637;
  if ( Item != -2147024637 )
  {
    LODWORD(v18) = *a3;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2D4,
      (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\stateatom.cpp",
      (const char *)(unsigned int)Item,
      (int)"EnumerateNextItem %u",
      v18);
    RtlReleaseSRWLockShared(v5);
    wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(
      &P,
      0);
    return v11;
  }
  v12 = v23;
  v13 = v5;
  *a3 = v23;
  if ( !v12 )
    goto LABEL_7;
  if ( v22 )
  {
    RtlReleaseSRWLockShared(v5);
    v16 = (char *)P;
    P = 0;
    if ( v16 )
    {
      RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v16 + 48));
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
    }
    return 2147942522LL;
  }
  else
  {
    RtlReleaseSRWLockShared(v5);
    v17 = (char *)P;
    P = 0;
    if ( v17 )
    {
      RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v17 + 48));
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18009e9fc  mov     [rsp-28h+arg_8], rbx
0x18009ea01  push    rbp
0x18009ea02  push    rsi
0x18009ea03  push    rdi
0x18009ea04  push    r14
0x18009ea06  push    r15
0x18009ea08  mov     rbp, rsp
0x18009ea0b  sub     rsp, 40h
0x18009ea0f  mov     r14, r8
0x18009ea12  mov     r15, rdx
0x18009ea15  mov     rax, [rcx+10h]; __annotation("Debug", "TelemetryAssert", "bufferLength != NULL")
0x18009ea19  lea     rbx, [rcx+18h]
0x18009ea1d  mov     [rbp+var_10], rax
0x18009ea21  mov     eax, [rcx+4]
0x18009ea24  mov     rcx, rbx
0x18009ea27  mov     [rbp+var_8], eax
0x18009ea2a  mov     [rbp+var_4], 0
0x18009ea31  mov     [rbp+P], 0
0x18009ea39  mov     [rbp+arg_10], 0
0x18009ea40  mov     [rbp+arg_0], 0
0x18009ea44  call    cs:__imp_RtlAcquireSRWLockShared
0x18009ea4b  nop     dword ptr [rax+rax+00h]
0x18009ea50  mov     rcx, gs:60h
0x18009ea59  xor     edx, edx; Flags
0x18009ea5b  mov     esi, [r14]
0x18009ea5e  mov     rcx, [rcx+30h]; HeapHandle
0x18009ea62  lea     r8d, [rdx+58h]; Size
0x18009ea66  call    cs:__imp_RtlAllocateHeap
0x18009ea6d  nop     dword ptr [rax+rax+00h]
0x18009ea72  mov     rdi, rax
0x18009ea75  test    rax, rax
0x18009ea78  jz      loc_18009EBFA
0x18009ea7e  mov     [rax], r15
0x18009ea81  lea     rcx, [rdi+30h]; CriticalSection
0x18009ea85  mov     qword ptr [rax+8], 0
0x18009ea8d  mov     [rax+10h], esi
0x18009ea90  lea     rax, [rbp+arg_10]
0x18009ea94  mov     [rdi+18h], rax
0x18009ea98  lea     rax, [rbp+arg_0]
0x18009ea9c  mov     [rdi+20h], rax
0x18009eaa0  lea     rax, [rbp+var_10]
0x18009eaa4  mov     [rdi+28h], rax
0x18009eaa8  call    cs:__imp_RtlInitializeCriticalSection
0x18009eaaf  nop     dword ptr [rax+rax+00h]
0x18009eab4  xor     esi, esi
0x18009eab6  mov     rdx, rdi
0x18009eab9  lea     rcx, [rbp+P]
0x18009eabd  call    ?reset@?$unique_ptr@V?$StateEnumerator@VRegKeyItemFetcher@@@@U?$default_delete@V?$StateEnumerator@VRegKeyItemFetcher@@@@@wistd@@@wistd@@QEAAXPEAV?$StateEnumerator@VRegKeyItemFetcher@@@@@Z; wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(StateEnumerator<RegKeyItemFetcher> *)
0x18009eac2  test    esi, esi
0x18009eac4  js      loc_18009EC2E
0x18009eaca  mov     rcx, [rbp+P]; __annotation("Debug", "TelemetryAssert", "containerValueEnumerator.get() != NULL")
0x18009eace  call    ?EnumerateNextItem@?$StateEnumerator@VAtomSettingsItemFetcher@@@@QEAAJXZ; StateEnumerator<AtomSettingsItemFetcher>::EnumerateNextItem(void)
0x18009ead3  mov     edi, eax
0x18009ead5  test    eax, eax
0x18009ead7  jns     short loc_18009EACA
0x18009ead9  mov     esi, 80070103h
0x18009eade  cmp     eax, esi
0x18009eae0  jnz     short loc_18009EB52
0x18009eae2  mov     eax, [rbp+arg_10]
0x18009eae5  mov     rcx, rbx
0x18009eae8  mov     [r14], eax
0x18009eaeb  test    eax, eax
0x18009eaed  jnz     loc_18009EB9B
0x18009eaf3  call    cs:__imp_RtlReleaseSRWLockShared
0x18009eafa  nop     dword ptr [rax+rax+00h]
0x18009eaff  mov     rbx, [rbp+P]
0x18009eb03  mov     [rbp+P], 0
0x18009eb0b  test    rbx, rbx
0x18009eb0e  jz      short loc_18009EB3E
0x18009eb10  lea     rcx, [rbx+30h]; CriticalSection
0x18009eb14  call    cs:__imp_RtlDeleteCriticalSection
0x18009eb1b  nop     dword ptr [rax+rax+00h]
0x18009eb20  mov     rcx, gs:60h
0x18009eb29  mov     r8, rbx; P
0x18009eb2c  xor     edx, edx; Flags
0x18009eb2e  mov     rcx, [rcx+30h]; HeapHandle
0x18009eb32  call    cs:__imp_RtlFreeHeap
0x18009eb39  nop     dword ptr [rax+rax+00h]
0x18009eb3e  mov     eax, esi
0x18009eb40  mov     rbx, [rsp+40h+arg_8]
0x18009eb45  add     rsp, 40h
0x18009eb49  pop     r15
0x18009eb4b  pop     r14
0x18009eb4d  pop     rdi
0x18009eb4e  pop     rsi
0x18009eb4f  pop     rbp
0x18009eb50  retn
0x18009eb52  mov     eax, [r14]
0x18009eb55  lea     r8, aOnecoreBaseApp_54; "onecore\\base\\appmodel\\statemanager\\"...
0x18009eb5c  mov     rcx, [rbp+28h]; this
0x18009eb60  mov     r9d, edi; char *
0x18009eb63  mov     dword ptr [rsp+40h+var_18], eax; char *
0x18009eb67  mov     edx, 2D4h; void *
0x18009eb6c  lea     rax, aEnumeratenexti; "EnumerateNextItem %u"
0x18009eb73  mov     qword ptr [rsp+40h+var_20], rax; int
0x18009eb78  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18009eb7d  mov     rcx, rbx
0x18009eb80  call    cs:__imp_RtlReleaseSRWLockShared
0x18009eb87  nop     dword ptr [rax+rax+00h]
0x18009eb8c  xor     edx, edx
0x18009eb8e  lea     rcx, [rbp+P]
0x18009eb92  call    ?reset@?$unique_ptr@V?$StateEnumerator@VRegKeyItemFetcher@@@@U?$default_delete@V?$StateEnumerator@VRegKeyItemFetcher@@@@@wistd@@@wistd@@QEAAXPEAV?$StateEnumerator@VRegKeyItemFetcher@@@@@Z; wistd::unique_ptr<StateEnumerator<RegKeyItemFetcher>,wistd::default_delete<StateEnumerator<RegKeyItemFetcher>>>::reset(StateEnumerator<RegKeyItemFetcher> *)
0x18009eb97  mov     eax, edi
0x18009eb99  jmp     short loc_18009EB40
0x18009eb9b  cmp     [rbp+arg_0], 0
0x18009eb9f  jz      loc_18009EC61
0x18009eba5  call    cs:__imp_RtlReleaseSRWLockShared
0x18009ebac  nop     dword ptr [rax+rax+00h]
0x18009ebb1  mov     rbx, [rbp+P]
0x18009ebb5  mov     [rbp+P], 0
0x18009ebbd  test    rbx, rbx
0x18009ebc0  jz      short loc_18009EBF0
0x18009ebc2  lea     rcx, [rbx+30h]; CriticalSection
0x18009ebc6  call    cs:__imp_RtlDeleteCriticalSection
0x18009ebcd  nop     dword ptr [rax+rax+00h]
0x18009ebd2  mov     rcx, gs:60h
0x18009ebdb  mov     r8, rbx; P
0x18009ebde  xor     edx, edx; Flags
0x18009ebe0  mov     rcx, [rcx+30h]; HeapHandle
0x18009ebe4  call    cs:__imp_RtlFreeHeap
0x18009ebeb  nop     dword ptr [rax+rax+00h]
0x18009ebf0  mov     eax, 8007007Ah
0x18009ebf5  jmp     loc_18009EB40
0x18009ebfa  mov     rcx, [rbp+28h]; this
0x18009ebfe  lea     rax, aNewU; "new %u"
0x18009ec05  mov     dword ptr [rsp+40h+var_18], esi; char *
0x18009ec09  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\StateManager\\"...
0x18009ec10  mov     esi, 8007000Eh
0x18009ec15  mov     qword ptr [rsp+40h+var_20], rax; int
0x18009ec1a  mov     r9d, esi; char *
0x18009ec1d  xor     edi, edi
0x18009ec1f  mov     edx, 0D9h; void *
0x18009ec24  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18009ec29  jmp     loc_18009EAB6
0x18009ec2e  mov     eax, [r14]
0x18009ec31  lea     r8, aOnecoreBaseApp_54; "onecore\\base\\appmodel\\statemanager\\"...
0x18009ec38  mov     rcx, [rbp+28h]; this
0x18009ec3c  mov     r9d, esi; char *
0x18009ec3f  mov     dword ptr [rsp+40h+var_18], eax; char *
0x18009ec43  mov     edx, 2B4h; void *
0x18009ec48  lea     rax, aCreateU; "Create %u"
0x18009ec4f  mov     qword ptr [rsp+40h+var_20], rax; int
0x18009ec54  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18009ec59  mov     rcx, rbx
0x18009ec5c  jmp     loc_18009EAF3
0x18009ec61  call    cs:__imp_RtlReleaseSRWLockShared
0x18009ec68  nop     dword ptr [rax+rax+00h]
0x18009ec6d  mov     rbx, [rbp+P]
0x18009ec71  mov     [rbp+P], 0
0x18009ec79  test    rbx, rbx
0x18009ec7c  jz      short loc_18009ECAC
0x18009ec7e  lea     rcx, [rbx+30h]; CriticalSection
0x18009ec82  call    cs:__imp_RtlDeleteCriticalSection
0x18009ec89  nop     dword ptr [rax+rax+00h]
0x18009ec8e  mov     rcx, gs:60h
0x18009ec97  mov     r8, rbx; P
0x18009ec9a  xor     edx, edx; Flags
0x18009ec9c  mov     rcx, [rcx+30h]; HeapHandle
0x18009eca0  call    cs:__imp_RtlFreeHeap
0x18009eca7  nop     dword ptr [rax+rax+00h]
0x18009ecac  xor     eax, eax
0x18009ecae  jmp     loc_18009EB40
```
