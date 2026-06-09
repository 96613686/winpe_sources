# VolumePropPage::UpdateStatusIndicators(HWND__ *)

- ea: `0x180019a54`
- end: `0x180019ba8`
- name: `?UpdateStatusIndicators@VolumePropPage@@AEAAJPEAUHWND__@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(VolumePropPage *__hidden this, HWND)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180018c30`
- `0x180019970`

## callees

- `0x180016410`
- `0x180018ff4`
- `0x180019a54`
- `0x180019d24`
- `0x180019ee0`
- `0x18001f010`

## import_xrefs

- `USER32!SetWindowTextW` at `0x180019b65`
- `USER32!SetWindowTextW` at `0x180019b65`
- `USER32!SendMessageW` at `0x180019b2f`
- `USER32!SendMessageW` at `0x180019b2f`
- `USER32!GetDlgItem` at `0x180019b59`
- `USER32!GetDlgItem` at `0x180019b59`

## pseudocode

```c
__int64 __fastcall VolumePropPage::UpdateStatusIndicators(VolumePropPage *this, HWND a2)
{
  int v4; // ebp
  unsigned int v5; // esi
  struct IDiskQuotaControl *v6; // rdi
  int v7; // ebx
  int v8; // eax
  int v9; // eax
  LPARAM v10; // r9
  const WCHAR *v11; // rbx
  HWND DlgItem; // rax
  _BYTE v14[8]; // [rsp+20h] [rbp-38h] BYREF
  const WCHAR **v15; // [rsp+28h] [rbp-30h]
  struct IDiskQuotaControl *v16; // [rsp+60h] [rbp+8h] BYREF

  v16 = 0;
  v4 = 40526;
  v5 = 3;
  if ( (int)DiskQuotaPropPage::GetQuotaController(this, &v16) >= 0 )
  {
    v6 = v16;
    v7 = ((__int64 (__fastcall *)(struct IDiskQuotaControl *, char *))v16->lpVtbl->GetDefaultQuotaThresholdText)(
           v16,
           (char *)this + 96);
    ((void (__fastcall *)(struct IDiskQuotaControl *))v6->lpVtbl->GetQuotaState)(v6);
    if ( v7 >= 0 )
    {
      if ( (*((_DWORD *)this + 24) & 0x200) != 0 )
      {
        v4 = 40530;
      }
      else
      {
        v8 = *((_DWORD *)this + 24) & 3;
        if ( v8 )
        {
          if ( (unsigned int)(v8 - 1) <= 1 )
            v4 = 40528;
        }
        else
        {
          v4 = 40527;
        }
      }
    }
  }
  if ( v4 != *((_DWORD *)this + 34) )
  {
    v9 = *((_DWORD *)this + 24);
    if ( (v9 & 0x200) != 0 )
    {
      v10 = 0;
    }
    else
    {
      if ( (v9 & 3) == 0 )
        v5 = 2;
      v10 = v5 | (unsigned __int64)(v5 << 16);
    }
    SendMessageW(*((HWND *)this + 21), 0x465u, 1u, v10);
    CString::CString((CString *)v14, g_hInstDll, v4);
    v11 = *v15;
    DlgItem = GetDlgItem(a2, 1001);
    SetWindowTextW(DlgItem, v11);
    *((_DWORD *)this + 34) = v4;
    VolumePropPage::InitializeControls(this, a2);
    CString::~CString((CString *)v14);
  }
  return 0;
}

```

## disassembly

```asm
0x180019a54  mov     rax, rsp
0x180019a57  mov     [rax+10h], rbx
0x180019a5b  mov     [rax+18h], rbp
0x180019a5f  push    rsi
0x180019a60  push    rdi
0x180019a61  push    r12
0x180019a63  push    r14
0x180019a65  push    r15
0x180019a67  sub     rsp, 30h
0x180019a6b  mov     r12, rdx
0x180019a6e  mov     qword ptr [rax+8], 0
0x180019a76  lea     rdx, [rax+8]; struct IDiskQuotaControl **
0x180019a7a  mov     r14, rcx
0x180019a7d  mov     ebp, 9E4Eh
0x180019a82  call    ?GetQuotaController@DiskQuotaPropPage@@IEAAJPEAPEAUIDiskQuotaControl@@@Z; DiskQuotaPropPage::GetQuotaController(IDiskQuotaControl * *)
0x180019a87  mov     esi, 3
0x180019a8c  test    eax, eax
0x180019a8e  js      short loc_180019AE8
0x180019a90  mov     rdi, [rsp+58h+arg_0]
0x180019a95  lea     rdx, [r14+60h]
0x180019a99  mov     rcx, rdi
0x180019a9c  mov     rax, [rdi]
0x180019a9f  mov     rax, [rax+38h]
0x180019aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019aa8  mov     rdx, [rdi]
0x180019aab  mov     ebx, eax
0x180019aad  mov     rcx, rdi
0x180019ab0  mov     rax, [rdx+10h]
0x180019ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ab9  test    ebx, ebx
0x180019abb  js      short loc_180019AE8
0x180019abd  mov     eax, [r14+60h]
0x180019ac1  bt      eax, 9
0x180019ac5  jnb     short loc_180019ACE
0x180019ac7  mov     ebp, 9E52h
0x180019acc  jmp     short loc_180019AE8
0x180019ace  and     eax, esi
0x180019ad0  jz      short loc_180019AE3
0x180019ad2  sub     eax, 1
0x180019ad5  jz      short loc_180019ADC
0x180019ad7  cmp     eax, 1
0x180019ada  jnz     short loc_180019AE8
0x180019adc  mov     ebp, 9E50h
0x180019ae1  jmp     short loc_180019AE8
0x180019ae3  mov     ebp, 9E4Fh
0x180019ae8  cmp     ebp, [r14+88h]
0x180019aef  jz      loc_180019B87
0x180019af5  mov     eax, [r14+60h]
0x180019af9  lea     rcx, [r14+0A8h]
0x180019b00  bt      eax, 9
0x180019b04  jb      loc_180019BA0
0x180019b0a  and     eax, esi
0x180019b0c  test    al, al
0x180019b0e  jnz     short loc_180019B15
0x180019b10  mov     esi, 2
0x180019b15  mov     r9d, esi
0x180019b18  mov     eax, esi
0x180019b1a  shl     r9d, 10h
0x180019b1e  or      r9, rax; lParam
0x180019b21  mov     rcx, [rcx]; hWnd
0x180019b24  mov     r8d, 1; wParam
0x180019b2a  mov     edx, 465h; Msg
0x180019b2f  call    cs:__imp_SendMessageW
0x180019b35  mov     rdx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180019b3c  lea     rcx, [rsp+58h+var_38]; this
0x180019b41  mov     r8d, ebp; int
0x180019b44  call    ??0CString@@QEAA@PEAUHINSTANCE__@@HZZ; CString::CString(HINSTANCE__ *,int,...)
0x180019b49  mov     rax, [rsp+58h+var_30]
0x180019b4e  mov     edx, 3E9h; nIDDlgItem
0x180019b53  mov     rcx, r12; hDlg
0x180019b56  mov     rbx, [rax]
0x180019b59  call    cs:__imp_GetDlgItem
0x180019b5f  mov     rcx, rax; hWnd
0x180019b62  mov     rdx, rbx; lpString
0x180019b65  call    cs:__imp_SetWindowTextW
0x180019b6b  mov     rdx, r12; HWND
0x180019b6e  mov     [r14+88h], ebp
0x180019b75  mov     rcx, r14; this
0x180019b78  call    ?InitializeControls@VolumePropPage@@AEAAJPEAUHWND__@@@Z; VolumePropPage::InitializeControls(HWND__ *)
0x180019b7d  lea     rcx, [rsp+58h+var_38]; this
0x180019b82  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180019b87  mov     rbx, [rsp+58h+arg_8]
0x180019b8c  xor     eax, eax
0x180019b8e  mov     rbp, [rsp+58h+arg_10]
0x180019b93  add     rsp, 30h
0x180019b97  pop     r15
0x180019b99  pop     r14
0x180019b9b  pop     r12
0x180019b9d  pop     rdi
0x180019b9e  pop     rsi
0x180019b9f  retn
0x180019ba0  xor     r9d, r9d
0x180019ba3  jmp     loc_180019B21
```
