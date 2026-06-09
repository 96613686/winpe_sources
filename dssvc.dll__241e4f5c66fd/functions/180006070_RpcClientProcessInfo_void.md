# RpcClientProcessInfo(void *)

- ea: `0x180006070`
- end: `0x180006280`
- name: `?RpcClientProcessInfo@@YA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAX@Z`
- size: `528`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180007220`
- `0x180007300`
- `0x180007440`
- `0x1800075e0`
- `0x1800076f0`
- `0x180007870`

## callees

- `0x18000417c`
- `0x1800041a0`
- `0x180006070`
- `0x180006b84`
- `0x180006d2c`
- `0x180006d54`
- `0x180006e54`
- `0x18001b30a`
- `0x18001b340`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800061c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800061c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800061d5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800061d5`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800060e3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800060e3`
- `RPCRT4!RpcImpersonateClient` at `0x1800060c2`
- `RPCRT4!RpcImpersonateClient` at `0x1800060c2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180006105`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000611f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180006105`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000611f`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180006167`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180006167`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x1800061f6`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x1800061f6`

## pseudocode

```c
__int64 __fastcall RpcClientProcessInfo(__int64 a1, void *a2)
{
  _QWORD *v4; // rcx
  WCHAR *v5; // rdx
  HANDLE v6; // rbx
  WCHAR *v7; // rax
  WCHAR *v8; // rdx
  void **v9; // rbx
  HANDLE CurrentThread; // rax
  __int64 v11; // r8
  unsigned int Pid; // [rsp+20h] [rbp-E0h] BYREF
  void *v14; // [rsp+28h] [rbp-D8h] BYREF
  DWORD dwSize; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 packageFullNameLength; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE token; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR packageFullName[128]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ExeName[264]; // [rsp+140h] [rbp+40h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(a1);
  token = 0;
  v14 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
    v4,
    L" Process: ",
    10);
  if ( RpcImpersonateClient(a2) )
  {
    v5 = L"failure 1";
LABEL_22:
    v11 = 9;
LABEL_23:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
      a1,
      v5,
      v11);
    goto LABEL_24;
  }
  Pid = 0;
  if ( I_RpcBindingInqLocalClientPID(0, &Pid) < 0 )
  {
    v5 = L"failure 2";
    goto LABEL_22;
  }
  v6 = OpenProcess(0x101000u, 0, Pid);
  if ( !v6 )
  {
    v6 = OpenProcess(0x100400u, 0, Pid);
    if ( !v6 )
    {
      v5 = L"failure 3";
      goto LABEL_22;
    }
  }
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v14);
  v14 = v6;
  memset_0(ExeName, 0, 0x208u);
  dwSize = 260;
  if ( QueryFullProcessImageNameW(v6, 0, ExeName, &dwSize) )
  {
    v7 = ExeName;
    v8 = ExeName;
    do
    {
      if ( !*v7 )
        break;
      if ( *v7 == 47 || *v7 == 92 )
        v8 = v7 + 1;
      ++v7;
    }
    while ( v7 );
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(a1, v8);
  }
  else
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
      a1,
      L"failure 4",
      9);
  }
  v9 = (void **)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&token);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, v9) )
  {
    packageFullNameLength = 128;
    if ( GetPackageFullNameFromToken(token, &packageFullNameLength, packageFullName) != 15700 )
    {
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
        a1,
        L" Package:",
        9);
      v11 = -1;
      do
        ++v11;
      while ( packageFullName[v11] );
      v5 = packageFullName;
      goto LABEL_23;
    }
  }
LABEL_24:
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v14);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&token);
  return a1;
}

```

## disassembly

```asm
0x180006070  mov     [rsp-8+arg_10], rbx
0x180006075  push    rbp
0x180006076  push    rsi
0x180006077  push    rdi
0x180006078  lea     rbp, [rsp-260h]
0x180006080  sub     rsp, 360h
0x180006087  mov     rax, cs:__security_cookie
0x18000608e  xor     rax, rsp
0x180006091  mov     [rbp+270h+var_20], rax
0x180006098  mov     rbx, rdx
0x18000609b  mov     rdi, rcx
0x18000609e  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800060a3  xor     esi, esi
0x1800060a5  lea     rdx, aProcess; " Process: "
0x1800060ac  mov     [rsp+370h+token], rsi
0x1800060b1  mov     [rsp+370h+var_348], rsi
0x1800060b6  lea     r8d, [rsi+0Ah]
0x1800060ba  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800060bf  mov     rcx, rbx; BindingHandle
0x1800060c2  call    cs:__imp_RpcImpersonateClient
0x1800060c8  test    eax, eax
0x1800060ca  jz      short loc_1800060D8
0x1800060cc  lea     rdx, aFailure1; "failure 1"
0x1800060d3  jmp     loc_180006239
0x1800060d8  lea     rdx, [rsp+370h+Pid]; Pid
0x1800060dd  mov     [rsp+370h+Pid], esi
0x1800060e1  xor     ecx, ecx; Binding
0x1800060e3  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800060e9  test    eax, eax
0x1800060eb  jns     short loc_1800060F9
0x1800060ed  lea     rdx, aFailure2; "failure 2"
0x1800060f4  jmp     loc_180006239
0x1800060f9  mov     r8d, [rsp+370h+Pid]; dwProcessId
0x1800060fe  xor     edx, edx; bInheritHandle
0x180006100  mov     ecx, 101000h; dwDesiredAccess
0x180006105  call    cs:__imp_OpenProcess
0x18000610b  mov     rbx, rax
0x18000610e  test    rax, rax
0x180006111  jnz     short loc_180006131
0x180006113  mov     r8d, [rsp+370h+Pid]; dwProcessId
0x180006118  xor     edx, edx; bInheritHandle
0x18000611a  mov     ecx, 100400h; dwDesiredAccess
0x18000611f  call    cs:__imp_OpenProcess
0x180006125  mov     rbx, rax
0x180006128  test    rax, rax
0x18000612b  jz      loc_180006232
0x180006131  lea     rcx, [rsp+370h+var_348]
0x180006136  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18000613b  xor     edx, edx; Val
0x18000613d  mov     [rsp+370h+var_348], rbx
0x180006142  mov     r8d, 208h; Size
0x180006148  lea     rcx, [rbp+270h+ExeName]; void *
0x18000614c  call    memset_0
0x180006151  lea     r9, [rsp+370h+dwSize]; lpdwSize
0x180006156  mov     [rsp+370h+dwSize], 104h
0x18000615e  lea     r8, [rbp+270h+ExeName]; lpExeName
0x180006162  xor     edx, edx; dwFlags
0x180006164  mov     rcx, rbx; hProcess
0x180006167  call    cs:__imp_QueryFullProcessImageNameW
0x18000616d  test    eax, eax
0x18000616f  jz      short loc_18000619E
0x180006171  lea     rax, [rbp+270h+ExeName]
0x180006175  lea     rdx, [rbp+270h+ExeName]
0x180006179  cmp     [rax], si
0x18000617c  jz      short loc_180006194
0x18000617e  cmp     word ptr [rax], 2Fh ; '/'
0x180006182  jz      short loc_18000618A
0x180006184  cmp     word ptr [rax], 5Ch ; '\'
0x180006188  jnz     short loc_18000618E
0x18000618a  lea     rdx, [rax+2]
0x18000618e  add     rax, 2
0x180006192  jnz     short loc_180006179
0x180006194  mov     rcx, rdi
0x180006197  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000619c  jmp     short loc_1800061B3
0x18000619e  mov     r8d, 9
0x1800061a4  lea     rdx, aFailure4; "failure 4"
0x1800061ab  mov     rcx, rdi
0x1800061ae  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800061b3  lea     rcx, [rsp+370h+token]
0x1800061b8  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x1800061bd  mov     rbx, rax
0x1800061c0  call    cs:__imp_GetCurrentThread
0x1800061c6  mov     edx, 8; DesiredAccess
0x1800061cb  mov     r9, rbx; TokenHandle
0x1800061ce  mov     rcx, rax; ThreadHandle
0x1800061d1  lea     r8d, [rdx-7]; OpenAsSelf
0x1800061d5  call    cs:__imp_OpenThreadToken
0x1800061db  test    eax, eax
0x1800061dd  jz      short loc_180006247
0x1800061df  mov     rcx, [rsp+370h+token]; token
0x1800061e4  lea     r8, [rsp+370h+packageFullName]; packageFullName
0x1800061e9  lea     rdx, [rsp+370h+packageFullNameLength]; packageFullNameLength
0x1800061ee  mov     [rsp+370h+packageFullNameLength], 80h
0x1800061f6  call    cs:__imp_GetPackageFullNameFromToken
0x1800061fc  cmp     eax, 3D54h
0x180006201  jz      short loc_180006247
0x180006203  mov     r8d, 9
0x180006209  lea     rdx, aPackage; " Package:"
0x180006210  mov     rcx, rdi
0x180006213  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180006218  lea     rax, [rsp+370h+packageFullName]
0x18000621d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006221  inc     r8
0x180006224  cmp     [rax+r8*2], si
0x180006229  jnz     short loc_180006221
0x18000622b  lea     rdx, [rsp+370h+packageFullName]
0x180006230  jmp     short loc_18000623F
0x180006232  lea     rdx, aFailure3; "failure 3"
0x180006239  mov     r8d, 9
0x18000623f  mov     rcx, rdi
0x180006242  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180006247  lea     rcx, [rsp+370h+var_348]
0x18000624c  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180006251  lea     rcx, [rsp+370h+token]
0x180006256  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18000625b  mov     rax, rdi
0x18000625e  mov     rcx, [rbp+270h+var_20]
0x180006265  xor     rcx, rsp; StackCookie
0x180006268  call    __security_check_cookie
0x18000626d  mov     rbx, [rsp+370h+arg_10]
0x180006275  add     rsp, 360h
0x18000627c  pop     rdi
0x18000627d  pop     rsi
0x18000627e  pop     rbp
0x18000627f  retn
```
