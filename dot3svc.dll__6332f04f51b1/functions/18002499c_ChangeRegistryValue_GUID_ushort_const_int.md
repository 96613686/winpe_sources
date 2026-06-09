# ChangeRegistryValue(_GUID *,ushort const *,int)

- ea: `0x18002499c`
- end: `0x180024be7`
- name: `?ChangeRegistryValue@@YAJPEAU_GUID@@PEBGH@Z`
- size: `587`
- prototype: `__int64 __fastcall(struct _GUID *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18002489c`
- `0x18002491c`

## callees

- `0x1800025f0`
- `0x1800084ec`
- `0x18002485c`
- `0x18002487c`
- `0x18002499c`
- `0x180024c88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024b8c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024b8c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180024ad5`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180024b32`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180024ad5`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180024b32`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180024ac8`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180024ac8`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x180024b25`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x180024b25`
- `NetSetupApi!NetSetupGetObjectProperties` at `0x180024a4c`
- `NetSetupApi!NetSetupGetObjectProperties` at `0x180024a4c`
- `NetSetupApi!NetSetupInitialize` at `0x1800249db`
- `NetSetupApi!NetSetupInitialize` at `0x1800249db`
- `NetSetupApi!NetSetupFreeObjectProperties` at `0x180024aa9`
- `NetSetupApi!NetSetupFreeObjectProperties` at `0x180024bb0`
- `NetSetupApi!NetSetupFreeObjectProperties` at `0x180024aa9`
- `NetSetupApi!NetSetupFreeObjectProperties` at `0x180024bb0`

## pseudocode

```c
__int64 __fastcall ChangeRegistryValue(struct _GUID *a1, const unsigned __int16 *a2, int a3)
{
  int ObjectProperties; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rbx
  int v10; // esi
  CONFIGRET v11; // eax
  DWORD v12; // eax
  CONFIGRET v13; // eax
  DWORD v14; // eax
  __int64 v15; // rdx
  int phkDevice; // [rsp+20h] [rbp-49h]
  unsigned int phkDevicea; // [rsp+20h] [rbp-49h]
  DEVNODE pdnDevInst; // [rsp+44h] [rbp-25h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-21h] BYREF
  BYTE Data[8]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v22; // [rsp+58h] [rbp-11h] BYREF
  __int64 v23; // [rsp+60h] [rbp-9h]
  _OWORD v24[2]; // [rsp+70h] [rbp+7h] BYREF
  int v25; // [rsp+90h] [rbp+27h]
  __int64 v26; // [rsp+94h] [rbp+2Bh]
  int v27; // [rsp+9Ch] [rbp+33h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v22 = 0;
  ObjectProperties = NetSetupInitialize(0, &v22);
  v7 = ObjectProperties;
  if ( ObjectProperties < 0 )
  {
    v8 = 24;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\net\\dot3\\ac\\server\\ndisport.cpp",
      (const char *)(unsigned int)ObjectProperties,
      phkDevice);
    goto LABEL_21;
  }
  v25 = 50;
  v26 = 0;
  v27 = 0;
  v23 = 0;
  v24[1] = NETSETUPPKEY_Interface_PnpInstance;
  phkDevice = 1;
  v24[0] = *a1;
  ObjectProperties = NetSetupGetObjectProperties(v22, 2, v24);
  v7 = ObjectProperties;
  if ( ObjectProperties < 0 )
  {
    v8 = 33;
    goto LABEL_5;
  }
  v9 = v23;
  if ( *(_DWORD *)(v23 + 32) != 18 )
  {
    v10 = -2147023728;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecoreuap\\net\\dot3\\ac\\server\\ndisport.cpp",
      (const char *)0x80070490LL,
      1);
LABEL_8:
    if ( v9 )
      NetSetupFreeObjectProperties(0, v9);
    v7 = v10;
    goto LABEL_21;
  }
  pdnDevInst = 0;
  v11 = CM_Locate_DevNodeW(&pdnDevInst, *(DEVINSTID_W *)(v23 + 40), 0);
  v12 = CM_MapCrToWin32Err(v11, 0x490u);
  if ( v12 )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x2E,
            (unsigned int)"onecoreuap\\net\\dot3\\ac\\server\\ndisport.cpp",
            (const char *)v12,
            1u);
    goto LABEL_8;
  }
  hKey = 0;
  v13 = CM_Open_DevNode_Key(pdnDevInst, 0x20006u, 0, 1u, &hKey, 1u);
  v14 = CM_MapCrToWin32Err(v13, 0x490u);
  if ( v14 )
  {
    v15 = 50;
LABEL_15:
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v15,
            (unsigned int)"onecoreuap\\net\\dot3\\ac\\server\\ndisport.cpp",
            (const char *)v14,
            phkDevicea);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_8;
  }
  *(_DWORD *)Data = 2 - (a3 != 0);
  v14 = RegSetValueExW(hKey, a2, 0, 4u, Data, 4u);
  if ( v14 )
  {
    v15 = 53;
    goto LABEL_15;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  if ( v9 )
    NetSetupFreeObjectProperties(0, v9);
  v7 = 0;
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<HNETSETUP__ *,void (*)(HNETSETUP__ *),&void NetSetupClose(HNETSETUP__ *),wistd::integral_constant<unsigned __int64,0>,HNETSETUP__ *,HNETSETUP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HNETSETUP__ *,void (*)(HNETSETUP__ *),&void NetSetupClose(HNETSETUP__ *),wistd::integral_constant<unsigned __int64,0>,HNETSETUP__ *,HNETSETUP__ *,0,std::nullptr_t>>(&v22);
  return v7;
}

```

## disassembly

```asm
0x18002499c  mov     [rsp-8+arg_10], rbx
0x1800249a1  mov     [rsp-8+arg_18], rsi
0x1800249a6  push    rbp
0x1800249a7  push    rdi
0x1800249a8  push    r14
0x1800249aa  lea     rbp, [rsp-47h]
0x1800249af  sub     rsp, 0B0h
0x1800249b6  mov     rax, cs:__security_cookie
0x1800249bd  xor     rax, rsp
0x1800249c0  mov     [rbp+57h+var_20], rax
0x1800249c4  mov     r14, rdx
0x1800249c7  mov     [rbp+57h+var_68], 0
0x1800249cf  mov     rdi, rcx
0x1800249d2  lea     rdx, [rbp+57h+var_68]
0x1800249d6  xor     ecx, ecx
0x1800249d8  mov     esi, r8d
0x1800249db  call    cs:__imp_NetSetupInitialize
0x1800249e1  mov     ebx, eax
0x1800249e3  test    eax, eax
0x1800249e5  jns     short loc_1800249EE
0x1800249e7  mov     edx, 18h
0x1800249ec  jmp     short loc_180024A5D
0x1800249ee  mov     eax, cs:dword_180045A88
0x1800249f4  lea     r8, [rbp+57h+var_50]
0x1800249f8  movups  xmm0, cs:NETSETUPPKEY_Interface_PnpInstance
0x1800249ff  mov     rcx, [rbp+57h+var_68]
0x180024a03  xor     r9d, r9d
0x180024a06  mov     [rbp+57h+var_30], eax
0x180024a09  xor     eax, eax
0x180024a0b  mov     [rbp+57h+var_2C], rax
0x180024a0f  mov     [rbp+57h+var_24], eax
0x180024a12  mov     [rbp+57h+var_80], eax
0x180024a15  lea     edx, [r9+2]
0x180024a19  mov     [rbp+57h+var_60], rax
0x180024a1d  lea     rax, [rbp+57h+var_60]
0x180024a21  mov     [rsp+0C0h+var_88], rax
0x180024a26  lea     rax, [rbp+57h+var_80]
0x180024a2a  mov     [rsp+0C0h+var_90], rax
0x180024a2f  lea     rax, [rbp+57h+var_40]
0x180024a33  movups  [rbp+57h+var_40], xmm0
0x180024a37  mov     qword ptr [rsp+0C0h+ulFlags], rax
0x180024a3c  movups  xmm0, xmmword ptr [rdi]
0x180024a3f  mov     dword ptr [rsp+0C0h+phkDevice], 1; unsigned int
0x180024a47  movdqu  [rbp+57h+var_50], xmm0
0x180024a4c  call    cs:__imp_NetSetupGetObjectProperties
0x180024a52  mov     ebx, eax
0x180024a54  test    eax, eax
0x180024a56  jns     short loc_180024A75
0x180024a58  mov     edx, 21h ; '!'; void *
0x180024a5d  mov     rcx, [rbp+5Fh]; this
0x180024a61  lea     r8, aOnecoreuapNetD; "onecoreuap\\net\\dot3\\ac\\server\\ndis"...
0x180024a68  mov     r9d, eax; char *
0x180024a6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024a70  jmp     loc_180024BB8
0x180024a75  mov     rbx, [rbp+57h+var_60]
0x180024a79  mov     edi, [rbp+57h+var_80]
0x180024a7c  cmp     dword ptr [rbx+20h], 12h
0x180024a80  jz      short loc_180024AB6
0x180024a82  mov     rcx, [rbp+5Fh]; this
0x180024a86  lea     r8, aOnecoreuapNetD; "onecoreuap\\net\\dot3\\ac\\server\\ndis"...
0x180024a8d  mov     esi, 80070490h
0x180024a92  mov     edx, 2Ah ; '*'; void *
0x180024a97  mov     r9d, esi; char *
0x180024a9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024a9f  test    rbx, rbx
0x180024aa2  jz      short loc_180024AAF
0x180024aa4  mov     rdx, rbx
0x180024aa7  mov     ecx, edi
0x180024aa9  call    cs:__imp_NetSetupFreeObjectProperties
0x180024aaf  mov     ebx, esi
0x180024ab1  jmp     loc_180024BB8
0x180024ab6  mov     [rbp+57h+pdnDevInst], 0
0x180024abd  lea     rcx, [rbp+57h+pdnDevInst]; pdnDevInst
0x180024ac1  mov     rdx, [rbx+28h]; pDeviceID
0x180024ac5  xor     r8d, r8d; ulFlags
0x180024ac8  call    cs:__imp_CM_Locate_DevNodeW
0x180024ace  mov     ecx, eax; CmReturnCode
0x180024ad0  mov     edx, 490h; DefaultErr
0x180024ad5  call    cs:__imp_CM_MapCrToWin32Err
0x180024adb  test    eax, eax
0x180024add  jz      short loc_180024AFB
0x180024adf  mov     rcx, [rbp+5Fh]; this
0x180024ae3  lea     r8, aOnecoreuapNetD; "onecoreuap\\net\\dot3\\ac\\server\\ndis"...
0x180024aea  mov     r9d, eax; char *
0x180024aed  mov     edx, 2Eh ; '.'; void *
0x180024af2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180024af7  mov     esi, eax
0x180024af9  jmp     short loc_180024A9F
0x180024afb  mov     ecx, [rbp+57h+pdnDevInst]; dnDevNode
0x180024afe  lea     rax, [rbp+57h+hKey]
0x180024b02  mov     [rsp+0C0h+ulFlags], 1; ulFlags
0x180024b0a  mov     r9d, 1; Disposition
0x180024b10  xor     r8d, r8d; ulHardwareProfile
0x180024b13  mov     [rsp+0C0h+phkDevice], rax; unsigned int
0x180024b18  mov     edx, 20006h; samDesired
0x180024b1d  mov     [rbp+57h+hKey], 0
0x180024b25  call    cs:__imp_CM_Open_DevNode_Key
0x180024b2b  mov     ecx, eax; CmReturnCode
0x180024b2d  mov     edx, 490h; DefaultErr
0x180024b32  call    cs:__imp_CM_MapCrToWin32Err
0x180024b38  test    eax, eax
0x180024b3a  jz      short loc_180024B64
0x180024b3c  mov     edx, 32h ; '2'; void *
0x180024b41  mov     rcx, [rbp+5Fh]; this
0x180024b45  lea     r8, aOnecoreuapNetD; "onecoreuap\\net\\dot3\\ac\\server\\ndis"...
0x180024b4c  mov     r9d, eax; char *
0x180024b4f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180024b54  lea     rcx, [rbp+57h+hKey]
0x180024b58  mov     esi, eax
0x180024b5a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180024b5f  jmp     loc_180024A9F
0x180024b64  mov     rcx, [rbp+57h+hKey]; hKey
0x180024b68  mov     r9d, 4; dwType
0x180024b6e  mov     [rsp+0C0h+ulFlags], r9d; cbData
0x180024b73  neg     esi
0x180024b75  mov     rdx, r14; lpValueName
0x180024b78  sbb     eax, eax
0x180024b7a  xor     r8d, r8d; Reserved
0x180024b7d  add     eax, 2
0x180024b80  mov     dword ptr [rbp+57h+Data], eax
0x180024b83  lea     rax, [rbp+57h+Data]
0x180024b87  mov     [rsp+0C0h+phkDevice], rax; lpData
0x180024b8c  call    cs:__imp_RegSetValueExW
0x180024b92  test    eax, eax
0x180024b94  jz      short loc_180024B9D
0x180024b96  mov     edx, 35h ; '5'
0x180024b9b  jmp     short loc_180024B41
0x180024b9d  lea     rcx, [rbp+57h+hKey]
0x180024ba1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180024ba6  test    rbx, rbx
0x180024ba9  jz      short loc_180024BB6
0x180024bab  mov     rdx, rbx
0x180024bae  mov     ecx, edi
0x180024bb0  call    cs:__imp_NetSetupFreeObjectProperties
0x180024bb6  xor     ebx, ebx
0x180024bb8  lea     rcx, [rbp+57h+var_68]
0x180024bbc  call    ??1?$unique_storage@U?$resource_policy@PEAUHNETSETUP__@@P6AXPEAU1@@Z$1?NetSetupClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HNETSETUP__ *,void (*)(HNETSETUP__ *),&NetSetupClose(HNETSETUP__ *),wistd::integral_constant<unsigned __int64,0>,HNETSETUP__ *,HNETSETUP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HNETSETUP__ *,void (*)(HNETSETUP__ *),&NetSetupClose(HNETSETUP__ *),wistd::integral_constant<unsigned __int64,0>,HNETSETUP__ *,HNETSETUP__ *,0,std::nullptr_t>>(void)
0x180024bc1  mov     eax, ebx
0x180024bc3  mov     rcx, [rbp+57h+var_20]
0x180024bc7  xor     rcx, rsp; StackCookie
0x180024bca  call    __security_check_cookie
0x180024bcf  lea     r11, [rsp+0C0h+var_10]
0x180024bd7  mov     rbx, [r11+30h]
0x180024bdb  mov     rsi, [r11+38h]
0x180024bdf  mov     rsp, r11
0x180024be2  pop     r14
0x180024be4  pop     rdi
0x180024be5  pop     rbp
0x180024be6  retn
```
