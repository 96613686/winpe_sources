# CFveDriveType::GetFveVolumePath(ushort const *,ushort *,ulong)

- ea: `0x18002bc10`
- end: `0x18002bdda`
- name: `?GetFveVolumePath@CFveDriveType@@SAJPEBGPEAGK@Z`
- size: `458`
- prototype: `signed int __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x180014aac`
- `0x180023fe4`
- `0x18002868c`
- `0x18002bb5c`

## callees

- `0x180001bb0`
- `0x180001bf0`
- `0x18000272c`
- `0x180002774`
- `0x18000b978`
- `0x18000b9bc`
- `0x18000b9f8`
- `0x18002bc10`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x18002bd7f`
- `KERNEL32!GetVolumePathNameW` at `0x18002bd7f`
- `KERNEL32!GetLastError` at `0x18002bd8d`
- `KERNEL32!GetLastError` at `0x18002bd8d`

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
  memset_0(a2, 0, 0x104u);
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
      return StringCchPrintfW(a2, 0x104u, L"%s%s", L"\\\\.\\", szVolumePathName);
    else
      return StringCchCopyW(a2, 0x104u, szVolumePathName);
  }
  return result;
}

```

## disassembly

```asm
0x18002bc10  mov     [rsp-8+arg_10], rbx
0x18002bc15  push    rbp
0x18002bc16  push    rsi
0x18002bc17  push    r14
0x18002bc19  lea     rbp, [rsp-160h]
0x18002bc21  sub     rsp, 260h
0x18002bc28  mov     rax, cs:__security_cookie
0x18002bc2f  xor     rax, rsp
0x18002bc32  mov     [rbp+170h+var_20], rax
0x18002bc39  mov     rsi, rdx
0x18002bc3c  mov     [rsp+270h+var_240], 0
0x18002bc45  mov     rbx, rcx
0x18002bc48  xor     edx, edx; Val
0x18002bc4a  lea     rcx, [rsp+270h+szVolumePathName]; void *
0x18002bc4f  mov     r8d, 208h; Size
0x18002bc55  call    memset_0
0x18002bc5a  mov     r14d, 104h
0x18002bc60  xor     edx, edx; Val
0x18002bc62  mov     r8d, r14d; Size
0x18002bc65  mov     rcx, rsi; void *
0x18002bc68  call    memset_0
0x18002bc6d  lea     r8, [rsp+270h+var_240]; unsigned __int64 *
0x18002bc72  mov     edx, r14d; unsigned __int64
0x18002bc75  mov     rcx, rbx; unsigned __int16 *
0x18002bc78  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002bc7d  test    eax, eax
0x18002bc7f  js      loc_18002BDB7
0x18002bc85  cmp     [rsp+270h+var_240], 2
0x18002bc8b  jnb     short loc_18002BC97
0x18002bc8d  mov     eax, 80070057h
0x18002bc92  jmp     loc_18002BDB7
0x18002bc97  cmp     [rsp+270h+var_240], 3
0x18002bc9d  ja      loc_18002BD74
0x18002bca3  movzx   ecx, word ptr [rbx]; C
0x18002bca6  call    iswascii
0x18002bcab  test    eax, eax
0x18002bcad  jz      short loc_18002BC8D
0x18002bcaf  cmp     word ptr [rbx+2], 3Ah ; ':'
0x18002bcb4  jnz     short loc_18002BC8D
0x18002bcb6  cmp     [rsp+270h+var_240], 3
0x18002bcbc  jnz     short loc_18002BCC5
0x18002bcbe  cmp     word ptr [rbx+4], 5Ch ; '\'
0x18002bcc3  jnz     short loc_18002BC8D
0x18002bcc5  mov     r8, rbx; unsigned __int16 *
0x18002bcc8  lea     rcx, [rsp+270h+szVolumePathName]; unsigned __int16 *
0x18002bccd  mov     rdx, r14; unsigned __int64
0x18002bcd0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002bcd5  test    eax, eax
0x18002bcd7  js      loc_18002BDB7
0x18002bcdd  lea     r8, [rsp+270h+var_240]; unsigned __int64 *
0x18002bce2  mov     rdx, r14; unsigned __int64
0x18002bce5  lea     rcx, [rsp+270h+szVolumePathName]; unsigned __int16 *
0x18002bcea  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002bcef  test    eax, eax
0x18002bcf1  js      loc_18002BDB7
0x18002bcf7  mov     rbx, [rsp+270h+var_240]
0x18002bcfc  cmp     rbx, 2
0x18002bd00  jb      short loc_18002BC8D
0x18002bd02  cmp     [rsp+rbx*2+270h+var_232], 5Ch ; '\'
0x18002bd08  jnz     short loc_18002BD25
0x18002bd0a  dec     rbx
0x18002bd0d  lea     rcx, [rbx+rbx]
0x18002bd11  cmp     rcx, 208h
0x18002bd18  jnb     loc_18002BDA1
0x18002bd1e  xor     eax, eax
0x18002bd20  mov     [rsp+rcx+270h+szVolumePathName], ax
0x18002bd25  movzx   ecx, [rsp+270h+szVolumePathName]; C
0x18002bd2a  call    iswascii
0x18002bd2f  test    eax, eax
0x18002bd31  jz      short loc_18002BDA7
0x18002bd33  cmp     [rsp+270h+var_22E], 3Ah ; ':'
0x18002bd39  jnz     short loc_18002BDA7
0x18002bd3b  cmp     rbx, 2
0x18002bd3f  jz      short loc_18002BD4F
0x18002bd41  cmp     rbx, 3
0x18002bd45  jnz     short loc_18002BDA7
0x18002bd47  cmp     [rsp+270h+var_22C], 5Ch ; '\'
0x18002bd4d  jnz     short loc_18002BDA7
0x18002bd4f  lea     rax, [rsp+270h+szVolumePathName]
0x18002bd54  mov     rdx, r14; unsigned __int64
0x18002bd57  lea     r9, asc_1800367B8; "\\\\.\\"
0x18002bd5e  mov     [rsp+270h+var_250], rax
0x18002bd63  lea     r8, aSS; "%s%s"
0x18002bd6a  mov     rcx, rsi; unsigned __int16 *
0x18002bd6d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bd72  jmp     short loc_18002BDB7
0x18002bd74  mov     r8d, r14d; cchBufferLength
0x18002bd77  lea     rdx, [rsp+270h+szVolumePathName]; lpszVolumePathName
0x18002bd7c  mov     rcx, rbx; lpszFileName
0x18002bd7f  call    cs:__imp_GetVolumePathNameW
0x18002bd85  test    eax, eax
0x18002bd87  jnz     loc_18002BCDD
0x18002bd8d  call    cs:__imp_GetLastError
0x18002bd93  test    eax, eax
0x18002bd95  jle     short loc_18002BDB7
0x18002bd97  movzx   eax, ax
0x18002bd9a  or      eax, 80070000h
0x18002bd9f  jmp     short loc_18002BDB7
0x18002bda1  call    __report_rangecheckfailure
0x18002bda7  lea     r8, [rsp+270h+szVolumePathName]; unsigned __int16 *
0x18002bdac  mov     rdx, r14; unsigned __int64
0x18002bdaf  mov     rcx, rsi; unsigned __int16 *
0x18002bdb2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002bdb7  mov     rcx, [rbp+170h+var_20]
0x18002bdbe  xor     rcx, rsp; StackCookie
0x18002bdc1  call    __security_check_cookie
0x18002bdc6  mov     rbx, [rsp+270h+arg_10]
0x18002bdce  add     rsp, 260h
0x18002bdd5  pop     r14
0x18002bdd7  pop     rsi
0x18002bdd8  pop     rbp
0x18002bdd9  retn
```
