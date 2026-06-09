# EapLm::Peer::EapLibraryManagerRuntime::CreateProxy(_EAP_METHOD_TYPE,int)

- ea: `0x180021e14`
- end: `0x180021fbd`
- name: `?CreateProxy@EapLibraryManagerRuntime@Peer@EapLm@@QEAAJU_EAP_METHOD_TYPE@@H@Z`
- size: `425`
- prototype: `__int64 __fastcall(EapLm::Peer::EapLibraryManagerRuntime *__hidden this, struct _EAP_METHOD_TYPE *__struct_ptr, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021fc4`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x18000d0e8`
- `0x180015534`
- `0x180016400`
- `0x18001b154`
- `0x180021e14`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180021e55`
- `ntdll!EtwEventEnabled` at `0x180021e55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021f82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021fa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021f82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021fa0`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180021f03`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180021f03`

## string_xrefs

- `0x180021f8c`: `COM Error`
- `0x180021fa9`: `COM Error`
- `0x180021f93`: `Create Third Party Proxy`
- `0x180021fb0`: `Create Third Party Proxy`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::EapLibraryManagerRuntime::CreateProxy(
        EapLm::Peer::EapLibraryManagerRuntime *this,
        struct _EAP_METHOD_TYPE *a2,
        int a3)
{
  __int64 v3; // rdi
  __int64 v6; // rsi
  __int64 v7; // rdi
  int v8; // esi
  __int64 v9; // rax
  DWORD v11; // eax
  DWORD LastError; // eax
  __int64 v13[2]; // [rsp+30h] [rbp-838h] BYREF
  char v14[2048]; // [rsp+40h] [rbp-828h] BYREF

  v3 = a3;
  v13[0] = 0;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v14, 0x800u, " Startin a new Eap3Host process for the author id: %d.", a2->dwAuthorId) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v14);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids);
  v6 = v3;
  v7 = 3 * v3;
  *((_DWORD *)this + 2 * v7 + 40) = a2->dwAuthorId;
  if ( CoGetClassObject(
         &GUID_87bb326b_e4a0_4de1_94f0_b9f41d0c6059,
         0x10004u,
         0,
         &GUID_00000001_0000_0000_c000_000000000046,
         (LPVOID *)this + v7 + 21) < 0 )
  {
    LastError = GetLastError();
    EapHost::EapException::Throw(L"Create Third Party Proxy", L"COM Error", LastError);
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, __int64 *))(**((_QWORD **)this + 3 * v6 + 21) + 24LL))(
         *((_QWORD *)this + 3 * v6 + 21),
         0,
         &GUID_c48ca462_67fb_4c12_a21a_6415460fa8ae,
         v13);
  if ( v8 < 0 )
  {
    v11 = GetLastError();
    EapHost::EapException::Throw(L"Create Third Party Proxy", L"COM Error", v11);
  }
  v9 = v13[0];
  v13[0] = 0;
  *((_QWORD *)this + v7 + 22) = v9;
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(v13);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180021e14  mov     [rsp+arg_18], rbx
0x180021e19  push    rbp
0x180021e1a  push    rsi
0x180021e1b  push    rdi
0x180021e1c  sub     rsp, 850h
0x180021e23  mov     rax, cs:__security_cookie
0x180021e2a  xor     rax, rsp
0x180021e2d  mov     [rsp+868h+var_28], rax
0x180021e35  movsxd  rdi, r8d
0x180021e38  mov     rbp, rdx
0x180021e3b  mov     rbx, rcx
0x180021e3e  mov     [rsp+868h+var_838], 0
0x180021e47  lea     rdx, DebugInfoEvent
0x180021e4e  mov     rcx, cs:eaphost_Context
0x180021e55  call    cs:__imp_EtwEventEnabled
0x180021e5b  test    al, al
0x180021e5d  jz      short loc_180021E9E
0x180021e5f  mov     r9d, [rbp+0Ch]
0x180021e63  lea     r8, aStartinANewEap; " Startin a new Eap3Host process for the"...
0x180021e6a  mov     edx, 800h; unsigned __int64
0x180021e6f  lea     rcx, [rsp+868h+var_828]; char *
0x180021e74  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180021e79  test    eax, eax
0x180021e7b  js      short loc_180021E9E
0x180021e7d  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180021e84  jge     short loc_180021E9E
0x180021e86  lea     r8, [rsp+868h+var_828]
0x180021e8b  lea     rdx, DebugInfoEvent
0x180021e92  lea     rcx, eaphost_Context
0x180021e99  call    McTemplateU0s_EtwEventWriteTransfer
0x180021e9e  lea     rax, WPP_GLOBAL_Control
0x180021ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x180021eac  cmp     rcx, rax
0x180021eaf  jz      short loc_180021ECC
0x180021eb1  test    byte ptr [rcx+1Ch], 4
0x180021eb5  jz      short loc_180021ECC
0x180021eb7  mov     edx, 0Fh
0x180021ebc  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x180021ec3  mov     rcx, [rcx+10h]
0x180021ec7  call    WPP_SF_
0x180021ecc  mov     rsi, rdi
0x180021ecf  lea     rdi, [rdi+rdi*2]
0x180021ed3  mov     eax, [rbp+0Ch]
0x180021ed6  mov     [rbx+rdi*8+0A0h], eax
0x180021edd  lea     rax, [rbx+0A8h]
0x180021ee4  lea     rax, [rax+rdi*8]
0x180021ee8  mov     [rsp+868h+ppv], rax; ppv
0x180021eed  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180021ef4  xor     r8d, r8d; pvReserved
0x180021ef7  mov     edx, 10004h; dwClsContext
0x180021efc  lea     rcx, _GUID_87bb326b_e4a0_4de1_94f0_b9f41d0c6059; rclsid
0x180021f03  call    cs:__imp_CoGetClassObject
0x180021f09  test    eax, eax
0x180021f0b  js      loc_180021FA0
0x180021f11  lea     rax, [rsi+rsi*2]
0x180021f15  mov     rcx, [rbx+rax*8+0A8h]
0x180021f1d  mov     rax, [rcx]
0x180021f20  lea     r9, [rsp+868h+var_838]
0x180021f25  lea     r8, _GUID_c48ca462_67fb_4c12_a21a_6415460fa8ae
0x180021f2c  xor     edx, edx
0x180021f2e  mov     rax, [rax+18h]
0x180021f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f37  mov     esi, eax
0x180021f39  test    eax, eax
0x180021f3b  js      short loc_180021F82
0x180021f3d  mov     rax, [rsp+868h+var_838]
0x180021f42  mov     [rsp+868h+var_838], 0
0x180021f4b  mov     [rbx+rdi*8+0B0h], rax
0x180021f53  lea     rcx, [rsp+868h+var_838]
0x180021f58  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180021f5d  mov     eax, esi
0x180021f5f  mov     rcx, [rsp+868h+var_28]
0x180021f67  xor     rcx, rsp; StackCookie
0x180021f6a  call    __security_check_cookie
0x180021f6f  mov     rbx, [rsp+868h+arg_18]
0x180021f77  add     rsp, 850h
0x180021f7e  pop     rdi
0x180021f7f  pop     rsi
0x180021f80  pop     rbp
0x180021f81  retn
0x180021f82  call    cs:__imp_GetLastError
0x180021f88  nop
0x180021f89  mov     r8d, eax; int
0x180021f8c  lea     rdx, aComError; "COM Error"
0x180021f93  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x180021f9a  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180021fa0  call    cs:__imp_GetLastError
0x180021fa6  mov     r8d, eax; int
0x180021fa9  lea     rdx, aComError; "COM Error"
0x180021fb0  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x180021fb7  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
```
