# ClusNode::ClusNode(PhaseManager &,wchar_t const *,wchar_t const *,wchar_t const *,ulong,ClusterGlobalData &)

- ea: `0x180046478`
- end: `0x1800465d9`
- name: `??0ClusNode@@QEAA@AEAVPhaseManager@@PEB_W11KAEAVClusterGlobalData@@@Z`
- size: `353`
- prototype: `ClusNode *(ClusNode *__hidden this, struct PhaseManager *, const wchar_t *, const wchar_t *, const wchar_t *, unsigned int, struct ClusterGlobalData *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18003f114`
- `0x1800791d0`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001cc2c`
- `0x180028f30`
- `0x18003180c`
- `0x180046478`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046585`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180046512`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180046512`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800464f8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800464f8`

## string_xrefs

- `0x180046550`: `Failed to connect to the service control manager on '%ws'`
- `0x18004658e`: `Failed to open the clussvc service on '%ws'`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
ClusNode *__fastcall ClusNode::ClusNode(
        ClusNode *this,
        struct PhaseManager *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        unsigned int a6,
        struct ClusterGlobalData *a7)
{
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // rax
  __int64 v11; // rbx
  DWORD LastError; // eax
  __int64 v13; // rbx
  DWORD v14; // eax
  _BYTE pExceptionObject[272]; // [rsp+30h] [rbp-138h] BYREF

  *(_QWORD *)this = a7;
  *((_QWORD *)this + 1) = a2;
  std::wstring::wstring((char *)this + 16, a3);
  std::wstring::wstring((char *)this + 48, a4);
  std::wstring::wstring((char *)this + 80, a5);
  *((_DWORD *)this + 28) = a6;
  v9 = OpenSCManagerW(a4, 0, 1u);
  *((_QWORD *)this + 15) = v9;
  v10 = OpenServiceW(v9, L"ClusSvc", 0x37u);
  *((_QWORD *)this + 16) = v10;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 29) = 0;
  if ( !*((_QWORD *)this + 15) )
  {
    v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 48);
    LastError = GetLastError();
    ClusRtl::ExceptionMsg::ExceptionMsg(
      (ClusRtl::ExceptionMsg *)pExceptionObject,
      LastError,
      L"Failed to connect to the service control manager on '%ws'",
      v11,
      this);
    throw (ClusRtl::ExceptionMsg *)pExceptionObject;
  }
  if ( !v10 )
  {
    v13 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 48);
    v14 = GetLastError();
    ClusRtl::ExceptionMsg::ExceptionMsg(
      (ClusRtl::ExceptionMsg *)pExceptionObject,
      v14,
      L"Failed to open the clussvc service on '%ws'",
      v13,
      this);
    throw (ClusRtl::ExceptionMsg *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180046478  mov     [rsp+arg_8], rbx
0x18004647d  push    rbp
0x18004647e  push    rsi
0x18004647f  push    rdi
0x180046480  sub     rsp, 150h
0x180046487  mov     rax, cs:__security_cookie
0x18004648e  xor     rax, rsp
0x180046491  mov     [rsp+168h+var_28], rax
0x180046499  mov     rdi, r9
0x18004649c  mov     rsi, rcx
0x18004649f  mov     [rsp+168h+var_148], rcx
0x1800464a4  mov     rbx, [rsp+168h+arg_20]
0x1800464ac  mov     rax, [rsp+168h+arg_30]
0x1800464b4  mov     [rcx], rax
0x1800464b7  mov     [rcx+8], rdx
0x1800464bb  add     rcx, 10h
0x1800464bf  mov     rdx, r8
0x1800464c2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800464c7  nop
0x1800464c8  lea     rbp, [rsi+30h]
0x1800464cc  mov     rdx, rdi
0x1800464cf  mov     rcx, rbp
0x1800464d2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800464d7  nop
0x1800464d8  lea     rcx, [rsi+50h]
0x1800464dc  mov     rdx, rbx
0x1800464df  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800464e4  nop
0x1800464e5  mov     eax, [rsp+168h+arg_28]
0x1800464ec  mov     [rsi+70h], eax
0x1800464ef  xor     edx, edx; lpDatabaseName
0x1800464f1  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800464f5  mov     rcx, rdi; lpMachineName
0x1800464f8  call    cs:__imp_OpenSCManagerW
0x1800464fe  mov     [rsi+78h], rax
0x180046502  mov     r8d, 37h ; '7'; dwDesiredAccess
0x180046508  lea     rdx, aClussvc; "ClusSvc"
0x18004650f  mov     rcx, rax; hSCManager
0x180046512  call    cs:__imp_OpenServiceW
0x180046518  mov     [rsi+80h], rax
0x18004651f  xor     ecx, ecx
0x180046521  mov     [rsi+88h], rcx
0x180046528  mov     [rsi+90h], rcx
0x18004652f  mov     [rsi+0E8h], rcx
0x180046536  cmp     [rsi+78h], rcx
0x18004653a  jnz     short loc_180046575
0x18004653c  mov     rcx, rbp
0x18004653f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180046544  mov     rbx, rax
0x180046547  call    cs:__imp_GetLastError
0x18004654d  mov     r9, rbx
0x180046550  lea     r8, aFailedToConnec; "Failed to connect to the service contro"...
0x180046557  mov     edx, eax; int
0x180046559  lea     rcx, [rsp+168h+pExceptionObject]; this
0x18004655e  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180046563  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18004656a  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x18004656f  call    _CxxThrowException_0
0x180046575  test    rax, rax
0x180046578  jnz     short loc_1800465B3
0x18004657a  mov     rcx, rbp
0x18004657d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180046582  mov     rbx, rax
0x180046585  call    cs:__imp_GetLastError
0x18004658b  mov     r9, rbx
0x18004658e  lea     r8, aFailedToOpenTh_0; "Failed to open the clussvc service on '"...
0x180046595  mov     edx, eax; int
0x180046597  lea     rcx, [rsp+168h+pExceptionObject]; this
0x18004659c  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x1800465a1  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x1800465a8  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x1800465ad  call    _CxxThrowException_0
0x1800465b3  mov     rax, rsi
0x1800465b6  mov     rcx, [rsp+168h+var_28]
0x1800465be  xor     rcx, rsp; StackCookie
0x1800465c1  call    __security_check_cookie
0x1800465c6  mov     rbx, [rsp+168h+arg_8]
0x1800465ce  add     rsp, 150h
0x1800465d5  pop     rdi
0x1800465d6  pop     rsi
0x1800465d7  pop     rbp
0x1800465d8  retn
```
