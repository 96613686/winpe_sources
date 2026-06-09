# CAMHandlePackagedProcessLaunch

- ea: `0x180021ed0`
- end: `0x1800220a9`
- name: `CAMHandlePackagedProcessLaunch`
- size: `473`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180022b30`

## callees

- `0x18000e214`
- `0x180015ec8`
- `0x180016bcc`
- `0x18001e304`
- `0x18002031c`
- `0x180021ed0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180021f1e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180021f1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021f55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021f6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021fe6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021ffb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002202d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022042`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022061`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022076`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021f55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021f6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021fe6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021ffb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002202d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022042`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022061`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022076`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180021ee6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180021ee6`
- `ntdll!RtlQueryPackageClaims` at `0x180021fac`
- `ntdll!RtlQueryPackageClaims` at `0x180021fac`

## string_xrefs

- `0x180021f33`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180021fc4`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180022096`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`

## pseudocode

```c
__int64 __fastcall CAMHandlePackagedProcessLaunch(DWORD a1)
{
  HANDLE v2; // rbx
  const char *v3; // r9
  void **v4; // rax
  const char *v5; // r9
  unsigned int LastError; // edi
  int PackageClaims; // eax
  unsigned int v9; // edi
  unsigned int v10; // edi
  const char *v11; // r9
  __int64 *v12; // rdx
  __int64 v13; // [rsp+0h] [rbp-48h] BYREF
  __int64 v14; // [rsp+20h] [rbp-28h]
  __int64 v15; // [rsp+28h] [rbp-20h]
  __int64 *v16; // [rsp+30h] [rbp-18h]
  __int64 v17; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HANDLE hObject; // [rsp+58h] [rbp+10h] BYREF
  __int64 v20; // [rsp+60h] [rbp+18h] BYREF

  v2 = OpenProcess(0x1000u, 0, a1);
  if ( !v2 )
  {
    try
    {
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3B6,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        v3);
    }
    catch ( ... )
    {
      v12 = &v13;
      *((_DWORD *)v12 + 22) = wil::details::in1diag3::Return_CaughtException(
                                (wil::details::in1diag3 *)v12[9],
                                (void *)0x3CF,
                                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
                                v11);
      return (unsigned int)hObject;
    }
  }
  hObject = 0;
  v4 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
  if ( OpenProcessToken(v2, 8u, v4) )
  {
    v20 = 0;
    v17 = 0;
    v16 = &v20;
    v15 = 0;
    v14 = 0;
    PackageClaims = RtlQueryPackageClaims(hObject, 0, 0, 0);
    if ( PackageClaims >= 0 )
    {
      if ( (v20 & 0x1000) != 0 )
      {
        v10 = CallCamPackagedProcessCreatedHandler(a1);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        if ( v2 != (HANDLE)-1LL )
          CloseHandle(v2);
        return v10;
      }
      else
      {
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        if ( v2 != (HANDLE)-1LL )
          CloseHandle(v2);
        return 0;
      }
    }
    else
    {
      v9 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x3C7,
             (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
             (const char *)(unsigned int)PackageClaims,
             v14);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( v2 != (HANDLE)-1LL )
        CloseHandle(v2);
      return v9;
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x3BC,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
                  v5);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( v2 != (HANDLE)-1LL )
      CloseHandle(v2);
    return LastError;
  }
}

```

## disassembly

```asm
0x180021ed0  mov     [rsp+arg_0], rbx
0x180021ed5  push    rdi
0x180021ed6  sub     rsp, 40h
0x180021eda  mov     edi, ecx
0x180021edc  mov     r8d, ecx; dwProcessId
0x180021edf  xor     edx, edx; bInheritHandle
0x180021ee1  mov     ecx, 1000h; dwDesiredAccess
0x180021ee6  call    cs:__imp_OpenProcess
0x180021eed  nop     dword ptr [rax+rax+00h]
0x180021ef2  mov     rbx, rax
0x180021ef5  mov     rcx, [rsp+48h]; this
0x180021efa  test    rax, rax
0x180021efd  jz      loc_180022096
0x180021f03  and     [rsp+48h+hObject], 0
0x180021f09  lea     rcx, [rsp+48h+hObject]
0x180021f0e  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x180021f13  mov     r8, rax; TokenHandle
0x180021f16  mov     edx, 8; DesiredAccess
0x180021f1b  mov     rcx, rbx; ProcessHandle
0x180021f1e  call    cs:__imp_OpenProcessToken
0x180021f25  nop     dword ptr [rax+rax+00h]
0x180021f2a  test    eax, eax
0x180021f2c  jnz     short loc_180021F7D
0x180021f2e  mov     rcx, [rsp+48h]; this
0x180021f33  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180021f3a  mov     edx, 3BCh; void *
0x180021f3f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021f44  mov     edi, eax
0x180021f46  mov     rcx, [rsp+48h+hObject]; hObject
0x180021f4b  lea     rdx, [rcx-1]
0x180021f4f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180021f53  ja      short loc_180021F61
0x180021f55  call    cs:__imp_CloseHandle
0x180021f5c  nop     dword ptr [rax+rax+00h]
0x180021f61  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180021f65  jz      short loc_180021F76
0x180021f67  mov     rcx, rbx; hObject
0x180021f6a  call    cs:__imp_CloseHandle
0x180021f71  nop     dword ptr [rax+rax+00h]
0x180021f76  mov     eax, edi
0x180021f78  jmp     loc_18002208A
0x180021f7d  and     [rsp+48h+arg_10], 0
0x180021f83  and     [rsp+48h+var_10], 0
0x180021f89  lea     rax, [rsp+48h+arg_10]
0x180021f8e  mov     [rsp+48h+var_18], rax
0x180021f93  and     [rsp+48h+var_20], 0
0x180021f99  and     [rsp+48h+var_28], 0
0x180021f9f  xor     r9d, r9d
0x180021fa2  xor     r8d, r8d
0x180021fa5  xor     edx, edx
0x180021fa7  mov     rcx, [rsp+48h+hObject]
0x180021fac  call    cs:__imp_RtlQueryPackageClaims
0x180021fb3  nop     dword ptr [rax+rax+00h]
0x180021fb8  test    eax, eax
0x180021fba  jns     short loc_18002200B
0x180021fbc  mov     rcx, [rsp+48h]; this
0x180021fc1  mov     r9d, eax; char *
0x180021fc4  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180021fcb  mov     edx, 3C7h; void *
0x180021fd0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180021fd5  mov     edi, eax
0x180021fd7  mov     rcx, [rsp+48h+hObject]; hObject
0x180021fdc  lea     rdx, [rcx-1]
0x180021fe0  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180021fe4  ja      short loc_180021FF2
0x180021fe6  call    cs:__imp_CloseHandle
0x180021fed  nop     dword ptr [rax+rax+00h]
0x180021ff2  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180021ff6  jz      short loc_180022007
0x180021ff8  mov     rcx, rbx; hObject
0x180021ffb  call    cs:__imp_CloseHandle
0x180022002  nop     dword ptr [rax+rax+00h]
0x180022007  mov     eax, edi
0x180022009  jmp     short loc_18002208A
0x18002200b  test    dword ptr [rsp+48h+arg_10], 1000h
0x180022013  jz      short loc_180022052
0x180022015  mov     ecx, edi; unsigned int
0x180022017  call    ?CallCamPackagedProcessCreatedHandler@@YAJK@Z; CallCamPackagedProcessCreatedHandler(ulong)
0x18002201c  mov     edi, eax
0x18002201e  mov     rcx, [rsp+48h+hObject]; hObject
0x180022023  lea     rdx, [rcx-1]
0x180022027  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002202b  ja      short loc_180022039
0x18002202d  call    cs:__imp_CloseHandle
0x180022034  nop     dword ptr [rax+rax+00h]
0x180022039  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002203d  jz      short loc_18002204E
0x18002203f  mov     rcx, rbx; hObject
0x180022042  call    cs:__imp_CloseHandle
0x180022049  nop     dword ptr [rax+rax+00h]
0x18002204e  mov     eax, edi
0x180022050  jmp     short loc_18002208A
0x180022052  mov     rcx, [rsp+48h+hObject]; hObject
0x180022057  lea     rax, [rcx-1]
0x18002205b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002205f  ja      short loc_18002206D
0x180022061  call    cs:__imp_CloseHandle
0x180022068  nop     dword ptr [rax+rax+00h]
0x18002206d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180022071  jz      short loc_180022082
0x180022073  mov     rcx, rbx; hObject
0x180022076  call    cs:__imp_CloseHandle
0x18002207d  nop     dword ptr [rax+rax+00h]
0x180022082  xor     eax, eax
0x180022084  jmp     short loc_18002208A
0x180022086  mov     eax, dword ptr [rsp+48h+hObject]
0x18002208a  mov     rbx, [rsp+48h+arg_0]
0x18002208f  add     rsp, 40h
0x180022093  pop     rdi
0x180022094  retn
0x180022096  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002209d  mov     edx, 3B6h; void *
0x1800220a2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
