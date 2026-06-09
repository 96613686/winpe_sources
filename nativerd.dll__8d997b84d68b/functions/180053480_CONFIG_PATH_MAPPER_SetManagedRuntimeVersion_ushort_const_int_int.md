# CONFIG_PATH_MAPPER::SetManagedRuntimeVersion(ushort const *,int,int *)

- ea: `0x180053480`
- end: `0x1800536ac`
- name: `?SetManagedRuntimeVersion@CONFIG_PATH_MAPPER@@QEAAJPEBGHPEAH@Z`
- size: `556`
- prototype: `__int64 __fastcall(CONFIG_PATH_MAPPER *__hidden this, const unsigned __int16 *, int, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180050944`

## callees

- `0x180007de0`
- `0x180052ec8`
- `0x180053028`
- `0x180053480`
- `0x1800538c0`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180053507`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005369f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180053507`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005369f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180053542`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800535c3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18005363b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180053542`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800535c3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18005363b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800534d9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800534d9`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180053599`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180053599`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180053550`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005368a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180053550`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005368a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180053574`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800535ae`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180053626`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180053574`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800535ae`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180053626`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180053614`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180053614`

## string_xrefs

- `0x18005359f`: `CONFIG\machine.config`
- `0x18005361a`: `CONFIG\web.config`

## pseudocode

```c
__int64 __fastcall CONFIG_PATH_MAPPER::SetManagedRuntimeVersion(
        CONFIG_PATH_MAPPER *this,
        const unsigned __int16 *a2,
        int appended,
        int *a4)
{
  int v8; // edi
  const unsigned __int16 *VersionPathMapperShouldBeUpdatedWith; // r15
  const unsigned __int16 *Str; // rax
  unsigned int CCH; // r12d
  unsigned __int16 *v13; // rax
  BOOL v14; // eax
  unsigned __int16 *v15; // rax
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v17[56]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v18[256]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(v18, 0, sizeof(v18));
  STRU::STRU((STRU *)v17, v18, 0x100u);
  *a4 = 0;
  v8 = 1;
  v16 = 1;
  if ( !appended && (unsigned int)CONFIG_PATH_MAPPER::IsLoadedRuntimeVersionValidForSpecifiedVersion(this, a2) )
    goto LABEL_3;
  VersionPathMapperShouldBeUpdatedWith = CONFIG_PATH_MAPPER::GetVersionPathMapperShouldBeUpdatedWith(this, a2);
  Str = STRU::QueryStr((CONFIG_PATH_MAPPER *)((char *)this + 56));
  appended = STRU::Copy((STRU *)v17, Str);
  if ( appended < 0 )
    goto LABEL_3;
  appended = CONFIG_PATH_MAPPER::AppendTrailingSlash((struct STRU *)v17);
  if ( appended < 0 )
    goto LABEL_3;
  appended = STRU::Append((STRU *)v17, VersionPathMapperShouldBeUpdatedWith);
  if ( appended < 0 )
    goto LABEL_3;
  appended = CONFIG_PATH_MAPPER::AppendTrailingSlash((struct STRU *)v17);
  if ( appended < 0 )
    goto LABEL_3;
  CCH = STRU::QueryCCH((STRU *)v17);
  appended = STRU::Append((STRU *)v17, L"CONFIG\\machine.config");
  if ( appended < 0 )
    goto LABEL_3;
  v13 = STRU::QueryStr((STRU *)v17);
  appended = CONFIG_PATH_MAPPER::SetPathMapping(this, L"MACHINE", v13, 1, 1, &v16);
  if ( appended < 0 )
    goto LABEL_3;
  v14 = *a4 || v16;
  *a4 = v14;
  STRU::SetLen((STRU *)v17, CCH);
  appended = STRU::Append((STRU *)v17, L"CONFIG\\web.config");
  if ( appended < 0 )
    goto LABEL_3;
  v15 = STRU::QueryStr((STRU *)v17);
  appended = CONFIG_PATH_MAPPER::SetPathMapping(this, L"MACHINE/WEBROOT", v15, 2, 1, &v16);
  if ( appended < 0 )
    goto LABEL_3;
  if ( !*a4 && !v16 )
    v8 = 0;
  *a4 = v8;
  appended = STRU::Copy((CONFIG_PATH_MAPPER *)((char *)this + 112), VersionPathMapperShouldBeUpdatedWith);
  if ( appended < 0 )
  {
LABEL_3:
    STRU::~STRU((STRU *)v17);
    return (unsigned int)appended;
  }
  else
  {
    STRU::~STRU((STRU *)v17);
    return 0;
  }
}

```

## disassembly

```asm
0x180053480  push    rbp
0x180053482  push    rbx
0x180053483  push    rsi
0x180053484  push    rdi
0x180053485  push    r12
0x180053487  push    r14
0x180053489  push    r15
0x18005348b  lea     rbp, [rsp-180h]
0x180053493  sub     rsp, 280h
0x18005349a  mov     rax, cs:__security_cookie
0x1800534a1  xor     rax, rsp
0x1800534a4  mov     [rbp+1B0h+var_40], rax
0x1800534ab  mov     ebx, r8d
0x1800534ae  mov     r15, rdx
0x1800534b1  mov     rsi, rcx
0x1800534b4  xor     edx, edx; Val
0x1800534b6  mov     r8d, 200h; Size
0x1800534bc  lea     rcx, [rsp+2B0h+var_240]; void *
0x1800534c1  mov     r14, r9
0x1800534c4  call    memset_0
0x1800534c9  mov     r8d, 100h
0x1800534cf  lea     rdx, [rsp+2B0h+var_240]
0x1800534d4  lea     rcx, [rsp+2B0h+var_278]
0x1800534d9  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800534df  mov     dword ptr [r14], 0
0x1800534e6  mov     edi, 1
0x1800534eb  mov     [rsp+2B0h+var_280], edi
0x1800534ef  test    ebx, ebx
0x1800534f1  jnz     short loc_180053530
0x1800534f3  mov     rdx, r15; unsigned __int16 *
0x1800534f6  mov     rcx, rsi; this
0x1800534f9  call    ?IsLoadedRuntimeVersionValidForSpecifiedVersion@CONFIG_PATH_MAPPER@@QEAAHPEBG@Z; CONFIG_PATH_MAPPER::IsLoadedRuntimeVersionValidForSpecifiedVersion(ushort const *)
0x1800534fe  test    eax, eax
0x180053500  jz      short loc_180053530
0x180053502  lea     rcx, [rsp+2B0h+var_278]
0x180053507  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18005350d  mov     eax, ebx
0x18005350f  mov     rcx, [rbp+1B0h+var_40]
0x180053516  xor     rcx, rsp; StackCookie
0x180053519  call    __security_check_cookie
0x18005351e  add     rsp, 280h
0x180053525  pop     r15
0x180053527  pop     r14
0x180053529  pop     r12
0x18005352b  pop     rdi
0x18005352c  pop     rsi
0x18005352d  pop     rbx
0x18005352e  pop     rbp
0x18005352f  retn
0x180053530  mov     rdx, r15; unsigned __int16 *
0x180053533  mov     rcx, rsi; this
0x180053536  call    ?GetVersionPathMapperShouldBeUpdatedWith@CONFIG_PATH_MAPPER@@QEAAPEBGPEBG@Z; CONFIG_PATH_MAPPER::GetVersionPathMapperShouldBeUpdatedWith(ushort const *)
0x18005353b  lea     rcx, [rsi+38h]
0x18005353f  mov     r15, rax
0x180053542  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180053548  mov     rdx, rax
0x18005354b  lea     rcx, [rsp+2B0h+var_278]
0x180053550  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180053556  mov     ebx, eax
0x180053558  test    eax, eax
0x18005355a  js      short loc_180053502
0x18005355c  lea     rcx, [rsp+2B0h+var_278]; struct STRU *
0x180053561  call    ?AppendTrailingSlash@CONFIG_PATH_MAPPER@@SAJPEAVSTRU@@@Z; CONFIG_PATH_MAPPER::AppendTrailingSlash(STRU *)
0x180053566  mov     ebx, eax
0x180053568  test    eax, eax
0x18005356a  js      short loc_180053502
0x18005356c  mov     rdx, r15
0x18005356f  lea     rcx, [rsp+2B0h+var_278]
0x180053574  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18005357a  mov     ebx, eax
0x18005357c  test    eax, eax
0x18005357e  js      short loc_180053502
0x180053580  lea     rcx, [rsp+2B0h+var_278]; struct STRU *
0x180053585  call    ?AppendTrailingSlash@CONFIG_PATH_MAPPER@@SAJPEAVSTRU@@@Z; CONFIG_PATH_MAPPER::AppendTrailingSlash(STRU *)
0x18005358a  mov     ebx, eax
0x18005358c  test    eax, eax
0x18005358e  js      loc_180053502
0x180053594  lea     rcx, [rsp+2B0h+var_278]
0x180053599  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18005359f  lea     rdx, aConfigMachineC_0; "CONFIG\\machine.config"
0x1800535a6  mov     r12d, eax
0x1800535a9  lea     rcx, [rsp+2B0h+var_278]
0x1800535ae  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800535b4  mov     ebx, eax
0x1800535b6  test    eax, eax
0x1800535b8  js      loc_180053502
0x1800535be  lea     rcx, [rsp+2B0h+var_278]
0x1800535c3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800535c9  mov     r9d, edi
0x1800535cc  lea     rdx, aMachine; "MACHINE"
0x1800535d3  mov     r8, rax
0x1800535d6  mov     rcx, rsi
0x1800535d9  lea     rax, [rsp+2B0h+var_280]
0x1800535de  mov     [rsp+2B0h+var_288], rax
0x1800535e3  mov     [rsp+2B0h+var_290], edi
0x1800535e7  call    ?SetPathMapping@CONFIG_PATH_MAPPER@@QEAAJPEBG0W4_ALLOW_DEFINITION_LEVEL@@HPEAH@Z; CONFIG_PATH_MAPPER::SetPathMapping(ushort const *,ushort const *,_ALLOW_DEFINITION_LEVEL,int,int *)
0x1800535ec  mov     ebx, eax
0x1800535ee  test    eax, eax
0x1800535f0  js      loc_180053502
0x1800535f6  cmp     dword ptr [r14], 0
0x1800535fa  jnz     short loc_180053607
0x1800535fc  cmp     [rsp+2B0h+var_280], 0
0x180053601  jnz     short loc_180053607
0x180053603  xor     eax, eax
0x180053605  jmp     short loc_180053609
0x180053607  mov     eax, edi
0x180053609  mov     edx, r12d
0x18005360c  mov     [r14], eax
0x18005360f  lea     rcx, [rsp+2B0h+var_278]
0x180053614  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18005361a  lea     rdx, aConfigWebConfi; "CONFIG\\web.config"
0x180053621  lea     rcx, [rsp+2B0h+var_278]
0x180053626  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18005362c  mov     ebx, eax
0x18005362e  test    eax, eax
0x180053630  js      loc_180053502
0x180053636  lea     rcx, [rsp+2B0h+var_278]
0x18005363b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180053641  mov     r9d, 2
0x180053647  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT"
0x18005364e  mov     r8, rax
0x180053651  mov     rcx, rsi
0x180053654  lea     rax, [rsp+2B0h+var_280]
0x180053659  mov     [rsp+2B0h+var_288], rax
0x18005365e  mov     [rsp+2B0h+var_290], edi
0x180053662  call    ?SetPathMapping@CONFIG_PATH_MAPPER@@QEAAJPEBG0W4_ALLOW_DEFINITION_LEVEL@@HPEAH@Z; CONFIG_PATH_MAPPER::SetPathMapping(ushort const *,ushort const *,_ALLOW_DEFINITION_LEVEL,int,int *)
0x180053667  mov     ebx, eax
0x180053669  test    eax, eax
0x18005366b  js      loc_180053502
0x180053671  cmp     dword ptr [r14], 0
0x180053675  jnz     short loc_180053680
0x180053677  cmp     [rsp+2B0h+var_280], 0
0x18005367c  jnz     short loc_180053680
0x18005367e  xor     edi, edi
0x180053680  lea     rcx, [rsi+70h]
0x180053684  mov     [r14], edi
0x180053687  mov     rdx, r15
0x18005368a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180053690  mov     ebx, eax
0x180053692  test    eax, eax
0x180053694  js      loc_180053502
0x18005369a  lea     rcx, [rsp+2B0h+var_278]
0x18005369f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800536a5  xor     eax, eax
0x1800536a7  jmp     loc_18005350F
```
