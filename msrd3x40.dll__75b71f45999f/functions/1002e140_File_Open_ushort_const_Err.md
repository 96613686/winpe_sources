# File::Open(ushort const *,Err &)

- ea: `0x1002e140`
- end: `0x1002e361`
- name: `?Open@File@@QAEXPBGAAVErr@@@Z`
- size: `545`
- prototype: `void __thiscall(File *__hidden this, LPCWSTR lpFileName, struct Err *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1001fe30`
- `0x10020080`

## callees

- `0x1001f350`
- `0x10025ee0`
- `0x100260d0`
- `0x1002e140`
- `0x1002ebe0`
- `0x1002ed90`
- `0x1004eda0`
- `0x1005dae5`
- `0x1005dc8d`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005e7f3`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1002e28c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1002e28c`

## pseudocode

```c
void __thiscall File::Open(File *this, LPCWSTR lpFileName, void **a3)
{
  WCHAR *v4; // eax
  struct Err *v5; // ecx
  DWORD FullPathNameW; // eax
  void *FirstFileW; // eax
  size_t *v8; // ebx
  unsigned int v9; // ecx
  void *v10; // [esp+10h] [ebp-260h]
  size_t *pcchNewDestLength; // [esp+14h] [ebp-25Ch] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [esp+18h] [ebp-258h] BYREF

  if ( lpFileName && *lpFileName && wcslen(lpFileName) <= 0x104 )
  {
    pcchNewDestLength = 0;
    v4 = (WCHAR *)operator new[](0x20Au);
    *((_DWORD *)this + 1) = v4;
    if ( (*(_BYTE *)a3 & 8) != 0 )
      FullPathNameW = 0;
    else
      FullPathNameW = JetGetFullPathNameW(lpFileName, 0x104u, v4, (LPWSTR *)&pcchNewDestLength);
    if ( (*(_BYTE *)a3 & 8) == 0 )
    {
      if ( FullPathNameW )
      {
        if ( FullPathNameW <= 0x104 && pcchNewDestLength )
        {
          FirstFileW = (void *)JetFindFirstFileW(*((LPCWSTR *)this + 1), &FindFileData);
          v10 = FirstFileW;
          if ( FirstFileW != (void *)-1 )
          {
            if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
            {
              v8 = pcchNewDestLength;
              if ( !WCSICMP(pcchNewDestLength, FindFileData.cFileName)
                || !WCSICMP(v8, FindFileData.cAlternateFileName)
                && (v9 = *((_DWORD *)this + 1), (int)(((unsigned int)v8 - v9) & 0xFFFFFFFE) < 522)
                && (unsigned int)v8 > v9 )
              {
                WCSCPY2(v8, (size_t)FindFileData.cFileName, 261 - (((int)v8 - *((_DWORD *)this + 1)) >> 1));
              }
              FirstFileW = v10;
            }
            FindClose(FirstFileW);
          }
          if ( (*(_BYTE *)a3 & 8) != 0
            || (File::ReallyOpen(this, *((LPCWSTR *)this + 1), (struct Err *)a3), (*(_BYTE *)a3 & 8) != 0) )
          {
            File::SetExtErrInfo(this, (struct Err *)a3, *((const unsigned __int16 **)this + 1));
          }
        }
        else
        {
          Err::SetError(a3, -1044, v5);
          File::SetExtErrInfo(this, (struct Err *)a3, lpFileName);
        }
      }
      else
      {
        System::ErrGetLastError(v5);
        File::SetExtErrInfo(this, (struct Err *)a3, lpFileName);
      }
    }
  }
  else if ( (int)*a3 < 8 )
  {
    if ( ((unsigned int)*a3 & 0xFFFFFFFE) != 0 )
    {
      if ( a3[3] )
        operator delete[](a3[3]);
      if ( a3[4] )
        operator delete[](a3[4]);
    }
    *a3 = (void *)8;
    a3[1] = (void *)-1044;
    a3[2] = 0;
    a3[3] = 0;
    a3[4] = 0;
  }
}

```

## disassembly

```asm
0x1002e140  mov     edi, edi
0x1002e142  push    ebp
0x1002e143  mov     ebp, esp
0x1002e145  and     esp, 0FFFFFFF8h
0x1002e148  sub     esp, 264h
0x1002e14e  mov     eax, ___security_cookie
0x1002e153  xor     eax, esp
0x1002e155  mov     [esp+264h+var_4], eax
0x1002e15c  push    ebx
0x1002e15d  mov     ebx, [ebp+lpFileName]
0x1002e160  push    esi
0x1002e161  mov     esi, [ebp+arg_4]
0x1002e164  push    edi
0x1002e165  mov     edi, ecx
0x1002e167  test    ebx, ebx
0x1002e169  jz      loc_1002E2FA
0x1002e16f  cmp     word ptr [ebx], 0
0x1002e173  jz      loc_1002E2FA
0x1002e179  mov     ecx, ebx
0x1002e17b  lea     edx, [ecx+2]
0x1002e17e  mov     edi, edi
0x1002e180  mov     ax, [ecx]
0x1002e183  add     ecx, 2
0x1002e186  test    ax, ax
0x1002e189  jnz     short loc_1002E180
0x1002e18b  sub     ecx, edx
0x1002e18d  sar     ecx, 1
0x1002e18f  cmp     ecx, 104h
0x1002e195  ja      loc_1002E2FA
0x1002e19b  push    20Ah; unsigned int
0x1002e1a0  mov     [esp+274h+pcchNewDestLength], 0
0x1002e1a8  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1002e1ad  add     esp, 4
0x1002e1b0  mov     [edi+4], eax
0x1002e1b3  test    byte ptr [esi], 8
0x1002e1b6  jnz     short loc_1002E1CB
0x1002e1b8  lea     ecx, [esp+270h+pcchNewDestLength]
0x1002e1bc  push    ecx; lpFilePart
0x1002e1bd  push    eax; lpBuffer
0x1002e1be  push    104h; nBufferLength
0x1002e1c3  push    ebx; lpFileName
0x1002e1c4  call    _JetGetFullPathNameW@16; JetGetFullPathNameW(x,x,x,x)
0x1002e1c9  jmp     short loc_1002E1CD
0x1002e1cb  xor     eax, eax
0x1002e1cd  test    byte ptr [esi], 8
0x1002e1d0  jnz     loc_1002E34A
0x1002e1d6  test    eax, eax
0x1002e1d8  jnz     short loc_1002E200
0x1002e1da  push    esi
0x1002e1db  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1002e1e0  push    ebx; unsigned __int16 *
0x1002e1e1  push    esi; struct Err *
0x1002e1e2  mov     ecx, edi; this
0x1002e1e4  call    ?SetExtErrInfo@File@@AAEXAAVErr@@PBG@Z; File::SetExtErrInfo(Err &,ushort const *)
0x1002e1e9  pop     edi
0x1002e1ea  pop     esi
0x1002e1eb  pop     ebx
0x1002e1ec  mov     ecx, [esp+264h+var_4]
0x1002e1f3  xor     ecx, esp; StackCookie
0x1002e1f5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002e1fa  mov     esp, ebp
0x1002e1fc  pop     ebp
0x1002e1fd  retn    8
0x1002e200  cmp     eax, 104h
0x1002e205  ja      loc_1002E2CD
0x1002e20b  cmp     [esp+270h+pcchNewDestLength], 0
0x1002e210  jz      loc_1002E2CD
0x1002e216  lea     eax, [esp+270h+FindFileData]
0x1002e21a  push    eax; lpFindFileData
0x1002e21b  push    dword ptr [edi+4]; lpFileName
0x1002e21e  call    _JetFindFirstFileW@8; JetFindFirstFileW(x,x)
0x1002e223  mov     [esp+270h+var_260], eax
0x1002e227  cmp     eax, 0FFFFFFFFh
0x1002e22a  jz      short loc_1002E292
0x1002e22c  test    byte ptr [esp+270h+FindFileData.dwFileAttributes], 10h
0x1002e231  jnz     short loc_1002E28B
0x1002e233  mov     ebx, [esp+270h+pcchNewDestLength]
0x1002e237  lea     edx, [esp+270h+FindFileData.cFileName]
0x1002e23b  mov     ecx, ebx
0x1002e23d  call    _WCSICMP@8; WCSICMP(x,x)
0x1002e242  test    eax, eax
0x1002e244  jz      short loc_1002E26D
0x1002e246  lea     edx, [esp+270h+FindFileData.cAlternateFileName]
0x1002e24d  mov     ecx, ebx
0x1002e24f  call    _WCSICMP@8; WCSICMP(x,x)
0x1002e254  test    eax, eax
0x1002e256  jnz     short loc_1002E287
0x1002e258  mov     ecx, [edi+4]
0x1002e25b  mov     eax, ebx
0x1002e25d  sub     eax, ecx
0x1002e25f  and     eax, 0FFFFFFFEh
0x1002e262  cmp     eax, 20Ah
0x1002e267  jge     short loc_1002E287
0x1002e269  cmp     ebx, ecx
0x1002e26b  jbe     short loc_1002E287
0x1002e26d  mov     edx, ebx
0x1002e26f  mov     eax, 105h
0x1002e274  sub     edx, [edi+4]
0x1002e277  mov     ecx, ebx; pcchNewDestLength
0x1002e279  sar     edx, 1
0x1002e27b  sub     eax, edx
0x1002e27d  lea     edx, [esp+270h+FindFileData.cFileName]; cchDest
0x1002e281  push    eax; int
0x1002e282  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1002e287  mov     eax, [esp+270h+var_260]
0x1002e28b  push    eax; hFindFile
0x1002e28c  call    ds:__imp__FindClose@4; FindClose(x)
0x1002e292  test    byte ptr [esi], 8
0x1002e295  jnz     short loc_1002E2AB
0x1002e297  push    esi; struct Err *
0x1002e298  push    dword ptr [edi+4]; lpFileName
0x1002e29b  mov     ecx, edi; this
0x1002e29d  call    ?ReallyOpen@File@@AAEXPAGAAVErr@@@Z; File::ReallyOpen(ushort *,Err &)
0x1002e2a2  test    byte ptr [esi], 8
0x1002e2a5  jz      loc_1002E34A
0x1002e2ab  push    dword ptr [edi+4]; unsigned __int16 *
0x1002e2ae  mov     ecx, edi; this
0x1002e2b0  push    esi; struct Err *
0x1002e2b1  call    ?SetExtErrInfo@File@@AAEXAAVErr@@PBG@Z; File::SetExtErrInfo(Err &,ushort const *)
0x1002e2b6  pop     edi
0x1002e2b7  pop     esi
0x1002e2b8  pop     ebx
0x1002e2b9  mov     ecx, [esp+264h+var_4]
0x1002e2c0  xor     ecx, esp; StackCookie
0x1002e2c2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002e2c7  mov     esp, ebp
0x1002e2c9  pop     ebp
0x1002e2ca  retn    8
0x1002e2cd  push    ecx
0x1002e2ce  push    0FFFFFBECh
0x1002e2d3  mov     ecx, esi
0x1002e2d5  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1002e2da  push    ebx; unsigned __int16 *
0x1002e2db  push    esi; struct Err *
0x1002e2dc  mov     ecx, edi; this
0x1002e2de  call    ?SetExtErrInfo@File@@AAEXAAVErr@@PBG@Z; File::SetExtErrInfo(Err &,ushort const *)
0x1002e2e3  pop     edi
0x1002e2e4  pop     esi
0x1002e2e5  pop     ebx
0x1002e2e6  mov     ecx, [esp+264h+var_4]
0x1002e2ed  xor     ecx, esp; StackCookie
0x1002e2ef  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002e2f4  mov     esp, ebp
0x1002e2f6  pop     ebp
0x1002e2f7  retn    8
0x1002e2fa  mov     eax, [esi]
0x1002e2fc  cmp     eax, 8
0x1002e2ff  jge     short loc_1002E34A
0x1002e301  test    eax, 0FFFFFFFEh
0x1002e306  jz      short loc_1002E328
0x1002e308  mov     eax, [esi+0Ch]
0x1002e30b  test    eax, eax
0x1002e30d  jz      short loc_1002E318
0x1002e30f  push    eax; Block
0x1002e310  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002e315  add     esp, 4
0x1002e318  mov     eax, [esi+10h]
0x1002e31b  test    eax, eax
0x1002e31d  jz      short loc_1002E328
0x1002e31f  push    eax; Block
0x1002e320  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002e325  add     esp, 4
0x1002e328  mov     dword ptr [esi], 8
0x1002e32e  mov     dword ptr [esi+4], 0FFFFFBECh
0x1002e335  mov     dword ptr [esi+8], 0
0x1002e33c  mov     dword ptr [esi+0Ch], 0
0x1002e343  mov     dword ptr [esi+10h], 0
0x1002e34a  mov     ecx, [esp+270h+var_4]
0x1002e351  pop     edi
0x1002e352  pop     esi
0x1002e353  pop     ebx
0x1002e354  xor     ecx, esp; StackCookie
0x1002e356  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002e35b  mov     esp, ebp
0x1002e35d  pop     ebp
0x1002e35e  retn    8
```
