# CFontManager::_DisplaySingleFontRemoveConfirmation(HWND__ *,IEnumFontNames *,int *)

- ea: `0x18001e31c`
- end: `0x18001e53d`
- name: `?_DisplaySingleFontRemoveConfirmation@CFontManager@@AEAAJPEAUHWND__@@PEAUIEnumFontNames@@PEAH@Z`
- size: `545`
- prototype: `__int64 __fastcall(CFontManager *__hidden this, HWND, struct IEnumFontNames *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18001dcc8`

## callees

- `0x180006668`
- `0x18001e31c`
- `0x18001f560`
- `0x1800223e8`
- `0x180022564`
- `0x18003104a`
- `0x180031070`
- `0x180031100`
- `0x180032010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18001e509`
- `SHELL32!__imp_ILFree` at `0x18001e509`
- `SHLWAPI!PathFileExistsW` at `0x18001e38c`
- `SHLWAPI!PathFileExistsW` at `0x18001e38c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001e3d0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001e3d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3da`

## pseudocode

```c
__int64 __fastcall CFontManager::_DisplaySingleFontRemoveConfirmation(
        CFontManager *this,
        HWND a2,
        struct IEnumFontNames *a3,
        int *a4)
{
  __int64 v4; // rax
  int v8; // ebx
  signed int LastError; // eax
  __int64 v10; // r8
  int v12; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR pszPath; // [rsp+28h] [rbp-D8h] BYREF
  LPITEMIDLIST pidl; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  HWND v16; // [rsp+44h] [rbp-BCh]
  HINSTANCE v17; // [rsp+4Ch] [rbp-B4h]
  int v18; // [rsp+54h] [rbp-ACh]
  int v19; // [rsp+58h] [rbp-A8h]
  __int64 v20; // [rsp+5Ch] [rbp-A4h]
  __int64 v21; // [rsp+64h] [rbp-9Ch]
  __int64 v22; // [rsp+6Ch] [rbp-94h]
  unsigned __int16 *v23; // [rsp+74h] [rbp-8Ch]
  int v24; // [rsp+88h] [rbp-78h]
  unsigned __int16 v25[384]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR Buffer[1024]; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned __int16 v27[1024]; // [rsp+BE0h] [rbp+AE0h] BYREF

  v4 = *(_QWORD *)a3;
  pszPath = 0;
  v8 = (*(__int64 (__fastcall **)(struct IEnumFontNames *, LPCWSTR *))(v4 + 24))(a3, &pszPath);
  if ( v8 >= 0 )
  {
    v8 = -2147467259;
    if ( pszPath )
    {
      if ( PathFileExistsW(pszPath) )
      {
        memset_0(Buffer, 0, sizeof(Buffer));
        if ( LoadStringW(g_hInstance, 0x1FA9u, Buffer, 1024) )
          goto LABEL_9;
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        if ( v8 >= 0 )
        {
LABEL_9:
          pidl = 0;
          v8 = FID_CreateFromPath(pszPath, &pidl);
          if ( v8 >= 0 )
          {
            v8 = FID_Description(pidl, v25, 0x180u);
            if ( v8 >= 0 )
            {
              memset_0(v27, 0, sizeof(v27));
              v8 = StringCchPrintfW(v27, 0x400u, Buffer, v25);
              if ( v8 >= 0 )
              {
                memset_0(&v15, 0, 0xA0u);
                v17 = g_hInstance;
                v16 = a2;
                v23 = v27;
                v15 = 160;
                v19 = 6;
                v18 = 8;
                v24 = 6;
                v21 = 412;
                v20 = 8103;
                v22 = 8104;
                v12 = 0;
                v8 = IsolationAwareTaskDialogIndirect(&v15, &v12, v10, 0);
                if ( v8 >= 0 )
                  *a4 = v12 == 6;
              }
            }
          }
          ILFree(pidl);
        }
      }
      else
      {
        v8 = 0;
        *a4 = 1;
      }
      (*(void (__fastcall **)(struct IEnumFontNames *))(*(_QWORD *)a3 + 32LL))(a3);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001e31c  push    rbp
0x18001e31e  push    rbx
0x18001e31f  push    rsi
0x18001e320  push    rdi
0x18001e321  push    r14
0x18001e323  lea     rbp, [rsp-12F0h]
0x18001e32b  mov     eax, 13F0h
0x18001e330  call    _alloca_probe
0x18001e335  sub     rsp, rax
0x18001e338  mov     rax, cs:__security_cookie
0x18001e33f  xor     rax, rsp
0x18001e342  mov     [rbp+1310h+var_30], rax
0x18001e349  mov     rax, [r8]
0x18001e34c  mov     r14, rdx
0x18001e34f  lea     rdx, [rsp+1410h+pszPath]
0x18001e354  mov     [rsp+1410h+pszPath], 0
0x18001e35d  mov     rcx, r8
0x18001e360  mov     rsi, r9
0x18001e363  mov     rdi, r8
0x18001e366  mov     rax, [rax+18h]
0x18001e36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e36f  mov     ebx, eax
0x18001e371  test    eax, eax
0x18001e373  js      loc_18001E51E
0x18001e379  mov     rcx, [rsp+1410h+pszPath]; pszPath
0x18001e37e  mov     ebx, 80004005h
0x18001e383  test    rcx, rcx
0x18001e386  jz      loc_18001E51E
0x18001e38c  call    cs:__imp_PathFileExistsW
0x18001e392  test    eax, eax
0x18001e394  jnz     short loc_18001E3A3
0x18001e396  xor     ebx, ebx
0x18001e398  mov     dword ptr [rsi], 1
0x18001e39e  jmp     loc_18001E50F
0x18001e3a3  xor     edx, edx; Val
0x18001e3a5  lea     rcx, [rbp+1310h+Buffer]; void *
0x18001e3ac  mov     r8d, 800h; Size
0x18001e3b2  call    memset_0
0x18001e3b7  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18001e3be  lea     r8, [rbp+1310h+Buffer]; lpBuffer
0x18001e3c5  mov     r9d, 400h; cchBufferMax
0x18001e3cb  mov     edx, 1FA9h; uID
0x18001e3d0  call    cs:__imp_LoadStringW
0x18001e3d6  test    eax, eax
0x18001e3d8  jnz     short loc_18001E3F7
0x18001e3da  call    cs:__imp_GetLastError
0x18001e3e0  mov     ebx, eax
0x18001e3e2  test    eax, eax
0x18001e3e4  jle     short loc_18001E3EF
0x18001e3e6  movzx   ebx, ax
0x18001e3e9  or      ebx, 80070000h
0x18001e3ef  test    ebx, ebx
0x18001e3f1  js      loc_18001E50F
0x18001e3f7  mov     rcx, [rsp+1410h+pszPath]; unsigned __int16 *
0x18001e3fc  lea     rdx, [rsp+1410h+pidl]; struct _ITEMIDLIST **
0x18001e401  mov     [rsp+1410h+pidl], 0
0x18001e40a  call    ?FID_CreateFromPath@@YAJPEBGPEAPEFAU_ITEMIDLIST@@@Z; FID_CreateFromPath(ushort const *,_ITEMIDLIST * *)
0x18001e40f  mov     ebx, eax
0x18001e411  test    eax, eax
0x18001e413  js      loc_18001E504
0x18001e419  mov     rcx, [rsp+1410h+pidl]; struct _ITEMIDLIST *
0x18001e41e  lea     rdx, [rbp+1310h+var_1330]; unsigned __int16 *
0x18001e422  mov     r8d, 180h; unsigned __int64
0x18001e428  call    ?FID_Description@@YAJPEFBU_ITEMIDLIST@@PEAG_K@Z; FID_Description(_ITEMIDLIST const *,ushort *,unsigned __int64)
0x18001e42d  mov     ebx, eax
0x18001e42f  test    eax, eax
0x18001e431  js      loc_18001E504
0x18001e437  xor     edx, edx; Val
0x18001e439  lea     rcx, [rbp+1310h+var_830]; void *
0x18001e440  mov     r8d, 800h; Size
0x18001e446  call    memset_0
0x18001e44b  lea     r9, [rbp+1310h+var_1330]
0x18001e44f  mov     edx, 400h; unsigned __int64
0x18001e454  lea     r8, [rbp+1310h+Buffer]; unsigned __int16 *
0x18001e45b  lea     rcx, [rbp+1310h+var_830]; unsigned __int16 *
0x18001e462  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e467  mov     ebx, eax
0x18001e469  test    eax, eax
0x18001e46b  js      loc_18001E504
0x18001e471  mov     ebx, 0A0h
0x18001e476  lea     rcx, [rsp+1410h+var_13D0]; void *
0x18001e47b  mov     r8d, ebx; Size
0x18001e47e  xor     edx, edx; Val
0x18001e480  call    memset_0
0x18001e485  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18001e48c  lea     rdx, [rsp+1410h+var_13F0]
0x18001e491  mov     [rsp+1410h+var_13C4], rax
0x18001e496  lea     rcx, [rsp+1410h+var_13D0]
0x18001e49b  mov     [rsp+1410h+var_13CC], r14
0x18001e4a0  lea     rax, [rbp+1310h+var_830]
0x18001e4a7  mov     r14d, 6
0x18001e4ad  mov     [rsp+1410h+var_139C], rax
0x18001e4b2  xor     r9d, r9d
0x18001e4b5  mov     [rsp+1410h+var_13D0], ebx
0x18001e4b9  mov     [rsp+1410h+var_13B8], r14d
0x18001e4be  mov     [rsp+1410h+var_13BC], 8
0x18001e4c6  mov     [rbp+1310h+var_1388], r14d
0x18001e4ca  mov     [rsp+1410h+var_13AC], 19Ch
0x18001e4d3  mov     [rsp+1410h+var_13B4], 1FA7h
0x18001e4dc  mov     [rsp+1410h+var_13A4], 1FA8h
0x18001e4e5  mov     [rsp+1410h+var_13F0], 0
0x18001e4ed  call    IsolationAwareTaskDialogIndirect
0x18001e4f2  mov     ebx, eax
0x18001e4f4  test    eax, eax
0x18001e4f6  js      short loc_18001E504
0x18001e4f8  xor     eax, eax
0x18001e4fa  cmp     [rsp+1410h+var_13F0], r14d
0x18001e4ff  setz    al
0x18001e502  mov     [rsi], eax
0x18001e504  mov     rcx, [rsp+1410h+pidl]; pidl
0x18001e509  call    cs:__imp_ILFree
0x18001e50f  mov     rax, [rdi]
0x18001e512  mov     rcx, rdi
0x18001e515  mov     rax, [rax+20h]
0x18001e519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e51e  mov     eax, ebx
0x18001e520  mov     rcx, [rbp+1310h+var_30]
0x18001e527  xor     rcx, rsp; StackCookie
0x18001e52a  call    __security_check_cookie
0x18001e52f  add     rsp, 13F0h
0x18001e536  pop     r14
0x18001e538  pop     rdi
0x18001e539  pop     rsi
0x18001e53a  pop     rbx
0x18001e53b  pop     rbp
0x18001e53c  retn
```
