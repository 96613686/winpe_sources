# DragManagerClientProxy::GetDesktop(void)

- ea: `0x1800287d0`
- end: `0x180028943`
- name: `?GetDesktop@DragManagerClientProxy@@AEAAJXZ`
- size: `371`
- prototype: `__int64 __fastcall(DragManagerClientProxy *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027d60`

## callees

- `0x180012b74`
- `0x1800287d0`
- `0x180028a6c`
- `0x180028a8c`
- `0x18007f688`
- `0x18008daac`
- `0x18008dcac`
- `0x18008ead4`
- `0x1800f0990`
- `0x1801ce010`

## import_xrefs

- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x180028898`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x180028898`
- `ext-ms-win-ntuser-windowstation-l1-1-0!OpenThreadDesktop` at `0x18002886b`
- `ext-ms-win-ntuser-windowstation-l1-1-0!OpenThreadDesktop` at `0x18002886b`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x1800288a5`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x1800288a5`

## string_xrefs

- `0x1800288e4`: `onecoreuap\windows\moderncore\inputv2\contextualprocessors\components\inputgestures\system\dragmanagerclientproxy.cpp`
- `0x180028902`: `onecoreuap\windows\moderncore\inputv2\contextualprocessors\components\inputgestures\system\dragmanagerclientproxy.cpp`
- `0x180028919`: `onecoreuap\windows\moderncore\inputv2\contextualprocessors\components\inputgestures\system\dragmanagerclientproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DragManagerClientProxy::GetDesktop(DragManagerClientProxy *this)
{
  Microsoft::Bamo::BaseBamoConnection *Connection; // rax
  struct IMessageSession *Session; // rdi
  void (__fastcall *v4)(struct IMessageSession *, __int64 *); // rbx
  int v5; // eax
  __int64 v6; // rcx
  HDESK v7; // rax
  HDESK v8; // rbx
  const char *v9; // r9
  __int64 v10; // rcx
  unsigned int LastError; // ebx
  int lpnLengthNeeded; // [rsp+20h] [rbp-58h]
  __int64 v14; // [rsp+30h] [rbp-48h] BYREF
  HDESK v15; // [rsp+38h] [rbp-40h] BYREF
  _OWORD v16[2]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  v14 = 0;
  Connection = Microsoft::Bamo::Lib::ISMBamos_AutoBamos::BamoList_VirtualTouchpadRect_Principal::GetConnection(*(Microsoft::Bamo::Lib::ISMBamos_AutoBamos::BamoList_VirtualTouchpadRect_Principal **)(*((_QWORD *)this + 4) + 16LL));
  Session = Microsoft::Bamo::BaseBamoConnection::GetSession(Connection);
  v4 = *(void (__fastcall **)(struct IMessageSession *, __int64 *))(*(_QWORD *)Session + 32LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  v4(Session, &v14);
  memset(v16, 0, 28);
  v5 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v14 + 24LL))(v14, v16);
  if ( v5 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\components\\inputgestures\\system\\d"
                    "ragmanagerclientproxy.cpp",
      (const char *)(unsigned int)v5,
      lpnLengthNeeded);
  v6 = DWORD1(v16[1]);
  *((_DWORD *)this + 40) = DWORD1(v16[1]);
  v7 = (HDESK)OpenThreadDesktop(v6, 0, 0, 1);
  v8 = v7;
  v15 = v7;
  if ( !v7 )
  {
    LastError = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\components\\inputgestures\\system\\d"
                    "ragmanagerclientproxy.cpp",
      (const char *)0x80070005LL,
      lpnLengthNeeded);
LABEL_10:
    wil::details::unique_storage<wil::details::resource_policy<HDESK__ *,int (*)(HDESK__ *),&int CloseDesktop(HDESK__ *),wistd::integral_constant<unsigned __int64,0>,HDESK__ *,HDESK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HDESK__ *,int (*)(HDESK__ *),&int CloseDesktop(HDESK__ *),wistd::integral_constant<unsigned __int64,0>,HDESK__ *,HDESK__ *,0,std::nullptr_t>>(&v15);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
    return LastError;
  }
  if ( !GetUserObjectInformationW(v7, 8, (char *)this + 152, 8u, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x96,
                  (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\components\\inputgesture"
                                "s\\system\\dragmanagerclientproxy.cpp",
                  v9);
    goto LABEL_10;
  }
  CloseDesktop(v8);
  v10 = v14;
  if ( v14 )
  {
    v14 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return 0;
}

```

## disassembly

```asm
0x1800287d0  push    rbp
0x1800287d2  push    rbx
0x1800287d3  push    rsi
0x1800287d4  push    rdi
0x1800287d5  mov     rbp, rsp
0x1800287d8  sub     rsp, 78h
0x1800287dc  mov     rax, cs:__security_cookie
0x1800287e3  xor     rax, rsp
0x1800287e6  mov     [rbp+var_18], rax
0x1800287ea  mov     rsi, rcx
0x1800287ed  mov     [rbp+var_48], 0
0x1800287f5  mov     rcx, [rcx+20h]
0x1800287f9  mov     rcx, [rcx+10h]; this
0x1800287fd  call    ?GetConnection@BamoList_VirtualTouchpadRect_Principal@ISMBamos_AutoBamos@Lib@Bamo@Microsoft@@QEBAPEAVBamoConnection@2@XZ; Microsoft::Bamo::Lib::ISMBamos_AutoBamos::BamoList_VirtualTouchpadRect_Principal::GetConnection(void)
0x180028802  mov     rcx, rax; this
0x180028805  call    ?GetSession@BaseBamoConnection@Bamo@Microsoft@@QEBAPEAUIMessageSession@@XZ; Microsoft::Bamo::BaseBamoConnection::GetSession(void)
0x18002880a  mov     rdi, rax
0x18002880d  mov     rcx, [rax]
0x180028810  mov     rbx, [rcx+20h]
0x180028814  lea     rcx, [rbp+var_48]
0x180028818  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002881d  lea     rdx, [rbp+var_48]
0x180028821  mov     rcx, rdi
0x180028824  mov     rax, rbx
0x180028827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002882c  xorps   xmm0, xmm0
0x18002882f  movups  [rbp+var_38], xmm0
0x180028833  movups  [rbp+var_38+0Ch], xmm0
0x180028837  mov     rcx, [rbp+var_48]
0x18002883b  mov     rax, [rcx]
0x18002883e  lea     rdx, [rbp+var_38]
0x180028842  mov     rax, [rax+18h]
0x180028846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002884b  mov     rcx, [rbp+20h]; this
0x18002884f  test    eax, eax
0x180028851  js      loc_1800288E1
0x180028857  mov     ecx, [rbp+var_24]
0x18002885a  mov     [rsi+0A0h], ecx
0x180028860  mov     r9d, 1
0x180028866  xor     r8d, r8d
0x180028869  xor     edx, edx
0x18002886b  call    cs:__imp_OpenThreadDesktop
0x180028871  mov     rbx, rax
0x180028874  mov     [rbp+var_40], rax
0x180028878  test    rax, rax
0x18002887b  jz      short loc_1800288F6
0x18002887d  lea     r8, [rsi+98h]; pvInfo
0x180028884  mov     qword ptr [rsp+78h+lpnLengthNeeded], 0; lpnLengthNeeded
0x18002888d  mov     edx, 8; nIndex
0x180028892  mov     r9d, edx; nLength
0x180028895  mov     rcx, rax; hObj
0x180028898  call    cs:__imp_GetUserObjectInformationW
0x18002889e  test    eax, eax
0x1800288a0  jz      short loc_180028915
0x1800288a2  mov     rcx, rbx; hDesktop
0x1800288a5  call    cs:__imp_CloseDesktop
0x1800288ab  nop
0x1800288ac  mov     rcx, [rbp+var_48]
0x1800288b0  test    rcx, rcx
0x1800288b3  jz      short loc_1800288CA
0x1800288b5  mov     [rbp+var_48], 0
0x1800288bd  mov     rax, [rcx]
0x1800288c0  mov     rax, [rax+10h]
0x1800288c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288c9  nop
0x1800288ca  xor     eax, eax
0x1800288cc  mov     rcx, [rbp+var_18]
0x1800288d0  xor     rcx, rsp; StackCookie
0x1800288d3  call    __security_check_cookie
0x1800288d8  add     rsp, 78h
0x1800288dc  pop     rdi
0x1800288dd  pop     rsi
0x1800288de  pop     rbx
0x1800288df  pop     rbp
0x1800288e0  retn
0x1800288e1  mov     r9d, eax; char *
0x1800288e4  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800288eb  mov     edx, 83h; void *
0x1800288f0  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800288f6  mov     rcx, [rbp+20h]; this
0x1800288fa  mov     ebx, 80070005h
0x1800288ff  mov     r9d, ebx; char *
0x180028902  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\moderncore\\inputv"...
0x180028909  mov     edx, 8Fh; void *
0x18002890e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028913  jmp     short loc_18002892C
0x180028915  mov     rcx, [rbp+20h]; this
0x180028919  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\moderncore\\inputv"...
0x180028920  mov     edx, 96h; void *
0x180028925  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002892a  mov     ebx, eax
0x18002892c  lea     rcx, [rbp+var_40]
0x180028930  call    ??1?$unique_storage@U?$resource_policy@PEAUHDESK__@@P6AHPEAU1@@Z$1?CloseDesktop@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HDESK__ *,int (*)(HDESK__ *),&CloseDesktop(HDESK__ *),wistd::integral_constant<unsigned __int64,0>,HDESK__ *,HDESK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HDESK__ *,int (*)(HDESK__ *),&CloseDesktop(HDESK__ *),wistd::integral_constant<unsigned __int64,0>,HDESK__ *,HDESK__ *,0,std::nullptr_t>>(void)
0x180028935  nop
0x180028936  lea     rcx, [rbp+var_48]
0x18002893a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002893f  mov     eax, ebx
0x180028941  jmp     short loc_1800288CC
```
