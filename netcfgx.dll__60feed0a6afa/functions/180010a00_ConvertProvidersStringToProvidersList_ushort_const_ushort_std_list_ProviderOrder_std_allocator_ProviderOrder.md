# ConvertProvidersStringToProvidersList(ushort const *,ushort,std::list<ProviderOrder,std::allocator<ProviderOrder>> &)

- ea: `0x180010a00`
- end: `0x180010f4d`
- name: `?ConvertProvidersStringToProvidersList@@YAJPEBGGAEAV?$list@UProviderOrder@@V?$allocator@UProviderOrder@@@std@@@std@@@Z`
- size: `1357`
- prototype: `int __fastcall(unsigned __int16 *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180011270`

## callees

- `0x180001f90`
- `0x180001fec`
- `0x1800030e0`
- `0x1800069b8`
- `0x180007b3c`
- `0x180007d38`
- `0x180007d80`
- `0x180007f78`
- `0x180007fe4`
- `0x180008548`
- `0x180008560`
- `0x1800087e0`
- `0x180010630`
- `0x18001084c`
- `0x180010a00`
- `0x180010f54`
- `0x1800123c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180010b44`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180010b44`

## string_xrefs

- `0x180010d9f`: `System\CurrentControlSet\Services\%s\NetworkProvider`

## pseudocode

```c
int __fastcall ConvertProvidersStringToProvidersList(unsigned __int16 *a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // r15
  _QWORD **v5; // rcx
  _QWORD *v6; // r14
  _QWORD *v7; // rdi
  _QWORD *v8; // r13
  int result; // eax
  int NetworkProviderName; // r14d
  __int64 v11; // rcx
  void *v12; // rax
  __int64 v13; // rdx
  const wchar_t *v14; // r11
  const wchar_t *i; // r12
  wchar_t *v16; // rax
  unsigned __int64 v17; // r14
  unsigned __int64 v18; // rdi
  __int64 v19; // rcx
  _BYTE *v20; // rbx
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rdx
  void *v23; // rcx
  int v24; // eax
  unsigned int v25; // ecx
  __int128 *v26; // r9
  _QWORD **v27; // rcx
  _QWORD *v28; // r12
  _QWORD *v29; // rdi
  void *v30; // [rsp+20h] [rbp-318h]
  HKEY hKey; // [rsp+28h] [rbp-310h] BYREF
  HKEY v32; // [rsp+30h] [rbp-308h] BYREF
  _BYTE *v33; // [rsp+38h] [rbp-300h] BYREF
  wchar_t *v34; // [rsp+40h] [rbp-2F8h]
  _QWORD *v35; // [rsp+48h] [rbp-2F0h]
  void *lpMem; // [rsp+50h] [rbp-2E8h]
  _QWORD *v37; // [rsp+58h] [rbp-2E0h]
  _BYTE v38[32]; // [rsp+60h] [rbp-2D8h] BYREF
  _BYTE v39[32]; // [rsp+80h] [rbp-2B8h] BYREF
  unsigned int v40; // [rsp+A0h] [rbp-298h]
  char v41; // [rsp+A4h] [rbp-294h]
  __int128 v42; // [rsp+A8h] [rbp-290h] BYREF
  unsigned __int64 v43; // [rsp+B8h] [rbp-280h]
  __int64 v44; // [rsp+C0h] [rbp-278h]
  __int128 v45; // [rsp+D0h] [rbp-268h] BYREF
  unsigned __int64 v46; // [rsp+E0h] [rbp-258h]
  unsigned __int64 v47; // [rsp+E8h] [rbp-250h]
  __int128 v48; // [rsp+F0h] [rbp-248h] BYREF
  __int64 v49; // [rsp+100h] [rbp-238h]
  __int64 v50; // [rsp+108h] [rbp-230h]
  unsigned int v51; // [rsp+110h] [rbp-228h] BYREF
  char v52; // [rsp+114h] [rbp-224h]
  unsigned __int16 v53[240]; // [rsp+120h] [rbp-218h] BYREF

  v3 = a3;
  v35 = a3;
  v32 = 0;
  v5 = (_QWORD **)*a3;
  **(_QWORD **)(*a3 + 8LL) = 0;
  v6 = *v5;
  if ( *v5 )
  {
    do
    {
      v7 = (_QWORD *)*v6;
      std::wstring::~wstring(v6 + 6);
      std::wstring::~wstring(v6 + 2);
      operator delete(v6, 0x58u);
      v6 = v7;
    }
    while ( v7 );
  }
  *(_QWORD *)*v3 = *v3;
  *(_QWORD *)(*v3 + 8LL) = *v3;
  v8 = v3 + 1;
  v37 = v3 + 1;
  v3[1] = 0;
  if ( !a1 )
    return -2147024882;
  result = HrRegOpenKeyEx(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\NetworkProvider\\ProviderOrder",
             0x20019u,
             &v32);
  NetworkProviderName = result;
  if ( !result )
  {
    v11 = -1;
    do
      ++v11;
    while ( a1[v11] );
    v12 = MemAlloc(saturated_mul(v11 + 1, 2u));
    lpMem = v12;
    if ( v12 )
    {
      v13 = -1;
      do
        ++v13;
      while ( a1[v13] );
      StringCchCopyW((unsigned __int16 *)v12, v13 + 1, a1);
      for ( i = v14; *i && !NetworkProviderName; i = v16 + 1 )
      {
        v16 = wcschr(i, 0x2Cu);
        v34 = v16;
        if ( v16 )
          *v16 = 0;
        if ( *i )
        {
          hKey = 0;
          v45 = 0;
          v46 = 0;
          v17 = 7;
          v47 = 7;
          LOWORD(v45) = 0;
          v48 = 0;
          v49 = 0;
          v50 = 7;
          LOWORD(v48) = 0;
          v51 = 0;
          v52 = 0;
          v42 = 0;
          v43 = 0;
          v44 = 0;
          v18 = -1;
          do
            ++v18;
          while ( i[v18] );
          if ( __eh34_try(-1, 0) )
          {
            __eh34_scope_strut(0);
            v19 = 0x7FFFFFFFFFFFFFFELL;
            if ( v18 > 0x7FFFFFFFFFFFFFFELL )
              std::_Xlen_string();
            if ( v18 > 7 )
            {
              v21 = v18 | 7;
              if ( (v18 | 7) <= 0x7FFFFFFFFFFFFFFELL )
              {
                v19 = 10;
                if ( v21 < 0xA )
                  v21 = 10;
              }
              else
              {
                v21 = 0x7FFFFFFFFFFFFFFELL;
              }
              v33 = (_BYTE *)v21;
              v30 = (void *)std::wstring::_Allocate_for_capacity<0>(v19, &v33);
              *(_QWORD *)&v42 = v30;
              memcpy_0(v30, i, 2 * v18);
              *((_WORD *)v30 + v18) = 0;
              v17 = v47;
              v20 = v33;
            }
            else
            {
              v43 = v18;
              v44 = 7;
              memcpy_0(&v42, i, 2 * v18);
              *((_WORD *)&v42 + v18) = 0;
              v20 = (_BYTE *)v44;
              v18 = v43;
            }
            if ( v17 > 7 )
            {
              v22 = 2 * v17 + 2;
              v23 = (void *)v45;
              if ( v22 >= 0x1000 )
              {
                if ( (unsigned __int64)(v45 - *(_QWORD *)(v45 - 8) - 8) > 0x1F )
                  __fastfail(5u);
                v22 = 2 * v17 + 41;
                v23 = *(void **)(v45 - 8);
              }
              operator delete(v23, v22);
            }
            v45 = v42;
            v46 = v18;
            v47 = (unsigned __int64)v20;
            v43 = 0;
            v44 = 7;
            LOWORD(v42) = 0;
            std::wstring::~wstring(&v42);
            v24 = HrRegQueryDword(v32, i, &v51);
            v25 = v51;
            if ( v24 == -2147024894 )
              v25 = 0x7FFFFFFF;
            v51 = v25;
            NetworkProviderName = 0;
            if ( v24 != -2147024894 )
              NetworkProviderName = v24;
            if ( !NetworkProviderName )
            {
              v26 = &v45;
              if ( v47 > 7 )
                v26 = (__int128 *)v45;
              StringCchPrintfW(v53, 0xEAu, L"System\\CurrentControlSet\\Services\\%s\\NetworkProvider", v26);
              NetworkProviderName = HrRegOpenKeyEx(HKEY_LOCAL_MACHINE, v53, 0x20019u, &hKey);
              if ( !NetworkProviderName )
              {
                NetworkProviderName = HrGetNetworkProviderName(hKey, (char **)&v48);
                if ( !NetworkProviderName )
                {
                  v33 = v38;
                  std::wstring::wstring(v38, &v45);
                  std::wstring::wstring(v39, &v48);
                  v40 = v51;
                  v41 = v52;
                  AddToProviderOrderList(v3, v38);
                }
                ATL::CRegKey::~CRegKey((ATL::CRegKey *)&hKey);
              }
            }
            std::wstring::~wstring(&v48);
            std::wstring::~wstring(&v45);
          }
          if ( __eh34_catch(0) )
          {
            if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
            {
              ATL::CRegKey::~CRegKey((ATL::CRegKey *)&hKey);
              NetworkProviderName = -2147024882;
              v3 = v35;
              __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180010E81);
            }
          }
          v16 = v34;
        }
        if ( !v16 )
          break;
      }
      MemFree(lpMem);
      v8 = v37;
    }
    ATL::CRegKey::~CRegKey((ATL::CRegKey *)&v32);
    if ( NetworkProviderName )
    {
      v27 = (_QWORD **)*v3;
      **(_QWORD **)(*v3 + 8LL) = 0;
      v28 = *v27;
      if ( *v27 )
      {
        do
        {
          v29 = (_QWORD *)*v28;
          std::wstring::~wstring(v28 + 6);
          std::wstring::~wstring(v28 + 2);
          operator delete(v28, 0x58u);
          v28 = v29;
        }
        while ( v29 );
      }
      *(_QWORD *)*v3 = *v3;
      *(_QWORD *)(*v3 + 8LL) = *v3;
      *v8 = 0;
    }
    return NetworkProviderName;
  }
  return result;
}

```

## disassembly

```asm
0x180010a00  mov     [rsp+arg_8], rbx
0x180010a05  mov     [rsp+arg_18], rsi
0x180010a0a  push    rdi
0x180010a0b  push    r12
0x180010a0d  push    r13
0x180010a0f  push    r14
0x180010a11  push    r15
0x180010a13  sub     rsp, 310h
0x180010a1a  mov     rax, cs:__security_cookie
0x180010a21  xor     rax, rsp
0x180010a24  mov     [rsp+338h+var_38], rax
0x180010a2c  mov     r15, r8
0x180010a2f  mov     r12, rcx
0x180010a32  mov     [rsp+338h+var_2F0], r8
0x180010a37  xor     esi, esi
0x180010a39  mov     [rsp+338h+var_308], rsi
0x180010a3e  mov     rcx, [r8]
0x180010a41  mov     rax, [rcx+8]
0x180010a45  mov     [rax], rsi
0x180010a48  mov     r14, [rcx]
0x180010a4b  test    r14, r14
0x180010a4e  jz      short loc_180010A7A
0x180010a50  mov     rdi, [r14]
0x180010a53  lea     rcx, [r14+30h]
0x180010a57  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010a5c  lea     rcx, [r14+10h]
0x180010a60  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010a65  mov     edx, 58h ; 'X'; unsigned __int64
0x180010a6a  mov     rcx, r14; void *
0x180010a6d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010a72  mov     r14, rdi
0x180010a75  test    rdi, rdi
0x180010a78  jnz     short loc_180010A50
0x180010a7a  mov     rax, [r15]
0x180010a7d  mov     [rax], rax
0x180010a80  mov     rax, [r15]
0x180010a83  mov     [rax+8], rax
0x180010a87  lea     r13, [r15+8]
0x180010a8b  mov     [rsp+338h+var_2E0], r13
0x180010a90  mov     [r13+0], rsi
0x180010a94  test    r12, r12
0x180010a97  jnz     short loc_180010AA3
0x180010a99  mov     eax, 8007000Eh
0x180010a9e  jmp     loc_180010F19
0x180010aa3  lea     r9, [rsp+338h+var_308]; HKEY *
0x180010aa8  mov     r8d, 20019h; unsigned int
0x180010aae  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Net"...
0x180010ab5  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180010abc  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x180010ac1  mov     r14d, eax
0x180010ac4  test    eax, eax
0x180010ac6  jnz     loc_180010F19
0x180010acc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180010ad0  mov     rcx, rbx
0x180010ad3  inc     rcx
0x180010ad6  cmp     [r12+rcx*2], si
0x180010adb  jnz     short loc_180010AD3
0x180010add  inc     rcx
0x180010ae0  mov     eax, 2
0x180010ae5  mul     rcx
0x180010ae8  cmovb   rax, rbx
0x180010aec  mov     rcx, rax; unsigned __int64
0x180010aef  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180010af4  mov     r11, rax
0x180010af7  mov     [rsp+338h+lpMem], rax
0x180010afc  test    rax, rax
0x180010aff  jz      loc_180010EB7
0x180010b05  mov     rdx, rbx
0x180010b08  inc     rdx
0x180010b0b  cmp     [r12+rdx*2], si
0x180010b10  jnz     short loc_180010B08
0x180010b12  inc     rdx; unsigned __int64
0x180010b15  mov     r8, r12; unsigned __int16 *
0x180010b18  mov     rcx, r11; unsigned __int16 *
0x180010b1b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010b20  mov     r12, r11
0x180010b23  mov     r13d, 7
0x180010b29  cmp     [r12], si
0x180010b2e  jz      loc_180010EA8
0x180010b34  test    r14d, r14d
0x180010b37  jnz     loc_180010EA8
0x180010b3d  lea     edx, [r14+2Ch]; Ch
0x180010b41  mov     rcx, r12; Str
0x180010b44  call    cs:__imp_wcschr
0x180010b4a  mov     [rsp+338h+var_2F8], rax
0x180010b4f  test    rax, rax
0x180010b52  jz      short loc_180010B57
0x180010b54  mov     [rax], si
0x180010b57  cmp     [r12], si
0x180010b5c  jz      loc_180010E9A
0x180010b62  mov     [rsp+338h+hKey], rsi
0x180010b67  xorps   xmm0, xmm0
0x180010b6a  movups  [rsp+338h+var_268], xmm0
0x180010b72  mov     [rsp+338h+var_258], rsi
0x180010b7a  mov     r14, r13
0x180010b7d  mov     [rsp+338h+var_250], r13
0x180010b85  mov     word ptr [rsp+338h+var_268], si
0x180010b8d  movups  [rsp+338h+var_248], xmm0
0x180010b95  mov     [rsp+338h+var_238], rsi
0x180010b9d  mov     [rsp+338h+var_230], r13
0x180010ba5  mov     word ptr [rsp+338h+var_248], si
0x180010bad  mov     [rsp+338h+var_228], esi
0x180010bb4  mov     [rsp+338h+var_224], sil
0x180010bbc  movups  [rsp+338h+var_290], xmm0
0x180010bc4  mov     [rsp+338h+var_280], rsi
0x180010bcc  mov     [rsp+338h+var_278], rsi
0x180010bd4  mov     rdi, rbx
0x180010bd7  inc     rdi
0x180010bda  cmp     [r12+rdi*2], si
0x180010bdf  jnz     short loc_180010BD7
0x180010be1  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180010beb  cmp     rdi, rcx
0x180010bee  ja      loc_180010F46
0x180010bf4  cmp     rdi, r13
0x180010bf7  ja      short loc_180010C3A
0x180010bf9  mov     [rsp+338h+var_280], rdi
0x180010c01  mov     [rsp+338h+var_278], r13
0x180010c09  lea     rbx, [rdi+rdi]
0x180010c0d  mov     r8, rbx; Size
0x180010c10  mov     rdx, r12; Src
0x180010c13  lea     rcx, [rsp+338h+var_290]; void *
0x180010c1b  call    memcpy_0
0x180010c20  mov     word ptr [rsp+rbx+338h+var_290], si
0x180010c28  mov     rbx, [rsp+338h+var_278]
0x180010c30  mov     rdi, [rsp+338h+var_280]
0x180010c38  jmp     short loc_180010CB2
0x180010c3a  mov     rax, rdi
0x180010c3d  or      rax, r13
0x180010c40  cmp     rax, rcx
0x180010c43  jbe     short loc_180010C4A
0x180010c45  mov     rax, rcx
0x180010c48  jmp     short loc_180010C56
0x180010c4a  mov     ecx, 0Ah
0x180010c4f  cmp     rax, rcx
0x180010c52  cmovb   rax, rcx
0x180010c56  mov     [rsp+338h+var_300], rax
0x180010c5b  lea     rdx, [rsp+338h+var_300]
0x180010c60  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180010c65  mov     r14, rax
0x180010c68  mov     [rsp+338h+var_318], rax
0x180010c6d  mov     word ptr [rsp+338h+var_290], r14w
0x180010c76  mov     ecx, dword ptr [rsp+338h+var_318+2]
0x180010c7a  mov     dword ptr [rsp+338h+var_290+2], ecx
0x180010c81  movzx   ecx, word ptr [rsp+338h+var_318+6]
0x180010c86  mov     word ptr [rsp+338h+var_290+6], cx
0x180010c8e  lea     rbx, [rdi+rdi]
0x180010c92  mov     r8, rbx; Size
0x180010c95  mov     rdx, r12; Src
0x180010c98  mov     rcx, rax; void *
0x180010c9b  call    memcpy_0
0x180010ca0  mov     [rbx+r14], si
0x180010ca5  mov     r14, [rsp+338h+var_250]
0x180010cad  mov     rbx, [rsp+338h+var_300]
0x180010cb2  cmp     r14, r13
0x180010cb5  jbe     short loc_180010CF1
0x180010cb7  lea     rdx, ds:2[r14*2]
0x180010cbf  mov     rcx, qword ptr [rsp+338h+var_268]
0x180010cc7  cmp     rdx, 1000h
0x180010cce  jb      short loc_180010CEC
0x180010cd0  mov     rax, [rcx-8]
0x180010cd4  sub     rcx, rax
0x180010cd7  sub     rcx, 8
0x180010cdb  cmp     rcx, 1Fh
0x180010cdf  ja      loc_180010E7A
0x180010ce5  add     rdx, 27h ; '''; unsigned __int64
0x180010ce9  mov     rcx, rax; void *
0x180010cec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010cf1  mov     rax, qword ptr [rsp+338h+var_290]
0x180010cf9  mov     qword ptr [rsp+338h+var_268], rax
0x180010d01  mov     rax, qword ptr [rsp+338h+var_290+8]
0x180010d09  mov     qword ptr [rsp+338h+var_268+8], rax
0x180010d11  mov     [rsp+338h+var_258], rdi
0x180010d19  mov     [rsp+338h+var_250], rbx
0x180010d21  mov     [rsp+338h+var_280], rsi
0x180010d29  mov     [rsp+338h+var_278], r13
0x180010d31  mov     word ptr [rsp+338h+var_290], si
0x180010d39  lea     rcx, [rsp+338h+var_290]
0x180010d41  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010d46  lea     r8, [rsp+338h+var_228]; unsigned int *
0x180010d4e  mov     rdx, r12; unsigned __int16 *
0x180010d51  mov     rcx, [rsp+338h+var_308]; HKEY
0x180010d56  call    ?HrRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; HrRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x180010d5b  mov     ecx, [rsp+338h+var_228]
0x180010d62  mov     edx, 7FFFFFFFh
0x180010d67  cmp     eax, 80070002h
0x180010d6c  cmovz   ecx, edx
0x180010d6f  mov     [rsp+338h+var_228], ecx
0x180010d76  mov     r14d, esi
0x180010d79  cmovnz  r14d, eax
0x180010d7d  test    r14d, r14d
0x180010d80  jnz     loc_180010E5D
0x180010d86  lea     r9, [rsp+338h+var_268]
0x180010d8e  cmp     [rsp+338h+var_250], r13
0x180010d96  cmova   r9, qword ptr [rsp+338h+var_268]
0x180010d9f  lea     r8, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\%s"...
0x180010da6  mov     edx, 0EAh; unsigned __int64
0x180010dab  lea     rcx, [rsp+338h+var_218]; unsigned __int16 *
0x180010db3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010db8  lea     r9, [rsp+338h+hKey]; HKEY *
0x180010dbd  mov     r8d, 20019h; unsigned int
0x180010dc3  lea     rdx, [rsp+338h+var_218]; unsigned __int16 *
0x180010dcb  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180010dd2  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x180010dd7  mov     r14d, eax
0x180010dda  test    eax, eax
0x180010ddc  jnz     short loc_180010E5D
0x180010dde  lea     rdx, [rsp+338h+var_248]
0x180010de6  mov     rcx, [rsp+338h+hKey]; hKey
0x180010deb  call    ?HrGetNetworkProviderName@@YAJPEAUHKEY__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HrGetNetworkProviderName(HKEY__ *,std::wstring &)
0x180010df0  mov     r14d, eax
0x180010df3  test    eax, eax
0x180010df5  jnz     short loc_180010E52
0x180010df7  lea     rax, [rsp+338h+var_2D8]
0x180010dfc  mov     [rsp+338h+var_300], rax
0x180010e01  lea     rdx, [rsp+338h+var_268]
0x180010e09  lea     rcx, [rsp+338h+var_2D8]
0x180010e0e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010e13  nop
0x180010e14  lea     rdx, [rsp+338h+var_248]
0x180010e1c  lea     rcx, [rsp+338h+var_2B8]
0x180010e24  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010e29  mov     eax, [rsp+338h+var_228]
0x180010e30  mov     [rsp+338h+var_298], eax
0x180010e37  mov     al, [rsp+338h+var_224]
0x180010e3e  mov     [rsp+338h+var_294], al
0x180010e45  lea     rdx, [rsp+338h+var_2D8]
0x180010e4a  mov     rcx, r15
0x180010e4d  call    ?AddToProviderOrderList@@YAXAEAV?$list@UProviderOrder@@V?$allocator@UProviderOrder@@@std@@@std@@UProviderOrder@@@Z; AddToProviderOrderList(std::list<ProviderOrder> &,ProviderOrder)
0x180010e52  lea     rcx, [rsp+338h+hKey]; this
0x180010e57  call    ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
0x180010e5c  nop
0x180010e5d  lea     rcx, [rsp+338h+var_248]
0x180010e65  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010e6a  lea     rcx, [rsp+338h+var_268]
0x180010e72  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010e77  nop
0x180010e78  jmp     short loc_180010E91
0x180010e7a  mov     ecx, 5
0x180010e7f  int     29h; Win8: RtlFailFast(ecx)
0x180010e81  xor     esi, esi
0x180010e83  lea     r13d, [rsi+7]
0x180010e87  mov     r14d, dword ptr [rsp+338h+var_318]
0x180010e8c  mov     r15, [rsp+338h+var_2F0]
0x180010e91  mov     rax, [rsp+338h+var_2F8]
0x180010e96  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180010e9a  test    rax, rax
0x180010e9d  jz      short loc_180010EA8
0x180010e9f  lea     r12, [rax+2]
0x180010ea3  jmp     loc_180010B29
0x180010ea8  mov     rcx, [rsp+338h+lpMem]; lpMem
0x180010ead  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180010eb2  mov     r13, [rsp+338h+var_2E0]
0x180010eb7  lea     rcx, [rsp+338h+var_308]; this
0x180010ebc  call    ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
0x180010ec1  test    r14d, r14d
0x180010ec4  jz      short loc_180010F16
0x180010ec6  mov     rcx, [r15]
0x180010ec9  mov     rax, [rcx+8]
0x180010ecd  mov     [rax], rsi
0x180010ed0  mov     r12, [rcx]
0x180010ed3  test    r12, r12
0x180010ed6  jz      short loc_180010F05
0x180010ed8  mov     rdi, [r12]
0x180010edc  lea     rcx, [r12+30h]
0x180010ee1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010ee6  lea     rcx, [r12+10h]
0x180010eeb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010ef0  mov     edx, 58h ; 'X'; unsigned __int64
0x180010ef5  mov     rcx, r12; void *
0x180010ef8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010efd  mov     r12, rdi
0x180010f00  test    rdi, rdi
0x180010f03  jnz     short loc_180010ED8
0x180010f05  mov     rax, [r15]
0x180010f08  mov     [rax], rax
0x180010f0b  mov     rax, [r15]
0x180010f0e  mov     [rax+8], rax
0x180010f12  mov     [r13+0], rsi
0x180010f16  mov     eax, r14d
0x180010f19  mov     rcx, [rsp+338h+var_38]
0x180010f21  xor     rcx, rsp; StackCookie
0x180010f24  call    __security_check_cookie
0x180010f29  lea     r11, [rsp+338h+var_28]
0x180010f31  mov     rbx, [r11+38h]
0x180010f35  mov     rsi, [r11+48h]
0x180010f39  mov     rsp, r11
0x180010f3c  pop     r15
0x180010f3e  pop     r14
0x180010f40  pop     r13
0x180010f42  pop     r12
0x180010f44  pop     rdi
0x180010f45  retn
0x180010f46  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
