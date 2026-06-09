# MCIWndString

- ea: `0x1800129a0`
- end: `0x180012abd`
- name: `MCIWndString`
- size: `285`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180010194`
- `0x180010cc0`
- `0x180012f08`
- `0x180013edc`
- `0x18001494c`
- `0x1800149d4`
- `0x180014cc8`

## callees

- `0x1800014b0`
- `0x1800014f0`
- `0x180003f98`
- `0x1800129a0`
- `0x1800134d4`
- `0x180015e38`

## import_xrefs

- `WINMM!mciSendStringW` at `0x180012a9a`
- `WINMM!mciSendStringW` at `0x180012a9a`

## pseudocode

```c
__int64 MCIWndString(__int64 a1, int a2, const wchar_t *a3, ...)
{
  WCHAR *v3; // rax
  unsigned __int64 v7; // r8
  WCHAR v8; // cx
  unsigned __int64 v9; // rax
  __int64 v10; // r9
  __int64 v11; // rax
  MCIERROR v12; // eax
  MCIERROR v13; // edi
  WCHAR strCommand[264]; // [rsp+30h] [rbp-248h] BYREF
  const wchar_t *pszFormat; // [rsp+290h] [rbp+18h]
  va_list argList; // [rsp+298h] [rbp+20h] BYREF

  va_start(argList, a3);
  pszFormat = a3;
  v3 = (WCHAR *)a3;
  if ( !*(_DWORD *)(a1 + 20) )
    return 0;
  v7 = 0;
  do
  {
    v8 = *v3;
    if ( (*v3 & 0xFFDF) == 0 )
      break;
    ++v3;
    strCommand[v7++] = v8;
    pszFormat = v3;
  }
  while ( v7 < 0x103 );
  v9 = v7;
  if ( 2 * v7 >= 0x208 )
    _report_rangecheckfailure();
  v10 = *(unsigned int *)(a1 + 16);
  strCommand[v9] = 0;
  StringCchPrintfW(&strCommand[v9], 260 - v7, L" %d ", v10);
  v11 = -1;
  do
    ++v11;
  while ( strCommand[v11] );
  StringCchVPrintfW(&strCommand[v11], 260 - v11, pszFormat, argList);
  v12 = mciSendStringW(strCommand, 0, 0, 0);
  v13 = v12;
  if ( a2 )
    MCIWndiHandleError(a1, v12);
  return v13;
}

```

## disassembly

```asm
0x1800129a0  mov     [rsp+pszFormat], r8
0x1800129a5  mov     qword ptr [rsp+argList], r9
0x1800129aa  push    rbx
0x1800129ab  push    rbp
0x1800129ac  push    rsi
0x1800129ad  push    rdi
0x1800129ae  sub     rsp, 258h
0x1800129b5  mov     rax, cs:__security_cookie
0x1800129bc  xor     rax, rsp
0x1800129bf  mov     [rsp+278h+var_38], rax
0x1800129c7  xor     ebp, ebp
0x1800129c9  mov     rax, r8
0x1800129cc  mov     esi, edx
0x1800129ce  mov     rbx, rcx
0x1800129d1  cmp     [rcx+14h], ebp
0x1800129d4  jnz     short loc_1800129F4
0x1800129d6  xor     eax, eax
0x1800129d8  mov     rcx, [rsp+278h+var_38]
0x1800129e0  xor     rcx, rsp; StackCookie
0x1800129e3  call    __security_check_cookie
0x1800129e8  add     rsp, 258h
0x1800129ef  pop     rdi
0x1800129f0  pop     rsi
0x1800129f1  pop     rbp
0x1800129f2  pop     rbx
0x1800129f3  retn
0x1800129f4  mov     r8, rbp
0x1800129f7  movzx   ecx, word ptr [rax]
0x1800129fa  mov     edx, 0FFDFh
0x1800129ff  test    dx, cx
0x180012a02  jz      short loc_180012A22
0x180012a04  add     rax, 2
0x180012a08  mov     [rsp+r8*2+278h+strCommand], cx
0x180012a0e  inc     r8
0x180012a11  mov     [rsp+278h+pszFormat], rax
0x180012a19  cmp     r8, 103h
0x180012a20  jb      short loc_1800129F7
0x180012a22  lea     rax, [r8+r8]
0x180012a26  cmp     rax, 208h
0x180012a2c  jnb     loc_180012AB7
0x180012a32  mov     r9d, [rbx+10h]
0x180012a36  lea     rcx, [rsp+278h+strCommand]
0x180012a3b  add     rcx, rax; pszDest
0x180012a3e  mov     edi, 104h
0x180012a43  mov     edx, edi
0x180012a45  sub     rdx, r8; cchDest
0x180012a48  lea     r8, aD_0; " %d "
0x180012a4f  mov     [rcx], bp
0x180012a52  call    StringCchPrintfW
0x180012a57  lea     rcx, [rsp+278h+strCommand]
0x180012a5c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012a60  inc     rax
0x180012a63  cmp     [rcx+rax*2], bp
0x180012a67  jnz     short loc_180012A60
0x180012a69  mov     r8, [rsp+278h+pszFormat]; pszFormat
0x180012a71  lea     rcx, [rsp+278h+strCommand]
0x180012a76  sub     rdi, rax
0x180012a79  lea     rcx, [rcx+rax*2]; pszDest
0x180012a7d  mov     rdx, rdi; cchDest
0x180012a80  lea     r9, [rsp+278h+argList]; argList
0x180012a88  call    StringCchVPrintfW
0x180012a8d  xor     r9d, r9d; hwndCallback
0x180012a90  lea     rcx, [rsp+278h+strCommand]; lpstrCommand
0x180012a95  xor     r8d, r8d; uReturnLength
0x180012a98  xor     edx, edx; lpstrReturnString
0x180012a9a  call    cs:__imp_mciSendStringW
0x180012aa0  mov     edi, eax
0x180012aa2  test    esi, esi
0x180012aa4  jz      short loc_180012AB0
0x180012aa6  mov     edx, eax
0x180012aa8  mov     rcx, rbx
0x180012aab  call    MCIWndiHandleError
0x180012ab0  mov     eax, edi
0x180012ab2  jmp     loc_1800129D8
0x180012ab7  call    __report_rangecheckfailure
```
