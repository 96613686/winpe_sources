# Win32DpiApi::DisableDpiCursorScalingForProcess(void)

- ea: `0x1400644dc`
- end: `0x140064745`
- name: `?DisableDpiCursorScalingForProcess@Win32DpiApi@@QEAAXXZ`
- size: `617`
- prototype: `void __fastcall(Win32DpiApi *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14006379c`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x140064174`
- `0x1400644dc`
- `0x140112010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x14006450d`
- `KERNEL32!LoadLibraryExW` at `0x14006450d`
- `KERNEL32!GetProcAddress` at `0x140064586`
- `KERNEL32!GetProcAddress` at `0x140064586`
- `KERNEL32!GetLastError` at `0x14006451c`
- `KERNEL32!GetLastError` at `0x140064591`
- `KERNEL32!GetLastError` at `0x14006451c`
- `KERNEL32!GetLastError` at `0x140064591`

## string_xrefs

- `0x140064506`: `mstscax.dll`
- `0x14006457c`: `DllGetClassObject`
- `0x140064622`: `DllGetClassObject failed`
- `0x140064682`: `CreateInstance failed`

## pseudocode

```c
void __fastcall Win32DpiApi::DisableDpiCursorScalingForProcess(Win32DpiApi *this)
{
  HMODULE Library; // rax
  DWORD LastError; // ebx
  unsigned int v3; // eax
  __int64 v4; // rdx
  FARPROC ProcAddress; // rax
  int v6; // eax
  char v7; // bl
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v9; // edx
  const char *v10; // rcx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // [rsp+40h] [rbp+10h] BYREF
  __int64 v16; // [rsp+48h] [rbp+18h] BYREF
  HMODULE v17; // [rsp+50h] [rbp+20h] BYREF

  v16 = 0;
  v15 = 0;
  Library = LoadLibraryExW(L"mstscax.dll", 0, 0x200u);
  v17 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "DllGetClassObject");
    if ( ProcAddress )
    {
      v6 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
             &CLSID_MsRdpClient11NotSafeForScripting,
             &GUID_00000001_0000_0000_c000_000000000046,
             &v16);
      v7 = v6;
      if ( v6 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v16 + 24LL))(
                v16,
                0,
                &GUID_71b4a60a_fe21_46d8_a39b_8e32ba0c5ecc,
                &v15);
        v7 = v11;
        if ( v11 >= 0 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 544LL))(v15);
          v7 = v12;
          if ( v12 >= 0
            || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_28;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v9 = 38;
          v10 = "IMsRdpClientNonScriptable7::DisableDpiCursorScalingForProcess failed";
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
          v9 = 37;
          v10 = "CreateInstance failed";
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
        v9 = 36;
        v10 = "DllGetClassObject failed";
      }
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        (unsigned int)WPP_35628b70d5363a316590e8499969a27c_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v10,
        v7);
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
  v13 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v17);
}

```

## disassembly

```asm
0x1400644dc  mov     [rsp-8+arg_18], rbx
0x1400644e1  mov     [rsp-8+arg_0], rcx
0x1400644e6  push    rbp
0x1400644e7  mov     rbp, rsp
0x1400644ea  sub     rsp, 30h
0x1400644ee  xor     edx, edx; hFile
0x1400644f0  mov     [rbp+arg_8], 0
0x1400644f8  mov     r8d, 200h; dwFlags
0x1400644fe  mov     [rbp+arg_0], 0
0x140064506  lea     rcx, tstrFilename; "mstscax.dll"
0x14006450d  call    cs:__imp_LoadLibraryExW
0x140064513  mov     [rbp+arg_10], rax
0x140064517  test    rax, rax
0x14006451a  jnz     short loc_14006457C
0x14006451c  call    cs:__imp_GetLastError
0x140064522  mov     ebx, eax
0x140064524  mov     rdx, cs:WPP_GLOBAL_Control
0x14006452b  lea     rcx, WPP_GLOBAL_Control
0x140064532  cmp     rdx, rcx
0x140064535  jz      loc_1400646F7
0x14006453b  test    byte ptr [rdx+1Ch], 8
0x14006453f  jz      loc_1400646F7
0x140064545  cmp     byte ptr [rdx+19h], 2
0x140064549  jb      loc_1400646F7
0x14006454f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064554  mov     edx, 22h ; '"'
0x140064559  mov     rcx, cs:WPP_GLOBAL_Control
0x140064560  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140064567  mov     r9d, eax
0x14006456a  mov     dword ptr [rsp+30h+var_10], ebx
0x14006456e  mov     rcx, [rcx+10h]
0x140064572  call    WPP_SF_Dd
0x140064577  jmp     loc_1400646F7
0x14006457c  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x140064583  mov     rcx, rax; hModule
0x140064586  call    cs:__imp_GetProcAddress
0x14006458c  test    rax, rax
0x14006458f  jnz     short loc_1400645D0
0x140064591  call    cs:__imp_GetLastError
0x140064597  mov     ebx, eax
0x140064599  mov     rdx, cs:WPP_GLOBAL_Control
0x1400645a0  lea     rcx, WPP_GLOBAL_Control
0x1400645a7  cmp     rdx, rcx
0x1400645aa  jz      loc_1400646F7
0x1400645b0  test    byte ptr [rdx+1Ch], 8
0x1400645b4  jz      loc_1400646F7
0x1400645ba  cmp     byte ptr [rdx+19h], 2
0x1400645be  jb      loc_1400646F7
0x1400645c4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400645c9  mov     edx, 23h ; '#'
0x1400645ce  jmp     short loc_140064559
0x1400645d0  lea     r8, [rbp+arg_8]
0x1400645d4  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x1400645db  lea     rcx, CLSID_MsRdpClient11NotSafeForScripting
0x1400645e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400645e7  mov     ebx, eax
0x1400645e9  test    eax, eax
0x1400645eb  jns     short loc_14006462E
0x1400645ed  mov     rdx, cs:WPP_GLOBAL_Control
0x1400645f4  lea     rcx, WPP_GLOBAL_Control
0x1400645fb  cmp     rdx, rcx
0x1400645fe  jz      loc_1400646F7
0x140064604  test    byte ptr [rdx+1Ch], 8
0x140064608  jz      loc_1400646F7
0x14006460e  cmp     byte ptr [rdx+19h], 2
0x140064612  jb      loc_1400646F7
0x140064618  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006461d  mov     edx, 24h ; '$'
0x140064622  lea     rcx, aDllgetclassobj_0; "DllGetClassObject failed"
0x140064629  jmp     loc_1400646D4
0x14006462e  mov     rcx, [rbp+arg_8]
0x140064632  lea     r9, [rbp+arg_0]
0x140064636  lea     r8, _GUID_71b4a60a_fe21_46d8_a39b_8e32ba0c5ecc
0x14006463d  xor     edx, edx
0x14006463f  mov     rax, [rcx]
0x140064642  mov     rax, [rax+18h]
0x140064646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006464b  mov     ebx, eax
0x14006464d  test    eax, eax
0x14006464f  jns     short loc_14006468B
0x140064651  mov     rdx, cs:WPP_GLOBAL_Control
0x140064658  lea     rcx, WPP_GLOBAL_Control
0x14006465f  cmp     rdx, rcx
0x140064662  jz      loc_1400646F7
0x140064668  test    byte ptr [rdx+1Ch], 8
0x14006466c  jz      loc_1400646F7
0x140064672  cmp     byte ptr [rdx+19h], 2
0x140064676  jb      short loc_1400646F7
0x140064678  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006467d  mov     edx, 25h ; '%'
0x140064682  lea     rcx, aCreateinstance_2; "CreateInstance failed"
0x140064689  jmp     short loc_1400646D4
0x14006468b  mov     rcx, [rbp+arg_0]
0x14006468f  mov     rax, [rcx]
0x140064692  mov     rax, [rax+220h]
0x140064699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006469e  mov     ebx, eax
0x1400646a0  test    eax, eax
0x1400646a2  jns     short loc_1400646F7
0x1400646a4  mov     rdx, cs:WPP_GLOBAL_Control
0x1400646ab  lea     rcx, WPP_GLOBAL_Control
0x1400646b2  cmp     rdx, rcx
0x1400646b5  jz      short loc_1400646F7
0x1400646b7  test    byte ptr [rdx+1Ch], 8
0x1400646bb  jz      short loc_1400646F7
0x1400646bd  cmp     byte ptr [rdx+19h], 2
0x1400646c1  jb      short loc_1400646F7
0x1400646c3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400646c8  mov     edx, 26h ; '&'
0x1400646cd  lea     rcx, aImsrdpclientno; "IMsRdpClientNonScriptable7::DisableDpiC"...
0x1400646d4  mov     [rsp+30h+var_8], ebx
0x1400646d8  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x1400646df  mov     [rsp+30h+var_10], rcx
0x1400646e4  mov     r9d, eax
0x1400646e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400646ee  mov     rcx, [rcx+10h]
0x1400646f2  call    WPP_SF_DsD
0x1400646f7  mov     rcx, [rbp+arg_0]
0x1400646fb  test    rcx, rcx
0x1400646fe  jz      short loc_140064714
0x140064700  mov     [rbp+arg_0], 0
0x140064708  mov     rax, [rcx]
0x14006470b  mov     rax, [rax+10h]
0x14006470f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064714  mov     rcx, [rbp+arg_8]
0x140064718  test    rcx, rcx
0x14006471b  jz      short loc_140064731
0x14006471d  mov     [rbp+arg_8], 0
0x140064725  mov     rax, [rcx]
0x140064728  mov     rax, [rax+10h]
0x14006472c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064731  lea     rcx, [rbp+arg_10]
0x140064735  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x14006473a  mov     rbx, [rsp+30h+arg_18]
0x14006473f  add     rsp, 30h
0x140064743  pop     rbp
0x140064744  retn
```
