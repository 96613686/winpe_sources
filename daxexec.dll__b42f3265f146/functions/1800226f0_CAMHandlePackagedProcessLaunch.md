# CAMHandlePackagedProcessLaunch

- ea: `0x1800226f0`
- end: `0x1800228d8`
- name: `CAMHandlePackagedProcessLaunch`
- size: `488`
- prototype: `__int64 __fastcall(DWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800234e0`

## callees

- `0x18000ff04`
- `0x180017aa4`
- `0x180018804`
- `0x18001ee90`
- `0x1800210fc`
- `0x1800226f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022741`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022741`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022778`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002278d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022815`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002282a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002285c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022871`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022890`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800228a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022778`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002278d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022815`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002282a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002285c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022871`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022890`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800228a5`
- `ntdll!RtlQueryPackageClaims` at `0x1800227db`
- `ntdll!RtlQueryPackageClaims` at `0x1800227db`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022706`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022706`

## string_xrefs

- `0x180022756`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x1800227f3`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x1800228c5`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
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
  int v14[2]; // [rsp+20h] [rbp-28h]
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
        (void *)0x3B8,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        v3);
    }
    catch ( ... )
    {
      v12 = &v13;
      *((_DWORD *)v12 + 22) = wil::details::in1diag3::Return_CaughtException(
                                (wil::details::in1diag3 *)v12[9],
                                (void *)0x3D1,
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
    *(_QWORD *)v14 = 0;
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
             (void *)0x3C9,
             (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
             (const char *)(unsigned int)PackageClaims,
             v14[0]);
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
                  (void *)0x3BE,
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
0x1800226f0  mov     [rsp+arg_0], rbx
0x1800226f5  push    rdi
0x1800226f6  sub     rsp, 40h
0x1800226fa  mov     edi, ecx
0x1800226fc  mov     r8d, ecx; dwProcessId
0x1800226ff  xor     edx, edx; bInheritHandle
0x180022701  mov     ecx, 1000h; dwDesiredAccess
0x180022706  call    cs:__imp_OpenProcess
0x18002270d  nop     dword ptr [rax+rax+00h]
0x180022712  mov     rbx, rax
0x180022715  mov     rcx, [rsp+48h]; this
0x18002271a  test    rax, rax
0x18002271d  jz      loc_1800228C5
0x180022723  mov     [rsp+48h+hObject], 0
0x18002272c  lea     rcx, [rsp+48h+hObject]
0x180022731  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x180022736  mov     r8, rax; TokenHandle
0x180022739  mov     edx, 8; DesiredAccess
0x18002273e  mov     rcx, rbx; ProcessHandle
0x180022741  call    cs:__imp_OpenProcessToken
0x180022748  nop     dword ptr [rax+rax+00h]
0x18002274d  test    eax, eax
0x18002274f  jnz     short loc_1800227A0
0x180022751  mov     rcx, [rsp+48h]; this
0x180022756  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002275d  mov     edx, 3BEh; void *
0x180022762  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180022767  mov     edi, eax
0x180022769  mov     rcx, [rsp+48h+hObject]; hObject
0x18002276e  lea     rdx, [rcx-1]
0x180022772  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180022776  ja      short loc_180022784
0x180022778  call    cs:__imp_CloseHandle
0x18002277f  nop     dword ptr [rax+rax+00h]
0x180022784  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180022788  jz      short loc_180022799
0x18002278a  mov     rcx, rbx; hObject
0x18002278d  call    cs:__imp_CloseHandle
0x180022794  nop     dword ptr [rax+rax+00h]
0x180022799  mov     eax, edi
0x18002279b  jmp     loc_1800228B9
0x1800227a0  mov     [rsp+48h+arg_10], 0
0x1800227a9  mov     [rsp+48h+var_10], 0
0x1800227b2  lea     rax, [rsp+48h+arg_10]
0x1800227b7  mov     [rsp+48h+var_18], rax
0x1800227bc  mov     [rsp+48h+var_20], 0
0x1800227c5  mov     qword ptr [rsp+48h+var_28], 0; int
0x1800227ce  xor     r9d, r9d
0x1800227d1  xor     r8d, r8d
0x1800227d4  xor     edx, edx
0x1800227d6  mov     rcx, [rsp+48h+hObject]
0x1800227db  call    cs:__imp_RtlQueryPackageClaims
0x1800227e2  nop     dword ptr [rax+rax+00h]
0x1800227e7  test    eax, eax
0x1800227e9  jns     short loc_18002283A
0x1800227eb  mov     rcx, [rsp+48h]; this
0x1800227f0  mov     r9d, eax; char *
0x1800227f3  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800227fa  mov     edx, 3C9h; void *
0x1800227ff  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180022804  mov     edi, eax
0x180022806  mov     rcx, [rsp+48h+hObject]; hObject
0x18002280b  lea     rdx, [rcx-1]
0x18002280f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180022813  ja      short loc_180022821
0x180022815  call    cs:__imp_CloseHandle
0x18002281c  nop     dword ptr [rax+rax+00h]
0x180022821  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180022825  jz      short loc_180022836
0x180022827  mov     rcx, rbx; hObject
0x18002282a  call    cs:__imp_CloseHandle
0x180022831  nop     dword ptr [rax+rax+00h]
0x180022836  mov     eax, edi
0x180022838  jmp     short loc_1800228B9
0x18002283a  test    dword ptr [rsp+48h+arg_10], 1000h
0x180022842  jz      short loc_180022881
0x180022844  mov     ecx, edi; unsigned int
0x180022846  call    ?CallCamPackagedProcessCreatedHandler@@YAJK@Z; CallCamPackagedProcessCreatedHandler(ulong)
0x18002284b  mov     edi, eax
0x18002284d  mov     rcx, [rsp+48h+hObject]; hObject
0x180022852  lea     rdx, [rcx-1]
0x180022856  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002285a  ja      short loc_180022868
0x18002285c  call    cs:__imp_CloseHandle
0x180022863  nop     dword ptr [rax+rax+00h]
0x180022868  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002286c  jz      short loc_18002287D
0x18002286e  mov     rcx, rbx; hObject
0x180022871  call    cs:__imp_CloseHandle
0x180022878  nop     dword ptr [rax+rax+00h]
0x18002287d  mov     eax, edi
0x18002287f  jmp     short loc_1800228B9
0x180022881  mov     rcx, [rsp+48h+hObject]; hObject
0x180022886  lea     rax, [rcx-1]
0x18002288a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002288e  ja      short loc_18002289C
0x180022890  call    cs:__imp_CloseHandle
0x180022897  nop     dword ptr [rax+rax+00h]
0x18002289c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800228a0  jz      short loc_1800228B1
0x1800228a2  mov     rcx, rbx; hObject
0x1800228a5  call    cs:__imp_CloseHandle
0x1800228ac  nop     dword ptr [rax+rax+00h]
0x1800228b1  xor     eax, eax
0x1800228b3  jmp     short loc_1800228B9
0x1800228b5  mov     eax, dword ptr [rsp+48h+hObject]
0x1800228b9  mov     rbx, [rsp+48h+arg_0]
0x1800228be  add     rsp, 40h
0x1800228c2  pop     rdi
0x1800228c3  retn
0x1800228c5  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800228cc  mov     edx, 3B8h; void *
0x1800228d1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
