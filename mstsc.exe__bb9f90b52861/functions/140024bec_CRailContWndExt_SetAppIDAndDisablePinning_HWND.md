# CRailContWndExt::SetAppIDAndDisablePinning(HWND__ *)

- ea: `0x140024bec`
- end: `0x140024efd`
- name: `?SetAppIDAndDisablePinning@CRailContWndExt@@AEBAJPEAUHWND__@@@Z`
- size: `785`
- prototype: `__int64 __fastcall(CRailContWndExt *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400222d0`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14001e404`
- `0x140024bec`
- `0x140114010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140024d7d`
- `msvcrt!memcpy_s` at `0x140024d7d`
- `KERNEL32!LoadLibraryW` at `0x140024c18`
- `KERNEL32!LoadLibraryW` at `0x140024c18`
- `KERNEL32!FreeLibrary` at `0x140024ec3`
- `KERNEL32!FreeLibrary` at `0x140024ec3`
- `KERNEL32!GetProcAddress` at `0x140024ca5`
- `KERNEL32!GetProcAddress` at `0x140024ca5`
- `KERNEL32!GetLastError` at `0x140024c26`
- `KERNEL32!GetLastError` at `0x140024c66`
- `KERNEL32!GetLastError` at `0x140024cb0`
- `KERNEL32!GetLastError` at `0x140024cf0`
- `KERNEL32!GetLastError` at `0x140024c26`
- `KERNEL32!GetLastError` at `0x140024c66`
- `KERNEL32!GetLastError` at `0x140024cb0`
- `KERNEL32!GetLastError` at `0x140024cf0`
- `ole32!CoTaskMemAlloc` at `0x140024d5f`
- `ole32!CoTaskMemAlloc` at `0x140024d5f`

## string_xrefs

- `0x140024c06`: `shell32.dll`

## pseudocode

```c
__int64 __fastcall CRailContWndExt::SetAppIDAndDisablePinning(CRailContWndExt *this, HWND a2)
{
  HMODULE LibraryW; // rax
  HMODULE v4; // r14
  signed int v5; // eax
  signed int v6; // edi
  DWORD v7; // ebx
  unsigned int v8; // eax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  DWORD v11; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  void *v13; // rax
  unsigned int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rcx
  __int128 v20; // [rsp+30h] [rbp-20h] BYREF
  __int64 v21; // [rsp+40h] [rbp-10h]
  __int64 v22; // [rsp+70h] [rbp+20h] BYREF

  v22 = 0;
  LibraryW = LoadLibraryW(L"shell32.dll");
  v4 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "SHGetPropertyStoreForWindow");
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = GetLastError();
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          99,
          &WPP_054707ce312e306d358833de4c0f150b_Traceguids,
          CurrentThreadActivityIdPrefix,
          v11);
      }
      goto LABEL_37;
    }
    v6 = 0;
    if ( !a2
      || (v6 = ((__int64 (__fastcall *)(HWND, GUID *, __int64 *))ProcAddress)(
                 a2,
                 &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                 &v22),
          v6 < 0) )
    {
LABEL_37:
      FreeLibrary(v4);
      goto LABEL_38;
    }
    *(_QWORD *)&v20 = 0;
    v21 = 0;
    v13 = CoTaskMemAlloc(0x54u);
    *((_QWORD *)&v20 + 1) = v13;
    if ( v13 )
    {
      memcpy_s(v13, 0x54u, L"Microsoft.Windows.RemoteApp.SecureDesktop", 0x54u);
      LOWORD(v20) = 31;
      (*(void (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v22 + 48LL))(
        v22,
        &PKEY_AppUserModel_ID,
        &v20);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 100;
LABEL_27:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_054707ce312e306d358833de4c0f150b_Traceguids, v14);
      }
    }
    else
    {
      v20 = 0;
      v21 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 101;
        goto LABEL_27;
      }
    }
    LOWORD(v20) = 11;
    WORD4(v20) = -1;
    v6 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v22 + 48LL))(
           v22,
           &PKEY_AppUserModel_PreventPinning,
           &v20);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_054707ce312e306d358833de4c0f150b_Traceguids, v16, v6);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_054707ce312e306d358833de4c0f150b_Traceguids, v17, a2);
    }
    goto LABEL_37;
  }
  v5 = GetLastError();
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = GetLastError();
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_054707ce312e306d358833de4c0f150b_Traceguids, v8, v7);
  }
LABEL_38:
  v18 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140024bec  mov     [rsp-18h+arg_8], rbx
0x140024bf1  mov     [rsp-18h+arg_10], rsi
0x140024bf6  mov     [rsp-18h+arg_0], rcx
0x140024bfb  push    rbp
0x140024bfc  push    rdi
0x140024bfd  push    r14
0x140024bff  mov     rbp, rsp
0x140024c02  sub     rsp, 50h
0x140024c06  lea     rcx, aShell32Dll_0; "shell32.dll"
0x140024c0d  mov     [rbp+arg_0], 0
0x140024c15  mov     rsi, rdx
0x140024c18  call    cs:__imp_LoadLibraryW
0x140024c1e  mov     r14, rax
0x140024c21  test    rax, rax
0x140024c24  jnz     short loc_140024C9B
0x140024c26  call    cs:__imp_GetLastError
0x140024c2c  mov     edi, eax
0x140024c2e  test    eax, eax
0x140024c30  jle     short loc_140024C3B
0x140024c32  movzx   edi, ax
0x140024c35  or      edi, 80070000h
0x140024c3b  mov     rax, cs:WPP_GLOBAL_Control
0x140024c42  lea     rbx, WPP_GLOBAL_Control
0x140024c49  cmp     rax, rbx
0x140024c4c  jz      loc_140024EC9
0x140024c52  test    byte ptr [rax+1Ch], 1
0x140024c56  jz      loc_140024EC9
0x140024c5c  cmp     byte ptr [rax+19h], 2
0x140024c60  jb      loc_140024EC9
0x140024c66  call    cs:__imp_GetLastError
0x140024c6c  mov     ebx, eax
0x140024c6e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140024c73  mov     rcx, cs:WPP_GLOBAL_Control
0x140024c7a  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x140024c81  mov     edx, 62h ; 'b'
0x140024c86  mov     dword ptr [rsp+50h+var_30], ebx
0x140024c8a  mov     r9d, eax
0x140024c8d  mov     rcx, [rcx+10h]
0x140024c91  call    WPP_SF_Dd
0x140024c96  jmp     loc_140024EC9
0x140024c9b  lea     rdx, aShgetpropertys; "SHGetPropertyStoreForWindow"
0x140024ca2  mov     rcx, r14; hModule
0x140024ca5  call    cs:__imp_GetProcAddress
0x140024cab  test    rax, rax
0x140024cae  jnz     short loc_140024D25
0x140024cb0  call    cs:__imp_GetLastError
0x140024cb6  mov     edi, eax
0x140024cb8  test    eax, eax
0x140024cba  jle     short loc_140024CC5
0x140024cbc  movzx   edi, ax
0x140024cbf  or      edi, 80070000h
0x140024cc5  mov     rax, cs:WPP_GLOBAL_Control
0x140024ccc  lea     rbx, WPP_GLOBAL_Control
0x140024cd3  cmp     rax, rbx
0x140024cd6  jz      loc_140024EC0
0x140024cdc  test    byte ptr [rax+1Ch], 1
0x140024ce0  jz      loc_140024EC0
0x140024ce6  cmp     byte ptr [rax+19h], 2
0x140024cea  jb      loc_140024EC0
0x140024cf0  call    cs:__imp_GetLastError
0x140024cf6  mov     ebx, eax
0x140024cf8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140024cfd  mov     edx, 63h ; 'c'
0x140024d02  mov     dword ptr [rsp+50h+var_30], ebx
0x140024d06  mov     rcx, cs:WPP_GLOBAL_Control
0x140024d0d  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x140024d14  mov     r9d, eax
0x140024d17  mov     rcx, [rcx+10h]
0x140024d1b  call    WPP_SF_Dd
0x140024d20  jmp     loc_140024EC0
0x140024d25  xor     edi, edi
0x140024d27  test    rsi, rsi
0x140024d2a  jz      loc_140024EC0
0x140024d30  lea     r8, [rbp+arg_0]
0x140024d34  mov     rcx, rsi
0x140024d37  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x140024d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024d43  mov     edi, eax
0x140024d45  test    eax, eax
0x140024d47  js      loc_140024EC0
0x140024d4d  xor     eax, eax
0x140024d4f  xorps   xmm0, xmm0
0x140024d52  movups  [rbp+var_20], xmm0
0x140024d56  mov     [rbp+var_10], rax
0x140024d5a  lea     ebx, [rax+54h]
0x140024d5d  mov     ecx, ebx; cb
0x140024d5f  call    cs:__imp_CoTaskMemAlloc
0x140024d65  mov     qword ptr [rbp+var_20+8], rax
0x140024d69  test    rax, rax
0x140024d6c  jz      short loc_140024DD0
0x140024d6e  mov     r9d, ebx; SourceSize
0x140024d71  lea     r8, aMicrosoftWindo_0; "Microsoft.Windows.RemoteApp.SecureDeskt"...
0x140024d78  mov     edx, ebx; DestinationSize
0x140024d7a  mov     rcx, rax; Destination
0x140024d7d  call    cs:__imp_memcpy_s
0x140024d83  mov     rcx, [rbp+arg_0]
0x140024d87  lea     eax, [rbx-35h]
0x140024d8a  mov     word ptr [rbp+var_20], ax
0x140024d8e  lea     r8, [rbp+var_20]
0x140024d92  lea     rdx, PKEY_AppUserModel_ID
0x140024d99  mov     rax, [rcx]
0x140024d9c  mov     rax, [rax+30h]
0x140024da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024da5  mov     rax, cs:WPP_GLOBAL_Control
0x140024dac  lea     rbx, WPP_GLOBAL_Control
0x140024db3  cmp     rax, rbx
0x140024db6  jz      short loc_140024E20
0x140024db8  test    byte ptr [rax+1Ch], 1
0x140024dbc  jz      short loc_140024E20
0x140024dbe  cmp     byte ptr [rax+19h], 5
0x140024dc2  jb      short loc_140024E20
0x140024dc4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140024dc9  mov     edx, 64h ; 'd'
0x140024dce  jmp     short loc_140024E06
0x140024dd0  xorps   xmm0, xmm0
0x140024dd3  xor     eax, eax
0x140024dd5  movups  [rbp+var_20], xmm0
0x140024dd9  mov     [rbp+var_10], rax
0x140024ddd  mov     rax, cs:WPP_GLOBAL_Control
0x140024de4  lea     rbx, WPP_GLOBAL_Control
0x140024deb  cmp     rax, rbx
0x140024dee  jz      short loc_140024E20
0x140024df0  test    byte ptr [rax+1Ch], 1
0x140024df4  jz      short loc_140024E20
0x140024df6  cmp     byte ptr [rax+19h], 2
0x140024dfa  jb      short loc_140024E20
0x140024dfc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140024e01  mov     edx, 65h ; 'e'
0x140024e06  mov     rcx, cs:WPP_GLOBAL_Control
0x140024e0d  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x140024e14  mov     r9d, eax
0x140024e17  mov     rcx, [rcx+10h]
0x140024e1b  call    WPP_SF_d
0x140024e20  mov     rcx, [rbp+arg_0]
0x140024e24  lea     r8, [rbp+var_20]
0x140024e28  mov     eax, 0Bh
0x140024e2d  lea     rdx, PKEY_AppUserModel_PreventPinning
0x140024e34  mov     word ptr [rbp+var_20], ax
0x140024e38  or      eax, 0FFFFFFFFh
0x140024e3b  mov     word ptr [rbp+var_20+8], ax
0x140024e3f  mov     rax, [rcx]
0x140024e42  mov     rax, [rax+30h]
0x140024e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024e4b  mov     edi, eax
0x140024e4d  test    eax, eax
0x140024e4f  jz      short loc_140024E7C
0x140024e51  mov     rax, cs:WPP_GLOBAL_Control
0x140024e58  cmp     rax, rbx
0x140024e5b  jz      short loc_140024EC0
0x140024e5d  test    byte ptr [rax+1Ch], 1
0x140024e61  jz      short loc_140024EC0
0x140024e63  cmp     byte ptr [rax+19h], 2
0x140024e67  jb      short loc_140024EC0
0x140024e69  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140024e6e  mov     edx, 66h ; 'f'
0x140024e73  mov     dword ptr [rsp+50h+var_30], edi
0x140024e77  jmp     loc_140024D06
0x140024e7c  mov     rax, cs:WPP_GLOBAL_Control
0x140024e83  cmp     rax, rbx
0x140024e86  jz      short loc_140024EC0
0x140024e88  test    dword ptr [rax+1Ch], 1000h
0x140024e8f  jz      short loc_140024EC0
0x140024e91  cmp     byte ptr [rax+19h], 4
0x140024e95  jb      short loc_140024EC0
0x140024e97  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140024e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140024ea3  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x140024eaa  mov     edx, 67h ; 'g'
0x140024eaf  mov     [rsp+50h+var_30], rsi
0x140024eb4  mov     r9d, eax
0x140024eb7  mov     rcx, [rcx+10h]
0x140024ebb  call    WPP_SF_Dq
0x140024ec0  mov     rcx, r14; hLibModule
0x140024ec3  call    cs:__imp_FreeLibrary
0x140024ec9  mov     rcx, [rbp+arg_0]
0x140024ecd  test    rcx, rcx
0x140024ed0  jz      short loc_140024EE6
0x140024ed2  mov     [rbp+arg_0], 0
0x140024eda  mov     rax, [rcx]
0x140024edd  mov     rax, [rax+10h]
0x140024ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024ee6  lea     r11, [rsp+50h+var_s0]
0x140024eeb  mov     eax, edi
0x140024eed  mov     rbx, [r11+28h]
0x140024ef1  mov     rsi, [r11+30h]
0x140024ef5  mov     rsp, r11
0x140024ef8  pop     r14
0x140024efa  pop     rdi
0x140024efb  pop     rbp
0x140024efc  retn
```
