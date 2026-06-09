# CConfigGeneralPage::SelectDeviceDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800122c0`
- end: `0x18001249c`
- name: `?SelectDeviceDlgProc@CConfigGeneralPage@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `476`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000edb0`
- `0x1800118a4`
- `0x1800122c0`
- `0x180017010`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x18001242c`
- `USER32!SetWindowLongPtrW` at `0x18001242c`
- `USER32!GetWindowLongPtrW` at `0x18001232a`
- `USER32!GetWindowLongPtrW` at `0x18001232a`
- `USER32!SendMessageW` at `0x180012468`
- `USER32!SendMessageW` at `0x180012486`
- `USER32!SendMessageW` at `0x180012468`
- `USER32!SendMessageW` at `0x180012486`
- `USER32!EndDialog` at `0x180012351`
- `USER32!EndDialog` at `0x180012415`
- `USER32!EndDialog` at `0x180012351`
- `USER32!EndDialog` at `0x180012415`
- `USER32!GetDlgItem` at `0x18001243a`
- `USER32!GetDlgItem` at `0x18001243a`

## pseudocode

```c
INT_PTR __fastcall CConfigGeneralPage::SelectDeviceDlgProc(HWND a1, int a2, __int16 a3, LONG_PTR a4)
{
  int v8; // ebx
  CConfigGeneralPage *WindowLongPtrW; // rax
  CConfigGeneralPage *v10; // r14
  unsigned int v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // esi
  HWND i; // rbx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  v8 = a2 - 272;
  if ( v8 )
  {
    if ( v8 != 1 )
      return 0;
    WindowLongPtrW = (CConfigGeneralPage *)GetWindowLongPtrW(a1, -21);
    v10 = WindowLongPtrW;
    if ( !WindowLongPtrW )
      return 0;
    if ( a3 != 1 )
    {
      if ( a3 == 2 )
      {
        EndDialog(a1, 2);
        return 1;
      }
      return 0;
    }
    v12 = CConfigGeneralPage::SaveDeviceSelection(WindowLongPtrW, a1);
    v13 = v12;
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_f5b496eade1b3798203481970613ce29_Traceguids, v12);
      }
      if ( v13 != 1003 )
      {
        (*(__int64 (__fastcall **)(CConfigGeneralPage *, _QWORD))(*(_QWORD *)v10 + 48LL))(v10, v13);
        FaxMsgBox(a1, *((_QWORD *)v10 + 1), 4656);
      }
    }
    else
    {
      EndDialog(a1, 1);
    }
  }
  else
  {
    SetWindowLongPtrW(a1, -21, a4);
    v14 = 0;
    for ( i = GetDlgItem(a1, 4581); v14 < *(_DWORD *)(a4 + 40); ++v14 )
      SendMessageW(i, 0x143u, 0, *(_QWORD *)(*(_QWORD *)(a4 + 32) + 72LL * v14 + 8));
    SendMessageW(i, 0x14Du, 0xFFFFFFFFFFFFFFFFuLL, *(_QWORD *)(a4 + 56));
  }
  return 1;
}

```

## disassembly

```asm
0x1800122c0  push    rbx
0x1800122c2  push    rbp
0x1800122c3  push    rsi
0x1800122c4  push    rdi
0x1800122c5  push    r12
0x1800122c7  push    r14
0x1800122c9  sub     rsp, 38h
0x1800122cd  mov     r14, r9
0x1800122d0  mov     rdi, r8
0x1800122d3  mov     ebx, edx
0x1800122d5  mov     rbp, rcx
0x1800122d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122df  lea     r12, WPP_GLOBAL_Control
0x1800122e6  cmp     rcx, r12
0x1800122e9  jz      short loc_18001230F
0x1800122eb  test    dword ptr [rcx+1Ch], 100h
0x1800122f2  jz      short loc_18001230F
0x1800122f4  cmp     byte ptr [rcx+19h], 5
0x1800122f8  jb      short loc_18001230F
0x1800122fa  mov     rcx, [rcx+10h]
0x1800122fe  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180012305  mov     edx, 1Ch
0x18001230a  call    WPP_SF_
0x18001230f  sub     ebx, 110h
0x180012315  jz      loc_180012421
0x18001231b  cmp     ebx, 1
0x18001231e  jnz     loc_18001241D
0x180012324  lea     edx, [rbx-16h]; nIndex
0x180012327  mov     rcx, rbp; hWnd
0x18001232a  call    cs:__imp_GetWindowLongPtrW
0x180012330  mov     r14, rax
0x180012333  test    rax, rax
0x180012336  jz      loc_18001241D
0x18001233c  movzx   edx, di
0x18001233f  sub     edx, ebx
0x180012341  jz      short loc_18001235E
0x180012343  cmp     edx, ebx
0x180012345  jnz     loc_18001241D
0x18001234b  lea     edx, [rbx+1]; nResult
0x18001234e  mov     rcx, rbp; hDlg
0x180012351  call    cs:__imp_EndDialog
0x180012357  mov     eax, ebx
0x180012359  jmp     loc_18001248F
0x18001235e  mov     rdx, rbp; HWND
0x180012361  mov     rcx, r14; this
0x180012364  call    ?SaveDeviceSelection@CConfigGeneralPage@@AEAAKPEAUHWND__@@@Z; CConfigGeneralPage::SaveDeviceSelection(HWND__ *)
0x180012369  mov     ebx, eax
0x18001236b  mov     edi, 1
0x180012370  test    eax, eax
0x180012372  jz      loc_18001240F
0x180012378  mov     rcx, cs:WPP_GLOBAL_Control
0x18001237f  cmp     rcx, r12
0x180012382  jz      short loc_1800123A9
0x180012384  test    dword ptr [rcx+1Ch], 100h
0x18001238b  jz      short loc_1800123A9
0x18001238d  cmp     byte ptr [rcx+19h], 2
0x180012391  jb      short loc_1800123A9
0x180012393  mov     rcx, [rcx+10h]
0x180012397  lea     edx, [rdi+1Ch]
0x18001239a  mov     r9d, eax
0x18001239d  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x1800123a4  call    WPP_SF_d
0x1800123a9  cmp     ebx, 3EBh
0x1800123af  jz      loc_18001248C
0x1800123b5  mov     rax, [r14]
0x1800123b8  mov     edx, ebx
0x1800123ba  mov     rcx, r14
0x1800123bd  mov     rax, [rax+30h]
0x1800123c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123c6  test    eax, eax
0x1800123c8  jnz     short loc_1800123F0
0x1800123ca  cmp     ebx, 5
0x1800123cd  jz      short loc_1800123EB
0x1800123cf  cmp     ebx, 8
0x1800123d2  jz      short loc_1800123E4
0x1800123d4  mov     eax, 1234h
0x1800123d9  cmp     ebx, 7Ah ; 'z'
0x1800123dc  lea     ecx, [rax+2]
0x1800123df  cmovnz  eax, ecx
0x1800123e2  jmp     short loc_1800123F0
0x1800123e4  mov     eax, 1237h
0x1800123e9  jmp     short loc_1800123F0
0x1800123eb  mov     eax, 1235h
0x1800123f0  mov     rdx, [r14+8]
0x1800123f4  mov     r9d, eax
0x1800123f7  mov     r8d, 1230h
0x1800123fd  mov     [rsp+68h+var_48], 10h
0x180012405  mov     rcx, rbp
0x180012408  call    FaxMsgBox
0x18001240d  jmp     short loc_18001248C
0x18001240f  mov     rdx, rdi; nResult
0x180012412  mov     rcx, rbp; hDlg
0x180012415  call    cs:__imp_EndDialog
0x18001241b  jmp     short loc_18001248C
0x18001241d  xor     eax, eax
0x18001241f  jmp     short loc_18001248F
0x180012421  mov     r8, r14; dwNewLong
0x180012424  mov     edx, 0FFFFFFEBh; nIndex
0x180012429  mov     rcx, rbp; hWnd
0x18001242c  call    cs:__imp_SetWindowLongPtrW
0x180012432  mov     edx, 11E5h; nIDDlgItem
0x180012437  mov     rcx, rbp; hDlg
0x18001243a  call    cs:__imp_GetDlgItem
0x180012440  xor     esi, esi
0x180012442  mov     rbx, rax
0x180012445  lea     edi, [rsi+1]
0x180012448  cmp     [r14+28h], esi
0x18001244c  jbe     short loc_180012476
0x18001244e  mov     r9, [r14+20h]
0x180012452  xor     r8d, r8d; wParam
0x180012455  mov     ecx, esi
0x180012457  mov     edx, 143h; Msg
0x18001245c  lea     rax, [rcx+rcx*8]
0x180012460  mov     rcx, rbx; hWnd
0x180012463  mov     r9, [r9+rax*8+8]; lParam
0x180012468  call    cs:__imp_SendMessageW
0x18001246e  add     esi, edi
0x180012470  cmp     esi, [r14+28h]
0x180012474  jb      short loc_18001244E
0x180012476  mov     r9, [r14+38h]; lParam
0x18001247a  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x18001247e  mov     edx, 14Dh; Msg
0x180012483  mov     rcx, rbx; hWnd
0x180012486  call    cs:__imp_SendMessageW
0x18001248c  mov     rax, rdi
0x18001248f  add     rsp, 38h
0x180012493  pop     r14
0x180012495  pop     r12
0x180012497  pop     rdi
0x180012498  pop     rsi
0x180012499  pop     rbp
0x18001249a  pop     rbx
0x18001249b  retn
```
