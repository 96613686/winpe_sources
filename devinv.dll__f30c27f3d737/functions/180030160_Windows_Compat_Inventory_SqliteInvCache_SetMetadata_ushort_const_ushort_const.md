# Windows::Compat::Inventory::SqliteInvCache::SetMetadata(ushort const *,ushort const *)

- ea: `0x180030160`
- end: `0x18003063d`
- name: `?SetMetadata@SqliteInvCache@Inventory@Compat@Windows@@UEAAJPEBG0@Z`
- size: `1245`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005e40`
- `0x18000fa50`
- `0x180013f20`
- `0x180016440`
- `0x180026308`
- `0x180030160`
- `0x180066c10`
- `0x18007ee44`
- `0x1800c9a2c`
- `0x1800e9be0`
- `0x1800ea520`
- `0x1800ec8f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030576`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030576`

## string_xrefs

- `0x1800301db`: `DELETE FROM `
- `0x1800303a0`: `REPLACE INTO `
- `0x1800302a9`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x180030335`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x180030366`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x18003046e`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x1800304f3`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x1800305bf`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x1800305e7`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::SetMetadata(
        Windows::Compat::Inventory::SqliteInvCache *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v3; // r12d
  int v4; // r14d
  _QWORD *v6; // rax
  __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  __int128 *v10; // rdx
  int v11; // eax
  int v12; // edi
  unsigned int v13; // ebx
  const char *v14; // rax
  __int64 v15; // rsi
  int v16; // eax
  int v17; // r14d
  const char *v18; // rax
  __int64 v19; // rax
  __int128 *v20; // rdx
  int v21; // eax
  int v22; // edi
  const char *v23; // rax
  int v24; // eax
  int v25; // r14d
  const char *v26; // rax
  __int64 v27; // r8
  int v28; // eax
  int i; // r12d
  int v30; // r14d
  const char *v31; // rax
  __int64 v33; // [rsp+40h] [rbp-29h] BYREF
  __int128 v34; // [rsp+48h] [rbp-21h] BYREF
  __int128 v35; // [rsp+58h] [rbp-11h]
  _BYTE Src[32]; // [rsp+68h] [rbp-1h] BYREF

  v3 = (int)a3;
  v4 = (int)a2;
  v33 = 0;
  v6 = (_QWORD *)((char *)this + 104);
  v7 = *((_QWORD *)this + 15);
  v8 = 0x7FFFFFFFFFFFFFFELL - v7;
  if ( a3 )
  {
    if ( v8 < 0xD )
      std::_Xlen_string();
    if ( v6[3] > 7u )
      v6 = (_QWORD *)*v6;
    std::wstring::wstring(Src, v7, a3, L"REPLACE INTO ", 13, v6, v7);
    v19 = std::wstring::append(Src, L" (Name, Value) VALUES (?, ?);");
    v34 = 0;
    v35 = 0;
    v34 = *(_OWORD *)v19;
    v35 = *(_OWORD *)(v19 + 16);
    *(_QWORD *)(v19 + 16) = 0;
    *(_QWORD *)(v19 + 24) = 7;
    *(_WORD *)v19 = 0;
    std::wstring::~wstring(Src);
    v33 = 0;
    v20 = &v34;
    if ( *((_QWORD *)&v35 + 1) > 7u )
      LODWORD(v20) = v34;
    v21 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v20, -1, 128, (__int64)&v33, 0);
    v22 = v21;
    if ( v21 )
    {
      if ( v21 > 0 )
        v13 = (unsigned __int16)v21 | 0x80070000;
      else
        v13 = v21;
      v23 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
        1270,
        "sqlite3_prepare_v2 failed: [%d] %hs",
        v22,
        v23);
      goto LABEL_12;
    }
    v15 = v33;
    if ( v33 )
    {
      v24 = bindText(v33, 1, v4, -2, 0, 2);
      v25 = v24;
      if ( v24 )
      {
        if ( v24 > 0 )
          v13 = (unsigned __int16)v24 | 0x80070000;
        else
          v13 = v24;
        v26 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
        v27 = 1284;
      }
      else
      {
        v28 = bindText(v15, 2, v3, -2, 0, 2);
        v25 = v28;
        if ( !v28 )
          goto LABEL_43;
        if ( v28 > 0 )
          v13 = (unsigned __int16)v28 | 0x80070000;
        else
          v13 = v28;
        v26 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
        v27 = 1292;
      }
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
        v27,
        "sqlite3_bind_text16 failed: [%d] %hs",
        v25,
        v26);
    }
    else
    {
      v13 = -2147467259;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
        1276,
        "sqlite3_prepare_v2 returned a null statement [%#x]",
        -2147467259);
    }
LABEL_52:
    std::wstring::~wstring(&v34);
    goto LABEL_53;
  }
  if ( v8 < 0xC )
    std::_Xlen_string();
  if ( v6[3] > 7u )
    v6 = (_QWORD *)*v6;
  std::wstring::wstring(Src, v7, 0, L"DELETE FROM ", 12, v6, v7);
  v9 = std::wstring::append(Src, L" WHERE Name = ?;");
  v34 = 0;
  v35 = 0;
  v34 = *(_OWORD *)v9;
  v35 = *(_OWORD *)(v9 + 16);
  *(_QWORD *)(v9 + 16) = 0;
  *(_QWORD *)(v9 + 24) = 7;
  *(_WORD *)v9 = 0;
  std::wstring::~wstring(Src);
  v33 = 0;
  v10 = &v34;
  if ( *((_QWORD *)&v35 + 1) > 7u )
    LODWORD(v10) = v34;
  v11 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v10, -1, 128, (__int64)&v33, 0);
  v12 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v13 = (unsigned __int16)v11 | 0x80070000;
    else
      v13 = v11;
    v14 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1245,
      "sqlite3_prepare_v2 failed: [%d] %hs",
      v12,
      v14);
LABEL_12:
    std::wstring::~wstring(&v34);
    v15 = v33;
    goto LABEL_53;
  }
  v15 = v33;
  if ( !v33 )
  {
    v13 = -2147467259;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1251,
      "sqlite3_prepare_v2 returned a null statement [%#x]",
      -2147467259);
    goto LABEL_52;
  }
  v16 = bindText(v33, 1, v4, -2, 0, 2);
  v17 = v16;
  if ( v16 )
  {
    if ( v16 > 0 )
      v13 = (unsigned __int16)v16 | 0x80070000;
    else
      v13 = v16;
    v18 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1259,
      "sqlite3_bind_text16 failed: [%d] %hs",
      v17,
      v18);
    goto LABEL_52;
  }
LABEL_43:
  std::wstring::~wstring(&v34);
  v13 = 0;
  for ( i = 0; i < 100; ++i )
  {
    v30 = sqlite3_step(v15);
    if ( (unsigned int)(v30 - 5) > 1 )
      break;
    Sleep(5u);
  }
  if ( v30 != 101 )
  {
    if ( v30 > 0 )
      v13 = (unsigned __int16)v30 | 0x80070000;
    else
      v13 = v30;
    v31 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1301,
      "sqlite3_step failed: [%d] %hs",
      v30,
      v31);
  }
LABEL_53:
  if ( v15 )
    sqlite3_finalize(v15);
  return v13;
}

```

## disassembly

```asm
0x180030160  push    rbp
0x180030162  push    rbx
0x180030163  push    rsi
0x180030164  push    rdi
0x180030165  push    r12
0x180030167  push    r14
0x180030169  push    r15
0x18003016b  lea     rbp, [rsp-27h]
0x180030170  sub     rsp, 90h
0x180030177  mov     rax, cs:__security_cookie
0x18003017e  xor     rax, rsp
0x180030181  mov     [rbp+57h+var_38], rax
0x180030185  mov     r12, r8
0x180030188  mov     r14, rdx
0x18003018b  mov     r15, rcx
0x18003018e  mov     [rbp+57h+var_80], 0
0x180030196  lea     rax, [rcx+68h]
0x18003019a  mov     rdx, [rax+10h]
0x18003019e  mov     rcx, 7FFFFFFFFFFFFFFEh
0x1800301a8  sub     rcx, rdx
0x1800301ab  test    r8, r8
0x1800301ae  jnz     loc_180030379
0x1800301b4  cmp     rcx, 0Ch
0x1800301b8  jb      loc_180030637
0x1800301be  cmp     qword ptr [rax+18h], 7
0x1800301c3  jbe     short loc_1800301C8
0x1800301c5  mov     rax, [rax]
0x1800301c8  mov     [rsp+0C0h+var_90], rdx
0x1800301cd  mov     [rsp+0C0h+var_98], rax
0x1800301d2  mov     [rsp+0C0h+var_A0], 0Ch
0x1800301db  lea     r9, aDeleteFrom; "DELETE FROM "
0x1800301e2  lea     rcx, [rbp+57h+Src]
0x1800301e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800301eb  nop
0x1800301ec  lea     rdx, aWhereName; " WHERE Name = ?;"
0x1800301f3  lea     rcx, [rbp+57h+Src]; Src
0x1800301f7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800301fc  xorps   xmm0, xmm0
0x1800301ff  movups  [rbp+57h+var_78], xmm0
0x180030203  xorps   xmm1, xmm1
0x180030206  movdqu  [rbp+57h+var_68], xmm1
0x18003020b  movups  xmm0, xmmword ptr [rax]
0x18003020e  movups  [rbp+57h+var_78], xmm0
0x180030212  movups  xmm1, xmmword ptr [rax+10h]
0x180030216  movups  [rbp+57h+var_68], xmm1
0x18003021a  mov     qword ptr [rax+10h], 0
0x180030222  mov     qword ptr [rax+18h], 7
0x18003022a  xor     ecx, ecx
0x18003022c  mov     [rax], cx
0x18003022f  lea     rcx, [rbp+57h+Src]; void *
0x180030233  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030238  mov     [rbp+57h+var_80], 0
0x180030240  lea     rdx, [rbp+57h+var_78]
0x180030244  cmp     qword ptr [rbp+57h+var_68+8], 7
0x180030249  cmova   rdx, qword ptr [rbp+57h+var_78]
0x18003024e  mov     [rsp+0C0h+var_98], 0
0x180030257  lea     rax, [rbp+57h+var_80]
0x18003025b  mov     [rsp+0C0h+var_A0], rax
0x180030260  mov     r9d, 80h
0x180030266  or      r8d, 0FFFFFFFFh
0x18003026a  mov     rcx, [r15+8]
0x18003026e  call    sqlite3Prepare16
0x180030273  mov     edi, eax
0x180030275  test    eax, eax
0x180030277  jz      short loc_1800302CD
0x180030279  test    eax, eax
0x18003027b  jg      short loc_180030281
0x18003027d  mov     ebx, eax
0x18003027f  jmp     short loc_18003028A
0x180030281  movzx   ebx, di
0x180030284  or      ebx, 80070000h
0x18003028a  mov     rcx, [r15+8]
0x18003028e  call    sqlite3_errmsg
0x180030293  mov     [rsp+0C0h+var_98], rax
0x180030298  mov     dword ptr [rsp+0C0h+var_A0], edi
0x18003029c  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x1800302a3  mov     r8d, 4DDh
0x1800302a9  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800302b0  mov     ecx, 1
0x1800302b5  call    AslLogCallPrintf
0x1800302ba  nop
0x1800302bb  lea     rcx, [rbp+57h+var_78]; void *
0x1800302bf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800302c4  mov     rsi, [rbp+57h+var_80]
0x1800302c8  jmp     loc_180030603
0x1800302cd  mov     rsi, [rbp+57h+var_80]
0x1800302d1  test    rsi, rsi
0x1800302d4  jz      short loc_18003034E
0x1800302d6  mov     byte ptr [rsp+0C0h+var_98], 2
0x1800302db  mov     [rsp+0C0h+var_A0], 0
0x1800302e4  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800302eb  mov     r8, r14
0x1800302ee  lea     edi, [r9+3]
0x1800302f2  mov     edx, edi
0x1800302f4  mov     rcx, rsi
0x1800302f7  call    bindText
0x1800302fc  mov     r14d, eax
0x1800302ff  test    eax, eax
0x180030301  jz      short loc_180030349
0x180030303  test    eax, eax
0x180030305  jg      short loc_18003030B
0x180030307  mov     ebx, eax
0x180030309  jmp     short loc_180030315
0x18003030b  movzx   ebx, r14w
0x18003030f  or      ebx, 80070000h
0x180030315  mov     rcx, [r15+8]
0x180030319  call    sqlite3_errmsg
0x18003031e  mov     [rsp+0C0h+var_98], rax
0x180030323  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x180030328  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x18003032f  mov     r8d, 4EBh
0x180030335  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::SqliteInvCa"...
0x18003033c  mov     ecx, edi
0x18003033e  call    AslLogCallPrintf
0x180030343  nop
0x180030344  jmp     loc_1800305F9
0x180030349  jmp     loc_180030551
0x18003034e  mov     eax, 80004005h
0x180030353  mov     ebx, eax
0x180030355  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180030359  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x180030360  mov     r8d, 4E3h
0x180030366  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::SqliteInvCa"...
0x18003036d  mov     ecx, 1
0x180030372  call    AslLogCallPrintf
0x180030377  jmp     short loc_180030344
0x180030379  cmp     rcx, 0Dh
0x18003037d  jb      loc_180030631
0x180030383  cmp     qword ptr [rax+18h], 7
0x180030388  jbe     short loc_18003038D
0x18003038a  mov     rax, [rax]
0x18003038d  mov     [rsp+0C0h+var_90], rdx
0x180030392  mov     [rsp+0C0h+var_98], rax
0x180030397  mov     [rsp+0C0h+var_A0], 0Dh
0x1800303a0  lea     r9, aReplaceInto; "REPLACE INTO "
0x1800303a7  lea     rcx, [rbp+57h+Src]
0x1800303ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800303b0  nop
0x1800303b1  lea     rdx, aNameValueValue; " (Name, Value) VALUES (?, ?);"
0x1800303b8  lea     rcx, [rbp+57h+Src]; Src
0x1800303bc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800303c1  xorps   xmm0, xmm0
0x1800303c4  movups  [rbp+57h+var_78], xmm0
0x1800303c8  xorps   xmm1, xmm1
0x1800303cb  movdqu  [rbp+57h+var_68], xmm1
0x1800303d0  movups  xmm0, xmmword ptr [rax]
0x1800303d3  movups  [rbp+57h+var_78], xmm0
0x1800303d7  movups  xmm1, xmmword ptr [rax+10h]
0x1800303db  movups  [rbp+57h+var_68], xmm1
0x1800303df  mov     qword ptr [rax+10h], 0
0x1800303e7  mov     qword ptr [rax+18h], 7
0x1800303ef  xor     ecx, ecx
0x1800303f1  mov     [rax], cx
0x1800303f4  lea     rcx, [rbp+57h+Src]; void *
0x1800303f8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800303fd  mov     [rbp+57h+var_80], 0
0x180030405  lea     rdx, [rbp+57h+var_78]
0x180030409  cmp     qword ptr [rbp+57h+var_68+8], 7
0x18003040e  cmova   rdx, qword ptr [rbp+57h+var_78]
0x180030413  mov     [rsp+0C0h+var_98], 0
0x18003041c  lea     rax, [rbp+57h+var_80]
0x180030420  mov     [rsp+0C0h+var_A0], rax
0x180030425  mov     r9d, 80h
0x18003042b  or      r8d, 0FFFFFFFFh
0x18003042f  mov     rcx, [r15+8]
0x180030433  call    sqlite3Prepare16
0x180030438  mov     edi, eax
0x18003043a  test    eax, eax
0x18003043c  jz      short loc_180030485
0x18003043e  test    eax, eax
0x180030440  jg      short loc_180030446
0x180030442  mov     ebx, eax
0x180030444  jmp     short loc_18003044F
0x180030446  movzx   ebx, di
0x180030449  or      ebx, 80070000h
0x18003044f  mov     rcx, [r15+8]
0x180030453  call    sqlite3_errmsg
0x180030458  mov     [rsp+0C0h+var_98], rax
0x18003045d  mov     dword ptr [rsp+0C0h+var_A0], edi
0x180030461  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x180030468  mov     r8d, 4F6h
0x18003046e  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::SqliteInvCa"...
0x180030475  mov     ecx, 1
0x18003047a  call    AslLogCallPrintf
0x18003047f  nop
0x180030480  jmp     loc_1800302BB
0x180030485  mov     rsi, [rbp+57h+var_80]
0x180030489  test    rsi, rsi
0x18003048c  jz      loc_1800305CF
0x180030492  mov     byte ptr [rsp+0C0h+var_98], 2
0x180030497  mov     [rsp+0C0h+var_A0], 0
0x1800304a0  mov     rbx, 0FFFFFFFFFFFFFFFEh
0x1800304a7  mov     r9, rbx
0x1800304aa  mov     r8, r14
0x1800304ad  lea     edi, [rbx+3]
0x1800304b0  mov     edx, edi
0x1800304b2  mov     rcx, rsi
0x1800304b5  call    bindText
0x1800304ba  mov     r14d, eax
0x1800304bd  test    eax, eax
0x1800304bf  jz      short loc_180030506
0x1800304c1  test    eax, eax
0x1800304c3  jg      short loc_1800304C9
0x1800304c5  mov     ebx, eax
0x1800304c7  jmp     short loc_1800304D3
0x1800304c9  movzx   ebx, r14w
0x1800304cd  or      ebx, 80070000h
0x1800304d3  mov     rcx, [r15+8]
0x1800304d7  call    sqlite3_errmsg
0x1800304dc  mov     r8d, 504h
0x1800304e2  mov     [rsp+0C0h+var_98], rax
0x1800304e7  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x1800304ee  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x1800304f3  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800304fa  mov     ecx, edi
0x1800304fc  call    AslLogCallPrintf
0x180030501  jmp     loc_1800305F9
0x180030506  mov     byte ptr [rsp+0C0h+var_98], 2
0x18003050b  mov     [rsp+0C0h+var_A0], 0
0x180030514  mov     r9, rbx
0x180030517  mov     r8, r12
0x18003051a  mov     edx, 2
0x18003051f  mov     rcx, rsi
0x180030522  call    bindText
0x180030527  mov     r14d, eax
0x18003052a  test    eax, eax
0x18003052c  jz      short loc_180030551
0x18003052e  test    eax, eax
0x180030530  jg      short loc_180030536
0x180030532  mov     ebx, eax
0x180030534  jmp     short loc_180030540
0x180030536  movzx   ebx, r14w
0x18003053a  or      ebx, 80070000h
0x180030540  mov     rcx, [r15+8]
0x180030544  call    sqlite3_errmsg
0x180030549  mov     r8d, 50Ch
0x18003054f  jmp     short loc_1800304E2
0x180030551  lea     rcx, [rbp+57h+var_78]; void *
0x180030555  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003055a  xor     ebx, ebx
0x18003055c  xor     r12d, r12d
0x18003055f  mov     rcx, rsi
0x180030562  call    sqlite3_step
0x180030567  mov     r14d, eax
0x18003056a  lea     ecx, [rax-5]
0x18003056d  cmp     ecx, edi
0x18003056f  ja      short loc_180030585
0x180030571  mov     ecx, 5; dwMilliseconds
0x180030576  call    cs:__imp_Sleep
0x18003057c  add     r12d, edi
0x18003057f  cmp     r12d, 64h ; 'd'
0x180030583  jl      short loc_18003055F
0x180030585  cmp     r14d, 65h ; 'e'
0x180030589  jz      short loc_180030603
0x18003058b  test    r14d, r14d
0x18003058e  jg      short loc_180030595
0x180030590  mov     ebx, r14d
0x180030593  jmp     short loc_18003059F
0x180030595  movzx   ebx, r14w
0x180030599  or      ebx, 80070000h
0x18003059f  mov     rcx, [r15+8]
0x1800305a3  call    sqlite3_errmsg
0x1800305a8  mov     [rsp+0C0h+var_98], rax
0x1800305ad  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x1800305b2  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x1800305b9  mov     r8d, 515h
0x1800305bf  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800305c6  mov     ecx, edi
0x1800305c8  call    AslLogCallPrintf
0x1800305cd  jmp     short loc_180030603
0x1800305cf  mov     eax, 80004005h
0x1800305d4  mov     ebx, eax
0x1800305d6  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800305da  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x1800305e1  mov     r8d, 4FCh
0x1800305e7  lea     rdx, aWindowsCompatI_12; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800305ee  mov     ecx, 1
0x1800305f3  call    AslLogCallPrintf
0x1800305f8  nop
0x1800305f9  lea     rcx, [rbp+57h+var_78]; void *
0x1800305fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030602  nop
0x180030603  test    rsi, rsi
0x180030606  jz      short loc_180030611
0x180030608  mov     rcx, rsi
0x18003060b  call    sqlite3_finalize
0x180030610  nop
0x180030611  mov     eax, ebx
0x180030613  mov     rcx, [rbp+57h+var_38]
0x180030617  xor     rcx, rsp; StackCookie
0x18003061a  call    __security_check_cookie
0x18003061f  add     rsp, 90h
0x180030626  pop     r15
0x180030628  pop     r14
0x18003062a  pop     r12
0x18003062c  pop     rdi
0x18003062d  pop     rsi
0x18003062e  pop     rbx
0x18003062f  pop     rbp
0x180030630  retn
  ... truncated ...
```
