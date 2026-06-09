# CServicingSession::CleanupStagingArea(IFhEngineCleanupProgressEvent *)

- ea: `0x1800228b0`
- end: `0x180022d11`
- name: `?CleanupStagingArea@CServicingSession@@UEAAJPEAUIFhEngineCleanupProgressEvent@@@Z`
- size: `1121`
- prototype: `__int64 __fastcall(CServicingSession *this, struct IFhEngineCleanupProgressEvent *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800031b0`
- `0x1800077f0`
- `0x180007818`
- `0x180009258`
- `0x1800093a8`
- `0x180009404`
- `0x18000c004`
- `0x18000cafc`
- `0x180012278`
- `0x1800127b0`
- `0x1800228b0`
- `0x180030b88`
- `0x180034010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180022aba`
- `ADVAPI32!SetThreadToken` at `0x180022c3a`
- `ADVAPI32!SetThreadToken` at `0x180022aba`
- `ADVAPI32!SetThreadToken` at `0x180022c3a`
- `ADVAPI32!OpenThreadToken` at `0x1800229b3`
- `ADVAPI32!OpenThreadToken` at `0x1800229b3`
- `KERNEL32!GetLastError` at `0x180022ac4`
- `KERNEL32!GetLastError` at `0x180022c56`
- `KERNEL32!GetLastError` at `0x180022ac4`
- `KERNEL32!GetLastError` at `0x180022c56`
- `KERNEL32!CloseHandle` at `0x180022914`
- `KERNEL32!CloseHandle` at `0x1800229ea`
- `KERNEL32!CloseHandle` at `0x180022914`
- `KERNEL32!CloseHandle` at `0x1800229ea`
- `KERNEL32!GetCurrentThread` at `0x18002299e`
- `KERNEL32!GetCurrentThread` at `0x18002299e`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180022951`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180022951`

## string_xrefs

- `0x180022ca3`: `!impersonating`
- `0x180022c11`: `Unexpected error during deletion of the staging area`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 __fastcall CServicingSession::CleanupStagingArea(
        CServicingSession *this,
        struct IFhEngineCleanupProgressEvent *a2)
{
  int v4; // r15d
  HANDLE *v5; // rdi
  void *v6; // rcx
  HRESULT v7; // eax
  signed int v8; // ebx
  HANDLE CurrentThread; // rax
  int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  signed int LastError; // eax
  int v15; // eax
  int v16; // ecx
  int v17; // eax
  PVOID *v18; // rcx
  PVOID *v19; // rcx
  signed int v20; // eax
  void *ppInterface; // [rsp+70h] [rbp+8h] BYREF
  char v23; // [rsp+80h] [rbp+18h] BYREF

  ppInterface = 0;
  v4 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids);
  v5 = (HANDLE *)((char *)this + 344);
  v6 = (void *)*((_QWORD *)this + 43);
  if ( v6 )
  {
    CloseHandle(v6);
    *v5 = 0;
  }
  if ( *((_DWORD *)this + 96) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 97) = 0;
    *((_DWORD *)this + 96) = 0;
    *((_QWORD *)this + 50) = 0;
    *((_QWORD *)this + 51) = 0;
  }
  v7 = CoGetCallContext(&GUID_0000013e_0000_0000_c000_000000000046, &ppInterface);
  v8 = v7;
  if ( v7 != -2147417833 )
  {
    if ( !v7 )
    {
      if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface) )
        goto LABEL_13;
      v8 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
      if ( v8 >= 0 )
      {
        v4 = 1;
        goto LABEL_13;
      }
LABEL_27:
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_58;
      v12 = 25;
      goto LABEL_30;
    }
    if ( v7 < 0 )
      goto LABEL_27;
  }
LABEL_13:
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, (PHANDLE)this + 43) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids);
    if ( *v5 )
    {
      CloseHandle(*v5);
      *v5 = 0;
    }
  }
  if ( ppInterface )
  {
    if ( v4 )
    {
      v4 = 0;
      v10 = (*(__int64 (**)(void))(*(_QWORD *)ppInterface + 40LL))();
      v8 = v10;
      if ( v10 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v12 = 27;
LABEL_25:
          v13 = (unsigned int)v10;
LABEL_31:
          WPP_SF_d(v11[2], v12, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids, v13);
          goto LABEL_58;
        }
        goto LABEL_58;
      }
    }
  }
  v10 = CSessionBaseRW::CacheUserSid((CServicingSession *)((char *)this + 8), *v5);
  v8 = v10;
  if ( v10 >= 0 )
  {
    if ( SetThreadToken(0, *v5) )
    {
      v10 = CSessionBaseRW::CleanupStagingArea(
              (CServicingSession *)((char *)this + 8),
              (int *)this + 96,
              (__int64 *)this + 50,
              a2);
      v8 = v10;
      if ( v10 >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids,
            *((_QWORD *)this + 8));
        v15 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                &v23,
                (char *)this + 64);
        v17 = FheFileOperations::PerformDirectoryTreeOperation(
                v16,
                v15,
                0,
                (int)this + 160,
                (__int64)this + 388,
                (__int64)this + 408,
                (__int64)a2);
        v8 = v17;
        if ( v17 < 0 )
        {
          v18 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              32,
              (int)WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids,
              *((_QWORD *)this + 8),
              v17);
            v18 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v8 != -2147024864 && v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 4) != 0 )
            WPP_SF_ss(
              (int)v18[2],
              33,
              (int)WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids,
              (int)"hr == HRESULT_FROM_WIN32(ERROR_SHARING_VIOLATION)",
              (__int64)"Unexpected error during deletion of the staging area");
          v8 = 0;
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v12 = 30;
          goto LABEL_25;
        }
      }
      goto LABEL_58;
    }
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_58;
    v12 = 29;
LABEL_30:
    v13 = (unsigned int)v8;
    goto LABEL_31;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = 28;
    goto LABEL_25;
  }
LABEL_58:
  if ( SetThreadToken(0, 0) )
  {
LABEL_64:
    v19 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_65;
  }
  v19 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v20 = GetLastError();
    if ( v20 > 0 )
      v20 = (unsigned __int16)v20 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids,
      (unsigned int)v20);
    goto LABEL_64;
  }
LABEL_65:
  if ( v4 && v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 4) != 0 )
  {
    WPP_SF_s(v19[2], 35, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids, "!impersonating");
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 < 0 && v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 4) != 0 )
    WPP_SF_s(v19[2], 36, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids, "SUCCEEDED(hr)");
  ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(&ppInterface);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800228b0  mov     [rsp+arg_8], rbx
0x1800228b5  mov     [rsp+arg_18], rbp
0x1800228ba  push    rsi
0x1800228bb  push    rdi
0x1800228bc  push    r12
0x1800228be  push    r14
0x1800228c0  push    r15
0x1800228c2  sub     rsp, 40h
0x1800228c6  mov     r12, rdx
0x1800228c9  mov     rsi, rcx
0x1800228cc  mov     [rsp+68h+ppInterface], 0
0x1800228d5  xor     r15d, r15d
0x1800228d8  lea     rbp, WPP_GLOBAL_Control
0x1800228df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228e6  cmp     rcx, rbp
0x1800228e9  jz      short loc_180022905
0x1800228eb  test    byte ptr [rcx+1Ch], 8
0x1800228ef  jz      short loc_180022905
0x1800228f1  lea     edx, [r15+18h]
0x1800228f5  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x1800228fc  mov     rcx, [rcx+10h]
0x180022900  call    WPP_SF_
0x180022905  lea     rdi, [rsi+158h]
0x18002290c  mov     rcx, [rdi]; hObject
0x18002290f  test    rcx, rcx
0x180022912  jz      short loc_18002291D
0x180022914  call    cs:__imp_CloseHandle
0x18002291a  mov     [rdi], r15
0x18002291d  lea     r14, [rsi+180h]
0x180022924  cmp     dword ptr [r14], 7FFFFFFFh
0x18002292b  jnz     short loc_180022945
0x18002292d  mov     [rsi+184h], r15d
0x180022934  mov     [r14], r15d
0x180022937  mov     [rsi+190h], r15
0x18002293e  mov     [rsi+198h], r15
0x180022945  lea     rdx, [rsp+68h+ppInterface]; ppInterface
0x18002294a  lea     rcx, _GUID_0000013e_0000_0000_c000_000000000046; riid
0x180022951  call    cs:__imp_CoGetCallContext
0x180022957  mov     ebx, eax
0x180022959  cmp     eax, 80010117h
0x18002295e  jz      short loc_18002299E
0x180022960  test    eax, eax
0x180022962  jnz     loc_180022A3E
0x180022968  mov     rcx, [rsp+68h+ppInterface]
0x18002296d  mov     rax, [rcx]
0x180022970  mov     rax, [rax+30h]
0x180022974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022979  test    eax, eax
0x18002297b  jnz     short loc_18002299E
0x18002297d  mov     rcx, [rsp+68h+ppInterface]
0x180022982  mov     rax, [rcx]
0x180022985  mov     rax, [rax+20h]
0x180022989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002298e  mov     ebx, eax
0x180022990  test    eax, eax
0x180022992  js      loc_180022A44
0x180022998  mov     r15d, 1
0x18002299e  call    cs:__imp_GetCurrentThread
0x1800229a4  mov     rcx, rax; ThreadHandle
0x1800229a7  mov     r9, rdi; TokenHandle
0x1800229aa  mov     edx, 0Ch; DesiredAccess
0x1800229af  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x1800229b3  call    cs:__imp_OpenThreadToken
0x1800229b9  test    eax, eax
0x1800229bb  jnz     short loc_1800229F7
0x1800229bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229c4  cmp     rcx, rbp
0x1800229c7  jz      short loc_1800229E2
0x1800229c9  test    byte ptr [rcx+1Ch], 2
0x1800229cd  jz      short loc_1800229E2
0x1800229cf  lea     edx, [rax+1Ah]
0x1800229d2  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x1800229d9  mov     rcx, [rcx+10h]
0x1800229dd  call    WPP_SF_
0x1800229e2  mov     rcx, [rdi]; hObject
0x1800229e5  test    rcx, rcx
0x1800229e8  jz      short loc_1800229F7
0x1800229ea  call    cs:__imp_CloseHandle
0x1800229f0  mov     qword ptr [rdi], 0
0x1800229f7  mov     rcx, [rsp+68h+ppInterface]
0x1800229fc  test    rcx, rcx
0x1800229ff  jz      short loc_180022A7B
0x180022a01  test    r15d, r15d
0x180022a04  jz      short loc_180022A7B
0x180022a06  xor     r15d, r15d
0x180022a09  mov     rax, [rcx]
0x180022a0c  mov     rax, [rax+28h]
0x180022a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a15  mov     ebx, eax
0x180022a17  test    eax, eax
0x180022a19  jns     short loc_180022A7B
0x180022a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a22  cmp     rcx, rbp
0x180022a25  jz      loc_180022C36
0x180022a2b  test    byte ptr [rcx+1Ch], 1
0x180022a2f  jz      loc_180022C36
0x180022a35  lea     edx, [r15+1Bh]
0x180022a39  mov     r9d, eax
0x180022a3c  jmp     short loc_180022A66
0x180022a3e  jns     loc_18002299E
0x180022a44  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a4b  cmp     rcx, rbp
0x180022a4e  jz      loc_180022C36
0x180022a54  test    byte ptr [rcx+1Ch], 1
0x180022a58  jz      loc_180022C36
0x180022a5e  mov     edx, 19h
0x180022a63  mov     r9d, ebx
0x180022a66  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x180022a6d  mov     rcx, [rcx+10h]
0x180022a71  call    WPP_SF_d
0x180022a76  jmp     loc_180022C36
0x180022a7b  mov     rdx, [rdi]; void *
0x180022a7e  lea     rcx, [rsi+8]; this
0x180022a82  call    ?CacheUserSid@CSessionBaseRW@@IEAAJPEAX@Z; CSessionBaseRW::CacheUserSid(void *)
0x180022a87  mov     ebx, eax
0x180022a89  test    eax, eax
0x180022a8b  jns     short loc_180022AB5
0x180022a8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a94  lea     rbp, WPP_GLOBAL_Control
0x180022a9b  cmp     rcx, rbp
0x180022a9e  jz      loc_180022C36
0x180022aa4  test    byte ptr [rcx+1Ch], 1
0x180022aa8  jz      loc_180022C36
0x180022aae  mov     edx, 1Ch
0x180022ab3  jmp     short loc_180022A39
0x180022ab5  mov     rdx, [rdi]; Token
0x180022ab8  xor     ecx, ecx; Thread
0x180022aba  call    cs:__imp_SetThreadToken
0x180022ac0  test    eax, eax
0x180022ac2  jnz     short loc_180022B04
0x180022ac4  call    cs:__imp_GetLastError
0x180022aca  mov     ebx, eax
0x180022acc  test    eax, eax
0x180022ace  jle     short loc_180022AD9
0x180022ad0  movzx   ebx, ax
0x180022ad3  or      ebx, 80070000h
0x180022ad9  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ae0  lea     rbp, WPP_GLOBAL_Control
0x180022ae7  cmp     rcx, rbp
0x180022aea  jz      loc_180022C36
0x180022af0  test    byte ptr [rcx+1Ch], 1
0x180022af4  jz      loc_180022C36
0x180022afa  mov     edx, 1Dh
0x180022aff  jmp     loc_180022A63
0x180022b04  lea     r8, [rsi+190h]; __int64 *
0x180022b0b  mov     r9, r12; struct IFhEngineCleanupProgressEvent *
0x180022b0e  mov     rdx, r14; int *
0x180022b11  lea     rcx, [rsi+8]; this
0x180022b15  call    ?CleanupStagingArea@CSessionBaseRW@@IEAAJPEAJPEA_JPEAUIFhEngineCleanupProgressEvent@@@Z; CSessionBaseRW::CleanupStagingArea(long *,__int64 *,IFhEngineCleanupProgressEvent *)
0x180022b1a  mov     ebx, eax
0x180022b1c  test    eax, eax
0x180022b1e  jns     short loc_180022B4B
0x180022b20  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b27  lea     rbp, WPP_GLOBAL_Control
0x180022b2e  cmp     rcx, rbp
0x180022b31  jz      loc_180022C36
0x180022b37  test    byte ptr [rcx+1Ch], 1
0x180022b3b  jz      loc_180022C36
0x180022b41  mov     edx, 1Eh
0x180022b46  jmp     loc_180022A39
0x180022b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b52  lea     rbp, WPP_GLOBAL_Control
0x180022b59  cmp     rcx, rbp
0x180022b5c  jz      short loc_180022B7D
0x180022b5e  test    byte ptr [rcx+1Ch], 8
0x180022b62  jz      short loc_180022B7D
0x180022b64  mov     edx, 1Fh
0x180022b69  mov     r9, [rsi+40h]
0x180022b6d  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x180022b74  mov     rcx, [rcx+10h]
0x180022b78  call    WPP_SF_S
0x180022b7d  lea     rbx, [rsi+198h]
0x180022b84  lea     rdi, [rsi+184h]
0x180022b8b  lea     rdx, [rsi+40h]
0x180022b8f  lea     rcx, [rsp+68h+arg_10]
0x180022b97  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180022b9c  mov     rdx, rax
0x180022b9f  mov     [rsp+68h+var_38], r12
0x180022ba4  mov     [rsp+68h+var_40], rbx
0x180022ba9  mov     [rsp+68h+var_48], rdi
0x180022bae  lea     r9, [rsi+0A0h]
0x180022bb5  xor     r8d, r8d
0x180022bb8  call    ?PerformDirectoryTreeOperation@FheFileOperations@@YAJW4DirectoryTreeOp@1@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HPEAHPEAJPEA_JPEAUIFhEngineCleanupProgressEvent@@@Z; FheFileOperations::PerformDirectoryTreeOperation(FheFileOperations::DirectoryTreeOp,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int,int *,long *,__int64 *,IFhEngineCleanupProgressEvent *)
0x180022bbd  mov     ebx, eax
0x180022bbf  test    eax, eax
0x180022bc1  jns     short loc_180022C36
0x180022bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bca  cmp     rcx, rbp
0x180022bcd  jz      short loc_180022BF9
0x180022bcf  test    byte ptr [rcx+1Ch], 1
0x180022bd3  jz      short loc_180022BF9
0x180022bd5  mov     edx, 20h ; ' '
0x180022bda  mov     dword ptr [rsp+68h+var_48], eax
0x180022bde  mov     r9, [rsi+40h]
0x180022be2  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x180022be9  mov     rcx, [rcx+10h]
0x180022bed  call    WPP_SF_Sd
0x180022bf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bf9  cmp     ebx, 80070020h
0x180022bff  jz      short loc_180022C34
0x180022c01  cmp     rcx, rbp
0x180022c04  jz      short loc_180022C34
0x180022c06  test    byte ptr [rcx+1Ch], 4
0x180022c0a  jz      short loc_180022C34
0x180022c0c  mov     edx, 21h ; '!'
0x180022c11  lea     rax, aUnexpectedErro; "Unexpected error during deletion of the"...
0x180022c18  mov     [rsp+68h+var_48], rax
0x180022c1d  lea     r9, aHrHresultFromW; "hr == HRESULT_FROM_WIN32(ERROR_SHARING_"...
0x180022c24  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x180022c2b  mov     rcx, [rcx+10h]
0x180022c2f  call    WPP_SF_ss
0x180022c34  xor     ebx, ebx
0x180022c36  xor     edx, edx; Token
0x180022c38  xor     ecx, ecx; Thread
0x180022c3a  call    cs:__imp_SetThreadToken
0x180022c40  test    eax, eax
0x180022c42  jnz     short loc_180022C87
0x180022c44  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c4b  cmp     rcx, rbp
0x180022c4e  jz      short loc_180022C8E
0x180022c50  test    byte ptr [rcx+1Ch], 1
0x180022c54  jz      short loc_180022C8E
0x180022c56  call    cs:__imp_GetLastError
0x180022c5c  test    eax, eax
0x180022c5e  jle     short loc_180022C68
0x180022c60  movzx   eax, ax
0x180022c63  or      eax, 80070000h
0x180022c68  mov     edx, 22h ; '"'
0x180022c6d  mov     r9d, eax
0x180022c70  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x180022c77  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c7e  mov     rcx, [rcx+10h]
0x180022c82  call    WPP_SF_d
0x180022c87  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c8e  test    r15d, r15d
0x180022c91  jz      short loc_180022CC1
0x180022c93  cmp     rcx, rbp
0x180022c96  jz      short loc_180022CC1
0x180022c98  test    byte ptr [rcx+1Ch], 4
0x180022c9c  jz      short loc_180022CC1
0x180022c9e  mov     edx, 23h ; '#'
0x180022ca3  lea     r9, aImpersonating; "!impersonating"
0x180022caa  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x180022cb1  mov     rcx, [rcx+10h]
0x180022cb5  call    WPP_SF_s
0x180022cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180022cc1  test    ebx, ebx
0x180022cc3  jns     short loc_180022CEC
0x180022cc5  cmp     rcx, rbp
0x180022cc8  jz      short loc_180022CEC
0x180022cca  test    byte ptr [rcx+1Ch], 4
0x180022cce  jz      short loc_180022CEC
0x180022cd0  mov     edx, 24h ; '$'
0x180022cd5  lea     r9, aSucceededHr; "SUCCEEDED(hr)"
0x180022cdc  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x180022ce3  mov     rcx, [rcx+10h]
0x180022ce7  call    WPP_SF_s
0x180022cec  lea     rcx, [rsp+68h+ppInterface]
0x180022cf1  call    ??1?$CComPtrBase@UIFhScopeIterator@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(void)
0x180022cf6  mov     eax, ebx
0x180022cf8  lea     r11, [rsp+68h+var_28]
0x180022cfd  mov     rbx, [r11+38h]
0x180022d01  mov     rbp, [r11+48h]
0x180022d05  mov     rsp, r11
0x180022d08  pop     r15
0x180022d0a  pop     r14
0x180022d0c  pop     r12
0x180022d0e  pop     rdi
0x180022d0f  pop     rsi
0x180022d10  retn
```
