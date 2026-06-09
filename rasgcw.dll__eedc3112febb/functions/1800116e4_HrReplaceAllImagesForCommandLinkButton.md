# HrReplaceAllImagesForCommandLinkButton

- ea: `0x1800116e4`
- end: `0x18001187b`
- name: `HrReplaceAllImagesForCommandLinkButton`
- size: `407`
- prototype: `__int64 __fastcall(HWND hWnd, HICON hicon)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001cea0`
- `0x18001dabc`

## callees

- `0x1800116e4`
- `0x18002ec04`
- `0x18002ed4c`
- `0x18002f3b0`

## import_xrefs

- `USER32!SendMessageW` at `0x180011723`
- `USER32!SendMessageW` at `0x18001180f`
- `USER32!SendMessageW` at `0x180011723`
- `USER32!SendMessageW` at `0x18001180f`
- `USER32!GetSystemMetrics` at `0x18001173d`
- `USER32!GetSystemMetrics` at `0x18001174f`
- `USER32!GetSystemMetrics` at `0x18001173d`
- `USER32!GetSystemMetrics` at `0x18001174f`
- `rtutils!TracePrintfExA` at `0x180011795`
- `rtutils!TracePrintfExA` at `0x1800117e8`
- `rtutils!TracePrintfExA` at `0x180011855`
- `rtutils!TracePrintfExA` at `0x180011795`
- `rtutils!TracePrintfExA` at `0x1800117e8`
- `rtutils!TracePrintfExA` at `0x180011855`

## string_xrefs

- `0x18001178b`: `Failed to create an image list for button. hr = %#x`
- `0x1800117dc`: `Failed to replace icon image %d. hr = %#x`
- `0x18001182b`: `Failed to replace image list. hr = %#x`

## pseudocode

```c
__int64 __fastcall HrReplaceAllImagesForCommandLinkButton(HWND hWnd, HICON hicon, int a3)
{
  int SystemMetrics; // ebx
  int v7; // eax
  struct _IMAGELIST *v8; // rbx
  unsigned int i; // edi
  unsigned int v11; // esi
  LPARAM lParam[2]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v13; // [rsp+40h] [rbp-38h]

  *(_OWORD *)lParam = 0;
  v13 = 0;
  if ( !(unsigned int)SendMessageW(hWnd, 0x1603u, 0, (LPARAM)lParam) )
  {
    v11 = -2147467259;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Failed to get the button image list. hr = %#x", 2147500037LL);
    return v11;
  }
  SystemMetrics = GetSystemMetrics(a3 != 0 ? 50 : 12);
  v7 = GetSystemMetrics(a3 != 0 ? 49 : 11);
  v8 = ImageList_Create(v7, SystemMetrics, 0x21u, 6, 0);
  if ( v8 )
  {
    for ( i = 0; i < 6; ++i )
    {
      if ( i != ImageList_ReplaceIcon(v8, -1, hicon) )
      {
        v11 = -2147467259;
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "Failed to replace icon image %d. hr = %#x", i, -2147467259);
        return v11;
      }
    }
    lParam[0] = (LPARAM)v8;
    DWORD2(v13) = 2;
    v11 = 0;
    if ( !(unsigned int)SendMessageW(hWnd, 0x1602u, 0, (LPARAM)lParam) )
    {
      v11 = -2147467259;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed to replace image list. hr = %#x", 2147500037LL);
    }
    return v11;
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "Failed to create an image list for button. hr = %#x", -2147467259);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800116e4  mov     [rsp+arg_10], rbx
0x1800116e9  push    rsi
0x1800116ea  push    rdi
0x1800116eb  push    r14
0x1800116ed  sub     rsp, 60h
0x1800116f1  mov     rax, cs:__security_cookie
0x1800116f8  xor     rax, rsp
0x1800116fb  mov     [rsp+78h+var_28], rax
0x180011700  xorps   xmm0, xmm0
0x180011703  lea     r9, [rsp+78h+lParam]; lParam
0x180011708  mov     edi, r8d
0x18001170b  mov     rsi, rdx
0x18001170e  xor     r8d, r8d; wParam
0x180011711  mov     edx, 1603h; Msg
0x180011716  movups  xmmword ptr [rsp+78h+lParam], xmm0
0x18001171b  mov     r14, rcx
0x18001171e  movups  [rsp+78h+var_38], xmm0
0x180011723  call    cs:__imp_SendMessageW
0x180011729  test    eax, eax
0x18001172b  jz      loc_180011834
0x180011731  mov     eax, edi
0x180011733  neg     eax
0x180011735  sbb     ecx, ecx
0x180011737  and     ecx, 26h
0x18001173a  add     ecx, 0Ch; nIndex
0x18001173d  call    cs:__imp_GetSystemMetrics
0x180011743  neg     edi
0x180011745  mov     ebx, eax
0x180011747  sbb     ecx, ecx
0x180011749  and     ecx, 26h
0x18001174c  add     ecx, 0Bh; nIndex
0x18001174f  call    cs:__imp_GetSystemMetrics
0x180011755  mov     r9d, 6; cInitial
0x18001175b  mov     [rsp+78h+cGrow], 0; cGrow
0x180011763  mov     edx, ebx; cy
0x180011765  mov     ecx, eax; cx
0x180011767  lea     r8d, [r9+1Bh]; flags
0x18001176b  call    ImageList_Create
0x180011770  mov     rbx, rax
0x180011773  test    rax, rax
0x180011776  jnz     short loc_1800117A2
0x180011778  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001177e  mov     ebx, 80004005h
0x180011783  cmp     ecx, 0FFFFFFFFh
0x180011786  jz      short loc_18001179B
0x180011788  mov     r9d, ebx
0x18001178b  lea     r8, aFailedToCreate_0; "Failed to create an image list for butt"...
0x180011792  lea     edx, [rax+0Ch]; dwFlags
0x180011795  call    cs:__imp_TracePrintfExA
0x18001179b  mov     eax, ebx
0x18001179d  jmp     loc_18001185D
0x1800117a2  xor     edi, edi
0x1800117a4  cmp     edi, 6
0x1800117a7  jnb     short loc_1800117F0
0x1800117a9  mov     r8, rsi; hicon
0x1800117ac  or      edx, 0FFFFFFFFh; i
0x1800117af  mov     rcx, rbx; himl
0x1800117b2  call    ImageList_ReplaceIcon
0x1800117b7  cmp     edi, eax
0x1800117b9  jnz     short loc_1800117BF
0x1800117bb  inc     edi
0x1800117bd  jmp     short loc_1800117A4
0x1800117bf  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800117c5  mov     ebx, 80004005h
0x1800117ca  mov     esi, ebx
0x1800117cc  cmp     ecx, 0FFFFFFFFh
0x1800117cf  jz      loc_18001185B
0x1800117d5  mov     r9d, edi
0x1800117d8  mov     [rsp+78h+cGrow], ebx
0x1800117dc  lea     r8, aFailedToReplac; "Failed to replace icon image %d. hr = %"...
0x1800117e3  mov     edx, 0Ch; dwFlags
0x1800117e8  call    cs:__imp_TracePrintfExA
0x1800117ee  jmp     short loc_18001185B
0x1800117f0  lea     r9, [rsp+78h+lParam]; lParam
0x1800117f5  mov     [rsp+78h+lParam], rbx
0x1800117fa  xor     r8d, r8d; wParam
0x1800117fd  mov     dword ptr [rsp+78h+var_38+8], 2
0x180011805  mov     edx, 1602h; Msg
0x18001180a  mov     rcx, r14; hWnd
0x18001180d  xor     esi, esi
0x18001180f  call    cs:__imp_SendMessageW
0x180011815  test    eax, eax
0x180011817  jnz     short loc_18001185B
0x180011819  mov     ecx, cs:g_dwTraceId
0x18001181f  mov     ebx, 80004005h
0x180011824  mov     esi, ebx
0x180011826  cmp     ecx, 0FFFFFFFFh
0x180011829  jz      short loc_18001185B
0x18001182b  lea     r8, aFailedToReplac_0; "Failed to replace image list. hr = %#x"
0x180011832  jmp     short loc_18001184D
0x180011834  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001183a  mov     ebx, 80004005h
0x18001183f  mov     esi, ebx
0x180011841  cmp     ecx, 0FFFFFFFFh
0x180011844  jz      short loc_18001185B
0x180011846  lea     r8, aFailedToGetThe; "Failed to get the button image list. hr"...
0x18001184d  mov     r9d, ebx
0x180011850  mov     edx, 0Ch; dwFlags
0x180011855  call    cs:__imp_TracePrintfExA
0x18001185b  mov     eax, esi
0x18001185d  mov     rcx, [rsp+78h+var_28]
0x180011862  xor     rcx, rsp; StackCookie
0x180011865  call    __security_check_cookie
0x18001186a  mov     rbx, [rsp+78h+arg_10]
0x180011872  add     rsp, 60h
0x180011876  pop     r14
0x180011878  pop     rdi
0x180011879  pop     rsi
0x18001187a  retn
```
