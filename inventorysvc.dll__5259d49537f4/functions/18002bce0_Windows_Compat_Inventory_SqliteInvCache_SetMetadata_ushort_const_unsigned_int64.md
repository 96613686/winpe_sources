# Windows::Compat::Inventory::SqliteInvCache::SetMetadata(ushort const *,unsigned __int64)

- ea: `0x18002bce0`
- end: `0x18002bfe8`
- name: `?SetMetadata@SqliteInvCache@Inventory@Compat@Windows@@UEAAJPEBG_K@Z`
- size: `776`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180002bf0`
- `0x1800074f0`
- `0x1800109dc`
- `0x1800152d0`
- `0x18001f3b4`
- `0x18001f4a4`
- `0x18001fd88`
- `0x18002bce0`
- `0x180036be4`
- `0x1800817cc`
- `0x1800a1980`
- `0x1800a22c0`
- `0x1800a4690`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002bf39`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002bf39`

## string_xrefs

- `0x18002bd51`: `REPLACE INTO `
- `0x18002bdfb`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x18002bf8f`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::SetMetadata(
        Windows::Compat::Inventory::SqliteInvCache *this,
        const unsigned __int16 *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // rbx
  int v4; // esi
  _QWORD *v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rdx
  int v9; // eax
  int v10; // edi
  __int64 v11; // r14
  unsigned int v12; // ebx
  int v13; // eax
  int v14; // esi
  __int64 v15; // rax
  __int64 v16; // r8
  const char *v17; // r9
  _WORD *v18; // r10
  _QWORD *v19; // r8
  int i; // r15d
  __int64 v22; // [rsp+20h] [rbp-69h]
  __int64 v23; // [rsp+20h] [rbp-69h]
  __int64 v24; // [rsp+28h] [rbp-61h]
  __int64 v25; // [rsp+28h] [rbp-61h]
  __int64 v26; // [rsp+28h] [rbp-61h]
  __int64 v27; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v28[4]; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v29[9]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v30[6]; // [rsp+B2h] [rbp+29h] BYREF

  v3 = a3;
  v4 = (int)a2;
  v6 = (_QWORD *)((char *)this + 104);
  v7 = *((_QWORD *)this + 15);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v7) < 0xD )
    std::_Xlen_string();
  if ( v6[3] > 7u )
    v6 = (_QWORD *)*v6;
  std::wstring::wstring(v28, v6, a3, L"REPLACE INTO ", 13, v6, v7);
  std::operator+<unsigned short>(v29, v28, L" (Name, Value) VALUES (?, ?);");
  std::wstring::~wstring(v28);
  v27 = 0;
  v8 = v29;
  if ( v29[3] > 7u )
    LODWORD(v8) = v29[0];
  v9 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v8, -1, 128, (__int64)&v27, 0);
  v10 = v9;
  v11 = v27;
  if ( v9 )
  {
    if ( v9 > 0 )
      v12 = (unsigned __int16)v9 | 0x80070000;
    else
      v12 = v9;
    v25 = sqlite3_errmsg(*((_QWORD *)this + 1));
    LODWORD(v22) = v10;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1194,
      "sqlite3_prepare_v2 failed: [%d] %hs",
      v22,
      v25);
    goto LABEL_38;
  }
  if ( v27 )
  {
    LOBYTE(v24) = 2;
    v13 = bindText(v27, 1, v4, -2, 0, v24);
    v14 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v12 = (unsigned __int16)v13 | 0x80070000;
      else
        v12 = v13;
      v15 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v16 = 1208;
    }
    else
    {
      v18 = v30;
      do
      {
        *--v18 = v3 % 0xA + 48;
        v3 /= 0xAu;
      }
      while ( v3 );
      std::wstring::wstring(v28, v18, v30);
      v19 = v28;
      if ( v28[3] > 7u )
        LODWORD(v19) = v28[0];
      LOBYTE(v26) = 2;
      v14 = bindText(v11, 2, (_DWORD)v19, -2, -1, v26);
      std::wstring::~wstring(v28);
      if ( !v14 )
      {
        v12 = 0;
        for ( i = 0; i < 100; ++i )
        {
          v14 = sqlite3_step(v11);
          if ( (unsigned int)(v14 - 5) > 1 )
            break;
          Sleep(5u);
        }
        if ( v14 == 101 )
          goto LABEL_38;
        if ( v14 > 0 )
          v12 = (unsigned __int16)v14 | 0x80070000;
        else
          v12 = v14;
        v15 = sqlite3_errmsg(*((_QWORD *)this + 1));
        v17 = "sqlite3_step failed: [%d] %hs";
        v16 = 1223;
        goto LABEL_19;
      }
      if ( v14 > 0 )
        v12 = (unsigned __int16)v14 | 0x80070000;
      else
        v12 = v14;
      v15 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v16 = 1216;
    }
    v17 = "sqlite3_bind_text16 failed: [%d] %hs";
LABEL_19:
    LODWORD(v23) = v14;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::SetMetadata", v16, v17, v23, v15);
    goto LABEL_38;
  }
  v12 = -2147467259;
  AslLogCallPrintf(
    1,
    "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
    1200,
    "sqlite3_prepare_v2 returned a null statement [%#x]",
    -2147467259);
LABEL_38:
  if ( v11 )
    sqlite3_finalize(v11);
  std::wstring::~wstring(v29);
  return v12;
}

```

## disassembly

```asm
0x18002bce0  mov     [rsp-8+arg_10], rbx
0x18002bce5  mov     [rsp-8+arg_18], rsi
0x18002bcea  push    rbp
0x18002bceb  push    rdi
0x18002bcec  push    r13
0x18002bcee  push    r14
0x18002bcf0  push    r15
0x18002bcf2  lea     rbp, [rsp-37h]
0x18002bcf7  sub     rsp, 0C0h
0x18002bcfe  mov     rax, cs:__security_cookie
0x18002bd05  xor     rax, rsp
0x18002bd08  mov     [rbp+57h+var_28], rax
0x18002bd0c  mov     rbx, r8
0x18002bd0f  mov     rsi, rdx
0x18002bd12  mov     r13, rcx
0x18002bd15  lea     rdx, [rcx+68h]
0x18002bd19  mov     rcx, [rdx+10h]
0x18002bd1d  mov     rax, 7FFFFFFFFFFFFFFEh
0x18002bd27  sub     rax, rcx
0x18002bd2a  cmp     rax, 0Dh
0x18002bd2e  jb      loc_18002BFE2
0x18002bd34  cmp     qword ptr [rdx+18h], 7
0x18002bd39  jbe     short loc_18002BD3E
0x18002bd3b  mov     rdx, [rdx]
0x18002bd3e  mov     [rsp+0E0h+var_B0], rcx
0x18002bd43  mov     [rsp+0E0h+var_B8], rdx
0x18002bd48  mov     [rsp+0E0h+var_C0], 0Dh
0x18002bd51  lea     r9, aReplaceInto; "REPLACE INTO "
0x18002bd58  lea     rcx, [rbp+57h+var_98]
0x18002bd5c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002bd61  nop
0x18002bd62  lea     r8, aNameValueValue; " (Name, Value) VALUES (?, ?);"
0x18002bd69  lea     rdx, [rbp+57h+var_98]
0x18002bd6d  lea     rcx, [rbp+57h+var_78]
0x18002bd71  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002bd76  nop
0x18002bd77  lea     rcx, [rbp+57h+var_98]; void *
0x18002bd7b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002bd80  nop
0x18002bd81  mov     [rbp+57h+var_A0], 0
0x18002bd89  lea     rdx, [rbp+57h+var_78]
0x18002bd8d  cmp     [rbp+57h+var_60], 7
0x18002bd92  cmova   rdx, [rbp+57h+var_78]
0x18002bd97  mov     [rsp+0E0h+var_B8], 0
0x18002bda0  lea     rax, [rbp+57h+var_A0]
0x18002bda4  mov     [rsp+0E0h+var_C0], rax
0x18002bda9  mov     r9d, 80h
0x18002bdaf  or      r8d, 0FFFFFFFFh
0x18002bdb3  mov     rcx, [r13+8]
0x18002bdb7  call    sqlite3Prepare16
0x18002bdbc  mov     edi, eax
0x18002bdbe  mov     r14, [rbp+57h+var_A0]
0x18002bdc2  test    eax, eax
0x18002bdc4  jz      short loc_18002BE0C
0x18002bdc6  test    eax, eax
0x18002bdc8  jg      short loc_18002BDCE
0x18002bdca  mov     ebx, eax
0x18002bdcc  jmp     short loc_18002BDD7
0x18002bdce  movzx   ebx, di
0x18002bdd1  or      ebx, 80070000h
0x18002bdd7  mov     rcx, [r13+8]
0x18002bddb  call    sqlite3_errmsg
0x18002bde0  mov     [rsp+0E0h+var_B8], rax
0x18002bde5  mov     dword ptr [rsp+0E0h+var_C0], edi
0x18002bde9  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x18002bdf0  mov     r8d, 4AAh
0x18002bdf6  mov     ecx, 1
0x18002bdfb  lea     rdx, aWindowsCompatI_47; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002be02  call    AslLogCallPrintf
0x18002be07  jmp     loc_18002BFA1
0x18002be0c  test    r14, r14
0x18002be0f  jz      loc_18002BF79
0x18002be15  mov     byte ptr [rsp+0E0h+var_B8], 2
0x18002be1a  mov     [rsp+0E0h+var_C0], 0
0x18002be23  mov     r15, 0FFFFFFFFFFFFFFFEh
0x18002be2a  mov     r9, r15
0x18002be2d  mov     r8, rsi
0x18002be30  lea     edi, [r15+3]
0x18002be34  mov     edx, edi
0x18002be36  mov     rcx, r14
0x18002be39  call    bindText
0x18002be3e  mov     esi, eax
0x18002be40  test    eax, eax
0x18002be42  jz      short loc_18002BE78
0x18002be44  test    eax, eax
0x18002be46  jg      short loc_18002BE4C
0x18002be48  mov     ebx, eax
0x18002be4a  jmp     short loc_18002BE55
0x18002be4c  movzx   ebx, si
0x18002be4f  or      ebx, 80070000h
0x18002be55  mov     rcx, [r13+8]
0x18002be59  call    sqlite3_errmsg
0x18002be5e  mov     r8d, 4B8h
0x18002be64  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x18002be6b  mov     [rsp+0E0h+var_B8], rax
0x18002be70  mov     dword ptr [rsp+0E0h+var_C0], esi
0x18002be74  mov     ecx, edi
0x18002be76  jmp     short loc_18002BDFB
0x18002be78  lea     r10, [rbp+57h+var_2E]
0x18002be7c  sub     r10, 2
0x18002be80  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002be8a  mul     rbx
0x18002be8d  shr     rdx, 3
0x18002be91  movzx   eax, dx
0x18002be94  shl     ax, 2
0x18002be98  lea     ecx, [rax+rdx]
0x18002be9b  add     cx, cx
0x18002be9e  sub     bx, cx
0x18002bea1  add     bx, 30h ; '0'
0x18002bea5  mov     [r10], bx
0x18002bea9  mov     rbx, rdx
0x18002beac  test    rdx, rdx
0x18002beaf  jnz     short loc_18002BE7C
0x18002beb1  lea     r8, [rbp+57h+var_2E]
0x18002beb5  mov     rdx, r10
0x18002beb8  lea     rcx, [rbp+57h+var_98]
0x18002bebc  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18002bec1  nop
0x18002bec2  lea     r8, [rbp+57h+var_98]
0x18002bec6  cmp     [rbp+57h+var_80], 7
0x18002becb  cmova   r8, [rbp+57h+var_98]
0x18002bed0  mov     byte ptr [rsp+0E0h+var_B8], 2
0x18002bed5  mov     [rsp+0E0h+var_C0], 0FFFFFFFFFFFFFFFFh
0x18002bede  mov     r9, r15
0x18002bee1  lea     edx, [rbx+2]
0x18002bee4  mov     rcx, r14
0x18002bee7  call    bindText
0x18002beec  mov     esi, eax
0x18002beee  lea     rcx, [rbp+57h+var_98]; void *
0x18002bef2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002bef7  test    esi, esi
0x18002bef9  jz      short loc_18002BF1E
0x18002befb  jg      short loc_18002BF01
0x18002befd  mov     ebx, esi
0x18002beff  jmp     short loc_18002BF0A
0x18002bf01  movzx   ebx, si
0x18002bf04  or      ebx, 80070000h
0x18002bf0a  mov     rcx, [r13+8]
0x18002bf0e  call    sqlite3_errmsg
0x18002bf13  mov     r8d, 4C0h
0x18002bf19  jmp     loc_18002BE64
0x18002bf1e  xor     ebx, ebx
0x18002bf20  xor     r15d, r15d
0x18002bf23  mov     rcx, r14
0x18002bf26  call    sqlite3_step
0x18002bf2b  mov     esi, eax
0x18002bf2d  lea     ecx, [rax-5]
0x18002bf30  cmp     ecx, edi
0x18002bf32  ja      short loc_18002BF48
0x18002bf34  mov     ecx, 5; dwMilliseconds
0x18002bf39  call    cs:__imp_Sleep
0x18002bf3f  add     r15d, edi
0x18002bf42  cmp     r15d, 64h ; 'd'
0x18002bf46  jl      short loc_18002BF23
0x18002bf48  cmp     esi, 65h ; 'e'
0x18002bf4b  jz      short loc_18002BFA1
0x18002bf4d  test    esi, esi
0x18002bf4f  jg      short loc_18002BF55
0x18002bf51  mov     ebx, esi
0x18002bf53  jmp     short loc_18002BF5E
0x18002bf55  movzx   ebx, si
0x18002bf58  or      ebx, 80070000h
0x18002bf5e  mov     rcx, [r13+8]
0x18002bf62  call    sqlite3_errmsg
0x18002bf67  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x18002bf6e  mov     r8d, 4C7h
0x18002bf74  jmp     loc_18002BE6B
0x18002bf79  mov     ebx, 80004005h
0x18002bf7e  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18002bf82  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x18002bf89  mov     r8d, 4B0h
0x18002bf8f  lea     rdx, aWindowsCompatI_47; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002bf96  mov     ecx, 1
0x18002bf9b  call    AslLogCallPrintf
0x18002bfa0  nop
0x18002bfa1  test    r14, r14
0x18002bfa4  jz      short loc_18002BFAF
0x18002bfa6  mov     rcx, r14
0x18002bfa9  call    sqlite3_finalize
0x18002bfae  nop
0x18002bfaf  lea     rcx, [rbp+57h+var_78]; void *
0x18002bfb3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002bfb8  mov     eax, ebx
0x18002bfba  mov     rcx, [rbp+57h+var_28]
0x18002bfbe  xor     rcx, rsp; StackCookie
0x18002bfc1  call    __security_check_cookie
0x18002bfc6  lea     r11, [rsp+0E0h+var_20]
0x18002bfce  mov     rbx, [r11+40h]
0x18002bfd2  mov     rsi, [r11+48h]
0x18002bfd6  mov     rsp, r11
0x18002bfd9  pop     r15
0x18002bfdb  pop     r14
0x18002bfdd  pop     r13
0x18002bfdf  pop     rdi
0x18002bfe0  pop     rbp
0x18002bfe1  retn
0x18002bfe2  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
