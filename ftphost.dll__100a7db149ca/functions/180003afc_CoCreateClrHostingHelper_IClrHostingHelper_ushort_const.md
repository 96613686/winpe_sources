# CoCreateClrHostingHelper(IClrHostingHelper * *,ushort const *)

- ea: `0x180003afc`
- end: `0x180003ca4`
- name: `?CoCreateClrHostingHelper@@YAJPEAPEAUIClrHostingHelper@@PEBG@Z`
- size: `424`
- prototype: `__int64 __fastcall(struct IClrHostingHelper **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003800`

## callees

- `0x180001008`
- `0x180003afc`
- `0x180003cdc`
- `0x180003e28`
- `0x180005010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003b30`
- `KERNEL32!GetLastError` at `0x180003b30`
- `KERNEL32!GetProcAddress` at `0x180003b70`
- `KERNEL32!GetProcAddress` at `0x180003b70`
- `KERNEL32!FreeLibrary` at `0x180003c93`
- `KERNEL32!FreeLibrary` at `0x180003c93`
- `KERNEL32!LoadLibraryExW` at `0x180003b22`
- `KERNEL32!LoadLibraryExW` at `0x180003b22`

## string_xrefs

- `0x180003b17`: `mscoree.dll`
- `0x180003b66`: `CLRCreateInstance`

## pseudocode

```c
__int64 __fastcall CoCreateClrHostingHelper(struct IClrHostingHelper **a1, const unsigned __int16 *a2)
{
  HMODULE Library; // rax
  HMODULE v4; // rsi
  signed int LastError; // eax
  unsigned int v6; // ebx
  FARPROC ProcAddress; // rax
  int v8; // eax
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  int v11; // eax
  unsigned __int64 v12; // rcx
  _QWORD *v13; // rax
  struct ICLRMetaHost *v15; // [rsp+50h] [rbp+8h] BYREF

  v15 = 0;
  Library = LoadLibraryExW(L"mscoree.dll", 0, 8u);
  v4 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "CLRCreateInstance");
    if ( ProcAddress )
    {
      v8 = ((__int64 (__fastcall *)(GUID *, GUID *, struct ICLRMetaHost **))ProcAddress)(
             &CLSID_CLRMetaHost,
             &GUID_d332db9e_b9b3_4125_8207_a14884f53216,
             &v15);
      v6 = v8;
      if ( v8 >= 0 )
      {
        v13 = operator new(0x28u);
        v10 = v13;
        if ( v13 )
        {
          v13[2] = v4;
          *((_DWORD *)v13 + 2) = 0;
          v4 = 0;
          v13[3] = 0;
          *v13 = &CLR_HOSTING_LEGACY::`vftable'{for `CLR_HOSTING_BASE'};
          v13[4] = &CLR_HOSTING_LEGACY::`vftable'{for `IClrHostingHelper'};
          v11 = CLR_HOSTING::Initialize((CLR_HOSTING *)v13, v15, a2);
LABEL_12:
          v12 = (unsigned __int64)(v10 + 4);
          v6 = v11;
          if ( v11 >= 0 )
            FTPHOST_CLASS::sm_pClrHostingHelper = (struct IClrHostingHelper *)(v12 & -(__int64)(v10 != 0));
          else
            (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v12 + 16LL))(v12);
          goto LABEL_18;
        }
LABEL_17:
        v6 = -2147024882;
        goto LABEL_18;
      }
      if ( v8 != -2147467263 )
        goto LABEL_18;
    }
    v9 = operator new(0x28u);
    v10 = v9;
    if ( v9 )
    {
      v9[2] = v4;
      *((_DWORD *)v9 + 2) = 0;
      v4 = 0;
      v9[3] = 0;
      *v9 = &CLR_HOSTING_LEGACY::`vftable'{for `CLR_HOSTING_BASE'};
      v9[4] = &CLR_HOSTING_LEGACY::`vftable'{for `IClrHostingHelper'};
      v11 = CLR_HOSTING_LEGACY::Initialize((CLR_HOSTING_LEGACY *)v9, a2);
      goto LABEL_12;
    }
    goto LABEL_17;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 == -2147024770 || v6 + 2147024894 <= 1 )
    v6 = -2147467262;
LABEL_18:
  if ( v15 )
  {
    (*(void (__fastcall **)(struct ICLRMetaHost *))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v4 )
    FreeLibrary(v4);
  return v6;
}

```

## disassembly

```asm
0x180003afc  mov     [rsp+arg_0], rcx
0x180003b01  push    rbx
0x180003b02  push    rbp
0x180003b03  push    rsi
0x180003b04  push    rdi
0x180003b05  sub     rsp, 28h
0x180003b09  mov     rbp, rdx
0x180003b0c  mov     [rsp+48h+arg_0], 0
0x180003b15  xor     edx, edx; hFile
0x180003b17  lea     rcx, LibFileName; "mscoree.dll"
0x180003b1e  lea     r8d, [rdx+8]; dwFlags
0x180003b22  call    cs:__imp_LoadLibraryExW
0x180003b28  mov     rsi, rax
0x180003b2b  test    rax, rax
0x180003b2e  jnz     short loc_180003B66
0x180003b30  call    cs:__imp_GetLastError
0x180003b36  mov     ebx, eax
0x180003b38  test    eax, eax
0x180003b3a  jle     short loc_180003B45
0x180003b3c  movzx   ebx, ax
0x180003b3f  or      ebx, 80070000h
0x180003b45  cmp     ebx, 8007007Eh
0x180003b4b  jz      short loc_180003B5C
0x180003b4d  lea     eax, [rbx+7FF8FFFEh]
0x180003b53  cmp     eax, 1
0x180003b56  ja      loc_180003C6C
0x180003b5c  mov     ebx, 80004002h
0x180003b61  jmp     loc_180003C6C
0x180003b66  lea     rdx, ProcName; "CLRCreateInstance"
0x180003b6d  mov     rcx, rsi; hModule
0x180003b70  call    cs:__imp_GetProcAddress
0x180003b76  test    rax, rax
0x180003b79  jz      short loc_180003BA4
0x180003b7b  lea     r8, [rsp+48h+arg_0]
0x180003b80  lea     rdx, _GUID_d332db9e_b9b3_4125_8207_a14884f53216
0x180003b87  lea     rcx, CLSID_CLRMetaHost
0x180003b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b93  mov     ebx, eax
0x180003b95  test    eax, eax
0x180003b97  jns     short loc_180003C07
0x180003b99  cmp     eax, 80004001h
0x180003b9e  jnz     loc_180003C6C
0x180003ba4  mov     ecx, 28h ; '('; Size
0x180003ba9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003bae  mov     rdi, rax
0x180003bb1  test    rax, rax
0x180003bb4  jz      loc_180003C67
0x180003bba  mov     [rax+10h], rsi
0x180003bbe  mov     rdx, rbp; unsigned __int16 *
0x180003bc1  mov     dword ptr [rax+8], 0
0x180003bc8  xor     esi, esi
0x180003bca  mov     qword ptr [rax+18h], 0
0x180003bd2  mov     rcx, rdi; this
0x180003bd5  lea     rax, ??_7CLR_HOSTING_LEGACY@@6BCLR_HOSTING_BASE@@@; const CLR_HOSTING_LEGACY::`vftable'{for `CLR_HOSTING_BASE'}
0x180003bdc  mov     [rdi], rax
0x180003bdf  lea     rax, ??_7CLR_HOSTING_LEGACY@@6BIClrHostingHelper@@@; const CLR_HOSTING_LEGACY::`vftable'{for `IClrHostingHelper'}
0x180003be6  mov     [rdi+20h], rax
0x180003bea  call    ?Initialize@CLR_HOSTING_LEGACY@@QEAAJPEBG@Z; CLR_HOSTING_LEGACY::Initialize(ushort const *)
0x180003bef  lea     rcx, [rdi+20h]
0x180003bf3  mov     ebx, eax
0x180003bf5  test    eax, eax
0x180003bf7  jns     short loc_180003C55
0x180003bf9  mov     rax, [rcx]
0x180003bfc  mov     rax, [rax+10h]
0x180003c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c05  jmp     short loc_180003C6C
0x180003c07  mov     ecx, 28h ; '('; Size
0x180003c0c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003c11  mov     rdi, rax
0x180003c14  test    rax, rax
0x180003c17  jz      short loc_180003C67
0x180003c19  mov     [rax+10h], rsi
0x180003c1d  mov     r8, rbp; unsigned __int16 *
0x180003c20  mov     dword ptr [rax+8], 0
0x180003c27  xor     esi, esi
0x180003c29  mov     qword ptr [rax+18h], 0
0x180003c31  mov     rcx, rdi; this
0x180003c34  lea     rax, ??_7CLR_HOSTING_LEGACY@@6BCLR_HOSTING_BASE@@@; const CLR_HOSTING_LEGACY::`vftable'{for `CLR_HOSTING_BASE'}
0x180003c3b  mov     [rdi], rax
0x180003c3e  lea     rax, ??_7CLR_HOSTING_LEGACY@@6BIClrHostingHelper@@@; const CLR_HOSTING_LEGACY::`vftable'{for `IClrHostingHelper'}
0x180003c45  mov     [rdi+20h], rax
0x180003c49  mov     rdx, [rsp+48h+arg_0]; struct ICLRMetaHost *
0x180003c4e  call    ?Initialize@CLR_HOSTING@@QEAAJPEAUICLRMetaHost@@PEBG@Z; CLR_HOSTING::Initialize(ICLRMetaHost *,ushort const *)
0x180003c53  jmp     short loc_180003BEF
0x180003c55  neg     rdi
0x180003c58  sbb     rax, rax
0x180003c5b  and     rax, rcx
0x180003c5e  mov     cs:?sm_pClrHostingHelper@FTPHOST_CLASS@@0PEAUIClrHostingHelper@@EA, rax; IClrHostingHelper * FTPHOST_CLASS::sm_pClrHostingHelper
0x180003c65  jmp     short loc_180003C6C
0x180003c67  mov     ebx, 8007000Eh
0x180003c6c  mov     rcx, [rsp+48h+arg_0]
0x180003c71  test    rcx, rcx
0x180003c74  jz      short loc_180003C8B
0x180003c76  mov     rax, [rcx]
0x180003c79  mov     rax, [rax+10h]
0x180003c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c82  mov     [rsp+48h+arg_0], 0
0x180003c8b  test    rsi, rsi
0x180003c8e  jz      short loc_180003C99
0x180003c90  mov     rcx, rsi; hLibModule
0x180003c93  call    cs:__imp_FreeLibrary
0x180003c99  mov     eax, ebx
0x180003c9b  add     rsp, 28h
0x180003c9f  pop     rdi
0x180003ca0  pop     rsi
0x180003ca1  pop     rbp
0x180003ca2  pop     rbx
0x180003ca3  retn
```
