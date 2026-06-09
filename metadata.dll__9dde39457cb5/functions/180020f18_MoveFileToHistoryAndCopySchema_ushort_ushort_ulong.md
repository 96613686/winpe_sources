# MoveFileToHistoryAndCopySchema(ushort *,ushort *,ulong)

- ea: `0x180020f18`
- end: `0x180021088`
- name: `?MoveFileToHistoryAndCopySchema@@YAJPEAG0K@Z`
- size: `368`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d680`
- `0x180018f60`

## callees

- `0x180008a08`
- `0x18001c21c`
- `0x18001c508`
- `0x180020f18`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x180021003`
- `KERNEL32!MoveFileExW` at `0x180021003`
- `KERNEL32!GetLastError` at `0x18002100d`
- `KERNEL32!GetLastError` at `0x18002100d`

## pseudocode

```c
__int64 __fastcall MoveFileToHistoryAndCopySchema(LPCWSTR lpExistingFileName, unsigned __int16 *a2, unsigned int a3)
{
  WCHAR *v3; // rsi
  void *v4; // rdi
  signed int v8; // ebx
  int v9; // eax
  signed int LastError; // eax
  void *Block; // [rsp+80h] [rbp+8h] BYREF
  LPCWSTR lpNewFileName; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  v4 = 0;
  lpNewFileName = 0;
  Block = 0;
  if ( lpExistingFileName && a2 )
  {
    v8 = ConstructHistoryFileName(
           (unsigned __int16 **)&lpNewFileName,
           (unsigned __int16 *)g_wszHistoryFileDir,
           g_cchHistoryFileDir,
           g_wszRealFileNameWithoutPathWithoutExtension,
           g_cchRealFileNameWithoutPathWithoutExtension,
           g_wszRealFileNameExtension,
           g_cchRealFileNameExtension,
           a3,
           0);
    if ( v8 < 0 )
    {
      v3 = (WCHAR *)lpNewFileName;
    }
    else
    {
      v9 = ConstructHistoryFileName(
             (unsigned __int16 **)&Block,
             (unsigned __int16 *)g_wszHistoryFileDir,
             g_cchHistoryFileDir,
             g_wszSchemaFileNameWithoutPathWithoutExtension,
             g_cchSchemaFileNameWithoutPathWithoutExtension,
             g_wszSchemaFileNameExtension,
             g_cchSchemaFileNameExtension,
             a3,
             0);
      v3 = (WCHAR *)lpNewFileName;
      v8 = v9;
      if ( v9 < 0 )
      {
LABEL_8:
        v4 = Block;
        goto LABEL_13;
      }
      if ( !MoveFileExW(lpExistingFileName, lpNewFileName, 1u) )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_8;
      }
      v4 = Block;
      v8 = CopyFileWithSecurityDescriptor(a2, (unsigned __int16 *)Block);
      if ( v8 >= 0 )
        v8 = 0;
    }
  }
  else
  {
    v8 = -2147024809;
  }
LABEL_13:
  if ( v3 )
    operator delete(v3);
  if ( v4 )
    operator delete(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180020f18  mov     r11, rsp
0x180020f1b  mov     [r11+10h], rbx
0x180020f1f  push    rbp
0x180020f20  push    rsi
0x180020f21  push    rdi
0x180020f22  push    r14
0x180020f24  push    r15
0x180020f26  sub     rsp, 50h
0x180020f2a  xor     esi, esi
0x180020f2c  xor     edi, edi
0x180020f2e  mov     [r11+20h], rsi
0x180020f32  mov     r15d, r8d
0x180020f35  mov     [r11+8], rdi
0x180020f39  mov     rbp, rdx
0x180020f3c  mov     r14, rcx
0x180020f3f  test    rcx, rcx
0x180020f42  jz      loc_180021053
0x180020f48  test    rdx, rdx
0x180020f4b  jz      loc_180021053
0x180020f51  mov     eax, cs:?g_cchRealFileNameExtension@@3KA; ulong g_cchRealFileNameExtension
0x180020f57  lea     rcx, [r11+20h]; unsigned __int16 **
0x180020f5b  mov     r9, cs:?g_wszRealFileNameWithoutPathWithoutExtension@@3PEAGEA; unsigned __int16 *
0x180020f62  mov     rdx, cs:?g_wszHistoryFileDir@@3PEAGEA; unsigned __int16 *
0x180020f69  mov     [rsp+78h+var_38], esi; unsigned int
0x180020f6d  mov     [r11-40h], r8d
0x180020f71  mov     r8d, cs:?g_cchHistoryFileDir@@3KA; unsigned int
0x180020f78  mov     [rsp+78h+var_48], eax; unsigned int
0x180020f7c  mov     rax, cs:?g_wszRealFileNameExtension@@3PEAGEA; ushort * g_wszRealFileNameExtension
0x180020f83  mov     [r11-50h], rax
0x180020f87  mov     eax, cs:?g_cchRealFileNameWithoutPathWithoutExtension@@3KA; ulong g_cchRealFileNameWithoutPathWithoutExtension
0x180020f8d  mov     [rsp+78h+var_58], eax; unsigned int
0x180020f91  call    ?ConstructHistoryFileName@@YAJPEAPEAGPEAGK1K1KKK@Z; ConstructHistoryFileName(ushort * *,ushort *,ulong,ushort *,ulong,ushort *,ulong,ulong,ulong)
0x180020f96  mov     ebx, eax
0x180020f98  test    eax, eax
0x180020f9a  js      loc_180021049
0x180020fa0  mov     eax, cs:?g_cchSchemaFileNameExtension@@3KA; ulong g_cchSchemaFileNameExtension
0x180020fa6  lea     rcx, [rsp+78h+Block]; unsigned __int16 **
0x180020fae  mov     r9, cs:?g_wszSchemaFileNameWithoutPathWithoutExtension@@3PEAGEA; unsigned __int16 *
0x180020fb5  mov     r8d, cs:?g_cchHistoryFileDir@@3KA; unsigned int
0x180020fbc  mov     rdx, cs:?g_wszHistoryFileDir@@3PEAGEA; unsigned __int16 *
0x180020fc3  mov     [rsp+78h+var_38], esi; unsigned int
0x180020fc7  mov     [rsp+78h+var_40], r15d; unsigned int
0x180020fcc  mov     [rsp+78h+var_48], eax; unsigned int
0x180020fd0  mov     rax, cs:?g_wszSchemaFileNameExtension@@3PEAGEA; ushort * g_wszSchemaFileNameExtension
0x180020fd7  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x180020fdc  mov     eax, cs:?g_cchSchemaFileNameWithoutPathWithoutExtension@@3KA; ulong g_cchSchemaFileNameWithoutPathWithoutExtension
0x180020fe2  mov     [rsp+78h+var_58], eax; unsigned int
0x180020fe6  call    ?ConstructHistoryFileName@@YAJPEAPEAGPEAGK1K1KKK@Z; ConstructHistoryFileName(ushort * *,ushort *,ulong,ushort *,ulong,ushort *,ulong,ulong,ulong)
0x180020feb  mov     rsi, [rsp+78h+lpNewFileName]
0x180020ff3  mov     ebx, eax
0x180020ff5  test    eax, eax
0x180020ff7  js      short loc_180021022
0x180020ff9  lea     r8d, [rdi+1]; dwFlags
0x180020ffd  mov     rdx, rsi; lpNewFileName
0x180021000  mov     rcx, r14; lpExistingFileName
0x180021003  call    cs:__imp_MoveFileExW
0x180021009  test    eax, eax
0x18002100b  jnz     short loc_18002102C
0x18002100d  call    cs:__imp_GetLastError
0x180021013  mov     ebx, eax
0x180021015  test    eax, eax
0x180021017  jle     short loc_180021022
0x180021019  movzx   ebx, ax
0x18002101c  or      ebx, 80070000h
0x180021022  mov     rdi, [rsp+78h+Block]
0x18002102a  jmp     short loc_180021058
0x18002102c  mov     rdi, [rsp+78h+Block]
0x180021034  mov     rcx, rbp; unsigned __int16 *
0x180021037  mov     rdx, rdi; unsigned __int16 *
0x18002103a  call    ?CopyFileWithSecurityDescriptor@@YAJPEAG0@Z; CopyFileWithSecurityDescriptor(ushort *,ushort *)
0x18002103f  mov     ebx, eax
0x180021041  test    eax, eax
0x180021043  js      short loc_180021058
0x180021045  xor     ebx, ebx
0x180021047  jmp     short loc_180021058
0x180021049  mov     rsi, [rsp+78h+lpNewFileName]
0x180021051  jmp     short loc_180021058
0x180021053  mov     ebx, 80070057h
0x180021058  test    rsi, rsi
0x18002105b  jz      short loc_180021065
0x18002105d  mov     rcx, rsi; Block
0x180021060  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021065  test    rdi, rdi
0x180021068  jz      short loc_180021072
0x18002106a  mov     rcx, rdi; Block
0x18002106d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021072  mov     eax, ebx
0x180021074  mov     rbx, [rsp+78h+arg_8]
0x18002107c  add     rsp, 50h
0x180021080  pop     r15
0x180021082  pop     r14
0x180021084  pop     rdi
0x180021085  pop     rsi
0x180021086  pop     rbp
0x180021087  retn
```
