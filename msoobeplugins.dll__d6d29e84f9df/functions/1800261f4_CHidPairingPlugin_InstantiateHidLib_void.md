# CHidPairingPlugin::_InstantiateHidLib(void)

- ea: `0x1800261f4`
- end: `0x180026384`
- name: `?_InstantiateHidLib@CHidPairingPlugin@@AEAAJXZ`
- size: `400`
- prototype: `__int64 __fastcall(CHidPairingPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800258f0`

## callees

- `0x180003470`
- `0x1800098cc`
- `0x18001ad08`
- `0x1800261f4`
- `0x1800af2f8`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026271`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026271`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800262de`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800262de`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800262b7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800262b7`

## string_xrefs

- `0x180026297`: `Found HidPairing Test Hook.  Using mock IHidPairing (CLSID %s)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CHidPairingPlugin::_InstantiateHidLib(CHidPairingPlugin *this)
{
  LPVOID *v2; // rsi
  LSTATUS ValueW; // eax
  bool v4; // sf
  HRESULT Instance; // ebx
  int v6; // r14d
  _DWORD *v7; // rdi
  DWORD pcbData[4]; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[264]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = (LPVOID *)((char *)this + 40);
  SafeRelease<IOOBETimeZoneItem>((char *)this + 40);
  pcbData[0] = 520;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\TestHooks",
             L"TestHidLibGUID",
             2u,
             0,
             sz,
             pcbData);
  v4 = ValueW < 0;
  if ( ValueW )
  {
    sz[0] = 0;
    v4 = ValueW < 0;
    if ( ValueW > 0 )
      v4 = 1;
  }
  if ( v4 )
  {
    v6 = *((_DWORD *)this + 18);
    *(_QWORD *)pcbData = 0;
    *v2 = 0;
    Instance = ATL::CComObject<CHidPairing>::CreateInstance(pcbData);
    if ( Instance >= 0 )
    {
      v7 = *(_DWORD **)pcbData;
      if ( *(_QWORD *)pcbData )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcbData + 8LL))(*(_QWORD *)pcbData);
      v7[49] = v6;
      *(_QWORD *)pcbData = 0;
      *v2 = v7;
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(pcbData);
    }
  }
  else
  {
    UnattendLogW(0, L"Found HidPairing Test Hook.  Using mock IHidPairing (CLSID %s)", sz);
    *(_OWORD *)pcbData = 0;
    Instance = CLSIDFromString(sz, (LPCLSID)pcbData);
    if ( Instance < 0 )
    {
LABEL_12:
      UnattendLogW(1, L"Failed to instantiate IHidPairing [hr=0x%08X]", (unsigned int)Instance);
      return (unsigned int)Instance;
    }
    Instance = CoCreateInstance((const IID *const)pcbData, 0, 1u, &GUID_0916b3b8_bf60_4867_8b22_d0a102a0bea2, v2);
  }
  if ( Instance < 0 )
    goto LABEL_12;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800261f4  mov     [rsp-8+arg_8], rbx
0x1800261f9  mov     [rsp-8+arg_10], rsi
0x1800261fe  push    rbp
0x1800261ff  push    rdi
0x180026200  push    r14
0x180026202  lea     rbp, [rsp-170h]
0x18002620a  sub     rsp, 270h
0x180026211  mov     rax, cs:__security_cookie
0x180026218  xor     rax, rsp
0x18002621b  mov     [rbp+180h+var_20], rax
0x180026222  mov     r14, rcx
0x180026225  lea     rsi, [rcx+28h]
0x180026229  mov     rcx, rsi
0x18002622c  call    ??$SafeRelease@UIOOBETimeZoneItem@@@@YAXPEAPEAUIOOBETimeZoneItem@@@Z; SafeRelease<IOOBETimeZoneItem>(IOOBETimeZoneItem * *)
0x180026231  mov     [rsp+280h+var_240], 208h
0x180026239  lea     rax, [rsp+280h+var_240]
0x18002623e  mov     [rsp+280h+pcbData], rax; pcbData
0x180026243  lea     rax, [rsp+280h+sz]
0x180026248  mov     [rsp+280h+pvData], rax; pvData
0x18002624d  mov     [rsp+280h+pdwType], 0; pdwType
0x180026256  mov     r9d, 2; dwFlags
0x18002625c  lea     r8, aTesthidlibguid; "TestHidLibGUID"
0x180026263  lea     rdx, aSoftwareMicros_39; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002626a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180026271  call    cs:__imp_RegGetValueW
0x180026277  test    eax, eax
0x180026279  jz      short loc_180026290
0x18002627b  xor     ecx, ecx
0x18002627d  mov     [rsp+280h+sz], cx
0x180026282  test    eax, eax
0x180026284  jle     short loc_180026290
0x180026286  movzx   eax, ax
0x180026289  or      eax, 80070000h
0x18002628e  test    eax, eax
0x180026290  js      short loc_1800262E8
0x180026292  lea     r8, [rsp+280h+sz]
0x180026297  lea     rdx, aFoundHidpairin; "Found HidPairing Test Hook.  Using mock"...
0x18002629e  xor     ecx, ecx
0x1800262a0  call    UnattendLogW
0x1800262a5  xorps   xmm0, xmm0
0x1800262a8  movups  xmmword ptr [rsp+280h+var_240], xmm0
0x1800262ad  lea     rdx, [rsp+280h+var_240]; pclsid
0x1800262b2  lea     rcx, [rsp+280h+sz]; lpsz
0x1800262b7  call    cs:__imp_CLSIDFromString
0x1800262bd  mov     ebx, eax
0x1800262bf  test    eax, eax
0x1800262c1  js      loc_180026347
0x1800262c7  mov     [rsp+280h+pdwType], rsi; ppv
0x1800262cc  lea     r9, _GUID_0916b3b8_bf60_4867_8b22_d0a102a0bea2; riid
0x1800262d3  xor     edx, edx; pUnkOuter
0x1800262d5  lea     r8d, [rdx+1]; dwClsContext
0x1800262d9  lea     rcx, [rsp+280h+var_240]; rclsid
0x1800262de  call    cs:__imp_CoCreateInstance
0x1800262e4  mov     ebx, eax
0x1800262e6  jmp     short loc_180026343
0x1800262e8  mov     r14d, [r14+48h]
0x1800262ec  mov     qword ptr [rsp+280h+var_240], 0
0x1800262f5  mov     qword ptr [rsi], 0
0x1800262fc  lea     rcx, [rsp+280h+var_240]
0x180026301  call    ?CreateInstance@?$CComObject@VCHidPairing@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CHidPairing>::CreateInstance(ATL::CComObject<CHidPairing> * *)
0x180026306  mov     ebx, eax
0x180026308  test    eax, eax
0x18002630a  js      short loc_180026343
0x18002630c  mov     rdi, qword ptr [rsp+280h+var_240]
0x180026311  test    rdi, rdi
0x180026314  jz      short loc_180026326
0x180026316  mov     rax, [rdi]
0x180026319  mov     rcx, rdi
0x18002631c  mov     rax, [rax+8]
0x180026320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026325  nop
0x180026326  mov     [rdi+0C4h], r14d
0x18002632d  mov     qword ptr [rsp+280h+var_240], 0
0x180026336  mov     [rsi], rdi
0x180026339  lea     rcx, [rsp+280h+var_240]
0x18002633e  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180026343  test    ebx, ebx
0x180026345  jns     short loc_18002635B
0x180026347  mov     r8d, ebx
0x18002634a  lea     rdx, aFailedToInstan; "Failed to instantiate IHidPairing [hr=0"...
0x180026351  mov     ecx, 1
0x180026356  call    UnattendLogW
0x18002635b  mov     eax, ebx
0x18002635d  mov     rcx, [rbp+180h+var_20]
0x180026364  xor     rcx, rsp; StackCookie
0x180026367  call    __security_check_cookie
0x18002636c  lea     r11, [rsp+280h+var_10]
0x180026374  mov     rbx, [r11+28h]
0x180026378  mov     rsi, [r11+30h]
0x18002637c  mov     rsp, r11
0x18002637f  pop     r14
0x180026381  pop     rdi
0x180026382  pop     rbp
0x180026383  retn
```
