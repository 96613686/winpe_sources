# std::_Regex_traits<ushort>::_Cache_locale(void)

- ea: `0x1800209e0`
- end: `0x180020bff`
- name: `?_Cache_locale@?$_Regex_traits@G@std@@AEAAXXZ`
- size: `543`
- prototype: `void __fastcall(struct std::_Facet_base **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001a3a0`
- `0x18002e434`

## callees

- `0x1800036ec`
- `0x1800209e0`
- `0x18002265c`
- `0x18002377c`
- `0x180033010`

## import_xrefs

- `msvcp_win!?id@?$collate@G@std@@2V0locale@2@A` at `0x180020a0e`
- `msvcp_win!?_Getcat@?$ctype@G@std@@SA_KPEAPEBVfacet@locale@2@PEBV42@@Z` at `0x180020b9e`
- `msvcp_win!?_Getcat@?$ctype@G@std@@SA_KPEAPEBVfacet@locale@2@PEBV42@@Z` at `0x180020b9e`
- `msvcp_win!?_Id_cnt@id@locale@std@@0HA` at `0x180020a2d`
- `msvcp_win!?_Id_cnt@id@locale@std@@0HA` at `0x180020ab7`
- `msvcp_win!?id@?$ctype@G@std@@2V0locale@2@A` at `0x180020a98`
- `msvcp_win!?_Getgloballocale@locale@std@@CAPEAV_Locimp@12@XZ` at `0x180020b04`
- `msvcp_win!?_Getgloballocale@locale@std@@CAPEAV_Locimp@12@XZ` at `0x180020b74`
- `msvcp_win!?_Getgloballocale@locale@std@@CAPEAV_Locimp@12@XZ` at `0x180020b04`
- `msvcp_win!?_Getgloballocale@locale@std@@CAPEAV_Locimp@12@XZ` at `0x180020b74`
- `msvcp_win!??0_Lockit@std@@QEAA@H@Z` at `0x1800209fc`
- `msvcp_win!??0_Lockit@std@@QEAA@H@Z` at `0x180020a21`
- `msvcp_win!??0_Lockit@std@@QEAA@H@Z` at `0x180020a86`
- `msvcp_win!??0_Lockit@std@@QEAA@H@Z` at `0x180020aab`
- `msvcp_win!??0_Lockit@std@@QEAA@H@Z` at `0x1800209fc`
- `msvcp_win!??0_Lockit@std@@QEAA@H@Z` at `0x180020a21`
- `msvcp_win!??0_Lockit@std@@QEAA@H@Z` at `0x180020a86`
- `msvcp_win!??0_Lockit@std@@QEAA@H@Z` at `0x180020aab`
- `msvcp_win!??1_Lockit@std@@QEAA@XZ` at `0x180020a40`
- `msvcp_win!??1_Lockit@std@@QEAA@XZ` at `0x180020a77`
- `msvcp_win!??1_Lockit@std@@QEAA@XZ` at `0x180020aca`
- `msvcp_win!??1_Lockit@std@@QEAA@XZ` at `0x180020bd8`
- `msvcp_win!??1_Lockit@std@@QEAA@XZ` at `0x180020a40`
- `msvcp_win!??1_Lockit@std@@QEAA@XZ` at `0x180020a77`
- `msvcp_win!??1_Lockit@std@@QEAA@XZ` at `0x180020aca`
- `msvcp_win!??1_Lockit@std@@QEAA@XZ` at `0x180020bd8`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall std::_Regex_traits<unsigned short>::_Cache_locale(struct std::_Facet_base **a1)
{
  struct std::_Facet_base *v2; // rbx
  struct std::_Facet_base *v3; // rdx
  __int64 v4; // rdi
  struct std::_Facet_base *v5; // rcx
  struct std::_Facet_base *v6; // rcx
  __int64 v7; // rdi
  struct std::_Facet_base *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  struct std::_Facet_base *v11; // rbx
  struct std::_Facet_base *v12; // [rsp+50h] [rbp+30h] BYREF
  char v13; // [rsp+58h] [rbp+38h] BYREF
  struct std::_Facet_base *v14; // [rsp+60h] [rbp+40h] BYREF

  std::_Lockit::_Lockit((std::_Lockit *)&v13, 0);
  v2 = (struct std::_Facet_base *)std::_Facetptr<std::collate<unsigned short>>::_Psave;
  v14 = (struct std::_Facet_base *)std::_Facetptr<std::collate<unsigned short>>::_Psave;
  if ( !std::collate<unsigned short>::id )
  {
    std::_Lockit::_Lockit((std::_Lockit *)&v12, 0);
    std::collate<unsigned short>::id = ++std::locale::id::_Id_cnt;
    std::_Lockit::~_Lockit((std::_Lockit *)&v12);
  }
  v3 = a1[3];
  v4 = 8LL * std::collate<unsigned short>::id;
  if ( std::collate<unsigned short>::id >= *((_QWORD *)v3 + 3) )
  {
    v5 = 0;
  }
  else
  {
    v5 = *(struct std::_Facet_base **)(v4 + *((_QWORD *)v3 + 2));
    if ( v5 )
    {
LABEL_5:
      v2 = v5;
      goto LABEL_6;
    }
  }
  if ( *((_BYTE *)v3 + 36) )
  {
    v9 = std::locale::_Getgloballocale(v5);
    if ( std::collate<unsigned short>::id >= *(_QWORD *)(v9 + 24) )
      goto LABEL_16;
    v5 = *(struct std::_Facet_base **)(v4 + *(_QWORD *)(v9 + 16));
  }
  if ( v5 )
    goto LABEL_5;
LABEL_16:
  if ( !v2 )
  {
    if ( std::collate<unsigned short>::_Getcat(&v14, a1 + 2) == -1 )
      std::_Throw_bad_cast();
    v2 = v14;
    v12 = v14;
    std::_Facet_Register(v14);
    (*(void (__fastcall **)(struct std::_Facet_base *))(*(_QWORD *)v2 + 8LL))(v2);
    std::_Facetptr<std::collate<unsigned short>>::_Psave = (__int64)v2;
  }
LABEL_6:
  std::_Lockit::~_Lockit((std::_Lockit *)&v13);
  *a1 = v2;
  std::_Lockit::_Lockit((std::_Lockit *)&v13, 0);
  v14 = (struct std::_Facet_base *)std::_Facetptr<std::ctype<unsigned short>>::_Psave;
  if ( !std::ctype<unsigned short>::id )
  {
    std::_Lockit::_Lockit((std::_Lockit *)&v12, 0);
    std::ctype<unsigned short>::id = ++std::locale::id::_Id_cnt;
    std::_Lockit::~_Lockit((std::_Lockit *)&v12);
  }
  v6 = a1[3];
  v7 = 8LL * std::ctype<unsigned short>::id;
  if ( std::ctype<unsigned short>::id >= *((_QWORD *)v6 + 3) )
  {
    v8 = 0;
  }
  else
  {
    v8 = *(struct std::_Facet_base **)(v7 + *((_QWORD *)v6 + 2));
    if ( v8 )
      goto LABEL_27;
  }
  if ( !*((_BYTE *)v6 + 36) )
    goto LABEL_23;
  v10 = std::locale::_Getgloballocale(v6);
  if ( std::ctype<unsigned short>::id < *(_QWORD *)(v10 + 24) )
  {
    v8 = *(struct std::_Facet_base **)(v7 + *(_QWORD *)(v10 + 16));
LABEL_23:
    if ( v8 )
      goto LABEL_27;
  }
  v8 = v14;
  if ( !v14 )
  {
    if ( std::ctype<unsigned short>::_Getcat(&v14, a1 + 2) == -1 )
      std::_Throw_bad_cast();
    v11 = v14;
    v12 = v14;
    std::_Facet_Register(v14);
    (*(void (__fastcall **)(struct std::_Facet_base *))(*(_QWORD *)v11 + 8LL))(v11);
    v8 = v14;
    std::_Facetptr<std::ctype<unsigned short>>::_Psave = (__int64)v14;
  }
LABEL_27:
  std::_Lockit::~_Lockit((std::_Lockit *)&v13);
  a1[1] = v8;
}

```

## disassembly

```asm
0x1800209e0  mov     [rsp-28h+arg_18], rbx
0x1800209e5  push    rbp
0x1800209e6  push    rsi
0x1800209e7  push    rdi
0x1800209e8  push    r14
0x1800209ea  push    r15
0x1800209ec  mov     rbp, rsp
0x1800209ef  sub     rsp, 20h
0x1800209f3  mov     r15, rcx
0x1800209f6  xor     edx, edx
0x1800209f8  lea     rcx, [rbp+arg_8]
0x1800209fc  call    cs:__imp_??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x180020a02  nop
0x180020a03  mov     rbx, cs:?_Psave@?$_Facetptr@V?$collate@G@std@@@std@@2PEBVfacet@locale@2@EB; std::locale::facet const * const std::_Facetptr<std::collate<ushort>>::_Psave
0x180020a0a  mov     [rbp+arg_10], rbx
0x180020a0e  mov     rdi, cs:__imp_?id@?$collate@G@std@@2V0locale@2@A; std::locale::id std::collate<ushort>::id
0x180020a15  cmp     qword ptr [rdi], 0
0x180020a19  jnz     short loc_180020A46
0x180020a1b  xor     edx, edx
0x180020a1d  lea     rcx, [rbp+arg_0]
0x180020a21  call    cs:__imp_??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x180020a27  cmp     qword ptr [rdi], 0
0x180020a2b  jnz     short loc_180020A3C
0x180020a2d  mov     rax, cs:__imp_?_Id_cnt@id@locale@std@@0HA; int std::locale::id::_Id_cnt
0x180020a34  inc     dword ptr [rax]
0x180020a36  movsxd  rax, dword ptr [rax]
0x180020a39  mov     [rdi], rax
0x180020a3c  lea     rcx, [rbp+arg_0]
0x180020a40  call    cs:__imp_??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x180020a46  mov     rsi, [rdi]
0x180020a49  mov     rdx, [r15+18h]
0x180020a4d  lea     rdi, ds:0[rsi*8]
0x180020a55  cmp     rsi, [rdx+18h]
0x180020a59  jnb     loc_180020AFC
0x180020a5f  mov     rax, [rdx+10h]
0x180020a63  mov     rcx, [rdi+rax]
0x180020a67  test    rcx, rcx
0x180020a6a  jz      loc_180020AFE
0x180020a70  mov     rbx, rcx
0x180020a73  lea     rcx, [rbp+arg_8]
0x180020a77  call    cs:__imp_??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x180020a7d  mov     [r15], rbx
0x180020a80  xor     edx, edx
0x180020a82  lea     rcx, [rbp+arg_8]
0x180020a86  call    cs:__imp_??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x180020a8c  nop
0x180020a8d  mov     rax, cs:?_Psave@?$_Facetptr@V?$ctype@G@std@@@std@@2PEBVfacet@locale@2@EB; std::locale::facet const * const std::_Facetptr<std::ctype<ushort>>::_Psave
0x180020a94  mov     [rbp+arg_10], rax
0x180020a98  mov     rbx, cs:__imp_?id@?$ctype@G@std@@2V0locale@2@A; std::locale::id std::ctype<ushort>::id
0x180020a9f  cmp     qword ptr [rbx], 0
0x180020aa3  jnz     short loc_180020AD0
0x180020aa5  xor     edx, edx
0x180020aa7  lea     rcx, [rbp+arg_0]
0x180020aab  call    cs:__imp_??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x180020ab1  cmp     qword ptr [rbx], 0
0x180020ab5  jnz     short loc_180020AC6
0x180020ab7  mov     rax, cs:__imp_?_Id_cnt@id@locale@std@@0HA; int std::locale::id::_Id_cnt
0x180020abe  inc     dword ptr [rax]
0x180020ac0  movsxd  rax, dword ptr [rax]
0x180020ac3  mov     [rbx], rax
0x180020ac6  lea     rcx, [rbp+arg_0]
0x180020aca  call    cs:__imp_??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x180020ad0  mov     rsi, [rbx]
0x180020ad3  mov     rcx, [r15+18h]
0x180020ad7  lea     rdi, ds:0[rsi*8]
0x180020adf  cmp     rsi, [rcx+18h]
0x180020ae3  jnb     loc_180020B6C
0x180020ae9  mov     rax, [rcx+10h]
0x180020aed  mov     rbx, [rdi+rax]
0x180020af1  test    rbx, rbx
0x180020af4  jnz     loc_180020BD4
0x180020afa  jmp     short loc_180020B6E
0x180020afc  xor     ecx, ecx
0x180020afe  cmp     byte ptr [rdx+24h], 0
0x180020b02  jz      short loc_180020B18
0x180020b04  call    cs:__imp_?_Getgloballocale@locale@std@@CAPEAV_Locimp@12@XZ; std::locale::_Getgloballocale(void)
0x180020b0a  cmp     rsi, [rax+18h]
0x180020b0e  jnb     short loc_180020B21
0x180020b10  mov     rax, [rax+10h]
0x180020b14  mov     rcx, [rdi+rax]
0x180020b18  test    rcx, rcx
0x180020b1b  jnz     loc_180020A70
0x180020b21  test    rbx, rbx
0x180020b24  jnz     loc_180020A73
0x180020b2a  lea     rdx, [r15+10h]
0x180020b2e  lea     rcx, [rbp+arg_10]
0x180020b32  call    ?_Getcat@?$collate@G@std@@SA_KPEAPEBVfacet@locale@2@PEBV42@@Z; std::collate<ushort>::_Getcat(std::locale::facet const * *,std::locale const *)
0x180020b37  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020b3b  jz      loc_180020BF9
0x180020b41  mov     rbx, [rbp+arg_10]
0x180020b45  mov     [rbp+arg_0], rbx
0x180020b49  mov     rcx, rbx; struct std::_Facet_base *
0x180020b4c  call    ?_Facet_Register@std@@YAXPEAV_Facet_base@1@@Z; std::_Facet_Register(std::_Facet_base *)
0x180020b51  mov     rax, [rbx]
0x180020b54  mov     rcx, rbx
0x180020b57  mov     rax, [rax+8]
0x180020b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b60  mov     cs:?_Psave@?$_Facetptr@V?$collate@G@std@@@std@@2PEBVfacet@locale@2@EB, rbx; std::locale::facet const * const std::_Facetptr<std::collate<ushort>>::_Psave
0x180020b67  jmp     loc_180020A73
0x180020b6c  xor     ebx, ebx
0x180020b6e  cmp     byte ptr [rcx+24h], 0
0x180020b72  jz      short loc_180020B88
0x180020b74  call    cs:__imp_?_Getgloballocale@locale@std@@CAPEAV_Locimp@12@XZ; std::locale::_Getgloballocale(void)
0x180020b7a  cmp     rsi, [rax+18h]
0x180020b7e  jnb     short loc_180020B8D
0x180020b80  mov     rax, [rax+10h]
0x180020b84  mov     rbx, [rdi+rax]
0x180020b88  test    rbx, rbx
0x180020b8b  jnz     short loc_180020BD4
0x180020b8d  mov     rbx, [rbp+arg_10]
0x180020b91  test    rbx, rbx
0x180020b94  jnz     short loc_180020BD4
0x180020b96  lea     rdx, [r15+10h]
0x180020b9a  lea     rcx, [rbp+arg_10]
0x180020b9e  call    cs:__imp_?_Getcat@?$ctype@G@std@@SA_KPEAPEBVfacet@locale@2@PEBV42@@Z; std::ctype<ushort>::_Getcat(std::locale::facet const * *,std::locale const *)
0x180020ba4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020ba8  jz      short loc_180020BF3
0x180020baa  mov     rbx, [rbp+arg_10]
0x180020bae  mov     [rbp+arg_0], rbx
0x180020bb2  mov     rcx, rbx; struct std::_Facet_base *
0x180020bb5  call    ?_Facet_Register@std@@YAXPEAV_Facet_base@1@@Z; std::_Facet_Register(std::_Facet_base *)
0x180020bba  mov     rax, [rbx]
0x180020bbd  mov     rcx, rbx
0x180020bc0  mov     rax, [rax+8]
0x180020bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bc9  mov     rbx, [rbp+arg_10]
0x180020bcd  mov     cs:?_Psave@?$_Facetptr@V?$ctype@G@std@@@std@@2PEBVfacet@locale@2@EB, rbx; std::locale::facet const * const std::_Facetptr<std::ctype<ushort>>::_Psave
0x180020bd4  lea     rcx, [rbp+arg_8]
0x180020bd8  call    cs:__imp_??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x180020bde  mov     [r15+8], rbx
0x180020be2  mov     rbx, [rsp+20h+arg_18]
0x180020be7  add     rsp, 20h
0x180020beb  pop     r15
0x180020bed  pop     r14
0x180020bef  pop     rdi
0x180020bf0  pop     rsi
0x180020bf1  pop     rbp
0x180020bf2  retn
0x180020bf3  call    ?_Throw_bad_cast@std@@YAXXZ; std::_Throw_bad_cast(void)
0x180020bf9  call    ?_Throw_bad_cast@std@@YAXXZ; std::_Throw_bad_cast(void)
```
