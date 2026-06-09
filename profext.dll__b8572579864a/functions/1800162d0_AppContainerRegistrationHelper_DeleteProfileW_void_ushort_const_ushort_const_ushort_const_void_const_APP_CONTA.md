# AppContainerRegistrationHelper::DeleteProfileW(void *,ushort const *,ushort const *,ushort const *,void * const,APP_CONTAINER_PROFILE_TYPE,_GUID const *)

- ea: `0x1800162d0`
- end: `0x18001654b`
- name: `?DeleteProfileW@AppContainerRegistrationHelper@@SAJPEAXPEBG11QEAXW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z`
- size: `635`
- prototype: `__int64 __fastcall(__int64, const char *, __int64, __int64, void *, unsigned int, struct _GUID *)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009a34`
- `0x18000ca58`
- `0x18000d980`

## callees

- `0x1800040c0`
- `0x1800041ec`
- `0x180005174`
- `0x18000a2f8`
- `0x18000a540`
- `0x18000c250`
- `0x18000fcb4`
- `0x180012424`
- `0x1800162d0`
- `0x180016644`

## import_xrefs

- `KERNELBASE!AppContainerUnregisterSid` at `0x1800164b1`
- `KERNELBASE!AppContainerUnregisterSid` at `0x1800164b1`
- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationDeleteAppContainer` at `0x180016429`
- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationDeleteAppContainer` at `0x180016429`

## string_xrefs

- `0x180016321`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800163a7`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18001643d`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800164ec`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800162e9`: `Name %ls Sid %ls`
- `0x18001639b`: `Name %ls Sid %ls`
- `0x1800164e0`: `Name %ls Sid %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall AppContainerRegistrationHelper::DeleteProfileW(
        __int64 a1,
        const char *a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        unsigned int a6,
        struct _GUID *a7)
{
  signed int v7; // ebx
  unsigned int v12; // eax
  signed int v13; // ecx
  int v14; // eax
  int v15; // edi
  char v16; // r14
  bool v17; // al
  const char *v18; // rdi
  unsigned int v19; // edi
  int v21; // [rsp+20h] [rbp-68h]
  int v22; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v7 = 0;
  if ( !a1 )
  {
    v12 = AppContainerRegistrationHelper::CleanupChildAppContainers(a5, a7);
    v13 = wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0x856,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)v12,
            (__int64)"Name %ls Sid %ls",
            a2,
            a4);
    if ( ((v13 + 0x80000000) & 0x80000000) == 0 && v13 != -2147024894 )
      v7 = v13;
  }
  v14 = AppContainerRegistrationHelper::DeleteStorageLocations(a1, a2, a4, a6, a7);
  v15 = v14;
  v16 = 1;
  v17 = v14 < 0 && v14 != -2147024891 && v14 != -2147024864;
  LOBYTE(v21) = v17;
  wil::details::in1diag3::Log_HrIfMsg(
    retaddr,
    (void *)0x863,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
    (const char *)(unsigned int)v15,
    v21,
    (bool)"Name %ls Sid %ls",
    a2,
    a4);
  if ( (v15 <= -2147024895 || (unsigned int)(v15 + 2147024892) <= 0x7FF8FFFB) && v7 >= 0 )
    v7 = v15;
  if ( ((a6 - 1) & 0xFFFFFFFD) != 0 )
  {
    if ( a3 )
    {
      if ( (unsigned __int8)IsNetworkIsolationDeleteAppContainerPresent() )
      {
        AppContainerRegistrationHelper::LogSuccess(
          &AppModelFirewallAppContainerDeletionStart,
          (const unsigned __int16 *)a2,
          0);
        v18 = (const char *)(unsigned int)NetworkIsolationDeleteAppContainer(a5, a3);
        wil::details::in1diag3::Log_IfWin32ErrorMsg(
          retaddr,
          (void *)0x873,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          v18,
          (unsigned int)"Name %ls display %ls",
          a2,
          a3);
        AppContainerRegistrationHelper::LogFailureWithContext(
          &AppModelFirewallAppContainerDeletionStop,
          (const unsigned __int16 *)a2,
          (int)v18,
          0);
        if ( ((unsigned int)v18 & 0xFFFFFFFD) != 0 && v7 >= 0 )
        {
          if ( (int)v18 > 0 )
            v7 = (unsigned __int16)v18 | 0x80070000;
          else
            v7 = (int)v18;
          AppContainerRegistrationHelper::LogFailure(&AppModelAppContainerUnregisterFirewallFailure, v7, a7);
        }
      }
    }
  }
  v19 = AppContainerUnregisterSid(a5);
  if ( (int)(v19 + 0x80000000) < 0 || v19 == -2147024894 )
    v16 = 0;
  LOBYTE(v22) = v16;
  wil::details::in1diag3::Log_HrIfMsg(
    retaddr,
    (void *)0x881,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
    (const char *)v19,
    v22,
    (bool)"Name %ls Sid %ls",
    a2,
    a4);
  if ( ((v19 + 0x80000000) & 0x80000000) == 0 && v19 != -2147024894 && v7 >= 0 )
  {
    v7 = v19;
    AppContainerRegistrationHelper::LogFailure(&AppModelAppContainerUnregisterSidFailure, v19, a7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800162d0  push    rbx
0x1800162d2  push    rbp
0x1800162d3  push    rsi
0x1800162d4  push    rdi
0x1800162d5  push    r12
0x1800162d7  push    r13
0x1800162d9  push    r14
0x1800162db  push    r15
0x1800162dd  sub     rsp, 48h
0x1800162e1  mov     rbp, [rsp+88h+arg_30]
0x1800162e9  lea     r13, aNameLsSidLs; "Name %ls Sid %ls"
0x1800162f0  xor     ebx, ebx
0x1800162f2  mov     r15, r9
0x1800162f5  mov     r12, r8
0x1800162f8  mov     rsi, rdx
0x1800162fb  mov     rdi, rcx
0x1800162fe  mov     r14d, 80000000h
0x180016304  test    rcx, rcx
0x180016307  jnz     short loc_180016357
0x180016309  mov     rcx, [rsp+88h+arg_20]; void *
0x180016311  mov     rdx, rbp; struct _GUID *
0x180016314  call    ?CleanupChildAppContainers@AppContainerRegistrationHelper@@CAJQEAXPEBU_GUID@@@Z; AppContainerRegistrationHelper::CleanupChildAppContainers(void * const,_GUID const *)
0x180016319  mov     rcx, [rsp+88h]; this
0x180016321  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180016328  mov     [rsp+88h+var_58], r15
0x18001632d  mov     r9d, eax; char *
0x180016330  mov     [rsp+88h+var_60], rsi; char *
0x180016335  mov     edx, 856h; void *
0x18001633a  mov     qword ptr [rsp+88h+var_68], r13; __int64
0x18001633f  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180016344  mov     ecx, eax
0x180016346  add     eax, r14d
0x180016349  test    r14d, eax
0x18001634c  jnz     short loc_180016357
0x18001634e  cmp     ecx, 80070002h
0x180016354  cmovnz  ebx, ecx
0x180016357  mov     r13d, [rsp+88h+arg_28]
0x18001635f  mov     r8, r15
0x180016362  mov     r9d, r13d
0x180016365  mov     qword ptr [rsp+88h+var_68], rbp
0x18001636a  mov     rdx, rsi
0x18001636d  mov     rcx, rdi
0x180016370  call    ?DeleteStorageLocations@AppContainerRegistrationHelper@@CAJPEAXPEBG1W4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::DeleteStorageLocations(void *,ushort const *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x180016375  mov     edi, eax
0x180016377  mov     r14b, 1
0x18001637a  test    eax, eax
0x18001637c  jns     short loc_180016391
0x18001637e  cmp     eax, 80070005h
0x180016383  jz      short loc_180016391
0x180016385  cmp     eax, 80070020h
0x18001638a  jz      short loc_180016391
0x18001638c  mov     al, r14b
0x18001638f  jmp     short loc_180016393
0x180016391  xor     eax, eax
0x180016393  mov     rcx, [rsp+88h]; this
0x18001639b  lea     rdx, aNameLsSidLs; "Name %ls Sid %ls"
0x1800163a2  mov     [rsp+88h+var_50], r15
0x1800163a7  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800163ae  mov     [rsp+88h+var_58], rsi; char *
0x1800163b3  mov     r9d, edi; char *
0x1800163b6  mov     [rsp+88h+var_60], rdx; bool
0x1800163bb  mov     edx, 863h; void *
0x1800163c0  mov     byte ptr [rsp+88h+var_68], al; int
0x1800163c4  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800163c9  cmp     edi, 80070001h
0x1800163cf  jle     short loc_1800163DE
0x1800163d1  lea     eax, [rdi+7FF8FFFCh]
0x1800163d7  cmp     eax, 7FF8FFFBh
0x1800163dc  ja      short loc_1800163E3
0x1800163de  test    ebx, ebx
0x1800163e0  cmovns  ebx, edi
0x1800163e3  lea     eax, [r13-1]
0x1800163e7  mov     r13d, 0FFFFFFFDh
0x1800163ed  test    r13d, eax
0x1800163f0  jz      loc_1800164A9
0x1800163f6  test    r12, r12
0x1800163f9  jz      loc_1800164A9
0x1800163ff  call    IsNetworkIsolationDeleteAppContainerPresent
0x180016404  test    al, al
0x180016406  jz      loc_1800164A9
0x18001640c  xor     r8d, r8d; struct _GUID *
0x18001640f  lea     rcx, AppModelFirewallAppContainerDeletionStart; struct _EVENT_DESCRIPTOR *
0x180016416  mov     rdx, rsi; unsigned __int16 *
0x180016419  call    ?LogSuccess@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogSuccess(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x18001641e  mov     rcx, [rsp+88h+arg_20]
0x180016426  mov     rdx, r12
0x180016429  call    cs:__imp_NetworkIsolationDeleteAppContainer
0x180016430  nop     dword ptr [rax+rax+00h]
0x180016435  mov     rcx, [rsp+88h]; this
0x18001643d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180016444  mov     edi, eax
0x180016446  mov     [rsp+88h+var_58], r12
0x18001644b  lea     rax, aNameLsDisplayL_0; "Name %ls display %ls"
0x180016452  mov     [rsp+88h+var_60], rsi; char *
0x180016457  mov     r9d, edi; char *
0x18001645a  mov     qword ptr [rsp+88h+var_68], rax; unsigned int
0x18001645f  mov     edx, 873h; void *
0x180016464  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180016469  xor     r9d, r9d; struct _GUID *
0x18001646c  lea     rcx, AppModelFirewallAppContainerDeletionStop; struct _EVENT_DESCRIPTOR *
0x180016473  mov     r8d, edi; int
0x180016476  mov     rdx, rsi; unsigned __int16 *
0x180016479  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x18001647e  test    r13d, edi
0x180016481  jz      short loc_1800164A9
0x180016483  test    ebx, ebx
0x180016485  js      short loc_1800164A9
0x180016487  test    edi, edi
0x180016489  jg      short loc_18001648F
0x18001648b  mov     ebx, edi
0x18001648d  jmp     short loc_180016498
0x18001648f  movzx   ebx, di
0x180016492  or      ebx, 80070000h
0x180016498  mov     r8, rbp; struct _GUID *
0x18001649b  lea     rcx, AppModelAppContainerUnregisterFirewallFailure; struct _EVENT_DESCRIPTOR *
0x1800164a2  mov     edx, ebx; int
0x1800164a4  call    ?LogFailure@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@JPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailure(_EVENT_DESCRIPTOR const *,long,_GUID const *)
0x1800164a9  mov     rcx, [rsp+88h+arg_20]
0x1800164b1  call    cs:__imp_AppContainerUnregisterSid
0x1800164b8  nop     dword ptr [rax+rax+00h]
0x1800164bd  mov     r12d, 80000000h
0x1800164c3  mov     edi, eax
0x1800164c5  add     eax, r12d
0x1800164c8  test    r12d, eax
0x1800164cb  jnz     short loc_1800164D5
0x1800164cd  cmp     edi, 80070002h
0x1800164d3  jnz     short loc_1800164D8
0x1800164d5  xor     r14d, r14d
0x1800164d8  mov     rcx, [rsp+88h]; this
0x1800164e0  lea     rax, aNameLsSidLs; "Name %ls Sid %ls"
0x1800164e7  mov     [rsp+88h+var_50], r15
0x1800164ec  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800164f3  mov     [rsp+88h+var_58], rsi; char *
0x1800164f8  mov     r9d, edi; char *
0x1800164fb  mov     [rsp+88h+var_60], rax; bool
0x180016500  mov     edx, 881h; void *
0x180016505  mov     byte ptr [rsp+88h+var_68], r14b; int
0x18001650a  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001650f  lea     eax, [rdi+r12]
0x180016513  test    r12d, eax
0x180016516  jnz     short loc_180016537
0x180016518  cmp     edi, 80070002h
0x18001651e  jz      short loc_180016537
0x180016520  test    ebx, ebx
0x180016522  js      short loc_180016537
0x180016524  mov     r8, rbp; struct _GUID *
0x180016527  lea     rcx, AppModelAppContainerUnregisterSidFailure; struct _EVENT_DESCRIPTOR *
0x18001652e  mov     edx, edi; int
0x180016530  mov     ebx, edi
0x180016532  call    ?LogFailure@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@JPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailure(_EVENT_DESCRIPTOR const *,long,_GUID const *)
0x180016537  mov     eax, ebx
0x180016539  add     rsp, 48h
0x18001653d  pop     r15
0x18001653f  pop     r14
0x180016541  pop     r13
0x180016543  pop     r12
0x180016545  pop     rdi
0x180016546  pop     rsi
0x180016547  pop     rbp
0x180016548  pop     rbx
0x180016549  retn
```
