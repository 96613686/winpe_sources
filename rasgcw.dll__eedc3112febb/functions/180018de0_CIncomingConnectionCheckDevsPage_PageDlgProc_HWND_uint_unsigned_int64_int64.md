# CIncomingConnectionCheckDevsPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180018de0`
- end: `0x180018ee4`
- name: `?PageDlgProc@CIncomingConnectionCheckDevsPage@@CAHPEAUHWND__@@I_K_J@Z`
- size: `260`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180018d90`
- `0x180018de0`
- `0x180018eec`

## import_xrefs

- `USER32!PostMessageW` at `0x180018eb3`
- `USER32!PostMessageW` at `0x180018ed1`
- `USER32!PostMessageW` at `0x180018eb3`
- `USER32!PostMessageW` at `0x180018ed1`
- `USER32!GetPropW` at `0x180018e2e`
- `USER32!GetPropW` at `0x180018e2e`
- `USER32!RemovePropW` at `0x180018e26`
- `USER32!RemovePropW` at `0x180018e26`
- `USER32!SetPropW` at `0x180018e12`
- `USER32!SetPropW` at `0x180018e12`
- `USER32!SendMessageW` at `0x180018e6b`
- `USER32!SendMessageW` at `0x180018e6b`
- `USER32!GetParent` at `0x180018e56`
- `USER32!GetParent` at `0x180018e9a`
- `USER32!GetParent` at `0x180018ebc`
- `USER32!GetParent` at `0x180018e56`
- `USER32!GetParent` at `0x180018e9a`
- `USER32!GetParent` at `0x180018ebc`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionCheckDevsPage::PageDlgProc(HWND hWnd, int a2, __int64 a3, __int64 a4)
{
  _DWORD *v4; // rbx
  CIncomingConnectionCheckDevsPage *v8; // rcx
  CIncomingConnectionCheckDevsPage *PropW; // r14
  __int64 v10; // rdi
  HWND Parent; // rax
  int v12; // ebx
  HWND v14; // rax
  HWND v15; // rax

  v4 = (_DWORD *)a4;
  if ( a2 == 272 )
  {
    if ( *(_DWORD *)a4 == 104 )
      v4 = *(_DWORD **)(a4 + 48);
    SetPropW(hWnd, L"_Win32_this_", v4);
    return 0;
  }
  if ( a2 == 2 )
  {
    RemovePropW(hWnd, L"_Win32_this_");
    return 0;
  }
  PropW = (CIncomingConnectionCheckDevsPage *)GetPropW(hWnd, L"_Win32_this_");
  if ( a2 != 78 )
  {
    if ( a2 == 273 )
    {
      v10 = a3 - 2011;
      if ( v10 )
      {
        if ( v10 != 1 )
          return 0;
      }
      else
      {
        v12 = CIncomingConnectionCheckDevsPage::CheckDevices(v8);
        CIncomingConnectionCheckDevsPage::UpdateDevicePresenceInPropertyBag(PropW, v12);
        if ( !v12 )
          return 0;
      }
      Parent = GetParent(hWnd);
      SendMessageW(Parent, 0x465u, 0xFFFFFFFFFFFFFFFFuLL, 0);
    }
    return 0;
  }
  if ( v4[4] != -200 )
    return 0;
  v14 = GetParent(hWnd);
  PostMessageW(v14, 0x470u, 0, 1);
  v15 = GetParent(hWnd);
  PostMessageW(v15, 0x48Au, 0, 6);
  return 1;
}

```

## disassembly

```asm
0x180018de0  push    rbx
0x180018de2  push    rbp
0x180018de3  push    rsi
0x180018de4  push    rdi
0x180018de5  push    r14
0x180018de7  sub     rsp, 20h
0x180018deb  mov     rbx, r9
0x180018dee  mov     rdi, r8
0x180018df1  mov     ebp, edx
0x180018df3  mov     rsi, rcx
0x180018df6  cmp     edx, 110h
0x180018dfc  jnz     short loc_180018E1A
0x180018dfe  cmp     dword ptr [r9], 68h ; 'h'
0x180018e02  jnz     short loc_180018E08
0x180018e04  mov     rbx, [r9+30h]
0x180018e08  mov     r8, rbx; hData
0x180018e0b  lea     rdx, aWin32This_2; "_Win32_this_"
0x180018e12  call    cs:__imp_SetPropW
0x180018e18  jmp     short loc_180018E93
0x180018e1a  lea     rdx, aWin32This_2; "_Win32_this_"
0x180018e21  cmp     ebp, 2
0x180018e24  jnz     short loc_180018E2E
0x180018e26  call    cs:__imp_RemovePropW
0x180018e2c  jmp     short loc_180018E93
0x180018e2e  call    cs:__imp_GetPropW
0x180018e34  mov     r14, rax
0x180018e37  cmp     ebp, 4Eh ; 'N'
0x180018e3a  jz      short loc_180018E8A
0x180018e3c  cmp     ebp, 111h
0x180018e42  jnz     short loc_180018E93
0x180018e44  sub     rdi, 7DBh
0x180018e4b  jz      short loc_180018E73
0x180018e4d  cmp     rdi, 1
0x180018e51  jnz     short loc_180018E93
0x180018e53  mov     rcx, rsi; hWnd
0x180018e56  call    cs:__imp_GetParent
0x180018e5c  xor     r9d, r9d; lParam
0x180018e5f  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x180018e63  mov     rcx, rax; hWnd
0x180018e66  mov     edx, 465h; Msg
0x180018e6b  call    cs:__imp_SendMessageW
0x180018e71  jmp     short loc_180018E93
0x180018e73  call    ?CheckDevices@CIncomingConnectionCheckDevsPage@@AEAAHXZ; CIncomingConnectionCheckDevsPage::CheckDevices(void)
0x180018e78  mov     edx, eax; int
0x180018e7a  mov     rcx, r14; this
0x180018e7d  mov     ebx, eax
0x180018e7f  call    ?UpdateDevicePresenceInPropertyBag@CIncomingConnectionCheckDevsPage@@AEAAXH@Z; CIncomingConnectionCheckDevsPage::UpdateDevicePresenceInPropertyBag(int)
0x180018e84  test    ebx, ebx
0x180018e86  jz      short loc_180018E93
0x180018e88  jmp     short loc_180018E53
0x180018e8a  cmp     dword ptr [rbx+10h], 0FFFFFF38h
0x180018e91  jz      short loc_180018E97
0x180018e93  xor     eax, eax
0x180018e95  jmp     short loc_180018ED9
0x180018e97  mov     rcx, rsi; hWnd
0x180018e9a  call    cs:__imp_GetParent
0x180018ea0  mov     ebx, 1
0x180018ea5  xor     r8d, r8d; wParam
0x180018ea8  mov     rcx, rax; hWnd
0x180018eab  mov     r9d, ebx; lParam
0x180018eae  mov     edx, 470h; Msg
0x180018eb3  call    cs:__imp_PostMessageW
0x180018eb9  mov     rcx, rsi; hWnd
0x180018ebc  call    cs:__imp_GetParent
0x180018ec2  lea     r9d, [rbx+5]; lParam
0x180018ec6  xor     r8d, r8d; wParam
0x180018ec9  mov     rcx, rax; hWnd
0x180018ecc  mov     edx, 48Ah; Msg
0x180018ed1  call    cs:__imp_PostMessageW
0x180018ed7  mov     eax, ebx
0x180018ed9  add     rsp, 20h
0x180018edd  pop     r14
0x180018edf  pop     rdi
0x180018ee0  pop     rsi
0x180018ee1  pop     rbp
0x180018ee2  pop     rbx
0x180018ee3  retn
```
