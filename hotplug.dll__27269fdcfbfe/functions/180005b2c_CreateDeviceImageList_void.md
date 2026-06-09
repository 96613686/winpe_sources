# CreateDeviceImageList(void)

- ea: `0x180005b2c`
- end: `0x180005c77`
- name: `?CreateDeviceImageList@@YAPEAU_IMAGELIST@@XZ`
- size: `331`
- prototype: `struct _IMAGELIST *(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002f9c`
- `0x180004114`
- `0x18000712c`

## callees

- `0x180005b2c`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180005bd6`
- `KERNEL32!GetModuleHandleW` at `0x180005bd6`
- `USER32!ReleaseDC` at `0x180005b7c`
- `USER32!ReleaseDC` at `0x180005b7c`
- `USER32!LoadImageW` at `0x180005c19`
- `USER32!LoadImageW` at `0x180005c19`
- `USER32!GetProcessDefaultLayout` at `0x180005b87`
- `USER32!GetProcessDefaultLayout` at `0x180005b87`
- `USER32!GetDC` at `0x180005b51`
- `USER32!GetDC` at `0x180005b51`
- `USER32!GetSystemMetrics` at `0x180005ba1`
- `USER32!GetSystemMetrics` at `0x180005bae`
- `USER32!GetSystemMetrics` at `0x180005bee`
- `USER32!GetSystemMetrics` at `0x180005bfb`
- `USER32!GetSystemMetrics` at `0x180005ba1`
- `USER32!GetSystemMetrics` at `0x180005bae`
- `USER32!GetSystemMetrics` at `0x180005bee`
- `USER32!GetSystemMetrics` at `0x180005bfb`
- `USER32!DestroyIcon` at `0x180005c50`
- `USER32!DestroyIcon` at `0x180005c50`
- `GDI32!GetDeviceCaps` at `0x180005b66`
- `GDI32!GetDeviceCaps` at `0x180005b66`
- `COMCTL32!ImageList_ReplaceIcon` at `0x180005c30`
- `COMCTL32!ImageList_ReplaceIcon` at `0x180005c30`
- `COMCTL32!ImageList_Create` at `0x180005bc6`
- `COMCTL32!ImageList_Create` at `0x180005bc6`
- `COMCTL32!ImageList_SetOverlayImage` at `0x180005c47`
- `COMCTL32!ImageList_SetOverlayImage` at `0x180005c47`

## string_xrefs

- `0x180005bcc`: `setupapi.dll`

## pseudocode

```c
struct _IMAGELIST *CreateDeviceImageList(void)
{
  UINT v0; // edi
  HDC DC; // rax
  HDC v2; // rbx
  int SystemMetrics; // ebx
  int v4; // eax
  struct _IMAGELIST *v5; // rsi
  HMODULE ModuleHandleW; // rbp
  int i; // edi
  int v8; // ebx
  int v9; // eax
  HICON ImageW; // rax
  HICON v11; // rbx
  int v12; // eax
  DWORD pdwDefaultLayout; // [rsp+50h] [rbp+8h] BYREF

  pdwDefaultLayout = 0;
  v0 = 1;
  DC = GetDC(0);
  v2 = DC;
  if ( DC )
  {
    v0 = 33;
    if ( GetDeviceCaps(DC, 12) <= 8 )
      v0 = 1;
    ReleaseDC(0, v2);
  }
  if ( GetProcessDefaultLayout(&pdwDefaultLayout) && (pdwDefaultLayout & 1) != 0 )
    v0 |= 0x2000u;
  SystemMetrics = GetSystemMetrics(50);
  v4 = GetSystemMetrics(49);
  v5 = ImageList_Create(v4, SystemMetrics, v0, 50, 1);
  ModuleHandleW = GetModuleHandleW(L"setupapi.dll");
  if ( ModuleHandleW )
  {
    for ( i = 500; i <= 502; ++i )
    {
      v8 = GetSystemMetrics(50);
      v9 = GetSystemMetrics(49);
      ImageW = (HICON)LoadImageW(ModuleHandleW, (LPCWSTR)(unsigned __int16)i, 1u, v9, v8, 0x8000u);
      v11 = ImageW;
      if ( ImageW )
      {
        v12 = ImageList_ReplaceIcon(v5, -1, ImageW);
        if ( v12 != -1 )
          ImageList_SetOverlayImage(v5, v12, i - 499);
        DestroyIcon(v11);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180005b2c  mov     [rsp+arg_8], rbx
0x180005b31  mov     [rsp+arg_10], rbp
0x180005b36  push    rsi
0x180005b37  push    rdi
0x180005b38  push    r14
0x180005b3a  sub     rsp, 30h
0x180005b3e  mov     r14d, 1
0x180005b44  mov     [rsp+48h+pdwDefaultLayout], 0
0x180005b4c  xor     ecx, ecx; hWnd
0x180005b4e  mov     edi, r14d
0x180005b51  call    cs:__imp_GetDC
0x180005b57  mov     rbx, rax
0x180005b5a  test    rax, rax
0x180005b5d  jz      short loc_180005B82
0x180005b5f  lea     edx, [r14+0Bh]; index
0x180005b63  mov     rcx, rax; hdc
0x180005b66  call    cs:__imp_GetDeviceCaps
0x180005b6c  lea     edi, [r14+20h]
0x180005b70  mov     rdx, rbx; hDC
0x180005b73  cmp     eax, 8
0x180005b76  cmovle  edi, r14d
0x180005b7a  xor     ecx, ecx; hWnd
0x180005b7c  call    cs:__imp_ReleaseDC
0x180005b82  lea     rcx, [rsp+48h+pdwDefaultLayout]; pdwDefaultLayout
0x180005b87  call    cs:__imp_GetProcessDefaultLayout
0x180005b8d  test    eax, eax
0x180005b8f  jz      short loc_180005B9C
0x180005b91  test    byte ptr [rsp+48h+pdwDefaultLayout], r14b
0x180005b96  jz      short loc_180005B9C
0x180005b98  bts     edi, 0Dh
0x180005b9c  mov     ecx, 32h ; '2'; nIndex
0x180005ba1  call    cs:__imp_GetSystemMetrics
0x180005ba7  mov     ecx, 31h ; '1'; nIndex
0x180005bac  mov     ebx, eax
0x180005bae  call    cs:__imp_GetSystemMetrics
0x180005bb4  mov     r9d, 32h ; '2'; cInitial
0x180005bba  mov     [rsp+48h+cGrow], r14d; cGrow
0x180005bbf  mov     ecx, eax; cx
0x180005bc1  mov     r8d, edi; flags
0x180005bc4  mov     edx, ebx; cy
0x180005bc6  call    cs:__imp_ImageList_Create
0x180005bcc  lea     rcx, ModuleName; "setupapi.dll"
0x180005bd3  mov     rsi, rax
0x180005bd6  call    cs:__imp_GetModuleHandleW
0x180005bdc  mov     rbp, rax
0x180005bdf  test    rax, rax
0x180005be2  jz      short loc_180005C61
0x180005be4  mov     edi, 1F4h
0x180005be9  mov     ecx, 32h ; '2'; nIndex
0x180005bee  call    cs:__imp_GetSystemMetrics
0x180005bf4  mov     ecx, 31h ; '1'; nIndex
0x180005bf9  mov     ebx, eax
0x180005bfb  call    cs:__imp_GetSystemMetrics
0x180005c01  movzx   edx, di; name
0x180005c04  mov     r8d, r14d; type
0x180005c07  mov     r9d, eax; cx
0x180005c0a  mov     [rsp+48h+fuLoad], 8000h; fuLoad
0x180005c12  mov     rcx, rbp; hInst
0x180005c15  mov     [rsp+48h+cGrow], ebx; cy
0x180005c19  call    cs:__imp_LoadImageW
0x180005c1f  mov     rbx, rax
0x180005c22  test    rax, rax
0x180005c25  jz      short loc_180005C56
0x180005c27  mov     r8, rax; hicon
0x180005c2a  or      edx, 0FFFFFFFFh; i
0x180005c2d  mov     rcx, rsi; himl
0x180005c30  call    cs:__imp_ImageList_ReplaceIcon
0x180005c36  cmp     eax, 0FFFFFFFFh
0x180005c39  jz      short loc_180005C4D
0x180005c3b  lea     r8d, [rdi-1F3h]; iOverlay
0x180005c42  mov     edx, eax; iImage
0x180005c44  mov     rcx, rsi; himl
0x180005c47  call    cs:__imp_ImageList_SetOverlayImage
0x180005c4d  mov     rcx, rbx; hIcon
0x180005c50  call    cs:__imp_DestroyIcon
0x180005c56  add     edi, r14d
0x180005c59  cmp     edi, 1F6h
0x180005c5f  jle     short loc_180005BE9
0x180005c61  mov     rbx, [rsp+48h+arg_8]
0x180005c66  mov     rax, rsi
0x180005c69  mov     rbp, [rsp+48h+arg_10]
0x180005c6e  add     rsp, 30h
0x180005c72  pop     r14
0x180005c74  pop     rdi
0x180005c75  pop     rsi
0x180005c76  retn
```
