# CIsoBurnUI::ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 &,ulong)

- ea: `0x14000b3c0`
- end: `0x14000b6de`
- name: `?ProcessWindowMessage@CIsoBurnUI@@UEAAHPEAUHWND__@@I_K_JAEA_JK@Z`
- size: `798`
- prototype: `int(CIsoBurnUI *__hidden this, HWND, unsigned int, unsigned __int64, __int64, __int64 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000ad38`
- `0x14000af38`
- `0x14000b3c0`
- `0x14000baa0`
- `0x14000c15c`
- `0x140010010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x14000b46c`
- `KERNEL32!GetTickCount64` at `0x14000b46c`
- `USER32!SendDlgItemMessageW` at `0x14000b667`
- `USER32!SendDlgItemMessageW` at `0x14000b667`
- `USER32!SendMessageW` at `0x14000b447`
- `USER32!SendMessageW` at `0x14000b4c8`
- `USER32!SendMessageW` at `0x14000b447`
- `USER32!SendMessageW` at `0x14000b4c8`
- `USER32!EndDialog` at `0x14000b532`
- `USER32!EndDialog` at `0x14000b532`
- `USER32!KillTimer` at `0x14000b4d7`
- `USER32!KillTimer` at `0x14000b4d7`
- `USER32!EnableWindow` at `0x14000b590`
- `USER32!EnableWindow` at `0x14000b590`
- `USER32!GetDlgItem` at `0x14000b42e`
- `USER32!GetDlgItem` at `0x14000b4b4`
- `USER32!GetDlgItem` at `0x14000b585`
- `USER32!GetDlgItem` at `0x14000b42e`
- `USER32!GetDlgItem` at `0x14000b4b4`
- `USER32!GetDlgItem` at `0x14000b585`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x14000b560`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x14000b560`
- `OLEAUT32!__imp_SysAllocString` at `0x14000b5f6`
- `OLEAUT32!__imp_SysAllocString` at `0x14000b5f6`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b61b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b61b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000b5e1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000b5e1`
- `COMCTL32!__imp_DPA_GetPtr` at `0x14000b695`
- `COMCTL32!__imp_DPA_GetPtr` at `0x14000b695`

## pseudocode

```c
__int64 __fastcall CIsoBurnUI::ProcessWindowMessage(
        HWND *this,
        HWND a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        WPARAM wParam,
        CIsoBurnUI *a6,
        unsigned int a7)
{
  __int64 inited; // rax
  HWND DlgItem; // rax
  int TickCount64; // eax
  unsigned int v13; // esi
  unsigned int v14; // esi
  HWND v15; // rax
  WPARAM v16; // r8
  UINT v17; // edx
  HWND v18; // rcx
  int v19; // eax
  int v20; // eax
  HWND v21; // rax
  OLECHAR *v22; // rbx
  int v23; // eax
  LRESULT v24; // rax
  struct _DPA *v25; // rcx
  _BOOL8 v26; // rbx
  const WCHAR *Ptr; // rax
  int *fuStyle; // [rsp+20h] [rbp-48h]
  LPVOID ppv; // [rsp+30h] [rbp-38h] BYREF

  if ( !a7 )
  {
    switch ( (_DWORD)a3 )
    {
      case 0x110:
        inited = CIsoBurnUI::OnInitDialog((CIsoBurnUI *)this, (unsigned int)a2, a3, a4, fuStyle);
LABEL_4:
        *(_QWORD *)a6 = inited;
        return 1;
      case 0x8001:
        inited = CIsoBurnUI::OnStatus((CIsoBurnUI *)this, (unsigned int)a2, a4, wParam, fuStyle);
        goto LABEL_4;
      case 0x8002:
        DlgItem = GetDlgItem(this[1], 202);
        SendMessageW(DlgItem, 0x402u, wParam, 0);
        *(_QWORD *)a6 = 0;
        return 1;
      case 0x113:
        TickCount64 = GetTickCount64();
        if ( ((*((_DWORD *)this + 42) - 7) & 0xFFFFFFFB) != 0 )
        {
          KillTimer(this[1], 1u);
          goto LABEL_21;
        }
        v13 = 100 * (TickCount64 - *((_DWORD *)this + 44));
        if ( v13 >= 0x827670 )
          v14 = 95;
        else
          v14 = v13 / 0x15F90;
        v15 = GetDlgItem(this[1], 202);
        v16 = v14;
        v17 = 1026;
        v18 = v15;
LABEL_16:
        SendMessageW(v18, v17, v16, 0);
LABEL_21:
        *(_QWORD *)a6 = 0;
        return 1;
      case 0x111:
        if ( (_WORD)a4 == 205 )
        {
          CIsoBurnUI::_StartBurn((CIsoBurnUI *)this, 0);
          goto LABEL_21;
        }
        if ( (_WORD)a4 == 2 )
        {
          v19 = *((_DWORD *)this + 46);
          if ( !v19 )
          {
            EndDialog(this[1], 0);
            goto LABEL_21;
          }
          if ( v19 != 1 )
            goto LABEL_21;
          *((_DWORD *)this + 46) = 2;
          v20 = ShellMessageBoxW(hInstance, 0, (LPCWSTR)0x107, (LPCWSTR)0x108, 0x134u);
          if ( *((_DWORD *)this + 46) != 2 )
            goto LABEL_21;
          if ( v20 != 6 )
          {
            *((_DWORD *)this + 46) = 1;
            goto LABEL_21;
          }
          *((_DWORD *)this + 46) = 3;
          v21 = GetDlgItem(this[1], 2);
          EnableWindow(v21, 0);
          v18 = this[1];
          v17 = 32769;
          v16 = 11;
          goto LABEL_16;
        }
        break;
      case 0x53:
        ppv = 0;
        if ( CoCreateInstance(
               &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
               0,
               1u,
               &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
               &ppv) >= 0 )
        {
          v22 = SysAllocString(L"mshelp://windows/?id=13aca111-6547-4dfd-b9ef-75ec2a1ce163");
          if ( v22 )
          {
            (*(void (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)ppv + 24LL))(ppv, v22);
            SysFreeString(v22);
          }
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        goto LABEL_21;
    }
    v23 = *((_DWORD *)this + 47);
    if ( v23 && (_DWORD)a3 == v23 )
    {
      v24 = SendDlgItemMessageW(this[1], 201, 0x147u, 0, 0);
      v25 = (struct _DPA *)this[19];
      v26 = 0;
      if ( v25 )
      {
        if ( v24 >= 0 && v24 < *(int *)v25 )
        {
          LOWORD(a7) = 0;
          Ptr = (const WCHAR *)DPA_GetPtr(v25, v24);
          if ( (int)CIsoBurnUI::_GetDriveLetterForVolumeName(Ptr, (unsigned __int16 *)&a7) >= 0 )
            v26 = (unsigned __int16)a7 == a4 + 65;
        }
      }
      *(_QWORD *)a6 = v26;
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000b3c0  push    rbx
0x14000b3c2  push    rsi
0x14000b3c3  push    rdi
0x14000b3c4  push    r14
0x14000b3c6  sub     rsp, 48h
0x14000b3ca  cmp     dword ptr [rsp+68h+arg_30], 0
0x14000b3d2  mov     rsi, r9
0x14000b3d5  mov     rbx, rcx
0x14000b3d8  jnz     loc_14000B6D2
0x14000b3de  cmp     r8d, 110h
0x14000b3e5  jnz     short loc_14000B401
0x14000b3e7  call    ?OnInitDialog@CIsoBurnUI@@IEAA_JI_K_JAEAH@Z; CIsoBurnUI::OnInitDialog(uint,unsigned __int64,__int64,int &)
0x14000b3ec  mov     rcx, [rsp+68h+arg_28]; this
0x14000b3f4  mov     [rcx], rax
0x14000b3f7  mov     eax, 1
0x14000b3fc  jmp     loc_14000B6D4
0x14000b401  cmp     r8d, 8001h
0x14000b408  jnz     short loc_14000B41C
0x14000b40a  mov     r9, [rsp+68h+wParam]; __int64
0x14000b412  mov     r8, rsi; unsigned __int64
0x14000b415  call    ?OnStatus@CIsoBurnUI@@IEAA_JI_K_JAEAH@Z; CIsoBurnUI::OnStatus(uint,unsigned __int64,__int64,int &)
0x14000b41a  jmp     short loc_14000B3EC
0x14000b41c  cmp     r8d, 8002h
0x14000b423  jnz     short loc_14000B45E
0x14000b425  mov     rcx, [rcx+8]; hDlg
0x14000b429  mov     edx, 0CAh; nIDDlgItem
0x14000b42e  call    cs:__imp_GetDlgItem
0x14000b434  mov     r8, [rsp+68h+wParam]; wParam
0x14000b43c  xor     r9d, r9d; lParam
0x14000b43f  mov     rcx, rax; hWnd
0x14000b442  mov     edx, 402h; Msg
0x14000b447  call    cs:__imp_SendMessageW
0x14000b44d  mov     rax, [rsp+68h+arg_28]
0x14000b455  mov     qword ptr [rax], 0
0x14000b45c  jmp     short loc_14000B3F7
0x14000b45e  mov     edi, 1
0x14000b463  cmp     r8d, 113h
0x14000b46a  jnz     short loc_14000B4DF
0x14000b46c  call    cs:__imp_GetTickCount64
0x14000b472  mov     ecx, [rbx+0A8h]
0x14000b478  sub     ecx, 7
0x14000b47b  test    ecx, 0FFFFFFFBh
0x14000b481  jnz     short loc_14000B4D0
0x14000b483  sub     eax, [rbx+0B0h]
0x14000b489  imul    esi, eax, 64h ; 'd'
0x14000b48c  cmp     esi, 827670h
0x14000b492  jnb     short loc_14000B4A6
0x14000b494  mov     eax, 74D3B7BBh
0x14000b499  mul     esi
0x14000b49b  sub     esi, edx
0x14000b49d  shr     esi, 1
0x14000b49f  add     esi, edx
0x14000b4a1  shr     esi, 10h
0x14000b4a4  jmp     short loc_14000B4AB
0x14000b4a6  mov     esi, 5Fh ; '_'
0x14000b4ab  mov     rcx, [rbx+8]; hDlg
0x14000b4af  mov     edx, 0CAh; nIDDlgItem
0x14000b4b4  call    cs:__imp_GetDlgItem
0x14000b4ba  mov     r8d, esi; wParam
0x14000b4bd  mov     edx, 402h; Msg
0x14000b4c2  mov     rcx, rax; hWnd
0x14000b4c5  xor     r9d, r9d; lParam
0x14000b4c8  call    cs:__imp_SendMessageW
0x14000b4ce  jmp     short loc_14000B4FC
0x14000b4d0  mov     rcx, [rbx+8]; hWnd
0x14000b4d4  mov     rdx, rdi; uIDEvent
0x14000b4d7  call    cs:__imp_KillTimer
0x14000b4dd  jmp     short loc_14000B4FC
0x14000b4df  cmp     r8d, 111h
0x14000b4e6  jnz     loc_14000B5B5
0x14000b4ec  lea     eax, [r8-44h]
0x14000b4f0  cmp     ax, si
0x14000b4f3  jnz     short loc_14000B512
0x14000b4f5  xor     edx, edx; int
0x14000b4f7  call    ?_StartBurn@CIsoBurnUI@@AEAAXH@Z; CIsoBurnUI::_StartBurn(int)
0x14000b4fc  mov     rax, [rsp+68h+arg_28]
0x14000b504  mov     qword ptr [rax], 0
0x14000b50b  mov     eax, edi
0x14000b50d  jmp     loc_14000B6D4
0x14000b512  mov     r14d, 2
0x14000b518  cmp     r14w, si
0x14000b51c  jnz     loc_14000B637
0x14000b522  mov     eax, [rcx+0B8h]
0x14000b528  test    eax, eax
0x14000b52a  jnz     short loc_14000B53A
0x14000b52c  mov     rcx, [rcx+8]; hDlg
0x14000b530  xor     edx, edx; nResult
0x14000b532  call    cs:__imp_EndDialog
0x14000b538  jmp     short loc_14000B4FC
0x14000b53a  cmp     eax, edi
0x14000b53c  jnz     short loc_14000B4FC
0x14000b53e  mov     r9d, 108h; lpcTitle
0x14000b544  mov     [rcx+0B8h], r14d
0x14000b54b  mov     rcx, cs:hInstance; hAppInst
0x14000b552  xor     edx, edx; hWnd
0x14000b554  mov     [rsp+68h+fuStyle], 134h; fuStyle
0x14000b55c  lea     r8d, [r9-1]; lpcText
0x14000b560  call    cs:__imp_ShellMessageBoxW
0x14000b566  cmp     [rbx+0B8h], r14d
0x14000b56d  jnz     short loc_14000B4FC
0x14000b56f  cmp     eax, 6
0x14000b572  jnz     short loc_14000B5AA
0x14000b574  mov     dword ptr [rbx+0B8h], 3
0x14000b57e  mov     edx, r14d; nIDDlgItem
0x14000b581  mov     rcx, [rbx+8]; hDlg
0x14000b585  call    cs:__imp_GetDlgItem
0x14000b58b  mov     rcx, rax; hWnd
0x14000b58e  xor     edx, edx; bEnable
0x14000b590  call    cs:__imp_EnableWindow
0x14000b596  mov     rcx, [rbx+8]
0x14000b59a  mov     edx, 8001h
0x14000b59f  mov     r8d, 0Bh
0x14000b5a5  jmp     loc_14000B4C5
0x14000b5aa  mov     [rbx+0B8h], edi
0x14000b5b0  jmp     loc_14000B4FC
0x14000b5b5  cmp     r8d, 53h ; 'S'
0x14000b5b9  jnz     short loc_14000B637
0x14000b5bb  lea     rax, [rsp+68h+ppv]
0x14000b5c0  mov     [rsp+68h+ppv], 0
0x14000b5c9  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x14000b5d0  mov     qword ptr [rsp+68h+fuStyle], rax; ppv
0x14000b5d5  mov     r8d, edi; dwClsContext
0x14000b5d8  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x14000b5df  xor     edx, edx; pUnkOuter
0x14000b5e1  call    cs:__imp_CoCreateInstance
0x14000b5e7  test    eax, eax
0x14000b5e9  js      loc_14000B4FC
0x14000b5ef  lea     rcx, aMshelpWindowsI; "mshelp://windows/?id=13aca111-6547-4dfd"...
0x14000b5f6  call    cs:__imp_SysAllocString
0x14000b5fc  mov     rbx, rax
0x14000b5ff  test    rax, rax
0x14000b602  jz      short loc_14000B621
0x14000b604  mov     rcx, [rsp+68h+ppv]
0x14000b609  mov     rdx, [rcx]
0x14000b60c  mov     rax, [rdx+18h]
0x14000b610  mov     rdx, rbx
0x14000b613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b618  mov     rcx, rbx; bstrString
0x14000b61b  call    cs:__imp_SysFreeString
0x14000b621  mov     rcx, [rsp+68h+ppv]
0x14000b626  mov     rax, [rcx]
0x14000b629  mov     rax, [rax+10h]
0x14000b62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b632  jmp     loc_14000B4FC
0x14000b637  mov     eax, [rcx+0BCh]
0x14000b63d  test    eax, eax
0x14000b63f  jz      loc_14000B6D2
0x14000b645  cmp     r8d, eax
0x14000b648  jnz     loc_14000B6D2
0x14000b64e  mov     rcx, [rcx+8]; hDlg
0x14000b652  mov     edx, 0C9h; nIDDlgItem
0x14000b657  xor     r9d, r9d; wParam
0x14000b65a  mov     qword ptr [rsp+68h+fuStyle], 0; lParam
0x14000b663  lea     r8d, [rdx+7Eh]; Msg
0x14000b667  call    cs:__imp_SendDlgItemMessageW
0x14000b66d  mov     rcx, [rbx+98h]; hdpa
0x14000b674  xor     ebx, ebx
0x14000b676  mov     rdx, rax; i
0x14000b679  test    rcx, rcx
0x14000b67c  jz      short loc_14000B6C2
0x14000b67e  test    rax, rax
0x14000b681  js      short loc_14000B6C2
0x14000b683  movsxd  rax, dword ptr [rcx]
0x14000b686  cmp     rdx, rax
0x14000b689  jge     short loc_14000B6C2
0x14000b68b  xor     eax, eax
0x14000b68d  mov     [rsp+68h+arg_30], ax
0x14000b695  call    cs:__imp_DPA_GetPtr
0x14000b69b  mov     rcx, rax; lpszVolumeName
0x14000b69e  lea     rdx, [rsp+68h+arg_30]; unsigned __int16 *
0x14000b6a6  call    ?_GetDriveLetterForVolumeName@CIsoBurnUI@@CAJPEBGPEAG@Z; CIsoBurnUI::_GetDriveLetterForVolumeName(ushort const *,ushort *)
0x14000b6ab  test    eax, eax
0x14000b6ad  js      short loc_14000B6C2
0x14000b6af  movzx   eax, [rsp+68h+arg_30]
0x14000b6b7  lea     rcx, [rsi+41h]
0x14000b6bb  cmp     rax, rcx
0x14000b6be  cmovz   rbx, rdi
0x14000b6c2  mov     rax, [rsp+68h+arg_28]
0x14000b6ca  mov     [rax], rbx
0x14000b6cd  jmp     loc_14000B50B
0x14000b6d2  xor     eax, eax
0x14000b6d4  add     rsp, 48h
0x14000b6d8  pop     r14
0x14000b6da  pop     rdi
0x14000b6db  pop     rsi
0x14000b6dc  pop     rbx
0x14000b6dd  retn
```
