# GetBackgroundTaskPackageIdentity(ushort const *,ulong)

- ea: `0x180019ec8`
- end: `0x180019fa2`
- name: `?GetBackgroundTaskPackageIdentity@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGK@Z`
- size: `218`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180019d70`
- `0x180066610`

## callees

- `0x18000c9c4`
- `0x180019ec8`
- `0x180019fa8`
- `0x18001a100`
- `0x18001a18c`
- `0x180023c00`
- `0x18002661c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180019f21`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180019f21`

## string_xrefs

- `0x180019f07`: `backgroundTaskHost.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall GetBackgroundTaskPackageIdentity(_QWORD *a1, __int64 a2, DWORD a3)
{
  __int64 v5; // r9
  HANDLE v6; // rbx
  const char *v7; // r9
  unsigned __int16 **v8; // r8
  int PackageFamilyNameFromProcess; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HANDLE v12; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(a2 + 2 * v5) );
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(L"backgroundTaskHost.exe", 22, a2) )
  {
    v6 = OpenProcess(0x1000u, 0, a3);
    v12 = v6;
    if ( (((unsigned __int64)v6 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x13C,
        (unsigned int)"shell\\onecore\\desktopshellext\\lib\\rolloutcoordinatordata.cpp",
        v7);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a1,
      0);
    PackageFamilyNameFromProcess = CallerIdentity::GetPackageFamilyNameFromProcess(v6, a1, v8);
    if ( PackageFamilyNameFromProcess < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13E,
        (unsigned int)"shell\\onecore\\desktopshellext\\lib\\rolloutcoordinatordata.cpp",
        (const char *)(unsigned int)PackageFamilyNameFromProcess,
        1);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v12);
  }
  return a1;
}

```

## disassembly

```asm
0x180019ec8  mov     rax, rsp
0x180019ecb  mov     [rax+18h], rbx
0x180019ecf  mov     [rax+20h], rsi
0x180019ed3  mov     [rax+8], rcx
0x180019ed7  push    rdi
0x180019ed8  sub     rsp, 30h
0x180019edc  mov     ebx, r8d
0x180019edf  mov     rdi, rcx
0x180019ee2  xor     esi, esi
0x180019ee4  mov     [rax-18h], esi
0x180019ee7  mov     [rcx], rsi
0x180019eea  mov     dword ptr [rax-18h], 1
0x180019ef1  or      r9, 0FFFFFFFFFFFFFFFFh
0x180019ef5  inc     r9
0x180019ef8  cmp     [rdx+r9*2], si
0x180019efd  jnz     short loc_180019EF5
0x180019eff  mov     r8, rdx
0x180019f02  mov     edx, 16h
0x180019f07  lea     rcx, aBackgroundtask; "backgroundTaskHost.exe"
0x180019f0e  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180019f13  test    al, al
0x180019f15  jz      short loc_180019F8E
0x180019f17  mov     r8d, ebx; dwProcessId
0x180019f1a  xor     edx, edx; bInheritHandle
0x180019f1c  mov     ecx, 1000h; dwDesiredAccess
0x180019f21  call    cs:__imp_OpenProcess
0x180019f27  mov     rbx, rax
0x180019f2a  mov     [rsp+38h+arg_8], rax
0x180019f2f  mov     rcx, [rsp+38h]; this
0x180019f34  inc     rax
0x180019f37  test    rax, 0FFFFFFFFFFFFFFFEh
0x180019f3d  jnz     short loc_180019F51
0x180019f3f  lea     r8, aShellOnecoreDe_7; "shell\\onecore\\desktopshellext\\lib\\r"...
0x180019f46  mov     edx, 13Ch; void *
0x180019f4b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180019f51  xor     edx, edx
0x180019f53  mov     rcx, rdi
0x180019f56  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180019f5b  mov     rdx, rdi; void *
0x180019f5e  mov     rcx, rbx; hProcess
0x180019f61  call    ?GetPackageFamilyNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetPackageFamilyNameFromProcess(void *,ushort * *)
0x180019f66  mov     rcx, [rsp+38h]; this
0x180019f6b  test    eax, eax
0x180019f6d  jns     short loc_180019F84
0x180019f6f  mov     r9d, eax; char *
0x180019f72  lea     r8, aShellOnecoreDe_7; "shell\\onecore\\desktopshellext\\lib\\r"...
0x180019f79  mov     edx, 13Eh; void *
0x180019f7e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019f84  lea     rcx, [rsp+38h+arg_8]
0x180019f89  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180019f8e  mov     rax, rdi
0x180019f91  mov     rbx, [rsp+38h+arg_10]
0x180019f96  mov     rsi, [rsp+38h+arg_18]
0x180019f9b  add     rsp, 30h
0x180019f9f  pop     rdi
0x180019fa0  retn
```
