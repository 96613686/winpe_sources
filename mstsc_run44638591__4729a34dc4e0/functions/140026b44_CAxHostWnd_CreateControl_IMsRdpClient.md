# CAxHostWnd::CreateControl(IMsRdpClient * *)

- ea: `0x140026b44`
- end: `0x1400271aa`
- name: `?CreateControl@CAxHostWnd@@QEAAHPEAPEAUIMsRdpClient@@@Z`
- size: `1638`
- prototype: `__int64 __fastcall(CAxHostWnd *__hidden this, struct IMsRdpClient **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400128d0`

## callees

- `0x140003b2c`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14001e130`
- `0x140026b44`
- `0x14002d6c0`
- `0x1400a1f78`
- `0x140114010`

## import_xrefs

- `VERSION!GetFileVersionInfoW` at `0x140026c84`
- `VERSION!GetFileVersionInfoW` at `0x140026c84`
- `VERSION!GetFileVersionInfoSizeW` at `0x140026be8`
- `VERSION!GetFileVersionInfoSizeW` at `0x140026be8`
- `VERSION!VerQueryValueW` at `0x140026cea`
- `VERSION!VerQueryValueW` at `0x140026cea`
- `KERNEL32!LoadLibraryW` at `0x140026b85`
- `KERNEL32!LoadLibraryW` at `0x140026b85`
- `KERNEL32!GetProcAddress` at `0x140026d61`
- `KERNEL32!GetProcAddress` at `0x140026d61`
- `KERNEL32!GetLastError` at `0x140026c1f`
- `KERNEL32!GetLastError` at `0x140026cb9`
- `KERNEL32!GetLastError` at `0x140026d1f`
- `KERNEL32!GetLastError` at `0x140026c1f`
- `KERNEL32!GetLastError` at `0x140026cb9`
- `KERNEL32!GetLastError` at `0x140026d1f`
- `ole32!CoTaskMemAlloc` at `0x140026c4c`
- `ole32!CoTaskMemAlloc` at `0x140026c4c`
- `ole32!CoTaskMemFree` at `0x140026d46`
- `ole32!CoTaskMemFree` at `0x140027114`
- `ole32!CoTaskMemFree` at `0x140027158`
- `ole32!CoTaskMemFree` at `0x140026d46`
- `ole32!CoTaskMemFree` at `0x140027114`
- `ole32!CoTaskMemFree` at `0x140027158`

## string_xrefs

- `0x140026b7e`: `mstscax.dll`
- `0x140026be1`: `mstscax.dll`
- `0x140026c78`: `mstscax.dll`
- `0x140026d5a`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall CAxHostWnd::CreateControl(CAxHostWnd *this, struct IMsRdpClient **a2)
{
  HMODULE LibraryW; // rax
  unsigned int v5; // eax
  DWORD FileVersionInfoSizeW; // eax
  __int64 v8; // rdi
  DWORD LastError; // eax
  _BYTE *v10; // rax
  void *v11; // rbx
  _BYTE *i; // rdx
  DWORD CurrentThreadActivityIdPrefix; // eax
  __int64 v14; // rdx
  int v15; // edi
  FARPROC ProcAddress; // rax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  _QWORD *v19; // rdi
  bool v20; // sf
  void (*v21)(void); // rax
  void (*v22)(void); // rax
  void *v23; // rax
  __int64 v24; // rcx
  void (*v25)(void); // rax
  __int64 v26; // [rsp+30h] [rbp-10h] BYREF
  LPVOID lpBuffer; // [rsp+38h] [rbp-8h] BYREF
  unsigned int puLen; // [rsp+78h] [rbp+38h] BYREF
  __int64 v29; // [rsp+80h] [rbp+40h] BYREF
  __int64 v30; // [rsp+88h] [rbp+48h] BYREF

  v30 = 0;
  v26 = 0;
  v29 = 0;
  if ( !a2 )
    return 4294967293LL;
  LibraryW = LoadLibraryW(L"mstscax.dll");
  *((_QWORD *)this + 5) = LibraryW;
  if ( LibraryW )
  {
    FileVersionInfoSizeW = GetFileVersionInfoSizeW(L"mstscax.dll", 0);
    v8 = FileVersionInfoSizeW;
    if ( !FileVersionInfoSizeW )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_397b24202ccc35f6d1972e544a06c8d6_Traceguids, LastError);
      }
      return 4294967293LL;
    }
    v10 = CoTaskMemAlloc(FileVersionInfoSizeW);
    v11 = v10;
    if ( !v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_397b24202ccc35f6d1972e544a06c8d6_Traceguids);
      }
      return 4294967293LL;
    }
    for ( i = &v10[v8]; v10 != i; ++v10 )
      *v10 = 0;
    if ( !GetFileVersionInfoW(L"mstscax.dll", 0, v8, v11) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_84;
      }
      CurrentThreadActivityIdPrefix = GetLastError();
      v14 = 15;
      goto LABEL_43;
    }
    lpBuffer = 0;
    puLen = 0;
    if ( !VerQueryValueW(v11, L"\\", &lpBuffer, &puLen) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_84;
      }
      CurrentThreadActivityIdPrefix = GetLastError();
      v14 = 16;
      goto LABEL_43;
    }
    v15 = *((unsigned __int16 *)lpBuffer + 7);
    if ( CClientUtilsWin32::UT_GetModuleBuildNumber() != v15 )
    {
      CoTaskMemFree(v11);
      return 4294967294LL;
    }
    ProcAddress = GetProcAddress(*((HMODULE *)this + 5), "DllGetClassObject");
    if ( ProcAddress )
    {
      if ( ((int (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
             &CLSID_MsRdpClientNotSafeForScripting,
             &IID_IClassFactory,
             &v30) >= 0 )
      {
        v19 = (_QWORD *)((char *)this + 24);
        v20 = (*(int (__fastcall **)(__int64, _QWORD, GUID *, char *))(*(_QWORD *)v30 + 24LL))(
                v30,
                0,
                &IID_IMsRdpClient,
                (char *)this + 24) < 0;
        v21 = *(void (**)(void))(*(_QWORD *)v30 + 16LL);
        if ( v20 )
        {
          v21();
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_84;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v14 = 19;
LABEL_43:
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v14,
            WPP_397b24202ccc35f6d1972e544a06c8d6_Traceguids,
            CurrentThreadActivityIdPrefix);
LABEL_84:
          CoTaskMemFree(v11);
          return 4294967293LL;
        }
        v21();
        if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v19)(*v19, &IID_IConnectionPointContainer, &v26) >= 0 )
        {
          v20 = (*(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v26 + 32LL))(
                  v26,
                  &DIID_IMsTscAxEvents,
                  &v29) < 0;
          v22 = *(void (**)(void))(*(_QWORD *)v26 + 16LL);
          if ( v20 )
          {
            v22();
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              goto LABEL_84;
            }
            v18 = 21;
          }
          else
          {
            v22();
            v23 = operator new(0x18u);
            if ( v23 )
            {
              v24 = *((_QWORD *)this + 12);
              *(_QWORD *)v23 = &CEventSink::`vftable';
              *((_QWORD *)v23 + 2) = v24;
              *((_DWORD *)v23 + 2) = 0;
            }
            *((_QWORD *)this + 6) = v23;
            if ( v23 )
            {
              _InterlockedIncrement((volatile signed __int32 *)v23 + 2);
              v20 = (*(int (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v29 + 40LL))(
                      v29,
                      *((_QWORD *)this + 6),
                      (char *)this + 32) < 0;
              v25 = *(void (**)(void))(*(_QWORD *)v29 + 16LL);
              if ( v20 )
              {
                v25();
                CEventSink::Release(*((CEventSink **)this + 6));
                *((_QWORD *)this + 6) = 0;
                v17 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
                {
                  goto LABEL_84;
                }
                v18 = 23;
              }
              else
              {
                v25();
                if ( (**(int (__fastcall ***)(_QWORD, GUID *, char *))*v19)(*v19, &IID_IOleObject, (char *)this + 72) < 0
                  || (**(int (__fastcall ***)(_QWORD, GUID *, char *))*v19)(
                       *v19,
                       &IID_IOleInPlaceActiveObject,
                       (char *)this + 80) < 0 )
                {
                  v17 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                    || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
                  {
                    goto LABEL_84;
                  }
                  v18 = 24;
                }
                else if ( (**(int (__fastcall ***)(_QWORD, GUID *, char *))*v19)(
                            *v19,
                            &IID_IOleInPlaceObject,
                            (char *)this + 88) >= 0 )
                {
                  if ( (*(int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 9) + 24LL))(
                         *((_QWORD *)this + 9),
                         *((_QWORD *)this + 7)) >= 0 )
                  {
                    *a2 = (struct IMsRdpClient *)*v19;
                    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 8LL))(*v19);
                    CoTaskMemFree(v11);
                    return 1;
                  }
                  v17 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                    || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
                  {
                    goto LABEL_84;
                  }
                  v18 = 26;
                }
                else
                {
                  v17 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                    || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
                  {
                    goto LABEL_84;
                  }
                  v18 = 25;
                }
              }
            }
            else
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
              {
                goto LABEL_84;
              }
              v18 = 22;
            }
          }
        }
        else
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            goto LABEL_84;
          }
          v18 = 20;
        }
      }
      else
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_84;
        }
        v18 = 18;
      }
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_84;
      }
      v18 = 17;
    }
    WPP_SF_(v17[2], v18, WPP_397b24202ccc35f6d1972e544a06c8d6_Traceguids);
    goto LABEL_84;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_397b24202ccc35f6d1972e544a06c8d6_Traceguids, v5);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x140026b44  mov     [rsp-28h+arg_0], rbx
0x140026b49  push    rbp
0x140026b4a  push    rsi
0x140026b4b  push    rdi
0x140026b4c  push    r14
0x140026b4e  push    r15
0x140026b50  mov     rbp, rsp
0x140026b53  sub     rsp, 40h
0x140026b57  mov     [rbp+arg_18], 0
0x140026b5f  mov     r15, rdx
0x140026b62  mov     [rbp+var_10], 0
0x140026b6a  mov     rsi, rcx
0x140026b6d  mov     [rbp+arg_10], 0
0x140026b75  test    rdx, rdx
0x140026b78  jz      loc_140027194
0x140026b7e  lea     rcx, tstrFilename; "mstscax.dll"
0x140026b85  call    cs:__imp_LoadLibraryW
0x140026b8b  mov     [rsi+28h], rax
0x140026b8f  test    rax, rax
0x140026b92  jnz     short loc_140026BDF
0x140026b94  mov     rcx, cs:WPP_GLOBAL_Control
0x140026b9b  lea     rax, WPP_GLOBAL_Control
0x140026ba2  cmp     rcx, rax
0x140026ba5  jz      short loc_140026BD7
0x140026ba7  test    byte ptr [rcx+1Ch], 1
0x140026bab  jz      short loc_140026BD7
0x140026bad  cmp     byte ptr [rcx+19h], 2
0x140026bb1  jb      short loc_140026BD7
0x140026bb3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140026bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140026bbf  lea     r8, WPP_397b24202ccc35f6d1972e544a06c8d6_Traceguids
0x140026bc6  mov     edx, 0Ch
0x140026bcb  mov     r9d, eax
0x140026bce  mov     rcx, [rcx+10h]
0x140026bd2  call    WPP_SF_d
0x140026bd7  or      eax, 0FFFFFFFFh
0x140026bda  jmp     loc_140027199
0x140026bdf  xor     edx, edx; lpdwHandle
0x140026be1  lea     rcx, tstrFilename; "mstscax.dll"
0x140026be8  call    cs:__imp_GetFileVersionInfoSizeW
0x140026bee  mov     edi, eax
0x140026bf0  test    eax, eax
0x140026bf2  jnz     short loc_140026C49
0x140026bf4  mov     rcx, cs:WPP_GLOBAL_Control
0x140026bfb  lea     rax, WPP_GLOBAL_Control
0x140026c02  cmp     rcx, rax
0x140026c05  jz      loc_140027194
0x140026c0b  test    byte ptr [rcx+1Ch], 1
0x140026c0f  jz      loc_140027194
0x140026c15  cmp     byte ptr [rcx+19h], 1
0x140026c19  jb      loc_140027194
0x140026c1f  call    cs:__imp_GetLastError
0x140026c25  mov     rcx, cs:WPP_GLOBAL_Control
0x140026c2c  lea     r8, WPP_397b24202ccc35f6d1972e544a06c8d6_Traceguids
0x140026c33  mov     edx, 0Dh
0x140026c38  mov     r9d, eax
0x140026c3b  mov     rcx, [rcx+10h]
0x140026c3f  call    WPP_SF_d
0x140026c44  jmp     loc_140027194
0x140026c49  mov     rcx, rdi; cb
0x140026c4c  call    cs:__imp_CoTaskMemAlloc
0x140026c52  mov     rbx, rax
0x140026c55  test    rax, rax
0x140026c58  jz      loc_140027160
0x140026c5e  lea     rdx, [rax+rdi]
0x140026c62  cmp     rax, rdx
0x140026c65  jz      short loc_140026C75
0x140026c67  xor     r8d, r8d
0x140026c6a  mov     [rax], r8b
0x140026c6d  inc     rax
0x140026c70  cmp     rax, rdx
0x140026c73  jnz     short loc_140026C67
0x140026c75  mov     r9, rbx; lpData
0x140026c78  lea     rcx, tstrFilename; "mstscax.dll"
0x140026c7f  mov     r8d, edi; dwLen
0x140026c82  xor     edx, edx; dwHandle
0x140026c84  call    cs:__imp_GetFileVersionInfoW
0x140026c8a  test    eax, eax
0x140026c8c  jnz     short loc_140026CC9
0x140026c8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140026c95  lea     rax, WPP_GLOBAL_Control
0x140026c9c  cmp     rcx, rax
0x140026c9f  jz      loc_140027155
0x140026ca5  test    byte ptr [rcx+1Ch], 1
0x140026ca9  jz      loc_140027155
0x140026caf  cmp     byte ptr [rcx+19h], 1
0x140026cb3  jb      loc_140027155
0x140026cb9  call    cs:__imp_GetLastError
0x140026cbf  mov     edx, 0Fh
0x140026cc4  jmp     loc_140026E5A
0x140026cc9  lea     r9, [rbp+puLen]; puLen
0x140026ccd  mov     [rbp+lpBuffer], 0
0x140026cd5  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x140026cd9  mov     [rbp+puLen], 0
0x140026ce0  lea     rdx, SubBlock; "\\"
0x140026ce7  mov     rcx, rbx; pBlock
0x140026cea  call    cs:__imp_VerQueryValueW
0x140026cf0  test    eax, eax
0x140026cf2  jnz     short loc_140026D2F
0x140026cf4  mov     rcx, cs:WPP_GLOBAL_Control
0x140026cfb  lea     rax, WPP_GLOBAL_Control
0x140026d02  cmp     rcx, rax
0x140026d05  jz      loc_140027155
0x140026d0b  test    byte ptr [rcx+1Ch], 1
0x140026d0f  jz      loc_140027155
0x140026d15  cmp     byte ptr [rcx+19h], 1
0x140026d19  jb      loc_140027155
0x140026d1f  call    cs:__imp_GetLastError
0x140026d25  mov     edx, 10h
0x140026d2a  jmp     loc_140026E5A
0x140026d2f  mov     rax, [rbp+lpBuffer]
0x140026d33  movzx   edi, word ptr [rax+0Eh]
0x140026d37  call    ?UT_GetModuleBuildNumber@CClientUtilsWin32@@SAGXZ; CClientUtilsWin32::UT_GetModuleBuildNumber(void)
0x140026d3c  movzx   eax, ax
0x140026d3f  cmp     eax, edi
0x140026d41  jz      short loc_140026D56
0x140026d43  mov     rcx, rbx; pv
0x140026d46  call    cs:__imp_CoTaskMemFree
0x140026d4c  mov     eax, 0FFFFFFFEh
0x140026d51  jmp     loc_140027199
0x140026d56  mov     rcx, [rsi+28h]; hModule
0x140026d5a  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x140026d61  call    cs:__imp_GetProcAddress
0x140026d67  test    rax, rax
0x140026d6a  jnz     short loc_140026DA1
0x140026d6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140026d73  lea     rax, WPP_GLOBAL_Control
0x140026d7a  cmp     rcx, rax
0x140026d7d  jz      loc_140027155
0x140026d83  test    byte ptr [rcx+1Ch], 1
0x140026d87  jz      loc_140027155
0x140026d8d  cmp     byte ptr [rcx+19h], 1
0x140026d91  jb      loc_140027155
0x140026d97  mov     edx, 11h
0x140026d9c  jmp     loc_140027145
0x140026da1  lea     r8, [rbp+arg_18]
0x140026da5  lea     rdx, IID_IClassFactory
0x140026dac  lea     rcx, CLSID_MsRdpClientNotSafeForScripting
0x140026db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026db8  test    eax, eax
0x140026dba  jns     short loc_140026DF1
0x140026dbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140026dc3  lea     rax, WPP_GLOBAL_Control
0x140026dca  cmp     rcx, rax
0x140026dcd  jz      loc_140027155
0x140026dd3  test    byte ptr [rcx+1Ch], 1
0x140026dd7  jz      loc_140027155
0x140026ddd  cmp     byte ptr [rcx+19h], 1
0x140026de1  jb      loc_140027155
0x140026de7  mov     edx, 12h
0x140026dec  jmp     loc_140027145
0x140026df1  mov     rcx, [rbp+arg_18]
0x140026df5  lea     rdi, [rsi+18h]
0x140026df9  mov     r9, rdi
0x140026dfc  lea     r8, IID_IMsRdpClient
0x140026e03  xor     edx, edx
0x140026e05  mov     rax, [rcx]
0x140026e08  mov     rax, [rax+18h]
0x140026e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e11  mov     rcx, [rbp+arg_18]
0x140026e15  test    eax, eax
0x140026e17  mov     rax, [rcx]
0x140026e1a  mov     rax, [rax+10h]
0x140026e1e  jns     short loc_140026E79
0x140026e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e25  mov     rcx, cs:WPP_GLOBAL_Control
0x140026e2c  lea     rax, WPP_GLOBAL_Control
0x140026e33  cmp     rcx, rax
0x140026e36  jz      loc_140027155
0x140026e3c  test    byte ptr [rcx+1Ch], 1
0x140026e40  jz      loc_140027155
0x140026e46  cmp     byte ptr [rcx+19h], 2
0x140026e4a  jb      loc_140027155
0x140026e50  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140026e55  mov     edx, 13h
0x140026e5a  mov     rcx, cs:WPP_GLOBAL_Control
0x140026e61  lea     r8, WPP_397b24202ccc35f6d1972e544a06c8d6_Traceguids
0x140026e68  mov     r9d, eax
0x140026e6b  mov     rcx, [rcx+10h]
0x140026e6f  call    WPP_SF_d
0x140026e74  jmp     loc_140027155
0x140026e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e7e  mov     rcx, [rdi]
0x140026e81  lea     r8, [rbp+var_10]
0x140026e85  lea     rdx, IID_IConnectionPointContainer
0x140026e8c  mov     rax, [rcx]
0x140026e8f  mov     rax, [rax]
0x140026e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e97  test    eax, eax
0x140026e99  jns     short loc_140026ED0
0x140026e9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140026ea2  lea     rax, WPP_GLOBAL_Control
0x140026ea9  cmp     rcx, rax
0x140026eac  jz      loc_140027155
0x140026eb2  test    byte ptr [rcx+1Ch], 1
0x140026eb6  jz      loc_140027155
0x140026ebc  cmp     byte ptr [rcx+19h], 1
0x140026ec0  jb      loc_140027155
0x140026ec6  mov     edx, 14h
0x140026ecb  jmp     loc_140027145
0x140026ed0  mov     rcx, [rbp+var_10]
0x140026ed4  lea     r8, [rbp+arg_10]
0x140026ed8  lea     rdx, DIID_IMsTscAxEvents
0x140026edf  mov     rax, [rcx]
0x140026ee2  mov     rax, [rax+20h]
0x140026ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026eeb  mov     rcx, [rbp+var_10]
0x140026eef  test    eax, eax
0x140026ef1  mov     rax, [rcx]
0x140026ef4  mov     rax, [rax+10h]
0x140026ef8  jns     short loc_140026F34
0x140026efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026eff  mov     rcx, cs:WPP_GLOBAL_Control
0x140026f06  lea     rax, WPP_GLOBAL_Control
0x140026f0d  cmp     rcx, rax
0x140026f10  jz      loc_140027155
0x140026f16  test    byte ptr [rcx+1Ch], 1
0x140026f1a  jz      loc_140027155
0x140026f20  cmp     byte ptr [rcx+19h], 1
0x140026f24  jb      loc_140027155
0x140026f2a  mov     edx, 15h
0x140026f2f  jmp     loc_140027145
0x140026f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026f39  mov     ecx, 18h; Size
0x140026f3e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140026f43  test    rax, rax
0x140026f46  jz      short loc_140026F61
0x140026f48  mov     rcx, [rsi+60h]
0x140026f4c  lea     rdx, ??_7CEventSink@@6B@; const CEventSink::`vftable'
0x140026f53  mov     [rax], rdx
0x140026f56  mov     [rax+10h], rcx
0x140026f5a  mov     dword ptr [rax+8], 0
0x140026f61  mov     [rsi+30h], rax
0x140026f65  test    rax, rax
0x140026f68  jnz     short loc_140026FAF
0x140026f6a  mov     rcx, [rbp+arg_10]
0x140026f6e  mov     rax, [rcx]
0x140026f71  mov     rax, [rax+10h]
0x140026f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026f7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140026f81  lea     rax, WPP_GLOBAL_Control
0x140026f88  cmp     rcx, rax
0x140026f8b  jz      loc_140027155
0x140026f91  test    byte ptr [rcx+1Ch], 1
0x140026f95  jz      loc_140027155
0x140026f9b  cmp     byte ptr [rcx+19h], 1
0x140026f9f  jb      loc_140027155
0x140026fa5  mov     edx, 16h
0x140026faa  jmp     loc_140027145
0x140026faf  lock inc dword ptr [rax+8]
0x140026fb3  mov     rcx, [rbp+arg_10]
0x140026fb7  lea     r8, [rsi+20h]
0x140026fbb  mov     rdx, [rsi+30h]
0x140026fbf  mov     rax, [rcx]
0x140026fc2  mov     rax, [rax+28h]
0x140026fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026fcb  mov     rcx, [rbp+arg_10]
0x140026fcf  test    eax, eax
0x140026fd1  mov     rax, [rcx]
0x140026fd4  mov     rax, [rax+10h]
0x140026fd8  jns     short loc_140027025
0x140026fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026fdf  mov     rcx, [rsi+30h]; this
0x140026fe3  call    ?Release@CEventSink@@UEAAKXZ; CEventSink::Release(void)
0x140026fe8  mov     qword ptr [rsi+30h], 0
0x140026ff0  mov     rcx, cs:WPP_GLOBAL_Control
0x140026ff7  lea     rax, WPP_GLOBAL_Control
0x140026ffe  cmp     rcx, rax
0x140027001  jz      loc_140027155
0x140027007  test    byte ptr [rcx+1Ch], 1
0x14002700b  jz      loc_140027155
0x140027011  cmp     byte ptr [rcx+19h], 1
0x140027015  jb      loc_140027155
0x14002701b  mov     edx, 17h
0x140027020  jmp     loc_140027145
0x140027025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002702a  mov     rcx, [rdi]
0x14002702d  lea     r8, [rsi+48h]
0x140027031  lea     rdx, IID_IOleObject
0x140027038  mov     rax, [rcx]
0x14002703b  mov     rax, [rax]
0x14002703e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027043  test    eax, eax
0x140027045  js      loc_140027121
0x14002704b  mov     rcx, [rdi]
0x14002704e  lea     r8, [rsi+50h]
0x140027052  lea     rdx, IID_IOleInPlaceActiveObject
0x140027059  mov     rax, [rcx]
0x14002705c  mov     rax, [rax]
0x14002705f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027064  test    eax, eax
0x140027066  js      loc_140027121
0x14002706c  mov     rcx, [rdi]
0x14002706f  lea     r8, [rsi+58h]
0x140027073  lea     rdx, IID_IOleInPlaceObject
0x14002707a  mov     rax, [rcx]
0x14002707d  mov     rax, [rax]
0x140027080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027085  test    eax, eax
0x140027087  jns     short loc_1400270BE
  ... truncated ...
```
