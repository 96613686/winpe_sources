# LogOpenKeys(ushort const *)

- ea: `0x1800152dc`
- end: `0x180015451`
- name: `?LogOpenKeys@@YAJPEBG@Z`
- size: `373`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800140c0`

## callees

- `0x1800053a0`
- `0x18000a9b8`
- `0x1800152dc`
- `0x180015458`
- `0x18002d2d8`
- `0x180035f88`
- `0x180049634`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001537b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001537b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015363`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015363`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800153c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800153c9`

## string_xrefs

- `0x1800153a7`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x1800153f8`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`

## pseudocode

```c
__int64 __fastcall LogOpenKeys(const unsigned __int16 *a1)
{
  __int64 v1; // rdx
  const unsigned __int16 *v2; // rax
  HANDLE CurrentThread; // rax
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  const unsigned __int16 **v8; // [rsp+20h] [rbp-50h] BYREF
  __int128 v9; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v10[4]; // [rsp+38h] [rbp-38h] BYREF
  __int128 v11; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  const unsigned __int16 *v13; // [rsp+90h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+98h] [rbp+28h] BYREF
  int v15; // [rsp+A0h] [rbp+30h] BYREF
  __int16 v16; // [rsp+A4h] [rbp+34h]
  __int64 v17; // [rsp+A8h] [rbp+38h] BYREF

  v13 = a1;
  v9 = 0;
  if ( a1 )
  {
    v1 = 0x7FFF;
    v2 = a1;
    while ( *v2 )
    {
      ++v2;
      if ( !--v1 )
        goto LABEL_7;
    }
    *((_QWORD *)&v9 + 1) = a1;
    LOWORD(v9) = -2 - 2 * v1;
    WORD1(v9) = -2 * v1;
  }
LABEL_7:
  v10[0] = 48;
  v10[2] = &v9;
  v11 = 0;
  v10[3] = 64;
  v10[1] = 0;
  v15 = 18;
  v16 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle)
    && (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
    || (v4 = PrivilegeAdjuster::AdjustPrivilegeIfNecessary((PrivilegeAdjuster *)&v15), v5 = v4, v4 >= 0) )
  {
    v17 = 0;
    v8 = &v13;
    v6 = OpenSubkeys::ForEachOpenSubkey__lambda_d1fb842c68b30bddff88d45ace1651b0____(&v17, v10, &v8);
    v5 = v6;
    if ( v6 >= 0 )
    {
      if ( v17 )
        Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v17);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      v5 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
        (const char *)(unsigned int)v6,
        (int)v8);
      if ( v17 )
        Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v17);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
      (const char *)(unsigned int)v4,
      (int)v8);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
  }
  PrivilegeAdjuster::~PrivilegeAdjuster((PrivilegeAdjuster *)&v15);
  return v5;
}

```

## disassembly

```asm
0x1800152dc  mov     [rsp-18h+arg_0], rcx
0x1800152e1  push    rbp
0x1800152e2  push    rbx
0x1800152e3  push    rdi
0x1800152e4  mov     rbp, rsp
0x1800152e7  sub     rsp, 70h
0x1800152eb  xor     edi, edi
0x1800152ed  xorps   xmm0, xmm0
0x1800152f0  movups  [rbp+var_48], xmm0
0x1800152f4  test    rcx, rcx
0x1800152f7  jz      short loc_180015330
0x1800152f9  mov     edx, 7FFFh
0x1800152fe  lea     r8d, [rdi+2]
0x180015302  mov     rax, rcx
0x180015305  cmp     [rax], di
0x180015308  jz      short loc_180015315
0x18001530a  add     rax, r8
0x18001530d  sub     rdx, 1
0x180015311  jnz     short loc_180015305
0x180015313  jmp     short loc_180015330
0x180015315  add     dx, dx
0x180015318  mov     qword ptr [rbp+var_48+8], rcx
0x18001531c  mov     eax, 0FFFEh
0x180015321  sub     ax, dx
0x180015324  mov     word ptr [rbp+var_48], ax
0x180015328  add     ax, r8w
0x18001532c  mov     word ptr [rbp+var_48+2], ax
0x180015330  lea     rax, [rbp+var_48]
0x180015334  mov     [rbp+var_38], 30h ; '0'
0x18001533c  xorps   xmm0, xmm0
0x18001533f  mov     [rbp+var_28], rax
0x180015343  movdqu  [rbp+var_18], xmm0
0x180015348  mov     [rbp+var_20], 40h ; '@'
0x180015350  mov     [rbp+var_30], rdi
0x180015354  mov     [rbp+arg_10], 12h
0x18001535b  mov     [rbp+arg_14], di
0x18001535f  mov     [rbp+TokenHandle], rdi
0x180015363  call    cs:__imp_GetCurrentThread
0x180015369  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001536d  mov     edx, 20008h; DesiredAccess
0x180015372  mov     rcx, rax; ThreadHandle
0x180015375  mov     r8d, 1; OpenAsSelf
0x18001537b  call    cs:__imp_OpenThreadToken
0x180015381  test    eax, eax
0x180015383  jz      short loc_180015394
0x180015385  mov     rax, [rbp+TokenHandle]
0x180015389  inc     rax
0x18001538c  test    rax, 0FFFFFFFFFFFFFFFEh
0x180015392  jnz     short loc_1800153D1
0x180015394  lea     rcx, [rbp+arg_10]; this
0x180015398  call    ?AdjustPrivilegeIfNecessary@PrivilegeAdjuster@@QEAAJXZ; PrivilegeAdjuster::AdjustPrivilegeIfNecessary(void)
0x18001539d  mov     ebx, eax
0x18001539f  test    eax, eax
0x1800153a1  jns     short loc_1800153D1
0x1800153a3  mov     rcx, [rbp+18h]; this
0x1800153a7  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800153ae  mov     r9d, eax; char *
0x1800153b1  mov     edx, 76h ; 'v'; void *
0x1800153b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800153bb  mov     rcx, [rbp+TokenHandle]; hObject
0x1800153bf  lea     rdx, [rcx-1]
0x1800153c3  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800153c7  ja      short loc_18001543E
0x1800153c9  call    cs:__imp_CloseHandle
0x1800153cf  jmp     short loc_18001543E
0x1800153d1  lea     rax, [rbp+arg_0]
0x1800153d5  mov     [rbp+arg_18], rdi
0x1800153d9  lea     r8, [rbp+var_50]
0x1800153dd  mov     [rbp+var_50], rax
0x1800153e1  lea     rdx, [rbp+var_38]
0x1800153e5  lea     rcx, [rbp+arg_18]
0x1800153e9  call    OpenSubkeys__ForEachOpenSubkey__lambda_d1fb842c68b30bddff88d45ace1651b0____
0x1800153ee  mov     ebx, eax
0x1800153f0  test    eax, eax
0x1800153f2  jns     short loc_180015425
0x1800153f4  mov     rcx, [rbp+18h]; this
0x1800153f8  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800153ff  mov     r9d, eax; char *
0x180015402  mov     edx, 81h; void *
0x180015407  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001540c  mov     rcx, [rbp+arg_18]
0x180015410  test    rcx, rcx
0x180015413  jz      short loc_18001541A
0x180015415  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18001541a  lea     rcx, [rbp+TokenHandle]
0x18001541e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180015423  jmp     short loc_18001543E
0x180015425  mov     rcx, [rbp+arg_18]
0x180015429  test    rcx, rcx
0x18001542c  jz      short loc_180015433
0x18001542e  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180015433  lea     rcx, [rbp+TokenHandle]
0x180015437  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001543c  mov     ebx, edi
0x18001543e  lea     rcx, [rbp+arg_10]; this
0x180015442  call    ??1PrivilegeAdjuster@@QEAA@XZ; PrivilegeAdjuster::~PrivilegeAdjuster(void)
0x180015447  mov     eax, ebx
0x180015449  add     rsp, 70h
0x18001544d  pop     rdi
0x18001544e  pop     rbx
0x18001544f  pop     rbp
0x180015450  retn
```
