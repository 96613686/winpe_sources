# _PrepDefAppCombo(HWND__ * const,int,std::vector<DelegationConfig::DelegationPackage,std::allocator<DelegationConfig::DelegationPackage>> const &,DelegationConfig::DelegationPackage const &)

- ea: `0x18000e94c`
- end: `0x18000eacf`
- name: `?_PrepDefAppCombo@@YAXQEAUHWND__@@HAEBV?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@AEBUDelegationPackage@DelegationConfig@@@Z`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000dc18`

## callees

- `0x1800015b0`
- `0x180008d24`
- `0x18000db84`
- `0x18000e94c`
- `0x18000eb2c`
- `0x18000eb3c`
- `0x180018d00`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18000eaa0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18000eaa0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000e98f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000e9dd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000ea19`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000ea3d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000ea8c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000e98f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000e9dd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000ea19`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000ea3d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000ea8c`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000e972`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000e972`

## pseudocode

```c
BOOL __fastcall _PrepDefAppCombo(HWND a1)
{
  HWND DlgItem; // rdi
  int v2; // ebp
  int v3; // esi
  _QWORD *v4; // rbx
  __int64 v5; // r14
  _QWORD *v6; // r9
  __int64 v7; // rdx
  _QWORD *StringResource; // rax
  int v9; // eax
  int v10; // ecx
  _BYTE v12[32]; // [rsp+20h] [rbp-48h] BYREF

  DlgItem = GetDlgItem(a1, 641);
  SendMessageW(DlgItem, 0x14Bu, 0, 0);
  v2 = 0;
  v3 = 0;
  v4 = (_QWORD *)std::vector<DelegationConfig::DelegationPackage>::_Unchecked_begin();
  v5 = std::vector<DelegationConfig::DelegationPackage>::_Unchecked_end();
  if ( v4 != (_QWORD *)v5 )
  {
    while ( *(_DWORD *)v4 != 1 )
    {
      if ( *(_DWORD *)v4 == 2 )
      {
        v7 = 20;
LABEL_9:
        StringResource = (_QWORD *)GetStringResource(v12, v7);
        if ( StringResource[3] > 7u )
          StringResource = (_QWORD *)*StringResource;
        SendMessageW(DlgItem, 0x143u, 0, (LPARAM)StringResource);
        std::wstring::_Tidy_deallocate(v12);
        goto LABEL_12;
      }
      v6 = v4 + 5;
      if ( v4[8] > 7u )
        v6 = (_QWORD *)*v6;
      SendMessageW(DlgItem, 0x143u, 0, (LPARAM)v6);
LABEL_12:
      SendMessageW(DlgItem, 0x151u, v2, (LPARAM)v4);
      v9 = memcmp_0(&g_selectedPackage, v4, 0x24u);
      v10 = v2;
      if ( v9 )
        v10 = v3;
      ++v2;
      v4 += 22;
      v3 = v10;
      if ( v4 == (_QWORD *)v5 )
        goto LABEL_15;
    }
    v7 = 19;
    goto LABEL_9;
  }
LABEL_15:
  SendMessageW(DlgItem, 0x14Eu, v3, 0);
  return EnableWindow(DlgItem, 1);
}

```

## disassembly

```asm
0x18000e94c  mov     [rsp+arg_8], rbx
0x18000e951  mov     [rsp+arg_10], rbp
0x18000e956  push    rsi
0x18000e957  push    rdi
0x18000e958  push    r14
0x18000e95a  sub     rsp, 50h
0x18000e95e  mov     rax, cs:__security_cookie
0x18000e965  xor     rax, rsp
0x18000e968  mov     [rsp+68h+var_28], rax
0x18000e96d  mov     edx, 281h; nIDDlgItem
0x18000e972  call    cs:__imp_GetDlgItem
0x18000e979  nop     dword ptr [rax+rax+00h]
0x18000e97e  xor     r9d, r9d; lParam
0x18000e981  xor     r8d, r8d; wParam
0x18000e984  mov     rcx, rax; hWnd
0x18000e987  mov     edx, 14Bh; Msg
0x18000e98c  mov     rdi, rax
0x18000e98f  call    cs:__imp_SendMessageW
0x18000e996  nop     dword ptr [rax+rax+00h]
0x18000e99b  xor     ebp, ebp
0x18000e99d  xor     esi, esi
0x18000e99f  call    ?_Unchecked_begin@?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@QEBAPEBUDelegationPackage@DelegationConfig@@XZ; std::vector<DelegationConfig::DelegationPackage>::_Unchecked_begin(void)
0x18000e9a4  mov     rbx, rax
0x18000e9a7  call    ?_Unchecked_end@?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@QEBAPEBUDelegationPackage@DelegationConfig@@XZ; std::vector<DelegationConfig::DelegationPackage>::_Unchecked_end(void)
0x18000e9ac  mov     r14, rax
0x18000e9af  cmp     rbx, rax
0x18000e9b2  jz      loc_18000EA7E
0x18000e9b8  mov     edx, [rbx]
0x18000e9ba  sub     edx, 1
0x18000e9bd  jz      short loc_18000E9F2
0x18000e9bf  cmp     edx, 1
0x18000e9c2  jz      short loc_18000E9EB
0x18000e9c4  cmp     qword ptr [rbx+40h], 7
0x18000e9c9  lea     r9, [rbx+28h]
0x18000e9cd  jbe     short loc_18000E9D2
0x18000e9cf  mov     r9, [r9]; lParam
0x18000e9d2  xor     r8d, r8d; wParam
0x18000e9d5  mov     edx, 143h; Msg
0x18000e9da  mov     rcx, rdi; hWnd
0x18000e9dd  call    cs:__imp_SendMessageW
0x18000e9e4  nop     dword ptr [rax+rax+00h]
0x18000e9e9  jmp     short loc_18000EA2F
0x18000e9eb  mov     edx, 14h
0x18000e9f0  jmp     short loc_18000E9F7
0x18000e9f2  mov     edx, 13h
0x18000e9f7  lea     rcx, [rsp+68h+var_48]
0x18000e9fc  call    ?GetStringResource@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; GetStringResource(uint)
0x18000ea01  cmp     qword ptr [rax+18h], 7
0x18000ea06  jbe     short loc_18000EA0B
0x18000ea08  mov     rax, [rax]
0x18000ea0b  mov     r9, rax; lParam
0x18000ea0e  xor     r8d, r8d; wParam
0x18000ea11  mov     edx, 143h; Msg
0x18000ea16  mov     rcx, rdi; hWnd
0x18000ea19  call    cs:__imp_SendMessageW
0x18000ea20  nop     dword ptr [rax+rax+00h]
0x18000ea25  lea     rcx, [rsp+68h+var_48]
0x18000ea2a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ea2f  movsxd  r8, ebp; wParam
0x18000ea32  mov     r9, rbx; lParam
0x18000ea35  mov     edx, 151h; Msg
0x18000ea3a  mov     rcx, rdi; hWnd
0x18000ea3d  call    cs:__imp_SendMessageW
0x18000ea44  nop     dword ptr [rax+rax+00h]
0x18000ea49  mov     r8d, 24h ; '$'; Size
0x18000ea4f  lea     rcx, ?g_selectedPackage@@3UDelegationPackage@DelegationConfig@@A; Buf1
0x18000ea56  mov     rdx, rbx; Buf2
0x18000ea59  call    memcmp_0
0x18000ea5e  test    eax, eax
0x18000ea60  mov     ecx, ebp
0x18000ea62  setz    al
0x18000ea65  test    al, al
0x18000ea67  cmovz   ecx, esi
0x18000ea6a  inc     ebp
0x18000ea6c  add     rbx, 0B0h
0x18000ea73  mov     esi, ecx
0x18000ea75  cmp     rbx, r14
0x18000ea78  jnz     loc_18000E9B8
0x18000ea7e  movsxd  r8, esi; wParam
0x18000ea81  xor     r9d, r9d; lParam
0x18000ea84  mov     edx, 14Eh; Msg
0x18000ea89  mov     rcx, rdi; hWnd
0x18000ea8c  call    cs:__imp_SendMessageW
0x18000ea93  nop     dword ptr [rax+rax+00h]
0x18000ea98  mov     edx, 1; bEnable
0x18000ea9d  mov     rcx, rdi; hWnd
0x18000eaa0  call    cs:__imp_EnableWindow
0x18000eaa7  nop     dword ptr [rax+rax+00h]
0x18000eaac  mov     rcx, [rsp+68h+var_28]
0x18000eab1  xor     rcx, rsp; StackCookie
0x18000eab4  call    __security_check_cookie
0x18000eab9  lea     r11, [rsp+68h+var_18]
0x18000eabe  mov     rbx, [r11+28h]
0x18000eac2  mov     rbp, [r11+30h]
0x18000eac6  mov     rsp, r11
0x18000eac9  pop     r14
0x18000eacb  pop     rdi
0x18000eacc  pop     rsi
0x18000eacd  retn
```
