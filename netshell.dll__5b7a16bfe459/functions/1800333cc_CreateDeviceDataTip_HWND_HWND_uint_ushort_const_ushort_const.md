# CreateDeviceDataTip(HWND__ *,HWND__ * *,uint,ushort const *,ushort const *)

- ea: `0x1800333cc`
- end: `0x180033578`
- name: `?CreateDeviceDataTip@@YAXPEAUHWND__@@PEAPEAU1@IPEBG2@Z`
- size: `428`
- prototype: `void __usercall(HWND hDlg@<rcx>, HWND *@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002df10`

## callees

- `0x18001e1e0`
- `0x18001eb7c`
- `0x18003323c`
- `0x1800333cc`
- `0x180033580`

## import_xrefs

- `USER32!SendMessageW` at `0x180033512`
- `USER32!SendMessageW` at `0x18003353a`
- `USER32!SendMessageW` at `0x180033551`
- `USER32!SendMessageW` at `0x180033512`
- `USER32!SendMessageW` at `0x18003353a`
- `USER32!SendMessageW` at `0x180033551`
- `USER32!SetWindowPos` at `0x18003347c`
- `USER32!SetWindowPos` at `0x18003347c`
- `USER32!GetDlgItem` at `0x1800334ad`
- `USER32!GetDlgItem` at `0x1800334ad`
- `USER32!GetSystemMetrics` at `0x18003351a`
- `USER32!GetSystemMetrics` at `0x18003351a`
- `USER32!CreateWindowExW` at `0x18003344f`
- `USER32!CreateWindowExW` at `0x18003344f`

## pseudocode

```c
void __fastcall CreateDeviceDataTip(HWND hDlg, HWND *a2, __int64 a3, const unsigned __int16 *a4, unsigned __int16 *a5)
{
  HWND Window; // rax
  HWND DlgItem; // rax
  unsigned int v10; // r8d
  HWND v11; // rcx
  unsigned int v12; // eax
  _DWORD lParam[4]; // [rsp+60h] [rbp-A0h] BYREF
  HWND v14; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v15; // [rsp+90h] [rbp-70h]
  unsigned __int16 v16[264]; // [rsp+B0h] [rbp-50h] BYREF

  if ( *a2 )
    goto LABEL_5;
  Window = CreateWindowExW(
             0,
             L"tooltips_class32",
             0,
             0x80000001,
             0x80000000,
             0x80000000,
             0x80000000,
             0x80000000,
             hDlg,
             0,
             0,
             0);
  *a2 = Window;
  if ( Window )
    SetWindowPos(Window, HWND_MESSAGE|0x2LL, 0x80000000, 0x80000000, 0x80000000, 0x80000000, 0x13u);
  if ( *a2 )
  {
LABEL_5:
    memset_0(lParam, 0, 0x48u);
    lParam[0] = 72;
    DlgItem = GetDlgItem(hDlg, 15003);
    lParam[1] = 17;
    v14 = DlgItem;
    memset_0(v16, 0, 0x208u);
    if ( a4 )
      GetLocationInfo(a4, v16);
    if ( a5 )
      AppendMacAddress(a5, v16, v10);
    if ( v16[0] )
    {
      v11 = *a2;
      v15 = v16;
      SendMessageW(v11, 0x432u, 0, (LPARAM)lParam);
      v12 = GetSystemMetrics(0) / 2;
      if ( v12 )
        SendMessageW(*a2, 0x418u, 0, v12);
      SendMessageW(*a2, 0x403u, 2u, 30000);
    }
  }
}

```

## disassembly

```asm
0x1800333cc  push    rbp
0x1800333ce  push    rbx
0x1800333cf  push    rsi
0x1800333d0  push    rdi
0x1800333d1  push    r12
0x1800333d3  push    r14
0x1800333d5  push    r15
0x1800333d7  lea     rbp, [rsp-1D0h]
0x1800333df  sub     rsp, 2D0h
0x1800333e6  mov     rax, cs:__security_cookie
0x1800333ed  xor     rax, rsp
0x1800333f0  mov     [rbp+200h+var_40], rax
0x1800333f7  mov     rdi, [rbp+200h+arg_20]
0x1800333fe  xor     r12d, r12d
0x180033401  mov     rsi, r9
0x180033404  mov     rbx, rdx
0x180033407  mov     r14, rcx
0x18003340a  cmp     [rdx], r12
0x18003340d  jnz     short loc_18003348B
0x18003340f  mov     [rsp+300h+lpParam], r12; lpParam
0x180033414  lea     rdx, ClassName; "tooltips_class32"
0x18003341b  mov     [rsp+300h+hInstance], r12; hInstance
0x180033420  mov     r15d, 80000000h
0x180033426  mov     [rsp+300h+hMenu], r12; hMenu
0x18003342b  mov     r9d, 80000001h; dwStyle
0x180033431  mov     [rsp+300h+hWndParent], rcx; hWndParent
0x180033436  xor     r8d, r8d; lpWindowName
0x180033439  mov     [rsp+300h+nHeight], r15d; nHeight
0x18003343e  xor     ecx, ecx; dwExStyle
0x180033440  mov     [rsp+300h+nWidth], r15d; nWidth
0x180033445  mov     [rsp+300h+Y], r15d; Y
0x18003344a  mov     [rsp+300h+X], r15d; X
0x18003344f  call    cs:__imp_CreateWindowExW
0x180033455  mov     [rbx], rax
0x180033458  test    rax, rax
0x18003345b  jz      short loc_180033482
0x18003345d  mov     [rsp+300h+nWidth], 13h; uFlags
0x180033465  mov     r9d, r15d; Y
0x180033468  mov     [rsp+300h+Y], r15d; cy
0x18003346d  mov     r8d, r15d; X
0x180033470  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x180033474  mov     [rsp+300h+X], r15d; cx
0x180033479  mov     rcx, rax; hWnd
0x18003347c  call    cs:__imp_SetWindowPos
0x180033482  cmp     [rbx], r12
0x180033485  jz      loc_180033557
0x18003348b  mov     r15d, 48h ; 'H'
0x180033491  lea     rcx, [rsp+300h+lParam]; void *
0x180033496  mov     r8d, r15d; Size
0x180033499  xor     edx, edx; Val
0x18003349b  call    memset_0
0x1800334a0  mov     edx, 3A9Bh; nIDDlgItem
0x1800334a5  mov     [rsp+300h+lParam], r15d
0x1800334aa  mov     rcx, r14; hDlg
0x1800334ad  call    cs:__imp_GetDlgItem
0x1800334b3  xor     edx, edx; Val
0x1800334b5  mov     [rsp+300h+lParam+4], 11h
0x1800334bd  mov     r8d, 208h; Size
0x1800334c3  mov     [rsp+300h+var_290], rax
0x1800334c8  lea     rcx, [rbp+200h+var_250]; void *
0x1800334cc  call    memset_0
0x1800334d1  test    rsi, rsi
0x1800334d4  jz      short loc_1800334E2
0x1800334d6  lea     rdx, [rbp+200h+var_250]; unsigned __int16 *
0x1800334da  mov     rcx, rsi; DeviceInstanceId
0x1800334dd  call    ?GetLocationInfo@@YAXPEBGPEAGK@Z; GetLocationInfo(ushort const *,ushort *,ulong)
0x1800334e2  test    rdi, rdi
0x1800334e5  jz      short loc_1800334F3
0x1800334e7  lea     rdx, [rbp+200h+var_250]; unsigned __int16 *
0x1800334eb  mov     rcx, rdi; unsigned __int16 *
0x1800334ee  call    ?AppendMacAddress@@YAXPEBGPEAGK@Z; AppendMacAddress(ushort const *,ushort *,ulong)
0x1800334f3  cmp     [rbp+200h+var_250], r12w
0x1800334f8  jz      short loc_180033557
0x1800334fa  mov     rcx, [rbx]; hWnd
0x1800334fd  lea     rax, [rbp+200h+var_250]
0x180033501  lea     r9, [rsp+300h+lParam]; lParam
0x180033506  mov     [rbp+200h+var_270], rax
0x18003350a  xor     r8d, r8d; wParam
0x18003350d  mov     edx, 432h; Msg
0x180033512  call    cs:__imp_SendMessageW
0x180033518  xor     ecx, ecx; nIndex
0x18003351a  call    cs:__imp_GetSystemMetrics
0x180033520  cdq
0x180033521  mov     edi, 2
0x180033526  idiv    edi
0x180033528  test    eax, eax
0x18003352a  jz      short loc_180033540
0x18003352c  mov     rcx, [rbx]; hWnd
0x18003352f  xor     r8d, r8d; wParam
0x180033532  mov     r9d, eax; lParam
0x180033535  mov     edx, 418h; Msg
0x18003353a  call    cs:__imp_SendMessageW
0x180033540  mov     rcx, [rbx]; hWnd
0x180033543  mov     r9d, 7530h; lParam
0x180033549  mov     r8, rdi; wParam
0x18003354c  mov     edx, 403h; Msg
0x180033551  call    cs:__imp_SendMessageW
0x180033557  mov     rcx, [rbp+200h+var_40]
0x18003355e  xor     rcx, rsp; StackCookie
0x180033561  call    __security_check_cookie
0x180033566  add     rsp, 2D0h
0x18003356d  pop     r15
0x18003356f  pop     r14
0x180033571  pop     r12
0x180033573  pop     rdi
0x180033574  pop     rsi
0x180033575  pop     rbx
0x180033576  pop     rbp
0x180033577  retn
```
