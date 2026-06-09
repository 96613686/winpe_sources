# DetailsView::OnCmdExport(void)

- ea: `0x18000d138`
- end: `0x18000d4c8`
- name: `?OnCmdExport@DetailsView@@AEAA_JXZ`
- size: `912`
- prototype: `__int64 __fastcall(DetailsView *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000de10`

## callees

- `0x180001510`
- `0x1800022b4`
- `0x18000d138`
- `0x18001ab24`
- `0x18001c9a4`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000d238`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000d238`
- `ole32!ReleaseStgMedium` at `0x18000d411`
- `ole32!ReleaseStgMedium` at `0x18000d411`
- `ole32!StgCreateDocfile` at `0x18000d2de`
- `ole32!StgCreateDocfile` at `0x18000d2de`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall DetailsView::OnCmdExport(HWND *this)
{
  HRESULT v2; // ebx
  unsigned int v3; // r8d
  unsigned int v4; // edx
  __int64 v6; // [rsp+50h] [rbp-3B8h] BYREF
  __int64 v7; // [rsp+58h] [rbp-3B0h] BYREF
  IStorage *ppstgOpen; // [rsp+60h] [rbp-3A8h] BYREF
  STGMEDIUM v9; // [rsp+68h] [rbp-3A0h] BYREF
  unsigned __int16 v10; // [rsp+80h] [rbp-388h] BYREF
  int v11; // [rsp+82h] [rbp-386h]
  __int16 v12; // [rsp+86h] [rbp-382h]
  __int64 v13; // [rsp+88h] [rbp-380h]
  int v14; // [rsp+90h] [rbp-378h]
  int v15; // [rsp+94h] [rbp-374h]
  __int64 v16; // [rsp+98h] [rbp-370h]
  tagOFNW v17; // [rsp+A0h] [rbp-368h] BYREF
  WCHAR Buffer[80]; // [rsp+140h] [rbp-2C8h] BYREF
  _BYTE v19[528]; // [rsp+1E0h] [rbp-228h] BYREF

  try
  {
    v2 = (*(__int64 (__fastcall **)(HWND *))*this)(this);
    if ( v2 >= 0 )
    {
      v11 = 0;
      v12 = 0;
      v16 = 4;
      v10 = DetailsView::DataObject::m_CF_NtDiskQuotaExport;
      v14 = 1;
      v13 = 0;
      v15 = -1;
      v2 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(MEMORY[0] + 40LL))(0, &v10);
      if ( v2 < 0 )
        goto LABEL_24;
      memset_0(v19, 0, 0x208u);
      memset_0(Buffer, 0, sizeof(Buffer));
      LoadStringW(g_hInstDll, 0x9EBFu, Buffer, 80);
      memset_0(&v17, 0, sizeof(v17));
      v17.lStructSize = 152;
      v17.hwndOwner = this[12];
      v17.hInstance = g_hInstDll;
      v17.lpstrFile = (LPWSTR)v19;
      v17.lpstrTitle = Buffer;
      v17.nMaxFile = 260;
      v17.Flags = 2062;
      if ( !GetSaveFileNameW(&v17) )
        goto LABEL_24;
      ppstgOpen = 0;
      v2 = StgCreateDocfile(v17.lpstrFile, 0x1012u, 0, &ppstgOpen);
      if ( v2 >= 0 )
      {
        v7 = 0;
        v2 = ((__int64 (__fastcall *)(IStorage *, const wchar_t *, __int64, _QWORD, _DWORD, __int64 *))ppstgOpen->lpVtbl->CreateStream)(
               ppstgOpen,
               L"NT DISKQUOTA IMPORTEXPORT",
               4114,
               0,
               0,
               &v7);
        if ( v2 >= 0 )
        {
          v9.tymed = 0;
          *(_OWORD *)&v9.hBitmap = 0;
          v2 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, STGMEDIUM *))(MEMORY[0] + 24LL))(0, &v10, &v9);
          if ( v2 >= 0 )
          {
            v6 = 0;
            v2 = (*(__int64 (__fastcall **)(HBITMAP, _QWORD, __int64, __int64 *))(*(_QWORD *)v9.hBitmap + 40LL))(
                   v9.hBitmap,
                   0,
                   1,
                   &v6);
            if ( v2 >= 0 )
            {
              v2 = (*(__int64 (__fastcall **)(HBITMAP, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v9.hBitmap + 40LL))(
                     v9.hBitmap,
                     0,
                     0,
                     0);
              if ( v2 >= 0 )
              {
                (*(void (__fastcall **)(HBITMAP, __int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v9.hBitmap + 56LL))(
                  v9.hBitmap,
                  v7,
                  -1,
                  0,
                  0);
                (*(void (__fastcall **)(HBITMAP, __int64, _QWORD, _QWORD))(*(_QWORD *)v9.hBitmap + 40LL))(
                  v9.hBitmap,
                  v6,
                  0,
                  0);
              }
            }
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          ReleaseStgMedium(&v9);
        }
        ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
        if ( v2 >= 0 )
          goto LABEL_24;
      }
      if ( v2 == -2147287036 )
      {
        v4 = 40589;
        goto LABEL_23;
      }
      if ( v2 == -2147287035 )
      {
        v4 = 40586;
        goto LABEL_23;
      }
      if ( v2 != -2147287032 )
      {
        if ( v2 == -2147286788 )
        {
          v4 = 40588;
          goto LABEL_23;
        }
        if ( v2 != -2147024882 )
        {
          v4 = 40585;
LABEL_23:
          DiskQuotaMsgBox(this[12], v4, v3, 0x10u);
LABEL_24:
          (*(void (__fastcall **)(_QWORD))(MEMORY[0] + 16LL))(0);
          return (unsigned __int64)(unsigned int)~v2 >> 31;
        }
      }
      v4 = 40587;
      goto LABEL_23;
    }
  }
  catch ( CAllocException )
  {
    throw;
  }
  return (unsigned __int64)(unsigned int)~v2 >> 31;
}

```

## disassembly

```asm
0x18000d138  mov     [rsp+arg_8], rbx
0x18000d13d  mov     [rsp+arg_10], rdi
0x18000d142  push    r14
0x18000d144  sub     rsp, 400h
0x18000d14b  mov     rax, cs:__security_cookie
0x18000d152  xor     rax, rsp
0x18000d155  mov     [rsp+408h+var_18], rax
0x18000d15d  mov     rdi, rcx
0x18000d160  xor     r14d, r14d
0x18000d163  mov     [rsp+408h+var_3C8], r14
0x18000d168  mov     rax, [rcx]
0x18000d16b  lea     r8, [rsp+408h+var_3C8]
0x18000d170  lea     rdx, _GUID_0000010e_0000_0000_c000_000000000046
0x18000d177  mov     rax, [rax]
0x18000d17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d17f  mov     ebx, eax
0x18000d181  test    eax, eax
0x18000d183  js      loc_18000D49A
0x18000d189  mov     [rsp+408h+var_386], r14d
0x18000d191  mov     [rsp+408h+var_382], r14w
0x18000d19a  mov     [rsp+408h+var_370], 4
0x18000d1a6  movzx   eax, cs:?m_CF_NtDiskQuotaExport@DataObject@DetailsView@@2GA; ushort DetailsView::DataObject::m_CF_NtDiskQuotaExport
0x18000d1ad  mov     [rsp+408h+var_388], ax
0x18000d1b5  mov     [rsp+408h+var_378], 1
0x18000d1c0  mov     [rsp+408h+var_380], r14
0x18000d1c8  mov     [rsp+408h+var_374], 0FFFFFFFFh
0x18000d1d3  mov     rcx, [rsp+408h+var_3C8]
0x18000d1d8  mov     rax, [rcx]
0x18000d1db  lea     rdx, [rsp+408h+var_388]
0x18000d1e3  mov     rax, [rax+28h]
0x18000d1e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1ec  mov     ebx, eax
0x18000d1ee  test    eax, eax
0x18000d1f0  js      loc_18000D484
0x18000d1f6  xor     edx, edx; Val
0x18000d1f8  mov     r8d, 208h; Size
0x18000d1fe  lea     rcx, [rsp+408h+var_228]; void *
0x18000d206  call    memset_0
0x18000d20b  xor     edx, edx; Val
0x18000d20d  mov     r8d, 0A0h; Size
0x18000d213  lea     rcx, [rsp+408h+Buffer]; void *
0x18000d21b  call    memset_0
0x18000d220  lea     r9d, [r14+50h]; cchBufferMax
0x18000d224  lea     r8, [rsp+408h+Buffer]; lpBuffer
0x18000d22c  mov     edx, 9EBFh; uID
0x18000d231  mov     rcx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18000d238  call    cs:__imp_LoadStringW
0x18000d23e  xor     edx, edx; Val
0x18000d240  mov     r8d, 98h; Size
0x18000d246  lea     rcx, [rsp+408h+var_368]; void *
0x18000d24e  call    memset_0
0x18000d253  mov     [rsp+408h+var_368.lStructSize], 98h
0x18000d25e  mov     rax, [rdi+60h]
0x18000d262  mov     [rsp+408h+var_368.hwndOwner], rax
0x18000d26a  mov     rax, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstDll
0x18000d271  mov     [rsp+408h+var_368.hInstance], rax
0x18000d279  lea     rax, [rsp+408h+var_228]
0x18000d281  mov     [rsp+408h+var_368.lpstrFile], rax
0x18000d289  lea     rax, [rsp+408h+Buffer]
0x18000d291  mov     [rsp+408h+var_368.lpstrTitle], rax
0x18000d299  mov     [rsp+408h+var_368.nMaxFile], 104h
0x18000d2a4  mov     [rsp+408h+var_368.Flags], 80Eh
0x18000d2af  lea     rcx, [rsp+408h+var_368]; LPOPENFILENAMEW
0x18000d2b7  call    GetSaveFileNameW
0x18000d2bc  test    eax, eax
0x18000d2be  jz      loc_18000D484
0x18000d2c4  mov     [rsp+408h+ppstgOpen], r14
0x18000d2c9  lea     r9, [rsp+408h+ppstgOpen]; ppstgOpen
0x18000d2ce  xor     r8d, r8d; reserved
0x18000d2d1  mov     edx, 1012h; grfMode
0x18000d2d6  mov     rcx, [rsp+408h+var_368.lpstrFile]; pwcsName
0x18000d2de  call    cs:__imp_StgCreateDocfile
0x18000d2e4  mov     ebx, eax
0x18000d2e6  test    eax, eax
0x18000d2e8  js      loc_18000D42C
0x18000d2ee  mov     [rsp+408h+var_3B0], r14
0x18000d2f3  mov     rcx, [rsp+408h+ppstgOpen]
0x18000d2f8  mov     rax, [rcx]
0x18000d2fb  lea     rdx, [rsp+408h+var_3B0]
0x18000d300  mov     [rsp+408h+var_3E0], rdx
0x18000d305  mov     dword ptr [rsp+408h+var_3E8], r14d
0x18000d30a  xor     r9d, r9d
0x18000d30d  mov     r8d, 1012h
0x18000d313  lea     rdx, aNtDiskquotaImp; "NT DISKQUOTA IMPORTEXPORT"
0x18000d31a  mov     rax, [rax+18h]
0x18000d31e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d323  mov     ebx, eax
0x18000d325  test    eax, eax
0x18000d327  js      loc_18000D417
0x18000d32d  mov     [rsp+408h+var_3A0.tymed], r14d
0x18000d332  xorps   xmm0, xmm0
0x18000d335  movdqu  xmmword ptr [rsp+408h+var_3A0.8], xmm0
0x18000d33b  mov     rcx, [rsp+408h+var_3C8]
0x18000d340  mov     rax, [rcx]
0x18000d343  lea     r8, [rsp+408h+var_3A0]
0x18000d348  lea     rdx, [rsp+408h+var_388]
0x18000d350  mov     rax, [rax+18h]
0x18000d354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d359  mov     ebx, eax
0x18000d35b  test    eax, eax
0x18000d35d  js      loc_18000D3FA
0x18000d363  mov     [rsp+408h+var_3C0], r14
0x18000d368  mov     [rsp+408h+var_3B8], r14
0x18000d36d  mov     rcx, qword ptr [rsp+408h+var_3A0.8]
0x18000d372  mov     rax, [rcx]
0x18000d375  lea     r9, [rsp+408h+var_3B8]
0x18000d37a  lea     r8d, [r14+1]
0x18000d37e  mov     edx, r14d
0x18000d381  mov     rax, [rax+28h]
0x18000d385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d38a  mov     ebx, eax
0x18000d38c  test    eax, eax
0x18000d38e  js      short loc_18000D3FA
0x18000d390  mov     rcx, qword ptr [rsp+408h+var_3A0.8]
0x18000d395  mov     rax, [rcx]
0x18000d398  xor     r9d, r9d
0x18000d39b  xor     r8d, r8d
0x18000d39e  mov     edx, r14d
0x18000d3a1  mov     rax, [rax+28h]
0x18000d3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3aa  mov     ebx, eax
0x18000d3ac  test    eax, eax
0x18000d3ae  js      short loc_18000D3FA
0x18000d3b0  or      eax, 0FFFFFFFFh
0x18000d3b3  mov     dword ptr [rsp+408h+var_3C0], eax
0x18000d3b7  mov     dword ptr [rsp+408h+var_3C0+4], eax
0x18000d3bb  mov     rcx, qword ptr [rsp+408h+var_3A0.8]
0x18000d3c0  mov     rax, [rcx]
0x18000d3c3  mov     [rsp+408h+var_3E8], r14
0x18000d3c8  xor     r9d, r9d
0x18000d3cb  mov     r8, [rsp+408h+var_3C0]
0x18000d3d0  mov     rdx, [rsp+408h+var_3B0]
0x18000d3d5  mov     rax, [rax+38h]
0x18000d3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3de  mov     rcx, qword ptr [rsp+408h+var_3A0.8]
0x18000d3e3  mov     rax, [rcx]
0x18000d3e6  xor     r9d, r9d
0x18000d3e9  xor     r8d, r8d
0x18000d3ec  mov     rdx, [rsp+408h+var_3B8]
0x18000d3f1  mov     rax, [rax+28h]
0x18000d3f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3fa  mov     rcx, [rsp+408h+var_3B0]
0x18000d3ff  mov     rax, [rcx]
0x18000d402  mov     rax, [rax+10h]
0x18000d406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d40b  nop
0x18000d40c  lea     rcx, [rsp+408h+var_3A0]; LPSTGMEDIUM
0x18000d411  call    cs:__imp_ReleaseStgMedium
0x18000d417  mov     rcx, [rsp+408h+ppstgOpen]
0x18000d41c  mov     rax, [rcx]
0x18000d41f  mov     rax, [rax+10h]
0x18000d423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d428  test    ebx, ebx
0x18000d42a  jns     short loc_18000D484
0x18000d42c  cmp     ebx, 80030004h
0x18000d432  jz      short loc_18000D470
0x18000d434  cmp     ebx, 80030005h
0x18000d43a  jz      short loc_18000D469
0x18000d43c  cmp     ebx, 80030008h
0x18000d442  jz      short loc_18000D462
0x18000d444  cmp     ebx, 800300FCh
0x18000d44a  jz      short loc_18000D45B
0x18000d44c  cmp     ebx, 8007000Eh
0x18000d452  jz      short loc_18000D462
0x18000d454  mov     edx, 9E89h
0x18000d459  jmp     short loc_18000D475
0x18000d45b  mov     edx, 9E8Ch
0x18000d460  jmp     short loc_18000D475
0x18000d462  mov     edx, 9E8Bh
0x18000d467  jmp     short loc_18000D475
0x18000d469  mov     edx, 9E8Ah
0x18000d46e  jmp     short loc_18000D475
0x18000d470  mov     edx, 9E8Dh; unsigned int
0x18000d475  mov     r9d, 10h; unsigned int
0x18000d47b  mov     rcx, [rdi+60h]; hWnd
0x18000d47f  call    ?DiskQuotaMsgBox@@YAHPEAUHWND__@@III@Z; DiskQuotaMsgBox(HWND__ *,uint,uint,uint)
0x18000d484  mov     rcx, [rsp+408h+var_3C8]
0x18000d489  mov     rax, [rcx]
0x18000d48c  mov     rax, [rax+10h]
0x18000d490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d495  mov     [rsp+408h+var_3C8], r14
0x18000d49a  not     ebx
0x18000d49c  mov     eax, ebx
0x18000d49e  shr     rax, 1Fh
0x18000d4a2  mov     rcx, [rsp+408h+var_18]
0x18000d4aa  xor     rcx, rsp; StackCookie
0x18000d4ad  call    __security_check_cookie
0x18000d4b2  lea     r11, [rsp+408h+var_8]
0x18000d4ba  mov     rbx, [r11+18h]
0x18000d4be  mov     rdi, [r11+20h]
0x18000d4c2  mov     rsp, r11
0x18000d4c5  pop     r14
0x18000d4c7  retn
```
