# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180008670`
- end: `0x180008cd3`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1635`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x180008670`
- `0x18001684c`

## callees

- `0x180008670`
- `0x180008cdc`
- `0x180008d08`
- `0x1800154e4`
- `0x1800159b8`
- `0x1800159f4`
- `0x180015a44`
- `0x180015b00`
- `0x180015b84`
- `0x180016350`
- `0x1800164b4`
- `0x180016738`
- `0x180016a0c`
- `0x180016ad0`
- `0x180016c58`
- `0x18001b550`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800088d0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800088d0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000899e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000899e`
- `KERNEL32!lstrcmpiW` at `0x1800086f6`
- `KERNEL32!lstrcmpiW` at `0x180008709`
- `KERNEL32!lstrcmpiW` at `0x1800087d4`
- `KERNEL32!lstrcmpiW` at `0x180008802`
- `KERNEL32!lstrcmpiW` at `0x180008a19`
- `KERNEL32!lstrcmpiW` at `0x1800086f6`
- `KERNEL32!lstrcmpiW` at `0x180008709`
- `KERNEL32!lstrcmpiW` at `0x1800087d4`
- `KERNEL32!lstrcmpiW` at `0x180008802`
- `KERNEL32!lstrcmpiW` at `0x180008a19`
- `KERNEL32!lstrcpynW` at `0x180008b3b`
- `KERNEL32!lstrcpynW` at `0x180008b3b`

## string_xrefs

- `0x1800086ff`: `ForceRemove`
- `0x1800087ca`: `NoRemove`
- `0x1800086ec`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  HKEY v7; // r15
  int Token; // ebx
  int *v9; // r13
  int v10; // r12d
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
  void *v24; // rsp
  ATL::CRegParser *v25; // rcx
  ATL::CRegParser *v26; // rcx
  ATL::CRegParser *v27; // rcx
  ATL::CRegParser *v28; // rcx
  DWORD dwOptions; // [rsp+20h] [rbp-30h]
  int v30; // [rsp+50h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+8h] BYREF
  __int64 v32; // [rsp+60h] [rbp+10h]
  __int64 v33; // [rsp+68h] [rbp+18h]
  HKEY v34; // [rsp+70h] [rbp+20h]
  int v35; // [rsp+78h] [rbp+28h]
  HKEY v36[3]; // [rsp+80h] [rbp+30h] BYREF
  DWORD dwDisposition; // [rsp+98h] [rbp+48h] BYREF
  int v38; // [rsp+9Ch] [rbp+4Ch]
  HKEY phkResult; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v40; // [rsp+A8h] [rbp+58h] BYREF
  WCHAR ValueName[264]; // [rsp+B0h] [rbp+60h] BYREF

  v30 = a4;
  v34 = a3;
  v40 = 0;
  v7 = 0;
  memset(v36, 0, sizeof(v36));
  Token = ATL::CRegParser::NextToken(this, a2);
  if ( Token >= 0 )
  {
    v9 = 0;
    v35 = 1;
    v10 = a5;
    v38 = a5;
    while ( *a2 != 125 )
    {
      v11 = lstrcmpiW(a2, L"Delete");
      if ( lstrcmpiW(a2, L"ForceRemove") && v11 )
        goto LABEL_16;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        break;
      if ( !v30 )
        goto LABEL_16;
      hKey = 0;
      v32 = 0;
      v33 = 0;
      if ( ATL::CRegParser::StrChrW(a2, 0x5Cu) )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_38:
        Token = -2147352567;
        break;
      }
      if ( ATL::CRegParser::CanForceRemoveKey(v12, a2) )
      {
        hKey = v34;
        ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, a2);
        hKey = 0;
      }
      if ( v11 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_16:
        if ( !lstrcmpiW(a2, L"NoRemove") )
        {
          v35 = 0;
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            break;
        }
        if ( lstrcmpiW(a2, L"Val") )
        {
          if ( ATL::CRegParser::StrChrW(a2, 0x5Cu) )
            goto LABEL_38;
          if ( v30 )
          {
            v18 = v34;
            v19 = 0;
            if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v36, v34, a2, 0xF003Fu, dwOptions)
              && (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v36, v18, a2, 0x20019u, dwOptions) )
            {
              dwDisposition = 0;
              phkResult = 0;
              if ( RegCreateKeyExW(v18, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition) )
                goto LABEL_38;
              v20 = ATL::CRegKey::Close((ATL::CRegKey *)v36);
              v7 = phkResult;
              v36[0] = phkResult;
              if ( v20 )
                goto LABEL_38;
            }
            else
            {
              v7 = v36[0];
            }
            if ( ((*a2 - 76) & 0xFFDF) == 0 )
              v19 = lstrcmpiW(a2, L"LocalServer32") == 0;
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              break;
            if ( *a2 == 61 )
            {
              Token = ATL::CRegParser::AddValue(this, v36, 0, a2, v19);
              if ( Token < 0 )
                break;
            }
            goto LABEL_46;
          }
          v23 = v34;
          if ( !v10 )
          {
            v10 = ATL::CRegKey::Open((ATL::CRegKey *)v36, v34, a2, 0x20019u, dwOptions) != 0;
            v7 = v36[0];
          }
          if ( !v9 )
          {
            if ( ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)0x208, v17) )
            {
              v24 = alloca(528);
              v9 = &v30;
            }
            else
            {
              v9 = (int *)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(
                            &v40,
                            520);
            }
            if ( !v9 )
            {
              Token = -2147024882;
              break;
            }
          }
          lstrcpynW((LPWSTR)v9, a2, 260);
          if ( v10 || ATL::CRegParser::HasSubKeys(v25, v7) || ATL::CRegParser::HasValues(v26, v7) )
          {
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              break;
            Token = ATL::CRegParser::SkipAssignment(this, a2);
            if ( Token < 0 )
              break;
            if ( *a2 == 123 )
            {
              Token = ATL::CRegParser::RegisterSubkeys(this, a2, v7, 0, v10);
              if ( Token < 0 )
                break;
              if ( !v10 )
              {
LABEL_72:
                if ( ATL::CRegParser::HasSubKeys(v27, v7) )
                {
                  if ( ATL::CRegParser::CanForceRemoveKey(v28, (const unsigned __int16 *)v9) )
                  {
                    ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v36, (const unsigned __int16 *)v9);
                    v7 = v36[0];
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
              v10 = v38;
            }
            else if ( !v10 )
            {
              goto LABEL_72;
            }
          }
          else
          {
LABEL_75:
            if ( (unsigned int)ATL::CRegKey::Close((ATL::CRegKey *)v36) )
              goto LABEL_38;
            if ( v35 )
            {
              v32 = 0;
              v33 = 0;
              hKey = v23;
              ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, (const unsigned __int16 *)v9);
              hKey = 0;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              break;
            Token = ATL::CRegParser::SkipAssignment(this, a2);
            if ( Token < 0 )
              break;
            v7 = v36[0];
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
          v13 = v30;
          if ( v30 )
          {
            v32 = 0;
            v33 = 0;
            hKey = v34;
            Token = ATL::CRegParser::AddValue(this, &hKey, ValueName, a2, 0);
            hKey = 0;
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            if ( Token < 0 )
              break;
            goto LABEL_47;
          }
          if ( !v10 )
          {
            hKey = 0;
            v32 = 0;
            v33 = 0;
            v14 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, v34, 0, 0x20006u, dwOptions);
            Token = v14;
            v15 = v14 <= 0;
            if ( v14 )
              goto LABEL_84;
            v14 = RegDeleteValueW(hKey, ValueName);
            Token = v14;
            if ( (v14 & 0xFFFFFFFD) != 0 )
            {
              v15 = v14 <= 0;
LABEL_84:
              if ( !v15 )
                Token = (unsigned __int16)v14 | 0x80070000;
LABEL_86:
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
          goto LABEL_86;
        Token = ATL::CRegParser::SkipAssignment(this, a2);
        if ( Token < 0 )
          goto LABEL_86;
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_46:
        v13 = v30;
LABEL_47:
        if ( *a2 == 123 )
        {
          v22 = -1;
          do
            ++v22;
          while ( a2[v22] );
          if ( v22 == 1 )
          {
            Token = ATL::CRegParser::RegisterSubkeys(this, a2, v7, v13, 0);
            if ( Token < 0 )
              break;
            goto LABEL_52;
          }
        }
      }
    }
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v36);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v40);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x180008670  push    rbp
0x180008672  push    rbx
0x180008673  push    rsi
0x180008674  push    rdi
0x180008675  push    r12
0x180008677  push    r13
0x180008679  push    r14
0x18000867b  push    r15
0x18000867d  sub     rsp, 2D8h
0x180008684  lea     rbp, [rsp+50h]
0x180008689  mov     rax, cs:__security_cookie
0x180008690  xor     rax, rbp
0x180008693  mov     [rbp+2C0h+var_50], rax
0x18000869a  mov     [rbp+2C0h+var_2C0], r9d
0x18000869e  mov     [rbp+2C0h+var_2A0], r8
0x1800086a2  mov     rdi, rdx
0x1800086a5  mov     rsi, rcx
0x1800086a8  xor     r14d, r14d
0x1800086ab  mov     [rbp+2C0h+var_268], r14
0x1800086af  mov     r15d, r14d
0x1800086b2  mov     [rbp+2C0h+var_290], r14
0x1800086b6  mov     [rbp+2C0h+var_288], r14
0x1800086ba  mov     [rbp+2C0h+var_280], r14
0x1800086be  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800086c3  mov     ebx, eax
0x1800086c5  test    eax, eax
0x1800086c7  js      loc_1800089C2
0x1800086cd  mov     r13d, r14d
0x1800086d0  mov     [rbp+2C0h+var_298], 1
0x1800086d7  mov     r12d, [rbp+2C0h+arg_20]
0x1800086de  mov     [rbp+2C0h+var_274], r12d
0x1800086e2  cmp     word ptr [rdi], 7Dh ; '}'
0x1800086e6  jz      loc_1800089C2
0x1800086ec  lea     rdx, String2; "Delete"
0x1800086f3  mov     rcx, rdi; lpString1
0x1800086f6  call    cs:__imp_lstrcmpiW
0x1800086fc  mov     r14d, eax
0x1800086ff  lea     rdx, aForceremove; "ForceRemove"
0x180008706  mov     rcx, rdi; lpString1
0x180008709  call    cs:__imp_lstrcmpiW
0x18000870f  xor     ebx, ebx
0x180008711  test    eax, eax
0x180008713  jz      short loc_18000871E
0x180008715  test    r14d, r14d
0x180008718  jnz     loc_1800087CA
0x18000871e  mov     rdx, rdi; unsigned __int16 *
0x180008721  mov     rcx, rsi; this
0x180008724  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008729  mov     ebx, eax
0x18000872b  test    eax, eax
0x18000872d  js      loc_1800089C2
0x180008733  xor     ebx, ebx
0x180008735  cmp     [rbp+2C0h+var_2C0], ebx
0x180008738  jz      loc_1800087CA
0x18000873e  mov     [rbp+2C0h+hKey], rbx
0x180008742  mov     [rbp+2C0h+var_2B0], rbx
0x180008746  mov     [rbp+2C0h+var_2A8], rbx
0x18000874a  lea     edx, [rbx+5Ch]; unsigned __int16
0x18000874d  mov     rcx, rdi; lpsz
0x180008750  call    ?StrChrW@CRegParser@ATL@@KAPEBGPEBGG@Z; ATL::CRegParser::StrChrW(ushort const *,ushort)
0x180008755  test    rax, rax
0x180008758  jnz     loc_180008C9F
0x18000875e  mov     rdx, rdi; unsigned __int16 *
0x180008761  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180008766  test    eax, eax
0x180008768  jz      short loc_180008782
0x18000876a  mov     rax, [rbp+2C0h+var_2A0]
0x18000876e  mov     [rbp+2C0h+hKey], rax
0x180008772  mov     rdx, rdi; unsigned __int16 *
0x180008775  lea     rcx, [rbp+2C0h+hKey]; this
0x180008779  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000877e  mov     [rbp+2C0h+hKey], rbx
0x180008782  test    r14d, r14d
0x180008785  jnz     short loc_1800087C1
0x180008787  mov     rdx, rdi; unsigned __int16 *
0x18000878a  mov     rcx, rsi; this
0x18000878d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008792  mov     ebx, eax
0x180008794  test    eax, eax
0x180008796  js      loc_180008C9D
0x18000879c  mov     rdx, rdi; unsigned __int16 *
0x18000879f  mov     rcx, rsi; this
0x1800087a2  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800087a7  mov     ebx, eax
0x1800087a9  lea     rcx, [rbp+2C0h+hKey]; this
0x1800087ad  test    eax, eax
0x1800087af  js      loc_180008CBE
0x1800087b5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800087ba  xor     ecx, ecx
0x1800087bc  jmp     loc_180008A6A
0x1800087c1  lea     rcx, [rbp+2C0h+hKey]; this
0x1800087c5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800087ca  lea     rdx, aNoremove; "NoRemove"
0x1800087d1  mov     rcx, rdi; lpString1
0x1800087d4  call    cs:__imp_lstrcmpiW
0x1800087da  test    eax, eax
0x1800087dc  jnz     short loc_1800087F8
0x1800087de  mov     [rbp+2C0h+var_298], ebx
0x1800087e1  mov     rdx, rdi; unsigned __int16 *
0x1800087e4  mov     rcx, rsi; this
0x1800087e7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800087ec  mov     ebx, eax
0x1800087ee  test    eax, eax
0x1800087f0  js      loc_1800089C2
0x1800087f6  xor     ebx, ebx
0x1800087f8  lea     rdx, aVal; "Val"
0x1800087ff  mov     rcx, rdi; lpString1
0x180008802  call    cs:__imp_lstrcmpiW
0x180008808  test    eax, eax
0x18000880a  jnz     loc_180008906
0x180008810  lea     rdx, [rbp+2C0h+ValueName]; unsigned __int16 *
0x180008814  mov     rcx, rsi; this
0x180008817  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000881c  mov     ebx, eax
0x18000881e  test    eax, eax
0x180008820  js      loc_1800089C2
0x180008826  mov     rdx, rdi; unsigned __int16 *
0x180008829  mov     rcx, rsi; this
0x18000882c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008831  mov     ebx, eax
0x180008833  xor     ecx, ecx
0x180008835  test    eax, eax
0x180008837  js      loc_1800089C2
0x18000883d  cmp     word ptr [rdi], 3Dh ; '='
0x180008841  jnz     loc_1800089BD
0x180008847  mov     r14d, [rbp+2C0h+var_2C0]
0x18000884b  test    r14d, r14d
0x18000884e  jz      short loc_180008897
0x180008850  mov     [rbp+2C0h+var_2B0], rcx
0x180008854  mov     [rbp+2C0h+var_2A8], rcx
0x180008858  mov     rax, [rbp+2C0h+var_2A0]
0x18000885c  mov     [rbp+2C0h+hKey], rax
0x180008860  mov     byte ptr [rsp+310h+dwOptions], cl; bool
0x180008864  mov     r9, rdi; unsigned __int16 *
0x180008867  lea     r8, [rbp+2C0h+ValueName]; unsigned __int16 *
0x18000886b  lea     rdx, [rbp+2C0h+hKey]; struct ATL::CRegKey *
0x18000886f  mov     rcx, rsi; this
0x180008872  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x180008877  mov     ebx, eax
0x180008879  xor     eax, eax
0x18000887b  mov     [rbp+2C0h+hKey], rax
0x18000887f  lea     rcx, [rbp+2C0h+hKey]; this
0x180008883  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008888  test    ebx, ebx
0x18000888a  js      loc_1800089C2
0x180008890  xor     ecx, ecx
0x180008892  jmp     loc_180008A6E
0x180008897  test    r12d, r12d
0x18000889a  jnz     short loc_1800088EC
0x18000889c  mov     [rbp+2C0h+hKey], rcx
0x1800088a0  mov     [rbp+2C0h+var_2B0], rcx
0x1800088a4  mov     [rbp+2C0h+var_2A8], rcx
0x1800088a8  mov     r9d, 20006h; unsigned int
0x1800088ae  xor     r8d, r8d; lpSubKey
0x1800088b1  mov     rdx, [rbp+2C0h+var_2A0]; hKey
0x1800088b5  lea     rcx, [rbp+2C0h+hKey]; this
0x1800088b9  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x1800088be  mov     ebx, eax
0x1800088c0  test    eax, eax
0x1800088c2  jnz     loc_180008CAF
0x1800088c8  lea     rdx, [rbp+2C0h+ValueName]; lpValueName
0x1800088cc  mov     rcx, [rbp+2C0h+hKey]; hKey
0x1800088d0  call    cs:__imp_RegDeleteValueW
0x1800088d6  mov     ebx, eax
0x1800088d8  test    eax, 0FFFFFFFDh
0x1800088dd  jnz     loc_180008CAD
0x1800088e3  lea     rcx, [rbp+2C0h+hKey]; this
0x1800088e7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800088ec  mov     rdx, rdi; unsigned __int16 *
0x1800088ef  mov     rcx, rsi; this
0x1800088f2  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800088f7  mov     ebx, eax
0x1800088f9  test    eax, eax
0x1800088fb  jns     loc_1800086E2
0x180008901  jmp     loc_1800089C2
0x180008906  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000890b  mov     rcx, rdi; lpsz
0x18000890e  call    ?StrChrW@CRegParser@ATL@@KAPEBGPEBGG@Z; ATL::CRegParser::StrChrW(ushort const *,ushort)
0x180008913  test    rax, rax
0x180008916  jnz     loc_1800089BD
0x18000891c  cmp     [rbp+2C0h+var_2C0], ebx
0x18000891f  jz      loc_180008ABE
0x180008925  mov     r9d, 0F003Fh; unsigned int
0x18000892b  mov     r8, rdi; lpSubKey
0x18000892e  mov     rbx, [rbp+2C0h+var_2A0]
0x180008932  mov     rdx, rbx; hKey
0x180008935  lea     rcx, [rbp+2C0h+var_290]; this
0x180008939  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x18000893e  xor     r14d, r14d
0x180008941  test    eax, eax
0x180008943  jz      loc_1800089FA
0x180008949  mov     r9d, 20019h; unsigned int
0x18000894f  mov     r8, rdi; lpSubKey
0x180008952  mov     rdx, rbx; hKey
0x180008955  lea     rcx, [rbp+2C0h+var_290]; this
0x180008959  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x18000895e  test    eax, eax
0x180008960  jz      loc_1800089FA
0x180008966  mov     [rbp+2C0h+dwDisposition], r14d
0x18000896a  mov     [rbp+2C0h+var_270], r14
0x18000896e  lea     rax, [rbp+2C0h+dwDisposition]
0x180008972  mov     [rsp+310h+lpdwDisposition], rax; lpdwDisposition
0x180008977  lea     rax, [rbp+2C0h+var_270]
0x18000897b  mov     [rsp+310h+phkResult], rax; phkResult
0x180008980  mov     [rsp+310h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180008985  mov     [rsp+310h+samDesired], 2001Fh; samDesired
0x18000898d  mov     [rsp+310h+dwOptions], r14d; dwOptions
0x180008992  xor     r9d, r9d; lpClass
0x180008995  xor     r8d, r8d; Reserved
0x180008998  mov     rdx, rdi; lpSubKey
0x18000899b  mov     rcx, rbx; hKey
0x18000899e  call    cs:__imp_RegCreateKeyExW
0x1800089a4  test    eax, eax
0x1800089a6  jnz     short loc_1800089BD
0x1800089a8  lea     rcx, [rbp+2C0h+var_290]; this
0x1800089ac  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800089b1  mov     r15, [rbp+2C0h+var_270]
0x1800089b5  mov     [rbp+2C0h+var_290], r15
0x1800089b9  test    eax, eax
0x1800089bb  jz      short loc_1800089FE
0x1800089bd  mov     ebx, 80020009h
0x1800089c2  lea     rcx, [rbp+2C0h+var_290]; this
0x1800089c6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800089cb  nop
0x1800089cc  lea     rcx, [rbp+2C0h+var_268]
0x1800089d0  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800089d5  mov     eax, ebx
0x1800089d7  mov     rcx, [rbp+2C0h+var_50]
0x1800089de  xor     rcx, rbp; StackCookie
0x1800089e1  call    __security_check_cookie
0x1800089e6  lea     rsp, [rbp+288h]
0x1800089ed  pop     r15
0x1800089ef  pop     r14
0x1800089f1  pop     r13
0x1800089f3  pop     r12
0x1800089f5  pop     rdi
0x1800089f6  pop     rsi
0x1800089f7  pop     rbx
0x1800089f8  pop     rbp
0x1800089f9  retn
0x1800089fa  mov     r15, [rbp+2C0h+var_290]
0x1800089fe  movzx   eax, word ptr [rdi]
0x180008a01  sub     ax, 4Ch ; 'L'
0x180008a05  mov     ecx, 0FFDFh
0x180008a0a  test    cx, ax
0x180008a0d  jnz     short loc_180008A2E
0x180008a0f  lea     rdx, aLocalserver32; "LocalServer32"
0x180008a16  mov     rcx, rdi; lpString1
0x180008a19  call    cs:__imp_lstrcmpiW
0x180008a1f  movzx   r14d, r14b
0x180008a23  test    eax, eax
0x180008a25  mov     eax, 1
0x180008a2a  cmovz   r14d, eax
0x180008a2e  mov     rdx, rdi; unsigned __int16 *
0x180008a31  mov     rcx, rsi; this
0x180008a34  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008a39  mov     ebx, eax
0x180008a3b  xor     ecx, ecx
0x180008a3d  test    eax, eax
0x180008a3f  js      short loc_1800089C2
0x180008a41  cmp     word ptr [rdi], 3Dh ; '='
0x180008a45  jnz     short loc_180008A6A
0x180008a47  mov     byte ptr [rsp+310h+dwOptions], r14b; bool
0x180008a4c  mov     r9, rdi; unsigned __int16 *
0x180008a4f  xor     r8d, r8d; unsigned __int16 *
0x180008a52  lea     rdx, [rbp+2C0h+var_290]; struct ATL::CRegKey *
0x180008a56  mov     rcx, rsi; this
0x180008a59  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x180008a5e  mov     ebx, eax
0x180008a60  xor     ecx, ecx
0x180008a62  test    eax, eax
0x180008a64  js      loc_1800089C2
0x180008a6a  mov     r14d, [rbp+2C0h+var_2C0]
0x180008a6e  cmp     word ptr [rdi], 7Bh ; '{'
0x180008a72  jnz     loc_1800086E2
0x180008a78  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008a7c  inc     rax
0x180008a7f  cmp     [rdi+rax*2], cx
0x180008a83  jnz     short loc_180008A7C
0x180008a85  cmp     rax, 1
0x180008a89  jnz     loc_1800086E2
0x180008a8f  mov     [rsp+310h+dwOptions], ecx; unsigned int
0x180008a93  mov     r9d, r14d; int
0x180008a96  mov     r8, r15; HKEY
0x180008a99  mov     rdx, rdi; unsigned __int16 *
0x180008a9c  mov     rcx, rsi; this
0x180008a9f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008aa4  mov     ebx, eax
0x180008aa6  test    eax, eax
0x180008aa8  js      loc_1800089C2
0x180008aae  mov     rdx, rdi; unsigned __int16 *
0x180008ab1  mov     rcx, rsi; this
0x180008ab4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008ab9  jmp     loc_1800088F7
0x180008abe  mov     r14, [rbp+2C0h+var_2A0]
0x180008ac2  test    r12d, r12d
0x180008ac5  jnz     short loc_180008AEB
0x180008ac7  mov     r9d, 20019h; unsigned int
0x180008acd  mov     r8, rdi; lpSubKey
0x180008ad0  mov     rdx, r14; hKey
  ... truncated ...
```
