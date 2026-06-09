# CServicingSession::CleanupTarget(ulong,IFhEngineCleanupProgressEvent *)

- ea: `0x180022d20`
- end: `0x180023207`
- name: `?CleanupTarget@CServicingSession@@UEAAJKPEAUIFhEngineCleanupProgressEvent@@@Z`
- size: `1255`
- prototype: `__int64 __fastcall(CServicingSession *this, unsigned int, struct IFhEngineCleanupProgressEvent *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800031b0`
- `0x1800077f0`
- `0x180007818`
- `0x1800093a8`
- `0x18000c004`
- `0x180010de8`
- `0x180022d20`
- `0x180034010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180022f4a`
- `ADVAPI32!SetThreadToken` at `0x180023122`
- `ADVAPI32!SetThreadToken` at `0x180022f4a`
- `ADVAPI32!SetThreadToken` at `0x180023122`
- `ADVAPI32!OpenThreadToken` at `0x180022e40`
- `ADVAPI32!OpenThreadToken` at `0x180022e40`
- `KERNEL32!GetLastError` at `0x180022f54`
- `KERNEL32!GetLastError` at `0x18002313e`
- `KERNEL32!GetLastError` at `0x180022f54`
- `KERNEL32!GetLastError` at `0x18002313e`
- `KERNEL32!CloseHandle` at `0x180022d9d`
- `KERNEL32!CloseHandle` at `0x180022e77`
- `KERNEL32!CloseHandle` at `0x180022d9d`
- `KERNEL32!CloseHandle` at `0x180022e77`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180023005`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x1800230df`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180023005`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x1800230df`
- `KERNEL32!GetCurrentThread` at `0x180022e2b`
- `KERNEL32!GetCurrentThread` at `0x180022e2b`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180022de0`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180022de0`

## string_xrefs

- `0x18002318b`: `!impersonating`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 __fastcall CServicingSession::CleanupTarget(
        CServicingSession *this,
        unsigned int a2,
        struct IFhEngineCleanupProgressEvent *a3)
{
  int v5; // r12d
  HANDLE *v6; // rsi
  void *v7; // rcx
  HRESULT v8; // eax
  unsigned int v9; // ebx
  HANDLE CurrentThread; // rax
  int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  signed int LastError; // eax
  int v16; // ebx
  PVOID *v17; // rcx
  signed int v18; // eax
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+60h] [rbp-10h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+B0h] [rbp+40h] BYREF
  struct IFhEngineCleanupProgressEvent *v22; // [rsp+C0h] [rbp+50h]
  void *ppInterface; // [rsp+C8h] [rbp+58h] BYREF

  v22 = a3;
  ppInterface = 0;
  TotalNumberOfBytes.QuadPart = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  v5 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids, a2);
  v6 = (HANDLE *)((char *)this + 344);
  v7 = (void *)*((_QWORD *)this + 43);
  if ( v7 )
  {
    CloseHandle(v7);
    *v6 = 0;
  }
  *((_DWORD *)this + 94) = a2;
  if ( *((_DWORD *)this + 98) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 95) = 0;
    *((_DWORD *)this + 98) = 0;
    *((_DWORD *)this + 99) = 0;
    *((_QWORD *)this + 52) = 0;
  }
  v8 = CoGetCallContext(&GUID_0000013e_0000_0000_c000_000000000046, &ppInterface);
  v9 = v8;
  if ( v8 != -2147417833 )
  {
    if ( !v8 )
    {
      if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface) )
        goto LABEL_13;
      v9 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
      if ( (v9 & 0x80000000) == 0 )
      {
        v5 = 1;
        goto LABEL_13;
      }
LABEL_27:
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_64;
      v13 = 14;
      goto LABEL_30;
    }
    if ( v8 < 0 )
      goto LABEL_27;
  }
LABEL_13:
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, (PHANDLE)this + 43) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids);
    if ( *v6 )
    {
      CloseHandle(*v6);
      *v6 = 0;
    }
  }
  if ( ppInterface )
  {
    if ( v5 )
    {
      v5 = 0;
      v11 = (*(__int64 (**)(void))(*(_QWORD *)ppInterface + 40LL))();
      v9 = v11;
      if ( v11 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 16;
LABEL_25:
          v14 = (unsigned int)v11;
LABEL_31:
          WPP_SF_d(v12[2], v13, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids, v14);
          goto LABEL_64;
        }
        goto LABEL_64;
      }
    }
  }
  v11 = CSessionBaseRW::CacheUserSid((CServicingSession *)((char *)this + 8), *v6);
  v9 = v11;
  if ( v11 >= 0 )
  {
    if ( SetThreadToken(0, *v6) )
    {
      v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 224LL))(*((_QWORD *)this + 2));
      if ( v16 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids,
            (unsigned int)v16);
        (**((void (__fastcall ***)(char *, _QWORD))this + 1))((char *)this + 8, (unsigned int)v16);
      }
      if ( *((_DWORD *)this + 39)
        && GetDiskFreeSpaceExW(*((LPCWSTR *)this + 9), 0, &TotalNumberOfBytes, &TotalNumberOfFreeBytes)
        && TotalNumberOfFreeBytes.QuadPart <= TotalNumberOfBytes.QuadPart
        && TotalNumberOfBytes.QuadPart )
      {
        *((_DWORD *)this + 92) = 100
                               * (TotalNumberOfBytes.QuadPart - TotalNumberOfFreeBytes.QuadPart)
                               / TotalNumberOfBytes.QuadPart;
      }
      v11 = CSessionBaseRW::RetireFileVersionsOnTarget(
              (CServicingSession *)((char *)this + 8),
              *(_ULARGE_INTEGER *)((char *)this + 104),
              0,
              a2,
              *((_DWORD *)this + 11),
              0,
              1,
              (int *)this + 98,
              (int *)this + 99,
              (int *)this + 95,
              (__int64 *)this + 52,
              v22);
      v9 = v11;
      if ( v11 == -2147024784 || v11 == -2147023661 )
      {
        v9 = 0;
      }
      else if ( v11 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 20;
          goto LABEL_25;
        }
        goto LABEL_64;
      }
      if ( *((_DWORD *)this + 39)
        && GetDiskFreeSpaceExW(*((LPCWSTR *)this + 9), 0, &TotalNumberOfBytes, &TotalNumberOfFreeBytes)
        && TotalNumberOfFreeBytes.QuadPart <= TotalNumberOfBytes.QuadPart
        && TotalNumberOfBytes.QuadPart )
      {
        *((_DWORD *)this + 93) = 100
                               * (TotalNumberOfBytes.QuadPart - TotalNumberOfFreeBytes.QuadPart)
                               / TotalNumberOfBytes.QuadPart;
      }
      goto LABEL_64;
    }
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_64;
    v13 = 18;
LABEL_30:
    v14 = v9;
    goto LABEL_31;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 17;
    goto LABEL_25;
  }
LABEL_64:
  if ( SetThreadToken(0, 0) )
  {
LABEL_70:
    v17 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_71;
  }
  v17 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v18 = GetLastError();
    if ( v18 > 0 )
      v18 = (unsigned __int16)v18 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids,
      (unsigned int)v18);
    goto LABEL_70;
  }
LABEL_71:
  if ( v5 && v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 4) != 0 )
  {
    WPP_SF_s(v17[2], 22, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids, "!impersonating");
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147220478 && v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 4) != 0 )
    WPP_SF_s(
      v17[2],
      23,
      WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids,
      "SUCCEEDED(hr) || hr == FHE_E_TARGET_UNAVAILABLE");
  ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(&ppInterface);
  return v9;
}

```

## disassembly

```asm
0x180022d20  mov     [rsp-38h+arg_8], rbx
0x180022d25  mov     [rsp-38h+arg_10], r8
0x180022d2a  push    rbp
0x180022d2b  push    rsi
0x180022d2c  push    rdi
0x180022d2d  push    r12
0x180022d2f  push    r13
0x180022d31  push    r14
0x180022d33  push    r15
0x180022d35  mov     rbp, rsp
0x180022d38  sub     rsp, 70h
0x180022d3c  mov     r13d, edx
0x180022d3f  mov     rdi, rcx
0x180022d42  mov     [rbp+ppInterface], 0
0x180022d4a  mov     qword ptr [rbp+TotalNumberOfBytes], 0
0x180022d52  mov     qword ptr [rbp+TotalNumberOfFreeBytes], 0
0x180022d5a  xor     r12d, r12d
0x180022d5d  lea     r14, WPP_GLOBAL_Control
0x180022d64  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d6b  cmp     rcx, r14
0x180022d6e  jz      short loc_180022D8E
0x180022d70  test    byte ptr [rcx+1Ch], 8
0x180022d74  jz      short loc_180022D8E
0x180022d76  lea     edx, [r12+0Dh]
0x180022d7b  mov     r9d, r13d
0x180022d7e  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x180022d85  mov     rcx, [rcx+10h]
0x180022d89  call    WPP_SF_d
0x180022d8e  lea     rsi, [rdi+158h]
0x180022d95  mov     rcx, [rsi]; hObject
0x180022d98  test    rcx, rcx
0x180022d9b  jz      short loc_180022DA6
0x180022d9d  call    cs:__imp_CloseHandle
0x180022da3  mov     [rsi], r12
0x180022da6  mov     [rdi+178h], r13d
0x180022dad  lea     r15, [rdi+188h]
0x180022db4  cmp     dword ptr [r15], 7FFFFFFFh
0x180022dbb  jnz     short loc_180022DD5
0x180022dbd  mov     [rdi+17Ch], r12d
0x180022dc4  mov     [r15], r12d
0x180022dc7  mov     [rdi+18Ch], r12d
0x180022dce  mov     [rdi+1A0h], r12
0x180022dd5  lea     rdx, [rbp+ppInterface]; ppInterface
0x180022dd9  lea     rcx, _GUID_0000013e_0000_0000_c000_000000000046; riid
0x180022de0  call    cs:__imp_CoGetCallContext
0x180022de6  mov     ebx, eax
0x180022de8  cmp     eax, 80010117h
0x180022ded  jz      short loc_180022E2B
0x180022def  test    eax, eax
0x180022df1  jnz     loc_180022ECB
0x180022df7  mov     rcx, [rbp+ppInterface]
0x180022dfb  mov     rax, [rcx]
0x180022dfe  mov     rax, [rax+30h]
0x180022e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e07  test    eax, eax
0x180022e09  jnz     short loc_180022E2B
0x180022e0b  mov     rcx, [rbp+ppInterface]
0x180022e0f  mov     rax, [rcx]
0x180022e12  mov     rax, [rax+20h]
0x180022e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e1b  mov     ebx, eax
0x180022e1d  test    eax, eax
0x180022e1f  js      loc_180022ED1
0x180022e25  mov     r12d, 1
0x180022e2b  call    cs:__imp_GetCurrentThread
0x180022e31  mov     rcx, rax; ThreadHandle
0x180022e34  mov     r9, rsi; TokenHandle
0x180022e37  mov     edx, 0Ch; DesiredAccess
0x180022e3c  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180022e40  call    cs:__imp_OpenThreadToken
0x180022e46  test    eax, eax
0x180022e48  jnz     short loc_180022E84
0x180022e4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e51  cmp     rcx, r14
0x180022e54  jz      short loc_180022E6F
0x180022e56  test    byte ptr [rcx+1Ch], 2
0x180022e5a  jz      short loc_180022E6F
0x180022e5c  lea     edx, [rax+0Fh]
0x180022e5f  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x180022e66  mov     rcx, [rcx+10h]
0x180022e6a  call    WPP_SF_
0x180022e6f  mov     rcx, [rsi]; hObject
0x180022e72  test    rcx, rcx
0x180022e75  jz      short loc_180022E84
0x180022e77  call    cs:__imp_CloseHandle
0x180022e7d  mov     qword ptr [rsi], 0
0x180022e84  mov     rcx, [rbp+ppInterface]
0x180022e88  test    rcx, rcx
0x180022e8b  jz      short loc_180022F08
0x180022e8d  test    r12d, r12d
0x180022e90  jz      short loc_180022F08
0x180022e92  xor     r12d, r12d
0x180022e95  mov     rax, [rcx]
0x180022e98  mov     rax, [rax+28h]
0x180022e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ea1  mov     ebx, eax
0x180022ea3  test    eax, eax
0x180022ea5  jns     short loc_180022F08
0x180022ea7  mov     rcx, cs:WPP_GLOBAL_Control
0x180022eae  cmp     rcx, r14
0x180022eb1  jz      loc_18002311E
0x180022eb7  test    byte ptr [rcx+1Ch], 1
0x180022ebb  jz      loc_18002311E
0x180022ec1  lea     edx, [r12+10h]
0x180022ec6  mov     r9d, eax
0x180022ec9  jmp     short loc_180022EF3
0x180022ecb  jns     loc_180022E2B
0x180022ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ed8  cmp     rcx, r14
0x180022edb  jz      loc_18002311E
0x180022ee1  test    byte ptr [rcx+1Ch], 1
0x180022ee5  jz      loc_18002311E
0x180022eeb  mov     edx, 0Eh
0x180022ef0  mov     r9d, ebx
0x180022ef3  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x180022efa  mov     rcx, [rcx+10h]
0x180022efe  call    WPP_SF_d
0x180022f03  jmp     loc_18002311E
0x180022f08  lea     r14, [rdi+8]
0x180022f0c  mov     rdx, [rsi]; void *
0x180022f0f  mov     rcx, r14; this
0x180022f12  call    ?CacheUserSid@CSessionBaseRW@@IEAAJPEAX@Z; CSessionBaseRW::CacheUserSid(void *)
0x180022f17  mov     ebx, eax
0x180022f19  test    eax, eax
0x180022f1b  jns     short loc_180022F45
0x180022f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f24  lea     r14, WPP_GLOBAL_Control
0x180022f2b  cmp     rcx, r14
0x180022f2e  jz      loc_18002311E
0x180022f34  test    byte ptr [rcx+1Ch], 1
0x180022f38  jz      loc_18002311E
0x180022f3e  mov     edx, 11h
0x180022f43  jmp     short loc_180022EC6
0x180022f45  mov     rdx, [rsi]; Token
0x180022f48  xor     ecx, ecx; Thread
0x180022f4a  call    cs:__imp_SetThreadToken
0x180022f50  test    eax, eax
0x180022f52  jnz     short loc_180022F94
0x180022f54  call    cs:__imp_GetLastError
0x180022f5a  mov     ebx, eax
0x180022f5c  test    eax, eax
0x180022f5e  jle     short loc_180022F69
0x180022f60  movzx   ebx, ax
0x180022f63  or      ebx, 80070000h
0x180022f69  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f70  lea     r14, WPP_GLOBAL_Control
0x180022f77  cmp     rcx, r14
0x180022f7a  jz      loc_18002311E
0x180022f80  test    byte ptr [rcx+1Ch], 1
0x180022f84  jz      loc_18002311E
0x180022f8a  mov     edx, 12h
0x180022f8f  jmp     loc_180022EF0
0x180022f94  mov     rcx, [rdi+10h]
0x180022f98  mov     rax, [rcx]
0x180022f9b  mov     rax, [rax+0E0h]
0x180022fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fa7  mov     ebx, eax
0x180022fa9  test    eax, eax
0x180022fab  jns     short loc_180022FEE
0x180022fad  mov     rcx, cs:WPP_GLOBAL_Control
0x180022fb4  lea     rax, WPP_GLOBAL_Control
0x180022fbb  cmp     rcx, rax
0x180022fbe  jz      short loc_180022FDE
0x180022fc0  test    byte ptr [rcx+1Ch], 2
0x180022fc4  jz      short loc_180022FDE
0x180022fc6  mov     edx, 13h
0x180022fcb  mov     r9d, ebx
0x180022fce  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x180022fd5  mov     rcx, [rcx+10h]
0x180022fd9  call    WPP_SF_d
0x180022fde  mov     rax, [r14]
0x180022fe1  mov     edx, ebx
0x180022fe3  mov     rcx, r14
0x180022fe6  mov     rax, [rax]
0x180022fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fee  cmp     dword ptr [rdi+9Ch], 0
0x180022ff5  jz      short loc_180023034
0x180022ff7  lea     r9, [rbp+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x180022ffb  lea     r8, [rbp+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x180022fff  xor     edx, edx; lpFreeBytesAvailableToCaller
0x180023001  mov     rcx, [rdi+48h]; lpDirectoryName
0x180023005  call    cs:__imp_GetDiskFreeSpaceExW
0x18002300b  test    eax, eax
0x18002300d  jz      short loc_180023034
0x18002300f  mov     rcx, qword ptr [rbp+TotalNumberOfBytes]
0x180023013  cmp     qword ptr [rbp+TotalNumberOfFreeBytes], rcx
0x180023017  ja      short loc_180023034
0x180023019  test    rcx, rcx
0x18002301c  jz      short loc_180023034
0x18002301e  mov     rax, rcx
0x180023021  sub     rax, qword ptr [rbp+TotalNumberOfFreeBytes]
0x180023025  imul    rax, 64h ; 'd'
0x180023029  xor     edx, edx
0x18002302b  div     rcx
0x18002302e  mov     [rdi+170h], eax
0x180023034  lea     rax, [rdi+1A0h]
0x18002303b  lea     rdx, [rdi+17Ch]
0x180023042  lea     r8, [rdi+18Ch]
0x180023049  mov     rcx, [rbp+arg_10]
0x18002304d  mov     [rsp+70h+var_18], rcx; struct IFhEngineCleanupProgressEvent *
0x180023052  mov     [rsp+70h+var_20], rax; __int64 *
0x180023057  mov     [rsp+70h+var_28], rdx; int *
0x18002305c  mov     [rsp+70h+var_30], r8; int *
0x180023061  mov     [rsp+70h+var_38], r15; int *
0x180023066  mov     [rsp+70h+var_40], 1; int
0x18002306e  mov     [rsp+70h+var_48], 0; int
0x180023076  mov     eax, [rdi+2Ch]
0x180023079  mov     [rsp+70h+var_50], eax; int
0x18002307d  mov     r9d, r13d; unsigned int
0x180023080  xor     r8d, r8d; unsigned __int64
0x180023083  mov     rdx, [rdi+68h]; unsigned __int64
0x180023087  mov     rcx, r14; this
0x18002308a  call    ?RetireFileVersionsOnTarget@CSessionBaseRW@@IEAAJ_K0KJHHPEAJ11PEA_JPEAUIFhEngineCleanupProgressEvent@@@Z; CSessionBaseRW::RetireFileVersionsOnTarget(unsigned __int64,unsigned __int64,ulong,long,int,int,long *,long *,long *,__int64 *,IFhEngineCleanupProgressEvent *)
0x18002308f  mov     ebx, eax
0x180023091  cmp     eax, 80070070h
0x180023096  jz      short loc_1800230C6
0x180023098  cmp     eax, 800704D3h
0x18002309d  jz      short loc_1800230C6
0x18002309f  test    eax, eax
0x1800230a1  jns     short loc_1800230C8
0x1800230a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800230aa  lea     r14, WPP_GLOBAL_Control
0x1800230b1  cmp     rcx, r14
0x1800230b4  jz      short loc_18002311E
0x1800230b6  test    byte ptr [rcx+1Ch], 1
0x1800230ba  jz      short loc_18002311E
0x1800230bc  mov     edx, 14h
0x1800230c1  jmp     loc_180022EC6
0x1800230c6  xor     ebx, ebx
0x1800230c8  cmp     dword ptr [rdi+9Ch], 0
0x1800230cf  jz      short loc_180023117
0x1800230d1  lea     r9, [rbp+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x1800230d5  lea     r8, [rbp+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x1800230d9  xor     edx, edx; lpFreeBytesAvailableToCaller
0x1800230db  mov     rcx, [rdi+48h]; lpDirectoryName
0x1800230df  call    cs:__imp_GetDiskFreeSpaceExW
0x1800230e5  test    eax, eax
0x1800230e7  jz      short loc_180023117
0x1800230e9  mov     rcx, qword ptr [rbp+TotalNumberOfBytes]
0x1800230ed  cmp     qword ptr [rbp+TotalNumberOfFreeBytes], rcx
0x1800230f1  ja      short loc_180023117
0x1800230f3  lea     r14, WPP_GLOBAL_Control
0x1800230fa  test    rcx, rcx
0x1800230fd  jz      short loc_18002311E
0x1800230ff  mov     rax, rcx
0x180023102  sub     rax, qword ptr [rbp+TotalNumberOfFreeBytes]
0x180023106  imul    rax, 64h ; 'd'
0x18002310a  xor     edx, edx
0x18002310c  div     rcx
0x18002310f  mov     [rdi+174h], eax
0x180023115  jmp     short loc_18002311E
0x180023117  lea     r14, WPP_GLOBAL_Control
0x18002311e  xor     edx, edx; Token
0x180023120  xor     ecx, ecx; Thread
0x180023122  call    cs:__imp_SetThreadToken
0x180023128  test    eax, eax
0x18002312a  jnz     short loc_18002316F
0x18002312c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023133  cmp     rcx, r14
0x180023136  jz      short loc_180023176
0x180023138  test    byte ptr [rcx+1Ch], 1
0x18002313c  jz      short loc_180023176
0x18002313e  call    cs:__imp_GetLastError
0x180023144  test    eax, eax
0x180023146  jle     short loc_180023150
0x180023148  movzx   eax, ax
0x18002314b  or      eax, 80070000h
0x180023150  mov     edx, 15h
0x180023155  mov     r9d, eax
0x180023158  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x18002315f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023166  mov     rcx, [rcx+10h]
0x18002316a  call    WPP_SF_d
0x18002316f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023176  test    r12d, r12d
0x180023179  jz      short loc_1800231A9
0x18002317b  cmp     rcx, r14
0x18002317e  jz      short loc_1800231A9
0x180023180  test    byte ptr [rcx+1Ch], 4
0x180023184  jz      short loc_1800231A9
0x180023186  mov     edx, 16h
0x18002318b  lea     r9, aImpersonating; "!impersonating"
0x180023192  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x180023199  mov     rcx, [rcx+10h]
0x18002319d  call    WPP_SF_s
0x1800231a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800231a9  mov     edx, 80000000h
0x1800231ae  lea     eax, [rbx+rdx]
0x1800231b1  test    edx, eax
0x1800231b3  jnz     short loc_1800231E4
0x1800231b5  cmp     ebx, 80040402h
0x1800231bb  jz      short loc_1800231E4
0x1800231bd  cmp     rcx, r14
0x1800231c0  jz      short loc_1800231E4
0x1800231c2  test    byte ptr [rcx+1Ch], 4
0x1800231c6  jz      short loc_1800231E4
0x1800231c8  mov     edx, 17h
0x1800231cd  lea     r9, aSucceededHrHrF_0; "SUCCEEDED(hr) || hr == FHE_E_TARGET_UNA"...
0x1800231d4  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x1800231db  mov     rcx, [rcx+10h]
  ... truncated ...
```
