# CRegistry::DeleteSubKeyTree(wchar_t const *)

- ea: `0x180036190`
- end: `0x180036318`
- name: `?DeleteSubKeyTree@CRegistry@@UEAAHPEB_W@Z`
- size: `392`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180036190`

## callees

- `0x180001da0`
- `0x180006270`
- `0x18001675c`
- `0x180035e20`
- `0x180035f0c`
- `0x180036144`
- `0x180036190`
- `0x180036368`
- `0x180036a24`
- `0x180036b18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800361bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800361bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRegistry::DeleteSubKeyTree(CRegistry *this, const wchar_t *a2)
{
  int v4; // edx
  __int64 v5; // r9
  unsigned int v6; // r8d
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
  v6 = CLMString::ReverseFindAnySlash((CLMString *)v12, v4) + 1;
  CLMString::Mid((__int64)v12, (__int64)v15, v6, v7 - v6);
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
        v8 = CRegistry::DeleteSubKey(this, v17);
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
0x180036190  mov     [rsp+arg_8], rbx
0x180036195  mov     [rsp+arg_10], rsi
0x18003619a  push    rdi
0x18003619b  sub     rsp, 390h
0x1800361a2  mov     rax, cs:__security_cookie
0x1800361a9  xor     rax, rsp
0x1800361ac  mov     [rsp+398h+var_18], rax
0x1800361b4  mov     rdi, rdx
0x1800361b7  mov     rbx, rcx
0x1800361ba  xor     ecx, ecx; dwErrCode
0x1800361bc  call    cs:__imp_SetLastError
0x1800361c2  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800361c6  xor     esi, esi
0x1800361c8  inc     r9
0x1800361cb  cmp     [rdi+r9*2], si
0x1800361d0  jnz     short loc_1800361C8
0x1800361d2  mov     [rsp+398h+var_35C], r9d
0x1800361d7  mov     [rsp+398h+var_360], r9d
0x1800361dc  mov     [rsp+398h+var_368], rdi
0x1800361e1  lea     rax, ??_7CConstString@@6B@; const CConstString::`vftable'
0x1800361e8  mov     [rsp+398h+var_370], rax
0x1800361ed  lea     rcx, [rsp+398h+var_370]; this
0x1800361f2  call    ?ReverseFindAnySlash@CLMString@@QEBAHH@Z; CLMString::ReverseFindAnySlash(int)
0x1800361f7  lea     r8d, [rax+1]
0x1800361fb  sub     r9d, r8d
0x1800361fe  lea     rdx, [rsp+398h+var_358]
0x180036203  lea     rcx, [rsp+398h+var_370]
0x180036208  call    ?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z; CLMString::Mid(uint,uint)
0x18003620d  lea     r9, [rsp+398h+var_358]; struct CLMSubStr *
0x180036212  lea     r8, [rsp+398h+var_330]; wchar_t *
0x180036217  mov     edx, 21h ; '!'; unsigned int
0x18003621c  lea     rcx, [rsp+398h+var_348]; this
0x180036221  call    ??0CLMString@@IEAA@IPEA_WAEBVCLMSubStr@@@Z; CLMString::CLMString(uint,wchar_t *,CLMSubStr const &)
0x180036226  lea     rax, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x18003622d  mov     [rsp+398h+var_348], rax
0x180036232  mov     [rsp+398h+var_378], esi
0x180036236  mov     r9d, 0F003Fh; unsigned int
0x18003623c  mov     r8, [rsp+398h+var_340]; wchar_t *
0x180036241  mov     rdx, rbx; struct CRegistry *
0x180036244  lea     rcx, [rsp+398h+var_2E8]; this
0x18003624c  call    ??0CRegistry@@QEAA@PEAV0@PEB_WK@Z; CRegistry::CRegistry(CRegistry *,wchar_t const *,ulong)
0x180036251  nop
0x180036252  mov     [rsp+398h+var_378], 104h
0x18003625a  lea     r9, [rsp+398h+var_378]; unsigned int *
0x18003625f  lea     r8, [rsp+398h+var_228]; wchar_t *
0x180036267  lea     rcx, [rsp+398h+var_2E8]; this
0x18003626f  call    ?EnumSubKey@CRegistry@@QEAAHIPEA_WPEAK@Z; CRegistry::EnumSubKey(uint,wchar_t *,ulong *)
0x180036274  test    eax, eax
0x180036276  jnz     short loc_1800362A4
0x180036278  lea     rcx, [rsp+398h+var_2E8]; this
0x180036280  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180036285  nop
0x180036286  mov     rdx, [rsp+398h+var_340]; wchar_t *
0x18003628b  mov     rcx, rbx; this
0x18003628e  call    ?DeleteSubKey@CRegistry@@QEAAHPEB_W@Z; CRegistry::DeleteSubKey(wchar_t const *)
0x180036293  mov     ebx, eax
0x180036295  lea     rcx, [rsp+398h+var_348]
0x18003629a  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x18003629f  nop
0x1800362a0  mov     eax, ebx
0x1800362a2  jmp     short loc_1800362F3
0x1800362a4  lea     rdx, [rsp+398h+var_228]; wchar_t *
0x1800362ac  lea     rcx, [rsp+398h+var_2E8]; this
0x1800362b4  call    ?DeleteSubKeyTree@CRegistry@@UEAAHPEB_W@Z; CRegistry::DeleteSubKeyTree(wchar_t const *)
0x1800362b9  test    eax, eax
0x1800362bb  jnz     short loc_180036252
0x1800362bd  lea     rcx, [rsp+398h+var_2E8]; this
0x1800362c5  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800362ca  nop
0x1800362cb  lea     rcx, [rsp+398h+var_348]
0x1800362d0  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x1800362d5  nop
0x1800362d6  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x1800362dd  mov     [rsp+398h+var_370], rax
0x1800362e2  xor     eax, eax
0x1800362e4  jmp     short loc_1800362F3
0x1800362e6  lea     rcx, [rsp+398h+var_348]
0x1800362eb  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x1800362f0  nop
0x1800362f1  xor     eax, eax
0x1800362f3  mov     rcx, [rsp+398h+var_18]
0x1800362fb  xor     rcx, rsp; StackCookie
0x1800362fe  call    __security_check_cookie
0x180036303  lea     r11, [rsp+398h+var_8]
0x18003630b  mov     rbx, [r11+18h]
0x18003630f  mov     rsi, [r11+20h]
0x180036313  mov     rsp, r11
0x180036316  pop     rdi
0x180036317  retn
```
