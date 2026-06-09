# CFtpDialogTemplate::_InitIcon(HWND__ *,CFtpFolder *,CFtpPidlList *)

- ea: `0x1800108e4`
- end: `0x1800109d6`
- name: `?_InitIcon@CFtpDialogTemplate@@AEAAJPEAUHWND__@@PEAVCFtpFolder@@PEAVCFtpPidlList@@@Z`
- size: `242`
- prototype: `int(CFtpDialogTemplate *__hidden this, HWND, struct CFtpFolder *, struct CFtpPidlList *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180010390`

## callees

- `0x180002240`
- `0x180002b60`
- `0x1800108e4`
- `0x18001bd78`
- `0x18001c5dc`
- `0x1800269f4`

## import_xrefs

- `SHELL32!ExtractIconW` at `0x180010948`
- `SHELL32!ExtractIconW` at `0x180010948`
- `USER32!SendMessageW` at `0x1800109a5`
- `USER32!SendMessageW` at `0x1800109a5`
- `USER32!DestroyIcon` at `0x1800109b3`
- `USER32!DestroyIcon` at `0x1800109b3`

## string_xrefs

- `0x18001093b`: `shell32.dll`

## pseudocode

```c
__int64 __fastcall CFtpDialogTemplate::_InitIcon(
        CFtpDialogTemplate *this,
        HWND a2,
        struct CFtpFolder *a3,
        struct CFtpPidlList *a4)
{
  const struct _ITEMIDLIST *Ptr; // rax
  struct _DPA *v8; // rcx
  __int64 result; // rax
  HICON v10; // rax
  SHFILEINFOW wParam; // [rsp+20h] [rbp-2E8h] BYREF

  memset_0(&wParam, 0, sizeof(wParam));
  if ( a4
    && (Ptr = (const struct _ITEMIDLIST *)*((_QWORD *)a4 + 2),
        v8 = *(struct _DPA **)((char *)&Ptr[5].mkid.cb + 1),
        *(_DWORD *)v8) )
  {
    if ( *(_DWORD *)v8 != 1 )
    {
      wParam.hIcon = ExtractIconW(g_hinst, L"shell32.dll", 0xFFFFFF7B);
      result = wParam.hIcon == 0 ? 0x8007000E : 0;
      goto LABEL_10;
    }
    if ( Ptr )
      Ptr = (const struct _ITEMIDLIST *)DPA_GetPtr(v8, 0);
  }
  else
  {
    Ptr = FtpID_GetLastIDReferense((const struct _ITEMIDLIST *)(*((_QWORD *)a3 + 6) + *((int *)a3 + 16)));
  }
  result = FtpPidl_GetFileInfo(Ptr, &wParam, 0x100u);
LABEL_10:
  if ( (int)result >= 0 )
  {
    v10 = (HICON)SendMessageW(a2, 0x170u, (WPARAM)wParam.hIcon, 0);
    if ( v10 )
      DestroyIcon(v10);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800108e4  push    rbx
0x1800108e6  push    rsi
0x1800108e7  push    rdi
0x1800108e8  sub     rsp, 2F0h
0x1800108ef  mov     rax, cs:__security_cookie
0x1800108f6  xor     rax, rsp
0x1800108f9  mov     [rsp+308h+var_28], rax
0x180010901  mov     rdi, r8
0x180010904  lea     rcx, [rsp+308h+wParam]; void *
0x180010909  mov     rsi, rdx
0x18001090c  mov     r8d, 2B8h; Size
0x180010912  xor     edx, edx; Val
0x180010914  mov     rbx, r9
0x180010917  call    memset_0
0x18001091c  test    rbx, rbx
0x18001091f  jz      short loc_180010971
0x180010921  mov     rax, [rbx+10h]
0x180010925  mov     rcx, [rax+10h]; hdpa
0x180010929  mov     edx, [rcx]
0x18001092b  test    edx, edx
0x18001092d  jz      short loc_180010971
0x18001092f  cmp     edx, 1
0x180010932  jz      short loc_180010961
0x180010934  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInst
0x18001093b  lea     rdx, pszExeFileName; "shell32.dll"
0x180010942  mov     r8d, 0FFFFFF7Bh; nIconIndex
0x180010948  call    cs:__imp_ExtractIconW
0x18001094e  mov     [rsp+308h+wParam.hIcon], rax
0x180010953  neg     rax
0x180010956  sbb     eax, eax
0x180010958  not     eax
0x18001095a  and     eax, 8007000Eh
0x18001095f  jmp     short loc_180010991
0x180010961  test    rax, rax
0x180010964  jz      short loc_18001096F
0x180010966  xor     edx, edx; i
0x180010968  call    DPA_GetPtr
0x18001096d  jmp     short loc_18001097E
0x18001096f  jmp     short loc_18001097E
0x180010971  movsxd  rcx, dword ptr [rdi+40h]
0x180010975  add     rcx, [rdi+30h]; struct _ITEMIDLIST *
0x180010979  call    ?FtpID_GetLastIDReferense@@YAPEFBU_ITEMIDLIST@@PEFBU1@@Z; FtpID_GetLastIDReferense(_ITEMIDLIST const *)
0x18001097e  mov     r8d, 100h; unsigned int
0x180010984  lea     rdx, [rsp+308h+wParam]; psfi
0x180010989  mov     rcx, rax; struct _ITEMIDLIST *
0x18001098c  call    ?FtpPidl_GetFileInfo@@YAJPEFBU_ITEMIDLIST@@PEAU_SHFILEINFOW@@K@Z; FtpPidl_GetFileInfo(_ITEMIDLIST const *,_SHFILEINFOW *,ulong)
0x180010991  test    eax, eax
0x180010993  js      short loc_1800109BB
0x180010995  mov     r8, [rsp+308h+wParam.hIcon]; wParam
0x18001099a  xor     r9d, r9d; lParam
0x18001099d  mov     edx, 170h; Msg
0x1800109a2  mov     rcx, rsi; hWnd
0x1800109a5  call    cs:__imp_SendMessageW
0x1800109ab  test    rax, rax
0x1800109ae  jz      short loc_1800109B9
0x1800109b0  mov     rcx, rax; hIcon
0x1800109b3  call    cs:__imp_DestroyIcon
0x1800109b9  xor     eax, eax
0x1800109bb  mov     rcx, [rsp+308h+var_28]
0x1800109c3  xor     rcx, rsp; StackCookie
0x1800109c6  call    __security_check_cookie
0x1800109cb  add     rsp, 2F0h
0x1800109d2  pop     rdi
0x1800109d3  pop     rsi
0x1800109d4  pop     rbx
0x1800109d5  retn
```
