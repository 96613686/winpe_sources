# CWUInfo::GetUpdatePolicyFields(void)

- ea: `0x1800d7510`
- end: `0x1800d7b63`
- name: `?GetUpdatePolicyFields@CWUInfo@@QEBAAEAU_UpdatePolicyData@@XZ`
- size: `1619`
- prototype: `struct _UpdatePolicyData *__fastcall(CWUInfo *__hidden this)`
- caller_count: `5`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800d6ef0`
- `0x1800d7b70`
- `0x1800d7ba0`
- `0x1800d7bc0`
- `0x1800d7be0`

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
- `0x1800d2e3c`
- `0x1800d7510`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d762c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d762c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d766a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d7687`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d766a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d7687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7b2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7b48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7b2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7b48`

## string_xrefs

- `0x1800d7660`: `ReadPolicy`
- `0x1800d767c`: `ReleaseUpdatePolicyValue`
- `0x1800d7625`: `updatepolicy.dll`
- `0x1800d7840`: `Software\Microsoft\WindowsUpdate\UX\Settings`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct _UpdatePolicyData *__fastcall CWUInfo::GetUpdatePolicyFields(CWUInfo *this, __int64 a2, unsigned __int16 a3)
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
  v4 = *(_DWORD *)(v3 + 992);
  v5 = -1;
  if ( (v4 & 1) == 0 )
  {
    *(_DWORD *)(v3 + 992) = v4 | 1;
    Block = (void *)(v3 + 1008);
    *(_OWORD *)(v3 + 1008) = 0;
    *(_QWORD *)(v3 + 1024) = 0;
    *(_QWORD *)(v3 + 1032) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)(v3 + 1008), L"#", 1u);
    *(_DWORD *)(v3 + 1040) = -1;
    *(_DWORD *)(v3 + 1044) = -1;
    *(_OWORD *)(v3 + 1048) = 0;
    *(_QWORD *)(v3 + 1064) = 0;
    *(_QWORD *)(v3 + 1072) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)(v3 + 1048), L"#", 1u);
    *(_OWORD *)(v3 + 1080) = 0;
    *(_QWORD *)(v3 + 1096) = 0;
    *(_QWORD *)(v3 + 1104) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)(v3 + 1080), L"#", 1u);
    _tlregdtor(CWUInfo::GetUpdatePolicyFields_::_2_::_dynamic_atexit_destructor_for__result__);
  }
  if ( !*(_BYTE *)(v3 + 317) )
  {
    *(_BYTE *)(v3 + 317) = 1;
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
        v12 = (char **)(v3 + 1080);
        if ( *(_QWORD *)(v3 + 1104) )
        {
          if ( *(_QWORD *)(v3 + 1104) <= 7u )
            v9 = (char *)(v3 + 1080);
          else
            v9 = *v12;
          *(_QWORD *)(v3 + 1096) = 1;
          *(_DWORD *)v9 = 49;
          goto LABEL_23;
        }
        v13 = L"1";
LABEL_16:
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v12, 1u, 1, v13);
        goto LABEL_23;
      }
      v12 = (char **)(v3 + 1080);
      if ( !*(_QWORD *)(v3 + 1104) )
      {
        v13 = L"0";
        goto LABEL_16;
      }
      if ( *(_QWORD *)(v3 + 1104) <= 7u )
        v9 = (char *)(v3 + 1080);
      else
        v9 = *v12;
      *(_QWORD *)(v3 + 1096) = 1;
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
        v17 = (char *)(v3 + 1008);
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
      v17 = (char *)(v3 + 1008);
      if ( *((_WORD *)Block + 8) != 3 )
        goto LABEL_32;
      v20 = L"True";
      if ( !*((_DWORD *)Block + 6) )
        v20 = L"False";
      v18 = -1;
      do
        ++v18;
      while ( v20[v18] );
      if ( v18 <= *(_QWORD *)(v3 + 1032) )
      {
        if ( *(_QWORD *)(v3 + 1032) <= 7u )
          v21 = (char *)(v3 + 1008);
        else
          v21 = *(char **)v17;
        *(_QWORD *)(v3 + 1024) = v18;
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
      v17 = (char *)(v3 + 1008);
      v15 = *(_QWORD *)(v3 + 1032);
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
          v25 = (char *)(v3 + 1008);
        else
          v25 = *(char **)v17;
        *(_QWORD *)(v3 + 1024) = 4;
        *(_QWORD *)v25 = 0x65007500720054LL;
        *((_WORD *)v25 + 4) = 0;
LABEL_60:
        if ( !(unsigned __int8)std::operator!=<unsigned short>(v3 + 1008, L"True", v15) )
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
              *(_DWORD *)(v3 + 1040) = *((_DWORD *)Block + 6);
            else
              *(_DWORD *)(v3 + 1040) = 0;
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
              *(_DWORD *)(v3 + 1044) = *((_DWORD *)Block + 6);
            else
              *(_DWORD *)(v3 + 1044) = 0;
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
            v31 = (char **)(v3 + 1048);
            do
              ++v5;
            while ( v11[v5] );
            if ( v5 <= *(_QWORD *)(v3 + 1072) )
            {
              if ( *(_QWORD *)(v3 + 1072) <= 7u )
                v32 = (char *)(v3 + 1048);
              else
                v32 = *v31;
              *(_QWORD *)(v3 + 1064) = v5;
              memmove_0(v32, v11, 2 * v5);
              *(_WORD *)&v32[2 * v5] = 0;
              goto LABEL_103;
            }
            v33 = v11;
            v34 = v5;
          }
          else
          {
            v31 = (char **)(v3 + 1048);
            if ( *(_QWORD *)(v3 + 1072) )
            {
              if ( *(_QWORD *)(v3 + 1072) <= 7u )
                v35 = (char *)(v3 + 1048);
              else
                v35 = *v31;
              *(_QWORD *)(v3 + 1064) = 1;
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
              JUMPOUT(0x1800D7B62LL);
            }
            return (struct _UpdatePolicyData *)(v3 + 1008);
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
  return (struct _UpdatePolicyData *)(v3 + 1008);
}

```

## disassembly

```asm
0x1800d7510  mov     [rsp-40h+Block], rcx
0x1800d7515  push    rbp
0x1800d7516  push    rbx
0x1800d7517  push    rsi
0x1800d7518  push    rdi
0x1800d7519  push    r12
0x1800d751b  push    r13
0x1800d751d  push    r14
0x1800d751f  push    r15
0x1800d7521  mov     rbp, rsp
0x1800d7524  sub     rsp, 38h
0x1800d7528  mov     ecx, cs:_tls_index
0x1800d752e  mov     rax, gs:58h
0x1800d7537  mov     r14, [rax+rcx*8]
0x1800d753b  mov     ecx, 3E0h
0x1800d7540  mov     eax, [rcx+r14]
0x1800d7544  mov     edx, 3F0h
0x1800d7549  xor     edi, edi
0x1800d754b  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800d754f  lea     r12d, [rdi+1]
0x1800d7553  test    r12b, al
0x1800d7556  jnz     loc_1800D75E5
0x1800d755c  or      eax, r12d
0x1800d755f  mov     [rcx+r14], eax
0x1800d7563  mov     ebx, edx
0x1800d7565  add     rbx, r14
0x1800d7568  mov     [rbp+Block], rbx
0x1800d756c  xorps   xmm0, xmm0
0x1800d756f  movups  xmmword ptr [rbx], xmm0
0x1800d7572  mov     [rbx+10h], rdi
0x1800d7576  mov     [rbx+18h], rdi
0x1800d757a  mov     r8d, r12d
0x1800d757d  lea     rdi, asc_1801B4764; "#"
0x1800d7584  mov     rdx, rdi
0x1800d7587  mov     rcx, rbx
0x1800d758a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800d758f  nop
0x1800d7590  mov     [rbx+20h], r15d
0x1800d7594  mov     [rbx+24h], r15d
0x1800d7598  lea     rcx, [rbx+28h]
0x1800d759c  xorps   xmm0, xmm0
0x1800d759f  movups  xmmword ptr [rcx], xmm0
0x1800d75a2  xor     esi, esi
0x1800d75a4  mov     [rcx+10h], rsi
0x1800d75a8  mov     [rcx+18h], rsi
0x1800d75ac  mov     r8d, r12d
0x1800d75af  mov     rdx, rdi
0x1800d75b2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800d75b7  nop
0x1800d75b8  lea     rcx, [rbx+48h]
0x1800d75bc  xorps   xmm0, xmm0
0x1800d75bf  movups  xmmword ptr [rcx], xmm0
0x1800d75c2  mov     [rcx+10h], rsi
0x1800d75c6  mov     [rcx+18h], rsi
0x1800d75ca  mov     r8d, r12d
0x1800d75cd  mov     rdx, rdi
0x1800d75d0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800d75d5  nop
0x1800d75d6  lea     rcx, _CWUInfo__GetUpdatePolicyFields____2____dynamic_atexit_destructor_for__result__
0x1800d75dd  call    __tlregdtor
0x1800d75e2  nop
0x1800d75e3  xor     edi, edi
0x1800d75e5  mov     eax, 13Dh
0x1800d75ea  cmp     [rax+r14], dil
0x1800d75ee  jnz     loc_1800D7B15
0x1800d75f4  mov     [rax+r14], r12b
0x1800d75f8  mov     [rbp+Block], rdi
0x1800d75fc  lea     rax, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800d7603  mov     [rbp+var_18], rax
0x1800d7607  mov     [rbp+hModule], rdi
0x1800d760b  xor     edx, edx; unsigned __int16
0x1800d760d  lea     ecx, [rdx+0Ah]; unsigned __int16
0x1800d7610  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1800d7615  test    al, al
0x1800d7617  jz      loc_1800D7AE0
0x1800d761d  xor     edx, edx; hFile
0x1800d761f  mov     r8d, 800h; dwFlags
0x1800d7625  lea     rcx, aUpdatepolicyDl; "updatepolicy.dll"
0x1800d762c  call    cs:__imp_LoadLibraryExW
0x1800d7632  mov     rbx, rax
0x1800d7635  cmp     [rbp+hModule], rdi
0x1800d7639  jz      short loc_1800D7653
0x1800d763b  mov     rax, [rbp+var_18]
0x1800d763f  lea     rcx, [rbp+var_18]
0x1800d7643  mov     rax, [rax]
0x1800d7646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d764b  test    al, al
0x1800d764d  jz      loc_1800D7B48
0x1800d7653  mov     [rbp+hModule], rbx
0x1800d7657  test    rbx, rbx
0x1800d765a  jz      loc_1800D7AE0
0x1800d7660  lea     rdx, aReadpolicy; "ReadPolicy"
0x1800d7667  mov     rcx, rbx; hModule
0x1800d766a  call    cs:__imp_GetProcAddress
0x1800d7670  mov     r12, rax
0x1800d7673  test    rax, rax
0x1800d7676  jz      loc_1800D7AE0
0x1800d767c  lea     rdx, aReleaseupdatep; "ReleaseUpdatePolicyValue"
0x1800d7683  mov     rcx, [rbp+hModule]; hModule
0x1800d7687  call    cs:__imp_GetProcAddress
0x1800d768d  mov     rsi, rax
0x1800d7690  lea     rdx, [rbp+Block]
0x1800d7694  mov     ecx, 0Ch
0x1800d7699  mov     rax, r12
0x1800d769c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d76a1  lea     r13, a1_0; "1"
0x1800d76a8  test    eax, eax
0x1800d76aa  js      loc_1800D7740
0x1800d76b0  mov     rax, [rbp+Block]
0x1800d76b4  mov     r8d, 1
0x1800d76ba  cmp     dword ptr [rax], 0Ch
0x1800d76bd  jnz     short loc_1800D7701
0x1800d76bf  cmp     [rax+4], r8d
0x1800d76c3  jnz     short loc_1800D7701
0x1800d76c5  mov     ebx, 3F0h
0x1800d76ca  mov     ecx, ebx
0x1800d76cc  add     rcx, 48h ; 'H'
0x1800d76d0  add     rcx, r14
0x1800d76d3  cmp     [rcx+18h], r8
0x1800d76d7  jb      short loc_1800D76F4
0x1800d76d9  cmp     qword ptr [rcx+18h], 7
0x1800d76de  jbe     short loc_1800D76E5
0x1800d76e0  mov     rdx, [rcx]
0x1800d76e3  jmp     short loc_1800D76E8
0x1800d76e5  mov     rdx, rcx
0x1800d76e8  mov     [rcx+10h], r8
0x1800d76ec  mov     dword ptr [rdx], 31h ; '1'
0x1800d76f2  jmp     short loc_1800D7745
0x1800d76f4  mov     r9, r13
0x1800d76f7  mov     rdx, r8
0x1800d76fa  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800d76ff  jmp     short loc_1800D7745
0x1800d7701  mov     ebx, 3F0h
0x1800d7706  mov     ecx, ebx
0x1800d7708  add     rcx, 48h ; 'H'
0x1800d770c  add     rcx, r14
0x1800d770f  cmp     [rcx+18h], r8
0x1800d7713  jb      short loc_1800D7737
0x1800d7715  cmp     qword ptr [rcx+18h], 7
0x1800d771a  jbe     short loc_1800D7721
0x1800d771c  mov     rdx, [rcx]
0x1800d771f  jmp     short loc_1800D7724
0x1800d7721  mov     rdx, rcx
0x1800d7724  mov     [rcx+10h], r8
0x1800d7728  mov     eax, dword ptr cs:a0_0; "0"
0x1800d772e  mov     [rdx], ax
0x1800d7731  mov     [rdx+2], di
0x1800d7735  jmp     short loc_1800D7745
0x1800d7737  lea     r9, a0_0; "0"
0x1800d773e  jmp     short loc_1800D76F7
0x1800d7740  mov     ebx, 3F0h
0x1800d7745  test    rsi, rsi
0x1800d7748  jz      short loc_1800D7758
0x1800d774a  lea     rcx, [rbp+Block]
0x1800d774e  mov     rax, rsi
0x1800d7751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7756  jmp     short loc_1800D776F
0x1800d7758  mov     rcx, [rbp+Block]; Block
0x1800d775c  test    rcx, rcx
0x1800d775f  jz      short loc_1800D776F
0x1800d7761  mov     edx, 28h ; '('
0x1800d7766  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d776b  mov     [rbp+Block], rdi
0x1800d776f  lea     rdx, [rbp+Block]
0x1800d7773  mov     ecx, 11h
0x1800d7778  mov     rax, r12
0x1800d777b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7780  test    eax, eax
0x1800d7782  js      loc_1800D7ACD
0x1800d7788  mov     rdx, [rbp+Block]
0x1800d778c  mov     ecx, [rdx+4]
0x1800d778f  mov     r8d, 3
0x1800d7795  test    ecx, ecx
0x1800d7797  jz      loc_1800D7836
0x1800d779d  sub     ecx, 1
0x1800d77a0  jz      short loc_1800D77C9
0x1800d77a2  cmp     ecx, 1
0x1800d77a5  jnz     loc_1800D78D7
0x1800d77ab  mov     ecx, ebx
0x1800d77ad  add     rcx, r14
0x1800d77b0  mov     edx, 5
0x1800d77b5  cmp     [rcx+18h], rdx
0x1800d77b9  jb      loc_1800D78CB
0x1800d77bf  cmp     qword ptr [rcx+18h], 7
0x1800d77c4  jmp     loc_1800D78A2
0x1800d77c9  mov     ecx, ebx
0x1800d77cb  add     rcx, r14
0x1800d77ce  cmp     [rdx+10h], r8w
0x1800d77d3  jnz     short loc_1800D77B0
0x1800d77d5  lea     r9, aFalse_0; "False"
0x1800d77dc  lea     rax, aTrue_0; "True"
0x1800d77e3  cmp     [rdx+18h], edi
0x1800d77e6  cmovz   rax, r9
0x1800d77ea  mov     rdx, r15
0x1800d77ed  inc     rdx
0x1800d77f0  cmp     [rax+rdx*2], di
0x1800d77f4  jnz     short loc_1800D77ED
0x1800d77f6  cmp     rdx, [rcx+18h]
0x1800d77fa  ja      short loc_1800D782E
0x1800d77fc  cmp     qword ptr [rcx+18h], 7
0x1800d7801  jbe     short loc_1800D7808
0x1800d7803  mov     rdi, [rcx]
0x1800d7806  jmp     short loc_1800D780B
0x1800d7808  mov     rdi, rcx
0x1800d780b  mov     [rcx+10h], rdx
0x1800d780f  lea     rbx, [rdx+rdx]
0x1800d7813  mov     r8, rbx; Size
0x1800d7816  mov     rdx, rax; Src
0x1800d7819  mov     rcx, rdi; void *
0x1800d781c  call    memmove_0
0x1800d7821  xor     eax, eax
0x1800d7823  mov     [rbx+rdi], ax
0x1800d7827  xor     edi, edi
0x1800d7829  jmp     loc_1800D78D7
0x1800d782e  mov     r9, rax
0x1800d7831  jmp     loc_1800D78D2
0x1800d7836  xor     r8d, r8d; unsigned int
0x1800d7839  lea     rdx, aDeferupgrade; "DeferUpgrade"
0x1800d7840  lea     rcx, aSoftwareMicros_36; "Software\\Microsoft\\WindowsUpdate\\UX"...
0x1800d7847  call    ?GetRegistryKeyDWORDOrDefault@Utils@@SAKPEBG0K@Z; Utils::GetRegistryKeyDWORDOrDefault(ushort const *,ushort const *,ulong)
0x1800d784c  mov     ecx, ebx
0x1800d784e  add     rcx, r14
0x1800d7851  mov     r8, [rcx+18h]
0x1800d7855  test    eax, eax
0x1800d7857  jz      short loc_1800D7894
0x1800d7859  mov     eax, 4
0x1800d785e  cmp     r8, rax
0x1800d7861  jb      short loc_1800D7888
0x1800d7863  cmp     r8, 7
0x1800d7867  jbe     short loc_1800D786E
0x1800d7869  mov     rdx, [rcx]
0x1800d786c  jmp     short loc_1800D7871
0x1800d786e  mov     rdx, rcx
0x1800d7871  mov     [rcx+10h], rax
0x1800d7875  mov     rax, 65007500720054h
0x1800d787f  mov     [rdx], rax
0x1800d7882  mov     [rdx+8], di
0x1800d7886  jmp     short loc_1800D78D7
0x1800d7888  lea     r9, aTrue_0; "True"
0x1800d788f  mov     rdx, rax
0x1800d7892  jmp     short loc_1800D78D2
0x1800d7894  mov     edx, 5
0x1800d7899  cmp     r8, rdx
0x1800d789c  jb      short loc_1800D78CB
0x1800d789e  cmp     r8, 7
0x1800d78a2  jbe     short loc_1800D78A9
0x1800d78a4  mov     rbx, [rcx]
0x1800d78a7  jmp     short loc_1800D78AC
0x1800d78a9  mov     rbx, rcx
0x1800d78ac  mov     [rcx+10h], rdx
0x1800d78b0  mov     r8d, 0Ah; Size
0x1800d78b6  lea     rdx, aFalse_0; "False"
0x1800d78bd  mov     rcx, rbx; void *
0x1800d78c0  call    memmove_0
0x1800d78c5  mov     [rbx+0Ah], di
0x1800d78c9  jmp     short loc_1800D78D7
0x1800d78cb  lea     r9, aFalse_0; "False"
0x1800d78d2  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800d78d7  mov     ebx, 3F0h
0x1800d78dc  add     rbx, r14
0x1800d78df  lea     rdx, aTrue_0; "True"
0x1800d78e6  mov     rcx, rbx
0x1800d78e9  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x1800d78ee  test    al, al
0x1800d78f0  jnz     loc_1800D7ACD
0x1800d78f6  test    rsi, rsi
0x1800d78f9  jz      short loc_1800D7909
0x1800d78fb  lea     rcx, [rbp+Block]
0x1800d78ff  mov     rax, rsi
0x1800d7902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7907  jmp     short loc_1800D7920
0x1800d7909  mov     rcx, [rbp+Block]; Block
0x1800d790d  test    rcx, rcx
0x1800d7910  jz      short loc_1800D7920
0x1800d7912  mov     edx, 28h ; '('
0x1800d7917  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d791c  mov     [rbp+Block], rdi
0x1800d7920  lea     rdx, [rbp+Block]
0x1800d7924  mov     ecx, 13h
0x1800d7929  mov     rax, r12
0x1800d792c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7931  mov     rcx, [rbp+Block]; Block
0x1800d7935  test    eax, eax
0x1800d7937  js      short loc_1800D7955
0x1800d7939  cmp     dword ptr [rcx+4], 1
0x1800d793d  jnz     short loc_1800D7952
0x1800d793f  mov     eax, 3
0x1800d7944  cmp     ax, [rcx+10h]
0x1800d7948  jnz     short loc_1800D7952
0x1800d794a  mov     eax, [rcx+18h]
0x1800d794d  mov     [rbx+20h], eax
0x1800d7950  jmp     short loc_1800D7955
0x1800d7952  mov     [rbx+20h], edi
0x1800d7955  test    rsi, rsi
0x1800d7958  jz      short loc_1800D7968
0x1800d795a  lea     rcx, [rbp+Block]
0x1800d795e  mov     rax, rsi
0x1800d7961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7966  jmp     short loc_1800D797B
0x1800d7968  test    rcx, rcx
  ... truncated ...
```
