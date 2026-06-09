# NgscbpFindVendorDeviceHwID

- ea: `0x18003a78c`
- end: `0x18003a9a2`
- name: `NgscbpFindVendorDeviceHwID`
- size: `534`
- prototype: `__int64 __fastcall(wchar_t *Str)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002c9c4`

## callees

- `0x1800090c0`
- `0x18003a78c`

## import_xrefs

- `msvcrt!wcschr` at `0x18003a828`
- `msvcrt!wcschr` at `0x18003a83e`
- `msvcrt!wcschr` at `0x18003a883`
- `msvcrt!wcschr` at `0x18003a896`
- `msvcrt!wcschr` at `0x18003a828`
- `msvcrt!wcschr` at `0x18003a83e`
- `msvcrt!wcschr` at `0x18003a883`
- `msvcrt!wcschr` at `0x18003a896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a92f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a92f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003a80a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003a865`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003a80a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003a865`

## pseudocode

```c
__int64 __fastcall NgscbpFindVendorDeviceHwID(wchar_t *Str, wchar_t **a2)
{
  wchar_t *v3; // rdi
  unsigned __int64 v4; // rax
  __int64 v5; // rax
  int v6; // eax
  wchar_t *v7; // rax
  int v8; // eax
  wchar_t *v9; // rax
  unsigned int v10; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  signed int LastError; // eax
  signed int v15; // eax

  v3 = Str;
  if ( a2 )
    *a2 = 0;
  if ( !Str )
  {
    v10 = -2147024809;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return v10;
    v13 = 254;
LABEL_28:
    WPP_SF_d(v12[2], v13, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v10);
    return v10;
  }
  if ( !a2 )
  {
    v10 = -2147467261;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return v10;
    v13 = 255;
    goto LABEL_28;
  }
  while ( 1 )
  {
    if ( !*v3 )
    {
LABEL_18:
      v10 = 0;
      *a2 = v3;
      return v10;
    }
    v4 = -1;
    do
      ++v4;
    while ( v3[v4] );
    if ( v4 < 8 )
      goto LABEL_9;
    v6 = CompareStringOrdinal(v3, 8, L"PCI\\VEN_", 8, 1);
    if ( !v6 )
      break;
    if ( v6 == 2 && wcschr(v3, 0x26u) )
    {
      v7 = wcschr(v3, 0x26u);
      v8 = CompareStringOrdinal(v7, 5, L"&DEV_", 5, 1);
      if ( !v8 )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v13 = 257;
          goto LABEL_28;
        }
        return v10;
      }
      if ( v8 == 2 )
      {
        v9 = wcschr(v3, 0x26u);
        if ( !wcschr(v9 + 1, 0x26u) )
          goto LABEL_18;
      }
    }
LABEL_9:
    v5 = -1;
    do
      ++v5;
    while ( v3[v5] );
    v3 += v5 + 1;
  }
  v15 = GetLastError();
  v10 = v15;
  if ( v15 > 0 )
    v10 = (unsigned __int16)v15 | 0x80070000;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v13 = 256;
    goto LABEL_28;
  }
  return v10;
}

```

## disassembly

```asm
0x18003a78c  push    rbx
0x18003a78e  push    rbp
0x18003a78f  push    rsi
0x18003a790  push    rdi
0x18003a791  sub     rsp, 38h
0x18003a795  xor     ebp, ebp
0x18003a797  mov     rsi, rdx
0x18003a79a  mov     rdi, rcx
0x18003a79d  test    rdx, rdx
0x18003a7a0  jz      short loc_18003A7A5
0x18003a7a2  mov     [rdx], rbp
0x18003a7a5  test    rcx, rcx
0x18003a7a8  jz      loc_18003A8BC
0x18003a7ae  test    rsi, rsi
0x18003a7b1  jz      loc_18003A972
0x18003a7b7  mov     ebx, 26h ; '&'
0x18003a7bc  cmp     [rdi], bp
0x18003a7bf  jz      loc_18003A8AB
0x18003a7c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003a7c9  inc     rax
0x18003a7cc  cmp     [rdi+rax*2], bp
0x18003a7d0  jnz     short loc_18003A7C9
0x18003a7d2  cmp     rax, 8
0x18003a7d6  jnb     short loc_18003A7EF
0x18003a7d8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003a7dc  inc     rax
0x18003a7df  cmp     [rdi+rax*2], bp
0x18003a7e3  jnz     short loc_18003A7DC
0x18003a7e5  lea     rdi, [rdi+rax*2]
0x18003a7e9  add     rdi, 2
0x18003a7ed  jmp     short loc_18003A7BC
0x18003a7ef  mov     r9d, 8; cchCount2
0x18003a7f5  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18003a7fd  mov     edx, r9d; cchCount1
0x18003a800  lea     r8, aPciVen; "PCI\\VEN_"
0x18003a807  mov     rcx, rdi; lpString1
0x18003a80a  call    cs:__imp_CompareStringOrdinal
0x18003a811  nop     dword ptr [rax+rax+00h]
0x18003a816  test    eax, eax
0x18003a818  jz      loc_18003A92F
0x18003a81e  cmp     eax, 2
0x18003a821  jnz     short loc_18003A7D8
0x18003a823  mov     edx, ebx; Ch
0x18003a825  mov     rcx, rdi; Str
0x18003a828  call    cs:__imp_wcschr
0x18003a82f  nop     dword ptr [rax+rax+00h]
0x18003a834  test    rax, rax
0x18003a837  jz      short loc_18003A7D8
0x18003a839  mov     edx, ebx; Ch
0x18003a83b  mov     rcx, rdi; Str
0x18003a83e  call    cs:__imp_wcschr
0x18003a845  nop     dword ptr [rax+rax+00h]
0x18003a84a  mov     r9d, 5; cchCount2
0x18003a850  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18003a858  mov     edx, r9d; cchCount1
0x18003a85b  lea     r8, aDev; "&DEV_"
0x18003a862  mov     rcx, rax; lpString1
0x18003a865  call    cs:__imp_CompareStringOrdinal
0x18003a86c  nop     dword ptr [rax+rax+00h]
0x18003a871  test    eax, eax
0x18003a873  jz      short loc_18003A8E1
0x18003a875  cmp     eax, 2
0x18003a878  jnz     loc_18003A7D8
0x18003a87e  mov     edx, ebx; Ch
0x18003a880  mov     rcx, rdi; Str
0x18003a883  call    cs:__imp_wcschr
0x18003a88a  nop     dword ptr [rax+rax+00h]
0x18003a88f  movzx   edx, bx; Ch
0x18003a892  lea     rcx, [rax+2]; Str
0x18003a896  call    cs:__imp_wcschr
0x18003a89d  nop     dword ptr [rax+rax+00h]
0x18003a8a2  test    rax, rax
0x18003a8a5  jnz     loc_18003A7D8
0x18003a8ab  mov     ebx, ebp
0x18003a8ad  mov     [rsi], rdi
0x18003a8b0  mov     eax, ebx
0x18003a8b2  add     rsp, 38h
0x18003a8b6  pop     rdi
0x18003a8b7  pop     rsi
0x18003a8b8  pop     rbp
0x18003a8b9  pop     rbx
0x18003a8ba  retn
0x18003a8bc  mov     ebx, 80070057h
0x18003a8c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a8c8  lea     rax, WPP_GLOBAL_Control
0x18003a8cf  cmp     rcx, rax
0x18003a8d2  jz      short loc_18003A8B0
0x18003a8d4  test    byte ptr [rcx+1Ch], 40h
0x18003a8d8  jz      short loc_18003A8B0
0x18003a8da  mov     edx, 0FEh
0x18003a8df  jmp     short loc_18003A91A
0x18003a8e1  call    cs:__imp_GetLastError
0x18003a8e8  nop     dword ptr [rax+rax+00h]
0x18003a8ed  mov     ebx, eax
0x18003a8ef  test    eax, eax
0x18003a8f1  jle     short loc_18003A8FC
0x18003a8f3  movzx   ebx, ax
0x18003a8f6  or      ebx, 80070000h
0x18003a8fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a903  lea     rax, WPP_GLOBAL_Control
0x18003a90a  cmp     rcx, rax
0x18003a90d  jz      short loc_18003A8B0
0x18003a90f  test    byte ptr [rcx+1Ch], 40h
0x18003a913  jz      short loc_18003A8B0
0x18003a915  mov     edx, 101h
0x18003a91a  mov     rcx, [rcx+10h]
0x18003a91e  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18003a925  mov     r9d, ebx
0x18003a928  call    WPP_SF_d
0x18003a92d  jmp     short loc_18003A8B0
0x18003a92f  call    cs:__imp_GetLastError
0x18003a936  nop     dword ptr [rax+rax+00h]
0x18003a93b  mov     ebx, eax
0x18003a93d  test    eax, eax
0x18003a93f  jle     short loc_18003A94A
0x18003a941  movzx   ebx, ax
0x18003a944  or      ebx, 80070000h
0x18003a94a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a951  lea     rax, WPP_GLOBAL_Control
0x18003a958  cmp     rcx, rax
0x18003a95b  jz      loc_18003A8B0
0x18003a961  test    byte ptr [rcx+1Ch], 40h
0x18003a965  jz      loc_18003A8B0
0x18003a96b  mov     edx, 100h
0x18003a970  jmp     short loc_18003A91A
0x18003a972  mov     ebx, 80004003h
0x18003a977  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a97e  lea     rax, WPP_GLOBAL_Control
0x18003a985  cmp     rcx, rax
0x18003a988  jz      loc_18003A8B0
0x18003a98e  test    byte ptr [rcx+1Ch], 40h
0x18003a992  jz      loc_18003A8B0
0x18003a998  mov     edx, 0FFh
0x18003a99d  jmp     loc_18003A91A
```
