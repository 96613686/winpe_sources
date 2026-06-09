# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)

- ea: `0x1800109fc`
- end: `0x180010e09`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z`
- size: `1037`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, struct ATL::CRegKey *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180012874`

## callees

- `0x180004640`
- `0x1800054bc`
- `0x180006b08`
- `0x18000e83c`
- `0x18000f204`
- `0x18000f9d8`
- `0x18000fa64`
- `0x18000faf8`
- `0x1800109fc`
- `0x180010e10`
- `0x1800135bc`
- `0x180013b08`
- `0x1800eeda0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010a6a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010a85`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010aa9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010ad5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010c59`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010c62`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010c8a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010db0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010dcf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010dd8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010a6a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010a85`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010aa9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010ad5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010c59`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010c62`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010c8a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010db0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010dcf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010dd8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010a48`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010a98`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010c77`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010a48`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010a98`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010c77`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180010d0e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180010d1f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180010d34`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180010d55`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180010d0e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180010d1f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180010d34`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180010d55`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180010b0b`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180010b0b`
- `KERNEL32!lstrcpynW` at `0x180010cf9`
- `KERNEL32!lstrcpynW` at `0x180010cf9`
- `USER32!CharPrevW` at `0x180010cd8`
- `USER32!CharPrevW` at `0x180010cd8`
- `ADVAPI32!RegSetValueExW` at `0x180010b37`
- `ADVAPI32!RegSetValueExW` at `0x180010c1d`
- `ADVAPI32!RegSetValueExW` at `0x180010d9f`
- `ADVAPI32!RegSetValueExW` at `0x180010b37`
- `ADVAPI32!RegSetValueExW` at `0x180010c1d`
- `ADVAPI32!RegSetValueExW` at `0x180010d9f`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegObject **this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        bool a5)
{
  const WCHAR *v6; // r12
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rsi
  int Token; // ebx
  unsigned __int16 *v11; // rcx
  unsigned __int16 *v12; // rdi
  unsigned __int16 *v13; // rcx
  HKEY v14; // rcx
  __int64 v15; // rbx
  unsigned __int64 v16; // rdx
  unsigned __int64 cbData; // r12
  __int64 v18; // rax
  void *v19; // rsp
  BYTE *lpData; // r15
  int i; // r9d
  unsigned __int8 v22; // al
  int v23; // r9d
  char v24; // dl
  __int64 v25; // r8
  __int64 v26; // rbx
  const BYTE *v27; // r15
  WCHAR *v28; // r14
  __int64 v29; // rax
  ATL::CRegObject *v30; // rcx
  const WCHAR *v31; // rax
  const WCHAR *v32; // r12
  unsigned __int16 *v33; // rax
  unsigned __int16 *v34; // r15
  __int64 v35; // rax
  BYTE Data[8]; // [rsp+30h] [rbp+0h] BYREF
  ULONG pulOut; // [rsp+38h] [rbp+8h] BYREF
  LPCWSTR lpValueName; // [rsp+40h] [rbp+10h]
  HKEY *v40; // [rsp+48h] [rbp+18h]
  unsigned __int16 *v41; // [rsp+50h] [rbp+20h]
  __int64 v42; // [rsp+58h] [rbp+28h] BYREF

  v41 = a4;
  lpValueName = a3;
  v40 = a2;
  v42 = 0;
  v6 = a3;
  *(_WORD *)Data = 0;
  v8 = (unsigned __int16 *)malloc(0x2000u);
  v9 = v8;
  if ( !v8 )
    goto LABEL_8;
  Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, v8);
  v11 = v9;
  if ( Token >= 0 )
  {
    if ( !(unsigned int)ATL::CRegParser::VTFromRegType(v9, (unsigned __int16 *)Data) )
    {
      free(v9);
      Token = -2147352567;
      goto LABEL_50;
    }
    v12 = (unsigned __int16 *)malloc(0x2000u);
    if ( !v12 )
      goto LABEL_7;
    ATL::CRegParser::SkipWhiteSpace((ATL::CRegParser *)this);
    Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, v12);
    if ( Token < 0 )
    {
      v13 = v12;
LABEL_11:
      free(v13);
      v11 = v9;
      goto LABEL_3;
    }
    pulOut = 0;
    if ( *(unsigned __int16 *)Data != 8 )
    {
      if ( *(unsigned __int16 *)Data != 17 )
      {
        if ( *(unsigned __int16 *)Data == 19 )
        {
          VarUI4FromStr(v12, 0, 0, &pulOut);
          v14 = *a2;
          *(_DWORD *)Data = pulOut;
          RegSetValueExW(v14, v6, 0, 4u, Data, 4u);
        }
        goto LABEL_48;
      }
      v15 = -1;
      do
        ++v15;
      while ( v12[v15] );
      if ( (v15 & 1) == 0 )
      {
        v16 = (unsigned int)((int)v15 >> 31);
        cbData = (int)v15 / 2;
        if ( cbData <= 0x400
          && (LODWORD(v16) = (int)v15 % 2,
              ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)((int)v15 / 2), v16)) )
        {
          v18 = cbData + 15;
          if ( cbData + 15 < cbData )
            v18 = 0xFFFFFFFFFFFFFF0LL;
          v19 = alloca(v18 & 0xFFFFFFFFFFFFFFF0uLL);
          lpData = Data;
        }
        else
        {
          lpData = (BYTE *)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(
                             &v42,
                             cbData);
        }
        if ( lpData )
        {
          memset_0(lpData, 0, cbData);
          for ( i = 0; i < (int)v15; lpData[v25] |= v22 << (4 - 4 * v24) )
          {
            v22 = ATL::CRegParser::ChToByte(v12[i]);
            v24 = v23 & 1;
            i = v23 + 1;
          }
          RegSetValueExW(*a2, lpValueName, 0, 3u, lpData, cbData);
          goto LABEL_48;
        }
      }
LABEL_33:
      free(v12);
      free(v9);
      Token = -2147467259;
      goto LABEL_50;
    }
    v26 = -1;
    v27 = (const BYTE *)v12;
    v28 = 0;
    if ( a5 )
    {
      v29 = -1;
      do
        ++v29;
      while ( v12[v29] );
      if ( (int)v29 > 4094 )
        goto LABEL_33;
      v28 = (WCHAR *)malloc(0x2000u);
      if ( !v28 )
      {
        free(v12);
LABEL_7:
        free(v9);
LABEL_8:
        Token = -2147024882;
        goto LABEL_50;
      }
      v30 = this[1];
      *(_QWORD *)Data = 0;
      v31 = ATL::CRegObject::StrFromMap(v30, L"Module");
      v32 = v31;
      if ( v31 )
      {
        v33 = (unsigned __int16 *)ATL::CRegParser::StrStrW(v12, v31);
        v34 = v33;
        if ( v33 && (v33 == v41 || *CharPrevW(v12, v33) != 34) )
        {
          *v28 = 0;
          lstrcpynW(v28, v12, v34 - v12);
          _o_wcscat_s(v28, 4096, L"\"");
          _o_wcscat_s(v28, 4096, v32);
          _o_wcscat_s(v28, 4096, L"\"");
          v35 = -1;
          do
            ++v35;
          while ( v32[v35] );
          _o_wcscat_s(v28, 4096, &v34[v35]);
          v27 = (const BYTE *)v28;
        }
        else
        {
          v27 = (const BYTE *)v12;
        }
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(Data);
      v6 = lpValueName;
    }
    do
      ++v26;
    while ( *(_WORD *)&v27[2 * v26] );
    RegSetValueExW(*v40, v6, 0, 1u, v27, 2 * v26 + 2);
    if ( v28 )
      free(v28);
LABEL_48:
    Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, v41);
    v13 = v12;
    if ( Token >= 0 )
    {
      free(v12);
      free(v9);
      Token = 0;
      goto LABEL_50;
    }
    goto LABEL_11;
  }
LABEL_3:
  free(v11);
LABEL_50:
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v42);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x1800109fc  push    rbp
0x1800109fe  push    rbx
0x1800109ff  push    rsi
0x180010a00  push    rdi
0x180010a01  push    r12
0x180010a03  push    r13
0x180010a05  push    r14
0x180010a07  push    r15
0x180010a09  sub     rsp, 78h
0x180010a0d  lea     rbp, [rsp+30h]
0x180010a12  mov     rax, cs:__security_cookie
0x180010a19  xor     rax, rbp
0x180010a1c  mov     [rbp+80h+var_50], rax
0x180010a20  mov     r13, rcx
0x180010a23  mov     [rbp+80h+var_60], r9
0x180010a27  xor     r15d, r15d
0x180010a2a  mov     [rbp+80h+lpValueName], r8
0x180010a2e  mov     edi, 2000h
0x180010a33  mov     [rbp+80h+var_68], rdx
0x180010a37  mov     ecx, edi; Size
0x180010a39  mov     [rbp+80h+var_58], r15
0x180010a3d  mov     r12, r8
0x180010a40  mov     word ptr [rbp+80h+Data], r15w
0x180010a45  mov     r14, rdx
0x180010a48  call    cs:__imp_malloc
0x180010a4e  mov     rsi, rax
0x180010a51  test    rax, rax
0x180010a54  jz      short loc_180010AAF
0x180010a56  mov     rdx, rax; unsigned __int16 *
0x180010a59  mov     rcx, r13; this
0x180010a5c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180010a61  mov     ebx, eax
0x180010a63  mov     rcx, rsi; lpString1
0x180010a66  test    eax, eax
0x180010a68  jns     short loc_180010A75
0x180010a6a  call    cs:__imp_free
0x180010a70  jmp     loc_180010DE1
0x180010a75  lea     rdx, [rbp+80h+Data]; unsigned __int16 *
0x180010a79  call    ?VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z; ATL::CRegParser::VTFromRegType(ushort const *,ushort &)
0x180010a7e  test    eax, eax
0x180010a80  jnz     short loc_180010A95
0x180010a82  mov     rcx, rsi; Block
0x180010a85  call    cs:__imp_free
0x180010a8b  mov     ebx, 80020009h
0x180010a90  jmp     loc_180010DE1
0x180010a95  mov     rcx, rdi; Size
0x180010a98  call    cs:__imp_malloc
0x180010a9e  mov     rdi, rax
0x180010aa1  test    rax, rax
0x180010aa4  jnz     short loc_180010AB9
0x180010aa6  mov     rcx, rsi; Block
0x180010aa9  call    cs:__imp_free
0x180010aaf  mov     ebx, 8007000Eh
0x180010ab4  jmp     loc_180010DE1
0x180010ab9  mov     rcx, r13; this
0x180010abc  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180010ac1  mov     rdx, rdi; unsigned __int16 *
0x180010ac4  mov     rcx, r13; this
0x180010ac7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180010acc  mov     ebx, eax
0x180010ace  test    eax, eax
0x180010ad0  jns     short loc_180010AE0
0x180010ad2  mov     rcx, rdi; Block
0x180010ad5  call    cs:__imp_free
0x180010adb  mov     rcx, rsi
0x180010ade  jmp     short loc_180010A6A
0x180010ae0  movzx   eax, word ptr [rbp+80h+Data]
0x180010ae4  mov     [rbp+80h+pulOut], r15d
0x180010ae8  cmp     eax, 8
0x180010aeb  jz      loc_180010C2B
0x180010af1  cmp     eax, 11h
0x180010af4  jz      short loc_180010B42
0x180010af6  cmp     eax, 13h
0x180010af9  jnz     loc_180010DB6
0x180010aff  lea     r9, [rbp+80h+pulOut]; pulOut
0x180010b03  xor     r8d, r8d; dwFlags
0x180010b06  xor     edx, edx; lcid
0x180010b08  mov     rcx, rdi; strIn
0x180010b0b  call    cs:__imp_VarUI4FromStr
0x180010b11  mov     eax, [rbp+80h+pulOut]
0x180010b14  mov     r9d, 4; dwType
0x180010b1a  mov     rcx, [r14]; hKey
0x180010b1d  xor     r8d, r8d; Reserved
0x180010b20  mov     dword ptr [rbp+80h+Data], eax
0x180010b23  mov     rdx, r12; lpValueName
0x180010b26  lea     rax, [rbp+80h+Data]
0x180010b2a  mov     [rsp+0B0h+cbData], 4; cbData
0x180010b32  mov     [rsp+0B0h+lpData], rax; lpData
0x180010b37  call    cs:__imp_RegSetValueExW
0x180010b3d  jmp     loc_180010DB6
0x180010b42  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180010b46  inc     rbx
0x180010b49  cmp     [rdi+rbx*2], r15w
0x180010b4e  jnz     short loc_180010B46
0x180010b50  test    bl, 1
0x180010b53  jnz     loc_180010C56
0x180010b59  mov     eax, ebx
0x180010b5b  mov     ecx, 2
0x180010b60  cdq; unsigned __int64
0x180010b61  idiv    ecx
0x180010b63  movsxd  r12, eax
0x180010b66  cmp     r12, 400h
0x180010b6d  ja      short loc_180010BA2
0x180010b6f  mov     rcx, r12; this
0x180010b72  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180010b77  test    al, al
0x180010b79  jz      short loc_180010BA2
0x180010b7b  lea     rax, [r12+0Fh]
0x180010b80  cmp     rax, r12
0x180010b83  ja      short loc_180010B8F
0x180010b85  mov     rax, 0FFFFFFFFFFFFFF0h
0x180010b8f  and     rax, 0FFFFFFFFFFFFFFF0h
0x180010b93  call    _alloca_probe
0x180010b98  sub     rsp, rax
0x180010b9b  lea     r15, [rsp+0B0h+Data]
0x180010ba0  jmp     short loc_180010BB1
0x180010ba2  mov     rdx, r12
0x180010ba5  lea     rcx, [rbp+80h+var_58]
0x180010ba9  call    ?Allocate@?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAAPEAX_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(unsigned __int64)
0x180010bae  mov     r15, rax
0x180010bb1  test    r15, r15
0x180010bb4  jz      loc_180010C56
0x180010bba  mov     r8, r12; Size
0x180010bbd  xor     edx, edx; Val
0x180010bbf  mov     rcx, r15; void *
0x180010bc2  call    memset_0
0x180010bc7  xor     eax, eax
0x180010bc9  mov     r9d, eax
0x180010bcc  test    ebx, ebx
0x180010bce  jle     short loc_180010C00
0x180010bd0  mov     ecx, r9d
0x180010bd3  mov     r8d, r9d
0x180010bd6  shr     r8, 1
0x180010bd9  movzx   ecx, word ptr [rdi+rcx*2]; unsigned __int16
0x180010bdd  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x180010be2  mov     edx, r9d
0x180010be5  mov     ecx, 4
0x180010bea  and     edx, 1
0x180010bed  inc     r9d
0x180010bf0  shl     edx, 2
0x180010bf3  sub     ecx, edx
0x180010bf5  shl     al, cl
0x180010bf7  or      [r8+r15], al
0x180010bfb  cmp     r9d, ebx
0x180010bfe  jl      short loc_180010BD0
0x180010c00  mov     rdx, [rbp+80h+lpValueName]; lpValueName
0x180010c04  mov     rcx, r14
0x180010c07  mov     [rsp+0B0h+cbData], r12d; cbData
0x180010c0c  mov     r9d, 3; dwType
0x180010c12  xor     r8d, r8d; Reserved
0x180010c15  mov     [rsp+0B0h+lpData], r15; lpData
0x180010c1a  mov     rcx, [rcx]; hKey
0x180010c1d  call    cs:__imp_RegSetValueExW
0x180010c23  xor     r15d, r15d
0x180010c26  jmp     loc_180010DB6
0x180010c2b  xor     ecx, ecx
0x180010c2d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180010c31  mov     r15, rdi
0x180010c34  mov     r14d, ecx
0x180010c37  cmp     [rbp+80h+arg_20], cl
0x180010c3d  jz      loc_180010D72
0x180010c43  mov     rax, rbx
0x180010c46  inc     rax
0x180010c49  cmp     [rdi+rax*2], cx
0x180010c4d  jnz     short loc_180010C46
0x180010c4f  cmp     eax, 0FFEh
0x180010c54  jle     short loc_180010C72
0x180010c56  mov     rcx, rdi; Block
0x180010c59  call    cs:__imp_free
0x180010c5f  mov     rcx, rsi; Block
0x180010c62  call    cs:__imp_free
0x180010c68  mov     ebx, 80004005h
0x180010c6d  jmp     loc_180010DE1
0x180010c72  mov     ecx, 2000h; Size
0x180010c77  call    cs:__imp_malloc
0x180010c7d  mov     r14, rax
0x180010c80  xor     eax, eax
0x180010c82  test    r14, r14
0x180010c85  jnz     short loc_180010C95
0x180010c87  mov     rcx, rdi; Block
0x180010c8a  call    cs:__imp_free
0x180010c90  jmp     loc_180010AA6
0x180010c95  mov     rcx, [r13+8]; this
0x180010c99  lea     rdx, aModule; "Module"
0x180010ca0  mov     qword ptr [rbp+80h+Data], rax
0x180010ca4  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x180010ca9  mov     r12, rax
0x180010cac  test    rax, rax
0x180010caf  jz      loc_180010D63
0x180010cb5  mov     rdx, rax; LPCWSTR
0x180010cb8  mov     rcx, rdi; lpsz
0x180010cbb  call    ?StrStrW@CRegParser@ATL@@KAPEBGPEBG0@Z; ATL::CRegParser::StrStrW(ushort const *,ushort const *)
0x180010cc0  mov     r15, rax
0x180010cc3  test    rax, rax
0x180010cc6  jz      loc_180010D60
0x180010ccc  cmp     rax, [rbp+80h+var_60]
0x180010cd0  jz      short loc_180010CE4
0x180010cd2  mov     rdx, rax; lpszCurrent
0x180010cd5  mov     rcx, rdi; lpszStart
0x180010cd8  call    cs:__imp_CharPrevW
0x180010cde  cmp     word ptr [rax], 22h ; '"'
0x180010ce2  jz      short loc_180010D60
0x180010ce4  xor     eax, eax
0x180010ce6  mov     r8, r15
0x180010ce9  sub     r8, rdi
0x180010cec  mov     [r14], ax
0x180010cf0  sar     r8, 1; iMaxLength
0x180010cf3  mov     rdx, rdi; lpString2
0x180010cf6  mov     rcx, r14; lpString1
0x180010cf9  call    cs:__imp_lstrcpynW
0x180010cff  lea     r8, asc_180155890; "\""
0x180010d06  mov     edx, 1000h
0x180010d0b  mov     rcx, r14
0x180010d0e  call    cs:__imp__o_wcscat_s
0x180010d14  mov     r8, r12
0x180010d17  mov     edx, 1000h
0x180010d1c  mov     rcx, r14
0x180010d1f  call    cs:__imp__o_wcscat_s
0x180010d25  lea     r8, asc_180155890; "\""
0x180010d2c  mov     edx, 1000h
0x180010d31  mov     rcx, r14
0x180010d34  call    cs:__imp__o_wcscat_s
0x180010d3a  mov     rax, rbx
0x180010d3d  xor     ecx, ecx
0x180010d3f  inc     rax
0x180010d42  cmp     [r12+rax*2], cx
0x180010d47  jnz     short loc_180010D3F
0x180010d49  lea     r8, [r15+rax*2]
0x180010d4d  mov     edx, 1000h
0x180010d52  mov     rcx, r14
0x180010d55  call    cs:__imp__o_wcscat_s
0x180010d5b  mov     r15, r14
0x180010d5e  jmp     short loc_180010D63
0x180010d60  mov     r15, rdi
0x180010d63  lea     rcx, [rbp+80h+Data]
0x180010d67  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180010d6c  mov     r12, [rbp+80h+lpValueName]
0x180010d70  xor     ecx, ecx
0x180010d72  inc     rbx
0x180010d75  cmp     [r15+rbx*2], cx
0x180010d7a  jnz     short loc_180010D72
0x180010d7c  mov     rcx, [rbp+80h+var_68]
0x180010d80  lea     eax, ds:2[rbx*2]
0x180010d87  mov     [rsp+0B0h+cbData], eax; cbData
0x180010d8b  mov     r9d, 1; dwType
0x180010d91  xor     r8d, r8d; Reserved
0x180010d94  mov     [rsp+0B0h+lpData], r15; lpData
0x180010d99  mov     rdx, r12; lpValueName
0x180010d9c  mov     rcx, [rcx]; hKey
0x180010d9f  call    cs:__imp_RegSetValueExW
0x180010da5  xor     r15d, r15d
0x180010da8  test    r14, r14
0x180010dab  jz      short loc_180010DB6
0x180010dad  mov     rcx, r14; Block
0x180010db0  call    cs:__imp_free
0x180010db6  mov     rdx, [rbp+80h+var_60]; unsigned __int16 *
0x180010dba  mov     rcx, r13; this
0x180010dbd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180010dc2  mov     ebx, eax
0x180010dc4  mov     rcx, rdi; Block
0x180010dc7  test    eax, eax
0x180010dc9  js      loc_180010AD5
0x180010dcf  call    cs:__imp_free
0x180010dd5  mov     rcx, rsi; Block
0x180010dd8  call    cs:__imp_free
0x180010dde  mov     ebx, r15d
0x180010de1  lea     rcx, [rbp+80h+var_58]
0x180010de5  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180010dea  mov     eax, ebx
0x180010dec  mov     rcx, [rbp+80h+var_50]
0x180010df0  xor     rcx, rbp; StackCookie
0x180010df3  call    __security_check_cookie
0x180010df8  lea     rsp, [rbp+48h]
0x180010dfc  pop     r15
0x180010dfe  pop     r14
0x180010e00  pop     r13
0x180010e02  pop     r12
0x180010e04  pop     rdi
0x180010e05  pop     rsi
0x180010e06  pop     rbx
0x180010e07  pop     rbp
0x180010e08  retn
```
