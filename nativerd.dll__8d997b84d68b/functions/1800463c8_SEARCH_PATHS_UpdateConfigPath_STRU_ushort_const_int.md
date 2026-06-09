# SEARCH_PATHS::UpdateConfigPath(STRU *,ushort const *,int *)

- ea: `0x1800463c8`
- end: `0x1800465f2`
- name: `?UpdateConfigPath@SEARCH_PATHS@@CAJPEAVSTRU@@PEBGPEAH@Z`
- size: `554`
- prototype: `__int64 __fastcall(struct STRU *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180045b7c`

## callees

- `0x1800463c8`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x1800465bd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800465c8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800465bd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800465c8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004647f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800464e4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180046509`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180046554`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180046593`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004647f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800464e4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180046509`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180046554`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180046593`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180046419`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004643f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180046419`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004643f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18004648d`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800464a1`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800464ba`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180046517`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18004652b`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180046544`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18004648d`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800464a1`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800464ba`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180046517`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18004652b`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180046544`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180046468`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800464f2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004659f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180046468`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800464f2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004659f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18004656c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18004656c`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800464ca`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800464ca`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800464af`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180046539`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800464af`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180046539`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180046582`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180046582`

## pseudocode

```c
__int64 __fastcall SEARCH_PATHS::UpdateConfigPath(struct STRU *a1, const unsigned __int16 *a2, int *a3)
{
  int v6; // ebx
  unsigned __int16 *Str; // rbx
  unsigned int CCH; // eax
  const unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx
  unsigned int v11; // eax
  const unsigned __int16 *v12; // rax
  _BYTE v14[56]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v15[56]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v16[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v17[64]; // [rsp+110h] [rbp+10h] BYREF

  memset_0(v16, 0, sizeof(v16));
  STRU::STRU((STRU *)v15, v16, 0x40u);
  memset_0(v17, 0, sizeof(v17));
  STRU::STRU((STRU *)v14, v17, 0x40u);
  if ( a1 && a2 && a3 )
  {
    v6 = STRU::Copy((STRU *)v15, a2);
    if ( v6 >= 0 )
    {
      while ( STRU::QueryCCH((STRU *)v15) )
      {
        Str = STRU::QueryStr((STRU *)v15);
        if ( Str[STRU::QueryCCH((STRU *)v15) - 1] != 47 )
          break;
        CCH = STRU::QueryCCH((STRU *)v15);
        STRU::SetLen((STRU *)v15, CCH - 1);
      }
      if ( STRU::IsEmpty((STRU *)v15) )
      {
        *a3 = 0;
        v6 = 0;
      }
      else
      {
        v9 = STRU::QueryStr(a1);
        v6 = STRU::Copy((STRU *)v14, v9);
        if ( v6 >= 0 )
        {
          while ( STRU::QueryCCH((STRU *)v14) )
          {
            v10 = STRU::QueryStr((STRU *)v14);
            if ( v10[STRU::QueryCCH((STRU *)v14) - 1] != 47 )
              break;
            v11 = STRU::QueryCCH((STRU *)v14);
            STRU::SetLen((STRU *)v14, v11 - 1);
          }
          if ( *STRU::QueryStr((STRU *)v15) == 47 || (v6 = STRU::Append((STRU *)v14, L"/"), v6 >= 0) )
          {
            v6 = STRU::Append((STRU *)v14, (const struct STRU *)v15);
            if ( v6 >= 0 )
            {
              v12 = STRU::QueryStr((STRU *)v14);
              v6 = STRU::Copy(a1, v12);
              if ( v6 >= 0 )
                *a3 = 1;
            }
          }
        }
      }
    }
  }
  else
  {
    v6 = -2147024809;
  }
  STRU::~STRU((STRU *)v14);
  STRU::~STRU((STRU *)v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800463c8  mov     [rsp-8+arg_18], rbx
0x1800463cd  push    rbp
0x1800463ce  push    rsi
0x1800463cf  push    rdi
0x1800463d0  lea     rbp, [rsp-0A0h]
0x1800463d8  sub     rsp, 1A0h
0x1800463df  mov     rax, cs:__security_cookie
0x1800463e6  xor     rax, rsp
0x1800463e9  mov     [rbp+0B0h+var_20], rax
0x1800463f0  mov     rdi, r8
0x1800463f3  mov     rbx, rdx
0x1800463f6  mov     rsi, rcx
0x1800463f9  xor     edx, edx; Val
0x1800463fb  mov     r8d, 80h; Size
0x180046401  lea     rcx, [rbp+0B0h+var_120]; void *
0x180046405  call    memset_0
0x18004640a  mov     r8d, 40h ; '@'
0x180046410  lea     rdx, [rbp+0B0h+var_120]
0x180046414  lea     rcx, [rsp+1B0h+var_158]
0x180046419  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004641f  xor     edx, edx; Val
0x180046421  lea     rcx, [rbp+0B0h+var_A0]; void *
0x180046425  mov     r8d, 80h; Size
0x18004642b  call    memset_0
0x180046430  mov     r8d, 40h ; '@'
0x180046436  lea     rdx, [rbp+0B0h+var_A0]
0x18004643a  lea     rcx, [rsp+1B0h+var_190]
0x18004643f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180046445  test    rsi, rsi
0x180046448  jz      loc_1800465B3
0x18004644e  test    rbx, rbx
0x180046451  jz      loc_1800465B3
0x180046457  test    rdi, rdi
0x18004645a  jz      loc_1800465B3
0x180046460  mov     rdx, rbx
0x180046463  lea     rcx, [rsp+1B0h+var_158]
0x180046468  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004646e  mov     ebx, eax
0x180046470  test    eax, eax
0x180046472  js      loc_1800465B8
0x180046478  jmp     short loc_1800464B5
0x18004647a  lea     rcx, [rsp+1B0h+var_158]
0x18004647f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180046485  lea     rcx, [rsp+1B0h+var_158]
0x18004648a  mov     rbx, rax
0x18004648d  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180046493  dec     eax
0x180046495  cmp     word ptr [rbx+rax*2], 2Fh ; '/'
0x18004649a  jnz     short loc_1800464C5
0x18004649c  lea     rcx, [rsp+1B0h+var_158]
0x1800464a1  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800464a7  lea     rcx, [rsp+1B0h+var_158]
0x1800464ac  lea     edx, [rax-1]
0x1800464af  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x1800464b5  lea     rcx, [rsp+1B0h+var_158]
0x1800464ba  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800464c0  cmp     eax, 1
0x1800464c3  jnb     short loc_18004647A
0x1800464c5  lea     rcx, [rsp+1B0h+var_158]
0x1800464ca  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x1800464d0  test    al, al
0x1800464d2  jz      short loc_1800464E1
0x1800464d4  mov     dword ptr [rdi], 0
0x1800464da  xor     ebx, ebx
0x1800464dc  jmp     loc_1800465B8
0x1800464e1  mov     rcx, rsi
0x1800464e4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800464ea  mov     rdx, rax
0x1800464ed  lea     rcx, [rsp+1B0h+var_190]
0x1800464f2  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800464f8  mov     ebx, eax
0x1800464fa  test    eax, eax
0x1800464fc  js      loc_1800465B8
0x180046502  jmp     short loc_18004653F
0x180046504  lea     rcx, [rsp+1B0h+var_190]
0x180046509  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004650f  lea     rcx, [rsp+1B0h+var_190]
0x180046514  mov     rbx, rax
0x180046517  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18004651d  dec     eax
0x18004651f  cmp     word ptr [rbx+rax*2], 2Fh ; '/'
0x180046524  jnz     short loc_18004654F
0x180046526  lea     rcx, [rsp+1B0h+var_190]
0x18004652b  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180046531  lea     rcx, [rsp+1B0h+var_190]
0x180046536  lea     edx, [rax-1]
0x180046539  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18004653f  lea     rcx, [rsp+1B0h+var_190]
0x180046544  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18004654a  cmp     eax, 1
0x18004654d  jnb     short loc_180046504
0x18004654f  lea     rcx, [rsp+1B0h+var_158]
0x180046554  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004655a  cmp     word ptr [rax], 2Fh ; '/'
0x18004655e  jz      short loc_180046578
0x180046560  lea     rdx, asc_18005F044; "/"
0x180046567  lea     rcx, [rsp+1B0h+var_190]
0x18004656c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180046572  mov     ebx, eax
0x180046574  test    eax, eax
0x180046576  js      short loc_1800465B8
0x180046578  lea     rdx, [rsp+1B0h+var_158]
0x18004657d  lea     rcx, [rsp+1B0h+var_190]
0x180046582  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x180046588  mov     ebx, eax
0x18004658a  test    eax, eax
0x18004658c  js      short loc_1800465B8
0x18004658e  lea     rcx, [rsp+1B0h+var_190]
0x180046593  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180046599  mov     rdx, rax
0x18004659c  mov     rcx, rsi
0x18004659f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800465a5  mov     ebx, eax
0x1800465a7  test    eax, eax
0x1800465a9  js      short loc_1800465B8
0x1800465ab  mov     dword ptr [rdi], 1
0x1800465b1  jmp     short loc_1800465B8
0x1800465b3  mov     ebx, 80070057h
0x1800465b8  lea     rcx, [rsp+1B0h+var_190]
0x1800465bd  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800465c3  lea     rcx, [rsp+1B0h+var_158]
0x1800465c8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800465ce  mov     eax, ebx
0x1800465d0  mov     rcx, [rbp+0B0h+var_20]
0x1800465d7  xor     rcx, rsp; StackCookie
0x1800465da  call    __security_check_cookie
0x1800465df  mov     rbx, [rsp+1B0h+arg_18]
0x1800465e7  add     rsp, 1A0h
0x1800465ee  pop     rdi
0x1800465ef  pop     rsi
0x1800465f0  pop     rbp
0x1800465f1  retn
```
