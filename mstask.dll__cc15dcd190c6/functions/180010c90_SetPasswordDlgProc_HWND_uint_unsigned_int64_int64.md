# SetPasswordDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180010c90`
- end: `0x180010fd9`
- name: `?SetPasswordDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `841`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task`

## callees

- `0x180001840`
- `0x180009ef8`
- `0x180009f38`
- `0x1800104c4`
- `0x180010c90`
- `0x180017e90`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180010d87`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180010d87`
- `USER32!SendMessageW` at `0x180010f20`
- `USER32!SendMessageW` at `0x180010f3f`
- `USER32!SendMessageW` at `0x180010f20`
- `USER32!SendMessageW` at `0x180010f3f`
- `USER32!GetDlgItem` at `0x180010f07`
- `USER32!GetDlgItem` at `0x180010f2e`
- `USER32!GetDlgItem` at `0x180010f07`
- `USER32!GetDlgItem` at `0x180010f2e`
- `USER32!WinHelpW` at `0x180010fa4`
- `USER32!WinHelpW` at `0x180010fa4`
- `USER32!GetDlgItemTextW` at `0x180010d5a`
- `USER32!GetDlgItemTextW` at `0x180010d75`
- `USER32!GetDlgItemTextW` at `0x180010d5a`
- `USER32!GetDlgItemTextW` at `0x180010d75`
- `USER32!SetDlgItemTextW` at `0x180010f58`
- `USER32!SetDlgItemTextW` at `0x180010f71`
- `USER32!SetDlgItemTextW` at `0x180010f58`
- `USER32!SetDlgItemTextW` at `0x180010f71`
- `USER32!EndDialog` at `0x180010eed`
- `USER32!EndDialog` at `0x180010eed`

## string_xrefs

- `0x180010f9d`: `%windir%\help\mstask.hlp`

## pseudocode

```c
INT_PTR __fastcall SetPasswordDlgProc(HWND a1, int a2, INT_PTR a3, __int64 a4)
{
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  __int64 v11; // rdi
  UINT DlgItemTextW; // r14d
  unsigned int v14; // r8d
  unsigned __int16 *v15; // r9
  __int64 v16; // rcx
  WCHAR *p_String; // rax
  WCHAR *p_String2; // rcx
  __int64 v19; // r15
  UINT v20; // r13d
  unsigned __int16 *v21; // rax
  unsigned int v22; // r8d
  unsigned __int16 *v23; // r9
  unsigned __int16 *v24; // r14
  WCHAR *v25; // rax
  __int64 v26; // r10
  __int64 v27; // rcx
  WCHAR *v28; // rax
  unsigned __int16 *v29; // rax
  unsigned int v30; // r8d
  unsigned __int16 *v31; // r9
  __int64 v32; // rcx
  const WCHAR *v33; // rax
  __int64 i; // r15
  __int64 v35; // rcx
  WCHAR *v36; // rax
  WCHAR *v37; // rax
  HWND DlgItem; // rax
  HWND v39; // rax
  UINT v40; // r8d
  HWND v41; // rcx
  WCHAR String; // [rsp+20h] [rbp-E0h] BYREF
  char v43[526]; // [rsp+22h] [rbp-DEh] BYREF
  WCHAR String2; // [rsp+230h] [rbp+130h] BYREF
  char v45[526]; // [rsp+232h] [rbp+132h] BYREF

  String = 0;
  memset_0(v43, 0, 0x200u);
  String2 = 0;
  memset_0(v45, 0, 0x200u);
  v8 = a2 - 83;
  if ( !v8 )
  {
    v41 = *(HWND *)(a4 + 16);
    v40 = 12;
    goto LABEL_43;
  }
  v9 = v8 - 40;
  if ( !v9 )
  {
    v40 = 10;
    v41 = (HWND)a3;
LABEL_43:
    WinHelpW(v41, szMstaskHelp, v40, (ULONG_PTR)L"f");
    return 1;
  }
  v10 = v9 - 149;
  if ( v10 )
  {
    if ( v10 != 1 )
      return 0;
    v11 = 514;
    if ( (unsigned __int16)a3 == 1 )
    {
      DlgItemTextW = GetDlgItemTextW(a1, 1002, &String, 257);
      GetDlgItemTextW(a1, 1001, &String2, 257);
      if ( lstrcmpW(&String, &String2) )
      {
        v16 = 514;
        p_String = &String;
        do
        {
          *(_BYTE *)p_String = 0;
          p_String = (WCHAR *)((char *)p_String + 1);
          --v16;
        }
        while ( v16 );
        p_String2 = &String2;
        do
        {
          *(_BYTE *)p_String2 = 0;
          p_String2 = (WCHAR *)((char *)p_String2 + 1);
          --v11;
        }
        while ( v11 );
        SchedUIMessageDialog(a1, 4134, v14, v15);
        return 1;
      }
      v19 = -1;
      if ( DlgItemTextW )
      {
        v20 = DlgItemTextW + 1;
        v21 = (unsigned __int16 *)operator new(saturated_mul(DlgItemTextW + 1, 2u));
        v24 = v21;
        if ( v21 )
        {
          StringCchCopyW(v21, v20, &String);
          v25 = &String;
          v26 = 514;
          do
          {
            *(_BYTE *)v25 = 0;
            v25 = (WCHAR *)((char *)v25 + 1);
            --v26;
          }
          while ( v26 );
          v27 = 514;
          v28 = &String2;
          do
          {
            *(_BYTE *)v28 = 0;
            v28 = (WCHAR *)((char *)v28 + 1);
            --v27;
          }
          while ( v27 );
        }
        else
        {
          SchedUIMessageDialog(a1, 4135, v22, v23);
        }
      }
      else
      {
        v29 = (unsigned __int16 *)operator new(2u);
        v24 = v29;
        if ( !v29 )
        {
          SchedUIMessageDialog(a1, 4135, v30, v31);
LABEL_39:
          EndDialog(a1, a3);
          return 1;
        }
        *v29 = 0;
      }
      v32 = qword_180023ED8;
      if ( qword_180023ED8 )
      {
        v33 = *(const WCHAR **)(qword_180023ED8 + 8);
        if ( v33 && v33 != &::String )
        {
          do
            ++v19;
          while ( v33[v19] );
          for ( i = 2 * v19 + 2; i; --i )
          {
            *(_BYTE *)v33 = 0;
            v33 = (const WCHAR *)((char *)v33 + 1);
          }
          operator delete(*(void **)(v32 + 8));
          v32 = qword_180023ED8;
        }
        *(_QWORD *)(v32 + 8) = v24;
      }
    }
    else if ( (unsigned __int16)a3 != 2 )
    {
      return 0;
    }
    v35 = 514;
    v36 = &String;
    do
    {
      *(_BYTE *)v36 = 0;
      v36 = (WCHAR *)((char *)v36 + 1);
      --v35;
    }
    while ( v35 );
    v37 = &String2;
    do
    {
      *(_BYTE *)v37 = 0;
      v37 = (WCHAR *)((char *)v37 + 1);
      --v11;
    }
    while ( v11 );
    goto LABEL_39;
  }
  qword_180023ED8 = a4;
  DlgItem = GetDlgItem(a1, 1002);
  SendMessageW(DlgItem, 0xC5u, 0x100u, 0);
  v39 = GetDlgItem(a1, 1001);
  SendMessageW(v39, 0xC5u, 0x100u, 0);
  SetDlgItemTextW(a1, 1002, *(LPCWSTR *)(qword_180023ED8 + 8));
  SetDlgItemTextW(a1, 1001, *(LPCWSTR *)(qword_180023ED8 + 8));
  CenterDialog(a1);
  return 1;
}

```

## disassembly

```asm
0x180010c90  mov     [rsp-8+arg_8], rbx
0x180010c95  push    rbp
0x180010c96  push    rsi
0x180010c97  push    rdi
0x180010c98  push    r12
0x180010c9a  push    r13
0x180010c9c  push    r14
0x180010c9e  push    r15
0x180010ca0  lea     rbp, [rsp-350h]
0x180010ca8  sub     rsp, 450h
0x180010caf  mov     rax, cs:__security_cookie
0x180010cb6  xor     rax, rsp
0x180010cb9  mov     [rbp+380h+var_40], rax
0x180010cc0  mov     r12, r8
0x180010cc3  mov     ebx, edx
0x180010cc5  mov     rsi, rcx
0x180010cc8  mov     r14d, 200h
0x180010cce  xor     r13d, r13d
0x180010cd1  lea     rcx, [rsp+480h+var_45E]; void *
0x180010cd6  mov     r8d, r14d; Size
0x180010cd9  mov     [rsp+480h+String], r13w
0x180010cdf  xor     edx, edx; Val
0x180010ce1  mov     rdi, r9
0x180010ce4  call    memset_0
0x180010ce9  mov     r8d, r14d; Size
0x180010cec  mov     [rbp+380h+String2], r13w
0x180010cf4  xor     edx, edx; Val
0x180010cf6  lea     rcx, [rbp+380h+var_24E]; void *
0x180010cfd  call    memset_0
0x180010d02  sub     ebx, 53h ; 'S'
0x180010d05  jz      loc_180010F8C
0x180010d0b  sub     ebx, 28h ; '('
0x180010d0e  jz      loc_180010F81
0x180010d14  sub     ebx, 95h
0x180010d1a  jz      loc_180010EF8
0x180010d20  cmp     ebx, 1
0x180010d23  jnz     short loc_180010D3D
0x180010d25  movzx   ecx, r12w
0x180010d29  lea     ebx, [r13+1]
0x180010d2d  lea     edi, [r14+2]
0x180010d31  sub     ecx, ebx
0x180010d33  jz      short loc_180010D44
0x180010d35  cmp     ecx, ebx
0x180010d37  jz      loc_180010EB3
0x180010d3d  xor     eax, eax
0x180010d3f  jmp     loc_180010FAF
0x180010d44  mov     r15d, 101h
0x180010d4a  lea     r8, [rsp+480h+String]; lpString
0x180010d4f  mov     r9d, r15d; cchMax
0x180010d52  mov     edx, 3EAh; nIDDlgItem
0x180010d57  mov     rcx, rsi; hDlg
0x180010d5a  call    cs:__imp_GetDlgItemTextW
0x180010d60  mov     r9d, r15d; cchMax
0x180010d63  lea     r8, [rbp+380h+String2]; lpString
0x180010d6a  mov     edx, 3E9h; nIDDlgItem
0x180010d6f  mov     rcx, rsi; hDlg
0x180010d72  mov     r14d, eax
0x180010d75  call    cs:__imp_GetDlgItemTextW
0x180010d7b  lea     rdx, [rbp+380h+String2]; lpString2
0x180010d82  lea     rcx, [rsp+480h+String]; lpString1
0x180010d87  call    cs:__imp_lstrcmpW
0x180010d8d  test    eax, eax
0x180010d8f  jz      short loc_180010DCB
0x180010d91  mov     rcx, rdi
0x180010d94  lea     rax, [rsp+480h+String]
0x180010d99  mov     [rax], r13b
0x180010d9c  add     rax, rbx
0x180010d9f  sub     rcx, rbx
0x180010da2  jnz     short loc_180010D99
0x180010da4  lea     rcx, [rbp+380h+String2]
0x180010dab  mov     [rcx], r13b
0x180010dae  add     rcx, rbx
0x180010db1  sub     rdi, rbx
0x180010db4  jnz     short loc_180010DAB
0x180010db6  mov     edx, 1026h; int
0x180010dbb  mov     rcx, rsi; HWND
0x180010dbe  call    ?SchedUIMessageDialog@@YAHPEAUHWND__@@HIPEAG@Z; SchedUIMessageDialog(HWND__ *,int,uint,ushort *)
0x180010dc3  mov     rax, rbx
0x180010dc6  jmp     loc_180010FAF
0x180010dcb  or      r15, 0FFFFFFFFFFFFFFFFh
0x180010dcf  test    r14d, r14d
0x180010dd2  jz      short loc_180010E42
0x180010dd4  lea     r13d, [r14+1]
0x180010dd8  lea     eax, [r15+3]
0x180010ddc  mul     r13
0x180010ddf  cmovb   rax, r15
0x180010de3  mov     rcx, rax; Size
0x180010de6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010deb  mov     r14, rax
0x180010dee  test    rax, rax
0x180010df1  jz      short loc_180010E30
0x180010df3  lea     r8, [rsp+480h+String]; unsigned __int16 *
0x180010df8  mov     edx, r13d; unsigned __int64
0x180010dfb  mov     rcx, rax; unsigned __int16 *
0x180010dfe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010e03  lea     rax, [rsp+480h+String]
0x180010e08  xor     r13d, r13d
0x180010e0b  mov     r10, rdi
0x180010e0e  mov     [rax], r13b
0x180010e11  add     rax, rbx
0x180010e14  sub     r10, rbx
0x180010e17  jnz     short loc_180010E0E
0x180010e19  mov     rcx, rdi
0x180010e1c  lea     rax, [rbp+380h+String2]
0x180010e23  mov     [rax], r13b
0x180010e26  add     rax, rbx
0x180010e29  sub     rcx, rbx
0x180010e2c  jnz     short loc_180010E23
0x180010e2e  jmp     short loc_180010E5C
0x180010e30  mov     edx, 1027h; int
0x180010e35  mov     rcx, rsi; HWND
0x180010e38  call    ?SchedUIMessageDialog@@YAHPEAUHWND__@@HIPEAG@Z; SchedUIMessageDialog(HWND__ *,int,uint,ushort *)
0x180010e3d  xor     r13d, r13d
0x180010e40  jmp     short loc_180010E5C
0x180010e42  mov     ecx, 2; Size
0x180010e47  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010e4c  mov     r14, rax
0x180010e4f  test    rax, rax
0x180010e52  jz      loc_180010EDA
0x180010e58  mov     [rax], r13w
0x180010e5c  mov     rcx, cs:qword_180023ED8
0x180010e63  test    rcx, rcx
0x180010e66  jz      short loc_180010EB3
0x180010e68  mov     rax, [rcx+8]
0x180010e6c  test    rax, rax
0x180010e6f  jz      short loc_180010EAF
0x180010e71  lea     rdx, String
0x180010e78  cmp     rax, rdx
0x180010e7b  jz      short loc_180010EAF
0x180010e7d  inc     r15
0x180010e80  cmp     [rax+r15*2], r13w
0x180010e85  jnz     short loc_180010E7D
0x180010e87  lea     r15, ds:2[r15*2]
0x180010e8f  test    r15, r15
0x180010e92  jz      short loc_180010E9F
0x180010e94  mov     [rax], r13b
0x180010e97  add     rax, rbx
0x180010e9a  sub     r15, rbx
0x180010e9d  jnz     short loc_180010E94
0x180010e9f  mov     rcx, [rcx+8]; Block
0x180010ea3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010ea8  mov     rcx, cs:qword_180023ED8
0x180010eaf  mov     [rcx+8], r14
0x180010eb3  mov     rcx, rdi
0x180010eb6  lea     rax, [rsp+480h+String]
0x180010ebb  mov     [rax], r13b
0x180010ebe  add     rax, rbx
0x180010ec1  sub     rcx, rbx
0x180010ec4  jnz     short loc_180010EBB
0x180010ec6  lea     rax, [rbp+380h+String2]
0x180010ecd  mov     [rax], r13b
0x180010ed0  add     rax, rbx
0x180010ed3  sub     rdi, rbx
0x180010ed6  jnz     short loc_180010ECD
0x180010ed8  jmp     short loc_180010EE7
0x180010eda  mov     edx, 1027h; int
0x180010edf  mov     rcx, rsi; HWND
0x180010ee2  call    ?SchedUIMessageDialog@@YAHPEAUHWND__@@HIPEAG@Z; SchedUIMessageDialog(HWND__ *,int,uint,ushort *)
0x180010ee7  mov     rdx, r12; nResult
0x180010eea  mov     rcx, rsi; hDlg
0x180010eed  call    cs:__imp_EndDialog
0x180010ef3  jmp     loc_180010DC3
0x180010ef8  mov     edx, 3EAh; nIDDlgItem
0x180010efd  mov     cs:qword_180023ED8, rdi
0x180010f04  mov     rcx, rsi; hDlg
0x180010f07  call    cs:__imp_GetDlgItem
0x180010f0d  mov     edi, 100h
0x180010f12  xor     r9d, r9d; lParam
0x180010f15  mov     rcx, rax; hWnd
0x180010f18  mov     r8d, edi; wParam
0x180010f1b  lea     ebx, [rdi-3Bh]
0x180010f1e  mov     edx, ebx; Msg
0x180010f20  call    cs:__imp_SendMessageW
0x180010f26  mov     edx, 3E9h; nIDDlgItem
0x180010f2b  mov     rcx, rsi; hDlg
0x180010f2e  call    cs:__imp_GetDlgItem
0x180010f34  xor     r9d, r9d; lParam
0x180010f37  mov     r8d, edi; wParam
0x180010f3a  mov     rcx, rax; hWnd
0x180010f3d  mov     edx, ebx; Msg
0x180010f3f  call    cs:__imp_SendMessageW
0x180010f45  mov     r8, cs:qword_180023ED8
0x180010f4c  mov     edx, 3EAh; nIDDlgItem
0x180010f51  mov     rcx, rsi; hDlg
0x180010f54  mov     r8, [r8+8]; lpString
0x180010f58  call    cs:__imp_SetDlgItemTextW
0x180010f5e  mov     r8, cs:qword_180023ED8
0x180010f65  mov     edx, 3E9h; nIDDlgItem
0x180010f6a  mov     rcx, rsi; hDlg
0x180010f6d  mov     r8, [r8+8]; lpString
0x180010f71  call    cs:__imp_SetDlgItemTextW
0x180010f77  mov     rcx, rsi; hWnd
0x180010f7a  call    ?CenterDialog@@YAXPEAUHWND__@@@Z; CenterDialog(HWND__ *)
0x180010f7f  jmp     short loc_180010FAA
0x180010f81  mov     r8d, 0Ah
0x180010f87  mov     rcx, r12
0x180010f8a  jmp     short loc_180010F96
0x180010f8c  mov     rcx, [rdi+10h]; hWndMain
0x180010f90  mov     r8d, 0Ch; uCommand
0x180010f96  lea     r9, dwData; "f"
0x180010f9d  lea     rdx, szMstaskHelp; "%windir%\\help\\mstask.hlp"
0x180010fa4  call    cs:__imp_WinHelpW
0x180010faa  mov     eax, 1
0x180010faf  mov     rcx, [rbp+380h+var_40]
0x180010fb6  xor     rcx, rsp; StackCookie
0x180010fb9  call    __security_check_cookie
0x180010fbe  mov     rbx, [rsp+480h+arg_8]
0x180010fc6  add     rsp, 450h
0x180010fcd  pop     r15
0x180010fcf  pop     r14
0x180010fd1  pop     r13
0x180010fd3  pop     r12
0x180010fd5  pop     rdi
0x180010fd6  pop     rsi
0x180010fd7  pop     rbp
0x180010fd8  retn
```
