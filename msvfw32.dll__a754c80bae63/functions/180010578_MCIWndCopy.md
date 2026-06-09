# MCIWndCopy

- ea: `0x180010578`
- end: `0x180010687`
- name: `MCIWndCopy`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180010194`

## callees

- `0x18000f704`
- `0x18000f8ec`
- `0x18000fb08`
- `0x18000fe2c`
- `0x180010578`
- `0x18001597c`

## import_xrefs

- `GDI32!DeleteObject` at `0x180010658`
- `GDI32!DeleteObject` at `0x180010658`
- `USER32!SendMessageW` at `0x180010600`
- `USER32!SendMessageW` at `0x180010600`
- `USER32!SetClipboardData` at `0x1800105ce`
- `USER32!SetClipboardData` at `0x1800105e1`
- `USER32!SetClipboardData` at `0x18001063c`
- `USER32!SetClipboardData` at `0x18001064f`
- `USER32!SetClipboardData` at `0x18001066b`
- `USER32!SetClipboardData` at `0x1800105ce`
- `USER32!SetClipboardData` at `0x1800105e1`
- `USER32!SetClipboardData` at `0x18001063c`
- `USER32!SetClipboardData` at `0x18001064f`
- `USER32!SetClipboardData` at `0x18001066b`
- `USER32!EmptyClipboard` at `0x1800105bb`
- `USER32!EmptyClipboard` at `0x1800105bb`
- `USER32!CloseClipboard` at `0x180010671`
- `USER32!CloseClipboard` at `0x180010671`
- `USER32!OpenClipboard` at `0x1800105b5`
- `USER32!OpenClipboard` at `0x1800105b5`
- `USER32!RegisterClipboardFormatW` at `0x180010591`
- `USER32!RegisterClipboardFormatW` at `0x1800105a0`
- `USER32!RegisterClipboardFormatW` at `0x180010591`
- `USER32!RegisterClipboardFormatW` at `0x1800105a0`

## string_xrefs

- `0x180010597`: `OwnerLink`

## pseudocode

```c
UINT __fastcall MCIWndCopy(__int64 a1)
{
  UINT v2; // edi
  UINT result; // eax
  UINT v4; // esi
  void *MPlayerData; // rax
  void *v6; // rax
  HBITMAP v7; // rsi
  HPALETTE v8; // rax
  HPALETTE v9; // rax
  HPALETTE v10; // rbx
  void *v11; // rdi
  void *v12; // rax

  v2 = RegisterClipboardFormatW(aszNative);
  result = RegisterClipboardFormatW(aszOwnerLink);
  v4 = result;
  if ( *(_DWORD *)(a1 + 20) )
  {
    OpenClipboard(*(HWND *)a1);
    EmptyClipboard();
    MPlayerData = (void *)GetMPlayerData(a1);
    SetClipboardData(v2, MPlayerData);
    v6 = (void *)GetMPlayerData(a1);
    SetClipboardData(v4, v6);
    v7 = BitmapMCI(a1);
    v8 = (HPALETTE)SendMessageW(*(HWND *)a1, 0x47Eu, 0, 0);
    v9 = (HPALETTE)CopyPalette(v8);
    v10 = v9;
    if ( v7 )
    {
      v11 = (void *)DibFromBitmap(v7, v9);
      v12 = (void *)PictureFromDib(v11, v10);
      if ( v12 )
        SetClipboardData(3u, v12);
      if ( v11 )
        SetClipboardData(8u, v11);
      DeleteObject(v7);
    }
    if ( v10 )
      SetClipboardData(9u, v10);
    return CloseClipboard();
  }
  return result;
}

```

## disassembly

```asm
0x180010578  mov     [rsp+arg_0], rbx
0x18001057d  mov     [rsp+arg_8], rsi
0x180010582  push    rdi
0x180010583  sub     rsp, 20h
0x180010587  mov     rbx, rcx
0x18001058a  lea     rcx, aszNative; "Native"
0x180010591  call    cs:__imp_RegisterClipboardFormatW
0x180010597  lea     rcx, aszOwnerLink; "OwnerLink"
0x18001059e  mov     edi, eax
0x1800105a0  call    cs:__imp_RegisterClipboardFormatW
0x1800105a6  cmp     dword ptr [rbx+14h], 0
0x1800105aa  mov     esi, eax
0x1800105ac  jz      loc_180010677
0x1800105b2  mov     rcx, [rbx]; hWndNewOwner
0x1800105b5  call    cs:__imp_OpenClipboard
0x1800105bb  call    cs:__imp_EmptyClipboard
0x1800105c1  mov     rcx, rbx
0x1800105c4  call    GetMPlayerData
0x1800105c9  mov     rdx, rax; hMem
0x1800105cc  mov     ecx, edi; uFormat
0x1800105ce  call    cs:__imp_SetClipboardData
0x1800105d4  mov     rcx, rbx
0x1800105d7  call    GetMPlayerData
0x1800105dc  mov     rdx, rax; hMem
0x1800105df  mov     ecx, esi; uFormat
0x1800105e1  call    cs:__imp_SetClipboardData
0x1800105e7  mov     rcx, rbx
0x1800105ea  call    BitmapMCI
0x1800105ef  mov     rcx, [rbx]; hWnd
0x1800105f2  xor     r9d, r9d; lParam
0x1800105f5  xor     r8d, r8d; wParam
0x1800105f8  mov     edx, 47Eh; Msg
0x1800105fd  mov     rsi, rax
0x180010600  call    cs:__imp_SendMessageW
0x180010606  mov     rcx, rax; hpal
0x180010609  call    CopyPalette
0x18001060e  mov     rbx, rax
0x180010611  test    rsi, rsi
0x180010614  jz      short loc_18001065E
0x180010616  mov     rdx, rax; hPal
0x180010619  mov     rcx, rsi; hbm
0x18001061c  call    DibFromBitmap
0x180010621  mov     rdx, rbx
0x180010624  mov     rcx, rax
0x180010627  mov     rdi, rax
0x18001062a  call    PictureFromDib
0x18001062f  test    rax, rax
0x180010632  jz      short loc_180010642
0x180010634  mov     rdx, rax; hMem
0x180010637  mov     ecx, 3; uFormat
0x18001063c  call    cs:__imp_SetClipboardData
0x180010642  test    rdi, rdi
0x180010645  jz      short loc_180010655
0x180010647  mov     rdx, rdi; hMem
0x18001064a  mov     ecx, 8; uFormat
0x18001064f  call    cs:__imp_SetClipboardData
0x180010655  mov     rcx, rsi; ho
0x180010658  call    cs:__imp_DeleteObject
0x18001065e  test    rbx, rbx
0x180010661  jz      short loc_180010671
0x180010663  mov     rdx, rbx; hMem
0x180010666  mov     ecx, 9; uFormat
0x18001066b  call    cs:__imp_SetClipboardData
0x180010671  call    cs:__imp_CloseClipboard
0x180010677  mov     rbx, [rsp+28h+arg_0]
0x18001067c  mov     rsi, [rsp+28h+arg_8]
0x180010681  add     rsp, 20h
0x180010685  pop     rdi
0x180010686  retn
```
