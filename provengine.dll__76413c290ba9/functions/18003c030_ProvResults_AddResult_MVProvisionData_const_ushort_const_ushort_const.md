# ProvResults::AddResult(_MVProvisionData const &,ushort const *,ushort const *)

- ea: `0x18003c030`
- end: `0x18003c432`
- name: `?AddResult@ProvResults@@QEBAXAEBU_MVProvisionData@@PEBG1@Z`
- size: `1026`
- prototype: `void __fastcall(HKEY *this, const struct _MVProvisionData *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180012eb4`

## callees

- `0x180002e70`
- `0x180021cf4`
- `0x18002f9bc`
- `0x18003c030`
- `0x18003cc98`
- `0x18003d0dc`
- `0x18004371a`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003c36a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003c36a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c339`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c348`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c339`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c348`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c1cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c204`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c323`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c1cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c204`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c323`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c358`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c358`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c0bc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c0bc`

## pseudocode

```c
void __fastcall ProvResults::AddResult(
        HKEY *this,
        const struct _MVProvisionData *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const WCHAR *v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // rax
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // rbx
  BYTE *v12; // rax
  BYTE *v13; // rdi
  unsigned __int64 v14; // rcx
  __int64 v15; // rax
  unsigned __int16 v16; // ax
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rax
  __int64 v19; // r9
  unsigned int v20; // eax
  unsigned int v21; // eax
  __int64 v22; // rax
  unsigned __int64 v23; // r14
  unsigned __int64 v24; // rsi
  BYTE *v25; // rax
  BYTE *v26; // rbx
  unsigned __int64 v27; // rdx
  __int64 v28; // rax
  unsigned __int16 v29; // ax
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rax
  __int64 v32; // r9
  unsigned int v33; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-69h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-69h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-69h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-69h]
  HKEY hKey; // [rsp+50h] [rbp-39h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-31h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-2Dh] BYREF
  BYTE *v41; // [rsp+60h] [rbp-29h]
  BYTE *v42; // [rsp+68h] [rbp-21h]
  LPCWSTR lpSubKey[3]; // [rsp+78h] [rbp-11h] BYREF
  unsigned __int64 v44; // [rsp+90h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  ProvResults::LazyCreateParentKey((ProvResults *)this);
  ProvResults::GetChildKeyNameFromProvData(lpSubKey);
  dwDisposition = 0;
  hKey = 0;
  v7 = (const WCHAR *)lpSubKey;
  if ( v44 >= 8 )
    v7 = lpSubKey[0];
  v8 = RegCreateKeyExW(this[9], v7, 0, 0, 0, 3u, 0, &hKey, &dwDisposition);
  if ( v8 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x82,
      (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v8,
      dwOptions);
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  v10 = v9 + 2;
  v42 = 0;
  v11 = saturated_mul(v9 + 2, 2u);
  v12 = (BYTE *)operator new[](v11);
  v13 = v12;
  if ( v12 )
    memset_0(v12, 0, v11);
  else
    v13 = 0;
  v42 = v13;
  v14 = 0;
  v15 = -1;
  do
    ++v15;
  while ( a3[v15] );
  if ( v15 )
  {
    do
    {
      v16 = 0;
      if ( a3[v14] != 47 )
        v16 = a3[v14];
      *(_WORD *)&v13[2 * v14++] = v16;
      v17 = -1;
      do
        ++v17;
      while ( a3[v17] );
    }
    while ( v14 < v17 );
  }
  v41 = 0;
  v18 = 2 * v10;
  if ( is_mul_ok(v10, 2u) )
  {
    v19 = 0;
  }
  else
  {
    v18 = -1;
    v19 = 2147942934LL;
  }
  if ( (int)v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v19,
      dwOptions);
  if ( v18 > 0xFFFFFFFF )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      v18 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
      dwOptions);
  v20 = RegSetValueExW(hKey, L"Categories", 0, 7u, v13, v18);
  if ( v20 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x94,
      (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v20,
      dwOptionsa);
  *(_DWORD *)Data = 1;
  v21 = RegSetValueExW(hKey, L"State", 0, 4u, Data, 4u);
  if ( v21 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x99,
      (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v21,
      dwOptionsb);
  if ( a4 )
  {
    v22 = -1;
    do
      ++v22;
    while ( a4[v22] );
    if ( v22 )
    {
      v23 = v22 + 2;
      v41 = 0;
      v24 = saturated_mul(v22 + 2, 2u);
      v25 = (BYTE *)operator new[](v24);
      v26 = v25;
      if ( v25 )
        memset_0(v25, 0, v24);
      else
        v26 = 0;
      v41 = v26;
      v27 = 0;
      v28 = -1;
      do
        ++v28;
      while ( a4[v28] );
      if ( v28 )
      {
        do
        {
          v29 = 0;
          if ( a4[v27] != 47 )
            v29 = a4[v27];
          *(_WORD *)&v26[2 * v27++] = v29;
          v30 = -1;
          do
            ++v30;
          while ( a4[v30] );
        }
        while ( v27 < v30 );
      }
      v31 = 2 * v23;
      if ( is_mul_ok(v23, 2u) )
      {
        v32 = 0;
      }
      else
      {
        v31 = -1;
        v32 = 2147942934LL;
      }
      if ( (int)v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA8,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
          (const char *)v32,
          dwOptionsb);
      if ( v31 > 0xFFFFFFFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA9,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
          v31 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
          dwOptionsb);
      v33 = RegSetValueExW(hKey, L"UserNamedChildNodes", 0, 7u, v26, v31);
      if ( v33 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0xAD,
          (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
          (const char *)v33,
          dwOptionsc);
      if ( v26 )
        operator delete[](v26);
    }
  }
  if ( v13 )
    operator delete[](v13);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v44 >= 8 )
    operator delete((void *)lpSubKey[0]);
}

```

## disassembly

```asm
0x18003c030  push    rbp
0x18003c032  push    rbx
0x18003c033  push    rsi
0x18003c034  push    rdi
0x18003c035  push    r12
0x18003c037  push    r13
0x18003c039  push    r14
0x18003c03b  push    r15
0x18003c03d  lea     rbp, [rsp-1Fh]
0x18003c042  sub     rsp, 0A8h
0x18003c049  mov     rax, cs:__security_cookie
0x18003c050  xor     rax, rsp
0x18003c053  mov     [rbp+57h+var_48], rax
0x18003c057  mov     r15, r9
0x18003c05a  mov     rsi, r8
0x18003c05d  mov     rbx, rdx
0x18003c060  mov     rdi, rcx
0x18003c063  call    ?LazyCreateParentKey@ProvResults@@AEBAXXZ; ProvResults::LazyCreateParentKey(void)
0x18003c068  mov     rdx, rbx
0x18003c06b  lea     rcx, [rbp+57h+lpSubKey]; void *
0x18003c06f  call    ?GetChildKeyNameFromProvData@ProvResults@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_MVProvisionData@@@Z; ProvResults::GetChildKeyNameFromProvData(_MVProvisionData const &)
0x18003c074  nop
0x18003c075  xor     r12d, r12d
0x18003c078  mov     [rbp+57h+dwDisposition], r12d
0x18003c07c  mov     [rbp+57h+hKey], r12
0x18003c080  lea     rdx, [rbp+57h+lpSubKey]
0x18003c084  cmp     [rbp+57h+var_50], 8
0x18003c089  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18003c08e  lea     rax, [rbp+57h+dwDisposition]
0x18003c092  mov     [rsp+0E0h+lpdwDisposition], rax; lpdwDisposition
0x18003c097  lea     rax, [rbp+57h+hKey]
0x18003c09b  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18003c0a0  mov     [rsp+0E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18003c0a5  mov     [rsp+0E0h+samDesired], 3; samDesired
0x18003c0ad  mov     [rsp+0E0h+dwOptions], r12d; int
0x18003c0b2  xor     r9d, r9d; lpClass
0x18003c0b5  xor     r8d, r8d; Reserved
0x18003c0b8  mov     rcx, [rdi+48h]; hKey
0x18003c0bc  call    cs:__imp_RegCreateKeyExW
0x18003c0c2  mov     rcx, [rbp+5Fh]; this
0x18003c0c6  test    eax, eax
0x18003c0c8  jnz     loc_18003C3A5
0x18003c0ce  or      r13, 0FFFFFFFFFFFFFFFFh
0x18003c0d2  mov     rax, r13
0x18003c0d5  inc     rax
0x18003c0d8  cmp     [rsi+rax*2], r12w
0x18003c0dd  jnz     short loc_18003C0D5
0x18003c0df  lea     r14, [rax+2]
0x18003c0e3  mov     [rbp+57h+var_78], r12
0x18003c0e7  mov     eax, 2
0x18003c0ec  mul     r14
0x18003c0ef  mov     rbx, rax
0x18003c0f2  cmovb   rbx, r13
0x18003c0f6  mov     rcx, rbx; unsigned __int64
0x18003c0f9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003c0fe  mov     rdi, rax
0x18003c101  test    rax, rax
0x18003c104  jz      short loc_18003C115
0x18003c106  mov     r8, rbx; Size
0x18003c109  xor     edx, edx; Val
0x18003c10b  mov     rcx, rax; void *
0x18003c10e  call    memset_0
0x18003c113  jmp     short loc_18003C118
0x18003c115  mov     rdi, r12
0x18003c118  mov     [rbp+57h+var_78], rdi
0x18003c11c  mov     rcx, r12
0x18003c11f  mov     rax, r13
0x18003c122  inc     rax
0x18003c125  cmp     [rsi+rax*2], r12w
0x18003c12a  jnz     short loc_18003C122
0x18003c12c  test    rax, rax
0x18003c12f  jz      short loc_18003C157
0x18003c131  mov     eax, r12d
0x18003c134  cmp     word ptr [rsi+rcx*2], 2Fh ; '/'
0x18003c139  cmovnz  ax, [rsi+rcx*2]
0x18003c13e  mov     [rdi+rcx*2], ax
0x18003c142  inc     rcx
0x18003c145  mov     rax, r13
0x18003c148  inc     rax
0x18003c14b  cmp     [rsi+rax*2], r12w
0x18003c150  jnz     short loc_18003C148
0x18003c152  cmp     rcx, rax
0x18003c155  jb      short loc_18003C131
0x18003c157  mov     [rbp+57h+var_80], r12
0x18003c15b  mov     ebx, 2
0x18003c160  mov     eax, ebx
0x18003c162  mul     r14
0x18003c165  mov     r8d, 80070216h
0x18003c16b  test    rdx, rdx
0x18003c16e  jnz     short loc_18003C175
0x18003c170  mov     r9d, r12d
0x18003c173  jmp     short loc_18003C17B
0x18003c175  mov     rax, r13
0x18003c178  mov     r9d, r8d; char *
0x18003c17b  mov     rcx, [rbp+5Fh]; this
0x18003c17f  test    r9d, r9d
0x18003c182  js      loc_18003C3BA
0x18003c188  mov     r13d, 0FFFFFFFFh
0x18003c18e  cmp     rax, r13
0x18003c191  mov     ecx, eax
0x18003c193  jbe     short loc_18003C198
0x18003c195  mov     ecx, r13d
0x18003c198  cmp     r13, rax
0x18003c19b  sbb     r9d, r9d
0x18003c19e  and     r9d, r8d; char *
0x18003c1a1  mov     r10, [rbp+5Fh]
0x18003c1a5  cmp     rax, r13
0x18003c1a8  ja      loc_18003C3CC
0x18003c1ae  mov     [rsp+0E0h+samDesired], ecx; cbData
0x18003c1b2  mov     qword ptr [rsp+0E0h+dwOptions], rdi; unsigned int
0x18003c1b7  mov     r9d, 7; dwType
0x18003c1bd  xor     r8d, r8d; Reserved
0x18003c1c0  lea     rdx, aCategories; "Categories"
0x18003c1c7  mov     rcx, [rbp+57h+hKey]; hKey
0x18003c1cb  call    cs:__imp_RegSetValueExW
0x18003c1d1  mov     rcx, [rbp+5Fh]; this
0x18003c1d5  test    eax, eax
0x18003c1d7  jnz     loc_18003C3E1
0x18003c1dd  mov     dword ptr [rbp+57h+Data], 1
0x18003c1e4  lea     r9d, [rax+4]; dwType
0x18003c1e8  mov     [rsp+0E0h+samDesired], r9d; cbData
0x18003c1ed  lea     rax, [rbp+57h+Data]
0x18003c1f1  mov     qword ptr [rsp+0E0h+dwOptions], rax; int
0x18003c1f6  xor     r8d, r8d; Reserved
0x18003c1f9  lea     rdx, aState; "State"
0x18003c200  mov     rcx, [rbp+57h+hKey]; hKey
0x18003c204  call    cs:__imp_RegSetValueExW
0x18003c20a  mov     rcx, [rbp+5Fh]; this
0x18003c20e  test    eax, eax
0x18003c210  jnz     loc_18003C3F6
0x18003c216  test    r15, r15
0x18003c219  jz      loc_18003C340
0x18003c21f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003c223  mov     rax, rcx
0x18003c226  inc     rax
0x18003c229  cmp     [r15+rax*2], r12w
0x18003c22e  jnz     short loc_18003C226
0x18003c230  test    rax, rax
0x18003c233  jz      loc_18003C340
0x18003c239  lea     r14, [rax+2]
0x18003c23d  mov     [rbp+57h+var_80], r12
0x18003c241  mov     rax, rbx
0x18003c244  mul     r14
0x18003c247  mov     rsi, rax
0x18003c24a  cmovb   rsi, rcx
0x18003c24e  mov     rcx, rsi; unsigned __int64
0x18003c251  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003c256  mov     rbx, rax
0x18003c259  test    rax, rax
0x18003c25c  jz      short loc_18003C26D
0x18003c25e  mov     r8, rsi; Size
0x18003c261  xor     edx, edx; Val
0x18003c263  mov     rcx, rax; void *
0x18003c266  call    memset_0
0x18003c26b  jmp     short loc_18003C270
0x18003c26d  mov     rbx, r12
0x18003c270  mov     [rbp+57h+var_80], rbx
0x18003c274  mov     rdx, r12
0x18003c277  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003c27b  inc     rax
0x18003c27e  cmp     [r15+rax*2], r12w
0x18003c283  jnz     short loc_18003C27B
0x18003c285  test    rax, rax
0x18003c288  jz      short loc_18003C2B9
0x18003c28a  mov     eax, r12d
0x18003c28d  cmp     word ptr [r15+rdx*2], 2Fh ; '/'
0x18003c293  cmovnz  ax, [r15+rdx*2]
0x18003c299  mov     [rbx+rdx*2], ax
0x18003c29d  inc     rdx
0x18003c2a0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003c2a4  inc     rcx
0x18003c2a7  cmp     [r15+rcx*2], r12w
0x18003c2ac  jnz     short loc_18003C2A4
0x18003c2ae  cmp     rdx, rcx
0x18003c2b1  jb      short loc_18003C28A
0x18003c2b3  mov     r13d, 0FFFFFFFFh
0x18003c2b9  mov     eax, 2
0x18003c2be  mul     r14
0x18003c2c1  test    rdx, rdx
0x18003c2c4  jnz     short loc_18003C2CB
0x18003c2c6  mov     r9d, r12d
0x18003c2c9  jmp     short loc_18003C2D5
0x18003c2cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003c2cf  mov     r9d, 80070216h; char *
0x18003c2d5  mov     rcx, [rbp+5Fh]; this
0x18003c2d9  test    r9d, r9d
0x18003c2dc  js      loc_18003C40B
0x18003c2e2  cmp     rax, r13
0x18003c2e5  mov     ecx, eax
0x18003c2e7  jbe     short loc_18003C2EC
0x18003c2e9  mov     ecx, r13d
0x18003c2ec  cmp     r13, rax
0x18003c2ef  sbb     r9d, r9d
0x18003c2f2  and     r9d, 80070216h; char *
0x18003c2f9  mov     r10, [rbp+5Fh]
0x18003c2fd  cmp     rax, r13
0x18003c300  ja      loc_18003C41D
0x18003c306  mov     [rsp+0E0h+samDesired], ecx; cbData
0x18003c30a  mov     qword ptr [rsp+0E0h+dwOptions], rbx; unsigned int
0x18003c30f  mov     r9d, 7; dwType
0x18003c315  xor     r8d, r8d; Reserved
0x18003c318  lea     rdx, aUsernamedchild; "UserNamedChildNodes"
0x18003c31f  mov     rcx, [rbp+57h+hKey]; hKey
0x18003c323  call    cs:__imp_RegSetValueExW
0x18003c329  mov     rcx, [rbp+5Fh]; this
0x18003c32d  test    eax, eax
0x18003c32f  jnz     short loc_18003C390
0x18003c331  test    rbx, rbx
0x18003c334  jz      short loc_18003C340
0x18003c336  mov     rcx, rbx
0x18003c339  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003c33f  nop
0x18003c340  test    rdi, rdi
0x18003c343  jz      short loc_18003C34F
0x18003c345  mov     rcx, rdi
0x18003c348  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003c34e  nop
0x18003c34f  mov     rcx, [rbp+57h+hKey]; hKey
0x18003c353  test    rcx, rcx
0x18003c356  jz      short loc_18003C35F
0x18003c358  call    cs:__imp_RegCloseKey
0x18003c35e  nop
0x18003c35f  cmp     [rbp+57h+var_50], 8
0x18003c364  jb      short loc_18003C370
0x18003c366  mov     rcx, [rbp+57h+lpSubKey]
0x18003c36a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003c370  mov     rcx, [rbp+57h+var_48]
0x18003c374  xor     rcx, rsp; StackCookie
0x18003c377  call    __security_check_cookie
0x18003c37c  add     rsp, 0A8h
0x18003c383  pop     r15
0x18003c385  pop     r14
0x18003c387  pop     r13
0x18003c389  pop     r12
0x18003c38b  pop     rdi
0x18003c38c  pop     rsi
0x18003c38d  pop     rbx
0x18003c38e  pop     rbp
0x18003c38f  retn
0x18003c390  mov     r9d, eax; char *
0x18003c393  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003c39a  mov     edx, 0ADh; void *
0x18003c39f  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18003c3a5  mov     r9d, eax; char *
0x18003c3a8  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003c3af  mov     edx, 82h; void *
0x18003c3b4  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18003c3ba  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003c3c1  mov     edx, 8Fh; void *
0x18003c3c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c3cc  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003c3d3  mov     edx, 90h; void *
0x18003c3d8  mov     rcx, r10; this
0x18003c3db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c3e1  mov     r9d, eax; char *
0x18003c3e4  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003c3eb  mov     edx, 94h; void *
0x18003c3f0  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18003c3f6  mov     r9d, eax; char *
0x18003c3f9  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003c400  mov     edx, 99h; void *
0x18003c405  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18003c40b  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003c412  mov     edx, 0A8h; void *
0x18003c417  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c41d  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003c424  mov     edx, 0A9h; void *
0x18003c429  mov     rcx, r10; this
0x18003c42c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
