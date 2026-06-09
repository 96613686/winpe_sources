# WaitForEditionUpgradeWNF(void)

- ea: `0x180020570`
- end: `0x180020768`
- name: `?WaitForEditionUpgradeWNF@@YAJXZ`
- size: `504`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001240c`

## callees

- `0x1800083c4`
- `0x1800085a8`
- `0x1800098dc`
- `0x18000ad18`
- `0x18000f38c`
- `0x180020570`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800205a4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800205a4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180020644`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180020644`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800205e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800205e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800205d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002067a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800206bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800206ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800205d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002067a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800206bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800206ef`

## string_xrefs

- `0x180020738`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 WaitForEditionUpgradeWNF(void)
{
  wil::details *v0; // rcx
  HANDLE Event; // rdi
  __int64 v2; // rcx
  __int64 v3; // r8
  void (__fastcall ***v4)(_QWORD, __int64); // rbx
  DWORD v5; // eax
  const char *v6; // r9
  __int64 v7; // r8
  const char *v8; // r9
  int LastErrorFailHr; // eax
  unsigned int v11; // ebx
  __int64 v12; // r8
  const char *v13; // r9
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE hObject; // [rsp+20h] [rbp-59h] BYREF
  void (__fastcall ***v17)(_QWORD, __int64); // [rsp+28h] [rbp-51h] BYREF
  char v18[8]; // [rsp+30h] [rbp-49h] BYREF
  _QWORD v19[13]; // [rsp+38h] [rbp-41h] BYREF
  _QWORD *v20; // [rsp+A0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  hObject = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    hObject = Event;
LABEL_3:
    v17 = 0;
    v19[0] = off_180048510;
    v19[1] = &hObject;
    v20 = v19;
    v4 = 0;
    if ( (int)wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(v2, v18, v3, &v17) >= 0 )
      v4 = v17;
    if ( v20 )
      (*(void (**)(void))(*v20 + 24LL))();
    v5 = WaitForSingleObjectEx(hObject, 0xEA60u, 0);
    if ( v5 == 258 )
    {
      if ( v4 )
        (**v4)(v4, 1);
      if ( hObject && !CloseHandle(hObject) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
      return 2147942658LL;
    }
    else
    {
      if ( v5 )
        wil::details::in1diag3::FailFast_Unexpected(
          retaddr,
          (void *)0xB0F,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v6);
      if ( v4 )
        (**v4)(v4, 1);
      if ( hObject )
      {
        if ( !CloseHandle(hObject) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v7, v8);
      }
      return 0;
    }
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v0);
  v11 = LastErrorFailHr;
  if ( LastErrorFailHr >= 0 )
    goto LABEL_3;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8B,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
    (const char *)(unsigned int)LastErrorFailHr,
    (int)hObject);
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v12, v13);
  return v11;
}

```

## disassembly

```asm
0x180020570  push    rbp
0x180020572  push    rbx
0x180020573  push    rsi
0x180020574  push    rdi
0x180020575  lea     rbp, [rsp-3Fh]
0x18002057a  sub     rsp, 0B8h
0x180020581  mov     rax, cs:__security_cookie
0x180020588  xor     rax, rsp
0x18002058b  mov     [rbp+57h+var_28], rax
0x18002058f  mov     r9d, 1F0003h; dwDesiredAccess
0x180020595  mov     [rbp+57h+hObject], 0
0x18002059d  xor     r8d, r8d; dwFlags
0x1800205a0  xor     edx, edx; lpName
0x1800205a2  xor     ecx, ecx; lpEventAttributes
0x1800205a4  call    cs:__imp_CreateEventExW
0x1800205aa  mov     rdi, rax
0x1800205ad  test    rax, rax
0x1800205b0  jz      loc_18002068C
0x1800205b6  call    cs:__imp_GetLastError
0x1800205bc  mov     rbx, [rbp+57h+hObject]
0x1800205c0  test    rbx, rbx
0x1800205c3  jz      short loc_1800205E6
0x1800205c5  call    cs:__imp_GetLastError
0x1800205cb  mov     rcx, rbx; hObject
0x1800205ce  mov     esi, eax
0x1800205d0  call    cs:__imp_CloseHandle
0x1800205d6  test    eax, eax
0x1800205d8  jz      loc_180020725
0x1800205de  mov     ecx, esi; dwErrCode
0x1800205e0  call    cs:__imp_SetLastError
0x1800205e6  mov     [rbp+57h+hObject], rdi
0x1800205ea  lea     rax, off_180048510
0x1800205f1  mov     [rbp+57h+var_A8], 0
0x1800205f9  mov     [rbp+57h+var_98], rax
0x1800205fd  lea     r9, [rbp+57h+var_A8]
0x180020601  lea     rax, [rbp+57h+hObject]
0x180020605  mov     [rbp+57h+var_90], rax
0x180020609  lea     rdx, [rbp+57h+var_A0]
0x18002060d  lea     rax, [rbp+57h+var_98]
0x180020611  mov     [rbp+57h+var_30], rax
0x180020615  call    ??$make_wnf_subscription_state@Uempty_wnf_state@details@wil@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@KPEAPEAU?$wnf_subscription_state@Uempty_wnf_state@details@wil@@@01@@Z; wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong,wil::details::wnf_subscription_state<wil::details::empty_wnf_state> * *)
0x18002061a  mov     rcx, [rbp+57h+var_30]
0x18002061e  xor     ebx, ebx
0x180020620  test    eax, eax
0x180020622  cmovns  rbx, [rbp+57h+var_A8]
0x180020627  test    rcx, rcx
0x18002062a  jz      short loc_180020638
0x18002062c  mov     rax, [rcx]
0x18002062f  mov     rax, [rax+18h]
0x180020633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020638  mov     rcx, [rbp+57h+hObject]; hHandle
0x18002063c  xor     r8d, r8d; bAlertable
0x18002063f  mov     edx, 0EA60h; dwMilliseconds
0x180020644  call    cs:__imp_WaitForSingleObjectEx
0x18002064a  cmp     eax, 102h
0x18002064f  jz      short loc_1800206CE
0x180020651  test    eax, eax
0x180020653  jnz     loc_180020734
0x180020659  test    rbx, rbx
0x18002065c  jz      short loc_180020671
0x18002065e  mov     rax, [rbx]
0x180020661  mov     edx, 1
0x180020666  mov     rcx, rbx
0x180020669  mov     rax, [rax]
0x18002066c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020671  mov     rcx, [rbp+57h+hObject]; hObject
0x180020675  test    rcx, rcx
0x180020678  jz      short loc_180020688
0x18002067a  call    cs:__imp_CloseHandle
0x180020680  test    eax, eax
0x180020682  jz      loc_180020759
0x180020688  xor     eax, eax
0x18002068a  jmp     short loc_1800206FE
0x18002068c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180020691  mov     ebx, eax
0x180020693  test    eax, eax
0x180020695  jns     loc_1800205EA
0x18002069b  mov     rcx, [rbp+5Fh]; this
0x18002069f  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800206a6  mov     r9d, eax; char *
0x1800206a9  mov     edx, 8Bh; void *
0x1800206ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800206b3  mov     rcx, [rbp+57h+hObject]; hObject
0x1800206b7  test    rcx, rcx
0x1800206ba  jz      short loc_1800206CA
0x1800206bc  call    cs:__imp_CloseHandle
0x1800206c2  test    eax, eax
0x1800206c4  jz      loc_18002074A
0x1800206ca  mov     eax, ebx
0x1800206cc  jmp     short loc_1800206FE
0x1800206ce  test    rbx, rbx
0x1800206d1  jz      short loc_1800206E6
0x1800206d3  mov     rax, [rbx]
0x1800206d6  mov     edx, 1
0x1800206db  mov     rcx, rbx
0x1800206de  mov     rax, [rax]
0x1800206e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206e6  mov     rcx, [rbp+57h+hObject]; hObject
0x1800206ea  test    rcx, rcx
0x1800206ed  jz      short loc_1800206F9
0x1800206ef  call    cs:__imp_CloseHandle
0x1800206f5  test    eax, eax
0x1800206f7  jz      short loc_180020716
0x1800206f9  mov     eax, 80070102h
0x1800206fe  mov     rcx, [rbp+57h+var_28]
0x180020702  xor     rcx, rsp; StackCookie
0x180020705  call    __security_check_cookie
0x18002070a  add     rsp, 0B8h
0x180020711  pop     rdi
0x180020712  pop     rsi
0x180020713  pop     rbx
0x180020714  pop     rbp
0x180020715  retn
0x180020716  mov     rcx, [rbp+5Fh]; this
0x18002071a  mov     edx, 0A0Bh; void *
0x18002071f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180020725  mov     rcx, [rbp+5Fh]; this
0x180020729  mov     edx, 0A0Bh; void *
0x18002072e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180020734  mov     rcx, [rbp+5Fh]; this
0x180020738  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002073f  mov     edx, 0B0Fh; void *
0x180020744  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18002074a  mov     rcx, [rbp+5Fh]; this
0x18002074e  mov     edx, 0A0Bh; void *
0x180020753  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180020759  mov     rcx, [rbp+5Fh]; this
0x18002075d  mov     edx, 0A0Bh; void *
0x180020762  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
