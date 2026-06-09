# TestDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x10051f6c0`
- end: `0x10051f8f7`
- name: `?TestDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `567`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x100518ac4`
- `0x10051f6c0`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x10051f83b`
- `KERNEL32!SetEvent` at `0x10051f83b`
- `KERNEL32!CloseHandle` at `0x10051f730`
- `KERNEL32!CloseHandle` at `0x10051f730`
- `USER32!SetWindowLongPtrW` at `0x10051f761`
- `USER32!SetWindowLongPtrW` at `0x10051f761`
- `USER32!GetWindowLongPtrW` at `0x10051f70d`
- `USER32!GetWindowLongPtrW` at `0x10051f70d`
- `USER32!EnableWindow` at `0x10051f78b`
- `USER32!EnableWindow` at `0x10051f78b`
- `USER32!GetDlgItem` at `0x10051f780`
- `USER32!GetDlgItem` at `0x10051f799`
- `USER32!GetDlgItem` at `0x10051f879`
- `USER32!GetDlgItem` at `0x10051f780`
- `USER32!GetDlgItem` at `0x10051f799`
- `USER32!GetDlgItem` at `0x10051f879`
- `USER32!EndDialog` at `0x10051f74e`
- `USER32!EndDialog` at `0x10051f74e`
- `USER32!ShowWindow` at `0x10051f851`
- `USER32!ShowWindow` at `0x10051f851`
- `ole32!CoCreateInstance` at `0x10051f7c5`
- `ole32!CoCreateInstance` at `0x10051f7c5`

## pseudocode

```c
INT_PTR __fastcall TestDlgProc(HWND a1, int a2, __int16 a3, LONG_PTR a4)
{
  int v7; // edx
  int v8; // edx
  LONG_PTR WindowLongPtrW; // rax
  LONG_PTR v10; // rsi
  HWND DlgItem; // rax
  HWND v12; // r14
  __int64 v13; // rax
  void (__fastcall *v14)(LPVOID, HWND, __int64, _QWORD, GUID *, GUID *); // rax
  HWND v16; // rax
  GUID v17; // [rsp+40h] [rbp-78h] BYREF
  __int64 v18; // [rsp+50h] [rbp-68h]
  GUID v19; // [rsp+60h] [rbp-58h] BYREF
  __int64 v20; // [rsp+70h] [rbp-48h]

  v7 = a2 - 2;
  if ( v7 )
  {
    v8 = v7 - 270;
    if ( v8 )
    {
      if ( v8 == 1 )
      {
        WindowLongPtrW = GetWindowLongPtrW(a1, -21);
        v10 = WindowLongPtrW;
        if ( a3 == 1 || a3 == 2 )
        {
          CloseHandle(*(HANDLE *)(WindowLongPtrW + 1800));
          *(_QWORD *)(v10 + 1800) = 0;
          EndDialog(a1, a3 == 1);
          return 1;
        }
      }
    }
    else
    {
      SetWindowLongPtrW(a1, -21, a4);
      CenterDialog(a1);
      *(_QWORD *)(a4 + 1808) = a1;
      DlgItem = GetDlgItem(a1, 1);
      EnableWindow(DlgItem, 0);
      v12 = GetDlgItem(a1, 30719);
      if ( CoCreateInstance(&CLSID_AccPropServices, 0, 3u, &GUID_6e26e776_04f0_495d_80e4_3330352e3169, &qword_1005D9DD8) >= 0 )
      {
        LOWORD(v19.Data1) = 3;
        v13 = *(_QWORD *)qword_1005D9DD8;
        *(_DWORD *)v19.Data4 = 2;
        v14 = *(void (__fastcall **)(LPVOID, HWND, __int64, _QWORD, GUID *, GUID *))(v13 + 48);
        v17 = v19;
        v18 = v20;
        v19 = LiveSetting_Property_GUID;
        v14(qword_1005D9DD8, v12, 4294967292LL, 0, &v19, &v17);
      }
      if ( SetEvent(*(HANDLE *)(a4 + 1816)) )
      {
        ShowWindow(a1, 5);
        return 1;
      }
    }
  }
  else if ( qword_1005D9DD8 )
  {
    v19 = LiveSetting_Property_GUID;
    v16 = GetDlgItem(a1, 30719);
    (*(void (__fastcall **)(LPVOID, HWND, __int64, _QWORD, GUID *, int))(*(_QWORD *)qword_1005D9DD8 + 72LL))(
      qword_1005D9DD8,
      v16,
      4294967292LL,
      0,
      &v19,
      1);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)qword_1005D9DD8 + 16LL))(qword_1005D9DD8);
    qword_1005D9DD8 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x10051f6c0  mov     [rsp+arg_8], rbx
0x10051f6c5  push    rbp
0x10051f6c6  push    rsi
0x10051f6c7  push    rdi
0x10051f6c8  push    r14
0x10051f6ca  push    r15
0x10051f6cc  sub     rsp, 90h
0x10051f6d3  mov     rax, cs:__security_cookie
0x10051f6da  xor     rax, rsp
0x10051f6dd  mov     [rsp+0B8h+var_38], rax
0x10051f6e5  mov     rbp, r9
0x10051f6e8  mov     rbx, r8
0x10051f6eb  mov     rdi, rcx
0x10051f6ee  sub     edx, 2
0x10051f6f1  jz      loc_10051F85C
0x10051f6f7  sub     edx, 10Eh
0x10051f6fd  jz      short loc_10051F759
0x10051f6ff  cmp     edx, 1
0x10051f702  jnz     loc_10051F8CE
0x10051f708  mov     edx, 0FFFFFFEBh; nIndex
0x10051f70d  call    cs:__imp_GetWindowLongPtrW
0x10051f713  movzx   ebp, bx
0x10051f716  mov     rsi, rax
0x10051f719  mov     edx, ebp
0x10051f71b  sub     edx, 1
0x10051f71e  jz      short loc_10051F729
0x10051f720  cmp     edx, 1
0x10051f723  jnz     loc_10051F8CE
0x10051f729  mov     rcx, [rax+708h]; hObject
0x10051f730  call    cs:__imp_CloseHandle
0x10051f736  xor     ebx, ebx
0x10051f738  mov     rcx, rdi; hDlg
0x10051f73b  mov     [rsi+708h], rbx
0x10051f742  lea     esi, [rbx+1]
0x10051f745  cmp     bp, si
0x10051f748  setz    bl
0x10051f74b  mov     rdx, rbx; nResult
0x10051f74e  call    cs:__imp_EndDialog
0x10051f754  jmp     loc_10051F857
0x10051f759  mov     r8, rbp; dwNewLong
0x10051f75c  mov     edx, 0FFFFFFEBh; nIndex
0x10051f761  call    cs:__imp_SetWindowLongPtrW
0x10051f767  mov     rcx, rdi; hWnd
0x10051f76a  call    ?CenterDialog@@YAXPEAUHWND__@@@Z; CenterDialog(HWND__ *)
0x10051f76f  mov     esi, 1
0x10051f774  mov     [rbp+710h], rdi
0x10051f77b  mov     edx, esi; nIDDlgItem
0x10051f77d  mov     rcx, rdi; hDlg
0x10051f780  call    cs:__imp_GetDlgItem
0x10051f786  mov     rcx, rax; hWnd
0x10051f789  xor     edx, edx; bEnable
0x10051f78b  call    cs:__imp_EnableWindow
0x10051f791  mov     edx, 77FFh; nIDDlgItem
0x10051f796  mov     rcx, rdi; hDlg
0x10051f799  call    cs:__imp_GetDlgItem
0x10051f79f  lea     r15d, [rsi+2]
0x10051f7a3  xor     edx, edx; pUnkOuter
0x10051f7a5  mov     r14, rax
0x10051f7a8  lea     r9, _GUID_6e26e776_04f0_495d_80e4_3330352e3169; riid
0x10051f7af  lea     rax, qword_1005D9DD8
0x10051f7b6  mov     r8d, r15d; dwClsContext
0x10051f7b9  lea     rcx, CLSID_AccPropServices; rclsid
0x10051f7c0  mov     [rsp+0B8h+ppv], rax; ppv
0x10051f7c5  call    cs:__imp_CoCreateInstance
0x10051f7cb  test    eax, eax
0x10051f7cd  js      short loc_10051F834
0x10051f7cf  mov     rcx, cs:qword_1005D9DD8
0x10051f7d6  lea     rdx, [rsp+0B8h+var_78]
0x10051f7db  movsd   xmm1, [rsp+0B8h+var_48]
0x10051f7e1  xor     r9d, r9d
0x10051f7e4  mov     [rsp+0B8h+var_90], rdx
0x10051f7e9  mov     r8d, 0FFFFFFFCh
0x10051f7ef  mov     word ptr [rsp+0B8h+var_58], r15w
0x10051f7f5  lea     rdx, [rsp+0B8h+var_58]
0x10051f7fa  mov     rax, [rcx]
0x10051f7fd  mov     dword ptr [rsp+0B8h+var_58+8], 2
0x10051f805  movups  xmm0, [rsp+0B8h+var_58]
0x10051f80a  mov     [rsp+0B8h+ppv], rdx
0x10051f80f  mov     rdx, r14
0x10051f812  mov     rax, [rax+30h]
0x10051f816  movaps  [rsp+0B8h+var_78], xmm0
0x10051f81b  movups  xmm0, xmmword ptr cs:LiveSetting_Property_GUID.Data1
0x10051f822  movsd   [rsp+0B8h+var_68], xmm1
0x10051f828  movdqu  [rsp+0B8h+var_58], xmm0
0x10051f82e  call    cs:__guard_dispatch_icall_fptr
0x10051f834  mov     rcx, [rbp+718h]; hEvent
0x10051f83b  call    cs:__imp_SetEvent
0x10051f841  test    eax, eax
0x10051f843  jz      loc_10051F8CE
0x10051f849  mov     edx, 5; nCmdShow
0x10051f84e  mov     rcx, rdi; hWnd
0x10051f851  call    cs:__imp_ShowWindow
0x10051f857  mov     rax, rsi
0x10051f85a  jmp     short loc_10051F8D0
0x10051f85c  xor     ebx, ebx
0x10051f85e  cmp     cs:qword_1005D9DD8, rbx
0x10051f865  jz      short loc_10051F8CE
0x10051f867  movups  xmm0, xmmword ptr cs:LiveSetting_Property_GUID.Data1
0x10051f86e  mov     edx, 77FFh; nIDDlgItem
0x10051f873  movdqu  [rsp+0B8h+var_58], xmm0
0x10051f879  call    cs:__imp_GetDlgItem
0x10051f87f  mov     rcx, cs:qword_1005D9DD8
0x10051f886  lea     esi, [rbx+1]
0x10051f889  mov     r10, rax
0x10051f88c  mov     dword ptr [rsp+0B8h+var_90], esi
0x10051f890  xor     r9d, r9d
0x10051f893  mov     r8d, 0FFFFFFFCh
0x10051f899  mov     rdx, [rcx]
0x10051f89c  mov     rax, [rdx+48h]
0x10051f8a0  lea     rdx, [rsp+0B8h+var_58]
0x10051f8a5  mov     [rsp+0B8h+ppv], rdx
0x10051f8aa  mov     rdx, r10
0x10051f8ad  call    cs:__guard_dispatch_icall_fptr
0x10051f8b3  mov     rcx, cs:qword_1005D9DD8
0x10051f8ba  mov     rax, [rcx]
0x10051f8bd  mov     rax, [rax+10h]
0x10051f8c1  call    cs:__guard_dispatch_icall_fptr
0x10051f8c7  mov     cs:qword_1005D9DD8, rbx
0x10051f8ce  xor     eax, eax
0x10051f8d0  mov     rcx, [rsp+0B8h+var_38]
0x10051f8d8  xor     rcx, rsp; StackCookie
0x10051f8db  call    __security_check_cookie
0x10051f8e0  mov     rbx, [rsp+0B8h+arg_8]
0x10051f8e8  add     rsp, 90h
0x10051f8ef  pop     r15
0x10051f8f1  pop     r14
0x10051f8f3  pop     rdi
0x10051f8f4  pop     rsi
0x10051f8f5  pop     rbp
0x10051f8f6  retn
```
