# PackWiz_CreateWizard(HWND__ *,_packageInfo *)

- ea: `0x18000bda0`
- end: `0x18000bed5`
- name: `?PackWiz_CreateWizard@@YAHPEAUHWND__@@PEAU_packageInfo@@@Z`
- size: `309`
- prototype: `__int64 __fastcall(HWND, struct _packageInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800050b0`

## callees

- `0x18000bda0`
- `0x18000c82c`
- `0x18000ca58`
- `0x18000cbbe`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x18000beb5`
- `KERNEL32!DeactivateActCtx` at `0x18000beb5`

## pseudocode

```c
__int64 __fastcall PackWiz_CreateWizard(HWND a1, struct _packageInfo *a2)
{
  HINSTANCE v4; // rbx
  unsigned int v5; // ebx
  PROPSHEETHEADERW_V2 v7; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v8[13]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v9[13]; // [rsp+E8h] [rbp-18h] BYREF
  ULONG_PTR ulCookie; // [rsp+170h] [rbp+70h] BYREF

  memset_0(&v7, 0, sizeof(v7));
  memset_0(v8, 0, sizeof(v8));
  v4 = g_hinst;
  v8[5] = PackWiz_SelectFileDlgProc;
  v8[0] = 104;
  v8[1] = g_hinst;
  v8[2] = 102;
  v8[9] = 3101;
  v8[6] = a2;
  memset_0(v9, 0, sizeof(v9));
  v9[0] = 104;
  v9[5] = PackWiz_SelectLabelDlgProc;
  v9[1] = v4;
  v7.ppsp = (LPCPROPSHEETPAGEW)v8;
  v9[2] = 107;
  v9[9] = 3102;
  v9[6] = a2;
  v7.dwSize = 96;
  v7.hInstance = v4;
  v7.dwFlags = 16396;
  v7.hwndParent = a1;
  v7.nPages = 2;
  v7.nStartPage = 0;
  v7.pszCaption = (LPCWSTR)3100;
  v7.hIcon = (HICON)1500;
  ulCookie = 0;
  SHActivateContext(&ulCookie);
  v5 = PropertySheetW(&v7);
  if ( ulCookie )
    DeactivateActCtx(0, ulCookie);
  return v5;
}

```

## disassembly

```asm
0x18000bda0  mov     [rsp-8+arg_8], rbx
0x18000bda5  mov     [rsp-8+arg_10], rsi
0x18000bdaa  push    rbp
0x18000bdab  push    rdi
0x18000bdac  push    r14
0x18000bdae  lea     rbp, [rsp-50h]
0x18000bdb3  sub     rsp, 150h
0x18000bdba  mov     rdi, rdx
0x18000bdbd  mov     rsi, rcx
0x18000bdc0  xor     edx, edx; Val
0x18000bdc2  lea     rcx, [rsp+160h+var_140]; void *
0x18000bdc7  lea     r8d, [rdx+60h]; Size
0x18000bdcb  call    memset_0
0x18000bdd0  mov     r14d, 68h ; 'h'
0x18000bdd6  lea     rcx, [rbp+60h+var_E0]; void *
0x18000bdda  mov     r8d, r14d; Size
0x18000bddd  xor     edx, edx; Val
0x18000bddf  call    memset_0
0x18000bde4  mov     rbx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x18000bdeb  lea     rax, ?PackWiz_SelectFileDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; PackWiz_SelectFileDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18000bdf2  mov     r8d, r14d; Size
0x18000bdf5  mov     [rbp+60h+var_B8], rax
0x18000bdf9  xor     edx, edx; Val
0x18000bdfb  mov     [rbp+60h+var_E0], r14
0x18000bdff  lea     rcx, [rbp+60h+var_78]; void *
0x18000be03  mov     [rbp+60h+var_D8], rbx
0x18000be07  mov     [rbp+60h+var_D0], 66h ; 'f'
0x18000be0f  mov     [rbp+60h+var_98], 0C1Dh
0x18000be17  mov     [rbp+60h+var_B0], rdi
0x18000be1b  call    memset_0
0x18000be20  lea     rax, ?PackWiz_SelectLabelDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; PackWiz_SelectLabelDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18000be27  mov     [rbp+60h+var_78], r14
0x18000be2b  mov     [rbp+60h+var_50], rax
0x18000be2f  lea     rcx, [rbp+60h+ulCookie]
0x18000be33  lea     rax, [rbp+60h+var_E0]
0x18000be37  mov     [rbp+60h+var_70], rbx
0x18000be3b  mov     qword ptr [rsp+160h+var_140.38h], rax
0x18000be40  mov     [rbp+60h+var_68], 6Bh ; 'k'
0x18000be48  mov     [rbp+60h+var_30], 0C1Eh
0x18000be50  mov     [rbp+60h+var_48], rdi
0x18000be54  mov     [rsp+160h+var_140.dwSize], 60h ; '`'
0x18000be5c  mov     [rsp+160h+var_140.hInstance], rbx
0x18000be61  mov     [rsp+160h+var_140.dwFlags], 400Ch
0x18000be69  mov     [rsp+160h+var_140.hwndParent], rsi
0x18000be6e  mov     [rsp+160h+var_140.nPages], 2
0x18000be76  mov     dword ptr [rsp+160h+var_140.30h], 0
0x18000be7e  mov     [rsp+160h+var_140.pszCaption], 0C1Ch
0x18000be87  mov     qword ptr [rsp+160h+var_140.18h], 5DCh
0x18000be90  mov     [rbp+60h+ulCookie], 0
0x18000be98  call    SHActivateContext
0x18000be9d  lea     rcx, [rsp+160h+var_140]; LPCPROPSHEETHEADERW
0x18000bea2  call    PropertySheetW
0x18000bea7  mov     rdx, [rbp+60h+ulCookie]; ulCookie
0x18000beab  mov     rbx, rax
0x18000beae  test    rdx, rdx
0x18000beb1  jz      short loc_18000BEBB
0x18000beb3  xor     ecx, ecx; dwFlags
0x18000beb5  call    cs:__imp_DeactivateActCtx
0x18000bebb  lea     r11, [rsp+160h+var_10]
0x18000bec3  mov     eax, ebx
0x18000bec5  mov     rbx, [r11+28h]
0x18000bec9  mov     rsi, [r11+30h]
0x18000becd  mov     rsp, r11
0x18000bed0  pop     r14
0x18000bed2  pop     rdi
0x18000bed3  pop     rbp
0x18000bed4  retn
```
