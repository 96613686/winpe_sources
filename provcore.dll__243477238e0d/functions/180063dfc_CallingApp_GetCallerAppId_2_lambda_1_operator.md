# _CallingApp::GetCallerAppId_::_2_::_lambda_1_::operator()

- ea: `0x180063dfc`
- end: `0x180063ef0`
- name: `_CallingApp::GetCallerAppId_::_2_::_lambda_1_::operator()`
- size: `244`
- prototype: `HRESULT __fastcall()`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180063dd8`

## callees

- `0x18000866c`
- `0x180011844`
- `0x180012400`
- `0x180012770`
- `0x1800127cc`
- `0x180063dfc`
- `0x1800665f0`
- `0x180067134`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063e54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063e54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063eb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063eb1`

## pseudocode

```c
__int64 __fastcall CallingApp::GetCallerAppId_::_2_::_lambda_1_::operator()(std::wstring **a1)
{
  wchar_t *v1; // rdi
  int CallingProcessHandle; // ebx
  HRESULT PackageFamilyNameFromProcess; // eax
  char *v5; // rcx
  unsigned __int64 v6; // rax
  const wchar_t *v7; // rax
  __int64 v8; // r10
  void *hProcess; // [rsp+48h] [rbp+10h] BYREF
  wchar_t *pszAppId; // [rsp+50h] [rbp+18h] BYREF

  v1 = 0;
  pszAppId = 0;
  hProcess = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle((unsigned int)a1, &hProcess);
  if ( CallingProcessHandle >= 0 )
  {
    PackageFamilyNameFromProcess = CallerIdentity::GetPackageFamilyNameFromProcess(hProcess, &pszAppId);
    v1 = pszAppId;
    CallingProcessHandle = PackageFamilyNameFromProcess;
  }
  v5 = (char *)hProcess;
  hProcess = 0;
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  if ( CallingProcessHandle >= 0 )
  {
    v6 = std::_WChar_traits<unsigned short>::length(v1);
    std::wstring::_Assign<unsigned short>(*a1, v1, v6);
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&(*a1)->_Mypair._Myval2);
      WPP_SF_S(*(_QWORD *)(v8 + 16), 0xDu, WPP_23c62c4a87f335c33f4b82b787c27e30_Traceguids, v7);
    }
    CoTaskMemFree(v1);
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->Control.Logger,
      0xEu,
      WPP_23c62c4a87f335c33f4b82b787c27e30_Traceguids,
      CallingProcessHandle);
  }
  return (unsigned int)CallingProcessHandle;
}

```

## disassembly

```asm
0x180063dfc  mov     rax, rsp
0x180063dff  mov     [rax+8], rbx
0x180063e03  push    rbp
0x180063e04  push    rsi
0x180063e05  push    rdi
0x180063e06  sub     rsp, 20h
0x180063e0a  xor     edi, edi
0x180063e0c  lea     rdx, [rax+10h]; dwProcessAccessFlags
0x180063e10  mov     [rax+18h], rdi
0x180063e14  mov     rsi, this
0x180063e17  mov     [rax+10h], rdi
0x180063e1b  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x180063e20  mov     ebx, eax
0x180063e22  test    eax, eax
0x180063e24  js      short loc_180063E3C
0x180063e26  mov     this, [rsp+38h+hProcess]; hProcess
0x180063e2b  lea     rdx, [rsp+38h+pszAppId]; ppszPackageFamilyName
0x180063e30  call    ?GetPackageFamilyNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetPackageFamilyNameFromProcess(void *,ushort * *)
0x180063e35  mov     rdi, [rsp+38h+pszAppId]
0x180063e3a  mov     ebx, eax
0x180063e3c  mov     this, [rsp+38h+hProcess]; hObject
0x180063e41  mov     [rsp+38h+hProcess], 0
0x180063e4a  lea     rax, [this-1]
0x180063e4e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180063e52  ja      short loc_180063E5A
0x180063e54  call    cs:__imp_CloseHandle
0x180063e5a  lea     rbp, WPP_GLOBAL_Control
0x180063e61  test    ebx, ebx
0x180063e63  js      short loc_180063EB7
0x180063e65  mov     this, rdi; _First
0x180063e68  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180063e6d  mov     this, [rsi]; this
0x180063e70  mov     r8, rax; _Count
0x180063e73  mov     rdx, rdi; _Ptr
0x180063e76  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180063e7b  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180063e82  cmp     r10, rbp
0x180063e85  jz      short loc_180063EAE
0x180063e87  test    byte ptr [r10+1Ch], 10h
0x180063e8c  jz      short loc_180063EAE
0x180063e8e  mov     this, [rsi]; this
0x180063e91  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180063e96  mov     this, [r10+10h]; Logger
0x180063e9a  lea     r8, WPP_23c62c4a87f335c33f4b82b787c27e30_Traceguids; TraceGuid
0x180063ea1  mov     r9, rax; _a1
0x180063ea4  mov     edx, 0Dh; id
0x180063ea9  call    WPP_SF_S
0x180063eae  mov     this, rdi; pv
0x180063eb1  call    cs:__imp_CoTaskMemFree
0x180063eb7  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180063ebe  cmp     this, rbp
0x180063ec1  jz      short loc_180063EE1
0x180063ec3  test    byte ptr [this+1Ch], 10h
0x180063ec7  jz      short loc_180063EE1
0x180063ec9  mov     this, [this+10h]; Logger
0x180063ecd  lea     r8, WPP_23c62c4a87f335c33f4b82b787c27e30_Traceguids; TraceGuid
0x180063ed4  mov     edx, 0Eh; id
0x180063ed9  mov     r9d, ebx; _a1
0x180063edc  call    WPP_SF_d
0x180063ee1  mov     eax, ebx
0x180063ee3  mov     rbx, [rsp+38h+arg_0]
0x180063ee8  add     rsp, 20h
0x180063eec  pop     rdi
0x180063eed  pop     rsi
0x180063eee  pop     rbp
0x180063eef  retn
```
