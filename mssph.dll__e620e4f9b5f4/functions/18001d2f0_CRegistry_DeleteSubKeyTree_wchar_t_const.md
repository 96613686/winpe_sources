# CRegistry::DeleteSubKeyTree(wchar_t const *)

- ea: `0x18001d2f0`
- end: `0x18001d478`
- name: `?DeleteSubKeyTree@CRegistry@@UEAAHPEB_W@Z`
- size: `392`
- prototype: `__int64 __fastcall(HKEY *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001d2f0`

## callees

- `0x180007158`
- `0x18000a0a0`
- `0x18000cc1c`
- `0x18000fcd0`
- `0x18001ce74`
- `0x18001ceb8`
- `0x18001d2a4`
- `0x18001d2f0`
- `0x18001d4c8`
- `0x18001e140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d31c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d31c`

## pseudocode

```c
__int64 __fastcall CRegistry::DeleteSubKeyTree(HKEY *this, const wchar_t *a2)
{
  int v4; // edx
  __int64 v5; // r9
  __int64 v6; // r8
  int v7; // r9d
  unsigned int v8; // ebx
  __int64 result; // rax
  unsigned int v10; // edx
  unsigned int v11; // [rsp+20h] [rbp-378h] BYREF
  _QWORD v12[2]; // [rsp+28h] [rbp-370h] BYREF
  int v13; // [rsp+38h] [rbp-360h]
  int v14; // [rsp+3Ch] [rbp-35Ch]
  _BYTE v15[16]; // [rsp+40h] [rbp-358h] BYREF
  void **v16; // [rsp+50h] [rbp-348h] BYREF
  wchar_t *v17; // [rsp+58h] [rbp-340h]
  wchar_t v18[36]; // [rsp+68h] [rbp-330h] BYREF
  _BYTE v19[192]; // [rsp+B0h] [rbp-2E8h] BYREF
  wchar_t v20[264]; // [rsp+170h] [rbp-228h] BYREF

  SetLastError(0);
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v14 = v5;
  v13 = v5;
  v12[1] = a2;
  v12[0] = &CConstString::`vftable';
  v6 = (unsigned int)CLMString::ReverseFindAnySlash((CLMString *)v12, v4) + 1;
  CLMString::Mid(v12, v15, v6, (unsigned int)(v7 - v6));
  CLMString::CLMString((CLMString *)&v16, 0x21u, v18, (const struct CLMSubStr *)v15);
  v16 = &TLMString<32,32,1024>::`vftable';
  v11 = 0;
  try
  {
    CRegistry::CRegistry((CRegistry *)v19, this, v17, 0xF003Fu);
    do
    {
      v11 = 260;
      if ( !CRegistry::EnumSubKey((CRegistry *)v19, v10, v20, &v11) )
      {
        CRegistry::~CRegistry((CRegistry *)v19);
        v8 = CRegistry::DeleteSubKey((CRegistry *)this, v17);
        TLMString<32,32,1024>::~TLMString<32,32,1024>(&v16);
        return v8;
      }
    }
    while ( (unsigned int)CRegistry::DeleteSubKeyTree((CRegistry *)v19, v20) );
    CRegistry::~CRegistry((CRegistry *)v19);
    TLMString<32,32,1024>::~TLMString<32,32,1024>(&v16);
    v12[0] = &CLMString::`vftable';
    result = 0;
  }
  catch ( ... )
  {
    TLMString<32,32,1024>::~TLMString<32,32,1024>(&v16);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001d2f0  mov     [rsp+arg_8], rbx
0x18001d2f5  mov     [rsp+arg_10], rsi
0x18001d2fa  push    rdi
0x18001d2fb  sub     rsp, 390h
0x18001d302  mov     rax, cs:__security_cookie
0x18001d309  xor     rax, rsp
0x18001d30c  mov     [rsp+398h+var_18], rax
0x18001d314  mov     rdi, rdx
0x18001d317  mov     rbx, rcx
0x18001d31a  xor     ecx, ecx; dwErrCode
0x18001d31c  call    cs:__imp_SetLastError
0x18001d322  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001d326  xor     esi, esi
0x18001d328  inc     r9
0x18001d32b  cmp     [rdi+r9*2], si
0x18001d330  jnz     short loc_18001D328
0x18001d332  mov     [rsp+398h+var_35C], r9d
0x18001d337  mov     [rsp+398h+var_360], r9d
0x18001d33c  mov     [rsp+398h+var_368], rdi
0x18001d341  lea     rax, ??_7CConstString@@6B@; const CConstString::`vftable'
0x18001d348  mov     [rsp+398h+var_370], rax
0x18001d34d  lea     rcx, [rsp+398h+var_370]; this
0x18001d352  call    ?ReverseFindAnySlash@CLMString@@QEBAHH@Z; CLMString::ReverseFindAnySlash(int)
0x18001d357  lea     r8d, [rax+1]
0x18001d35b  sub     r9d, r8d
0x18001d35e  lea     rdx, [rsp+398h+var_358]
0x18001d363  lea     rcx, [rsp+398h+var_370]
0x18001d368  call    ?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z; CLMString::Mid(uint,uint)
0x18001d36d  lea     r9, [rsp+398h+var_358]; struct CLMSubStr *
0x18001d372  lea     r8, [rsp+398h+var_330]; wchar_t *
0x18001d377  mov     edx, 21h ; '!'; unsigned int
0x18001d37c  lea     rcx, [rsp+398h+var_348]; this
0x18001d381  call    ??0CLMString@@IEAA@IPEA_WAEBVCLMSubStr@@@Z; CLMString::CLMString(uint,wchar_t *,CLMSubStr const &)
0x18001d386  lea     rax, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x18001d38d  mov     [rsp+398h+var_348], rax
0x18001d392  mov     [rsp+398h+var_378], esi
0x18001d396  mov     r9d, 0F003Fh; unsigned int
0x18001d39c  mov     r8, [rsp+398h+var_340]; wchar_t *
0x18001d3a1  mov     rdx, rbx; struct CRegistry *
0x18001d3a4  lea     rcx, [rsp+398h+var_2E8]; this
0x18001d3ac  call    ??0CRegistry@@QEAA@PEAV0@PEB_WK@Z; CRegistry::CRegistry(CRegistry *,wchar_t const *,ulong)
0x18001d3b1  nop
0x18001d3b2  mov     [rsp+398h+var_378], 104h
0x18001d3ba  lea     r9, [rsp+398h+var_378]; unsigned int *
0x18001d3bf  lea     r8, [rsp+398h+var_228]; wchar_t *
0x18001d3c7  lea     rcx, [rsp+398h+var_2E8]; this
0x18001d3cf  call    ?EnumSubKey@CRegistry@@QEAAHIPEA_WPEAK@Z; CRegistry::EnumSubKey(uint,wchar_t *,ulong *)
0x18001d3d4  test    eax, eax
0x18001d3d6  jnz     short loc_18001D404
0x18001d3d8  lea     rcx, [rsp+398h+var_2E8]; this
0x18001d3e0  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18001d3e5  nop
0x18001d3e6  mov     rdx, [rsp+398h+var_340]; wchar_t *
0x18001d3eb  mov     rcx, rbx; this
0x18001d3ee  call    ?DeleteSubKey@CRegistry@@QEAAHPEB_W@Z; CRegistry::DeleteSubKey(wchar_t const *)
0x18001d3f3  mov     ebx, eax
0x18001d3f5  lea     rcx, [rsp+398h+var_348]
0x18001d3fa  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x18001d3ff  nop
0x18001d400  mov     eax, ebx
0x18001d402  jmp     short loc_18001D453
0x18001d404  lea     rdx, [rsp+398h+var_228]; wchar_t *
0x18001d40c  lea     rcx, [rsp+398h+var_2E8]; this
0x18001d414  call    ?DeleteSubKeyTree@CRegistry@@UEAAHPEB_W@Z; CRegistry::DeleteSubKeyTree(wchar_t const *)
0x18001d419  test    eax, eax
0x18001d41b  jnz     short loc_18001D3B2
0x18001d41d  lea     rcx, [rsp+398h+var_2E8]; this
0x18001d425  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18001d42a  nop
0x18001d42b  lea     rcx, [rsp+398h+var_348]
0x18001d430  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x18001d435  nop
0x18001d436  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x18001d43d  mov     [rsp+398h+var_370], rax
0x18001d442  xor     eax, eax
0x18001d444  jmp     short loc_18001D453
0x18001d446  lea     rcx, [rsp+398h+var_348]
0x18001d44b  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x18001d450  nop
0x18001d451  xor     eax, eax
0x18001d453  mov     rcx, [rsp+398h+var_18]
0x18001d45b  xor     rcx, rsp; StackCookie
0x18001d45e  call    __security_check_cookie
0x18001d463  lea     r11, [rsp+398h+var_8]
0x18001d46b  mov     rbx, [r11+18h]
0x18001d46f  mov     rsi, [r11+20h]
0x18001d473  mov     rsp, r11
0x18001d476  pop     rdi
0x18001d477  retn
```
