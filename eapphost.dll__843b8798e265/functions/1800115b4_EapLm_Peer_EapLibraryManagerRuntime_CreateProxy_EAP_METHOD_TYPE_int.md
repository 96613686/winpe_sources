# EapLm::Peer::EapLibraryManagerRuntime::CreateProxy(_EAP_METHOD_TYPE,int)

- ea: `0x1800115b4`
- end: `0x180011776`
- name: `?CreateProxy@EapLibraryManagerRuntime@Peer@EapLm@@QEAAJU_EAP_METHOD_TYPE@@H@Z`
- size: `450`
- prototype: `__int64 __fastcall(EapLm::Peer::EapLibraryManagerRuntime *__hidden this, struct _EAP_METHOD_TYPE *__struct_ptr, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001177c`

## callees

- `0x180002af0`
- `0x180004d1c`
- `0x18000a21c`
- `0x1800115b4`
- `0x180011cb8`
- `0x1800120c4`
- `0x18001e7c0`
- `0x180039010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800115f5`
- `ntdll!EtwEventEnabled` at `0x1800115f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001172f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001172f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011753`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800116a9`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800116a9`

## string_xrefs

- `0x18001173f`: `COM Error`
- `0x180011762`: `COM Error`
- `0x180011746`: `Create Third Party Proxy`
- `0x180011769`: `Create Third Party Proxy`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800115b4  mov     [rsp+arg_18], rbx
0x1800115b9  push    rbp
0x1800115ba  push    rsi
0x1800115bb  push    rdi
0x1800115bc  sub     rsp, 850h
0x1800115c3  mov     rax, cs:__security_cookie
0x1800115ca  xor     rax, rsp
0x1800115cd  mov     [rsp+868h+var_28], rax
0x1800115d5  movsxd  rdi, r8d
0x1800115d8  mov     rbp, rdx
0x1800115db  mov     rbx, rcx
0x1800115de  mov     [rsp+868h+var_838], 0
0x1800115e7  lea     rdx, DebugInfoEvent
0x1800115ee  mov     rcx, cs:eaphost_Context
0x1800115f5  call    cs:__imp_EtwEventEnabled
0x1800115fc  nop     dword ptr [rax+rax+00h]
0x180011601  test    al, al
0x180011603  jz      short loc_180011644
0x180011605  mov     r9d, [rbp+0Ch]
0x180011609  lea     r8, aStartinANewEap; " Startin a new Eap3Host process for the"...
0x180011610  mov     edx, 800h; unsigned __int64
0x180011615  lea     rcx, [rsp+868h+var_828]; char *
0x18001161a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001161f  test    eax, eax
0x180011621  js      short loc_180011644
0x180011623  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001162a  jge     short loc_180011644
0x18001162c  lea     r8, [rsp+868h+var_828]
0x180011631  lea     rdx, DebugInfoEvent
0x180011638  lea     rcx, eaphost_Context
0x18001163f  call    McTemplateU0s_EtwEventWriteTransfer
0x180011644  lea     rax, WPP_GLOBAL_Control
0x18001164b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011652  cmp     rcx, rax
0x180011655  jz      short loc_180011672
0x180011657  test    byte ptr [rcx+1Ch], 4
0x18001165b  jz      short loc_180011672
0x18001165d  mov     edx, 0Fh
0x180011662  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x180011669  mov     rcx, [rcx+10h]
0x18001166d  call    WPP_SF_
0x180011672  mov     rsi, rdi
0x180011675  lea     rdi, [rdi+rdi*2]
0x180011679  mov     eax, [rbp+0Ch]
0x18001167c  mov     [rbx+rdi*8+0A0h], eax
0x180011683  lea     rax, [rbx+0A8h]
0x18001168a  lea     rax, [rax+rdi*8]
0x18001168e  mov     [rsp+868h+ppv], rax; ppv
0x180011693  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18001169a  xor     r8d, r8d; pvReserved
0x18001169d  mov     edx, 10004h; dwClsContext
0x1800116a2  lea     rcx, _GUID_87bb326b_e4a0_4de1_94f0_b9f41d0c6059; rclsid
0x1800116a9  call    cs:__imp_CoGetClassObject
0x1800116b0  nop     dword ptr [rax+rax+00h]
0x1800116b5  test    eax, eax
0x1800116b7  js      loc_180011753
0x1800116bd  lea     rax, [rsi+rsi*2]
0x1800116c1  mov     rcx, [rbx+rax*8+0A8h]
0x1800116c9  mov     rax, [rcx]
0x1800116cc  lea     r9, [rsp+868h+var_838]
0x1800116d1  lea     r8, _GUID_c48ca462_67fb_4c12_a21a_6415460fa8ae
0x1800116d8  xor     edx, edx
0x1800116da  mov     rax, [rax+18h]
0x1800116de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116e3  mov     esi, eax
0x1800116e5  test    eax, eax
0x1800116e7  js      short loc_18001172F
0x1800116e9  mov     rax, [rsp+868h+var_838]
0x1800116ee  mov     [rsp+868h+var_838], 0
0x1800116f7  mov     [rbx+rdi*8+0B0h], rax
0x1800116ff  lea     rcx, [rsp+868h+var_838]
0x180011704  call    ?Release@?$ComPointer@UIUnknown@@@@AEAAXXZ; ComPointer<IUnknown>::Release(void)
0x180011709  mov     eax, esi
0x18001170b  mov     rcx, [rsp+868h+var_28]
0x180011713  xor     rcx, rsp; StackCookie
0x180011716  call    __security_check_cookie
0x18001171b  mov     rbx, [rsp+868h+arg_18]
0x180011723  add     rsp, 850h
0x18001172a  pop     rdi
0x18001172b  pop     rsi
0x18001172c  pop     rbp
0x18001172d  retn
0x18001172f  call    cs:__imp_GetLastError
0x180011736  nop     dword ptr [rax+rax+00h]
0x18001173b  nop
0x18001173c  mov     r8d, eax; int
0x18001173f  lea     rdx, aComError; "COM Error"
0x180011746  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x18001174d  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180011753  call    cs:__imp_GetLastError
0x18001175a  nop     dword ptr [rax+rax+00h]
0x18001175f  mov     r8d, eax; int
0x180011762  lea     rdx, aComError; "COM Error"
0x180011769  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x180011770  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
```
