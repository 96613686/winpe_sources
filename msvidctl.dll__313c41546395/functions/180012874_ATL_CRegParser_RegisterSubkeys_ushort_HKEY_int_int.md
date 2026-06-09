# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180012874`
- end: `0x180012e8e`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1562`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, unsigned __int16 *@<rdx>, HKEY@<r8>, int@<r9d>, int)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800125a8`
- `0x180012874`

## callees

- `0x180004640`
- `0x180006b08`
- `0x18000f204`
- `0x18000fa14`
- `0x1800109fc`
- `0x180010e10`
- `0x180010e4c`
- `0x180010e9c`
- `0x180011110`
- `0x1800114a0`
- `0x18001195c`
- `0x1800119e0`
- `0x180011c40`
- `0x180012218`
- `0x180012874`
- `0x180013534`
- `0x180013b08`

## import_xrefs

- `KERNEL32!lstrcpynW` at `0x180012cd0`
- `KERNEL32!lstrcpynW` at `0x180012cd0`
- `KERNEL32!lstrcmpiW` at `0x1800128fa`
- `KERNEL32!lstrcmpiW` at `0x18001290d`
- `KERNEL32!lstrcmpiW` at `0x1800129d6`
- `KERNEL32!lstrcmpiW` at `0x180012a04`
- `KERNEL32!lstrcmpiW` at `0x180012ba9`
- `KERNEL32!lstrcmpiW` at `0x1800128fa`
- `KERNEL32!lstrcmpiW` at `0x18001290d`
- `KERNEL32!lstrcmpiW` at `0x1800129d6`
- `KERNEL32!lstrcmpiW` at `0x180012a04`
- `KERNEL32!lstrcmpiW` at `0x180012ba9`
- `ADVAPI32!RegDeleteValueW` at `0x180012ad4`
- `ADVAPI32!RegDeleteValueW` at `0x180012ad4`

## string_xrefs

- `0x180012903`: `ForceRemove`
- `0x1800129cc`: `NoRemove`
- `0x1800128f0`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  HKEY v7; // r12
  int Token; // ebx
  int *v9; // r13
  int v10; // r15d
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // r14d
  LSTATUS v14; // eax
  bool v15; // cc
  int v16; // eax
  unsigned __int64 v17; // rdx
  HKEY v18; // rbx
  unsigned __int16 *v19; // r9
  bool v20; // r14
  __int64 v21; // rax
  HKEY v22; // r14
  void *v23; // rsp
  ATL::CRegParser *v24; // rcx
  ATL::CRegParser *v25; // rcx
  ATL::CRegParser *v26; // rcx
  ATL::CRegParser *v27; // rcx
  unsigned int v29; // [rsp+20h] [rbp-20h]
  struct _SECURITY_ATTRIBUTES *v30; // [rsp+30h] [rbp-10h]
  unsigned int *v31; // [rsp+38h] [rbp-8h]
  int v32; // [rsp+40h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+8h] BYREF
  __int64 v34; // [rsp+50h] [rbp+10h]
  __int64 v35; // [rsp+58h] [rbp+18h]
  HKEY v36; // [rsp+60h] [rbp+20h]
  int v37; // [rsp+68h] [rbp+28h]
  HKEY v38[3]; // [rsp+70h] [rbp+30h] BYREF
  int v39; // [rsp+88h] [rbp+48h]
  _QWORD v40[2]; // [rsp+90h] [rbp+50h] BYREF
  WCHAR ValueName[264]; // [rsp+A0h] [rbp+60h] BYREF

  v32 = a4;
  v36 = a3;
  v40[0] = 0;
  v7 = 0;
  memset(v38, 0, sizeof(v38));
  Token = ATL::CRegParser::NextToken(this, a2);
  if ( Token >= 0 )
  {
    v9 = 0;
    v37 = 1;
    v10 = a5;
    v39 = a5;
    while ( *a2 != 125 )
    {
      v11 = lstrcmpiW(a2, L"Delete");
      if ( lstrcmpiW(a2, L"ForceRemove") && v11 )
        goto LABEL_16;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        break;
      if ( !v32 )
        goto LABEL_16;
      hKey = 0;
      v34 = 0;
      v35 = 0;
      if ( ATL::CRegParser::StrChrW(a2, 0x5Cu) )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_80:
        Token = -2147352567;
        break;
      }
      if ( ATL::CRegParser::CanForceRemoveKey(v12, a2) )
      {
        hKey = v36;
        ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, a2);
        hKey = 0;
      }
      if ( v11 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_16:
        if ( !lstrcmpiW(a2, L"NoRemove") )
        {
          v37 = 0;
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            break;
        }
        if ( lstrcmpiW(a2, L"Val") )
        {
          if ( ATL::CRegParser::StrChrW(a2, 0x5Cu) )
            goto LABEL_80;
          if ( v32 )
          {
            v18 = v36;
            if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v38, v36, a2, 0xF003Fu, 0)
              && (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v38, v18, a2, 0x20019u, 0)
              && (unsigned int)ATL::CRegKey::Create((ATL::CRegKey *)v38, v18, a2, v19, v29, 0x2001Fu, v30, v31) )
            {
              goto LABEL_80;
            }
            v20 = 0;
            if ( ((*a2 - 76) & 0xFFDF) == 0 )
              v20 = lstrcmpiW(a2, L"LocalServer32") == 0;
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              break;
            if ( *a2 == 61 )
            {
              Token = ATL::CRegParser::AddValue((ATL::CRegObject **)this, v38, 0, a2, v20);
              if ( Token < 0 )
                break;
            }
            v7 = v38[0];
            goto LABEL_43;
          }
          v22 = v36;
          if ( !v10 )
          {
            v10 = ATL::CRegKey::Open((ATL::CRegKey *)v38, v36, a2, 0x20019u, 0) != 0;
            v7 = v38[0];
          }
          if ( !v9 )
          {
            if ( ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)0x208, v17) )
            {
              v23 = alloca(528);
              v9 = &v32;
            }
            else
            {
              v9 = (int *)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(
                            v40,
                            520);
            }
            if ( !v9 )
            {
              Token = -2147024882;
              break;
            }
          }
          lstrcpynW((LPWSTR)v9, a2, 260);
          if ( v10 || ATL::CRegParser::HasSubKeys(v24, v7) || ATL::CRegParser::HasValues(v25, v7) )
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
LABEL_69:
                if ( ATL::CRegParser::HasSubKeys(v26, v7) )
                {
                  if ( ATL::CRegParser::CanForceRemoveKey(v27, (const unsigned __int16 *)v9) )
                  {
                    ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v38, (const unsigned __int16 *)v9);
                    v7 = v38[0];
                  }
LABEL_49:
                  v16 = ATL::CRegParser::NextToken(this, a2);
                  goto LABEL_30;
                }
                goto LABEL_72;
              }
              Token = ATL::CRegParser::NextToken(this, a2);
              if ( Token < 0 )
                break;
              Token = ATL::CRegParser::SkipAssignment(this, a2);
              if ( Token < 0 )
                break;
              v10 = v39;
            }
            else if ( !v10 )
            {
              goto LABEL_69;
            }
          }
          else
          {
LABEL_72:
            if ( (unsigned int)ATL::CRegKey::Close((ATL::CRegKey *)v38) )
              goto LABEL_80;
            if ( v37 )
            {
              v34 = 0;
              v35 = 0;
              hKey = v22;
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
            v7 = v38[0];
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
            goto LABEL_80;
          v13 = v32;
          if ( v32 )
          {
            v34 = 0;
            v35 = 0;
            hKey = v36;
            Token = ATL::CRegParser::AddValue((ATL::CRegObject **)this, &hKey, ValueName, a2, 0);
            hKey = 0;
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            if ( Token < 0 )
              break;
            goto LABEL_44;
          }
          if ( !v10 )
          {
            hKey = 0;
            v34 = 0;
            v35 = 0;
            v14 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, v36, 0, 0x20006u, 0);
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
LABEL_43:
        v13 = v32;
LABEL_44:
        if ( *a2 == 123 )
        {
          v21 = -1;
          do
            ++v21;
          while ( a2[v21] );
          if ( v21 == 1 )
          {
            Token = ATL::CRegParser::RegisterSubkeys(this, a2, v7, v13, 0);
            if ( Token < 0 )
              break;
            goto LABEL_49;
          }
        }
      }
    }
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v38);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(v40);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x180012874  push    rbp
0x180012876  push    rbx
0x180012877  push    rsi
0x180012878  push    rdi
0x180012879  push    r12
0x18001287b  push    r13
0x18001287d  push    r14
0x18001287f  push    r15
0x180012881  sub     rsp, 2C8h
0x180012888  lea     rbp, [rsp+40h]
0x18001288d  mov     rax, cs:__security_cookie
0x180012894  xor     rax, rbp
0x180012897  mov     [rbp+2C0h+var_50], rax
0x18001289e  mov     [rbp+2C0h+var_2C0], r9d
0x1800128a2  mov     [rbp+2C0h+var_2A0], r8
0x1800128a6  mov     rdi, rdx
0x1800128a9  mov     rsi, rcx
0x1800128ac  xor     r14d, r14d
0x1800128af  mov     [rbp+2C0h+var_270], r14
0x1800128b3  mov     r12d, r14d
0x1800128b6  mov     [rbp+2C0h+var_290], r14
0x1800128ba  mov     [rbp+2C0h+var_288], r14
0x1800128be  mov     [rbp+2C0h+var_280], r14
0x1800128c2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800128c7  mov     ebx, eax
0x1800128c9  test    eax, eax
0x1800128cb  js      loc_180012E36
0x1800128d1  mov     r13d, r14d
0x1800128d4  mov     [rbp+2C0h+var_298], 1
0x1800128db  mov     r15d, [rbp+2C0h+arg_20]
0x1800128e2  mov     [rbp+2C0h+var_278], r15d
0x1800128e6  cmp     word ptr [rdi], 7Dh ; '}'
0x1800128ea  jz      loc_180012E36
0x1800128f0  lea     rdx, aDelete; "Delete"
0x1800128f7  mov     rcx, rdi; lpString1
0x1800128fa  call    cs:__imp_lstrcmpiW
0x180012900  mov     r14d, eax
0x180012903  lea     rdx, aForceremove; "ForceRemove"
0x18001290a  mov     rcx, rdi; lpString1
0x18001290d  call    cs:__imp_lstrcmpiW
0x180012913  xor     ebx, ebx
0x180012915  test    eax, eax
0x180012917  jz      short loc_180012922
0x180012919  test    r14d, r14d
0x18001291c  jnz     loc_1800129CC
0x180012922  mov     rdx, rdi; unsigned __int16 *
0x180012925  mov     rcx, rsi; this
0x180012928  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001292d  mov     ebx, eax
0x18001292f  test    eax, eax
0x180012931  js      loc_180012E36
0x180012937  xor     ebx, ebx
0x180012939  cmp     [rbp+2C0h+var_2C0], ebx
0x18001293c  jz      loc_1800129CC
0x180012942  mov     [rbp+2C0h+hKey], rbx
0x180012946  mov     [rbp+2C0h+var_2B0], rbx
0x18001294a  mov     [rbp+2C0h+var_2A8], rbx
0x18001294e  lea     edx, [rbx+5Ch]; unsigned __int16
0x180012951  mov     rcx, rdi; lpsz
0x180012954  call    ?StrChrW@CRegParser@ATL@@KAPEBGPEBGG@Z; ATL::CRegParser::StrChrW(ushort const *,ushort)
0x180012959  test    rax, rax
0x18001295c  jnz     loc_180012E28
0x180012962  mov     rdx, rdi; unsigned __int16 *
0x180012965  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18001296a  test    eax, eax
0x18001296c  jz      short loc_180012986
0x18001296e  mov     rax, [rbp+2C0h+var_2A0]
0x180012972  mov     [rbp+2C0h+hKey], rax
0x180012976  mov     rdx, rdi; unsigned __int16 *
0x180012979  lea     rcx, [rbp+2C0h+hKey]; this
0x18001297d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180012982  mov     [rbp+2C0h+hKey], rbx
0x180012986  test    r14d, r14d
0x180012989  jnz     short loc_1800129C3
0x18001298b  mov     rdx, rdi; unsigned __int16 *
0x18001298e  mov     rcx, rsi; this
0x180012991  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180012996  mov     ebx, eax
0x180012998  test    eax, eax
0x18001299a  js      loc_180012E26
0x1800129a0  mov     rdx, rdi; unsigned __int16 *
0x1800129a3  mov     rcx, rsi; this
0x1800129a6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800129ab  mov     ebx, eax
0x1800129ad  lea     rcx, [rbp+2C0h+hKey]; this
0x1800129b1  test    eax, eax
0x1800129b3  js      loc_180012E7F
0x1800129b9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800129be  jmp     loc_180012BFA
0x1800129c3  lea     rcx, [rbp+2C0h+hKey]; this
0x1800129c7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800129cc  lea     rdx, aNoremove; "NoRemove"
0x1800129d3  mov     rcx, rdi; lpString1
0x1800129d6  call    cs:__imp_lstrcmpiW
0x1800129dc  test    eax, eax
0x1800129de  jnz     short loc_1800129FA
0x1800129e0  mov     [rbp+2C0h+var_298], ebx
0x1800129e3  mov     rdx, rdi; unsigned __int16 *
0x1800129e6  mov     rcx, rsi; this
0x1800129e9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800129ee  mov     ebx, eax
0x1800129f0  test    eax, eax
0x1800129f2  js      loc_180012E36
0x1800129f8  xor     ebx, ebx
0x1800129fa  lea     rdx, String2; "Val"
0x180012a01  mov     rcx, rdi; lpString1
0x180012a04  call    cs:__imp_lstrcmpiW
0x180012a0a  test    eax, eax
0x180012a0c  jnz     loc_180012B0A
0x180012a12  lea     rdx, [rbp+2C0h+ValueName]; unsigned __int16 *
0x180012a16  mov     rcx, rsi; this
0x180012a19  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180012a1e  mov     ebx, eax
0x180012a20  test    eax, eax
0x180012a22  js      loc_180012E36
0x180012a28  mov     rdx, rdi; unsigned __int16 *
0x180012a2b  mov     rcx, rsi; this
0x180012a2e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180012a33  mov     ebx, eax
0x180012a35  xor     ecx, ecx
0x180012a37  test    eax, eax
0x180012a39  js      loc_180012E36
0x180012a3f  cmp     word ptr [rdi], 3Dh ; '='
0x180012a43  jnz     loc_180012E31
0x180012a49  mov     r14d, [rbp+2C0h+var_2C0]
0x180012a4d  test    r14d, r14d
0x180012a50  jz      short loc_180012A97
0x180012a52  mov     [rbp+2C0h+var_2B0], rcx
0x180012a56  mov     [rbp+2C0h+var_2A8], rcx
0x180012a5a  mov     rax, [rbp+2C0h+var_2A0]
0x180012a5e  mov     [rbp+2C0h+hKey], rax
0x180012a62  mov     [rsp+300h+var_2E0], cl; bool
0x180012a66  mov     r9, rdi; unsigned __int16 *
0x180012a69  lea     r8, [rbp+2C0h+ValueName]; unsigned __int16 *
0x180012a6d  lea     rdx, [rbp+2C0h+hKey]; struct ATL::CRegKey *
0x180012a71  mov     rcx, rsi; this
0x180012a74  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x180012a79  mov     ebx, eax
0x180012a7b  xor     eax, eax
0x180012a7d  mov     [rbp+2C0h+hKey], rax
0x180012a81  lea     rcx, [rbp+2C0h+hKey]; this
0x180012a85  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180012a8a  test    ebx, ebx
0x180012a8c  js      loc_180012E36
0x180012a92  jmp     loc_180012BFE
0x180012a97  test    r15d, r15d
0x180012a9a  jnz     short loc_180012AF0
0x180012a9c  mov     [rbp+2C0h+hKey], rcx
0x180012aa0  mov     [rbp+2C0h+var_2B0], rcx
0x180012aa4  mov     [rbp+2C0h+var_2A8], rcx
0x180012aa8  mov     dword ptr [rsp+300h+var_2E0], ecx; unsigned int
0x180012aac  mov     r9d, 20006h; unsigned int
0x180012ab2  xor     r8d, r8d; lpSubKey
0x180012ab5  mov     rdx, [rbp+2C0h+var_2A0]; hKey
0x180012ab9  lea     rcx, [rbp+2C0h+hKey]; this
0x180012abd  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x180012ac2  mov     ebx, eax
0x180012ac4  test    eax, eax
0x180012ac6  jnz     loc_180012E70
0x180012acc  lea     rdx, [rbp+2C0h+ValueName]; lpValueName
0x180012ad0  mov     rcx, [rbp+2C0h+hKey]; hKey
0x180012ad4  call    cs:__imp_RegDeleteValueW
0x180012ada  mov     ebx, eax
0x180012adc  test    eax, 0FFFFFFFDh
0x180012ae1  jnz     loc_180012E6E
0x180012ae7  lea     rcx, [rbp+2C0h+hKey]; this
0x180012aeb  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180012af0  mov     rdx, rdi; unsigned __int16 *
0x180012af3  mov     rcx, rsi; this
0x180012af6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180012afb  mov     ebx, eax
0x180012afd  test    eax, eax
0x180012aff  jns     loc_1800128E6
0x180012b05  jmp     loc_180012E36
0x180012b0a  mov     edx, 5Ch ; '\'; unsigned __int16
0x180012b0f  mov     rcx, rdi; lpsz
0x180012b12  call    ?StrChrW@CRegParser@ATL@@KAPEBGPEBGG@Z; ATL::CRegParser::StrChrW(ushort const *,ushort)
0x180012b17  test    rax, rax
0x180012b1a  jnz     loc_180012E31
0x180012b20  cmp     [rbp+2C0h+var_2C0], ebx
0x180012b23  jz      loc_180012C50
0x180012b29  mov     dword ptr [rsp+300h+var_2E0], ebx; unsigned int
0x180012b2d  mov     r9d, 0F003Fh; unsigned int
0x180012b33  mov     r8, rdi; lpSubKey
0x180012b36  mov     rbx, [rbp+2C0h+var_2A0]
0x180012b3a  mov     rdx, rbx; hKey
0x180012b3d  lea     rcx, [rbp+2C0h+var_290]; this
0x180012b41  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x180012b46  xor     r12d, r12d
0x180012b49  test    eax, eax
0x180012b4b  jz      short loc_180012B8A
0x180012b4d  mov     dword ptr [rsp+300h+var_2E0], r12d; unsigned int
0x180012b52  mov     r9d, 20019h; unsigned int
0x180012b58  mov     r8, rdi; lpSubKey
0x180012b5b  mov     rdx, rbx; hKey
0x180012b5e  lea     rcx, [rbp+2C0h+var_290]; this
0x180012b62  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x180012b67  test    eax, eax
0x180012b69  jz      short loc_180012B8A
0x180012b6b  mov     [rsp+300h+var_2D8], 2001Fh; unsigned int
0x180012b73  mov     r8, rdi; lpSubKey
0x180012b76  mov     rdx, rbx; hKey
0x180012b79  lea     rcx, [rbp+2C0h+var_290]; this
0x180012b7d  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180012b82  test    eax, eax
0x180012b84  jnz     loc_180012E31
0x180012b8a  movzx   r14d, r12b
0x180012b8e  movzx   eax, word ptr [rdi]
0x180012b91  sub     ax, 4Ch ; 'L'
0x180012b95  mov     ecx, 0FFDFh
0x180012b9a  test    cx, ax
0x180012b9d  jnz     short loc_180012BBA
0x180012b9f  lea     rdx, aLocalserver32; "LocalServer32"
0x180012ba6  mov     rcx, rdi; lpString1
0x180012ba9  call    cs:__imp_lstrcmpiW
0x180012baf  test    eax, eax
0x180012bb1  mov     eax, 1
0x180012bb6  cmovz   r14d, eax
0x180012bba  mov     rdx, rdi; unsigned __int16 *
0x180012bbd  mov     rcx, rsi; this
0x180012bc0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180012bc5  mov     ebx, eax
0x180012bc7  test    eax, eax
0x180012bc9  js      loc_180012E36
0x180012bcf  cmp     word ptr [rdi], 3Dh ; '='
0x180012bd3  jnz     short loc_180012BF6
0x180012bd5  mov     [rsp+300h+var_2E0], r14b; bool
0x180012bda  mov     r9, rdi; unsigned __int16 *
0x180012bdd  xor     r8d, r8d; unsigned __int16 *
0x180012be0  lea     rdx, [rbp+2C0h+var_290]; struct ATL::CRegKey *
0x180012be4  mov     rcx, rsi; this
0x180012be7  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x180012bec  mov     ebx, eax
0x180012bee  test    eax, eax
0x180012bf0  js      loc_180012E36
0x180012bf6  mov     r12, [rbp+2C0h+var_290]
0x180012bfa  mov     r14d, [rbp+2C0h+var_2C0]
0x180012bfe  cmp     word ptr [rdi], 7Bh ; '{'
0x180012c02  jnz     loc_1800128E6
0x180012c08  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012c0c  xor     ecx, ecx
0x180012c0e  inc     rax
0x180012c11  cmp     [rdi+rax*2], cx
0x180012c15  jnz     short loc_180012C0E
0x180012c17  cmp     rax, 1
0x180012c1b  jnz     loc_1800128E6
0x180012c21  mov     dword ptr [rsp+300h+var_2E0], ecx; int
0x180012c25  mov     r9d, r14d; int
0x180012c28  mov     r8, r12; HKEY
0x180012c2b  mov     rdx, rdi; unsigned __int16 *
0x180012c2e  mov     rcx, rsi; this
0x180012c31  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180012c36  mov     ebx, eax
0x180012c38  test    eax, eax
0x180012c3a  js      loc_180012E36
0x180012c40  mov     rdx, rdi; unsigned __int16 *
0x180012c43  mov     rcx, rsi; this
0x180012c46  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180012c4b  jmp     loc_180012AFB
0x180012c50  mov     r14, [rbp+2C0h+var_2A0]
0x180012c54  test    r15d, r15d
0x180012c57  jnz     short loc_180012C80
0x180012c59  mov     dword ptr [rsp+300h+var_2E0], ebx; unsigned int
0x180012c5d  mov     r9d, 20019h; unsigned int
0x180012c63  mov     r8, rdi; lpSubKey
0x180012c66  mov     rdx, r14; hKey
0x180012c69  lea     rcx, [rbp+2C0h+var_290]; this
0x180012c6d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x180012c72  test    eax, eax
0x180012c74  lea     eax, [r15+1]
0x180012c78  cmovnz  r15d, eax
0x180012c7c  mov     r12, [rbp+2C0h+var_290]
0x180012c80  test    r13, r13
0x180012c83  jnz     short loc_180012CC4
0x180012c85  mov     r13d, 208h
0x180012c8b  mov     ecx, r13d; this
0x180012c8e  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180012c93  test    al, al
0x180012c95  jz      short loc_180012CAC
0x180012c97  mov     eax, [rsp+300h+var_300]
0x180012c9a  lea     eax, [r13+8]
0x180012c9e  sub     rsp, rax
0x180012ca1  lea     r13, [rsp+300h+var_2C0]
0x180012ca6  mov     eax, [r13+0]
0x180012caa  jmp     short loc_180012CBB
0x180012cac  mov     rdx, r13
0x180012caf  lea     rcx, [rbp+2C0h+var_270]
0x180012cb3  call    ?Allocate@?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAAPEAX_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(unsigned __int64)
0x180012cb8  mov     r13, rax
0x180012cbb  test    r13, r13
0x180012cbe  jz      loc_180012E86
0x180012cc4  mov     r8d, 104h; iMaxLength
0x180012cca  mov     rdx, rdi; lpString2
0x180012ccd  mov     rcx, r13; lpString1
0x180012cd0  call    cs:__imp_lstrcpynW
0x180012cd6  test    r15d, r15d
0x180012cd9  jnz     short loc_180012CF7
0x180012cdb  mov     rdx, r12; HKEY
0x180012cde  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x180012ce3  test    eax, eax
  ... truncated ...
```
