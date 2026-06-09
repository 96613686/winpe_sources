# CFveDriveType::GetFveVolumePath(ushort const *,ushort *,ulong)

- ea: `0x1800d7084`
- end: `0x1800d727e`
- name: `?GetFveVolumePath@CFveDriveType@@SAJPEBGPEAGK@Z`
- size: `506`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180066f10`

## callees

- `0x1800050c0`
- `0x18000aae0`
- `0x180023800`
- `0x18005e368`
- `0x1800d7084`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `msvcrt!iswascii` at `0x1800d7126`
- `msvcrt!iswascii` at `0x1800d71b1`
- `msvcrt!iswascii` at `0x1800d7126`
- `msvcrt!iswascii` at `0x1800d71b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7225`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7225`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800d7211`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800d7211`

## pseudocode

```c
signed int __fastcall CFveDriveType::GetFveVolumePath(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  signed int result; // eax
  unsigned __int64 v5; // rbx
  unsigned __int64 v6[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+40h] [rbp-C0h] BYREF

  v6[0] = 0;
  memset_0(szVolumePathName, 0, 0x208u);
  memset_0(a2, 0, 0x400u);
  result = StringCchLengthW(a1, 0x104u, v6);
  if ( result < 0 )
    return result;
  if ( v6[0] < 2 )
    return -2147024809;
  if ( v6[0] > 3 )
  {
    if ( !GetVolumePathNameW(a1, szVolumePathName, 0x104u) )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
  }
  else
  {
    if ( !iswascii(*a1) || a1[1] != 58 || v6[0] == 3 && a1[2] != 92 )
      return -2147024809;
    result = StringCchCopyW(szVolumePathName, 0x104u, a1);
    if ( result < 0 )
      return result;
  }
  result = StringCchLengthW(szVolumePathName, 0x104u, v6);
  if ( result >= 0 )
  {
    v5 = v6[0];
    if ( v6[0] < 2 )
      return -2147024809;
    if ( *((_WORD *)&v6[1] + v6[0] + 3) == 92 )
    {
      v5 = v6[0] - 1;
      if ( 2 * (v6[0] - 1) >= 0x208 )
        _report_rangecheckfailure();
      szVolumePathName[v5] = 0;
    }
    if ( iswascii(szVolumePathName[0]) && szVolumePathName[1] == 58 && (v5 == 2 || v5 == 3 && szVolumePathName[2] == 92) )
      return StringCchPrintfW(a2, 0x400u, L"%s%s", L"\\\\.\\", szVolumePathName);
    else
      return StringCchCopyW(a2, 0x400u, szVolumePathName);
  }
  return result;
}

```

## disassembly

```asm
0x1800d7084  mov     [rsp-8+arg_10], rbx
0x1800d7089  mov     [rsp-8+arg_18], rsi
0x1800d708e  push    rbp
0x1800d708f  push    r14
0x1800d7091  push    r15
0x1800d7093  lea     rbp, [rsp-160h]
0x1800d709b  sub     rsp, 260h
0x1800d70a2  mov     rax, cs:__security_cookie
0x1800d70a9  xor     rax, rsp
0x1800d70ac  mov     [rbp+170h+var_20], rax
0x1800d70b3  mov     rsi, rdx
0x1800d70b6  mov     [rsp+270h+var_240], 0
0x1800d70bf  mov     rbx, rcx
0x1800d70c2  xor     edx, edx; Val
0x1800d70c4  lea     rcx, [rsp+270h+szVolumePathName]; void *
0x1800d70c9  mov     r8d, 208h; Size
0x1800d70cf  call    memset_0
0x1800d70d4  mov     r15d, 400h
0x1800d70da  xor     edx, edx; Val
0x1800d70dc  mov     r8d, r15d; Size
0x1800d70df  mov     rcx, rsi; void *
0x1800d70e2  call    memset_0
0x1800d70e7  mov     r14d, 104h
0x1800d70ed  lea     r8, [rsp+270h+var_240]; unsigned __int64 *
0x1800d70f2  mov     edx, r14d; unsigned __int64
0x1800d70f5  mov     rcx, rbx; unsigned __int16 *
0x1800d70f8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800d70fd  test    eax, eax
0x1800d70ff  js      loc_1800D7255
0x1800d7105  cmp     [rsp+270h+var_240], 2
0x1800d710b  jnb     short loc_1800D7117
0x1800d710d  mov     eax, 80070057h
0x1800d7112  jmp     loc_1800D7255
0x1800d7117  cmp     [rsp+270h+var_240], 3
0x1800d711d  ja      loc_1800D7206
0x1800d7123  movzx   ecx, word ptr [rbx]; C
0x1800d7126  call    cs:__imp_iswascii
0x1800d712d  nop     dword ptr [rax+rax+00h]
0x1800d7132  test    eax, eax
0x1800d7134  jz      short loc_1800D710D
0x1800d7136  cmp     word ptr [rbx+2], 3Ah ; ':'
0x1800d713b  jnz     short loc_1800D710D
0x1800d713d  cmp     [rsp+270h+var_240], 3
0x1800d7143  jnz     short loc_1800D714C
0x1800d7145  cmp     word ptr [rbx+4], 5Ch ; '\'
0x1800d714a  jnz     short loc_1800D710D
0x1800d714c  mov     r8, rbx; unsigned __int16 *
0x1800d714f  lea     rcx, [rsp+270h+szVolumePathName]; unsigned __int16 *
0x1800d7154  mov     rdx, r14; unsigned __int64
0x1800d7157  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d715c  test    eax, eax
0x1800d715e  js      loc_1800D7255
0x1800d7164  lea     r8, [rsp+270h+var_240]; unsigned __int64 *
0x1800d7169  mov     rdx, r14; unsigned __int64
0x1800d716c  lea     rcx, [rsp+270h+szVolumePathName]; unsigned __int16 *
0x1800d7171  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800d7176  test    eax, eax
0x1800d7178  js      loc_1800D7255
0x1800d717e  mov     rbx, [rsp+270h+var_240]
0x1800d7183  cmp     rbx, 2
0x1800d7187  jb      short loc_1800D710D
0x1800d7189  cmp     [rsp+rbx*2+270h+var_232], 5Ch ; '\'
0x1800d718f  jnz     short loc_1800D71AC
0x1800d7191  dec     rbx
0x1800d7194  lea     rcx, [rbx+rbx]
0x1800d7198  cmp     rcx, 208h
0x1800d719f  jnb     loc_1800D723F
0x1800d71a5  xor     eax, eax
0x1800d71a7  mov     [rsp+rcx+270h+szVolumePathName], ax
0x1800d71ac  movzx   ecx, [rsp+270h+szVolumePathName]; C
0x1800d71b1  call    cs:__imp_iswascii
0x1800d71b8  nop     dword ptr [rax+rax+00h]
0x1800d71bd  test    eax, eax
0x1800d71bf  jz      loc_1800D7245
0x1800d71c5  cmp     [rsp+270h+var_22E], 3Ah ; ':'
0x1800d71cb  jnz     short loc_1800D7245
0x1800d71cd  cmp     rbx, 2
0x1800d71d1  jz      short loc_1800D71E1
0x1800d71d3  cmp     rbx, 3
0x1800d71d7  jnz     short loc_1800D7245
0x1800d71d9  cmp     [rsp+270h+var_22C], 5Ch ; '\'
0x1800d71df  jnz     short loc_1800D7245
0x1800d71e1  lea     rax, [rsp+270h+szVolumePathName]
0x1800d71e6  mov     rdx, r15; unsigned __int64
0x1800d71e9  lea     r9, asc_1801413E0; "\\\\.\\"
0x1800d71f0  mov     [rsp+270h+var_250], rax
0x1800d71f5  lea     r8, aSS; "%s%s"
0x1800d71fc  mov     rcx, rsi; unsigned __int16 *
0x1800d71ff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d7204  jmp     short loc_1800D7255
0x1800d7206  mov     r8d, r14d; cchBufferLength
0x1800d7209  lea     rdx, [rsp+270h+szVolumePathName]; lpszVolumePathName
0x1800d720e  mov     rcx, rbx; lpszFileName
0x1800d7211  call    cs:__imp_GetVolumePathNameW
0x1800d7218  nop     dword ptr [rax+rax+00h]
0x1800d721d  test    eax, eax
0x1800d721f  jnz     loc_1800D7164
0x1800d7225  call    cs:__imp_GetLastError
0x1800d722c  nop     dword ptr [rax+rax+00h]
0x1800d7231  test    eax, eax
0x1800d7233  jle     short loc_1800D7255
0x1800d7235  movzx   eax, ax
0x1800d7238  or      eax, 80070000h
0x1800d723d  jmp     short loc_1800D7255
0x1800d723f  call    __report_rangecheckfailure
0x1800d7245  lea     r8, [rsp+270h+szVolumePathName]; unsigned __int16 *
0x1800d724a  mov     rdx, r15; unsigned __int64
0x1800d724d  mov     rcx, rsi; unsigned __int16 *
0x1800d7250  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d7255  mov     rcx, [rbp+170h+var_20]
0x1800d725c  xor     rcx, rsp; StackCookie
0x1800d725f  call    __security_check_cookie
0x1800d7264  lea     r11, [rsp+270h+var_10]
0x1800d726c  mov     rbx, [r11+30h]
0x1800d7270  mov     rsi, [r11+38h]
0x1800d7274  mov     rsp, r11
0x1800d7277  pop     r15
0x1800d7279  pop     r14
0x1800d727b  pop     rbp
0x1800d727c  retn
```
