# CFontAgent_Type1::_PrepareDestinationFilePaths(int,ushort *,uint,ushort *,uint)

- ea: `0x1800087d0`
- end: `0x1800088f5`
- name: `?_PrepareDestinationFilePaths@CFontAgent_Type1@@IEAAJHPEAGI0I@Z`
- size: `293`
- prototype: `__int64 __fastcall(CFontAgent_Type1 *this, int, unsigned __int16 *, unsigned int, unsigned __int16 *pszPath)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007b80`

## callees

- `0x1800087d0`
- `0x1800138c8`
- `0x180013920`
- `0x180013a38`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800088ba`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800088ba`

## pseudocode

```c
__int64 __fastcall CFontAgent_Type1::_PrepareDestinationFilePaths(
        CFontAgent_Type1 *this,
        int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *pszPath)
{
  int appended; // ebx
  int v9; // edi
  unsigned int v10; // edx
  unsigned int v11; // edx
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  WCHAR String2[264]; // [rsp+30h] [rbp-458h] BYREF
  WCHAR String1[264]; // [rsp+240h] [rbp-248h] BYREF

  appended = 0;
  *a3 = 0;
  v9 = -1;
  *pszPath = 0;
  while ( appended >= 0 )
  {
    appended = PathAppendFileToFontsDirectory(a2, a3, (const unsigned __int16 *)this + 420, a4);
    if ( appended >= 0 )
    {
      PathAppendFileToFontsDirectory(a2, pszPath, (const unsigned __int16 *)this + 680, a4);
      appended = PathMakeFilenameUnique(a3, v10, v9);
      if ( appended >= 0 )
      {
        appended = PathMakeFilenameUnique(pszPath, v11, v9);
        if ( appended >= 0 )
        {
          appended = PathExtractFileName(a3, String1, v12);
          if ( appended >= 0 )
          {
            appended = PathExtractFileName(pszPath, String2, v13);
            if ( appended >= 0 && CompareStringW(0x7Fu, 1u, String1, -1, String2, -1) == 2 )
              break;
          }
        }
      }
    }
    ++v9;
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800087d0  mov     [rsp+arg_18], rbx
0x1800087d5  push    rbp
0x1800087d6  push    rsi
0x1800087d7  push    rdi
0x1800087d8  push    r14
0x1800087da  push    r15
0x1800087dc  sub     rsp, 460h
0x1800087e3  mov     rax, cs:__security_cookie
0x1800087ea  xor     rax, rsp
0x1800087ed  mov     [rsp+488h+var_38], rax
0x1800087f5  mov     rsi, [rsp+488h+pszPath]
0x1800087fd  xor     eax, eax
0x1800087ff  xor     ebx, ebx
0x180008801  mov     [r8], ax
0x180008805  mov     r14, r8
0x180008808  mov     r15d, edx
0x18000880b  mov     rbp, rcx
0x18000880e  or      edi, 0FFFFFFFFh
0x180008811  mov     [rsi], ax
0x180008814  test    ebx, ebx
0x180008816  js      loc_1800088CC
0x18000881c  lea     r8, [rbp+348h]; unsigned __int16 *
0x180008823  mov     rdx, r14; unsigned __int16 *
0x180008826  mov     ecx, r15d; int
0x180008829  call    ?PathAppendFileToFontsDirectory@@YAJHPEAGPEBGI@Z; PathAppendFileToFontsDirectory(int,ushort *,ushort const *,uint)
0x18000882e  mov     ebx, eax
0x180008830  test    eax, eax
0x180008832  js      loc_1800088C5
0x180008838  lea     r8, [rbp+550h]; unsigned __int16 *
0x18000883f  mov     rdx, rsi; unsigned __int16 *
0x180008842  mov     ecx, r15d; int
0x180008845  call    ?PathAppendFileToFontsDirectory@@YAJHPEAGPEBGI@Z; PathAppendFileToFontsDirectory(int,ushort *,ushort const *,uint)
0x18000884a  mov     r8d, edi; int
0x18000884d  mov     rcx, r14; unsigned __int16 *
0x180008850  call    ?PathMakeFilenameUnique@@YAJPEAGIH@Z; PathMakeFilenameUnique(ushort *,uint,int)
0x180008855  mov     ebx, eax
0x180008857  test    eax, eax
0x180008859  js      short loc_1800088C5
0x18000885b  mov     r8d, edi; int
0x18000885e  mov     rcx, rsi; unsigned __int16 *
0x180008861  call    ?PathMakeFilenameUnique@@YAJPEAGIH@Z; PathMakeFilenameUnique(ushort *,uint,int)
0x180008866  mov     ebx, eax
0x180008868  test    eax, eax
0x18000886a  js      short loc_1800088C5
0x18000886c  lea     rdx, [rsp+488h+String1]; unsigned __int16 *
0x180008874  mov     rcx, r14; pszPath
0x180008877  call    ?PathExtractFileName@@YAJPEBGPEAGI@Z; PathExtractFileName(ushort const *,ushort *,uint)
0x18000887c  mov     ebx, eax
0x18000887e  test    eax, eax
0x180008880  js      short loc_1800088C5
0x180008882  lea     rdx, [rsp+488h+String2]; unsigned __int16 *
0x180008887  mov     rcx, rsi; pszPath
0x18000888a  call    ?PathExtractFileName@@YAJPEBGPEAGI@Z; PathExtractFileName(ushort const *,ushort *,uint)
0x18000888f  mov     ebx, eax
0x180008891  test    eax, eax
0x180008893  js      short loc_1800088C5
0x180008895  or      r9d, 0FFFFFFFFh; cchCount1
0x180008899  mov     [rsp+488h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800088a1  lea     rax, [rsp+488h+String2]
0x1800088a6  lea     r8, [rsp+488h+String1]; lpString1
0x1800088ae  mov     [rsp+488h+lpString2], rax; lpString2
0x1800088b3  lea     edx, [r9+2]; dwCmpFlags
0x1800088b7  lea     ecx, [rdx+7Eh]; Locale
0x1800088ba  call    cs:__imp_CompareStringW
0x1800088c0  cmp     eax, 2
0x1800088c3  jz      short loc_1800088CC
0x1800088c5  inc     edi
0x1800088c7  jmp     loc_180008814
0x1800088cc  mov     eax, ebx
0x1800088ce  mov     rcx, [rsp+488h+var_38]
0x1800088d6  xor     rcx, rsp; StackCookie
0x1800088d9  call    __security_check_cookie
0x1800088de  mov     rbx, [rsp+488h+arg_18]
0x1800088e6  add     rsp, 460h
0x1800088ed  pop     r15
0x1800088ef  pop     r14
0x1800088f1  pop     rdi
0x1800088f2  pop     rsi
0x1800088f3  pop     rbp
0x1800088f4  retn
```
