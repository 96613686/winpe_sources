# GetPolicyUpdatedAccountId(ushort * *)

- ea: `0x180011724`
- end: `0x1800118ef`
- name: `?GetPolicyUpdatedAccountId@@YAJPEAPEAG@Z`
- size: `459`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18007586c`

## callees

- `0x1800071c0`
- `0x180011724`
- `0x1800118f8`
- `0x18001191c`
- `0x180011938`
- `0x18002e614`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011793`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011793`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011804`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001189c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011804`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001189c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800117c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800118df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800117c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800118df`

## string_xrefs

- `0x18001173b`: `onecoreuap\admin\enterprisemgmt\hvsi\hvsitasks.cpp`
- `0x1800117a6`: `onecoreuap\admin\enterprisemgmt\hvsi\hvsitasks.cpp`
- `0x18001184d`: `onecoreuap\admin\enterprisemgmt\hvsi\hvsitasks.cpp`
- `0x1800118aa`: `onecoreuap\admin\enterprisemgmt\hvsi\hvsitasks.cpp`
- `0x1800117d5`: `PolicyUpdatedAccountId_LastWrite`
- `0x18001187f`: `PolicyUpdatedAccountId_LastWrite`

## pseudocode

```c
__int64 __fastcall GetPolicyUpdatedAccountId(unsigned __int16 **a1)
{
  unsigned int v2; // ebx
  unsigned int ValueW; // eax
  __int64 v5; // rdx
  unsigned __int64 v6; // rax
  unsigned __int16 *v7; // rbx
  unsigned int v8; // eax
  int phkResult; // [rsp+20h] [rbp-20h]
  unsigned int phkResulta; // [rsp+20h] [rbp-20h]
  unsigned int phkResultb; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD pcbData; // [rsp+60h] [rbp+20h] BYREF
  DWORD pdwType; // [rsp+68h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int16 *pvData; // [rsp+78h] [rbp+38h] BYREF

  if ( !a1 )
  {
    v2 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\hvsi\\hvsitasks.cpp",
      (const char *)0x80004003LL,
      phkResult);
    return v2;
  }
  *a1 = 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\HVSICSP", 0, 0x20019u, &hKey);
  if ( ValueW )
  {
    v5 = 81;
LABEL_6:
    v2 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v5,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\hvsi\\hvsitasks.cpp",
           (const char *)ValueW,
           phkResulta);
    goto LABEL_7;
  }
  pdwType = 1;
  pcbData = 0;
  ValueW = RegGetValueW(hKey, 0, L"PolicyUpdatedAccountId_LastWrite", 2u, &pdwType, 0, &pcbData);
  if ( ValueW )
  {
    v5 = 86;
    goto LABEL_6;
  }
  v6 = 2 * ((unsigned __int64)pcbData >> 1);
  if ( !is_mul_ok((unsigned __int64)pcbData >> 1, 2u) )
    v6 = -1;
  pvData = (unsigned __int16 *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  v7 = pvData;
  if ( !pvData )
  {
    v2 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\hvsi\\hvsitasks.cpp",
      (const char *)0x8007000ELL,
      phkResulta);
LABEL_15:
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)&pvData);
LABEL_7:
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  v8 = RegGetValueW(hKey, 0, L"PolicyUpdatedAccountId_LastWrite", 2u, &pdwType, pvData, &pcbData);
  if ( v8 )
  {
    v2 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x5B,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\hvsi\\hvsitasks.cpp",
           (const char *)v8,
           phkResultb);
    goto LABEL_15;
  }
  pvData = 0;
  *a1 = v7;
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)&pvData);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180011724  push    rbp
0x180011726  push    rbx
0x180011727  push    rdi
0x180011728  mov     rbp, rsp
0x18001172b  sub     rsp, 40h
0x18001172f  mov     rdi, rcx
0x180011732  test    rcx, rcx
0x180011735  jnz     short loc_180011759
0x180011737  mov     rcx, [rbp+18h]; this
0x18001173b  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\hvsi"...
0x180011742  mov     ebx, 80004003h
0x180011747  lea     edx, [rdi+4Bh]; void *
0x18001174a  mov     r9d, ebx; char *
0x18001174d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011752  mov     eax, ebx
0x180011754  jmp     loc_1800118E7
0x180011759  mov     qword ptr [rcx], 0
0x180011760  xor     edx, edx
0x180011762  lea     rcx, [rbp+hKey]
0x180011766  mov     [rbp+hKey], 0
0x18001176e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180011773  lea     rax, [rbp+hKey]
0x180011777  mov     r9d, 20019h; samDesired
0x18001177d  xor     r8d, r8d; ulOptions
0x180011780  mov     [rsp+40h+phkResult], rax; unsigned int
0x180011785  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\HVSICSP"
0x18001178c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011793  call    cs:__imp_RegOpenKeyExW
0x180011799  test    eax, eax
0x18001179b  jz      short loc_1800117C8
0x18001179d  mov     edx, 51h ; 'Q'; void *
0x1800117a2  mov     rcx, [rbp+18h]; this
0x1800117a6  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\hvsi"...
0x1800117ad  mov     r9d, eax; char *
0x1800117b0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800117b5  mov     ebx, eax
0x1800117b7  mov     rcx, [rbp+hKey]; hKey
0x1800117bb  test    rcx, rcx
0x1800117be  jz      short loc_180011752
0x1800117c0  call    cs:__imp_RegCloseKey
0x1800117c6  jmp     short loc_180011752
0x1800117c8  mov     rcx, [rbp+hKey]; hkey
0x1800117cc  lea     rax, [rbp+arg_0]
0x1800117d0  mov     [rsp+40h+pcbData], rax; pcbData
0x1800117d5  lea     r8, aPolicyupdateda; "PolicyUpdatedAccountId_LastWrite"
0x1800117dc  lea     rax, [rbp+pdwType]
0x1800117e0  mov     [rsp+40h+pvData], 0; pvData
0x1800117e9  mov     r9d, 2; dwFlags
0x1800117ef  mov     [rsp+40h+phkResult], rax; int
0x1800117f4  xor     edx, edx; lpSubKey
0x1800117f6  mov     [rbp+pdwType], 1
0x1800117fd  mov     [rbp+arg_0], 0
0x180011804  call    cs:__imp_RegGetValueW
0x18001180a  test    eax, eax
0x18001180c  jz      short loc_180011815
0x18001180e  mov     edx, 56h ; 'V'
0x180011813  jmp     short loc_1800117A2
0x180011815  mov     ecx, [rbp+arg_0]
0x180011818  mov     eax, 2
0x18001181d  shr     rcx, 1
0x180011820  mul     rcx
0x180011823  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001182a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011831  cmovb   rax, rcx
0x180011835  mov     rcx, rax; unsigned __int64
0x180011838  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001183d  mov     [rbp+arg_18], rax
0x180011841  mov     rbx, rax
0x180011844  test    rax, rax
0x180011847  jnz     short loc_180011872
0x180011849  mov     rcx, [rbp+18h]; this
0x18001184d  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\hvsi"...
0x180011854  mov     ebx, 8007000Eh
0x180011859  lea     edx, [rax+59h]; void *
0x18001185c  mov     r9d, ebx; char *
0x18001185f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011864  lea     rcx, [rbp+arg_18]
0x180011868  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001186d  jmp     loc_1800117B7
0x180011872  mov     rcx, [rbp+hKey]; hkey
0x180011876  lea     rax, [rbp+arg_0]
0x18001187a  mov     [rsp+40h+pcbData], rax; pcbData
0x18001187f  lea     r8, aPolicyupdateda; "PolicyUpdatedAccountId_LastWrite"
0x180011886  lea     rax, [rbp+pdwType]
0x18001188a  mov     [rsp+40h+pvData], rbx; pvData
0x18001188f  mov     r9d, 2; dwFlags
0x180011895  mov     [rsp+40h+phkResult], rax; unsigned int
0x18001189a  xor     edx, edx; lpSubKey
0x18001189c  call    cs:__imp_RegGetValueW
0x1800118a2  test    eax, eax
0x1800118a4  jz      short loc_1800118C2
0x1800118a6  mov     rcx, [rbp+18h]; this
0x1800118aa  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\hvsi"...
0x1800118b1  mov     r9d, eax; char *
0x1800118b4  mov     edx, 5Bh ; '['; void *
0x1800118b9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800118be  mov     ebx, eax
0x1800118c0  jmp     short loc_180011864
0x1800118c2  lea     rcx, [rbp+arg_18]
0x1800118c6  mov     [rbp+arg_18], 0
0x1800118ce  mov     [rdi], rbx
0x1800118d1  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800118d6  mov     rcx, [rbp+hKey]; hKey
0x1800118da  test    rcx, rcx
0x1800118dd  jz      short loc_1800118E5
0x1800118df  call    cs:__imp_RegCloseKey
0x1800118e5  xor     eax, eax
0x1800118e7  add     rsp, 40h
0x1800118eb  pop     rdi
0x1800118ec  pop     rbx
0x1800118ed  pop     rbp
0x1800118ee  retn
```
