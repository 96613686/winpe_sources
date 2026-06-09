# GetBoldWindowFont

- ea: `0x18002ae98`
- end: `0x18002b051`
- name: `GetBoldWindowFont`
- size: `441`
- prototype: `int __fastcall(HWND hWnd, int, HFONT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000f9b0`
- `0x18001f380`

## callees

- `0x18002ae98`
- `0x18003c4ec`
- `0x18003ce6c`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `msvcrt!wcstoul` at `0x18002afdb`
- `msvcrt!wcstoul` at `0x18002afdb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002afb5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002afb5`
- `GDI32!CreateFontIndirectW` at `0x18002b010`
- `GDI32!CreateFontIndirectW` at `0x18002b010`
- `GDI32!GetObjectW` at `0x18002af21`
- `GDI32!GetObjectW` at `0x18002af21`
- `GDI32!GetStockObject` at `0x18002af08`
- `GDI32!GetStockObject` at `0x18002af08`
- `GDI32!GetDeviceCaps` at `0x18002afeb`
- `GDI32!GetDeviceCaps` at `0x18002afeb`
- `USER32!GetDC` at `0x18002af3a`
- `USER32!GetDC` at `0x18002af3a`
- `USER32!ReleaseDC` at `0x18002b020`
- `USER32!ReleaseDC` at `0x18002b020`
- `USER32!SendMessageW` at `0x18002aefa`
- `USER32!SendMessageW` at `0x18002aefa`

## pseudocode

```c
int __fastcall GetBoldWindowFont(HWND hWnd, int a2, HFONT *a3)
{
  HDC DC; // rax
  HDC v7; // rbx
  const wchar_t *StringPcch; // rdi
  const wchar_t *v9; // r14
  unsigned int v10; // esi
  LOGFONTW pv; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t String[264]; // [rsp+90h] [rbp-70h] BYREF

  memset_0(&pv, 0, sizeof(pv));
  *a3 = 0;
  DC = (HDC)SendMessageW(hWnd, 0x31u, 0, 0);
  if ( DC || (DC = (HDC)GetStockObject(13)) != 0 )
  {
    LODWORD(DC) = GetObjectW(DC, 92, &pv);
    if ( (_DWORD)DC )
    {
      pv.lfWeight = 700;
      DC = GetDC(hWnd);
      v7 = DC;
      if ( DC )
      {
        if ( a2 )
        {
          StringPcch = (const wchar_t *)PszLoadStringPcch(g_hinstDll);
          v9 = (const wchar_t *)PszLoadStringPcch(g_hinstDll);
          if ( StringPcch )
            StringCchCopyWrapW(pv.lfFaceName, 0x20u, StringPcch);
          v10 = 12;
          lstrlenW(StringPcch);
          if ( v9 )
          {
            StringCchCopyWrapW(String, 0x104u, v9);
            v10 = wcstoul(String, 0, 10);
          }
          pv.lfHeight = (int)(v10 * GetDeviceCaps(v7, 90)) / -72;
        }
        *a3 = CreateFontIndirectW(&pv);
        LODWORD(DC) = ReleaseDC(hWnd, v7);
      }
    }
  }
  return (int)DC;
}

```

## disassembly

```asm
0x18002ae98  mov     [rsp-8+arg_8], rbx
0x18002ae9d  mov     [rsp-8+arg_18], rsi
0x18002aea2  push    rbp
0x18002aea3  push    rdi
0x18002aea4  push    r12
0x18002aea6  push    r14
0x18002aea8  push    r15
0x18002aeaa  lea     rbp, [rsp-1B0h]
0x18002aeb2  sub     rsp, 2B0h
0x18002aeb9  mov     rax, cs:__security_cookie
0x18002aec0  xor     rax, rsp
0x18002aec3  mov     [rbp+1D0h+var_30], rax
0x18002aeca  mov     r12, r8
0x18002aecd  mov     edi, edx
0x18002aecf  mov     r15, rcx
0x18002aed2  mov     ebx, 5Ch ; '\'
0x18002aed7  mov     r8d, ebx; Size
0x18002aeda  lea     rcx, [rsp+2D0h+pv]; void *
0x18002aedf  xor     edx, edx; Val
0x18002aee1  call    memset_0
0x18002aee6  xor     r9d, r9d; lParam
0x18002aee9  mov     qword ptr [r12], 0
0x18002aef1  xor     r8d, r8d; wParam
0x18002aef4  lea     edx, [rbx-2Bh]; Msg
0x18002aef7  mov     rcx, r15; hWnd
0x18002aefa  call    cs:__imp_SendMessageW
0x18002af00  test    rax, rax
0x18002af03  jnz     short loc_18002AF17
0x18002af05  lea     ecx, [rbx-4Fh]; i
0x18002af08  call    cs:__imp_GetStockObject
0x18002af0e  test    rax, rax
0x18002af11  jz      loc_18002B026
0x18002af17  lea     r8, [rsp+2D0h+pv]; pv
0x18002af1c  mov     edx, ebx; c
0x18002af1e  mov     rcx, rax; h
0x18002af21  call    cs:__imp_GetObjectW
0x18002af27  test    eax, eax
0x18002af29  jz      loc_18002B026
0x18002af2f  mov     rcx, r15; hWnd
0x18002af32  mov     [rsp+2D0h+var_290], 2BCh
0x18002af3a  call    cs:__imp_GetDC
0x18002af40  mov     rbx, rax
0x18002af43  test    rax, rax
0x18002af46  jz      loc_18002B026
0x18002af4c  test    edi, edi
0x18002af4e  jz      loc_18002B00B
0x18002af54  mov     rcx, cs:g_hinstDll; hModule
0x18002af5b  lea     r8, [rsp+2D0h+var_2B0]
0x18002af60  mov     edx, 5FAh
0x18002af65  mov     [rsp+2D0h+var_2B0], 0
0x18002af6d  call    PszLoadStringPcch
0x18002af72  mov     rcx, cs:g_hinstDll; hModule
0x18002af79  lea     r8, [rsp+2D0h+var_2B0]
0x18002af7e  mov     edx, 5FBh
0x18002af83  mov     [rsp+2D0h+var_2B0], 0
0x18002af8b  mov     rdi, rax
0x18002af8e  call    PszLoadStringPcch
0x18002af93  mov     r14, rax
0x18002af96  test    rdi, rdi
0x18002af99  jz      short loc_18002AFAD
0x18002af9b  mov     r8, rdi
0x18002af9e  lea     rcx, [rsp+2D0h+var_284]
0x18002afa3  mov     edx, 20h ; ' '
0x18002afa8  call    StringCchCopyWrapW
0x18002afad  mov     rcx, rdi; lpString
0x18002afb0  mov     esi, 0Ch
0x18002afb5  call    cs:__imp_lstrlenW
0x18002afbb  test    r14, r14
0x18002afbe  jz      short loc_18002AFE3
0x18002afc0  mov     r8, r14
0x18002afc3  lea     rcx, [rbp+1D0h+String]
0x18002afc7  mov     edx, 104h
0x18002afcc  call    StringCchCopyWrapW
0x18002afd1  xor     edx, edx; EndPtr
0x18002afd3  lea     r8d, [rsi-2]; Radix
0x18002afd7  lea     rcx, [rbp+1D0h+String]; String
0x18002afdb  call    cs:__imp_wcstoul
0x18002afe1  mov     esi, eax
0x18002afe3  mov     edx, 5Ah ; 'Z'; index
0x18002afe8  mov     rcx, rbx; hdc
0x18002afeb  call    cs:__imp_GetDeviceCaps
0x18002aff1  mov     ecx, eax
0x18002aff3  mov     eax, 0C71C71C7h
0x18002aff8  imul    ecx, esi
0x18002affb  imul    ecx
0x18002affd  sar     edx, 4
0x18002b000  mov     eax, edx
0x18002b002  shr     eax, 1Fh
0x18002b005  add     edx, eax
0x18002b007  mov     [rsp+2D0h+pv], edx
0x18002b00b  lea     rcx, [rsp+2D0h+pv]; lplf
0x18002b010  call    cs:__imp_CreateFontIndirectW
0x18002b016  mov     rdx, rbx; hDC
0x18002b019  mov     rcx, r15; hWnd
0x18002b01c  mov     [r12], rax
0x18002b020  call    cs:__imp_ReleaseDC
0x18002b026  mov     rcx, [rbp+1D0h+var_30]
0x18002b02d  xor     rcx, rsp; StackCookie
0x18002b030  call    __security_check_cookie
0x18002b035  lea     r11, [rsp+2D0h+var_20]
0x18002b03d  mov     rbx, [r11+38h]
0x18002b041  mov     rsi, [r11+48h]
0x18002b045  mov     rsp, r11
0x18002b048  pop     r15
0x18002b04a  pop     r14
0x18002b04c  pop     r12
0x18002b04e  pop     rdi
0x18002b04f  pop     rbp
0x18002b050  retn
```
