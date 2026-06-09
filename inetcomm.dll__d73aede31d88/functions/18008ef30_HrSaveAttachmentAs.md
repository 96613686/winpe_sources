# HrSaveAttachmentAs

- ea: `0x18008ef30`
- end: `0x18008f1fc`
- name: `HrSaveAttachmentAs`
- size: `716`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x18008e760`

## callees

- `0x1800055bc`
- `0x18008e2f0`
- `0x18008ed30`
- `0x18008ef30`
- `0x1800cacb8`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!ReplaceCharsW` at `0x18008f041`
- `MSOERT2!ReplaceCharsW` at `0x18008f041`
- `SHLWAPI!PathFindExtensionW` at `0x18008efec`
- `SHLWAPI!PathFindExtensionW` at `0x18008efec`
- `SHLWAPI!PathFileExistsW` at `0x18008f0ea`
- `SHLWAPI!PathFileExistsW` at `0x18008f0ea`
- `KERNEL32!DeleteFileW` at `0x18008f1c2`
- `KERNEL32!DeleteFileW` at `0x18008f1c2`
- `KERNEL32!CopyFileW` at `0x18008f108`
- `KERNEL32!CopyFileW` at `0x18008f108`
- `USER32!LoadStringW` at `0x18008f02d`
- `USER32!LoadStringW` at `0x18008f088`
- `USER32!LoadStringW` at `0x18008f14b`
- `USER32!LoadStringW` at `0x18008f02d`
- `USER32!LoadStringW` at `0x18008f088`
- `USER32!LoadStringW` at `0x18008f14b`

## pseudocode

```c
__int64 __fastcall HrSaveAttachmentAs(HWND a1, __int64 a2, __int64 a3, int a4)
{
  int v8; // ebx
  LPWSTR ExtensionW; // rsi
  const WCHAR *lpstrDefExt; // rax
  __int64 v11; // rdx
  void *v13; // [rsp+20h] [rbp-E0h] BYREF
  struct tagOFNW v14; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR NewFileName[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR v16[512]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR Buffer[512]; // [rsp+6E0h] [rbp+5E0h] BYREF

  v8 = -2147024809;
  memset_0(&v14, 0, sizeof(v14));
  memset_0(v16, 0, sizeof(v16));
  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(NewFileName, 0, 0x208u);
  v13 = 0;
  if ( a2 && a3 )
  {
    StringCchCopyW(NewFileName, 0x104u, (const unsigned __int16 *)(a3 + 1040));
    ExtensionW = PathFindExtensionW((LPCWSTR)(a3 + 1040));
    memset_0(&v14, 0, sizeof(v14));
    v14.lStructSize = 152;
    v14.hwndOwner = a1;
    LoadStringW(g_hLocRes, 0x494u, Buffer, 512);
    ReplaceCharsW(Buffer, 124);
    v14.lpstrFilter = Buffer;
    v14.nMaxFile = 260;
    v14.lpstrFile = NewFileName;
    v14.nFilterIndex = 1;
    LoadStringW(g_hLocRes, 0x493u, v16, 512);
    v14.lpstrTitle = v16;
    if ( ExtensionW && *ExtensionW )
    {
      lpstrDefExt = v14.lpstrDefExt;
      if ( ExtensionW[1] )
        lpstrDefExt = ExtensionW + 1;
      v14.lpstrDefExt = lpstrDefExt;
    }
    v14.Flags = 34830;
    if ( (unsigned int)HrAthGetFileNameW(&v14) )
    {
      return (unsigned int)-2147217398;
    }
    else
    {
      v11 = *(_QWORD *)(a3 + 1584);
      if ( v11 )
      {
        v8 = HrSaveAttachToFile(a2, v11, NewFileName);
        if ( v8 < 0 )
          return (unsigned int)v8;
      }
      else
      {
        if ( !PathFileExistsW((LPCWSTR)(a3 + 1040)) )
          return (unsigned int)-2147217323;
        if ( !CopyFileW((LPCWSTR)(a3 + 1040), NewFileName, 1) )
          return (unsigned int)-2147467259;
      }
      LoadStringW(g_hLocRes, 0x57Au, v16, 512);
      v8 = CreateAttachmentServices(v16, &IID_IAttachmentExecute, &v13);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(void *, WCHAR *))(*(_QWORD *)v13 + 40LL))(v13, NewFileName);
        if ( v8 >= 0 )
        {
          if ( a4 )
            (*(void (__fastcall **)(void *, const wchar_t *))(*(_QWORD *)v13 + 64LL))(v13, L"about:internet");
          v8 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v13 + 88LL))(v13);
          if ( v8 < 0 )
            DeleteFileW(NewFileName);
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18008ef30  push    rbp
0x18008ef32  push    rbx
0x18008ef33  push    rsi
0x18008ef34  push    rdi
0x18008ef35  push    r12
0x18008ef37  push    r14
0x18008ef39  push    r15
0x18008ef3b  lea     rbp, [rsp-9F0h]
0x18008ef43  sub     rsp, 0AF0h
0x18008ef4a  mov     rax, cs:__security_cookie
0x18008ef51  xor     rax, rsp
0x18008ef54  mov     [rbp+0A20h+var_40], rax
0x18008ef5b  mov     rdi, r8
0x18008ef5e  mov     r14, rdx
0x18008ef61  mov     r12, rcx
0x18008ef64  xor     edx, edx; Val
0x18008ef66  mov     r8d, 98h; Size
0x18008ef6c  lea     rcx, [rsp+0B20h+var_AF0]; void *
0x18008ef71  mov     r15d, r9d
0x18008ef74  mov     ebx, 80070057h
0x18008ef79  call    memset_0
0x18008ef7e  mov     esi, 400h
0x18008ef83  lea     rcx, [rbp+0A20h+var_840]; void *
0x18008ef8a  mov     r8d, esi; Size
0x18008ef8d  xor     edx, edx; Val
0x18008ef8f  call    memset_0
0x18008ef94  mov     r8d, esi; Size
0x18008ef97  lea     rcx, [rbp+0A20h+Buffer]; void *
0x18008ef9e  xor     edx, edx; Val
0x18008efa0  call    memset_0
0x18008efa5  xor     edx, edx; Val
0x18008efa7  lea     rcx, [rbp+0A20h+NewFileName]; void *
0x18008efab  mov     r8d, 208h; Size
0x18008efb1  call    memset_0
0x18008efb6  mov     [rsp+0B20h+var_B00], 0
0x18008efbf  test    r14, r14
0x18008efc2  jz      loc_18008F1D9
0x18008efc8  test    rdi, rdi
0x18008efcb  jz      loc_18008F1D9
0x18008efd1  lea     rbx, [rdi+410h]
0x18008efd8  mov     edx, 104h; unsigned __int64
0x18008efdd  mov     r8, rbx; unsigned __int16 *
0x18008efe0  lea     rcx, [rbp+0A20h+NewFileName]; unsigned __int16 *
0x18008efe4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008efe9  mov     rcx, rbx; pszPath
0x18008efec  call    cs:__imp_PathFindExtensionW
0x18008eff2  xor     edx, edx; Val
0x18008eff4  lea     rcx, [rsp+0B20h+var_AF0]; void *
0x18008eff9  mov     r8d, 98h; Size
0x18008efff  mov     rsi, rax
0x18008f002  call    memset_0
0x18008f007  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18008f00e  lea     r8, [rbp+0A20h+Buffer]; lpBuffer
0x18008f015  mov     r9d, 200h; cchBufferMax
0x18008f01b  mov     [rsp+0B20h+var_AF0.lStructSize], 98h
0x18008f023  mov     edx, 494h; uID
0x18008f028  mov     [rsp+0B20h+var_AF0.hwndOwner], r12
0x18008f02d  call    cs:__imp_LoadStringW
0x18008f033  xor     r8d, r8d
0x18008f036  lea     rcx, [rbp+0A20h+Buffer]
0x18008f03d  lea     edx, [r8+7Ch]
0x18008f041  call    cs:__imp_ReplaceCharsW
0x18008f047  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18008f04e  lea     rax, [rbp+0A20h+Buffer]
0x18008f055  mov     [rsp+0B20h+var_AF0.lpstrFilter], rax
0x18008f05a  lea     r8, [rbp+0A20h+var_840]; lpBuffer
0x18008f061  lea     rax, [rbp+0A20h+NewFileName]
0x18008f065  mov     [rsp+0B20h+var_AF0.nMaxFile], 104h
0x18008f06d  mov     r12d, 1
0x18008f073  mov     [rsp+0B20h+var_AF0.lpstrFile], rax
0x18008f078  mov     r9d, 200h; cchBufferMax
0x18008f07e  mov     [rsp+0B20h+var_AF0.nFilterIndex], r12d
0x18008f083  mov     edx, 493h; uID
0x18008f088  call    cs:__imp_LoadStringW
0x18008f08e  lea     rax, [rbp+0A20h+var_840]
0x18008f095  mov     [rbp+0A20h+var_AF0.lpstrTitle], rax
0x18008f099  test    rsi, rsi
0x18008f09c  jz      short loc_18008F0BA
0x18008f09e  xor     eax, eax
0x18008f0a0  cmp     ax, [rsi]
0x18008f0a3  jz      short loc_18008F0BA
0x18008f0a5  mov     rax, [rbp+0A20h+var_AF0.lpstrDefExt]
0x18008f0a9  lea     rcx, [rsi+2]
0x18008f0ad  xor     edx, edx
0x18008f0af  cmp     dx, [rcx]
0x18008f0b2  cmovnz  rax, rcx
0x18008f0b6  mov     [rbp+0A20h+var_AF0.lpstrDefExt], rax
0x18008f0ba  xor     edx, edx
0x18008f0bc  mov     [rbp+0A20h+var_AF0.Flags], 880Eh
0x18008f0c3  lea     rcx, [rsp+0B20h+var_AF0]; LPOPENFILENAMEW
0x18008f0c8  call    HrAthGetFileNameW
0x18008f0cd  test    eax, eax
0x18008f0cf  jz      short loc_18008F0DB
0x18008f0d1  mov     ebx, 8004100Ah
0x18008f0d6  jmp     loc_18008F1D9
0x18008f0db  mov     rdx, [rdi+630h]
0x18008f0e2  test    rdx, rdx
0x18008f0e5  jnz     short loc_18008F11C
0x18008f0e7  mov     rcx, rbx; pszPath
0x18008f0ea  call    cs:__imp_PathFileExistsW
0x18008f0f0  test    eax, eax
0x18008f0f2  jnz     short loc_18008F0FE
0x18008f0f4  mov     ebx, 80041055h
0x18008f0f9  jmp     loc_18008F1D9
0x18008f0fe  mov     r8d, r12d; bFailIfExists
0x18008f101  lea     rdx, [rbp+0A20h+NewFileName]; lpNewFileName
0x18008f105  mov     rcx, rbx; lpExistingFileName
0x18008f108  call    cs:__imp_CopyFileW
0x18008f10e  test    eax, eax
0x18008f110  jnz     short loc_18008F132
0x18008f112  mov     ebx, 80004005h
0x18008f117  jmp     loc_18008F1D9
0x18008f11c  lea     r8, [rbp+0A20h+NewFileName]
0x18008f120  mov     rcx, r14
0x18008f123  call    HrSaveAttachToFile
0x18008f128  mov     ebx, eax
0x18008f12a  test    eax, eax
0x18008f12c  js      loc_18008F1D9
0x18008f132  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18008f139  lea     r8, [rbp+0A20h+var_840]; lpBuffer
0x18008f140  mov     r9d, 200h; cchBufferMax
0x18008f146  mov     edx, 57Ah; uID
0x18008f14b  call    cs:__imp_LoadStringW
0x18008f151  lea     r8, [rsp+0B20h+var_B00]; void **
0x18008f156  lea     rdx, IID_IAttachmentExecute; struct _GUID *
0x18008f15d  lea     rcx, [rbp+0A20h+var_840]; unsigned __int16 *
0x18008f164  call    ?CreateAttachmentServices@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; CreateAttachmentServices(ushort const *,_GUID const &,void * *)
0x18008f169  mov     ebx, eax
0x18008f16b  test    eax, eax
0x18008f16d  js      short loc_18008F1D9
0x18008f16f  mov     rcx, [rsp+0B20h+var_B00]
0x18008f174  lea     rdx, [rbp+0A20h+NewFileName]
0x18008f178  mov     rax, [rcx]
0x18008f17b  mov     rax, [rax+28h]
0x18008f17f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f184  mov     ebx, eax
0x18008f186  test    eax, eax
0x18008f188  js      short loc_18008F1C8
0x18008f18a  test    r15d, r15d
0x18008f18d  jz      short loc_18008F1A7
0x18008f18f  mov     rcx, [rsp+0B20h+var_B00]
0x18008f194  lea     rdx, aAboutInternet; "about:internet"
0x18008f19b  mov     rax, [rcx]
0x18008f19e  mov     rax, [rax+40h]
0x18008f1a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f1a7  mov     rcx, [rsp+0B20h+var_B00]
0x18008f1ac  mov     rax, [rcx]
0x18008f1af  mov     rax, [rax+58h]
0x18008f1b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f1b8  mov     ebx, eax
0x18008f1ba  test    eax, eax
0x18008f1bc  jns     short loc_18008F1C8
0x18008f1be  lea     rcx, [rbp+0A20h+NewFileName]; lpFileName
0x18008f1c2  call    cs:__imp_DeleteFileW
0x18008f1c8  mov     rcx, [rsp+0B20h+var_B00]
0x18008f1cd  mov     rax, [rcx]
0x18008f1d0  mov     rax, [rax+10h]
0x18008f1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f1d9  mov     eax, ebx
0x18008f1db  mov     rcx, [rbp+0A20h+var_40]
0x18008f1e2  xor     rcx, rsp; StackCookie
0x18008f1e5  call    __security_check_cookie
0x18008f1ea  add     rsp, 0AF0h
0x18008f1f1  pop     r15
0x18008f1f3  pop     r14
0x18008f1f5  pop     r12
0x18008f1f7  pop     rdi
0x18008f1f8  pop     rsi
0x18008f1f9  pop     rbx
0x18008f1fa  pop     rbp
0x18008f1fb  retn
```
