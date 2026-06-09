# CRdpPipeGfxPlugin::OnPipelineRestart(void)

- ea: `0x18005c160`
- end: `0x18005c71f`
- name: `?OnPipelineRestart@CRdpPipeGfxPlugin@@UEAAJXZ`
- size: `1471`
- prototype: `__int64 __fastcall(CRdpPipeGfxPlugin *this, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callees

- `0x1800015f0`
- `0x180002d8c`
- `0x180002ea4`
- `0x1800071c0`
- `0x1800071f0`
- `0x180012200`
- `0x18001e49c`
- `0x18005c160`
- `0x18005d73c`
- `0x18005d9a4`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c40b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c40b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c4c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c4c2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005c3f8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005c3f8`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18005c194`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18005c194`

## string_xrefs

- `0x18005c433`: `Fail to open Indirect Display device`
- `0x18005c231`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005c2f4`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005c383`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005c457`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005c4fb`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005c626`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005c54d`: `GfxPlugin`

## pseudocode

```c
__int64 __fastcall CRdpPipeGfxPlugin::OnPipelineRestart(CRdpPipeGfxPlugin *this, __int64 a2, __int64 a3)
{
  char *v4; // rcx
  __int64 v5; // rsi
  __int64 v6; // rdx
  signed int v7; // ebx
  __int64 v8; // r8
  int v9; // r9d
  int v10; // ecx
  int *v11; // rdx
  const char **v12; // rax
  __int64 v13; // rcx
  HANDLE FileW; // r14
  signed int LastError; // eax
  const char *v16; // r8
  int v17; // ecx
  int v18; // r9d
  int v19; // ecx
  int v20; // r9d
  const char **v22; // [rsp+40h] [rbp-19h]
  const char *v23; // [rsp+50h] [rbp-9h] BYREF
  __int64 v24; // [rsp+58h] [rbp-1h] BYREF
  const char *v25; // [rsp+60h] [rbp+7h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+78h] [rbp+1Fh]
  char *v28; // [rsp+C0h] [rbp+67h] BYREF
  const char *v29; // [rsp+C8h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+D0h] [rbp+77h] BYREF
  const char *v31; // [rsp+D8h] [rbp+7Fh] BYREF

  v30 = 0;
  v4 = (char *)this + 152;
  v28 = v4;
  if ( *((_DWORD *)v4 + 2) )
    PAL_System_CritSecEnter(*(_QWORD *)v4, a2, a3);
  if ( *((_QWORD *)this + 11) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v30, a2, a3);
    v5 = *((_QWORD *)this + 11);
    v30 = v5;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v30);
  }
  else
  {
    v5 = 0;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v28);
  CRdpPipeGfxPlugin::StopPipeMgrLite((CRdpPipeGfxPlugin *)((char *)this - 8));
  CRdpPipeGfxPlugin::UnloadRdpLite((CRdpPipeGfxPlugin *)((char *)this - 8));
  v7 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD))(**((_QWORD **)this + 12) + 64LL))(
         *((_QWORD *)this + 12),
         L"EnablePipeMgrLite",
         0);
  if ( v7 >= 0 )
  {
    if ( !v5 )
      goto LABEL_35;
    v13 = *((_QWORD *)this + 12);
    v27 = 0;
    *(_OWORD *)lpFileName = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, LPCWSTR *))(*(_QWORD *)v13 + 24LL))(
           v13,
           L"IddDeviceInstance",
           lpFileName);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_35;
      LODWORD(v28) = 1323;
      v31 = "Failed to get property CONN_PROPERTY_IDD_DEVICE_INSTANCE";
      v11 = (int *)byte_180199BB5;
      v25 = "OnPipelineRestart";
      v24 = (__int64)"clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v23 = "Error HResult failed";
      v22 = &v25;
      v12 = &v23;
      goto LABEL_9;
    }
    if ( LOWORD(lpFileName[0]) != 8 )
    {
      v7 = -2147418113;
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_35;
      LODWORD(v28) = 1329;
      v31 = "IDD device instance is not set properly";
      v11 = &dword_180199B64;
      v25 = "OnPipelineRestart";
      v24 = (__int64)"clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v23 = "Error condition failed";
      v22 = &v25;
      v12 = &v23;
      goto LABEL_9;
    }
    FileW = CreateFileW(lpFileName[1], 0x10000000u, 3u, 0, 4u, 0x800080u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_35;
        LODWORD(v28) = 1343;
        v31 = "Fail to open Indirect Display device";
        v11 = &dword_180199B14;
        v25 = "OnPipelineRestart";
        v24 = (__int64)"clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
        v23 = "Error HResult failed";
        v22 = &v25;
        v12 = &v23;
        goto LABEL_9;
      }
    }
    v7 = (*(__int64 (__fastcall **)(__int64, HANDLE))(*(_QWORD *)v5 + 32LL))(v5, FileW);
    if ( v7 < 0 )
    {
      CloseHandle(FileW);
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_35;
      LODWORD(v28) = 1350;
      v31 = "SetRdpIddHandle failed";
      v11 = &dword_180199AC4;
      v25 = "OnPipelineRestart";
      v24 = (__int64)"clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v23 = "Error HResult failed";
      v22 = &v25;
      v12 = &v23;
      goto LABEL_9;
    }
    v16 = "Checkpoint";
    if ( (unsigned int)dword_1801B76C8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801B76C8, 0x470000000000LL) )
    {
      v29 = "GfxPlugin";
      v28 = (char *)this + 196;
      v31 = "Stack";
      v25 = (const char *)0x1000000;
      v24 = (__int64)v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
        v17,
        (unsigned int)&word_180199A5E,
        (_DWORD)v16,
        v18,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&v31,
        (__int64)&v29,
        (__int64)&v28);
    }
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, const char *))(*(_QWORD *)v5 + 24LL))(v5, 1, v16);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_35;
      LODWORD(v28) = 1356;
      v31 = "Failed to Enable Gfx provider ";
      v11 = (int *)&word_180199A0E;
      v25 = "OnPipelineRestart";
      v24 = (__int64)"clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v23 = "Error HResult failed";
      v22 = &v25;
      v12 = &v23;
      goto LABEL_9;
    }
    if ( (unsigned int)dword_1801B76C8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801B76C8, 0x470000000000LL) )
    {
      LODWORD(v28) = 1;
      v29 = (char *)this + 196;
      v31 = "GfxPlugin";
      v23 = "Checkpoint";
      v25 = "Stack";
      v24 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        v19,
        (unsigned int)&byte_1801999A7,
        v8,
        v20,
        (__int64)&v23,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&v31,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  else
  {
    v10 = dword_1801B76C8;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v28) = 1313;
      v31 = "Failed to set property CONN_PROPERTY_ENABLE_PIPEMGR_LITE";
      v11 = (int *)byte_180199C05;
      v23 = "OnPipelineRestart";
      v24 = (__int64)"clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v25 = "Error HResult failed";
      v22 = &v23;
      v12 = &v25;
LABEL_9:
      LODWORD(v29) = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v10,
        (_DWORD)v11,
        v8,
        v9,
        (__int64)v12,
        (__int64)&v29,
        (__int64)&v24,
        (__int64)&v28,
        (__int64)v22,
        (__int64)&v31);
    }
  }
LABEL_35:
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v30, v6, v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005c160  push    rbp
0x18005c162  push    rbx
0x18005c163  push    rsi
0x18005c164  push    rdi
0x18005c165  push    r12
0x18005c167  push    r14
0x18005c169  lea     rbp, [rsp-2Fh]
0x18005c16e  sub     rsp, 88h
0x18005c175  mov     rdi, rcx
0x18005c178  mov     [rbp+57h+arg_10], 0
0x18005c180  add     rcx, 98h
0x18005c187  mov     [rbp+57h+arg_0], rcx
0x18005c18b  cmp     dword ptr [rcx+8], 0
0x18005c18f  jz      short loc_18005C19A
0x18005c191  mov     rcx, [rcx]
0x18005c194  call    cs:__imp_PAL_System_CritSecEnter
0x18005c19a  cmp     qword ptr [rdi+58h], 0
0x18005c19f  jnz     short loc_18005C1A5
0x18005c1a1  xor     esi, esi
0x18005c1a3  jmp     short loc_18005C1BF
0x18005c1a5  lea     rcx, [rbp+57h+arg_10]
0x18005c1a9  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18005c1ae  mov     rsi, [rdi+58h]
0x18005c1b2  lea     rcx, [rbp+57h+arg_10]
0x18005c1b6  mov     [rbp+57h+arg_10], rsi
0x18005c1ba  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18005c1bf  lea     rcx, [rbp+57h+arg_0]; this
0x18005c1c3  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18005c1c8  lea     rcx, [rdi-8]; this
0x18005c1cc  call    ?StopPipeMgrLite@CRdpPipeGfxPlugin@@QEAAXXZ; CRdpPipeGfxPlugin::StopPipeMgrLite(void)
0x18005c1d1  lea     rcx, [rdi-8]; this
0x18005c1d5  call    ?UnloadRdpLite@CRdpPipeGfxPlugin@@AEAAXXZ; CRdpPipeGfxPlugin::UnloadRdpLite(void)
0x18005c1da  mov     rcx, [rdi+60h]
0x18005c1de  lea     rdx, aEnablepipemgrl; "EnablePipeMgrLite"
0x18005c1e5  xor     r8d, r8d
0x18005c1e8  mov     rax, [rcx]
0x18005c1eb  mov     rax, [rax+40h]
0x18005c1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c1f4  mov     ebx, eax
0x18005c1f6  test    eax, eax
0x18005c1f8  jns     loc_18005C28A
0x18005c1fe  mov     ecx, cs:dword_1801B76C8
0x18005c204  cmp     ecx, 2
0x18005c207  jbe     loc_18005C704
0x18005c20d  lea     rax, aFailedToSetPro_3; "Failed to set property CONN_PROPERTY_EN"...
0x18005c214  mov     dword ptr [rbp+57h+arg_0], 521h
0x18005c21b  mov     [rbp+57h+arg_18], rax
0x18005c21f  lea     rdx, byte_180199C05
0x18005c226  lea     rax, aOnpipelinerest; "OnPipelineRestart"
0x18005c22d  mov     [rbp+57h+var_60], rax
0x18005c231  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18005c238  mov     [rbp+57h+var_58], rax
0x18005c23c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18005c243  mov     [rbp+57h+var_50], rax
0x18005c247  lea     rax, [rbp+57h+arg_18]
0x18005c24b  mov     [rsp+0B0h+var_68], rax
0x18005c250  lea     rax, [rbp+57h+var_60]
0x18005c254  mov     [rsp+0B0h+var_70], rax
0x18005c259  lea     rax, [rbp+57h+arg_0]
0x18005c25d  mov     [rsp+0B0h+var_78], rax
0x18005c262  lea     rax, [rbp+57h+var_58]
0x18005c266  mov     [rsp+0B0h+hTemplateFile], rax
0x18005c26b  lea     rax, [rbp+57h+arg_8]
0x18005c26f  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x18005c274  lea     rax, [rbp+57h+var_50]
0x18005c278  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x18005c27d  mov     dword ptr [rbp+57h+arg_8], ebx
0x18005c280  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18005c285  jmp     loc_18005C704
0x18005c28a  test    rsi, rsi
0x18005c28d  jz      loc_18005C704
0x18005c293  mov     rcx, [rdi+60h]
0x18005c297  lea     r8, [rbp+57h+lpFileName]
0x18005c29b  xor     eax, eax
0x18005c29d  lea     rdx, aIdddeviceinsta; "IddDeviceInstance"
0x18005c2a4  mov     [rbp+57h+var_38], rax
0x18005c2a8  xorps   xmm0, xmm0
0x18005c2ab  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x18005c2af  mov     rax, [rcx]
0x18005c2b2  mov     rax, [rax+18h]
0x18005c2b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c2bb  mov     ebx, eax
0x18005c2bd  test    eax, eax
0x18005c2bf  jns     short loc_18005C340
0x18005c2c1  mov     eax, cs:dword_1801B76C8
0x18005c2c7  cmp     eax, 2
0x18005c2ca  jbe     loc_18005C704
0x18005c2d0  lea     rax, aFailedToGetPro_0; "Failed to get property CONN_PROPERTY_ID"...
0x18005c2d7  mov     dword ptr [rbp+57h+arg_0], 52Bh
0x18005c2de  mov     [rbp+57h+arg_18], rax
0x18005c2e2  lea     rdx, byte_180199BB5
0x18005c2e9  lea     rax, aOnpipelinerest; "OnPipelineRestart"
0x18005c2f0  mov     [rbp+57h+var_50], rax
0x18005c2f4  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18005c2fb  mov     [rbp+57h+var_58], rax
0x18005c2ff  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18005c306  mov     [rbp+57h+var_60], rax
0x18005c30a  lea     rax, [rbp+57h+arg_18]
0x18005c30e  mov     [rsp+0B0h+var_68], rax
0x18005c313  lea     rax, [rbp+57h+var_50]
0x18005c317  mov     [rsp+0B0h+var_70], rax
0x18005c31c  lea     rax, [rbp+57h+arg_0]
0x18005c320  mov     [rsp+0B0h+var_78], rax
0x18005c325  lea     rax, [rbp+57h+var_58]
0x18005c329  mov     [rsp+0B0h+hTemplateFile], rax
0x18005c32e  lea     rax, [rbp+57h+arg_8]
0x18005c332  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x18005c337  lea     rax, [rbp+57h+var_60]
0x18005c33b  jmp     loc_18005C278
0x18005c340  cmp     word ptr [rbp+57h+lpFileName], 8
0x18005c345  jz      loc_18005C3CF
0x18005c34b  mov     eax, cs:dword_1801B76C8
0x18005c351  mov     ebx, 8000FFFFh
0x18005c356  cmp     eax, 2
0x18005c359  jbe     loc_18005C704
0x18005c35f  lea     rax, aIddDeviceInsta; "IDD device instance is not set properly"
0x18005c366  mov     dword ptr [rbp+57h+arg_0], 531h
0x18005c36d  mov     [rbp+57h+arg_18], rax
0x18005c371  lea     rdx, dword_180199B64
0x18005c378  lea     rax, aOnpipelinerest; "OnPipelineRestart"
0x18005c37f  mov     [rbp+57h+var_50], rax
0x18005c383  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18005c38a  mov     [rbp+57h+var_58], rax
0x18005c38e  lea     rax, aErrorCondition; "Error condition failed"
0x18005c395  mov     [rbp+57h+var_60], rax
0x18005c399  lea     rax, [rbp+57h+arg_18]
0x18005c39d  mov     [rsp+0B0h+var_68], rax
0x18005c3a2  lea     rax, [rbp+57h+var_50]
0x18005c3a6  mov     [rsp+0B0h+var_70], rax
0x18005c3ab  lea     rax, [rbp+57h+arg_0]
0x18005c3af  mov     [rsp+0B0h+var_78], rax
0x18005c3b4  lea     rax, [rbp+57h+var_58]
0x18005c3b8  mov     [rsp+0B0h+hTemplateFile], rax
0x18005c3bd  lea     rax, [rbp+57h+arg_8]
0x18005c3c1  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x18005c3c6  lea     rax, [rbp+57h+var_60]
0x18005c3ca  jmp     loc_18005C278
0x18005c3cf  mov     rcx, [rbp+57h+lpFileName+8]; lpFileName
0x18005c3d3  xor     r9d, r9d; lpSecurityAttributes
0x18005c3d6  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18005c3df  mov     edx, 10000000h; dwDesiredAccess
0x18005c3e4  mov     [rsp+0B0h+dwFlagsAndAttributes], 800080h; dwFlagsAndAttributes
0x18005c3ec  mov     [rsp+0B0h+dwCreationDisposition], 4; dwCreationDisposition
0x18005c3f4  lea     r8d, [r9+3]; dwShareMode
0x18005c3f8  call    cs:__imp_CreateFileW
0x18005c3fe  mov     r14, rax
0x18005c401  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005c405  jnz     loc_18005C4A3
0x18005c40b  call    cs:__imp_GetLastError
0x18005c411  mov     ebx, eax
0x18005c413  test    eax, eax
0x18005c415  jle     short loc_18005C420
0x18005c417  movzx   ebx, ax
0x18005c41a  or      ebx, 80070000h
0x18005c420  test    ebx, ebx
0x18005c422  jns     short loc_18005C4A3
0x18005c424  mov     eax, cs:dword_1801B76C8
0x18005c42a  cmp     eax, 2
0x18005c42d  jbe     loc_18005C704
0x18005c433  lea     rax, aFailToOpenIndi; "Fail to open Indirect Display device"
0x18005c43a  mov     dword ptr [rbp+57h+arg_0], 53Fh
0x18005c441  mov     [rbp+57h+arg_18], rax
0x18005c445  lea     rdx, dword_180199B14
0x18005c44c  lea     rax, aOnpipelinerest; "OnPipelineRestart"
0x18005c453  mov     [rbp+57h+var_50], rax
0x18005c457  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18005c45e  mov     [rbp+57h+var_58], rax
0x18005c462  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18005c469  mov     [rbp+57h+var_60], rax
0x18005c46d  lea     rax, [rbp+57h+arg_18]
0x18005c471  mov     [rsp+0B0h+var_68], rax
0x18005c476  lea     rax, [rbp+57h+var_50]
0x18005c47a  mov     [rsp+0B0h+var_70], rax
0x18005c47f  lea     rax, [rbp+57h+arg_0]
0x18005c483  mov     [rsp+0B0h+var_78], rax
0x18005c488  lea     rax, [rbp+57h+var_58]
0x18005c48c  mov     [rsp+0B0h+hTemplateFile], rax
0x18005c491  lea     rax, [rbp+57h+arg_8]
0x18005c495  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x18005c49a  lea     rax, [rbp+57h+var_60]
0x18005c49e  jmp     loc_18005C278
0x18005c4a3  mov     rax, [rsi]
0x18005c4a6  mov     rdx, r14
0x18005c4a9  mov     rcx, rsi
0x18005c4ac  mov     rax, [rax+20h]
0x18005c4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c4b5  mov     ebx, eax
0x18005c4b7  test    eax, eax
0x18005c4b9  jns     loc_18005C547
0x18005c4bf  mov     rcx, r14; hObject
0x18005c4c2  call    cs:__imp_CloseHandle
0x18005c4c8  mov     eax, cs:dword_1801B76C8
0x18005c4ce  cmp     eax, 2
0x18005c4d1  jbe     loc_18005C704
0x18005c4d7  lea     rax, aSetrdpiddhandl_0; "SetRdpIddHandle failed"
0x18005c4de  mov     dword ptr [rbp+57h+arg_0], 546h
0x18005c4e5  mov     [rbp+57h+arg_18], rax
0x18005c4e9  lea     rdx, dword_180199AC4
0x18005c4f0  lea     rax, aOnpipelinerest; "OnPipelineRestart"
0x18005c4f7  mov     [rbp+57h+var_50], rax
0x18005c4fb  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18005c502  mov     [rbp+57h+var_58], rax
0x18005c506  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18005c50d  mov     [rbp+57h+var_60], rax
0x18005c511  lea     rax, [rbp+57h+arg_18]
0x18005c515  mov     [rsp+0B0h+var_68], rax
0x18005c51a  lea     rax, [rbp+57h+var_50]
0x18005c51e  mov     [rsp+0B0h+var_70], rax
0x18005c523  lea     rax, [rbp+57h+arg_0]
0x18005c527  mov     [rsp+0B0h+var_78], rax
0x18005c52c  lea     rax, [rbp+57h+var_58]
0x18005c530  mov     [rsp+0B0h+hTemplateFile], rax
0x18005c535  lea     rax, [rbp+57h+arg_8]
0x18005c539  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x18005c53e  lea     rax, [rbp+57h+var_60]
0x18005c542  jmp     loc_18005C278
0x18005c547  mov     eax, cs:dword_1801B76C8
0x18005c54d  lea     r14, aGfxplugin; "GfxPlugin"
0x18005c554  lea     r12, aStack; "Stack"
0x18005c55b  lea     r8, aCheckpoint; "Checkpoint"
0x18005c562  cmp     eax, 4
0x18005c565  jbe     short loc_18005C5D9
0x18005c567  mov     rdx, 470000000000h
0x18005c571  lea     rcx, dword_1801B76C8
0x18005c578  call    _tlgKeywordOn
0x18005c57d  test    al, al
0x18005c57f  jz      short loc_18005C5D9
0x18005c581  lea     rax, [rdi+0C4h]
0x18005c588  mov     [rbp+57h+arg_8], r14
0x18005c58c  mov     [rbp+57h+arg_0], rax
0x18005c590  lea     rdx, word_180199A5E
0x18005c597  lea     rax, [rbp+57h+arg_0]
0x18005c59b  mov     [rbp+57h+arg_18], r12
0x18005c59f  mov     [rsp+0B0h+var_70], rax
0x18005c5a4  lea     rax, [rbp+57h+arg_8]
0x18005c5a8  mov     [rsp+0B0h+var_78], rax
0x18005c5ad  lea     rax, [rbp+57h+arg_18]
0x18005c5b1  mov     [rsp+0B0h+hTemplateFile], rax
0x18005c5b6  lea     rax, [rbp+57h+var_50]
0x18005c5ba  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x18005c5bf  lea     rax, [rbp+57h+var_58]
0x18005c5c3  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x18005c5c8  mov     [rbp+57h+var_50], 1000000h
0x18005c5d0  mov     [rbp+57h+var_58], r8
0x18005c5d4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x18005c5d9  mov     rax, [rsi]
0x18005c5dc  mov     edx, 1
0x18005c5e1  mov     rcx, rsi
0x18005c5e4  mov     rax, [rax+18h]
0x18005c5e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c5ed  mov     ebx, eax
0x18005c5ef  test    eax, eax
0x18005c5f1  mov     eax, cs:dword_1801B76C8
0x18005c5f7  jns     short loc_18005C672
0x18005c5f9  cmp     eax, 2
0x18005c5fc  jbe     loc_18005C704
0x18005c602  lea     rax, aFailedToEnable_1; "Failed to Enable Gfx provider "
0x18005c609  mov     dword ptr [rbp+57h+arg_0], 54Ch
0x18005c610  mov     [rbp+57h+arg_18], rax
0x18005c614  lea     rdx, word_180199A0E
0x18005c61b  lea     rax, aOnpipelinerest; "OnPipelineRestart"
0x18005c622  mov     [rbp+57h+var_50], rax
0x18005c626  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18005c62d  mov     [rbp+57h+var_58], rax
0x18005c631  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18005c638  mov     [rbp+57h+var_60], rax
0x18005c63c  lea     rax, [rbp+57h+arg_18]
0x18005c640  mov     [rsp+0B0h+var_68], rax
0x18005c645  lea     rax, [rbp+57h+var_50]
0x18005c649  mov     [rsp+0B0h+var_70], rax
0x18005c64e  lea     rax, [rbp+57h+arg_0]
0x18005c652  mov     [rsp+0B0h+var_78], rax
0x18005c657  lea     rax, [rbp+57h+var_58]
0x18005c65b  mov     [rsp+0B0h+hTemplateFile], rax
0x18005c660  lea     rax, [rbp+57h+arg_8]
0x18005c664  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x18005c669  lea     rax, [rbp+57h+var_60]
0x18005c66d  jmp     loc_18005C278
0x18005c672  cmp     eax, 4
0x18005c675  jbe     loc_18005C704
0x18005c67b  mov     rdx, 470000000000h
0x18005c685  lea     rcx, dword_1801B76C8
0x18005c68c  call    _tlgKeywordOn
0x18005c691  test    al, al
0x18005c693  jz      short loc_18005C704
0x18005c695  lea     rax, [rdi+0C4h]
0x18005c69c  mov     dword ptr [rbp+57h+arg_0], 1
0x18005c6a3  mov     [rbp+57h+arg_8], rax
0x18005c6a7  lea     rdx, byte_1801999A7
0x18005c6ae  lea     rax, aCheckpoint; "Checkpoint"
0x18005c6b5  mov     [rbp+57h+arg_18], r14
0x18005c6b9  mov     [rbp+57h+var_60], rax
0x18005c6bd  lea     rax, [rbp+57h+arg_0]
0x18005c6c1  mov     [rsp+0B0h+var_68], rax
0x18005c6c6  lea     rax, [rbp+57h+arg_8]
0x18005c6ca  mov     [rsp+0B0h+var_70], rax
0x18005c6cf  lea     rax, [rbp+57h+arg_18]
0x18005c6d3  mov     [rsp+0B0h+var_78], rax
0x18005c6d8  lea     rax, [rbp+57h+var_50]
0x18005c6dc  mov     [rsp+0B0h+hTemplateFile], rax
  ... truncated ...
```
