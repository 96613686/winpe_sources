# CConfigGeneralPage::DisplayAdditionalDeviceSettings(HWND__ *)

- ea: `0x18001067c`
- end: `0x180010742`
- name: `?DisplayAdditionalDeviceSettings@CConfigGeneralPage@@AEAAKPEAUHWND__@@@Z`
- size: `198`
- prototype: `unsigned int(CConfigGeneralPage *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180011040`

## callees

- `0x18000e314`
- `0x18001067c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010706`
- `KERNEL32!GetLastError` at `0x180010706`
- `USER32!DialogBoxParamW` at `0x1800106fb`
- `USER32!DialogBoxParamW` at `0x1800106fb`

## pseudocode

```c
__int64 __fastcall CConfigGeneralPage::DisplayAdditionalDeviceSettings(CConfigGeneralPage *this, HWND a2)
{
  HINSTANCE v2; // r10
  DWORD LastError; // ebx
  INT_PTR v4; // rax
  LPARAM dwInitParam[3]; // [rsp+30h] [rbp-50h] BYREF
  int v7; // [rsp+48h] [rbp-38h]
  __int64 v8; // [rsp+50h] [rbp-30h]
  int v9; // [rsp+58h] [rbp-28h]
  char *v10; // [rsp+60h] [rbp-20h]
  __int64 v11; // [rsp+68h] [rbp-18h]
  LPVOID lpMem; // [rsp+70h] [rbp-10h]
  int v13; // [rsp+78h] [rbp-8h]
  int v14; // [rsp+7Ch] [rbp-4h]

  v2 = (HINSTANCE)*((_QWORD *)this + 1);
  v11 = *((_QWORD *)this + 15);
  LastError = 0;
  v8 = *((_QWORD *)this + 4);
  v9 = *((_DWORD *)this + 10);
  v10 = (char *)this + 48;
  v14 = *((_DWORD *)this + 32);
  dwInitParam[2] = (LPARAM)a2;
  dwInitParam[1] = (LPARAM)v2;
  v7 = 4602;
  dwInitParam[0] = (LPARAM)&CDeviceSettingsDialog::`vftable';
  lpMem = 0;
  v13 = 0;
  v4 = DialogBoxParamW(v2, (LPCWSTR)0x11FA, a2, CDialogUI::DlgProc, (LPARAM)dwInitParam);
  if ( v4 > 0 )
  {
    if ( (_DWORD)v4 == 2 )
      LastError = 995;
  }
  else
  {
    LastError = GetLastError();
  }
  dwInitParam[0] = (LPARAM)&CDeviceSettingsDialog::`vftable';
  ReleasePrinterNames(lpMem);
  return LastError;
}

```

## disassembly

```asm
0x18001067c  mov     [rsp-8+arg_0], rbx
0x180010681  mov     [rsp-8+arg_8], rdi
0x180010686  push    rbp
0x180010687  mov     rbp, rsp
0x18001068a  sub     rsp, 80h
0x180010691  mov     rax, [rcx+78h]
0x180010695  lea     rdi, ??_7CDeviceSettingsDialog@@6B@; const CDeviceSettingsDialog::`vftable'
0x18001069c  mov     r10, [rcx+8]
0x1800106a0  lea     r9, ?DlgProc@CDialogUI@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1800106a7  mov     [rbp+var_18], rax
0x1800106ab  mov     r11d, 11FAh
0x1800106b1  mov     rax, [rcx+20h]
0x1800106b5  xor     ebx, ebx
0x1800106b7  mov     [rbp+var_30], rax
0x1800106bb  mov     r8, rdx; hWndParent
0x1800106be  mov     eax, [rcx+28h]
0x1800106c1  mov     [rbp+var_28], eax
0x1800106c4  lea     rax, [rcx+30h]
0x1800106c8  mov     [rbp+var_20], rax
0x1800106cc  mov     eax, [rcx+80h]
0x1800106d2  mov     rcx, r10; hInstance
0x1800106d5  mov     [rbp+var_4], eax
0x1800106d8  lea     rax, [rbp+var_50]
0x1800106dc  mov     [rbp+var_40], rdx
0x1800106e0  mov     edx, r11d; lpTemplateName
0x1800106e3  mov     [rsp+80h+dwInitParam], rax; dwInitParam
0x1800106e8  mov     [rbp+var_48], r10
0x1800106ec  mov     [rbp+var_38], r11d
0x1800106f0  mov     [rbp+var_50], rdi
0x1800106f4  mov     [rbp+lpMem], rbx
0x1800106f8  mov     [rbp+var_8], ebx
0x1800106fb  call    cs:__imp_DialogBoxParamW
0x180010701  test    rax, rax
0x180010704  jg      short loc_180010710
0x180010706  call    cs:__imp_GetLastError
0x18001070c  mov     ebx, eax
0x18001070e  jmp     short loc_18001071B
0x180010710  cmp     eax, 2
0x180010713  mov     ecx, 3E3h
0x180010718  cmovz   ebx, ecx
0x18001071b  mov     edx, [rbp+var_8]
0x18001071e  mov     rcx, [rbp+lpMem]; lpMem
0x180010722  mov     [rbp+var_50], rdi
0x180010726  call    ReleasePrinterNames
0x18001072b  lea     r11, [rsp+80h+var_s0]
0x180010733  mov     eax, ebx
0x180010735  mov     rbx, [r11+10h]
0x180010739  mov     rdi, [r11+18h]
0x18001073d  mov     rsp, r11
0x180010740  pop     rbp
0x180010741  retn
```
