# GetSelFile

- ea: `0x180010a4c`
- end: `0x180010cd3`
- name: `GetSelFile`
- size: `647`
- prototype: `__int64 __fastcall(HWND hDlg, __int64, int, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000c440`

## callees

- `0x180002e14`
- `0x180004afc`
- `0x180010828`
- `0x180010978`
- `0x180010a4c`
- `0x180011564`
- `0x18001463c`
- `0x180014aae`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_wstat` at `0x180010c8e`
- `msvcrt!_wstat` at `0x180010c8e`
- `msvcrt!_wsplitpath_s` at `0x180010bc1`
- `msvcrt!_wsplitpath_s` at `0x180010bc1`
- `USER32!GetWindowTextW` at `0x180010b85`
- `USER32!GetWindowTextW` at `0x180010b85`
- `USER32!GetDlgItem` at `0x180010b24`
- `USER32!GetDlgItem` at `0x180010b72`
- `USER32!GetDlgItem` at `0x180010b24`
- `USER32!GetDlgItem` at `0x180010b72`

## pseudocode

```c
__int64 __fastcall GetSelFile(HWND hDlg, __int64 a2, int a3, wchar_t *a4, unsigned int a5)
{
  unsigned int v8; // ebx
  HWND DlgItem; // rax
  HWND v11; // rax
  unsigned int v12; // ebx
  size_t v13; // rdx
  size_t v14; // rax
  size_t v15; // rdx
  __int64 v16; // r11
  size_t pcchLength; // [rsp+50h] [rbp-B0h] BYREF
  size_t v18; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v19[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v20; // [rsp+80h] [rbp-80h]
  wchar_t Dir; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v22[526]; // [rsp+92h] [rbp-6Eh] BYREF
  WCHAR String; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v24[526]; // [rsp+2A2h] [rbp+1A2h] BYREF
  wchar_t Drive; // [rsp+4B0h] [rbp+3B0h] BYREF
  _BYTE v26[526]; // [rsp+4B2h] [rbp+3B2h] BYREF
  __int16 v27; // [rsp+6C0h] [rbp+5C0h] BYREF
  _BYTE v28[526]; // [rsp+6C2h] [rbp+5C2h] BYREF

  String = 0;
  memset_0(v24, 0, 0x208u);
  Drive = 0;
  memset_0(v26, 0, 0x208u);
  Dir = 0;
  memset_0(v22, 0, 0x208u);
  v27 = 0;
  memset_0(v28, 0, 0x208u);
  pcchLength = 0;
  memset(v19, 0, sizeof(v19));
  v20 = 0;
  if ( !a4 || (v8 = a5) == 0 )
  {
    a4 = (wchar_t *)&v27;
    v8 = 261;
  }
  DlgItem = GetDlgItem(hDlg, 1884);
  if ( (unsigned int)DetermineSel2(DlgItem, 0, 0, 0, 0, 0, 0, &pcchLength) )
    return GetFileFromParam(pcchLength, a4, v8);
  v11 = GetDlgItem(hDlg, a3);
  if ( GetWindowTextW(v11, &String, 261) < 0 )
    return 0;
  _wsplitpath_s(&String, &Drive, 0x105u, &Dir, 0x105u, 0, 0, 0, 0);
  v12 = v8 - 1;
  *a4 = 0;
  if ( !Drive && Dir != 92 )
  {
    v18 = 0;
    GetBrowseParent(hDlg, &Dir);
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)&v22[2 * v14 - 2] );
    pcchLength = v14;
    if ( StringLengthWorkerW(&Dir, v13, &pcchLength) >= 0
      && StringLengthWorkerW(&String, v15, &v18) >= 0
      && v18 + pcchLength + 1 <= v12 )
    {
      StringCchCopyW(a4, v12, &Dir);
      v12 -= v16;
      if ( *((_WORD *)&v20 + v16 + 7) != 92 )
        StringCchCatW(a4, v12--, L"\\");
    }
  }
  StringCchCatW(a4, v12, &String);
  if ( (unsigned int)_wstat(a4, v19) )
    return 0;
  else
    return (unsigned int)(SWORD3(v19[0]) < 0) + 1;
}

```

## disassembly

```asm
0x180010a4c  push    rbp
0x180010a4e  push    rbx
0x180010a4f  push    rsi
0x180010a50  push    rdi
0x180010a51  push    r12
0x180010a53  push    r14
0x180010a55  push    r15
0x180010a57  lea     rbp, [rsp-7E0h]
0x180010a5f  sub     rsp, 8E0h
0x180010a66  mov     rax, cs:__security_cookie
0x180010a6d  xor     rax, rsp
0x180010a70  mov     [rbp+810h+var_40], rax
0x180010a77  mov     r14d, r8d
0x180010a7a  mov     rsi, rcx
0x180010a7d  mov     ebx, 208h
0x180010a82  lea     rcx, [rbp+810h+var_66E]; void *
0x180010a89  xor     r15d, r15d
0x180010a8c  mov     r8d, ebx; Size
0x180010a8f  xor     edx, edx; Val
0x180010a91  mov     [rbp+810h+String], r15w
0x180010a99  mov     rdi, r9
0x180010a9c  call    memset_0
0x180010aa1  mov     r8d, ebx; Size
0x180010aa4  mov     [rbp+810h+Drive], r15w
0x180010aac  xor     edx, edx; Val
0x180010aae  lea     rcx, [rbp+810h+var_45E]; void *
0x180010ab5  call    memset_0
0x180010aba  mov     r8d, ebx; Size
0x180010abd  mov     [rbp+810h+Dir], r15w
0x180010ac2  xor     edx, edx; Val
0x180010ac4  lea     rcx, [rbp+810h+var_87E]; void *
0x180010ac8  call    memset_0
0x180010acd  mov     r8d, ebx; Size
0x180010ad0  mov     [rbp+810h+var_250], r15w
0x180010ad8  xor     edx, edx; Val
0x180010ada  lea     rcx, [rbp+810h+var_24E]; void *
0x180010ae1  call    memset_0
0x180010ae6  mov     [rsp+910h+pcchLength], r15
0x180010aeb  xorps   xmm0, xmm0
0x180010aee  mov     r12d, 105h
0x180010af4  movups  [rsp+910h+var_8B0], xmm0
0x180010af9  movups  [rsp+910h+var_8A0], xmm0
0x180010afe  movups  [rbp+810h+var_890], xmm0
0x180010b02  test    rdi, rdi
0x180010b05  jz      short loc_180010B12
0x180010b07  mov     ebx, [rbp+810h+arg_20]
0x180010b0d  cmp     ebx, 1
0x180010b10  jnb     short loc_180010B1C
0x180010b12  lea     rdi, [rbp+810h+var_250]
0x180010b19  mov     ebx, r12d
0x180010b1c  mov     edx, 75Ch; nIDDlgItem
0x180010b21  mov     rcx, rsi; hDlg
0x180010b24  call    cs:__imp_GetDlgItem
0x180010b2a  lea     rcx, [rsp+910h+pcchLength]
0x180010b2f  xor     r9d, r9d
0x180010b32  mov     [rsp+910h+Ext], rcx; __int64
0x180010b37  xor     r8d, r8d
0x180010b3a  mov     dword ptr [rsp+910h+FilenameCount], r15d; int
0x180010b3f  xor     edx, edx
0x180010b41  mov     [rsp+910h+Filename], r15; __int64
0x180010b46  mov     rcx, rax; hWnd
0x180010b49  mov     dword ptr [rsp+910h+DirCount], r15d; int
0x180010b4e  call    DetermineSel2
0x180010b53  test    eax, eax
0x180010b55  jz      short loc_180010B6C
0x180010b57  mov     rcx, [rsp+910h+pcchLength]
0x180010b5c  mov     r8d, ebx
0x180010b5f  mov     rdx, rdi
0x180010b62  call    GetFileFromParam
0x180010b67  jmp     loc_180010CB2
0x180010b6c  mov     edx, r14d; nIDDlgItem
0x180010b6f  mov     rcx, rsi; hDlg
0x180010b72  call    cs:__imp_GetDlgItem
0x180010b78  mov     r8d, r12d; nMaxCount
0x180010b7b  lea     rdx, [rbp+810h+String]; lpString
0x180010b82  mov     rcx, rax; hWnd
0x180010b85  call    cs:__imp_GetWindowTextW
0x180010b8b  test    eax, eax
0x180010b8d  js      loc_180010CB0
0x180010b93  mov     [rsp+910h+ExtCount], r15; ExtCount
0x180010b98  lea     r9, [rbp+810h+Dir]; Dir
0x180010b9c  mov     [rsp+910h+Ext], r15; Ext
0x180010ba1  lea     rdx, [rbp+810h+Drive]; Drive
0x180010ba8  mov     [rsp+910h+FilenameCount], r15; FilenameCount
0x180010bad  lea     rcx, [rbp+810h+String]; FullPath
0x180010bb4  mov     [rsp+910h+Filename], r15; Filename
0x180010bb9  mov     r8, r12; DriveCount
0x180010bbc  mov     [rsp+910h+DirCount], r12; DirCount
0x180010bc1  call    cs:__imp__wsplitpath_s
0x180010bc7  dec     ebx
0x180010bc9  mov     [rdi], r15w
0x180010bcd  cmp     [rbp+810h+Drive], r15w
0x180010bd5  jnz     loc_180010C75
0x180010bdb  cmp     [rbp+810h+Dir], 5Ch ; '\'
0x180010be0  jz      loc_180010C75
0x180010be6  lea     rdx, [rbp+810h+Dir]
0x180010bea  mov     [rsp+910h+var_8B8], r15
0x180010bef  mov     rcx, rsi
0x180010bf2  call    GetBrowseParent
0x180010bf7  lea     rcx, [rbp+810h+Dir]
0x180010bfb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010bff  inc     rax
0x180010c02  cmp     [rcx+rax*2], r15w
0x180010c07  jnz     short loc_180010BFF
0x180010c09  lea     r8, [rsp+910h+pcchLength]; pcchLength
0x180010c0e  mov     [rsp+910h+pcchLength], rax
0x180010c13  lea     rcx, [rbp+810h+Dir]; psz
0x180010c17  call    StringLengthWorkerW
0x180010c1c  test    eax, eax
0x180010c1e  js      short loc_180010C75
0x180010c20  lea     r8, [rsp+910h+var_8B8]; pcchLength
0x180010c25  lea     rcx, [rbp+810h+String]; psz
0x180010c2c  call    StringLengthWorkerW
0x180010c31  test    eax, eax
0x180010c33  js      short loc_180010C75
0x180010c35  mov     r11, [rsp+910h+pcchLength]
0x180010c3a  mov     edx, ebx; cchDest
0x180010c3c  lea     rcx, [r11+1]
0x180010c40  add     rcx, [rsp+910h+var_8B8]
0x180010c45  cmp     rcx, rdx
0x180010c48  ja      short loc_180010C75
0x180010c4a  lea     r8, [rbp+810h+Dir]; pszSrc
0x180010c4e  mov     rcx, rdi; pszDest
0x180010c51  call    StringCchCopyW
0x180010c56  sub     ebx, r11d
0x180010c59  cmp     word ptr [rbp+r11*2+810h+var_890+0Eh], 5Ch ; '\'
0x180010c60  jz      short loc_180010C75
0x180010c62  mov     edx, ebx; cchDest
0x180010c64  lea     r8, SubBlock; "\\"
0x180010c6b  mov     rcx, rdi; pszDest
0x180010c6e  call    StringCchCatW
0x180010c73  dec     ebx
0x180010c75  mov     edx, ebx; cchDest
0x180010c77  lea     r8, [rbp+810h+String]; pszSrc
0x180010c7e  mov     rcx, rdi; pszDest
0x180010c81  call    StringCchCatW
0x180010c86  lea     rdx, [rsp+910h+var_8B0]
0x180010c8b  mov     rcx, rdi
0x180010c8e  call    cs:__imp__wstat
0x180010c94  test    eax, eax
0x180010c96  jnz     short loc_180010CB0
0x180010c98  movzx   eax, word ptr [rsp+910h+var_8B0+6]
0x180010c9d  mov     ecx, 8000h
0x180010ca2  and     ax, cx
0x180010ca5  neg     ax
0x180010ca8  sbb     eax, eax
0x180010caa  neg     eax
0x180010cac  inc     eax
0x180010cae  jmp     short loc_180010CB2
0x180010cb0  xor     eax, eax
0x180010cb2  mov     rcx, [rbp+810h+var_40]
0x180010cb9  xor     rcx, rsp; StackCookie
0x180010cbc  call    __security_check_cookie
0x180010cc1  add     rsp, 8E0h
0x180010cc8  pop     r15
0x180010cca  pop     r14
0x180010ccc  pop     r12
0x180010cce  pop     rdi
0x180010ccf  pop     rsi
0x180010cd0  pop     rbx
0x180010cd1  pop     rbp
0x180010cd2  retn
```
