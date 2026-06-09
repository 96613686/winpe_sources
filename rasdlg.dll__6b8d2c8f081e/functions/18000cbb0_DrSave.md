# DrSave

- ea: `0x18000cbb0`
- end: `0x18000cfa7`
- name: `DrSave`
- size: `1015`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18000b07c`
- `0x18000c9c8`

## callees

- `0x180007528`
- `0x18000c55c`
- `0x18000cbb0`
- `0x18000cfb0`
- `0x18000d1ac`
- `0x18000ef98`
- `0x18003ce6c`
- `0x18003d184`
- `0x180048b6c`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `msvcrt!wcspbrk` at `0x18000cc9f`
- `msvcrt!wcspbrk` at `0x18000cc9f`
- `RASAPI32!WritePhonebookFile` at `0x18000cf4e`
- `RASAPI32!WritePhonebookFile` at `0x18000cf4e`
- `USER32!GetWindowTextW` at `0x18000cc3b`
- `USER32!GetWindowTextW` at `0x18000cc76`
- `USER32!GetWindowTextW` at `0x18000ccd2`
- `USER32!GetWindowTextW` at `0x18000cc3b`
- `USER32!GetWindowTextW` at `0x18000cc76`
- `USER32!GetWindowTextW` at `0x18000ccd2`
- `USER32!SendMessageW` at `0x18000cded`
- `USER32!SendMessageW` at `0x18000ce0c`
- `USER32!SendMessageW` at `0x18000cded`
- `USER32!SendMessageW` at `0x18000ce0c`
- `USER32!SetWindowTextW` at `0x18000cc87`
- `USER32!SetWindowTextW` at `0x18000cc87`

## pseudocode

```c
__int64 __fastcall DrSave(__int64 a1)
{
  __int64 v2; // rbx
  const wchar_t *v3; // r14
  const wchar_t *v4; // rsi
  __int64 v5; // rcx
  HWND v6; // rcx
  int v7; // esi
  int v8; // ecx
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  wchar_t *v13; // rax
  __int64 result; // rax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+44h] [rbp-BCh] BYREF
  wchar_t v18[257]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t v19[257]; // [rsp+24Ah] [rbp+14Ah] BYREF
  wchar_t v20[18]; // [rsp+44Ch] [rbp+34Ch] BYREF

  memset_0(&v16, 0, 0x42Cu);
  v2 = **(_QWORD **)a1;
  if ( (*(_BYTE *)(*(_QWORD *)a1 + 8LL) & 1) != 0 )
  {
    v3 = (const wchar_t *)(v2 + 1522);
    GetWindowTextW(*(HWND *)(a1 + 16), (LPWSTR)(v2 + 1522), 257);
    v4 = (const wchar_t *)(v2 + 2036);
    if ( (unsigned int)DrIsPasswordStyleEnabled(*(_QWORD *)(a1 + 24)) )
      GetWindowTextW(*(HWND *)(a1 + 24), (LPWSTR)(v2 + 2036), 257);
    else
      StringCchCopyWrapW((wchar_t *)(v2 + 2036), 0x11u, L"****************");
    SetWindowTextW(*(HWND *)(a1 + 24), &WideCharStr);
    EncodePasswordW(v2 + 2036);
    if ( wcspbrk((const wchar_t *)(v2 + 1522), L"@\\") )
    {
      *(_OWORD *)(v2 + 2550) = 0;
      *(_OWORD *)(v2 + 2566) = 0;
    }
  }
  else
  {
    if ( (*(_BYTE *)(*(_QWORD *)a1 + 8LL) & 0x10) == 0 )
      goto LABEL_32;
    v3 = (const wchar_t *)(v2 + 1522);
    v4 = (const wchar_t *)(v2 + 2036);
  }
  if ( (*(_BYTE *)(*(_QWORD *)a1 + 8LL) & 2) != 0 )
    GetWindowTextW(*(HWND *)(a1 + 32), (LPWSTR)(v2 + 2550), 16);
  memset_0(&v17, 0, 0x428u);
  v16 = 1068;
  StringCchCopyWrapW(v18, 0x101u, v3);
  EncodePasswordW(v4);
  StringCchCopyWrapW(v19, 0x101u, v4);
  EncodePasswordW(v4);
  StringCchCopyWrapW(v20, 0x10u, (const wchar_t *)(v2 + 2550));
  v5 = *(_QWORD *)(v2 + 376);
  if ( v5 && *(_QWORD *)(v2 + 384) )
  {
    StringCchCopyWrapW((wchar_t *)(v5 + 12), 0x101u, v18);
    StringCchCopyWrapW((wchar_t *)(*(_QWORD *)(v2 + 376) + 526LL), 0x101u, v19);
    EncodePasswordW(*(_QWORD *)(v2 + 376) + 526LL);
    StringCchCopyWrapW((wchar_t *)(*(_QWORD *)(v2 + 376) + 1040LL), 0x10u, v20);
    **(_DWORD **)(v2 + 384) = 1;
  }
  else if ( (*(_BYTE *)(*(_QWORD *)a1 + 8LL) & 0x10) == 0 && !*(_DWORD *)(v2 + 456) )
  {
    if ( (unsigned int)SendMessageW(*(HWND *)(a1 + 40), 0xF0u, 0, 0) )
    {
      v6 = *(HWND *)(a1 + 56);
      v17 = 0;
      v7 = SendMessageW(v6, 0xF0u, 0, 0);
      if ( v7 && *(_DWORD *)(a1 + 224) )
      {
        DeleteSavedCredentials(v2, *(HWND *)(a1 + 8), 0, 0);
        v8 = 8;
        *(_DWORD *)(v2 + 460) = 0;
      }
      else
      {
        v8 = v17;
      }
      v9 = *(_QWORD *)(a1 + 232);
      v10 = *(_QWORD *)(a1 + 8);
      v17 = v8 | 7;
      if ( !(unsigned int)SaveCredentials(v2, v10, &v16, v9) )
      {
        if ( v7 )
        {
          *(_DWORD *)(v2 + 464) = 1;
          v11 = *(_QWORD *)(a1 + 232);
          if ( v11 )
          {
            *(_QWORD *)(v2 + 368) = v11;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
          }
        }
        else
        {
          *(_DWORD *)(v2 + 460) = 1;
        }
      }
    }
    else
    {
      if ( *(_DWORD *)(**(_QWORD **)a1 + 360LL) && *(_DWORD *)(a1 + 224) )
      {
        DeleteSavedCredentials(v2, *(HWND *)(a1 + 8), 0, 1);
        *(_DWORD *)(v2 + 464) = 0;
      }
      DeleteSavedCredentials(v2, *(HWND *)(a1 + 8), 0, 0);
      *(_DWORD *)(v2 + 460) = 0;
    }
  }
  v12 = 514;
  v13 = v19;
  do
  {
    *(_BYTE *)v13 = 0;
    v13 = (wchar_t *)((char *)v13 + 1);
    --v12;
  }
  while ( v12 );
LABEL_32:
  if ( (*(_BYTE *)(*(_QWORD *)a1 + 8LL) & 4) != 0 )
  {
    if ( *(_DWORD *)(*(_QWORD *)(v2 + 440) + 548LL) )
      DrSaveVPNDestinationPreference(a1);
    else
      DrSavePhoneNumber(a1, v2);
  }
  result = *(_QWORD *)(v2 + 440);
  if ( *(_DWORD *)(result + 532) )
  {
    result = WritePhonebookFile(*(_QWORD *)(v2 + 32), 0);
    if ( (_DWORD)result )
      return ErrorDlgUtil(*(HWND *)(a1 + 8), 0x158u, result, v15, 0x169u, 0xFAu);
  }
  return result;
}

```

## disassembly

```asm
0x18000cbb0  mov     [rsp-8+arg_8], rbx
0x18000cbb5  mov     [rsp-8+arg_10], rsi
0x18000cbba  push    rbp
0x18000cbbb  push    rdi
0x18000cbbc  push    r13
0x18000cbbe  push    r14
0x18000cbc0  push    r15
0x18000cbc2  lea     rbp, [rsp-380h]
0x18000cbca  sub     rsp, 480h
0x18000cbd1  mov     rax, cs:__security_cookie
0x18000cbd8  xor     rax, rsp
0x18000cbdb  mov     [rbp+3A0h+var_30], rax
0x18000cbe2  mov     rdi, rcx
0x18000cbe5  xor     edx, edx; Val
0x18000cbe7  lea     rcx, [rsp+4A0h+var_460]; void *
0x18000cbec  mov     r8d, 42Ch; Size
0x18000cbf2  call    memset_0
0x18000cbf7  mov     rax, [rdi]
0x18000cbfa  xor     r15d, r15d
0x18000cbfd  test    byte ptr [rax+8], 1
0x18000cc01  lea     r13d, [r15+10h]
0x18000cc05  mov     rbx, [rax]
0x18000cc08  jnz     short loc_18000CC27
0x18000cc0a  test    [rax+8], r13b
0x18000cc0e  jz      loc_18000CF0D
0x18000cc14  lea     r14, [rbx+5F2h]
0x18000cc1b  lea     rsi, [rbx+7F4h]
0x18000cc22  jmp     loc_18000CCBB
0x18000cc27  mov     rcx, [rdi+10h]; hWnd
0x18000cc2b  lea     r14, [rbx+5F2h]
0x18000cc32  mov     rdx, r14; lpString
0x18000cc35  mov     r8d, 101h; nMaxCount
0x18000cc3b  call    cs:__imp_GetWindowTextW
0x18000cc41  mov     rcx, [rdi+18h]
0x18000cc45  lea     rsi, [rbx+7F4h]
0x18000cc4c  call    DrIsPasswordStyleEnabled
0x18000cc51  test    eax, eax
0x18000cc53  jnz     short loc_18000CC69
0x18000cc55  lea     r8, g_pszSavedPasswordToken; "****************"
0x18000cc5c  mov     rcx, rsi
0x18000cc5f  lea     edx, [rax+11h]
0x18000cc62  call    StringCchCopyWrapW
0x18000cc67  jmp     short loc_18000CC7C
0x18000cc69  mov     rcx, [rdi+18h]; hWnd
0x18000cc6d  mov     r8d, 101h; nMaxCount
0x18000cc73  mov     rdx, rsi; lpString
0x18000cc76  call    cs:__imp_GetWindowTextW
0x18000cc7c  mov     rcx, [rdi+18h]; hWnd
0x18000cc80  lea     rdx, WideCharStr; lpString
0x18000cc87  call    cs:__imp_SetWindowTextW
0x18000cc8d  mov     rcx, rsi
0x18000cc90  call    EncodePasswordW
0x18000cc95  lea     rdx, Control; "@\\"
0x18000cc9c  mov     rcx, r14; String
0x18000cc9f  call    cs:__imp_wcspbrk
0x18000cca5  test    rax, rax
0x18000cca8  jz      short loc_18000CCBB
0x18000ccaa  xorps   xmm0, xmm0
0x18000ccad  movups  xmmword ptr [rbx+9F6h], xmm0
0x18000ccb4  movups  xmmword ptr [rbx+0A06h], xmm0
0x18000ccbb  mov     rax, [rdi]
0x18000ccbe  test    byte ptr [rax+8], 2
0x18000ccc2  jz      short loc_18000CCD8
0x18000ccc4  mov     rcx, [rdi+20h]; hWnd
0x18000ccc8  lea     rdx, [rbx+9F6h]; lpString
0x18000cccf  mov     r8d, r13d; nMaxCount
0x18000ccd2  call    cs:__imp_GetWindowTextW
0x18000ccd8  xor     edx, edx; Val
0x18000ccda  lea     rcx, [rsp+4A0h+var_45C]; void *
0x18000ccdf  mov     r8d, 428h; Size
0x18000cce5  call    memset_0
0x18000ccea  mov     r8, r14
0x18000cced  mov     [rsp+4A0h+var_460], 42Ch
0x18000ccf5  mov     r14d, 101h
0x18000ccfb  lea     rcx, [rsp+4A0h+var_458]
0x18000cd00  mov     edx, r14d
0x18000cd03  call    StringCchCopyWrapW
0x18000cd08  mov     rcx, rsi
0x18000cd0b  call    EncodePasswordW
0x18000cd10  mov     r8, rsi
0x18000cd13  lea     rcx, [rbp+3A0h+var_256]
0x18000cd1a  mov     edx, r14d
0x18000cd1d  call    StringCchCopyWrapW
0x18000cd22  mov     rcx, rsi
0x18000cd25  call    EncodePasswordW
0x18000cd2a  lea     r8, [rbx+9F6h]
0x18000cd31  mov     rdx, r13
0x18000cd34  lea     rcx, [rbp+3A0h+var_54]
0x18000cd3b  call    StringCchCopyWrapW
0x18000cd40  mov     rcx, [rbx+178h]
0x18000cd47  test    rcx, rcx
0x18000cd4a  jz      short loc_18000CDC2
0x18000cd4c  cmp     [rbx+180h], r15
0x18000cd53  jz      short loc_18000CDC2
0x18000cd55  add     rcx, 0Ch
0x18000cd59  lea     r8, [rsp+4A0h+var_458]
0x18000cd5e  mov     edx, r14d
0x18000cd61  call    StringCchCopyWrapW
0x18000cd66  mov     rcx, [rbx+178h]
0x18000cd6d  lea     r8, [rbp+3A0h+var_256]
0x18000cd74  mov     esi, 20Eh
0x18000cd79  mov     edx, r14d
0x18000cd7c  add     rcx, rsi
0x18000cd7f  call    StringCchCopyWrapW
0x18000cd84  mov     rcx, [rbx+178h]
0x18000cd8b  add     rcx, rsi
0x18000cd8e  call    EncodePasswordW
0x18000cd93  mov     rcx, [rbx+178h]
0x18000cd9a  lea     r8, [rbp+3A0h+var_54]
0x18000cda1  add     rcx, 410h
0x18000cda8  mov     rdx, r13
0x18000cdab  call    StringCchCopyWrapW
0x18000cdb0  mov     rax, [rbx+180h]
0x18000cdb7  mov     dword ptr [rax], 1
0x18000cdbd  jmp     loc_18000CEF5
0x18000cdc2  mov     rax, [rdi]
0x18000cdc5  test    [rax+8], r13b
0x18000cdc9  jnz     loc_18000CEF5
0x18000cdcf  cmp     [rbx+1C8h], r15d
0x18000cdd6  jnz     loc_18000CEF5
0x18000cddc  mov     rcx, [rdi+28h]; hWnd
0x18000cde0  mov     esi, 0F0h
0x18000cde5  mov     edx, esi; Msg
0x18000cde7  xor     r9d, r9d; lParam
0x18000cdea  xor     r8d, r8d; wParam
0x18000cded  call    cs:__imp_SendMessageW
0x18000cdf3  test    eax, eax
0x18000cdf5  jz      loc_18000CEA8
0x18000cdfb  mov     rcx, [rdi+38h]; hWnd
0x18000cdff  xor     r9d, r9d; lParam
0x18000ce02  xor     r8d, r8d; wParam
0x18000ce05  mov     [rsp+4A0h+var_45C], r15d
0x18000ce0a  mov     edx, esi; Msg
0x18000ce0c  call    cs:__imp_SendMessageW
0x18000ce12  mov     rsi, rax
0x18000ce15  test    eax, eax
0x18000ce17  jz      short loc_18000CE42
0x18000ce19  cmp     [rdi+0E0h], r15d
0x18000ce20  jz      short loc_18000CE42
0x18000ce22  mov     rdx, [rdi+8]
0x18000ce26  xor     r9d, r9d
0x18000ce29  xor     r8d, r8d
0x18000ce2c  mov     rcx, rbx
0x18000ce2f  call    DeleteSavedCredentials
0x18000ce34  mov     ecx, 8
0x18000ce39  mov     [rbx+1CCh], r15d
0x18000ce40  jmp     short loc_18000CE46
0x18000ce42  mov     ecx, [rsp+4A0h+var_45C]
0x18000ce46  mov     r9, [rdi+0E8h]
0x18000ce4d  lea     r8, [rsp+4A0h+var_460]
0x18000ce52  mov     rdx, [rdi+8]
0x18000ce56  or      ecx, 7
0x18000ce59  mov     [rsp+4A0h+var_45C], ecx
0x18000ce5d  mov     rcx, rbx
0x18000ce60  call    SaveCredentials
0x18000ce65  test    eax, eax
0x18000ce67  jnz     loc_18000CEF5
0x18000ce6d  test    esi, esi
0x18000ce6f  jz      short loc_18000CE9C
0x18000ce71  mov     dword ptr [rbx+1D0h], 1
0x18000ce7b  mov     rcx, [rdi+0E8h]
0x18000ce82  test    rcx, rcx
0x18000ce85  jz      short loc_18000CEF5
0x18000ce87  mov     [rbx+170h], rcx
0x18000ce8e  mov     rax, [rcx]
0x18000ce91  mov     rax, [rax+8]
0x18000ce95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce9a  jmp     short loc_18000CEF5
0x18000ce9c  mov     dword ptr [rbx+1CCh], 1
0x18000cea6  jmp     short loc_18000CEF5
0x18000cea8  mov     rax, [rdi]
0x18000ceab  mov     rcx, [rax]
0x18000ceae  cmp     [rcx+168h], r15d
0x18000ceb5  jz      short loc_18000CEDC
0x18000ceb7  cmp     [rdi+0E0h], r15d
0x18000cebe  jz      short loc_18000CEDC
0x18000cec0  mov     rdx, [rdi+8]
0x18000cec4  mov     r9d, 1
0x18000ceca  xor     r8d, r8d
0x18000cecd  mov     rcx, rbx
0x18000ced0  call    DeleteSavedCredentials
0x18000ced5  mov     [rbx+1D0h], r15d
0x18000cedc  mov     rdx, [rdi+8]
0x18000cee0  xor     r9d, r9d
0x18000cee3  xor     r8d, r8d
0x18000cee6  mov     rcx, rbx
0x18000cee9  call    DeleteSavedCredentials
0x18000ceee  mov     [rbx+1CCh], r15d
0x18000cef5  mov     ecx, 202h
0x18000cefa  lea     rax, [rbp+3A0h+var_256]
0x18000cf01  mov     [rax], r15b
0x18000cf04  inc     rax
0x18000cf07  sub     rcx, 1
0x18000cf0b  jnz     short loc_18000CF01
0x18000cf0d  mov     rax, [rdi]
0x18000cf10  test    byte ptr [rax+8], 4
0x18000cf14  jz      short loc_18000CF38
0x18000cf16  mov     rax, [rbx+1B8h]
0x18000cf1d  mov     rcx, rdi
0x18000cf20  cmp     [rax+224h], r15d
0x18000cf27  jz      short loc_18000CF30
0x18000cf29  call    DrSaveVPNDestinationPreference
0x18000cf2e  jmp     short loc_18000CF38
0x18000cf30  mov     rdx, rbx
0x18000cf33  call    DrSavePhoneNumber
0x18000cf38  mov     rax, [rbx+1B8h]
0x18000cf3f  cmp     [rax+214h], r15d
0x18000cf46  jz      short loc_18000CF7C
0x18000cf48  mov     rcx, [rbx+20h]
0x18000cf4c  xor     edx, edx
0x18000cf4e  call    cs:__imp_WritePhonebookFile
0x18000cf54  test    eax, eax
0x18000cf56  jz      short loc_18000CF7C
0x18000cf58  mov     rcx, [rdi+8]; hWnd
0x18000cf5c  xor     r9d, r9d
0x18000cf5f  mov     [rsp+4A0h+var_470], 0FAh; UINT
0x18000cf67  mov     r8d, eax; dwMessageId
0x18000cf6a  mov     edx, 158h; uID
0x18000cf6f  mov     [rsp+4A0h+var_478], 169h; UINT
0x18000cf77  call    ErrorDlgUtil
0x18000cf7c  mov     rcx, [rbp+3A0h+var_30]
0x18000cf83  xor     rcx, rsp; StackCookie
0x18000cf86  call    __security_check_cookie
0x18000cf8b  lea     r11, [rsp+4A0h+var_20]
0x18000cf93  mov     rbx, [r11+38h]
0x18000cf97  mov     rsi, [r11+40h]
0x18000cf9b  mov     rsp, r11
0x18000cf9e  pop     r15
0x18000cfa0  pop     r14
0x18000cfa2  pop     r13
0x18000cfa4  pop     rdi
0x18000cfa5  pop     rbp
0x18000cfa6  retn
```
