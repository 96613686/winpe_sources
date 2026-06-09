# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000a980`
- end: `0x18000b088`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1800`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, unsigned __int16 *@<rdx>, HKEY@<r8>, int@<r9d>, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x18000a980`
- `0x18001418c`

## callees

- `0x18000a980`
- `0x18000b090`
- `0x18000b2d8`
- `0x180011700`
- `0x180011bd8`
- `0x180012430`
- `0x180012d7c`
- `0x1800131ec`
- `0x180013270`
- `0x1800139a8`
- `0x180013b1c`
- `0x18001405c`
- `0x180014c70`
- `0x180014d34`
- `0x1800153c8`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ace8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ace8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000abee`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000abee`
- `KERNEL32!lstrcmpiW` at `0x18000aa11`
- `KERNEL32!lstrcmpiW` at `0x18000aa24`
- `KERNEL32!lstrcmpiW` at `0x18000aaf1`
- `KERNEL32!lstrcmpiW` at `0x18000ab1f`
- `KERNEL32!lstrcmpiW` at `0x18000ad35`
- `KERNEL32!lstrcmpiW` at `0x18000aa11`
- `KERNEL32!lstrcmpiW` at `0x18000aa24`
- `KERNEL32!lstrcmpiW` at `0x18000aaf1`
- `KERNEL32!lstrcmpiW` at `0x18000ab1f`
- `KERNEL32!lstrcmpiW` at `0x18000ad35`
- `KERNEL32!lstrcpynW` at `0x18000ae5b`
- `KERNEL32!lstrcpynW` at `0x18000ae5b`

## string_xrefs

- `0x18000aa1a`: `ForceRemove`
- `0x18000aae7`: `NoRemove`
- `0x18000aa07`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
  int v14; // eax
  LSTATUS v15; // eax
  int v16; // eax
  unsigned __int64 v18; // rdx
  HKEY v19; // rbx
  bool v20; // r14
  int v21; // eax
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
  HKEY v34[3]; // [rsp+70h] [rbp+20h] BYREF
  HKEY v35; // [rsp+88h] [rbp+38h]
  int v36; // [rsp+90h] [rbp+40h]
  DWORD dwDisposition; // [rsp+94h] [rbp+44h] BYREF
  int v38; // [rsp+98h] [rbp+48h]
  HKEY phkResult; // [rsp+A0h] [rbp+50h] BYREF
  _QWORD *v40; // [rsp+A8h] [rbp+58h] BYREF
  WCHAR ValueName[264]; // [rsp+B0h] [rbp+60h] BYREF

  v30 = a4;
  v35 = a3;
  v40 = 0;
  v7 = 0;
  memset(v34, 0, sizeof(v34));
  Token = ATL::CRegParser::NextToken(this, a2);
  if ( Token < 0 )
  {
    ATL::CRegKey::Close((ATL::CRegKey *)v34);
    goto LABEL_33;
  }
  v9 = 0;
  v36 = 1;
  v10 = a5;
  v38 = a5;
  while ( 1 )
  {
    if ( *a2 == 125 )
      goto LABEL_32;
    v11 = lstrcmpiW(a2, L"Delete");
    if ( lstrcmpiW(a2, L"ForceRemove") && v11 )
      goto LABEL_17;
    Token = ATL::CRegParser::NextToken(this, a2);
    if ( Token < 0 )
      goto LABEL_32;
    if ( !v30 )
      goto LABEL_17;
    hKey = 0;
    v32 = 0;
    v33 = 0;
    if ( ATL::CRegParser::StrChrW(a2, 0x5Cu) )
      break;
    if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, a2) )
    {
      hKey = v35;
      ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, a2);
      hKey = 0;
    }
    if ( v11 )
    {
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_17:
      if ( !lstrcmpiW(a2, L"NoRemove") )
      {
        v36 = 0;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_32;
      }
      if ( lstrcmpiW(a2, L"Val") )
      {
        if ( ATL::CRegParser::StrChrW(a2, 0x5Cu) )
          goto LABEL_40;
        if ( v30 )
        {
          v19 = v35;
          v20 = 0;
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, v35, a2, 0xF003Fu, dwOptions)
            && (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, v19, a2, 0x20019u, dwOptions) )
          {
            dwDisposition = 0;
            phkResult = 0;
            if ( RegCreateKeyExW(v19, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition)
              || (v21 = ATL::CRegKey::Close((ATL::CRegKey *)v34), v7 = phkResult, v34[0] = phkResult, v21) )
            {
LABEL_40:
              ATL::CRegKey::Close((ATL::CRegKey *)v34);
              goto LABEL_85;
            }
          }
          else
          {
            v7 = v34[0];
          }
          if ( ((*a2 - 76) & 0xFFDF) == 0 )
            v20 = lstrcmpiW(a2, L"LocalServer32") == 0;
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_32;
          if ( *a2 == 61 )
          {
            Token = ATL::CRegParser::AddValue((ATL::CRegObject **)this, v34, 0, a2, v20);
            if ( Token < 0 )
              goto LABEL_32;
          }
          goto LABEL_47;
        }
        v23 = v35;
        if ( !v10 )
        {
          v10 = ATL::CRegKey::Open((ATL::CRegKey *)v34, v35, a2, 0x20019u, dwOptions) != 0;
          v7 = v34[0];
        }
        if ( !v9 )
        {
          if ( ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)0x208, v18) )
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
            ATL::CRegKey::Close((ATL::CRegKey *)v34);
            Token = -2147024882;
            goto LABEL_33;
          }
        }
        lstrcpynW((LPWSTR)v9, a2, 260);
        if ( v10 || ATL::CRegParser::HasSubKeys(v25, v7) || ATL::CRegParser::HasValues(v26, v7) )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_32;
          Token = ATL::CRegParser::SkipAssignment(this, a2);
          if ( Token < 0 )
            goto LABEL_32;
          if ( *a2 == 123 )
          {
            Token = ATL::CRegParser::RegisterSubkeys(this, a2, v7, 0, v10);
            if ( Token < 0 )
              goto LABEL_32;
            if ( !v10 )
            {
LABEL_73:
              if ( ATL::CRegParser::HasSubKeys(v27, v7) )
              {
                if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v28, (const unsigned __int16 *)v9) )
                {
                  ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v34, (const unsigned __int16 *)v9);
                  v7 = v34[0];
                }
LABEL_53:
                v16 = ATL::CRegParser::NextToken(this, a2);
                goto LABEL_31;
              }
              goto LABEL_76;
            }
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              goto LABEL_32;
            Token = ATL::CRegParser::SkipAssignment(this, a2);
            if ( Token < 0 )
              goto LABEL_32;
            v10 = v38;
          }
          else if ( !v10 )
          {
            goto LABEL_73;
          }
        }
        else
        {
LABEL_76:
          if ( (unsigned int)ATL::CRegKey::Close((ATL::CRegKey *)v34) )
            goto LABEL_40;
          if ( v36 )
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
            goto LABEL_32;
          Token = ATL::CRegParser::SkipAssignment(this, a2);
          if ( Token < 0 )
            goto LABEL_32;
          v7 = v34[0];
        }
      }
      else
      {
        Token = ATL::CRegParser::NextToken(this, ValueName);
        if ( Token < 0 )
          goto LABEL_32;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_32;
        if ( *a2 != 61 )
          goto LABEL_40;
        v13 = v30;
        if ( v30 )
        {
          v32 = 0;
          v33 = 0;
          hKey = v35;
          Token = ATL::CRegParser::AddValue((ATL::CRegObject **)this, &hKey, ValueName, a2, 0);
          hKey = 0;
          if ( Token < 0 )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            ATL::CRegKey::Close((ATL::CRegKey *)v34);
            goto LABEL_33;
          }
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          goto LABEL_48;
        }
        if ( !v10 )
        {
          hKey = 0;
          v32 = 0;
          v33 = 0;
          v14 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, v35, 0, 0x20006u, dwOptions);
          Token = v14;
          if ( v14 )
          {
            if ( v14 > 0 )
              Token = (unsigned __int16)v14 | 0x80070000;
            goto LABEL_92;
          }
          v15 = RegDeleteValueW(hKey, ValueName);
          Token = v15;
          if ( (v15 & 0xFFFFFFFD) != 0 )
          {
            if ( v15 > 0 )
              Token = (unsigned __int16)v15 | 0x80070000;
LABEL_92:
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_32:
            ATL::CRegKey::Close((ATL::CRegKey *)v34);
            goto LABEL_33;
          }
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
        }
        v16 = ATL::CRegParser::SkipAssignment(this, a2);
LABEL_31:
        Token = v16;
        if ( v16 < 0 )
          goto LABEL_32;
      }
    }
    else
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_92;
      Token = ATL::CRegParser::SkipAssignment(this, a2);
      if ( Token < 0 )
        goto LABEL_92;
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_47:
      v13 = v30;
LABEL_48:
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
            goto LABEL_32;
          goto LABEL_53;
        }
      }
    }
  }
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
  ATL::CRegKey::Close((ATL::CRegKey *)v34);
LABEL_85:
  Token = -2147352567;
LABEL_33:
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v40);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x18000a980  push    rbp
0x18000a982  push    rbx
0x18000a983  push    rsi
0x18000a984  push    rdi
0x18000a985  push    r12
0x18000a987  push    r13
0x18000a989  push    r14
0x18000a98b  push    r15
0x18000a98d  sub     rsp, 2D8h
0x18000a994  lea     rbp, [rsp+50h]
0x18000a999  mov     rax, cs:__security_cookie
0x18000a9a0  xor     rax, rbp
0x18000a9a3  mov     [rbp+2C0h+var_50], rax
0x18000a9aa  mov     [rbp+2C0h+var_2C0], r9d
0x18000a9ae  mov     [rbp+2C0h+var_288], r8
0x18000a9b2  mov     rdi, rdx
0x18000a9b5  mov     rsi, rcx
0x18000a9b8  xor     r14d, r14d
0x18000a9bb  mov     [rbp+2C0h+var_268], r14
0x18000a9bf  mov     r15d, r14d
0x18000a9c2  mov     [rbp+2C0h+var_2A0], r14
0x18000a9c6  mov     [rbp+2C0h+var_298], r14
0x18000a9ca  mov     [rbp+2C0h+var_290], r14
0x18000a9ce  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a9d3  mov     ebx, eax
0x18000a9d5  test    eax, eax
0x18000a9d7  jns     short loc_18000A9E8
0x18000a9d9  lea     rcx, [rbp+2C0h+var_2A0]; this
0x18000a9dd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000a9e2  nop
0x18000a9e3  jmp     loc_18000AC2A
0x18000a9e8  mov     r13, r14
0x18000a9eb  mov     [rbp+2C0h+var_280], 1
0x18000a9f2  mov     r12d, [rbp+2C0h+arg_20]
0x18000a9f9  mov     [rbp+2C0h+var_278], r12d
0x18000a9fd  cmp     word ptr [rdi], 7Dh ; '}'
0x18000aa01  jz      loc_18000AC20
0x18000aa07  lea     rdx, String2; "Delete"
0x18000aa0e  mov     rcx, rdi; lpString1
0x18000aa11  call    cs:__imp_lstrcmpiW
0x18000aa17  mov     r14d, eax
0x18000aa1a  lea     rdx, aForceremove; "ForceRemove"
0x18000aa21  mov     rcx, rdi; lpString1
0x18000aa24  call    cs:__imp_lstrcmpiW
0x18000aa2a  xor     ebx, ebx
0x18000aa2c  test    eax, eax
0x18000aa2e  jz      short loc_18000AA39
0x18000aa30  test    r14d, r14d
0x18000aa33  jnz     loc_18000AAE7
0x18000aa39  mov     rdx, rdi; unsigned __int16 *
0x18000aa3c  mov     rcx, rsi; this
0x18000aa3f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000aa44  mov     ebx, eax
0x18000aa46  test    eax, eax
0x18000aa48  js      loc_18000AC20
0x18000aa4e  xor     ebx, ebx
0x18000aa50  cmp     [rbp+2C0h+var_2C0], ebx
0x18000aa53  jz      loc_18000AAE7
0x18000aa59  mov     [rbp+2C0h+hKey], rbx
0x18000aa5d  mov     [rbp+2C0h+var_2B0], rbx
0x18000aa61  mov     [rbp+2C0h+var_2A8], rbx
0x18000aa65  lea     edx, [rbx+5Ch]; unsigned __int16
0x18000aa68  mov     rcx, rdi; lpsz
0x18000aa6b  call    ?StrChrW@CRegParser@ATL@@KAPEBGPEBGG@Z; ATL::CRegParser::StrChrW(ushort const *,ushort)
0x18000aa70  test    rax, rax
0x18000aa73  jnz     loc_18000AFDC
0x18000aa79  mov     rdx, rdi; unsigned __int16 *
0x18000aa7c  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18000aa81  test    eax, eax
0x18000aa83  jz      short loc_18000AA9D
0x18000aa85  mov     rax, [rbp+2C0h+var_288]
0x18000aa89  mov     [rbp+2C0h+hKey], rax
0x18000aa8d  mov     rdx, rdi; unsigned __int16 *
0x18000aa90  lea     rcx, [rbp+2C0h+hKey]; this
0x18000aa94  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000aa99  mov     [rbp+2C0h+hKey], rbx
0x18000aa9d  test    r14d, r14d
0x18000aaa0  jnz     short loc_18000AADD
0x18000aaa2  mov     rdx, rdi; unsigned __int16 *
0x18000aaa5  mov     rcx, rsi; this
0x18000aaa8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000aaad  mov     ebx, eax
0x18000aaaf  test    eax, eax
0x18000aab1  js      loc_18000AFCD
0x18000aab7  mov     rdx, rdi; unsigned __int16 *
0x18000aaba  mov     rcx, rsi; this
0x18000aabd  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000aac2  mov     ebx, eax
0x18000aac4  test    eax, eax
0x18000aac6  js      loc_18000AFBE
0x18000aacc  lea     rcx, [rbp+2C0h+hKey]; this
0x18000aad0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000aad5  nop
0x18000aad6  xor     ecx, ecx
0x18000aad8  jmp     loc_18000AD8A
0x18000aadd  lea     rcx, [rbp+2C0h+hKey]; this
0x18000aae1  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000aae6  nop
0x18000aae7  lea     rdx, aNoremove; "NoRemove"
0x18000aaee  mov     rcx, rdi; lpString1
0x18000aaf1  call    cs:__imp_lstrcmpiW
0x18000aaf7  test    eax, eax
0x18000aaf9  jnz     short loc_18000AB15
0x18000aafb  mov     [rbp+2C0h+var_280], ebx
0x18000aafe  mov     rdx, rdi; unsigned __int16 *
0x18000ab01  mov     rcx, rsi; this
0x18000ab04  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000ab09  mov     ebx, eax
0x18000ab0b  test    eax, eax
0x18000ab0d  js      loc_18000AC20
0x18000ab13  xor     ebx, ebx
0x18000ab15  lea     rdx, aVal; "Val"
0x18000ab1c  mov     rcx, rdi; lpString1
0x18000ab1f  call    cs:__imp_lstrcmpiW
0x18000ab25  test    eax, eax
0x18000ab27  jnz     loc_18000AC58
0x18000ab2d  lea     rdx, [rbp+2C0h+ValueName]; unsigned __int16 *
0x18000ab31  mov     rcx, rsi; this
0x18000ab34  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000ab39  mov     ebx, eax
0x18000ab3b  test    eax, eax
0x18000ab3d  js      loc_18000AC20
0x18000ab43  mov     rdx, rdi; unsigned __int16 *
0x18000ab46  mov     rcx, rsi; this
0x18000ab49  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000ab4e  mov     ebx, eax
0x18000ab50  xor     ecx, ecx
0x18000ab52  test    eax, eax
0x18000ab54  js      loc_18000AC20
0x18000ab5a  cmp     word ptr [rdi], 3Dh ; '='
0x18000ab5e  jnz     loc_18000B049
0x18000ab64  mov     r14d, [rbp+2C0h+var_2C0]
0x18000ab68  test    r14d, r14d
0x18000ab6b  jz      short loc_18000ABB5
0x18000ab6d  mov     [rbp+2C0h+var_2B0], rcx
0x18000ab71  mov     [rbp+2C0h+var_2A8], rcx
0x18000ab75  mov     rax, [rbp+2C0h+var_288]
0x18000ab79  mov     [rbp+2C0h+hKey], rax
0x18000ab7d  mov     byte ptr [rsp+310h+dwOptions], cl; bool
0x18000ab81  mov     r9, rdi; unsigned __int16 *
0x18000ab84  lea     r8, [rbp+2C0h+ValueName]; unsigned __int16 *
0x18000ab88  lea     rdx, [rbp+2C0h+hKey]; struct ATL::CRegKey *
0x18000ab8c  mov     rcx, rsi; this
0x18000ab8f  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x18000ab94  mov     ebx, eax
0x18000ab96  xor     eax, eax
0x18000ab98  mov     [rbp+2C0h+hKey], rax
0x18000ab9c  test    ebx, ebx
0x18000ab9e  js      loc_18000AFFA
0x18000aba4  lea     rcx, [rbp+2C0h+hKey]; this
0x18000aba8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000abad  nop
0x18000abae  xor     ecx, ecx
0x18000abb0  jmp     loc_18000AD8E
0x18000abb5  test    r12d, r12d
0x18000abb8  jnz     short loc_18000AC0B
0x18000abba  mov     [rbp+2C0h+hKey], rcx
0x18000abbe  mov     [rbp+2C0h+var_2B0], rcx
0x18000abc2  mov     [rbp+2C0h+var_2A8], rcx
0x18000abc6  mov     r9d, 20006h; unsigned int
0x18000abcc  xor     r8d, r8d; lpSubKey
0x18000abcf  mov     rdx, [rbp+2C0h+var_288]; hKey
0x18000abd3  lea     rcx, [rbp+2C0h+hKey]; this
0x18000abd7  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x18000abdc  mov     ebx, eax
0x18000abde  test    eax, eax
0x18000abe0  jnz     loc_18000B02F
0x18000abe6  lea     rdx, [rbp+2C0h+ValueName]; lpValueName
0x18000abea  mov     rcx, [rbp+2C0h+hKey]; hKey
0x18000abee  call    cs:__imp_RegDeleteValueW
0x18000abf4  mov     ebx, eax
0x18000abf6  test    eax, 0FFFFFFFDh
0x18000abfb  jnz     loc_18000B013
0x18000ac01  lea     rcx, [rbp+2C0h+hKey]; this
0x18000ac05  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ac0a  nop
0x18000ac0b  mov     rdx, rdi; unsigned __int16 *
0x18000ac0e  mov     rcx, rsi; this
0x18000ac11  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000ac16  mov     ebx, eax
0x18000ac18  test    eax, eax
0x18000ac1a  jns     loc_18000A9FD
0x18000ac20  lea     rcx, [rbp+2C0h+var_2A0]; this
0x18000ac24  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ac29  nop
0x18000ac2a  lea     rcx, [rbp+2C0h+var_268]
0x18000ac2e  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x18000ac33  mov     eax, ebx
0x18000ac35  mov     rcx, [rbp+2C0h+var_50]
0x18000ac3c  xor     rcx, rbp; StackCookie
0x18000ac3f  call    __security_check_cookie
0x18000ac44  lea     rsp, [rbp+288h]
0x18000ac4b  pop     r15
0x18000ac4d  pop     r14
0x18000ac4f  pop     r13
0x18000ac51  pop     r12
0x18000ac53  pop     rdi
0x18000ac54  pop     rsi
0x18000ac55  pop     rbx
0x18000ac56  pop     rbp
0x18000ac57  retn
0x18000ac58  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000ac5d  mov     rcx, rdi; lpsz
0x18000ac60  call    ?StrChrW@CRegParser@ATL@@KAPEBGPEBGG@Z; ATL::CRegParser::StrChrW(ushort const *,ushort)
0x18000ac65  test    rax, rax
0x18000ac68  jnz     loc_18000B078
0x18000ac6e  cmp     [rbp+2C0h+var_2C0], ebx
0x18000ac71  jz      loc_18000ADDE
0x18000ac77  mov     r9d, 0F003Fh; unsigned int
0x18000ac7d  mov     r8, rdi; lpSubKey
0x18000ac80  mov     rbx, [rbp+2C0h+var_288]
0x18000ac84  mov     rdx, rbx; hKey
0x18000ac87  lea     rcx, [rbp+2C0h+var_2A0]; this
0x18000ac8b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x18000ac90  xor     r14d, r14d
0x18000ac93  test    eax, eax
0x18000ac95  jz      short loc_18000AD16
0x18000ac97  mov     r9d, 20019h; unsigned int
0x18000ac9d  mov     r8, rdi; lpSubKey
0x18000aca0  mov     rdx, rbx; hKey
0x18000aca3  lea     rcx, [rbp+2C0h+var_2A0]; this
0x18000aca7  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x18000acac  test    eax, eax
0x18000acae  jz      short loc_18000AD16
0x18000acb0  mov     [rbp+2C0h+dwDisposition], r14d
0x18000acb4  mov     [rbp+2C0h+var_270], r14
0x18000acb8  lea     rax, [rbp+2C0h+dwDisposition]
0x18000acbc  mov     [rsp+310h+lpdwDisposition], rax; lpdwDisposition
0x18000acc1  lea     rax, [rbp+2C0h+var_270]
0x18000acc5  mov     [rsp+310h+phkResult], rax; phkResult
0x18000acca  mov     [rsp+310h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000accf  mov     [rsp+310h+samDesired], 2001Fh; samDesired
0x18000acd7  mov     [rsp+310h+dwOptions], r14d; dwOptions
0x18000acdc  xor     r9d, r9d; lpClass
0x18000acdf  xor     r8d, r8d; Reserved
0x18000ace2  mov     rdx, rdi; lpSubKey
0x18000ace5  mov     rcx, rbx; hKey
0x18000ace8  call    cs:__imp_RegCreateKeyExW
0x18000acee  test    eax, eax
0x18000acf0  jnz     short loc_18000AD07
0x18000acf2  lea     rcx, [rbp+2C0h+var_2A0]; this
0x18000acf6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000acfb  mov     r15, [rbp+2C0h+var_270]
0x18000acff  mov     [rbp+2C0h+var_2A0], r15
0x18000ad03  test    eax, eax
0x18000ad05  jz      short loc_18000AD1A
0x18000ad07  lea     rcx, [rbp+2C0h+var_2A0]; this
0x18000ad0b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ad10  nop
0x18000ad11  jmp     loc_18000AFF0
0x18000ad16  mov     r15, [rbp+2C0h+var_2A0]
0x18000ad1a  movzx   eax, word ptr [rdi]
0x18000ad1d  sub     ax, 4Ch ; 'L'
0x18000ad21  mov     ecx, 0FFDFh
0x18000ad26  test    cx, ax
0x18000ad29  jnz     short loc_18000AD4A
0x18000ad2b  lea     rdx, aLocalserver32; "LocalServer32"
0x18000ad32  mov     rcx, rdi; lpString1
0x18000ad35  call    cs:__imp_lstrcmpiW
0x18000ad3b  movzx   r14d, r14b
0x18000ad3f  test    eax, eax
0x18000ad41  mov     eax, 1
0x18000ad46  cmovz   r14d, eax
0x18000ad4a  mov     rdx, rdi; unsigned __int16 *
0x18000ad4d  mov     rcx, rsi; this
0x18000ad50  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000ad55  mov     ebx, eax
0x18000ad57  xor     ecx, ecx
0x18000ad59  test    eax, eax
0x18000ad5b  js      loc_18000AC20
0x18000ad61  cmp     word ptr [rdi], 3Dh ; '='
0x18000ad65  jnz     short loc_18000AD8A
0x18000ad67  mov     byte ptr [rsp+310h+dwOptions], r14b; bool
0x18000ad6c  mov     r9, rdi; unsigned __int16 *
0x18000ad6f  xor     r8d, r8d; unsigned __int16 *
0x18000ad72  lea     rdx, [rbp+2C0h+var_2A0]; struct ATL::CRegKey *
0x18000ad76  mov     rcx, rsi; this
0x18000ad79  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x18000ad7e  mov     ebx, eax
0x18000ad80  xor     ecx, ecx
0x18000ad82  test    eax, eax
0x18000ad84  js      loc_18000AC20
0x18000ad8a  mov     r14d, [rbp+2C0h+var_2C0]
0x18000ad8e  cmp     word ptr [rdi], 7Bh ; '{'
0x18000ad92  jnz     loc_18000A9FD
0x18000ad98  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ad9c  inc     rax
0x18000ad9f  cmp     [rdi+rax*2], cx
0x18000ada3  jnz     short loc_18000AD9C
0x18000ada5  cmp     rax, 1
0x18000ada9  jnz     loc_18000A9FD
0x18000adaf  mov     [rsp+310h+dwOptions], ecx; unsigned int
0x18000adb3  mov     r9d, r14d; int
0x18000adb6  mov     r8, r15; HKEY
0x18000adb9  mov     rdx, rdi; unsigned __int16 *
0x18000adbc  mov     rcx, rsi; this
0x18000adbf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000adc4  mov     ebx, eax
0x18000adc6  test    eax, eax
0x18000adc8  js      loc_18000AC20
  ... truncated ...
```
