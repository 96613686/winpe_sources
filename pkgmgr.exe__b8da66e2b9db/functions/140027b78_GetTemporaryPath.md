# GetTemporaryPath

- ea: `0x140027b78`
- end: `0x140027cd1`
- name: `GetTemporaryPath`
- size: `345`
- prototype: `__int64 __fastcall(__int64, WCHAR *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140025b30`

## callees

- `0x140002360`
- `0x14000731c`
- `0x1400074c0`
- `0x140012a00`
- `0x140027a20`
- `0x140027b78`
- `0x14002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027be8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027c35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027be8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027c35`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x140027bde`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x140027bde`

## string_xrefs

- `0x140027bff`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x140027c4a`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x140027c0a`: `Windows::COM::GetTemporaryPath`
- `0x140027c64`: `Windows::COM::GetTemporaryPath`

## pseudocode

```c
__int64 __fastcall GetTemporaryPath(__int64 a1, WCHAR *a2)
{
  DWORD TempPathW; // eax
  HINSTANCE v4; // rdx
  signed int LastError; // eax
  unsigned int v6; // r8d
  _QWORD *v7; // rdx
  unsigned int v8; // ebx
  Windows::Detail *v10; // [rsp+20h] [rbp-60h] BYREF
  __int64 (__fastcall *v11)(__int64, WCHAR *); // [rsp+28h] [rbp-58h] BYREF
  _QWORD v12[4]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v13[4]; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v14; // [rsp+70h] [rbp-10h] BYREF

  v14 = 0;
  v10 = 0;
  v11 = 0;
  if ( a2 )
    *a2 = 0;
  if ( Windows::COM::LoadSystemLibraryAndFunction(a1, (__int64)a2, (HMODULE *)&v10, (FARPROC *)&v11) < 0 )
    TempPathW = GetTempPathW(0x104u, a2);
  else
    TempPathW = v11(260, a2);
  if ( !TempPathW )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        INTERNAL_ERROR_ACTION();
    }
    else
    {
      LastError = 14077;
    }
    v12[2] = 82;
    v12[0] = "onecore\\base\\wcp\\rtllib\\win32lib\\pathwin32_library.cpp";
    v12[1] = "Windows::COM::GetTemporaryPath";
    v12[3] = "GetLastError";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = LastError;
    v7 = v12;
    goto LABEL_16;
  }
  if ( TempPathW == -1 )
  {
    v13[2] = 86;
    v13[0] = "onecore\\base\\wcp\\rtllib\\win32lib\\pathwin32_library.cpp";
    v13[3] = "static_cast<DWORD>(1292L)";
    v13[1] = "Windows::COM::GetTemporaryPath";
    v7 = v13;
    v6 = -2147023604;
LABEL_16:
    v8 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
           &v14,
           (__int64)v7,
           v6);
LABEL_19:
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(
      &v10,
      v4);
    return v8;
  }
  if ( TempPathW > 0x104 )
  {
    v8 = -2147024774;
    goto LABEL_19;
  }
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(
    &v10,
    v4);
  return 0;
}

```

## disassembly

```asm
0x140027b78  mov     [rsp-8+arg_0], rbx
0x140027b7d  push    rbp
0x140027b7e  mov     rbp, rsp
0x140027b81  sub     rsp, 80h
0x140027b88  mov     rax, cs:__security_cookie
0x140027b8f  xor     rax, rsp
0x140027b92  mov     [rbp+var_8], rax
0x140027b96  mov     [rbp+var_10], 0
0x140027b9d  mov     rbx, rdx
0x140027ba0  mov     [rbp+var_60], 0
0x140027ba8  mov     [rbp+var_58], 0
0x140027bb0  test    rdx, rdx
0x140027bb3  jz      short loc_140027BBA
0x140027bb5  xor     eax, eax
0x140027bb7  mov     [rdx], ax
0x140027bba  lea     r9, [rbp+var_58]
0x140027bbe  lea     r8, [rbp+var_60]
0x140027bc2  call    ?LoadSystemLibraryAndFunction@COM@Windows@@YAJQEB_WQEBDPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@2@PEAP6A_JXZ@Z; Windows::COM::LoadSystemLibraryAndFunction(wchar_t const * const,char const * const,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *,__int64 (**)(void))
0x140027bc7  mov     rdx, rbx; lpBuffer
0x140027bca  mov     ecx, 104h; nBufferLength
0x140027bcf  test    eax, eax
0x140027bd1  js      short loc_140027BDE
0x140027bd3  mov     rax, [rbp+var_58]
0x140027bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027bdc  jmp     short loc_140027BE4
0x140027bde  call    cs:__imp_GetTempPathW
0x140027be4  test    eax, eax
0x140027be6  jnz     short loc_140027C45
0x140027be8  call    cs:__imp_GetLastError
0x140027bee  test    eax, eax
0x140027bf0  jnz     short loc_140027C35
0x140027bf2  mov     eax, 36FDh
0x140027bf7  mov     [rbp+var_40], 52h ; 'R'
0x140027bff  lea     rcx, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x140027c06  mov     [rbp+var_50], rcx
0x140027c0a  lea     rcx, aWindowsComGett; "Windows::COM::GetTemporaryPath"
0x140027c11  mov     [rbp+var_48], rcx
0x140027c15  lea     rcx, aGetlasterror; "GetLastError"
0x140027c1c  mov     [rbp+var_38], rcx
0x140027c20  test    eax, eax
0x140027c22  jle     short loc_140027C2C
0x140027c24  movzx   eax, ax
0x140027c27  or      eax, 80070000h
0x140027c2c  mov     r8d, eax
0x140027c2f  lea     rdx, [rbp+var_50]
0x140027c33  jmp     short loc_140027C7D
0x140027c35  call    cs:__imp_GetLastError
0x140027c3b  test    eax, eax
0x140027c3d  jz      loc_140027CCB
0x140027c43  jmp     short loc_140027BF7
0x140027c45  cmp     eax, 0FFFFFFFFh
0x140027c48  jnz     short loc_140027C8A
0x140027c4a  lea     rcx, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x140027c51  mov     [rbp+var_20], 56h ; 'V'
0x140027c59  mov     [rbp+var_30], rcx
0x140027c5d  lea     rax, aStaticCastDwor; "static_cast<DWORD>(1292L)"
0x140027c64  lea     rcx, aWindowsComGett; "Windows::COM::GetTemporaryPath"
0x140027c6b  mov     [rbp+var_18], rax
0x140027c6f  mov     [rbp+var_28], rcx
0x140027c73  lea     rdx, [rbp+var_30]
0x140027c77  mov     r8d, 8007050Ch
0x140027c7d  lea     rcx, [rbp+var_10]
0x140027c81  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140027c86  mov     ebx, eax
0x140027c88  jmp     short loc_140027C96
0x140027c8a  cmp     eax, 104h
0x140027c8f  jbe     short loc_140027CA3
0x140027c91  mov     ebx, 8007007Ah
0x140027c96  lea     rcx, [rbp+var_60]
0x140027c9a  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x140027c9f  mov     eax, ebx
0x140027ca1  jmp     short loc_140027CAE
0x140027ca3  lea     rcx, [rbp+var_60]
0x140027ca7  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x140027cac  xor     eax, eax
0x140027cae  mov     rcx, [rbp+var_8]
0x140027cb2  xor     rcx, rsp; StackCookie
0x140027cb5  call    __security_check_cookie
0x140027cba  mov     rbx, [rsp+80h+arg_0]
0x140027cc2  add     rsp, 80h
0x140027cc9  pop     rbp
0x140027cca  retn
0x140027ccb  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
