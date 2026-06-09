# GRANULAR_CHANGE_LIST::GetSiteElementChanges(CONFIG_ELEMENT *,CONFIG_ELEMENT *)

- ea: `0x1800551cc`
- end: `0x18005565b`
- name: `?GetSiteElementChanges@GRANULAR_CHANGE_LIST@@AEAAJPEAVCONFIG_ELEMENT@@0@Z`
- size: `1167`
- prototype: `__int64 __fastcall(GRANULAR_CHANGE_LIST *__hidden this, struct CONFIG_ELEMENT *, struct CONFIG_ELEMENT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180055664`

## callees

- `0x18002ff78`
- `0x1800307c4`
- `0x18003219c`
- `0x1800541c4`
- `0x180054328`
- `0x1800551cc`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180055412`
- `msvcrt!_wcsicmp` at `0x180055412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800554fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800554fd`
- `iisutil!?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z` at `0x18005556d`
- `iisutil!?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z` at `0x18005556d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005561f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180055629`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005561f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180055629`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800554c2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800555bf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800554c2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800555bf`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005522e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180055254`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005522e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180055254`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800552be`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800552be`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800552d7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800554ad`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800555ae`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800552d7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800554ad`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800555ae`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180055450`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180055450`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18005547c`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180055580`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18005547c`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180055580`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18005527f`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18005527f`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180055614`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180055614`

## pseudocode

```c
__int64 __fastcall GRANULAR_CHANGE_LIST::GetSiteElementChanges(
        GRANULAR_CHANGE_LIST *this,
        struct CONFIG_ELEMENT *a2,
        struct CONFIG_ELEMENT *a3)
{
  struct CONFIG_COLLECTION *v6; // rdi
  signed int IsEqual; // ebx
  int DefaultInternalCollection; // eax
  struct CONFIG_COLLECTION *v9; // r13
  int v10; // eax
  unsigned int v11; // r15d
  unsigned int j; // esi
  struct CONFIG_ELEMENT *v13; // r12
  int v14; // esi
  const unsigned __int16 *v15; // rax
  signed int LastError; // eax
  unsigned int i; // esi
  __int64 v18; // rcx
  int v19; // r15d
  const unsigned __int16 *Str; // rax
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *String2; // [rsp+38h] [rbp-C8h] BYREF
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  struct CONFIG_COLLECTION *v25; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-B0h] BYREF
  struct CONFIG_COLLECTION *v27; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v28; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v29[56]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v30[56]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v31[56]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 v32[128]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v33[128]; // [rsp+210h] [rbp+110h] BYREF

  v28 = 0;
  memset_0(v32, 0, sizeof(v32));
  STRU::STRU((STRU *)v30, v32, 0x80u);
  memset_0(v33, 0, sizeof(v33));
  STRU::STRU((STRU *)v29, v33, 0x80u);
  v24 = 0;
  v25 = 0;
  v6 = 0;
  v27 = 0;
  v22 = 0;
  String1 = 0;
  String2 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v31);
  IsEqual = (*(__int64 (__fastcall **)(char *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*((_QWORD *)a2 + 2) + 64LL))(
              (char *)a2 + 16,
              L"name",
              &v28,
              0,
              0);
  if ( IsEqual < 0 )
    goto LABEL_51;
  IsEqual = STRU::Copy((STRU *)v30, L"MACHINE/WEBROOT/APPHOST/");
  if ( IsEqual < 0 )
    goto LABEL_51;
  IsEqual = STRU::Append((STRU *)v30, v28);
  if ( IsEqual < 0 )
    goto LABEL_51;
  IsEqual = CONFIG_ELEMENT::IsEqual(a2, a3, &v24, 1);
  if ( IsEqual < 0 )
    goto LABEL_51;
  if ( !v24 )
  {
    IsEqual = GRANULAR_CHANGE_LIST::AppendChangedSite(this, a2);
    if ( IsEqual >= 0 )
      IsEqual = GRANULAR_CHANGE_LIST::AppendChangedSite(this, a3);
    goto LABEL_51;
  }
  DefaultInternalCollection = CONFIG_ELEMENT::GetDefaultInternalCollection(a2, &v25);
  v9 = v25;
  IsEqual = DefaultInternalCollection;
  if ( DefaultInternalCollection >= 0 )
  {
    v10 = CONFIG_ELEMENT::GetDefaultInternalCollection(a3, &v27);
    v6 = v27;
    IsEqual = v10;
    if ( v10 >= 0 )
    {
      v11 = 0;
      while ( 2 )
      {
        if ( v11 >= *((_DWORD *)v9 + 8) )
        {
          for ( i = 0; i < *((_DWORD *)v6 + 8); ++i )
          {
            v18 = *(_QWORD *)(*((_QWORD *)v6 + 5) + 24LL * i) + 16LL;
            IsEqual = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v18 + 64LL))(
                        v18,
                        L"path",
                        &String2,
                        0,
                        0);
            if ( IsEqual < 0 )
              break;
            if ( !MULTISZ::FindStringNoCase((MULTISZ *)v31, String2) )
            {
              IsEqual = STRU::Copy((STRU *)v29, (const struct STRU *)v30);
              if ( IsEqual < 0 )
                goto LABEL_47;
              if ( *String2 != 47 || String2[1] )
              {
                v19 = 0;
                IsEqual = STRU::Append((STRU *)v29, String2);
                if ( IsEqual < 0 )
                  goto LABEL_47;
              }
              else
              {
                v19 = 1;
              }
              Str = STRU::QueryStr((STRU *)v29);
              IsEqual = GRANULAR_CHANGE_LIST::AppendChangedPath(this, Str, 0, 1);
              if ( IsEqual < 0 || *((_DWORD *)this + 1) == 1 && v19 )
                break;
            }
          }
          break;
        }
        v25 = *(struct CONFIG_COLLECTION **)(*((_QWORD *)v9 + 5) + 24LL * v11);
        IsEqual = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *, wchar_t **, _QWORD, _QWORD))(*((_QWORD *)v25 + 2) + 64LL))(
                    (char *)v25 + 16,
                    L"path",
                    &String1,
                    0,
                    0);
        if ( IsEqual >= 0 )
        {
          for ( j = 0; ; ++j )
          {
            if ( j >= *((_DWORD *)v6 + 8) )
              goto LABEL_23;
            v13 = *(struct CONFIG_ELEMENT **)(*((_QWORD *)v6 + 5) + 24LL * j);
            IsEqual = (*(__int64 (__fastcall **)(_QWORD *, const unsigned __int16 *, wchar_t **, _QWORD, _QWORD))(*((_QWORD *)v13 + 2) + 64LL))(
                        (_QWORD *)v13 + 2,
                        L"path",
                        &String2,
                        0,
                        0);
            if ( IsEqual < 0 )
              goto LABEL_47;
            if ( !_wcsicmp(String1, String2) )
              break;
          }
          if ( v13 )
          {
            IsEqual = CONFIG_ELEMENT::IsEqual(v25, v13, &v22, 0);
            if ( IsEqual < 0 )
              break;
            if ( !MULTISZ::Append((MULTISZ *)v31, String2) )
            {
              LastError = GetLastError();
              IsEqual = LastError;
              if ( LastError > 0 )
                IsEqual = (unsigned __int16)LastError | 0x80070000;
              break;
            }
            if ( v22 )
            {
LABEL_32:
              ++v11;
              continue;
            }
          }
          else
          {
LABEL_23:
            v22 = 0;
          }
          IsEqual = STRU::Copy((STRU *)v29, (const struct STRU *)v30);
          if ( IsEqual < 0 )
            break;
          if ( *String1 != 47 || String1[1] )
          {
            v14 = 0;
            IsEqual = STRU::Append((STRU *)v29, String1);
            if ( IsEqual < 0 )
              break;
          }
          else
          {
            v14 = 1;
          }
          v15 = STRU::QueryStr((STRU *)v29);
          IsEqual = GRANULAR_CHANGE_LIST::AppendChangedPath(this, v15, 0, 1);
          if ( IsEqual >= 0 && (*((_DWORD *)this + 1) != 1 || !v14) )
            goto LABEL_32;
        }
        break;
      }
    }
  }
LABEL_47:
  if ( v9 )
    CONFIG_COLLECTION::DereferenceConfigCollection(v9);
  if ( v6 )
    CONFIG_COLLECTION::DereferenceConfigCollection(v6);
LABEL_51:
  MULTISZ::~MULTISZ((MULTISZ *)v31);
  STRU::~STRU((STRU *)v29);
  STRU::~STRU((STRU *)v30);
  return (unsigned int)IsEqual;
}

```

## disassembly

```asm
0x1800551cc  mov     [rsp-8+arg_18], rbx
0x1800551d1  push    rbp
0x1800551d2  push    rsi
0x1800551d3  push    rdi
0x1800551d4  push    r12
0x1800551d6  push    r13
0x1800551d8  push    r14
0x1800551da  push    r15
0x1800551dc  lea     rbp, [rsp-220h]
0x1800551e4  sub     rsp, 320h
0x1800551eb  mov     rax, cs:__security_cookie
0x1800551f2  xor     rax, rsp
0x1800551f5  mov     [rbp+250h+var_40], rax
0x1800551fc  mov     r15, r8
0x1800551ff  mov     rsi, rdx
0x180055202  mov     r14, rcx
0x180055205  mov     edi, 100h
0x18005520a  xor     r12d, r12d
0x18005520d  lea     rcx, [rbp+250h+var_240]; void *
0x180055211  mov     r8d, edi; Size
0x180055214  mov     [rsp+350h+var_2F0], r12
0x180055219  xor     edx, edx; Val
0x18005521b  call    memset_0
0x180055220  lea     ebx, [rdi-80h]
0x180055223  mov     r8d, ebx
0x180055226  lea     rdx, [rbp+250h+var_240]
0x18005522a  lea     rcx, [rbp+250h+var_2B0]
0x18005522e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180055234  mov     r8d, edi; Size
0x180055237  lea     rcx, [rbp+250h+var_140]; void *
0x18005523e  xor     edx, edx; Val
0x180055240  call    memset_0
0x180055245  mov     r8d, ebx
0x180055248  lea     rdx, [rbp+250h+var_140]
0x18005524f  lea     rcx, [rsp+350h+var_2E8]
0x180055254  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18005525a  lea     rcx, [rbp+250h+var_278]
0x18005525e  mov     [rsp+350h+var_310], r12d
0x180055263  mov     [rsp+350h+var_308], r12
0x180055268  mov     edi, r12d
0x18005526b  mov     [rsp+350h+var_2F8], r12
0x180055270  mov     [rsp+350h+var_320], r12d
0x180055275  mov     [rsp+350h+String1], r12
0x18005527a  mov     [rsp+350h+String2], r12
0x18005527f  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180055285  lea     rcx, [rsi+10h]
0x180055289  mov     [rsp+350h+var_330], r12
0x18005528e  mov     rax, [rcx]
0x180055291  lea     r8, [rsp+350h+var_2F0]
0x180055296  xor     r9d, r9d
0x180055299  lea     rdx, aName; "name"
0x1800552a0  mov     rax, [rax+40h]
0x1800552a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552a9  mov     ebx, eax
0x1800552ab  test    eax, eax
0x1800552ad  js      loc_180055610
0x1800552b3  lea     rdx, aMachineWebroot_1; "MACHINE/WEBROOT/APPHOST/"
0x1800552ba  lea     rcx, [rbp+250h+var_2B0]
0x1800552be  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800552c4  mov     ebx, eax
0x1800552c6  test    eax, eax
0x1800552c8  js      loc_180055610
0x1800552ce  mov     rdx, [rsp+350h+var_2F0]
0x1800552d3  lea     rcx, [rbp+250h+var_2B0]
0x1800552d7  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800552dd  mov     ebx, eax
0x1800552df  test    eax, eax
0x1800552e1  js      loc_180055610
0x1800552e7  lea     r9d, [r12+1]; int
0x1800552ec  mov     rdx, r15; struct CONFIG_ELEMENT *
0x1800552ef  lea     r8, [rsp+350h+var_310]; int *
0x1800552f4  mov     rcx, rsi; this
0x1800552f7  call    ?IsEqual@CONFIG_ELEMENT@@QEAAJPEAV1@PEAHH@Z; CONFIG_ELEMENT::IsEqual(CONFIG_ELEMENT *,int *,int)
0x1800552fc  mov     ebx, eax
0x1800552fe  test    eax, eax
0x180055300  js      loc_180055610
0x180055306  cmp     [rsp+350h+var_310], r12d
0x18005530b  jnz     short loc_180055334
0x18005530d  mov     rdx, rsi; struct CONFIG_ELEMENT *
0x180055310  mov     rcx, r14; this
0x180055313  call    ?AppendChangedSite@GRANULAR_CHANGE_LIST@@AEAAJPEAVCONFIG_ELEMENT@@@Z; GRANULAR_CHANGE_LIST::AppendChangedSite(CONFIG_ELEMENT *)
0x180055318  mov     ebx, eax
0x18005531a  test    eax, eax
0x18005531c  js      loc_180055610
0x180055322  mov     rdx, r15; struct CONFIG_ELEMENT *
0x180055325  mov     rcx, r14; this
0x180055328  call    ?AppendChangedSite@GRANULAR_CHANGE_LIST@@AEAAJPEAVCONFIG_ELEMENT@@@Z; GRANULAR_CHANGE_LIST::AppendChangedSite(CONFIG_ELEMENT *)
0x18005532d  mov     ebx, eax
0x18005532f  jmp     loc_180055610
0x180055334  lea     rdx, [rsp+350h+var_308]; struct CONFIG_COLLECTION **
0x180055339  mov     rcx, rsi; this
0x18005533c  call    ?GetDefaultInternalCollection@CONFIG_ELEMENT@@QEAAJPEAPEAVCONFIG_COLLECTION@@@Z; CONFIG_ELEMENT::GetDefaultInternalCollection(CONFIG_COLLECTION * *)
0x180055341  mov     r13, [rsp+350h+var_308]
0x180055346  mov     ebx, eax
0x180055348  test    eax, eax
0x18005534a  js      loc_1800555F6
0x180055350  lea     rdx, [rsp+350h+var_2F8]; struct CONFIG_COLLECTION **
0x180055355  mov     rcx, r15; this
0x180055358  call    ?GetDefaultInternalCollection@CONFIG_ELEMENT@@QEAAJPEAPEAVCONFIG_COLLECTION@@@Z; CONFIG_ELEMENT::GetDefaultInternalCollection(CONFIG_COLLECTION * *)
0x18005535d  mov     rdi, [rsp+350h+var_2F8]
0x180055362  mov     ebx, eax
0x180055364  test    eax, eax
0x180055366  js      loc_1800555F6
0x18005536c  mov     r15d, r12d
0x18005536f  cmp     r15d, [r13+20h]
0x180055373  jnb     loc_18005551B
0x180055379  mov     eax, r15d
0x18005537c  lea     r8, [rsp+350h+String1]
0x180055381  xor     r9d, r9d
0x180055384  mov     [rsp+350h+var_330], r12
0x180055389  lea     rdx, aPath; "path"
0x180055390  lea     rcx, [rax+rax*2]
0x180055394  mov     rax, [r13+28h]
0x180055398  mov     rax, [rax+rcx*8]
0x18005539c  mov     [rsp+350h+var_308], rax
0x1800553a1  lea     rcx, [rax+10h]
0x1800553a5  mov     rax, [rcx]
0x1800553a8  mov     rax, [rax+40h]
0x1800553ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800553b1  mov     ebx, eax
0x1800553b3  test    eax, eax
0x1800553b5  js      loc_1800555F6
0x1800553bb  mov     esi, r12d
0x1800553be  cmp     esi, [rdi+20h]
0x1800553c1  jnb     loc_18005546B
0x1800553c7  mov     eax, esi
0x1800553c9  lea     r8, [rsp+350h+String2]
0x1800553ce  xor     r9d, r9d
0x1800553d1  mov     [rsp+350h+var_330], 0
0x1800553da  lea     rdx, aPath; "path"
0x1800553e1  lea     rcx, [rax+rax*2]
0x1800553e5  mov     rax, [rdi+28h]
0x1800553e9  mov     r12, [rax+rcx*8]
0x1800553ed  lea     rcx, [r12+10h]
0x1800553f2  mov     rax, [rcx]
0x1800553f5  mov     rax, [rax+40h]
0x1800553f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800553fe  mov     ebx, eax
0x180055400  test    eax, eax
0x180055402  js      loc_1800555F6
0x180055408  mov     rdx, [rsp+350h+String2]; String2
0x18005540d  mov     rcx, [rsp+350h+String1]; String1
0x180055412  call    cs:__imp__wcsicmp
0x180055418  test    eax, eax
0x18005541a  jz      short loc_180055420
0x18005541c  inc     esi
0x18005541e  jmp     short loc_1800553BE
0x180055420  test    r12, r12
0x180055423  jz      short loc_18005546B
0x180055425  mov     rcx, [rsp+350h+var_308]; this
0x18005542a  lea     r8, [rsp+350h+var_320]; int *
0x18005542f  xor     r9d, r9d; int
0x180055432  mov     rdx, r12; struct CONFIG_ELEMENT *
0x180055435  call    ?IsEqual@CONFIG_ELEMENT@@QEAAJPEAV1@PEAHH@Z; CONFIG_ELEMENT::IsEqual(CONFIG_ELEMENT *,int *,int)
0x18005543a  xor     r12d, r12d
0x18005543d  mov     ebx, eax
0x18005543f  test    eax, eax
0x180055441  js      loc_1800555F6
0x180055447  mov     rdx, [rsp+350h+String2]
0x18005544c  lea     rcx, [rbp+250h+var_278]
0x180055450  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x180055456  test    eax, eax
0x180055458  jz      loc_1800554FD
0x18005545e  cmp     [rsp+350h+var_320], r12d
0x180055463  jnz     loc_1800554F5
0x180055469  jmp     short loc_180055473
0x18005546b  xor     r12d, r12d
0x18005546e  mov     [rsp+350h+var_320], r12d
0x180055473  lea     rdx, [rbp+250h+var_2B0]
0x180055477  lea     rcx, [rsp+350h+var_2E8]
0x18005547c  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180055482  mov     ebx, eax
0x180055484  test    eax, eax
0x180055486  js      loc_1800555F6
0x18005548c  mov     rdx, [rsp+350h+String1]
0x180055491  cmp     word ptr [rdx], 2Fh ; '/'
0x180055495  jnz     short loc_1800554A5
0x180055497  cmp     [rdx+2], r12w
0x18005549c  jnz     short loc_1800554A5
0x18005549e  mov     esi, 1
0x1800554a3  jmp     short loc_1800554BD
0x1800554a5  lea     rcx, [rsp+350h+var_2E8]
0x1800554aa  mov     esi, r12d
0x1800554ad  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800554b3  mov     ebx, eax
0x1800554b5  test    eax, eax
0x1800554b7  js      loc_1800555F6
0x1800554bd  lea     rcx, [rsp+350h+var_2E8]
0x1800554c2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800554c8  mov     r9d, 1; int
0x1800554ce  xor     r8d, r8d; int
0x1800554d1  mov     rdx, rax; unsigned __int16 *
0x1800554d4  mov     rcx, r14; this
0x1800554d7  call    ?AppendChangedPath@GRANULAR_CHANGE_LIST@@AEAAJPEBGHH@Z; GRANULAR_CHANGE_LIST::AppendChangedPath(ushort const *,int,int)
0x1800554dc  mov     ebx, eax
0x1800554de  test    eax, eax
0x1800554e0  js      loc_1800555F6
0x1800554e6  cmp     dword ptr [r14+4], 1
0x1800554eb  jnz     short loc_1800554F5
0x1800554ed  test    esi, esi
0x1800554ef  jnz     loc_1800555F6
0x1800554f5  inc     r15d
0x1800554f8  jmp     loc_18005536F
0x1800554fd  call    cs:__imp_GetLastError
0x180055503  mov     ebx, eax
0x180055505  test    eax, eax
0x180055507  jle     loc_1800555F6
0x18005550d  movzx   ebx, ax
0x180055510  or      ebx, 80070000h
0x180055516  jmp     loc_1800555F6
0x18005551b  mov     esi, r12d
0x18005551e  cmp     [rdi+20h], r12d
0x180055522  jbe     loc_1800555F6
0x180055528  mov     eax, esi
0x18005552a  lea     r8, [rsp+350h+String2]
0x18005552f  xor     r9d, r9d
0x180055532  mov     [rsp+350h+var_330], r12
0x180055537  lea     rdx, aPath; "path"
0x18005553e  lea     rcx, [rax+rax*2]
0x180055542  mov     rax, [rdi+28h]
0x180055546  mov     rcx, [rax+rcx*8]
0x18005554a  add     rcx, 10h
0x18005554e  mov     rax, [rcx]
0x180055551  mov     rax, [rax+40h]
0x180055555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005555a  mov     ebx, eax
0x18005555c  test    eax, eax
0x18005555e  js      loc_1800555F6
0x180055564  mov     rdx, [rsp+350h+String2]
0x180055569  lea     rcx, [rbp+250h+var_278]
0x18005556d  call    cs:__imp_?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z; MULTISZ::FindStringNoCase(ushort const *)
0x180055573  test    eax, eax
0x180055575  jnz     short loc_1800555EB
0x180055577  lea     rdx, [rbp+250h+var_2B0]
0x18005557b  lea     rcx, [rsp+350h+var_2E8]
0x180055580  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180055586  mov     ebx, eax
0x180055588  test    eax, eax
0x18005558a  js      short loc_1800555F6
0x18005558c  mov     rdx, [rsp+350h+String2]
0x180055591  cmp     word ptr [rdx], 2Fh ; '/'
0x180055595  jnz     short loc_1800555A6
0x180055597  cmp     [rdx+2], r12w
0x18005559c  jnz     short loc_1800555A6
0x18005559e  mov     r15d, 1
0x1800555a4  jmp     short loc_1800555BA
0x1800555a6  lea     rcx, [rsp+350h+var_2E8]
0x1800555ab  mov     r15d, r12d
0x1800555ae  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800555b4  mov     ebx, eax
0x1800555b6  test    eax, eax
0x1800555b8  js      short loc_1800555F6
0x1800555ba  lea     rcx, [rsp+350h+var_2E8]
0x1800555bf  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800555c5  mov     r9d, 1; int
0x1800555cb  xor     r8d, r8d; int
0x1800555ce  mov     rdx, rax; unsigned __int16 *
0x1800555d1  mov     rcx, r14; this
0x1800555d4  call    ?AppendChangedPath@GRANULAR_CHANGE_LIST@@AEAAJPEBGHH@Z; GRANULAR_CHANGE_LIST::AppendChangedPath(ushort const *,int,int)
0x1800555d9  mov     ebx, eax
0x1800555db  test    eax, eax
0x1800555dd  js      short loc_1800555F6
0x1800555df  cmp     dword ptr [r14+4], 1
0x1800555e4  jnz     short loc_1800555EB
0x1800555e6  test    r15d, r15d
0x1800555e9  jnz     short loc_1800555F6
0x1800555eb  inc     esi
0x1800555ed  cmp     esi, [rdi+20h]
0x1800555f0  jb      loc_180055528
0x1800555f6  test    r13, r13
0x1800555f9  jz      short loc_180055603
0x1800555fb  mov     rcx, r13; this
0x1800555fe  call    ?DereferenceConfigCollection@CONFIG_COLLECTION@@QEAAXXZ; CONFIG_COLLECTION::DereferenceConfigCollection(void)
0x180055603  test    rdi, rdi
0x180055606  jz      short loc_180055610
0x180055608  mov     rcx, rdi; this
0x18005560b  call    ?DereferenceConfigCollection@CONFIG_COLLECTION@@QEAAXXZ; CONFIG_COLLECTION::DereferenceConfigCollection(void)
0x180055610  lea     rcx, [rbp+250h+var_278]
0x180055614  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18005561a  lea     rcx, [rsp+350h+var_2E8]
0x18005561f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180055625  lea     rcx, [rbp+250h+var_2B0]
0x180055629  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18005562f  mov     eax, ebx
0x180055631  mov     rcx, [rbp+250h+var_40]
0x180055638  xor     rcx, rsp; StackCookie
0x18005563b  call    __security_check_cookie
0x180055640  mov     rbx, [rsp+350h+arg_18]
0x180055648  add     rsp, 320h
0x18005564f  pop     r15
0x180055651  pop     r14
0x180055653  pop     r13
0x180055655  pop     r12
0x180055657  pop     rdi
0x180055658  pop     rsi
0x180055659  pop     rbp
0x18005565a  retn
```
