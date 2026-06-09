# EapLm::Peer::EapLibraryManagerRuntime::CreateProxy(_EAP_METHOD_TYPE,int)

- ea: `0x180010eb4`
- end: `0x18001105d`
- name: `?CreateProxy@EapLibraryManagerRuntime@Peer@EapLm@@QEAAJU_EAP_METHOD_TYPE@@H@Z`
- size: `425`
- prototype: `__int64 __fastcall(EapLm::Peer::EapLibraryManagerRuntime *__hidden this, struct _EAP_METHOD_TYPE *__struct_ptr, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011064`

## callees

- `0x180002a90`
- `0x180004b98`
- `0x180009dc4`
- `0x180010eb4`
- `0x180011578`
- `0x180011958`
- `0x18001dcbc`
- `0x180038010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180010ef5`
- `ntdll!EtwEventEnabled` at `0x180010ef5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011040`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180010fa3`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180010fa3`

## string_xrefs

- `0x18001102c`: `COM Error`
- `0x180011049`: `COM Error`
- `0x180011033`: `Create Third Party Proxy`
- `0x180011050`: `Create Third Party Proxy`

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
  _QWORD v13[2]; // [rsp+30h] [rbp-838h] BYREF
  char v14[2048]; // [rsp+40h] [rbp-828h] BYREF

  v3 = a3;
  v13[0] = 0;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v14, 0x800u, " Startin a new Eap3Host process for the author id: %d.", a2->dwAuthorId) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v14);
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids);
  }
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
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, _QWORD *))(**((_QWORD **)this + 3 * v6 + 21) + 24LL))(
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
  ComPointer<IUnknown>::Release(v13);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180010eb4  mov     [rsp+arg_18], rbx
0x180010eb9  push    rbp
0x180010eba  push    rsi
0x180010ebb  push    rdi
0x180010ebc  sub     rsp, 850h
0x180010ec3  mov     rax, cs:__security_cookie
0x180010eca  xor     rax, rsp
0x180010ecd  mov     [rsp+868h+var_28], rax
0x180010ed5  movsxd  rdi, r8d
0x180010ed8  mov     rbp, rdx
0x180010edb  mov     rbx, rcx
0x180010ede  mov     [rsp+868h+var_838], 0
0x180010ee7  lea     rdx, DebugInfoEvent
0x180010eee  mov     rcx, cs:eaphost_Context
0x180010ef5  call    cs:__imp_EtwEventEnabled
0x180010efb  test    al, al
0x180010efd  jz      short loc_180010F3E
0x180010eff  mov     r9d, [rbp+0Ch]
0x180010f03  lea     r8, aStartinANewEap; " Startin a new Eap3Host process for the"...
0x180010f0a  mov     edx, 800h; unsigned __int64
0x180010f0f  lea     rcx, [rsp+868h+var_828]; char *
0x180010f14  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180010f19  test    eax, eax
0x180010f1b  js      short loc_180010F3E
0x180010f1d  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180010f24  jge     short loc_180010F3E
0x180010f26  lea     r8, [rsp+868h+var_828]
0x180010f2b  lea     rdx, DebugInfoEvent
0x180010f32  lea     rcx, eaphost_Context
0x180010f39  call    McTemplateU0s_EtwEventWriteTransfer
0x180010f3e  lea     rax, WPP_GLOBAL_Control
0x180010f45  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f4c  cmp     rcx, rax
0x180010f4f  jz      short loc_180010F6C
0x180010f51  test    byte ptr [rcx+1Ch], 4
0x180010f55  jz      short loc_180010F6C
0x180010f57  mov     edx, 0Fh
0x180010f5c  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x180010f63  mov     rcx, [rcx+10h]
0x180010f67  call    WPP_SF_
0x180010f6c  mov     rsi, rdi
0x180010f6f  lea     rdi, [rdi+rdi*2]
0x180010f73  mov     eax, [rbp+0Ch]
0x180010f76  mov     [rbx+rdi*8+0A0h], eax
0x180010f7d  lea     rax, [rbx+0A8h]
0x180010f84  lea     rax, [rax+rdi*8]
0x180010f88  mov     [rsp+868h+ppv], rax; ppv
0x180010f8d  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180010f94  xor     r8d, r8d; pvReserved
0x180010f97  mov     edx, 10004h; dwClsContext
0x180010f9c  lea     rcx, _GUID_87bb326b_e4a0_4de1_94f0_b9f41d0c6059; rclsid
0x180010fa3  call    cs:__imp_CoGetClassObject
0x180010fa9  test    eax, eax
0x180010fab  js      loc_180011040
0x180010fb1  lea     rax, [rsi+rsi*2]
0x180010fb5  mov     rcx, [rbx+rax*8+0A8h]
0x180010fbd  mov     rax, [rcx]
0x180010fc0  lea     r9, [rsp+868h+var_838]
0x180010fc5  lea     r8, _GUID_c48ca462_67fb_4c12_a21a_6415460fa8ae
0x180010fcc  xor     edx, edx
0x180010fce  mov     rax, [rax+18h]
0x180010fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fd7  mov     esi, eax
0x180010fd9  test    eax, eax
0x180010fdb  js      short loc_180011022
0x180010fdd  mov     rax, [rsp+868h+var_838]
0x180010fe2  mov     [rsp+868h+var_838], 0
0x180010feb  mov     [rbx+rdi*8+0B0h], rax
0x180010ff3  lea     rcx, [rsp+868h+var_838]
0x180010ff8  call    ?Release@?$ComPointer@UIUnknown@@@@AEAAXXZ; ComPointer<IUnknown>::Release(void)
0x180010ffd  mov     eax, esi
0x180010fff  mov     rcx, [rsp+868h+var_28]
0x180011007  xor     rcx, rsp; StackCookie
0x18001100a  call    __security_check_cookie
0x18001100f  mov     rbx, [rsp+868h+arg_18]
0x180011017  add     rsp, 850h
0x18001101e  pop     rdi
0x18001101f  pop     rsi
0x180011020  pop     rbp
0x180011021  retn
0x180011022  call    cs:__imp_GetLastError
0x180011028  nop
0x180011029  mov     r8d, eax; int
0x18001102c  lea     rdx, aComError; "COM Error"
0x180011033  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x18001103a  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180011040  call    cs:__imp_GetLastError
0x180011046  mov     r8d, eax; int
0x180011049  lea     rdx, aComError; "COM Error"
0x180011050  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x180011057  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
```
