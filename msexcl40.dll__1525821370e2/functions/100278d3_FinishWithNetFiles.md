# FinishWithNetFiles

- ea: `0x100278d3`
- end: `0x100279e9`
- name: `FinishWithNetFiles`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100279f0`

## callees

- `0x10006400`
- `0x10018b80`
- `0x10022871`
- `0x10024042`
- `0x100246ef`
- `0x10025ab7`
- `0x100278d3`
- `0x10032ea8`
- `0x100338a0`
- `0x10035510`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x10027992`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x10027992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100279d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100279d2`

## pseudocode

```c
int __thiscall FinishWithNetFiles(char *this)
{
  char *v1; // esi
  int result; // eax
  int **v3; // edi
  int v4; // ebx
  int v5; // eax
  int *v6; // esi
  wchar_t Dir[256]; // [esp+10h] [ebp-428h] BYREF
  WCHAR PathName[264]; // [esp+210h] [ebp-228h] BYREF
  wchar_t Drive[10]; // [esp+420h] [ebp-18h] BYREF

  v1 = this;
  result = NetProtocolType(this + 594);
  if ( result )
  {
    v3 = (int **)*((_DWORD *)v1 + 15);
    v4 = 0;
    if ( v3 )
    {
      do
      {
        if ( v3[1] == (int *)1 )
        {
          v5 = NetUploadToNet((wchar_t *)v3[3], (int)v3[2]);
          v4 = v5;
          if ( v5 == -1032 || v5 == -1023 || v5 == -1305 )
            ErrorSetExtendedInfoSz1(0);
        }
        JetDeleteFileW((LPCWSTR)v3[3]);
        v6 = *v3;
        MemFree(v3);
        v3 = (int **)v6;
      }
      while ( v6 );
      v1 = this;
    }
    __wsplitpath_s((const wchar_t *)v1 + 36, Drive, 8u, Dir, 0xFFu, 0, 0, 0, 0);
    WCSCPY2(PathName, Drive, 0x105u);
    WCSCAT2(PathName, Dir, 0x105u);
    if ( !JetRemoveDirectoryW(PathName) )
      GetLastError();
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x100278d3  mov     edi, edi
0x100278d5  push    ebp
0x100278d6  mov     ebp, esp
0x100278d8  sub     esp, 42Ch
0x100278de  mov     eax, ___security_cookie
0x100278e3  xor     eax, ebp
0x100278e5  mov     [ebp+var_4], eax
0x100278e8  push    ebx
0x100278e9  push    esi
0x100278ea  mov     esi, ecx
0x100278ec  push    edi
0x100278ed  mov     [ebp+var_42C], esi
0x100278f3  lea     ecx, [esi+252h]
0x100278f9  call    _NetProtocolType@4; NetProtocolType(x)
0x100278fe  test    eax, eax
0x10027900  jz      loc_100279DA
0x10027906  mov     edi, [esi+3Ch]
0x10027909  xor     ebx, ebx
0x1002790b  test    edi, edi
0x1002790d  jz      short loc_10027974
0x1002790f  cmp     dword ptr [edi+4], 1
0x10027913  jnz     short loc_10027957
0x10027915  push    dword ptr [edi+8]
0x10027918  mov     ecx, [edi+0Ch]
0x1002791b  call    _NetUploadToNet@12; NetUploadToNet(x,x,x)
0x10027920  mov     ebx, eax
0x10027922  cmp     ebx, 0FFFFFBF8h
0x10027928  jnz     short loc_10027931
0x1002792a  mov     ecx, 0FFFFE020h
0x1002792f  jmp     short loc_1002794D
0x10027931  cmp     ebx, 0FFFFFC01h
0x10027937  jnz     short loc_10027940
0x10027939  mov     ecx, 0FFFFE01Fh
0x1002793e  jmp     short loc_1002794D
0x10027940  cmp     ebx, 0FFFFFAE7h
0x10027946  jnz     short loc_10027957
0x10027948  mov     ecx, 0FFFFDF94h
0x1002794d  mov     edx, [edi+8]
0x10027950  push    0
0x10027952  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x10027957  push    dword ptr [edi+0Ch]; lpFileName
0x1002795a  call    _JetDeleteFileW@4; JetDeleteFileW(x)
0x1002795f  mov     esi, [edi]
0x10027961  mov     ecx, edi
0x10027963  call    _MemFree@4; MemFree(x)
0x10027968  mov     edi, esi
0x1002796a  test    esi, esi
0x1002796c  jnz     short loc_1002790F
0x1002796e  mov     esi, [ebp+var_42C]
0x10027974  push    0; ExtCount
0x10027976  push    0; Ext
0x10027978  push    0; FilenameCount
0x1002797a  push    0; Filename
0x1002797c  push    0FFh; DirCount
0x10027981  lea     eax, [ebp+Dir]
0x10027987  push    eax; Dir
0x10027988  push    8; DriveCount
0x1002798a  lea     eax, [ebp+Drive]
0x1002798d  push    eax; Drive
0x1002798e  lea     eax, [esi+48h]
0x10027991  push    eax; FullPath
0x10027992  call    ds:__imp___wsplitpath_s
0x10027998  add     esp, 24h
0x1002799b  lea     edx, [ebp+Drive]
0x1002799e  mov     esi, 105h
0x100279a3  lea     ecx, [ebp+PathName]
0x100279a9  push    esi
0x100279aa  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100279af  push    esi
0x100279b0  lea     edx, [ebp+Dir]
0x100279b6  lea     ecx, [ebp+PathName]
0x100279bc  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100279c1  lea     eax, [ebp+PathName]
0x100279c7  push    eax; lpPathName
0x100279c8  call    _JetRemoveDirectoryW@4; JetRemoveDirectoryW(x)
0x100279cd  cmp     eax, 1
0x100279d0  jz      short loc_100279D8
0x100279d2  call    ds:__imp__GetLastError@0; GetLastError()
0x100279d8  mov     eax, ebx
0x100279da  mov     ecx, [ebp+var_4]
0x100279dd  pop     edi
0x100279de  pop     esi
0x100279df  xor     ecx, ebp; StackCookie
0x100279e1  pop     ebx
0x100279e2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100279e7  leave
0x100279e8  retn
```
