# UserTabFillUserList

- ea: `0x180030748`
- end: `0x180030958`
- name: `UserTabFillUserList`
- size: `528`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180030b44`
- `0x180030d5c`
- `0x18003154c`

## callees

- `0x180030748`
- `0x1800349c4`
- `0x1800353e0`
- `0x1800356c4`
- `0x1800395ec`
- `0x180039780`
- `0x180046764`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `GDI32!DeleteObject` at `0x180030804`
- `GDI32!DeleteObject` at `0x180030804`
- `USER32!LoadIconW` at `0x1800307e8`
- `USER32!LoadIconW` at `0x1800307e8`
- `USER32!SendMessageW` at `0x18003081b`
- `USER32!SendMessageW` at `0x1800308c4`
- `USER32!SendMessageW` at `0x18003090e`
- `USER32!SendMessageW` at `0x18003081b`
- `USER32!SendMessageW` at `0x1800308c4`
- `USER32!SendMessageW` at `0x18003090e`
- `USER32!GetSystemMetrics` at `0x1800307c3`
- `USER32!GetSystemMetrics` at `0x1800307cf`
- `USER32!GetSystemMetrics` at `0x1800307c3`
- `USER32!GetSystemMetrics` at `0x1800307cf`

## pseudocode

```c
__int64 __fastcall UserTabFillUserList(HWND hWnd, __int64 a2)
{
  unsigned int v4; // r12d
  int v5; // r14d
  HINSTANCE v6; // rdi
  int SystemMetrics; // ebx
  int v8; // eax
  UINT v9; // r8d
  int v10; // r9d
  struct _IMAGELIST *v11; // r15
  HICON IconW; // rax
  int v13; // edx
  HICON v14; // rbx
  unsigned int i; // ebx
  __int64 v16; // r8
  __int64 v17; // rdi
  __int64 v18; // rax
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  int lParam; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int lParam_4; // [rsp+44h] [rbp-BCh] BYREF
  _WORD *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  LPARAM v28; // [rsp+A0h] [rbp-60h] BYREF
  int v29; // [rsp+ACh] [rbp-54h]
  int v30; // [rsp+B0h] [rbp-50h]
  _WORD v31[288]; // [rsp+100h] [rbp+0h] BYREF

  memset_0(&lParam, 0, 0x58u);
  v22 = 0;
  memset_0(v31, 0, 0x234u);
  if ( a2 )
  {
    v4 = *(_DWORD *)(a2 + 8);
    v5 = 0;
    v6 = hInstance;
    SystemMetrics = GetSystemMetrics(50);
    v8 = GetSystemMetrics(49);
    v11 = ImageList_Create(v8, SystemMetrics, v9, v10, v20);
    IconW = LoadIconW(v6, (LPCWSTR)0x38);
    v14 = IconW;
    if ( IconW )
    {
      ImageList_ReplaceIcon(v11, v13, IconW);
      DeleteObject(v14);
    }
    SendMessageW(hWnd, 0x1003u, 1u, (LPARAM)v11);
    memset_0(&lParam_4, 0, 0x54u);
    lParam = 3;
    for ( i = 0; i < v4; ++i )
    {
      v21 = 282;
      if ( !(unsigned int)usrGetUserHandle(a2, i, &v22) )
      {
        v17 = v22;
        usrGetDisplayName(v22, v31, v16, &v21);
        if ( v17 )
          v5 = *(_BYTE *)(v17 + 796) & 8;
        v27 = 0;
        v25 = v31;
        v18 = -1;
        lParam_4 = i;
        do
          ++v18;
        while ( v31[v18] );
        v26 = v18 + 1;
        SendMessageW(hWnd, 0x104Du, 0, (LPARAM)&lParam);
        ListView_SetCheck(hWnd, i, v5);
      }
    }
    memset_0(&v28, 0, 0x58u);
    v30 = 3;
    v29 = 3;
    SendMessageW(hWnd, 0x102Bu, 0, (LPARAM)&v28);
    return 0;
  }
  else
  {
    ErrDisplayError(hWnd);
    return 87;
  }
}

```

## disassembly

```asm
0x180030748  mov     [rsp-8+arg_10], rbx
0x18003074d  push    rbp
0x18003074e  push    rsi
0x18003074f  push    rdi
0x180030750  push    r12
0x180030752  push    r13
0x180030754  push    r14
0x180030756  push    r15
0x180030758  lea     rbp, [rsp-250h]
0x180030760  sub     rsp, 350h
0x180030767  mov     rax, cs:__security_cookie
0x18003076e  xor     rax, rsp
0x180030771  mov     [rbp+280h+var_40], rax
0x180030778  mov     r13, rdx
0x18003077b  mov     rsi, rcx
0x18003077e  xor     edx, edx; Val
0x180030780  lea     rcx, [rsp+380h+lParam]; void *
0x180030785  lea     r8d, [rdx+58h]; Size
0x180030789  call    memset_0
0x18003078e  xor     edx, edx; Val
0x180030790  mov     [rsp+380h+var_348], 0
0x180030799  mov     r8d, 234h; Size
0x18003079f  lea     rcx, [rbp+280h+var_280]; void *
0x1800307a3  call    memset_0
0x1800307a8  test    r13, r13
0x1800307ab  jz      loc_180030918
0x1800307b1  mov     r12d, [r13+8]
0x1800307b5  xor     r14d, r14d
0x1800307b8  mov     rdi, cs:hInstance
0x1800307bf  lea     ecx, [r14+32h]; nIndex
0x1800307c3  call    cs:__imp_GetSystemMetrics
0x1800307c9  lea     ecx, [r14+31h]; nIndex
0x1800307cd  mov     ebx, eax
0x1800307cf  call    cs:__imp_GetSystemMetrics
0x1800307d5  mov     ecx, eax; cx
0x1800307d7  mov     edx, ebx; cy
0x1800307d9  call    ImageList_Create
0x1800307de  lea     edx, [r14+38h]; lpIconName
0x1800307e2  mov     rcx, rdi; hInstance
0x1800307e5  mov     r15, rax
0x1800307e8  call    cs:__imp_LoadIconW
0x1800307ee  mov     rbx, rax
0x1800307f1  test    rax, rax
0x1800307f4  jz      short loc_18003080A
0x1800307f6  mov     r8, rax; hicon
0x1800307f9  mov     rcx, r15; himl
0x1800307fc  call    ImageList_ReplaceIcon
0x180030801  mov     rcx, rbx; ho
0x180030804  call    cs:__imp_DeleteObject
0x18003080a  mov     r9, r15; lParam
0x18003080d  mov     edx, 1003h; Msg
0x180030812  mov     r8d, 1; wParam
0x180030818  mov     rcx, rsi; hWnd
0x18003081b  call    cs:__imp_SendMessageW
0x180030821  xor     edx, edx; Val
0x180030823  lea     rcx, [rsp+380h+lParam+4]; void *
0x180030828  lea     r8d, [rdx+54h]; Size
0x18003082c  call    memset_0
0x180030831  xor     r15d, r15d
0x180030834  mov     [rsp+380h+lParam], 3
0x18003083c  mov     ebx, r15d
0x18003083f  test    r12d, r12d
0x180030842  jz      loc_1800308E2
0x180030848  lea     r8, [rsp+380h+var_348]
0x18003084d  mov     [rsp+380h+var_350], 11Ah
0x180030855  mov     edx, ebx
0x180030857  mov     rcx, r13
0x18003085a  call    usrGetUserHandle
0x18003085f  test    eax, eax
0x180030861  jnz     short loc_1800308D7
0x180030863  mov     rdi, [rsp+380h+var_348]
0x180030868  lea     r9, [rsp+380h+var_350]
0x18003086d  mov     rcx, rdi
0x180030870  lea     rdx, [rbp+280h+var_280]
0x180030874  call    usrGetDisplayName
0x180030879  test    rdi, rdi
0x18003087c  jz      short loc_18003088A
0x18003087e  movzx   r14d, byte ptr [rdi+31Ch]
0x180030886  and     r14d, 8
0x18003088a  lea     rax, [rbp+280h+var_280]
0x18003088e  mov     [rsp+380h+var_31C], r15d
0x180030893  mov     [rsp+380h+var_328], rax
0x180030898  lea     rcx, [rbp+280h+var_280]
0x18003089c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800308a0  mov     [rsp+380h+lParam+4], ebx
0x1800308a4  inc     rax
0x1800308a7  cmp     [rcx+rax*2], r15w
0x1800308ac  jnz     short loc_1800308A4
0x1800308ae  inc     eax
0x1800308b0  lea     r9, [rsp+380h+lParam]; lParam
0x1800308b5  xor     r8d, r8d; wParam
0x1800308b8  mov     [rsp+380h+var_320], eax
0x1800308bc  mov     edx, 104Dh; Msg
0x1800308c1  mov     rcx, rsi; hWnd
0x1800308c4  call    cs:__imp_SendMessageW
0x1800308ca  mov     r8d, r14d
0x1800308cd  mov     edx, ebx
0x1800308cf  mov     rcx, rsi; hWnd
0x1800308d2  call    ListView_SetCheck
0x1800308d7  inc     ebx
0x1800308d9  cmp     ebx, r12d
0x1800308dc  jb      loc_180030848
0x1800308e2  xor     edx, edx; Val
0x1800308e4  lea     rcx, [rbp+280h+var_2E0]; void *
0x1800308e8  lea     r8d, [rdx+58h]; Size
0x1800308ec  call    memset_0
0x1800308f1  lea     r9, [rbp+280h+var_2E0]; lParam
0x1800308f5  mov     [rbp+280h+var_2D0], 3
0x1800308fc  xor     r8d, r8d; wParam
0x1800308ff  mov     [rbp+280h+var_2D4], 3
0x180030906  mov     edx, 102Bh; Msg
0x18003090b  mov     rcx, rsi; hWnd
0x18003090e  call    cs:__imp_SendMessageW
0x180030914  xor     eax, eax
0x180030916  jmp     short loc_18003092E
0x180030918  mov     edx, 1CA3h
0x18003091d  mov     rcx, rsi; hWnd
0x180030920  lea     r8d, [rdx-17h]
0x180030924  call    ErrDisplayError
0x180030929  mov     eax, 57h ; 'W'
0x18003092e  mov     rcx, [rbp+280h+var_40]
0x180030935  xor     rcx, rsp; StackCookie
0x180030938  call    __security_check_cookie
0x18003093d  mov     rbx, [rsp+380h+arg_10]
0x180030945  add     rsp, 350h
0x18003094c  pop     r15
0x18003094e  pop     r14
0x180030950  pop     r13
0x180030952  pop     r12
0x180030954  pop     rdi
0x180030955  pop     rsi
0x180030956  pop     rbp
0x180030957  retn
```
