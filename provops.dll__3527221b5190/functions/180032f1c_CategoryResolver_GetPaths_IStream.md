# CategoryResolver::GetPaths(IStream *)

- ea: `0x180032f1c`
- end: `0x18003339a`
- name: `?GetPaths@CategoryResolver@@QEAA?AV?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@PEAUIStream@@@Z`
- size: `1150`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, IUnknown *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18002e740`

## callees

- `0x180004d68`
- `0x18000cbe4`
- `0x18000de00`
- `0x18001b388`
- `0x18002066c`
- `0x1800210f0`
- `0x180028d48`
- `0x180032dc8`
- `0x180032f1c`
- `0x18003348c`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800331b9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033278`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800331b9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033278`
- `msvcrt!_wcsicmp` at `0x180032fd4`
- `msvcrt!_wcsicmp` at `0x18003306c`
- `msvcrt!_wcsicmp` at `0x18003308a`
- `msvcrt!_wcsicmp` at `0x18003309f`
- `msvcrt!_wcsicmp` at `0x180032fd4`
- `msvcrt!_wcsicmp` at `0x18003306c`
- `msvcrt!_wcsicmp` at `0x18003308a`
- `msvcrt!_wcsicmp` at `0x18003309f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall CategoryResolver::GetPaths(__int64 a1, _QWORD *a2, IUnknown *a3)
{
  int v4; // r13d
  void **v5; // r12
  int v6; // eax
  char v7; // r15
  void **v8; // rbx
  void **v9; // r14
  int v10; // eax
  int v11; // esi
  int v12; // eax
  const wchar_t *v13; // rdx
  int v14; // eax
  int v15; // eax
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // rsi
  unsigned __int64 v18; // r8
  __int64 v19; // rsi
  void *v20; // rcx
  unsigned int v22; // eax
  unsigned int v23; // eax
  int v24; // [rsp+20h] [rbp-49h] BYREF
  void *ppvObject; // [rsp+28h] [rbp-41h] BYREF
  wchar_t *String2; // [rsp+30h] [rbp-39h] BYREF
  __int128 v27; // [rsp+38h] [rbp-31h] BYREF
  void **v28; // [rsp+48h] [rbp-21h]
  int v29; // [rsp+50h] [rbp-19h]
  int v30; // [rsp+54h] [rbp-15h]
  void *Src[2]; // [rsp+58h] [rbp-11h] BYREF
  void *v32[3]; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int64 v33; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  Src[1] = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v4 = 1;
  v29 = 1;
  v27 = 0;
  v5 = 0;
  v28 = 0;
  v24 = 0;
  CreateReaderOnStream(&ppvObject, a3);
  while ( !(*(unsigned int (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v24) )
  {
    if ( v24 == 1 )
    {
      String2 = 0;
      v6 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
             ppvObject,
             &String2,
             0);
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x20,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
          (const char *)(unsigned int)v6,
          v24);
      if ( _wcsicmp(L"wap-provisioningdoc", String2) )
      {
        v22 = wil::verify_hresult<long>(0x8000FFFF);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5D,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
          (const char *)v22,
          v24);
      }
      break;
    }
  }
  v7 = 0;
  v8 = (void **)*((_QWORD *)&v27 + 1);
  v9 = (void **)v27;
  while ( 1 )
  {
    v10 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v24);
    if ( v10 )
      break;
    if ( v24 == 1 )
    {
      v11 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject);
      v30 = v11;
      String2 = 0;
      Src[0] = 0;
      v12 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
              ppvObject,
              &String2,
              0);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x27,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
          (const char *)(unsigned int)v12,
          v24);
      if ( _wcsicmp(L"characteristic", String2) )
      {
        if ( _wcsicmp(L"parm", String2) && _wcsicmp(L"noparm", String2) )
        {
          v23 = wil::verify_hresult<long>(0x8000FFFF);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x32,
            (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
            (const char *)v23,
            v24);
        }
        v13 = L"name";
      }
      else
      {
        v13 = L"type";
      }
      v14 = (*(__int64 (__fastcall **)(void *, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 80LL))(
              ppvObject,
              v13,
              0);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x35,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
          (const char *)(unsigned int)v14,
          v24);
      v15 = (*(__int64 (__fastcall **)(void *, void **, _QWORD))(*(_QWORD *)ppvObject + 128LL))(ppvObject, Src, 0);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x36,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
          (const char *)(unsigned int)v15,
          v24);
      v33 = 7;
      v32[2] = 0;
      LOWORD(v32[0]) = 0;
      if ( *(_WORD *)Src[0] )
      {
        v16 = -1;
        do
          ++v16;
        while ( *((_WORD *)Src[0] + v16) );
      }
      else
      {
        v16 = 0;
      }
      std::wstring::assign(v32, (char *)Src[0], v16);
      v4 |= 4u;
      v29 = v4;
      if ( v32 >= v8 || v9 > v32 )
      {
        if ( v8 == v5 )
        {
          std::vector<std::wstring>::_Reserve(&v27);
          v5 = v28;
          v8 = (void **)*((_QWORD *)&v27 + 1);
          v9 = (void **)v27;
        }
        std::wstring::wstring(v8, v32);
      }
      else
      {
        v17 = (char *)v32 - (char *)v9;
        if ( v8 == v5 )
        {
          std::vector<std::wstring>::_Reserve(&v27);
          v5 = v28;
          v8 = (void **)*((_QWORD *)&v27 + 1);
          v9 = (void **)v27;
        }
        std::wstring::wstring(v8, (void **)((char *)v9 + (v17 & 0xFFFFFFFFFFFFFFE0uLL)));
        v11 = v30;
      }
      v8 += 4;
      *((_QWORD *)&v27 + 1) = v8;
      if ( v33 >= 8 )
        operator delete(v32[0]);
      v7 = 1;
      if ( v11 )
      {
LABEL_34:
        if ( v7 )
        {
          v7 = 0;
          v18 = a2[1];
          if ( (unsigned __int64)&v27 >= v18 || *a2 > (unsigned __int64)&v27 )
          {
            if ( v18 == a2[2] )
              std::vector<std::vector<std::wstring>>::_Reserve(a2);
            std::vector<std::wstring>::vector<std::wstring>(a2[1], &v27);
            a2[1] += 24LL;
          }
          else
          {
            v19 = ((__int64)&v27 - *a2) / 24;
            if ( v18 == a2[2] )
              std::vector<std::vector<std::wstring>>::_Reserve(a2);
            std::vector<std::wstring>::vector<std::wstring>(a2[1], *a2 + 24 * v19);
            a2[1] += 24LL;
          }
        }
        if ( v9 != v8 )
        {
          v8 -= 4;
          if ( (unsigned __int64)v8[3] >= 8 )
            operator delete(*v8);
          v8[3] = (void *)7;
          v8[2] = 0;
          *(_WORD *)v8 = 0;
          *((_QWORD *)&v27 + 1) = v8;
        }
      }
    }
    else if ( v24 == 15 )
    {
      goto LABEL_34;
    }
  }
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
      (const char *)(unsigned int)v10,
      v24);
  v20 = ppvObject;
  if ( ppvObject )
  {
    ppvObject = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
  }
  std::vector<std::wstring>::_Tidy((__int64)&v27);
  return a2;
}

```

## disassembly

```asm
0x180032f1c  mov     [rsp-8+arg_0], rbx
0x180032f21  push    rbp
0x180032f22  push    rsi
0x180032f23  push    rdi
0x180032f24  push    r12
0x180032f26  push    r13
0x180032f28  push    r14
0x180032f2a  push    r15
0x180032f2c  lea     rbp, [rsp-27h]
0x180032f31  sub     rsp, 90h
0x180032f38  mov     rax, cs:__security_cookie
0x180032f3f  xor     rax, rsp
0x180032f42  mov     [rbp+57h+var_38], rax
0x180032f46  mov     rdi, rdx
0x180032f49  mov     [rbp+57h+var_60], rdx
0x180032f4d  xor     esi, esi
0x180032f4f  mov     [rbp+57h+var_70], esi
0x180032f52  mov     [rdx], rsi
0x180032f55  mov     [rdx+8], rsi
0x180032f59  mov     [rdx+10h], rsi
0x180032f5d  lea     r13d, [rsi+1]
0x180032f61  mov     [rbp+57h+var_70], r13d
0x180032f65  xorps   xmm0, xmm0
0x180032f68  movdqu  [rbp+57h+var_88], xmm0
0x180032f6d  mov     r12d, esi
0x180032f70  mov     [rbp+57h+var_78], rsi
0x180032f74  mov     [rbp+57h+var_A0], esi
0x180032f77  mov     rdx, r8; pInputStream
0x180032f7a  lea     rcx, [rbp+57h+ppvObject]; ppvObject
0x180032f7e  call    CreateReaderOnStream
0x180032f83  nop
0x180032f84  mov     rcx, [rbp+57h+ppvObject]
0x180032f88  mov     rax, [rcx]
0x180032f8b  lea     rdx, [rbp+57h+var_A0]
0x180032f8f  mov     rax, [rax+30h]
0x180032f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f98  test    eax, eax
0x180032f9a  jnz     short loc_180032FE2
0x180032f9c  cmp     [rbp+57h+var_A0], 1
0x180032fa0  jnz     short loc_180032F84
0x180032fa2  mov     [rbp+57h+String2], rsi
0x180032fa6  mov     rcx, [rbp+57h+ppvObject]
0x180032faa  mov     rax, [rcx]
0x180032fad  xor     r8d, r8d
0x180032fb0  lea     rdx, [rbp+57h+String2]
0x180032fb4  mov     rax, [rax+70h]
0x180032fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032fbd  mov     rcx, [rbp+5Fh]; this
0x180032fc1  test    eax, eax
0x180032fc3  js      loc_180033323
0x180032fc9  mov     rdx, [rbp+57h+String2]; String2
0x180032fcd  lea     rcx, aWapProvisionin; "wap-provisioningdoc"
0x180032fd4  call    cs:__imp__wcsicmp
0x180032fda  test    eax, eax
0x180032fdc  jnz     loc_180033300
0x180032fe2  mov     r15b, sil
0x180032fe5  mov     rbx, qword ptr [rbp+57h+var_88+8]
0x180032fe9  mov     r14, qword ptr [rbp+57h+var_88]
0x180032fed  mov     rcx, [rbp+57h+ppvObject]
0x180032ff1  mov     rax, [rcx]
0x180032ff4  lea     rdx, [rbp+57h+var_A0]
0x180032ff8  mov     rax, [rax+30h]
0x180032ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033001  test    eax, eax
0x180033003  jnz     loc_180033296
0x180033009  mov     ecx, [rbp+57h+var_A0]
0x18003300c  sub     ecx, 1
0x18003300f  jz      short loc_18003301B
0x180033011  cmp     ecx, 0Eh
0x180033014  jnz     short loc_180032FED
0x180033016  jmp     loc_1800331CF
0x18003301b  mov     rcx, [rbp+57h+ppvObject]
0x18003301f  mov     rax, [rcx]
0x180033022  mov     rax, [rax+0A0h]
0x180033029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003302e  mov     esi, eax
0x180033030  mov     [rbp+57h+var_6C], eax
0x180033033  xor     r15d, r15d
0x180033036  mov     [rbp+57h+String2], r15
0x18003303a  mov     [rbp+57h+Src], r15
0x18003303e  mov     rcx, [rbp+57h+ppvObject]
0x180033042  mov     rax, [rcx]
0x180033045  xor     r8d, r8d
0x180033048  lea     rdx, [rbp+57h+String2]
0x18003304c  mov     rax, [rax+70h]
0x180033050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033055  mov     rcx, [rbp+5Fh]; this
0x180033059  test    eax, eax
0x18003305b  js      loc_180033385
0x180033061  mov     rdx, [rbp+57h+String2]; String2
0x180033065  lea     rcx, aCharacteristic; "characteristic"
0x18003306c  call    cs:__imp__wcsicmp
0x180033072  test    eax, eax
0x180033074  jnz     short loc_18003307F
0x180033076  lea     rdx, aType; "type"
0x18003307d  jmp     short loc_1800330B4
0x18003307f  mov     rdx, [rbp+57h+String2]; String2
0x180033083  lea     rcx, aParm; "parm"
0x18003308a  call    cs:__imp__wcsicmp
0x180033090  test    eax, eax
0x180033092  jz      short loc_1800330AD
0x180033094  mov     rdx, [rbp+57h+String2]; String2
0x180033098  lea     rcx, aNoparm; "noparm"
0x18003309f  call    cs:__imp__wcsicmp
0x1800330a5  test    eax, eax
0x1800330a7  jnz     loc_180033338
0x1800330ad  lea     rdx, aName; "name"
0x1800330b4  mov     rcx, [rbp+57h+ppvObject]
0x1800330b8  mov     rax, [rcx]
0x1800330bb  xor     r8d, r8d
0x1800330be  mov     rax, [rax+50h]
0x1800330c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330c7  mov     rcx, [rbp+5Fh]; this
0x1800330cb  test    eax, eax
0x1800330cd  js      loc_180033370
0x1800330d3  mov     rcx, [rbp+57h+ppvObject]
0x1800330d7  mov     rax, [rcx]
0x1800330da  xor     r8d, r8d
0x1800330dd  lea     rdx, [rbp+57h+Src]
0x1800330e1  mov     rax, [rax+80h]
0x1800330e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330ed  mov     rcx, [rbp+5Fh]; this
0x1800330f1  test    eax, eax
0x1800330f3  js      loc_18003335B
0x1800330f9  mov     rdx, [rbp+57h+Src]; Src
0x1800330fd  mov     [rbp+57h+var_40], 7
0x180033105  mov     [rbp+57h+var_48], r15
0x180033109  mov     word ptr [rbp+57h+var_58], r15w
0x18003310e  cmp     [rdx], r15w
0x180033112  jnz     short loc_180033119
0x180033114  mov     r8, r15
0x180033117  jmp     short loc_180033127
0x180033119  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003311d  inc     r8
0x180033120  cmp     [rdx+r8*2], r15w
0x180033125  jnz     short loc_18003311D
0x180033127  lea     rcx, [rbp+57h+var_58]; void *
0x18003312b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180033130  or      r13d, 4
0x180033134  mov     [rbp+57h+var_70], r13d
0x180033138  lea     rax, [rbp+57h+var_58]
0x18003313c  cmp     rax, rbx
0x18003313f  jnb     short loc_180033180
0x180033141  lea     rax, [rbp+57h+var_58]
0x180033145  cmp     r14, rax
0x180033148  ja      short loc_180033180
0x18003314a  lea     rsi, [rbp+57h+var_58]
0x18003314e  sub     rsi, r14
0x180033151  cmp     rbx, r12
0x180033154  jnz     short loc_18003316B
0x180033156  lea     rcx, [rbp+57h+var_88]
0x18003315a  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x18003315f  mov     r12, [rbp+57h+var_78]
0x180033163  mov     rbx, qword ptr [rbp+57h+var_88+8]
0x180033167  mov     r14, qword ptr [rbp+57h+var_88]
0x18003316b  and     rsi, 0FFFFFFFFFFFFFFE0h
0x18003316f  lea     rdx, [r14+rsi]
0x180033173  mov     rcx, rbx
0x180033176  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18003317b  mov     esi, [rbp+57h+var_6C]
0x18003317e  jmp     short loc_1800331A6
0x180033180  cmp     rbx, r12
0x180033183  jnz     short loc_18003319A
0x180033185  lea     rcx, [rbp+57h+var_88]
0x180033189  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x18003318e  mov     r12, [rbp+57h+var_78]
0x180033192  mov     rbx, qword ptr [rbp+57h+var_88+8]
0x180033196  mov     r14, qword ptr [rbp+57h+var_88]
0x18003319a  lea     rdx, [rbp+57h+var_58]
0x18003319e  mov     rcx, rbx
0x1800331a1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800331a6  add     rbx, 20h ; ' '
0x1800331aa  mov     qword ptr [rbp+57h+var_88+8], rbx
0x1800331ae  cmp     [rbp+57h+var_40], 8
0x1800331b3  jb      short loc_1800331BF
0x1800331b5  mov     rcx, [rbp+57h+var_58]
0x1800331b9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800331bf  mov     r15b, 1
0x1800331c2  test    esi, esi
0x1800331c4  mov     esi, 0
0x1800331c9  jz      loc_180032FED
0x1800331cf  test    r15b, r15b
0x1800331d2  jz      loc_180033261
0x1800331d8  mov     r15b, sil
0x1800331db  mov     r8, [rdi+8]
0x1800331df  lea     rax, [rbp+57h+var_88]
0x1800331e3  cmp     rax, r8
0x1800331e6  jnb     short loc_180033241
0x1800331e8  lea     rax, [rbp+57h+var_88]
0x1800331ec  cmp     [rdi], rax
0x1800331ef  ja      short loc_180033241
0x1800331f1  lea     rcx, [rbp+57h+var_88]
0x1800331f5  sub     rcx, [rdi]
0x1800331f8  mov     rax, 2AAAAAAAAAAAAAABh
0x180033202  imul    rcx
0x180033205  mov     rsi, rdx
0x180033208  sar     rsi, 2
0x18003320c  mov     rax, rsi
0x18003320f  shr     rax, 3Fh
0x180033213  add     rsi, rax
0x180033216  cmp     r8, [rdi+10h]
0x18003321a  jnz     short loc_180033224
0x18003321c  mov     rcx, rdi
0x18003321f  call    ?_Reserve@?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::vector<std::wstring>>::_Reserve(unsigned __int64)
0x180033224  lea     rcx, [rsi+rsi*2]
0x180033228  mov     rax, [rdi]
0x18003322b  lea     rdx, [rax+rcx*8]
0x18003322f  mov     rcx, [rdi+8]
0x180033233  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180033238  add     qword ptr [rdi+8], 18h
0x18003323d  xor     esi, esi
0x18003323f  jmp     short loc_180033261
0x180033241  cmp     r8, [rdi+10h]
0x180033245  jnz     short loc_18003324F
0x180033247  mov     rcx, rdi
0x18003324a  call    ?_Reserve@?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::vector<std::wstring>>::_Reserve(unsigned __int64)
0x18003324f  lea     rdx, [rbp+57h+var_88]
0x180033253  mov     rcx, [rdi+8]
0x180033257  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x18003325c  add     qword ptr [rdi+8], 18h
0x180033261  cmp     r14, rbx
0x180033264  jz      loc_180032FED
0x18003326a  add     rbx, 0FFFFFFFFFFFFFFE0h
0x18003326e  cmp     qword ptr [rbx+18h], 8
0x180033273  jb      short loc_18003327E
0x180033275  mov     rcx, [rbx]
0x180033278  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003327e  mov     qword ptr [rbx+18h], 7
0x180033286  mov     [rbx+10h], rsi
0x18003328a  mov     [rbx], si
0x18003328d  mov     qword ptr [rbp+57h+var_88+8], rbx
0x180033291  jmp     loc_180032FED
0x180033296  mov     rcx, [rbp+5Fh]; this
0x18003329a  test    eax, eax
0x18003329c  js      short loc_1800332EB
0x18003329e  mov     rcx, [rbp+57h+ppvObject]
0x1800332a2  test    rcx, rcx
0x1800332a5  jz      short loc_1800332B8
0x1800332a7  mov     [rbp+57h+ppvObject], rsi
0x1800332ab  mov     rdx, [rcx]
0x1800332ae  mov     rax, [rdx+10h]
0x1800332b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332b7  nop
0x1800332b8  lea     rcx, [rbp+57h+var_88]
0x1800332bc  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800332c1  mov     rax, rdi
0x1800332c4  mov     rcx, [rbp+57h+var_38]
0x1800332c8  xor     rcx, rsp; StackCookie
0x1800332cb  call    __security_check_cookie
0x1800332d0  mov     rbx, [rsp+0C0h+arg_0]
0x1800332d8  add     rsp, 90h
0x1800332df  pop     r15
0x1800332e1  pop     r14
0x1800332e3  pop     r13
0x1800332e5  pop     r12
0x1800332e7  pop     rdi
0x1800332e8  pop     rsi
0x1800332e9  pop     rbp
0x1800332ea  retn
0x1800332eb  mov     r9d, eax; char *
0x1800332ee  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x1800332f5  mov     edx, 86h; void *
0x1800332fa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033300  mov     ecx, 8000FFFFh
0x180033305  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18003330a  mov     r9d, eax; char *
0x18003330d  mov     rcx, [rbp+5Fh]; this
0x180033311  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x180033318  mov     edx, 5Dh ; ']'; void *
0x18003331d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033323  mov     r9d, eax; char *
0x180033326  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x18003332d  mov     edx, 20h ; ' '; void *
0x180033332  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033338  mov     ecx, 8000FFFFh
0x18003333d  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180033342  mov     r9d, eax; char *
0x180033345  mov     rcx, [rbp+5Fh]; this
0x180033349  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x180033350  mov     edx, 32h ; '2'; void *
0x180033355  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003335b  mov     r9d, eax; char *
0x18003335e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x180033365  mov     edx, 36h ; '6'; void *
0x18003336a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033370  mov     r9d, eax; char *
0x180033373  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x18003337a  mov     edx, 35h ; '5'; void *
0x18003337f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033385  mov     r9d, eax; char *
0x180033388  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x18003338f  mov     edx, 27h ; '''; void *
0x180033394  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
