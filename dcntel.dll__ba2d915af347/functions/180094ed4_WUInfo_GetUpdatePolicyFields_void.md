# WUInfo::GetUpdatePolicyFields(void)

- ea: `0x180094ed4`
- end: `0x180095527`
- name: `?GetUpdatePolicyFields@WUInfo@@QEBAAEAU_UpdatePolicyData_2@@XZ`
- size: `1619`
- prototype: `struct _UpdatePolicyData_2 *__fastcall(WUInfo *__hidden this)`
- caller_count: `5`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800942b0`
- `0x180095530`
- `0x180095870`
- `0x180095890`
- `0x180095930`

## callees

- `0x180009260`
- `0x180009448`
- `0x180009f08`
- `0x180014f2c`
- `0x1800157b8`
- `0x18001daf0`
- `0x18001dcc8`
- `0x180021b84`
- `0x18002a690`
- `0x180094ed4`
- `0x1800d2e3c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180094ff0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180094ff0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009502e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009504b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009502e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009504b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800954f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009550c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800954f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009550c`

## string_xrefs

- `0x180095024`: `ReadPolicy`
- `0x180095040`: `ReleaseUpdatePolicyValue`
- `0x180094fe9`: `updatepolicy.dll`
- `0x180095204`: `Software\Microsoft\WindowsUpdate\UX\Settings`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct _UpdatePolicyData_2 *__fastcall WUInfo::GetUpdatePolicyFields(WUInfo *this, __int64 a2, unsigned __int16 a3)
{
  __int64 v3; // r14
  int v4; // eax
  unsigned __int64 v5; // r15
  HMODULE Library; // rbx
  FARPROC ProcAddress; // r12
  FARPROC v8; // rsi
  char *v9; // rdx
  __int64 v10; // r8
  const wchar_t *v11; // r13
  char **v12; // rcx
  const wchar_t *v13; // r9
  int v14; // ecx
  unsigned __int64 v15; // r8
  int v16; // ecx
  char *v17; // rcx
  unsigned __int64 v18; // rdx
  bool v19; // cc
  const wchar_t *v20; // rax
  char *v21; // rdi
  __int64 v22; // rbx
  const wchar_t *v23; // r9
  int RegistryKeyDWORDOrDefault; // eax
  char *v25; // rdx
  char *v26; // rbx
  int v27; // eax
  void *v28; // rcx
  int v29; // eax
  void *v30; // rcx
  char **v31; // rcx
  char *v32; // rdi
  const wchar_t *v33; // r9
  unsigned __int64 v34; // rdx
  char *v35; // rdx
  void *v36; // rcx
  signed int LastError; // eax
  int v39; // edx
  unsigned int v40; // r8d
  signed int v41; // eax
  int v42; // edx
  unsigned int v43; // r8d
  const int *v44; // [rsp+20h] [rbp-18h] BYREF
  HMODULE hModule; // [rsp+28h] [rbp-10h]
  void *Block; // [rsp+80h] [rbp+48h] BYREF

  Block = this;
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + *(unsigned int *)&tls_index);
  v4 = *(_DWORD *)(v3 + 576);
  v5 = -1;
  if ( (v4 & 1) == 0 )
  {
    *(_DWORD *)(v3 + 576) = v4 | 1;
    Block = (void *)(v3 + 592);
    *(_OWORD *)(v3 + 592) = 0;
    *(_QWORD *)(v3 + 608) = 0;
    *(_QWORD *)(v3 + 616) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)(v3 + 592), L"#", 1u);
    *(_DWORD *)(v3 + 624) = -1;
    *(_DWORD *)(v3 + 628) = -1;
    *(_OWORD *)(v3 + 632) = 0;
    *(_QWORD *)(v3 + 648) = 0;
    *(_QWORD *)(v3 + 656) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)(v3 + 632), L"#", 1u);
    *(_OWORD *)(v3 + 664) = 0;
    *(_QWORD *)(v3 + 680) = 0;
    *(_QWORD *)(v3 + 688) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)(v3 + 664), L"#", 1u);
    _tlregdtor(WUInfo::GetUpdatePolicyFields_::_2_::_dynamic_atexit_destructor_for__result__);
  }
  if ( !*(_BYTE *)(v3 + 312) )
  {
    *(_BYTE *)(v3 + 312) = 1;
    Block = 0;
    v44 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    hModule = 0;
    if ( !IsWindowsVersionOrGreater(0xAu, 0, a3)
      || (Library = LoadLibraryExW(L"updatepolicy.dll", 0, 0x800u), (hModule = Library) == 0)
      || (ProcAddress = GetProcAddress(Library, "ReadPolicy")) == 0 )
    {
LABEL_109:
      v36 = Block;
      goto LABEL_110;
    }
    v8 = GetProcAddress(hModule, "ReleaseUpdatePolicyValue");
    v11 = L"1";
    if ( ((int (__fastcall *)(__int64, void **))ProcAddress)(12, &Block) >= 0 )
    {
      v10 = 1;
      if ( *(_DWORD *)Block == 12 && *((_DWORD *)Block + 1) == 1 )
      {
        v12 = (char **)(v3 + 664);
        if ( *(_QWORD *)(v3 + 688) )
        {
          if ( *(_QWORD *)(v3 + 688) <= 7u )
            v9 = (char *)(v3 + 664);
          else
            v9 = *v12;
          *(_QWORD *)(v3 + 680) = 1;
          *(_DWORD *)v9 = 49;
          goto LABEL_23;
        }
        v13 = L"1";
LABEL_16:
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v12, 1u, 1, v13);
        goto LABEL_23;
      }
      v12 = (char **)(v3 + 664);
      if ( !*(_QWORD *)(v3 + 688) )
      {
        v13 = L"0";
        goto LABEL_16;
      }
      if ( *(_QWORD *)(v3 + 688) <= 7u )
        v9 = (char *)(v3 + 664);
      else
        v9 = *v12;
      *(_QWORD *)(v3 + 680) = 1;
      *(_WORD *)v9 = a0_0[0];
      *((_WORD *)v9 + 1) = 0;
    }
LABEL_23:
    if ( v8 )
    {
      ((void (__fastcall *)(void **, char *, __int64))v8)(&Block, v9, v10);
    }
    else if ( Block )
    {
      operator delete(Block);
      Block = 0;
    }
    if ( ((int (__fastcall *)(__int64, void **))ProcAddress)(17, &Block) < 0 )
    {
LABEL_107:
      if ( v8 )
        goto LABEL_108;
      goto LABEL_109;
    }
    v14 = *((_DWORD *)Block + 1);
    v15 = 3;
    if ( v14 )
    {
      v16 = v14 - 1;
      if ( v16 )
      {
        if ( v16 != 1 )
          goto LABEL_60;
        v17 = (char *)(v3 + 592);
LABEL_32:
        v18 = 5;
        if ( *((_QWORD *)v17 + 3) >= 5u )
        {
          v19 = *((_QWORD *)v17 + 3) <= 7u;
LABEL_54:
          if ( v19 )
            v26 = v17;
          else
            v26 = *(char **)v17;
          *((_QWORD *)v17 + 2) = 5;
          memmove_0(v26, L"False", 0xAu);
          *((_WORD *)v26 + 5) = 0;
          goto LABEL_60;
        }
LABEL_58:
        v23 = L"False";
        goto LABEL_59;
      }
      v17 = (char *)(v3 + 592);
      if ( *((_WORD *)Block + 8) != 3 )
        goto LABEL_32;
      v20 = L"True";
      if ( !*((_DWORD *)Block + 6) )
        v20 = L"False";
      v18 = -1;
      do
        ++v18;
      while ( v20[v18] );
      if ( v18 <= *(_QWORD *)(v3 + 616) )
      {
        if ( *(_QWORD *)(v3 + 616) <= 7u )
          v21 = (char *)(v3 + 592);
        else
          v21 = *(char **)v17;
        *(_QWORD *)(v3 + 608) = v18;
        v22 = 2 * v18;
        memmove_0(v21, v20, 2 * v18);
        *(_WORD *)&v21[v22] = 0;
        goto LABEL_60;
      }
      v23 = v20;
    }
    else
    {
      RegistryKeyDWORDOrDefault = Utils::GetRegistryKeyDWORDOrDefault(
                                    L"Software\\Microsoft\\WindowsUpdate\\UX\\Settings",
                                    L"DeferUpgrade",
                                    0);
      v17 = (char *)(v3 + 592);
      v15 = *(_QWORD *)(v3 + 616);
      if ( !RegistryKeyDWORDOrDefault )
      {
        v18 = 5;
        if ( v15 >= 5 )
        {
          v19 = v15 <= 7;
          goto LABEL_54;
        }
        goto LABEL_58;
      }
      if ( v15 >= 4 )
      {
        if ( v15 <= 7 )
          v25 = (char *)(v3 + 592);
        else
          v25 = *(char **)v17;
        *(_QWORD *)(v3 + 608) = 4;
        *(_QWORD *)v25 = 0x65007500720054LL;
        *((_WORD *)v25 + 4) = 0;
LABEL_60:
        if ( !(unsigned __int8)std::operator!=<unsigned short>(v3 + 592, L"True", v15) )
        {
          if ( v8 )
          {
            ((void (__fastcall *)(void **))v8)(&Block);
          }
          else if ( Block )
          {
            operator delete(Block);
            Block = 0;
          }
          v27 = ((__int64 (__fastcall *)(__int64, void **))ProcAddress)(19, &Block);
          v28 = Block;
          if ( v27 >= 0 )
          {
            if ( *((_DWORD *)Block + 1) == 1 && *((_WORD *)Block + 8) == 3 )
              *(_DWORD *)(v3 + 624) = *((_DWORD *)Block + 6);
            else
              *(_DWORD *)(v3 + 624) = 0;
          }
          if ( v8 )
          {
            ((void (__fastcall *)(void **))v8)(&Block);
          }
          else if ( v28 )
          {
            operator delete(v28);
            Block = 0;
          }
          v29 = ((__int64 (__fastcall *)(__int64, void **))ProcAddress)(20, &Block);
          v30 = Block;
          if ( v29 >= 0 )
          {
            if ( *((_DWORD *)Block + 1) == 1 && *((_WORD *)Block + 8) == 3 )
              *(_DWORD *)(v3 + 628) = *((_DWORD *)Block + 6);
            else
              *(_DWORD *)(v3 + 628) = 0;
          }
          if ( v8 )
          {
            ((void (__fastcall *)(void **))v8)(&Block);
          }
          else if ( v30 )
          {
            operator delete(v30);
            Block = 0;
          }
          if ( ((int (__fastcall *)(__int64, void **))ProcAddress)(21, &Block) < 0 )
            goto LABEL_103;
          if ( *((_DWORD *)Block + 1) == 1 && *((_WORD *)Block + 8) == 3 )
          {
            if ( !*((_DWORD *)Block + 6) )
              v11 = L"0";
            v31 = (char **)(v3 + 632);
            do
              ++v5;
            while ( v11[v5] );
            if ( v5 <= *(_QWORD *)(v3 + 656) )
            {
              if ( *(_QWORD *)(v3 + 656) <= 7u )
                v32 = (char *)(v3 + 632);
              else
                v32 = *v31;
              *(_QWORD *)(v3 + 648) = v5;
              memmove_0(v32, v11, 2 * v5);
              *(_WORD *)&v32[2 * v5] = 0;
              goto LABEL_103;
            }
            v33 = v11;
            v34 = v5;
          }
          else
          {
            v31 = (char **)(v3 + 632);
            if ( *(_QWORD *)(v3 + 656) )
            {
              if ( *(_QWORD *)(v3 + 656) <= 7u )
                v35 = (char *)(v3 + 632);
              else
                v35 = *v31;
              *(_QWORD *)(v3 + 648) = 1;
              *(_WORD *)v35 = a0_0[0];
              *((_WORD *)v35 + 1) = 0;
              goto LABEL_103;
            }
            v33 = L"0";
            v34 = 1;
          }
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            v31,
            v34,
            1,
            v33);
LABEL_103:
          if ( v8 )
          {
            ((void (__fastcall *)(void **))v8)(&Block);
LABEL_108:
            ((void (__fastcall *)(void **))v8)(&Block);
            goto LABEL_112;
          }
          if ( !Block )
          {
LABEL_112:
            v44 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
            if ( hModule && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v44) )
            {
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v39, v40);
              v41 = GetLastError();
              if ( v41 > 0 )
                v41 = (unsigned __int16)v41 | 0x80070000;
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v41, v42, v43);
              JUMPOUT(0x180095526LL);
            }
            return (struct _UpdatePolicyData_2 *)(v3 + 592);
          }
          operator delete(Block);
          v36 = 0;
          Block = 0;
LABEL_110:
          if ( v36 )
          {
            operator delete(v36);
            Block = 0;
          }
          goto LABEL_112;
        }
        goto LABEL_107;
      }
      v23 = L"True";
      v18 = 4;
    }
LABEL_59:
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)v17,
      v18,
      v15,
      v23);
    goto LABEL_60;
  }
  return (struct _UpdatePolicyData_2 *)(v3 + 592);
}

```

## disassembly

```asm
0x180094ed4  mov     [rsp-40h+Block], rcx
0x180094ed9  push    rbp
0x180094eda  push    rbx
0x180094edb  push    rsi
0x180094edc  push    rdi
0x180094edd  push    r12
0x180094edf  push    r13
0x180094ee1  push    r14
0x180094ee3  push    r15
0x180094ee5  mov     rbp, rsp
0x180094ee8  sub     rsp, 38h
0x180094eec  mov     ecx, cs:_tls_index
0x180094ef2  mov     rax, gs:58h
0x180094efb  mov     r14, [rax+rcx*8]
0x180094eff  mov     ecx, 240h
0x180094f04  mov     eax, [rcx+r14]
0x180094f08  mov     edx, 250h
0x180094f0d  xor     edi, edi
0x180094f0f  or      r15, 0FFFFFFFFFFFFFFFFh
0x180094f13  lea     r12d, [rdi+1]
0x180094f17  test    r12b, al
0x180094f1a  jnz     loc_180094FA9
0x180094f20  or      eax, r12d
0x180094f23  mov     [rcx+r14], eax
0x180094f27  mov     ebx, edx
0x180094f29  add     rbx, r14
0x180094f2c  mov     [rbp+Block], rbx
0x180094f30  xorps   xmm0, xmm0
0x180094f33  movups  xmmword ptr [rbx], xmm0
0x180094f36  mov     [rbx+10h], rdi
0x180094f3a  mov     [rbx+18h], rdi
0x180094f3e  mov     r8d, r12d
0x180094f41  lea     rdi, asc_1801B4764; "#"
0x180094f48  mov     rdx, rdi
0x180094f4b  mov     rcx, rbx
0x180094f4e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180094f53  nop
0x180094f54  mov     [rbx+20h], r15d
0x180094f58  mov     [rbx+24h], r15d
0x180094f5c  lea     rcx, [rbx+28h]
0x180094f60  xorps   xmm0, xmm0
0x180094f63  movups  xmmword ptr [rcx], xmm0
0x180094f66  xor     esi, esi
0x180094f68  mov     [rcx+10h], rsi
0x180094f6c  mov     [rcx+18h], rsi
0x180094f70  mov     r8d, r12d
0x180094f73  mov     rdx, rdi
0x180094f76  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180094f7b  nop
0x180094f7c  lea     rcx, [rbx+48h]
0x180094f80  xorps   xmm0, xmm0
0x180094f83  movups  xmmword ptr [rcx], xmm0
0x180094f86  mov     [rcx+10h], rsi
0x180094f8a  mov     [rcx+18h], rsi
0x180094f8e  mov     r8d, r12d
0x180094f91  mov     rdx, rdi
0x180094f94  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180094f99  nop
0x180094f9a  lea     rcx, _WUInfo__GetUpdatePolicyFields____2____dynamic_atexit_destructor_for__result__
0x180094fa1  call    __tlregdtor
0x180094fa6  nop
0x180094fa7  xor     edi, edi
0x180094fa9  mov     eax, 138h
0x180094fae  cmp     [rax+r14], dil
0x180094fb2  jnz     loc_1800954D9
0x180094fb8  mov     [rax+r14], r12b
0x180094fbc  mov     [rbp+Block], rdi
0x180094fc0  lea     rax, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180094fc7  mov     [rbp+var_18], rax
0x180094fcb  mov     [rbp+hModule], rdi
0x180094fcf  xor     edx, edx; unsigned __int16
0x180094fd1  lea     ecx, [rdx+0Ah]; unsigned __int16
0x180094fd4  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x180094fd9  test    al, al
0x180094fdb  jz      loc_1800954A4
0x180094fe1  xor     edx, edx; hFile
0x180094fe3  mov     r8d, 800h; dwFlags
0x180094fe9  lea     rcx, aUpdatepolicyDl; "updatepolicy.dll"
0x180094ff0  call    cs:__imp_LoadLibraryExW
0x180094ff6  mov     rbx, rax
0x180094ff9  cmp     [rbp+hModule], rdi
0x180094ffd  jz      short loc_180095017
0x180094fff  mov     rax, [rbp+var_18]
0x180095003  lea     rcx, [rbp+var_18]
0x180095007  mov     rax, [rax]
0x18009500a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009500f  test    al, al
0x180095011  jz      loc_18009550C
0x180095017  mov     [rbp+hModule], rbx
0x18009501b  test    rbx, rbx
0x18009501e  jz      loc_1800954A4
0x180095024  lea     rdx, aReadpolicy; "ReadPolicy"
0x18009502b  mov     rcx, rbx; hModule
0x18009502e  call    cs:__imp_GetProcAddress
0x180095034  mov     r12, rax
0x180095037  test    rax, rax
0x18009503a  jz      loc_1800954A4
0x180095040  lea     rdx, aReleaseupdatep; "ReleaseUpdatePolicyValue"
0x180095047  mov     rcx, [rbp+hModule]; hModule
0x18009504b  call    cs:__imp_GetProcAddress
0x180095051  mov     rsi, rax
0x180095054  lea     rdx, [rbp+Block]
0x180095058  mov     ecx, 0Ch
0x18009505d  mov     rax, r12
0x180095060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095065  lea     r13, a1_0; "1"
0x18009506c  test    eax, eax
0x18009506e  js      loc_180095104
0x180095074  mov     rax, [rbp+Block]
0x180095078  mov     r8d, 1
0x18009507e  cmp     dword ptr [rax], 0Ch
0x180095081  jnz     short loc_1800950C5
0x180095083  cmp     [rax+4], r8d
0x180095087  jnz     short loc_1800950C5
0x180095089  mov     ebx, 250h
0x18009508e  mov     ecx, ebx
0x180095090  add     rcx, 48h ; 'H'
0x180095094  add     rcx, r14
0x180095097  cmp     [rcx+18h], r8
0x18009509b  jb      short loc_1800950B8
0x18009509d  cmp     qword ptr [rcx+18h], 7
0x1800950a2  jbe     short loc_1800950A9
0x1800950a4  mov     rdx, [rcx]
0x1800950a7  jmp     short loc_1800950AC
0x1800950a9  mov     rdx, rcx
0x1800950ac  mov     [rcx+10h], r8
0x1800950b0  mov     dword ptr [rdx], 31h ; '1'
0x1800950b6  jmp     short loc_180095109
0x1800950b8  mov     r9, r13
0x1800950bb  mov     rdx, r8
0x1800950be  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800950c3  jmp     short loc_180095109
0x1800950c5  mov     ebx, 250h
0x1800950ca  mov     ecx, ebx
0x1800950cc  add     rcx, 48h ; 'H'
0x1800950d0  add     rcx, r14
0x1800950d3  cmp     [rcx+18h], r8
0x1800950d7  jb      short loc_1800950FB
0x1800950d9  cmp     qword ptr [rcx+18h], 7
0x1800950de  jbe     short loc_1800950E5
0x1800950e0  mov     rdx, [rcx]
0x1800950e3  jmp     short loc_1800950E8
0x1800950e5  mov     rdx, rcx
0x1800950e8  mov     [rcx+10h], r8
0x1800950ec  mov     eax, dword ptr cs:a0_0; "0"
0x1800950f2  mov     [rdx], ax
0x1800950f5  mov     [rdx+2], di
0x1800950f9  jmp     short loc_180095109
0x1800950fb  lea     r9, a0_0; "0"
0x180095102  jmp     short loc_1800950BB
0x180095104  mov     ebx, 250h
0x180095109  test    rsi, rsi
0x18009510c  jz      short loc_18009511C
0x18009510e  lea     rcx, [rbp+Block]
0x180095112  mov     rax, rsi
0x180095115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009511a  jmp     short loc_180095133
0x18009511c  mov     rcx, [rbp+Block]; Block
0x180095120  test    rcx, rcx
0x180095123  jz      short loc_180095133
0x180095125  mov     edx, 28h ; '('
0x18009512a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009512f  mov     [rbp+Block], rdi
0x180095133  lea     rdx, [rbp+Block]
0x180095137  mov     ecx, 11h
0x18009513c  mov     rax, r12
0x18009513f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095144  test    eax, eax
0x180095146  js      loc_180095491
0x18009514c  mov     rdx, [rbp+Block]
0x180095150  mov     ecx, [rdx+4]
0x180095153  mov     r8d, 3
0x180095159  test    ecx, ecx
0x18009515b  jz      loc_1800951FA
0x180095161  sub     ecx, 1
0x180095164  jz      short loc_18009518D
0x180095166  cmp     ecx, 1
0x180095169  jnz     loc_18009529B
0x18009516f  mov     ecx, ebx
0x180095171  add     rcx, r14
0x180095174  mov     edx, 5
0x180095179  cmp     [rcx+18h], rdx
0x18009517d  jb      loc_18009528F
0x180095183  cmp     qword ptr [rcx+18h], 7
0x180095188  jmp     loc_180095266
0x18009518d  mov     ecx, ebx
0x18009518f  add     rcx, r14
0x180095192  cmp     [rdx+10h], r8w
0x180095197  jnz     short loc_180095174
0x180095199  lea     r9, aFalse_0; "False"
0x1800951a0  lea     rax, aTrue_0; "True"
0x1800951a7  cmp     [rdx+18h], edi
0x1800951aa  cmovz   rax, r9
0x1800951ae  mov     rdx, r15
0x1800951b1  inc     rdx
0x1800951b4  cmp     [rax+rdx*2], di
0x1800951b8  jnz     short loc_1800951B1
0x1800951ba  cmp     rdx, [rcx+18h]
0x1800951be  ja      short loc_1800951F2
0x1800951c0  cmp     qword ptr [rcx+18h], 7
0x1800951c5  jbe     short loc_1800951CC
0x1800951c7  mov     rdi, [rcx]
0x1800951ca  jmp     short loc_1800951CF
0x1800951cc  mov     rdi, rcx
0x1800951cf  mov     [rcx+10h], rdx
0x1800951d3  lea     rbx, [rdx+rdx]
0x1800951d7  mov     r8, rbx; Size
0x1800951da  mov     rdx, rax; Src
0x1800951dd  mov     rcx, rdi; void *
0x1800951e0  call    memmove_0
0x1800951e5  xor     eax, eax
0x1800951e7  mov     [rbx+rdi], ax
0x1800951eb  xor     edi, edi
0x1800951ed  jmp     loc_18009529B
0x1800951f2  mov     r9, rax
0x1800951f5  jmp     loc_180095296
0x1800951fa  xor     r8d, r8d; unsigned int
0x1800951fd  lea     rdx, aDeferupgrade; "DeferUpgrade"
0x180095204  lea     rcx, aSoftwareMicros_36; "Software\\Microsoft\\WindowsUpdate\\UX"...
0x18009520b  call    ?GetRegistryKeyDWORDOrDefault@Utils@@SAKPEBG0K@Z; Utils::GetRegistryKeyDWORDOrDefault(ushort const *,ushort const *,ulong)
0x180095210  mov     ecx, ebx
0x180095212  add     rcx, r14
0x180095215  mov     r8, [rcx+18h]
0x180095219  test    eax, eax
0x18009521b  jz      short loc_180095258
0x18009521d  mov     eax, 4
0x180095222  cmp     r8, rax
0x180095225  jb      short loc_18009524C
0x180095227  cmp     r8, 7
0x18009522b  jbe     short loc_180095232
0x18009522d  mov     rdx, [rcx]
0x180095230  jmp     short loc_180095235
0x180095232  mov     rdx, rcx
0x180095235  mov     [rcx+10h], rax
0x180095239  mov     rax, 65007500720054h
0x180095243  mov     [rdx], rax
0x180095246  mov     [rdx+8], di
0x18009524a  jmp     short loc_18009529B
0x18009524c  lea     r9, aTrue_0; "True"
0x180095253  mov     rdx, rax
0x180095256  jmp     short loc_180095296
0x180095258  mov     edx, 5
0x18009525d  cmp     r8, rdx
0x180095260  jb      short loc_18009528F
0x180095262  cmp     r8, 7
0x180095266  jbe     short loc_18009526D
0x180095268  mov     rbx, [rcx]
0x18009526b  jmp     short loc_180095270
0x18009526d  mov     rbx, rcx
0x180095270  mov     [rcx+10h], rdx
0x180095274  mov     r8d, 0Ah; Size
0x18009527a  lea     rdx, aFalse_0; "False"
0x180095281  mov     rcx, rbx; void *
0x180095284  call    memmove_0
0x180095289  mov     [rbx+0Ah], di
0x18009528d  jmp     short loc_18009529B
0x18009528f  lea     r9, aFalse_0; "False"
0x180095296  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18009529b  mov     ebx, 250h
0x1800952a0  add     rbx, r14
0x1800952a3  lea     rdx, aTrue_0; "True"
0x1800952aa  mov     rcx, rbx
0x1800952ad  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x1800952b2  test    al, al
0x1800952b4  jnz     loc_180095491
0x1800952ba  test    rsi, rsi
0x1800952bd  jz      short loc_1800952CD
0x1800952bf  lea     rcx, [rbp+Block]
0x1800952c3  mov     rax, rsi
0x1800952c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800952cb  jmp     short loc_1800952E4
0x1800952cd  mov     rcx, [rbp+Block]; Block
0x1800952d1  test    rcx, rcx
0x1800952d4  jz      short loc_1800952E4
0x1800952d6  mov     edx, 28h ; '('
0x1800952db  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800952e0  mov     [rbp+Block], rdi
0x1800952e4  lea     rdx, [rbp+Block]
0x1800952e8  mov     ecx, 13h
0x1800952ed  mov     rax, r12
0x1800952f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800952f5  mov     rcx, [rbp+Block]; Block
0x1800952f9  test    eax, eax
0x1800952fb  js      short loc_180095319
0x1800952fd  cmp     dword ptr [rcx+4], 1
0x180095301  jnz     short loc_180095316
0x180095303  mov     eax, 3
0x180095308  cmp     ax, [rcx+10h]
0x18009530c  jnz     short loc_180095316
0x18009530e  mov     eax, [rcx+18h]
0x180095311  mov     [rbx+20h], eax
0x180095314  jmp     short loc_180095319
0x180095316  mov     [rbx+20h], edi
0x180095319  test    rsi, rsi
0x18009531c  jz      short loc_18009532C
0x18009531e  lea     rcx, [rbp+Block]
0x180095322  mov     rax, rsi
0x180095325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009532a  jmp     short loc_18009533F
0x18009532c  test    rcx, rcx
  ... truncated ...
```
