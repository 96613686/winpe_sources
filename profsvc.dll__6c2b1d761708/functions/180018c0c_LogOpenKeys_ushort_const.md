# LogOpenKeys(ushort const *)

- ea: `0x180018c0c`
- end: `0x180018d94`
- name: `?LogOpenKeys@@YAJPEBG@Z`
- size: `392`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f330`

## callees

- `0x1800084bc`
- `0x18000b060`
- `0x180017fdc`
- `0x180018c0c`
- `0x180030ad0`
- `0x18003651c`
- `0x18004bb10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180018cb1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180018cb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018c93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018c93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018d05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018d05`

## string_xrefs

- `0x180018ce3`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x180018d3a`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`

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
0x180018c0c  mov     [rsp-18h+arg_0], rcx
0x180018c11  push    rbp
0x180018c12  push    rbx
0x180018c13  push    rdi
0x180018c14  mov     rbp, rsp
0x180018c17  sub     rsp, 70h
0x180018c1b  xor     edi, edi
0x180018c1d  xorps   xmm0, xmm0
0x180018c20  movups  [rbp+var_48], xmm0
0x180018c24  test    rcx, rcx
0x180018c27  jz      short loc_180018C60
0x180018c29  mov     edx, 7FFFh
0x180018c2e  lea     r8d, [rdi+2]
0x180018c32  mov     rax, rcx
0x180018c35  cmp     [rax], di
0x180018c38  jz      short loc_180018C45
0x180018c3a  add     rax, r8
0x180018c3d  sub     rdx, 1
0x180018c41  jnz     short loc_180018C35
0x180018c43  jmp     short loc_180018C60
0x180018c45  add     dx, dx
0x180018c48  mov     qword ptr [rbp+var_48+8], rcx
0x180018c4c  mov     eax, 0FFFEh
0x180018c51  sub     ax, dx
0x180018c54  mov     word ptr [rbp+var_48], ax
0x180018c58  add     ax, r8w
0x180018c5c  mov     word ptr [rbp+var_48+2], ax
0x180018c60  lea     rax, [rbp+var_48]
0x180018c64  mov     [rbp+var_38], 30h ; '0'
0x180018c6c  xorps   xmm0, xmm0
0x180018c6f  mov     [rbp+var_28], rax
0x180018c73  movdqu  [rbp+var_18], xmm0
0x180018c78  mov     [rbp+var_20], 40h ; '@'
0x180018c80  mov     [rbp+var_30], rdi
0x180018c84  mov     [rbp+arg_10], 12h
0x180018c8b  mov     [rbp+arg_14], di
0x180018c8f  mov     [rbp+TokenHandle], rdi
0x180018c93  call    cs:__imp_GetCurrentThread
0x180018c9a  nop     dword ptr [rax+rax+00h]
0x180018c9f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180018ca3  mov     edx, 20008h; DesiredAccess
0x180018ca8  mov     rcx, rax; ThreadHandle
0x180018cab  mov     r8d, 1; OpenAsSelf
0x180018cb1  call    cs:__imp_OpenThreadToken
0x180018cb8  nop     dword ptr [rax+rax+00h]
0x180018cbd  test    eax, eax
0x180018cbf  jz      short loc_180018CD0
0x180018cc1  mov     rax, [rbp+TokenHandle]
0x180018cc5  inc     rax
0x180018cc8  test    rax, 0FFFFFFFFFFFFFFFEh
0x180018cce  jnz     short loc_180018D13
0x180018cd0  lea     rcx, [rbp+arg_10]; this
0x180018cd4  call    ?AdjustPrivilegeIfNecessary@PrivilegeAdjuster@@QEAAJXZ; PrivilegeAdjuster::AdjustPrivilegeIfNecessary(void)
0x180018cd9  mov     ebx, eax
0x180018cdb  test    eax, eax
0x180018cdd  jns     short loc_180018D13
0x180018cdf  mov     rcx, [rbp+18h]; this
0x180018ce3  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180018cea  mov     r9d, eax; char *
0x180018ced  mov     edx, 76h ; 'v'; void *
0x180018cf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018cf7  mov     rcx, [rbp+TokenHandle]; hObject
0x180018cfb  lea     rdx, [rcx-1]
0x180018cff  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180018d03  ja      short loc_180018D80
0x180018d05  call    cs:__imp_CloseHandle
0x180018d0c  nop     dword ptr [rax+rax+00h]
0x180018d11  jmp     short loc_180018D80
0x180018d13  lea     rax, [rbp+arg_0]
0x180018d17  mov     [rbp+arg_18], rdi
0x180018d1b  lea     r8, [rbp+var_50]
0x180018d1f  mov     [rbp+var_50], rax
0x180018d23  lea     rdx, [rbp+var_38]
0x180018d27  lea     rcx, [rbp+arg_18]
0x180018d2b  call    OpenSubkeys__ForEachOpenSubkey__lambda_d1fb842c68b30bddff88d45ace1651b0____
0x180018d30  mov     ebx, eax
0x180018d32  test    eax, eax
0x180018d34  jns     short loc_180018D67
0x180018d36  mov     rcx, [rbp+18h]; this
0x180018d3a  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180018d41  mov     r9d, eax; char *
0x180018d44  mov     edx, 81h; void *
0x180018d49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018d4e  mov     rcx, [rbp+arg_18]
0x180018d52  test    rcx, rcx
0x180018d55  jz      short loc_180018D5C
0x180018d57  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180018d5c  lea     rcx, [rbp+TokenHandle]
0x180018d60  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180018d65  jmp     short loc_180018D80
0x180018d67  mov     rcx, [rbp+arg_18]
0x180018d6b  test    rcx, rcx
0x180018d6e  jz      short loc_180018D75
0x180018d70  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180018d75  lea     rcx, [rbp+TokenHandle]
0x180018d79  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180018d7e  mov     ebx, edi
0x180018d80  lea     rcx, [rbp+arg_10]; this
0x180018d84  call    ??1PrivilegeAdjuster@@QEAA@XZ; PrivilegeAdjuster::~PrivilegeAdjuster(void)
0x180018d89  mov     eax, ebx
0x180018d8b  add     rsp, 70h
0x180018d8f  pop     rdi
0x180018d90  pop     rbx
0x180018d91  pop     rbp
0x180018d92  retn
```
