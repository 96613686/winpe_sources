# DusmCache::SetDataPlan(DusmConnection const &,_DUSM_SOURCE,_DUSM_DATAPLAN_STATUS const &)

- ea: `0x18001d524`
- end: `0x18001d5dc`
- name: `?SetDataPlan@DusmCache@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_DATAPLAN_STATUS@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(__int64, unsigned int, const void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180015cc0`
- `0x180016190`

## callees

- `0x1800173fc`
- `0x18001b544`
- `0x18001b754`
- `0x18001b944`
- `0x18001d524`
- `0x18001d87c`
- `0x18001d910`
- `0x18001fd20`
- `0x18002b9f0`

## string_xrefs

- `0x18001d5ca`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001d5b8`: `DusmCache::SetDataPlan::invalidDataPlan`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DusmCache::SetDataPlan(__int64 a1, unsigned int a2, const void *a3)
{
  __int128 v6; // xmm0
  __int64 v7; // rcx
  unsigned int v8; // edx
  const char *v9; // rax
  const char *v11; // [rsp+28h] [rbp-30h]
  int v12; // [rsp+30h] [rbp-28h] BYREF
  __int128 v13; // [rsp+34h] [rbp-24h]
  int v14; // [rsp+44h] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !(unsigned int)DusmIsValidDataPlan(a3) )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x33B,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
      (const char *)0x57,
      (unsigned int)"DusmCache::SetDataPlan::invalidDataPlan",
      v11);
  v6 = *(_OWORD *)(a1 + 32);
  v7 = *(unsigned int *)(a1 + 16);
  v12 = 1;
  v13 = v6;
  v14 = DusmMediaToIfType(v7);
  v9 = (const char *)EnumToString(v8);
  NetworkingTriageScenario::GetConnected::DataPlanChangedEvent(
    (const struct NetworkingTriageScenario::GetConnected::RequiredFields *)&v12,
    v9,
    0);
  DusmStore::SetDataPlan(a1, a2, a3, 0);
  DusmCache::UpdateCostFromConnection(a1, a2);
  return DusmCore::SetDataPlan(a1, a3, a2);
}

```

## disassembly

```asm
0x18001d524  mov     [rsp+arg_0], rbx
0x18001d529  mov     [rsp+arg_8], rsi
0x18001d52e  push    rdi
0x18001d52f  sub     rsp, 50h
0x18001d533  mov     rsi, rcx
0x18001d536  mov     rdi, r8
0x18001d539  mov     rcx, r8
0x18001d53c  mov     ebx, edx
0x18001d53e  call    ?DusmIsValidDataPlan@@YAHAEBU_DUSM_DATAPLAN_STATUS@@W4_DUSM_SOURCE@@@Z; DusmIsValidDataPlan(_DUSM_DATAPLAN_STATUS const &,_DUSM_SOURCE)
0x18001d543  test    eax, eax
0x18001d545  jz      short loc_18001D5B3
0x18001d547  movups  xmm0, xmmword ptr [rsi+20h]
0x18001d54b  mov     ecx, [rsi+10h]
0x18001d54e  mov     [rsp+58h+var_28], 1
0x18001d556  movdqu  [rsp+58h+var_24], xmm0
0x18001d55c  call    ?DusmMediaToIfType@@YAIW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaToIfType(_DUSM_MEDIA_TYPE)
0x18001d561  mov     ecx, edx
0x18001d563  mov     [rsp+58h+var_14], eax
0x18001d567  call    ?EnumToString@@YAPEBDW4_DUSM_SOURCE@@@Z; EnumToString(_DUSM_SOURCE)
0x18001d56c  mov     rdx, rax; char *
0x18001d56f  lea     rcx, [rsp+58h+var_28]; struct NetworkingTriageScenario::GetConnected::RequiredFields *
0x18001d574  xor     r8d, r8d; bool
0x18001d577  call    ?DataPlanChangedEvent@GetConnected@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBD_N@Z; NetworkingTriageScenario::GetConnected::DataPlanChangedEvent(NetworkingTriageScenario::GetConnected::RequiredFields const &,char const *,bool)
0x18001d57c  xor     r9d, r9d
0x18001d57f  mov     r8, rdi
0x18001d582  mov     edx, ebx
0x18001d584  mov     rcx, rsi
0x18001d587  call    ?SetDataPlan@DusmStore@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_DATAPLAN_STATUS@@H@Z; DusmStore::SetDataPlan(DusmConnection const &,_DUSM_SOURCE,_DUSM_DATAPLAN_STATUS const &,int)
0x18001d58c  mov     edx, ebx
0x18001d58e  mov     rcx, rsi
0x18001d591  call    ?UpdateCostFromConnection@DusmCache@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@@Z; DusmCache::UpdateCostFromConnection(DusmConnection const &,_DUSM_SOURCE)
0x18001d596  mov     r8d, ebx
0x18001d599  mov     rdx, rdi
0x18001d59c  mov     rcx, rsi
0x18001d59f  mov     rbx, [rsp+58h+arg_0]
0x18001d5a4  mov     rsi, [rsp+58h+arg_8]
0x18001d5a9  add     rsp, 50h
0x18001d5ad  pop     rdi
0x18001d5ae  jmp     ?SetDataPlan@DusmCore@@SAXAEBVDusmConnection@@AEBU_DUSM_DATAPLAN_STATUS@@W4_DUSM_SOURCE@@@Z; DusmCore::SetDataPlan(DusmConnection const &,_DUSM_DATAPLAN_STATUS const &,_DUSM_SOURCE)
0x18001d5b3  mov     rcx, [rsp+58h]; this
0x18001d5b8  lea     rax, aDusmcacheSetda; "DusmCache::SetDataPlan::invalidDataPlan"
0x18001d5bf  mov     r9d, 57h ; 'W'; char *
0x18001d5c5  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x18001d5ca  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001d5d1  mov     edx, 33Bh; void *
0x18001d5d6  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
