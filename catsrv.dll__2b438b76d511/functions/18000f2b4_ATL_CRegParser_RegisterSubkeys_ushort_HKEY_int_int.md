# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000f2b4`
- end: `0x18000f913`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1631`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, unsigned __int16 *@<rdx>, HKEY@<r8>, int@<r9d>, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x18000f2b4`
- `0x180016f5c`

## callees

- `0x18000f2b4`
- `0x18000f91c`
- `0x18000fb64`
- `0x1800150fc`
- `0x1800155d0`
- `0x180015cec`
- `0x180016000`
- `0x18001645c`
- `0x1800164e0`
- `0x180016870`
- `0x1800169ec`
- `0x180016e48`
- `0x18001739c`
- `0x180017460`
- `0x1800177d0`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f5e2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f5e2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000f514`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000f514`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcpynW` at `0x18000f77e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcpynW` at `0x18000f77e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f33a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f34d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f418`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f446`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f65c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f33a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f34d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f418`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f446`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f65c`

## string_xrefs

- `0x18000f340`: `ForceRemove`
- `0x18000f40e`: `NoRemove`
- `0x18000f330`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  HKEY v5; // r15
  int Token; // ebx
  int v9; // r12d
  int *v10; // r13
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // r14d
  LSTATUS v14; // eax
  bool v15; // cc
  int v16; // eax
  unsigned __int64 v17; // rdx
  HKEY v18; // rbx
  bool v19; // r14
  int v20; // eax
  __int64 v22; // rax
  HKEY v23; // r14
  int v24; // eax
  void *v25; // rsp
  ATL::CRegParser *v26; // rcx
  ATL::CRegParser *v27; // rcx
  ATL::CRegParser *v28; // rcx
  ATL::CRegParser *v29; // rcx
  DWORD dwOptions; // [rsp+20h] [rbp-30h]
  int v31; // [rsp+50h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+8h] BYREF
  __int64 v33; // [rsp+60h] [rbp+10h]
  __int64 v34; // [rsp+68h] [rbp+18h]
  HKEY v35; // [rsp+70h] [rbp+20h]
  int v36; // [rsp+78h] [rbp+28h]
  HKEY v37[3]; // [rsp+80h] [rbp+30h] BYREF
  DWORD dwDisposition; // [rsp+98h] [rbp+48h] BYREF
  int v39; // [rsp+9Ch] [rbp+4Ch]
  HKEY phkResult; // [rsp+A0h] [rbp+50h] BYREF
  _QWORD *v41; // [rsp+A8h] [rbp+58h] BYREF
  WCHAR ValueName[264]; // [rsp+B0h] [rbp+60h] BYREF

  v31 = a4;
  v41 = 0;
  v5 = 0;
  memset(v37, 0, sizeof(v37));
  v35 = a3;
  Token = ATL::CRegParser::NextToken(this, a2);
  if ( Token >= 0 )
  {
    v9 = a5;
    v10 = 0;
    v39 = a5;
    v36 = 1;
    while ( *a2 != 125 )
    {
      v11 = lstrcmpiW(a2, L"Delete");
      if ( lstrcmpiW(a2, L"ForceRemove") && v11 )
        goto LABEL_16;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        break;
      if ( !v31 )
        goto LABEL_16;
      hKey = 0;
      v33 = 0;
      v34 = 0;
      if ( ATL::CRegParser::StrChrW(a2, 0x5Cu) )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_38:
        Token = -2147352567;
        break;
      }
      if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, a2) )
      {
        hKey = v35;
        ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, a2);
        hKey = 0;
      }
      if ( v11 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_16:
        if ( !lstrcmpiW(a2, L"NoRemove") )
        {
          v36 = 0;
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            break;
        }
        if ( lstrcmpiW(a2, L"Val") )
        {
          if ( ATL::CRegParser::StrChrW(a2, 0x5Cu) )
            goto LABEL_38;
          if ( v31 )
          {
            v18 = v35;
            v19 = 0;
            if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v37, v35, a2, 0xF003Fu, dwOptions)
              && (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v37, v18, a2, 0x20019u, dwOptions) )
            {
              dwDisposition = 0;
              phkResult = 0;
              if ( RegCreateKeyExW(v18, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition) )
                goto LABEL_38;
              v20 = ATL::CRegKey::Close((ATL::CRegKey *)v37);
              v5 = phkResult;
              v37[0] = phkResult;
              if ( v20 )
                goto LABEL_38;
            }
            else
            {
              v5 = v37[0];
            }
            if ( ((*a2 - 76) & 0xFFDF) == 0 )
              v19 = lstrcmpiW(a2, L"LocalServer32") == 0;
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              break;
            if ( *a2 == 61 )
            {
              Token = ATL::CRegParser::AddValue(this, v37, 0, a2, v19);
              if ( Token < 0 )
                break;
            }
            goto LABEL_46;
          }
          v23 = v35;
          if ( !v9 )
          {
            v24 = ATL::CRegKey::Open((ATL::CRegKey *)v37, v35, a2, 0x20019u, dwOptions);
            v5 = v37[0];
            v9 = v24 != 0;
          }
          if ( !v10 )
          {
            if ( ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)0x208, v17) )
            {
              v25 = alloca(528);
              v10 = &v31;
            }
            else
            {
              v10 = (int *)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(
                             &v41,
                             520);
            }
            if ( !v10 )
            {
              Token = -2147024882;
              break;
            }
          }
          lstrcpynW((LPWSTR)v10, a2, 260);
          if ( v9 || ATL::CRegParser::HasSubKeys(v26, v5) || ATL::CRegParser::HasValues(v27, v5) )
          {
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              break;
            Token = ATL::CRegParser::SkipAssignment(this, a2);
            if ( Token < 0 )
              break;
            if ( *a2 == 123 )
            {
              Token = ATL::CRegParser::RegisterSubkeys(this, a2, v5, 0, v9);
              if ( Token < 0 )
                break;
              if ( !v9 )
              {
LABEL_72:
                if ( ATL::CRegParser::HasSubKeys(v28, v5) )
                {
                  if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v29, (const unsigned __int16 *)v10) )
                  {
                    ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v37, (const unsigned __int16 *)v10);
                    v5 = v37[0];
                  }
LABEL_52:
                  v16 = ATL::CRegParser::NextToken(this, a2);
                  goto LABEL_30;
                }
                goto LABEL_75;
              }
              Token = ATL::CRegParser::NextToken(this, a2);
              if ( Token < 0 )
                break;
              Token = ATL::CRegParser::SkipAssignment(this, a2);
              if ( Token < 0 )
                break;
              v9 = v39;
            }
            else if ( !v9 )
            {
              goto LABEL_72;
            }
          }
          else
          {
LABEL_75:
            if ( (unsigned int)ATL::CRegKey::Close((ATL::CRegKey *)v37) )
              goto LABEL_38;
            if ( v36 )
            {
              v33 = 0;
              v34 = 0;
              hKey = v23;
              ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, (const unsigned __int16 *)v10);
              hKey = 0;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              break;
            Token = ATL::CRegParser::SkipAssignment(this, a2);
            if ( Token < 0 )
              break;
            v5 = v37[0];
          }
        }
        else
        {
          Token = ATL::CRegParser::NextToken(this, ValueName);
          if ( Token < 0 )
            break;
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            break;
          if ( *a2 != 61 )
            goto LABEL_38;
          v13 = v31;
          if ( v31 )
          {
            v33 = 0;
            v34 = 0;
            hKey = v35;
            Token = ATL::CRegParser::AddValue(this, &hKey, ValueName, a2, 0);
            hKey = 0;
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            if ( Token < 0 )
              break;
            goto LABEL_47;
          }
          if ( !v9 )
          {
            hKey = 0;
            v33 = 0;
            v34 = 0;
            v14 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, v35, 0, 0x20006u, dwOptions);
            Token = v14;
            v15 = v14 <= 0;
            if ( v14 )
              goto LABEL_83;
            v14 = RegDeleteValueW(hKey, ValueName);
            Token = v14;
            if ( (v14 & 0xFFFFFFFD) != 0 )
            {
              v15 = v14 <= 0;
LABEL_83:
              if ( !v15 )
                Token = (unsigned __int16)v14 | 0x80070000;
LABEL_85:
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
              break;
            }
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
          v16 = ATL::CRegParser::SkipAssignment(this, a2);
LABEL_30:
          Token = v16;
          if ( v16 < 0 )
            break;
        }
      }
      else
      {
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_85;
        Token = ATL::CRegParser::SkipAssignment(this, a2);
        if ( Token < 0 )
          goto LABEL_85;
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_46:
        v13 = v31;
LABEL_47:
        if ( *a2 == 123 )
        {
          v22 = -1;
          do
            ++v22;
          while ( a2[v22] );
          if ( v22 == 1 )
          {
            Token = ATL::CRegParser::RegisterSubkeys(this, a2, v5, v13, 0);
            if ( Token < 0 )
              break;
            goto LABEL_52;
          }
        }
      }
    }
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v37);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v41);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x18000f2b4  push    rbp
0x18000f2b6  push    rbx
0x18000f2b7  push    rsi
0x18000f2b8  push    rdi
0x18000f2b9  push    r12
0x18000f2bb  push    r13
0x18000f2bd  push    r14
0x18000f2bf  push    r15
0x18000f2c1  sub     rsp, 2D8h
0x18000f2c8  lea     rbp, [rsp+50h]
0x18000f2cd  mov     rax, cs:__security_cookie
0x18000f2d4  xor     rax, rbp
0x18000f2d7  mov     [rbp+2C0h+var_50], rax
0x18000f2de  xor     r14d, r14d
0x18000f2e1  mov     [rbp+2C0h+var_2C0], r9d
0x18000f2e5  mov     [rbp+2C0h+var_268], r14
0x18000f2e9  mov     r15d, r14d
0x18000f2ec  mov     [rbp+2C0h+var_290], r14
0x18000f2f0  mov     rdi, rdx
0x18000f2f3  mov     [rbp+2C0h+var_288], r14
0x18000f2f7  mov     rsi, rcx
0x18000f2fa  mov     [rbp+2C0h+var_280], r14
0x18000f2fe  mov     [rbp+2C0h+var_2A0], r8
0x18000f302  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000f307  mov     ebx, eax
0x18000f309  test    eax, eax
0x18000f30b  js      loc_18000F606
0x18000f311  mov     r12d, [rbp+2C0h+arg_20]
0x18000f318  mov     r13d, r14d
0x18000f31b  mov     [rbp+2C0h+var_274], r12d
0x18000f31f  mov     [rbp+2C0h+var_298], 1
0x18000f326  cmp     word ptr [rdi], 7Dh ; '}'
0x18000f32a  jz      loc_18000F606
0x18000f330  lea     rdx, aDelete; "Delete"
0x18000f337  mov     rcx, rdi; lpString1
0x18000f33a  call    cs:__imp_lstrcmpiW
0x18000f340  lea     rdx, aForceremove; "ForceRemove"
0x18000f347  mov     rcx, rdi; lpString1
0x18000f34a  mov     r14d, eax
0x18000f34d  call    cs:__imp_lstrcmpiW
0x18000f353  xor     ebx, ebx
0x18000f355  test    eax, eax
0x18000f357  jz      short loc_18000F362
0x18000f359  test    r14d, r14d
0x18000f35c  jnz     loc_18000F40E
0x18000f362  mov     rdx, rdi; unsigned __int16 *
0x18000f365  mov     rcx, rsi; this
0x18000f368  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000f36d  mov     ebx, eax
0x18000f36f  test    eax, eax
0x18000f371  js      loc_18000F606
0x18000f377  xor     ebx, ebx
0x18000f379  cmp     [rbp+2C0h+var_2C0], ebx
0x18000f37c  jz      loc_18000F40E
0x18000f382  lea     edx, [rbx+5Ch]; unsigned __int16
0x18000f385  mov     [rbp+2C0h+hKey], rbx
0x18000f389  mov     rcx, rdi; lpsz
0x18000f38c  mov     [rbp+2C0h+var_2B0], rbx
0x18000f390  mov     [rbp+2C0h+var_2A8], rbx
0x18000f394  call    ?StrChrW@CRegParser@ATL@@KAPEBGPEBGG@Z; ATL::CRegParser::StrChrW(ushort const *,ushort)
0x18000f399  test    rax, rax
0x18000f39c  jnz     loc_18000F8E0
0x18000f3a2  mov     rdx, rdi; unsigned __int16 *
0x18000f3a5  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18000f3aa  test    eax, eax
0x18000f3ac  jz      short loc_18000F3C6
0x18000f3ae  mov     rax, [rbp+2C0h+var_2A0]
0x18000f3b2  lea     rcx, [rbp+2C0h+hKey]; this
0x18000f3b6  mov     rdx, rdi; unsigned __int16 *
0x18000f3b9  mov     [rbp+2C0h+hKey], rax
0x18000f3bd  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000f3c2  mov     [rbp+2C0h+hKey], rbx
0x18000f3c6  test    r14d, r14d
0x18000f3c9  jnz     short loc_18000F405
0x18000f3cb  mov     rdx, rdi; unsigned __int16 *
0x18000f3ce  mov     rcx, rsi; this
0x18000f3d1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000f3d6  mov     ebx, eax
0x18000f3d8  test    eax, eax
0x18000f3da  js      loc_18000F8FB
0x18000f3e0  mov     rdx, rdi; unsigned __int16 *
0x18000f3e3  mov     rcx, rsi; this
0x18000f3e6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000f3eb  lea     rcx, [rbp+2C0h+hKey]; this
0x18000f3ef  mov     ebx, eax
0x18000f3f1  test    eax, eax
0x18000f3f3  js      loc_18000F8FF
0x18000f3f9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f3fe  xor     ecx, ecx
0x18000f400  jmp     loc_18000F6AD
0x18000f405  lea     rcx, [rbp+2C0h+hKey]; this
0x18000f409  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f40e  lea     rdx, aNoremove; "NoRemove"
0x18000f415  mov     rcx, rdi; lpString1
0x18000f418  call    cs:__imp_lstrcmpiW
0x18000f41e  test    eax, eax
0x18000f420  jnz     short loc_18000F43C
0x18000f422  mov     rdx, rdi; unsigned __int16 *
0x18000f425  mov     [rbp+2C0h+var_298], ebx
0x18000f428  mov     rcx, rsi; this
0x18000f42b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000f430  mov     ebx, eax
0x18000f432  test    eax, eax
0x18000f434  js      loc_18000F606
0x18000f43a  xor     ebx, ebx
0x18000f43c  lea     rdx, aVal; "Val"
0x18000f443  mov     rcx, rdi; lpString1
0x18000f446  call    cs:__imp_lstrcmpiW
0x18000f44c  test    eax, eax
0x18000f44e  jnz     loc_18000F54A
0x18000f454  lea     rdx, [rbp+2C0h+ValueName]; unsigned __int16 *
0x18000f458  mov     rcx, rsi; this
0x18000f45b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000f460  mov     ebx, eax
0x18000f462  test    eax, eax
0x18000f464  js      loc_18000F606
0x18000f46a  mov     rdx, rdi; unsigned __int16 *
0x18000f46d  mov     rcx, rsi; this
0x18000f470  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000f475  xor     ecx, ecx
0x18000f477  mov     ebx, eax
0x18000f479  test    eax, eax
0x18000f47b  js      loc_18000F606
0x18000f481  cmp     word ptr [rdi], 3Dh ; '='
0x18000f485  jnz     loc_18000F601
0x18000f48b  mov     r14d, [rbp+2C0h+var_2C0]
0x18000f48f  test    r14d, r14d
0x18000f492  jz      short loc_18000F4DB
0x18000f494  mov     rax, [rbp+2C0h+var_2A0]
0x18000f498  lea     r8, [rbp+2C0h+ValueName]; unsigned __int16 *
0x18000f49c  mov     [rbp+2C0h+var_2B0], rcx
0x18000f4a0  lea     rdx, [rbp+2C0h+hKey]; struct ATL::CRegKey *
0x18000f4a4  mov     [rbp+2C0h+var_2A8], rcx
0x18000f4a8  mov     r9, rdi; unsigned __int16 *
0x18000f4ab  mov     byte ptr [rsp+310h+dwOptions], cl; bool
0x18000f4af  mov     rcx, rsi; this
0x18000f4b2  mov     [rbp+2C0h+hKey], rax
0x18000f4b6  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x18000f4bb  mov     ebx, eax
0x18000f4bd  lea     rcx, [rbp+2C0h+hKey]; this
0x18000f4c1  xor     eax, eax
0x18000f4c3  mov     [rbp+2C0h+hKey], rax
0x18000f4c7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f4cc  test    ebx, ebx
0x18000f4ce  js      loc_18000F606
0x18000f4d4  xor     ecx, ecx
0x18000f4d6  jmp     loc_18000F6B1
0x18000f4db  test    r12d, r12d
0x18000f4de  jnz     short loc_18000F530
0x18000f4e0  mov     rdx, [rbp+2C0h+var_2A0]; hKey
0x18000f4e4  mov     r9d, 20006h; unsigned int
0x18000f4ea  mov     [rbp+2C0h+hKey], rcx
0x18000f4ee  xor     r8d, r8d; lpSubKey
0x18000f4f1  mov     [rbp+2C0h+var_2B0], rcx
0x18000f4f5  mov     [rbp+2C0h+var_2A8], rcx
0x18000f4f9  lea     rcx, [rbp+2C0h+hKey]; this
0x18000f4fd  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x18000f502  mov     ebx, eax
0x18000f504  test    eax, eax
0x18000f506  jnz     loc_18000F8F0
0x18000f50c  mov     rcx, [rbp+2C0h+hKey]; hKey
0x18000f510  lea     rdx, [rbp+2C0h+ValueName]; lpValueName
0x18000f514  call    cs:__imp_RegDeleteValueW
0x18000f51a  mov     ebx, eax
0x18000f51c  test    eax, 0FFFFFFFDh
0x18000f521  jnz     loc_18000F8EE
0x18000f527  lea     rcx, [rbp+2C0h+hKey]; this
0x18000f52b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f530  mov     rdx, rdi; unsigned __int16 *
0x18000f533  mov     rcx, rsi; this
0x18000f536  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000f53b  mov     ebx, eax
0x18000f53d  test    eax, eax
0x18000f53f  jns     loc_18000F326
0x18000f545  jmp     loc_18000F606
0x18000f54a  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000f54f  mov     rcx, rdi; lpsz
0x18000f552  call    ?StrChrW@CRegParser@ATL@@KAPEBGPEBGG@Z; ATL::CRegParser::StrChrW(ushort const *,ushort)
0x18000f557  test    rax, rax
0x18000f55a  jnz     loc_18000F601
0x18000f560  cmp     [rbp+2C0h+var_2C0], ebx
0x18000f563  jz      loc_18000F701
0x18000f569  mov     rbx, [rbp+2C0h+var_2A0]
0x18000f56d  lea     rcx, [rbp+2C0h+var_290]; this
0x18000f571  mov     rdx, rbx; hKey
0x18000f574  mov     r9d, 0F003Fh; unsigned int
0x18000f57a  mov     r8, rdi; lpSubKey
0x18000f57d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x18000f582  xor     r14d, r14d
0x18000f585  test    eax, eax
0x18000f587  jz      loc_18000F63D
0x18000f58d  mov     r9d, 20019h; unsigned int
0x18000f593  lea     rcx, [rbp+2C0h+var_290]; this
0x18000f597  mov     r8, rdi; lpSubKey
0x18000f59a  mov     rdx, rbx; hKey
0x18000f59d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x18000f5a2  test    eax, eax
0x18000f5a4  jz      loc_18000F63D
0x18000f5aa  lea     rax, [rbp+2C0h+dwDisposition]
0x18000f5ae  mov     [rbp+2C0h+dwDisposition], r14d
0x18000f5b2  mov     [rsp+310h+lpdwDisposition], rax; lpdwDisposition
0x18000f5b7  xor     r9d, r9d; lpClass
0x18000f5ba  lea     rax, [rbp+2C0h+var_270]
0x18000f5be  mov     [rbp+2C0h+var_270], r14
0x18000f5c2  mov     [rsp+310h+phkResult], rax; phkResult
0x18000f5c7  xor     r8d, r8d; Reserved
0x18000f5ca  mov     [rsp+310h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000f5cf  mov     rdx, rdi; lpSubKey
0x18000f5d2  mov     [rsp+310h+samDesired], 2001Fh; samDesired
0x18000f5da  mov     rcx, rbx; hKey
0x18000f5dd  mov     [rsp+310h+dwOptions], r14d; dwOptions
0x18000f5e2  call    cs:__imp_RegCreateKeyExW
0x18000f5e8  test    eax, eax
0x18000f5ea  jnz     short loc_18000F601
0x18000f5ec  lea     rcx, [rbp+2C0h+var_290]; this
0x18000f5f0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f5f5  mov     r15, [rbp+2C0h+var_270]
0x18000f5f9  mov     [rbp+2C0h+var_290], r15
0x18000f5fd  test    eax, eax
0x18000f5ff  jz      short loc_18000F641
0x18000f601  mov     ebx, 80020009h
0x18000f606  lea     rcx, [rbp+2C0h+var_290]; this
0x18000f60a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f60f  lea     rcx, [rbp+2C0h+var_268]
0x18000f613  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x18000f618  mov     eax, ebx
0x18000f61a  mov     rcx, [rbp+2C0h+var_50]
0x18000f621  xor     rcx, rbp; StackCookie
0x18000f624  call    __security_check_cookie
0x18000f629  lea     rsp, [rbp+288h]
0x18000f630  pop     r15
0x18000f632  pop     r14
0x18000f634  pop     r13
0x18000f636  pop     r12
0x18000f638  pop     rdi
0x18000f639  pop     rsi
0x18000f63a  pop     rbx
0x18000f63b  pop     rbp
0x18000f63c  retn
0x18000f63d  mov     r15, [rbp+2C0h+var_290]
0x18000f641  movzx   eax, word ptr [rdi]
0x18000f644  mov     ecx, 0FFDFh
0x18000f649  sub     ax, 4Ch ; 'L'
0x18000f64d  test    cx, ax
0x18000f650  jnz     short loc_18000F671
0x18000f652  lea     rdx, aLocalserver32; "LocalServer32"
0x18000f659  mov     rcx, rdi; lpString1
0x18000f65c  call    cs:__imp_lstrcmpiW
0x18000f662  test    eax, eax
0x18000f664  movzx   r14d, r14b
0x18000f668  mov     eax, 1
0x18000f66d  cmovz   r14d, eax
0x18000f671  mov     rdx, rdi; unsigned __int16 *
0x18000f674  mov     rcx, rsi; this
0x18000f677  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000f67c  xor     ecx, ecx
0x18000f67e  mov     ebx, eax
0x18000f680  test    eax, eax
0x18000f682  js      short loc_18000F606
0x18000f684  cmp     word ptr [rdi], 3Dh ; '='
0x18000f688  jnz     short loc_18000F6AD
0x18000f68a  mov     r9, rdi; unsigned __int16 *
0x18000f68d  mov     byte ptr [rsp+310h+dwOptions], r14b; bool
0x18000f692  xor     r8d, r8d; unsigned __int16 *
0x18000f695  lea     rdx, [rbp+2C0h+var_290]; struct ATL::CRegKey *
0x18000f699  mov     rcx, rsi; this
0x18000f69c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x18000f6a1  xor     ecx, ecx
0x18000f6a3  mov     ebx, eax
0x18000f6a5  test    eax, eax
0x18000f6a7  js      loc_18000F606
0x18000f6ad  mov     r14d, [rbp+2C0h+var_2C0]
0x18000f6b1  cmp     word ptr [rdi], 7Bh ; '{'
0x18000f6b5  jnz     loc_18000F326
0x18000f6bb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f6bf  inc     rax
0x18000f6c2  cmp     [rdi+rax*2], cx
0x18000f6c6  jnz     short loc_18000F6BF
0x18000f6c8  cmp     rax, 1
0x18000f6cc  jnz     loc_18000F326
0x18000f6d2  mov     [rsp+310h+dwOptions], ecx; unsigned int
0x18000f6d6  mov     r9d, r14d; int
0x18000f6d9  mov     rcx, rsi; this
0x18000f6dc  mov     r8, r15; HKEY
0x18000f6df  mov     rdx, rdi; unsigned __int16 *
0x18000f6e2  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000f6e7  mov     ebx, eax
0x18000f6e9  test    eax, eax
0x18000f6eb  js      loc_18000F606
0x18000f6f1  mov     rdx, rdi; unsigned __int16 *
0x18000f6f4  mov     rcx, rsi; this
0x18000f6f7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000f6fc  jmp     loc_18000F53B
0x18000f701  mov     r14, [rbp+2C0h+var_2A0]
0x18000f705  test    r12d, r12d
0x18000f708  jnz     short loc_18000F72E
0x18000f70a  mov     r9d, 20019h; unsigned int
0x18000f710  lea     rcx, [rbp+2C0h+var_290]; this
0x18000f714  mov     r8, rdi; lpSubKey
0x18000f717  mov     rdx, r14; hKey
  ... truncated ...
```
