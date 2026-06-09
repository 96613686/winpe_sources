# HrGetAttachIconByFile

- ea: `0x18008eb80`
- end: `0x18008ec66`
- name: `HrGetAttachIconByFile`
- size: `230`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x18008e520`
- `0x18008ead0`

## callees

- `0x18008eb80`
- `0x1800cc9ba`
- `0x1800cca00`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x18008ebe5`
- `SHLWAPI!PathFindExtensionW` at `0x18008ebe5`
- `KERNEL32!GetFileAttributesW` at `0x18008ebc6`
- `KERNEL32!GetFileAttributesW` at `0x18008ebc6`
- `USER32!LoadIconA` at `0x18008ec2d`
- `USER32!LoadIconA` at `0x18008ec2d`
- `USER32!CopyIcon` at `0x18008ec36`
- `USER32!CopyIcon` at `0x18008ec36`
- `SHELL32!SHGetFileInfoW` at `0x18008ec11`
- `SHELL32!SHGetFileInfoW` at `0x18008ec11`

## pseudocode

```c
__int64 __fastcall HrGetAttachIconByFile(LPCWSTR pszPath, int a2, HICON *a3)
{
  const WCHAR *ExtensionW; // rax
  HICON hIcon; // rax
  HICON IconA; // rax
  SHFILEINFOW psfi; // [rsp+30h] [rbp-2D8h] BYREF

  memset_0(&psfi, 0, sizeof(psfi));
  if ( !pszPath )
    goto LABEL_7;
  if ( GetFileAttributesW(pszPath) == -1 )
  {
    ExtensionW = PathFindExtensionW(pszPath);
    if ( !ExtensionW )
    {
LABEL_7:
      IconA = LoadIconA(g_hLocRes, (LPCSTR)1);
      hIcon = CopyIcon(IconA);
      goto LABEL_8;
    }
    SHGetFileInfoW(ExtensionW, 0x80u, &psfi, 0x2B8u, 273 - (a2 != 0));
  }
  else
  {
    SHGetFileInfoW(pszPath, 0, &psfi, 0x2B8u, 257 - (a2 != 0));
  }
  hIcon = psfi.hIcon;
  if ( !psfi.hIcon )
    goto LABEL_7;
LABEL_8:
  *a3 = hIcon;
  return 0;
}

```

## disassembly

```asm
0x18008eb80  mov     [rsp+arg_8], rbx
0x18008eb85  mov     [rsp+arg_18], rsi
0x18008eb8a  push    rdi
0x18008eb8b  sub     rsp, 300h
0x18008eb92  mov     rax, cs:__security_cookie
0x18008eb99  xor     rax, rsp
0x18008eb9c  mov     [rsp+308h+var_18], rax
0x18008eba4  mov     rsi, r8
0x18008eba7  mov     edi, edx
0x18008eba9  mov     rbx, rcx
0x18008ebac  xor     edx, edx; Val
0x18008ebae  mov     r8d, 2B8h; Size
0x18008ebb4  lea     rcx, [rsp+308h+psfi]; void *
0x18008ebb9  call    memset_0
0x18008ebbe  test    rbx, rbx
0x18008ebc1  jz      short loc_18008EC21
0x18008ebc3  mov     rcx, rbx; lpFileName
0x18008ebc6  call    cs:__imp_GetFileAttributesW
0x18008ebcc  mov     rcx, rbx; pszPath
0x18008ebcf  cmp     eax, 0FFFFFFFFh
0x18008ebd2  jz      short loc_18008EBE5
0x18008ebd4  neg     edi
0x18008ebd6  sbb     eax, eax
0x18008ebd8  add     eax, 101h
0x18008ebdd  mov     [rsp+308h+uFlags], eax
0x18008ebe1  xor     edx, edx
0x18008ebe3  jmp     short loc_18008EC06
0x18008ebe5  call    cs:__imp_PathFindExtensionW
0x18008ebeb  test    rax, rax
0x18008ebee  jz      short loc_18008EC21
0x18008ebf0  neg     edi
0x18008ebf2  mov     edx, 80h; dwFileAttributes
0x18008ebf7  sbb     ecx, ecx
0x18008ebf9  add     ecx, 111h
0x18008ebff  mov     [rsp+308h+uFlags], ecx; uFlags
0x18008ec03  mov     rcx, rax; pszPath
0x18008ec06  mov     r9d, 2B8h; cbFileInfo
0x18008ec0c  lea     r8, [rsp+308h+psfi]; psfi
0x18008ec11  call    cs:__imp_SHGetFileInfoW
0x18008ec17  mov     rax, [rsp+308h+psfi.hIcon]
0x18008ec1c  test    rax, rax
0x18008ec1f  jnz     short loc_18008EC3C
0x18008ec21  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18008ec28  mov     edx, 1; lpIconName
0x18008ec2d  call    cs:__imp_LoadIconA
0x18008ec33  mov     rcx, rax; hIcon
0x18008ec36  call    cs:__imp_CopyIcon
0x18008ec3c  mov     [rsi], rax
0x18008ec3f  xor     eax, eax
0x18008ec41  mov     rcx, [rsp+308h+var_18]
0x18008ec49  xor     rcx, rsp; StackCookie
0x18008ec4c  call    __security_check_cookie
0x18008ec51  lea     r11, [rsp+308h+var_8]
0x18008ec59  mov     rbx, [r11+18h]
0x18008ec5d  mov     rsi, [r11+28h]
0x18008ec61  mov     rsp, r11
0x18008ec64  pop     rdi
0x18008ec65  retn
```
