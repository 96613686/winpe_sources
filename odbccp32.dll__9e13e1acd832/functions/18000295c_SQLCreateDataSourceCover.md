# SQLCreateDataSourceCover

- ea: `0x18000295c`
- end: `0x180002cd0`
- name: `SQLCreateDataSourceCover`
- size: `884`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x180002ce0`
- `0x180002d20`

## callees

- `0x180002368`
- `0x180002940`
- `0x18000295c`
- `0x180002e4c`
- `0x180002f80`
- `0x1800033bc`
- `0x180004bac`
- `0x180007c0c`
- `0x180011ec4`
- `0x180011f34`
- `0x1800131ac`
- `0x180013270`
- `0x180014ae0`

## import_xrefs

- `USER32!IsWindow` at `0x1800029b0`
- `USER32!IsWindow` at `0x1800029b0`
- `USER32!MessageBoxW` at `0x180002acb`
- `USER32!MessageBoxW` at `0x180002b3a`
- `USER32!MessageBoxW` at `0x180002acb`
- `USER32!MessageBoxW` at `0x180002b3a`
- `USER32!LoadStringW` at `0x180002a63`
- `USER32!LoadStringW` at `0x180002aae`
- `USER32!LoadStringW` at `0x180002b1c`
- `USER32!LoadStringW` at `0x180002a63`
- `USER32!LoadStringW` at `0x180002aae`
- `USER32!LoadStringW` at `0x180002b1c`

## pseudocode

```c
__int64 __fastcall SQLCreateDataSourceCover(__int64 a1)
{
  HWND v2; // rcx
  __int64 v3; // rcx
  int DataSourceUI; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // edi
  int v8; // ebx
  __int64 v9; // rcx
  __int16 v10; // r15
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // ecx
  wchar_t *v14; // r9
  __int64 v15; // r14
  __int64 v16; // rax
  unsigned __int64 v17; // r14
  bool v18; // zf
  HWND v19; // rcx
  __int64 v21[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h]
  void *v23; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Text[512]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR Buffer[512]; // [rsp+660h] [rbp+560h] BYREF

  v2 = *(HWND *)(a1 + 8);
  v22 = 0;
  *(_OWORD *)v21 = 0;
  if ( v2 && IsWindow(v2) )
  {
    v22 = 0;
    v21[0] = a1;
    if ( (AllocateConnStruct(v3, &v21[1]) & 0xFFFE) != 0 )
      return 0;
    *(_DWORD *)v21[1] = 2;
    DataSourceUI = CreateDataSourceUI(*(HWND *)(a1 + 8), v21);
    v7 = 1;
    v8 = DataSourceUI;
    if ( (_DWORD)v22 )
      goto LABEL_32;
    if ( !DataSourceUI )
      goto LABEL_34;
    v9 = v21[0];
    if ( (unsigned int)(*(_DWORD *)(v21[0] + 16) - 2) > 1 )
    {
      if ( (*(_BYTE *)(v21[0] + 24) & 1) == 0 )
      {
        if ( (SaveConnStructToFileDSN(*(HWND *)(a1 + 8), v5, v6, *(const wchar_t **)(v21[1] + 16), (_QWORD *)v21[1])
            & 0xFFFE) != 0 )
        {
LABEL_12:
          v13 = 18;
LABEL_33:
          PostInstError(v13);
          v8 = 0;
          goto LABEL_34;
        }
        goto LABEL_34;
      }
      v23 = 0;
      if ( (BuildConnStringFromConnStruct(v21[0], v21[1], &v23) & 0xFFFE) != 0 )
        goto LABEL_34;
      LoadStringW(g_hResDLL, 0x58Au, Buffer, 512);
      v10 = VerifyFileDSN(*(HWND *)(a1 + 8));
      OFree(v23);
      if ( v10 == -1 )
      {
        LoadStringW(g_hResDLL, 0x589u, Text, 512);
        if ( MessageBoxW(*(HWND *)(a1 + 8), Text, Buffer, 0x34u) != 6
          || (SaveConnStructToFileDSN(*(HWND *)(a1 + 8), v11, v12, *(const wchar_t **)(v21[1] + 16), (_QWORD *)v21[1])
            & 0xFFFE) != 0 )
        {
          goto LABEL_12;
        }
        goto LABEL_17;
      }
      if ( v10 == 1 )
      {
        LoadStringW(g_hResDLL, 0x595u, Text, 512);
        MessageBoxW(*(HWND *)(a1 + 8), Text, Buffer, 0x30u);
        v8 = 0;
        PostInstError(18);
        goto LABEL_34;
      }
      if ( v10 != 100 )
      {
        if ( !v10 )
LABEL_17:
          v8 = 1;
LABEL_34:
        ReleaseConnStruct(v21[1]);
        if ( v8 && !(_DWORD)v22 )
          return v7;
        return 0;
      }
LABEL_32:
      v13 = 16;
      goto LABEL_33;
    }
    if ( !*(_WORD *)(v21[0] + 28) )
    {
      v14 = (wchar_t *)&szAttributes;
LABEL_30:
      v18 = *(_DWORD *)(v9 + 16) == 2;
      v19 = *(HWND *)(a1 + 8);
      g_wSystemDSN = v18 + 1;
      v8 = ConfigDataSourceW(v19, 1u, *(const wchar_t **)(v21[1] + 32), (__int64)v14);
      g_wSystemDSN = 4;
      goto LABEL_34;
    }
    v15 = -1;
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)(v21[0] + 28 + 2 * v16) );
    if ( (unsigned __int64)(v16 + 4) <= 0x103 )
    {
      StringCchPrintfW(pszDest, 0x105u, L"%s%s", L"DSN=", v21[0] + 28);
      do
        ++v15;
      while ( pszDest[v15] );
      v17 = 2 * v15 + 2;
      if ( v17 >= 0x20A )
        _report_rangecheckfailure();
      v9 = v21[0];
      v14 = pszDest;
      *(wchar_t *)((char *)pszDest + v17) = 0;
      goto LABEL_30;
    }
    PostInstError(7);
    ReleaseConnStruct(v21[1]);
  }
  else
  {
    PostInstError(3);
  }
  return 0;
}

```

## disassembly

```asm
0x18000295c  mov     [rsp-8+arg_8], rbx
0x180002961  mov     [rsp-8+arg_10], rsi
0x180002966  push    rbp
0x180002967  push    rdi
0x180002968  push    r12
0x18000296a  push    r14
0x18000296c  push    r15
0x18000296e  lea     rbp, [rsp-970h]
0x180002976  sub     rsp, 0A70h
0x18000297d  mov     rax, cs:__security_cookie
0x180002984  xor     rax, rsp
0x180002987  mov     [rbp+990h+var_30], rax
0x18000298e  xor     eax, eax
0x180002990  mov     rsi, rcx
0x180002993  mov     rcx, [rcx+8]; hWnd
0x180002997  xor     r12d, r12d
0x18000299a  mov     [rsp+0A90h+var_A50], rax
0x18000299f  xorps   xmm0, xmm0
0x1800029a2  movups  xmmword ptr [rsp+0A90h+var_A60], xmm0
0x1800029a7  test    rcx, rcx
0x1800029aa  jz      loc_180002C99
0x1800029b0  call    cs:__imp_IsWindow
0x1800029b6  test    eax, eax
0x1800029b8  jz      loc_180002C99
0x1800029be  lea     rdx, [rsp+0A90h+var_A60+8]
0x1800029c3  mov     [rsp+0A90h+var_A50], r12
0x1800029c8  mov     [rsp+0A90h+var_A60], rsi
0x1800029cd  call    AllocateConnStruct
0x1800029d2  test    ax, 0FFFEh
0x1800029d6  jnz     loc_180002C92
0x1800029dc  mov     rax, [rsp+0A90h+var_A60+8]
0x1800029e1  lea     rdx, [rsp+0A90h+var_A60]
0x1800029e6  mov     dword ptr [rax], 2
0x1800029ec  mov     rcx, [rsi+8]
0x1800029f0  call    CreateDataSourceUI
0x1800029f5  lea     edi, [r12+1]
0x1800029fa  mov     ebx, eax
0x1800029fc  cmp     dword ptr [rsp+0A90h+var_A50], r12d
0x180002a01  jnz     loc_180002C70
0x180002a07  test    eax, eax
0x180002a09  jz      loc_180002C7D
0x180002a0f  mov     rcx, [rsp+0A90h+var_A60]
0x180002a14  mov     eax, [rcx+10h]
0x180002a17  sub     eax, 2
0x180002a1a  cmp     eax, edi
0x180002a1c  jbe     loc_180002B94
0x180002a22  test    [rcx+18h], dil
0x180002a26  jz      loc_180002B6E
0x180002a2c  mov     rdx, [rsp+0A90h+var_A60+8]
0x180002a31  lea     r8, [rsp+0A90h+var_A48]
0x180002a36  mov     [rsp+0A90h+var_A48], r12
0x180002a3b  call    BuildConnStringFromConnStruct
0x180002a40  test    ax, 0FFFEh
0x180002a44  jnz     loc_180002C7D
0x180002a4a  mov     rcx, cs:g_hResDLL; hInstance
0x180002a51  lea     r8, [rbp+990h+Buffer]; lpBuffer
0x180002a58  mov     r9d, 200h; cchBufferMax
0x180002a5e  mov     edx, 58Ah; uID
0x180002a63  call    cs:__imp_LoadStringW
0x180002a69  mov     rdx, [rsp+0A90h+var_A48]
0x180002a6e  xor     r9d, r9d
0x180002a71  mov     rcx, [rsi+8]; hWnd
0x180002a75  mov     r8d, edi
0x180002a78  call    VerifyFileDSN
0x180002a7d  mov     rcx, [rsp+0A90h+var_A48]
0x180002a82  movzx   r15d, ax
0x180002a86  call    OFree
0x180002a8b  or      r14, 0FFFFFFFFFFFFFFFFh
0x180002a8f  cmp     r15w, r14w
0x180002a93  jnz     short loc_180002AFD
0x180002a95  mov     rcx, cs:g_hResDLL; hInstance
0x180002a9c  lea     r8, [rbp+990h+Text]; lpBuffer
0x180002aa3  mov     r9d, 200h; cchBufferMax
0x180002aa9  mov     edx, 589h; uID
0x180002aae  call    cs:__imp_LoadStringW
0x180002ab4  mov     rcx, [rsi+8]; hWnd
0x180002ab8  lea     r9d, [r12+34h]; uType
0x180002abd  lea     r8, [rbp+990h+Buffer]; lpCaption
0x180002ac4  lea     rdx, [rbp+990h+Text]; lpText
0x180002acb  call    cs:__imp_MessageBoxW
0x180002ad1  cmp     eax, 6
0x180002ad4  jnz     short loc_180002AF3
0x180002ad6  mov     r9, [rsp+0A90h+var_A60+8]
0x180002adb  mov     rcx, [rsi+8]; hWnd
0x180002adf  mov     [rsp+0A90h+var_A70], r9; __int64
0x180002ae4  mov     r9, [r9+10h]
0x180002ae8  call    SaveConnStructToFileDSN
0x180002aed  test    ax, 0FFFEh
0x180002af1  jz      short loc_180002B67
0x180002af3  mov     ecx, 12h
0x180002af8  jmp     loc_180002C75
0x180002afd  cmp     r15w, di
0x180002b01  jnz     short loc_180002B52
0x180002b03  mov     rcx, cs:g_hResDLL; hInstance
0x180002b0a  lea     r8, [rbp+990h+Text]; lpBuffer
0x180002b11  mov     r9d, 200h; cchBufferMax
0x180002b17  mov     edx, 595h; uID
0x180002b1c  call    cs:__imp_LoadStringW
0x180002b22  mov     rcx, [rsi+8]; hWnd
0x180002b26  lea     r8, [rbp+990h+Buffer]; lpCaption
0x180002b2d  mov     r9d, 30h ; '0'; uType
0x180002b33  lea     rdx, [rbp+990h+Text]; lpText
0x180002b3a  call    cs:__imp_MessageBoxW
0x180002b40  mov     ecx, 12h
0x180002b45  mov     ebx, r12d
0x180002b48  call    PostInstError
0x180002b4d  jmp     loc_180002C7D
0x180002b52  cmp     r15w, 64h ; 'd'
0x180002b57  jz      loc_180002C70
0x180002b5d  test    r15w, r15w
0x180002b61  jnz     loc_180002C7D
0x180002b67  mov     ebx, edi
0x180002b69  jmp     loc_180002C7D
0x180002b6e  mov     r9, [rsp+0A90h+var_A60+8]
0x180002b73  mov     rcx, [rsi+8]; hWnd
0x180002b77  mov     [rsp+0A90h+var_A70], r9; __int64
0x180002b7c  mov     r9, [r9+10h]
0x180002b80  call    SaveConnStructToFileDSN
0x180002b85  test    ax, 0FFFEh
0x180002b89  jz      loc_180002C7D
0x180002b8f  jmp     loc_180002AF3
0x180002b94  lea     rdx, [rcx+1Ch]
0x180002b98  cmp     [rdx], r12w
0x180002b9c  jnz     short loc_180002BAA
0x180002b9e  lea     r9, szAttributes
0x180002ba5  jmp     loc_180002C32
0x180002baa  or      r14, 0FFFFFFFFFFFFFFFFh
0x180002bae  mov     rax, r14
0x180002bb1  inc     rax
0x180002bb4  cmp     [rdx+rax*2], r12w
0x180002bb9  jnz     short loc_180002BB1
0x180002bbb  add     rax, 4
0x180002bbf  cmp     rax, 103h
0x180002bc5  jbe     short loc_180002BE0
0x180002bc7  mov     ecx, 7
0x180002bcc  call    PostInstError
0x180002bd1  mov     rcx, [rsp+0A90h+var_A60+8]
0x180002bd6  call    ReleaseConnStruct
0x180002bdb  jmp     loc_180002CA3
0x180002be0  mov     [rsp+0A90h+var_A70], rdx
0x180002be5  lea     r9, aDsn_0; "DSN="
0x180002bec  mov     edx, 105h; cchDest
0x180002bf1  lea     r8, aSS_1; "%s%s"
0x180002bf8  lea     rcx, [rsp+0A90h+pszDest]; pszDest
0x180002bfd  call    StringCchPrintfW
0x180002c02  lea     rax, [rsp+0A90h+pszDest]
0x180002c07  inc     r14
0x180002c0a  cmp     [rax+r14*2], r12w
0x180002c0f  jnz     short loc_180002C07
0x180002c11  lea     r14, ds:2[r14*2]
0x180002c19  cmp     r14, 20Ah
0x180002c20  jnb     short loc_180002C6A
0x180002c22  mov     rcx, [rsp+0A90h+var_A60]
0x180002c27  lea     r9, [rsp+0A90h+pszDest]
0x180002c2c  mov     [rsp+r14+0A90h+pszDest], r12w
0x180002c32  cmp     dword ptr [rcx+10h], 2
0x180002c36  mov     eax, r12d
0x180002c39  mov     r8, [rsp+0A90h+var_A60+8]
0x180002c3e  mov     edx, edi
0x180002c40  mov     rcx, [rsi+8]; hWnd
0x180002c44  setz    al
0x180002c47  add     ax, di
0x180002c4a  mov     cs:g_wSystemDSN, ax
0x180002c51  mov     r8, [r8+20h]
0x180002c55  call    ConfigDataSourceW
0x180002c5a  mov     ebx, eax
0x180002c5c  mov     eax, 4
0x180002c61  mov     cs:g_wSystemDSN, ax
0x180002c68  jmp     short loc_180002C7D
0x180002c6a  call    __report_rangecheckfailure
0x180002c70  mov     ecx, 10h
0x180002c75  call    PostInstError
0x180002c7a  mov     ebx, r12d
0x180002c7d  mov     rcx, [rsp+0A90h+var_A60+8]
0x180002c82  call    ReleaseConnStruct
0x180002c87  test    ebx, ebx
0x180002c89  jz      short loc_180002C92
0x180002c8b  cmp     dword ptr [rsp+0A90h+var_A50], r12d
0x180002c90  jz      short loc_180002C95
0x180002c92  mov     edi, r12d
0x180002c95  mov     eax, edi
0x180002c97  jmp     short loc_180002CA5
0x180002c99  mov     ecx, 3
0x180002c9e  call    PostInstError
0x180002ca3  xor     eax, eax
0x180002ca5  mov     rcx, [rbp+990h+var_30]
0x180002cac  xor     rcx, rsp; StackCookie
0x180002caf  call    __security_check_cookie
0x180002cb4  lea     r11, [rsp+0A90h+var_20]
0x180002cbc  mov     rbx, [r11+38h]
0x180002cc0  mov     rsi, [r11+40h]
0x180002cc4  mov     rsp, r11
0x180002cc7  pop     r15
0x180002cc9  pop     r14
0x180002ccb  pop     r12
0x180002ccd  pop     rdi
0x180002cce  pop     rbp
0x180002ccf  retn
```
