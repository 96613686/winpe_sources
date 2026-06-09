# CIntlAdvancedDlg::_CopySettings_SetListViewData(void)

- ea: `0x180009b5c`
- end: `0x180009c98`
- name: `?_CopySettings_SetListViewData@CIntlAdvancedDlg@@AEAAXXZ`
- size: `316`
- prototype: `void __fastcall(CIntlAdvancedDlg *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180009a14`

## callees

- `0x180008184`
- `0x18000827c`
- `0x180008908`
- `0x180009aac`
- `0x18002a112`
- `0x18002a150`

## pseudocode

```c
void __fastcall CIntlAdvancedDlg::_CopySettings_SetListViewData(CIntlAdvancedDlg *this)
{
  int v2; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v3; // [rsp+24h] [rbp-DCh]
  __int16 v4; // [rsp+124h] [rbp+24h]
  __int16 v5; // [rsp+1CEh] [rbp+CEh]
  __int64 v6; // [rsp+278h] [rbp+178h]
  char v7; // [rsp+280h] [rbp+180h]
  __int64 v8; // [rsp+288h] [rbp+188h]
  int v9; // [rsp+290h] [rbp+190h]
  _BYTE v10[640]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v6 = 0;
  v7 = 0;
  v8 = 0;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  CAccountData::ReadUserData((__int64)&v2, 0);
  *(_DWORD *)this = HIDWORD(v6);
  CAccountData::ToDisplayNames((CAccountData *)&v2, (struct ACCOUNTDISPLAYNAMES *)v10);
  CAccountListView::SetData(*((_QWORD *)this + 2), 0, v10);
  CAccountData::ReadUserData((__int64)&v2, 1);
  *(_DWORD *)this |= HIDWORD(v6);
  CAccountData::ToDisplayNames((CAccountData *)&v2, (struct ACCOUNTDISPLAYNAMES *)v10);
  CAccountListView::SetData(*((_QWORD *)this + 2), 1, v10);
  CIntlAdvancedDlg::_CopySettings_ReadNewUsersData(this, (struct CAccountData *)&v2);
  *(_DWORD *)this |= HIDWORD(v6);
  CAccountData::ToDisplayNames((CAccountData *)&v2, (struct ACCOUNTDISPLAYNAMES *)v10);
  CAccountListView::SetData(*((_QWORD *)this + 2), 2, v10);
}

```

## disassembly

```asm
0x180009b5c  mov     [rsp-8+arg_8], rbx
0x180009b61  push    rbp
0x180009b62  lea     rbp, [rsp-430h]
0x180009b6a  sub     rsp, 530h
0x180009b71  mov     rax, cs:__security_cookie
0x180009b78  xor     rax, rsp
0x180009b7b  mov     [rbp+430h+var_10], rax
0x180009b82  mov     rbx, rcx
0x180009b85  xor     edx, edx; Val
0x180009b87  xor     ecx, ecx
0x180009b89  mov     r8d, 280h; Size
0x180009b8f  mov     [rbp+430h+var_2B8], rcx
0x180009b96  mov     [rbp+430h+var_2B0], cl
0x180009b9c  mov     [rbp+430h+var_2A8], rcx
0x180009ba3  mov     [rsp+530h+var_510], ecx
0x180009ba7  mov     [rsp+530h+var_50C], cx
0x180009bac  mov     [rbp+430h+var_40C], cx
0x180009bb0  mov     [rbp+430h+var_362], cx
0x180009bb7  mov     [rbp+430h+var_2A0], ecx
0x180009bbd  lea     rcx, [rbp+430h+var_290]; void *
0x180009bc4  call    memset_0
0x180009bc9  xor     edx, edx
0x180009bcb  lea     rcx, [rsp+530h+var_510]
0x180009bd0  call    ?ReadUserData@CAccountData@@QEAAXW4ACCOUNTTYPE@@@Z; CAccountData::ReadUserData(ACCOUNTTYPE)
0x180009bd5  mov     eax, dword ptr [rbp+430h+var_2B8+4]
0x180009bdb  lea     rdx, [rbp+430h+var_290]; struct ACCOUNTDISPLAYNAMES *
0x180009be2  lea     rcx, [rsp+530h+var_510]; this
0x180009be7  mov     [rbx], eax
0x180009be9  call    ?ToDisplayNames@CAccountData@@QEAAXPEAUACCOUNTDISPLAYNAMES@@@Z; CAccountData::ToDisplayNames(ACCOUNTDISPLAYNAMES *)
0x180009bee  mov     rcx, [rbx+10h]
0x180009bf2  lea     r8, [rbp+430h+var_290]
0x180009bf9  xor     edx, edx
0x180009bfb  call    ?SetData@CAccountListView@@QEAAXW4ACCOUNTTYPE@@PEAUACCOUNTDISPLAYNAMES@@@Z; CAccountListView::SetData(ACCOUNTTYPE,ACCOUNTDISPLAYNAMES *)
0x180009c00  mov     edx, 1
0x180009c05  lea     rcx, [rsp+530h+var_510]
0x180009c0a  call    ?ReadUserData@CAccountData@@QEAAXW4ACCOUNTTYPE@@@Z; CAccountData::ReadUserData(ACCOUNTTYPE)
0x180009c0f  mov     eax, dword ptr [rbp+430h+var_2B8+4]
0x180009c15  lea     rdx, [rbp+430h+var_290]; struct ACCOUNTDISPLAYNAMES *
0x180009c1c  or      [rbx], eax
0x180009c1e  lea     rcx, [rsp+530h+var_510]; this
0x180009c23  call    ?ToDisplayNames@CAccountData@@QEAAXPEAUACCOUNTDISPLAYNAMES@@@Z; CAccountData::ToDisplayNames(ACCOUNTDISPLAYNAMES *)
0x180009c28  mov     rcx, [rbx+10h]
0x180009c2c  lea     r8, [rbp+430h+var_290]
0x180009c33  mov     edx, 1
0x180009c38  call    ?SetData@CAccountListView@@QEAAXW4ACCOUNTTYPE@@PEAUACCOUNTDISPLAYNAMES@@@Z; CAccountListView::SetData(ACCOUNTTYPE,ACCOUNTDISPLAYNAMES *)
0x180009c3d  lea     rdx, [rsp+530h+var_510]; struct CAccountData *
0x180009c42  mov     rcx, rbx; this
0x180009c45  call    ?_CopySettings_ReadNewUsersData@CIntlAdvancedDlg@@AEAAXPEAVCAccountData@@@Z; CIntlAdvancedDlg::_CopySettings_ReadNewUsersData(CAccountData *)
0x180009c4a  mov     eax, dword ptr [rbp+430h+var_2B8+4]
0x180009c50  lea     rdx, [rbp+430h+var_290]; struct ACCOUNTDISPLAYNAMES *
0x180009c57  or      [rbx], eax
0x180009c59  lea     rcx, [rsp+530h+var_510]; this
0x180009c5e  call    ?ToDisplayNames@CAccountData@@QEAAXPEAUACCOUNTDISPLAYNAMES@@@Z; CAccountData::ToDisplayNames(ACCOUNTDISPLAYNAMES *)
0x180009c63  mov     rcx, [rbx+10h]
0x180009c67  lea     r8, [rbp+430h+var_290]
0x180009c6e  mov     edx, 2
0x180009c73  call    ?SetData@CAccountListView@@QEAAXW4ACCOUNTTYPE@@PEAUACCOUNTDISPLAYNAMES@@@Z; CAccountListView::SetData(ACCOUNTTYPE,ACCOUNTDISPLAYNAMES *)
0x180009c78  mov     rcx, [rbp+430h+var_10]
0x180009c7f  xor     rcx, rsp; StackCookie
0x180009c82  call    __security_check_cookie
0x180009c87  mov     rbx, [rsp+530h+arg_8]
0x180009c8f  add     rsp, 530h
0x180009c96  pop     rbp
0x180009c97  retn
```
