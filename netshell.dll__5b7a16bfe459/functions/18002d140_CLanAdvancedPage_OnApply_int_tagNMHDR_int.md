# CLanAdvancedPage::OnApply(int,tagNMHDR *,int &)

- ea: `0x18002d140`
- end: `0x18002d4d2`
- name: `?OnApply@CLanAdvancedPage@@QEAA_JHPEAUtagNMHDR@@AEAH@Z`
- size: `914`
- prototype: `__int64 __fastcall(CLanAdvancedPage *__hidden this, int, struct tagNMHDR *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18002fc20`

## callees

- `0x180017714`
- `0x180018d74`
- `0x18001bc10`
- `0x18002cbb0`
- `0x18002d140`
- `0x18003ff7c`
- `0x180065010`

## import_xrefs

- `USER32!SendMessageW` at `0x18002d20c`
- `USER32!SendMessageW` at `0x18002d225`
- `USER32!SendMessageW` at `0x18002d379`
- `USER32!SendMessageW` at `0x18002d396`
- `USER32!SendMessageW` at `0x18002d20c`
- `USER32!SendMessageW` at `0x18002d225`
- `USER32!SendMessageW` at `0x18002d379`
- `USER32!SendMessageW` at `0x18002d396`
- `USER32!IsDlgButtonChecked` at `0x18002d191`
- `USER32!IsDlgButtonChecked` at `0x18002d471`
- `USER32!IsDlgButtonChecked` at `0x18002d191`
- `USER32!IsDlgButtonChecked` at `0x18002d471`
- `ADVAPI32!RegCloseKey` at `0x18002d4af`
- `ADVAPI32!RegCloseKey` at `0x18002d4af`
- `ADVAPI32!RegCreateKeyExW` at `0x18002d461`
- `ADVAPI32!RegCreateKeyExW` at `0x18002d461`
- `ADVAPI32!RegSetValueExW` at `0x18002d4a5`
- `ADVAPI32!RegSetValueExW` at `0x18002d4a5`
- `ole32!CoTaskMemFree` at `0x18002d25b`
- `ole32!CoTaskMemFree` at `0x18002d25b`

## string_xrefs

- `0x18002d437`: `System\CurrentControlSet\Control\Network\SharedAccessConnection`

## pseudocode

```c
__int64 __fastcall CLanAdvancedPage::OnApply(CLanAdvancedPage *this, int a2, struct tagNMHDR *a3, int *a4)
{
  HWND *v4; // r15
  bool v5; // zf
  HWND v7; // rcx
  int v8; // ebx
  char v9; // r14
  LRESULT v10; // rsi
  HWND v11; // rbx
  int v12; // eax
  int v13; // eax
  DWORD v14; // ecx
  HWND v15; // rsi
  int v16; // eax
  LRESULT v17; // rcx
  struct IUnknown *v19; // [rsp+50h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-20h] BYREF
  LPVOID pv[3]; // [rsp+60h] [rbp-18h] BYREF
  struct IUnknown *v22; // [rsp+C0h] [rbp+48h] BYREF
  int v23; // [rsp+C8h] [rbp+50h] BYREF
  struct tagNMHDR *Data; // [rsp+D0h] [rbp+58h] BYREF
  int *v25; // [rsp+D8h] [rbp+60h] BYREF

  v25 = a4;
  Data = a3;
  v23 = a2;
  v4 = (HWND *)((char *)this + 8);
  v5 = *((_DWORD *)this + 8) == 0;
  v7 = (HWND)*((_QWORD *)this + 1);
  v22 = 0;
  v19 = 0;
  LODWORD(v25) = 0;
  v23 = 0;
  pv[0] = 0;
  if ( !v5 != (IsDlgButtonChecked(v7, 105) != 0) )
  {
    if ( *((_DWORD *)this + 8) )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, int **, int *))(**((_QWORD **)this + 11) + 40LL))(
             *((_QWORD *)this + 11),
             &v25,
             &v23);
      if ( v8 >= 0 )
      {
        *((_DWORD *)this + 8) = 0;
        goto LABEL_39;
      }
      goto LABEL_23;
    }
    v9 = 0;
    if ( *((_DWORD *)this + 19) <= 1u )
    {
      v10 = **((_QWORD **)this + 8);
    }
    else
    {
      v10 = 0;
      v11 = *(HWND *)ATL::CWindow::GetDlgItem(v4, &Data, 107);
      v12 = SendMessageW(v11, 0x147u, 0, 0);
      if ( v12 == -1 )
        goto LABEL_12;
      v10 = SendMessageW(v11, 0x150u, v12, 0);
    }
    if ( v10 && (*(int (__fastcall **)(LRESULT, LPVOID *))(*(_QWORD *)v10 + 56LL))(v10, pv) >= 0 )
    {
      v9 = *((_BYTE *)pv[0] + 3);
      CoTaskMemFree(pv[0]);
    }
LABEL_12:
    if ( *((_DWORD *)this + 10) )
    {
      v13 = v9
          ? (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6))
          : (*(unsigned __int64 (__fastcall **)(_QWORD, int **, int *))(**((_QWORD **)this + 11) + 40LL))(
              *((_QWORD *)this + 11),
              &v25,
              &v23);
      v8 = v13;
      if ( v13 < 0 )
        goto LABEL_23;
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown **))(**((_QWORD **)this + 12) + 80LL))(
           *((_QWORD *)this + 12),
           &v19);
    if ( v8 < 0 )
      goto LABEL_23;
    if ( !v9 )
    {
      v8 = (*(__int64 (__fastcall **)(LRESULT, struct IUnknown **))(*(_QWORD *)v10 + 88LL))(v10, &v22);
      if ( v8 < 0 )
      {
        ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl[1].QueryInterface)(v19);
LABEL_22:
        ReleaseObj(v19);
        if ( v8 >= 0 )
          goto LABEL_39;
LABEL_23:
        v14 = (unsigned __int16)v8;
        if ( (unsigned __int16)v8 == 782 )
        {
          NcMsgBox(hInst, *v4, 0x3E90u, 0x3EB1u, 0x40u);
          goto LABEL_39;
        }
LABEL_38:
        NcRasMsgBoxWithErrorText(v14, hInst, *v4, 0x3E88u, 0x385u, (*((_DWORD *)this + 8) != 0) + 16030, 0x30u);
        goto LABEL_39;
      }
      ReleaseObj(v22);
    }
    *((_DWORD *)this + 8) = 1;
    goto LABEL_22;
  }
  v8 = 0;
  if ( *((_DWORD *)this + 14) && *((_DWORD *)this + 19) )
  {
    if ( *((_DWORD *)this + 19) <= 1u )
    {
      v17 = **((_QWORD **)this + 8);
    }
    else
    {
      v15 = *(HWND *)ATL::CWindow::GetDlgItem(v4, &Data, 107);
      v16 = SendMessageW(v15, 0x147u, 0, 0);
      if ( v16 == -1 )
        goto LABEL_39;
      v17 = SendMessageW(v15, 0x150u, v16, 0);
    }
    if ( v17 )
    {
      v8 = (*(__int64 (__fastcall **)(LRESULT, struct IUnknown **))(*(_QWORD *)v17 + 88LL))(v17, &v22);
      if ( v8 >= 0 )
      {
        ReleaseObj(v22);
        goto LABEL_39;
      }
      if ( (*(int (__fastcall **)(_QWORD, int **, int *))(**((_QWORD **)this + 11) + 40LL))(
             *((_QWORD *)this + 11),
             &v25,
             &v23) >= 0 )
        *((_DWORD *)this + 8) = 0;
      v14 = (unsigned __int16)v8;
      goto LABEL_38;
    }
  }
LABEL_39:
  hKey = 0;
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Network\\SharedAccessConnection",
          0,
          0,
          0,
          2u,
          0,
          &hKey,
          0) )
  {
    LODWORD(Data) = IsDlgButtonChecked(*v4, 109) == 1;
    RegSetValueExW(hKey, L"EnableControl", 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
  }
  if ( v8 < 0 )
    v8 = 1;
  return LresFromHr(v8);
}

```

## disassembly

```asm
0x18002d140  mov     [rsp-40h+arg_18], r9
0x18002d145  mov     [rsp-40h+Data], r8
0x18002d14a  mov     [rsp-40h+arg_8], edx
0x18002d14e  push    rbp
0x18002d14f  push    rbx
0x18002d150  push    rsi
0x18002d151  push    rdi
0x18002d152  push    r12
0x18002d154  push    r13
0x18002d156  push    r14
0x18002d158  push    r15
0x18002d15a  mov     rbp, rsp
0x18002d15d  sub     rsp, 78h
0x18002d161  xor     r12d, r12d
0x18002d164  lea     r15, [rcx+8]
0x18002d168  cmp     [rcx+20h], r12d
0x18002d16c  mov     rdi, rcx
0x18002d16f  mov     rcx, [r15]; hDlg
0x18002d172  mov     ebx, r12d
0x18002d175  mov     [rbp+arg_0], r12
0x18002d179  setnz   bl
0x18002d17c  lea     edx, [r12+69h]; nIDButton
0x18002d181  mov     [rbp+var_28], r12
0x18002d185  mov     dword ptr [rbp+arg_18], r12d
0x18002d189  mov     [rbp+arg_8], r12d
0x18002d18d  mov     [rbp+pv], r12
0x18002d191  call    cs:__imp_IsDlgButtonChecked
0x18002d197  mov     ecx, r12d
0x18002d19a  lea     r13d, [r12+1]
0x18002d19f  test    eax, eax
0x18002d1a1  setnz   cl
0x18002d1a4  cmp     ebx, ecx
0x18002d1a6  jz      loc_18002D339
0x18002d1ac  cmp     [rdi+20h], r12d
0x18002d1b0  jz      short loc_18002D1DD
0x18002d1b2  mov     rcx, [rdi+58h]
0x18002d1b6  lea     r8, [rbp+arg_8]
0x18002d1ba  lea     rdx, [rbp+arg_18]
0x18002d1be  mov     rax, [rcx]
0x18002d1c1  mov     rax, [rax+28h]
0x18002d1c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1ca  mov     ebx, eax
0x18002d1cc  test    eax, eax
0x18002d1ce  js      loc_18002D2F2
0x18002d1d4  mov     [rdi+20h], r12d
0x18002d1d8  jmp     loc_18002D429
0x18002d1dd  mov     r14b, r12b
0x18002d1e0  cmp     [rdi+4Ch], r13d
0x18002d1e4  jbe     short loc_18002D230
0x18002d1e6  mov     r8d, 6Bh ; 'k'
0x18002d1ec  lea     rdx, [rbp+Data]
0x18002d1f0  mov     rcx, r15
0x18002d1f3  mov     rsi, r12
0x18002d1f6  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x18002d1fb  xor     r9d, r9d; lParam
0x18002d1fe  xor     r8d, r8d; wParam
0x18002d201  mov     edx, 147h; Msg
0x18002d206  mov     rbx, [rax]
0x18002d209  mov     rcx, rbx; hWnd
0x18002d20c  call    cs:__imp_SendMessageW
0x18002d212  cmp     eax, 0FFFFFFFFh
0x18002d215  jz      short loc_18002D261
0x18002d217  movsxd  r8, eax; wParam
0x18002d21a  xor     r9d, r9d; lParam
0x18002d21d  mov     edx, 150h; Msg
0x18002d222  mov     rcx, rbx; hWnd
0x18002d225  call    cs:__imp_SendMessageW
0x18002d22b  mov     rsi, rax
0x18002d22e  jmp     short loc_18002D237
0x18002d230  mov     rax, [rdi+40h]
0x18002d234  mov     rsi, [rax]
0x18002d237  test    rsi, rsi
0x18002d23a  jz      short loc_18002D261
0x18002d23c  mov     rax, [rsi]
0x18002d23f  lea     rdx, [rbp+pv]
0x18002d243  mov     rcx, rsi
0x18002d246  mov     rax, [rax+38h]
0x18002d24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d24f  test    eax, eax
0x18002d251  js      short loc_18002D261
0x18002d253  mov     rcx, [rbp+pv]; pv
0x18002d257  mov     r14b, [rcx+3]
0x18002d25b  call    cs:__imp_CoTaskMemFree
0x18002d261  cmp     [rdi+28h], r12d
0x18002d265  jz      short loc_18002D29C
0x18002d267  test    r14b, r14b
0x18002d26a  jz      short loc_18002D27E
0x18002d26c  mov     rcx, [rdi+30h]
0x18002d270  mov     rax, [rcx]
0x18002d273  mov     rax, [rax+18h]
0x18002d277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d27c  jmp     short loc_18002D296
0x18002d27e  mov     rcx, [rdi+58h]
0x18002d282  lea     r8, [rbp+arg_8]
0x18002d286  lea     rdx, [rbp+arg_18]
0x18002d28a  mov     rax, [rcx]
0x18002d28d  mov     rax, [rax+28h]
0x18002d291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d296  mov     ebx, eax
0x18002d298  test    eax, eax
0x18002d29a  js      short loc_18002D2F2
0x18002d29c  mov     rcx, [rdi+60h]
0x18002d2a0  lea     rdx, [rbp+var_28]
0x18002d2a4  mov     rax, [rcx]
0x18002d2a7  mov     rax, [rax+50h]
0x18002d2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2b0  mov     ebx, eax
0x18002d2b2  test    eax, eax
0x18002d2b4  js      short loc_18002D2F2
0x18002d2b6  test    r14b, r14b
0x18002d2b9  jnz     short loc_18002D2DD
0x18002d2bb  mov     rax, [rsi]
0x18002d2be  lea     rdx, [rbp+arg_0]
0x18002d2c2  mov     rcx, rsi
0x18002d2c5  mov     rax, [rax+58h]
0x18002d2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2ce  mov     ebx, eax
0x18002d2d0  test    eax, eax
0x18002d2d2  js      short loc_18002D327
0x18002d2d4  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x18002d2d8  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002d2dd  mov     [rdi+20h], r13d
0x18002d2e1  mov     rcx, [rbp+var_28]; struct IUnknown *
0x18002d2e5  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002d2ea  test    ebx, ebx
0x18002d2ec  jns     loc_18002D429
0x18002d2f2  movzx   ecx, bx
0x18002d2f5  cmp     ecx, 30Eh
0x18002d2fb  jnz     loc_18002D3F1
0x18002d301  mov     rdx, [r15]; hWnd
0x18002d304  mov     r9d, 3EB1h; unsigned int
0x18002d30a  mov     rcx, cs:hInst; hModule
0x18002d311  mov     [rsp+78h+dwOptions], 40h ; '@'; uType
0x18002d319  lea     r8d, [r9-21h]; unsigned int
0x18002d31d  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18002d322  jmp     loc_18002D429
0x18002d327  mov     rcx, [rbp+var_28]
0x18002d32b  mov     rax, [rcx]
0x18002d32e  mov     rax, [rax+18h]
0x18002d332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d337  jmp     short loc_18002D2E1
0x18002d339  mov     ebx, r12d
0x18002d33c  cmp     [rdi+38h], r12d
0x18002d340  jz      loc_18002D429
0x18002d346  cmp     [rdi+4Ch], r12d
0x18002d34a  jz      loc_18002D429
0x18002d350  cmp     [rdi+4Ch], r13d
0x18002d354  jbe     short loc_18002D3A1
0x18002d356  mov     r8d, 6Bh ; 'k'
0x18002d35c  lea     rdx, [rbp+Data]
0x18002d360  mov     rcx, r15
0x18002d363  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x18002d368  xor     r9d, r9d; lParam
0x18002d36b  xor     r8d, r8d; wParam
0x18002d36e  mov     edx, 147h; Msg
0x18002d373  mov     rsi, [rax]
0x18002d376  mov     rcx, rsi; hWnd
0x18002d379  call    cs:__imp_SendMessageW
0x18002d37f  cmp     eax, 0FFFFFFFFh
0x18002d382  jz      loc_18002D429
0x18002d388  movsxd  r8, eax; wParam
0x18002d38b  xor     r9d, r9d; lParam
0x18002d38e  mov     edx, 150h; Msg
0x18002d393  mov     rcx, rsi; hWnd
0x18002d396  call    cs:__imp_SendMessageW
0x18002d39c  mov     rcx, rax
0x18002d39f  jmp     short loc_18002D3A8
0x18002d3a1  mov     rax, [rdi+40h]
0x18002d3a5  mov     rcx, [rax]
0x18002d3a8  test    rcx, rcx
0x18002d3ab  jz      short loc_18002D429
0x18002d3ad  mov     rax, [rcx]
0x18002d3b0  lea     rdx, [rbp+arg_0]
0x18002d3b4  mov     rax, [rax+58h]
0x18002d3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3bd  mov     ebx, eax
0x18002d3bf  test    eax, eax
0x18002d3c1  js      short loc_18002D3CE
0x18002d3c3  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x18002d3c7  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002d3cc  jmp     short loc_18002D429
0x18002d3ce  mov     rcx, [rdi+58h]
0x18002d3d2  lea     r8, [rbp+arg_8]
0x18002d3d6  lea     rdx, [rbp+arg_18]
0x18002d3da  mov     rax, [rcx]
0x18002d3dd  mov     rax, [rax+28h]
0x18002d3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3e6  test    eax, eax
0x18002d3e8  js      short loc_18002D3EE
0x18002d3ea  mov     [rdi+20h], r12d
0x18002d3ee  movzx   ecx, bx; dwMessageId
0x18002d3f1  mov     eax, [rdi+20h]
0x18002d3f4  mov     r9d, 3E88h; unsigned int
0x18002d3fa  mov     r8, [r15]; hWnd
0x18002d3fd  neg     eax
0x18002d3ff  mov     dword ptr [rsp+78h+lpSecurityAttributes], 30h ; '0'; uType
0x18002d407  sbb     edx, edx
0x18002d409  neg     edx
0x18002d40b  add     edx, 3E9Eh
0x18002d411  mov     [rsp+78h+samDesired], edx; unsigned int
0x18002d415  mov     rdx, cs:hInst; hModule
0x18002d41c  mov     [rsp+78h+dwOptions], 385h; unsigned int
0x18002d424  call    ?NcRasMsgBoxWithErrorText@@YAHKPEAUHINSTANCE__@@PEAUHWND__@@IIIIZZ; NcRasMsgBoxWithErrorText(ulong,HINSTANCE__ *,HWND__ *,uint,uint,uint,uint,...)
0x18002d429  mov     [rsp+78h+lpdwDisposition], r12; lpdwDisposition
0x18002d42e  lea     rax, [rbp+hKey]
0x18002d432  mov     [rsp+78h+phkResult], rax; phkResult
0x18002d437  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Net"...
0x18002d43e  mov     [rsp+78h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18002d443  xor     r9d, r9d; lpClass
0x18002d446  mov     [rsp+78h+samDesired], 2; samDesired
0x18002d44e  xor     r8d, r8d; Reserved
0x18002d451  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d458  mov     [rsp+78h+dwOptions], r12d; dwOptions
0x18002d45d  mov     [rbp+hKey], r12
0x18002d461  call    cs:__imp_RegCreateKeyExW
0x18002d467  test    eax, eax
0x18002d469  jnz     short loc_18002D4B5
0x18002d46b  mov     rcx, [r15]; hDlg
0x18002d46e  lea     edx, [rax+6Dh]; nIDButton
0x18002d471  call    cs:__imp_IsDlgButtonChecked
0x18002d477  mov     ecx, r12d
0x18002d47a  lea     rdx, ValueName; "EnableControl"
0x18002d481  cmp     eax, r13d
0x18002d484  mov     r9d, 4; dwType
0x18002d48a  lea     rax, [rbp+Data]
0x18002d48e  mov     [rsp+78h+samDesired], r9d; cbData
0x18002d493  setz    cl
0x18002d496  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x18002d49b  mov     dword ptr [rbp+Data], ecx
0x18002d49e  xor     r8d, r8d; Reserved
0x18002d4a1  mov     rcx, [rbp+hKey]; hKey
0x18002d4a5  call    cs:__imp_RegSetValueExW
0x18002d4ab  mov     rcx, [rbp+hKey]; hKey
0x18002d4af  call    cs:__imp_RegCloseKey
0x18002d4b5  test    ebx, ebx
0x18002d4b7  cmovs   ebx, r13d
0x18002d4bb  mov     ecx, ebx; int
0x18002d4bd  add     rsp, 78h
0x18002d4c1  pop     r15
0x18002d4c3  pop     r14
0x18002d4c5  pop     r13
0x18002d4c7  pop     r12
0x18002d4c9  pop     rdi
0x18002d4ca  pop     rsi
0x18002d4cb  pop     rbx
0x18002d4cc  pop     rbp
0x18002d4cd  jmp     ?LresFromHr@@YA_JJ@Z; LresFromHr(long)
```
