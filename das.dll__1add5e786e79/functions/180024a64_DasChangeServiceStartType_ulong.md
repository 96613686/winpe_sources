# DasChangeServiceStartType(ulong)

- ea: `0x180024a64`
- end: `0x180024be3`
- name: `?DasChangeServiceStartType@@YAJK@Z`
- size: `383`
- prototype: `__int64 __fastcall(DWORD dwStartType, int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180028ed8`
- `0x1800436e4`

## callees

- `0x18001a760`
- `0x180024a64`
- `0x180024bec`
- `0x18002a948`
- `0x18002a96c`
- `0x18002aa34`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024b14`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024b14`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180024b6f`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180024b6f`

## string_xrefs

- `0x180024aef`: `onecore\base\devices\association\service\lib\srventry.cpp`
- `0x180024b81`: `onecore\base\devices\association\service\lib\srventry.cpp`

## pseudocode

```c
__int64 __fastcall DasChangeServiceStartType(DWORD dwStartType, int a2, int a3)
{
  const wchar_t *v4; // rdi
  const wchar_t *v5; // rax
  int v6; // eax
  unsigned int LastError; // ebx
  int v8; // edx
  int v9; // r8d
  const char *v10; // r9
  int lpBinaryPathName; // [rsp+20h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  SC_HANDLE hSCObject; // [rsp+A8h] [rbp+10h] BYREF

  v4 = L"auto";
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v5 = L"auto";
    if ( dwStartType != 2 )
      v5 = (const wchar_t *)L"trigger";
    WPP_RECORDER_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      a2,
      a3,
      10,
      &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
      (__int64)v5);
  }
  hSCObject = 0;
  v6 = DasOpenService(&hSCObject, 2);
  LastError = v6;
  if ( v6 >= 0 )
  {
    if ( ChangeServiceConfigW(hSCObject, 0xFFFFFFFF, dwStartType, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        if ( dwStartType != 2 )
          v4 = (const wchar_t *)L"trigger";
        WPP_RECORDER_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v8,
          v9,
          11,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
          (__int64)v4);
      }
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x59,
                    (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\srventry.cpp",
                    v10);
    }
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&hSCObject);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\srventry.cpp",
      (const char *)(unsigned int)v6,
      lpBinaryPathName);
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
  }
  return LastError;
}

```

## disassembly

```asm
0x180024a64  push    rbx
0x180024a66  push    rsi
0x180024a67  push    rdi
0x180024a68  push    r12
0x180024a6a  push    r14
0x180024a6c  push    r15
0x180024a6e  sub     rsp, 68h
0x180024a72  mov     esi, ecx
0x180024a74  lea     r14, WPP_RECORDER_INITIALIZED
0x180024a7b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180024a82  lea     r15, aTrigger; "trigger"
0x180024a89  lea     rdi, aAuto; "auto"
0x180024a90  lea     r12, WPP_f5243b9130583a582cae89f06194ea2b_Traceguids
0x180024a97  jz      short loc_180024AC3
0x180024a99  cmp     ecx, 2
0x180024a9c  mov     rax, rdi
0x180024a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024aa6  mov     r9d, 0Ah; int
0x180024aac  cmovnz  rax, r15
0x180024ab0  mov     [rsp+98h+lpLoadOrderGroup], rax; __int64
0x180024ab5  mov     [rsp+98h+lpBinaryPathName], r12; int
0x180024aba  mov     rcx, [rcx+28h]; int
0x180024abe  call    WPP_RECORDER_SF_S
0x180024ac3  mov     edx, 2
0x180024ac8  mov     [rsp+98h+hSCObject], 0
0x180024ad4  lea     rcx, [rsp+98h+hSCObject]
0x180024adc  call    ?DasOpenService@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; DasOpenService(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>> &,ulong)
0x180024ae1  mov     ebx, eax
0x180024ae3  test    eax, eax
0x180024ae5  jns     short loc_180024B1F
0x180024ae7  mov     rcx, [rsp+98h]; this
0x180024aef  lea     r8, aOnecoreBaseDev_9; "onecore\\base\\devices\\association\\se"...
0x180024af6  mov     r9d, eax; char *
0x180024af9  mov     edx, 58h ; 'X'; void *
0x180024afe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024b03  mov     rcx, [rsp+98h+hSCObject]; hSCObject
0x180024b0b  test    rcx, rcx
0x180024b0e  jz      loc_180024BD3
0x180024b14  call    cs:__imp_CloseServiceHandle
0x180024b1a  jmp     loc_180024BD3
0x180024b1f  mov     rcx, [rsp+98h+hSCObject]; hService
0x180024b27  or      edx, 0FFFFFFFFh; dwServiceType
0x180024b2a  mov     [rsp+98h+lpDisplayName], 0; lpDisplayName
0x180024b33  mov     r9d, edx; dwErrorControl
0x180024b36  mov     [rsp+98h+lpPassword], 0; lpPassword
0x180024b3f  mov     r8d, esi; dwStartType
0x180024b42  mov     [rsp+98h+lpServiceStartName], 0; lpServiceStartName
0x180024b4b  mov     [rsp+98h+lpDependencies], 0; lpDependencies
0x180024b54  mov     [rsp+98h+lpdwTagId], 0; lpdwTagId
0x180024b5d  mov     [rsp+98h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180024b66  mov     [rsp+98h+lpBinaryPathName], 0; lpBinaryPathName
0x180024b6f  call    cs:__imp_ChangeServiceConfigW
0x180024b75  test    eax, eax
0x180024b77  jnz     short loc_180024B94
0x180024b79  mov     rcx, [rsp+98h]; this
0x180024b81  lea     r8, aOnecoreBaseDev_9; "onecore\\base\\devices\\association\\se"...
0x180024b88  lea     edx, [rax+59h]; void *
0x180024b8b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024b90  mov     ebx, eax
0x180024b92  jmp     short loc_180024BC6
0x180024b94  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180024b9b  jz      short loc_180024BC4
0x180024b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024ba4  cmp     esi, 2
0x180024ba7  mov     r9d, 0Bh; int
0x180024bad  cmovnz  rdi, r15
0x180024bb1  mov     [rsp+98h+lpLoadOrderGroup], rdi; __int64
0x180024bb6  mov     rcx, [rcx+28h]; int
0x180024bba  mov     [rsp+98h+lpBinaryPathName], r12; MessageGuid
0x180024bbf  call    WPP_RECORDER_SF_S
0x180024bc4  xor     ebx, ebx
0x180024bc6  lea     rcx, [rsp+98h+hSCObject]
0x180024bce  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180024bd3  mov     eax, ebx
0x180024bd5  add     rsp, 68h
0x180024bd9  pop     r15
0x180024bdb  pop     r14
0x180024bdd  pop     r12
0x180024bdf  pop     rdi
0x180024be0  pop     rsi
0x180024be1  pop     rbx
0x180024be2  retn
```
