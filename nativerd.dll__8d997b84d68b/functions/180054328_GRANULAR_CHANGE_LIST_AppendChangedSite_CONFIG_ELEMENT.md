# GRANULAR_CHANGE_LIST::AppendChangedSite(CONFIG_ELEMENT *)

- ea: `0x180054328`
- end: `0x18005455f`
- name: `?AppendChangedSite@GRANULAR_CHANGE_LIST@@AEAAJPEAVCONFIG_ELEMENT@@@Z`
- size: `567`
- prototype: `__int64 __fastcall(GRANULAR_CHANGE_LIST *__hidden this, struct CONFIG_ELEMENT *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180054190`
- `0x1800551cc`
- `0x180055664`

## callees

- `0x18002ff78`
- `0x1800307c4`
- `0x1800541c4`
- `0x180054328`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180054526`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180054531`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180054526`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180054531`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800544cd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800544f9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800544cd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800544f9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180054384`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800543b9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180054384`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800543b9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800543f9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800543f9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180054413`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800544bd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180054413`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800544bd`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18005449b`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18005449b`

## pseudocode

```c
__int64 __fastcall GRANULAR_CHANGE_LIST::AppendChangedSite(GRANULAR_CHANGE_LIST *this, struct CONFIG_ELEMENT *a2)
{
  struct CONFIG_COLLECTION *v4; // rdi
  int appended; // ebx
  int DefaultInternalCollection; // eax
  unsigned int i; // esi
  __int64 v8; // rcx
  const unsigned __int16 *v9; // rax
  const unsigned __int16 *Str; // rax
  struct CONFIG_COLLECTION *v12; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned __int16 *v13; // [rsp+38h] [rbp-C8h] BYREF
  const unsigned __int16 *v14; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[56]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v16[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v17[128]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v18[128]; // [rsp+1C0h] [rbp+C0h] BYREF

  v13 = 0;
  memset_0(v17, 0, sizeof(v17));
  STRU::STRU((STRU *)v15, v17, 0x80u);
  v12 = 0;
  v14 = 0;
  v4 = 0;
  memset_0(v18, 0, sizeof(v18));
  STRU::STRU((STRU *)v16, v18, 0x80u);
  appended = (*(__int64 (__fastcall **)(char *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*((_QWORD *)a2 + 2) + 64LL))(
               (char *)a2 + 16,
               L"name",
               &v13,
               0,
               0);
  if ( appended >= 0 )
  {
    appended = STRU::Copy((STRU *)v15, L"MACHINE/WEBROOT/APPHOST/");
    if ( appended >= 0 )
    {
      appended = STRU::Append((STRU *)v15, v13);
      if ( appended >= 0 )
      {
        if ( *((int *)this + 1) < 2 )
        {
          Str = STRU::QueryStr((STRU *)v15);
          appended = GRANULAR_CHANGE_LIST::AppendChangedPath(this, Str, 0, 1);
        }
        else
        {
          DefaultInternalCollection = CONFIG_ELEMENT::GetDefaultInternalCollection(a2, &v12);
          v4 = v12;
          appended = DefaultInternalCollection;
          if ( DefaultInternalCollection >= 0 )
          {
            for ( i = 0; i < *((_DWORD *)v4 + 8); ++i )
            {
              v8 = *(_QWORD *)(*((_QWORD *)v4 + 5) + 24LL * i) + 16LL;
              appended = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v8 + 64LL))(
                           v8,
                           L"path",
                           &v14,
                           0,
                           0);
              if ( appended < 0 )
                break;
              appended = STRU::Copy((STRU *)v16, (const struct STRU *)v15);
              if ( appended < 0 )
                break;
              if ( *v14 != 47 || v14[1] )
              {
                appended = STRU::Append((STRU *)v16, v14);
                if ( appended < 0 )
                  break;
              }
              v9 = STRU::QueryStr((STRU *)v16);
              appended = GRANULAR_CHANGE_LIST::AppendChangedPath(this, v9, 0, 1);
              if ( appended < 0 )
                break;
            }
          }
        }
        if ( v4 )
          CONFIG_COLLECTION::DereferenceConfigCollection(v4);
      }
    }
  }
  STRU::~STRU((STRU *)v16);
  STRU::~STRU((STRU *)v15);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180054328  mov     [rsp-8+arg_10], rbx
0x18005432d  push    rbp
0x18005432e  push    rsi
0x18005432f  push    rdi
0x180054330  push    r12
0x180054332  push    r14
0x180054334  lea     rbp, [rsp-1D0h]
0x18005433c  sub     rsp, 2D0h
0x180054343  mov     rax, cs:__security_cookie
0x18005434a  xor     rax, rsp
0x18005434d  mov     [rbp+1F0h+var_30], rax
0x180054354  mov     rsi, rdx
0x180054357  mov     r14, rcx
0x18005435a  xor     r12d, r12d
0x18005435d  lea     rcx, [rbp+1F0h+var_230]; void *
0x180054361  xor     edx, edx; Val
0x180054363  mov     [rsp+2F0h+var_2B8], r12
0x180054368  mov     r8d, 100h; Size
0x18005436e  call    memset_0
0x180054373  mov     ebx, 80h
0x180054378  lea     rdx, [rbp+1F0h+var_230]
0x18005437c  mov     r8d, ebx
0x18005437f  lea     rcx, [rsp+2F0h+var_2A8]
0x180054384  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18005438a  xor     edx, edx; Val
0x18005438c  mov     [rsp+2F0h+var_2C0], r12
0x180054391  mov     r8d, 100h; Size
0x180054397  mov     [rsp+2F0h+var_2B0], r12
0x18005439c  lea     rcx, [rbp+1F0h+var_130]; void *
0x1800543a3  mov     edi, r12d
0x1800543a6  call    memset_0
0x1800543ab  mov     r8d, ebx
0x1800543ae  lea     rdx, [rbp+1F0h+var_130]
0x1800543b5  lea     rcx, [rbp+1F0h+var_270]
0x1800543b9  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800543bf  lea     rcx, [rsi+10h]
0x1800543c3  mov     [rsp+2F0h+var_2D0], r12
0x1800543c8  mov     rax, [rcx]
0x1800543cb  lea     r8, [rsp+2F0h+var_2B8]
0x1800543d0  xor     r9d, r9d
0x1800543d3  lea     rdx, aName; "name"
0x1800543da  mov     rax, [rax+40h]
0x1800543de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800543e3  mov     ebx, eax
0x1800543e5  test    eax, eax
0x1800543e7  js      loc_180054522
0x1800543ed  lea     rdx, aMachineWebroot_1; "MACHINE/WEBROOT/APPHOST/"
0x1800543f4  lea     rcx, [rsp+2F0h+var_2A8]
0x1800543f9  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800543ff  mov     ebx, eax
0x180054401  test    eax, eax
0x180054403  js      loc_180054522
0x180054409  mov     rdx, [rsp+2F0h+var_2B8]
0x18005440e  lea     rcx, [rsp+2F0h+var_2A8]
0x180054413  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180054419  mov     ebx, eax
0x18005441b  test    eax, eax
0x18005441d  js      loc_180054522
0x180054423  cmp     dword ptr [r14+4], 2
0x180054428  jl      loc_1800544F4
0x18005442e  lea     rdx, [rsp+2F0h+var_2C0]; struct CONFIG_COLLECTION **
0x180054433  mov     rcx, rsi; this
0x180054436  call    ?GetDefaultInternalCollection@CONFIG_ELEMENT@@QEAAJPEAPEAVCONFIG_COLLECTION@@@Z; CONFIG_ELEMENT::GetDefaultInternalCollection(CONFIG_COLLECTION * *)
0x18005443b  mov     rdi, [rsp+2F0h+var_2C0]
0x180054440  mov     ebx, eax
0x180054442  test    eax, eax
0x180054444  js      loc_180054515
0x18005444a  mov     esi, r12d
0x18005444d  cmp     esi, [rdi+20h]
0x180054450  jnb     loc_180054515
0x180054456  mov     eax, esi
0x180054458  lea     r8, [rsp+2F0h+var_2B0]
0x18005445d  xor     r9d, r9d
0x180054460  mov     [rsp+2F0h+var_2D0], r12
0x180054465  lea     rdx, aPath; "path"
0x18005446c  lea     rcx, [rax+rax*2]
0x180054470  mov     rax, [rdi+28h]
0x180054474  mov     rcx, [rax+rcx*8]
0x180054478  add     rcx, 10h
0x18005447c  mov     rax, [rcx]
0x18005447f  mov     rax, [rax+40h]
0x180054483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054488  mov     ebx, eax
0x18005448a  test    eax, eax
0x18005448c  js      loc_180054515
0x180054492  lea     rdx, [rsp+2F0h+var_2A8]
0x180054497  lea     rcx, [rbp+1F0h+var_270]
0x18005449b  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x1800544a1  mov     ebx, eax
0x1800544a3  test    eax, eax
0x1800544a5  js      short loc_180054515
0x1800544a7  mov     rdx, [rsp+2F0h+var_2B0]
0x1800544ac  cmp     word ptr [rdx], 2Fh ; '/'
0x1800544b0  jnz     short loc_1800544B9
0x1800544b2  cmp     [rdx+2], r12w
0x1800544b7  jz      short loc_1800544C9
0x1800544b9  lea     rcx, [rbp+1F0h+var_270]
0x1800544bd  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800544c3  mov     ebx, eax
0x1800544c5  test    eax, eax
0x1800544c7  js      short loc_180054515
0x1800544c9  lea     rcx, [rbp+1F0h+var_270]
0x1800544cd  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800544d3  mov     r9d, 1; int
0x1800544d9  xor     r8d, r8d; int
0x1800544dc  mov     rdx, rax; unsigned __int16 *
0x1800544df  mov     rcx, r14; this
0x1800544e2  call    ?AppendChangedPath@GRANULAR_CHANGE_LIST@@AEAAJPEBGHH@Z; GRANULAR_CHANGE_LIST::AppendChangedPath(ushort const *,int,int)
0x1800544e7  mov     ebx, eax
0x1800544e9  test    eax, eax
0x1800544eb  js      short loc_180054515
0x1800544ed  inc     esi
0x1800544ef  jmp     loc_18005444D
0x1800544f4  lea     rcx, [rsp+2F0h+var_2A8]
0x1800544f9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800544ff  mov     r9d, 1; int
0x180054505  xor     r8d, r8d; int
0x180054508  mov     rdx, rax; unsigned __int16 *
0x18005450b  mov     rcx, r14; this
0x18005450e  call    ?AppendChangedPath@GRANULAR_CHANGE_LIST@@AEAAJPEBGHH@Z; GRANULAR_CHANGE_LIST::AppendChangedPath(ushort const *,int,int)
0x180054513  mov     ebx, eax
0x180054515  test    rdi, rdi
0x180054518  jz      short loc_180054522
0x18005451a  mov     rcx, rdi; this
0x18005451d  call    ?DereferenceConfigCollection@CONFIG_COLLECTION@@QEAAXXZ; CONFIG_COLLECTION::DereferenceConfigCollection(void)
0x180054522  lea     rcx, [rbp+1F0h+var_270]
0x180054526  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18005452c  lea     rcx, [rsp+2F0h+var_2A8]
0x180054531  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180054537  mov     eax, ebx
0x180054539  mov     rcx, [rbp+1F0h+var_30]
0x180054540  xor     rcx, rsp; StackCookie
0x180054543  call    __security_check_cookie
0x180054548  mov     rbx, [rsp+2F0h+arg_10]
0x180054550  add     rsp, 2D0h
0x180054557  pop     r14
0x180054559  pop     r12
0x18005455b  pop     rdi
0x18005455c  pop     rsi
0x18005455d  pop     rbp
0x18005455e  retn
```
