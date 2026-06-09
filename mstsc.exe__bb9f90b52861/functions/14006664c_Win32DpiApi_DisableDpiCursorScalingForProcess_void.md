# Win32DpiApi::DisableDpiCursorScalingForProcess(void)

- ea: `0x14006664c`
- end: `0x1400668b5`
- name: `?DisableDpiCursorScalingForProcess@Win32DpiApi@@QEAAXXZ`
- size: `617`
- prototype: `void __fastcall(Win32DpiApi *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14006590c`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400662e4`
- `0x14006664c`
- `0x140114010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x14006667d`
- `KERNEL32!LoadLibraryExW` at `0x14006667d`
- `KERNEL32!GetProcAddress` at `0x1400666f6`
- `KERNEL32!GetProcAddress` at `0x1400666f6`
- `KERNEL32!GetLastError` at `0x14006668c`
- `KERNEL32!GetLastError` at `0x140066701`
- `KERNEL32!GetLastError` at `0x14006668c`
- `KERNEL32!GetLastError` at `0x140066701`

## string_xrefs

- `0x140066676`: `mstscax.dll`
- `0x1400666ec`: `DllGetClassObject`
- `0x140066792`: `DllGetClassObject failed`
- `0x1400667f2`: `CreateInstance failed`

## pseudocode

```c
void __fastcall Win32DpiApi::DisableDpiCursorScalingForProcess(Win32DpiApi *this)
{
  HMODULE Library; // rax
  DWORD LastError; // ebx
  unsigned int v3; // eax
  __int64 v4; // rdx
  FARPROC ProcAddress; // rax
  int v6; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v8; // edx
  const char *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // [rsp+40h] [rbp+10h] BYREF
  __int64 v13; // [rsp+48h] [rbp+18h] BYREF
  HMODULE v14; // [rsp+50h] [rbp+20h] BYREF

  v13 = 0;
  v12 = 0;
  Library = LoadLibraryExW(L"mstscax.dll", 0, 0x200u);
  v14 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "DllGetClassObject");
    if ( ProcAddress )
    {
      v6 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
             &CLSID_MsRdpClient11NotSafeForScripting,
             &GUID_00000001_0000_0000_c000_000000000046,
             &v13);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v13 + 24LL))(
               v13,
               0,
               &GUID_71b4a60a_fe21_46d8_a39b_8e32ba0c5ecc,
               &v12);
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 544LL))(v12);
          if ( v6 >= 0
            || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_28;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v8 = 38;
          v9 = "IMsRdpClientNonScriptable7::DisableDpiCursorScalingForProcess failed";
        }
        else
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_28;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v8 = 37;
          v9 = "CreateInstance failed";
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_28;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 36;
        v9 = "DllGetClassObject failed";
      }
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        (unsigned int)WPP_35628b70d5363a316590e8499969a27c_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v9,
        v6);
      goto LABEL_28;
    }
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = RdpWppGetCurrentThreadActivityIdPrefix();
      v4 = 35;
      goto LABEL_6;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = RdpWppGetCurrentThreadActivityIdPrefix();
      v4 = 34;
LABEL_6:
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, WPP_35628b70d5363a316590e8499969a27c_Traceguids, v3, LastError);
    }
  }
LABEL_28:
  v10 = v12;
  if ( v12 )
  {
    v12 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = v13;
  if ( v13 )
  {
    v13 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v14);
}

```

## disassembly

```asm
0x14006664c  mov     [rsp-8+arg_18], rbx
0x140066651  mov     [rsp-8+arg_0], rcx
0x140066656  push    rbp
0x140066657  mov     rbp, rsp
0x14006665a  sub     rsp, 30h
0x14006665e  xor     edx, edx; hFile
0x140066660  mov     [rbp+arg_8], 0
0x140066668  mov     r8d, 200h; dwFlags
0x14006666e  mov     [rbp+arg_0], 0
0x140066676  lea     rcx, tstrFilename; "mstscax.dll"
0x14006667d  call    cs:__imp_LoadLibraryExW
0x140066683  mov     [rbp+arg_10], rax
0x140066687  test    rax, rax
0x14006668a  jnz     short loc_1400666EC
0x14006668c  call    cs:__imp_GetLastError
0x140066692  mov     ebx, eax
0x140066694  mov     rdx, cs:WPP_GLOBAL_Control
0x14006669b  lea     rcx, WPP_GLOBAL_Control
0x1400666a2  cmp     rdx, rcx
0x1400666a5  jz      loc_140066867
0x1400666ab  test    byte ptr [rdx+1Ch], 8
0x1400666af  jz      loc_140066867
0x1400666b5  cmp     byte ptr [rdx+19h], 2
0x1400666b9  jb      loc_140066867
0x1400666bf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400666c4  mov     edx, 22h ; '"'
0x1400666c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400666d0  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x1400666d7  mov     r9d, eax
0x1400666da  mov     dword ptr [rsp+30h+var_10], ebx
0x1400666de  mov     rcx, [rcx+10h]
0x1400666e2  call    WPP_SF_Dd
0x1400666e7  jmp     loc_140066867
0x1400666ec  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x1400666f3  mov     rcx, rax; hModule
0x1400666f6  call    cs:__imp_GetProcAddress
0x1400666fc  test    rax, rax
0x1400666ff  jnz     short loc_140066740
0x140066701  call    cs:__imp_GetLastError
0x140066707  mov     ebx, eax
0x140066709  mov     rdx, cs:WPP_GLOBAL_Control
0x140066710  lea     rcx, WPP_GLOBAL_Control
0x140066717  cmp     rdx, rcx
0x14006671a  jz      loc_140066867
0x140066720  test    byte ptr [rdx+1Ch], 8
0x140066724  jz      loc_140066867
0x14006672a  cmp     byte ptr [rdx+19h], 2
0x14006672e  jb      loc_140066867
0x140066734  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066739  mov     edx, 23h ; '#'
0x14006673e  jmp     short loc_1400666C9
0x140066740  lea     r8, [rbp+arg_8]
0x140066744  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x14006674b  lea     rcx, CLSID_MsRdpClient11NotSafeForScripting
0x140066752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066757  mov     ebx, eax
0x140066759  test    eax, eax
0x14006675b  jns     short loc_14006679E
0x14006675d  mov     rdx, cs:WPP_GLOBAL_Control
0x140066764  lea     rcx, WPP_GLOBAL_Control
0x14006676b  cmp     rdx, rcx
0x14006676e  jz      loc_140066867
0x140066774  test    byte ptr [rdx+1Ch], 8
0x140066778  jz      loc_140066867
0x14006677e  cmp     byte ptr [rdx+19h], 2
0x140066782  jb      loc_140066867
0x140066788  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006678d  mov     edx, 24h ; '$'
0x140066792  lea     rcx, aDllgetclassobj_0; "DllGetClassObject failed"
0x140066799  jmp     loc_140066844
0x14006679e  mov     rcx, [rbp+arg_8]
0x1400667a2  lea     r9, [rbp+arg_0]
0x1400667a6  lea     r8, _GUID_71b4a60a_fe21_46d8_a39b_8e32ba0c5ecc
0x1400667ad  xor     edx, edx
0x1400667af  mov     rax, [rcx]
0x1400667b2  mov     rax, [rax+18h]
0x1400667b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400667bb  mov     ebx, eax
0x1400667bd  test    eax, eax
0x1400667bf  jns     short loc_1400667FB
0x1400667c1  mov     rdx, cs:WPP_GLOBAL_Control
0x1400667c8  lea     rcx, WPP_GLOBAL_Control
0x1400667cf  cmp     rdx, rcx
0x1400667d2  jz      loc_140066867
0x1400667d8  test    byte ptr [rdx+1Ch], 8
0x1400667dc  jz      loc_140066867
0x1400667e2  cmp     byte ptr [rdx+19h], 2
0x1400667e6  jb      short loc_140066867
0x1400667e8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400667ed  mov     edx, 25h ; '%'
0x1400667f2  lea     rcx, aCreateinstance_2; "CreateInstance failed"
0x1400667f9  jmp     short loc_140066844
0x1400667fb  mov     rcx, [rbp+arg_0]
0x1400667ff  mov     rax, [rcx]
0x140066802  mov     rax, [rax+220h]
0x140066809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006680e  mov     ebx, eax
0x140066810  test    eax, eax
0x140066812  jns     short loc_140066867
0x140066814  mov     rdx, cs:WPP_GLOBAL_Control
0x14006681b  lea     rcx, WPP_GLOBAL_Control
0x140066822  cmp     rdx, rcx
0x140066825  jz      short loc_140066867
0x140066827  test    byte ptr [rdx+1Ch], 8
0x14006682b  jz      short loc_140066867
0x14006682d  cmp     byte ptr [rdx+19h], 2
0x140066831  jb      short loc_140066867
0x140066833  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066838  mov     edx, 26h ; '&'
0x14006683d  lea     rcx, aImsrdpclientno; "IMsRdpClientNonScriptable7::DisableDpiC"...
0x140066844  mov     [rsp+30h+var_8], ebx
0x140066848  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x14006684f  mov     [rsp+30h+var_10], rcx
0x140066854  mov     r9d, eax
0x140066857  mov     rcx, cs:WPP_GLOBAL_Control
0x14006685e  mov     rcx, [rcx+10h]
0x140066862  call    WPP_SF_DsD
0x140066867  mov     rcx, [rbp+arg_0]
0x14006686b  test    rcx, rcx
0x14006686e  jz      short loc_140066884
0x140066870  mov     [rbp+arg_0], 0
0x140066878  mov     rax, [rcx]
0x14006687b  mov     rax, [rax+10h]
0x14006687f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066884  mov     rcx, [rbp+arg_8]
0x140066888  test    rcx, rcx
0x14006688b  jz      short loc_1400668A1
0x14006688d  mov     [rbp+arg_8], 0
0x140066895  mov     rax, [rcx]
0x140066898  mov     rax, [rax+10h]
0x14006689c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400668a1  lea     rcx, [rbp+arg_10]
0x1400668a5  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1400668aa  mov     rbx, [rsp+30h+arg_18]
0x1400668af  add     rsp, 30h
0x1400668b3  pop     rbp
0x1400668b4  retn
```
