# ProgressDialog::Create(HINSTANCE__ *,HWND__ *)

- ea: `0x180015870`
- end: `0x18001590b`
- name: `?Create@ProgressDialog@@UEAAHPEAUHINSTANCE__@@PEAUHWND__@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(LPARAM dwInitParam, HINSTANCE hInstance, HWND hWndParent)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005ebc`
- `0x18000c8c4`

## callees

- `0x180015870`
- `0x18001c0c4`
- `0x18001c888`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x1800158da`
- `KERNEL32!DeactivateActCtx` at `0x1800158da`
- `USER32!CreateDialogParamW` at `0x1800158c5`
- `USER32!CreateDialogParamW` at `0x1800158c5`
- `USER32!GetDlgItem` at `0x1800158ef`
- `USER32!GetDlgItem` at `0x1800158ef`

## pseudocode

```c
_BOOL8 __fastcall ProgressDialog::Create(LPARAM dwInitParam, HINSTANCE hInstance, HWND hWndParent)
{
  const WCHAR *v3; // rdi
  HWND DialogParamW; // rdi
  ULONG_PTR ulCookie; // [rsp+60h] [rbp+8h] BYREF

  v3 = (const WCHAR *)*(unsigned __int16 *)(dwInitParam + 8);
  ulCookie = 0;
  if ( (unsigned int)SHActivateContext(&ulCookie) )
  {
    if ( g_hActCtx != (HANDLE)-3LL )
      DelayLoadCC();
    DialogParamW = CreateDialogParamW(hInstance, v3, hWndParent, ProgressDialog::DlgProc, dwInitParam);
    if ( ulCookie )
      DeactivateActCtx(0, ulCookie);
  }
  else
  {
    DialogParamW = 0;
  }
  *(_QWORD *)(dwInitParam + 40) = DialogParamW;
  if ( DialogParamW )
    *(_QWORD *)(dwInitParam + 24) = GetDlgItem(DialogParamW, *(_DWORD *)(dwInitParam + 12));
  return *(_QWORD *)(dwInitParam + 40) != 0;
}

```

## disassembly

```asm
0x180015870  push    rbx
0x180015872  push    rbp
0x180015873  push    rsi
0x180015874  push    rdi
0x180015875  sub     rsp, 38h
0x180015879  movzx   edi, word ptr [rcx+8]
0x18001587d  mov     rbx, rcx
0x180015880  lea     rcx, [rsp+58h+ulCookie]
0x180015885  mov     [rsp+58h+ulCookie], 0
0x18001588e  mov     rsi, r8
0x180015891  mov     rbp, rdx
0x180015894  call    SHActivateContext
0x180015899  test    eax, eax
0x18001589b  jnz     short loc_1800158A1
0x18001589d  xor     edi, edi
0x18001589f  jmp     short loc_1800158E0
0x1800158a1  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFDh
0x1800158a9  jz      short loc_1800158B0
0x1800158ab  call    DelayLoadCC
0x1800158b0  lea     r9, ?DlgProc@ProgressDialog@@CA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1800158b7  mov     [rsp+58h+dwInitParam], rbx; dwInitParam
0x1800158bc  mov     r8, rsi; hWndParent
0x1800158bf  mov     rdx, rdi; lpTemplateName
0x1800158c2  mov     rcx, rbp; hInstance
0x1800158c5  call    cs:__imp_CreateDialogParamW
0x1800158cb  mov     rdx, [rsp+58h+ulCookie]; ulCookie
0x1800158d0  mov     rdi, rax
0x1800158d3  test    rdx, rdx
0x1800158d6  jz      short loc_1800158E0
0x1800158d8  xor     ecx, ecx; dwFlags
0x1800158da  call    cs:__imp_DeactivateActCtx
0x1800158e0  mov     [rbx+28h], rdi
0x1800158e4  test    rdi, rdi
0x1800158e7  jz      short loc_1800158F9
0x1800158e9  mov     edx, [rbx+0Ch]; nIDDlgItem
0x1800158ec  mov     rcx, rdi; hDlg
0x1800158ef  call    cs:__imp_GetDlgItem
0x1800158f5  mov     [rbx+18h], rax
0x1800158f9  xor     eax, eax
0x1800158fb  cmp     [rbx+28h], rax
0x1800158ff  setnz   al
0x180015902  add     rsp, 38h
0x180015906  pop     rdi
0x180015907  pop     rsi
0x180015908  pop     rbp
0x180015909  pop     rbx
0x18001590a  retn
```
