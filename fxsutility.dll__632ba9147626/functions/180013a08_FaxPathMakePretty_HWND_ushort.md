# FaxPathMakePretty(HWND__ *,ushort)

- ea: `0x180013a08`
- end: `0x180013af4`
- name: `?FaxPathMakePretty@@YAJPEAUHWND__@@G@Z`
- size: `236`
- prototype: `__int64 __fastcall(HWND hDlg, unsigned __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011310`

## callees

- `0x180013a08`
- `0x180015cf0`

## import_xrefs

- `SHLWAPI!PathMakePrettyW` at `0x180013a9a`
- `SHLWAPI!PathMakePrettyW` at `0x180013a9a`
- `KERNEL32!GetFullPathNameW` at `0x180013a6f`
- `KERNEL32!GetFullPathNameW` at `0x180013a6f`
- `KERNEL32!GetLastError` at `0x180013a79`
- `KERNEL32!GetLastError` at `0x180013a79`
- `USER32!SetDlgItemTextW` at `0x180013ab3`
- `USER32!SetDlgItemTextW` at `0x180013ab3`
- `USER32!GetDlgItemTextW` at `0x180013a3e`
- `USER32!GetDlgItemTextW` at `0x180013a3e`

## pseudocode

```c
__int64 __fastcall FaxPathMakePretty(HWND hDlg, unsigned __int16 a2)
{
  int v2; // esi
  __int64 v4; // rax
  DWORD FullPathNameW; // eax
  signed int LastError; // eax
  signed int v7; // ebx
  WCHAR String[264]; // [rsp+20h] [rbp-448h] BYREF
  WCHAR Buffer[264]; // [rsp+230h] [rbp-238h] BYREF

  v2 = a2;
  GetDlgItemTextW(hDlg, a2, String, 260);
  v4 = -1;
  do
    ++v4;
  while ( String[v4] );
  if ( !v4 )
    return 0;
  FullPathNameW = GetFullPathNameW(String, 0x104u, Buffer, 0);
  if ( FullPathNameW )
  {
    if ( FullPathNameW > 0x104 )
      return (unsigned int)-2147024774;
    goto LABEL_8;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_8:
    if ( PathMakePrettyW(Buffer) )
    {
      v7 = 0;
      SetDlgItemTextW(hDlg, v2, Buffer);
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180013a08  mov     [rsp+arg_10], rbx
0x180013a0d  push    rbp
0x180013a0e  push    rsi
0x180013a0f  push    rdi
0x180013a10  sub     rsp, 450h
0x180013a17  mov     rax, cs:__security_cookie
0x180013a1e  xor     rax, rsp
0x180013a21  mov     [rsp+468h+var_28], rax
0x180013a29  movzx   esi, dx
0x180013a2c  lea     r8, [rsp+468h+String]; lpString
0x180013a31  mov     ebx, 104h
0x180013a36  mov     edx, esi; nIDDlgItem
0x180013a38  mov     r9d, ebx; cchMax
0x180013a3b  mov     rdi, rcx
0x180013a3e  call    cs:__imp_GetDlgItemTextW
0x180013a44  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013a48  lea     rcx, [rsp+468h+String]
0x180013a4d  xor     ebp, ebp
0x180013a4f  inc     rax
0x180013a52  cmp     [rcx+rax*2], bp
0x180013a56  jnz     short loc_180013A4F
0x180013a58  test    rax, rax
0x180013a5b  jz      short loc_180013ACD
0x180013a5d  xor     r9d, r9d; lpFilePart
0x180013a60  lea     r8, [rsp+468h+Buffer]; lpBuffer
0x180013a68  mov     edx, ebx; nBufferLength
0x180013a6a  lea     rcx, [rsp+468h+String]; lpFileName
0x180013a6f  call    cs:__imp_GetFullPathNameW
0x180013a75  test    eax, eax
0x180013a77  jnz     short loc_180013ABB
0x180013a79  call    cs:__imp_GetLastError
0x180013a7f  mov     ebx, eax
0x180013a81  test    eax, eax
0x180013a83  jle     short loc_180013A8E
0x180013a85  movzx   ebx, ax
0x180013a88  or      ebx, 80070000h
0x180013a8e  test    ebx, ebx
0x180013a90  js      short loc_180013ACF
0x180013a92  lea     rcx, [rsp+468h+Buffer]; pszPath
0x180013a9a  call    cs:__imp_PathMakePrettyW
0x180013aa0  test    eax, eax
0x180013aa2  jz      short loc_180013AC6
0x180013aa4  lea     r8, [rsp+468h+Buffer]; lpString
0x180013aac  mov     edx, esi; nIDDlgItem
0x180013aae  mov     rcx, rdi; hDlg
0x180013ab1  mov     ebx, ebp
0x180013ab3  call    cs:__imp_SetDlgItemTextW
0x180013ab9  jmp     short loc_180013ACF
0x180013abb  cmp     eax, ebx
0x180013abd  jbe     short loc_180013A92
0x180013abf  mov     ebx, 8007007Ah
0x180013ac4  jmp     short loc_180013ACF
0x180013ac6  mov     ebx, 80004005h
0x180013acb  jmp     short loc_180013ACF
0x180013acd  mov     ebx, ebp
0x180013acf  mov     eax, ebx
0x180013ad1  mov     rcx, [rsp+468h+var_28]
0x180013ad9  xor     rcx, rsp; StackCookie
0x180013adc  call    __security_check_cookie
0x180013ae1  mov     rbx, [rsp+468h+arg_10]
0x180013ae9  add     rsp, 450h
0x180013af0  pop     rdi
0x180013af1  pop     rsi
0x180013af2  pop     rbp
0x180013af3  retn
```
