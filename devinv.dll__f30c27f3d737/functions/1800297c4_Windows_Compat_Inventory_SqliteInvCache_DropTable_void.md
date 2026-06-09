# Windows::Compat::Inventory::SqliteInvCache::DropTable(void)

- ea: `0x1800297c4`
- end: `0x180029b3a`
- name: `?DropTable@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ`
- size: `886`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180027e90`

## callees

- `0x180005e40`
- `0x18000fa50`
- `0x180010a9c`
- `0x180013f20`
- `0x180016440`
- `0x180026308`
- `0x1800297c4`
- `0x18003172c`
- `0x180066c10`
- `0x1800c9a2c`
- `0x1800e9be0`
- `0x1800ea520`
- `0x1800ec8f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029a2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a1a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002992b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029aa3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002992b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029aa3`

## string_xrefs

- `0x1800298f0`: `Windows::Compat::Inventory::SqliteInvCache::DropTable`
- `0x18002995e`: `Windows::Compat::Inventory::SqliteInvCache::DropTable`
- `0x180029ad6`: `Windows::Compat::Inventory::SqliteInvCache::DropTable`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::DropTable(
        Windows::Compat::Inventory::SqliteInvCache *this,
        __int64 a2,
        __int64 a3)
{
  int v4; // r12d
  _QWORD *v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int128 *v8; // rdx
  signed int v9; // edi
  const char *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // ebx
  const char *v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // rax
  DWORD LastError; // ebx
  __int128 *v18; // rdx
  int v19; // ebx
  __int64 v20; // r12
  __int64 v21; // rax
  const char *v22; // r9
  __int64 v23; // r8
  int i; // r15d
  __int64 v26; // [rsp+20h] [rbp-69h]
  __int64 v27; // [rsp+40h] [rbp-49h] BYREF
  __int128 v28; // [rsp+48h] [rbp-41h] BYREF
  __int128 v29; // [rsp+58h] [rbp-31h]
  _OWORD Src[2]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v31[32]; // [rsp+88h] [rbp-1h] BYREF

  v4 = 0;
  v5 = (_QWORD *)((char *)this + 72);
  v6 = *((_QWORD *)this + 11);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v6) < 0x15 )
    std::_Xlen_string();
  if ( v5[3] > 7u )
    v5 = (_QWORD *)*v5;
  std::wstring::wstring(Src, v5, a3, L"DROP TABLE IF EXISTS ", 21, v5, v6);
  v7 = std::wstring::append(Src, L";");
  v28 = 0;
  v29 = 0;
  v28 = *(_OWORD *)v7;
  v29 = *(_OWORD *)(v7 + 16);
  *(_QWORD *)(v7 + 16) = 0;
  *(_QWORD *)(v7 + 24) = 7;
  *(_WORD *)v7 = 0;
  std::wstring::~wstring(Src);
  std::list<std::wstring>::clear((char *)this + 24);
  std::list<std::wstring>::clear((char *)this + 48);
  v27 = 0;
  v8 = &v28;
  if ( *((_QWORD *)&v29 + 1) > 7u )
    LODWORD(v8) = v28;
  v9 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v8, -1, 128, (__int64)&v27, 0);
  if ( v9 )
  {
    v10 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::DropTable",
      1544,
      "sqlite3_exec failed: [%d] %hs",
      v9,
      v10);
    if ( v9 <= 0 )
      goto LABEL_17;
    v9 = (unsigned __int16)v9;
    goto LABEL_9;
  }
  v9 = 0;
  do
  {
    v13 = sqlite3_step(v27);
    if ( (unsigned int)(v13 - 5) > 1 )
      break;
    Sleep(5u);
    ++v4;
  }
  while ( v4 < 100 );
  if ( v13 != 101 )
  {
    v14 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::DropTable",
      1552,
      "sqlite3_step failed: [%d] %hs",
      v13,
      v14);
    if ( v13 > 0 )
    {
      v9 = (unsigned __int16)v13;
LABEL_9:
      v9 |= 0x80070000;
      goto LABEL_17;
    }
    v9 = v13;
  }
LABEL_17:
  v15 = (_QWORD *)((char *)this + 104);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - *((_QWORD *)this + 15)) < 0x15 )
    std::_Xlen_string();
  if ( *((_QWORD *)this + 16) > 7u )
    v15 = (_QWORD *)*v15;
  std::wstring::wstring(v31, v11, v12, L"DROP TABLE IF EXISTS ", 21, v15, *((_QWORD *)this + 15));
  v16 = std::wstring::append(v31, L";");
  Src[0] = *(_OWORD *)v16;
  Src[1] = *(_OWORD *)(v16 + 16);
  *(_QWORD *)(v16 + 16) = 0;
  *(_QWORD *)(v16 + 24) = 7;
  *(_WORD *)v16 = 0;
  std::wstring::operator=(&v28, Src);
  std::wstring::~wstring(Src);
  std::wstring::~wstring(v31);
  if ( v27 )
  {
    LastError = GetLastError();
    sqlite3_finalize(v27);
    SetLastError(LastError);
  }
  v27 = 0;
  v18 = &v28;
  if ( *((_QWORD *)&v29 + 1) > 7u )
    LODWORD(v18) = v28;
  v19 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v18, -1, 128, (__int64)&v27, 0);
  v20 = v27;
  if ( v19 )
  {
    v21 = sqlite3_errmsg(*((_QWORD *)this + 1));
    v22 = "sqlite3_exec failed: [%d] %hs";
    v23 = 1562;
  }
  else
  {
    for ( i = 0; i < 100; ++i )
    {
      v19 = sqlite3_step(v20);
      if ( (unsigned int)(v19 - 5) > 1 )
        break;
      Sleep(5u);
    }
    if ( v19 == 101 )
      goto LABEL_34;
    v21 = sqlite3_errmsg(*((_QWORD *)this + 1));
    v22 = "sqlite3_step failed: [%d] %hs";
    v23 = 1570;
  }
  LODWORD(v26) = v19;
  AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::DropTable", v23, v22, v26, v21);
  if ( v19 > 0 )
    v9 = (unsigned __int16)v19 | 0x80070000;
  else
    v9 = v19;
LABEL_34:
  if ( v20 )
    sqlite3_finalize(v20);
  std::wstring::~wstring(&v28);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800297c4  push    rbp
0x1800297c6  push    rbx
0x1800297c7  push    rdi
0x1800297c8  push    r12
0x1800297ca  push    r14
0x1800297cc  push    r15
0x1800297ce  lea     rbp, [rsp-2Fh]
0x1800297d3  sub     rsp, 0B8h
0x1800297da  mov     rax, cs:__security_cookie
0x1800297e1  xor     rax, rsp
0x1800297e4  mov     [rbp+57h+var_38], rax
0x1800297e8  mov     r14, rcx
0x1800297eb  xor     r12d, r12d
0x1800297ee  lea     rdx, [rcx+48h]
0x1800297f2  mov     rcx, [rdx+10h]
0x1800297f6  mov     r15, 7FFFFFFFFFFFFFFEh
0x180029800  mov     rax, r15
0x180029803  sub     rax, rcx
0x180029806  cmp     rax, 15h
0x18002980a  jb      loc_180029B34
0x180029810  cmp     qword ptr [rdx+18h], 7
0x180029815  jbe     short loc_18002981A
0x180029817  mov     rdx, [rdx]
0x18002981a  mov     [rsp+0E0h+var_B0], rcx
0x18002981f  mov     [rsp+0E0h+var_B8], rdx
0x180029824  mov     [rsp+0E0h+var_C0], 15h
0x18002982d  lea     r9, aDropTableIfExi; "DROP TABLE IF EXISTS "
0x180029834  lea     rcx, [rbp+57h+Src]
0x180029838  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002983d  nop
0x18002983e  lea     rdx, asc_180123B10; ";"
0x180029845  lea     rcx, [rbp+57h+Src]; Src
0x180029849  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002984e  xorps   xmm0, xmm0
0x180029851  movups  [rbp+57h+var_98], xmm0
0x180029855  xorps   xmm1, xmm1
0x180029858  movdqu  [rbp+57h+var_88], xmm1
0x18002985d  movups  xmm0, xmmword ptr [rax]
0x180029860  movups  [rbp+57h+var_98], xmm0
0x180029864  movups  xmm1, xmmword ptr [rax+10h]
0x180029868  movups  [rbp+57h+var_88], xmm1
0x18002986c  mov     [rax+10h], r12
0x180029870  mov     qword ptr [rax+18h], 7
0x180029878  mov     [rax], r12w
0x18002987c  lea     rcx, [rbp+57h+Src]; void *
0x180029880  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029885  nop
0x180029886  lea     rcx, [r14+18h]
0x18002988a  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::list<std::wstring>::clear(void)
0x18002988f  lea     rcx, [r14+30h]
0x180029893  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::list<std::wstring>::clear(void)
0x180029898  mov     [rbp+57h+var_A0], r12
0x18002989c  lea     rdx, [rbp+57h+var_98]
0x1800298a0  cmp     qword ptr [rbp+57h+var_88+8], 7
0x1800298a5  cmova   rdx, qword ptr [rbp+57h+var_98]
0x1800298aa  mov     [rsp+0E0h+var_B8], r12
0x1800298af  lea     rax, [rbp+57h+var_A0]
0x1800298b3  mov     [rsp+0E0h+var_C0], rax
0x1800298b8  mov     r9d, 80h
0x1800298be  or      r8d, 0FFFFFFFFh
0x1800298c2  mov     rcx, [r14+8]
0x1800298c6  call    sqlite3Prepare16
0x1800298cb  mov     edi, eax
0x1800298cd  test    eax, eax
0x1800298cf  jz      short loc_180029910
0x1800298d1  mov     rcx, [r14+8]
0x1800298d5  call    sqlite3_errmsg
0x1800298da  mov     [rsp+0E0h+var_B8], rax
0x1800298df  mov     dword ptr [rsp+0E0h+var_C0], edi
0x1800298e3  lea     r9, aSqlite3ExecFai; "sqlite3_exec failed: [%d] %hs"
0x1800298ea  mov     r8d, 608h
0x1800298f0  lea     rdx, aWindowsCompatI; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800298f7  mov     ecx, 1
0x1800298fc  call    AslLogCallPrintf
0x180029901  test    edi, edi
0x180029903  jle     short loc_180029982
0x180029905  movzx   edi, di
0x180029908  or      edi, 80070000h
0x18002990e  jmp     short loc_180029982
0x180029910  mov     edi, r12d
0x180029913  mov     rcx, [rbp+57h+var_A0]
0x180029917  call    sqlite3_step
0x18002991c  mov     ebx, eax
0x18002991e  lea     ecx, [rax-5]
0x180029921  cmp     ecx, 1
0x180029924  ja      short loc_18002993A
0x180029926  mov     ecx, 5; dwMilliseconds
0x18002992b  call    cs:__imp_Sleep
0x180029931  inc     r12d
0x180029934  cmp     r12d, 64h ; 'd'
0x180029938  jl      short loc_180029913
0x18002993a  cmp     ebx, 65h ; 'e'
0x18002993d  jz      short loc_18002997F
0x18002993f  mov     rcx, [r14+8]
0x180029943  call    sqlite3_errmsg
0x180029948  mov     [rsp+0E0h+var_B8], rax
0x18002994d  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180029951  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x180029958  mov     r8d, 610h
0x18002995e  lea     rdx, aWindowsCompatI; "Windows::Compat::Inventory::SqliteInvCa"...
0x180029965  mov     ecx, 1
0x18002996a  call    AslLogCallPrintf
0x18002996f  xor     r12d, r12d
0x180029972  test    ebx, ebx
0x180029974  jg      short loc_18002997A
0x180029976  mov     edi, ebx
0x180029978  jmp     short loc_180029982
0x18002997a  movzx   edi, bx
0x18002997d  jmp     short loc_180029908
0x18002997f  xor     r12d, r12d
0x180029982  lea     rax, [r14+68h]
0x180029986  mov     rcx, [rax+10h]
0x18002998a  sub     r15, rcx
0x18002998d  cmp     r15, 15h
0x180029991  jb      loc_180029B2E
0x180029997  cmp     qword ptr [rax+18h], 7
0x18002999c  jbe     short loc_1800299A1
0x18002999e  mov     rax, [rax]
0x1800299a1  mov     [rsp+0E0h+var_B0], rcx
0x1800299a6  mov     [rsp+0E0h+var_B8], rax
0x1800299ab  mov     [rsp+0E0h+var_C0], 15h
0x1800299b4  lea     r9, aDropTableIfExi; "DROP TABLE IF EXISTS "
0x1800299bb  lea     rcx, [rbp+57h+var_58]
0x1800299bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800299c4  nop
0x1800299c5  lea     rdx, asc_180123B10; ";"
0x1800299cc  lea     rcx, [rbp+57h+var_58]; Src
0x1800299d0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800299d5  movups  xmm0, xmmword ptr [rax]
0x1800299d8  movups  [rbp+57h+Src], xmm0
0x1800299dc  movups  xmm1, xmmword ptr [rax+10h]
0x1800299e0  movups  [rbp+57h+var_68], xmm1
0x1800299e4  mov     [rax+10h], r12
0x1800299e8  mov     qword ptr [rax+18h], 7
0x1800299f0  mov     [rax], r12w
0x1800299f4  lea     rdx, [rbp+57h+Src]
0x1800299f8  lea     rcx, [rbp+57h+var_98]
0x1800299fc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180029a01  lea     rcx, [rbp+57h+Src]; void *
0x180029a05  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029a0a  nop
0x180029a0b  lea     rcx, [rbp+57h+var_58]; void *
0x180029a0f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029a14  cmp     [rbp+57h+var_A0], r12
0x180029a18  jz      short loc_180029A34
0x180029a1a  call    cs:__imp_GetLastError
0x180029a20  mov     ebx, eax
0x180029a22  mov     rcx, [rbp+57h+var_A0]
0x180029a26  call    sqlite3_finalize
0x180029a2b  mov     ecx, ebx; dwErrCode
0x180029a2d  call    cs:__imp_SetLastError
0x180029a33  nop
0x180029a34  mov     [rbp+57h+var_A0], r12
0x180029a38  lea     rdx, [rbp+57h+var_98]
0x180029a3c  cmp     qword ptr [rbp+57h+var_88+8], 7
0x180029a41  cmova   rdx, qword ptr [rbp+57h+var_98]
0x180029a46  mov     [rsp+0E0h+var_B8], r12
0x180029a4b  lea     rax, [rbp+57h+var_A0]
0x180029a4f  mov     [rsp+0E0h+var_C0], rax
0x180029a54  mov     r9d, 80h
0x180029a5a  or      r8d, 0FFFFFFFFh
0x180029a5e  mov     rcx, [r14+8]
0x180029a62  call    sqlite3Prepare16
0x180029a67  mov     ebx, eax
0x180029a69  mov     r12, [rbp+57h+var_A0]
0x180029a6d  test    eax, eax
0x180029a6f  jz      short loc_180029A89
0x180029a71  mov     rcx, [r14+8]
0x180029a75  call    sqlite3_errmsg
0x180029a7a  lea     r9, aSqlite3ExecFai; "sqlite3_exec failed: [%d] %hs"
0x180029a81  mov     r8d, 61Ah
0x180029a87  jmp     short loc_180029ACD
0x180029a89  xor     r15d, r15d
0x180029a8c  mov     rcx, r12
0x180029a8f  call    sqlite3_step
0x180029a94  mov     ebx, eax
0x180029a96  lea     ecx, [rax-5]
0x180029a99  cmp     ecx, 1
0x180029a9c  ja      short loc_180029AB2
0x180029a9e  mov     ecx, 5; dwMilliseconds
0x180029aa3  call    cs:__imp_Sleep
0x180029aa9  inc     r15d
0x180029aac  cmp     r15d, 64h ; 'd'
0x180029ab0  jl      short loc_180029A8C
0x180029ab2  cmp     ebx, 65h ; 'e'
0x180029ab5  jz      short loc_180029AF8
0x180029ab7  mov     rcx, [r14+8]
0x180029abb  call    sqlite3_errmsg
0x180029ac0  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x180029ac7  mov     r8d, 622h
0x180029acd  mov     [rsp+0E0h+var_B8], rax
0x180029ad2  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180029ad6  lea     rdx, aWindowsCompatI; "Windows::Compat::Inventory::SqliteInvCa"...
0x180029add  mov     ecx, 1
0x180029ae2  call    AslLogCallPrintf
0x180029ae7  test    ebx, ebx
0x180029ae9  jg      short loc_180029AEF
0x180029aeb  mov     edi, ebx
0x180029aed  jmp     short loc_180029AF8
0x180029aef  movzx   edi, bx
0x180029af2  or      edi, 80070000h
0x180029af8  test    r12, r12
0x180029afb  jz      short loc_180029B06
0x180029afd  mov     rcx, r12
0x180029b00  call    sqlite3_finalize
0x180029b05  nop
0x180029b06  lea     rcx, [rbp+57h+var_98]; void *
0x180029b0a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029b0f  mov     eax, edi
0x180029b11  mov     rcx, [rbp+57h+var_38]
0x180029b15  xor     rcx, rsp; StackCookie
0x180029b18  call    __security_check_cookie
0x180029b1d  add     rsp, 0B8h
0x180029b24  pop     r15
0x180029b26  pop     r14
0x180029b28  pop     r12
0x180029b2a  pop     rdi
0x180029b2b  pop     rbx
0x180029b2c  pop     rbp
0x180029b2d  retn
0x180029b2e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180029b34  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
