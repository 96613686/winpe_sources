# helium::CreateLookasideRegistryValue(HKEY__ *,DESKTOP_APPX_REGKEYANDVALUE const &,TokenMap &)

- ea: `0x180011f2c`
- end: `0x180012178`
- name: `?CreateLookasideRegistryValue@helium@@YAXPEAUHKEY__@@AEBUDESKTOP_APPX_REGKEYANDVALUE@@AEAVTokenMap@@@Z`
- size: `588`
- prototype: `void __fastcall(helium *__hidden this, HKEY, const struct DESKTOP_APPX_REGKEYANDVALUE *, struct TokenMap *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011b84`

## callees

- `0x1800053a0`
- `0x180011300`
- `0x180011820`
- `0x180011b04`
- `0x180011f2c`
- `0x180013048`
- `0x18004f2d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800120aa`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800120aa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001202d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001205f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012091`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001202d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001205f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012091`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall helium::CreateLookasideRegistryValue(
        helium *this,
        _QWORD *a2,
        const struct DESKTOP_APPX_REGKEYANDVALUE *a3,
        struct TokenMap *a4)
{
  void *v7; // rdx
  const WCHAR *v8; // rsi
  __int64 v9; // rbx
  __int64 v10; // r9
  unsigned int v11; // edi
  __int64 v12; // r9
  __int64 v13; // rdx
  WCHAR *v14; // r9
  int v15; // [rsp+30h] [rbp-59h] BYREF
  WCHAR v16[16]; // [rsp+38h] [rbp-51h] BYREF
  _OWORD v17[2]; // [rsp+58h] [rbp-31h] BYREF
  WCHAR String1[8]; // [rsp+78h] [rbp-11h] BYREF
  WCHAR v19[12]; // [rsp+88h] [rbp-1h] BYREF

  v17[0] = 0;
  v17[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v17[0]) = 0;
  v7 = (void *)a2[1];
  if ( v7 )
  {
    std::wstring::operator=(v17, v7);
    TokenMap::DetokenizeString(a3, v17, 0);
  }
  v8 = (const WCHAR *)a2[3];
  wcscpy(String1, L"REG_SZ");
  wcscpy(v16, L"REG_EXPAND_SZ");
  wcscpy(v19, L"REG_DWORD");
  v9 = -1;
  if ( !v8 || !*v8 )
  {
    v11 = 1;
LABEL_16:
    v13 = a2[2];
    memset(v16, 0, sizeof(v16));
    do
      ++v9;
    while ( *(_WORD *)(v13 + 2 * v9) );
    std::wstring::_Construct<1,unsigned short const *>(v16, v13, v9);
    TokenMap::DetokenizeString(a3, v16, 0);
    v14 = v16;
    if ( *(_QWORD *)&v16[12] > 7u )
      v14 = *(WCHAR **)v16;
    helium::SetLookasideRegistryValue(this, v17, v11, v14, 2 * (*(_DWORD *)&v16[8] + 1));
    std::wstring::~wstring(v16);
    goto LABEL_21;
  }
  v10 = -1;
  do
    ++v10;
  while ( v8[v10] );
  v11 = 1;
  if ( CompareStringOrdinal(String1, 6, v8, v10, 1) == 2 )
    goto LABEL_16;
  v12 = -1;
  do
    ++v12;
  while ( v8[v12] );
  if ( CompareStringOrdinal(v16, 13, v8, v12, 1) == 2 )
  {
    v11 = 2;
    goto LABEL_16;
  }
  do
    ++v9;
  while ( v8[v9] );
  if ( CompareStringOrdinal(v19, 9, v8, v9, 1) == 2 )
  {
    v15 = _o__wtoi(a2[2]);
    helium::SetLookasideRegistryValue(this, v17, 4, &v15, 4);
  }
LABEL_21:
  std::wstring::~wstring(v17);
}

```

## disassembly

```asm
0x180011f2c  mov     [rsp-8+arg_18], rbx
0x180011f31  push    rbp
0x180011f32  push    rsi
0x180011f33  push    rdi
0x180011f34  push    r12
0x180011f36  push    r13
0x180011f38  push    r14
0x180011f3a  push    r15
0x180011f3c  lea     rbp, [rsp-27h]
0x180011f41  sub     rsp, 0B0h
0x180011f48  mov     rax, cs:__security_cookie
0x180011f4f  xor     rax, rsp
0x180011f52  mov     [rbp+57h+var_40], rax
0x180011f56  mov     r15, r8
0x180011f59  mov     r14, rdx
0x180011f5c  mov     r12, rcx
0x180011f5f  xorps   xmm0, xmm0
0x180011f62  movups  [rbp+57h+var_88], xmm0
0x180011f66  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180011f6e  movdqu  [rbp+57h+var_78], xmm1
0x180011f73  xor     r13d, r13d
0x180011f76  mov     word ptr [rbp+57h+var_88], r13w
0x180011f7b  mov     rdx, [rdx+8]; Src
0x180011f7f  test    rdx, rdx
0x180011f82  jz      short loc_180011F9C
0x180011f84  lea     rcx, [rbp+57h+var_88]; void *
0x180011f88  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x180011f8d  xor     r8d, r8d
0x180011f90  lea     rdx, [rbp+57h+var_88]
0x180011f94  mov     rcx, r15
0x180011f97  call    ?DetokenizeString@TokenMap@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; TokenMap::DetokenizeString(std::wstring &,bool)
0x180011f9c  mov     rsi, [r14+18h]
0x180011fa0  movsd   xmm0, qword ptr cs:aRegSz; "REG_SZ"
0x180011fa8  movsd   qword ptr [rbp+57h+String1], xmm0
0x180011fad  mov     eax, dword ptr cs:aRegSz+8; "SZ"
0x180011fb3  mov     [rbp+57h+var_60], eax
0x180011fb6  movzx   eax, word ptr cs:aRegSz+0Ch; ""
0x180011fbd  mov     [rbp+57h+var_5C], ax
0x180011fc1  movups  xmm0, xmmword ptr cs:aRegExpandSz; "REG_EXPAND_SZ"
0x180011fc8  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x180011fcc  movsd   xmm0, qword ptr cs:aRegExpandSz+10h; "ND_SZ"
0x180011fd4  movsd   qword ptr [rbp+57h+var_98], xmm0
0x180011fd9  mov     eax, dword ptr cs:aRegExpandSz+18h; "Z"
0x180011fdf  mov     dword ptr [rbp+57h+var_98+8], eax
0x180011fe2  movups  xmm0, xmmword ptr cs:aRegDword; "REG_DWORD"
0x180011fe9  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180011fed  mov     eax, dword ptr cs:aRegDword+10h; "D"
0x180011ff3  mov     [rbp+57h+var_48], eax
0x180011ff6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011ffa  test    rsi, rsi
0x180011ffd  jz      loc_1800120D6
0x180012003  cmp     [rsi], r13w
0x180012007  jz      loc_1800120D6
0x18001200d  mov     r9, rbx
0x180012010  inc     r9; cchCount2
0x180012013  cmp     [rsi+r9*2], r13w
0x180012018  jnz     short loc_180012010
0x18001201a  mov     edi, 1
0x18001201f  mov     [rsp+0E0h+bIgnoreCase], edi; bIgnoreCase
0x180012023  mov     r8, rsi; lpString2
0x180012026  lea     edx, [rdi+5]; cchCount1
0x180012029  lea     rcx, [rbp+57h+String1]; lpString1
0x18001202d  call    cs:__imp_CompareStringOrdinal
0x180012034  nop     dword ptr [rax+rax+00h]
0x180012039  cmp     eax, 2
0x18001203c  jz      loc_1800120DB
0x180012042  mov     r9, rbx
0x180012045  inc     r9; cchCount2
0x180012048  cmp     [rsi+r9*2], r13w
0x18001204d  jnz     short loc_180012045
0x18001204f  mov     [rsp+0E0h+bIgnoreCase], edi; bIgnoreCase
0x180012053  mov     r8, rsi; lpString2
0x180012056  mov     edx, 0Dh; cchCount1
0x18001205b  lea     rcx, [rbp+57h+var_A8]; lpString1
0x18001205f  call    cs:__imp_CompareStringOrdinal
0x180012066  nop     dword ptr [rax+rax+00h]
0x18001206b  cmp     eax, 2
0x18001206e  jnz     short loc_180012074
0x180012070  mov     edi, eax
0x180012072  jmp     short loc_1800120DB
0x180012074  inc     rbx
0x180012077  cmp     [rsi+rbx*2], r13w
0x18001207c  jnz     short loc_180012074
0x18001207e  mov     r9, rbx; cchCount2
0x180012081  mov     [rsp+0E0h+bIgnoreCase], edi; bIgnoreCase
0x180012085  mov     r8, rsi; lpString2
0x180012088  mov     edx, 9; cchCount1
0x18001208d  lea     rcx, [rbp+57h+var_58]; lpString1
0x180012091  call    cs:__imp_CompareStringOrdinal
0x180012098  nop     dword ptr [rax+rax+00h]
0x18001209d  cmp     eax, 2
0x1800120a0  jnz     loc_180012147
0x1800120a6  mov     rcx, [r14+10h]
0x1800120aa  call    cs:__imp__o__wtoi
0x1800120b1  nop     dword ptr [rax+rax+00h]
0x1800120b6  mov     [rbp+57h+var_B0], eax
0x1800120b9  mov     r8d, 4
0x1800120bf  mov     [rsp+0E0h+bIgnoreCase], r8d
0x1800120c4  lea     r9, [rbp+57h+var_B0]
0x1800120c8  lea     rdx, [rbp+57h+var_88]
0x1800120cc  mov     rcx, r12
0x1800120cf  call    ?SetLookasideRegistryValue@helium@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEBEK@Z; helium::SetLookasideRegistryValue(HKEY__ *,std::wstring const &,ulong,uchar const *,ulong)
0x1800120d4  jmp     short loc_180012147
0x1800120d6  mov     edi, 1
0x1800120db  mov     rdx, [r14+10h]
0x1800120df  xorps   xmm0, xmm0
0x1800120e2  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x1800120e6  xorps   xmm1, xmm1
0x1800120e9  movdqu  [rbp+57h+var_98], xmm1
0x1800120ee  inc     rbx
0x1800120f1  cmp     [rdx+rbx*2], r13w
0x1800120f6  jnz     short loc_1800120EE
0x1800120f8  mov     r8, rbx
0x1800120fb  lea     rcx, [rbp+57h+var_A8]
0x1800120ff  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180012104  nop
0x180012105  xor     r8d, r8d
0x180012108  lea     rdx, [rbp+57h+var_A8]
0x18001210c  mov     rcx, r15
0x18001210f  call    ?DetokenizeString@TokenMap@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; TokenMap::DetokenizeString(std::wstring &,bool)
0x180012114  lea     r9, [rbp+57h+var_A8]
0x180012118  cmp     qword ptr [rbp+57h+var_98+8], 7
0x18001211d  cmova   r9, qword ptr [rbp+57h+var_A8]
0x180012122  mov     eax, dword ptr [rbp+57h+var_98]
0x180012125  inc     eax
0x180012127  add     eax, eax
0x180012129  mov     [rsp+0E0h+bIgnoreCase], eax
0x18001212d  mov     r8d, edi
0x180012130  lea     rdx, [rbp+57h+var_88]
0x180012134  mov     rcx, r12
0x180012137  call    ?SetLookasideRegistryValue@helium@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEBEK@Z; helium::SetLookasideRegistryValue(HKEY__ *,std::wstring const &,ulong,uchar const *,ulong)
0x18001213c  nop
0x18001213d  lea     rcx, [rbp+57h+var_A8]; void *
0x180012141  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012146  nop
0x180012147  lea     rcx, [rbp+57h+var_88]; void *
0x18001214b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012150  mov     rcx, [rbp+57h+var_40]
0x180012154  xor     rcx, rsp; StackCookie
0x180012157  call    __security_check_cookie
0x18001215c  mov     rbx, [rsp+0E0h+arg_18]
0x180012164  add     rsp, 0B0h
0x18001216b  pop     r15
0x18001216d  pop     r14
0x18001216f  pop     r13
0x180012171  pop     r12
0x180012173  pop     rdi
0x180012174  pop     rsi
0x180012175  pop     rbp
0x180012176  retn
```
