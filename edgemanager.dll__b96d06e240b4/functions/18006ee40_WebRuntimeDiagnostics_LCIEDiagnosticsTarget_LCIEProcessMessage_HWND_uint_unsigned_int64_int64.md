# WebRuntimeDiagnostics::LCIEDiagnosticsTarget::LCIEProcessMessage(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18006ee40`
- end: `0x18006f09a`
- name: `?LCIEProcessMessage@LCIEDiagnosticsTarget@WebRuntimeDiagnostics@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `602`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180018b30`
- `0x18002b5a0`
- `0x180037b5c`
- `0x18006ea64`
- `0x18006ee40`
- `0x18006f2c4`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18006ef1c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18006ef4a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18006efe5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18006f011`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18006f078`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18006ef1c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18006ef4a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18006efe5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18006f011`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18006f078`
- `edgeIso!__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x18006ee9e`
- `edgeIso!__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x18006ee9e`
- `edgeIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18006ef86`
- `edgeIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18006ef86`
- `edgeIso!__imp_?IsoReleaseThread@@YAKK@Z` at `0x18006ef6f`
- `edgeIso!__imp_?IsoReleaseThread@@YAKK@Z` at `0x18006ef6f`
- `edgeIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x18006ee79`
- `edgeIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x18006ee79`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18006ef8e`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18006ef8e`
- `edgeIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x18006eebf`
- `edgeIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x18006eebf`

## pseudocode

```c
__int64 __fastcall WebRuntimeDiagnostics::LCIEDiagnosticsTarget::LCIEProcessMessage(
        HWND a1,
        __int64 a2,
        int a3,
        unsigned int a4)
{
  HWND *v6; // rax
  const char *v7; // r9
  HWND *v8; // rdi
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  const char *v14; // r9
  const char *v15; // r9
  __int64 v17; // rbx
  _QWORD *v18; // rax
  __int64 v19; // rcx
  int v20; // r8d
  const char *v21; // r9
  const char *v22; // r9
  __int64 v23; // rbx
  _QWORD *v24; // rax
  __int64 v25; // rcx
  int v26; // r8d
  HWND v27; // rcx
  const char *v28; // r9
  _IsoComponent *v29; // [rsp+30h] [rbp-28h] BYREF
  struct _IsoMessage *v30; // [rsp+38h] [rbp-20h] BYREF
  _QWORD *v31; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  unsigned int v33; // [rsp+98h] [rbp+40h] BYREF

  v30 = 0;
  v33 = 0;
  if ( !IsoGetMessageBufferAddress(a4, 1, 0, &v30, &v33) )
  {
    v29 = 0;
    if ( !(unsigned int)IsoGetArtifactAddress(*(unsigned int *)v30, 1, &v29) )
    {
      v6 = (HWND *)IsoInProcessData(v29, 0x30001u, *((_DWORD *)v29 + 65), 0);
      v8 = v6;
      if ( !v6 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x47,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticstarget.cpp",
          v7);
      v9 = a3 - 3548;
      if ( v9 )
      {
        v10 = v9 - 2;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( v12 )
            {
              v13 = v12 - 1;
              if ( v13 )
              {
                if ( v13 == 7 && !PostMessageW(*v6, 0x405u, 0, 0) )
                  wil::details::in1diag3::_FailFast_GetLastError(
                    retaddr,
                    (void *)0x8D,
                    (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticstarget.cpp",
                    v14);
              }
              else if ( !PostMessageW(*v6, 0x404u, 0, 0) )
              {
                wil::details::in1diag3::_FailFast_GetLastError(
                  retaddr,
                  (void *)0x6B,
                  (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticstarget.cpp",
                  v15);
              }
            }
            else
            {
              IsoReleaseThread(*((_DWORD *)v29 + 10));
              _IsoComponent::SetAppObj(v29, 0);
              IsoRemoveArtifact(*(_DWORD *)v30);
            }
          }
          else
          {
            v17 = TFlatIsoMessage<LCIE_MSGID_F12_CREATE_DIAGNOSTICS_DATA_MSG>::VerifyExactSize(a4);
            if ( v17 )
            {
              v18 = operator new(0x18u);
              v19 = *(_QWORD *)v17;
              v20 = *(_DWORD *)(v17 + 16);
              v18[1] = *(_QWORD *)(v17 + 8);
              *((_DWORD *)v18 + 4) = v20;
              *v18 = v19;
              v31 = v18;
              if ( !PostMessageW(*v8, 0x403u, (WPARAM)v18, *((unsigned int *)v30 + 1)) )
                wil::details::in1diag3::_FailFast_GetLastError(
                  retaddr,
                  (void *)0x7A,
                  (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticstarget.cpp",
                  v21);
            }
          }
        }
        else if ( !PostMessageW(*v6, 0x402u, 0, 0) )
        {
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x61,
            (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticstarget.cpp",
            v22);
        }
      }
      else
      {
        v23 = TFlatIsoMessage<LCIE_MSGID_F12_CREATE_DIAGNOSTICS_DATA_MSG>::VerifyExactSize(a4);
        if ( v23 )
        {
          v24 = operator new(0x18u);
          v25 = *(_QWORD *)v23;
          v26 = *(_DWORD *)(v23 + 16);
          v24[1] = *(_QWORD *)(v23 + 8);
          *((_DWORD *)v24 + 4) = v26;
          *v24 = v25;
          v27 = *v8;
          v31 = v24;
          if ( !PostMessageW(v27, 0x401u, (WPARAM)v24, 0) )
            wil::details::in1diag3::_FailFast_GetLastError(
              retaddr,
              (void *)0x56,
              (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticstarget.cpp",
              v28);
        }
      }
    }
    IsoFreeMessageBuffer(a4);
  }
  return 0;
}

```

## disassembly

```asm
0x18006ee40  push    rbp
0x18006ee42  push    rbx
0x18006ee43  push    rsi
0x18006ee44  push    rdi
0x18006ee45  mov     rbp, rsp
0x18006ee48  sub     rsp, 58h
0x18006ee4c  mov     rsi, r9
0x18006ee4f  mov     [rbp+var_20], 0
0x18006ee57  mov     rbx, r8
0x18006ee5a  mov     [rbp+arg_18], 0
0x18006ee61  xor     r8d, r8d
0x18006ee64  lea     rax, [rbp+arg_18]
0x18006ee68  lea     r9, [rbp+var_20]
0x18006ee6c  mov     [rsp+58h+var_38], rax
0x18006ee71  mov     ecx, esi
0x18006ee73  lea     edi, [r8+1]
0x18006ee77  mov     edx, edi
0x18006ee79  call    cs:__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z; IsoGetMessageBufferAddress(ulong,int,ulong *,_IsoMessage * *,ulong *)
0x18006ee7f  test    eax, eax
0x18006ee81  jnz     loc_18006EF94
0x18006ee87  mov     rcx, [rbp+var_20]
0x18006ee8b  lea     r8, [rbp+var_28]
0x18006ee8f  mov     [rbp+var_28], 0
0x18006ee97  xor     r9d, r9d
0x18006ee9a  mov     edx, edi
0x18006ee9c  mov     ecx, [rcx]
0x18006ee9e  call    cs:__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,IsoArtifactType,_IsoArtifact * *,ulong *)
0x18006eea4  test    eax, eax
0x18006eea6  jnz     loc_18006EF8C
0x18006eeac  mov     rcx, [rbp+var_28]
0x18006eeb0  xor     r9d, r9d
0x18006eeb3  mov     edx, 30001h
0x18006eeb8  mov     r8d, [rcx+104h]
0x18006eebf  call    cs:__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z; IsoInProcessData(_IsoArtifact *,ulong,ulong,void *)
0x18006eec5  mov     rcx, [rbp+20h]; this
0x18006eec9  mov     rdi, rax
0x18006eecc  test    rax, rax
0x18006eecf  jnz     short loc_18006EEE1
0x18006eed1  lea     r8, aOnecoreuapInet_16; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18006eed8  lea     edx, [rax+47h]; void *
0x18006eedb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18006eee1  sub     ebx, 0DDCh
0x18006eee7  jz      loc_18006F033
0x18006eeed  sub     ebx, 2
0x18006eef0  jz      loc_18006F003
0x18006eef6  sub     ebx, 1
0x18006eef9  jz      loc_18006EF9F
0x18006eeff  sub     ebx, 1
0x18006ef02  jz      short loc_18006EF68
0x18006ef04  sub     ebx, 1
0x18006ef07  jz      short loc_18006EF3C
0x18006ef09  cmp     ebx, 7
0x18006ef0c  jnz     short loc_18006EF8C
0x18006ef0e  mov     rcx, [rax]; hWnd
0x18006ef11  xor     r9d, r9d; lParam
0x18006ef14  xor     r8d, r8d; wParam
0x18006ef17  mov     edx, 405h; Msg
0x18006ef1c  call    cs:__imp_PostMessageW
0x18006ef22  test    eax, eax
0x18006ef24  jnz     short loc_18006EF8C
0x18006ef26  mov     rcx, [rbp+20h]; this
0x18006ef2a  lea     r8, aOnecoreuapInet_16; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18006ef31  mov     edx, 8Dh; void *
0x18006ef36  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18006ef3c  mov     rcx, [rax]; hWnd
0x18006ef3f  xor     r9d, r9d; lParam
0x18006ef42  xor     r8d, r8d; wParam
0x18006ef45  mov     edx, 404h; Msg
0x18006ef4a  call    cs:__imp_PostMessageW
0x18006ef50  test    eax, eax
0x18006ef52  jnz     short loc_18006EF8C
0x18006ef54  mov     rcx, [rbp+20h]; this
0x18006ef58  lea     r8, aOnecoreuapInet_16; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18006ef5f  lea     edx, [rax+6Bh]; void *
0x18006ef62  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18006ef68  mov     rcx, [rbp+var_28]
0x18006ef6c  mov     ecx, [rcx+28h]
0x18006ef6f  call    cs:__imp_?IsoReleaseThread@@YAKK@Z; IsoReleaseThread(ulong)
0x18006ef75  mov     rcx, [rbp+var_28]; this
0x18006ef79  xor     edx, edx; void *
0x18006ef7b  call    ?SetAppObj@_IsoComponent@@QEAAXQEAX@Z; _IsoComponent::SetAppObj(void * const)
0x18006ef80  mov     rcx, [rbp+var_20]
0x18006ef84  mov     ecx, [rcx]
0x18006ef86  call    cs:__imp_?IsoRemoveArtifact@@YAJK@Z; IsoRemoveArtifact(ulong)
0x18006ef8c  mov     ecx, esi
0x18006ef8e  call    cs:__imp_?IsoFreeMessageBuffer@@YAJK@Z; IsoFreeMessageBuffer(ulong)
0x18006ef94  xor     eax, eax
0x18006ef96  add     rsp, 58h
0x18006ef9a  pop     rdi
0x18006ef9b  pop     rsi
0x18006ef9c  pop     rbx
0x18006ef9d  pop     rbp
0x18006ef9e  retn
0x18006ef9f  mov     ecx, esi
0x18006efa1  call    ?VerifyExactSize@?$TFlatIsoMessage@ULCIE_MSGID_F12_CREATE_DIAGNOSTICS_DATA_MSG@@@@SAPEAULCIE_MSGID_F12_CREATE_DIAGNOSTICS_DATA_MSG@@K@Z; TFlatIsoMessage<LCIE_MSGID_F12_CREATE_DIAGNOSTICS_DATA_MSG>::VerifyExactSize(ulong)
0x18006efa6  mov     rbx, rax
0x18006efa9  test    rax, rax
0x18006efac  jz      short loc_18006EF8C
0x18006efae  mov     ecx, 18h; Size
0x18006efb3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006efb8  mov     rdx, [rbx+8]
0x18006efbc  mov     rcx, [rbx]
0x18006efbf  mov     r8d, [rbx+10h]
0x18006efc3  mov     [rax+8], rdx
0x18006efc7  mov     edx, 403h; Msg
0x18006efcc  mov     [rax+10h], r8d
0x18006efd0  mov     r8, rax; wParam
0x18006efd3  mov     [rax], rcx
0x18006efd6  mov     rcx, [rbp+var_20]
0x18006efda  mov     [rbp+var_18], rax
0x18006efde  mov     r9d, [rcx+4]; lParam
0x18006efe2  mov     rcx, [rdi]; hWnd
0x18006efe5  call    cs:__imp_PostMessageW
0x18006efeb  test    eax, eax
0x18006efed  jnz     short loc_18006EF8C
0x18006efef  mov     rcx, [rbp+20h]; this
0x18006eff3  lea     r8, aOnecoreuapInet_16; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18006effa  lea     edx, [rax+7Ah]; void *
0x18006effd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18006f003  mov     rcx, [rax]; hWnd
0x18006f006  xor     r9d, r9d; lParam
0x18006f009  xor     r8d, r8d; wParam
0x18006f00c  mov     edx, 402h; Msg
0x18006f011  call    cs:__imp_PostMessageW
0x18006f017  test    eax, eax
0x18006f019  jnz     loc_18006EF8C
0x18006f01f  mov     rcx, [rbp+20h]; this
0x18006f023  lea     r8, aOnecoreuapInet_16; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18006f02a  lea     edx, [rax+61h]; void *
0x18006f02d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18006f033  mov     ecx, esi
0x18006f035  call    ?VerifyExactSize@?$TFlatIsoMessage@ULCIE_MSGID_F12_CREATE_DIAGNOSTICS_DATA_MSG@@@@SAPEAULCIE_MSGID_F12_CREATE_DIAGNOSTICS_DATA_MSG@@K@Z; TFlatIsoMessage<LCIE_MSGID_F12_CREATE_DIAGNOSTICS_DATA_MSG>::VerifyExactSize(ulong)
0x18006f03a  mov     rbx, rax
0x18006f03d  test    rax, rax
0x18006f040  jz      loc_18006EF8C
0x18006f046  mov     ecx, 18h; Size
0x18006f04b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006f050  mov     rdx, [rbx+8]
0x18006f054  xor     r9d, r9d; lParam
0x18006f057  mov     rcx, [rbx]
0x18006f05a  mov     r8d, [rbx+10h]
0x18006f05e  mov     [rax+8], rdx
0x18006f062  mov     edx, 401h; Msg
0x18006f067  mov     [rax+10h], r8d
0x18006f06b  mov     r8, rax; wParam
0x18006f06e  mov     [rax], rcx
0x18006f071  mov     rcx, [rdi]; hWnd
0x18006f074  mov     [rbp+var_18], rax
0x18006f078  call    cs:__imp_PostMessageW
0x18006f07e  test    eax, eax
0x18006f080  jnz     loc_18006EF8C
0x18006f086  mov     rcx, [rbp+20h]; this
0x18006f08a  lea     r8, aOnecoreuapInet_16; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18006f091  lea     edx, [rax+56h]; void *
0x18006f094  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
