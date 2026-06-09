# MCIWndGetValue

- ea: `0x180010aa4`
- end: `0x180010bff`
- name: `MCIWndGetValue`
- size: `347`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180010cc0`
- `0x180012cdc`
- `0x1800135a4`
- `0x180013edc`

## callees

- `0x1800014b0`
- `0x1800014f0`
- `0x180003f98`
- `0x180010aa4`
- `0x1800134d4`
- `0x180015e38`

## import_xrefs

- `WINMM!mciSendStringW` at `0x180010b83`
- `WINMM!mciSendStringW` at `0x180010b83`

## pseudocode

```c
__int64 MCIWndGetValue(__int64 a1, int a2, const wchar_t *a3, unsigned int a4, ...)
{
  unsigned __int64 i; // rcx
  unsigned __int64 v8; // rax
  __int64 v9; // rax
  MCIERROR v10; // eax
  MCIERROR v11; // ebx
  WCHAR v12; // ax
  unsigned int v13; // ecx
  WCHAR *v14; // rdx
  WCHAR strReturnString[20]; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR strCommand[264]; // [rsp+50h] [rbp-B0h] BYREF
  va_list argList; // [rsp+2D0h] [rbp+1D0h] BYREF

  va_start(argList, a4);
  for ( i = 0; i < 0x103; ++i )
  {
    if ( (*a3 & 0xFFDF) == 0 )
      break;
    strCommand[i] = *a3++;
  }
  v8 = i;
  if ( 2 * i >= 0x208 )
    _report_rangecheckfailure();
  strCommand[v8] = 0;
  if ( *(_DWORD *)(a1 + 20) )
    StringCchPrintfW(&strCommand[v8], 260 - i, L" %d ", *(unsigned int *)(a1 + 16));
  v9 = -1;
  do
    ++v9;
  while ( strCommand[v9] );
  StringCchVPrintfW(&strCommand[v9], 260 - v9, a3, argList);
  v10 = mciSendStringW(strCommand, strReturnString, 0x14u, 0);
  v11 = v10;
  if ( a2 )
    MCIWndiHandleError(a1, v10);
  if ( v11 )
    return a4;
  v12 = strReturnString[0];
  v13 = 0;
  if ( strReturnString[0] >= 0x30u )
  {
    v14 = strReturnString;
    do
    {
      if ( v12 > 0x39u )
        break;
      ++v14;
      v13 = v12 + 2 * (5 * v13 - 24);
      v12 = *v14;
    }
    while ( *v14 >= 0x30u );
  }
  return v13;
}

```

## disassembly

```asm
0x180010aa4  mov     [rsp-8+arg_18], r9d
0x180010aa9  push    rbp
0x180010aaa  push    rbx
0x180010aab  push    rsi
0x180010aac  push    rdi
0x180010aad  push    r14
0x180010aaf  push    r15
0x180010ab1  lea     rbp, [rsp-178h]
0x180010ab9  sub     rsp, 278h
0x180010ac0  mov     rax, cs:__security_cookie
0x180010ac7  xor     rax, rsp
0x180010aca  mov     [rbp+1A0h+var_40], rax
0x180010ad1  xor     r15d, r15d
0x180010ad4  mov     rdi, rcx
0x180010ad7  mov     ecx, r15d
0x180010ada  mov     rbx, r8
0x180010add  mov     r14d, edx
0x180010ae0  movzx   eax, word ptr [rbx]
0x180010ae3  mov     edx, 0FFDFh
0x180010ae8  test    dx, ax
0x180010aeb  jz      short loc_180010B02
0x180010aed  mov     [rsp+rcx*2+2A0h+strCommand], ax
0x180010af2  add     rbx, 2
0x180010af6  inc     rcx
0x180010af9  cmp     rcx, 103h
0x180010b00  jb      short loc_180010AE0
0x180010b02  lea     rax, [rcx+rcx]
0x180010b06  cmp     rax, 208h
0x180010b0c  jnb     loc_180010BF9
0x180010b12  lea     r10, [rsp+2A0h+strCommand]
0x180010b17  mov     esi, 104h
0x180010b1c  add     r10, rax
0x180010b1f  mov     [r10], r15w
0x180010b23  cmp     [rdi+14h], r15d
0x180010b27  jz      short loc_180010B41
0x180010b29  mov     r9d, [rdi+10h]
0x180010b2d  lea     r8, aD_0; " %d "
0x180010b34  mov     edx, esi
0x180010b36  sub     rdx, rcx; cchDest
0x180010b39  mov     rcx, r10; pszDest
0x180010b3c  call    StringCchPrintfW
0x180010b41  lea     r9, [rbp+1A0h+argList]; argList
0x180010b48  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010b4c  lea     rcx, [rsp+2A0h+strCommand]
0x180010b51  inc     rax
0x180010b54  cmp     [rcx+rax*2], r15w
0x180010b59  jnz     short loc_180010B51
0x180010b5b  sub     rsi, rax
0x180010b5e  lea     rcx, [rsp+2A0h+strCommand]
0x180010b63  lea     rcx, [rcx+rax*2]; pszDest
0x180010b67  mov     rdx, rsi; cchDest
0x180010b6a  mov     r8, rbx; pszFormat
0x180010b6d  call    StringCchVPrintfW
0x180010b72  xor     r9d, r9d; hwndCallback
0x180010b75  lea     rdx, [rsp+2A0h+strReturnString]; lpstrReturnString
0x180010b7a  lea     rcx, [rsp+2A0h+strCommand]; lpstrCommand
0x180010b7f  lea     r8d, [r9+14h]; uReturnLength
0x180010b83  call    cs:__imp_mciSendStringW
0x180010b89  mov     ebx, eax
0x180010b8b  test    r14d, r14d
0x180010b8e  jz      short loc_180010B9A
0x180010b90  mov     edx, eax
0x180010b92  mov     rcx, rdi
0x180010b95  call    MCIWndiHandleError
0x180010b9a  test    ebx, ebx
0x180010b9c  jnz     short loc_180010BF1
0x180010b9e  movzx   eax, [rsp+2A0h+strReturnString]
0x180010ba3  mov     ecx, r15d
0x180010ba6  cmp     ax, 30h ; '0'
0x180010baa  jb      short loc_180010BD0
0x180010bac  lea     rdx, [rsp+2A0h+strReturnString]
0x180010bb1  cmp     ax, 39h ; '9'
0x180010bb5  ja      short loc_180010BD0
0x180010bb7  movzx   eax, ax
0x180010bba  lea     ecx, [rcx+rcx*4]
0x180010bbd  add     rdx, 2
0x180010bc1  lea     ecx, [rcx-18h]
0x180010bc4  lea     ecx, [rax+rcx*2]
0x180010bc7  movzx   eax, word ptr [rdx]
0x180010bca  cmp     ax, 30h ; '0'
0x180010bce  jnb     short loc_180010BB1
0x180010bd0  mov     eax, ecx
0x180010bd2  mov     rcx, [rbp+1A0h+var_40]
0x180010bd9  xor     rcx, rsp; StackCookie
0x180010bdc  call    __security_check_cookie
0x180010be1  add     rsp, 278h
0x180010be8  pop     r15
0x180010bea  pop     r14
0x180010bec  pop     rdi
0x180010bed  pop     rsi
0x180010bee  pop     rbx
0x180010bef  pop     rbp
0x180010bf0  retn
0x180010bf1  mov     eax, [rbp+1A0h+arg_18]
0x180010bf7  jmp     short loc_180010BD2
0x180010bf9  call    __report_rangecheckfailure
```
