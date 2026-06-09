# CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)

- ea: `0x180038474`
- end: `0x18003864b`
- name: `?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z`
- size: `471`
- prototype: `int(CSearchRegistryRedirectHelper *__hidden this, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800027a0`
- `0x180002e20`
- `0x180004bf0`

## callees

- `0x180003df0`
- `0x180004080`
- `0x180006270`
- `0x180011374`
- `0x180018098`
- `0x180038474`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800384df`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800385b6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800384df`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800385b6`

## string_xrefs

- `0x180038511`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`
- `0x18003854d`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`

## pseudocode

```c
__int64 __fastcall CSearchRegistryRedirectHelper::MapRegistryKeyPath(
        const wchar_t *this,
        const wchar_t *a2,
        wchar_t *a3)
{
  __int64 v3; // rdi
  const WCHAR *v5; // rbx
  __int64 v6; // r8
  __int64 v8; // rsi
  __int64 v9; // rbp
  int v10; // eax
  unsigned __int64 v11; // r10
  unsigned int v12; // edi
  int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // esi
  __int64 v17; // rdx
  const WCHAR *v18; // r8
  __int64 v19; // r8
  int v20; // edi
  int bIgnoreCase; // [rsp+20h] [rbp-78h]
  LPCWCH lpString2[3]; // [rsp+30h] [rbp-68h] BYREF
  int v23; // [rsp+48h] [rbp-50h]
  int v24; // [rsp+4Ch] [rbp-4Ch]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v3 = -1;
  v5 = a2;
  v6 = 69LL * *(_QWORD *)this;
  v8 = -1;
  v9 = LODWORD(off_180053580[v6 + 2]);
  do
    ++v8;
  while ( a2[v8] );
  if ( (unsigned int)v8 >= (unsigned int)v9 && CompareStringOrdinal(a2, v9, off_180053580[v6 + 1], -1, 1) == 2 )
  {
    v10 = StringCchCopyW(a3, 0x104u, this + 4);
    v12 = v10;
    if ( v10 >= 0 )
    {
      if ( (unsigned int)v8 <= (unsigned int)v9 )
        return 0;
      v14 = StringCchCatW(a3, v11, &v5[v9]);
      v15 = v14;
      if ( v14 >= 0 )
      {
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x49,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
          (const char *)(unsigned int)v14,
          bIgnoreCase);
        return v15;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
        (const char *)(unsigned int)v10,
        bIgnoreCase);
      return v12;
    }
  }
  else
  {
    v16 = 0;
    lpString2[0] = L"Software";
    lpString2[1] = L"System";
    while ( v16 < 2 )
    {
      v17 = -1;
      v18 = lpString2[v16];
      do
        ++v17;
      while ( v18[v17] );
      if ( CompareStringOrdinal(v5, v17, v18, -1, 1) == 2 )
      {
        if ( (byte_180054482 & 0x20) != 0 )
        {
          if ( v5 )
          {
            do
              ++v3;
            while ( v5[v3] );
            v20 = 2 * v3 + 2;
          }
          else
          {
            v20 = 10;
          }
          v23 = v20;
          v24 = 0;
          if ( !v5 )
            v5 = L"NULL";
          lpString2[2] = v5;
          McGenEventWrite_EventWriteTransfer(
            Microsoft_Windows_Search_Core_Context,
            MSSearchTraceId_ETWLogging,
            v19,
            2,
            lpString2);
        }
        return 2147500037LL;
      }
      ++v16;
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180038474  push    rbx
0x180038476  push    rbp
0x180038477  push    rsi
0x180038478  push    rdi
0x180038479  push    r12
0x18003847b  push    r14
0x18003847d  push    r15
0x18003847f  sub     rsp, 60h
0x180038483  mov     rax, cs:__security_cookie
0x18003848a  xor     rax, rsp
0x18003848d  mov     [rsp+98h+var_48], rax
0x180038492  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180038496  lea     rax, off_180053580; "WSearch"
0x18003849d  mov     r14, r8
0x1800384a0  mov     rbx, rdx
0x1800384a3  imul    r8, [rcx], 228h
0x1800384aa  mov     r15, rcx
0x1800384ad  mov     rsi, rdi
0x1800384b0  xor     r12d, r12d
0x1800384b3  mov     ebp, [r8+rax+10h]
0x1800384b8  inc     rsi
0x1800384bb  cmp     [rdx+rsi*2], r12w
0x1800384c0  jnz     short loc_1800384B8
0x1800384c2  cmp     esi, ebp
0x1800384c4  jb      loc_18003856F
0x1800384ca  mov     r8, [r8+rax+8]; lpString2
0x1800384cf  mov     r9d, edi; cchCount2
0x1800384d2  mov     edx, ebp; cchCount1
0x1800384d4  mov     [rsp+98h+bIgnoreCase], 1; int
0x1800384dc  mov     rcx, rbx; lpString1
0x1800384df  call    cs:__imp_CompareStringOrdinal
0x1800384e5  cmp     eax, 2
0x1800384e8  jnz     loc_18003856F
0x1800384ee  mov     r10d, 104h
0x1800384f4  lea     r8, [r15+8]; wchar_t *
0x1800384f8  mov     edx, r10d; unsigned __int64
0x1800384fb  mov     rcx, r14; wchar_t *
0x1800384fe  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180038503  mov     edi, eax
0x180038505  test    eax, eax
0x180038507  jns     short loc_18003852C
0x180038509  mov     rcx, [rsp+98h]; this
0x180038511  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\com"...
0x180038518  mov     r9d, eax; char *
0x18003851b  mov     edx, 46h ; 'F'; void *
0x180038520  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038525  mov     eax, edi
0x180038527  jmp     loc_18003862F
0x18003852c  cmp     esi, ebp
0x18003852e  jbe     short loc_180038568
0x180038530  lea     r8, [rbx+rbp*2]; wchar_t *
0x180038534  mov     rdx, r10; unsigned __int64
0x180038537  mov     rcx, r14; wchar_t *
0x18003853a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003853f  mov     ebx, eax
0x180038541  test    eax, eax
0x180038543  jns     short loc_180038568
0x180038545  mov     rcx, [rsp+98h]; this
0x18003854d  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\com"...
0x180038554  mov     r9d, eax; char *
0x180038557  mov     edx, 49h ; 'I'; void *
0x18003855c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038561  mov     eax, ebx
0x180038563  jmp     loc_18003862F
0x180038568  xor     eax, eax
0x18003856a  jmp     loc_18003862F
0x18003856f  lea     rax, aSoftware; "Software"
0x180038576  mov     esi, r12d
0x180038579  mov     [rsp+98h+lpString2], rax
0x18003857e  lea     rax, aSystem_0; "System"
0x180038585  mov     [rsp+98h+var_60], rax
0x18003858a  cmp     esi, 2
0x18003858d  jnb     loc_18003862A
0x180038593  movsxd  rax, esi
0x180038596  mov     rdx, rdi
0x180038599  mov     r8, [rsp+rax*8+98h+lpString2]; lpString2
0x18003859e  inc     rdx; cchCount1
0x1800385a1  cmp     [r8+rdx*2], r12w
0x1800385a6  jnz     short loc_18003859E
0x1800385a8  mov     r9d, edi; cchCount2
0x1800385ab  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x1800385b3  mov     rcx, rbx; lpString1
0x1800385b6  call    cs:__imp_CompareStringOrdinal
0x1800385bc  cmp     eax, 2
0x1800385bf  jz      short loc_1800385C5
0x1800385c1  inc     esi
0x1800385c3  jmp     short loc_18003858A
0x1800385c5  test    cs:byte_180054482, 20h
0x1800385cc  jz      short loc_18003862A
0x1800385ce  test    rbx, rbx
0x1800385d1  jz      short loc_1800385E6
0x1800385d3  inc     rdi
0x1800385d6  cmp     [rbx+rdi*2], r12w
0x1800385db  jnz     short loc_1800385D3
0x1800385dd  lea     edi, ds:2[rdi*2]
0x1800385e4  jmp     short loc_1800385EB
0x1800385e6  mov     edi, 0Ah
0x1800385eb  test    rbx, rbx
0x1800385ee  mov     [rsp+98h+var_50], edi
0x1800385f2  lea     rax, aNull; "NULL"
0x1800385f9  mov     [rsp+98h+var_4C], r12d
0x1800385fe  cmovz   rbx, rax
0x180038602  lea     rdx, MSSearchTraceId_ETWLogging
0x180038609  lea     rax, [rsp+98h+lpString2]
0x18003860e  mov     [rsp+98h+var_58], rbx
0x180038613  mov     r9d, 2
0x180038619  mov     qword ptr [rsp+98h+bIgnoreCase], rax
0x18003861e  lea     rcx, Microsoft_Windows_Search_Core_Context
0x180038625  call    McGenEventWrite_EventWriteTransfer
0x18003862a  mov     eax, 80004005h
0x18003862f  mov     rcx, [rsp+98h+var_48]
0x180038634  xor     rcx, rsp; StackCookie
0x180038637  call    __security_check_cookie
0x18003863c  add     rsp, 60h
0x180038640  pop     r15
0x180038642  pop     r14
0x180038644  pop     r12
0x180038646  pop     rdi
0x180038647  pop     rsi
0x180038648  pop     rbp
0x180038649  pop     rbx
0x18003864a  retn
```
