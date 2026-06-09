# CreateSelfHistoryItem(CRAInvitationHistoryItem *)

- ea: `0x140027098`
- end: `0x140027299`
- name: `?CreateSelfHistoryItem@@YAJPEAVCRAInvitationHistoryItem@@@Z`
- size: `513`
- prototype: `__int64 __fastcall(struct CRAInvitationHistoryItem *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400273a4`
- `0x14002f0d0`

## callees

- `0x140027098`
- `0x140029978`
- `0x140034ce4`
- `0x140043d58`
- `0x140043dac`
- `0x1400441fc`
- `0x14004ad80`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140027172`
- `OLEAUT32!__imp_SysFreeString` at `0x1400271d1`
- `OLEAUT32!__imp_SysFreeString` at `0x14002722d`
- `OLEAUT32!__imp_SysFreeString` at `0x140027275`
- `OLEAUT32!__imp_SysFreeString` at `0x140027172`
- `OLEAUT32!__imp_SysFreeString` at `0x1400271d1`
- `OLEAUT32!__imp_SysFreeString` at `0x14002722d`
- `OLEAUT32!__imp_SysFreeString` at `0x140027275`

## string_xrefs

- `0x1400270e3`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x14002711e`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140027255`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x1400270c9`: `CreateSelfHistoryItem`
- `0x140027125`: `CreateSelfHistoryItem`
- `0x14002724e`: `CreateSelfHistoryItem`

## pseudocode

```c
__int64 __fastcall CreateSelfHistoryItem(struct CRAInvitationHistoryItem *this)
{
  unsigned int v2; // edi
  signed int UserInfoAsBSTR; // eax
  CEventLogger *v4; // rcx
  unsigned int v5; // r9d
  OLECHAR *v6; // rbx
  signed int v7; // eax
  CEventLogger *v8; // rcx
  signed int v9; // eax
  CEventLogger *v10; // rcx
  signed int v11; // eax
  CEventLogger *v12; // rcx
  BSTR bstrString; // [rsp+30h] [rbp-28h] BYREF
  __int128 v15; // [rsp+38h] [rbp-20h]

  bstrString = 0;
  v15 = 0;
  if ( !this )
  {
    v2 = -2147467261;
    CEventLogger::LogError(
      0,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x1506u,
      L"CreateSelfHistoryItem",
      0x80004003);
    return v2;
  }
  UserInfoAsBSTR = GetUserInfoAsBSTR(1, &bstrString);
  v2 = UserInfoAsBSTR;
  if ( UserInfoAsBSTR < 0 )
  {
    v5 = 5384;
LABEL_5:
    CEventLogger::LogError(
      v4,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      v5,
      L"CreateSelfHistoryItem",
      UserInfoAsBSTR);
    v6 = bstrString;
    goto LABEL_23;
  }
  v6 = bstrString;
  v7 = CRAInvitationHistoryItem::put_Name(this, bstrString);
  v2 = v7;
  if ( v7 >= 0 )
  {
    if ( v6 )
    {
      SysFreeString(v6);
      bstrString = 0;
    }
    UserInfoAsBSTR = GetUserInfoAsBSTR(2, &bstrString);
    v2 = UserInfoAsBSTR;
    if ( UserInfoAsBSTR < 0 )
    {
      v5 = 5388;
      goto LABEL_5;
    }
    v6 = bstrString;
    v9 = CRAInvitationHistoryItem::put_ComputerName(this, bstrString);
    v2 = v9;
    if ( v9 >= 0 )
    {
      if ( v6 )
      {
        SysFreeString(v6);
        bstrString = 0;
      }
      UserInfoAsBSTR = GetUserInfoAsBSTR(3, &bstrString);
      v2 = UserInfoAsBSTR;
      if ( UserInfoAsBSTR >= 0 )
      {
        v6 = bstrString;
        v11 = CRAInvitationHistoryItem::put_Avatar(this, bstrString);
        v2 = v11;
        if ( v11 >= 0 )
        {
          if ( v6 )
          {
            SysFreeString(v6);
            v6 = 0;
          }
          v2 = -2147467259;
          CEventLogger::LogError(
            v12,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
            0x1514u,
            L"CreateSelfHistoryItem",
            0x80004005);
        }
        else
        {
          CEventLogger::LogError(
            v12,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
            0x1511u,
            L"CreateSelfHistoryItem",
            v11);
        }
        goto LABEL_23;
      }
      v5 = 5392;
      goto LABEL_5;
    }
    CEventLogger::LogError(
      v10,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x150Du,
      L"CreateSelfHistoryItem",
      v9);
  }
  else
  {
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x1509u,
      L"CreateSelfHistoryItem",
      v7);
  }
LABEL_23:
  if ( v6 )
    SysFreeString(v6);
  return v2;
}

```

## disassembly

```asm
0x140027098  push    rbp
0x14002709a  push    rbx
0x14002709b  push    rsi
0x14002709c  push    rdi
0x14002709d  mov     rbp, rsp
0x1400270a0  sub     rsp, 58h
0x1400270a4  mov     rax, cs:__security_cookie
0x1400270ab  xor     rax, rsp
0x1400270ae  mov     [rbp+var_10], rax
0x1400270b2  mov     [rbp+bstrString], 0
0x1400270ba  xorps   xmm0, xmm0
0x1400270bd  mov     rsi, rcx
0x1400270c0  movups  [rbp+var_20], xmm0
0x1400270c4  test    rcx, rcx
0x1400270c7  jnz     short loc_140027100
0x1400270c9  lea     rax, aCreateselfhist; "CreateSelfHistoryItem"
0x1400270d0  mov     [rsp+58h+var_30], 80004003h; unsigned int
0x1400270d8  mov     r9d, 1506h; unsigned int
0x1400270de  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x1400270e3  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x1400270ea  mov     edi, 80004003h
0x1400270ef  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400270f6  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400270fb  jmp     loc_140027281
0x140027100  lea     rdx, [rbp+bstrString]
0x140027104  mov     ecx, 1
0x140027109  call    ?GetUserInfoAsBSTR@@YAJW4_USERINFOTYPE@@PEAPEAG@Z; GetUserInfoAsBSTR(_USERINFOTYPE,ushort * *)
0x14002710e  mov     edi, eax
0x140027110  test    eax, eax
0x140027112  jns     short loc_140027146
0x140027114  mov     r9d, 1508h; unsigned int
0x14002711a  mov     [rsp+58h+var_30], eax; unsigned int
0x14002711e  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140027125  lea     rax, aCreateselfhist; "CreateSelfHistoryItem"
0x14002712c  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140027133  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x140027138  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002713d  mov     rbx, [rbp+bstrString]
0x140027141  jmp     loc_14002726D
0x140027146  mov     rbx, [rbp+bstrString]
0x14002714a  mov     rcx, rsi; this
0x14002714d  mov     rdx, rbx; unsigned __int16 *
0x140027150  call    ?put_Name@CRAInvitationHistoryItem@@QEAAJPEAG@Z; CRAInvitationHistoryItem::put_Name(ushort *)
0x140027155  mov     edi, eax
0x140027157  test    eax, eax
0x140027159  jns     short loc_14002716A
0x14002715b  mov     [rsp+58h+var_30], eax
0x14002715f  mov     r9d, 1509h
0x140027165  jmp     loc_14002724E
0x14002716a  test    rbx, rbx
0x14002716d  jz      short loc_140027186
0x14002716f  mov     rcx, rbx; bstrString
0x140027172  call    cs:__imp_SysFreeString
0x140027179  nop     dword ptr [rax+rax+00h]
0x14002717e  mov     [rbp+bstrString], 0
0x140027186  lea     rdx, [rbp+bstrString]
0x14002718a  mov     ecx, 2
0x14002718f  call    ?GetUserInfoAsBSTR@@YAJW4_USERINFOTYPE@@PEAPEAG@Z; GetUserInfoAsBSTR(_USERINFOTYPE,ushort * *)
0x140027194  mov     edi, eax
0x140027196  test    eax, eax
0x140027198  jns     short loc_1400271A5
0x14002719a  mov     r9d, 150Ch
0x1400271a0  jmp     loc_14002711A
0x1400271a5  mov     rbx, [rbp+bstrString]
0x1400271a9  mov     rcx, rsi; this
0x1400271ac  mov     rdx, rbx; unsigned __int16 *
0x1400271af  call    ?put_ComputerName@CRAInvitationHistoryItem@@QEAAJPEAG@Z; CRAInvitationHistoryItem::put_ComputerName(ushort *)
0x1400271b4  mov     edi, eax
0x1400271b6  test    eax, eax
0x1400271b8  jns     short loc_1400271C9
0x1400271ba  mov     [rsp+58h+var_30], eax
0x1400271be  mov     r9d, 150Dh
0x1400271c4  jmp     loc_14002724E
0x1400271c9  test    rbx, rbx
0x1400271cc  jz      short loc_1400271E5
0x1400271ce  mov     rcx, rbx; bstrString
0x1400271d1  call    cs:__imp_SysFreeString
0x1400271d8  nop     dword ptr [rax+rax+00h]
0x1400271dd  mov     [rbp+bstrString], 0
0x1400271e5  lea     rdx, [rbp+bstrString]
0x1400271e9  mov     ecx, 3
0x1400271ee  call    ?GetUserInfoAsBSTR@@YAJW4_USERINFOTYPE@@PEAPEAG@Z; GetUserInfoAsBSTR(_USERINFOTYPE,ushort * *)
0x1400271f3  mov     edi, eax
0x1400271f5  test    eax, eax
0x1400271f7  jns     short loc_140027204
0x1400271f9  mov     r9d, 1510h
0x1400271ff  jmp     loc_14002711A
0x140027204  mov     rbx, [rbp+bstrString]
0x140027208  mov     rcx, rsi; this
0x14002720b  mov     rdx, rbx; unsigned __int16 *
0x14002720e  call    ?put_Avatar@CRAInvitationHistoryItem@@QEAAJPEAG@Z; CRAInvitationHistoryItem::put_Avatar(ushort *)
0x140027213  mov     edi, eax
0x140027215  test    eax, eax
0x140027217  jns     short loc_140027225
0x140027219  mov     [rsp+58h+var_30], eax
0x14002721d  mov     r9d, 1511h
0x140027223  jmp     short loc_14002724E
0x140027225  test    rbx, rbx
0x140027228  jz      short loc_14002723B
0x14002722a  mov     rcx, rbx; bstrString
0x14002722d  call    cs:__imp_SysFreeString
0x140027234  nop     dword ptr [rax+rax+00h]
0x140027239  xor     ebx, ebx
0x14002723b  mov     edi, 80004005h
0x140027240  mov     [rsp+58h+var_30], 80004005h; unsigned int
0x140027248  mov     r9d, 1514h; unsigned int
0x14002724e  lea     rax, aCreateselfhist; "CreateSelfHistoryItem"
0x140027255  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002725c  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x140027261  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140027268  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002726d  test    rbx, rbx
0x140027270  jz      short loc_140027281
0x140027272  mov     rcx, rbx; bstrString
0x140027275  call    cs:__imp_SysFreeString
0x14002727c  nop     dword ptr [rax+rax+00h]
0x140027281  mov     eax, edi
0x140027283  mov     rcx, [rbp+var_10]
0x140027287  xor     rcx, rsp; StackCookie
0x14002728a  call    __security_check_cookie
0x14002728f  add     rsp, 58h
0x140027293  pop     rdi
0x140027294  pop     rsi
0x140027295  pop     rbx
0x140027296  pop     rbp
0x140027297  retn
```
